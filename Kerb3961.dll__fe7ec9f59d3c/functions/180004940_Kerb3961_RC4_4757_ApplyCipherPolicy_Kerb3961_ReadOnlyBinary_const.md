# Kerb3961::RC4_4757::ApplyCipherPolicy(Kerb3961::ReadOnlyBinary const &)

- ea: `0x180004940`
- end: `0x18000497e`
- name: `?ApplyCipherPolicy@RC4_4757@Kerb3961@@EEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@@Z`
- size: `62`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180002c64`
- `0x180004940`

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
0x180004940  push    rbx
0x180004942  sub     rsp, 20h
0x180004946  cmp     qword ptr [r8], 4
0x18000494a  mov     rbx, rdx
0x18000494d  mov     rdx, rcx; char *
0x180004950  jz      short loc_180004966
0x180004952  lea     rcx, aMarshaledpolic_0; "marshaledPolicy.length == sizeof(m_poli"...
0x180004959  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000495e  mov     dword ptr [rbx], 0C000000Dh
0x180004964  jmp     short loc_180004975
0x180004966  mov     rax, [r8+8]
0x18000496a  mov     ecx, [rax]
0x18000496c  mov     [rdx+68h], ecx
0x18000496f  mov     dword ptr [rbx], 0
0x180004975  mov     rax, rbx
0x180004978  add     rsp, 20h
0x18000497c  pop     rbx
0x18000497d  retn
```
