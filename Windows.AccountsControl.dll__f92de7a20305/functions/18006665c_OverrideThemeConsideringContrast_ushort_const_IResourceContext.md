# OverrideThemeConsideringContrast(ushort const *,IResourceContext *)

- ea: `0x18006665c`
- end: `0x1800667d8`
- name: `?OverrideThemeConsideringContrast@@YAXPEBGPEAUIResourceContext@@@Z`
- size: `380`
- prototype: `void __fastcall(const unsigned __int16 *, struct IResourceContext *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800661ec`

## callees

- `0x180018f90`
- `0x18003319c`
- `0x1800658a8`
- `0x18006665c`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006671f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180066777`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18006671f`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180066777`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall OverrideThemeConsideringContrast(const unsigned __int16 *a1, struct IResourceContext *a2)
{
  int v3; // eax
  const WCHAR *v4; // r14
  __int64 v5; // rdi
  LPCWCH v6; // rbx
  int v7; // eax
  __int64 v8; // rdx
  const WCHAR *v9; // rcx
  const WCHAR *v10; // rdx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-30h]
  LPCWCH lpString1; // [rsp+30h] [rbp-20h] BYREF
  int cchCount1[2]; // [rsp+38h] [rbp-18h]
  __int64 v14; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]
  int v16; // [rsp+88h] [rbp+38h] BYREF

  lpString1 = 0;
  *(_QWORD *)cchCount1 = 0;
  v14 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(&lpString1, a1, -1);
  v16 = 0;
  v3 = (*(__int64 (__fastcall **)(struct IResourceContext *, int *))(*(_QWORD *)a2 + 64LL))(a2, &v16);
  if ( v3 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x5E,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\resourcehelperlib\\mrticonhelpers.cpp",
      (const char *)(unsigned int)v3,
      bIgnoreCase);
  v4 = &word_18008CC90;
  v5 = *(_QWORD *)cchCount1;
  v6 = lpString1;
  v7 = v16;
  if ( v16 == 3 )
  {
    LODWORD(v8) = cchCount1[0];
    if ( *(_QWORD *)cchCount1 == -1 )
    {
      if ( lpString1 )
      {
        v8 = -1;
        do
          ++v8;
        while ( lpString1[v8] );
      }
      else
      {
        LODWORD(v8) = 0;
      }
    }
    v9 = &word_18008CC90;
    if ( lpString1 )
      v9 = lpString1;
    if ( CompareStringOrdinal(v9, v8, L"Dark", -1, 1) == 2 )
    {
      v10 = L"Light";
LABEL_26:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(
        &lpString1,
        v10,
        -1);
      v6 = lpString1;
      goto LABEL_27;
    }
    v7 = v16;
  }
  if ( (unsigned int)(v7 - 1) <= 1 )
  {
    if ( v5 == -1 )
    {
      if ( v6 )
      {
        v5 = -1;
        do
          ++v5;
        while ( v6[v5] );
      }
      else
      {
        LODWORD(v5) = 0;
      }
    }
    if ( v6 )
      v4 = v6;
    if ( CompareStringOrdinal(v4, v5, L"Light", -1, 1) == 2 )
    {
      v10 = L"Dark";
      goto LABEL_26;
    }
  }
LABEL_27:
  (*(void (__fastcall **)(struct IResourceContext *, const wchar_t *, LPCWCH))(*(_QWORD *)a2 + 144LL))(a2, L"Theme", v6);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpString1);
}

```

## disassembly

