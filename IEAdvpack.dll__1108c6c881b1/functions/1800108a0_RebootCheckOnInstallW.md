# RebootCheckOnInstallW

- ea: `0x1800108a0`
- end: `0x1800109cd`
- name: `RebootCheckOnInstallW`
- size: `301`
- prototype: `HRESULT __stdcall(HWND hwnd, LPCWSTR pszINF, LPCWSTR pszSec, DWORD dwReserved)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180010810`

## callees

- `0x1800022bc`
- `0x180004700`
- `0x180004754`
- `0x1800082f0`
- `0x18000a61c`
- `0x18000d90c`
- `0x1800108a0`
- `0x18001b980`

## import_xrefs

- `SHLWAPI!PathRemoveFileSpecW` at `0x18001091f`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18001091f`

## pseudocode

```c
HRESULT __stdcall RebootCheckOnInstallW(HWND hwnd, LPCWSTR pszINF, LPCWSTR pszSec, DWORD dwReserved)
{
  HRESULT v6; // ebx
  WCHAR SectionName[104]; // [rsp+40h] [rbp-308h] BYREF
  WCHAR pszPath[264]; // [rsp+110h] [rbp-238h] BYREF

  if ( !pszINF || !*pszINF )
    return 1;
  hWnd = hwnd;
  word_1800257D2 = 1;
  if ( IsFullPath(pszINF) )
  {
    StringCchCopyW(pszPath, 0x104u, (size_t *)pszINF);
    PathRemoveFileSpecW(pszPath);
    v6 = CommonInstallInit(pszINF, pszSec, SectionName, 0x64u, 0, 0, 0x20u);
    if ( v6 >= 0 )
    {
      v6 = SetLDIDs(pszINF, SectionName, 0, 0);
      if ( v6 >= 0 )
      {
        dword_180025CA0 = 1;
        v6 = ProcessFileSections(SectionName, pszPath, (PSP_FILE_CALLBACK_W)MyFileCheckCallback);
        if ( v6 >= 0 || !dword_180025CA0 )
          v6 = dword_180025CA0;
      }
    }
  }
  else
  {
    v6 = -2147024809;
  }
  CommonInstallCleanup();
  return v6;
}

```

## disassembly

```asm
0x1800108a0  mov     [rsp+arg_0], rbx
0x1800108a5  push    rbp
0x1800108a6  push    rsi
0x1800108a7  push    rdi
0x1800108a8  sub     rsp, 330h
0x1800108af  mov     rax, cs:__security_cookie
0x1800108b6  xor     rax, rsp
0x1800108b9  mov     [rsp+348h+var_28], rax
0x1800108c1  xor     ebp, ebp
0x1800108c3  mov     rbx, r8
0x1800108c6  mov     rsi, rdx
0x1800108c9  test    rdx, rdx
0x1800108cc  jz      loc_1800109A5
0x1800108d2  cmp     [rdx], bp
0x1800108d5  jz      loc_1800109A5
0x1800108db  mov     cs:hWnd, rcx
0x1800108e2  lea     edi, [rbp+1]
0x1800108e5  mov     rcx, rdx; unsigned __int16 *
0x1800108e8  mov     cs:word_1800257D2, di
0x1800108ef  call    ?IsFullPath@@YAHPEBG@Z; IsFullPath(ushort const *)
0x1800108f4  test    eax, eax
0x1800108f6  jnz     short loc_180010902
0x1800108f8  mov     ebx, 80070057h
0x1800108fd  jmp     loc_18001099C
0x180010902  mov     r8, rsi; unsigned __int16 *
0x180010905  lea     rcx, [rsp+348h+pszPath]; unsigned __int16 *
0x18001090d  mov     edx, 104h; unsigned __int64
0x180010912  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180010917  lea     rcx, [rsp+348h+pszPath]; pszPath
0x18001091f  call    cs:__imp_PathRemoveFileSpecW
0x180010925  mov     [rsp+348h+var_318], 20h ; ' '; unsigned int
0x18001092d  lea     r8, [rsp+348h+SectionName]; unsigned __int16 *
0x180010932  mov     [rsp+348h+var_320], ebp; int
0x180010936  mov     r9d, 64h ; 'd'; unsigned int
0x18001093c  mov     rdx, rbx; unsigned __int16 *
0x18001093f  mov     [rsp+348h+var_328], rbp; unsigned __int16 *
0x180010944  mov     rcx, rsi; unsigned __int16 *
0x180010947  call    ?CommonInstallInit@@YAJPEBG0PEAGK0HK@Z; CommonInstallInit(ushort const *,ushort const *,ushort *,ulong,ushort const *,int,ulong)
0x18001094c  mov     ebx, eax
0x18001094e  test    eax, eax
0x180010950  js      short loc_18001099C
0x180010952  xor     r9d, r9d; unsigned __int16 *
0x180010955  lea     rdx, [rsp+348h+SectionName]; unsigned __int16 *
0x18001095a  xor     r8d, r8d; unsigned int
0x18001095d  mov     rcx, rsi; unsigned __int16 *
0x180010960  call    ?SetLDIDs@@YAJPEBG0K0@Z; SetLDIDs(ushort const *,ushort const *,ulong,ushort const *)
0x180010965  mov     ebx, eax
0x180010967  test    eax, eax
0x180010969  js      short loc_18001099C
0x18001096b  lea     r8, ?MyFileCheckCallback@@YAIPEAXI_K1@Z; MsgHandler
0x180010972  mov     cs:dword_180025CA0, edi
0x180010978  lea     rdx, [rsp+348h+pszPath]; SourceRootPath
0x180010980  lea     rcx, [rsp+348h+SectionName]; SectionName
0x180010985  call    ?ProcessFileSections@@YAJPEBG0P6AIPEAXI_K2@Z@Z; ProcessFileSections(ushort const *,ushort const *,uint (*)(void *,uint,unsigned __int64,unsigned __int64))
0x18001098a  mov     ebx, eax
0x18001098c  mov     eax, cs:dword_180025CA0
0x180010992  test    ebx, ebx
0x180010994  jns     short loc_18001099A
0x180010996  test    eax, eax
0x180010998  jnz     short loc_18001099C
0x18001099a  mov     ebx, eax
0x18001099c  call    ?CommonInstallCleanup@@YAXXZ; CommonInstallCleanup(void)
0x1800109a1  mov     eax, ebx
0x1800109a3  jmp     short loc_1800109AA
0x1800109a5  mov     eax, 1
0x1800109aa  mov     rcx, [rsp+348h+var_28]
0x1800109b2  xor     rcx, rsp; StackCookie
0x1800109b5  call    __security_check_cookie
0x1800109ba  mov     rbx, [rsp+348h+arg_0]
0x1800109c2  add     rsp, 330h
0x1800109c9  pop     rdi
0x1800109ca  pop     rsi
0x1800109cb  pop     rbp
0x1800109cc  retn
```
