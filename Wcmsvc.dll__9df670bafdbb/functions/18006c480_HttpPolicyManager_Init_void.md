# HttpPolicyManager::Init(void)

- ea: `0x18006c480`
- end: `0x18006c5c1`
- name: `?Init@HttpPolicyManager@@SAKXZ`
- size: `321`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18006c3d8`

## callees

- `0x180010080`
- `0x1800137a0`
- `0x180034470`
- `0x18006c480`
- `0x18007b57c`
- `0x18008534c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006c492`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006c492`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c56e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c56e`
- `WINHTTP!WinHttpOpen` at `0x18006c560`
- `WINHTTP!WinHttpOpen` at `0x18006c560`

## string_xrefs

- `0x18006c4a9`: `onecoreuap\net\wcm\service\base\selection\lib\httppolicymanager.cpp`

## pseudocode

```c
__int64 HttpPolicyManager::Init(void)
{
  HANDLE EventW; // rax
  const char *v1; // r9
  std::_Ref_count_base *v2; // rax
  std::_Ref_count_base *v3; // rcx
  __int64 v4; // rcx
  std::_Ref_count_base *v5; // rcx
  _QWORD *v6; // rbx
  HINTERNET v7; // rax
  DWORD LastError; // ebx
  __int64 result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  EventW = CreateEventW(0, 1, 0, 0);
  try
  {
    g_httpPolicyManagerExitHandle = EventW;
    if ( !EventW )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x14,
        (unsigned int)"onecoreuap\\net\\wcm\\service\\base\\selection\\lib\\httppolicymanager.cpp",
        v1);
    v2 = (std::_Ref_count_base *)operator new(0x18u);
    *((_DWORD *)v2 + 2) = 1;
    *((_DWORD *)v2 + 3) = 1;
    *(_QWORD *)v2 = &std::_Ref_count_obj2<HttpPolicyManager>::`vftable';
    *((_QWORD *)v2 + 2) = 0;
    HttpPolicyManager::s_HttpPolicyManagerInstance = (__int64)v2 + 16;
    v3 = qword_180140100;
    qword_180140100 = v2;
    if ( v3 )
    {
      std::_Ref_count_base::_Decref(v3);
      v2 = qword_180140100;
    }
    if ( v2 )
    {
      v4 = HttpPolicyManager::s_HttpPolicyManagerInstance;
      _InterlockedIncrement((volatile signed __int32 *)v2 + 3);
    }
    else
    {
      v4 = 0;
      v2 = 0;
    }
    qword_1801400E8 = v4;
    v5 = qword_1801400F0;
    qword_1801400F0 = v2;
    if ( v5 )
      std::_Ref_count_base::_Decwref(v5);
    v6 = (_QWORD *)HttpPolicyManager::s_HttpPolicyManagerInstance;
    v7 = WinHttpOpen(L"WCM", 1u, 0, 0, 0);
    *v6 = v7;
    if ( v7 )
    {
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 11, WPP_1af9fc7ab7b7322054bb1175abdcc28e_Traceguids, LastError);
      }
    }
    result = LastError;
  }
  catch ( std::exception )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u
      && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 10, WPP_1af9fc7ab7b7322054bb1175abdcc28e_Traceguids);
    }
    if ( g_httpPolicyManagerExitHandle )
    {
      CloseHandle(g_httpPolicyManagerExitHandle);
      g_httpPolicyManagerExitHandle = 0;
    }
    return 8;
  }
  return result;
}

```

## disassembly

```asm
0x18006c480  push    rbx
0x18006c482  sub     rsp, 30h
0x18006c486  xor     r9d, r9d; lpName
0x18006c489  xor     r8d, r8d; bInitialState
0x18006c48c  lea     edx, [r9+1]; bManualReset
0x18006c490  xor     ecx, ecx; lpEventAttributes
0x18006c492  call    cs:__imp_CreateEventW
0x18006c498  mov     cs:?g_httpPolicyManagerExitHandle@@3PEAXEA, rax; void * g_httpPolicyManagerExitHandle
0x18006c49f  test    rax, rax
0x18006c4a2  jnz     short loc_18006C4B8
0x18006c4a4  mov     rcx, [rsp+38h]; this
0x18006c4a9  lea     r8, aOnecoreuapNetW_0; "onecoreuap\\net\\wcm\\service\\base\\se"...
0x18006c4b0  lea     edx, [rax+14h]; void *
0x18006c4b3  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18006c4b8  mov     ecx, 18h; Size
0x18006c4bd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006c4c2  mov     dword ptr [rax+8], 1
0x18006c4c9  mov     dword ptr [rax+0Ch], 1
0x18006c4d0  lea     rcx, ??_7?$_Ref_count_obj2@VHttpPolicyManager@@@std@@6B@; const std::_Ref_count_obj2<HttpPolicyManager>::`vftable'
0x18006c4d7  mov     [rax], rcx
0x18006c4da  lea     rcx, [rax+10h]
0x18006c4de  mov     qword ptr [rcx], 0
0x18006c4e5  mov     cs:?s_HttpPolicyManagerInstance@HttpPolicyManager@@0V?$shared_ptr@VHttpPolicyManager@@@std@@A, rcx; std::shared_ptr<HttpPolicyManager> HttpPolicyManager::s_HttpPolicyManagerInstance
0x18006c4ec  mov     rcx, cs:qword_180140100; this
0x18006c4f3  mov     cs:qword_180140100, rax
0x18006c4fa  test    rcx, rcx
0x18006c4fd  jz      short loc_18006C50B
0x18006c4ff  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18006c504  mov     rax, cs:qword_180140100
0x18006c50b  test    rax, rax
0x18006c50e  jz      short loc_18006C51D
0x18006c510  mov     rcx, cs:?s_HttpPolicyManagerInstance@HttpPolicyManager@@0V?$shared_ptr@VHttpPolicyManager@@@std@@A; std::shared_ptr<HttpPolicyManager> HttpPolicyManager::s_HttpPolicyManagerInstance
0x18006c517  lock inc dword ptr [rax+0Ch]
0x18006c51b  jmp     short loc_18006C521
0x18006c51d  xor     ecx, ecx
0x18006c51f  xor     eax, eax
0x18006c521  mov     cs:qword_1801400E8, rcx
0x18006c528  mov     rcx, cs:qword_1801400F0; this
0x18006c52f  mov     cs:qword_1801400F0, rax
0x18006c536  test    rcx, rcx
0x18006c539  jz      short loc_18006C540
0x18006c53b  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18006c540  mov     rbx, cs:?s_HttpPolicyManagerInstance@HttpPolicyManager@@0V?$shared_ptr@VHttpPolicyManager@@@std@@A; std::shared_ptr<HttpPolicyManager> HttpPolicyManager::s_HttpPolicyManagerInstance
0x18006c547  mov     [rsp+38h+dwFlags], 0; dwFlags
0x18006c54f  xor     r9d, r9d; pszProxyBypassW
0x18006c552  xor     r8d, r8d; pszProxyW
0x18006c555  lea     edx, [r9+1]; dwAccessType
0x18006c559  lea     rcx, pszAgentW; "WCM"
0x18006c560  call    cs:__imp_WinHttpOpen
0x18006c566  mov     [rbx], rax
0x18006c569  test    rax, rax
0x18006c56c  jnz     short loc_18006C5AF
0x18006c56e  call    cs:__imp_GetLastError
0x18006c574  mov     ebx, eax
0x18006c576  lea     rax, WPP_GLOBAL_Control
0x18006c57d  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c584  cmp     rcx, rax
0x18006c587  jz      short loc_18006C5B1
0x18006c589  cmp     byte ptr [rcx+19h], 2
0x18006c58d  jb      short loc_18006C5B1
0x18006c58f  test    byte ptr [rcx+1Ch], 1
0x18006c593  jz      short loc_18006C5B1
0x18006c595  mov     edx, 0Bh
0x18006c59a  mov     r9d, ebx
0x18006c59d  lea     r8, WPP_1af9fc7ab7b7322054bb1175abdcc28e_Traceguids
0x18006c5a4  mov     rcx, [rcx+10h]
0x18006c5a8  call    WPP_SF_d
0x18006c5ad  jmp     short loc_18006C5B1
0x18006c5af  xor     ebx, ebx
0x18006c5b1  mov     eax, ebx
0x18006c5b3  jmp     short loc_18006C5BA
0x18006c5b5  mov     eax, 8
0x18006c5ba  add     rsp, 30h
0x18006c5be  pop     rbx
0x18006c5bf  retn
```
