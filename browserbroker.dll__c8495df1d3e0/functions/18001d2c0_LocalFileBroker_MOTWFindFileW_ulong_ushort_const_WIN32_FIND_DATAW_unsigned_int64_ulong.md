# LocalFileBroker::MOTWFindFileW(ulong,ushort const *,_WIN32_FIND_DATAW *,unsigned __int64 *,ulong *)

- ea: `0x18001d2c0`
- end: `0x18001d447`
- name: `?MOTWFindFileW@LocalFileBroker@@UEAAJKPEBGPEAU_WIN32_FIND_DATAW@@PEA_KPEAK@Z`
- size: `391`
- prototype: `int(LocalFileBroker *__hidden this, unsigned int, const unsigned __int16 *, struct _WIN32_FIND_DATAW *, unsigned __int64 *, unsigned int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002ce0`
- `0x1800037ac`
- `0x18000e428`
- `0x18001d2c0`
- `0x18001e08c`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcspbrk` at `0x18001d343`
- `api-ms-win-crt-string-l1-1-0!wcspbrk` at `0x18001d343`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001d3d3`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001d3e5`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001d3d3`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x18001d3e5`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001d392`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18001d392`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001d3ae`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18001d3ae`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x18001d3be`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x18001d3be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d361`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d361`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001d358`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18001d358`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001d37d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001d37d`

## pseudocode

```c
__int64 __fastcall LocalFileBroker::MOTWFindFileW(
        LocalFileBroker *this,
        int a2,
        const unsigned __int16 *a3,
        struct _WIN32_FIND_DATAW *a4,
        unsigned __int64 *a5,
        unsigned int *a6)
{
  int PIC; // esi
  HANDLE FirstFileW; // rbx
  WCHAR *i; // rcx
  wchar_t *v12; // rax
  unsigned int v14[4]; // [rsp+20h] [rbp-258h] BYREF
  WCHAR pszPath[264]; // [rsp+30h] [rbp-248h] BYREF

  v14[0] = 0;
  *a5 = -1;
  *a6 = 5;
  PIC = BrokerAuthenticateAttachedCallerGetPIC(2, v14);
  if ( PIC >= 0 )
  {
    if ( a2 )
    {
      return (unsigned int)-2147467260;
    }
    else if ( wcspbrk(a3, L"?*") )
    {
      *a6 = 5;
    }
    else
    {
      FirstFileW = FindFirstFileW(a3, a4);
      *a6 = GetLastError();
      if ( FirstFileW != (HANDLE)-1LL )
      {
        *a5 = 0;
        FindClose(FirstFileW);
        _o_wcscpy_s(pszPath, 260, a3);
        for ( i = pszPath; ; i = v12 )
        {
          v12 = wcschr(i, 0x2Fu);
          if ( !v12 )
            break;
          *v12 = 92;
        }
        PathRemoveFileSpecW(pszPath);
        _o_wcscat_s(pszPath, 260, L"\\");
        _o_wcscat_s(pszPath, 260, a4->cFileName);
        if ( !(unsigned __int8)FileAccessAllowed(pszPath) )
        {
          *a5 = -1;
          *a6 = 5;
          memset_0(a4, 0, sizeof(struct _WIN32_FIND_DATAW));
        }
      }
    }
  }
  return (unsigned int)PIC;
}

