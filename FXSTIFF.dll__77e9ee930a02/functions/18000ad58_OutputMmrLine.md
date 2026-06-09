# OutputMmrLine

- ea: `0x18000ad58`
- end: `0x18000b118`
- name: `OutputMmrLine`
- size: `960`
- prototype: `__int64 __fastcall(int *, unsigned __int8, unsigned __int16 *, unsigned __int16 *, int **, unsigned __int8 *, unsigned __int64, int)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18000a130`
- `0x18000b120`
- `0x18000bb50`

## callees

- `0x1800042c4`
- `0x180009f04`
- `0x180009f34`
- `0x18000ad58`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000b01f`
- `KERNEL32!SetLastError` at `0x18000b082`
- `KERNEL32!SetLastError` at `0x18000b0c9`
- `KERNEL32!SetLastError` at `0x18000b01f`
- `KERNEL32!SetLastError` at `0x18000b082`
- `KERNEL32!SetLastError` at `0x18000b0c9`

## pseudocode

```c
__int64 __fastcall OutputMmrLine(
        int *a1,
        unsigned __int8 a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        int **a5,
        unsigned __int8 *a6,
        unsigned __int64 a7,
        int a8)
{
  int v8; // r11d
  int v9; // r14d
  int *v10; // rbx
  int v11; // edi
  int v12; // ecx
  unsigned __int16 *v13; // r12
  int v15; // r10d
  unsigned int v16; // r8d
  int v17; // eax
  __int64 v18; // rax
  unsigned __int64 v19; // rsi
  int v20; // r9d
  int v21; // r10d
  int v22; // ecx
  int v23; // r8d
  unsigned __int8 v24; // cl
  unsigned __int64 v25; // r8
  unsigned int v26; // eax
  char v27; // cl
  int v28; // r13d
  int v29; // eax
  unsigned __int8 v30; // dl
  int v31; // edx
  int v32; // eax
  int v33; // r12d
  int v34; // ebx
  int v35; // edx
  int v36; // r10d
  int v37; // eax
  __int64 v38; // rax
  __int64 result; // rax
  _QWORD *v40; // rcx
  __int64 v41; // rdx
  int *v42; // [rsp+70h] [rbp+48h] BYREF
  unsigned __int8 v43; // [rsp+78h] [rbp+50h] BYREF
  int v44; // [rsp+80h] [rbp+58h]
  unsigned __int16 *v45; // [rsp+88h] [rbp+60h]

  v45 = a4;
  v42 = a1;
  v8 = a8;
  v9 = 0;
  v10 = a1;
  v44 = 0;
  v11 = 0;
  v12 = 0;
  v13 = a4;
  v15 = 0;
  do
  {
    v16 = a3[v12];
    if ( v16 >= v8 )
      break;
    if ( (_WORD)v16 == a3[v12 + 1] )
    {
      v17 = 2;
    }
    else
    {
      v18 = v15++;
      a3[v18] = v16;
      v17 = 1;
    }
    v12 += v17;
  }
  while ( v12 < 1730 );
  v19 = a7;
  v20 = 0;
  a3[v15] = v8;
  v21 = *a3;
  v22 = *v13;
  while ( 1 )
  {
    if ( (unsigned __int64)v10 >= v19 || (unsigned __int64)((__int64)(v19 - (_QWORD)v10) >> 2) < 4 )
    {
      SetLastError(0x7Au);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          &WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids,
          (unsigned int)((__int64)(v19 - (_QWORD)v10) >> 2));
      }
      return 0;
    }
    v23 = v22 < v8 ? v13[v11 + 1] : v8;
    if ( v23 >= v21 )
    {
      if ( (unsigned int)(v21 - v22 + 3) > 6 )
      {
        if ( v21 < v8 )
          v28 = a3[v9 + 1];
        else
          v28 = v8;
        v29 = 4 << a2;
        v30 = a2 + 3;
        *v10 += v29;
        v43 = v30;
        if ( v30 > 0x1Fu )
        {
          v43 = v30 - 32;
          v42 = v10 + 1;
          v10[1] = 4u >> (3 - (v30 - 32));
        }
        v31 = v9;
        if ( v9 >= 1731 )
        {
LABEL_28:
          v32 = v44;
        }
        else
        {
          while ( a3[v31] <= v20 )
          {
            if ( ++v31 >= 1731 )
              goto LABEL_28;
          }
          v9 = v31;
          v32 = v31 & 1;
          v44 = v32;
        }
        if ( v21 && v32 )
        {
          v33 = 0;
          v34 = v28 - v21;
          v35 = 255;
          v36 = v21 - v20;
        }
        else
        {
          v33 = 255;
          v34 = v28 - v21;
          v36 = v21 - v20;
          v35 = 0;
        }
        OutputRunFastReversed(v36, v35, &v42, &v43);
        OutputRunFastReversed(v34, v33, &v42, &v43);
        a2 = v43;
        v20 = v28;
        v8 = a8;
        v10 = v42;
        v13 = v45;
      }
      else
      {
        v25 = (unsigned int)v21 - (unsigned __int64)(unsigned int)v22;
        *v10 += asc_18001BCD8[2 * v25 + 7] << a2;
        a2 += LOBYTE(asc_18001BCD8[2 * v25 + 6]);
        if ( a2 > 0x1Fu )
        {
          ++v10;
          v26 = asc_18001BCD8[2 * v25 + 7];
          a2 -= 32;
          v27 = LOBYTE(asc_18001BCD8[2 * v25 + 6]) - a2;
          v42 = v10;
          *v10 = v26 >> v27;
        }
        v20 = v21;
      }
    }
    else
    {
      v24 = a2;
      a2 += 4;
      *v10 += 8 << v24;
      if ( a2 > 0x1Fu )
      {
        v42 = ++v10;
        a2 -= 32;
        *v10 = 8u >> (4 - a2);
      }
      v20 = v23;
    }
    if ( v20 >= v8 )
      break;
    while ( v9 < 1731 )
    {
      if ( a3[v9] > v20 )
        goto LABEL_41;
      ++v9;
    }
    if ( v9 == 1731 )
    {
      SetLastError(0x7Au);
      v40 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v41 = 32;
        goto LABEL_60;
      }
      return 0;
    }
