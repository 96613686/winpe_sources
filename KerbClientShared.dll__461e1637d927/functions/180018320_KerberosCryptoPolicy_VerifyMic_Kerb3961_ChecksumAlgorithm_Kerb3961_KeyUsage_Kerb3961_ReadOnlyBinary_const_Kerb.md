# KerberosCryptoPolicy::VerifyMic(Kerb3961::ChecksumAlgorithm *,Kerb3961::KeyUsage,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,KdcPrincipalKeyState)

- ea: `0x180018320`
- end: `0x18001843d`
- name: `?VerifyMic@KerberosCryptoPolicy@@QEAA_NPEAUChecksumAlgorithm@Kerb3961@@W4KeyUsage@3@AEBUReadOnlyBinary@3@2W4KdcPrincipalKeyState@@@Z`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009c50`

## callees

- `0x18000c66c`
- `0x180017128`
- `0x180018204`
- `0x180018320`
- `0x180029010`

## pseudocode

```c
bool __fastcall KerberosCryptoPolicy::VerifyMic(
        KerberosCryptoPolicy *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6)
{
  unsigned int v9; // eax
  __int64 v10; // rax
  __int64 *v11; // rdi
  unsigned int v12; // ebx
  unsigned int v13; // eax
  __int64 Key; // rax
  __int64 v15; // rcx
  __int64 v16; // rax
  bool v17; // bl
  _QWORD v19[2]; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v20[16]; // [rsp+40h] [rbp-58h] BYREF
  int v21; // [rsp+50h] [rbp-48h]

  v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a2 + 120LL))(a2);
  v10 = KerberosCryptoPolicy::OpenEncryptionAlgorithm(a1, v9, 17);
  v11 = (__int64 *)v10;
  if ( !v10 )
    return 0;
  v12 = *((_DWORD *)a1 + 14);
  v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 216LL))(v10);
  a6 = 0;
  Key = KerberosCryptoPolicy::GetKey(a1, v13, 17, v12);
  if ( !Key )
    return 0;
  v15 = *(unsigned int *)(Key + 16);
  v19[1] = *(_QWORD *)(Key + 24);
  v16 = *v11;
  v19[0] = v15;
  (*(void (__fastcall **)(__int64 *, _BYTE *, _QWORD *, __int64, int, int *))(v16 + 168))(v11, v20, v19, 17, 2, &a6);
  v17 = v21 >= 0
     && *(int *)(*(__int64 (__fastcall **)(__int64, int *, _BYTE *, __int64, __int64))(*(_QWORD *)a2 + 96LL))(
                  a2,
                  &a6,
                  v20,
                  a4,
                  a5) >= 0;
  Kerb3961::SpecificKeyReturn::~SpecificKeyReturn((Kerb3961::SpecificKeyReturn *)v20);
  return v17;
}

```

## disassembly

```asm
0x180018320  push    rbx
0x180018322  push    rbp
0x180018323  push    rsi
0x180018324  push    rdi
0x180018325  push    r12
0x180018327  push    r14
0x180018329  sub     rsp, 68h
0x18001832d  mov     rax, [rdx]
0x180018330  mov     rbp, rcx
0x180018333  mov     rcx, rdx
0x180018336  mov     r14, r9
0x180018339  mov     rsi, rdx
0x18001833c  mov     rax, [rax+78h]
0x180018340  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018345  mov     r12d, 11h
0x18001834b  mov     edx, eax
0x18001834d  mov     r8d, r12d
0x180018350  mov     rcx, rbp
0x180018353  call    ?OpenEncryptionAlgorithm@KerberosCryptoPolicy@@QEBAPEAUEncryptionAlgorithm@Kerb3961@@KW4KeyUsage@3@@Z; KerberosCryptoPolicy::OpenEncryptionAlgorithm(ulong,Kerb3961::KeyUsage)
0x180018358  mov     rdi, rax
0x18001835b  test    rax, rax
0x18001835e  jz      loc_18001842E
0x180018364  mov     rcx, [rax]
0x180018367  mov     ebx, [rbp+38h]
0x18001836a  mov     rax, [rcx+0D8h]
0x180018371  mov     rcx, rdi
0x180018374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018379  lea     rcx, [rsp+98h+arg_28]
0x180018381  mov     [rsp+98h+arg_28], 0
0x18001838c  mov     [rsp+98h+var_70], rcx
0x180018391  mov     r9d, ebx
0x180018394  mov     rcx, rbp
0x180018397  mov     r8d, r12d
0x18001839a  mov     edx, eax
0x18001839c  call    ?GetKey@KerberosCryptoPolicy@@QEAAPEAU_KERB_ENCRYPTION_KEY@@JW4KeyUsage@Kerb3961@@W4KdcKeyType@@W4KdcPrincipalKeyState@@PEAK@Z; KerberosCryptoPolicy::GetKey(long,Kerb3961::KeyUsage,KdcKeyType,KdcPrincipalKeyState,ulong *)
0x1800183a1  test    rax, rax
0x1800183a4  jz      loc_18001842E
0x1800183aa  mov     ecx, [rax+10h]
0x1800183ad  lea     r8, [rsp+98h+var_68]
0x1800183b2  mov     rax, [rax+18h]
0x1800183b6  lea     rdx, [rsp+98h+var_58]
0x1800183bb  mov     [rsp+98h+var_60], rax
0x1800183c0  mov     r9d, r12d
0x1800183c3  mov     rax, [rdi]
0x1800183c6  mov     [rsp+98h+var_68], rcx
0x1800183cb  mov     rcx, rdi
0x1800183ce  mov     dword ptr [rsp+98h+var_78], 2
0x1800183d6  mov     rax, [rax+0A8h]
0x1800183dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800183e2  cmp     [rsp+98h+var_48], 0
0x1800183e7  jl      short loc_18001841E
0x1800183e9  mov     rax, [rsi]
0x1800183ec  lea     r8, [rsp+98h+var_58]
0x1800183f1  mov     rcx, [rsp+98h+arg_20]
0x1800183f9  lea     rdx, [rsp+98h+arg_28]
0x180018401  mov     [rsp+98h+var_78], rcx
0x180018406  mov     r9, r14
0x180018409  mov     rcx, rsi
0x18001840c  mov     rax, [rax+60h]
0x180018410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018415  cmp     dword ptr [rax], 0
0x180018418  jl      short loc_18001841E
0x18001841a  mov     bl, 1
0x18001841c  jmp     short loc_180018420
0x18001841e  xor     ebx, ebx
0x180018420  lea     rcx, [rsp+98h+var_58]; this
0x180018425  call    ??1SpecificKeyReturn@Kerb3961@@QEAA@XZ; Kerb3961::SpecificKeyReturn::~SpecificKeyReturn(void)
0x18001842a  mov     al, bl
0x18001842c  jmp     short loc_180018430
0x18001842e  xor     al, al
0x180018430  add     rsp, 68h
0x180018434  pop     r14
0x180018436  pop     r12
0x180018438  pop     rdi
0x180018439  pop     rsi
0x18001843a  pop     rbp
0x18001843b  pop     rbx
0x18001843c  retn
```
