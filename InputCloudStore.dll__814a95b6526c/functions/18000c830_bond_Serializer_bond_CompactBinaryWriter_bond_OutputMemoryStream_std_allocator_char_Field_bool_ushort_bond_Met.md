# bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>::Field<bool>(ushort,bond::Metadata const &,bool const &)

- ea: `0x18000c830`
- end: `0x18000c8b3`
- name: `??$Field@_N@?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@bond@@QEBA_NGAEBUMetadata@1@AEB_N@Z`
- size: `131`
- prototype: `char __fastcall(_QWORD *, unsigned __int16, __int64, _BYTE *)`
- caller_count: `14`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a018`
- `0x18000a2d0`
- `0x18000ce80`
- `0x18000d334`
- `0x18000d4b8`
- `0x18000e474`
- `0x18000e638`
- `0x18000e8d0`
- `0x18000ee88`
- `0x18000f02c`
- `0x18000f408`
- `0x18000f874`
- `0x18001bce4`
- `0x18001bdac`

## callees

- `0x18000c830`
- `0x18002271c`
- `0x180022850`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char __fastcall bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>::Field<bool>(
        _QWORD *a1,
        unsigned __int16 a2,
        __int64 a3,
        _BYTE *a4)
{
  _QWORD *v5; // rbx
  __int64 v6; // r9
  __int64 v7; // rdx

  if ( *(_DWORD *)(a3 + 80) || *a4 != (*(_QWORD *)(a3 + 88) != 0) )
  {
    v5 = (_QWORD *)*a1;
    bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>::WriteFieldBegin(*a1, 2, a2);
    v6 = *v5;
    v7 = *(unsigned int *)(*v5 + 28LL);
    if ( v7 + (unsigned __int64)*(unsigned int *)(*v5 + 32LL) + 1 > *(unsigned int *)(*v5 + 24LL) )
    {
      bond::OutputMemoryStream<std::allocator<char>>::Write(*v5, a4, 1);
    }
    else
    {
      *(_BYTE *)(v7 + *(_QWORD *)(v6 + 48)) = *a4;
      ++*(_DWORD *)(v6 + 28);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000c830  mov     [rsp+arg_0], rbx
0x18000c835  push    rdi
0x18000c836  sub     rsp, 20h
0x18000c83a  cmp     dword ptr [r8+50h], 0
0x18000c83f  mov     rdi, r9
0x18000c842  jnz     short loc_18000C858
0x18000c844  movzx   eax, byte ptr [r9]
0x18000c848  xor     r10d, r10d
0x18000c84b  cmp     [r8+58h], r10
0x18000c84f  setnz   r10b
0x18000c853  cmp     eax, r10d
0x18000c856  jz      short loc_18000C8A6
0x18000c858  mov     rbx, [rcx]
0x18000c85b  movzx   r8d, dx
0x18000c85f  mov     rcx, rbx
0x18000c862  mov     edx, 2
0x18000c867  call    ?WriteFieldBegin@?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@QEAAXW4BondDataType@3_bond_enumerators@2@G@Z; bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>::WriteFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType,ushort)
0x18000c86c  mov     r9, [rbx]
0x18000c86f  mov     ecx, [r9+20h]
0x18000c873  mov     edx, [r9+1Ch]
0x18000c877  inc     rcx
0x18000c87a  mov     eax, [r9+18h]
0x18000c87e  add     rcx, rdx
0x18000c881  cmp     rcx, rax
0x18000c884  ja      short loc_18000C895
0x18000c886  mov     al, [rdi]
0x18000c888  mov     rcx, [r9+30h]
0x18000c88c  mov     [rdx+rcx], al
0x18000c88f  inc     dword ptr [r9+1Ch]
0x18000c893  jmp     short loc_18000C8A6
0x18000c895  mov     r8d, 1
0x18000c89b  mov     rdx, rdi
0x18000c89e  mov     rcx, r9
0x18000c8a1  call    ?Write@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAAXPEBXI@Z; bond::OutputMemoryStream<std::allocator<char>>::Write(void const *,uint)
0x18000c8a6  mov     rbx, [rsp+28h+arg_0]
0x18000c8ab  xor     al, al
0x18000c8ad  add     rsp, 20h
0x18000c8b1  pop     rdi
0x18000c8b2  retn
```
