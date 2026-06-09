# Vml::PathIsDirectoryW(ushort const *)

- ea: `0x14011733c`
- end: `0x140117463`
- name: `?PathIsDirectoryW@Vml@@YAHPEBG@Z`
- size: `295`
- prototype: `__int64 __fastcall(WCHAR *lpFileName, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x140117280`

## callees

- `0x14011733c`
- `0x140132940`
- `0x140132d30`
- `0x1401335fc`
- `0x140188280`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14011742f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14011742f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareW` at `0x140117378`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareW` at `0x140117378`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x140117361`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x140117361`
- `MPR!WNetGetResourceInformationW` at `0x1401173e6`
- `MPR!WNetGetResourceInformationW` at `0x1401173e6`

## pseudocode

```c
__int64 __fastcall Vml::PathIsDirectoryW(WCHAR *lpFileName, const unsigned __int16 *a2)
{
  struct _NETRESOURCEW *v3; // rax
  struct _NETRESOURCEW *v4; // rdi
  unsigned int v5; // ebx
  DWORD FileAttributesW; // eax
  LPWSTR lpSystem; // [rsp+20h] [rbp-28h] BYREF
  DWORD cbBuffer; // [rsp+28h] [rbp-20h] BYREF
  struct _NETRESOURCEW *v10; // [rsp+30h] [rbp-18h] BYREF

  if ( !lpFileName || PathIsUNCServerW(lpFileName) )
    return 0;
  if ( !PathIsUNCServerShareW(lpFileName) )
  {
LABEL_13:
    FileAttributesW = GetFileAttributesW(lpFileName);
    if ( FileAttributesW != -1 )
      return (FileAttributesW >> 4) & 1;
    return 0;
  }
  v3 = (struct _NETRESOURCEW *)operator new(0x400u, (const struct std::nothrow_t *)&std::nothrow);
  v4 = v3;
  if ( !v3 )
  {
    v10 = 0;
LABEL_12:
    __1__unique_ptr_TNetResourceBuffer__7__PathIsDirectoryW_Vml__YAHPEBG_Z_U__default_delete_TNetResourceBuffer__7__PathIsDirectoryW_Vml__YAHPEBG_Z__std___std__QEAA_XZ((void **)&v10);
    goto LABEL_13;
  }
  memset_0(v3, 0, 0x400u);
  *(_QWORD *)&v4->dwScope = 2;
  v4->lpRemoteName = lpFileName;
  cbBuffer = 1024;
  lpSystem = 0;
  v10 = v4;
  if ( WNetGetResourceInformationW(v4, v4, &cbBuffer, &lpSystem) || !v4->dwDisplayType )
    goto LABEL_12;
  if ( v4->dwDisplayType != 3 || (v5 = 1, v4->dwType > 1) )
    v5 = 0;
  __1__unique_ptr_TNetResourceBuffer__7__PathIsDirectoryW_Vml__YAHPEBG_Z_U__default_delete_TNetResourceBuffer__7__PathIsDirectoryW_Vml__YAHPEBG_Z__std___std__QEAA_XZ((void **)&v10);
  return v5;
}

```

## disassembly

