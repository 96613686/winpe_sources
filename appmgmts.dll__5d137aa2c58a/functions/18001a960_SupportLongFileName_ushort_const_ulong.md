# SupportLongFileName(ushort const *,ulong *)

- ea: `0x18001a960`
- end: `0x18001ab70`
- name: `?SupportLongFileName@@YAPEAGPEBGPEAK@Z`
- size: `528`
- prototype: `unsigned __int16 *__fastcall(WCHAR *, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18001a140`

## callees

- `0x180002aa0`
- `0x18000cc10`
- `0x18001a960`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001aa46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001aaee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001aa46`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001aaee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a9a4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001aa5b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ab06`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001a9a4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001aa5b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18001ab06`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001aad2`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001ab36`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001aad2`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x18001ab36`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x18001aa29`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x18001aa87`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x18001aa29`
- `api-ms-win-core-processenvironment-l1-1-0!GetCurrentDirectoryW` at `0x18001aa87`

## pseudocode

```c
unsigned __int16 *__fastcall SupportLongFileName(WCHAR *a1, unsigned int *a2)
{
  __int64 v4; // rax
  unsigned int v5; // eax
  unsigned __int16 *v6; // rbx
  const unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // r8
  unsigned __int64 v9; // rdx
  DWORD CurrentDirectoryW; // eax
  unsigned int v11; // ecx
  DWORD v12; // ebp
  unsigned __int16 *v13; // rax
  unsigned __int16 *v14; // rax
  DWORD v15; // eax
  unsigned __int64 v16; // rdx
  unsigned __int16 *v17; // rcx
  DWORD FullPathNameW; // ebp
  unsigned int v19; // eax
  unsigned __int16 *v20; // rax
  DWORD v21; // eax
  LPWSTR FilePart; // [rsp+40h] [rbp+8h] BYREF

  if ( a1 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a1[v4] );
  }
  else
  {
    LODWORD(v4) = 0;
  }
  v5 = v4 + 520;
  *a2 = v5;
  v6 = (unsigned __int16 *)LocalAlloc(0x40u, 2LL * v5);
  if ( !v6 )
    return 0;
  v7 = a1 + 1;
  if ( a1 && *a1 == 92 && *v7 == 92 )
  {
    StringCchCopyW(v6, *a2, L"\\\\?\\UNC\\");
    v8 = a1 + 2;
LABEL_12:
    StringCchCatW(v6, *a2, v8);
    return v6;
  }
  v9 = *a2;
  if ( *v7 == 58 )
  {
    StringCchCopyW(v6, v9, L"\\\\?\\");
    v8 = a1;
    goto LABEL_12;
  }
  if ( *a1 != 92 )
  {
    FilePart = 0;
    StringCchCopyW(v6, v9, L"\\\\?\\");
    FullPathNameW = GetFullPathNameW(a1, *a2 - 4, v6 + 4, &FilePart);
    v19 = *a2;
    if ( FullPathNameW )
    {
      if ( FullPathNameW <= v19 - 4 )
        return v6;
      LocalFree(v6);
      *a2 = FullPathNameW + 520;
      v20 = (unsigned __int16 *)LocalAlloc(0x40u, 2LL * (FullPathNameW + 520));
      v6 = v20;
      if ( !v20 )
        return 0;
      StringCchCopyW(v20, *a2, L"\\\\?\\");
      v21 = GetFullPathNameW(a1, *a2 - 4, v6 + 4, &FilePart);
      if ( v21 && v21 <= *a2 - 4 )
        return v6;
      v16 = *a2;
    }
    else
    {
      v16 = v19;
    }
    v17 = v6;
    goto LABEL_33;
  }
  StringCchCopyW(v6, v9, L"\\\\?\\");
  CurrentDirectoryW = GetCurrentDirectoryW(*a2 - 4, v6 + 4);
  v11 = *a2;
  v12 = CurrentDirectoryW;
  if ( !CurrentDirectoryW )
  {
    v13 = v6;
LABEL_24:
    v16 = v11;
    v17 = v13;
LABEL_33:
    StringCchCopyW(v17, v16, a1);
    return v6;
  }
  if ( CurrentDirectoryW <= v11 - 4 )
  {
    v11 -= 6;
    goto LABEL_23;
  }
  LocalFree(v6);
  *a2 = v12 + 4;
  v14 = (unsigned __int16 *)LocalAlloc(0x40u, 2LL * (v12 + 4));
  v6 = v14;
  if ( v14 )
  {
    StringCchCopyW(v14, *a2, L"\\\\?\\");
    v15 = GetCurrentDirectoryW(*a2 - 4, v6 + 4);
    if ( !v15 || v15 > *a2 - 4 )
    {
      v11 = *a2;
      v13 = v6;
      goto LABEL_24;
    }
    v11 = *a2 - 6;
LABEL_23:
    v13 = v6 + 6;
    goto LABEL_24;
  }
  return 0;
}

```

