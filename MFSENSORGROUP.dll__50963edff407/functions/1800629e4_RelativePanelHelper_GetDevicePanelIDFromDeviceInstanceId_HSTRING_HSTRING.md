# RelativePanelHelper::GetDevicePanelIDFromDeviceInstanceId(HSTRING__ *,HSTRING__ * *)

- ea: `0x1800629e4`
- end: `0x180062b64`
- name: `?GetDevicePanelIDFromDeviceInstanceId@RelativePanelHelper@@SAJPEAUHSTRING__@@PEAPEAU2@@Z`
- size: `384`
- prototype: `static int(HSTRING, HSTRING *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180062814`

## callees

- `0x180005fa0`
- `0x180044f30`
- `0x1800629e4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180062a8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180062a8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180062b22`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180062b22`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180062abc`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x180062abc`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x180062af8`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x180062af8`

## pseudocode

```c
__int64 __fastcall RelativePanelHelper::GetDevicePanelIDFromDeviceInstanceId(HSTRING a1, HSTRING *a2)
{
  unsigned int v3; // ebx
  __int64 v4; // rdx
  PCWSTR StringRawBuffer; // rax
  HRESULT ObjectProperties; // eax
  __int64 v7; // rdx
  __int64 Property; // rax
  const WCHAR *v9; // rcx
  __int64 v10; // rdx
  unsigned int v12; // [rsp+40h] [rbp-40h] BYREF
  UINT32 length; // [rsp+44h] [rbp-3Ch] BYREF
  __int64 v14; // [rsp+48h] [rbp-38h] BYREF
  __int128 v15; // [rsp+50h] [rbp-30h] BYREF
  int v16; // [rsp+60h] [rbp-20h]
  int v17; // [rsp+64h] [rbp-1Ch]
  __int64 v18; // [rsp+68h] [rbp-18h]

  v14 = 0;
  v12 = 0;
  length = 0;
  v16 = 2;
  v17 = 0;
  v18 = 0;
  v15 = DEVPKEY_Device_PanelId;
  if ( !a1 )
  {
    v3 = -2147024809;
    if ( g_wppLevels )
    {
      v4 = 16;
LABEL_4:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, WPP_aee6aa9be8a63b0b8ddb6c6384966d29_Traceguids, 0, v3);
      return v3;
    }
    return v3;
  }
  if ( !a2 )
  {
    v3 = -2147467261;
    if ( g_wppLevels )
    {
      v4 = 17;
      goto LABEL_4;
    }
    return v3;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(a1, &length);
  ObjectProperties = DevGetObjectProperties(3, StringRawBuffer, 0, 1, &v15, &v12, &v14);
  v3 = ObjectProperties;
  if ( ObjectProperties < 0 )
  {
    if ( !g_wppLevels )
      return v3;
    v7 = 18;
LABEL_12:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      WPP_aee6aa9be8a63b0b8ddb6c6384966d29_Traceguids,
      0,
      ObjectProperties);
    return v3;
  }
  Property = DevFindProperty(&DEVPKEY_Device_PanelId, 0, 0, v12, v14);
  if ( !Property )
    return (unsigned int)-2147024809;
  if ( *(_DWORD *)(Property + 32) != 18 )
    return (unsigned int)-2147024809;
  v9 = *(const WCHAR **)(Property + 40);
  if ( !v9 )
    return (unsigned int)-2147024809;
  v10 = -1;
  do
    ++v10;
  while ( v9[v10] );
  ObjectProperties = WindowsCreateString(v9, v10, a2);
  v3 = ObjectProperties;
  if ( ObjectProperties < 0 && g_wppLevels )
  {
    v7 = 19;
    goto LABEL_12;
  }
  return v3;
}

