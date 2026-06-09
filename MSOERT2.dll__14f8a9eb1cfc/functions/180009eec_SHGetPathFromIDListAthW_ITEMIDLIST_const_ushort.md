# SHGetPathFromIDListAthW(_ITEMIDLIST const *,ushort *)

- ea: `0x180009eec`
- end: `0x180009f80`
- name: `?SHGetPathFromIDListAthW@@YAHPEFBU_ITEMIDLIST@@PEAG@Z`
- size: `148`
- prototype: `__int64 __fastcall(LPCITEMIDLIST pidl, LPWSTR lpWideCharStr)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180009750`
- `0x18000a640`

## callees

- `0x180009eec`
- `0x180012fc0`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x180009f4d`
- `KERNEL32!MultiByteToWideChar` at `0x180009f4d`
- `SHELL32!SHGetPathFromIDListA` at `0x180009f26`
- `SHELL32!SHGetPathFromIDListA` at `0x180009f26`
- `SHELL32!SHGetPathFromIDListW` at `0x180009f11`
- `SHELL32!SHGetPathFromIDListW` at `0x180009f11`

## pseudocode

```c
__int64 __fastcall SHGetPathFromIDListAthW(LPCITEMIDLIST pidl, LPWSTR lpWideCharStr)
{
  unsigned int v4; // r8d
  CHAR pszPath[272]; // [rsp+30h] [rbp-128h] BYREF

  v4 = SHGetPathFromIDListW(pidl, lpWideCharStr);
  if ( !v4 )
  {
    v4 = SHGetPathFromIDListA(pidl, pszPath);
    if ( v4 )
      return MultiByteToWideChar(0, 0, pszPath, -1, lpWideCharStr, 260) != 0;
  }
  return v4;
}

```

## disassembly

```asm
0x180009eec  mov     [rsp+arg_10], rbx
0x180009ef1  push    rdi
0x180009ef2  sub     rsp, 150h
0x180009ef9  mov     rax, cs:__security_cookie
0x180009f00  xor     rax, rsp
0x180009f03  mov     [rsp+158h+var_18], rax
0x180009f0b  mov     rdi, rdx
0x180009f0e  mov     rbx, rcx
0x180009f11  call    cs:__imp_SHGetPathFromIDListW
0x180009f17  mov     r8d, eax
0x180009f1a  test    eax, eax
0x180009f1c  jnz     short loc_180009F5C
0x180009f1e  lea     rdx, [rsp+158h+pszPath]; pszPath
0x180009f23  mov     rcx, rbx; pidl
0x180009f26  call    cs:__imp_SHGetPathFromIDListA
0x180009f2c  mov     r8d, eax
0x180009f2f  test    eax, eax
0x180009f31  jz      short loc_180009F5C
0x180009f33  mov     [rsp+158h+cchWideChar], 104h; cchWideChar
0x180009f3b  lea     r8, [rsp+158h+pszPath]; lpMultiByteStr
0x180009f40  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180009f44  mov     [rsp+158h+lpWideCharStr], rdi; lpWideCharStr
0x180009f49  xor     edx, edx; dwFlags
0x180009f4b  xor     ecx, ecx; CodePage
0x180009f4d  call    cs:__imp_MultiByteToWideChar
0x180009f53  xor     r8d, r8d
0x180009f56  test    eax, eax
0x180009f58  setnz   r8b
0x180009f5c  mov     eax, r8d
0x180009f5f  mov     rcx, [rsp+158h+var_18]
0x180009f67  xor     rcx, rsp; StackCookie
0x180009f6a  call    __security_check_cookie
0x180009f6f  mov     rbx, [rsp+158h+arg_10]
0x180009f77  add     rsp, 150h
0x180009f7e  pop     rdi
0x180009f7f  retn
```
