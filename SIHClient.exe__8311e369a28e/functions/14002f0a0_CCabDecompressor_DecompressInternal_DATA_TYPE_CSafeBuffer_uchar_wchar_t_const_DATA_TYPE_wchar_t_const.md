# CCabDecompressor::DecompressInternal(DATA_TYPE,CSafeBuffer<uchar> *,wchar_t const *,DATA_TYPE,wchar_t const *)

- ea: `0x14002f0a0`
- end: `0x14002f18c`
- name: `?DecompressInternal@CCabDecompressor@@AEAAJW4DATA_TYPE@@PEAV?$CSafeBuffer@E@@PEB_W02@Z`
- size: `236`
- prototype: `__int64 __fastcall(CCabDecompressor *this, int, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14002fc9c`

## callees

- `0x140008de4`
- `0x14002ed50`
- `0x14002f0a0`

## import_xrefs

- `Cabinet!__imp_FDICopy` at `0x14002f103`
- `Cabinet!__imp_FDICopy` at `0x14002f103`

## string_xrefs

- `0x14002f146`: `C:\__w\1\s\src\Client\lib\CabDecompressor\CabDecompressor.cpp`
- `0x14002f167`: `C:\__w\1\s\src\Client\lib\CabDecompressor\CabDecompressor.cpp`

## pseudocode

```c
__int64 __fastcall CCabDecompressor::DecompressInternal(
        CCabDecompressor *this,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  CHAR *v7; // rdx
  BOOL v8; // eax
  int v9; // r8d
  int LastFDIErrorHr; // edi
  int v11; // ebx
  int pfnfdin; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *((_DWORD *)this + 35) = a5;
  *((_DWORD *)this + 34) = a2;
  if ( a2 )
    *((_QWORD *)this + 15) = a4;
  else
    *((_QWORD *)this + 7) = a3;
  v7 = (CHAR *)*((_QWORD *)this + 6);
  *((_QWORD *)this + 16) = a6;
  v8 = FDICopy(*((HFDI *)this + 5), v7, (LPSTR)&pszCabPath, 0, CCabDecompressor::Notification, 0, this);
  v9 = -2147467260;
  if ( v8 )
  {
    LastFDIErrorHr = 0;
  }
  else
  {
    LastFDIErrorHr = CCabDecompressor::GetLastFDIErrorHr(this);
    if ( LastFDIErrorHr == v9 && *((_DWORD *)this + 42) == -2145124340 )
      return 0;
  }
  if ( LastFDIErrorHr == v9 )
  {
    v11 = *((_DWORD *)this + 42);
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1FE,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\CabDecompressor\\CabDecompressor.cpp",
        (const char *)(unsigned int)v11,
        pfnfdin);
      return (unsigned int)v11;
    }
    goto LABEL_12;
  }
  if ( LastFDIErrorHr < 0 )
  {
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1FF,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\CabDecompressor\\CabDecompressor.cpp",
      (const char *)(unsigned int)LastFDIErrorHr,
      pfnfdin);
    return (unsigned int)LastFDIErrorHr;
  }
  return 0;
}

```

## disassembly

```asm
0x14002f0a0  mov     [rsp+arg_0], rbx
0x14002f0a5  push    rdi
0x14002f0a6  sub     rsp, 40h
0x14002f0aa  mov     eax, [rsp+48h+arg_20]
0x14002f0ae  mov     rbx, rcx
0x14002f0b1  mov     [rcx+8Ch], eax
0x14002f0b7  mov     [rcx+88h], edx
0x14002f0bd  test    edx, edx
0x14002f0bf  jnz     short loc_14002F0C7
0x14002f0c1  mov     [rcx+38h], r8
0x14002f0c5  jmp     short loc_14002F0CB
0x14002f0c7  mov     [rcx+78h], r9
0x14002f0cb  mov     rax, [rsp+48h+arg_28]
0x14002f0d0  lea     r8, pszCabPath; pszCabPath
0x14002f0d7  mov     rdx, [rcx+30h]; pszCabinet
0x14002f0db  xor     r9d, r9d; flags
0x14002f0de  mov     [rcx+80h], rax
0x14002f0e5  lea     rax, ?Notification@CCabDecompressor@@CA_JW4FDINOTIFICATIONTYPE@@PEAUFDINOTIFICATION@@@Z; CCabDecompressor::Notification(FDINOTIFICATIONTYPE,FDINOTIFICATION *)
0x14002f0ec  mov     rcx, [rcx+28h]; hfdi
0x14002f0f0  mov     [rsp+48h+pvUser], rbx; pvUser
0x14002f0f5  mov     [rsp+48h+pfnfdid], 0; pfnfdid
0x14002f0fe  mov     [rsp+48h+pfnfdin], rax; int
0x14002f103  call    cs:__imp_FDICopy
0x14002f109  mov     r8d, 80004004h
0x14002f10f  test    eax, eax
0x14002f111  jz      short loc_14002F117
0x14002f113  xor     edi, edi
0x14002f115  jmp     short loc_14002F132
0x14002f117  mov     rcx, rbx; this
0x14002f11a  call    ?GetLastFDIErrorHr@CCabDecompressor@@QEAAJXZ; CCabDecompressor::GetLastFDIErrorHr(void)
0x14002f11f  mov     edi, eax
0x14002f121  cmp     eax, r8d
0x14002f124  jnz     short loc_14002F132
0x14002f126  cmp     dword ptr [rbx+0A8h], 8024000Ch
0x14002f130  jz      short loc_14002F17F
0x14002f132  cmp     edi, r8d
0x14002f135  jnz     short loc_14002F15E
0x14002f137  mov     ebx, [rbx+0A8h]
0x14002f13d  test    ebx, ebx
0x14002f13f  jns     short loc_14002F162
0x14002f141  mov     rcx, [rsp+48h]; this
0x14002f146  lea     r8, aCW1SSrcClientL_3; "C:\\__w\\1\\s\\src\\Client\\lib\\CabDec"...
0x14002f14d  mov     r9d, ebx; char *
0x14002f150  mov     edx, 1FEh; void *
0x14002f155  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002f15a  mov     eax, ebx
0x14002f15c  jmp     short loc_14002F181
0x14002f15e  test    edi, edi
0x14002f160  jns     short loc_14002F17F
0x14002f162  mov     rcx, [rsp+48h]; this
0x14002f167  lea     r8, aCW1SSrcClientL_3; "C:\\__w\\1\\s\\src\\Client\\lib\\CabDec"...
0x14002f16e  mov     r9d, edi; char *
0x14002f171  mov     edx, 1FFh; void *
0x14002f176  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002f17b  mov     eax, edi
0x14002f17d  jmp     short loc_14002F181
0x14002f17f  xor     eax, eax
0x14002f181  mov     rbx, [rsp+48h+arg_0]
0x14002f186  add     rsp, 40h
0x14002f18a  pop     rdi
0x14002f18b  retn
```
