# Windows::Internal::CapabilityAccess::Private::GetAppSelector(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Windows::Internal::CapabilityAccess::Private::AppIdType,ulong)

- ea: `0x180040930`
- end: `0x180040a77`
- name: `?GetAppSelector@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@W4AppIdType@1234@K@Z`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180048784`

## callees

- `0x1800094c0`
- `0x18000a0bc`
- `0x18001649c`
- `0x18001c3b4`
- `0x18002576c`
- `0x180029408`
- `0x1800299c4`
- `0x18002e304`
- `0x180039e9c`
- `0x18003f4a0`
- `0x18003f928`
- `0x180040930`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180040980`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800409c3`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800409c3`
- `api-ms-win-appmodel-runtime-l1-1-0!GetApplicationUserModelId` at `0x180040a1c`
- `api-ms-win-appmodel-runtime-l1-1-0!GetApplicationUserModelId` at `0x180040a1c`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::GetAppSelector(
        __int64 a1,
        __int64 a2,
        int a3,
        DWORD a4)
{
  int v5; // eax
  HANDLE v6; // rbx
  const char *v7; // r9
  unsigned int v8; // eax
  unsigned int v10; // [rsp+20h] [rbp-E0h]
  UINT32 applicationUserModelIdLength; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v12[2]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v13[16]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v14; // [rsp+58h] [rbp-A8h]
  WCHAR applicationUserModelId[136]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v12[0] = a1;
  if ( a3 == 2 )
  {
    Windows::Internal::CapabilityAccess::Private::BinaryNameFromBinaryFullPath(v13, a2);
    v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v13);
    std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
      (unsigned int)v12,
      v5,
      v5 + 2 * v14,
      v5,
      *(__int64 *)&_o_towlower);
    std::wstring::wstring(a1, v13);
    std::wstring::_Tidy_deallocate(v13);
  }
  else
  {
    v6 = OpenProcess(0x1000u, 0, a4);
    v12[0] = v6;
    if ( (((unsigned __int64)v6 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x908,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
        v7);
    memset_0(applicationUserModelId, 0, 0x104u);
    applicationUserModelIdLength = 130;
    v8 = GetApplicationUserModelId(v6, &applicationUserModelIdLength, applicationUserModelId);
    if ( v8 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x90D,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
        (const char *)v8,
        v10);
    std::wstring::wstring(a1, applicationUserModelId);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v12);
  }
  return a1;
}

```

## disassembly

```asm
0x180040930  push    rbp
0x180040932  push    rbx
0x180040933  push    rdi
0x180040934  lea     rbp, [rsp-90h]
0x18004093c  sub     rsp, 190h
0x180040943  mov     rax, cs:__security_cookie
0x18004094a  xor     rax, rsp
0x18004094d  mov     [rbp+0A0h+var_20], rax
0x180040954  mov     rdi, rcx
0x180040957  mov     [rsp+1A0h+var_168], rcx
0x18004095c  cmp     r8d, 2
0x180040960  jnz     short loc_1800409B9
0x180040962  lea     rcx, [rsp+1A0h+var_158]
0x180040967  call    ?BinaryNameFromBinaryFullPath@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV56@@Z; Windows::Internal::CapabilityAccess::Private::BinaryNameFromBinaryFullPath(std::wstring const &)
0x18004096c  nop
0x18004096d  lea     rcx, [rsp+1A0h+var_158]
0x180040972  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180040977  mov     rcx, [rsp+1A0h+var_148]
0x18004097c  lea     r8, [rax+rcx*2]
0x180040980  mov     rcx, cs:__imp__o_towlower
0x180040987  mov     qword ptr [rsp+1A0h+var_180], rcx
0x18004098c  mov     r9, rax
0x18004098f  mov     rdx, rax
0x180040992  lea     rcx, [rsp+1A0h+var_168]
0x180040997  call    ??$transform@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@P6AGG@Z@std@@YA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0V10@P6AGG@Z@Z; std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort)>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort))
0x18004099c  lea     rdx, [rsp+1A0h+var_158]
0x1800409a1  mov     rcx, rdi
0x1800409a4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800409a9  nop
0x1800409aa  lea     rcx, [rsp+1A0h+var_158]
0x1800409af  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800409b4  jmp     loc_180040A5A
0x1800409b9  mov     r8d, r9d; dwProcessId
0x1800409bc  xor     edx, edx; bInheritHandle
0x1800409be  mov     ecx, 1000h; dwDesiredAccess
0x1800409c3  call    cs:__imp_OpenProcess
0x1800409c9  mov     rbx, rax
0x1800409cc  mov     [rsp+1A0h+var_168], rax
0x1800409d1  inc     rax
0x1800409d4  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800409da  jnz     short loc_1800409F5
0x1800409dc  mov     rcx, [rbp+0A8h]; this
0x1800409e3  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x1800409ea  mov     edx, 908h; void *
0x1800409ef  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800409f5  xor     edx, edx; Val
0x1800409f7  mov     r8d, 104h; Size
0x1800409fd  lea     rcx, [rsp+1A0h+applicationUserModelId]; void *
0x180040a02  call    memset_0
0x180040a07  mov     [rsp+1A0h+applicationUserModelIdLength], 82h
0x180040a0f  lea     r8, [rsp+1A0h+applicationUserModelId]; applicationUserModelId
0x180040a14  lea     rdx, [rsp+1A0h+applicationUserModelIdLength]; applicationUserModelIdLength
0x180040a19  mov     rcx, rbx; hProcess
0x180040a1c  call    cs:__imp_GetApplicationUserModelId
0x180040a22  mov     rcx, [rbp+0A8h]; this
0x180040a29  test    eax, eax
0x180040a2b  jz      short loc_180040A42
0x180040a2d  mov     r9d, eax; char *
0x180040a30  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180040a37  mov     edx, 90Dh; void *
0x180040a3c  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180040a42  lea     rdx, [rsp+1A0h+applicationUserModelId]
0x180040a47  mov     rcx, rdi
0x180040a4a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180040a4f  nop
0x180040a50  lea     rcx, [rsp+1A0h+var_168]
0x180040a55  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180040a5a  mov     rax, rdi
0x180040a5d  mov     rcx, [rbp+0A0h+var_20]
0x180040a64  xor     rcx, rsp; StackCookie
0x180040a67  call    __security_check_cookie
0x180040a6c  add     rsp, 190h
0x180040a73  pop     rdi
0x180040a74  pop     rbx
0x180040a75  pop     rbp
0x180040a76  retn
```
