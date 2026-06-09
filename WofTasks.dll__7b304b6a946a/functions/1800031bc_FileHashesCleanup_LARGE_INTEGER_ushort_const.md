# FileHashesCleanup(_LARGE_INTEGER,ushort const *)

- ea: `0x1800031bc`
- end: `0x18000327b`
- name: `?FileHashesCleanup@@YAXT_LARGE_INTEGER@@PEBG@Z`
- size: `191`
- prototype: `void __fastcall(union _LARGE_INTEGER, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, loader_planting`

## callers

- `0x1800038dc`

## callees

- `0x1800031bc`
- `0x18000466c`
- `0x1800051c0`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180003231`
- `msvcrt!swprintf_s` at `0x180003231`
- `KERNEL32!DeleteFileW` at `0x180003248`
- `KERNEL32!DeleteFileW` at `0x180003248`

## pseudocode

```c
void __fastcall FileHashesCleanup(union _LARGE_INTEGER a1, const unsigned __int16 *a2)
{
  union _LARGE_INTEGER v4; // rbx
  wchar_t Buffer[264]; // [rsp+40h] [rbp-228h] BYREF

  if ( (unsigned __int64)(a1.QuadPart - 1) <= 0x7FFFFFFFFFFFFFFDLL )
  {
    for ( v4.QuadPart = 0; v4.QuadPart < a1.QuadPart; ++v4.QuadPart )
    {
      if ( swprintf_s(Buffer, 0x104u, L"%s%s\\%s%016I64X", a2, L"\\System Volume Information", L"WIMH.", v4.QuadPart) >= 0 )
      {
        ReportDataSourceIdDeletion(v4);
        DeleteFileW(Buffer);
      }
    }
  }
}

```

## disassembly

```asm
0x1800031bc  mov     [rsp+arg_10], rbx
0x1800031c1  mov     [rsp+arg_18], rsi
0x1800031c6  push    rdi
0x1800031c7  sub     rsp, 260h
0x1800031ce  mov     rax, cs:__security_cookie
0x1800031d5  xor     rax, rsp
0x1800031d8  mov     [rsp+268h+var_18], rax
0x1800031e0  lea     rax, [rcx-1]
0x1800031e4  mov     rdi, rcx
0x1800031e7  mov     rcx, 7FFFFFFFFFFFFFFDh
0x1800031f1  mov     rsi, rdx
0x1800031f4  cmp     rax, rcx
0x1800031f7  ja      short loc_180003256
0x1800031f9  xor     ebx, ebx
0x1800031fb  test    rdi, rdi
0x1800031fe  jle     short loc_180003256
0x180003200  lea     rax, aWimh; "WIMH."
0x180003207  mov     [rsp+268h+var_238], rbx
0x18000320c  mov     [rsp+268h+var_240], rax
0x180003211  lea     r8, aSSS016i64x; "%s%s\\%s%016I64X"
0x180003218  lea     rax, aSystemVolumeIn; "\\System Volume Information"
0x18000321f  mov     r9, rsi
0x180003222  mov     edx, 104h; BufferCount
0x180003227  mov     [rsp+268h+var_248], rax
0x18000322c  lea     rcx, [rsp+268h+Buffer]; Buffer
0x180003231  call    cs:__imp_swprintf_s
0x180003237  test    eax, eax
0x180003239  js      short loc_18000324E
0x18000323b  mov     rcx, rbx; union _LARGE_INTEGER
0x18000323e  call    ?ReportDataSourceIdDeletion@@YAJT_LARGE_INTEGER@@@Z; ReportDataSourceIdDeletion(_LARGE_INTEGER)
0x180003243  lea     rcx, [rsp+268h+Buffer]; lpFileName
0x180003248  call    cs:__imp_DeleteFileW
0x18000324e  inc     rbx
0x180003251  cmp     rbx, rdi
0x180003254  jl      short loc_180003200
0x180003256  mov     rcx, [rsp+268h+var_18]
0x18000325e  xor     rcx, rsp; StackCookie
0x180003261  call    __security_check_cookie
0x180003266  lea     r11, [rsp+268h+var_8]
0x18000326e  mov     rbx, [r11+20h]
0x180003272  mov     rsi, [r11+28h]
0x180003276  mov     rsp, r11
0x180003279  pop     rdi
0x18000327a  retn
```
