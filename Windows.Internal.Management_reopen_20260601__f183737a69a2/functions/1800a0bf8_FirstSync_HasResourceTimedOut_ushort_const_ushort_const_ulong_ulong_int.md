# FirstSync::HasResourceTimedOut(ushort const *,ushort const *,ulong,ulong,int *)

- ea: `0x1800a0bf8`
- end: `0x1800a0dec`
- name: `?HasResourceTimedOut@FirstSync@@YAJPEBG0KKPEAH@Z`
- size: `500`
- prototype: `__int64 __usercall@<rax>(PCWSTR pszMore@<rcx>, PCWSTR@<rdx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, unsigned int, int *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18002430c`
- `0x1800a73f8`

## callees

- `0x180004eb0`
- `0x18000a5c4`
- `0x18000d50c`
- `0x18000dc18`
- `0x180016698`
- `0x180017024`
- `0x18001705c`
- `0x180017118`
- `0x1800184c0`
- `0x1800a0060`
- `0x1800a094c`
- `0x1800a0bf8`

## import_xrefs

- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800a0d22`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800a0d22`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x1800a0d60`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x1800a0d60`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FirstSync::HasResourceTimedOut(PCWSTR pszMore, PCWSTR a2, unsigned int *a3, int a4, _DWORD *a5)
{
  __int64 v6; // r14
  __int64 v9; // rdx
  int TimeoutUntilSyncFailure; // ebx
  const unsigned __int16 *v11; // rax
  int DWORD; // eax
  __int64 v13; // r9
  __int64 v14; // rdx
  const unsigned __int16 *v15; // rax
  unsigned int v16; // r9d
  int v17; // eax
  unsigned int v19; // [rsp+20h] [rbp-40h] BYREF
  unsigned __int16 v20[2]; // [rsp+24h] [rbp-3Ch] BYREF
  unsigned int v21; // [rsp+28h] [rbp-38h] BYREF
  unsigned __int16 v22[4]; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v23[32]; // [rsp+38h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]

  v6 = (unsigned int)a3;
  if ( pszMore )
  {
    if ( (unsigned int)a3 >= 4 )
    {
      v9 = 791;
      goto LABEL_3;
    }
    if ( !a5 )
    {
      TimeoutUntilSyncFailure = -2147467261;
      v9 = 792;
      goto LABEL_4;
    }
    *(_DWORD *)v20 = 0;
    TimeoutUntilSyncFailure = FirstSync::GetTimeoutUntilSyncFailure(pszMore, v20, a3);
    if ( TimeoutUntilSyncFailure < 0 )
    {
      v9 = 795;
      goto LABEL_4;
    }
    v21 = 0;
    TimeoutUntilSyncFailure = ULongLongToULong(60LL * *(unsigned int *)v20, &v21);
    if ( TimeoutUntilSyncFailure < 0 )
    {
      v9 = 798;
      goto LABEL_4;
    }
    *(_QWORD *)v22 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      v22,
      0);
    TimeoutUntilSyncFailure = FirstSync::GetFirstSyncKey(pszMore, a2, v22, (HKEY *)1);
    if ( TimeoutUntilSyncFailure >= 0 )
    {
      v19 = 0;
      std::wstring::wstring(v23, off_1800D14E0[v6]);
      std::wstring::append(v23, L"Duration");
      v11 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v23);
      DWORD = OmaDmRegistryGetDWORD(*(HKEY *)v22, 0, v11, &v19);
      TimeoutUntilSyncFailure = DWORD;
      if ( DWORD < 0 )
      {
        v13 = (unsigned int)DWORD;
        v14 = 807;
LABEL_21:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v14,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
          (const char *)v13,
          v19);
        std::wstring::~wstring(v23);
        goto LABEL_22;
      }
      if ( a4 + v19 < v19 )
      {
        v19 = -1;
        TimeoutUntilSyncFailure = -2147024362;
        v13 = 2147942934LL;
        v14 = 808;
        goto LABEL_21;
      }
      v19 += a4;
      v15 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v23);
      v17 = OmaDmRegistrySetDWORD(*(HKEY *)v22, 0, v15, v16);
      TimeoutUntilSyncFailure = v17;
      if ( v17 < 0 )
      {
        v13 = (unsigned int)v17;
        v14 = 809;
        goto LABEL_21;
      }
      *a5 = v19 >= v21;
      std::wstring::~wstring(v23);
      TimeoutUntilSyncFailure = 0;
    }
