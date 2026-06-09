# Transcoder::GetTranscodedStream(std::filesystem::path &&,ulong,IStream &,Mso::FunctorThrow<std::unique_ptr<std::basic_istream<char,std::char_traits<char>>,std::default_delete<std::basic_istream<char,std::char_traits<char>>>> (char const *)> &&)

- ea: `0x1802036ac`
- end: `0x180203b65`
- name: `?GetTranscodedStream@Transcoder@@YA?AV?$TCntPtr@UIStream@@@Mso@@$$QEAVpath@filesystem@std@@KAEAUIStream@@$$QEAV?$FunctorThrow@$$A6A?AV?$unique_ptr@V?$basic_istream@DU?$char_traits@D@std@@@std@@U?$default_delete@V?$basic_istream@DU?$char_traits@D@std@@@std@@@2@@std@@PEBD@Z@3@@Z`
- size: `1209`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1801dbe30`

## callees

- `0x18000b5a8`
- `0x18000c29c`
- `0x1800565ba`
- `0x1800578b0`
- `0x180057e70`
- `0x180072d00`
- `0x180077780`
- `0x1800fb268`
- `0x180144dd8`
- `0x180159780`
- `0x180193df4`
- `0x180202ab0`
- `0x180202c74`
- `0x1802036ac`
- `0x180204524`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180203afc`
- `KERNEL32!CloseHandle` at `0x180203afc`
- `KERNEL32!OpenProcess` at `0x180203acf`
- `KERNEL32!OpenProcess` at `0x180203acf`
- `KERNEL32!GetProcAddress` at `0x180203991`
- `KERNEL32!GetProcAddress` at `0x180203991`
- `KERNEL32!GetModuleHandleW` at `0x180203981`
- `KERNEL32!GetModuleHandleW` at `0x180203981`
- `KERNEL32!WaitForSingleObject` at `0x180203ae8`
- `KERNEL32!WaitForSingleObject` at `0x180203ae8`
- `MSO!__imp_?LrGetBroker@@YAAEAUILrBroker@LowRights@@XZ` at `0x180203a2e`
- `MSO!__imp_?LrGetBroker@@YAAEAUILrBroker@LowRights@@XZ` at `0x180203a2e`
- `Mso30Win32Client!__imp_?GetAPI@Gimme@Mso@@YAPEAUIGimme@12@XZ` at `0x1802039b7`
- `Mso30Win32Client!__imp_?GetAPI@Gimme@Mso@@YAPEAUIGimme@12@XZ` at `0x1802039b7`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180203a97`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180203a97`

## string_xrefs

