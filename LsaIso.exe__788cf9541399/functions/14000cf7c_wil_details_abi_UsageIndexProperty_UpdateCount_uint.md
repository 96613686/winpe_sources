# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x14000cf7c`
- end: `0x14000cfc6`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `74`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, installer_update`

## callers

- `0x1400095ac`
- `0x14000b978`
- `0x14000c584`

## callees

- `0x14000cf7c`

## import_xrefs

- `ntdll!memcpy_s` at `0x14000cfbb`
- `ntdll!memcpy_s` at `0x14000cfbb`

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
0x14000cf7c  sub     rsp, 28h
0x14000cf80  lea     r8, [rcx+4]; Source
0x14000cf84  cmp     [r8], edx
0x14000cf87  jz      short loc_14000CFC1
0x14000cf89  mov     al, [rcx+2]
0x14000cf8c  mov     [r8], edx
0x14000cf8f  cmp     al, 1
0x14000cf91  jnz     short loc_14000CFAB
0x14000cf93  mov     r9d, 2
0x14000cf99  mov     [rsp+28h+arg_8], dx
0x14000cf9e  movzx   eax, dx
0x14000cfa1  lea     r8, [rsp+28h+arg_8]
0x14000cfa6  mov     edx, r9d
0x14000cfa9  jmp     short loc_14000CFB7
0x14000cfab  cmp     al, 2
0x14000cfad  jnz     short loc_14000CFC1
0x14000cfaf  mov     edx, 4; DestinationSize
0x14000cfb4  mov     r9d, edx; SourceSize
0x14000cfb7  mov     rcx, [rcx+10h]; Destination
0x14000cfbb  call    cs:__imp_memcpy_s
0x14000cfc1  add     rsp, 28h
0x14000cfc5  retn
```
