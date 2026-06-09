# BinXmlWriter::ParseTemplateString(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>,bool)

- ea: `0x18002ee5c`
- end: `0x18002f283`
- name: `?ParseTemplateString@BinXmlWriter@@AEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@_N@Z`
- size: `1063`
- prototype: `__int64 __fastcall(BinXmlWriter *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18002eb48`

## callees

- `0x1800136d0`
- `0x1800139a0`
- `0x18001fc00`
- `0x180023548`
- `0x18002e29c`
- `0x18002ee5c`
- `0x18002f3c0`
- `0x18002f50c`
- `0x180038fb4`

## pseudocode

```c
void __fastcall BinXmlWriter::ParseTemplateString(BinXmlWriter *this, _QWORD *a2, char a3)
{
  unsigned __int64 v3; // rbx
  int v6; // r13d
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // r15
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // r10
  __int64 v13; // r11
  __int64 v14; // rsi
  __int64 v15; // r14
  __int64 v16; // rbx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rbx
  int v20; // r8d
  unsigned int v21; // edx
  __int64 v22; // rcx
  int v23; // ecx
  __int64 v24; // r11
  __int128 pExceptionObject; // [rsp+30h] [rbp-59h] BYREF
  __int64 v26; // [rsp+40h] [rbp-49h]
  int v27; // [rsp+48h] [rbp-41h]
  int v28; // [rsp+4Ch] [rbp-3Dh]
  int v29; // [rsp+50h] [rbp-39h]
  __int64 v30; // [rsp+58h] [rbp-31h] BYREF
  int v31; // [rsp+60h] [rbp-29h]
  int v32; // [rsp+64h] [rbp-25h]
  __int64 v33; // [rsp+68h] [rbp-21h] BYREF
  int v34; // [rsp+70h] [rbp-19h]
  int v35; // [rsp+74h] [rbp-15h]
  int v36; // [rsp+78h] [rbp-11h]
  char v37; // [rsp+7Ch] [rbp-Dh]
  __int16 v38; // [rsp+7Dh] [rbp-Ch]
  char v39; // [rsp+7Fh] [rbp-Ah]
  __int128 v40; // [rsp+80h] [rbp-9h]
  char v41[16]; // [rsp+90h] [rbp+7h] BYREF
  char v42; // [rsp+A0h] [rbp+17h] BYREF
  unsigned __int8 v43; // [rsp+F8h] [rbp+6Fh] BYREF
  char v44; // [rsp+100h] [rbp+77h]
  unsigned int v45; // [rsp+108h] [rbp+7Fh] BYREF

  v44 = a3;
  v3 = a2[1];
  v6 = 0;
  v7 = 0;
  v8 = 37;
  v9 = *a2;
  v10 = *a2;
  while ( 1 )
  {
    v11 = utl::_StringTraits<utl::char_traits<wchar_t>>::find(v10, v3, v7, v8);
    v14 = v11;
    if ( v11 == -1 )
      break;
    if ( v11 + 1 >= v3 || (v15 = 2 * v11, v16 = 2 * v11 + v9, *(_WORD *)(v16 + 2) == (_WORD)v8) )
    {
      v19 = 2;
    }
    else
    {
      if ( v13 && v6 > 0 )
      {
        v40 = *(_OWORD *)utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>::substr(a2, v41, v13, v11 - v13);
        BinXmlWriter::StrLenValue(this);
      }
      v17 = a2[1];
      v45 = 0;
      v43 = 0;
      v18 = utl::_FromCharsImpl<utl::from_wchars_result,unsigned int,wchar_t>(
              (unsigned int)&v42,
              (int)v16 + 2,
              (int)v9 + 2 * (int)v17,
              (unsigned int)&v45,
              10,
              (__int64)&v43);
      if ( *(_DWORD *)(v18 + 8) || v45 > (unsigned int)v43 + 0x7FFFFFFF )
      {
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_85d062a0b6fe3b8294a27f03dd74ac9f_Traceguids, 87);
        }
        v26 = 0;
        v27 = 87;
        v28 = -1;
        pExceptionObject = 0;
        v29 = 1045;
        throw (EvtException *)&pExceptionObject;
      }
      v19 = (*(_QWORD *)v18 - v15 - v9 - 2) >> 1;
      if ( (unsigned __int64)(v19 - 1) > 1 )
      {
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_85d062a0b6fe3b8294a27f03dd74ac9f_Traceguids, 87);
        }
        v26 = 0;
        v27 = 87;
        v28 = -1;
        pExceptionObject = 0;
        v29 = 1052;
        throw (EvtException *)&pExceptionObject;
      }
      v20 = v43 + (v45 ^ -v43);
      if ( v20 <= 0 )
      {
        if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_85d062a0b6fe3b8294a27f03dd74ac9f_Traceguids, 87);
        }
        v26 = 0;
        v27 = 87;
        v28 = -1;
        pExceptionObject = 0;
        v29 = 1057;
        throw (EvtException *)&pExceptionObject;
      }
      v33 = 0;
      v38 = 0;
      v21 = v20 - 1;
      v39 = 0;
      v34 = -1;
      v37 = 0;
      v35 = 8;
      v36 = (v44 != 0) + 13;
      v22 = *((_QWORD *)this + 11);
      if ( v22 )
      {
        if ( v21 >= *((_DWORD *)this + 24) )
        {
          if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_85d062a0b6fe3b8294a27f03dd74ac9f_Traceguids, 87);
          }
          v26 = 0;
          v27 = 87;
          v28 = -1;
          pExceptionObject = 0;
          v29 = 1074;
          throw (EvtException *)&pExceptionObject;
        }
        v23 = *(_DWORD *)(v22 + 4LL * v20 - 4);
        if ( (v23 & 0x80u) != 0 && *((_BYTE *)this + 104) )
        {
          if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_85d062a0b6fe3b8294a27f03dd74ac9f_Traceguids, 50);
          }
          v26 = 0;
          v27 = 50;
          v28 = -1;
          pExceptionObject = 0;
          v29 = 1085;
          throw (EvtException *)&pExceptionObject;
        }
        LODWORD(v33) = v21 | (v23 << 16);
      }
      else
      {
        LODWORD(v33) = v21 | 0x10000;
      }
      ++v6;
      BinXmlWriter::AddToken(this, (const struct BinXmlToken *)&v33);
      v8 = 37;
    }
    v24 = v19 + v14;
    v10 = v9;
    v3 = a2[1];
    v7 = v24;
  }
  if ( !v13 )
  {
    v31 = *((_DWORD *)a2 + 2);
    v32 = 1;
    v30 = v12;
    BinXmlWriter::Value(this, (const struct BinXmlVariant *)&v30);
  }
}

```

