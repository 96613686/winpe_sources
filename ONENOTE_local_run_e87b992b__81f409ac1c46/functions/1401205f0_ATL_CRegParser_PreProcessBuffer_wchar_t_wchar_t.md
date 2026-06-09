# ATL::CRegParser::PreProcessBuffer(wchar_t *,wchar_t * *)

- ea: `0x1401205f0`
- end: `0x140120940`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEA_WPEAPEA_W@Z`
- size: `848`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, wchar_t *Str, wchar_t **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x140120d48`

## callees

- `0x14001193c`
- `0x140056ac0`
- `0x14011c2f8`
- `0x14011c8a0`
- `0x14011d540`
- `0x14011e5dc`
- `0x1401205f0`
- `0x14012276c`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x14012086f`
- `KERNEL32!lstrcmpiW` at `0x14012086f`
- `VCRUNTIME140!wcsstr` at `0x1401206e0`
- `VCRUNTIME140!wcsstr` at `0x1401206e0`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x140120845`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x140120845`
- `ole32!CoTaskMemFree` at `0x14012068f`
- `ole32!CoTaskMemFree` at `0x14012090a`
- `ole32!CoTaskMemFree` at `0x14012068f`
- `ole32!CoTaskMemFree` at `0x14012090a`
- `ole32!CoTaskMemAlloc` at `0x140120675`
- `ole32!CoTaskMemAlloc` at `0x140120675`
- `USER32!CharNextW` at `0x1401206f3`
- `USER32!CharNextW` at `0x1401206ff`
- `USER32!CharNextW` at `0x14012070b`
- `USER32!CharNextW` at `0x140120717`
- `USER32!CharNextW` at `0x140120771`
- `USER32!CharNextW` at `0x1401207d9`
- `USER32!CharNextW` at `0x1401208b6`
- `USER32!CharNextW` at `0x1401208d5`
- `USER32!CharNextW` at `0x1401206f3`
- `USER32!CharNextW` at `0x1401206ff`
- `USER32!CharNextW` at `0x14012070b`
- `USER32!CharNextW` at `0x140120717`
- `USER32!CharNextW` at `0x140120771`
- `USER32!CharNextW` at `0x1401207d9`
- `USER32!CharNextW` at `0x1401208b6`
- `USER32!CharNextW` at `0x1401208d5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(LPCWSTR *this, wchar_t *Str, wchar_t **a3)
{
  const wchar_t *v3; // rsi
  unsigned int v5; // ebx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  _WORD *v9; // rax
  bool v11; // al
  int v12; // r13d
  char v13; // r15
  char v14; // r14
  wchar_t *v15; // rax
  const WCHAR *v16; // rax
  const WCHAR *v17; // rax
  const WCHAR *v18; // rax
  const wchar_t *v19; // rax
  const wchar_t *v20; // rdx
  LPWSTR v21; // rax
  wchar_t *v22; // rax
  wchar_t *v23; // r14
  __int64 v24; // rcx
  errno_t v25; // eax
  LPCWSTR v26; // r12
  int v27; // esi
  __int64 v28; // r15
  const wchar_t **ValueAt; // rax
  const WCHAR *i; // rax
  wchar_t *v31; // rcx
  char v32; // [rsp+20h] [rbp-49h]
  char v33; // [rsp+21h] [rbp-48h]
  bool v34; // [rsp+22h] [rbp-47h]
  _DWORD v35[2]; // [rsp+28h] [rbp-41h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-39h]
  wchar_t **v37; // [rsp+38h] [rbp-31h]
  wchar_t Destination[32]; // [rsp+40h] [rbp-29h] BYREF

  v37 = a3;
  v3 = Str;
  v5 = 0;
  if ( !Str || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( Str[v6] );
  v7 = 2 * v6;
  if ( v7 < 100 )
    v7 = 1000;
  v35[0] = 0;
  v35[1] = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 <= 0xFFFFFFFF )
  {
    v9 = CoTaskMemAlloc((unsigned int)v8);
    pv = v9;
    if ( v9 )
      *v9 = 0;
  }
  else
  {
    v9 = 0;
    pv = 0;
  }
  if ( !v9 )
  {
    CoTaskMemFree(0);
    return 2147942414LL;
  }
  *this = v3;
  v11 = ATL::_AtlRegisterPerUser;
  v34 = ATL::_AtlRegisterPerUser;
  v12 = 0;
  v13 = 0;
  v33 = 0;
  v14 = 0;
  v32 = 0;
  while ( *v3 )
  {
    if ( !v11 )
      goto LABEL_35;
    if ( !v12 )
    {
      v15 = wcsstr(v3, L"HKCR");
      if ( v15 )
      {
        if ( v15 == *this )
        {
          v16 = CharNextW(*this);
          *this = v16;
          v17 = CharNextW(v16);
          *this = v17;
          v18 = CharNextW(v17);
          *this = v18;
          *this = CharNextW(v18);
          if ( !(unsigned int)ATL::CRegParser::CParseBuffer::AddString(
                                (ATL::CRegParser::CParseBuffer *)v35,
                                L"HKCU\r\n{\tSoftware\r\n\t{\r\n\t\tClasses") )
            goto LABEL_39;
          v13 = 1;
          v33 = 1;
        }
      }
    }
    if ( **this != 39 )
      goto LABEL_27;
    if ( !v14 )
    {
      v14 = 1;
      v32 = 1;
      goto LABEL_35;
    }
    if ( !(unsigned int)ATL::CRegParser::EndOfVar((ATL::CRegParser *)this) )
    {
      v19 = CharNextW(*this);
      *this = v19;
      if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v35, v19, 1) )
        goto LABEL_39;
LABEL_27:
      if ( v14 )
        goto LABEL_35;
      goto LABEL_28;
    }
    v14 = 0;
    v32 = 0;
