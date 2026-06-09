# CPipeClient::Init(wchar_t const *,wchar_t const *)

- ea: `0x180073820`
- end: `0x180073ca1`
- name: `?Init@CPipeClient@@IEAAXPEB_W0@Z`
- size: `1153`
- prototype: `void(CPipeClient *__hidden this, const wchar_t *, const wchar_t *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180072edc`

## callees

- `0x180038f08`
- `0x180072768`
- `0x180073820`
- `0x1800740f4`
- `0x1800748a4`
- `0x1800a4e0c`
- `0x1800e5cc0`
- `0x1800f0d04`
- `0x180181e28`
- `0x180188d90`
- `0x180189cda`
- `0x18019b924`
- `0x1801b5de8`
- `0x1801f8430`
- `0x1801f851c`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073afc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073b40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073b51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073be6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073afc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073b40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073b51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073be6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180073bff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180073bff`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800739c1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800739c1`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x1800739ea`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x1800739ea`
- `api-ms-win-core-namedpipe-l1-1-0!WaitNamedPipeW` at `0x180073aee`
- `api-ms-win-core-namedpipe-l1-1-0!WaitNamedPipeW` at `0x180073aee`

## string_xrefs

- `0x180073a08`: `onecoreuap\base\appmodel\search\tquery\cicommon\crequest.cxx`
- `0x180073ac5`: `onecoreuap\base\appmodel\search\tquery\cicommon\crequest.cxx`
- `0x180073b7f`: `onecoreuap\base\appmodel\search\tquery\cicommon\crequest.cxx`
- `0x180073b94`: `onecoreuap\base\appmodel\search\tquery\cicommon\crequest.cxx`
- `0x180073ba9`: `onecoreuap\base\appmodel\search\tquery\cicommon\crequest.cxx`
- `0x180073bbe`: `onecoreuap\base\appmodel\search\tquery\cicommon\crequest.cxx`
- `0x180073c13`: `onecoreuap\base\appmodel\search\tquery\cicommon\crequest.cxx`
- `0x180073c32`: `onecoreuap\base\appmodel\search\tquery\cicommon\crequest.cxx`
- `0x180073c51`: `onecoreuap\base\appmodel\search\tquery\cicommon\crequest.cxx`
- `0x180073c70`: `onecoreuap\base\appmodel\search\tquery\cicommon\crequest.cxx`
- `0x180073c8f`: `onecoreuap\base\appmodel\search\tquery\cicommon\crequest.cxx`
- `0x1802ba446`: `onecoreuap\base\appmodel\search\tquery\cicommon\crequest.cxx`
- `0x1802ba462`: `onecoreuap\base\appmodel\search\tquery\cicommon\crequest.cxx`
- `0x1800739fc`: `[Proxy] created pipe %#x\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CPipeClient::Init(CPipeClient *this, const wchar_t *a2, wchar_t *a3)
{
  bool v6; // al
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rdx
  WCHAR *v10; // rax
  __int64 v11; // r8
  __int64 v12; // rcx
  const wchar_t *v13; // rdx
  __int64 v14; // r9
  WCHAR *v15; // rax
  wchar_t v16; // r8
  WCHAR *v17; // rcx
  HANDLE FileW; // rax
  const struct _GUID *v19; // rdx
  const wchar_t *v20; // rcx
  const struct _GUID *v21; // r8
  int InstanceByCrossContainer; // eax
  int v23; // eax
  unsigned int v24; // edx
  int ContainerIdInContainer; // eax
  unsigned int v26; // r8d
  int QueryPipeNameForContainer; // eax
  DWORD TimeoutWithDefault; // eax
  DWORD LastError; // eax
  bool v30; // al
  DWORD v31; // eax
  bool v32; // al
  signed int v33; // eax
  unsigned int v34; // ebx
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  DWORD Mode[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR FileName[264]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t pExceptionObject[264]; // [rsp+260h] [rbp+160h] BYREF
  wchar_t v39[264]; // [rsp+470h] [rbp+370h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+6C8h] [rbp+5C8h]

  *(_OWORD *)((char *)this + 24) = 0;
  *(_OWORD *)((char *)this + 40) = 0;
  *(_OWORD *)((char *)this + 56) = 0;
  *(_OWORD *)((char *)this + 72) = 0;
  *((_DWORD *)this + 4) = *a2 != 46;
  v6 = IsRunningInContainer();
  *((_BYTE *)this + 112) = v6;
  if ( !*((_DWORD *)this + 4) && v6 )
  {
    *(_QWORD *)Mode = 0;
    Microsoft::WRL::ComPtr<IGathererBackOff>::InternalRelease(Mode);
    InstanceByCrossContainer = CoCreateInstanceByCrossContainer(v20, v19, v21, (void **)Mode);
    if ( InstanceByCrossContainer < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9E,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cicommon\\crequest.cxx",
        (const char *)(unsigned int)InstanceByCrossContainer,
        dwCreationDisposition);
    v23 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)Mode + 24LL))(*(_QWORD *)Mode);
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA0,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cicommon\\crequest.cxx",
        (const char *)(unsigned int)v23,
        dwCreationDisposition);
    ContainerIdInContainer = GetContainerIdInContainer(pExceptionObject, v24);
    if ( ContainerIdInContainer < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA3,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cicommon\\crequest.cxx",
        (const char *)(unsigned int)ContainerIdInContainer,
        dwCreationDisposition);
    QueryPipeNameForContainer = GetQueryPipeNameForContainer(pExceptionObject, v39, v26);
    if ( QueryPipeNameForContainer < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA5,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cicommon\\crequest.cxx",
        (const char *)(unsigned int)QueryPipeNameForContainer,
        dwCreationDisposition);
    a3 = v39;
    Microsoft::WRL::ComPtr<IGathererBackOff>::InternalRelease(Mode);
  }
  v7 = -1;
  do
    ++v7;
  while ( a2[v7] );
  v8 = -1;
  do
    ++v8;
  while ( a3[v8] );
  if ( (unsigned int)(v8 + v7 + 20) >= 0x104 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xAF,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cicommon\\crequest.cxx",
      (const char *)0x80070057LL,
      dwCreationDisposition);
  wcscpy(FileName, L"\\\\");
  if ( StringCchCatW(FileName, 0x104u, a2) < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB4,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cicommon\\crequest.cxx",
      (const char *)0x80070057LL,
      dwCreationDisposition);
  v9 = 260;
  v10 = FileName;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v9;
  }
  while ( v9 );
  v11 = (260 - v9) & -(__int64)(v9 != 0);
  if ( !v9 )
    goto LABEL_46;
  v12 = 2147483646;
  v13 = L"\\pipe\\";
  v14 = 260 - v11;
  v15 = &FileName[v11];
  if ( v11 != 260 )
  {
    do
    {
      if ( !v12 )
        break;
      v16 = *v13;
      if ( !*v13 )
        break;
      ++v13;
      *v15++ = v16;
      --v12;
      --v14;
    }
    while ( v14 );
  }
  v17 = v15 - 1;
  if ( v14 )
    v17 = v15;
  *v17 = 0;
  if ( !v14 )
LABEL_46:
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB7,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cicommon\\crequest.cxx",
      (const char *)0x80070057LL,
      dwCreationDisposition);
  if ( StringCchCatW(FileName, 0x104u, a3) < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBA,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cicommon\\crequest.cxx",
      (const char *)0x80070057LL,
      dwCreationDisposition);
  while ( 1 )
  {
    if ( !*((_BYTE *)this + 112) )
    {
      TimeoutWithDefault = CPipeClient::GetTimeoutWithDefault(this, 0, 0, 0);
      if ( !WaitNamedPipeW(FileName, TimeoutWithDefault) )
      {
        LastError = GetLastError();
        if ( LastError == 2 )
        {
          v30 = IsDeviceUnderDPL();
          wil::ResultException::ResultException(
            (wil::ResultException *)pExceptionObject,
            v30 ? -2147024540 : -2147215328);
          throw (wil::ResultException *)pExceptionObject;
        }
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0xD9,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cicommon\\crequest.cxx",
          (const char *)LastError,
          dwCreationDisposition);
      }
    }
    FileW = CreateFileW(FileName, 0xC0000000, 3u, 0, 3u, 0x40000080u, 0);
    *((_QWORD *)this + 1) = FileW;
    if ( FileW != (HANDLE)-1LL )
      break;
    if ( GetLastError() != 231 )
    {
      v31 = GetLastError();
      if ( v31 == 2 )
      {
        v32 = IsDeviceUnderDPL();
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xFF,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cicommon\\crequest.cxx",
          (const char *)(v32 ? -2147024540 : -2147215328),
          dwCreationDisposition);
      }
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x103,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cicommon\\crequest.cxx",
        (const char *)v31,
        dwCreationDisposition);
    }
  }
  Mode[0] = 2;
  if ( !SetNamedPipeHandleState(FileW, Mode, 0, 0) )
  {
    v33 = GetLastError();
    v34 = v33;
    if ( v33 > 0 )
      v34 = (unsigned __int16)v33 | 0x80070000;
    CloseHandle(*((HANDLE *)this + 1));
    *((_QWORD *)this + 1) = -1;
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xF6,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cicommon\\crequest.cxx",
      (const char *)v34,
      dwCreationDisposition);
  }
  SearchIndexerDebug::Verbose(
    (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\cicommon\\crequest.cxx",
    (const wchar_t *)0x108,
    (unsigned int)L"[Proxy] created pipe %#x\n",
    *((const wchar_t **)this + 1));
}

```

