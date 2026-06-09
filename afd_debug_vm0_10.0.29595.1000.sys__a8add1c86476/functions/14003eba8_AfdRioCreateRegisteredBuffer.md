# AfdRioCreateRegisteredBuffer

- ea: `0x14003eba8`
- end: `0x14003ed69`
- name: `AfdRioCreateRegisteredBuffer`
- size: `449`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14006c56c`

## callees

- `0x14003eba8`
- `0x14006c028`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14003eccc`
- `ntoskrnl!ExAllocatePool2` at `0x14003eccc`
- `NDIS!NdisAcquireRWLockWrite` at `0x14003ebf2`
- `NDIS!NdisAcquireRWLockWrite` at `0x14003ebf2`
- `NDIS!NdisReleaseRWLock` at `0x14003ec10`
- `NDIS!NdisReleaseRWLock` at `0x14003eca8`
- `NDIS!NdisReleaseRWLock` at `0x14003ecf9`
- `NDIS!NdisReleaseRWLock` at `0x14003ed42`
- `NDIS!NdisReleaseRWLock` at `0x14003ec10`
- `NDIS!NdisReleaseRWLock` at `0x14003eca8`
- `NDIS!NdisReleaseRWLock` at `0x14003ecf9`
- `NDIS!NdisReleaseRWLock` at `0x14003ed42`

## pseudocode

```c
__int64 __fastcall AfdRioCreateRegisteredBuffer(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        unsigned int *a5,
        __int64 *a6)
{
  __int64 Pool2; // r8
  char v11; // r9
  char v12; // r10
  unsigned int v13; // edi
  _QWORD *v14; // r14
  unsigned int *v15; // r11
  unsigned int v16; // eax
  unsigned int v17; // ecx
  int v18; // esi
  struct _LOCK_STATE_EX LockState; // [rsp+20h] [rbp-38h] BYREF
  __int64 v20; // [rsp+28h] [rbp-30h]

  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  *a6 = 0;
  NdisAcquireRWLockWrite(*(PNDIS_RW_LOCK_EX *)(a1 + 96), &LockState, 0);
  if ( *(_BYTE *)(a1 + 136) )
  {
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 96), &LockState);
    return 3221225860LL;
  }
  Pool2 = 0;
  v11 = 1;
  v12 = 1;
  v13 = *(_DWORD *)(a1 + 124);
  v14 = (_QWORD *)(a1 + 104);
  v15 = (unsigned int *)(a1 + 120);
  while ( 1 )
  {
    if ( !v13 )
      goto LABEL_7;
    Pool2 = *(_QWORD *)(*v14 + 8LL * v13);
    if ( !Pool2 )
      break;
    if ( *(_DWORD *)(Pool2 + 32) == 2 )
    {
      v11 = 0;
      goto LABEL_13;
    }
LABEL_7:
    v16 = v13;
    v17 = v13 + 1;
    v13 = 0;
    if ( v16 != *v15 - 1 )
      v13 = v17;
    if ( v13 == *(_DWORD *)(a1 + 124) )
      goto LABEL_14;
  }
  v12 = 0;
LABEL_13:
  *(_DWORD *)(a1 + 124) = v13;
LABEL_14:
  if ( v11 )
  {
    if ( v12 )
    {
      v13 = *v15;
      v18 = AfdRioGrowTable(a1 + 104, a1 + 120, 1649363282);
      if ( v18 < 0 )
      {
        NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 96), &LockState);
        return (unsigned int)v18;
      }
      *(_DWORD *)(a1 + 124) = v13;
    }
    Pool2 = ExAllocatePool2(97, 48, 1649363282);
    v20 = Pool2;
    *(_QWORD *)(*v14 + 8LL * v13) = Pool2;
  }
  *(_QWORD *)Pool2 = a2;
  *(_QWORD *)(Pool2 + 8) = a3;
  *(_DWORD *)(Pool2 + 16) = a4;
  *(_QWORD *)(Pool2 + 24) = 1;
  *(_DWORD *)(Pool2 + 32) = 0;
  *a5 = v13;
  *a6 = Pool2;
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)(a1 + 96), &LockState);
  return 0;
}

```

## disassembly

