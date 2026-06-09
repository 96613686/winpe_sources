# CCacheMigration::OpenFiles(void)

- ea: `0x18005f450`
- end: `0x18005f621`
- name: `?OpenFiles@CCacheMigration@@AEAAJXZ`
- size: `465`
- prototype: `__int64 __fastcall(CCacheMigration *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18005e87c`

## callees

- `0x180004374`
- `0x1800391e0`
- `0x18005f450`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f4cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f54c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f5c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f4cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f54c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005f5c7`
- `KERNEL32!CreateFileW` at `0x18005f4bf`
- `KERNEL32!CreateFileW` at `0x18005f53f`
- `KERNEL32!CreateFileW` at `0x18005f5ba`
- `KERNEL32!CreateFileW` at `0x18005f4bf`
- `KERNEL32!CreateFileW` at `0x18005f53f`
- `KERNEL32!CreateFileW` at `0x18005f5ba`

## pseudocode

```c
__int64 __fastcall CCacheMigration::OpenFiles(CCacheMigration *this)
{
  char *v2; // rsi
  signed int LastError; // eax
  unsigned int v4; // ebx
  CHostedCacheMsgEncoding *v5; // rcx
  int v6; // edx
  signed int v7; // eax
  signed int v8; // eax

  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 50, WPP_18b6af83c6ca397905990f7f7c77c73f_Traceguids);
  }
  v2 = (char *)this + 210;
  *((_QWORD *)this + 25) = CreateFileW((LPCWSTR)this + 105, 0x80010000, 0, 0, 3u, 0x10000000u, 0);
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError )
  {
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v6 = 51;
LABEL_27:
      WPP_SF_dS(
        *((_QWORD *)v5 + 12),
        v6,
        (unsigned int)WPP_18b6af83c6ca397905990f7f7c77c73f_Traceguids,
        v4,
        (__int64)v2);
    }
  }
  else
  {
    v2 = (char *)this + 732;
    *((_QWORD *)this + 23) = CreateFileW((LPCWSTR)this + 366, 0x80010000, 0, 0, 3u, 0x10000000u, 0);
    v7 = GetLastError();
    v4 = v7;
    if ( v7 )
    {
      if ( v7 > 0 )
        v4 = (unsigned __int16)v7 | 0x80070000;
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        v6 = 52;
        goto LABEL_27;
      }
    }
    else
    {
      v4 = 0;
      v2 = (char *)this + 1254;
      *((_QWORD *)this + 24) = CreateFileW((LPCWSTR)this + 627, 0x80010000, 0, 0, 3u, 0x10000000u, 0);
      v8 = GetLastError();
      if ( v8 )
      {
        v4 = v8 > 0 ? (unsigned __int16)v8 | 0x80070000 : v8;
        v5 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) )
        {
          v6 = 53;
          goto LABEL_27;
        }
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18005f450  push    rbx
0x18005f452  push    rsi
0x18005f453  push    rdi
0x18005f454  push    r15
0x18005f456  sub     rsp, 48h
0x18005f45a  mov     rdi, rcx
0x18005f45d  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f464  lea     r15, WPP_GLOBAL_Control
0x18005f46b  cmp     rcx, r15
0x18005f46e  jz      short loc_18005F491
0x18005f470  test    byte ptr [rcx+6Ch], 4
0x18005f474  jz      short loc_18005F491
0x18005f476  cmp     byte ptr [rcx+69h], 4
0x18005f47a  jb      short loc_18005F491
0x18005f47c  mov     rcx, [rcx+60h]
0x18005f480  lea     r8, WPP_18b6af83c6ca397905990f7f7c77c73f_Traceguids
0x18005f487  mov     edx, 32h ; '2'
0x18005f48c  call    WPP_SF_
0x18005f491  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18005f49a  lea     rsi, [rdi+0D2h]
0x18005f4a1  mov     rcx, rsi; lpFileName
0x18005f4a4  mov     [rsp+68h+dwFlagsAndAttributes], 10000000h; dwFlagsAndAttributes
0x18005f4ac  xor     r9d, r9d; lpSecurityAttributes
0x18005f4af  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18005f4b7  xor     r8d, r8d; dwShareMode
0x18005f4ba  mov     edx, 80010000h; dwDesiredAccess
0x18005f4bf  call    cs:__imp_CreateFileW
0x18005f4c5  mov     [rdi+0C8h], rax
0x18005f4cc  call    cs:__imp_GetLastError
0x18005f4d2  mov     ebx, eax
0x18005f4d4  test    eax, eax
0x18005f4d6  jz      short loc_18005F511
0x18005f4d8  jle     short loc_18005F4E3
0x18005f4da  movzx   ebx, ax
0x18005f4dd  or      ebx, 80070000h
0x18005f4e3  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f4ea  cmp     rcx, r15
0x18005f4ed  jz      loc_18005F615
0x18005f4f3  test    byte ptr [rcx+6Ch], 4
0x18005f4f7  jz      loc_18005F615
0x18005f4fd  cmp     byte ptr [rcx+69h], 1
0x18005f501  jb      loc_18005F615
0x18005f507  mov     edx, 33h ; '3'
0x18005f50c  jmp     loc_18005F5FD
0x18005f511  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18005f51a  lea     rsi, [rdi+2DCh]
0x18005f521  mov     rcx, rsi; lpFileName
0x18005f524  mov     [rsp+68h+dwFlagsAndAttributes], 10000000h; dwFlagsAndAttributes
0x18005f52c  xor     r9d, r9d; lpSecurityAttributes
0x18005f52f  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18005f537  xor     r8d, r8d; dwShareMode
0x18005f53a  mov     edx, 80010000h; dwDesiredAccess
0x18005f53f  call    cs:__imp_CreateFileW
0x18005f545  mov     [rdi+0B8h], rax
0x18005f54c  call    cs:__imp_GetLastError
0x18005f552  mov     ebx, eax
0x18005f554  test    eax, eax
0x18005f556  jz      short loc_18005F58E
0x18005f558  jle     short loc_18005F563
0x18005f55a  movzx   ebx, ax
0x18005f55d  or      ebx, 80070000h
0x18005f563  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f56a  cmp     rcx, r15
0x18005f56d  jz      loc_18005F615
0x18005f573  test    byte ptr [rcx+6Ch], 4
0x18005f577  jz      loc_18005F615
0x18005f57d  cmp     byte ptr [rcx+69h], 1
0x18005f581  jb      loc_18005F615
0x18005f587  mov     edx, 34h ; '4'
0x18005f58c  jmp     short loc_18005F5FD
0x18005f58e  xor     ebx, ebx
0x18005f590  lea     rsi, [rdi+4E6h]
0x18005f597  mov     [rsp+68h+hTemplateFile], rbx; hTemplateFile
0x18005f59c  xor     r9d, r9d; lpSecurityAttributes
0x18005f59f  mov     [rsp+68h+dwFlagsAndAttributes], 10000000h; dwFlagsAndAttributes
0x18005f5a7  xor     r8d, r8d; dwShareMode
0x18005f5aa  mov     edx, 80010000h; dwDesiredAccess
0x18005f5af  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18005f5b7  mov     rcx, rsi; lpFileName
0x18005f5ba  call    cs:__imp_CreateFileW
0x18005f5c0  mov     [rdi+0C0h], rax
0x18005f5c7  call    cs:__imp_GetLastError
0x18005f5cd  test    eax, eax
0x18005f5cf  jz      short loc_18005F615
0x18005f5d1  jg      short loc_18005F5D7
0x18005f5d3  mov     ebx, eax
0x18005f5d5  jmp     short loc_18005F5E0
0x18005f5d7  movzx   ebx, ax
0x18005f5da  or      ebx, 80070000h
0x18005f5e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18005f5e7  cmp     rcx, r15
0x18005f5ea  jz      short loc_18005F615
0x18005f5ec  test    byte ptr [rcx+6Ch], 4
0x18005f5f0  jz      short loc_18005F615
0x18005f5f2  cmp     byte ptr [rcx+69h], 1
0x18005f5f6  jb      short loc_18005F615
0x18005f5f8  mov     edx, 35h ; '5'
0x18005f5fd  mov     rcx, [rcx+60h]
0x18005f601  lea     r8, WPP_18b6af83c6ca397905990f7f7c77c73f_Traceguids
0x18005f608  mov     r9d, ebx
0x18005f60b  mov     qword ptr [rsp+68h+dwCreationDisposition], rsi
0x18005f610  call    WPP_SF_dS
0x18005f615  mov     eax, ebx
0x18005f617  add     rsp, 48h
0x18005f61b  pop     r15
0x18005f61d  pop     rdi
0x18005f61e  pop     rsi
0x18005f61f  pop     rbx
0x18005f620  retn
```
