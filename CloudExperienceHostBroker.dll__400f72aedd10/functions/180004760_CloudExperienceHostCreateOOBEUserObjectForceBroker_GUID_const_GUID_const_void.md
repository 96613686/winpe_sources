# CloudExperienceHostCreateOOBEUserObjectForceBroker(_GUID const &,_GUID const &,void * *)

- ea: `0x180004760`
- end: `0x18000487a`
- name: `?CloudExperienceHostCreateOOBEUserObjectForceBroker@@YAJAEBU_GUID@@0PEAPEAX@Z`
- size: `282`
- prototype: `__int64 __fastcall(const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002b024`
- `0x18002cd40`
- `0x18002cf40`
- `0x18002e610`
- `0x180030020`

## callees

- `0x180002a3c`
- `0x180004760`
- `0x180008344`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800047a4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800047a4`

## string_xrefs

- `0x1800047e0`: `onecoreuap\internal\shell\inc\cloudexperiencehostcreatebrokeredobjecthelpers.h`
- `0x180004841`: `onecoreuap\internal\shell\inc\cloudexperiencehostcreatebrokeredobjecthelpers.h`

## pseudocode

```c
__int64 __fastcall CloudExperienceHostCreateOOBEUserObjectForceBroker(
        const struct _GUID *a1,
        const struct _GUID *a2,
        void **a3)
{
  HRESULT v5; // eax
  unsigned int v6; // ebx
  int v7; // eax
  unsigned int v8; // ebx
  LPVOID v9; // rcx
  LPVOID v11; // rcx
  LPVOID v12; // rcx
  int ppv; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  LPVOID v15; // [rsp+60h] [rbp+8h] BYREF

  v15 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  v5 = CoCreateInstance(
         &GUID_e9309678_18b4_414b_ba7a_2c9a7bcf9684,
         0,
         1u,
         &GUID_ef2e1c05_9173_433a_baa2_ada0c25d0b99,
         &v15);
  v6 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\cloudexperiencehostcreatebrokeredobjecthelpers.h",
      (const char *)(unsigned int)v5,
      ppv);
    v12 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
    }
    return v6;
  }
  else
  {
    v7 = (*(__int64 (__fastcall **)(LPVOID, GUID *, const struct _GUID *, void **))(*(_QWORD *)v15 + 40LL))(
           v15,
           &GUID_86c815aa_4888_4063_b0ab_03c49f788be4,
           a2,
           a3);
    v8 = v7;
    if ( v7 >= 0 )
    {
      v11 = v15;
      if ( v15 )
      {
        v15 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v11 + 16LL))(v11);
      }
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3E,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\cloudexperiencehostcreatebrokeredobjecthelpers.h",
        (const char *)(unsigned int)v7,
        ppv);
      v9 = v15;
      if ( v15 )
      {
        v15 = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v9 + 16LL))(v9);
      }
      return v8;
    }
  }
}

```

## disassembly

```asm
0x180004760  mov     [rsp+arg_0], rcx
0x180004765  push    rbx
0x180004766  push    rbp
0x180004767  push    rsi
0x180004768  push    rdi
0x180004769  sub     rsp, 38h
0x18000476d  mov     rdi, r8
0x180004770  mov     rsi, rdx
0x180004773  xor     ebp, ebp
0x180004775  mov     [rsp+58h+arg_0], rbp
0x18000477a  lea     rcx, [rsp+58h+arg_0]
0x18000477f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180004784  lea     rax, [rsp+58h+arg_0]
0x180004789  mov     qword ptr [rsp+58h+ppv], rax; int
0x18000478e  lea     r9, _GUID_ef2e1c05_9173_433a_baa2_ada0c25d0b99; riid
0x180004795  xor     edx, edx; pUnkOuter
0x180004797  mov     r8d, 1; dwClsContext
0x18000479d  lea     rcx, _GUID_e9309678_18b4_414b_ba7a_2c9a7bcf9684; rclsid
0x1800047a4  call    cs:__imp_CoCreateInstance
0x1800047aa  mov     ebx, eax
0x1800047ac  test    eax, eax
0x1800047ae  js      loc_180004839
0x1800047b4  mov     rcx, [rsp+58h+arg_0]
0x1800047b9  mov     rax, [rcx]
0x1800047bc  mov     r9, rdi
0x1800047bf  mov     r8, rsi
0x1800047c2  lea     rdx, _GUID_86c815aa_4888_4063_b0ab_03c49f788be4
0x1800047c9  mov     rax, [rax+28h]
0x1800047cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047d2  mov     ebx, eax
0x1800047d4  test    eax, eax
0x1800047d6  jns     short loc_180004819
0x1800047d8  mov     rcx, [rsp+58h]; this
0x1800047dd  mov     r9d, eax; char *
0x1800047e0  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x1800047e7  mov     edx, 3Eh ; '>'; void *
0x1800047ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800047f1  nop
0x1800047f2  mov     rcx, [rsp+58h+arg_0]
0x1800047f7  test    rcx, rcx
0x1800047fa  jz      short loc_18000480E
0x1800047fc  mov     [rsp+58h+arg_0], rbp
0x180004801  mov     rax, [rcx]
0x180004804  mov     rax, [rax+10h]
0x180004808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000480d  nop
0x18000480e  mov     eax, ebx
0x180004810  add     rsp, 38h
0x180004814  pop     rdi
0x180004815  pop     rsi
0x180004816  pop     rbp
0x180004817  pop     rbx
0x180004818  retn
0x180004819  mov     rcx, [rsp+58h+arg_0]
0x18000481e  test    rcx, rcx
0x180004821  jz      short loc_180004835
0x180004823  mov     [rsp+58h+arg_0], rbp
0x180004828  mov     rax, [rcx]
0x18000482b  mov     rax, [rax+10h]
0x18000482f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004834  nop
0x180004835  xor     eax, eax
0x180004837  jmp     short loc_180004810
0x180004839  mov     rcx, [rsp+58h]; this
0x18000483e  mov     r9d, ebx; char *
0x180004841  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x180004848  mov     edx, 3Dh ; '='; void *
0x18000484d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004852  nop
0x180004853  mov     rcx, [rsp+58h+arg_0]
0x180004858  test    rcx, rcx
0x18000485b  jz      short loc_18000486F
0x18000485d  mov     [rsp+58h+arg_0], rbp
0x180004862  mov     rax, [rcx]
0x180004865  mov     rax, [rax+10h]
0x180004869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000486e  nop
0x18000486f  mov     eax, ebx
0x180004871  add     rsp, 38h
0x180004875  pop     rdi
0x180004876  pop     rsi
0x180004877  pop     rbp
0x180004878  pop     rbx
0x180004879  retn
```
