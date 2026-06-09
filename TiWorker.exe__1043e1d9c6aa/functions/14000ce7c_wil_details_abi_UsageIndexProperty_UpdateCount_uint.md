# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x14000ce7c`
- end: `0x14000cec5`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `73`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *this, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000ac1c`
- `0x14000c0f8`
- `0x14000c7c4`

## callees

- `0x140005ef8`
- `0x14000ce7c`

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
0x14000ce7c  sub     rsp, 28h
0x14000ce80  lea     r8, [rcx+4]; Source
0x14000ce84  cmp     [r8], edx
0x14000ce87  jz      short loc_14000CEC0
0x14000ce89  mov     al, [rcx+2]
0x14000ce8c  mov     [r8], edx
0x14000ce8f  cmp     al, 1
0x14000ce91  jnz     short loc_14000CEAB
0x14000ce93  mov     r9d, 2
0x14000ce99  mov     [rsp+28h+arg_8], dx
0x14000ce9e  movzx   eax, dx
0x14000cea1  lea     r8, [rsp+28h+arg_8]
0x14000cea6  mov     edx, r9d
0x14000cea9  jmp     short loc_14000CEB7
0x14000ceab  cmp     al, 2
0x14000cead  jnz     short loc_14000CEC0
0x14000ceaf  mov     edx, 4; DestinationSize
0x14000ceb4  mov     r9d, edx; SourceSize
0x14000ceb7  mov     rcx, [rcx+10h]; Destination
0x14000cebb  call    memcpy_s
0x14000cec0  add     rsp, 28h
0x14000cec4  retn
```