## disassembly

```asm
0x180073820  push    rbp
0x180073822  push    rbx
0x180073823  push    rsi
0x180073824  push    rdi
0x180073825  push    r12
0x180073827  push    r14
0x180073829  push    r15
0x18007382b  lea     rbp, [rsp-590h]
0x180073833  sub     rsp, 690h
0x18007383a  mov     rax, cs:__security_cookie
0x180073841  xor     rax, rsp
0x180073844  mov     [rbp+5C0h+var_40], rax
0x18007384b  mov     rbx, r8
0x18007384e  mov     rsi, rdx
0x180073851  mov     rdi, rcx
0x180073854  xorps   xmm0, xmm0
0x180073857  movups  xmmword ptr [rcx+18h], xmm0
0x18007385b  movups  xmmword ptr [rcx+28h], xmm0
0x18007385f  xorps   xmm1, xmm1
0x180073862  movups  xmmword ptr [rcx+38h], xmm1
0x180073866  movups  xmmword ptr [rcx+48h], xmm1
0x18007386a  mov     ecx, 2Eh ; '.'
0x18007386f  xor     r14d, r14d
0x180073872  mov     eax, r14d
0x180073875  cmp     cx, [rdx]
0x180073878  setnz   al
0x18007387b  mov     [rdi+10h], eax
0x18007387e  call    ?IsRunningInContainer@@YA_NXZ; IsRunningInContainer(void)
0x180073883  mov     [rdi+70h], al
0x180073886  cmp     [rdi+10h], r14d
0x18007388a  jz      loc_180073A35
0x180073890  or      r12, 0FFFFFFFFFFFFFFFFh
0x180073894  mov     rax, r12
0x180073897  inc     rax
0x18007389a  cmp     [rsi+rax*2], r14w
0x18007389f  jnz     short loc_180073897
0x1800738a1  mov     rcx, r12
0x1800738a4  inc     rcx
0x1800738a7  cmp     [rbx+rcx*2], r14w
0x1800738ac  jnz     short loc_1800738A4
0x1800738ae  add     eax, 14h
0x1800738b1  add     eax, ecx
0x1800738b3  mov     r15d, 104h
0x1800738b9  cmp     eax, r15d
0x1800738bc  jnb     loc_180073C25
0x1800738c2  mov     eax, dword ptr cs:asc_1802E96D8; "\\\\"
0x1800738c8  mov     dword ptr [rsp+6C0h+FileName], eax
0x1800738cc  movzx   eax, word ptr cs:asc_1802E96D8+4; ""
0x1800738d3  mov     [rsp+6C0h+var_66C], ax
0x1800738d8  mov     r8, rsi; wchar_t *
0x1800738db  mov     edx, r15d; unsigned __int64
0x1800738de  lea     rcx, [rsp+6C0h+FileName]; wchar_t *
0x1800738e3  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800738e8  test    eax, eax
0x1800738ea  js      loc_180073C44
0x1800738f0  mov     edx, r15d
0x1800738f3  lea     rax, [rsp+6C0h+FileName]
0x1800738f8  cmp     [rax], r14w
0x1800738fc  jz      short loc_180073908
0x1800738fe  add     rax, 2
0x180073902  sub     rdx, 1
0x180073906  jnz     short loc_1800738F8
0x180073908  mov     rax, rdx
0x18007390b  mov     rcx, r15
0x18007390e  sub     rcx, rdx
0x180073911  neg     rax
0x180073914  sbb     r8, r8
0x180073917  and     r8, rcx
0x18007391a  test    rdx, rdx
0x18007391d  jz      loc_180073C82
0x180073923  mov     ecx, 7FFFFFFEh
0x180073928  lea     rdx, aPipe; "\\pipe\\"
0x18007392f  mov     r9, r15
0x180073932  sub     r9, r8
0x180073935  lea     rax, [rsp+6C0h+FileName]
0x18007393a  lea     rax, [rax+r8*2]
0x18007393e  jz      short loc_180073964
0x180073940  test    rcx, rcx
0x180073943  jz      short loc_180073964
0x180073945  movzx   r8d, word ptr [rdx]
0x180073949  test    r8w, r8w
0x18007394d  jz      short loc_180073964
0x18007394f  add     rdx, 2
0x180073953  mov     [rax], r8w
0x180073957  add     rax, 2
0x18007395b  dec     rcx
0x18007395e  sub     r9, 1
0x180073962  jnz     short loc_180073940
0x180073964  lea     rcx, [rax-2]
0x180073968  test    r9, r9
0x18007396b  cmovnz  rcx, rax
0x18007396f  mov     [rcx], r14w
0x180073973  jz      loc_180073C82
0x180073979  mov     r8, rbx; wchar_t *
0x18007397c  mov     rdx, r15; unsigned __int64
0x18007397f  lea     rcx, [rsp+6C0h+FileName]; wchar_t *
0x180073984  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180073989  test    eax, eax
0x18007398b  js      loc_180073C63
0x180073991  mov     ebx, 3
0x180073996  cmp     [rdi+70h], r14b
0x18007399a  jz      loc_180073AD7
0x1800739a0  mov     [rsp+6C0h+hTemplateFile], r14; hTemplateFile
0x1800739a5  mov     [rsp+6C0h+dwFlagsAndAttributes], 40000080h; dwFlagsAndAttributes
0x1800739ad  mov     [rsp+6C0h+dwCreationDisposition], ebx; unsigned int
0x1800739b1  xor     r9d, r9d; lpSecurityAttributes
0x1800739b4  mov     r8d, ebx; dwShareMode
0x1800739b7  mov     edx, 0C0000000h; dwDesiredAccess
0x1800739bc  lea     rcx, [rsp+6C0h+FileName]; lpFileName
0x1800739c1  call    cs:__imp_CreateFileW
0x1800739c7  mov     [rdi+8], rax
0x1800739cb  cmp     rax, r12
0x1800739ce  jz      loc_180073B40
0x1800739d4  mov     [rsp+6C0h+Mode], 2
0x1800739dc  xor     r9d, r9d; lpCollectDataTimeout
0x1800739df  xor     r8d, r8d; lpMaxCollectionCount
0x1800739e2  lea     rdx, [rsp+6C0h+Mode]; lpMode
0x1800739e7  mov     rcx, rax; hNamedPipe
0x1800739ea  call    cs:__imp_SetNamedPipeHandleState
0x1800739f0  test    eax, eax
0x1800739f2  jz      loc_180073BE6
0x1800739f8  mov     r9, [rdi+8]; wchar_t *
0x1800739fc  lea     r8, aProxyCreatedPi; "[Proxy] created pipe %#x\n"
0x180073a03  mov     edx, 108h; wchar_t *
0x180073a08  lea     rcx, aOnecoreuapBase_173; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180073a0f  call    ?Verbose@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x180073a14  mov     rcx, [rbp+5C0h+var_40]
0x180073a1b  xor     rcx, rsp; StackCookie
0x180073a1e  call    __security_check_cookie
0x180073a23  add     rsp, 690h
0x180073a2a  pop     r15
0x180073a2c  pop     r14
0x180073a2e  pop     r12
0x180073a30  pop     rdi
0x180073a31  pop     rsi
0x180073a32  pop     rbx
0x180073a33  pop     rbp
0x180073a34  retn
0x180073a35  test    al, al
0x180073a37  jz      loc_180073890
0x180073a3d  mov     qword ptr [rsp+6C0h+Mode], r14
0x180073a42  lea     rcx, [rsp+6C0h+Mode]
0x180073a47  call    ?InternalRelease@?$ComPtr@UIGathererBackOff@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IGathererBackOff>::InternalRelease(void)
0x180073a4c  lea     r9, [rsp+6C0h+Mode]; void **
0x180073a51  call    ?CoCreateInstanceByCrossContainer@@YAJPEB_WAEBU_GUID@@1PEAPEAX@Z; CoCreateInstanceByCrossContainer(wchar_t const *,_GUID const &,_GUID const &,void * *)
0x180073a56  mov     rcx, [rbp+5C8h]; this
0x180073a5d  test    eax, eax
0x180073a5f  js      loc_180073B91
0x180073a65  mov     rcx, qword ptr [rsp+6C0h+Mode]
0x180073a6a  mov     rax, [rcx]
0x180073a6d  mov     rax, [rax+18h]
0x180073a71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073a76  mov     rcx, [rbp+5C8h]; this
0x180073a7d  test    eax, eax
0x180073a7f  js      loc_180073BA6
0x180073a85  lea     rcx, [rbp+5C0h+pExceptionObject]; pvData
0x180073a8c  call    ?GetContainerIdInContainer@@YAJPEA_WK@Z; GetContainerIdInContainer(wchar_t *,ulong)
0x180073a91  mov     rcx, [rbp+5C8h]; this
0x180073a98  test    eax, eax
0x180073a9a  js      loc_180073BBB
0x180073aa0  lea     rdx, [rbp+5C0h+var_250]; wchar_t *
0x180073aa7  lea     rcx, [rbp+5C0h+pExceptionObject]; wchar_t *
0x180073aae  call    ?GetQueryPipeNameForContainer@@YAJPEB_WPEA_WK@Z; GetQueryPipeNameForContainer(wchar_t const *,wchar_t *,ulong)
0x180073ab3  mov     rcx, [rbp+5C8h]; this
0x180073aba  test    eax, eax
0x180073abc  jns     loc_180073BD0
0x180073ac2  mov     r9d, eax; char *
0x180073ac5  lea     r8, aOnecoreuapBase_66; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180073acc  mov     edx, 0A5h; void *
0x180073ad1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180073ad7  xor     r9d, r9d; unsigned int *
0x180073ada  xor     r8d, r8d; struct _OVERLAPPED *
0x180073add  xor     edx, edx; unsigned int
0x180073adf  mov     rcx, rdi; this
0x180073ae2  call    ?GetTimeoutWithDefault@CPipeClient@@AEAAKKPEAU_OVERLAPPED@@PEAK@Z; CPipeClient::GetTimeoutWithDefault(ulong,_OVERLAPPED *,ulong *)
0x180073ae7  mov     edx, eax; nTimeOut
0x180073ae9  lea     rcx, [rsp+6C0h+FileName]; lpNamedPipeName
0x180073aee  call    cs:__imp_WaitNamedPipeW
0x180073af4  test    eax, eax
0x180073af6  jnz     loc_1800739A0
0x180073afc  call    cs:__imp_GetLastError
0x180073b02  cmp     eax, 2
0x180073b05  jnz     loc_1802BA43C
0x180073b0b  call    ?IsDeviceUnderDPL@@YA_NXZ; IsDeviceUnderDPL(void)
0x180073b10  neg     al
0x180073b12  sbb     edx, edx
0x180073b14  and     edx, 2E944h
0x180073b1a  add     edx, 80041820h; int
0x180073b20  lea     rcx, [rbp+5C0h+pExceptionObject]; this
0x180073b27  call    ??0ResultException@wil@@QEAA@J@Z; wil::ResultException::ResultException(long)
0x180073b2c  lea     rdx, _TI2?AVResultException@wil@@; pThrowInfo
0x180073b33  lea     rcx, [rbp+5C0h+pExceptionObject]; pExceptionObject
0x180073b3a  call    _CxxThrowException_0
0x180073b40  call    cs:__imp_GetLastError
0x180073b46  cmp     eax, 0E7h
0x180073b4b  jz      loc_180073996
0x180073b51  call    cs:__imp_GetLastError
0x180073b57  cmp     eax, 2
0x180073b5a  jnz     loc_1802BA458
0x180073b60  call    ?IsDeviceUnderDPL@@YA_NXZ; IsDeviceUnderDPL(void)
0x180073b65  neg     al
0x180073b67  sbb     r9d, r9d
0x180073b6a  and     r9d, 2E944h
0x180073b71  add     r9d, 80041820h; char *
0x180073b78  mov     rcx, [rbp+5C8h]; this
0x180073b7f  lea     r8, aOnecoreuapBase_66; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180073b86  mov     edx, 0FFh; void *
0x180073b8b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180073b91  mov     r9d, eax; char *
0x180073b94  lea     r8, aOnecoreuapBase_66; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180073b9b  mov     edx, 9Eh; void *
0x180073ba0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180073ba6  mov     r9d, eax; char *
0x180073ba9  lea     r8, aOnecoreuapBase_66; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180073bb0  mov     edx, 0A0h; void *
0x180073bb5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180073bbb  mov     r9d, eax; char *
0x180073bbe  lea     r8, aOnecoreuapBase_66; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180073bc5  mov     edx, 0A3h; void *
0x180073bca  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180073bd0  lea     rbx, [rbp+5C0h+var_250]
0x180073bd7  lea     rcx, [rsp+6C0h+Mode]
0x180073bdc  call    ?InternalRelease@?$ComPtr@UIGathererBackOff@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IGathererBackOff>::InternalRelease(void)
0x180073be1  jmp     loc_180073890
0x180073be6  call    cs:__imp_GetLastError
0x180073bec  mov     ebx, eax
0x180073bee  test    eax, eax
0x180073bf0  jle     short loc_180073BFB
0x180073bf2  movzx   ebx, ax
0x180073bf5  or      ebx, 80070000h
0x180073bfb  mov     rcx, [rdi+8]; hObject
0x180073bff  call    cs:__imp_CloseHandle
0x180073c05  mov     [rdi+8], r12
0x180073c09  mov     rcx, [rbp+5C8h]; this
0x180073c10  mov     r9d, ebx; char *
0x180073c13  lea     r8, aOnecoreuapBase_66; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180073c1a  mov     edx, 0F6h; void *
0x180073c1f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180073c25  mov     rcx, [rbp+5C8h]; this
0x180073c2c  mov     r9d, 80070057h; char *
0x180073c32  lea     r8, aOnecoreuapBase_66; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180073c39  mov     edx, 0AFh; void *
0x180073c3e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180073c44  mov     rcx, [rbp+5C8h]; this
0x180073c4b  mov     r9d, 80070057h; char *
0x180073c51  lea     r8, aOnecoreuapBase_66; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180073c58  mov     edx, 0B4h; void *
0x180073c5d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180073c63  mov     rcx, [rbp+5C8h]; this
0x180073c6a  mov     r9d, 80070057h; char *
0x180073c70  lea     r8, aOnecoreuapBase_66; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180073c77  mov     edx, 0BAh; void *
0x180073c7c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180073c82  mov     rcx, [rbp+5C8h]; this
0x180073c89  mov     r9d, 80070057h; char *
0x180073c8f  lea     r8, aOnecoreuapBase_66; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180073c96  mov     edx, 0B7h; void *
0x180073c9b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802ba43c  mov     rcx, [rbp+5C8h]; this
0x1802ba443  mov     r9d, eax; char *
0x1802ba446  lea     r8, aOnecoreuapBase_66; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1802ba44d  mov     edx, 0D9h; void *
0x1802ba452  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1802ba458  mov     rcx, [rbp+5C8h]; this
0x1802ba45f  mov     r9d, eax; char *
0x1802ba462  lea     r8, aOnecoreuapBase_66; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1802ba469  mov     edx, 103h; void *
0x1802ba46e  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
