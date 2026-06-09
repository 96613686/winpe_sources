# CErrorString::CErrorString(long,int)

- ea: `0x140048f9c`
- end: `0x140049248`
- name: `??0CErrorString@@QEAA@JH@Z`
- size: `684`
- prototype: `CErrorString *__fastcall(CErrorString *this, DWORD dwMessageId)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x14002a0cc`

## callees

- `0x1400030a0`
- `0x1400198c4`
- `0x140028218`
- `0x140028508`
- `0x140029bd4`
- `0x14002a8ec`
- `0x140048f9c`
- `0x140049250`
- `0x1400492f4`
- `0x140049388`
- `0x140049454`
- `0x140049520`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x1400491a7`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x1400491a7`
- `api-ms-win-crt-private-l1-1-0!_o_strerror` at `0x1400490b9`
- `api-ms-win-crt-private-l1-1-0!_o_strerror` at `0x1400490b9`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140049083`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140049175`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140049083`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140049175`

## string_xrefs

- `0x1400490d1`: `onecoreuap\base\appmodel\search\common\pkmutild\lmstr.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
CErrorString *__fastcall CErrorString::CErrorString(CErrorString *this, DWORD dwMessageId)
{
  wchar_t *v3; // rbx
  DWORD v4; // esi
  int v5; // eax
  __int64 v6; // r15
  CResourceLibrary *WininetError; // rax
  unsigned int v8; // edx
  unsigned int v9; // r9d
  unsigned int v10; // r8d
  DWORD v11; // eax
  __int64 v12; // rax
  const CHAR *v13; // r13
  __int64 v14; // r14
  unsigned int v15; // r12d
  unsigned int v16; // edx
  wchar_t v17; // ax
  int lpBuffer; // [rsp+28h] [rbp-79h]
  unsigned int nSize; // [rsp+30h] [rbp-71h]
  char **v21; // [rsp+38h] [rbp-69h]
  void **v22; // [rsp+68h] [rbp-39h] BYREF
  wchar_t *v23; // [rsp+70h] [rbp-31h]
  __int64 v24; // [rsp+78h] [rbp-29h]
  _WORD v25[28]; // [rsp+80h] [rbp-21h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+100h] [rbp+5Fh]

  v3 = (wchar_t *)((char *)this + 24);
  *((_QWORD *)this + 1) = (char *)this + 24;
  *((_QWORD *)this + 2) = 1025;
  *((_WORD *)this + 12) = 0;
  *(_QWORD *)this = &CErrorString::`vftable';
  v4 = -2147216127;
  if ( dwMessageId != -2147418113 )
    v4 = dwMessageId;
  v5 = v4 & 0x1FFF0000;
  v6 = -1;
  if ( (v4 & 0x1FFF0000) == 0x70000 )
  {
    if ( (unsigned int)(unsigned __int16)v4 - 12001 <= 0xC0 )
    {
      WininetError = CErrorString::GetWininetError(this);
      v9 = 1024;
      v10 = (unsigned __int16)v4;
LABEL_6:
      v11 = CResourceLibrary::FormatMessageW(WininetError, v8, v10, v9, v3, nSize, v21);
      goto LABEL_22;
    }
    if ( (unsigned int)(unsigned __int16)v4 - 5632 <= 0x250 )
      goto LABEL_8;
    v11 = FormatMessageW(0x1000u, 0, (unsigned __int16)v4, 0x400u, (LPWSTR)this + 12, 0x400u, 0);
  }
  else
  {
    if ( v5 == 0x40000 )
    {
      if ( (unsigned int)(unsigned __int16)v4 - 5632 > 0x250 )
      {
        WininetError = CErrorString::GetResLibError(this);
        goto LABEL_9;
      }
LABEL_8:
      WininetError = CErrorString::GetCIError();
LABEL_9:
      v9 = 0;
      v10 = v4;
      goto LABEL_6;
    }
    if ( v5 != 6619136 )
    {
LABEL_30:
      FormatMessageW(0x1000u, 0, v4, 0x400u, v3, 0x400u, 0);
      goto LABEL_31;
    }
    v12 = _o_strerror((unsigned __int16)v4);
    v13 = (const CHAR *)v12;
    if ( !v12 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB6,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\pkmutild\\lmstr.cxx",
        (const char *)0x80004003LL,
        lpBuffer);
    v14 = -1;
    do
      ++v14;
    while ( *(_BYTE *)(v14 + v12) );
    v15 = v14 + 1;
    if ( (unsigned int)(v14 + 1) > *((_DWORD *)this + 4) )
      CLMString::GrowInConstructor(this, v15);
    v11 = MultiByteToWideCharSZ(v13, v14, *((wchar_t **)this + 1), v15);
    *((_DWORD *)this + 5) = v11;
  }
