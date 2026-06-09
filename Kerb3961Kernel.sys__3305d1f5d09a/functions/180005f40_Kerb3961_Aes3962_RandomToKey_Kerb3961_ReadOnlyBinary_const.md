# Kerb3961::Aes3962::RandomToKey(Kerb3961::ReadOnlyBinary const &)

- ea: `0x180005f40`
- end: `0x180005f9b`
- name: `?RandomToKey@Aes3962@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@@Z`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180003a54`
- `0x180005f40`
- `0x180011760`

## pseudocode

```c
__int64 __fastcall Kerb3961::Aes3962::RandomToKey(__int64 a1, __int64 a2, _QWORD *a3)
{
  _QWORD v5[3]; // [rsp+20h] [rbp-18h] BYREF

  if ( *a3 >= *(_QWORD *)(a1 + 104) )
  {
    v5[0] = *(_QWORD *)(a1 + 104);
    v5[1] = a3[1];
    Kerb3961::CopyBuffer(a2, (__int64)v5);
  }
  else
  {
    Kerb3961::Logging::Verify::ConditionFailed(
      (Kerb3961::Logging::Verify *)"randomSeed.length >= m_keySize",
      (const char *)a2);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741789;
  }
  return a2;
}

```

## disassembly

```asm
0x180005f40  push    rbx
0x180005f42  sub     rsp, 30h
0x180005f46  mov     rax, [rcx+68h]
0x180005f4a  mov     rbx, rdx
0x180005f4d  cmp     [r8], rax
0x180005f50  jnb     short loc_180005F76
0x180005f52  lea     rcx, aRandomseedLeng_0; "randomSeed.length >= m_keySize"
0x180005f59  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180005f5e  mov     qword ptr [rbx], 0
0x180005f65  mov     qword ptr [rbx+8], 0
0x180005f6d  mov     dword ptr [rbx+10h], 0C0000023h
0x180005f74  jmp     short loc_180005F91
0x180005f76  mov     [rsp+38h+var_18], rax
0x180005f7b  lea     rdx, [rsp+38h+var_18]
0x180005f80  mov     rax, [r8+8]
0x180005f84  mov     rcx, rbx
0x180005f87  mov     [rsp+38h+var_10], rax
0x180005f8c  call    ?CopyBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@AEBUReadOnlyBinary@1@@Z; Kerb3961::CopyBuffer(Kerb3961::ReadOnlyBinary const &)
0x180005f91  mov     rax, rbx
0x180005f94  add     rsp, 30h
0x180005f98  pop     rbx
0x180005f99  retn
```
