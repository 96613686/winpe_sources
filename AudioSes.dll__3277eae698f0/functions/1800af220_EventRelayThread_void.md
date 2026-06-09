# EventRelayThread(void *)

- ea: `0x1800af220`
- end: `0x1800af3fc`
- name: `?EventRelayThread@@YAKPEAX@Z`
- size: `476`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180007f00`
- `0x180082830`
- `0x180087e80`
- `0x1800af220`
- `0x1800b0dac`
- `0x1800b18f0`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800af38a`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800af38a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800af3b4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800af3c0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800af3b4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800af3c0`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800af3aa`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800af3aa`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800af2cc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800af2cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800af344`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800af344`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!SetThreadAffinityMask` at `0x1800af350`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!SetThreadAffinityMask` at `0x1800af350`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800af31b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800af31b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800af2e3`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800af2e3`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x1800af3ce`
- `AVRT!AvRevertMmThreadCharacteristics` at `0x1800af3ce`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x1800af261`
- `AVRT!AvSetMmThreadCharacteristicsW` at `0x1800af261`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall EventRelayThread(HANDLE *Parameter)
{
  HANDLE v2; // rsi
  const char *v3; // r9
  DWORD_PTR v4; // rbx
  HANDLE CurrentThread; // rax
  DWORD v6; // eax
  void *v7; // rdx
  unsigned int v8; // r8d
  const char *v9; // r9
  DWORD TaskIndex; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-BCh] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-B8h] BYREF
  DWORD_PTR dwThreadAffinityMask; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE *v15; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE Handles[2]; // [rsp+60h] [rbp-A0h] BYREF
  GUID pclsid; // [rsp+70h] [rbp-90h] BYREF
  OLECHAR sz[512]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4B8h] [rbp+3B8h]

  v15 = Parameter;
  TaskIndex = 0;
  v2 = AvSetMmThreadCharacteristicsW(L"Audio", &TaskIndex);
  if ( !v2 )
    wil::details::in1diag3::_Log_GetLastError(
      retaddr,
      (void *)0x17,
      (unsigned int)"avcore\\audiocore\\client\\audioclient\\guestaudioclientcore.cpp",
      v3);
  pclsid = 0;
  pcbData = 1024;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Audio",
          L"CrossVmGuestRTProperties",
          2u,
          0,
          sz,
          &pcbData)
    && CLSIDFromString(sz, &pclsid) >= 0 )
  {
    dwThreadAffinityMask = 0;
    ppv = 0;
    if ( CoCreateInstance(&pclsid, 0, 1u, &GUID_316ab5e2_69f2_463e_bb17_b23c22aa324c, &ppv) >= 0
      && (*(int (__fastcall **)(LPVOID, DWORD_PTR *))(*(_QWORD *)ppv + 24LL))(ppv, &dwThreadAffinityMask) >= 0 )
    {
      v4 = dwThreadAffinityMask;
      CurrentThread = GetCurrentThread();
      SetThreadAffinityMask(CurrentThread, v4);
    }
    wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(&ppv);
  }
  Handles[0] = Parameter[2];
  Handles[1] = *Parameter;
  while ( 1 )
  {
    v6 = WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0);
    if ( !v6 )
      break;
    if ( v6 == 1 )
    {
      ResetEvent(*Parameter);
      SetEvent(Parameter[1]);
    }
    else
    {
      wil::details::in1diag3::Log_GetLastError(retaddr, v7, v8, v9);
    }
  }
  SetEvent(Parameter[1]);
  if ( v2 )
    AvRevertMmThreadCharacteristics(v2);
  std::unique_ptr<EventRelayThreadContext>::~unique_ptr<EventRelayThreadContext>(&v15);
  return 0;
}

```

## disassembly

