# CloudExperienceHostCreateElevatedObject(_GUID const &,_GUID const &,void * *)

- ea: `0x18007d690`
- end: `0x18007d738`
- name: `?CloudExperienceHostCreateElevatedObject@@YAJAEBU_GUID@@0PEAPEAX@Z`
- size: `168`
- prototype: `__int64 __fastcall(const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `11`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18007cd5c`
- `0x18007ce38`
- `0x18007e4e0`
- `0x18007e5c0`
- `0x18009f380`
- `0x18009f9d0`
- `0x18009fa54`
- `0x1800a0fb0`
- `0x1800a1030`
- `0x1800acee0`
- `0x1800c4570`

## callees

- `0x18000fa5c`
- `0x1800153f8`
- `0x18007d690`
- `0x1800dc010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007d6d3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007d6d3`

## string_xrefs

- `0x18007d70b`: `onecoreuap\internal\shell\inc\cloudexperiencehostcreatebrokeredobjecthelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CloudExperienceHostCreateElevatedObject(const struct _GUID *a1, const struct _GUID *a2, void **a3)
{
  HRESULT v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  int ppv; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  LPVOID v12; // [rsp+78h] [rbp+20h] BYREF

  v12 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v12);
  v6 = CoCreateInstance(
         &GUID_ea297d29_fc9f_41ef_a2e0_666891b01c6e,
         0,
         1u,
         &GUID_10316cc3_d36e_46cd_8344_d85f12419862,
         &v12);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(LPVOID, const struct _GUID *, const struct _GUID *, void **))(*(_QWORD *)v12 + 24LL))(
           v12,
           a1,
           a2,
           a3);
    v7 = v6;
    if ( v6 >= 0 )
    {
      v7 = 0;
      goto LABEL_7;
    }
    v8 = 16;
  }
  else
  {
    v8 = 15;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\cloudexperiencehostcreatebrokeredobjecthelpers.h",
    (const char *)(unsigned int)v6,
    ppv);
LABEL_7:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v12);
  return v7;
}

```

## disassembly

```asm
0x18007d690  push    rbx
0x18007d692  push    rbp
0x18007d693  push    rsi
0x18007d694  push    rdi
0x18007d695  sub     rsp, 38h
0x18007d699  mov     rdi, r8
0x18007d69c  mov     rsi, rdx
0x18007d69f  mov     rbp, rcx
0x18007d6a2  mov     [rsp+58h+arg_18], 0
0x18007d6ab  lea     rcx, [rsp+58h+arg_18]
0x18007d6b0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007d6b5  lea     rax, [rsp+58h+arg_18]
0x18007d6ba  mov     qword ptr [rsp+58h+ppv], rax; int
0x18007d6bf  lea     r9, _GUID_10316cc3_d36e_46cd_8344_d85f12419862; riid
0x18007d6c6  xor     edx, edx; pUnkOuter
0x18007d6c8  lea     r8d, [rdx+1]; dwClsContext
0x18007d6cc  lea     rcx, _GUID_ea297d29_fc9f_41ef_a2e0_666891b01c6e; rclsid
0x18007d6d3  call    cs:__imp_CoCreateInstance
0x18007d6d9  mov     ebx, eax
0x18007d6db  test    eax, eax
0x18007d6dd  jns     short loc_18007D6E6
0x18007d6df  mov     edx, 0Fh
0x18007d6e4  jmp     short loc_18007D70B
0x18007d6e6  mov     rcx, [rsp+58h+arg_18]
0x18007d6eb  mov     rax, [rcx]
0x18007d6ee  mov     r9, rdi
0x18007d6f1  mov     r8, rsi
0x18007d6f4  mov     rdx, rbp
0x18007d6f7  mov     rax, [rax+18h]
0x18007d6fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d700  mov     ebx, eax
0x18007d702  test    eax, eax
0x18007d704  jns     short loc_18007D721
0x18007d706  mov     edx, 10h; void *
0x18007d70b  lea     r8, aOnecoreuapInte_9; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x18007d712  mov     r9d, eax; char *
0x18007d715  mov     rcx, [rsp+58h]; this
0x18007d71a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007d71f  jmp     short loc_18007D723
0x18007d721  xor     ebx, ebx
0x18007d723  lea     rcx, [rsp+58h+arg_18]
0x18007d728  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007d72d  mov     eax, ebx
0x18007d72f  add     rsp, 38h
0x18007d733  pop     rdi
0x18007d734  pop     rsi
0x18007d735  pop     rbp
0x18007d736  pop     rbx
0x18007d737  retn
```
