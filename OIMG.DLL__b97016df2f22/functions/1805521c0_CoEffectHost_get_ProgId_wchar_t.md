# CoEffectHost::get_ProgId(wchar_t * *)

- ea: `0x1805521c0`
- end: `0x18055232b`
- name: `?get_ProgId@CoEffectHost@@UEAAJPEAPEA_W@Z`
- size: `363`
- prototype: `__int64 __fastcall(CoEffectHost *__hidden this, wchar_t **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1804c6944`
- `0x1805521c0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18055225e`
- `OLEAUT32!__imp_SysAllocString` at `0x18055225e`
- `OLEAUT32!__imp_SysFreeString` at `0x180552255`
- `OLEAUT32!__imp_SysFreeString` at `0x1805522e0`
- `OLEAUT32!__imp_SysFreeString` at `0x180552255`
- `OLEAUT32!__imp_SysFreeString` at `0x1805522e0`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1805522c6`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1805522c6`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1805522d1`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x1805522d1`
- `api-ms-win-crt-string-l1-1-0!iswdigit` at `0x180552226`
- `api-ms-win-crt-string-l1-1-0!iswdigit` at `0x180552226`
- `ole32!StringFromCLSID` at `0x18055227f`
- `ole32!StringFromCLSID` at `0x18055227f`
- `ole32!ProgIDFromCLSID` at `0x1805521fe`
- `ole32!ProgIDFromCLSID` at `0x1805521fe`
- `ole32!CoTaskMemFree` at `0x1805522b8`
- `ole32!CoTaskMemFree` at `0x1805522b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CoEffectHost::get_ProgId(CoEffectHost *this, wchar_t **a2)
{
  wchar_t *v3; // rdi
  OLECHAR *v4; // rbx
  const IID *v5; // rsi
  unsigned __int64 v6; // r14
  OLECHAR *v7; // rsi
  wint_t v8; // ax
  HRESULT v9; // eax
  UINT v10; // eax
  OLECHAR *psz; // [rsp+50h] [rbp+8h] BYREF
  OLECHAR *v13; // [rsp+60h] [rbp+18h]

  v3 = 0;
  v4 = 0;
  v13 = 0;
  if ( !*((_QWORD *)this + 40) )
    goto LABEL_24;
  psz = 0;
  v5 = (const IID *)((char *)this + 336);
  if ( ProgIDFromCLSID((const IID *const)this + 21, &psz) < 0 )
  {
    v9 = StringFromCLSID(v5, &psz);
    if ( v9 == -2147024882 || v9 == -2045378032 || v9 == -2045312765 || v9 == -2045247216 )
      ATL::BaseAtlThrow(v9);
    if ( v9 < 0 )
      ATL::BaseAtlThrow(v9);
    goto LABEL_10;
  }
  v6 = 0;
  v7 = psz;
  v8 = *psz;
  if ( *psz )
  {
    do
    {
      if ( v8 == 46 )
        v6 = (unsigned __int64)v7;
      else
        v6 &= -(__int64)(iswdigit(v8) != 0);
      v8 = *++v7;
    }
    while ( *v7 );
    if ( v6 )
      *(_WORD *)v6 = 0;
LABEL_10:
    v7 = psz;
  }
  if ( v7 )
  {
    SysFreeString(0);
    v4 = SysAllocString(v7);
    v13 = v4;
    if ( !v4 )
      ATL::BaseAtlThrow(-2147024882);
    v7 = psz;
  }
  if ( v7 )
    CoTaskMemFree(v7);
  if ( v4 )
  {
    v10 = SysStringByteLen(v4);
    v3 = SysAllocStringByteLen((LPCSTR)v4, v10);
  }
LABEL_24:
  *a2 = v3;
  SysFreeString(v4);
  return 0;
}

```

## disassembly

