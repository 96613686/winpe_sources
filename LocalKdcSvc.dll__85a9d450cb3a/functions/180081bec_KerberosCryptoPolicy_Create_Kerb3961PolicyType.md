# KerberosCryptoPolicy::Create(Kerb3961PolicyType)

- ea: `0x180081bec`
- end: `0x180081d3a`
- name: `?Create@KerberosCryptoPolicy@@SA?AV?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@W4Kerb3961PolicyType@@@Z`
- size: `334`
- prototype: `__int64 **__fastcall(__int64 **)`
- caller_count: `32`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000be4c`
- `0x180010d44`
- `0x180011fc0`
- `0x180013f64`
- `0x180014554`
- `0x18001cb70`
- `0x18001d17c`
- `0x18001d2a4`
- `0x180021eb4`
- `0x180024ffc`
- `0x180026d04`
- `0x18002dd48`
- `0x18002e6c4`
- `0x180030324`
- `0x1800412e0`
- `0x18004b348`
- `0x180050e78`
- `0x180058454`
- `0x18005a3a4`
- `0x18005c334`
- `0x180060c24`
- `0x180061bbc`
- `0x1800684f4`
- `0x18006ac88`
- `0x18006ad68`
- `0x18006b4e0`
- `0x180080a90`
- `0x180081714`
- `0x180081d40`
- `0x180083144`
- `0x18008422c`
- `0x180085580`

## callees

- `0x180002f24`
- `0x18000ab40`
- `0x18000ab5c`
- `0x180081bec`
- `0x18009c010`

## import_xrefs

- `Kerb3961!__imp_GetDomainCipherPolicy` at `0x180081bff`
- `Kerb3961!__imp_GetDomainCipherPolicy` at `0x180081bff`

## pseudocode

```c
__int64 **__fastcall KerberosCryptoPolicy::Create(__int64 **a1)
{
  __int64 DomainCipherPolicy; // rbx
  __int64 *v3; // rax
  __int64 *v4; // rsi
  Kerb3961::CipherPartnerHandle *v5; // r14
  Kerb3961::CipherPartnerHandle *v6; // rbx
  __int64 v7; // rbx
  __int64 v9; // [rsp+20h] [rbp-38h] BYREF
  __int64 v10; // [rsp+28h] [rbp-30h]
  int v11; // [rsp+30h] [rbp-28h]
  _BYTE v12[32]; // [rsp+38h] [rbp-20h] BYREF
  __int64 *v13; // [rsp+A0h] [rbp+48h] BYREF

  DomainCipherPolicy = GetDomainCipherPolicy();
  v3 = (__int64 *)operator new(0x80u);
  v13 = v3;
  v4 = v3;
  v3[6] = 0;
  v5 = (Kerb3961::CipherPartnerHandle *)(v3 + 4);
  *v3 = DomainCipherPolicy;
  v6 = (Kerb3961::CipherPartnerHandle *)(v3 + 2);
  v3[2] = 0;
  v3[3] = 0;
  v3[4] = 0;
  v3[5] = 0;
  *((_BYTE *)v3 + 8) = 0;
  *((_DWORD *)v3 + 14) = 0;
  *((_BYTE *)v3 + 64) = 0;
  v3[9] = 0;
  *((_DWORD *)v3 + 20) = 0;
  *((_BYTE *)v3 + 88) = 0;
  v3[12] = 0;
  *((_BYTE *)v3 + 104) = 0;
  v3[14] = 0;
  v3[15] = 0;
  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*v3 + 56LL))(*v3, &v9);
  if ( v11 < 0 )
    goto LABEL_2;
  Kerb3961::CipherPartnerHandle::~CipherPartnerHandle(v6);
  *(_QWORD *)v6 = v9;
  *((_QWORD *)v6 + 1) = v10;
  v10 = 0;
  v9 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)*v4 + 56LL))(*v4, v12);
  Kerb3961::CipherPartnerHandle::~CipherPartnerHandle((Kerb3961::CipherPartnerHandle *)&v9);
  v9 = *(_QWORD *)v7;
  v10 = *(_QWORD *)(v7 + 8);
  *(_QWORD *)(v7 + 8) = 0;
  *(_QWORD *)v7 = 0;
  v11 = *(_DWORD *)(v7 + 16);
  *(_DWORD *)(v7 + 16) = -1073741823;
  Kerb3961::CipherPartnerHandle::~CipherPartnerHandle((Kerb3961::CipherPartnerHandle *)v12);
  if ( v11 < 0 )
  {
LABEL_2:
    *a1 = 0;
  }
  else
  {
    Kerb3961::CipherPartnerHandle::~CipherPartnerHandle(v5);
    *(_QWORD *)v5 = v9;
    *((_QWORD *)v5 + 1) = v10;
    v10 = 0;
    v9 = 0;
    *a1 = v4;
    v13 = 0;
  }
  Kerb3961::CipherPartnerHandle::~CipherPartnerHandle((Kerb3961::CipherPartnerHandle *)&v9);
  utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(&v13);
  return a1;
}

