# CCbsTiPackage::GetIdentity(ICbsIdentity * *)

- ea: `0x140013724`
- end: `0x1400138d4`
- name: `?GetIdentity@CCbsTiPackage@@UEAAJPEAPEAUICbsIdentity@@@Z`
- size: `432`
- prototype: `__int64 __fastcall(CCbsTiPackage *__hidden this, struct ICbsIdentity **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x140013710`

## callees

- `0x140002070`
- `0x1400023e0`
- `0x140002674`
- `0x140013724`
- `0x140017658`
- `0x140023280`
- `0x1400247ec`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1400137d3`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1400137d3`

## string_xrefs

- `0x1400137df`: `Failed to get task allocator for Trusted Installer.`

## pseudocode

```c
__int64 __fastcall CCbsTiPackage::GetIdentity(CCbsTiPackage *this, struct ICbsIdentity **a2)
{
  wchar_t *v2; // rdi
  unsigned int v5; // ebx
  __int64 v6; // rcx
  const wchar_t *v7; // rcx
  int QuickIdentity; // eax
  HRESULT Malloc; // eax
  CCbsIdentity *v10; // rax
  CCbsIdentity *v11; // rax
  struct ICbsIdentity *v12; // r14
  int v13; // eax
  wchar_t *v15; // [rsp+30h] [rbp-38h] BYREF
  LPMALLOC ppMalloc; // [rsp+38h] [rbp-30h] BYREF

  v2 = 0;
  v15 = 0;
  ppMalloc = 0;
  if ( !a2 )
  {
    v5 = -2147467261;
    CBSWdsLogLight(0x4000000u, 0x80004003, (size_t *)1, "NULL Identity");
    goto LABEL_18;
  }
  v6 = *((_QWORD *)this - 2);
  if ( v6 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 24LL))(v6);
    goto LABEL_18;
  }
  v7 = (const wchar_t *)*((_QWORD *)this - 7);
  if ( v7 )
  {
    QuickIdentity = GetQuickIdentity(v7, &v15);
    if ( QuickIdentity < 0 )
      CBSWdsLogLight(0x4000000u, (unsigned int)QuickIdentity, (size_t *)1, "Unable to process package string");
    Malloc = CoGetMalloc(1u, &ppMalloc);
    v5 = Malloc;
    if ( Malloc < 0 )
    {
      CBSWdsLogLight(
        0x4000000u,
        (unsigned int)Malloc,
        (size_t *)1,
        "Failed to get task allocator for Trusted Installer.");
LABEL_10:
      v2 = v15;
      goto LABEL_18;
    }
    v10 = (CCbsIdentity *)operator new(0x338u);
    if ( !v10 || (v11 = CCbsIdentity::CCbsIdentity(v10, ppMalloc), (v12 = v11) == 0) )
    {
      v5 = -2147024882;
      CBSWdsLogLight(0x4000000u, 0x8007000E, (size_t *)1, "Failed to allocate identity.");
      goto LABEL_10;
    }
    v2 = v15;
    v13 = (*(__int64 (__fastcall **)(CCbsIdentity *, wchar_t *))(*(_QWORD *)v11 + 56LL))(v11, v15);
    v5 = v13;
    if ( v13 >= 0 )
    {
      *a2 = v12;
    }
    else
    {
      CBSWdsLogLight(0x4000000u, (unsigned int)v13, (size_t *)1, "Failed to load from string: %S", v2);
      (*(void (__fastcall **)(struct ICbsIdentity *))(*(_QWORD *)v12 + 16LL))(v12);
    }
  }
  else
  {
    v5 = -2147467263;
  }
LABEL_18:
  if ( ppMalloc )
    ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
  if ( v2 )
    operator delete(v2 - 4);
  return v5;
}

```

## disassembly

