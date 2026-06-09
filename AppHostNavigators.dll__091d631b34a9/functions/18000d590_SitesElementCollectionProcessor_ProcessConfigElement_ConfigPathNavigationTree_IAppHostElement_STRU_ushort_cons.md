# SitesElementCollectionProcessor::ProcessConfigElement(ConfigPathNavigationTree *,IAppHostElement *,STRU &,ushort const *)

- ea: `0x18000d590`
- end: `0x18000d655`
- name: `?ProcessConfigElement@SitesElementCollectionProcessor@@UEAAXPEAVConfigPathNavigationTree@@PEAUIAppHostElement@@AEAVSTRU@@PEBG@Z`
- size: `197`
- prototype: `void(SitesElementCollectionProcessor *__hidden this, struct ConfigPathNavigationTree *, struct IAppHostElement *, struct STRU *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800018a0`
- `0x180001910`
- `0x180001a30`
- `0x18000d1a8`
- `0x18000d590`
- `0x1800105a0`

## pseudocode

```c
void __fastcall SitesElementCollectionProcessor::ProcessConfigElement(
        SitesElementCollectionProcessor *this,
        struct ConfigPathNavigationTree *a2,
        struct IAppHostElement *a3,
        struct STRU *a4,
        const unsigned __int16 *a5)
{
  _QWORD v9[9]; // [rsp+30h] [rbp-48h] BYREF

  if ( dword_18001E5C8 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_18001E5C8);
    if ( dword_18001E5C8 == -1 )
    {
      atexit(SitesElementCollectionProcessor::ProcessConfigElement_::_2_::_dynamic_atexit_destructor_for__bstrPathString__);
      Init_thread_footer(&dword_18001E5C8);
    }
  }
  Helpers::EnsureInitializedSerialized((struct ScopedBSTR *)&qword_18001E5A0, (OLECHAR *)L"path");
  v9[0] = &SiteElementCollectionProcessor::`vftable';
  v9[2] = a5;
  v9[1] = this;
  v9[3] = 0;
  SiteSectionElementCollectionProcessorBase::Invoke(
    (SiteSectionElementCollectionProcessorBase *)v9,
    a2,
    a3,
    qword_18001E5A0,
    a4);
}

```

## disassembly

```asm
0x18000d590  push    rbx
0x18000d592  push    rbp
0x18000d593  push    rsi
0x18000d594  push    rdi
0x18000d595  sub     rsp, 58h
0x18000d599  mov     r10d, cs:_tls_index
0x18000d5a0  mov     rbp, rcx
0x18000d5a3  mov     rax, gs:58h
0x18000d5ac  mov     rbx, r9
0x18000d5af  mov     ecx, 4
0x18000d5b4  mov     rdi, r8
0x18000d5b7  mov     rsi, rdx
0x18000d5ba  mov     rax, [rax+r10*8]
0x18000d5be  mov     eax, [rcx+rax]
0x18000d5c1  cmp     cs:dword_18001E5C8, eax
0x18000d5c7  jle     short loc_18000D5F6
0x18000d5c9  lea     rcx, dword_18001E5C8
0x18000d5d0  call    _Init_thread_header
0x18000d5d5  cmp     cs:dword_18001E5C8, 0FFFFFFFFh
0x18000d5dc  jnz     short loc_18000D5F6
0x18000d5de  lea     rcx, _SitesElementCollectionProcessor__ProcessConfigElement____2____dynamic_atexit_destructor_for__bstrPathString__; void (__cdecl *)()
0x18000d5e5  call    atexit
0x18000d5ea  lea     rcx, dword_18001E5C8
0x18000d5f1  call    _Init_thread_footer
0x18000d5f6  lea     rdx, aPath; "path"
0x18000d5fd  lea     rcx, qword_18001E5A0; this
0x18000d604  call    ?EnsureInitializedSerialized@Helpers@@SAXAEAVScopedBSTR@@PEBG@Z; Helpers::EnsureInitializedSerialized(ScopedBSTR &,ushort const *)
0x18000d609  mov     r9, cs:qword_18001E5A0; unsigned __int16 *
0x18000d610  lea     rax, ??_7SiteElementCollectionProcessor@@6B@; const SiteElementCollectionProcessor::`vftable'
0x18000d617  mov     [rsp+78h+var_48], rax
0x18000d61c  lea     rcx, [rsp+78h+var_48]; this
0x18000d621  mov     rax, [rsp+78h+arg_20]
0x18000d629  mov     r8, rdi; struct IAppHostElement *
0x18000d62c  mov     rdx, rsi; struct ConfigPathNavigationTree *
0x18000d62f  mov     [rsp+78h+var_38], rax
0x18000d634  mov     [rsp+78h+var_40], rbp
0x18000d639  mov     [rsp+78h+var_30], 0
0x18000d642  mov     [rsp+78h+var_58], rbx; struct STRU *
0x18000d647  call    ?Invoke@SiteSectionElementCollectionProcessorBase@@QEAAXPEAVConfigPathNavigationTree@@PEAUIAppHostElement@@PEAGAEAVSTRU@@@Z; SiteSectionElementCollectionProcessorBase::Invoke(ConfigPathNavigationTree *,IAppHostElement *,ushort *,STRU &)
0x18000d64c  add     rsp, 58h
0x18000d650  pop     rdi
0x18000d651  pop     rsi
0x18000d652  pop     rbp
0x18000d653  pop     rbx
0x18000d654  retn
```
