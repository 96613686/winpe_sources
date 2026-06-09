# Wallet::Utils::SetItemImageProperty(IWalletItem *,__MIDL___MIDL_itf_wallettypes_0000_0000_0010,ushort const *)

- ea: `0x18003a010`
- end: `0x18003a1a9`
- name: `?SetItemImageProperty@Utils@Wallet@@YAJPEAUIWalletItem@@W4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@PEBG@Z`
- size: `409`
- prototype: `__int64 __fastcall(__int64, unsigned int, const char *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18002e5b0`

## callees

- `0x180008cc0`
- `0x18001aa00`
- `0x18001aa30`
- `0x18003a010`
- `0x180043052`
- `0x180043090`
- `0x180045010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18003a131`
- `OLEAUT32!__imp_SysAllocString` at `0x18003a131`
- `dsclient!DSCreateSharedFileToken` at `0x18003a11a`
- `dsclient!DSCreateSharedFileToken` at `0x18003a11a`
- `dsclient!DSRemoveSharingToken` at `0x18003a164`
- `dsclient!DSRemoveSharingToken` at `0x18003a164`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003a170`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003a170`

## string_xrefs

- `0x18003a09d`: `[Wallet Utils] SetItemImageProperty, Path: %S`

## pseudocode

```c
__int64 __fastcall Wallet::Utils::SetItemImageProperty(__int64 a1, unsigned int a2, const char *a3)
{
  int v6; // ebx
  __int64 v7; // rax
  int v8; // eax
  OLECHAR *psz; // [rsp+30h] [rbp-D0h] BYREF
  PROPVARIANT pvar[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v12; // [rsp+48h] [rbp-B8h]
  _DWORD v13[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v14; // [rsp+58h] [rbp-A8h]
  __int64 v15; // [rsp+60h] [rbp-A0h]
  const wchar_t *v16; // [rsp+68h] [rbp-98h]
  __int64 v17; // [rsp+70h] [rbp-90h]
  const wchar_t *v18; // [rsp+78h] [rbp-88h]
  _BYTE v19[288]; // [rsp+80h] [rbp-80h] BYREF

  psz = 0;
  *(_OWORD *)pvar = 0;
  v12 = 0;
  if ( !a1 )
  {
    v6 = -2147467261;
    goto LABEL_13;
  }
  if ( a2 - 200 > 8 )
  {
    v6 = -2147024809;
    goto LABEL_13;
  }
  if ( !a3 || !*(_WORD *)a3 )
    goto LABEL_9;
  wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy(
    5,
    "Wallet::Utils::SetItemImageProperty",
    798,
    "[Wallet Utils] SetItemImageProperty, Path: %S",
    a3);
  v13[0] = 0;
  v13[1] = 1;
  v14 = 2;
  v15 = 0;
  v16 = L"S-1-5-18";
  v17 = 0;
  v18 = L"S-1-5-18";
  memset_0(v19, 0, sizeof(v19));
  v7 = tlx::replace<tlx::handle_traits<unsigned short *,void (*)(unsigned short *),&void DSFreeString(unsigned short *),0>>(&psz);
  v6 = DSCreateSharedFileToken(a3, v13, 0, 0, v7);
  if ( v6 >= 0 )
  {
    LOWORD(pvar[0]) = 8;
    pvar[1] = SysAllocString(psz);
LABEL_9:
    v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, PROPVARIANT *))(*(_QWORD *)a1 + 56LL))(a1, a2, pvar);
    v6 = 0;
    if ( v8 < 0 )
      v6 = v8;
  }
  if ( psz )
    DSRemoveSharingToken();
LABEL_13:
  PropVariantClear(pvar);
  tlx::unique_any<tlx::handle_traits<unsigned short *,void (*)(unsigned short *),&void DSFreeString(unsigned short *),0>>::~unique_any<tlx::handle_traits<unsigned short *,void (*)(unsigned short *),&void DSFreeString(unsigned short *),0>>(&psz);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003a010  mov     [rsp-8+arg_18], rbx
0x18003a015  push    rbp
0x18003a016  push    rsi
0x18003a017  push    rdi
0x18003a018  push    r14
0x18003a01a  push    r15
0x18003a01c  lea     rbp, [rsp-0B0h]
0x18003a024  sub     rsp, 1B0h
0x18003a02b  mov     rax, cs:__security_cookie
0x18003a032  xor     rax, rsp
0x18003a035  mov     [rbp+0D0h+var_30], rax
0x18003a03c  mov     rbx, r8
0x18003a03f  mov     esi, edx
0x18003a041  mov     rdi, rcx
0x18003a044  xor     r14d, r14d
0x18003a047  mov     [rsp+1D0h+psz], r14
0x18003a04c  xorps   xmm0, xmm0
0x18003a04f  xor     eax, eax
0x18003a051  movups  xmmword ptr [rsp+1D0h+pvar], xmm0
0x18003a056  mov     [rsp+1D0h+var_188], rax
0x18003a05b  test    rcx, rcx
0x18003a05e  jnz     short loc_18003A06A
0x18003a060  mov     ebx, 80004003h
0x18003a065  jmp     loc_18003A16B
0x18003a06a  lea     eax, [rdx-0C8h]
0x18003a070  mov     r15d, 8
0x18003a076  cmp     eax, r15d
0x18003a079  jbe     short loc_18003A085
0x18003a07b  mov     ebx, 80070057h
0x18003a080  jmp     loc_18003A16B
0x18003a085  test    rbx, rbx
0x18003a088  jz      loc_18003A13C
0x18003a08e  cmp     [r8], r14w
0x18003a092  jz      loc_18003A13C
0x18003a098  mov     [rsp+1D0h+var_1B0], rbx
0x18003a09d  lea     r9, aWalletUtilsSet_0; "[Wallet Utils] SetItemImageProperty, Pa"...
0x18003a0a4  mov     r8d, 31Eh
0x18003a0aa  lea     rdx, aWalletUtilsSet; "Wallet::Utils::SetItemImageProperty"
0x18003a0b1  mov     ecx, 5
0x18003a0b6  call    ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x18003a0bb  mov     [rsp+1D0h+var_180], r14d
0x18003a0c0  mov     [rsp+1D0h+var_17C], 1
0x18003a0c8  mov     [rsp+1D0h+var_178], 2
0x18003a0d1  mov     [rsp+1D0h+var_170], r14
0x18003a0d6  lea     rcx, aS1518; "S-1-5-18"
0x18003a0dd  mov     [rsp+1D0h+var_168], rcx
0x18003a0e2  mov     [rsp+1D0h+var_160], r14
0x18003a0e7  mov     [rsp+1D0h+var_158], rcx
0x18003a0ec  xor     edx, edx; Val
0x18003a0ee  mov     r8d, 120h; Size
0x18003a0f4  lea     rcx, [rbp+0D0h+var_150]; void *
0x18003a0f8  call    memset_0
0x18003a0fd  lea     rcx, [rsp+1D0h+psz]
0x18003a102  call    ??$replace@U?$handle_traits@PEAGP6AXPEAG@Z$1?DSFreeString@@YAX0@Z$0A@@tlx@@@tlx@@YAPEAPEAGAEAV?$unique_any@U?$handle_traits@PEAGP6AXPEAG@Z$1?DSFreeString@@YAX0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<ushort *,void (*)(ushort *),&DSFreeString(ushort *),0>>(tlx::unique_any<tlx::handle_traits<ushort *,void (*)(ushort *),&DSFreeString(ushort *),0>> &)
0x18003a107  mov     [rsp+1D0h+var_1B0], rax
0x18003a10c  xor     r9d, r9d
0x18003a10f  xor     r8d, r8d
0x18003a112  lea     rdx, [rsp+1D0h+var_180]
0x18003a117  mov     rcx, rbx
0x18003a11a  call    cs:__imp_DSCreateSharedFileToken
0x18003a120  mov     ebx, eax
0x18003a122  test    eax, eax
0x18003a124  js      short loc_18003A15A
0x18003a126  mov     word ptr [rsp+1D0h+pvar], r15w
0x18003a12c  mov     rcx, [rsp+1D0h+psz]; psz
0x18003a131  call    cs:__imp_SysAllocString
0x18003a137  mov     [rsp+1D0h+pvar+8], rax
0x18003a13c  mov     rax, [rdi]
0x18003a13f  lea     r8, [rsp+1D0h+pvar]
0x18003a144  mov     edx, esi
0x18003a146  mov     rcx, rdi
0x18003a149  mov     rax, [rax+38h]
0x18003a14d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a152  mov     ebx, r14d
0x18003a155  test    eax, eax
0x18003a157  cmovs   ebx, eax
0x18003a15a  mov     rcx, [rsp+1D0h+psz]
0x18003a15f  test    rcx, rcx
0x18003a162  jz      short loc_18003A16B
0x18003a164  call    cs:__imp_DSRemoveSharingToken
0x18003a16a  nop
0x18003a16b  lea     rcx, [rsp+1D0h+pvar]; pvar
0x18003a170  call    cs:__imp_PropVariantClear
0x18003a176  nop
0x18003a177  lea     rcx, [rsp+1D0h+psz]
0x18003a17c  call    ??1?$unique_any@U?$handle_traits@PEAGP6AXPEAG@Z$1?DSFreeString@@YAX0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<ushort *,void (*)(ushort *),&DSFreeString(ushort *),0>>::~unique_any<tlx::handle_traits<ushort *,void (*)(ushort *),&DSFreeString(ushort *),0>>(void)
0x18003a181  mov     eax, ebx
0x18003a183  mov     rcx, [rbp+0D0h+var_30]
0x18003a18a  xor     rcx, rsp; StackCookie
0x18003a18d  call    __security_check_cookie
0x18003a192  mov     rbx, [rsp+1D0h+arg_18]
0x18003a19a  add     rsp, 1B0h
0x18003a1a1  pop     r15
0x18003a1a3  pop     r14
0x18003a1a5  pop     rdi
0x18003a1a6  pop     rsi
0x18003a1a7  pop     rbp
0x18003a1a8  retn
```
