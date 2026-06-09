# std::_Func_impl_no_alloc__lambda_f402bcd9d736ceed28e0331ccf9eeeba__void_::_Do_call

- ea: `0x180019b40`
- end: `0x180019cd3`
- name: `std::_Func_impl_no_alloc__lambda_f402bcd9d736ceed28e0331ccf9eeeba__void_::_Do_call`
- size: `403`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update`

## callees

- `0x180003a00`
- `0x180009084`
- `0x18000a024`
- `0x180010dcc`
- `0x180014720`
- `0x1800148f4`
- `0x180014ed0`
- `0x180016e1c`
- `0x180019b40`
- `0x180035f30`
- `0x1800379d4`
- `0x180038868`
- `0x180042460`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019cb5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180019cb5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019ca7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180019ca7`

## string_xrefs

- `0x180019c14`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageoverlayserver.cpp`
- `0x180019c32`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageoverlayserver.cpp`
- `0x180019c73`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageoverlayserver.cpp`

## pseudocode

```c
void __fastcall std::_Func_impl_no_alloc__lambda_f402bcd9d736ceed28e0331ccf9eeeba__void_::_Do_call(__int64 a1)
{
  __int64 v1; // rdi
  __int64 v2; // r8
  wchar_t *v3; // rcx
  int v4; // esi
  wchar_t **v5; // rdx
  int updated; // ebx
  unsigned __int64 v7; // r9
  __int64 v8; // rdx
  int v9; // eax
  void *v10; // rbx
  HANDLE ProcessHeap; // rax
  int v12[8]; // [rsp+20h] [rbp-69h] BYREF
  wchar_t *S2[3]; // [rsp+40h] [rbp-49h] BYREF
  unsigned __int64 v14; // [rsp+58h] [rbp-31h]
  __int128 v15; // [rsp+60h] [rbp-29h] BYREF
  __int128 lpMem; // [rsp+70h] [rbp-19h]
  __int128 v17; // [rsp+80h] [rbp-9h] BYREF
  __int64 v18; // [rsp+90h] [rbp+7h]
  int v19; // [rsp+98h] [rbp+Fh]
  __int64 v20; // [rsp+A0h] [rbp+17h]
  char v21; // [rsp+A8h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v1 = a1 + 8;
  v2 = *(_QWORD *)(a1 + 280);
  if ( *(_DWORD *)v2 == 1 )
  {
    wil::ActivityThreadWatcher::ActivityThreadWatcher(
      (wil::ActivityThreadWatcher *)&v15,
      (struct wil::details::IFailureCallback *)(a1 + 8),
      (const struct wil::details::StoredCallContextInfo *)(v2 + 40));
  }
  else
  {
    v15 = 0;
    lpMem = 0;
    v17 = 0;
    v18 = 0;
    v19 = 0;
    v20 = 0;
    v21 = 0;
  }
  RetrievePendingDeviceInternationalSettings(S2);
  if ( S2[2] )
  {
    v3 = (wchar_t *)S2;
    if ( v14 > 7 )
      v3 = S2[0];
    v4 = ApplyToDeviceInternationalSettings(v3);
    v5 = S2;
    if ( v14 > 7 )
      v5 = (wchar_t **)S2[0];
    std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(
      v12,
      v5);
    updated = UpdatePendingLanguageInstallationState(v12, (unsigned int)v4);
    std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(v12);
    if ( updated < 0 )
    {
      v7 = (unsigned int)updated;
      v8 = 296;
LABEL_11:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageoverlayserver.cpp",
        (const char *)v7,
        v12[0]);
      goto LABEL_17;
    }
    if ( v4 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x129,
        (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageoverlayserver.cpp",
        (const char *)(unsigned int)v4,
        v12[0]);
      updated = v4;
      goto LABEL_17;
    }
    v9 = DeletePendingDeviceInternationalSettings();
    updated = v9;
    if ( v9 < 0 )
    {
      v7 = (unsigned int)v9;
      v8 = 298;
      goto LABEL_11;
    }
  }
  updated = 0;
LABEL_17:
  std::basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>::~basic_string<unsigned short,details::case_insensitive_wchar_traits,std::allocator<unsigned short>>(S2);
  if ( updated < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x86,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageoverlayserver.cpp",
      (const char *)(unsigned int)updated,
      v12[0]);
  wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v1);
  if ( v19 )
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)&v17);
  if ( BYTE8(lpMem) )
  {
    v10 = (void *)lpMem;
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v10);
  }
}

