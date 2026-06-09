# Kerb3961::RC4_4757::HashData(Kerb3961::ReadOnlyBinary const &)

- ea: `0x180008500`
- end: `0x1800085c3`
- name: `?HashData@RC4_4757@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@@Z`
- size: `195`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800050e0`
- `0x180005480`
- `0x180005ed0`
- `0x180006270`
- `0x180006ac0`
- `0x1800082f0`

## callees

- `0x180001d64`
- `0x180002c64`
- `0x180002fc0`
- `0x1800048b0`
- `0x180008500`

## import_xrefs

- `bcrypt!BCryptHash` at `0x180008574`
- `bcrypt!BCryptHash` at `0x180008574`

## pseudocode

```c
__int64 __fastcall Kerb3961::RC4_4757::HashData(__int64 a1, __int64 a2, __int64 a3)
{
  void *v6; // rsi
  int v7; // eax
  int v8; // r8d
  int v9; // ebp
  const struct std::nothrow_t *v10; // rdx
  void *v12; // [rsp+80h] [rbp+18h] BYREF

  if ( *(_QWORD *)a3 <= 0xFFFFFFFF )
  {
    utl::make_unique<unsigned char [0],0>(&v12, 0x10u);
    v6 = v12;
    v7 = BCryptHash(*(_QWORD *)(a1 + 88), 0, 0, *(_QWORD *)(a3 + 8), *(_DWORD *)a3, v12, 16);
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
        operator delete(v6, v10);
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
0x180008500  push    rbx
0x180008502  push    rbp
0x180008503  push    rsi
0x180008504  push    rdi
0x180008505  sub     rsp, 48h
0x180008509  mov     eax, 0FFFFFFFFh
0x18000850e  mov     rdi, r8
0x180008511  mov     rbx, rdx
0x180008514  mov     rbp, rcx
0x180008517  cmp     [r8], rax
0x18000851a  jbe     short loc_18000853A
0x18000851c  lea     rcx, aStaticCastSize_6; "static_cast<size_t>(data.length) <= sta"...
0x180008523  call    ?ConditionFailed@Verify@Logging@Kerb3961@@YAXPEBD@Z; Kerb3961::Logging::Verify::ConditionFailed(char const *)
0x180008528  xor     edi, edi
0x18000852a  mov     [rbx], rdi
0x18000852d  mov     [rbx+8], rdi
0x180008531  mov     dword ptr [rbx+10h], 0C0000095h
0x180008538  jmp     short loc_1800085B7
0x18000853a  mov     edx, 10h
0x18000853f  lea     rcx, [rsp+68h+arg_10]
0x180008547  call    ??$make_unique@$$BY0A@E$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@utl@@@0@_K@Z; utl::make_unique<uchar [0],0>(unsigned __int64)
0x18000854c  mov     eax, [rdi]
0x18000854e  xor     r8d, r8d
0x180008551  mov     rsi, [rsp+68h+arg_10]
0x180008559  xor     edx, edx
0x18000855b  mov     r9, [rdi+8]
0x18000855f  mov     rcx, [rbp+58h]
0x180008563  mov     [rsp+68h+var_38], 10h
0x18000856b  mov     [rsp+68h+var_40], rsi
0x180008570  mov     [rsp+68h+var_48], eax
0x180008574  call    cs:__imp_BCryptHash
0x18000857a  xor     edi, edi
0x18000857c  mov     ebp, eax
0x18000857e  test    eax, eax
0x180008580  jns     short loc_1800085A9
0x180008582  mov     edx, eax; char *
0x180008584  lea     rcx, aBcrypthashMHas; "BCryptHash(m_hashHandle, nullptr, 0, co"...
0x18000858b  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x180008590  mov     [rbx], rdi
0x180008593  mov     [rbx+8], rdi
0x180008597  mov     [rbx+10h], ebp
0x18000859a  test    rsi, rsi
0x18000859d  jz      short loc_1800085B7
0x18000859f  mov     rcx, rsi; void *
0x1800085a2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800085a7  jmp     short loc_1800085B7
0x1800085a9  mov     qword ptr [rbx], 10h
0x1800085b0  mov     [rbx+8], rsi
0x1800085b4  mov     [rbx+10h], edi
0x1800085b7  mov     rax, rbx
0x1800085ba  add     rsp, 48h
0x1800085be  pop     rdi
0x1800085bf  pop     rsi
0x1800085c0  pop     rbp
0x1800085c1  pop     rbx
0x1800085c2  retn
```
