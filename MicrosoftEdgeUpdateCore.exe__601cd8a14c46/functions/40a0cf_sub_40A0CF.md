# sub_40A0CF

- ea: `0x40a0cf`
- end: `0x40a121`
- name: `sub_40A0CF`
- size: `82`
- prototype: `_DWORD *__thiscall(_DWORD *this, _DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x409aee`

## callees

- `0x4015fb`
- `0x401fbb`
- `0x405b8c`
- `0x405ba1`
- `0x40a0cf`

## string_xrefs

- `0x40a0e9`: `update`

## pseudocode

```c
_DWORD *__thiscall sub_40A0CF(_DWORD *this, _DWORD *a2)
{
  int *v3; // eax

  *a2 = 0;
  v3 = sub_4015FB();
  sub_401FBB(a2, (int)v3);
  sub_405B8C((int)a2, (int)L"/%s", L"update");
  if ( *(_DWORD *)(this[11] - 12) )
    sub_405BA1((int)a2, (int)L" /%s \"%s\"", L"sessionid", this[11]);
  return a2;
}

```

## disassembly

```asm
0x40a0cf  push    ebp
0x40a0d0  mov     ebp, esp
0x40a0d2  push    esi
0x40a0d3  push    edi
0x40a0d4  mov     edi, [ebp+arg_0]
0x40a0d7  mov     esi, ecx
0x40a0d9  and     dword ptr [edi], 0
0x40a0dc  call    sub_4015FB
0x40a0e1  push    eax
0x40a0e2  mov     ecx, edi
0x40a0e4  call    sub_401FBB
0x40a0e9  push    offset aUpdate; "update"
0x40a0ee  push    offset aS; "/%s"
0x40a0f3  push    edi
0x40a0f4  call    sub_405B8C
0x40a0f9  mov     eax, [esi+2Ch]
0x40a0fc  add     esp, 0Ch
0x40a0ff  cmp     dword ptr [eax-0Ch], 0
0x40a103  jz      short loc_40A119
0x40a105  push    eax
0x40a106  push    offset aSessionid; "sessionid"
0x40a10b  push    offset aSS_2; " /%s \"%s\""
0x40a110  push    edi
0x40a111  call    sub_405BA1
0x40a116  add     esp, 10h
0x40a119  mov     eax, edi
0x40a11b  pop     edi
0x40a11c  pop     esi
0x40a11d  pop     ebp
0x40a11e  retn    4
```