```

## disassembly

```asm
0x18001d2c0  mov     [rsp+arg_0], rbx
0x18001d2c5  push    rbp
0x18001d2c6  push    rsi
0x18001d2c7  push    rdi
0x18001d2c8  push    r14
0x18001d2ca  push    r15
0x18001d2cc  sub     rsp, 250h
0x18001d2d3  mov     rax, cs:__security_cookie
0x18001d2da  xor     rax, rsp
0x18001d2dd  mov     [rsp+278h+var_38], rax
0x18001d2e5  mov     r15, [rsp+278h+arg_20]
0x18001d2ed  mov     ebx, edx
0x18001d2ef  mov     rdi, [rsp+278h+arg_28]
0x18001d2f7  lea     rdx, [rsp+278h+var_258]; unsigned int *
0x18001d2fc  mov     ecx, 2; unsigned int
0x18001d301  mov     [rsp+278h+var_258], 0
0x18001d309  mov     r14, r9
0x18001d30c  mov     rbp, r8
0x18001d30f  mov     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x18001d316  mov     dword ptr [rdi], 5
0x18001d31c  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x18001d321  mov     esi, eax
0x18001d323  test    eax, eax
0x18001d325  js      loc_18001D41E
0x18001d32b  test    ebx, ebx
0x18001d32d  jz      short loc_18001D339
0x18001d32f  mov     esi, 80004004h
0x18001d334  jmp     loc_18001D41E
0x18001d339  lea     rdx, Control; "?*"
0x18001d340  mov     rcx, rbp; String
0x18001d343  call    cs:__imp_wcspbrk
0x18001d349  test    rax, rax
0x18001d34c  jnz     loc_18001D418
0x18001d352  mov     rdx, r14; lpFindFileData
0x18001d355  mov     rcx, rbp; lpFileName
0x18001d358  call    cs:__imp_FindFirstFileW
0x18001d35e  mov     rbx, rax
0x18001d361  call    cs:__imp_GetLastError
0x18001d367  mov     [rdi], eax
0x18001d369  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18001d36d  jz      loc_18001D41E
0x18001d373  mov     rcx, rbx; hFindFile
0x18001d376  mov     qword ptr [r15], 0
0x18001d37d  call    cs:__imp_FindClose
0x18001d383  mov     r8, rbp
0x18001d386  lea     rcx, [rsp+278h+pszPath]
0x18001d38b  mov     ebp, 104h
0x18001d390  mov     edx, ebp
0x18001d392  call    cs:__imp__o_wcscpy_s
0x18001d398  lea     rcx, [rsp+278h+pszPath]
0x18001d39d  mov     ebx, 2Fh ; '/'
0x18001d3a2  jmp     short loc_18001D3AC
0x18001d3a4  mov     word ptr [rax], 5Ch ; '\'
0x18001d3a9  mov     rcx, rax; Str
0x18001d3ac  mov     edx, ebx; Ch
0x18001d3ae  call    cs:__imp_wcschr
0x18001d3b4  test    rax, rax
0x18001d3b7  jnz     short loc_18001D3A4
0x18001d3b9  lea     rcx, [rsp+278h+pszPath]; pszPath
0x18001d3be  call    cs:__imp_PathRemoveFileSpecW
0x18001d3c4  lea     r8, SubBlock; "\\"
0x18001d3cb  mov     rdx, rbp
0x18001d3ce  lea     rcx, [rsp+278h+pszPath]
0x18001d3d3  call    cs:__imp__o_wcscat_s
0x18001d3d9  lea     r8, [r14+2Ch]
0x18001d3dd  mov     rdx, rbp
0x18001d3e0  lea     rcx, [rsp+278h+pszPath]
0x18001d3e5  call    cs:__imp__o_wcscat_s
0x18001d3eb  lea     rcx, [rsp+278h+pszPath]
0x18001d3f0  call    _FileAccessAllowed
0x18001d3f5  test    al, al
0x18001d3f7  jnz     short loc_18001D41E
0x18001d3f9  mov     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x18001d400  xor     edx, edx; Val
0x18001d402  mov     r8d, 250h; Size
0x18001d408  mov     dword ptr [rdi], 5
0x18001d40e  mov     rcx, r14; void *
0x18001d411  call    memset_0
0x18001d416  jmp     short loc_18001D41E
0x18001d418  mov     dword ptr [rdi], 5
0x18001d41e  mov     eax, esi
0x18001d420  mov     rcx, [rsp+278h+var_38]
0x18001d428  xor     rcx, rsp; StackCookie
0x18001d42b  call    __security_check_cookie
0x18001d430  mov     rbx, [rsp+278h+arg_0]
0x18001d438  add     rsp, 250h
0x18001d43f  pop     r15
0x18001d441  pop     r14
0x18001d443  pop     rdi
0x18001d444  pop     rsi
0x18001d445  pop     rbp
0x18001d446  retn
```
