# NgcReqResp::Request::FromVector(std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x140020604`
- end: `0x140020821`
- name: `?FromVector@Request@NgcReqResp@@SA?AU12@AEBV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `541`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x140022790`

## callees

- `0x140009fa0`
- `0x14000a508`
- `0x14000a61c`
- `0x14000f6a0`
- `0x14000fc48`
- `0x140017380`
- `0x14001850c`
- `0x14001cf2c`
- `0x14001d19c`
- `0x14001d1f4`
- `0x14001dca4`
- `0x14001e8cc`
- `0x140020604`

## string_xrefs

- `0x1400207af`: `onecore\ds\security\ngc\inc\ngcreqresp.h`
- `0x1400207c7`: `onecore\ds\security\ngc\inc\ngcreqresp.h`
- `0x1400207df`: `onecore\ds\security\ngc\inc\ngcreqresp.h`
- `0x1400207f7`: `onecore\ds\security\ngc\inc\ngcreqresp.h`
- `0x14002080f`: `onecore\ds\security\ngc\inc\ngcreqresp.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NgcReqResp::Request::FromVector(__int64 a1, __int64 *a2)
{
  __int64 v4; // r8
  unsigned __int64 v5; // rdx
  int v6; // ecx
  int v7; // eax
  __int64 v8; // rax
  __int64 v9; // rdi
  __int64 v10; // rax
  __int64 *v11; // rbx
  _QWORD *v12; // rdi
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v17; // [rsp+20h] [rbp-59h] BYREF
  _BYTE v18[24]; // [rsp+30h] [rbp-49h] BYREF
  _BYTE v19[24]; // [rsp+48h] [rbp-31h] BYREF
  _BYTE v20[24]; // [rsp+60h] [rbp-19h] BYREF
  int v21; // [rsp+78h] [rbp-1h] BYREF
  unsigned __int16 v22; // [rsp+7Ch] [rbp+3h]
  unsigned __int8 v23; // [rsp+7Eh] [rbp+5h]
  int v24; // [rsp+80h] [rbp+7h]
  _BYTE v25[32]; // [rsp+88h] [rbp+Fh] BYREF
  _QWORD *v26; // [rsp+A8h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v17 = a1;
  NgcReqResp::Request::Request((NgcReqResp::Request *)&v21);
  v4 = *a2;
  v5 = a2[1] - *a2;
  if ( v5 < 7 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x83,
      (unsigned int)"onecore\\ds\\security\\ngc\\inc\\ngcreqresp.h",
      (const char *)0x80090005LL,
      v17);
  v6 = v21 - *(_DWORD *)v4;
  if ( v21 == *(_DWORD *)v4 )
  {
    v7 = *(unsigned __int16 *)(v4 + 4);
    v6 = v22 - v7;
    if ( v22 == v7 )
      v6 = v23 - *(unsigned __int8 *)(v4 + 6);
  }
  if ( v6 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x84,
      (unsigned int)"onecore\\ds\\security\\ngc\\inc\\ngcreqresp.h",
      (const char *)0x8009000ALL,
      v17);
  if ( v5 < 0xB )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x87,
      (unsigned int)"onecore\\ds\\security\\ngc\\inc\\ngcreqresp.h",
      (const char *)0x80090005LL,
      v17);
  v24 = *(_DWORD *)(v4 + 7);
  if ( v5 < 0xF )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x8C,
      (unsigned int)"onecore\\ds\\security\\ngc\\inc\\ngcreqresp.h",
      (const char *)0x80090005LL,
      v17);
  v8 = *(unsigned int *)(v4 + 11);
  v9 = v8 + 15;
  if ( v5 < v8 + 15 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x90,
      (unsigned int)"onecore\\ds\\security\\ngc\\inc\\ngcreqresp.h",
      (const char *)0x80090005LL,
      v17);
  std::wstring::_Assign<unsigned short>(v25, v4 + 15, v8 >> 1);
  if ( v24 == 2 )
  {
    std::vector<unsigned char>::vector<unsigned char>(v18, v9 + *a2, a2[1]);
    v10 = std::vector<unsigned char>::vector<unsigned char>(v19, v18);
    v11 = (__int64 *)NgcReqResp::DeriveSharedSecretParams::FromVector(v20, v10);
    v12 = operator new(0x18u);
    v13 = v11[2];
    v11[2] = 0;
    v14 = v11[1];
    v11[1] = 0;
    v15 = *v11;
    *v11 = 0;
    *v12 = v15;
    v12[1] = v14;
    v12[2] = v13;
    std::vector<unsigned char>::_Tidy(v20);
    v17 = 0;
    v26 = v12;
    std::unique_ptr<NgcReqResp::DeriveSharedSecretParams>::~unique_ptr<NgcReqResp::DeriveSharedSecretParams>(&v17);
    std::vector<unsigned char>::_Tidy(v18);
  }
  NgcReqResp::Request::Request(a1, &v21);
  NgcReqResp::Request::~Request((NgcReqResp::Request *)&v21);
  return a1;
}

```

