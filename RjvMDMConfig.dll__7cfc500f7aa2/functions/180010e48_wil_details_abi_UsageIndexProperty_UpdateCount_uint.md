# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x180010e48`
- end: `0x180010e92`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `74`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18000a148`
- `0x18000c1f0`
- `0x18000fdf4`

## callees

- `0x18000596c`
- `0x180010e48`

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
0x180010e48  sub     rsp, 28h
0x180010e4c  lea     r8, [rcx+4]; Source
0x180010e50  cmp     [r8], edx
0x180010e53  jz      short loc_180010E8C
0x180010e55  mov     al, [rcx+2]
0x180010e58  mov     [r8], edx
0x180010e5b  cmp     al, 1
0x180010e5d  jnz     short loc_180010E77
0x180010e5f  mov     r9d, 2
0x180010e65  mov     [rsp+28h+arg_8], dx
0x180010e6a  movzx   eax, dx
0x180010e6d  lea     r8, [rsp+28h+arg_8]
0x180010e72  mov     edx, r9d
0x180010e75  jmp     short loc_180010E83
0x180010e77  cmp     al, 2
0x180010e79  jnz     short loc_180010E8C
0x180010e7b  mov     edx, 4; DestinationSize
0x180010e80  mov     r9d, edx; SourceSize
0x180010e83  mov     rcx, [rcx+10h]; Destination
0x180010e87  call    memcpy_s
0x180010e8c  add     rsp, 28h
0x180010e90  retn
```
