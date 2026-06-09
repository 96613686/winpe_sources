# Kerb3961::Aes8009::GetMic(Kerb3961::ReturnType<Kerb3961::SpecificKeyReturn,&Kerb3961::SingleGetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn const &),&Kerb3961::SingleSetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn &)> &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x180014270`
- end: `0x180014330`
- name: `?GetMic@Aes8009@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@USpecificKeyReturn@Kerb3961@@$1??$SingleGetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@@Z`
- size: `192`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001d64`
- `0x180002c64`
- `0x180002fc0`
- `0x18000f908`
- `0x180014270`

## pseudocode

```c
__int64 __fastcall Kerb3961::Aes8009::GetMic(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  _QWORD *v4; // r8
  int v7; // r8d
  int v8; // edi
  void *v9; // rcx
  _BYTE v11[8]; // [rsp+30h] [rbp-28h] BYREF
  void *v12; // [rsp+38h] [rbp-20h]
  char *v13; // [rsp+40h] [rbp-18h]

  v4 = *(_QWORD **)(a3 + 8);
  if ( *v4 )
  {
    Kerb3961::GetHmac((__int64)v11, *(const char **)(a1 + 144), v4, a4, *(unsigned int *)(a1 + 152));
    v8 = (int)v13;
    if ( (int)v13 >= 0 )
    {
      *(_QWORD *)a2 = *(_QWORD *)(a1 + 80);
      *(_QWORD *)(a2 + 8) = v12;
      *(_DWORD *)(a2 + 16) = v8;
    }
    else
    {
      Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"hmac", (const char *)(unsigned int)v13, v7);
      v9 = v12;
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v8;
      if ( v9 )
        operator delete(v9, 0);
    }
  }
  else
  {
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"key->Kc.length > 0", (const char *)a2);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741811;
  }
  return a2;
}

```

## disassembly

```asm
0x180014270  mov     [rsp+arg_0], rbx
0x180014275  mov     [rsp+arg_8], rsi
0x18001427a  push    rdi
0x18001427b  sub     rsp, 50h
0x18001427f  mov     r8, [r8+8]
0x180014283  mov     rbx, rdx
0x180014286  mov     rsi, rcx
0x180014289  cmp     qword ptr [r8], 0
0x18001428d  ja      short loc_1800142B3
0x18001428f  lea     rcx, aKeyKcLength0; "key->Kc.length > 0"
0x180014296  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18001429b  mov     qword ptr [rbx], 0
0x1800142a2  mov     qword ptr [rbx+8], 0
0x1800142aa  mov     dword ptr [rbx+10h], 0C000000Dh
0x1800142b1  jmp     short loc_18001431D
0x1800142b3  mov     eax, [rcx+98h]
0x1800142b9  mov     rdx, [rcx+90h]
0x1800142c0  lea     rcx, [rsp+58h+var_28]
0x1800142c5  mov     [rsp+58h+var_38], rax
0x1800142ca  call    ?GetHmac@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@PEAXAEBUReadOnlyBinary@1@1_K@Z; Kerb3961::GetHmac(void *,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,unsigned __int64)
0x1800142cf  mov     edi, dword ptr [rsp+58h+var_18]
0x1800142d3  test    edi, edi
0x1800142d5  jns     short loc_18001430A
0x1800142d7  mov     edx, edi; char *
0x1800142d9  lea     rcx, aHmac; "hmac"
0x1800142e0  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x1800142e5  mov     rcx, [rsp+58h+var_20]; void *
0x1800142ea  mov     qword ptr [rbx], 0
0x1800142f1  mov     qword ptr [rbx+8], 0
0x1800142f9  mov     [rbx+10h], edi
0x1800142fc  test    rcx, rcx
0x1800142ff  jz      short loc_18001431D
0x180014301  xor     edx, edx; struct std::nothrow_t *
0x180014303  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180014308  jmp     short loc_18001431D
0x18001430a  mov     rax, [rsi+50h]
0x18001430e  mov     [rbx], rax
0x180014311  mov     rax, [rsp+58h+var_20]
0x180014316  mov     [rbx+8], rax
0x18001431a  mov     [rbx+10h], edi
0x18001431d  mov     rsi, [rsp+58h+arg_8]
0x180014322  mov     rax, rbx
0x180014325  mov     rbx, [rsp+58h+arg_0]
0x18001432a  add     rsp, 50h
0x18001432e  pop     rdi
0x18001432f  retn
```
