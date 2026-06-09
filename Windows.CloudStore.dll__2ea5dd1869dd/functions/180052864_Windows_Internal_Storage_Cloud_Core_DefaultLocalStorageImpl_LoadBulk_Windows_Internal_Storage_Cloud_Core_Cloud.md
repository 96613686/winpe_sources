# Windows::Internal::Storage::Cloud::Core::DefaultLocalStorageImpl::LoadBulk(Windows::Internal::Storage::Cloud::Core::CloudStoreItemId const &,bool,std::basic_string<char,std::char_traits<char>,std::allocator<char>> &)

- ea: `0x180052864`
- end: `0x180052baa`
- name: `?LoadBulk@DefaultLocalStorageImpl@Core@Cloud@Storage@Internal@Windows@@AEAAJAEBVCloudStoreItemId@23456@_NAEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `838`
- prototype: `__int64 __fastcall(__int64, const char *, char, __int64)`
- caller_count: `2`
- callee_count: `20`
- tags: `file_ops, registry_config`

## callers

- `0x180013fd0`
- `0x1800527c0`

## callees

- `0x180016cf4`
- `0x1800238d0`
- `0x180023fd4`
- `0x1800320d4`
- `0x180052704`
- `0x180052730`
- `0x180052864`
- `0x180052ce4`
- `0x180054000`
- `0x180054258`
- `0x18005b244`
- `0x18005de38`
- `0x18005ded4`
- `0x1800626e8`
- `0x18007aaa8`
- `0x1800c8458`
- `0x1800fc644`
- `0x1800febe4`
- `0x1801201a0`
- `0x180120c94`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800529c3`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800529c3`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180052a5c`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180052a5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180052b28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180052b28`

## string_xrefs

- `0x180052996`: `onecoreuap\shell\cloudstore\store\cache\src\defaultlocalstorage.cpp`
- `0x1800529d4`: `onecoreuap\shell\cloudstore\store\cache\src\defaultlocalstorage.cpp`
- `0x180052a0a`: `onecoreuap\shell\cloudstore\store\cache\src\defaultlocalstorage.cpp`
- `0x180052a6d`: `onecoreuap\shell\cloudstore\store\cache\src\defaultlocalstorage.cpp`
- `0x180052a97`: `onecoreuap\shell\cloudstore\store\cache\src\defaultlocalstorage.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Storage::Cloud::Core::DefaultLocalStorageImpl::LoadBulk(
        __int64 a1,
        const char *a2,
        char a3,
        __int64 a4)
{
  const char *v6; // r12
  const char *v7; // r14
  const char *v8; // rdi
  const char *v9; // rsi
  const char *v10; // r15
  __int64 v11; // rcx
  unsigned int v12; // r14d
  char v13; // al
  char *v14; // rsi
  const char *v15; // r9
  unsigned int LastError; // ebx
  DWORD LowPart; // ebx
  DWORD v18; // edi
  size_t v19; // r8
  void *v20; // rdi
  const char *v21; // r9
  const unsigned __int16 *v23; // rbx
  int lpOverlapped; // [rsp+20h] [rbp-E0h]
  int lpOverlappeda; // [rsp+20h] [rbp-E0h]
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-D0h] BYREF
  void *lpBuffer; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE hFile; // [rsp+40h] [rbp-C0h] BYREF
  _LARGE_INTEGER FileSize; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v30; // [rsp+50h] [rbp-B0h]
  unsigned __int16 *v31[2]; // [rsp+58h] [rbp-A8h] BYREF
  __m128i si128; // [rsp+68h] [rbp-98h]
  _QWORD v33[42]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  v30 = a4;
  v6 = "Baseline";
  if ( !a3 )
    v6 = "Payload";
  v7 = a2 + 128;
  if ( *((_QWORD *)a2 + 19) > 0xFu )
    v7 = *(const char **)v7;
  v8 = a2 + 160;
  if ( *((_QWORD *)a2 + 23) > 0xFu )
    v8 = *(const char **)v8;
  v9 = a2 + 64;
  if ( *((_QWORD *)a2 + 11) > 0xFu )
    v9 = *(const char **)v9;
  if ( *((_QWORD *)a2 + 3) <= 0xFu )
    v10 = a2;
  else
    v10 = *(const char **)a2;
  wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v33,
    "LoadBulkActivity");
  v33[0] = &Windows::Internal::Storage::Cloud::CloudStoreTelemetry::LoadBulkActivity::`vftable';
  Windows::Internal::Storage::Cloud::CloudStoreTelemetry::LoadBulkActivity::StartActivity(
    (Windows::Internal::Storage::Cloud::CloudStoreTelemetry::LoadBulkActivity *)v33,
    v10,
    v9,
    v8,
    v7,
    v6);
  *(_OWORD *)v31 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v31[0]) = 0;
  hFile = (HANDLE)-1LL;
  v12 = Windows::Internal::Storage::Cloud::Core::DefaultLocalStorageImpl::InitializeFileAndPath(
          v11,
          (const WCHAR *)v31,
          &hFile,
          0,
          a3,
          (__int64)a2);
  v13 = 1;
  if ( v12 + 2147024894 <= 1 || !v12 )
    v13 = 0;
  if ( v13 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2AF,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\defaultlocalstorage.cpp",
      (const char *)v12,
      lpOverlapped);
  v14 = (char *)hFile;
  if ( !v12 )
  {
    FileSize.QuadPart = 0;
    if ( !GetFileSizeEx(hFile, &FileSize) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x2B4,
                    (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\defaultlocalstorage.cpp",
                    v15);
LABEL_27:
      std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,bool>::~pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,bool>(&hFile);
      std::wstring::~wstring(v31);
      Windows::Internal::Storage::Cloud::CloudStoreTelemetry::LoadBulkActivity::~LoadBulkActivity((Windows::Internal::Storage::Cloud::CloudStoreTelemetry::LoadBulkActivity *)v33);
      return LastError;
    }
    LowPart = FileSize.LowPart;
    if ( FileSize.QuadPart > 0xFFFFFFFFLL )
    {
      LastError = -2147024673;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2B9,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\defaultlocalstorage.cpp",
        (const char *)0x800700DFLL,
        lpOverlapped);
      goto LABEL_27;
    }
    v18 = FileSize.LowPart + 1;
    std::make_unique<char [0],0>(&lpBuffer, FileSize.LowPart + 1);
    v19 = v18;
    v20 = lpBuffer;
    memset_0(lpBuffer, 0, v19);
    NumberOfBytesRead = 0;
    if ( !ReadFile(v14, v20, LowPart, &NumberOfBytesRead, 0) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x2C4,
                    (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\defaultlocalstorage.cpp",
                    v21);
LABEL_26:
      std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&lpBuffer);
      goto LABEL_27;
    }
    if ( LowPart != NumberOfBytesRead )
    {
      LastError = -2147418113;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2C6,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\defaultlocalstorage.cpp",
        (const char *)0x8000FFFFLL,
        lpOverlappeda);
      goto LABEL_26;
    }
    std::string::assign(v30, v20);
    std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(&lpBuffer);
  }
  v23 = (const unsigned __int16 *)v31;
  if ( si128.m128i_i64[1] > 7uLL )
    v23 = v31[0];
  wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
    v33,
    0);
  Windows::Internal::Storage::Cloud::CloudStoreTelemetry::LoadBulkActivity::Stop(
    (Windows::Internal::Storage::Cloud::CloudStoreTelemetry::LoadBulkActivity *)v33,
    v23);
  if ( (unsigned __int64)(v14 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v14);
  if ( si128.m128i_i64[1] > 7uLL )
    std::_Deallocate<16>(v31[0], 2 * si128.m128i_i64[1] + 2);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v31[0]) = 0;
  v33[0] = &Windows::Internal::Storage::Cloud::CloudStoreTelemetry::LoadBulkActivity::`vftable';
  wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(v33);
  wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(v33);
  return v12;
}

