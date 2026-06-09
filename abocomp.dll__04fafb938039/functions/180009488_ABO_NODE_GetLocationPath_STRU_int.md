# ABO_NODE::GetLocationPath(STRU *,int)

- ea: `0x180009488`
- end: `0x18000980f`
- name: `?GetLocationPath@ABO_NODE@@QEAAJPEAVSTRU@@H@Z`
- size: `903`
- prototype: `__int64 __fastcall(ABO_NODE *__hidden this, struct STRU *, int)`
- caller_count: `5`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180009818`
- `0x180009ce0`
- `0x18000a1c0`
- `0x18000aaa8`
- `0x180023cf0`

## callees

- `0x18000341a`
- `0x180003460`
- `0x18000473c`
- `0x180007ac8`
- `0x180008bf8`
- `0x180009488`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180009600`
- `msvcrt!_wcsnicmp` at `0x180009639`
- `msvcrt!_wcsnicmp` at `0x18000976a`
- `msvcrt!_wcsnicmp` at `0x180009600`
- `msvcrt!_wcsnicmp` at `0x180009639`
- `msvcrt!_wcsnicmp` at `0x18000976a`
- `msvcrt!wcschr` at `0x180009677`
- `msvcrt!wcschr` at `0x180009677`
- `msvcrt!wcstoul` at `0x180009697`
- `msvcrt!wcstoul` at `0x180009697`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800095db`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180009614`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800096bb`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800095db`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180009614`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800096bb`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18000978c`
- `iisutil!?Copy@STRU@@QEAAJAEBV1@@Z` at `0x18000978c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800094e5`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180009512`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180009538`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000955d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800094e5`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180009512`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180009538`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000955d`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800097bd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800097c8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800097d2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800097dd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800097bd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800097c8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800097d2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800097dd`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800095cd`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800095f0`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180009629`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180009652`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180009664`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800096ad`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800096d9`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800096ed`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000971e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800095cd`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800095f0`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180009629`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180009652`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180009664`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800096ad`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800096d9`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800096ed`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000971e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800097a4`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800097a4`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800096fe`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800096fe`

## pseudocode

