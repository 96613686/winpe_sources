# GetCachedMachineDomainInfo(ushort * *,ushort * *)

- ea: `0x18000fe30`
- end: `0x18000fffe`
- name: `?GetCachedMachineDomainInfo@@YAJPEAPEAG0@Z`
- size: `462`
- prototype: `__int64 __fastcall(unsigned __int16 **, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000f560`
- `0x1800196cc`

## callees

- `0x18000fe30`
- `0x180010920`
- `0x180010950`
- `0x18001a450`
- `0x18001a6ac`

## import_xrefs

- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18000ffe7`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18000ffe7`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18000fe87`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18000fe87`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18000fec2`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18000fec2`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18000ffd8`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18000ffd8`

## string_xrefs

- `0x18000fe99`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyutil.cxx`
- `0x18000ffa7`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeyutil.cxx`

## pseudocode

```c
__int64 __fastcall GetCachedMachineDomainInfo(unsigned __int16 **a1, unsigned __int16 **a2)
{
  unsigned int v2; // ebx
  NTSTATUS v5; // edi
  unsigned int v6; // r9d
  __int64 v7; // rsi
  void *v8; // rax
  void *v9; // rdi
  unsigned int v10; // r9d
  unsigned int v11; // ecx
  __int64 v12; // r14
  void *v13; // rax
  void *v14; // rsi
  PVOID v15; // rcx
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+20h] [rbp-30h] BYREF
  PVOID Buffer; // [rsp+90h] [rbp+40h] BYREF
  PVOID PolicyHandle; // [rsp+98h] [rbp+48h] BYREF

  v2 = 0;
  Buffer = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  PolicyHandle = 0;
  if ( !g_pwszForestName || !g_pwszDomainDNSName )
  {
    v5 = LsaOpenPolicy(0, &ObjectAttributes, 1u, &PolicyHandle);
    if ( v5 < 0 )
    {
      v6 = 801;
LABEL_5:
      SidKeyDebugTraceError(v5, "ntStatus", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyutil.cxx", v6);
      v2 = v5;
      goto LABEL_22;
    }
    v5 = LsaQueryInformationPolicy(PolicyHandle, PolicyDnsDomainInformation, &Buffer);
    if ( v5 < 0 )
    {
      v6 = 813;
      goto LABEL_5;
    }
    if ( !Buffer || !*((_QWORD *)Buffer + 3) || !*((_QWORD *)Buffer + 5) )
    {
      v2 = -2147024891;
      v10 = 824;
      v11 = -2147024891;
      goto LABEL_21;
    }
    v7 = *((unsigned __int16 *)Buffer + 8);
    v8 = SIDKeyProvAlloc(v7 + 2);
    v9 = v8;
    if ( !v8 )
    {
      v10 = 834;
LABEL_13:
      v2 = -2147024882;
      v11 = -2147024882;
LABEL_21:
      SidKeyDebugTraceError(v11, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeyutil.cxx", v10);
      goto LABEL_22;
    }
    memcpy_0(v8, *((const void **)Buffer + 3), v7 + 2);
    v12 = *((unsigned __int16 *)Buffer + 16);
    v13 = SIDKeyProvAlloc(v12 + 2);
    v14 = v13;
    if ( !v13 )
    {
      v10 = 845;
      goto LABEL_13;
    }
    memcpy_0(v13, *((const void **)Buffer + 5), v12 + 2);
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_pwszDomainDNSName, (signed __int64)v9, 0) )
      SIDKeyProvFree(v9);
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_pwszForestName, (signed __int64)v14, 0) )
      SIDKeyProvFree(v14);
  }
LABEL_22:
  v15 = Buffer;
  *a1 = (unsigned __int16 *)g_pwszDomainDNSName;
  *a2 = (unsigned __int16 *)g_pwszForestName;
  if ( v15 )
    LsaFreeMemory(v15);
  if ( PolicyHandle )
    LsaClose(PolicyHandle);
  return v2;
}

```

## disassembly

