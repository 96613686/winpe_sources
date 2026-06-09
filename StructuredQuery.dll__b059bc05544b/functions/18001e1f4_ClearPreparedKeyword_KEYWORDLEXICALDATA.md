# ClearPreparedKeyword(KEYWORDLEXICALDATA *)

- ea: `0x18001e1f4`
- end: `0x18001e22c`
- name: `?ClearPreparedKeyword@@YAXPEAUKEYWORDLEXICALDATA@@@Z`
- size: `56`
- prototype: `void __fastcall(LPVOID *)`
- caller_count: `4`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001e110`
- `0x18001e688`
- `0x18001e7b8`
- `0x18002eda8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e200`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e211`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e200`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001e211`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ClearPreparedKeyword(LPVOID *a1)
{
  void *v2; // rcx

  CoTaskMemFree(*a1);
  v2 = a1[1];
  *a1 = 0;
  CoTaskMemFree(v2);
  a1[1] = 0;
  *((_DWORD *)a1 + 4) = 0;
}

```

## disassembly

```asm
0x18001e1f4  push    rbx
0x18001e1f6  sub     rsp, 20h
0x18001e1fa  mov     rbx, rcx
0x18001e1fd  mov     rcx, [rcx]; pv
0x18001e200  call    cs:__imp_CoTaskMemFree
0x18001e206  mov     rcx, [rbx+8]; pv
0x18001e20a  mov     qword ptr [rbx], 0
0x18001e211  call    cs:__imp_CoTaskMemFree
0x18001e217  mov     qword ptr [rbx+8], 0
0x18001e21f  mov     dword ptr [rbx+10h], 0
0x18001e226  add     rsp, 20h
0x18001e22a  pop     rbx
0x18001e22b  retn
```
