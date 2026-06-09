# bond::CompactBinaryReader<bond::InputBuffer>::SkipStructV2(void)

- ea: `0x18000bd78`
- end: `0x18000bddf`
- name: `?SkipStructV2@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@IEAAXXZ`
- size: `103`
- prototype: `__int64 __fastcall(bond::InputBuffer *this)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000b9b0`
- `0x18000b9d8`
- `0x18000ba24`
- `0x18000bde8`
- `0x18000bfa0`

## callees

- `0x18000a420`
- `0x18000bd78`
- `0x180017210`
- `0x180019808`

## pseudocode

```c
void __fastcall bond::CompactBinaryReader<bond::InputBuffer>::SkipStructV2(bond::InputBuffer *this)
{
  __int64 v2; // rcx
  __int64 v3; // rbx
  unsigned int v4; // [rsp+30h] [rbp+8h] BYREF
  char *v5; // [rsp+38h] [rbp+10h] BYREF

  v4 = 0;
  v2 = *((unsigned int *)this + 6);
  if ( *((unsigned int *)this + 4) <= (unsigned __int64)(v2 + 4) )
  {
    bond::GenericReadVariableUnsigned<bond::InputBuffer,unsigned int>(this, &v4);
  }
  else
  {
    v3 = *(_QWORD *)this;
    v5 = (char *)(*(_QWORD *)this + v2);
    bond::input_buffer::VariableUnsignedUnchecked<unsigned int,0>::Read(&v5, (int *)&v4);
    *((_DWORD *)this + 6) = (_DWORD)v5 - v3;
  }
  bond::InputBuffer::Skip(this, v4);
}

```

## disassembly

```asm
0x18000bd78  mov     r11, rsp
0x18000bd7b  mov     [r11+18h], rbx
0x18000bd7f  push    rdi
0x18000bd80  sub     rsp, 20h
0x18000bd84  mov     rdi, rcx
0x18000bd87  mov     [rsp+28h+arg_0], 0
0x18000bd8f  mov     ecx, [rcx+18h]
0x18000bd92  mov     edx, [rdi+10h]
0x18000bd95  lea     rax, [rcx+4]
0x18000bd99  cmp     rdx, rax
0x18000bd9c  lea     rdx, [r11+8]
0x18000bda0  jbe     short loc_18000BDC1
0x18000bda2  mov     rbx, [rdi]
0x18000bda5  lea     rax, [rbx+rcx]
0x18000bda9  lea     rcx, [r11+10h]
0x18000bdad  mov     [r11+10h], rax
0x18000bdb1  call    ?Read@?$VariableUnsignedUnchecked@I$0A@@input_buffer@bond@@SAXAEAPEBDAEAI@Z; bond::input_buffer::VariableUnsignedUnchecked<uint,0>::Read(char const * &,uint &)
0x18000bdb6  mov     eax, dword ptr [rsp+28h+arg_8]
0x18000bdba  sub     eax, ebx
0x18000bdbc  mov     [rdi+18h], eax
0x18000bdbf  jmp     short loc_18000BDC9
0x18000bdc1  mov     rcx, rdi; this
0x18000bdc4  call    ??$GenericReadVariableUnsigned@VInputBuffer@bond@@I@bond@@YAXAEAVInputBuffer@0@AEAI@Z; bond::GenericReadVariableUnsigned<bond::InputBuffer,uint>(bond::InputBuffer &,uint &)
0x18000bdc9  mov     edx, [rsp+28h+arg_0]; unsigned int
0x18000bdcd  mov     rcx, rdi; this
0x18000bdd0  mov     rbx, [rsp+28h+arg_10]
0x18000bdd5  add     rsp, 20h
0x18000bdd9  pop     rdi
0x18000bdda  jmp     ?Skip@InputBuffer@bond@@QEAAXI@Z; bond::InputBuffer::Skip(uint)
```
