# DavQueryUrlCacheEntry

- ea: `0x18001bb00`
- end: `0x18001bbd8`
- name: `DavQueryUrlCacheEntry`
- size: `216`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180014fa0`
- `0x18001507c`
- `0x1800196d0`

## callees

- `0x18000b81c`
- `0x18001bb00`
- `0x18002b3bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bbba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bbba`
- `KERNEL32!LocalFree` at `0x18001bb61`
- `KERNEL32!LocalFree` at `0x18001bbb2`
- `KERNEL32!LocalFree` at `0x18001bb61`
- `KERNEL32!LocalFree` at `0x18001bbb2`
- `KERNEL32!LocalAlloc` at `0x18001bb2f`
- `KERNEL32!LocalAlloc` at `0x18001bb2f`

## pseudocode

```c
__int64 __fastcall DavQueryUrlCacheEntry(__int64 a1)
{
  unsigned int v3; // eax
  unsigned int v4; // ebp
  HLOCAL v5; // rax
  __int64 v6; // rcx
  void *v7; // rdi
  DWORD Entry; // eax
  DWORD LastError; // ebx
  unsigned int i; // [rsp+60h] [rbp+8h] BYREF

  if ( *(_QWORD *)(a1 + 608) )
    return 0;
  v3 = 584;
  v4 = 0;
  for ( i = 584; ; v3 = i )
  {
    v5 = LocalAlloc(0x40u, v3);
    v7 = v5;
    if ( !v5 )
    {
      LastError = GetLastError();
      if ( LastError )
        return LastError;
LABEL_14:
      *(_QWORD *)(a1 + 608) = v7;
      return LastError;
    }
    Entry = TfsGetEntry(v6, *(_QWORD *)(a1 + 584), (__int64)v5, &i);
    LastError = Entry;
    if ( !Entry )
      goto LABEL_14;
    if ( Entry != 122 )
      break;
    ++v4;
    LocalFree(v7);
    if ( v4 >= 2 )
      return LastError;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_dS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      242,
      (unsigned int)WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids,
      Entry,
      *(_QWORD *)(a1 + 584));
  LocalFree(v7);
  return LastError;
}

```

## disassembly

```asm
0x18001bb00  push    rbx
0x18001bb02  push    rbp
0x18001bb03  push    rsi
0x18001bb04  push    rdi
0x18001bb05  sub     rsp, 38h
0x18001bb09  cmp     qword ptr [rcx+260h], 0
0x18001bb11  mov     rsi, rcx
0x18001bb14  jz      short loc_18001BB1D
0x18001bb16  xor     eax, eax
0x18001bb18  jmp     loc_18001BBCF
0x18001bb1d  mov     eax, 248h
0x18001bb22  xor     ebp, ebp
0x18001bb24  mov     [rsp+58h+arg_0], eax
0x18001bb28  mov     edx, eax; uBytes
0x18001bb2a  mov     ecx, 40h ; '@'; uFlags
0x18001bb2f  call    cs:__imp_LocalAlloc
0x18001bb35  mov     rdi, rax
0x18001bb38  test    rax, rax
0x18001bb3b  jz      short loc_18001BBBA
0x18001bb3d  mov     rdx, [rsi+248h]
0x18001bb44  lea     r9, [rsp+58h+arg_0]
0x18001bb49  mov     r8, rax
0x18001bb4c  call    TfsGetEntry
0x18001bb51  mov     ebx, eax
0x18001bb53  test    eax, eax
0x18001bb55  jz      short loc_18001BBC6
0x18001bb57  cmp     eax, 7Ah ; 'z'
0x18001bb5a  jnz     short loc_18001BB72
0x18001bb5c  mov     rcx, rdi; hMem
0x18001bb5f  inc     ebp
0x18001bb61  call    cs:__imp_LocalFree
0x18001bb67  cmp     ebp, 2
0x18001bb6a  jnb     short loc_18001BBCD
0x18001bb6c  mov     eax, [rsp+58h+arg_0]
0x18001bb70  jmp     short loc_18001BB28
0x18001bb72  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bb79  lea     rax, WPP_GLOBAL_Control
0x18001bb80  cmp     rcx, rax
0x18001bb83  jz      short loc_18001BBAF
0x18001bb85  test    byte ptr [rcx+1Ch], 2
0x18001bb89  jz      short loc_18001BBAF
0x18001bb8b  mov     rax, [rsi+248h]
0x18001bb92  lea     r8, WPP_03a38b450eb239675e3775cc0b0f525c_Traceguids
0x18001bb99  mov     rcx, [rcx+10h]
0x18001bb9d  mov     edx, 0F2h
0x18001bba2  mov     r9d, ebx
0x18001bba5  mov     [rsp+58h+var_38], rax
0x18001bbaa  call    WPP_SF_dS
0x18001bbaf  mov     rcx, rdi; hMem
0x18001bbb2  call    cs:__imp_LocalFree
0x18001bbb8  jmp     short loc_18001BBCD
0x18001bbba  call    cs:__imp_GetLastError
0x18001bbc0  mov     ebx, eax
0x18001bbc2  test    eax, eax
0x18001bbc4  jnz     short loc_18001BBCD
0x18001bbc6  mov     [rsi+260h], rdi
0x18001bbcd  mov     eax, ebx
0x18001bbcf  add     rsp, 38h
0x18001bbd3  pop     rdi
0x18001bbd4  pop     rsi
0x18001bbd5  pop     rbp
0x18001bbd6  pop     rbx
0x18001bbd7  retn
```
