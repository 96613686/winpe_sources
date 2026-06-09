# AipCollectImageProperties

- ea: `0x1800061c8`
- end: `0x180006731`
- name: `AipCollectImageProperties`
- size: `1385`
- prototype: `__int64 __fastcall(__int64, _DWORD *, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002ce0`

## callees

- `0x18000423c`
- `0x180004584`
- `0x180004980`
- `0x180004ca0`
- `0x180005e84`
- `0x180006068`
- `0x1800061c8`
- `0x1800068a8`
- `0x180006928`
- `0x180006994`
- `0x180006a08`
- `0x180006f08`
- `0x1800074a0`
- `0x18000890c`
- `0x1800095c0`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x1800063b8`
- `ntdll!NtQueryInformationFile` at `0x1800063b8`

## pseudocode

```c
__int64 __fastcall AipCollectImageProperties(__int64 a1, _DWORD *a2, __int64 a3, _QWORD *a4)
{
  char v4; // al
  void *v6; // rcx
  int FullImagePath; // edi
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // rcx
  _QWORD *v13; // rcx
  unsigned int i; // edi
  void *v15; // rcx
  NTSTATUS v16; // eax
  int v17; // edx
  int v18; // r8d
  int ImageVersionInfo; // eax
  __int64 v20; // r8
  int v21; // r9d
  unsigned int v22; // esi
  char *v23; // r10
  unsigned int v24; // esi
  __int64 v25; // rdx
  __int64 v26; // rcx
  void *FileInformationClass; // [rsp+20h] [rbp-99h]
  __int64 v29; // [rsp+50h] [rbp-69h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-61h] BYREF
  __int128 FileInformation; // [rsp+68h] [rbp-51h] BYREF
  __int64 v32; // [rsp+78h] [rbp-41h]
  _BYTE v33[80]; // [rsp+80h] [rbp-39h] BYREF

  v4 = 0;
  v32 = 0;
  v29 = 0;
  v6 = *(void **)(a1 + 8);
  FileInformation = 0;
  IoStatusBlock = 0;
  if ( v6 )
  {
    FullImagePath = AiGetFullImagePath(v6, (__int64)&v29, (__int64)&v29 + 4);
    if ( FullImagePath < 0 )
      return (unsigned int)FullImagePath;
    v4 = BYTE4(v29);
    if ( (v29 & 0x400000000LL) != 0 || (_DWORD)v29 == 2 || (_DWORD)v29 == 51 )
      *(_DWORD *)(a1 + 80) = 1;
  }
  if ( *a2 )
  {
    if ( (v4 & 0x10) == 0 )
    {
      if ( *(_QWORD *)(a1 + 64) )
      {
        FullImagePath = AiGetVolumeInfo(a1 + 56, a1 + 40, a1 + 84);
        if ( FullImagePath < 0 )
          return (unsigned int)FullImagePath;
      }
    }
    FullImagePath = AiInitializeSoftwarePathMacroList();
    if ( FullImagePath < 0 )
      return (unsigned int)FullImagePath;
    FullImagePath = AiConvertFullImagePathToMacroFormat(
                      a1,
                      a1 + 24,
                      *(_QWORD *)a1,
                      a1 + 40,
                      a1 + 56,
                      *(_DWORD *)(a1 + 80),
                      *(_DWORD *)(a1 + 84));
    if ( FullImagePath < 0 )
      return (unsigned int)FullImagePath;
    if ( a4 )
    {
      v11 = *(unsigned int *)(a1 + 644);
      if ( (unsigned int)v11 >= 5 )
        return (unsigned int)-2147483643;
      v12 = 5 * (v11 + 11);
      *(_DWORD *)(a1 + 644) = v11 + 1;
      *(_OWORD *)(a1 + 8 * v12) = *(_OWORD *)&qword_18000B0B8;
      *(_WORD *)(a1 + 8 * v12 + 16) = 3;
      *(_DWORD *)(a1 + 8 * v12 + 24) = *(_DWORD *)(a1 + 92);
      *(_QWORD *)(a1 + 8 * v12 + 32) = *(_QWORD *)(a1 + 104);
      *(_DWORD *)(a1 + 8 * v12 + 20) = 2;
    }
    v13 = WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      for ( i = 0; i < *(_DWORD *)(a1 + 92); ++i )
      {
        if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 0x10) != 0 )
        {
          WPP_SF_Z(v13[2], 10, v10, *(_QWORD *)(a1 + 104) + 16LL * i);
          v13 = WPP_GLOBAL_Control;
        }
      }
    }
  }
  v15 = *(void **)(a1 + 8);
  if ( !v15 )
  {
    FullImagePath = 0;
    *(_DWORD *)(a1 + 176) = -2;
    *(_DWORD *)(a1 + 336) = -2;
    *(_DWORD *)(a1 + 396) = -2;
LABEL_74:
    if ( a4 )
      *a4 = a1 + 640;
    v26 = 0;
    a2[1] = *(_DWORD *)(a1 + 396) >= 0;
    do
      a2[v26++ + 3] &= *(_DWORD *)(a1 + 176) >= 0;
    while ( v26 != 3 );
    return (unsigned int)FullImagePath;
  }
  v16 = NtQueryInformationFile(v15, &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation);
  v18 = DWORD2(FileInformation);
  FullImagePath = v16;
  *(_QWORD *)(a1 + 72) = *((_QWORD *)&FileInformation + 1);
  if ( v16 < 0 )
    return (unsigned int)FullImagePath;
  ImageVersionInfo = AiComputeImageHashWithOffset(*(_QWORD *)(a1 + 8), v17, v18, (int)a2 + 12, a1 + 180, a1 + 276);
  *(_DWORD *)(a1 + 176) = ImageVersionInfo;
  if ( ImageVersionInfo < 0 )
    return (unsigned int)ImageVersionInfo;
  if ( a4 )
  {
    v22 = 0;
    do
    {
      if ( a2[v22 + 3] )
      {
        FullImagePath = AipAddHashAttribute(a1, v22);
        if ( FullImagePath < 0 )
          return (unsigned int)FullImagePath;
      }
    }
    while ( ++v22 < 3 );
  }
  v23 = (char *)WPP_GLOBAL_Control;
  if ( *(_DWORD *)(a1 + 280) == 20 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
  {
    v24 = 0;
    do
    {
      RtlStringCbPrintfA(&v33[2 * v24], 65LL - 2 * v24, "%2.2x", *(unsigned __int8 *)(v24 + a1 + 212));
      ++v24;
    }
    while ( v24 < *(_DWORD *)(a1 + 280) );
    v23 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v25, v20, v33);
      v23 = (char *)WPP_GLOBAL_Control;
    }
  }
  if ( a2[1] )
  {
    if ( !*(_BYTE *)(a1 + 392) )
    {
      *(_DWORD *)(a1 + 396) = AiGetTrustedPublisherName(
                                *(_QWORD *)(a1 + 8),
                                *(_QWORD *)(a1 + 16),
                                v20,
                                v21,
                                FileInformationClass,
                                (PUNICODE_STRING)(a1 + 400));
      v23 = (char *)WPP_GLOBAL_Control;
    }
    ImageVersionInfo = *(_DWORD *)(a1 + 396);
    if ( ImageVersionInfo < 0 )
    {
      if ( ImageVersionInfo != -2 )
        return (unsigned int)ImageVersionInfo;
    }
    else if ( v23 != (char *)&WPP_GLOBAL_Control && v23[28] < 0 )
    {
      WPP_SF_Z(*((_QWORD *)v23 + 2), 12, v20, a1 + 400);
      v23 = (char *)WPP_GLOBAL_Control;
    }
    if ( a2[1] && *(int *)(a1 + 396) >= 0 )
      goto LABEL_51;
  }
  if ( a2[2] )
  {
LABEL_51:
    if ( *(int *)(a1 + 336) < 0 )
    {
      ImageVersionInfo = AiGetImageVersionInfo(*(HANDLE *)(a1 + 8), a1 + 344, a1 + 348, a1 + 352, a1 + 360, a1 + 376);
      *(_DWORD *)(a1 + 336) = ImageVersionInfo;
      if ( ImageVersionInfo < 0 )
      {
        if ( ImageVersionInfo != -2 )
          return (unsigned int)ImageVersionInfo;
        goto LABEL_70;
      }
      v23 = (char *)WPP_GLOBAL_Control;
    }
    if ( *(_QWORD *)(a1 + 368) && v23 != (char *)&WPP_GLOBAL_Control && (v23[28] & 0x40) != 0 )
    {
      WPP_SF_Z(*((_QWORD *)v23 + 2), 13, v20, a1 + 360);
      v23 = (char *)WPP_GLOBAL_Control;
    }
    if ( *(_QWORD *)(a1 + 384) )
    {
      if ( v23 == (char *)&WPP_GLOBAL_Control )
        goto LABEL_70;
      if ( (v23[28] & 0x40) != 0 )
      {
        WPP_SF_Z(*((_QWORD *)v23 + 2), 14, v20, a1 + 376);
        v23 = (char *)WPP_GLOBAL_Control;
      }
    }
    if ( v23 != (char *)&WPP_GLOBAL_Control )
    {
      if ( (v23[28] & 0x40) != 0 )
      {
        WPP_SF_DDDD(
          *((_QWORD *)v23 + 2),
          15,
          HIWORD(*(_DWORD *)(a1 + 344)),
          HIWORD(*(_DWORD *)(a1 + 340)),
          (unsigned __int16)*(_DWORD *)(a1 + 340),
          HIWORD(*(_DWORD *)(a1 + 344)),
          (unsigned __int16)*(_DWORD *)(a1 + 344));
        v23 = (char *)WPP_GLOBAL_Control;
      }
      if ( v23 != (char *)&WPP_GLOBAL_Control && (v23[28] & 0x40) != 0 )
        WPP_SF_DDDD(
          *((_QWORD *)v23 + 2),
          16,
          HIWORD(*(_DWORD *)(a1 + 352)),
          HIWORD(*(_DWORD *)(a1 + 348)),
          (unsigned __int16)*(_DWORD *)(a1 + 348),
          HIWORD(*(_DWORD *)(a1 + 352)),
          (unsigned __int16)*(_DWORD *)(a1 + 352));
    }
  }