## disassembly

```asm
0x18002ee5c  mov     [rsp-8+arg_0], rbx
0x18002ee61  mov     [rsp-8+arg_10], r8b
0x18002ee66  push    rbp
0x18002ee67  push    rsi
0x18002ee68  push    rdi
0x18002ee69  push    r12
0x18002ee6b  push    r13
0x18002ee6d  push    r14
0x18002ee6f  push    r15
0x18002ee71  lea     rbp, [rsp-27h]
0x18002ee76  sub     rsp, 0B0h
0x18002ee7d  mov     r10, [rdx]
0x18002ee80  xor     r14d, r14d
0x18002ee83  mov     rbx, [rdx+8]
0x18002ee87  mov     r12, rdx
0x18002ee8a  mov     rdi, rcx
0x18002ee8d  mov     r13d, r14d
0x18002ee90  mov     r11d, r14d
0x18002ee93  mov     r8d, r14d
0x18002ee96  lea     r9d, [r14+25h]
0x18002ee9a  mov     r15, r10
0x18002ee9d  mov     rax, r10
0x18002eea0  mov     rdx, rbx
0x18002eea3  mov     rcx, rax
0x18002eea6  call    ?find@?$_StringTraits@U?$char_traits@_W@utl@@@utl@@SA_KPEB_W_K1_W@Z; utl::_StringTraits<utl::char_traits<wchar_t>>::find(wchar_t const *,unsigned __int64,unsigned __int64,wchar_t)
0x18002eeab  mov     rsi, rax
0x18002eeae  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002eeb2  jz      loc_18002F244
0x18002eeb8  lea     rcx, [rax+1]
0x18002eebc  cmp     rcx, rbx
0x18002eebf  jnb     loc_18002F01B
0x18002eec5  lea     r14, [rax+rax]
0x18002eec9  lea     rbx, [r14+r15]
0x18002eecd  cmp     [rbx+2], r9w
0x18002eed2  jz      loc_18002F015
0x18002eed8  test    r11, r11
0x18002eedb  jz      short loc_18002EF0B
0x18002eedd  test    r13d, r13d
0x18002eee0  jle     short loc_18002EF0B
0x18002eee2  mov     r9, rax
0x18002eee5  lea     rdx, [rbp+57h+var_50]
0x18002eee9  sub     r9, r11
0x18002eeec  mov     r8, r11
0x18002eeef  mov     rcx, r12
0x18002eef2  call    ?substr@?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@QEBA?AV12@_K0@Z; utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>::substr(unsigned __int64,unsigned __int64)
0x18002eef7  lea     rdx, [rbp+57h+var_60]
0x18002eefb  mov     rcx, rdi; this
0x18002eefe  movups  xmm0, xmmword ptr [rax]
0x18002ef01  movdqu  [rbp+57h+var_60], xmm0
0x18002ef06  call    ?StrLenValue@BinXmlWriter@@AEAAXV?$basic_string_view@_WU?$char_traits@_W@utl@@@utl@@@Z; BinXmlWriter::StrLenValue(utl::basic_string_view<wchar_t,utl::char_traits<wchar_t>>)
0x18002ef0b  mov     rax, [r12+8]
0x18002ef10  lea     r9, [rbp+57h+arg_18]
0x18002ef14  lea     rdx, [rbx+2]
0x18002ef18  mov     [rbp+57h+arg_18], 0
0x18002ef1f  lea     rcx, [rbp+57h+var_40]
0x18002ef23  mov     [rbp+57h+arg_8], 0
0x18002ef27  lea     r8, [r15+rax*2]
0x18002ef2b  lea     rax, [rbp+57h+arg_8]
0x18002ef2f  mov     [rsp+0E0h+var_B8], rax
0x18002ef34  mov     [rsp+0E0h+var_C0], 0Ah
0x18002ef3c  call    ??$_FromCharsImpl@Ufrom_wchars_result@utl@@I_W@utl@@YA?AUfrom_wchars_result@0@PEB_W0AEAIHPEA_N@Z; utl::_FromCharsImpl<utl::from_wchars_result,uint,wchar_t>(wchar_t const *,wchar_t const *,uint &,int,bool *)
0x18002ef41  cmp     dword ptr [rax+8], 0
0x18002ef45  jnz     loc_18002F1D8
0x18002ef4b  movzx   edx, [rbp+57h+arg_8]
0x18002ef4f  lea     ecx, [rdx+7FFFFFFFh]
0x18002ef55  cmp     [rbp+57h+arg_18], ecx
0x18002ef58  ja      loc_18002F1D8
0x18002ef5e  mov     rbx, [rax]
0x18002ef61  sub     rbx, r14
0x18002ef64  sub     rbx, r15
0x18002ef67  sub     rbx, 2
0x18002ef6b  sar     rbx, 1
0x18002ef6e  lea     rax, [rbx-1]
0x18002ef72  cmp     rax, 1
0x18002ef76  ja      loc_18002F16C
0x18002ef7c  mov     r8d, edx
0x18002ef7f  xor     r14d, r14d
0x18002ef82  neg     r8d
0x18002ef85  xor     r8d, [rbp+57h+arg_18]
0x18002ef89  add     r8d, edx
0x18002ef8c  test    r8d, r8d
0x18002ef8f  jle     loc_18002F104
0x18002ef95  xor     eax, eax
0x18002ef97  mov     [rbp+57h+var_78], r14
0x18002ef9b  mov     [rbp+57h+var_63], ax
0x18002ef9f  lea     edx, [r8-1]
0x18002efa3  mov     [rbp+57h+var_61], al
0x18002efa6  mov     al, [rbp+57h+arg_10]
0x18002efa9  neg     al
0x18002efab  mov     [rbp+57h+var_70], 0FFFFFFFFh
0x18002efb2  mov     [rbp+57h+var_64], r14b
0x18002efb6  sbb     ecx, ecx
0x18002efb8  mov     [rbp+57h+var_6C], 8
0x18002efbf  neg     ecx
0x18002efc1  add     ecx, 0Dh
0x18002efc4  mov     [rbp+57h+var_68], ecx
0x18002efc7  mov     rcx, [rdi+58h]
0x18002efcb  test    rcx, rcx
0x18002efce  jz      short loc_18002EFF4
0x18002efd0  cmp     edx, [rdi+60h]
0x18002efd3  jnb     loc_18002F09C
0x18002efd9  movsxd  rax, r8d
0x18002efdc  mov     ecx, [rcx+rax*4-4]
0x18002efe0  test    cl, cl
0x18002efe2  jns     short loc_18002EFEA
0x18002efe4  cmp     [rdi+68h], r14b
0x18002efe8  jnz     short loc_18002F034
0x18002efea  shl     ecx, 10h
0x18002efed  or      ecx, edx
0x18002efef  mov     dword ptr [rbp+57h+var_78], ecx
0x18002eff2  jmp     short loc_18002EFFB
0x18002eff4  bts     edx, 10h
0x18002eff8  mov     dword ptr [rbp+57h+var_78], edx
0x18002effb  inc     r13d
0x18002effe  lea     rdx, [rbp+57h+var_78]; struct BinXmlToken *
0x18002f002  mov     rcx, rdi; this
0x18002f005  call    ?AddToken@BinXmlWriter@@QEAAXAEBUBinXmlToken@@@Z; BinXmlWriter::AddToken(BinXmlToken const &)
0x18002f00a  mov     r10, r15
0x18002f00d  mov     r9d, 25h ; '%'
0x18002f013  jmp     short loc_18002F020
0x18002f015  mov     r10, r15
0x18002f018  xor     r14d, r14d
0x18002f01b  mov     ebx, 2
0x18002f020  lea     r11, [rbx+rsi]
0x18002f024  mov     rax, r15
0x18002f027  mov     rbx, [r12+8]
0x18002f02c  mov     r8, r11
0x18002f02f  jmp     loc_18002EEA0
0x18002f034  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f03b  lea     rax, WPP_GLOBAL_Control
0x18002f042  mov     ebx, 32h ; '2'
0x18002f047  cmp     rcx, rax
0x18002f04a  jz      short loc_18002F06E
0x18002f04c  test    byte ptr [rcx+1Ch], 2
0x18002f050  jz      short loc_18002F06E
0x18002f052  cmp     byte ptr [rcx+19h], 2
0x18002f056  jb      short loc_18002F06E
0x18002f058  mov     rcx, [rcx+10h]
0x18002f05c  lea     edx, [rbx-17h]
0x18002f05f  mov     r9d, ebx
0x18002f062  lea     r8, WPP_85d062a0b6fe3b8294a27f03dd74ac9f_Traceguids
0x18002f069  call    WPP_SF_D
0x18002f06e  xorps   xmm0, xmm0
0x18002f071  mov     [rbp+57h+var_A0], r14
0x18002f075  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18002f07c  mov     [rbp+57h+var_98], ebx
0x18002f07f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002f083  mov     [rbp+57h+var_94], 0FFFFFFFFh
0x18002f08a  movdqu  [rbp+57h+pExceptionObject], xmm0
0x18002f08f  mov     [rbp+57h+var_90], 43Dh
0x18002f096  call    _CxxThrowException_0
0x18002f09c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f0a3  lea     rax, WPP_GLOBAL_Control
0x18002f0aa  mov     ebx, 57h ; 'W'
0x18002f0af  cmp     rcx, rax
0x18002f0b2  jz      short loc_18002F0D6
0x18002f0b4  test    byte ptr [rcx+1Ch], 2
0x18002f0b8  jz      short loc_18002F0D6
0x18002f0ba  cmp     byte ptr [rcx+19h], 2
0x18002f0be  jb      short loc_18002F0D6
0x18002f0c0  mov     rcx, [rcx+10h]
0x18002f0c4  lea     edx, [rbx-3Dh]
0x18002f0c7  mov     r9d, ebx
0x18002f0ca  lea     r8, WPP_85d062a0b6fe3b8294a27f03dd74ac9f_Traceguids
0x18002f0d1  call    WPP_SF_D
0x18002f0d6  xorps   xmm0, xmm0
0x18002f0d9  mov     [rbp+57h+var_A0], r14
0x18002f0dd  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18002f0e4  mov     [rbp+57h+var_98], ebx
0x18002f0e7  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002f0eb  mov     [rbp+57h+var_94], 0FFFFFFFFh
0x18002f0f2  movdqu  [rbp+57h+pExceptionObject], xmm0
0x18002f0f7  mov     [rbp+57h+var_90], 432h
0x18002f0fe  call    _CxxThrowException_0
0x18002f104  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f10b  lea     rax, WPP_GLOBAL_Control
0x18002f112  mov     ebx, 57h ; 'W'
0x18002f117  cmp     rcx, rax
0x18002f11a  jz      short loc_18002F13E
0x18002f11c  test    byte ptr [rcx+1Ch], 2
0x18002f120  jz      short loc_18002F13E
0x18002f122  cmp     byte ptr [rcx+19h], 2
0x18002f126  jb      short loc_18002F13E
0x18002f128  mov     rcx, [rcx+10h]
0x18002f12c  lea     edx, [rbx-3Eh]
0x18002f12f  mov     r9d, ebx
0x18002f132  lea     r8, WPP_85d062a0b6fe3b8294a27f03dd74ac9f_Traceguids
0x18002f139  call    WPP_SF_D
0x18002f13e  xorps   xmm0, xmm0
0x18002f141  mov     [rbp+57h+var_A0], r14
0x18002f145  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18002f14c  mov     [rbp+57h+var_98], ebx
0x18002f14f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002f153  mov     [rbp+57h+var_94], 0FFFFFFFFh
0x18002f15a  movdqu  [rbp+57h+pExceptionObject], xmm0
0x18002f15f  mov     [rbp+57h+var_90], 421h
0x18002f166  call    _CxxThrowException_0
0x18002f16c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f173  lea     rax, WPP_GLOBAL_Control
0x18002f17a  mov     ebx, 57h ; 'W'
0x18002f17f  cmp     rcx, rax
0x18002f182  jz      short loc_18002F1A6
0x18002f184  test    byte ptr [rcx+1Ch], 2
0x18002f188  jz      short loc_18002F1A6
0x18002f18a  cmp     byte ptr [rcx+19h], 2
0x18002f18e  jb      short loc_18002F1A6
0x18002f190  mov     rcx, [rcx+10h]
0x18002f194  lea     edx, [rbx-3Fh]
0x18002f197  mov     r9d, ebx
0x18002f19a  lea     r8, WPP_85d062a0b6fe3b8294a27f03dd74ac9f_Traceguids
0x18002f1a1  call    WPP_SF_D
0x18002f1a6  xorps   xmm0, xmm0
0x18002f1a9  mov     [rbp+57h+var_A0], 0
0x18002f1b1  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18002f1b8  mov     [rbp+57h+var_98], ebx
0x18002f1bb  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002f1bf  mov     [rbp+57h+var_94], 0FFFFFFFFh
0x18002f1c6  movdqu  [rbp+57h+pExceptionObject], xmm0
0x18002f1cb  mov     [rbp+57h+var_90], 41Ch
0x18002f1d2  call    _CxxThrowException_0
0x18002f1d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f1df  lea     rax, WPP_GLOBAL_Control
0x18002f1e6  mov     ebx, 57h ; 'W'
0x18002f1eb  cmp     rcx, rax
0x18002f1ee  jz      short loc_18002F212
0x18002f1f0  test    byte ptr [rcx+1Ch], 2
0x18002f1f4  jz      short loc_18002F212
0x18002f1f6  cmp     byte ptr [rcx+19h], 2
0x18002f1fa  jb      short loc_18002F212
0x18002f1fc  mov     rcx, [rcx+10h]
0x18002f200  lea     edx, [rbx-40h]
0x18002f203  mov     r9d, ebx
0x18002f206  lea     r8, WPP_85d062a0b6fe3b8294a27f03dd74ac9f_Traceguids
0x18002f20d  call    WPP_SF_D
0x18002f212  xorps   xmm0, xmm0
0x18002f215  mov     [rbp+57h+var_A0], 0
0x18002f21d  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18002f224  mov     [rbp+57h+var_98], ebx
0x18002f227  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18002f22b  mov     [rbp+57h+var_94], 0FFFFFFFFh
0x18002f232  movdqu  [rbp+57h+pExceptionObject], xmm0
0x18002f237  mov     [rbp+57h+var_90], 415h
0x18002f23e  call    _CxxThrowException_0
0x18002f244  test    r11, r11
0x18002f247  jnz     short loc_18002F268
0x18002f249  mov     eax, [r12+8]
0x18002f24e  lea     rdx, [rbp+57h+var_88]; struct BinXmlVariant *
0x18002f252  mov     rcx, rdi; this
0x18002f255  mov     [rbp+57h+var_80], eax
0x18002f258  mov     [rbp+57h+var_7C], 1
0x18002f25f  mov     [rbp+57h+var_88], r10
0x18002f263  call    ?Value@BinXmlWriter@@QEAAXAEBUBinXmlVariant@@@Z; BinXmlWriter::Value(BinXmlVariant const &)
0x18002f268  mov     rbx, [rsp+0E0h+arg_0]
0x18002f270  add     rsp, 0B0h
0x18002f277  pop     r15
0x18002f279  pop     r14
0x18002f27b  pop     r13
0x18002f27d  pop     r12
0x18002f27f  pop     rdi
0x18002f280  pop     rsi
0x18002f281  pop     rbp
0x18002f282  retn
```
