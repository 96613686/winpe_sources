# FilterInstantiate(ushort const *,void * *)

- ea: `0x180047c74`
- end: `0x180047d21`
- name: `?FilterInstantiate@@YAJPEBGPEAPEAX@Z`
- size: `173`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180047294`

## callees

- `0x18000b394`
- `0x180047c74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047cbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047cbc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047d02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047d02`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180047ca8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180047ca8`

## string_xrefs

- `0x180047ce1`: `avcore\midi2\libs\midikscommon\midikscommon.cpp`

## pseudocode

```c
__int64 __fastcall FilterInstantiate(const unsigned __int16 *a1, void **a2)
{
  char *FileW; // rbx
  signed int LastError; // eax
  unsigned int v5; // edi
  int v7; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  FileW = (char *)CreateFileW(a1, 0xC0000000, 0, 0, 3u, 0x40000080u, 0);
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
    goto LABEL_10;
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError )
  {
    if ( LastError <= 0 )
      goto LABEL_6;
  }
  else
  {
    LOWORD(v5) = 31;
  }
  v5 = (unsigned __int16)v5 | 0x80070000;
LABEL_6:
  if ( (v5 & 0x80000000) == 0 )
  {
LABEL_10:
    *a2 = FileW;
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xDE,
    (unsigned int)"avcore\\midi2\\libs\\midikscommon\\midikscommon.cpp",
    (const char *)v5,
    v7);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  return v5;
}

```

## disassembly

```asm
0x180047c74  mov     rax, rsp
0x180047c77  mov     [rax+8], rbx
0x180047c7b  mov     [rax+10h], rsi
0x180047c7f  push    rdi
0x180047c80  sub     rsp, 40h
0x180047c84  mov     qword ptr [rax-18h], 0
0x180047c8c  mov     rsi, rdx
0x180047c8f  mov     dword ptr [rax-20h], 40000080h
0x180047c96  mov     edx, 0C0000000h; dwDesiredAccess
0x180047c9b  xor     r9d, r9d; lpSecurityAttributes
0x180047c9e  mov     dword ptr [rax-28h], 3
0x180047ca5  xor     r8d, r8d; dwShareMode
0x180047ca8  call    cs:__imp_CreateFileW
0x180047cae  mov     rbx, rax
0x180047cb1  inc     rax
0x180047cb4  test    rax, 0FFFFFFFFFFFFFFFEh
0x180047cba  jnz     short loc_180047D0C
0x180047cbc  call    cs:__imp_GetLastError
0x180047cc2  mov     edi, eax
0x180047cc4  test    eax, eax
0x180047cc6  jnz     short loc_180047CCD
0x180047cc8  lea     edi, [rax+1Fh]
0x180047ccb  jmp     short loc_180047CCF
0x180047ccd  jle     short loc_180047CD8
0x180047ccf  movzx   edi, di
0x180047cd2  or      edi, 80070000h
0x180047cd8  test    edi, edi
0x180047cda  jns     short loc_180047D0C
0x180047cdc  mov     rcx, [rsp+48h]; this
0x180047ce1  lea     r8, aAvcoreMidi2Lib_1; "avcore\\midi2\\libs\\midikscommon\\midi"...
0x180047ce8  mov     r9d, edi; char *
0x180047ceb  mov     edx, 0DEh; void *
0x180047cf0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180047cf5  lea     rcx, [rbx-1]
0x180047cf9  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x180047cfd  ja      short loc_180047D08
0x180047cff  mov     rcx, rbx; hObject
0x180047d02  call    cs:__imp_CloseHandle
0x180047d08  mov     eax, edi
0x180047d0a  jmp     short loc_180047D11
0x180047d0c  mov     [rsi], rbx
0x180047d0f  xor     eax, eax
0x180047d11  mov     rbx, [rsp+48h+arg_0]
0x180047d16  mov     rsi, [rsp+48h+arg_8]
0x180047d1b  add     rsp, 40h
0x180047d1f  pop     rdi
0x180047d20  retn
```
