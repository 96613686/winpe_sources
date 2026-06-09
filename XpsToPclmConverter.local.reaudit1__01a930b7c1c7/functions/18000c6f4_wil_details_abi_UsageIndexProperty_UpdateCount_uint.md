# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x18000c6f4`
- end: `0x18000c73d`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `73`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800091f4`
- `0x18000b1a4`
- `0x18000bec0`

## callees

- `0x18000c6f4`
- `0x18000d374`

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
0x18000c6f4  sub     rsp, 28h
0x18000c6f8  lea     r8, [rcx+4]; Source
0x18000c6fc  cmp     [r8], edx
0x18000c6ff  jz      short loc_18000C738
0x18000c701  mov     al, [rcx+2]
0x18000c704  mov     [r8], edx
0x18000c707  cmp     al, 1
0x18000c709  jnz     short loc_18000C723
0x18000c70b  mov     r9d, 2
0x18000c711  mov     [rsp+28h+arg_8], dx
0x18000c716  movzx   eax, dx
0x18000c719  lea     r8, [rsp+28h+arg_8]
0x18000c71e  mov     edx, r9d
0x18000c721  jmp     short loc_18000C72F
0x18000c723  cmp     al, 2
0x18000c725  jnz     short loc_18000C738
0x18000c727  mov     edx, 4; DestinationSize
0x18000c72c  mov     r9d, edx; SourceSize
0x18000c72f  mov     rcx, [rcx+10h]; Destination
0x18000c733  call    memcpy_s
0x18000c738  add     rsp, 28h
0x18000c73c  retn
```
