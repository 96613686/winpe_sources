# Common::Deployment::GetSystemBinaryForArchitecture(StateRepository::SRProcessorArchitecture,ushort const *,bool,Common::StringBuffer &)

- ea: `0x180017d94`
- end: `0x180018107`
- name: `?GetSystemBinaryForArchitecture@Deployment@Common@@YAJW4SRProcessorArchitecture@StateRepository@@PEBG_NAEAVStringBuffer@2@@Z`
- size: `883`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180005f50`
- `0x180017b84`
- `0x180018a54`
- `0x180041c70`
- `0x18007e4fc`
- `0x18007e694`
- `0x180099d30`
- `0x18013dafc`
- `0x18014b834`
- `0x1801708d4`
- `0x180170d5c`
- `0x180173258`
- `0x1801748b4`

## callees

- `0x180017d94`
- `0x180018110`
- `0x180018df8`
- `0x18001aba8`
- `0x1800434a0`
- `0x180098bf4`
- `0x1800a021c`
- `0x1800a219c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800180c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800180c4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180017e0e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180017ea1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180017e0e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180017ea1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180017dd7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800180e4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x180017dd7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800180e4`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x180017fd5`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x1800180a9`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x180017fd5`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x1800180a9`

## string_xrefs

- `0x180018013`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180018030`: `onecore\base\appmodel\common\widestring.cpp`
- `0x180017e41`: `onecore\admin\appmodel\common\packageid.cpp`
- `0x180017f8d`: `onecore\admin\appmodel\common\packageid.cpp`
- `0x180017fb1`: `onecore\admin\appmodel\common\packageid.cpp`
- `0x180018048`: `onecore\admin\appmodel\common\packageid.cpp`
- `0x180017f7a`: `onecore\base\appmodel\common\pathhelpers.cpp`
- `0x180018068`: `onecore\base\appmodel\common\stringbuilder.cpp`

## pseudocode

