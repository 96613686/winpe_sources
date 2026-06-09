# CommonBuffer_AcquireBuffers

- ea: `0x14002bd4c`
- end: `0x14002be98`
- name: `CommonBuffer_AcquireBuffers`
- size: `332`
- prototype: `__int64 __usercall@<rax>(PVOID Context@<rcx>, __int64, int, __int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400082d0`
- `0x140012ab0`
- `0x14002bad0`
- `0x1400575cc`

## callees

- `0x140006620`
- `0x14002bd4c`
- `0x14002bea0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14002bde8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002be1c`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002bde8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002be1c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002bdb6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002be70`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002bdb6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002be70`

## pseudocode

```c
__int64 __fastcall CommonBuffer_AcquireBuffers(
        KSPIN_LOCK *Context,
        int a2,
        int a3,
        int a4,
        __int64 a5,
        int a6,
        _QWORD *a7)
{
  int v8; // eax
  unsigned int v9; // edi
  KIRQL v11; // al
  PVOID *v12; // r8
  __int64 v13; // rax
  _QWORD *v14; // rcx
  char v15; // bp
  _QWORD *v16; // rbx
  KSPIN_LOCK *v17; // r14
  KIRQL v18; // al
  _QWORD **v19; // rsi
  KIRQL v20; // dl
  _QWORD *i; // rcx
  char v22; // [rsp+60h] [rbp+8h] BYREF

  v22 = 0;
  v8 = XilCoreCommonBuffer_AcquireBuffers((int)Context + 88, a2, a3, a4, a5, a6, (__int64)&v22);
  v9 = v8;
  if ( !v22 )
    return v9;
  v16 = a7;
  if ( v8 < 0 && a7 )
  {
    v11 = KeAcquireSpinLockRaiseToDpc(Context + 6);
    v12 = (PVOID *)Context[8];
    if ( *v12 != Context + 7 )
      goto LABEL_5;
    *v16 = Context + 7;
    v16[1] = v12;
    v9 = 259;
    *v12 = v16;
    Context[8] = (KSPIN_LOCK)v16;
    KeReleaseSpinLock(Context + 6, v11);
  }
  if ( (unsigned __int8)CommonBuffer_QueueWorkItem(Context) || !v16 )
    return v9;
  v17 = Context + 6;
  v15 = 0;
  v18 = KeAcquireSpinLockRaiseToDpc(Context + 6);
  v19 = (_QWORD **)(Context + 7);
  v20 = v18;
  for ( i = *v19; ; i = (_QWORD *)*i )
  {
    if ( v19 == i )
      goto LABEL_9;
    if ( i == v16 )
      break;
  }
  v13 = *v16;
  if ( *(_QWORD **)(*v16 + 8LL) != v16 || (v14 = (_QWORD *)v16[1], (_QWORD *)*v14 != v16) )
LABEL_5:
    __fastfail(3u);
  *v14 = v13;
  v15 = 1;
  *(_QWORD *)(v13 + 8) = v14;
LABEL_9:
  KeReleaseSpinLock(v17, v20);
  if ( v15 )
    return (unsigned int)-1073741670;
  return v9;
}

```

## disassembly

