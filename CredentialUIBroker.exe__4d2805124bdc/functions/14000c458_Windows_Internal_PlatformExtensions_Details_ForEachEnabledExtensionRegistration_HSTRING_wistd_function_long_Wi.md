# Windows::Internal::PlatformExtensions::Details::ForEachEnabledExtensionRegistration(HSTRING__ *,wistd::function<long (Windows::Internal::PlatformExtensions::Details::ExtensionRegistration const *,bool,bool *)> const &)

- ea: `0x14000c458`
- end: `0x14000c5ef`
- name: `?ForEachEnabledExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@AEBV?$function@$$A6AJPEBVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@_NPEA_N@Z@wistd@@@Z`
- size: `407`
- prototype: `__int64 __fastcall(HSTRING, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x140017060`

## callees

- `0x14000c458`
- `0x14000d40c`
- `0x1400136fc`
- `0x14001af00`
- `0x14001f010`

## string_xrefs

- `0x14000c4bc`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x14000c5c4`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::PlatformExtensions::Details::ForEachEnabledExtensionRegistration(
        HSTRING a1,
        __int64 a2)
{
  int ExtensionRegistrationsForExtensionPoint; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  __int64 v6; // rsi
  unsigned __int64 i; // rbx
  int v8; // edi
  __int64 v9; // rcx
  __int64 v11; // rdx
  int v12; // [rsp+20h] [rbp-40h]
  __int64 v13; // [rsp+30h] [rbp-30h] BYREF
  __int64 v14; // [rsp+38h] [rbp-28h] BYREF
  unsigned __int64 v15; // [rsp+40h] [rbp-20h] BYREF
  char *v16; // [rsp+48h] [rbp-18h] BYREF
  __int64 v17; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  char v19; // [rsp+90h] [rbp+30h] BYREF
  char v20; // [rsp+98h] [rbp+38h] BYREF

  v14 = 0;
  ExtensionRegistrationsForExtensionPoint = Windows::Internal::PlatformExtensions::Details::GetExtensionRegistrationsForExtensionPoint(a1);
  v4 = ExtensionRegistrationsForExtensionPoint;
  if ( ExtensionRegistrationsForExtensionPoint < 0 )
  {
    v5 = 352;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
      (const char *)(unsigned int)ExtensionRegistrationsForExtensionPoint,
      v12);
    goto LABEL_20;
  }
  v6 = v14;
  v15 = 0;
  ExtensionRegistrationsForExtensionPoint = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v14 + 8LL))(
                                              v14,
                                              &v15);
  v4 = ExtensionRegistrationsForExtensionPoint;
  if ( ExtensionRegistrationsForExtensionPoint < 0 )
  {
    v5 = 355;
    goto LABEL_5;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= v15 )
      goto LABEL_15;
    v13 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, __int64 *))(*(_QWORD *)v6 + 16LL))(v6, i, &v13);
    if ( v8 < 0 )
      break;
    if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13) )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 40LL))(v13);
      v9 = *(_QWORD *)(a2 + 112);
      v16 = &v19;
      v17 = v13;
      v19 = 0;
      v20 = 0;
      if ( !v9 )
        __fastfail(7u);
      v8 = (*(__int64 (__fastcall **)(__int64, __int64 *, char *, char **))(*(_QWORD *)v9 + 32LL))(v9, &v17, &v20, &v16);
      if ( v8 < 0 )
      {
        v11 = 389;
        goto LABEL_19;
      }
      if ( !v19 )
      {
        wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(
          &v13,
          0);
LABEL_15:
        wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(
          &v14,
          0);
        return 0;
      }
    }
    wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(
      &v13,
      0);
  }
  v11 = 365;
LABEL_19:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
    (const char *)(unsigned int)v8,
    v12);
  wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(
    &v13,
    0);
  v4 = v8;
LABEL_20:
  wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(
    &v14,
    0);
  return v4;
}

```

## disassembly