```asm
0x14011733c  mov     [rsp+arg_8], rbx
0x140117341  push    rdi
0x140117342  sub     rsp, 40h
0x140117346  mov     rax, cs:__security_cookie
0x14011734d  xor     rax, rsp
0x140117350  mov     [rsp+48h+var_10], rax
0x140117355  mov     rbx, rcx
0x140117358  test    rcx, rcx
0x14011735b  jz      loc_140117448
0x140117361  call    cs:__imp_PathIsUNCServerW
0x140117368  nop     dword ptr [rax+rax+00h]
0x14011736d  test    eax, eax
0x14011736f  jnz     loc_140117448
0x140117375  mov     rcx, rbx; pszPath
0x140117378  call    cs:__imp_PathIsUNCServerShareW
0x14011737f  nop     dword ptr [rax+rax+00h]
0x140117384  test    eax, eax
0x140117386  jz      loc_14011742C
0x14011738c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140117393  mov     ecx, 400h; unsigned __int64
0x140117398  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14011739d  mov     rdi, rax
0x1401173a0  test    rax, rax
0x1401173a3  jz      short loc_140117419
0x1401173a5  xor     edx, edx; Val
0x1401173a7  mov     r8d, 400h; Size
0x1401173ad  mov     rcx, rax; void *
0x1401173b0  call    memset_0
0x1401173b5  mov     qword ptr [rdi], 2
0x1401173bc  lea     r9, [rsp+48h+lpSystem]; lplpSystem
0x1401173c1  mov     [rdi+18h], rbx
0x1401173c5  lea     r8, [rsp+48h+cbBuffer]; lpcbBuffer
0x1401173ca  mov     rdx, rdi; lpBuffer
0x1401173cd  mov     [rsp+48h+cbBuffer], 400h
0x1401173d5  mov     rcx, rdi; lpNetResource
0x1401173d8  mov     [rsp+48h+lpSystem], 0
0x1401173e1  mov     [rsp+48h+var_18], rdi
0x1401173e6  call    cs:__imp_WNetGetResourceInformationW
0x1401173ed  nop     dword ptr [rax+rax+00h]
0x1401173f2  test    eax, eax
0x1401173f4  jnz     short loc_140117422
0x1401173f6  cmp     [rdi+8], eax
0x1401173f9  jz      short loc_140117422
0x1401173fb  cmp     dword ptr [rdi+8], 3
0x1401173ff  jnz     short loc_140117409
0x140117401  lea     ebx, [rax+1]
0x140117404  cmp     [rdi+4], ebx
0x140117407  jbe     short loc_14011740B
0x140117409  xor     ebx, ebx
0x14011740b  lea     rcx, [rsp+48h+var_18]
0x140117410  call    ??1?$unique_ptr@TNetResourceBuffer@?7??PathIsDirectoryW@Vml@@YAHPEBG@Z@U?$default_delete@TNetResourceBuffer@?7??PathIsDirectoryW@Vml@@YAHPEBG@Z@@std@@@std@@QEAA@XZ; std::unique_ptr<`Vml::PathIsDirectoryW(ushort const *)'::`8'::NetResourceBuffer,std::default_delete<`Vml::PathIsDirectoryW(ushort const *)'::`8'::NetResourceBuffer>>::~unique_ptr<`Vml::PathIsDirectoryW(ushort const *)'::`8'::NetResourceBuffer,std::default_delete<`Vml::PathIsDirectoryW(ushort const *)'::`8'::NetResourceBuffer>>(void)
0x140117415  mov     eax, ebx
0x140117417  jmp     short loc_14011744A
0x140117419  mov     [rsp+48h+var_18], 0
0x140117422  lea     rcx, [rsp+48h+var_18]
0x140117427  call    ??1?$unique_ptr@TNetResourceBuffer@?7??PathIsDirectoryW@Vml@@YAHPEBG@Z@U?$default_delete@TNetResourceBuffer@?7??PathIsDirectoryW@Vml@@YAHPEBG@Z@@std@@@std@@QEAA@XZ; std::unique_ptr<`Vml::PathIsDirectoryW(ushort const *)'::`8'::NetResourceBuffer,std::default_delete<`Vml::PathIsDirectoryW(ushort const *)'::`8'::NetResourceBuffer>>::~unique_ptr<`Vml::PathIsDirectoryW(ushort const *)'::`8'::NetResourceBuffer,std::default_delete<`Vml::PathIsDirectoryW(ushort const *)'::`8'::NetResourceBuffer>>(void)
0x14011742c  mov     rcx, rbx; lpFileName
0x14011742f  call    cs:__imp_GetFileAttributesW
0x140117436  nop     dword ptr [rax+rax+00h]
0x14011743b  cmp     eax, 0FFFFFFFFh
0x14011743e  jz      short loc_140117448
0x140117440  shr     eax, 4
0x140117443  and     eax, 1
0x140117446  jmp     short loc_14011744A
0x140117448  xor     eax, eax
0x14011744a  mov     rcx, [rsp+48h+var_10]
0x14011744f  xor     rcx, rsp; StackCookie
0x140117452  call    __security_check_cookie
0x140117457  mov     rbx, [rsp+48h+arg_8]
0x14011745c  add     rsp, 40h
0x140117460  pop     rdi
0x140117461  retn
```
