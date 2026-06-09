# FirstSync::ResetTimeOut(ushort const *,ushort const *)

- ea: `0x1800a1838`
- end: `0x1800a1969`
- name: `?ResetTimeOut@FirstSync@@YAJPEBG0@Z`
- size: `305`
- prototype: `__int64 __fastcall(PCWSTR pszMore, PCWSTR, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800330c0`

## callees

- `0x18000a5c4`
- `0x180016698`
- `0x180017118`
- `0x180095238`
- `0x1800a0060`
- `0x1800a0df4`
- `0x1800a1838`

## import_xrefs

- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x1800a1904`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x1800a1931`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x1800a1904`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x1800a1931`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FirstSync::ResetTimeOut(PCWSTR pszMore, PCWSTR a2, const unsigned __int16 *a3)
{
  unsigned int v5; // ebx
  int FirstSyncKey; // eax
  int v7; // r9d
  __int64 v8; // rdx
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  HKEY v12; // [rsp+30h] [rbp+8h] BYREF

  if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x40) != 0 )
    McTemplateU0zz_EventWriteTransfer(pszMore, a2, pszMore, a2);
  if ( pszMore )
  {
    v12 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &v12,
      0);
    FirstSyncKey = FirstSync::GetFirstSyncKey(pszMore, a2, (unsigned __int16 *)&v12, (HKEY *)1);
    v5 = FirstSyncKey;
    if ( FirstSyncKey >= 0 )
    {
      FirstSyncKey = FirstSync::InitializeAllResourceTimeoutCounters(pszMore, a2, (const unsigned __int16 *)1, v7);
      v5 = FirstSyncKey;
      if ( FirstSyncKey >= 0 )
      {
        FirstSyncKey = OmaDmRegistrySetDWORD(v12, 0, L"IsSyncDone", 0);
        v5 = FirstSyncKey;
        if ( FirstSyncKey >= 0 )
        {
          FirstSyncKey = OmaDmRegistrySetDWORD(v12, 0, L"ProvisioningStatus", 2u);
          v5 = FirstSyncKey;
          if ( FirstSyncKey >= 0 )
          {
            v5 = 0;
            goto LABEL_15;
          }
          v8 = 932;
        }
        else
        {
          v8 = 931;
        }
      }
      else
      {
        v8 = 930;
      }
    }
    else
    {
      v8 = 929;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
      (const char *)(unsigned int)FirstSyncKey,
      v10);
LABEL_15:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v12);
    return v5;
  }
  v5 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x39F,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctools.cpp",
    (const char *)0x80070057LL,
    v10);
  return v5;
}

```

## disassembly

```asm
0x1800a1838  mov     [rsp+arg_8], rbx
0x1800a183d  mov     [rsp+arg_10], rsi
0x1800a1842  push    rdi; int
0x1800a1843  sub     rsp, 20h
0x1800a1847  mov     rsi, rdx
0x1800a184a  mov     rdi, rcx
0x1800a184d  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 40h
0x1800a1854  jz      short loc_1800A1861
0x1800a1856  mov     r9, rdx
0x1800a1859  mov     r8, rcx
0x1800a185c  call    McTemplateU0zz_EventWriteTransfer
0x1800a1861  test    rdi, rdi
0x1800a1864  jnz     short loc_1800A1889
0x1800a1866  mov     rcx, [rsp+28h]; this
0x1800a186b  mov     ebx, 80070057h
0x1800a1870  mov     r9d, ebx; char *
0x1800a1873  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a187a  mov     edx, 39Fh; void *
0x1800a187f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a1884  jmp     loc_1800A1956
0x1800a1889  mov     [rsp+28h+arg_0], 0
0x1800a1892  xor     edx, edx
0x1800a1894  lea     rcx, [rsp+28h+arg_0]
0x1800a1899  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800a189e  mov     r9d, 1; HKEY *
0x1800a18a4  lea     r8, [rsp+28h+arg_0]; unsigned __int16 *
0x1800a18a9  mov     rdx, rsi; PCWSTR
0x1800a18ac  mov     rcx, rdi; pszMore
0x1800a18af  call    ?GetFirstSyncKey@FirstSync@@YAJPEBG0PEAPEAUHKEY__@@H@Z; FirstSync::GetFirstSyncKey(ushort const *,ushort const *,HKEY__ * *,int)
0x1800a18b4  mov     ebx, eax
0x1800a18b6  test    eax, eax
0x1800a18b8  jns     short loc_1800A18C1
0x1800a18ba  mov     edx, 3A1h
0x1800a18bf  jmp     short loc_1800A18DD
0x1800a18c1  mov     r8d, 1; unsigned __int16 *
0x1800a18c7  mov     rdx, rsi; PCWSTR
0x1800a18ca  mov     rcx, rdi; pszMore
0x1800a18cd  call    ?InitializeAllResourceTimeoutCounters@FirstSync@@YAJPEBG0H@Z; FirstSync::InitializeAllResourceTimeoutCounters(ushort const *,ushort const *,int)
0x1800a18d2  mov     ebx, eax
0x1800a18d4  test    eax, eax
0x1800a18d6  jns     short loc_1800A18F3
0x1800a18d8  mov     edx, 3A2h; void *
0x1800a18dd  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a18e4  mov     r9d, eax; char *
0x1800a18e7  mov     rcx, [rsp+28h]; this
0x1800a18ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a18f1  jmp     short loc_1800A194C
0x1800a18f3  xor     r9d, r9d
0x1800a18f6  lea     r8, aIssyncdone; "IsSyncDone"
0x1800a18fd  xor     edx, edx
0x1800a18ff  mov     rcx, [rsp+28h+arg_0]
0x1800a1904  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800a190b  nop     dword ptr [rax+rax+00h]
0x1800a1910  mov     ebx, eax
0x1800a1912  test    eax, eax
0x1800a1914  jns     short loc_1800A191D
0x1800a1916  mov     edx, 3A3h
0x1800a191b  jmp     short loc_1800A18DD
0x1800a191d  mov     r9d, 2
0x1800a1923  lea     r8, aProvisioningst; "ProvisioningStatus"
0x1800a192a  xor     edx, edx
0x1800a192c  mov     rcx, [rsp+28h+arg_0]
0x1800a1931  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800a1938  nop     dword ptr [rax+rax+00h]
0x1800a193d  mov     ebx, eax
0x1800a193f  test    eax, eax
0x1800a1941  jns     short loc_1800A194A
0x1800a1943  mov     edx, 3A4h
0x1800a1948  jmp     short loc_1800A18DD
0x1800a194a  xor     ebx, ebx
0x1800a194c  lea     rcx, [rsp+28h+arg_0]
0x1800a1951  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a1956  mov     eax, ebx
0x1800a1958  mov     rbx, [rsp+28h+arg_8]
0x1800a195d  mov     rsi, [rsp+28h+arg_10]
0x1800a1962  add     rsp, 20h
0x1800a1966  pop     rdi
0x1800a1967  retn
```