LABEL_70:
  if ( a4 && a2[1] )
    FullImagePath = AipAddFQBNAttribute(a1);
  if ( FullImagePath >= 0 )
    goto LABEL_74;
  return (unsigned int)FullImagePath;
}

```

## disassembly

```asm
0x1800061c8  mov     [rsp-8+arg_10], rbx
0x1800061cd  push    rbp
0x1800061ce  push    rsi
0x1800061cf  push    rdi
0x1800061d0  push    r12
0x1800061d2  push    r13
0x1800061d4  push    r14
0x1800061d6  push    r15
0x1800061d8  lea     rbp, [rsp-27h]
0x1800061dd  sub     rsp, 0E0h
0x1800061e4  mov     rax, cs:__security_cookie
0x1800061eb  xor     rax, rsp
0x1800061ee  mov     [rbp+57h+var_40], rax
0x1800061f2  xor     eax, eax
0x1800061f4  xor     r13d, r13d
0x1800061f7  xorps   xmm0, xmm0
0x1800061fa  mov     [rbp+57h+var_98], rax
0x1800061fe  mov     rbx, rcx
0x180006201  mov     dword ptr [rbp+57h+var_C0], r13d
0x180006205  mov     rcx, [rcx+8]; FileHandle
0x180006209  mov     r12, r9
0x18000620c  mov     dword ptr [rbp+57h+var_C0+4], eax
0x18000620f  mov     r14, rdx
0x180006212  movups  [rbp+57h+FileInformation], xmm0
0x180006216  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18000621a  test    rcx, rcx
0x18000621d  jz      short loc_180006266
0x18000621f  lea     rax, [rbp+57h+var_C0+4]
0x180006223  mov     [rsp+110h+DestinationString], rax; __int64
0x180006228  lea     r9, [rbx+38h]
0x18000622c  lea     rax, [rbp+57h+var_C0]
0x180006230  lea     r8, [rbx+18h]
0x180006234  mov     qword ptr [rsp+110h+FileInformationClass], rax; __int64
0x180006239  lea     rdx, [rbx+10h]
0x18000623d  call    AiGetFullImagePath
0x180006242  mov     edi, eax
0x180006244  test    eax, eax
0x180006246  js      loc_180006708
0x18000624c  mov     eax, dword ptr [rbp+57h+var_C0+4]
0x18000624f  test    al, 4
0x180006251  jnz     short loc_18000625F
0x180006253  cmp     dword ptr [rbp+57h+var_C0], 2
0x180006257  jz      short loc_18000625F
0x180006259  cmp     dword ptr [rbp+57h+var_C0], 33h ; '3'
0x18000625d  jnz     short loc_180006266
0x18000625f  mov     dword ptr [rbx+50h], 1
0x180006266  lea     r15, WPP_GLOBAL_Control
0x18000626d  cmp     [r14], r13d
0x180006270  jz      loc_18000637C
0x180006276  test    al, 10h
0x180006278  jnz     short loc_18000629B
0x18000627a  cmp     [rbx+40h], r13
0x18000627e  jz      short loc_18000629B
0x180006280  lea     r8, [rbx+54h]
0x180006284  lea     rdx, [rbx+28h]
0x180006288  lea     rcx, [rbx+38h]
0x18000628c  call    AiGetVolumeInfo
0x180006291  mov     edi, eax
0x180006293  test    eax, eax
0x180006295  js      loc_180006708
0x18000629b  call    AiInitializeSoftwarePathMacroList
0x1800062a0  mov     edi, eax
0x1800062a2  test    eax, eax
0x1800062a4  js      loc_180006708
0x1800062aa  mov     eax, [rbx+54h]
0x1800062ad  lea     rcx, [rbx+38h]
0x1800062b1  mov     r8, [rbx]
0x1800062b4  lea     r9, [rbx+28h]
0x1800062b8  mov     dword ptr [rsp+110h+var_E0], eax
0x1800062bc  lea     rdx, [rbx+18h]
0x1800062c0  mov     eax, [rbx+50h]
0x1800062c3  mov     dword ptr [rsp+110h+DestinationString], eax
0x1800062c7  mov     qword ptr [rsp+110h+FileInformationClass], rcx
0x1800062cc  mov     rcx, rbx
0x1800062cf  call    AiConvertFullImagePathToMacroFormat
0x1800062d4  mov     edi, eax
0x1800062d6  test    eax, eax
0x1800062d8  js      loc_180006708
0x1800062de  test    r12, r12
0x1800062e1  jz      short loc_180006334
0x1800062e3  mov     edx, [rbx+284h]
0x1800062e9  cmp     edx, 5
0x1800062ec  jb      short loc_1800062F8
0x1800062ee  mov     edi, 80000005h
0x1800062f3  jmp     loc_180006708
0x1800062f8  movups  xmm0, xmmword ptr cs:qword_18000B0B8
0x1800062ff  lea     rax, [rdx+0Bh]
0x180006303  lea     rcx, [rax+rax*4]
0x180006307  lea     eax, [rdx+1]
0x18000630a  mov     [rbx+284h], eax
0x180006310  movdqu  xmmword ptr [rbx+rcx*8], xmm0
0x180006315  mov     word ptr [rbx+rcx*8+10h], 3
0x18000631c  mov     eax, [rbx+5Ch]
0x18000631f  mov     [rbx+rcx*8+18h], eax
0x180006323  mov     rax, [rbx+68h]
0x180006327  mov     [rbx+rcx*8+20h], rax
0x18000632c  mov     dword ptr [rbx+rcx*8+14h], 2
0x180006334  mov     rcx, cs:WPP_GLOBAL_Control
0x18000633b  test    byte ptr [rcx+1Ch], 10h
0x18000633f  jz      short loc_18000637C
0x180006341  mov     edi, r13d
0x180006344  cmp     [rbx+5Ch], r13d
0x180006348  jbe     short loc_18000637C
0x18000634a  cmp     rcx, r15
0x18000634d  jz      short loc_180006375
0x18000634f  test    byte ptr [rcx+1Ch], 10h
0x180006353  jz      short loc_180006375
0x180006355  mov     rcx, [rcx+10h]
0x180006359  mov     edx, 0Ah
0x18000635e  mov     r9d, edi
0x180006361  shl     r9, 4
0x180006365  add     r9, [rbx+68h]
0x180006369  call    WPP_SF_Z
0x18000636e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006375  inc     edi
0x180006377  cmp     edi, [rbx+5Ch]
0x18000637a  jb      short loc_18000634A
0x18000637c  mov     rcx, [rbx+8]; FileHandle
0x180006380  test    rcx, rcx
0x180006383  jnz     short loc_1800063A2
0x180006385  lea     esi, [rcx-2]
0x180006388  mov     edi, r13d
0x18000638b  mov     [rbx+0B0h], esi
0x180006391  mov     [rbx+150h], esi
0x180006397  mov     [rbx+18Ch], esi
0x18000639d  jmp     loc_1800066CD
0x1800063a2  mov     r9d, 18h; Length
0x1800063a8  mov     [rsp+110h+FileInformationClass], 5; FileInformationClass
0x1800063b0  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x1800063b4  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800063b8  call    cs:__imp_NtQueryInformationFile
0x1800063be  mov     r8, qword ptr [rbp+57h+FileInformation+8]
0x1800063c2  mov     edi, eax
0x1800063c4  mov     [rbx+48h], r8
0x1800063c8  test    eax, eax
0x1800063ca  js      loc_180006708
0x1800063d0  lea     rax, [rbx+114h]
0x1800063d7  lea     rcx, [rbx+0B4h]
0x1800063de  mov     [rsp+110h+DestinationString], rax
0x1800063e3  mov     qword ptr [rsp+110h+FileInformationClass], rcx; hStateData
0x1800063e8  lea     r9, [r14+0Ch]
0x1800063ec  mov     rcx, [rbx+8]
0x1800063f0  call    AiComputeImageHashWithOffset
0x1800063f5  mov     [rbx+0B0h], eax
0x1800063fb  test    eax, eax
0x1800063fd  jns     short loc_180006406
0x1800063ff  mov     edi, eax
0x180006401  jmp     loc_180006708
0x180006406  test    r12, r12
0x180006409  jz      short loc_180006432
0x18000640b  mov     esi, r13d
0x18000640e  mov     eax, esi
0x180006410  cmp     [r14+rax*4+0Ch], r13d
0x180006415  jz      short loc_18000642B
0x180006417  mov     edx, esi
0x180006419  mov     rcx, rbx
0x18000641c  call    AipAddHashAttribute
0x180006421  mov     edi, eax
0x180006423  test    eax, eax
0x180006425  js      loc_180006708
0x18000642b  inc     esi
0x18000642d  cmp     esi, 3
0x180006430  jb      short loc_18000640E
0x180006432  cmp     dword ptr [rbx+118h], 14h
0x180006439  mov     r10, cs:WPP_GLOBAL_Control
0x180006440  jnz     short loc_1800064A6
0x180006442  test    byte ptr [r10+1Ch], 20h
0x180006447  jz      short loc_1800064A6
0x180006449  mov     esi, r13d
0x18000644c  mov     eax, esi
0x18000644e  lea     ecx, [rsi+rsi]
0x180006451  mov     edx, 41h ; 'A'
0x180006456  lea     r8, a22x; "%2.2x"
0x18000645d  sub     rdx, rcx
0x180006460  movzx   r9d, byte ptr [rax+rbx+0D4h]
0x180006469  lea     rax, [rbp+57h+var_90]
0x18000646d  add     rcx, rax
0x180006470  call    RtlStringCbPrintfA
0x180006475  inc     esi
0x180006477  cmp     esi, [rbx+118h]
0x18000647d  jb      short loc_18000644C
0x18000647f  mov     r10, cs:WPP_GLOBAL_Control
0x180006486  cmp     r10, r15
0x180006489  jz      short loc_1800064A6
0x18000648b  test    byte ptr [r10+1Ch], 20h
0x180006490  jz      short loc_1800064A6
0x180006492  mov     rcx, [r10+10h]
0x180006496  lea     r9, [rbp+57h+var_90]
0x18000649a  call    WPP_SF_s
0x18000649f  mov     r10, cs:WPP_GLOBAL_Control
0x1800064a6  mov     esi, 0FFFFFFFEh
0x1800064ab  cmp     [r14+4], r13d
0x1800064af  jz      loc_180006539
0x1800064b5  lea     r15, [rbx+190h]
0x1800064bc  cmp     [rbx+188h], r13b
0x1800064c3  jnz     short loc_1800064E4
0x1800064c5  mov     rdx, [rbx+10h]; int
0x1800064c9  mov     rcx, [rbx+8]; int
0x1800064cd  mov     [rsp+110h+DestinationString], r15; DestinationString
0x1800064d2  call    AiGetTrustedPublisherName
0x1800064d7  mov     [rbx+18Ch], eax
0x1800064dd  mov     r10, cs:WPP_GLOBAL_Control
0x1800064e4  mov     eax, [rbx+18Ch]
0x1800064ea  test    eax, eax
0x1800064ec  js      short loc_18000651B
0x1800064ee  lea     rax, WPP_GLOBAL_Control
0x1800064f5  cmp     r10, rax
0x1800064f8  jz      short loc_180006523
0x1800064fa  test    byte ptr [r10+1Ch], 80h
0x1800064ff  jz      short loc_180006523
0x180006501  mov     rcx, [r10+10h]
0x180006505  mov     edx, 0Ch
0x18000650a  mov     r9, r15
0x18000650d  call    WPP_SF_Z
0x180006512  mov     r10, cs:WPP_GLOBAL_Control
0x180006519  jmp     short loc_180006523
0x18000651b  cmp     eax, esi
0x18000651d  jnz     loc_1800063FF
0x180006523  lea     r15, WPP_GLOBAL_Control
0x18000652a  cmp     [r14+4], r13d
0x18000652e  jz      short loc_180006539
0x180006530  cmp     [rbx+18Ch], r13d
0x180006537  jge     short loc_180006543
0x180006539  cmp     [r14+8], r13d
0x18000653d  jz      loc_1800066B4
0x180006543  cmp     [rbx+150h], r13d
0x18000654a  jge     short loc_1800065BA
0x18000654c  lea     rax, [rbx+178h]
0x180006553  mov     [rsp+110h+var_D0], rax; __int64
0x180006558  lea     rcx, [rbx+168h]
0x18000655f  mov     [rsp+110h+var_D8], rcx; __int64
0x180006564  lea     rdx, [rbx+160h]
0x18000656b  mov     rcx, [rbx+8]; FileHandle
0x18000656f  lea     r8, [rbx+15Ch]
0x180006576  mov     [rsp+110h+var_E0], rdx; __int64
0x18000657b  lea     r10, [rbx+158h]
0x180006582  mov     [rsp+110h+DestinationString], r8; __int64
0x180006587  lea     r9, [rbx+154h]
0x18000658e  mov     r8, [rbx+10h]
0x180006592  mov     qword ptr [rsp+110h+FileInformationClass], r10; __int64
0x180006597  call    AiGetImageVersionInfo
0x18000659c  mov     [rbx+150h], eax
0x1800065a2  test    eax, eax
0x1800065a4  jns     short loc_1800065B3
0x1800065a6  cmp     eax, esi
0x1800065a8  jz      loc_1800066B4
0x1800065ae  jmp     loc_1800063FF
0x1800065b3  mov     r10, cs:WPP_GLOBAL_Control
0x1800065ba  mov     sil, 40h ; '@'
0x1800065bd  cmp     [rbx+170h], r13
0x1800065c4  jz      short loc_1800065ED
0x1800065c6  cmp     r10, r15
0x1800065c9  jz      short loc_1800065ED
0x1800065cb  test    [r10+1Ch], sil
0x1800065cf  jz      short loc_1800065ED
0x1800065d1  mov     rcx, [r10+10h]
0x1800065d5  lea     r9, [rbx+168h]
0x1800065dc  mov     edx, 0Dh
0x1800065e1  call    WPP_SF_Z
0x1800065e6  mov     r10, cs:WPP_GLOBAL_Control
0x1800065ed  cmp     [rbx+180h], r13
0x1800065f4  jz      short loc_180006621
0x1800065f6  cmp     r10, r15
0x1800065f9  jz      loc_1800066B4
0x1800065ff  test    [r10+1Ch], sil
0x180006603  jz      short loc_180006621
0x180006605  mov     rcx, [r10+10h]
0x180006609  lea     r9, [rbx+178h]
0x180006610  mov     edx, 0Eh
0x180006615  call    WPP_SF_Z
0x18000661a  mov     r10, cs:WPP_GLOBAL_Control
0x180006621  cmp     r10, r15
0x180006624  jz      loc_1800066B4
0x18000662a  test    [r10+1Ch], sil
0x18000662e  jz      short loc_180006670
0x180006630  mov     r8d, [rbx+158h]
0x180006637  mov     edx, 0Fh
0x18000663c  mov     r9d, [rbx+154h]
0x180006643  movzx   ecx, r8w
0x180006647  mov     dword ptr [rsp+110h+var_E0], ecx
0x18000664b  mov     rcx, [r10+10h]
0x18000664f  movzx   eax, r9w
0x180006653  shr     r8d, 10h
0x180006657  mov     dword ptr [rsp+110h+DestinationString], r8d
0x18000665c  shr     r9d, 10h
0x180006660  mov     [rsp+110h+FileInformationClass], eax
0x180006664  call    WPP_SF_DDDD
0x180006669  mov     r10, cs:WPP_GLOBAL_Control
0x180006670  cmp     r10, r15
0x180006673  jz      short loc_1800066B4
0x180006675  test    [r10+1Ch], sil
0x180006679  jz      short loc_1800066B4
0x18000667b  mov     r8d, [rbx+160h]
0x180006682  mov     edx, 10h
0x180006687  mov     r9d, [rbx+15Ch]
0x18000668e  movzx   ecx, r8w
0x180006692  mov     dword ptr [rsp+110h+var_E0], ecx
0x180006696  mov     rcx, [r10+10h]
0x18000669a  movzx   eax, r9w
0x18000669e  shr     r8d, 10h
  ... truncated ...
```
