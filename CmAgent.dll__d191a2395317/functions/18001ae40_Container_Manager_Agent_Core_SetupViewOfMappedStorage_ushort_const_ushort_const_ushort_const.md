# Container::Manager::Agent::Core::SetupViewOfMappedStorage(ushort const *,ushort const *,ushort const *)

- ea: `0x18001ae40`
- end: `0x18001b5f1`
- name: `?SetupViewOfMappedStorage@Core@Agent@Manager@Container@@YAJPEBG00@Z`
- size: `1969`
- prototype: `__int64 __fastcall(Container::Manager::Agent::Core *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, reparse_path, loader_planting, service_task, installer_update`

## callers

- `0x180005220`

## callees

- `0x180002140`
- `0x180002534`
- `0x180002c48`
- `0x180002f1c`
- `0x1800045e4`
- `0x180005934`
- `0x1800059f8`
- `0x1800063e8`
- `0x180007b2c`
- `0x18000892c`
- `0x1800095f8`
- `0x18000a768`
- `0x18000af30`
- `0x18000bb98`
- `0x18000bc38`
- `0x18001ae40`
- `0x18001c350`
- `0x180024afc`
- `0x180024f94`
- `0x1800361b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001af97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001afa8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001af97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001afa8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001aff4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b108`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b4e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b540`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b598`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001aff4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b108`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b4e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b540`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001b598`
- `ntdll!RtlInitUnicodeString` at `0x18001b086`
- `ntdll!RtlInitUnicodeString` at `0x18001b086`
- `ntdll!RtlNtPathNameToDosPathName` at `0x18001b176`
- `ntdll!RtlNtPathNameToDosPathName` at `0x18001b176`
- `ntdll!RtlpEnsureBufferSize` at `0x18001b0bf`
- `ntdll!RtlpEnsureBufferSize` at `0x18001b0bf`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001aed6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001aed6`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001af87`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18001af87`

## string_xrefs

- `0x18001aef5`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x18001afcd`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x18001b0da`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x18001b1d3`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x18001b278`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x18001b365`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x18001b3b9`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x18001b473`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x18001b51f`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`
- `0x18001b57f`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`

## pseudocode

