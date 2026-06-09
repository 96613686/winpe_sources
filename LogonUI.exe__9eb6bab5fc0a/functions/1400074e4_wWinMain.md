# wWinMain

- ea: `0x1400074e4`
- end: `0x1400076ca`
- name: `wWinMain`
- size: `486`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002760`

## callees

- `0x140001160`
- `0x140006fac`
- `0x1400074e4`
- `0x140008010`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_set_error_mode` at `0x1400075a1`
- `api-ms-win-crt-runtime-l1-1-0!_set_error_mode` at `0x1400075a1`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1400075ac`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x1400075ac`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x140007509`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x140007509`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400074fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1400074fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000763c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000763c`
- `RPCRT4!I_RpcServerDisableExceptionFilter` at `0x140007529`
- `RPCRT4!I_RpcServerDisableExceptionFilter` at `0x140007529`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140007516`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140007516`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140007553`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140007675`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140007553`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140007675`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400076ae`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400076ae`

## string_xrefs

- `0x1400075e5`: `/testclientprocessid:`

## pseudocode

```c
int __stdcall wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)
{
  HANDLE CurrentProcess; // rax
  HRESULT v6; // ebx
  unsigned int v7; // edi
  unsigned int v8; // esi
  unsigned int v9; // r14d
  int v10; // r15d
  __int64 v11; // rdx
  __int64 v12; // rbx
  HLOCAL v13; // rdi
  unsigned int v15; // [rsp+30h] [rbp-38h] BYREF
  unsigned int v16; // [rsp+34h] [rbp-34h] BYREF
  unsigned int v17; // [rsp+38h] [rbp-30h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-28h] BYREF
  LPVOID v19; // [rsp+48h] [rbp-20h] BYREF
  __int64 v20; // [rsp+50h] [rbp-18h] BYREF
  HLOCAL hMem[2]; // [rsp+58h] [rbp-10h] BYREF

  CurrentProcess = GetCurrentProcess();
  SetPriorityClass(CurrentProcess, 0x80u);
  v6 = CoInitializeEx(0, 6u);
  if ( v6 >= 0 )
  {
    I_RpcServerDisableExceptionFilter();
    ppv = 0;
    if ( CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &ppv) >= 0 )
    {
      (*(void (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 1, 2);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    v15 = 0;
    v7 = 0;
    v16 = 0;
    v8 = 0;
    v17 = 0;
    v9 = 0;
    LODWORD(ppv) = 0;
    v10 = 0;
    _set_error_mode(1);
    SetErrorMode(0xC001u);
    if ( *lpCmdLine )
    {
      hMem[0] = 0;
      v20 = 0;
      if ( (int)ParseCommandLineToStringArrayLocalAlloc(lpCmdLine, v11, hMem, &v20) >= 0 )
      {
        v12 = v20;
        v13 = hMem[0];
        GetSwitchValue(hMem[0], v20, L"/testclientprocessid:", &v15);
        GetSwitchValue(v13, v12, L"/flags:", &v16);
        GetSwitchValue(v13, v12, L"/state0:", &v17);
        GetSwitchValue(v13, v12, L"/state1:", &ppv);
        LocalFree(v13);
        v7 = v15;
        v8 = v16;
        v9 = v17;
        v10 = (int)ppv;
      }
    }
    v19 = 0;
    v6 = CoCreateInstance(&CLSID_LogonUIController, 0, 1u, &GUID_e76c5d5b_7ad9_4496_9efd_dfa08ec700bb, &v19);
    if ( v6 >= 0 )
    {
      (*(void (__fastcall **)(LPVOID, _QWORD, _QWORD, _QWORD, int))(*(_QWORD *)v19 + 24LL))(v19, v8, v7, v9, v10);
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v19 + 16LL))(v19);
    }
    CoUninitialize();
  }
  return (unsigned int)v6 >> 31;
}

