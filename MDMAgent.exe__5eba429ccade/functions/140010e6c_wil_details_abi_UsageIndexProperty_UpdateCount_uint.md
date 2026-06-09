# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x140010e6c`
- end: `0x140010eb5`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `73`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *this, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000b3f8`
- `0x14000cca8`
- `0x1400101d8`

## callees

- `0x140007ea4`
- `0x140010e6c`

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
0x140010e6c  sub     rsp, 28h
0x140010e70  lea     r8, [rcx+4]; Source
0x140010e74  cmp     [r8], edx
0x140010e77  jz      short loc_140010EB0
0x140010e79  mov     al, [rcx+2]
0x140010e7c  mov     [r8], edx
0x140010e7f  cmp     al, 1
0x140010e81  jnz     short loc_140010E9B
0x140010e83  mov     r9d, 2
0x140010e89  mov     [rsp+28h+arg_8], dx
0x140010e8e  movzx   eax, dx
0x140010e91  lea     r8, [rsp+28h+arg_8]
0x140010e96  mov     edx, r9d
0x140010e99  jmp     short loc_140010EA7
0x140010e9b  cmp     al, 2
0x140010e9d  jnz     short loc_140010EB0
0x140010e9f  mov     edx, 4; DestinationSize
0x140010ea4  mov     r9d, edx; SourceSize
0x140010ea7  mov     rcx, [rcx+10h]; Destination
0x140010eab  call    memcpy_s
0x140010eb0  add     rsp, 28h
0x140010eb4  retn
```
