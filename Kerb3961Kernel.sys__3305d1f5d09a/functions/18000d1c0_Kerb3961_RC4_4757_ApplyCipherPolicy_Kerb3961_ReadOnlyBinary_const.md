# Kerb3961::RC4_4757::ApplyCipherPolicy(Kerb3961::ReadOnlyBinary const &)

- ea: `0x18000d1c0`
- end: `0x18000d1ff`
- name: `?ApplyCipherPolicy@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@@Z`
- size: `63`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x18000d1c0`
- `0x180011760`

## pseudocode

```c
_DWORD *__fastcall Kerb3961::RC4_4757::ApplyCipherPolicy(char *a1, _DWORD *a2, __int64 a3)
{
  if ( *(_QWORD *)a3 == 4 )
  {
    *((_DWORD *)a1 + 26) = **(_DWORD **)(a3 + 8);
    *a2 = 0;
  }
  else
  {
    Kerb3961::Logging::Verify::ConditionFailed(
      (Kerb3961::Logging::Verify *)"marshaledPolicy.length == sizeof(m_policy)",
      a1);
    *a2 = -1073741811;
  }
  return a2;
}

```

## disassembly

```asm
0x18000d1c0  push    rbx
0x18000d1c2  sub     rsp, 20h
0x18000d1c6  cmp     qword ptr [r8], 4
0x18000d1ca  mov     rbx, rdx
0x18000d1cd  mov     rdx, rcx; char *
0x18000d1d0  jz      short loc_18000D1E6
0x18000d1d2  lea     rcx, aMarshaledpolic_0; "marshaledPolicy.length == sizeof(m_poli"...
0x18000d1d9  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000d1de  mov     dword ptr [rbx], 0C000000Dh
0x18000d1e4  jmp     short loc_18000D1F5
0x18000d1e6  mov     rax, [r8+8]
0x18000d1ea  mov     ecx, [rax]
0x18000d1ec  mov     [rdx+68h], ecx
0x18000d1ef  mov     dword ptr [rbx], 0
0x18000d1f5  mov     rax, rbx
0x18000d1f8  add     rsp, 20h
0x18000d1fc  pop     rbx
0x18000d1fd  retn
```
