# OneSettings::ParseJsonBlob(char const *)

- ea: `0x140018680`
- end: `0x14001890d`
- name: `?ParseJsonBlob@OneSettings@@AEAAJPEBD@Z`
- size: `653`
- prototype: `__int64 __fastcall(OneSettings *__hidden this, const char *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1400168b4`

## callees

- `0x140002600`
- `0x1400028d8`
- `0x140003540`
- `0x140007870`
- `0x140008e98`
- `0x140018680`
- `0x14001d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x14001871f`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x14001871f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001874e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400187d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001883f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001874e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1400187d3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x14001883f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140018788`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140018788`

## string_xrefs

- `0x140018747`: `Windows.Data.Json.JsonValue`

## pseudocode

```c
__int64 __fastcall OneSettings::ParseJsonBlob(OneSettings *this, const char *a2)
{
  unsigned __int64 v4; // rdi
  __int64 v5; // rax
  unsigned __int64 v6; // r14
  unsigned __int64 v7; // rax
  unsigned __int16 *v8; // rax
  WCHAR *v9; // rsi
  int ActivationFactory; // ebx
  int v11; // edx
  unsigned int v12; // r8d
  HRESULT v13; // eax
  int v14; // edx
  unsigned int v15; // r8d
  _QWORD *v16; // rbx
  __int64 v17; // r14
  HRESULT v18; // eax
  int v19; // edx
  unsigned int v20; // r8d
  _QWORD *v21; // rbx
  __int64 v22; // rdi
  __int64 v23; // r14
  HRESULT v24; // eax
  int v25; // edx
  unsigned int v26; // r8d
  _QWORD *v27; // rcx
  __int64 v28; // rcx
  _QWORD *v29; // rcx
  _QWORD *v31; // [rsp+20h] [rbp-40h] BYREF
  _QWORD *v32; // [rsp+28h] [rbp-38h] BYREF
  __int64 v33; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-28h] BYREF
  HSTRING string; // [rsp+50h] [rbp-10h] BYREF

  v4 = -1;
  v5 = -1;
  do
    ++v5;
  while ( a2[v5] );
  v6 = (unsigned int)(v5 + 1);
  v7 = 2 * v6;
  if ( !is_mul_ok(v6, 2u) )
    v7 = -1;
  v8 = (unsigned __int16 *)operator new[](v7, (const struct std::nothrow_t *)std::nothrow);
  v9 = v8;
  if ( v8 )
  {
    if ( *((_QWORD *)this + 26) )
      ActivationFactory = StringCchPrintfW(v8, v6, L"%hs", a2);
    else
      ActivationFactory = -2147418113;
  }
  else
  {
    ActivationFactory = -2147024882;
  }
  if ( wcsstr(v9, L"\"settings\":") )
  {
    v31 = 0;
    if ( ActivationFactory >= 0 )
    {
      string = 0;
      v13 = WindowsCreateStringReference(L"Windows.Data.Json.JsonValue", 0x1Bu, &hstringHeader, &string);
      if ( v13 < 0 )
        goto LABEL_33;
      ActivationFactory = RoGetActivationFactory(string, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v31);
    }
    v33 = 0;
    if ( ActivationFactory < 0 )
      goto LABEL_21;
    v16 = v31;
    v17 = *v31;
    string = 0;
    do
      ++v4;
    while ( v9[v4] );
    if ( v4 <= 0xFFFFFFFF )
    {
      if ( (int)v4 + 1 >= (unsigned int)v4 )
      {
        v18 = WindowsCreateStringReference(v9, v4, &hstringHeader, &string);
        if ( v18 < 0 )
        {
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v18, v19, v20);
          goto LABEL_36;
        }
        ActivationFactory = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64 *))(v17 + 48))(v16, string, &v33);
LABEL_21:
        v32 = 0;
        if ( ActivationFactory < 0 )
          goto LABEL_25;
        ActivationFactory = (*(__int64 (__fastcall **)(__int64, _QWORD **))(*(_QWORD *)v33 + 96LL))(v33, &v32);
        if ( ActivationFactory < 0 )
          goto LABEL_25;
        v21 = v32;
        v22 = *v32;
        v23 = *((_QWORD *)this + 26);
        string = 0;
        v24 = WindowsCreateStringReference(L"settings", 8u, &hstringHeader, &string);
        if ( v24 >= 0 )
        {
          ActivationFactory = (*(__int64 (__fastcall **)(_QWORD *, HSTRING, __int64))(v22 + 64))(v21, string, v23);
LABEL_25:
          v27 = v32;
          if ( v32 )
          {
            v32 = 0;
            (*(void (__fastcall **)(_QWORD *))(*v27 + 16LL))(v27);
          }
          v28 = v33;
          if ( v33 )
          {
            v33 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
          }
          v29 = v31;
          if ( v31 )
          {
            v31 = 0;
            (*(void (__fastcall **)(_QWORD *))(*v29 + 16LL))(v29);
          }
          goto LABEL_31;
        }
LABEL_36:
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v24, v25, v26);
        JUMPOUT(0x14001890CLL);
      }
LABEL_34:
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v11, v12);
      __debugbreak();
    }
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v11, v12);
LABEL_33:
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v13, v14, v15);
    goto LABEL_34;
  }
LABEL_31:
  operator delete(v9);
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x140018680  mov     [rsp-28h+arg_10], rbx
0x140018685  mov     [rsp-28h+arg_18], rsi
0x14001868a  push    rbp
0x14001868b  push    rdi
0x14001868c  push    r12
0x14001868e  push    r14
0x140018690  push    r15
0x140018692  mov     rbp, rsp
0x140018695  sub     rsp, 60h
0x140018699  mov     rax, cs:__security_cookie
0x1400186a0  xor     rax, rsp
0x1400186a3  mov     [rbp+var_8], rax
0x1400186a7  mov     rbx, rdx
0x1400186aa  mov     r15, rcx
0x1400186ad  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400186b1  mov     rax, rdi
0x1400186b4  xor     r12d, r12d
0x1400186b7  inc     rax
0x1400186ba  cmp     [rdx+rax], r12b
0x1400186be  jnz     short loc_1400186B7
0x1400186c0  lea     r14d, [rax+1]
0x1400186c4  mov     eax, 2
0x1400186c9  mul     r14
0x1400186cc  cmovb   rax, rdi
0x1400186d0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400186d7  mov     rcx, rax; unsigned __int64
0x1400186da  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1400186df  mov     rsi, rax
0x1400186e2  test    rax, rax
0x1400186e5  jnz     short loc_1400186EE
0x1400186e7  mov     ebx, 8007000Eh
0x1400186ec  jmp     short loc_140018715
0x1400186ee  cmp     [r15+0D0h], r12
0x1400186f5  jnz     short loc_1400186FE
0x1400186f7  mov     ebx, 8000FFFFh
0x1400186fc  jmp     short loc_140018715
0x1400186fe  mov     r9, rbx
0x140018701  lea     r8, aHs_0; "%hs"
0x140018708  mov     rdx, r14; unsigned __int64
0x14001870b  mov     rcx, rsi; unsigned __int16 *
0x14001870e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140018713  mov     ebx, eax
0x140018715  lea     rdx, aSettings_0; "\"settings\":"
0x14001871c  mov     rcx, rsi; Str
0x14001871f  call    cs:__imp_wcsstr
0x140018725  test    rax, rax
0x140018728  jz      loc_1400188B0
0x14001872e  mov     [rbp+var_40], r12
0x140018732  test    ebx, ebx
0x140018734  js      short loc_140018790
0x140018736  mov     [rbp+string], r12
0x14001873a  lea     r9, [rbp+string]; string
0x14001873e  lea     r8, [rbp+hstringHeader]; hstringHeader
0x140018742  mov     edx, 1Bh; length
0x140018747  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x14001874e  call    cs:__imp_WindowsCreateStringReference
0x140018754  test    eax, eax
0x140018756  js      loc_1400188EA
0x14001875c  mov     rbx, [rbp+string]
0x140018760  mov     rcx, [rbp+var_40]
0x140018764  test    rcx, rcx
0x140018767  jz      short loc_14001877A
0x140018769  mov     [rbp+var_40], r12
0x14001876d  mov     rax, [rcx]
0x140018770  mov     rax, [rax+10h]
0x140018774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018779  nop
0x14001877a  lea     r8, [rbp+var_40]
0x14001877e  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x140018785  mov     rcx, rbx
0x140018788  call    cs:__imp_RoGetActivationFactory
0x14001878e  mov     ebx, eax
0x140018790  mov     [rbp+var_30], r12
0x140018794  test    ebx, ebx
0x140018796  js      short loc_1400187F7
0x140018798  mov     rbx, [rbp+var_40]
0x14001879c  mov     r14, [rbx]
0x14001879f  mov     [rbp+string], r12
0x1400187a3  inc     rdi
0x1400187a6  cmp     [rsi+rdi*2], r12w
0x1400187ab  jnz     short loc_1400187A3
0x1400187ad  mov     eax, 0FFFFFFFFh
0x1400187b2  cmp     rdi, rax
0x1400187b5  ja      loc_1400188DF
0x1400187bb  lea     eax, [rdi+1]
0x1400187be  cmp     eax, edi
0x1400187c0  jb      loc_1400188F2
0x1400187c6  lea     r9, [rbp+string]; string
0x1400187ca  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1400187ce  mov     edx, edi; length
0x1400187d0  mov     rcx, rsi; sourceString
0x1400187d3  call    cs:__imp_WindowsCreateStringReference
0x1400187d9  test    eax, eax
0x1400187db  js      loc_1400188FD
0x1400187e1  lea     r8, [rbp+var_30]
0x1400187e5  mov     rdx, [rbp+string]
0x1400187e9  mov     rcx, rbx
0x1400187ec  mov     rax, [r14+30h]
0x1400187f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400187f5  mov     ebx, eax
0x1400187f7  mov     [rbp+var_38], r12
0x1400187fb  test    ebx, ebx
0x1400187fd  js      short loc_140018862
0x1400187ff  mov     rcx, [rbp+var_30]
0x140018803  mov     rax, [rcx]
0x140018806  lea     rdx, [rbp+var_38]
0x14001880a  mov     rax, [rax+60h]
0x14001880e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018813  mov     ebx, eax
0x140018815  test    eax, eax
0x140018817  js      short loc_140018862
0x140018819  mov     rbx, [rbp+var_38]
0x14001881d  mov     rdi, [rbx]
0x140018820  mov     r14, [r15+0D0h]
0x140018827  mov     [rbp+string], r12
0x14001882b  lea     r9, [rbp+string]; string
0x14001882f  lea     r8, [rbp+hstringHeader]; hstringHeader
0x140018833  mov     edx, 8; length
0x140018838  lea     rcx, aSettings; "settings"
0x14001883f  call    cs:__imp_WindowsCreateStringReference
0x140018845  test    eax, eax
0x140018847  js      loc_140018905
0x14001884d  mov     r8, r14
0x140018850  mov     rdx, [rbp+string]
0x140018854  mov     rcx, rbx
0x140018857  mov     rax, [rdi+40h]
0x14001885b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018860  mov     ebx, eax
0x140018862  mov     rcx, [rbp+var_38]
0x140018866  test    rcx, rcx
0x140018869  jz      short loc_14001887C
0x14001886b  mov     [rbp+var_38], r12
0x14001886f  mov     rax, [rcx]
0x140018872  mov     rax, [rax+10h]
0x140018876  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001887b  nop
0x14001887c  mov     rcx, [rbp+var_30]
0x140018880  test    rcx, rcx
0x140018883  jz      short loc_140018896
0x140018885  mov     [rbp+var_30], r12
0x140018889  mov     rax, [rcx]
0x14001888c  mov     rax, [rax+10h]
0x140018890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018895  nop
0x140018896  mov     rcx, [rbp+var_40]
0x14001889a  test    rcx, rcx
0x14001889d  jz      short loc_1400188B0
0x14001889f  mov     [rbp+var_40], r12
0x1400188a3  mov     rax, [rcx]
0x1400188a6  mov     rax, [rax+10h]
0x1400188aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400188af  nop
0x1400188b0  mov     rcx, rsi; Block
0x1400188b3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400188b8  mov     eax, ebx
0x1400188ba  mov     rcx, [rbp+var_8]
0x1400188be  xor     rcx, rsp; StackCookie
0x1400188c1  call    __security_check_cookie
0x1400188c6  lea     r11, [rsp+60h+var_s0]
0x1400188cb  mov     rbx, [r11+40h]
0x1400188cf  mov     rsi, [r11+48h]
0x1400188d3  mov     rsp, r11
0x1400188d6  pop     r15
0x1400188d8  pop     r14
0x1400188da  pop     r12
0x1400188dc  pop     rdi
0x1400188dd  pop     rbp
0x1400188de  retn
0x1400188df  mov     ecx, 80070216h; this
0x1400188e4  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1400188e9  nop
0x1400188ea  mov     ecx, eax; this
0x1400188ec  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1400188f1  nop
0x1400188f2  mov     ecx, 80070216h; this
0x1400188f7  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1400188fc  int     3; Trap to Debugger
0x1400188fd  mov     ecx, eax; this
0x1400188ff  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x140018904  nop
0x140018905  mov     ecx, eax; this
0x140018907  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
