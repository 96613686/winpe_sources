# COpenSearchRowset::_ParseChannelElement(IXmlReader *,ulong,ushort const *,ushort const *)

- ea: `0x1800456a0`
- end: `0x18004576c`
- name: `?_ParseChannelElement@COpenSearchRowset@@AEAAJPEAUIXmlReader@@KPEBG1@Z`
- size: `204`
- prototype: `__int64 __fastcall(COpenSearchRowset *__hidden this, struct IXmlReader *, unsigned int, LPCWSTR pszStr1, PCWSTR psz1)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800453f0`

## callees

- `0x18004419c`
- `0x1800456a0`
- `0x180045774`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180045707`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180045707`
- `SHLWAPI!UrlCompareW` at `0x1800456cc`
- `SHLWAPI!UrlCompareW` at `0x1800456cc`
- `SHLWAPI!__imp_StrCmpICW` at `0x1800456e0`
- `SHLWAPI!__imp_StrCmpICW` at `0x180045745`
- `SHLWAPI!__imp_StrCmpICW` at `0x1800456e0`
- `SHLWAPI!__imp_StrCmpICW` at `0x180045745`

## string_xrefs

- `0x1800456b4`: `http://a9.com/-/spec/opensearch/1.1/`

## pseudocode

```c
__int64 __fastcall COpenSearchRowset::_ParseChannelElement(
        COpenSearchRowset *this,
        struct IXmlReader *a2,
        unsigned int a3,
        LPCWSTR pszStr1,
        PCWSTR psz1)
{
  __int64 v5; // rbp
  unsigned int v8; // ebx
  COpenSearchRowset *v10; // rcx
  int ElementText; // eax
  int v12; // eax
  __int64 v13; // rdx
  unsigned __int16 *v15; // [rsp+20h] [rbp-38h] BYREF

  v5 = a3;
  v8 = 0;
  if ( UrlCompareW(psz1, L"http://a9.com/-/spec/opensearch/1.1/", 1) )
  {
    if ( !StrCmpICW(pszStr1, L"item") )
      return (unsigned int)COpenSearchRowset::_ParseItem(this, a2, v5);
  }
  else if ( !StrCmpICW(pszStr1, L"itemsPerPage") )
  {
    v15 = 0;
    ElementText = COpenSearchRowset::_GetElementText(v10, a2, (const unsigned __int16 **)&v15);
    v8 = ElementText;
    if ( ElementText < 0 )
    {
      if ( ElementText == -2147023728 )
        return 0;
    }
    else
    {
      v12 = _o__wtoi(v15);
      if ( v12 > 0 )
      {
        *((_DWORD *)this + 13) = v12;
        v13 = 3 * v5;
        *((_DWORD *)this + 2 * v13 + 160) = v12;
        *((_DWORD *)this + 2 * v13 + 161) = 1;
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x1800456a0  push    rbx
0x1800456a2  push    rbp
0x1800456a3  push    rsi
0x1800456a4  push    rdi
0x1800456a5  push    r14
0x1800456a7  sub     rsp, 30h
0x1800456ab  mov     ebp, r8d
0x1800456ae  mov     rsi, rdx
0x1800456b1  mov     rdi, rcx
0x1800456b4  lea     rdx, aHttpA9ComSpecO; "http://a9.com/-/spec/opensearch/1.1/"
0x1800456bb  mov     rcx, [rsp+58h+psz1]; psz1
0x1800456c3  xor     ebx, ebx
0x1800456c5  mov     r14, r9
0x1800456c8  lea     r8d, [rbx+1]; fIgnoreSlash
0x1800456cc  call    cs:__imp_UrlCompareW
0x1800456d2  mov     rcx, r14; pszStr1
0x1800456d5  test    eax, eax
0x1800456d7  jnz     short loc_18004573E
0x1800456d9  lea     rdx, aItemsperpage; "itemsPerPage"
0x1800456e0  call    cs:__imp_StrCmpICW
0x1800456e6  test    eax, eax
0x1800456e8  jnz     short loc_18004575F
0x1800456ea  lea     r8, [rsp+58h+var_38]; unsigned __int16 **
0x1800456ef  mov     [rsp+58h+var_38], rbx
0x1800456f4  mov     rdx, rsi; struct IXmlReader *
0x1800456f7  call    ?_GetElementText@COpenSearchRowset@@AEAAJPEAUIXmlReader@@PEAPEBG@Z; COpenSearchRowset::_GetElementText(IXmlReader *,ushort const * *)
0x1800456fc  mov     ebx, eax
0x1800456fe  test    eax, eax
0x180045700  js      short loc_180045733
0x180045702  mov     rcx, [rsp+58h+var_38]
0x180045707  call    cs:__imp__o__wtoi
0x18004570d  test    eax, eax
0x18004570f  jle     short loc_18004575F
0x180045711  mov     [rdi+34h], eax
0x180045714  lea     rdx, ds:0[rbp*2]
0x18004571c  add     rdx, rbp
0x18004571f  mov     [rdi+rdx*8+280h], eax
0x180045726  mov     dword ptr [rdi+rdx*8+284h], 1
0x180045731  jmp     short loc_18004575F
0x180045733  cmp     eax, 80070490h
0x180045738  jnz     short loc_18004575F
0x18004573a  xor     ebx, ebx
0x18004573c  jmp     short loc_18004575F
0x18004573e  lea     rdx, aItem; "item"
0x180045745  call    cs:__imp_StrCmpICW
0x18004574b  test    eax, eax
0x18004574d  jnz     short loc_18004575F
0x18004574f  mov     r8d, ebp; unsigned int
0x180045752  mov     rdx, rsi; struct IXmlReader *
0x180045755  mov     rcx, rdi; this
0x180045758  call    ?_ParseItem@COpenSearchRowset@@AEAAJPEAUIXmlReader@@K@Z; COpenSearchRowset::_ParseItem(IXmlReader *,ulong)
0x18004575d  mov     ebx, eax
0x18004575f  mov     eax, ebx
0x180045761  add     rsp, 30h
0x180045765  pop     r14
0x180045767  pop     rdi
0x180045768  pop     rsi
0x180045769  pop     rbp
0x18004576a  pop     rbx
0x18004576b  retn
```
