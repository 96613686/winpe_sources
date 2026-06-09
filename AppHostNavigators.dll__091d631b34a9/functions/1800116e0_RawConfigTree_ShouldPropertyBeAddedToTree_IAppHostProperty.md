# RawConfigTree::ShouldPropertyBeAddedToTree(IAppHostProperty *)

- ea: `0x1800116e0`
- end: `0x1800118ff`
- name: `?ShouldPropertyBeAddedToTree@RawConfigTree@@UEAA_NPEAUIAppHostProperty@@@Z`
- size: `543`
- prototype: `bool __fastcall(RawConfigTree *__hidden this, struct IAppHostProperty *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800018a0`
- `0x180001910`
- `0x180001a30`
- `0x1800105a0`
- `0x1800116e0`
- `0x180012f3c`
- `0x180014010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x1800117f9`
- `OLEAUT32!__imp_VariantInit` at `0x180011804`
- `OLEAUT32!__imp_VariantInit` at `0x18001180f`
- `OLEAUT32!__imp_VariantInit` at `0x1800117f9`
- `OLEAUT32!__imp_VariantInit` at `0x180011804`
- `OLEAUT32!__imp_VariantInit` at `0x18001180f`
- `OLEAUT32!__imp_VariantClear` at `0x180011894`
- `OLEAUT32!__imp_VariantClear` at `0x18001189f`
- `OLEAUT32!__imp_VariantClear` at `0x1800118aa`
- `OLEAUT32!__imp_VariantClear` at `0x1800118cb`
- `OLEAUT32!__imp_VariantClear` at `0x1800118d6`
- `OLEAUT32!__imp_VariantClear` at `0x1800118e1`
- `OLEAUT32!__imp_VariantClear` at `0x180011894`
- `OLEAUT32!__imp_VariantClear` at `0x18001189f`
- `OLEAUT32!__imp_VariantClear` at `0x1800118aa`
- `OLEAUT32!__imp_VariantClear` at `0x1800118cb`
- `OLEAUT32!__imp_VariantClear` at `0x1800118d6`
- `OLEAUT32!__imp_VariantClear` at `0x1800118e1`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall RawConfigTree::ShouldPropertyBeAddedToTree(RawConfigTree *this, struct IAppHostProperty *a2)
{
  __int64 v3; // rbx
  int v4; // eax
  VARIANTARG v6; // [rsp+20h] [rbp-50h] BYREF
  VARIANTARG v7; // [rsp+38h] [rbp-38h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-20h] BYREF
  int pExceptionObject; // [rsp+98h] [rbp+28h] BYREF

  v3 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  if ( dword_18001E6BC > *(_DWORD *)(v3 + 4) )
  {
    Init_thread_header(&dword_18001E6BC);
    if ( dword_18001E6BC == -1 )
    {
      atexit(RawConfigTree::ShouldPropertyBeAddedToTree_::_2_::_dynamic_atexit_destructor_for__bstrIsDefaultValue__);
      Init_thread_footer(&dword_18001E6BC);
    }
  }
  Helpers::EnsureInitializedSerialized((struct ScopedBSTR *)&qword_18001E6A8, (OLECHAR *)L"isDefaultValue");
  if ( dword_18001E6B8 > *(_DWORD *)(v3 + 4) )
  {
    Init_thread_header(&dword_18001E6B8);
    if ( dword_18001E6B8 == -1 )
    {
      atexit(RawConfigTree::ShouldPropertyBeAddedToTree_::_2_::_dynamic_atexit_destructor_for__bstrIsPresent__);
      Init_thread_footer(&dword_18001E6B8);
    }
  }
  Helpers::EnsureInitializedSerialized((struct ScopedBSTR *)&qword_18001E6B0, (OLECHAR *)L"isPresent");
  if ( dword_18001E6A0 > *(_DWORD *)(v3 + 4) )
  {
    Init_thread_header(&dword_18001E6A0);
    if ( dword_18001E6A0 == -1 )
    {
      atexit(RawConfigTree::ShouldPropertyBeAddedToTree_::_2_::_dynamic_atexit_destructor_for__bstrIsInheritedFromDefault__);
      Init_thread_footer(&dword_18001E6A0);
    }
  }
  Helpers::EnsureInitializedSerialized((struct ScopedBSTR *)&qword_18001E6C0, (OLECHAR *)L"isInheritedFromDefault");
  VariantInit(&pvarg);
  VariantInit(&v7);
  VariantInit(&v6);
  v4 = ((__int64 (__fastcall *)(struct IAppHostProperty *, _QWORD, VARIANTARG *))a2->lpVtbl->GetMetadata)(
         a2,
         qword_18001E6A8,
         &pvarg);
  if ( v4 < 0 )
    goto LABEL_18;
  if ( pvarg.iVal == -1 )
    goto LABEL_17;
  v4 = ((__int64 (__fastcall *)(struct IAppHostProperty *, _QWORD, VARIANTARG *))a2->lpVtbl->GetMetadata)(
         a2,
         qword_18001E6B0,
         &v7);
  if ( v4 < 0 )
    goto LABEL_18;
  if ( !v7.iVal )
    goto LABEL_17;
  v4 = ((__int64 (__fastcall *)(struct IAppHostProperty *, _QWORD, VARIANTARG *))a2->lpVtbl->GetMetadata)(
         a2,
         qword_18001E6C0,
         &v6);
  if ( v4 < 0 )
  {
LABEL_18:
    pExceptionObject = v4;
    throw (long *)&pExceptionObject;
  }
  if ( v6.iVal != -1 )
  {
    VariantClear(&v6);
    VariantClear(&v7);
    VariantClear(&pvarg);
    return 1;
  }
LABEL_17:
  VariantClear(&v6);
  VariantClear(&v7);
  VariantClear(&pvarg);
  return 0;
}

