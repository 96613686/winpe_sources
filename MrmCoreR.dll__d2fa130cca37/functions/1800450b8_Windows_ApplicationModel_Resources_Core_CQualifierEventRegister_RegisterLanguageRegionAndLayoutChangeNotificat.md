# Windows::ApplicationModel::Resources::Core::CQualifierEventRegister::RegisterLanguageRegionAndLayoutChangeNotification(void)

- ea: `0x1800450b8`
- end: `0x180045481`
- name: `?RegisterLanguageRegionAndLayoutChangeNotification@CQualifierEventRegister@Core@Resources@ApplicationModel@Windows@@QEAAJXZ`
- size: `969`
- prototype: `__int64 __fastcall(Windows::ApplicationModel::Resources::Core::CQualifierEventRegister *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180044ce0`

## callees

- `0x180017960`
- `0x18002c8d0`
- `0x18002cfd0`
- `0x180035110`
- `0x1800450b8`
- `0x1800455c8`
- `0x1800862f0`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180045128`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180045128`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045437`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045463`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045437`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045463`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800451ec`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800451ec`
- `bcp47mrm!GetApplicationLayoutDirection` at `0x180045218`
- `bcp47mrm!GetApplicationLayoutDirection` at `0x180045218`
- `api-ms-win-core-com-l1-1-0!CoIncrementMTAUsage` at `0x1800451ce`
- `api-ms-win-core-com-l1-1-0!CoIncrementMTAUsage` at `0x1800451ce`

## pseudocode

