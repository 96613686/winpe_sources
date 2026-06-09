# CompletionIterator::get_CurrentPosition(ulong *)

- ea: `0x180003100`
- end: `0x18000318d`
- name: `?get_CurrentPosition@CompletionIterator@@UEAAJPEAK@Z`
- size: `141`
- prototype: `__int64 __fastcall(CompletionIterator *__hidden this, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002620`
- `0x180002e08`
- `0x180003100`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CompletionIterator::get_CurrentPosition(CompletionIterator *this, unsigned int *a2)
{
  __int64 result; // rax
  unsigned int v5; // eax
  char v6; // al
  char *v7; // rcx
  int v8; // eax
  int v9; // ecx

  if ( !a2 )
    return 2147942487LL;
  if ( *((_BYTE *)this + 128) )
  {
    result = CompletionIterator::FullyComputePositions(this);
    if ( (int)result < 0 )
      return result;
    v6 = (*(__int64 (__fastcall **)(CompletionIterator *))(*(_QWORD *)this + 88LL))(this);
    v7 = (char *)this + 32;
    if ( v6 )
    {
      v8 = OrderedSet<PositionData>::SortList(v7);
      if ( v8 >= 0 )
        v8 = *(_DWORD *)(*((_QWORD *)this + 13) + 8LL);
      v5 = v8 + 1;
    }
    else
    {
      v9 = OrderedSet<PositionData>::SortList(v7);
      if ( v9 >= 0 )
        v9 = *(_DWORD *)(*((_QWORD *)this + 13) + 8LL);
      v5 = *((_DWORD *)this + 13) - v9;
    }
  }
  else
  {
    v5 = 0;
  }
  *a2 = v5;
  return 0;
}

```

## disassembly

```asm
0x180003100  mov     [rsp+arg_0], rbx
0x180003105  mov     [rsp+arg_8], rsi
0x18000310a  push    rdi
0x18000310b  sub     rsp, 20h
0x18000310f  mov     rdi, rdx
0x180003112  mov     rbx, rcx
0x180003115  test    rdx, rdx
0x180003118  jnz     short loc_180003121
0x18000311a  mov     eax, 80070057h
0x18000311f  jmp     short loc_18000317D
0x180003121  cmp     byte ptr [rcx+80h], 0
0x180003128  jnz     short loc_18000312E
0x18000312a  xor     eax, eax
0x18000312c  jmp     short loc_180003179
0x18000312e  call    ?FullyComputePositions@CompletionIterator@@AEAAJXZ; CompletionIterator::FullyComputePositions(void)
0x180003133  test    eax, eax
0x180003135  js      short loc_18000317D
0x180003137  mov     rax, [rbx]
0x18000313a  mov     rcx, rbx
0x18000313d  mov     rax, [rax+58h]
0x180003141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003146  lea     rcx, [rbx+20h]
0x18000314a  test    al, al
0x18000314c  jz      short loc_180003162
0x18000314e  call    ?SortList@?$OrderedSet@VPositionData@@@@AEAAJXZ; OrderedSet<PositionData>::SortList(void)
0x180003153  test    eax, eax
0x180003155  js      short loc_18000315E
0x180003157  mov     rax, [rbx+68h]
0x18000315b  mov     eax, [rax+8]
0x18000315e  inc     eax
0x180003160  jmp     short loc_180003179
0x180003162  call    ?SortList@?$OrderedSet@VPositionData@@@@AEAAJXZ; OrderedSet<PositionData>::SortList(void)
0x180003167  mov     ecx, eax
0x180003169  test    eax, eax
0x18000316b  js      short loc_180003174
0x18000316d  mov     rax, [rbx+68h]
0x180003171  mov     ecx, [rax+8]
0x180003174  mov     eax, [rbx+34h]
0x180003177  sub     eax, ecx
0x180003179  mov     [rdi], eax
0x18000317b  xor     eax, eax
0x18000317d  mov     rbx, [rsp+28h+arg_0]
0x180003182  mov     rsi, [rsp+28h+arg_8]
0x180003187  add     rsp, 20h
0x18000318b  pop     rdi
0x18000318c  retn
```