LABEL_22:
  v16 = v11;
  if ( !v11 )
    goto LABEL_30;
  *((_WORD *)this + 1036) = 0;
  while ( 1 )
  {
    v17 = *v3;
    if ( !*v3 )
      break;
    if ( v17 == 13 || v17 == 10 )
      *v3 = 32;
    ++v3;
  }
  CLMString::Truncate(this, v16);
LABEL_31:
  v23 = v25;
  v24 = 24;
  v25[0] = 0;
  v22 = &CNumString::`vftable';
  _o__itow_s(v4, v25, 24, 16);
  CLMString::Truncate((CLMString *)&v22, 0x17u);
  do
    ++v6;
  while ( v25[v6] );
  CLMString::Truncate((CLMString *)&v22, v6);
  CLMString::Append(this, L"(HRESULT : 0x", 0xFFFFFFFF);
  CLMString::Append(this, v23, 0xFFFFFFFF);
  CLMString::Append(this, L")", 0xFFFFFFFF);
  CNumString::~CNumString((CNumString *)&v22);
  *((_WORD *)this + 1036) = 0;
  return this;
}

```

## disassembly

```asm
0x140048f9c  mov     rax, rsp
0x140048f9f  push    rbp
0x140048fa0  push    rsi
0x140048fa1  push    rdi
0x140048fa2  push    r12
0x140048fa4  push    r13
0x140048fa6  push    r14
0x140048fa8  push    r15
0x140048faa  lea     rbp, [rax-5Fh]
0x140048fae  sub     rsp, 0C0h
0x140048fb5  mov     [rbp+57h+var_B0], 0FFFFFFFFFFFFFFFEh
0x140048fbd  mov     [rax+18h], rbx
0x140048fc1  mov     rax, cs:__security_cookie
0x140048fc8  xor     rax, rsp
0x140048fcb  mov     [rbp+57h+var_40], rax
0x140048fcf  mov     rdi, rcx
0x140048fd2  mov     [rbp+57h+var_A0], rcx
0x140048fd6  lea     rbx, [rcx+18h]
0x140048fda  mov     [rcx+8], rbx
0x140048fde  mov     qword ptr [rcx+10h], 401h
0x140048fe6  xor     r12d, r12d
0x140048fe9  mov     [rbx], r12w
0x140048fed  lea     rax, ??_7CErrorString@@6B@; const CErrorString::`vftable'
0x140048ff4  mov     [rcx], rax
0x140048ff7  mov     esi, 80041501h
0x140048ffc  cmp     edx, 8000FFFFh
0x140049002  cmovnz  esi, edx
0x140049005  mov     eax, esi
0x140049007  and     eax, 1FFF0000h
0x14004900c  mov     r13d, 400h
0x140049012  or      r15, 0FFFFFFFFFFFFFFFFh
0x140049016  cmp     eax, 70000h
0x14004901b  jnz     short loc_14004908E
0x14004901d  movzx   r14d, si
0x140049021  lea     eax, [r14-2EE1h]
0x140049028  cmp     eax, 0C0h
0x14004902d  ja      short loc_14004904C
0x14004902f  call    ?GetWininetError@CErrorString@@AEAAAEAVCResourceLibrary@@XZ; CErrorString::GetWininetError(void)
0x140049034  mov     r9d, r13d; unsigned int
0x140049037  mov     r8d, r14d; unsigned int
0x14004903a  mov     [rsp+0F0h+lpBuffer], rbx; wchar_t *
0x14004903f  mov     rcx, rax; this
0x140049042  call    ?FormatMessageW@CResourceLibrary@@QEAAIKIIPEA_WIPEAPEAD@Z; CResourceLibrary::FormatMessageW(ulong,uint,uint,wchar_t *,uint,char * *)
0x140049047  jmp     loc_140049122
0x14004904c  lea     eax, [r14-1600h]
0x140049053  cmp     eax, 250h
0x140049058  ja      short loc_140049067
0x14004905a  call    ?GetCIError@CErrorString@@CAAEAVCResourceLibrary@@XZ; CErrorString::GetCIError(void)
0x14004905f  xor     r9d, r9d
0x140049062  mov     r8d, esi
0x140049065  jmp     short loc_14004903A
0x140049067  mov     [rsp+30h], r12; Arguments
0x14004906c  mov     [rsp+0F0h+nSize], r13d; nSize
0x140049071  mov     [rsp+0F0h+lpBuffer], rbx; lpBuffer
0x140049076  mov     r9d, r13d; dwLanguageId
0x140049079  mov     r8d, r14d; dwMessageId
0x14004907c  xor     edx, edx; lpSource
0x14004907e  mov     ecx, 1000h; dwFlags
0x140049083  call    cs:__imp_FormatMessageW
0x140049089  jmp     loc_140049122
0x14004908e  cmp     eax, 40000h
0x140049093  jnz     short loc_1400490AB
0x140049095  movzx   eax, si
0x140049098  sub     eax, 1600h
0x14004909d  cmp     eax, 250h
0x1400490a2  jbe     short loc_14004905A
0x1400490a4  call    ?GetResLibError@CErrorString@@AEAAAEAVCResourceLibrary@@XZ; CErrorString::GetResLibError(void)
0x1400490a9  jmp     short loc_14004905F
0x1400490ab  cmp     eax, 650000h
0x1400490b0  jnz     loc_140049159
0x1400490b6  movzx   ecx, si
0x1400490b9  call    cs:__imp__o_strerror
0x1400490bf  mov     r13, rax
0x1400490c2  test    rax, rax
0x1400490c5  jnz     short loc_1400490E3
0x1400490c7  mov     rcx, [rbp+5Fh]; this
0x1400490cb  mov     r9d, 80004003h; char *
0x1400490d1  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\search\\com"...
0x1400490d8  mov     edx, 0B6h; void *
0x1400490dd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400490e3  mov     r14, r15
0x1400490e6  inc     r14
0x1400490e9  cmp     [r14+rax], r12b
0x1400490ed  jnz     short loc_1400490E6
0x1400490ef  lea     r12d, [r14+1]
0x1400490f3  cmp     r12d, [rdi+10h]
0x1400490f7  jbe     short loc_140049104
0x1400490f9  mov     edx, r12d; unsigned int
0x1400490fc  mov     rcx, rdi; this
0x1400490ff  call    ?GrowInConstructor@CLMString@@IEAAXI@Z; CLMString::GrowInConstructor(uint)
0x140049104  mov     r9d, r12d; int
0x140049107  mov     r8, [rdi+8]; wchar_t *
0x14004910b  mov     edx, r14d; cbMultiByte
0x14004910e  mov     rcx, r13; lpMultiByteStr
0x140049111  call    ?MultiByteToWideCharSZ@@YAHPEBDHPEA_WH@Z; MultiByteToWideCharSZ(char const *,int,wchar_t *,int)
0x140049116  mov     [rdi+14h], eax
0x140049119  xor     r12d, r12d
0x14004911c  mov     r13d, 400h
0x140049122  mov     edx, eax; unsigned int
0x140049124  test    eax, eax
0x140049126  jz      short loc_140049159
0x140049128  mov     [rdi+818h], r12w
0x140049130  jmp     short loc_140049147
0x140049132  cmp     ax, 0Dh
0x140049136  jz      short loc_14004913E
0x140049138  cmp     ax, 0Ah
0x14004913c  jnz     short loc_140049143
0x14004913e  mov     word ptr [rbx], 20h ; ' '
0x140049143  add     rbx, 2
0x140049147  movzx   eax, word ptr [rbx]
0x14004914a  test    ax, ax
0x14004914d  jnz     short loc_140049132
0x14004914f  mov     rcx, rdi; this
0x140049152  call    ?Truncate@CLMString@@QEAAXI@Z; CLMString::Truncate(uint)
0x140049157  jmp     short loc_14004917B
0x140049159  mov     [rsp+30h], r12; Arguments
0x14004915e  mov     [rsp+0F0h+nSize], r13d; nSize
0x140049163  mov     [rsp+0F0h+lpBuffer], rbx; lpBuffer
0x140049168  mov     r9d, r13d; dwLanguageId
0x14004916b  mov     r8d, esi; dwMessageId
0x14004916e  xor     edx, edx; lpSource
0x140049170  mov     ecx, 1000h; dwFlags
0x140049175  call    cs:__imp_FormatMessageW
0x14004917b  lea     rax, [rbp+57h+var_78]
0x14004917f  mov     [rbp+57h+var_88], rax
0x140049183  mov     r8d, 18h
0x140049189  mov     [rbp+57h+var_80], r8
0x14004918d  mov     [rbp+57h+var_78], r12w
0x140049192  lea     rax, ??_7CNumString@@6B@; const CNumString::`vftable'
0x140049199  mov     [rbp+57h+var_90], rax
0x14004919d  lea     r9d, [r8-8]
0x1400491a1  lea     rdx, [rbp+57h+var_78]
0x1400491a5  mov     ecx, esi
0x1400491a7  call    cs:__imp__o__itow_s
0x1400491ad  mov     edx, 17h; unsigned int
0x1400491b2  lea     rcx, [rbp+57h+var_90]; this
0x1400491b6  call    ?Truncate@CLMString@@QEAAXI@Z; CLMString::Truncate(uint)
0x1400491bb  lea     rax, [rbp+57h+var_78]
0x1400491bf  inc     r15
0x1400491c2  cmp     [rax+r15*2], r12w
0x1400491c7  jnz     short loc_1400491BF
0x1400491c9  mov     edx, r15d; unsigned int
0x1400491cc  lea     rcx, [rbp+57h+var_90]; this
0x1400491d0  call    ?Truncate@CLMString@@QEAAXI@Z; CLMString::Truncate(uint)
0x1400491d5  nop
0x1400491d6  or      ebx, 0FFFFFFFFh
0x1400491d9  mov     r8d, ebx; unsigned int
0x1400491dc  lea     rdx, aHresult0x; "(HRESULT : 0x"
0x1400491e3  mov     rcx, rdi; this
0x1400491e6  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x1400491eb  mov     r8d, ebx; unsigned int
0x1400491ee  mov     rdx, [rbp+57h+var_88]; wchar_t *
0x1400491f2  mov     rcx, rdi; this
0x1400491f5  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x1400491fa  mov     r8d, ebx; unsigned int
0x1400491fd  lea     rdx, asc_140058F08; ")"
0x140049204  mov     rcx, rdi; this
0x140049207  call    ?Append@CLMString@@QEAAHPEB_WI@Z; CLMString::Append(wchar_t const *,uint)
0x14004920c  nop
0x14004920d  lea     rcx, [rbp+57h+var_90]; this
0x140049211  call    ??1CNumString@@UEAA@XZ; CNumString::~CNumString(void)
0x140049216  mov     [rdi+818h], r12w
0x14004921e  mov     rax, rdi
0x140049221  mov     rcx, [rbp+57h+var_40]
0x140049225  xor     rcx, rsp; StackCookie
0x140049228  call    __security_check_cookie
0x14004922d  mov     rbx, [rsp+0F0h+arg_10]
0x140049235  add     rsp, 0C0h
0x14004923c  pop     r15
0x14004923e  pop     r14
0x140049240  pop     r13
0x140049242  pop     r12
0x140049244  pop     rdi
0x140049245  pop     rsi
0x140049246  pop     rbp
0x140049247  retn
```
