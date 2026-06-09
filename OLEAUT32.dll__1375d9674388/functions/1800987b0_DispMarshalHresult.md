# DispMarshalHresult

- ea: `0x1800987b0`
- end: `0x1800987ce`
- name: `DispMarshalHresult`
- size: `30`
- prototype: ``
- caller_count: `46`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18004bfcc`
- `0x180078910`
- `0x1800816fc`
- `0x180081b4c`
- `0x180081c60`
- `0x180081cec`
- `0x180082294`
- `0x180082324`
- `0x180082534`
- `0x1800825d0`
- `0x180082868`
- `0x180082974`
- `0x180082a40`
- `0x180082b44`
- `0x180082d08`
- `0x180082fb4`
- `0x1800830ec`
- `0x18008322c`
- `0x18008332c`
- `0x180083464`
- `0x180083524`
- `0x180083740`
- `0x1800838b8`
- `0x18008399c`
- `0x180083a54`
- `0x180083b94`
- `0x180083c24`
- `0x180083ca8`
- `0x180083de0`
- `0x180083f2c`
- `0x180083ff0`
- `0x1800844b8`
- `0x180084748`
- `0x180084850`
- `0x180084964`
- `0x180084c4c`
- `0x180084ce0`
- `0x180084d94`
- `0x180084e28`
- `0x180084ef8`
- `0x180084ff4`
- `0x1800852f4`
- `0x180085524`
- `0x18008575c`
- `0x180085aa4`
- `0x180098304`

## callees

- `0x180098680`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalHresult` at `0x1800987c7`

## pseudocode

```c
HRESULT __fastcall DispMarshalHresult(__int64 a1, int a2)
{
  HRESULT v2; // eax
  LPSTREAM v3; // r8

  v2 = Win16ScodeFromWin32Scode(a2);
  return CoMarshalHresult(v3, v2);
}

```

## disassembly

```asm
0x1800987b0  sub     rsp, 28h
0x1800987b4  mov     r8, rcx
0x1800987b7  mov     ecx, edx; int
0x1800987b9  call    ?Win16ScodeFromWin32Scode@@YAJJ@Z; Win16ScodeFromWin32Scode(long)
0x1800987be  mov     edx, eax
0x1800987c0  mov     rcx, r8
0x1800987c3  add     rsp, 28h
0x1800987c7  jmp     cs:__imp_CoMarshalHresult
```
