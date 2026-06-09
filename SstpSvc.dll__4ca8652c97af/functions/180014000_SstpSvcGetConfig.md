# SstpSvcGetConfig

- ea: `0x180014000`
- end: `0x18001416a`
- name: `SstpSvcGetConfig`
- size: `362`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000827c`
- `0x180008360`
- `0x180014000`
- `0x18001bcba`
- `0x18001bcf0`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x1800140f5`
- `RPCRT4!RpcRevertToSelf` at `0x1800140f5`
- `RPCRT4!RpcImpersonateClient` at `0x180014058`
- `RPCRT4!RpcImpersonateClient` at `0x180014058`
- `sstpcfg!GetSstpProxyConfig` at `0x1800140b4`
- `sstpcfg!GetSstpProxyConfig` at `0x1800140b4`
- `sstpcfg!GetSstpConfiguration` at `0x1800140c6`
- `sstpcfg!GetSstpConfiguration` at `0x1800140c6`

## string_xrefs

- `0x18001410a`: `SstpSvcGetConfig: FATAL ERROR. RpcRevertToSelf failed with error %d`
- `0x180014073`: `SstpSvcGetConfig: RpcImpersonateClient failed with error %d`
- `0x1800140dd`: `SstpSvcGetConfig: GetSstpConfiguration failed with error %d`

## pseudocode

```c
__int64 __fastcall SstpSvcGetConfig(__int64 a1, __int64 a2)
{
  unsigned int v3; // eax
  unsigned int SstpConfiguration; // ebx
  int v6; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v7[2044]; // [rsp+24h] [rbp-DCh] BYREF

  v6 = 0;
  memset_0(v7, 0, sizeof(v7));
  *(_OWORD *)a2 = 0;
  *(_OWORD *)(a2 + 16) = 0;
  *(_QWORD *)(a2 + 32) = 0;
  v3 = RpcImpersonateClient(0);
  SstpConfiguration = v3;
  if ( v3 )
  {
    if ( (byte_18002D803 & 8) == 0 )
      goto LABEL_10;
    LOWORD(v6) = 0;
    FormatRRASErrorString(&v6, L"SstpSvcGetConfig: RpcImpersonateClient failed with error %d", v3);
    goto LABEL_4;
  }
  GetSstpProxyConfig(0, a2);
  SstpConfiguration = GetSstpConfiguration(0, 0, a2 + 16, a2 + 4, v6);
  if ( !SstpConfiguration )
  {
    *(_DWORD *)(a2 + 8) = 32780;
    goto LABEL_10;
  }
  if ( (byte_18002D803 & 8) != 0 )
  {
    LOWORD(v6) = 0;
    FormatRRASErrorString(&v6, L"SstpSvcGetConfig: GetSstpConfiguration failed with error %d", SstpConfiguration);
LABEL_4:
    if ( (byte_18002D803 & 8) != 0 )
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v6);
  }
LABEL_10:
  if ( RpcRevertToSelf() )
  {
    if ( (byte_18002D803 & 8) != 0 )
    {
      LOWORD(v6) = 0;
      FormatRRASErrorString(
        &v6,
        L"SstpSvcGetConfig: FATAL ERROR. RpcRevertToSelf failed with error %d",
        SstpConfiguration);
      if ( (byte_18002D803 & 8) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasSSTPSvcTraceError, &v6);
    }
  }
  return SstpConfiguration;
}

```

## disassembly

