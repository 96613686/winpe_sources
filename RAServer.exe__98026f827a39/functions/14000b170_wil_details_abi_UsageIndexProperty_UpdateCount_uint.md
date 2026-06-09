# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x14000b170`
- end: `0x14000b1ba`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `74`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140005fd8`
- `0x140008f40`
- `0x14000a878`

## callees

- `0x14000b170`

## import_xrefs

- `msvcrt!memcpy_s` at `0x14000b1af`
- `msvcrt!memcpy_s` at `0x14000b1af`

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
0x14000b170  sub     rsp, 28h
0x14000b174  lea     r8, [rcx+4]; Source
0x14000b178  cmp     [r8], edx
0x14000b17b  jz      short loc_14000B1B5
0x14000b17d  mov     al, [rcx+2]
0x14000b180  mov     [r8], edx
0x14000b183  cmp     al, 1
0x14000b185  jnz     short loc_14000B19F
0x14000b187  mov     r9d, 2
0x14000b18d  mov     [rsp+28h+arg_8], dx
0x14000b192  movzx   eax, dx
0x14000b195  lea     r8, [rsp+28h+arg_8]
0x14000b19a  mov     edx, r9d
0x14000b19d  jmp     short loc_14000B1AB
0x14000b19f  cmp     al, 2
0x14000b1a1  jnz     short loc_14000B1B5
0x14000b1a3  mov     edx, 4; DestinationSize
0x14000b1a8  mov     r9d, edx; SourceSize
0x14000b1ab  mov     rcx, [rcx+10h]; Destination
0x14000b1af  call    cs:__imp_memcpy_s
0x14000b1b5  add     rsp, 28h
0x14000b1b9  retn
```
