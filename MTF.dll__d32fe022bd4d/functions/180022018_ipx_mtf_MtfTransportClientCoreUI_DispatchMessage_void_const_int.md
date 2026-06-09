# ipx::mtf::MtfTransportClientCoreUI::_DispatchMessage(void const *,int)

- ea: `0x180022018`
- end: `0x180022296`
- name: `?_DispatchMessage@MtfTransportClientCoreUI@mtf@ipx@@IEAAJPEBXH@Z`
- size: `638`
- prototype: `__int64 __fastcall(ipx::mtf::MtfTransportClientCoreUI *__hidden this, const void *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180022500`

## callees

- `0x180006074`
- `0x180022018`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180022122`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180022122`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022041`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022041`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180022067`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002207c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180022067`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002207c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ipx::mtf::MtfTransportClientCoreUI::_DispatchMessage(
        ipx::mtf::MtfTransportClientCoreUI *this,
        _DWORD *a2,
        unsigned int a3)
{
  RTL_SRWLOCK *v6; // rsi
  HRESULT v8; // eax
  unsigned int v9; // esi
  LPSTREAM v10; // rcx
  int v11; // eax
  LPSTREAM v12; // rcx
  int v13; // eax
  LPSTREAM v14; // rcx
  LPSTREAM v15; // rcx
  int v16; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  LPSTREAM ppstm; // [rsp+50h] [rbp+20h] BYREF
  ipx::mtf::MtfTransportClientCoreUI *v19; // [rsp+68h] [rbp+38h]

  v6 = (RTL_SRWLOCK *)((char *)this + 288);
  AcquireSRWLockExclusive((PSRWLOCK)this + 36);
  if ( (*(unsigned int (__fastcall **)(ipx::mtf::MtfTransportClientCoreUI *))(*(_QWORD *)this + 8LL))(this) == 1 )
  {
    _InterlockedDecrement((volatile signed __int32 *)this + 6);
    if ( v6 )
      ReleaseSRWLockExclusive(v6);
    return 0;
  }
  if ( v6 )
    ReleaseSRWLockExclusive(v6);
  v19 = this;
  if ( a3 < 0x18 )
  {
    (*(void (__fastcall **)(ipx::mtf::MtfTransportClientCoreUI *))(*(_QWORD *)this + 16LL))(this);
    return 0;
  }
  if ( a3 != a2[4] )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x254,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\transportcoreui.cpp",
      (const char *)0x80004005LL,
      v16);
    (*(void (__fastcall **)(ipx::mtf::MtfTransportClientCoreUI *))(*(_QWORD *)this + 16LL))(this);
    return 2147500037LL;
  }
  if ( !*((_BYTE *)a2 + 21) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x257,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\transportcoreui.cpp",
      (const char *)0x80004005LL,
      v16);
    (*(void (__fastcall **)(ipx::mtf::MtfTransportClientCoreUI *))(*(_QWORD *)this + 16LL))(this);
    return 2147500037LL;
  }
  if ( *((_BYTE *)a2 + 20) == 4 )
  {
    ppstm = 0;
    v8 = CreateStreamOnHGlobal(0, 1, &ppstm);
    v9 = v8;
    if ( v8 >= 0 )
    {
      v11 = (*(__int64 (__fastcall **)(LPSTREAM, char *, _QWORD, _QWORD))(*(_QWORD *)ppstm + 32LL))(
              ppstm,
              (char *)a2 + 24,
              a3 - 24,
              0);
      v9 = v11;
      if ( v11 >= 0 )
      {
        v13 = (*(__int64 (__fastcall **)(LPSTREAM, _QWORD, _QWORD, _QWORD))(*(_QWORD *)ppstm + 40LL))(ppstm, 0, 0, 0);
        v9 = v13;
        if ( v13 >= 0 )
        {
          v9 = (*(__int64 (__fastcall **)(ipx::mtf::MtfTransportClientCoreUI *, _DWORD *, _QWORD, LPSTREAM))(*(_QWORD *)this + 24LL))(
                 this,
                 a2,
                 (unsigned int)a2[3],
                 ppstm);
          v15 = ppstm;
          ppstm = 0;
          if ( v15 )
            (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v15 + 16LL))(v15);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x263,
            (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\transportcoreui.cpp",
            (const char *)(unsigned int)v13,
            v16);
          v14 = ppstm;
          ppstm = 0;
          if ( v14 )
            (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v14 + 16LL))(v14);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x260,
          (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\transportcoreui.cpp",
          (const char *)(unsigned int)v11,
          v16);
        v12 = ppstm;
        ppstm = 0;
        if ( v12 )
          (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v12 + 16LL))(v12);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x25C,
        (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\transportcoreui.cpp",
        (const char *)(unsigned int)v8,
        v16);
      v10 = ppstm;
      ppstm = 0;
      if ( v10 )
        (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)v10 + 16LL))(v10);
    }
    (*(void (__fastcall **)(ipx::mtf::MtfTransportClientCoreUI *))(*(_QWORD *)this + 16LL))(this);
    return v9;
  }
  else
  {
    (*(void (__fastcall **)(ipx::mtf::MtfTransportClientCoreUI *))(*(_QWORD *)this + 16LL))(this);
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x180022018  mov     [rsp-18h+arg_8], rsi
0x18002201d  mov     [rsp-18h+arg_10], rdi
0x180022022  push    rbp
0x180022023  push    r14
0x180022025  push    r15
0x180022027  mov     rbp, rsp
0x18002202a  sub     rsp, 30h
0x18002202e  mov     r15d, r8d
0x180022031  mov     r14, rdx
0x180022034  mov     rdi, rcx
0x180022037  lea     rsi, [rcx+120h]
0x18002203e  mov     rcx, rsi; SRWLock
0x180022041  call    cs:__imp_AcquireSRWLockExclusive
0x180022047  mov     rax, [rdi]
0x18002204a  mov     rcx, rdi
0x18002204d  mov     rax, [rax+8]
0x180022051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022056  cmp     eax, 1
0x180022059  jnz     short loc_180022074
0x18002205b  lock dec dword ptr [rdi+18h]
0x18002205f  test    rsi, rsi
0x180022062  jz      short loc_18002206D
0x180022064  mov     rcx, rsi; SRWLock
0x180022067  call    cs:__imp_ReleaseSRWLockExclusive
0x18002206d  xor     eax, eax
0x18002206f  jmp     loc_180022282
0x180022074  test    rsi, rsi
0x180022077  jz      short loc_180022082
0x180022079  mov     rcx, rsi; SRWLock
0x18002207c  call    cs:__imp_ReleaseSRWLockExclusive
0x180022082  mov     [rbp+arg_18], rdi
0x180022086  cmp     r15d, 18h
0x18002208a  jnb     short loc_18002209D
0x18002208c  mov     rax, [rdi]
0x18002208f  mov     rcx, rdi
0x180022092  mov     rax, [rax+10h]
0x180022096  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002209b  jmp     short loc_18002206D
0x18002209d  cmp     r15d, [r14+10h]
0x1800220a1  jz      short loc_1800220D8
0x1800220a3  mov     rcx, [rbp+18h]; this
0x1800220a7  mov     r9d, 80004005h; char *
0x1800220ad  lea     r8, aMincoreTextinp_2; "mincore\\textinput\\dev\\mtf\\internal"...
0x1800220b4  mov     edx, 254h; void *
0x1800220b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800220be  nop
0x1800220bf  mov     rcx, [rdi]
0x1800220c2  mov     rax, [rcx+10h]
0x1800220c6  mov     rcx, rdi
0x1800220c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800220ce  mov     eax, 80004005h
0x1800220d3  jmp     loc_180022282
0x1800220d8  cmp     byte ptr [r14+15h], 0
0x1800220dd  jnz     short loc_180022104
0x1800220df  mov     rcx, [rbp+18h]; this
0x1800220e3  mov     r9d, 80004005h; char *
0x1800220e9  lea     r8, aMincoreTextinp_2; "mincore\\textinput\\dev\\mtf\\internal"...
0x1800220f0  mov     edx, 257h; void *
0x1800220f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800220fa  nop
0x1800220fb  mov     rax, [rdi]
0x1800220fe  mov     rax, [rax+10h]
0x180022102  jmp     short loc_1800220C6
0x180022104  cmp     byte ptr [r14+14h], 4
0x180022109  jnz     loc_18002226E
0x18002210f  mov     [rbp+ppstm], 0
0x180022117  lea     r8, [rbp+ppstm]; ppstm
0x18002211b  mov     edx, 1; fDeleteOnRelease
0x180022120  xor     ecx, ecx; hGlobal
0x180022122  call    cs:__imp_CreateStreamOnHGlobal
0x180022128  mov     esi, eax
0x18002212a  test    eax, eax
0x18002212c  jns     short loc_18002217B
0x18002212e  mov     rcx, [rbp+18h]; this
0x180022132  mov     r9d, eax; char *
0x180022135  lea     r8, aMincoreTextinp_2; "mincore\\textinput\\dev\\mtf\\internal"...
0x18002213c  mov     edx, 25Ch; void *
0x180022141  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022146  nop
0x180022147  mov     rcx, [rbp+ppstm]
0x18002214b  mov     [rbp+ppstm], 0
0x180022153  test    rcx, rcx
0x180022156  jz      short loc_180022165
0x180022158  mov     rax, [rcx]
0x18002215b  mov     rax, [rax+10h]
0x18002215f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022164  nop
0x180022165  mov     rax, [rdi]
0x180022168  mov     rcx, rdi
0x18002216b  mov     rax, [rax+10h]
0x18002216f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022174  mov     eax, esi
0x180022176  jmp     loc_180022282
0x18002217b  mov     rcx, [rbp+ppstm]
0x18002217f  mov     rax, [rcx]
0x180022182  lea     r8d, [r15-18h]
0x180022186  lea     rdx, [r14+18h]
0x18002218a  xor     r9d, r9d
0x18002218d  mov     rax, [rax+20h]
0x180022191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022196  mov     esi, eax
0x180022198  test    eax, eax
0x18002219a  jns     short loc_1800221D5
0x18002219c  mov     rcx, [rbp+18h]; this
0x1800221a0  mov     r9d, eax; char *
0x1800221a3  lea     r8, aMincoreTextinp_2; "mincore\\textinput\\dev\\mtf\\internal"...
0x1800221aa  mov     edx, 260h; void *
0x1800221af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800221b4  nop
0x1800221b5  mov     rcx, [rbp+ppstm]
0x1800221b9  mov     [rbp+ppstm], 0
0x1800221c1  test    rcx, rcx
0x1800221c4  jz      short loc_1800221D3
0x1800221c6  mov     rax, [rcx]
0x1800221c9  mov     rax, [rax+10h]
0x1800221cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800221d2  nop
0x1800221d3  jmp     short loc_180022165
0x1800221d5  mov     rcx, [rbp+ppstm]
0x1800221d9  mov     rax, [rcx]
0x1800221dc  xor     r9d, r9d
0x1800221df  xor     r8d, r8d
0x1800221e2  xor     edx, edx
0x1800221e4  mov     rax, [rax+28h]
0x1800221e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800221ed  mov     esi, eax
0x1800221ef  test    eax, eax
0x1800221f1  jns     short loc_18002222F
0x1800221f3  mov     rcx, [rbp+18h]; this
0x1800221f7  mov     r9d, eax; char *
0x1800221fa  lea     r8, aMincoreTextinp_2; "mincore\\textinput\\dev\\mtf\\internal"...
0x180022201  mov     edx, 263h; void *
0x180022206  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002220b  nop
0x18002220c  mov     rcx, [rbp+ppstm]
0x180022210  mov     [rbp+ppstm], 0
0x180022218  test    rcx, rcx
0x18002221b  jz      short loc_18002222A
0x18002221d  mov     rax, [rcx]
0x180022220  mov     rax, [rax+10h]
0x180022224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022229  nop
0x18002222a  jmp     loc_180022165
0x18002222f  mov     rax, [rdi]
0x180022232  mov     r9, [rbp+ppstm]
0x180022236  mov     r8d, [r14+0Ch]
0x18002223a  mov     rdx, r14
0x18002223d  mov     rcx, rdi
0x180022240  mov     rax, [rax+18h]
0x180022244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022249  mov     esi, eax
0x18002224b  mov     rcx, [rbp+ppstm]
0x18002224f  mov     [rbp+ppstm], 0
0x180022257  test    rcx, rcx
0x18002225a  jz      short loc_180022269
0x18002225c  mov     rdx, [rcx]
0x18002225f  mov     rax, [rdx+10h]
0x180022263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022268  nop
0x180022269  jmp     loc_180022165
0x18002226e  mov     rax, [rdi]
0x180022271  mov     rcx, rdi
0x180022274  mov     rax, [rax+10h]
0x180022278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002227d  mov     eax, 8000FFFFh
0x180022282  mov     rsi, [rsp+30h+arg_8]
0x180022287  mov     rdi, [rsp+30h+arg_10]
0x18002228c  add     rsp, 30h
0x180022290  pop     r15
0x180022292  pop     r14
0x180022294  pop     rbp
0x180022295  retn
```
