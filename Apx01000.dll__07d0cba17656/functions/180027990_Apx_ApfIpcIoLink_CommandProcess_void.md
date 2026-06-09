# Apx::ApfIpcIoLink::CommandProcess(void)

- ea: `0x180027990`
- end: `0x180027ffe`
- name: `?CommandProcess@ApfIpcIoLink@Apx@@QEAAXXZ`
- size: `1646`
- prototype: `void __fastcall(unsigned __int64 this)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180028730`

## callees

- `0x180001d30`
- `0x180002100`
- `0x18000213c`
- `0x1800027c8`
- `0x18000a12c`
- `0x18000a1b4`
- `0x18000afac`
- `0x18000ba84`
- `0x18000bd94`
- `0x18000c7ec`
- `0x18001051c`
- `0x180011e6c`
- `0x18002769c`
- `0x180027800`
- `0x1800278d8`
- `0x180027990`
- `0x18002812c`
- `0x180029118`
- `0x1800292ec`
- `0x18002a010`

## pseudocode

```c
void __fastcall Apx::ApfIpcIoLink::CommandProcess(unsigned __int64 this)
{
  _DWORD *v2; // rdi
  _QWORD *v3; // rcx
  __int64 v4; // rax
  int v5; // eax
  int v6; // eax
  struct APF_MESSAGE_REPLY_COMMAND *v7; // rsi
  unsigned __int64 v8; // r13
  __int64 v9; // r8
  signed int v10; // r15d
  char *v11; // r10
  unsigned __int64 nInBufferSize; // r13
  unsigned int v13; // eax
  unsigned __int64 v14; // rax
  struct APF_MESSAGE_REPLY_COMMAND *v15; // rax
  __int64 v16; // rdx
  int v17; // ecx
  char *v18; // rax
  int v19; // eax
  const char *v20; // r9
  int v21; // r15d
  const char *v22; // r9
  const struct std::nothrow_t *v23; // rdx
  DWORD NumberOfBytesTransferred; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v25; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v26; // [rsp+68h] [rbp-98h]
  __int128 v27; // [rsp+78h] [rbp-88h]
  _DWORD v28[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v29; // [rsp+98h] [rbp-68h]
  __int16 v30; // [rsp+A8h] [rbp-58h]
  __int16 v31; // [rsp+AAh] [rbp-56h]
  __int64 v32; // [rsp+C0h] [rbp-40h]
  int v33; // [rsp+C8h] [rbp-38h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids);
  }
  v2 = *(_DWORD **)(this + 256);
  NumberOfBytesTransferred = 0;
  v25 = 0;
  v26 = 0;
  v27 = 0;
  memset_0(v28, 0, 0x1B8u);
  if ( Apx::ApfIpcIoLink::StartOperation((Apx::ApfIpcIoLink *)this) )
  {
    v4 = *(_QWORD *)(this + 64);
    *(_QWORD *)&v25 = 48;
    v26 = 0u;
    *((_QWORD *)&v25 + 1) = v4;
    v27 = 0;
    memset_0(v2, 0, 0x318u);
    v5 = Apx::ApfHelper::SyncIoctl(
           *(void **)(this + 112),
           0,
           0x1DC044u,
           &v25,
           0x30u,
           v2,
           0x318u,
           &NumberOfBytesTransferred,
           *(void **)(this + 416));
    if ( v5 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids, ~this, v5);
      }
LABEL_77:
      Apx::ApfIpcIoLink::EndOperation((Apx::ApfIpcIoLink *)this);
      goto LABEL_78;
    }
    v6 = Apx::ApfHelper::ValidateMessageHeader((struct APF_MESSAGE_HEADER *)v2, NumberOfBytesTransferred);
    if ( v6 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_qd(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids, ~this, v6);
      }
LABEL_71:
      if ( !*(_BYTE *)(this + 432)
        && (int)Apx::ApfWorkItemQueue::AddWorkItemToQueue(
                  (Apx::ApfWorkItemQueue *)(this + 120),
                  (struct Apx::ApfWorkItemBase *)(this + 240)) < 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids);
      }
      goto LABEL_77;
    }
    v7 = (struct APF_MESSAGE_REPLY_COMMAND *)v28;
    memset_0(v28, 0, 0x48u);
    v28[0] = 72;
    v8 = NumberOfBytesTransferred;
    v28[1] = 2;
    v29 = *((_QWORD *)v2 + 1);
    v30 = *((_WORD *)v2 + 12);
    v31 = *((_WORD *)v2 + 13);
    v32 = *((_QWORD *)v2 + 2);
    v33 = -1073741811;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_a14efb7a51f43eb0e09e57a52721e26b_Traceguids);
    }
    v10 = Apx::ApfHelper::ValidateMessageHeader((struct APF_MESSAGE_HEADER *)v2, v8);
    if ( v10 >= 0 )
      v10 = v8 < (unsigned int)*v2 + (unsigned __int64)(unsigned int)v2[7] ? 0x80004005 : 0;
    v11 = (char *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_a14efb7a51f43eb0e09e57a52721e26b_Traceguids);
      v11 = (char *)WPP_GLOBAL_Control;
    }
    if ( v10 < 0 )
    {
      LODWORD(nInBufferSize) = 72;
      if ( v11 != (char *)&WPP_GLOBAL_Control && v11[28] < 0 && (unsigned __int8)v11[25] >= 3u )
        WPP_SF_qd(*((_QWORD *)v11 + 2), 56, &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids, ~this, v10);
LABEL_63:
      Apx::ApfIpcIoLink::ApfLogReplyCmd((Apx::ApfIpcIoLink *)this, v7);
      v21 = Apx::ApfHelper::SyncIoctl(
              *(void **)(this + 112),
              0x1388u,
              0x1DC048u,
              v7,
              nInBufferSize,
              0,
              0,
              &NumberOfBytesTransferred,
              *(void **)(this + 416));
      Apx::ApfIpcIoLink::ApfLogReplyCmdResult((Apx::ApfIpcIoLink *)this, v7, v21, v22);
      if ( v21 < 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 28) < 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_qqd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          58,
          &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids,
          ~this,
          v2,
          v21);
      }
      if ( v7 != (struct APF_MESSAGE_REPLY_COMMAND *)v28 && v7 )
        operator delete(v7, v23);
      goto LABEL_71;
    }
    v13 = 0x7FFFFFFF;
    if ( v2[8] < 0x7FFFFFFFu )
      v13 = v2[8];
    nInBufferSize = v13 + 72LL;
    if ( nInBufferSize > 0x1B8 )
    {
      v14 = 8 * ((nInBufferSize >> 3) + 1);
      if ( !is_mul_ok((nInBufferSize >> 3) + 1, 8u) )
        v14 = -1;
      v15 = (struct APF_MESSAGE_REPLY_COMMAND *)operator new[](v14, (const struct std::nothrow_t *)&std::nothrow);
      v7 = v15;
      if ( !v15 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 28) < 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_qdd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            57,
            &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids,
            ~this,
            nInBufferSize,
            -2147024882);
        }
        v7 = (struct APF_MESSAGE_REPLY_COMMAND *)v28;
        v33 = -1073741670;
        goto LABEL_63;
      }
      memset_0(v15, 0, 0x48u);
      *(_DWORD *)v7 = 72;
      *((_DWORD *)v7 + 1) = 2;
      *((_QWORD *)v7 + 1) = *((_QWORD *)v2 + 1);
      *((_WORD *)v7 + 12) = *((_WORD *)v2 + 12);
      *((_WORD *)v7 + 13) = *((_WORD *)v2 + 13);
      *((_QWORD *)v7 + 6) = *((_QWORD *)v2 + 2);
      *((_DWORD *)v7 + 14) = -1073741811;
      v11 = (char *)WPP_GLOBAL_Control;
    }
    if ( (v2[1] & 0x10) != 0 )
    {
      if ( v11 != (char *)&WPP_GLOBAL_Control && v11[28] < 0 && (unsigned __int8)v11[25] >= 5u )
      {
        v16 = 66;
LABEL_56:
        WPP_SF_iqidD(
          *((_QWORD *)v11 + 2),
          v16,
          v9,
          *(_QWORD *)(this + 64),
          v2,
          *((_QWORD *)v2 + 2),
          *((unsigned __int16 *)v2 + 12),
          *((unsigned __int16 *)v2 + 13));
      }
    }
    else if ( v11 != (char *)&WPP_GLOBAL_Control && v11[28] < 0 && (unsigned __int8)v11[25] >= 4u )
    {
      v16 = 67;
      goto LABEL_56;
    }
    v17 = v2[8];
    if ( v17 )
      v18 = (char *)v7 + *(unsigned int *)v7;
    else
      v18 = 0;
    v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _DWORD *, _QWORD, char *, int, DWORD *))(this + 88))(
            *(_QWORD *)(this + 96),
            *((unsigned __int16 *)v2 + 12),
            v2,
            (unsigned int)(*v2 + v2[7]),
            v18,
            v17,
            &NumberOfBytesTransferred);
    *((_DWORD *)v7 + 14) = v19;
    *((_QWORD *)v7 + 8) = NumberOfBytesTransferred;
    if ( v19 >= 0 )
      *((_DWORD *)v7 + 7) = NumberOfBytesTransferred;
    Apx::ApfIpcIoLink::ApfLogCmdResult((Apx::ApfIpcIoLink *)this, (struct APF_MESSAGE_COMMAND *)v2, v19, v20);
    goto LABEL_63;
  }
  v3 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    return;
  if ( *((char *)WPP_GLOBAL_Control + 28) < 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_qqd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      53,
      &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids,
      ~this,
      *(_QWORD *)(this + 64),
      -2147467260);
LABEL_78:
    v3 = WPP_GLOBAL_Control;
  }
  if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 1) != 0 && *((_BYTE *)v3 + 25) >= 5u )
    WPP_SF_(v3[2], 60, &WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids);
}

```

