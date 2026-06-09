# SensorGroupId::LoadSensorGroupIdsFromRegistry(CTUnkArray<IMFSensorGroupId> &)

- ea: `0x180011d94`
- end: `0x18001206b`
- name: `?LoadSensorGroupIdsFromRegistry@SensorGroupId@@SAJAEAV?$CTUnkArray@UIMFSensorGroupId@@@@@Z`
- size: `727`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010adc`

## callees

- `0x180005fa0`
- `0x180008f9c`
- `0x1800099b4`
- `0x18000ec30`
- `0x18000fde4`
- `0x180011d94`
- `0x1800121f4`
- `0x180044f30`
- `0x180045900`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180011e35`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180011e35`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011f35`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011f35`

## pseudocode

```c
__int64 __fastcall SensorGroupId::LoadSensorGroupIdsFromRegistry(__int64 *a1)
{
  int v2; // eax
  unsigned int v3; // edi
  DWORD i; // esi
  LSTATUS v5; // eax
  int v6; // eax
  __int64 v8; // rdx
  struct IMFSensorGroupId *v9; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v10; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchName; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR Name[264]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  v2 = OpenSensorGroupRegistryKey(0, 131353, 0, &hKey);
  v3 = v2;
  if ( v2 < 0 )
  {
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, &WPP_c6ec3a891c39353f20252a4447583601_Traceguids, 0, v2);
  }
  else
  {
    for ( i = 0; ; ++i )
    {
      memset_0(Name, 0, 0x208u);
      cchName = 260;
      v5 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
      if ( v5 == 259 )
        goto LABEL_18;
      if ( v5 )
        break;
      v9 = 0;
      v10 = 0;
      v6 = SensorGroupId::CreateSensorGroupId(&v9);
      v3 = v6;
      if ( v6 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_14;
        v8 = 52;
        goto LABEL_32;
      }
      v6 = (**(__int64 (__fastcall ***)(struct IMFSensorGroupId *, GUID *, __int64 *))v9)(
             v9,
             &GUID_1725de0f_cf7a_4075_9365_d8c5d1eea8d7,
             &v10);
      v3 = v6;
      if ( v6 < 0 )
      {
        if ( !g_wppLevels )
        {
LABEL_14:
          if ( v10 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
          if ( v9 )
            (*(void (__fastcall **)(struct IMFSensorGroupId *))(*(_QWORD *)v9 + 16LL))(v9);
          goto LABEL_18;
        }
        v8 = 53;
LABEL_32:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v8, &WPP_c6ec3a891c39353f20252a4447583601_Traceguids, 0, v6);
        goto LABEL_14;
      }
      if ( (*(int (__fastcall **)(__int64, __int64, WCHAR *))(*(_QWORD *)v10 + 208LL))(v10, 1, Name) >= 0
        && !(unsigned __int8)IsInCollection(a1, v9)
        && !(unsigned int)CTUnkArray<IMFMediaType>::Add(a1, (__int64)v9) )
      {
        v3 = -2147024882;
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            54,
            &WPP_c6ec3a891c39353f20252a4447583601_Traceguids,
            0,
            -2147024882);
        wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v10);
        wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v9);
        goto LABEL_18;
      }
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      if ( v9 )
        (*(void (__fastcall **)(struct IMFSensorGroupId *))(*(_QWORD *)v9 + 16LL))(v9);
    }
    if ( v5 <= 0 )
      v3 = v5;
    else
      v3 = (unsigned __int16)v5 | 0x80070000;
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_c6ec3a891c39353f20252a4447583601_Traceguids, 0, v3);
  }
