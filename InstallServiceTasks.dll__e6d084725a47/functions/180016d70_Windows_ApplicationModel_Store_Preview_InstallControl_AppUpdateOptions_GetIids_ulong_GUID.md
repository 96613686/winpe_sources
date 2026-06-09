# Windows::ApplicationModel::Store::Preview::InstallControl::AppUpdateOptions::GetIids(ulong *,_GUID * *)

- ea: `0x180016d70`
- end: `0x180016dda`
- name: `?GetIids@AppUpdateOptions@InstallControl@Preview@Store@ApplicationModel@Windows@@UEAAJPEAKPEAPEAU_GUID@@@Z`
- size: `106`
- prototype: `__int64 __fastcall(Windows::ApplicationModel::Store::Preview::InstallControl::AppUpdateOptions *__hidden this, unsigned int *, struct _GUID **)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180016de0`

## callees

- `0x180016ac0`
- `0x180016d70`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016d92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180016d92`

## pseudocode

```c
__int64 __fastcall Windows::ApplicationModel::Store::Preview::InstallControl::AppUpdateOptions::GetIids(
        Windows::ApplicationModel::Store::Preview::InstallControl::AppUpdateOptions *this,
        unsigned int *a2,
        struct _GUID **a3)
{
  GUID *v5; // rax
  __int64 v6; // rcx
  __int64 result; // rax
  struct _GUID *v8; // r8
  int v9; // [rsp+38h] [rbp+10h] BYREF

  *a3 = 0;
  *a2 = 0;
  v5 = (GUID *)CoTaskMemAlloc(0x30u);
  if ( !v5 )
    return 2147942414LL;
  v9 = 1;
  *v5 = GUID_26f0b02f_c2f3_4aea_af8c_6308dd9db85f;
  Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::ApplicationModel::Store::Preview::InstallControl::IAppUpdateOptions2,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::FillArrayWithIid(
    v6,
    &v9,
    v5);
  *a2 = 3;
  result = 0;
  *a3 = v8;
  return result;
}

```

## disassembly

```asm
0x180016d70  mov     [rsp+arg_0], rbx
0x180016d75  push    rdi
0x180016d76  sub     rsp, 20h
0x180016d7a  mov     qword ptr [r8], 0
0x180016d81  mov     ecx, 30h ; '0'; cb
0x180016d86  mov     dword ptr [rdx], 0
0x180016d8c  mov     rbx, r8
0x180016d8f  mov     rdi, rdx
0x180016d92  call    cs:__imp_CoTaskMemAlloc
0x180016d98  mov     r8, rax
0x180016d9b  test    rax, rax
0x180016d9e  jnz     short loc_180016DA7
0x180016da0  mov     eax, 8007000Eh
0x180016da5  jmp     short loc_180016DCF
0x180016da7  movups  xmm0, xmmword ptr cs:_GUID_26f0b02f_c2f3_4aea_af8c_6308dd9db85f.Data1
0x180016dae  lea     rdx, [rsp+28h+arg_8]
0x180016db3  mov     [rsp+28h+arg_8], 1
0x180016dbb  movdqu  xmmword ptr [rax], xmm0
0x180016dbf  call    ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIAppUpdateOptions2@InstallControl@Preview@Store@ApplicationModel@Windows@@U?$CloakedIid@UIAgileObject@@@23@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Windows::ApplicationModel::Store::Preview::InstallControl::IAppUpdateOptions2,Microsoft::WRL::CloakedIid<IAgileObject>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
0x180016dc4  mov     dword ptr [rdi], 3
0x180016dca  xor     eax, eax
0x180016dcc  mov     [rbx], r8
0x180016dcf  mov     rbx, [rsp+28h+arg_0]
0x180016dd4  add     rsp, 20h
0x180016dd8  pop     rdi
0x180016dd9  retn
```
