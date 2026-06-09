# ATL::CAtlExeModuleT<Windows::Globalization::Spelling::CHostModule>::PreMessageLoop(int)

- ea: `0x1400046e8`
- end: `0x1400048c8`
- name: `?PreMessageLoop@?$CAtlExeModuleT@VCHostModule@Spelling@Globalization@Windows@@@ATL@@QEAAJH@Z`
- size: `480`
- prototype: `__int64 __fastcall(IUnknown *, DWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000584c`

## callees

- `0x1400046e8`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x140004897`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x140004897`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x140004830`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x140004865`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x140004830`
- `api-ms-win-core-com-l1-1-0!CoResumeClassObjects` at `0x140004865`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x140004779`
- `api-ms-win-core-com-l1-1-0!CoRegisterClassObject` at `0x140004779`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14000480e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14000480e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004823`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000485d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004823`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000485d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140004854`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140004854`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400047d0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1400047d0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140004843`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140004843`

## pseudocode

```c
__int64 __fastcall ATL::CAtlExeModuleT<Windows::Globalization::Spelling::CHostModule>::PreMessageLoop(
        IUnknown *a1,
        DWORD a2)
{
  HRESULT v2; // ebx
  struct ATL::_ATL_OBJMAP_ENTRY30 **v3; // rdi
  __int64 *v4; // rax
  struct ATL::_ATL_OBJMAP_ENTRY30 *v5; // rsi
  HANDLE v6; // rdi
  HRESULT v7; // eax
  struct ATL::_ATL_OBJMAP_ENTRY30 **v8; // rdi
  __int64 *v9; // rcx
  struct ATL::_ATL_OBJMAP_ENTRY30 *v10; // rdx
  LPUNKNOWN pUnk; // [rsp+40h] [rbp+8h] BYREF
  DWORD ThreadId; // [rsp+48h] [rbp+10h] BYREF

  ThreadId = a2;
  pUnk = a1;
  v2 = 1;
  v3 = off_14001B2E0;
  v4 = off_14001B2E8;
  if ( off_14001B2E0 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)off_14001B2E8 )
  {
    do
    {
      if ( v2 < 0 )
        return (unsigned int)v2;
      v5 = *v3;
      if ( *v3 )
      {
        pUnk = 0;
        if ( *((_QWORD *)v5 + 2) )
        {
          v2 = (*((__int64 (__fastcall **)(_QWORD, GUID *, LPUNKNOWN *))v5 + 2))(
                 *((_QWORD *)v5 + 3),
                 &GUID_00000000_0000_0000_c000_000000000046,
                 &pUnk);
          if ( v2 >= 0 )
            v2 = CoRegisterClassObject(*(const IID *const *)v5, pUnk, 4u, 5u, (LPDWORD)v5 + 10);
          if ( pUnk )
            ((void (__fastcall *)(LPUNKNOWN))pUnk->lpVtbl->Release)(pUnk);
          v4 = off_14001B2E8;
        }
        else
        {
          v2 = 0;
        }
      }
      ++v3;
    }
    while ( v3 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v4 );
    if ( v2 < 0 )
      return (unsigned int)v2;
    if ( !v2 )
    {
      if ( byte_14001C030 )
      {
        hEvent = CreateEventW(0, 0, 0, 0);
        if ( !hEvent )
        {
LABEL_18:
          v2 = -2147467259;
LABEL_24:
          v7 = 0;
          v8 = off_14001B2E0;
          v9 = off_14001B2E8;
          while ( v8 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v9 && !v7 )
          {
            v10 = *v8;
            if ( *v8 && *((_DWORD *)v10 + 10) )
            {
              v7 = CoRevokeClassObject(*((_DWORD *)v10 + 10));
              v9 = off_14001B2E8;
            }
            ++v8;
          }
          return (unsigned int)v2;
        }
        ThreadId = 0;
        v6 = CreateThread(
               0,
               0,
               ATL::CAtlExeModuleT<Windows::Globalization::Spelling::CHostModule>::MonitorProc,
               &Windows::Globalization::Spelling::_AtlModule,
               0,
               &ThreadId);
        if ( !v6 )
        {
          CloseHandle(hEvent);
          goto LABEL_18;
        }
        v2 = CoResumeClassObjects();
        if ( v2 < 0 )
        {
          SetEvent(hEvent);
          WaitForSingleObject(v6, 2 * dword_14001C028);
        }
        CloseHandle(v6);
      }
      else
      {
        v2 = CoResumeClassObjects();
      }
      if ( v2 >= 0 )
        return (unsigned int)v2;
      goto LABEL_24;
    }
  }
  byte_14001C030 = 0;
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400046e8  mov     rax, rsp
0x1400046eb  mov     [rax+18h], rbx
0x1400046ef  mov     [rax+20h], rsi
0x1400046f3  mov     [rax+10h], edx
0x1400046f6  mov     [rax+8], rcx
0x1400046fa  push    rdi
0x1400046fb  sub     rsp, 30h
0x1400046ff  mov     ebx, 1
0x140004704  mov     rdi, cs:off_14001B2E0
0x14000470b  mov     rax, cs:off_14001B2E8
0x140004712  cmp     rdi, rax
0x140004715  jnb     loc_1400048AF
0x14000471b  test    ebx, ebx
0x14000471d  js      loc_1400048B6
0x140004723  mov     rsi, [rdi]
0x140004726  test    rsi, rsi
0x140004729  jz      short loc_14000479E
0x14000472b  mov     [rsp+38h+pUnk], 0
0x140004734  cmp     qword ptr [rsi+10h], 0
0x140004739  jnz     short loc_14000473F
0x14000473b  xor     ebx, ebx
0x14000473d  jmp     short loc_14000479E
0x14000473f  lea     r8, [rsp+38h+pUnk]
0x140004744  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x14000474b  mov     rcx, [rsi+18h]
0x14000474f  mov     rax, [rsi+10h]
0x140004753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004758  mov     ebx, eax
0x14000475a  test    eax, eax
0x14000475c  js      short loc_140004781
0x14000475e  lea     rax, [rsi+28h]
0x140004762  mov     [rsp+38h+lpdwRegister], rax; lpdwRegister
0x140004767  mov     r9d, 5; flags
0x14000476d  lea     r8d, [r9-1]; dwClsContext
0x140004771  mov     rdx, [rsp+38h+pUnk]; pUnk
0x140004776  mov     rcx, [rsi]; rclsid
0x140004779  call    cs:__imp_CoRegisterClassObject
0x14000477f  mov     ebx, eax
0x140004781  mov     rcx, [rsp+38h+pUnk]
0x140004786  test    rcx, rcx
0x140004789  jz      short loc_140004797
0x14000478b  mov     rax, [rcx]
0x14000478e  mov     rax, [rax+10h]
0x140004792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004797  mov     rax, cs:off_14001B2E8
0x14000479e  add     rdi, 8
0x1400047a2  cmp     rdi, rax
0x1400047a5  jb      loc_14000471B
0x1400047ab  test    ebx, ebx
0x1400047ad  js      loc_1400048B6
0x1400047b3  jnz     loc_1400048AF
0x1400047b9  cmp     cs:byte_14001C030, 0
0x1400047c0  jz      loc_140004865
0x1400047c6  xor     r9d, r9d; lpName
0x1400047c9  xor     r8d, r8d; bInitialState
0x1400047cc  xor     edx, edx; bManualReset
0x1400047ce  xor     ecx, ecx; lpEventAttributes
0x1400047d0  call    cs:__imp_CreateEventW
0x1400047d6  mov     cs:hEvent, rax
0x1400047dd  test    rax, rax
0x1400047e0  jz      short loc_140004829
0x1400047e2  mov     [rsp+38h+ThreadId], 0
0x1400047ea  lea     rax, [rsp+38h+ThreadId]
0x1400047ef  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x1400047f4  mov     dword ptr [rsp+38h+lpdwRegister], 0; dwCreationFlags
0x1400047fc  lea     r9, ?_AtlModule@Spelling@Globalization@Windows@@3VCHostModule@123@A; lpParameter
0x140004803  lea     r8, ?MonitorProc@?$CAtlExeModuleT@VCHostModule@Spelling@Globalization@Windows@@@ATL@@SAKPEAX@Z; lpStartAddress
0x14000480a  xor     edx, edx; dwStackSize
0x14000480c  xor     ecx, ecx; lpThreadAttributes
0x14000480e  call    cs:__imp_CreateThread
0x140004814  mov     rdi, rax
0x140004817  test    rax, rax
0x14000481a  jnz     short loc_140004830
0x14000481c  mov     rcx, cs:hEvent; hObject
0x140004823  call    cs:__imp_CloseHandle
0x140004829  mov     ebx, 80004005h
0x14000482e  jmp     short loc_140004871
0x140004830  call    cs:__imp_CoResumeClassObjects
0x140004836  mov     ebx, eax
0x140004838  test    eax, eax
0x14000483a  jns     short loc_14000485A
0x14000483c  mov     rcx, cs:hEvent; hEvent
0x140004843  call    cs:__imp_SetEvent
0x140004849  mov     edx, cs:dword_14001C028
0x14000484f  add     edx, edx; dwMilliseconds
0x140004851  mov     rcx, rdi; hHandle
0x140004854  call    cs:__imp_WaitForSingleObject
0x14000485a  mov     rcx, rdi; hObject
0x14000485d  call    cs:__imp_CloseHandle
0x140004863  jmp     short loc_14000486D
0x140004865  call    cs:__imp_CoResumeClassObjects
0x14000486b  mov     ebx, eax
0x14000486d  test    ebx, ebx
0x14000486f  jns     short loc_1400048B6
0x140004871  xor     eax, eax
0x140004873  mov     rdi, cs:off_14001B2E0
0x14000487a  mov     rcx, cs:off_14001B2E8
0x140004881  jmp     short loc_1400048A8
0x140004883  test    eax, eax
0x140004885  jnz     short loc_1400048B6
0x140004887  mov     rdx, [rdi]
0x14000488a  test    rdx, rdx
0x14000488d  jz      short loc_1400048A4
0x14000488f  cmp     [rdx+28h], eax
0x140004892  jz      short loc_1400048A4
0x140004894  mov     ecx, [rdx+28h]; dwRegister
0x140004897  call    cs:__imp_CoRevokeClassObject
0x14000489d  mov     rcx, cs:off_14001B2E8
0x1400048a4  add     rdi, 8
0x1400048a8  cmp     rdi, rcx
0x1400048ab  jb      short loc_140004883
0x1400048ad  jmp     short loc_1400048B6
0x1400048af  mov     cs:byte_14001C030, 0
0x1400048b6  mov     eax, ebx
0x1400048b8  mov     rbx, [rsp+38h+arg_10]
0x1400048bd  mov     rsi, [rsp+38h+arg_18]
0x1400048c2  add     rsp, 30h
0x1400048c6  pop     rdi
0x1400048c7  retn
```
