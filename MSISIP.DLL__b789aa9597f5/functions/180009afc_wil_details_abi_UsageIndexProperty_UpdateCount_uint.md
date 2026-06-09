# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x180009afc`
- end: `0x180009b46`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `74`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180004eb0`
- `0x18000c80c`

## callees

- `0x180009afc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180009b3b`
- `msvcrt!memcpy_s` at `0x180009b3b`

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
0x180009afc  sub     rsp, 28h
0x180009b00  lea     r8, [rcx+4]; Source
0x180009b04  cmp     [r8], edx
0x180009b07  jz      short loc_180009B41
0x180009b09  mov     al, [rcx+2]
0x180009b0c  mov     [r8], edx
0x180009b0f  cmp     al, 1
0x180009b11  jnz     short loc_180009B2B
0x180009b13  mov     r9d, 2
0x180009b19  mov     [rsp+28h+arg_8], dx
0x180009b1e  movzx   eax, dx
0x180009b21  lea     r8, [rsp+28h+arg_8]
0x180009b26  mov     edx, r9d
0x180009b29  jmp     short loc_180009B37
0x180009b2b  cmp     al, 2
0x180009b2d  jnz     short loc_180009B41
0x180009b2f  mov     edx, 4; DestinationSize
0x180009b34  mov     r9d, edx; SourceSize
0x180009b37  mov     rcx, [rcx+10h]; Destination
0x180009b3b  call    cs:__imp_memcpy_s
0x180009b41  add     rsp, 28h
0x180009b45  retn
```
