# FirstSync::InitializeResourceTimeoutCounter(ushort const *,ushort const *,ulong,int)

- ea: `0x1800a0e5c`
- end: `0x1800a0fd1`
- name: `?InitializeResourceTimeoutCounter@FirstSync@@YAJPEBG0KH@Z`
- size: `373`
- prototype: `__int64 __fastcall(PCWSTR pszMore, PCWSTR, const unsigned __int16 *, unsigned int, int)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18002430c`
- `0x1800a0df4`

## callees

- `0x180004eb0`
- `0x18000a5c4`
- `0x18000d50c`
- `0x18000dc18`
- `0x180016698`
- `0x180017024`
- `0x18001705c`
- `0x180017118`
- `0x1800a0060`
- `0x1800a0e5c`

## import_xrefs

- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800a0f48`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800a0f48`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x1800a0f6d`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x1800a0f6d`

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
    std::wstring::wstring(v17, off_1800D14E0[v5]);
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
0x1800a0e5c  push    rbp
0x1800a0e5e  push    rbx
0x1800a0e5f  push    rsi
0x1800a0e60  push    rdi
0x1800a0e61  push    r14
0x1800a0e63  mov     rbp, rsp
0x1800a0e66  sub     rsp, 60h
0x1800a0e6a  mov     rax, cs:__security_cookie
0x1800a0e71  xor     rax, rsp
0x1800a0e74  mov     [rbp+var_10], rax
0x1800a0e78  mov     esi, r9d
0x1800a0e7b  mov     edi, r8d
0x1800a0e7e  mov     r14, rdx
0x1800a0e81  mov     rbx, rcx
0x1800a0e84  test    rcx, rcx
0x1800a0e87  jnz     short loc_1800A0EAB
0x1800a0e89  mov     edx, 37Eh; void *
0x1800a0e8e  mov     ebx, 80070057h
0x1800a0e93  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a0e9a  mov     r9d, ebx; char *
0x1800a0e9d  mov     rcx, [rbp+28h]; this
0x1800a0ea1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0ea6  jmp     loc_1800A0FB7
0x1800a0eab  cmp     edi, 4
0x1800a0eae  jb      short loc_1800A0EB7
0x1800a0eb0  mov     edx, 37Fh
0x1800a0eb5  jmp     short loc_1800A0E8E
0x1800a0eb7  mov     [rbp+var_38], 0
0x1800a0ebe  mov     qword ptr [rbp+var_40], 0
0x1800a0ec6  xor     edx, edx
0x1800a0ec8  lea     rcx, [rbp+var_40]
0x1800a0ecc  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800a0ed1  mov     r9d, 1; HKEY *
0x1800a0ed7  lea     r8, [rbp+var_40]; unsigned __int16 *
0x1800a0edb  mov     rdx, r14; PCWSTR
0x1800a0ede  mov     rcx, rbx; pszMore
0x1800a0ee1  call    ?GetFirstSyncKey@FirstSync@@YAJPEBG0PEAPEAUHKEY__@@H@Z; FirstSync::GetFirstSyncKey(ushort const *,ushort const *,HKEY__ * *,int)
0x1800a0ee6  mov     ebx, eax
0x1800a0ee8  test    eax, eax
0x1800a0eea  jns     short loc_1800A0F09
0x1800a0eec  mov     rcx, [rbp+28h]; this
0x1800a0ef0  mov     r9d, eax; char *
0x1800a0ef3  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a0efa  mov     edx, 383h; void *
0x1800a0eff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0f04  jmp     loc_1800A0FAE
0x1800a0f09  lea     rax, off_1800D14E0; "Policy"
0x1800a0f10  mov     rdx, [rax+rdi*8]
0x1800a0f14  lea     rcx, [rbp+var_30]
0x1800a0f18  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a0f1d  nop
0x1800a0f1e  lea     rdx, aDuration; "Duration"
0x1800a0f25  lea     rcx, [rbp+var_30]
0x1800a0f29  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800a0f2e  test    esi, esi
0x1800a0f30  jnz     short loc_1800A0F58
0x1800a0f32  lea     rcx, [rbp+var_30]
0x1800a0f36  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a0f3b  mov     r8, rax
0x1800a0f3e  lea     r9, [rbp+var_38]
0x1800a0f42  xor     edx, edx
0x1800a0f44  mov     rcx, qword ptr [rbp+var_40]
0x1800a0f48  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800a0f4f  nop     dword ptr [rax+rax+00h]
0x1800a0f54  test    eax, eax
0x1800a0f56  jns     short loc_1800A0FA3
0x1800a0f58  lea     rcx, [rbp+var_30]
0x1800a0f5c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a0f61  mov     r8, rax
0x1800a0f64  xor     r9d, r9d
0x1800a0f67  xor     edx, edx
0x1800a0f69  mov     rcx, qword ptr [rbp+var_40]
0x1800a0f6d  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800a0f74  nop     dword ptr [rax+rax+00h]
0x1800a0f79  mov     ebx, eax
0x1800a0f7b  test    eax, eax
0x1800a0f7d  jns     short loc_1800A0FA3
0x1800a0f7f  mov     rcx, [rbp+28h]; this
0x1800a0f83  mov     r9d, eax; char *
0x1800a0f86  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a0f8d  mov     edx, 38Bh; void *
0x1800a0f92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0f97  nop
0x1800a0f98  lea     rcx, [rbp+var_30]
0x1800a0f9c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a0fa1  jmp     short loc_1800A0FAE
0x1800a0fa3  lea     rcx, [rbp+var_30]
0x1800a0fa7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a0fac  xor     ebx, ebx
0x1800a0fae  lea     rcx, [rbp+var_40]
0x1800a0fb2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a0fb7  mov     eax, ebx
0x1800a0fb9  mov     rcx, [rbp+var_10]
0x1800a0fbd  xor     rcx, rsp; StackCookie
0x1800a0fc0  call    __security_check_cookie
0x1800a0fc5  add     rsp, 60h
0x1800a0fc9  pop     r14
0x1800a0fcb  pop     rdi
0x1800a0fcc  pop     rsi
0x1800a0fcd  pop     rbx
0x1800a0fce  pop     rbp
0x1800a0fcf  retn
```
