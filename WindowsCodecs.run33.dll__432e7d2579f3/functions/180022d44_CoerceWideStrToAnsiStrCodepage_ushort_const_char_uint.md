# CoerceWideStrToAnsiStrCodepage(ushort const *,char * *,uint)

- ea: `0x180022d44`
- end: `0x180022e31`
- name: `?CoerceWideStrToAnsiStrCodepage@@YAJPEBGPEAPEADI@Z`
- size: `237`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr, char **, unsigned int)`
- caller_count: `7`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180022b84`
- `0x180023220`
- `0x180055aa4`
- `0x1800d2960`
- `0x1800d6550`
- `0x1800d6b00`
- `0x1800d6d10`

## callees

- `0x180022d44`
- `0x1800bb784`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022d98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022d98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022e22`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180022e22`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180022d84`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180022dd0`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180022d84`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180022dd0`

## pseudocode

```c
__int64 __fastcall CoerceWideStrToAnsiStrCodepage(LPCWCH lpWideCharStr, char **a2, UINT a3)
{
  int v6; // eax
  unsigned int cbMultiByte; // ebx
  unsigned int v8; // eax
  CHAR *lpMultiByteStr; // rax
  char *v10; // rdi
  unsigned int v11; // ebx

  v6 = WideCharToMultiByte(a3, 0, lpWideCharStr, -1, 0, 0, 0, 0);
  cbMultiByte = v6;
  if ( v6 )
  {
    v8 = v6 + 1;
    if ( v8 < cbMultiByte )
    {
      v11 = -2147024362;
    }
    else
    {
      lpMultiByteStr = (CHAR *)CoTaskMemAlloc(v8);
      v10 = lpMultiByteStr;
      if ( lpMultiByteStr )
      {
        if ( WideCharToMultiByte(a3, 0, lpWideCharStr, -1, lpMultiByteStr, cbMultiByte, 0, 0) )
        {
          v11 = 0;
          *a2 = v10;
        }
        else
        {
          v11 = -2003292412;
          if ( (_DWORD)g_doStackCaptures )
            DoStackCapture(-2003292412);
          CoTaskMemFree(v10);
        }
        return v11;
      }
      v11 = -2147024882;
    }
  }
  else
  {
    v11 = -2147024809;
  }
  if ( (_DWORD)g_doStackCaptures )
    DoStackCapture(v11);
  return v11;
}

```

## disassembly

```asm
0x180022d44  mov     rax, rsp
0x180022d47  push    rbx
0x180022d48  push    rbp
0x180022d49  push    rsi
0x180022d4a  push    rdi
0x180022d4b  push    r14
0x180022d4d  sub     rsp, 40h
0x180022d51  mov     qword ptr [rax-30h], 0
0x180022d59  mov     ebp, r8d
0x180022d5c  mov     qword ptr [rax-38h], 0
0x180022d64  mov     r8, rcx; lpWideCharStr
0x180022d67  mov     rsi, rdx
0x180022d6a  mov     dword ptr [rax-40h], 0
0x180022d71  mov     r14, rcx
0x180022d74  mov     qword ptr [rax-48h], 0
0x180022d7c  mov     ecx, ebp; CodePage
0x180022d7e  or      r9d, 0FFFFFFFFh; cchWideChar
0x180022d82  xor     edx, edx; dwFlags
0x180022d84  call    cs:__imp_WideCharToMultiByte
0x180022d8a  mov     ebx, eax
0x180022d8c  test    eax, eax
0x180022d8e  jz      short loc_180022E03
0x180022d90  inc     eax
0x180022d92  cmp     eax, ebx
0x180022d94  jb      short loc_180022DEC
0x180022d96  mov     ecx, eax; cb
0x180022d98  call    cs:__imp_CoTaskMemAlloc
0x180022d9e  mov     rdi, rax
0x180022da1  test    rax, rax
0x180022da4  jz      loc_180022E2A
0x180022daa  mov     [rsp+68h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180022db3  or      r9d, 0FFFFFFFFh; cchWideChar
0x180022db7  mov     [rsp+68h+lpDefaultChar], 0; lpDefaultChar
0x180022dc0  mov     r8, r14; lpWideCharStr
0x180022dc3  mov     [rsp+68h+cbMultiByte], ebx; cbMultiByte
0x180022dc7  xor     edx, edx; dwFlags
0x180022dc9  mov     ecx, ebp; CodePage
0x180022dcb  mov     [rsp+68h+lpMultiByteStr], rax; lpMultiByteStr
0x180022dd0  call    cs:__imp_WideCharToMultiByte
0x180022dd6  test    eax, eax
0x180022dd8  jz      short loc_180022E0A
0x180022dda  xor     ebx, ebx
0x180022ddc  mov     [rsi], rdi
0x180022ddf  mov     eax, ebx
0x180022de1  add     rsp, 40h
0x180022de5  pop     r14
0x180022de7  pop     rdi
0x180022de8  pop     rsi
0x180022de9  pop     rbp
0x180022dea  pop     rbx
0x180022deb  retn
0x180022dec  mov     ebx, 80070216h
0x180022df1  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180022df8  jz      short loc_180022DDF
0x180022dfa  mov     ecx, ebx; int
0x180022dfc  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180022e01  jmp     short loc_180022DDF
0x180022e03  mov     ebx, 80070057h
0x180022e08  jmp     short loc_180022DF1
0x180022e0a  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180022e11  mov     ebx, 88982F04h
0x180022e16  jz      short loc_180022E1F
0x180022e18  mov     ecx, ebx; int
0x180022e1a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180022e1f  mov     rcx, rdi; pv
0x180022e22  call    cs:__imp_CoTaskMemFree
0x180022e28  jmp     short loc_180022DDF
0x180022e2a  mov     ebx, 8007000Eh
0x180022e2f  jmp     short loc_180022DF1
```
