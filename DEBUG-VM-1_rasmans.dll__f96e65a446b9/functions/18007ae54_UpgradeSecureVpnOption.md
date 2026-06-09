# UpgradeSecureVpnOption

- ea: `0x18007ae54`
- end: `0x18007b015`
- name: `UpgradeSecureVpnOption`
- size: `449`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18007aa48`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x18007ae54`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007af76`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18007af76`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007af0c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007af0c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007afd5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007afd5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18007afbc`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18007afbc`

## string_xrefs

- `0x18007af02`: `System\CurrentControlSet\Services\Rasman\PPP`

## pseudocode

```c
__int64 __fastcall UpgradeSecureVpnOption(HKEY hKey, __int64 a2)
{
  struct _LIST_ENTRY *v4; // rcx
  unsigned int v5; // ebx
  __int64 v6; // rdx
  unsigned int v7; // eax
  __int64 v8; // rdx
  HKEY hKeya; // [rsp+30h] [rbp-10h] BYREF
  int Data; // [rsp+78h] [rbp+38h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+40h] BYREF
  DWORD Type; // [rsp+88h] [rbp+48h] BYREF

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 864, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  hKeya = 0;
  Type = 4;
  cbData = 4;
  Data = 0;
  if ( !a2 )
  {
    v5 = 87;
    if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 6u )
    {
      v6 = 865;
LABEL_31:
      WPP_SF_d(v4[1].Flink, v6, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v5);
      return v5;
    }
    return v5;
  }
  v7 = RegOpenKeyExW(hKey, L"System\\CurrentControlSet\\Services\\Rasman\\PPP", 0, 0x20019u, &hKeya);
  v5 = v7;
  if ( v7 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v8 = 866;
LABEL_15:
      WPP_SF_d(v4[1].Flink, v8, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v7);
LABEL_24:
      v4 = WPP_GLOBAL_Control;
    }
  }
  else
  {
    v7 = RegQueryValueExW(hKeya, L"SecureVPN", 0, &Type, (LPBYTE)&Data, &cbData);
    v5 = v7;
    if ( !v7 )
    {
      if ( Data )
        *(_DWORD *)(a2 + 164) = 512;
      RegDeleteValueW(hKeya, L"SecureVPN");
      goto LABEL_24;
    }
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      v8 = 867;
      goto LABEL_15;
    }
  }
  if ( hKeya )
  {
    RegCloseKey(hKeya);
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v4[1].Blink) < 0 && BYTE1(v4[1].Blink) >= 6u )
  {
    v6 = 868;
    goto LABEL_31;
  }
  return v5;
}

```

## disassembly

