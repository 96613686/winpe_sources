# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x1800177bc`
- end: `0x180017806`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `74`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18000dc70`
- `0x180015698`
- `0x180016cd8`

## callees

- `0x1800177bc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800177fb`
- `msvcrt!memcpy_s` at `0x1800177fb`

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
0x1800177bc  sub     rsp, 28h
0x1800177c0  lea     r8, [rcx+4]; Source
0x1800177c4  cmp     [r8], edx
0x1800177c7  jz      short loc_180017801
0x1800177c9  mov     al, [rcx+2]
0x1800177cc  mov     [r8], edx
0x1800177cf  cmp     al, 1
0x1800177d1  jnz     short loc_1800177EB
0x1800177d3  mov     r9d, 2
0x1800177d9  mov     [rsp+28h+arg_8], dx
0x1800177de  movzx   eax, dx
0x1800177e1  lea     r8, [rsp+28h+arg_8]
0x1800177e6  mov     edx, r9d
0x1800177e9  jmp     short loc_1800177F7
0x1800177eb  cmp     al, 2
0x1800177ed  jnz     short loc_180017801
0x1800177ef  mov     edx, 4; DestinationSize
0x1800177f4  mov     r9d, edx; SourceSize
0x1800177f7  mov     rcx, [rcx+10h]; Destination
0x1800177fb  call    cs:__imp_memcpy_s
0x180017801  add     rsp, 28h
0x180017805  retn
```
