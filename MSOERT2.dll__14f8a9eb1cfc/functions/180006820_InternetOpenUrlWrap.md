# InternetOpenUrlWrap

- ea: `0x180006820`
- end: `0x18000685f`
- name: `InternetOpenUrlWrap`
- size: `63`
- prototype: `__int64 __fastcall(int, int, int, int, DWORD, DWORD_PTR, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001c80`
- `0x180006820`

## import_xrefs

- `WININET!InternetOpenUrlW` at `0x18000683a`
- `WININET!InternetOpenUrlW` at `0x18000683a`

## pseudocode

```c
__int64 __fastcall InternetOpenUrlWrap(
        void *a1,
        const WCHAR *a2,
        const WCHAR *a3,
        DWORD a4,
        DWORD dwFlags,
        DWORD_PTR dwContext,
        _QWORD *a7)
{
  unsigned int v7; // ebx
  HINTERNET v8; // rcx

  v7 = 0;
  v8 = InternetOpenUrlW(a1, a2, a3, a4, dwFlags, dwContext);
  *a7 = v8;
  if ( !v8 )
    return (unsigned int)HrGetLastError();
  return v7;
}

```

## disassembly

```asm
0x180006820  push    rbx
0x180006822  sub     rsp, 30h
0x180006826  mov     rax, [rsp+38h+arg_28]
0x18000682b  xor     ebx, ebx
0x18000682d  mov     [rsp+38h+dwContext], rax; dwContext
0x180006832  mov     eax, [rsp+38h+arg_20]
0x180006836  mov     [rsp+38h+dwFlags], eax; dwFlags
0x18000683a  call    cs:__imp_InternetOpenUrlW
0x180006840  mov     rcx, rax
0x180006843  mov     rax, [rsp+38h+arg_30]
0x180006848  mov     [rax], rcx
0x18000684b  test    rcx, rcx
0x18000684e  jnz     short loc_180006857
0x180006850  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x180006855  mov     ebx, eax
0x180006857  mov     eax, ebx
0x180006859  add     rsp, 30h
0x18000685d  pop     rbx
0x18000685e  retn
```
