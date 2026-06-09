# CsCloseConsole

- ea: `0x14001eb64`
- end: `0x14001ed2f`
- name: `CsCloseConsole`
- size: `459`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14001b5ec`
- `0x14001b86c`
- `0x14001b8ac`

## callees

- `0x14001eb64`
- `0x14001f40c`

## import_xrefs

- `ntdll!RtlReleaseSRWLockExclusive` at `0x14001eb90`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x14001eb90`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14001eb82`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x14001eb82`
- `ntdll!RtlFreeHeap` at `0x14001ec15`
- `ntdll!RtlFreeHeap` at `0x14001ec66`
- `ntdll!RtlFreeHeap` at `0x14001ec9f`
- `ntdll!RtlFreeHeap` at `0x14001ecee`
- `ntdll!RtlFreeHeap` at `0x14001ed19`
- `ntdll!RtlFreeHeap` at `0x14001ec15`
- `ntdll!RtlFreeHeap` at `0x14001ec66`
- `ntdll!RtlFreeHeap` at `0x14001ec9f`
- `ntdll!RtlFreeHeap` at `0x14001ecee`
- `ntdll!RtlFreeHeap` at `0x14001ed19`
- `ntdll!TpWaitForIoCompletion` at `0x14001ebe1`
- `ntdll!TpWaitForIoCompletion` at `0x14001ebe1`
- `ntdll!TpReleaseIoCompletion` at `0x14001ebeb`
- `ntdll!TpReleaseIoCompletion` at `0x14001ebeb`
- `ntdll!NtDeviceIoControlFile` at `0x14001ebd5`
- `ntdll!NtDeviceIoControlFile` at `0x14001ebd5`
- `ntdll!NtClose` at `0x14001ebf4`
- `ntdll!NtClose` at `0x14001ec4e`
- `ntdll!NtClose` at `0x14001ed01`
- `ntdll!NtClose` at `0x14001ebf4`
- `ntdll!NtClose` at `0x14001ec4e`
- `ntdll!NtClose` at `0x14001ed01`

## pseudocode

```c
BOOLEAN __fastcall CsCloseConsole(char *P)
{
  void *v2; // r8
  _QWORD **v3; // rsi
  _QWORD *v4; // rbx
  _QWORD *v5; // rax
  void *v6; // rcx
  _QWORD **v7; // rbx
  _QWORD *v8; // r8
  _QWORD *v9; // rax
  _QWORD *i; // rbx
  _QWORD **v11; // rbx
  _QWORD *v12; // r8
  _QWORD *v13; // rax
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+50h] [rbp-18h] BYREF

  IoStatusBlock = 0;
  RtlAcquireSRWLockExclusive(P + 48);
  P[56] = 1;
  RtlReleaseSRWLockExclusive(P + 48);
  NtDeviceIoControlFile(*(HANDLE *)P, 0, 0, 0, &IoStatusBlock, 0x50001Bu, 0, 0, 0, 0);
  TpWaitForIoCompletion(*((_QWORD *)P + 3), 0);
  TpReleaseIoCompletion(*((_QWORD *)P + 3));
  NtClose(*(HANDLE *)P);
  v2 = (void *)*((_QWORD *)P + 19);
  if ( v2 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v2);
  v3 = (_QWORD **)(P + 64);
  while ( 1 )
  {
    v4 = *v3;
    if ( *v3 == v3 )
      break;
    if ( (_QWORD **)v4[1] != v3 || (v5 = (_QWORD *)*v4, *(_QWORD **)(*v4 + 8LL) != v4) )
LABEL_23:
      __fastfail(3u);
    *v3 = v5;
    v5[1] = v3;
    v6 = (void *)v4[3];
    if ( v6 )
      NtClose(v6);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
  }
  v7 = (_QWORD **)(P + 112);
  while ( 1 )
  {
    v8 = *v7;
    if ( *v7 == v7 )
      break;
    if ( (_QWORD **)v8[1] != v7 )
      goto LABEL_23;
    v9 = (_QWORD *)*v8;
    if ( *(_QWORD **)(*v8 + 8LL) != v8 )
      goto LABEL_23;
    *v7 = v9;
    v9[1] = v7;
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
  }
  for ( i = P + 80; (_QWORD *)*i != i; CspFreeServerScreen(*i) )
    ;
  v11 = (_QWORD **)(P + 184);
  while ( 1 )
  {
    v12 = *v11;
    if ( *v11 == v11 )
      break;
    if ( (_QWORD **)v12[1] != v11 )
      goto LABEL_23;
    v13 = (_QWORD *)*v12;
    if ( *(_QWORD **)(*v12 + 8LL) != v12 )
      goto LABEL_23;
    *v11 = v13;
    v13[1] = v11;
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v12);
  }
  NtClose(*((HANDLE *)P + 1));
  return RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
}

```