```asm
0x140013724  mov     [rsp+arg_10], rbx
0x140013729  push    rdi
0x14001372a  push    r14
0x14001372c  push    r15
0x14001372e  sub     rsp, 50h
0x140013732  mov     rax, cs:__security_cookie
0x140013739  xor     rax, rsp
0x14001373c  mov     [rsp+68h+var_28], rax
0x140013741  xor     edi, edi
0x140013743  mov     r15, rdx
0x140013746  mov     [rsp+68h+var_38], rdi
0x14001374b  mov     rax, rcx
0x14001374e  mov     [rsp+68h+ppMalloc], rdi
0x140013753  test    rdx, rdx
0x140013756  jnz     short loc_140013779
0x140013758  lea     r8d, [rdx+1]
0x14001375c  mov     ebx, 80004003h
0x140013761  mov     edx, ebx
0x140013763  lea     r9, aNullIdentity; "NULL Identity"
0x14001376a  mov     ecx, 4000000h
0x14001376f  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140013774  jmp     loc_14001388F
0x140013779  mov     rcx, [rcx-10h]
0x14001377d  test    rcx, rcx
0x140013780  jz      short loc_140013795
0x140013782  mov     rax, [rcx]
0x140013785  mov     rax, [rax+18h]
0x140013789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001378e  mov     ebx, eax
0x140013790  jmp     loc_14001388F
0x140013795  mov     rcx, [rax-38h]; Str
0x140013799  test    rcx, rcx
0x14001379c  jz      loc_14001388A
0x1400137a2  lea     rdx, [rsp+68h+var_38]; wchar_t **
0x1400137a7  call    ?GetQuickIdentity@@YAJPEB_WPEAPEA_W@Z; GetQuickIdentity(wchar_t const *,wchar_t * *)
0x1400137ac  test    eax, eax
0x1400137ae  jns     short loc_1400137C9
0x1400137b0  lea     r9, aUnableToProces; "Unable to process package string"
0x1400137b7  mov     r8d, 1
0x1400137bd  mov     edx, eax
0x1400137bf  mov     ecx, 4000000h
0x1400137c4  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400137c9  lea     rdx, [rsp+68h+ppMalloc]; ppMalloc
0x1400137ce  mov     ecx, 1; dwMemContext
0x1400137d3  call    cs:__imp_CoGetMalloc
0x1400137d9  mov     ebx, eax
0x1400137db  test    eax, eax
0x1400137dd  jns     short loc_140013802
0x1400137df  lea     r9, aFailedToGetTas; "Failed to get task allocator for Truste"...
0x1400137e6  mov     edx, eax
0x1400137e8  mov     r8d, 1
0x1400137ee  mov     ecx, 4000000h
0x1400137f3  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x1400137f8  mov     rdi, [rsp+68h+var_38]
0x1400137fd  jmp     loc_14001388F
0x140013802  mov     ecx, 338h; Size
0x140013807  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001380c  test    rax, rax
0x14001380f  jz      short loc_140013877
0x140013811  mov     rdx, [rsp+68h+ppMalloc]; struct IMalloc *
0x140013816  mov     rcx, rax; this
0x140013819  call    ??0CCbsIdentity@@QEAA@PEAUIMalloc@@_W@Z; CCbsIdentity::CCbsIdentity(IMalloc *,wchar_t)
0x14001381e  mov     r14, rax
0x140013821  test    rax, rax
0x140013824  jz      short loc_140013877
0x140013826  mov     rcx, [rax]
0x140013829  mov     rdi, [rsp+68h+var_38]
0x14001382e  mov     rdx, rdi
0x140013831  mov     rax, [rcx+38h]
0x140013835  mov     rcx, r14
0x140013838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001383d  mov     ebx, eax
0x14001383f  test    eax, eax
0x140013841  jns     short loc_140013872
0x140013843  lea     r9, aFailedToLoadFr; "Failed to load from string: %S"
0x14001384a  mov     [rsp+68h+var_48], rdi
0x14001384f  mov     r8d, 1
0x140013855  mov     edx, eax
0x140013857  mov     ecx, 4000000h
0x14001385c  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140013861  mov     rax, [r14]
0x140013864  mov     rcx, r14
0x140013867  mov     rax, [rax+10h]
0x14001386b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013870  jmp     short loc_14001388F
0x140013872  mov     [r15], r14
0x140013875  jmp     short loc_14001388F
0x140013877  mov     ebx, 8007000Eh
0x14001387c  lea     r9, aFailedToAlloca_8; "Failed to allocate identity."
0x140013883  mov     edx, ebx
0x140013885  jmp     loc_1400137E8
0x14001388a  mov     ebx, 80004001h
0x14001388f  mov     rcx, [rsp+68h+ppMalloc]
0x140013894  test    rcx, rcx
0x140013897  jz      short loc_1400138A5
0x140013899  mov     rax, [rcx]
0x14001389c  mov     rax, [rax+10h]
0x1400138a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400138a5  test    rdi, rdi
0x1400138a8  jz      short loc_1400138B3
0x1400138aa  lea     rcx, [rdi-8]; void *
0x1400138ae  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400138b3  mov     eax, ebx
0x1400138b5  mov     rcx, [rsp+68h+var_28]
0x1400138ba  xor     rcx, rsp; StackCookie
0x1400138bd  call    __security_check_cookie
0x1400138c2  mov     rbx, [rsp+68h+arg_10]
0x1400138ca  add     rsp, 50h
0x1400138ce  pop     r15
0x1400138d0  pop     r14
0x1400138d2  pop     rdi
0x1400138d3  retn
```
