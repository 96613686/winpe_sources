# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x180015e68`
- end: `0x180015eb2`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `74`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180012264`
- `0x1800141a4`
- `0x180014db4`

## callees

- `0x180015e68`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180015ea7`
- `msvcrt!memcpy_s` at `0x180015ea7`

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
0x180015e68  sub     rsp, 28h
0x180015e6c  lea     r8, [rcx+4]; Source
0x180015e70  cmp     [r8], edx
0x180015e73  jz      short loc_180015EAD
0x180015e75  mov     al, [rcx+2]
0x180015e78  mov     [r8], edx
0x180015e7b  cmp     al, 1
0x180015e7d  jnz     short loc_180015E97
0x180015e7f  mov     r9d, 2
0x180015e85  mov     [rsp+28h+arg_8], dx
0x180015e8a  movzx   eax, dx
0x180015e8d  lea     r8, [rsp+28h+arg_8]
0x180015e92  mov     edx, r9d
0x180015e95  jmp     short loc_180015EA3
0x180015e97  cmp     al, 2
0x180015e99  jnz     short loc_180015EAD
0x180015e9b  mov     edx, 4; DestinationSize
0x180015ea0  mov     r9d, edx; SourceSize
0x180015ea3  mov     rcx, [rcx+10h]; Destination
0x180015ea7  call    cs:__imp_memcpy_s
0x180015ead  add     rsp, 28h
0x180015eb1  retn
```