```asm
0x14002bd4c  mov     r11, rsp
0x14002bd4f  mov     [r11+10h], rbx
0x14002bd53  mov     [r11+18h], rbp
0x14002bd57  push    rsi
0x14002bd58  push    rdi
0x14002bd59  push    r14
0x14002bd5b  sub     rsp, 40h
0x14002bd5f  lea     rax, [r11+8]
0x14002bd63  mov     [rsp+58h+arg_0], 0
0x14002bd68  mov     [r11-28h], rax
0x14002bd6c  mov     rsi, rcx
0x14002bd6f  mov     eax, [rsp+58h+arg_28]
0x14002bd76  add     rcx, 58h ; 'X'
0x14002bd7a  mov     [rsp+58h+var_30], eax
0x14002bd7e  mov     rax, [rsp+58h+arg_20]
0x14002bd86  mov     [r11-38h], rax
0x14002bd8a  call    XilCoreCommonBuffer_AcquireBuffers
0x14002bd8f  cmp     [rsp+58h+arg_0], 0
0x14002bd94  mov     edi, eax
0x14002bd96  jnz     loc_14002BE38
0x14002bd9c  mov     rbx, [rsp+58h+arg_8]
0x14002bda1  mov     eax, edi
0x14002bda3  mov     rbp, [rsp+58h+arg_10]
0x14002bda8  add     rsp, 40h
0x14002bdac  pop     r14
0x14002bdae  pop     rdi
0x14002bdaf  pop     rsi
0x14002bdb0  retn
0x14002bdb2  lea     rcx, [rsi+30h]; SpinLock
0x14002bdb6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002bdbd  nop     dword ptr [rax+rax+00h]
0x14002bdc2  lea     rdx, [rsi+38h]
0x14002bdc6  mov     r8, [rdx+8]
0x14002bdca  cmp     [r8], rdx
0x14002bdcd  jnz     short loc_14002BDF6
0x14002bdcf  mov     [rbx], rdx
0x14002bdd2  lea     rcx, [rsi+30h]; SpinLock
0x14002bdd6  mov     [rbx+8], r8
0x14002bdda  mov     edi, 103h
0x14002bddf  mov     [r8], rbx
0x14002bde2  mov     [rdx+8], rbx
0x14002bde6  mov     dl, al; NewIrql
0x14002bde8  call    cs:__imp_KeReleaseSpinLock
0x14002bdef  nop     dword ptr [rax+rax+00h]
0x14002bdf4  jmp     short loc_14002BE4D
0x14002bdf6  mov     ecx, 3
0x14002bdfb  int     29h; Win8: RtlFailFast(ecx)
0x14002bdfd  mov     rax, [rbx]
0x14002be00  cmp     [rax+8], rbx
0x14002be04  jnz     short loc_14002BDF6
0x14002be06  mov     rcx, [rbx+8]
0x14002be0a  cmp     [rcx], rbx
0x14002be0d  jnz     short loc_14002BDF6
0x14002be0f  mov     [rcx], rax
0x14002be12  mov     bpl, 1
0x14002be15  mov     [rax+8], rcx
0x14002be19  mov     rcx, r14; SpinLock
0x14002be1c  call    cs:__imp_KeReleaseSpinLock
0x14002be23  nop     dword ptr [rax+rax+00h]
0x14002be28  test    bpl, bpl
0x14002be2b  mov     eax, 0C000009Ah
0x14002be30  cmovnz  edi, eax
0x14002be33  jmp     loc_14002BD9C
0x14002be38  mov     rbx, [rsp+58h+arg_30]
0x14002be40  test    eax, eax
0x14002be42  jns     short loc_14002BE4D
0x14002be44  test    rbx, rbx
0x14002be47  jnz     loc_14002BDB2
0x14002be4d  mov     rcx, rsi; Context
0x14002be50  call    CommonBuffer_QueueWorkItem
0x14002be55  test    al, al
0x14002be57  jnz     loc_14002BD9C
0x14002be5d  test    rbx, rbx
0x14002be60  jz      loc_14002BD9C
0x14002be66  lea     r14, [rsi+30h]
0x14002be6a  xor     bpl, bpl
0x14002be6d  mov     rcx, r14; SpinLock
0x14002be70  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002be77  nop     dword ptr [rax+rax+00h]
0x14002be7c  add     rsi, 38h ; '8'
0x14002be80  mov     dl, al; NewIrql
0x14002be82  mov     rcx, [rsi]
0x14002be85  cmp     rsi, rcx
0x14002be88  jz      short loc_14002BE19
0x14002be8a  cmp     rcx, rbx
0x14002be8d  jz      loc_14002BDFD
0x14002be93  mov     rcx, [rcx]
0x14002be96  jmp     short loc_14002BE85
```