```c
__int64 __fastcall Common::Deployment::GetSystemBinaryForArchitecture(
        unsigned int a1,
        const unsigned __int16 *a2,
        char a3,
        __int64 a4)
{
  const unsigned __int16 *v6; // rsi
  __int64 v8; // rcx
  unsigned __int16 ImageFileMachineFromArchitecture; // ax
  unsigned __int16 v10; // r15
  unsigned int SystemWow64Directory2W; // edi
  const char *v12; // r9
  __int64 v13; // rax
  __int64 v14; // r14
  __int64 v15; // rdx
  WCHAR *v17; // rcx
  UINT SystemDirectoryW; // eax
  UINT v19; // edi
  __int64 v20; // rcx
  unsigned int appended; // ebx
  const unsigned __int16 *v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rdx
  int v26; // eax
  unsigned int v27; // r12d
  int v28; // eax
  struct _SYSTEM_INFO v29; // [rsp+20h] [rbp-49h] BYREF
  _SYSTEM_INFO SystemInfo; // [rsp+50h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v6 = a2;
  if ( !a2 )
  {
    v15 = 19;
    goto LABEL_11;
  }
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  GetSystemInfo(&SystemInfo);
  if ( SystemInfo.wProcessorArchitecture == 12 && a3 && a1 == 11 )
    a1 = 0;
  v8 = 0;
  if ( a1 != 14 )
    v8 = a1;
  ImageFileMachineFromArchitecture = Common::Deployment::GetImageFileMachineFromArchitecture(v8);
  v10 = ImageFileMachineFromArchitecture;
  if ( ImageFileMachineFromArchitecture != 1 )
  {
    SystemWow64Directory2W = GetSystemWow64Directory2W(0, 0, ImageFileMachineFromArchitecture);
    if ( SystemWow64Directory2W )
      goto LABEL_7;
    if ( v10 != 0x8664
      || GetLastError() != 160
      || (memset(&v29, 0, sizeof(v29)), GetSystemInfo(&v29), v29.wProcessorArchitecture != 12) )
    {
LABEL_56:
      v25 = 64;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v25,
               (unsigned int)"onecore\\admin\\appmodel\\common\\packageid.cpp",
               v12);
    }
    v10 = 1;
  }
  SystemWow64Directory2W = GetSystemDirectoryW(0, 0);
  if ( !SystemWow64Directory2W )
    goto LABEL_56;
LABEL_7:
  v13 = -1;
  do
    ++v13;
  while ( v6[v13] );
  v14 = (unsigned int)v13 + SystemWow64Directory2W + 1;
  if ( (unsigned int)v14 < SystemWow64Directory2W )
  {
    v15 = 69;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\admin\\appmodel\\common\\packageid.cpp",
      (const char *)0x80070057LL,
      v29.dwOemId);
    return 2147942487LL;
  }
  if ( (unsigned int)v14 > ((*(_DWORD *)(a4 + 16) - 1) & (unsigned int)-(*(_DWORD *)(a4 + 16) != 0)) )
  {
    v26 = Common::StringBuffer::SetCapacity((Common::StringBuffer *)a4, v14);
    v27 = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x20C,
        (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)(unsigned int)v26,
        v29.dwOemId);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x48,
        (unsigned int)"onecore\\admin\\appmodel\\common\\packageid.cpp",
        (const char *)v27,
        v29.dwOemId);
      return v27;
    }
  }
  *(_DWORD *)a4 = v14;
  if ( (_DWORD)v14 )
    *(_WORD *)(*(_QWORD *)(a4 + 8) + 2 * v14) = 0;
  v17 = *(WCHAR **)(a4 + 8);
  if ( v10 == 1 )
    SystemDirectoryW = GetSystemDirectoryW(v17, SystemWow64Directory2W);
  else
    SystemDirectoryW = GetSystemWow64Directory2W(v17, SystemWow64Directory2W, v10);
  v19 = SystemDirectoryW;
  if ( !SystemDirectoryW )
  {
    v25 = 82;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v25,
             (unsigned int)"onecore\\admin\\appmodel\\common\\packageid.cpp",
             v12);
  }
  if ( SystemDirectoryW <= ((*(_DWORD *)(a4 + 16) - 1) & (unsigned int)-(*(_DWORD *)(a4 + 16) != 0))
    || (v28 = Common::StringBuffer::SetCapacity((Common::StringBuffer *)a4, SystemDirectoryW), v28 >= 0) )
  {
    v20 = *(_QWORD *)(a4 + 8);
    *(_DWORD *)a4 = v19;
    *(_WORD *)(v20 + 2LL * v19) = 0;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x20C,
      (unsigned int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)(unsigned int)v28,
      v29.dwOemId);
  }
  v29.lpMinimumApplicationAddress = (LPVOID)a4;
  *(_QWORD *)&v29.dwOemId = &Common::StringBufferBuilder::`vftable';
  v29.lpMaximumApplicationAddress = (LPVOID)a4;
  do
  {
    if ( *v6 != 47 && *v6 != 92 )
      break;
    ++v6;
  }
  while ( v6 );
  if ( !v6 || !*v6 )
    return 0;
  appended = Common::PathHelpers::AddTrailingSlashIfNecessary((struct Common::StringBufferBuilder *)&v29);
  if ( (appended & 0x80000000) != 0 )
  {
    v24 = 140;
  }
  else
  {
    v22 = v6;
    v23 = 0x3FFFFFFF;
    do
    {
      if ( !*v22 )
        break;
      ++v22;
      --v23;
    }
    while ( v23 );
    appended = v23 == 0 ? 0x80070057 : 0;
    if ( v23 )
    {
      appended = Common::StringBuilder::AppendChars((Common::StringBuilder *)&v29, v6, v23 != 0 ? 0x3FFFFFFF - v23 : 0);
      if ( (appended & 0x80000000) == 0 )
        return 0;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x35,
        (unsigned int)"onecore\\base\\appmodel\\common\\stringbuilder.cpp",
        (const char *)appended,
        v29.dwOemId);
    }
    v24 = 141;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v24,
    (unsigned int)"onecore\\base\\appmodel\\common\\pathhelpers.cpp",
    (const char *)appended,
    v29.dwOemId);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x56,
    (unsigned int)"onecore\\admin\\appmodel\\common\\packageid.cpp",
    (const char *)appended,
    v29.dwOemId);
  return appended;
}

