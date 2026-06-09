# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x180009788`
- end: `0x1800097d1`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `73`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *this, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180005bb4`
- `0x180007e68`
- `0x180008dbc`

## callees

- `0x180009788`
- `0x18000a558`

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
0x180009788  sub     rsp, 28h
0x18000978c  lea     r8, [rcx+4]; Source
0x180009790  cmp     [r8], edx
0x180009793  jz      short loc_1800097CC
0x180009795  mov     al, [rcx+2]
0x180009798  mov     [r8], edx
0x18000979b  cmp     al, 1
0x18000979d  jnz     short loc_1800097B7
0x18000979f  mov     r9d, 2
0x1800097a5  mov     [rsp+28h+arg_8], dx
0x1800097aa  movzx   eax, dx
0x1800097ad  lea     r8, [rsp+28h+arg_8]
0x1800097b2  mov     edx, r9d
0x1800097b5  jmp     short loc_1800097C3
0x1800097b7  cmp     al, 2
0x1800097b9  jnz     short loc_1800097CC
0x1800097bb  mov     edx, 4; DestinationSize
0x1800097c0  mov     r9d, edx; SourceSize
0x1800097c3  mov     rcx, [rcx+10h]; Destination
0x1800097c7  call    memcpy_s
0x1800097cc  add     rsp, 28h
0x1800097d0  retn
```
