# MME_ServiceStart(void)

- ea: `0x180113c80`
- end: `0x180113d4f`
- name: `?MME_ServiceStart@@YAJXZ`
- size: `207`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800f03f0`

## callees

- `0x180071f50`
- `0x18011389c`
- `0x180113c80`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180113d24`
- `ntdll!RtlAcquireResourceExclusive` at `0x180113d24`
- `ntdll!RtlReleaseResource` at `0x180113d47`
- `ntdll!RtlReleaseResource` at `0x180113d47`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180113cef`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180113cef`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180113cc6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180113cde`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180113cc6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180113cde`

## pseudocode

```c
__int64 MME_ServiceStart(void)
{
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_62e65b1aa5e43d79debbf88575ed7e0c_Traceguids);
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
0x180113c80  sub     rsp, 28h
0x180113c84  mov     rcx, cs:WPP_GLOBAL_Control
0x180113c8b  lea     rax, WPP_GLOBAL_Control
0x180113c92  cmp     rcx, rax
0x180113c95  jz      short loc_180113CB8
0x180113c97  test    byte ptr [rcx+1Ch], 20h
0x180113c9b  jz      short loc_180113CB8
0x180113c9d  cmp     byte ptr [rcx+19h], 4
0x180113ca1  jb      short loc_180113CB8
0x180113ca3  mov     rcx, [rcx+10h]
0x180113ca7  lea     r8, WPP_62e65b1aa5e43d79debbf88575ed7e0c_Traceguids
0x180113cae  mov     edx, 1Fh
0x180113cb3  call    WPP_SF_
0x180113cb8  lea     rdx, ?AudiosrvSid@@3PEAXEA; Sid
0x180113cbf  lea     rcx, StringSid; "S-1-5-80-2676549577-1911656217-26250965"...
0x180113cc6  call    cs:__imp_ConvertStringSidToSidW
0x180113ccc  test    eax, eax
0x180113cce  jz      short loc_180113CF5
0x180113cd0  lea     rdx, ?AudioEndpointBuilderSid@@3PEAXEA; Sid
0x180113cd7  lea     rcx, aS1580158094894; "S-1-5-80-1580948945-3239616721-25292375"...
0x180113cde  call    cs:__imp_ConvertStringSidToSidW
0x180113ce4  test    eax, eax
0x180113ce6  jnz     short loc_180113D12
0x180113ce8  mov     rcx, cs:?AudiosrvSid@@3PEAXEA; hMem
0x180113cef  call    cs:__imp_LocalFree
0x180113cf5  mov     cs:?AudiosrvSid@@3PEAXEA, 0; void * AudiosrvSid
0x180113d00  mov     cs:?AudioEndpointBuilderSid@@3PEAXEA, 0; void * AudioEndpointBuilderSid
0x180113d0b  xor     eax, eax
0x180113d0d  add     rsp, 28h
0x180113d11  retn
0x180113d12  call    ?InitializePnpInfo@@YAHXZ; InitializePnpInfo(void)
0x180113d17  test    eax, eax
0x180113d19  jz      short loc_180113D0B
0x180113d1b  mov     dl, 1; Wait
0x180113d1d  lea     rcx, ?PnpInfoResource@@3U_RTL_RESOURCE@@A; Resource
0x180113d24  call    cs:__imp_RtlAcquireResourceExclusive
0x180113d2a  mov     rax, cs:?g_pPnpInfoShared@@3PEAU_MMPNPINFO@@EA; _MMPNPINFO * g_pPnpInfoShared
0x180113d31  lock inc dword ptr [rax+4]
0x180113d35  mov     rax, cs:?g_pPnpInfoActual@@3PEAU_MMPNPINFO@@EA; _MMPNPINFO * g_pPnpInfoActual
0x180113d3c  lock inc dword ptr [rax+4]
0x180113d40  lea     rcx, ?PnpInfoResource@@3U_RTL_RESOURCE@@A; Resource
0x180113d47  call    cs:__imp_RtlReleaseResource
0x180113d4d  jmp     short loc_180113D0B
```
