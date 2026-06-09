# CATUtils::IsDesktopOOBEUserSessionActive(void)

- ea: `0x1400157f8`
- end: `0x14001582a`
- name: `?IsDesktopOOBEUserSessionActive@CATUtils@@SA_NXZ`
- size: `50`
- prototype: `bool(void)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000b250`
- `0x14000fd08`
- `0x140010244`

## callees

- `0x1400157f8`
- `0x1400158e4`

## import_xrefs

- `KERNEL32!OOBEComplete` at `0x140015809`
- `KERNEL32!OOBEComplete` at `0x140015809`

## pseudocode

```c
char CATUtils::IsDesktopOOBEUserSessionActive(void)
{
  const unsigned __int16 *v0; // rdx
  wil *v1; // rcx
  int v3; // [rsp+30h] [rbp+8h] BYREF

  v3 = 0;
  if ( !(unsigned int)OOBEComplete(&v3) || v3 )
    return 0;
  else
    return wil::is_default_system_managed_account(v1, v0);
}

```

## disassembly

```asm
0x1400157f8  sub     rsp, 28h
0x1400157fc  lea     rcx, [rsp+28h+arg_0]
0x140015801  mov     [rsp+28h+arg_0], 0
0x140015809  call    cs:__imp_OOBEComplete
0x14001580f  test    eax, eax
0x140015811  jz      short loc_140015823
0x140015813  cmp     [rsp+28h+arg_0], 0
0x140015818  jnz     short loc_140015823
0x14001581a  add     rsp, 28h
0x14001581e  jmp     ?is_default_system_managed_account@wil@@YA_NPEBG@Z; wil::is_default_system_managed_account(ushort const *)
0x140015823  xor     al, al
0x140015825  add     rsp, 28h
0x140015829  retn
```
