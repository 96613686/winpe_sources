# ApphostNodeChildrenInitializer::Invoke(ConfigPathNavigationTree *,ConfigPathTagNode *)

- ea: `0x18000cee0`
- end: `0x18000d0fc`
- name: `?Invoke@ApphostNodeChildrenInitializer@@EEAAXPEAVConfigPathNavigationTree@@PEAVConfigPathTagNode@@@Z`
- size: `540`
- prototype: `void(ApphostNodeChildrenInitializer *__hidden this, struct ConfigPathNavigationTree *, struct ConfigPathTagNode *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800018a0`
- `0x180001910`
- `0x180001a30`
- `0x1800021a4`
- `0x1800021e0`
- `0x18000c8a8`
- `0x18000cee0`
- `0x18000d1a8`
- `0x1800105a0`
- `0x180012f3c`
- `0x1800130a0`
- `0x180014010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ApphostNodeChildrenInitializer::Invoke(
        ApphostNodeChildrenInitializer *this,
        struct ConfigPathNavigationTree *a2,
        struct ConfigPathTagNode *a3)
{
  __int64 v5; // rbx
  int v6; // eax
  int pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  struct IAppHostElement *v8; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v9[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v10[4]; // [rsp+50h] [rbp-B0h] BYREF
  int v11; // [rsp+54h] [rbp-ACh]
  __int16 *v12; // [rsp+58h] [rbp-A8h]
  int v13; // [rsp+60h] [rbp-A0h]
  __int16 v14; // [rsp+70h] [rbp-90h] BYREF

  v5 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( dword_18001E5C4 > *(_DWORD *)(v5 + 4) )
  {
    Init_thread_header(&dword_18001E5C4);
    if ( dword_18001E5C4 == -1 )
    {
      atexit(ApphostNodeChildrenInitializer::Invoke_::_2_::_dynamic_atexit_destructor_for__bstrSiteSectionPath__);
      Init_thread_footer(&dword_18001E5C4);
    }
  }
  Helpers::EnsureInitializedSerialized(
    (struct ScopedBSTR *)&qword_18001E590,
    (OLECHAR *)L"system.applicationHost/sites");
  if ( dword_18001E5C0 > *(_DWORD *)(v5 + 4) )
  {
    Init_thread_header(&dword_18001E5C0);
    if ( dword_18001E5C0 == -1 )
    {
      atexit(ApphostNodeChildrenInitializer::Invoke_::_2_::_dynamic_atexit_destructor_for__bstrAppHostConfigPath__);
      Init_thread_footer(&dword_18001E5C0);
    }
  }
  Helpers::EnsureInitializedSerialized((struct ScopedBSTR *)&qword_18001E5B0, (OLECHAR *)L"MACHINE/WEBROOT/APPHOST");
  if ( dword_18001E5CC > *(_DWORD *)(v5 + 4) )
  {
    Init_thread_header(&dword_18001E5CC);
    if ( dword_18001E5CC == -1 )
    {
      atexit(ApphostNodeChildrenInitializer::Invoke_::_2_::_dynamic_atexit_destructor_for__bstrNameString__);
      Init_thread_footer(&dword_18001E5CC);
    }
  }
  Helpers::EnsureInitializedSerialized((struct ScopedBSTR *)&qword_18001E5B8, (OLECHAR *)L"name");
  v8 = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, struct IAppHostElement **))(**(_QWORD **)(*((_QWORD *)a2 + 20)
                                                                                                  + 16LL)
                                                                                    + 24LL))(
         *(_QWORD *)(*((_QWORD *)a2 + 20) + 16LL),
         qword_18001E590,
         qword_18001E5B0,
         &v8);
  if ( v6 < 0 )
  {
    pExceptionObject = v6;
    throw (long *)&pExceptionObject;
  }
  v10[2] = 0;
  v11 = 520;
  v12 = &v14;
  v13 = 0;
  v14 = 0;
  ConfigPathNode::GetConfigPath(a3, a2, (struct STRU *)v10);
  v9[0] = &SitesElementCollectionProcessor::`vftable';
  v9[1] = a3;
  SiteSectionElementCollectionProcessorBase::Invoke(
    (SiteSectionElementCollectionProcessorBase *)v9,
    a2,
    v8,
    qword_18001E5B8,
    (struct STRU *)v10);
  BUFFER::~BUFFER((BUFFER *)v10);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v8);
}

