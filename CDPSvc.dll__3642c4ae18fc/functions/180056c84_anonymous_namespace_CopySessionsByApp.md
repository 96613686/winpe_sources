# _anonymous_namespace_::CopySessionsByApp

- ea: `0x180056c84`
- end: `0x180056ea2`
- name: `_anonymous_namespace_::CopySessionsByApp`
- size: `542`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180056ea8`

## callees

- `0x180004928`
- `0x180010d04`
- `0x1800130ec`
- `0x180043b48`
- `0x1800449b4`
- `0x1800568ac`
- `0x180056c84`
- `0x18006a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180056d63`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180056d63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180056d49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180056d57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180056d49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180056d57`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056d1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056d9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056e24`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056d1c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056d9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180056e24`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall anonymous_namespace_::CopySessionsByApp(struct IInspectable *a1, HSTRING a2, __int64 *a3)
{
  _QWORD *v5; // rcx
  _QWORD *v6; // rax
  __int64 v7; // rsi
  int v8; // eax
  unsigned int v9; // ebx
  struct IInspectable *v10; // rbx
  HRESULT (__stdcall *GetRuntimeClassName)(IInspectable *, HSTRING *); // rdi
  int v12; // eax
  PCWSTR StringRawBuffer; // rbx
  PCWSTR v14; // rax
  struct IInspectable **v15; // rdx
  struct IInspectable **v16; // rdx
  __int64 v18; // [rsp+20h] [rbp-10h] BYREF
  _QWORD *v19; // [rsp+28h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  struct IInspectable *v21; // [rsp+60h] [rbp+30h] BYREF
  HSTRING string; // [rsp+78h] [rbp+48h] BYREF

  v21 = a1;
  v5 = SharingPlatform::Internal::SessionsList::sm_allHostSessions;
  v6 = *(_QWORD **)SharingPlatform::Internal::SessionsList::sm_allHostSessions;
  v19 = *(_QWORD **)SharingPlatform::Internal::SessionsList::sm_allHostSessions;
  while ( v6 != v5 )
  {
    v7 = v6[6];
    v18 = v7;
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionIdentifier>::InternalAddRef(&v18);
    v21 = 0;
    v8 = Microsoft::WRL::WeakRef::As<SharingPlatform::ISession>((Microsoft::WRL::WeakRef *)&v18, &v21);
    v9 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A,
        (unsigned int)".\\sessionslist.cpp",
        (const char *)(unsigned int)v8,
        v18);
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v21);
      if ( v7 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      return v9;
    }
    v10 = v21;
    if ( v21 )
    {
      if ( a2 )
      {
        string = 0;
        GetRuntimeClassName = v21->lpVtbl[1].GetRuntimeClassName;
        WindowsDeleteString(0);
        string = 0;
        v12 = ((__int64 (__fastcall *)(struct IInspectable *, HSTRING *))GetRuntimeClassName)(v10, &string);
        v9 = v12;
        if ( v12 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2E,
            (unsigned int)".\\sessionslist.cpp",
            (const char *)(unsigned int)v12,
            v18);
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v21);
          if ( v7 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
          return v9;
        }
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        v14 = WindowsGetStringRawBuffer(a2, 0);
        if ( !(unsigned int)_o__wcsicmp(v14, StringRawBuffer) )
        {
          v15 = (struct IInspectable **)a3[1];
          if ( v15 == (struct IInspectable **)a3[2] )
          {
            std::vector<Microsoft::WRL::ComPtr<SharingPlatform::IParticipantIdentifier>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<SharingPlatform::IParticipantIdentifier> &>(
              a3,
              (__int64)v15,
              (__int64 *)&v21);
          }
          else
          {
            *v15 = v21;
            Microsoft::WRL::ComPtr<SharingPlatform::ISessionIdentifier>::InternalAddRef(v15);
            a3[1] += 8;
          }
        }
        WindowsDeleteString(string);
      }
      else
      {
        v16 = (struct IInspectable **)a3[1];
        if ( v16 == (struct IInspectable **)a3[2] )
        {
          std::vector<Microsoft::WRL::ComPtr<SharingPlatform::IParticipantIdentifier>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<SharingPlatform::IParticipantIdentifier> &>(
            a3,
            (__int64)v16,
            (__int64 *)&v21);
        }
        else
        {
          *v16 = v21;
          Microsoft::WRL::ComPtr<SharingPlatform::ISessionIdentifier>::InternalAddRef(v16);
          a3[1] += 8;
        }
      }
    }
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v21);
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,Microsoft::WRL::ComPtr<ICDPDevice>>>>,std::_Iterator_base0>::operator++(&v19);
    v6 = v19;
    v5 = SharingPlatform::Internal::SessionsList::sm_allHostSessions;
  }
  return 0;
}

