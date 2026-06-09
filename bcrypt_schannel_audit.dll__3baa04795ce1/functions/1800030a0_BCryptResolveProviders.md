# BCryptResolveProviders

- ea: `0x1800030a0`
- end: `0x18000384b`
- name: `BCryptResolveProviders`
- size: `1963`
- prototype: `NTSTATUS __stdcall(LPCWSTR pszContext, ULONG dwInterface, LPCWSTR pszFunction, LPCWSTR pszProvider, ULONG dwMode, ULONG dwFlags, ULONG *pcbBuffer, PCRYPT_PROVIDER_REFS *ppBuffer)`
- caller_count: `4`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180001590`
- `0x180002de0`
- `0x18000466c`
- `0x180014990`

## callees

- `0x180002040`
- `0x1800022cc`
- `0x1800030a0`
- `0x180003860`
- `0x180003dc0`
- `0x180004120`
- `0x1800041d0`
- `0x180004200`
- `0x18001b79d`
- `0x18001b7e0`

## import_xrefs

- `ntdll!NtDeviceIoControlFile` at `0x180003487`
- `ntdll!NtDeviceIoControlFile` at `0x180003487`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003760`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003760`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000373a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000373a`

## pseudocode

```c
NTSTATUS __stdcall BCryptResolveProviders(
        LPCWSTR pszContext,
        ULONG dwInterface,
        LPCWSTR pszFunction,
        LPCWSTR pszProvider,
        ULONG dwMode,
        ULONG dwFlags,
        ULONG *pcbBuffer,
        PCRYPT_PROVIDER_REFS *ppBuffer)
{
  unsigned __int8 *v11; // r15
  NTSTATUS v12; // ebx
  NTSTATUS v13; // esi
  unsigned int v15; // esi
  unsigned int v16; // ecx
  unsigned __int8 *v17; // r14
  unsigned int v18; // ebx
  unsigned __int8 *v19; // rdi
  _BYTE *v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  ULONG *v23; // r12
  int v24; // r9d
  PCRYPT_PROVIDER_REFS v25; // rdi
  unsigned int v26; // esi
  unsigned __int8 *InputBuffer; // r14
  ULONG OutputBufferLength; // ecx
  NTSTATUS *OutputBuffer; // r12
  NTSTATUS v30; // eax
  unsigned int v31; // r14d
  bool v32; // zf
  PCRYPT_PROVIDER_REFS v33; // rdi
  __int64 v34; // r8
  unsigned __int64 v35; // rdx
  unsigned __int64 rgpProviders; // rcx
  __int64 cProviders; // r12
  unsigned __int64 v38; // r8
  char *v39; // rax
  __int64 j; // r14
  void *v41; // rcx
  unsigned int v42; // esi
  unsigned int i; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int v44; // [rsp+5Ch] [rbp-ACh] BYREF
  ULONG InputBufferLength[2]; // [rsp+60h] [rbp-A8h] BYREF
  ULONG *v46; // [rsp+68h] [rbp-A0h]
  void *IoStatusBlock[3]; // [rsp+70h] [rbp-98h] BYREF
  char Src; // [rsp+88h] [rbp-80h] BYREF
  char v49; // [rsp+90h] [rbp-78h] BYREF
  unsigned __int8 v50[320]; // [rsp+98h] [rbp-70h] BYREF

  v11 = v50;
  v46 = pcbBuffer;
  InputBufferLength[0] = dwInterface;
  if ( dwInterface > 8 && dwInterface - 65537 > 3 || !dwMode || dwMode != 1 && dwMode - 2 > 1 || !pcbBuffer )
  {
    v12 = 87;
    goto LABEL_4;
  }
  if ( (dwFlags & 0xFFFFFFFC) != 0 )
  {
    v12 = 1004;
    goto LABEL_4;
  }
  v15 = 48;
  v16 = 48;
  v44 = 48;
  if ( pszContext )
  {
    v44 = 0;
    v12 = SzString_CchLength(pszContext, &v44, 0);
    if ( v12 )
      goto LABEL_4;
    v16 = ((2 * v44 + 9) & 0xFFFFFFF8) + 48;
    v44 = v16;
  }
  if ( pszFunction )
  {
    i = 0;
    v12 = SzString_CchLength(pszFunction, &i, 0);
    if ( v12 )
      goto LABEL_4;
    v16 = ((2 * i + 9) & 0xFFFFFFF8) + v44;
    v44 = v16;
  }
  if ( pszProvider )
  {
    i = 0;
    v12 = SzString_CchLength(pszProvider, &i, 0);
    if ( v12 )
      goto LABEL_4;
    v16 = ((2 * i + 9) & 0xFFFFFFF8) + v44;
    v44 = v16;
  }
  if ( v16 > 0x140 )
  {
    v11 = (unsigned __int8 *)((__int64 (*)(void))SafeAllocaAllocateFromHeap)();
    if ( !v11 )
    {
      v12 = 8;
      goto LABEL_4;
    }
  }
  if ( pszContext )
  {
    v41 = v11 + 48;
    i = 0;
    if ( !v11 )
      v41 = 0;
    IoStatusBlock[0] = v41;
    v12 = SzString_CchLength(pszContext, &i, 0);
    if ( v12 )
      goto LABEL_4;
    v42 = (2 * i + 9) & 0xFFFFFFF8;
    if ( IoStatusBlock[0] )
      memcpy_0(IoStatusBlock[0], pszContext, 2LL * (i + 1));
    v15 = v42 + 48;
  }
  else
  {
    IoStatusBlock[0] = 0;
  }
  v17 = 0;
  if ( pszFunction )
  {
    if ( v11 )
      v17 = &v11[v15];
    i = 0;
    v12 = SzString_CchLength(pszFunction, &i, 0);
    if ( v12 )
      goto LABEL_4;
    v18 = (2 * i + 9) & 0xFFFFFFF8;
    if ( v17 )
      memcpy_0(v17, pszFunction, 2LL * (i + 1));
    v15 += v18;
  }
  v19 = 0;
  if ( pszProvider )
  {
    if ( v11 )
      v19 = &v11[v15];
    i = 0;
    v12 = SzString_CchLength(pszProvider, &i, 0);
    if ( v12 )
      goto LABEL_4;
    if ( v19 )
      memcpy_0(v19, pszProvider, 2LL * (i + 1));
  }
  if ( v11 )
  {
    v20 = IoStatusBlock[0];
    *((_DWORD *)v11 + 4) = InputBufferLength[0];
    *((_DWORD *)v11 + 10) = dwMode;
    *((_DWORD *)v11 + 11) = dwFlags;
    v21 = v20 - v11;
    if ( !v20 )
      v21 = -1;
    *((_QWORD *)v11 + 1) = v21;
    v22 = v17 - v11;
    if ( !v17 )
      v22 = -1;
    *((_QWORD *)v11 + 3) = v22;
    if ( v19 )
      *((_QWORD *)v11 + 4) = v19 - v11;
    else
      *((_QWORD *)v11 + 4) = -1;
  }
  InputBufferLength[0] = 0;
  if ( !ppBuffer )
  {
    v12 = 0;
    v13 = IoCallKernelDriver(0x20000u, v11, v44, 0, InputBufferLength);
    if ( v13 == -1073741789 )
    {
      v23 = v46;
      v24 = 0;
      *v46 = InputBufferLength[0];
      goto LABEL_64;
    }
    goto LABEL_83;
  }
  v25 = *ppBuffer;
  v12 = 0;
  if ( *ppBuffer )
    v26 = *v46;
  else
    v26 = 384;
  for ( i = v26; ; v26 = i )
  {
    if ( !*ppBuffer )
    {
      if ( v25 )
        BCryptFree(v25);
      v25 = (PCRYPT_PROVIDER_REFS)SafeAllocaAllocateFromHeap(v26);
      if ( !v25 )
      {
        v13 = -1073741801;
LABEL_83:
        v23 = v46;
LABEL_84:
        v24 = 0;
        goto LABEL_64;
      }
    }
    *(_OWORD *)&IoStatusBlock[1] = 0;
    if ( v11 )
    {
      if ( v44 < 8 )
        goto LABEL_125;
      InputBuffer = v11;
      InputBufferLength[0] = v44;
    }
    else
    {
      InputBuffer = (unsigned __int8 *)&v49;
      InputBufferLength[0] = 8;
    }
    *(_DWORD *)InputBuffer = 439041101;
    *((_DWORD *)InputBuffer + 1) = 0x20000;
    if ( v25 && (OutputBufferLength = v26, LODWORD(IoStatusBlock[0]) = v26, v26 >= 8) )
    {
      OutputBuffer = (NTSTATUS *)v25;
    }
    else
    {
      OutputBufferLength = 8;
      OutputBuffer = (NTSTATUS *)&Src;
      LODWORD(IoStatusBlock[0]) = 8;
    }
    if ( !g_hIoDevice )
    {
      v13 = 0;
      EnterCriticalSection(&g_csIoInitialize);
      if ( !g_hIoDevice )
        v13 = _IoOpenDevice();
      LeaveCriticalSection(&g_csIoInitialize);
      if ( v13 < 0 )
        goto LABEL_119;
      OutputBufferLength = (ULONG)IoStatusBlock[0];
      v26 = i;
    }
    v30 = NtDeviceIoControlFile(
            g_hIoDevice,
            0,
            0,
            0,
            (PIO_STATUS_BLOCK)&IoStatusBlock[1],
            0x390400u,
            InputBuffer,
            InputBufferLength[0],
            OutputBuffer,
            OutputBufferLength);
    v31 = (unsigned int)IoStatusBlock[2];
    if ( v30 < 0 )
      break;
    if ( v25 && v26 >= LODWORD(IoStatusBlock[2]) )
    {
      if ( OutputBuffer == (NTSTATUS *)&Src )
        memcpy_0(v25, OutputBuffer, LODWORD(IoStatusBlock[2]));
      v23 = v46;
      v13 = 0;
      *v46 = v31;
      goto LABEL_63;
    }
    v30 = -1073741789;
    i = (unsigned int)IoStatusBlock[2];
    v13 = -1073741789;
LABEL_121:
    if ( *ppBuffer )
      goto LABEL_102;
  }
  if ( v30 == -1073741789 )
    goto LABEL_125;
  if ( v30 == -2147483643 )
  {
    if ( LODWORD(IoStatusBlock[2]) < 4 )
      goto LABEL_125;
    v13 = *OutputBuffer;
    if ( *OutputBuffer == -1073741789 )
    {
      if ( LODWORD(IoStatusBlock[2]) != 8 )
        goto LABEL_125;
      v31 = OutputBuffer[1];
      i = v31;
    }
    else
    {
      if ( LODWORD(IoStatusBlock[2]) != 4 )
      {
LABEL_125:
        v23 = v46;
        v13 = -1073741595;
        *v46 = i;
        goto LABEL_126;
      }
LABEL_119:
      v31 = i;
    }
    v30 = v13;
    if ( v13 != -1073741789 )
      goto LABEL_102;
    goto LABEL_121;
  }
  v31 = i;
  v13 = v30;
LABEL_102:
  v23 = v46;
  *v46 = v31;
  if ( v30 >= 0 )
  {
LABEL_63:
    v32 = *ppBuffer == 0;
    *ppBuffer = v25;
    v24 = v32;
    goto LABEL_64;
  }
LABEL_126:
  if ( !v25 || *ppBuffer )
    goto LABEL_84;
  BCryptFree(v25);
  v24 = 0;
LABEL_64:
  LODWORD(IoStatusBlock[0]) = v24;
  if ( v13 < 0 )
  {
LABEL_90:
    if ( v24 )
    {
      BCryptFree(*ppBuffer);
      *ppBuffer = 0;
    }
    if ( v13 < 0 )
      goto LABEL_5;
LABEL_4:
    v13 = WinErrorToNtStatus(v12);
    goto LABEL_5;
  }
  v33 = *ppBuffer;
  if ( !*ppBuffer )
    goto LABEL_5;
  if ( &v33[1] < v33 )
    goto LABEL_123;
  v34 = *v23;
  InputBufferLength[0] = v34;
  v35 = (unsigned int)v34;
  if ( &v33[1] > (PCRYPT_PROVIDER_REFS)((char *)v33 + v34) )
    goto LABEL_123;
  rgpProviders = (unsigned __int64)v33->rgpProviders;
  cProviders = v33->cProviders;
  if ( rgpProviders == -1 )
  {
    v33->rgpProviders = 0;
    if ( !(_DWORD)cProviders )
    {
      v39 = 0;
      goto LABEL_74;
    }
    goto LABEL_123;
  }
  if ( !(_DWORD)cProviders
    || rgpProviders >= (unsigned int)v34
    || (v38 = rgpProviders + 8 * cProviders, v38 < rgpProviders)
    || v38 > v35 )
  {
LABEL_123:
    v12 = 1359;
    goto LABEL_90;
  }
  v39 = (char *)v33 + rgpProviders;
  LODWORD(v34) = v35;
  v33->rgpProviders = (PCRYPT_PROVIDER_REF *)((char *)v33 + rgpProviders);
LABEL_74:
  if ( v39 )
  {
    for ( j = 0; (unsigned int)j < (unsigned int)cProviders; j = (unsigned int)(j + 1) )
    {
      v12 = IoUnpack_ProviderRef(&v33->rgpProviders[j], (unsigned __int8 *)v33, v34);
      if ( v12 )
      {
        v24 = (int)IoStatusBlock[0];
        goto LABEL_90;
      }
      LODWORD(v34) = InputBufferLength[0];
    }
  }
LABEL_5:
  if ( v11 && v11 != v50 )
    BCryptFree(v11);
  if ( !ppBuffer && v13 == -1073741789 )
    return 0;
  return v13;
}

```