```c
__int64 __fastcall Windows::ApplicationModel::Resources::Core::CQualifierEventRegister::RegisterLanguageRegionAndLayoutChangeNotification(
        Windows::ApplicationModel::Resources::Core::CQualifierEventRegister *this)
{
  __int64 v2; // rcx
  signed int v3; // ebx
  HANDLE EventW; // rax
  __int64 v5; // r8
  _BYTE *v6; // rax
  __int64 v7; // r14
  __int64 v8; // rcx
  __int64 v9; // rsi
  __int64 v10; // r15
  __int64 v11; // rdx
  _BYTE *v12; // rax
  HANDLE Thread; // rax
  __int64 v15; // r8
  int v16; // eax
  __int64 v17; // r11
  _WORD *v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rcx
  __int64 v21; // r9
  __int64 v22; // rdx
  __int64 v23; // rdx
  int Length; // eax
  __int64 v25; // r11
  _WORD *v26; // rax
  __int64 v27; // r9
  __int64 v28; // rdx
  signed int LastError; // eax
  signed int v30; // eax
  DWORD dwCreationFlags; // [rsp+20h] [rbp-E0h]
  __int64 v32; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE *v33; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v34[32]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v35[176]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v2 = *((_QWORD *)this + 9);
  if ( v2 && (*(unsigned __int8 (__fastcall **)(__int64, const WCHAR *))(*(_QWORD *)v2 + 344LL))(v2, L"Language") )
  {
    v3 = 0;
    if ( *((_QWORD *)this + 5) != -1 )
    {
LABEL_15:
      if ( *((_DWORD *)this + 7) == -1 )
      {
        LODWORD(v32) = -1;
        GetApplicationLayoutDirection(0, &v32);
        *((_DWORD *)this + 7) = v32;
      }
      return (unsigned int)v3;
    }
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 5) = EventW;
    if ( EventW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      if ( v3 < 0 )
      {
LABEL_13:
        wil::details::unique_storage<wil::details::resource_policy<CO_MTA_USAGE_COOKIE__ *,long (*)(CO_MTA_USAGE_COOKIE__ *),&long CoDecrementMTAUsage(CO_MTA_USAGE_COOKIE__ *),wistd::integral_constant<unsigned __int64,0>,CO_MTA_USAGE_COOKIE__ *,CO_MTA_USAGE_COOKIE__ *,0,std::nullptr_t>>::reset(
          this,
          0);
        CoIncrementMTAUsage(this);
        Thread = CreateThread(
                   0,
                   0,
                   (LPTHREAD_START_ROUTINE)Windows::ApplicationModel::Resources::Core::LanguageChangeNotifyThreadProc,
                   this,
                   0,
                   0);
        *((_QWORD *)this + 4) = Thread;
        if ( !Thread )
        {
          wil::details::unique_storage<wil::details::resource_policy<CO_MTA_USAGE_COOKIE__ *,long (*)(CO_MTA_USAGE_COOKIE__ *),&long CoDecrementMTAUsage(CO_MTA_USAGE_COOKIE__ *),wistd::integral_constant<unsigned __int64,0>,CO_MTA_USAGE_COOKIE__ *,CO_MTA_USAGE_COOKIE__ *,0,std::nullptr_t>>::reset(
            this,
            0);
          v30 = GetLastError();
          v3 = v30;
          if ( v30 > 0 )
            v3 = (unsigned __int16)v30 | 0x80070000;
        }
        if ( v3 < 0 )
          return (unsigned int)v3;
        goto LABEL_15;
      }
    }
    v5 = *((_QWORD *)this + 8);
    v6 = v35;
    v7 = 172;
    v8 = 172;
    do
    {
      *v6++ = 0;
      --v8;
    }
    while ( v8 );
    v9 = 86;
    v10 = 2147483646;
    if ( !*(_BYTE *)(v5 + 8) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x117,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\ccontext.cpp",
        (const char *)0x80070015LL,
        dwCreationFlags);
LABEL_9:
      v11 = *((_QWORD *)this + 8);
      v12 = v35;
      do
      {
        *v12++ = 0;
        --v7;
      }
      while ( v7 );
      if ( !*(_BYTE *)(v11 + 8) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x117,
          (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\ccontext.cpp",
          (const char *)0x80070015LL,
          dwCreationFlags);
        goto LABEL_13;
      }
      DefStringResult_InitBuf(v34);
      v33 = v34;
      if ( (*(int (__fastcall **)(_QWORD, const WCHAR *, _BYTE **))(**(_QWORD **)(v23 + 24) + 72LL))(
             *(_QWORD *)(v23 + 24),
             L"HomeRegion",
             &v33) >= 0 )
      {
        v32 = 0;
        Length = DefStringResult_GetLength(v33);
        if ( Length < 0 )
        {
          v27 = (unsigned int)Length;
          v28 = 296;
LABEL_49:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v28,
            (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\ccontext.cpp",
            (const char *)v27,
            dwCreationFlags);
          goto LABEL_50;
        }
        if ( (unsigned __int64)(v32 + 1) <= 0x56 )
        {
          if ( v25 && (*(_QWORD *)v25 || !*(_DWORD *)(v25 + 8)) && (*(_DWORD *)(v25 + 8) || !*(_QWORD *)v25) )
          {
            v26 = *(_WORD **)(v25 + 16);
            do
            {
              if ( !v10 )
                break;
              if ( !*v26 )
                break;
              ++v26;
              --v10;
              --v9;
            }
            while ( v9 );
            v27 = v9 == 0 ? 0x8007007A : 0;
            if ( v9 )
              goto LABEL_50;
            v28 = 310;
          }
          else
          {
            v27 = 2147942487LL;
            v28 = 308;
          }
          goto LABEL_49;
        }
      }
LABEL_50:
      Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v33);
      goto LABEL_13;
    }
    DefStringResult_InitBuf(v34);
    v33 = v34;
    if ( (*(int (__fastcall **)(_QWORD, const WCHAR *, _BYTE **))(**(_QWORD **)(v15 + 24) + 72LL))(
           *(_QWORD *)(v15 + 24),
           L"Language",
           &v33) >= 0 )
    {
      v32 = 0;
      v16 = DefStringResult_GetLength(v33);
      if ( v16 < 0 )
      {
        v21 = (unsigned int)v16;
        v22 = 296;
LABEL_33:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v22,
          (unsigned int)"onecoreuap\\base\\mrt\\runtime\\src\\ccontext.cpp",
          (const char *)v21,
          dwCreationFlags);
        goto LABEL_34;
      }
      if ( (unsigned __int64)(v32 + 1) <= 0x56 )
      {
        if ( v17 && (*(_QWORD *)v17 || !*(_DWORD *)(v17 + 8)) && (*(_DWORD *)(v17 + 8) || !*(_QWORD *)v17) )
        {
          v18 = *(_WORD **)(v17 + 16);
          v19 = 2147483646;
          v20 = 86;
          do
          {
            if ( !v19 )
              break;
            if ( !*v18 )
              break;
            ++v18;
            --v19;
            --v20;
          }
          while ( v20 );
          v21 = v20 == 0 ? 0x8007007A : 0;
          if ( v20 )
            goto LABEL_34;
          v22 = 310;
        }
        else
        {
          v21 = 2147942487LL;
          v22 = 308;
        }
        goto LABEL_33;
      }
    }
LABEL_34:
    Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v33);
    goto LABEL_9;
  }
  return 0;
}

```

## disassembly

