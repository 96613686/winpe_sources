# _ExpandPath

- ea: `0x18005d70c`
- end: `0x18005d7ae`
- name: `_ExpandPath`
- size: `162`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x18005d08c`

## callees

- `0x18005cd08`
- `0x18005d70c`
- `0x1800c6940`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d73f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d73f`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x18005d77c`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x18005d77c`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18005d735`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18005d735`

## pseudocode

```c
__int64 __fastcall ExpandPath(const WCHAR *a1, WCHAR *a2)
{
  signed int LastError; // eax
  int v4; // ebx
  WCHAR Dst[264]; // [rsp+30h] [rbp-228h] BYREF

  if ( !ExpandEnvironmentStringsW(a1, Dst, 0x105u) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_4;
  }
  Dst[260] = 0;
  v4 = PathCchCanonicalize(a2, 0x104u, Dst);
  if ( v4 < 0 )
  {
LABEL_4:
    Log_HREvent_33(v4);
    return (unsigned int)v4;
  }
  return 0;
}

```

## disassembly

```asm
0x18005d70c  push    rbx
0x18005d70e  sub     rsp, 250h
0x18005d715  mov     rax, cs:__security_cookie
0x18005d71c  xor     rax, rsp
0x18005d71f  mov     [rsp+258h+var_18], rax
0x18005d727  mov     rbx, rdx
0x18005d72a  mov     r8d, 105h; nSize
0x18005d730  lea     rdx, [rsp+258h+Dst]; lpDst
0x18005d735  call    cs:__imp_ExpandEnvironmentStringsW
0x18005d73b  test    eax, eax
0x18005d73d  jnz     short loc_18005D765
0x18005d73f  call    cs:__imp_GetLastError
0x18005d745  mov     ebx, eax
0x18005d747  test    eax, eax
0x18005d749  jle     short loc_18005D754
0x18005d74b  movzx   ebx, ax
0x18005d74e  or      ebx, 80070000h
0x18005d754  xor     edx, edx
0x18005d756  lea     r9d, [rdx+7Ah]
0x18005d75a  mov     ecx, ebx; int
0x18005d75c  call    Log_HREvent_33
0x18005d761  mov     eax, ebx
0x18005d763  jmp     short loc_18005D795
0x18005d765  xor     eax, eax
0x18005d767  lea     r8, [rsp+258h+Dst]; pszPathIn
0x18005d76c  mov     edx, 104h; cchPathOut
0x18005d771  mov     [rsp+258h+var_20], ax
0x18005d779  mov     rcx, rbx; pszPathOut
0x18005d77c  call    cs:__imp_PathCchCanonicalize
0x18005d782  mov     ebx, eax
0x18005d784  test    eax, eax
0x18005d786  jns     short loc_18005D793
0x18005d788  mov     edx, 1
0x18005d78d  lea     r9d, [rdx+7Dh]
0x18005d791  jmp     short loc_18005D75A
0x18005d793  xor     eax, eax
0x18005d795  mov     rcx, [rsp+258h+var_18]
0x18005d79d  xor     rcx, rsp; StackCookie
0x18005d7a0  call    __security_check_cookie
0x18005d7a5  add     rsp, 250h
0x18005d7ac  pop     rbx
0x18005d7ad  retn
```
