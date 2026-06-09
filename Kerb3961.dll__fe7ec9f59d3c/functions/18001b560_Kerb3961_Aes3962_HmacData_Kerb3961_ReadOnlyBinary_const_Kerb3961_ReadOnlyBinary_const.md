# Kerb3961::Aes3962::HmacData(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x18001b560`
- end: `0x18001b5e3`
- name: `?HmacData@Aes3962@Kerb3961@@EEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z`
- size: `131`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops`

## callees

- `0x180001d64`
- `0x180002fc0`
- `0x18000f908`
- `0x18001b560`

## pseudocode

```c
__int64 __fastcall Kerb3961::Aes3962::HmacData(__int64 a1, __int64 a2, _QWORD *a3, __int64 a4)
{
  int v5; // r8d
  int v6; // edi
  void *v7; // rcx
  _BYTE v9[8]; // [rsp+30h] [rbp-28h] BYREF
  void *v10; // [rsp+38h] [rbp-20h]
  char *v11; // [rsp+40h] [rbp-18h]

  Kerb3961::GetHmac((__int64)v9, *(const char **)(a1 + 184), a3, a4, 0x14u);
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
      operator delete(v7, 0);
  }
  return a2;
}

```

## disassembly

```asm
0x18001b560  mov     [rsp+arg_0], rbx
0x18001b565  push    rdi
0x18001b566  sub     rsp, 50h
0x18001b56a  mov     rbx, rdx
0x18001b56d  mov     [rsp+58h+var_38], 14h
0x18001b576  mov     rdx, [rcx+0B8h]
0x18001b57d  lea     rcx, [rsp+58h+var_28]
0x18001b582  call    ?GetHmac@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@PEAXAEBUReadOnlyBinary@1@1_K@Z; Kerb3961::GetHmac(void *,Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &,unsigned __int64)
0x18001b587  mov     edi, dword ptr [rsp+58h+var_18]
0x18001b58b  test    edi, edi
0x18001b58d  jns     short loc_18001B5C2
0x18001b58f  mov     edx, edi; char *
0x18001b591  lea     rcx, aResult; "result"
0x18001b598  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001b59d  mov     rcx, [rsp+58h+var_20]; void *
0x18001b5a2  mov     qword ptr [rbx], 0
0x18001b5a9  mov     qword ptr [rbx+8], 0
0x18001b5b1  mov     [rbx+10h], edi
0x18001b5b4  test    rcx, rcx
0x18001b5b7  jz      short loc_18001B5D5
0x18001b5b9  xor     edx, edx; struct std::nothrow_t *
0x18001b5bb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001b5c0  jmp     short loc_18001B5D5
0x18001b5c2  mov     rax, [rsp+58h+var_20]
0x18001b5c7  mov     [rbx+8], rax
0x18001b5cb  mov     [rbx+10h], edi
0x18001b5ce  mov     qword ptr [rbx], 0Ch
0x18001b5d5  mov     rax, rbx
0x18001b5d8  mov     rbx, [rsp+58h+arg_0]
0x18001b5dd  add     rsp, 50h
0x18001b5e1  pop     rdi
0x18001b5e2  retn
```