## disassembly

```asm
0x140020604  mov     [rsp-8+arg_10], rbx
0x140020609  push    rbp
0x14002060a  push    rsi
0x14002060b  push    rdi
0x14002060c  lea     rbp, [rsp-47h]
0x140020611  sub     rsp, 0C0h
0x140020618  mov     rax, cs:__security_cookie
0x14002061f  xor     rax, rsp
0x140020622  mov     [rbp+57h+var_20], rax
0x140020626  mov     rbx, rdx
0x140020629  mov     rsi, rcx
0x14002062c  mov     [rbp+57h+var_B0], rcx
0x140020630  lea     rcx, [rbp+57h+var_58]; this
0x140020634  call    ??0Request@NgcReqResp@@QEAA@XZ; NgcReqResp::Request::Request(void)
0x140020639  nop
0x14002063a  mov     r8, [rbx]
0x14002063d  mov     rdx, [rbx+8]
0x140020641  sub     rdx, r8
0x140020644  mov     rcx, [rbp+5Fh]; this
0x140020648  cmp     rdx, 7
0x14002064c  jb      loc_1400207C1
0x140020652  mov     ecx, [rbp+57h+var_58]
0x140020655  sub     ecx, [r8]
0x140020658  jnz     short loc_140020672
0x14002065a  movzx   ecx, [rbp+57h+var_54]
0x14002065e  movzx   eax, word ptr [r8+4]
0x140020663  sub     ecx, eax
0x140020665  jnz     short loc_140020672
0x140020667  movzx   ecx, [rbp+57h+var_52]
0x14002066b  movzx   eax, byte ptr [r8+6]
0x140020670  sub     ecx, eax
0x140020672  test    ecx, ecx
0x140020674  setnz   al
0x140020677  mov     rcx, [rbp+5Fh]; this
0x14002067b  test    al, al
0x14002067d  jnz     loc_1400207D9
0x140020683  mov     rcx, [rbp+5Fh]; this
0x140020687  cmp     rdx, 0Bh
0x14002068b  jb      loc_1400207F1
0x140020691  mov     eax, [r8+7]
0x140020695  mov     [rbp+57h+var_50], eax
0x140020698  mov     rcx, [rbp+5Fh]; this
0x14002069c  cmp     rdx, 0Fh
0x1400206a0  jb      loc_140020809
0x1400206a6  mov     eax, [r8+0Bh]
0x1400206aa  lea     rdi, [rax+0Fh]
0x1400206ae  mov     rcx, [rbp+5Fh]; this
0x1400206b2  cmp     rdx, rdi
0x1400206b5  jb      loc_1400207A9
0x1400206bb  lea     rdx, [r8+0Fh]
0x1400206bf  sub     rax, rdx
0x1400206c2  add     r8, 0Fh
0x1400206c6  add     r8, rax
0x1400206c9  sar     r8, 1
0x1400206cc  lea     rcx, [rbp+57h+var_48]
0x1400206d0  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1400206d5  cmp     [rbp+57h+var_50], 2
0x1400206d9  jnz     loc_140020771
0x1400206df  mov     rdx, [rbx]
0x1400206e2  add     rdx, rdi
0x1400206e5  mov     r8, [rbx+8]
0x1400206e9  lea     rcx, [rbp+57h+var_A0]
0x1400206ed  call    ??$?0V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@std@@$0A@@?$vector@EV?$allocator@E@std@@@std@@QEAA@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@E@std@@@std@@@1@0AEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uchar>>>,std::allocator<uchar> const &)
0x1400206f2  nop
0x1400206f3  lea     rdx, [rbp+57h+var_A0]
0x1400206f7  lea     rcx, [rbp+57h+var_88]
0x1400206fb  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x140020700  mov     rdx, rax
0x140020703  lea     rcx, [rbp+57h+var_70]
0x140020707  call    ?FromVector@DeriveSharedSecretParams@NgcReqResp@@SA?AU12@V?$vector@EV?$allocator@E@std@@@std@@@Z; NgcReqResp::DeriveSharedSecretParams::FromVector(std::vector<uchar>)
0x14002070c  mov     rbx, rax
0x14002070f  mov     ecx, 18h; Size
0x140020714  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140020719  mov     rdi, rax
0x14002071c  mov     r8, [rbx+10h]
0x140020720  mov     qword ptr [rbx+10h], 0
0x140020728  mov     rdx, [rbx+8]
0x14002072c  mov     qword ptr [rbx+8], 0
0x140020734  mov     rcx, [rbx]
0x140020737  mov     qword ptr [rbx], 0
0x14002073e  mov     [rax], rcx
0x140020741  mov     [rax+8], rdx
0x140020745  mov     [rax+10h], r8
0x140020749  lea     rcx, [rbp+57h+var_70]
0x14002074d  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140020752  mov     [rbp+57h+var_B0], 0
0x14002075a  mov     [rbp+57h+var_28], rdi
0x14002075e  lea     rcx, [rbp+57h+var_B0]
0x140020762  call    ??1?$unique_ptr@UDeriveSharedSecretParams@NgcReqResp@@U?$default_delete@UDeriveSharedSecretParams@NgcReqResp@@@std@@@std@@QEAA@XZ; std::unique_ptr<NgcReqResp::DeriveSharedSecretParams>::~unique_ptr<NgcReqResp::DeriveSharedSecretParams>(void)
0x140020767  nop
0x140020768  lea     rcx, [rbp+57h+var_A0]
0x14002076c  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x140020771  lea     rdx, [rbp+57h+var_58]
0x140020775  mov     rcx, rsi
0x140020778  call    ??0Request@NgcReqResp@@QEAA@$$QEAU01@@Z; NgcReqResp::Request::Request(NgcReqResp::Request &&)
0x14002077d  nop
0x14002077e  lea     rcx, [rbp+57h+var_58]; this
0x140020782  call    ??1Request@NgcReqResp@@QEAA@XZ; NgcReqResp::Request::~Request(void)
0x140020787  mov     rax, rsi
0x14002078a  mov     rcx, [rbp+57h+var_20]
0x14002078e  xor     rcx, rsp; StackCookie
0x140020791  call    __security_check_cookie
0x140020796  mov     rbx, [rsp+0D0h+arg_10]
0x14002079e  add     rsp, 0C0h
0x1400207a5  pop     rdi
0x1400207a6  pop     rsi
0x1400207a7  pop     rbp
0x1400207a8  retn
0x1400207a9  mov     r9d, 80090005h; char *
0x1400207af  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\ngc\\inc\\ngcreq"...
0x1400207b6  mov     edx, 90h; void *
0x1400207bb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400207c1  mov     r9d, 80090005h; char *
0x1400207c7  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\ngc\\inc\\ngcreq"...
0x1400207ce  mov     edx, 83h; void *
0x1400207d3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400207d9  mov     r9d, 8009000Ah; char *
0x1400207df  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\ngc\\inc\\ngcreq"...
0x1400207e6  mov     edx, 84h; void *
0x1400207eb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400207f1  mov     r9d, 80090005h; char *
0x1400207f7  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\ngc\\inc\\ngcreq"...
0x1400207fe  mov     edx, 87h; void *
0x140020803  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140020809  mov     r9d, 80090005h; char *
0x14002080f  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\ngc\\inc\\ngcreq"...
0x140020816  mov     edx, 8Ch; void *
0x14002081b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
