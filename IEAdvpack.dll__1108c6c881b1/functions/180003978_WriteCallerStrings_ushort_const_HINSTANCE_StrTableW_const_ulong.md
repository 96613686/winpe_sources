# WriteCallerStrings(ushort const *,HINSTANCE__ *,_StrTableW const *,ulong)

- ea: `0x180003978`
- end: `0x180003a56`
- name: `?WriteCallerStrings@@YAJPEBGPEAUHINSTANCE__@@PEBU_StrTableW@@K@Z`
- size: `222`
- prototype: `__int64 __fastcall(const unsigned __int16 *, HINSTANCE hInstance, const struct _StrTableW *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180003be0`

## callees

- `0x180002eb0`
- `0x1800035c8`
- `0x180003978`
- `0x18001b980`

## import_xrefs

- `USER32!LoadStringW` at `0x1800039de`
- `USER32!LoadStringW` at `0x1800039de`

## pseudocode

```c
__int64 __fastcall WriteCallerStrings(
        const unsigned __int16 *a1,
        HINSTANCE hInstance,
        const struct _StrTableW *a3,
        unsigned int a4)
{
  STRENTRYW *pse; // rbx
  unsigned int v9; // edi
  DWORD i; // esi
  WCHAR *pszValue; // r8
  WCHAR Buffer[264]; // [rsp+30h] [rbp-468h] BYREF
  unsigned __int16 v14[264]; // [rsp+240h] [rbp-258h] BYREF

  pse = a3->pse;
  v9 = -2147467259;
  for ( i = 0; i < a3->cEntries; ++i )
  {
    if ( !pse )
      return v9;
    pszValue = pse->pszValue;
    if ( (unsigned __int64)pszValue - 1 <= 0xFFFE )
    {
      if ( !LoadStringW(hInstance, (UINT)pse->pszValue, Buffer, 260) )
        return v9;
      pszValue = Buffer;
    }
    if ( *pszValue != 34 )
    {
      StringCchPrintfW(v14, 0x104u, L"\"%s\"", pszValue);
      pszValue = v14;
    }
    MySmartWrite(a1, pse->pszName, pszValue, a1, a4);
    ++pse;
  }
  return 0;
}

```

## disassembly

```asm
0x180003978  push    rbx
0x18000397a  push    rbp
0x18000397b  push    rsi
0x18000397c  push    rdi
0x18000397d  push    r12
0x18000397f  push    r14
0x180003981  push    r15
0x180003983  sub     rsp, 460h
0x18000398a  mov     rax, cs:__security_cookie
0x180003991  xor     rax, rsp
0x180003994  mov     [rsp+498h+var_48], rax
0x18000399c  mov     rbx, [r8+8]
0x1800039a0  mov     r14d, r9d
0x1800039a3  mov     rbp, r8
0x1800039a6  mov     r12, rdx
0x1800039a9  mov     r15, rcx
0x1800039ac  mov     edi, 80004005h
0x1800039b1  xor     esi, esi
0x1800039b3  cmp     esi, [rbp+0]
0x1800039b6  jnb     short loc_180003A30
0x1800039b8  test    rbx, rbx
0x1800039bb  jz      short loc_180003A32
0x1800039bd  mov     r8, [rbx+8]
0x1800039c1  lea     rax, [r8-1]
0x1800039c5  cmp     rax, 0FFFEh
0x1800039cb  ja      short loc_1800039ED
0x1800039cd  mov     edx, [rbx+8]; uID
0x1800039d0  lea     r8, [rsp+498h+Buffer]; lpBuffer
0x1800039d5  mov     r9d, 104h; cchBufferMax
0x1800039db  mov     rcx, r12; hInstance
0x1800039de  call    cs:__imp_LoadStringW
0x1800039e4  test    eax, eax
0x1800039e6  jz      short loc_180003A32
0x1800039e8  lea     r8, [rsp+498h+Buffer]
0x1800039ed  cmp     word ptr [r8], 22h ; '"'
0x1800039f2  jz      short loc_180003A18
0x1800039f4  mov     r9, r8
0x1800039f7  lea     rcx, [rsp+498h+var_258]; unsigned __int16 *
0x1800039ff  lea     r8, aS; "\"%s\""
0x180003a06  mov     edx, 104h; unsigned __int64
0x180003a0b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180003a10  lea     r8, [rsp+498h+var_258]; unsigned __int16 *
0x180003a18  mov     rdx, [rbx]; unsigned __int16 *
0x180003a1b  mov     r9, r15; unsigned __int16 *
0x180003a1e  mov     [rsp+498h+var_478], r14d; unsigned int
0x180003a23  call    ?MySmartWrite@@YAHPEBG000K@Z; MySmartWrite(ushort const *,ushort const *,ushort const *,ushort const *,ulong)
0x180003a28  inc     esi
0x180003a2a  add     rbx, 10h
0x180003a2e  jmp     short loc_1800039B3
0x180003a30  xor     edi, edi
0x180003a32  mov     eax, edi
0x180003a34  mov     rcx, [rsp+498h+var_48]
0x180003a3c  xor     rcx, rsp; StackCookie
0x180003a3f  call    __security_check_cookie
0x180003a44  add     rsp, 460h
0x180003a4b  pop     r15
0x180003a4d  pop     r14
0x180003a4f  pop     r12
0x180003a51  pop     rdi
0x180003a52  pop     rsi
0x180003a53  pop     rbp
0x180003a54  pop     rbx
0x180003a55  retn
```