```

## disassembly

```asm
0x1400074e4  push    rbp
0x1400074e6  push    rbx
0x1400074e7  push    rsi
0x1400074e8  push    rdi
0x1400074e9  push    r12
0x1400074eb  push    r13
0x1400074ed  push    r14
0x1400074ef  push    r15
0x1400074f1  mov     rbp, rsp
0x1400074f4  sub     rsp, 68h
0x1400074f8  mov     r12, r8
0x1400074fb  call    cs:__imp_GetCurrentProcess
0x140007501  mov     rcx, rax; hProcess
0x140007504  mov     edx, 80h; dwPriorityClass
0x140007509  call    cs:__imp_SetPriorityClass
0x14000750f  mov     edx, 6; dwCoInit
0x140007514  xor     ecx, ecx; pvReserved
0x140007516  call    cs:__imp_CoInitializeEx
0x14000751c  xor     r13d, r13d
0x14000751f  mov     ebx, eax
0x140007521  test    eax, eax
0x140007523  js      loc_1400076B4
0x140007529  call    cs:__imp_I_RpcServerDisableExceptionFilter
0x14000752f  lea     rax, [rbp+var_28]
0x140007533  mov     [rbp+var_28], r13
0x140007537  lea     ebx, [r13+1]
0x14000753b  mov     [rsp+68h+ppv], rax; ppv
0x140007540  mov     r8d, ebx; dwClsContext
0x140007543  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x14000754a  xor     edx, edx; pUnkOuter
0x14000754c  lea     rcx, CLSID_GlobalOptions; rclsid
0x140007553  call    cs:__imp_CoCreateInstance
0x140007559  test    eax, eax
0x14000755b  js      short loc_140007583
0x14000755d  mov     rcx, [rbp+var_28]
0x140007561  lea     r8d, [r13+2]
0x140007565  mov     edx, ebx
0x140007567  mov     rax, [rcx]
0x14000756a  mov     rax, [rax+18h]
0x14000756e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007573  mov     rcx, [rbp+var_28]
0x140007577  mov     rax, [rcx]
0x14000757a  mov     rax, [rax+10h]
0x14000757e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007583  mov     ecx, ebx; Mode
0x140007585  mov     [rbp+var_38], r13d
0x140007589  mov     edi, r13d
0x14000758c  mov     [rbp+var_34], r13d
0x140007590  mov     esi, r13d
0x140007593  mov     [rbp+var_30], r13d
0x140007597  mov     r14d, r13d
0x14000759a  mov     dword ptr [rbp+var_28], r13d
0x14000759e  mov     r15d, r13d
0x1400075a1  call    cs:__imp__set_error_mode
0x1400075a7  mov     ecx, 0C001h; uMode
0x1400075ac  call    cs:__imp_SetErrorMode
0x1400075b2  cmp     [r12], r13w
0x1400075b7  jz      loc_140007655
0x1400075bd  lea     r9, [rbp+var_18]
0x1400075c1  mov     [rbp+hMem], r13
0x1400075c5  lea     r8, [rbp+hMem]
0x1400075c9  mov     [rbp+var_18], r13
0x1400075cd  mov     rcx, r12
0x1400075d0  call    ParseCommandLineToStringArrayLocalAlloc
0x1400075d5  test    eax, eax
0x1400075d7  js      short loc_140007655
0x1400075d9  mov     rbx, [rbp+var_18]
0x1400075dd  lea     r9, [rbp+var_38]
0x1400075e1  mov     rdi, [rbp+hMem]
0x1400075e5  lea     r8, aTestclientproc; "/testclientprocessid:"
0x1400075ec  mov     rdx, rbx
0x1400075ef  mov     rcx, rdi
0x1400075f2  call    _GetSwitchValue
0x1400075f7  lea     r9, [rbp+var_34]
0x1400075fb  mov     rdx, rbx
0x1400075fe  lea     r8, aFlags; "/flags:"
0x140007605  mov     rcx, rdi
0x140007608  call    _GetSwitchValue
0x14000760d  lea     r9, [rbp+var_30]
0x140007611  mov     rdx, rbx
0x140007614  lea     r8, aState0; "/state0:"
0x14000761b  mov     rcx, rdi
0x14000761e  call    _GetSwitchValue
0x140007623  lea     r9, [rbp+var_28]
0x140007627  mov     rdx, rbx
0x14000762a  lea     r8, aState1; "/state1:"
0x140007631  mov     rcx, rdi
0x140007634  call    _GetSwitchValue
0x140007639  mov     rcx, rdi; hMem
0x14000763c  call    cs:__imp_LocalFree
0x140007642  mov     edi, [rbp+var_38]
0x140007645  mov     ebx, 1
0x14000764a  mov     esi, [rbp+var_34]
0x14000764d  mov     r14d, [rbp+var_30]
0x140007651  mov     r15d, dword ptr [rbp+var_28]
0x140007655  lea     rax, [rbp+var_20]
0x140007659  mov     [rbp+var_20], r13
0x14000765d  lea     r9, _GUID_e76c5d5b_7ad9_4496_9efd_dfa08ec700bb; riid
0x140007664  mov     [rsp+68h+ppv], rax; ppv
0x140007669  mov     r8d, ebx; dwClsContext
0x14000766c  lea     rcx, CLSID_LogonUIController; rclsid
0x140007673  xor     edx, edx; pUnkOuter
0x140007675  call    cs:__imp_CoCreateInstance
0x14000767b  mov     ebx, eax
0x14000767d  test    eax, eax
0x14000767f  js      short loc_1400076AE
0x140007681  mov     rcx, [rbp+var_20]
0x140007685  mov     r9d, r14d
0x140007688  mov     r8d, edi
0x14000768b  mov     dword ptr [rsp+68h+ppv], r15d
0x140007690  mov     edx, esi
0x140007692  mov     rax, [rcx]
0x140007695  mov     rax, [rax+18h]
0x140007699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000769e  mov     rcx, [rbp+var_20]
0x1400076a2  mov     rax, [rcx]
0x1400076a5  mov     rax, [rax+10h]
0x1400076a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400076ae  call    cs:__imp_CoUninitialize
0x1400076b4  shr     ebx, 1Fh
0x1400076b7  mov     eax, ebx
0x1400076b9  add     rsp, 68h
0x1400076bd  pop     r15
0x1400076bf  pop     r14
0x1400076c1  pop     r13
0x1400076c3  pop     r12
0x1400076c5  pop     rdi
0x1400076c6  pop     rsi
0x1400076c7  pop     rbx
0x1400076c8  pop     rbp
0x1400076c9  retn
```