```

## disassembly

```asm
0x1800116e0  mov     [rsp-18h+arg_0], rbx
0x1800116e5  mov     [rsp-18h+arg_10], rsi
0x1800116ea  push    rbp
0x1800116eb  push    rdi
0x1800116ec  push    r14
0x1800116ee  mov     rbp, rsp
0x1800116f1  sub     rsp, 70h
0x1800116f5  mov     rdi, rdx
0x1800116f8  mov     ecx, cs:_tls_index
0x1800116fe  mov     rax, gs:58h
0x180011707  mov     r14d, 4
0x18001170d  mov     rbx, [rax+rcx*8]
0x180011711  or      esi, 0FFFFFFFFh
0x180011714  mov     eax, [rbx+r14]
0x180011718  cmp     cs:dword_18001E6BC, eax
0x18001171e  jle     short loc_18001174C
0x180011720  lea     rcx, dword_18001E6BC
0x180011727  call    _Init_thread_header
0x18001172c  cmp     cs:dword_18001E6BC, esi
0x180011732  jnz     short loc_18001174C
0x180011734  lea     rcx, _RawConfigTree__ShouldPropertyBeAddedToTree____2____dynamic_atexit_destructor_for__bstrIsDefaultValue__; void (__cdecl *)()
0x18001173b  call    atexit
0x180011740  lea     rcx, dword_18001E6BC
0x180011747  call    _Init_thread_footer
0x18001174c  lea     rdx, aIsdefaultvalue; "isDefaultValue"
0x180011753  lea     rcx, qword_18001E6A8; this
0x18001175a  call    ?EnsureInitializedSerialized@Helpers@@SAXAEAVScopedBSTR@@PEBG@Z; Helpers::EnsureInitializedSerialized(ScopedBSTR &,ushort const *)
0x18001175f  mov     eax, [rbx+r14]
0x180011763  cmp     cs:dword_18001E6B8, eax
0x180011769  jle     short loc_180011797
0x18001176b  lea     rcx, dword_18001E6B8
0x180011772  call    _Init_thread_header
0x180011777  cmp     cs:dword_18001E6B8, esi
0x18001177d  jnz     short loc_180011797
0x18001177f  lea     rcx, _RawConfigTree__ShouldPropertyBeAddedToTree____2____dynamic_atexit_destructor_for__bstrIsPresent__; void (__cdecl *)()
0x180011786  call    atexit
0x18001178b  lea     rcx, dword_18001E6B8
0x180011792  call    _Init_thread_footer
0x180011797  lea     rdx, aIspresent; "isPresent"
0x18001179e  lea     rcx, qword_18001E6B0; this
0x1800117a5  call    ?EnsureInitializedSerialized@Helpers@@SAXAEAVScopedBSTR@@PEBG@Z; Helpers::EnsureInitializedSerialized(ScopedBSTR &,ushort const *)
0x1800117aa  mov     eax, [rbx+r14]
0x1800117ae  cmp     cs:dword_18001E6A0, eax
0x1800117b4  jle     short loc_1800117E2
0x1800117b6  lea     rcx, dword_18001E6A0
0x1800117bd  call    _Init_thread_header
0x1800117c2  cmp     cs:dword_18001E6A0, esi
0x1800117c8  jnz     short loc_1800117E2
0x1800117ca  lea     rcx, _RawConfigTree__ShouldPropertyBeAddedToTree____2____dynamic_atexit_destructor_for__bstrIsInheritedFromDefault__; void (__cdecl *)()
0x1800117d1  call    atexit
0x1800117d6  lea     rcx, dword_18001E6A0
0x1800117dd  call    _Init_thread_footer
0x1800117e2  lea     rdx, aIsinheritedfro; "isInheritedFromDefault"
0x1800117e9  lea     rcx, qword_18001E6C0; this
0x1800117f0  call    ?EnsureInitializedSerialized@Helpers@@SAXAEAVScopedBSTR@@PEBG@Z; Helpers::EnsureInitializedSerialized(ScopedBSTR &,ushort const *)
0x1800117f5  lea     rcx, [rbp+pvarg]; pvarg
0x1800117f9  call    cs:__imp_VariantInit
0x1800117ff  nop
0x180011800  lea     rcx, [rbp+var_38]; pvarg
0x180011804  call    cs:__imp_VariantInit
0x18001180a  nop
0x18001180b  lea     rcx, [rbp+var_50]; pvarg
0x18001180f  call    cs:__imp_VariantInit
0x180011815  nop
0x180011816  mov     rax, [rdi]
0x180011819  lea     r8, [rbp+pvarg]
0x18001181d  mov     rdx, cs:qword_18001E6A8
0x180011824  mov     rcx, rdi
0x180011827  mov     rax, [rax+48h]
0x18001182b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011830  xor     ebx, ebx
0x180011832  test    eax, eax
0x180011834  js      loc_1800118EB
0x18001183a  cmp     word ptr [rbp+pvarg+8], si
0x18001183e  jz      loc_1800118C7
0x180011844  mov     rax, [rdi]
0x180011847  lea     r8, [rbp+var_38]
0x18001184b  mov     rdx, cs:qword_18001E6B0
0x180011852  mov     rcx, rdi
0x180011855  mov     rax, [rax+48h]
0x180011859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001185e  test    eax, eax
0x180011860  js      loc_1800118EB
0x180011866  cmp     word ptr [rbp+var_38+8], bx
0x18001186a  jz      short loc_1800118C7
0x18001186c  mov     rax, [rdi]
0x18001186f  lea     r8, [rbp+var_50]
0x180011873  mov     rdx, cs:qword_18001E6C0
0x18001187a  mov     rcx, rdi
0x18001187d  mov     rax, [rax+48h]
0x180011881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011886  test    eax, eax
0x180011888  js      short loc_1800118EB
0x18001188a  cmp     word ptr [rbp+var_50+8], si
0x18001188e  jz      short loc_1800118C7
0x180011890  lea     rcx, [rbp+var_50]; pvarg
0x180011894  call    cs:__imp_VariantClear
0x18001189a  nop
0x18001189b  lea     rcx, [rbp+var_38]; pvarg
0x18001189f  call    cs:__imp_VariantClear
0x1800118a5  nop
0x1800118a6  lea     rcx, [rbp+pvarg]; pvarg
0x1800118aa  call    cs:__imp_VariantClear
0x1800118b0  mov     al, 1
0x1800118b2  lea     r11, [rsp+70h+var_s0]
0x1800118b7  mov     rbx, [r11+20h]
0x1800118bb  mov     rsi, [r11+30h]
0x1800118bf  mov     rsp, r11
0x1800118c2  pop     r14
0x1800118c4  pop     rdi
0x1800118c5  pop     rbp
0x1800118c6  retn
0x1800118c7  lea     rcx, [rbp+var_50]; pvarg
0x1800118cb  call    cs:__imp_VariantClear
0x1800118d1  nop
0x1800118d2  lea     rcx, [rbp+var_38]; pvarg
0x1800118d6  call    cs:__imp_VariantClear
0x1800118dc  nop
0x1800118dd  lea     rcx, [rbp+pvarg]; pvarg
0x1800118e1  call    cs:__imp_VariantClear
0x1800118e7  xor     al, al
0x1800118e9  jmp     short loc_1800118B2
0x1800118eb  mov     [rbp+pExceptionObject], eax
0x1800118ee  lea     rdx, _TI1J; pThrowInfo
0x1800118f5  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1800118f9  call    _CxxThrowException_0
```
