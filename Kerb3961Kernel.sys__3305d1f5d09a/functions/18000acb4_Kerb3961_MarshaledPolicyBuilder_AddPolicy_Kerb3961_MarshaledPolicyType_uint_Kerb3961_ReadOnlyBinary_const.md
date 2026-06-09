# Kerb3961::MarshaledPolicyBuilder::AddPolicy(Kerb3961::MarshaledPolicyType,uint,Kerb3961::ReadOnlyBinary const &)

- ea: `0x18000acb4`
- end: `0x18000adec`
- name: `?AddPolicy@MarshaledPolicyBuilder@Kerb3961@@AEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@W4MarshaledPolicyType@2@IAEBUReadOnlyBinary@2@@Z`
- size: `312`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c230`

## callees

- `0x180005b1c`
- `0x18000acb4`
- `0x18000af4c`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`
- `0x180012300`

## string_xrefs

- `0x18000ad98`: `m_components.emplace_back(utl::move(buffer))`

## pseudocode

```c
_DWORD *__fastcall Kerb3961::MarshaledPolicyBuilder::AddPolicy(_QWORD *a1, _DWORD *a2, int a3, int a4, __int64 a5)
{
  unsigned __int64 v9; // r15
  int v10; // r8d
  int v11; // ebx
  _DWORD *v12; // rcx
  _DWORD *v13; // rdi
  __int64 v14; // rcx
  unsigned __int64 v15; // rcx
  unsigned __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v20; // [rsp+20h] [rbp-68h] BYREF
  _DWORD *v21; // [rsp+28h] [rbp-60h]
  char *v22; // [rsp+30h] [rbp-58h]

  v9 = ((*(_QWORD *)a5 + 23LL) & 0xFFFFFFFFFFFFFFF8uLL) + 8;
  Kerb3961::MakeBuffer(&v20);
  v11 = (int)v22;
  if ( (int)v22 >= 0 )
  {
    v13 = v21;
    *v21 = a3;
    v13[1] = a4;
    *((_QWORD *)v13 + 1) = *(_QWORD *)a5;
    *((_QWORD *)v13 + 2) = v9;
    memmove(v13 + 6, *(const void **)(a5 + 8), *(_QWORD *)a5);
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
      Kerb3961Free(v12);
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
0x18000acb4  push    rbx
0x18000acb6  push    rbp
0x18000acb7  push    rsi
0x18000acb8  push    rdi
0x18000acb9  push    r12
0x18000acbb  push    r13
0x18000acbd  push    r14
0x18000acbf  push    r15
0x18000acc1  sub     rsp, 48h
0x18000acc5  mov     r14, [rsp+88h+arg_20]
0x18000accd  mov     rsi, rdx
0x18000acd0  mov     rbp, rcx
0x18000acd3  mov     r12d, r9d
0x18000acd6  lea     rcx, [rsp+88h+var_68]
0x18000acdb  mov     r13d, r8d
0x18000acde  mov     r15, [r14]
0x18000ace1  add     r15, 17h
0x18000ace5  and     r15, 0FFFFFFFFFFFFFFF8h
0x18000ace9  add     r15, 8
0x18000aced  mov     rdx, r15
0x18000acf0  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x18000acf5  mov     ebx, dword ptr [rsp+88h+var_58]
0x18000acf9  test    ebx, ebx
0x18000acfb  jns     short loc_18000AD20
0x18000acfd  mov     edx, ebx; char *
0x18000acff  lea     rcx, aBuffer; "buffer"
0x18000ad06  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000ad0b  mov     rcx, [rsp+88h+var_60]
0x18000ad10  mov     [rsi], ebx
0x18000ad12  test    rcx, rcx
0x18000ad15  jz      loc_18000ADD7
0x18000ad1b  jmp     loc_18000ADB2
0x18000ad20  mov     rdi, [rsp+88h+var_60]
0x18000ad25  mov     [rdi], r13d
0x18000ad28  lea     rcx, [rdi+18h]; void *
0x18000ad2c  mov     [rdi+4], r12d
0x18000ad30  mov     rax, [r14]
0x18000ad33  mov     [rdi+8], rax
0x18000ad37  mov     [rdi+10h], r15
0x18000ad3b  mov     r8, [r14]; Size
0x18000ad3e  mov     rdx, [r14+8]; Src
0x18000ad42  call    memmove
0x18000ad47  mov     rcx, [rbp+10h]
0x18000ad4b  cmp     [rbp+8], rcx
0x18000ad4f  jnz     short loc_18000ADB9
0x18000ad51  sub     rcx, [rbp+0]
0x18000ad55  mov     rax, 0AAAAAAAAAAAAAAABh
0x18000ad5f  sar     rcx, 3
0x18000ad63  imul    rcx, rax
0x18000ad67  mov     rax, rcx
0x18000ad6a  shr     rax, 2
0x18000ad6e  imul    rdx, rax, 7
0x18000ad72  mov     rax, 555555555555555h
0x18000ad7c  add     rdx, 8
0x18000ad80  cmp     rdx, rax
0x18000ad83  cmova   rdx, rax
0x18000ad87  cmp     rcx, rdx
0x18000ad8a  jnb     short loc_18000AD98
0x18000ad8c  mov     rcx, rbp
0x18000ad8f  call    ?_SetCapacity@?$vector@U?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@Kerb3961@@V?$allocator@U?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@Kerb3961@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)>,utl::allocator<Kerb3961::ReturnType<Kerb3961::OwnedBinary,&Kerb3961::SingleGetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary const &),&Kerb3961::SingleSetter<Kerb3961::OwnedBinary,16>(Kerb3961::OwnedBinary &)>>>::_SetCapacity(unsigned __int64)
0x18000ad94  test    al, al
0x18000ad96  jnz     short loc_18000ADB9
0x18000ad98  lea     rcx, aMComponentsEmp; "m_components.emplace_back(utl::move(buf"...
0x18000ad9f  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000ada4  mov     dword ptr [rsi], 0C0000017h
0x18000adaa  test    rdi, rdi
0x18000adad  jz      short loc_18000ADD7
0x18000adaf  mov     rcx, rdi
0x18000adb2  call    Kerb3961Free
0x18000adb7  jmp     short loc_18000ADD7
0x18000adb9  mov     rcx, [rbp+8]
0x18000adbd  mov     rax, [rsp+88h+var_68]
0x18000adc2  mov     [rcx+10h], ebx
0x18000adc5  mov     [rcx], rax
0x18000adc8  mov     [rcx+8], rdi
0x18000adcc  add     qword ptr [rbp+8], 18h
0x18000add1  mov     dword ptr [rsi], 0
0x18000add7  mov     rax, rsi
0x18000adda  add     rsp, 48h
0x18000adde  pop     r15
0x18000ade0  pop     r14
0x18000ade2  pop     r13
0x18000ade4  pop     r12
0x18000ade6  pop     rdi
0x18000ade7  pop     rsi
0x18000ade8  pop     rbp
0x18000ade9  pop     rbx
0x18000adea  retn
```
