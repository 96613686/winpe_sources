# DelNodeRunDLL32W

- ea: `0x18000b1d0`
- end: `0x18000b230`
- name: `DelNodeRunDLL32W`
- size: `96`
- prototype: `HRESULT __stdcall(HWND hwnd, HINSTANCE hInstance, LPWSTR pszParms, INT nShow)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180005660`

## callees

- `0x180006af8`
- `0x18000b1d0`
- `0x18000b240`

## import_xrefs

- `msvcrt!_wtol` at `0x18000b21b`
- `msvcrt!_wtol` at `0x18000b21b`

## pseudocode

```c
HRESULT __stdcall DelNodeRunDLL32W(HWND hwnd, HINSTANCE hInstance, LPWSTR pszParms, INT nShow)
{
  unsigned __int16 *StringField; // rbx
  unsigned __int16 *v5; // rax
  unsigned __int16 *v7; // [rsp+40h] [rbp+18h] BYREF

  v7 = pszParms;
  StringField = GetStringField(&v7, L",", 34, 1);
  v5 = GetStringField(&v7, L",", 34, 1);
  if ( v5 )
    LODWORD(v5) = _wtol(v5);
  return DelNodeW(StringField, (DWORD)v5);
}

```

## disassembly

```asm
0x18000b1d0  mov     [rsp+arg_10], r8
0x18000b1d5  push    rbx
0x18000b1d6  sub     rsp, 20h
0x18000b1da  mov     r8d, 22h ; '"'; unsigned __int16
0x18000b1e0  lea     rdx, asc_18001E134; ","
0x18000b1e7  lea     rcx, [rsp+28h+arg_10]; unsigned __int16 **
0x18000b1ec  lea     r9d, [r8-21h]; int
0x18000b1f0  call    ?GetStringField@@YAPEAGPEAPEAGPEBGGH@Z; GetStringField(ushort * *,ushort const *,ushort,int)
0x18000b1f5  mov     r8d, 22h ; '"'; unsigned __int16
0x18000b1fb  lea     rdx, asc_18001E134; ","
0x18000b202  lea     rcx, [rsp+28h+arg_10]; unsigned __int16 **
0x18000b207  mov     rbx, rax
0x18000b20a  lea     r9d, [r8-21h]; int
0x18000b20e  call    ?GetStringField@@YAPEAGPEAPEAGPEBGGH@Z; GetStringField(ushort * *,ushort const *,ushort,int)
0x18000b213  test    rax, rax
0x18000b216  jz      short loc_18000B221
0x18000b218  mov     rcx, rax; String
0x18000b21b  call    cs:__imp__wtol
0x18000b221  mov     edx, eax
0x18000b223  mov     rcx, rbx
0x18000b226  add     rsp, 20h
0x18000b22a  pop     rbx
0x18000b22b  jmp     DelNodeW
```