```asm
0x1800af220  push    rbp
0x1800af222  push    rbx
0x1800af223  push    rsi
0x1800af224  push    rdi
0x1800af225  lea     rbp, [rsp-398h]
0x1800af22d  sub     rsp, 498h
0x1800af234  mov     rax, cs:__security_cookie
0x1800af23b  xor     rax, rsp
0x1800af23e  mov     [rbp+3B0h+var_30], rax
0x1800af245  mov     rdi, rcx
0x1800af248  mov     [rsp+4B0h+var_458], rcx
0x1800af24d  mov     [rsp+4B0h+TaskIndex], 0
0x1800af255  lea     rdx, [rsp+4B0h+TaskIndex]; TaskIndex
0x1800af25a  lea     rcx, TaskName; "Audio"
0x1800af261  call    cs:__imp_AvSetMmThreadCharacteristicsW
0x1800af267  mov     rsi, rax
0x1800af26a  mov     rcx, [rbp+3B8h]; this
0x1800af271  test    rax, rax
0x1800af274  jnz     short loc_1800AF285
0x1800af276  lea     r8, aAvcoreAudiocor_66; "avcore\\audiocore\\client\\audioclient"...
0x1800af27d  lea     edx, [rax+17h]; void *
0x1800af280  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x1800af285  xorps   xmm0, xmm0
0x1800af288  movups  xmmword ptr [rsp+4B0h+pclsid.Data1], xmm0
0x1800af28d  mov     [rsp+4B0h+var_46C], 400h
0x1800af295  lea     rax, [rsp+4B0h+var_46C]
0x1800af29a  mov     [rsp+4B0h+pcbData], rax; pcbData
0x1800af29f  lea     rax, [rbp+3B0h+sz]
0x1800af2a3  mov     [rsp+4B0h+pvData], rax; pvData
0x1800af2a8  mov     [rsp+4B0h+pdwType], 0; pdwType
0x1800af2b1  mov     r9d, 2; dwFlags
0x1800af2b7  lea     r8, aCrossvmguestrt; "CrossVmGuestRTProperties"
0x1800af2be  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800af2c5  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800af2cc  call    cs:__imp_RegGetValueW
0x1800af2d2  test    eax, eax
0x1800af2d4  jnz     loc_1800AF361
0x1800af2da  lea     rdx, [rsp+4B0h+pclsid]; pclsid
0x1800af2df  lea     rcx, [rbp+3B0h+sz]; lpsz
0x1800af2e3  call    cs:__imp_CLSIDFromString
0x1800af2e9  test    eax, eax
0x1800af2eb  js      short loc_1800AF361
0x1800af2ed  mov     [rsp+4B0h+dwThreadAffinityMask], 0
0x1800af2f6  mov     [rsp+4B0h+ppv], 0
0x1800af2ff  lea     rax, [rsp+4B0h+ppv]
0x1800af304  mov     [rsp+4B0h+pdwType], rax; ppv
0x1800af309  lea     r9, _GUID_316ab5e2_69f2_463e_bb17_b23c22aa324c; riid
0x1800af310  xor     edx, edx; pUnkOuter
0x1800af312  lea     r8d, [rdx+1]; dwClsContext
0x1800af316  lea     rcx, [rsp+4B0h+pclsid]; rclsid
0x1800af31b  call    cs:__imp_CoCreateInstance
0x1800af321  test    eax, eax
0x1800af323  js      short loc_1800AF357
0x1800af325  mov     rcx, [rsp+4B0h+ppv]
0x1800af32a  mov     rax, [rcx]
0x1800af32d  lea     rdx, [rsp+4B0h+dwThreadAffinityMask]
0x1800af332  mov     rax, [rax+18h]
0x1800af336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800af33b  test    eax, eax
0x1800af33d  js      short loc_1800AF357
0x1800af33f  mov     rbx, [rsp+4B0h+dwThreadAffinityMask]
0x1800af344  call    cs:__imp_GetCurrentThread
0x1800af34a  mov     rdx, rbx; dwThreadAffinityMask
0x1800af34d  mov     rcx, rax; hThread
0x1800af350  call    cs:__imp_SetThreadAffinityMask
0x1800af356  nop
0x1800af357  lea     rcx, [rsp+4B0h+ppv]; void *
0x1800af35c  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x1800af361  mov     rax, [rdi+10h]
0x1800af365  mov     [rsp+4B0h+Handles], rax
0x1800af36a  mov     rax, [rdi]
0x1800af36d  mov     [rsp+4B0h+var_448], rax
0x1800af372  mov     dword ptr [rsp+4B0h+pdwType], 0; bAlertable
0x1800af37a  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800af37e  xor     r8d, r8d; bWaitAll
0x1800af381  lea     rdx, [rsp+4B0h+Handles]; lpHandles
0x1800af386  lea     ecx, [r8+2]; nCount
0x1800af38a  call    cs:__imp_WaitForMultipleObjectsEx
0x1800af390  test    eax, eax
0x1800af392  jz      short loc_1800AF3BC
0x1800af394  cmp     eax, 1
0x1800af397  jz      short loc_1800AF3A7
0x1800af399  mov     rcx, [rbp+3B8h]; this
0x1800af3a0  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x1800af3a5  jmp     short loc_1800AF372
0x1800af3a7  mov     rcx, [rdi]; hEvent
0x1800af3aa  call    cs:__imp_ResetEvent
0x1800af3b0  mov     rcx, [rdi+8]; hEvent
0x1800af3b4  call    cs:__imp_SetEvent
0x1800af3ba  jmp     short loc_1800AF372
0x1800af3bc  mov     rcx, [rdi+8]; hEvent
0x1800af3c0  call    cs:__imp_SetEvent
0x1800af3c6  test    rsi, rsi
0x1800af3c9  jz      short loc_1800AF3D5
0x1800af3cb  mov     rcx, rsi; AvrtHandle
0x1800af3ce  call    cs:__imp_AvRevertMmThreadCharacteristics
0x1800af3d4  nop
0x1800af3d5  lea     rcx, [rsp+4B0h+var_458]
0x1800af3da  call    ??1?$unique_ptr@UEventRelayThreadContext@@U?$default_delete@UEventRelayThreadContext@@@std@@@std@@QEAA@XZ; std::unique_ptr<EventRelayThreadContext>::~unique_ptr<EventRelayThreadContext>(void)
0x1800af3df  xor     eax, eax
0x1800af3e1  mov     rcx, [rbp+3B0h+var_30]
0x1800af3e8  xor     rcx, rsp; StackCookie
0x1800af3eb  call    __security_check_cookie
0x1800af3f0  add     rsp, 498h
0x1800af3f7  pop     rdi
0x1800af3f8  pop     rsi
0x1800af3f9  pop     rbx
0x1800af3fa  pop     rbp
0x1800af3fb  retn
```