```asm
0x14003eba8  mov     r11, rsp
0x14003ebab  mov     [r11+18h], rbx
0x14003ebaf  mov     [r11+20h], rsi
0x14003ebb3  mov     [r11+10h], rdx
0x14003ebb7  mov     [r11+8], rcx
0x14003ebbb  push    rdi
0x14003ebbc  push    r12
0x14003ebbe  push    r13
0x14003ebc0  push    r14
0x14003ebc2  push    r15
0x14003ebc4  sub     rsp, 30h
0x14003ebc8  mov     r12d, r9d
0x14003ebcb  mov     r13, r8
0x14003ebce  mov     rbx, rcx
0x14003ebd1  xor     eax, eax
0x14003ebd3  mov     word ptr [rsp+58h+LockState.OldIrql], ax
0x14003ebd8  mov     [rsp+58h+LockState.Flags], al
0x14003ebdc  mov     r15, [rsp+58h+arg_28]
0x14003ebe4  mov     [r15], rax
0x14003ebe7  xor     r8d, r8d; Flags
0x14003ebea  lea     rdx, [r11-38h]; LockState
0x14003ebee  mov     rcx, [rcx+60h]; Lock
0x14003ebf2  call    cs:__imp_NdisAcquireRWLockWrite
0x14003ebf9  nop     dword ptr [rax+rax+00h]
0x14003ebfe  cmp     byte ptr [rbx+88h], 0
0x14003ec05  jz      short loc_14003EC26
0x14003ec07  lea     rdx, [rsp+58h+LockState]; LockState
0x14003ec0c  mov     rcx, [rbx+60h]; Lock
0x14003ec10  call    cs:__imp_NdisReleaseRWLock
0x14003ec17  nop     dword ptr [rax+rax+00h]
0x14003ec1c  mov     eax, 0C0000184h
0x14003ec21  jmp     loc_14003ED50
0x14003ec26  xor     r8d, r8d
0x14003ec29  mov     r9b, 1
0x14003ec2c  mov     r10b, r9b
0x14003ec2f  mov     esi, [rbx+7Ch]
0x14003ec32  mov     edi, esi
0x14003ec34  lea     r14, [rbx+68h]
0x14003ec38  lea     r11, [rbx+78h]
0x14003ec3c  test    edi, edi
0x14003ec3e  jz      short loc_14003EC55
0x14003ec40  mov     ecx, edi
0x14003ec42  mov     rax, [r14]
0x14003ec45  mov     r8, [rax+rcx*8]
0x14003ec49  test    r8, r8
0x14003ec4c  jz      short loc_14003EC71
0x14003ec4e  cmp     dword ptr [r8+20h], 2
0x14003ec53  jz      short loc_14003EC6C
0x14003ec55  mov     edx, [r11]
0x14003ec58  dec     edx
0x14003ec5a  mov     eax, edi
0x14003ec5c  lea     ecx, [rdi+1]
0x14003ec5f  xor     edi, edi
0x14003ec61  cmp     eax, edx
0x14003ec63  cmovnz  edi, ecx
0x14003ec66  cmp     edi, esi
0x14003ec68  jz      short loc_14003EC77
0x14003ec6a  jmp     short loc_14003EC3C
0x14003ec6c  xor     r9b, r9b
0x14003ec6f  jmp     short loc_14003EC74
0x14003ec71  xor     r10b, r10b
0x14003ec74  mov     [rbx+7Ch], edi
0x14003ec77  test    r9b, r9b
0x14003ec7a  jz      loc_14003ED0C
0x14003ec80  test    r10b, r10b
0x14003ec83  jz      short loc_14003ECBE
0x14003ec85  mov     edi, [r11]
0x14003ec88  mov     r8d, 624F4952h
0x14003ec8e  mov     rdx, r11
0x14003ec91  mov     rcx, r14
0x14003ec94  call    AfdRioGrowTable
0x14003ec99  mov     esi, eax
0x14003ec9b  test    eax, eax
0x14003ec9d  jns     short loc_14003ECBB
0x14003ec9f  lea     rdx, [rsp+58h+LockState]; LockState
0x14003eca4  mov     rcx, [rbx+60h]; Lock
0x14003eca8  call    cs:__imp_NdisReleaseRWLock
0x14003ecaf  nop     dword ptr [rax+rax+00h]
0x14003ecb4  mov     eax, esi
0x14003ecb6  jmp     loc_14003ED50
0x14003ecbb  mov     [rbx+7Ch], edi
0x14003ecbe  mov     edx, 30h ; '0'
0x14003ecc3  lea     ecx, [rdx+31h]
0x14003ecc6  mov     r8d, 624F4952h
0x14003eccc  call    cs:__imp_ExAllocatePool2
0x14003ecd3  nop     dword ptr [rax+rax+00h]
0x14003ecd8  mov     r8, rax
0x14003ecdb  mov     [rsp+58h+var_30], rax
0x14003ece0  mov     ecx, edi
0x14003ece2  mov     rax, [r14]
0x14003ece5  mov     [rax+rcx*8], r8
0x14003ece9  jmp     short loc_14003ED0C
0x14003eceb  lea     rdx, [rsp+58h+LockState]; LockState
0x14003ecf0  mov     rcx, [rsp+58h+arg_0]
0x14003ecf5  mov     rcx, [rcx+60h]; Lock
0x14003ecf9  call    cs:__imp_NdisReleaseRWLock
0x14003ed00  nop     dword ptr [rax+rax+00h]
0x14003ed05  mov     eax, 0C0000017h
0x14003ed0a  jmp     short loc_14003ED50
0x14003ed0c  mov     rax, [rsp+58h+arg_8]
0x14003ed11  mov     [r8], rax
0x14003ed14  mov     [r8+8], r13
0x14003ed18  mov     [r8+10h], r12d
0x14003ed1c  mov     qword ptr [r8+18h], 1
0x14003ed24  mov     dword ptr [r8+20h], 0
0x14003ed2c  mov     rax, [rsp+58h+arg_20]
0x14003ed34  mov     [rax], edi
0x14003ed36  mov     [r15], r8
0x14003ed39  lea     rdx, [rsp+58h+LockState]; LockState
0x14003ed3e  mov     rcx, [rbx+60h]; Lock
0x14003ed42  call    cs:__imp_NdisReleaseRWLock
0x14003ed49  nop     dword ptr [rax+rax+00h]
0x14003ed4e  xor     eax, eax
0x14003ed50  mov     rbx, [rsp+58h+arg_10]
0x14003ed55  mov     rsi, [rsp+58h+arg_18]
0x14003ed5a  add     rsp, 30h
0x14003ed5e  pop     r15
0x14003ed60  pop     r14
0x14003ed62  pop     r13
0x14003ed64  pop     r12
0x14003ed66  pop     rdi
0x14003ed67  retn
```
