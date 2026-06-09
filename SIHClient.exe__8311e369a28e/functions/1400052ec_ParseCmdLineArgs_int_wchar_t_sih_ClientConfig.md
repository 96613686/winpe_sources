# ParseCmdLineArgs(int,wchar_t * *,sih::ClientConfig *)

- ea: `0x1400052ec`
- end: `0x1400057da`
- name: `?ParseCmdLineArgs@@YAJHPEAPEA_WPEAUClientConfig@sih@@@Z`
- size: `1262`
- prototype: `__int64 __fastcall(int, wchar_t **, struct sih::ClientConfig *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400057e0`

## callees

- `0x140003de4`
- `0x1400052ec`
- `0x140005f98`
- `0x140006804`
- `0x140006e74`
- `0x1400071c0`
- `0x1400072b4`
- `0x1400073f0`
- `0x1400154b4`
- `0x140017934`
- `0x140018394`
- `0x140023b30`
- `0x140045ad4`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400056d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400056d9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400056c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400056c4`

## string_xrefs

- `0x14000540e`: `/commit`
- `0x14000549c`: `/commit`
- `0x140005749`: `StateSeparation tasks expect no arguments.`
- `0x1400056bd`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall ParseCmdLineArgs(int a1, wchar_t **a2, struct sih::ClientConfig *a3)
{
  wchar_t **v4; // rdi
  unsigned int v5; // ebx
  unsigned int v6; // esi
  __int64 i; // r15
  wchar_t *v9; // rdx
  __int64 v10; // r8
  wchar_t **v11; // r12
  wchar_t **v12; // rcx
  wchar_t **v13; // r13
  wchar_t **v14; // rdi
  signed __int64 v15; // r12
  const wchar_t *v16; // rcx
  const wchar_t *v17; // rcx
  const wchar_t *v18; // rcx
  char v19; // r13
  const wchar_t *v20; // rcx
  const wchar_t *v21; // rcx
  const wchar_t *v22; // rcx
  const wchar_t *v23; // rcx
  const wchar_t *v24; // rcx
  const wchar_t *v25; // rcx
  int v26; // r8d
  __int64 v27; // r15
  wchar_t *v28; // rdx
  __int64 v29; // r8
  void *v30; // rax
  const wchar_t *v31; // rax
  char v32; // di
  HMODULE ModuleHandleW; // rax
  bool v34; // cl
  __int64 RegKeyPath; // rax
  __int64 v36; // rcx
  __int64 v37; // [rsp+20h] [rbp-99h]
  char v38; // [rsp+41h] [rbp-78h]
  __int64 v40; // [rsp+50h] [rbp-69h]
  _BYTE v41[32]; // [rsp+58h] [rbp-61h] BYREF
  wchar_t *S1[2]; // [rsp+78h] [rbp-41h] BYREF
  size_t N[2]; // [rsp+88h] [rbp-31h]
  void *Src[2]; // [rsp+98h] [rbp-21h] BYREF
  _OWORD v45[2]; // [rsp+B8h] [rbp-1h] BYREF

  v4 = a2;
  v5 = 0;
  v6 = 0;
  v38 = 0;
  if ( !a2 || !a3 )
    goto LABEL_81;
  if ( a1 == 1 )
    return 0;
  if ( a1 <= 1 )
    goto LABEL_79;
  v40 = a1;
  for ( i = 1; i < v40; ++i )
  {
    v9 = v4[i];
    *(_OWORD *)S1 = 0;
    *(_OWORD *)N = 0;
    v10 = -1;
    do
      ++v10;
    while ( v9[v10] );
    std::wstring::_Construct<1,wchar_t const *>(S1);
    v11 = S1;
    if ( N[1] > 7 )
      v11 = (wchar_t **)S1[0];
    v12 = S1;
    if ( N[1] > 7 )
      v12 = (wchar_t **)S1[0];
    v13 = (wchar_t **)((char *)v12 + 2 * N[0]);
    v14 = S1;
    if ( N[1] > 7 )
      v14 = (wchar_t **)S1[0];
    if ( v14 != v13 )
    {
      v15 = (char *)v11 - (char *)v14;
      do
      {
        *(_WORD *)((char *)v14 + v15) = o_towlower_0(*(unsigned __int16 *)v14);
        v14 = (wchar_t **)((char *)v14 + 2);
      }
      while ( v14 != v13 );
    }
    v16 = (const wchar_t *)S1;
    if ( N[1] > 7 )
      v16 = S1[0];
    if ( N[0] == 15 && !wmemcmp(v16, L"/managerebootui", 0xFu) )
      goto LABEL_30;
    v17 = (const wchar_t *)S1;
    if ( N[1] > 7 )
      v17 = S1[0];
    if ( N[0] == 7 && !wmemcmp(v17, L"/commit", 7u) )
      goto LABEL_30;
    v18 = (const wchar_t *)S1;
    if ( N[1] > 7 )
      v18 = S1[0];
    if ( N[0] == 11 && !wmemcmp(v18, L"/postreboot", 0xBu) )
    {
LABEL_30:
      ++v6;
      v19 = 1;
      v38 = 1;
      v20 = (const wchar_t *)S1;
      if ( N[1] > 7 )
        v20 = S1[0];
      if ( N[0] == 15 && !wmemcmp(v20, L"/managerebootui", 0xFu) )
      {
        *(_DWORD *)a3 = 3;
      }
      else
      {
        v21 = (const wchar_t *)S1;
        if ( N[1] > 7 )
          v21 = S1[0];
        if ( N[0] == 7 && !wmemcmp(v21, L"/commit", 7u) )
        {
          *(_DWORD *)a3 = 2;
        }
        else
        {
          v22 = (const wchar_t *)S1;
          if ( N[1] > 7 )
            v22 = S1[0];
          if ( N[0] == 11 && !wmemcmp(v22, L"/postreboot", 0xBu) )
            *(_DWORD *)a3 = 4;
        }
      }
    }
    else
    {
      v19 = v38;
    }
    v23 = (const wchar_t *)S1;
    if ( N[1] > 7 )
      v23 = S1[0];
    if ( N[0] == 5 && !wmemcmp(v23, L"/boot", 5u) )
    {
      ++v6;
      *(_DWORD *)a3 = 0;
    }
    v24 = (const wchar_t *)S1;
    if ( N[1] > 7 )
      v24 = S1[0];
    if ( N[0] == 14 && !wmemcmp(v24, L"/boot-periodic", 0xEu) )
    {
      ++v6;
      *(_DWORD *)a3 = 1;
    }
    v25 = (const wchar_t *)S1;
    if ( N[1] > 7 )
      v25 = S1[0];
    if ( N[0] == 3 && !wmemcmp(v25, L"/cv", 3u) )
    {
      v27 = i + 1;
      if ( v27 >= v40 )
      {
        v5 = -2147024809;
      }
      else
      {
        WUTrace(0, 0, 0x400000, (unsigned int)(v26 + 1), 0, L"cV = %ws");
        v28 = a2[v27];
        memset(v45, 0, sizeof(v45));
        v29 = -1;
        do
          ++v29;
        while ( v28[v29] );
        std::wstring::_Construct<1,wchar_t const *>(v45);
        v30 = (void *)std::wstring::wstring(v41, v45);
        sih::utils::VerifyCV(Src, v30);
        v5 = -2147024809;
        std::string::~string(Src);
        std::wstring::~wstring(v45);
      }
      std::wstring::~wstring(S1);
      goto LABEL_82;
    }
    v4 = a2;
    std::wstring::~wstring(S1);
  }
  if ( v6 > 1 )
  {
    v31 = L"Multiple actions in the cmd, each should be mutual exclusive.";
    goto LABEL_80;
  }
  if ( !v6 )
  {
LABEL_79:
    v31 = L"Unsupported action in the cmd.";
LABEL_80:
    WUTrace(0, 0, 0x400000, 1, 0, v31);
LABEL_81:
    v5 = -2147024809;
LABEL_82:
    LODWORD(v37) = v5;
    WUTrace("ParseCmdLineArgs", 693, 0x400000, 1, v37, L"mode (%d)");
    return v5;
  }
  if ( v19 )
  {
    v32 = 0;
    ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
    if ( ModuleHandleW )
      GetProcAddress(ModuleHandleW, "RtlIsStateSeparationEnabled");
    if ( (unsigned int)AreTestKeysAllowed(v34) )
    {
      RegKeyPath = GetRegKeyPath(29);
      if ( (unsigned int)RegQueryDwordValueWithDefaultAndRangeCheck(v36, RegKeyPath, L"IsStateSeparationEnabled", 0) )
      {
        v32 = 1;
        WUTrace(0, 0, 0x400000, 4, 0, L"IsStateSeparationEnabled (testoverride).");
      }
    }
    if ( !v32 )
    {
      v5 = -2145103598;
      goto LABEL_82;
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1400052ec  mov     [rsp-8+arg_0], rbx
0x1400052f1  push    rbp
0x1400052f2  push    rsi
0x1400052f3  push    rdi
0x1400052f4  push    r12
0x1400052f6  push    r13
0x1400052f8  push    r14
0x1400052fa  push    r15
0x1400052fc  lea     rbp, [rsp-27h]
0x140005301  sub     rsp, 0E0h
0x140005308  mov     rax, cs:__security_cookie
0x14000530f  xor     rax, rsp
0x140005312  mov     [rbp+57h+var_38], rax
0x140005316  mov     r14, r8
0x140005319  mov     rdi, rdx
0x14000531c  mov     [rbp+57h+var_C8], rdx
0x140005320  xor     ebx, ebx
0x140005322  mov     esi, ebx
0x140005324  mov     [rbp+57h+var_D0], bl
0x140005327  mov     [rbp+57h+var_CF], bl
0x14000532a  test    rdx, rdx
0x14000532d  jz      loc_140005778
0x140005333  test    r8, r8
0x140005336  jz      loc_140005778
0x14000533c  cmp     ecx, 1
0x14000533f  jnz     short loc_140005348
0x140005341  xor     eax, eax
0x140005343  jmp     loc_1400057B3
0x140005348  jle     loc_140005752
0x14000534e  movsxd  rax, ecx
0x140005351  mov     [rbp+57h+var_C0], rax
0x140005355  mov     r15d, 1
0x14000535b  mov     rdx, [rdi+r15*8]
0x14000535f  xorps   xmm0, xmm0
0x140005362  movups  xmmword ptr [rbp+57h+S1], xmm0
0x140005366  xorps   xmm1, xmm1
0x140005369  movdqu  xmmword ptr [rbp+57h+N], xmm1
0x14000536e  or      r8, 0FFFFFFFFFFFFFFFFh
0x140005372  inc     r8
0x140005375  cmp     [rdx+r8*2], bx
0x14000537a  jnz     short loc_140005372
0x14000537c  lea     rcx, [rbp+57h+S1]
0x140005380  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140005385  lea     r12, [rbp+57h+S1]
0x140005389  mov     r8, [rbp+57h+S1]
0x14000538d  cmp     [rbp+57h+N+8], 7
0x140005392  cmova   r12, r8
0x140005396  lea     rcx, [rbp+57h+S1]
0x14000539a  cmova   rcx, r8
0x14000539e  mov     rax, [rbp+57h+N]
0x1400053a2  lea     r13, [rcx+rax*2]
0x1400053a6  lea     rdi, [rbp+57h+S1]
0x1400053aa  cmova   rdi, r8
0x1400053ae  cmp     rdi, r13
0x1400053b1  jz      short loc_1400053CC
0x1400053b3  sub     r12, rdi
0x1400053b6  movzx   ecx, word ptr [rdi]
0x1400053b9  call    _o_towlower_0
0x1400053be  mov     [rdi+r12], ax
0x1400053c3  add     rdi, 2
0x1400053c7  cmp     rdi, r13
0x1400053ca  jnz     short loc_1400053B6
0x1400053cc  mov     r8, [rbp+57h+N]; N
0x1400053d0  lea     rcx, [rbp+57h+S1]
0x1400053d4  mov     edi, 7
0x1400053d9  cmp     [rbp+57h+N+8], rdi
0x1400053dd  cmova   rcx, [rbp+57h+S1]; S1
0x1400053e2  cmp     r8, 0Fh
0x1400053e6  jnz     short loc_1400053F8
0x1400053e8  lea     rdx, aManagerebootui; "/managerebootui"
0x1400053ef  call    wmemcmp
0x1400053f4  test    eax, eax
0x1400053f6  jz      short loc_14000544D
0x1400053f8  mov     r8, [rbp+57h+N]; N
0x1400053fc  lea     rcx, [rbp+57h+S1]
0x140005400  cmp     [rbp+57h+N+8], rdi
0x140005404  cmova   rcx, [rbp+57h+S1]; S1
0x140005409  cmp     r8, rdi
0x14000540c  jnz     short loc_14000541E
0x14000540e  lea     rdx, aCommit; "/commit"
0x140005415  call    wmemcmp
0x14000541a  test    eax, eax
0x14000541c  jz      short loc_14000544D
0x14000541e  mov     r8, [rbp+57h+N]; N
0x140005422  lea     rcx, [rbp+57h+S1]
0x140005426  cmp     [rbp+57h+N+8], rdi
0x14000542a  cmova   rcx, [rbp+57h+S1]; S1
0x14000542f  cmp     r8, 0Bh
0x140005433  jnz     loc_1400054E5
0x140005439  lea     rdx, aPostreboot; "/postreboot"
0x140005440  call    wmemcmp
0x140005445  test    eax, eax
0x140005447  jnz     loc_1400054E5
0x14000544d  inc     esi
0x14000544f  mov     r13b, 1
0x140005452  mov     [rbp+57h+var_CF], r13b
0x140005456  mov     r8, [rbp+57h+N]; N
0x14000545a  lea     rcx, [rbp+57h+S1]
0x14000545e  cmp     [rbp+57h+N+8], rdi
0x140005462  cmova   rcx, [rbp+57h+S1]; S1
0x140005467  cmp     r8, 0Fh
0x14000546b  jnz     short loc_140005486
0x14000546d  lea     rdx, aManagerebootui; "/managerebootui"
0x140005474  call    wmemcmp
0x140005479  test    eax, eax
0x14000547b  jnz     short loc_140005486
0x14000547d  mov     dword ptr [r14], 3
0x140005484  jmp     short loc_1400054E9
0x140005486  mov     r8, [rbp+57h+N]; N
0x14000548a  lea     rcx, [rbp+57h+S1]
0x14000548e  cmp     [rbp+57h+N+8], rdi
0x140005492  cmova   rcx, [rbp+57h+S1]; S1
0x140005497  cmp     r8, rdi
0x14000549a  jnz     short loc_1400054B5
0x14000549c  lea     rdx, aCommit; "/commit"
0x1400054a3  call    wmemcmp
0x1400054a8  test    eax, eax
0x1400054aa  jnz     short loc_1400054B5
0x1400054ac  mov     dword ptr [r14], 2
0x1400054b3  jmp     short loc_1400054E9
0x1400054b5  mov     r8, [rbp+57h+N]; N
0x1400054b9  lea     rcx, [rbp+57h+S1]
0x1400054bd  cmp     [rbp+57h+N+8], rdi
0x1400054c1  cmova   rcx, [rbp+57h+S1]; S1
0x1400054c6  cmp     r8, 0Bh
0x1400054ca  jnz     short loc_1400054E9
0x1400054cc  lea     rdx, aPostreboot; "/postreboot"
0x1400054d3  call    wmemcmp
0x1400054d8  test    eax, eax
0x1400054da  jnz     short loc_1400054E9
0x1400054dc  mov     dword ptr [r14], 4
0x1400054e3  jmp     short loc_1400054E9
0x1400054e5  mov     r13b, [rbp+57h+var_CF]
0x1400054e9  mov     r8, [rbp+57h+N]; N
0x1400054ed  lea     rcx, [rbp+57h+S1]
0x1400054f1  cmp     [rbp+57h+N+8], rdi
0x1400054f5  cmova   rcx, [rbp+57h+S1]; S1
0x1400054fa  cmp     r8, 5
0x1400054fe  jnz     short loc_140005515
0x140005500  lea     rdx, aBoot; "/boot"
0x140005507  call    wmemcmp
0x14000550c  test    eax, eax
0x14000550e  jnz     short loc_140005515
0x140005510  inc     esi
0x140005512  mov     [r14], ebx
0x140005515  mov     r8, [rbp+57h+N]; N
0x140005519  lea     rcx, [rbp+57h+S1]
0x14000551d  cmp     [rbp+57h+N+8], rdi
0x140005521  cmova   rcx, [rbp+57h+S1]; S1
0x140005526  cmp     r8, 0Eh
0x14000552a  jnz     short loc_140005545
0x14000552c  lea     rdx, aBootPeriodic; "/boot-periodic"
0x140005533  call    wmemcmp
0x140005538  test    eax, eax
0x14000553a  jnz     short loc_140005545
0x14000553c  inc     esi
0x14000553e  mov     dword ptr [r14], 1
0x140005545  mov     r8, [rbp+57h+N]; N
0x140005549  lea     rcx, [rbp+57h+S1]
0x14000554d  cmp     [rbp+57h+N+8], rdi
0x140005551  cmova   rcx, [rbp+57h+S1]; S1
0x140005556  cmp     r8, 3
0x14000555a  jnz     loc_140005649
0x140005560  lea     rdx, aCv; "/cv"
0x140005567  call    wmemcmp
0x14000556c  test    eax, eax
0x14000556e  jnz     loc_140005649
0x140005574  inc     r15
0x140005577  cmp     r15, [rbp+57h+var_C0]
0x14000557b  jge     loc_14000569D
0x140005581  cmp     [rbp+57h+var_D0], bl
0x140005584  jnz     loc_14000569D
0x14000558a  mov     r12b, 1
0x14000558d  mov     [rbp+57h+var_D0], r12b
0x140005591  mov     rdi, [rbp+57h+var_C8]
0x140005595  mov     rax, [rdi+r15*8]
0x140005599  mov     [rsp+110h+var_E0], rax
0x14000559e  lea     rax, aCvWs; "cV = %ws"
0x1400055a5  mov     [rsp+110h+var_E8], rax
0x1400055aa  mov     [rsp+110h+var_F0], rbx
0x1400055af  xor     edx, edx
0x1400055b1  xor     ecx, ecx
0x1400055b3  lea     r9d, [r8+1]
0x1400055b7  mov     r8d, 400000h
0x1400055bd  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1400055c2  mov     [rbp+57h+var_CE], bl
0x1400055c5  mov     rdx, [rdi+r15*8]
0x1400055c9  xorps   xmm0, xmm0
0x1400055cc  movups  [rbp+57h+var_58], xmm0
0x1400055d0  xorps   xmm1, xmm1
0x1400055d3  movdqu  [rbp+57h+var_48], xmm1
0x1400055d8  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400055dc  inc     r8
0x1400055df  cmp     [rdx+r8*2], bx
0x1400055e4  jnz     short loc_1400055DC
0x1400055e6  lea     rcx, [rbp+57h+var_58]
0x1400055ea  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400055ef  lea     rdx, [rbp+57h+var_58]
0x1400055f3  lea     rcx, [rbp+57h+var_B8]
0x1400055f7  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1400055fc  mov     rdx, rax; void *
0x1400055ff  lea     r8, [rbp+57h+var_CE]
0x140005603  lea     rcx, [rbp+57h+Src]; Src
0x140005607  call    ?VerifyCV@utils@sih@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@4@PEA_N@Z; sih::utils::VerifyCV(std::wstring,bool *)
0x14000560c  cmp     [rbp+57h+var_CE], bl
0x14000560f  jz      short loc_140005678
0x140005611  lea     rcx, [r14+8]; void *
0x140005615  lea     rax, [rbp+57h+Src]
0x140005619  cmp     rcx, rax
0x14000561c  jz      short loc_140005635
0x14000561e  lea     rdx, [rbp+57h+Src]
0x140005622  cmp     [rbp+57h+var_60], 0Fh
0x140005627  cmova   rdx, [rbp+57h+Src]; Src
0x14000562c  mov     r8, [rbp+57h+Size]; Size
0x140005630  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x140005635  lea     rcx, [rbp+57h+Src]
0x140005639  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14000563e  lea     rcx, [rbp+57h+var_58]; void *
0x140005642  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140005647  jmp     short loc_140005651
0x140005649  mov     rdi, [rbp+57h+var_C8]
0x14000564d  mov     r12b, [rbp+57h+var_D0]
0x140005651  lea     rcx, [rbp+57h+S1]; void *
0x140005655  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000565a  inc     r15
0x14000565d  cmp     r15, [rbp+57h+var_C0]
0x140005661  jl      loc_14000535B
0x140005667  cmp     esi, 1
0x14000566a  jbe     short loc_1400056A4
0x14000566c  lea     rax, aMultipleAction; "Multiple actions in the cmd, each shoul"...
0x140005673  jmp     loc_140005759
0x140005678  mov     ebx, 80070057h
0x14000567d  lea     rcx, [rbp+57h+Src]
0x140005681  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140005686  lea     rcx, [rbp+57h+var_58]; void *
0x14000568a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000568f  lea     rcx, [rbp+57h+S1]; void *
0x140005693  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140005698  jmp     loc_14000577D
0x14000569d  mov     ebx, 80070057h
0x1400056a2  jmp     short loc_14000568F
0x1400056a4  test    esi, esi
0x1400056a6  jnz     short loc_1400056B1
0x1400056a8  test    r12b, r12b
0x1400056ab  jz      loc_140005752
0x1400056b1  test    r13b, r13b
0x1400056b4  jz      loc_1400057B1
0x1400056ba  mov     dil, bl
0x1400056bd  lea     rcx, ModuleName; "ntdll.dll"
0x1400056c4  call    cs:__imp_GetModuleHandleW
0x1400056ca  test    rax, rax
0x1400056cd  jz      short loc_1400056DF
0x1400056cf  lea     rdx, aRtlisstatesepa; "RtlIsStateSeparationEnabled"
0x1400056d6  mov     rcx, rax; hModule
0x1400056d9  call    cs:__imp_GetProcAddress
0x1400056df  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x1400056e4  test    eax, eax
0x1400056e6  jz      short loc_140005738
0x1400056e8  mov     ecx, 1Dh
0x1400056ed  call    ?GetRegKeyPath@@YAPEB_WW4WURegKey@RegUtil@@@Z; GetRegKeyPath(RegUtil::WURegKey)
0x1400056f2  mov     dword ptr [rsp+110h+var_E8], 0FFFFFFFFh
0x1400056fa  xor     r9d, r9d
0x1400056fd  lea     r8, aIsstateseparat_0; "IsStateSeparationEnabled"
0x140005704  mov     rdx, rax
0x140005707  call    ?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z; RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)
0x14000570c  test    eax, eax
0x14000570e  jz      short loc_140005738
0x140005710  mov     dil, 1
0x140005713  lea     rax, aIsstateseparat; "IsStateSeparationEnabled (testoverride)"...
0x14000571a  mov     [rsp+110h+var_E8], rax
0x14000571f  mov     [rsp+110h+var_F0], rbx
0x140005724  xor     edx, edx
0x140005726  xor     ecx, ecx
0x140005728  lea     r9d, [rdx+4]
0x14000572c  mov     r8d, 400000h
0x140005732  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140005737  nop
0x140005738  test    dil, dil
0x14000573b  jnz     short loc_140005744
0x14000573d  mov     ebx, 80245112h
0x140005742  jmp     short loc_14000577D
0x140005744  test    r12b, r12b
0x140005747  jz      short loc_1400057B1
0x140005749  lea     rax, aStateseparatio; "StateSeparation tasks expect no argumen"...
0x140005750  jmp     short loc_140005759
0x140005752  lea     rax, aUnsupportedAct; "Unsupported action in the cmd."
0x140005759  mov     [rsp+110h+var_E8], rax
0x14000575e  mov     [rsp+110h+var_F0], rbx
0x140005763  mov     r9d, 1
0x140005769  mov     r8d, 400000h
0x14000576f  xor     edx, edx
0x140005771  xor     ecx, ecx
0x140005773  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140005778  mov     ebx, 80070057h
0x14000577d  mov     ecx, [r14]
0x140005780  mov     dword ptr [rsp+110h+var_E0], ecx
0x140005784  lea     rax, aModeD; "mode (%d)"
0x14000578b  mov     [rsp+110h+var_E8], rax
0x140005790  mov     dword ptr [rsp+110h+var_F0], ebx
0x140005794  mov     edx, 2B5h
  ... truncated ...
```
