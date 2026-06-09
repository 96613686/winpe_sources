# KerberosCryptoPolicy::GetMic(Kerb3961::ChecksumAlgorithm *,Kerb3961::KeyUsage,Kerb3961::ReadOnlyBinary const &,KERB_CHECKSUM *)

- ea: `0x14001e3c8`
- end: `0x14001e461`
- name: `?GetMic@KerberosCryptoPolicy@@QEAA_NPEAUChecksumAlgorithm@Kerb3961@@W4KeyUsage@3@AEBUReadOnlyBinary@3@PEAUKERB_CHECKSUM@@@Z`
- size: `153`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001ac5c`
- `0x14001b094`

## callees

- `0x1400066f0`
- `0x14001e3c8`
- `0x14001e468`
- `0x14003a010`

## pseudocode

```c
char __fastcall KerberosCryptoPolicy::GetMic(KerberosCryptoPolicy *a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5)
{
  size_t v9; // rax
  void *v10; // rax

  if ( !a5 )
    return 0;
  if ( !*(_QWORD *)(a5 + 16) )
  {
    v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 128LL))(a2);
    v10 = MIDL_user_allocate(v9);
    *(_QWORD *)(a5 + 16) = v10;
    if ( !v10 )
      return 0;
  }
  *(_DWORD *)a5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 104LL))(a2);
  return KerberosCryptoPolicy::GetMic(a1, a2, a3, a4, *(void **)(a5 + 16), (_DWORD *)(a5 + 8));
}

```

## disassembly

```asm
0x14001e3c8  push    rbx
0x14001e3ca  push    rbp
0x14001e3cb  push    rsi
0x14001e3cc  push    rdi
0x14001e3cd  push    r12
0x14001e3cf  push    r14
0x14001e3d1  push    r15
0x14001e3d3  sub     rsp, 30h
0x14001e3d7  mov     rbx, [rsp+68h+arg_20]
0x14001e3df  mov     r14, r9
0x14001e3e2  mov     r15, r8
0x14001e3e5  mov     rsi, rdx
0x14001e3e8  mov     r12, rcx
0x14001e3eb  test    rbx, rbx
0x14001e3ee  jz      short loc_14001E450
0x14001e3f0  lea     rbp, [rbx+8]
0x14001e3f4  cmp     qword ptr [rbp+8], 0
0x14001e3f9  jnz     short loc_14001E41E
0x14001e3fb  mov     rax, [rdx]
0x14001e3fe  mov     rcx, rdx
0x14001e401  mov     rax, [rax+80h]
0x14001e408  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e40d  mov     rcx, rax; size
0x14001e410  call    MIDL_user_allocate
0x14001e415  mov     [rbx+10h], rax
0x14001e419  test    rax, rax
0x14001e41c  jz      short loc_14001E450
0x14001e41e  mov     rax, [rsi]
0x14001e421  mov     rcx, rsi
0x14001e424  mov     rax, [rax+68h]
0x14001e428  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e42d  mov     [rbx], eax
0x14001e42f  mov     r9, r14
0x14001e432  mov     rax, [rbx+10h]
0x14001e436  mov     r8, r15
0x14001e439  mov     [rsp+68h+var_40], rbp
0x14001e43e  mov     rdx, rsi
0x14001e441  mov     rcx, r12
0x14001e444  mov     [rsp+68h+var_48], rax
0x14001e449  call    ?GetMic@KerberosCryptoPolicy@@QEAA_NPEAUChecksumAlgorithm@Kerb3961@@W4KeyUsage@3@AEBUReadOnlyBinary@3@PEAXPEAK@Z; KerberosCryptoPolicy::GetMic(Kerb3961::ChecksumAlgorithm *,Kerb3961::KeyUsage,Kerb3961::ReadOnlyBinary const &,void *,ulong *)
0x14001e44e  jmp     short loc_14001E452
0x14001e450  xor     al, al
0x14001e452  add     rsp, 30h
0x14001e456  pop     r15
0x14001e458  pop     r14
0x14001e45a  pop     r12
0x14001e45c  pop     rdi
0x14001e45d  pop     rsi
0x14001e45e  pop     rbp
0x14001e45f  pop     rbx
0x14001e460  retn
```