```

## disassembly

```asm
0x1800629e4  mov     [rsp-18h+arg_10], rbx
0x1800629e9  push    rbp
0x1800629ea  push    rsi
0x1800629eb  push    rdi
0x1800629ec  mov     rbp, rsp
0x1800629ef  sub     rsp, 80h
0x1800629f6  mov     rax, cs:__security_cookie
0x1800629fd  xor     rax, rsp
0x180062a00  mov     [rbp+var_10], rax
0x180062a04  movups  xmm0, cs:DEVPKEY_Device_PanelId
0x180062a0b  mov     eax, cs:dword_18007E2D0
0x180062a11  xor     esi, esi
0x180062a13  mov     [rbp+var_38], rsi
0x180062a17  mov     rdi, rdx
0x180062a1a  mov     [rbp+var_40], esi
0x180062a1d  mov     [rbp+length], esi
0x180062a20  mov     [rbp+var_20], eax
0x180062a23  mov     [rbp+var_1C], esi
0x180062a26  mov     [rbp+var_18], rsi
0x180062a2a  movups  [rbp+var_30], xmm0
0x180062a2e  test    rcx, rcx
0x180062a31  jnz     short loc_180062A6B
0x180062a33  mov     ebx, 80070057h
0x180062a38  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180062a3f  jb      loc_180062B43
0x180062a45  lea     edx, [rsi+10h]
0x180062a48  mov     dword ptr [rsp+80h+var_60], ebx
0x180062a4c  mov     rcx, cs:WPP_GLOBAL_Control
0x180062a53  lea     r8, WPP_aee6aa9be8a63b0b8ddb6c6384966d29_Traceguids
0x180062a5a  xor     r9d, r9d
0x180062a5d  mov     rcx, [rcx+10h]
0x180062a61  call    WPP_SF_qD
0x180062a66  jmp     loc_180062B43
0x180062a6b  test    rdi, rdi
0x180062a6e  jnz     short loc_180062A87
0x180062a70  mov     ebx, 80004003h
0x180062a75  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180062a7c  jb      loc_180062B43
0x180062a82  lea     edx, [rdi+11h]
0x180062a85  jmp     short loc_180062A48
0x180062a87  lea     rdx, [rbp+length]; length
0x180062a8b  call    cs:__imp_WindowsGetStringRawBuffer
0x180062a91  lea     rcx, [rbp+var_38]
0x180062a95  mov     r9d, 1
0x180062a9b  mov     [rsp+80h+var_50], rcx
0x180062aa0  xor     r8d, r8d
0x180062aa3  lea     rcx, [rbp+var_40]
0x180062aa7  mov     rdx, rax
0x180062aaa  mov     [rsp+80h+var_58], rcx
0x180062aaf  lea     rcx, [rbp+var_30]
0x180062ab3  mov     [rsp+80h+var_60], rcx
0x180062ab8  lea     ecx, [r9+2]
0x180062abc  call    cs:__imp_DevGetObjectProperties
0x180062ac2  mov     ebx, eax
0x180062ac4  test    eax, eax
0x180062ac6  jns     short loc_180062ADF
0x180062ac8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180062acf  jb      short loc_180062B43
0x180062ad1  mov     edx, 12h
0x180062ad6  mov     dword ptr [rsp+80h+var_60], eax
0x180062ada  jmp     loc_180062A4C
0x180062adf  mov     rax, [rbp+var_38]
0x180062ae3  lea     rcx, DEVPKEY_Device_PanelId
0x180062aea  mov     r9d, [rbp+var_40]
0x180062aee  xor     r8d, r8d
0x180062af1  xor     edx, edx
0x180062af3  mov     [rsp+80h+var_60], rax
0x180062af8  call    cs:__imp_DevFindProperty
0x180062afe  test    rax, rax
0x180062b01  jz      short loc_180062B3E
0x180062b03  cmp     dword ptr [rax+20h], 12h
0x180062b07  jnz     short loc_180062B3E
0x180062b09  mov     rcx, [rax+28h]; sourceString
0x180062b0d  test    rcx, rcx
0x180062b10  jz      short loc_180062B3E
0x180062b12  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180062b16  inc     rdx; length
0x180062b19  cmp     [rcx+rdx*2], si
0x180062b1d  jnz     short loc_180062B16
0x180062b1f  mov     r8, rdi; string
0x180062b22  call    cs:__imp_WindowsCreateString
0x180062b28  mov     ebx, eax
0x180062b2a  test    eax, eax
0x180062b2c  jns     short loc_180062B43
0x180062b2e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180062b35  jb      short loc_180062B43
0x180062b37  mov     edx, 13h
0x180062b3c  jmp     short loc_180062AD6
0x180062b3e  mov     ebx, 80070057h
0x180062b43  mov     eax, ebx
0x180062b45  mov     rcx, [rbp+var_10]
0x180062b49  xor     rcx, rsp; StackCookie
0x180062b4c  call    __security_check_cookie
0x180062b51  mov     rbx, [rsp+80h+arg_10]
0x180062b59  add     rsp, 80h
0x180062b60  pop     rdi
0x180062b61  pop     rsi
0x180062b62  pop     rbp
0x180062b63  retn
```