```

## disassembly

```asm
0x180019b40  push    rbp
0x180019b42  push    rbx
0x180019b43  push    rsi
0x180019b44  push    rdi
0x180019b45  lea     rbp, [rsp-3Fh]
0x180019b4a  sub     rsp, 0C8h
0x180019b51  mov     rax, cs:__security_cookie
0x180019b58  xor     rax, rsp
0x180019b5b  mov     [rbp+57h+var_30], rax
0x180019b5f  lea     rdi, [rcx+8]
0x180019b63  mov     r8, [rdi+110h]
0x180019b6a  cmp     dword ptr [r8], 1
0x180019b6e  jnz     short loc_180019B82
0x180019b70  add     r8, 28h ; '('; struct wil::details::StoredCallContextInfo *
0x180019b74  mov     rdx, rdi; struct wil::details::IFailureCallback *
0x180019b77  lea     rcx, [rbp+57h+var_80]; this
0x180019b7b  call    ??0ActivityThreadWatcher@wil@@QEAA@PEAUIFailureCallback@details@1@AEBVStoredCallContextInfo@31@@Z; wil::ActivityThreadWatcher::ActivityThreadWatcher(wil::details::IFailureCallback *,wil::details::StoredCallContextInfo const &)
0x180019b80  jmp     short loc_180019BB1
0x180019b82  mov     [rbp+57h+var_68], 0
0x180019b86  xorps   xmm0, xmm0
0x180019b89  movups  [rbp+57h+var_80], xmm0
0x180019b8d  movups  xmmword ptr [rbp-19h], xmm0
0x180019b91  movdqa  [rbp+57h+var_60], xmm0
0x180019b96  mov     [rbp+57h+var_50], 0
0x180019b9e  mov     [rbp+57h+var_48], 0
0x180019ba5  mov     [rbp+57h+var_40], 0
0x180019bad  mov     [rbp+57h+var_38], 0
0x180019bb1  lea     rcx, [rbp+57h+S2]
0x180019bb5  call    ?RetrievePendingDeviceInternationalSettings@@YA?AV?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@XZ; RetrievePendingDeviceInternationalSettings(void)
0x180019bba  nop
0x180019bbb  cmp     [rbp+57h+var_90], 0
0x180019bc0  jz      loc_180019C5D
0x180019bc6  lea     rcx, [rbp+57h+S2]
0x180019bca  cmp     [rbp+57h+var_88], 7
0x180019bcf  cmova   rcx, [rbp+57h+S2]; S2
0x180019bd4  call    ?ApplyToDeviceInternationalSettings@@YAJPEBG@Z; ApplyToDeviceInternationalSettings(ushort const *)
0x180019bd9  mov     esi, eax
0x180019bdb  lea     rdx, [rbp+57h+S2]
0x180019bdf  cmp     [rbp+57h+var_88], 7
0x180019be4  cmova   rdx, [rbp+57h+S2]
0x180019be9  lea     rcx, [rbp+57h+var_C0]
0x180019bed  call    ??0?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@QEBG@Z; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(ushort const * const)
0x180019bf2  mov     edx, esi
0x180019bf4  lea     rcx, [rbp+57h+var_C0]
0x180019bf8  call    ?UpdatePendingLanguageInstallationState@@YAJAEBV?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@J@Z; UpdatePendingLanguageInstallationState(std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>> const &,long)
0x180019bfd  mov     ebx, eax
0x180019bff  lea     rcx, [rbp+57h+var_C0]; void *
0x180019c03  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180019c08  test    ebx, ebx
0x180019c0a  jns     short loc_180019C27
0x180019c0c  mov     r9d, ebx; char *
0x180019c0f  mov     edx, 128h; void *
0x180019c14  lea     r8, aOnecoreBaseLan_31; "onecore\\base\\languageoverlay\\service"...
0x180019c1b  mov     rcx, [rbp+5Fh]; this
0x180019c1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019c24  nop
0x180019c25  jmp     short loc_180019C5F
0x180019c27  test    esi, esi
0x180019c29  jns     short loc_180019C48
0x180019c2b  mov     rcx, [rbp+5Fh]; this
0x180019c2f  mov     r9d, esi; char *
0x180019c32  lea     r8, aOnecoreBaseLan_31; "onecore\\base\\languageoverlay\\service"...
0x180019c39  mov     edx, 129h; void *
0x180019c3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019c43  nop
0x180019c44  mov     ebx, esi
0x180019c46  jmp     short loc_180019C5F
0x180019c48  call    ?DeletePendingDeviceInternationalSettings@@YAJXZ; DeletePendingDeviceInternationalSettings(void)
0x180019c4d  mov     ebx, eax
0x180019c4f  test    eax, eax
0x180019c51  jns     short loc_180019C5D
0x180019c53  mov     r9d, eax
0x180019c56  mov     edx, 12Ah
0x180019c5b  jmp     short loc_180019C14
0x180019c5d  xor     ebx, ebx
0x180019c5f  lea     rcx, [rbp+57h+S2]; void *
0x180019c63  call    ??1?$basic_string@GUcase_insensitive_wchar_traits@details@@V?$allocator@G@std@@@std@@QEAA@XZ; std::basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>::~basic_string<ushort,details::case_insensitive_wchar_traits,std::allocator<ushort>>(void)
0x180019c68  mov     rcx, [rbp+5Fh]; this
0x180019c6c  test    ebx, ebx
0x180019c6e  jns     short loc_180019C84
0x180019c70  mov     r9d, ebx; char *
0x180019c73  lea     r8, aOnecoreBaseLan_31; "onecore\\base\\languageoverlay\\service"...
0x180019c7a  mov     edx, 86h; void *
0x180019c7f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180019c84  mov     rcx, rdi
0x180019c87  call    ?Stop@?$ActivityBase@VLanguageOverlayTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LanguageOverlayTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180019c8c  nop
0x180019c8d  cmp     [rbp+57h+var_48], 0
0x180019c91  jz      short loc_180019C9D
0x180019c93  lea     rcx, [rbp+57h+var_60]; this
0x180019c97  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x180019c9c  nop
0x180019c9d  cmp     [rbp+57h+var_68], 0
0x180019ca1  jz      short loc_180019CBB
0x180019ca3  mov     rbx, [rbp+57h+lpMem]
0x180019ca7  call    cs:__imp_GetProcessHeap
0x180019cad  mov     r8, rbx; lpMem
0x180019cb0  xor     edx, edx; dwFlags
0x180019cb2  mov     rcx, rax; hHeap
0x180019cb5  call    cs:__imp_HeapFree
0x180019cbb  mov     rcx, [rbp+57h+var_30]
0x180019cbf  xor     rcx, rsp; StackCookie
0x180019cc2  call    __security_check_cookie
0x180019cc7  add     rsp, 0C8h
0x180019cce  pop     rdi
0x180019ccf  pop     rsi
0x180019cd0  pop     rbx
0x180019cd1  pop     rbp
0x180019cd2  retn
```
