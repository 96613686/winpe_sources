# JCJobInit

- ea: `0x180014e7c`
- end: `0x18001506b`
- name: `JCJobInit`
- size: `495`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18001283c`

## callees

- `0x1800028d8`
- `0x18000ae40`
- `0x1800127d0`
- `0x180014e7c`
- `0x1800160ec`
- `0x1800166a0`
- `0x18001a658`
- `0x18001d5bc`

## import_xrefs

- `KERNEL32!GetTempFileNameW` at `0x180015000`
- `KERNEL32!GetTempFileNameW` at `0x180015000`
- `KERNEL32!GetTempPathW` at `0x180014fe2`
- `KERNEL32!GetTempPathW` at `0x180014fe2`
- `KERNEL32!DeleteFileW` at `0x180014efb`
- `KERNEL32!DeleteFileW` at `0x180014efb`
- `KERNEL32!SetLastError` at `0x18001502d`
- `KERNEL32!SetLastError` at `0x18001502d`
- `KERNEL32!LocalFree` at `0x180014edc`
- `KERNEL32!LocalFree` at `0x180014f0d`
- `KERNEL32!LocalFree` at `0x18001503b`
- `KERNEL32!LocalFree` at `0x180014edc`
- `KERNEL32!LocalFree` at `0x180014f0d`
- `KERNEL32!LocalFree` at `0x18001503b`
- `KERNEL32!LocalAlloc` at `0x180014fb3`
- `KERNEL32!LocalAlloc` at `0x180014fc8`
- `KERNEL32!LocalAlloc` at `0x180014fb3`
- `KERNEL32!LocalAlloc` at `0x180014fc8`

## pseudocode

```c
__int64 __fastcall JCJobInit(__int64 a1)
{
  _DWORD *v1; // rsi
  unsigned int v2; // ebx
  bool v4; // zf
  void *v5; // rcx
  const WCHAR *v6; // rcx
  void *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  __int64 v10; // rax
  WCHAR *v11; // rsi
  HLOCAL v12; // rax
  int v13; // eax

  v1 = (_DWORD *)(a1 + 2152);
  v2 = 0;
  if ( (*(_BYTE *)(a1 + 2152) & 8) != 0 )
  {
    v4 = *(_DWORD *)(a1 + 3440) == 0;
    goto LABEL_29;
  }
  if ( *(_DWORD *)(a1 + 3668) )
  {
    BTermUFL();
    BDeletePSFonts(a1);
    *v1 &= ~0x80000000;
  }
  if ( *(_DWORD *)(a1 + 3664) )
  {
    OPFlushToSpool(a1);
    v5 = *(void **)(a1 + 2896);
    if ( v5 )
      LocalFree(v5);
    *(_QWORD *)(a1 + 2896) = 0;
    *(_DWORD *)(a1 + 3664) = 0;
  }
  v6 = *(const WCHAR **)(a1 + 2192);
  if ( v6 )
  {
    DeleteFileW(v6);
    v7 = *(void **)(a1 + 2192);
    if ( v7 )
      LocalFree(v7);
  }
  memset_0(v1, 0, 0x50u);
  *(_OWORD *)(a1 + 724) = 0;
  BAllocateSpoolBuf(a1);
  GSStackInit(a1);
  *(_DWORD *)(a1 + 2240) = *(_DWORD *)(a1 + 136);
  *(_DWORD *)(a1 + 2244) = GetFontCacheSize(a1);
  v8 = *(_QWORD *)(a1 + 96);
  *(_DWORD *)(a1 + 2236) = 0;
  *(_QWORD *)(a1 + 2248) = 0;
  *(_QWORD *)(a1 + 2256) = 0;
  if ( *(_DWORD *)(v8 + 124) <= 1u )
    *(_DWORD *)(a1 + 2236) = 3;
  v9 = *(_DWORD *)(a1 + 3440);
  v4 = v9 == 0;
  if ( !v9 )
  {
    v10 = *(_QWORD *)(a1 + 3464);
    if ( (*(_BYTE *)(v10 + 12) & 1) == 0 || (*(_BYTE *)(v10 + 16) & 1) == 0 )
      goto LABEL_28;
    *(_DWORD *)(a1 + 2208) = 0;
    v11 = (WCHAR *)LocalAlloc(0, 0x208u);
    if ( v11 && (v12 = LocalAlloc(0, 0x208u), (*(_QWORD *)(a1 + 2192) = v12) != 0) )
    {
      if ( !GetTempPathW(0x104u, v11) || !GetTempFileNameW(v11, L"nhr", 0, *(LPWSTR *)(a1 + 2192)) )
        *(_DWORD *)(a1 + 3440) = 1;
    }
    else
    {
      if ( !*(_DWORD *)(a1 + 3440) )
      {
        *(_DWORD *)(a1 + 3440) = 1;
        SetLastError(8u);
      }
      if ( !v11 )
        goto LABEL_26;
    }
    LocalFree(v11);
LABEL_26:
    v13 = *(_DWORD *)(a1 + 3440);
    v4 = v13 == 0;
    if ( v13 )
      goto LABEL_29;
    *(_DWORD *)(a1 + 2236) &= ~2u;
LABEL_28:
    v4 = 1;
  }
LABEL_29:
  LOBYTE(v2) = v4;
  return v2;
}

