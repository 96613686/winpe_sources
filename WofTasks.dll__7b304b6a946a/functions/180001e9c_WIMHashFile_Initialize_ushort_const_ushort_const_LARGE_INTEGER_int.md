# WIMHashFile::Initialize(ushort const *,ushort const *,_LARGE_INTEGER,int *)

- ea: `0x180001e9c`
- end: `0x180002284`
- name: `?Initialize@WIMHashFile@@QEAAJPEBG0T_LARGE_INTEGER@@PEAH@Z`
- size: `1000`
- prototype: `__int64 __fastcall(union _LARGE_INTEGER *this, const unsigned __int16 *, const unsigned __int16 *, union _LARGE_INTEGER, int *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, service_task`

## callers

- `0x1800040a8`

## callees

- `0x180001c20`
- `0x180001e9c`
- `0x18000228c`
- `0x180002768`
- `0x1800027fc`
- `0x1800028d8`
- `0x1800029bc`
- `0x1800029fc`
- `0x180004434`
- `0x180005176`
- `0x180005182`
- `0x1800051c0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180001f81`
- `KERNEL32!HeapFree` at `0x180001f81`
- `KERNEL32!HeapAlloc` at `0x180002083`
- `KERNEL32!HeapAlloc` at `0x180002083`
- `KERNEL32!GetProcessHeap` at `0x180001f73`
- `KERNEL32!GetProcessHeap` at `0x180002075`
- `KERNEL32!GetProcessHeap` at `0x180001f73`
- `KERNEL32!GetProcessHeap` at `0x180002075`
- `KERNEL32!GetFileSizeEx` at `0x180002174`
- `KERNEL32!GetFileSizeEx` at `0x180002174`
- `KERNEL32!SetEndOfFile` at `0x1800021e5`
- `KERNEL32!SetEndOfFile` at `0x1800021e5`
- `KERNEL32!GetLastError` at `0x180002184`
- `KERNEL32!GetLastError` at `0x1800021ef`
- `KERNEL32!GetLastError` at `0x180002184`
- `KERNEL32!GetLastError` at `0x1800021ef`
- `bcrypt!BCryptGetProperty` at `0x180001f49`
- `bcrypt!BCryptGetProperty` at `0x180002001`
- `bcrypt!BCryptGetProperty` at `0x180001f49`
- `bcrypt!BCryptGetProperty` at `0x180002001`
- `bcrypt!BCryptCreateMultiHash` at `0x180002040`
- `bcrypt!BCryptCreateMultiHash` at `0x180002040`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180001f12`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180001fcf`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180001f12`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180001fcf`

## pseudocode

