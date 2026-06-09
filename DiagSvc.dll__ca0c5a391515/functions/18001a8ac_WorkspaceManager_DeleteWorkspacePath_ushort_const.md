# WorkspaceManager::DeleteWorkspacePath(ushort const *)

- ea: `0x18001a8ac`
- end: `0x18001aa77`
- name: `?DeleteWorkspacePath@WorkspaceManager@@AEAAJPEBG@Z`
- size: `459`
- prototype: `__int64 __fastcall(WorkspaceManager *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18001a880`
- `0x18001ac20`

## callees

- `0x180001720`
- `0x180001e7c`
- `0x180003fc0`
- `0x1800046c0`
- `0x180004b78`
- `0x18001134c`
- `0x18001a8ac`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001a8e9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001a8e9`
- `ext-ms-win-shell-shell32-l1-2-1!SHFileOperationW` at `0x18001a984`
- `ext-ms-win-shell-shell32-l1-2-1!SHFileOperationW` at `0x18001a984`

## string_xrefs

- `0x18001a9dd`: `WorkspaceManager::DeleteWorkspacePath`
- `0x18001a9e9`: `Deleted Workspace`

## pseudocode

```c
__int64 __fastcall WorkspaceManager::DeleteWorkspacePath(WorkspaceManager *this, const unsigned __int16 *a2)
{
  signed int v3; // ebx
  DWORD FileAttributesW; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rax
  unsigned __int64 v9; // rcx
  int v10; // eax
  int v11; // ecx
  int v12; // r8d
  int v13; // r9d
  int v15; // [rsp+60h] [rbp-A0h] BYREF
  signed int v16; // [rsp+64h] [rbp-9Ch] BYREF
  char *v17; // [rsp+68h] [rbp-98h] BYREF
  const char *v18; // [rsp+70h] [rbp-90h] BYREF
  const char *v19; // [rsp+78h] [rbp-88h] BYREF
  const char *v20; // [rsp+80h] [rbp-80h] BYREF
  char *v21; // [rsp+88h] [rbp-78h] BYREF
  _SHFILEOPSTRUCTW FileOp; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v23[264]; // [rsp+D0h] [rbp-30h] BYREF

  v3 = 0;
  FileAttributesW = GetFileAttributesW(a2);
  if ( FileAttributesW != -1 && (FileAttributesW & 0x10) != 0 )
  {
    memset_0(v23, 0, 0x20Au);
    v3 = StringCchCopyW(v23, 0x104u, a2);
    v8 = -1;
    do
      ++v8;
    while ( v23[v8] );
    v9 = 2LL * (unsigned int)(v8 + 1);
    if ( v9 >= 0x20A )
      _report_rangecheckfailure();
    v23[(unsigned int)(v8 + 1)] = 0;
    if ( v3 >= 0 )
    {
      memset(&FileOp.pTo, 0, 32);
      FileOp.pFrom = v23;
      *(_OWORD *)&FileOp.hwnd = 0;
      FileOp.wFunc = 3;
      FileOp.fFlags = 1556;
      v10 = SHFileOperationW(&FileOp);
      v3 = v10;
      if ( v10 > 0 )
        v3 = (unsigned __int16)v10 | 0x80070000;
    }
    if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v9, v6, v7) )
    {
      v15 = 187;
      v17 = (char *)this + 96;
      v16 = v3;
      v18 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\workspacemanager\\lib\\workspacemanager.cpp";
      v19 = "WorkspaceManager::DeleteWorkspacePath";
      v20 = "Deleted Workspace";
      v21 = (char *)this + 225;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v11,
        (unsigned int)&unk_180031120,
        v12,
        v13,
        (__int64)&v21,
        (__int64)&v16,
        (__int64)&v20,
        (__int64)&v19,
        (__int64)&v18,
        (__int64)&v15,
        (__int64)&v17);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001a8ac  mov     [rsp-8+arg_0], rbx
