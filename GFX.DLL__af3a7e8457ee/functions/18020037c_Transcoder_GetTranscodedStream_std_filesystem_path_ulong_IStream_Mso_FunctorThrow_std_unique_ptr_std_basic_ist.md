# Transcoder::GetTranscodedStream(std::filesystem::path &&,ulong,IStream &,Mso::FunctorThrow<std::unique_ptr<std::basic_istream<char,std::char_traits<char>>,std::default_delete<std::basic_istream<char,std::char_traits<char>>>> (char const *)> &&)

- ea: `0x18020037c`
- end: `0x180200835`
- name: `?GetTranscodedStream@Transcoder@@YA?AV?$TCntPtr@UIStream@@@Mso@@$$QEAVpath@filesystem@std@@KAEAUIStream@@$$QEAV?$FunctorThrow@$$A6A?AV?$unique_ptr@V?$basic_istream@DU?$char_traits@D@std@@@std@@U?$default_delete@V?$basic_istream@DU?$char_traits@D@std@@@std@@@2@@std@@PEBD@Z@3@@Z`
- size: `1209`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801d81f0`

## callees

- `0x18000b320`
- `0x18000c300`
- `0x180055b26`
- `0x180056ee0`
- `0x1800573f0`
- `0x180064e30`
- `0x18007aa30`
- `0x18008dd10`
- `0x18008eeb8`
- `0x18008feec`
- `0x180190114`
- `0x1801ff780`
- `0x1801ff944`
- `0x18020037c`
- `0x1802011f4`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1802007cc`
- `KERNEL32!CloseHandle` at `0x1802007cc`
- `KERNEL32!OpenProcess` at `0x18020079f`
- `KERNEL32!OpenProcess` at `0x18020079f`
- `KERNEL32!GetProcAddress` at `0x180200661`
- `KERNEL32!GetProcAddress` at `0x180200661`
- `KERNEL32!GetModuleHandleW` at `0x180200651`
- `KERNEL32!GetModuleHandleW` at `0x180200651`
- `KERNEL32!WaitForSingleObject` at `0x1802007b8`
- `KERNEL32!WaitForSingleObject` at `0x1802007b8`
- `MSO!__imp_?LrGetBroker@@YAAEAUILrBroker@LowRights@@XZ` at `0x1802006fe`
- `MSO!__imp_?LrGetBroker@@YAAEAUILrBroker@LowRights@@XZ` at `0x1802006fe`
- `Mso30Win32Client!__imp_?GetAPI@Gimme@Mso@@YAPEAUIGimme@12@XZ` at `0x180200687`
- `Mso30Win32Client!__imp_?GetAPI@Gimme@Mso@@YAPEAUIGimme@12@XZ` at `0x180200687`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180200767`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180200767`

## string_xrefs

