# ThreadFreeTlsMsgBuffer(void)

- ea: `0x180001b00`
- end: `0x180001b4b`
- name: `?ThreadFreeTlsMsgBuffer@@YAXXZ`
- size: `75`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001280`

## callees

- `0x180001b00`
- `0x180014010`

## import_xrefs

- `KERNEL32!TlsSetValue` at `0x180001b3f`
- `KERNEL32!TlsGetValue` at `0x180001b0f`
- `KERNEL32!TlsGetValue` at `0x180001b0f`

## pseudocode

```c
void ThreadFreeTlsMsgBuffer(void)
{
  LPVOID Value; // r8

  if ( g_dwTlsMsgBuffIndex != -1 )
  {
    Value = TlsGetValue(g_dwTlsMsgBuffIndex);
    if ( Value )
      ((void (__fastcall *)(LPMALLOC, LPVOID))g_pMalloc->lpVtbl->Free)(g_pMalloc, Value);
    TlsSetValue(g_dwTlsMsgBuffIndex, 0);
  }
}

```

## disassembly

```asm
0x180001b00  sub     rsp, 28h
0x180001b04  mov     ecx, cs:?g_dwTlsMsgBuffIndex@@3KA; dwTlsIndex
0x180001b0a  cmp     ecx, 0FFFFFFFFh
0x180001b0d  jz      short loc_180001B46
0x180001b0f  call    cs:__imp_TlsGetValue
0x180001b15  mov     r8, rax
0x180001b18  test    rax, rax
0x180001b1b  jz      short loc_180001B33
0x180001b1d  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x180001b24  mov     rdx, [rcx]
0x180001b27  mov     rax, [rdx+28h]
0x180001b2b  mov     rdx, r8
0x180001b2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b33  mov     ecx, cs:?g_dwTlsMsgBuffIndex@@3KA; ulong g_dwTlsMsgBuffIndex
0x180001b39  xor     edx, edx
0x180001b3b  add     rsp, 28h
0x180001b3f  jmp     cs:__imp_TlsSetValue
0x180001b46  add     rsp, 28h
0x180001b4a  retn
```
