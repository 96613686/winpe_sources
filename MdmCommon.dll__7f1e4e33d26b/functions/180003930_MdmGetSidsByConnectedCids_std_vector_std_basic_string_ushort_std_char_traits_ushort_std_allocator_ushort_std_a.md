# MdmGetSidsByConnectedCids(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x180003930`
- end: `0x180003a0e`
- name: `?MdmGetSidsByConnectedCids@@YAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@0@Z`
- size: `222`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001520`
- `0x180003930`
- `0x1800064f0`
- `0x180006548`
- `0x180015bf0`

## string_xrefs

- `0x18000399f`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x180003990`: `CHR(MdmAccountHelper::GetSidsByConnectedCids(vCids, vSids))`

## pseudocode

```c
__int64 __fastcall MdmGetSidsByConnectedCids(__int64 *a1, __int64 a2, __int64 a3)
{
  int v5; // edx
  int SidsByConnectedCids; // ebx
  __int64 v7; // r8
  __int64 v8; // rcx
  int v10; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v11[16]; // [rsp+38h] [rbp-30h] BYREF
  int *v12; // [rsp+48h] [rbp-20h]
  __int64 v13; // [rsp+50h] [rbp-18h]

  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(a1, MDMCOMMON_SIDS_BY_CIDS, a3, 1, v11);
  SidsByConnectedCids = MdmAccountHelper::GetSidsByConnectedCids(a1, a2);
  if ( SidsByConnectedCids < 0 )
  {
    v8 = (unsigned int)Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits;
    if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
      goto LABEL_7;
    McTemplateU0dsqs_EventWriteTransfer(
      Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits,
      v5,
      SidsByConnectedCids,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\dll\\dllmain.cpp",
      32,
      "CHR(MdmAccountHelper::GetSidsByConnectedCids(vCids, vSids))");
  }
  v8 = (unsigned int)Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits;
LABEL_7:
  if ( (v8 & 2) != 0 )
  {
    v10 = SidsByConnectedCids;
    v12 = &v10;
    v13 = 4;
    McGenEventWrite_EventWriteTransfer(v8, MDMCOMMON_SIDS_BY_CIDS_RESULT, v7, 2, v11);
  }
  return (unsigned int)SidsByConnectedCids;
}

```

## disassembly

```asm
0x180003930  mov     [rsp+arg_10], rbx
0x180003935  push    rdi
0x180003936  sub     rsp, 60h
0x18000393a  mov     rax, cs:__security_cookie
0x180003941  xor     rax, rsp
0x180003944  mov     [rsp+68h+var_10], rax
0x180003949  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x180003950  mov     rdi, rdx
0x180003953  mov     rbx, rcx
0x180003956  jz      short loc_180003974
0x180003958  lea     rax, [rsp+68h+var_30]
0x18000395d  mov     r9d, 1
0x180003963  lea     rdx, MDMCOMMON_SIDS_BY_CIDS
0x18000396a  mov     [rsp+68h+var_48], rax
0x18000396f  call    McGenEventWrite_EventWriteTransfer
0x180003974  mov     rdx, rdi
0x180003977  mov     rcx, rbx
0x18000397a  call    ?GetSidsByConnectedCids@MdmAccountHelper@@SAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@0@Z; MdmAccountHelper::GetSidsByConnectedCids(std::vector<std::wstring> &,std::vector<std::wstring> &)
0x18000397f  mov     ebx, eax
0x180003981  test    eax, eax
0x180003983  jns     short loc_1800039B3
0x180003985  mov     ecx, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x18000398b  test    cl, 1
0x18000398e  jz      short loc_1800039B9
0x180003990  lea     rax, aChrMdmaccounth_2; "CHR(MdmAccountHelper::GetSidsByConnecte"...
0x180003997  mov     r8d, ebx
0x18000399a  mov     [rsp+68h+var_40], rax
0x18000399f  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800039a6  mov     dword ptr [rsp+68h+var_48], 320h
0x1800039ae  call    McTemplateU0dsqs_EventWriteTransfer
0x1800039b3  mov     ecx, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x1800039b9  test    cl, 2
0x1800039bc  jz      short loc_1800039F1
0x1800039be  lea     rax, [rsp+68h+var_38]
0x1800039c3  mov     [rsp+68h+var_38], ebx
0x1800039c7  mov     [rsp+68h+var_20], rax
0x1800039cc  lea     rdx, MDMCOMMON_SIDS_BY_CIDS_RESULT
0x1800039d3  lea     rax, [rsp+68h+var_30]
0x1800039d8  mov     [rsp+68h+var_18], 4
0x1800039e1  mov     r9d, 2
0x1800039e7  mov     [rsp+68h+var_48], rax
0x1800039ec  call    McGenEventWrite_EventWriteTransfer
0x1800039f1  mov     eax, ebx
0x1800039f3  mov     rcx, [rsp+68h+var_10]
0x1800039f8  xor     rcx, rsp; StackCookie
0x1800039fb  call    __security_check_cookie
0x180003a00  mov     rbx, [rsp+68h+arg_10]
0x180003a08  add     rsp, 60h
0x180003a0c  pop     rdi
0x180003a0d  retn
```
