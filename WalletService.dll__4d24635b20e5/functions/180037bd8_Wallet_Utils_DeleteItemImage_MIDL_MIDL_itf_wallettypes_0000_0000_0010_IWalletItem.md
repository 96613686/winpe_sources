# Wallet::Utils::DeleteItemImage(__MIDL___MIDL_itf_wallettypes_0000_0000_0010,IWalletItem *)

- ea: `0x180037bd8`
- end: `0x180037cd8`
- name: `?DeleteItemImage@Utils@Wallet@@YAJW4__MIDL___MIDL_itf_wallettypes_0000_0000_0010@@PEAUIWalletItem@@@Z`
- size: `256`
- prototype: `__int64 __fastcall(unsigned int, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180022000`

## callees

- `0x18000d8d8`
- `0x180013f78`
- `0x180037bd8`
- `0x180037e58`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037c72`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037c72`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180037c68`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180037c68`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180037caf`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180037cc0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180037caf`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180037cc0`

## pseudocode

```c
__int64 __fastcall Wallet::Utils::DeleteItemImage(unsigned int a1, __int64 a2)
{
  unsigned int v4; // edi
  wchar_t *v5; // r8
  int v6; // eax
  int v7; // ebx
  PROPVARIANT pvar[2]; // [rsp+20h] [rbp-40h] BYREF
  __int64 v10; // [rsp+30h] [rbp-30h]
  LPCWSTR lpFileName[2]; // [rsp+38h] [rbp-28h] BYREF
  __int64 v12; // [rsp+48h] [rbp-18h]

  *(_OWORD *)pvar = 0;
  v10 = 0;
  if ( a2 )
  {
    if ( a1 - 200 <= 8 )
    {
      if ( (*(int (__fastcall **)(__int64, _QWORD, PROPVARIANT *))(*(_QWORD *)a2 + 48LL))(a2, a1, pvar) >= 0
        && pvar[1]
        && *(_WORD *)pvar[1] )
      {
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(lpFileName);
        if ( (int)Wallet::Utils::GetAbsoluteFilePathFromDssTokenOrDssUri(v5) >= 0 && !DeleteFileW(lpFileName[0]) )
          GetLastError();
        utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(lpFileName);
      }
      *(_OWORD *)lpFileName = 0;
      v12 = 0;
      v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, LPCWSTR *))(*(_QWORD *)a2 + 56LL))(a2, a1, lpFileName);
      v7 = 0;
      if ( v6 < 0 )
        v7 = v6;
      PropVariantClear((PROPVARIANT *)lpFileName);
      v4 = 0;
      if ( v7 < 0 )
        v4 = v7;
    }
    else
    {
      v4 = -2147024809;
    }
  }
  else
  {
    v4 = -2147467261;
  }
  PropVariantClear(pvar);
  return v4;
}

```

## disassembly

```asm
0x180037bd8  mov     [rsp-8+arg_0], rbx
0x180037bdd  mov     [rsp-8+arg_8], rdi
0x180037be2  push    rbp
0x180037be3  mov     rbp, rsp
0x180037be6  sub     rsp, 60h
0x180037bea  mov     rbx, rdx
0x180037bed  mov     edi, ecx
0x180037bef  xorps   xmm0, xmm0
0x180037bf2  xor     eax, eax
0x180037bf4  movups  xmmword ptr [rbp+pvar], xmm0
0x180037bf8  mov     [rbp+var_30], rax
0x180037bfc  test    rdx, rdx
0x180037bff  jnz     short loc_180037C0B
0x180037c01  mov     edi, 80004003h
0x180037c06  jmp     loc_180037CBC
0x180037c0b  lea     eax, [rcx-0C8h]
0x180037c11  cmp     eax, 8
0x180037c14  jbe     short loc_180037C20
0x180037c16  mov     edi, 80070057h
0x180037c1b  jmp     loc_180037CBC
0x180037c20  mov     rax, [rdx]
0x180037c23  lea     r8, [rbp+pvar]
0x180037c27  mov     edx, edi
0x180037c29  mov     rcx, rbx
0x180037c2c  mov     rax, [rax+30h]
0x180037c30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037c35  test    eax, eax
0x180037c37  js      short loc_180037C82
0x180037c39  mov     r8, [rbp+pvar+8]
0x180037c3d  test    r8, r8
0x180037c40  jz      short loc_180037C82
0x180037c42  xor     eax, eax
0x180037c44  cmp     ax, [r8]
0x180037c48  jz      short loc_180037C82
0x180037c4a  lea     rcx, [rbp+lpFileName]
0x180037c4e  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@XZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(void)
0x180037c53  nop
0x180037c54  lea     rdx, [rbp+lpFileName]
0x180037c58  mov     rcx, r8; String2
0x180037c5b  call    ?GetAbsoluteFilePathFromDssTokenOrDssUri@Utils@Wallet@@YAJPEBGAEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; Wallet::Utils::GetAbsoluteFilePathFromDssTokenOrDssUri(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &)
0x180037c60  test    eax, eax
0x180037c62  js      short loc_180037C79
0x180037c64  mov     rcx, [rbp+lpFileName]; lpFileName
0x180037c68  call    cs:__imp_DeleteFileW
0x180037c6e  test    eax, eax
0x180037c70  jnz     short loc_180037C79
0x180037c72  call    cs:__imp_GetLastError
0x180037c78  nop
0x180037c79  lea     rcx, [rbp+lpFileName]
0x180037c7d  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180037c82  xorps   xmm0, xmm0
0x180037c85  xor     eax, eax
0x180037c87  movups  xmmword ptr [rbp+lpFileName], xmm0
0x180037c8b  mov     [rbp+var_18], rax
0x180037c8f  mov     rax, [rbx]
0x180037c92  lea     r8, [rbp+lpFileName]
0x180037c96  mov     edx, edi
0x180037c98  mov     rcx, rbx
0x180037c9b  mov     rax, [rax+38h]
0x180037c9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037ca4  xor     ebx, ebx
0x180037ca6  test    eax, eax
0x180037ca8  cmovs   ebx, eax
0x180037cab  lea     rcx, [rbp+lpFileName]; pvar
0x180037caf  call    cs:__imp_PropVariantClear
0x180037cb5  xor     edi, edi
0x180037cb7  test    ebx, ebx
0x180037cb9  cmovs   edi, ebx
0x180037cbc  lea     rcx, [rbp+pvar]; pvar
0x180037cc0  call    cs:__imp_PropVariantClear
0x180037cc6  mov     eax, edi
0x180037cc8  mov     rbx, [rsp+60h+arg_0]
0x180037ccd  mov     rdi, [rsp+60h+arg_8]
0x180037cd2  add     rsp, 60h
0x180037cd6  pop     rbp
0x180037cd7  retn
```
