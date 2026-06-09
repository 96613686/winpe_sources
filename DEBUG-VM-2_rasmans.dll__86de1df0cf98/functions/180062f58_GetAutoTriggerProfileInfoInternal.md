# GetAutoTriggerProfileInfoInternal

- ea: `0x180062f58`
- end: `0x180063231`
- name: `GetAutoTriggerProfileInfoInternal`
- size: `729`
- prototype: `__int64 __usercall@<rax>(PVOID pvData@<rcx>, PVOID)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x1800635cc`

## callees

- `0x180005e0c`
- `0x180005e34`
- `0x180062f58`
- `0x180066490`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180063089`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800630f0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180063173`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180063089`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800630f0`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180063173`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006301b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006301b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800631dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800631dc`

## string_xrefs

- `0x180062ff0`: `SYSTEM\CurrentControlSet\Services\RasMan\Config`
- `0x180063001`: `OSDATA\SYSTEM\CurrentControlSet\Services\RasMan\Config`
- `0x180063065`: `AutoTriggerProfilePhonebookPath`

## pseudocode

```c
__int64 __fastcall GetAutoTriggerProfileInfoInternal(_WORD *pvData, __int64 a2, _WORD *a3, DWORD a4, _OWORD *a5)
{
  struct _LIST_ENTRY *v7; // rcx
  int v8; // eax
  const WCHAR *v9; // rdx
  unsigned int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // r9
  unsigned int ValueW; // eax
  unsigned int v15; // eax
  HKEY v16; // rcx
  PVOID pvDataa; // [rsp+28h] [rbp-18h]
  HKEY hkey; // [rsp+70h] [rbp+30h] BYREF
  DWORD pcbData; // [rsp+88h] [rbp+48h] BYREF

  pcbData = a4;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x1000) != 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control[1].Flink, 77, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  hkey = 0;
  pcbData = 0;
  if ( pvData && a3 )
  {
    *pvData = 0;
    *a3 = 0;
    v8 = StateSepEnabled();
    v9 = L"OSDATA\\SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
    if ( !v8 )
      v9 = L"SYSTEM\\CurrentControlSet\\Services\\RasMan\\Config";
    v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v9, 0, 0x20019u, &hkey);
    v11 = v10;
    if ( v10 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x1000) != 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        v12 = 79;
LABEL_14:
        v13 = v10;
LABEL_36:
        WPP_SF_d(v7[1].Flink, v12, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, v13);
LABEL_37:
        v7 = WPP_GLOBAL_Control;
        goto LABEL_38;
      }
      goto LABEL_38;
    }
    pcbData = 522;
    ValueW = RegGetValueW(hkey, 0, L"AutoTriggerProfilePhonebookPath", 2u, 0, pvData, &pcbData);
    if ( ValueW
      && WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x1000) != 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 82, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, ValueW);
    }
    pcbData = 514;
    v15 = RegGetValueW(hkey, 0, L"AutoTriggerProfileEntryName", 2u, 0, a3, &pcbData);
    v11 = v15;
    if ( v15 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x1000) == 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
LABEL_26:
        if ( !a5 )
          goto LABEL_38;
        pcbData = 16;
        v16 = hkey;
        pvDataa = a5;
        *a5 = 0;
        v10 = RegGetValueW(v16, 0, L"AutoTriggerProfileGUID", 8u, 0, pvDataa, &pcbData);
        v11 = v10;
        if ( !v10 )
          goto LABEL_37;
        v7 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control[1].Blink) & 0x1000) != 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          v12 = 84;
          goto LABEL_14;
        }
LABEL_38:
        if ( hkey )
        {
          RegCloseKey(hkey);
          v7 = WPP_GLOBAL_Control;
          hkey = 0;
        }
        goto LABEL_40;
      }
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 83, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, v15);
    }
    v7 = WPP_GLOBAL_Control;
    goto LABEL_26;
  }
  v11 = 87;
  if ( v7 == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
    return v11;
  if ( (HIDWORD(v7[1].Blink) & 0x1000) != 0 && BYTE1(v7[1].Blink) >= 2u )
  {
    v12 = 78;
    v13 = 87;
    goto LABEL_36;
  }
LABEL_40:
  if ( v7 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && (HIDWORD(v7[1].Blink) & 0x1000) != 0
    && BYTE1(v7[1].Blink) >= 6u )
  {
    WPP_SF_d(v7[1].Flink, 85, &WPP_35bda7d4026d31c4197dea276c13321c_Traceguids, v11);
  }
  return v11;
}

```

## disassembly

