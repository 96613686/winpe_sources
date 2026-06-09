# AudioSpecificConfig_Parse(CSAudioSpecificConfig *,CDK_BITSTREAM *,int,CSTpCallBacks *,uchar,uchar,AUDIO_OBJECT_TYPE)

- ea: `0x180011da8`
- end: `0x18001225b`
- name: `?AudioSpecificConfig_Parse@@YA?AW4TRANSPORTDEC_ERROR@@PEAUCSAudioSpecificConfig@@PEAUCDK_BITSTREAM@@HPEAUCSTpCallBacks@@EEW4AUDIO_OBJECT_TYPE@@@Z`
- size: `1203`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `3`
- callee_count: `12`
- tags: `registry_config, loader_planting`

## callers

- `0x180011b10`
- `0x1800712d4`
- `0x180078c50`

## callees

- `0x18000e9b0`
- `0x1800110c0`
- `0x180011da8`
- `0x1800122cc`
- `0x1800125f4`
- `0x18001262c`
- `0x180012768`
- `0x18004afa0`
- `0x18004dd14`
- `0x1800793b8`
- `0x180079784`
- `0x1800960c0`

## pseudocode

```c
__int64 __fastcall AudioSpecificConfig_Parse(
        unsigned __int8 *a1,
        int *a2,
        int a3,
        __int64 a4,
        unsigned __int8 a5,
        unsigned __int8 a6,
        int a7)
{
  int v10; // r15d
  unsigned int *v11; // r14
  unsigned int SampleRate; // eax
  __int64 v13; // r8
  char v15; // al
  unsigned __int64 v16; // rcx
  _BYTE *v17; // rbx
  __int64 result; // rax
  _BYTE *v19; // rsi
  unsigned int v20; // r14d
  __int64 v21; // r8
  unsigned int v22; // ebx
  int v23; // ecx
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  int v28; // ecx
  int v29; // ecx
  int v30; // eax
  char v31; // al
  int v32; // eax
  int AOT; // eax
  __int64 v34; // r8
  __int64 v35; // rdx
  unsigned int (__fastcall *v36)(_QWORD, int *, _QWORD, _QWORD, _DWORD, _DWORD, int, int, _DWORD, unsigned __int8, unsigned __int8 *); // rax
  unsigned int v37; // esi
  unsigned int v38; // [rsp+A0h] [rbp+8h]

  CDKsyncCache_0(a2);
  v38 = a2[2];
  memset_0(a1, 0, 0x6DCu);
  v10 = -1;
  *((_DWORD *)a1 + 300) = -1;
  a1[1231] = 15;
  a1[1225] = -1;
  memset_0(a1 + 732, 0, 0x1D1u);
  a1[734] = 15;
  v11 = (unsigned int *)(a1 + 1204);
  a1[1234] = a5;
  a1[1235] = a6;
  a1[1236] = a6;
  a1[1237] = a6;
  if ( a7 )
  {
    *((_DWORD *)a1 + 300) = a7;
    v19 = a1 + 1229;
    v17 = a1 + 1224;
  }
  else
  {
    *((_DWORD *)a1 + 300) = getAOT(a2);
    SampleRate = getSampleRate(a2, a1 + 1231, 4);
    *v11 = SampleRate;
    if ( !SampleRate )
      return 1025;
    if ( !(*((_DWORD *)a1 + 300) == 39 ? SampleRate <= 0x5DC00 : SampleRate <= 0x17700) )
      return 1025;
    v15 = CDKreadBits(a2, 4, v13);
    v16 = *((unsigned int *)a1 + 300);
    v17 = a1 + 1224;
    a1[1224] = v15;
    if ( v15 == 15 && (_DWORD)v16 == 2 )
    {
      *v17 = 31;
    }
    else if ( v15 )
    {
      if ( v15 > 2 && ((_DWORD)v16 == 6 || (_DWORD)v16 == 20) )
        return 1026;
    }
    else if ( (unsigned int)v16 <= 0x27 )
    {
      v35 = 0x80009A0000LL;
      if ( _bittest64(&v35, v16) )
        return 1026;
    }
    a1[1230] = 0;
    v19 = a1 + 1229;
    a1[1229] = 0;
    if ( (_DWORD)v16 == 5 || (_DWORD)v16 == 29 )
    {
      *((_DWORD *)a1 + 304) = 5;
      *v19 = 1;
      if ( (_DWORD)v16 == 29 )
        a1[1230] = 1;
      v32 = getSampleRate(a2, a1 + 1232, 4);
      *((_DWORD *)a1 + 305) = v32;
      if ( (unsigned int)(v32 - 1) > 0x176FF )
        return 1025;
      AOT = getAOT(a2);
      *((_DWORD *)a1 + 300) = AOT;
      if ( AOT != 2 )
      {
        if ( AOT != 22 )
          return 1026;
        a1[1233] = CDKreadBits(a2, 4, v34);
      }
    }
    else
    {
      *((_DWORD *)a1 + 304) = 0;
    }
  }
  switch ( *((_DWORD *)a1 + 300) )
  {
    case 2:
    case 6:
    case 0x11:
    case 0x14:
    case 0x16:
    case 0x17:
      v20 = v38;
      result = GaSpecificConfig_Parse(a1, a1, a2, v38);
      v22 = result;
      if ( (_DWORD)result )
        return result;
      v10 = *(_DWORD *)a1;
LABEL_23:
      v23 = *((_DWORD *)a1 + 300);
      if ( v23 == 2
        || *((_DWORD *)a1 + 300) == 6
        || *((_DWORD *)a1 + 300) == 17
        || *((_DWORD *)a1 + 300) == 20
        || *((_DWORD *)a1 + 300) == 22 )
      {
        *((_DWORD *)a1 + 302) = v10 != 0 ? 960 : 1024;
      }
      else if ( *((_DWORD *)a1 + 300) == 23 )
      {
        *((_DWORD *)a1 + 302) = v10 != 0 ? 480 : 512;
        goto LABEL_44;
      }
      v24 = v23 - 17;
      if ( v24 )
      {
        v25 = v24 - 3;
        if ( v25 )
        {
          v26 = v25 - 2;
          if ( v26 )
          {
            v27 = v26 - 1;
            if ( v27 )
            {
              v28 = v27 - 1;
              if ( v28 )
              {
                v29 = v28 - 1;
                if ( v29 )
                {
                  if ( v29 != 14 )
                    goto LABEL_36;
                }
              }
            }
          }
        }
      }
LABEL_44:
      v31 = CDKreadBits(a2, 2, v21);
      a1[1225] = v31;
      if ( v31 <= 1 )
      {
LABEL_36:
        if ( a3 )
        {
          v30 = *((_DWORD *)a1 + 300);
          if ( v30 == 2 || (unsigned int)(v30 - 22) <= 1 )
          {
            v22 = AudioSpecificConfig_ExtensionParse(a1, a2, a4);
            if ( v22 )
              return v22;
          }
        }
        if ( *((_DWORD *)a1 + 300) != 42 )
          return v22;
        CDKsyncCache_0(a2);
        v37 = a2[2] - v20;
        if ( !(unsigned int)StoreConfigAsBitstream(a2, v37, a1 + 1238) )
        {
          *((_DWORD *)a1 + 438) = (v37 - (v37 >> 31)) ^ ((int)(v37 - (v37 >> 31)) >> 31);
          return v22;
        }
        return 1025;
      }
      return 1026;
    case 0x1E:
      v36 = *(unsigned int (__fastcall **)(_QWORD, int *, _QWORD, _QWORD, _DWORD, _DWORD, int, int, _DWORD, unsigned __int8, unsigned __int8 *))(a4 + 64);
      if ( !v36
        || v36(
             *(_QWORD *)(a4 + 72),
             a2,
             *((unsigned int *)a1 + 300),
             *v11,
             *((_DWORD *)a1 + 302),
             (char)*v17,
             1,
             -1,
             0,
             a1[1234],
             a1 + 1237) )
      {
        return 1026;
      }
      v22 = 0;
      goto LABEL_70;
    case 0x27:
      result = EldSpecificConfig_Parse(a1, a2, a4);
      v22 = result;
      if ( (_DWORD)result )
        return result;
      v10 = *a1;
      *v19 = a1[1];
      *((_DWORD *)a1 + 305) = *v11 * (a1[3] + 1);
LABEL_70:
      v20 = v38;
      goto LABEL_23;
  }
  if ( *((_DWORD *)a1 + 300) != 42 )
    return 1026;
  result = UsacConfig_Parse(a1, a2, a4);
  v22 = result;
  if ( !(_DWORD)result )
    goto LABEL_70;
  return result;
}

```

