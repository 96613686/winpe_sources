# KerberosCryptoPolicy::DecryptNoCopy(KERB_ENCRYPTED_DATA *,Kerb3961::KeyUsage,ulong *,void * *,ulong *,KdcPrincipalKeyState)

- ea: `0x14001efd0`
- end: `0x14001f1cd`
- name: `?DecryptNoCopy@KerberosCryptoPolicy@@AEAAJPEAUKERB_ENCRYPTED_DATA@@W4KeyUsage@Kerb3961@@PEAKPEAPEAX2W4KdcPrincipalKeyState@@@Z`
- size: `509`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14001bad8`

## callees

- `0x140006720`
- `0x14001bf88`
- `0x14001e3a8`
- `0x14001eaf4`
- `0x14001efb0`
- `0x14001efd0`
- `0x14001f460`
- `0x14003a010`

## pseudocode

```c
__int64 __fastcall KerberosCryptoPolicy::DecryptNoCopy(
        KerberosCryptoPolicy *a1,
        __int64 a2,
        __int64 a3,
        _DWORD *a4,
        void **a5)
{
  __int64 v8; // rax
  __int64 v9; // rdi
  unsigned int v11; // ebx
  unsigned int v12; // eax
  __int64 Key; // rax
  unsigned int v14; // ebx
  __int64 v15; // rax
  __int64 v16; // [rsp+40h] [rbp-61h] BYREF
  __int64 v17; // [rsp+48h] [rbp-59h]
  _QWORD v18[2]; // [rsp+50h] [rbp-51h] BYREF
  __int64 v19; // [rsp+60h] [rbp-41h] BYREF
  void *v20; // [rsp+68h] [rbp-39h]
  int v21; // [rsp+70h] [rbp-31h]
  _BYTE v22[16]; // [rsp+78h] [rbp-29h] BYREF
  int v23; // [rsp+88h] [rbp-19h]
  _BYTE v24[16]; // [rsp+90h] [rbp-11h] BYREF
  int v25; // [rsp+A0h] [rbp-1h]

  if ( !a2 || !*(_QWORD *)(a2 + 24) || !a4 || !a5 )
    return 60;
  v8 = KerberosCryptoPolicy::OpenEncryptionAlgorithm(a1, *(_DWORD *)(a2 + 4), 2);
  v9 = v8;
  if ( !v8 )
    return 14;
  v11 = *((_DWORD *)a1 + 14);
  v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 216LL))(v8);
  Key = KerberosCryptoPolicy::GetKey(a1, v12, 2, v11);
  if ( !Key )
    return 41;
  v16 = *(unsigned int *)(Key + 16);
  v17 = *(_QWORD *)(Key + 24);
  (*(void (__fastcall **)(__int64, _BYTE *, __int64 *, __int64, int))(*(_QWORD *)v9 + 168LL))(v9, v24, &v16, 2, 1);
  if ( v25 < 0 )
    goto LABEL_14;
  (*(void (__fastcall **)(__int64, _BYTE *, _BYTE *, _QWORD))(*(_QWORD *)v9 + 184LL))(v9, v22, v24, 0);
  if ( v23 < 0 )
  {
    Kerb3961::CipherStateReturn::~CipherStateReturn((Kerb3961::CipherStateReturn *)v22);
    v14 = 60;
LABEL_15:
    Kerb3961::SpecificKeyReturn::~SpecificKeyReturn((Kerb3961::SpecificKeyReturn *)v24);
    return v14;
  }
  v18[0] = *(unsigned int *)(a2 + 16);
  v18[1] = *(_QWORD *)(a2 + 24);
  v15 = *(_QWORD *)v9;
  v16 = 0;
  v17 = 0;
  (*(void (__fastcall **)(__int64, __int64 *, _BYTE *, _BYTE *, _QWORD *, __int64 *))(v15 + 208))(
    v9,
    &v19,
    v24,
    v22,
    v18,
    &v16);
  if ( v21 < 0 )
  {
    Kerb3961::OwnedBinary::~OwnedBinary((Kerb3961::OwnedBinary *)&v19);
    Kerb3961::CipherStateReturn::~CipherStateReturn((Kerb3961::CipherStateReturn *)v22);
LABEL_14:
    v14 = 41;
    goto LABEL_15;
  }
  if ( *a5 )
    SafeAllocaFreeToHeap(*a5);
  *a4 = v19;
  *a5 = v20;
  v20 = 0;
  v19 = 0;
  v21 = -1073741823;
  Kerb3961::OwnedBinary::~OwnedBinary((Kerb3961::OwnedBinary *)&v19);
  Kerb3961::CipherStateReturn::~CipherStateReturn((Kerb3961::CipherStateReturn *)v22);
  Kerb3961::SpecificKeyReturn::~SpecificKeyReturn((Kerb3961::SpecificKeyReturn *)v24);
  return 0;
}

