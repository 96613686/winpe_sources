# wWinMain

- ea: `0x14001c3d4`
- end: `0x14001c67f`
- name: `wWinMain`
- size: `683`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140003470`

## callees

- `0x1400032f0`
- `0x140006140`
- `0x140007300`
- `0x14000aec8`
- `0x14000e920`
- `0x1400136fc`
- `0x1400172ac`
- `0x14001c3d4`
- `0x14001f010`

## import_xrefs

- `ADVAPI32!GetSidSubAuthority` at `0x14001c44e`
- `ADVAPI32!GetSidSubAuthority` at `0x14001c459`
- `ADVAPI32!GetSidSubAuthority` at `0x14001c44e`
- `ADVAPI32!GetSidSubAuthority` at `0x14001c459`
- `KERNEL32!FindStringOrdinal` at `0x14001c5b3`
- `KERNEL32!FindStringOrdinal` at `0x14001c5e1`
- `KERNEL32!FindStringOrdinal` at `0x14001c60f`
- `KERNEL32!FindStringOrdinal` at `0x14001c5b3`
- `KERNEL32!FindStringOrdinal` at `0x14001c5e1`
- `KERNEL32!FindStringOrdinal` at `0x14001c60f`
- `KERNEL32!GetCurrentThreadId` at `0x14001c551`
- `KERNEL32!GetCurrentThreadId` at `0x14001c551`
- `USER32!TranslateMessage` at `0x14001c63e`
- `USER32!TranslateMessage` at `0x14001c63e`
- `USER32!DispatchMessageW` at `0x14001c648`
- `USER32!DispatchMessageW` at `0x14001c648`
- `USER32!GetMessageW` at `0x14001c65a`
- `USER32!GetMessageW` at `0x14001c65a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14001c3ec`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14001c3ec`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001c4a6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14001c4a6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14001c66c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14001c66c`

## string_xrefs

- `0x14001c41c`: `pcshell\shell\auth\creduibroker\exe\creduibroker.cpp`
- `0x14001c4bb`: `pcshell\shell\auth\creduibroker\exe\creduibroker.cpp`

## pseudocode

```c
int __stdcall wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)
{
  int token_information; // eax
  int v6; // ebx
  PSID *v8; // rbx
  HRESULT v9; // edi
  __int64 v10; // rdx
  DWORD CurrentThreadId; // edi
  __int64 v12; // rbx
  struct Microsoft::WRL::Details::ModuleBase *v13; // rdx
  const unsigned __int16 *v14; // r8
  int ppv; // [rsp+20h] [rbp-50h]
  int ppva; // [rsp+20h] [rbp-50h]
  void *Block; // [rsp+30h] [rbp-40h] BYREF
  __int64 v18; // [rsp+38h] [rbp-38h] BYREF
  MSG Msg; // [rsp+40h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  if ( CoInitializeEx(0, 2u) < 0 )
    return 0;
  Block = 0;
  token_information = wil::get_token_information_nothrow<_TOKEN_MANDATORY_LABEL,0>(&Block, -4);
  v6 = token_information;
  if ( token_information < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x30C,
      (unsigned int)"pcshell\\shell\\auth\\creduibroker\\exe\\creduibroker.cpp",
      (const char *)(unsigned int)token_information,
      ppv);
    if ( Block )
      operator delete(Block);
    return v6;
  }
  v8 = (PSID *)Block;
  GetSidSubAuthority(*(PSID *)Block, 0);
  if ( *GetSidSubAuthority(*v8, 0) <= 0x2000 )
  {
LABEL_17:
    if ( v8 )
      operator delete(v8);
    CurrentThreadId = GetCurrentThreadId();
    v12 = Microsoft::WRL::Details::OutOfProcModuleBase<CSingleUseOutOfProcModule>::Create();
    if ( !*(_QWORD *)(v12 + 8) )
    {
      byte_14002A680 = 1;
      qword_14002A668 = (__int64)off_140021620;
      byte_14002A670 = 0;
      dword_14002A678 = CurrentThreadId;
      *(_QWORD *)(v12 + 8) = &qword_14002A668;
    }
    if ( FindStringOrdinal(0x400000u, lpCmdLine, -1, L"NonAppContainerFailedMip", -1, 1) == -1 )
    {
      if ( FindStringOrdinal(0x400000u, lpCmdLine, -1, L"NonAppContainer", -1, 1) == -1 )
      {
        if ( FindStringOrdinal(0x400000u, lpCmdLine, -1, L"AppContainer", -1, 1) != -1 )
          *(_DWORD *)(v12 + 16) = 1;
      }
      else
      {
        *(_DWORD *)(v12 + 16) = 2;
      }
    }
    else
    {
      *(_DWORD *)(v12 + 16) = 3;
    }
    if ( (int)Microsoft::WRL::Details::RegisterObjects<2>(v12) >= 0 )
    {
      memset(&Msg, 0, sizeof(Msg));
      while ( GetMessageW(&Msg, 0, 0, 0) > 0 )
      {
        TranslateMessage(&Msg);
        DispatchMessageW(&Msg);
      }
      Microsoft::WRL::Details::UnregisterObjects((Microsoft::WRL::Details *)v12, v13, v14);
    }
    CoUninitialize();
    return 0;
  }
  Block = 0;
  v18 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&Block);
  v9 = CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, &Block);
  if ( v9 >= 0 )
  {
    v9 = (*(__int64 (__fastcall **)(void *, __int64, __int64 *))(*(_QWORD *)Block + 32LL))(Block, 4, &v18);
    if ( v9 < 0 )
    {
      v10 = 792;
      goto LABEL_9;
    }
    v9 = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)Block + 24LL))(Block, 4, v18 | 0x100);
    if ( v9 < 0 )
    {
      v10 = 793;
      goto LABEL_9;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&Block);
    goto LABEL_17;
  }
  v10 = 791;
