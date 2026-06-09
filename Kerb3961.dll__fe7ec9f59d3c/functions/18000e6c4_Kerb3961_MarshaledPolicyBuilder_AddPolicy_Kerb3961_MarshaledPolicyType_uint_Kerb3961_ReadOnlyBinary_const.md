# Kerb3961::MarshaledPolicyBuilder::AddPolicy(Kerb3961::MarshaledPolicyType,uint,Kerb3961::ReadOnlyBinary const &)

- ea: `0x18000e6c4`
- end: `0x18000e7fd`
- name: `?AddPolicy@MarshaledPolicyBuilder@Kerb3961@@AEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@W4MarshaledPolicyType@2@IAEBUReadOnlyBinary@2@@Z`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000ca80`

## callees

- `0x180001d64`
- `0x180002c64`
- `0x180002fc0`
- `0x18000901c`
- `0x18000e6c4`
- `0x18000e804`
- `0x18001d360`

## string_xrefs

- `0x18000e7a8`: `m_components.emplace_back(utl::move(buffer))`

## pseudocode

```c
_DWORD *__fastcall Kerb3961::MarshaledPolicyBuilder::AddPolicy(_QWORD *a1, _DWORD *a2, int a3, int a4, __int64 a5)
{
  unsigned __int64 v9; // r15
  int v10; // r8d
  int v11; // ebx
  void *v12; // rcx
  _DWORD *v13; // rdi
  __int64 v14; // rcx
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v20; // [rsp+20h] [rbp-68h] BYREF
  void *v21; // [rsp+28h] [rbp-60h]
  char *v22; // [rsp+30h] [rbp-58h]

  v9 = ((*(_QWORD *)a5 + 23LL) & 0xFFFFFFFFFFFFFFF8uLL) + 8;
  Kerb3961::MakeBuffer(&v20);
  v11 = (int)v22;
  if ( (int)v22 >= 0 )
  {
    v13 = v21;
    *(_DWORD *)v21 = a3;
    v13[1] = a4;
    *((_QWORD *)v13 + 1) = *(_QWORD *)a5;
    *((_QWORD *)v13 + 2) = v9;
    memcpy_0(v13 + 6, *(const void **)(a5 + 8), *(_QWORD *)a5);
    v14 = a1[2];
    if ( a1[1] != v14 )
      goto LABEL_12;
    v15 = 0xAAAAAAAAAAAAAAABuLL * ((v14 - *a1) >> 3);
    v16 = 7 * (v15 >> 2) + 8;
    if ( v16 > 0x555555555555555LL )
      v16 = 0x555555555555555LL;
    if ( v15 < v16
      && (unsigned __int8)utl::vector<Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::ResultBlock const & Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::ResultBlock & Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)>,utl::allocator<Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::ResultBlock const & Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::ResultBlock & Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)>>>::_SetCapacity(a1) )
    {
LABEL_12:
      v17 = a1[1];
      v18 = v20;
      *(_DWORD *)(v17 + 16) = v11;
      *(_QWORD *)v17 = v18;
      *(_QWORD *)(v17 + 8) = v13;
      a1[1] += 24LL;
      *a2 = 0;
      return a2;
    }
    Kerb3961::Logging::Verify::ConditionFailed(
      (Kerb3961::Logging::Verify *)"m_components.emplace_back(utl::move(buffer))",
      (const char *)v16);
    *a2 = -1073741801;
    if ( v13 )
    {
      v12 = v13;
LABEL_11:
      operator delete(v12, 0);
    }
  }
  else
  {
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"buffer", (const char *)(unsigned int)v22, v10);
    v12 = v21;
    *a2 = v11;
    if ( v12 )
      goto LABEL_11;
  }
  return a2;
}

