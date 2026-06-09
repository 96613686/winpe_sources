# NaturalLanguage6::CNLGSentenceSeparator::LoadCustomLexicon(void)

- ea: `0x180016540`
- end: `0x180016814`
- name: `?LoadCustomLexicon@CNLGSentenceSeparator@NaturalLanguage6@@IEAAJXZ`
- size: `724`
- prototype: `__int64 __fastcall(NaturalLanguage6::CNLGSentenceSeparator *__hidden this)`
- caller_count: `41`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180015b10`
- `0x1800160a0`
- `0x180032f40`
- `0x180033460`
- `0x1800338d0`
- `0x180033a40`
- `0x180033d90`
- `0x180034160`
- `0x1800421d0`
- `0x1800424c0`
- `0x1800427b0`
- `0x180042aa0`
- `0x180042d90`
- `0x180043080`
- `0x180043370`
- `0x180043900`
- `0x180043bf0`
- `0x180043ee0`
- `0x1800441d0`
- `0x1800444c0`
- `0x180044a80`
- `0x180045250`
- `0x180045540`
- `0x180045830`
- `0x180045b20`
- `0x180045f90`
- `0x180046280`
- `0x180046570`
- `0x180046860`
- `0x1800469c0`
- `0x180046fb0`
- `0x1800472a0`
- `0x180047590`
- `0x180047880`
- `0x180047b70`
- `0x180047e60`
- `0x180048150`
- `0x180048740`
- `0x180048a30`
- `0x180048d20`
- `0x180049010`

## callees

- `0x180003894`
- `0x180005160`
- `0x180016540`
- `0x180016a1c`
- `0x180017858`
- `0x180017aa4`
- `0x180030600`
- `0x180036b04`
- `0x18004d594`
- `0x18005af0c`
- `0x18009e300`
- `0x1800b0010`

## import_xrefs

- `msvcrt!_errno` at `0x1800166b1`
- `msvcrt!_errno` at `0x1800166b1`
- `msvcrt!_waccess` at `0x1800166a6`
- `msvcrt!_waccess` at `0x1800166a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall NaturalLanguage6::CNLGSentenceSeparator::LoadCustomLexicon(
        NaturalLanguage6::CNLGSentenceSeparator *this,
        __int64 a2,
        HINSTANCE a3)
{
  int v4; // ebx
  unsigned __int16 *v5; // rsi
  unsigned __int16 v6; // r15
  __int16 v7; // ax
  __int64 v8; // rbx
  unsigned __int16 *v9; // rcx
  unsigned __int64 v10; // rdi
  __int64 v11; // rdx
  unsigned __int16 *v12; // r8
  __int64 v13; // rax
  unsigned __int16 v14; // r9
  __int64 result; // rax
  unsigned __int64 v16; // rcx
  __int64 (__fastcall ***v17)(_QWORD, GUID *, __int64 *); // rax
  bool v18; // r8
  __int64 (__fastcall ***v19)(_QWORD, GUID *, __int64 *); // rax
  int v20; // eax
  struct IUnknown *v21; // rdi
  int v22; // eax
  unsigned int v23; // ebx
  _com_error *v24; // rbx
  __int64 v25; // [rsp+20h] [rbp-2C8h] BYREF
  int v26; // [rsp+28h] [rbp-2C0h]
  int v27; // [rsp+2Ch] [rbp-2BCh]
  unsigned int v28; // [rsp+30h] [rbp-2B8h]
  unsigned __int16 *v29; // [rsp+38h] [rbp-2B0h]
  __int64 i; // [rsp+40h] [rbp-2A8h]
  __int64 (__fastcall ***v31)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-2A0h] BYREF
  int v32; // [rsp+50h] [rbp-298h]
  unsigned __int16 *v33; // [rsp+58h] [rbp-290h]
  unsigned __int64 v34; // [rsp+60h] [rbp-288h]
  __int64 v35; // [rsp+68h] [rbp-280h]
  __int64 v36; // [rsp+70h] [rbp-278h]
  _com_error *v37; // [rsp+78h] [rbp-270h] BYREF
  unsigned __int16 v38[264]; // [rsp+90h] [rbp-258h] BYREF
  void *retaddr; // [rsp+2E8h] [rbp+0h]

  v36 = -2;
  v4 = 0;
  v5 = (unsigned __int16 *)((char *)this + 626);
  if ( !*((_WORD *)this + 313) )
  {
    v6 = *((_WORD *)this + 50);
    v7 = -1;
    while ( v6 != v7 )
    {
      if ( !(unsigned int)GetModuleFilePath(v5, 260, a3) )
        return 0;
      *((_WORD *)this + 573) = 0;
      v8 = -1;
      do
        ++v8;
      while ( v5[v8] );
      StringCchPrintfW(v38, 0x105u, L"Custom%04x.lex", v6);
      v9 = (unsigned __int16 *)((char *)this + 2 * v8 + 626);
      v26 = 0;
      v10 = 261 - v8;
      if ( 261 == v8 || (v4 = 0, v10 > 0x7FFFFFFF) )
        v4 = -2147024809;
      v26 = v4;
      if ( v4 < 0 )
      {
        if ( v10 )
          *v9 = 0;
      }
      else
      {
        v11 = 2147483646;
        v35 = 2147483646;
        v12 = v38;
        v33 = v38;
        v34 = v10;
        v29 = v9;
        v13 = 0;
        for ( i = 0; v10; i = v13 )
        {
          if ( !v11 )
            break;
          v14 = *v12;
          if ( !*v12 )
            break;
          v33 = ++v12;
          *v9++ = v14;
          v29 = v9;
          v34 = --v10;
          v35 = --v11;
          ++v13;
        }
        v4 = 0;
        if ( !v10 )
        {
          v29 = --v9;
          i = v13 - 1;
          v4 = -2147024774;
        }
        *v9 = 0;
        v26 = v4;
      }
      v27 = v4;
      if ( v4 < 0 )
        return 0;
      if ( _waccess(v5, 4) != -1 || *_errno() != 2 )
      {
        result = NaturalLanguage6::CNLGSentenceSeparator::InitTextContexts(this);
        v27 = result;
        if ( (int)result >= 0 )
        {
          try
          {
            v25 = 0;
            v17 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))NaturalLanguage6::Lexicon::operator new(v16);
            v31 = v17;
            if ( v17 )
              v19 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))NaturalLanguage6::Lexicon::Lexicon(
                                                                           (NaturalLanguage6::Lexicon *)v17,
                                                                           v5,
                                                                           v18);
            else
              v19 = 0;
            v31 = v19;
            v20 = _com_ptr_t<_com_IIID<NaturalLanguage6::ILexicon,&__s_GUID const _GUID_004cd7e2_8b63_4ef9_8d46_080cdbbe47af>>::_QueryInterface<IDispatch *>(
                    &v25,
                    &v31);
            if ( (int)(v20 + 0x80000000) >= 0 && v20 != -2147467262 )
              _com_issue_error(v20);
          }
          catch ( _com_error *v37 )
          {
            v24 = v37;
            ImxTraceCatch(1, *((unsigned int *)v37 + 2), retaddr);
            if ( *((_DWORD *)v24 + 2) == -2147024882 )
            {
              v28 = *((_DWORD *)v24 + 2);
              _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(&v25);
              return v28;
            }
            v32 = 0;
            _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(&v25);
            return 0;
          }
          v21 = (struct IUnknown *)*((_QWORD *)this + 7);
          v22 = ((__int64 (__fastcall *)(struct IUnknown *, __int64))v21->lpVtbl[4].QueryInterface)(v21, v25);
          v23 = v22;
          if ( v22 < 0 )
            _com_issue_errorex(v22, v21, &GUID_b6797cc0_11ae_4047_a438_26c0c916eb8d);
          v27 = v22;
          _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(&v25);
          return v23;
        }
        return result;
      }
      v7 = v6;
      v6 &= 0x3FFu;
    }
  }
  *v5 = 0;
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180016540  push    rbx
0x180016542  push    rsi
0x180016543  push    rdi
0x180016544  push    r12
0x180016546  push    r14
0x180016548  push    r15
0x18001654a  sub     rsp, 2B8h
0x180016551  mov     [rsp+2E8h+var_278], 0FFFFFFFFFFFFFFFEh
0x18001655a  mov     rax, cs:__security_cookie
0x180016561  xor     rax, rsp
0x180016564  mov     [rsp+2E8h+var_48], rax
0x18001656c  mov     r14, rcx
0x18001656f  xor     r12d, r12d
0x180016572  mov     ebx, r12d
0x180016575  lea     rsi, [rcx+272h]
0x18001657c  cmp     [rsi], r12w
0x180016580  jnz     loc_1800167F6
0x180016586  movzx   r15d, word ptr [rcx+64h]
0x18001658b  mov     eax, 0FFFFh
0x180016590  cmp     r15w, ax
0x180016594  jz      loc_1800167F6
0x18001659a  mov     edx, 104h; int
0x18001659f  mov     rcx, rsi; unsigned __int16 *
0x1800165a2  call    ?GetModuleFilePath@@YAHPEAGHPEAUHINSTANCE__@@@Z; GetModuleFilePath(ushort *,int,HINSTANCE__ *)
0x1800165a7  test    eax, eax
0x1800165a9  jz      loc_18001671B
0x1800165af  mov     [r14+47Ah], r12w
0x1800165b7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800165bb  inc     rbx
0x1800165be  cmp     [rsi+rbx*2], r12w
0x1800165c3  jnz     short loc_1800165BB
0x1800165c5  mov     edi, 105h
0x1800165ca  movzx   r9d, r15w
0x1800165ce  lea     r8, aCustom04xLex; "Custom%04x.lex"
0x1800165d5  mov     edx, edi; unsigned __int64
0x1800165d7  lea     rcx, [rsp+2E8h+var_258]; unsigned __int16 *
0x1800165df  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800165e4  lea     rcx, [r14+272h]
0x1800165eb  lea     rcx, [rcx+rbx*2]
0x1800165ef  mov     [rsp+2E8h+var_2C0], r12d
0x1800165f4  sub     rdi, rbx
0x1800165f7  jz      loc_18001671F
0x1800165fd  mov     ebx, r12d
0x180016600  cmp     rdi, 7FFFFFFFh
0x180016607  ja      loc_18001671F
0x18001660d  mov     [rsp+2E8h+var_2C0], ebx
0x180016611  test    ebx, ebx
0x180016613  js      loc_180016729
0x180016619  mov     edx, 7FFFFFFEh
0x18001661e  mov     [rsp+2E8h+var_280], rdx
0x180016623  lea     r8, [rsp+2E8h+var_258]
0x18001662b  mov     [rsp+2E8h+var_290], r8
0x180016630  mov     [rsp+2E8h+var_288], rdi
0x180016635  mov     [rsp+2E8h+var_2B0], rcx
0x18001663a  mov     rax, r12
0x18001663d  mov     [rsp+2E8h+var_2A8], rax
0x180016642  test    rdi, rdi
0x180016645  jz      short loc_180016686
0x180016647  test    rdx, rdx
0x18001664a  jz      short loc_180016686
0x18001664c  movzx   r9d, word ptr [r8]
0x180016650  test    r9w, r9w
0x180016654  jz      short loc_180016686
0x180016656  add     r8, 2
0x18001665a  mov     [rsp+2E8h+var_290], r8
0x18001665f  mov     [rcx], r9w
0x180016663  add     rcx, 2
0x180016667  mov     [rsp+2E8h+var_2B0], rcx
0x18001666c  dec     rdi
0x18001666f  mov     [rsp+2E8h+var_288], rdi
0x180016674  dec     rdx
0x180016677  mov     [rsp+2E8h+var_280], rdx
0x18001667c  inc     rax
0x18001667f  mov     [rsp+2E8h+var_2A8], rax
0x180016684  jmp     short loc_180016642
0x180016686  mov     ebx, r12d
0x180016689  test    rdi, rdi
0x18001668c  jz      short loc_1800166CE
0x18001668e  mov     [rcx], r12w
0x180016692  mov     [rsp+2E8h+var_2C0], ebx
0x180016696  mov     [rsp+2E8h+var_2BC], ebx
0x18001669a  test    ebx, ebx
0x18001669c  js      short loc_1800166E6
0x18001669e  mov     edx, 4; AccessMode
0x1800166a3  mov     rcx, rsi; FileName
0x1800166a6  call    cs:__imp__waccess
0x1800166ac  cmp     eax, 0FFFFFFFFh
0x1800166af  jnz     short loc_180016709
0x1800166b1  call    cs:__imp__errno
0x1800166b7  cmp     dword ptr [rax], 2
0x1800166ba  jnz     short loc_180016709
0x1800166bc  movzx   eax, r15w
0x1800166c0  mov     ecx, 3FFh
0x1800166c5  and     r15w, cx
0x1800166c9  jmp     loc_180016590
0x1800166ce  sub     rcx, 2
0x1800166d2  mov     [rsp+2E8h+var_2B0], rcx
0x1800166d7  dec     rax
0x1800166da  mov     [rsp+2E8h+var_2A8], rax
0x1800166df  mov     ebx, 8007007Ah
0x1800166e4  jmp     short loc_18001668E
0x1800166e6  xor     eax, eax
0x1800166e8  mov     rcx, [rsp+2E8h+var_48]
0x1800166f0  xor     rcx, rsp; StackCookie
0x1800166f3  call    __security_check_cookie
0x1800166f8  add     rsp, 2B8h
0x1800166ff  pop     r15
0x180016701  pop     r14
0x180016703  pop     r12
0x180016705  pop     rdi
0x180016706  pop     rsi
0x180016707  pop     rbx
0x180016708  retn
0x180016709  mov     rcx, r14; this
0x18001670c  call    ?InitTextContexts@CNLGSentenceSeparator@NaturalLanguage6@@AEAAJXZ; NaturalLanguage6::CNLGSentenceSeparator::InitTextContexts(void)
0x180016711  mov     [rsp+2E8h+var_2BC], eax
0x180016715  test    eax, eax
0x180016717  jns     short loc_18001673B
0x180016719  jmp     short loc_1800166E8
0x18001671b  xor     eax, eax
0x18001671d  jmp     short loc_1800166E8
0x18001671f  mov     ebx, 80070057h
0x180016724  jmp     loc_18001660D
0x180016729  test    rdi, rdi
0x18001672c  jz      loc_180016696
0x180016732  mov     [rcx], r12w
0x180016736  jmp     loc_180016696
0x18001673b  mov     [rsp+2E8h+var_2C8], r12
0x180016740  call    ??2Lexicon@NaturalLanguage6@@SAPEAX_K@Z; NaturalLanguage6::Lexicon::operator new(unsigned __int64)
0x180016745  mov     [rsp+2E8h+var_2A0], rax
0x18001674a  test    rax, rax
0x18001674d  jz      short loc_18001675C
0x18001674f  mov     rdx, rsi; unsigned __int16 *
0x180016752  mov     rcx, rax; this
0x180016755  call    ??0Lexicon@NaturalLanguage6@@QEAA@PEBG_N@Z; NaturalLanguage6::Lexicon::Lexicon(ushort const *,bool)
0x18001675a  jmp     short loc_18001675F
0x18001675c  mov     rax, r12
0x18001675f  mov     [rsp+2E8h+var_2A0], rax
0x180016764  lea     rdx, [rsp+2E8h+var_2A0]
0x180016769  lea     rcx, [rsp+2E8h+var_2C8]
0x18001676e  call    ??$_QueryInterface@PEAUIDispatch@@@?$_com_ptr_t@V?$_com_IIID@UILexicon@NaturalLanguage6@@$1?_GUID_004cd7e2_8b63_4ef9_8d46_080cdbbe47af@@3U__s_GUID@@B@@@@AEAAJAEBQEAUIDispatch@@@Z; _com_ptr_t<_com_IIID<NaturalLanguage6::ILexicon,&__s_GUID const _GUID_004cd7e2_8b63_4ef9_8d46_080cdbbe47af>>::_QueryInterface<IDispatch *>(IDispatch * const &)
0x180016773  mov     edx, 80000000h
0x180016778  lea     ecx, [rax+rdx]
0x18001677b  test    edx, ecx
0x18001677d  jnz     short loc_18001678E
0x18001677f  cmp     eax, 80004002h
0x180016784  jz      short loc_18001678E
0x180016786  mov     ecx, eax; int
0x180016788  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18001678e  mov     rdi, [r14+38h]
0x180016792  mov     rax, [rdi]
0x180016795  mov     rdx, [rsp+2E8h+var_2C8]
0x18001679a  mov     rcx, rdi
0x18001679d  mov     rax, [rax+60h]
0x1800167a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167a6  mov     ebx, eax
0x1800167a8  test    eax, eax
0x1800167aa  jns     short loc_1800167BD
0x1800167ac  lea     r8, _GUID_b6797cc0_11ae_4047_a438_26c0c916eb8d; struct _GUID *
0x1800167b3  mov     rdx, rdi; struct IUnknown *
0x1800167b6  mov     ecx, eax; int
0x1800167b8  call    ?_com_issue_errorex@@YAXJPEAUIUnknown@@AEBU_GUID@@@Z; _com_issue_errorex(long,IUnknown *,_GUID const &)
0x1800167bd  mov     [rsp+2E8h+var_2BC], ebx
0x1800167c1  lea     rcx, [rsp+2E8h+var_2C8]
0x1800167c6  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x1800167cb  mov     eax, ebx
0x1800167cd  jmp     loc_1800166E8
0x1800167d2  lea     rcx, [rsp+2E8h+var_2C8]
0x1800167d7  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x1800167dc  mov     eax, [rsp+2E8h+var_2B8]
0x1800167e0  jmp     loc_1800166E8
0x1800167e5  lea     rcx, [rsp+2E8h+var_2C8]
0x1800167ea  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x1800167ef  xor     eax, eax
0x1800167f1  jmp     loc_1800166E8
0x1800167f6  mov     [rsi], r12w
0x1800167fa  mov     eax, ebx
0x1800167fc  jmp     loc_1800166E8
0x180016801  mov     eax, dword ptr [rsp+2E8h+var_2C8]
0x180016805  jmp     loc_1800166E8
0x18001680a  mov     eax, 80004005h
0x18001680f  jmp     loc_1800166E8
```
