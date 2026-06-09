# CRemoveDeviceContextHandler::_ExecuteRemoveDevice(IShellItemArray *,DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity &&)

- ea: `0x18000b5dc`
- end: `0x18000b960`
- name: `?_ExecuteRemoveDevice@CRemoveDeviceContextHandler@@AEAAJPEAUIShellItemArray@@$$QEAVRemoveDeviceActivity@DeviceCenterContextHandlersTelemetry@@@Z`
- size: `900`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, loader_planting`

## callers

- `0x1800085b0`

## callees

- `0x180001be0`
- `0x180001c04`
- `0x180005860`
- `0x180005d1c`
- `0x180005ea4`
- `0x180005f24`
- `0x180007434`
- `0x180008214`
- `0x1800088f0`
- `0x18000b5dc`
- `0x18000b968`
- `0x18000bdec`
- `0x18000be1c`
- `0x18000c7a0`
- `0x18000c966`
- `0x18000c990`
- `0x18000e010`

## import_xrefs

- `SHELL32!__imp_ILFree` at `0x18000b8b4`
- `SHELL32!__imp_ILFree` at `0x18000b8b4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b87e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b87e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b88c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b88c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b82c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b82c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000b809`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18000b809`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b817`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b817`
- `USER32!GetForegroundWindow` at `0x18000b76c`
- `USER32!GetForegroundWindow` at `0x18000b76c`
- `USER32!DestroyIcon` at `0x18000b8c3`
- `USER32!DestroyIcon` at `0x18000b8c3`

## string_xrefs

- `0x18000b68e`: `RemoveDeviceActivity`

## pseudocode

