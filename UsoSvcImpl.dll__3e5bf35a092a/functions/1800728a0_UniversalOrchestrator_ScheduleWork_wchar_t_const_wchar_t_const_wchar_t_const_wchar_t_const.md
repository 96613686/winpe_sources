# UniversalOrchestrator::ScheduleWork(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *)

- ea: `0x1800728a0`
- end: `0x180072dcc`
- name: `?ScheduleWork@UniversalOrchestrator@@UEAAJPEB_W000@Z`
- size: `1324`
- prototype: `__int64 __fastcall(UniversalOrchestrator *this, const wchar_t *, const wchar_t *, const wchar_t *, const wchar_t *)`
- caller_count: `0`
- callee_count: `17`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180008e64`
- `0x180010890`
- `0x1800108b4`
- `0x1800112d0`
- `0x180011680`
- `0x180039448`
- `0x1800420e0`
- `0x18006222c`
- `0x180062ac0`
- `0x18006ea28`
- `0x1800709dc`
- `0x1800728a0`
- `0x180072dd4`
- `0x1800750e4`
- `0x180080dd0`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800729ee`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800729fb`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800729ee`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1800729fb`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180072936`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180072936`

## string_xrefs

- `0x180072d9f`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\resource.h`
- `0x180072db9`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall UniversalOrchestrator::ScheduleWork(
        UniversalOrchestrator *this,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        const wchar_t *a5)
{
  __int64 result; // rax
  HRESULT v9; // eax
  _QWORD *System; // rax
  char v11; // r15
  volatile signed __int32 *v12; // rbx
  unsigned int v13; // ebx
  const char *v14; // r9
  _QWORD *v15; // rax
  Windows::Trust *v16; // rcx
  char v17; // si
  volatile signed __int32 *v18; // rbx
  _QWORD *v19; // rcx
  __int64 v20; // rax
  _QWORD *v21; // rax
  __int64 v22; // r8
  __int64 v23; // r8
  _QWORD *v24; // rdx
  __int64 v25; // r8
  int v26; // ecx
  __int64 v27; // rax
  __int64 traits_2_unsigned_short; // rax
  const char *v29; // r9
  __int64 v30; // r11
  __int64 v31; // rax
  int v32; // eax
  unsigned int v33; // ebx
  int v34; // [rsp+20h] [rbp-128h]
  const wchar_t *v35; // [rsp+50h] [rbp-F8h] BYREF
  volatile signed __int32 *v36; // [rsp+58h] [rbp-F0h]
  _OWORD v37[2]; // [rsp+60h] [rbp-E8h] BYREF
  char v38; // [rsp+80h] [rbp-C8h]
  _OWORD v39[2]; // [rsp+88h] [rbp-C0h] BYREF
  char v40; // [rsp+A8h] [rbp-A0h]
  _OWORD v41[2]; // [rsp+B0h] [rbp-98h] BYREF
  char v42; // [rsp+D0h] [rbp-78h]
  __int64 v43; // [rsp+D8h] [rbp-70h] BYREF
  _QWORD v44[3]; // [rsp+E0h] [rbp-68h] BYREF
  unsigned __int64 v45; // [rsp+F8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  if ( a2 )
  {
    if ( *a2 )
    {
      v9 = CoImpersonateClient();
      try
      {
        if ( v9 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1262,
            (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\resource.h",
            (const char *)(unsigned int)v9,
            v34);
        System = (_QWORD *)SystemInterface::Service::GetSystem(&v35);
        v11 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*System + 176LL))(*System);
        v12 = v36;
        if ( v36 )
        {
          if ( _InterlockedExchangeAdd(v36 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
            if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
          }
        }
        if ( v11 )
        {
          CoRevertToSelf();
          Windows::PathVerification::VerifyUpdaterPath(v44, a2, a3);
          v15 = (_QWORD *)SystemInterface::Service::GetSystem(&v35);
          if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)*v15 + 184LL))(*v15)
            || (v17 = 0, !Windows::Trust::IsUMCIEnabled(v16)) )
          {
            v17 = 1;
          }
          v18 = v36;
          if ( v36 )
          {
            if ( _InterlockedExchangeAdd(v36 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
              if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
            }
          }
          if ( !v17 )
            goto LABEL_29;
          v19 = v44;
          if ( v45 > 7 )
            v19 = (_QWORD *)v44[0];
          v20 = -1;
          do
            ++v20;
          while ( *((_WORD *)v19 + v20) );
          v35 = (const wchar_t *)v19;
          v36 = (volatile signed __int32 *)v20;
          if ( (unsigned __int8)Windows::Trust::IsSelfSignedOrCatalogSignedFile(&v35) )
          {
LABEL_29:
            memset(v41, 0, sizeof(v41));
            v22 = -1;
            do
              ++v22;
            while ( a5[v22] );
            std::wstring::_Construct<1,wchar_t const *>(v41);
            v42 = 1;
            memset(v39, 0, sizeof(v39));
            v23 = -1;
            do
              ++v23;
            while ( a4[v23] );
            std::wstring::_Construct<1,wchar_t const *>(v39);
            v40 = 1;
            v24 = v44;
            if ( v45 > 7 )
              v24 = (_QWORD *)v44[0];
            memset(v37, 0, sizeof(v37));
            v25 = -1;
            do
              ++v25;
            while ( *((_WORD *)v24 + v25) );
            std::wstring::_Construct<1,wchar_t const *>(v37);
            v38 = 1;
            v27 = -1;
            do
              ++v27;
            while ( a2[v27] );
            v35 = a2;
            v36 = (volatile signed __int32 *)v27;
            UniversalOrchestrator::QueueWork(
              v26,
              (unsigned int)&v35,
              (unsigned int)v37,
              (unsigned int)v39,
              (__int64)v41);
            if ( v38 )
              std::wstring::~wstring(v37);
            if ( v40 )
              std::wstring::~wstring(v39);
            if ( v42 )
              std::wstring::~wstring(v41);
            v43 = 0;
            traits_2_unsigned_short = anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                        L"LegacyUOProvider",
                                        word_180121B5A,
                                        0);
            if ( traits_2_unsigned_short == v30
              || (v31 = (traits_2_unsigned_short - (__int64)L"LegacyUOProvider") >> 1, v31 == -1) )
            {
              wil::details::in1diag3::_FailFast_Unexpected(
                retaddr,
                (void *)0xC9,
                (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
                v29);
            }
            v35 = L"LegacyUOProvider";
            v36 = (volatile signed __int32 *)v31;
            GetUpdateManager(&v43, &v35);
            v32 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64))(*(_QWORD *)v43 + 72LL))(v43, 0, 0, 1);
            v33 = v32;
            if ( v32 >= 0 )
            {
              if ( v43 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
              std::wstring::~wstring(v44);
              result = 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x251,
                (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\UnivOrchLib\\UniversalOrchestratorHelper.cpp",
                (const char *)(unsigned int)v32,
                1);
              if ( v43 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
              std::wstring::~wstring(v44);
              result = v33;
            }
          }
          else
          {
            v21 = v44;
            if ( v45 > 7 )
              v21 = (_QWORD *)v44[0];
            wil::details::in1diag3::Return_HrMsg(
              retaddr,
              (void *)0x246,
              (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\UnivOrchLib\\UniversalOrchestratorHelper.cpp",
              (const char *)0x80070005LL,
              (int)"InvalidSignature.  Caller: [%ws] Cmdline: [%ws]",
              (const char *)a2,
              v21);
            std::wstring::~wstring(v44);
            result = 2147942405LL;
          }
        }
        else
        {
          v13 = wil::details::in1diag3::Return_Win32Msg(
                  retaddr,
                  (void *)0x23A,
                  (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\UnivOrchLib\\UniversalOrchestratorHelper.cpp",
                  (const char *)5,
                  (unsigned int)"Caller: %ws Cmdline: %ws",
                  (const char *)a2,
                  a3);
          CoRevertToSelf();
          result = v13;
        }
      }
      catch ( ... )
      {
        return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0x255,
                               (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\UnivOrchLib\\UniversalOrchestratorHelper.cpp",
                               v14);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x232,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\UnivOrchLib\\UniversalOrchestratorHelper.cpp",
        (const char *)0x80070057LL,
        v34);
      return 2147942487LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x231,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\core\\UnivOrchLib\\UniversalOrchestratorHelper.cpp",
      (const char *)0x80070057LL,
      v34);
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800728a0  push    rbx
0x1800728a2  push    rsi
0x1800728a3  push    rdi
0x1800728a4  push    r12
0x1800728a6  push    r13
0x1800728a8  push    r14
0x1800728aa  push    r15
0x1800728ac  sub     rsp, 110h
0x1800728b3  mov     rax, cs:__security_cookie
0x1800728ba  xor     rax, rsp
0x1800728bd  mov     [rsp+148h+var_48], rax
0x1800728c5  mov     r13, r9
0x1800728c8  mov     rsi, r8
0x1800728cb  mov     r14, rdx
0x1800728ce  mov     r12, [rsp+148h+arg_20]
0x1800728d6  xor     edi, edi
0x1800728d8  mov     [rsp+148h+var_104], edi
0x1800728dc  test    rdx, rdx
0x1800728df  jnz     short loc_180072909
0x1800728e1  mov     rcx, [rsp+148h]; this
0x1800728e9  mov     ebx, 80070057h
0x1800728ee  mov     r9d, ebx; char *
0x1800728f1  lea     r8, aCW1SSrcOrchest_48; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x1800728f8  mov     edx, 231h; void *
0x1800728fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072902  mov     eax, ebx
0x180072904  jmp     loc_180072D79
0x180072909  cmp     [rdx], di
0x18007290c  jnz     short loc_180072936
0x18007290e  mov     rcx, [rsp+148h]; this
0x180072916  mov     ebx, 80070057h
0x18007291b  mov     r9d, ebx; char *
0x18007291e  lea     r8, aCW1SSrcOrchest_48; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x180072925  mov     edx, 232h; void *
0x18007292a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007292f  mov     eax, ebx
0x180072931  jmp     loc_180072D79
0x180072936  call    cs:__imp_CoImpersonateClient
0x18007293c  mov     rcx, [rsp+148h]; this
0x180072944  test    eax, eax
0x180072946  js      loc_180072D9C
0x18007294c  mov     [rsp+148h+var_108], 1
0x180072951  lea     rcx, [rsp+148h+var_F8]
0x180072956  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x18007295b  nop
0x18007295c  mov     rcx, [rax]
0x18007295f  mov     rax, [rcx]
0x180072962  mov     rax, [rax+0B0h]
0x180072969  call    _guard_dispatch_icall
0x18007296e  mov     r15b, al
0x180072971  mov     rbx, [rsp+148h+var_F0]
0x180072976  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18007297a  test    rbx, rbx
0x18007297d  jz      short loc_1800729B2
0x18007297f  mov     ecx, edi
0x180072981  lock xadd [rbx+8], ecx
0x180072986  add     ecx, edi
0x180072988  jnz     short loc_1800729B2
0x18007298a  mov     rax, [rbx]
0x18007298d  mov     rcx, rbx
0x180072990  mov     rax, [rax]
0x180072993  call    _guard_dispatch_icall
0x180072998  mov     eax, edi
0x18007299a  lock xadd [rbx+0Ch], eax
0x18007299f  add     eax, edi
0x1800729a1  jnz     short loc_1800729B2
0x1800729a3  mov     rax, [rbx]
0x1800729a6  mov     rcx, rbx
0x1800729a9  mov     rax, [rax+8]
0x1800729ad  call    _guard_dispatch_icall
0x1800729b2  test    r15b, r15b
0x1800729b5  jnz     short loc_1800729FB
0x1800729b7  mov     rcx, [rsp+148h]; this
0x1800729bf  mov     [rsp+148h+var_118], rsi
0x1800729c4  mov     [rsp+148h+var_120], r14; char *
0x1800729c9  lea     rax, aCallerWsCmdlin; "Caller: %ws Cmdline: %ws"
0x1800729d0  mov     qword ptr [rsp+148h+var_128], rax; unsigned int
0x1800729d5  mov     r9d, 5; char *
0x1800729db  lea     r8, aCW1SSrcOrchest_48; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x1800729e2  mov     edx, 23Ah; void *
0x1800729e7  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x1800729ec  mov     ebx, eax
0x1800729ee  call    cs:__imp_CoRevertToSelf
0x1800729f4  mov     eax, ebx
0x1800729f6  jmp     loc_180072D79
0x1800729fb  call    cs:__imp_CoRevertToSelf
0x180072a01  mov     r8, rsi
0x180072a04  mov     rdx, r14
0x180072a07  lea     rcx, [rsp+148h+var_68]
0x180072a0f  call    ?VerifyUpdaterPath@PathVerification@Windows@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0@Z; Windows::PathVerification::VerifyUpdaterPath(wchar_t const *,wchar_t const *)
0x180072a14  nop
0x180072a15  lea     rcx, [rsp+148h+var_F8]
0x180072a1a  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x180072a1f  nop
0x180072a20  mov     [rsp+148h+var_104], 3
0x180072a28  mov     rcx, [rax]
0x180072a2b  mov     rax, [rcx]
0x180072a2e  mov     rax, [rax+0B8h]
0x180072a35  call    _guard_dispatch_icall
0x180072a3a  xor     r15d, r15d
0x180072a3d  test    al, al
0x180072a3f  jz      short loc_180072A4D
0x180072a41  call    ?IsUMCIEnabled@Trust@Windows@@YA_NXZ; Windows::Trust::IsUMCIEnabled(void)
0x180072a46  test    al, al
0x180072a48  mov     sil, r15b
0x180072a4b  jnz     short loc_180072A50
0x180072a4d  mov     sil, 1
0x180072a50  mov     rbx, [rsp+148h+var_F0]
0x180072a55  test    rbx, rbx
0x180072a58  jz      short loc_180072A8D
0x180072a5a  mov     eax, edi
0x180072a5c  lock xadd [rbx+8], eax
0x180072a61  add     eax, edi
0x180072a63  jnz     short loc_180072A8D
0x180072a65  mov     rax, [rbx]
0x180072a68  mov     rcx, rbx
0x180072a6b  mov     rax, [rax]
0x180072a6e  call    _guard_dispatch_icall
0x180072a73  mov     eax, edi
0x180072a75  lock xadd [rbx+0Ch], eax
0x180072a7a  add     eax, edi
0x180072a7c  jnz     short loc_180072A8D
0x180072a7e  mov     rax, [rbx]
0x180072a81  mov     rcx, rbx
0x180072a84  mov     rax, [rax+8]
0x180072a88  call    _guard_dispatch_icall
0x180072a8d  test    sil, sil
0x180072a90  jz      loc_180072B3B
0x180072a96  lea     rcx, [rsp+148h+var_68]
0x180072a9e  cmp     [rsp+148h+var_50], 7
0x180072aa7  cmova   rcx, [rsp+148h+var_68]
0x180072ab0  mov     rax, rdi
0x180072ab3  inc     rax
0x180072ab6  cmp     [rcx+rax*2], r15w
0x180072abb  jnz     short loc_180072AB3
0x180072abd  mov     [rsp+148h+var_F8], rcx
0x180072ac2  mov     [rsp+148h+var_F0], rax
0x180072ac7  lea     rcx, [rsp+148h+var_F8]
0x180072acc  call    ?IsSelfSignedOrCatalogSignedFile@Trust@Windows@@YA_NV?$basic_zstring_view@_W@wil@@_N@Z; Windows::Trust::IsSelfSignedOrCatalogSignedFile(wil::basic_zstring_view<wchar_t>,bool)
0x180072ad1  test    al, al
0x180072ad3  jnz     short loc_180072B3B
0x180072ad5  lea     rax, [rsp+148h+var_68]
0x180072add  cmp     [rsp+148h+var_50], 7
0x180072ae6  cmova   rax, [rsp+148h+var_68]
0x180072aef  mov     rcx, [rsp+148h]; this
0x180072af7  mov     [rsp+148h+var_118], rax
0x180072afc  mov     [rsp+148h+var_120], r14; char *
0x180072b01  lea     rax, aInvalidsignatu; "InvalidSignature.  Caller: [%ws] Cmdlin"...
0x180072b08  mov     qword ptr [rsp+148h+var_128], rax; int
0x180072b0d  mov     ebx, 80070005h
0x180072b12  mov     r9d, ebx; char *
0x180072b15  lea     r8, aCW1SSrcOrchest_48; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x180072b1c  mov     edx, 246h; void *
0x180072b21  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180072b26  nop
0x180072b27  lea     rcx, [rsp+148h+var_68]; void *
0x180072b2f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180072b34  mov     eax, ebx
0x180072b36  jmp     loc_180072D79
0x180072b3b  xorps   xmm0, xmm0
0x180072b3e  movups  [rsp+148h+var_98], xmm0
0x180072b46  xorps   xmm1, xmm1
0x180072b49  movdqu  [rsp+148h+var_88], xmm1
0x180072b52  mov     r8, rdi
0x180072b55  inc     r8
0x180072b58  cmp     [r12+r8*2], r15w
0x180072b5d  jnz     short loc_180072B55
0x180072b5f  mov     rdx, r12
0x180072b62  lea     rcx, [rsp+148h+var_98]
0x180072b6a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180072b6f  mov     esi, 1
0x180072b74  mov     [rsp+148h+var_78], sil
0x180072b7c  xorps   xmm0, xmm0
0x180072b7f  movups  [rsp+148h+var_C0], xmm0
0x180072b87  xorps   xmm1, xmm1
0x180072b8a  movdqu  [rsp+148h+var_B0], xmm1
0x180072b93  mov     r8, rdi
0x180072b96  inc     r8
0x180072b99  cmp     [r13+r8*2+0], r15w
0x180072b9f  jnz     short loc_180072B96
0x180072ba1  mov     rdx, r13
0x180072ba4  lea     rcx, [rsp+148h+var_C0]
0x180072bac  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180072bb1  mov     [rsp+148h+var_A0], sil
0x180072bb9  lea     rdx, [rsp+148h+var_68]
0x180072bc1  cmp     [rsp+148h+var_50], 7
0x180072bca  cmova   rdx, [rsp+148h+var_68]
0x180072bd3  xorps   xmm0, xmm0
0x180072bd6  movups  [rsp+148h+var_E8], xmm0
0x180072bdb  xorps   xmm1, xmm1
0x180072bde  movdqu  [rsp+148h+var_D8], xmm1
0x180072be4  mov     r8, rdi
0x180072be7  inc     r8
0x180072bea  cmp     [rdx+r8*2], r15w
0x180072bef  jnz     short loc_180072BE7
0x180072bf1  lea     rcx, [rsp+148h+var_E8]
0x180072bf6  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180072bfb  mov     [rsp+148h+var_C8], sil
0x180072c03  mov     rax, rdi
0x180072c06  inc     rax
0x180072c09  cmp     [r14+rax*2], r15w
0x180072c0e  jnz     short loc_180072C06
0x180072c10  mov     [rsp+148h+var_F8], r14
0x180072c15  mov     [rsp+148h+var_F0], rax
0x180072c1a  lea     rax, [rsp+148h+var_98]
0x180072c22  mov     qword ptr [rsp+148h+var_128], rax
0x180072c27  lea     r9, [rsp+148h+var_C0]
0x180072c2f  lea     r8, [rsp+148h+var_E8]
0x180072c34  lea     rdx, [rsp+148h+var_F8]
0x180072c39  call    ?QueueWork@UniversalOrchestrator@@AEAAXV?$basic_zstring_view@_W@wil@@AEBV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@11@Z; UniversalOrchestrator::QueueWork(wil::basic_zstring_view<wchar_t>,std::optional<std::wstring> const &,std::optional<std::wstring> const &,std::optional<std::wstring> const &)
0x180072c3e  nop
0x180072c3f  cmp     [rsp+148h+var_C8], r15b
0x180072c47  jz      short loc_180072C54
0x180072c49  lea     rcx, [rsp+148h+var_E8]; void *
0x180072c4e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180072c53  nop
0x180072c54  cmp     [rsp+148h+var_A0], r15b
0x180072c5c  jz      short loc_180072C6C
0x180072c5e  lea     rcx, [rsp+148h+var_C0]; void *
0x180072c66  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180072c6b  nop
0x180072c6c  cmp     [rsp+148h+var_78], r15b
0x180072c74  jz      short loc_180072C83
0x180072c76  lea     rcx, [rsp+148h+var_98]; void *
0x180072c7e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180072c83  mov     [rsp+148h+var_70], r15
0x180072c8b  xor     r8d, r8d
0x180072c8e  lea     r11, word_180121B5A
0x180072c95  mov     rdx, r11
0x180072c98  lea     rbx, aLegacyuoprovid_0; "LegacyUOProvider"
0x180072c9f  mov     rcx, rbx
0x180072ca2  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x180072ca7  cmp     rax, r11
0x180072caa  jz      loc_180072DB1
0x180072cb0  sub     rax, rbx
0x180072cb3  sar     rax, 1
0x180072cb6  cmp     rax, rdi
0x180072cb9  jz      loc_180072DB1
0x180072cbf  mov     [rsp+148h+var_F8], rbx
0x180072cc4  mov     [rsp+148h+var_F0], rax
0x180072cc9  lea     rdx, [rsp+148h+var_F8]
0x180072cce  lea     rcx, [rsp+148h+var_70]
0x180072cd6  call    ?GetUpdateManager@@YA?AV?$com_ptr_t@UIUpdateManager@@Uerr_exception_policy@wil@@@wil@@V?$basic_zstring_view@_W@2@@Z; GetUpdateManager(wil::basic_zstring_view<wchar_t>)
0x180072cdb  nop
0x180072cdc  mov     rcx, [rsp+148h+var_70]
0x180072ce4  mov     rax, [rcx]
0x180072ce7  mov     [rsp+148h+var_128], esi; int
0x180072ceb  mov     r9d, esi
0x180072cee  xor     r8d, r8d
0x180072cf1  xor     edx, edx
0x180072cf3  mov     rax, [rax+48h]
0x180072cf7  call    _guard_dispatch_icall
0x180072cfc  mov     ebx, eax
0x180072cfe  test    eax, eax
0x180072d00  jns     short loc_180072D4A
0x180072d02  mov     rcx, [rsp+148h]; this
0x180072d0a  mov     r9d, eax; char *
0x180072d0d  lea     r8, aCW1SSrcOrchest_48; "C:\\__w\\1\\s\\src\\orchestrator\\core"...
0x180072d14  mov     edx, 251h; void *
0x180072d19  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180072d1e  nop
0x180072d1f  mov     rcx, [rsp+148h+var_70]
0x180072d27  test    rcx, rcx
0x180072d2a  jz      short loc_180072D39
0x180072d2c  mov     rax, [rcx]
0x180072d2f  mov     rax, [rax+10h]
0x180072d33  call    _guard_dispatch_icall
0x180072d38  nop
0x180072d39  lea     rcx, [rsp+148h+var_68]; void *
0x180072d41  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180072d46  mov     eax, ebx
0x180072d48  jmp     short loc_180072D79
0x180072d4a  mov     rcx, [rsp+148h+var_70]
0x180072d52  test    rcx, rcx
0x180072d55  jz      short loc_180072D64
0x180072d57  mov     rax, [rcx]
0x180072d5a  mov     rax, [rax+10h]
0x180072d5e  call    _guard_dispatch_icall
0x180072d63  nop
0x180072d64  lea     rcx, [rsp+148h+var_68]; void *
0x180072d6c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180072d71  xor     eax, eax
0x180072d73  jmp     short loc_180072D79
0x180072d75  mov     eax, [rsp+148h+var_104]
0x180072d79  mov     rcx, [rsp+148h+var_48]
0x180072d81  xor     rcx, rsp; StackCookie
0x180072d84  call    __security_check_cookie
0x180072d89  add     rsp, 110h
0x180072d90  pop     r15
0x180072d92  pop     r14
0x180072d94  pop     r13
0x180072d96  pop     r12
0x180072d98  pop     rdi
0x180072d99  pop     rsi
0x180072d9a  pop     rbx
0x180072d9b  retn
0x180072d9c  mov     r9d, eax; char *
0x180072d9f  lea     r8, aCW1SPackagesMi_4; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x180072da6  mov     edx, 1262h; void *
0x180072dab  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
  ... truncated ...
```
