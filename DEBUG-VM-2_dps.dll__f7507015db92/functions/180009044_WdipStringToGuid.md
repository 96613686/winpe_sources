# WdipStringToGuid

- ea: `0x180009044`
- end: `0x18000907f`
- name: `WdipStringToGuid`
- size: `59`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000dc30`
- `0x18000e9d4`
- `0x18000ed8c`
- `0x180015b84`
- `0x180016914`

## callees

- `0x180009044`
- `0x18001745c`

## pseudocode

```c
__int64 __fastcall WdipStringToGuid(__int64 a1, __int64 a2)
{
  __int64 v3; // [rsp+30h] [rbp+8h] BYREF

  v3 = a1;
  if ( a1 && a2 )
    return tlx::string_to_guid<unsigned short const *>(a2, &v3) == 0 ? 0x80070057 : 0;
  else
    return 2147942487LL;
}

```

## disassembly

```asm
0x180009044  mov     [rsp+arg_0], rcx
0x180009049  sub     rsp, 28h
0x18000904d  mov     rax, rdx
0x180009050  test    rcx, rcx
0x180009053  jz      short loc_180009075
0x180009055  test    rax, rax
0x180009058  jz      short loc_180009075
0x18000905a  lea     rdx, [rsp+28h+arg_0]
0x18000905f  mov     rcx, rax
0x180009062  call    ??$string_to_guid@PEBG@tlx@@YAPEBGPEAU_GUID@@AEBQEBG@Z; tlx::string_to_guid<ushort const *>(_GUID *,ushort const * const &)
0x180009067  neg     rax
0x18000906a  sbb     eax, eax
0x18000906c  not     eax
0x18000906e  and     eax, 80070057h
0x180009073  jmp     short loc_18000907A
0x180009075  mov     eax, 80070057h
0x18000907a  add     rsp, 28h
0x18000907e  retn
```
