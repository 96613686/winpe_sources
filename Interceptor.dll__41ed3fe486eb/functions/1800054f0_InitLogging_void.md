# InitLogging(void)

- ea: `0x1800054f0`
- end: `0x1800056ea`
- name: `?InitLogging@@YAXXZ`
- size: `506`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800056ec`

## callees

- `0x180002b40`
- `0x18000410c`
- `0x1800052dc`
- `0x1800054f0`
- `0x180005804`
- `0x180005d04`
- `0x180021278`
- `0x180022a70`
- `0x1800266e0`
- `0x18002b400`

## import_xrefs

- `KERNEL32!GetModuleFileNameA` at `0x180005657`
- `KERNEL32!GetModuleFileNameA` at `0x180005657`
- `KERNEL32!GetCurrentProcessId` at `0x18000565d`
- `KERNEL32!GetCurrentProcessId` at `0x18000565d`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800055be`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800056b9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800055be`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800056b9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800055c5`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800056c0`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800055c5`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800056c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void InitLogging(void)
{
  __int64 v0; // rcx
  void *v1; // rcx
  int v2; // edx
  int v3; // ecx
  char v4; // bl
  int v5; // r8d
  int v6; // r9d
  __int64 v7; // rdx
  __int64 v8; // rcx
  void *v9; // rcx
  DWORD CurrentProcessId; // [rsp+44h] [rbp-BCh] BYREF
  void *Src[2]; // [rsp+48h] [rbp-B8h] BYREF
  __m128i si128; // [rsp+58h] [rbp-A8h]
  void *Block[2]; // [rsp+68h] [rbp-98h] BYREF
  __int128 v14; // [rsp+78h] [rbp-88h]
  CHAR Filename[256]; // [rsp+90h] [rbp-70h] BYREF

  *(_OWORD *)Src = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Src[0]) = 0;
  OPath::GetTempPathW((char *)Src);
  *(_OWORD *)Block = 0;
  v14 = 0;
  std::wstring::_Construct<1,wchar_t const *>(Block, L"Interceptor(*).log", 18);
  OPath::Combine(Src, Block, Src);
  if ( *((_QWORD *)&v14 + 1) > 7u )
  {
    v1 = Block[0];
    if ( (unsigned __int64)(2LL * *((_QWORD *)&v14 + 1) + 2) >= 0x1000 )
    {
      v1 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v1 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v1);
  }
  if ( OLog::sinstance )
    OLog::SetFile(v0, Src);
  v4 = sub_1800052DC();
  if ( OLog::sinstance )
  {
    LOBYTE(v3) = *(_BYTE *)OLog::sinstance;
    *(_BYTE *)OLog::sinstance = v4;
    if ( (_BYTE)v3 != v4 )
      Mso::Logging::MsoSendTraceTag<unsigned char,unsigned char>(v3, v2, v5, v6);
  }
  if ( (unsigned __int8)v4 >= 0x32u )
    HIBYTE(word_1800631F0) = 1;
  byte_1800631F2 = 1;
  if ( olog == 100 )
  {
    memset(Filename, 0, 255);
    GetModuleFileNameA(0, Filename, 0xFFu);
    CurrentProcessId = GetCurrentProcessId();
    LogLineFormat<42,char [255],unsigned long>(v8, v7, Filename, &CurrentProcessId);
  }
  if ( si128.m128i_i64[1] > 7uLL )
  {
    v9 = Src[0];
    if ( (unsigned __int64)(2 * si128.m128i_i64[1] + 2) >= 0x1000 )
    {
      v9 = (void *)*((_QWORD *)Src[0] - 1);
      if ( (unsigned __int64)((char *)Src[0] - (char *)v9 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v9);
  }
}

```

## disassembly

```asm
0x1800054f0  mov     [rsp-8+arg_0], rbx
0x1800054f5  mov     [rsp-8+arg_8], rdi
0x1800054fa  push    rbp
0x1800054fb  lea     rbp, [rsp-0A0h]
0x180005503  sub     rsp, 1A0h
0x18000550a  mov     rax, cs:__security_cookie
0x180005511  xor     rax, rsp
0x180005514  mov     [rbp+0A0h+var_10], rax
0x18000551b  xorps   xmm0, xmm0
0x18000551e  movups  xmmword ptr [rsp+1A0h+Src], xmm0
0x180005523  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18000552b  movdqu  [rsp+1A0h+var_148], xmm1
0x180005531  xor     edi, edi
0x180005533  mov     word ptr [rsp+1A0h+Src], di
0x180005538  lea     rcx, [rsp+1A0h+Src]; Src
0x18000553d  call    ?GetTempPathW@OPath@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; OPath::GetTempPathW(std::wstring &)
0x180005542  xorps   xmm0, xmm0
0x180005545  movups  xmmword ptr [rsp+1A0h+Block], xmm0
0x18000554a  xorps   xmm1, xmm1
0x18000554d  movdqu  [rsp+1A0h+var_128], xmm1
0x180005553  lea     r8d, [rdi+12h]
0x180005557  lea     rdx, aInterceptorLog; "Interceptor(*).log"
0x18000555e  lea     rcx, [rsp+1A0h+Block]
0x180005563  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180005568  lea     r8, [rsp+1A0h+Src]
0x18000556d  lea     rdx, [rsp+1A0h+Block]
0x180005572  lea     rcx, [rsp+1A0h+Src]
0x180005577  call    ?Combine@OPath@@SAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEAV23@@Z; OPath::Combine(std::wstring const &,std::wstring const &,std::wstring &)
0x18000557c  mov     rax, qword ptr [rbp+0A0h+var_128+8]
0x180005580  cmp     rax, 7
0x180005584  jbe     short loc_1800055CB
0x180005586  mov     rcx, [rsp+1A0h+Block]; Block
0x18000558b  mov     rdx, rcx
0x18000558e  lea     rax, ds:2[rax*2]
0x180005596  cmp     rax, 1000h
0x18000559c  jb      short loc_1800055C5
0x18000559e  mov     rcx, [rcx-8]
0x1800055a2  sub     rdx, rcx
0x1800055a5  lea     rax, [rdx-8]
0x1800055a9  cmp     rax, 1Fh
0x1800055ad  jbe     short loc_1800055C5
0x1800055af  mov     [rsp+1A0h+Reserved], rdi; Reserved
0x1800055b4  xor     r9d, r9d; LineNo
0x1800055b7  xor     r8d, r8d; FileName
0x1800055ba  xor     edx, edx; FunctionName
0x1800055bc  xor     ecx, ecx; Expression
0x1800055be  call    cs:__imp__invoke_watson
0x1800055c5  call    cs:__imp_free
0x1800055cb  cmp     cs:?sinstance@OLog@@2PEAV1@EA, rdi; OLog * OLog::sinstance
0x1800055d2  jz      short loc_1800055DE
0x1800055d4  lea     rdx, [rsp+1A0h+Src]
0x1800055d9  call    ?SetFile@OLog@@QEAAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; OLog::SetFile(std::wstring const &)
0x1800055de  call    sub_1800052DC
0x1800055e3  mov     bl, al
0x1800055e5  mov     rax, cs:?sinstance@OLog@@2PEAV1@EA; OLog * OLog::sinstance
0x1800055ec  test    rax, rax
0x1800055ef  jz      short loc_18000561A
0x1800055f1  mov     cl, [rax]
0x1800055f3  mov     [rax], bl
0x1800055f5  cmp     cl, bl
0x1800055f7  jz      short loc_18000561A
0x1800055f9  mov     [rsp+1A0h+var_160], bl
0x1800055fd  mov     [rsp+1A0h+var_15F], cl
0x180005601  lea     rax, [rsp+1A0h+var_160]
0x180005606  mov     [rsp+1A0h+var_170], rax
0x18000560b  lea     rax, [rsp+1A0h+var_15F]
0x180005610  mov     [rsp+1A0h+var_178], rax
0x180005615  call    ??$MsoSendTraceTag@EE@Logging@Mso@@YAXKW4Category@01@W4Severity@01@W4DataCategories@01@PEB_WAEBE4@Z; Mso::Logging::MsoSendTraceTag<uchar,uchar>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Logging::DataCategories,wchar_t const *,uchar const &,uchar const &)
0x18000561a  cmp     bl, 32h ; '2'
0x18000561d  jb      short loc_180005626
0x18000561f  mov     byte ptr cs:word_1800631F0+1, 1
0x180005626  mov     cs:byte_1800631F2, 1
0x18000562d  cmp     cs:?olog@@3VOLog@@A, 64h ; 'd'; OLog olog
0x180005634  jnz     short loc_180005676
0x180005636  mov     [rbp+0A0h+Filename], dil
0x18000563a  xor     edx, edx; Val
0x18000563c  mov     r8d, 0FEh; Size
0x180005642  lea     rcx, [rbp+0A0h+var_10F]; void *
0x180005646  call    memset
0x18000564b  mov     r8d, 0FFh; nSize
0x180005651  lea     rdx, [rbp+0A0h+Filename]; lpFilename
0x180005655  xor     ecx, ecx; hModule
0x180005657  call    cs:__imp_GetModuleFileNameA
0x18000565d  call    cs:__imp_GetCurrentProcessId
0x180005663  mov     [rsp+1A0h+var_15C], eax
0x180005667  lea     r9, [rsp+1A0h+var_15C]
0x18000566c  lea     r8, [rbp+0A0h+Filename]
0x180005670  call    ??$LogLineFormat@$0CK@$$BY0PP@DK@@YAXW4Severity@Logging@Mso@@AEAY0CK@$$CB_WAEAY0PP@$$CBDAEBK@Z; LogLineFormat<42,char [255],ulong>(Mso::Logging::Severity,wchar_t const (&)[42],char const (&)[255],ulong const &)
0x180005675  nop
0x180005676  mov     rax, qword ptr [rsp+1A0h+var_148+8]
0x18000567b  cmp     rax, 7
0x18000567f  jbe     short loc_1800056C6
0x180005681  mov     rcx, [rsp+1A0h+Src]; Block
0x180005686  mov     rdx, rcx
0x180005689  lea     rax, ds:2[rax*2]
0x180005691  cmp     rax, 1000h
0x180005697  jb      short loc_1800056C0
0x180005699  mov     rcx, [rcx-8]
0x18000569d  sub     rdx, rcx
0x1800056a0  lea     rax, [rdx-8]
0x1800056a4  cmp     rax, 1Fh
0x1800056a8  jbe     short loc_1800056C0
0x1800056aa  mov     [rsp+1A0h+Reserved], rdi; Reserved
0x1800056af  xor     r9d, r9d; LineNo
0x1800056b2  xor     r8d, r8d; FileName
0x1800056b5  xor     edx, edx; FunctionName
0x1800056b7  xor     ecx, ecx; Expression
0x1800056b9  call    cs:__imp__invoke_watson
0x1800056c0  call    cs:__imp_free
0x1800056c6  mov     rcx, [rbp+0A0h+var_10]
0x1800056cd  xor     rcx, rsp; StackCookie
0x1800056d0  call    __security_check_cookie
0x1800056d5  lea     r11, [rsp+1A0h+var_s0]
0x1800056dd  mov     rbx, [r11+10h]
0x1800056e1  mov     rdi, [r11+18h]
0x1800056e5  mov     rsp, r11
0x1800056e8  pop     rbp
0x1800056e9  retn
```