```c
__int64 __fastcall WIMHashFile::Initialize(
        union _LARGE_INTEGER *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        union _LARGE_INTEGER a4,
        int *a5)
{
  __m128i si128; // xmm0
  BCRYPT_HANDLE *v6; // rdi
  NTSTATUS Property; // ebx
  int USN; // ebx
  const unsigned __int16 **v12; // rdi
  bool v13; // sf
  unsigned __int16 *v14; // rsi
  HANDLE v15; // rax
  BCRYPT_HANDLE *v17; // rdi
  int MultiHash; // eax
  __int64 v19; // r14
  __int64 v20; // rbx
  HANDLE ProcessHeap; // rax
  void *v22; // rax
  __int64 v23; // r9
  unsigned int v24; // r8d
  __int64 v25; // r9
  signed int LastError; // eax
  __int128 v27; // rax
  union _LARGE_INTEGER v28; // rdx
  signed int v29; // eax
  __int64 v30; // rax
  UCHAR pbOutput[4]; // [rsp+40h] [rbp-51h] BYREF
  ULONG pcbResult; // [rsp+44h] [rbp-4Dh] BYREF
  int v33; // [rsp+48h] [rbp-49h] BYREF
  union _LARGE_INTEGER FileSize; // [rsp+50h] [rbp-41h] BYREF
  __int64 v35; // [rsp+58h] [rbp-39h] BYREF
  __m128i v36; // [rsp+60h] [rbp-31h] BYREF
  unsigned __int8 Buf1[32]; // [rsp+70h] [rbp-21h] BYREF

  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v6 = (BCRYPT_HANDLE *)&this[20];
  this[19] = a4;
  FileSize.QuadPart = 0;
  v33 = 0;
  v35 = 0;
  pcbResult = 0;
  *(_DWORD *)pbOutput = 0;
  v36 = si128;
  Property = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)&this[20], L"SHA256", 0, 0);
  if ( Property < 0 )
    goto LABEL_2;
  Property = BCryptGetProperty(*v6, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0);
  if ( Property < 0 )
    goto LABEL_2;
  if ( *(_DWORD *)pbOutput != 32 )
  {
LABEL_5:
    USN = -2147418113;
LABEL_6:
    v12 = (const unsigned __int16 **)&this[18];
LABEL_7:
    v13 = USN < 0;
    goto LABEL_8;
  }
  v17 = (BCRYPT_HANDLE *)&this[21];
  Property = BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)&this[21], L"SHA256", 0, 0x60u);
  if ( Property < 0
    || (Property = BCryptGetProperty(*v17, L"HashDigestLength", pbOutput, 4u, &pcbResult, 0), Property < 0) )
  {
LABEL_2:
    USN = Property | 0x10000000;
  }
  else
  {
    if ( *(_DWORD *)pbOutput != 32 )
      goto LABEL_5;
    MultiHash = BCryptCreateMultiHash(*v17, &this[22], 4);
    USN = MultiHash | 0x10000000;
    if ( MultiHash >= 0 )
      USN = 0;
  }
  if ( USN )
    goto LABEL_6;
  v19 = -1;
  v20 = -1;
  do
    ++v20;
  while ( a2[v20] );
  ProcessHeap = GetProcessHeap();
  v22 = HeapAlloc(ProcessHeap, 0, 2 * v20 + 2);
  v12 = (const unsigned __int16 **)&this[18];
  this[18].QuadPart = (LONGLONG)v22;
  if ( v22 )
  {
    do
      ++v19;
    while ( a2[v19] );
    memcpy_0(v22, a2, 2 * v19 + 2);
    USN = File::Initialize((File *)this, a3, 0xC0000000, v23, 0, &v33);
    if ( USN )
      goto LABEL_7;
    if ( !v33 )
    {
      LogFile(&WofTaskCreateHashFileEventId, a3, a2);
      USN = WIMHashFile::InitializeHeader((WIMHashFile *)this);
      if ( !USN )
      {
        USN = 0;
        *a5 = 0;
        goto LABEL_11;
      }
      goto LABEL_7;
    }
    USN = File::Read((File *)this, &this[2], 0x74u, 0);
    v13 = USN < 0;
    if ( USN )
      goto LABEL_8;
    USN = WIMHashFile::Hash((WIMHashFile *)this, (unsigned __int8 *)&this[2], v24, Buf1);
    if ( USN )
      goto LABEL_7;
    if ( !memcmp_0(Buf1, (char *)&this[12].QuadPart + 4, 0x20u) )
    {
      if ( GetFileSizeEx((HANDLE)this->QuadPart, &FileSize) )
        goto LABEL_50;
      LastError = GetLastError();
      USN = LastError;
      if ( LastError > 0 )
        USN = (unsigned __int16)LastError | 0x80070000;
      v13 = USN < 0;
      if ( !USN )
      {
LABEL_50:
        v27 = (__int64)((this[7].QuadPart + 4095) & 0xFFFFFFFFFFFFF000uLL);
        v28.QuadPart = this[8].LowPart + 16 * ((__int64)(v27 + (WORD4(v27) & 0xFFF)) >> 12);
        if ( FileSize.QuadPart == v28.QuadPart )
          goto LABEL_39;
        FileSize = v28;
        USN = File::MoveFilePointer((File *)this, v28);
        if ( USN )
          goto LABEL_7;
        if ( SetEndOfFile((HANDLE)this->QuadPart) )
          goto LABEL_39;
        v29 = GetLastError();
        USN = v29;
        if ( v29 > 0 )
          USN = (unsigned __int16)v29 | 0x80070000;
        v13 = USN < 0;
        if ( !USN )
        {
LABEL_39:
          USN = File::Initialize((File *)&v36, *v12, 0x80000000, v25, 0x28000000u, 0);
          if ( !USN )
          {
            USN = File::GetUSN((File *)&v36, &v35);
            if ( USN >= 0 )
            {
              v30 = v35;
            }
            else
            {
              v30 = 0;
              USN = 0;
            }
            *a5 = v30 != this[6].QuadPart;
          }
          goto LABEL_7;
        }
      }
LABEL_8:
      if ( !v13 )
        goto LABEL_11;
      goto LABEL_9;
    }
    USN = -2147023504;
  }
  else
  {
    USN = -2147024882;
  }
LABEL_9:
  v14 = (unsigned __int16 *)*v12;
  if ( *v12 )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 0, v14);
    *v12 = 0;
  }
LABEL_11:
  File::~File((File *)&v36);
  return (unsigned int)USN;
}

```

