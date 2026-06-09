# Kerb3961::Aes3962::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x1800056f0`
- end: `0x180005772`
- name: `?HmacData@Aes3962@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z`
- size: `130`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800056f0`
- `0x18000a6c0`
- `0x1800118cc`
- `0x180011b40`

## pseudocode

```c
__int64 __fastcall Kerb3961::Aes3962::HmacData(__int64 a1, __int64 a2, _QWORD *a3, __int64 a4)
{
  int v5; // r8d
  int v6; // edi
  __int64 v7; // rcx
  _BYTE v9[8]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v10; // [rsp+38h] [rbp-20h]
  char *v11; // [rsp+40h] [rbp-18h]

  Kerb3961::GetHmac((__int64)v9, *(char **)(a1 + 184), a3, a4, (const char *)0x14);
  v6 = (int)v11;
  if ( (int)v11 >= 0 )
  {
    *(_QWORD *)(a2 + 8) = v10;
    *(_DWORD *)(a2 + 16) = v6;
    *(_QWORD *)a2 = 12;
  }
  else
  {
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"result", (const char *)(unsigned int)v11, v5);
    v7 = v10;
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v6;
    if ( v7 )
      Kerb3961Free(v7);
  }
  return a2;
}

```

## disassembly

```asm
0x1800056f0  mov     [rsp+arg_0], rbx
0x1800056f5  push    rdi
0x1800056f6  sub     rsp, 50h
0x1800056fa  mov     rbx, rdx
0x1800056fd  mov     [rsp+58h+var_38], 14h
0x180005706  mov     rdx, [rcx+0B8h]
0x18000570d  lea     rcx, [rsp+58h+var_28]
0x180005712  call    ?GetHmac@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@PEAXAEBUReadOnlyBinary@1@1_K@Z; Kerb3961::GetHmac(void *,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,unsigned __int64)
0x180005717  mov     edi, dword ptr [rsp+58h+var_18]
0x18000571b  test    edi, edi
0x18000571d  jns     short loc_180005750
0x18000571f  mov     edx, edi; char *
0x180005721  lea     rcx, aResult; "result"
0x180005728  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000572d  mov     rcx, [rsp+58h+var_20]
0x180005732  mov     qword ptr [rbx], 0
0x180005739  mov     qword ptr [rbx+8], 0
0x180005741  mov     [rbx+10h], edi
0x180005744  test    rcx, rcx
0x180005747  jz      short loc_180005763
0x180005749  call    Kerb3961Free
0x18000574e  jmp     short loc_180005763
0x180005750  mov     rax, [rsp+58h+var_20]
0x180005755  mov     [rbx+8], rax
0x180005759  mov     [rbx+10h], edi
0x18000575c  mov     qword ptr [rbx], 0Ch
0x180005763  mov     rax, rbx
0x180005766  mov     rbx, [rsp+58h+arg_0]
0x18000576b  add     rsp, 50h
0x18000576f  pop     rdi
0x180005770  retn
```
