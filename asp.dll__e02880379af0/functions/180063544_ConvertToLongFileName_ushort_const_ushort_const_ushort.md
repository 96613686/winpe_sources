# ConvertToLongFileName(ushort const *,ushort const *,ushort * *)

- ea: `0x180063544`
- end: `0x180063780`
- name: `?ConvertToLongFileName@@YAHPEBG0PEAPEAG@Z`
- size: `572`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180063788`

## callees

- `0x180023d86`
- `0x180023dd0`
- `0x180063544`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180063737`
- `msvcrt!wcscpy_s` at `0x180063737`
- `KERNEL32!HeapAlloc` at `0x1800636f9`
- `KERNEL32!HeapAlloc` at `0x1800636f9`
- `KERNEL32!GetLongPathNameW` at `0x18006362d`
- `KERNEL32!GetLongPathNameW` at `0x1800636ab`
- `KERNEL32!GetLongPathNameW` at `0x18006362d`
- `KERNEL32!GetLongPathNameW` at `0x1800636ab`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800635cf`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800635cf`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x1800635f8`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x180063642`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x180063676`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x1800636c0`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x1800636da`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x18006371a`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x1800635f8`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x180063642`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x180063676`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x1800636c0`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x1800636da`
- `iisutil!?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ` at `0x18006371a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800635e5`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800635e5`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180063601`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18006364b`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18006367f`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800636c9`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800636e3`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180063723`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180063601`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18006364b`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18006367f`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800636c9`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800636e3`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x180063723`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18006374b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180063756`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18006374b`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180063756`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180063663`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180063663`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180063610`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18006361e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18006368e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18006369c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18006370c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180063610`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18006361e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18006368e`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18006369c`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18006370c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180063595`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800635c1`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180063595`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800635c1`

## pseudocode

```c
__int64 __fastcall ConvertToLongFileName(const unsigned __int16 *a1, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  BUFFER *Buffer; // rax
  DWORD v7; // edi
  WCHAR *Str; // rbx
  const WCHAR *v9; // rax
  DWORD LongPathNameW; // ebx
  BUFFER *v11; // rax
  BUFFER *v12; // rax
  DWORD v13; // edi
  WCHAR *v14; // rbx
  const WCHAR *v15; // rax
  DWORD v16; // ebx
  BUFFER *v17; // rax
  BUFFER *v18; // rax
  unsigned int Size; // eax
  unsigned __int16 *v20; // rax
  const wchar_t *v21; // rbx
  BUFFER *v22; // rax
  unsigned int v23; // eax
  unsigned int v24; // ebx
  _BYTE v26[56]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v27[56]; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v28[264]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v29[264]; // [rsp+2A0h] [rbp+1A0h] BYREF

  memset_0(v28, 0, 0x208u);
  STRU::STRU((STRU *)v26, v28, 0x104u);
  memset_0(v29, 0, 0x208u);
  STRU::STRU((STRU *)v27, v29, 0x104u);
  if ( (int)STRU::Copy((STRU *)v27, a1) < 0 )
    goto LABEL_10;
  if ( (int)STRU::Append((STRU *)v27, a2) < 0 )
    goto LABEL_10;
  Buffer = STRU::QueryBuffer((STRU *)v26);
  v7 = BUFFER::QuerySize(Buffer) >> 1;
  Str = STRU::QueryStr((STRU *)v26);
  v9 = STRU::QueryStr((STRU *)v27);
  LongPathNameW = GetLongPathNameW(v9, Str, v7);
  if ( !LongPathNameW )
    goto LABEL_10;
  v11 = STRU::QueryBuffer((STRU *)v26);
  if ( LongPathNameW >= BUFFER::QuerySize(v11) >> 1 )
  {
    if ( (int)STRU::Resize((STRU *)v26, 2 * LongPathNameW + 2) < 0 )
      goto LABEL_10;
    v12 = STRU::QueryBuffer((STRU *)v26);
    v13 = BUFFER::QuerySize(v12) >> 1;
    v14 = STRU::QueryStr((STRU *)v26);
    v15 = STRU::QueryStr((STRU *)v27);
    v16 = GetLongPathNameW(v15, v14, v13);
    if ( !v16 )
      goto LABEL_10;
    v17 = STRU::QueryBuffer((STRU *)v26);
    if ( v16 >= BUFFER::QuerySize(v17) >> 1 )
      goto LABEL_10;
  }
  v18 = STRU::QueryBuffer((STRU *)v26);
  Size = BUFFER::QuerySize(v18);
  v20 = (unsigned __int16 *)HeapAlloc(g_hDenaliHeap, 0, Size + 2LL);
  *a3 = v20;
  if ( v20 )
  {
    v21 = STRU::QueryStr((STRU *)v26);
    v22 = STRU::QueryBuffer((STRU *)v26);
    v23 = BUFFER::QuerySize(v22);
    wcscpy_s(*a3, ((unsigned __int64)v23 >> 1) + 1, v21);
    v24 = 1;
  }
  else
  {
LABEL_10:
    v24 = 0;
  }
  STRU::~STRU((STRU *)v27);
  STRU::~STRU((STRU *)v26);
  return v24;
}

