# Host::PreMessageLoop(int)

- ea: `0x140006dcc`
- end: `0x140007048`
- name: `?PreMessageLoop@Host@@QEAAJH@Z`
- size: `636`
- prototype: `__int64 __fastcall(IUnknown *this, DWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140007050`

## callees

- `0x140005dc8`
- `0x14000634c`
- `0x140006dcc`
- `0x140008010`

## import_xrefs

- `KERNEL32!WaitForSingleObject` at `0x140006f3a`
- `KERNEL32!WaitForSingleObject` at `0x140006f3a`
- `KERNEL32!CloseHandle` at `0x140006f00`
- `KERNEL32!CloseHandle` at `0x140006f9b`
- `KERNEL32!CloseHandle` at `0x140006f00`
- `KERNEL32!CloseHandle` at `0x140006f9b`
- `KERNEL32!SetEvent` at `0x140006f24`
- `KERNEL32!SetEvent` at `0x140006f24`
- `KERNEL32!CreateEventW` at `0x140006ea9`
- `KERNEL32!CreateEventW` at `0x140006ea9`
- `KERNEL32!CreateThread` at `0x140006eeb`
- `KERNEL32!CreateThread` at `0x140006eeb`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x140006e58`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x140006e58`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x140006f7c`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x140006f7c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140006fd6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140006fd6`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x140006f11`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x140006fa3`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x140006f11`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x140006fa3`

## pseudocode

