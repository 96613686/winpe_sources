# Windows::Security::Isolation::FileDialogBrokerCommon::GetCommonFileSaveDialogLegacy(_GUID const &,IFileDialog * *)

- ea: `0x140007cf8`
- end: `0x140007d87`
- name: `?GetCommonFileSaveDialogLegacy@FileDialogBrokerCommon@Isolation@Security@Windows@@YAJAEBU_GUID@@PEAPEAUIFileDialog@@@Z`
- size: `143`
- prototype: `__int64 __fastcall(IID *rclsid, const struct _GUID *, struct IFileDialog **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000e164`

## callees

- `0x1400066d0`
- `0x140007cf8`
- `0x140007df4`
- `0x140007e14`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140007d35`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140007d35`

## string_xrefs

- `0x140007d47`: `onecoreuap\ds\security\isolation\broker\exe\filedialogbrokercommon.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBrokerCommon::GetCommonFileSaveDialogLegacy(
        IID *rclsid,
        const struct _GUID *a2,
        struct IFileDialog **a3)
{
  HRESULT v5; // eax
  LPVOID v6; // rax
  const char *v7; // r9
  __int64 result; // rax
  int ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPVOID v11; // [rsp+50h] [rbp+18h] BYREF

  v11 = 0;
  wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(&v11);
  v5 = CoCreateInstance(rclsid, 0, 1u, &GUID_42f85136_db7e_439c_85f1_e4075d135fc8, &v11);
  try
  {
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x29,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\exe\\filedialogbrokercommon.cpp",
        (const char *)(unsigned int)v5,
        ppv);
    v6 = v11;
    v11 = 0;
    *(_QWORD *)&a2->Data1 = v6;
    wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>((__int64 *)&v11);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2E,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\exe\\filedialogbrokercommon.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x140007cf8  mov     [rsp+arg_0], rbx
0x140007cfd  push    rdi
0x140007cfe  sub     rsp, 30h
0x140007d02  mov     rbx, rdx
0x140007d05  mov     rdi, rcx
0x140007d08  mov     [rsp+38h+arg_10], 0
0x140007d11  lea     rcx, [rsp+38h+arg_10]
0x140007d16  call    ?reset@?$com_ptr_t@UIFileDialogEvents@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(void)
0x140007d1b  lea     rax, [rsp+38h+arg_10]
0x140007d20  mov     qword ptr [rsp+38h+ppv], rax; int
0x140007d25  lea     r9, _GUID_42f85136_db7e_439c_85f1_e4075d135fc8; riid
0x140007d2c  xor     edx, edx; pUnkOuter
0x140007d2e  lea     r8d, [rdx+1]; dwClsContext
0x140007d32  mov     rcx, rdi; rclsid
0x140007d35  call    cs:__imp_CoCreateInstance
0x140007d3b  mov     rcx, [rsp+38h]; this
0x140007d40  test    eax, eax
0x140007d42  jns     short loc_140007D58
0x140007d44  mov     r9d, eax; char *
0x140007d47  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\isolation\\br"...
0x140007d4e  mov     edx, 29h ; ')'; void *
0x140007d53  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140007d58  mov     rax, [rsp+38h+arg_10]
0x140007d5d  mov     [rsp+38h+arg_10], 0
0x140007d66  mov     [rbx], rax
0x140007d69  lea     rcx, [rsp+38h+arg_10]
0x140007d6e  call    ??1?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>(void)
0x140007d73  xor     eax, eax
0x140007d75  jmp     short loc_140007D7B
0x140007d77  mov     eax, dword ptr [rsp+38h+arg_10]
0x140007d7b  mov     rbx, [rsp+38h+arg_0]
0x140007d80  add     rsp, 30h
0x140007d84  pop     rdi
0x140007d85  retn
```