```c
__int64 __fastcall Container::Manager::Agent::Core::SetupViewOfMappedStorage(
        Container::Manager::Agent::Core *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  HANDLE FileW; // rdi
  const char *v8; // r9
  __int64 v9; // r15
  unsigned int LastError; // ebx
  WCHAR *v11; // rbx
  DWORD i; // r14d
  WCHAR *v13; // rax
  const struct std::nothrow_t *v14; // rdx
  WCHAR *v15; // rsi
  const char *v16; // r9
  const struct std::nothrow_t *v17; // rdx
  unsigned __int64 v18; // r14
  UCHAR *v19; // rax
  UCHAR *v20; // rbx
  UCHAR *p_ReservedForAllocatedSize; // rcx
  USHORT v22; // dx
  USHORT Length; // r9
  unsigned __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // rdx
  const struct std::nothrow_t *v27; // rdx
  int v28; // r14d
  const struct std::nothrow_t *v29; // rdx
  unsigned __int64 v30; // rdx
  NTSTATUS v31; // eax
  __int64 v32; // rdx
  const struct std::nothrow_t *v33; // rdx
  const struct std::nothrow_t *v34; // rdx
  __int64 v35; // r8
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // rdx
  void *v39; // rcx
  __int64 v40; // rdx
  int v41; // eax
  int v42; // eax
  const struct std::nothrow_t *v43; // rdx
  const struct std::nothrow_t *v44; // rdx
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  void *v47[2]; // [rsp+40h] [rbp-C0h] BYREF
  _WORD v48[8]; // [rsp+50h] [rbp-B0h] BYREF
  void *v49; // [rsp+60h] [rbp-A0h] BYREF
  char *v50; // [rsp+68h] [rbp-98h]
  _WORD v51[8]; // [rsp+70h] [rbp-90h] BYREF
  DWORD BytesReturned; // [rsp+80h] [rbp-80h] BYREF
  void *v53[2]; // [rsp+88h] [rbp-78h] BYREF
  _WORD v54[8]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v55; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v56; // [rsp+B8h] [rbp-48h]
  void *v57; // [rsp+C0h] [rbp-40h]
  struct _UNICODE_STRING DestinationString; // [rsp+C8h] [rbp-38h] BYREF
  _RTL_UNICODE_STRING_BUFFER Path; // [rsp+D8h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  *(_QWORD *)&v55 = a2;
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    &Path.ByteBuffer.ReservedForIMalloc,
    "SetupViewOfMappedStorage",
    a3,
    a4);
  Path.ByteBuffer.ReservedForIMalloc = &CmAgentTraceProvider::SetupViewOfMappedStorage::`vftable';
  CmAgentTraceProvider::SetupViewOfMappedStorage::StartActivity(
    (CmAgentTraceProvider::SetupViewOfMappedStorage *)&Path.ByteBuffer.ReservedForIMalloc,
    (const unsigned __int16 *)this,
    a2,
    a3 != 0);
  FileW = CreateFileW((LPCWSTR)this, 0x80000000, 3u, 0, 3u, 0x2200000u, 0);
  v9 = -1;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x53D,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
                  v8);
    goto LABEL_91;
  }
  v11 = 0;
  for ( i = 216; ; i *= 2 )
  {
    v13 = (WCHAR *)operator new[](i, (const struct std::nothrow_t *)&std::nothrow);
    v15 = v13;
    if ( v13 )
      memset_0(v13, 0, i);
    else
      v15 = 0;
    if ( v11 )
      operator delete(v11, v14);
    if ( !v15 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x549,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
        (const char *)0x8007000ELL,
        dwCreationDisposition);
      if ( FileW )
        CloseHandle(FileW);
      Path.ByteBuffer.ReservedForIMalloc = &CmAgentTraceProvider::SetupViewOfMappedStorage::`vftable';
      wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&Path.ByteBuffer.ReservedForIMalloc);
      wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(&Path.ByteBuffer.ReservedForIMalloc);
      return 2147942414LL;
    }
    BytesReturned = 0;
    if ( DeviceIoControl(FileW, 0x900A8u, 0, 0, v15, i, &BytesReturned, 0) )
      break;
    if ( GetLastError() != 122 && GetLastError() != 234 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x560,
                    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
                    v16);
      operator delete(v15, v17);
      if ( FileW )
        CloseHandle(FileW);
      goto LABEL_91;
    }
    v11 = v15;
  }
  v18 = v15[5];
  v19 = (UCHAR *)operator new[](v18, (const struct std::nothrow_t *)&std::nothrow);
  v20 = v19;
  if ( !v19 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x56E,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
      (const char *)0x8007000ELL,
      dwCreationDisposition);
    goto LABEL_88;
  }
  memset_0(v19, 0, (unsigned int)v18);
  *(_DWORD *)(&Path.String.MaximumLength + 1) = 0;
  Path.ByteBuffer.ReservedForAllocatedSize = 0;
  if ( v18 >= 2 )
  {
    p_ReservedForAllocatedSize = v20;
  }
  else
  {
    p_ReservedForAllocatedSize = (UCHAR *)&Path.ByteBuffer.ReservedForAllocatedSize;
    v18 = 2;
  }
  Path.ByteBuffer.Buffer = p_ReservedForAllocatedSize;
  Path.ByteBuffer.Size = v18;
  Path.ByteBuffer.StaticBuffer = p_ReservedForAllocatedSize;
  Path.ByteBuffer.StaticSize = v18;
  Path.String.Buffer = (PWSTR)p_ReservedForAllocatedSize;
  if ( p_ReservedForAllocatedSize )
    *(_WORD *)p_ReservedForAllocatedSize = 0;
  Path.String.Length = 0;
  Path.String.MaximumLength = v18;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, v15 + 8);
  v22 = 0;
  Path.String.Length = 0;
  Length = DestinationString.Length;
  v24 = DestinationString.Length + 2LL;
  if ( v24 > 0xFFFE )
  {
    v25 = 3221225734LL;
    goto LABEL_27;
  }
  if ( v24 > Path.ByteBuffer.Size )
  {
    if ( RtlpEnsureBufferSize(0, &Path.ByteBuffer, v24) < 0 )
    {
      v25 = 3221225495LL;
LABEL_27:
      v26 = 1404;
LABEL_28:
      v28 = wil::details::in1diag3::Return_NtStatus(
              retaddr,
              (void *)v26,
              (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
              (const char *)v25,
              dwCreationDisposition);
LABEL_29:
      operator delete(v20, v27);
      operator delete(v15, v29);
      if ( FileW )
        CloseHandle(FileW);
      LastError = v28;
      goto LABEL_91;
    }
    v22 = Path.String.Length;
    Length = DestinationString.Length;
  }
  Path.String.Buffer = (PWSTR)Path.ByteBuffer.Buffer;
  memmove_0(&Path.ByteBuffer.Buffer[2 * ((unsigned __int64)v22 >> 1)], DestinationString.Buffer, Length);
  v30 = (unsigned __int16)(Path.String.Length + DestinationString.Length);
  Path.String.MaximumLength = v30 + 2;
  Path.String.Length += DestinationString.Length;
  Path.String.Buffer[v30 >> 1] = 0;
  v31 = RtlNtPathNameToDosPathName(0, &Path, 0, 0);
  if ( v31 < 0 )
  {
    v25 = (unsigned int)v31;
    v26 = 1410;
    goto LABEL_28;
  }
  v47[0] = v48;
  v47[1] = v48;
  v48[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v47,
                           L"\\\\?\\",
                           4) )
  {
    v32 = 1413;
    goto LABEL_37;
  }
  if ( Path.String.Buffer )
  {
    v35 = -1;
    do
      ++v35;
    while ( Path.String.Buffer[v35] );
  }
  else
  {
    v35 = 0;
  }
  if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                          v47,
                          Path.String.Buffer,
                          v35) )
  {
    v49 = v51;
    v50 = (char *)v51;
    v51[0] = 0;
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             &v49,
                             L"\\\\?\\vmsmb\\VSMB-{dcc079ae-60ba-4d07-847c-3493609c0870}\\",
                             54) )
    {
      v36 = 1417;
LABEL_50:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v36,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
        (const char *)0x8007000ELL,
        dwCreationDisposition);
LABEL_51:
      if ( v49 != v51 )
        operator delete(v49, (const struct std::nothrow_t *)&std::nothrow);
      goto LABEL_38;
    }
    if ( (_QWORD)v55 )
    {
      v37 = -1;
      do
        ++v37;
      while ( *(_WORD *)(v55 + 2 * v37) );
    }
    else
    {
      v37 = 0;
    }
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             &v49,
                             v55,
                             v37) )
    {
      v36 = 1418;
      goto LABEL_50;
    }
    if ( a3 )
    {
      v53[0] = v54;
      v53[1] = v54;
      v54[0] = 0;
      *(_QWORD *)&v55 = v49;
      *((_QWORD *)&v55 + 1) = (v50 - (_BYTE *)v49) >> 1;
      if ( !(unsigned __int8)Csl::Path::Assign((Csl::Path *)v53) )
      {
        v40 = 1424;
        goto LABEL_67;
      }
      *(_QWORD *)&v55 = a3;
      do
        ++v9;
      while ( a3[v9] );
      *((_QWORD *)&v55 + 1) = v9;
      if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)v53) )
      {
        v40 = 1425;
LABEL_67:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v40,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
          (const char *)0x8007000ELL,
          dwCreationDisposition);
        if ( v53[0] != v54 )
          operator delete(v53[0], (const struct std::nothrow_t *)&std::nothrow);
        goto LABEL_51;
      }
      v41 = Csl::UnlockVolumeWithExternalKey(v47, v53);
      v28 = v41;
      if ( v41 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x595,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
          (const char *)(unsigned int)v41,
          dwCreationDisposition);
        if ( v53[0] != v54 )
          operator delete(v53[0], (const struct std::nothrow_t *)&std::nothrow);
        goto LABEL_72;
      }
      v39 = v53[0];
      if ( v53[0] != v54 )
        operator delete(v53[0], (const struct std::nothrow_t *)&std::nothrow);
    }
    v56 = 0;
    v55 = UTILITY_VM_LAYER_ID;
    v57 = v49;
    v42 = WciSetupFilter(v39, v38, v47[0], &v55);
    v28 = v42;
    if ( v42 >= 0 )
    {
      wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(
        &Path.ByteBuffer.ReservedForIMalloc,
        0);
      if ( v49 != v51 )
        operator delete(v49, (const struct std::nothrow_t *)&std::nothrow);
      if ( v47[0] != v48 )
        operator delete(v47[0], (const struct std::nothrow_t *)&std::nothrow);
      operator delete(v20, v43);
      operator delete(v15, v44);
      if ( FileW )
        CloseHandle(FileW);
      Path.ByteBuffer.ReservedForIMalloc = &CmAgentTraceProvider::SetupViewOfMappedStorage::`vftable';
      wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&Path.ByteBuffer.ReservedForIMalloc);
      wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(&Path.ByteBuffer.ReservedForIMalloc);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5A8,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
      (const char *)(unsigned int)v42,
      dwCreationDisposition);