```asm
0x18006665c  mov     [rsp-28h+arg_0], rbx
0x180066661  mov     [rsp-28h+arg_10], rsi
0x180066666  push    rbp
0x180066667  push    rdi
0x180066668  push    r12
0x18006666a  push    r14
0x18006666c  push    r15
0x18006666e  mov     rbp, rsp
0x180066671  sub     rsp, 50h
0x180066675  mov     rsi, rdx
0x180066678  xor     r15d, r15d
0x18006667b  mov     [rbp+lpString1], r15
0x18006667f  mov     qword ptr [rbp+cchCount1], r15
0x180066683  mov     [rbp+var_10], r15
0x180066687  or      r12, 0FFFFFFFFFFFFFFFFh
0x18006668b  mov     r8, r12
0x18006668e  mov     rdx, rcx
0x180066691  lea     rcx, [rbp+lpString1]
0x180066695  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18006669a  mov     [rbp+arg_8], r15d
0x18006669e  mov     rax, [rsi]
0x1800666a1  lea     rdx, [rbp+arg_8]
0x1800666a5  mov     rcx, rsi
0x1800666a8  mov     rax, [rax+40h]
0x1800666ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800666b1  mov     rcx, [rbp+28h]; this
0x1800666b5  test    eax, eax
0x1800666b7  jns     short loc_1800666CD
0x1800666b9  mov     r9d, eax; char *
0x1800666bc  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\accountscontrol\\api"...
0x1800666c3  lea     edx, [r15+5Eh]; void *
0x1800666c7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800666cd  lea     r14, word_18008CC90
0x1800666d4  mov     rdi, qword ptr [rbp+cchCount1]
0x1800666d8  mov     rbx, [rbp+lpString1]
0x1800666dc  mov     eax, [rbp+arg_8]
0x1800666df  cmp     eax, 3
0x1800666e2  jnz     short loc_180066736
0x1800666e4  mov     rdx, rdi
0x1800666e7  cmp     rdi, r12
0x1800666ea  jnz     short loc_180066703
0x1800666ec  test    rbx, rbx
0x1800666ef  jz      short loc_180066700
0x1800666f1  mov     rdx, r12
0x1800666f4  inc     rdx
0x1800666f7  cmp     [rbx+rdx*2], r15w
0x1800666fc  jnz     short loc_1800666F4
0x1800666fe  jmp     short loc_180066703
0x180066700  mov     rdx, r15; cchCount1
0x180066703  mov     rcx, r14
0x180066706  test    rbx, rbx
0x180066709  cmovnz  rcx, rbx; lpString1
0x18006670d  mov     [rsp+50h+bIgnoreCase], 1; bIgnoreCase
0x180066715  mov     r9d, r12d; cchCount2
0x180066718  lea     r8, aDark; "Dark"
0x18006671f  call    cs:__imp_CompareStringOrdinal
0x180066725  cmp     eax, 2
0x180066728  jnz     short loc_180066733
0x18006672a  lea     rdx, aLight; "Light"
0x180066731  jmp     short loc_180066789
0x180066733  mov     eax, [rbp+arg_8]
0x180066736  dec     eax
0x180066738  cmp     eax, 1
0x18006673b  ja      short loc_180066799
0x18006673d  cmp     rdi, r12
0x180066740  jnz     short loc_180066759
0x180066742  test    rbx, rbx
0x180066745  jz      short loc_180066756
0x180066747  mov     rdi, r12
0x18006674a  inc     rdi
0x18006674d  cmp     [rbx+rdi*2], r15w
0x180066752  jnz     short loc_18006674A
0x180066754  jmp     short loc_180066759
0x180066756  mov     rdi, r15
0x180066759  test    rbx, rbx
0x18006675c  cmovnz  r14, rbx
0x180066760  mov     edx, edi; cchCount1
0x180066762  mov     [rsp+50h+bIgnoreCase], 1; bIgnoreCase
0x18006676a  mov     r9d, r12d; cchCount2
0x18006676d  lea     r8, aLight; "Light"
0x180066774  mov     rcx, r14; lpString1
0x180066777  call    cs:__imp_CompareStringOrdinal
0x18006677d  cmp     eax, 2
0x180066780  jnz     short loc_180066799
0x180066782  lea     rdx, aDark; "Dark"
0x180066789  mov     r8, r12
0x18006678c  lea     rcx, [rbp+lpString1]
0x180066790  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x180066795  mov     rbx, [rbp+lpString1]
0x180066799  mov     rax, [rsi]
0x18006679c  mov     r8, rbx
0x18006679f  lea     rdx, aTheme; "Theme"
0x1800667a6  mov     rcx, rsi
0x1800667a9  mov     rax, [rax+90h]
0x1800667b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800667b5  nop
0x1800667b6  lea     rcx, [rbp+lpString1]
0x1800667ba  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800667bf  lea     r11, [rsp+50h+var_s0]
0x1800667c4  mov     rbx, [r11+30h]
0x1800667c8  mov     rsi, [r11+40h]
0x1800667cc  mov     rsp, r11
0x1800667cf  pop     r15
0x1800667d1  pop     r14
0x1800667d3  pop     r12
0x1800667d5  pop     rdi
0x1800667d6  pop     rbp
0x1800667d7  retn
```
