# Windows::FileSystem::MoNotificationUxPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180065770`
- end: `0x1800659c1`
- name: `?MoNotificationUxPath@FileSystem@Windows@@UEAA?AVpath@filesystem@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@5@@Z`
- size: `593`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180007660`
- `0x180007dfc`
- `0x18001ba70`
- `0x18001ee04`
- `0x18001ee70`
- `0x1800209fc`
- `0x18002183c`
- `0x180058020`
- `0x180063e34`
- `0x180064a78`
- `0x1800655c8`
- `0x180065770`
- `0x180066030`
- `0x180071010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800658fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800658fb`

## string_xrefs

- `0x1800657de`: `system.MoNotificationUxPath.`
- `0x1800659a9`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\servicesystem\filesystem.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void *__fastcall Windows::FileSystem::MoNotificationUxPath(__int64 a1, void *a2, _QWORD *a3)
{
  _QWORD *v4; // rbx
  _QWORD *v5; // rsi
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // r8
  __int64 v9; // r8
  const struct std::filesystem::path *v10; // rdx
  LPVOID pv[4]; // [rsp+48h] [rbp-61h] BYREF
  __int128 v13; // [rsp+68h] [rbp-41h] BYREF
  __int64 v14; // [rsp+78h] [rbp-31h]
  __int64 v15; // [rsp+80h] [rbp-29h]
  __int128 v16; // [rsp+88h] [rbp-21h] BYREF
  __int64 v17; // [rsp+98h] [rbp-11h]
  __int64 v18; // [rsp+A0h] [rbp-9h]
  __int128 v19; // [rsp+A8h] [rbp-1h] BYREF
  __int64 v20; // [rsp+B8h] [rbp+Fh]
  __int64 v21; // [rsp+C0h] [rbp+17h]
  _QWORD v22[4]; // [rsp+C8h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  pv[1] = a2;
  if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - a3[2]) < 0x1C )
    std::_Xlen_string();
  if ( a3[3] > 7u )
    a3 = (_QWORD *)*a3;
  std::wstring::wstring(v22, a2, a3, L"system.MoNotificationUxPath.");
  v4 = v22;
  if ( v22[3] > 7u )
    v4 = (_QWORD *)v22[0];
  v5 = operator new(0x10u);
  pv[0] = v5;
  *v5 = &uus::Session::`vftable';
  v5[1] = uus::Utility::GetFirstBrainSession<uus::Brain3>((__int64)v4, 2);
  pv[2] = v5;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v19, L"MoNotificationUx.exe");
  v6 = v5[1];
  if ( v6 )
  {
    v7 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 40LL))(v6, 1);
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(v7 + 2 * v8) );
    v13 = 0;
    v14 = 0;
    v15 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v13, v7);
  }
  else
  {
    wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
      pv,
      L"%SystemRoot%\\uus");
    v9 = -1;
    do
      ++v9;
    while ( *((_WORD *)pv[0] + v9) );
    v16 = 0;
    v17 = 0;
    v18 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v16, pv[0]);
    if ( pv[0] )
      CoTaskMemFree(pv[0]);
    uus::Utility::GetGuestOrNativeArchFolder(&v13, &v16);
    std::wstring::_Tidy_deallocate(&v16);
  }
  std::filesystem::operator/(a2, &v13, (std::filesystem *)&v19);
  std::wstring::_Tidy_deallocate(&v13);
  std::wstring::_Tidy_deallocate(&v19);
  if ( !std::filesystem::exists((std::filesystem *)a2, v10) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x42,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\servicesystem\\filesystem.cpp",
      (const char *)0x80070002LL,
      28);
  (*(void (__fastcall **)(_QWORD *, __int64))*v5)(v5, 1);
  std::wstring::_Tidy_deallocate(v22);
  return a2;
}

