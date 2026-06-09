# Microsoft::Resources::HasCapability(ushort const *)

- ea: `0x180007e84`
- end: `0x180007f27`
- name: `?HasCapability@Resources@Microsoft@@YA_NPEBG@Z`
- size: `163`
- prototype: `bool __fastcall(Microsoft::Resources *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001aafc`

## callees

- `0x180007e84`
- `0x180007f30`
- `0x180078f0c`

## import_xrefs

- `ntdll!RtlCheckSandboxedToken` at `0x180007eec`
- `ntdll!RtlCheckSandboxedToken` at `0x180007eec`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180007ed3`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180007ed3`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x180007ea8`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x180007ea8`

## pseudocode

```c
bool __fastcall Microsoft::Resources::HasCapability(Microsoft::Resources *this, const unsigned __int16 *a2)
{
  enum WELL_KNOWN_SID_TYPE v3; // edx
  enum WELL_KNOWN_SID_TYPE v4; // edx
  enum WELL_KNOWN_SID_TYPE v5; // edx
  Microsoft::Resources *v6; // [rsp+30h] [rbp+8h] BYREF
  int v7; // [rsp+38h] [rbp+10h] BYREF

  v6 = this;
  if ( Microsoft::Resources::IsPackagedAndAppContainer(this) )
  {
    LOBYTE(v6) = 0;
    return !(unsigned int)CapabilityCheck(0, L"packageContents", &v6) && (_BYTE)v6;
  }
  v7 = 0;
  RtlGetDeviceFamilyInfoEnum(0, &v7, 0);
  if ( v7 == 5 )
    return 0;
  LOBYTE(v6) = 0;
  if ( (unsigned int)RtlCheckSandboxedToken(0, &v6)
    || (_BYTE)v6
    || Microsoft::Resources::IsCurrentTokenMemberOf((Microsoft::Resources *)0x16, v3)
    || Microsoft::Resources::IsCurrentTokenMemberOf((Microsoft::Resources *)0x17, v4) )
  {
    return 0;
  }
  return !Microsoft::Resources::IsCurrentTokenMemberOf((Microsoft::Resources *)0x18, v5);
}

```

## disassembly

```asm
0x180007e84  mov     [rsp+arg_0], rcx
0x180007e89  sub     rsp, 28h
0x180007e8d  call    ?IsPackagedAndAppContainer@Resources@Microsoft@@YA_NXZ; Microsoft::Resources::IsPackagedAndAppContainer(void)
0x180007e92  xor     ecx, ecx
0x180007e94  test    al, al
0x180007e96  jz      short loc_180007EC3
0x180007e98  lea     r8, [rsp+28h+arg_0]
0x180007e9d  mov     byte ptr [rsp+28h+arg_0], cl
0x180007ea1  lea     rdx, aPackagecontent; "packageContents"
0x180007ea8  call    cs:__imp_CapabilityCheck
0x180007eae  test    eax, eax
0x180007eb0  jnz     short loc_180007EBC
0x180007eb2  cmp     byte ptr [rsp+28h+arg_0], al
0x180007eb6  jz      short loc_180007EBC
0x180007eb8  mov     al, 1
0x180007eba  jmp     short loc_180007EBE
0x180007ebc  xor     al, al
0x180007ebe  add     rsp, 28h
0x180007ec2  retn
0x180007ec3  xor     r8d, r8d
0x180007ec6  mov     [rsp+28h+arg_8], 0
0x180007ece  lea     rdx, [rsp+28h+arg_8]
0x180007ed3  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x180007ed9  cmp     [rsp+28h+arg_8], 5
0x180007ede  jz      short loc_180007EBC
0x180007ee0  lea     rdx, [rsp+28h+arg_0]
0x180007ee5  mov     byte ptr [rsp+28h+arg_0], 0
0x180007eea  xor     ecx, ecx
0x180007eec  call    cs:__imp_RtlCheckSandboxedToken
0x180007ef2  test    eax, eax
0x180007ef4  jnz     short loc_180007EBC
0x180007ef6  cmp     byte ptr [rsp+28h+arg_0], al
0x180007efa  jnz     short loc_180007EBC
0x180007efc  lea     ecx, [rax+16h]; this
0x180007eff  call    ?IsCurrentTokenMemberOf@Resources@Microsoft@@YA_NW4WELL_KNOWN_SID_TYPE@@@Z; Microsoft::Resources::IsCurrentTokenMemberOf(WELL_KNOWN_SID_TYPE)
0x180007f04  test    al, al
0x180007f06  jnz     short loc_180007EBC
0x180007f08  mov     ecx, 17h; this
0x180007f0d  call    ?IsCurrentTokenMemberOf@Resources@Microsoft@@YA_NW4WELL_KNOWN_SID_TYPE@@@Z; Microsoft::Resources::IsCurrentTokenMemberOf(WELL_KNOWN_SID_TYPE)
0x180007f12  test    al, al
0x180007f14  jnz     short loc_180007EBC
0x180007f16  mov     ecx, 18h; this
0x180007f1b  call    ?IsCurrentTokenMemberOf@Resources@Microsoft@@YA_NW4WELL_KNOWN_SID_TYPE@@@Z; Microsoft::Resources::IsCurrentTokenMemberOf(WELL_KNOWN_SID_TYPE)
0x180007f20  test    al, al
0x180007f22  setz    al
0x180007f25  jmp     short loc_180007EBE
```
