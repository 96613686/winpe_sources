# AdminElevate::LinktoSystemRestorePoint(void)

- ea: `0x18001e0d0`
- end: `0x18001e168`
- name: `?LinktoSystemRestorePoint@AdminElevate@@UEAAJXZ`
- size: `152`
- prototype: `__int64 __fastcall(AdminElevate *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18001e0d0`
- `0x18002d1ee`
- `0x18002d220`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001e10d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001e10d`
- `SHELL32!ShellExecuteW` at `0x18001e134`
- `SHELL32!ShellExecuteW` at `0x18001e134`

## string_xrefs

- `0x18001e106`: `%systemroot%\system32\rstrui.exe`

## pseudocode

```c
HINSTANCE __fastcall AdminElevate::LinktoSystemRestorePoint(AdminElevate *this)
{
  HINSTANCE result; // rax
  WCHAR Dst[264]; // [rsp+30h] [rbp-228h] BYREF

  memset_0(Dst, 0, 0x20Au);
  if ( !ExpandEnvironmentStringsW(L"%systemroot%\\system32\\rstrui.exe", Dst, 0x105u) )
    return 0;
  result = ShellExecuteW(0, 0, Dst, 0, 0, 10);
  if ( (__int64)result > 32 )
    return 0;
  if ( (int)result > 0 )
    return (HINSTANCE)((unsigned __int16)result | 0x80070000);
  return result;
}

```

## disassembly

```asm
0x18001e0d0  sub     rsp, 258h
0x18001e0d7  mov     rax, cs:__security_cookie
0x18001e0de  xor     rax, rsp
0x18001e0e1  mov     [rsp+258h+var_18], rax
0x18001e0e9  xor     edx, edx; Val
0x18001e0eb  lea     rcx, [rsp+258h+Dst]; void *
0x18001e0f0  mov     r8d, 20Ah; Size
0x18001e0f6  call    memset_0
0x18001e0fb  mov     r8d, 105h; nSize
0x18001e101  lea     rdx, [rsp+258h+Dst]; lpDst
0x18001e106  lea     rcx, aSystemrootSyst_0; "%systemroot%\\system32\\rstrui.exe"
0x18001e10d  call    cs:__imp_ExpandEnvironmentStringsW
0x18001e113  test    eax, eax
0x18001e115  jz      short loc_18001E14E
0x18001e117  mov     [rsp+258h+nShowCmd], 0Ah; nShowCmd
0x18001e11f  lea     r8, [rsp+258h+Dst]; lpFile
0x18001e124  xor     r9d, r9d; lpParameters
0x18001e127  mov     [rsp+258h+lpDirectory], 0; lpDirectory
0x18001e130  xor     edx, edx; lpOperation
0x18001e132  xor     ecx, ecx; hwnd
0x18001e134  call    cs:__imp_ShellExecuteW
0x18001e13a  cmp     rax, 20h ; ' '
0x18001e13e  jg      short loc_18001E14E
0x18001e140  test    eax, eax
0x18001e142  jle     short loc_18001E150
0x18001e144  movzx   eax, ax
0x18001e147  or      eax, 80070000h
0x18001e14c  jmp     short loc_18001E150
0x18001e14e  xor     eax, eax
0x18001e150  mov     rcx, [rsp+258h+var_18]
0x18001e158  xor     rcx, rsp; StackCookie
0x18001e15b  call    __security_check_cookie
0x18001e160  add     rsp, 258h
0x18001e167  retn
```
