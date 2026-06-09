# GetCaptionFromPidl(_ITEMIDLIST *,ushort *,ulong)

- ea: `0x18000b6a8`
- end: `0x18000b75d`
- name: `?GetCaptionFromPidl@@YAJPEFAU_ITEMIDLIST@@PEAGK@Z`
- size: `181`
- prototype: `int(struct _ITEMIDLIST *, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000b2e0`

## callees

- `0x18000893c`
- `0x18000b6a8`
- `0x180016280`

## import_xrefs

- `USER32!LoadStringW` at `0x18000b70c`
- `USER32!LoadStringW` at `0x18000b70c`
- `SHELL32!SHGetNameFromIDList` at `0x18000b6e9`
- `SHELL32!SHGetNameFromIDList` at `0x18000b6e9`
- `ole32!CoTaskMemFree` at `0x18000b72b`
- `ole32!CoTaskMemFree` at `0x18000b72b`

## pseudocode

```c
__int64 __fastcall GetCaptionFromPidl(struct _ITEMIDLIST *a1, unsigned __int16 *a2)
{
  unsigned int v3; // ebx
  PWSTR ppszName; // [rsp+20h] [rbp-348h] BYREF
  WCHAR Buffer[400]; // [rsp+30h] [rbp-338h] BYREF

  ppszName = 0;
  if ( a1 && a2 )
  {
    v3 = -2147467259;
    if ( SHGetNameFromIDList(a1, SIGDN_NORMALDISPLAY, &ppszName) >= 0 )
    {
      LoadStringW(g_hInstance, 0x1394u, Buffer, 400);
      StringCchPrintfW(a2, 0x190u, Buffer, ppszName);
      CoTaskMemFree(ppszName);
      return 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v3;
}

```

## disassembly

```asm
0x18000b6a8  mov     [rsp+arg_10], rbx
0x18000b6ad  push    rdi
0x18000b6ae  sub     rsp, 360h
0x18000b6b5  mov     rax, cs:__security_cookie
0x18000b6bc  xor     rax, rsp
0x18000b6bf  mov     [rsp+368h+var_18], rax
0x18000b6c7  mov     [rsp+368h+ppszName], 0
0x18000b6d0  mov     rdi, rdx
0x18000b6d3  test    rcx, rcx
0x18000b6d6  jz      short loc_18000B735
0x18000b6d8  test    rdx, rdx
0x18000b6db  jz      short loc_18000B735
0x18000b6dd  lea     r8, [rsp+368h+ppszName]; ppszName
0x18000b6e2  xor     edx, edx; sigdnName
0x18000b6e4  mov     ebx, 80004005h
0x18000b6e9  call    cs:__imp_SHGetNameFromIDList
0x18000b6ef  test    eax, eax
0x18000b6f1  js      short loc_18000B73A
0x18000b6f3  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x18000b6fa  lea     r8, [rsp+368h+Buffer]; lpBuffer
0x18000b6ff  mov     ebx, 190h
0x18000b704  mov     edx, 1394h; uID
0x18000b709  mov     r9d, ebx; cchBufferMax
0x18000b70c  call    cs:__imp_LoadStringW
0x18000b712  mov     r9, [rsp+368h+ppszName]
0x18000b717  lea     r8, [rsp+368h+Buffer]; pszFormat
0x18000b71c  mov     edx, ebx; cchDest
0x18000b71e  mov     rcx, rdi; pszDest
0x18000b721  call    StringCchPrintfW
0x18000b726  mov     rcx, [rsp+368h+ppszName]; pv
0x18000b72b  call    cs:__imp_CoTaskMemFree
0x18000b731  xor     ebx, ebx
0x18000b733  jmp     short loc_18000B73A
0x18000b735  mov     ebx, 80070057h
0x18000b73a  mov     eax, ebx
0x18000b73c  mov     rcx, [rsp+368h+var_18]
0x18000b744  xor     rcx, rsp; StackCookie
0x18000b747  call    __security_check_cookie
0x18000b74c  mov     rbx, [rsp+368h+arg_10]
0x18000b754  add     rsp, 360h
0x18000b75b  pop     rdi
0x18000b75c  retn
```
