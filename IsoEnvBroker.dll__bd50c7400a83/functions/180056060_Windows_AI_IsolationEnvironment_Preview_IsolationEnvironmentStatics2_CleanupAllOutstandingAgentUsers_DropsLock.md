# Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics2::CleanupAllOutstandingAgentUsers_DropsLock(void)

- ea: `0x180056060`
- end: `0x1800564ea`
- name: `?CleanupAllOutstandingAgentUsers_DropsLock@IsolationEnvironmentStatics2@Preview@IsolationEnvironment@AI@Windows@@SAXXZ`
- size: `1162`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180061100`
- `0x180062ba8`

## callees

- `0x180002520`
- `0x1800075e4`
- `0x18001045c`
- `0x180011e18`
- `0x18001f998`
- `0x180026974`
- `0x1800293e4`
- `0x18002fc24`
- `0x18005410c`
- `0x180055950`
- `0x180055da4`
- `0x180056060`
- `0x18005917c`
- `0x1800615a8`

## import_xrefs

- `NETAPI32!NetUserGetInfo` at `0x1800561b7`
- `NETAPI32!NetUserGetInfo` at `0x1800561b7`
- `NETAPI32!NetApiBufferFree` at `0x180056287`
- `NETAPI32!NetApiBufferFree` at `0x180056287`
- `NETAPI32!NetUserSetInfo` at `0x180056236`
- `NETAPI32!NetUserSetInfo` at `0x180056236`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800560c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800560f8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800563f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800560c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800560f8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800563f5`

## string_xrefs

