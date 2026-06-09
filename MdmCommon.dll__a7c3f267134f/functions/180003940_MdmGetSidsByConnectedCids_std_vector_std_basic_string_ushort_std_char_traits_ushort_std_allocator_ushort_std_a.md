# MdmGetSidsByConnectedCids(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &)

- ea: `0x180003940`
- end: `0x180003a1f`
- name: `?MdmGetSidsByConnectedCids@@YAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@0@Z`
- size: `223`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001520`
- `0x180003940`
- `0x180006560`
- `0x1800065c0`
- `0x180016080`

## string_xrefs

- `0x1800039af`: `onecoreuap\shell\devicedirectory\mdmcommon\dll\dllmain.cpp`
- `0x1800039a0`: `CHR(MdmAccountHelper::GetSidsByConnectedCids(vCids, vSids))`

## pseudocode

```c
__int64 __fastcall MdmGetSidsByConnectedCids(__int64 *a1, __int64 *a2, __int64 a3)
{
  int v5; // edx
  int SidsByConnectedCids; // ebx
  __int64 v7; // r8
  __int64 v8; // rcx
  int v10; // [rsp+30h] [rbp-38h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v11; // [rsp+38h] [rbp-30h] BYREF
  int *v12; // [rsp+48h] [rbp-20h]
  __int64 v13; // [rsp+50h] [rbp-18h]

  if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer((__int64)a1, (const EVENT_DESCRIPTOR *)MDMCOMMON_SIDS_BY_CIDS, a3, 1u, &v11);
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
    McGenEventWrite_EventWriteTransfer(v8, (const EVENT_DESCRIPTOR *)MDMCOMMON_SIDS_BY_CIDS_RESULT, v7, 2u, &v11);
  }
  return (unsigned int)SidsByConnectedCids;
}

```

## disassembly

```asm
0x180003940  mov     [rsp+arg_10], rbx
0x180003945  push    rdi
0x180003946  sub     rsp, 60h
0x18000394a  mov     rax, cs:__security_cookie
0x180003951  xor     rax, rsp
0x180003954  mov     [rsp+68h+var_10], rax
0x180003959  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 2
0x180003960  mov     rdi, rdx
0x180003963  mov     rbx, rcx
0x180003966  jz      short loc_180003984
0x180003968  lea     rax, [rsp+68h+var_30]
0x18000396d  mov     r9d, 1
0x180003973  lea     rdx, MDMCOMMON_SIDS_BY_CIDS
0x18000397a  mov     [rsp+68h+var_48], rax
0x18000397f  call    McGenEventWrite_EventWriteTransfer
0x180003984  mov     rdx, rdi
0x180003987  mov     rcx, rbx
0x18000398a  call    ?GetSidsByConnectedCids@MdmAccountHelper@@SAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@0@Z; MdmAccountHelper::GetSidsByConnectedCids(std::vector<std::wstring> &,std::vector<std::wstring> &)
0x18000398f  mov     ebx, eax
0x180003991  test    eax, eax
0x180003993  jns     short loc_1800039C3
0x180003995  mov     ecx, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x18000399b  test    cl, 1
0x18000399e  jz      short loc_1800039C9
0x1800039a0  lea     rax, aChrMdmaccounth_2; "CHR(MdmAccountHelper::GetSidsByConnecte"...
0x1800039a7  mov     r8d, ebx
0x1800039aa  mov     [rsp+68h+var_40], rax
0x1800039af  lea     r9, aOnecoreuapShel_3; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x1800039b6  mov     dword ptr [rsp+68h+var_48], 320h
0x1800039be  call    McTemplateU0dsqs_EventWriteTransfer
0x1800039c3  mov     ecx, cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits
0x1800039c9  test    cl, 2
0x1800039cc  jz      short loc_180003A01
0x1800039ce  lea     rax, [rsp+68h+var_38]
0x1800039d3  mov     [rsp+68h+var_38], ebx
0x1800039d7  mov     [rsp+68h+var_20], rax
0x1800039dc  lea     rdx, MDMCOMMON_SIDS_BY_CIDS_RESULT
0x1800039e3  lea     rax, [rsp+68h+var_30]
0x1800039e8  mov     [rsp+68h+var_18], 4
0x1800039f1  mov     r9d, 2
0x1800039f7  mov     [rsp+68h+var_48], rax
0x1800039fc  call    McGenEventWrite_EventWriteTransfer
0x180003a01  mov     eax, ebx
0x180003a03  mov     rcx, [rsp+68h+var_10]
0x180003a08  xor     rcx, rsp; StackCookie
0x180003a0b  call    __security_check_cookie
0x180003a10  mov     rbx, [rsp+68h+arg_10]
0x180003a18  add     rsp, 60h
0x180003a1c  pop     rdi
0x180003a1d  retn
```
