# SetNetworkQualificationInRegistry(ushort const *,int)

- ea: `0x180010c28`
- end: `0x180010d36`
- name: `?SetNetworkQualificationInRegistry@@YAJPEBGH@Z`
- size: `270`
- prototype: `__int64 __fastcall(const unsigned __int16 *, HKEY, __int64, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180010120`

## callees

- `0x18000a644`
- `0x18000e40c`
- `0x180010c28`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010cc1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010cc1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010cd1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010d1c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010cd1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010d1c`

## pseudocode

```c
__int64 __fastcall SetNetworkQualificationInRegistry(
        const unsigned __int16 *a1,
        HKEY a2,
        __int64 a3,
        unsigned __int16 *a4)
{
  int v4; // edi
  int v6; // ebx
  HKEY v7; // rdi
  unsigned int lpData; // [rsp+20h] [rbp-48h]
  DWORD cbData; // [rsp+28h] [rbp-40h]
  struct _SECURITY_ATTRIBUTES *v11; // [rsp+30h] [rbp-38h]
  unsigned int *v12; // [rsp+38h] [rbp-30h]
  HKEY hKey[4]; // [rsp+40h] [rbp-28h] BYREF
  int Data; // [rsp+78h] [rbp+10h] BYREF

  v4 = (int)a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
  memset(hKey, 0, 24);
  v6 = ATL::CRegKey::Create((ATL::CRegKey *)hKey, a2, a1, a4, lpData, cbData, v11, v12);
  if ( v6 )
  {
    v7 = hKey[0];
  }
  else
  {
    Data = v4;
    v7 = hKey[0];
    v6 = RegSetValueExW(hKey[0], L"AutoSetup", 0, 4u, (const BYTE *)&Data, 4u);
    if ( v7 )
    {
      RegCloseKey(v7);
      v7 = 0;
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
  if ( v6 > 0 )
    v6 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 )
    RegCloseKey(v7);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180010c28  mov     [rsp+arg_0], rbx
0x180010c2d  mov     [rsp+arg_10], rbp
0x180010c32  push    rdi
0x180010c33  sub     rsp, 60h
0x180010c37  mov     edi, edx
0x180010c39  mov     rbx, rcx
0x180010c3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180010c43  lea     rbp, WPP_GLOBAL_Control
0x180010c4a  cmp     rcx, rbp
0x180010c4d  jz      short loc_180010C6A
0x180010c4f  test    byte ptr [rcx+1Ch], 20h
0x180010c53  jz      short loc_180010C6A
0x180010c55  mov     rcx, [rcx+10h]
0x180010c59  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x180010c60  mov     edx, 19h
0x180010c65  call    WPP_SF_
0x180010c6a  mov     r8, rbx; unsigned __int16 *
0x180010c6d  mov     [rsp+68h+hKey], 0
0x180010c76  lea     rcx, [rsp+68h+hKey]; this
0x180010c7b  mov     [rsp+68h+var_20], 0
0x180010c84  mov     [rsp+68h+var_18], 0
0x180010c8d  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x180010c92  mov     ebx, eax
0x180010c94  test    eax, eax
0x180010c96  jnz     short loc_180010CDB
0x180010c98  lea     r9d, [rax+4]; dwType
0x180010c9c  mov     [rsp+68h+Data], edi
0x180010ca0  mov     rdi, [rsp+68h+hKey]
0x180010ca5  lea     rax, [rsp+68h+Data]
0x180010caa  mov     [rsp+68h+cbData], r9d; cbData
0x180010caf  lea     rdx, ValueName; "AutoSetup"
0x180010cb6  mov     rcx, rdi; hKey
0x180010cb9  mov     [rsp+68h+lpData], rax; lpData
0x180010cbe  xor     r8d, r8d; Reserved
0x180010cc1  call    cs:__imp_RegSetValueExW
0x180010cc7  mov     ebx, eax
0x180010cc9  test    rdi, rdi
0x180010ccc  jz      short loc_180010CE0
0x180010cce  mov     rcx, rdi; hKey
0x180010cd1  call    cs:__imp_RegCloseKey
0x180010cd7  xor     edi, edi
0x180010cd9  jmp     short loc_180010CE0
0x180010cdb  mov     rdi, [rsp+68h+hKey]
0x180010ce0  mov     rcx, cs:WPP_GLOBAL_Control
0x180010ce7  cmp     rcx, rbp
0x180010cea  jz      short loc_180010D07
0x180010cec  test    byte ptr [rcx+1Ch], 20h
0x180010cf0  jz      short loc_180010D07
0x180010cf2  mov     rcx, [rcx+10h]
0x180010cf6  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x180010cfd  mov     edx, 1Ah
0x180010d02  call    WPP_SF_
0x180010d07  test    ebx, ebx
0x180010d09  jle     short loc_180010D14
0x180010d0b  movzx   ebx, bx
0x180010d0e  or      ebx, 80070000h
0x180010d14  test    rdi, rdi
0x180010d17  jz      short loc_180010D22
0x180010d19  mov     rcx, rdi; hKey
0x180010d1c  call    cs:__imp_RegCloseKey
0x180010d22  lea     r11, [rsp+68h+var_8]
0x180010d27  mov     eax, ebx
0x180010d29  mov     rbx, [r11+10h]
0x180010d2d  mov     rbp, [r11+20h]
0x180010d31  mov     rsp, r11
0x180010d34  pop     rdi
0x180010d35  retn
```
