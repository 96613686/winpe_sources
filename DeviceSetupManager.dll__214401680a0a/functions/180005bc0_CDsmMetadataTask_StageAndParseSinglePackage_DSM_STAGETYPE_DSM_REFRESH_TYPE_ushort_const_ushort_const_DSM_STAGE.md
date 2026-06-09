# CDsmMetadataTask::_StageAndParseSinglePackage(DSM_STAGETYPE,DSM_REFRESH_TYPE,ushort const *,ushort const *,DSM_STAGERESULT *)

- ea: `0x180005bc0`
- end: `0x180005de2`
- name: `?_StageAndParseSinglePackage@CDsmMetadataTask@@AEAAJW4DSM_STAGETYPE@@W4DSM_REFRESH_TYPE@@PEBG2PEAW4DSM_STAGERESULT@@@Z`
- size: `546`
- prototype: `__int64(__int64, __int64, __int64, ...)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800054b0`
- `0x1800057f4`

## callees

- `0x180005bc0`
- `0x18000e420`
- `0x180021790`
- `0x180022070`
- `0x180027a50`
- `0x18003ee30`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005c06`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180005c06`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005dc2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180005dc2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005d19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005d6c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005d19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180005d6c`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180005c1f`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180005c1f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 CDsmMetadataTask::_StageAndParseSinglePackage(__int64 a1, __int64 a2, __int64 a3, ...)
{
  _FILETIME v4; // rbx
  __int64 result; // rax
  int v6; // ebx
  char ElapsedMilliSeconds; // al
  int v8; // ecx
  _QWORD v9[3]; // [rsp+30h] [rbp-29h] BYREF
  PROPVARIANT pvar[2]; // [rsp+48h] [rbp-11h] BYREF
  __int64 v11; // [rsp+58h] [rbp-1h]
  _QWORD v12[2]; // [rsp+60h] [rbp+7h] BYREF
  unsigned __int64 UnbiasedTime[2]; // [rsp+70h] [rbp+17h] BYREF
  char v14; // [rsp+80h] [rbp+27h]
  LPVOID pv; // [rsp+C8h] [rbp+6Fh] BYREF
  va_list pva; // [rsp+C8h] [rbp+6Fh]
  LPVOID v17; // [rsp+D0h] [rbp+77h] BYREF
  va_list va1; // [rsp+D0h] [rbp+77h]
  _FILETIME SystemTimeAsFileTime; // [rsp+D8h] [rbp+7Fh] BYREF
  va_list SystemTimeAsFileTimea; // [rsp+D8h] [rbp+7Fh]
  va_list va3; // [rsp+E0h] [rbp+87h] BYREF

  va_start(va3, a3);
  va_start(SystemTimeAsFileTimea, a3);
  va_start(va1, a3);
  va_start(pva, a3);
  pv = va_arg(va1, LPVOID);
  va_copy(SystemTimeAsFileTimea, va1);
  v17 = va_arg(SystemTimeAsFileTimea, LPVOID);
  va_copy(va3, SystemTimeAsFileTimea);
  SystemTimeAsFileTime = va_arg(va3, _FILETIME);
  v4 = SystemTimeAsFileTime;
  *(_DWORD *)SystemTimeAsFileTime.dwLowDateTime = 4;
  v12[1] = 0;
  UnbiasedTime[1] = 0;
  v14 = 0;
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime((LPFILETIME)SystemTimeAsFileTimea);
  v12[0] = SystemTimeAsFileTime;
  QueryUnbiasedInterruptTime(UnbiasedTime);
  v14 = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_06df393cd1103d62962c75dbf951854a_Traceguids, 0);
  v17 = 0;
  pv = 0;
  result = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _FILETIME, LPVOID *, LPVOID *))(*(_QWORD *)CDsmMetadataTask::s_pPkgSrc
                                                                                    + 48LL))(
             CDsmMetadataTask::s_pPkgSrc,
             0,
             v4,
             (LPVOID *)pva,
             (LPVOID *)va1);
  v6 = result;
  if ( (int)result >= 0 )
  {
    if ( pv )
    {
      CDsmTimer::Stop((CDsmTimer *)v12);
      if ( (Microsoft_Windows_DeviceSetupManagerEnableBits & 1) != 0 )
      {
        ElapsedMilliSeconds = CDsmTimer::GetElapsedMilliSeconds((CDsmTimer *)v12, 0);
        McTemplateU0zji_EventWriteTransfer(
          v8,
          (unsigned int)MetadataStagingSucceeded,
          (_DWORD)pv,
          a1 + 28,
          ElapsedMilliSeconds);
      }
      v9[0] = 31;
      v9[2] = 0;
      v9[1] = pv;
      (*(void (__fastcall **)(_QWORD, __int128 *, _QWORD, _QWORD, _QWORD *))(**(_QWORD **)(a1 + 8) + 32LL))(
        *(_QWORD *)(a1 + 8),
        &DEVPKEY_DeviceSetup_MetadataPackageId,
        0,
        0,
        v9);
      CoTaskMemFree(pv);
    }
    if ( v17 )
    {
      v6 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)CDsmMetadataTask::s_pParser + 40LL))(CDsmMetadataTask::s_pParser);
      if ( v6 >= 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_06df393cd1103d62962c75dbf951854a_Traceguids);
      CoTaskMemFree(v17);
    }
    *(_OWORD *)pvar = 0;
    v11 = 0;
    if ( (*(int (__fastcall **)(_QWORD, __int128 *, _QWORD, _QWORD, PROPVARIANT *))(**(_QWORD **)(a1 + 8) + 24LL))(
           *(_QWORD *)(a1 + 8),
           &DEVPKEY_DeviceContainer_DCA_PackageFamilyName,
           0,
           0,
           pvar) >= 0
      && LOWORD(pvar[0]) == 4127 )
    {
      **(_DWORD **)(a1 + 16) |= 0x80u;
    }
    PropVariantClear(pvar);
    return (unsigned int)v6;
  }
  return result;
}

