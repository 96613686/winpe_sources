# _AfxIsComboBoxControl(HWND__ *,uint)

- ea: `0x18001c6d8`
- end: `0x18001c76e`
- name: `?_AfxIsComboBoxControl@@YAHPEAUHWND__@@I@Z`
- size: `150`
- prototype: `__int64 __fastcall(HWND hWnd, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007e20`
- `0x18001c630`
- `0x18002c9b0`

## callees

- `0x18001c6d8`
- `0x1800d1fe0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001c742`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18001c742`
- `USER32!GetWindowLongW` at `0x18001c700`
- `USER32!GetWindowLongW` at `0x18001c700`
- `USER32!GetClassNameW` at `0x18001c71b`
- `USER32!GetClassNameW` at `0x18001c71b`

## string_xrefs

- `0x18001c725`: `combobox`

## pseudocode

```c
_BOOL8 __fastcall _AfxIsComboBoxControl(HWND hWnd, int a2)
{
  WCHAR ClassName[12]; // [rsp+30h] [rbp-28h] BYREF

  if ( !hWnd || (GetWindowLongW(hWnd, -16) & 0xF) != a2 )
    return 0;
  GetClassNameW(hWnd, ClassName, 10);
  return CompareStringW(0x7Fu, 1u, ClassName, -1, L"combobox", -1) == 2;
}

```

## disassembly

```asm
0x18001c6d8  mov     [rsp+arg_8], rbx
0x18001c6dd  push    rdi
0x18001c6de  sub     rsp, 50h
0x18001c6e2  mov     rax, cs:__security_cookie
0x18001c6e9  xor     rax, rsp
0x18001c6ec  mov     [rsp+58h+var_10], rax
0x18001c6f1  mov     edi, edx
0x18001c6f3  mov     rbx, rcx
0x18001c6f6  test    rcx, rcx
0x18001c6f9  jz      short loc_18001C754
0x18001c6fb  mov     edx, 0FFFFFFF0h; nIndex
0x18001c700  call    cs:__imp_GetWindowLongW
0x18001c706  and     eax, 0Fh
0x18001c709  cmp     eax, edi
0x18001c70b  jnz     short loc_18001C754
0x18001c70d  mov     r8d, 0Ah; nMaxCount
0x18001c713  lea     rdx, [rsp+58h+ClassName]; lpClassName
0x18001c718  mov     rcx, rbx; hWnd
0x18001c71b  call    cs:__imp_GetClassNameW
0x18001c721  or      r9d, 0FFFFFFFFh; cchCount1
0x18001c725  lea     rax, aCombobox_0; "combobox"
0x18001c72c  mov     [rsp+58h+cchCount2], r9d; cchCount2
0x18001c731  lea     r8, [rsp+58h+ClassName]; lpString1
0x18001c736  mov     [rsp+58h+lpString2], rax; lpString2
0x18001c73b  lea     edx, [r9+2]; dwCmpFlags
0x18001c73f  lea     ecx, [rdx+7Eh]; Locale
0x18001c742  call    cs:__imp_CompareStringW
0x18001c748  xor     ecx, ecx
0x18001c74a  cmp     eax, 2
0x18001c74d  setz    cl
0x18001c750  mov     eax, ecx
0x18001c752  jmp     short loc_18001C756
0x18001c754  xor     eax, eax
0x18001c756  mov     rcx, [rsp+58h+var_10]
0x18001c75b  xor     rcx, rsp; StackCookie
0x18001c75e  call    __security_check_cookie
0x18001c763  mov     rbx, [rsp+58h+arg_8]
0x18001c768  add     rsp, 50h
0x18001c76c  pop     rdi
0x18001c76d  retn
```