LABEL_22:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v22);
    return (unsigned int)TimeoutUntilSyncFailure;
  }
  v9 = 790;
LABEL_3:
  TimeoutUntilSyncFailure = -2147024809;
LABEL_4:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
    (const char *)(unsigned int)TimeoutUntilSyncFailure,
    v19);
  return (unsigned int)TimeoutUntilSyncFailure;
}

```

## disassembly

```asm
0x1800a0bf8  push    rbp
0x1800a0bfa  push    rbx
0x1800a0bfb  push    rsi
0x1800a0bfc  push    rdi
0x1800a0bfd  push    r12
0x1800a0bff  push    r14
0x1800a0c01  push    r15
0x1800a0c03  mov     rbp, rsp
0x1800a0c06  sub     rsp, 60h
0x1800a0c0a  mov     rax, cs:__security_cookie
0x1800a0c11  xor     rax, rsp
0x1800a0c14  mov     [rbp+var_8], rax
0x1800a0c18  mov     r15d, r9d
0x1800a0c1b  mov     r14d, r8d
0x1800a0c1e  mov     r12, rdx
0x1800a0c21  mov     rdi, rcx
0x1800a0c24  mov     rsi, qword ptr [rbp+arg_20]
0x1800a0c28  test    rcx, rcx
0x1800a0c2b  jnz     short loc_1800A0C4F
0x1800a0c2d  mov     edx, 316h; void *
0x1800a0c32  mov     ebx, 80070057h
0x1800a0c37  mov     rcx, [rbp+38h]; this
0x1800a0c3b  mov     r9d, ebx; char *
0x1800a0c3e  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a0c45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0c4a  jmp     loc_1800A0DCE
0x1800a0c4f  cmp     r14d, 4
0x1800a0c53  jb      short loc_1800A0C5C
0x1800a0c55  mov     edx, 317h
0x1800a0c5a  jmp     short loc_1800A0C32
0x1800a0c5c  test    rsi, rsi
0x1800a0c5f  jnz     short loc_1800A0C6D
0x1800a0c61  mov     ebx, 80004003h
0x1800a0c66  mov     edx, 318h
0x1800a0c6b  jmp     short loc_1800A0C37
0x1800a0c6d  mov     dword ptr [rbp+var_3C], 0
0x1800a0c74  lea     rdx, [rbp+var_3C]; unsigned __int16 *
0x1800a0c78  call    ?GetTimeoutUntilSyncFailure@FirstSync@@YAJPEBGPEAK@Z; FirstSync::GetTimeoutUntilSyncFailure(ushort const *,ulong *)
0x1800a0c7d  mov     ebx, eax
0x1800a0c7f  test    eax, eax
0x1800a0c81  jns     short loc_1800A0C8A
0x1800a0c83  mov     edx, 31Bh
0x1800a0c88  jmp     short loc_1800A0C37
0x1800a0c8a  mov     [rbp+var_38], 0
0x1800a0c91  mov     eax, dword ptr [rbp+var_3C]
0x1800a0c94  imul    rcx, rax, 3Ch ; '<'; unsigned __int64
0x1800a0c98  lea     rdx, [rbp+var_38]; unsigned int *
0x1800a0c9c  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800a0ca1  mov     ebx, eax
0x1800a0ca3  test    eax, eax
0x1800a0ca5  jns     short loc_1800A0CAE
0x1800a0ca7  mov     edx, 31Eh
0x1800a0cac  jmp     short loc_1800A0C37
0x1800a0cae  mov     qword ptr [rbp+var_30], 0
0x1800a0cb6  xor     edx, edx
0x1800a0cb8  lea     rcx, [rbp+var_30]
0x1800a0cbc  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800a0cc1  mov     r9d, 1; HKEY *
0x1800a0cc7  lea     r8, [rbp+var_30]; unsigned __int16 *
0x1800a0ccb  mov     rdx, r12; PCWSTR
0x1800a0cce  mov     rcx, rdi; pszMore
0x1800a0cd1  call    ?GetFirstSyncKey@FirstSync@@YAJPEBG0PEAPEAUHKEY__@@H@Z; FirstSync::GetFirstSyncKey(ushort const *,ushort const *,HKEY__ * *,int)
0x1800a0cd6  mov     ebx, eax
0x1800a0cd8  test    eax, eax
0x1800a0cda  js      loc_1800A0DC5
0x1800a0ce0  mov     [rbp+var_40], 0
0x1800a0ce7  lea     rax, off_1800D14E0; "Policy"
0x1800a0cee  mov     rdx, [rax+r14*8]
0x1800a0cf2  lea     rcx, [rbp+var_28]
0x1800a0cf6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a0cfb  nop
0x1800a0cfc  lea     rdx, aDuration; "Duration"
0x1800a0d03  lea     rcx, [rbp+var_28]
0x1800a0d07  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800a0d0c  lea     rcx, [rbp+var_28]
0x1800a0d10  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a0d15  mov     r8, rax
0x1800a0d18  lea     r9, [rbp+var_40]
0x1800a0d1c  xor     edx, edx
0x1800a0d1e  mov     rcx, qword ptr [rbp+var_30]
0x1800a0d22  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800a0d29  nop     dword ptr [rax+rax+00h]
0x1800a0d2e  mov     ebx, eax
0x1800a0d30  test    eax, eax
0x1800a0d32  jns     short loc_1800A0D3E
0x1800a0d34  mov     r9d, eax
0x1800a0d37  mov     edx, 327h
0x1800a0d3c  jmp     short loc_1800A0DAA
0x1800a0d3e  mov     eax, [rbp+var_40]
0x1800a0d41  lea     r9d, [r15+rax]
0x1800a0d45  cmp     r9d, eax
0x1800a0d48  jb      short loc_1800A0D96
0x1800a0d4a  mov     [rbp+var_40], r9d
0x1800a0d4e  lea     rcx, [rbp+var_28]
0x1800a0d52  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a0d57  mov     r8, rax
0x1800a0d5a  xor     edx, edx
0x1800a0d5c  mov     rcx, qword ptr [rbp+var_30]
0x1800a0d60  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800a0d67  nop     dword ptr [rax+rax+00h]
0x1800a0d6c  mov     ebx, eax
0x1800a0d6e  test    eax, eax
0x1800a0d70  jns     short loc_1800A0D7C
0x1800a0d72  mov     r9d, eax
0x1800a0d75  mov     edx, 329h
0x1800a0d7a  jmp     short loc_1800A0DAA
0x1800a0d7c  xor     ecx, ecx
0x1800a0d7e  mov     eax, [rbp+var_38]
0x1800a0d81  cmp     [rbp+var_40], eax
0x1800a0d84  setnb   cl
0x1800a0d87  mov     [rsi], ecx
0x1800a0d89  lea     rcx, [rbp+var_28]
0x1800a0d8d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a0d92  xor     ebx, ebx
0x1800a0d94  jmp     short loc_1800A0DC5
0x1800a0d96  mov     [rbp+var_40], 0FFFFFFFFh
0x1800a0d9d  mov     ebx, 80070216h
0x1800a0da2  mov     r9d, ebx; char *
0x1800a0da5  mov     edx, 328h; void *
0x1800a0daa  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a0db1  mov     rcx, [rbp+38h]; this
0x1800a0db5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0dba  nop
0x1800a0dbb  lea     rcx, [rbp+var_28]
0x1800a0dbf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a0dc4  nop
0x1800a0dc5  lea     rcx, [rbp+var_30]
0x1800a0dc9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a0dce  mov     eax, ebx
0x1800a0dd0  mov     rcx, [rbp+var_8]
0x1800a0dd4  xor     rcx, rsp; StackCookie
0x1800a0dd7  call    __security_check_cookie
0x1800a0ddc  add     rsp, 60h
0x1800a0de0  pop     r15
0x1800a0de2  pop     r14
0x1800a0de4  pop     r12
0x1800a0de6  pop     rdi
0x1800a0de7  pop     rsi
0x1800a0de8  pop     rbx
0x1800a0de9  pop     rbp
0x1800a0dea  retn
```
