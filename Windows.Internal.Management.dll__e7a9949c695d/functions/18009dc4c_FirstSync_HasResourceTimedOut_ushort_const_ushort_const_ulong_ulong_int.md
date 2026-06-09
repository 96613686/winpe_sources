# FirstSync::HasResourceTimedOut(ushort const *,ushort const *,ulong,ulong,int *)

- ea: `0x18009dc4c`
- end: `0x18009de33`
- name: `?HasResourceTimedOut@FirstSync@@YAJPEBG0KKPEAH@Z`
- size: `487`
- prototype: `__int64 __usercall@<rax>(PCWSTR pszMore@<rcx>, PCWSTR@<rdx>, const unsigned __int16 *@<r8>, unsigned int@<r9d>, unsigned int, int *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180025be0`
- `0x1800a40ac`

## callees

- `0x180004d50`
- `0x18000a2a4`
- `0x18000cfdc`
- `0x18000d724`
- `0x180015f70`
- `0x1800168d0`
- `0x1800168fc`
- `0x1800169b8`
- `0x180019ae4`
- `0x18009d138`
- `0x18009d9b8`
- `0x18009dc4c`

## import_xrefs

- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18009dd76`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x18009dd76`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x18009ddae`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x18009ddae`

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
      std::wstring::wstring(v23, off_1800CD4E0[v6]);
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
0x18009dc4c  push    rbp
0x18009dc4e  push    rbx
0x18009dc4f  push    rsi
0x18009dc50  push    rdi
0x18009dc51  push    r12
0x18009dc53  push    r14
0x18009dc55  push    r15
0x18009dc57  mov     rbp, rsp
0x18009dc5a  sub     rsp, 60h
0x18009dc5e  mov     rax, cs:__security_cookie
0x18009dc65  xor     rax, rsp
0x18009dc68  mov     [rbp+var_8], rax
0x18009dc6c  mov     r15d, r9d
0x18009dc6f  mov     r14d, r8d
0x18009dc72  mov     r12, rdx
0x18009dc75  mov     rdi, rcx
0x18009dc78  mov     rsi, qword ptr [rbp+arg_20]
0x18009dc7c  test    rcx, rcx
0x18009dc7f  jnz     short loc_18009DCA3
0x18009dc81  mov     edx, 316h; void *
0x18009dc86  mov     ebx, 80070057h
0x18009dc8b  mov     rcx, [rbp+38h]; this
0x18009dc8f  mov     r9d, ebx; char *
0x18009dc92  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x18009dc99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009dc9e  jmp     loc_18009DE16
0x18009dca3  cmp     r14d, 4
0x18009dca7  jb      short loc_18009DCB0
0x18009dca9  mov     edx, 317h
0x18009dcae  jmp     short loc_18009DC86
0x18009dcb0  test    rsi, rsi
0x18009dcb3  jnz     short loc_18009DCC1
0x18009dcb5  mov     ebx, 80004003h
0x18009dcba  mov     edx, 318h
0x18009dcbf  jmp     short loc_18009DC8B
0x18009dcc1  mov     dword ptr [rbp+var_3C], 0
0x18009dcc8  lea     rdx, [rbp+var_3C]; unsigned __int16 *
0x18009dccc  call    ?GetTimeoutUntilSyncFailure@FirstSync@@YAJPEBGPEAK@Z; FirstSync::GetTimeoutUntilSyncFailure(ushort const *,ulong *)
0x18009dcd1  mov     ebx, eax
0x18009dcd3  test    eax, eax
0x18009dcd5  jns     short loc_18009DCDE
0x18009dcd7  mov     edx, 31Bh
0x18009dcdc  jmp     short loc_18009DC8B
0x18009dcde  mov     [rbp+var_38], 0
0x18009dce5  mov     eax, dword ptr [rbp+var_3C]
0x18009dce8  imul    rcx, rax, 3Ch ; '<'; unsigned __int64
0x18009dcec  lea     rdx, [rbp+var_38]; unsigned int *
0x18009dcf0  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x18009dcf5  mov     ebx, eax
0x18009dcf7  test    eax, eax
0x18009dcf9  jns     short loc_18009DD02
0x18009dcfb  mov     edx, 31Eh
0x18009dd00  jmp     short loc_18009DC8B
0x18009dd02  mov     qword ptr [rbp+var_30], 0
0x18009dd0a  xor     edx, edx
0x18009dd0c  lea     rcx, [rbp+var_30]
0x18009dd10  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18009dd15  mov     r9d, 1; HKEY *
0x18009dd1b  lea     r8, [rbp+var_30]; unsigned __int16 *
0x18009dd1f  mov     rdx, r12; PCWSTR
0x18009dd22  mov     rcx, rdi; pszMore
0x18009dd25  call    ?GetFirstSyncKey@FirstSync@@YAJPEBG0PEAPEAUHKEY__@@H@Z; FirstSync::GetFirstSyncKey(ushort const *,ushort const *,HKEY__ * *,int)
0x18009dd2a  mov     ebx, eax
0x18009dd2c  test    eax, eax
0x18009dd2e  js      loc_18009DE0D
0x18009dd34  mov     [rbp+var_40], 0
0x18009dd3b  lea     rax, off_1800CD4E0; "Policy"
0x18009dd42  mov     rdx, [rax+r14*8]
0x18009dd46  lea     rcx, [rbp+var_28]
0x18009dd4a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009dd4f  nop
0x18009dd50  lea     rdx, aDuration; "Duration"
0x18009dd57  lea     rcx, [rbp+var_28]
0x18009dd5b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18009dd60  lea     rcx, [rbp+var_28]
0x18009dd64  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009dd69  mov     r8, rax
0x18009dd6c  lea     r9, [rbp+var_40]
0x18009dd70  xor     edx, edx
0x18009dd72  mov     rcx, qword ptr [rbp+var_30]
0x18009dd76  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x18009dd7c  mov     ebx, eax
0x18009dd7e  test    eax, eax
0x18009dd80  jns     short loc_18009DD8C
0x18009dd82  mov     r9d, eax
0x18009dd85  mov     edx, 327h
0x18009dd8a  jmp     short loc_18009DDF2
0x18009dd8c  mov     eax, [rbp+var_40]
0x18009dd8f  lea     r9d, [r15+rax]
0x18009dd93  cmp     r9d, eax
0x18009dd96  jb      short loc_18009DDDE
0x18009dd98  mov     [rbp+var_40], r9d
0x18009dd9c  lea     rcx, [rbp+var_28]
0x18009dda0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18009dda5  mov     r8, rax
0x18009dda8  xor     edx, edx
0x18009ddaa  mov     rcx, qword ptr [rbp+var_30]
0x18009ddae  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18009ddb4  mov     ebx, eax
0x18009ddb6  test    eax, eax
0x18009ddb8  jns     short loc_18009DDC4
0x18009ddba  mov     r9d, eax
0x18009ddbd  mov     edx, 329h
0x18009ddc2  jmp     short loc_18009DDF2
0x18009ddc4  xor     ecx, ecx
0x18009ddc6  mov     eax, [rbp+var_38]
0x18009ddc9  cmp     [rbp+var_40], eax
0x18009ddcc  setnb   cl
0x18009ddcf  mov     [rsi], ecx
0x18009ddd1  lea     rcx, [rbp+var_28]
0x18009ddd5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009ddda  xor     ebx, ebx
0x18009dddc  jmp     short loc_18009DE0D
0x18009ddde  mov     [rbp+var_40], 0FFFFFFFFh
0x18009dde5  mov     ebx, 80070216h
0x18009ddea  mov     r9d, ebx; char *
0x18009dded  mov     edx, 328h; void *
0x18009ddf2  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x18009ddf9  mov     rcx, [rbp+38h]; this
0x18009ddfd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009de02  nop
0x18009de03  lea     rcx, [rbp+var_28]
0x18009de07  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18009de0c  nop
0x18009de0d  lea     rcx, [rbp+var_30]
0x18009de11  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009de16  mov     eax, ebx
0x18009de18  mov     rcx, [rbp+var_8]
0x18009de1c  xor     rcx, rsp; StackCookie
0x18009de1f  call    __security_check_cookie
0x18009de24  add     rsp, 60h
0x18009de28  pop     r15
0x18009de2a  pop     r14
0x18009de2c  pop     r12
0x18009de2e  pop     rdi
0x18009de2f  pop     rsi
0x18009de30  pop     rbx
0x18009de31  pop     rbp
0x18009de32  retn
```
