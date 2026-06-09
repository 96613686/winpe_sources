# Windows::Security::Isolation::FileDialogBrokerCommon::GetCommonFileOpenDialogLegacy(_GUID const &,IFileDialog * *)

- ea: `0x140007bcc`
- end: `0x140007c5b`
- name: `?GetCommonFileOpenDialogLegacy@FileDialogBrokerCommon@Isolation@Security@Windows@@YAJAEBU_GUID@@PEAPEAUIFileDialog@@@Z`
- size: `143`
- prototype: `__int64 __fastcall(IID *rclsid, const struct _GUID *, struct IFileDialog **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000df3c`

## callees

- `0x1400066d0`
- `0x140007bcc`
- `0x140007df4`
- `0x140007e14`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140007c09`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140007c09`

## string_xrefs

- `0x140007c1b`: `onecoreuap\ds\security\isolation\broker\exe\filedialogbrokercommon.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBrokerCommon::GetCommonFileOpenDialogLegacy(
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
        (void *)0x1F,
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
                           (void *)0x24,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\exe\\filedialogbrokercommon.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x140007bcc  mov     [rsp+arg_0], rbx
0x140007bd1  push    rdi
0x140007bd2  sub     rsp, 30h
0x140007bd6  mov     rbx, rdx
0x140007bd9  mov     rdi, rcx
0x140007bdc  mov     [rsp+38h+arg_10], 0
0x140007be5  lea     rcx, [rsp+38h+arg_10]
0x140007bea  call    ?reset@?$com_ptr_t@UIFileDialogEvents@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(void)
0x140007bef  lea     rax, [rsp+38h+arg_10]
0x140007bf4  mov     qword ptr [rsp+38h+ppv], rax; int
0x140007bf9  lea     r9, _GUID_42f85136_db7e_439c_85f1_e4075d135fc8; riid
0x140007c00  xor     edx, edx; pUnkOuter
0x140007c02  lea     r8d, [rdx+1]; dwClsContext
0x140007c06  mov     rcx, rdi; rclsid
0x140007c09  call    cs:__imp_CoCreateInstance
0x140007c0f  mov     rcx, [rsp+38h]; this
0x140007c14  test    eax, eax
0x140007c16  jns     short loc_140007C2C
0x140007c18  mov     r9d, eax; char *
0x140007c1b  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\isolation\\br"...
0x140007c22  mov     edx, 1Fh; void *
0x140007c27  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140007c2c  mov     rax, [rsp+38h+arg_10]
0x140007c31  mov     [rsp+38h+arg_10], 0
0x140007c3a  mov     [rbx], rax
0x140007c3d  lea     rcx, [rsp+38h+arg_10]
0x140007c42  call    ??1?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>(void)
0x140007c47  xor     eax, eax
0x140007c49  jmp     short loc_140007C4F
0x140007c4b  mov     eax, dword ptr [rsp+38h+arg_10]
0x140007c4f  mov     rbx, [rsp+38h+arg_0]
0x140007c54  add     rsp, 30h
0x140007c58  pop     rdi
0x140007c59  retn
```