## disassembly

```asm
0x180011da8  mov     [rsp+arg_8], rbx
0x180011dad  mov     [rsp+arg_10], r8d
0x180011db2  push    rbp
0x180011db3  push    rsi
0x180011db4  push    rdi
0x180011db5  push    r12
0x180011db7  push    r13
0x180011db9  push    r14
0x180011dbb  push    r15
0x180011dbd  sub     rsp, 60h
0x180011dc1  mov     rdi, rcx
0x180011dc4  mov     r13, r9
0x180011dc7  mov     rcx, rdx
0x180011dca  mov     rbp, rdx
0x180011dcd  call    CDKsyncCache_0
0x180011dd2  mov     eax, [rbp+8]
0x180011dd5  xor     edx, edx; Val
0x180011dd7  mov     r8d, 6DCh; Size
0x180011ddd  mov     [rsp+98h+arg_0], eax
0x180011de4  mov     rcx, rdi; void *
0x180011de7  call    memset_0
0x180011dec  or      r15d, 0FFFFFFFFh
0x180011df0  lea     rbx, [rdi+2DCh]
0x180011df7  lea     rsi, [rdi+4CFh]
0x180011dfe  mov     [rdi+4B0h], r15d
0x180011e05  mov     rcx, rbx; void *
0x180011e08  mov     byte ptr [rsi], 0Fh
0x180011e0b  xor     edx, edx; Val
0x180011e0d  mov     [rdi+4C9h], r15b
0x180011e14  mov     r8d, 1D1h; Size
0x180011e1a  call    memset_0
0x180011e1f  mov     al, [rsp+98h+arg_20]
0x180011e26  lea     r12, [rdi+4D5h]
0x180011e2d  mov     byte ptr [rbx+2], 0Fh
0x180011e31  lea     r14, [rdi+4B4h]
0x180011e38  mov     [rdi+4D2h], al
0x180011e3e  lea     ebx, [r15+5]
0x180011e42  mov     al, [rsp+98h+arg_28]
0x180011e49  mov     [rdi+4D3h], al
0x180011e4f  mov     [rdi+4D4h], al
0x180011e55  mov     [r12], al
0x180011e59  mov     eax, [rsp+98h+arg_30]
0x180011e60  test    eax, eax
0x180011e62  jnz     loc_180012026
0x180011e68  mov     rcx, rbp
0x180011e6b  call    getAOT
0x180011e70  mov     r8d, ebx
0x180011e73  mov     [rdi+4B0h], eax
0x180011e79  mov     rdx, rsi
0x180011e7c  mov     rcx, rbp
0x180011e7f  call    getSampleRate
0x180011e84  mov     [r14], eax
0x180011e87  test    eax, eax
0x180011e89  jz      loc_1800120EE
0x180011e8f  cmp     dword ptr [rdi+4B0h], 27h ; '''
0x180011e96  jz      loc_1800120F8
0x180011e9c  cmp     eax, 17700h
0x180011ea1  ja      loc_1800120EE
0x180011ea7  mov     edx, ebx
0x180011ea9  mov     rcx, rbp
0x180011eac  call    CDKreadBits
0x180011eb1  mov     ecx, [rdi+4B0h]
0x180011eb7  lea     rbx, [rdi+4C8h]
0x180011ebe  mov     [rbx], al
0x180011ec0  cmp     al, 0Fh
0x180011ec2  jz      loc_180012102
0x180011ec8  test    al, al
0x180011eca  jz      loc_180012113
0x180011ed0  cmp     al, 2
0x180011ed2  jle     short loc_180011EFC
0x180011ed4  cmp     ecx, 6
0x180011ed7  jnz     short loc_180011EF7
0x180011ed9  mov     eax, 402h
0x180011ede  mov     rbx, [rsp+98h+arg_8]
0x180011ee6  add     rsp, 60h
0x180011eea  pop     r15
0x180011eec  pop     r14
0x180011eee  pop     r13
0x180011ef0  pop     r12
0x180011ef2  pop     rdi
0x180011ef3  pop     rsi
0x180011ef4  pop     rbp
0x180011ef5  retn
0x180011ef7  cmp     ecx, 14h
0x180011efa  jz      short loc_180011ED9
0x180011efc  mov     byte ptr [rdi+4CEh], 0
0x180011f03  lea     rsi, [rdi+4CDh]
0x180011f0a  mov     byte ptr [rsi], 0
0x180011f0d  cmp     ecx, 5
0x180011f10  jz      loc_18001207B
0x180011f16  cmp     ecx, 1Dh
0x180011f19  jz      loc_18001207B
0x180011f1f  mov     dword ptr [rdi+4C0h], 0
0x180011f29  mov     r8d, [rdi+4B0h]
0x180011f30  mov     ecx, r8d
0x180011f33  sub     ecx, 2
0x180011f36  jz      short loc_180011F50
0x180011f38  sub     ecx, 4
0x180011f3b  jz      short loc_180011F50
0x180011f3d  sub     ecx, 0Bh
0x180011f40  jz      short loc_180011F50
0x180011f42  sub     ecx, 3
0x180011f45  jz      short loc_180011F50
0x180011f47  sub     ecx, 2
0x180011f4a  jnz     loc_180012135
0x180011f50  mov     r14d, [rsp+98h+arg_0]
0x180011f58  mov     r8, rbp
0x180011f5b  mov     r9d, r14d
0x180011f5e  mov     rdx, rdi
0x180011f61  mov     rcx, rdi
0x180011f64  call    GaSpecificConfig_Parse
0x180011f69  mov     ebx, eax
0x180011f6b  test    eax, eax
0x180011f6d  jnz     loc_180011EDE
0x180011f73  mov     r15d, [rdi]
0x180011f76  mov     ecx, [rdi+4B0h]
0x180011f7c  mov     edx, ecx
0x180011f7e  sub     edx, 2
0x180011f81  jz      short loc_180011F9B
0x180011f83  sub     edx, 4
0x180011f86  jz      short loc_180011F9B
0x180011f88  sub     edx, 0Bh
0x180011f8b  jz      short loc_180011F9B
0x180011f8d  sub     edx, 3
0x180011f90  jz      short loc_180011F9B
0x180011f92  sub     edx, 2
0x180011f95  jnz     loc_18001203F
0x180011f9b  neg     r15d
0x180011f9e  sbb     eax, eax
0x180011fa0  and     eax, 0FFFFFFC0h
0x180011fa3  add     eax, 400h
0x180011fa8  mov     [rdi+4B8h], eax
0x180011fae  sub     ecx, 11h
0x180011fb1  jz      loc_18001205B
0x180011fb7  sub     ecx, 3
0x180011fba  jz      loc_18001205B
0x180011fc0  sub     ecx, 2
0x180011fc3  jz      loc_18001205B
0x180011fc9  sub     ecx, 1
0x180011fcc  jz      loc_18001205B
0x180011fd2  sub     ecx, 1
0x180011fd5  jz      loc_18001205B
0x180011fdb  sub     ecx, 1
0x180011fde  jz      short loc_18001205B
0x180011fe0  cmp     ecx, 0Eh
0x180011fe3  jz      short loc_18001205B
0x180011fe5  cmp     [rsp+98h+arg_10], 0
0x180011fed  jz      short loc_180012012
0x180011fef  mov     eax, [rdi+4B0h]
0x180011ff5  cmp     eax, 2
0x180011ff8  jnz     loc_18001220A
0x180011ffe  mov     r8, r13
0x180012001  mov     rdx, rbp
0x180012004  mov     rcx, rdi
0x180012007  call    AudioSpecificConfig_ExtensionParse
0x18001200c  mov     ebx, eax
0x18001200e  test    eax, eax
0x180012010  jnz     short loc_18001201F
0x180012012  cmp     dword ptr [rdi+4B0h], 2Ah ; '*'
0x180012019  jz      loc_18001221B
0x18001201f  mov     eax, ebx
0x180012021  jmp     loc_180011EDE
0x180012026  mov     [rdi+4B0h], eax
0x18001202c  lea     rsi, [rdi+4CDh]
0x180012033  lea     rbx, [rdi+4C8h]
0x18001203a  jmp     loc_180011F29
0x18001203f  cmp     edx, 1
0x180012042  jnz     loc_180011FAE
0x180012048  neg     r15d
0x18001204b  sbb     eax, eax
0x18001204d  and     eax, 0FFFFFFE0h
0x180012050  add     eax, 200h
0x180012055  mov     [rdi+4B8h], eax
0x18001205b  mov     edx, 2
0x180012060  mov     rcx, rbp
0x180012063  call    CDKreadBits
0x180012068  mov     [rdi+4C9h], al
0x18001206e  cmp     al, 1
0x180012070  jg      loc_180011ED9
0x180012076  jmp     loc_180011FE5
0x18001207b  mov     dword ptr [rdi+4C0h], 5
0x180012085  mov     byte ptr [rsi], 1
0x180012088  cmp     ecx, 1Dh
0x18001208b  jnz     short loc_180012094
0x18001208d  mov     byte ptr [rdi+4CEh], 1
0x180012094  lea     rdx, [rdi+4D0h]
0x18001209b  mov     r8d, 4
0x1800120a1  mov     rcx, rbp
0x1800120a4  call    getSampleRate
0x1800120a9  mov     [rdi+4C4h], eax
0x1800120af  dec     eax
0x1800120b1  cmp     eax, 176FFh
0x1800120b6  ja      short loc_1800120EE
0x1800120b8  mov     rcx, rbp
0x1800120bb  call    getAOT
0x1800120c0  mov     [rdi+4B0h], eax
0x1800120c6  cmp     eax, 2
0x1800120c9  jz      loc_180011F29
0x1800120cf  cmp     eax, 16h
0x1800120d2  jnz     loc_180011ED9
0x1800120d8  lea     edx, [rax-12h]
0x1800120db  mov     rcx, rbp
0x1800120de  call    CDKreadBits
0x1800120e3  mov     [rdi+4D1h], al
0x1800120e9  jmp     loc_180011F29
0x1800120ee  mov     eax, 401h
0x1800120f3  jmp     loc_180011EDE
0x1800120f8  cmp     eax, 5DC00h
0x1800120fd  jmp     loc_180011EA1
0x180012102  cmp     ecx, 2
0x180012105  jnz     loc_180011EC8
0x18001210b  mov     byte ptr [rbx], 1Fh
0x18001210e  jmp     loc_180011EFC
0x180012113  cmp     ecx, 27h ; '''
0x180012116  ja      loc_180011EFC
0x18001211c  mov     rdx, 80009A0000h
0x180012126  bt      rdx, rcx
0x18001212a  jb      loc_180011ED9
0x180012130  jmp     loc_180011EFC
0x180012135  sub     ecx, 1
0x180012138  jz      loc_180011F50
0x18001213e  sub     ecx, 7
0x180012141  jz      short loc_1800121A1
0x180012143  sub     ecx, 9
0x180012146  jz      short loc_18001216E
0x180012148  cmp     ecx, 3
0x18001214b  jnz     loc_180011ED9
0x180012151  mov     r8, r13
0x180012154  mov     rdx, rbp
0x180012157  mov     rcx, rdi
0x18001215a  call    UsacConfig_Parse
0x18001215f  mov     ebx, eax
0x180012161  test    eax, eax
0x180012163  jz      loc_1800121FD
0x180012169  jmp     loc_180011EDE
0x18001216e  mov     r8, r13
0x180012171  mov     rdx, rbp
0x180012174  mov     rcx, rdi
0x180012177  call    EldSpecificConfig_Parse
0x18001217c  mov     ebx, eax
0x18001217e  test    eax, eax
0x180012180  jnz     loc_180011EDE
0x180012186  mov     al, [rdi+1]
0x180012189  movzx   r15d, byte ptr [rdi]
0x18001218d  mov     [rsi], al
0x18001218f  movzx   eax, byte ptr [rdi+3]
0x180012193  inc     eax
0x180012195  imul    eax, [r14]
0x180012199  mov     [rdi+4C4h], eax
0x18001219f  jmp     short loc_1800121FD
0x1800121a1  mov     rax, [r13+40h]
0x1800121a5  test    rax, rax
0x1800121a8  jz      loc_180011ED9
0x1800121ae  mov     cl, [rdi+4D2h]
0x1800121b4  movsx   edx, byte ptr [rbx]
0x1800121b7  mov     r9d, [r14]
0x1800121ba  mov     [rsp+98h+var_48], r12
0x1800121bf  mov     [rsp+98h+var_50], cl
0x1800121c3  mov     ecx, [rdi+4B8h]
0x1800121c9  mov     [rsp+98h+var_58], 0
0x1800121d1  mov     [rsp+98h+var_60], r15d
0x1800121d6  mov     [rsp+98h+var_68], 1
0x1800121de  mov     [rsp+98h+var_70], edx
0x1800121e2  mov     rdx, rbp
0x1800121e5  mov     [rsp+98h+var_78], ecx
0x1800121e9  mov     rcx, [r13+48h]
0x1800121ed  call    cs:__guard_dispatch_icall_fptr
0x1800121f3  test    eax, eax
0x1800121f5  jnz     loc_180011ED9
0x1800121fb  xor     ebx, ebx
0x1800121fd  mov     r14d, [rsp+98h+arg_0]
0x180012205  jmp     loc_180011F76
0x18001220a  add     eax, 0FFFFFFEAh
0x18001220d  cmp     eax, 1
0x180012210  ja      loc_180012012
0x180012216  jmp     loc_180011FFE
0x18001221b  mov     rcx, rbp
0x18001221e  call    CDKsyncCache_0
0x180012223  mov     esi, [rbp+8]
0x180012226  lea     r8, [rdi+4D6h]
0x18001222d  sub     esi, r14d
0x180012230  mov     rcx, rbp
0x180012233  mov     edx, esi
0x180012235  call    StoreConfigAsBitstream
0x18001223a  test    eax, eax
0x18001223c  jnz     loc_1800120EE
0x180012242  mov     eax, esi
0x180012244  shr     eax, 1Fh
0x180012247  sub     esi, eax
0x180012249  mov     eax, esi
0x18001224b  sar     eax, 1Fh
0x18001224e  xor     eax, esi
0x180012250  mov     [rdi+6D8h], eax
0x180012256  jmp     loc_18001201F
```
