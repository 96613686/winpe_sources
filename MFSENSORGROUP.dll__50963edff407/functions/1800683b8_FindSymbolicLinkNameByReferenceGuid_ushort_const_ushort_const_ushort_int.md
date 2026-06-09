# FindSymbolicLinkNameByReferenceGuid(ushort const *,ushort const *,ushort *,int)

- ea: `0x1800683b8`
- end: `0x18006857f`
- name: `?FindSymbolicLinkNameByReferenceGuid@@YAJPEBG0PEAGH@Z`
- size: `455`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, LPBYTE lpData)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, registry_config`

## callers

- `0x180068318`

## callees

- `0x180005fa0`
- `0x180051a1c`
- `0x180067d90`
- `0x1800683b8`
- `0x18006b55c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800684d6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800684d6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180068433`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180068433`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180068564`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180068564`

## pseudocode

```c
__int64 __fastcall FindSymbolicLinkNameByReferenceGuid(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        LPBYTE lpData)
{
  signed int v6; // ebx
  LSTATUS v7; // eax
  signed int v8; // esi
  __int64 v9; // rdx
  LSTATUS v10; // esi
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  DWORD cbData; // [rsp+78h] [rbp+20h] BYREF

  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  cbData = 520;
  v6 = 0;
  if ( (unsigned __int8)byte_18008D62F >= 8u )
    WPP_SF_SS(
      *((_QWORD *)WPP_GLOBAL_Control + 37),
      16,
      (unsigned int)&WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids,
      (_DWORD)a1,
      (__int64)a2);
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a1, 0, 0x20019u, &hKey);
  v8 = v7;
  if ( v7 )
  {
    if ( (unsigned __int8)byte_18008D62F >= 8u )
      WPP_SF_dS(
        *((_QWORD *)WPP_GLOBAL_Control + 37),
        17,
        (unsigned int)&WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids,
        v7,
        (__int64)a1);
    v6 = v8 > 0 ? (unsigned __int16)v8 | 0x80070000 : v8;
    if ( v6 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_26;
      v9 = 18;
      goto LABEL_12;
    }
  }
  v10 = RegQueryValueExW(hKey, a2, 0, 0, lpData, &cbData);
  if ( v10 )
  {
    if ( (unsigned __int8)byte_18008D62F >= 8u )
      WPP_SF_dSS(*((_QWORD *)WPP_GLOBAL_Control + 37), (__int64)a1, (__int64)a2);
    if ( v10 > 0 )
      v6 = (unsigned __int16)v10 | 0x80070000;
    else
      v6 = v10;
    if ( g_wppLevels )
    {
      v9 = 20;
LABEL_12:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, &WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids, 0, v6);
    }
  }
  else if ( *(_WORD *)lpData == 92
         && *((_WORD *)lpData + 1) == 63
         && *((_WORD *)lpData + 2) == 63
         && *((_WORD *)lpData + 3) == 92 )
  {
    *((_WORD *)lpData + 1) = 92;
  }
LABEL_26:
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(hKey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800683b8  mov     rax, rsp
0x1800683bb  mov     [rax+8], rbx
0x1800683bf  mov     [rax+10h], rbp
0x1800683c3  mov     [rax+20h], r9d
0x1800683c7  push    rsi
0x1800683c8  push    rdi
0x1800683c9  push    r14
0x1800683cb  sub     rsp, 40h
0x1800683cf  mov     rdi, r8
0x1800683d2  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFFh
0x1800683da  mov     r14, rdx
0x1800683dd  mov     dword ptr [rax+20h], 208h
0x1800683e4  mov     rbp, rcx
0x1800683e7  xor     ebx, ebx
0x1800683e9  cmp     cs:byte_18008D62F, 8
0x1800683f0  jb      short loc_180068416
0x1800683f2  mov     r9, rcx
0x1800683f5  mov     [rax-38h], r14
0x1800683f9  mov     rcx, cs:WPP_GLOBAL_Control
0x180068400  lea     edx, [rbx+10h]
0x180068403  lea     r8, WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids
0x18006840a  mov     rcx, [rcx+128h]
0x180068411  call    WPP_SF_SS
0x180068416  lea     rax, [rsp+58h+hKey]
0x18006841b  mov     r9d, 20019h; samDesired
0x180068421  xor     r8d, r8d; ulOptions
0x180068424  mov     [rsp+58h+phkResult], rax; phkResult
0x180068429  mov     rdx, rbp; lpSubKey
0x18006842c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180068433  call    cs:__imp_RegOpenKeyExW
0x180068439  mov     esi, eax
0x18006843b  test    eax, eax
0x18006843d  jz      short loc_1800684B9
0x18006843f  cmp     cs:byte_18008D62F, 8
0x180068446  jb      short loc_18006846F
0x180068448  mov     rcx, cs:WPP_GLOBAL_Control
0x18006844f  lea     r8, WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids
0x180068456  mov     edx, 11h
0x18006845b  mov     [rsp+58h+phkResult], rbp
0x180068460  mov     r9d, eax
0x180068463  mov     rcx, [rcx+128h]
0x18006846a  call    WPP_SF_dS
0x18006846f  test    esi, esi
0x180068471  jg      short loc_180068477
0x180068473  mov     ebx, esi
0x180068475  jmp     short loc_180068480
0x180068477  movzx   ebx, si
0x18006847a  or      ebx, 80070000h
0x180068480  test    ebx, ebx
0x180068482  jns     short loc_1800684B9
0x180068484  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006848b  jb      loc_180068555
0x180068491  mov     edx, 12h
0x180068496  mov     rcx, cs:WPP_GLOBAL_Control
0x18006849d  lea     r8, WPP_062b0285d2ed37de30ae44f3d8d240c9_Traceguids
0x1800684a4  xor     r9d, r9d
0x1800684a7  mov     dword ptr [rsp+58h+phkResult], ebx
0x1800684ab  mov     rcx, [rcx+10h]
0x1800684af  call    WPP_SF_qD
0x1800684b4  jmp     loc_180068555
0x1800684b9  mov     rcx, [rsp+58h+hKey]; hKey
0x1800684be  lea     rax, [rsp+58h+cbData]
0x1800684c3  mov     [rsp+58h+lpcbData], rax; lpcbData
0x1800684c8  xor     r9d, r9d; lpType
0x1800684cb  xor     r8d, r8d; lpReserved
0x1800684ce  mov     [rsp+58h+phkResult], rdi; lpData
0x1800684d3  mov     rdx, r14; lpValueName
0x1800684d6  call    cs:__imp_RegQueryValueExW
0x1800684dc  mov     esi, eax
0x1800684de  test    eax, eax
0x1800684e0  jz      short loc_180068533
0x1800684e2  cmp     cs:byte_18008D62F, 8
0x1800684e9  jb      short loc_18006850B
0x1800684eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800684f2  mov     r9d, eax
0x1800684f5  mov     [rsp+58h+lpcbData], r14; __int64
0x1800684fa  mov     [rsp+58h+phkResult], rbp; __int64
0x1800684ff  mov     rcx, [rcx+128h]; LoggerHandle
0x180068506  call    WPP_SF_dSS
0x18006850b  test    esi, esi
0x18006850d  jg      short loc_180068513
0x18006850f  mov     ebx, esi
0x180068511  jmp     short loc_18006851C
0x180068513  movzx   ebx, si
0x180068516  or      ebx, 80070000h
0x18006851c  test    ebx, ebx
0x18006851e  jns     short loc_180068533
0x180068520  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180068527  jb      short loc_180068555
0x180068529  mov     edx, 14h
0x18006852e  jmp     loc_180068496
0x180068533  mov     eax, 5Ch ; '\'
0x180068538  cmp     [rdi], ax
0x18006853b  jnz     short loc_180068555
0x18006853d  cmp     word ptr [rdi+2], 3Fh ; '?'
0x180068542  jnz     short loc_180068555
0x180068544  cmp     word ptr [rdi+4], 3Fh ; '?'
0x180068549  jnz     short loc_180068555
0x18006854b  cmp     [rdi+6], ax
0x18006854f  jnz     short loc_180068555
0x180068551  mov     [rdi+2], ax
0x180068555  mov     rcx, [rsp+58h+hKey]; hKey
0x18006855a  lea     rdx, [rcx-1]
0x18006855e  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180068562  ja      short loc_18006856A
0x180068564  call    cs:__imp_RegCloseKey
0x18006856a  mov     rbp, [rsp+58h+arg_8]
0x18006856f  mov     eax, ebx
0x180068571  mov     rbx, [rsp+58h+arg_0]
0x180068576  add     rsp, 40h
0x18006857a  pop     r14
0x18006857c  pop     rdi
0x18006857d  pop     rsi
0x18006857e  retn
```