- `0x18020064a`: `kernel32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall Transcoder::GetTranscodedStream(_QWORD *a1, __int64 a2, unsigned int a3, __int64 a4, __int64 a5)
{
  wchar_t **v8; // r14
  unsigned int v9; // r15d
  char *v10; // r15
  const wchar_t *i; // rcx
  wchar_t *v12; // rax
  int v13; // edx
  wchar_t *v14; // rbx
  unsigned int v15; // r8d
  __int64 v16; // rbx
  void *v17; // rax
  __int64 v18; // rax
  _WORD *v19; // r9
  __int128 *v20; // rax
  _QWORD *v21; // rax
  _QWORD *v22; // rbx
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  unsigned __int64 v25; // rcx
  int v26; // eax
  struct Mso::Gimme::IGimme *API; // rax
  struct LowRights::ILrBroker *Broker; // rax
  DWORD v29; // eax
  __int64 v30; // rax
  HANDLE v31; // rax
  void *v32; // rdi
  _QWORD *v34; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v35[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD *v36; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v37; // [rsp+68h] [rbp-98h] BYREF
  char v38[518]; // [rsp+6Ah] [rbp-96h] BYREF
  _OWORD v39[2]; // [rsp+270h] [rbp+170h] BYREF
  int v40; // [rsp+290h] [rbp+190h]
  _QWORD *v41; // [rsp+298h] [rbp+198h]
  int v42; // [rsp+2A0h] [rbp+1A0h]
  char v43; // [rsp+2A4h] [rbp+1A4h]
  __int16 v44; // [rsp+2A5h] [rbp+1A5h]
  char v45; // [rsp+2A7h] [rbp+1A7h]
  int v46; // [rsp+2A8h] [rbp+1A8h]
  __int16 v47; // [rsp+2ACh] [rbp+1ACh]
  __int128 v48; // [rsp+2B0h] [rbp+1B0h] BYREF
  __m128i si128; // [rsp+2C0h] [rbp+1C0h]
  wchar_t *S[2]; // [rsp+2D0h] [rbp+1D0h] BYREF
  __int128 v51; // [rsp+2E0h] [rbp+1E0h]
  _QWORD v52[4]; // [rsp+2F0h] [rbp+1F0h] BYREF
  _BYTE v53[32]; // [rsp+310h] [rbp+210h] BYREF
  _BYTE v54[42]; // [rsp+330h] [rbp+230h] BYREF
  _BYTE v55[6]; // [rsp+35Ah] [rbp+25Ah] BYREF

  v34 = a1;
  Mso::Make<Transcoder::CTranscoderProxy,Transcoder::CTranscoderProxy,IStream &,Mso::FunctorThrow<std::unique_ptr<std::istream> (char const *)>>(
    &v34,
    a4,
    a5);
  v48 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v48) = 0;
  std::wstring::wstring(S, a2);
  v8 = S;
  if ( *((_QWORD *)&v51 + 1) > 7u )
    v8 = (wchar_t **)S[0];
  v9 = 1;
  if ( (_QWORD)v51 )
  {
    v10 = (char *)v8 + 2 * v51;
    for ( i = (const wchar_t *)v8; ; i = v14 + 1 )
    {
      v12 = wmemchr(i, 0x22u, (v10 - (char *)i) >> 1);
      v14 = v12;
      if ( !v12 )
        break;
      if ( !wmemcmp(v12, L"\"", (unsigned int)(v13 - 33)) )
      {
        v16 = ((char *)v14 - (char *)v8) >> 1;
        v9 = v15;
        goto LABEL_11;
      }
    }
    v9 = 1;
  }
  v16 = -1;
LABEL_11:
  std::wstring::~wstring(S);
  std::wstring::wstring(v53, a2);
  if ( v16 )
  {
    v17 = (void *)std::operator+<wchar_t>(v54, L"\"", v53);
    v18 = std::wstring::append(v17);
    *(_OWORD *)S = *(_OWORD *)v18;
    v51 = *(_OWORD *)(v18 + 16);
    *(_WORD *)v18 = 0;
    *(_QWORD *)(v18 + 16) = 0;
    *(_QWORD *)(v18 + 24) = 7;
    std::wstring::operator=(&v48, S);
    std::wstring::~wstring(S);
    std::wstring::~wstring(v54);
  }
  else
  {
    std::wstring::operator=(&v48, v53);
  }
  std::wstring::~wstring(v53);
  v19 = v55;
  do
  {
    *--v19 = a3 % 0xA + 48;
    a3 /= 0xAu;
  }
  while ( a3 );
  std::wstring::wstring(v52, v19, v55);
  v20 = &v48;
  if ( si128.m128i_i64[1] > 7uLL )
    v20 = (__int128 *)v48;
  v35[0] = v20;
  v21 = v52;
  if ( v52[3] > 7u )
    v21 = (_QWORD *)v52[0];
  v35[1] = v21;
  v22 = v34;
  v36 = v34;
  v37 = 0;
  memset_0(v38, 0, sizeof(v38));
  v39[0] = 0;
  v39[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v39[0]) = 0;
  v42 = 0;
  v44 = 0;
  v46 = 256;
  v47 = 0;
  v41 = v35;
  v40 = 2;
  v43 = v9;
  v45 = v9;
  ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
  ProcAddress = GetProcAddress(ModuleHandleW, "IsUserCetAvailableInEnvironment");
  if ( ProcAddress )
  {
    v26 = ((__int64 (__fastcall *)(_QWORD))ProcAddress)(0);
    v25 = (unsigned __int8)v47;
    if ( v26 )
      v25 = v9;
    LOBYTE(v47) = v25;
  }
  API = Mso::Gimme::GetAPI((Mso::Gimme *)v25);
  if ( (*(unsigned __int8 (__fastcall **)(struct Mso::Gimme::IGimme *, __int64, _QWORD, _QWORD, __int16 *, int, int))(*(_QWORD *)API + 24LL))(
         API,
         284,
         0,
         0,
         &v37,
         260,
         3871) )
  {
    Broker = LrGetBroker();
    if ( (**(unsigned __int8 (__fastcall ***)(struct LowRights::ILrBroker *, _QWORD **))Broker)(Broker, &v36) )
    {
      if ( !v22 )
        CrashWithRecovery(0x1E3C3840u, 0);
      if ( v22[1] )
      {
        v30 = Mso::TCntPtr<IWICImagingFactory>::operator->(v22 + 1);
        v29 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      }
      else
      {
        v29 = 0;
      }
      v31 = OpenProcess(0x100000u, v9, v29);
      v32 = v31;
      if ( v31 )
      {
        WaitForSingleObject(v31, 0xFFFFFFFF);
        Transcoder::CTranscoderProxy::GetOutputStream(v22, a1);
        CloseHandle(v32);
      }
      else
      {
        *a1 = 0;
      }
      std::wstring::~wstring(v39);
      std::wstring::~wstring(v52);
      std::wstring::~wstring(&v48);
      goto LABEL_39;
    }
    *a1 = 0;
    std::wstring::~wstring(v39);
    std::wstring::~wstring(v52);
    std::wstring::~wstring(&v48);
    if ( v22 )
LABEL_39:
      (*(void (__fastcall **)(_QWORD *))(*v22 + 8LL))(v22);
  }
  else
  {
    *a1 = 0;
    std::wstring::~wstring(v39);
    std::wstring::~wstring(v52);
    std::wstring::~wstring(&v48);
    if ( v22 )
      goto LABEL_39;
  }
  return a1;
}

```

