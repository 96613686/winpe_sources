# CPubCacheBackingStore::MoveHashStore(ushort *,ushort *,ushort const *,void *,bool)

- ea: `0x18005a7b8`
- end: `0x18005ab02`
- name: `?MoveHashStore@CPubCacheBackingStore@@AEAAKPEAG0PEBGPEAX_N@Z`
- size: `842`
- prototype: `__int64 __fastcall(CPubCacheBackingStore *this, unsigned __int16 *, unsigned __int16 *, const unsigned __int16 *, HANDLE hTransaction, bool)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18005ab08`

## callees

- `0x180004374`
- `0x1800094d4`
- `0x18000cf48`
- `0x18000cfc0`
- `0x18005a434`
- `0x18005a7b8`
- `0x180062688`
- `0x180114ae0`
- `0x1801448c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a86b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a91f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a96e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005aaaa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a86b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a91f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005a96e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005aaaa`
- `api-ms-win-core-kernel32-legacy-l1-1-3!RemoveDirectoryTransactedW` at `0x18005a964`
- `api-ms-win-core-kernel32-legacy-l1-1-3!RemoveDirectoryTransactedW` at `0x18005aaa0`
- `api-ms-win-core-kernel32-legacy-l1-1-3!RemoveDirectoryTransactedW` at `0x18005a964`
- `api-ms-win-core-kernel32-legacy-l1-1-3!RemoveDirectoryTransactedW` at `0x18005aaa0`
- `api-ms-win-core-kernel32-legacy-l1-1-3!CreateDirectoryTransactedW` at `0x18005a861`
- `api-ms-win-core-kernel32-legacy-l1-1-3!CreateDirectoryTransactedW` at `0x18005a915`
- `api-ms-win-core-kernel32-legacy-l1-1-3!CreateDirectoryTransactedW` at `0x18005a861`
- `api-ms-win-core-kernel32-legacy-l1-1-3!CreateDirectoryTransactedW` at `0x18005a915`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPubCacheBackingStore::MoveHashStore(
        CPubCacheBackingStore *this,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        const unsigned __int16 *a4,
        HANDLE hTransaction,
        bool a6)
{
  int v10; // eax
  DWORD appended; // ebx
  DWORD LastError; // eax
  CHostedCacheMsgEncoding *v13; // rcx
  int v14; // edx
  WCHAR *v15; // r9
  unsigned int i; // edi
  unsigned int HashSubStorePath; // eax
  unsigned __int16 *v18; // r9
  DWORD v19; // eax
  char v21; // [rsp+20h] [rbp-E0h]
  WCHAR NewDirectory[264]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR v23[264]; // [rsp+240h] [rbp+140h] BYREF
  WCHAR PathName[264]; // [rsp+450h] [rbp+350h] BYREF

  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 252, WPP_817cd87503153d87380e6127cb13644a_Traceguids);
  }
  v10 = StringCchCopyW(NewDirectory, 0x104u, a3);
  if ( v10 < 0 )
    appended = (unsigned __int16)v10;
  else
    appended = AppendFilePath(NewDirectory, a4);
  if ( !CreateDirectoryTransactedW(0, NewDirectory, 0, hTransaction) )
  {
    LastError = GetLastError();
    appended = LastError;
    if ( LastError != 183 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v14 = 253;
LABEL_14:
        v15 = NewDirectory;
LABEL_15:
        v21 = LastError;
LABEL_16:
        WPP_SF_Sd(
          *((_QWORD *)v13 + 12),
          v14,
          (unsigned int)WPP_817cd87503153d87380e6127cb13644a_Traceguids,
          (_DWORD)v15,
          v21);
      }
      return appended;
    }
    appended = 0;
  }
  for ( i = 0; i < 0x10; ++i )
  {
    HashSubStorePath = GenerateHashSubStorePath(a2, i, PathName);
    appended = HashSubStorePath;
    if ( HashSubStorePath )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) == 0
        || !*((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        return appended;
      }
      v14 = 254;
      v21 = HashSubStorePath;
LABEL_52:
      LODWORD(v15) = (_DWORD)a2;
      goto LABEL_16;
    }
    LastError = GenerateHashSubStorePath(NewDirectory, i, v23);
    appended = LastError;
    if ( LastError )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v14 = 255;
        goto LABEL_14;
      }
      return appended;
    }
    if ( !CreateDirectoryTransactedW(0, v23, 0, hTransaction) )
    {
      LastError = GetLastError();
      appended = LastError;
      if ( LastError != 183 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          v14 = 256;
          v15 = v23;
          goto LABEL_15;
        }
        return appended;
      }
      appended = 0;
    }
    if ( a6 )
    {
      v19 = CPubCacheBackingStore::MoveCacheFolder(this, PathName, v23, v18, hTransaction);
      appended = v19;
      if ( v19 )
      {
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          WPP_SF_SSD(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            257,
            (unsigned int)WPP_817cd87503153d87380e6127cb13644a_Traceguids,
            (unsigned int)PathName,
            (__int64)v23,
            v19);
        }
        return appended;
      }
    }
    if ( !RemoveDirectoryTransactedW(PathName, hTransaction) )
    {
      appended = GetLastError();
      if ( appended - 2 > 1 )
      {
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 12),
            258,
            (unsigned int)WPP_817cd87503153d87380e6127cb13644a_Traceguids,
            (unsigned int)PathName,
            appended);
        }
        return appended;
      }
      appended = 0;
    }
  }
  if ( !RemoveDirectoryTransactedW(a2, hTransaction) )
  {
    appended = GetLastError();
    if ( appended - 2 <= 1 )
      return 0;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v14 = 259;
      v21 = appended;
      goto LABEL_52;
    }
  }
  return appended;
}