```asm
0x1800450b8  push    rbp
0x1800450ba  push    rbx
0x1800450bb  push    rsi
0x1800450bc  push    rdi
0x1800450bd  push    r12
0x1800450bf  push    r13
0x1800450c1  push    r14
0x1800450c3  push    r15
0x1800450c5  lea     rbp, [rsp-28h]
0x1800450ca  sub     rsp, 128h
0x1800450d1  mov     rax, cs:__security_cookie
0x1800450d8  xor     rax, rsp
0x1800450db  mov     [rbp+60h+var_50], rax
0x1800450df  mov     rdi, rcx
0x1800450e2  xor     r12d, r12d
0x1800450e5  mov     rcx, [rcx+48h]
0x1800450e9  test    rcx, rcx
0x1800450ec  jz      loc_180045247
0x1800450f2  mov     rax, [rcx]
0x1800450f5  lea     rdx, aLanguage; "Language"
0x1800450fc  mov     rax, [rax+158h]
0x180045103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045108  test    al, al
0x18004510a  jz      loc_180045247
0x180045110  cmp     qword ptr [rdi+28h], 0FFFFFFFFFFFFFFFFh
0x180045115  mov     ebx, r12d
0x180045118  jnz     loc_180045203
0x18004511e  xor     r9d, r9d; lpName
0x180045121  xor     r8d, r8d; bInitialState
0x180045124  xor     edx, edx; bManualReset
0x180045126  xor     ecx, ecx; lpEventAttributes
0x180045128  call    cs:__imp_CreateEventW
0x18004512e  mov     [rdi+28h], rax
0x180045132  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180045136  jz      loc_180045437
0x18004513c  mov     r8, [rdi+40h]
0x180045140  lea     rax, [rsp+160h+var_100]
0x180045145  mov     r14d, 0ACh
0x18004514b  mov     ecx, r14d
0x18004514e  mov     [rax], r12b
0x180045151  inc     rax
0x180045154  sub     rcx, 1
0x180045158  jnz     short loc_18004514E
0x18004515a  lea     esi, [rcx+56h]
0x18004515d  mov     r15d, 7FFFFFFEh
0x180045163  lea     r13, aOnecoreuapBase_27; "onecoreuap\\base\\mrt\\runtime\\src\\cc"...
0x18004516a  cmp     [r8+8], r12b
0x18004516e  jnz     loc_18004524B
0x180045174  mov     rcx, [rbp+68h]; this
0x180045178  mov     r9d, 80070015h; char *
0x18004517e  mov     r8, r13; unsigned int
0x180045181  mov     edx, 117h; void *
0x180045186  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004518b  mov     rdx, [rdi+40h]
0x18004518f  lea     rax, [rsp+160h+var_100]
0x180045194  mov     [rax], r12b
0x180045197  inc     rax
0x18004519a  sub     r14, 1
0x18004519e  jnz     short loc_180045194
0x1800451a0  cmp     [rdx+8], r12b
0x1800451a4  jnz     loc_180045330
0x1800451aa  mov     rcx, [rbp+68h]; this
0x1800451ae  mov     r9d, 80070015h; char *
0x1800451b4  mov     r8, r13; unsigned int
0x1800451b7  mov     edx, 117h; void *
0x1800451bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800451c1  xor     edx, edx
0x1800451c3  mov     rcx, rdi
0x1800451c6  call    ?reset@?$unique_storage@U?$resource_policy@PEAUCO_MTA_USAGE_COOKIE__@@P6AJPEAU1@@Z$1?CoDecrementMTAUsage@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUCO_MTA_USAGE_COOKIE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<CO_MTA_USAGE_COOKIE__ *,long (*)(CO_MTA_USAGE_COOKIE__ *),&CoDecrementMTAUsage(CO_MTA_USAGE_COOKIE__ *),wistd::integral_constant<unsigned __int64,0>,CO_MTA_USAGE_COOKIE__ *,CO_MTA_USAGE_COOKIE__ *,0,std::nullptr_t>>::reset(CO_MTA_USAGE_COOKIE__ *)
0x1800451cb  mov     rcx, rdi
0x1800451ce  call    cs:__imp_CoIncrementMTAUsage
0x1800451d4  mov     r9, rdi; lpParameter
0x1800451d7  mov     [rsp+160h+lpThreadId], r12; lpThreadId
0x1800451dc  lea     r8, ?LanguageChangeNotifyThreadProc@Core@Resources@ApplicationModel@Windows@@YAKPEAX@Z; lpStartAddress
0x1800451e3  mov     [rsp+160h+dwCreationFlags], r12d; dwCreationFlags
0x1800451e8  xor     edx, edx; dwStackSize
0x1800451ea  xor     ecx, ecx; lpThreadAttributes
0x1800451ec  call    cs:__imp_CreateThread
0x1800451f2  mov     [rdi+20h], rax
0x1800451f6  test    rax, rax
0x1800451f9  jz      loc_180045459
0x1800451ff  test    ebx, ebx
0x180045201  js      short loc_180045225
0x180045203  cmp     dword ptr [rdi+1Ch], 0FFFFFFFFh
0x180045207  jnz     short loc_180045225
0x180045209  lea     rdx, [rsp+160h+var_130]
0x18004520e  mov     dword ptr [rsp+160h+var_130], 0FFFFFFFFh
0x180045216  xor     ecx, ecx
0x180045218  call    cs:__imp_GetApplicationLayoutDirection
0x18004521e  mov     ecx, dword ptr [rsp+160h+var_130]
0x180045222  mov     [rdi+1Ch], ecx
0x180045225  mov     eax, ebx
0x180045227  mov     rcx, [rbp+60h+var_50]
0x18004522b  xor     rcx, rsp; StackCookie
0x18004522e  call    __security_check_cookie
0x180045233  add     rsp, 128h
0x18004523a  pop     r15
0x18004523c  pop     r14
0x18004523e  pop     r13
0x180045240  pop     r12
0x180045242  pop     rdi
0x180045243  pop     rsi
0x180045244  pop     rbx
0x180045245  pop     rbp
0x180045246  retn
0x180045247  xor     eax, eax
0x180045249  jmp     short loc_180045227
0x18004524b  lea     rcx, [rsp+160h+var_120]
0x180045250  call    DefStringResult_InitBuf
0x180045255  lea     rcx, [rsp+160h+var_120]
0x18004525a  mov     [rsp+160h+var_128], rcx
0x18004525f  lea     rdx, aLanguage; "Language"
0x180045266  mov     rcx, [r8+18h]
0x18004526a  lea     r8, [rsp+160h+var_128]
0x18004526f  mov     rax, [rcx]
0x180045272  mov     rax, [rax+48h]
0x180045276  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004527b  test    eax, eax
0x18004527d  js      loc_180045321
0x180045283  mov     r11, [rsp+160h+var_128]
0x180045288  lea     rdx, [rsp+160h+var_130]
0x18004528d  mov     rcx, r11
0x180045290  mov     [rsp+160h+var_130], r12
0x180045295  call    DefStringResult_GetLength
0x18004529a  test    eax, eax
0x18004529c  js      loc_180045420
0x1800452a2  mov     rax, [rsp+160h+var_130]
0x1800452a7  inc     rax
0x1800452aa  cmp     rax, rsi
0x1800452ad  ja      short loc_180045321
0x1800452af  test    r11, r11
0x1800452b2  jz      loc_180045403
0x1800452b8  cmp     [r11], r12
0x1800452bb  jnz     short loc_1800452C7
0x1800452bd  cmp     [r11+8], r12d
0x1800452c1  ja      loc_180045403
0x1800452c7  cmp     [r11+8], r12d
0x1800452cb  jnz     short loc_1800452D6
0x1800452cd  cmp     [r11], r12
0x1800452d0  jnz     loc_180045403
0x1800452d6  mov     rdx, [r11+10h]
0x1800452da  mov     rax, r15
0x1800452dd  mov     rcx, rsi
0x1800452e0  test    rax, rax
0x1800452e3  jz      short loc_1800452F8
0x1800452e5  cmp     [rdx], r12w
0x1800452e9  jz      short loc_1800452F8
0x1800452eb  add     rdx, 2
0x1800452ef  dec     rax
0x1800452f2  sub     rcx, 1
0x1800452f6  jnz     short loc_1800452E0
0x1800452f8  mov     rax, rcx
0x1800452fb  neg     rax
0x1800452fe  sbb     r9d, r9d
0x180045301  not     r9d
0x180045304  and     r9d, 8007007Ah; char *
0x18004530b  test    rcx, rcx
0x18004530e  jnz     short loc_180045321
0x180045310  mov     edx, 136h; void *
0x180045315  mov     rcx, [rbp+68h]; this
0x180045319  mov     r8, r13; unsigned int
0x18004531c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045321  lea     rcx, [rsp+160h+var_128]; this
0x180045326  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x18004532b  jmp     loc_18004518B
0x180045330  lea     rcx, [rsp+160h+var_120]
0x180045335  call    DefStringResult_InitBuf
0x18004533a  lea     rcx, [rsp+160h+var_120]
0x18004533f  mov     [rsp+160h+var_128], rcx
0x180045344  lea     r8, [rsp+160h+var_128]
0x180045349  mov     rcx, [rdx+18h]
0x18004534d  lea     rdx, aHomeregion; "HomeRegion"
0x180045354  mov     rax, [rcx]
0x180045357  mov     rax, [rax+48h]
0x18004535b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045360  test    eax, eax
0x180045362  js      loc_1800453F4
0x180045368  mov     r11, [rsp+160h+var_128]
0x18004536d  lea     rdx, [rsp+160h+var_130]
0x180045372  mov     rcx, r11
0x180045375  mov     [rsp+160h+var_130], r12
0x18004537a  call    DefStringResult_GetLength
0x18004537f  test    eax, eax
0x180045381  js      loc_18004542D
0x180045387  mov     rax, [rsp+160h+var_130]
0x18004538c  inc     rax
0x18004538f  cmp     rax, rsi
0x180045392  ja      short loc_1800453F4
0x180045394  test    r11, r11
0x180045397  jz      short loc_180045413
0x180045399  cmp     [r11], r12
0x18004539c  jnz     short loc_1800453A4
0x18004539e  cmp     [r11+8], r12d
0x1800453a2  ja      short loc_180045413
0x1800453a4  cmp     [r11+8], r12d
0x1800453a8  jnz     short loc_1800453AF
0x1800453aa  cmp     [r11], r12
0x1800453ad  jnz     short loc_180045413
0x1800453af  mov     rax, [r11+10h]
0x1800453b3  test    r15, r15
0x1800453b6  jz      short loc_1800453CB
0x1800453b8  cmp     [rax], r12w
0x1800453bc  jz      short loc_1800453CB
0x1800453be  add     rax, 2
0x1800453c2  dec     r15
0x1800453c5  sub     rsi, 1
0x1800453c9  jnz     short loc_1800453B3
0x1800453cb  mov     rax, rsi
0x1800453ce  neg     rax
0x1800453d1  sbb     r9d, r9d
0x1800453d4  not     r9d
0x1800453d7  and     r9d, 8007007Ah; char *
0x1800453de  test    rsi, rsi
0x1800453e1  jnz     short loc_1800453F4
0x1800453e3  mov     edx, 136h; void *
0x1800453e8  mov     rcx, [rbp+68h]; this
0x1800453ec  mov     r8, r13; unsigned int
0x1800453ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800453f4  lea     rcx, [rsp+160h+var_128]; this
0x1800453f9  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x1800453fe  jmp     loc_1800451C1
0x180045403  mov     r9d, 80070057h
0x180045409  mov     edx, 134h
0x18004540e  jmp     loc_180045315
0x180045413  mov     r9d, 80070057h
0x180045419  mov     edx, 134h
0x18004541e  jmp     short loc_1800453E8
0x180045420  mov     r9d, eax
0x180045423  mov     edx, 128h
0x180045428  jmp     loc_180045315
0x18004542d  mov     r9d, eax
0x180045430  mov     edx, 128h
0x180045435  jmp     short loc_1800453E8
0x180045437  call    cs:__imp_GetLastError
0x18004543d  mov     ebx, eax
0x18004543f  test    eax, eax
0x180045441  jle     short loc_18004544C
0x180045443  movzx   ebx, ax
0x180045446  or      ebx, 80070000h
0x18004544c  test    ebx, ebx
0x18004544e  js      loc_1800451C1
0x180045454  jmp     loc_18004513C
0x180045459  xor     edx, edx
0x18004545b  mov     rcx, rdi
0x18004545e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUCO_MTA_USAGE_COOKIE__@@P6AJPEAU1@@Z$1?CoDecrementMTAUsage@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUCO_MTA_USAGE_COOKIE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<CO_MTA_USAGE_COOKIE__ *,long (*)(CO_MTA_USAGE_COOKIE__ *),&CoDecrementMTAUsage(CO_MTA_USAGE_COOKIE__ *),wistd::integral_constant<unsigned __int64,0>,CO_MTA_USAGE_COOKIE__ *,CO_MTA_USAGE_COOKIE__ *,0,std::nullptr_t>>::reset(CO_MTA_USAGE_COOKIE__ *)
0x180045463  call    cs:__imp_GetLastError
0x180045469  mov     ebx, eax
0x18004546b  test    eax, eax
0x18004546d  jle     loc_1800451FF
0x180045473  movzx   ebx, ax
0x180045476  or      ebx, 80070000h
0x18004547c  jmp     loc_1800451FF
```
