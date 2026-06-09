# CLanguageComponentsInstallerHandler::SetTaskEnabledStateForCurrentUserAccordingToFutureAction(ushort const *,FutureAction)

- ea: `0x18001b728`
- end: `0x18001b833`
- name: `?SetTaskEnabledStateForCurrentUserAccordingToFutureAction@CLanguageComponentsInstallerHandler@@AEBAXPEBGW4FutureAction@@@Z`
- size: `267`
- prototype: `void __fastcall(__int64, __int64, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800140e0`
- `0x18001d0f0`

## callees

- `0x180003520`
- `0x180005954`
- `0x180006380`
- `0x180018350`
- `0x18001b728`
- `0x18001b970`
- `0x18002a010`

## string_xrefs

- `0x18001b76d`: `\Microsoft\Windows\LanguageComponentsInstaller\Installation`
- `0x18001b7ce`: `\Microsoft\Windows\LanguageComponentsInstaller\Installation`

## pseudocode

```c
void __fastcall CLanguageComponentsInstallerHandler::SetTaskEnabledStateForCurrentUserAccordingToFutureAction(
        __int64 a1,
        __int64 a2,
        int a3)
{
  __int64 v3; // r8
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int128 v6; // [rsp+20h] [rbp-30h] BYREF
  __int128 v7; // [rsp+30h] [rbp-20h]
  int v8[2]; // [rsp+40h] [rbp-10h] BYREF

  if ( *(_DWORD *)(a1 + 56) != 1 )
  {
    if ( a3 )
    {
      if ( a3 != 1 )
        return;
      v6 = 0;
      v7 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v6);
      GetTaskService((int)v8);
      LOBYTE(v3) = 1;
      SetTaskEnabledValueForCurrentUser(v8, &v6, v3);
      v4 = *(_QWORD *)v8;
      if ( *(_QWORD *)v8 )
      {
        *(_QWORD *)v8 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
      }
    }
    else
    {
      v6 = 0;
      v7 = 0;
      std::wstring::_Construct<1,unsigned short const *>(&v6);
      GetTaskService((int)v8);
      SetTaskEnabledValueForCurrentUser(v8, &v6, 0);
      v5 = *(_QWORD *)v8;
      if ( *(_QWORD *)v8 )
      {
        *(_QWORD *)v8 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      }
    }
    std::wstring::~wstring(&v6);
  }
}

```

## disassembly

```asm
0x18001b728  push    rbp
0x18001b72a  mov     rbp, rsp
0x18001b72d  sub     rsp, 50h
0x18001b731  mov     rax, cs:__security_cookie
0x18001b738  xor     rax, rsp
0x18001b73b  mov     [rbp+var_8], rax
0x18001b73f  cmp     dword ptr [rcx+38h], 1
0x18001b743  jz      loc_18001B821
0x18001b749  test    r8d, r8d
0x18001b74c  jz      short loc_18001B7B9
0x18001b74e  cmp     r8d, 1
0x18001b752  jnz     loc_18001B821
0x18001b758  xorps   xmm0, xmm0
0x18001b75b  movups  [rbp+var_30], xmm0
0x18001b75f  xorps   xmm1, xmm1
0x18001b762  movdqu  [rbp+var_20], xmm1
0x18001b767  mov     r8d, 3Bh ; ';'
0x18001b76d  lea     rdx, aMicrosoftWindo_1; "\\Microsoft\\Windows\\LanguageComponent"...
0x18001b774  lea     rcx, [rbp+var_30]
0x18001b778  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001b77d  nop
0x18001b77e  lea     rcx, [rbp+var_10]; int
0x18001b782  call    ?GetTaskService@@YA?AV?$ComPtr@UITaskService@@@WRL@Microsoft@@XZ; GetTaskService(void)
0x18001b787  nop
0x18001b788  mov     r8b, 1
0x18001b78b  lea     rdx, [rbp+var_30]
0x18001b78f  lea     rcx, [rbp+var_10]
0x18001b793  call    ?SetTaskEnabledValueForCurrentUser@@YAXAEBV?$ComPtr@UITaskService@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; SetTaskEnabledValueForCurrentUser(Microsoft::WRL::ComPtr<ITaskService> const &,std::wstring const &,bool)
0x18001b798  nop
0x18001b799  mov     rcx, qword ptr [rbp+var_10]
0x18001b79d  test    rcx, rcx
0x18001b7a0  jz      short loc_18001B7B7
0x18001b7a2  mov     qword ptr [rbp+var_10], 0
0x18001b7aa  mov     rax, [rcx]
0x18001b7ad  mov     rax, [rax+10h]
0x18001b7b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b7b6  nop
0x18001b7b7  jmp     short loc_18001B818
0x18001b7b9  xorps   xmm0, xmm0
0x18001b7bc  movups  [rbp+var_30], xmm0
0x18001b7c0  xorps   xmm1, xmm1
0x18001b7c3  movdqu  [rbp+var_20], xmm1
0x18001b7c8  mov     r8d, 3Bh ; ';'
0x18001b7ce  lea     rdx, aMicrosoftWindo_1; "\\Microsoft\\Windows\\LanguageComponent"...
0x18001b7d5  lea     rcx, [rbp+var_30]
0x18001b7d9  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001b7de  nop
0x18001b7df  lea     rcx, [rbp+var_10]; int
0x18001b7e3  call    ?GetTaskService@@YA?AV?$ComPtr@UITaskService@@@WRL@Microsoft@@XZ; GetTaskService(void)
0x18001b7e8  nop
0x18001b7e9  xor     r8d, r8d
0x18001b7ec  lea     rdx, [rbp+var_30]
0x18001b7f0  lea     rcx, [rbp+var_10]
0x18001b7f4  call    ?SetTaskEnabledValueForCurrentUser@@YAXAEBV?$ComPtr@UITaskService@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z; SetTaskEnabledValueForCurrentUser(Microsoft::WRL::ComPtr<ITaskService> const &,std::wstring const &,bool)
0x18001b7f9  nop
0x18001b7fa  mov     rcx, qword ptr [rbp+var_10]
0x18001b7fe  test    rcx, rcx
0x18001b801  jz      short loc_18001B818
0x18001b803  mov     qword ptr [rbp+var_10], 0
0x18001b80b  mov     rax, [rcx]
0x18001b80e  mov     rax, [rax+10h]
0x18001b812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b817  nop
0x18001b818  lea     rcx, [rbp+var_30]; void *
0x18001b81c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001b821  mov     rcx, [rbp+var_8]
0x18001b825  xor     rcx, rsp; StackCookie
0x18001b828  call    __security_check_cookie
0x18001b82d  add     rsp, 50h
0x18001b831  pop     rbp
0x18001b832  retn
```
