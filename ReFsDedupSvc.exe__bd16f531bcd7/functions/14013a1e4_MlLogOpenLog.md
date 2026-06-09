# MlLogOpenLog

- ea: `0x14013a1e4`
- end: `0x14013a680`
- name: `MlLogOpenLog`
- size: `1180`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1400fdfac`

## callees

- `0x1400057a4`
- `0x1400057e0`
- `0x1400057f8`
- `0x140139d40`
- `0x14013a1e4`
- `0x140151150`
- `0x140151a28`
- `0x140152088`
- `0x1401525f4`
- `0x1401b9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateMutexA` at `0x14013a3c7`
- `api-ms-win-core-synch-l1-1-0!CreateMutexA` at `0x14013a3c7`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x14013a3f6`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x14013a3f6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14013a564`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14013a57c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14013a564`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14013a57c`
- `RPCRT4!UuidCreate` at `0x14013a485`
- `RPCRT4!UuidCreate` at `0x14013a485`

## pseudocode

```c
__int64 __fastcall MlLogOpenLog(
        __int64 a1,
        char a2,
        __int64 a3,
        __int64 a4,
        unsigned __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        char a9,
        int a10,
        int a11,
        int a12,
        int a13,
        int a14,
        _DWORD *a15,
        _QWORD *a16)
{
  bool v16; // zf
  RPC_STATUS ControlArea; // edi
  char *PoolWithTagImpl; // rax
  char *v21; // rbx
  int v22; // eax
  HANDLE MutexA; // rax
  __int64 v24; // rcx
  _BYTE *v25; // rsi
  int v26; // eax
  _BYTE *v27; // rax
  __int64 v28; // rcx
  void *v29; // rcx
  void *v30; // rcx
  int v31; // eax
  int v32; // ebp

  v16 = AA_FAIL_LOG_OPEN == 0;
  *a16 = 0;
  if ( !v16 && !a15 && !a2 )
    return (unsigned int)-1073741670;
  if ( (__int64)a5 <= 0x2000 || (a5 & 0xFFF) != 0 || ((((a6 >> 63) & 0xFFF) + a6) & 0xFFF) != ((a6 >> 63) & 0xFFF) )
    return (unsigned int)-1073741811;
  PoolWithTagImpl = (char *)MlAllocatePoolWithTagImpl(4095, 0x4000);
  v21 = PoolWithTagImpl;
  if ( !PoolWithTagImpl )
    return (unsigned int)-1073741670;
  memset_0(PoolWithTagImpl, 0, 0x4000u);
  v22 = a13;
  *((_DWORD *)v21 + 914) = 1;
  if ( !a13 )
    v22 = 4096;
  *((_DWORD *)v21 + 3067) = v22;
  if ( (a9 & 1) != 0 )
    *((_DWORD *)v21 + 15) |= 1u;
  if ( (a9 & 0x20) == 0 )
  {
    if ( a14 )
      goto LABEL_15;
LABEL_17:
    if ( (a9 & 4) != 0 )
      *((_DWORD *)v21 + 3064) = 8;
    if ( (a9 & 0x10) != 0 )
      *((_DWORD *)v21 + 3064) |= 0x10u;
    *((_DWORD *)v21 + 3066) = a11;
    *((_QWORD *)v21 + 460) = a8 / 4096;
    *((_QWORD *)v21 + 459) = a7 / 4096;
    *((_DWORD *)v21 + 3065) = 1735347277;
    *((_QWORD *)v21 + 1) = a6 / 4096;
    *((_DWORD *)v21 + 916) = 4096;
    *((_DWORD *)v21 + 917) = 1;
    *((_QWORD *)v21 + 2) = (__int64)(a5 + a6) / 4096;
    *((_QWORD *)v21 + 463) = ML_LSN_INVALID;
    *((_QWORD *)v21 + 461) = 0;
    *((_QWORD *)v21 + 462) = (unsigned int)(a5 >> 12);
    MutexA = CreateMutexA(0, 0, 0);
    *((_DWORD *)v21 + 932) = 0;
    *((_QWORD *)v21 + 465) = MutexA;
    *((_DWORD *)v21 + 3068) = 0;
    *((_QWORD *)v21 + 1535) = CreateEventA(0, 1, 0, 0);
    *((_DWORD *)v21 + 3088) = 1;
    if ( *((_QWORD *)&xmmword_140243D40 + 1) )
      (*((void (__fastcall **)(__int64, char *))&xmmword_140243D40 + 1))(a1, v21 + 12352);
    if ( !*((_QWORD *)&xmmword_140243D30 + 1) || !(_QWORD)xmmword_140243D40 )
      *((_DWORD *)v21 + 3088) = 1;
    *((_QWORD *)v21 + 1545) = a1;
    if ( a2 )
    {
      if ( a15 )
      {
        *((_DWORD *)v21 + 7) = a15[1] + 1;
        *((_DWORD *)v21 + 6) = *a15;
        ++a15[1];
        *((_DWORD *)v21 + 15) |= 2u;
      }
      else
      {
        *((_QWORD *)v21 + 3) = 1;
      }
      *((_QWORD *)v21 + 4) = *((_QWORD *)v21 + 3);
      *(_QWORD *)v21 = 0;
      *((_DWORD *)v21 + 14) = 1;
      *((_DWORD *)v21 + 16) = 1;
      ControlArea = UuidCreate((UUID *)(v21 + 40));
      if ( ControlArea < 0 )
        goto LABEL_46;
      v25 = 0;
      v26 = (a15 != 0) + 6;
LABEL_58:
      *((_DWORD *)v21 + 914) = v26;
      *((_QWORD *)v21 + 469) = *((_QWORD *)v21 + 3);
      *((_QWORD *)v21 + 464) = ML_LSN_NULL;
      ControlArea = LogInitializeFlushWindows(v21);
      if ( ControlArea >= 0 )
      {
        if ( (v21[12256] & 0x10) != 0 )
        {
LABEL_63:
          *a16 = v21;
          v21 = 0;
        }
        else
        {
          v32 = 0;
          while ( 1 )
          {
            memcpy_0(v21 + 0x2000, v21, 0xE48u);
            ControlArea = LogCoreWriteControlArea(v21, a1);
            if ( ControlArea < 0 )
              break;
            if ( (unsigned int)++v32 >= 2 )
              goto LABEL_63;
          }
        }
      }
      if ( !v25 )
      {
LABEL_45:
        if ( !v21 )
          return (unsigned int)ControlArea;
        goto LABEL_46;
      }
LABEL_44:
      free(v25 - 16);
      goto LABEL_45;
    }
    *((_DWORD *)v21 + 914) = 2;
    v27 = (_BYTE *)MlAllocatePoolWithTagImpl(v24, 3656);
    v25 = v27;
    if ( !v27 )
    {
      ControlArea = -1073741670;
      goto LABEL_46;
    }
    memset_0(v27, 0, 0xE48u);
    ControlArea = LogCoreReadControlArea(v21, a1, v25);
    if ( ControlArea < 0 )
    {
      *((_DWORD *)v21 + 914) = 3;
      goto LABEL_44;
    }
    if ( *((_DWORD *)v25 + 16) == 1
      && *((_QWORD *)v21 + 1) == *((_QWORD *)v25 + 1)
      && *((_QWORD *)v21 + 2) == *((_QWORD *)v25 + 2)
      && ((v21[60] & 1) == 0 || (v25[60] & 1) != 0) )
    {
      if ( (v21[60] & 0x20) != 0 )
      {
        if ( (v25[60] & 0x20) == 0 )
          goto LABEL_43;
      }
      else
      {
        *((_DWORD *)v25 + 15) &= ~0x20u;
      }
      if ( a15 && *(_QWORD *)a15 < *((_QWORD *)v25 + 3) )
      {
        ControlArea = -1073741807;
        goto LABEL_44;
      }
      memcpy_0(v21, v25, 0xE48u);
      v31 = *((_DWORD *)v21 + 9);
      ++*((_DWORD *)v21 + 14);
      *((_DWORD *)v21 + 923) = v31;
      *((_DWORD *)v21 + 925) = v31;
      v26 = (v21[60] & 2) != 0 ? 7 : 4;
      goto LABEL_58;
    }
LABEL_43:
    ControlArea = -1073741774;
    goto LABEL_44;
  }
  *((_DWORD *)v21 + 15) |= 0x20u;
  *((_DWORD *)v21 + 3092) = a14;
  if ( a14 )
    goto LABEL_17;
LABEL_15:
  ControlArea = -1073741811;
LABEL_46:
  v28 = *((_QWORD *)v21 + 1531);
  if ( v28 )
    free((void *)(v28 - 16));
  v29 = (void *)*((_QWORD *)v21 + 465);
  if ( v29 )
    CloseHandle(v29);
  v30 = (void *)*((_QWORD *)v21 + 1535);
  if ( v30 )
    CloseHandle(v30);
  LogUninitializeFlushWindows(v21);
  free(v21 - 16);
  return (unsigned int)ControlArea;
}