```c
__int64 __fastcall Host::PreMessageLoop(IUnknown *this, DWORD a2)
{
  struct ATL::_ATL_OBJMAP_ENTRY30 **v2; // rbx
  HRESULT Instance; // edi
  __int64 *v4; // rax
  struct ATL::_ATL_OBJMAP_ENTRY30 *v5; // rsi
  bool v6; // zf
  NCoreLibrary *v7; // rcx
  HANDLE v8; // rbx
  int LastErrorAsHResult; // eax
  struct ATL::_ATL_OBJMAP_ENTRY30 **v10; // rsi
  __int64 *v11; // rdx
  HRESULT v12; // eax
  DWORD v13; // ecx
  LPUNKNOWN pUnk; // [rsp+40h] [rbp+8h] BYREF
  DWORD ThreadId; // [rsp+48h] [rbp+10h] BYREF

  ThreadId = a2;
  pUnk = this;
  v2 = off_14000C0E0;
  Instance = 1;
  v4 = off_14000C0E8;
  while ( v2 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v4 )
  {
    if ( Instance < 0 )
      goto LABEL_40;
    v5 = *v2;
    if ( *v2 )
    {
      v6 = *((_QWORD *)v5 + 2) == 0;
      pUnk = 0;
      if ( v6 )
      {
        Instance = 0;
      }
      else
      {
        Instance = (*((__int64 (__fastcall **)(_QWORD, GUID *, LPUNKNOWN *))v5 + 2))(
                     *((_QWORD *)v5 + 3),
                     &GUID_00000000_0000_0000_c000_000000000046,
                     &pUnk);
        if ( Instance >= 0 )
          Instance = CoRegisterClassObject(*(const IID *const *)v5, pUnk, 4u, 4u, (LPDWORD)v5 + 10);
        if ( pUnk )
          ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
        v4 = off_14000C0E8;
      }
    }
    ++v2;
  }
  if ( Instance < 0 )
  {
LABEL_40:
    byte_14000C580 = 0;
LABEL_41:
    SandboxTelemetry::WriteDbgTraceError(
      "Host::PreMessageLoop",
      L"Sandbox Host: PreMessageLoop failed. Error hr: 0x%x",
      (unsigned int)Instance);
    return (unsigned int)Instance;
  }
  if ( !byte_14000C580 )
  {
    Instance = CoResumeClassObjects();
    goto LABEL_33;
  }
  hEvent = CreateEventW(0, 0, 0, 0);
  if ( !hEvent )
    goto LABEL_21;
  ThreadId = 0;
  v8 = CreateThread(0, 0, Host::MonitorProc, &_AtlModule, 0, &ThreadId);
  if ( !v8 )
  {
    CloseHandle(hEvent);
LABEL_21:
    LastErrorAsHResult = NCoreLibrary::GetLastErrorAsHResult(v7);
    v10 = off_14000C0E0;
    Instance = LastErrorAsHResult;
    v11 = off_14000C0E8;
    if ( LastErrorAsHResult >= 0 )
      Instance = -2147024890;
    v12 = 0;
    while ( v10 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v11 && !v12 )
    {
      if ( *v10 )
      {
        v13 = *((_DWORD *)*v10 + 10);
        if ( v13 )
        {
          v12 = CoRevokeClassObject(v13);
          v11 = off_14000C0E8;
        }
      }
      ++v10;
    }
    goto LABEL_33;
  }
  if ( v8 == (HANDLE)-1LL )
    goto LABEL_21;
  Instance = CoResumeClassObjects();
  if ( Instance < 0 )
  {
    SetEvent(hEvent);
    WaitForSingleObject(v8, dwMilliseconds);
  }
  CloseHandle(v8);
LABEL_33:
  if ( Instance < 0 )
    goto LABEL_41;
  pUnk = 0;
  Instance = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &IID_IGlobalOptions, (LPVOID *)&pUnk);
  if ( Instance >= 0 )
    Instance = ((__int64 (__fastcall *)(LPUNKNOWN, __int64, __int64))pUnk->lpVtbl[1].QueryInterface)(pUnk, 1, 1);
  if ( pUnk )
    ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
  if ( Instance < 0 )
    goto LABEL_41;
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x140006dcc  mov     rax, rsp
0x140006dcf  mov     [rax+18h], rbx
0x140006dd3  mov     [rax+20h], rsi
0x140006dd7  mov     [rax+10h], edx
0x140006dda  mov     [rax+8], rcx
0x140006dde  push    rdi
0x140006ddf  sub     rsp, 30h
0x140006de3  mov     rbx, cs:off_14000C0E0
0x140006dea  mov     edi, 1
0x140006def  mov     rax, cs:off_14000C0E8
0x140006df6  jmp     loc_140006E81
0x140006dfb  test    edi, edi
0x140006dfd  js      loc_140007019
0x140006e03  mov     rsi, [rbx]
0x140006e06  test    rsi, rsi
0x140006e09  jz      short loc_140006E7D
0x140006e0b  cmp     qword ptr [rsi+10h], 0
0x140006e10  mov     [rsp+38h+pUnk], 0
0x140006e19  jnz     short loc_140006E1F
0x140006e1b  xor     edi, edi
0x140006e1d  jmp     short loc_140006E7D
0x140006e1f  mov     rcx, [rsi+18h]
0x140006e23  lea     r8, [rsp+38h+pUnk]
0x140006e28  mov     rax, [rsi+10h]
0x140006e2c  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x140006e33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006e38  mov     edi, eax
0x140006e3a  test    eax, eax
0x140006e3c  js      short loc_140006E60
0x140006e3e  mov     rdx, [rsp+38h+pUnk]; pUnk
0x140006e43  lea     rax, [rsi+28h]
0x140006e47  mov     rcx, [rsi]; rclsid
0x140006e4a  mov     r9d, 4; flags
0x140006e50  mov     r8d, r9d; dwClsContext
0x140006e53  mov     [rsp+38h+lpdwRegister], rax; lpdwRegister
0x140006e58  call    cs:__imp_CoRegisterClassObject
0x140006e5e  mov     edi, eax
0x140006e60  mov     rcx, [rsp+38h+pUnk]
0x140006e65  test    rcx, rcx
0x140006e68  jz      short loc_140006E76
0x140006e6a  mov     rax, [rcx]
0x140006e6d  mov     rax, [rax+10h]
0x140006e71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006e76  mov     rax, cs:off_14000C0E8
0x140006e7d  add     rbx, 8
0x140006e81  cmp     rbx, rax
0x140006e84  jb      loc_140006DFB
0x140006e8a  test    edi, edi
0x140006e8c  js      loc_140007019
0x140006e92  cmp     cs:byte_14000C580, 0
0x140006e99  jz      loc_140006FA3
0x140006e9f  xor     r9d, r9d; lpName
0x140006ea2  xor     r8d, r8d; bInitialState
0x140006ea5  xor     edx, edx; bManualReset
0x140006ea7  xor     ecx, ecx; lpEventAttributes
0x140006ea9  call    cs:__imp_CreateEventW
0x140006eaf  mov     cs:hEvent, rax
0x140006eb6  test    rax, rax
0x140006eb9  jz      loc_140006F42
0x140006ebf  lea     rax, [rsp+38h+ThreadId]
0x140006ec4  mov     [rsp+38h+ThreadId], 0
0x140006ecc  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x140006ed1  lea     r9, ?_AtlModule@@3VHost@@A; lpParameter
0x140006ed8  lea     r8, ?MonitorProc@Host@@SAKPEAX@Z; lpStartAddress
0x140006edf  mov     dword ptr [rsp+38h+lpdwRegister], 0; dwCreationFlags
0x140006ee7  xor     edx, edx; dwStackSize
0x140006ee9  xor     ecx, ecx; lpThreadAttributes
0x140006eeb  call    cs:__imp_CreateThread
0x140006ef1  mov     rbx, rax
0x140006ef4  test    rax, rax
0x140006ef7  jnz     short loc_140006F06
0x140006ef9  mov     rcx, cs:hEvent; hObject
0x140006f00  call    cs:__imp_CloseHandle
0x140006f06  test    rbx, rbx
0x140006f09  jz      short loc_140006F42
0x140006f0b  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140006f0f  jz      short loc_140006F46
0x140006f11  call    cs:__imp_CoResumeClassObjects
0x140006f17  mov     edi, eax
0x140006f19  test    eax, eax
0x140006f1b  jns     short loc_140006F98
0x140006f1d  mov     rcx, cs:hEvent; hEvent
0x140006f24  call    cs:__imp_SetEvent
0x140006f2a  mov     edx, cs:dwMilliseconds; dwMilliseconds
0x140006f30  xor     ecx, ecx
0x140006f32  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140006f36  cmovnz  rcx, rbx; hHandle
0x140006f3a  call    cs:__imp_WaitForSingleObject
0x140006f40  jmp     short loc_140006F98
0x140006f42  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140006f46  call    ?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsHResult(void)
0x140006f4b  mov     rsi, cs:off_14000C0E0
0x140006f52  mov     edi, eax
0x140006f54  mov     rdx, cs:off_14000C0E8
0x140006f5b  test    edi, edi
0x140006f5d  mov     eax, 80070006h
0x140006f62  cmovns  edi, eax
0x140006f65  xor     eax, eax
0x140006f67  jmp     short loc_140006F8D
0x140006f69  test    eax, eax
0x140006f6b  jnz     short loc_140006F92
0x140006f6d  mov     rcx, [rsi]
0x140006f70  test    rcx, rcx
0x140006f73  jz      short loc_140006F89
0x140006f75  mov     ecx, [rcx+28h]; dwRegister
0x140006f78  test    ecx, ecx
0x140006f7a  jz      short loc_140006F89
0x140006f7c  call    cs:__imp_CoRevokeClassObject
0x140006f82  mov     rdx, cs:off_14000C0E8
0x140006f89  add     rsi, 8
0x140006f8d  cmp     rsi, rdx
0x140006f90  jb      short loc_140006F69
0x140006f92  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140006f96  jz      short loc_140006FAB
0x140006f98  mov     rcx, rbx; hObject
0x140006f9b  call    cs:__imp_CloseHandle
0x140006fa1  jmp     short loc_140006FAB
0x140006fa3  call    cs:__imp_CoResumeClassObjects
0x140006fa9  mov     edi, eax
0x140006fab  test    edi, edi
0x140006fad  js      short loc_140007020
0x140006faf  xor     edx, edx; pUnkOuter
0x140006fb1  mov     [rsp+38h+pUnk], 0
0x140006fba  lea     rax, [rsp+38h+pUnk]
0x140006fbf  lea     r9, IID_IGlobalOptions; riid
0x140006fc6  mov     [rsp+38h+lpdwRegister], rax; ppv
0x140006fcb  lea     rcx, CLSID_GlobalOptions; rclsid
0x140006fd2  lea     r8d, [rdx+1]; dwClsContext
0x140006fd6  call    cs:__imp_CoCreateInstance
0x140006fdc  mov     edi, eax
0x140006fde  test    eax, eax
0x140006fe0  js      short loc_140006FFD
0x140006fe2  mov     rcx, [rsp+38h+pUnk]
0x140006fe7  mov     edx, 1
0x140006fec  mov     r8d, edx
0x140006fef  mov     rax, [rcx]
0x140006ff2  mov     rax, [rax+18h]
0x140006ff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006ffb  mov     edi, eax
0x140006ffd  mov     rcx, [rsp+38h+pUnk]
0x140007002  test    rcx, rcx
0x140007005  jz      short loc_140007013
0x140007007  mov     rax, [rcx]
0x14000700a  mov     rax, [rax+10h]
0x14000700e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007013  test    edi, edi
0x140007015  jns     short loc_140007036
0x140007017  jmp     short loc_140007020
0x140007019  mov     cs:byte_14000C580, 0
0x140007020  mov     r8d, edi
0x140007023  lea     rdx, aSandboxHostPre; "Sandbox Host: PreMessageLoop failed. Er"...
0x14000702a  lea     rcx, aHostPremessage; "Host::PreMessageLoop"
0x140007031  call    ?WriteDbgTraceError@SandboxTelemetry@@SAXPEADPEAGZZ; SandboxTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x140007036  mov     rbx, [rsp+38h+arg_10]
0x14000703b  mov     eax, edi
0x14000703d  mov     rsi, [rsp+38h+arg_18]
0x140007042  add     rsp, 30h
0x140007046  pop     rdi
0x140007047  retn
```
