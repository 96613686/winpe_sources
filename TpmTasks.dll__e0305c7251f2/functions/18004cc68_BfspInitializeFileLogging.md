# BfspInitializeFileLogging

- ea: `0x18004cc68`
- end: `0x18004cce7`
- name: `BfspInitializeFileLogging`
- size: `127`
- prototype: `__int64 __fastcall(wchar_t *FileName)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180048c3c`

## callees

- `0x18004cc68`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x18004ccc5`
- `api-ms-win-crt-private-l1-1-0!_o__wfopen_s` at `0x18004ccc5`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004ccaa`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004ccaa`

## pseudocode

```c
errno_t __fastcall BfspInitializeFileLogging(wchar_t *FileName)
{
  __int64 v2; // rbx
  __int64 v3; // rbx
  errno_t result; // eax

  if ( !FileLoggingEnabled )
  {
    v2 = -1;
    do
      ++v2;
    while ( FileName[v2] );
    v3 = v2 - 1;
    if ( v3 )
    {
      while ( FileName[v3] != 92 )
      {
        if ( !--v3 )
          return result;
      }
      FileName[v3] = 0;
      CreateDirectoryW(FileName, 0);
      FileName[v3] = 92;
      result = _wfopen_s(&LogFileStream, FileName, L"w");
      if ( LogFileStream )
        FileLoggingEnabled = 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18004cc68  push    rbx
0x18004cc6a  push    rbp
0x18004cc6b  push    rsi
0x18004cc6c  push    rdi
0x18004cc6d  sub     rsp, 28h
0x18004cc71  xor     esi, esi
0x18004cc73  mov     rdi, rcx
0x18004cc76  cmp     cs:FileLoggingEnabled, esi
0x18004cc7c  jnz     short loc_18004CCDE
0x18004cc7e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18004cc82  inc     rbx
0x18004cc85  cmp     [rcx+rbx*2], si
0x18004cc89  jnz     short loc_18004CC82
0x18004cc8b  sub     rbx, 1
0x18004cc8f  jz      short loc_18004CCDE
0x18004cc91  mov     ebp, 5Ch ; '\'
0x18004cc96  cmp     [rcx+rbx*2], bp
0x18004cc9a  jz      short loc_18004CCA4
0x18004cc9c  sub     rbx, 1
0x18004cca0  jnz     short loc_18004CC96
0x18004cca2  jmp     short loc_18004CCDE
0x18004cca4  xor     edx, edx; lpSecurityAttributes
0x18004cca6  mov     [rcx+rbx*2], si
0x18004ccaa  call    cs:__imp_CreateDirectoryW
0x18004ccb0  lea     r8, aW; "w"
0x18004ccb7  mov     [rdi+rbx*2], bp
0x18004ccbb  mov     rdx, rdi; FileName
0x18004ccbe  lea     rcx, LogFileStream; Stream
0x18004ccc5  call    cs:__imp__wfopen_s
0x18004cccb  cmp     cs:LogFileStream, rsi
0x18004ccd2  jz      short loc_18004CCDE
0x18004ccd4  mov     cs:FileLoggingEnabled, 1
0x18004ccde  add     rsp, 28h
0x18004cce2  pop     rdi
0x18004cce3  pop     rsi
0x18004cce4  pop     rbp
0x18004cce5  pop     rbx
0x18004cce6  retn
```
