# RelativePanelHelper::GetDevicePanelID(ushort const *,HSTRING__ * *)

- ea: `0x180062814`
- end: `0x1800629dd`
- name: `?GetDevicePanelID@RelativePanelHelper@@SAJPEBGPEAPEAUHSTRING__@@@Z`
- size: `457`
- prototype: `__int64 __fastcall(LPCWSTR pszDeviceInterface, HSTRING *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180061984`

## callees

- `0x180005fa0`
- `0x180044f30`
- `0x1800626ac`
- `0x180062814`
- `0x1800629e4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180062937`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180062937`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x1800628d0`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x1800628d0`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x18006290c`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x18006290c`

## pseudocode

```c
__int64 __fastcall RelativePanelHelper::GetDevicePanelID(LPCWSTR pszDeviceInterface, HSTRING *a2)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  HRESULT ObjectProperties; // eax
  __int64 v7; // rdx
  __int64 Property; // rax
  const WCHAR *v9; // rcx
  __int64 v10; // rdx
  unsigned int v12; // [rsp+40h] [rbp-40h] BYREF
  __int64 v13; // [rsp+48h] [rbp-38h] BYREF
  HSTRING string; // [rsp+50h] [rbp-30h] BYREF
  __int128 v15; // [rsp+58h] [rbp-28h] BYREF
  int v16; // [rsp+68h] [rbp-18h]
  int v17; // [rsp+6Ch] [rbp-14h]
  __int64 v18; // [rsp+70h] [rbp-10h]

  v13 = 0;
  v12 = 0;
  v16 = 2;
  v17 = 0;
  v18 = 0;
  v15 = DEVPKEY_Device_PanelId;
  if ( pszDeviceInterface )
  {
    if ( !a2 )
    {
      v4 = -2147467261;
      if ( !g_wppLevels )
        return v4;
      v5 = 11;
      goto LABEL_4;
    }
    ObjectProperties = DevGetObjectProperties(1, pszDeviceInterface, 0, 1, &v15, &v12, &v13);
    v4 = ObjectProperties;
    if ( ObjectProperties >= 0 )
    {
      Property = DevFindProperty(&DEVPKEY_Device_PanelId, 0, 0, v12, v13);
      if ( Property && *(_DWORD *)(Property + 32) == 18 && (v9 = *(const WCHAR **)(Property + 40)) != 0 )
      {
        v10 = -1;
        do
          ++v10;
        while ( v9[v10] );
        ObjectProperties = WindowsCreateString(v9, v10, a2);
        v4 = ObjectProperties;
        if ( ObjectProperties >= 0 || !g_wppLevels )
          return v4;
        v7 = 13;
      }
      else
      {
        string = 0;
        ObjectProperties = RelativePanelHelper::GetDeviceInstanceIdFromInterfacePath(pszDeviceInterface, &string);
        v4 = ObjectProperties;
        if ( ObjectProperties >= 0 )
        {
          ObjectProperties = RelativePanelHelper::GetDevicePanelIDFromDeviceInstanceId(string, a2);
          v4 = ObjectProperties;
          if ( ObjectProperties >= 0 || !g_wppLevels )
            return v4;
          v7 = 15;
        }
        else
        {
          if ( !g_wppLevels )
            return v4;
          v7 = 14;
        }
      }
    }
    else
    {
      if ( !g_wppLevels )
        return v4;
      v7 = 12;
    }
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      WPP_aee6aa9be8a63b0b8ddb6c6384966d29_Traceguids,
      0,
      ObjectProperties);
    return v4;
  }
  v4 = -2147024809;
  if ( g_wppLevels )
  {
    v5 = 10;
LABEL_4:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, WPP_aee6aa9be8a63b0b8ddb6c6384966d29_Traceguids, 0, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x180062814  mov     [rsp-18h+arg_10], rbx
0x180062819  mov     [rsp-18h+arg_18], rsi
0x18006281e  push    rbp
0x18006281f  push    rdi
0x180062820  push    r14
0x180062822  mov     rbp, rsp
0x180062825  sub     rsp, 80h
0x18006282c  mov     rax, cs:__security_cookie
0x180062833  xor     rax, rsp
0x180062836  mov     [rbp+var_8], rax
0x18006283a  movups  xmm0, cs:DEVPKEY_Device_PanelId
0x180062841  mov     eax, cs:dword_18007E2D0
0x180062847  xor     r14d, r14d
0x18006284a  mov     [rbp+var_38], r14
0x18006284e  mov     rdi, rdx
0x180062851  mov     [rbp+var_40], r14d
0x180062855  mov     rsi, rcx
0x180062858  mov     [rbp+var_18], eax
0x18006285b  mov     [rbp+var_14], r14d
0x18006285f  mov     [rbp+var_10], r14
0x180062863  movups  [rbp+var_28], xmm0
0x180062867  test    rcx, rcx
0x18006286a  jnz     short loc_18006288A
0x18006286c  mov     ebx, 80070057h
0x180062871  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180062878  jb      loc_1800629B7
0x18006287e  lea     edx, [rcx+0Ah]
0x180062881  mov     dword ptr [rsp+80h+var_60], ebx
0x180062885  jmp     loc_18006299D
0x18006288a  test    rdi, rdi
0x18006288d  jnz     short loc_1800628A6
0x18006288f  mov     ebx, 80004003h
0x180062894  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006289b  jb      loc_1800629B7
0x1800628a1  lea     edx, [rdi+0Bh]
0x1800628a4  jmp     short loc_180062881
0x1800628a6  lea     rax, [rbp+var_38]
0x1800628aa  mov     r9d, 1
0x1800628b0  mov     [rsp+80h+var_50], rax
0x1800628b5  xor     r8d, r8d
0x1800628b8  lea     rax, [rbp+var_40]
0x1800628bc  mov     rdx, rsi
0x1800628bf  mov     [rsp+80h+var_58], rax
0x1800628c4  mov     ecx, r9d
0x1800628c7  lea     rax, [rbp+var_28]
0x1800628cb  mov     [rsp+80h+var_60], rax
0x1800628d0  call    cs:__imp_DevGetObjectProperties
0x1800628d6  mov     ebx, eax
0x1800628d8  test    eax, eax
0x1800628da  jns     short loc_1800628F3
0x1800628dc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800628e3  jb      loc_1800629B7
0x1800628e9  mov     edx, 0Ch
0x1800628ee  jmp     loc_180062999
0x1800628f3  mov     rax, [rbp+var_38]
0x1800628f7  lea     rcx, DEVPKEY_Device_PanelId
0x1800628fe  mov     r9d, [rbp+var_40]
0x180062902  xor     r8d, r8d
0x180062905  xor     edx, edx
0x180062907  mov     [rsp+80h+var_60], rax
0x18006290c  call    cs:__imp_DevFindProperty
0x180062912  test    rax, rax
0x180062915  jz      short loc_180062953
0x180062917  cmp     dword ptr [rax+20h], 12h
0x18006291b  jnz     short loc_180062953
0x18006291d  mov     rcx, [rax+28h]; sourceString
0x180062921  test    rcx, rcx
0x180062924  jz      short loc_180062953
0x180062926  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18006292a  inc     rdx; length
0x18006292d  cmp     [rcx+rdx*2], r14w
0x180062932  jnz     short loc_18006292A
0x180062934  mov     r8, rdi; string
0x180062937  call    cs:__imp_WindowsCreateString
0x18006293d  mov     ebx, eax
0x18006293f  test    eax, eax
0x180062941  jns     short loc_1800629B7
0x180062943  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006294a  jb      short loc_1800629B7
0x18006294c  mov     edx, 0Dh
0x180062951  jmp     short loc_180062999
0x180062953  lea     rdx, [rbp+string]; string
0x180062957  mov     [rbp+string], r14
0x18006295b  mov     rcx, rsi; pszDeviceInterface
0x18006295e  call    ?GetDeviceInstanceIdFromInterfacePath@RelativePanelHelper@@SAJPEBGPEAPEAUHSTRING__@@@Z; RelativePanelHelper::GetDeviceInstanceIdFromInterfacePath(ushort const *,HSTRING__ * *)
0x180062963  mov     ebx, eax
0x180062965  test    eax, eax
0x180062967  jns     short loc_180062979
0x180062969  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180062970  jb      short loc_1800629B7
0x180062972  mov     edx, 0Eh
0x180062977  jmp     short loc_180062999
0x180062979  mov     rcx, [rbp+string]; HSTRING
0x18006297d  mov     rdx, rdi; HSTRING *
0x180062980  call    ?GetDevicePanelIDFromDeviceInstanceId@RelativePanelHelper@@SAJPEAUHSTRING__@@PEAPEAU2@@Z; RelativePanelHelper::GetDevicePanelIDFromDeviceInstanceId(HSTRING__ *,HSTRING__ * *)
0x180062985  mov     ebx, eax
0x180062987  test    eax, eax
0x180062989  jns     short loc_1800629B7
0x18006298b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180062992  jb      short loc_1800629B7
0x180062994  mov     edx, 0Fh
0x180062999  mov     dword ptr [rsp+80h+var_60], eax
0x18006299d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800629a4  lea     r8, WPP_aee6aa9be8a63b0b8ddb6c6384966d29_Traceguids
0x1800629ab  xor     r9d, r9d
0x1800629ae  mov     rcx, [rcx+10h]
0x1800629b2  call    WPP_SF_qD
0x1800629b7  mov     eax, ebx
0x1800629b9  mov     rcx, [rbp+var_8]
0x1800629bd  xor     rcx, rsp; StackCookie
0x1800629c0  call    __security_check_cookie
0x1800629c5  lea     r11, [rsp+80h+var_s0]
0x1800629cd  mov     rbx, [r11+30h]
0x1800629d1  mov     rsi, [r11+38h]
0x1800629d5  mov     rsp, r11
0x1800629d8  pop     r14
0x1800629da  pop     rdi
0x1800629db  pop     rbp
0x1800629dc  retn
```
