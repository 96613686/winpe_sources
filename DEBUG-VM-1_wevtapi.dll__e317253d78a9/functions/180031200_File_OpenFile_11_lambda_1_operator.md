# _File::OpenFile_::_11_::_lambda_1_::operator()

- ea: `0x180031200`
- end: `0x180031497`
- name: `_File::OpenFile_::_11_::_lambda_1_::operator()`
- size: `663`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800227b4`

## callees

- `0x180023548`
- `0x180031200`
- `0x180033174`
- `0x180034bec`
- `0x180034d34`
- `0x180038fb4`

## pseudocode

```c
__int64 __fastcall File::OpenFile_::_11_::_lambda_1_::operator()(__int64 *a1)
{
  __int128 *FileHeader; // rax
  __int128 v3; // xmm0
  __int128 v4; // xmm1
  __int128 v5; // xmm2
  __int128 v6; // xmm3
  __int128 v7; // xmm4
  __int128 v8; // xmm5
  __int128 v9; // xmm6
  __int128 v10; // xmm7
  _OWORD *v11; // rax
  __int64 result; // rax
  __int128 pExceptionObject; // [rsp+28h] [rbp-79h] BYREF
  __int64 v14; // [rsp+38h] [rbp-69h]
  int v15; // [rsp+40h] [rbp-61h]
  int v16; // [rsp+44h] [rbp-5Dh]
  int v17; // [rsp+48h] [rbp-59h]
  _BYTE v18[168]; // [rsp+50h] [rbp-51h] BYREF

  *(_QWORD *)(*a1 + 792) = GetLogSize(*(void **)(*a1 + 672));
  if ( *(_QWORD *)(*a1 + 792) < 0x11000u )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_b0e12c676fa238c8d52327699eb18844_Traceguids, 1500);
    }
    v14 = 0;
    v15 = 1500;
    v16 = -1;
    pExceptionObject = 0;
    v17 = 444;
    throw (EvtException *)&pExceptionObject;
  }
  FileHeader = (__int128 *)ReadFileHeader(v18, *(_QWORD *)(*a1 + 672));
  v3 = *FileHeader;
  v4 = FileHeader[1];
  v5 = FileHeader[2];
  v6 = FileHeader[3];
  v7 = FileHeader[4];
  v8 = FileHeader[5];
  v9 = FileHeader[6];
  v10 = FileHeader[7];
  v11 = (_OWORD *)*a1;
  v11[1] = v3;
  v11[2] = v4;
  v11[3] = v5;
  v11[4] = v6;
  v11[5] = v7;
  v11[6] = v8;
  v11[7] = v9;
  v11[8] = v10;
  if ( !IsFileHeaderValid((PUCHAR)(*a1 + 16)) )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_b0e12c676fa238c8d52327699eb18844_Traceguids, 1500);
    }
    v14 = 0;
    v15 = 1500;
    v16 = -1;
    pExceptionObject = 0;
    v17 = 452;
    throw (EvtException *)&pExceptionObject;
  }
  result = *a1;
  if ( *(_WORD *)(*a1 + 54) > 3u )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_b0e12c676fa238c8d52327699eb18844_Traceguids, 15035);
    }
    v14 = 0;
    v15 = 15035;
    v16 = -1;
    pExceptionObject = 0;
    v17 = 457;
    throw (EvtException *)&pExceptionObject;
  }
  if ( *(_WORD *)(*a1 + 54) < 3u )
  {
    if ( WPP_GLOBAL_Control != (LastErrInfo *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, &WPP_b0e12c676fa238c8d52327699eb18844_Traceguids, 15034);
    }
    v14 = 0;
    v15 = 15034;
    v16 = -1;
    pExceptionObject = 0;
    v17 = 462;
    throw (EvtException *)&pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x180031200  mov     rax, rsp
0x180031203  mov     [rax+8], rdi
0x180031207  push    rbp
0x180031208  lea     rbp, [rax-5Fh]
0x18003120c  sub     rsp, 0F0h
0x180031213  mov     rdi, rcx
0x180031216  movaps  xmmword ptr [rax-18h], xmm6
0x18003121a  mov     rcx, [rcx]
0x18003121d  movaps  xmmword ptr [rax-28h], xmm7
0x180031221  mov     rcx, [rcx+2A0h]; void *
0x180031228  call    ?GetLogSize@@YA_KPEAX@Z; GetLogSize(void *)
0x18003122d  mov     rdx, [rdi]
0x180031230  mov     [rdx+318h], rax
0x180031237  mov     rdx, [rdi]
0x18003123a  cmp     qword ptr [rdx+318h], 11000h
0x180031245  jnb     short loc_1800312B8
0x180031247  mov     rcx, cs:WPP_GLOBAL_Control
0x18003124e  lea     rax, WPP_GLOBAL_Control
0x180031255  mov     edi, 5DCh
0x18003125a  cmp     rcx, rax
0x18003125d  jz      short loc_180031286
0x18003125f  test    dword ptr [rcx+1Ch], 8000h
0x180031266  jz      short loc_180031286
0x180031268  cmp     byte ptr [rcx+19h], 2
0x18003126c  jb      short loc_180031286
0x18003126e  mov     rcx, [rcx+10h]
0x180031272  lea     r8, WPP_b0e12c676fa238c8d52327699eb18844_Traceguids
0x180031279  mov     edx, 10h
0x18003127e  mov     r9d, edi
0x180031281  call    WPP_SF_D
0x180031286  xorps   xmm0, xmm0
0x180031289  mov     [rbp+57h+var_C0], 0
0x180031291  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x180031298  mov     [rbp+57h+var_B8], edi
0x18003129b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18003129f  mov     [rbp+57h+var_B4], 0FFFFFFFFh
0x1800312a6  movdqu  [rbp+57h+pExceptionObject], xmm0
0x1800312ab  mov     [rbp+57h+var_B0], 1BCh
0x1800312b2  call    _CxxThrowException_0
0x1800312b8  mov     rdx, [rdx+2A0h]
0x1800312bf  lea     rcx, [rbp+57h+var_A8]
0x1800312c3  call    ReadFileHeader
0x1800312c8  movups  xmm0, xmmword ptr [rax]
0x1800312cb  movups  xmm1, xmmword ptr [rax+10h]
0x1800312cf  movups  xmm2, xmmword ptr [rax+20h]
0x1800312d3  movups  xmm3, xmmword ptr [rax+30h]
0x1800312d7  movups  xmm4, xmmword ptr [rax+40h]
0x1800312db  movups  xmm5, xmmword ptr [rax+50h]
0x1800312df  movups  xmm6, xmmword ptr [rax+60h]
0x1800312e3  movups  xmm7, xmmword ptr [rax+70h]
0x1800312e7  mov     rax, [rdi]
0x1800312ea  movups  xmmword ptr [rax+10h], xmm0
0x1800312ee  movups  xmmword ptr [rax+20h], xmm1
0x1800312f2  movups  xmmword ptr [rax+30h], xmm2
0x1800312f6  movups  xmmword ptr [rax+40h], xmm3
0x1800312fa  movups  xmmword ptr [rax+50h], xmm4
0x1800312fe  movups  xmmword ptr [rax+60h], xmm5
0x180031302  movups  xmmword ptr [rax+70h], xmm6
0x180031306  movups  xmmword ptr [rax+80h], xmm7
0x18003130d  mov     rcx, [rdi]
0x180031310  add     rcx, 10h; Buffer
0x180031314  call    ?IsFileHeaderValid@@YA_NAEBUFileHeader@@@Z; IsFileHeaderValid(FileHeader const &)
0x180031319  test    al, al
0x18003131b  jnz     short loc_18003138E
0x18003131d  mov     rcx, cs:WPP_GLOBAL_Control
0x180031324  lea     rax, WPP_GLOBAL_Control
0x18003132b  mov     edi, 5DCh
0x180031330  cmp     rcx, rax
0x180031333  jz      short loc_18003135C
0x180031335  test    dword ptr [rcx+1Ch], 8000h
0x18003133c  jz      short loc_18003135C
0x18003133e  cmp     byte ptr [rcx+19h], 2
0x180031342  jb      short loc_18003135C
0x180031344  mov     rcx, [rcx+10h]
0x180031348  lea     r8, WPP_b0e12c676fa238c8d52327699eb18844_Traceguids
0x18003134f  mov     edx, 11h
0x180031354  mov     r9d, edi
0x180031357  call    WPP_SF_D
0x18003135c  xorps   xmm0, xmm0
0x18003135f  mov     [rbp+57h+var_C0], 0
0x180031367  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18003136e  mov     [rbp+57h+var_B8], edi
0x180031371  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180031375  mov     [rbp+57h+var_B4], 0FFFFFFFFh
0x18003137c  movdqu  [rbp+57h+pExceptionObject], xmm0
0x180031381  mov     [rbp+57h+var_B0], 1C4h
0x180031388  call    _CxxThrowException_0
0x18003138e  mov     rax, [rdi]
0x180031391  cmp     word ptr [rax+36h], 3
0x180031396  jbe     short loc_180031409
0x180031398  mov     rcx, cs:WPP_GLOBAL_Control
0x18003139f  lea     rax, WPP_GLOBAL_Control
0x1800313a6  mov     edi, 3ABBh
0x1800313ab  cmp     rcx, rax
0x1800313ae  jz      short loc_1800313D7
0x1800313b0  test    dword ptr [rcx+1Ch], 8000h
0x1800313b7  jz      short loc_1800313D7
0x1800313b9  cmp     byte ptr [rcx+19h], 2
0x1800313bd  jb      short loc_1800313D7
0x1800313bf  mov     rcx, [rcx+10h]
0x1800313c3  lea     r8, WPP_b0e12c676fa238c8d52327699eb18844_Traceguids
0x1800313ca  mov     edx, 12h
0x1800313cf  mov     r9d, edi
0x1800313d2  call    WPP_SF_D
0x1800313d7  xorps   xmm0, xmm0
0x1800313da  mov     [rbp+57h+var_C0], 0
0x1800313e2  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x1800313e9  mov     [rbp+57h+var_B8], edi
0x1800313ec  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800313f0  mov     [rbp+57h+var_B4], 0FFFFFFFFh
0x1800313f7  movdqu  [rbp+57h+pExceptionObject], xmm0
0x1800313fc  mov     [rbp+57h+var_B0], 1C9h
0x180031403  call    _CxxThrowException_0
0x180031409  jnb     short loc_18003147C
0x18003140b  mov     rcx, cs:WPP_GLOBAL_Control
0x180031412  lea     rax, WPP_GLOBAL_Control
0x180031419  mov     edi, 3ABAh
0x18003141e  cmp     rcx, rax
0x180031421  jz      short loc_18003144A
0x180031423  test    dword ptr [rcx+1Ch], 8000h
0x18003142a  jz      short loc_18003144A
0x18003142c  cmp     byte ptr [rcx+19h], 2
0x180031430  jb      short loc_18003144A
0x180031432  mov     rcx, [rcx+10h]
0x180031436  lea     r8, WPP_b0e12c676fa238c8d52327699eb18844_Traceguids
0x18003143d  mov     edx, 13h
0x180031442  mov     r9d, edi
0x180031445  call    WPP_SF_D
0x18003144a  xorps   xmm0, xmm0
0x18003144d  mov     [rbp+57h+var_C0], 0
0x180031455  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x18003145c  mov     [rbp+57h+var_B8], edi
0x18003145f  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180031463  mov     [rbp+57h+var_B4], 0FFFFFFFFh
0x18003146a  movdqu  [rbp+57h+pExceptionObject], xmm0
0x18003146f  mov     [rbp+57h+var_B0], 1CEh
0x180031476  call    _CxxThrowException_0
0x18003147c  lea     r11, [rsp+0F0h+var_s0]
0x180031484  mov     rdi, [r11+10h]
0x180031488  movaps  xmm6, xmmword ptr [r11-10h]
0x18003148d  movaps  xmm7, xmmword ptr [r11-20h]
0x180031492  mov     rsp, r11
0x180031495  pop     rbp
0x180031496  retn
```