```

## disassembly

```asm
0x14001efd0  push    rbp
0x14001efd2  push    rbx
0x14001efd3  push    rsi
0x14001efd4  push    rdi
0x14001efd5  push    r13
0x14001efd7  push    r14
0x14001efd9  push    r15
0x14001efdb  lea     rbp, [rsp-0Fh]
0x14001efe0  sub     rsp, 0B0h
0x14001efe7  mov     r15, r9
0x14001efea  mov     rsi, rdx
0x14001efed  mov     r13, rcx
0x14001eff0  test    rdx, rdx
0x14001eff3  jz      loc_14001F1B6
0x14001eff9  cmp     qword ptr [rdx+18h], 0
0x14001effe  jz      loc_14001F1B6
0x14001f004  test    r9, r9
0x14001f007  jz      loc_14001F1B6
0x14001f00d  mov     r14, [rbp+3Fh+arg_20]
0x14001f011  test    r14, r14
0x14001f014  jz      loc_14001F1B6
0x14001f01a  mov     edx, [rdx+4]
0x14001f01d  mov     r8d, 2
0x14001f023  call    ?OpenEncryptionAlgorithm@KerberosCryptoPolicy@@QEBAPEAUEncryptionAlgorithm@Kerb3961@@KW4KeyUsage@3@@Z; KerberosCryptoPolicy::OpenEncryptionAlgorithm(ulong,Kerb3961::KeyUsage)
0x14001f028  mov     rdi, rax
0x14001f02b  test    rax, rax
0x14001f02e  jnz     short loc_14001F038
0x14001f030  lea     eax, [rdi+0Eh]
0x14001f033  jmp     loc_14001F1BB
0x14001f038  mov     rax, [rax]
0x14001f03b  mov     rcx, rdi
0x14001f03e  mov     ebx, [r13+38h]
0x14001f042  mov     rax, [rax+0D8h]
0x14001f049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f04e  mov     rcx, [rbp+3Fh+arg_28]
0x14001f052  mov     r9d, ebx
0x14001f055  mov     [rsp+0E0h+var_B8], rcx
0x14001f05a  mov     ebx, 2
0x14001f05f  mov     r8d, ebx
0x14001f062  mov     rcx, r13
0x14001f065  mov     edx, eax
0x14001f067  call    ?GetKey@KerberosCryptoPolicy@@QEAAPEAU_KERB_ENCRYPTION_KEY@@JW4KeyUsage@Kerb3961@@W4KdcKeyType@@W4KdcPrincipalKeyState@@PEAK@Z; KerberosCryptoPolicy::GetKey(long,Kerb3961::KeyUsage,KdcKeyType,KdcPrincipalKeyState,ulong *)
0x14001f06c  mov     rcx, rax
0x14001f06f  test    rax, rax
0x14001f072  jnz     short loc_14001F07C
0x14001f074  lea     eax, [rbx+27h]
0x14001f077  jmp     loc_14001F1BB
0x14001f07c  mov     eax, [rax+10h]
0x14001f07f  lea     r8, [rbp+3Fh+var_A0]
0x14001f083  mov     [rbp+3Fh+var_A0], rax
0x14001f087  lea     rdx, [rbp+3Fh+var_50]
0x14001f08b  mov     rax, [rcx+18h]
0x14001f08f  mov     r9, rbx
0x14001f092  mov     [rbp+3Fh+var_98], rax
0x14001f096  mov     rcx, rdi
0x14001f099  mov     rax, [rdi]
0x14001f09c  mov     dword ptr [rsp+0E0h+var_C0], 1
0x14001f0a4  mov     rax, [rax+0A8h]
0x14001f0ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f0b0  cmp     [rbp+3Fh+var_40], 0
0x14001f0b4  jl      loc_14001F154
0x14001f0ba  mov     rax, [rdi]
0x14001f0bd  lea     r8, [rbp+3Fh+var_50]
0x14001f0c1  xor     r9d, r9d
0x14001f0c4  lea     rdx, [rbp+3Fh+var_68]
0x14001f0c8  mov     rcx, rdi
0x14001f0cb  mov     rax, [rax+0B8h]
0x14001f0d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f0d7  cmp     [rbp+3Fh+var_58], 0
0x14001f0db  jge     short loc_14001F0ED
0x14001f0dd  lea     rcx, [rbp+3Fh+var_68]; this
0x14001f0e1  call    ??1CipherStateReturn@Kerb3961@@QEAA@XZ; Kerb3961::CipherStateReturn::~CipherStateReturn(void)
0x14001f0e6  mov     ebx, 3Ch ; '<'
0x14001f0eb  jmp     short loc_14001F159
0x14001f0ed  mov     eax, [rsi+10h]
0x14001f0f0  lea     rcx, [rbp+3Fh+var_A0]
0x14001f0f4  mov     [rbp+3Fh+var_90], rax
0x14001f0f8  lea     r9, [rbp+3Fh+var_68]
0x14001f0fc  mov     rax, [rsi+18h]
0x14001f100  lea     r8, [rbp+3Fh+var_50]
0x14001f104  mov     [rsp+0E0h+var_B8], rcx
0x14001f109  lea     rdx, [rbp+3Fh+var_80]
0x14001f10d  mov     [rbp+3Fh+var_88], rax
0x14001f111  lea     rcx, [rbp+3Fh+var_90]
0x14001f115  mov     rax, [rdi]
0x14001f118  mov     [rsp+0E0h+var_C0], rcx
0x14001f11d  mov     rcx, rdi
0x14001f120  mov     [rbp+3Fh+var_A0], 0
0x14001f128  mov     [rbp+3Fh+var_98], 0
0x14001f130  mov     rax, [rax+0D0h]
0x14001f137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001f13c  cmp     [rbp+3Fh+var_70], 0
0x14001f140  jge     short loc_14001F166
0x14001f142  lea     rcx, [rbp+3Fh+var_80]; this
0x14001f146  call    ??1OwnedBinary@Kerb3961@@QEAA@XZ; Kerb3961::OwnedBinary::~OwnedBinary(void)
0x14001f14b  lea     rcx, [rbp+3Fh+var_68]; this
0x14001f14f  call    ??1CipherStateReturn@Kerb3961@@QEAA@XZ; Kerb3961::CipherStateReturn::~CipherStateReturn(void)
0x14001f154  mov     ebx, 29h ; ')'
0x14001f159  lea     rcx, [rbp+3Fh+var_50]; this
0x14001f15d  call    ??1SpecificKeyReturn@Kerb3961@@QEAA@XZ; Kerb3961::SpecificKeyReturn::~SpecificKeyReturn(void)
0x14001f162  mov     eax, ebx
0x14001f164  jmp     short loc_14001F1BB
0x14001f166  mov     rcx, [r14]; void *
0x14001f169  test    rcx, rcx
0x14001f16c  jz      short loc_14001F173
0x14001f16e  call    SafeAllocaFreeToHeap
0x14001f173  mov     eax, dword ptr [rbp+3Fh+var_80]
0x14001f176  lea     rcx, [rbp+3Fh+var_80]; this
0x14001f17a  mov     [r15], eax
0x14001f17d  mov     rax, [rbp+3Fh+var_78]
0x14001f181  mov     [r14], rax
0x14001f184  mov     [rbp+3Fh+var_78], 0
0x14001f18c  mov     [rbp+3Fh+var_80], 0
0x14001f194  mov     [rbp+3Fh+var_70], 0C0000001h
0x14001f19b  call    ??1OwnedBinary@Kerb3961@@QEAA@XZ; Kerb3961::OwnedBinary::~OwnedBinary(void)
0x14001f1a0  lea     rcx, [rbp+3Fh+var_68]; this
0x14001f1a4  call    ??1CipherStateReturn@Kerb3961@@QEAA@XZ; Kerb3961::CipherStateReturn::~CipherStateReturn(void)
0x14001f1a9  lea     rcx, [rbp+3Fh+var_50]; this
0x14001f1ad  call    ??1SpecificKeyReturn@Kerb3961@@QEAA@XZ; Kerb3961::SpecificKeyReturn::~SpecificKeyReturn(void)
0x14001f1b2  xor     eax, eax
0x14001f1b4  jmp     short loc_14001F1BB
0x14001f1b6  mov     eax, 3Ch ; '<'
0x14001f1bb  add     rsp, 0B0h
0x14001f1c2  pop     r15
0x14001f1c4  pop     r14
0x14001f1c6  pop     r13
0x14001f1c8  pop     rdi
0x14001f1c9  pop     rsi
0x14001f1ca  pop     rbx
0x14001f1cb  pop     rbp
0x14001f1cc  retn
```
