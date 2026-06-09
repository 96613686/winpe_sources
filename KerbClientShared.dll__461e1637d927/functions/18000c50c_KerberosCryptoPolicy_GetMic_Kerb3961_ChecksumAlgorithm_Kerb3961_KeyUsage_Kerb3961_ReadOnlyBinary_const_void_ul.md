# KerberosCryptoPolicy::GetMic(Kerb3961::ChecksumAlgorithm *,Kerb3961::KeyUsage,Kerb3961::ReadOnlyBinary const &,void *,ulong *)

- ea: `0x18000c50c`
- end: `0x18000c666`
- name: `?GetMic@KerberosCryptoPolicy@@QEAA_NPEAUChecksumAlgorithm@Kerb3961@@W4KeyUsage@3@AEBUReadOnlyBinary@3@PEAXPEAK@Z`
- size: `346`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018280`

## callees

- `0x18000c50c`
- `0x18000c66c`
- `0x18000c68c`
- `0x180017128`
- `0x180018204`
- `0x1800283fc`
- `0x180029010`

## pseudocode

```c
char __fastcall KerberosCryptoPolicy::GetMic(
        KerberosCryptoPolicy *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        void *a5,
        _DWORD *a6)
{
  unsigned int v9; // eax
  __int64 v10; // rax
  __int64 *v11; // r14
  unsigned int v12; // ebx
  unsigned int v13; // eax
  __int64 Key; // rax
  __int64 v15; // rcx
  __int64 v16; // rax
  int v18; // ebx
  int v19; // [rsp+30h] [rbp-50h] BYREF
  _QWORD v20[2]; // [rsp+38h] [rbp-48h] BYREF
  size_t Size[2]; // [rsp+48h] [rbp-38h] BYREF
  int v22; // [rsp+58h] [rbp-28h]
  _BYTE v23[16]; // [rsp+60h] [rbp-20h] BYREF
  int v24; // [rsp+70h] [rbp-10h]

  if ( !a5 )
    return 0;
  if ( !a6 )
    return 0;
  v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 120LL))(a2);
  v10 = KerberosCryptoPolicy::OpenEncryptionAlgorithm(a1, v9, a3);
  v11 = (__int64 *)v10;
  if ( !v10 )
    return 0;
  v12 = *((_DWORD *)a1 + 14);
  v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 216LL))(v10);
  v19 = 0;
  Key = KerberosCryptoPolicy::GetKey(a1, v13, a3, v12);
  if ( !Key )
    return 0;
  v15 = *(unsigned int *)(Key + 16);
  v20[1] = *(_QWORD *)(Key + 24);
  v16 = *v11;
  v20[0] = v15;
  (*(void (__fastcall **)(__int64 *, _BYTE *, _QWORD *, __int64, int, int *))(v16 + 168))(v11, v23, v20, a3, 2, &v19);
  if ( v24 < 0 )
  {
LABEL_6:
    Kerb3961::SpecificKeyReturn::~SpecificKeyReturn((Kerb3961::SpecificKeyReturn *)v23);
    return 0;
  }
  (*(void (__fastcall **)(__int64, size_t *, _BYTE *, __int64))(*(_QWORD *)a2 + 88LL))(a2, Size, v23, a4);
  if ( v22 < 0 )
  {
    Kerb3961::OwnedBinary::~OwnedBinary((Kerb3961::OwnedBinary *)Size);
    goto LABEL_6;
  }
  v18 = Size[0];
  memcpy_0(a5, (const void *)Size[1], Size[0]);
  *a6 = v18;
  Kerb3961::OwnedBinary::~OwnedBinary((Kerb3961::OwnedBinary *)Size);
  Kerb3961::SpecificKeyReturn::~SpecificKeyReturn((Kerb3961::SpecificKeyReturn *)v23);
  return 1;
}

