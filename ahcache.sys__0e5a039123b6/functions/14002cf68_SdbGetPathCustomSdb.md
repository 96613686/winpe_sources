# SdbGetPathCustomSdb

- ea: `0x14002cf68`
- end: `0x14002d031`
- name: `SdbGetPathCustomSdb`
- size: `201`
- prototype: `_BOOL8 __fastcall(int, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x14002d038`

## callees

- `0x1400079f0`
- `0x140007e40`
- `0x14002cf68`
- `0x14002d3f4`
- `0x14003e364`
- `0x140042fec`

## string_xrefs

- `0x14002cffd`: `SdbpGetSystemSdbFilePath failed [%x]`
- `0x14002cfc3`: `SdbGetPathCustomSdb`

## pseudocode

```c
_BOOL8 __fastcall SdbGetPathCustomSdb(int a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v7; // edx
  int v8; // r9d
  int SystemSdbFilePath; // eax
  int v10; // ebx
  const char *v11; // r9
  __int64 v12; // r8
  __int64 v14; // [rsp+20h] [rbp-98h]
  wchar_t pszDest[48]; // [rsp+30h] [rbp-88h] BYREF

  memset(pszDest, 0, 0x56u);
  if ( a3 && (SystemSdbFilePath = SdbpGetCustomSdbFileName(pszDest), v10 = SystemSdbFilePath, SystemSdbFilePath < 0) )
  {
    v11 = "SdbpGetCustomSdbFileName failed [%x]";
    v12 = 1620;
  }
  else
  {
    SystemSdbFilePath = SdbpGetSystemSdbFilePath(a1, v7, 10, v8, (__int64)pszDest, a4);
    v10 = SystemSdbFilePath;
    if ( SystemSdbFilePath >= 0 )
    {
      v10 = 0;
      return v10 >= 0;
    }
    v11 = "SdbpGetSystemSdbFilePath failed [%x]";
    v12 = 1632;
  }
  LODWORD(v14) = SystemSdbFilePath;
  AslLogCallPrintf(1, "SdbGetPathCustomSdb", v12, v11, v14);
  return v10 >= 0;
}

```

## disassembly

```asm
0x14002cf68  push    rbx
0x14002cf6a  push    rsi
0x14002cf6b  push    rdi
0x14002cf6c  sub     rsp, 0A0h
0x14002cf73  mov     rax, cs:__security_cookie
0x14002cf7a  xor     rax, rsp
0x14002cf7d  mov     [rsp+0B8h+var_28], rax
0x14002cf85  xor     edx, edx; Val
0x14002cf87  mov     rbx, r8
0x14002cf8a  mov     rdi, rcx
0x14002cf8d  mov     rsi, r9
0x14002cf90  lea     rcx, [rsp+0B8h+pszDest]; void *
0x14002cf95  lea     r8d, [rdx+56h]; Size
0x14002cf99  call    memset
0x14002cf9e  test    rbx, rbx
0x14002cfa1  jz      short loc_14002CFDA
0x14002cfa3  mov     r8, rbx
0x14002cfa6  lea     rcx, [rsp+0B8h+pszDest]; pszDest
0x14002cfab  call    SdbpGetCustomSdbFileName
0x14002cfb0  mov     ebx, eax
0x14002cfb2  test    eax, eax
0x14002cfb4  jns     short loc_14002CFDA
0x14002cfb6  lea     r9, aSdbpgetcustoms_0; "SdbpGetCustomSdbFileName failed [%x]"
0x14002cfbd  mov     r8d, 654h
0x14002cfc3  lea     rdx, aSdbgetpathcust_0; "SdbGetPathCustomSdb"
0x14002cfca  mov     dword ptr [rsp+0B8h+var_98], eax
0x14002cfce  mov     ecx, 1
0x14002cfd3  call    AslLogCallPrintf
0x14002cfd8  jmp     short loc_14002D00E
0x14002cfda  lea     rax, [rsp+0B8h+pszDest]
0x14002cfdf  mov     [rsp+0B8h+var_90], rsi
0x14002cfe4  mov     r8d, 0Ah
0x14002cfea  mov     [rsp+0B8h+var_98], rax
0x14002cfef  mov     rcx, rdi
0x14002cff2  call    SdbpGetSystemSdbFilePath
0x14002cff7  mov     ebx, eax
0x14002cff9  test    eax, eax
0x14002cffb  jns     short loc_14002D00C
0x14002cffd  lea     r9, aSdbpgetsystems; "SdbpGetSystemSdbFilePath failed [%x]"
0x14002d004  mov     r8d, 660h
0x14002d00a  jmp     short loc_14002CFC3
0x14002d00c  xor     ebx, ebx
0x14002d00e  not     ebx
0x14002d010  shr     ebx, 1Fh
0x14002d013  mov     eax, ebx
0x14002d015  mov     rcx, [rsp+0B8h+var_28]
0x14002d01d  xor     rcx, rsp; StackCookie
0x14002d020  call    __security_check_cookie
0x14002d025  add     rsp, 0A0h
0x14002d02c  pop     rdi
0x14002d02d  pop     rsi
0x14002d02e  pop     rbx
0x14002d02f  retn
```
