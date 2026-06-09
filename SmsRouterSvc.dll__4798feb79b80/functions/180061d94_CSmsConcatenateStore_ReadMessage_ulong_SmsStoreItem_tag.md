# CSmsConcatenateStore::ReadMessage(ulong,SmsStoreItem_tag *)

- ea: `0x180061d94`
- end: `0x180061e6f`
- name: `?ReadMessage@CSmsConcatenateStore@@AEAAJKPEAUSmsStoreItem_tag@@@Z`
- size: `219`
- prototype: `__int64 __fastcall(CSmsConcatenateStore *this, LONG, struct SmsStoreItem_tag *)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180061050`
- `0x180061618`
- `0x180061a74`
- `0x180062084`

## callees

- `0x180051628`
- `0x180053ba4`
- `0x180061d94`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061dcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061dcd`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180061dc2`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180061dc2`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180061dfe`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180061dfe`

## string_xrefs

- `0x180061e54`: `CSmsConcatenateStore::ReadMessage`
- `0x180061e2f`: `Store message read hr=0x%08X, location=%d, partindex=%d, totalparts=%d, uid=%s, IccId=%S`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall CSmsConcatenateStore::ReadMessage(CSmsConcatenateStore *this, LONG a2, struct SmsStoreItem_tag *a3)
{
  void *v5; // rcx
  signed int LastError; // eax
  unsigned int v9; // ebx
  const char *DisplayString; // rax

  v5 = (void *)*((_QWORD *)this + 16);
  if ( v5 == (void *)-1LL )
    return 2147942421LL;
  if ( SetFilePointer(v5, a2, 0, 0) == -1 )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v9 = 0;
    if ( !ReadFile(*((HANDLE *)this + 16), a3, 0x298u, 0, 0) )
      v9 = -2147024883;
  }
  DisplayString = GetDisplayString((unsigned __int8 *)a3 + 532, *((_DWORD *)a3 + 132));
  LogSmsRouterInfo(
    "CSmsConcatenateStore::ReadMessage",
    0x13Eu,
    "Store message read hr=0x%08X, location=%d, partindex=%d, totalparts=%d, uid=%s, IccId=%S",
    v9,
    a2,
    *((_DWORD *)a3 + 150),
    *((_DWORD *)a3 + 149),
    DisplayString,
    (const wchar_t *)a3 + 304);
  return v9;
}

```

## disassembly

```asm
0x180061d94  push    rbx
0x180061d96  push    rbp
0x180061d97  push    rsi
0x180061d98  push    rdi
0x180061d99  sub     rsp, 58h
0x180061d9d  mov     rsi, rcx
0x180061da0  mov     rdi, r8
0x180061da3  mov     rcx, [rcx+80h]; hFile
0x180061daa  mov     ebp, edx
0x180061dac  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180061db0  jnz     short loc_180061DBC
0x180061db2  mov     eax, 80070015h
0x180061db7  jmp     loc_180061E66
0x180061dbc  xor     r9d, r9d; dwMoveMethod
0x180061dbf  xor     r8d, r8d; lpDistanceToMoveHigh
0x180061dc2  call    cs:__imp_SetFilePointer
0x180061dc8  cmp     eax, 0FFFFFFFFh
0x180061dcb  jnz     short loc_180061DE4
0x180061dcd  call    cs:__imp_GetLastError
0x180061dd3  mov     ebx, eax
0x180061dd5  test    eax, eax
0x180061dd7  jle     short loc_180061E0E
0x180061dd9  movzx   ebx, ax
0x180061ddc  or      ebx, 80070000h
0x180061de2  jmp     short loc_180061E0E
0x180061de4  mov     rcx, [rsi+80h]; hFile
0x180061deb  xor     ebx, ebx
0x180061ded  xor     r9d, r9d; lpNumberOfBytesRead
0x180061df0  mov     [rsp+78h+lpOverlapped], rbx; lpOverlapped
0x180061df5  mov     r8d, 298h; nNumberOfBytesToRead
0x180061dfb  mov     rdx, rdi; lpBuffer
0x180061dfe  call    cs:__imp_ReadFile
0x180061e04  test    eax, eax
0x180061e06  mov     ecx, 8007000Dh
0x180061e0b  cmovz   ebx, ecx
0x180061e0e  mov     edx, [rdi+210h]; unsigned int
0x180061e14  lea     rcx, [rdi+214h]; unsigned __int8 *
0x180061e1b  call    ?GetDisplayString@@YAPEBDPEAEK@Z; GetDisplayString(uchar *,ulong)
0x180061e20  lea     rcx, [rdi+260h]
0x180061e27  mov     r9d, ebx
0x180061e2a  mov     [rsp+78h+var_38], rcx
0x180061e2f  lea     r8, aStoreMessageRe; "Store message read hr=0x%08X, location="...
0x180061e36  mov     ecx, [rdi+254h]
0x180061e3c  mov     edx, 13Eh; unsigned int
0x180061e41  mov     [rsp+78h+var_40], rax
0x180061e46  mov     [rsp+78h+var_48], ecx
0x180061e4a  mov     ecx, [rdi+258h]
0x180061e50  mov     [rsp+78h+var_50], ecx
0x180061e54  lea     rcx, aCsmsconcatenat_6; "CSmsConcatenateStore::ReadMessage"
0x180061e5b  mov     dword ptr [rsp+78h+lpOverlapped], ebp
0x180061e5f  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x180061e64  mov     eax, ebx
0x180061e66  add     rsp, 58h
0x180061e6a  pop     rdi
0x180061e6b  pop     rsi
0x180061e6c  pop     rbp
0x180061e6d  pop     rbx
0x180061e6e  retn
```
