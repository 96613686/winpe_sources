# KerberosCryptoPolicy::Create(Kerb3961PolicyType)

- ea: `0x14001e8dc`
- end: `0x14001ea4c`
- name: `?Create@KerberosCryptoPolicy@@SA?AV?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@W4Kerb3961PolicyType@@@Z`
- size: `368`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14001bfa8`
- `0x14001ea54`

## callees

- `0x140002a80`
- `0x140003730`
- `0x14001ab60`
- `0x14001e8dc`
- `0x14003a010`

## import_xrefs

- `Kerb3961!__imp_GetLocalCipherPolicy` at `0x14001e8f4`
- `Kerb3961!__imp_GetLocalCipherPolicy` at `0x14001e8f4`

## pseudocode

```c
__int64 **__fastcall KerberosCryptoPolicy::Create(__int64 **a1)
{
  __int64 LocalCipherPolicy; // rbx
  __int64 *v3; // rax
  __int64 *v4; // rdi
  __int64 v5; // rcx
  __int64 v6; // rbx
  __int64 v8; // [rsp+20h] [rbp-30h] BYREF
  __int64 v9; // [rsp+28h] [rbp-28h]
  int v10; // [rsp+30h] [rbp-20h]
  _BYTE v11[24]; // [rsp+38h] [rbp-18h] BYREF
  __int64 *v12; // [rsp+80h] [rbp+30h] BYREF

  LocalCipherPolicy = GetLocalCipherPolicy();
  v3 = (__int64 *)operator new(0x80u);
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
    v6 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)*v4 + 56LL))(*v4, v11);
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
  utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v12);
  return a1;
}

```

## disassembly

```asm
0x14001e8dc  mov     [rsp-18h+arg_0], rbx
0x14001e8e1  mov     [rsp-18h+arg_8], rsi
0x14001e8e6  push    rbp
0x14001e8e7  push    rdi
0x14001e8e8  push    r14
0x14001e8ea  mov     rbp, rsp
0x14001e8ed  sub     rsp, 50h
0x14001e8f1  mov     rsi, rcx
0x14001e8f4  call    cs:__imp_GetLocalCipherPolicy
0x14001e8fa  mov     ecx, 80h; Size
0x14001e8ff  mov     rbx, rax
0x14001e902  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001e907  xor     r14d, r14d
0x14001e90a  mov     rdi, rax
0x14001e90d  test    rax, rax
0x14001e910  jz      loc_14001EA26
0x14001e916  mov     [rax], rbx
0x14001e919  lea     rdx, [rbp+var_30]
0x14001e91d  mov     [rax+8], r14b
0x14001e921  mov     [rax+10h], r14
0x14001e925  mov     [rax+18h], r14
0x14001e929  mov     [rax+20h], r14
0x14001e92d  mov     [rax+28h], r14
0x14001e931  mov     [rax+30h], r14
0x14001e935  mov     [rax+38h], r14d
0x14001e939  mov     [rax+40h], r14b
0x14001e93d  mov     [rax+48h], r14
0x14001e941  mov     [rax+50h], r14d
0x14001e945  mov     [rax+58h], r14b
0x14001e949  mov     [rax+60h], r14
0x14001e94d  mov     [rax+68h], r14b
0x14001e951  mov     [rax+70h], r14
0x14001e955  mov     [rax+78h], r14
0x14001e959  mov     rcx, [rax]
0x14001e95c  mov     [rbp+arg_10], rax
0x14001e960  mov     rax, [rcx]
0x14001e963  mov     rax, [rax+38h]
0x14001e967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e96c  cmp     [rbp+var_20], r14d
0x14001e970  jge     short loc_14001E983
0x14001e972  mov     [rsi], r14
0x14001e975  lea     rcx, [rbp+var_30]; this
0x14001e979  call    ??1CipherPartnerHandle@Kerb3961@@QEAA@XZ; Kerb3961::CipherPartnerHandle::~CipherPartnerHandle(void)
0x14001e97e  jmp     loc_14001EA2D
0x14001e983  lea     rcx, [rdi+10h]; this
0x14001e987  call    ??1CipherPartnerHandle@Kerb3961@@QEAA@XZ; Kerb3961::CipherPartnerHandle::~CipherPartnerHandle(void)
0x14001e98c  mov     rax, [rbp+var_30]
0x14001e990  lea     rdx, [rbp+var_18]
0x14001e994  mov     [rdi+10h], rax
0x14001e998  mov     rax, [rbp+var_28]
0x14001e99c  mov     [rdi+18h], rax
0x14001e9a0  mov     [rbp+var_28], r14
0x14001e9a4  mov     [rbp+var_30], r14
0x14001e9a8  mov     rcx, [rdi]
0x14001e9ab  mov     rax, [rcx]
0x14001e9ae  mov     rax, [rax+38h]
0x14001e9b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001e9b7  lea     rcx, [rbp+var_30]; this
0x14001e9bb  mov     rbx, rax
0x14001e9be  call    ??1CipherPartnerHandle@Kerb3961@@QEAA@XZ; Kerb3961::CipherPartnerHandle::~CipherPartnerHandle(void)
0x14001e9c3  mov     rcx, [rbx]
0x14001e9c6  mov     [rbp+var_30], rcx
0x14001e9ca  mov     rcx, [rbx+8]
0x14001e9ce  mov     [rbp+var_28], rcx
0x14001e9d2  mov     [rbx+8], r14
0x14001e9d6  mov     [rbx], r14
0x14001e9d9  mov     ecx, [rbx+10h]
0x14001e9dc  mov     [rbp+var_20], ecx
0x14001e9df  lea     rcx, [rbp+var_18]; this
0x14001e9e3  mov     dword ptr [rbx+10h], 0C0000001h
0x14001e9ea  call    ??1CipherPartnerHandle@Kerb3961@@QEAA@XZ; Kerb3961::CipherPartnerHandle::~CipherPartnerHandle(void)
0x14001e9ef  cmp     [rbp+var_20], r14d
0x14001e9f3  jl      loc_14001E972
0x14001e9f9  lea     rcx, [rdi+20h]; this
0x14001e9fd  call    ??1CipherPartnerHandle@Kerb3961@@QEAA@XZ; Kerb3961::CipherPartnerHandle::~CipherPartnerHandle(void)
0x14001ea02  mov     rax, [rbp+var_30]
0x14001ea06  mov     [rdi+20h], rax
0x14001ea0a  mov     rax, [rbp+var_28]
0x14001ea0e  mov     [rdi+28h], rax
0x14001ea12  mov     [rbp+var_28], r14
0x14001ea16  mov     [rbp+var_30], r14
0x14001ea1a  mov     [rsi], rdi
0x14001ea1d  mov     [rbp+arg_10], r14
0x14001ea21  jmp     loc_14001E975
0x14001ea26  mov     [rbp+arg_10], r14
0x14001ea2a  mov     [rsi], r14
0x14001ea2d  lea     rcx, [rbp+arg_10]
0x14001ea31  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x14001ea36  mov     rbx, [rsp+50h+arg_0]
0x14001ea3b  mov     rax, rsi
0x14001ea3e  mov     rsi, [rsp+50h+arg_8]
0x14001ea43  add     rsp, 50h
0x14001ea47  pop     r14
0x14001ea49  pop     rdi
0x14001ea4a  pop     rbp
0x14001ea4b  retn
```