## disassembly

```asm
0x180027990  push    rbp
0x180027992  push    rbx
0x180027993  push    rsi
0x180027994  push    rdi
0x180027995  push    r13
0x180027997  push    r15
0x180027999  lea     rbp, [rsp-168h]
0x1800279a1  sub     rsp, 268h
0x1800279a8  mov     rax, cs:__security_cookie
0x1800279af  xor     rax, rsp
0x1800279b2  mov     [rbp+190h+var_40], rax
0x1800279b9  mov     rbx, rcx
0x1800279bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800279c3  lea     r15, WPP_GLOBAL_Control
0x1800279ca  cmp     rcx, r15
0x1800279cd  jz      short loc_1800279F0
0x1800279cf  test    byte ptr [rcx+1Ch], 1
0x1800279d3  jz      short loc_1800279F0
0x1800279d5  cmp     byte ptr [rcx+19h], 5
0x1800279d9  jb      short loc_1800279F0
0x1800279db  mov     rcx, [rcx+10h]
0x1800279df  lea     r8, WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids
0x1800279e6  mov     edx, 34h ; '4'
0x1800279eb  call    WPP_SF_
0x1800279f0  mov     rdi, [rbx+100h]
0x1800279f7  lea     rcx, [rbp+190h+var_200]; void *
0x1800279fb  xorps   xmm0, xmm0
0x1800279fe  xor     r13d, r13d
0x180027a01  xor     edx, edx; Val
0x180027a03  mov     [rsp+290h+NumberOfBytesTransferred], r13d
0x180027a08  mov     r8d, 1B8h; Size
0x180027a0e  movups  [rsp+290h+var_238], xmm0
0x180027a13  movups  [rsp+290h+var_228], xmm0
0x180027a18  movups  [rsp+290h+var_218], xmm0
0x180027a1d  call    memset_0
0x180027a22  mov     rcx, rbx; this
0x180027a25  call    ?StartOperation@ApfIpcIoLink@Apx@@AEAA_NXZ; Apx::ApfIpcIoLink::StartOperation(void)
0x180027a2a  test    al, al
0x180027a2c  jnz     short loc_180027A82
0x180027a2e  mov     rcx, cs:WPP_GLOBAL_Control
0x180027a35  cmp     rcx, r15
0x180027a38  jz      loc_180027FDF
0x180027a3e  test    byte ptr [rcx+1Ch], 80h
0x180027a42  jz      loc_180027FB9
0x180027a48  cmp     byte ptr [rcx+19h], 4
0x180027a4c  jb      loc_180027FB9
0x180027a52  mov     rax, [rbx+40h]
0x180027a56  lea     edx, [r13+35h]
0x180027a5a  mov     rcx, [rcx+10h]
0x180027a5e  lea     r8, WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids
0x180027a65  mov     r9, rbx
0x180027a68  mov     dword ptr [rsp+290h+var_268], 80004004h
0x180027a70  not     r9
0x180027a73  mov     qword ptr [rsp+290h+nInBufferSize], rax
0x180027a78  call    WPP_SF_qqd
0x180027a7d  jmp     loc_180027FB2
0x180027a82  mov     rax, [rbx+40h]
0x180027a86  xorps   xmm0, xmm0
0x180027a89  mov     esi, 318h
0x180027a8e  mov     qword ptr [rsp+290h+var_238], 30h ; '0'
0x180027a97  mov     r8d, esi; Size
0x180027a9a  mov     qword ptr [rsp+290h+var_228], r13
0x180027a9f  xor     edx, edx; Val
0x180027aa1  mov     qword ptr [rsp+290h+var_238+8], rax
0x180027aa6  mov     rcx, rdi; void *
0x180027aa9  mov     qword ptr [rsp+290h+var_228+8], r13
0x180027aae  movdqu  [rsp+290h+var_218], xmm0
0x180027ab4  call    memset_0
0x180027ab9  mov     rax, [rbx+1A0h]
0x180027ac0  lea     r9, [rsp+290h+var_238]; void *
0x180027ac5  mov     rcx, [rbx+70h]; void *
0x180027ac9  xor     edx, edx; unsigned int
0x180027acb  mov     [rsp+290h+var_250], rax; void *
0x180027ad0  mov     r8d, 1DC044h; unsigned int
0x180027ad6  lea     rax, [rsp+290h+NumberOfBytesTransferred]
0x180027adb  mov     [rsp+290h+lpNumberOfBytesTransferred], rax; lpNumberOfBytesTransferred
0x180027ae0  mov     [rsp+290h+var_260], esi; DWORD
0x180027ae4  mov     [rsp+290h+var_268], rdi; void *
0x180027ae9  mov     [rsp+290h+nInBufferSize], 30h ; '0'; nInBufferSize
0x180027af1  call    ?SyncIoctl@ApfHelper@Apx@@SAJPEAXKK0K0KPEAK0@Z; Apx::ApfHelper::SyncIoctl(void *,ulong,ulong,void *,ulong,void *,ulong,ulong *,void *)
0x180027af6  test    eax, eax
0x180027af8  jns     short loc_180027B42
0x180027afa  mov     rcx, cs:WPP_GLOBAL_Control
0x180027b01  cmp     rcx, r15
0x180027b04  jz      loc_180027FAA
0x180027b0a  test    byte ptr [rcx+1Ch], 80h
0x180027b0e  jz      loc_180027FAA
0x180027b14  cmp     byte ptr [rcx+19h], 3
0x180027b18  jb      loc_180027FAA
0x180027b1e  mov     rcx, [rcx+10h]
0x180027b22  lea     r8, WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids
0x180027b29  mov     r9, rbx
0x180027b2c  mov     [rsp+290h+nInBufferSize], eax
0x180027b30  not     r9
0x180027b33  mov     edx, 36h ; '6'
0x180027b38  call    WPP_SF_qd
0x180027b3d  jmp     loc_180027FAA
0x180027b42  mov     edx, [rsp+290h+NumberOfBytesTransferred]; unsigned int
0x180027b46  mov     rcx, rdi; struct APF_MESSAGE_HEADER *
0x180027b49  call    ?ValidateMessageHeader@ApfHelper@Apx@@SAJPEAUAPF_MESSAGE_HEADER@@K@Z; Apx::ApfHelper::ValidateMessageHeader(APF_MESSAGE_HEADER *,ulong)
0x180027b4e  test    eax, eax
0x180027b50  jns     short loc_180027B9A
0x180027b52  mov     rcx, cs:WPP_GLOBAL_Control
0x180027b59  cmp     rcx, r15
0x180027b5c  jz      loc_180027F5D
0x180027b62  test    byte ptr [rcx+1Ch], 80h
0x180027b66  jz      loc_180027F5D
0x180027b6c  cmp     byte ptr [rcx+19h], 3
0x180027b70  jb      loc_180027F5D
0x180027b76  mov     rcx, [rcx+10h]
0x180027b7a  lea     r8, WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids
0x180027b81  mov     r9, rbx
0x180027b84  mov     [rsp+290h+nInBufferSize], eax
0x180027b88  not     r9
0x180027b8b  mov     edx, 37h ; '7'
0x180027b90  call    WPP_SF_qd
0x180027b95  jmp     loc_180027F5D
0x180027b9a  mov     r13d, 48h ; 'H'
0x180027ba0  lea     rcx, [rbp+190h+var_200]; void *
0x180027ba4  mov     r8d, r13d; Size
0x180027ba7  lea     rsi, [rbp+190h+var_200]
0x180027bab  xor     edx, edx; Val
0x180027bad  call    memset_0
0x180027bb2  mov     [rbp+190h+var_200], r13d
0x180027bb6  mov     r13d, [rsp+290h+NumberOfBytesTransferred]
0x180027bbb  mov     [rbp+190h+var_1FC], 2
0x180027bc2  mov     rax, [rdi+8]
0x180027bc6  mov     [rbp+190h+var_1F8], rax
0x180027bca  movzx   eax, word ptr [rdi+18h]
0x180027bce  mov     [rbp+190h+var_1E8], ax
0x180027bd2  movzx   eax, word ptr [rdi+1Ah]
0x180027bd6  mov     [rbp+190h+var_1E6], ax
0x180027bda  mov     rax, [rdi+10h]
0x180027bde  mov     [rbp+190h+var_1D0], rax
0x180027be2  mov     [rbp+190h+var_1C8], 0C000000Dh
0x180027be9  mov     rcx, cs:WPP_GLOBAL_Control
0x180027bf0  cmp     rcx, r15
0x180027bf3  jz      short loc_180027C16
0x180027bf5  test    byte ptr [rcx+1Ch], 1
0x180027bf9  jz      short loc_180027C16
0x180027bfb  cmp     byte ptr [rcx+19h], 5
0x180027bff  jb      short loc_180027C16
0x180027c01  mov     rcx, [rcx+10h]
0x180027c05  lea     r8, WPP_a14efb7a51f43eb0e09e57a52721e26b_Traceguids
0x180027c0c  mov     edx, 1Fh
0x180027c11  call    WPP_SF_
0x180027c16  mov     edx, r13d; unsigned int
0x180027c19  mov     rcx, rdi; struct APF_MESSAGE_HEADER *
0x180027c1c  call    ?ValidateMessageHeader@ApfHelper@Apx@@SAJPEAUAPF_MESSAGE_HEADER@@K@Z; Apx::ApfHelper::ValidateMessageHeader(APF_MESSAGE_HEADER *,ulong)
0x180027c21  mov     r15d, eax
0x180027c24  test    eax, eax
0x180027c26  js      short loc_180027C3D
0x180027c28  mov     ecx, [rdi+1Ch]
0x180027c2b  mov     eax, [rdi]
0x180027c2d  add     rcx, rax
0x180027c30  cmp     r13, rcx
0x180027c33  sbb     r15d, r15d
0x180027c36  and     r15d, 80004005h
0x180027c3d  mov     r10, cs:WPP_GLOBAL_Control
0x180027c44  lea     rax, WPP_GLOBAL_Control
0x180027c4b  cmp     r10, rax
0x180027c4e  jz      short loc_180027C81
0x180027c50  test    byte ptr [r10+1Ch], 1
0x180027c55  jz      short loc_180027C81
0x180027c57  cmp     byte ptr [r10+19h], 5
0x180027c5c  jb      short loc_180027C81
0x180027c5e  mov     rcx, [r10+10h]
0x180027c62  lea     r8, WPP_a14efb7a51f43eb0e09e57a52721e26b_Traceguids
0x180027c69  mov     edx, 20h ; ' '
0x180027c6e  call    WPP_SF_
0x180027c73  mov     r10, cs:WPP_GLOBAL_Control
0x180027c7a  lea     rax, WPP_GLOBAL_Control
0x180027c81  test    r15d, r15d
0x180027c84  jns     short loc_180027CCF
0x180027c86  mov     r13d, 48h ; 'H'
0x180027c8c  cmp     r10, rax
0x180027c8f  jz      loc_180027E96
0x180027c95  test    byte ptr [r10+1Ch], 80h
0x180027c9a  jz      loc_180027E96
0x180027ca0  cmp     byte ptr [r10+19h], 3
0x180027ca5  jb      loc_180027E96
0x180027cab  mov     rcx, [r10+10h]
0x180027caf  lea     edx, [r13-10h]
0x180027cb3  mov     r9, rbx
0x180027cb6  mov     [rsp+290h+nInBufferSize], r15d
0x180027cbb  not     r9
0x180027cbe  lea     r8, WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids
0x180027cc5  call    WPP_SF_qd
0x180027cca  jmp     loc_180027E96
0x180027ccf  mov     eax, 7FFFFFFFh
0x180027cd4  cmp     [rdi+20h], eax
0x180027cd7  cmovb   eax, [rdi+20h]
0x180027cdb  mov     r13d, eax
0x180027cde  add     r13, 48h ; 'H'
0x180027ce2  cmp     r13, 1B8h
0x180027ce9  jbe     loc_180027DC3
0x180027cef  mov     rcx, r13
0x180027cf2  mov     eax, 8
0x180027cf7  shr     rcx, 3
0x180027cfb  inc     rcx
0x180027cfe  mul     rcx
0x180027d01  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180027d08  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180027d0f  cmovb   rax, rcx
0x180027d13  mov     rcx, rax; unsigned __int64
0x180027d16  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180027d1b  mov     rsi, rax
0x180027d1e  test    rax, rax
0x180027d21  jnz     short loc_180027D78
0x180027d23  mov     rcx, cs:WPP_GLOBAL_Control
0x180027d2a  lea     rax, WPP_GLOBAL_Control
0x180027d31  cmp     rcx, rax
0x180027d34  jz      short loc_180027D68
0x180027d36  test    byte ptr [rcx+1Ch], 80h
0x180027d3a  jz      short loc_180027D68
0x180027d3c  cmp     byte ptr [rcx+19h], 2
0x180027d40  jb      short loc_180027D68
0x180027d42  mov     rcx, [rcx+10h]
0x180027d46  lea     edx, [rsi+39h]
0x180027d49  mov     r9, rbx
0x180027d4c  mov     dword ptr [rsp+290h+var_268], 8007000Eh
0x180027d54  not     r9
0x180027d57  mov     [rsp+290h+nInBufferSize], r13d
0x180027d5c  lea     r8, WPP_2d35061b702c341682ff2b4d4ce7d817_Traceguids
0x180027d63  call    WPP_SF_qdd
0x180027d68  lea     rsi, [rbp+190h+var_200]
0x180027d6c  mov     [rbp+190h+var_1C8], 0C000009Ah
0x180027d73  jmp     loc_180027E96
0x180027d78  mov     r15d, 48h ; 'H'
0x180027d7e  xor     edx, edx; Val
0x180027d80  mov     r8d, r15d; Size
0x180027d83  mov     rcx, rsi; void *
0x180027d86  call    memset_0
0x180027d8b  mov     [rsi], r15d
0x180027d8e  mov     dword ptr [rsi+4], 2
0x180027d95  mov     rax, [rdi+8]
0x180027d99  mov     [rsi+8], rax
0x180027d9d  movzx   eax, word ptr [rdi+18h]
0x180027da1  mov     [rsi+18h], ax
0x180027da5  movzx   eax, word ptr [rdi+1Ah]
0x180027da9  mov     [rsi+1Ah], ax
0x180027dad  mov     rax, [rdi+10h]
0x180027db1  mov     [rsi+30h], rax
0x180027db5  mov     dword ptr [rsi+38h], 0C000000Dh
0x180027dbc  mov     r10, cs:WPP_GLOBAL_Control
0x180027dc3  test    byte ptr [rdi+4], 10h
0x180027dc7  jz      short loc_180027DEA
0x180027dc9  lea     rax, WPP_GLOBAL_Control
0x180027dd0  cmp     r10, rax
0x180027dd3  jz      short loc_180027E34
0x180027dd5  test    byte ptr [r10+1Ch], 80h
0x180027dda  jz      short loc_180027E34
0x180027ddc  cmp     byte ptr [r10+19h], 5
0x180027de1  jb      short loc_180027E34
0x180027de3  mov     edx, 42h ; 'B'
0x180027de8  jmp     short loc_180027E09
0x180027dea  lea     rax, WPP_GLOBAL_Control
0x180027df1  cmp     r10, rax
0x180027df4  jz      short loc_180027E34
0x180027df6  test    byte ptr [r10+1Ch], 80h
0x180027dfb  jz      short loc_180027E34
0x180027dfd  cmp     byte ptr [r10+19h], 4
0x180027e02  jb      short loc_180027E34
0x180027e04  mov     edx, 43h ; 'C'
0x180027e09  movzx   eax, word ptr [rdi+1Ah]
0x180027e0d  movzx   ecx, word ptr [rdi+18h]
0x180027e11  mov     r9, [rbx+40h]
0x180027e15  mov     dword ptr [rsp+290h+lpNumberOfBytesTransferred], eax
0x180027e19  mov     rax, [rdi+10h]
0x180027e1d  mov     [rsp+290h+var_260], ecx
0x180027e21  mov     rcx, [r10+10h]
0x180027e25  mov     [rsp+290h+var_268], rax
0x180027e2a  mov     qword ptr [rsp+290h+nInBufferSize], rdi
0x180027e2f  call    WPP_SF_iqidD
0x180027e34  mov     ecx, [rdi+20h]
0x180027e37  test    ecx, ecx
0x180027e39  jz      short loc_180027E42
0x180027e3b  mov     eax, [rsi]
0x180027e3d  add     rax, rsi
0x180027e40  jmp     short loc_180027E44
0x180027e42  xor     eax, eax
0x180027e44  mov     r9d, [rdi+1Ch]
0x180027e48  lea     rdx, [rsp+290h+NumberOfBytesTransferred]
0x180027e4d  add     r9d, [rdi]
0x180027e50  mov     r8, rdi
0x180027e53  mov     qword ptr [rsp+290h+var_260], rdx
0x180027e58  movzx   edx, word ptr [rdi+18h]
0x180027e5c  mov     dword ptr [rsp+290h+var_268], ecx
0x180027e60  mov     rcx, [rbx+60h]
0x180027e64  mov     qword ptr [rsp+290h+nInBufferSize], rax
0x180027e69  mov     rax, [rbx+58h]
0x180027e6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027e72  mov     [rsi+38h], eax
0x180027e75  mov     ecx, [rsp+290h+NumberOfBytesTransferred]
0x180027e79  mov     [rsi+40h], rcx
0x180027e7d  test    eax, eax
0x180027e7f  js      short loc_180027E88
0x180027e81  mov     ecx, [rsp+290h+NumberOfBytesTransferred]
0x180027e85  mov     [rsi+1Ch], ecx
0x180027e88  mov     r8d, eax; int
  ... truncated ...
```
