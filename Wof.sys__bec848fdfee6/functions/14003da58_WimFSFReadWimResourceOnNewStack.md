# WimFSFReadWimResourceOnNewStack

- ea: `0x14003da58`
- end: `0x14003e017`
- name: `WimFSFReadWimResourceOnNewStack`
- size: `1471`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000cfc0`

## callees

- `0x1400094f0`
- `0x14000c074`
- `0x14000d3b8`
- `0x14000fb60`
- `0x140010078`
- `0x1400105e8`
- `0x1400106a8`
- `0x1400107e8`
- `0x140011560`
- `0x1400119c0`
- `0x14002e244`
- `0x14003cd40`
- `0x14003da58`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14003dec3`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14003dec3`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003dbd9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003dbd9`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003de6d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003de6d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003dbc1`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003dbc1`

## pseudocode

```c
__int64 __fastcall WimFSFReadWimResourceOnNewStack(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  void *v4; // rdi
  void *v5; // r14
  __int64 v6; // r12
  __int64 v7; // r13
  __int64 v8; // rax
  _DWORD *v9; // r15
  __int64 result; // rax
  struct _FLT_CALLBACK_DATA *v11; // rbx
  __int64 v12; // rdx
  __int64 v13; // r8
  int v14; // edi
  __int64 v15; // r13
  __int64 v16; // r8
  __int64 v17; // r9
  unsigned __int64 v18; // r15
  __int64 v19; // rdi
  struct _FLT_CALLBACK_DATA *v20; // rbx
  unsigned int v21; // ecx
  unsigned int v22; // edi
  char v23; // al
  char v24; // dl
  const char *v25; // r9
  char *PoolWithTag; // r15
  PVOID v27; // r12
  char *v28; // rax
  __int64 v29; // rsi
  __int64 v30; // rdx
  char *v31; // rcx
  PDEVICE_OBJECT v32; // r8
  const char *v33; // r9
  unsigned __int8 v34; // [rsp+40h] [rbp-C0h]
  char v35; // [rsp+41h] [rbp-BFh]
  char v36; // [rsp+42h] [rbp-BEh]
  unsigned int v37; // [rsp+44h] [rbp-BCh]
  SIZE_T NumberOfBytes; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v39; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v40; // [rsp+58h] [rbp-A8h]
  __int64 v41; // [rsp+60h] [rbp-A0h] BYREF
  int v42[2]; // [rsp+68h] [rbp-98h] BYREF
  _DWORD Context[72]; // [rsp+70h] [rbp-90h] BYREF

  v3 = *(_QWORD *)(a1 + 64);
  v4 = *(void **)(a1 + 96);
  v5 = *(void **)(a1 + 72);
  v6 = *(unsigned int *)(a1 + 88);
  v7 = *(_QWORD *)(a1 + 80);
  v40 = *(_QWORD *)(a1 + 24);
  v34 = *(_BYTE *)(a1 + 56);
  v39 = 0;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids);
  *(_DWORD *)(a1 + 92) = 0;
  v8 = *(_QWORD *)(a1 + 40);
  v9 = (_DWORD *)((v7 + 64) & -(__int64)(v7 != 0));
  if ( v3 >= v8 )
    return 0;
  if ( v8 == *(_QWORD *)(a1 + 32) )
  {
    memset(Context, 0, sizeof(Context));
    v11 = (struct _FLT_CALLBACK_DATA *)(*(_QWORD *)(a1 + 48) + v3);
    WimFSFInitializeCompletionContextOnStack((_OWORD *)a1, v12, (__int64)Context);
    LOBYTE(v13) = 1;
    result = WimFSFReadWim(v34, 0, v13, v11, v4, v5, v6, (char *)Context);
    *(_DWORD *)(a1 + 92) = Context[29];
    return result;
  }
  if ( v7 )
  {
    v14 = 0;
    if ( (*v9 & 1) == 0 )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids);
      LOBYTE(a2) = v34;
      v14 = WimFSFBuildChunkTable(a1, a2, v9 + 8);
      if ( v14 < 0 )
        goto LABEL_68;
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)v7 + 32LL));
      *v9 |= 1u;
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)v7 + 32LL));
    }
    if ( !v39 )
      v39 = *(_QWORD *)(((v7 + 64) & -(__int64)(v7 != 0)) + 0x20);
  }
  else
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids);
    LOBYTE(a2) = v34;
    v14 = WimFSFBuildChunkTable(a1, a2, &v39);
    if ( v14 < 0 )
      goto LABEL_68;
  }
  if ( v3 + v6 > *(_QWORD *)(a1 + 40) )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_dd(
        WPP_GLOBAL_Control->AttachedDevice,
        29,
        WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids,
        (unsigned int)v6,
        *(_DWORD *)(a1 + 40) - v3);
    LODWORD(v6) = *(_DWORD *)(a1 + 40) - v3;
  }
  if ( (_DWORD)v6 )
  {
    *(_QWORD *)v42 = 0;
    v37 = 0;
    NumberOfBytes = 0;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        30,
        WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids,
        (unsigned int)v6);
    v15 = v40;
    v16 = *(unsigned int *)(v40 + 104);
    v17 = v3 / v16;
    v40 = v3 / v16;
    v18 = (-v16 & (v3 + v16 + (unsigned __int64)(unsigned int)v6 - 1)) / v16;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids, v17, v18);
      LODWORD(v17) = v40;
    }
    v19 = v39;
    if ( v39 )
    {
      v41 = WimFSFGetChunkOffset(v39, (unsigned int)v17);
      v20 = (struct _FLT_CALLBACK_DATA *)v41;
      v21 = WimFSFGetChunkOffset(v19, (unsigned int)v18) - (_DWORD)v20;
    }
    else
    {
      v20 = *(struct _FLT_CALLBACK_DATA **)(a1 + 48);
      v21 = *(_DWORD *)(a1 + 32);
      v41 = (__int64)v20;
    }
    v22 = v21 + 4;
    if ( (*(_DWORD *)(v15 + 96) & 0x40000) == 0 )
      v22 = v21;
    if ( v34 )
    {
      v23 = WimFSFGetAlignedSizesForIntegrity(
              v15,
              (unsigned int)&v41,
              v22,
              *(_DWORD *)(v15 + 92),
              (__int64)v42,
              (__int64)&NumberOfBytes,
              (__int64)&NumberOfBytes + 4);
      v20 = *(struct _FLT_CALLBACK_DATA **)v42;
      v24 = v23;
      v22 = NumberOfBytes;
      v37 = HIDWORD(NumberOfBytes);
      v36 = 1;
    }
    else
    {
      v36 = 0;
      v24 = 1;
    }
    v35 = v24;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      v25 = "IS";
      if ( !v24 )
        v25 = "IS NOT";
      WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids, v25);
    }
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_dd(
        WPP_GLOBAL_Control->AttachedDevice,
        33,
        WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids,
        v22,
        *(_DWORD *)(v15 + 448));
    if ( v22 <= *(_DWORD *)(v15 + 448) )
    {
      v28 = (char *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)(v15 + 512));
      v27 = v28;
      if ( !v28 )
        goto LABEL_51;
      PoolWithTag = v28;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids);
    }
    else
    {
      PoolWithTag = (char *)ExAllocatePoolWithTag(PagedPool, v22, 0x44527077u);
      if ( !PoolWithTag )
      {
LABEL_51:
        v14 = -1073741670;
        goto LABEL_68;
      }
      v27 = 0;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids, v22);
    }
    v29 = a1 - 24;
    *(_QWORD *)(v29 + 272) = v27;
    *(_QWORD *)(v29 + 240) = WimFSFReadWimResourceOnNewStackExtendedCompletion;
    *(_QWORD *)(v29 + 248) = v39;
    *(_DWORD *)(v29 + 264) = v40;
    *(_QWORD *)(v29 + 280) = PoolWithTag;
    v30 = v37;
    if ( v34 )
      v31 = &PoolWithTag[v37];
    else
      v31 = PoolWithTag;
    *(_QWORD *)(v29 + 256) = v31;
    v32 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      v33 = "PAGING";
      if ( !v34 )
        v33 = "NORMAL";
      WPP_SF_sqD(WPP_GLOBAL_Control->AttachedDevice, v37, (_DWORD)WPP_GLOBAL_Control, (_DWORD)v33, (char)v31, v37);
    }
    LOBYTE(v32) = v35;
    LOBYTE(v30) = v36;
    v14 = WimFSFReadWim(v34, v30, (__int64)v32, v20, PoolWithTag, 0, v22, (char *)v29);
  }
LABEL_68:
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids, (unsigned int)v14);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14003da58  push    rbp
0x14003da5a  push    rbx
0x14003da5b  push    rsi
0x14003da5c  push    rdi
0x14003da5d  push    r12
0x14003da5f  push    r13
0x14003da61  push    r14
0x14003da63  push    r15
0x14003da65  lea     rbp, [rsp-0A8h]
0x14003da6d  sub     rsp, 1A8h
0x14003da74  mov     rax, cs:__security_cookie
0x14003da7b  xor     rax, rsp
0x14003da7e  mov     [rbp+0E0h+var_50], rax
0x14003da85  mov     rax, [rcx+18h]
0x14003da89  mov     rsi, rcx
0x14003da8c  mov     rbx, [rcx+40h]
0x14003da90  mov     rdi, [rcx+60h]
0x14003da94  mov     r14, [rcx+48h]
0x14003da98  mov     r12d, [rcx+58h]
0x14003da9c  mov     r13, [rcx+50h]
0x14003daa0  mov     [rsp+1E0h+var_188], rax
0x14003daa5  mov     al, [rcx+38h]
0x14003daa8  mov     byte ptr [rsp+1E0h+var_1A0], al
0x14003daac  mov     [rsp+1E0h+var_190], 0
0x14003dab5  mov     rcx, cs:WPP_GLOBAL_Control
0x14003dabc  mov     eax, [rcx+2Ch]
0x14003dabf  test    al, 20h
0x14003dac1  jz      short loc_14003DADE
0x14003dac3  cmp     byte ptr [rcx+29h], 4
0x14003dac7  jb      short loc_14003DADE
0x14003dac9  mov     rcx, [rcx+18h]
0x14003dacd  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14003dad4  mov     edx, 1Ah
0x14003dad9  call    WPP_SF_
0x14003dade  mov     rax, r13
0x14003dae1  mov     dword ptr [rsi+5Ch], 0
0x14003dae8  neg     rax
0x14003daeb  lea     rcx, [r13+40h]
0x14003daef  mov     rax, [rsi+28h]
0x14003daf3  sbb     r15, r15
0x14003daf6  and     r15, rcx
0x14003daf9  cmp     rbx, rax
0x14003dafc  jl      short loc_14003DB05
0x14003dafe  xor     eax, eax
0x14003db00  jmp     loc_14003DFF3
0x14003db05  cmp     rax, [rsi+20h]
0x14003db09  jnz     short loc_14003DB63
0x14003db0b  xor     edx, edx; Val
0x14003db0d  lea     rcx, [rsp+1E0h+var_170]; void *
0x14003db12  mov     r8d, 120h; Size
0x14003db18  call    memset
0x14003db1d  add     rbx, [rsi+30h]
0x14003db21  lea     r8, [rsp+1E0h+var_170]
0x14003db26  mov     rcx, rsi
0x14003db29  call    WimFSFInitializeCompletionContextOnStack
0x14003db2e  mov     cl, byte ptr [rsp+1E0h+var_1A0]; int
0x14003db32  lea     rax, [rsp+1E0h+var_170]
0x14003db37  mov     [rsp+1E0h+Context], rax; Context
0x14003db3c  mov     r9, rbx; int
0x14003db3f  mov     [rsp+1E0h+var_1B0], r12d; int
0x14003db44  mov     r8b, 1; int
0x14003db47  mov     [rsp+1E0h+var_1B8], r14; __int64
0x14003db4c  xor     edx, edx; int
0x14003db4e  mov     [rsp+1E0h+var_1C0], rdi; PVOID
0x14003db53  call    WimFSFReadWim
0x14003db58  mov     ecx, [rbp+0E0h+var_FC]
0x14003db5b  mov     [rsi+5Ch], ecx
0x14003db5e  jmp     loc_14003DFF3
0x14003db63  mov     r14b, 5
0x14003db66  test    r13, r13
0x14003db69  jz      loc_14003DBF8
0x14003db6f  mov     eax, [r15]
0x14003db72  xor     edi, edi
0x14003db74  test    al, 1
0x14003db76  jnz     short loc_14003DBE5
0x14003db78  mov     rcx, cs:WPP_GLOBAL_Control
0x14003db7f  mov     eax, [rcx+2Ch]
0x14003db82  test    al, 20h
0x14003db84  jz      short loc_14003DB9F
0x14003db86  cmp     [rcx+29h], r14b
0x14003db8a  jb      short loc_14003DB9F
0x14003db8c  mov     rcx, [rcx+18h]
0x14003db90  lea     edx, [rdi+1Bh]
0x14003db93  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14003db9a  call    WPP_SF_
0x14003db9f  mov     dl, byte ptr [rsp+1E0h+var_1A0]
0x14003dba3  lea     r8, [r15+20h]
0x14003dba7  mov     rcx, rsi
0x14003dbaa  call    WimFSFBuildChunkTable
0x14003dbaf  mov     edi, eax
0x14003dbb1  test    eax, eax
0x14003dbb3  js      loc_14003DFC5
0x14003dbb9  mov     rcx, [r13+0]
0x14003dbbd  add     rcx, 20h ; ' '; FastMutex
0x14003dbc1  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14003dbc8  nop     dword ptr [rax+rax+00h]
0x14003dbcd  or      dword ptr [r15], 1
0x14003dbd1  mov     rcx, [r13+0]
0x14003dbd5  add     rcx, 20h ; ' '; FastMutex
0x14003dbd9  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14003dbe0  nop     dword ptr [rax+rax+00h]
0x14003dbe5  cmp     [rsp+1E0h+var_190], 0
0x14003dbeb  jnz     short loc_14003DC3C
0x14003dbed  mov     rax, [r15+20h]
0x14003dbf1  mov     [rsp+1E0h+var_190], rax
0x14003dbf6  jmp     short loc_14003DC3C
0x14003dbf8  mov     rcx, cs:WPP_GLOBAL_Control
0x14003dbff  mov     eax, [rcx+2Ch]
0x14003dc02  test    al, 20h
0x14003dc04  jz      short loc_14003DC21
0x14003dc06  cmp     [rcx+29h], r14b
0x14003dc0a  jb      short loc_14003DC21
0x14003dc0c  mov     rcx, [rcx+18h]
0x14003dc10  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14003dc17  mov     edx, 1Ch
0x14003dc1c  call    WPP_SF_
0x14003dc21  mov     dl, byte ptr [rsp+1E0h+var_1A0]
0x14003dc25  lea     r8, [rsp+1E0h+var_190]
0x14003dc2a  mov     rcx, rsi
0x14003dc2d  call    WimFSFBuildChunkTable
0x14003dc32  mov     edi, eax
0x14003dc34  test    eax, eax
0x14003dc36  js      loc_14003DFC5
0x14003dc3c  lea     rax, [rbx+r12]
0x14003dc40  cmp     rax, [rsi+28h]
0x14003dc44  jle     short loc_14003DC82
0x14003dc46  mov     rcx, cs:WPP_GLOBAL_Control
0x14003dc4d  mov     eax, [rcx+2Ch]
0x14003dc50  test    al, 20h
0x14003dc52  jz      short loc_14003DC7B
0x14003dc54  cmp     [rcx+29h], r14b
0x14003dc58  jb      short loc_14003DC7B
0x14003dc5a  mov     eax, [rsi+28h]
0x14003dc5d  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14003dc64  mov     rcx, [rcx+18h]
0x14003dc68  sub     eax, ebx
0x14003dc6a  mov     edx, 1Dh
0x14003dc6f  mov     dword ptr [rsp+1E0h+var_1C0], eax
0x14003dc73  mov     r9d, r12d
0x14003dc76  call    WPP_SF_dd
0x14003dc7b  mov     r12d, [rsi+28h]
0x14003dc7f  sub     r12d, ebx
0x14003dc82  test    r12d, r12d
0x14003dc85  jz      loc_14003DFC5
0x14003dc8b  xor     eax, eax
0x14003dc8d  mov     qword ptr [rsp+1E0h+var_178], 0
0x14003dc96  mov     [rsp+1E0h+var_19C], eax
0x14003dc9a  mov     dword ptr [rsp+1E0h+NumberOfBytes+4], eax
0x14003dc9e  mov     dword ptr [rsp+1E0h+NumberOfBytes], 0
0x14003dca6  mov     rcx, cs:WPP_GLOBAL_Control
0x14003dcad  mov     eax, [rcx+2Ch]
0x14003dcb0  test    al, 20h
0x14003dcb2  jz      short loc_14003DCD2
0x14003dcb4  cmp     [rcx+29h], r14b
0x14003dcb8  jb      short loc_14003DCD2
0x14003dcba  mov     rcx, [rcx+18h]
0x14003dcbe  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14003dcc5  mov     edx, 1Eh
0x14003dcca  mov     r9d, r12d
0x14003dccd  call    WPP_SF_d
0x14003dcd2  mov     r13, [rsp+1E0h+var_188]
0x14003dcd7  mov     rax, rbx
0x14003dcda  cqo
0x14003dcdc  mov     r8d, [r13+68h]
0x14003dce0  idiv    r8
0x14003dce3  mov     ecx, r8d
0x14003dce6  xor     edx, edx
0x14003dce8  mov     r9, rax
0x14003dceb  mov     [rsp+1E0h+var_188], rax
0x14003dcf0  neg     rcx
0x14003dcf3  mov     eax, r12d
0x14003dcf6  dec     rax
0x14003dcf9  add     rax, r8
0x14003dcfc  add     rax, rbx
0x14003dcff  and     rax, rcx
0x14003dd02  div     r8
0x14003dd05  mov     r15, rax
0x14003dd08  mov     rcx, cs:WPP_GLOBAL_Control
0x14003dd0f  mov     edx, [rcx+2Ch]
0x14003dd12  test    dl, 20h
0x14003dd15  jz      short loc_14003DD3C
0x14003dd17  cmp     [rcx+29h], r14b
0x14003dd1b  jb      short loc_14003DD3C
0x14003dd1d  mov     rcx, [rcx+18h]
0x14003dd21  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14003dd28  mov     edx, 1Fh
0x14003dd2d  mov     dword ptr [rsp+1E0h+var_1C0], r15d
0x14003dd32  call    WPP_SF_dd
0x14003dd37  mov     r9, [rsp+1E0h+var_188]
0x14003dd3c  mov     rdi, [rsp+1E0h+var_190]
0x14003dd41  test    rdi, rdi
0x14003dd44  jz      short loc_14003DD6B
0x14003dd46  mov     edx, r9d
0x14003dd49  mov     rcx, rdi
0x14003dd4c  call    WimFSFGetChunkOffset
0x14003dd51  mov     edx, r15d
0x14003dd54  mov     [rsp+1E0h+var_180], rax
0x14003dd59  mov     rcx, rdi
0x14003dd5c  mov     rbx, rax
0x14003dd5f  call    WimFSFGetChunkOffset
0x14003dd64  mov     rcx, rax
0x14003dd67  sub     ecx, ebx
0x14003dd69  jmp     short loc_14003DD77
0x14003dd6b  mov     rbx, [rsi+30h]
0x14003dd6f  mov     ecx, [rsi+20h]
0x14003dd72  mov     [rsp+1E0h+var_180], rbx
0x14003dd77  test    dword ptr [r13+60h], 40000h
0x14003dd7f  lea     edi, [rcx+4]
0x14003dd82  cmovz   edi, ecx
0x14003dd85  cmp     byte ptr [rsp+1E0h+var_1A0], 0
0x14003dd8a  jz      short loc_14003DDD8
0x14003dd8c  mov     r9d, [r13+5Ch]
0x14003dd90  lea     rax, [rsp+1E0h+NumberOfBytes+4]
0x14003dd95  mov     qword ptr [rsp+1E0h+var_1B0], rax
0x14003dd9a  lea     rdx, [rsp+1E0h+var_180]
0x14003dd9f  lea     rax, [rsp+1E0h+NumberOfBytes]
0x14003dda4  mov     r8d, edi
0x14003dda7  mov     [rsp+1E0h+var_1B8], rax
0x14003ddac  mov     rcx, r13
0x14003ddaf  lea     rax, [rsp+1E0h+var_178]
0x14003ddb4  mov     [rsp+1E0h+var_1C0], rax
0x14003ddb9  call    WimFSFGetAlignedSizesForIntegrity
0x14003ddbe  mov     rbx, qword ptr [rsp+1E0h+var_178]
0x14003ddc3  mov     dl, al
0x14003ddc5  mov     eax, dword ptr [rsp+1E0h+NumberOfBytes+4]
0x14003ddc9  mov     edi, dword ptr [rsp+1E0h+NumberOfBytes]
0x14003ddcd  mov     [rsp+1E0h+var_19C], eax
0x14003ddd1  mov     byte ptr [rsp+1E0h+var_1A0+2], 1
0x14003ddd6  jmp     short loc_14003DDDF
0x14003ddd8  mov     byte ptr [rsp+1E0h+var_1A0+2], 0
0x14003dddd  mov     dl, 1
0x14003dddf  mov     byte ptr [rsp+1E0h+var_1A0+1], dl
0x14003dde3  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ddea  mov     eax, [rcx+2Ch]
0x14003dded  test    al, 20h
0x14003ddef  jz      short loc_14003DE20
0x14003ddf1  cmp     [rcx+29h], r14b
0x14003ddf5  jb      short loc_14003DE20
0x14003ddf7  mov     rcx, [rcx+18h]
0x14003ddfb  lea     rax, aIsNot; "IS NOT"
0x14003de02  test    dl, dl
0x14003de04  lea     r9, aIs; "IS"
0x14003de0b  mov     edx, 20h ; ' '
0x14003de10  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14003de17  cmovz   r9, rax
0x14003de1b  call    WPP_SF_s
0x14003de20  mov     rcx, cs:WPP_GLOBAL_Control
0x14003de27  mov     eax, [rcx+2Ch]
0x14003de2a  test    al, 20h
0x14003de2c  jz      short loc_14003DE57
0x14003de2e  cmp     [rcx+29h], r14b
0x14003de32  jb      short loc_14003DE57
0x14003de34  mov     eax, [r13+1C0h]
0x14003de3b  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14003de42  mov     rcx, [rcx+18h]
0x14003de46  mov     edx, 21h ; '!'
0x14003de4b  mov     r9d, edi
0x14003de4e  mov     dword ptr [rsp+1E0h+var_1C0], eax
0x14003de52  call    WPP_SF_dd
0x14003de57  cmp     edi, [r13+1C0h]
0x14003de5e  jbe     short loc_14003DEBC
0x14003de60  mov     edx, edi; NumberOfBytes
0x14003de62  mov     ecx, 1; PoolType
0x14003de67  mov     r8d, 44527077h; Tag
0x14003de6d  call    cs:__imp_ExAllocatePoolWithTag
0x14003de74  nop     dword ptr [rax+rax+00h]
0x14003de79  mov     r15, rax
0x14003de7c  test    rax, rax
0x14003de7f  jnz     short loc_14003DE8B
0x14003de81  mov     edi, 0C000009Ah
0x14003de86  jmp     loc_14003DFC5
0x14003de8b  mov     rcx, cs:WPP_GLOBAL_Control
0x14003de92  xor     r12d, r12d
0x14003de95  mov     eax, [rcx+2Ch]
0x14003de98  test    al, 20h
0x14003de9a  jz      short loc_14003DF03
0x14003de9c  cmp     [rcx+29h], r14b
0x14003dea0  jb      short loc_14003DF03
0x14003dea2  mov     rcx, [rcx+18h]
0x14003dea6  lea     edx, [r12+22h]
0x14003deab  mov     r9d, edi
0x14003deae  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14003deb5  call    WPP_SF_d
0x14003deba  jmp     short loc_14003DF03
0x14003debc  lea     rcx, [r13+200h]; Lookaside
0x14003dec3  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14003deca  nop     dword ptr [rax+rax+00h]
0x14003decf  mov     r12, rax
0x14003ded2  test    rax, rax
0x14003ded5  jz      short loc_14003DE81
0x14003ded7  mov     r15, rax
0x14003deda  mov     rcx, cs:WPP_GLOBAL_Control
0x14003dee1  mov     eax, [rcx+2Ch]
0x14003dee4  test    al, 20h
0x14003dee6  jz      short loc_14003DF03
0x14003dee8  cmp     [rcx+29h], r14b
0x14003deec  jb      short loc_14003DF03
0x14003deee  mov     rcx, [rcx+18h]
0x14003def2  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14003def9  mov     edx, 23h ; '#'
  ... truncated ...
```
