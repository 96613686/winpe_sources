# KampReadConfiguredKeepaliveFloorTime

- ea: `0x180016920`
- end: `0x180016a60`
- name: `KampReadConfiguredKeepaliveFloorTime`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800159b8`

## callees

- `0x18000a0a0`
- `0x180016920`
- `0x180016d98`
- `0x18001c500`
- `0x180020494`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016994`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180016994`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016a16`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180016a16`

## string_xrefs

- `0x1800169c3`: `Kam: keepalive floor configuration `
- `0x1800169f9`: `Kam: keepalive floor configuration on cell`

## pseudocode

```c
__int64 KampReadConfiguredKeepaliveFloorTime()
{
  const WCHAR *v0; // rdx
  unsigned int Integer2; // eax
  __int64 v2; // rdx
  __int64 v3; // rcx
  __int64 result; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids);
  }
  v0 = (const WCHAR *)&lpSubKey;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  if ( *((_QWORD *)&xmmword_18004D9D0 + 1) > 7u )
    v0 = lpSubKey;
  RegOpenKeyExW(HKEY_LOCAL_MACHINE, v0, 0, 0x20019u, &hKey);
  Integer2 = GetInteger2(hKey, L"KeepAliveFloorTime", 1);
  g_KamFloorTime = Integer2;
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    McTemplateU0zq_EventWriteTransfer(v3, v2, L"Kam: keepalive floor configuration ", Integer2);
  result = GetInteger2(hKey, L"KeepAliveFloorTimeOnCell", (unsigned int)g_KamFloorTimeOnCell);
  g_KamFloorTimeOnCell = result;
  if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
  {
    McTemplateU0zq_EventWriteTransfer(v6, v5, L"Kam: keepalive floor configuration on cell", (unsigned int)result);
    result = (unsigned int)g_KamFloorTimeOnCell;
  }
  if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
  {
    RegCloseKey(hKey);
    result = (unsigned int)g_KamFloorTimeOnCell;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    return WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids);
  }
  return result;
}

```

## disassembly

```asm
0x180016920  push    rdi
0x180016922  sub     rsp, 30h
0x180016926  mov     rcx, cs:WPP_GLOBAL_Control
0x18001692d  lea     rdi, WPP_GLOBAL_Control
0x180016934  cmp     rcx, rdi
0x180016937  jz      short loc_18001695A
0x180016939  test    byte ptr [rcx+1Ch], 1
0x18001693d  jz      short loc_18001695A
0x18001693f  cmp     byte ptr [rcx+19h], 6
0x180016943  jb      short loc_18001695A
0x180016945  mov     rcx, [rcx+10h]
0x180016949  lea     r8, WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids
0x180016950  mov     edx, 0Eh
0x180016955  call    WPP_SF_
0x18001695a  cmp     qword ptr cs:xmmword_18004D9D0+8, 7
0x180016962  lea     rax, [rsp+38h+hKey]
0x180016967  lea     rdx, lpSubKey
0x18001696e  mov     [rsp+38h+hKey], 0FFFFFFFFFFFFFFFFh
0x180016977  cmova   rdx, qword ptr cs:lpSubKey; lpSubKey
0x18001697f  mov     r9d, 20019h; samDesired
0x180016985  xor     r8d, r8d; ulOptions
0x180016988  mov     [rsp+38h+phkResult], rax; phkResult
0x18001698d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180016994  call    cs:__imp_RegOpenKeyExW
0x18001699a  mov     rcx, [rsp+38h+hKey]
0x18001699f  lea     rdx, aKeepalivefloor; "KeepAliveFloorTime"
0x1800169a6  mov     r8d, 1
0x1800169ac  call    GetInteger2
0x1800169b1  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800169b8  mov     cs:g_KamFloorTime, eax
0x1800169be  jz      short loc_1800169CF
0x1800169c0  mov     r9d, eax
0x1800169c3  lea     r8, aKamKeepaliveFl; "Kam: keepalive floor configuration "
0x1800169ca  call    McTemplateU0zq_EventWriteTransfer
0x1800169cf  mov     r8d, cs:g_KamFloorTimeOnCell
0x1800169d6  lea     rdx, aKeepalivefloor_0; "KeepAliveFloorTimeOnCell"
0x1800169dd  mov     rcx, [rsp+38h+hKey]
0x1800169e2  call    GetInteger2
0x1800169e7  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800169ee  mov     cs:g_KamFloorTimeOnCell, eax
0x1800169f4  jz      short loc_180016A0B
0x1800169f6  mov     r9d, eax
0x1800169f9  lea     r8, aKamKeepaliveFl_0; "Kam: keepalive floor configuration on c"...
0x180016a00  call    McTemplateU0zq_EventWriteTransfer
0x180016a05  mov     eax, cs:g_KamFloorTimeOnCell
0x180016a0b  mov     rcx, [rsp+38h+hKey]; hKey
0x180016a10  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180016a14  jz      short loc_180016A22
0x180016a16  call    cs:__imp_RegCloseKey
0x180016a1c  mov     eax, cs:g_KamFloorTimeOnCell
0x180016a22  mov     rcx, cs:WPP_GLOBAL_Control
0x180016a29  cmp     rcx, rdi
0x180016a2c  jz      short loc_180016A5A
0x180016a2e  test    byte ptr [rcx+1Ch], 1
0x180016a32  jz      short loc_180016A5A
0x180016a34  cmp     byte ptr [rcx+19h], 6
0x180016a38  jb      short loc_180016A5A
0x180016a3a  mov     r9d, cs:g_KamFloorTime
0x180016a41  lea     r8, WPP_9a5d6e18e6df3235d52b8c1fc51e833d_Traceguids
0x180016a48  mov     rcx, [rcx+10h]
0x180016a4c  mov     edx, 0Fh
0x180016a51  mov     dword ptr [rsp+38h+phkResult], eax
0x180016a55  call    WPP_SF_dd
0x180016a5a  add     rsp, 30h
0x180016a5e  pop     rdi
0x180016a5f  retn
```
