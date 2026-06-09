# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x18000a784`
- end: `0x18000a7cd`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `73`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800089b0`
- `0x180009938`
- `0x18000a28c`

## callees

- `0x1800076d8`
- `0x18000a784`

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
0x18000a784  sub     rsp, 28h
0x18000a788  lea     r8, [rcx+4]; Source
0x18000a78c  cmp     [r8], edx
0x18000a78f  jz      short loc_18000A7C8
0x18000a791  mov     al, [rcx+2]
0x18000a794  mov     [r8], edx
0x18000a797  cmp     al, 1
0x18000a799  jnz     short loc_18000A7B3
0x18000a79b  mov     r9d, 2
0x18000a7a1  mov     [rsp+28h+arg_8], dx
0x18000a7a6  movzx   eax, dx
0x18000a7a9  lea     r8, [rsp+28h+arg_8]
0x18000a7ae  mov     edx, r9d
0x18000a7b1  jmp     short loc_18000A7BF
0x18000a7b3  cmp     al, 2
0x18000a7b5  jnz     short loc_18000A7C8
0x18000a7b7  mov     edx, 4; DestinationSize
0x18000a7bc  mov     r9d, edx; SourceSize
0x18000a7bf  mov     rcx, [rcx+10h]; Destination
0x18000a7c3  call    memcpy_s
0x18000a7c8  add     rsp, 28h
0x18000a7cc  retn
```
