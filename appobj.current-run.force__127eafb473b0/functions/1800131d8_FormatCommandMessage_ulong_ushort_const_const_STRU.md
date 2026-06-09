# FormatCommandMessage(ulong,ushort const * * const,STRU *)

- ea: `0x1800131d8`
- end: `0x180013280`
- name: `?FormatCommandMessage@@YAJKQEAPEBGPEAVSTRU@@@Z`
- size: `168`
- prototype: `__int64 __fastcall(DWORD dwMessageId, va_list *Arguments, struct STRU *this)`
- caller_count: `11`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005e40`
- `0x1800067c8`
- `0x180006b6c`
- `0x180006be0`
- `0x180009aac`
- `0x18000c5e0`
- `0x18000c800`
- `0x18000cb80`
- `0x18000fc84`
- `0x180012b28`
- `0x180013030`

## callees

- `0x180002e90`
- `0x1800131d8`
- `0x180013288`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001322d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001322d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180013223`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180013223`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001326d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001326d`

## pseudocode

```c
__int64 __fastcall FormatCommandMessage(DWORD dwMessageId, va_list *Arguments, struct STRU *this)
{
  int v4; // ebx
  signed int LastError; // eax
  unsigned __int8 *Buffer; // [rsp+60h] [rbp+18h] BYREF

  Buffer = 0;
  if ( this )
  {
    if ( FormatMessageW(0x2900u, g_hModule, dwMessageId, 0, (LPWSTR)&Buffer, 0, Arguments) )
      goto LABEL_7;
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 >= 0 )
    {
LABEL_7:
      v4 = STRU::Copy(this, Buffer);
      if ( v4 >= 0 )
        v4 = StripWhiteSpace(this);
    }
    if ( Buffer )
      LocalFree(Buffer);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800131d8  mov     [rsp+arg_0], rbx
0x1800131dd  push    rdi
0x1800131de  sub     rsp, 40h
0x1800131e2  mov     [rsp+48h+Buffer], 0
0x1800131eb  mov     rdi, r8
0x1800131ee  test    r8, r8
0x1800131f1  jnz     short loc_1800131FA
0x1800131f3  mov     ebx, 80070057h
0x1800131f8  jmp     short loc_180013273
0x1800131fa  mov     [rsp+48h+Arguments], rdx; Arguments
0x1800131ff  lea     rax, [rsp+48h+Buffer]
0x180013204  mov     rdx, cs:?g_hModule@@3PEAUHINSTANCE__@@EA; lpSource
0x18001320b  mov     r8d, ecx; dwMessageId
0x18001320e  mov     [rsp+48h+nSize], 0; nSize
0x180013216  mov     ecx, 2900h; dwFlags
0x18001321b  xor     r9d, r9d; dwLanguageId
0x18001321e  mov     [rsp+48h+lpBuffer], rax; lpBuffer
0x180013223  call    cs:__imp_FormatMessageW
0x180013229  test    eax, eax
0x18001322b  jnz     short loc_180013246
0x18001322d  call    cs:__imp_GetLastError
0x180013233  mov     ebx, eax
0x180013235  test    eax, eax
0x180013237  jle     short loc_180013242
0x180013239  movzx   ebx, ax
0x18001323c  or      ebx, 80070000h
0x180013242  test    ebx, ebx
0x180013244  js      short loc_180013263
0x180013246  mov     rdx, [rsp+48h+Buffer]; unsigned __int16 *
0x18001324b  mov     rcx, rdi; this
0x18001324e  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180013253  mov     ebx, eax
0x180013255  test    eax, eax
0x180013257  js      short loc_180013263
0x180013259  mov     rcx, rdi; this
0x18001325c  call    ?StripWhiteSpace@@YAJPEAVSTRU@@@Z; StripWhiteSpace(STRU *)
0x180013261  mov     ebx, eax
0x180013263  mov     rcx, [rsp+48h+Buffer]; hMem
0x180013268  test    rcx, rcx
0x18001326b  jz      short loc_180013273
0x18001326d  call    cs:__imp_LocalFree
0x180013273  mov     eax, ebx
0x180013275  mov     rbx, [rsp+48h+arg_0]
0x18001327a  add     rsp, 40h
0x18001327e  pop     rdi
0x18001327f  retn
```