LABEL_41:
    v37 = v11 - 1;
    if ( v11 <= 0 )
      v37 = v11;
    v11 = v37;
    if ( v37 >= 1731 )
    {
LABEL_46:
      if ( v11 != 1731 )
        goto LABEL_47;
      SetLastError(0x7Au);
      v40 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v41 = 33;
LABEL_60:
        WPP_SF_(v40[2], v41, &WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids);
        return 0;
      }
      return 0;
    }
    while ( v13[v11] <= v20 )
    {
      if ( ++v11 >= 1731 )
        goto LABEL_46;
    }
LABEL_47:
    v21 = a3[v9];
    v22 = v13[v11];
    if ( (((unsigned __int8)v9 ^ (unsigned __int8)v11) & 1) != 0 && v22 < v8 )
    {
      v38 = v11++;
      v22 = v13[v38 + 1];
    }
  }
  result = 1;
  *a5 = v10;
  *a6 = a2;
  return result;
}

```

## disassembly

```asm
0x18000ad58  mov     [rsp-40h+arg_18], r9
0x18000ad5d  mov     [rsp-40h+arg_0], rcx
0x18000ad62  push    rbp
0x18000ad63  push    rbx
0x18000ad64  push    rsi
0x18000ad65  push    rdi
0x18000ad66  push    r12
0x18000ad68  push    r13
0x18000ad6a  push    r14
0x18000ad6c  push    r15
0x18000ad6e  mov     rbp, rsp
0x18000ad71  sub     rsp, 28h
0x18000ad75  mov     r11d, [rbp+arg_38]
0x18000ad7c  xor     r14d, r14d
0x18000ad7f  mov     rbx, rcx
0x18000ad82  mov     [rbp+arg_10], 0
0x18000ad89  xor     edi, edi
0x18000ad8b  xor     ecx, ecx
0x18000ad8d  mov     r12, r9
0x18000ad90  mov     r15, r8
0x18000ad93  lea     r13d, [r14+1]
0x18000ad97  xor     r10d, r10d
0x18000ad9a  movsxd  rax, ecx
0x18000ad9d  movzx   r8d, word ptr [r15+rax*2]
0x18000ada2  cmp     r8d, r11d
0x18000ada5  jnb     short loc_18000ADCE
0x18000ada7  cmp     r8w, [r15+rax*2+2]
0x18000adad  jnz     short loc_18000ADB6
0x18000adaf  mov     eax, 2
0x18000adb4  jmp     short loc_18000ADC4
0x18000adb6  movsxd  rax, r10d
0x18000adb9  add     r10d, r13d
0x18000adbc  mov     [r15+rax*2], r8w
0x18000adc1  mov     eax, r13d
0x18000adc4  add     ecx, eax
0x18000adc6  cmp     ecx, 6C2h
0x18000adcc  jl      short loc_18000AD9A
0x18000adce  mov     rsi, [rbp+arg_30]
0x18000add2  xor     r9d, r9d
0x18000add5  movsxd  rax, r10d
0x18000add8  mov     [r15+rax*2], r11w
0x18000addd  movzx   r10d, word ptr [r15]
0x18000ade1  movzx   ecx, word ptr [r12]
0x18000ade6  jmp     loc_18000B011
0x18000adeb  mov     rax, rsi
0x18000adee  sub     rax, rbx
0x18000adf1  sar     rax, 2
0x18000adf5  cmp     rax, 4
0x18000adf9  jb      loc_18000B01A
0x18000adff  cmp     ecx, r11d
0x18000ae02  jl      short loc_18000AE09
0x18000ae04  mov     r8d, r11d
0x18000ae07  jmp     short loc_18000AE12
0x18000ae09  movsxd  rax, edi
0x18000ae0c  movzx   r8d, word ptr [r12+rax*2+2]
0x18000ae12  cmp     r8d, r10d
0x18000ae15  jge     short loc_18000AE51
0x18000ae17  mov     cl, dl
0x18000ae19  mov     r9d, 8
0x18000ae1f  mov     eax, r9d
0x18000ae22  add     dl, 4
0x18000ae25  shl     eax, cl
0x18000ae27  add     [rbx], eax
0x18000ae29  cmp     dl, 1Fh
0x18000ae2c  jbe     short loc_18000AE49
0x18000ae2e  add     rbx, 4
0x18000ae32  lea     ecx, [r9-4]
0x18000ae36  sub     dl, 20h ; ' '
0x18000ae39  mov     [rbp+arg_0], rbx
0x18000ae3d  movzx   edx, dl
0x18000ae40  mov     eax, r9d
0x18000ae43  sub     ecx, edx
0x18000ae45  shr     eax, cl
0x18000ae47  mov     [rbx], eax
0x18000ae49  mov     r9d, r8d
0x18000ae4c  jmp     loc_18000AF8D
0x18000ae51  mov     eax, r10d
0x18000ae54  sub     eax, ecx
0x18000ae56  add     eax, 3
0x18000ae59  cmp     eax, 6
0x18000ae5c  ja      short loc_18000AEA7
0x18000ae5e  mov     eax, ecx
0x18000ae60  lea     r9, asc_18001BCD8; "\a "
0x18000ae67  mov     cl, dl
0x18000ae69  mov     r8d, r10d
0x18000ae6c  sub     r8, rax
0x18000ae6f  movzx   eax, word ptr [r9+r8*4+0Eh]
0x18000ae75  shl     eax, cl
0x18000ae77  add     [rbx], eax
0x18000ae79  add     dl, [r9+r8*4+0Ch]
0x18000ae7e  cmp     dl, 1Fh
0x18000ae81  jbe     short loc_18000AE9F
0x18000ae83  mov     cl, [r9+r8*4+0Ch]
0x18000ae88  add     rbx, 4
0x18000ae8c  movzx   eax, word ptr [r9+r8*4+0Eh]
0x18000ae92  sub     dl, 20h ; ' '
0x18000ae95  sub     cl, dl
0x18000ae97  mov     [rbp+arg_0], rbx
0x18000ae9b  shr     eax, cl
0x18000ae9d  mov     [rbx], eax
0x18000ae9f  mov     r9d, r10d
0x18000aea2  jmp     loc_18000AF8D
0x18000aea7  cmp     r10d, r11d
0x18000aeaa  jl      short loc_18000AEB1
0x18000aeac  mov     r13d, r11d
0x18000aeaf  jmp     short loc_18000AEBA
0x18000aeb1  movsxd  rax, r14d
0x18000aeb4  movzx   r13d, word ptr [r15+rax*2+2]
0x18000aeba  mov     cl, dl
0x18000aebc  mov     eax, 4
0x18000aec1  shl     eax, cl
0x18000aec3  add     dl, 3
0x18000aec6  add     [rbx], eax
0x18000aec8  mov     [rbp+arg_8], dl
0x18000aecb  cmp     dl, 1Fh
0x18000aece  jbe     short loc_18000AEF1
0x18000aed0  add     rbx, 4
0x18000aed4  sub     dl, 20h ; ' '
0x18000aed7  movzx   eax, dl
0x18000aeda  mov     ecx, 3
0x18000aedf  mov     [rbp+arg_8], al
0x18000aee2  sub     ecx, eax
0x18000aee4  mov     eax, 4
0x18000aee9  mov     [rbp+arg_0], rbx
0x18000aeed  shr     eax, cl
0x18000aeef  mov     [rbx], eax
0x18000aef1  mov     r8d, 6C3h
0x18000aef7  mov     edx, r14d
0x18000aefa  cmp     r14d, r8d
0x18000aefd  jge     short loc_18000AF13
0x18000aeff  movsxd  rax, edx
0x18000af02  movzx   ecx, word ptr [r15+rax*2]
0x18000af07  cmp     ecx, r9d
0x18000af0a  jg      short loc_18000AF32
0x18000af0c  inc     edx
0x18000af0e  cmp     edx, r8d
0x18000af11  jl      short loc_18000AEFF
0x18000af13  mov     eax, [rbp+arg_10]
0x18000af16  test    r10d, r10d
0x18000af19  jz      short loc_18000AF3F
0x18000af1b  test    eax, eax
0x18000af1d  jz      short loc_18000AF3F
0x18000af1f  mov     ebx, r13d
0x18000af22  xor     r12d, r12d
0x18000af25  sub     ebx, r10d
0x18000af28  mov     edx, 0FFh
0x18000af2d  sub     r10d, r9d
0x18000af30  jmp     short loc_18000AF50
0x18000af32  mov     eax, edx
0x18000af34  mov     r14d, edx
0x18000af37  and     eax, 1
0x18000af3a  mov     [rbp+arg_10], eax
0x18000af3d  jmp     short loc_18000AF16
0x18000af3f  mov     ebx, r13d
0x18000af42  mov     r12d, 0FFh
0x18000af48  sub     ebx, r10d
0x18000af4b  sub     r10d, r9d
0x18000af4e  xor     edx, edx
0x18000af50  lea     r9, [rbp+arg_8]
0x18000af54  mov     ecx, r10d
0x18000af57  lea     r8, [rbp+arg_0]
0x18000af5b  call    OutputRunFastReversed
0x18000af60  mov     edx, r12d
0x18000af63  lea     r9, [rbp+arg_8]
0x18000af67  mov     ecx, ebx
0x18000af69  lea     r8, [rbp+arg_0]
0x18000af6d  call    OutputRunFastReversed
0x18000af72  mov     dl, [rbp+arg_8]
0x18000af75  mov     r9d, r13d
0x18000af78  mov     r11d, [rbp+arg_38]
0x18000af7f  mov     r13d, 1
0x18000af85  mov     rbx, [rbp+arg_0]
0x18000af89  mov     r12, [rbp+arg_18]
0x18000af8d  cmp     r9d, r11d
0x18000af90  jge     loc_18000B103
0x18000af96  mov     r10d, 6C3h
0x18000af9c  jmp     short loc_18000AFAE
0x18000af9e  movsxd  rax, r14d
0x18000afa1  movzx   ecx, word ptr [r15+rax*2]
0x18000afa6  cmp     ecx, r9d
0x18000afa9  jg      short loc_18000AFB9
0x18000afab  add     r14d, r13d
0x18000afae  cmp     r14d, r10d
0x18000afb1  jl      short loc_18000AF9E
0x18000afb3  jz      loc_18000B0C4
0x18000afb9  test    edi, edi
0x18000afbb  movsxd  r8, r14d
0x18000afbe  lea     eax, [rdi-1]
0x18000afc1  cmovle  eax, edi
0x18000afc4  mov     edi, eax
0x18000afc6  cmp     eax, r10d
0x18000afc9  jge     short loc_18000AFE0
0x18000afcb  movsxd  rax, edi
0x18000afce  movzx   ecx, word ptr [r12+rax*2]
0x18000afd3  cmp     ecx, r9d
0x18000afd6  jg      short loc_18000AFE9
0x18000afd8  add     edi, r13d
0x18000afdb  cmp     edi, r10d
0x18000afde  jl      short loc_18000AFCB
0x18000afe0  cmp     edi, r10d
0x18000afe3  jz      loc_18000B07D
0x18000afe9  movzx   r10d, word ptr [r15+r8*2]
0x18000afee  movsxd  rax, edi
0x18000aff1  movzx   ecx, word ptr [r12+rax*2]
0x18000aff6  mov     eax, edi
0x18000aff8  xor     eax, r14d
0x18000affb  test    r13b, al
0x18000affe  jz      short loc_18000B011
0x18000b000  cmp     ecx, r11d
0x18000b003  jge     short loc_18000B011
0x18000b005  movsxd  rax, edi
0x18000b008  add     edi, r13d
0x18000b00b  movzx   ecx, word ptr [r12+rax*2+2]
0x18000b011  cmp     rbx, rsi
0x18000b014  jb      loc_18000ADEB
0x18000b01a  mov     ecx, 7Ah ; 'z'; dwErrCode
0x18000b01f  call    cs:__imp_SetLastError
0x18000b026  nop     dword ptr [rax+rax+00h]
0x18000b02b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b032  lea     rax, WPP_GLOBAL_Control
0x18000b039  cmp     rcx, rax
0x18000b03c  jz      short loc_18000B069
0x18000b03e  test    byte ptr [rcx+1Ch], 2
0x18000b042  jz      short loc_18000B069
0x18000b044  cmp     byte ptr [rcx+19h], 2
0x18000b048  jb      short loc_18000B069
0x18000b04a  mov     rcx, [rcx+10h]
0x18000b04e  lea     r8, WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids
0x18000b055  sub     rsi, rbx
0x18000b058  mov     edx, 1Fh
0x18000b05d  sar     rsi, 2
0x18000b061  mov     r9d, esi
0x18000b064  call    WPP_SF_d
0x18000b069  xor     eax, eax
0x18000b06b  add     rsp, 28h
0x18000b06f  pop     r15
0x18000b071  pop     r14
0x18000b073  pop     r13
0x18000b075  pop     r12
0x18000b077  pop     rdi
0x18000b078  pop     rsi
0x18000b079  pop     rbx
0x18000b07a  pop     rbp
0x18000b07b  retn
0x18000b07d  mov     ecx, 7Ah ; 'z'; dwErrCode
0x18000b082  call    cs:__imp_SetLastError
0x18000b089  nop     dword ptr [rax+rax+00h]
0x18000b08e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b095  lea     rax, WPP_GLOBAL_Control
0x18000b09c  cmp     rcx, rax
0x18000b09f  jz      short loc_18000B069
0x18000b0a1  test    byte ptr [rcx+1Ch], 2
0x18000b0a5  jz      short loc_18000B069
0x18000b0a7  cmp     byte ptr [rcx+19h], 2
0x18000b0ab  jb      short loc_18000B069
0x18000b0ad  mov     edx, 21h ; '!'
0x18000b0b2  mov     rcx, [rcx+10h]
0x18000b0b6  lea     r8, WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids
0x18000b0bd  call    WPP_SF_
0x18000b0c2  jmp     short loc_18000B069
0x18000b0c4  mov     ecx, 7Ah ; 'z'; dwErrCode
0x18000b0c9  call    cs:__imp_SetLastError
0x18000b0d0  nop     dword ptr [rax+rax+00h]
0x18000b0d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b0dc  lea     rax, WPP_GLOBAL_Control
0x18000b0e3  cmp     rcx, rax
0x18000b0e6  jz      short loc_18000B069
0x18000b0e8  test    byte ptr [rcx+1Ch], 2
0x18000b0ec  jz      loc_18000B069
0x18000b0f2  cmp     byte ptr [rcx+19h], 2
0x18000b0f6  jb      loc_18000B069
0x18000b0fc  mov     edx, 20h ; ' '
0x18000b101  jmp     short loc_18000B0B2
0x18000b103  mov     rcx, [rbp+arg_20]
0x18000b107  mov     eax, r13d
0x18000b10a  mov     [rcx], rbx
0x18000b10d  mov     rcx, [rbp+arg_28]
0x18000b111  mov     [rcx], dl
0x18000b113  jmp     loc_18000B06B
```