- `0x18020397a`: `kernel32.dll`

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
0x1802036ac  mov     [rsp-8+arg_10], rbx
0x1802036b1  push    rbp
0x1802036b2  push    rsi
0x1802036b3  push    rdi
0x1802036b4  push    r12
0x1802036b6  push    r13
0x1802036b8  push    r14
0x1802036ba  push    r15
0x1802036bc  lea     rbp, [rsp-270h]
0x1802036c4  sub     rsp, 370h
0x1802036cb  mov     rax, cs:__security_cookie
0x1802036d2  xor     rax, rsp
0x1802036d5  mov     [rbp+2A0h+var_40], rax
0x1802036dc  mov     edi, r8d
0x1802036df  mov     r12, rdx
0x1802036e2  mov     rsi, rcx
0x1802036e5  mov     [rsp+3A0h+var_360], rcx
0x1802036ea  mov     r8, [rbp+2A0h+arg_20]
0x1802036f1  xor     r13d, r13d
0x1802036f4  mov     rdx, r9
0x1802036f7  lea     rcx, [rsp+3A0h+var_360]
0x1802036fc  call    ??$Make@VCTranscoderProxy@Transcoder@@V12@AEAUIStream@@V?$FunctorThrow@$$A6A?AV?$unique_ptr@V?$basic_istream@DU?$char_traits@D@std@@@std@@U?$default_delete@V?$basic_istream@DU?$char_traits@D@std@@@std@@@2@@std@@PEBD@Z@Mso@@@Mso@@YA?AV?$TCntPtr@VCTranscoderProxy@Transcoder@@@0@AEAUIStream@@$$QEAV?$FunctorThrow@$$A6A?AV?$unique_ptr@V?$basic_istream@DU?$char_traits@D@std@@@std@@U?$default_delete@V?$basic_istream@DU?$char_traits@D@std@@@std@@@2@@std@@PEBD@Z@0@@Z; Mso::Make<Transcoder::CTranscoderProxy,Transcoder::CTranscoderProxy,IStream &,Mso::FunctorThrow<std::unique_ptr<std::istream> (char const *)>>(IStream &,Mso::FunctorThrow<std::unique_ptr<std::istream> (char const *)> &&)
0x180203701  xorps   xmm0, xmm0
0x180203704  movups  [rbp+2A0h+var_F0], xmm0
0x18020370b  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180203713  movdqu  [rbp+2A0h+var_E0], xmm1
0x18020371b  mov     word ptr [rbp+2A0h+var_F0], r13w
0x180203723  mov     rdx, r12
0x180203726  lea     rcx, [rbp+2A0h+S]
0x18020372d  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180203732  lea     r14, [rbp+2A0h+S]
0x180203739  cmp     qword ptr [rbp+2A0h+var_C0+8], 7
0x180203741  cmova   r14, [rbp+2A0h+S]
0x180203749  mov     rax, qword ptr [rbp+2A0h+var_C0]
0x180203750  lea     r15d, [r13+1]
0x180203754  cmp     rax, r15
0x180203757  jb      short loc_1802037A9
0x180203759  lea     r15, [r14+rax*2]
0x18020375d  mov     rcx, r14; S
0x180203760  mov     r8, r15
0x180203763  sub     r8, rcx
0x180203766  sar     r8, 1; N
0x180203769  mov     edx, 22h ; '"'; C
0x18020376e  call    wmemchr
0x180203773  mov     rbx, rax
0x180203776  test    rax, rax
0x180203779  jz      short loc_1802037A3
0x18020377b  lea     r8d, [rdx-21h]; N
0x18020377f  lea     rdx, S2; "\""
0x180203786  mov     rcx, rax; S1
0x180203789  call    wmemcmp
0x18020378e  test    eax, eax
0x180203790  jz      short loc_180203798
0x180203792  lea     rcx, [rbx+2]
0x180203796  jmp     short loc_180203760
0x180203798  sub     rbx, r14
0x18020379b  sar     rbx, 1
0x18020379e  mov     r15, r8
0x1802037a1  jmp     short loc_1802037AD
0x1802037a3  mov     r15d, 1
0x1802037a9  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1802037ad  lea     rcx, [rbp+2A0h+S]
0x1802037b4  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1802037b9  mov     rdx, r12
0x1802037bc  lea     rcx, [rbp+2A0h+var_90]
0x1802037c3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1802037c8  test    rbx, rbx
0x1802037cb  jz      loc_180203851
0x1802037d1  lea     r8, [rbp+2A0h+var_90]
0x1802037d8  lea     rdx, S2; "\""
0x1802037df  lea     rcx, [rbp+2A0h+var_70]
0x1802037e6  call    ??$?H_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@QEB_W$$QEAV10@@Z; std::operator+<wchar_t>(wchar_t const * const,std::wstring &&)
0x1802037eb  nop
0x1802037ec  mov     r8, r15
0x1802037ef  lea     rdx, S2; "\""
0x1802037f6  mov     rcx, rax; Src
0x1802037f9  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x1802037fe  movups  xmm0, xmmword ptr [rax]
0x180203801  movups  xmmword ptr [rbp+2A0h+S], xmm0
0x180203808  movups  xmm1, xmmword ptr [rax+10h]
0x18020380c  movups  [rbp+2A0h+var_C0], xmm1
0x180203813  mov     [rax], r13w
0x180203817  mov     [rax+10h], r13
0x18020381b  mov     qword ptr [rax+18h], 7
0x180203823  lea     rdx, [rbp+2A0h+S]
0x18020382a  lea     rcx, [rbp+2A0h+var_F0]
0x180203831  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180203836  lea     rcx, [rbp+2A0h+S]
0x18020383d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180203842  nop
0x180203843  lea     rcx, [rbp+2A0h+var_70]
0x18020384a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18020384f  jmp     short loc_180203864
0x180203851  lea     rdx, [rbp+2A0h+var_90]
0x180203858  lea     rcx, [rbp+2A0h+var_F0]
0x18020385f  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180203864  lea     rcx, [rbp+2A0h+var_90]
0x18020386b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180203870  lea     r9, [rbp+2A0h+var_46]
0x180203877  sub     r9, 2
0x18020387b  mov     eax, 0CCCCCCCDh
0x180203880  mul     edi
0x180203882  shr     edx, 3
0x180203885  movzx   eax, dx
0x180203888  shl     ax, 2
0x18020388c  lea     ecx, [rax+rdx]
0x18020388f  add     cx, cx
0x180203892  sub     di, cx
0x180203895  add     di, 30h ; '0'
0x180203899  mov     [r9], di
0x18020389d  mov     edi, edx
0x18020389f  test    edx, edx
0x1802038a1  jnz     short loc_180203877
0x1802038a3  lea     r8, [rbp+2A0h+var_46]
0x1802038aa  mov     rdx, r9
0x1802038ad  lea     rcx, [rbp+2A0h+var_B0]
0x1802038b4  call    ??$?0PEA_W$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEA_W0AEBV?$allocator@_W@1@@Z; std::wstring::wstring(wchar_t *,wchar_t *,std::allocator<wchar_t> const &)
0x1802038b9  lea     rax, [rbp+2A0h+var_F0]
0x1802038c0  cmp     qword ptr [rbp+2A0h+var_E0+8], 7
0x1802038c8  cmova   rax, qword ptr [rbp+2A0h+var_F0]
0x1802038d0  mov     [rsp+3A0h+var_350], rax
0x1802038d5  lea     rax, [rbp+2A0h+var_B0]
0x1802038dc  cmp     [rbp+2A0h+var_98], 7
0x1802038e4  cmova   rax, [rbp+2A0h+var_B0]
0x1802038ec  mov     [rsp+3A0h+var_348], rax
0x1802038f1  mov     rbx, [rsp+3A0h+var_360]
0x1802038f6  mov     [rsp+3A0h+var_340], rbx
0x1802038fb  mov     [rsp+3A0h+var_338], r13w
0x180203901  xor     edx, edx; Val
0x180203903  mov     r8d, 206h; Size
0x180203909  lea     rcx, [rsp+3A0h+var_336]; void *
0x18020390e  call    memset_0
0x180203913  xorps   xmm0, xmm0
0x180203916  movups  [rbp+2A0h+var_130], xmm0
0x18020391d  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180203925  movdqa  [rbp+2A0h+var_120], xmm1
0x18020392d  mov     word ptr [rbp+2A0h+var_130], r13w
0x180203935  mov     [rbp+2A0h+var_100], r13d
0x18020393c  mov     [rbp+2A0h+var_FB], r13w
0x180203944  mov     [rbp+2A0h+var_F8], 100h
0x18020394e  mov     [rbp+2A0h+var_F4], r13w
0x180203956  lea     rax, [rsp+3A0h+var_350]
0x18020395b  mov     [rbp+2A0h+var_108], rax
0x180203962  mov     [rbp+2A0h+var_110], 2
0x18020396c  mov     [rbp+2A0h+var_FC], r15b
0x180203973  mov     [rbp+2A0h+var_F9], r15b
0x18020397a  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x180203981  call    cs:__imp_GetModuleHandleW
0x180203987  mov     rcx, rax; hModule
0x18020398a  lea     rdx, aIsusercetavail; "IsUserCetAvailableInEnvironment"
0x180203991  call    cs:__imp_GetProcAddress
0x180203997  test    rax, rax
0x18020399a  jz      short loc_1802039B7
0x18020399c  xor     ecx, ecx
0x18020399e  call    cs:__guard_dispatch_icall_fptr
0x1802039a4  movzx   ecx, byte ptr [rbp+2A0h+var_F4]
0x1802039ab  test    eax, eax
0x1802039ad  cmovnz  ecx, r15d
0x1802039b1  mov     byte ptr [rbp+2A0h+var_F4], cl
0x1802039b7  call    cs:__imp_?GetAPI@Gimme@Mso@@YAPEAUIGimme@12@XZ; Mso::Gimme::GetAPI(void)
0x1802039bd  mov     r10, rax
0x1802039c0  mov     rcx, [rax]
0x1802039c3  mov     rax, [rcx+18h]
0x1802039c7  mov     [rsp+3A0h+var_370], 0F1Fh
0x1802039cf  mov     [rsp+3A0h+var_378], 104h
0x1802039d7  lea     rcx, [rsp+3A0h+var_338]
0x1802039dc  mov     [rsp+3A0h+var_380], rcx
0x1802039e1  xor     r9d, r9d
0x1802039e4  xor     r8d, r8d
0x1802039e7  mov     edx, 11Ch
0x1802039ec  mov     rcx, r10
0x1802039ef  call    cs:__guard_dispatch_icall_fptr
0x1802039f5  test    al, al
0x1802039f7  jnz     short loc_180203A2E
0x1802039f9  mov     [rsi], r13
0x1802039fc  lea     rcx, [rbp+2A0h+var_130]
0x180203a03  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180203a08  lea     rcx, [rbp+2A0h+var_B0]
0x180203a0f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180203a14  lea     rcx, [rbp+2A0h+var_F0]
0x180203a1b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180203a20  test    rbx, rbx
0x180203a23  jz      loc_180203B38
0x180203a29  jmp     loc_180203B28
0x180203a2e  call    cs:__imp_?LrGetBroker@@YAAEAUILrBroker@LowRights@@XZ; LrGetBroker(void)
0x180203a34  mov     r8, rax
0x180203a37  mov     rcx, [rax]
0x180203a3a  mov     rax, [rcx]
0x180203a3d  lea     rdx, [rsp+3A0h+var_340]
0x180203a42  mov     rcx, r8
0x180203a45  call    cs:__guard_dispatch_icall_fptr
0x180203a4b  test    al, al
0x180203a4d  jnz     short loc_180203A8B
0x180203a4f  mov     [rsi], r13
0x180203a52  lea     rcx, [rbp+2A0h+var_130]
0x180203a59  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180203a5e  lea     rcx, [rbp+2A0h+var_B0]
0x180203a65  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180203a6a  lea     rcx, [rbp+2A0h+var_F0]
0x180203a71  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180203a76  test    rbx, rbx
0x180203a79  jz      loc_180203B38
0x180203a7f  mov     rcx, [rbx]
0x180203a82  mov     rax, [rcx+8]
0x180203a86  jmp     loc_180203B2F
0x180203a8b  test    rbx, rbx
0x180203a8e  jnz     short loc_180203A9E
0x180203a90  xor     edx, edx
0x180203a92  mov     ecx, 1E3C3840h
0x180203a97  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180203a9d  nop
0x180203a9e  lea     rcx, [rbx+8]
0x180203aa2  cmp     [rcx], r13
0x180203aa5  jnz     short loc_180203AAC
0x180203aa7  mov     eax, r13d
0x180203aaa  jmp     short loc_180203AC4
0x180203aac  call    ??C?$TCntPtr@UIWICImagingFactory@@@Mso@@QEBAPEAUIWICImagingFactory@@XZ; Mso::TCntPtr<IWICImagingFactory>::operator->(void)
0x180203ab1  mov     r8, rax
0x180203ab4  mov     rcx, [rax]
0x180203ab7  mov     rax, [rcx+10h]
0x180203abb  mov     rcx, r8
0x180203abe  call    cs:__guard_dispatch_icall_fptr
0x180203ac4  mov     r8d, eax; dwProcessId
0x180203ac7  mov     edx, r15d; bInheritHandle
0x180203aca  mov     ecx, 100000h; dwDesiredAccess
0x180203acf  call    cs:__imp_OpenProcess
0x180203ad5  mov     rdi, rax
0x180203ad8  test    rax, rax
0x180203adb  jnz     short loc_180203AE2
0x180203add  mov     [rsi], r13
0x180203ae0  jmp     short loc_180203B03
0x180203ae2  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180203ae5  mov     rcx, rdi; hHandle
0x180203ae8  call    cs:__imp_WaitForSingleObject
0x180203aee  mov     rdx, rsi
0x180203af1  mov     rcx, rbx
0x180203af4  call    ?GetOutputStream@CTranscoderProxy@Transcoder@@QEAA?AV?$TCntPtr@UIStream@@@Mso@@XZ; Transcoder::CTranscoderProxy::GetOutputStream(void)
0x180203af9  mov     rcx, rdi; hObject
0x180203afc  call    cs:__imp_CloseHandle
0x180203b02  nop
0x180203b03  lea     rcx, [rbp+2A0h+var_130]
0x180203b0a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180203b0f  lea     rcx, [rbp+2A0h+var_B0]
0x180203b16  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180203b1b  lea     rcx, [rbp+2A0h+var_F0]
0x180203b22  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180203b27  nop
0x180203b28  mov     rax, [rbx]
0x180203b2b  mov     rax, [rax+8]
0x180203b2f  mov     rcx, rbx
0x180203b32  call    cs:__guard_dispatch_icall_fptr
0x180203b38  mov     rax, rsi
0x180203b3b  mov     rcx, [rbp+2A0h+var_40]
0x180203b42  xor     rcx, rsp; StackCookie
0x180203b45  call    __security_check_cookie
0x180203b4a  mov     rbx, [rsp+3A0h+arg_10]
0x180203b52  add     rsp, 370h
0x180203b59  pop     r15
0x180203b5b  pop     r14
0x180203b5d  pop     r13
0x180203b5f  pop     r12
0x180203b61  pop     rdi
0x180203b62  pop     rsi
0x180203b63  pop     rbp
0x180203b64  retn
```