```

## disassembly

```asm
0x180014e7c  mov     [rsp+arg_0], rbx
0x180014e81  mov     [rsp+arg_8], rsi
0x180014e86  push    rdi
0x180014e87  sub     rsp, 20h
0x180014e8b  lea     rsi, [rcx+868h]
0x180014e92  xor     ebx, ebx
0x180014e94  test    byte ptr [rsi], 8
0x180014e97  mov     rdi, rcx
0x180014e9a  jz      short loc_180014EA7
0x180014e9c  cmp     [rcx+0D70h], ebx
0x180014ea2  jmp     loc_180015056
0x180014ea7  cmp     [rcx+0E54h], ebx
0x180014ead  jz      short loc_180014EC0
0x180014eaf  call    BTermUFL
0x180014eb4  mov     rcx, rdi
0x180014eb7  call    BDeletePSFonts
0x180014ebc  btr     dword ptr [rsi], 1Fh
0x180014ec0  cmp     [rdi+0E50h], ebx
0x180014ec6  jz      short loc_180014EEF
0x180014ec8  mov     rcx, rdi
0x180014ecb  call    OPFlushToSpool
0x180014ed0  mov     rcx, [rdi+0B50h]; hMem
0x180014ed7  test    rcx, rcx
0x180014eda  jz      short loc_180014EE2
0x180014edc  call    cs:__imp_LocalFree
0x180014ee2  mov     [rdi+0B50h], rbx
0x180014ee9  mov     [rdi+0E50h], ebx
0x180014eef  mov     rcx, [rdi+890h]; lpFileName
0x180014ef6  test    rcx, rcx
0x180014ef9  jz      short loc_180014F13
0x180014efb  call    cs:__imp_DeleteFileW
0x180014f01  mov     rcx, [rdi+890h]; hMem
0x180014f08  test    rcx, rcx
0x180014f0b  jz      short loc_180014F13
0x180014f0d  call    cs:__imp_LocalFree
0x180014f13  xor     edx, edx; Val
0x180014f15  mov     rcx, rsi; void *
0x180014f18  lea     r8d, [rdx+50h]; Size
0x180014f1c  call    memset_0
0x180014f21  xorps   xmm0, xmm0
0x180014f24  mov     rcx, rdi
0x180014f27  movups  xmmword ptr [rdi+2D4h], xmm0
0x180014f2e  call    BAllocateSpoolBuf
0x180014f33  mov     rcx, rdi
0x180014f36  call    GSStackInit
0x180014f3b  mov     eax, [rdi+88h]
0x180014f41  mov     rcx, rdi
0x180014f44  mov     [rdi+8C0h], eax
0x180014f4a  call    GetFontCacheSize
0x180014f4f  mov     [rdi+8C4h], eax
0x180014f55  mov     rax, [rdi+60h]
0x180014f59  mov     [rdi+8BCh], ebx
0x180014f5f  mov     [rdi+8C8h], rbx
0x180014f66  mov     [rdi+8D0h], rbx
0x180014f6d  cmp     dword ptr [rax+7Ch], 1
0x180014f71  ja      short loc_180014F7D
0x180014f73  mov     dword ptr [rdi+8BCh], 3
0x180014f7d  mov     eax, [rdi+0D70h]
0x180014f83  test    eax, eax
0x180014f85  jnz     loc_180015056
0x180014f8b  mov     rax, [rdi+0D88h]
0x180014f92  test    byte ptr [rax+0Ch], 1
0x180014f96  jz      loc_180015052
0x180014f9c  test    byte ptr [rax+10h], 1
0x180014fa0  jz      loc_180015052
0x180014fa6  mov     edx, 208h; uBytes
0x180014fab  mov     [rdi+8A0h], ebx
0x180014fb1  xor     ecx, ecx; uFlags
0x180014fb3  call    cs:__imp_LocalAlloc
0x180014fb9  mov     rsi, rax
0x180014fbc  test    rax, rax
0x180014fbf  jz      short loc_180015016
0x180014fc1  mov     edx, 208h; uBytes
0x180014fc6  xor     ecx, ecx; uFlags
0x180014fc8  call    cs:__imp_LocalAlloc
0x180014fce  mov     [rdi+890h], rax
0x180014fd5  test    rax, rax
0x180014fd8  jz      short loc_180015016
0x180014fda  mov     rdx, rsi; lpBuffer
0x180014fdd  mov     ecx, 104h; nBufferLength
0x180014fe2  call    cs:__imp_GetTempPathW
0x180014fe8  test    eax, eax
0x180014fea  jz      short loc_18001500A
0x180014fec  mov     r9, [rdi+890h]; lpTempFileName
0x180014ff3  lea     rdx, PrefixString; "nhr"
0x180014ffa  xor     r8d, r8d; uUnique
0x180014ffd  mov     rcx, rsi; lpPathName
0x180015000  call    cs:__imp_GetTempFileNameW
0x180015006  test    eax, eax
0x180015008  jnz     short loc_180015038
0x18001500a  mov     dword ptr [rdi+0D70h], 1
0x180015014  jmp     short loc_180015038
0x180015016  cmp     [rdi+0D70h], ebx
0x18001501c  jnz     short loc_180015033
0x18001501e  mov     ecx, 8; dwErrCode
0x180015023  mov     dword ptr [rdi+0D70h], 1
0x18001502d  call    cs:__imp_SetLastError
0x180015033  test    rsi, rsi
0x180015036  jz      short loc_180015041
0x180015038  mov     rcx, rsi; hMem
0x18001503b  call    cs:__imp_LocalFree
0x180015041  mov     eax, [rdi+0D70h]
0x180015047  test    eax, eax
0x180015049  jnz     short loc_180015056
0x18001504b  and     dword ptr [rdi+8BCh], 0FFFFFFFDh
0x180015052  mov     eax, ebx
0x180015054  test    eax, eax
0x180015056  mov     rsi, [rsp+28h+arg_8]
0x18001505b  setz    bl
0x18001505e  mov     eax, ebx
0x180015060  mov     rbx, [rsp+28h+arg_0]
0x180015065  add     rsp, 20h
0x180015069  pop     rdi
0x18001506a  retn
```
