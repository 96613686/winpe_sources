# Kerb3961::GetHmac(void *,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,unsigned __int64)

- ea: `0x18000f908`
- end: `0x18000f953`
- name: `?GetHmac@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@PEAXAEBUReadOnlyBinary@1@1_K@Z`
- size: `75`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009160`
- `0x1800126e0`
- `0x180012ab8`
- `0x1800130b0`
- `0x180014270`
- `0x18001b560`

## callees

- `0x180002c64`
- `0x18000f754`
- `0x18000f908`

## pseudocode

```c
__int64 __fastcall Kerb3961::GetHmac(__int64 a1, const char *a2, _QWORD *a3, __int64 a4, unsigned __int64 a5)
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
0x18000f908  push    rbx
0x18000f90a  sub     rsp, 30h
0x18000f90e  cmp     qword ptr [r8], 0
0x18000f912  mov     rbx, rcx
0x18000f915  ja      short loc_18000F93B
0x18000f917  lea     rcx, aKeyLength0; "key.length > 0"
0x18000f91e  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000f923  mov     qword ptr [rbx], 0
0x18000f92a  mov     qword ptr [rbx+8], 0
0x18000f932  mov     dword ptr [rbx+10h], 0C000000Dh
0x18000f939  jmp     short loc_18000F94A
0x18000f93b  mov     rax, [rsp+38h+arg_20]
0x18000f940  mov     [rsp+38h+var_18], rax
0x18000f945  call    ?GetHashCommon@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@PEAXAEBUReadOnlyBinary@1@1_K@Z; Kerb3961::GetHashCommon(void *,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,unsigned __int64)
0x18000f94a  mov     rax, rbx
0x18000f94d  add     rsp, 30h
0x18000f951  pop     rbx
0x18000f952  retn
```
