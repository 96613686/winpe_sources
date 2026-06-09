# _ExpandPath(ushort const *,ushort *)

- ea: `0x18005262c`
- end: `0x1800526c4`
- name: `?_ExpandPath@@YAJPEBGPEAG@Z`
- size: `152`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x180052320`

## callees

- `0x180052258`
- `0x18005262c`
- `0x1800c6940`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005265f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005265f`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x180052692`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x180052692`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180052655`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180052655`

## pseudocode

```c
__int64 __fastcall _ExpandPath(const unsigned __int16 *a1, unsigned __int16 *a2)
{
  signed int LastError; // eax
  int v4; // ebx
  WCHAR Dst[264]; // [rsp+30h] [rbp-228h] BYREF

  if ( !ExpandEnvironmentStringsW(a1, Dst, 0x104u) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_4;
  }
  v4 = PathCchCanonicalize(a2, 0x104u, Dst);
  if ( v4 < 0 )
  {
LABEL_4:
    Log_HREvent_28(v4);
    return (unsigned int)v4;
  }
  return 0;
}

```

## disassembly

```asm
0x18005262c  push    rbx
0x18005262e  sub     rsp, 250h
0x180052635  mov     rax, cs:__security_cookie
0x18005263c  xor     rax, rsp
0x18005263f  mov     [rsp+258h+var_18], rax
0x180052647  mov     rbx, rdx
0x18005264a  mov     r8d, 104h; nSize
0x180052650  lea     rdx, [rsp+258h+Dst]; lpDst
0x180052655  call    cs:__imp_ExpandEnvironmentStringsW
0x18005265b  test    eax, eax
0x18005265d  jnz     short loc_180052685
0x18005265f  call    cs:__imp_GetLastError
0x180052665  mov     ebx, eax
0x180052667  test    eax, eax
0x180052669  jle     short loc_180052674
0x18005266b  movzx   ebx, ax
0x18005266e  or      ebx, 80070000h
0x180052674  xor     edx, edx
0x180052676  lea     r9d, [rdx+54h]
0x18005267a  mov     ecx, ebx; int
0x18005267c  call    Log_HREvent_28
0x180052681  mov     eax, ebx
0x180052683  jmp     short loc_1800526AB
0x180052685  lea     r8, [rsp+258h+Dst]; pszPathIn
0x18005268a  mov     edx, 104h; cchPathOut
0x18005268f  mov     rcx, rbx; pszPathOut
0x180052692  call    cs:__imp_PathCchCanonicalize
0x180052698  mov     ebx, eax
0x18005269a  test    eax, eax
0x18005269c  jns     short loc_1800526A9
0x18005269e  mov     edx, 1
0x1800526a3  lea     r9d, [rdx+56h]
0x1800526a7  jmp     short loc_18005267A
0x1800526a9  xor     eax, eax
0x1800526ab  mov     rcx, [rsp+258h+var_18]
0x1800526b3  xor     rcx, rsp; StackCookie
0x1800526b6  call    __security_check_cookie
0x1800526bb  add     rsp, 250h
0x1800526c2  pop     rbx
0x1800526c3  retn
```