```asm
0x18000fe30  push    rbp
0x18000fe32  push    rbx
0x18000fe33  push    rsi
0x18000fe34  push    rdi
0x18000fe35  push    r12
0x18000fe37  push    r14
0x18000fe39  push    r15
0x18000fe3b  mov     rbp, rsp
0x18000fe3e  sub     rsp, 50h
0x18000fe42  xor     ebx, ebx
0x18000fe44  xorps   xmm0, xmm0
0x18000fe47  cmp     cs:?g_pwszForestName@@3PEAGEA, rbx; ushort * g_pwszForestName
0x18000fe4e  mov     r15, rdx
0x18000fe51  mov     r12, rcx
0x18000fe54  mov     [rbp+Buffer], rbx
0x18000fe58  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18000fe5c  mov     [rbp+PolicyHandle], rbx
0x18000fe60  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18000fe64  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000fe68  jz      short loc_18000FE77
0x18000fe6a  cmp     cs:?g_pwszDomainDNSName@@3PEAGEA, rbx; ushort * g_pwszDomainDNSName
0x18000fe71  jnz     loc_18000FFBA
0x18000fe77  lea     r9, [rbp+PolicyHandle]; PolicyHandle
0x18000fe7b  mov     r8d, 1; DesiredAccess
0x18000fe81  lea     rdx, [rbp+ObjectAttributes]; ObjectAttributes
0x18000fe85  xor     ecx, ecx; SystemName
0x18000fe87  call    cs:__imp_LsaOpenPolicy
0x18000fe8d  mov     edi, eax
0x18000fe8f  test    eax, eax
0x18000fe91  jns     short loc_18000FEB5
0x18000fe93  mov     r9d, 321h; unsigned int
0x18000fe99  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000fea0  mov     ecx, edi; unsigned int
0x18000fea2  lea     rdx, aNtstatus; "ntStatus"
0x18000fea9  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000feae  mov     ebx, edi
0x18000feb0  jmp     loc_18000FFBA
0x18000feb5  mov     rcx, [rbp+PolicyHandle]; PolicyHandle
0x18000feb9  lea     r8, [rbp+Buffer]; Buffer
0x18000febd  mov     edx, 0Ch; InformationClass
0x18000fec2  call    cs:__imp_LsaQueryInformationPolicy
0x18000fec8  mov     edi, eax
0x18000feca  test    eax, eax
0x18000fecc  jns     short loc_18000FED6
0x18000fece  mov     r9d, 32Dh
0x18000fed4  jmp     short loc_18000FE99
0x18000fed6  mov     rax, [rbp+Buffer]
0x18000feda  test    rax, rax
0x18000fedd  jz      loc_18000FF97
0x18000fee3  cmp     [rax+18h], rbx
0x18000fee7  jz      loc_18000FF97
0x18000feed  cmp     [rax+28h], rbx
0x18000fef1  jz      loc_18000FF97
0x18000fef7  movzx   esi, word ptr [rax+10h]
0x18000fefb  lea     rcx, [rsi+2]; unsigned __int64
0x18000feff  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000ff04  mov     rdi, rax
0x18000ff07  test    rax, rax
0x18000ff0a  jnz     short loc_18000FF21
0x18000ff0c  mov     r9d, 342h
0x18000ff12  mov     ebx, 8007000Eh
0x18000ff17  mov     ecx, 8007000Eh
0x18000ff1c  jmp     loc_18000FFA7
0x18000ff21  mov     rdx, [rbp+Buffer]
0x18000ff25  lea     r8, [rsi+2]; Size
0x18000ff29  mov     rcx, rdi; void *
0x18000ff2c  mov     rdx, [rdx+18h]; Src
0x18000ff30  call    memcpy_0
0x18000ff35  mov     rax, [rbp+Buffer]
0x18000ff39  movzx   r14d, word ptr [rax+20h]
0x18000ff3e  lea     rcx, [r14+2]; unsigned __int64
0x18000ff42  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000ff47  mov     rsi, rax
0x18000ff4a  test    rax, rax
0x18000ff4d  jnz     short loc_18000FF57
0x18000ff4f  mov     r9d, 34Dh
0x18000ff55  jmp     short loc_18000FF12
0x18000ff57  mov     rdx, [rbp+Buffer]
0x18000ff5b  lea     r8, [r14+2]; Size
0x18000ff5f  mov     rcx, rsi; void *
0x18000ff62  mov     rdx, [rdx+28h]; Src
0x18000ff66  call    memcpy_0
0x18000ff6b  xor     eax, eax
0x18000ff6d  lock cmpxchg cs:?g_pwszDomainDNSName@@3PEAGEA, rdi; ushort * g_pwszDomainDNSName
0x18000ff76  jz      short loc_18000FF80
0x18000ff78  mov     rcx, rdi; lpMem
0x18000ff7b  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18000ff80  xor     eax, eax
0x18000ff82  lock cmpxchg cs:?g_pwszForestName@@3PEAGEA, rsi; ushort * g_pwszForestName
0x18000ff8b  jz      short loc_18000FFBA
0x18000ff8d  mov     rcx, rsi; lpMem
0x18000ff90  call    ?SIDKeyProvFree@@YAXPEAX@Z; SIDKeyProvFree(void *)
0x18000ff95  jmp     short loc_18000FFBA
0x18000ff97  mov     ebx, 80070005h
0x18000ff9c  mov     r9d, 338h; unsigned int
0x18000ffa2  mov     ecx, 80070005h; unsigned int
0x18000ffa7  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000ffae  lea     rdx, aHr; "hr"
0x18000ffb5  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000ffba  mov     rax, cs:?g_pwszDomainDNSName@@3PEAGEA; ushort * g_pwszDomainDNSName
0x18000ffc1  mov     rcx, [rbp+Buffer]; Buffer
0x18000ffc5  mov     [r12], rax
0x18000ffc9  mov     rax, cs:?g_pwszForestName@@3PEAGEA; ushort * g_pwszForestName
0x18000ffd0  mov     [r15], rax
0x18000ffd3  test    rcx, rcx
0x18000ffd6  jz      short loc_18000FFDE
0x18000ffd8  call    cs:__imp_LsaFreeMemory
0x18000ffde  mov     rcx, [rbp+PolicyHandle]; ObjectHandle
0x18000ffe2  test    rcx, rcx
0x18000ffe5  jz      short loc_18000FFED
0x18000ffe7  call    cs:__imp_LsaClose
0x18000ffed  mov     eax, ebx
0x18000ffef  add     rsp, 50h
0x18000fff3  pop     r15
0x18000fff5  pop     r14
0x18000fff7  pop     r12
0x18000fff9  pop     rdi
0x18000fffa  pop     rsi
0x18000fffb  pop     rbx
0x18000fffc  pop     rbp
0x18000fffd  retn
```
