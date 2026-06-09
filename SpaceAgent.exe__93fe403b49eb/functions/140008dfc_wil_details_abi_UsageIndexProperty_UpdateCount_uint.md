# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x140008dfc`
- end: `0x140008e46`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `74`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *this, int)`
- caller_count: `3`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140005358`
- `0x1400074f4`
- `0x140007fc0`

## callees

- `0x140008dfc`

## import_xrefs

- `msvcrt!memcpy_s` at `0x140008e3b`
- `msvcrt!memcpy_s` at `0x140008e3b`

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
0x140008dfc  sub     rsp, 28h
0x140008e00  lea     r8, [rcx+4]; Source
0x140008e04  cmp     [r8], edx
0x140008e07  jz      short loc_140008E41
0x140008e09  mov     al, [rcx+2]
0x140008e0c  mov     [r8], edx
0x140008e0f  cmp     al, 1
0x140008e11  jnz     short loc_140008E2B
0x140008e13  mov     r9d, 2
0x140008e19  mov     [rsp+28h+arg_8], dx
0x140008e1e  movzx   eax, dx
0x140008e21  lea     r8, [rsp+28h+arg_8]
0x140008e26  mov     edx, r9d
0x140008e29  jmp     short loc_140008E37
0x140008e2b  cmp     al, 2
0x140008e2d  jnz     short loc_140008E41
0x140008e2f  mov     edx, 4; DestinationSize
0x140008e34  mov     r9d, edx; SourceSize
0x140008e37  mov     rcx, [rcx+10h]; Destination
0x140008e3b  call    cs:__imp_memcpy_s
0x140008e41  add     rsp, 28h
0x140008e45  retn
```
