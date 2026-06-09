# SrSettings::CSrSettings::ClearWifiInfo(bool)

- ea: `0x180006fe0`
- end: `0x180007078`
- name: `?ClearWifiInfo@CSrSettings@SrSettings@@UEAAJ_N@Z`
- size: `152`
- prototype: `__int64 __fastcall(SrSettings::CSrSettings *this, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180006fe0`
- `0x18000e074`
- `0x18000ef08`
- `0x180010a0c`

## string_xrefs

- `0x180007057`: `Failed to set ACL to wifi setting file. Error: 0x%08x`

## pseudocode

```c
__int64 __fastcall SrSettings::CSrSettings::ClearWifiInfo(SrSettings::CSrSettings *this, char a2)
{
  __int64 result; // rax
  const unsigned __int16 *v4; // r8
  int v5; // eax
  unsigned int v6; // edi

  if ( !*((_BYTE *)this + 3945) )
    return 2147942421LL;
  if ( a2 )
    v4 = L"ManagedWiFiCredential";
  else
    v4 = L"WiFiCredential";
  v5 = SrSettings::CSrSettings::SetSetting(this, *((const unsigned __int16 **)this + 13), v4, 0, 0);
  v6 = v5;
  if ( v5 >= 0 )
  {
    result = SrSettings::CSrSettings::SetACL(this, *((WCHAR **)this + 13));
    if ( (int)result < 0 )
    {
      SrSettings::CSrSettings::Trace(
        this,
        1,
        L"Failed to set ACL to wifi setting file. Error: 0x%08x",
        (unsigned int)result);
      return 0;
    }
  }
  else
  {
    SrSettings::CSrSettings::Trace(this, 2, L"Failed to clear wifi info. Error: 0x%08x", (unsigned int)v5);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x180006fe0  mov     [rsp+arg_0], rbx
0x180006fe5  push    rdi
0x180006fe6  sub     rsp, 30h
0x180006fea  cmp     byte ptr [rcx+0F69h], 0
0x180006ff1  mov     rbx, rcx
0x180006ff4  jnz     short loc_180006FFD
0x180006ff6  mov     eax, 80070015h
0x180006ffb  jmp     short loc_18000706D
0x180006ffd  xor     r9d, r9d; unsigned __int16 *
0x180007000  mov     [rsp+38h+var_18], 0; unsigned __int16 *
0x180007009  test    dl, dl
0x18000700b  mov     rdx, [rcx+68h]; unsigned __int16 *
0x18000700f  jz      short loc_18000703E
0x180007011  lea     r8, aManagedwificre; "ManagedWiFiCredential"
0x180007018  call    ?SetSetting@CSrSettings@SrSettings@@AEAAJPEBG000@Z; SrSettings::CSrSettings::SetSetting(ushort const *,ushort const *,ushort const *,ushort const *)
0x18000701d  mov     edi, eax
0x18000701f  mov     rcx, rbx; this
0x180007022  test    eax, eax
0x180007024  jns     short loc_180007047
0x180007026  mov     r9d, eax
0x180007029  lea     r8, aFailedToClearW; "Failed to clear wifi info. Error: 0x%08"...
0x180007030  mov     edx, 2
0x180007035  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000703a  mov     eax, edi
0x18000703c  jmp     short loc_18000706D
0x18000703e  lea     r8, aWificredential; "WiFiCredential"
0x180007045  jmp     short loc_180007018
0x180007047  mov     rdx, [rbx+68h]; lpFileName
0x18000704b  call    ?SetACL@CSrSettings@SrSettings@@AEAAJPEBG@Z; SrSettings::CSrSettings::SetACL(ushort const *)
0x180007050  test    eax, eax
0x180007052  jns     short loc_18000706D
0x180007054  mov     r9d, eax
0x180007057  lea     r8, aFailedToSetAcl_0; "Failed to set ACL to wifi setting file."...
0x18000705e  mov     edx, 1
0x180007063  mov     rcx, rbx
0x180007066  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000706b  xor     eax, eax
0x18000706d  mov     rbx, [rsp+38h+arg_0]
0x180007072  add     rsp, 30h
0x180007076  pop     rdi
0x180007077  retn
```
