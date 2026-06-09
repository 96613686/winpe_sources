# KerberosCryptoPolicy::Create(Kerb3961PolicyType)

- ea: `0x18000bd80`
- end: `0x18000bf1e`
- name: `?Create@KerberosCryptoPolicy@@SA?AV?$unique_ptr@VKerberosCryptoPolicy@@U?$default_delete@VKerberosCryptoPolicy@@@utl@@@utl@@W4Kerb3961PolicyType@@@Z`
- size: `414`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x180009d50`
- `0x18000af04`

## callees

- `0x180001a00`
- `0x180002074`
- `0x180009c88`
- `0x18000bd80`
- `0x18000d010`

## import_xrefs

- `Kerb3961!__imp_GetDomainCipherPolicy` at `0x18000bd93`
- `Kerb3961!__imp_GetDomainCipherPolicy` at `0x18000bd93`

## pseudocode

```c
KerberosCryptoPolicy **__fastcall KerberosCryptoPolicy::Create(KerberosCryptoPolicy **a1)
{
  __int64 DomainCipherPolicy; // rbx
  KerberosCryptoPolicy *v3; // rdi
  _QWORD *v4; // r14
  _QWORD *v5; // rbx
  __int64 v6; // rbx
  __int64 v8; // [rsp+20h] [rbp-38h] BYREF
  __int64 v9; // [rsp+28h] [rbp-30h]
  int v10; // [rsp+30h] [rbp-28h]
  _QWORD v11[4]; // [rsp+38h] [rbp-20h] BYREF

  DomainCipherPolicy = GetDomainCipherPolicy();
  v3 = (KerberosCryptoPolicy *)operator new(0x80u);
  *((_QWORD *)v3 + 6) = 0;
  v4 = (_QWORD *)((char *)v3 + 32);
  *(_QWORD *)v3 = DomainCipherPolicy;
  v5 = (_QWORD *)((char *)v3 + 16);
  *((_QWORD *)v3 + 2) = 0;
  *((_QWORD *)v3 + 3) = 0;
  *((_QWORD *)v3 + 4) = 0;
  *((_QWORD *)v3 + 5) = 0;
  *((_BYTE *)v3 + 8) = 0;
  *((_DWORD *)v3 + 14) = 0;
  *((_BYTE *)v3 + 64) = 0;
  *((_QWORD *)v3 + 9) = 0;
  *((_DWORD *)v3 + 20) = 0;
  *((_BYTE *)v3 + 88) = 0;
  *((_QWORD *)v3 + 12) = 0;
  *((_BYTE *)v3 + 104) = 0;
  *((_QWORD *)v3 + 14) = 0;
  *((_QWORD *)v3 + 15) = 0;
  (*(void (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)v3 + 56LL))(*(_QWORD *)v3, &v8);
  if ( v10 < 0 )
    goto LABEL_9;
  if ( *((_QWORD *)v3 + 3) )
    (*(void (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)*v5 + 64LL))(*v5, v5);
  *v5 = v8;
  *((_QWORD *)v3 + 3) = v9;
  v9 = 0;
  v8 = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD *))(**(_QWORD **)v3 + 56LL))(*(_QWORD *)v3, v11);
  if ( v9 )
    (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 64LL))(v8, &v8);
  v8 = *(_QWORD *)v6;
  v9 = *(_QWORD *)(v6 + 8);
  *(_QWORD *)(v6 + 8) = 0;
  *(_QWORD *)v6 = 0;
  v10 = *(_DWORD *)(v6 + 16);
  *(_DWORD *)(v6 + 16) = -1073741823;
  if ( v11[1] )
    (*(void (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)v11[0] + 64LL))(v11[0], v11);
  if ( v10 >= 0 )
  {
    if ( *((_QWORD *)v3 + 5) )
      (*(void (__fastcall **)(_QWORD, _QWORD *))(*(_QWORD *)*v4 + 64LL))(*v4, v4);
    *v4 = v8;
    *((_QWORD *)v3 + 5) = v9;
    *a1 = v3;
  }
  else
  {
LABEL_9:
    *a1 = 0;
    if ( v9 )
      (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 64LL))(v8, &v8);
    KerberosCryptoPolicy::~KerberosCryptoPolicy(v3);
    operator delete(v3, (const struct std::nothrow_t *)0x80);
  }
  return a1;
}

