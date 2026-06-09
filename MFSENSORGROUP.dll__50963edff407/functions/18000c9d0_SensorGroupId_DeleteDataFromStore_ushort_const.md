# SensorGroupId::DeleteDataFromStore(ushort const *)

- ea: `0x18000c9d0`
- end: `0x18000cb2a`
- name: `?DeleteDataFromStore@SensorGroupId@@UEAAJPEBG@Z`
- size: `346`
- prototype: `__int64 __fastcall(SensorGroupId *this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x180005fa0`
- `0x18000c9d0`
- `0x18000d1c4`
- `0x18000ec30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ca82`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ca82`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c9ef`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c9ef`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000ca45`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000ca45`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ca79`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ca79`

## pseudocode

```c
__int64 __fastcall SensorGroupId::DeleteDataFromStore(SensorGroupId *this, const unsigned __int16 *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // r14
  char *v5; // rsi
  const unsigned __int16 *v6; // rcx
  int v7; // eax
  HKEY v8; // rbx
  signed int v9; // edi
  LSTATUS v10; // eax
  __int64 v12; // rdx
  HKEY hKey; // [rsp+50h] [rbp+8h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v5 = (char *)this - 8;
  if ( SensorGroupId::InternalIsEmpty((SensorGroupId *)((char *)this - 8)) )
  {
    v9 = -1072875850;
    if ( !g_wppLevels )
      goto LABEL_11;
    v12 = 131;
LABEL_16:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v12,
      &WPP_c6ec3a891c39353f20252a4447583601_Traceguids,
      (char *)this - 8,
      v9);
    goto LABEL_11;
  }
  if ( !a2 )
  {
    v9 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_11;
    v12 = 132;
    goto LABEL_16;
  }
  v6 = (const unsigned __int16 *)*((_QWORD *)this + 140);
  hKey = 0;
  v7 = OpenSensorGroupRegistryKey(v6, 131334, 0, &hKey);
  v8 = hKey;
  v9 = v7;
  if ( v7 < 0 )
  {
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 133, &WPP_c6ec3a891c39353f20252a4447583601_Traceguids, v5, v7);
  }
  else
  {
    v10 = RegDeleteValueW(hKey, a2);
    v9 = v10;
    if ( v10 )
    {
      if ( v10 > 0 )
        v9 = (unsigned __int16)v10 | 0x80070000;
      if ( v9 < 0 && g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 134, &WPP_c6ec3a891c39353f20252a4447583601_Traceguids, v5, v9);
    }
    else
    {
      v9 = 0;
    }
  }
  if ( v8 )
    RegCloseKey(v8);
LABEL_11:
  LeaveCriticalSection(v2);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18000c9d0  mov     [rsp+arg_8], rbx
0x18000c9d5  mov     [rsp+arg_10], rbp
0x18000c9da  push    rsi
0x18000c9db  push    rdi
0x18000c9dc  push    r14
0x18000c9de  sub     rsp, 30h
0x18000c9e2  lea     r14, [rcx+10h]
0x18000c9e6  mov     rbx, rcx
0x18000c9e9  mov     rcx, r14; lpCriticalSection
0x18000c9ec  mov     rbp, rdx
0x18000c9ef  call    cs:__imp_EnterCriticalSection
0x18000c9f5  lea     rsi, [rbx-8]
0x18000c9f9  mov     rcx, rsi; this
0x18000c9fc  call    ?InternalIsEmpty@SensorGroupId@@IEAA_NXZ; SensorGroupId::InternalIsEmpty(void)
0x18000ca01  test    al, al
0x18000ca03  jnz     loc_18000CAB1
0x18000ca09  test    rbp, rbp
0x18000ca0c  jz      loc_18000CAEB
0x18000ca12  mov     rcx, [rbx+460h]; unsigned __int16 *
0x18000ca19  lea     r9, [rsp+48h+hKey]; HKEY *
0x18000ca1e  xor     r8d, r8d; bool *
0x18000ca21  mov     [rsp+48h+hKey], 0
0x18000ca2a  mov     edx, 20106h; unsigned int
0x18000ca2f  call    ?OpenSensorGroupRegistryKey@@YAJPEBGKPEA_NPEAPEAUHKEY__@@@Z; OpenSensorGroupRegistryKey(ushort const *,ulong,bool *,HKEY__ * *)
0x18000ca34  mov     rbx, [rsp+48h+hKey]
0x18000ca39  mov     edi, eax
0x18000ca3b  test    eax, eax
0x18000ca3d  js      short loc_18000CA9D
0x18000ca3f  mov     rdx, rbp; lpValueName
0x18000ca42  mov     rcx, rbx; hKey
0x18000ca45  call    cs:__imp_RegDeleteValueW
0x18000ca4b  mov     edi, eax
0x18000ca4d  test    eax, eax
0x18000ca4f  jz      loc_18000CB23
0x18000ca55  jle     short loc_18000CA60
0x18000ca57  movzx   edi, ax
0x18000ca5a  or      edi, 80070000h
0x18000ca60  test    edi, edi
0x18000ca62  jns     short loc_18000CA71
0x18000ca64  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000ca6b  jnb     loc_18000CAFB
0x18000ca71  test    rbx, rbx
0x18000ca74  jz      short loc_18000CA7F
0x18000ca76  mov     rcx, rbx; hKey
0x18000ca79  call    cs:__imp_RegCloseKey
0x18000ca7f  mov     rcx, r14; lpCriticalSection
0x18000ca82  call    cs:__imp_LeaveCriticalSection
0x18000ca88  mov     rbx, [rsp+48h+arg_8]
0x18000ca8d  mov     eax, edi
0x18000ca8f  mov     rbp, [rsp+48h+arg_10]
0x18000ca94  add     rsp, 30h
0x18000ca98  pop     r14
0x18000ca9a  pop     rdi
0x18000ca9b  pop     rsi
0x18000ca9c  retn
0x18000ca9d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000caa4  jb      short loc_18000CA71
0x18000caa6  mov     edx, 85h
0x18000caab  mov     [rsp+48h+var_28], eax
0x18000caaf  jmp     short loc_18000CB04
0x18000cab1  mov     edi, 0C00D36B6h
0x18000cab6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000cabd  jb      short loc_18000CA7F
0x18000cabf  mov     edx, 83h
0x18000cac4  jmp     short loc_18000CACB
0x18000cac6  mov     edx, 84h
0x18000cacb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cad2  lea     r8, WPP_c6ec3a891c39353f20252a4447583601_Traceguids
0x18000cad9  mov     r9, rsi
0x18000cadc  mov     [rsp+48h+var_28], edi
0x18000cae0  mov     rcx, [rcx+10h]
0x18000cae4  call    WPP_SF_qD
0x18000cae9  jmp     short loc_18000CA7F
0x18000caeb  mov     edi, 80070057h
0x18000caf0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000caf7  jb      short loc_18000CA7F
0x18000caf9  jmp     short loc_18000CAC6
0x18000cafb  mov     edx, 86h
0x18000cb00  mov     [rsp+48h+var_28], edi
0x18000cb04  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cb0b  lea     r8, WPP_c6ec3a891c39353f20252a4447583601_Traceguids
0x18000cb12  mov     r9, rsi
0x18000cb15  mov     rcx, [rcx+10h]
0x18000cb19  call    WPP_SF_qD
0x18000cb1e  jmp     loc_18000CA71
0x18000cb23  xor     edi, edi
0x18000cb25  jmp     loc_18000CA71
```
