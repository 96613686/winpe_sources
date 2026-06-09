# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x1400111f4`
- end: `0x14001123e`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `74`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *this, int)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x14000b4b4`
- `0x14000f718`
- `0x14001096c`

## callees

- `0x1400111f4`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140011233`
- `msvcrt!memcpy_s` at `0x140011233`

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
0x1400111f4  sub     rsp, 28h
0x1400111f8  lea     r8, [rcx+4]; Source
0x1400111fc  cmp     [r8], edx
0x1400111ff  jz      short loc_140011239
0x140011201  mov     al, [rcx+2]
0x140011204  mov     [r8], edx
0x140011207  cmp     al, 1
0x140011209  jnz     short loc_140011223
0x14001120b  mov     r9d, 2
0x140011211  mov     [rsp+28h+arg_8], dx
0x140011216  movzx   eax, dx
0x140011219  lea     r8, [rsp+28h+arg_8]
0x14001121e  mov     edx, r9d
0x140011221  jmp     short loc_14001122F
0x140011223  cmp     al, 2
0x140011225  jnz     short loc_140011239
0x140011227  mov     edx, 4; DestinationSize
0x14001122c  mov     r9d, edx; SourceSize
0x14001122f  mov     rcx, [rcx+10h]; Destination
0x140011233  call    cs:__imp_memcpy_s
0x140011239  add     rsp, 28h
0x14001123d  retn
```
