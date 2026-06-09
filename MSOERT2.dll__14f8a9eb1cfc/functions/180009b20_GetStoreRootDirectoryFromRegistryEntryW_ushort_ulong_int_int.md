# GetStoreRootDirectoryFromRegistryEntryW(ushort *,ulong,int,int *)

- ea: `0x180009b20`
- end: `0x180009bd1`
- name: `?GetStoreRootDirectoryFromRegistryEntryW@@YAJPEAGKHPEAH@Z`
- size: `177`
- prototype: `__int64 __fastcall(LPCWSTR pszPath, unsigned int, int, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180009a50`
- `0x180009be0`

## callees

- `0x180004640`
- `0x180009b20`
- `0x180009cc0`
- `0x180012fc0`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsW` at `0x180009b6a`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180009b6a`
- `SHLWAPI!PathRemoveBackslashW` at `0x180009b90`
- `SHLWAPI!PathRemoveBackslashW` at `0x180009b90`

## pseudocode

```c
__int64 __fastcall GetStoreRootDirectoryFromRegistryEntryW(WCHAR *pszPath, unsigned int a2, int a3, int *a4)
{
  unsigned __int64 v4; // rdi
  __int64 result; // rax
  WCHAR Dst[264]; // [rsp+20h] [rbp-238h] BYREF

  v4 = a2;
  if ( !a4 )
    return 2147500035LL;
  if ( !pszPath || !a2 )
    return 2147942487LL;
  if ( !a3 )
  {
LABEL_8:
    PathRemoveBackslashW(pszPath);
    result = HrCreateDirectoryIfDoesntExistW(pszPath);
    *a4 = result == 1;
    return result;
  }
  if ( ExpandEnvironmentStringsW(pszPath, Dst, 0x104u) - 1 <= 0x103 )
  {
    result = StringCchCopyW(pszPath, v4, Dst);
    if ( (int)result < 0 )
      return result;
    goto LABEL_8;
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x180009b20  push    rbx
0x180009b22  push    rsi
0x180009b23  push    rdi
0x180009b24  sub     rsp, 240h
0x180009b2b  mov     rax, cs:__security_cookie
0x180009b32  xor     rax, rsp
0x180009b35  mov     [rsp+258h+var_28], rax
0x180009b3d  mov     edi, edx
0x180009b3f  mov     rsi, r9
0x180009b42  mov     rbx, rcx
0x180009b45  test    r9, r9
0x180009b48  jnz     short loc_180009B51
0x180009b4a  mov     eax, 80004003h
0x180009b4f  jmp     short loc_180009BB6
0x180009b51  test    rbx, rbx
0x180009b54  jz      short loc_180009BB1
0x180009b56  test    edx, edx
0x180009b58  jz      short loc_180009BB1
0x180009b5a  test    r8d, r8d
0x180009b5d  jz      short loc_180009B8D
0x180009b5f  mov     r8d, 104h; nSize
0x180009b65  lea     rdx, [rsp+258h+Dst]; lpDst
0x180009b6a  call    cs:__imp_ExpandEnvironmentStringsW
0x180009b70  dec     eax
0x180009b72  cmp     eax, 103h
0x180009b77  ja      short loc_180009BAA
0x180009b79  mov     rdx, rdi; unsigned __int64
0x180009b7c  lea     r8, [rsp+258h+Dst]; unsigned __int16 *
0x180009b81  mov     rcx, rbx; unsigned __int16 *
0x180009b84  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009b89  test    eax, eax
0x180009b8b  js      short loc_180009BB6
0x180009b8d  mov     rcx, rbx; pszPath
0x180009b90  call    cs:__imp_PathRemoveBackslashW
0x180009b96  mov     rcx, rbx; pszPath
0x180009b99  call    ?HrCreateDirectoryIfDoesntExistW@@YAJPEBG@Z; HrCreateDirectoryIfDoesntExistW(ushort const *)
0x180009b9e  xor     ecx, ecx
0x180009ba0  cmp     eax, 1
0x180009ba3  setz    cl
0x180009ba6  mov     [rsi], ecx
0x180009ba8  jmp     short loc_180009BB6
0x180009baa  mov     eax, 80004005h
0x180009baf  jmp     short loc_180009BB6
0x180009bb1  mov     eax, 80070057h
0x180009bb6  mov     rcx, [rsp+258h+var_28]
0x180009bbe  xor     rcx, rsp; StackCookie
0x180009bc1  call    __security_check_cookie
0x180009bc6  add     rsp, 240h
0x180009bcd  pop     rdi
0x180009bce  pop     rsi
0x180009bcf  pop     rbx
0x180009bd0  retn
```
