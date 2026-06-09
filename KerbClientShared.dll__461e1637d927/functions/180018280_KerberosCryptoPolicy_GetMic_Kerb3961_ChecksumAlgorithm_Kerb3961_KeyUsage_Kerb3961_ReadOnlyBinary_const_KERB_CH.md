# KerberosCryptoPolicy::GetMic(Kerb3961::ChecksumAlgorithm *,Kerb3961::KeyUsage,Kerb3961::ReadOnlyBinary const &,KERB_CHECKSUM *)

- ea: `0x180018280`
- end: `0x180018319`
- name: `?GetMic@KerberosCryptoPolicy@@QEAA_NPEAUChecksumAlgorithm@Kerb3961@@W4KeyUsage@3@AEBUReadOnlyBinary@3@PEAUKERB_CHECKSUM@@@Z`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009bd8`

## callees

- `0x180008990`
- `0x18000c50c`
- `0x180018280`
- `0x180029010`

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
0x180018280  push    rbx
0x180018282  push    rbp
0x180018283  push    rsi
0x180018284  push    rdi
0x180018285  push    r12
0x180018287  push    r14
0x180018289  push    r15
0x18001828b  sub     rsp, 30h
0x18001828f  mov     rbx, [rsp+68h+arg_20]
0x180018297  mov     r14, r9
0x18001829a  mov     r15, r8
0x18001829d  mov     rsi, rdx
0x1800182a0  mov     r12, rcx
0x1800182a3  test    rbx, rbx
0x1800182a6  jz      short loc_180018308
0x1800182a8  lea     rbp, [rbx+8]
0x1800182ac  cmp     qword ptr [rbp+8], 0
0x1800182b1  jnz     short loc_1800182D6
0x1800182b3  mov     rax, [rdx]
0x1800182b6  mov     rcx, rdx
0x1800182b9  mov     rax, [rax+80h]
0x1800182c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182c5  mov     rcx, rax; size
0x1800182c8  call    MIDL_user_allocate
0x1800182cd  mov     [rbx+10h], rax
0x1800182d1  test    rax, rax
0x1800182d4  jz      short loc_180018308
0x1800182d6  mov     rax, [rsi]
0x1800182d9  mov     rcx, rsi
0x1800182dc  mov     rax, [rax+68h]
0x1800182e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182e5  mov     [rbx], eax
0x1800182e7  mov     r9, r14
0x1800182ea  mov     rax, [rbx+10h]
0x1800182ee  mov     r8, r15
0x1800182f1  mov     [rsp+68h+var_40], rbp
0x1800182f6  mov     rdx, rsi
0x1800182f9  mov     rcx, r12
0x1800182fc  mov     [rsp+68h+var_48], rax
0x180018301  call    ?GetMic@KerberosCryptoPolicy@@QEAA_NPEAUChecksumAlgorithm@Kerb3961@@W4KeyUsage@3@AEBUReadOnlyBinary@3@PEAXPEAK@Z; KerberosCryptoPolicy::GetMic(Kerb3961::ChecksumAlgorithm *,Kerb3961::KeyUsage,Kerb3961::ReadOnlyBinary const &,void *,ulong *)
0x180018306  jmp     short loc_18001830A
0x180018308  xor     al, al
0x18001830a  add     rsp, 30h
0x18001830e  pop     r15
0x180018310  pop     r14
0x180018312  pop     r12
0x180018314  pop     rdi
0x180018315  pop     rsi
0x180018316  pop     rbp
0x180018317  pop     rbx
0x180018318  retn
```
