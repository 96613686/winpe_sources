# Speller::CSuggestProcessor::SuggestGermanCompounds2(int)

- ea: `0x18003916c`
- end: `0x180039580`
- name: `?SuggestGermanCompounds2@CSuggestProcessor@Speller@@AEAAXH@Z`
- size: `1044`
- prototype: `void __fastcall(Speller::CSuggestProcessor *__hidden this, int)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1800967ac`

## callees

- `0x180009690`
- `0x180009710`
- `0x18000a630`
- `0x180035640`
- `0x18003916c`
- `0x180039588`
- `0x18003ed6c`
- `0x1800925e4`
- `0x180093564`
- `0x1800966e0`
- `0x180096934`
- `0x18009e300`
- `0x1800b0010`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18003933a`
- `msvcrt!wcsncpy_s` at `0x180039459`
- `msvcrt!wcsncpy_s` at `0x18003933a`
- `msvcrt!wcsncpy_s` at `0x180039459`

## pseudocode

```c
void __fastcall Speller::CSuggestProcessor::SuggestGermanCompounds2(Speller::CSuggestProcessor *this, unsigned int a2)
{
  __int64 v2; // rax
  unsigned __int64 v5; // rsi
  __int64 v6; // rax
  char v7; // bl
  bool v8; // r8
  bool v9; // r9
  unsigned int i; // edi
  struct Speller::CSuggestion *v11; // r12
  __int64 j; // r14
  __int16 v13; // bx
  bool v14; // dl
  __int64 v15; // rax
  __int64 v16; // rbx
  wchar_t v17; // bx
  wchar_t v18; // ax
  int *v19; // rax
  wchar_t v20; // bx
  wchar_t v21; // ax
  unsigned int v22; // edx
  bool v23; // [rsp+30h] [rbp-D0h]
  int v24; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v25; // [rsp+38h] [rbp-C8h]
  _BYTE v26[4]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v27[4]; // [rsp+44h] [rbp-BCh] BYREF
  _BYTE v28[8]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE pExceptionObject[64]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v30; // [rsp+90h] [rbp-70h] BYREF
  int v31; // [rsp+A0h] [rbp-60h]
  wchar_t Destination[72]; // [rsp+B0h] [rbp-50h] BYREF
  const void *retaddr; // [rsp+188h] [rbp+88h]

  v2 = *((_QWORD *)this + 1);
  if ( (unsigned __int64)a2 >= *(_QWORD *)(v2 + 112) )
  {
    CNLException::CNLException((CNLException *)pExceptionObject, 2147942487LL, retaddr);
    throw (CNLException *)pExceptionObject;
  }
  v5 = *(_QWORD *)(v2 + 104) + ((unsigned __int64)a2 << 7);
  if ( *(int *)(v5 + 80) < 7 )
  {
    if ( *(_BYTE *)(v5 + 65) )
    {
      if ( !*(_BYTE *)(v5 + 66) && Speller::CSuggestProcessor::ShouldRunSuggestions(this, a2) )
      {
        v6 = *((_QWORD *)this + 1);
        v7 = *(_BYTE *)(v6 + 9);
        *(_BYTE *)(v6 + 9) = 1;
        SuppLexDataCollection::Load(*(SuppLexDataCollection **)(*((_QWORD *)this + 1) + 56LL), 2);
        Speller::CSuggestProcessor::Suggest(this, a2, v8, v9);
        *(_BYTE *)(*((_QWORD *)this + 1) + 9LL) = v7;
        SuppLexDataCollection::Load(*(SuppLexDataCollection **)(*((_QWORD *)this + 1) + 56LL), 0);
        for ( i = 0; i < 954437177 * (unsigned int)((__int64)(*(_QWORD *)(v5 + 104) - *(_QWORD *)(v5 + 96)) >> 4); ++i )
        {
          v11 = Speller::CSuggestionCollection::GetAt((Speller::CSuggestionCollection *)(v5 + 88), i);
          if ( *((_DWORD *)v11 + 33) == *(_DWORD *)(v5 + 8) + 1 )
          {
            for ( j = 0; (unsigned int)j < *(_DWORD *)(v5 + 8) - 1; j = (unsigned int)(j + 1) )
            {
              v13 = CMN_CharLowerW(*(unsigned __int16 *)(*(_QWORD *)(v5 + 24) + 2 * j));
              if ( v13 != (unsigned __int16)CMN_CharLowerW(*((unsigned __int16 *)v11 + j)) )
              {
                v14 = 0;
                if ( *((_WORD *)v11 + j) != 101 )
                  v14 = *((_WORD *)v11 + j) != 115;
                if ( ((unsigned int)j <= 1
                   || *((_WORD *)v11 + j) != 115
                   || *((_WORD *)v11 + (unsigned int)(j - 1)) != 115)
                  && !v14
                  && (_DWORD)j
                  && (_DWORD)j != *((_DWORD *)v11 + 33) - 1 )
                {
                  wcsncpy_s(Destination, 0x41u, (const wchar_t *)v11, (int)j + 1LL);
                  v31 = 0;
                  v15 = *((_QWORD *)this + 1);
                  v30 = 0;
                  v16 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(*(_QWORD *)(v15 + 32) + 168LL) + 56LL))(*(_QWORD *)(*(_QWORD *)(v15 + 32) + 168LL));
                  v25 = v16;
                  (*(void (__fastcall **)(__int64, int *, wchar_t *, __int64, __int128 *))(*(_QWORD *)v16 + 208LL))(
                    v16,
                    &v24,
                    Destination,
                    (int)j + 1LL,
                    &v30);
                  if ( (v24 & 0xFFFFFFu) - 16777214 > 1 && (v30 & 0x1400) != 0 )
                    goto LABEL_29;
                  v17 = Destination[0];
                  v18 = (unsigned int)CMN_IsCharUpperW(Destination[0]) ? CMN_CharLowerW(v17) : CMN_CharUpperW(v17);
                  v16 = v25;
                  Destination[0] = v18;
                  v24 = *(_DWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *, wchar_t *, __int64, __int128 *))(*(_QWORD *)v25 + 208LL))(
                                     v25,
                                     v26,
                                     Destination,
                                     (int)j + 1LL,
                                     &v30);
                  if ( (v24 & 0xFFFFFFu) - 16777214 > 1 && ((((unsigned int)v30 >> 10) & 4) != 0 || (v30 & 0x400) != 0) )
                  {
LABEL_29:
                    wcsncpy_s(Destination, 0x41u, (const wchar_t *)v11 + (int)j + 1, *((_DWORD *)v11 + 33) - (int)j - 1);
                    v19 = (int *)(*(__int64 (__fastcall **)(__int64, _BYTE *, wchar_t *, __int64, __int128 *))(*(_QWORD *)v16 + 208LL))(
                                   v16,
                                   v27,
                                   Destination,
                                   *((_DWORD *)v11 + 33) - (int)j - 1LL,
                                   &v30);
                    v20 = Destination[0];
                    v24 = *v19;
                    v23 = (v24 & 0xFFFFFFu) - 16777214 > 1;
                    v21 = (unsigned int)CMN_IsCharUpperW(Destination[0]) ? CMN_CharLowerW(v20) : CMN_CharUpperW(v20);
                    Destination[0] = v21;
                    v24 = *(_DWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *, wchar_t *, __int64, __int128 *))(*(_QWORD *)v25 + 208LL))(
                                       v25,
                                       v28,
                                       Destination,
                                       *((_DWORD *)v11 + 33) - (int)j - 1LL,
                                       &v30);
                    if ( (v24 & 0xFFFFFFu) - 16777214 > 1 || v23 )
                      goto LABEL_35;
                  }
                }
                break;
              }
            }
          }
          v22 = i--;
          Speller::CSuggestionCollection::RemoveAt((Speller::CSuggestionCollection *)(v5 + 88), v22);
