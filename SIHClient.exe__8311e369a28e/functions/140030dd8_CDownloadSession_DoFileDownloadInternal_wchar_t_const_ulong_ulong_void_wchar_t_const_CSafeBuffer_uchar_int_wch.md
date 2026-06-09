# CDownloadSession::DoFileDownloadInternal(wchar_t const *,ulong,ulong,void *,wchar_t const *,CSafeBuffer<uchar> *,int *,wchar_t const *,ulong)

- ea: `0x140030dd8`
- end: `0x140031156`
- name: `?DoFileDownloadInternal@CDownloadSession@@AEAAJPEB_WKKPEAX0PEAV?$CSafeBuffer@E@@PEAH0K@Z`
- size: `894`
- prototype: `__int64 __fastcall(wchar_t **this, const wchar_t *, __int64, unsigned int, int, wchar_t *, int, _DWORD *, wchar_t *, unsigned int)`
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140030b54`

## callees

- `0x140003de4`
- `0x140008de4`
- `0x14000ce30`
- `0x140011444`
- `0x1400154b4`
- `0x1400177e0`
- `0x140030dd8`
- `0x14003115c`
- `0x1400318f8`
- `0x140031afc`
- `0x140031bd4`
- `0x140031d1c`
- `0x1400320b4`
- `0x140032268`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140031042`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x140031042`
- `WINHTTP!WinHttpCloseHandle` at `0x140030f6e`
- `WINHTTP!WinHttpCloseHandle` at `0x140030f6e`

## string_xrefs

- `0x140030e64`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`

## pseudocode

