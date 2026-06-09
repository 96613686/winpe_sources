# EnterpriseFeatureControl::ReadPolicyState(bool *)

- ea: `0x180019ffc`
- end: `0x18001a13c`
- name: `?ReadPolicyState@EnterpriseFeatureControl@@CAJPEA_N@Z`
- size: `320`
- prototype: `__int64 __fastcall(bool *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x180018ff4`

## callees

- `0x18000972c`
- `0x180009f8c`
- `0x180010248`
- `0x180012940`
- `0x180017c74`
- `0x180019ffc`
- `0x18001a234`
- `0x18001be8c`

## string_xrefs

- `0x18001a0c4`: `\UpdatePolicy\PolicyState`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall EnterpriseFeatureControl::ReadPolicyState(bool *a1, const unsigned __int16 *a2)
{
  unsigned int v3; // edi
  __int64 v4; // rdx
  __int64 v5; // r9
  int PersistedRegistryLocation; // eax
  __int64 v7; // rdx
  unsigned __int16 *v8; // rdi
  __int64 v9; // rdx
  __int64 v10; // r9
  int v11; // eax
  HKEY v12; // rcx
  const unsigned __int16 *v13; // r8
  int v14; // eax
  const wchar_t *v16; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  unsigned int v18; // [rsp+50h] [rbp+20h] BYREF
  unsigned __int16 *v19; // [rsp+58h] [rbp+28h] BYREF
  unsigned __int16 *v20; // [rsp+60h] [rbp+30h] BYREF

  v18 = 0;
  v19 = 0;
  v20 = 0;
  if ( !a1 )
  {
    v3 = -2147467261;
    v4 = 149;
    v5 = 2147500035LL;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
      (const char *)v5,
      (int)v16);
    goto LABEL_17;
  }
  PersistedRegistryLocation = EnterpriseFeatureControl::GetPersistedRegistryLocation(
                                (const unsigned __int16 *)a1,
                                a2,
                                &v20);
  v3 = PersistedRegistryLocation;
  if ( PersistedRegistryLocation < 0 )
  {
    v4 = 151;
LABEL_5:
    v5 = (unsigned int)PersistedRegistryLocation;
    goto LABEL_6;
  }
  PersistedRegistryLocation = StringCchLengthW(v20, 0x7FFFFFFFu, (unsigned __int64 *)&v19);
  v3 = PersistedRegistryLocation;
  if ( PersistedRegistryLocation < 0 )
  {
    v4 = 153;
    goto LABEL_5;
  }
  v8 = v19;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &v19,
    v7,
    v19 + 14);
  if ( v19 )
  {
    v16 = L"\\UpdatePolicy\\PolicyState";
    v11 = StringCchPrintfW(v19, (unsigned __int64)(v8 + 14), L"%s\\%s", v20);
    v3 = v11;
    if ( v11 >= 0 )
    {
      v14 = EnterpriseFeatureControl::RegQueryDwordValue(v12, v19, v13, &v18);
      v3 = v14;
      if ( v14 >= 0 )
      {
        *a1 = v18 - 1 <= 1;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
        v3 = 0;
        goto LABEL_17;
      }
      v10 = (unsigned int)v14;
      v9 = 171;
    }
    else
    {
      v10 = (unsigned int)v11;
      v9 = 165;
    }
  }
  else
  {
    v3 = -2147024882;
    v9 = 158;
    v10 = 2147942414LL;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseFeatureControl.h",
    (const char *)v10,
    (int)v16);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v19);
LABEL_17:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v20);
  return v3;
}

