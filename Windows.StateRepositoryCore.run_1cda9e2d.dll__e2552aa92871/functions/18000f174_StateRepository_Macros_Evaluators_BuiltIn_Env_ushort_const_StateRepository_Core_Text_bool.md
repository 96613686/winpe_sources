# StateRepository::Macros::Evaluators::BuiltIn::Env(ushort const *,StateRepository::Core::Text &,bool &)

- ea: `0x18000f174`
- end: `0x18000f220`
- name: `?Env@BuiltIn@Evaluators@Macros@StateRepository@@YAJPEBGAEAVText@Core@4@AEA_N@Z`
- size: `172`
- prototype: `int(StateRepository::Macros::Evaluators::BuiltIn *__hidden this, const unsigned __int16 *, struct StateRepository::Core::Text *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000f228`

## callees

- `0x18000940c`
- `0x18000e760`
- `0x18000ee8c`
- `0x18000f000`
- `0x18000f174`

## string_xrefs

- `0x18000f1b2`: `onecore\internal\sdk\inc\wil\opensource/wil/win32_helpers.h`

## pseudocode

```c
__int64 __fastcall StateRepository::Macros::Evaluators::BuiltIn::Env(
        StateRepository::Macros::Evaluators::BuiltIn *this,
        StateRepository::Core::Text *a2,
        struct StateRepository::Core::Text *a3,
        bool *a4)
{
  unsigned int v6; // ebx
  unsigned __int64 v7; // r9
  __int64 v8; // rdx
  unsigned __int16 *v9; // rdx
  int v10; // eax
  int v12; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  unsigned __int16 *v14; // [rsp+60h] [rbp+18h] BYREF

  *(_BYTE *)a3 = 0;
  v14 = 0;
  v6 = wil::GetEnvironmentVariableW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,128>(
         this,
         &v14,
         a3,
         a4);
  if ( (int)(v6 + 0x80000000) < 0 || v6 == -2147024693 )
  {
    v9 = v14;
    *(_BYTE *)a3 = 1;
    if ( !v9 || !*v9 || (v10 = StateRepository::Core::Text::Append(a2, v9), v6 = v10, v10 >= 0) )
    {
      v6 = 0;
      goto LABEL_10;
    }
    v7 = (unsigned int)v10;
    v8 = 128;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F2,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/win32_helpers.h",
      (const char *)v6,
      v12);
    v7 = v6;
    v8 = 124;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srmacros-builtin.cpp",
    (const char *)v7,
    v12);
LABEL_10:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v14);
  return v6;
}

```

## disassembly

```asm
0x18000f174  push    rbx
0x18000f176  push    rbp
0x18000f177  push    rsi
0x18000f178  push    rdi
0x18000f179  sub     rsp, 28h
0x18000f17d  mov     rsi, rdx
0x18000f180  xor     ebp, ebp
0x18000f182  lea     rdx, [rsp+48h+arg_10]
0x18000f187  mov     [r8], bpl
0x18000f18a  mov     [rsp+48h+arg_10], rbp
0x18000f18f  mov     rdi, r8
0x18000f192  call    ??$GetEnvironmentVariableW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0IA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::GetEnvironmentVariableW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,128>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18000f197  mov     ebx, eax
0x18000f199  mov     eax, 80000000h
0x18000f19e  lea     ecx, [rbx+rax]
0x18000f1a1  test    eax, ecx
0x18000f1a3  jnz     short loc_18000F1CE
0x18000f1a5  cmp     ebx, 800700CBh
0x18000f1ab  jz      short loc_18000F1CE
0x18000f1ad  mov     rcx, [rsp+48h]; this
0x18000f1b2  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000f1b9  mov     r9d, ebx; char *
0x18000f1bc  mov     edx, 1F2h; void *
0x18000f1c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f1c6  mov     r9d, ebx
0x18000f1c9  lea     edx, [rbp+7Ch]
0x18000f1cc  jmp     short loc_18000F1F6
0x18000f1ce  mov     rdx, [rsp+48h+arg_10]; unsigned __int16 *
0x18000f1d3  mov     byte ptr [rdi], 1
0x18000f1d6  test    rdx, rdx
0x18000f1d9  jz      short loc_18000F209
0x18000f1db  cmp     [rdx], bp
0x18000f1de  jz      short loc_18000F209
0x18000f1e0  mov     rcx, rsi; this
0x18000f1e3  call    ?Append@Text@Core@StateRepository@@QEAAJPEBG@Z; StateRepository::Core::Text::Append(ushort const *)
0x18000f1e8  mov     ebx, eax
0x18000f1ea  test    eax, eax
0x18000f1ec  jns     short loc_18000F209
0x18000f1ee  mov     r9d, eax; char *
0x18000f1f1  mov     edx, 80h; void *
0x18000f1f6  mov     rcx, [rsp+48h]; this
0x18000f1fb  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\staterepositor"...
0x18000f202  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f207  jmp     short loc_18000F20B
0x18000f209  mov     ebx, ebp
0x18000f20b  lea     rcx, [rsp+48h+arg_10]
0x18000f210  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000f215  mov     eax, ebx
0x18000f217  add     rsp, 28h
0x18000f21b  pop     rdi
0x18000f21c  pop     rsi
0x18000f21d  pop     rbp
0x18000f21e  pop     rbx
0x18000f21f  retn
```
