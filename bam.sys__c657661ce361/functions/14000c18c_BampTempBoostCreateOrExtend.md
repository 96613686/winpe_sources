# BampTempBoostCreateOrExtend

- ea: `0x14000c18c`
- end: `0x14000c3dc`
- name: `BampTempBoostCreateOrExtend`
- size: `592`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x140012eec`

## callees

- `0x140001430`
- `0x1400026d0`
- `0x140002ac0`
- `0x14000b978`
- `0x14000be6c`
- `0x14000c18c`
- `0x14000c464`
- `0x1400113a0`
- `0x1400113f0`
- `0x140011430`
- `0x140011520`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000c1c0`
- `ntoskrnl!ExAllocatePool2` at `0x14000c1c0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c2b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c2b2`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14000c1f6`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x14000c1f6`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x14000c343`
- `ntoskrnl!RtlRbInsertNodeEx` at `0x14000c343`

## pseudocode

```c
__int64 __fastcall BampTempBoostCreateOrExtend(int a1)
{
  _DWORD *Pool2; // rax
  _DWORD *v3; // rsi
  unsigned int v4; // ebx
  ULONGLONG v5; // rbp
  __int64 v6; // r8
  unsigned __int64 v7; // rbx
  int v8; // edi
  int v9; // eax
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rbx
  int v12; // edi
  unsigned __int64 v13; // rax
  int v15; // [rsp+30h] [rbp-78h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v16; // [rsp+38h] [rbp-70h] BYREF
  int *v17; // [rsp+58h] [rbp-50h]
  __int64 v18; // [rsp+60h] [rbp-48h]
  int v19; // [rsp+B0h] [rbp+8h] BYREF

  v19 = a1;
  Pool2 = (_DWORD *)ExAllocatePool2(256, 64, 1265459522);
  v3 = Pool2;
  if ( !Pool2 )
  {
    v4 = -1073741801;
    goto LABEL_37;
  }
  memset(Pool2, 0, 0x40u);
  v3[6] = a1;
  v3[14] = 3;
  v5 = KeQueryUnbiasedInterruptTime() + 50000000;
  BampAcquireTempBoostsLockExclusive();
  v7 = BampTempBoosts;
  if ( (BYTE8(BampTempBoosts) & 1) != 0 && (_QWORD)BampTempBoosts )
    v7 = (unsigned __int64)&BampTempBoosts ^ BampTempBoosts;
  v8 = BYTE8(BampTempBoosts) & 1;
  if ( v7 )
  {
    do
    {
      v9 = BampTempBoostsTreeCompareRoutine(&v19, v7);
      if ( v9 >= 0 )
      {
        if ( v9 <= 0 )
          break;
        v10 = *(_QWORD *)(v7 + 8);
      }
      else
      {
        v10 = *(_QWORD *)v7;
      }
      if ( v8 && v10 )
        v7 ^= v10;
      else
        v7 = v10;
    }
    while ( v7 );
    if ( v7 )
    {
      BampAcquireThrottlingWorkerLock();
      if ( (*(_BYTE *)(v7 + 48) & 1) != 0 )
      {
        BampRemoveThrottlingActionItem(v7 + 32);
        *(_QWORD *)(v7 + 48) = v5 & 0xFFFFFFFFFFFFFFFEuLL;
        BampInsertThrottlingActionItem(v7 + 32);
        v4 = 0;
        BampReleaseThrottlingWorkerLock();
        BampReleaseTempBoostsLockExclusive();
        ExFreePoolWithTag(v3, 0x4B6D6142u);
        goto LABEL_37;
      }
      BampReleaseThrottlingWorkerLock();
    }
  }
  v11 = BampTempBoosts;
  if ( (BYTE8(BampTempBoosts) & 1) != 0 && (_QWORD)BampTempBoosts )
    v11 = (unsigned __int64)&BampTempBoosts ^ BampTempBoosts;
  LOBYTE(v6) = 0;
  v12 = BYTE8(BampTempBoosts) & 1;
  if ( v11 )
  {
    while ( 1 )
    {
      if ( (int)BampTempBoostsTreeCompareRoutine(&v19, v11) < 0 )
      {
        v13 = *(_QWORD *)v11;
        if ( v12 )
        {
          if ( !v13 )
            goto LABEL_35;
          v13 ^= v11;
        }
        if ( !v13 )
        {
LABEL_35:
          LOBYTE(v6) = 0;
          break;
        }
      }
      else
      {
        v13 = *(_QWORD *)(v11 + 8);
        if ( v12 )
        {
          if ( !v13 )
            goto LABEL_29;
          v13 ^= v11;
        }
        if ( !v13 )
        {
LABEL_29:
          LOBYTE(v6) = 1;
          break;
        }
      }
      v11 = v13;
    }
  }
  RtlRbInsertNodeEx(&BampTempBoosts, v11, v6, v3);
  BampAcquireThrottlingWorkerLock();
  *((_QWORD *)v3 + 6) = v5 & 0xFFFFFFFFFFFFFFFEuLL;
  BampInsertThrottlingActionItem(v3 + 8);
  BampReleaseThrottlingWorkerLock();
  BampReleaseTempBoostsLockExclusive();
  v4 = 0;
LABEL_37:
  if ( (unsigned int)dword_140007010 > 4 )
  {
    v15 = a1;
    v17 = &v15;
    v18 = 4;
    tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140007010, (unsigned __int8 *)byte_140004A3D, 0, 0, 3u, &v16);
  }
  return v4;
}