```asm
0x18007ae54  push    rbp
0x18007ae56  push    rbx
0x18007ae57  push    rdi
0x18007ae58  push    r12
0x18007ae5a  push    r15
0x18007ae5c  mov     rbp, rsp
0x18007ae5f  sub     rsp, 40h
0x18007ae63  mov     rdi, rdx
0x18007ae66  mov     rbx, rcx
0x18007ae69  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ae70  lea     r15, WPP_GLOBAL_Control
0x18007ae77  lea     r12, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18007ae7e  cmp     rcx, r15
0x18007ae81  jz      short loc_18007AEA7
0x18007ae83  test    byte ptr [rcx+1Ch], 80h
0x18007ae87  jz      short loc_18007AEA7
0x18007ae89  cmp     byte ptr [rcx+19h], 6
0x18007ae8d  jb      short loc_18007AEA7
0x18007ae8f  mov     rcx, [rcx+10h]
0x18007ae93  mov     edx, 360h
0x18007ae98  mov     r8, r12
0x18007ae9b  call    WPP_SF_
0x18007aea0  mov     rcx, cs:WPP_GLOBAL_Control
0x18007aea7  mov     [rbp+hKey], 0
0x18007aeaf  mov     eax, 4
0x18007aeb4  mov     [rbp+Type], eax
0x18007aeb7  mov     [rbp+cbData], eax
0x18007aeba  mov     [rbp+Data], 0
0x18007aec1  test    rdi, rdi
0x18007aec4  jnz     short loc_18007AEF0
0x18007aec6  lea     ebx, [rax+53h]
0x18007aec9  cmp     rcx, r15
0x18007aecc  jz      loc_18007B007
0x18007aed2  test    byte ptr [rcx+1Ch], 80h
0x18007aed6  jz      loc_18007B007
0x18007aedc  cmp     byte ptr [rcx+19h], 6
0x18007aee0  jb      loc_18007B007
0x18007aee6  mov     edx, 361h
0x18007aeeb  jmp     loc_18007AFF8
0x18007aef0  lea     rax, [rbp+hKey]
0x18007aef4  mov     r9d, 20019h; samDesired
0x18007aefa  xor     r8d, r8d; ulOptions
0x18007aefd  mov     [rsp+40h+phkResult], rax; phkResult
0x18007af02  lea     rdx, c_pszRegKeySecureVpn; "System\\CurrentControlSet\\Services\\Ra"...
0x18007af09  mov     rcx, rbx; hKey
0x18007af0c  call    cs:__imp_RegOpenKeyExW
0x18007af12  mov     ebx, eax
0x18007af14  test    eax, eax
0x18007af16  jz      short loc_18007AF52
0x18007af18  mov     rcx, cs:WPP_GLOBAL_Control
0x18007af1f  cmp     rcx, r15
0x18007af22  jz      loc_18007AFC9
0x18007af28  test    byte ptr [rcx+1Ch], 80h
0x18007af2c  jz      loc_18007AFC9
0x18007af32  cmp     byte ptr [rcx+19h], 2
0x18007af36  jb      loc_18007AFC9
0x18007af3c  mov     edx, 362h
0x18007af41  mov     rcx, [rcx+10h]
0x18007af45  mov     r9d, eax
0x18007af48  mov     r8, r12
0x18007af4b  call    WPP_SF_d
0x18007af50  jmp     short loc_18007AFC2
0x18007af52  mov     rcx, [rbp+hKey]; hKey
0x18007af56  lea     rax, [rbp+cbData]
0x18007af5a  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18007af5f  lea     r9, [rbp+Type]; lpType
0x18007af63  lea     rax, [rbp+Data]
0x18007af67  xor     r8d, r8d; lpReserved
0x18007af6a  lea     rdx, c_pszRegValSecureVpn; "SecureVPN"
0x18007af71  mov     [rsp+40h+phkResult], rax; lpData
0x18007af76  call    cs:__imp_RegQueryValueExW
0x18007af7c  mov     ebx, eax
0x18007af7e  test    eax, eax
0x18007af80  jz      short loc_18007AFA1
0x18007af82  mov     rcx, cs:WPP_GLOBAL_Control
0x18007af89  cmp     rcx, r15
0x18007af8c  jz      short loc_18007AFC9
0x18007af8e  test    byte ptr [rcx+1Ch], 80h
0x18007af92  jz      short loc_18007AFC9
0x18007af94  cmp     byte ptr [rcx+19h], 2
0x18007af98  jb      short loc_18007AFC9
0x18007af9a  mov     edx, 363h
0x18007af9f  jmp     short loc_18007AF41
0x18007afa1  cmp     [rbp+Data], 0
0x18007afa5  jz      short loc_18007AFB1
0x18007afa7  mov     dword ptr [rdi+0A4h], 200h
0x18007afb1  mov     rcx, [rbp+hKey]; hKey
0x18007afb5  lea     rdx, c_pszRegValSecureVpn; "SecureVPN"
0x18007afbc  call    cs:__imp_RegDeleteValueW
0x18007afc2  mov     rcx, cs:WPP_GLOBAL_Control
0x18007afc9  mov     rax, [rbp+hKey]
0x18007afcd  test    rax, rax
0x18007afd0  jz      short loc_18007AFE2
0x18007afd2  mov     rcx, rax; hKey
0x18007afd5  call    cs:__imp_RegCloseKey
0x18007afdb  mov     rcx, cs:WPP_GLOBAL_Control
0x18007afe2  cmp     rcx, r15
0x18007afe5  jz      short loc_18007B007
0x18007afe7  test    byte ptr [rcx+1Ch], 80h
0x18007afeb  jz      short loc_18007B007
0x18007afed  cmp     byte ptr [rcx+19h], 6
0x18007aff1  jb      short loc_18007B007
0x18007aff3  mov     edx, 364h
0x18007aff8  mov     rcx, [rcx+10h]
0x18007affc  mov     r9d, ebx
0x18007afff  mov     r8, r12
0x18007b002  call    WPP_SF_d
0x18007b007  mov     eax, ebx
0x18007b009  add     rsp, 40h
0x18007b00d  pop     r15
0x18007b00f  pop     r12
0x18007b011  pop     rdi
0x18007b012  pop     rbx
0x18007b013  pop     rbp
0x18007b014  retn
```
