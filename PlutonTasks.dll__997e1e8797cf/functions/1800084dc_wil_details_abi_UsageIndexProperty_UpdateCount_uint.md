# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x1800084dc`
- end: `0x180008525`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `73`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *this, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800049bc`
- `0x180006b74`
- `0x180007acc`

## callees

- `0x1800084dc`
- `0x18000934c`

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
0x1800084dc  sub     rsp, 28h
0x1800084e0  lea     r8, [rcx+4]; Source
0x1800084e4  cmp     [r8], edx
0x1800084e7  jz      short loc_180008520
0x1800084e9  mov     al, [rcx+2]
0x1800084ec  mov     [r8], edx
0x1800084ef  cmp     al, 1
0x1800084f1  jnz     short loc_18000850B
0x1800084f3  mov     r9d, 2
0x1800084f9  mov     [rsp+28h+arg_8], dx
0x1800084fe  movzx   eax, dx
0x180008501  lea     r8, [rsp+28h+arg_8]
0x180008506  mov     edx, r9d
0x180008509  jmp     short loc_180008517
0x18000850b  cmp     al, 2
0x18000850d  jnz     short loc_180008520
0x18000850f  mov     edx, 4; DestinationSize
0x180008514  mov     r9d, edx; SourceSize
0x180008517  mov     rcx, [rcx+10h]; Destination
0x18000851b  call    memcpy_s
0x180008520  add     rsp, 28h
0x180008524  retn
```
