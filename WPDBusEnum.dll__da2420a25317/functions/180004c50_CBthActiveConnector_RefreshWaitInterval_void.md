# CBthActiveConnector::_RefreshWaitInterval(void)

- ea: `0x180004c50`
- end: `0x180004efb`
- name: `?_RefreshWaitInterval@CBthActiveConnector@@AEAAJXZ`
- size: `683`
- prototype: `__int64 __fastcall(CBthActiveConnector *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180004620`
- `0x180006360`

## callees

- `0x180004c50`
- `0x180007f28`
- `0x18000dfd4`
- `0x18000e080`
- `0x18000e1b8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004d54`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004d54`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004cd6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004cd6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004d0a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004d0a`

## string_xrefs

- `0x180004cc8`: `System\CurrentControlSet\Services\WpdBusEnum\BthActiveConnect`
- `0x180004eb3`: `System\CurrentControlSet\Services\WpdBusEnum\BthActiveConnect`

## pseudocode

```c
__int64 __fastcall CBthActiveConnector::_RefreshWaitInterval(CBthActiveConnector *this)
{
  bool v1; // zf
  const WCHAR *v2; // rdi
  unsigned int v3; // esi
  LSTATUS v6; // eax
  signed int v7; // ebp
  LSTATUS v8; // eax
  __int64 v9; // r9
  CPnPNotification *v10; // rcx
  __int64 v11; // rdx
  DWORD Type; // [rsp+60h] [rbp+8h] BYREF
  unsigned int Data; // [rsp+68h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+18h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+20h] BYREF

  cbData = 4;
  v1 = *((_DWORD *)this + 2) == 1;
  v2 = L"DCInterval";
  v3 = 0;
  hKey = 0;
  Data = 0;
  Type = 0;
  if ( !v1 )
    v2 = L"ACInterval";
  if ( *((_DWORD *)this + 3) )
  {
    if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, &WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids);
    }
    return 0;
  }
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\WpdBusEnum\\BthActiveConnect",
         0,
         0x20019u,
         &hKey);
  v7 = v6;
  if ( !v6 )
  {
    v8 = RegQueryValueExW(hKey, v2, 0, &Type, (LPBYTE)&Data, &cbData);
    if ( v8 )
    {
      if ( v8 > 0 )
        v3 = (unsigned __int16)v8 | 0x80070000;
      else
        v3 = v8;
      if ( (int)(v3 + 0x80000000) >= 0
        && v3 != -2147024894
        && WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          55,
          (unsigned int)&WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids,
          (_DWORD)v2,
          v3);
      }
      goto LABEL_13;
    }
    v9 = Type;
    if ( Type == 4 )
    {
      if ( 1000 * Data >= Data )
      {
        _InterlockedExchange((volatile __int32 *)this, 1000 * Data);
        if ( WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            53,
            &WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids,
            *(unsigned int *)this);
        }
        goto LABEL_13;
      }
      v3 = -2147024362;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CPnPNotification *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
LABEL_13:
        RegCloseKey(hKey);
        return v3;
      }
      v11 = 52;
      v9 = 4;
    }
    else
    {
      v3 = -2147418113;
      v10 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CPnPNotification *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      {
        goto LABEL_13;
      }
      v11 = 54;
    }
    WPP_SF_dd(*((_QWORD *)v10 + 2), v11, &WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids, v9, v3);
    goto LABEL_13;
  }
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( v7 < 0
    && WPP_GLOBAL_Control != (CPnPNotification *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      56,
      (unsigned int)&WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids,
      (unsigned int)L"System\\CurrentControlSet\\Services\\WpdBusEnum\\BthActiveConnect",
      v7);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180004c50  push    rbx
0x180004c52  push    rsi
0x180004c53  push    rdi
0x180004c54  sub     rsp, 40h
0x180004c58  xor     eax, eax
0x180004c5a  mov     [rsp+58h+cbData], 4
0x180004c62  cmp     dword ptr [rcx+8], 1
0x180004c66  lea     rdi, aDcinterval; "DCInterval"
0x180004c6d  mov     esi, eax
0x180004c6f  mov     [rsp+58h+hKey], rax
0x180004c74  mov     [rsp+58h+Data], eax
0x180004c78  mov     rbx, rcx
0x180004c7b  mov     [rsp+58h+Type], eax
0x180004c7f  lea     rax, aAcinterval; "ACInterval"
0x180004c86  cmovnz  rdi, rax
0x180004c8a  cmp     [rcx+0Ch], esi
0x180004c8d  jz      short loc_180004CB0
0x180004c8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180004c96  lea     rax, WPP_GLOBAL_Control
0x180004c9d  cmp     rcx, rax
0x180004ca0  jnz     loc_180004ED4
0x180004ca6  mov     eax, esi
0x180004ca8  add     rsp, 40h
0x180004cac  pop     rdi
0x180004cad  pop     rsi
0x180004cae  pop     rbx
0x180004caf  retn
0x180004cb0  lea     rax, [rsp+58h+hKey]
0x180004cb5  mov     [rsp+58h+var_20], rbp
0x180004cba  mov     r9d, 20019h; samDesired
0x180004cc0  mov     [rsp+58h+phkResult], rax; phkResult
0x180004cc5  xor     r8d, r8d; ulOptions
0x180004cc8  lea     rdx, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Wp"...
0x180004ccf  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004cd6  call    cs:__imp_RegOpenKeyExW
0x180004cdc  mov     ebp, eax
0x180004cde  test    eax, eax
0x180004ce0  jnz     loc_180004D66
0x180004ce6  mov     rcx, [rsp+58h+hKey]; hKey
0x180004ceb  lea     rax, [rsp+58h+cbData]
0x180004cf0  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180004cf5  lea     r9, [rsp+58h+Type]; lpType
0x180004cfa  lea     rax, [rsp+58h+Data]
0x180004cff  xor     r8d, r8d; lpReserved
0x180004d02  mov     rdx, rdi; lpValueName
0x180004d05  mov     [rsp+58h+phkResult], rax; lpData
0x180004d0a  call    cs:__imp_RegQueryValueExW
0x180004d10  test    eax, eax
0x180004d12  jnz     short loc_180004D80
0x180004d14  mov     r9d, [rsp+58h+Type]
0x180004d19  cmp     r9d, 4
0x180004d1d  jnz     loc_180004DD5
0x180004d23  imul    ecx, [rsp+58h+Data], 3E8h
0x180004d2b  cmp     ecx, [rsp+58h+Data]
0x180004d2f  jb      short loc_180004D8D
0x180004d31  xchg    ecx, [rbx]
0x180004d33  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d3a  lea     rax, WPP_GLOBAL_Control
0x180004d41  cmp     rcx, rax
0x180004d44  jz      short loc_180004D4F
0x180004d46  test    dword ptr [rcx+1Ch], 800h
0x180004d4d  jnz     short loc_180004DB8
0x180004d4f  mov     rcx, [rsp+58h+hKey]; hKey
0x180004d54  call    cs:__imp_RegCloseKey
0x180004d5a  mov     rbp, [rsp+58h+var_20]
0x180004d5f  mov     eax, esi
0x180004d61  jmp     loc_180004CA8
0x180004d66  jg      loc_180004E80
0x180004d6c  test    ebp, ebp
0x180004d6e  js      loc_180004E8E
0x180004d74  mov     eax, ebp
0x180004d76  mov     rbp, [rsp+58h+var_20]
0x180004d7b  jmp     loc_180004CA8
0x180004d80  jg      loc_180004E19
0x180004d86  mov     esi, eax
0x180004d88  jmp     loc_180004E22
0x180004d8d  mov     esi, 80070216h
0x180004d92  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d99  lea     rax, WPP_GLOBAL_Control
0x180004da0  cmp     rcx, rax
0x180004da3  jz      short loc_180004D4F
0x180004da5  test    byte ptr [rcx+1Ch], 2
0x180004da9  jz      short loc_180004D4F
0x180004dab  mov     edx, 34h ; '4'
0x180004db0  mov     r9d, 4
0x180004db6  jmp     short loc_180004E00
0x180004db8  mov     r9d, [rbx]
0x180004dbb  lea     r8, WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids
0x180004dc2  mov     rcx, [rcx+10h]
0x180004dc6  mov     edx, 35h ; '5'
0x180004dcb  call    WPP_SF_d
0x180004dd0  jmp     loc_180004D4F
0x180004dd5  mov     esi, 8000FFFFh
0x180004dda  mov     rcx, cs:WPP_GLOBAL_Control
0x180004de1  lea     rax, WPP_GLOBAL_Control
0x180004de8  cmp     rcx, rax
0x180004deb  jz      loc_180004D4F
0x180004df1  test    byte ptr [rcx+1Ch], 2
0x180004df5  jz      loc_180004D4F
0x180004dfb  mov     edx, 36h ; '6'
0x180004e00  mov     rcx, [rcx+10h]
0x180004e04  lea     r8, WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids
0x180004e0b  mov     dword ptr [rsp+58h+phkResult], esi
0x180004e0f  call    WPP_SF_dd
0x180004e14  jmp     loc_180004D4F
0x180004e19  movzx   esi, ax
0x180004e1c  or      esi, 80070000h
0x180004e22  mov     ecx, 80000000h
0x180004e27  lea     eax, [rsi+rcx]
0x180004e2a  test    ecx, eax
0x180004e2c  jnz     loc_180004D4F
0x180004e32  cmp     esi, 80070002h
0x180004e38  jz      loc_180004D4F
0x180004e3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e45  lea     rax, WPP_GLOBAL_Control
0x180004e4c  cmp     rcx, rax
0x180004e4f  jz      loc_180004D4F
0x180004e55  test    byte ptr [rcx+1Ch], 2
0x180004e59  jz      loc_180004D4F
0x180004e5f  mov     rcx, [rcx+10h]
0x180004e63  lea     r8, WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids
0x180004e6a  mov     edx, 37h ; '7'
0x180004e6f  mov     dword ptr [rsp+58h+phkResult], esi
0x180004e73  mov     r9, rdi
0x180004e76  call    WPP_SF_Sd
0x180004e7b  jmp     loc_180004D4F
0x180004e80  movzx   ebp, ax
0x180004e83  or      ebp, 80070000h
0x180004e89  jmp     loc_180004D6C
0x180004e8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e95  lea     rax, WPP_GLOBAL_Control
0x180004e9c  cmp     rcx, rax
0x180004e9f  jz      loc_180004D74
0x180004ea5  test    byte ptr [rcx+1Ch], 2
0x180004ea9  jz      loc_180004D74
0x180004eaf  mov     rcx, [rcx+10h]
0x180004eb3  lea     r9, aSystemCurrentc; "System\\CurrentControlSet\\Services\\Wp"...
0x180004eba  mov     edx, 38h ; '8'
0x180004ebf  mov     dword ptr [rsp+58h+phkResult], ebp
0x180004ec3  lea     r8, WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids
0x180004eca  call    WPP_SF_Sd
0x180004ecf  jmp     loc_180004D74
0x180004ed4  test    dword ptr [rcx+1Ch], 800h
0x180004edb  jz      loc_180004CA6
0x180004ee1  mov     rcx, [rcx+10h]
0x180004ee5  lea     r8, WPP_0f88d5a9d8393f53423a785fee9a5214_Traceguids
0x180004eec  mov     edx, 39h ; '9'
0x180004ef1  call    WPP_SF_
0x180004ef6  jmp     loc_180004CA6
```
