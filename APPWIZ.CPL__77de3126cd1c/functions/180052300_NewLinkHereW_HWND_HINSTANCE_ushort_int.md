# NewLinkHereW(HWND__ *,HINSTANCE__ *,ushort *,int)

- ea: `0x180052300`
- end: `0x1800523ca`
- name: `?NewLinkHereW@@YAXPEAUHWND__@@PEAUHINSTANCE__@@PEAGH@Z`
- size: `202`
- prototype: `void __fastcall(HWND, HINSTANCE, unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops`

## callees

- `0x18000791c`
- `0x180052300`
- `0x180052dd0`
- `0x1800582a2`
- `0x1800582e0`
- `0x1800583a0`

## import_xrefs

- `SHLWAPI!PathFileExistsW` at `0x180052388`
- `SHLWAPI!PathFileExistsW` at `0x180052388`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18005236f`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18005236f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800523a3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800523a3`

## pseudocode

```c
void __fastcall NewLinkHereW(HWND a1, HINSTANCE a2, unsigned __int16 *a3)
{
  HWND v5; // [rsp+20h] [rbp-1138h] BYREF
  int v6; // [rsp+28h] [rbp-1130h]
  WCHAR *v7; // [rsp+A60h] [rbp-6F8h]
  unsigned __int16 *v8; // [rsp+D00h] [rbp-458h]
  WCHAR pszPath[264]; // [rsp+F30h] [rbp-228h] BYREF

  memset_0(&v5, 0, 0xF08u);
  v5 = a1;
  v6 = 32;
  v8 = a3;
  StringCchCopyW(pszPath, 0x104u, a3);
  PathRemoveFileSpecW(pszPath);
  v7 = pszPath;
  if ( PathFileExistsW(a3) )
  {
    if ( !(unsigned int)LinkWizard((struct _WIZDATA *)&v5) )
      DeleteFileW(a3);
  }
}

```

## disassembly

```asm
0x180052300  mov     [rsp+arg_8], rbx
0x180052305  push    rdi
0x180052306  mov     eax, 1150h
0x18005230b  call    _alloca_probe
0x180052310  sub     rsp, rax
0x180052313  mov     rax, cs:__security_cookie
0x18005231a  xor     rax, rsp
0x18005231d  mov     [rsp+1158h+var_18], rax
0x180052325  mov     rdi, r8
0x180052328  mov     rbx, rcx
0x18005232b  mov     r8d, 0F08h; Size
0x180052331  lea     rcx, [rsp+1158h+var_1138]; void *
0x180052336  xor     edx, edx; Val
0x180052338  call    memset_0
0x18005233d  mov     r8, rdi; unsigned __int16 *
0x180052340  mov     [rsp+1158h+var_1138], rbx
0x180052345  mov     edx, 104h; unsigned __int64
0x18005234a  mov     [rsp+1158h+var_1130], 20h ; ' '
0x180052352  lea     rcx, [rsp+1158h+pszPath]; unsigned __int16 *
0x18005235a  mov     [rsp+1158h+var_458], rdi
0x180052362  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180052367  lea     rcx, [rsp+1158h+pszPath]; pszPath
0x18005236f  call    cs:__imp_PathRemoveFileSpecW
0x180052375  lea     rax, [rsp+1158h+pszPath]
0x18005237d  mov     rcx, rdi; pszPath
0x180052380  mov     [rsp+1158h+var_6F8], rax
0x180052388  call    cs:__imp_PathFileExistsW
0x18005238e  test    eax, eax
0x180052390  jz      short loc_1800523A9
0x180052392  lea     rcx, [rsp+1158h+var_1138]; struct _WIZDATA *
0x180052397  call    LinkWizard
0x18005239c  test    eax, eax
0x18005239e  jnz     short loc_1800523A9
0x1800523a0  mov     rcx, rdi; lpFileName
0x1800523a3  call    cs:__imp_DeleteFileW
0x1800523a9  mov     rcx, [rsp+1158h+var_18]
0x1800523b1  xor     rcx, rsp; StackCookie
0x1800523b4  call    __security_check_cookie
0x1800523b9  mov     rbx, [rsp+1158h+arg_8]
0x1800523c1  add     rsp, 1150h
0x1800523c8  pop     rdi
0x1800523c9  retn
```
