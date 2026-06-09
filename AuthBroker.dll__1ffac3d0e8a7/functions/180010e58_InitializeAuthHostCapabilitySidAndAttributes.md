# _InitializeAuthHostCapabilitySidAndAttributes

- ea: `0x180010e58`
- end: `0x18001102c`
- name: `_InitializeAuthHostCapabilitySidAndAttributes`
- size: `468`
- prototype: `HRESULT __fastcall(unsigned int brokerFlags, unsigned int enablePrivateNetwork, _SID_AND_ATTRIBUTES *capabilitySidAndAttributes, unsigned int *capabilityCount)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000ed84`
- `0x180010494`

## callees

- `0x1800109b8`
- `0x180010e58`
- `0x180020520`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010f0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010fd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010f0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010fd9`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180010fcf`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x180010fcf`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180010f9b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180010f9b`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180010f03`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180010f03`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180010fc0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180010fc0`
- `ntdll!RtlAllocateAndInitializeSidEx` at `0x180010fb0`
- `ntdll!RtlAllocateAndInitializeSidEx` at `0x180010fb0`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x180010f77`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x180010f77`
- `ntdll!RtlInitUnicodeString` at `0x180010f64`
- `ntdll!RtlInitUnicodeString` at `0x180010f64`

## pseudocode

```c
__int64 __fastcall InitializeAuthHostCapabilitySidAndAttributes(
        unsigned int brokerFlags,
        unsigned int enablePrivateNetwork,
        _SID_AND_ATTRIBUTES *capabilitySidAndAttributes,
        unsigned int *capabilityCount)
{
  int v6; // edi
  __int64 v7; // rbx
  unsigned int v8; // esi
  _SID_AND_ATTRIBUTES *pSid; // r14
  DWORD v10; // r9d
  signed int LastError; // eax
  unsigned int v12; // esi
  _SID_AND_ATTRIBUTES *v13; // rbx
  int v14; // eax
  __int64 v15; // rdx
  void *Sid; // rbx
  DWORD LengthSid; // eax
  signed int v18; // eax
  _UNICODE_STRING CapNameString; // [rsp+60h] [rbp-A0h] BYREF
  _SID_IDENTIFIER_AUTHORITY appAuthority; // [rsp+70h] [rbp-90h] BYREF
  unsigned int authorities[15]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int8 SidBuffer[48]; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int8 GroupSidBuffer[44]; // [rsp+E8h] [rbp-18h] BYREF

  *(_WORD *)&appAuthority.Value[4] = 3840;
  *(_DWORD *)appAuthority.Value = 0;
  v6 = 0;
  if ( (brokerFlags & 0x100000) != 0 )
    v7 = 4;
  else
    v7 = (unsigned int)(enablePrivateNetwork != 0) + 2;
  v8 = 0;
  do
  {
    pSid = &capabilitySidAndAttributes[v8];
    v10 = AuthHostBuiltInCapabilities[v8];
    pSid->Attributes = 4;
    if ( !AllocateAndInitializeSid(&appAuthority, 2u, 3u, v10, 0, 0, 0, 0, 0, 0, &pSid->Sid) )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      pSid->Sid = 0;
    }
    ++v8;
  }
  while ( v8 < (unsigned int)v7 );
  v12 = v7 + 1;
  *(_OWORD *)&authorities[8] = 0;
  v13 = &capabilitySidAndAttributes[v7];
  CapNameString = 0;
  *(_OWORD *)authorities = 0;
  v13->Attributes = 4;
  *(_OWORD *)&authorities[4] = 0;
  *(_OWORD *)&authorities[11] = 0;
  RtlInitUnicodeString(&CapNameString, AuthHostNameCapabilities[0]);
  v14 = RtlDeriveCapabilitySidsFromName(&CapNameString, GroupSidBuffer, SidBuffer);
  if ( v14 < 0
    || (*(_DWORD *)appAuthority.Value = 0,
        *(_WORD *)&appAuthority.Value[4] = 0,
        LOBYTE(v15) = *GetSidSubAuthorityCount(SidBuffer),
        v14 = RtlAllocateAndInitializeSidEx(&appAuthority, v15, authorities, v13),
        v14 < 0) )
  {
    v13->Sid = 0;
    v6 = v14 | 0x10000000;
  }
  else
  {
    Sid = v13->Sid;
    LengthSid = GetLengthSid(Sid);
    if ( !CopySid(LengthSid, Sid, SidBuffer) )
    {
      v18 = GetLastError();
      v6 = v18;
      if ( v18 > 0 )
        v6 = (unsigned __int16)v18 | 0x80070000;
    }
  }
  if ( v6 < 0 )
  {
    FreeAuthHostCapabilitySidAndAttributes(capabilitySidAndAttributes, v12);
    v12 = 0;
  }
  *capabilityCount = v12;
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180010e58  mov     [rsp-8+arg_0], rbx
0x180010e5d  push    rbp
0x180010e5e  push    rsi
0x180010e5f  push    rdi
0x180010e60  push    r12
0x180010e62  push    r13
0x180010e64  push    r14
0x180010e66  push    r15
0x180010e68  lea     rbp, [rsp-20h]
0x180010e6d  sub     rsp, 120h
0x180010e74  mov     rax, cs:__security_cookie
0x180010e7b  xor     rax, rsp
0x180010e7e  mov     [rbp+50h+var_38], rax
0x180010e82  xor     r13d, r13d
0x180010e85  mov     word ptr [rsp+150h+appAuthority.Value+4], 0F00h
0x180010e8c  mov     dword ptr [rsp+150h+appAuthority.Value], r13d
0x180010e91  mov     r12, capabilityCount
0x180010e94  mov     r15, capabilitySidAndAttributes
0x180010e97  mov     edi, r13d
0x180010e9a  bt      brokerFlags, 14h
0x180010e9e  jnb     short loc_180010EA7
0x180010ea0  mov     ebx, 4
0x180010ea5  jmp     short loc_180010EB0
0x180010ea7  neg     enablePrivateNetwork
0x180010ea9  sbb     ebx, ebx
0x180010eab  neg     ebx
0x180010ead  add     ebx, 2
0x180010eb0  mov     esi, r13d
0x180010eb3  mov     r9d, esi
0x180010eb6  lea     rax, _AuthHostBuiltInCapabilities
0x180010ebd  mov     r14d, esi
0x180010ec0  lea     rcx, [rsp+150h+appAuthority]; pIdentifierAuthority
0x180010ec5  shl     r14, 4
0x180010ec9  mov     r8d, 3; nSubAuthority0
0x180010ecf  add     r14, r15
0x180010ed2  mov     dl, 2; nSubAuthorityCount
0x180010ed4  mov     r9d, [rax+capabilityCount*4]; nSubAuthority1
0x180010ed8  mov     [rsp+150h+pSid], r14; pSid
0x180010edd  mov     [rsp+150h+nSubAuthority7], r13d; nSubAuthority7
0x180010ee2  mov     [rsp+150h+nSubAuthority6], r13d; nSubAuthority6
0x180010ee7  mov     [rsp+150h+nSubAuthority5], r13d; nSubAuthority5
0x180010eec  mov     [rsp+150h+nSubAuthority4], r13d; nSubAuthority4
0x180010ef1  mov     [rsp+150h+nSubAuthority3], r13d; nSubAuthority3
0x180010ef6  mov     [rsp+150h+nSubAuthority2], r13d; nSubAuthority2
0x180010efb  mov     dword ptr [r14+8], 4
0x180010f03  call    cs:__imp_AllocateAndInitializeSid
0x180010f09  test    eax, eax
0x180010f0b  jnz     short loc_180010F25
0x180010f0d  call    cs:__imp_GetLastError
0x180010f13  mov     edi, eax
0x180010f15  test    eax, eax
0x180010f17  jle     short loc_180010F22
0x180010f19  movzx   edi, ax
0x180010f1c  or      edi, 80070000h
0x180010f22  mov     [r14], r13
0x180010f25  inc     esi
0x180010f27  cmp     esi, ebx
0x180010f29  jb      short loc_180010EB3
0x180010f2b  mov     rdx, cs:_AuthHostNameCapabilities; SourceString
0x180010f32  lea     esi, [rbx+1]
0x180010f35  xorps   xmm1, xmm1
0x180010f38  shl     rbx, 4
0x180010f3c  xorps   xmm0, xmm0
0x180010f3f  lea     rcx, [rsp+150h+CapNameString]; DestinationString
0x180010f44  movups  xmmword ptr [rbp+50h+authorities+20h], xmm1
0x180010f48  add     rbx, r15
0x180010f4b  movups  xmmword ptr [rsp+150h+CapNameString.Length], xmm0
0x180010f50  movups  xmmword ptr [rsp+150h+authorities], xmm1
0x180010f55  mov     dword ptr [rbx+8], 4
0x180010f5c  movups  xmmword ptr [rbp+50h+authorities+10h], xmm1
0x180010f60  movups  xmmword ptr [rbp+50h+authorities+2Ch], xmm1
0x180010f64  call    cs:__imp_RtlInitUnicodeString
0x180010f6a  lea     capabilitySidAndAttributes, [rbp+50h+SidBuffer]
0x180010f6e  lea     rdx, [rbp+50h+GroupSidBuffer]
0x180010f72  lea     rcx, [rsp+150h+CapNameString]
0x180010f77  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x180010f7d  test    eax, eax
0x180010f7f  jns     short loc_180010F8C
0x180010f81  mov     edi, eax
0x180010f83  mov     [rbx], r13
0x180010f86  bts     edi, 1Ch
0x180010f8a  jmp     short loc_180010FEE
0x180010f8c  lea     rcx, [rbp+50h+SidBuffer]; pSid
0x180010f90  mov     dword ptr [rsp+150h+appAuthority.Value], r13d
0x180010f95  mov     word ptr [rsp+150h+appAuthority.Value+4], r13w
0x180010f9b  call    cs:__imp_GetSidSubAuthorityCount
0x180010fa1  mov     capabilityCount, rbx
0x180010fa4  lea     capabilitySidAndAttributes, [rsp+150h+authorities]
0x180010fa9  lea     rcx, [rsp+150h+appAuthority]
0x180010fae  mov     dl, [rax]
0x180010fb0  call    cs:__imp_RtlAllocateAndInitializeSidEx
0x180010fb6  test    eax, eax
0x180010fb8  js      short loc_180010F81
0x180010fba  mov     rbx, [rbx]
0x180010fbd  mov     rcx, rbx; pSid
0x180010fc0  call    cs:__imp_GetLengthSid
0x180010fc6  lea     capabilitySidAndAttributes, [rbp+50h+SidBuffer]; pSourceSid
0x180010fca  mov     rdx, rbx; pDestinationSid
0x180010fcd  mov     brokerFlags, eax; nDestinationSidLength
0x180010fcf  call    cs:__imp_CopySid
0x180010fd5  test    eax, eax
0x180010fd7  jnz     short loc_180010FEE
0x180010fd9  call    cs:__imp_GetLastError
0x180010fdf  mov     edi, eax
0x180010fe1  test    eax, eax
0x180010fe3  jle     short loc_180010FEE
0x180010fe5  movzx   edi, ax
0x180010fe8  or      edi, 80070000h
0x180010fee  test    edi, edi
0x180010ff0  jns     short loc_180010FFF
0x180010ff2  mov     enablePrivateNetwork, esi; capabilityCount
0x180010ff4  mov     rcx, r15; capabilitySidAndAttributes
0x180010ff7  call    _FreeAuthHostCapabilitySidAndAttributes
0x180010ffc  mov     esi, r13d
0x180010fff  mov     [r12], esi
0x180011003  mov     eax, edi
0x180011005  mov     rcx, [rbp+50h+var_38]
0x180011009  xor     rcx, rsp; StackCookie
0x18001100c  call    __security_check_cookie
0x180011011  mov     rbx, [rsp+150h+arg_0]
0x180011019  add     rsp, 120h
0x180011020  pop     r15
0x180011022  pop     r14
0x180011024  pop     r13
0x180011026  pop     r12
0x180011028  pop     rdi
0x180011029  pop     rsi
0x18001102a  pop     rbp
0x18001102b  retn
```
