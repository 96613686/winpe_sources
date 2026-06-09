# Kerb3961::GetHmac(void *,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,unsigned __int64)

- ea: `0x18000a6c0`
- end: `0x18000a70c`
- name: `?GetHmac@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@PEAXAEBUReadOnlyBinary@1@1_K@Z`
- size: `76`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800056f0`
- `0x180007ad0`
- `0x180007e9c`
- `0x1800083f0`
- `0x180008b40`
- `0x180010260`

## callees

- `0x18000a500`
- `0x18000a6c0`
- `0x180011760`

## pseudocode

```c
__int64 __fastcall Kerb3961::GetHmac(__int64 a1, char *a2, _QWORD *a3, __int64 a4, const char *a5)
{
  if ( *a3 )
  {
    Kerb3961::GetHashCommon(a1, a2, a3, a4, a5);
  }
  else
  {
    Kerb3961::Logging::Verify::ConditionFailed((Kerb3961::Logging::Verify *)"key.length > 0", a2);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_DWORD *)(a1 + 16) = -1073741811;
  }
  return a1;
}

```

## disassembly

```asm
0x18000a6c0  push    rbx
0x18000a6c2  sub     rsp, 30h
0x18000a6c6  cmp     qword ptr [r8], 0
0x18000a6ca  mov     rbx, rcx
0x18000a6cd  ja      short loc_18000A6F3
0x18000a6cf  lea     rcx, aKeyLength0; "key.length > 0"
0x18000a6d6  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000a6db  mov     qword ptr [rbx], 0
0x18000a6e2  mov     qword ptr [rbx+8], 0
0x18000a6ea  mov     dword ptr [rbx+10h], 0C000000Dh
0x18000a6f1  jmp     short loc_18000A702
0x18000a6f3  mov     rax, [rsp+38h+arg_20]
0x18000a6f8  mov     [rsp+38h+var_18], rax
0x18000a6fd  call    ?GetHashCommon@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@PEAXAEBUReadOnlyBinary@1@1_K@Z; Kerb3961::GetHashCommon(void *,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,unsigned __int64)
0x18000a702  mov     rax, rbx
0x18000a705  add     rsp, 30h
0x18000a709  pop     rbx
0x18000a70a  retn
```
