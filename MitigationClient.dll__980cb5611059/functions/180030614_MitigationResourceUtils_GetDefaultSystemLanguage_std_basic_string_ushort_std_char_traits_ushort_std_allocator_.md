# MitigationResourceUtils::GetDefaultSystemLanguage(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180030614`
- end: `0x1800306ff`
- name: `?GetDefaultSystemLanguage@MitigationResourceUtils@@SAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `235`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800307fc`

## callees

- `0x18001206c`
- `0x18001208c`
- `0x180013ebc`
- `0x180018858`
- `0x1800304cc`
- `0x180030528`
- `0x180030614`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x180030640`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x1800306ae`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x180030640`
- `api-ms-win-core-localization-l1-2-0!GetSystemPreferredUILanguages` at `0x1800306ae`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MitigationResourceUtils::GetDefaultSystemLanguage(__int64 a1)
{
  const char *v2; // r9
  PZZWSTR v4; // rbx
  unsigned int LastError; // ebx
  unsigned __int64 v6; // rdx
  const char *v7; // r9
  __int64 v8; // rax
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  ULONG pcchLanguagesBuffer; // [rsp+38h] [rbp+10h] BYREF
  ULONG pulNumLanguages; // [rsp+40h] [rbp+18h] BYREF
  PZZWSTR pwszLanguagesBuffer; // [rsp+48h] [rbp+20h] BYREF

  pulNumLanguages = 0;
  pcchLanguagesBuffer = 0;
  if ( !GetSystemPreferredUILanguages(8u, &pulNumLanguages, 0, &pcchLanguagesBuffer) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x58,
             (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\utils\\mitigationresourceutils.cpp",
             v2);
  std::make_unique<unsigned short [0],0>(&pwszLanguagesBuffer, pcchLanguagesBuffer);
  v4 = pwszLanguagesBuffer;
  if ( pwszLanguagesBuffer )
  {
    if ( GetSystemPreferredUILanguages(8u, &pulNumLanguages, pwszLanguagesBuffer, &pcchLanguagesBuffer) )
    {
      v8 = std::_WChar_traits<unsigned short>::length(v4);
      std::wstring::_Assign<unsigned short>(a1, v4, v8);
      LastError = 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x63,
                    (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\utils\\mitigationresourceutils.cpp",
                    v7);
    }
  }
  else
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5B,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\utils\\mitigationresourceutils.cpp",
      (const char *)0x8007000ELL,
      v9);
  }
  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>((void **)&pwszLanguagesBuffer, v6);
  return LastError;
}

```

## disassembly

```asm
0x180030614  mov     rax, rsp
0x180030617  mov     [rax+8], rbx
0x18003061b  push    rdi; int
0x18003061c  sub     rsp, 20h
0x180030620  mov     rdi, rcx
0x180030623  mov     dword ptr [rax+18h], 0
0x18003062a  mov     dword ptr [rax+10h], 0
0x180030631  lea     r9, [rax+10h]; pcchLanguagesBuffer
0x180030635  xor     r8d, r8d; pwszLanguagesBuffer
0x180030638  lea     rdx, [rax+18h]; pulNumLanguages
0x18003063c  lea     ecx, [r8+8]; dwFlags
0x180030640  call    cs:__imp_GetSystemPreferredUILanguages
0x180030646  test    eax, eax
0x180030648  jnz     short loc_180030663
0x18003064a  mov     rcx, [rsp+28h]; this
0x18003064f  lea     r8, aOnecoreBaseDia_0; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180030656  lea     edx, [rax+58h]; void *
0x180030659  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003065e  jmp     loc_1800306F4
0x180030663  mov     edx, [rsp+28h+pcchLanguagesBuffer]
0x180030667  lea     rcx, [rsp+28h+pwszLanguagesBuffer]
0x18003066c  call    ??$make_unique@$$BY0A@G$0A@@std@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@0@_K@Z; std::make_unique<ushort [0],0>(unsigned __int64)
0x180030671  nop
0x180030672  mov     rbx, [rsp+28h+pwszLanguagesBuffer]
0x180030677  test    rbx, rbx
0x18003067a  jnz     short loc_18003069C
0x18003067c  mov     rcx, [rsp+28h]; this
0x180030681  mov     ebx, 8007000Eh
0x180030686  mov     r9d, ebx; char *
0x180030689  lea     r8, aOnecoreBaseDia_0; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180030690  mov     edx, 5Bh ; '['; void *
0x180030695  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003069a  jmp     short loc_1800306E8
0x18003069c  lea     r9, [rsp+28h+pcchLanguagesBuffer]; pcchLanguagesBuffer
0x1800306a1  mov     r8, rbx; pwszLanguagesBuffer
0x1800306a4  lea     rdx, [rsp+28h+pulNumLanguages]; pulNumLanguages
0x1800306a9  mov     ecx, 8; dwFlags
0x1800306ae  call    cs:__imp_GetSystemPreferredUILanguages
0x1800306b4  test    eax, eax
0x1800306b6  jnz     short loc_1800306D0
0x1800306b8  mov     rcx, [rsp+28h]; this
0x1800306bd  lea     r8, aOnecoreBaseDia_0; "onecore\\base\\diagnosis\\mitigation\\c"...
0x1800306c4  lea     edx, [rax+63h]; void *
0x1800306c7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800306cc  mov     ebx, eax
0x1800306ce  jmp     short loc_1800306E8
0x1800306d0  mov     rcx, rbx
0x1800306d3  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x1800306d8  mov     r8, rax
0x1800306db  mov     rdx, rbx
0x1800306de  mov     rcx, rdi
0x1800306e1  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800306e6  xor     ebx, ebx
0x1800306e8  lea     rcx, [rsp+28h+pwszLanguagesBuffer]
0x1800306ed  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1800306f2  mov     eax, ebx
0x1800306f4  mov     rbx, [rsp+28h+arg_0]
0x1800306f9  add     rsp, 20h
0x1800306fd  pop     rdi
0x1800306fe  retn
```
