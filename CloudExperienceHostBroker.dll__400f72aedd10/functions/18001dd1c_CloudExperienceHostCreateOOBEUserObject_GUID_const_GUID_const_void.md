# CloudExperienceHostCreateOOBEUserObject(_GUID const &,_GUID const &,void * *)

- ea: `0x18001dd1c`
- end: `0x18001ddc4`
- name: `?CloudExperienceHostCreateOOBEUserObject@@YAJAEBU_GUID@@0PEAPEAX@Z`
- size: `168`
- prototype: `__int64 __fastcall(const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `12`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001d318`
- `0x18002a9b8`
- `0x18002ab90`
- `0x18002ac48`
- `0x18002ace4`
- `0x18002ae3c`
- `0x18002b300`
- `0x18002d430`
- `0x18002f320`
- `0x18002f900`
- `0x180031238`
- `0x1800312d4`

## callees

- `0x180002a3c`
- `0x180008344`
- `0x18001dd1c`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001dd5f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001dd5f`

## string_xrefs

- `0x18001dd97`: `onecoreuap\internal\shell\inc\cloudexperiencehostcreatebrokeredobjecthelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CloudExperienceHostCreateOOBEUserObject(const struct _GUID *a1, const struct _GUID *a2, void **a3)
{
  HRESULT v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  int ppv; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  LPVOID v12; // [rsp+78h] [rbp+20h] BYREF

  v12 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
  v6 = CoCreateInstance(
         &GUID_e9309678_18b4_414b_ba7a_2c9a7bcf9684,
         0,
         1u,
         &GUID_ef2e1c05_9173_433a_baa2_ada0c25d0b99,
         &v12);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(LPVOID, const struct _GUID *, const struct _GUID *, void **))(*(_QWORD *)v12 + 32LL))(
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
    v8 = 32;
  }
  else
  {
    v8 = 31;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\cloudexperiencehostcreatebrokeredobjecthelpers.h",
    (const char *)(unsigned int)v6,
    ppv);
LABEL_7:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
  return v7;
}

```

## disassembly

```asm
0x18001dd1c  push    rbx
0x18001dd1e  push    rbp
0x18001dd1f  push    rsi
0x18001dd20  push    rdi
0x18001dd21  sub     rsp, 38h
0x18001dd25  mov     rdi, r8
0x18001dd28  mov     rsi, rdx
0x18001dd2b  mov     rbp, rcx
0x18001dd2e  mov     [rsp+58h+arg_18], 0
0x18001dd37  lea     rcx, [rsp+58h+arg_18]
0x18001dd3c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001dd41  lea     rax, [rsp+58h+arg_18]
0x18001dd46  mov     qword ptr [rsp+58h+ppv], rax; int
0x18001dd4b  lea     r9, _GUID_ef2e1c05_9173_433a_baa2_ada0c25d0b99; riid
0x18001dd52  xor     edx, edx; pUnkOuter
0x18001dd54  lea     r8d, [rdx+1]; dwClsContext
0x18001dd58  lea     rcx, _GUID_e9309678_18b4_414b_ba7a_2c9a7bcf9684; rclsid
0x18001dd5f  call    cs:__imp_CoCreateInstance
0x18001dd65  mov     ebx, eax
0x18001dd67  test    eax, eax
0x18001dd69  jns     short loc_18001DD72
0x18001dd6b  mov     edx, 1Fh
0x18001dd70  jmp     short loc_18001DD97
0x18001dd72  mov     rcx, [rsp+58h+arg_18]
0x18001dd77  mov     rax, [rcx]
0x18001dd7a  mov     r9, rdi
0x18001dd7d  mov     r8, rsi
0x18001dd80  mov     rdx, rbp
0x18001dd83  mov     rax, [rax+20h]
0x18001dd87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd8c  mov     ebx, eax
0x18001dd8e  test    eax, eax
0x18001dd90  jns     short loc_18001DDAD
0x18001dd92  mov     edx, 20h ; ' '; void *
0x18001dd97  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x18001dd9e  mov     r9d, eax; char *
0x18001dda1  mov     rcx, [rsp+58h]; this
0x18001dda6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ddab  jmp     short loc_18001DDAF
0x18001ddad  xor     ebx, ebx
0x18001ddaf  lea     rcx, [rsp+58h+arg_18]
0x18001ddb4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001ddb9  mov     eax, ebx
0x18001ddbb  add     rsp, 38h
0x18001ddbf  pop     rdi
0x18001ddc0  pop     rsi
0x18001ddc1  pop     rbp
0x18001ddc2  pop     rbx
0x18001ddc3  retn
```
