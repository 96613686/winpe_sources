# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x140006de0`
- end: `0x140006e29`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `73`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *this, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140003ac4`
- `0x1400059f4`
- `0x1400065d0`

## callees

- `0x140006de0`
- `0x140007a00`

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
0x140006de0  sub     rsp, 28h
0x140006de4  lea     r8, [rcx+4]; Source
0x140006de8  cmp     [r8], edx
0x140006deb  jz      short loc_140006E24
0x140006ded  mov     al, [rcx+2]
0x140006df0  mov     [r8], edx
0x140006df3  cmp     al, 1
0x140006df5  jnz     short loc_140006E0F
0x140006df7  mov     r9d, 2
0x140006dfd  mov     [rsp+28h+arg_8], dx
0x140006e02  movzx   eax, dx
0x140006e05  lea     r8, [rsp+28h+arg_8]
0x140006e0a  mov     edx, r9d
0x140006e0d  jmp     short loc_140006E1B
0x140006e0f  cmp     al, 2
0x140006e11  jnz     short loc_140006E24
0x140006e13  mov     edx, 4; DestinationSize
0x140006e18  mov     r9d, edx; SourceSize
0x140006e1b  mov     rcx, [rcx+10h]; Destination
0x140006e1f  call    memcpy_s
0x140006e24  add     rsp, 28h
0x140006e28  retn
```