```

## disassembly

```asm
0x18000e6c4  push    rbx
0x18000e6c6  push    rbp
0x18000e6c7  push    rsi
0x18000e6c8  push    rdi
0x18000e6c9  push    r12
0x18000e6cb  push    r13
0x18000e6cd  push    r14
0x18000e6cf  push    r15
0x18000e6d1  sub     rsp, 48h
0x18000e6d5  mov     r14, [rsp+88h+arg_20]
0x18000e6dd  mov     rsi, rdx
0x18000e6e0  mov     rbp, rcx
0x18000e6e3  mov     r12d, r9d
0x18000e6e6  lea     rcx, [rsp+88h+var_68]
0x18000e6eb  mov     r13d, r8d
0x18000e6ee  mov     r15, [r14]
0x18000e6f1  add     r15, 17h
0x18000e6f5  and     r15, 0FFFFFFFFFFFFFFF8h
0x18000e6f9  add     r15, 8
0x18000e6fd  mov     rdx, r15
0x18000e700  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x18000e705  mov     ebx, dword ptr [rsp+88h+var_58]
0x18000e709  test    ebx, ebx
0x18000e70b  jns     short loc_18000E730
0x18000e70d  mov     edx, ebx; char *
0x18000e70f  lea     rcx, aBuffer; "buffer"
0x18000e716  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000e71b  mov     rcx, [rsp+88h+var_60]
0x18000e720  mov     [rsi], ebx
0x18000e722  test    rcx, rcx
0x18000e725  jz      loc_18000E7E9
0x18000e72b  jmp     loc_18000E7C2
0x18000e730  mov     rdi, [rsp+88h+var_60]
0x18000e735  mov     [rdi], r13d
0x18000e738  lea     rcx, [rdi+18h]; void *
0x18000e73c  mov     [rdi+4], r12d
0x18000e740  mov     rax, [r14]
0x18000e743  mov     [rdi+8], rax
0x18000e747  mov     [rdi+10h], r15
0x18000e74b  mov     r8, [r14]; Size
0x18000e74e  mov     rdx, [r14+8]; Src
0x18000e752  call    memcpy_0
0x18000e757  mov     rcx, [rbp+10h]
0x18000e75b  cmp     [rbp+8], rcx
0x18000e75f  jnz     short loc_18000E7CB
0x18000e761  sub     rcx, [rbp+0]
0x18000e765  mov     rax, 0AAAAAAAAAAAAAAABh
0x18000e76f  sar     rcx, 3
0x18000e773  imul    rcx, rax
0x18000e777  mov     rax, rcx
0x18000e77a  shr     rax, 2
0x18000e77e  imul    rdx, rax, 7
0x18000e782  mov     rax, 555555555555555h
0x18000e78c  add     rdx, 8
0x18000e790  cmp     rdx, rax
0x18000e793  cmova   rdx, rax
0x18000e797  cmp     rcx, rdx
0x18000e79a  jnb     short loc_18000E7A8
0x18000e79c  mov     rcx, rbp
0x18000e79f  call    ?_SetCapacity@?$vector@U?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@Kerb3961@@V?$allocator@U?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@Kerb3961@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)>,utl::allocator<Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)>>>::_SetCapacity(unsigned __int64)
0x18000e7a4  test    al, al
0x18000e7a6  jnz     short loc_18000E7CB
0x18000e7a8  lea     rcx, aMComponentsEmp; "m_components.emplace_back(utl::move(buf"...
0x18000e7af  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000e7b4  mov     dword ptr [rsi], 0C0000017h
0x18000e7ba  test    rdi, rdi
0x18000e7bd  jz      short loc_18000E7E9
0x18000e7bf  mov     rcx, rdi; void *
0x18000e7c2  xor     edx, edx; struct std::nothrow_t *
0x18000e7c4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000e7c9  jmp     short loc_18000E7E9
0x18000e7cb  mov     rcx, [rbp+8]
0x18000e7cf  mov     rax, [rsp+88h+var_68]
0x18000e7d4  mov     [rcx+10h], ebx
0x18000e7d7  mov     [rcx], rax
0x18000e7da  mov     [rcx+8], rdi
0x18000e7de  add     qword ptr [rbp+8], 18h
0x18000e7e3  mov     dword ptr [rsi], 0
0x18000e7e9  mov     rax, rsi
0x18000e7ec  add     rsp, 48h
0x18000e7f0  pop     r15
0x18000e7f2  pop     r14
0x18000e7f4  pop     r13
0x18000e7f6  pop     r12
0x18000e7f8  pop     rdi
0x18000e7f9  pop     rsi
0x18000e7fa  pop     rbp
0x18000e7fb  pop     rbx
0x18000e7fc  retn
```