## disassembly

```asm
0x180001e9c  push    rbp
0x180001e9e  push    rbx
0x180001e9f  push    rsi
0x180001ea0  push    rdi
0x180001ea1  push    r12
0x180001ea3  push    r13
0x180001ea5  push    r14
0x180001ea7  push    r15
0x180001ea9  lea     rbp, [rsp-17h]
0x180001eae  sub     rsp, 0A8h
0x180001eb5  mov     rax, cs:__security_cookie
0x180001ebc  xor     rax, rsp
0x180001ebf  mov     [rbp+4Fh+var_50], rax
0x180001ec3  movdqa  xmm0, cs:__xmm@0000000000000000ffffffffffffffff
0x180001ecb  lea     rdi, [rcx+0A0h]
0x180001ed2  mov     r12, [rbp+4Fh+arg_20]
0x180001ed6  xor     r14d, r14d
0x180001ed9  mov     [rcx+98h], r9
0x180001ee0  mov     r13, r8
0x180001ee3  mov     r15, rdx
0x180001ee6  mov     qword ptr [rbp+4Fh+FileSize], r14
0x180001eea  mov     rsi, rcx
0x180001eed  mov     [rbp+4Fh+var_98], r14d
0x180001ef1  mov     rcx, rdi; phAlgorithm
0x180001ef4  mov     [rbp+4Fh+var_88], r14
0x180001ef8  xor     r9d, r9d; dwFlags
0x180001efb  mov     [rbp+4Fh+var_9C], r14d
0x180001eff  xor     r8d, r8d; pszImplementation
0x180001f02  mov     dword ptr [rbp+4Fh+pbOutput], r14d
0x180001f06  lea     rdx, pszAlgId; "SHA256"
0x180001f0d  movdqu  [rbp+4Fh+var_80], xmm0
0x180001f12  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180001f18  mov     ebx, eax
0x180001f1a  test    eax, eax
0x180001f1c  jns     short loc_180001F27
0x180001f1e  bts     ebx, 1Ch
0x180001f22  jmp     loc_180002052
0x180001f27  mov     rcx, [rdi]; hObject
0x180001f2a  lea     rax, [rbp+4Fh+var_9C]
0x180001f2e  mov     [rsp+0E0h+dwFlags], r14d; dwFlags
0x180001f33  lea     r8, [rbp+4Fh+pbOutput]; pbOutput
0x180001f37  mov     r9d, 4; cbOutput
0x180001f3d  mov     [rsp+0E0h+pcbResult], rax; pcbResult
0x180001f42  lea     rdx, pszProperty; "HashDigestLength"
0x180001f49  call    cs:__imp_BCryptGetProperty
0x180001f4f  mov     ebx, eax
0x180001f51  test    eax, eax
0x180001f53  js      short loc_180001F1E
0x180001f55  cmp     dword ptr [rbp+4Fh+pbOutput], 20h ; ' '
0x180001f59  jz      short loc_180001FB5
0x180001f5b  mov     ebx, 8000FFFFh
0x180001f60  lea     rdi, [rsi+90h]
0x180001f67  test    ebx, ebx
0x180001f69  jns     short loc_180001F8A
0x180001f6b  mov     rsi, [rdi]
0x180001f6e  test    rsi, rsi
0x180001f71  jz      short loc_180001F8A
0x180001f73  call    cs:__imp_GetProcessHeap
0x180001f79  mov     r8, rsi; lpMem
0x180001f7c  xor     edx, edx; dwFlags
0x180001f7e  mov     rcx, rax; hHeap
0x180001f81  call    cs:__imp_HeapFree
0x180001f87  mov     [rdi], r14
0x180001f8a  lea     rcx, [rbp+4Fh+var_80]; this
0x180001f8e  call    ??1File@@QEAA@XZ; File::~File(void)
0x180001f93  mov     eax, ebx
0x180001f95  mov     rcx, [rbp+4Fh+var_50]
0x180001f99  xor     rcx, rsp; StackCookie
0x180001f9c  call    __security_check_cookie
0x180001fa1  add     rsp, 0A8h
0x180001fa8  pop     r15
0x180001faa  pop     r14
0x180001fac  pop     r13
0x180001fae  pop     r12
0x180001fb0  pop     rdi
0x180001fb1  pop     rsi
0x180001fb2  pop     rbx
0x180001fb3  pop     rbp
0x180001fb4  retn
0x180001fb5  lea     rdi, [rsi+0A8h]
0x180001fbc  mov     r9d, 60h ; '`'; dwFlags
0x180001fc2  mov     rcx, rdi; phAlgorithm
0x180001fc5  lea     rdx, pszAlgId; "SHA256"
0x180001fcc  xor     r8d, r8d; pszImplementation
0x180001fcf  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180001fd5  mov     ebx, eax
0x180001fd7  test    eax, eax
0x180001fd9  js      loc_180001F1E
0x180001fdf  mov     rcx, [rdi]; hObject
0x180001fe2  lea     rax, [rbp+4Fh+var_9C]
0x180001fe6  mov     [rsp+0E0h+dwFlags], r14d; dwFlags
0x180001feb  lea     r8, [rbp+4Fh+pbOutput]; pbOutput
0x180001fef  mov     r9d, 4; cbOutput
0x180001ff5  mov     [rsp+0E0h+pcbResult], rax; pcbResult
0x180001ffa  lea     rdx, pszProperty; "HashDigestLength"
0x180002001  call    cs:__imp_BCryptGetProperty
0x180002007  mov     ebx, eax
0x180002009  test    eax, eax
0x18000200b  js      loc_180001F1E
0x180002011  cmp     dword ptr [rbp+4Fh+pbOutput], 20h ; ' '
0x180002015  jnz     loc_180001F5B
0x18000201b  mov     rcx, [rdi]
0x18000201e  lea     rdx, [rsi+0B0h]
0x180002025  mov     [rsp+0E0h+var_A8], r14d
0x18000202a  xor     r9d, r9d
0x18000202d  mov     [rsp+0E0h+var_B0], r14d
0x180002032  mov     qword ptr [rsp+0E0h+dwFlags], r14
0x180002037  mov     dword ptr [rsp+0E0h+pcbResult], r14d
0x18000203c  lea     r8d, [r9+4]
0x180002040  call    cs:__imp_BCryptCreateMultiHash
0x180002046  mov     ebx, eax
0x180002048  bts     ebx, 1Ch
0x18000204c  test    eax, eax
0x18000204e  cmovns  ebx, r14d
0x180002052  test    ebx, ebx
0x180002054  jnz     loc_180001F60
0x18000205a  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000205e  mov     rbx, r14
0x180002061  xor     eax, eax
0x180002063  inc     rbx
0x180002066  cmp     [r15+rbx*2], ax
0x18000206b  jnz     short loc_180002063
0x18000206d  lea     rbx, ds:2[rbx*2]
0x180002075  call    cs:__imp_GetProcessHeap
0x18000207b  mov     r8, rbx; dwBytes
0x18000207e  xor     edx, edx; dwFlags
0x180002080  mov     rcx, rax; hHeap
0x180002083  call    cs:__imp_HeapAlloc
0x180002089  xor     ecx, ecx
0x18000208b  lea     rdi, [rsi+90h]
0x180002092  mov     [rdi], rax
0x180002095  test    rax, rax
0x180002098  jz      loc_180002277
0x18000209e  inc     r14
0x1800020a1  cmp     [r15+r14*2], cx
0x1800020a6  jnz     short loc_18000209E
0x1800020a8  lea     r8, ds:2[r14*2]; Size
0x1800020b0  mov     rdx, r15; Src
0x1800020b3  mov     rcx, rax; void *
0x1800020b6  call    memcpy_0
0x1800020bb  lea     rax, [rbp+4Fh+var_98]
0x1800020bf  xor     r14d, r14d
0x1800020c2  mov     qword ptr [rsp+0E0h+dwFlags], rax; int *
0x1800020c7  mov     r8d, 0C0000000h; unsigned int
0x1800020cd  mov     rdx, r13; unsigned __int16 *
0x1800020d0  mov     dword ptr [rsp+0E0h+pcbResult], r14d; unsigned int
0x1800020d5  mov     rcx, rsi; this
0x1800020d8  call    ?Initialize@File@@QEAAJPEBGKKKPEAH@Z; File::Initialize(ushort const *,ulong,ulong,ulong,int *)
0x1800020dd  mov     ebx, eax
0x1800020df  test    eax, eax
0x1800020e1  jnz     loc_180001F67
0x1800020e7  cmp     [rbp+4Fh+var_98], r14d
0x1800020eb  jnz     short loc_18000211D
0x1800020ed  mov     r8, r15; unsigned __int16 *
0x1800020f0  lea     rcx, WofTaskCreateHashFileEventId; EventDescriptor
0x1800020f7  mov     rdx, r13; unsigned __int16 *
0x1800020fa  call    ?LogFile@@YAXPEBU_EVENT_DESCRIPTOR@@PEBG1@Z; LogFile(_EVENT_DESCRIPTOR const *,ushort const *,ushort const *)
0x1800020ff  mov     rcx, rsi; this
0x180002102  call    ?InitializeHeader@WIMHashFile@@AEAAJXZ; WIMHashFile::InitializeHeader(void)
0x180002107  mov     ebx, eax
0x180002109  test    eax, eax
0x18000210b  jnz     loc_180001F67
0x180002111  mov     ebx, r14d
0x180002114  mov     [r12], r14d
0x180002118  jmp     loc_180001F8A
0x18000211d  xor     r9d, r9d; unsigned int *
0x180002120  lea     rdx, [rsi+10h]; void *
0x180002124  mov     rcx, rsi; this
0x180002127  lea     r8d, [r9+74h]; unsigned int
0x18000212b  call    ?Read@File@@QEAAJPEAXKPEAK@Z; File::Read(void *,ulong,ulong *)
0x180002130  mov     ebx, eax
0x180002132  test    eax, eax
0x180002134  jnz     loc_180001F69
0x18000213a  lea     r9, [rbp+4Fh+Buf1]; unsigned __int8 *
0x18000213e  mov     rcx, rsi; this
0x180002141  lea     rdx, [rsi+10h]; unsigned __int8 *
0x180002145  call    ?Hash@WIMHashFile@@QEAAJPEAEK0@Z; WIMHashFile::Hash(uchar *,ulong,uchar *)
0x18000214a  mov     ebx, eax
0x18000214c  test    eax, eax
0x18000214e  jnz     loc_180001F67
0x180002154  lea     rdx, [rsi+64h]; Buf2
0x180002158  lea     r8d, [rax+20h]; Size
0x18000215c  lea     rcx, [rbp+4Fh+Buf1]; Buf1
0x180002160  call    memcmp_0
0x180002165  test    eax, eax
0x180002167  jnz     loc_18000226D
0x18000216d  mov     rcx, [rsi]; hFile
0x180002170  lea     rdx, [rbp+4Fh+FileSize]; lpFileSize
0x180002174  call    cs:__imp_GetFileSizeEx
0x18000217a  mov     r15d, 80070000h
0x180002180  test    eax, eax
0x180002182  jnz     short loc_18000219E
0x180002184  call    cs:__imp_GetLastError
0x18000218a  mov     ebx, eax
0x18000218c  test    eax, eax
0x18000218e  jle     short loc_180002196
0x180002190  movzx   ebx, ax
0x180002193  or      ebx, r15d
0x180002196  test    ebx, ebx
0x180002198  jnz     loc_180001F69
0x18000219e  mov     rax, [rsi+38h]
0x1800021a2  mov     ecx, 0FFFh
0x1800021a7  add     rax, rcx
0x1800021aa  and     rax, 0FFFFFFFFFFFFF000h
0x1800021b0  cqo
0x1800021b2  and     rdx, rcx
0x1800021b5  mov     ecx, [rsi+40h]
0x1800021b8  add     rdx, rax
0x1800021bb  sar     rdx, 0Ch
0x1800021bf  shl     rdx, 4
0x1800021c3  add     rdx, rcx; union _LARGE_INTEGER
0x1800021c6  cmp     qword ptr [rbp+4Fh+FileSize], rdx
0x1800021ca  jz      short loc_180002209
0x1800021cc  mov     rcx, rsi; this
0x1800021cf  mov     qword ptr [rbp+4Fh+FileSize], rdx
0x1800021d3  call    ?MoveFilePointer@File@@QEAAJT_LARGE_INTEGER@@@Z; File::MoveFilePointer(_LARGE_INTEGER)
0x1800021d8  mov     ebx, eax
0x1800021da  test    eax, eax
0x1800021dc  jnz     loc_180001F67
0x1800021e2  mov     rcx, [rsi]; hFile
0x1800021e5  call    cs:__imp_SetEndOfFile
0x1800021eb  test    eax, eax
0x1800021ed  jnz     short loc_180002209
0x1800021ef  call    cs:__imp_GetLastError
0x1800021f5  mov     ebx, eax
0x1800021f7  test    eax, eax
0x1800021f9  jle     short loc_180002201
0x1800021fb  movzx   ebx, ax
0x1800021fe  or      ebx, r15d
0x180002201  test    ebx, ebx
0x180002203  jnz     loc_180001F69
0x180002209  mov     rdx, [rdi]; unsigned __int16 *
0x18000220c  lea     rcx, [rbp+4Fh+var_80]; this
0x180002210  mov     qword ptr [rsp+0E0h+dwFlags], r14; int *
0x180002215  mov     r8d, 80000000h; unsigned int
0x18000221b  mov     dword ptr [rsp+0E0h+pcbResult], 28000000h; unsigned int
0x180002223  call    ?Initialize@File@@QEAAJPEBGKKKPEAH@Z; File::Initialize(ushort const *,ulong,ulong,ulong,int *)
0x180002228  mov     ebx, eax
0x18000222a  test    eax, eax
0x18000222c  jnz     loc_180001F67
0x180002232  lea     rdx, [rbp+4Fh+var_88]; __int64 *
0x180002236  lea     rcx, [rbp+4Fh+var_80]; this
0x18000223a  call    ?GetUSN@File@@QEAAJPEA_J@Z; File::GetUSN(__int64 *)
0x18000223f  mov     ebx, eax
0x180002241  test    eax, eax
0x180002243  jns     short loc_18000224D
0x180002245  mov     rax, r14
0x180002248  mov     ebx, r14d
0x18000224b  jmp     short loc_180002251
0x18000224d  mov     rax, [rbp+4Fh+var_88]
0x180002251  cmp     rax, [rsi+30h]
0x180002255  jz      short loc_180002264
0x180002257  mov     dword ptr [r12], 1
0x18000225f  jmp     loc_180001F67
0x180002264  mov     [r12], r14d
0x180002268  jmp     loc_180001F67
0x18000226d  mov     ebx, 80070570h
0x180002272  jmp     loc_180001F6B
0x180002277  mov     ebx, 8007000Eh
0x18000227c  xor     r14d, r14d
0x18000227f  jmp     loc_180001F6B
```
