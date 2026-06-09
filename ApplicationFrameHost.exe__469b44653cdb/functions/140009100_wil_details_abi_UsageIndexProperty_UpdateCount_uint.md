# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x140009100`
- end: `0x140009149`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `73`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140005d20`
- `0x140007a7c`
- `0x14000893c`

## callees

- `0x140009100`
- `0x140009d98`

## pseudocode

```c
void __fastcall wil::details_abi::UsageIndexProperty::UpdateCount(wil::details_abi::UsageIndexProperty *this, int a2)
{
  __int16 *v2; // r8
  char v3; // al
  rsize_t v4; // r9
  rsize_t v5; // rdx
  __int16 v6; // [rsp+38h] [rbp+10h] BYREF

  v2 = (__int16 *)((char *)this + 4);
  if ( *((_DWORD *)this + 1) != a2 )
  {
    v3 = *((_BYTE *)this + 2);
    *(_DWORD *)v2 = a2;
    if ( v3 == 1 )
    {
      v4 = 2;
      v6 = a2;
      v2 = &v6;
      v5 = 2;
    }
    else
    {
      if ( v3 != 2 )
        return;
      v5 = 4;
      v4 = 4;
    }
    memcpy_s(*((void *const *)this + 2), v5, v2, v4);
  }
}

```

## disassembly

```asm
0x140009100  sub     rsp, 28h
0x140009104  lea     r8, [rcx+4]; Source
0x140009108  cmp     [r8], edx
0x14000910b  jz      short loc_140009144
0x14000910d  mov     al, [rcx+2]
0x140009110  mov     [r8], edx
0x140009113  cmp     al, 1
0x140009115  jnz     short loc_14000912F
0x140009117  mov     r9d, 2
0x14000911d  mov     [rsp+28h+arg_8], dx
0x140009122  movzx   eax, dx
0x140009125  lea     r8, [rsp+28h+arg_8]
0x14000912a  mov     edx, r9d
0x14000912d  jmp     short loc_14000913B
0x14000912f  cmp     al, 2
0x140009131  jnz     short loc_140009144
0x140009133  mov     edx, 4; DestinationSize
0x140009138  mov     r9d, edx; SourceSize
0x14000913b  mov     rcx, [rcx+10h]; Destination
0x14000913f  call    memcpy_s
0x140009144  add     rsp, 28h
0x140009148  retn
```
