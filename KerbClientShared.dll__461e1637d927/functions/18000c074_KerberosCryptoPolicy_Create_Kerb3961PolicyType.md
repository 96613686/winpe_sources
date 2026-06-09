# KerberosCryptoPolicy::Create(Kerb3961PolicyType)

- ea: `0x18000c074`
- end: `0x18000c1e8`
- name: `?Create@KerberosCryptoPolicy@@SA?AV?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@W4Kerb3961PolicyType@@@Z`
- size: `372`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000bc8c`
- `0x18000bcf4`
- `0x18000c00c`
- `0x18000c498`
- `0x180015010`

## callees

- `0x1800060d0`
- `0x180006140`
- `0x18000c074`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18000c09d`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18000c09d`
- `Kerb3961!__imp_GetLocalCipherPolicy` at `0x18000c08c`
- `Kerb3961!__imp_GetLocalCipherPolicy` at `0x18000c08c`

## pseudocode

```c
_QWORD *__fastcall KerberosCryptoPolicy::Create(_QWORD *a1)
{
  __int64 LocalCipherPolicy; // rbx
  _QWORD *v3; // rax
  _QWORD *v4; // rdi
  __int64 v5; // rcx
  __int64 v6; // rbx
  __int64 v8; // [rsp+20h] [rbp-30h] BYREF
  __int64 v9; // [rsp+28h] [rbp-28h]
  int v10; // [rsp+30h] [rbp-20h]
  _BYTE v11[24]; // [rsp+38h] [rbp-18h] BYREF
  _QWORD *v12; // [rsp+80h] [rbp+30h] BYREF

  LocalCipherPolicy = GetLocalCipherPolicy();
  v3 = LocalAlloc(0x40u, 0x80u);
  v4 = v3;
  if ( v3 )
  {
    *v3 = LocalCipherPolicy;
    *((_BYTE *)v3 + 8) = 0;
    v3[2] = 0;
    v3[3] = 0;
    v3[4] = 0;
    v3[5] = 0;
    v3[6] = 0;
    *((_DWORD *)v3 + 14) = 0;
    *((_BYTE *)v3 + 64) = 0;
    v3[9] = 0;
    *((_DWORD *)v3 + 20) = 0;
    *((_BYTE *)v3 + 88) = 0;
    v3[12] = 0;
    *((_BYTE *)v3 + 104) = 0;
    v3[14] = 0;
    v3[15] = 0;
    v5 = *v3;
    v12 = v3;
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v5 + 56LL))(v5, &v8);
    if ( v10 < 0 )
      goto LABEL_3;
    Kerb3961::CipherPartnerHandle::~CipherPartnerHandle((Kerb3961::CipherPartnerHandle *)(v4 + 2));
    v4[2] = v8;
    v4[3] = v9;
    v9 = 0;
    v8 = 0;
    v6 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v4 + 56LL))(*v4, v11);
    Kerb3961::CipherPartnerHandle::~CipherPartnerHandle((Kerb3961::CipherPartnerHandle *)&v8);
    v8 = *(_QWORD *)v6;
    v9 = *(_QWORD *)(v6 + 8);
    *(_QWORD *)(v6 + 8) = 0;
    *(_QWORD *)v6 = 0;
    v10 = *(_DWORD *)(v6 + 16);
    *(_DWORD *)(v6 + 16) = -1073741823;
    Kerb3961::CipherPartnerHandle::~CipherPartnerHandle((Kerb3961::CipherPartnerHandle *)v11);
    if ( v10 < 0 )
    {
LABEL_3:
      *a1 = 0;
    }
    else
    {
      Kerb3961::CipherPartnerHandle::~CipherPartnerHandle((Kerb3961::CipherPartnerHandle *)(v4 + 4));
      v4[4] = v8;
      v4[5] = v9;
      v9 = 0;
      v8 = 0;
      *a1 = v4;
      v12 = 0;
    }
    Kerb3961::CipherPartnerHandle::~CipherPartnerHandle((Kerb3961::CipherPartnerHandle *)&v8);
  }
  else
  {
    v12 = 0;
    *a1 = 0;
  }
  utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>((__int64 *)&v12);
  return a1;
}