- `0x1800564a2`: `onecoreuap\windows\core\isoenvbroker\inc\checked_srwlock.h`
- `0x1800564b4`: `onecoreuap\windows\core\isoenvbroker\inc\checked_srwlock.h`
- `0x1800564c6`: `onecoreuap\windows\core\isoenvbroker\inc\checked_srwlock.h`
- `0x1800564d8`: `onecoreuap\windows\core\isoenvbroker\lib\common\UserAccountHelpers.h`
- `0x18005645f`: `Failed to set service to demand start: %#x`
- `0x1800561fb`: `Disabling AU: Account %s already disabled.`
- `0x180056383`: `(v2) Deleted AU account %s for owning user %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics2::CleanupAllOutstandingAgentUsers_DropsLock(
        void)
{
  const char *v0; // r9
  char v1; // r12
  int v2; // ebx
  char v3; // al
  _QWORD *v4; // rdi
  int v5; // ebx
  char v6; // al
  AgentAccountRegistry *v7; // rcx
  __int64 v8; // r14
  __m128i si128; // xmm6
  _QWORD *v10; // r13
  char **v11; // rsi
  char **v12; // rbx
  _QWORD *v13; // rsi
  _QWORD *i; // rbx
  const WCHAR *v15; // r15
  char v16; // al
  DWORD Info; // eax
  const wchar_t *v18; // rdx
  DWORD v19; // eax
  LPBYTE v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rdx
  _QWORD *j; // rbx
  _QWORD *v24; // rsi
  int v25; // eax
  __int64 v26; // r9
  _QWORD *v27; // r9
  _QWORD *v28; // r8
  _QWORD *v29; // rax
  _QWORD *v30; // r8
  const char *v31; // r9
  int v32; // ebx
  int v33; // ebx
  _QWORD *k; // rax
  bool v35; // al
  bool v36; // zf
  int started; // eax
  __int64 v38; // [rsp+28h] [rbp-99h]
  LPBYTE bufptr; // [rsp+38h] [rbp-89h] BYREF
  int buf; // [rsp+40h] [rbp-81h] BYREF
  DWORD parm_err; // [rsp+44h] [rbp-7Dh] BYREF
  __int128 v42; // [rsp+48h] [rbp-79h] BYREF
  __int64 v43; // [rsp+58h] [rbp-69h]
  char *v44[2]; // [rsp+68h] [rbp-59h] BYREF
  __m128i v45; // [rsp+78h] [rbp-49h]
  char *v46[2]; // [rsp+88h] [rbp-39h] BYREF
  __m128i v47; // [rsp+98h] [rbp-29h]
  __int64 v48; // [rsp+A8h] [rbp-19h]
  wil::details::in1diag3 *retaddr; // [rsp+120h] [rbp+5Fh]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID58336780>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID58336780>::GetImpl'::`2'::impl) )
  {
    v42 = 0;
    v43 = 0;
    v1 = 1;
    if ( dword_1800B9164 > 0 || (v2 = dword_1800B9160, v36 = v2 == GetCurrentThreadId(), v3 = 1, v36) )
      v3 = 0;
    if ( v3 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x175,
        (int)"onecoreuap\\windows\\core\\isoenvbroker\\inc\\checked_srwlock.h",
        v0);
    v4 = *(_QWORD **)qword_1800B9470;
    if ( dword_1800B9164 > 0 || (v5 = dword_1800B9160, v36 = v5 == GetCurrentThreadId(), v6 = 1, v36) )
      v6 = 0;
    v7 = retaddr;
    if ( v6 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x175,
        (int)"onecoreuap\\windows\\core\\isoenvbroker\\inc\\checked_srwlock.h",
        v0);
    v8 = qword_1800B9470;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
LABEL_11:
    if ( v4 != (_QWORD *)v8 )
    {
      v10 = v4 + 2;
      v11 = (char **)*((_QWORD *)&v42 + 1);
      v12 = (char **)v42;
      if ( (_QWORD)v42 != *((_QWORD *)&v42 + 1) )
      {
        do
        {
          std::wstring::~wstring(v12 + 4);
          std::wstring::~wstring(v12);
          v12 += 9;
        }
        while ( v12 != v11 );
        *((_QWORD *)&v42 + 1) = v42;
      }
      v13 = *(_QWORD **)(v4[6] + 48LL);
      for ( i = (_QWORD *)*v13; ; i = (_QWORD *)*i )
      {
        if ( i == v13 )
        {
          v24 = (_QWORD *)*((_QWORD *)&v42 + 1);
          for ( j = (_QWORD *)v42; j != v24; j += 9 )
          {
            v25 = AgentAccountHelpers2::CleanupAgentUserForUser_DropsLock(j, j + 4, j[8]);
            v26 = (unsigned int)v25;
            if ( v25 < 0 )
            {
              if ( v4[5] <= 7u )
                v29 = v4 + 2;
              else
                v29 = (_QWORD *)*v10;
              if ( j[3] <= 7u )
                v30 = j;
              else
                v30 = (_QWORD *)*j;
              Log(2u, L"(v2) Failed to clean up AU account %s, error %#x, for owning user %s", v30, v26, v29);
            }
            else
            {
              if ( v4[5] <= 7u )
                v27 = v4 + 2;
              else
                v27 = (_QWORD *)*v10;
              if ( j[3] <= 7u )
                v28 = j;
              else
                v28 = (_QWORD *)*j;
              Log(4u, L"(v2) Deleted AU account %s for owning user %s", v28, v27);
            }
          }
          v4 = (_QWORD *)*v4;
          goto LABEL_11;
        }
        if ( i[5] <= 7u )
          v15 = (const WCHAR *)(i + 2);
        else
          v15 = (const WCHAR *)i[2];
        if ( !v15 || (v16 = 0, !*v15) )
          v16 = 1;
        if ( v16 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0x130,
            (int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\common\\UserAccountHelpers.h",
            v0);
        bufptr = 0;
        Info = NetUserGetInfo(0, v15, 4u, &bufptr);
        if ( Info )
        {
          if ( Info == 2221 )
            Log(4u, L"Disabling AU: Account %s does not exist.", v15);
          else
            Log(3u, L"Disabling AU: NetUserGetInfo failed for %s: %#x", v15, Info);
        }
        else
        {
          if ( (bufptr[40] & 2) != 0 )
          {
            v18 = L"Disabling AU: Account %s already disabled.";
          }
          else
          {
            buf = 0;
            buf = *((_DWORD *)bufptr + 10) | 2;
            parm_err = 0;
            v19 = NetUserSetInfo(0, v15, 0x3F0u, (LPBYTE)&buf, &parm_err);
            if ( v19 )
            {
              LODWORD(v38) = parm_err;
              Log(2u, L"Disabling AU: NetUserSetInfo failed for %s: %#x (parm_error: %u)", v15, v19, v38);
              goto LABEL_34;
            }
            v18 = L"Disabled account %s.";
          }
          Log(4u, v18, v15);
        }
LABEL_34:
        v20 = bufptr;
        bufptr = 0;
        if ( v20 )
          NetApiBufferFree(v20);
        std::wstring::wstring((__int64)v44, (__int64)(i + 2));
        std::wstring::wstring((__int64)v46, (__int64)(i + 6));
        v21 = v4[6];
        v48 = v21;
        v22 = *((_QWORD *)&v42 + 1);
        if ( *((_QWORD *)&v42 + 1) == v43 )
        {
          std::vector__Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics2::CleanupAllOutstandingAgentUsers_DropsLock_::_2_::AgentInfo_std::allocator__Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics2::CleanupAllOutstandingAgentUsers_DropsLock_::_2_::AgentInfo___::_Emplace_reallocate__Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics2::CleanupAllOutstandingAgentUsers_DropsLock_::_2_::AgentInfo_(
            &v42,
            *((_QWORD *)&v42 + 1),
            v44);
        }
        else
        {
          **((_QWORD **)&v42 + 1) = v44[0];
          *(char **)(v22 + 8) = v44[1];
          *(__m128i *)(v22 + 16) = v45;
          v45 = si128;
          LOWORD(v44[0]) = 0;
          *(char **)(v22 + 32) = v46[0];
          *(char **)(v22 + 40) = v46[1];
          *(__m128i *)(v22 + 48) = v47;
          v47 = si128;
          LOWORD(v46[0]) = 0;
          *(_QWORD *)(v22 + 64) = v21;
          *((_QWORD *)&v42 + 1) += 72LL;
        }
        std::wstring::~wstring(v46);
        std::wstring::~wstring(v44);
      }
    }
    AgentAccountRegistry::RemoveEmptyKeys(v7);
    if ( dword_1800B9164 > 0 || (v32 = dword_1800B9160, v32 == GetCurrentThreadId()) )
      v1 = 0;
    if ( v1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x175,
        (int)"onecoreuap\\windows\\core\\isoenvbroker\\inc\\checked_srwlock.h",
        v31);
    v33 = 0;
    for ( k = *(_QWORD **)qword_1800B9470; k != (_QWORD *)qword_1800B9470; k = (_QWORD *)*k )
      v33 += *(_DWORD *)(k[6] + 120LL);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59959135>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID59959135>::GetImpl'::`2'::impl) )
    {
      v35 = MopUpMemUserProfiles();
      if ( v33 )
      {
LABEL_73:
        std::vector__Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics2::CleanupAllOutstandingAgentUsers_DropsLock_::_2_::AgentInfo_std::allocator__Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics2::CleanupAllOutstandingAgentUsers_DropsLock_::_2_::AgentInfo___::_vector__Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics2::CleanupAllOutstandingAgentUsers_DropsLock_::_2_::AgentInfo_std::allocator__Windows::AI::IsolationEnvironment::Preview::IsolationEnvironmentStatics2::CleanupAllOutstandingAgentUsers_DropsLock_::_2_::AgentInfo___(&v42);
        return;
      }
      v36 = !v35;
    }
    else
    {
      v36 = v33 == 0;
    }
    if ( v36 )
    {
      started = SetServiceStartType(3u);
      if ( started < 0 )
        Log(2u, L"Failed to set service to demand start: %#x", (unsigned int)started);
    }
    goto LABEL_73;
  }
}