```c
__int64 __fastcall CDownloadSession::DoFileDownloadInternal(
        wchar_t **this,
        const wchar_t *a2,
        __int64 a3,
        unsigned int a4,
        int a5,
        wchar_t *a6,
        int a7,
        _DWORD *a8,
        wchar_t *a9,
        unsigned int a10)
{
  unsigned int v13; // r8d
  int Request; // ebx
  void *v15; // r8
  int v16; // eax
  void *v17; // rdx
  int IsFileToBeDownloaded; // eax
  wchar_t *v19; // rcx
  void **v20; // rbx
  wchar_t *v21; // rcx
  int StringHeaderValueWorker; // eax
  void *v23; // rdx
  int v24; // eax
  unsigned int lpString2; // [rsp+20h] [rbp-68h]
  PCNZWCH lpString2a; // [rsp+20h] [rbp-68h]
  const wchar_t *cchCount2; // [rsp+28h] [rbp-60h]
  int v29; // [rsp+40h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( a8 )
    *a8 = 0;
  if ( a2 && *a2 && a6 )
  {
    if ( (unsigned int)AreTestKeysAllowed() )
    {
      v29 = 0;
      if ( (int)RegQueryDwordValue(
                  -2147483646,
                  L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
                  L"DownloadSessionErrorOverride",
                  &v29) >= 0 )
        return (unsigned int)v29;
    }
    Request = CDownloadSession::Initialize((CDownloadSession *)this, a2, v13, a4);
    if ( Request < 0 )
      return (unsigned int)Request;
    v29 = 1;
    v16 = CDownloadSession::SendRequestToServerForFileInformation((CDownloadSession *)this, a2, v15, a9, lpString2, a10);
    Request = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x34A,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\DownloadFile\\DownloadSession.cpp",
        (const char *)(unsigned int)v16,
        (int)lpString2a);
      return (unsigned int)Request;
    }
    IsFileToBeDownloaded = CDownloadSession::IsFileToBeDownloaded((CDownloadSession *)this, v17, a6, &v29);
    Request = IsFileToBeDownloaded;
    if ( IsFileToBeDownloaded < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x34B,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\DownloadFile\\DownloadSession.cpp",
        (const char *)(unsigned int)IsFileToBeDownloaded,
        (int)lpString2a);
    if ( Request < 0 )
      return (unsigned int)Request;
    if ( v29 )
    {
      if ( *((_DWORD *)this + 6) == 1 && (*((_DWORD *)this + 48) != 304 || !*((_DWORD *)this + 55)) )
        goto LABEL_25;
      v19 = this[2];
      if ( v19 )
        WinHttpCloseHandle(v19);
      HIDWORD(lpString2a) = 0;
      this[2] = 0;
      *((_DWORD *)this + 6) = 2;
      Request = CDownloadSession::MakeRequest(this, a2, 1);
      if ( Request >= 0 )
      {
LABEL_25:
        CDownloadSession::CacheServerFileTime((CDownloadSession *)this);
        v20 = (void **)(this + 26);
        v21 = this[26];
        if ( v21 )
          SusFree(v21);
        *v20 = 0;
        StringHeaderValueWorker = CDownloadSession::GetStringHeaderValueWorker(
                                    (CDownloadSession *)this,
                                    1u,
                                    0,
                                    this + 26);
        *((_DWORD *)this + 54) = StringHeaderValueWorker;
        if ( StringHeaderValueWorker < 0 )
        {
          if ( *v20 )
            SusFree(*v20);
          *v20 = 0;
        }
        if ( *((_DWORD *)this + 42) )
        {
          if ( *((int *)this + 54) >= 0 && *v20 )
          {
            if ( CompareStringW(0x7Fu, 1u, (PCNZWCH)*v20, -1, L"text/html", -1) == 2
              || (unsigned int)WUStringStartsWithI(this[26], L"text/html;") )
            {
              Request = -2145124296;
              cchCount2 = L"WinHttp: Content-Type header is text/html (Bailing)";
              LODWORD(lpString2a) = -2145124296;
              goto LABEL_17;
            }
            WUTrace(0, 0, 32, 5, 0, L"WinHttp: Content-Type header is %ls.  Continuing.");
          }
          else
          {
            LODWORD(lpString2a) = *((_DWORD *)this + 54);
            WUTrace(0, 0, 32, 5, lpString2a, L"WinHttp: Failed to get the content type");
          }
        }
        v24 = CDownloadSession::PerformDownloadToFile((CDownloadSession *)this, v23, a6);
        Request = v24;
        if ( v24 >= 0 )
        {
          WUTrace(0, 0, 32, 5, 0, L"WinHttp: Successfully downloaded %ls");
          if ( a8 )
            *a8 = 1;
        }
        else
        {
          LODWORD(lpString2a) = v24;
          WUTrace(0, 0, 32, 5, lpString2a, L"WinHttp: DoFileDownload PerformDownload");
        }
        return (unsigned int)Request;
      }
      cchCount2 = L"WinHttp: DoFileDownload MakeRequest";
      LODWORD(lpString2a) = Request;
    }
    else
    {
      Request = 0;
      cchCount2 = L"WinHttp: Server file is not newer. Skipping download.";
      lpString2a = 0;
    }
LABEL_17:
    WUTrace(0, 0, 32, 5, lpString2a, cchCount2);
    return (unsigned int)Request;
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x140030dd8  mov     [rsp+arg_10], rbx
0x140030ddd  push    rbp
0x140030dde  push    rsi
0x140030ddf  push    rdi
0x140030de0  push    r12
0x140030de2  push    r13
0x140030de4  push    r14
0x140030de6  push    r15
0x140030de8  sub     rsp, 50h
0x140030dec  mov     rax, cs:__security_cookie
0x140030df3  xor     rax, rsp
0x140030df6  mov     [rsp+88h+var_40], rax
0x140030dfb  mov     r15, [rsp+88h+arg_38]
0x140030e03  xor     r13d, r13d
0x140030e06  mov     r12, [rsp+88h+arg_28]
0x140030e0e  mov     ebx, r9d
0x140030e11  mov     rsi, [rsp+88h+arg_40]
0x140030e19  mov     r14, rdx
0x140030e1c  mov     rdi, rcx
0x140030e1f  test    r15, r15
0x140030e22  jz      short loc_140030E27
0x140030e24  mov     [r15], r13d
0x140030e27  test    r14, r14
0x140030e2a  jz      loc_14003112C
0x140030e30  cmp     [rdx], r13w
0x140030e34  jz      loc_14003112C
0x140030e3a  test    r12, r12
0x140030e3d  jz      loc_14003112C
0x140030e43  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x140030e48  test    eax, eax
0x140030e4a  jz      short loc_140030E7D
0x140030e4c  lea     r9, [rsp+88h+var_48]
0x140030e51  mov     [rsp+88h+var_48], r13d
0x140030e56  lea     r8, ?c_downloadSessionErrorOverride@@3QB_WB; "DownloadSessionErrorOverride"
0x140030e5d  mov     rcx, 0FFFFFFFF80000002h
0x140030e64  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140030e6b  call    ?RegQueryDwordValue@@YAJPEAUHKEY__@@PEB_W1PEAKW4RegistryHiveType@@@Z; RegQueryDwordValue(HKEY__ *,wchar_t const *,wchar_t const *,ulong *,RegistryHiveType)
0x140030e70  test    eax, eax
0x140030e72  js      short loc_140030E7D
0x140030e74  mov     ebx, [rsp+88h+var_48]
0x140030e78  jmp     loc_140031128
0x140030e7d  mov     r9d, ebx; unsigned int
0x140030e80  mov     rdx, r14; wchar_t *
0x140030e83  mov     rcx, rdi; this
0x140030e86  call    ?Initialize@CDownloadSession@@AEAAJPEB_WKK@Z; CDownloadSession::Initialize(wchar_t const *,ulong,ulong)
0x140030e8b  mov     ebx, eax
0x140030e8d  test    eax, eax
0x140030e8f  js      loc_140031128
0x140030e95  mov     eax, [rsp+88h+arg_48]
0x140030e9c  mov     ebp, 1
0x140030ea1  mov     r9, rsi; wchar_t *
0x140030ea4  mov     [rsp+88h+var_48], ebp
0x140030ea8  mov     rdx, r14; wchar_t *
0x140030eab  mov     [rsp+88h+cchCount2], eax; unsigned int
0x140030eaf  mov     rcx, rdi; this
0x140030eb2  call    ?SendRequestToServerForFileInformation@CDownloadSession@@AEAAJPEB_WPEAX0KK@Z; CDownloadSession::SendRequestToServerForFileInformation(wchar_t const *,void *,wchar_t const *,ulong,ulong)
0x140030eb7  mov     ebx, eax
0x140030eb9  test    eax, eax
0x140030ebb  jns     short loc_140030EDE
0x140030ebd  mov     rcx, [rsp+88h]; this
0x140030ec5  lea     r8, aCW1SSrcClientL_24; "C:\\__w\\1\\s\\src\\Client\\lib\\Downlo"...
0x140030ecc  mov     r9d, eax; char *
0x140030ecf  mov     edx, 34Ah; void *
0x140030ed4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140030ed9  jmp     loc_140031128
0x140030ede  lea     r9, [rsp+88h+var_48]; int *
0x140030ee3  mov     r8, r12; wchar_t *
0x140030ee6  mov     rcx, rdi; this
0x140030ee9  call    ?IsFileToBeDownloaded@CDownloadSession@@AEAAJPEAXPEB_WPEAH@Z; CDownloadSession::IsFileToBeDownloaded(void *,wchar_t const *,int *)
0x140030eee  mov     ebx, eax
0x140030ef0  test    eax, eax
0x140030ef2  jns     short loc_140030F10
0x140030ef4  mov     rcx, [rsp+88h]; this
0x140030efc  lea     r8, aCW1SSrcClientL_24; "C:\\__w\\1\\s\\src\\Client\\lib\\Downlo"...
0x140030f03  mov     r9d, eax; char *
0x140030f06  mov     edx, 34Bh; void *
0x140030f0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140030f10  test    ebx, ebx
0x140030f12  js      loc_140031128
0x140030f18  cmp     [rsp+88h+var_48], r13d
0x140030f1d  jnz     short loc_140030F4B
0x140030f1f  lea     rax, aWinhttpServerF; "WinHttp: Server file is not newer. Skip"...
0x140030f26  mov     ebx, r13d
0x140030f29  mov     qword ptr [rsp+88h+cchCount2], rax
0x140030f2e  mov     [rsp+88h+lpString2], r13
0x140030f33  mov     r9d, 5
0x140030f39  lea     r8d, [r9+1Bh]
0x140030f3d  xor     edx, edx
0x140030f3f  xor     ecx, ecx
0x140030f41  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140030f46  jmp     loc_140031128
0x140030f4b  cmp     [rdi+18h], ebp
0x140030f4e  jnz     short loc_140030F65
0x140030f50  cmp     dword ptr [rdi+0C0h], 130h
0x140030f5a  jnz     short loc_140030FAF
0x140030f5c  cmp     [rdi+0DCh], r13d
0x140030f63  jz      short loc_140030FAF
0x140030f65  mov     rcx, [rdi+10h]; hInternet
0x140030f69  test    rcx, rcx
0x140030f6c  jz      short loc_140030F74
0x140030f6e  call    cs:__imp_WinHttpCloseHandle
0x140030f74  mov     [rsp+88h+cchCount2], r13d
0x140030f79  mov     r8d, ebp
0x140030f7c  mov     rdx, r14
0x140030f7f  mov     [rsp+88h+lpString2], r13
0x140030f84  mov     rcx, rdi
0x140030f87  mov     [rdi+10h], r13
0x140030f8b  mov     dword ptr [rdi+18h], 2
0x140030f92  call    ?MakeRequest@CDownloadSession@@AEAAJPEB_WW4WinHttpRequestVerbType@@PEAX0K@Z; CDownloadSession::MakeRequest(wchar_t const *,WinHttpRequestVerbType,void *,wchar_t const *,ulong)
0x140030f97  mov     ebx, eax
0x140030f99  test    eax, eax
0x140030f9b  jns     short loc_140030FAF
0x140030f9d  lea     rax, aWinhttpDofiled; "WinHttp: DoFileDownload MakeRequest"
0x140030fa4  mov     qword ptr [rsp+88h+cchCount2], rax
0x140030fa9  mov     dword ptr [rsp+88h+lpString2], ebx
0x140030fad  jmp     short loc_140030F33
0x140030faf  mov     rcx, rdi; this
0x140030fb2  call    ?CacheServerFileTime@CDownloadSession@@AEAAXXZ; CDownloadSession::CacheServerFileTime(void)
0x140030fb7  lea     rbx, [rdi+0D0h]
0x140030fbe  mov     rcx, [rbx]; lpMem
0x140030fc1  test    rcx, rcx
0x140030fc4  jz      short loc_140030FCB
0x140030fc6  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140030fcb  mov     r9, rbx; wchar_t **
0x140030fce  mov     [rbx], r13
0x140030fd1  xor     r8d, r8d; wchar_t *
0x140030fd4  mov     edx, ebp; unsigned int
0x140030fd6  mov     rcx, rdi; this
0x140030fd9  call    ?GetStringHeaderValueWorker@CDownloadSession@@AEAAJKPEB_WPEAPEA_W@Z; CDownloadSession::GetStringHeaderValueWorker(ulong,wchar_t const *,wchar_t * *)
0x140030fde  mov     [rdi+0D8h], eax
0x140030fe4  test    eax, eax
0x140030fe6  jns     short loc_140030FF8
0x140030fe8  mov     rcx, [rbx]; lpMem
0x140030feb  test    rcx, rcx
0x140030fee  jz      short loc_140030FF5
0x140030ff0  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140030ff5  mov     [rbx], r13
0x140030ff8  mov     esi, 5
0x140030ffd  lea     ebp, [rsi+1Bh]
0x140031000  cmp     [rdi+0A8h], r13d
0x140031007  jz      loc_1400310D1
0x14003100d  mov     eax, [rdi+0D8h]
0x140031013  test    eax, eax
0x140031015  js      loc_1400310B2
0x14003101b  mov     r8, [rbx]; lpString1
0x14003101e  test    r8, r8
0x140031021  jz      loc_1400310B2
0x140031027  or      r9d, 0FFFFFFFFh; cchCount1
0x14003102b  lea     rax, String2; "text/html"
0x140031032  mov     [rsp+88h+cchCount2], r9d; cchCount2
0x140031037  lea     edx, [rsi-4]; dwCmpFlags
0x14003103a  lea     ecx, [rsi+7Ah]; Locale
0x14003103d  mov     [rsp+88h+lpString2], rax; lpString2
0x140031042  call    cs:__imp_CompareStringW
0x140031048  cmp     eax, 2
0x14003104b  jz      short loc_140031092
0x14003104d  mov     rcx, [rdi+0D0h]; lpString1
0x140031054  lea     rdx, aTextHtml; "text/html;"
0x14003105b  call    ?WUStringStartsWithI@@YAHPEB_W0@Z; WUStringStartsWithI(wchar_t const *,wchar_t const *)
0x140031060  test    eax, eax
0x140031062  jnz     short loc_140031092
0x140031064  mov     rax, [rdi+0D0h]
0x14003106b  mov     r9d, esi
0x14003106e  mov     [rsp+88h+var_58], rax
0x140031073  mov     r8d, ebp
0x140031076  lea     rax, aWinhttpContent; "WinHttp: Content-Type header is %ls.  C"...
0x14003107d  xor     edx, edx
0x14003107f  mov     qword ptr [rsp+88h+cchCount2], rax
0x140031084  xor     ecx, ecx
0x140031086  mov     [rsp+88h+lpString2], r13
0x14003108b  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140031090  jmp     short loc_1400310D1
0x140031092  lea     rax, aWinhttpContent_0; "WinHttp: Content-Type header is text/ht"...
0x140031099  mov     ebx, 80240038h
0x14003109e  mov     qword ptr [rsp+88h+cchCount2], rax
0x1400310a3  mov     r9d, esi
0x1400310a6  mov     dword ptr [rsp+88h+lpString2], ebx
0x1400310aa  mov     r8d, ebp
0x1400310ad  jmp     loc_140030F3D
0x1400310b2  lea     rcx, aWinhttpFailedT; "WinHttp: Failed to get the content type"
0x1400310b9  mov     r9d, esi
0x1400310bc  mov     qword ptr [rsp+88h+cchCount2], rcx
0x1400310c1  mov     r8d, ebp
0x1400310c4  xor     ecx, ecx
0x1400310c6  mov     dword ptr [rsp+88h+lpString2], eax
0x1400310ca  xor     edx, edx
0x1400310cc  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1400310d1  mov     r8, r12; wchar_t *
0x1400310d4  mov     rcx, rdi; this
0x1400310d7  call    ?PerformDownloadToFile@CDownloadSession@@AEAAJPEAXPEB_W@Z; CDownloadSession::PerformDownloadToFile(void *,wchar_t const *)
0x1400310dc  xor     edx, edx
0x1400310de  xor     ecx, ecx
0x1400310e0  mov     ebx, eax
0x1400310e2  mov     r9d, esi
0x1400310e5  mov     r8d, ebp
0x1400310e8  test    eax, eax
0x1400310ea  jns     short loc_140031101
0x1400310ec  lea     rax, aWinhttpDofiled_0; "WinHttp: DoFileDownload PerformDownload"
0x1400310f3  mov     qword ptr [rsp+88h+cchCount2], rax
0x1400310f8  mov     dword ptr [rsp+88h+lpString2], ebx
0x1400310fc  jmp     loc_140030F41
0x140031101  lea     rax, aWinhttpSuccess; "WinHttp: Successfully downloaded %ls"
0x140031108  mov     [rsp+88h+var_58], r14
0x14003110d  mov     qword ptr [rsp+88h+cchCount2], rax
0x140031112  mov     [rsp+88h+lpString2], r13
0x140031117  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14003111c  test    r15, r15
0x14003111f  jz      short loc_140031128
0x140031121  mov     dword ptr [r15], 1
0x140031128  mov     eax, ebx
0x14003112a  jmp     short loc_140031131
0x14003112c  mov     eax, 80070057h
0x140031131  mov     rcx, [rsp+88h+var_40]
0x140031136  xor     rcx, rsp; StackCookie
0x140031139  call    __security_check_cookie
0x14003113e  mov     rbx, [rsp+88h+arg_10]
0x140031146  add     rsp, 50h
0x14003114a  pop     r15
0x14003114c  pop     r14
0x14003114e  pop     r13
0x140031150  pop     r12
0x140031152  pop     rdi
0x140031153  pop     rsi
0x140031154  pop     rbp
0x140031155  retn
```
