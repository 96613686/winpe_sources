# sub_40BBA1

- ea: `0x40bba1`
- end: `0x40bbe7`
- name: `sub_40BBA1`
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

- `0x40bbbc`: `Microsoft\EdgeUpdate`

## pseudocode

```c
_DWORD *__stdcall sub_40BBA1(_DWORD *a1)
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
0x40bba1  push    ebp
0x40bba2  mov     ebp, esp
0x40bba4  push    ecx
0x40bba5  push    esi
0x40bba6  mov     esi, [ebp+arg_0]
0x40bba9  and     dword ptr [esi], 0
0x40bbac  call    sub_4015FB
0x40bbb1  push    eax
0x40bbb2  mov     ecx, esi
0x40bbb4  call    sub_401FBB
0x40bbb9  push    esi
0x40bbba  push    1
0x40bbbc  push    offset aMicrosoftEdgeu_1; "Microsoft\\EdgeUpdate"
0x40bbc1  lea     ecx, [ebp+var_4]
0x40bbc4  call    sub_401CFA
0x40bbc9  push    26h ; '&'
0x40bbcb  mov     edx, eax
0x40bbcd  pop     ecx
0x40bbce  call    sub_40A943
0x40bbd3  pop     ecx
0x40bbd4  pop     ecx
0x40bbd5  mov     ecx, [ebp+var_4]
0x40bbd8  add     ecx, 0FFFFFFF0h
0x40bbdb  call    sub_4015D2
0x40bbe0  mov     eax, esi
0x40bbe2  pop     esi
0x40bbe3  leave
0x40bbe4  retn    4
```