## disassembly

```asm
0x14001eb64  mov     [rsp+arg_0], rbx
0x14001eb69  mov     [rsp+arg_8], rsi
0x14001eb6e  push    rdi
0x14001eb6f  sub     rsp, 60h
0x14001eb73  mov     rdi, rcx
0x14001eb76  xorps   xmm0, xmm0
0x14001eb79  add     rcx, 30h ; '0'
0x14001eb7d  movups  xmmword ptr [rsp+68h+var_18], xmm0
0x14001eb82  call    cs:__imp_RtlAcquireSRWLockExclusive
0x14001eb88  lea     rcx, [rdi+30h]
0x14001eb8c  mov     byte ptr [rdi+38h], 1
0x14001eb90  call    cs:__imp_RtlReleaseSRWLockExclusive
0x14001eb96  mov     rcx, [rdi]; FileHandle
0x14001eb99  lea     rax, [rsp+68h+var_18]
0x14001eb9e  mov     [rsp+68h+OutputBufferLength], 0; OutputBufferLength
0x14001eba6  xor     r9d, r9d; ApcContext
0x14001eba9  mov     [rsp+68h+OutputBuffer], 0; OutputBuffer
0x14001ebb2  xor     r8d, r8d; ApcRoutine
0x14001ebb5  mov     [rsp+68h+InputBufferLength], 0; InputBufferLength
0x14001ebbd  xor     edx, edx; Event
0x14001ebbf  mov     [rsp+68h+InputBuffer], 0; InputBuffer
0x14001ebc8  mov     [rsp+68h+IoControlCode], 50001Bh; IoControlCode
0x14001ebd0  mov     [rsp+68h+IoStatusBlock], rax; IoStatusBlock
0x14001ebd5  call    cs:__imp_NtDeviceIoControlFile
0x14001ebdb  mov     rcx, [rdi+18h]
0x14001ebdf  xor     edx, edx
0x14001ebe1  call    cs:__imp_TpWaitForIoCompletion
0x14001ebe7  mov     rcx, [rdi+18h]
0x14001ebeb  call    cs:__imp_TpReleaseIoCompletion
0x14001ebf1  mov     rcx, [rdi]; Handle
0x14001ebf4  call    cs:__imp_NtClose
0x14001ebfa  mov     r8, [rdi+98h]; P
0x14001ec01  test    r8, r8
0x14001ec04  jz      short loc_14001EC1B
0x14001ec06  mov     rcx, gs:60h
0x14001ec0f  xor     edx, edx; Flags
0x14001ec11  mov     rcx, [rcx+30h]; HeapHandle
0x14001ec15  call    cs:__imp_RtlFreeHeap
0x14001ec1b  lea     rsi, [rdi+40h]
0x14001ec1f  mov     rbx, [rsi]
0x14001ec22  cmp     rbx, rsi
0x14001ec25  jz      short loc_14001EC6E
0x14001ec27  cmp     [rbx+8], rsi
0x14001ec2b  jnz     loc_14001ECF6
0x14001ec31  mov     rax, [rbx]
0x14001ec34  cmp     [rax+8], rbx
0x14001ec38  jnz     loc_14001ECF6
0x14001ec3e  mov     [rsi], rax
0x14001ec41  mov     [rax+8], rsi
0x14001ec45  mov     rcx, [rbx+18h]; Handle
0x14001ec49  test    rcx, rcx
0x14001ec4c  jz      short loc_14001EC54
0x14001ec4e  call    cs:__imp_NtClose
0x14001ec54  mov     rcx, gs:60h
0x14001ec5d  mov     r8, rbx; P
0x14001ec60  xor     edx, edx; Flags
0x14001ec62  mov     rcx, [rcx+30h]; HeapHandle
0x14001ec66  call    cs:__imp_RtlFreeHeap
0x14001ec6c  jmp     short loc_14001EC1F
0x14001ec6e  lea     rbx, [rdi+70h]
0x14001ec72  mov     r8, [rbx]; P
0x14001ec75  cmp     r8, rbx
0x14001ec78  jz      short loc_14001ECA7
0x14001ec7a  cmp     [r8+8], rbx
0x14001ec7e  jnz     short loc_14001ECF6
0x14001ec80  mov     rax, [r8]
0x14001ec83  cmp     [rax+8], r8
0x14001ec87  jnz     short loc_14001ECF6
0x14001ec89  mov     [rbx], rax
0x14001ec8c  xor     edx, edx; Flags
0x14001ec8e  mov     [rax+8], rbx
0x14001ec92  mov     rcx, gs:60h
0x14001ec9b  mov     rcx, [rcx+30h]; HeapHandle
0x14001ec9f  call    cs:__imp_RtlFreeHeap
0x14001eca5  jmp     short loc_14001EC72
0x14001eca7  lea     rbx, [rdi+50h]
0x14001ecab  cmp     [rbx], rbx
0x14001ecae  jz      short loc_14001ECBA
0x14001ecb0  mov     rcx, [rbx]
0x14001ecb3  call    CspFreeServerScreen
0x14001ecb8  jmp     short loc_14001ECAB
0x14001ecba  lea     rbx, [rdi+0B8h]
0x14001ecc1  mov     r8, [rbx]; P
0x14001ecc4  cmp     r8, rbx
0x14001ecc7  jz      short loc_14001ECFD
0x14001ecc9  cmp     [r8+8], rbx
0x14001eccd  jnz     short loc_14001ECF6
0x14001eccf  mov     rax, [r8]
0x14001ecd2  cmp     [rax+8], r8
0x14001ecd6  jnz     short loc_14001ECF6
0x14001ecd8  mov     [rbx], rax
0x14001ecdb  xor     edx, edx; Flags
0x14001ecdd  mov     [rax+8], rbx
0x14001ece1  mov     rcx, gs:60h
0x14001ecea  mov     rcx, [rcx+30h]; HeapHandle
0x14001ecee  call    cs:__imp_RtlFreeHeap
0x14001ecf4  jmp     short loc_14001ECC1
0x14001ecf6  mov     ecx, 3
0x14001ecfb  int     29h; Win8: RtlFailFast(ecx)
0x14001ecfd  mov     rcx, [rdi+8]; Handle
0x14001ed01  call    cs:__imp_NtClose
0x14001ed07  mov     rcx, gs:60h
0x14001ed10  mov     r8, rdi; P
0x14001ed13  xor     edx, edx; Flags
0x14001ed15  mov     rcx, [rcx+30h]; HeapHandle
0x14001ed19  call    cs:__imp_RtlFreeHeap
0x14001ed1f  mov     rbx, [rsp+68h+arg_0]
0x14001ed24  mov     rsi, [rsp+68h+arg_8]
0x14001ed29  add     rsp, 60h
0x14001ed2d  pop     rdi
0x14001ed2e  retn
```