LABEL_18:
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x180011d94  push    rbp
0x180011d96  push    rsi
0x180011d97  push    rdi
0x180011d98  push    r14
0x180011d9a  lea     rbp, [rsp-188h]
0x180011da2  sub     rsp, 288h
0x180011da9  mov     rax, cs:__security_cookie
0x180011db0  xor     rax, rsp
0x180011db3  mov     [rbp+1A0h+var_30], rax
0x180011dba  mov     r14, rcx
0x180011dbd  mov     [rsp+2A0h+hKey], 0
0x180011dc6  xor     ecx, ecx; unsigned __int16 *
0x180011dc8  lea     r9, [rsp+2A0h+hKey]; HKEY *
0x180011dcd  xor     r8d, r8d; bool *
0x180011dd0  mov     edx, 20119h; unsigned int
0x180011dd5  call    ?OpenSensorGroupRegistryKey@@YAJPEBGKPEA_NPEAPEAUHKEY__@@@Z; OpenSensorGroupRegistryKey(ushort const *,ulong,bool *,HKEY__ * *)
0x180011dda  mov     edi, eax
0x180011ddc  test    eax, eax
0x180011dde  js      loc_18001204C
0x180011de4  xor     esi, esi
0x180011de6  xor     edx, edx; Val
0x180011de8  lea     rcx, [rsp+2A0h+Name]; void *
0x180011ded  mov     r8d, 208h; Size
0x180011df3  call    memset_0
0x180011df8  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180011dfd  lea     r9, [rsp+2A0h+cchName]; lpcchName
0x180011e02  mov     [rsp+2A0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180011e0b  lea     r8, [rsp+2A0h+Name]; lpName
0x180011e10  mov     [rsp+2A0h+lpcchClass], 0; lpcchClass
0x180011e19  mov     edx, esi; dwIndex
0x180011e1b  mov     [rsp+2A0h+lpClass], 0; lpClass
0x180011e24  mov     [rsp+2A0h+lpReserved], 0; lpReserved
0x180011e2d  mov     [rsp+2A0h+cchName], 104h
0x180011e35  call    cs:__imp_RegEnumKeyExW
0x180011e3b  cmp     eax, 103h
0x180011e40  jz      loc_180011F28
0x180011e46  test    eax, eax
0x180011e48  jnz     loc_180011FCB
0x180011e4e  lea     rcx, [rsp+2A0h+var_260]; struct IMFSensorGroupId **
0x180011e53  mov     [rsp+2A0h+var_260], 0
0x180011e5c  mov     [rsp+2A0h+var_258], 0
0x180011e65  call    ?CreateSensorGroupId@SensorGroupId@@SAJPEAPEAUIMFSensorGroupId@@@Z; SensorGroupId::CreateSensorGroupId(IMFSensorGroupId * *)
0x180011e6a  mov     edi, eax
0x180011e6c  test    eax, eax
0x180011e6e  js      loc_180012013
0x180011e74  mov     rcx, [rsp+2A0h+var_260]
0x180011e79  lea     r8, [rsp+2A0h+var_258]
0x180011e7e  lea     rdx, _GUID_1725de0f_cf7a_4075_9365_d8c5d1eea8d7
0x180011e85  mov     rax, [rcx]
0x180011e88  mov     rax, [rax]
0x180011e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e90  mov     edi, eax
0x180011e92  test    eax, eax
0x180011e94  js      short loc_180011EEF
0x180011e96  mov     rcx, [rsp+2A0h+var_258]
0x180011e9b  lea     r8, [rsp+2A0h+Name]
0x180011ea0  mov     edx, 1
0x180011ea5  mov     rax, [rcx]
0x180011ea8  mov     rax, [rax+0D0h]
0x180011eaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011eb4  test    eax, eax
0x180011eb6  jns     loc_180011F59
0x180011ebc  mov     rcx, [rsp+2A0h+var_258]
0x180011ec1  test    rcx, rcx
0x180011ec4  jz      short loc_180011ED2
0x180011ec6  mov     rax, [rcx]
0x180011ec9  mov     rax, [rax+10h]
0x180011ecd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ed2  mov     rcx, [rsp+2A0h+var_260]
0x180011ed7  test    rcx, rcx
0x180011eda  jz      short loc_180011EE8
0x180011edc  mov     rax, [rcx]
0x180011edf  mov     rax, [rax+10h]
0x180011ee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ee8  inc     esi
0x180011eea  jmp     loc_180011DE6
0x180011eef  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180011ef6  jnb     loc_180012064
0x180011efc  mov     rcx, [rsp+2A0h+var_258]
0x180011f01  test    rcx, rcx
0x180011f04  jz      short loc_180011F12
0x180011f06  mov     rax, [rcx]
0x180011f09  mov     rax, [rax+10h]
0x180011f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f12  mov     rcx, [rsp+2A0h+var_260]
0x180011f17  test    rcx, rcx
0x180011f1a  jz      short loc_180011F28
0x180011f1c  mov     rax, [rcx]
0x180011f1f  mov     rax, [rax+10h]
0x180011f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f28  cmp     [rsp+2A0h+hKey], 0
0x180011f2e  jz      short loc_180011F3B
0x180011f30  mov     rcx, [rsp+2A0h+hKey]; hKey
0x180011f35  call    cs:__imp_RegCloseKey
0x180011f3b  mov     eax, edi
0x180011f3d  mov     rcx, [rbp+1A0h+var_30]
0x180011f44  xor     rcx, rsp; StackCookie
0x180011f47  call    __security_check_cookie
0x180011f4c  add     rsp, 288h
0x180011f53  pop     r14
0x180011f55  pop     rdi
0x180011f56  pop     rsi
0x180011f57  pop     rbp
0x180011f58  retn
0x180011f59  mov     rdx, [rsp+2A0h+var_260]
0x180011f5e  mov     rcx, r14
0x180011f61  call    ?IsInCollection@@YA_NAEAV?$CTUnkArray@UIMFSensorGroupId@@@@PEAUIMFSensorGroupId@@@Z; IsInCollection(CTUnkArray<IMFSensorGroupId> &,IMFSensorGroupId *)
0x180011f66  test    al, al
0x180011f68  jnz     loc_180011EBC
0x180011f6e  mov     rdx, [rsp+2A0h+var_260]
0x180011f73  mov     rcx, r14
0x180011f76  call    ?Add@?$CTUnkArray@UIMFMediaType@@@@QEAAHPEAUIMFMediaType@@@Z; CTUnkArray<IMFMediaType>::Add(IMFMediaType *)
0x180011f7b  test    eax, eax
0x180011f7d  jnz     loc_180011EBC
0x180011f83  mov     edi, 8007000Eh
0x180011f88  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180011f8f  jb      short loc_180011FB2
0x180011f91  mov     rcx, cs:WPP_GLOBAL_Control
0x180011f98  lea     edx, [rax+36h]
0x180011f9b  xor     r9d, r9d
0x180011f9e  mov     dword ptr [rsp+2A0h+lpReserved], edi
0x180011fa2  lea     r8, WPP_c6ec3a891c39353f20252a4447583601_Traceguids
0x180011fa9  mov     rcx, [rcx+10h]
0x180011fad  call    WPP_SF_qD
0x180011fb2  lea     rcx, [rsp+2A0h+var_258]
0x180011fb7  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180011fbc  lea     rcx, [rsp+2A0h+var_260]
0x180011fc1  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x180011fc6  jmp     loc_180011F28
0x180011fcb  jle     short loc_180012048
0x180011fcd  movzx   edi, ax
0x180011fd0  or      edi, 80070000h
0x180011fd6  test    edi, edi
0x180011fd8  jns     loc_180011EE8
0x180011fde  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180011fe5  jb      loc_180011F28
0x180011feb  mov     edx, 33h ; '3'
0x180011ff0  mov     dword ptr [rsp+2A0h+lpReserved], edi
0x180011ff4  mov     rcx, cs:WPP_GLOBAL_Control
0x180011ffb  lea     r8, WPP_c6ec3a891c39353f20252a4447583601_Traceguids
0x180012002  xor     r9d, r9d
0x180012005  mov     rcx, [rcx+10h]
0x180012009  call    WPP_SF_qD
0x18001200e  jmp     loc_180011F28
0x180012013  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001201a  jb      loc_180011EFC
0x180012020  mov     edx, 34h ; '4'
0x180012025  mov     rcx, cs:WPP_GLOBAL_Control
0x18001202c  lea     r8, WPP_c6ec3a891c39353f20252a4447583601_Traceguids
0x180012033  xor     r9d, r9d
0x180012036  mov     dword ptr [rsp+2A0h+lpReserved], eax
0x18001203a  mov     rcx, [rcx+10h]
0x18001203e  call    WPP_SF_qD
0x180012043  jmp     loc_180011EFC
0x180012048  mov     edi, eax
0x18001204a  jmp     short loc_180011FD6
0x18001204c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180012053  jb      loc_180011F28
0x180012059  mov     edx, 32h ; '2'
0x18001205e  mov     dword ptr [rsp+2A0h+lpReserved], eax
0x180012062  jmp     short loc_180011FF4
0x180012064  mov     edx, 35h ; '5'
0x180012069  jmp     short loc_180012025
```
