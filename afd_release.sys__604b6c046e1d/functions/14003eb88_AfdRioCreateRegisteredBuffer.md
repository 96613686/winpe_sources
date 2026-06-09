# AfdRioCreateRegisteredBuffer

- ea: `0x14003eb88`
- end: `0x14003ed49`
- name: `AfdRioCreateRegisteredBuffer`
- size: `449`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, unsigned int *, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14006c3cc`

## callees

- `0x14003eb88`
- `0x14006be88`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14003ecac`
- `ntoskrnl!ExAllocatePool2` at `0x14003ecac`
- `NDIS!NdisAcquireRWLockWrite` at `0x14003ebd2`
- `NDIS!NdisAcquireRWLockWrite` at `0x14003ebd2`
- `NDIS!NdisReleaseRWLock` at `0x14003ebf0`
- `NDIS!NdisReleaseRWLock` at `0x14003ec88`
- `NDIS!NdisReleaseRWLock` at `0x14003ecd9`
- `NDIS!NdisReleaseRWLock` at `0x14003ed22`
- `NDIS!NdisReleaseRWLock` at `0x14003ebf0`
- `NDIS!NdisReleaseRWLock` at `0x14003ec88`
- `NDIS!NdisReleaseRWLock` at `0x14003ecd9`
- `NDIS!NdisReleaseRWLock` at `0x14003ed22`

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
0x14003eb88  mov     r11, rsp
0x14003eb8b  mov     [r11+18h], rbx
0x14003eb8f  mov     [r11+20h], rsi
0x14003eb93  mov     [r11+10h], rdx
0x14003eb97  mov     [r11+8], rcx
0x14003eb9b  push    rdi
0x14003eb9c  push    r12
0x14003eb9e  push    r13
0x14003eba0  push    r14
0x14003eba2  push    r15
0x14003eba4  sub     rsp, 30h
0x14003eba8  mov     r12d, r9d
0x14003ebab  mov     r13, r8
0x14003ebae  mov     rbx, rcx
0x14003ebb1  xor     eax, eax
0x14003ebb3  mov     word ptr [rsp+58h+LockState.OldIrql], ax
0x14003ebb8  mov     [rsp+58h+LockState.Flags], al
0x14003ebbc  mov     r15, [rsp+58h+arg_28]
0x14003ebc4  mov     [r15], rax
0x14003ebc7  xor     r8d, r8d; Flags
0x14003ebca  lea     rdx, [r11-38h]; LockState
0x14003ebce  mov     rcx, [rcx+60h]; Lock
0x14003ebd2  call    cs:__imp_NdisAcquireRWLockWrite
0x14003ebd9  nop     dword ptr [rax+rax+00h]
0x14003ebde  cmp     byte ptr [rbx+88h], 0
0x14003ebe5  jz      short loc_14003EC06
0x14003ebe7  lea     rdx, [rsp+58h+LockState]; LockState
0x14003ebec  mov     rcx, [rbx+60h]; Lock
0x14003ebf0  call    cs:__imp_NdisReleaseRWLock
0x14003ebf7  nop     dword ptr [rax+rax+00h]
0x14003ebfc  mov     eax, 0C0000184h
0x14003ec01  jmp     loc_14003ED30
0x14003ec06  xor     r8d, r8d
0x14003ec09  mov     r9b, 1
0x14003ec0c  mov     r10b, r9b
0x14003ec0f  mov     esi, [rbx+7Ch]
0x14003ec12  mov     edi, esi
0x14003ec14  lea     r14, [rbx+68h]
0x14003ec18  lea     r11, [rbx+78h]
0x14003ec1c  test    edi, edi
0x14003ec1e  jz      short loc_14003EC35
0x14003ec20  mov     ecx, edi
0x14003ec22  mov     rax, [r14]
0x14003ec25  mov     r8, [rax+rcx*8]
0x14003ec29  test    r8, r8
0x14003ec2c  jz      short loc_14003EC51
0x14003ec2e  cmp     dword ptr [r8+20h], 2
0x14003ec33  jz      short loc_14003EC4C
0x14003ec35  mov     edx, [r11]
0x14003ec38  dec     edx
0x14003ec3a  mov     eax, edi
0x14003ec3c  lea     ecx, [rdi+1]
0x14003ec3f  xor     edi, edi
0x14003ec41  cmp     eax, edx
0x14003ec43  cmovnz  edi, ecx
0x14003ec46  cmp     edi, esi
0x14003ec48  jz      short loc_14003EC57
0x14003ec4a  jmp     short loc_14003EC1C
0x14003ec4c  xor     r9b, r9b
0x14003ec4f  jmp     short loc_14003EC54
0x14003ec51  xor     r10b, r10b
0x14003ec54  mov     [rbx+7Ch], edi
0x14003ec57  test    r9b, r9b
0x14003ec5a  jz      loc_14003ECEC
0x14003ec60  test    r10b, r10b
0x14003ec63  jz      short loc_14003EC9E
0x14003ec65  mov     edi, [r11]
0x14003ec68  mov     r8d, 624F4952h
0x14003ec6e  mov     rdx, r11
0x14003ec71  mov     rcx, r14
0x14003ec74  call    AfdRioGrowTable
0x14003ec79  mov     esi, eax
0x14003ec7b  test    eax, eax
0x14003ec7d  jns     short loc_14003EC9B
0x14003ec7f  lea     rdx, [rsp+58h+LockState]; LockState
0x14003ec84  mov     rcx, [rbx+60h]; Lock
0x14003ec88  call    cs:__imp_NdisReleaseRWLock
0x14003ec8f  nop     dword ptr [rax+rax+00h]
0x14003ec94  mov     eax, esi
0x14003ec96  jmp     loc_14003ED30
0x14003ec9b  mov     [rbx+7Ch], edi
0x14003ec9e  mov     edx, 30h ; '0'
0x14003eca3  lea     ecx, [rdx+31h]
0x14003eca6  mov     r8d, 624F4952h
0x14003ecac  call    cs:__imp_ExAllocatePool2
0x14003ecb3  nop     dword ptr [rax+rax+00h]
0x14003ecb8  mov     r8, rax
0x14003ecbb  mov     [rsp+58h+var_30], rax
0x14003ecc0  mov     ecx, edi
0x14003ecc2  mov     rax, [r14]
0x14003ecc5  mov     [rax+rcx*8], r8
0x14003ecc9  jmp     short loc_14003ECEC
0x14003eccb  lea     rdx, [rsp+58h+LockState]; LockState
0x14003ecd0  mov     rcx, [rsp+58h+arg_0]
0x14003ecd5  mov     rcx, [rcx+60h]; Lock
0x14003ecd9  call    cs:__imp_NdisReleaseRWLock
0x14003ece0  nop     dword ptr [rax+rax+00h]
0x14003ece5  mov     eax, 0C0000017h
0x14003ecea  jmp     short loc_14003ED30
0x14003ecec  mov     rax, [rsp+58h+arg_8]
0x14003ecf1  mov     [r8], rax
0x14003ecf4  mov     [r8+8], r13
0x14003ecf8  mov     [r8+10h], r12d
0x14003ecfc  mov     qword ptr [r8+18h], 1
0x14003ed04  mov     dword ptr [r8+20h], 0
0x14003ed0c  mov     rax, [rsp+58h+arg_20]
0x14003ed14  mov     [rax], edi
0x14003ed16  mov     [r15], r8
0x14003ed19  lea     rdx, [rsp+58h+LockState]; LockState
0x14003ed1e  mov     rcx, [rbx+60h]; Lock
0x14003ed22  call    cs:__imp_NdisReleaseRWLock
0x14003ed29  nop     dword ptr [rax+rax+00h]
0x14003ed2e  xor     eax, eax
0x14003ed30  mov     rbx, [rsp+58h+arg_10]
0x14003ed35  mov     rsi, [rsp+58h+arg_18]
0x14003ed3a  add     rsp, 30h
0x14003ed3e  pop     r15
0x14003ed40  pop     r14
0x14003ed42  pop     r13
0x14003ed44  pop     r12
0x14003ed46  pop     rdi
0x14003ed47  retn
```
