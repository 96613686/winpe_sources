# wil::details_abi::UsageIndexProperty::UpdateCount(uint)

- ea: `0x1400116e4`
- end: `0x14001172e`
- name: `?UpdateCount@UsageIndexProperty@details_abi@wil@@QEAAXI@Z`
- size: `74`
- prototype: `void __fastcall(wil::details_abi::UsageIndexProperty *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x14000b918`
- `0x14000d290`
- `0x1400109fc`

## callees

- `0x140008200`
- `0x1400116e4`

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
0x1400116e4  sub     rsp, 28h
0x1400116e8  lea     r8, [rcx+4]; Source
0x1400116ec  cmp     [r8], edx
0x1400116ef  jz      short loc_140011728
0x1400116f1  mov     al, [rcx+2]
0x1400116f4  mov     [r8], edx
0x1400116f7  cmp     al, 1
0x1400116f9  jnz     short loc_140011713
0x1400116fb  mov     r9d, 2
0x140011701  mov     [rsp+28h+arg_8], dx
0x140011706  movzx   eax, dx
0x140011709  lea     r8, [rsp+28h+arg_8]
0x14001170e  mov     edx, r9d
0x140011711  jmp     short loc_14001171F
0x140011713  cmp     al, 2
0x140011715  jnz     short loc_140011728
0x140011717  mov     edx, 4; DestinationSize
0x14001171c  mov     r9d, edx; SourceSize
0x14001171f  mov     rcx, [rcx+10h]; Destination
0x140011723  call    memcpy_s
0x140011728  add     rsp, 28h
0x14001172c  retn
```