```

## disassembly

```asm
0x18000bd80  push    rbp
0x18000bd82  push    rbx
0x18000bd83  push    rsi
0x18000bd84  push    rdi
0x18000bd85  push    r14
0x18000bd87  push    r15
0x18000bd89  mov     rbp, rsp
0x18000bd8c  sub     rsp, 58h
0x18000bd90  mov     rsi, rcx
0x18000bd93  call    cs:__imp_GetDomainCipherPolicy
0x18000bd99  mov     ecx, 80h; Size
0x18000bd9e  mov     rbx, rax
0x18000bda1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bda6  xor     r15d, r15d
0x18000bda9  lea     rdx, [rbp+var_38]
0x18000bdad  mov     rdi, rax
0x18000bdb0  mov     [rax+30h], r15
0x18000bdb4  lea     r14, [rax+20h]
0x18000bdb8  mov     [rax], rbx
0x18000bdbb  lea     rbx, [rax+10h]
0x18000bdbf  mov     [rbx], r15
0x18000bdc2  mov     [rbx+8], r15
0x18000bdc6  mov     [r14], r15
0x18000bdc9  mov     [r14+8], r15
0x18000bdcd  mov     [rax+8], r15b
0x18000bdd1  mov     [rax+38h], r15d
0x18000bdd5  mov     [rax+40h], r15b
0x18000bdd9  mov     [rax+48h], r15
0x18000bddd  mov     [rax+50h], r15d
0x18000bde1  mov     [rax+58h], r15b
0x18000bde5  mov     [rax+60h], r15
0x18000bde9  mov     [rax+68h], r15b
0x18000bded  mov     [rax+70h], r15
0x18000bdf1  mov     [rax+78h], r15
0x18000bdf5  mov     rcx, [rax]
0x18000bdf8  mov     rax, [rcx]
0x18000bdfb  mov     rax, [rax+38h]
0x18000bdff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be04  cmp     [rbp+var_28], r15d
0x18000be08  jl      loc_18000BEB0
0x18000be0e  cmp     [rbx+8], r15
0x18000be12  jz      short loc_18000BE26
0x18000be14  mov     rcx, [rbx]
0x18000be17  mov     rdx, rbx
0x18000be1a  mov     rax, [rcx]
0x18000be1d  mov     rax, [rax+40h]
0x18000be21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be26  mov     rax, [rbp+var_38]
0x18000be2a  lea     rdx, [rbp+var_20]
0x18000be2e  mov     [rbx], rax
0x18000be31  mov     rax, [rbp+var_30]
0x18000be35  mov     [rbx+8], rax
0x18000be39  mov     [rbp+var_30], r15
0x18000be3d  mov     [rbp+var_38], r15
0x18000be41  mov     rcx, [rdi]
0x18000be44  mov     rax, [rcx]
0x18000be47  mov     rax, [rax+38h]
0x18000be4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be50  mov     rbx, rax
0x18000be53  cmp     [rbp+var_30], r15
0x18000be57  jz      short loc_18000BE6D
0x18000be59  mov     rcx, [rbp+var_38]
0x18000be5d  mov     rdx, [rcx]
0x18000be60  mov     rax, [rdx+40h]
0x18000be64  lea     rdx, [rbp+var_38]
0x18000be68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be6d  mov     rcx, [rbx]
0x18000be70  mov     [rbp+var_38], rcx
0x18000be74  mov     rax, [rbx+8]
0x18000be78  mov     [rbp+var_30], rax
0x18000be7c  mov     [rbx+8], r15
0x18000be80  mov     [rbx], r15
0x18000be83  mov     eax, [rbx+10h]
0x18000be86  mov     [rbp+var_28], eax
0x18000be89  mov     dword ptr [rbx+10h], 0C0000001h
0x18000be90  cmp     [rbp+var_18], r15
0x18000be94  jz      short loc_18000BEAA
0x18000be96  mov     rcx, [rbp+var_20]
0x18000be9a  lea     rdx, [rbp+var_20]
0x18000be9e  mov     rax, [rcx]
0x18000bea1  mov     rax, [rax+40h]
0x18000bea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000beaa  cmp     [rbp+var_28], r15d
0x18000beae  jge     short loc_18000BEE4
0x18000beb0  mov     [rsi], r15
0x18000beb3  cmp     [rbp+var_30], r15
0x18000beb7  jz      short loc_18000BECD
0x18000beb9  mov     rcx, [rbp+var_38]
0x18000bebd  lea     rdx, [rbp+var_38]
0x18000bec1  mov     rax, [rcx]
0x18000bec4  mov     rax, [rax+40h]
0x18000bec8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000becd  mov     rcx, rdi; this
0x18000bed0  call    ??1KerberosCryptoPolicy@@QEAA@XZ; KerberosCryptoPolicy::~KerberosCryptoPolicy(void)
0x18000bed5  mov     edx, 80h; struct std::nothrow_t *
0x18000beda  mov     rcx, rdi; void *
0x18000bedd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000bee2  jmp     short loc_18000BF0E
0x18000bee4  cmp     [r14+8], r15
0x18000bee8  jz      short loc_18000BEFC
0x18000beea  mov     rcx, [r14]
0x18000beed  mov     rdx, r14
0x18000bef0  mov     rax, [rcx]
0x18000bef3  mov     rax, [rax+40h]
0x18000bef7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000befc  mov     rax, [rbp+var_38]
0x18000bf00  mov     [r14], rax
0x18000bf03  mov     rax, [rbp+var_30]
0x18000bf07  mov     [r14+8], rax
0x18000bf0b  mov     [rsi], rdi
0x18000bf0e  mov     rax, rsi
0x18000bf11  add     rsp, 58h
0x18000bf15  pop     r15
0x18000bf17  pop     r14
0x18000bf19  pop     rdi
0x18000bf1a  pop     rsi
0x18000bf1b  pop     rbx
0x18000bf1c  pop     rbp
0x18000bf1d  retn
```
