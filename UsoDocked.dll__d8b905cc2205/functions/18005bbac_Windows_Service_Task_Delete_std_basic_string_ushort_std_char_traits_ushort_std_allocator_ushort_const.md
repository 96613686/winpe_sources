# Windows::Service::Task::Delete(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18005bbac`
- end: `0x18005bee6`
- name: `?Delete@Task@Service@Windows@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `826`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, service_task, installer_update`

## callers

- `0x18005bef0`

## callees

- `0x180007660`
- `0x18001ba70`
- `0x18001ee04`
- `0x1800209fc`
- `0x180023ac4`
- `0x180045bd4`
- `0x18005bbac`
- `0x18005c718`
- `0x18005e98c`
- `0x180071010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18005bdf2`
- `OLEAUT32!__imp_SysFreeString` at `0x18005be18`
- `OLEAUT32!__imp_SysFreeString` at `0x18005be40`
- `OLEAUT32!__imp_SysFreeString` at `0x18005be66`
- `OLEAUT32!__imp_SysFreeString` at `0x18005bdf2`
- `OLEAUT32!__imp_SysFreeString` at `0x18005be18`
- `OLEAUT32!__imp_SysFreeString` at `0x18005be40`
- `OLEAUT32!__imp_SysFreeString` at `0x18005be66`

## string_xrefs

- `0x18005beaa`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005bebf`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`
- `0x18005bed4`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\scheduler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void __fastcall Windows::Service::Task::Delete(_QWORD *a1)
{
  __int64 *v2; // rbx
  PCNZWCH *v3; // rdx
  __int64 v4; // rax
  int v5; // eax
  __int64 v6; // rax
  int v7; // eax
  int v8; // eax
  _QWORD *System; // rax
  __int64 v10; // rax
  __int64 v11; // rbx
  void (__fastcall *v12)(__int64, _OWORD *); // rdi
  __int64 v13; // r8
  volatile signed __int32 *v14; // rbx
  volatile signed __int32 *v15; // rbx
  __int64 *v16; // [rsp+20h] [rbp-29h] BYREF
  BSTR bstrString; // [rsp+28h] [rbp-21h] BYREF
  __int64 v18; // [rsp+30h] [rbp-19h] BYREF
  int v19[2]; // [rsp+38h] [rbp-11h] BYREF
  BSTR v20; // [rsp+40h] [rbp-9h] BYREF
  __int64 *v21; // [rsp+48h] [rbp-1h] BYREF
  volatile signed __int32 *v22; // [rsp+50h] [rbp+7h]
  _BYTE v23[8]; // [rsp+58h] [rbp+Fh] BYREF
  volatile signed __int32 *v24; // [rsp+60h] [rbp+17h]
  _OWORD v25[2]; // [rsp+68h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  Windows::Service::Task::TaskService((LPVOID *)v19);
  v2 = *(__int64 **)v19;
  v21 = *(__int64 **)v19;
  if ( *(_QWORD *)v19 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v19 + 8LL))(*(_QWORD *)v19);
  Windows::Service::Task::EnsureTaskFolderExists(&v21);
  if ( v2 )
    (*(void (__fastcall **)(__int64 *))(*v2 + 16))(v2);
  v3 = &Windows::Service::Task::c_taskFolder;
  if ( (unsigned __int64)qword_180097688 > 7 )
    v3 = (PCNZWCH *)Windows::Service::Task::c_taskFolder;
  wil::make_bstr(&v20, v3);
  v16 = 0;
  v4 = **(_QWORD **)v19;
  v16 = 0;
  v5 = (*(__int64 (__fastcall **)(_QWORD, BSTR, __int64 **))(v4 + 56))(*(_QWORD *)v19, v20, &v16);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x10E,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
      (const char *)(unsigned int)v5,
      (int)v16);
  if ( a1[3] > 7u )
    a1 = (_QWORD *)*a1;
  wil::make_bstr(&bstrString, a1);
  v18 = 0;
  v6 = *v16;
  v18 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64 *, BSTR, __int64 *))(v6 + 104))(v16, bstrString, &v18);
  if ( (unsigned int)(v7 + 2147024894) <= 1 )
  {
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    if ( bstrString )
      SysFreeString(bstrString);
    if ( v16 )
      (*(void (__fastcall **)(__int64 *))(*v16 + 16))(v16);
    if ( v20 )
      SysFreeString(v20);
  }
  else
  {
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x11B,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
        (const char *)(unsigned int)v7,
        (int)v16);
    v8 = (*(__int64 (__fastcall **)(__int64 *, BSTR, _QWORD))(*v16 + 120))(v16, bstrString, 0);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x11E,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\scheduler.cpp",
        (const char *)(unsigned int)v8,
        (int)v16);
    System = (_QWORD *)SystemInterface::Service::GetSystem(v23);
    v10 = (*(__int64 (__fastcall **)(_QWORD, __int64 **))(*(_QWORD *)*System + 96LL))(*System, &v21);
    v11 = *(_QWORD *)v10;
    v12 = *(void (__fastcall **)(__int64, _OWORD *))(**(_QWORD **)v10 + 72LL);
    memset(v25, 0, sizeof(v25));
    v13 = -1;
    do
      ++v13;
    while ( bstrString[v13] );
    std::wstring::_Construct<1,unsigned short const *>(v25, bstrString);
    v12(v11, v25);
    std::wstring::_Tidy_deallocate(v25);
    v14 = v22;
    if ( v22 )
    {
      if ( !_InterlockedDecrement(v22 + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
        if ( !_InterlockedDecrement(v14 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
      }
    }
    v15 = v24;
    if ( v24 )
    {
      if ( !_InterlockedDecrement(v24 + 2) )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
        if ( !_InterlockedDecrement(v15 + 3) )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
      }
    }
    if ( v18 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    if ( bstrString )
      SysFreeString(bstrString);
    if ( v16 )
      (*(void (__fastcall **)(__int64 *))(*v16 + 16))(v16);
    if ( v20 )
      SysFreeString(v20);
  }
  if ( *(_QWORD *)v19 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v19 + 16LL))(*(_QWORD *)v19);
}

