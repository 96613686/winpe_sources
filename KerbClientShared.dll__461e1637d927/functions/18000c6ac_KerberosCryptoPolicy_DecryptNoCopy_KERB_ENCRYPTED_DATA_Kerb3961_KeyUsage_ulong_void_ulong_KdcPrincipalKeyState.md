# KerberosCryptoPolicy::DecryptNoCopy(KERB_ENCRYPTED_DATA *,Kerb3961::KeyUsage,ulong *,void * *,ulong *,KdcPrincipalKeyState)

- ea: `0x18000c6ac`
- end: `0x18000c894`
- name: `?DecryptNoCopy@KerberosCryptoPolicy@@AEAAJPEAUKERB_ENCRYPTED_DATA@@W4KeyUsage@Kerb3961@@PEAKPEAPEAX2W4KdcPrincipalKeyState@@@Z`
- size: `488`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _DWORD *, void **)`
- caller_count: `7`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180009d60`
- `0x18000a1b0`
- `0x18000aed0`
- `0x18000b790`
- `0x18000c8c0`
- `0x18000cf30`
- `0x180016190`

## callees

- `0x180007e10`
- `0x18000c66c`
- `0x18000c68c`
- `0x18000c6ac`
- `0x18000c89c`
- `0x180017128`
- `0x180018204`
- `0x180029010`

## pseudocode

```c
__int64 __fastcall KerberosCryptoPolicy::DecryptNoCopy(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4, void **a5)
{
  __int64 v9; // rax
  __int64 v10; // rdi
  unsigned int v12; // ebx
  unsigned int v13; // eax
  __int64 Key; // rax
  unsigned int v15; // ebx
  __int64 v16; // rax
  __int64 v17; // [rsp+40h] [rbp-71h] BYREF
  __int64 v18; // [rsp+48h] [rbp-69h]
  _QWORD v19[2]; // [rsp+50h] [rbp-61h] BYREF
  __int64 v20; // [rsp+60h] [rbp-51h] BYREF
  void *v21; // [rsp+68h] [rbp-49h]
  int v22; // [rsp+70h] [rbp-41h]
  _BYTE v23[16]; // [rsp+78h] [rbp-39h] BYREF
  int v24; // [rsp+88h] [rbp-29h]
  _BYTE v25[16]; // [rsp+90h] [rbp-21h] BYREF
  int v26; // [rsp+A0h] [rbp-11h]

  if ( !a2 || !*(_QWORD *)(a2 + 24) || !a4 || !a5 )
    return 60;
  v9 = KerberosCryptoPolicy::OpenEncryptionAlgorithm(a1, *(unsigned int *)(a2 + 4));
  v10 = v9;
  if ( !v9 )
    return 14;
  v12 = *(_DWORD *)(a1 + 56);
  v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 216LL))(v9);
  Key = KerberosCryptoPolicy::GetKey(a1, v13, a3, v12);
  if ( !Key )
    return 41;
  v17 = *(unsigned int *)(Key + 16);
  v18 = *(_QWORD *)(Key + 24);
  (*(void (__fastcall **)(__int64, _BYTE *, __int64 *, __int64, int))(*(_QWORD *)v10 + 168LL))(v10, v25, &v17, a3, 1);
  if ( v26 < 0 )
    goto LABEL_14;
  (*(void (__fastcall **)(__int64, _BYTE *, _BYTE *, _QWORD))(*(_QWORD *)v10 + 184LL))(v10, v23, v25, 0);
  if ( v24 < 0 )
  {
    Kerb3961::CipherStateReturn::~CipherStateReturn((Kerb3961::CipherStateReturn *)v23);
    v15 = 60;
LABEL_15:
    Kerb3961::SpecificKeyReturn::~SpecificKeyReturn((Kerb3961::SpecificKeyReturn *)v25);
    return v15;
  }
  v19[0] = *(unsigned int *)(a2 + 16);
  v19[1] = *(_QWORD *)(a2 + 24);
  v16 = *(_QWORD *)v10;
  v17 = 0;
  v18 = 0;
  (*(void (__fastcall **)(__int64, __int64 *, _BYTE *, _BYTE *, _QWORD *, __int64 *))(v16 + 208))(
    v10,
    &v20,
    v25,
    v23,
    v19,
    &v17);
  if ( v22 < 0 )
  {
    Kerb3961::OwnedBinary::~OwnedBinary((Kerb3961::OwnedBinary *)&v20);
    Kerb3961::CipherStateReturn::~CipherStateReturn((Kerb3961::CipherStateReturn *)v23);
LABEL_14:
    v15 = 41;
    goto LABEL_15;
  }
  if ( *a5 )
    MIDL_user_free(*a5);
  *a4 = v20;
  *a5 = v21;
  v21 = 0;
  v20 = 0;
  v22 = -1073741823;
  Kerb3961::OwnedBinary::~OwnedBinary((Kerb3961::OwnedBinary *)&v20);
  Kerb3961::CipherStateReturn::~CipherStateReturn((Kerb3961::CipherStateReturn *)v23);
  Kerb3961::SpecificKeyReturn::~SpecificKeyReturn((Kerb3961::SpecificKeyReturn *)v25);
  return 0;
}

```

