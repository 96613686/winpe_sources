# SetNetworkSizeInRegistry(ushort const *,ulong,int)

- ea: `0x180010d3c`
- end: `0x180010ece`
- name: `?SetNetworkSizeInRegistry@@YAJPEBGKH@Z`
- size: `402`
- prototype: `__int64 __fastcall(const unsigned __int16 *, HKEY, int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010120`

## callees

- `0x18000a644`
- `0x18000e40c`
- `0x180010d3c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010df6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180010df6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010de6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010e1e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010e57`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010de6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010e1e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010e57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010e67`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010eb1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010e67`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010eb1`

## pseudocode

```c
__int64 __fastcall SetNetworkSizeInRegistry(const unsigned __int16 *a1, HKEY a2, int a3, unsigned __int16 *a4)
{
  int v5; // edi
  int v7; // ebx
  HKEY v8; // rdi
  unsigned int lpData; // [rsp+20h] [rbp-40h]
  DWORD cbData; // [rsp+28h] [rbp-38h]
  struct _SECURITY_ATTRIBUTES *v12; // [rsp+30h] [rbp-30h]
  unsigned int *v13; // [rsp+38h] [rbp-28h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-20h] BYREF
  HKEY hKey[3]; // [rsp+48h] [rbp-18h] BYREF
  int Data; // [rsp+98h] [rbp+38h] BYREF

  v5 = (int)a2;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
  memset(hKey, 0, sizeof(hKey));
  SystemTimeAsFileTime = 0;
  v7 = ATL::CRegKey::Create((ATL::CRegKey *)hKey, a2, a1, a4, lpData, cbData, v12, v13);
  if ( v7 )
  {
    v8 = hKey[0];
  }
  else
  {
    Data = v5;
    v8 = hKey[0];
    v7 = RegSetValueExW(hKey[0], L"NetworkSize", 0, 4u, (const BYTE *)&Data, 4u);
    if ( !v7 )
    {
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v7 = RegSetValueExW(v8, L"NetworkSizeTimestamp", 0, 3u, (const BYTE *)&SystemTimeAsFileTime, 8u);
      if ( !v7 )
      {
        if ( a3 )
        {
          Data = 1;
          v7 = RegSetValueExW(v8, L"NetworkSizeEverDisqualified", 0, 4u, (const BYTE *)&Data, 4u);
        }
      }
    }
    if ( v8 )
    {
      RegCloseKey(v8);
      v8 = 0;
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_1de612464331343acbc2280e70e7e1cd_Traceguids);
  if ( v7 > 0 )
    v7 = (unsigned __int16)v7 | 0x80070000;
  if ( v8 )
    RegCloseKey(v8);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180010d3c  mov     [rsp-18h+arg_0], rbx
0x180010d41  mov     [rsp-18h+arg_8], rsi
0x180010d46  push    rbp
0x180010d47  push    rdi
0x180010d48  push    r12
0x180010d4a  mov     rbp, rsp
0x180010d4d  sub     rsp, 60h
0x180010d51  mov     esi, r8d
0x180010d54  mov     edi, edx
0x180010d56  mov     rbx, rcx
0x180010d59  mov     rcx, cs:WPP_GLOBAL_Control
0x180010d60  lea     r12, WPP_GLOBAL_Control
0x180010d67  cmp     rcx, r12
0x180010d6a  jz      short loc_180010D87
0x180010d6c  test    byte ptr [rcx+1Ch], 20h
0x180010d70  jz      short loc_180010D87
0x180010d72  mov     rcx, [rcx+10h]
0x180010d76  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x180010d7d  mov     edx, 1Dh
0x180010d82  call    WPP_SF_
0x180010d87  mov     r8, rbx; unsigned __int16 *
0x180010d8a  mov     [rbp+hKey], 0
0x180010d92  lea     rcx, [rbp+hKey]; this
0x180010d96  mov     [rbp+var_10], 0
0x180010d9e  mov     [rbp+var_8], 0
0x180010da6  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180010dae  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x180010db3  mov     ebx, eax
0x180010db5  test    eax, eax
0x180010db7  jnz     loc_180010E71
0x180010dbd  mov     [rbp+Data], edi
0x180010dc0  lea     rax, [rbp+Data]
0x180010dc4  mov     rdi, [rbp+hKey]
0x180010dc8  lea     r9d, [rbx+4]; dwType
0x180010dcc  mov     rcx, rdi; hKey
0x180010dcf  mov     [rsp+60h+cbData], 4; cbData
0x180010dd7  xor     r8d, r8d; Reserved
0x180010dda  mov     [rsp+60h+lpData], rax; lpData
0x180010ddf  lea     rdx, aNetworksize; "NetworkSize"
0x180010de6  call    cs:__imp_RegSetValueExW
0x180010dec  mov     ebx, eax
0x180010dee  test    eax, eax
0x180010df0  jnz     short loc_180010E5F
0x180010df2  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180010df6  call    cs:__imp_GetSystemTimeAsFileTime
0x180010dfc  lea     rax, [rbp+SystemTimeAsFileTime]
0x180010e00  mov     [rsp+60h+cbData], 8; cbData
0x180010e08  lea     r9d, [rbx+3]; dwType
0x180010e0c  mov     [rsp+60h+lpData], rax; lpData
0x180010e11  xor     r8d, r8d; Reserved
0x180010e14  lea     rdx, aNetworksizetim; "NetworkSizeTimestamp"
0x180010e1b  mov     rcx, rdi; hKey
0x180010e1e  call    cs:__imp_RegSetValueExW
0x180010e24  mov     ebx, eax
0x180010e26  test    eax, eax
0x180010e28  jnz     short loc_180010E5F
0x180010e2a  test    esi, esi
0x180010e2c  jz      short loc_180010E5F
0x180010e2e  lea     rax, [rbp+Data]
0x180010e32  mov     [rsp+60h+cbData], 4; cbData
0x180010e3a  lea     r9d, [rbx+4]; dwType
0x180010e3e  mov     [rsp+60h+lpData], rax; lpData
0x180010e43  xor     r8d, r8d; Reserved
0x180010e46  mov     [rbp+Data], 1
0x180010e4d  lea     rdx, aNetworksizeeve; "NetworkSizeEverDisqualified"
0x180010e54  mov     rcx, rdi; hKey
0x180010e57  call    cs:__imp_RegSetValueExW
0x180010e5d  mov     ebx, eax
0x180010e5f  test    rdi, rdi
0x180010e62  jz      short loc_180010E75
0x180010e64  mov     rcx, rdi; hKey
0x180010e67  call    cs:__imp_RegCloseKey
0x180010e6d  xor     edi, edi
0x180010e6f  jmp     short loc_180010E75
0x180010e71  mov     rdi, [rbp+hKey]
0x180010e75  mov     rcx, cs:WPP_GLOBAL_Control
0x180010e7c  cmp     rcx, r12
0x180010e7f  jz      short loc_180010E9C
0x180010e81  test    byte ptr [rcx+1Ch], 20h
0x180010e85  jz      short loc_180010E9C
0x180010e87  mov     rcx, [rcx+10h]
0x180010e8b  lea     r8, WPP_1de612464331343acbc2280e70e7e1cd_Traceguids
0x180010e92  mov     edx, 1Eh
0x180010e97  call    WPP_SF_
0x180010e9c  test    ebx, ebx
0x180010e9e  jle     short loc_180010EA9
0x180010ea0  movzx   ebx, bx
0x180010ea3  or      ebx, 80070000h
0x180010ea9  test    rdi, rdi
0x180010eac  jz      short loc_180010EB7
0x180010eae  mov     rcx, rdi; hKey
0x180010eb1  call    cs:__imp_RegCloseKey
0x180010eb7  lea     r11, [rsp+60h+var_s0]
0x180010ebc  mov     eax, ebx
0x180010ebe  mov     rbx, [r11+20h]
0x180010ec2  mov     rsi, [r11+28h]
0x180010ec6  mov     rsp, r11
0x180010ec9  pop     r12
0x180010ecb  pop     rdi
0x180010ecc  pop     rbp
0x180010ecd  retn
```