## disassembly

```asm
0x1800030a0  mov     r11, rsp
0x1800030a3  push    rbp
0x1800030a4  push    rsi
0x1800030a5  lea     rbp, [r11-118h]
0x1800030ac  sub     rsp, 208h
0x1800030b3  mov     rax, cs:__security_cookie
0x1800030ba  xor     rax, rsp
0x1800030bd  mov     [rbp+110h+var_40], rax
0x1800030c4  mov     [r11+10h], rbx
0x1800030c8  mov     eax, edx
0x1800030ca  mov     [r11-18h], rdi
0x1800030ce  mov     rdi, r8
0x1800030d1  mov     [r11-20h], r12
0x1800030d5  mov     r12, r9
0x1800030d8  mov     [r11-28h], r13
0x1800030dc  mov     r13, [rbp+110h+ppBuffer]
0x1800030e3  mov     [r11-30h], r14
0x1800030e7  mov     r14, rcx
0x1800030ea  mov     rcx, [rbp+110h+pcbBuffer]
0x1800030f1  mov     [r11-38h], r15
0x1800030f5  lea     r15, [rbp+110h+var_180]
0x1800030f9  mov     [rsp+210h+var_1B0], rcx
0x1800030fe  mov     [rsp+210h+var_1B8], edx
0x180003102  cmp     edx, 8
0x180003105  jbe     loc_18000318E
0x18000310b  add     eax, 0FFFEFFFFh
0x180003110  cmp     eax, 3
0x180003113  jbe     short loc_18000318E
0x180003115  mov     ebx, 57h ; 'W'
0x18000311a  mov     ecx, ebx; Status
0x18000311c  call    ?WinErrorToNtStatus@@YAJK@Z; WinErrorToNtStatus(ulong)
0x180003121  mov     esi, eax
0x180003123  mov     r14, [rsp+210h+var_28]
0x18000312b  mov     r12, [rsp+210h+var_18]
0x180003133  mov     rdi, [rsp+200h]
0x18000313b  mov     rbx, [rsp+210h+arg_8]
0x180003143  test    r15, r15
0x180003146  jz      short loc_180003159
0x180003148  lea     rax, [rbp+110h+var_180]
0x18000314c  cmp     r15, rax
0x18000314f  jz      short loc_180003159
0x180003151  mov     rcx, r15
0x180003154  call    BCryptFree
0x180003159  mov     r15, [rsp+210h+var_30]
0x180003161  test    r13, r13
0x180003164  mov     r13, [rsp+210h+var_20]
0x18000316c  jz      loc_18000383B
0x180003172  mov     eax, esi
0x180003174  mov     rcx, [rbp+110h+var_40]
0x18000317b  xor     rcx, rsp; StackCookie
0x18000317e  call    __security_check_cookie
0x180003183  add     rsp, 208h
0x18000318a  pop     rsi
0x18000318b  pop     rbp
0x18000318c  retn
0x18000318e  mov     eax, [rbp+110h+dwMode]
0x180003194  test    eax, eax
0x180003196  jz      loc_180003115
0x18000319c  sub     eax, 1
0x18000319f  jz      short loc_1800031AF
0x1800031a1  sub     eax, 1
0x1800031a4  jz      short loc_1800031AF
0x1800031a6  cmp     eax, 1
0x1800031a9  jnz     loc_180003115
0x1800031af  test    rcx, rcx
0x1800031b2  jz      loc_180003115
0x1800031b8  test    [rbp+110h+dwFlags], 0FFFFFFFCh
0x1800031c2  jnz     loc_180003811
0x1800031c8  mov     esi, 30h ; '0'
0x1800031cd  mov     ecx, esi
0x1800031cf  mov     [rsp+210h+var_1BC], ecx
0x1800031d3  test    r14, r14
0x1800031d6  jnz     loc_180003697
0x1800031dc  test    rdi, rdi
0x1800031df  jz      short loc_18000321B
0x1800031e1  xor     r8d, r8d; unsigned int
0x1800031e4  mov     [rsp+210h+var_1C0], 0
0x1800031ec  lea     rdx, [rsp+210h+var_1C0]; unsigned int *
0x1800031f1  mov     rcx, rdi; unsigned __int16 *
0x1800031f4  call    ?SzString_CchLength@@YAKPEBGPEAKK@Z; SzString_CchLength(ushort const *,ulong *,ulong)
0x1800031f9  mov     ebx, eax
0x1800031fb  test    eax, eax
0x1800031fd  jnz     loc_18000311A
0x180003203  mov     ecx, [rsp+210h+var_1BC]
0x180003207  mov     eax, [rsp+210h+var_1C0]
0x18000320b  lea     eax, ds:9[rax*2]
0x180003212  and     eax, 0FFFFFFF8h
0x180003215  add     ecx, eax
0x180003217  mov     [rsp+210h+var_1BC], ecx
0x18000321b  test    r12, r12
0x18000321e  jz      short loc_18000325A
0x180003220  xor     r8d, r8d; unsigned int
0x180003223  mov     [rsp+210h+var_1C0], 0
0x18000322b  lea     rdx, [rsp+210h+var_1C0]; unsigned int *
0x180003230  mov     rcx, r12; unsigned __int16 *
0x180003233  call    ?SzString_CchLength@@YAKPEBGPEAKK@Z; SzString_CchLength(ushort const *,ulong *,ulong)
0x180003238  mov     ebx, eax
0x18000323a  test    eax, eax
0x18000323c  jnz     loc_18000311A
0x180003242  mov     ecx, [rsp+210h+var_1BC]
0x180003246  mov     eax, [rsp+210h+var_1C0]
0x18000324a  lea     eax, ds:9[rax*2]
0x180003251  and     eax, 0FFFFFFF8h
0x180003254  add     ecx, eax
0x180003256  mov     [rsp+210h+var_1BC], ecx
0x18000325a  cmp     ecx, 140h
0x180003260  ja      loc_18000377D
0x180003266  test    r14, r14
0x180003269  jnz     loc_1800036D2
0x18000326f  xor     ecx, ecx
0x180003271  mov     qword ptr [rsp+210h+var_1A8], rcx
0x180003276  xor     r14d, r14d
0x180003279  test    rdi, rdi
0x18000327c  jz      short loc_1800032D2
0x18000327e  test    r15, r15
0x180003281  jz      short loc_180003289
0x180003283  mov     r14d, esi
0x180003286  add     r14, r15
0x180003289  xor     r8d, r8d; unsigned int
0x18000328c  mov     [rsp+210h+var_1C0], 0
0x180003294  lea     rdx, [rsp+210h+var_1C0]; unsigned int *
0x180003299  mov     rcx, rdi; unsigned __int16 *
0x18000329c  call    ?SzString_CchLength@@YAKPEBGPEAKK@Z; SzString_CchLength(ushort const *,ulong *,ulong)
0x1800032a1  mov     ebx, eax
0x1800032a3  test    eax, eax
0x1800032a5  jnz     loc_18000311A
0x1800032ab  mov     eax, [rsp+210h+var_1C0]
0x1800032af  lea     ebx, ds:9[rax*2]
0x1800032b6  and     ebx, 0FFFFFFF8h
0x1800032b9  test    r14, r14
0x1800032bc  jz      short loc_1800032D0
0x1800032be  lea     r8d, [rax+1]
0x1800032c2  mov     rdx, rdi; Src
0x1800032c5  add     r8, r8; Size
0x1800032c8  mov     rcx, r14; void *
0x1800032cb  call    memcpy_0
0x1800032d0  add     esi, ebx
0x1800032d2  xor     edi, edi
0x1800032d4  test    r12, r12
0x1800032d7  jz      short loc_18000330E
0x1800032d9  test    r15, r15
0x1800032dc  jz      short loc_1800032E3
0x1800032de  mov     edi, esi
0x1800032e0  add     rdi, r15
0x1800032e3  xor     r8d, r8d; unsigned int
0x1800032e6  mov     [rsp+210h+var_1C0], 0
0x1800032ee  lea     rdx, [rsp+210h+var_1C0]; unsigned int *
0x1800032f3  mov     rcx, r12; unsigned __int16 *
0x1800032f6  call    ?SzString_CchLength@@YAKPEBGPEAKK@Z; SzString_CchLength(ushort const *,ulong *,ulong)
0x1800032fb  mov     ebx, eax
0x1800032fd  test    eax, eax
0x1800032ff  jnz     loc_18000311A
0x180003305  test    rdi, rdi
0x180003308  jnz     loc_1800033BD
0x18000330e  test    r15, r15
0x180003311  jz      short loc_18000336D
0x180003313  mov     eax, [rsp+210h+var_1B8]
0x180003317  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x18000331e  mov     rcx, qword ptr [rsp+210h+var_1A8]
0x180003323  mov     [r15+10h], eax
0x180003327  mov     eax, [rbp+110h+dwMode]
0x18000332d  mov     [r15+28h], eax
0x180003331  mov     eax, [rbp+110h+dwFlags]
0x180003337  mov     [r15+2Ch], eax
0x18000333b  mov     rax, rcx
0x18000333e  sub     rax, r15
0x180003341  test    rcx, rcx
0x180003344  cmovz   rax, rdx
0x180003348  mov     [r15+8], rax
0x18000334c  mov     rax, r14
0x18000334f  sub     rax, r15
0x180003352  test    r14, r14
0x180003355  cmovz   rax, rdx
0x180003359  mov     [r15+18h], rax
0x18000335d  test    rdi, rdi
0x180003360  jz      loc_180003626
0x180003366  sub     rdi, r15
0x180003369  mov     [r15+20h], rdi
0x18000336d  mov     [rsp+210h+var_1B8], 0
0x180003375  test    r13, r13
0x180003378  jnz     short loc_1800033D8
0x18000337a  mov     r8d, [rsp+210h+var_1BC]; unsigned int
0x18000337f  lea     rax, [rsp+210h+var_1B8]
0x180003384  xor     r9d, r9d; unsigned __int8 *
0x180003387  mov     [rsp+210h+IoStatusBlock], rax; unsigned int *
0x18000338c  mov     rdx, r15; unsigned __int8 *
0x18000338f  mov     ecx, 20000h; unsigned int
0x180003394  call    ?IoCallKernelDriver@@YAJKPEAEK0PEAK@Z; IoCallKernelDriver(ulong,uchar *,ulong,uchar *,ulong *)
0x180003399  xor     ebx, ebx
0x18000339b  mov     esi, eax
0x18000339d  cmp     eax, 0C0000023h
0x1800033a2  jnz     loc_1800035C1
0x1800033a8  mov     r12, [rsp+210h+var_1B0]
0x1800033ad  xor     r9d, r9d
0x1800033b0  mov     eax, [rsp+210h+var_1B8]
0x1800033b4  mov     [r12], eax
0x1800033b8  jmp     loc_1800034E3
0x1800033bd  mov     r8d, [rsp+210h+var_1C0]
0x1800033c2  mov     rdx, r12; Src
0x1800033c5  inc     r8d
0x1800033c8  mov     rcx, rdi; void *
0x1800033cb  add     r8, r8; Size
0x1800033ce  call    memcpy_0
0x1800033d3  jmp     loc_18000330E
0x1800033d8  mov     rdi, [r13+0]
0x1800033dc  xor     ebx, ebx
0x1800033de  test    rdi, rdi
0x1800033e1  jz      loc_1800037D1
0x1800033e7  mov     r12, [rsp+210h+var_1B0]
0x1800033ec  mov     esi, [r12]
0x1800033f0  mov     [rsp+210h+var_1C0], esi
0x1800033f4  cmp     [r13+0], rbx
0x1800033f8  jz      loc_18000359C
0x1800033fe  xorps   xmm0, xmm0
0x180003401  movups  xmmword ptr [rsp+210h+var_1A8+8], xmm0
0x180003406  test    r15, r15
0x180003409  jnz     loc_1800035E5
0x18000340f  lea     r14, [rbp+110h+var_188]
0x180003413  mov     [rsp+210h+var_1B8], 8
0x18000341b  mov     dword ptr [r14], 1A2B3C4Dh
0x180003422  mov     dword ptr [r14+4], 20000h
0x18000342a  test    rdi, rdi
0x18000342d  jnz     loc_1800035CE
0x180003433  mov     ecx, 8
0x180003438  lea     r12, [rbp+110h+Src]
0x18000343c  mov     dword ptr [rsp+210h+var_1A8], ecx
0x180003440  mov     rax, cs:?g_hIoDevice@@3REAXEA; void * g_hIoDevice
0x180003447  test    rax, rax
0x18000344a  jz      loc_180003731
0x180003450  mov     eax, [rsp+210h+var_1B8]
0x180003454  xor     r9d, r9d; ApcContext
0x180003457  mov     [rsp+210h+OutputBufferLength], ecx; OutputBufferLength
0x18000345b  xor     r8d, r8d; ApcRoutine
0x18000345e  mov     rcx, cs:?g_hIoDevice@@3REAXEA; FileHandle
0x180003465  xor     edx, edx; Event
0x180003467  mov     [rsp+210h+OutputBuffer], r12; OutputBuffer
0x18000346c  mov     [rsp+210h+InputBufferLength], eax; InputBufferLength
0x180003470  lea     rax, [rsp+210h+var_1A8+8]
0x180003475  mov     [rsp+210h+InputBuffer], r14; InputBuffer
0x18000347a  mov     [rsp+210h+IoControlCode], 390400h; IoControlCode
0x180003482  mov     [rsp+210h+IoStatusBlock], rax; IoStatusBlock
0x180003487  call    cs:__imp_NtDeviceIoControlFile
0x18000348e  nop     dword ptr [rax+rax+00h]
0x180003493  mov     r14d, dword ptr [rsp+210h+var_1A8+10h]
0x180003498  test    eax, eax
0x18000349a  js      loc_18000362F
0x1800034a0  test    rdi, rdi
0x1800034a3  jz      loc_1800037A8
0x1800034a9  cmp     esi, r14d
0x1800034ac  jb      loc_1800037A8
0x1800034b2  lea     rax, [rbp+110h+Src]
0x1800034b6  cmp     r12, rax
0x1800034b9  jnz     short loc_1800034C9
0x1800034bb  mov     r8d, r14d; Size
0x1800034be  mov     rdx, r12; Src
0x1800034c1  mov     rcx, rdi; void *
0x1800034c4  call    memcpy_0
0x1800034c9  mov     r12, [rsp+210h+var_1B0]
0x1800034ce  xor     esi, esi
0x1800034d0  mov     [r12], r14d
0x1800034d4  xor     r9d, r9d
0x1800034d7  cmp     [r13+0], rbx
0x1800034db  mov     [r13+0], rdi
0x1800034df  setz    r9b
0x1800034e3  mov     dword ptr [rsp+210h+var_1A8], r9d
0x1800034e8  test    esi, esi
0x1800034ea  js      loc_180003603
0x1800034f0  mov     rdi, [r13+0]
0x1800034f4  test    rdi, rdi
0x1800034f7  jz      loc_180003123
0x1800034fd  lea     rcx, [rdi+10h]
0x180003501  cmp     rcx, rdi
0x180003504  jb      loc_1800037C7
0x18000350a  mov     r8d, [r12]
0x18000350e  mov     [rsp+210h+var_1B8], r8d
0x180003513  mov     edx, r8d
0x180003516  lea     rax, [r8+rdi]
0x18000351a  cmp     rcx, rax
0x18000351d  ja      loc_1800037C7
0x180003523  mov     rcx, [rdi+8]
0x180003527  mov     r12d, [rdi]
0x18000352a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000352e  jz      loc_180003827
0x180003534  test    r12d, r12d
0x180003537  jz      loc_1800037C7
0x18000353d  cmp     rcx, rdx
0x180003540  jnb     loc_1800037C7
0x180003546  lea     r8, [rcx+r12*8]
0x18000354a  cmp     r8, rcx
0x18000354d  jb      loc_1800037C7
0x180003553  cmp     r8, rdx
0x180003556  ja      loc_1800037C7
0x18000355c  lea     rax, [rcx+rdi]
0x180003560  mov     r8d, edx; unsigned int
0x180003563  mov     [rdi+8], rax
0x180003567  test    rax, rax
0x18000356a  jz      loc_180003123
0x180003570  xor     r14d, r14d
0x180003573  cmp     r14d, r12d
0x180003576  jnb     loc_180003123
  ... truncated ...
```