```

## disassembly

```asm
0x180005bc0  mov     [rsp-8+arg_0], rbx
0x180005bc5  mov     [rsp-8+arg_8], rsi
0x180005bca  mov     [rsp-8+pv], r9
0x180005bcf  push    rbp
0x180005bd0  push    rdi
0x180005bd1  push    r14
0x180005bd3  lea     rbp, [rsp-37h]
0x180005bd8  sub     rsp, 90h
0x180005bdf  mov     rdi, rcx
0x180005be2  mov     rbx, qword ptr [rbp+47h+SystemTimeAsFileTime.dwLowDateTime]
0x180005be6  mov     dword ptr [rbx], 4
0x180005bec  xor     esi, esi
0x180005bee  mov     [rbp+47h+var_38], rsi
0x180005bf2  mov     [rbp+47h+var_28], rsi
0x180005bf6  mov     [rbp+47h+var_20], sil
0x180005bfa  mov     [rbp+47h+var_40], rsi
0x180005bfe  mov     qword ptr [rbp+47h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x180005c02  lea     rcx, [rbp+47h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180005c06  call    cs:__imp_GetSystemTimeAsFileTime
0x180005c0c  mov     eax, [rbp+47h+SystemTimeAsFileTime.dwHighDateTime]
0x180005c12  mov     dword ptr [rbp+47h+var_40+4], eax
0x180005c15  mov     eax, [rbp+47h+SystemTimeAsFileTime.dwLowDateTime]
0x180005c18  mov     dword ptr [rbp+47h+var_40], eax
0x180005c1b  lea     rcx, [rbp+47h+UnbiasedTime]; UnbiasedTime
0x180005c1f  call    cs:__imp_QueryUnbiasedInterruptTime
0x180005c25  mov     [rbp+47h+var_20], 1
0x180005c29  lea     r14, WPP_GLOBAL_Control
0x180005c30  mov     rcx, cs:WPP_GLOBAL_Control
0x180005c37  cmp     rcx, r14
0x180005c3a  jz      short loc_180005C5A
0x180005c3c  test    byte ptr [rcx+1Ch], 1
0x180005c40  jz      short loc_180005C5A
0x180005c42  mov     edx, 20h ; ' '
0x180005c47  xor     r9d, r9d
0x180005c4a  lea     r8, WPP_06df393cd1103d62962c75dbf951854a_Traceguids
0x180005c51  mov     rcx, [rcx+10h]
0x180005c55  call    WPP_SF_d
0x180005c5a  mov     [rbp+47h+arg_20], rsi
0x180005c5e  mov     [rbp+47h+pv], rsi
0x180005c62  mov     rcx, cs:?s_pPkgSrc@CDsmMetadataTask@@0V?$CComPtr@UIDsmMetadataPackageSource@@@ATL@@A; ATL::CComPtr<IDsmMetadataPackageSource> CDsmMetadataTask::s_pPkgSrc
0x180005c69  mov     rax, [rcx]
0x180005c6c  lea     rdx, [rbp+47h+arg_20]
0x180005c70  mov     [rsp+0A0h+var_80], rdx
0x180005c75  lea     r9, [rbp+47h+pv]
0x180005c79  mov     r8, rbx
0x180005c7c  xor     edx, edx
0x180005c7e  mov     rax, [rax+30h]
0x180005c82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c87  mov     ebx, eax
0x180005c89  test    eax, eax
0x180005c8b  js      loc_180005DCA
0x180005c91  cmp     [rbp+47h+pv], rsi
0x180005c95  jz      loc_180005D1F
0x180005c9b  lea     rcx, [rbp+47h+var_40]; this
0x180005c9f  call    ?Stop@CDsmTimer@@QEAAXXZ; CDsmTimer::Stop(void)
0x180005ca4  test    cs:Microsoft_Windows_DeviceSetupManagerEnableBits, 1
0x180005cab  jz      short loc_180005CD1
0x180005cad  xor     edx, edx; bool
0x180005caf  lea     rcx, [rbp+47h+var_40]; this
0x180005cb3  call    ?GetElapsedMilliSeconds@CDsmTimer@@QEAA_K_N@Z; CDsmTimer::GetElapsedMilliSeconds(bool)
0x180005cb8  lea     r9, [rdi+1Ch]
0x180005cbc  mov     [rsp+0A0h+var_80], rax
0x180005cc1  mov     r8, [rbp+47h+pv]
0x180005cc5  lea     rdx, MetadataStagingSucceeded
0x180005ccc  call    McTemplateU0zji_EventWriteTransfer
0x180005cd1  xorps   xmm0, xmm0
0x180005cd4  xor     eax, eax
0x180005cd6  movups  [rbp+47h+var_70], xmm0
0x180005cda  mov     [rbp+47h+var_60], rax
0x180005cde  mov     rax, [rbp+47h+pv]
0x180005ce2  mov     qword ptr [rbp+47h+var_70+8], rax
0x180005ce6  mov     eax, 1Fh
0x180005ceb  mov     word ptr [rbp+47h+var_70], ax
0x180005cef  mov     rcx, [rdi+8]
0x180005cf3  mov     rax, [rcx]
0x180005cf6  lea     rdx, [rbp+47h+var_70]
0x180005cfa  mov     [rsp+0A0h+var_80], rdx
0x180005cff  xor     r9d, r9d
0x180005d02  xor     r8d, r8d
0x180005d05  lea     rdx, DEVPKEY_DeviceSetup_MetadataPackageId
0x180005d0c  mov     rax, [rax+20h]
0x180005d10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d15  mov     rcx, [rbp+47h+pv]; pv
0x180005d19  call    cs:__imp_CoTaskMemFree
0x180005d1f  mov     rdx, [rbp+47h+arg_20]
0x180005d23  test    rdx, rdx
0x180005d26  jz      short loc_180005D72
0x180005d28  mov     rcx, cs:?s_pParser@CDsmMetadataTask@@0V?$CComPtr@UIDsmPropertySource@@@ATL@@A; ATL::CComPtr<IDsmPropertySource> CDsmMetadataTask::s_pParser
0x180005d2f  mov     rax, [rcx]
0x180005d32  mov     rax, [rax+28h]
0x180005d36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d3b  mov     ebx, eax
0x180005d3d  test    eax, eax
0x180005d3f  js      short loc_180005D68
0x180005d41  mov     rcx, cs:WPP_GLOBAL_Control
0x180005d48  cmp     rcx, r14
0x180005d4b  jz      short loc_180005D68
0x180005d4d  test    byte ptr [rcx+1Ch], 1
0x180005d51  jz      short loc_180005D68
0x180005d53  mov     edx, 25h ; '%'
0x180005d58  lea     r8, WPP_06df393cd1103d62962c75dbf951854a_Traceguids
0x180005d5f  mov     rcx, [rcx+10h]
0x180005d63  call    WPP_SF_
0x180005d68  mov     rcx, [rbp+47h+arg_20]; pv
0x180005d6c  call    cs:__imp_CoTaskMemFree
0x180005d72  xorps   xmm0, xmm0
0x180005d75  xor     eax, eax
0x180005d77  movups  xmmword ptr [rbp+47h+pvar], xmm0
0x180005d7b  mov     [rbp+47h+var_48], rax
0x180005d7f  mov     rcx, [rdi+8]
0x180005d83  mov     rax, [rcx]
0x180005d86  lea     rdx, [rbp+47h+pvar]
0x180005d8a  mov     [rsp+0A0h+var_80], rdx
0x180005d8f  xor     r9d, r9d
0x180005d92  xor     r8d, r8d
0x180005d95  lea     rdx, DEVPKEY_DeviceContainer_DCA_PackageFamilyName
0x180005d9c  mov     rax, [rax+18h]
0x180005da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005da5  test    eax, eax
0x180005da7  js      short loc_180005DBE
0x180005da9  mov     eax, 101Fh
0x180005dae  cmp     word ptr [rbp+47h+pvar], ax
0x180005db2  jnz     short loc_180005DBE
0x180005db4  mov     rax, [rdi+10h]
0x180005db8  or      dword ptr [rax], 80h
0x180005dbe  lea     rcx, [rbp+47h+pvar]; pvar
0x180005dc2  call    cs:__imp_PropVariantClear
0x180005dc8  mov     eax, ebx
0x180005dca  lea     r11, [rsp+0A0h+var_10]
0x180005dd2  mov     rbx, [r11+20h]
0x180005dd6  mov     rsi, [r11+28h]
0x180005dda  mov     rsp, r11
0x180005ddd  pop     r14
0x180005ddf  pop     rdi
0x180005de0  pop     rbp
0x180005de1  retn
```
