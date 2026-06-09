# Kerb3961::RC4_4757::StringToKey(Kerb3961::ReadOnlyString const &,Kerb3961::ReadOnlyString const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x180009c50`
- end: `0x180009cd4`
- name: `?StringToKey@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyString@2@0AEBUReadOnlyBinary@2@@Z`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002c64`
- `0x180009c50`
- `0x18000f754`

## pseudocode

```c
__int64 __fastcall Kerb3961::RC4_4757::StringToKey(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 v3; // rax
  _QWORD v6[2]; // [rsp+30h] [rbp-28h] BYREF
  _QWORD v7[3]; // [rsp+40h] [rbp-18h] BYREF

  v3 = *a3;
  if ( (unsigned __int64)*a3 <= 0x7FFFFFFF )
  {
    v7[0] = 0;
    v6[0] = 2 * v3;
    v6[1] = a3[1];
    v7[1] = 0;
    Kerb3961::GetHashCommon(a2, (const char *)0x11, v7, (__int64)v6, 0x10u);
  }
  else
  {
    Kerb3961::Logging::Verify::ConditionFailed(
      (Kerb3961::Logging::Verify *)"static_cast<size_t>(data.length) <= static_cast<size_t>(utl::numeric_limits<uint32_t>"
                                   "::max() / sizeof(*data.buffer))",
      (const char *)a2);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = -1073741675;
  }
  return a2;
}

```

## disassembly

```asm
0x180009c50  push    rbx
0x180009c52  sub     rsp, 50h
0x180009c56  mov     rax, [r8]
0x180009c59  mov     rbx, rdx
0x180009c5c  cmp     rax, 7FFFFFFFh
0x180009c62  jbe     short loc_180009C88
0x180009c64  lea     rcx, aStaticCastSize; "static_cast<size_t>(data.length) <= sta"...
0x180009c6b  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180009c70  mov     qword ptr [rbx], 0
0x180009c77  mov     qword ptr [rbx+8], 0
0x180009c7f  mov     dword ptr [rbx+10h], 0C0000095h
0x180009c86  jmp     short loc_180009CCB
0x180009c88  add     rax, rax
0x180009c8b  mov     [rsp+58h+var_18], 0
0x180009c94  mov     [rsp+58h+var_28], rax
0x180009c99  lea     r9, [rsp+58h+var_28]
0x180009c9e  mov     rax, [r8+8]
0x180009ca2  mov     edx, 11h
0x180009ca7  lea     r8, [rsp+58h+var_18]
0x180009cac  mov     [rsp+58h+var_20], rax
0x180009cb1  mov     rcx, rbx
0x180009cb4  mov     [rsp+58h+var_10], 0
0x180009cbd  mov     [rsp+58h+var_38], 10h
0x180009cc6  call    ?GetHashCommon@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@PEAXAEBUReadOnlyBinary@1@1_K@Z; Kerb3961::GetHashCommon(void *,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,unsigned __int64)
0x180009ccb  mov     rax, rbx
0x180009cce  add     rsp, 50h
0x180009cd2  pop     rbx
0x180009cd3  retn
```