```asm
0x1805521c0  mov     rax, rsp
0x1805521c3  mov     [rax+10h], rbx
0x1805521c7  mov     [rax+20h], rsi
0x1805521cb  push    rdi
0x1805521cc  push    r14
0x1805521ce  push    r15
0x1805521d0  sub     rsp, 30h
0x1805521d4  mov     r15, rdx
0x1805521d7  xor     edi, edi
0x1805521d9  mov     ebx, edi
0x1805521db  mov     [rax+18h], rbx
0x1805521df  cmp     [rcx+140h], rdi
0x1805521e6  jz      loc_1805522DA
0x1805521ec  mov     [rax+8], rdi
0x1805521f0  lea     rsi, [rcx+150h]
0x1805521f7  lea     rdx, [rax+8]; lplpszProgID
0x1805521fb  mov     rcx, rsi; clsid
0x1805521fe  call    cs:__imp_ProgIDFromCLSID
0x180552204  test    eax, eax
0x180552206  js      short loc_180552277
0x180552208  mov     r14d, edi
0x18055220b  mov     rsi, [rsp+48h+psz]
0x180552210  movzx   eax, word ptr [rsi]
0x180552213  test    ax, ax
0x180552216  jz      short loc_18055224E
0x180552218  cmp     ax, 2Eh ; '.'
0x18055221c  jnz     short loc_180552223
0x18055221e  mov     r14, rsi
0x180552221  jmp     short loc_180552234
0x180552223  movzx   ecx, ax; C
0x180552226  call    cs:__imp_iswdigit
0x18055222c  neg     eax
0x18055222e  sbb     rcx, rcx
0x180552231  and     r14, rcx
0x180552234  add     rsi, 2
0x180552238  movzx   eax, word ptr [rsi]
0x18055223b  test    ax, ax
0x18055223e  jnz     short loc_180552218
0x180552240  test    r14, r14
0x180552243  jz      short loc_180552249
0x180552245  mov     [r14], di
0x180552249  mov     rsi, [rsp+48h+psz]
0x18055224e  test    rsi, rsi
0x180552251  jz      short loc_1805522B0
0x180552253  xor     ecx, ecx; bstrString
0x180552255  call    cs:__imp_SysFreeString
0x18055225b  mov     rcx, rsi; psz
0x18055225e  call    cs:__imp_SysAllocString
0x180552264  mov     rbx, rax
0x180552267  mov     [rsp+48h+arg_10], rax
0x18055226c  test    rax, rax
0x18055226f  jz      loc_180552318
0x180552275  jmp     short loc_1805522AB
0x180552277  lea     rdx, [rsp+48h+psz]; lplpsz
0x18055227c  mov     rcx, rsi; rclsid
0x18055227f  call    cs:__imp_StringFromCLSID
0x180552285  cmp     eax, 8007000Eh
0x18055228a  jz      loc_180552311
0x180552290  cmp     eax, 86160210h
0x180552295  jz      short loc_180552311
0x180552297  cmp     eax, 86170103h
0x18055229c  jz      short loc_180552311
0x18055229e  cmp     eax, 86180110h
0x1805522a3  jz      short loc_180552311
0x1805522a5  test    eax, eax
0x1805522a7  js      short loc_180552322
0x1805522a9  jmp     short loc_180552249
0x1805522ab  mov     rsi, [rsp+48h+psz]
0x1805522b0  test    rsi, rsi
0x1805522b3  jz      short loc_1805522BE
0x1805522b5  mov     rcx, rsi; pv
0x1805522b8  call    cs:__imp_CoTaskMemFree
0x1805522be  test    rbx, rbx
0x1805522c1  jz      short loc_1805522DA
0x1805522c3  mov     rcx, rbx; bstr
0x1805522c6  call    cs:__imp_SysStringByteLen
0x1805522cc  mov     edx, eax; len
0x1805522ce  mov     rcx, rbx; psz
0x1805522d1  call    cs:__imp_SysAllocStringByteLen
0x1805522d7  mov     rdi, rax
0x1805522da  mov     [r15], rdi
0x1805522dd  mov     rcx, rbx; bstrString
0x1805522e0  call    cs:__imp_SysFreeString
0x1805522e6  xor     eax, eax
0x1805522e8  jmp     short loc_1805522FD
0x1805522ea  mov     eax, dword ptr [rsp+48h+psz]
0x1805522ee  mov     edx, 86160101h
0x1805522f3  cmp     [rsp+48h+var_20], 216h
0x1805522fa  cmovz   eax, edx
0x1805522fd  mov     rbx, [rsp+48h+arg_8]
0x180552302  mov     rsi, [rsp+48h+arg_18]
0x180552307  add     rsp, 30h
0x18055230b  pop     r15
0x18055230d  pop     r14
0x18055230f  pop     rdi
0x180552310  retn
0x180552311  mov     ecx, eax; int
0x180552313  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x180552318  mov     ecx, 8007000Eh; int
0x18055231d  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x180552322  mov     ecx, eax; int
0x180552324  call    ?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
```
