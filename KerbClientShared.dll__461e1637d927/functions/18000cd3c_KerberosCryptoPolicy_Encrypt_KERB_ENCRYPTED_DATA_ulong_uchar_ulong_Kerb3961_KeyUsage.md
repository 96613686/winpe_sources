# KerberosCryptoPolicy::Encrypt(KERB_ENCRYPTED_DATA *,ulong,uchar *,ulong,Kerb3961::KeyUsage)

- ea: `0x18000cd3c`
- end: `0x18000cf21`
- name: `?Encrypt@KerberosCryptoPolicy@@QEAAJPEAUKERB_ENCRYPTED_DATA@@KPEAEKW4KeyUsage@Kerb3961@@@Z`
- size: `485`
- prototype: ``
- caller_count: `6`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180009fa0`
- `0x18000a3d0`
- `0x18000a650`
- `0x18000a920`
- `0x18000b5b0`
- `0x18000c2d0`

## callees

- `0x180007e10`
- `0x18000c66c`
- `0x18000c68c`
- `0x18000c89c`
- `0x18000cd3c`
- `0x18000e558`
- `0x180018204`
- `0x1800283fc`
- `0x180029010`

## pseudocode

```c
__int64 __fastcall KerberosCryptoPolicy::Encrypt(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  __int64 v6; // r13
  __int64 v11; // rax
  __int64 v12; // rsi
  unsigned int v13; // ebx
  unsigned int v14; // eax
  __int64 Key; // rax
  __int64 v16; // rcx
  __int64 v17; // rax
  __int64 v18; // r9
  __int64 v19; // rax
  void (__fastcall *v20)(__int64, size_t *, _QWORD *, _BYTE *, _QWORD *, __int64 *); // rax
  int v21; // esi
  void **v22; // rbx
  __int64 v23; // rcx
  unsigned int v24; // ebx
  __int64 v25; // [rsp+40h] [rbp-59h] BYREF
  __int64 v26; // [rsp+48h] [rbp-51h]
  _QWORD v27[2]; // [rsp+50h] [rbp-49h] BYREF
  size_t Size; // [rsp+60h] [rbp-39h] BYREF
  void *Src; // [rsp+68h] [rbp-31h]
  int v30; // [rsp+70h] [rbp-29h]
  _QWORD v31[2]; // [rsp+78h] [rbp-21h] BYREF
  int v32; // [rsp+88h] [rbp-11h]
  _BYTE v33[16]; // [rsp+90h] [rbp-9h] BYREF
  int v34; // [rsp+A0h] [rbp+7h]

  v6 = a3;
  if ( !a2 )
    return 60;
  v11 = KerberosCryptoPolicy::SelectEncryptionAlgorithm(a1, a6);
  v12 = v11;
  if ( !v11 )
    return 14;
  v13 = *(_DWORD *)(a1 + 56);
  v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v11 + 216LL))(v11);
  a5 = 0;
  Key = KerberosCryptoPolicy::GetKey(a1, v14, a6, v13);
  if ( !Key )
    return 14;
  v16 = *(unsigned int *)(Key + 16);
  v26 = *(_QWORD *)(Key + 24);
  v17 = *(_QWORD *)v12;
  v25 = v16;
  (*(void (__fastcall **)(__int64, _QWORD *, __int64 *, __int64, int, int *))(v17 + 168))(v12, v31, &v25, a6, 1, &a5);
  if ( v32 < 0 )
  {
LABEL_6:
    Kerb3961::SpecificKeyReturn::~SpecificKeyReturn((Kerb3961::SpecificKeyReturn *)v31);
    return 60;
  }
  LOBYTE(v18) = 1;
  (*(void (__fastcall **)(__int64, _BYTE *, _QWORD *, __int64))(*(_QWORD *)v12 + 184LL))(v12, v33, v31, v18);
  if ( v34 < 0 )
  {
    Kerb3961::CipherStateReturn::~CipherStateReturn((Kerb3961::CipherStateReturn *)v33);
    goto LABEL_6;
  }
  v19 = *(_QWORD *)v12;
  v25 = 0;
  v20 = *(void (__fastcall **)(__int64, size_t *, _QWORD *, _BYTE *, _QWORD *, __int64 *))(v19 + 200);
  v26 = 0;
  v27[0] = v6;
  v27[1] = a4;
  v20(v12, &Size, v31, v33, v27, &v25);
  if ( v30 < 0 )
  {
    v24 = 60;
  }
  else
  {
    v21 = Size;
    v22 = (void **)(a2 + 24);
    if ( *(_DWORD *)(a2 + 16) >= (unsigned int)Size && *v22 )
    {
      memcpy_0(*v22, Src, (unsigned int)Size);
    }
    else
    {
      if ( *v22 )
        MIDL_user_free(*v22);
      *v22 = Src;
      Src = 0;
      Size = 0;
      v30 = -1073741823;
    }
    v23 = v31[0];
    *(_DWORD *)(a2 + 16) = v21;
    *(_DWORD *)(a2 + 4) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 216LL))(v23);
    v24 = 0;
  }
  Kerb3961::OwnedBinary::~OwnedBinary((Kerb3961::OwnedBinary *)&Size);
  Kerb3961::CipherStateReturn::~CipherStateReturn((Kerb3961::CipherStateReturn *)v33);
  Kerb3961::SpecificKeyReturn::~SpecificKeyReturn((Kerb3961::SpecificKeyReturn *)v31);
  return v24;
}