LABEL_9:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"pcshell\\shell\\auth\\creduibroker\\exe\\creduibroker.cpp",
    (const char *)(unsigned int)v9,
    ppva);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&Block);
  if ( v8 )
    operator delete(v8);
  return v9;
}

```

## disassembly

```asm
0x14001c3d4  push    rbp
0x14001c3d6  push    rbx
0x14001c3d7  push    rsi
0x14001c3d8  push    rdi
0x14001c3d9  push    r15
0x14001c3db  mov     rbp, rsp
0x14001c3de  sub     rsp, 70h
0x14001c3e2  mov     edx, 2; dwCoInit
0x14001c3e7  xor     ecx, ecx; pvReserved
0x14001c3e9  mov     rsi, r8
0x14001c3ec  call    cs:__imp_CoInitializeEx
0x14001c3f2  test    eax, eax
0x14001c3f4  js      loc_14001C672
0x14001c3fa  mov     rdx, 0FFFFFFFFFFFFFFFCh
0x14001c401  mov     [rbp+Block], 0
0x14001c409  lea     rcx, [rbp+Block]
0x14001c40d  call    ??$get_token_information_nothrow@U_TOKEN_MANDATORY_LABEL@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_MANDATORY_LABEL@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_MANDATORY_LABEL,0>(wistd::unique_ptr<_TOKEN_MANDATORY_LABEL,wil::details::token_info_deleter> &,void *)
0x14001c412  mov     ebx, eax
0x14001c414  test    eax, eax
0x14001c416  jns     short loc_14001C445
0x14001c418  mov     rcx, [rbp+28h]; this
0x14001c41c  lea     r8, aPcshellShellAu_0; "pcshell\\shell\\auth\\creduibroker\\exe"...
0x14001c423  mov     r9d, eax; char *
0x14001c426  mov     edx, 30Ch; void *
0x14001c42b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001c430  mov     rcx, [rbp+Block]; Block
0x14001c434  test    rcx, rcx
0x14001c437  jz      short loc_14001C43E
0x14001c439  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14001c43e  mov     eax, ebx
0x14001c440  jmp     loc_14001C674
0x14001c445  mov     rbx, [rbp+Block]
0x14001c449  xor     edx, edx; nSubAuthority
0x14001c44b  mov     rcx, [rbx]; pSid
0x14001c44e  call    cs:__imp_GetSidSubAuthority
0x14001c454  mov     rcx, [rbx]; pSid
0x14001c457  xor     edx, edx; nSubAuthority
0x14001c459  call    cs:__imp_GetSidSubAuthority
0x14001c45f  mov     r15d, 1
0x14001c465  cmp     dword ptr [rax], 2000h
0x14001c46b  jbe     loc_14001C544
0x14001c471  lea     rcx, [rbp+Block]
0x14001c475  mov     [rbp+Block], 0
0x14001c47d  mov     [rbp+var_38], 0
0x14001c485  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001c48a  lea     rax, [rbp+Block]
0x14001c48e  mov     r8d, r15d; dwClsContext
0x14001c491  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x14001c498  mov     [rsp+70h+ppv], rax; int
0x14001c49d  xor     edx, edx; pUnkOuter
0x14001c49f  lea     rcx, CLSID_GlobalOptions; rclsid
0x14001c4a6  call    cs:__imp_CoCreateInstance
0x14001c4ac  mov     edi, eax
0x14001c4ae  test    eax, eax
0x14001c4b0  jns     short loc_14001C4E7
0x14001c4b2  mov     edx, 317h; void *
0x14001c4b7  mov     rcx, [rbp+28h]; this
0x14001c4bb  lea     r8, aPcshellShellAu_0; "pcshell\\shell\\auth\\creduibroker\\exe"...
0x14001c4c2  mov     r9d, edi; char *
0x14001c4c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001c4ca  lea     rcx, [rbp+Block]
0x14001c4ce  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001c4d3  test    rbx, rbx
0x14001c4d6  jz      short loc_14001C4E0
0x14001c4d8  mov     rcx, rbx; Block
0x14001c4db  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14001c4e0  mov     eax, edi
0x14001c4e2  jmp     loc_14001C674
0x14001c4e7  mov     rcx, [rbp+Block]
0x14001c4eb  lea     r8, [rbp+var_38]
0x14001c4ef  mov     edx, 4
0x14001c4f4  mov     rax, [rcx]
0x14001c4f7  mov     rax, [rax+20h]
0x14001c4fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c500  mov     edi, eax
0x14001c502  test    eax, eax
0x14001c504  jns     short loc_14001C50D
0x14001c506  mov     edx, 318h
0x14001c50b  jmp     short loc_14001C4B7
0x14001c50d  mov     rcx, [rbp+Block]
0x14001c511  mov     edx, 4
0x14001c516  mov     r8, [rbp+var_38]
0x14001c51a  bts     r8, 8
0x14001c51f  mov     rax, [rcx]
0x14001c522  mov     rax, [rax+18h]
0x14001c526  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c52b  mov     edi, eax
0x14001c52d  test    eax, eax
0x14001c52f  jns     short loc_14001C53B
0x14001c531  mov     edx, 319h
0x14001c536  jmp     loc_14001C4B7
0x14001c53b  lea     rcx, [rbp+Block]
0x14001c53f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14001c544  test    rbx, rbx
0x14001c547  jz      short loc_14001C551
0x14001c549  mov     rcx, rbx; Block
0x14001c54c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14001c551  call    cs:__imp_GetCurrentThreadId
0x14001c557  mov     edi, eax
0x14001c559  call    ?Create@?$OutOfProcModuleBase@VCSingleUseOutOfProcModule@@@Details@WRL@Microsoft@@SAAEAVCSingleUseOutOfProcModule@@XZ; Microsoft::WRL::Details::OutOfProcModuleBase<CSingleUseOutOfProcModule>::Create(void)
0x14001c55e  mov     rbx, rax
0x14001c561  cmp     qword ptr [rax+8], 0
0x14001c566  jnz     short loc_14001C595
0x14001c568  lea     rax, off_140021620
0x14001c56f  mov     cs:byte_14002A680, r15b
0x14001c576  mov     cs:qword_14002A668, rax
0x14001c57d  lea     rax, qword_14002A668
0x14001c584  mov     cs:byte_14002A670, 0
0x14001c58b  mov     cs:dword_14002A678, edi
0x14001c591  mov     [rbx+8], rax
0x14001c595  or      edi, 0FFFFFFFFh
0x14001c598  mov     [rsp+70h+bIgnoreCase], r15d; bIgnoreCase
0x14001c59d  mov     r8d, edi; cchSource
0x14001c5a0  mov     dword ptr [rsp+70h+ppv], edi; cchValue
0x14001c5a4  lea     r9, StringValue; "NonAppContainerFailedMip"
0x14001c5ab  mov     rdx, rsi; lpStringSource
0x14001c5ae  mov     ecx, 400000h; dwFindStringOrdinalFlags
0x14001c5b3  call    cs:__imp_FindStringOrdinal
0x14001c5b9  cmp     eax, edi
0x14001c5bb  jz      short loc_14001C5C6
0x14001c5bd  mov     dword ptr [rbx+10h], 3
0x14001c5c4  jmp     short loc_14001C61D
0x14001c5c6  mov     [rsp+70h+bIgnoreCase], r15d; bIgnoreCase
0x14001c5cb  lea     r9, aNonappcontaine; "NonAppContainer"
0x14001c5d2  mov     r8d, edi; cchSource
0x14001c5d5  mov     dword ptr [rsp+70h+ppv], edi; cchValue
0x14001c5d9  mov     rdx, rsi; lpStringSource
0x14001c5dc  mov     ecx, 400000h; dwFindStringOrdinalFlags
0x14001c5e1  call    cs:__imp_FindStringOrdinal
0x14001c5e7  cmp     eax, edi
0x14001c5e9  jz      short loc_14001C5F4
0x14001c5eb  mov     dword ptr [rbx+10h], 2
0x14001c5f2  jmp     short loc_14001C61D
0x14001c5f4  mov     [rsp+70h+bIgnoreCase], r15d; bIgnoreCase
0x14001c5f9  lea     r9, aAppcontainer; "AppContainer"
0x14001c600  mov     r8d, edi; cchSource
0x14001c603  mov     dword ptr [rsp+70h+ppv], edi; cchValue
0x14001c607  mov     rdx, rsi; lpStringSource
0x14001c60a  mov     ecx, 400000h; dwFindStringOrdinalFlags
0x14001c60f  call    cs:__imp_FindStringOrdinal
0x14001c615  cmp     eax, edi
0x14001c617  jz      short loc_14001C61D
0x14001c619  mov     [rbx+10h], r15d
0x14001c61d  mov     rcx, rbx
0x14001c620  call    ??$RegisterObjects@$01@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBG@Z; Microsoft::WRL::Details::RegisterObjects<2>(Microsoft::WRL::Details::ModuleBase *,ushort const *)
0x14001c625  test    eax, eax
0x14001c627  js      short loc_14001C66C
0x14001c629  xorps   xmm0, xmm0
0x14001c62c  movups  xmmword ptr [rbp+Msg.hwnd], xmm0
0x14001c630  movups  xmmword ptr [rbp+Msg.wParam], xmm0
0x14001c634  movups  xmmword ptr [rbp+Msg.time], xmm0
0x14001c638  jmp     short loc_14001C64E
0x14001c63a  lea     rcx, [rbp+Msg]; lpMsg
0x14001c63e  call    cs:__imp_TranslateMessage
0x14001c644  lea     rcx, [rbp+Msg]; lpMsg
0x14001c648  call    cs:__imp_DispatchMessageW
0x14001c64e  xor     r9d, r9d; wMsgFilterMax
0x14001c651  lea     rcx, [rbp+Msg]; lpMsg
0x14001c655  xor     r8d, r8d; wMsgFilterMin
0x14001c658  xor     edx, edx; hWnd
0x14001c65a  call    cs:__imp_GetMessageW
0x14001c660  test    eax, eax
0x14001c662  jg      short loc_14001C63A
0x14001c664  mov     rcx, rbx; this
0x14001c667  call    ?UnregisterObjects@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEBG@Z; Microsoft::WRL::Details::UnregisterObjects(Microsoft::WRL::Details::ModuleBase *,ushort const *)
0x14001c66c  call    cs:__imp_CoUninitialize
0x14001c672  xor     eax, eax
0x14001c674  add     rsp, 70h
0x14001c678  pop     r15
0x14001c67a  pop     rdi
0x14001c67b  pop     rsi
0x14001c67c  pop     rbx
0x14001c67d  pop     rbp
0x14001c67e  retn
```
