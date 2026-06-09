# GetCurrentNetworkCost(ulong *)

- ea: `0x180016cac`
- end: `0x180016d64`
- name: `?GetCurrentNetworkCost@@YAJPEAK@Z`
- size: `184`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180015cf0`

## callees

- `0x18000912c`
- `0x18000d544`
- `0x180016cac`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016cf8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016cf8`

## string_xrefs

- `0x180016d2d`: `onecoreuap\enduser\winstore\installservice\lib\scanforupdatesworker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetCurrentNetworkCost(unsigned int *a1)
{
  unsigned int v2; // edi
  __int64 v3; // r9
  __int64 v4; // rdx
  int v5; // eax
  int ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPVOID v9; // [rsp+40h] [rbp+8h] BYREF

  v9 = 0;
  if ( a1 )
  {
    *a1 = 1;
    if ( CoCreateInstance(&CLSID_NetworkListManager, 0, 0x17u, &GUID_dcb00008_570f_4a9b_8d69_199fdba5723b, &v9) >= 0 )
    {
      *a1 = 0;
      v5 = (*(__int64 (__fastcall **)(LPVOID, unsigned int *, _QWORD))(*(_QWORD *)v9 + 24LL))(v9, a1, 0);
      v2 = v5;
      if ( v5 < 0 )
      {
        v3 = (unsigned int)v5;
        v4 = 133;
        goto LABEL_6;
      }
      if ( !*a1 )
        *a1 = 1;
    }
    v2 = 0;
    goto LABEL_10;
  }
  v2 = -2147467261;
  v3 = 2147500035LL;
  v4 = 124;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\scanforupdatesworker.cpp",
    (const char *)v3,
    ppv);
LABEL_10:
  wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>((__int64 *)&v9);
  return v2;
}

```

## disassembly

```asm
0x180016cac  mov     [rsp+arg_8], rbx
0x180016cb1  push    rdi
0x180016cb2  sub     rsp, 30h
0x180016cb6  mov     rbx, rcx
0x180016cb9  mov     [rsp+38h+arg_0], 0
0x180016cc2  test    rcx, rcx
0x180016cc5  jnz     short loc_180016CD4
0x180016cc7  mov     edi, 80004003h
0x180016ccc  mov     r9d, edi
0x180016ccf  lea     edx, [rcx+7Ch]
0x180016cd2  jmp     short loc_180016D2D
0x180016cd4  mov     dword ptr [rcx], 1
0x180016cda  lea     rax, [rsp+38h+arg_0]
0x180016cdf  mov     qword ptr [rsp+38h+ppv], rax; int
0x180016ce4  lea     r9, _GUID_dcb00008_570f_4a9b_8d69_199fdba5723b; riid
0x180016ceb  xor     edx, edx; pUnkOuter
0x180016ced  lea     r8d, [rdx+17h]; dwClsContext
0x180016cf1  lea     rcx, CLSID_NetworkListManager; rclsid
0x180016cf8  call    cs:__imp_CoCreateInstance
0x180016cfe  test    eax, eax
0x180016d00  js      short loc_180016D4B
0x180016d02  mov     dword ptr [rbx], 0
0x180016d08  mov     rcx, [rsp+38h+arg_0]
0x180016d0d  mov     rax, [rcx]
0x180016d10  xor     r8d, r8d
0x180016d13  mov     rdx, rbx
0x180016d16  mov     rax, [rax+18h]
0x180016d1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016d1f  mov     edi, eax
0x180016d21  test    eax, eax
0x180016d23  jns     short loc_180016D40
0x180016d25  mov     r9d, eax; char *
0x180016d28  mov     edx, 85h; void *
0x180016d2d  lea     r8, aOnecoreuapEndu_11; "onecoreuap\\enduser\\winstore\\installs"...
0x180016d34  mov     rcx, [rsp+38h]; this
0x180016d39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016d3e  jmp     short loc_180016D4D
0x180016d40  cmp     dword ptr [rbx], 0
0x180016d43  jnz     short loc_180016D4B
0x180016d45  mov     dword ptr [rbx], 1
0x180016d4b  xor     edi, edi
0x180016d4d  lea     rcx, [rsp+38h+arg_0]
0x180016d52  call    ??1?$com_ptr_t@UITaskSchedulerEx2@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>::~com_ptr_t<ITaskSchedulerEx2,wil::err_exception_policy>(void)
0x180016d57  mov     eax, edi
0x180016d59  mov     rbx, [rsp+38h+arg_8]
0x180016d5e  add     rsp, 30h
0x180016d62  pop     rdi
0x180016d63  retn
```