## disassembly

```asm
0x18000c6ac  push    rbp
0x18000c6ae  push    rbx
0x18000c6af  push    rsi
0x18000c6b0  push    rdi
0x18000c6b1  push    r12
0x18000c6b3  push    r13
0x18000c6b5  push    r14
0x18000c6b7  push    r15
0x18000c6b9  lea     rbp, [rsp-7]
0x18000c6be  sub     rsp, 0B8h
0x18000c6c5  mov     r15, r9
0x18000c6c8  mov     r12, r8
0x18000c6cb  mov     rsi, rdx
0x18000c6ce  mov     r13, rcx
0x18000c6d1  test    rdx, rdx
0x18000c6d4  jz      loc_18000C87B
0x18000c6da  cmp     qword ptr [rdx+18h], 0
0x18000c6df  jz      loc_18000C87B
0x18000c6e5  test    r9, r9
0x18000c6e8  jz      loc_18000C87B
0x18000c6ee  mov     r14, [rbp+3Fh+arg_20]
0x18000c6f2  test    r14, r14
0x18000c6f5  jz      loc_18000C87B
0x18000c6fb  mov     edx, [rdx+4]
0x18000c6fe  call    ?OpenEncryptionAlgorithm@KerberosCryptoPolicy@@QEBAPEAUEncryptionAlgorithm@Kerb3961@@KW4KeyUsage@3@@Z; KerberosCryptoPolicy::OpenEncryptionAlgorithm(ulong,Kerb3961::KeyUsage)
0x18000c703  mov     rdi, rax
0x18000c706  test    rax, rax
0x18000c709  jnz     short loc_18000C713
0x18000c70b  lea     eax, [rdi+0Eh]
0x18000c70e  jmp     loc_18000C880
0x18000c713  mov     rax, [rax]
0x18000c716  mov     rcx, rdi
0x18000c719  mov     ebx, [r13+38h]
0x18000c71d  mov     rax, [rax+0D8h]
0x18000c724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c729  mov     rcx, [rbp+3Fh+arg_28]
0x18000c72d  mov     r9d, ebx
0x18000c730  mov     [rsp+0F0h+var_C8], rcx
0x18000c735  mov     r8, r12
0x18000c738  mov     rcx, r13
0x18000c73b  mov     edx, eax
0x18000c73d  call    ?GetKey@KerberosCryptoPolicy@@QEAAPEAU_KERB_ENCRYPTION_KEY@@JW4KeyUsage@Kerb3961@@W4KdcKeyType@@W4KdcPrincipalKeyState@@PEAK@Z; KerberosCryptoPolicy::GetKey(long,Kerb3961::KeyUsage,KdcKeyType,KdcPrincipalKeyState,ulong *)
0x18000c742  xor     ebx, ebx
0x18000c744  mov     rcx, rax
0x18000c747  test    rax, rax
0x18000c74a  jnz     short loc_18000C754
0x18000c74c  lea     eax, [rcx+29h]
0x18000c74f  jmp     loc_18000C880
0x18000c754  mov     eax, [rax+10h]
0x18000c757  lea     r8, [rbp+3Fh+var_B0]
0x18000c75b  mov     [rbp+3Fh+var_B0], rax
0x18000c75f  lea     rdx, [rbp+3Fh+var_60]
0x18000c763  mov     rax, [rcx+18h]
0x18000c767  mov     r9, r12
0x18000c76a  mov     [rbp+3Fh+var_A8], rax
0x18000c76e  mov     rcx, rdi
0x18000c771  mov     rax, [rdi]
0x18000c774  mov     dword ptr [rsp+0F0h+var_D0], 1
0x18000c77c  mov     rax, [rax+0A8h]
0x18000c783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c788  cmp     [rbp+3Fh+var_50], ebx
0x18000c78b  jl      loc_18000C821
0x18000c791  mov     rax, [rdi]
0x18000c794  lea     r8, [rbp+3Fh+var_60]
0x18000c798  xor     r9d, r9d
0x18000c79b  lea     rdx, [rbp+3Fh+var_78]
0x18000c79f  mov     rcx, rdi
0x18000c7a2  mov     rax, [rax+0B8h]
0x18000c7a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7ae  cmp     [rbp+3Fh+var_68], ebx
0x18000c7b1  jge     short loc_18000C7C3
0x18000c7b3  lea     rcx, [rbp+3Fh+var_78]; this
0x18000c7b7  call    ??1CipherStateReturn@Kerb3961@@QEAA@XZ; Kerb3961::CipherStateReturn::~CipherStateReturn(void)
0x18000c7bc  mov     ebx, 3Ch ; '<'
0x18000c7c1  jmp     short loc_18000C826
0x18000c7c3  mov     eax, [rsi+10h]
0x18000c7c6  lea     rcx, [rbp+3Fh+var_B0]
0x18000c7ca  mov     [rbp+3Fh+var_A0], rax
0x18000c7ce  lea     r9, [rbp+3Fh+var_78]
0x18000c7d2  mov     rax, [rsi+18h]
0x18000c7d6  lea     r8, [rbp+3Fh+var_60]
0x18000c7da  mov     [rsp+0F0h+var_C8], rcx
0x18000c7df  lea     rdx, [rbp+3Fh+var_90]
0x18000c7e3  mov     [rbp+3Fh+var_98], rax
0x18000c7e7  lea     rcx, [rbp+3Fh+var_A0]
0x18000c7eb  mov     rax, [rdi]
0x18000c7ee  mov     [rsp+0F0h+var_D0], rcx
0x18000c7f3  mov     rcx, rdi
0x18000c7f6  mov     [rbp+3Fh+var_B0], rbx
0x18000c7fa  mov     [rbp+3Fh+var_A8], rbx
0x18000c7fe  mov     rax, [rax+0D0h]
0x18000c805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c80a  cmp     [rbp+3Fh+var_80], ebx
0x18000c80d  jge     short loc_18000C833
0x18000c80f  lea     rcx, [rbp+3Fh+var_90]; this
0x18000c813  call    ??1OwnedBinary@Kerb3961@@QEAA@XZ; Kerb3961::OwnedBinary::~OwnedBinary(void)
0x18000c818  lea     rcx, [rbp+3Fh+var_78]; this
0x18000c81c  call    ??1CipherStateReturn@Kerb3961@@QEAA@XZ; Kerb3961::CipherStateReturn::~CipherStateReturn(void)
0x18000c821  mov     ebx, 29h ; ')'
0x18000c826  lea     rcx, [rbp+3Fh+var_60]; this
0x18000c82a  call    ??1SpecificKeyReturn@Kerb3961@@QEAA@XZ; Kerb3961::SpecificKeyReturn::~SpecificKeyReturn(void)
0x18000c82f  mov     eax, ebx
0x18000c831  jmp     short loc_18000C880
0x18000c833  mov     rcx, [r14]; void *
0x18000c836  test    rcx, rcx
0x18000c839  jz      short loc_18000C840
0x18000c83b  call    MIDL_user_free
0x18000c840  mov     eax, dword ptr [rbp+3Fh+var_90]
0x18000c843  lea     rcx, [rbp+3Fh+var_90]; this
0x18000c847  mov     [r15], eax
0x18000c84a  mov     rax, [rbp+3Fh+var_88]
0x18000c84e  mov     [r14], rax
0x18000c851  mov     [rbp+3Fh+var_88], rbx
0x18000c855  mov     [rbp+3Fh+var_90], rbx
0x18000c859  mov     [rbp+3Fh+var_80], 0C0000001h
0x18000c860  call    ??1OwnedBinary@Kerb3961@@QEAA@XZ; Kerb3961::OwnedBinary::~OwnedBinary(void)
0x18000c865  lea     rcx, [rbp+3Fh+var_78]; this
0x18000c869  call    ??1CipherStateReturn@Kerb3961@@QEAA@XZ; Kerb3961::CipherStateReturn::~CipherStateReturn(void)
0x18000c86e  lea     rcx, [rbp+3Fh+var_60]; this
0x18000c872  call    ??1SpecificKeyReturn@Kerb3961@@QEAA@XZ; Kerb3961::SpecificKeyReturn::~SpecificKeyReturn(void)
0x18000c877  xor     eax, eax
0x18000c879  jmp     short loc_18000C880
0x18000c87b  mov     eax, 3Ch ; '<'
0x18000c880  add     rsp, 0B8h
0x18000c887  pop     r15
0x18000c889  pop     r14
0x18000c88b  pop     r13
0x18000c88d  pop     r12
0x18000c88f  pop     rdi
0x18000c890  pop     rsi
0x18000c891  pop     rbx
0x18000c892  pop     rbp
0x18000c893  retn
```