```asm
0x180062f58  mov     [rsp-28h+arg_8], rbx
0x180062f5d  mov     [rsp-28h+arg_10], rsi
0x180062f62  mov     [rsp-28h+arg_18], r9d
0x180062f67  push    rbp
0x180062f68  push    rdi
0x180062f69  push    r12
0x180062f6b  push    r13
0x180062f6d  push    r15
0x180062f6f  mov     rbp, rsp
0x180062f72  sub     rsp, 40h
0x180062f76  mov     rsi, r8
0x180062f79  mov     rdi, rcx
0x180062f7c  mov     rcx, cs:WPP_GLOBAL_Control
0x180062f83  lea     r12, WPP_GLOBAL_Control
0x180062f8a  lea     r13, WPP_35bda7d4026d31c4197dea276c13321c_Traceguids
0x180062f91  mov     r15d, 1000h
0x180062f97  cmp     rcx, r12
0x180062f9a  jz      short loc_180062FC0
0x180062f9c  test    [rcx+1Ch], r15d
0x180062fa0  jz      short loc_180062FC0
0x180062fa2  cmp     byte ptr [rcx+19h], 6
0x180062fa6  jb      short loc_180062FC0
0x180062fa8  mov     rcx, [rcx+10h]
0x180062fac  mov     edx, 4Dh ; 'M'
0x180062fb1  mov     r8, r13
0x180062fb4  call    WPP_SF_
0x180062fb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180062fc0  mov     [rbp+hkey], 0
0x180062fc8  mov     [rbp+arg_18], 0
0x180062fcf  test    rdi, rdi
0x180062fd2  jz      loc_1800631A1
0x180062fd8  test    rsi, rsi
0x180062fdb  jz      loc_1800631A1
0x180062fe1  xor     eax, eax
0x180062fe3  mov     [rdi], ax
0x180062fe6  mov     [rsi], ax
0x180062fe9  call    StateSepEnabled
0x180062fee  test    eax, eax
0x180062ff0  lea     rcx, aSystemCurrentc_21; "SYSTEM\\CurrentControlSet\\Services\\Ra"...
0x180062ff7  lea     rax, [rbp+hkey]
0x180062ffb  mov     r9d, 20019h; samDesired
0x180063001  lea     rdx, aOsdataSystemCu_0; "OSDATA\\SYSTEM\\CurrentControlSet\\Serv"...
0x180063008  mov     [rsp+40h+phkResult], rax; phkResult
0x18006300d  cmovz   rdx, rcx; lpSubKey
0x180063011  xor     r8d, r8d; ulOptions
0x180063014  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006301b  call    cs:__imp_RegOpenKeyExW
0x180063021  mov     ebx, eax
0x180063023  test    eax, eax
0x180063025  jz      short loc_180063058
0x180063027  mov     rcx, cs:WPP_GLOBAL_Control
0x18006302e  cmp     rcx, r12
0x180063031  jz      loc_1800631D0
0x180063037  test    [rcx+1Ch], r15d
0x18006303b  jz      loc_1800631D0
0x180063041  cmp     byte ptr [rcx+19h], 2
0x180063045  jb      loc_1800631D0
0x18006304b  mov     edx, 4Fh ; 'O'
0x180063050  mov     r9d, eax
0x180063053  jmp     loc_1800631BD
0x180063058  mov     rcx, [rbp+hkey]; hkey
0x18006305c  lea     rax, [rbp+arg_18]
0x180063060  mov     [rsp+40h+pcbData], rax; pcbData
0x180063065  lea     r8, aAutotriggerpro_5; "AutoTriggerProfilePhonebookPath"
0x18006306c  mov     [rsp+40h+pvData], rdi; pvData
0x180063071  mov     r9d, 2; dwFlags
0x180063077  xor     edx, edx; lpSubKey
0x180063079  mov     [rsp+40h+phkResult], 0; pdwType
0x180063082  mov     [rbp+arg_18], 20Ah
0x180063089  call    cs:__imp_RegGetValueW
0x18006308f  test    eax, eax
0x180063091  jz      short loc_1800630BF
0x180063093  mov     rcx, cs:WPP_GLOBAL_Control
0x18006309a  cmp     rcx, r12
0x18006309d  jz      short loc_1800630BF
0x18006309f  test    [rcx+1Ch], r15d
0x1800630a3  jz      short loc_1800630BF
0x1800630a5  cmp     byte ptr [rcx+19h], 2
0x1800630a9  jb      short loc_1800630BF
0x1800630ab  mov     rcx, [rcx+10h]
0x1800630af  mov     edx, 52h ; 'R'
0x1800630b4  mov     r9d, eax
0x1800630b7  mov     r8, r13
0x1800630ba  call    WPP_SF_d
0x1800630bf  mov     rcx, [rbp+hkey]; hkey
0x1800630c3  lea     rax, [rbp+arg_18]
0x1800630c7  mov     [rsp+40h+pcbData], rax; pcbData
0x1800630cc  lea     r8, aAutotriggerpro_6; "AutoTriggerProfileEntryName"
0x1800630d3  mov     [rsp+40h+pvData], rsi; pvData
0x1800630d8  mov     r9d, 2; dwFlags
0x1800630de  xor     edx, edx; lpSubKey
0x1800630e0  mov     [rsp+40h+phkResult], 0; pdwType
0x1800630e9  mov     [rbp+arg_18], 202h
0x1800630f0  call    cs:__imp_RegGetValueW
0x1800630f6  mov     ebx, eax
0x1800630f8  test    eax, eax
0x1800630fa  jz      short loc_180063128
0x1800630fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180063103  cmp     rcx, r12
0x180063106  jz      short loc_18006312F
0x180063108  test    [rcx+1Ch], r15d
0x18006310c  jz      short loc_18006312F
0x18006310e  cmp     byte ptr [rcx+19h], 2
0x180063112  jb      short loc_18006312F
0x180063114  mov     rcx, [rcx+10h]
0x180063118  mov     edx, 53h ; 'S'
0x18006311d  mov     r9d, eax
0x180063120  mov     r8, r13
0x180063123  call    WPP_SF_d
0x180063128  mov     rcx, cs:WPP_GLOBAL_Control
0x18006312f  mov     rax, [rbp+arg_20]
0x180063133  test    rax, rax
0x180063136  jz      loc_1800631D0
0x18006313c  lea     rcx, [rbp+arg_18]
0x180063140  mov     [rbp+arg_18], 10h
0x180063147  mov     [rsp+40h+pcbData], rcx; pcbData
0x18006314c  lea     r8, aAutotriggerpro_7; "AutoTriggerProfileGUID"
0x180063153  mov     rcx, [rbp+hkey]; hkey
0x180063157  xorps   xmm0, xmm0
0x18006315a  mov     [rsp+40h+pvData], rax; pvData
0x18006315f  mov     r9d, 8; dwFlags
0x180063165  xor     edx, edx; lpSubKey
0x180063167  mov     [rsp+40h+phkResult], 0; pdwType
0x180063170  movups  xmmword ptr [rax], xmm0
0x180063173  call    cs:__imp_RegGetValueW
0x180063179  mov     ebx, eax
0x18006317b  test    eax, eax
0x18006317d  jz      short loc_1800631C9
0x18006317f  mov     rcx, cs:WPP_GLOBAL_Control
0x180063186  cmp     rcx, r12
0x180063189  jz      short loc_1800631D0
0x18006318b  test    [rcx+1Ch], r15d
0x18006318f  jz      short loc_1800631D0
0x180063191  cmp     byte ptr [rcx+19h], 2
0x180063195  jb      short loc_1800631D0
0x180063197  mov     edx, 54h ; 'T'
0x18006319c  jmp     loc_180063050
0x1800631a1  mov     ebx, 57h ; 'W'
0x1800631a6  cmp     rcx, r12
0x1800631a9  jz      short loc_180063216
0x1800631ab  test    [rcx+1Ch], r15d
0x1800631af  jz      short loc_1800631F1
0x1800631b1  cmp     byte ptr [rcx+19h], 2
0x1800631b5  jb      short loc_1800631F1
0x1800631b7  lea     edx, [rbx-9]
0x1800631ba  mov     r9d, ebx
0x1800631bd  mov     rcx, [rcx+10h]
0x1800631c1  mov     r8, r13
0x1800631c4  call    WPP_SF_d
0x1800631c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800631d0  mov     rax, [rbp+hkey]
0x1800631d4  test    rax, rax
0x1800631d7  jz      short loc_1800631F1
0x1800631d9  mov     rcx, rax; hKey
0x1800631dc  call    cs:__imp_RegCloseKey
0x1800631e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800631e9  mov     [rbp+hkey], 0
0x1800631f1  cmp     rcx, r12
0x1800631f4  jz      short loc_180063216
0x1800631f6  test    [rcx+1Ch], r15d
0x1800631fa  jz      short loc_180063216
0x1800631fc  cmp     byte ptr [rcx+19h], 6
0x180063200  jb      short loc_180063216
0x180063202  mov     rcx, [rcx+10h]
0x180063206  mov     edx, 55h ; 'U'
0x18006320b  mov     r9d, ebx
0x18006320e  mov     r8, r13
0x180063211  call    WPP_SF_d
0x180063216  lea     r11, [rsp+40h+var_s0]
0x18006321b  mov     eax, ebx
0x18006321d  mov     rbx, [r11+38h]
0x180063221  mov     rsi, [r11+40h]
0x180063225  mov     rsp, r11
0x180063228  pop     r15
0x18006322a  pop     r13
0x18006322c  pop     r12
0x18006322e  pop     rdi
0x18006322f  pop     rbp
0x180063230  retn
```