```

## disassembly

```asm
0x18005bbac  mov     [rsp-8+arg_8], rbx
0x18005bbb1  mov     [rsp-8+arg_10], rsi
0x18005bbb6  push    rbp
0x18005bbb7  push    rdi
0x18005bbb8  push    r14
0x18005bbba  lea     rbp, [rsp-47h]
0x18005bbbf  sub     rsp, 90h
0x18005bbc6  mov     rax, cs:__security_cookie
0x18005bbcd  xor     rax, rsp
0x18005bbd0  mov     [rbp+57h+var_18], rax
0x18005bbd4  mov     rdi, rcx
0x18005bbd7  xor     esi, esi
0x18005bbd9  lea     rcx, [rbp+57h+var_68]; int
0x18005bbdd  call    ?TaskService@Task@Service@Windows@@CA?AV?$com_ptr_t@UITaskService@@Uerr_exception_policy@wil@@@wil@@XZ; Windows::Service::Task::TaskService(void)
0x18005bbe2  nop
0x18005bbe3  mov     rbx, qword ptr [rbp+57h+var_68]
0x18005bbe7  mov     [rbp+57h+var_58], rbx
0x18005bbeb  test    rbx, rbx
0x18005bbee  jz      short loc_18005BC00
0x18005bbf0  mov     rax, [rbx]
0x18005bbf3  mov     rcx, rbx
0x18005bbf6  mov     rax, [rax+8]
0x18005bbfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bbff  nop
0x18005bc00  lea     rcx, [rbp+57h+var_58]
0x18005bc04  call    ?EnsureTaskFolderExists@Task@Service@Windows@@CAXAEBV?$com_ptr_t@UITaskService@@Uerr_exception_policy@wil@@@wil@@@Z; Windows::Service::Task::EnsureTaskFolderExists(wil::com_ptr_t<ITaskService,wil::err_exception_policy> const &)
0x18005bc09  nop
0x18005bc0a  test    rbx, rbx
0x18005bc0d  jz      short loc_18005BC1F
0x18005bc0f  mov     rax, [rbx]
0x18005bc12  mov     rcx, rbx
0x18005bc15  mov     rax, [rax+10h]
0x18005bc19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bc1e  nop
0x18005bc1f  lea     rdx, ?c_taskFolder@Task@Service@Windows@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Windows::Service::Task::c_taskFolder
0x18005bc26  cmp     cs:qword_180097688, 7
0x18005bc2e  cmova   rdx, cs:?c_taskFolder@Task@Service@Windows@@0V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Windows::Service::Task::c_taskFolder
0x18005bc36  lea     rcx, [rbp+57h+var_60]
0x18005bc3a  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18005bc3f  nop
0x18005bc40  mov     [rbp+57h+var_80], rsi
0x18005bc44  mov     rcx, qword ptr [rbp+57h+var_68]
0x18005bc48  mov     rax, [rcx]
0x18005bc4b  mov     [rbp+57h+var_80], rsi
0x18005bc4f  lea     r8, [rbp+57h+var_80]
0x18005bc53  mov     rdx, [rbp+57h+var_60]
0x18005bc57  mov     rax, [rax+38h]
0x18005bc5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bc60  mov     rcx, [rbp+5Fh]; this
0x18005bc64  test    eax, eax
0x18005bc66  js      loc_18005BEBC
0x18005bc6c  cmp     qword ptr [rdi+18h], 7
0x18005bc71  jbe     short loc_18005BC76
0x18005bc73  mov     rdi, [rdi]
0x18005bc76  mov     rdx, rdi
0x18005bc79  lea     rcx, [rbp+57h+bstrString]
0x18005bc7d  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18005bc82  nop
0x18005bc83  mov     [rbp+57h+var_70], rsi
0x18005bc87  mov     rcx, [rbp+57h+var_80]
0x18005bc8b  mov     rax, [rcx]
0x18005bc8e  mov     [rbp+57h+var_70], rsi
0x18005bc92  lea     r8, [rbp+57h+var_70]
0x18005bc96  mov     rdx, [rbp+57h+bstrString]
0x18005bc9a  mov     rax, [rax+68h]
0x18005bc9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bca3  lea     ecx, [rax+7FF8FFFEh]
0x18005bca9  cmp     ecx, 1
0x18005bcac  jbe     loc_18005BE21
0x18005bcb2  mov     rcx, [rbp+5Fh]; this
0x18005bcb6  test    eax, eax
0x18005bcb8  js      loc_18005BED1
0x18005bcbe  mov     rcx, [rbp+57h+var_80]
0x18005bcc2  mov     rax, [rcx]
0x18005bcc5  xor     r8d, r8d
0x18005bcc8  mov     rdx, [rbp+57h+bstrString]
0x18005bccc  mov     rax, [rax+78h]
0x18005bcd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bcd5  mov     rcx, [rbp+5Fh]; this
0x18005bcd9  test    eax, eax
0x18005bcdb  js      loc_18005BEA7
0x18005bce1  lea     rcx, [rbp+57h+var_48]
0x18005bce5  call    ?GetSystem@Service@SystemInterface@@YA?AV?$shared_ptr@VSystem@Service@SystemInterface@@@std@@XZ; SystemInterface::Service::GetSystem(void)
0x18005bcea  nop
0x18005bceb  mov     rcx, [rax]
0x18005bcee  mov     rax, [rcx]
0x18005bcf1  lea     rdx, [rbp+57h+var_58]
0x18005bcf5  mov     rax, [rax+60h]
0x18005bcf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bcfe  nop
0x18005bcff  mov     rbx, [rax]
0x18005bd02  mov     rax, [rbx]
0x18005bd05  mov     rdi, [rax+48h]
0x18005bd09  mov     rdx, [rbp+57h+bstrString]
0x18005bd0d  xorps   xmm0, xmm0
0x18005bd10  movups  [rbp+57h+var_38], xmm0
0x18005bd14  xorps   xmm1, xmm1
0x18005bd17  movdqu  [rbp+57h+var_28], xmm1
0x18005bd1c  or      r14, 0FFFFFFFFFFFFFFFFh
0x18005bd20  mov     r8, r14
0x18005bd23  inc     r8
0x18005bd26  cmp     [rdx+r8*2], si
0x18005bd2b  jnz     short loc_18005BD23
0x18005bd2d  lea     rcx, [rbp+57h+var_38]
0x18005bd31  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18005bd36  nop
0x18005bd37  lea     rdx, [rbp+57h+var_38]
0x18005bd3b  mov     rcx, rbx
0x18005bd3e  mov     rax, rdi
0x18005bd41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd46  nop
0x18005bd47  lea     rcx, [rbp+57h+var_38]
0x18005bd4b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005bd50  nop
0x18005bd51  mov     rbx, [rbp+57h+var_50]
0x18005bd55  test    rbx, rbx
0x18005bd58  jz      short loc_18005BD92
0x18005bd5a  mov     eax, r14d
0x18005bd5d  lock xadd [rbx+8], eax
0x18005bd62  add     eax, r14d
0x18005bd65  jnz     short loc_18005BD92
0x18005bd67  mov     rax, [rbx]
0x18005bd6a  mov     rcx, rbx
0x18005bd6d  mov     rax, [rax]
0x18005bd70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd75  mov     eax, r14d
0x18005bd78  lock xadd [rbx+0Ch], eax
0x18005bd7d  add     eax, r14d
0x18005bd80  jnz     short loc_18005BD92
0x18005bd82  mov     rax, [rbx]
0x18005bd85  mov     rcx, rbx
0x18005bd88  mov     rax, [rax+8]
0x18005bd8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bd91  nop
0x18005bd92  mov     rbx, [rbp+57h+var_40]
0x18005bd96  test    rbx, rbx
0x18005bd99  jz      short loc_18005BDD3
0x18005bd9b  mov     eax, r14d
0x18005bd9e  lock xadd [rbx+8], eax
0x18005bda3  add     eax, r14d
0x18005bda6  jnz     short loc_18005BDD3
0x18005bda8  mov     rax, [rbx]
0x18005bdab  mov     rcx, rbx
0x18005bdae  mov     rax, [rax]
0x18005bdb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bdb6  mov     eax, r14d
0x18005bdb9  lock xadd [rbx+0Ch], eax
0x18005bdbe  add     eax, r14d
0x18005bdc1  jnz     short loc_18005BDD3
0x18005bdc3  mov     rax, [rbx]
0x18005bdc6  mov     rcx, rbx
0x18005bdc9  mov     rax, [rax+8]
0x18005bdcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bdd2  nop
0x18005bdd3  mov     rcx, [rbp+57h+var_70]
0x18005bdd7  test    rcx, rcx
0x18005bdda  jz      short loc_18005BDE9
0x18005bddc  mov     rax, [rcx]
0x18005bddf  mov     rax, [rax+10h]
0x18005bde3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005bde8  nop
0x18005bde9  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18005bded  test    rcx, rcx
0x18005bdf0  jz      short loc_18005BDF9
0x18005bdf2  call    cs:__imp_SysFreeString
0x18005bdf8  nop
0x18005bdf9  mov     rcx, [rbp+57h+var_80]
0x18005bdfd  test    rcx, rcx
0x18005be00  jz      short loc_18005BE0F
0x18005be02  mov     rax, [rcx]
0x18005be05  mov     rax, [rax+10h]
0x18005be09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005be0e  nop
0x18005be0f  mov     rcx, [rbp+57h+var_60]; bstrString
0x18005be13  test    rcx, rcx
0x18005be16  jz      short loc_18005BE1F
0x18005be18  call    cs:__imp_SysFreeString
0x18005be1e  nop
0x18005be1f  jmp     short loc_18005BE6D
0x18005be21  mov     rcx, [rbp+57h+var_70]
0x18005be25  test    rcx, rcx
0x18005be28  jz      short loc_18005BE37
0x18005be2a  mov     rax, [rcx]
0x18005be2d  mov     rax, [rax+10h]
0x18005be31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005be36  nop
0x18005be37  mov     rcx, [rbp+57h+bstrString]; bstrString
0x18005be3b  test    rcx, rcx
0x18005be3e  jz      short loc_18005BE47
0x18005be40  call    cs:__imp_SysFreeString
0x18005be46  nop
0x18005be47  mov     rcx, [rbp+57h+var_80]
0x18005be4b  test    rcx, rcx
0x18005be4e  jz      short loc_18005BE5D
0x18005be50  mov     rax, [rcx]
0x18005be53  mov     rax, [rax+10h]
0x18005be57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005be5c  nop
0x18005be5d  mov     rcx, [rbp+57h+var_60]; bstrString
0x18005be61  test    rcx, rcx
0x18005be64  jz      short loc_18005BE6D
0x18005be66  call    cs:__imp_SysFreeString
0x18005be6c  nop
0x18005be6d  mov     rcx, qword ptr [rbp+57h+var_68]
0x18005be71  test    rcx, rcx
0x18005be74  jz      short loc_18005BE83
0x18005be76  mov     rax, [rcx]
0x18005be79  mov     rax, [rax+10h]
0x18005be7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005be82  nop
0x18005be83  mov     rcx, [rbp+57h+var_18]
0x18005be87  xor     rcx, rsp; StackCookie
0x18005be8a  call    __security_check_cookie
0x18005be8f  lea     r11, [rsp+0A0h+var_10]
0x18005be97  mov     rbx, [r11+28h]
0x18005be9b  mov     rsi, [r11+30h]
0x18005be9f  mov     rsp, r11
0x18005bea2  pop     r14
0x18005bea4  pop     rdi
0x18005bea5  pop     rbp
0x18005bea6  retn
0x18005bea7  mov     r9d, eax; char *
0x18005beaa  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005beb1  mov     edx, 11Eh; void *
0x18005beb6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005bebc  mov     r9d, eax; char *
0x18005bebf  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005bec6  mov     edx, 10Eh; void *
0x18005becb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005bed1  mov     r9d, eax; char *
0x18005bed4  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18005bedb  mov     edx, 11Bh; void *
0x18005bee0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