```c
__int64 __fastcall CRemoveDeviceContextHandler::_ExecuteRemoveDevice(__int64 a1, __int64 *a2, __int64 a3)
{
  __int64 v5; // rax
  signed int v6; // edi
  __int64 v7; // r8
  char *v8; // rax
  unsigned int v9; // r8d
  char *v10; // rsi
  char *v11; // rdi
  char *v12; // rbx
  LPITEMIDLIST *v13; // r15
  HICON *v14; // r13
  __int64 v15; // rdx
  int v16; // eax
  unsigned int v17; // r8d
  HANDLE Thread; // rax
  signed int LastError; // eax
  unsigned int v20; // r8d
  void *v21; // rbx
  HANDLE ProcessHeap; // rax
  DWORD dwCreationFlags; // [rsp+20h] [rbp-E0h]
  DWORD dwCreationFlagsa; // [rsp+20h] [rbp-E0h]
  __int64 v26; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v27; // [rsp+38h] [rbp-C8h] BYREF
  char v28[16]; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp-B0h]
  char v30; // [rsp+58h] [rbp-A8h]
  char v31[48]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v32[42]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18);
  v5 = *a2;
  v26 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v5 + 64))(a2, 0, &v26);
  if ( v6 >= 0 )
  {
    v8 = (char *)operator new(0x168u);
    v10 = v8;
    if ( v8 )
    {
      v11 = v8 + 24;
      v12 = v8 + 32;
      *((_DWORD *)v8 + 8) = 0;
      *((_QWORD *)v8 + 33) = 0;
      *((_QWORD *)v8 + 34) = 0;
      v8[36] = 0;
      v8[96] = 0;
      *((_DWORD *)v8 + 18) = 0;
      *((_QWORD *)v8 + 10) = "RemoveDeviceActivity";
      *((_QWORD *)v8 + 11) = 0;
      *((_DWORD *)v8 + 26) = 0;
      memset_0(v8 + 112, 0, 0x98u);
      *((_DWORD *)v12 + 62) = 1;
      v13 = (LPITEMIDLIST *)(v10 + 8);
      v14 = (HICON *)(v10 + 16);
      *((_QWORD *)v12 + 32) = 0;
      *((_QWORD *)v11 + 35) = 0;
      *((_QWORD *)v11 + 34) = v12;
      *((_QWORD *)v11 + 36) = 0;
      *((_QWORD *)v11 + 38) = 0;
      *((_DWORD *)v11 + 78) = 0;
      v11[328] = 0;
      *((_QWORD *)v11 + 40) = v11 + 48;
      *((_QWORD *)v11 + 37) = v11;
      *(_QWORD *)v11 = &DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity::`vftable';
      *(_QWORD *)v10 = 0;
      *((_QWORD *)v10 + 1) = 0;
      *((_QWORD *)v10 + 2) = 0;
      wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(
        (__int64)v32,
        (__int64)(v10 + 24),
        *((_DWORD *)v10 + 84) != 0);
      v32[0] = &DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity::`vftable';
      wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::operator=(
        (__int64)(v10 + 24),
        a3);
      DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity::~RemoveDeviceActivity((DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity *)v32);
      GetIconFromItem(v26, v15, v10 + 16);
      *(_QWORD *)v10 = GetForegroundWindow();
      v27 = 0;
      v6 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v26)(
             v26,
             &GUID_1079acfc_29bd_11d3_8e0d_00c04f6837d5,
             &v27);
      if ( v6 >= 0 )
      {
        v16 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v27 + 40LL))(v27, v10 + 8);
        v6 = v16;
        if ( v16 >= 0 )
        {
          wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(v10 + 24);
          (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
          Thread = CreateThread(0, 0, CRemoveDeviceContextHandler::ExecuteRemoveDeviceThreadProc, v10, 0, 0);
          if ( Thread )
          {
            CloseHandle(Thread);
          }
          else
          {
            wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ContinueOnCurrentThread(
              v10 + 24,
              v28);
            LastError = GetLastError();
            v6 = LastError;
            if ( LastError > 0 )
              v6 = (unsigned __int16)LastError | 0x80070000;
            wil::details::in1diag3::Log_Hr(
              retaddr,
              (void *)0x14C,
              v20,
              (const char *)(unsigned int)v6,
              dwCreationFlagsa);
            (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
            wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v31);
            if ( v30 )
            {
              v21 = lpMem;
              ProcessHeap = GetProcessHeap();
              HeapFree(ProcessHeap, 0, v21);
            }
          }
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x13A, v17, (const char *)(unsigned int)v16, dwCreationFlags);
        }
      }
      if ( v27 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      if ( v6 < 0 )
      {
        if ( *v13 )
          ILFree(*v13);
        if ( *v14 )
          DestroyIcon(*v14);
        DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity::~RemoveDeviceActivity((DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity *)(v10 + 24));
        operator delete(v10);
      }
    }
    else
    {
      v6 = -2147024882;
      wil::details::in1diag3::Log_Hr(retaddr, (void *)0x12B, v9, (const char *)0x8007000ELL, dwCreationFlags);
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, v7, (unsigned int)v6);
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000b5dc  mov     [rsp-8+arg_0], rbx
0x18000b5e1  push    rbp
0x18000b5e2  push    rsi
0x18000b5e3  push    rdi
0x18000b5e4  push    r12
0x18000b5e6  push    r13
0x18000b5e8  push    r14
0x18000b5ea  push    r15
0x18000b5ec  lea     rbp, [rsp-0F0h]
0x18000b5f4  sub     rsp, 1F0h
0x18000b5fb  mov     rax, cs:__security_cookie
0x18000b602  xor     rax, rsp
0x18000b605  mov     [rbp+120h+var_40], rax
0x18000b60c  mov     r12, r8
0x18000b60f  mov     rbx, rdx
0x18000b612  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b619  lea     rax, WPP_GLOBAL_Control
0x18000b620  cmp     rcx, rax
0x18000b623  jz      short loc_18000B639
0x18000b625  test    byte ptr [rcx+1Ch], 20h
0x18000b629  jz      short loc_18000B639
0x18000b62b  mov     rcx, [rcx+10h]
0x18000b62f  mov     edx, 12h
0x18000b634  call    WPP_SF_
0x18000b639  mov     rax, [rbx]
0x18000b63c  lea     r8, [rsp+220h+var_1F0]
0x18000b641  xor     r14d, r14d
0x18000b644  xor     edx, edx
0x18000b646  mov     rcx, rbx
0x18000b649  mov     [rsp+220h+var_1F0], r14
0x18000b64e  mov     rax, [rax+40h]
0x18000b652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b657  mov     edi, eax
0x18000b659  test    eax, eax
0x18000b65b  js      loc_18000B8F4
0x18000b661  mov     ecx, 168h; Size
0x18000b666  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b66b  mov     rsi, rax
0x18000b66e  test    rax, rax
0x18000b671  jz      loc_18000B8DB
0x18000b677  lea     rdi, [rax+18h]
0x18000b67b  xor     edx, edx; Val
0x18000b67d  lea     rbx, [rdi+8]
0x18000b681  mov     r8d, 98h; Size
0x18000b687  lea     rcx, [rbx+50h]; void *
0x18000b68b  mov     [rbx], r14d
0x18000b68e  lea     rax, aRemovedeviceac; "RemoveDeviceActivity"
0x18000b695  mov     [rcx+98h], r14
0x18000b69c  mov     [rcx+0A0h], r14
0x18000b6a3  mov     [rbx+4], r14b
0x18000b6a7  mov     [rbx+40h], r14b
0x18000b6ab  mov     [rbx+28h], r14d
0x18000b6af  mov     [rbx+30h], rax
0x18000b6b3  mov     [rbx+38h], r14
0x18000b6b7  mov     [rbx+48h], r14d
0x18000b6bb  call    memset_0
0x18000b6c0  mov     dword ptr [rbx+0F8h], 1
0x18000b6ca  lea     r15, [rsi+8]
0x18000b6ce  xor     eax, eax
0x18000b6d0  lea     r13, [rsi+10h]
0x18000b6d4  mov     [rbx+100h], rax
0x18000b6db  lea     rcx, [rbp+120h+var_190]
0x18000b6df  mov     [rdi+118h], r14
0x18000b6e6  lea     rax, [rdi+30h]
0x18000b6ea  mov     [rdi+110h], rbx
0x18000b6f1  lea     rbx, ??_7RemoveDeviceActivity@DeviceCenterContextHandlersTelemetry@@6B@; const DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity::`vftable'
0x18000b6f8  mov     [rdi+120h], r14
0x18000b6ff  mov     [rdi+130h], r14
0x18000b706  mov     [rdi+138h], r14d
0x18000b70d  mov     [rdi+148h], r14b
0x18000b714  mov     [rdi+140h], rax
0x18000b71b  mov     [rdi+128h], rdi
0x18000b722  mov     [rdi], rbx
0x18000b725  mov     [rsi], r14
0x18000b728  mov     [r15], r14
0x18000b72b  mov     [r13+0], r14
0x18000b72f  lea     r14, [rsi+18h]
0x18000b733  cmp     dword ptr [r14+138h], 0
0x18000b73b  mov     rdx, r14
0x18000b73e  setnz   r8b
0x18000b742  call    ??0?$ActivityBase@VDeviceCenterContextHandlersLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@_N@Z; wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType> &&,bool)
0x18000b747  mov     rdx, r12
0x18000b74a  mov     [rbp+120h+var_190], rbx
0x18000b74e  mov     rcx, r14
0x18000b751  call    ??4?$ActivityBase@VDeviceCenterContextHandlersLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::operator=(wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType> &&)
0x18000b756  lea     rcx, [rbp+120h+var_190]; this
0x18000b75a  call    ??1RemoveDeviceActivity@DeviceCenterContextHandlersTelemetry@@QEAA@XZ; DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity::~RemoveDeviceActivity(void)
0x18000b75f  mov     rcx, [rsp+220h+var_1F0]
0x18000b764  mov     r8, r13
0x18000b767  call    GetIconFromItem
0x18000b76c  call    cs:__imp_GetForegroundWindow
0x18000b772  mov     [rsi], rax
0x18000b775  xor     r12d, r12d
0x18000b778  mov     rcx, [rsp+220h+var_1F0]
0x18000b77d  lea     r8, [rsp+220h+var_1E8]
0x18000b782  mov     [rsp+220h+var_1E8], r12
0x18000b787  lea     rdx, _GUID_1079acfc_29bd_11d3_8e0d_00c04f6837d5
0x18000b78e  mov     rax, [rcx]
0x18000b791  mov     rax, [rax]
0x18000b794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b799  mov     edi, eax
0x18000b79b  test    eax, eax
0x18000b79d  js      loc_18000B892
0x18000b7a3  mov     rcx, [rsp+220h+var_1E8]
0x18000b7a8  mov     rdx, r15
0x18000b7ab  mov     rax, [rcx]
0x18000b7ae  mov     rax, [rax+28h]
0x18000b7b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7b7  mov     edi, eax
0x18000b7b9  test    eax, eax
0x18000b7bb  jns     short loc_18000B7D6
0x18000b7bd  mov     rcx, [rbp+128h]; this
0x18000b7c4  mov     r9d, eax; char *
0x18000b7c7  mov     edx, 13Ah; void *
0x18000b7cc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000b7d1  jmp     loc_18000B892
0x18000b7d6  mov     rcx, r14
0x18000b7d9  call    ?IgnoreCurrentThread@?$ActivityBase@VDeviceCenterContextHandlersLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18000b7de  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000b7e5  mov     rax, [rcx]
0x18000b7e8  mov     rax, [rax+8]
0x18000b7ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7f1  mov     r9, rsi; lpParameter
0x18000b7f4  mov     [rsp+220h+lpThreadId], r12; lpThreadId
0x18000b7f9  lea     r8, ?ExecuteRemoveDeviceThreadProc@CRemoveDeviceContextHandler@@SAKPEAX@Z; lpStartAddress
0x18000b800  mov     [rsp+220h+dwCreationFlags], r12d; int
0x18000b805  xor     edx, edx; dwStackSize
0x18000b807  xor     ecx, ecx; lpThreadAttributes
0x18000b809  call    cs:__imp_CreateThread
0x18000b80f  test    rax, rax
0x18000b812  jz      short loc_18000B81F
0x18000b814  mov     rcx, rax; hObject
0x18000b817  call    cs:__imp_CloseHandle
0x18000b81d  jmp     short loc_18000B892
0x18000b81f  lea     rdx, [rsp+220h+var_1E0]
0x18000b824  mov     rcx, r14
0x18000b827  call    ?ContinueOnCurrentThread@?$ActivityBase@VDeviceCenterContextHandlersLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA?AVActivityThreadWatcher@2@XZ; wil::ActivityBase<DeviceCenterContextHandlersLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ContinueOnCurrentThread(void)
0x18000b82c  call    cs:__imp_GetLastError
0x18000b832  mov     edi, eax
0x18000b834  test    eax, eax
0x18000b836  jle     short loc_18000B841
0x18000b838  movzx   edi, ax
0x18000b83b  or      edi, 80070000h
0x18000b841  mov     rcx, [rbp+128h]; this
0x18000b848  mov     r9d, edi; char *
0x18000b84b  mov     edx, 14Ch; void *
0x18000b850  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18000b855  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000b85c  mov     rax, [rcx]
0x18000b85f  mov     rax, [rax+10h]
0x18000b863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b868  lea     rcx, [rsp+220h+var_1C0]; this
0x18000b86d  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x18000b872  cmp     [rsp+220h+var_1C8], r12b
0x18000b877  jz      short loc_18000B892
0x18000b879  mov     rbx, [rsp+220h+lpMem]
0x18000b87e  call    cs:__imp_GetProcessHeap
0x18000b884  mov     r8, rbx; lpMem
0x18000b887  xor     edx, edx; dwFlags
0x18000b889  mov     rcx, rax; hHeap
0x18000b88c  call    cs:__imp_HeapFree
0x18000b892  mov     rcx, [rsp+220h+var_1E8]
0x18000b897  test    rcx, rcx
0x18000b89a  jz      short loc_18000B8A8
0x18000b89c  mov     rax, [rcx]
0x18000b89f  mov     rax, [rax+10h]
0x18000b8a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8a8  test    edi, edi
0x18000b8aa  jns     short loc_18000B8F4
0x18000b8ac  mov     rcx, [r15]; pidl
0x18000b8af  test    rcx, rcx
0x18000b8b2  jz      short loc_18000B8BA
0x18000b8b4  call    cs:__imp_ILFree
0x18000b8ba  mov     rcx, [r13+0]; hIcon
0x18000b8be  test    rcx, rcx
0x18000b8c1  jz      short loc_18000B8C9
0x18000b8c3  call    cs:__imp_DestroyIcon
0x18000b8c9  mov     rcx, r14; this
0x18000b8cc  call    ??1RemoveDeviceActivity@DeviceCenterContextHandlersTelemetry@@QEAA@XZ; DeviceCenterContextHandlersTelemetry::RemoveDeviceActivity::~RemoveDeviceActivity(void)
0x18000b8d1  mov     rcx, rsi; Block
0x18000b8d4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000b8d9  jmp     short loc_18000B8F4
0x18000b8db  mov     rcx, [rbp+128h]; this
0x18000b8e2  mov     edi, 8007000Eh
0x18000b8e7  mov     r9d, edi; char *
0x18000b8ea  mov     edx, 12Bh; void *
0x18000b8ef  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18000b8f4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b8fb  lea     rax, WPP_GLOBAL_Control
0x18000b902  cmp     rcx, rax
0x18000b905  jz      short loc_18000B91E
0x18000b907  test    byte ptr [rcx+1Ch], 20h
0x18000b90b  jz      short loc_18000B91E
0x18000b90d  mov     rcx, [rcx+10h]
0x18000b911  mov     edx, 13h
0x18000b916  mov     r9d, edi
0x18000b919  call    WPP_SF_d
0x18000b91e  mov     rcx, [rsp+220h+var_1F0]
0x18000b923  test    rcx, rcx
0x18000b926  jz      short loc_18000B934
0x18000b928  mov     rax, [rcx]
0x18000b92b  mov     rax, [rax+10h]
0x18000b92f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b934  mov     eax, edi
0x18000b936  mov     rcx, [rbp+120h+var_40]
0x18000b93d  xor     rcx, rsp; StackCookie
0x18000b940  call    __security_check_cookie
0x18000b945  mov     rbx, [rsp+220h+arg_0]
0x18000b94d  add     rsp, 1F0h
0x18000b954  pop     r15
0x18000b956  pop     r14
0x18000b958  pop     r13
0x18000b95a  pop     r12
0x18000b95c  pop     rdi
0x18000b95d  pop     rsi
0x18000b95e  pop     rbp
0x18000b95f  retn
```