```

## disassembly

```asm
0x180056060  mov     rax, rsp
0x180056063  push    rbp
0x180056064  push    rbx
0x180056065  push    rsi
0x180056066  push    rdi
0x180056067  push    r12
0x180056069  push    r13
0x18005606b  push    r14
0x18005606d  push    r15
0x18005606f  lea     rbp, [rax-5Fh]
0x180056073  sub     rsp, 0D8h
0x18005607a  movaps  xmmword ptr [rax-58h], xmm6
0x18005607e  mov     rax, cs:__security_cookie
0x180056085  xor     rax, rsp
0x180056088  mov     [rbp+57h+var_60], rax
0x18005608c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID58336780@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID58336780@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID58336780> `wil::Feature<__WilFeatureTraits_Feature_ID58336780>::GetImpl(void)'::`2'::impl
0x180056093  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID58336780@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID58336780>::__private_IsEnabled(void)
0x180056098  xor     r15d, r15d
0x18005609b  test    al, al
0x18005609d  jz      loc_18005647A
0x1800560a3  xorps   xmm0, xmm0
0x1800560a6  movdqu  [rbp+57h+var_D0], xmm0
0x1800560ab  mov     [rbp+57h+var_C0], r15
0x1800560af  mov     eax, cs:dword_1800B9164
0x1800560b5  mov     r12b, 1
0x1800560b8  test    eax, eax
0x1800560ba  jg      short loc_1800560CF
0x1800560bc  mov     ebx, cs:dword_1800B9160
0x1800560c2  call    cs:__imp_GetCurrentThreadId
0x1800560c8  cmp     ebx, eax
0x1800560ca  mov     al, r12b
0x1800560cd  jnz     short loc_1800560D2
0x1800560cf  mov     al, r15b
0x1800560d2  mov     rcx, [rbp+5Fh]; this
0x1800560d6  test    al, al
0x1800560d8  jnz     loc_1800564B4
0x1800560de  mov     rdi, cs:qword_1800B9470
0x1800560e5  mov     rdi, [rdi]
0x1800560e8  mov     eax, cs:dword_1800B9164
0x1800560ee  test    eax, eax
0x1800560f0  jg      short loc_180056105
0x1800560f2  mov     ebx, cs:dword_1800B9160
0x1800560f8  call    cs:__imp_GetCurrentThreadId
0x1800560fe  cmp     ebx, eax
0x180056100  mov     al, r12b
0x180056103  jnz     short loc_180056108
0x180056105  mov     al, r15b
0x180056108  mov     rcx, [rbp+5Fh]; this
0x18005610c  test    al, al
0x18005610e  jnz     loc_1800564C6
0x180056114  mov     r14, cs:qword_1800B9470
0x18005611b  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180056123  cmp     rdi, r14
0x180056126  jz      loc_1800563E0
0x18005612c  lea     r13, [rdi+10h]
0x180056130  mov     rsi, qword ptr [rbp+57h+var_D0+8]
0x180056134  mov     rbx, qword ptr [rbp+57h+var_D0]
0x180056138  cmp     rbx, rsi
0x18005613b  jz      short loc_18005615F
0x18005613d  lea     rcx, [rbx+20h]
0x180056141  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180056146  mov     rcx, rbx
0x180056149  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005614e  add     rbx, 48h ; 'H'
0x180056152  cmp     rbx, rsi
0x180056155  jnz     short loc_18005613D
0x180056157  mov     rax, qword ptr [rbp+57h+var_D0]
0x18005615b  mov     qword ptr [rbp+57h+var_D0+8], rax
0x18005615f  mov     rsi, [r13+20h]
0x180056163  mov     rsi, [rsi+30h]
0x180056167  mov     rbx, [rsi]
0x18005616a  cmp     rbx, rsi
0x18005616d  jz      loc_180056340
0x180056173  cmp     qword ptr [rbx+28h], 7
0x180056178  jbe     short loc_180056180
0x18005617a  mov     r15, [rbx+10h]
0x18005617e  jmp     short loc_180056184
0x180056180  lea     r15, [rbx+10h]
0x180056184  xor     edx, edx
0x180056186  test    r15, r15
0x180056189  jz      short loc_180056193
0x18005618b  cmp     [r15], dx
0x18005618f  mov     al, dl
0x180056191  jnz     short loc_180056196
0x180056193  mov     al, r12b
0x180056196  mov     rcx, [rbp+5Fh]; this
0x18005619a  test    al, al
0x18005619c  jnz     loc_1800564D8
0x1800561a2  mov     [rsp+110h+bufptr], rdx
0x1800561a7  lea     r9, [rsp+110h+bufptr]; bufptr
0x1800561ac  mov     r8d, 4; level
0x1800561b2  mov     rdx, r15; username
0x1800561b5  xor     ecx, ecx; servername
0x1800561b7  call    cs:__imp_NetUserGetInfo
0x1800561bd  test    eax, eax
0x1800561bf  jz      short loc_1800561F0
0x1800561c1  mov     r8, r15
0x1800561c4  cmp     eax, 8ADh
0x1800561c9  jnz     short loc_1800561D7
0x1800561cb  lea     rdx, aDisablingAuAcc_0; "Disabling AU: Account %s does not exist"...
0x1800561d2  jmp     loc_18005626A
0x1800561d7  mov     r9d, eax
0x1800561da  lea     rdx, aDisablingAuNet_0; "Disabling AU: NetUserGetInfo failed for"...
0x1800561e1  mov     ecx, 3; unsigned __int8
0x1800561e6  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x1800561eb  jmp     loc_180056275
0x1800561f0  mov     rax, [rsp+110h+bufptr]
0x1800561f5  test    byte ptr [rax+28h], 2
0x1800561f9  jz      short loc_180056204
0x1800561fb  lea     rdx, aDisablingAuAcc; "Disabling AU: Account %s already disabl"...
0x180056202  jmp     short loc_180056267
0x180056204  mov     [rsp+110h+buf], 0
0x18005620c  mov     eax, [rax+28h]
0x18005620f  or      eax, 2
0x180056212  mov     [rsp+110h+buf], eax
0x180056216  mov     [rbp+57h+parm_err], 0
0x18005621d  lea     rax, [rbp+57h+parm_err]
0x180056221  mov     [rsp+20h], rax; parm_err
0x180056226  lea     r9, [rsp+110h+buf]; buf
0x18005622b  mov     r8d, 3F0h; level
0x180056231  mov     rdx, r15; username
0x180056234  xor     ecx, ecx; servername
0x180056236  call    cs:__imp_NetUserSetInfo
0x18005623c  test    eax, eax
0x18005623e  jz      short loc_180056260
0x180056240  mov     ecx, [rbp+57h+parm_err]
0x180056243  mov     [rsp+20h], ecx
0x180056247  mov     r9d, eax
0x18005624a  mov     r8, r15
0x18005624d  lea     rdx, aDisablingAuNet; "Disabling AU: NetUserSetInfo failed for"...
0x180056254  mov     ecx, 2; unsigned __int8
0x180056259  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18005625e  jmp     short loc_180056275
0x180056260  lea     rdx, aDisabledAccoun; "Disabled account %s."
0x180056267  mov     r8, r15
0x18005626a  mov     ecx, 4; unsigned __int8
0x18005626f  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180056274  nop
0x180056275  mov     rcx, [rsp+110h+bufptr]; Buffer
0x18005627a  xor     r15d, r15d
0x18005627d  mov     [rsp+110h+bufptr], r15
0x180056282  test    rcx, rcx
0x180056285  jz      short loc_18005628D
0x180056287  call    cs:__imp_NetApiBufferFree
0x18005628d  lea     rdx, [rbx+10h]
0x180056291  lea     rcx, [rbp+57h+var_B0]
0x180056295  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18005629a  nop
0x18005629b  lea     rdx, [rbx+30h]
0x18005629f  lea     rcx, [rbp+57h+var_90]
0x1800562a3  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800562a8  mov     rcx, [r13+20h]
0x1800562ac  mov     [rbp+57h+var_70], rcx
0x1800562b0  mov     rdx, qword ptr [rbp+57h+var_D0+8]
0x1800562b4  cmp     rdx, [rbp+57h+var_C0]
0x1800562b8  jz      short loc_180056318
0x1800562ba  mov     rax, [rbp+57h+var_B0]
0x1800562be  mov     [rdx], rax
0x1800562c1  mov     rax, [rbp+57h+var_A8]
0x1800562c5  mov     [rdx+8], rax
0x1800562c9  mov     rax, qword ptr [rbp+57h+var_A0]
0x1800562cd  mov     [rdx+10h], rax
0x1800562d1  mov     rax, qword ptr [rbp+57h+var_A0+8]
0x1800562d5  mov     [rdx+18h], rax
0x1800562d9  movdqa  [rbp+57h+var_A0], xmm6
0x1800562de  mov     word ptr [rbp+57h+var_B0], r15w
0x1800562e3  mov     rax, [rbp+57h+var_90]
0x1800562e7  mov     [rdx+20h], rax
0x1800562eb  mov     rax, [rbp+57h+var_88]
0x1800562ef  mov     [rdx+28h], rax
0x1800562f3  mov     rax, qword ptr [rbp+57h+var_80]
0x1800562f7  mov     [rdx+30h], rax
0x1800562fb  mov     rax, qword ptr [rbp+57h+var_80+8]
0x1800562ff  mov     [rdx+38h], rax
0x180056303  movdqa  [rbp+57h+var_80], xmm6
0x180056308  mov     word ptr [rbp+57h+var_90], r15w
0x18005630d  mov     [rdx+40h], rcx
0x180056311  add     qword ptr [rbp+57h+var_D0+8], 48h ; 'H'
0x180056316  jmp     short loc_180056326
0x180056318  lea     r8, [rbp+57h+var_B0]
0x18005631c  lea     rcx, [rbp+57h+var_D0]
0x180056320  call    std__vector__Windows__AI__IsolationEnvironment__Preview__IsolationEnvironmentStatics2__CleanupAllOutstandingAgentUsers_DropsLock____2___AgentInfo_std__allocator__Windows__AI__IsolationEnvironment__Preview__IsolationEnvironmentStatics2__CleanupAllOutstandingAgentUsers_DropsLock____2___AgentInfo______Emplace_reallocate__Windows__AI__IsolationEnvironment__Preview__IsolationEnvironmentStatics2__CleanupAllOutstandingAgentUsers_DropsLock____2___AgentInfo_
0x180056325  nop
0x180056326  lea     rcx, [rbp+57h+var_90]
0x18005632a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005632f  lea     rcx, [rbp+57h+var_B0]
0x180056333  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180056338  mov     rbx, [rbx]
0x18005633b  jmp     loc_18005616A
0x180056340  mov     rbx, qword ptr [rbp+57h+var_D0]
0x180056344  mov     rsi, qword ptr [rbp+57h+var_D0+8]
0x180056348  jmp     loc_1800563CF
0x18005634d  lea     rdx, [rbx+20h]
0x180056351  mov     r8, [rbx+40h]
0x180056355  mov     rcx, rbx
0x180056358  call    ?CleanupAgentUserForUser_DropsLock@AgentAccountHelpers2@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0AEAVOwningUserRegistry@@@Z; AgentAccountHelpers2::CleanupAgentUserForUser_DropsLock(std::wstring const &,std::wstring const &,OwningUserRegistry &)
0x18005635d  mov     r9d, eax
0x180056360  test    eax, eax
0x180056362  js      short loc_180056396
0x180056364  cmp     qword ptr [r13+18h], 7
0x180056369  jbe     short loc_180056371
0x18005636b  mov     r9, [r13+0]
0x18005636f  jmp     short loc_180056374
0x180056371  mov     r9, r13
0x180056374  cmp     qword ptr [rbx+18h], 7
0x180056379  jbe     short loc_180056380
0x18005637b  mov     r8, [rbx]
0x18005637e  jmp     short loc_180056383
0x180056380  mov     r8, rbx
0x180056383  lea     rdx, aV2DeletedAuAcc; "(v2) Deleted AU account %s for owning u"...
0x18005638a  mov     ecx, 4; unsigned __int8
0x18005638f  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180056394  jmp     short loc_1800563CB
0x180056396  cmp     qword ptr [r13+18h], 7
0x18005639b  jbe     short loc_1800563A3
0x18005639d  mov     rax, [r13+0]
0x1800563a1  jmp     short loc_1800563A6
0x1800563a3  mov     rax, r13
0x1800563a6  cmp     qword ptr [rbx+18h], 7
0x1800563ab  jbe     short loc_1800563B2
0x1800563ad  mov     r8, [rbx]
0x1800563b0  jmp     short loc_1800563B5
0x1800563b2  mov     r8, rbx
0x1800563b5  mov     [rsp+20h], rax
0x1800563ba  lea     rdx, aV2FailedToClea; "(v2) Failed to clean up AU account %s, "...
0x1800563c1  mov     ecx, 2; unsigned __int8
0x1800563c6  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x1800563cb  add     rbx, 48h ; 'H'
0x1800563cf  cmp     rbx, rsi
0x1800563d2  jnz     loc_18005634D
0x1800563d8  mov     rdi, [rdi]
0x1800563db  jmp     loc_180056123
0x1800563e0  call    ?RemoveEmptyKeys@AgentAccountRegistry@@QEAAXXZ; AgentAccountRegistry::RemoveEmptyKeys(void)
0x1800563e5  mov     eax, cs:dword_1800B9164
0x1800563eb  test    eax, eax
0x1800563ed  jg      short loc_1800563FF
0x1800563ef  mov     ebx, cs:dword_1800B9160
0x1800563f5  call    cs:__imp_GetCurrentThreadId
0x1800563fb  cmp     ebx, eax
0x1800563fd  jnz     short loc_180056402
0x1800563ff  mov     r12b, r15b
0x180056402  mov     rcx, [rbp+5Fh]; this
0x180056406  test    r12b, r12b
0x180056409  jnz     loc_1800564A2
0x18005640f  mov     ebx, r15d
0x180056412  mov     rcx, cs:qword_1800B9470
0x180056419  mov     rax, [rcx]
0x18005641c  cmp     rax, rcx
0x18005641f  jz      short loc_18005642D
0x180056421  mov     rdx, [rax+30h]
0x180056425  add     ebx, [rdx+78h]
0x180056428  mov     rax, [rax]
0x18005642b  jmp     short loc_18005641C
0x18005642d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID59959135@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID59959135@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59959135> `wil::Feature<__WilFeatureTraits_Feature_ID59959135>::GetImpl(void)'::`2'::impl
0x180056434  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID59959135@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59959135>::__private_IsEnabled(void)
0x180056439  test    al, al
0x18005643b  jz      short loc_18005644A
0x18005643d  call    ?MopUpMemUserProfiles@@YA_NXZ; MopUpMemUserProfiles(void)
0x180056442  test    ebx, ebx
0x180056444  jnz     short loc_180056471
0x180056446  test    al, al
0x180056448  jmp     short loc_18005644C
0x18005644a  test    ebx, ebx
0x18005644c  jnz     short loc_180056471
0x18005644e  mov     ecx, 3; unsigned int
0x180056453  call    ?SetServiceStartType@@YAJK@Z; SetServiceStartType(ulong)
0x180056458  test    eax, eax
0x18005645a  jns     short loc_180056471
0x18005645c  mov     r8d, eax
0x18005645f  lea     rdx, aFailedToSetSer; "Failed to set service to demand start: "...
0x180056466  mov     ecx, 2; unsigned __int8
0x18005646b  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180056470  nop
0x180056471  lea     rcx, [rbp+57h+var_D0]
0x180056475  call    std__vector__Windows__AI__IsolationEnvironment__Preview__IsolationEnvironmentStatics2__CleanupAllOutstandingAgentUsers_DropsLock____2___AgentInfo_std__allocator__Windows__AI__IsolationEnvironment__Preview__IsolationEnvironmentStatics2__CleanupAllOutstandingAgentUsers_DropsLock____2___AgentInfo______vector__Windows__AI__IsolationEnvironment__Preview__IsolationEnvironmentStatics2__CleanupAllOutstandingAgentUsers_DropsLock____2___AgentInfo_std__allocator__Windows__AI__IsolationEnvironment__Preview__IsolationEnvironmentStatics2__CleanupAllOutstandingAgentUsers_DropsLock____2___AgentInfo___
0x18005647a  mov     rcx, [rbp+57h+var_60]
0x18005647e  xor     rcx, rsp; StackCookie
0x180056481  call    __security_check_cookie
0x180056486  movaps  xmm6, [rsp+110h+var_58+8]
0x18005648e  add     rsp, 0D8h
0x180056495  pop     r15
0x180056497  pop     r14
0x180056499  pop     r13
0x18005649b  pop     r12
0x18005649d  pop     rdi
0x18005649e  pop     rsi
0x18005649f  pop     rbx
0x1800564a0  pop     rbp
0x1800564a1  retn
0x1800564a2  lea     r8, aOnecoreuapWind_13; "onecoreuap\\windows\\core\\isoenvbroker"...
0x1800564a9  mov     edx, 175h; void *
0x1800564ae  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800564b4  lea     r8, aOnecoreuapWind_13; "onecoreuap\\windows\\core\\isoenvbroker"...
0x1800564bb  mov     edx, 175h; void *
0x1800564c0  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800564c6  lea     r8, aOnecoreuapWind_13; "onecoreuap\\windows\\core\\isoenvbroker"...
0x1800564cd  mov     edx, 175h; void *
0x1800564d2  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800564d8  lea     r8, aOnecoreuapWind_27; "onecoreuap\\windows\\core\\isoenvbroker"...
0x1800564df  mov     edx, 130h; void *
  ... truncated ...
```
