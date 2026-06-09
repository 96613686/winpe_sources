# FilterInstantiate(ushort const *,void * *)

- ea: `0x1800271f4`
- end: `0x1800272a1`
- name: `?FilterInstantiate@@YAJPEBGPEAPEAX@Z`
- size: `173`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800267e4`

## callees

- `0x18000a814`
- `0x1800271f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002723c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002723c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027282`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027282`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180027228`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180027228`

## string_xrefs

- `0x180027261`: `avcore\midi2\libs\midikscommon\midikscommon.cpp`

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
0x1800271f4  mov     rax, rsp
0x1800271f7  mov     [rax+8], rbx
0x1800271fb  mov     [rax+10h], rsi
0x1800271ff  push    rdi
0x180027200  sub     rsp, 40h
0x180027204  mov     qword ptr [rax-18h], 0
0x18002720c  mov     rsi, rdx
0x18002720f  mov     dword ptr [rax-20h], 40000080h
0x180027216  mov     edx, 0C0000000h; dwDesiredAccess
0x18002721b  xor     r9d, r9d; lpSecurityAttributes
0x18002721e  mov     dword ptr [rax-28h], 3
0x180027225  xor     r8d, r8d; dwShareMode
0x180027228  call    cs:__imp_CreateFileW
0x18002722e  mov     rbx, rax
0x180027231  inc     rax
0x180027234  test    rax, 0FFFFFFFFFFFFFFFEh
0x18002723a  jnz     short loc_18002728C
0x18002723c  call    cs:__imp_GetLastError
0x180027242  mov     edi, eax
0x180027244  test    eax, eax
0x180027246  jnz     short loc_18002724D
0x180027248  lea     edi, [rax+1Fh]
0x18002724b  jmp     short loc_18002724F
0x18002724d  jle     short loc_180027258
0x18002724f  movzx   edi, di
0x180027252  or      edi, 80070000h
0x180027258  test    edi, edi
0x18002725a  jns     short loc_18002728C
0x18002725c  mov     rcx, [rsp+48h]; this
0x180027261  lea     r8, aAvcoreMidi2Lib_1; "avcore\\midi2\\libs\\midikscommon\\midi"...
0x180027268  mov     r9d, edi; char *
0x18002726b  mov     edx, 0DEh; void *
0x180027270  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027275  lea     rcx, [rbx-1]
0x180027279  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x18002727d  ja      short loc_180027288
0x18002727f  mov     rcx, rbx; hObject
0x180027282  call    cs:__imp_CloseHandle
0x180027288  mov     eax, edi
0x18002728a  jmp     short loc_180027291
0x18002728c  mov     [rsi], rbx
0x18002728f  xor     eax, eax
0x180027291  mov     rbx, [rsp+48h+arg_0]
0x180027296  mov     rsi, [rsp+48h+arg_8]
0x18002729b  add     rsp, 40h
0x18002729f  pop     rdi
0x1800272a0  retn
```