```

## disassembly

```asm
0x18005a7b8  push    rbp
0x18005a7ba  push    rbx
0x18005a7bb  push    rsi
0x18005a7bc  push    rdi
0x18005a7bd  push    r13
0x18005a7bf  push    r14
0x18005a7c1  push    r15
0x18005a7c3  lea     rbp, [rsp-570h]
0x18005a7cb  sub     rsp, 670h
0x18005a7d2  mov     rax, cs:__security_cookie
0x18005a7d9  xor     rax, rsp
0x18005a7dc  mov     [rbp+5A0h+var_40], rax
0x18005a7e3  mov     rsi, [rbp+5A0h+hTransaction]
0x18005a7ea  mov     rbx, r9
0x18005a7ed  mov     rdi, r8
0x18005a7f0  mov     r14, rdx
0x18005a7f3  mov     r15, rcx
0x18005a7f6  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a7fd  lea     r13, WPP_GLOBAL_Control
0x18005a804  cmp     rcx, r13
0x18005a807  jz      short loc_18005A82A
0x18005a809  test    byte ptr [rcx+6Ch], 4
0x18005a80d  jz      short loc_18005A82A
0x18005a80f  cmp     byte ptr [rcx+69h], 4
0x18005a813  jb      short loc_18005A82A
0x18005a815  mov     rcx, [rcx+60h]
0x18005a819  lea     r8, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x18005a820  mov     edx, 0FCh
0x18005a825  call    WPP_SF_
0x18005a82a  mov     r8, rdi; unsigned __int16 *
0x18005a82d  lea     rcx, [rsp+6A0h+NewDirectory]; unsigned __int16 *
0x18005a832  mov     edx, 104h; unsigned __int64
0x18005a837  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005a83c  test    eax, eax
0x18005a83e  js      short loc_18005A851
0x18005a840  mov     rdx, rbx; unsigned __int16 *
0x18005a843  lea     rcx, [rsp+6A0h+NewDirectory]; unsigned __int16 *
0x18005a848  call    ?AppendFilePath@@YAKPEAGPEBG@Z; AppendFilePath(ushort *,ushort const *)
0x18005a84d  mov     ebx, eax
0x18005a84f  jmp     short loc_18005A854
0x18005a851  movzx   ebx, ax
0x18005a854  mov     r9, rsi; hTransaction
0x18005a857  lea     rdx, [rsp+6A0h+NewDirectory]; lpNewDirectory
0x18005a85c  xor     r8d, r8d; lpSecurityAttributes
0x18005a85f  xor     ecx, ecx; lpTemplateDirectory
0x18005a861  call    cs:__imp_CreateDirectoryTransactedW
0x18005a867  test    eax, eax
0x18005a869  jnz     short loc_18005A8C3
0x18005a86b  call    cs:__imp_GetLastError
0x18005a871  mov     ebx, eax
0x18005a873  cmp     eax, 0B7h
0x18005a878  jz      short loc_18005A8C1
0x18005a87a  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a881  cmp     rcx, r13
0x18005a884  jz      loc_18005AADF
0x18005a88a  test    byte ptr [rcx+6Ch], 4
0x18005a88e  jz      loc_18005AADF
0x18005a894  cmp     byte ptr [rcx+69h], 1
0x18005a898  jb      loc_18005AADF
0x18005a89e  mov     edx, 0FDh
0x18005a8a3  lea     r9, [rsp+6A0h+NewDirectory]
0x18005a8a8  mov     dword ptr [rsp+6A0h+var_680], eax
0x18005a8ac  mov     rcx, [rcx+60h]
0x18005a8b0  lea     r8, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x18005a8b7  call    WPP_SF_Sd
0x18005a8bc  jmp     loc_18005AADF
0x18005a8c1  xor     ebx, ebx
0x18005a8c3  xor     edi, edi
0x18005a8c5  mov     rcx, r14; unsigned __int16 *
0x18005a8c8  cmp     edi, 10h
0x18005a8cb  jnb     loc_18005AA9D
0x18005a8d1  lea     r8, [rbp+5A0h+PathName]; unsigned __int16 *
0x18005a8d8  mov     edx, edi; unsigned int
0x18005a8da  call    ?GenerateHashSubStorePath@@YAKPEAGK0@Z; GenerateHashSubStorePath(ushort *,ulong,ushort *)
0x18005a8df  mov     ebx, eax
0x18005a8e1  test    eax, eax
0x18005a8e3  jnz     loc_18005AA74
0x18005a8e9  lea     r8, [rbp+5A0h+var_460]; unsigned __int16 *
0x18005a8f0  mov     edx, edi; unsigned int
0x18005a8f2  lea     rcx, [rsp+6A0h+NewDirectory]; unsigned __int16 *
0x18005a8f7  call    ?GenerateHashSubStorePath@@YAKPEAGK0@Z; GenerateHashSubStorePath(ushort *,ulong,ushort *)
0x18005a8fc  mov     ebx, eax
0x18005a8fe  test    eax, eax
0x18005a900  jnz     loc_18005AA4E
0x18005a906  mov     r9, rsi; hTransaction
0x18005a909  lea     rdx, [rbp+5A0h+var_460]; lpNewDirectory
0x18005a910  xor     r8d, r8d; lpSecurityAttributes
0x18005a913  xor     ecx, ecx; lpTemplateDirectory
0x18005a915  call    cs:__imp_CreateDirectoryTransactedW
0x18005a91b  test    eax, eax
0x18005a91d  jnz     short loc_18005A930
0x18005a91f  call    cs:__imp_GetLastError
0x18005a925  mov     ebx, eax
0x18005a927  cmp     eax, 0B7h
0x18005a92c  jnz     short loc_18005A98B
0x18005a92e  xor     ebx, ebx
0x18005a930  cmp     [rbp+5A0h+arg_28], 0
0x18005a937  jz      short loc_18005A95A
0x18005a939  lea     r8, [rbp+5A0h+var_460]; unsigned __int16 *
0x18005a940  mov     [rsp+6A0h+var_680], rsi; void *
0x18005a945  lea     rdx, [rbp+5A0h+PathName]; unsigned __int16 *
0x18005a94c  mov     rcx, r15; this
0x18005a94f  call    ?MoveCacheFolder@CPubCacheBackingStore@@AEAAKPEAG00PEAX@Z; CPubCacheBackingStore::MoveCacheFolder(ushort *,ushort *,ushort *,void *)
0x18005a954  mov     ebx, eax
0x18005a956  test    eax, eax
0x18005a958  jnz     short loc_18005A9C0
0x18005a95a  mov     rdx, rsi; hTransaction
0x18005a95d  lea     rcx, [rbp+5A0h+PathName]; lpPathName
0x18005a964  call    cs:__imp_RemoveDirectoryTransactedW
0x18005a96a  test    eax, eax
0x18005a96c  jnz     short loc_18005A984
0x18005a96e  call    cs:__imp_GetLastError
0x18005a974  mov     ebx, eax
0x18005a976  add     eax, 0FFFFFFFEh
0x18005a979  cmp     eax, 1
0x18005a97c  ja      loc_18005AA15
0x18005a982  xor     ebx, ebx
0x18005a984  inc     edi
0x18005a986  jmp     loc_18005A8C5
0x18005a98b  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a992  cmp     rcx, r13
0x18005a995  jz      loc_18005AADF
0x18005a99b  test    byte ptr [rcx+6Ch], 4
0x18005a99f  jz      loc_18005AADF
0x18005a9a5  cmp     byte ptr [rcx+69h], 1
0x18005a9a9  jb      loc_18005AADF
0x18005a9af  mov     edx, 100h
0x18005a9b4  lea     r9, [rbp+5A0h+var_460]
0x18005a9bb  jmp     loc_18005A8A8
0x18005a9c0  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a9c7  cmp     rcx, r13
0x18005a9ca  jz      loc_18005AADF
0x18005a9d0  test    byte ptr [rcx+6Ch], 4
0x18005a9d4  jz      loc_18005AADF
0x18005a9da  cmp     byte ptr [rcx+69h], 1
0x18005a9de  jb      loc_18005AADF
0x18005a9e4  mov     rcx, [rcx+60h]
0x18005a9e8  lea     r9, [rbp+5A0h+PathName]
0x18005a9ef  mov     [rsp+6A0h+var_678], eax
0x18005a9f3  lea     r8, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x18005a9fa  lea     rax, [rbp+5A0h+var_460]
0x18005aa01  mov     edx, 101h
0x18005aa06  mov     [rsp+6A0h+var_680], rax
0x18005aa0b  call    WPP_SF_SSD
0x18005aa10  jmp     loc_18005AADF
0x18005aa15  mov     rcx, cs:WPP_GLOBAL_Control
0x18005aa1c  cmp     rcx, r13
0x18005aa1f  jz      loc_18005AADF
0x18005aa25  test    byte ptr [rcx+6Ch], 4
0x18005aa29  jz      loc_18005AADF
0x18005aa2f  cmp     byte ptr [rcx+69h], 1
0x18005aa33  jb      loc_18005AADF
0x18005aa39  mov     edx, 102h
0x18005aa3e  mov     dword ptr [rsp+6A0h+var_680], ebx
0x18005aa42  lea     r9, [rbp+5A0h+PathName]
0x18005aa49  jmp     loc_18005A8AC
0x18005aa4e  mov     rcx, cs:WPP_GLOBAL_Control
0x18005aa55  cmp     rcx, r13
0x18005aa58  jz      loc_18005AADF
0x18005aa5e  test    byte ptr [rcx+6Ch], 4
0x18005aa62  jz      short loc_18005AADF
0x18005aa64  cmp     byte ptr [rcx+69h], 1
0x18005aa68  jb      short loc_18005AADF
0x18005aa6a  mov     edx, 0FFh
0x18005aa6f  jmp     loc_18005A8A3
0x18005aa74  mov     rcx, cs:WPP_GLOBAL_Control
0x18005aa7b  cmp     rcx, r13
0x18005aa7e  jz      short loc_18005AADF
0x18005aa80  test    byte ptr [rcx+6Ch], 4
0x18005aa84  jz      short loc_18005AADF
0x18005aa86  cmp     byte ptr [rcx+69h], 1
0x18005aa8a  jb      short loc_18005AADF
0x18005aa8c  mov     edx, 0FEh
0x18005aa91  mov     dword ptr [rsp+6A0h+var_680], eax
0x18005aa95  mov     r9, r14
0x18005aa98  jmp     loc_18005A8AC
0x18005aa9d  mov     rdx, rsi; hTransaction
0x18005aaa0  call    cs:__imp_RemoveDirectoryTransactedW
0x18005aaa6  test    eax, eax
0x18005aaa8  jnz     short loc_18005AADF
0x18005aaaa  call    cs:__imp_GetLastError
0x18005aab0  mov     ebx, eax
0x18005aab2  add     eax, 0FFFFFFFEh
0x18005aab5  cmp     eax, 1
0x18005aab8  jbe     short loc_18005AADD
0x18005aaba  mov     rcx, cs:WPP_GLOBAL_Control
0x18005aac1  cmp     rcx, r13
0x18005aac4  jz      short loc_18005AADF
0x18005aac6  test    byte ptr [rcx+6Ch], 4
0x18005aaca  jz      short loc_18005AADF
0x18005aacc  cmp     byte ptr [rcx+69h], 1
0x18005aad0  jb      short loc_18005AADF
0x18005aad2  mov     edx, 103h
0x18005aad7  mov     dword ptr [rsp+6A0h+var_680], ebx
0x18005aadb  jmp     short loc_18005AA95
0x18005aadd  xor     ebx, ebx
0x18005aadf  mov     eax, ebx
0x18005aae1  mov     rcx, [rbp+5A0h+var_40]
0x18005aae8  xor     rcx, rsp; StackCookie
0x18005aaeb  call    __security_check_cookie
0x18005aaf0  add     rsp, 670h
0x18005aaf7  pop     r15
0x18005aaf9  pop     r14
0x18005aafb  pop     r13
0x18005aafd  pop     rdi
0x18005aafe  pop     rsi
0x18005aaff  pop     rbx
0x18005ab00  pop     rbp
0x18005ab01  retn
```