```

## disassembly

```asm
0x180019ffc  push    rbp
0x180019ffe  push    rsi
0x180019fff  push    rdi
0x18001a000  mov     rbp, rsp
0x18001a003  sub     rsp, 30h
0x18001a007  mov     [rbp+arg_0], 0
0x18001a00e  mov     rsi, rcx
0x18001a011  mov     [rbp+arg_8], 0
0x18001a019  mov     [rbp+arg_10], 0
0x18001a021  test    rcx, rcx
0x18001a024  jnz     short loc_18001A035
0x18001a026  mov     edi, 80004003h
0x18001a02b  mov     edx, 95h; unsigned __int16 *
0x18001a030  mov     r9d, edi
0x18001a033  jmp     short loc_18001A04C
0x18001a035  lea     r8, [rbp+arg_10]; unsigned __int16 **
0x18001a039  call    ?GetPersistedRegistryLocation@EnterpriseFeatureControl@@CAJPEBG0PEAPEAG@Z; EnterpriseFeatureControl::GetPersistedRegistryLocation(ushort const *,ushort const *,ushort * *)
0x18001a03e  mov     edi, eax
0x18001a040  test    eax, eax
0x18001a042  jns     short loc_18001A061
0x18001a044  mov     edx, 97h; void *
0x18001a049  mov     r9d, eax; char *
0x18001a04c  mov     rcx, [rbp+18h]; this
0x18001a050  lea     r8, aOnecoreInterna_4; "onecore\\internal\\enduser\\inc\\Enterp"...
0x18001a057  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a05c  jmp     loc_18001A129
0x18001a061  mov     rcx, [rbp+arg_10]; unsigned __int16 *
0x18001a065  lea     r8, [rbp+arg_8]; unsigned __int64 *
0x18001a069  mov     edx, 7FFFFFFFh; unsigned __int64
0x18001a06e  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001a073  mov     edi, eax
0x18001a075  test    eax, eax
0x18001a077  jns     short loc_18001A080
0x18001a079  mov     edx, 99h
0x18001a07e  jmp     short loc_18001A049
0x18001a080  mov     rdi, [rbp+arg_8]
0x18001a084  lea     rcx, [rbp+arg_8]
0x18001a088  lea     r8, [rdi+1Ch]
0x18001a08c  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18001a091  cmp     [rbp+arg_8], 0
0x18001a096  jnz     short loc_18001A0C0
0x18001a098  mov     edi, 8007000Eh
0x18001a09d  mov     edx, 9Eh; void *
0x18001a0a2  mov     r9d, edi; char *
0x18001a0a5  mov     rcx, [rbp+18h]; this
0x18001a0a9  lea     r8, aOnecoreInterna_4; "onecore\\internal\\enduser\\inc\\Enterp"...
0x18001a0b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a0b5  lea     rcx, [rbp+arg_8]
0x18001a0b9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001a0be  jmp     short loc_18001A129
0x18001a0c0  mov     r9, [rbp+arg_10]
0x18001a0c4  lea     rax, aUpdatepolicyPo; "\\UpdatePolicy\\PolicyState"
0x18001a0cb  mov     rcx, [rbp+arg_8]; unsigned __int16 *
0x18001a0cf  lea     r8, aSS; "%s\\%s"
0x18001a0d6  lea     rdx, [rdi+1Ch]; unsigned __int64
0x18001a0da  mov     [rsp+30h+var_10], rax
0x18001a0df  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001a0e4  mov     edi, eax
0x18001a0e6  test    eax, eax
0x18001a0e8  jns     short loc_18001A0F4
0x18001a0ea  mov     r9d, eax
0x18001a0ed  mov     edx, 0A5h
0x18001a0f2  jmp     short loc_18001A0A5
0x18001a0f4  mov     rdx, [rbp+arg_8]; unsigned __int16 *
0x18001a0f8  lea     r9, [rbp+arg_0]; unsigned int *
0x18001a0fc  call    ?RegQueryDwordValue@EnterpriseFeatureControl@@CAJPEAUHKEY__@@PEBG1PEAK@Z; EnterpriseFeatureControl::RegQueryDwordValue(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18001a101  mov     edi, eax
0x18001a103  test    eax, eax
0x18001a105  jns     short loc_18001A111
0x18001a107  mov     r9d, eax
0x18001a10a  mov     edx, 0ABh
0x18001a10f  jmp     short loc_18001A0A5
0x18001a111  mov     eax, [rbp+arg_0]
0x18001a114  lea     rcx, [rbp+arg_8]
0x18001a118  dec     eax
0x18001a11a  cmp     eax, 1
0x18001a11d  setbe   al
0x18001a120  mov     [rsi], al
0x18001a122  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001a127  xor     edi, edi
0x18001a129  lea     rcx, [rbp+arg_10]
0x18001a12d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18001a132  mov     eax, edi
0x18001a134  add     rsp, 30h
0x18001a138  pop     rdi
0x18001a139  pop     rsi
0x18001a13a  pop     rbp
0x18001a13b  retn
```
