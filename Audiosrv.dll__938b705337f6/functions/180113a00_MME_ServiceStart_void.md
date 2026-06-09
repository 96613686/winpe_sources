# MME_ServiceStart(void)

- ea: `0x180113a00`
- end: `0x180113acf`
- name: `?MME_ServiceStart@@YAJXZ`
- size: `207`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800f0be0`

## callees

- `0x180072450`
- `0x18011361c`
- `0x180113a00`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180113aa4`
- `ntdll!RtlAcquireResourceExclusive` at `0x180113aa4`
- `ntdll!RtlReleaseResource` at `0x180113ac7`
- `ntdll!RtlReleaseResource` at `0x180113ac7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180113a6f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180113a6f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180113a46`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180113a5e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180113a46`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180113a5e`

## pseudocode

```c
__int64 MME_ServiceStart(void)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_62e65b1aa5e43d79debbf88575ed7e0c_Traceguids);
  }
  if ( !ConvertStringSidToSidW(L"S-1-5-80-2676549577-1911656217-2625096541-4178041876-1366760775", &AudiosrvSid) )
    goto LABEL_8;
  if ( !ConvertStringSidToSidW(
          L"S-1-5-80-1580948945-3239616721-2529237571-3761093093-1214243633",
          &AudioEndpointBuilderSid) )
  {
    LocalFree(AudiosrvSid);
LABEL_8:
    AudiosrvSid = 0;
    AudioEndpointBuilderSid = 0;
    return 0;
  }
  if ( (unsigned int)InitializePnpInfo() )
  {
    RtlAcquireResourceExclusive(&PnpInfoResource, 1u);
    _InterlockedIncrement((volatile signed __int32 *)g_pPnpInfoShared + 1);
    _InterlockedIncrement((volatile signed __int32 *)g_pPnpInfoActual + 1);
    RtlReleaseResource(&PnpInfoResource);
  }
  return 0;
}

```

## disassembly

```asm
0x180113a00  sub     rsp, 28h
0x180113a04  mov     rcx, cs:WPP_GLOBAL_Control
0x180113a0b  lea     rax, WPP_GLOBAL_Control
0x180113a12  cmp     rcx, rax
0x180113a15  jz      short loc_180113A38
0x180113a17  test    byte ptr [rcx+1Ch], 20h
0x180113a1b  jz      short loc_180113A38
0x180113a1d  cmp     byte ptr [rcx+19h], 4
0x180113a21  jb      short loc_180113A38
0x180113a23  mov     rcx, [rcx+10h]
0x180113a27  lea     r8, WPP_62e65b1aa5e43d79debbf88575ed7e0c_Traceguids
0x180113a2e  mov     edx, 1Fh
0x180113a33  call    WPP_SF_
0x180113a38  lea     rdx, ?AudiosrvSid@@3PEAXEA; Sid
0x180113a3f  lea     rcx, StringSid; "S-1-5-80-2676549577-1911656217-26250965"...
0x180113a46  call    cs:__imp_ConvertStringSidToSidW
0x180113a4c  test    eax, eax
0x180113a4e  jz      short loc_180113A75
0x180113a50  lea     rdx, ?AudioEndpointBuilderSid@@3PEAXEA; Sid
0x180113a57  lea     rcx, aS1580158094894; "S-1-5-80-1580948945-3239616721-25292375"...
0x180113a5e  call    cs:__imp_ConvertStringSidToSidW
0x180113a64  test    eax, eax
0x180113a66  jnz     short loc_180113A92
0x180113a68  mov     rcx, cs:?AudiosrvSid@@3PEAXEA; hMem
0x180113a6f  call    cs:__imp_LocalFree
0x180113a75  mov     cs:?AudiosrvSid@@3PEAXEA, 0; void * AudiosrvSid
0x180113a80  mov     cs:?AudioEndpointBuilderSid@@3PEAXEA, 0; void * AudioEndpointBuilderSid
0x180113a8b  xor     eax, eax
0x180113a8d  add     rsp, 28h
0x180113a91  retn
0x180113a92  call    ?InitializePnpInfo@@YAHXZ; InitializePnpInfo(void)
0x180113a97  test    eax, eax
0x180113a99  jz      short loc_180113A8B
0x180113a9b  mov     dl, 1; Wait
0x180113a9d  lea     rcx, ?PnpInfoResource@@3U_RTL_RESOURCE@@A; Resource
0x180113aa4  call    cs:__imp_RtlAcquireResourceExclusive
0x180113aaa  mov     rax, cs:?g_pPnpInfoShared@@3PEAU_MMPNPINFO@@EA; _MMPNPINFO * g_pPnpInfoShared
0x180113ab1  lock inc dword ptr [rax+4]
0x180113ab5  mov     rax, cs:?g_pPnpInfoActual@@3PEAU_MMPNPINFO@@EA; _MMPNPINFO * g_pPnpInfoActual
0x180113abc  lock inc dword ptr [rax+4]
0x180113ac0  lea     rcx, ?PnpInfoResource@@3U_RTL_RESOURCE@@A; Resource
0x180113ac7  call    cs:__imp_RtlReleaseResource
0x180113acd  jmp     short loc_180113A8B
```
