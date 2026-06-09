# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x180011d14`
- end: `0x180011d5e`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `74`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *this, int)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18000fa84`
- `0x180010f1c`
- `0x180011a5c`

## callees

- `0x180011d14`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180011d53`
- `msvcrt!memcpy_s` at `0x180011d53`

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
0x180011d14  sub     rsp, 28h
0x180011d18  lea     r8, [rcx+4]; Source
0x180011d1c  cmp     [r8], edx
0x180011d1f  jz      short loc_180011D59
0x180011d21  mov     al, [rcx+2]
0x180011d24  mov     [r8], edx
0x180011d27  cmp     al, 1
0x180011d29  jnz     short loc_180011D43
0x180011d2b  mov     r9d, 2
0x180011d31  mov     [rsp+28h+arg_8], dx
0x180011d36  movzx   eax, dx
0x180011d39  lea     r8, [rsp+28h+arg_8]
0x180011d3e  mov     edx, r9d
0x180011d41  jmp     short loc_180011D4F
0x180011d43  cmp     al, 2
0x180011d45  jnz     short loc_180011D59
0x180011d47  mov     edx, 4; DestinationSize
0x180011d4c  mov     r9d, edx; SourceSize
0x180011d4f  mov     rcx, [rcx+10h]; Destination
0x180011d53  call    cs:__imp_memcpy_s
0x180011d59  add     rsp, 28h
0x180011d5d  retn
```
