# WIMHashFile::InitializeHeader(void)

- ea: `0x18000228c`
- end: `0x18000246e`
- name: `?InitializeHeader@WIMHashFile@@AEAAJXZ`
- size: `482`
- prototype: `__int64 __fastcall(WIMHashFile *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180001e9c`

## callees

- `0x180001c20`
- `0x18000228c`
- `0x180002768`
- `0x1800027c4`
- `0x1800027fc`
- `0x1800028d8`
- `0x1800029fc`
- `0x180002a88`
- `0x180005176`
- `0x18000518e`
- `0x1800051c0`

## import_xrefs

- `KERNEL32!GetSystemInfo` at `0x1800022ff`
- `KERNEL32!GetSystemInfo` at `0x1800022ff`
- `KERNEL32!GetFileSizeEx` at `0x180002367`
- `KERNEL32!GetFileSizeEx` at `0x180002367`
- `KERNEL32!GetLastError` at `0x180002371`
- `KERNEL32!GetLastError` at `0x180002371`

## pseudocode

```c
__int64 __fastcall WIMHashFile::InitializeHeader(WIMHashFile *this)
{
  DWORD dwPageSize; // eax
  const unsigned __int16 *v3; // rdx
  __int64 v4; // r9
  int v5; // ebx
  signed int LastError; // eax
  bool v7; // sf
  __int128 v8; // xmm0
  __int64 v9; // r8
  union _LARGE_INTEGER FileSize; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE hFile[2]; // [rsp+38h] [rbp-C8h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE Buf1[24]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v15; // [rsp+98h] [rbp-68h]

  FileSize.QuadPart = 0;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  *(__m128i *)hFile = _mm_load_si128((const __m128i *)&_xmm);
  memset_0(Buf1, 0, 0xD0u);
  memset_0((char *)this + 16, 0, 0x74u);
  GetSystemInfo(&SystemInfo);
  dwPageSize = SystemInfo.dwPageSize;
  v3 = (const unsigned __int16 *)*((_QWORD *)this + 18);
  *((_QWORD *)this + 7) = 0;
  *((_DWORD *)this + 4) = 1766027095;
  *((_DWORD *)this + 5) = 1;
  *((_DWORD *)this + 16) = (dwPageSize + 115) & ~(dwPageSize - 1);
  v5 = File::Initialize((File *)hFile, v3, 0x80000000, v4, 0, 0);
  if ( v5 )
  {
LABEL_15:
    v7 = v5 < 0;
    goto LABEL_16;
  }
  if ( GetFileSizeEx(hFile[0], &FileSize) )
    goto LABEL_6;
  LastError = GetLastError();
  v5 = LastError;
  if ( LastError > 0 )
    v5 = (unsigned __int16)LastError | 0x80070000;
  v7 = v5 < 0;
  if ( !v5 )
  {
LABEL_6:
    if ( FileSize.QuadPart < 0x178uLL )
    {
LABEL_7:
      v5 = -2147023504;
LABEL_17:
      memset_0((char *)this + 16, 0, 0x74u);
      goto LABEL_18;
    }
    v5 = File::Read((File *)hFile, Buf1, 0xD0u, 0);
    if ( !v5 )
    {
      if ( memcmp_0(Buf1, "MSWIM", 8u) )
        goto LABEL_7;
      v8 = v15;
      *((union _LARGE_INTEGER *)this + 3) = FileSize;
      *((_OWORD *)this + 2) = v8;
      if ( (int)File::GetUSN(hFile, (__int64 *)this + 6) < 0 )
        *((_QWORD *)this + 6) = 0;
      v5 = WIMHashFile::Hash(this, (unsigned __int8 *)this + 16, v9, (unsigned __int8 *)this + 100);
      if ( !v5 )
      {
        v5 = File::Write((const unsigned __int16 **)this, (char *)this + 16, 0x74u);
        if ( !v5 )
          v5 = File::Flush((HANDLE *)this);
      }
    }
    goto LABEL_15;
  }
LABEL_16:
  if ( v7 )
    goto LABEL_17;
LABEL_18:
  File::~File(hFile);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000228c  push    rbp
0x18000228e  push    rbx
0x18000228f  push    rsi
0x180002290  push    rdi
0x180002291  lea     rbp, [rsp-68h]
0x180002296  sub     rsp, 168h
0x18000229d  mov     rax, cs:__security_cookie
0x1800022a4  xor     rax, rsp
0x1800022a7  mov     [rbp+80h+var_30], rax
0x1800022ab  movdqa  xmm1, cs:__xmm@0000000000000000ffffffffffffffff
0x1800022b3  xorps   xmm0, xmm0
0x1800022b6  mov     rdi, rcx
0x1800022b9  mov     qword ptr [rsp+180h+FileSize], 0
0x1800022c2  lea     rcx, [rbp+80h+Buf1]; void *
0x1800022c6  xor     edx, edx; Val
0x1800022c8  mov     r8d, 0D0h; Size
0x1800022ce  movups  xmmword ptr [rsp+180h+SystemInfo], xmm0
0x1800022d3  movups  xmmword ptr [rsp+180h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x1800022d8  movups  xmmword ptr [rsp+180h+SystemInfo.dwNumberOfProcessors], xmm0
0x1800022dd  movdqu  xmmword ptr [rsp+180h+hFile], xmm1
0x1800022e3  call    memset_0
0x1800022e8  xor     edx, edx; Val
0x1800022ea  lea     rsi, [rdi+10h]
0x1800022ee  mov     rcx, rsi; void *
0x1800022f1  lea     r8d, [rdx+74h]; Size
0x1800022f5  call    memset_0
0x1800022fa  lea     rcx, [rsp+180h+SystemInfo]; lpSystemInfo
0x1800022ff  call    cs:__imp_GetSystemInfo
0x180002305  mov     eax, [rsp+180h+SystemInfo.dwPageSize]
0x180002309  mov     r8d, 80000000h; unsigned int
0x18000230f  mov     rdx, [rdi+90h]; unsigned __int16 *
0x180002316  mov     [rsp+180h+var_158], 0; int *
0x18000231f  mov     qword ptr [rdi+38h], 0
0x180002327  lea     ecx, [rax-1]
0x18000232a  mov     dword ptr [rsi], 69436F57h
0x180002330  not     ecx
0x180002332  mov     dword ptr [rdi+14h], 1
0x180002339  add     eax, 73h ; 's'
0x18000233c  mov     [rsp+180h+var_160], 0; unsigned int
0x180002344  and     ecx, eax
0x180002346  mov     [rdi+40h], ecx
0x180002349  lea     rcx, [rsp+180h+hFile]; this
0x18000234e  call    ?Initialize@File@@QEAAJPEBGKKKPEAH@Z; File::Initialize(ushort const *,ulong,ulong,ulong,int *)
0x180002353  mov     ebx, eax
0x180002355  test    eax, eax
0x180002357  jnz     loc_180002438
0x18000235d  mov     rcx, [rsp+180h+hFile]; hFile
0x180002362  lea     rdx, [rsp+180h+FileSize]; lpFileSize
0x180002367  call    cs:__imp_GetFileSizeEx
0x18000236d  test    eax, eax
0x18000236f  jnz     short loc_18000238E
0x180002371  call    cs:__imp_GetLastError
0x180002377  mov     ebx, eax
0x180002379  test    eax, eax
0x18000237b  jle     short loc_180002386
0x18000237d  movzx   ebx, ax
0x180002380  or      ebx, 80070000h
0x180002386  test    ebx, ebx
0x180002388  jnz     loc_18000243A
0x18000238e  cmp     qword ptr [rsp+180h+FileSize], 178h
0x180002397  jnb     short loc_1800023A3
0x180002399  mov     ebx, 80070570h
0x18000239e  jmp     loc_18000243C
0x1800023a3  xor     r9d, r9d; unsigned int *
0x1800023a6  lea     rdx, [rbp+80h+Buf1]; void *
0x1800023aa  mov     r8d, 0D0h; unsigned int
0x1800023b0  lea     rcx, [rsp+180h+hFile]; this
0x1800023b5  call    ?Read@File@@QEAAJPEAXKPEAK@Z; File::Read(void *,ulong,ulong *)
0x1800023ba  mov     ebx, eax
0x1800023bc  test    eax, eax
0x1800023be  jnz     short loc_180002438
0x1800023c0  lea     r8d, [rax+8]; Size
0x1800023c4  lea     rdx, aMswim; "MSWIM"
0x1800023cb  lea     rcx, [rbp+80h+Buf1]; Buf1
0x1800023cf  call    memcmp_0
0x1800023d4  test    eax, eax
0x1800023d6  jnz     short loc_180002399
0x1800023d8  movups  xmm0, [rbp+80h+var_E8]
0x1800023dc  mov     rax, qword ptr [rsp+180h+FileSize]
0x1800023e1  lea     rdx, [rdi+30h]; __int64 *
0x1800023e5  lea     rcx, [rsp+180h+hFile]; this
0x1800023ea  mov     [rdi+18h], rax
0x1800023ee  movdqu  xmmword ptr [rdi+20h], xmm0
0x1800023f3  call    ?GetUSN@File@@QEAAJPEA_J@Z; File::GetUSN(__int64 *)
0x1800023f8  test    eax, eax
0x1800023fa  jns     short loc_180002404
0x1800023fc  mov     qword ptr [rdi+30h], 0
0x180002404  lea     r9, [rdi+64h]; unsigned __int8 *
0x180002408  mov     rdx, rsi; unsigned __int8 *
0x18000240b  mov     rcx, rdi; this
0x18000240e  call    ?Hash@WIMHashFile@@QEAAJPEAEK0@Z; WIMHashFile::Hash(uchar *,ulong,uchar *)
0x180002413  mov     ebx, eax
0x180002415  test    eax, eax
0x180002417  jnz     short loc_180002438
0x180002419  lea     r8d, [rax+74h]; unsigned int
0x18000241d  mov     rdx, rsi; void *
0x180002420  mov     rcx, rdi; this
0x180002423  call    ?Write@File@@QEAAJPEAXK@Z; File::Write(void *,ulong)
0x180002428  mov     ebx, eax
0x18000242a  test    eax, eax
0x18000242c  jnz     short loc_180002438
0x18000242e  mov     rcx, rdi; this
0x180002431  call    ?Flush@File@@QEAAJXZ; File::Flush(void)
0x180002436  mov     ebx, eax
0x180002438  test    ebx, ebx
0x18000243a  jns     short loc_18000244A
0x18000243c  xor     edx, edx; Val
0x18000243e  mov     rcx, rsi; void *
0x180002441  lea     r8d, [rdx+74h]; Size
0x180002445  call    memset_0
0x18000244a  lea     rcx, [rsp+180h+hFile]; this
0x18000244f  call    ??1File@@QEAA@XZ; File::~File(void)
0x180002454  mov     eax, ebx
0x180002456  mov     rcx, [rbp+80h+var_30]
0x18000245a  xor     rcx, rsp; StackCookie
0x18000245d  call    __security_check_cookie
0x180002462  add     rsp, 168h
0x180002469  pop     rdi
0x18000246a  pop     rsi
0x18000246b  pop     rbx
0x18000246c  pop     rbp
0x18000246d  retn
```
