# FirstSync::SetStartTimeIfEmpty(ushort const *,ushort const *)

- ea: `0x1800a1d24`
- end: `0x1800a1e3d`
- name: `?SetStartTimeIfEmpty@FirstSync@@YAJPEBG0@Z`
- size: `281`
- prototype: `__int64 __fastcall(PCWSTR pszMore, PCWSTR, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18002430c`
- `0x1800a73f8`

## callees

- `0x18000a5c4`
- `0x180016698`
- `0x180017118`
- `0x1800a0060`
- `0x1800a0720`
- `0x1800a1d24`
- `0x1800a2090`

## import_xrefs

- `DMCmnUtils!OmaDmRegistrySetBinary` at `0x1800a1df6`
- `DMCmnUtils!OmaDmRegistrySetBinary` at `0x1800a1df6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a1dbc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a1dbc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FirstSync::SetStartTimeIfEmpty(PCWSTR pszMore, PCWSTR a2, const unsigned __int16 *a3)
{
  unsigned int v5; // ebx
  int FirstSyncKey; // eax
  unsigned __int64 *v7; // r9
  __int64 v8; // rdx
  const struct _FILETIME *v9; // rdx
  int v11; // [rsp+20h] [rbp-20h]
  unsigned __int64 v12; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  HKEY v14; // [rsp+60h] [rbp+20h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+70h] [rbp+30h] BYREF
  __int64 v16; // [rsp+78h] [rbp+38h] BYREF

  if ( pszMore )
  {
    v14 = 0;
    v16 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &v14,
      0);
    FirstSyncKey = FirstSync::GetFirstSyncKey(pszMore, a2, (unsigned __int16 *)&v14, (HKEY *)1);
    v5 = FirstSyncKey;
    if ( FirstSyncKey >= 0 )
    {
      if ( (int)FirstSync::GetStartTime(pszMore, a2, (const unsigned __int16 *)&v16, v7) >= 0
        || (SystemTimeAsFileTime = 0,
            GetSystemTimeAsFileTime(&SystemTimeAsFileTime),
            v12 = wil::FileTime::ToInt64((wil::FileTime *)&SystemTimeAsFileTime, v9),
            FirstSyncKey = OmaDmRegistrySetBinary(v14, 0, L"Timestamp", &v12, 8u),
            v5 = FirstSyncKey,
            FirstSyncKey >= 0) )
      {
        v5 = 0;
        goto LABEL_10;
      }
      v8 = 887;
    }
    else
    {
      v8 = 882;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
      (const char *)(unsigned int)FirstSyncKey,
      v11);
LABEL_10:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v14);
    return v5;
  }
  v5 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x36E,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
    (const char *)0x80070057LL,
    v11);
  return v5;
}

```

## disassembly

```asm
0x1800a1d24  mov     [rsp-18h+arg_8], rbx
0x1800a1d29  push    rbp
0x1800a1d2a  push    rsi
0x1800a1d2b  push    rdi
0x1800a1d2c  mov     rbp, rsp
0x1800a1d2f  sub     rsp, 40h
0x1800a1d33  mov     rsi, rdx
0x1800a1d36  mov     rdi, rcx
0x1800a1d39  test    rcx, rcx
0x1800a1d3c  jnz     short loc_1800A1D60
0x1800a1d3e  mov     rcx, [rbp+18h]; this
0x1800a1d42  mov     ebx, 80070057h
0x1800a1d47  mov     r9d, ebx; char *
0x1800a1d4a  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a1d51  mov     edx, 36Eh; void *
0x1800a1d56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a1d5b  jmp     loc_1800A1E2D
0x1800a1d60  mov     [rbp+arg_0], 0
0x1800a1d68  mov     [rbp+arg_18], 0
0x1800a1d70  xor     edx, edx
0x1800a1d72  lea     rcx, [rbp+arg_0]
0x1800a1d76  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800a1d7b  mov     r9d, 1; HKEY *
0x1800a1d81  lea     r8, [rbp+arg_0]; unsigned __int16 *
0x1800a1d85  mov     rdx, rsi; PCWSTR
0x1800a1d88  mov     rcx, rdi; pszMore
0x1800a1d8b  call    ?GetFirstSyncKey@FirstSync@@YAJPEBG0PEAPEAUHKEY__@@H@Z; FirstSync::GetFirstSyncKey(ushort const *,ushort const *,HKEY__ * *,int)
0x1800a1d90  mov     ebx, eax
0x1800a1d92  test    eax, eax
0x1800a1d94  jns     short loc_1800A1D9D
0x1800a1d96  mov     edx, 372h
0x1800a1d9b  jmp     short loc_1800A1E0D
0x1800a1d9d  lea     r8, [rbp+arg_18]; unsigned __int16 *
0x1800a1da1  mov     rdx, rsi; PCWSTR
0x1800a1da4  mov     rcx, rdi; pszMore
0x1800a1da7  call    ?GetStartTime@FirstSync@@YAJPEBG0PEA_K@Z; FirstSync::GetStartTime(ushort const *,ushort const *,unsigned __int64 *)
0x1800a1dac  test    eax, eax
0x1800a1dae  jns     short loc_1800A1E22
0x1800a1db0  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800a1db8  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800a1dbc  call    cs:__imp_GetSystemTimeAsFileTime
0x1800a1dc3  nop     dword ptr [rax+rax+00h]
0x1800a1dc8  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800a1dcc  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800a1dd0  lea     rcx, [rbp+SystemTimeAsFileTime]; this
0x1800a1dd4  call    ?ToInt64@FileTime@wil@@YA_KAEBU_FILETIME@@@Z; wil::FileTime::ToInt64(_FILETIME const &)
0x1800a1dd9  mov     [rbp+var_10], rax
0x1800a1ddd  mov     [rsp+40h+var_20], 8; int
0x1800a1de5  lea     r9, [rbp+var_10]
0x1800a1de9  lea     r8, aTimestamp; "Timestamp"
0x1800a1df0  xor     edx, edx
0x1800a1df2  mov     rcx, [rbp+arg_0]
0x1800a1df6  call    cs:__imp_?OmaDmRegistrySetBinary@@YAJPEAUHKEY__@@PEBG1PEAXK@Z; OmaDmRegistrySetBinary(HKEY__ *,ushort const *,ushort const *,void *,ulong)
0x1800a1dfd  nop     dword ptr [rax+rax+00h]
0x1800a1e02  mov     ebx, eax
0x1800a1e04  test    eax, eax
0x1800a1e06  jns     short loc_1800A1E22
0x1800a1e08  mov     edx, 377h; void *
0x1800a1e0d  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a1e14  mov     r9d, eax; char *
0x1800a1e17  mov     rcx, [rbp+18h]; this
0x1800a1e1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a1e20  jmp     short loc_1800A1E24
0x1800a1e22  xor     ebx, ebx
0x1800a1e24  lea     rcx, [rbp+arg_0]
0x1800a1e28  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a1e2d  mov     eax, ebx
0x1800a1e2f  mov     rbx, [rsp+40h+arg_8]
0x1800a1e34  add     rsp, 40h
0x1800a1e38  pop     rdi
0x1800a1e39  pop     rsi
0x1800a1e3a  pop     rbp
0x1800a1e3b  retn
```
