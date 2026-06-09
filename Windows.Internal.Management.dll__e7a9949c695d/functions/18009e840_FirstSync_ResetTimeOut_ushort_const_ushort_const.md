# FirstSync::ResetTimeOut(ushort const *,ushort const *)

- ea: `0x18009e840`
- end: `0x18009e964`
- name: `?ResetTimeOut@FirstSync@@YAJPEBG0@Z`
- size: `292`
- prototype: `__int64 __fastcall(PCWSTR pszMore, PCWSTR, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180034070`

## callees

- `0x18000a2a4`
- `0x180015f70`
- `0x1800169b8`
- `0x180092ad8`
- `0x18009d138`
- `0x18009de3c`
- `0x18009e840`

## import_xrefs

- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x18009e90c`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x18009e933`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x18009e90c`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x18009e933`

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
0x18009e840  mov     [rsp+arg_8], rbx
0x18009e845  mov     [rsp+arg_10], rsi
0x18009e84a  push    rdi; int
0x18009e84b  sub     rsp, 20h
0x18009e84f  mov     rsi, rdx
0x18009e852  mov     rdi, rcx
0x18009e855  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 40h
0x18009e85c  jz      short loc_18009E869
0x18009e85e  mov     r9, rdx
0x18009e861  mov     r8, rcx
0x18009e864  call    McTemplateU0zz_EventWriteTransfer
0x18009e869  test    rdi, rdi
0x18009e86c  jnz     short loc_18009E891
0x18009e86e  mov     rcx, [rsp+28h]; this
0x18009e873  mov     ebx, 80070057h
0x18009e878  mov     r9d, ebx; char *
0x18009e87b  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x18009e882  mov     edx, 39Fh; void *
0x18009e887  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009e88c  jmp     loc_18009E952
0x18009e891  mov     [rsp+28h+arg_0], 0
0x18009e89a  xor     edx, edx
0x18009e89c  lea     rcx, [rsp+28h+arg_0]
0x18009e8a1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18009e8a6  mov     r9d, 1; HKEY *
0x18009e8ac  lea     r8, [rsp+28h+arg_0]; unsigned __int16 *
0x18009e8b1  mov     rdx, rsi; PCWSTR
0x18009e8b4  mov     rcx, rdi; pszMore
0x18009e8b7  call    ?GetFirstSyncKey@FirstSync@@YAJPEBG0PEAPEAUHKEY__@@H@Z; FirstSync::GetFirstSyncKey(ushort const *,ushort const *,HKEY__ * *,int)
0x18009e8bc  mov     ebx, eax
0x18009e8be  test    eax, eax
0x18009e8c0  jns     short loc_18009E8C9
0x18009e8c2  mov     edx, 3A1h
0x18009e8c7  jmp     short loc_18009E8E5
0x18009e8c9  mov     r8d, 1; unsigned __int16 *
0x18009e8cf  mov     rdx, rsi; PCWSTR
0x18009e8d2  mov     rcx, rdi; pszMore
0x18009e8d5  call    ?InitializeAllResourceTimeoutCounters@FirstSync@@YAJPEBG0H@Z; FirstSync::InitializeAllResourceTimeoutCounters(ushort const *,ushort const *,int)
0x18009e8da  mov     ebx, eax
0x18009e8dc  test    eax, eax
0x18009e8de  jns     short loc_18009E8FB
0x18009e8e0  mov     edx, 3A2h; void *
0x18009e8e5  lea     r8, aOnecoreuapAdmi_40; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x18009e8ec  mov     r9d, eax; char *
0x18009e8ef  mov     rcx, [rsp+28h]; this
0x18009e8f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009e8f9  jmp     short loc_18009E948
0x18009e8fb  xor     r9d, r9d
0x18009e8fe  lea     r8, aIssyncdone; "IsSyncDone"
0x18009e905  xor     edx, edx
0x18009e907  mov     rcx, [rsp+28h+arg_0]
0x18009e90c  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18009e912  mov     ebx, eax
0x18009e914  test    eax, eax
0x18009e916  jns     short loc_18009E91F
0x18009e918  mov     edx, 3A3h
0x18009e91d  jmp     short loc_18009E8E5
0x18009e91f  mov     r9d, 2
0x18009e925  lea     r8, aProvisioningst; "ProvisioningStatus"
0x18009e92c  xor     edx, edx
0x18009e92e  mov     rcx, [rsp+28h+arg_0]
0x18009e933  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18009e939  mov     ebx, eax
0x18009e93b  test    eax, eax
0x18009e93d  jns     short loc_18009E946
0x18009e93f  mov     edx, 3A4h
0x18009e944  jmp     short loc_18009E8E5
0x18009e946  xor     ebx, ebx
0x18009e948  lea     rcx, [rsp+28h+arg_0]
0x18009e94d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009e952  mov     eax, ebx
0x18009e954  mov     rbx, [rsp+28h+arg_8]
0x18009e959  mov     rsi, [rsp+28h+arg_10]
0x18009e95e  add     rsp, 20h
0x18009e962  pop     rdi
0x18009e963  retn
```