```asm
0x14000c458  mov     [rsp-18h+arg_0], rbx
0x14000c45d  mov     [rsp-18h+arg_8], rsi
0x14000c462  push    rbp
0x14000c463  push    rdi
0x14000c464  push    r14
0x14000c466  mov     rbp, rsp
0x14000c469  sub     rsp, 60h
0x14000c46d  mov     r14, rdx
0x14000c470  mov     [rbp+var_28], 0
0x14000c478  lea     rdx, [rbp+var_28]
0x14000c47c  call    ?GetExtensionRegistrationsForExtensionPoint@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@PEAV?$unique_ptr@VExtensionRegistrationCollection@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistrationCollection@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@@Z; Windows::Internal::PlatformExtensions::Details::GetExtensionRegistrationsForExtensionPoint(HSTRING__ *,wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollection,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollection>> *)
0x14000c481  mov     ebx, eax
0x14000c483  test    eax, eax
0x14000c485  jns     short loc_14000C48E
0x14000c487  mov     edx, 160h
0x14000c48c  jmp     short loc_14000C4B8
0x14000c48e  mov     rsi, [rbp+var_28]
0x14000c492  lea     rdx, [rbp+var_20]
0x14000c496  mov     [rbp+var_20], 0
0x14000c49e  mov     rcx, rsi
0x14000c4a1  mov     rax, [rsi]
0x14000c4a4  mov     rax, [rax+8]
0x14000c4a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c4ad  mov     ebx, eax
0x14000c4af  test    eax, eax
0x14000c4b1  jns     short loc_14000C4D0
0x14000c4b3  mov     edx, 163h; void *
0x14000c4b8  mov     rcx, [rbp+18h]; this
0x14000c4bc  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x14000c4c3  mov     r9d, eax; char *
0x14000c4c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c4cb  jmp     loc_14000C5E0
0x14000c4d0  xor     ebx, ebx
0x14000c4d2  cmp     rbx, [rbp+var_20]
0x14000c4d6  jnb     loc_14000C58B
0x14000c4dc  mov     [rbp+var_30], 0
0x14000c4e4  lea     r8, [rbp+var_30]
0x14000c4e8  mov     rax, [rsi]
0x14000c4eb  mov     rdx, rbx
0x14000c4ee  mov     rcx, rsi
0x14000c4f1  mov     rax, [rax+10h]
0x14000c4f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c4fa  mov     edi, eax
0x14000c4fc  test    eax, eax
0x14000c4fe  js      loc_14000C5BB
0x14000c504  mov     rcx, [rbp+var_30]
0x14000c508  mov     rax, [rcx]
0x14000c50b  mov     rax, [rax+8]
0x14000c50f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c514  test    al, al
0x14000c516  jnz     short loc_14000C56D
0x14000c518  mov     rcx, [rbp+var_30]
0x14000c51c  mov     rax, [rcx]
0x14000c51f  mov     rax, [rax+28h]
0x14000c523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c528  mov     rcx, [r14+70h]
0x14000c52c  lea     rax, [rbp+arg_10]
0x14000c530  mov     [rbp+var_18], rax
0x14000c534  mov     rax, [rbp+var_30]
0x14000c538  mov     [rbp+var_10], rax
0x14000c53c  mov     [rbp+arg_10], 0
0x14000c540  mov     [rbp+arg_18], 0
0x14000c544  test    rcx, rcx
0x14000c547  jz      short loc_14000C5B4
0x14000c549  mov     rax, [rcx]
0x14000c54c  lea     r9, [rbp+var_18]
0x14000c550  lea     r8, [rbp+arg_18]
0x14000c554  lea     rdx, [rbp+var_10]
0x14000c558  mov     rax, [rax+20h]
0x14000c55c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c561  mov     edi, eax
0x14000c563  test    eax, eax
0x14000c565  js      short loc_14000C5AD
0x14000c567  cmp     [rbp+arg_10], 0
0x14000c56b  jz      short loc_14000C580
0x14000c56d  xor     edx, edx
0x14000c56f  lea     rcx, [rbp+var_30]
0x14000c573  call    ?reset@?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(Windows::Internal::PlatformExtensions::Details::ExtensionRegistration *)
0x14000c578  inc     rbx
0x14000c57b  jmp     loc_14000C4D2
0x14000c580  xor     edx, edx
0x14000c582  lea     rcx, [rbp+var_30]
0x14000c586  call    ?reset@?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(Windows::Internal::PlatformExtensions::Details::ExtensionRegistration *)
0x14000c58b  xor     edx, edx
0x14000c58d  lea     rcx, [rbp+var_28]
0x14000c591  call    ?reset@?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(Windows::Internal::PlatformExtensions::Details::ExtensionRegistration *)
0x14000c596  xor     eax, eax
0x14000c598  lea     r11, [rsp+60h+var_s0]
0x14000c59d  mov     rbx, [r11+20h]
0x14000c5a1  mov     rsi, [r11+28h]
0x14000c5a5  mov     rsp, r11
0x14000c5a8  pop     r14
0x14000c5aa  pop     rdi
0x14000c5ab  pop     rbp
0x14000c5ac  retn
0x14000c5ad  mov     edx, 185h
0x14000c5b2  jmp     short loc_14000C5C0
0x14000c5b4  mov     ecx, 7
0x14000c5b9  int     29h; Win8: RtlFailFast(ecx)
0x14000c5bb  mov     edx, 16Dh; void *
0x14000c5c0  mov     rcx, [rbp+18h]; this
0x14000c5c4  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x14000c5cb  mov     r9d, edi; char *
0x14000c5ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000c5d3  xor     edx, edx
0x14000c5d5  lea     rcx, [rbp+var_30]
0x14000c5d9  call    ?reset@?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(Windows::Internal::PlatformExtensions::Details::ExtensionRegistration *)
0x14000c5de  mov     ebx, edi
0x14000c5e0  xor     edx, edx
0x14000c5e2  lea     rcx, [rbp+var_28]
0x14000c5e6  call    ?reset@?$unique_ptr@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@U?$default_delete@VExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@wistd@@@wistd@@QEAAXPEAVExtensionRegistration@Details@PlatformExtensions@Internal@Windows@@@Z; wistd::unique_ptr<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration,wistd::default_delete<Windows::Internal::PlatformExtensions::Details::ExtensionRegistration>>::reset(Windows::Internal::PlatformExtensions::Details::ExtensionRegistration *)
0x14000c5eb  mov     eax, ebx
0x14000c5ed  jmp     short loc_14000C598
```
