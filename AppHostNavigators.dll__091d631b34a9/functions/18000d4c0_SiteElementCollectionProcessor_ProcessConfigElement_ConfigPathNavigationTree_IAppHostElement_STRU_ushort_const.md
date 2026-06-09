# SiteElementCollectionProcessor::ProcessConfigElement(ConfigPathNavigationTree *,IAppHostElement *,STRU &,ushort const *)

- ea: `0x18000d4c0`
- end: `0x18000d585`
- name: `?ProcessConfigElement@SiteElementCollectionProcessor@@UEAAXPEAVConfigPathNavigationTree@@PEAUIAppHostElement@@AEAVSTRU@@PEBG@Z`
- size: `197`
- prototype: `void(SiteElementCollectionProcessor *__hidden this, struct ConfigPathNavigationTree *, struct IAppHostElement *, struct STRU *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800018a0`
- `0x180001910`
- `0x180001a30`
- `0x18000d1a8`
- `0x18000d4c0`
- `0x1800105a0`

## pseudocode

```c
void __fastcall SiteElementCollectionProcessor::ProcessConfigElement(
        SiteElementCollectionProcessor *this,
        struct ConfigPathNavigationTree *a2,
        struct IAppHostElement *a3,
        struct STRU *a4,
        const unsigned __int16 *a5)
{
  _QWORD v9[9]; // [rsp+30h] [rbp-48h] BYREF

  if ( dword_18001E5D0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_18001E5D0);
    if ( dword_18001E5D0 == -1 )
    {
      atexit(SiteElementCollectionProcessor::ProcessConfigElement_::_2_::_dynamic_atexit_destructor_for__bstrPathString__);
      Init_thread_footer(&dword_18001E5D0);
    }
  }
  Helpers::EnsureInitializedSerialized((struct ScopedBSTR *)&qword_18001E5A8, (OLECHAR *)L"path");
  v9[0] = &ApplicationElementCollectionProcessor::`vftable';
  v9[2] = a5;
  v9[1] = this;
  v9[3] = 0;
  SiteSectionElementCollectionProcessorBase::Invoke(
    (SiteSectionElementCollectionProcessorBase *)v9,
    a2,
    a3,
    qword_18001E5A8,
    a4);
}

```

## disassembly

```asm
0x18000d4c0  push    rbx
0x18000d4c2  push    rbp
0x18000d4c3  push    rsi
0x18000d4c4  push    rdi
0x18000d4c5  sub     rsp, 58h
0x18000d4c9  mov     r10d, cs:_tls_index
0x18000d4d0  mov     rbp, rcx
0x18000d4d3  mov     rax, gs:58h
0x18000d4dc  mov     rbx, r9
0x18000d4df  mov     ecx, 4
0x18000d4e4  mov     rdi, r8
0x18000d4e7  mov     rsi, rdx
0x18000d4ea  mov     rax, [rax+r10*8]
0x18000d4ee  mov     eax, [rcx+rax]
0x18000d4f1  cmp     cs:dword_18001E5D0, eax
0x18000d4f7  jle     short loc_18000D526
0x18000d4f9  lea     rcx, dword_18001E5D0
0x18000d500  call    _Init_thread_header
0x18000d505  cmp     cs:dword_18001E5D0, 0FFFFFFFFh
0x18000d50c  jnz     short loc_18000D526
0x18000d50e  lea     rcx, _SiteElementCollectionProcessor__ProcessConfigElement____2____dynamic_atexit_destructor_for__bstrPathString__; void (__cdecl *)()
0x18000d515  call    atexit
0x18000d51a  lea     rcx, dword_18001E5D0
0x18000d521  call    _Init_thread_footer
0x18000d526  lea     rdx, aPath; "path"
0x18000d52d  lea     rcx, qword_18001E5A8; this
0x18000d534  call    ?EnsureInitializedSerialized@Helpers@@SAXAEAVScopedBSTR@@PEBG@Z; Helpers::EnsureInitializedSerialized(ScopedBSTR &,ushort const *)
0x18000d539  mov     r9, cs:qword_18001E5A8; unsigned __int16 *
0x18000d540  lea     rax, ??_7ApplicationElementCollectionProcessor@@6B@; const ApplicationElementCollectionProcessor::`vftable'
0x18000d547  mov     [rsp+78h+var_48], rax
0x18000d54c  lea     rcx, [rsp+78h+var_48]; this
0x18000d551  mov     rax, [rsp+78h+arg_20]
0x18000d559  mov     r8, rdi; struct IAppHostElement *
0x18000d55c  mov     rdx, rsi; struct ConfigPathNavigationTree *
0x18000d55f  mov     [rsp+78h+var_38], rax
0x18000d564  mov     [rsp+78h+var_40], rbp
0x18000d569  mov     [rsp+78h+var_30], 0
0x18000d572  mov     [rsp+78h+var_58], rbx; struct STRU *
0x18000d577  call    ?Invoke@SiteSectionElementCollectionProcessorBase@@QEAAXPEAVConfigPathNavigationTree@@PEAUIAppHostElement@@PEAGAEAVSTRU@@@Z; SiteSectionElementCollectionProcessorBase::Invoke(ConfigPathNavigationTree *,IAppHostElement *,ushort *,STRU &)
0x18000d57c  add     rsp, 58h
0x18000d580  pop     rdi
0x18000d581  pop     rsi
0x18000d582  pop     rbp
0x18000d583  pop     rbx
0x18000d584  retn
```
