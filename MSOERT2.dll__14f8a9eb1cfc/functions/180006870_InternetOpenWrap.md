# InternetOpenWrap

- ea: `0x180006870`
- end: `0x1800068a5`
- name: `InternetOpenWrap`
- size: `53`
- prototype: `__int64 __fastcall(int, int, int, int, DWORD, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001c80`
- `0x180006870`

## import_xrefs

- `WININET!InternetOpenA` at `0x180006880`
- `WININET!InternetOpenA` at `0x180006880`

## pseudocode

```c
__int64 __fastcall InternetOpenWrap(
        const CHAR *a1,
        DWORD a2,
        const CHAR *a3,
        const CHAR *a4,
        DWORD dwFlags,
        _QWORD *a6)
{
  unsigned int v6; // ebx
  HINTERNET v7; // rcx

  v6 = 0;
  v7 = InternetOpenA(a1, a2, a3, a4, dwFlags);
  *a6 = v7;
  if ( !v7 )
    return (unsigned int)HrGetLastError();
  return v6;
}

```

## disassembly

```asm
0x180006870  push    rbx
0x180006872  sub     rsp, 30h
0x180006876  mov     eax, [rsp+38h+arg_20]
0x18000687a  xor     ebx, ebx
0x18000687c  mov     [rsp+38h+dwFlags], eax; dwFlags
0x180006880  call    cs:__imp_InternetOpenA
0x180006886  mov     rcx, rax
0x180006889  mov     rax, [rsp+38h+arg_28]
0x18000688e  mov     [rax], rcx
0x180006891  test    rcx, rcx
0x180006894  jnz     short loc_18000689D
0x180006896  call    ?HrGetLastError@@YAJXZ; HrGetLastError(void)
0x18000689b  mov     ebx, eax
0x18000689d  mov     eax, ebx
0x18000689f  add     rsp, 30h
0x1800068a3  pop     rbx
0x1800068a4  retn
```