LABEL_72:
    if ( v49 != v51 )
      operator delete(v49, (const struct std::nothrow_t *)&std::nothrow);
    if ( v47[0] != v48 )
      operator delete(v47[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_29;
  }
  v32 = 1414;
LABEL_37:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v32,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
    (const char *)0x8007000ELL,
    dwCreationDisposition);
LABEL_38:
  if ( v47[0] != v48 )
    operator delete(v47[0], (const struct std::nothrow_t *)&std::nothrow);
  operator delete(v20, v33);
LABEL_88:
  operator delete(v15, v34);
  if ( FileW )
    CloseHandle(FileW);
  LastError = -2147024882;
LABEL_91:
  Path.ByteBuffer.ReservedForIMalloc = &CmAgentTraceProvider::SetupViewOfMappedStorage::`vftable';
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&Path.ByteBuffer.ReservedForIMalloc);
  wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(&Path.ByteBuffer.ReservedForIMalloc);
  return LastError;
}

```

## disassembly

```asm
0x18001ae40  mov     [rsp-8+arg_10], rbx
0x18001ae45  push    rbp
0x18001ae46  push    rsi
0x18001ae47  push    rdi
0x18001ae48  push    r12
0x18001ae4a  push    r13
0x18001ae4c  push    r14
0x18001ae4e  push    r15
0x18001ae50  lea     rbp, [rsp-170h]
0x18001ae58  sub     rsp, 270h
0x18001ae5f  mov     rax, cs:__security_cookie
0x18001ae66  xor     rax, rsp
0x18001ae69  mov     [rbp+1A0h+var_40], rax
0x18001ae70  mov     r13, r8
0x18001ae73  mov     rdi, rdx
0x18001ae76  mov     qword ptr [rbp+1A0h+var_1F8], rdx
0x18001ae7a  mov     rbx, rcx
0x18001ae7d  lea     rdx, aSetupviewofmap; "SetupViewOfMappedStorage"
0x18001ae84  lea     rcx, [rbp+1A0h+Path.ByteBuffer.ReservedForIMalloc]
0x18001ae88  call    ??0?$ActivityBase@VCmAgentTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<CmAgentTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001ae8d  lea     rax, ??_7SetupViewOfMappedStorage@CmAgentTraceProvider@@6B@; const CmAgentTraceProvider::SetupViewOfMappedStorage::`vftable'
0x18001ae94  mov     [rbp+1A0h+Path.ByteBuffer.ReservedForIMalloc], rax
0x18001ae98  test    r13, r13
0x18001ae9b  setnz   r9b; bool
0x18001ae9f  mov     r8, rdi; unsigned __int16 *
0x18001aea2  mov     rdx, rbx; unsigned __int16 *
0x18001aea5  lea     rcx, [rbp+1A0h+Path.ByteBuffer.ReservedForIMalloc]; this
0x18001aea9  call    ?StartActivity@SetupViewOfMappedStorage@CmAgentTraceProvider@@QEAAXPEBG0_N@Z; CmAgentTraceProvider::SetupViewOfMappedStorage::StartActivity(ushort const *,ushort const *,bool)
0x18001aeae  nop
0x18001aeaf  mov     [rsp+2A0h+hTemplateFile], 0; hTemplateFile
0x18001aeb8  mov     [rsp+2A0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18001aec0  mov     r8d, 3; dwShareMode
0x18001aec6  mov     [rsp+2A0h+dwCreationDisposition], r8d; int
0x18001aecb  xor     r9d, r9d; lpSecurityAttributes
0x18001aece  mov     edx, 80000000h; dwDesiredAccess
0x18001aed3  mov     rcx, rbx; lpFileName
0x18001aed6  call    cs:__imp_CreateFileW
0x18001aedd  nop     dword ptr [rax+rax+00h]
0x18001aee2  mov     rdi, rax
0x18001aee5  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001aee9  cmp     rax, r15
0x18001aeec  jnz     short loc_18001AF0D
0x18001aeee  mov     rcx, [rbp+1A8h]; this
0x18001aef5  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x18001aefc  mov     edx, 53Dh; void *
0x18001af01  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001af06  mov     ebx, eax
0x18001af08  jmp     loc_18001B551
0x18001af0d  xor     ebx, ebx
0x18001af0f  mov     r14d, 0D8h
0x18001af15  mov     r12d, r14d
0x18001af18  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001af1f  mov     ecx, r14d; unsigned __int64
0x18001af22  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001af27  mov     rsi, rax
0x18001af2a  test    rax, rax
0x18001af2d  jz      short loc_18001AF41
0x18001af2f  mov     r8d, r12d; Size
0x18001af32  xor     edx, edx; Val
0x18001af34  mov     rcx, rax; void *
0x18001af37  call    memset_0
0x18001af3c  xor     r12d, r12d
0x18001af3f  jmp     short loc_18001AF47
0x18001af41  xor     r12d, r12d
0x18001af44  mov     esi, r12d
0x18001af47  test    rbx, rbx
0x18001af4a  jz      short loc_18001AF54
0x18001af4c  mov     rcx, rbx; void *
0x18001af4f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001af54  test    rsi, rsi
0x18001af57  jz      loc_18001B572
0x18001af5d  mov     [rbp+1A0h+BytesReturned], r12d
0x18001af61  mov     [rsp+2A0h+lpOverlapped], r12; lpOverlapped
0x18001af66  lea     rax, [rbp+1A0h+BytesReturned]
0x18001af6a  mov     [rsp+2A0h+hTemplateFile], rax; lpBytesReturned
0x18001af6f  mov     [rsp+2A0h+dwFlagsAndAttributes], r14d; nOutBufferSize
0x18001af74  mov     qword ptr [rsp+2A0h+dwCreationDisposition], rsi; int
0x18001af79  xor     r9d, r9d; nInBufferSize
0x18001af7c  xor     r8d, r8d; lpInBuffer
0x18001af7f  mov     edx, 900A8h; dwIoControlCode
0x18001af84  mov     rcx, rdi; hDevice
0x18001af87  call    cs:__imp_DeviceIoControl
0x18001af8e  nop     dword ptr [rax+rax+00h]
0x18001af93  test    eax, eax
0x18001af95  jnz     short loc_18001B005
0x18001af97  call    cs:__imp_GetLastError
0x18001af9e  nop     dword ptr [rax+rax+00h]
0x18001afa3  cmp     eax, 7Ah ; 'z'
0x18001afa6  jz      short loc_18001AFBB
0x18001afa8  call    cs:__imp_GetLastError
0x18001afaf  nop     dword ptr [rax+rax+00h]
0x18001afb4  cmp     eax, 0EAh
0x18001afb9  jnz     short loc_18001AFC6
0x18001afbb  mov     rbx, rsi
0x18001afbe  add     r14d, r14d
0x18001afc1  jmp     loc_18001AF15
0x18001afc6  mov     rcx, [rbp+1A8h]; this
0x18001afcd  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x18001afd4  mov     edx, 560h; void *
0x18001afd9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001afde  mov     ebx, eax
0x18001afe0  mov     rcx, rsi; void *
0x18001afe3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001afe8  test    rdi, rdi
0x18001afeb  jz      loc_18001B551
0x18001aff1  mov     rcx, rdi; hObject
0x18001aff4  call    cs:__imp_CloseHandle
0x18001affb  nop     dword ptr [rax+rax+00h]
0x18001b000  jmp     loc_18001B551
0x18001b005  movzx   r14d, word ptr [rsi+0Ah]
0x18001b00a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001b011  mov     ecx, r14d; unsigned __int64
0x18001b014  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001b019  mov     rbx, rax
0x18001b01c  test    rax, rax
0x18001b01f  jz      loc_18001B512
0x18001b025  mov     r8d, r14d; Size
0x18001b028  xor     edx, edx; Val
0x18001b02a  mov     rcx, rax; void *
0x18001b02d  call    memset_0
0x18001b032  mov     dword ptr [rbp+1A0h+Path.String+4], r12d
0x18001b036  mov     [rbp+1A0h+Path.ByteBuffer.ReservedForAllocatedSize], r12
0x18001b03a  mov     eax, 2
0x18001b03f  cmp     r14, rax
0x18001b042  jnb     short loc_18001B04D
0x18001b044  lea     rcx, [rbp+1A0h+Path.ByteBuffer.ReservedForAllocatedSize]
0x18001b048  mov     r14d, eax
0x18001b04b  jmp     short loc_18001B050
0x18001b04d  mov     rcx, rbx
0x18001b050  mov     [rbp+1A0h+Path.ByteBuffer.Buffer], rcx
0x18001b054  mov     [rbp+1A0h+Path.ByteBuffer.Size], r14
0x18001b058  mov     [rbp+1A0h+Path.ByteBuffer.StaticBuffer], rcx
0x18001b05c  mov     [rbp+1A0h+Path.ByteBuffer.StaticSize], r14
0x18001b060  mov     [rbp+1A0h+Path.String.Buffer], rcx
0x18001b064  test    rcx, rcx
0x18001b067  jz      short loc_18001B06D
0x18001b069  mov     [rcx], r12w
0x18001b06d  mov     [rbp+1A0h+Path.String.Length], r12w
0x18001b072  mov     [rbp+1A0h+Path.String.MaximumLength], r14w
0x18001b077  xorps   xmm0, xmm0
0x18001b07a  movups  xmmword ptr [rbp+1A0h+DestinationString.Length], xmm0
0x18001b07e  lea     rdx, [rsi+10h]; SourceString
0x18001b082  lea     rcx, [rbp+1A0h+DestinationString]; DestinationString
0x18001b086  call    cs:__imp_RtlInitUnicodeString
0x18001b08d  nop     dword ptr [rax+rax+00h]
0x18001b092  mov     edx, r12d
0x18001b095  mov     [rbp+1A0h+Path.String.Length], dx
0x18001b099  movzx   r9d, [rbp+1A0h+DestinationString.Length]
0x18001b09e  lea     r8, [r9+2]; RequiredSize
0x18001b0a2  cmp     r8, 0FFFEh
0x18001b0a9  jbe     short loc_18001B0B3
0x18001b0ab  mov     r9d, 0C0000106h
0x18001b0b1  jmp     short loc_18001B0D5
0x18001b0b3  cmp     r8, [rbp+1A0h+Path.ByteBuffer.Size]
0x18001b0b7  jbe     short loc_18001B125
0x18001b0b9  lea     rdx, [rbp+1A0h+Path.ByteBuffer]; Buffer
0x18001b0bd  xor     ecx, ecx; Flags
0x18001b0bf  call    cs:__imp_RtlpEnsureBufferSize
0x18001b0c6  nop     dword ptr [rax+rax+00h]
0x18001b0cb  test    eax, eax
0x18001b0cd  jns     short loc_18001B11C
0x18001b0cf  mov     r9d, 0C0000017h; char *
0x18001b0d5  mov     edx, 57Ch; void *
0x18001b0da  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x18001b0e1  mov     rcx, [rbp+1A8h]; this
0x18001b0e8  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18001b0ed  mov     r14d, eax
0x18001b0f0  mov     rcx, rbx; void *
0x18001b0f3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001b0f8  mov     rcx, rsi; void *
0x18001b0fb  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001b100  test    rdi, rdi
0x18001b103  jz      short loc_18001B114
0x18001b105  mov     rcx, rdi; hObject
0x18001b108  call    cs:__imp_CloseHandle
0x18001b10f  nop     dword ptr [rax+rax+00h]
0x18001b114  mov     ebx, r14d
0x18001b117  jmp     loc_18001B551
0x18001b11c  movzx   edx, [rbp+1A0h+Path.String.Length]
0x18001b120  movzx   r9d, [rbp+1A0h+DestinationString.Length]
0x18001b125  mov     rcx, [rbp+1A0h+Path.ByteBuffer.Buffer]
0x18001b129  mov     [rbp+1A0h+Path.String.Buffer], rcx
0x18001b12d  movzx   r8d, r9w; Size
0x18001b131  movzx   eax, dx
0x18001b134  shr     rax, 1
0x18001b137  lea     rcx, [rcx+rax*2]; void *
0x18001b13b  mov     rdx, [rbp+1A0h+DestinationString.Buffer]; Src
0x18001b13f  call    memmove_0
0x18001b144  movzx   eax, [rbp+1A0h+DestinationString.Length]
0x18001b148  add     ax, [rbp+1A0h+Path.String.Length]
0x18001b14c  movzx   edx, ax
0x18001b14f  mov     eax, 2
0x18001b154  add     eax, edx
0x18001b156  mov     [rbp+1A0h+Path.String.MaximumLength], ax
0x18001b15a  mov     [rbp+1A0h+Path.String.Length], dx
0x18001b15e  shr     rdx, 1
0x18001b161  mov     rax, [rbp+1A0h+Path.String.Buffer]
0x18001b165  mov     [rax+rdx*2], r12w
0x18001b16a  xor     r9d, r9d; Unknown
0x18001b16d  xor     r8d, r8d; PathType
0x18001b170  lea     rdx, [rbp+1A0h+Path]; Path
0x18001b174  xor     ecx, ecx; Flags
0x18001b176  call    cs:__imp_RtlNtPathNameToDosPathName
0x18001b17d  nop     dword ptr [rax+rax+00h]
0x18001b182  test    eax, eax
0x18001b184  jns     short loc_18001B193
0x18001b186  mov     r9d, eax
0x18001b189  mov     edx, 582h
0x18001b18e  jmp     loc_18001B0DA
0x18001b193  lea     rax, [rsp+2A0h+var_250]
0x18001b198  mov     [rsp+2A0h+var_260], rax
0x18001b19d  lea     rax, [rsp+2A0h+var_250]
0x18001b1a2  mov     [rsp+2A0h+var_258], rax
0x18001b1a7  mov     [rsp+2A0h+var_250], r12w
0x18001b1ad  mov     r8d, 4
0x18001b1b3  lea     rdx, String2; "\\\\?\\"
0x18001b1ba  lea     rcx, [rsp+2A0h+var_260]
0x18001b1bf  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18001b1c4  test    al, al
0x18001b1c6  jnz     short loc_18001B20E
0x18001b1c8  mov     edx, 585h; void *
0x18001b1cd  mov     r9d, 8007000Eh; char *
0x18001b1d3  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x18001b1da  mov     rcx, [rbp+1A8h]; this
0x18001b1e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b1e6  lea     rax, [rsp+2A0h+var_250]
0x18001b1eb  mov     rcx, [rsp+2A0h+var_260]; void *
0x18001b1f0  cmp     rcx, rax
0x18001b1f3  jz      short loc_18001B201
0x18001b1f5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001b1fc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001b201  mov     rcx, rbx; void *
0x18001b204  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001b209  jmp     loc_18001B530
0x18001b20e  mov     rdx, [rbp+1A0h+Path.String.Buffer]
0x18001b212  test    rdx, rdx
0x18001b215  jz      short loc_18001B226
0x18001b217  mov     r8, r15
0x18001b21a  inc     r8
0x18001b21d  cmp     [rdx+r8*2], r12w
0x18001b222  jnz     short loc_18001B21A
0x18001b224  jmp     short loc_18001B229
0x18001b226  mov     r8, r12
0x18001b229  lea     rcx, [rsp+2A0h+var_260]
0x18001b22e  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18001b233  test    al, al
0x18001b235  jnz     short loc_18001B23E
0x18001b237  mov     edx, 586h
0x18001b23c  jmp     short loc_18001B1CD
0x18001b23e  lea     rax, [rsp+2A0h+var_230]
0x18001b243  mov     [rsp+2A0h+var_240], rax
0x18001b248  lea     rax, [rsp+2A0h+var_230]
0x18001b24d  mov     [rsp+2A0h+var_238], rax
0x18001b252  mov     [rsp+2A0h+var_230], r12w
0x18001b258  mov     r8d, 36h ; '6'
0x18001b25e  lea     rdx, aVmsmbVsmbDcc07; "\\\\?\\vmsmb\\VSMB-{dcc079ae-60ba-4d07-"...
0x18001b265  lea     rcx, [rsp+2A0h+var_240]
0x18001b26a  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18001b26f  test    al, al
0x18001b271  jnz     short loc_18001B2B5
0x18001b273  mov     edx, 589h; void *
0x18001b278  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x18001b27f  mov     r9d, 8007000Eh; char *
0x18001b285  mov     rcx, [rbp+1A8h]; this
0x18001b28c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b291  lea     rax, [rsp+2A0h+var_230]
0x18001b296  mov     rcx, [rsp+2A0h+var_240]; void *
0x18001b29b  cmp     rcx, rax
0x18001b29e  jz      loc_18001B1E6
0x18001b2a4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001b2ab  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001b2b0  jmp     loc_18001B1E6
0x18001b2b5  mov     rax, qword ptr [rbp+1A0h+var_1F8]
0x18001b2b9  test    rax, rax
0x18001b2bc  jz      short loc_18001B2CD
0x18001b2be  mov     r8, r15
0x18001b2c1  inc     r8
0x18001b2c4  cmp     [rax+r8*2], r12w
0x18001b2c9  jnz     short loc_18001B2C1
0x18001b2cb  jmp     short loc_18001B2D0
0x18001b2cd  mov     r8, r12
0x18001b2d0  mov     rdx, rax
0x18001b2d3  lea     rcx, [rsp+2A0h+var_240]
0x18001b2d8  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18001b2dd  test    al, al
0x18001b2df  jnz     short loc_18001B2E8
0x18001b2e1  mov     edx, 58Ah
0x18001b2e6  jmp     short loc_18001B278
0x18001b2e8  test    r13, r13
0x18001b2eb  jz      loc_18001B43B
0x18001b2f1  lea     rax, [rbp+1A0h+var_208]
0x18001b2f5  mov     [rbp+1A0h+var_218], rax
0x18001b2f9  lea     rax, [rbp+1A0h+var_208]
0x18001b2fd  mov     [rbp+1A0h+var_210], rax
0x18001b301  mov     [rbp+1A0h+var_208], r12w
0x18001b306  mov     rax, [rsp+2A0h+var_240]
0x18001b30b  mov     qword ptr [rbp+1A0h+var_1F8], rax
0x18001b30f  mov     rcx, [rsp+2A0h+var_238]
0x18001b314  sub     rcx, rax
0x18001b317  sar     rcx, 1
  ... truncated ...
```
