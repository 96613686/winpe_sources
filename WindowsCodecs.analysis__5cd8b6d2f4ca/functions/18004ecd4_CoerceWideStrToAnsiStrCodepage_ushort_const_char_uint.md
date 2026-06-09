# CoerceWideStrToAnsiStrCodepage(ushort const *,char * *,uint)

- ea: `0x18004ecd4`
- end: `0x18004edde`
- name: `?CoerceWideStrToAnsiStrCodepage@@YAJPEBGPEAPEADI@Z`
- size: `266`
- prototype: `__int64 __fastcall(LPCWCH lpWideCharStr, char **, unsigned int)`
- caller_count: `7`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180048d3c`
- `0x18004eb0c`
- `0x18004f1e0`
- `0x1800d52f0`
- `0x1800d9000`
- `0x1800d95e0`
- `0x1800d97f0`

## callees

- `0x18004ecd4`
- `0x1800bd9d4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004ed32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004ed32`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004edc9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004edc9`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18004ed14`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18004ed70`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18004ed14`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18004ed70`

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
0x18004ecd4  mov     rax, rsp
0x18004ecd7  push    rbx
0x18004ecd8  push    rbp
0x18004ecd9  push    rsi
0x18004ecda  push    rdi
0x18004ecdb  push    r14
0x18004ecdd  sub     rsp, 40h
0x18004ece1  mov     qword ptr [rax-30h], 0
0x18004ece9  mov     ebp, r8d
0x18004ecec  mov     qword ptr [rax-38h], 0
0x18004ecf4  mov     r8, rcx; lpWideCharStr
0x18004ecf7  mov     rsi, rdx
0x18004ecfa  mov     dword ptr [rax-40h], 0
0x18004ed01  mov     r14, rcx
0x18004ed04  mov     qword ptr [rax-48h], 0
0x18004ed0c  mov     ecx, ebp; CodePage
0x18004ed0e  or      r9d, 0FFFFFFFFh; cchWideChar
0x18004ed12  xor     edx, edx; dwFlags
0x18004ed14  call    cs:__imp_WideCharToMultiByte
0x18004ed1b  nop     dword ptr [rax+rax+00h]
0x18004ed20  mov     ebx, eax
0x18004ed22  test    eax, eax
0x18004ed24  jz      loc_18004EDAA
0x18004ed2a  inc     eax
0x18004ed2c  cmp     eax, ebx
0x18004ed2e  jb      short loc_18004ED93
0x18004ed30  mov     ecx, eax; cb
0x18004ed32  call    cs:__imp_CoTaskMemAlloc
0x18004ed39  nop     dword ptr [rax+rax+00h]
0x18004ed3e  mov     rdi, rax
0x18004ed41  test    rax, rax
0x18004ed44  jz      loc_18004EDD7
0x18004ed4a  mov     [rsp+68h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x18004ed53  or      r9d, 0FFFFFFFFh; cchWideChar
0x18004ed57  mov     [rsp+68h+lpDefaultChar], 0; lpDefaultChar
0x18004ed60  mov     r8, r14; lpWideCharStr
0x18004ed63  mov     [rsp+68h+cbMultiByte], ebx; cbMultiByte
0x18004ed67  xor     edx, edx; dwFlags
0x18004ed69  mov     ecx, ebp; CodePage
0x18004ed6b  mov     [rsp+68h+lpMultiByteStr], rax; lpMultiByteStr
0x18004ed70  call    cs:__imp_WideCharToMultiByte
0x18004ed77  nop     dword ptr [rax+rax+00h]
0x18004ed7c  test    eax, eax
0x18004ed7e  jz      short loc_18004EDB1
0x18004ed80  xor     ebx, ebx
0x18004ed82  mov     [rsi], rdi
0x18004ed85  mov     eax, ebx
0x18004ed87  add     rsp, 40h
0x18004ed8b  pop     r14
0x18004ed8d  pop     rdi
0x18004ed8e  pop     rsi
0x18004ed8f  pop     rbp
0x18004ed90  pop     rbx
0x18004ed91  retn
0x18004ed93  mov     ebx, 80070216h
0x18004ed98  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18004ed9f  jz      short loc_18004ED85
0x18004eda1  mov     ecx, ebx; int
0x18004eda3  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18004eda8  jmp     short loc_18004ED85
0x18004edaa  mov     ebx, 80070057h
0x18004edaf  jmp     short loc_18004ED98
0x18004edb1  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18004edb8  mov     ebx, 88982F04h
0x18004edbd  jz      short loc_18004EDC6
0x18004edbf  mov     ecx, ebx; int
0x18004edc1  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18004edc6  mov     rcx, rdi; pv
0x18004edc9  call    cs:__imp_CoTaskMemFree
0x18004edd0  nop     dword ptr [rax+rax+00h]
0x18004edd5  jmp     short loc_18004ED85
0x18004edd7  mov     ebx, 8007000Eh
0x18004eddc  jmp     short loc_18004ED98
```
