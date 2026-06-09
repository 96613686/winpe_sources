# SetProxyBlanketImpersonationLevelAndDynamicCloaking(IUnknown *)

- ea: `0x180065c04`
- end: `0x180065e91`
- name: `?SetProxyBlanketImpersonationLevelAndDynamicCloaking@@YAJPEAUIUnknown@@@Z`
- size: `653`
- prototype: `__int64 __fastcall(struct IUnknown *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180065ea0`

## callees

- `0x18000b064`
- `0x1800189b8`
- `0x180065c04`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065d53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065e07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065e42`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065d53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065e07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180065e42`

## string_xrefs

- `0x180065e7f`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180065c6d`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\sessionmanagerbrokerimpl.cpp`
- `0x180065d38`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\sessionmanagerbrokerimpl.cpp`
- `0x180065dec`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\sessionmanagerbrokerimpl.cpp`

## pseudocode

```c
__int64 __fastcall SetProxyBlanketImpersonationLevelAndDynamicCloaking(struct IUnknown *a1)
{
  int v2; // eax
  unsigned int v3; // edi
  __int64 v5; // rax
  int v6; // eax
  int v7; // eax
  int v8; // [rsp+20h] [rbp-60h]
  int v9; // [rsp+20h] [rbp-60h]
  unsigned int v10; // [rsp+50h] [rbp-30h] BYREF
  __int64 *v11; // [rsp+58h] [rbp-28h] BYREF
  LPVOID pv[4]; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  unsigned int v14; // [rsp+B8h] [rbp+38h] BYREF

  pv[2] = a1;
  if ( a1 )
    ((void (__fastcall *)(struct IUnknown *))a1->lpVtbl->AddRef)(a1);
  v11 = 0;
  v2 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 **))a1->lpVtbl->QueryInterface)(
         a1,
         &GUID_0000013d_0000_0000_c000_000000000046,
         &v11);
  if ( v2 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v2,
      v8);
  if ( !v11 )
  {
    v3 = -2147467262;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x36,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\sessionmanagerbrokerimpl.cpp",
      (const char *)0x80004002LL,
      v8);
    if ( v11 )
      (*(void (__fastcall **)(__int64 *))(*v11 + 16))(v11);
    ((void (__fastcall *)(struct IUnknown *))a1->lpVtbl->Release)(a1);
    return v3;
  }
  v10 = 0;
  v14 = 0;
  pv[1] = 0;
  pv[0] = 0;
  v5 = *v11;
  pv[0] = 0;
  v6 = (*(__int64 (__fastcall **)(__int64 *, struct IUnknown *, unsigned int *, unsigned int *))(v5 + 24))(
         v11,
         a1,
         &v10,
         &v14);
  v3 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\sessionmanagerbrokerimpl.cpp",
      (const char *)(unsigned int)v6,
      (int)pv);
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
    if ( v11 )
      (*(void (__fastcall **)(__int64 *))(*v11 + 16))(v11);
LABEL_14:
    ((void (__fastcall *)(struct IUnknown *))a1->lpVtbl->Release)(a1);
    return v3;
  }
  v9 = (int)pv[0];
  v7 = (*(__int64 (__fastcall **)(__int64 *, struct IUnknown *, _QWORD, _QWORD))(*v11 + 32))(v11, a1, v10, v14);
  v3 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x51,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\sessionmanagerbrokerimpl.cpp",
      (const char *)(unsigned int)v7,
      v9);
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
    if ( v11 )
      (*(void (__fastcall **)(__int64 *))(*v11 + 16))(v11);
    goto LABEL_14;
  }
  if ( pv[0] )
    CoTaskMemFree(pv[0]);
  if ( v11 )
    (*(void (__fastcall **)(__int64 *))(*v11 + 16))(v11);
  ((void (__fastcall *)(struct IUnknown *))a1->lpVtbl->Release)(a1);
  return 0;
}

```

## disassembly

