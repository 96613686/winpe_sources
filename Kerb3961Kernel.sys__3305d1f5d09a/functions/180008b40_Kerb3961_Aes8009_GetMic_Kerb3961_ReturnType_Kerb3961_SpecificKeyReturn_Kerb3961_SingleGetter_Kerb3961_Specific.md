# Kerb3961::Aes8009::GetMic(Kerb3961::ReturnType<Kerb3961::SpecificKeyReturn,&Kerb3961::SingleGetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn const &),&Kerb3961::SingleSetter<Kerb3961::SpecificKeyReturn,16>(Kerb3961::SpecificKeyReturn &)> &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x180008b40`
- end: `0x180008bff`
- name: `?GetMic@Aes8009@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEAU?$ReturnType@USpecificKeyReturn@Kerb3961@@$1??$SingleGetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@USpecificKeyReturn@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@@Z`
- size: `191`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180008b40`
- `0x18000a6c0`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`

## pseudocode

```c
__int64 __fastcall Kerb3961::Aes8009::GetMic(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  _QWORD *v4; // r8
  int v7; // r8d
  int v8; // edi
  __int64 v9; // rcx
  _BYTE v11[8]; // [rsp+30h] [rbp-28h] BYREF
  __int64 v12; // [rsp+38h] [rbp-20h]
  char *v13; // [rsp+40h] [rbp-18h]

  v4 = *(_QWORD **)(a3 + 8);
  if ( *v4 )
  {
    Kerb3961::GetHmac((__int64)v11, *(char **)(a1 + 144), v4, a4, (const char *)*(unsigned int *)(a1 + 152));
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
        Kerb3961Free(v9);
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
0x180008b40  mov     [rsp+arg_0], rbx
0x180008b45  mov     [rsp+arg_8], rsi
0x180008b4a  push    rdi
0x180008b4b  sub     rsp, 50h
0x180008b4f  mov     r8, [r8+8]
0x180008b53  mov     rbx, rdx
0x180008b56  mov     rsi, rcx
0x180008b59  cmp     qword ptr [r8], 0
0x180008b5d  ja      short loc_180008B83
0x180008b5f  lea     rcx, aKeyKcLength0; "key->Kc.length > 0"
0x180008b66  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180008b6b  mov     qword ptr [rbx], 0
0x180008b72  mov     qword ptr [rbx+8], 0
0x180008b7a  mov     dword ptr [rbx+10h], 0C000000Dh
0x180008b81  jmp     short loc_180008BEB
0x180008b83  mov     eax, [rcx+98h]
0x180008b89  mov     rdx, [rcx+90h]
0x180008b90  lea     rcx, [rsp+58h+var_28]
0x180008b95  mov     [rsp+58h+var_38], rax
0x180008b9a  call    ?GetHmac@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@PEAXAEBUReadOnlyBinary@1@1_K@Z; Kerb3961::GetHmac(void *,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,unsigned __int64)
0x180008b9f  mov     edi, dword ptr [rsp+58h+var_18]
0x180008ba3  test    edi, edi
0x180008ba5  jns     short loc_180008BD8
0x180008ba7  mov     edx, edi; char *
0x180008ba9  lea     rcx, aHmac; "hmac"
0x180008bb0  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180008bb5  mov     rcx, [rsp+58h+var_20]
0x180008bba  mov     qword ptr [rbx], 0
0x180008bc1  mov     qword ptr [rbx+8], 0
0x180008bc9  mov     [rbx+10h], edi
0x180008bcc  test    rcx, rcx
0x180008bcf  jz      short loc_180008BEB
0x180008bd1  call    Kerb3961Free
0x180008bd6  jmp     short loc_180008BEB
0x180008bd8  mov     rax, [rsi+50h]
0x180008bdc  mov     [rbx], rax
0x180008bdf  mov     rax, [rsp+58h+var_20]
0x180008be4  mov     [rbx+8], rax
0x180008be8  mov     [rbx+10h], edi
0x180008beb  mov     rsi, [rsp+58h+arg_8]
0x180008bf0  mov     rax, rbx
0x180008bf3  mov     rbx, [rsp+58h+arg_0]
0x180008bf8  add     rsp, 50h
0x180008bfc  pop     rdi
0x180008bfd  retn
```
