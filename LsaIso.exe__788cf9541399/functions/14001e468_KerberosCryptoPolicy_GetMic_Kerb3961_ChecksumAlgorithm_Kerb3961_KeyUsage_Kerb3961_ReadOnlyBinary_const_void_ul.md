# KerberosCryptoPolicy::GetMic(Kerb3961::ChecksumAlgorithm *,Kerb3961::KeyUsage,Kerb3961::ReadOnlyBinary const &,void *,ulong *)

- ea: `0x14001e468`
- end: `0x14001e5c2`
- name: `?GetMic@KerberosCryptoPolicy@@QEAA_NPEAUChecksumAlgorithm@Kerb3961@@W4KeyUsage@3@AEBUReadOnlyBinary@3@PEAXPEAK@Z`
- size: `346`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14001e3c8`

## callees

- `0x140003ad6`
- `0x14001bf88`
- `0x14001e3a8`
- `0x14001e468`
- `0x14001eaf4`
- `0x14001f460`
- `0x14003a010`

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
0x14001e468  mov     [rsp-28h+arg_0], rbx
0x14001e46d  mov     [rsp-28h+arg_8], rsi
0x14001e472  mov     [rsp-28h+arg_18], r9
0x14001e477  push    rbp
0x14001e478  push    rdi
0x14001e479  push    r12
0x14001e47b  push    r13
0x14001e47d  push    r14
0x14001e47f  mov     rbp, rsp
0x14001e482  sub     rsp, 80h
0x14001e489  cmp     [rbp+arg_20], 0
0x14001e48e  mov     r12, r8
0x14001e491  mov     rdi, rdx
0x14001e494  mov     r13, rcx
0x14001e497  jz      loc_14001E54C
0x14001e49d  mov     rsi, [rbp+arg_28]
0x14001e4a1  test    rsi, rsi
0x14001e4a4  jz      loc_14001E54C
0x14001e4aa  mov     rax, [rdx]
0x14001e4ad  mov     rcx, rdx
0x14001e4b0  mov     rax, [rax+78h]
0x14001e4b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e4b9  mov     edx, eax
0x14001e4bb  mov     r8, r12
0x14001e4be  mov     rcx, r13
0x14001e4c1  call    ?OpenEncryptionAlgorithm@KerberosCryptoPolicy@@QEBAPEAUEncryptionAlgorithm@Kerb3961@@KW4KeyUsage@3@@Z; KerberosCryptoPolicy::OpenEncryptionAlgorithm(ulong,Kerb3961::KeyUsage)
0x14001e4c6  mov     r14, rax
0x14001e4c9  test    rax, rax
0x14001e4cc  jz      short loc_14001E54C
0x14001e4ce  mov     rcx, [rax]
0x14001e4d1  mov     ebx, [r13+38h]
0x14001e4d5  mov     rax, [rcx+0D8h]
0x14001e4dc  mov     rcx, r14
0x14001e4df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e4e4  lea     rcx, [rbp+var_50]
0x14001e4e8  mov     [rbp+var_50], 0
0x14001e4ef  mov     [rsp+80h+var_58], rcx
0x14001e4f4  mov     r9d, ebx
0x14001e4f7  mov     rcx, r13
0x14001e4fa  mov     r8, r12
0x14001e4fd  mov     edx, eax
0x14001e4ff  call    ?GetKey@KerberosCryptoPolicy@@QEAAPEAU_KERB_ENCRYPTION_KEY@@JW4KeyUsage@Kerb3961@@W4KdcKeyType@@W4KdcPrincipalKeyState@@PEAK@Z; KerberosCryptoPolicy::GetKey(long,Kerb3961::KeyUsage,KdcKeyType,KdcPrincipalKeyState,ulong *)
0x14001e504  test    rax, rax
0x14001e507  jz      short loc_14001E54C
0x14001e509  mov     ecx, [rax+10h]
0x14001e50c  lea     r8, [rbp+var_48]
0x14001e510  mov     rax, [rax+18h]
0x14001e514  lea     rdx, [rbp+var_20]
0x14001e518  mov     [rbp+var_40], rax
0x14001e51c  mov     r9, r12
0x14001e51f  mov     rax, [r14]
0x14001e522  mov     [rbp+var_48], rcx
0x14001e526  mov     rcx, r14
0x14001e529  mov     [rsp+80h+var_60], 2
0x14001e531  mov     rax, [rax+0A8h]
0x14001e538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e53d  cmp     [rbp+var_10], 0
0x14001e541  jge     short loc_14001E56A
0x14001e543  lea     rcx, [rbp+var_20]; this
0x14001e547  call    ??1SpecificKeyReturn@Kerb3961@@QEAA@XZ; Kerb3961::SpecificKeyReturn::~SpecificKeyReturn(void)
0x14001e54c  xor     al, al
0x14001e54e  lea     r11, [rsp+80h+var_s0]
0x14001e556  mov     rbx, [r11+30h]
0x14001e55a  mov     rsi, [r11+38h]
0x14001e55e  mov     rsp, r11
0x14001e561  pop     r14
0x14001e563  pop     r13
0x14001e565  pop     r12
0x14001e567  pop     rdi
0x14001e568  pop     rbp
0x14001e569  retn
0x14001e56a  mov     rax, [rdi]
0x14001e56d  lea     r8, [rbp+var_20]
0x14001e571  mov     r9, [rbp+arg_18]
0x14001e575  lea     rdx, [rbp+Size]
0x14001e579  mov     rcx, rdi
0x14001e57c  mov     rax, [rax+58h]
0x14001e580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e585  cmp     [rbp+var_28], 0
0x14001e589  jge     short loc_14001E596
0x14001e58b  lea     rcx, [rbp+Size]; this
0x14001e58f  call    ??1OwnedBinary@Kerb3961@@QEAA@XZ; Kerb3961::OwnedBinary::~OwnedBinary(void)
0x14001e594  jmp     short loc_14001E543
0x14001e596  mov     rbx, [rbp+Size]
0x14001e59a  mov     rdx, [rbp+Src]; Src
0x14001e59e  mov     r8, rbx; Size
0x14001e5a1  mov     rcx, [rbp+arg_20]; void *
0x14001e5a5  call    memcpy_0
0x14001e5aa  lea     rcx, [rbp+Size]; this
0x14001e5ae  mov     [rsi], ebx
0x14001e5b0  call    ??1OwnedBinary@Kerb3961@@QEAA@XZ; Kerb3961::OwnedBinary::~OwnedBinary(void)
0x14001e5b5  lea     rcx, [rbp+var_20]; this
0x14001e5b9  call    ??1SpecificKeyReturn@Kerb3961@@QEAA@XZ; Kerb3961::SpecificKeyReturn::~SpecificKeyReturn(void)
0x14001e5be  mov     al, 1
0x14001e5c0  jmp     short loc_14001E54E
```