```asm
0x180014000  mov     [rsp-8+arg_0], rbx
0x180014005  mov     [rsp-8+arg_10], rdi
0x18001400a  push    rbp
0x18001400b  lea     rbp, [rsp-730h]
0x180014013  sub     rsp, 830h
0x18001401a  mov     rax, cs:__security_cookie
0x180014021  xor     rax, rsp
0x180014024  mov     [rbp+730h+var_10], rax
0x18001402b  mov     rdi, rdx
0x18001402e  lea     rcx, [rsp+830h+var_80C]; void *
0x180014033  xor     eax, eax
0x180014035  xor     edx, edx; Val
0x180014037  mov     r8d, 7FCh; Size
0x18001403d  mov     [rsp+830h+var_810], eax
0x180014041  call    memset_0
0x180014046  xorps   xmm0, xmm0
0x180014049  xor     eax, eax
0x18001404b  movups  xmmword ptr [rdi], xmm0
0x18001404e  xor     ecx, ecx; BindingHandle
0x180014050  movups  xmmword ptr [rdi+10h], xmm0
0x180014054  mov     [rdi+20h], rax
0x180014058  call    cs:__imp_RpcImpersonateClient
0x18001405e  mov     ebx, eax
0x180014060  test    eax, eax
0x180014062  jz      short loc_1800140AF
0x180014064  test    cs:byte_18002D803, 8
0x18001406b  jz      loc_1800140F5
0x180014071  xor     ecx, ecx
0x180014073  lea     rdx, aSstpsvcgetconf_1; "SstpSvcGetConfig: RpcImpersonateClient "...
0x18001407a  mov     word ptr [rsp+830h+var_810], cx
0x18001407f  mov     r8d, eax
0x180014082  lea     rcx, [rsp+830h+var_810]
0x180014087  call    FormatRRASErrorString
0x18001408c  test    cs:byte_18002D803, 8
0x180014093  jz      short loc_1800140F5
0x180014095  lea     r8, [rsp+830h+var_810]
0x18001409a  lea     rdx, RasSSTPSvcTraceError
0x1800140a1  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800140a8  call    McTemplateU0z_EventWriteTransfer
0x1800140ad  jmp     short loc_1800140F5
0x1800140af  mov     rdx, rdi
0x1800140b2  xor     ecx, ecx
0x1800140b4  call    cs:__imp_GetSstpProxyConfig
0x1800140ba  lea     r9, [rdi+4]
0x1800140be  xor     edx, edx
0x1800140c0  lea     r8, [rdi+10h]
0x1800140c4  xor     ecx, ecx
0x1800140c6  call    cs:__imp_GetSstpConfiguration
0x1800140cc  mov     ebx, eax
0x1800140ce  test    eax, eax
0x1800140d0  jz      short loc_1800140EE
0x1800140d2  test    cs:byte_18002D803, 8
0x1800140d9  jz      short loc_1800140F5
0x1800140db  xor     eax, eax
0x1800140dd  lea     rdx, aSstpsvcgetconf; "SstpSvcGetConfig: GetSstpConfiguration "...
0x1800140e4  mov     word ptr [rsp+830h+var_810], ax
0x1800140e9  mov     r8d, ebx
0x1800140ec  jmp     short loc_180014082
0x1800140ee  mov     dword ptr [rdi+8], 800Ch
0x1800140f5  call    cs:__imp_RpcRevertToSelf
0x1800140fb  test    eax, eax
0x1800140fd  jz      short loc_180014144
0x1800140ff  test    cs:byte_18002D803, 8
0x180014106  jz      short loc_180014144
0x180014108  xor     eax, eax
0x18001410a  lea     rdx, aSstpsvcgetconf_0; "SstpSvcGetConfig: FATAL ERROR. RpcRever"...
0x180014111  mov     r8d, ebx
0x180014114  mov     word ptr [rsp+830h+var_810], ax
0x180014119  lea     rcx, [rsp+830h+var_810]
0x18001411e  call    FormatRRASErrorString
0x180014123  test    cs:byte_18002D803, 8
0x18001412a  jz      short loc_180014144
0x18001412c  lea     r8, [rsp+830h+var_810]
0x180014131  lea     rdx, RasSSTPSvcTraceError
0x180014138  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001413f  call    McTemplateU0z_EventWriteTransfer
0x180014144  mov     eax, ebx
0x180014146  mov     rcx, [rbp+730h+var_10]
0x18001414d  xor     rcx, rsp; StackCookie
0x180014150  call    __security_check_cookie
0x180014155  lea     r11, [rsp+830h+var_s0]
0x18001415d  mov     rbx, [r11+10h]
0x180014161  mov     rdi, [r11+20h]
0x180014165  mov     rsp, r11
0x180014168  pop     rbp
0x180014169  retn
```
