# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x1400103dc`
- end: `0x140010425`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `73`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000ed00`
- `0x14000fa98`
- `0x140010084`

## callees

- `0x1400103dc`
- `0x140011fb8`

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
    memcpy_s_0(*((void *const *)this + 2), v5, v2, v4);
  }
}

```

## disassembly

```asm
0x1400103dc  sub     rsp, 28h
0x1400103e0  lea     r8, [rcx+4]; Source
0x1400103e4  cmp     [r8], edx
0x1400103e7  jz      short loc_140010420
0x1400103e9  mov     al, [rcx+2]
0x1400103ec  mov     [r8], edx
0x1400103ef  cmp     al, 1
0x1400103f1  jnz     short loc_14001040B
0x1400103f3  mov     r9d, 2
0x1400103f9  mov     [rsp+28h+arg_8], dx
0x1400103fe  movzx   eax, dx
0x140010401  lea     r8, [rsp+28h+arg_8]
0x140010406  mov     edx, r9d
0x140010409  jmp     short loc_140010417
0x14001040b  cmp     al, 2
0x14001040d  jnz     short loc_140010420
0x14001040f  mov     edx, 4; DestinationSize
0x140010414  mov     r9d, edx; SourceSize
0x140010417  mov     rcx, [rcx+10h]; Destination
0x14001041b  call    memcpy_s_0
0x140010420  add     rsp, 28h
0x140010424  retn
```
