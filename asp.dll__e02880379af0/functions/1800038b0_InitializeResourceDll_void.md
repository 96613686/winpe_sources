# InitializeResourceDll(void)

- ea: `0x1800038b0`
- end: `0x1800039b0`
- name: `?InitializeResourceDll@@YAJXZ`
- size: `256`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180004a64`
- `0x18004a3d0`
- `0x18004a420`

## callees

- `0x1800038b0`
- `0x180023d86`
- `0x180023dd0`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x180003970`
- `KERNEL32!LoadLibraryW` at `0x180003970`
- `KERNEL32!GetWindowsDirectoryW` at `0x180003914`
- `KERNEL32!GetWindowsDirectoryW` at `0x180003914`
- `KERNEL32!GetLastError` at `0x1800255f0`
- `KERNEL32!GetLastError` at `0x1800255f0`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000393e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180003956`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000393e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180003956`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000398b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000398b`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18000392c`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x18000392c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003906`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003967`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003906`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180003967`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800038fb`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800038fb`

## string_xrefs

- `0x18000394a`: `iisres.dll`
- `0x180003932`: `\system32\inetsrv\`

## pseudocode

```c
__int64 InitializeResourceDll(void)
{
  WCHAR *Str; // rax
  signed int v1; // ebx
  const WCHAR *v2; // rax
  signed int LastError; // eax
  _BYTE v5[64]; // [rsp+20h] [rbp-328h] BYREF
  unsigned __int16 v6[360]; // [rsp+60h] [rbp-2E8h] BYREF

  if ( g_hResourceDLL )
    return 0;
  memset_0(v6, 0, sizeof(v6));
  STRU::STRU((STRU *)v5, v6, 0x168u);
  Str = STRU::QueryStr((STRU *)v5);
  if ( GetWindowsDirectoryW(Str, 0x104u) - 1 > 0x103
    || (STRU::SyncWithBuffer((STRU *)v5), v1 = STRU::Append((STRU *)v5, L"\\system32\\inetsrv\\"), v1 >= 0)
    && (v1 = STRU::Append((STRU *)v5, L"iisres.dll"), v1 >= 0)
    && (v2 = STRU::QueryStr((STRU *)v5), (g_hResourceDLL = LoadLibraryW(v2)) == 0) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
  }
  STRU::~STRU((STRU *)v5);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x1800038b0  push    rbx
0x1800038b2  sub     rsp, 340h
0x1800038b9  mov     rax, cs:__security_cookie
0x1800038c0  xor     rax, rsp
0x1800038c3  mov     [rsp+348h+var_18], rax
0x1800038cb  cmp     cs:?g_hResourceDLL@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hResourceDLL
0x1800038d3  jnz     loc_1800039AC
0x1800038d9  xor     edx, edx; Val
0x1800038db  lea     rcx, [rsp+348h+var_2E8]; void *
0x1800038e0  mov     r8d, 2D0h; Size
0x1800038e6  call    memset_0
0x1800038eb  mov     r8d, 168h
0x1800038f1  lea     rdx, [rsp+348h+var_2E8]
0x1800038f6  lea     rcx, [rsp+348h+var_328]
0x1800038fb  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180003901  lea     rcx, [rsp+348h+var_328]
0x180003906  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000390c  mov     rcx, rax; lpBuffer
0x18000390f  mov     edx, 104h; uSize
0x180003914  call    cs:__imp_GetWindowsDirectoryW
0x18000391a  dec     eax
0x18000391c  cmp     eax, 103h
0x180003921  ja      loc_1800255F0
0x180003927  lea     rcx, [rsp+348h+var_328]
0x18000392c  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x180003932  lea     rdx, aSystem32Inetsr; "\\system32\\inetsrv\\"
0x180003939  lea     rcx, [rsp+348h+var_328]
0x18000393e  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180003944  mov     ebx, eax
0x180003946  test    eax, eax
0x180003948  js      short loc_180003986
0x18000394a  lea     rdx, aIisresDll; "iisres.dll"
0x180003951  lea     rcx, [rsp+348h+var_328]
0x180003956  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x18000395c  mov     ebx, eax
0x18000395e  test    eax, eax
0x180003960  js      short loc_180003986
0x180003962  lea     rcx, [rsp+348h+var_328]
0x180003967  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000396d  mov     rcx, rax; lpLibFileName
0x180003970  call    cs:__imp_LoadLibraryW
0x180003976  mov     cs:?g_hResourceDLL@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hResourceDLL
0x18000397d  test    rax, rax
0x180003980  jz      loc_1800255F0
0x180003986  lea     rcx, [rsp+348h+var_328]
0x18000398b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180003991  mov     eax, ebx
0x180003993  mov     rcx, [rsp+348h+var_18]
0x18000399b  xor     rcx, rsp; StackCookie
0x18000399e  call    __security_check_cookie
0x1800039a3  add     rsp, 340h
0x1800039aa  pop     rbx
0x1800039ab  retn
0x1800039ac  xor     eax, eax
0x1800039ae  jmp     short loc_180003993
0x1800255f0  call    cs:__imp_GetLastError
0x1800255f6  mov     ebx, eax
0x1800255f8  test    eax, eax
0x1800255fa  jle     loc_180003986
0x180025600  movzx   ebx, ax
0x180025603  or      ebx, 80070000h
0x180025609  jmp     loc_180003986
```
