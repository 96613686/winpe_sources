# CSmsConcatenateStore::SaveMessage(ulong,SmsStoreItem_tag *)

- ea: `0x180061e78`
- end: `0x180061f4b`
- name: `?SaveMessage@CSmsConcatenateStore@@AEAAJKPEAUSmsStoreItem_tag@@@Z`
- size: `211`
- prototype: `__int64 __fastcall(CSmsConcatenateStore *this, LONG, struct SmsStoreItem_tag *)`
- caller_count: `5`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18004d928`
- `0x18004e378`
- `0x1800606cc`
- `0x180061050`
- `0x180062084`

## callees

- `0x180051628`
- `0x180053ba4`
- `0x180061e78`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061ed5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180061ed5`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180061ea6`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180061ea6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180061ecb`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180061ecb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSmsConcatenateStore::SaveMessage(CSmsConcatenateStore *this, LONG a2, struct SmsStoreItem_tag *a3)
{
  void *v5; // rcx
  unsigned int v8; // ebx
  signed int LastError; // eax
  const char *DisplayString; // rax

  v5 = (void *)*((_QWORD *)this + 16);
  if ( v5 == (void *)-1LL )
    return 2147942421LL;
  if ( SetFilePointer(v5, a2, 0, 0) == -1 || (v8 = 0, !WriteFile(*((HANDLE *)this + 16), a3, 0x298u, 0, 0)) )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
  }
  DisplayString = GetDisplayString((unsigned __int8 *)a3 + 532, *((_DWORD *)a3 + 132));
  LogSmsRouterInfo(
    "CSmsConcatenateStore::SaveMessage",
    0x161u,
    "Store message saved hr=0x%08X, location=%d, partindex=%d, totalparts=%d, uid=%s, IccId=%S",
    v8,
    a2,
    *((_DWORD *)a3 + 150),
    *((_DWORD *)a3 + 149),
    DisplayString,
    (const wchar_t *)a3 + 304);
  return v8;
}

```

## disassembly

```asm
0x180061e78  push    rbx
0x180061e7a  push    rbp
0x180061e7b  push    rsi
0x180061e7c  push    rdi
0x180061e7d  sub     rsp, 58h
0x180061e81  mov     rsi, rcx
0x180061e84  mov     rdi, r8
0x180061e87  mov     rcx, [rcx+80h]; hFile
0x180061e8e  mov     ebp, edx
0x180061e90  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180061e94  jnz     short loc_180061EA0
0x180061e96  mov     eax, 80070015h
0x180061e9b  jmp     loc_180061F42
0x180061ea0  xor     r9d, r9d; dwMoveMethod
0x180061ea3  xor     r8d, r8d; lpDistanceToMoveHigh
0x180061ea6  call    cs:__imp_SetFilePointer
0x180061eac  cmp     eax, 0FFFFFFFFh
0x180061eaf  jz      short loc_180061ED5
0x180061eb1  mov     rcx, [rsi+80h]; hFile
0x180061eb8  xor     ebx, ebx
0x180061eba  xor     r9d, r9d; lpNumberOfBytesWritten
0x180061ebd  mov     [rsp+78h+lpOverlapped], rbx; lpOverlapped
0x180061ec2  mov     r8d, 298h; nNumberOfBytesToWrite
0x180061ec8  mov     rdx, rdi; lpBuffer
0x180061ecb  call    cs:__imp_WriteFile
0x180061ed1  test    eax, eax
0x180061ed3  jnz     short loc_180061EEA
0x180061ed5  call    cs:__imp_GetLastError
0x180061edb  mov     ebx, eax
0x180061edd  test    eax, eax
0x180061edf  jle     short loc_180061EEA
0x180061ee1  movzx   ebx, ax
0x180061ee4  or      ebx, 80070000h
0x180061eea  mov     edx, [rdi+210h]; unsigned int
0x180061ef0  lea     rcx, [rdi+214h]; unsigned __int8 *
0x180061ef7  call    ?GetDisplayString@@YAPEBDPEAEK@Z; GetDisplayString(uchar *,ulong)
0x180061efc  lea     rcx, [rdi+260h]
0x180061f03  mov     r9d, ebx
0x180061f06  mov     [rsp+78h+var_38], rcx
0x180061f0b  lea     r8, aStoreMessageSa; "Store message saved hr=0x%08X, location"...
0x180061f12  mov     ecx, [rdi+254h]
0x180061f18  mov     edx, 161h; unsigned int
0x180061f1d  mov     [rsp+78h+var_40], rax
0x180061f22  mov     [rsp+78h+var_48], ecx
0x180061f26  mov     ecx, [rdi+258h]
0x180061f2c  mov     [rsp+78h+var_50], ecx
0x180061f30  lea     rcx, aCsmsconcatenat_3; "CSmsConcatenateStore::SaveMessage"
0x180061f37  mov     dword ptr [rsp+78h+lpOverlapped], ebp
0x180061f3b  call    ?LogSmsRouterInfo@@YAXPEADK0ZZ; LogSmsRouterInfo(char *,ulong,char *,...)
0x180061f40  mov     eax, ebx
0x180061f42  add     rsp, 58h
0x180061f46  pop     rdi
0x180061f47  pop     rsi
0x180061f48  pop     rbp
0x180061f49  pop     rbx
0x180061f4a  retn
```
