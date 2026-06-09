# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x180013d3c`
- end: `0x180013d85`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `73`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000dd5c`
- `0x180010d94`
- `0x1800134e0`

## callees

- `0x18000dbd8`
- `0x180013d3c`

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
0x180013d3c  sub     rsp, 28h
0x180013d40  lea     r8, [rcx+4]; Source
0x180013d44  cmp     [r8], edx
0x180013d47  jz      short loc_180013D80
0x180013d49  mov     al, [rcx+2]
0x180013d4c  mov     [r8], edx
0x180013d4f  cmp     al, 1
0x180013d51  jnz     short loc_180013D6B
0x180013d53  mov     r9d, 2
0x180013d59  mov     [rsp+28h+arg_8], dx
0x180013d5e  movzx   eax, dx
0x180013d61  lea     r8, [rsp+28h+arg_8]
0x180013d66  mov     edx, r9d
0x180013d69  jmp     short loc_180013D77
0x180013d6b  cmp     al, 2
0x180013d6d  jnz     short loc_180013D80
0x180013d6f  mov     edx, 4; DestinationSize
0x180013d74  mov     r9d, edx; SourceSize
0x180013d77  mov     rcx, [rcx+10h]; Destination
0x180013d7b  call    memcpy_s
0x180013d80  add     rsp, 28h
0x180013d84  retn
```
