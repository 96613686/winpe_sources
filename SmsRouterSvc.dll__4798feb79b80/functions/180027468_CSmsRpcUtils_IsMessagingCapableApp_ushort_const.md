# CSmsRpcUtils::IsMessagingCapableApp(ushort const *)

- ea: `0x180027468`
- end: `0x1800275f5`
- name: `?IsMessagingCapableApp@CSmsRpcUtils@@SAHPEBG@Z`
- size: `397`
- prototype: `__int64 __fastcall(PCWSTR packageFullName)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003c580`

## callees

- `0x180003a60`
- `0x180004998`
- `0x180026a40`
- `0x180027468`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800275a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800275c5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800275a3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800275c5`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002758f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002758f`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x180027510`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x180027510`
- `ntdll!RtlInitUnicodeString` at `0x1800274fc`
- `ntdll!RtlInitUnicodeString` at `0x1800274fc`
- `ext-ms-win-security-capauthz-l1-1-0!QueryApplicationCapabilities` at `0x18002755b`
- `ext-ms-win-security-capauthz-l1-1-0!QueryApplicationCapabilities` at `0x18002755b`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x1800274d1`
- `api-ms-win-appmodel-runtime-l1-1-0!PackageFamilyNameFromFullName` at `0x1800274d1`

## pseudocode

```c
__int64 __fastcall CSmsRpcUtils::IsMessagingCapableApp(PCWSTR packageFullName)
{
  int v2; // eax
  unsigned int v3; // edi
  __int64 i; // r14
  unsigned int v6; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  _BYTE pSid2[56]; // [rsp+78h] [rbp-88h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v12[48]; // [rsp+140h] [rbp+40h] BYREF

  hMem = 0;
  v6 = 0;
  DestinationString = 0;
  memset_0(packageFamilyName, 0, 0x82u);
  packageFamilyNameLength = 65;
  if ( PackageFamilyNameFromFullName(packageFullName, &packageFamilyNameLength, packageFamilyName) )
    return 0;
  if ( !(unsigned int)CSmsRpcUtils::DoesAppMeetCTA(packageFamilyName) )
    return 0;
  RtlInitUnicodeString(&DestinationString, L"cellularMessaging");
  if ( (int)RtlDeriveCapabilitySidsFromName(&DestinationString, v12, pSid2) < 0 )
    return 0;
  v2 = QueryApplicationCapabilities(packageFullName, &hMem, &v6, 0, 0, 0, 0, 0, 0);
  if ( v2 == -2147024444 )
  {
    return 1;
  }
  else
  {
    v3 = 0;
    if ( v2 >= 0 )
    {
      for ( i = 0; (unsigned int)i < v6; i = (unsigned int)(i + 1) )
      {
        if ( EqualSid(*((PSID *)hMem + i), pSid2) )
          v3 = 1;
        LocalFree(*((HLOCAL *)hMem + i));
        *((_QWORD *)hMem + i) = 0;
      }
      LocalFree(hMem);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180027468  mov     [rsp-8+arg_8], rbx
0x18002746d  mov     [rsp-8+arg_10], rsi
0x180027472  push    rbp
0x180027473  push    rdi
0x180027474  push    r14
0x180027476  lea     rbp, [rsp-80h]
0x18002747b  sub     rsp, 180h
0x180027482  mov     rax, cs:__security_cookie
0x180027489  xor     rax, rsp
0x18002748c  mov     [rbp+90h+var_20], rax
0x180027490  mov     rbx, rcx
0x180027493  mov     [rsp+190h+hMem], 0
0x18002749c  xorps   xmm0, xmm0
0x18002749f  mov     [rsp+190h+var_140], 0
0x1800274a7  lea     rcx, [rbp+90h+packageFamilyName]; void *
0x1800274ab  xor     edx, edx; Val
0x1800274ad  mov     r8d, 82h; Size
0x1800274b3  movups  xmmword ptr [rsp+190h+DestinationString.Length], xmm0
0x1800274b8  call    memset_0
0x1800274bd  lea     r8, [rbp+90h+packageFamilyName]; packageFamilyName
0x1800274c1  mov     [rsp+190h+packageFamilyNameLength], 41h ; 'A'
0x1800274c9  lea     rdx, [rsp+190h+packageFamilyNameLength]; packageFamilyNameLength
0x1800274ce  mov     rcx, rbx; packageFullName
0x1800274d1  call    cs:__imp_PackageFamilyNameFromFullName
0x1800274d7  test    eax, eax
0x1800274d9  jnz     loc_1800275CF
0x1800274df  lea     rcx, [rbp+90h+packageFamilyName]; unsigned __int16 *
0x1800274e3  call    ?DoesAppMeetCTA@CSmsRpcUtils@@SAHPEBG@Z; CSmsRpcUtils::DoesAppMeetCTA(ushort const *)
0x1800274e8  test    eax, eax
0x1800274ea  jz      loc_1800275CF
0x1800274f0  lea     rdx, SourceString; "cellularMessaging"
0x1800274f7  lea     rcx, [rsp+190h+DestinationString]; DestinationString
0x1800274fc  call    cs:__imp_RtlInitUnicodeString
0x180027502  lea     r8, [rsp+190h+pSid2]
0x180027507  lea     rdx, [rbp+90h+var_50]
0x18002750b  lea     rcx, [rsp+190h+DestinationString]
0x180027510  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x180027516  test    eax, eax
0x180027518  js      loc_1800275CF
0x18002751e  mov     [rsp+190h+var_150], 0
0x180027527  lea     r8, [rsp+190h+var_140]
0x18002752c  mov     [rsp+190h+var_158], 0
0x180027535  lea     rdx, [rsp+190h+hMem]
0x18002753a  mov     [rsp+190h+var_160], 0
0x180027543  xor     r9d, r9d
0x180027546  mov     [rsp+190h+var_168], 0
0x18002754f  mov     rcx, rbx
0x180027552  mov     [rsp+190h+var_170], 0
0x18002755b  call    cs:__imp_QueryApplicationCapabilities
0x180027561  cmp     eax, 800701C4h
0x180027566  jnz     short loc_18002756F
0x180027568  mov     edi, 1
0x18002756d  jmp     short loc_1800275CB
0x18002756f  xor     edi, edi
0x180027571  test    eax, eax
0x180027573  js      short loc_1800275CB
0x180027575  xor     r14d, r14d
0x180027578  cmp     [rsp+190h+var_140], edi
0x18002757c  jbe     short loc_1800275C0
0x18002757e  lea     esi, [rdi+1]
0x180027581  mov     rcx, [rsp+190h+hMem]
0x180027586  lea     rdx, [rsp+190h+pSid2]; pSid2
0x18002758b  mov     rcx, [rcx+r14*8]; pSid1
0x18002758f  call    cs:__imp_EqualSid
0x180027595  mov     rcx, [rsp+190h+hMem]
0x18002759a  test    eax, eax
0x18002759c  cmovnz  edi, esi
0x18002759f  mov     rcx, [rcx+r14*8]; hMem
0x1800275a3  call    cs:__imp_LocalFree
0x1800275a9  mov     rcx, [rsp+190h+hMem]
0x1800275ae  mov     qword ptr [rcx+r14*8], 0
0x1800275b6  add     r14d, esi
0x1800275b9  cmp     r14d, [rsp+190h+var_140]
0x1800275be  jb      short loc_180027581
0x1800275c0  mov     rcx, [rsp+190h+hMem]; hMem
0x1800275c5  call    cs:__imp_LocalFree
0x1800275cb  mov     eax, edi
0x1800275cd  jmp     short loc_1800275D1
0x1800275cf  xor     eax, eax
0x1800275d1  mov     rcx, [rbp+90h+var_20]
0x1800275d5  xor     rcx, rsp; StackCookie
0x1800275d8  call    __security_check_cookie
0x1800275dd  lea     r11, [rsp+190h+var_10]
0x1800275e5  mov     rbx, [r11+28h]
0x1800275e9  mov     rsi, [r11+30h]
0x1800275ed  mov     rsp, r11
0x1800275f0  pop     r14
0x1800275f2  pop     rdi
0x1800275f3  pop     rbp
0x1800275f4  retn
```
