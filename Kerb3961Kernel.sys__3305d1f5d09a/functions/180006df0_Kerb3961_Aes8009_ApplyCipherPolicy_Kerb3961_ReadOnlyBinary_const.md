# Kerb3961::Aes8009::ApplyCipherPolicy(Kerb3961::ReadOnlyBinary const &)

- ea: `0x180006df0`
- end: `0x180006e32`
- name: `?ApplyCipherPolicy@Aes8009@Kerb3961@@EEAA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@@Z`
- size: `66`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180006df0`
- `0x180011760`

## pseudocode

```c
_DWORD *__fastcall Kerb3961::Aes8009::ApplyCipherPolicy(char *a1, _DWORD *a2, __int64 a3)
{
  if ( *(_QWORD *)a3 == 1 )
  {
    a1[164] = **(_BYTE **)(a3 + 8);
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
0x180006df0  push    rbx
0x180006df2  sub     rsp, 20h
0x180006df6  cmp     qword ptr [r8], 1
0x180006dfa  mov     rbx, rdx
0x180006dfd  mov     rdx, rcx; char *
0x180006e00  jz      short loc_180006E16
0x180006e02  lea     rcx, aMarshaledpolic_0; "marshaledPolicy.length == sizeof(m_poli"...
0x180006e09  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180006e0e  mov     dword ptr [rbx], 0C000000Dh
0x180006e14  jmp     short loc_180006E28
0x180006e16  mov     rax, [r8+8]
0x180006e1a  mov     cl, [rax]
0x180006e1c  mov     [rdx+0A4h], cl
0x180006e22  mov     dword ptr [rbx], 0
0x180006e28  mov     rax, rbx
0x180006e2b  add     rsp, 20h
0x180006e2f  pop     rbx
0x180006e30  retn
```