```c
__int64 __fastcall ABO_NODE::GetLocationPath(ABO_NODE *this, struct STRU *a2, int a3)
{
  __int64 v6; // rdi
  __int64 v7; // r14
  int v8; // ebx
  const unsigned __int16 *Str; // rax
  const wchar_t *v10; // rax
  const wchar_t *v11; // rax
  unsigned __int16 *v12; // rbx
  wchar_t *v13; // rax
  const unsigned __int16 *v14; // rax
  __int64 v15; // rbx
  const unsigned __int16 *v16; // rax
  ABO_NODE *v17; // rbx
  const unsigned __int16 *v18; // rax
  wchar_t *EndPtr; // [rsp+20h] [rbp-E0h] BYREF
  ABO_NODE *v21; // [rsp+28h] [rbp-D8h] BYREF
  _BYTE v22[56]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v23[56]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v24[56]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v25[56]; // [rsp+D8h] [rbp-28h] BYREF
  wchar_t v26[12]; // [rsp+110h] [rbp+10h] BYREF
  wchar_t String2[12]; // [rsp+128h] [rbp+28h] BYREF
  unsigned __int16 v28[256]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 v29[256]; // [rsp+340h] [rbp+240h] BYREF
  unsigned __int16 v30[256]; // [rsp+540h] [rbp+440h] BYREF
  unsigned __int16 v31[256]; // [rsp+740h] [rbp+640h] BYREF

  memset_0(v28, 0, sizeof(v28));
  STRU::STRU((STRU *)v22, v28, 0x100u);
  v21 = 0;
  memset_0(v29, 0, sizeof(v29));
  STRU::STRU((STRU *)v25, v29, 0x100u);
  memset_0(v30, 0, sizeof(v30));
  STRU::STRU((STRU *)v23, v30, 0x100u);
  memset_0(v31, 0, sizeof(v31));
  STRU::STRU((STRU *)v24, v31, 0x100u);
  v6 = -1;
  v7 = -1;
  wcscpy(v26, L"/LM/W3SVC");
  do
    ++v7;
  while ( v26[v7] );
  wcscpy(String2, L"/LM/MIMEMAP");
  do
    ++v6;
  while ( String2[v6] );
  EndPtr = 0;
  if ( a2 )
  {
    Str = STRU::QueryStr((ABO_NODE *)((char *)this + 256));
    v8 = STRU::Copy((STRU *)v22, Str);
    if ( v8 < 0 )
      goto LABEL_20;
    v10 = STRU::QueryStr((STRU *)v22);
    if ( !_wcsnicmp(v10, String2, (unsigned int)v6) )
    {
LABEL_9:
      v8 = STRU::Copy(a2, &word_18002E968);
      goto LABEL_20;
    }
    v11 = STRU::QueryStr((STRU *)v22);
    if ( _wcsnicmp(v11, v26, (unsigned int)v7) )
    {
LABEL_11:
      v8 = -2147024894;
      goto LABEL_20;
    }
    if ( !STRU::QueryStr((STRU *)v22)[(unsigned int)v7] )
      goto LABEL_9;
    v12 = &STRU::QueryStr((STRU *)v22)[(unsigned int)v7];
    v13 = wcschr(v12 + 1, 0x2Fu);
    if ( v13 )
    {
      v15 = v13 - STRU::QueryStr((STRU *)v22);
      v16 = STRU::QueryStr((STRU *)v22);
      v8 = STRU::Copy((STRU *)v23, v16, v15);
      if ( v8 < 0 )
        goto LABEL_20;
    }
    else
    {
      if ( !a3 )
        goto LABEL_11;
      wcstoul(v12 + 1, &EndPtr, 10);
      if ( *EndPtr )
        goto LABEL_11;
      v14 = STRU::QueryStr((STRU *)v22);
      v8 = STRU::Copy((STRU *)v23, v14);
      if ( v8 < 0 )
        goto LABEL_20;
    }
    v17 = *(ABO_NODE **)(*((_QWORD *)this + 22) + 16LL);
    v18 = STRU::QueryStr((STRU *)v23);
    ABO_NODE::FindNode(v17, v18, &v21);
  }
  v8 = -2147024809;
LABEL_20:
  STRU::~STRU((STRU *)v24);
  STRU::~STRU((STRU *)v23);
  STRU::~STRU((STRU *)v25);
  STRU::~STRU((STRU *)v22);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180009488  mov     [rsp-8+arg_10], rbx
0x18000948d  push    rbp
0x18000948e  push    rsi
0x18000948f  push    rdi
0x180009490  push    r12
0x180009492  push    r13
0x180009494  push    r14
0x180009496  push    r15
0x180009498  lea     rbp, [rsp-850h]
0x1800094a0  sub     rsp, 950h
0x1800094a7  mov     rax, cs:__security_cookie
0x1800094ae  xor     rax, rsp
0x1800094b1  mov     [rbp+880h+var_40], rax
0x1800094b8  mov     r15d, r8d
0x1800094bb  mov     rsi, rdx
0x1800094be  mov     r13, rcx
0x1800094c1  mov     edi, 200h
0x1800094c6  mov     r8d, edi; Size
0x1800094c9  lea     rcx, [rbp+880h+var_840]; void *
0x1800094cd  xor     edx, edx; Val
0x1800094cf  call    memset_0
0x1800094d4  mov     ebx, 100h
0x1800094d9  lea     rdx, [rbp+880h+var_840]
0x1800094dd  mov     r8d, ebx
0x1800094e0  lea     rcx, [rsp+980h+var_950]
0x1800094e5  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800094eb  xor     r12d, r12d
0x1800094ee  lea     rcx, [rbp+880h+var_640]; void *
0x1800094f5  mov     r8d, edi; Size
0x1800094f8  mov     [rsp+980h+var_958], r12
0x1800094fd  xor     edx, edx; Val
0x1800094ff  call    memset_0
0x180009504  mov     r8d, ebx
0x180009507  lea     rdx, [rbp+880h+var_640]
0x18000950e  lea     rcx, [rbp+880h+var_8A8]
0x180009512  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180009518  mov     r8d, edi; Size
0x18000951b  lea     rcx, [rbp+880h+var_440]; void *
0x180009522  xor     edx, edx; Val
0x180009524  call    memset_0
0x180009529  mov     r8d, ebx
0x18000952c  lea     rdx, [rbp+880h+var_440]
0x180009533  lea     rcx, [rsp+980h+var_918]
0x180009538  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000953e  mov     r8d, edi; Size
0x180009541  lea     rcx, [rbp+880h+var_240]; void *
0x180009548  xor     edx, edx; Val
0x18000954a  call    memset_0
0x18000954f  mov     r8d, ebx
0x180009552  lea     rdx, [rbp+880h+var_240]
0x180009559  lea     rcx, [rbp+880h+var_8E0]
0x18000955d  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180009563  mov     eax, dword ptr cs:aLmW3svc_0+10h; "C"
0x180009569  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000956d  movups  xmm0, xmmword ptr cs:aLmW3svc_0; "/LM/W3SVC"
0x180009574  mov     [rbp+880h+var_860], eax
0x180009577  mov     r14, rdi
0x18000957a  lea     rax, [rbp+880h+var_870]
0x18000957e  movups  xmmword ptr [rbp+880h+var_870], xmm0
0x180009582  inc     r14
0x180009585  cmp     [rax+r14*2], r12w
0x18000958a  jnz     short loc_180009582
0x18000958c  movups  xmm0, xmmword ptr cs:aLmMimemap_0; "/LM/MIMEMAP"
0x180009593  lea     rax, [rbp+880h+String2]
0x180009597  movsd   xmm1, qword ptr cs:aLmMimemap_0+10h; "MAP"
0x18000959f  movups  xmmword ptr [rbp+880h+String2], xmm0
0x1800095a3  movsd   [rbp+880h+var_848], xmm1
0x1800095a8  inc     rdi
0x1800095ab  cmp     [rax+rdi*2], r12w
0x1800095b0  jnz     short loc_1800095A8
0x1800095b2  mov     [rsp+980h+EndPtr], r12
0x1800095b7  test    rsi, rsi
0x1800095ba  jnz     short loc_1800095C6
0x1800095bc  mov     ebx, 80070057h
0x1800095c1  jmp     loc_1800097B9
0x1800095c6  lea     rcx, [r13+100h]
0x1800095cd  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800095d3  mov     rdx, rax
0x1800095d6  lea     rcx, [rsp+980h+var_950]
0x1800095db  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800095e1  mov     ebx, eax
0x1800095e3  test    eax, eax
0x1800095e5  js      loc_1800097B9
0x1800095eb  lea     rcx, [rsp+980h+var_950]
0x1800095f0  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800095f6  mov     r8d, edi; MaxCount
0x1800095f9  lea     rdx, [rbp+880h+String2]; String2
0x1800095fd  mov     rcx, rax; String1
0x180009600  call    cs:__imp__wcsnicmp
0x180009606  test    eax, eax
0x180009608  jnz     short loc_180009621
0x18000960a  lea     rdx, word_18002E968
0x180009611  mov     rcx, rsi
0x180009614  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000961a  mov     ebx, eax
0x18000961c  jmp     loc_1800097B9
0x180009621  lea     rcx, [rsp+980h+var_950]
0x180009626  mov     ebx, r14d
0x180009629  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000962f  mov     r8d, r14d; MaxCount
0x180009632  lea     rdx, [rbp+880h+var_870]; String2
0x180009636  mov     rcx, rax; String1
0x180009639  call    cs:__imp__wcsnicmp
0x18000963f  test    eax, eax
0x180009641  jz      short loc_18000964D
0x180009643  mov     ebx, 80070002h
0x180009648  jmp     loc_1800097B9
0x18000964d  lea     rcx, [rsp+980h+var_950]
0x180009652  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180009658  cmp     [rax+rbx*2], r12w
0x18000965d  jz      short loc_18000960A
0x18000965f  lea     rcx, [rsp+980h+var_950]
0x180009664  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000966a  mov     edx, 2Fh ; '/'; Ch
0x18000966f  lea     rbx, [rax+rbx*2]
0x180009673  lea     rcx, [rbx+2]; Str
0x180009677  call    cs:__imp_wcschr
0x18000967d  mov     rdi, rax
0x180009680  test    rax, rax
0x180009683  jnz     short loc_1800096D1
0x180009685  test    r15d, r15d
0x180009688  jz      short loc_180009643
0x18000968a  lea     r8d, [rax+0Ah]; Radix
0x18000968e  lea     rdx, [rsp+980h+EndPtr]; EndPtr
0x180009693  lea     rcx, [rbx+2]; String
0x180009697  call    cs:__imp_wcstoul
0x18000969d  mov     rcx, [rsp+980h+EndPtr]
0x1800096a2  cmp     [rcx], r12w
0x1800096a6  jnz     short loc_180009643
0x1800096a8  lea     rcx, [rsp+980h+var_950]
0x1800096ad  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800096b3  mov     rdx, rax
0x1800096b6  lea     rcx, [rsp+980h+var_918]
0x1800096bb  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800096c1  mov     ebx, eax
0x1800096c3  test    eax, eax
0x1800096c5  js      loc_1800097B9
0x1800096cb  lea     r15d, [rdi+1]
0x1800096cf  jmp     short loc_18000970E
0x1800096d1  lea     rcx, [rsp+980h+var_950]
0x1800096d6  mov     r15d, r12d
0x1800096d9  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800096df  mov     rbx, rdi
0x1800096e2  lea     rcx, [rsp+980h+var_950]
0x1800096e7  sub     rbx, rax
0x1800096ea  sar     rbx, 1
0x1800096ed  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800096f3  mov     r8d, ebx
0x1800096f6  lea     rcx, [rsp+980h+var_918]
0x1800096fb  mov     rdx, rax
0x1800096fe  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180009704  mov     ebx, eax
0x180009706  test    eax, eax
0x180009708  js      loc_1800097B9
0x18000970e  mov     rax, [r13+0B0h]
0x180009715  lea     rcx, [rsp+980h+var_918]
0x18000971a  mov     rbx, [rax+10h]
0x18000971e  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180009724  lea     r8, [rsp+980h+var_958]; struct ABO_NODE **
0x180009729  mov     rcx, rbx; this
0x18000972c  mov     rdx, rax; unsigned __int16 *
0x18000972f  call    ?FindNode@ABO_NODE@@QEAAJPEBGPEAPEAV1@@Z; ABO_NODE::FindNode(ushort const *,ABO_NODE * *)
0x180009734  mov     r14, [rsp+980h+var_958]
0x180009739  mov     ebx, eax
0x18000973b  test    eax, eax
0x18000973d  js      short loc_1800097AC
0x18000973f  lea     r8, [rbp+880h+var_8E0]; struct STRU *
0x180009743  mov     rcx, r14; this
0x180009746  call    ?GetAttributeValue@ABO_NODE@@QEAAJPEBGPEAVSTRU@@@Z; ABO_NODE::GetAttributeValue(ushort const *,STRU *)
0x18000974b  test    eax, eax
0x18000974d  jns     short loc_180009756
0x18000974f  mov     ebx, 80070002h
0x180009754  jmp     short loc_1800097AC
0x180009756  test    r15d, r15d
0x180009759  jnz     short loc_180009785
0x18000975b  lea     rcx, [rdi+2]; String1
0x18000975f  lea     r8d, [r15+4]; MaxCount
0x180009763  lea     rdx, aRoot_0; "ROOT"
0x18000976a  call    cs:__imp__wcsnicmp
0x180009770  test    eax, eax
0x180009772  jnz     short loc_18000974F
0x180009774  cmp     [rdi+0Ah], r12w
0x180009779  jz      short loc_180009785
0x18000977b  lea     eax, [r15+2Fh]
0x18000977f  cmp     [rdi+0Ah], ax
0x180009783  jnz     short loc_18000974F
0x180009785  lea     rdx, [rbp+880h+var_8E0]
0x180009789  mov     rcx, rsi
0x18000978c  call    cs:__imp_?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x180009792  mov     ebx, eax
0x180009794  test    eax, eax
0x180009796  js      short loc_1800097AC
0x180009798  test    r15d, r15d
0x18000979b  jnz     short loc_1800097AC
0x18000979d  lea     rdx, [rdi+0Ah]
0x1800097a1  mov     rcx, rsi
0x1800097a4  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800097aa  mov     ebx, eax
0x1800097ac  test    r14, r14
0x1800097af  jz      short loc_1800097B9
0x1800097b1  mov     rcx, r14; this
0x1800097b4  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x1800097b9  lea     rcx, [rbp+880h+var_8E0]
0x1800097bd  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800097c3  lea     rcx, [rsp+980h+var_918]
0x1800097c8  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800097ce  lea     rcx, [rbp+880h+var_8A8]
0x1800097d2  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800097d8  lea     rcx, [rsp+980h+var_950]
0x1800097dd  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800097e3  mov     eax, ebx
0x1800097e5  mov     rcx, [rbp+880h+var_40]
0x1800097ec  xor     rcx, rsp; StackCookie
0x1800097ef  call    __security_check_cookie
0x1800097f4  mov     rbx, [rsp+980h+arg_10]
0x1800097fc  add     rsp, 950h
0x180009803  pop     r15
0x180009805  pop     r14
0x180009807  pop     r13
0x180009809  pop     r12
0x18000980b  pop     rdi
0x18000980c  pop     rsi
0x18000980d  pop     rbp
0x18000980e  retn
```