LABEL_28:
    if ( **this == 123 )
      ++v12;
    if ( **this == 125 && !--v12 && v13 == 1 )
    {
      if ( !(unsigned int)ATL::CRegParser::CParseBuffer::AddString(
                            (ATL::CRegParser::CParseBuffer *)v35,
                            L"\r\n\t}\r\n}\r\n") )
        goto LABEL_39;
      v13 = 0;
      v33 = 0;
    }
LABEL_35:
    v20 = *this;
    if ( **this != 37 )
      goto LABEL_38;
    v21 = CharNextW(*this);
    *this = v21;
    if ( *v21 == 37 )
    {
      v20 = v21;
LABEL_38:
      if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)v35, v20, 1) )
        goto LABEL_39;
      goto LABEL_54;
    }
    v22 = ATL::CRegParser::StrChr(v21, 0x25u);
    v23 = v22;
    if ( !v22 )
      goto LABEL_55;
    v24 = v22 - *this;
    if ( v24 > 31 )
    {
      v5 = -2147467259;
      goto LABEL_58;
    }
    v25 = wcsncpy_s(Destination, 0x20u, *this, (int)v24);
    ATL::AtlCrtErrorCheck(v25);
    v26 = this[1];
    v27 = 0;
    v28 = 0;
    while ( v27 < *((_DWORD *)v26 + 6) )
    {
      if ( !lstrcmpiW(*(LPCWSTR *)(v28 + *((_QWORD *)v26 + 1)), Destination) )
        goto LABEL_47;
      ++v27;
      v28 += 8;
    }
    v27 = -1;
LABEL_47:
    if ( v27 == -1
      || (ValueAt = (const wchar_t **)ATL::CSimpleMap<wchar_t *,wchar_t *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                                        v26 + 4,
                                        (unsigned int)v27),
          !*ValueAt) )
    {
LABEL_55:
      v5 = -2147352567;
      goto LABEL_58;
    }
    if ( !(unsigned int)ATL::CRegParser::CParseBuffer::AddString((ATL::CRegParser::CParseBuffer *)v35, *ValueAt) )
    {
LABEL_39:
      v5 = -2147024882;
      goto LABEL_58;
    }
    for ( i = *this; i != v23; *this = i )
      i = CharNextW(i);
    v13 = v33;
    v14 = v32;
LABEL_54:
    v3 = CharNextW(*this);
    *this = v3;
    v11 = v34;
  }
  v31 = (wchar_t *)pv;
  pv = 0;
  *v37 = v31;
LABEL_58:
  CoTaskMemFree(pv);
  return v5;
}