```

## disassembly

```asm
0x180065770  mov     [rsp-8+arg_0], rbx
0x180065775  mov     [rsp-8+arg_18], rsi
0x18006577a  push    rbp
0x18006577b  push    rdi
0x18006577c  push    r15
0x18006577e  lea     rbp, [rsp-47h]
0x180065783  sub     rsp, 0F0h
0x18006578a  mov     rax, cs:__security_cookie
0x180065791  xor     rax, rsp
0x180065794  mov     [rbp+57h+var_18], rax
0x180065798  mov     rdi, rdx
0x18006579b  mov     [rbp+57h+var_B0], rdx
0x18006579f  xor     r15d, r15d
0x1800657a2  mov     [rbp+57h+var_C0], r15d
0x1800657a6  mov     rcx, [r8+10h]
0x1800657aa  mov     rax, 7FFFFFFFFFFFFFFEh
0x1800657b4  sub     rax, rcx
0x1800657b7  cmp     rax, 1Ch
0x1800657bb  jb      loc_1800659BB
0x1800657c1  cmp     qword ptr [r8+18h], 7
0x1800657c6  jbe     short loc_1800657CB
0x1800657c8  mov     r8, [r8]
0x1800657cb  mov     [rsp+100h+var_D0], rcx
0x1800657d0  mov     [rsp+100h+var_D8], r8
0x1800657d5  mov     qword ptr [rsp+100h+var_E0], 1Ch; int
0x1800657de  lea     r9, aSystemMonotifi; "system.MoNotificationUxPath."
0x1800657e5  lea     rcx, [rbp+57h+var_38]
0x1800657e9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x1800657ee  mov     [rbp+57h+var_C0], 2
0x1800657f5  lea     rbx, [rbp+57h+var_38]
0x1800657f9  cmp     [rbp+57h+var_20], 7
0x1800657fe  cmova   rbx, [rbp+57h+var_38]
0x180065803  mov     ecx, 10h; Size
0x180065808  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006580d  mov     rsi, rax
0x180065810  mov     [rbp+57h+pv], rax
0x180065814  lea     rax, ??_7Session@uus@@6B@; const uus::Session::`vftable'
0x18006581b  mov     [rsi], rax
0x18006581e  mov     edx, 2
0x180065823  mov     rcx, rbx
0x180065826  call    ??$GetFirstBrainSession@UBrain3@uus@@@Utility@uus@@SAPEAUBrain3@1@PEBGI@Z; uus::Utility::GetFirstBrainSession<uus::Brain3>(ushort const *,uint)
0x18006582b  mov     [rsi+8], rax
0x18006582f  mov     [rbp+57h+var_A8], rsi
0x180065833  mov     [rbp+57h+var_C0], 6
0x18006583a  xorps   xmm0, xmm0
0x18006583d  movups  [rbp+57h+var_58], xmm0
0x180065841  mov     [rbp+57h+var_48], r15
0x180065845  mov     [rbp+57h+var_40], r15
0x180065849  mov     r8d, 14h
0x18006584f  lea     rdx, aMonotification; "MoNotificationUx.exe"
0x180065856  lea     rcx, [rbp+57h+var_58]
0x18006585a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18006585f  mov     [rbp+57h+var_C0], 36h ; '6'
0x180065866  mov     rcx, [rsi+8]
0x18006586a  test    rcx, rcx
0x18006586d  jz      short loc_1800658B0
0x18006586f  mov     rax, [rcx]
0x180065872  mov     edx, 1
0x180065877  mov     rax, [rax+28h]
0x18006587b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065880  or      r8, 0FFFFFFFFFFFFFFFFh
0x180065884  inc     r8
0x180065887  cmp     [rax+r8*2], r15w
0x18006588c  jnz     short loc_180065884
0x18006588e  xorps   xmm0, xmm0
0x180065891  movups  [rbp+57h+var_98], xmm0
0x180065895  mov     [rbp+57h+var_88], r15
0x180065899  mov     [rbp+57h+var_80], r15
0x18006589d  mov     rdx, rax
0x1800658a0  lea     rcx, [rbp+57h+var_98]
0x1800658a4  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800658a9  mov     ebx, 3B6h
0x1800658ae  jmp     short loc_18006591D
0x1800658b0  lea     rdx, aSystemrootUus; "%SystemRoot%\\uus"
0x1800658b7  lea     rcx, [rbp+57h+pv]
0x1800658bb  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *)
0x1800658c0  nop
0x1800658c1  mov     rdx, [rbp+57h+pv]
0x1800658c5  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800658c9  inc     r8
0x1800658cc  cmp     [rdx+r8*2], r15w
0x1800658d1  jnz     short loc_1800658C9
0x1800658d3  xorps   xmm0, xmm0
0x1800658d6  movups  [rbp+57h+var_78], xmm0
0x1800658da  mov     [rbp+57h+var_68], r15
0x1800658de  mov     [rbp+57h+var_60], r15
0x1800658e2  lea     rcx, [rbp+57h+var_78]
0x1800658e6  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800658eb  mov     [rbp+57h+var_C0], 1C36h
0x1800658f2  mov     rcx, [rbp+57h+pv]; pv
0x1800658f6  test    rcx, rcx
0x1800658f9  jz      short loc_180065902
0x1800658fb  call    cs:__imp_CoTaskMemFree
0x180065901  nop
0x180065902  lea     rdx, [rbp+57h+var_78]
0x180065906  lea     rcx, [rbp+57h+var_98]
0x18006590a  call    ?GetGuestOrNativeArchFolder@Utility@uus@@SA?AVpath@filesystem@std@@AEBV345@@Z; uus::Utility::GetGuestOrNativeArchFolder(std::filesystem::path const &)
0x18006590f  mov     ebx, 1CB6h
0x180065914  lea     rcx, [rbp+57h+var_78]
0x180065918  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006591d  or      ebx, 40h
0x180065920  mov     [rbp+57h+var_C0], ebx
0x180065923  lea     r8, [rbp+57h+var_58]; this
0x180065927  lea     rdx, [rbp+57h+var_98]; void *
0x18006592b  mov     rcx, rdi; Src
0x18006592e  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x180065933  or      ebx, 8
0x180065936  lea     rcx, [rbp+57h+var_98]
0x18006593a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006593f  nop
0x180065940  lea     rcx, [rbp+57h+var_58]
0x180065944  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180065949  or      ebx, 1
0x18006594c  mov     [rbp+57h+var_C0], ebx
0x18006594f  mov     rcx, rdi; this
0x180065952  call    ?exists@filesystem@std@@YA_NAEBVpath@12@@Z; std::filesystem::exists(std::filesystem::path const &)
0x180065957  mov     rcx, [rbp+5Fh]; this
0x18006595b  test    al, al
0x18006595d  jz      short loc_1800659A3
0x18006595f  mov     rcx, [rsi]
0x180065962  mov     rax, [rcx]
0x180065965  mov     edx, 1
0x18006596a  mov     rcx, rsi
0x18006596d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180065972  nop
0x180065973  lea     rcx, [rbp+57h+var_38]
0x180065977  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006597c  mov     rax, rdi
0x18006597f  mov     rcx, [rbp+57h+var_18]
0x180065983  xor     rcx, rsp; StackCookie
0x180065986  call    __security_check_cookie
0x18006598b  lea     r11, [rsp+100h+var_10]
0x180065993  mov     rbx, [r11+20h]
0x180065997  mov     rsi, [r11+38h]
0x18006599b  mov     rsp, r11
0x18006599e  pop     r15
0x1800659a0  pop     rdi
0x1800659a1  pop     rbp
0x1800659a2  retn
0x1800659a3  mov     r9d, 80070002h; char *
0x1800659a9  lea     r8, aOnecoreEnduser_18; "onecore\\enduser\\windowsupdate\\muse\\"...
0x1800659b0  mov     edx, 42h ; 'B'; void *
0x1800659b5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800659bb  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