```

## disassembly

```asm
0x180063544  mov     [rsp-8+arg_18], rbx
0x180063549  push    rbp
0x18006354a  push    rsi
0x18006354b  push    rdi
0x18006354c  lea     rbp, [rsp-3C0h]
0x180063554  sub     rsp, 4C0h
0x18006355b  mov     rax, cs:__security_cookie
0x180063562  xor     rax, rsp
0x180063565  mov     [rbp+3D0h+var_20], rax
0x18006356c  mov     rsi, r8
0x18006356f  mov     rdi, rdx
0x180063572  mov     rbx, rcx
0x180063575  xor     edx, edx; Val
0x180063577  mov     r8d, 208h; Size
0x18006357d  lea     rcx, [rbp+3D0h+var_440]; void *
0x180063581  call    memset_0
0x180063586  mov     r8d, 104h
0x18006358c  lea     rdx, [rbp+3D0h+var_440]
0x180063590  lea     rcx, [rsp+4D0h+var_4B0]
0x180063595  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18006359b  xor     edx, edx; Val
0x18006359d  lea     rcx, [rbp+3D0h+var_230]; void *
0x1800635a4  mov     r8d, 208h; Size
0x1800635aa  call    memset_0
0x1800635af  mov     r8d, 104h
0x1800635b5  lea     rdx, [rbp+3D0h+var_230]
0x1800635bc  lea     rcx, [rsp+4D0h+var_478]
0x1800635c1  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800635c7  mov     rdx, rbx
0x1800635ca  lea     rcx, [rsp+4D0h+var_478]
0x1800635cf  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800635d5  test    eax, eax
0x1800635d7  js      loc_180063744
0x1800635dd  mov     rdx, rdi
0x1800635e0  lea     rcx, [rsp+4D0h+var_478]
0x1800635e5  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800635eb  test    eax, eax
0x1800635ed  js      loc_180063744
0x1800635f3  lea     rcx, [rsp+4D0h+var_4B0]
0x1800635f8  call    cs:__imp_?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ; STRU::QueryBuffer(void)
0x1800635fe  mov     rcx, rax
0x180063601  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180063607  mov     edi, eax
0x180063609  lea     rcx, [rsp+4D0h+var_4B0]
0x18006360e  shr     edi, 1
0x180063610  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180063616  lea     rcx, [rsp+4D0h+var_478]
0x18006361b  mov     rbx, rax
0x18006361e  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180063624  mov     r8d, edi; cchBuffer
0x180063627  mov     rdx, rbx; lpszLongPath
0x18006362a  mov     rcx, rax; lpszShortPath
0x18006362d  call    cs:__imp_GetLongPathNameW
0x180063633  mov     ebx, eax
0x180063635  test    eax, eax
0x180063637  jz      loc_180063744
0x18006363d  lea     rcx, [rsp+4D0h+var_4B0]
0x180063642  call    cs:__imp_?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ; STRU::QueryBuffer(void)
0x180063648  mov     rcx, rax
0x18006364b  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180063651  shr     eax, 1
0x180063653  cmp     ebx, eax
0x180063655  jb      short loc_1800636D5
0x180063657  lea     edx, ds:2[rbx*2]
0x18006365e  lea     rcx, [rsp+4D0h+var_4B0]
0x180063663  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x180063669  test    eax, eax
0x18006366b  js      loc_180063744
0x180063671  lea     rcx, [rsp+4D0h+var_4B0]
0x180063676  call    cs:__imp_?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ; STRU::QueryBuffer(void)
0x18006367c  mov     rcx, rax
0x18006367f  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180063685  mov     edi, eax
0x180063687  lea     rcx, [rsp+4D0h+var_4B0]
0x18006368c  shr     edi, 1
0x18006368e  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180063694  lea     rcx, [rsp+4D0h+var_478]
0x180063699  mov     rbx, rax
0x18006369c  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x1800636a2  mov     r8d, edi; cchBuffer
0x1800636a5  mov     rdx, rbx; lpszLongPath
0x1800636a8  mov     rcx, rax; lpszShortPath
0x1800636ab  call    cs:__imp_GetLongPathNameW
0x1800636b1  mov     ebx, eax
0x1800636b3  test    eax, eax
0x1800636b5  jz      loc_180063744
0x1800636bb  lea     rcx, [rsp+4D0h+var_4B0]
0x1800636c0  call    cs:__imp_?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ; STRU::QueryBuffer(void)
0x1800636c6  mov     rcx, rax
0x1800636c9  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x1800636cf  shr     eax, 1
0x1800636d1  cmp     ebx, eax
0x1800636d3  jnb     short loc_180063744
0x1800636d5  lea     rcx, [rsp+4D0h+var_4B0]
0x1800636da  call    cs:__imp_?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ; STRU::QueryBuffer(void)
0x1800636e0  mov     rcx, rax
0x1800636e3  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x1800636e9  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x1800636f0  xor     edx, edx; dwFlags
0x1800636f2  mov     r8d, eax
0x1800636f5  add     r8, 2; dwBytes
0x1800636f9  call    cs:__imp_HeapAlloc
0x1800636ff  mov     [rsi], rax
0x180063702  test    rax, rax
0x180063705  jz      short loc_180063744
0x180063707  lea     rcx, [rsp+4D0h+var_4B0]
0x18006370c  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180063712  lea     rcx, [rsp+4D0h+var_4B0]
0x180063717  mov     rbx, rax
0x18006371a  call    cs:__imp_?QueryBuffer@STRU@@QEAAPEAVBUFFER@@XZ; STRU::QueryBuffer(void)
0x180063720  mov     rcx, rax
0x180063723  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180063729  mov     rcx, [rsi]; Destination
0x18006372c  mov     r8, rbx; Source
0x18006372f  mov     edx, eax
0x180063731  shr     rdx, 1
0x180063734  inc     rdx; SizeInWords
0x180063737  call    cs:__imp_wcscpy_s
0x18006373d  mov     ebx, 1
0x180063742  jmp     short loc_180063746
0x180063744  xor     ebx, ebx
0x180063746  lea     rcx, [rsp+4D0h+var_478]
0x18006374b  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180063751  lea     rcx, [rsp+4D0h+var_4B0]
0x180063756  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18006375c  mov     eax, ebx
0x18006375e  mov     rcx, [rbp+3D0h+var_20]
0x180063765  xor     rcx, rsp; StackCookie
0x180063768  call    __security_check_cookie
0x18006376d  mov     rbx, [rsp+4D0h+arg_18]
0x180063775  add     rsp, 4C0h
0x18006377c  pop     rdi
0x18006377d  pop     rsi
0x18006377e  pop     rbp
0x18006377f  retn
```
