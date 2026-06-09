# Windows::Security::Isolation::FileDialogBrokerCommon::GetCommonFileSaveDialog(_GUID const &,IFileSaveDialog * *)

- ea: `0x140007c64`
- end: `0x140007cef`
- name: `?GetCommonFileSaveDialog@FileDialogBrokerCommon@Isolation@Security@Windows@@YAJAEBU_GUID@@PEAPEAUIFileSaveDialog@@@Z`
- size: `139`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBrokerCommon *__hidden this, const struct _GUID *, struct IFileSaveDialog **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000e044`

## callees

- `0x1400066d0`
- `0x140007c64`
- `0x140007df4`
- `0x140007e14`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140007ca2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140007ca2`

## string_xrefs

- `0x140007cb4`: `onecoreuap\ds\security\isolation\broker\exe\filedialogbrokercommon.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBrokerCommon::GetCommonFileSaveDialog(
        Windows::Security::Isolation::FileDialogBrokerCommon *this,
        const struct _GUID *a2,
        struct IFileSaveDialog **a3)
{
  HRESULT v4; // eax
  LPVOID v5; // rax
  const char *v6; // r9
  __int64 result; // rax
  int ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPVOID v10; // [rsp+40h] [rbp+8h] BYREF

  v10 = 0;
  wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(&v10);
  v4 = CoCreateInstance(&CLSID_FileSaveDialog, 0, 1u, &GUID_84bccd23_5fde_4cdb_aea4_af64b83d78ab, &v10);
  try
  {
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x15,
        (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\exe\\filedialogbrokercommon.cpp",
        (const char *)(unsigned int)v4,
        ppv);
    v5 = v10;
    v10 = 0;
    *(_QWORD *)&a2->Data1 = v5;
    wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>((__int64 *)&v10);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1A,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\exe\\filedialogbrokercommon.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x140007c64  mov     [rsp+arg_0], rcx
0x140007c69  push    rbx
0x140007c6a  sub     rsp, 30h
0x140007c6e  mov     rbx, rdx
0x140007c71  mov     [rsp+38h+arg_0], 0
0x140007c7a  lea     rcx, [rsp+38h+arg_0]
0x140007c7f  call    ?reset@?$com_ptr_t@UIFileDialogEvents@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(void)
0x140007c84  lea     rax, [rsp+38h+arg_0]
0x140007c89  mov     qword ptr [rsp+38h+ppv], rax; int
0x140007c8e  lea     r9, _GUID_84bccd23_5fde_4cdb_aea4_af64b83d78ab; riid
0x140007c95  xor     edx, edx; pUnkOuter
0x140007c97  lea     r8d, [rdx+1]; dwClsContext
0x140007c9b  lea     rcx, CLSID_FileSaveDialog; rclsid
0x140007ca2  call    cs:__imp_CoCreateInstance
0x140007ca8  mov     rcx, [rsp+38h]; this
0x140007cad  test    eax, eax
0x140007caf  jns     short loc_140007CC5
0x140007cb1  mov     r9d, eax; char *
0x140007cb4  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\isolation\\br"...
0x140007cbb  mov     edx, 15h; void *
0x140007cc0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140007cc5  mov     rax, [rsp+38h+arg_0]
0x140007cca  mov     [rsp+38h+arg_0], 0
0x140007cd3  mov     [rbx], rax
0x140007cd6  lea     rcx, [rsp+38h+arg_0]
0x140007cdb  call    ??1?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>(void)
0x140007ce0  xor     eax, eax
0x140007ce2  jmp     short loc_140007CE8
0x140007ce4  mov     eax, dword ptr [rsp+38h+arg_0]
0x140007ce8  add     rsp, 30h
0x140007cec  pop     rbx
0x140007ced  retn
```
