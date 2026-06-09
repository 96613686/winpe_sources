# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x18000ce68`
- end: `0x18000ceb1`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `73`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *this, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180003ab8`
- `0x18000bc48`
- `0x18000ca9c`

## callees

- `0x1800034d8`
- `0x18000ce68`

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
0x18000ce68  sub     rsp, 28h
0x18000ce6c  lea     r8, [rcx+4]; Source
0x18000ce70  cmp     [r8], edx
0x18000ce73  jz      short loc_18000CEAC
0x18000ce75  mov     al, [rcx+2]
0x18000ce78  mov     [r8], edx
0x18000ce7b  cmp     al, 1
0x18000ce7d  jnz     short loc_18000CE97
0x18000ce7f  mov     r9d, 2
0x18000ce85  mov     [rsp+28h+arg_8], dx
0x18000ce8a  movzx   eax, dx
0x18000ce8d  lea     r8, [rsp+28h+arg_8]
0x18000ce92  mov     edx, r9d
0x18000ce95  jmp     short loc_18000CEA3
0x18000ce97  cmp     al, 2
0x18000ce99  jnz     short loc_18000CEAC
0x18000ce9b  mov     edx, 4; DestinationSize
0x18000cea0  mov     r9d, edx; SourceSize
0x18000cea3  mov     rcx, [rcx+10h]; Destination
0x18000cea7  call    memcpy_s
0x18000ceac  add     rsp, 28h
0x18000ceb0  retn
```