```asm
0x180065c04  push    rbp
0x180065c06  push    rbx
0x180065c07  push    rdi
0x180065c08  mov     rbp, rsp
0x180065c0b  sub     rsp, 80h
0x180065c12  mov     rbx, rcx
0x180065c15  mov     [rbp+var_10], rcx
0x180065c19  test    rcx, rcx
0x180065c1c  jz      short loc_180065C2B
0x180065c1e  mov     rax, [rcx]
0x180065c21  mov     rax, [rax+8]
0x180065c25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065c2a  nop
0x180065c2b  mov     [rbp+var_28], 0
0x180065c33  mov     rax, [rbx]
0x180065c36  lea     r8, [rbp+var_28]
0x180065c3a  lea     rdx, _GUID_0000013d_0000_0000_c000_000000000046
0x180065c41  mov     rcx, rbx
0x180065c44  mov     rax, [rax]
0x180065c47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065c4c  mov     rcx, [rbp+18h]; this
0x180065c50  test    eax, eax
0x180065c52  js      loc_180065E7C
0x180065c58  mov     rcx, [rbp+var_28]
0x180065c5c  test    rcx, rcx
0x180065c5f  jnz     short loc_180065CAC
0x180065c61  mov     rcx, [rbp+18h]; this
0x180065c65  mov     edi, 80004002h
0x180065c6a  mov     r9d, edi; char *
0x180065c6d  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\search\\com"...
0x180065c74  mov     edx, 36h ; '6'; void *
0x180065c79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065c7e  nop
0x180065c7f  mov     rcx, [rbp+var_28]
0x180065c83  test    rcx, rcx
0x180065c86  jz      short loc_180065C95
0x180065c88  mov     rax, [rcx]
0x180065c8b  mov     rax, [rax+10h]
0x180065c8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065c94  nop
0x180065c95  mov     rcx, [rbx]
0x180065c98  mov     rax, [rcx+10h]
0x180065c9c  mov     rcx, rbx
0x180065c9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065ca4  nop
0x180065ca5  mov     eax, edi
0x180065ca7  jmp     loc_180065E71
0x180065cac  mov     [rbp+var_30], 0
0x180065cb3  mov     [rbp+arg_18], 0
0x180065cba  mov     [rbp+arg_10], 0
0x180065cc1  mov     [rbp+arg_8], 0
0x180065cc8  mov     [rbp+arg_0], 0
0x180065ccf  mov     [rbp+var_18], 0
0x180065cd7  mov     [rbp+pv], 0
0x180065cdf  mov     rax, [rcx]
0x180065ce2  mov     [rbp+pv], 0
0x180065cea  lea     rdx, [rbp+arg_0]
0x180065cee  mov     [rsp+80h+var_40], rdx
0x180065cf3  lea     rdx, [rbp+var_18]
0x180065cf7  mov     [rsp+80h+var_48], rdx
0x180065cfc  lea     rdx, [rbp+arg_8]
0x180065d00  mov     [rsp+80h+var_50], rdx
0x180065d05  lea     rdx, [rbp+arg_10]
0x180065d09  mov     [rsp+80h+var_58], rdx
0x180065d0e  lea     rdx, [rbp+pv]
0x180065d12  mov     qword ptr [rsp+80h+var_60], rdx; int
0x180065d17  lea     r9, [rbp+arg_18]
0x180065d1b  lea     r8, [rbp+var_30]
0x180065d1f  mov     rdx, rbx
0x180065d22  mov     rax, [rax+18h]
0x180065d26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065d2b  mov     edi, eax
0x180065d2d  test    eax, eax
0x180065d2f  jns     short loc_180065D85
0x180065d31  mov     rcx, [rbp+18h]; this
0x180065d35  mov     r9d, eax; char *
0x180065d38  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\search\\com"...
0x180065d3f  mov     edx, 46h ; 'F'; void *
0x180065d44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065d49  nop
0x180065d4a  mov     rcx, [rbp+pv]; pv
0x180065d4e  test    rcx, rcx
0x180065d51  jz      short loc_180065D5A
0x180065d53  call    cs:__imp_CoTaskMemFree
0x180065d59  nop
0x180065d5a  mov     rcx, [rbp+var_28]
0x180065d5e  test    rcx, rcx
0x180065d61  jz      short loc_180065D70
0x180065d63  mov     rax, [rcx]
0x180065d66  mov     rax, [rax+10h]
0x180065d6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065d6f  nop
0x180065d70  mov     rax, [rbx]
0x180065d73  mov     rcx, rbx
0x180065d76  mov     rax, [rax+10h]
0x180065d7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065d7f  nop
0x180065d80  jmp     loc_180065CA5
0x180065d85  mov     r9d, 3
0x180065d8b  mov     [rbp+arg_8], r9d
0x180065d8f  mov     r8d, [rbp+arg_0]
0x180065d93  and     r8d, 0FFFFFFDFh
0x180065d97  or      r8d, 40h
0x180065d9b  mov     [rbp+arg_0], r8d
0x180065d9f  mov     rcx, [rbp+var_28]
0x180065da3  mov     rdx, [rbp+var_18]
0x180065da7  mov     r10d, [rbp+arg_10]
0x180065dab  mov     r11, [rbp+pv]
0x180065daf  mov     rax, [rcx]
0x180065db2  mov     dword ptr [rsp+80h+var_40], r8d
0x180065db7  mov     [rsp+80h+var_48], rdx
0x180065dbc  mov     dword ptr [rsp+80h+var_50], r9d
0x180065dc1  mov     dword ptr [rsp+80h+var_58], r10d
0x180065dc6  mov     qword ptr [rsp+80h+var_60], r11; int
0x180065dcb  mov     r9d, [rbp+arg_18]
0x180065dcf  mov     r8d, [rbp+var_30]
0x180065dd3  mov     rdx, rbx
0x180065dd6  mov     rax, [rax+20h]
0x180065dda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065ddf  mov     edi, eax
0x180065de1  test    eax, eax
0x180065de3  jns     short loc_180065E39
0x180065de5  mov     rcx, [rbp+18h]; this
0x180065de9  mov     r9d, eax; char *
0x180065dec  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\search\\com"...
0x180065df3  mov     edx, 51h ; 'Q'; void *
0x180065df8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180065dfd  nop
0x180065dfe  mov     rcx, [rbp+pv]; pv
0x180065e02  test    rcx, rcx
0x180065e05  jz      short loc_180065E0E
0x180065e07  call    cs:__imp_CoTaskMemFree
0x180065e0d  nop
0x180065e0e  mov     rcx, [rbp+var_28]
0x180065e12  test    rcx, rcx
0x180065e15  jz      short loc_180065E24
0x180065e17  mov     rax, [rcx]
0x180065e1a  mov     rax, [rax+10h]
0x180065e1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065e23  nop
0x180065e24  mov     rax, [rbx]
0x180065e27  mov     rcx, rbx
0x180065e2a  mov     rax, [rax+10h]
0x180065e2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065e33  nop
0x180065e34  jmp     loc_180065CA5
0x180065e39  mov     rcx, [rbp+pv]; pv
0x180065e3d  test    rcx, rcx
0x180065e40  jz      short loc_180065E49
0x180065e42  call    cs:__imp_CoTaskMemFree
0x180065e48  nop
0x180065e49  mov     rcx, [rbp+var_28]
0x180065e4d  test    rcx, rcx
0x180065e50  jz      short loc_180065E5F
0x180065e52  mov     rax, [rcx]
0x180065e55  mov     rax, [rax+10h]
0x180065e59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065e5e  nop
0x180065e5f  mov     rax, [rbx]
0x180065e62  mov     rcx, rbx
0x180065e65  mov     rax, [rax+10h]
0x180065e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065e6e  nop
0x180065e6f  xor     eax, eax
0x180065e71  add     rsp, 80h
0x180065e78  pop     rdi
0x180065e79  pop     rbx
0x180065e7a  pop     rbp
0x180065e7b  retn
0x180065e7c  mov     r9d, eax; char *
0x180065e7f  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180065e86  mov     edx, 1CBEh; void *
0x180065e8b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