## disassembly

```asm
0x18020037c  mov     [rsp-8+arg_10], rbx
0x180200381  push    rbp
0x180200382  push    rsi
0x180200383  push    rdi
0x180200384  push    r12
0x180200386  push    r13
0x180200388  push    r14
0x18020038a  push    r15
0x18020038c  lea     rbp, [rsp-270h]
0x180200394  sub     rsp, 370h
0x18020039b  mov     rax, cs:__security_cookie
0x1802003a2  xor     rax, rsp
0x1802003a5  mov     [rbp+2A0h+var_40], rax
0x1802003ac  mov     edi, r8d
0x1802003af  mov     r12, rdx
0x1802003b2  mov     rsi, rcx
0x1802003b5  mov     [rsp+3A0h+var_360], rcx
0x1802003ba  mov     r8, [rbp+2A0h+arg_20]
0x1802003c1  xor     r13d, r13d
0x1802003c4  mov     rdx, r9
0x1802003c7  lea     rcx, [rsp+3A0h+var_360]
0x1802003cc  call    ??$Make@VCTranscoderProxy@Transcoder@@V12@AEAUIStream@@V?$FunctorThrow@$$A6A?AV?$unique_ptr@V?$basic_istream@DU?$char_traits@D@std@@@std@@U?$default_delete@V?$basic_istream@DU?$char_traits@D@std@@@std@@@2@@std@@PEBD@Z@Mso@@@Mso@@YA?AV?$TCntPtr@VCTranscoderProxy@Transcoder@@@0@AEAUIStream@@$$QEAV?$FunctorThrow@$$A6A?AV?$unique_ptr@V?$basic_istream@DU?$char_traits@D@std@@@std@@U?$default_delete@V?$basic_istream@DU?$char_traits@D@std@@@std@@@2@@std@@PEBD@Z@0@@Z; Mso::Make<Transcoder::CTranscoderProxy,Transcoder::CTranscoderProxy,IStream &,Mso::FunctorThrow<std::unique_ptr<std::istream> (char const *)>>(IStream &,Mso::FunctorThrow<std::unique_ptr<std::istream> (char const *)> &&)
0x1802003d1  xorps   xmm0, xmm0
0x1802003d4  movups  [rbp+2A0h+var_F0], xmm0
0x1802003db  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1802003e3  movdqu  [rbp+2A0h+var_E0], xmm1
0x1802003eb  mov     word ptr [rbp+2A0h+var_F0], r13w
0x1802003f3  mov     rdx, r12
0x1802003f6  lea     rcx, [rbp+2A0h+S]
0x1802003fd  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180200402  lea     r14, [rbp+2A0h+S]
0x180200409  cmp     qword ptr [rbp+2A0h+var_C0+8], 7
0x180200411  cmova   r14, [rbp+2A0h+S]
0x180200419  mov     rax, qword ptr [rbp+2A0h+var_C0]
0x180200420  lea     r15d, [r13+1]
0x180200424  cmp     rax, r15
0x180200427  jb      short loc_180200479
0x180200429  lea     r15, [r14+rax*2]
0x18020042d  mov     rcx, r14; S
0x180200430  mov     r8, r15
0x180200433  sub     r8, rcx
0x180200436  sar     r8, 1; N
0x180200439  mov     edx, 22h ; '"'; C
0x18020043e  call    wmemchr
0x180200443  mov     rbx, rax
0x180200446  test    rax, rax
0x180200449  jz      short loc_180200473
0x18020044b  lea     r8d, [rdx-21h]; N
0x18020044f  lea     rdx, S2; "\""
0x180200456  mov     rcx, rax; S1
0x180200459  call    wmemcmp
0x18020045e  test    eax, eax
0x180200460  jz      short loc_180200468
0x180200462  lea     rcx, [rbx+2]
0x180200466  jmp     short loc_180200430
0x180200468  sub     rbx, r14
0x18020046b  sar     rbx, 1
0x18020046e  mov     r15, r8
0x180200471  jmp     short loc_18020047D
0x180200473  mov     r15d, 1
0x180200479  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18020047d  lea     rcx, [rbp+2A0h+S]
0x180200484  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180200489  mov     rdx, r12
0x18020048c  lea     rcx, [rbp+2A0h+var_90]
0x180200493  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180200498  test    rbx, rbx
0x18020049b  jz      loc_180200521
0x1802004a1  lea     r8, [rbp+2A0h+var_90]
0x1802004a8  lea     rdx, S2; "\""
0x1802004af  lea     rcx, [rbp+2A0h+var_70]
0x1802004b6  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@QEB_W$$QEAV10@@Z; std::operator+<wchar_t>(wchar_t const * const,std::wstring &&)
0x1802004bb  nop
0x1802004bc  mov     r8, r15
0x1802004bf  lea     rdx, S2; "\""
0x1802004c6  mov     rcx, rax; Src
0x1802004c9  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x1802004ce  movups  xmm0, xmmword ptr [rax]
0x1802004d1  movups  xmmword ptr [rbp+2A0h+S], xmm0
0x1802004d8  movups  xmm1, xmmword ptr [rax+10h]
0x1802004dc  movups  [rbp+2A0h+var_C0], xmm1
0x1802004e3  mov     [rax], r13w
0x1802004e7  mov     [rax+10h], r13
0x1802004eb  mov     qword ptr [rax+18h], 7
0x1802004f3  lea     rdx, [rbp+2A0h+S]
0x1802004fa  lea     rcx, [rbp+2A0h+var_F0]
0x180200501  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180200506  lea     rcx, [rbp+2A0h+S]
0x18020050d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180200512  nop
0x180200513  lea     rcx, [rbp+2A0h+var_70]
0x18020051a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18020051f  jmp     short loc_180200534
0x180200521  lea     rdx, [rbp+2A0h+var_90]
0x180200528  lea     rcx, [rbp+2A0h+var_F0]
0x18020052f  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180200534  lea     rcx, [rbp+2A0h+var_90]
0x18020053b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180200540  lea     r9, [rbp+2A0h+var_46]
0x180200547  sub     r9, 2
0x18020054b  mov     eax, 0CCCCCCCDh
0x180200550  mul     edi
0x180200552  shr     edx, 3
0x180200555  movzx   eax, dx
0x180200558  shl     ax, 2
0x18020055c  lea     ecx, [rax+rdx]
0x18020055f  add     cx, cx
0x180200562  sub     di, cx
0x180200565  add     di, 30h ; '0'
0x180200569  mov     [r9], di
0x18020056d  mov     edi, edx
0x18020056f  test    edx, edx
0x180200571  jnz     short loc_180200547
0x180200573  lea     r8, [rbp+2A0h+var_46]
0x18020057a  mov     rdx, r9
0x18020057d  lea     rcx, [rbp+2A0h+var_B0]
0x180200584  call    ??$?0PEA_W$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEA_W0AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wchar_t *,wchar_t *,std::allocator<wchar_t> const &)
0x180200589  lea     rax, [rbp+2A0h+var_F0]
0x180200590  cmp     qword ptr [rbp+2A0h+var_E0+8], 7
0x180200598  cmova   rax, qword ptr [rbp+2A0h+var_F0]
0x1802005a0  mov     [rsp+3A0h+var_350], rax
0x1802005a5  lea     rax, [rbp+2A0h+var_B0]
0x1802005ac  cmp     [rbp+2A0h+var_98], 7
0x1802005b4  cmova   rax, [rbp+2A0h+var_B0]
0x1802005bc  mov     [rsp+3A0h+var_348], rax
0x1802005c1  mov     rbx, [rsp+3A0h+var_360]
0x1802005c6  mov     [rsp+3A0h+var_340], rbx
0x1802005cb  mov     [rsp+3A0h+var_338], r13w
0x1802005d1  xor     edx, edx; Val
0x1802005d3  mov     r8d, 206h; Size
0x1802005d9  lea     rcx, [rsp+3A0h+var_336]; void *
0x1802005de  call    memset_0
0x1802005e3  xorps   xmm0, xmm0
0x1802005e6  movups  [rbp+2A0h+var_130], xmm0
0x1802005ed  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1802005f5  movdqa  [rbp+2A0h+var_120], xmm1
0x1802005fd  mov     word ptr [rbp+2A0h+var_130], r13w
0x180200605  mov     [rbp+2A0h+var_100], r13d
0x18020060c  mov     [rbp+2A0h+var_FB], r13w
0x180200614  mov     [rbp+2A0h+var_F8], 100h
0x18020061e  mov     [rbp+2A0h+var_F4], r13w
0x180200626  lea     rax, [rsp+3A0h+var_350]
0x18020062b  mov     [rbp+2A0h+var_108], rax
0x180200632  mov     [rbp+2A0h+var_110], 2
0x18020063c  mov     [rbp+2A0h+var_FC], r15b
0x180200643  mov     [rbp+2A0h+var_F9], r15b
0x18020064a  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x180200651  call    cs:__imp_GetModuleHandleW
0x180200657  mov     rcx, rax; hModule
0x18020065a  lea     rdx, aIsusercetavail; "IsUserCetAvailableInEnvironment"
0x180200661  call    cs:__imp_GetProcAddress
0x180200667  test    rax, rax
0x18020066a  jz      short loc_180200687
0x18020066c  xor     ecx, ecx
0x18020066e  call    cs:__guard_dispatch_icall_fptr
0x180200674  movzx   ecx, byte ptr [rbp+2A0h+var_F4]
0x18020067b  test    eax, eax
0x18020067d  cmovnz  ecx, r15d
0x180200681  mov     byte ptr [rbp+2A0h+var_F4], cl
0x180200687  call    cs:__imp_?GetAPI@Gimme@Mso@@YAPEAUIGimme@12@XZ; Mso::Gimme::GetAPI(void)
0x18020068d  mov     r10, rax
0x180200690  mov     rcx, [rax]
0x180200693  mov     rax, [rcx+18h]
0x180200697  mov     [rsp+3A0h+var_370], 0F1Fh
0x18020069f  mov     [rsp+3A0h+var_378], 104h
0x1802006a7  lea     rcx, [rsp+3A0h+var_338]
0x1802006ac  mov     [rsp+3A0h+var_380], rcx
0x1802006b1  xor     r9d, r9d
0x1802006b4  xor     r8d, r8d
0x1802006b7  mov     edx, 11Ch
0x1802006bc  mov     rcx, r10
0x1802006bf  call    cs:__guard_dispatch_icall_fptr
0x1802006c5  test    al, al
0x1802006c7  jnz     short loc_1802006FE
0x1802006c9  mov     [rsi], r13
0x1802006cc  lea     rcx, [rbp+2A0h+var_130]
0x1802006d3  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1802006d8  lea     rcx, [rbp+2A0h+var_B0]
0x1802006df  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1802006e4  lea     rcx, [rbp+2A0h+var_F0]
0x1802006eb  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1802006f0  test    rbx, rbx
0x1802006f3  jz      loc_180200808
0x1802006f9  jmp     loc_1802007F8
0x1802006fe  call    cs:__imp_?LrGetBroker@@YAAEAUILrBroker@LowRights@@XZ; LrGetBroker(void)
0x180200704  mov     r8, rax
0x180200707  mov     rcx, [rax]
0x18020070a  mov     rax, [rcx]
0x18020070d  lea     rdx, [rsp+3A0h+var_340]
0x180200712  mov     rcx, r8
0x180200715  call    cs:__guard_dispatch_icall_fptr
0x18020071b  test    al, al
0x18020071d  jnz     short loc_18020075B
0x18020071f  mov     [rsi], r13
0x180200722  lea     rcx, [rbp+2A0h+var_130]
0x180200729  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18020072e  lea     rcx, [rbp+2A0h+var_B0]
0x180200735  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18020073a  lea     rcx, [rbp+2A0h+var_F0]
0x180200741  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180200746  test    rbx, rbx
0x180200749  jz      loc_180200808
0x18020074f  mov     rcx, [rbx]
0x180200752  mov     rax, [rcx+8]
0x180200756  jmp     loc_1802007FF
0x18020075b  test    rbx, rbx
0x18020075e  jnz     short loc_18020076E
0x180200760  xor     edx, edx
0x180200762  mov     ecx, 1E3C3840h
0x180200767  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18020076d  nop
0x18020076e  lea     rcx, [rbx+8]
0x180200772  cmp     [rcx], r13
0x180200775  jnz     short loc_18020077C
0x180200777  mov     eax, r13d
0x18020077a  jmp     short loc_180200794
0x18020077c  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x180200781  mov     r8, rax
0x180200784  mov     rcx, [rax]
0x180200787  mov     rax, [rcx+10h]
0x18020078b  mov     rcx, r8
0x18020078e  call    cs:__guard_dispatch_icall_fptr
0x180200794  mov     r8d, eax; dwProcessId
0x180200797  mov     edx, r15d; bInheritHandle
0x18020079a  mov     ecx, 100000h; dwDesiredAccess
0x18020079f  call    cs:__imp_OpenProcess
0x1802007a5  mov     rdi, rax
0x1802007a8  test    rax, rax
0x1802007ab  jnz     short loc_1802007B2
0x1802007ad  mov     [rsi], r13
0x1802007b0  jmp     short loc_1802007D3
0x1802007b2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1802007b5  mov     rcx, rdi; hHandle
0x1802007b8  call    cs:__imp_WaitForSingleObject
0x1802007be  mov     rdx, rsi
0x1802007c1  mov     rcx, rbx
0x1802007c4  call    ?GetOutputStream@CTranscoderProxy@Transcoder@@QEAA?AV?$TCntPtr@UIStream@@@Mso@@XZ; Transcoder::CTranscoderProxy::GetOutputStream(void)
0x1802007c9  mov     rcx, rdi; hObject
0x1802007cc  call    cs:__imp_CloseHandle
0x1802007d2  nop
0x1802007d3  lea     rcx, [rbp+2A0h+var_130]
0x1802007da  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1802007df  lea     rcx, [rbp+2A0h+var_B0]
0x1802007e6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1802007eb  lea     rcx, [rbp+2A0h+var_F0]
0x1802007f2  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1802007f7  nop
0x1802007f8  mov     rax, [rbx]
0x1802007fb  mov     rax, [rax+8]
0x1802007ff  mov     rcx, rbx
0x180200802  call    cs:__guard_dispatch_icall_fptr
0x180200808  mov     rax, rsi
0x18020080b  mov     rcx, [rbp+2A0h+var_40]
0x180200812  xor     rcx, rsp; StackCookie
0x180200815  call    __security_check_cookie
0x18020081a  mov     rbx, [rsp+3A0h+arg_10]
0x180200822  add     rsp, 370h
0x180200829  pop     r15
0x18020082b  pop     r14
0x18020082d  pop     r13
0x18020082f  pop     r12
0x180200831  pop     rdi
0x180200832  pop     rsi
0x180200833  pop     rbp
0x180200834  retn
```