```

## disassembly

```asm
0x18000cee0  mov     [rsp-8+arg_0], rbx
0x18000cee5  mov     [rsp-8+arg_18], rsi
0x18000ceea  push    rbp
0x18000ceeb  push    rdi
0x18000ceec  push    r14
0x18000ceee  lea     rbp, [rsp-190h]
0x18000cef6  sub     rsp, 290h
0x18000cefd  mov     rax, cs:__security_cookie
0x18000cf04  xor     rax, rsp
0x18000cf07  mov     [rbp+1A0h+var_20], rax
0x18000cf0e  mov     rsi, r8
0x18000cf11  mov     rdi, rdx
0x18000cf14  mov     ecx, cs:_tls_index
0x18000cf1a  mov     rax, gs:58h
0x18000cf23  mov     r14d, 4
0x18000cf29  mov     rbx, [rax+rcx*8]
0x18000cf2d  mov     eax, [rbx+r14]
0x18000cf31  cmp     cs:dword_18001E5C4, eax
0x18000cf37  jle     short loc_18000CF66
0x18000cf39  lea     rcx, dword_18001E5C4
0x18000cf40  call    _Init_thread_header
0x18000cf45  cmp     cs:dword_18001E5C4, 0FFFFFFFFh
0x18000cf4c  jnz     short loc_18000CF66
0x18000cf4e  lea     rcx, _ApphostNodeChildrenInitializer__Invoke____2____dynamic_atexit_destructor_for__bstrSiteSectionPath__; void (__cdecl *)()
0x18000cf55  call    atexit
0x18000cf5a  lea     rcx, dword_18001E5C4
0x18000cf61  call    _Init_thread_footer
0x18000cf66  lea     rdx, aSystemApplicat; "system.applicationHost/sites"
0x18000cf6d  lea     rcx, qword_18001E590; this
0x18000cf74  call    ?EnsureInitializedSerialized@Helpers@@SAXAEAVScopedBSTR@@PEBG@Z; Helpers::EnsureInitializedSerialized(ScopedBSTR &,ushort const *)
0x18000cf79  mov     eax, [rbx+r14]
0x18000cf7d  cmp     cs:dword_18001E5C0, eax
0x18000cf83  jle     short loc_18000CFB2
0x18000cf85  lea     rcx, dword_18001E5C0
0x18000cf8c  call    _Init_thread_header
0x18000cf91  cmp     cs:dword_18001E5C0, 0FFFFFFFFh
0x18000cf98  jnz     short loc_18000CFB2
0x18000cf9a  lea     rcx, _ApphostNodeChildrenInitializer__Invoke____2____dynamic_atexit_destructor_for__bstrAppHostConfigPath__; void (__cdecl *)()
0x18000cfa1  call    atexit
0x18000cfa6  lea     rcx, dword_18001E5C0
0x18000cfad  call    _Init_thread_footer
0x18000cfb2  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18000cfb9  lea     rcx, qword_18001E5B0; this
0x18000cfc0  call    ?EnsureInitializedSerialized@Helpers@@SAXAEAVScopedBSTR@@PEBG@Z; Helpers::EnsureInitializedSerialized(ScopedBSTR &,ushort const *)
0x18000cfc5  mov     eax, [rbx+r14]
0x18000cfc9  cmp     cs:dword_18001E5CC, eax
0x18000cfcf  jle     short loc_18000CFFE
0x18000cfd1  lea     rcx, dword_18001E5CC
0x18000cfd8  call    _Init_thread_header
0x18000cfdd  cmp     cs:dword_18001E5CC, 0FFFFFFFFh
0x18000cfe4  jnz     short loc_18000CFFE
0x18000cfe6  lea     rcx, _ApphostNodeChildrenInitializer__Invoke____2____dynamic_atexit_destructor_for__bstrNameString__; void (__cdecl *)()
0x18000cfed  call    atexit
0x18000cff2  lea     rcx, dword_18001E5CC
0x18000cff9  call    _Init_thread_footer
0x18000cffe  lea     rdx, aName; "name"
0x18000d005  lea     rcx, qword_18001E5B8; this
0x18000d00c  call    ?EnsureInitializedSerialized@Helpers@@SAXAEAVScopedBSTR@@PEBG@Z; Helpers::EnsureInitializedSerialized(ScopedBSTR &,ushort const *)
0x18000d011  xor     ebx, ebx
0x18000d013  mov     [rsp+2A0h+var_268], rbx
0x18000d018  mov     rax, [rdi+0A0h]
0x18000d01f  mov     rcx, [rax+10h]
0x18000d023  mov     rax, [rcx]
0x18000d026  lea     r9, [rsp+2A0h+var_268]
0x18000d02b  mov     r8, cs:qword_18001E5B0
0x18000d032  mov     rdx, cs:qword_18001E590
0x18000d039  mov     rax, [rax+18h]
0x18000d03d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d042  test    eax, eax
0x18000d044  jns     short loc_18000D05C
0x18000d046  mov     [rsp+2A0h+pExceptionObject], eax
0x18000d04a  lea     rdx, _TI1J; pThrowInfo
0x18000d051  lea     rcx, [rsp+2A0h+pExceptionObject]; pExceptionObject
0x18000d056  call    _CxxThrowException_0
0x18000d05c  mov     [rsp+2A0h+var_24E], bl
0x18000d060  mov     [rsp+2A0h+var_24C], 208h
0x18000d068  lea     rax, [rsp+2A0h+var_230]
0x18000d06d  mov     [rsp+2A0h+var_248], rax
0x18000d072  mov     [rsp+2A0h+var_240], ebx
0x18000d076  mov     [rsp+2A0h+var_230], bx
0x18000d07b  lea     r8, [rsp+2A0h+var_250]; struct STRU *
0x18000d080  mov     rdx, rdi; struct ConfigPathNavigationTree *
0x18000d083  mov     rcx, rsi; this
0x18000d086  call    ?GetConfigPath@ConfigPathNode@@QEAAXPEAVConfigPathNavigationTree@@AEAVSTRU@@@Z; ConfigPathNode::GetConfigPath(ConfigPathNavigationTree *,STRU &)
0x18000d08b  lea     rax, ??_7SitesElementCollectionProcessor@@6B@; const SitesElementCollectionProcessor::`vftable'
0x18000d092  mov     [rsp+2A0h+var_260], rax
0x18000d097  mov     [rsp+2A0h+var_258], rsi
0x18000d09c  lea     rax, [rsp+2A0h+var_250]
0x18000d0a1  mov     [rsp+2A0h+var_280], rax; struct STRU *
0x18000d0a6  mov     r9, cs:qword_18001E5B8; unsigned __int16 *
0x18000d0ad  mov     r8, [rsp+2A0h+var_268]; struct IAppHostElement *
0x18000d0b2  mov     rdx, rdi; struct ConfigPathNavigationTree *
0x18000d0b5  lea     rcx, [rsp+2A0h+var_260]; this
0x18000d0ba  call    ?Invoke@SiteSectionElementCollectionProcessorBase@@QEAAXPEAVConfigPathNavigationTree@@PEAUIAppHostElement@@PEAGAEAVSTRU@@@Z; SiteSectionElementCollectionProcessorBase::Invoke(ConfigPathNavigationTree *,IAppHostElement *,ushort *,STRU &)
0x18000d0bf  nop
0x18000d0c0  lea     rcx, [rsp+2A0h+var_250]; this
0x18000d0c5  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000d0ca  nop
0x18000d0cb  lea     rcx, [rsp+2A0h+var_268]
0x18000d0d0  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000d0d5  mov     rcx, [rbp+1A0h+var_20]
0x18000d0dc  xor     rcx, rsp; StackCookie
0x18000d0df  call    __security_check_cookie
0x18000d0e4  lea     r11, [rsp+2A0h+var_10]
0x18000d0ec  mov     rbx, [r11+20h]
0x18000d0f0  mov     rsi, [r11+38h]
0x18000d0f4  mov     rsp, r11
0x18000d0f7  pop     r14
0x18000d0f9  pop     rdi
0x18000d0fa  pop     rbp
0x18000d0fb  retn
```