```

## disassembly

```asm
0x14000c18c  mov     [rsp+arg_0], ecx
0x14000c190  push    rbx
0x14000c191  push    rbp
0x14000c192  push    rsi
0x14000c193  push    rdi
0x14000c194  push    r12
0x14000c196  push    r14
0x14000c198  sub     rsp, 78h
0x14000c19c  mov     rax, cs:__security_cookie
0x14000c1a3  xor     rax, rsp
0x14000c1a6  mov     [rsp+0A8h+var_40], rax
0x14000c1ab  mov     r14d, ecx
0x14000c1ae  mov     ebx, 40h ; '@'
0x14000c1b3  mov     edx, ebx
0x14000c1b5  mov     r8d, 4B6D6142h
0x14000c1bb  mov     ecx, 100h
0x14000c1c0  call    cs:__imp_ExAllocatePool2
0x14000c1c7  nop     dword ptr [rax+rax+00h]
0x14000c1cc  mov     rsi, rax
0x14000c1cf  test    rax, rax
0x14000c1d2  jnz     short loc_14000C1DE
0x14000c1d4  mov     ebx, 0C0000017h
0x14000c1d9  jmp     loc_14000C371
0x14000c1de  mov     r8, rbx; Size
0x14000c1e1  xor     edx, edx; Val
0x14000c1e3  mov     rcx, rsi; void *
0x14000c1e6  call    memset
0x14000c1eb  mov     [rsi+18h], r14d
0x14000c1ef  mov     dword ptr [rsi+38h], 3
0x14000c1f6  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x14000c1fd  nop     dword ptr [rax+rax+00h]
0x14000c202  lea     rbp, [rax+2FAF080h]
0x14000c209  call    BampAcquireTempBoostsLockExclusive
0x14000c20e  mov     rcx, qword ptr cs:BampTempBoosts+8
0x14000c215  lea     r12, BampTempBoosts
0x14000c21c  mov     rbx, qword ptr cs:BampTempBoosts
0x14000c223  test    cl, 1
0x14000c226  jz      short loc_14000C230
0x14000c228  test    rbx, rbx
0x14000c22b  jz      short loc_14000C230
0x14000c22d  xor     rbx, r12
0x14000c230  movzx   edi, cl
0x14000c233  and     edi, 1
0x14000c236  test    rbx, rbx
0x14000c239  jz      loc_14000C2C8
0x14000c23f  mov     rdx, rbx
0x14000c242  lea     rcx, [rsp+0A8h+arg_0]
0x14000c24a  call    BampTempBoostsTreeCompareRoutine
0x14000c24f  test    eax, eax
0x14000c251  jns     short loc_14000C258
0x14000c253  mov     rax, [rbx]
0x14000c256  jmp     short loc_14000C25E
0x14000c258  jle     short loc_14000C274
0x14000c25a  mov     rax, [rbx+8]
0x14000c25e  test    edi, edi
0x14000c260  jz      short loc_14000C26C
0x14000c262  test    rax, rax
0x14000c265  jz      short loc_14000C26C
0x14000c267  xor     rbx, rax
0x14000c26a  jmp     short loc_14000C26F
0x14000c26c  mov     rbx, rax
0x14000c26f  test    rbx, rbx
0x14000c272  jnz     short loc_14000C23F
0x14000c274  test    rbx, rbx
0x14000c277  jz      short loc_14000C2C8
0x14000c279  call    BampAcquireThrottlingWorkerLock
0x14000c27e  test    byte ptr [rbx+30h], 1
0x14000c282  jz      short loc_14000C2C3
0x14000c284  lea     rcx, [rbx+20h]
0x14000c288  call    BampRemoveThrottlingActionItem
0x14000c28d  and     rbp, 0FFFFFFFFFFFFFFFEh
0x14000c291  lea     rcx, [rbx+20h]
0x14000c295  mov     [rbx+30h], rbp
0x14000c299  call    BampInsertThrottlingActionItem
0x14000c29e  xor     ebx, ebx
0x14000c2a0  call    BampReleaseThrottlingWorkerLock
0x14000c2a5  call    BampReleaseTempBoostsLockExclusive
0x14000c2aa  mov     edx, 4B6D6142h; Tag
0x14000c2af  mov     rcx, rsi; P
0x14000c2b2  call    cs:__imp_ExFreePoolWithTag
0x14000c2b9  nop     dword ptr [rax+rax+00h]
0x14000c2be  jmp     loc_14000C371
0x14000c2c3  call    BampReleaseThrottlingWorkerLock
0x14000c2c8  mov     rax, qword ptr cs:BampTempBoosts+8
0x14000c2cf  mov     rbx, qword ptr cs:BampTempBoosts
0x14000c2d6  test    al, 1
0x14000c2d8  jz      short loc_14000C2E2
0x14000c2da  test    rbx, rbx
0x14000c2dd  jz      short loc_14000C2E2
0x14000c2df  xor     rbx, r12
0x14000c2e2  movzx   edi, al
0x14000c2e5  xor     r8b, r8b
0x14000c2e8  and     edi, 1
0x14000c2eb  test    rbx, rbx
0x14000c2ee  jz      short loc_14000C33A
0x14000c2f0  mov     rdx, rbx
0x14000c2f3  lea     rcx, [rsp+0A8h+arg_0]
0x14000c2fb  call    BampTempBoostsTreeCompareRoutine
0x14000c300  test    eax, eax
0x14000c302  js      short loc_14000C31E
0x14000c304  mov     rax, [rbx+8]
0x14000c308  test    edi, edi
0x14000c30a  jz      short loc_14000C314
0x14000c30c  test    rax, rax
0x14000c30f  jz      short loc_14000C319
0x14000c311  xor     rax, rbx
0x14000c314  test    rax, rax
0x14000c317  jnz     short loc_14000C332
0x14000c319  mov     r8b, 1
0x14000c31c  jmp     short loc_14000C33A
0x14000c31e  mov     rax, [rbx]
0x14000c321  test    edi, edi
0x14000c323  jz      short loc_14000C32D
0x14000c325  test    rax, rax
0x14000c328  jz      short loc_14000C337
0x14000c32a  xor     rax, rbx
0x14000c32d  test    rax, rax
0x14000c330  jz      short loc_14000C337
0x14000c332  mov     rbx, rax
0x14000c335  jmp     short loc_14000C2F0
0x14000c337  xor     r8b, r8b
0x14000c33a  mov     r9, rsi
0x14000c33d  mov     rdx, rbx
0x14000c340  mov     rcx, r12
0x14000c343  call    cs:__imp_RtlRbInsertNodeEx
0x14000c34a  nop     dword ptr [rax+rax+00h]
0x14000c34f  call    BampAcquireThrottlingWorkerLock
0x14000c354  lea     rcx, [rsi+20h]
0x14000c358  and     rbp, 0FFFFFFFFFFFFFFFEh
0x14000c35c  mov     [rcx+10h], rbp
0x14000c360  call    BampInsertThrottlingActionItem
0x14000c365  call    BampReleaseThrottlingWorkerLock
0x14000c36a  call    BampReleaseTempBoostsLockExclusive
0x14000c36f  xor     ebx, ebx
0x14000c371  mov     eax, cs:dword_140007010
0x14000c377  cmp     eax, 4
0x14000c37a  jbe     short loc_14000C3BF
0x14000c37c  lea     rax, [rsp+0A8h+var_78]
0x14000c381  mov     [rsp+0A8h+var_78], r14d
0x14000c386  mov     [rsp+0A8h+var_50], rax
0x14000c38b  lea     rdx, byte_140004A3D
0x14000c392  lea     rax, [rsp+0A8h+var_70]
0x14000c397  mov     [rsp+0A8h+var_48], 4
0x14000c3a0  mov     [rsp+0A8h+var_80], rax
0x14000c3a5  lea     rcx, dword_140007010
0x14000c3ac  xor     r9d, r9d
0x14000c3af  mov     [rsp+0A8h+var_88], 3
0x14000c3b7  xor     r8d, r8d
0x14000c3ba  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000c3bf  mov     eax, ebx
0x14000c3c1  mov     rcx, [rsp+0A8h+var_40]
0x14000c3c6  xor     rcx, rsp; StackCookie
0x14000c3c9  call    __security_check_cookie
0x14000c3ce  add     rsp, 78h
0x14000c3d2  pop     r14
0x14000c3d4  pop     r12
0x14000c3d6  pop     rdi
0x14000c3d7  pop     rsi
0x14000c3d8  pop     rbp
0x14000c3d9  pop     rbx
0x14000c3da  retn
```
