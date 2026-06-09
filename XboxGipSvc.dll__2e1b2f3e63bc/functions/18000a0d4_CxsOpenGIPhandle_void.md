# CxsOpenGIPhandle(void * *)

- ea: `0x18000a0d4`
- end: `0x18000a1ac`
- name: `?CxsOpenGIPhandle@@YAKPEAPEAX@Z`
- size: `216`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000a600`
- `0x18000b11c`

## callees

- `0x180002b70`
- `0x18000a0d4`
- `0x18000b84c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000a161`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000a161`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a127`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a127`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000a118`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000a118`

## pseudocode

```c
__int64 __fastcall CxsOpenGIPhandle(void **a1)
{
  DWORD i; // ebx
  DWORD v3; // edi
  HANDLE FileW; // rsi
  DWORD LastError; // eax
  __int64 v6; // rdx
  __int64 v7; // r8

  for ( i = 100; ; i += 100 )
  {
    v3 = 0;
    FileW = CreateFileW(L"\\\\.\\XboxGIP", 0xC0000000, 3u, 0, 3u, 0x20000000u, 0);
    if ( FileW != (HANDLE)-1LL )
      break;
    LastError = GetLastError();
    v3 = LastError;
    if ( i >= 0x12C )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, &WPP_4b7fc9b143d0368172f607d8a9267014_Traceguids, LastError);
      }
      break;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, v7, LastError, i);
    }
    Sleep(i);
  }
  *a1 = FileW;
  return v3;
}

```

## disassembly

```asm
0x18000a0d4  push    rbx
0x18000a0d6  push    rbp
0x18000a0d7  push    rsi
0x18000a0d8  push    rdi
0x18000a0d9  push    r14
0x18000a0db  sub     rsp, 40h
0x18000a0df  mov     r14, rcx
0x18000a0e2  lea     rbp, WPP_GLOBAL_Control
0x18000a0e9  mov     ebx, 64h ; 'd'
0x18000a0ee  xor     edi, edi
0x18000a0f0  lea     rcx, FileName; "\\\\.\\XboxGIP"
0x18000a0f7  mov     [rsp+68h+hTemplateFile], rdi; hTemplateFile
0x18000a0fc  xor     r9d, r9d; lpSecurityAttributes
0x18000a0ff  mov     [rsp+68h+dwFlagsAndAttributes], 20000000h; dwFlagsAndAttributes
0x18000a107  mov     edx, 0C0000000h; dwDesiredAccess
0x18000a10c  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18000a114  lea     r8d, [rdi+3]; dwShareMode
0x18000a118  call    cs:__imp_CreateFileW
0x18000a11e  mov     rsi, rax
0x18000a121  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000a125  jnz     short loc_18000A19C
0x18000a127  call    cs:__imp_GetLastError
0x18000a12d  mov     edi, eax
0x18000a12f  cmp     ebx, 12Ch
0x18000a135  jnb     short loc_18000A16C
0x18000a137  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a13e  cmp     rcx, rbp
0x18000a141  jz      short loc_18000A15F
0x18000a143  test    byte ptr [rcx+1Ch], 4
0x18000a147  jz      short loc_18000A15F
0x18000a149  cmp     byte ptr [rcx+19h], 3
0x18000a14d  jb      short loc_18000A15F
0x18000a14f  mov     rcx, [rcx+10h]
0x18000a153  mov     r9d, eax
0x18000a156  mov     [rsp+68h+dwCreationDisposition], ebx
0x18000a15a  call    WPP_SF_Dd
0x18000a15f  mov     ecx, ebx; dwMilliseconds
0x18000a161  call    cs:__imp_Sleep
0x18000a167  add     ebx, 64h ; 'd'
0x18000a16a  jmp     short loc_18000A0EE
0x18000a16c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a173  cmp     rcx, rbp
0x18000a176  jz      short loc_18000A19C
0x18000a178  test    byte ptr [rcx+1Ch], 4
0x18000a17c  jz      short loc_18000A19C
0x18000a17e  cmp     byte ptr [rcx+19h], 2
0x18000a182  jb      short loc_18000A19C
0x18000a184  mov     rcx, [rcx+10h]
0x18000a188  lea     r8, WPP_4b7fc9b143d0368172f607d8a9267014_Traceguids
0x18000a18f  mov     edx, 2Fh ; '/'
0x18000a194  mov     r9d, eax
0x18000a197  call    WPP_SF_D
0x18000a19c  mov     [r14], rsi
0x18000a19f  mov     eax, edi
0x18000a1a1  add     rsp, 40h
0x18000a1a5  pop     r14
0x18000a1a7  pop     rdi
0x18000a1a8  pop     rsi
0x18000a1a9  pop     rbp
0x18000a1aa  pop     rbx
0x18000a1ab  retn
```
