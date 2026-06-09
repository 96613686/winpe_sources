# FirstSync::InitializeResourceTimeoutCounter(ushort const *,ushort const *,ulong,int)

- ea: `0x18009dea4`
- end: `0x18009e00c`
- name: `?InitializeResourceTimeoutCounter@FirstSync@@YAJPEBG0KH@Z`
- size: `360`
- prototype: `__int64 __fastcall(PCWSTR pszMore, PCWSTR, const unsigned __int16 *, unsigned int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180025be0`
- `0x18009de3c`

## callees

- `0x180004d50`
- `0x18000a2a4`
- `0x18000cfdc`
- `0x18000d724`
- `0x180015f70`
- `0x1800168d0`
- `0x1800168fc`
- `0x1800169b8`
- `0x18009d138`
- `0x18009dea4`

## import_xrefs

- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18009df90`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18009df90`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x18009dfaf`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x18009dfaf`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FirstSync::InitializeResourceTimeoutCounter(
        PCWSTR pszMore,
        PCWSTR a2,
        const unsigned __int16 *a3,
        int a4)
{
  __int64 v5; // rdi
  __int64 v8; // rdx
  unsigned int v9; // ebx
  int FirstSyncKey; // eax
  const unsigned __int16 *v11; // rax
  const unsigned __int16 *v12; // rax
  int v13; // eax
  unsigned __int16 v15[4]; // [rsp+20h] [rbp-40h] BYREF
  unsigned int v16; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v17[32]; // [rsp+30h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  v5 = (unsigned int)a3;
  if ( !pszMore )
  {
    v8 = 894;
LABEL_3:
    v9 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
      (const char *)0x80070057LL,
      *(int *)v15);
    return v9;
  }
  if ( (unsigned int)a3 >= 4 )
  {
    v8 = 895;
    goto LABEL_3;
  }
  v16 = 0;
  *(_QWORD *)v15 = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    v15,
    0);
  FirstSyncKey = FirstSync::GetFirstSyncKey(pszMore, a2, v15, (HKEY *)1);
  v9 = FirstSyncKey;
  if ( FirstSyncKey >= 0 )
  {
    std::wstring::wstring(v17, off_1800CD4E0[v5]);
    std::wstring::append(v17, L"Duration");
    if ( (a4
       || (v11 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17),
           (int)OmaDmRegistryGetDWORD(*(HKEY *)v15, 0, v11, &v16) < 0))
      && (v12 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17),
          v13 = OmaDmRegistrySetDWORD(*(HKEY *)v15, 0, v12, 0),
          v9 = v13,
          v13 < 0) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x38B,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
        (const char *)(unsigned int)v13,
        *(int *)v15);
      std::wstring::~wstring(v17);
    }
    else
    {
      std::wstring::~wstring(v17);
      v9 = 0;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x383,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
      (const char *)(unsigned int)FirstSyncKey,
      *(int *)v15);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v15);
  return v9;
}

```

## disassembly

```asm
0x18009dea4  push    rbp
0x18009dea6  push    rbx
0x18009dea7  push    rsi
0x18009dea8  push    rdi
0x18009dea9  push    r14
0x18009deab  mov     rbp, rsp
0x18009deae  sub     rsp, 60h
0x18009deb2  mov     rax, cs:__security_cookie
0x18009deb9  xor     rax, rsp
0x18009debc  mov     [rbp+var_10], rax
0x18009dec0  mov     esi, r9d
0x18009dec3  mov     edi, r8d
0x18009dec6  mov     r14, rdx
0x18009dec9  mov     rbx, rcx
0x18009decc  test    rcx, rcx
0x18009decf  jnz     short loc_18009DEF3
0x18009ded1  mov     edx, 37Eh; void *
0x18009ded6  mov     ebx, 80070057h
0x18009dedb  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x18009dee2  mov     r9d, ebx; char *
0x18009dee5  mov     rcx, [rbp+28h]; this
0x18009dee9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009deee  jmp     loc_18009DFF3
0x18009def3  cmp     edi, 4
0x18009def6  jb      short loc_18009DEFF
0x18009def8  mov     edx, 37Fh
0x18009defd  jmp     short loc_18009DED6
0x18009deff  mov     [rbp+var_38], 0
0x18009df06  mov     qword ptr [rbp+var_40], 0
0x18009df0e  xor     edx, edx
0x18009df10  lea     rcx, [rbp+var_40]
0x18009df14  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18009df19  mov     r9d, 1; HKEY *
0x18009df1f  lea     r8, [rbp+var_40]; unsigned __int16 *
0x18009df23  mov     rdx, r14; PCWSTR
0x18009df26  mov     rcx, rbx; pszMore
0x18009df29  call    ?GetFirstSyncKey@FirstSync@@YAJPEBG0PEAPEAUHKEY__@@H@Z; FirstSync::GetFirstSyncKey(ushort const *,ushort const *,HKEY__ * *,int)
0x18009df2e  mov     ebx, eax
0x18009df30  test    eax, eax
0x18009df32  jns     short loc_18009DF51
0x18009df34  mov     rcx, [rbp+28h]; this
0x18009df38  mov     r9d, eax; char *
0x18009df3b  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x18009df42  mov     edx, 383h; void *
0x18009df47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009df4c  jmp     loc_18009DFEA
0x18009df51  lea     rax, off_1800CD4E0; "Policy"
0x18009df58  mov     rdx, [rax+rdi*8]
0x18009df5c  lea     rcx, [rbp+var_30]
0x18009df60  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009df65  nop
0x18009df66  lea     rdx, aDuration; "Duration"
0x18009df6d  lea     rcx, [rbp+var_30]
0x18009df71  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18009df76  test    esi, esi
0x18009df78  jnz     short loc_18009DF9A
0x18009df7a  lea     rcx, [rbp+var_30]
0x18009df7e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009df83  mov     r8, rax
0x18009df86  lea     r9, [rbp+var_38]
0x18009df8a  xor     edx, edx
0x18009df8c  mov     rcx, qword ptr [rbp+var_40]
0x18009df90  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18009df96  test    eax, eax
0x18009df98  jns     short loc_18009DFDF
0x18009df9a  lea     rcx, [rbp+var_30]
0x18009df9e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009dfa3  mov     r8, rax
0x18009dfa6  xor     r9d, r9d
0x18009dfa9  xor     edx, edx
0x18009dfab  mov     rcx, qword ptr [rbp+var_40]
0x18009dfaf  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18009dfb5  mov     ebx, eax
0x18009dfb7  test    eax, eax
0x18009dfb9  jns     short loc_18009DFDF
0x18009dfbb  mov     rcx, [rbp+28h]; this
0x18009dfbf  mov     r9d, eax; char *
0x18009dfc2  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x18009dfc9  mov     edx, 38Bh; void *
0x18009dfce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009dfd3  nop
0x18009dfd4  lea     rcx, [rbp+var_30]
0x18009dfd8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009dfdd  jmp     short loc_18009DFEA
0x18009dfdf  lea     rcx, [rbp+var_30]
0x18009dfe3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009dfe8  xor     ebx, ebx
0x18009dfea  lea     rcx, [rbp+var_40]
0x18009dfee  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009dff3  mov     eax, ebx
0x18009dff5  mov     rcx, [rbp+var_10]
0x18009dff9  xor     rcx, rsp; StackCookie
0x18009dffc  call    __security_check_cookie
0x18009e001  add     rsp, 60h
0x18009e005  pop     r14
0x18009e007  pop     rdi
0x18009e008  pop     rsi
0x18009e009  pop     rbx
0x18009e00a  pop     rbp
0x18009e00b  retn
```