```

## disassembly

```asm
0x1401205f0  mov     [rsp-8+arg_8], rbx
0x1401205f5  push    rbp
0x1401205f6  push    rsi
0x1401205f7  push    rdi
0x1401205f8  push    r12
0x1401205fa  push    r13
0x1401205fc  push    r14
0x1401205fe  push    r15
0x140120600  lea     rbp, [rsp-27h]
0x140120605  sub     rsp, 90h
0x14012060c  mov     rax, cs:__security_cookie
0x140120613  xor     rax, rsp
0x140120616  mov     [rbp+57h+var_40], rax
0x14012061a  mov     [rbp+57h+var_88], r8
0x14012061e  mov     rsi, rdx
0x140120621  mov     rdi, rcx
0x140120624  xor     ebx, ebx
0x140120626  test    rdx, rdx
0x140120629  jz      loc_140120914
0x14012062f  test    r8, r8
0x140120632  jz      loc_140120914
0x140120638  mov     [r8], rbx
0x14012063b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14012063f  inc     rax
0x140120642  cmp     [rdx+rax*2], bx
0x140120646  jnz     short loc_14012063F
0x140120648  add     eax, eax
0x14012064a  mov     ecx, 3E8h
0x14012064f  cmp     eax, 64h ; 'd'
0x140120652  cmovl   eax, ecx
0x140120655  mov     [rbp+57h+var_98], ebx
0x140120658  mov     [rbp+57h+var_94], eax
0x14012065b  mov     ecx, eax
0x14012065d  add     rcx, rcx
0x140120660  mov     eax, 0FFFFFFFFh
0x140120665  cmp     rcx, rax
0x140120668  jbe     short loc_140120673
0x14012066a  mov     rax, rbx
0x14012066d  mov     [rbp+57h+pv], rbx
0x140120671  jmp     short loc_140120687
0x140120673  mov     ecx, ecx; cb
0x140120675  call    cs:__imp_CoTaskMemAlloc
0x14012067b  mov     [rbp+57h+pv], rax
0x14012067f  test    rax, rax
0x140120682  jz      short loc_140120687
0x140120684  mov     [rax], bx
0x140120687  test    rax, rax
0x14012068a  jnz     short loc_14012069F
0x14012068c  mov     rcx, rax; pv
0x14012068f  call    cs:__imp_CoTaskMemFree
0x140120695  mov     eax, 8007000Eh
0x14012069a  jmp     loc_140120919
0x14012069f  mov     [rdi], rsi
0x1401206a2  mov     al, cs:?_AtlRegisterPerUser@ATL@@3_NA; bool ATL::_AtlRegisterPerUser
0x1401206a8  mov     [rbp+57h+var_9E], al
0x1401206ab  mov     r13d, ebx
0x1401206ae  mov     r15b, bl
0x1401206b1  mov     [rbp+57h+var_9F], bl
0x1401206b4  mov     r14b, bl
0x1401206b7  mov     [rbp+57h+var_A0], bl
0x1401206ba  mov     r12d, 25h ; '%'
0x1401206c0  cmp     [rsi], bx
0x1401206c3  jz      loc_1401208F7
0x1401206c9  cmp     al, 1
0x1401206cb  jnz     loc_1401207CD
0x1401206d1  test    r13d, r13d
0x1401206d4  jnz     short loc_14012073F
0x1401206d6  lea     rdx, aHkcr; "HKCR"
0x1401206dd  mov     rcx, rsi; Str
0x1401206e0  call    cs:__imp_wcsstr
0x1401206e6  test    rax, rax
0x1401206e9  jz      short loc_14012073F
0x1401206eb  cmp     rax, [rdi]
0x1401206ee  jnz     short loc_14012073F
0x1401206f0  mov     rcx, [rdi]; lpsz
0x1401206f3  call    cs:__imp_CharNextW
0x1401206f9  mov     [rdi], rax
0x1401206fc  mov     rcx, rax; lpsz
0x1401206ff  call    cs:__imp_CharNextW
0x140120705  mov     [rdi], rax
0x140120708  mov     rcx, rax; lpsz
0x14012070b  call    cs:__imp_CharNextW
0x140120711  mov     [rdi], rax
0x140120714  mov     rcx, rax; lpsz
0x140120717  call    cs:__imp_CharNextW
0x14012071d  mov     [rdi], rax
0x140120720  lea     rdx, aHkcuSoftwareCl; "HKCU\r\n{\tSoftware\r\n\t{\r\n\t\tClass"...
0x140120727  lea     rcx, [rbp+57h+var_98]; this
0x14012072b  call    ?AddString@CParseBuffer@CRegParser@ATL@@QEAAHPEB_W@Z; ATL::CRegParser::CParseBuffer::AddString(wchar_t const *)
0x140120730  test    eax, eax
0x140120732  jz      loc_140120802
0x140120738  mov     r15b, 1
0x14012073b  mov     [rbp+57h+var_9F], r15b
0x14012073f  mov     rax, [rdi]
0x140120742  mov     ecx, 27h ; '''
0x140120747  cmp     cx, [rax]
0x14012074a  jnz     short loc_140120790
0x14012074c  test    r14b, r14b
0x14012074f  jnz     short loc_14012075A
0x140120751  mov     r14b, 1
0x140120754  mov     [rbp+57h+var_A0], r14b
0x140120758  jmp     short loc_1401207CD
0x14012075a  mov     rcx, rdi; this
0x14012075d  call    ?EndOfVar@CRegParser@ATL@@IEAAHXZ; ATL::CRegParser::EndOfVar(void)
0x140120762  test    eax, eax
0x140120764  jz      short loc_14012076E
0x140120766  mov     r14b, bl
0x140120769  mov     [rbp+57h+var_A0], bl
0x14012076c  jmp     short loc_140120795
0x14012076e  mov     rcx, [rdi]; lpsz
0x140120771  call    cs:__imp_CharNextW
0x140120777  mov     [rdi], rax
0x14012077a  mov     r8d, 1; int
0x140120780  mov     rdx, rax; wchar_t *
0x140120783  lea     rcx, [rbp+57h+var_98]; this
0x140120787  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z; ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)
0x14012078c  test    eax, eax
0x14012078e  jz      short loc_140120802
0x140120790  test    r14b, r14b
0x140120793  jnz     short loc_1401207CD
0x140120795  mov     rax, [rdi]
0x140120798  cmp     word ptr [rax], 7Bh ; '{'
0x14012079c  jnz     short loc_1401207A1
0x14012079e  inc     r13d
0x1401207a1  cmp     word ptr [rax], 7Dh ; '}'
0x1401207a5  jnz     short loc_1401207CD
0x1401207a7  sub     r13d, 1
0x1401207ab  jnz     short loc_1401207CD
0x1401207ad  cmp     r15b, 1
0x1401207b1  jnz     short loc_1401207CD
0x1401207b3  lea     rdx, asc_1402049D8; "\r\n\t}\r\n}\r\n"
0x1401207ba  lea     rcx, [rbp+57h+var_98]; this
0x1401207be  call    ?AddString@CParseBuffer@CRegParser@ATL@@QEAAHPEB_W@Z; ATL::CRegParser::CParseBuffer::AddString(wchar_t const *)
0x1401207c3  test    eax, eax
0x1401207c5  jz      short loc_140120802
0x1401207c7  mov     r15b, bl
0x1401207ca  mov     [rbp+57h+var_9F], bl
0x1401207cd  mov     rdx, [rdi]
0x1401207d0  cmp     [rdx], r12w
0x1401207d4  jnz     short loc_1401207EB
0x1401207d6  mov     rcx, rdx; lpsz
0x1401207d9  call    cs:__imp_CharNextW
0x1401207df  mov     [rdi], rax
0x1401207e2  cmp     [rax], r12w
0x1401207e6  jnz     short loc_14012080C
0x1401207e8  mov     rdx, rax; wchar_t *
0x1401207eb  mov     r8d, 1; int
0x1401207f1  lea     rcx, [rbp+57h+var_98]; this
0x1401207f5  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z; ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)
0x1401207fa  test    eax, eax
0x1401207fc  jnz     loc_1401208D2
0x140120802  mov     ebx, 8007000Eh
0x140120807  jmp     loc_140120906
0x14012080c  mov     edx, r12d; wchar_t
0x14012080f  mov     rcx, rax; lpsz
0x140120812  call    ?StrChr@CRegParser@ATL@@KAPEA_WPEA_W_W@Z; ATL::CRegParser::StrChr(wchar_t *,wchar_t)
0x140120817  mov     r14, rax
0x14012081a  test    rax, rax
0x14012081d  jz      loc_1401208E9
0x140120823  mov     rcx, rax
0x140120826  sub     rcx, [rdi]
0x140120829  sar     rcx, 1
0x14012082c  cmp     rcx, 1Fh
0x140120830  jg      loc_1401208F0
0x140120836  movsxd  r9, ecx; MaxCount
0x140120839  mov     r8, [rdi]; Source
0x14012083c  mov     edx, 20h ; ' '; SizeInWords
0x140120841  lea     rcx, [rbp+57h+Destination]; Destination
0x140120845  call    cs:__imp_wcsncpy_s
0x14012084b  mov     ecx, eax; int
0x14012084d  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x140120852  mov     r12, [rdi+8]
0x140120856  mov     esi, ebx
0x140120858  mov     r15, rbx
0x14012085b  cmp     esi, [r12+18h]
0x140120860  jge     short loc_140120881
0x140120862  mov     rax, [r12+8]
0x140120867  lea     rdx, [rbp+57h+Destination]; lpString2
0x14012086b  mov     rcx, [r15+rax]; lpString1
0x14012086f  call    cs:__imp_lstrcmpiW
0x140120875  test    eax, eax
0x140120877  jz      short loc_140120884
0x140120879  inc     esi
0x14012087b  add     r15, 8
0x14012087f  jmp     short loc_14012085B
0x140120881  or      esi, 0FFFFFFFFh
0x140120884  cmp     esi, 0FFFFFFFFh
0x140120887  jz      short loc_1401208E9
0x140120889  mov     edx, esi
0x14012088b  lea     rcx, [r12+8]
0x140120890  call    ?GetValueAt@?$CSimpleMap@PEA_WPEA_WVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEA_WH@Z; ATL::CSimpleMap<wchar_t *,wchar_t *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x140120895  cmp     [rax], rbx
0x140120898  jz      short loc_1401208E9
0x14012089a  mov     rdx, [rax]; wchar_t *
0x14012089d  lea     rcx, [rbp+57h+var_98]; this
0x1401208a1  call    ?AddString@CParseBuffer@CRegParser@ATL@@QEAAHPEB_W@Z; ATL::CRegParser::CParseBuffer::AddString(wchar_t const *)
0x1401208a6  test    eax, eax
0x1401208a8  jz      loc_140120802
0x1401208ae  mov     rax, [rdi]
0x1401208b1  jmp     short loc_1401208BF
0x1401208b3  mov     rcx, rax; lpsz
0x1401208b6  call    cs:__imp_CharNextW
0x1401208bc  mov     [rdi], rax
0x1401208bf  cmp     rax, r14
0x1401208c2  jnz     short loc_1401208B3
0x1401208c4  mov     r12d, 25h ; '%'
0x1401208ca  mov     r15b, [rbp+57h+var_9F]
0x1401208ce  mov     r14b, [rbp+57h+var_A0]
0x1401208d2  mov     rcx, [rdi]; lpsz
0x1401208d5  call    cs:__imp_CharNextW
0x1401208db  mov     rsi, rax
0x1401208de  mov     [rdi], rax
0x1401208e1  mov     al, [rbp+57h+var_9E]
0x1401208e4  jmp     loc_1401206C0
0x1401208e9  mov     ebx, 80020009h
0x1401208ee  jmp     short loc_140120906
0x1401208f0  mov     ebx, 80004005h
0x1401208f5  jmp     short loc_140120906
0x1401208f7  mov     rcx, [rbp+57h+pv]
0x1401208fb  mov     [rbp+57h+pv], rbx
0x1401208ff  mov     rax, [rbp+57h+var_88]
0x140120903  mov     [rax], rcx
0x140120906  mov     rcx, [rbp+57h+pv]; pv
0x14012090a  call    cs:__imp_CoTaskMemFree
0x140120910  mov     eax, ebx
0x140120912  jmp     short loc_140120919
0x140120914  mov     eax, 80004003h
0x140120919  mov     rcx, [rbp+57h+var_40]
0x14012091d  xor     rcx, rsp; StackCookie
0x140120920  call    __security_check_cookie
0x140120925  mov     rbx, [rsp+0C0h+arg_8]
0x14012092d  add     rsp, 90h
0x140120934  pop     r15
0x140120936  pop     r14
0x140120938  pop     r13
0x14012093a  pop     r12
0x14012093c  pop     rdi
0x14012093d  pop     rsi
0x14012093e  pop     rbp
0x14012093f  retn
```
