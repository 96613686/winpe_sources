# ValidAsyncInfoSignature(_ASYNC_EVENT_INFO *)

- ea: `0x180008fd0`
- end: `0x180009004`
- name: `?ValidAsyncInfoSignature@@YAHPEAU_ASYNC_EVENT_INFO@@@Z`
- size: `52`
- prototype: `_BOOL8 __fastcall(const wchar_t *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180009ba0`
- `0x180009dd0`
- `0x18000a140`
- `0x18000a2c0`
- `0x18000aa00`

## callees

- `0x180008fd0`
- `0x18003d4d6`

## pseudocode

```c
_BOOL8 __fastcall ValidAsyncInfoSignature(const wchar_t *a1)
{
  return a1 && qword_180043400 != (__int64 *)a1 && wcscmp_0(a1, L"KukiMuki") == 0;
}

```

## disassembly

```asm
0x180008fd0  sub     rsp, 28h
0x180008fd4  test    rcx, rcx
0x180008fd7  jz      short loc_180008FFC
0x180008fd9  lea     rax, qword_180043400
0x180008fe0  cmp     rax, rcx
0x180008fe3  jz      short loc_180008FFC
0x180008fe5  lea     rdx, aKukimuki; "KukiMuki"
0x180008fec  call    wcscmp_0
0x180008ff1  xor     ecx, ecx
0x180008ff3  test    eax, eax
0x180008ff5  setz    cl
0x180008ff8  mov     eax, ecx
0x180008ffa  jmp     short loc_180008FFE
0x180008ffc  xor     eax, eax
0x180008ffe  add     rsp, 28h
0x180009002  retn
```