LABEL_35:
          ;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18003916c  mov     [rsp-8+arg_10], rbx
0x180039171  push    rbp
0x180039172  push    rsi
0x180039173  push    rdi
0x180039174  push    r12
0x180039176  push    r13
0x180039178  push    r14
0x18003917a  push    r15
0x18003917c  lea     rbp, [rsp-50h]
0x180039181  sub     rsp, 150h
0x180039188  mov     rax, cs:__security_cookie
0x18003918f  xor     rax, rsp
0x180039192  mov     [rbp+80h+var_40], rax
0x180039196  mov     rax, [rcx+8]
0x18003919a  mov     r13, rcx
0x18003919d  mov     edi, edx
0x18003919f  mov     esi, edx
0x1800391a1  cmp     rdi, [rax+70h]
0x1800391a5  jb      short loc_1800391CF
0x1800391a7  mov     r8, [rbp+88h]; void *
0x1800391ae  lea     rcx, [rsp+180h+pExceptionObject]; this
0x1800391b3  mov     edx, 80070057h; int
0x1800391b8  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x1800391bd  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x1800391c4  lea     rcx, [rsp+180h+pExceptionObject]; pExceptionObject
0x1800391c9  call    _CxxThrowException_0
0x1800391cf  shl     rsi, 7
0x1800391d3  add     rsi, [rax+68h]
0x1800391d7  cmp     dword ptr [rsi+50h], 7
0x1800391db  jge     loc_180039559
0x1800391e1  cmp     byte ptr [rsi+41h], 0
0x1800391e5  jz      loc_180039559
0x1800391eb  cmp     byte ptr [rsi+42h], 0
0x1800391ef  jnz     loc_180039559
0x1800391f5  mov     edx, edi; int
0x1800391f7  call    ?ShouldRunSuggestions@CSuggestProcessor@Speller@@AEAA_NH@Z; Speller::CSuggestProcessor::ShouldRunSuggestions(int)
0x1800391fc  test    al, al
0x1800391fe  jz      loc_180039559
0x180039204  mov     rax, [r13+8]
0x180039208  mov     edx, 2; int
0x18003920d  mov     bl, [rax+9]
0x180039210  mov     byte ptr [rax+9], 1
0x180039214  mov     rcx, [r13+8]
0x180039218  mov     rcx, [rcx+38h]; this
0x18003921c  call    ?Load@SuppLexDataCollection@@QEAA_NH@Z; SuppLexDataCollection::Load(int)
0x180039221  mov     edx, edi; int
0x180039223  mov     rcx, r13; this
0x180039226  call    ?Suggest@CSuggestProcessor@Speller@@AEAA_NH_N0@Z; Speller::CSuggestProcessor::Suggest(int,bool,bool)
0x18003922b  mov     rax, [r13+8]
0x18003922f  xor     edx, edx; int
0x180039231  mov     [rax+9], bl
0x180039234  mov     rcx, [r13+8]
0x180039238  mov     rcx, [rcx+38h]; this
0x18003923c  call    ?Load@SuppLexDataCollection@@QEAA_NH@Z; SuppLexDataCollection::Load(int)
0x180039241  lea     r15, [rsi+58h]
0x180039245  mov     rcx, 8E38E38E38E38E39h
0x18003924f  mov     rax, [r15+10h]
0x180039253  xor     edi, edi
0x180039255  sub     rax, [r15+8]
0x180039259  sar     rax, 4
0x18003925d  imul    rax, rcx
0x180039261  test    eax, eax
0x180039263  jz      loc_180039559
0x180039269  mov     edx, edi; unsigned int
0x18003926b  mov     rcx, r15; this
0x18003926e  call    ?GetAt@CSuggestionCollection@Speller@@QEBAAEAVCSuggestion@2@I@Z; Speller::CSuggestionCollection::GetAt(uint)
0x180039273  mov     ecx, [rsi+8]
0x180039276  mov     edx, 1
0x18003927b  add     ecx, edx
0x18003927d  mov     r12, rax
0x180039280  cmp     [rax+84h], ecx
0x180039286  jnz     loc_180039529
0x18003928c  xor     r14d, r14d
0x18003928f  mov     eax, [rsi+8]
0x180039292  sub     eax, edx
0x180039294  cmp     r14d, eax
0x180039297  jnb     loc_180039529
0x18003929d  mov     rcx, [rsi+18h]
0x1800392a1  movzx   ecx, word ptr [rcx+r14*2]
0x1800392a6  call    CMN_CharLowerW
0x1800392ab  movzx   ecx, word ptr [r12+r14*2]
0x1800392b0  movzx   ebx, ax
0x1800392b3  call    CMN_CharLowerW
0x1800392b8  cmp     bx, ax
0x1800392bb  jnz     short loc_1800392C7
0x1800392bd  mov     edx, 1
0x1800392c2  add     r14d, edx
0x1800392c5  jmp     short loc_18003928F
0x1800392c7  xor     dl, dl
0x1800392c9  mov     ecx, 1
0x1800392ce  cmp     word ptr [r12+r14*2], 65h ; 'e'
0x1800392d4  jz      short loc_1800392E2
0x1800392d6  cmp     word ptr [r12+r14*2], 73h ; 's'
0x1800392dc  movzx   edx, dl
0x1800392df  cmovnz  edx, ecx
0x1800392e2  cmp     r14d, ecx
0x1800392e5  jbe     short loc_180039304
0x1800392e7  cmp     word ptr [r12+r14*2], 73h ; 's'
0x1800392ed  jnz     short loc_180039304
0x1800392ef  lea     eax, [r14-1]
0x1800392f3  cmp     word ptr [r12+rax*2], 73h ; 's'
0x1800392f9  jz      loc_180039529
0x1800392ff  mov     ecx, 1
0x180039304  test    dl, dl
0x180039306  jnz     loc_180039529
0x18003930c  test    r14d, r14d
0x18003930f  jz      loc_180039529
0x180039315  mov     eax, [r12+84h]
0x18003931d  sub     eax, ecx
0x18003931f  cmp     r14d, eax
0x180039322  jz      loc_180039529
0x180039328  movsxd  r9, r14d
0x18003932b  lea     rcx, [rbp+80h+Destination]; Destination
0x18003932f  inc     r9; MaxCount
0x180039332  mov     r8, r12; Source
0x180039335  mov     edx, 41h ; 'A'; SizeInWords
0x18003933a  call    cs:__imp_wcsncpy_s
0x180039340  xor     eax, eax
0x180039342  xorps   xmm0, xmm0
0x180039345  mov     [rbp+80h+var_E0], eax
0x180039348  mov     rax, [r13+8]
0x18003934c  movups  [rbp+80h+var_F0], xmm0
0x180039350  mov     rcx, [rax+20h]
0x180039354  mov     rcx, [rcx+0A8h]
0x18003935b  mov     rax, [rcx]
0x18003935e  mov     rax, [rax+38h]
0x180039362  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039367  mov     rbx, rax
0x18003936a  mov     [rsp+180h+var_148], rax
0x18003936f  movsxd  r9, r14d
0x180039372  lea     r8, [rbp+80h+Destination]
0x180039376  inc     r9
0x180039379  lea     rdx, [rsp+180h+var_14C]
0x18003937e  mov     rcx, [rax]
0x180039381  mov     rax, [rcx+0D0h]
0x180039388  lea     rcx, [rbp+80h+var_F0]
0x18003938c  mov     [rsp+180h+var_160], rcx
0x180039391  mov     rcx, rbx
0x180039394  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039399  mov     ecx, [rsp+180h+var_14C]
0x18003939d  and     ecx, 0FFFFFFh
0x1800393a3  sub     ecx, 0FFFFFEh
0x1800393a9  cmp     ecx, 1
0x1800393ac  jbe     short loc_1800393B7
0x1800393ae  test    dword ptr [rbp+80h+var_F0], 1400h
0x1800393b5  jnz     short loc_180039436
0x1800393b7  movzx   ebx, [rbp+80h+Destination]
0x1800393bb  movzx   ecx, bx
0x1800393be  call    CMN_IsCharUpperW
0x1800393c3  movzx   ecx, bx
0x1800393c6  test    eax, eax
0x1800393c8  jz      short loc_1800393D1
0x1800393ca  call    CMN_CharLowerW
0x1800393cf  jmp     short loc_1800393D6
0x1800393d1  call    CMN_CharUpperW
0x1800393d6  mov     rbx, [rsp+180h+var_148]
0x1800393db  lea     rcx, [rbp+80h+var_F0]
0x1800393df  mov     [rbp+80h+Destination], ax
0x1800393e3  lea     r8, [rbp+80h+Destination]
0x1800393e7  mov     [rsp+180h+var_160], rcx
0x1800393ec  lea     rdx, [rsp+180h+var_140]
0x1800393f1  movsxd  r9, r14d
0x1800393f4  mov     rcx, rbx
0x1800393f7  mov     rax, [rbx]
0x1800393fa  inc     r9
0x1800393fd  mov     rax, [rax+0D0h]
0x180039404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039409  mov     ecx, [rax]
0x18003940b  mov     [rsp+180h+var_14C], ecx
0x18003940f  and     ecx, 0FFFFFFh
0x180039415  sub     ecx, 0FFFFFEh
0x18003941b  cmp     ecx, 1
0x18003941e  jbe     loc_180039529
0x180039424  mov     eax, dword ptr [rbp+80h+var_F0]
0x180039427  shr     eax, 0Ah
0x18003942a  test    al, 4
0x18003942c  jnz     short loc_180039436
0x18003942e  test    al, 1
0x180039430  jz      loc_180039529
0x180039436  mov     eax, [r12+84h]
0x18003943e  lea     rcx, [rbp+80h+Destination]; Destination
0x180039442  sub     eax, r14d
0x180039445  mov     edx, 41h ; 'A'; SizeInWords
0x18003944a  dec     eax
0x18003944c  movsxd  r9, eax; MaxCount
0x18003944f  movsxd  rax, r14d
0x180039452  inc     rax
0x180039455  lea     r8, [r12+rax*2]; Source
0x180039459  call    cs:__imp_wcsncpy_s
0x18003945f  mov     rcx, [rbx]
0x180039462  lea     r8, [rbp+80h+Destination]
0x180039466  mov     eax, [r12+84h]
0x18003946e  lea     rdx, [rsp+180h+var_13C]
0x180039473  sub     eax, r14d
0x180039476  movsxd  r9, eax
0x180039479  mov     rax, [rcx+0D0h]
0x180039480  dec     r9
0x180039483  lea     rcx, [rbp+80h+var_F0]
0x180039487  mov     [rsp+180h+var_160], rcx
0x18003948c  mov     rcx, rbx
0x18003948f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039494  movzx   ebx, [rbp+80h+Destination]
0x180039498  mov     ecx, [rax]
0x18003949a  mov     [rsp+180h+var_14C], ecx
0x18003949e  and     ecx, 0FFFFFFh
0x1800394a4  sub     ecx, 0FFFFFEh
0x1800394aa  cmp     ecx, 1
0x1800394ad  movzx   ecx, bx
0x1800394b0  setnbe  [rsp+180h+var_150]
0x1800394b5  call    CMN_IsCharUpperW
0x1800394ba  movzx   ecx, bx
0x1800394bd  test    eax, eax
0x1800394bf  jz      short loc_1800394C8
0x1800394c1  call    CMN_CharLowerW
0x1800394c6  jmp     short loc_1800394CD
0x1800394c8  call    CMN_CharUpperW
0x1800394cd  mov     r10, [rsp+180h+var_148]
0x1800394d2  lea     r8, [rbp+80h+Destination]
0x1800394d6  mov     [rbp+80h+Destination], ax
0x1800394da  lea     rdx, [rsp+180h+var_138]
0x1800394df  mov     eax, [r12+84h]
0x1800394e7  sub     eax, r14d
0x1800394ea  mov     rcx, [r10]
0x1800394ed  movsxd  r9, eax
0x1800394f0  dec     r9
0x1800394f3  mov     rax, [rcx+0D0h]
0x1800394fa  lea     rcx, [rbp+80h+var_F0]
0x1800394fe  mov     [rsp+180h+var_160], rcx
0x180039503  mov     rcx, r10
0x180039506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003950b  mov     ecx, [rax]
0x18003950d  mov     [rsp+180h+var_14C], ecx
0x180039511  and     ecx, 0FFFFFFh
0x180039517  sub     ecx, 0FFFFFEh
0x18003951d  cmp     ecx, 1
0x180039520  ja      short loc_180039535
0x180039522  cmp     [rsp+180h+var_150], 0
0x180039527  jnz     short loc_180039535
0x180039529  mov     edx, edi; unsigned int
0x18003952b  mov     rcx, r15; this
0x18003952e  dec     edi
0x180039530  call    ?RemoveAt@CSuggestionCollection@Speller@@QEAAXI@Z; Speller::CSuggestionCollection::RemoveAt(uint)
0x180039535  mov     rax, [r15+10h]
0x180039539  mov     rcx, 8E38E38E38E38E39h
0x180039543  sub     rax, [r15+8]
0x180039547  inc     edi
0x180039549  sar     rax, 4
0x18003954d  imul    rax, rcx
0x180039551  cmp     edi, eax
0x180039553  jb      loc_180039269
0x180039559  mov     rcx, [rbp+80h+var_40]
0x18003955d  xor     rcx, rsp; StackCookie
0x180039560  call    __security_check_cookie
0x180039565  mov     rbx, [rsp+180h+arg_10]
0x18003956d  add     rsp, 150h
0x180039574  pop     r15
0x180039576  pop     r14
0x180039578  pop     r13
0x18003957a  pop     r12
0x18003957c  pop     rdi
0x18003957d  pop     rsi
0x18003957e  pop     rbp
0x18003957f  retn
```
