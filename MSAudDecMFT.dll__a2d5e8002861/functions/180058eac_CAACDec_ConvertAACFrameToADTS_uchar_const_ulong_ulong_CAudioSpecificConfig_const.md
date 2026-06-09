# CAACDec::ConvertAACFrameToADTS(uchar const *,ulong,ulong,CAudioSpecificConfig const *)

- ea: `0x180058eac`
- end: `0x180059274`
- name: `?ConvertAACFrameToADTS@CAACDec@@IEAAJPEBEKKPEBUCAudioSpecificConfig@@@Z`
- size: `968`
- prototype: `__int64 __fastcall(CAACDec *this, const unsigned __int8 *, unsigned int, int, const struct CAudioSpecificConfig *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180002550`

## callees

- `0x180003af0`
- `0x18003daf0`
- `0x180058eac`
- `0x180096060`
- `0x1800960c0`

## import_xrefs

- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180059182`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x180059182`

## string_xrefs

- `0x1800591bb`: `CAACDec::ConvertAACFrameToADTS() dwChannelConfiguration = %d, m_TimePerFrame = %12I64d, updated m_hnsOutputSampleDuration = %12I64d`

## pseudocode

```c
__int64 __fastcall CAACDec::ConvertAACFrameToADTS(
        CAACDec *this,
        const unsigned __int8 *a2,
        unsigned int a3,
        int a4,
        const struct CAudioSpecificConfig *a5)
{
  rsize_t v6; // rsi
  const unsigned __int8 *v7; // rbp
  int v8; // edi
  char v9; // r14
  int v10; // eax
  int *v11; // rax
  int v12; // r12d
  _BYTE *v13; // rcx
  unsigned int v14; // ebp
  int v15; // edx
  __int64 v16; // r10
  unsigned int v17; // r11d
  __int64 v18; // rax
  char v19; // r8
  int v20; // esi
  int v21; // r8d
  bool v22; // zf
  int v23; // eax
  TraceLoggingHelperBase *v24; // rdi
  _BYTE Buf1[88]; // [rsp+40h] [rbp-58h] BYREF
  __int64 v27; // [rsp+A0h] [rbp+8h]
  char v29; // [rsp+B0h] [rbp+18h]

  v6 = a3;
  v7 = a2;
  TraceLoggingHelperBase::TraceVA(
    (CAACDec *)((char *)this + 246488),
    5u,
    "CAACDec::ConvertAACFrameToADTS",
    0x23Au,
    "CAACDec::ConvertAACFrameToADTS(dwInBufferSize=%d, pInBuffer=0x%p, dwBitOffset=%d) Enter",
    a3,
    a2,
    a4);
  if ( (unsigned int)(v6 + 7) > 0xC000 || !(_DWORD)v6 )
  {
    v20 = -2147467259;
LABEL_30:
    v24 = (CAACDec *)((char *)this + 246488);
    goto LABEL_31;
  }
  v8 = 1;
  v9 = 1;
  v10 = *(_DWORD *)a5;
  if ( *(_DWORD *)a5 == 5 || v10 == 29 || (v29 = 1, v10 == 4) )
    v29 = 0;
  if ( (unsigned int)(v10 - 1) <= 3 )
    v9 = *(_BYTE *)a5 - 1;
  v11 = (int *)*((_QWORD *)this + 30748);
  *((_DWORD *)this + 28) = ((_WORD)v6 + 7) & 0x1FFF;
  if ( v11 )
  {
    v12 = *v11;
  }
  else
  {
    v13 = (_BYTE *)*((_QWORD *)this + 30750);
    v12 = 0;
    if ( v13 )
    {
      v14 = 0;
      Buf1[0] = v13[3];
      Buf1[1] = v13[16];
      Buf1[2] = v13[17];
      Buf1[3] = v13[4];
      Buf1[4] = v13[48];
      Buf1[5] = v13[49];
      Buf1[6] = v13[5];
      Buf1[7] = v13[80];
      Buf1[8] = v13[81];
      Buf1[9] = v13[6];
      while ( v14 < 8 )
      {
        v27 = 11LL * v14;
        if ( !memcmp_0(Buf1, (char *)qword_1800B7390 + v27 + 1, 0xAu) )
        {
          v12 = *((unsigned __int8 *)qword_1800B7390 + v27);
          break;
        }
        ++v14;
      }
      v7 = a2;
    }
  }
  *((_BYTE *)this + 132) = -1;
  *((_BYTE *)this + 133) = (8 * v29) | 0xF1;
  *((_BYTE *)this + 134) = ((v12 & 4) != 0) | (4 * ((16 * v9) | *((_BYTE *)a5 + 4) & 0xF));
  v15 = *((int *)this + 28) >> 3;
  *((_BYTE *)this + 135) = ((_BYTE)v12 << 6) | (*((int *)this + 28) >> 11);
  *((_BYTE *)this + 136) = v15;
  *((_BYTE *)this + 137) = 32 * *((_BYTE *)this + 112);
  *((_BYTE *)this + 138) = 0;
  if ( a4 )
  {
    v16 = (unsigned int)(v6 - 1);
    if ( (_DWORD)v6 != 1 )
    {
      v17 = 0;
      do
      {
        v18 = v17 + 7;
        v19 = v7[v17++] << a4;
        *((_BYTE *)this + v18 + 132) = (v7[v17] >> (8 - a4)) | v19;
      }
      while ( v17 < (unsigned int)v16 );
    }
    *((_BYTE *)this + (unsigned int)(v6 + 6) + 132) = v7[v16] << a4;
  }
  else
  {
    memcpy_s_0((char *)this + 139, 0xBFF9u, v7, v6);
  }
  v20 = (*(__int64 (__fastcall **)(CAACDec *, _QWORD))(*(_QWORD *)this + 24LL))(this, *((unsigned int *)this + 28));
  if ( v20 < 0 )
    goto LABEL_30;
  ++*((_DWORD *)this + 61503);
  ++*((_DWORD *)this + 61504);
  if ( *(_DWORD *)a5 != 5 && *(_DWORD *)a5 != 29 )
    v8 = 0;
  v21 = *((_DWORD *)this + 61475);
  *((_DWORD *)this + 61636) = v8;
  v22 = *(_DWORD *)a5 == 29;
  *((_DWORD *)this + 61502) = v12;
  *((_DWORD *)this + 29) = 1024;
  *((_DWORD *)this + 61637) = v22;
  *((_DWORD *)this + 61487) = v21;
  v23 = MulDiv(1024, 10000000, v21);
  v24 = (CAACDec *)((char *)this + 246488);
  *((_QWORD *)this + 4) = v23;
  *((_QWORD *)this + 8) += v23;
  TraceLoggingHelperBase::TraceVA(
    (CAACDec *)((char *)this + 246488),
    5u,
    "CAACDec::ConvertAACFrameToADTS",
    0x2B1u,
    "CAACDec::ConvertAACFrameToADTS() dwChannelConfiguration = %d, m_TimePerFrame = %12I64d, updated m_hnsOutputSampleDuration = %12I64d",
    v12,
    v23,
    *((_QWORD *)this + 8));
LABEL_31:
  TraceLoggingHelperBase::TraceVA(
    v24,
    5u,
    "CAACDec::ConvertAACFrameToADTS",
    0x2B5u,
    "CAACDec::ConvertAACFrameToADTS() m_ulOutputFrameCnt=%d, m_ulBadFrameCnt=%d",
    *((_DWORD *)this + 61504),
    *((_DWORD *)this + 61505));
  if ( v20 )
    TraceLoggingHelperBase::TraceVA(
      v24,
      2u,
      "CAACDec::ConvertAACFrameToADTS",
      0x2B6u,
      "Error %08X returned: File: %s, Line: %d",
      v20,
      "avcore\\codecdsp\\audio\\aacdec\\current\\mft\\aacdecxheaac.cpp",
      694);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x180058eac  mov     rax, rsp
0x180058eaf  mov     [rax+20h], r9d
0x180058eb3  mov     [rax+10h], rdx
0x180058eb7  push    rbx
0x180058eb8  push    rbp
0x180058eb9  push    rsi
0x180058eba  push    rdi
0x180058ebb  push    r12
0x180058ebd  push    r13
0x180058ebf  push    r14
0x180058ec1  push    r15
0x180058ec3  sub     rsp, 58h
0x180058ec7  mov     [rax-60h], r9d
0x180058ecb  mov     rbx, rcx
0x180058ece  mov     [rax-68h], rdx
0x180058ed2  lea     rcx, aCaacdecConvert_0; "CAACDec::ConvertAACFrameToADTS(dwInBuff"...
0x180058ed9  mov     esi, r8d
0x180058edc  mov     rbp, rdx
0x180058edf  mov     [rax-70h], esi
0x180058ee2  lea     r8, aCaacdecConvert; "CAACDec::ConvertAACFrameToADTS"
0x180058ee9  mov     [rax-78h], rcx
0x180058eed  mov     r9d, 23Ah; unsigned int
0x180058ef3  lea     rcx, [rbx+3C2D8h]; this
0x180058efa  mov     edx, 5; unsigned __int8
0x180058eff  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x180058f04  lea     ecx, [rsi+7]
0x180058f07  cmp     ecx, 0C000h
0x180058f0d  ja      loc_1800591DB
0x180058f13  test    esi, esi
0x180058f15  jz      loc_1800591DB
0x180058f1b  mov     r15, [rsp+98h+arg_20]
0x180058f23  mov     edi, 1
0x180058f28  mov     r14b, dil
0x180058f2b  mov     eax, [r15]
0x180058f2e  cmp     eax, 5
0x180058f31  jz      short loc_180058F45
0x180058f33  cmp     eax, 1Dh
0x180058f36  jz      short loc_180058F45
0x180058f38  mov     [rsp+98h+arg_10], dil
0x180058f40  cmp     eax, 4
0x180058f43  jnz     short loc_180058F4E
0x180058f45  xor     dl, dl
0x180058f47  mov     [rsp+98h+arg_10], dl
0x180058f4e  dec     eax
0x180058f50  cmp     eax, 3
0x180058f53  ja      short loc_180058F5B
0x180058f55  mov     r14b, [r15]
0x180058f58  sub     r14b, dil
0x180058f5b  mov     rax, [rbx+3C0E0h]
0x180058f62  and     ecx, 1FFFh
0x180058f68  mov     [rbx+70h], ecx
0x180058f6b  mov     r13d, 8
0x180058f71  test    rax, rax
0x180058f74  jz      short loc_180058F7E
0x180058f76  mov     r12d, [rax]
0x180058f79  jmp     loc_18005902E
0x180058f7e  mov     rcx, [rbx+3C0F0h]
0x180058f85  xor     r12d, r12d
0x180058f88  test    rcx, rcx
0x180058f8b  jz      loc_18005902E
0x180058f91  mov     al, [rcx+3]
0x180058f94  xor     ebp, ebp
0x180058f96  mov     [rsp+98h+Buf1], al
0x180058f9a  mov     al, [rcx+10h]
0x180058f9d  mov     [rsp+98h+var_57], al
0x180058fa1  mov     al, [rcx+11h]
0x180058fa4  mov     [rsp+98h+var_56], al
0x180058fa8  mov     al, [rcx+4]
0x180058fab  mov     [rsp+98h+var_55], al
0x180058faf  mov     al, [rcx+30h]
0x180058fb2  mov     [rsp+98h+var_54], al
0x180058fb6  mov     al, [rcx+31h]
0x180058fb9  mov     [rsp+98h+var_53], al
0x180058fbd  mov     al, [rcx+5]
0x180058fc0  mov     [rsp+98h+var_52], al
0x180058fc4  mov     al, [rcx+50h]
0x180058fc7  mov     [rsp+98h+var_51], al
0x180058fcb  mov     al, [rcx+51h]
0x180058fce  mov     [rsp+98h+var_50], al
0x180058fd2  mov     al, [rcx+6]
0x180058fd5  lea     rcx, qword_1800B7390
0x180058fdc  mov     [rsp+98h+var_4F], al
0x180058fe0  cmp     ebp, r13d
0x180058fe3  jnb     short loc_180059026
0x180058fe5  mov     eax, ebp
0x180058fe7  mov     r8d, 0Ah; Size
0x180058fed  imul    rax, 0Bh
0x180058ff1  mov     [rsp+98h+arg_0], rax
0x180058ff9  lea     rdx, [rax+1]
0x180058ffd  add     rdx, rcx; Buf2
0x180059000  lea     rcx, [rsp+98h+Buf1]; Buf1
0x180059005  call    memcmp_0
0x18005900a  lea     rcx, qword_1800B7390
0x180059011  test    eax, eax
0x180059013  jz      short loc_180059019
0x180059015  add     ebp, edi
0x180059017  jmp     short loc_180058FE0
0x180059019  mov     rax, [rsp+98h+arg_0]
0x180059021  movzx   r12d, byte ptr [rax+rcx]
0x180059026  mov     rbp, [rsp+98h+arg_8]
0x18005902e  mov     al, [rsp+98h+arg_10]
0x180059035  shl     al, 3
0x180059038  or      al, 0F1h
0x18005903a  mov     byte ptr [rbx+84h], 0FFh
0x180059041  mov     [rbx+85h], al
0x180059047  mov     al, r12b
0x18005904a  mov     cl, [r15+4]
0x18005904e  and     cl, 0Fh
0x180059051  shr     al, 2
0x180059054  and     al, dil
0x180059057  shl     r14b, 4
0x18005905b  or      cl, r14b
0x18005905e  mov     r14d, [rsp+98h+arg_18]
0x180059066  shl     cl, 2
0x180059069  or      cl, al
0x18005906b  mov     al, r12b
0x18005906e  mov     [rbx+86h], cl
0x180059074  mov     edx, [rbx+70h]
0x180059077  mov     ecx, edx
0x180059079  shl     al, 6
0x18005907c  sar     ecx, 0Bh
0x18005907f  or      cl, al
0x180059081  sar     edx, 3
0x180059084  mov     [rbx+87h], cl
0x18005908a  mov     [rbx+88h], dl
0x180059090  mov     al, [rbx+70h]
0x180059093  shl     al, 5
0x180059096  mov     [rbx+89h], al
0x18005909c  mov     byte ptr [rbx+8Ah], 0
0x1800590a3  test    r14d, r14d
0x1800590a6  jnz     short loc_1800590C1
0x1800590a8  mov     r9, rsi; SourceSize
0x1800590ab  lea     rcx, [rbx+8Bh]; Destination
0x1800590b2  mov     r8, rbp; Source
0x1800590b5  mov     edx, 0BFF9h; DestinationSize
0x1800590ba  call    memcpy_s_0
0x1800590bf  jmp     short loc_180059114
0x1800590c1  lea     r10d, [rsi-1]
0x1800590c5  test    r10d, r10d
0x1800590c8  jz      short loc_180059101
0x1800590ca  xor     r11d, r11d
0x1800590cd  sub     r13b, r14b
0x1800590d0  mov     eax, r11d
0x1800590d3  lea     r9d, [r11+1]
0x1800590d7  mov     dl, [r9+rbp]
0x1800590db  mov     ecx, r14d
0x1800590de  mov     r8b, [rax+rbp]
0x1800590e2  lea     eax, [r11+7]
0x1800590e6  shl     r8b, cl
0x1800590e9  mov     r11d, r9d
0x1800590ec  mov     cl, r13b
0x1800590ef  shr     dl, cl
0x1800590f1  or      r8b, dl
0x1800590f4  mov     [rax+rbx+84h], r8b
0x1800590fc  cmp     r9d, r10d
0x1800590ff  jb      short loc_1800590D0
0x180059101  mov     dl, [r10+rbp]
0x180059105  lea     eax, [rsi+6]
0x180059108  mov     ecx, r14d
0x18005910b  shl     dl, cl
0x18005910d  mov     [rax+rbx+84h], dl
0x180059114  mov     rax, [rbx]
0x180059117  mov     rcx, rbx
0x18005911a  mov     edx, [rbx+70h]
0x18005911d  mov     rax, [rax+18h]
0x180059121  call    cs:__guard_dispatch_icall_fptr
0x180059127  mov     esi, eax
0x180059129  test    eax, eax
0x18005912b  js      loc_1800591E0
0x180059131  add     [rbx+3C0FCh], edi
0x180059137  add     [rbx+3C100h], edi
0x18005913d  cmp     dword ptr [r15], 5
0x180059141  jz      short loc_18005914B
0x180059143  cmp     dword ptr [r15], 1Dh
0x180059147  jz      short loc_18005914B
0x180059149  xor     edi, edi
0x18005914b  mov     r8d, [rbx+3C08Ch]; nDenominator
0x180059152  xor     eax, eax
0x180059154  mov     [rbx+3C310h], edi
0x18005915a  mov     ecx, 400h; nNumber
0x18005915f  cmp     dword ptr [r15], 1Dh
0x180059163  mov     edx, 989680h; nNumerator
0x180059168  mov     [rbx+3C0F8h], r12d
0x18005916f  setz    al
0x180059172  mov     [rbx+74h], ecx
0x180059175  mov     [rbx+3C314h], eax
0x18005917b  mov     [rbx+3C0BCh], r8d
0x180059182  call    cs:__imp_MulDiv
0x180059189  nop     dword ptr [rax+rax+00h]
0x18005918e  movsxd  rcx, eax
0x180059191  lea     rdi, [rbx+3C2D8h]
0x180059198  mov     [rbx+20h], rcx
0x18005919c  mov     r9d, 2B1h; unsigned int
0x1800591a2  add     [rbx+40h], rcx
0x1800591a6  lea     r8, aCaacdecConvert; "CAACDec::ConvertAACFrameToADTS"
0x1800591ad  mov     rax, [rbx+40h]
0x1800591b1  mov     edx, 5; unsigned __int8
0x1800591b6  mov     [rsp+98h+var_60], rax
0x1800591bb  lea     rax, aCaacdecConvert_2; "CAACDec::ConvertAACFrameToADTS() dwChan"...
0x1800591c2  mov     [rsp+98h+var_68], rcx
0x1800591c7  mov     rcx, rdi; this
0x1800591ca  mov     [rsp+98h+var_70], r12d
0x1800591cf  mov     [rsp+98h+Format], rax; Format
0x1800591d4  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x1800591d9  jmp     short loc_1800591E7
0x1800591db  mov     esi, 80004005h
0x1800591e0  lea     rdi, [rbx+3C2D8h]
0x1800591e7  mov     eax, [rbx+3C104h]
0x1800591ed  lea     r8, aCaacdecConvert; "CAACDec::ConvertAACFrameToADTS"
0x1800591f4  mov     dword ptr [rsp+98h+var_68], eax
0x1800591f8  mov     r9d, 2B5h; unsigned int
0x1800591fe  mov     eax, [rbx+3C100h]
0x180059204  mov     edx, 5; unsigned __int8
0x180059209  mov     [rsp+98h+var_70], eax
0x18005920d  mov     rcx, rdi; this
0x180059210  lea     rax, aCaacdecConvert_1; "CAACDec::ConvertAACFrameToADTS() m_ulOu"...
0x180059217  mov     [rsp+98h+Format], rax; Format
0x18005921c  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x180059221  test    esi, esi
0x180059223  jz      short loc_180059260
0x180059225  mov     r9d, 2B6h; unsigned int
0x18005922b  lea     rax, aAvcoreCodecdsp; "avcore\\codecdsp\\audio\\aacdec\\curren"...
0x180059232  mov     dword ptr [rsp+98h+var_60], r9d
0x180059237  lea     r8, aCaacdecConvert; "CAACDec::ConvertAACFrameToADTS"
0x18005923e  mov     [rsp+98h+var_68], rax
0x180059243  mov     edx, 2; unsigned __int8
0x180059248  lea     rax, aError08xReturn; "Error %08X returned: File: %s, Line: %d"
0x18005924f  mov     [rsp+98h+var_70], esi
0x180059253  mov     rcx, rdi; this
0x180059256  mov     [rsp+98h+Format], rax; Format
0x18005925b  call    ?TraceVA@TraceLoggingHelperBase@@QEAAXEPEBDI0ZZ; TraceLoggingHelperBase::TraceVA(uchar,char const *,uint,char const *,...)
0x180059260  mov     eax, esi
0x180059262  add     rsp, 58h
0x180059266  pop     r15
0x180059268  pop     r14
0x18005926a  pop     r13
0x18005926c  pop     r12
0x18005926e  pop     rdi
0x18005926f  pop     rsi
0x180059270  pop     rbp
0x180059271  pop     rbx
0x180059272  retn
```
