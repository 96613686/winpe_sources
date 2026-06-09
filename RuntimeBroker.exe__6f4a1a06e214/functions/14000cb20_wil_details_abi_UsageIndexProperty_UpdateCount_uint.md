# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x14000cb20`
- end: `0x14000cb69`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `73`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1400035bc`
- `0x14000417c`
- `0x14000c8fc`

## callees

- `0x140006030`
- `0x14000cb20`

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
0x14000cb20  sub     rsp, 28h
0x14000cb24  lea     r8, [rcx+4]; Source
0x14000cb28  cmp     [r8], edx
0x14000cb2b  jz      short loc_14000CB64
0x14000cb2d  mov     al, [rcx+2]
0x14000cb30  mov     [r8], edx
0x14000cb33  cmp     al, 1
0x14000cb35  jnz     short loc_14000CB4F
0x14000cb37  mov     r9d, 2
0x14000cb3d  mov     [rsp+28h+arg_8], dx
0x14000cb42  movzx   eax, dx
0x14000cb45  lea     r8, [rsp+28h+arg_8]
0x14000cb4a  mov     edx, r9d
0x14000cb4d  jmp     short loc_14000CB5B
0x14000cb4f  cmp     al, 2
0x14000cb51  jnz     short loc_14000CB64
0x14000cb53  mov     edx, 4; DestinationSize
0x14000cb58  mov     r9d, edx; SourceSize
0x14000cb5b  mov     rcx, [rcx+10h]; Destination
0x14000cb5f  call    memcpy_s
0x14000cb64  add     rsp, 28h
0x14000cb68  retn
```