```

## disassembly

```asm
0x14013a1e4  push    rbx
0x14013a1e6  push    rbp
0x14013a1e7  push    rsi
0x14013a1e8  push    rdi
0x14013a1e9  push    r12
0x14013a1eb  push    r13
0x14013a1ed  push    r14
0x14013a1ef  push    r15
0x14013a1f1  sub     rsp, 28h
0x14013a1f5  mov     r12, [rsp+68h+arg_78]
0x14013a1fd  xor     r13d, r13d
0x14013a200  cmp     cs:AA_FAIL_LOG_OPEN, r13d
0x14013a207  mov     sil, dl
0x14013a20a  mov     r14, [rsp+68h+arg_70]
0x14013a212  mov     r15, rcx
0x14013a215  mov     [r12], r13
0x14013a219  jz      short loc_14013A22E
0x14013a21b  test    r14, r14
0x14013a21e  jnz     short loc_14013A22E
0x14013a220  test    dl, dl
0x14013a222  jnz     short loc_14013A22E
0x14013a224  mov     edi, 0C000009Ah
0x14013a229  jmp     loc_14013A66C
0x14013a22e  mov     rdi, [rsp+68h+arg_20]
0x14013a236  cmp     rdi, 2000h
0x14013a23d  jle     loc_14013A667
0x14013a243  mov     ecx, 0FFFh
0x14013a248  test    rcx, rdi
0x14013a24b  jnz     loc_14013A667
0x14013a251  mov     rbp, [rsp+68h+arg_28]
0x14013a259  mov     rax, rbp
0x14013a25c  cqo
0x14013a25e  and     rdx, rcx
0x14013a261  add     rax, rdx
0x14013a264  and     rax, rcx
0x14013a267  cmp     rax, rdx
0x14013a26a  jnz     loc_14013A667
0x14013a270  mov     edx, 4000h
0x14013a275  call    MlAllocatePoolWithTagImpl
0x14013a27a  mov     rbx, rax
0x14013a27d  test    rax, rax
0x14013a280  jz      short loc_14013A224
0x14013a282  xor     edx, edx; Val
0x14013a284  mov     r8d, 4000h; Size
0x14013a28a  mov     rcx, rax; void *
0x14013a28d  call    memset_0
0x14013a292  mov     eax, [rsp+68h+arg_60]
0x14013a299  mov     r9d, 1
0x14013a29f  mov     ecx, dword ptr [rsp+68h+arg_40]
0x14013a2a6  test    eax, eax
0x14013a2a8  mov     r11d, 1000h
0x14013a2ae  mov     [rbx+0E48h], r9d
0x14013a2b5  cmovz   eax, r11d
0x14013a2b9  mov     [rbx+2FECh], eax
0x14013a2bf  test    r9b, cl
0x14013a2c2  jz      short loc_14013A2C8
0x14013a2c4  or      [rbx+3Ch], r9d
0x14013a2c8  test    cl, 20h
0x14013a2cb  jz      short loc_14013A2EC
0x14013a2cd  mov     eax, [rsp+68h+arg_68]
0x14013a2d4  or      dword ptr [rbx+3Ch], 20h
0x14013a2d8  mov     [rbx+3050h], eax
0x14013a2de  test    eax, eax
0x14013a2e0  jnz     short loc_14013A2F6
0x14013a2e2  mov     edi, 0C000000Dh
0x14013a2e7  jmp     loc_14013A543
0x14013a2ec  cmp     [rsp+68h+arg_68], r13d
0x14013a2f4  jnz     short loc_14013A2E2
0x14013a2f6  mov     rax, [rsp+68h+arg_30]
0x14013a2fe  mov     r10d, 0FFFh
0x14013a304  cqo
0x14013a306  and     rdx, r10
0x14013a309  lea     r8, [rdx+rax]
0x14013a30d  mov     rax, [rsp+68h+arg_38]
0x14013a315  cqo
0x14013a317  sar     r8, 0Ch
0x14013a31b  and     rdx, r10
0x14013a31e  add     rdx, rax
0x14013a321  sar     rdx, 0Ch
0x14013a325  test    cl, 4
0x14013a328  jz      short loc_14013A334
0x14013a32a  mov     dword ptr [rbx+2FE0h], 8
0x14013a334  test    cl, 10h
0x14013a337  jz      short loc_14013A340
0x14013a339  or      dword ptr [rbx+2FE0h], 10h
0x14013a340  mov     eax, [rsp+68h+arg_50]
0x14013a347  xor     ecx, ecx; lpMutexAttributes
0x14013a349  mov     [rbx+2FE8h], eax
0x14013a34f  mov     rax, rbp
0x14013a352  mov     [rbx+0E60h], rdx
0x14013a359  cqo
0x14013a35b  and     rdx, r10
0x14013a35e  mov     [rbx+0E58h], r8
0x14013a365  add     rax, rdx
0x14013a368  mov     dword ptr [rbx+2FE4h], 676F4C4Dh
0x14013a372  sar     rax, 0Ch
0x14013a376  xor     r8d, r8d; lpName
0x14013a379  mov     [rbx+8], rax
0x14013a37d  lea     rax, [rdi+rbp]
0x14013a381  cqo
0x14013a383  shr     rdi, 0Ch
0x14013a387  and     rdx, r10
0x14013a38a  mov     [rbx+0E50h], r11d
0x14013a391  add     rax, rdx
0x14013a394  mov     [rbx+0E54h], r9d
0x14013a39b  sar     rax, 0Ch
0x14013a39f  xor     edx, edx; bInitialOwner
0x14013a3a1  mov     [rbx+10h], rax
0x14013a3a5  mov     rax, cs:ML_LSN_INVALID
0x14013a3ac  mov     [rbx+0E78h], rax
0x14013a3b3  mov     [rbx+0E68h], r13
0x14013a3ba  mov     [rbx+0E74h], r13d
0x14013a3c1  mov     [rbx+0E70h], edi
0x14013a3c7  call    cs:__imp_CreateMutexA
0x14013a3ce  nop     dword ptr [rax+rax+00h]
0x14013a3d3  xor     r9d, r9d; lpName
0x14013a3d6  mov     [rbx+0E90h], r13d
0x14013a3dd  xor     r8d, r8d; bInitialState
0x14013a3e0  mov     [rbx+0E88h], rax
0x14013a3e7  xor     ecx, ecx; lpEventAttributes
0x14013a3e9  mov     [rbx+2FF0h], r13d
0x14013a3f0  lea     ebp, [r9+1]
0x14013a3f4  mov     edx, ebp; bManualReset
0x14013a3f6  call    cs:__imp_CreateEventA
0x14013a3fd  nop     dword ptr [rax+rax+00h]
0x14013a402  lea     rdi, [rbx+3040h]
0x14013a409  mov     [rbx+2FF8h], rax
0x14013a410  mov     [rdi], ebp
0x14013a412  mov     rax, qword ptr cs:xmmword_140243D40+8
0x14013a419  test    rax, rax
0x14013a41c  jz      short loc_14013A429
0x14013a41e  mov     rdx, rdi
0x14013a421  mov     rcx, r15
0x14013a424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14013a429  cmp     qword ptr cs:xmmword_140243D30+8, r13
0x14013a430  jz      short loc_14013A43B
0x14013a432  cmp     qword ptr cs:xmmword_140243D40, r13
0x14013a439  jnz     short loc_14013A43D
0x14013a43b  mov     [rdi], ebp
0x14013a43d  mov     [rbx+3048h], r15
0x14013a444  mov     edi, 0E48h
0x14013a449  test    sil, sil
0x14013a44c  jz      short loc_14013A4AD
0x14013a44e  test    r14, r14
0x14013a451  jnz     short loc_14013A459
0x14013a453  mov     [rbx+18h], rbp
0x14013a457  jmp     short loc_14013A470
0x14013a459  mov     eax, [r14+4]
0x14013a45d  add     eax, ebp
0x14013a45f  mov     [rbx+1Ch], eax
0x14013a462  mov     eax, [r14]
0x14013a465  mov     [rbx+18h], eax
0x14013a468  add     [r14+4], ebp
0x14013a46c  or      dword ptr [rbx+3Ch], 2
0x14013a470  mov     rax, [rbx+18h]
0x14013a474  lea     rcx, [rbx+28h]; Uuid
0x14013a478  mov     [rbx+20h], rax
0x14013a47c  mov     [rbx], r13
0x14013a47f  mov     [rbx+38h], ebp
0x14013a482  mov     [rbx+40h], ebp
0x14013a485  call    cs:__imp_UuidCreate
0x14013a48c  nop     dword ptr [rax+rax+00h]
0x14013a491  mov     edi, eax
0x14013a493  test    eax, eax
0x14013a495  js      loc_14013A543
0x14013a49b  neg     r14
0x14013a49e  mov     rsi, r13
0x14013a4a1  sbb     eax, eax
0x14013a4a3  neg     eax
0x14013a4a5  add     eax, 6
0x14013a4a8  jmp     loc_14013A5EC
0x14013a4ad  mov     rdx, rdi
0x14013a4b0  mov     dword ptr [rbx+0E48h], 2
0x14013a4ba  call    MlAllocatePoolWithTagImpl
0x14013a4bf  mov     rsi, rax
0x14013a4c2  test    rax, rax
0x14013a4c5  jnz     short loc_14013A4CE
0x14013a4c7  mov     edi, 0C000009Ah
0x14013a4cc  jmp     short loc_14013A543
0x14013a4ce  mov     r8, rdi; Size
0x14013a4d1  xor     edx, edx; Val
0x14013a4d3  mov     rcx, rsi; void *
0x14013a4d6  call    memset_0
0x14013a4db  mov     r8, rsi
0x14013a4de  mov     rdx, r15
0x14013a4e1  mov     rcx, rbx
0x14013a4e4  call    LogCoreReadControlArea
0x14013a4e9  mov     edi, eax
0x14013a4eb  test    eax, eax
0x14013a4ed  jns     short loc_14013A4FB
0x14013a4ef  mov     dword ptr [rbx+0E48h], 3
0x14013a4f9  jmp     short loc_14013A531
0x14013a4fb  cmp     [rsi+40h], ebp
0x14013a4fe  jnz     short loc_14013A52C
0x14013a500  mov     rax, [rsi+8]
0x14013a504  cmp     [rbx+8], rax
0x14013a508  jnz     short loc_14013A52C
0x14013a50a  mov     rax, [rsi+10h]
0x14013a50e  cmp     [rbx+10h], rax
0x14013a512  jnz     short loc_14013A52C
0x14013a514  test    [rbx+3Ch], bpl
0x14013a518  jz      short loc_14013A520
0x14013a51a  test    [rsi+3Ch], bpl
0x14013a51e  jz      short loc_14013A52C
0x14013a520  test    byte ptr [rbx+3Ch], 20h
0x14013a524  jz      short loc_14013A59E
0x14013a526  test    byte ptr [rsi+3Ch], 20h
0x14013a52a  jnz     short loc_14013A5A2
0x14013a52c  mov     edi, 0C0000032h
0x14013a531  lea     rcx, [rsi-10h]; Block
0x14013a535  call    free
0x14013a53a  test    rbx, rbx
0x14013a53d  jz      loc_14013A66C
0x14013a543  mov     rcx, [rbx+2FD8h]
0x14013a54a  test    rcx, rcx
0x14013a54d  jz      short loc_14013A558
0x14013a54f  add     rcx, 0FFFFFFFFFFFFFFF0h; Block
0x14013a553  call    free
0x14013a558  mov     rcx, [rbx+0E88h]; hObject
0x14013a55f  test    rcx, rcx
0x14013a562  jz      short loc_14013A570
0x14013a564  call    cs:__imp_CloseHandle
0x14013a56b  nop     dword ptr [rax+rax+00h]
0x14013a570  mov     rcx, [rbx+2FF8h]; hObject
0x14013a577  test    rcx, rcx
0x14013a57a  jz      short loc_14013A588
0x14013a57c  call    cs:__imp_CloseHandle
0x14013a583  nop     dword ptr [rax+rax+00h]
0x14013a588  mov     rcx, rbx
0x14013a58b  call    LogUninitializeFlushWindows
0x14013a590  lea     rcx, [rbx-10h]; Block
0x14013a594  call    free
0x14013a599  jmp     loc_14013A66C
0x14013a59e  and     dword ptr [rsi+3Ch], 0FFFFFFDFh
0x14013a5a2  test    r14, r14
0x14013a5a5  jz      short loc_14013A5BA
0x14013a5a7  mov     rax, [rsi+18h]
0x14013a5ab  cmp     [r14], rax
0x14013a5ae  jnb     short loc_14013A5BA
0x14013a5b0  mov     edi, 0C0000011h
0x14013a5b5  jmp     loc_14013A531
0x14013a5ba  mov     rcx, rbx; void *
0x14013a5bd  mov     rdx, rsi; Src
0x14013a5c0  mov     r8d, 0E48h; Size
0x14013a5c6  call    memcpy_0
0x14013a5cb  mov     eax, [rbx+24h]
0x14013a5ce  add     [rbx+38h], ebp
0x14013a5d1  mov     [rbx+0E6Ch], eax
0x14013a5d7  mov     [rbx+0E74h], eax
0x14013a5dd  mov     al, [rbx+3Ch]
0x14013a5e0  and     al, 2
0x14013a5e2  neg     al
0x14013a5e4  sbb     eax, eax
0x14013a5e6  and     eax, 3
0x14013a5e9  add     eax, 4
0x14013a5ec  mov     [rbx+0E48h], eax
0x14013a5f2  mov     rcx, rbx
0x14013a5f5  mov     rax, [rbx+18h]
0x14013a5f9  mov     [rbx+0EA8h], rax
0x14013a600  mov     rax, cs:ML_LSN_NULL
0x14013a607  mov     [rbx+0E80h], rax
0x14013a60e  call    LogInitializeFlushWindows
0x14013a613  mov     edi, eax
0x14013a615  test    eax, eax
0x14013a617  js      short loc_14013A659
0x14013a619  test    byte ptr [rbx+2FE0h], 10h
0x14013a620  jnz     short loc_14013A652
0x14013a622  mov     ebp, r13d
0x14013a625  lea     rcx, [rbx+2000h]; void *
0x14013a62c  mov     rdx, rbx; Src
0x14013a62f  mov     r8d, 0E48h; Size
0x14013a635  call    memcpy_0
0x14013a63a  mov     rdx, r15
0x14013a63d  mov     rcx, rbx
0x14013a640  call    LogCoreWriteControlArea
0x14013a645  mov     edi, eax
0x14013a647  test    eax, eax
0x14013a649  js      short loc_14013A659
0x14013a64b  inc     ebp
0x14013a64d  cmp     ebp, 2
0x14013a650  jb      short loc_14013A625
0x14013a652  mov     [r12], rbx
0x14013a656  mov     rbx, r13
0x14013a659  test    rsi, rsi
0x14013a65c  jz      loc_14013A53A
0x14013a662  jmp     loc_14013A531
0x14013a667  mov     edi, 0C000000Dh
0x14013a66c  mov     eax, edi
0x14013a66e  add     rsp, 28h
0x14013a672  pop     r15
0x14013a674  pop     r14
0x14013a676  pop     r13
0x14013a678  pop     r12
0x14013a67a  pop     rdi
0x14013a67b  pop     rsi
0x14013a67c  pop     rbp
0x14013a67d  pop     rbx
0x14013a67e  retn
```