## disassembly

```asm
0x18001a960  mov     [rsp+arg_8], rbx
0x18001a965  mov     [rsp+arg_10], rbp
0x18001a96a  push    rsi
0x18001a96b  push    rdi
0x18001a96c  push    r14
0x18001a96e  sub     rsp, 20h
0x18001a972  xor     r14d, r14d
0x18001a975  mov     rdi, rdx
0x18001a978  mov     rsi, rcx
0x18001a97b  test    rcx, rcx
0x18001a97e  jnz     short loc_18001A985
0x18001a980  mov     eax, r14d
0x18001a983  jmp     short loc_18001A993
0x18001a985  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001a989  inc     rax
0x18001a98c  cmp     [rcx+rax*2], r14w
0x18001a991  jnz     short loc_18001A989
0x18001a993  add     eax, 208h
0x18001a998  mov     ecx, 40h ; '@'; uFlags
0x18001a99d  mov     [rdx], eax
0x18001a99f  mov     edx, eax
0x18001a9a1  add     rdx, rdx; uBytes
0x18001a9a4  call    cs:__imp_LocalAlloc
0x18001a9aa  mov     rbx, rax
0x18001a9ad  test    rax, rax
0x18001a9b0  jz      loc_18001AB5B
0x18001a9b6  lea     rax, [rsi+2]
0x18001a9ba  test    rsi, rsi
0x18001a9bd  jz      short loc_18001A9E8
0x18001a9bf  cmp     [rsi], r14w
0x18001a9c3  jz      short loc_18001A9E8
0x18001a9c5  cmp     word ptr [rsi], 5Ch ; '\'
0x18001a9c9  jnz     short loc_18001A9E8
0x18001a9cb  cmp     word ptr [rax], 5Ch ; '\'
0x18001a9cf  jnz     short loc_18001A9E8
0x18001a9d1  mov     edx, [rdi]; unsigned __int64
0x18001a9d3  lea     r8, aUnc; "\\\\?\\UNC\\"
0x18001a9da  mov     rcx, rbx; unsigned __int16 *
0x18001a9dd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001a9e2  lea     r8, [rsi+4]
0x18001a9e6  jmp     short loc_18001AA02
0x18001a9e8  cmp     word ptr [rax], 3Ah ; ':'
0x18001a9ec  lea     r8, asc_180030910; "\\\\?\\"
0x18001a9f3  mov     edx, [rdi]; unsigned __int64
0x18001a9f5  mov     rcx, rbx; unsigned __int16 *
0x18001a9f8  jnz     short loc_18001AA11
0x18001a9fa  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001a9ff  mov     r8, rsi; unsigned __int16 *
0x18001aa02  mov     edx, [rdi]; unsigned __int64
0x18001aa04  mov     rcx, rbx; unsigned __int16 *
0x18001aa07  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001aa0c  jmp     loc_18001AB56
0x18001aa11  cmp     word ptr [rsi], 5Ch ; '\'
0x18001aa15  jnz     loc_18001AAB7
0x18001aa1b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001aa20  mov     ecx, [rdi]
0x18001aa22  lea     rdx, [rbx+8]; lpBuffer
0x18001aa26  sub     ecx, 4; nBufferLength
0x18001aa29  call    cs:__imp_GetCurrentDirectoryW
0x18001aa2f  mov     ecx, [rdi]
0x18001aa31  mov     ebp, eax
0x18001aa33  test    eax, eax
0x18001aa35  jnz     short loc_18001AA3C
0x18001aa37  mov     rax, rbx
0x18001aa3a  jmp     short loc_18001AAAD
0x18001aa3c  lea     eax, [rcx-4]
0x18001aa3f  cmp     ebp, eax
0x18001aa41  jbe     short loc_18001AAA6
0x18001aa43  mov     rcx, rbx; hMem
0x18001aa46  call    cs:__imp_LocalFree
0x18001aa4c  lea     eax, [rbp+4]
0x18001aa4f  mov     ecx, 40h ; '@'; uFlags
0x18001aa54  mov     edx, eax
0x18001aa56  add     rdx, rdx; uBytes
0x18001aa59  mov     [rdi], eax
0x18001aa5b  call    cs:__imp_LocalAlloc
0x18001aa61  mov     rbx, rax
0x18001aa64  test    rax, rax
0x18001aa67  jz      loc_18001AB5B
0x18001aa6d  mov     edx, [rdi]; unsigned __int64
0x18001aa6f  lea     r8, asc_180030910; "\\\\?\\"
0x18001aa76  mov     rcx, rax; unsigned __int16 *
0x18001aa79  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001aa7e  mov     ecx, [rdi]
0x18001aa80  lea     rdx, [rbx+8]; lpBuffer
0x18001aa84  sub     ecx, 4; nBufferLength
0x18001aa87  call    cs:__imp_GetCurrentDirectoryW
0x18001aa8d  test    eax, eax
0x18001aa8f  jz      short loc_18001AA9F
0x18001aa91  mov     edx, [rdi]
0x18001aa93  lea     ecx, [rdx-4]
0x18001aa96  cmp     eax, ecx
0x18001aa98  ja      short loc_18001AA9F
0x18001aa9a  lea     ecx, [rdx-6]
0x18001aa9d  jmp     short loc_18001AAA9
0x18001aa9f  mov     ecx, [rdi]
0x18001aaa1  mov     rax, rbx
0x18001aaa4  jmp     short loc_18001AAAD
0x18001aaa6  add     ecx, 0FFFFFFFAh
0x18001aaa9  lea     rax, [rbx+0Ch]
0x18001aaad  mov     edx, ecx
0x18001aaaf  mov     rcx, rax
0x18001aab2  jmp     loc_18001AB4E
0x18001aab7  mov     [rsp+38h+FilePart], r14
0x18001aabc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001aac1  mov     edx, [rdi]
0x18001aac3  lea     r9, [rsp+38h+FilePart]; lpFilePart
0x18001aac8  sub     edx, 4; nBufferLength
0x18001aacb  lea     r8, [rbx+8]; lpBuffer
0x18001aacf  mov     rcx, rsi; lpFileName
0x18001aad2  call    cs:__imp_GetFullPathNameW
0x18001aad8  mov     ebp, eax
0x18001aada  mov     eax, [rdi]
0x18001aadc  test    ebp, ebp
0x18001aade  jnz     short loc_18001AAE4
0x18001aae0  mov     edx, eax
0x18001aae2  jmp     short loc_18001AB4B
0x18001aae4  add     eax, 0FFFFFFFCh
0x18001aae7  cmp     ebp, eax
0x18001aae9  jbe     short loc_18001AB56
0x18001aaeb  mov     rcx, rbx; hMem
0x18001aaee  call    cs:__imp_LocalFree
0x18001aaf4  lea     eax, [rbp+208h]
0x18001aafa  mov     ecx, 40h ; '@'; uFlags
0x18001aaff  mov     edx, eax
0x18001ab01  add     rdx, rdx; uBytes
0x18001ab04  mov     [rdi], eax
0x18001ab06  call    cs:__imp_LocalAlloc
0x18001ab0c  mov     rbx, rax
0x18001ab0f  test    rax, rax
0x18001ab12  jz      short loc_18001AB5B
0x18001ab14  mov     edx, [rdi]; unsigned __int64
0x18001ab16  lea     r8, asc_180030910; "\\\\?\\"
0x18001ab1d  mov     rcx, rax; unsigned __int16 *
0x18001ab20  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001ab25  mov     edx, [rdi]
0x18001ab27  lea     r8, [rbx+8]; lpBuffer
0x18001ab2b  sub     edx, 4; nBufferLength
0x18001ab2e  lea     r9, [rsp+38h+FilePart]; lpFilePart
0x18001ab33  mov     rcx, rsi; lpFileName
0x18001ab36  call    cs:__imp_GetFullPathNameW
0x18001ab3c  test    eax, eax
0x18001ab3e  jz      short loc_18001AB49
0x18001ab40  mov     ecx, [rdi]
0x18001ab42  sub     ecx, 4
0x18001ab45  cmp     eax, ecx
0x18001ab47  jbe     short loc_18001AB56
0x18001ab49  mov     edx, [rdi]; unsigned __int64
0x18001ab4b  mov     rcx, rbx; unsigned __int16 *
0x18001ab4e  mov     r8, rsi; unsigned __int16 *
0x18001ab51  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001ab56  mov     rax, rbx
0x18001ab59  jmp     short loc_18001AB5D
0x18001ab5b  xor     eax, eax
0x18001ab5d  mov     rbx, [rsp+38h+arg_8]
0x18001ab62  mov     rbp, [rsp+38h+arg_10]
0x18001ab67  add     rsp, 20h
0x18001ab6b  pop     r14
0x18001ab6d  pop     rdi
0x18001ab6e  pop     rsi
0x18001ab6f  retn
```
