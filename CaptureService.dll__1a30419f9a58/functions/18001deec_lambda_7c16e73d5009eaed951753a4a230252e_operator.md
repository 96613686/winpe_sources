# _lambda_7c16e73d5009eaed951753a4a230252e_::operator()

- ea: `0x18001deec`
- end: `0x18001dfbe`
- name: `_lambda_7c16e73d5009eaed951753a4a230252e_::operator()`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001dfd0`

## callees

- `0x180005548`
- `0x18000ddc4`
- `0x180014cec`
- `0x180017ac0`
- `0x18001deec`
- `0x18001ea08`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001df08`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001df08`

## string_xrefs

- `0x18001dfac`: `onecoreuap\windows\dwm\capture\svc\dll\capturesessionmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall lambda_7c16e73d5009eaed951753a4a230252e_::operator()(struct _RTL_CRITICAL_SECTION **a1)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rbx
  struct _RTL_CRITICAL_SECTION_DEBUG *v4; // rsi
  Windows::Graphics::Capture::Server::CapturableItem *v5; // rdi
  int v6; // eax
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  Windows::Graphics::Capture::Server::CapturableItem *v9; // [rsp+30h] [rbp+8h] BYREF
  struct _RTL_CRITICAL_SECTION *v10; // [rsp+38h] [rbp+10h] BYREF

  v2 = *a1 + 1;
  EnterCriticalSection(v2);
  v10 = v2;
  DebugInfo = (*a1)->DebugInfo;
  v4 = *(struct _RTL_CRITICAL_SECTION_DEBUG **)&(*a1)->LockCount;
  while ( DebugInfo != v4 )
  {
    v5 = *(Windows::Graphics::Capture::Server::CapturableItem **)(*(_QWORD *)&DebugInfo->Type + 64LL);
    v9 = v5;
    if ( v5 )
      (*(void (__fastcall **)(Windows::Graphics::Capture::Server::CapturableItem *))(*(_QWORD *)v5 + 8LL))(v5);
    if ( *((_BYTE *)v5 + 105)
      && !Windows::Graphics::Capture::Server::CheckCAMCapability(0, *(_DWORD *)(*(_QWORD *)&DebugInfo->Type + 108LL)) )
    {
      v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)&DebugInfo->Type + 40LL) + 56LL))(*(_QWORD *)&DebugInfo->Type + 40LL);
      if ( v6 < 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x2B,
          (unsigned int)"onecoreuap\\windows\\dwm\\capture\\svc\\dll\\capturesessionmanager.cpp",
          (const char *)(unsigned int)v6,
          v7);
      Windows::Graphics::Capture::Server::CapturableItem::SignalClosedEvent(v5);
    }
    wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v9);
    DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)((char *)DebugInfo + 8);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v10);
}

```

## disassembly

```asm
0x18001deec  mov     [rsp+arg_10], rbx
0x18001def1  mov     [rsp+arg_18], rsi
0x18001def6  push    rdi
0x18001def7  sub     rsp, 20h
0x18001defb  mov     rdi, rcx
0x18001defe  mov     rbx, [rcx]
0x18001df01  add     rbx, 28h ; '('
0x18001df05  mov     rcx, rbx; lpCriticalSection
0x18001df08  call    cs:__imp_EnterCriticalSection
0x18001df0e  mov     [rsp+28h+arg_8], rbx
0x18001df13  mov     rax, [rdi]
0x18001df16  mov     rbx, [rax]
0x18001df19  mov     rsi, [rax+8]
0x18001df1d  jmp     short loc_18001DF8A
0x18001df1f  mov     rax, [rbx]
0x18001df22  mov     rdi, [rax+40h]
0x18001df26  mov     [rsp+28h+arg_0], rdi
0x18001df2b  test    rdi, rdi
0x18001df2e  jz      short loc_18001DF40
0x18001df30  mov     rax, [rdi]
0x18001df33  mov     rcx, rdi
0x18001df36  mov     rax, [rax+8]
0x18001df3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df3f  nop
0x18001df40  cmp     byte ptr [rdi+69h], 0
0x18001df44  jz      short loc_18001DF7C
0x18001df46  mov     rdx, [rbx]
0x18001df49  mov     edx, [rdx+6Ch]
0x18001df4c  xor     ecx, ecx
0x18001df4e  call    ?CheckCAMCapability@Server@Capture@Graphics@Windows@@YA_NW4CaptureServerAccessRequestKind@1234@K@Z; Windows::Graphics::Capture::Server::CheckCAMCapability(Windows::Graphics::Capture::Server::CaptureServerAccessRequestKind,ulong)
0x18001df53  test    al, al
0x18001df55  jnz     short loc_18001DF7C
0x18001df57  mov     rcx, [rbx]
0x18001df5a  add     rcx, 28h ; '('
0x18001df5e  mov     rax, [rcx]
0x18001df61  mov     rax, [rax+38h]
0x18001df65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df6a  mov     rcx, [rsp+28h]; this
0x18001df6f  test    eax, eax
0x18001df71  js      short loc_18001DFA9
0x18001df73  mov     rcx, rdi; this
0x18001df76  call    ?SignalClosedEvent@CapturableItem@Server@Capture@Graphics@Windows@@QEAAXXZ; Windows::Graphics::Capture::Server::CapturableItem::SignalClosedEvent(void)
0x18001df7b  nop
0x18001df7c  lea     rcx, [rsp+28h+arg_0]
0x18001df81  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x18001df86  add     rbx, 8
0x18001df8a  cmp     rbx, rsi
0x18001df8d  jnz     short loc_18001DF1F
0x18001df8f  lea     rcx, [rsp+28h+arg_8]
0x18001df94  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18001df99  mov     rbx, [rsp+28h+arg_10]
0x18001df9e  mov     rsi, [rsp+28h+arg_18]
0x18001dfa3  add     rsp, 20h
0x18001dfa7  pop     rdi
0x18001dfa8  retn
0x18001dfa9  mov     r9d, eax; char *
0x18001dfac  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\dwm\\capture\\svc"...
0x18001dfb3  mov     edx, 2Bh ; '+'; void *
0x18001dfb8  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
