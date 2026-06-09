# SrSettings::CSrSettings::StoreWifiInfo(ushort const *,ushort const *,bool)

- ea: `0x180010400`
- end: `0x180010541`
- name: `?StoreWifiInfo@CSrSettings@SrSettings@@UEAAJPEBG0_N@Z`
- size: `321`
- prototype: `__int64 __fastcall(SrSettings::CSrSettings *__hidden this, const unsigned __int16 *lpStruct, const unsigned __int16 *, bool)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callees

- `0x18000e074`
- `0x18000ebf8`
- `0x18000ef08`
- `0x180010400`
- `0x180010a0c`
- `0x180012d7c`

## string_xrefs

- `0x18001046a`: `WiFi setting file %s doesn't exist, create it`
- `0x18001049c`: `Failed to create wifi setting file. Error: 0x%08x`
- `0x1800104ba`: `Failed to set ACL to wifi setting file. Error: 0x%08x`
- `0x1800104f2`: `Failed to store WiFi SSID. Error: 0x%08x`

## pseudocode

```c
__int64 __fastcall SrSettings::CSrSettings::StoreWifiInfo(
        const unsigned __int16 **this,
        unsigned __int16 *lpStruct,
        unsigned __int16 *a3,
        char a4)
{
  __int64 result; // rax
  int v9; // edi
  const wchar_t *v10; // r8
  const unsigned __int16 *v11; // rsi

  if ( *((_BYTE *)this + 3944) )
  {
    SrSettings::CSrSettings::Trace(this, 2, L"Cannot store WiFi info in UseInWinRE mode");
    return 2147942405LL;
  }
  if ( !*((_BYTE *)this + 3945) )
    return 2147942421LL;
  if ( !(unsigned int)FileExists(this[13]) )
  {
    SrSettings::CSrSettings::Trace(this, 0, L"WiFi setting file %s doesn't exist, create it", this[13]);
    v9 = SrSettings::CSrSettings::SetSetting((SrSettings::CSrSettings *)this, this[13], L"WiFiCredential", 0, 0);
    if ( v9 < 0 )
    {
      v10 = L"Failed to create wifi setting file. Error: 0x%08x";
LABEL_16:
      SrSettings::CSrSettings::Trace(this, 2, v10, (unsigned int)v9);
      return (unsigned int)v9;
    }
  }
  v9 = SrSettings::CSrSettings::SetACL((SrSettings::CSrSettings *)this, (WCHAR *)this[13]);
  if ( v9 >= 0 )
  {
    v11 = L"ManagedWiFiCredential";
    if ( !a4 )
      v11 = L"WiFiCredential";
    v9 = SrSettings::CSrSettings::SetResourceString((SrSettings::CSrSettings *)this, this[13], v11, L"SSID", lpStruct);
    if ( v9 >= 0 )
    {
      result = SrSettings::CSrSettings::SetResourceString(
                 (SrSettings::CSrSettings *)this,
                 this[13],
                 v11,
                 L"Password",
                 a3);
      v9 = result;
      if ( (int)result >= 0 )
        return result;
      v10 = L"Failed to store WiFi password. Error: 0x%08x";
      goto LABEL_16;
    }
    SrSettings::CSrSettings::Trace(this, 2, L"Failed to store WiFi SSID. Error: 0x%08x", (unsigned int)v9);
  }
  else
  {
    SrSettings::CSrSettings::Trace(this, 2, L"Failed to set ACL to wifi setting file. Error: 0x%08x", (unsigned int)v9);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180010400  push    rbx
0x180010402  push    rbp
0x180010403  push    rsi
0x180010404  push    rdi
0x180010405  push    r13
0x180010407  push    r14
0x180010409  push    r15
0x18001040b  sub     rsp, 30h
0x18001040f  cmp     byte ptr [rcx+0F68h], 0
0x180010416  mov     r14b, r9b
0x180010419  mov     rbp, r8
0x18001041c  mov     r15, rdx
0x18001041f  mov     rbx, rcx
0x180010422  jz      short loc_18001043F
0x180010424  lea     r8, aCannotStoreWif; "Cannot store WiFi info in UseInWinRE mo"...
0x18001042b  mov     edx, 2
0x180010430  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180010435  mov     eax, 80070005h
0x18001043a  jmp     loc_180010532
0x18001043f  cmp     byte ptr [rcx+0F69h], 0
0x180010446  jnz     short loc_180010452
0x180010448  mov     eax, 80070015h
0x18001044d  jmp     loc_180010532
0x180010452  mov     rcx, [rcx+68h]
0x180010456  call    FileExists
0x18001045b  lea     r13, aWificredential; "WiFiCredential"
0x180010462  test    eax, eax
0x180010464  jnz     short loc_1800104A5
0x180010466  mov     r9, [rbx+68h]
0x18001046a  lea     r8, aWifiSettingFil_0; "WiFi setting file %s doesn't exist, cre"...
0x180010471  xor     edx, edx
0x180010473  mov     rcx, rbx
0x180010476  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18001047b  mov     rdx, [rbx+68h]; unsigned __int16 *
0x18001047f  xor     r9d, r9d; unsigned __int16 *
0x180010482  mov     r8, r13; unsigned __int16 *
0x180010485  mov     [rsp+68h+lpStruct], 0; unsigned __int16 *
0x18001048e  mov     rcx, rbx; this
0x180010491  call    ?SetSetting@CSrSettings@SrSettings@@AEAAJPEBG000@Z; SrSettings::CSrSettings::SetSetting(ushort const *,ushort const *,ushort const *,ushort const *)
0x180010496  mov     edi, eax
0x180010498  test    eax, eax
0x18001049a  jns     short loc_1800104A5
0x18001049c  lea     r8, aFailedToCreate; "Failed to create wifi setting file. Err"...
0x1800104a3  jmp     short loc_180010520
0x1800104a5  mov     rdx, [rbx+68h]; lpFileName
0x1800104a9  mov     rcx, rbx; this
0x1800104ac  call    ?SetACL@CSrSettings@SrSettings@@AEAAJPEBG@Z; SrSettings::CSrSettings::SetACL(ushort const *)
0x1800104b1  mov     edi, eax
0x1800104b3  mov     rcx, rbx; this
0x1800104b6  test    eax, eax
0x1800104b8  jns     short loc_1800104C3
0x1800104ba  lea     r8, aFailedToSetAcl_0; "Failed to set ACL to wifi setting file."...
0x1800104c1  jmp     short loc_180010523
0x1800104c3  mov     rdx, [rbx+68h]; unsigned __int16 *
0x1800104c7  lea     rsi, aManagedwificre; "ManagedWiFiCredential"
0x1800104ce  test    r14b, r14b
0x1800104d1  mov     [rsp+68h+lpStruct], r15; lpStruct
0x1800104d6  lea     r9, aSsid; "SSID"
0x1800104dd  cmovz   rsi, r13
0x1800104e1  mov     r8, rsi; unsigned __int16 *
0x1800104e4  call    ?SetResourceString@CSrSettings@SrSettings@@AEAAJPEBG000@Z; SrSettings::CSrSettings::SetResourceString(ushort const *,ushort const *,ushort const *,ushort const *)
0x1800104e9  mov     edi, eax
0x1800104eb  mov     rcx, rbx; this
0x1800104ee  test    eax, eax
0x1800104f0  jns     short loc_1800104FB
0x1800104f2  lea     r8, aFailedToStoreW_0; "Failed to store WiFi SSID. Error: 0x%08"...
0x1800104f9  jmp     short loc_180010523
0x1800104fb  mov     rdx, [rbx+68h]; unsigned __int16 *
0x1800104ff  lea     r9, aPassword; "Password"
0x180010506  mov     r8, rsi; unsigned __int16 *
0x180010509  mov     [rsp+68h+lpStruct], rbp; lpStruct
0x18001050e  call    ?SetResourceString@CSrSettings@SrSettings@@AEAAJPEBG000@Z; SrSettings::CSrSettings::SetResourceString(ushort const *,ushort const *,ushort const *,ushort const *)
0x180010513  mov     edi, eax
0x180010515  test    eax, eax
0x180010517  jns     short loc_180010532
0x180010519  lea     r8, aFailedToStoreW; "Failed to store WiFi password. Error: 0"...
0x180010520  mov     rcx, rbx
0x180010523  mov     r9d, edi
0x180010526  mov     edx, 2
0x18001052b  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x180010530  mov     eax, edi
0x180010532  add     rsp, 30h
0x180010536  pop     r15
0x180010538  pop     r14
0x18001053a  pop     r13
0x18001053c  pop     rdi
0x18001053d  pop     rsi
0x18001053e  pop     rbp
0x18001053f  pop     rbx
0x180010540  retn
```
