# CAxisServHelper::CreateDirectoryWithAcls(ushort *)

- ea: `0x18000a2fc`
- end: `0x18000a3a5`
- name: `?CreateDirectoryWithAcls@CAxisServHelper@@QEAAJPEAG@Z`
- size: `169`
- prototype: `int(CAxisServHelper *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000bf6c`

## callees

- `0x18000725c`
- `0x18000a2fc`
- `0x18000d914`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a340`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a340`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000a336`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18000a336`

## string_xrefs

- `0x18000a36d`: `Failed to Restamp Temp Directory Folder. Error 0x%x`

## pseudocode

```c
__int64 __fastcall CAxisServHelper::CreateDirectoryWithAcls(CAxisServHelper *this, unsigned __int16 *a2)
{
  void *v2; // rax
  unsigned int v5; // ebx
  signed int LastError; // eax
  CAxisServHelper *v7; // rcx
  int v8; // eax
  int v10; // [rsp+20h] [rbp-38h]
  struct _SECURITY_ATTRIBUTES v11; // [rsp+30h] [rbp-28h] BYREF

  v2 = (void *)*((_QWORD *)this + 131);
  *(_QWORD *)&v11.nLength = 24;
  *(_QWORD *)&v11.bInheritHandle = 1;
  v11.lpSecurityDescriptor = v2;
  v5 = 0;
  if ( !CreateDirectoryW(a2, &v11) )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError == 183 )
    {
      v8 = CAxisServHelper::ReStampFileDacl(v7, a2, *((struct _ACL **)this + 132));
      v5 = v8;
      if ( v8 < 0 )
      {
        v10 = v8;
        AxISEvents::DebugMsg(
          (AxISEvents *)&qword_180021AD8,
          8u,
          2u,
          L"Failed to Restamp Temp Directory Folder. Error 0x%x",
          v10);
      }
    }
    else if ( LastError > 0 )
    {
      return (unsigned __int16)LastError | 0x80070000;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x18000a2fc  mov     r11, rsp
0x18000a2ff  mov     [r11+8], rbx
0x18000a303  mov     [r11+10h], rsi
0x18000a307  push    rdi
0x18000a308  sub     rsp, 50h
0x18000a30c  mov     rax, [rcx+418h]
0x18000a313  mov     rdi, rdx
0x18000a316  mov     rsi, rcx
0x18000a319  mov     qword ptr [r11-28h], 18h
0x18000a321  mov     rcx, rdi; lpPathName
0x18000a324  mov     qword ptr [r11-18h], 1
0x18000a32c  lea     rdx, [r11-28h]; lpSecurityAttributes
0x18000a330  mov     [r11-20h], rax
0x18000a334  xor     ebx, ebx
0x18000a336  call    cs:__imp_CreateDirectoryW
0x18000a33c  test    eax, eax
0x18000a33e  jnz     short loc_18000A393
0x18000a340  call    cs:__imp_GetLastError
0x18000a346  mov     ebx, eax
0x18000a348  cmp     eax, 0B7h
0x18000a34d  jnz     short loc_18000A386
0x18000a34f  mov     r8, [rsi+420h]; struct _ACL *
0x18000a356  mov     rdx, rdi; unsigned __int16 *
0x18000a359  call    ?ReStampFileDacl@CAxisServHelper@@QEAAJPEAGPEAU_ACL@@@Z; CAxisServHelper::ReStampFileDacl(ushort *,_ACL *)
0x18000a35e  mov     ebx, eax
0x18000a360  test    eax, eax
0x18000a362  jns     short loc_18000A393
0x18000a364  mov     edx, 8; unsigned int
0x18000a369  mov     [rsp+58h+var_38], eax
0x18000a36d  lea     r9, aFailedToRestam; "Failed to Restamp Temp Directory Folder"...
0x18000a374  lea     rcx, qword_180021AD8; this
0x18000a37b  lea     r8d, [rdx-6]; unsigned __int8
0x18000a37f  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x18000a384  jmp     short loc_18000A393
0x18000a386  test    eax, eax
0x18000a388  jle     short loc_18000A393
0x18000a38a  movzx   ebx, ax
0x18000a38d  or      ebx, 80070000h
0x18000a393  mov     rsi, [rsp+58h+arg_8]
0x18000a398  mov     eax, ebx
0x18000a39a  mov     rbx, [rsp+58h+arg_0]
0x18000a39f  add     rsp, 50h
0x18000a3a3  pop     rdi
0x18000a3a4  retn
```
