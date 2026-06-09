# wil::details_abi::UsageIndexProperty::GetSize(void)

- ea: `0x180008784`
- end: `0x1800087b0`
- name: `?GetSize@UsageIndexProperty@details_abi@wil@@QEBA_KXZ`
- size: `44`
- prototype: `unsigned __int64 __fastcall(wil::details_abi::UsageIndexProperty *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180004c5c`
- `0x180006c20`
- `0x180008664`

## callees

- `0x180008784`

## pseudocode

```c
__int64 __fastcall wil::details_abi::UsageIndexProperty::GetSize(wil::details_abi::UsageIndexProperty *this)
{
  __int64 result; // rax
  char v2; // dl

  if ( *(_WORD *)this )
    result = *(unsigned __int16 *)this;
  else
    result = *((unsigned __int16 *)this + 4) + 2LL;
  v2 = *((_BYTE *)this + 2);
  if ( v2 == 1 )
  {
    result += 2;
  }
  else if ( v2 == 2 )
  {
    result += 4;
  }
  return result;
}

```

## disassembly

```asm
0x180008784  cmp     word ptr [rcx], 0
0x180008788  jnz     short loc_180008794
0x18000878a  movzx   eax, word ptr [rcx+8]
0x18000878e  add     rax, 2
0x180008792  jmp     short loc_180008797
0x180008794  movzx   eax, word ptr [rcx]
0x180008797  mov     dl, [rcx+2]
0x18000879a  cmp     dl, 1
0x18000879d  jnz     short loc_1800087A4
0x18000879f  add     rax, 2
0x1800087a3  retn
0x1800087a4  cmp     dl, 2
0x1800087a7  lea     rcx, [rax+4]
0x1800087ab  cmovz   rax, rcx
0x1800087af  retn
```