```

## disassembly

```asm
0x18000cd3c  push    rbp
0x18000cd3e  push    rbx
0x18000cd3f  push    rsi
0x18000cd40  push    rdi
0x18000cd41  push    r12
0x18000cd43  push    r13
0x18000cd45  push    r15
0x18000cd47  lea     rbp, [rsp-17h]
0x18000cd4c  sub     rsp, 0B0h
0x18000cd53  mov     r13d, r8d
0x18000cd56  mov     r12, r9
0x18000cd59  mov     rdi, rdx
0x18000cd5c  mov     r15, rcx
0x18000cd5f  test    rdx, rdx
0x18000cd62  jnz     short loc_18000CD6E
0x18000cd64  mov     eax, 3Ch ; '<'
0x18000cd69  jmp     loc_18000CF0F
0x18000cd6e  mov     rdx, [rbp+47h+arg_28]
0x18000cd72  call    ?SelectEncryptionAlgorithm@KerberosCryptoPolicy@@QEAAPEAUEncryptionAlgorithm@Kerb3961@@W4KeyUsage@3@W4KdcPrincipalKeyState@@@Z; KerberosCryptoPolicy::SelectEncryptionAlgorithm(Kerb3961::KeyUsage,KdcPrincipalKeyState)
0x18000cd77  mov     rsi, rax
0x18000cd7a  test    rax, rax
0x18000cd7d  jz      loc_18000CF0A
0x18000cd83  mov     rcx, [rax]
0x18000cd86  mov     ebx, [r15+38h]
0x18000cd8a  mov     rax, [rcx+0D8h]
0x18000cd91  mov     rcx, rsi
0x18000cd94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd99  mov     r8, [rbp+47h+arg_28]
0x18000cd9d  lea     rcx, [rbp+47h+arg_20]
0x18000cda1  mov     [rsp+0E0h+var_B8], rcx
0x18000cda6  mov     r9d, ebx
0x18000cda9  mov     rcx, r15
0x18000cdac  mov     [rbp+47h+arg_20], 0
0x18000cdb3  mov     edx, eax
0x18000cdb5  call    ?GetKey@KerberosCryptoPolicy@@QEAAPEAU_KERB_ENCRYPTION_KEY@@JW4KeyUsage@Kerb3961@@W4KdcKeyType@@W4KdcPrincipalKeyState@@PEAK@Z; KerberosCryptoPolicy::GetKey(long,Kerb3961::KeyUsage,KdcKeyType,KdcPrincipalKeyState,ulong *)
0x18000cdba  xor     r15d, r15d
0x18000cdbd  test    rax, rax
0x18000cdc0  jz      loc_18000CF0A
0x18000cdc6  mov     ecx, [rax+10h]
0x18000cdc9  lea     r8, [rbp+47h+var_A0]
0x18000cdcd  mov     rax, [rax+18h]
0x18000cdd1  lea     rdx, [rbp+47h+var_68]
0x18000cdd5  mov     r9, [rbp+47h+arg_28]
0x18000cdd9  mov     [rbp+47h+var_98], rax
0x18000cddd  mov     rax, [rsi]
0x18000cde0  mov     [rbp+47h+var_A0], rcx
0x18000cde4  mov     rcx, rsi
0x18000cde7  mov     dword ptr [rsp+0E0h+var_C0], 1
0x18000cdef  mov     rax, [rax+0A8h]
0x18000cdf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdfb  cmp     [rbp+47h+var_58], r15d
0x18000cdff  jge     short loc_18000CE0F
0x18000ce01  lea     rcx, [rbp+47h+var_68]; this
0x18000ce05  call    ??1SpecificKeyReturn@Kerb3961@@QEAA@XZ; Kerb3961::SpecificKeyReturn::~SpecificKeyReturn(void)
0x18000ce0a  jmp     loc_18000CD64
0x18000ce0f  mov     rax, [rsi]
0x18000ce12  lea     r8, [rbp+47h+var_68]
0x18000ce16  mov     r9b, 1
0x18000ce19  lea     rdx, [rbp+47h+var_50]
0x18000ce1d  mov     rcx, rsi
0x18000ce20  mov     rax, [rax+0B8h]
0x18000ce27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce2c  cmp     [rbp+47h+var_40], r15d
0x18000ce30  jge     short loc_18000CE3D
0x18000ce32  lea     rcx, [rbp+47h+var_50]; this
0x18000ce36  call    ??1CipherStateReturn@Kerb3961@@QEAA@XZ; Kerb3961::CipherStateReturn::~CipherStateReturn(void)
0x18000ce3b  jmp     short loc_18000CE01
0x18000ce3d  mov     rax, [rsi]
0x18000ce40  lea     rcx, [rbp+47h+var_A0]
0x18000ce44  mov     [rsp+0E0h+var_B8], rcx
0x18000ce49  lea     r9, [rbp+47h+var_50]
0x18000ce4d  lea     rcx, [rbp+47h+var_90]
0x18000ce51  mov     [rbp+47h+var_A0], r15
0x18000ce55  mov     [rsp+0E0h+var_C0], rcx
0x18000ce5a  lea     r8, [rbp+47h+var_68]
0x18000ce5e  mov     rax, [rax+0C8h]
0x18000ce65  lea     rdx, [rbp+47h+Size]
0x18000ce69  mov     rcx, rsi
0x18000ce6c  mov     [rbp+47h+var_98], r15
0x18000ce70  mov     [rbp+47h+var_90], r13
0x18000ce74  mov     [rbp+47h+var_88], r12
0x18000ce78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce7d  cmp     [rbp+47h+var_70], r15d
0x18000ce81  jl      short loc_18000CEE6
0x18000ce83  mov     esi, dword ptr [rbp+47h+Size]
0x18000ce86  lea     rbx, [rdi+18h]
0x18000ce8a  cmp     [rdi+10h], esi
0x18000ce8d  jb      short loc_18000CEA5
0x18000ce8f  mov     rcx, [rbx]; void *
0x18000ce92  test    rcx, rcx
0x18000ce95  jz      short loc_18000CEA5
0x18000ce97  mov     rdx, [rbp+47h+Src]; Src
0x18000ce9b  mov     r8d, esi; Size
0x18000ce9e  call    memcpy_0
0x18000cea3  jmp     short loc_18000CEC8
0x18000cea5  mov     rcx, [rbx]; void *
0x18000cea8  test    rcx, rcx
0x18000ceab  jz      short loc_18000CEB2
0x18000cead  call    MIDL_user_free
0x18000ceb2  mov     rax, [rbp+47h+Src]
0x18000ceb6  mov     [rbx], rax
0x18000ceb9  mov     [rbp+47h+Src], r15
0x18000cebd  mov     [rbp+47h+Size], r15
0x18000cec1  mov     [rbp+47h+var_70], 0C0000001h
0x18000cec8  mov     rcx, [rbp+47h+var_68]
0x18000cecc  mov     [rdi+10h], esi
0x18000cecf  mov     rax, [rcx]
0x18000ced2  mov     rax, [rax+0D8h]
0x18000ced9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cede  mov     [rdi+4], eax
0x18000cee1  mov     ebx, r15d
0x18000cee4  jmp     short loc_18000CEEB
0x18000cee6  mov     ebx, 3Ch ; '<'
0x18000ceeb  lea     rcx, [rbp+47h+Size]; this
0x18000ceef  call    ??1OwnedBinary@Kerb3961@@QEAA@XZ; Kerb3961::OwnedBinary::~OwnedBinary(void)
0x18000cef4  lea     rcx, [rbp+47h+var_50]; this
0x18000cef8  call    ??1CipherStateReturn@Kerb3961@@QEAA@XZ; Kerb3961::CipherStateReturn::~CipherStateReturn(void)
0x18000cefd  lea     rcx, [rbp+47h+var_68]; this
0x18000cf01  call    ??1SpecificKeyReturn@Kerb3961@@QEAA@XZ; Kerb3961::SpecificKeyReturn::~SpecificKeyReturn(void)
0x18000cf06  mov     eax, ebx
0x18000cf08  jmp     short loc_18000CF0F
0x18000cf0a  mov     eax, 0Eh
0x18000cf0f  add     rsp, 0B0h
0x18000cf16  pop     r15
0x18000cf18  pop     r13
0x18000cf1a  pop     r12
0x18000cf1c  pop     rdi
0x18000cf1d  pop     rsi
0x18000cf1e  pop     rbx
0x18000cf1f  pop     rbp
0x18000cf20  retn
```
