# Kerb3961::RC4_4757::DeriveSpecificKey(Kerb3961::ReadOnlyBinary const &,Kerb3961::KeyUsage,Kerb3961::SpecificKeyScenario)

- ea: `0x180007500`
- end: `0x180007645`
- name: `?DeriveSpecificKey@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@USpecificKeyReturn@Kerb3961@@$1??$SingleGetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@W4KeyUsage@2@W4SpecificKeyScenario@2@@Z`
- size: `325`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x180001d64`
- `0x1800029bc`
- `0x180002c64`
- `0x180002fc0`
- `0x18000712c`
- `0x180007500`

## pseudocode

```c
__int64 __fastcall Kerb3961::RC4_4757::DeriveSpecificKey(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  char *v8; // rax
  const char *v9; // rdx
  void *v10; // rdi
  __int64 v11; // rax
  int v12; // r8d
  void *v13; // rcx
  __int64 v14; // rsi
  __int64 v15; // rax
  int v16; // esi
  void *v17; // rcx
  _BYTE v19[8]; // [rsp+20h] [rbp-48h] BYREF
  void *v20; // [rsp+28h] [rbp-40h]

  v8 = (char *)operator new(0x20u, (const struct std::nothrow_t *)a2);
  v10 = v8;
  if ( v8 )
  {
    *(_QWORD *)(v8 + 20) = 0;
    *((_DWORD *)v8 + 7) = 0;
    *(_QWORD *)v8 = 0;
    *((_QWORD *)v8 + 1) = 0;
    *((_DWORD *)v8 + 4) = -1073741823;
    v11 = Kerb3961::CopyBuffer((__int64)v19, a3);
    v13 = (void *)*((_QWORD *)v10 + 1);
    v14 = v11;
    if ( v13 )
      operator delete(v13, 0);
    *(_QWORD *)v10 = *(_QWORD *)v14;
    v15 = *(_QWORD *)(v14 + 8);
    *(_QWORD *)v14 = 0;
    *((_QWORD *)v10 + 1) = v15;
    LODWORD(v15) = *(_DWORD *)(v14 + 16);
    *(_QWORD *)(v14 + 8) = 0;
    *((_DWORD *)v10 + 4) = v15;
    *(_DWORD *)(v14 + 16) = -1073741823;
    if ( v20 )
      operator delete(v20, 0);
    v16 = *((_DWORD *)v10 + 4);
    if ( v16 >= 0 )
    {
      *((_QWORD *)v10 + 3) = a4;
      if ( a4 == 3 )
        *((_QWORD *)v10 + 3) = 8;
      *(_QWORD *)a2 = a1;
      *(_QWORD *)(a2 + 8) = v10;
      *(_DWORD *)(a2 + 16) = 0;
    }
    else
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"specificKey->key",
        (const char *)(unsigned int)v16,
        v12);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v16;
      v17 = (void *)*((_QWORD *)v10 + 1);
      if ( v17 )
        operator delete(v17, 0);
      operator delete(v10, (const struct std::nothrow_t *)0x20);
    }
  }
  else
  {
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"specificKey", v9);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741801;
  }
  return a2;
}

```

## disassembly

```asm
0x180007500  push    rbx
0x180007502  push    rbp
0x180007503  push    rsi
0x180007504  push    rdi
0x180007505  push    r14
0x180007507  sub     rsp, 40h
0x18000750b  mov     r14, rcx
0x18000750e  mov     rbp, r9
0x180007511  mov     ecx, 20h ; ' '; unsigned __int64
0x180007516  mov     rsi, r8
0x180007519  mov     rbx, rdx
0x18000751c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180007521  mov     rdi, rax
0x180007524  test    rax, rax
0x180007527  jz      loc_180007615
0x18000752d  mov     qword ptr [rax+14h], 0
0x180007535  lea     rcx, [rsp+68h+var_48]
0x18000753a  mov     dword ptr [rax+1Ch], 0
0x180007541  mov     rdx, rsi
0x180007544  mov     qword ptr [rax], 0
0x18000754b  mov     qword ptr [rax+8], 0
0x180007553  mov     dword ptr [rax+10h], 0C0000001h
0x18000755a  call    ?CopyBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@@Z; Kerb3961::CopyBuffer(Kerb3961::ReadOnlyBinary const &)
0x18000755f  mov     rcx, [rdi+8]; void *
0x180007563  mov     rsi, rax
0x180007566  test    rcx, rcx
0x180007569  jz      short loc_180007572
0x18000756b  xor     edx, edx; struct std::nothrow_t *
0x18000756d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007572  mov     rcx, [rsi]
0x180007575  mov     [rdi], rcx
0x180007578  mov     rax, [rsi+8]
0x18000757c  mov     qword ptr [rsi], 0
0x180007583  mov     [rdi+8], rax
0x180007587  mov     eax, [rsi+10h]
0x18000758a  mov     qword ptr [rsi+8], 0
0x180007592  mov     [rdi+10h], eax
0x180007595  mov     dword ptr [rsi+10h], 0C0000001h
0x18000759c  mov     rcx, [rsp+68h+var_40]; void *
0x1800075a1  test    rcx, rcx
0x1800075a4  jz      short loc_1800075AD
0x1800075a6  xor     edx, edx; struct std::nothrow_t *
0x1800075a8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800075ad  mov     esi, [rdi+10h]
0x1800075b0  test    esi, esi
0x1800075b2  jns     short loc_1800075F3
0x1800075b4  mov     edx, esi; char *
0x1800075b6  lea     rcx, aSpecifickeyKey; "specificKey->key"
0x1800075bd  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800075c2  mov     qword ptr [rbx], 0
0x1800075c9  mov     qword ptr [rbx+8], 0
0x1800075d1  mov     [rbx+10h], esi
0x1800075d4  mov     rcx, [rdi+8]; void *
0x1800075d8  test    rcx, rcx
0x1800075db  jz      short loc_1800075E4
0x1800075dd  xor     edx, edx; struct std::nothrow_t *
0x1800075df  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800075e4  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x1800075e9  mov     rcx, rdi; void *
0x1800075ec  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800075f1  jmp     short loc_180007637
0x1800075f3  mov     [rdi+18h], rbp
0x1800075f7  cmp     rbp, 3
0x1800075fb  jnz     short loc_180007605
0x1800075fd  mov     qword ptr [rdi+18h], 8
0x180007605  mov     [rbx], r14
0x180007608  mov     [rbx+8], rdi
0x18000760c  mov     dword ptr [rbx+10h], 0
0x180007613  jmp     short loc_180007637
0x180007615  lea     rcx, aSpecifickey; "specificKey"
0x18000761c  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180007621  mov     qword ptr [rbx], 0
0x180007628  mov     qword ptr [rbx+8], 0
0x180007630  mov     dword ptr [rbx+10h], 0C0000017h
0x180007637  mov     rax, rbx
0x18000763a  add     rsp, 40h
0x18000763e  pop     r14
0x180007640  pop     rdi
0x180007641  pop     rsi
0x180007642  pop     rbp
0x180007643  pop     rbx
0x180007644  retn
```
