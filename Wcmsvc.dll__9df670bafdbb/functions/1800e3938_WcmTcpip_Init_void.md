# WcmTcpip::Init(void)

- ea: `0x1800e3938`
- end: `0x1800e3b2e`
- name: `?Init@WcmTcpip@@SAKXZ`
- size: `502`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800b0d60`

## callees

- `0x180010080`
- `0x1800184e8`
- `0x180019434`
- `0x180027630`
- `0x180034470`
- `0x18007b57c`
- `0x18008534c`
- `0x1800e2820`
- `0x1800e28d4`
- `0x1800e3070`
- `0x1800e3938`
- `0x1800e3bdc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e3ac7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e3afe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e3ac7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e3afe`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e39c2`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800e39c2`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800e3b13`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800e3b13`

## string_xrefs

- `0x1800e39d9`: `onecoreuap\net\wcm\service\base\wcmtcpip\wcmtcpip.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 WcmTcpip::Init(void)
{
  __int64 result; // rax
  HANDLE EventW; // rax
  const char *v2; // r9
  struct _RTL_CRITICAL_SECTION *v3; // rbx
  std::_Ref_count_base *v4; // rcx
  WcmTcpip *v5; // rax
  std::_Ref_count_base *v6; // rcx
  unsigned int started; // edi
  WcmTcpip *v8; // rbx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+30h] [rbp+8h] BYREF
  WcmTcpip *v11; // [rsp+38h] [rbp+10h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
    && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, &WPP_a69e3d30d60831f26448b35f4a7aba9c_Traceguids);
  }
  if ( (unsigned int)IsServerSKU() )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, &WPP_a69e3d30d60831f26448b35f4a7aba9c_Traceguids);
    }
    return 50;
  }
  else
  {
    EventW = CreateEventW(0, 1, 0, 0);
    try
    {
      g_wcmTcpipExitHandle = EventW;
      if ( !EventW )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x32,
          (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\wcmtcpip\\wcmtcpip.cpp",
          v2);
      v3 = (struct _RTL_CRITICAL_SECTION *)operator new(0x198u);
      lpCriticalSection = v3;
      v3->LockCount = 1;
      v3->RecursionCount = 1;
      v3->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&std::_Ref_count_obj2<WcmTcpip>::`vftable';
      WcmTcpip::WcmTcpip((WcmTcpip *)&v3->OwningThread);
      WcmTcpip::s_WcmTcpipInstance = (WcmTcpip *)&v3->OwningThread;
      v4 = qword_180140180;
      qword_180140180 = (std::_Ref_count_base *)v3;
      if ( v4 )
      {
        std::_Ref_count_base::_Decref(v4);
        v3 = (struct _RTL_CRITICAL_SECTION *)qword_180140180;
      }
      if ( v3 )
      {
        v5 = WcmTcpip::s_WcmTcpipInstance;
        _InterlockedIncrement(&v3->RecursionCount);
      }
      else
      {
        v5 = 0;
        v3 = 0;
      }
      *(_QWORD *)&xmmword_180140188 = v5;
      v6 = (std::_Ref_count_base *)*((_QWORD *)&xmmword_180140188 + 1);
      *((_QWORD *)&xmmword_180140188 + 1) = v3;
      if ( v6 )
        std::_Ref_count_base::_Decwref(v6);
      started = WcmTcpip::StartListeners(WcmTcpip::s_WcmTcpipInstance);
      if ( !started )
      {
        v8 = WcmTcpip::s_WcmTcpipInstance;
        v11 = WcmTcpip::s_WcmTcpipInstance;
        lpCriticalSection = 0;
        wil::EnterCriticalSection(&lpCriticalSection, (char *)WcmTcpip::s_WcmTcpipInstance + 8);
        if ( *((_BYTE *)v8 + 272) )
        {
          if ( lpCriticalSection )
            LeaveCriticalSection(lpCriticalSection);
        }
        else
        {
          if ( *(_DWORD *)v8 == 1 )
            std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__WcmTcpip::Init_::_9_::_lambda_1___(
              (char *)v8 + 152,
              &v11);
          else
            std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__WcmTcpip::Init_::_9_::_lambda_1___(
              (char *)v8 + 232,
              &v11);
          if ( lpCriticalSection )
            LeaveCriticalSection(lpCriticalSection);
          _InterlockedIncrement64((volatile signed __int64 *)v8 + 17);
          SubmitThreadpoolWork(*((PTP_WORK *)v8 + 16));
        }
      }
      result = started;
    }
    catch ( std::exception )
    {
      if ( g_wcmTcpipExitHandle )
      {
        CloseHandle(g_wcmTcpipExitHandle);
        g_wcmTcpipExitHandle = 0;
      }
      return 8;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800e3938  mov     [rsp+arg_10], rbx
0x1800e393d  push    rdi
0x1800e393e  sub     rsp, 20h
0x1800e3942  lea     rbx, WPP_GLOBAL_Control
0x1800e3949  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e3950  cmp     rcx, rbx
0x1800e3953  jz      short loc_1800E3976
0x1800e3955  cmp     byte ptr [rcx+19h], 4
0x1800e3959  jb      short loc_1800E3976
0x1800e395b  test    byte ptr [rcx+1Ch], 1
0x1800e395f  jz      short loc_1800E3976
0x1800e3961  mov     edx, 0Ah
0x1800e3966  lea     r8, WPP_a69e3d30d60831f26448b35f4a7aba9c_Traceguids
0x1800e396d  mov     rcx, [rcx+10h]
0x1800e3971  call    WPP_SF_
0x1800e3976  call    IsServerSKU
0x1800e397b  test    eax, eax
0x1800e397d  jz      short loc_1800E39B6
0x1800e397f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e3986  cmp     rcx, rbx
0x1800e3989  jz      short loc_1800E39AC
0x1800e398b  cmp     byte ptr [rcx+19h], 4
0x1800e398f  jb      short loc_1800E39AC
0x1800e3991  test    byte ptr [rcx+1Ch], 1
0x1800e3995  jz      short loc_1800E39AC
0x1800e3997  mov     edx, 0Bh
0x1800e399c  lea     r8, WPP_a69e3d30d60831f26448b35f4a7aba9c_Traceguids
0x1800e39a3  mov     rcx, [rcx+10h]
0x1800e39a7  call    WPP_SF_
0x1800e39ac  mov     eax, 32h ; '2'
0x1800e39b1  jmp     loc_1800E3B22
0x1800e39b6  xor     r9d, r9d; lpName
0x1800e39b9  xor     r8d, r8d; bInitialState
0x1800e39bc  lea     edx, [r9+1]; bManualReset
0x1800e39c0  xor     ecx, ecx; lpEventAttributes
0x1800e39c2  call    cs:__imp_CreateEventW
0x1800e39c8  mov     cs:?g_wcmTcpipExitHandle@@3PEAXEA, rax; void * g_wcmTcpipExitHandle
0x1800e39cf  mov     rcx, [rsp+28h]; this
0x1800e39d4  test    rax, rax
0x1800e39d7  jnz     short loc_1800E39E8
0x1800e39d9  lea     r8, aOnecoreuapNetW_1; "onecoreuap\\net\\wcm\\service\\base\\wc"...
0x1800e39e0  lea     edx, [rax+32h]; void *
0x1800e39e3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800e39e8  mov     ecx, 198h; Size
0x1800e39ed  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800e39f2  mov     rbx, rax
0x1800e39f5  mov     [rsp+28h+lpCriticalSection], rax
0x1800e39fa  mov     dword ptr [rax+8], 1
0x1800e3a01  mov     dword ptr [rax+0Ch], 1
0x1800e3a08  lea     rax, ??_7?$_Ref_count_obj2@VWcmTcpip@@@std@@6B@; const std::_Ref_count_obj2<WcmTcpip>::`vftable'
0x1800e3a0f  mov     [rbx], rax
0x1800e3a12  lea     rdi, [rbx+10h]
0x1800e3a16  mov     rcx, rdi; this
0x1800e3a19  call    ??0WcmTcpip@@QEAA@XZ; WcmTcpip::WcmTcpip(void)
0x1800e3a1e  nop
0x1800e3a1f  mov     cs:?s_WcmTcpipInstance@WcmTcpip@@0V?$shared_ptr@VWcmTcpip@@@std@@A, rdi; std::shared_ptr<WcmTcpip> WcmTcpip::s_WcmTcpipInstance
0x1800e3a26  mov     rcx, cs:qword_180140180; this
0x1800e3a2d  mov     cs:qword_180140180, rbx
0x1800e3a34  test    rcx, rcx
0x1800e3a37  jz      short loc_1800E3A45
0x1800e3a39  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800e3a3e  mov     rbx, cs:qword_180140180
0x1800e3a45  test    rbx, rbx
0x1800e3a48  jz      short loc_1800E3A57
0x1800e3a4a  mov     rax, cs:?s_WcmTcpipInstance@WcmTcpip@@0V?$shared_ptr@VWcmTcpip@@@std@@A; std::shared_ptr<WcmTcpip> WcmTcpip::s_WcmTcpipInstance
0x1800e3a51  lock inc dword ptr [rbx+0Ch]
0x1800e3a55  jmp     short loc_1800E3A5B
0x1800e3a57  xor     eax, eax
0x1800e3a59  xor     ebx, ebx
0x1800e3a5b  mov     qword ptr cs:xmmword_180140188, rax
0x1800e3a62  mov     rcx, qword ptr cs:xmmword_180140188+8; this
0x1800e3a69  mov     qword ptr cs:xmmword_180140188+8, rbx
0x1800e3a70  test    rcx, rcx
0x1800e3a73  jz      short loc_1800E3A7A
0x1800e3a75  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x1800e3a7a  mov     rcx, cs:?s_WcmTcpipInstance@WcmTcpip@@0V?$shared_ptr@VWcmTcpip@@@std@@A; this
0x1800e3a81  call    ?StartListeners@WcmTcpip@@AEAAKXZ; WcmTcpip::StartListeners(void)
0x1800e3a86  mov     edi, eax
0x1800e3a88  test    eax, eax
0x1800e3a8a  jnz     loc_1800E3B19
0x1800e3a90  mov     rbx, cs:?s_WcmTcpipInstance@WcmTcpip@@0V?$shared_ptr@VWcmTcpip@@@std@@A; std::shared_ptr<WcmTcpip> WcmTcpip::s_WcmTcpipInstance
0x1800e3a97  mov     [rsp+28h+arg_8], rbx
0x1800e3a9c  mov     [rsp+28h+lpCriticalSection], 0
0x1800e3aa5  lea     rdx, [rbx+8]
0x1800e3aa9  lea     rcx, [rsp+28h+lpCriticalSection]
0x1800e3aae  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800e3ab3  nop
0x1800e3ab4  cmp     [rbx+110h], dil
0x1800e3abb  jz      short loc_1800E3ACF
0x1800e3abd  mov     rcx, [rsp+28h+lpCriticalSection]; lpCriticalSection
0x1800e3ac2  test    rcx, rcx
0x1800e3ac5  jz      short loc_1800E3B19
0x1800e3ac7  call    cs:__imp_LeaveCriticalSection
0x1800e3acd  jmp     short loc_1800E3B19
0x1800e3acf  lea     rdx, [rsp+28h+arg_8]
0x1800e3ad4  cmp     dword ptr [rbx], 1
0x1800e3ad7  jnz     short loc_1800E3AE7
0x1800e3ad9  lea     rcx, [rbx+98h]
0x1800e3ae0  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__WcmTcpip__Init____9____lambda_1___
0x1800e3ae5  jmp     short loc_1800E3AF4
0x1800e3ae7  lea     rcx, [rbx+0E8h]
0x1800e3aee  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__WcmTcpip__Init____9____lambda_1___
0x1800e3af3  nop
0x1800e3af4  mov     rcx, [rsp+28h+lpCriticalSection]; lpCriticalSection
0x1800e3af9  test    rcx, rcx
0x1800e3afc  jz      short loc_1800E3B04
0x1800e3afe  call    cs:__imp_LeaveCriticalSection
0x1800e3b04  lock inc qword ptr [rbx+88h]
0x1800e3b0c  mov     rcx, [rbx+80h]; pwk
0x1800e3b13  call    cs:__imp_SubmitThreadpoolWork
0x1800e3b19  mov     eax, edi
0x1800e3b1b  jmp     short loc_1800E3B22
0x1800e3b1d  mov     eax, 8
0x1800e3b22  mov     rbx, [rsp+28h+arg_10]
0x1800e3b27  add     rsp, 20h
0x1800e3b2b  pop     rdi
0x1800e3b2c  retn
```