0x18001a8b1  mov     [rsp-8+arg_10], rsi
0x18001a8b6  push    rbp
0x18001a8b7  push    rdi
0x18001a8b8  push    r14
0x18001a8ba  lea     rbp, [rsp-1F0h]
0x18001a8c2  sub     rsp, 2F0h
0x18001a8c9  mov     rax, cs:__security_cookie
0x18001a8d0  xor     rax, rsp
0x18001a8d3  mov     [rbp+200h+var_20], rax
0x18001a8da  mov     rsi, rcx
0x18001a8dd  xor     r14d, r14d
0x18001a8e0  mov     rcx, rdx; lpFileName
0x18001a8e3  mov     ebx, r14d
0x18001a8e6  mov     rdi, rdx
0x18001a8e9  call    cs:__imp_GetFileAttributesW
0x18001a8ef  cmp     eax, 0FFFFFFFFh
0x18001a8f2  jz      loc_18001AA48
0x18001a8f8  test    al, 10h
0x18001a8fa  jz      loc_18001AA48
0x18001a900  xor     edx, edx; Val
0x18001a902  lea     rcx, [rbp+200h+var_230]; void *
0x18001a906  mov     r8d, 20Ah; Size
0x18001a90c  call    memset_0
0x18001a911  mov     r8, rdi; unsigned __int16 *
0x18001a914  lea     rcx, [rbp+200h+var_230]; unsigned __int16 *
0x18001a918  mov     edx, 104h; unsigned __int64
0x18001a91d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001a922  mov     ebx, eax
0x18001a924  lea     rcx, [rbp+200h+var_230]
0x18001a928  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a92c  inc     rax
0x18001a92f  cmp     [rcx+rax*2], r14w
0x18001a934  jnz     short loc_18001A92C
0x18001a936  lea     ecx, [rax+1]
0x18001a939  add     rcx, rcx
0x18001a93c  cmp     rcx, 20Ah
0x18001a943  jnb     loc_18001AA71
0x18001a949  mov     [rbp+rcx+200h+var_230], r14w
0x18001a94f  test    ebx, ebx
0x18001a951  js      short loc_18001A999
0x18001a953  xor     eax, eax
0x18001a955  lea     rcx, [rbp+200h+FileOp]; lpFileOp
0x18001a959  xorps   xmm0, xmm0
0x18001a95c  mov     [rbp+200h+FileOp.lpszProgressTitle], rax
0x18001a960  lea     rax, [rbp+200h+var_230]
0x18001a964  movups  xmmword ptr [rbp+200h+FileOp.pFrom], xmm0
0x18001a968  mov     [rbp+200h+FileOp.pFrom], rax
0x18001a96c  mov     eax, 614h
0x18001a971  movups  xmmword ptr [rbp+200h+FileOp.hwnd], xmm0
0x18001a975  mov     [rbp+200h+FileOp.wFunc], 3
0x18001a97c  movups  xmmword ptr [rbp+200h+FileOp.fFlags], xmm0
0x18001a980  mov     [rbp+200h+FileOp.fFlags], ax
0x18001a984  call    cs:__imp_SHFileOperationW
0x18001a98a  mov     ebx, eax
0x18001a98c  test    eax, eax
0x18001a98e  jle     short loc_18001A999
0x18001a990  movzx   ebx, ax
0x18001a993  or      ebx, 80070000h
0x18001a999  mov     eax, cs:dword_180039000
0x18001a99f  cmp     eax, 5
0x18001a9a2  jbe     loc_18001AA48
0x18001a9a8  call    _tlgKeywordOn
0x18001a9ad  test    al, al
0x18001a9af  jz      loc_18001AA48
0x18001a9b5  lea     rax, [rsi+60h]
0x18001a9b9  mov     [rsp+300h+var_2A0], 0BBh
0x18001a9c1  mov     [rsp+300h+var_298], rax
0x18001a9c6  lea     rdx, unk_180031120
0x18001a9cd  lea     rax, aOnecoreuapBase_5; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x18001a9d4  mov     [rsp+300h+var_29C], ebx
0x18001a9d8  mov     [rsp+300h+var_290], rax
0x18001a9dd  lea     rax, aWorkspacemanag_0; "WorkspaceManager::DeleteWorkspacePath"
0x18001a9e4  mov     [rsp+300h+var_288], rax
0x18001a9e9  lea     rax, aDeletedWorkspa; "Deleted Workspace"
0x18001a9f0  mov     [rbp+200h+var_280], rax
0x18001a9f4  lea     rax, [rsi+0E1h]
0x18001a9fb  mov     [rbp+200h+var_278], rax
0x18001a9ff  lea     rax, [rsp+300h+var_298]
0x18001aa04  mov     [rsp+300h+var_2B0], rax
0x18001aa09  lea     rax, [rsp+300h+var_2A0]
0x18001aa0e  mov     [rsp+300h+var_2B8], rax
0x18001aa13  lea     rax, [rsp+300h+var_290]
0x18001aa18  mov     [rsp+300h+var_2C0], rax
0x18001aa1d  lea     rax, [rsp+300h+var_288]
0x18001aa22  mov     [rsp+300h+var_2C8], rax
0x18001aa27  lea     rax, [rbp+200h+var_280]
0x18001aa2b  mov     [rsp+300h+var_2D0], rax
0x18001aa30  lea     rax, [rsp+300h+var_29C]
0x18001aa35  mov     [rsp+300h+var_2D8], rax
0x18001aa3a  lea     rax, [rbp+200h+var_278]
0x18001aa3e  mov     [rsp+300h+var_2E0], rax
0x18001aa43  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001aa48  mov     eax, ebx
0x18001aa4a  mov     rcx, [rbp+200h+var_20]
0x18001aa51  xor     rcx, rsp; StackCookie
0x18001aa54  call    __security_check_cookie
0x18001aa59  lea     r11, [rsp+300h+var_10]
0x18001aa61  mov     rbx, [r11+20h]
0x18001aa65  mov     rsi, [r11+30h]
0x18001aa69  mov     rsp, r11
0x18001aa6c  pop     r14
0x18001aa6e  pop     rdi
0x18001aa6f  pop     rbp
0x18001aa70  retn
0x18001aa71  call    __report_rangecheckfailure
```
