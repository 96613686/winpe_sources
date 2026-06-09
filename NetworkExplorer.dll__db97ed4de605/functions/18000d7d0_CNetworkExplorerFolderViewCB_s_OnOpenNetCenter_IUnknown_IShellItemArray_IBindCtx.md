# CNetworkExplorerFolderViewCB::s_OnOpenNetCenter(IUnknown *,IShellItemArray *,IBindCtx *)

- ea: `0x18000d7d0`
- end: `0x18000d871`
- name: `?s_OnOpenNetCenter@CNetworkExplorerFolderViewCB@@SAJPEAUIUnknown@@PEAUIShellItemArray@@PEAUIBindCtx@@@Z`
- size: `161`
- prototype: `__int64 __fastcall(struct IUnknown *, struct IShellItemArray *, struct IBindCtx *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a120`

## callees

- `0x18000a1ec`
- `0x18000b364`
- `0x18000d7d0`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000d807`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000d807`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CNetworkExplorerFolderViewCB::s_OnOpenNetCenter(
        struct IUnknown *a1,
        struct IShellItemArray *a2,
        struct IBindCtx *a3)
{
  HRESULT v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rdx
  __int64 v7; // r8
  int ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPVOID v11; // [rsp+58h] [rbp+20h] BYREF

  v11 = 0;
  Microsoft::WRL::ComPtr<IOpenControlPanel>::InternalRelease(&v11, a2, a3);
  v3 = CoCreateInstance(&CLSID_OpenControlPanel, 0, 1u, &GUID_d11ad862_66de_4df4_bf6c_1f5621996af1, &v11);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v3 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *, const wchar_t *, _QWORD))(*(_QWORD *)v11 + 24LL))(
           v11,
           L"Microsoft.NetworkAndSharingCenter",
           L"Advanced",
           0);
    v4 = v3;
    if ( v3 >= 0 )
    {
      v4 = 0;
      goto LABEL_7;
    }
    v5 = 2777;
  }
  else
  {
    v5 = 2775;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"net\\homenet\\explorer\\folders\\profilefolder.cpp",
    (const char *)(unsigned int)v3,
    ppv);
LABEL_7:
  Microsoft::WRL::ComPtr<IOpenControlPanel>::InternalRelease(&v11, v6, v7);
  return v4;
}

```

## disassembly

```asm
0x18000d7d0  push    rbx
0x18000d7d2  sub     rsp, 30h
0x18000d7d6  mov     [rsp+38h+arg_18], 0
0x18000d7df  lea     rcx, [rsp+38h+arg_18]
0x18000d7e4  call    ?InternalRelease@?$ComPtr@UIOpenControlPanel@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IOpenControlPanel>::InternalRelease(void)
0x18000d7e9  lea     rax, [rsp+38h+arg_18]
0x18000d7ee  mov     qword ptr [rsp+38h+ppv], rax; int
0x18000d7f3  lea     r9, _GUID_d11ad862_66de_4df4_bf6c_1f5621996af1; riid
0x18000d7fa  xor     edx, edx; pUnkOuter
0x18000d7fc  lea     r8d, [rdx+1]; dwClsContext
0x18000d800  lea     rcx, CLSID_OpenControlPanel; rclsid
0x18000d807  call    cs:__imp_CoCreateInstance
0x18000d80d  mov     ebx, eax
0x18000d80f  test    eax, eax
0x18000d811  jns     short loc_18000D81A
0x18000d813  mov     edx, 0AD7h
0x18000d818  jmp     short loc_18000D847
0x18000d81a  mov     rcx, [rsp+38h+arg_18]
0x18000d81f  mov     rax, [rcx]
0x18000d822  xor     r9d, r9d
0x18000d825  lea     r8, aAdvanced; "Advanced"
0x18000d82c  lea     rdx, aMicrosoftNetwo; "Microsoft.NetworkAndSharingCenter"
0x18000d833  mov     rax, [rax+18h]
0x18000d837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d83c  mov     ebx, eax
0x18000d83e  test    eax, eax
0x18000d840  jns     short loc_18000D85D
0x18000d842  mov     edx, 0AD9h; void *
0x18000d847  lea     r8, aNetHomenetExpl; "net\\homenet\\explorer\\folders\\profil"...
0x18000d84e  mov     r9d, eax; char *
0x18000d851  mov     rcx, [rsp+38h]; this
0x18000d856  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d85b  jmp     short loc_18000D85F
0x18000d85d  xor     ebx, ebx
0x18000d85f  lea     rcx, [rsp+38h+arg_18]
0x18000d864  call    ?InternalRelease@?$ComPtr@UIOpenControlPanel@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IOpenControlPanel>::InternalRelease(void)
0x18000d869  mov     eax, ebx
0x18000d86b  add     rsp, 30h
0x18000d86f  pop     rbx
0x18000d870  retn
```