```

## disassembly

```asm
0x180017d94  push    rbp
0x180017d96  push    rbx
0x180017d97  push    rsi
0x180017d98  push    rdi
0x180017d99  push    r12
0x180017d9b  push    r13
0x180017d9d  push    r14
0x180017d9f  push    r15
0x180017da1  lea     rbp, [rsp-1Fh]
0x180017da6  sub     rsp, 88h
0x180017dad  xor     r13d, r13d
0x180017db0  mov     rbx, r9
0x180017db3  mov     r14b, r8b
0x180017db6  mov     rsi, rdx
0x180017db9  mov     edi, ecx
0x180017dbb  test    rdx, rdx
0x180017dbe  jz      loc_180018086
0x180017dc4  xorps   xmm0, xmm0
0x180017dc7  lea     rcx, [rbp+57h+SystemInfo]; lpSystemInfo
0x180017dcb  movups  xmmword ptr [rbp+57h+SystemInfo], xmm0
0x180017dcf  movups  xmmword ptr [rbp+57h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x180017dd3  movups  xmmword ptr [rbp+57h+SystemInfo.dwNumberOfProcessors], xmm0
0x180017dd7  call    cs:__imp_GetSystemInfo
0x180017ddd  cmp     word ptr [rbp+57h+SystemInfo], 0Ch
0x180017de2  jz      loc_180018090
0x180017de8  mov     ecx, r13d
0x180017deb  cmp     edi, 0Eh
0x180017dee  cmovnz  ecx, edi
0x180017df1  call    ?GetImageFileMachineFromArchitecture@Deployment@Common@@YAGW4SRProcessorArchitecture@StateRepository@@_N@Z; Common::Deployment::GetImageFileMachineFromArchitecture(StateRepository::SRProcessorArchitecture,bool)
0x180017df6  xor     edx, edx; uSize
0x180017df8  xor     ecx, ecx; lpBuffer
0x180017dfa  mov     r12d, 1
0x180017e00  movzx   r15d, ax
0x180017e04  cmp     ax, r12w
0x180017e08  jnz     loc_1800180A5
0x180017e0e  call    cs:__imp_GetSystemDirectoryW
0x180017e14  mov     edi, eax
0x180017e16  test    eax, eax
0x180017e18  jz      loc_1800180FD
0x180017e1e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017e22  inc     rax
0x180017e25  cmp     [rsi+rax*2], r13w
0x180017e2a  jnz     short loc_180017E22
0x180017e2c  lea     r14d, [rdi+1]
0x180017e30  add     r14d, eax
0x180017e33  cmp     r14d, edi
0x180017e36  jnb     short loc_180017E6B
0x180017e38  mov     edx, 45h ; 'E'; void *
0x180017e3d  mov     rcx, [rbp+5Fh]; this
0x180017e41  lea     r8, aOnecoreAdminAp_169; "onecore\\admin\\appmodel\\common\\packa"...
0x180017e48  mov     edi, 80070057h
0x180017e4d  mov     r9d, edi; char *
0x180017e50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017e55  mov     eax, edi
0x180017e57  add     rsp, 88h
0x180017e5e  pop     r15
0x180017e60  pop     r14
0x180017e62  pop     r13
0x180017e64  pop     r12
0x180017e66  pop     rdi
0x180017e67  pop     rsi
0x180017e68  pop     rbx
0x180017e69  pop     rbp
0x180017e6a  retn
0x180017e6b  mov     eax, [rbx+10h]
0x180017e6e  lea     ecx, [rax-1]
0x180017e71  neg     eax
0x180017e73  sbb     eax, eax
0x180017e75  and     eax, ecx
0x180017e77  cmp     r14d, eax
0x180017e7a  ja      loc_180017FE0
0x180017e80  mov     [rbx], r14d
0x180017e83  test    r14d, r14d
0x180017e86  jz      short loc_180017E91
0x180017e88  mov     rcx, [rbx+8]
0x180017e8c  mov     [rcx+r14*2], r13w
0x180017e91  mov     rcx, [rbx+8]; lpBuffer
0x180017e95  mov     edx, edi; uSize
0x180017e97  cmp     r15w, r12w
0x180017e9b  jnz     loc_180017FD1
0x180017ea1  call    cs:__imp_GetSystemDirectoryW
0x180017ea7  mov     edi, eax
0x180017ea9  test    eax, eax
0x180017eab  jz      loc_180017FA8
0x180017eb1  mov     eax, [rbx+10h]
0x180017eb4  lea     ecx, [rax-1]
0x180017eb7  neg     eax
0x180017eb9  sbb     eax, eax
0x180017ebb  and     eax, ecx
0x180017ebd  cmp     edi, eax
0x180017ebf  ja      loc_180017FFD
0x180017ec5  mov     rcx, [rbx+8]
0x180017ec9  mov     edx, edi
0x180017ecb  mov     [rbx], edi
0x180017ecd  mov     [rcx+rdx*2], r13w
0x180017ed2  lea     rax, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x180017ed9  mov     [rbp+57h+var_A0.lpMinimumApplicationAddress], rbx
0x180017edd  mov     qword ptr [rbp+57h+var_A0], rax
0x180017ee1  mov     [rbp+57h+var_A0.lpMaximumApplicationAddress], rbx
0x180017ee5  cmp     word ptr [rsi], 2Fh ; '/'
0x180017ee9  jz      loc_180017FC2
0x180017eef  cmp     word ptr [rsi], 5Ch ; '\'
0x180017ef3  jz      loc_180017FC2
0x180017ef9  test    rsi, rsi
0x180017efc  jz      short loc_180017F6A
0x180017efe  cmp     [rsi], r13w
0x180017f02  jz      short loc_180017F6A
0x180017f04  lea     rcx, [rbp+57h+var_A0]; struct Common::StringBufferBuilder *
0x180017f08  call    ?AddTrailingSlashIfNecessary@PathHelpers@Common@@SAJPEAVStringBufferBuilder@2@@Z; Common::PathHelpers::AddTrailingSlashIfNecessary(Common::StringBufferBuilder *)
0x180017f0d  mov     ebx, eax
0x180017f0f  test    eax, eax
0x180017f11  js      short loc_180017F71
0x180017f13  mov     edx, 3FFFFFFFh
0x180017f18  mov     rax, rsi
0x180017f1b  mov     ecx, edx
0x180017f1d  cmp     [rax], r13w
0x180017f21  jz      short loc_180017F2C
0x180017f23  add     rax, 2
0x180017f27  sub     rcx, r12
0x180017f2a  jnz     short loc_180017F1D
0x180017f2c  mov     rax, rcx
0x180017f2f  neg     rax
0x180017f32  mov     rax, rcx
0x180017f35  sbb     ebx, ebx
0x180017f37  sub     rdx, rcx
0x180017f3a  not     ebx
0x180017f3c  and     ebx, 80070057h
0x180017f42  neg     rax
0x180017f45  sbb     r8, r8
0x180017f48  and     r8, rdx; unsigned int
0x180017f4b  test    rcx, rcx
0x180017f4e  jz      loc_180018064
0x180017f54  mov     rdx, rsi; unsigned __int16 *
0x180017f57  lea     rcx, [rbp+57h+var_A0]; this
0x180017f5b  call    ?AppendChars@StringBuilder@Common@@QEAAJPEBGK@Z; Common::StringBuilder::AppendChars(ushort const *,ulong)
0x180017f60  mov     ebx, eax
0x180017f62  test    eax, eax
0x180017f64  js      loc_18001807C
0x180017f6a  xor     eax, eax
0x180017f6c  jmp     loc_180017E57
0x180017f71  mov     edx, 8Ch; void *
0x180017f76  mov     rcx, [rbp+5Fh]; this
0x180017f7a  lea     r8, aOnecoreBaseApp_109; "onecore\\base\\appmodel\\common\\pathhe"...
0x180017f81  mov     r9d, ebx; char *
0x180017f84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017f89  mov     rcx, [rbp+5Fh]; this
0x180017f8d  lea     r8, aOnecoreAdminAp_169; "onecore\\admin\\appmodel\\common\\packa"...
0x180017f94  mov     r9d, ebx; char *
0x180017f97  mov     edx, 56h ; 'V'; void *
0x180017f9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017fa1  mov     eax, ebx
0x180017fa3  jmp     loc_180017E57
0x180017fa8  mov     edx, 52h ; 'R'; void *
0x180017fad  mov     rcx, [rbp+5Fh]; this
0x180017fb1  lea     r8, aOnecoreAdminAp_169; "onecore\\admin\\appmodel\\common\\packa"...
0x180017fb8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180017fbd  jmp     loc_180017E57
0x180017fc2  add     rsi, 2
0x180017fc6  jnz     loc_180017EE5
0x180017fcc  jmp     loc_180017EF9
0x180017fd1  movzx   r8d, r15w
0x180017fd5  call    cs:__imp_GetSystemWow64Directory2W
0x180017fdb  jmp     loc_180017EA7
0x180017fe0  mov     edx, r14d; unsigned int
0x180017fe3  mov     rcx, rbx; this
0x180017fe6  call    ?SetCapacity@StringBuffer@Common@@QEAAJK@Z; Common::StringBuffer::SetCapacity(ulong)
0x180017feb  mov     r12d, eax
0x180017fee  test    eax, eax
0x180017ff0  js      short loc_18001802C
0x180017ff2  mov     r12d, 1
0x180017ff8  jmp     loc_180017E80
0x180017ffd  mov     edx, edi; unsigned int
0x180017fff  mov     rcx, rbx; this
0x180018002  call    ?SetCapacity@StringBuffer@Common@@QEAAJK@Z; Common::StringBuffer::SetCapacity(ulong)
0x180018007  test    eax, eax
0x180018009  jns     loc_180017EC5
0x18001800f  mov     rcx, [rbp+5Fh]; this
0x180018013  lea     r8, aOnecoreBaseApp_88; "onecore\\base\\appmodel\\common\\widest"...
0x18001801a  mov     r9d, eax; char *
0x18001801d  mov     edx, 20Ch; void *
0x180018022  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180018027  jmp     loc_180017ED2
0x18001802c  mov     rcx, [rbp+5Fh]; this
0x180018030  lea     r8, aOnecoreBaseApp_88; "onecore\\base\\appmodel\\common\\widest"...
0x180018037  mov     r9d, r12d; char *
0x18001803a  mov     edx, 20Ch; void *
0x18001803f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180018044  mov     rcx, [rbp+5Fh]; this
0x180018048  lea     r8, aOnecoreAdminAp_169; "onecore\\admin\\appmodel\\common\\packa"...
0x18001804f  mov     r9d, r12d; char *
0x180018052  mov     edx, 48h ; 'H'; void *
0x180018057  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001805c  mov     eax, r12d
0x18001805f  jmp     loc_180017E57
0x180018064  mov     rcx, [rbp+5Fh]; this
0x180018068  lea     r8, aOnecoreBaseApp_16; "onecore\\base\\appmodel\\common\\string"...
0x18001806f  mov     r9d, ebx; char *
0x180018072  mov     edx, 35h ; '5'; void *
0x180018077  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001807c  mov     edx, 8Dh
0x180018081  jmp     loc_180017F76
0x180018086  mov     edx, 13h
0x18001808b  jmp     loc_180017E3D
0x180018090  test    r14b, r14b
0x180018093  jz      loc_180017DE8
0x180018099  cmp     edi, 0Bh
0x18001809c  cmovz   edi, r13d
0x1800180a0  jmp     loc_180017DE8
0x1800180a5  movzx   r8d, r15w
0x1800180a9  call    cs:__imp_GetSystemWow64Directory2W
0x1800180af  mov     edi, eax
0x1800180b1  test    eax, eax
0x1800180b3  jnz     loc_180017E1E
0x1800180b9  mov     eax, 8664h
0x1800180be  cmp     r15w, ax
0x1800180c2  jnz     short loc_1800180FD
0x1800180c4  call    cs:__imp_GetLastError
0x1800180ca  cmp     eax, 0A0h
0x1800180cf  jnz     short loc_1800180FD
0x1800180d1  xorps   xmm0, xmm0
0x1800180d4  lea     rcx, [rbp+57h+var_A0]; lpSystemInfo
0x1800180d8  movups  xmmword ptr [rbp+57h+var_A0], xmm0
0x1800180dc  movups  xmmword ptr [rbp+57h+var_A0.lpMaximumApplicationAddress], xmm0
0x1800180e0  movups  xmmword ptr [rbp+57h+var_A0.dwNumberOfProcessors], xmm0
0x1800180e4  call    cs:__imp_GetSystemInfo
0x1800180ea  cmp     word ptr [rbp+57h+var_A0], 0Ch
0x1800180ef  jnz     short loc_1800180FD
0x1800180f1  xor     edx, edx
0x1800180f3  mov     r15d, r12d
0x1800180f6  xor     ecx, ecx
0x1800180f8  jmp     loc_180017E0E
0x1800180fd  mov     edx, 40h ; '@'
0x180018102  jmp     loc_180017FAD
```
