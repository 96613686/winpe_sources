# sub_40BB5B

- ea: `0x40bb5b`
- end: `0x40bba1`
- name: `sub_40BB5B`
- size: `70`
- prototype: `_DWORD *__stdcall(_DWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x409862`

## callees

- `0x4015d2`
- `0x4015fb`
- `0x401cfa`
- `0x401fbb`
- `0x40a943`

## string_xrefs

- `0x40bb76`: `Microsoft\EdgeUpdate`

## pseudocode

```c
_DWORD *__stdcall sub_40BB5B(_DWORD *a1)
{
  int v1; // eax
  int v3; // [esp+4h] [ebp-4h]

  *a1 = 0;
  v1 = sub_4015FB();
  sub_401FBB(v1);
  sub_401CFA((wchar_t *)L"Microsoft\\EdgeUpdate");
  sub_40A943(1, a1);
  sub_4015D2(v3 - 16);
  return a1;
}

```

## disassembly

```asm
0x40bb5b  push    ebp
0x40bb5c  mov     ebp, esp
0x40bb5e  push    ecx
0x40bb5f  push    esi
0x40bb60  mov     esi, [ebp+arg_0]
0x40bb63  and     dword ptr [esi], 0
0x40bb66  call    sub_4015FB
0x40bb6b  push    eax
0x40bb6c  mov     ecx, esi
0x40bb6e  call    sub_401FBB
0x40bb73  push    esi
0x40bb74  push    1
0x40bb76  push    offset aMicrosoftEdgeu_1; "Microsoft\\EdgeUpdate"
0x40bb7b  lea     ecx, [ebp+var_4]
0x40bb7e  call    sub_401CFA
0x40bb83  push    1Ch
0x40bb85  mov     edx, eax
0x40bb87  pop     ecx
0x40bb88  call    sub_40A943
0x40bb8d  pop     ecx
0x40bb8e  pop     ecx
0x40bb8f  mov     ecx, [ebp+var_4]
0x40bb92  add     ecx, 0FFFFFFF0h
0x40bb95  call    sub_4015D2
0x40bb9a  mov     eax, esi
0x40bb9c  pop     esi
0x40bb9d  leave
0x40bb9e  retn    4
```
