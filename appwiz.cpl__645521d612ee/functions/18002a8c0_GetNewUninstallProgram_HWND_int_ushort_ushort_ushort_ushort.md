# GetNewUninstallProgram(HWND__ *,int,ushort *,ushort *,ushort * *,ushort * *)

- ea: `0x18002a8c0`
- end: `0x18002a9c7`
- name: `?GetNewUninstallProgram@@YAJPEAUHWND__@@HPEAG1PEAPEAG2@Z`
- size: `263`
- prototype: `__int64 __fastcall(HWND, int, unsigned __int16 *, unsigned __int16 *, PWSTR *ppszApplication, PWSTR *ppszParameters)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002b890`

## callees

- `0x180007960`
- `0x18002a8c0`
- `0x180055e8c`
- `0x1800582e0`

## import_xrefs

- `SHELL32!SHEvaluateSystemCommandTemplate` at `0x18002a994`
- `SHELL32!SHEvaluateSystemCommandTemplate` at `0x18002a994`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002a91e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002a91e`

## pseudocode

```c
__int64 __fastcall GetNewUninstallProgram(
        HWND a1,
        int a2,
        unsigned __int16 *a3,
        unsigned __int16 *a4,
        PWSTR *ppszApplication,
        PWSTR *ppszParameters)
{
  int v10; // ebx
  __int64 v11; // rcx
  WCHAR *v13; // [rsp+30h] [rbp-478h] BYREF
  int v14; // [rsp+38h] [rbp-470h]
  int v15; // [rsp+3Ch] [rbp-46Ch]
  WCHAR pszCmdTemplate[264]; // [rsp+40h] [rbp-468h] BYREF
  WCHAR Buffer[264]; // [rsp+250h] [rbp-258h] BYREF

  v10 = -2147467259;
  if ( LoadStringW(g_hinst, 0x7FAu, Buffer, 260) )
  {
    v10 = StringCchPrintfW(pszCmdTemplate, 0x104u, Buffer, a4, a3);
    if ( v10 >= 0 )
    {
      v15 = 0;
      v13 = pszCmdTemplate;
      v14 = a2;
      if ( SHFusionDialogBoxParam(v11, 306, a1, NewUninstallProc, &v13) )
        return (unsigned int)SHEvaluateSystemCommandTemplate(pszCmdTemplate, ppszApplication, 0, ppszParameters);
      else
        return (unsigned int)-2147467259;
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002a8c0  push    rbx
0x18002a8c2  push    rbp
0x18002a8c3  push    rsi
0x18002a8c4  push    rdi
0x18002a8c5  push    r12
0x18002a8c7  push    r14
0x18002a8c9  push    r15
0x18002a8cb  sub     rsp, 470h
0x18002a8d2  mov     rax, cs:__security_cookie
0x18002a8d9  xor     rax, rsp
0x18002a8dc  mov     [rsp+4A8h+var_48], rax
0x18002a8e4  mov     rdi, [rsp+4A8h+ppszApplication]
0x18002a8ec  mov     r12, r9
0x18002a8ef  mov     rsi, [rsp+4A8h+ppszParameters]
0x18002a8f7  mov     r15, r8
0x18002a8fa  mov     ebp, edx
0x18002a8fc  lea     r8, [rsp+4A8h+Buffer]; lpBuffer
0x18002a904  mov     r14, rcx
0x18002a907  mov     r9d, 104h; cchBufferMax
0x18002a90d  mov     rcx, cs:g_hinst; hInstance
0x18002a914  mov     edx, 7FAh; uID
0x18002a919  mov     ebx, 80004005h
0x18002a91e  call    cs:__imp_LoadStringW
0x18002a924  test    eax, eax
0x18002a926  jz      short loc_18002A9A3
0x18002a928  mov     r9, r12
0x18002a92b  mov     [rsp+4A8h+var_488], r15
0x18002a930  lea     r8, [rsp+4A8h+Buffer]; unsigned __int16 *
0x18002a938  mov     edx, 104h; unsigned __int64
0x18002a93d  lea     rcx, [rsp+4A8h+pszCmdTemplate]; unsigned __int16 *
0x18002a942  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002a947  mov     ebx, eax
0x18002a949  test    eax, eax
0x18002a94b  js      short loc_18002A9A3
0x18002a94d  lea     rax, [rsp+4A8h+pszCmdTemplate]
0x18002a952  mov     [rsp+4A8h+var_46C], 0
0x18002a95a  mov     [rsp+4A8h+var_478], rax
0x18002a95f  lea     r9, ?NewUninstallProc@@YA_JPEAUHWND__@@I_K_J@Z; NewUninstallProc(HWND__ *,uint,unsigned __int64,__int64)
0x18002a966  lea     rax, [rsp+4A8h+var_478]
0x18002a96b  mov     [rsp+4A8h+var_470], ebp
0x18002a96f  mov     r8, r14
0x18002a972  mov     [rsp+4A8h+var_488], rax
0x18002a977  mov     edx, 132h
0x18002a97c  call    SHFusionDialogBoxParam
0x18002a981  test    rax, rax
0x18002a984  jz      short loc_18002A99E
0x18002a986  mov     r9, rsi; ppszParameters
0x18002a989  lea     rcx, [rsp+4A8h+pszCmdTemplate]; pszCmdTemplate
0x18002a98e  xor     r8d, r8d; ppszCommandLine
0x18002a991  mov     rdx, rdi; ppszApplication
0x18002a994  call    cs:__imp_SHEvaluateSystemCommandTemplate
0x18002a99a  mov     ebx, eax
0x18002a99c  jmp     short loc_18002A9A3
0x18002a99e  mov     ebx, 80004005h
0x18002a9a3  mov     eax, ebx
0x18002a9a5  mov     rcx, [rsp+4A8h+var_48]
0x18002a9ad  xor     rcx, rsp; StackCookie
0x18002a9b0  call    __security_check_cookie
0x18002a9b5  add     rsp, 470h
0x18002a9bc  pop     r15
0x18002a9be  pop     r14
0x18002a9c0  pop     r12
0x18002a9c2  pop     rdi
0x18002a9c3  pop     rsi
0x18002a9c4  pop     rbp
0x18002a9c5  pop     rbx
0x18002a9c6  retn
```
