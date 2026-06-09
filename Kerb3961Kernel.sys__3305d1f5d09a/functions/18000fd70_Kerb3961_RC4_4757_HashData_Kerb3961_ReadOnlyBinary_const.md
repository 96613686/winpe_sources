# Kerb3961::RC4_4757::HashData(Kerb3961::ReadOnlyBinary const &)

- ea: `0x18000fd70`
- end: `0x18000fe3d`
- name: `?HashData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@@Z`
- size: `205`
- prototype: ``
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x18000d580`
- `0x18000d900`
- `0x18000e310`
- `0x18000e6b0`
- `0x18000eec0`
- `0x18000fb70`

## callees

- `0x180001818`
- `0x18000fd70`
- `0x180011760`
- `0x1800118cc`
- `0x180011b40`

## import_xrefs

- `cng!BCryptHash` at `0x18000fde7`
- `cng!BCryptHash` at `0x18000fde7`

## pseudocode

```c
__int64 __fastcall Kerb3961::RC4_4757::HashData(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rsi
  int v7; // eax
  int v8; // r8d
  int v9; // ebp
  __int64 v11; // [rsp+80h] [rbp+18h] BYREF

  if ( *(_QWORD *)a3 <= 0xFFFFFFFF )
  {
    utl::make_unique<unsigned char [0],0>(&v11, (const struct std::nothrow_t *)0x10);
    v6 = v11;
    v7 = BCryptHash(*(_QWORD *)(a1 + 88), 0, 0, *(_QWORD *)(a3 + 8), *(_DWORD *)a3, v11, 16);
    v9 = v7;
    if ( v7 >= 0 )
    {
      *(_QWORD *)a2 = 16;
      *(_QWORD *)(a2 + 8) = v6;
      *(_DWORD *)(a2 + 16) = 0;
    }
    else
    {
      Kerb3961::Logging::Verify::StatusFailed(
        (Kerb3961::Logging::Verify *)"BCryptHash(m_hashHandle, nullptr, 0, const_cast<uint8_t*>(data.buffer), static_cast"
                                     "<uint32_t>(data.length), result.get(), HASH_SIZE)",
        (const char *)(unsigned int)v7,
        v8);
      *(_QWORD *)a2 = 0;
      *(_QWORD *)(a2 + 8) = 0;
      *(_DWORD *)(a2 + 16) = v9;
      if ( v6 )
        Kerb3961Free(v6);
    }
  }
  else
  {
    Kerb3961::Logging::Verify::ConditionFailed(
      (Kerb3961::Logging::Verify *)"static_cast<size_t>(data.length) <= static_cast<size_t>(utl::numeric_limits<uint32_t>::max())",
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
0x18000fd70  push    rbx
0x18000fd72  push    rbp
0x18000fd73  push    rsi
0x18000fd74  push    rdi
0x18000fd75  sub     rsp, 48h
0x18000fd79  mov     eax, 0FFFFFFFFh
0x18000fd7e  mov     rdi, r8
0x18000fd81  mov     rbx, rdx
0x18000fd84  mov     rbp, rcx
0x18000fd87  cmp     [r8], rax
0x18000fd8a  jbe     short loc_18000FDAD
0x18000fd8c  lea     rcx, aStaticCastSize_3; "static_cast<size_t>(data.length) <= sta"...
0x18000fd93  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x18000fd98  xor     edi, edi
0x18000fd9a  mov     [rbx], rdi
0x18000fd9d  mov     [rbx+8], rdi
0x18000fda1  mov     dword ptr [rbx+10h], 0C0000095h
0x18000fda8  jmp     loc_18000FE30
0x18000fdad  mov     edx, 10h
0x18000fdb2  lea     rcx, [rsp+68h+arg_10]
0x18000fdba  call    ??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z; utl::make_unique<uchar [0],0>(unsigned __int64)
0x18000fdbf  mov     eax, [rdi]
0x18000fdc1  xor     r8d, r8d
0x18000fdc4  mov     rsi, [rsp+68h+arg_10]
0x18000fdcc  xor     edx, edx
0x18000fdce  mov     r9, [rdi+8]
0x18000fdd2  mov     rcx, [rbp+58h]
0x18000fdd6  mov     [rsp+68h+var_38], 10h
0x18000fdde  mov     [rsp+68h+var_40], rsi
0x18000fde3  mov     [rsp+68h+var_48], eax
0x18000fde7  call    cs:__imp_BCryptHash
0x18000fdee  nop     dword ptr [rax+rax+00h]
0x18000fdf3  xor     edi, edi
0x18000fdf5  mov     ebp, eax
0x18000fdf7  test    eax, eax
0x18000fdf9  jns     short loc_18000FE22
0x18000fdfb  mov     edx, eax; char *
0x18000fdfd  lea     rcx, aBcrypthashMHas; "BCryptHash(m_hashHandle, nullptr, 0, co"...
0x18000fe04  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18000fe09  mov     [rbx], rdi
0x18000fe0c  mov     [rbx+8], rdi
0x18000fe10  mov     [rbx+10h], ebp
0x18000fe13  test    rsi, rsi
0x18000fe16  jz      short loc_18000FE30
0x18000fe18  mov     rcx, rsi
0x18000fe1b  call    Kerb3961Free
0x18000fe20  jmp     short loc_18000FE30
0x18000fe22  mov     qword ptr [rbx], 10h
0x18000fe29  mov     [rbx+8], rsi
0x18000fe2d  mov     [rbx+10h], edi
0x18000fe30  mov     rax, rbx
0x18000fe33  add     rsp, 48h
0x18000fe37  pop     rdi
0x18000fe38  pop     rsi
0x18000fe39  pop     rbp
0x18000fe3a  pop     rbx
0x18000fe3b  retn
```