```

## disassembly

```asm
0x180081bec  push    rbp
0x180081bee  push    rbx
0x180081bef  push    rsi
0x180081bf0  push    rdi
0x180081bf1  push    r14
0x180081bf3  push    r15
0x180081bf5  mov     rbp, rsp
0x180081bf8  sub     rsp, 58h
0x180081bfc  mov     rdi, rcx
0x180081bff  call    cs:__imp_GetDomainCipherPolicy
0x180081c05  mov     ecx, 80h; Size
0x180081c0a  mov     rbx, rax
0x180081c0d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180081c12  xor     r15d, r15d
0x180081c15  mov     [rbp+arg_10], rax
0x180081c19  mov     rsi, rax
0x180081c1c  lea     rdx, [rbp+var_38]
0x180081c20  mov     [rax+30h], r15
0x180081c24  lea     r14, [rax+20h]
0x180081c28  mov     [rax], rbx
0x180081c2b  lea     rbx, [rax+10h]
0x180081c2f  mov     [rbx], r15
0x180081c32  mov     [rbx+8], r15
0x180081c36  mov     [r14], r15
0x180081c39  mov     [r14+8], r15
0x180081c3d  mov     [rax+8], r15b
0x180081c41  mov     [rax+38h], r15d
0x180081c45  mov     [rax+40h], r15b
0x180081c49  mov     [rax+48h], r15
0x180081c4d  mov     [rax+50h], r15d
0x180081c51  mov     [rax+58h], r15b
0x180081c55  mov     [rax+60h], r15
0x180081c59  mov     [rax+68h], r15b
0x180081c5d  mov     [rax+70h], r15
0x180081c61  mov     [rax+78h], r15
0x180081c65  mov     rcx, [rax]
0x180081c68  mov     rax, [rcx]
0x180081c6b  mov     rax, [rax+38h]
0x180081c6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081c74  cmp     [rbp+var_28], r15d
0x180081c78  jge     short loc_180081C82
0x180081c7a  mov     [rdi], r15
0x180081c7d  jmp     loc_180081D18
0x180081c82  mov     rcx, rbx; this
0x180081c85  call    ??1CipherPartnerHandle@Kerb3961@@QEAA@XZ; Kerb3961::CipherPartnerHandle::~CipherPartnerHandle(void)
0x180081c8a  mov     rax, [rbp+var_38]
0x180081c8e  lea     rdx, [rbp+var_20]
0x180081c92  mov     [rbx], rax
0x180081c95  mov     rax, [rbp+var_30]
0x180081c99  mov     [rbx+8], rax
0x180081c9d  mov     [rbp+var_30], r15
0x180081ca1  mov     [rbp+var_38], r15
0x180081ca5  mov     rcx, [rsi]
0x180081ca8  mov     rax, [rcx]
0x180081cab  mov     rax, [rax+38h]
0x180081caf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081cb4  lea     rcx, [rbp+var_38]; this
0x180081cb8  mov     rbx, rax
0x180081cbb  call    ??1CipherPartnerHandle@Kerb3961@@QEAA@XZ; Kerb3961::CipherPartnerHandle::~CipherPartnerHandle(void)
0x180081cc0  mov     rcx, [rbx]
0x180081cc3  mov     [rbp+var_38], rcx
0x180081cc7  mov     rcx, [rbx+8]
0x180081ccb  mov     [rbp+var_30], rcx
0x180081ccf  mov     [rbx+8], r15
0x180081cd3  mov     [rbx], r15
0x180081cd6  mov     ecx, [rbx+10h]
0x180081cd9  mov     [rbp+var_28], ecx
0x180081cdc  lea     rcx, [rbp+var_20]; this
0x180081ce0  mov     dword ptr [rbx+10h], 0C0000001h
0x180081ce7  call    ??1CipherPartnerHandle@Kerb3961@@QEAA@XZ; Kerb3961::CipherPartnerHandle::~CipherPartnerHandle(void)
0x180081cec  cmp     [rbp+var_28], r15d
0x180081cf0  jl      short loc_180081C7A
0x180081cf2  mov     rcx, r14; this
0x180081cf5  call    ??1CipherPartnerHandle@Kerb3961@@QEAA@XZ; Kerb3961::CipherPartnerHandle::~CipherPartnerHandle(void)
0x180081cfa  mov     rax, [rbp+var_38]
0x180081cfe  mov     [r14], rax
0x180081d01  mov     rax, [rbp+var_30]
0x180081d05  mov     [r14+8], rax
0x180081d09  mov     [rbp+var_30], r15
0x180081d0d  mov     [rbp+var_38], r15
0x180081d11  mov     [rdi], rsi
0x180081d14  mov     [rbp+arg_10], r15
0x180081d18  lea     rcx, [rbp+var_38]; this
0x180081d1c  call    ??1CipherPartnerHandle@Kerb3961@@QEAA@XZ; Kerb3961::CipherPartnerHandle::~CipherPartnerHandle(void)
0x180081d21  lea     rcx, [rbp+arg_10]
0x180081d25  call    ??1?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>::~unique_ptr<KerberosCryptoPolicy,utl::default_delete<KerberosCryptoPolicy>>(void)
0x180081d2a  mov     rax, rdi
0x180081d2d  add     rsp, 58h
0x180081d31  pop     r15
0x180081d33  pop     r14
0x180081d35  pop     rdi
0x180081d36  pop     rsi
0x180081d37  pop     rbx
0x180081d38  pop     rbp
0x180081d39  retn
```