```

## disassembly

```asm
0x18000c074  mov     [rsp-18h+arg_0], rbx
0x18000c079  mov     [rsp-18h+arg_8], rsi
0x18000c07e  push    rbp
0x18000c07f  push    rdi
0x18000c080  push    r14
0x18000c082  mov     rbp, rsp
0x18000c085  sub     rsp, 50h
0x18000c089  mov     rsi, rcx
0x18000c08c  call    cs:__imp_GetLocalCipherPolicy
0x18000c092  mov     edx, 80h; uBytes
0x18000c097  mov     rbx, rax
0x18000c09a  lea     ecx, [rdx-40h]; uFlags
0x18000c09d  call    cs:__imp_LocalAlloc
0x18000c0a3  xor     r14d, r14d
0x18000c0a6  mov     rdi, rax
0x18000c0a9  test    rax, rax
0x18000c0ac  jz      loc_18000C1C2
0x18000c0b2  mov     [rax], rbx
0x18000c0b5  lea     rdx, [rbp+var_30]
0x18000c0b9  mov     [rax+8], r14b
0x18000c0bd  mov     [rax+10h], r14
0x18000c0c1  mov     [rax+18h], r14
0x18000c0c5  mov     [rax+20h], r14
0x18000c0c9  mov     [rax+28h], r14
0x18000c0cd  mov     [rax+30h], r14
0x18000c0d1  mov     [rax+38h], r14d
0x18000c0d5  mov     [rax+40h], r14b
0x18000c0d9  mov     [rax+48h], r14
0x18000c0dd  mov     [rax+50h], r14d
0x18000c0e1  mov     [rax+58h], r14b
0x18000c0e5  mov     [rax+60h], r14
0x18000c0e9  mov     [rax+68h], r14b
0x18000c0ed  mov     [rax+70h], r14
0x18000c0f1  mov     [rax+78h], r14
0x18000c0f5  mov     rcx, [rax]
0x18000c0f8  mov     [rbp+arg_10], rax
0x18000c0fc  mov     rax, [rcx]
0x18000c0ff  mov     rax, [rax+38h]
0x18000c103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c108  cmp     [rbp+var_20], r14d
0x18000c10c  jge     short loc_18000C11F
0x18000c10e  mov     [rsi], r14
0x18000c111  lea     rcx, [rbp+var_30]; this
0x18000c115  call    ??1CipherPartnerHandle@Kerb3961@@QEAA@XZ; Kerb3961::CipherPartnerHandle::~CipherPartnerHandle(void)
0x18000c11a  jmp     loc_18000C1C9
0x18000c11f  lea     rcx, [rdi+10h]; this
0x18000c123  call    ??1CipherPartnerHandle@Kerb3961@@QEAA@XZ; Kerb3961::CipherPartnerHandle::~CipherPartnerHandle(void)
0x18000c128  mov     rax, [rbp+var_30]
0x18000c12c  lea     rdx, [rbp+var_18]
0x18000c130  mov     [rdi+10h], rax
0x18000c134  mov     rax, [rbp+var_28]
0x18000c138  mov     [rdi+18h], rax
0x18000c13c  mov     [rbp+var_28], r14
0x18000c140  mov     [rbp+var_30], r14
0x18000c144  mov     rcx, [rdi]
0x18000c147  mov     rax, [rcx]
0x18000c14a  mov     rax, [rax+38h]
0x18000c14e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c153  lea     rcx, [rbp+var_30]; this
0x18000c157  mov     rbx, rax
0x18000c15a  call    ??1CipherPartnerHandle@Kerb3961@@QEAA@XZ; Kerb3961::CipherPartnerHandle::~CipherPartnerHandle(void)
0x18000c15f  mov     rcx, [rbx]
0x18000c162  mov     [rbp+var_30], rcx
0x18000c166  mov     rcx, [rbx+8]
0x18000c16a  mov     [rbp+var_28], rcx
0x18000c16e  mov     [rbx+8], r14
0x18000c172  mov     [rbx], r14
0x18000c175  mov     ecx, [rbx+10h]
0x18000c178  mov     [rbp+var_20], ecx
0x18000c17b  lea     rcx, [rbp+var_18]; this
0x18000c17f  mov     dword ptr [rbx+10h], 0C0000001h
0x18000c186  call    ??1CipherPartnerHandle@Kerb3961@@QEAA@XZ; Kerb3961::CipherPartnerHandle::~CipherPartnerHandle(void)
0x18000c18b  cmp     [rbp+var_20], r14d
0x18000c18f  jl      loc_18000C10E
0x18000c195  lea     rcx, [rdi+20h]; this
0x18000c199  call    ??1CipherPartnerHandle@Kerb3961@@QEAA@XZ; Kerb3961::CipherPartnerHandle::~CipherPartnerHandle(void)
0x18000c19e  mov     rax, [rbp+var_30]
0x18000c1a2  mov     [rdi+20h], rax
0x18000c1a6  mov     rax, [rbp+var_28]
0x18000c1aa  mov     [rdi+28h], rax
0x18000c1ae  mov     [rbp+var_28], r14
0x18000c1b2  mov     [rbp+var_30], r14
0x18000c1b6  mov     [rsi], rdi
0x18000c1b9  mov     [rbp+arg_10], r14
0x18000c1bd  jmp     loc_18000C111
0x18000c1c2  mov     [rbp+arg_10], r14
0x18000c1c6  mov     [rsi], r14
0x18000c1c9  lea     rcx, [rbp+arg_10]
0x18000c1cd  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x18000c1d2  mov     rbx, [rsp+50h+arg_0]
0x18000c1d7  mov     rax, rsi
0x18000c1da  mov     rsi, [rsp+50h+arg_8]
0x18000c1df  add     rsp, 50h
0x18000c1e3  pop     r14
0x18000c1e5  pop     rdi
0x18000c1e6  pop     rbp
0x18000c1e7  retn
```