```

## disassembly

```asm
0x180056c84  mov     [rsp-28h+arg_8], rbx
0x180056c89  mov     [rsp-28h+arg_0], rcx
0x180056c8e  push    rbp
0x180056c8f  push    rsi
0x180056c90  push    rdi
0x180056c91  push    r14
0x180056c93  push    r15
0x180056c95  mov     rbp, rsp
0x180056c98  sub     rsp, 30h
0x180056c9c  mov     r14, r8
0x180056c9f  mov     r15, rdx
0x180056ca2  mov     rcx, cs:?sm_allHostSessions@SessionsList@Internal@SharingPlatform@@0V?$map@U_GUID@@VWeakRef@WRL@Microsoft@@UGUIDComparer@Internal@SharingPlatform@@V?$allocator@U?$pair@$$CBU_GUID@@VWeakRef@WRL@Microsoft@@@std@@@std@@@std@@A; std::map<_GUID,Microsoft::WRL::WeakRef,SharingPlatform::Internal::GUIDComparer,std::allocator<std::pair<_GUID const,Microsoft::WRL::WeakRef>>> SharingPlatform::Internal::SessionsList::sm_allHostSessions
0x180056ca9  mov     rax, [rcx]
0x180056cac  mov     [rbp+var_8], rax
0x180056cb0  cmp     rax, rcx
0x180056cb3  jz      loc_180056E8F
0x180056cb9  mov     rsi, [rax+30h]
0x180056cbd  mov     [rbp+var_10], rsi
0x180056cc1  lea     rcx, [rbp+var_10]
0x180056cc5  call    ?InternalAddRef@?$ComPtr@UISessionIdentifier@SharingPlatform@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionIdentifier>::InternalAddRef(void)
0x180056cca  nop
0x180056ccb  mov     [rbp+arg_0], 0
0x180056cd3  lea     rdx, [rbp+arg_0]; struct IInspectable **
0x180056cd7  lea     rcx, [rbp+var_10]; this
0x180056cdb  call    ??$As@UISession@SharingPlatform@@@WeakRef@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UISession@SharingPlatform@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::WeakRef::As<SharingPlatform::ISession>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<SharingPlatform::ISession>>)
0x180056ce0  mov     ebx, eax
0x180056ce2  test    eax, eax
0x180056ce4  js      loc_180056E53
0x180056cea  mov     rbx, [rbp+arg_0]
0x180056cee  test    rbx, rbx
0x180056cf1  jnz     short loc_180056D02
0x180056cf3  lea     rcx, [rbp+arg_0]
0x180056cf7  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180056cfc  nop
0x180056cfd  jmp     loc_180056DD9
0x180056d02  test    r15, r15
0x180056d05  jz      loc_180056DA6
0x180056d0b  mov     [rbp+string], 0
0x180056d13  mov     rax, [rbx]
0x180056d16  mov     rdi, [rax+50h]
0x180056d1a  xor     ecx, ecx; string
0x180056d1c  call    cs:__imp_WindowsDeleteString
0x180056d22  mov     [rbp+string], 0
0x180056d2a  lea     rdx, [rbp+string]
0x180056d2e  mov     rcx, rbx
0x180056d31  mov     rax, rdi
0x180056d34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056d39  mov     ebx, eax
0x180056d3b  test    eax, eax
0x180056d3d  js      loc_180056E07
0x180056d43  xor     edx, edx; length
0x180056d45  mov     rcx, [rbp+string]; string
0x180056d49  call    cs:__imp_WindowsGetStringRawBuffer
0x180056d4f  mov     rbx, rax
0x180056d52  xor     edx, edx; length
0x180056d54  mov     rcx, r15; string
0x180056d57  call    cs:__imp_WindowsGetStringRawBuffer
0x180056d5d  mov     rdx, rbx
0x180056d60  mov     rcx, rax
0x180056d63  call    cs:__imp__o__wcsicmp
0x180056d69  test    eax, eax
0x180056d6b  jnz     short loc_180056D9A
0x180056d6d  mov     rdx, [r14+8]
0x180056d71  cmp     rdx, [r14+10h]
0x180056d75  jz      short loc_180056D8D
0x180056d77  mov     rax, [rbp+arg_0]
0x180056d7b  mov     [rdx], rax
0x180056d7e  mov     rcx, rdx
0x180056d81  call    ?InternalAddRef@?$ComPtr@UISessionIdentifier@SharingPlatform@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionIdentifier>::InternalAddRef(void)
0x180056d86  add     qword ptr [r14+8], 8
0x180056d8b  jmp     short loc_180056D9A
0x180056d8d  lea     r8, [rbp+arg_0]
0x180056d91  mov     rcx, r14
0x180056d94  call    ??$_Emplace_reallocate@AEAV?$ComPtr@UIParticipantIdentifier@SharingPlatform@@@WRL@Microsoft@@@?$vector@V?$ComPtr@UIParticipantIdentifier@SharingPlatform@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIParticipantIdentifier@SharingPlatform@@@WRL@Microsoft@@@std@@@std@@AEAAPEAV?$ComPtr@UIParticipantIdentifier@SharingPlatform@@@WRL@Microsoft@@QEAV234@AEAV234@@Z; std::vector<Microsoft::WRL::ComPtr<SharingPlatform::IParticipantIdentifier>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<SharingPlatform::IParticipantIdentifier> &>(Microsoft::WRL::ComPtr<SharingPlatform::IParticipantIdentifier> * const,Microsoft::WRL::ComPtr<SharingPlatform::IParticipantIdentifier> &)
0x180056d99  nop
0x180056d9a  mov     rcx, [rbp+string]; string
0x180056d9e  call    cs:__imp_WindowsDeleteString
0x180056da4  jmp     short loc_180056DCF
0x180056da6  mov     rdx, [r14+8]
0x180056daa  cmp     rdx, [r14+10h]
0x180056dae  jz      short loc_180056DC2
0x180056db0  mov     [rdx], rbx
0x180056db3  mov     rcx, rdx
0x180056db6  call    ?InternalAddRef@?$ComPtr@UISessionIdentifier@SharingPlatform@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionIdentifier>::InternalAddRef(void)
0x180056dbb  add     qword ptr [r14+8], 8
0x180056dc0  jmp     short loc_180056DCF
0x180056dc2  lea     r8, [rbp+arg_0]
0x180056dc6  mov     rcx, r14
0x180056dc9  call    ??$_Emplace_reallocate@AEAV?$ComPtr@UIParticipantIdentifier@SharingPlatform@@@WRL@Microsoft@@@?$vector@V?$ComPtr@UIParticipantIdentifier@SharingPlatform@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIParticipantIdentifier@SharingPlatform@@@WRL@Microsoft@@@std@@@std@@AEAAPEAV?$ComPtr@UIParticipantIdentifier@SharingPlatform@@@WRL@Microsoft@@QEAV234@AEAV234@@Z; std::vector<Microsoft::WRL::ComPtr<SharingPlatform::IParticipantIdentifier>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<SharingPlatform::IParticipantIdentifier> &>(Microsoft::WRL::ComPtr<SharingPlatform::IParticipantIdentifier> * const,Microsoft::WRL::ComPtr<SharingPlatform::IParticipantIdentifier> &)
0x180056dce  nop
0x180056dcf  lea     rcx, [rbp+arg_0]
0x180056dd3  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180056dd8  nop
0x180056dd9  test    rsi, rsi
0x180056ddc  jz      short loc_180056DEE
0x180056dde  mov     rax, [rsi]
0x180056de1  mov     rcx, rsi
0x180056de4  mov     rax, [rax+10h]
0x180056de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056ded  nop
0x180056dee  lea     rcx, [rbp+var_8]
0x180056df2  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$ComPtr@VICDPDevice@@@WRL@Microsoft@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,Microsoft::WRL::ComPtr<ICDPDevice>>>>,std::_Iterator_base0>::operator++(void)
0x180056df7  mov     rax, [rbp+var_8]
0x180056dfb  mov     rcx, cs:?sm_allHostSessions@SessionsList@Internal@SharingPlatform@@0V?$map@U_GUID@@VWeakRef@WRL@Microsoft@@UGUIDComparer@Internal@SharingPlatform@@V?$allocator@U?$pair@$$CBU_GUID@@VWeakRef@WRL@Microsoft@@@std@@@std@@@std@@A; std::map<_GUID,Microsoft::WRL::WeakRef,SharingPlatform::Internal::GUIDComparer,std::allocator<std::pair<_GUID const,Microsoft::WRL::WeakRef>>> SharingPlatform::Internal::SessionsList::sm_allHostSessions
0x180056e02  jmp     loc_180056CB0
0x180056e07  mov     rcx, [rbp+28h]; this
0x180056e0b  mov     r9d, ebx; char *
0x180056e0e  lea     r8, aSessionslistCp; ".\\sessionslist.cpp"
0x180056e15  mov     edx, 2Eh ; '.'; void *
0x180056e1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180056e1f  nop
0x180056e20  mov     rcx, [rbp+string]; string
0x180056e24  call    cs:__imp_WindowsDeleteString
0x180056e2a  mov     [rbp+string], 0
0x180056e32  lea     rcx, [rbp+arg_0]
0x180056e36  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180056e3b  nop
0x180056e3c  test    rsi, rsi
0x180056e3f  jz      short loc_180056E51
0x180056e41  mov     rax, [rsi]
0x180056e44  mov     rcx, rsi
0x180056e47  mov     rax, [rax+10h]
0x180056e4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056e50  nop
0x180056e51  jmp     short loc_180056E8B
0x180056e53  mov     rcx, [rbp+28h]; this
0x180056e57  mov     r9d, ebx; char *
0x180056e5a  lea     r8, aSessionslistCp; ".\\sessionslist.cpp"
0x180056e61  mov     edx, 1Ah; void *
0x180056e66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180056e6b  nop
0x180056e6c  lea     rcx, [rbp+arg_0]
0x180056e70  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180056e75  nop
0x180056e76  test    rsi, rsi
0x180056e79  jz      short loc_180056E8B
0x180056e7b  mov     rax, [rsi]
0x180056e7e  mov     rcx, rsi
0x180056e81  mov     rax, [rax+10h]
0x180056e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056e8a  nop
0x180056e8b  mov     eax, ebx
0x180056e8d  jmp     short loc_180056E91
0x180056e8f  xor     eax, eax
0x180056e91  mov     rbx, [rsp+30h+arg_8]
0x180056e96  add     rsp, 30h
0x180056e9a  pop     r15
0x180056e9c  pop     r14
0x180056e9e  pop     rdi
0x180056e9f  pop     rsi
0x180056ea0  pop     rbp
0x180056ea1  retn
```
