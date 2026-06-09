# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x140006bc8`
- end: `0x140006c11`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `73`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140001e60`
- `0x140004490`
- `0x140006590`

## callees

- `0x140001cdc`
- `0x140006bc8`

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
0x140006bc8  sub     rsp, 28h
0x140006bcc  lea     r8, [rcx+4]; Source
0x140006bd0  cmp     [r8], edx
0x140006bd3  jz      short loc_140006C0C
0x140006bd5  mov     al, [rcx+2]
0x140006bd8  mov     [r8], edx
0x140006bdb  cmp     al, 1
0x140006bdd  jnz     short loc_140006BF7
0x140006bdf  mov     r9d, 2
0x140006be5  mov     [rsp+28h+arg_8], dx
0x140006bea  movzx   eax, dx
0x140006bed  lea     r8, [rsp+28h+arg_8]
0x140006bf2  mov     edx, r9d
0x140006bf5  jmp     short loc_140006C03
0x140006bf7  cmp     al, 2
0x140006bf9  jnz     short loc_140006C0C
0x140006bfb  mov     edx, 4; DestinationSize
0x140006c00  mov     r9d, edx; SourceSize
0x140006c03  mov     rcx, [rcx+10h]; Destination
0x140006c07  call    memcpy_s
0x140006c0c  add     rsp, 28h
0x140006c10  retn
```
