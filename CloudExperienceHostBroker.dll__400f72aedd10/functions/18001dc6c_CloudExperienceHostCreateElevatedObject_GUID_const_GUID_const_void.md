# CloudExperienceHostCreateElevatedObject(_GUID const &,_GUID const &,void * *)

- ea: `0x18001dc6c`
- end: `0x18001dd14`
- name: `?CloudExperienceHostCreateElevatedObject@@YAJAEBU_GUID@@0PEAPEAX@Z`
- size: `168`
- prototype: `__int64 __fastcall(const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001d318`
- `0x180022660`
- `0x180022924`
- `0x18002ad84`
- `0x180034a50`
- `0x180034b30`

## callees

- `0x180002a3c`
- `0x180008344`
- `0x18001dc6c`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001dcaf`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001dcaf`

## string_xrefs

- `0x18001dce7`: `onecoreuap\internal\shell\inc\cloudexperiencehostcreatebrokeredobjecthelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CloudExperienceHostCreateElevatedObject(const struct _GUID *a1, const struct _GUID *a2, void **a3)
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
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12);
  return v7;
}

```

## disassembly

```asm
0x18001dc6c  push    rbx
0x18001dc6e  push    rbp
0x18001dc6f  push    rsi
0x18001dc70  push    rdi
0x18001dc71  sub     rsp, 38h
0x18001dc75  mov     rdi, r8
0x18001dc78  mov     rsi, rdx
0x18001dc7b  mov     rbp, rcx
0x18001dc7e  mov     [rsp+58h+arg_18], 0
0x18001dc87  lea     rcx, [rsp+58h+arg_18]
0x18001dc8c  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001dc91  lea     rax, [rsp+58h+arg_18]
0x18001dc96  mov     qword ptr [rsp+58h+ppv], rax; int
0x18001dc9b  lea     r9, _GUID_10316cc3_d36e_46cd_8344_d85f12419862; riid
0x18001dca2  xor     edx, edx; pUnkOuter
0x18001dca4  lea     r8d, [rdx+1]; dwClsContext
0x18001dca8  lea     rcx, _GUID_ea297d29_fc9f_41ef_a2e0_666891b01c6e; rclsid
0x18001dcaf  call    cs:__imp_CoCreateInstance
0x18001dcb5  mov     ebx, eax
0x18001dcb7  test    eax, eax
0x18001dcb9  jns     short loc_18001DCC2
0x18001dcbb  mov     edx, 0Fh
0x18001dcc0  jmp     short loc_18001DCE7
0x18001dcc2  mov     rcx, [rsp+58h+arg_18]
0x18001dcc7  mov     rax, [rcx]
0x18001dcca  mov     r9, rdi
0x18001dccd  mov     r8, rsi
0x18001dcd0  mov     rdx, rbp
0x18001dcd3  mov     rax, [rax+18h]
0x18001dcd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dcdc  mov     ebx, eax
0x18001dcde  test    eax, eax
0x18001dce0  jns     short loc_18001DCFD
0x18001dce2  mov     edx, 10h; void *
0x18001dce7  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x18001dcee  mov     r9d, eax; char *
0x18001dcf1  mov     rcx, [rsp+58h]; this
0x18001dcf6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dcfb  jmp     short loc_18001DCFF
0x18001dcfd  xor     ebx, ebx
0x18001dcff  lea     rcx, [rsp+58h+arg_18]
0x18001dd04  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001dd09  mov     eax, ebx
0x18001dd0b  add     rsp, 38h
0x18001dd0f  pop     rdi
0x18001dd10  pop     rsi
0x18001dd11  pop     rbp
0x18001dd12  pop     rbx
0x18001dd13  retn
```
