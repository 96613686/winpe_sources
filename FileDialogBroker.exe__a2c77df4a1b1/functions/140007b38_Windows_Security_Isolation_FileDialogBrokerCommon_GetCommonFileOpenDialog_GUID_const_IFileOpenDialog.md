# Windows::Security::Isolation::FileDialogBrokerCommon::GetCommonFileOpenDialog(_GUID const &,IFileOpenDialog * *)

- ea: `0x140007b38`
- end: `0x140007bc3`
- name: `?GetCommonFileOpenDialog@FileDialogBrokerCommon@Isolation@Security@Windows@@YAJAEBU_GUID@@PEAPEAUIFileOpenDialog@@@Z`
- size: `139`
- prototype: `__int64 __fastcall(Windows::Security::Isolation::FileDialogBrokerCommon *__hidden this, const struct _GUID *, struct IFileOpenDialog **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000de1c`

## callees

- `0x1400066d0`
- `0x140007b38`
- `0x140007df4`
- `0x140007e14`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140007b76`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140007b76`

## string_xrefs

- `0x140007b88`: `onecoreuap\ds\security\isolation\broker\exe\filedialogbrokercommon.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Security::Isolation::FileDialogBrokerCommon::GetCommonFileOpenDialog(
        Windows::Security::Isolation::FileDialogBrokerCommon *this,
        const struct _GUID *a2,
        struct IFileOpenDialog **a3)
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
  v4 = CoCreateInstance(&CLSID_FileOpenDialog, 0, 1u, &GUID_d57c7288_d4ad_4768_be02_9d969532d960, &v10);
  try
  {
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB,
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
                           (void *)0x10,
                           (unsigned int)"onecoreuap\\ds\\security\\isolation\\broker\\exe\\filedialogbrokercommon.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x140007b38  mov     [rsp+arg_0], rcx
0x140007b3d  push    rbx
0x140007b3e  sub     rsp, 30h
0x140007b42  mov     rbx, rdx
0x140007b45  mov     [rsp+38h+arg_0], 0
0x140007b4e  lea     rcx, [rsp+38h+arg_0]
0x140007b53  call    ?reset@?$com_ptr_t@UIFileDialogEvents@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFileDialogEvents,wil::err_exception_policy>::reset(void)
0x140007b58  lea     rax, [rsp+38h+arg_0]
0x140007b5d  mov     qword ptr [rsp+38h+ppv], rax; int
0x140007b62  lea     r9, _GUID_d57c7288_d4ad_4768_be02_9d969532d960; riid
0x140007b69  xor     edx, edx; pUnkOuter
0x140007b6b  lea     r8d, [rdx+1]; dwClsContext
0x140007b6f  lea     rcx, CLSID_FileOpenDialog; rclsid
0x140007b76  call    cs:__imp_CoCreateInstance
0x140007b7c  mov     rcx, [rsp+38h]; this
0x140007b81  test    eax, eax
0x140007b83  jns     short loc_140007B99
0x140007b85  mov     r9d, eax; char *
0x140007b88  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\isolation\\br"...
0x140007b8f  mov     edx, 0Bh; void *
0x140007b94  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140007b99  mov     rax, [rsp+38h+arg_0]
0x140007b9e  mov     [rsp+38h+arg_0], 0
0x140007ba7  mov     [rbx], rax
0x140007baa  lea     rcx, [rsp+38h+arg_0]
0x140007baf  call    ??1?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>(void)
0x140007bb4  xor     eax, eax
0x140007bb6  jmp     short loc_140007BBC
0x140007bb8  mov     eax, dword ptr [rsp+38h+arg_0]
0x140007bbc  add     rsp, 30h
0x140007bc0  pop     rbx
0x140007bc1  retn
```