```

## disassembly

```asm
0x18000c50c  mov     [rsp-28h+arg_0], rbx
0x18000c511  mov     [rsp-28h+arg_8], rsi
0x18000c516  mov     [rsp-28h+arg_18], r9
0x18000c51b  push    rbp
0x18000c51c  push    rdi
0x18000c51d  push    r12
0x18000c51f  push    r13
0x18000c521  push    r14
0x18000c523  mov     rbp, rsp
0x18000c526  sub     rsp, 80h
0x18000c52d  cmp     [rbp+arg_20], 0
0x18000c532  mov     r12, r8
0x18000c535  mov     rdi, rdx
0x18000c538  mov     r13, rcx
0x18000c53b  jz      loc_18000C5F0
0x18000c541  mov     rsi, [rbp+arg_28]
0x18000c545  test    rsi, rsi
0x18000c548  jz      loc_18000C5F0
0x18000c54e  mov     rax, [rdx]
0x18000c551  mov     rcx, rdx
0x18000c554  mov     rax, [rax+78h]
0x18000c558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c55d  mov     edx, eax
0x18000c55f  mov     r8, r12
0x18000c562  mov     rcx, r13
0x18000c565  call    ?OpenEncryptionAlgorithm@KerberosCryptoPolicy@@QEBAPEAUEncryptionAlgorithm@Kerb3961@@KW4KeyUsage@3@@Z; KerberosCryptoPolicy::OpenEncryptionAlgorithm(ulong,Kerb3961::KeyUsage)
0x18000c56a  mov     r14, rax
0x18000c56d  test    rax, rax
0x18000c570  jz      short loc_18000C5F0
0x18000c572  mov     rcx, [rax]
0x18000c575  mov     ebx, [r13+38h]
0x18000c579  mov     rax, [rcx+0D8h]
0x18000c580  mov     rcx, r14
0x18000c583  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c588  lea     rcx, [rbp+var_50]
0x18000c58c  mov     [rbp+var_50], 0
0x18000c593  mov     [rsp+80h+var_58], rcx
0x18000c598  mov     r9d, ebx
0x18000c59b  mov     rcx, r13
0x18000c59e  mov     r8, r12
0x18000c5a1  mov     edx, eax
0x18000c5a3  call    ?GetKey@KerberosCryptoPolicy@@QEAAPEAU_KERB_ENCRYPTION_KEY@@JW4KeyUsage@Kerb3961@@W4KdcKeyType@@W4KdcPrincipalKeyState@@PEAK@Z; KerberosCryptoPolicy::GetKey(long,Kerb3961::KeyUsage,KdcKeyType,KdcPrincipalKeyState,ulong *)
0x18000c5a8  test    rax, rax
0x18000c5ab  jz      short loc_18000C5F0
0x18000c5ad  mov     ecx, [rax+10h]
0x18000c5b0  lea     r8, [rbp+var_48]
0x18000c5b4  mov     rax, [rax+18h]
0x18000c5b8  lea     rdx, [rbp+var_20]
0x18000c5bc  mov     [rbp+var_40], rax
0x18000c5c0  mov     r9, r12
0x18000c5c3  mov     rax, [r14]
0x18000c5c6  mov     [rbp+var_48], rcx
0x18000c5ca  mov     rcx, r14
0x18000c5cd  mov     [rsp+80h+var_60], 2
0x18000c5d5  mov     rax, [rax+0A8h]
0x18000c5dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5e1  cmp     [rbp+var_10], 0
0x18000c5e5  jge     short loc_18000C60E
0x18000c5e7  lea     rcx, [rbp+var_20]; this
0x18000c5eb  call    ??1SpecificKeyReturn@Kerb3961@@QEAA@XZ; Kerb3961::SpecificKeyReturn::~SpecificKeyReturn(void)
0x18000c5f0  xor     al, al
0x18000c5f2  lea     r11, [rsp+80h+var_s0]
0x18000c5fa  mov     rbx, [r11+30h]
0x18000c5fe  mov     rsi, [r11+38h]
0x18000c602  mov     rsp, r11
0x18000c605  pop     r14
0x18000c607  pop     r13
0x18000c609  pop     r12
0x18000c60b  pop     rdi
0x18000c60c  pop     rbp
0x18000c60d  retn
0x18000c60e  mov     rax, [rdi]
0x18000c611  lea     r8, [rbp+var_20]
0x18000c615  mov     r9, [rbp+arg_18]
0x18000c619  lea     rdx, [rbp+Size]
0x18000c61d  mov     rcx, rdi
0x18000c620  mov     rax, [rax+58h]
0x18000c624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c629  cmp     [rbp+var_28], 0
0x18000c62d  jge     short loc_18000C63A
0x18000c62f  lea     rcx, [rbp+Size]; this
0x18000c633  call    ??1OwnedBinary@Kerb3961@@QEAA@XZ; Kerb3961::OwnedBinary::~OwnedBinary(void)
0x18000c638  jmp     short loc_18000C5E7
0x18000c63a  mov     rbx, [rbp+Size]
0x18000c63e  mov     rdx, [rbp+Src]; Src
0x18000c642  mov     r8, rbx; Size
0x18000c645  mov     rcx, [rbp+arg_20]; void *
0x18000c649  call    memcpy_0
0x18000c64e  lea     rcx, [rbp+Size]; this
0x18000c652  mov     [rsi], ebx
0x18000c654  call    ??1OwnedBinary@Kerb3961@@QEAA@XZ; Kerb3961::OwnedBinary::~OwnedBinary(void)
0x18000c659  lea     rcx, [rbp+var_20]; this
0x18000c65d  call    ??1SpecificKeyReturn@Kerb3961@@QEAA@XZ; Kerb3961::SpecificKeyReturn::~SpecificKeyReturn(void)
0x18000c662  mov     al, 1
0x18000c664  jmp     short loc_18000C5F2
```