```

## disassembly

```asm
0x180052864  mov     [rsp-8+arg_0], rbx
0x180052869  push    rbp
0x18005286a  push    rsi
0x18005286b  push    rdi
0x18005286c  push    r12
0x18005286e  push    r13
0x180052870  push    r14
0x180052872  push    r15
0x180052874  lea     rbp, [rsp-0E0h]
0x18005287c  sub     rsp, 1E0h
0x180052883  mov     rax, cs:__security_cookie
0x18005288a  xor     rax, rsp
0x18005288d  mov     [rbp+110h+var_40], rax
0x180052894  mov     [rsp+210h+var_1C0], r9
0x180052899  mov     r13b, r8b
0x18005289c  mov     rbx, rdx
0x18005289f  lea     rax, aPayload_0; "Payload"
0x1800528a6  lea     r12, aBaseline; "Baseline"
0x1800528ad  test    r8b, r8b
0x1800528b0  cmovz   r12, rax
0x1800528b4  lea     r14, [rdx+80h]
0x1800528bb  cmp     qword ptr [r14+18h], 0Fh
0x1800528c0  jbe     short loc_1800528C5
0x1800528c2  mov     r14, [r14]
0x1800528c5  lea     rdi, [rdx+0A0h]
0x1800528cc  cmp     qword ptr [rdi+18h], 0Fh
0x1800528d1  jbe     short loc_1800528D6
0x1800528d3  mov     rdi, [rdi]
0x1800528d6  lea     rsi, [rdx+40h]
0x1800528da  cmp     qword ptr [rsi+18h], 0Fh
0x1800528df  jbe     short loc_1800528E4
0x1800528e1  mov     rsi, [rsi]
0x1800528e4  cmp     qword ptr [rdx+18h], 0Fh
0x1800528e9  jbe     short loc_1800528F0
0x1800528eb  mov     r15, [rdx]
0x1800528ee  jmp     short loc_1800528F3
0x1800528f0  mov     r15, rbx
0x1800528f3  lea     rdx, aLoadbulkactivi; "LoadBulkActivity"
0x1800528fa  lea     rcx, [rbp+110h+var_190]
0x1800528fe  call    ??0?$ActivityBase@VCloudStoreTelemetry@Cloud@Storage@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180052903  lea     rax, ??_7LoadBulkActivity@CloudStoreTelemetry@Cloud@Storage@Internal@Windows@@6B@; const Windows::Internal::Storage::Cloud::CloudStoreTelemetry::LoadBulkActivity::`vftable'
0x18005290a  mov     [rbp+110h+var_190], rax
0x18005290e  mov     [rsp+210h+var_1E8], r12; char *
0x180052913  mov     [rsp+210h+lpOverlapped], r14; char *
0x180052918  mov     r9, rdi; char *
0x18005291b  mov     r8, rsi; char *
0x18005291e  mov     rdx, r15; char *
0x180052921  lea     rcx, [rbp+110h+var_190]; this
0x180052925  call    ?StartActivity@LoadBulkActivity@CloudStoreTelemetry@Cloud@Storage@Internal@Windows@@QEAAXPEBD0000@Z; Windows::Internal::Storage::Cloud::CloudStoreTelemetry::LoadBulkActivity::StartActivity(char const *,char const *,char const *,char const *,char const *)
0x18005292a  nop
0x18005292b  xorps   xmm0, xmm0
0x18005292e  movups  xmmword ptr [rsp+210h+var_1B8], xmm0
0x180052933  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18005293b  movdqu  [rsp+210h+var_1A8], xmm1
0x180052941  xor     r15d, r15d
0x180052944  mov     word ptr [rsp+210h+var_1B8], r15w
0x18005294a  mov     [rsp+210h+hFile], 0FFFFFFFFFFFFFFFFh
0x180052953  mov     [rsp+210h+var_1E8], rbx
0x180052958  mov     byte ptr [rsp+210h+lpOverlapped], r13b; int
0x18005295d  xor     r9d, r9d
0x180052960  lea     r8, [rsp+210h+hFile]
0x180052965  lea     rdx, [rsp+210h+var_1B8]
0x18005296a  call    ?InitializeFileAndPath@DefaultLocalStorageImpl@Core@Cloud@Storage@Internal@Windows@@AEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@_N2AEBVCloudStoreItemId@23456@@Z; Windows::Internal::Storage::Cloud::Core::DefaultLocalStorageImpl::InitializeFileAndPath(std::wstring &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,bool,bool,Windows::Internal::Storage::Cloud::Core::CloudStoreItemId const &)
0x18005296f  mov     r14d, eax
0x180052972  lea     ecx, [rax+7FF8FFFEh]
0x180052978  lea     eax, [r15+1]
0x18005297c  cmp     ecx, eax
0x18005297e  jbe     short loc_180052985
0x180052980  test    r14d, r14d
0x180052983  jnz     short loc_180052988
0x180052985  mov     al, r15b
0x180052988  mov     rcx, [rbp+118h]; this
0x18005298f  test    al, al
0x180052991  jz      short loc_1800529A8
0x180052993  mov     r9d, r14d; char *
0x180052996  lea     r8, aOnecoreuapShel_105; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x18005299d  mov     edx, 2AFh; void *
0x1800529a2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800529a8  mov     rsi, [rsp+210h+hFile]
0x1800529ad  test    r14d, r14d
0x1800529b0  jnz     loc_180052AF2
0x1800529b6  mov     qword ptr [rsp+210h+FileSize], r15
0x1800529bb  lea     rdx, [rsp+210h+FileSize]; lpFileSize
0x1800529c0  mov     rcx, rsi; hFile
0x1800529c3  call    cs:__imp_GetFileSizeEx
0x1800529c9  test    eax, eax
0x1800529cb  jnz     short loc_1800529EC
0x1800529cd  mov     rcx, [rbp+118h]; this
0x1800529d4  lea     r8, aOnecoreuapShel_105; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1800529db  mov     edx, 2B4h; void *
0x1800529e0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800529e5  mov     ebx, eax
0x1800529e7  jmp     loc_180052AB4
0x1800529ec  mov     eax, 0FFFFFFFFh
0x1800529f1  mov     rbx, qword ptr [rsp+210h+FileSize]
0x1800529f6  cmp     rbx, rax
0x1800529f9  jle     short loc_180052A20
0x1800529fb  mov     rcx, [rbp+118h]; this
0x180052a02  mov     ebx, 800700DFh
0x180052a07  mov     r9d, ebx; char *
0x180052a0a  lea     r8, aOnecoreuapShel_105; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x180052a11  mov     edx, 2B9h; void *
0x180052a16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052a1b  jmp     loc_180052AB4
0x180052a20  lea     eax, [rbx+1]
0x180052a23  mov     edi, eax
0x180052a25  mov     edx, eax
0x180052a27  lea     rcx, [rsp+210h+lpBuffer]
0x180052a2c  call    ??$make_unique@$$BY0A@D$0A@@std@@YA?AV?$unique_ptr@$$BY0A@DU?$default_delete@$$BY0A@D@std@@@0@_K@Z; std::make_unique<char [0],0>(unsigned __int64)
0x180052a31  nop
0x180052a32  mov     r8d, edi; Size
0x180052a35  xor     edx, edx; Val
0x180052a37  mov     rdi, [rsp+210h+lpBuffer]
0x180052a3c  mov     rcx, rdi; void *
0x180052a3f  call    memset_0
0x180052a44  mov     [rsp+210h+NumberOfBytesRead], r15d
0x180052a49  mov     [rsp+210h+lpOverlapped], r15; int
0x180052a4e  lea     r9, [rsp+210h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180052a53  mov     r8d, ebx; nNumberOfBytesToRead
0x180052a56  mov     rdx, rdi; lpBuffer
0x180052a59  mov     rcx, rsi; hFile
0x180052a5c  call    cs:__imp_ReadFile
0x180052a62  test    eax, eax
0x180052a64  jnz     short loc_180052A82
0x180052a66  mov     rcx, [rbp+118h]; this
0x180052a6d  lea     r8, aOnecoreuapShel_105; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x180052a74  mov     edx, 2C4h; void *
0x180052a79  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180052a7e  mov     ebx, eax
0x180052a80  jmp     short loc_180052AA9
0x180052a82  cmp     ebx, [rsp+210h+NumberOfBytesRead]
0x180052a86  jz      short loc_180052ADA
0x180052a88  mov     rcx, [rbp+118h]; this
0x180052a8f  mov     ebx, 8000FFFFh
0x180052a94  mov     r9d, ebx; char *
0x180052a97  lea     r8, aOnecoreuapShel_105; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x180052a9e  mov     edx, 2C6h; void *
0x180052aa3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052aa8  nop
0x180052aa9  lea     rcx, [rsp+210h+lpBuffer]
0x180052aae  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x180052ab3  nop
0x180052ab4  lea     rcx, [rsp+210h+hFile]
0x180052ab9  call    ??1?$pair@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@_N@std@@QEAA@XZ; std::pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,bool>::~pair<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,bool>(void)
0x180052abe  nop
0x180052abf  lea     rcx, [rsp+210h+var_1B8]
0x180052ac4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180052ac9  nop
0x180052aca  lea     rcx, [rbp+110h+var_190]; this
0x180052ace  call    ??1LoadBulkActivity@CloudStoreTelemetry@Cloud@Storage@Internal@Windows@@QEAA@XZ; Windows::Internal::Storage::Cloud::CloudStoreTelemetry::LoadBulkActivity::~LoadBulkActivity(void)
0x180052ad3  mov     eax, ebx
0x180052ad5  jmp     loc_180052B80
0x180052ada  mov     rdx, rdi
0x180052add  mov     rcx, [rsp+210h+var_1C0]
0x180052ae2  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD@Z; std::string::assign(char const * const)
0x180052ae7  nop
0x180052ae8  lea     rcx, [rsp+210h+lpBuffer]
0x180052aed  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x180052af2  lea     rbx, [rsp+210h+var_1B8]
0x180052af7  cmp     qword ptr [rsp+210h+var_1A8+8], 7
0x180052afd  cmova   rbx, [rsp+210h+var_1B8]
0x180052b03  xor     edx, edx
0x180052b05  lea     rcx, [rbp+110h+var_190]
0x180052b09  call    ?SetStopResult@?$ActivityBase@VCloudStoreTelemetry@Cloud@Storage@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXJPEAJ@Z; wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x180052b0e  mov     rdx, rbx; unsigned __int16 *
0x180052b11  lea     rcx, [rbp+110h+var_190]; this
0x180052b15  call    ?Stop@LoadBulkActivity@CloudStoreTelemetry@Cloud@Storage@Internal@Windows@@QEAAXPEBG@Z; Windows::Internal::Storage::Cloud::CloudStoreTelemetry::LoadBulkActivity::Stop(ushort const *)
0x180052b1a  nop
0x180052b1b  lea     rax, [rsi-1]
0x180052b1f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180052b23  ja      short loc_180052B2F
0x180052b25  mov     rcx, rsi; hObject
0x180052b28  call    cs:__imp_CloseHandle
0x180052b2e  nop
0x180052b2f  mov     rdx, qword ptr [rsp+210h+var_1A8+8]
0x180052b34  cmp     rdx, 7
0x180052b38  jbe     short loc_180052B4C
0x180052b3a  lea     rdx, ds:2[rdx*2]
0x180052b42  mov     rcx, [rsp+210h+var_1B8]
0x180052b47  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180052b4c  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x180052b54  movdqu  [rsp+210h+var_1A8], xmm0
0x180052b5a  mov     word ptr [rsp+210h+var_1B8], r15w
0x180052b60  lea     rax, ??_7LoadBulkActivity@CloudStoreTelemetry@Cloud@Storage@Internal@Windows@@6B@; const Windows::Internal::Storage::Cloud::CloudStoreTelemetry::LoadBulkActivity::`vftable'
0x180052b67  mov     [rbp+110h+var_190], rax
0x180052b6b  lea     rcx, [rbp+110h+var_190]
0x180052b6f  call    ?Destroy@?$ActivityBase@VCloudStoreTelemetry@Cloud@Storage@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180052b74  lea     rcx, [rbp+110h+var_190]
0x180052b78  call    ??1?$ActivityBase@VCloudStoreTelemetry@Cloud@Storage@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<Windows::Internal::Storage::Cloud::CloudStoreTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180052b7d  mov     eax, r14d
0x180052b80  mov     rcx, [rbp+110h+var_40]
0x180052b87  xor     rcx, rsp; StackCookie
0x180052b8a  call    __security_check_cookie
0x180052b8f  mov     rbx, [rsp+210h+arg_0]
0x180052b97  add     rsp, 1E0h
0x180052b9e  pop     r15
0x180052ba0  pop     r14
0x180052ba2  pop     r13
0x180052ba4  pop     r12
0x180052ba6  pop     rdi
0x180052ba7  pop     rsi
0x180052ba8  pop     rbp
0x180052ba9  retn
```
