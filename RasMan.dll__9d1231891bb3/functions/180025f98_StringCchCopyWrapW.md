# StringCchCopyWrapW

- ea: `0x180025f98`
- end: `0x180025fdc`
- name: `StringCchCopyWrapW`
- size: `68`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180023618`
- `0x180024d88`
- `0x180025508`
- `0x180025940`
- `0x180025e60`

## callees

- `0x1800251ac`
- `0x180025f98`

## import_xrefs

- `rtutils!TracePrintfExA` at `0x180025fce`
- `rtutils!TracePrintfExA` at `0x180025fce`

## string_xrefs

- `0x180025fc2`: `StringCchCopy failed due to error 0x%x`

## pseudocode

```c
__int64 __fastcall StringCchCopyWrapW(wchar_t *a1, size_t a2, const wchar_t *a3, STRSAFE_LPWSTR *a4)
{
  unsigned int v4; // ebx
  HRESULT v5; // eax
  size_t *v7; // [rsp+20h] [rbp-18h]

  v4 = 0;
  v5 = StringCchCopyExW(a1, a2, a3, a4, v7, 0x900u);
  if ( v5 < 0 )
  {
    v4 = (unsigned __int16)v5;
    if ( g_dwTraceId != -1 )
      TracePrintfExA(g_dwTraceId, 0xCu, "StringCchCopy failed due to error 0x%x", v5);
  }
  return v4;
}

```

## disassembly

```asm
0x180025f98  push    rbx
0x180025f9a  sub     rsp, 30h
0x180025f9e  xor     ebx, ebx
0x180025fa0  mov     [rsp+38h+dwFlags], 900h; dwFlags
0x180025fa8  call    StringCchCopyExW
0x180025fad  test    eax, eax
0x180025faf  jns     short loc_180025FD4
0x180025fb1  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180025fb7  movzx   ebx, ax
0x180025fba  cmp     ecx, 0FFFFFFFFh
0x180025fbd  jz      short loc_180025FD4
0x180025fbf  mov     r9d, eax
0x180025fc2  lea     r8, aStringcchcopyF; "StringCchCopy failed due to error 0x%x"
0x180025fc9  mov     edx, 0Ch; dwFlags
0x180025fce  call    cs:__imp_TracePrintfExA
0x180025fd4  mov     eax, ebx
0x180025fd6  add     rsp, 30h
0x180025fda  pop     rbx
0x180025fdb  retn
```
