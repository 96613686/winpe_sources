# CloudExperienceHostCreateElevatedObject(_GUID const &,_GUID const &,void * *)

- ea: `0x18000b518`
- end: `0x18000b5c9`
- name: `?CloudExperienceHostCreateElevatedObject@@YAJAEBU_GUID@@0PEAPEAX@Z`
- size: `177`
- prototype: `__int64 __fastcall(const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000ae50`

## callees

- `0x1800067b0`
- `0x180007134`
- `0x18000b518`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b55a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b55a`

## string_xrefs

- `0x18000b59a`: `onecoreuap\internal\shell\inc\cloudexperiencehostcreatebrokeredobjecthelpers.h`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostCreateElevatedObject(const struct _GUID *a1, const struct _GUID *a2, void **a3)
{
  HRESULT v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  int ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPVOID v10; // [rsp+48h] [rbp+10h] BYREF

  v10 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v10);
  v4 = CoCreateInstance(
         &GUID_ea297d29_fc9f_41ef_a2e0_666891b01c6e,
         0,
         1u,
         &GUID_10316cc3_d36e_46cd_8344_d85f12419862,
         &v10);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(LPVOID, GUID *, GUID *, void **))(*(_QWORD *)v10 + 24LL))(
           v10,
           &GUID_80a90d72_a834_4f3d_ad3b_c7abbe4a0f66,
           &GUID_d9860fcb_edd8_42df_a696_4e839da5e804,
           a3);
    v5 = v4;
    if ( v4 >= 0 )
    {
      v5 = 0;
      goto LABEL_7;
    }
    v6 = 16;
  }
  else
  {
    v6 = 15;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\cloudexperiencehostcreatebrokeredobjecthelpers.h",
    (const char *)(unsigned int)v4,
    ppv);
LABEL_7:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v10);
  return v5;
}

```

## disassembly

```asm
0x18000b518  mov     rax, rsp
0x18000b51b  mov     [rax+8], rbx
0x18000b51f  mov     [rax+10h], rdx
0x18000b523  push    rdi
0x18000b524  sub     rsp, 30h
0x18000b528  mov     rdi, r8
0x18000b52b  mov     qword ptr [rax+10h], 0
0x18000b533  lea     rcx, [rax+10h]
0x18000b537  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000b53c  lea     rax, [rsp+38h+arg_8]
0x18000b541  mov     qword ptr [rsp+38h+ppv], rax; int
0x18000b546  lea     r9, _GUID_10316cc3_d36e_46cd_8344_d85f12419862; riid
0x18000b54d  xor     edx, edx; pUnkOuter
0x18000b54f  lea     r8d, [rdx+1]; dwClsContext
0x18000b553  lea     rcx, _GUID_ea297d29_fc9f_41ef_a2e0_666891b01c6e; rclsid
0x18000b55a  call    cs:__imp_CoCreateInstance
0x18000b560  mov     ebx, eax
0x18000b562  test    eax, eax
0x18000b564  jns     short loc_18000B56D
0x18000b566  mov     edx, 0Fh
0x18000b56b  jmp     short loc_18000B59A
0x18000b56d  mov     rcx, [rsp+38h+arg_8]
0x18000b572  mov     rax, [rcx]
0x18000b575  mov     r9, rdi
0x18000b578  lea     r8, _GUID_d9860fcb_edd8_42df_a696_4e839da5e804
0x18000b57f  lea     rdx, _GUID_80a90d72_a834_4f3d_ad3b_c7abbe4a0f66
0x18000b586  mov     rax, [rax+18h]
0x18000b58a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b58f  mov     ebx, eax
0x18000b591  test    eax, eax
0x18000b593  jns     short loc_18000B5B0
0x18000b595  mov     edx, 10h; void *
0x18000b59a  lea     r8, aOnecoreuapInte_4; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x18000b5a1  mov     r9d, eax; char *
0x18000b5a4  mov     rcx, [rsp+38h]; this
0x18000b5a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b5ae  jmp     short loc_18000B5B2
0x18000b5b0  xor     ebx, ebx
0x18000b5b2  lea     rcx, [rsp+38h+arg_8]
0x18000b5b7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000b5bc  mov     eax, ebx
0x18000b5be  mov     rbx, [rsp+38h+arg_0]
0x18000b5c3  add     rsp, 30h
0x18000b5c7  pop     rdi
0x18000b5c8  retn
```
