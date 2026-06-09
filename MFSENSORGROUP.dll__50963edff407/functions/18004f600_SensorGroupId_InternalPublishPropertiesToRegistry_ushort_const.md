# SensorGroupId::InternalPublishPropertiesToRegistry(ushort const *)

- ea: `0x18004f600`
- end: `0x18004fa38`
- name: `?InternalPublishPropertiesToRegistry@SensorGroupId@@IEAAJPEBG@Z`
- size: `1080`
- prototype: `int(SensorGroupId *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180050170`

## callees

- `0x180005fa0`
- `0x180009dbc`
- `0x18000c8b0`
- `0x18000c94c`
- `0x18000d1f0`
- `0x18000ec30`
- `0x18000f518`
- `0x18000fb44`
- `0x180015efc`
- `0x180028d5c`
- `0x180028e5c`
- `0x180044f30`
- `0x180045900`
- `0x18004f600`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004f75b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004f75b`

## pseudocode

```c
__int64 __fastcall SensorGroupId::InternalPublishPropertiesToRegistry(SensorGroupId *this, const unsigned __int16 *a2)
{
  signed int v4; // ebx
  __int64 v5; // rdx
  int v6; // eax
  __int64 v7; // rdx
  LSTATUS v8; // eax
  __int64 v9; // r14
  __int64 v10; // rsi
  DWORD v11; // r9d
  const unsigned __int16 *v12; // rdx
  char v13; // bl
  const unsigned __int16 *v14; // rax
  int v15; // edx
  int v16; // eax
  const unsigned __int16 *v17; // rax
  DWORD v18; // r12d
  DWORD i; // esi
  __int64 v20; // rcx
  const unsigned __int16 *v21; // rax
  int v22; // r14d
  __int64 v23; // rcx
  const unsigned __int8 *v24; // rax
  __int64 v25; // rdx
  DWORD dwOptions[2]; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v30; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v31[264]; // [rsp+70h] [rbp-90h] BYREF

  phkResult = 0;
  hKey = 0;
  if ( !a2 )
  {
    v4 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_48;
    v5 = 296;
    goto LABEL_4;
  }
  if ( (unsigned __int8)byte_18008D62D >= 8u )
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      297,
      (unsigned int)&WPP_c6ec3a891c39353f20252a4447583601_Traceguids,
      (_DWORD)this,
      (__int64)a2);
  if ( *((_DWORD *)this + 32) > 1u )
  {
    SensorGroupProperty::Allocate((SensorGroupId *)((char *)this + 1792), 0);
    SensorGroupProperty::Allocate((SensorGroupId *)((char *)this + 1856), 0);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v6 = OpenSensorGroupRegistryKey(0, 131334, 0, &hKey);
  v4 = v6;
  if ( v6 < 0 )
  {
    if ( g_wppLevels )
    {
      v7 = 298;
LABEL_13:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_c6ec3a891c39353f20252a4447583601_Traceguids, this, v6);
    }
    goto LABEL_48;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  v8 = RegCreateKeyExW(hKey, a2, 0, 0, 0, 0x20106u, (const LPSECURITY_ATTRIBUTES)((char *)this + 152), &phkResult, 0);
  v4 = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      v4 = (unsigned __int16)v8 | 0x80070000;
    if ( v4 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_48;
      v5 = 299;
LABEL_4:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, &WPP_c6ec3a891c39353f20252a4447583601_Traceguids, this, v4);
LABEL_48:
      if ( byte_18008D62D )
      {
        v25 = 306;
LABEL_52:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v25, &WPP_c6ec3a891c39353f20252a4447583601_Traceguids, this, v4);
      }
      goto LABEL_53;
    }
  }
  else
  {
    v4 = 0;
  }
  v9 = 0;
  v10 = 0;
  do
  {
    if ( *((_BYTE *)this + v10 + 284) && *(_DWORD *)((char *)this + v10 + 280) )
    {
      v11 = *(_DWORD *)((char *)this + v10 + 292);
      v12 = *(const unsigned __int16 **)((char *)this + v10 + 272);
      if ( v11 )
      {
        v16 = SensorGroupId::WriteToReg(
                a2,
                v12,
                *(const unsigned __int8 **)((char *)this + v10 + 296),
                v11,
                *(_DWORD *)((char *)this + v10 + 280));
        v13 = v16;
        if ( v16 >= 0 )
        {
          if ( (unsigned __int8)byte_18008D62D >= 8u )
          {
            v17 = SensorGroupProperty::TraceSz((SensorGroupId *)((char *)this + v10 + 256));
            WPP_SF_qS(
              *((_QWORD *)WPP_GLOBAL_Control + 27),
              302,
              (unsigned int)&WPP_c6ec3a891c39353f20252a4447583601_Traceguids,
              (_DWORD)this,
              (__int64)v17);
          }
          goto LABEL_33;
        }
        if ( byte_18008D62D )
        {
          v14 = SensorGroupProperty::TraceSz((SensorGroupId *)((char *)this + v10 + 256));
          v15 = 301;
          goto LABEL_30;
        }
      }
      else
      {
        v13 = (*(__int64 (__fastcall **)(char *, const unsigned __int16 *))(*((_QWORD *)this + 1) + 120LL))(
                (char *)this + 8,
                v12);
        if ( (unsigned __int8)byte_18008D62D >= 8u )
        {
          v14 = SensorGroupProperty::TraceSz((SensorGroupId *)((char *)this + v10 + 256));
          v15 = 300;
LABEL_30:
          WPP_SF_qDS(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            v15,
            (unsigned int)&WPP_c6ec3a891c39353f20252a4447583601_Traceguids,
            (_DWORD)this,
            v13,
            (__int64)v14);
        }
      }
LABEL_33:
      v4 = 0;
    }
    ++v9;
    v10 += 64;
  }
  while ( v9 != 26 );
  v18 = *((_DWORD *)this + 32);
  for ( i = 0; i < v18; ++i )
  {
    memset_0(v31, 0, 0x208u);
    v20 = *(_QWORD *)(*((_QWORD *)this + 15) + 8LL * i);
    v21 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 24LL))(v20);
    v30 = 0;
    v6 = StringCchLengthW(v21, 0x7FFFFFFFu, &v30);
    v4 = v6;
    if ( v6 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_48;
      v7 = 303;
      goto LABEL_13;
    }
    dwOptions[0] = i;
    v22 = v30 + 1;
    v6 = StringCchPrintfW(v31, 0x104u, L"%s%d", L"Device", *(_QWORD *)dwOptions);
    v4 = v6;
    if ( v6 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_48;
      v7 = 304;
      goto LABEL_13;
    }
    v23 = *(_QWORD *)(*((_QWORD *)this + 15) + 8LL * i);
    v24 = (const unsigned __int8 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 24LL))(v23);
    v6 = SensorGroupId::WriteToReg(a2, v31, v24, 2 * v22, 1u);
    v4 = v6;
    if ( v6 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_48;
      v7 = 305;
      goto LABEL_13;
    }
  }
  if ( v4 < 0 )
    goto LABEL_48;
  if ( (unsigned __int8)byte_18008D62D >= 8u )
  {
    v25 = 307;
    goto LABEL_52;
  }
LABEL_53:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18004f600  mov     [rsp-8+arg_10], rbx
0x18004f605  push    rbp
0x18004f606  push    rsi
0x18004f607  push    rdi
0x18004f608  push    r12
0x18004f60a  push    r13
0x18004f60c  push    r14
0x18004f60e  push    r15
0x18004f610  lea     rbp, [rsp-190h]
0x18004f618  sub     rsp, 290h
0x18004f61f  mov     rax, cs:__security_cookie
0x18004f626  xor     rax, rsp
0x18004f629  mov     [rbp+1C0h+var_40], rax
0x18004f630  xor     r13d, r13d
0x18004f633  mov     r15, rdx
0x18004f636  mov     [rsp+2C0h+var_268], r13
0x18004f63b  mov     rdi, rcx
0x18004f63e  mov     [rsp+2C0h+hKey], r13
0x18004f643  test    rdx, rdx
0x18004f646  jnz     short loc_18004F682
0x18004f648  mov     ebx, 80070057h
0x18004f64d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004f654  jb      loc_18004F9B9
0x18004f65a  mov     edx, 128h
0x18004f65f  mov     [rsp+2C0h+dwOptions], ebx
0x18004f663  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f66a  lea     r8, WPP_c6ec3a891c39353f20252a4447583601_Traceguids
0x18004f671  mov     r9, rdi
0x18004f674  mov     rcx, [rcx+10h]
0x18004f678  call    WPP_SF_qD
0x18004f67d  jmp     loc_18004F9B9
0x18004f682  mov     r12b, 8
0x18004f685  cmp     cs:byte_18008D62D, r12b
0x18004f68c  jb      short loc_18004F6B5
0x18004f68e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f695  lea     r8, WPP_c6ec3a891c39353f20252a4447583601_Traceguids
0x18004f69c  mov     edx, 129h
0x18004f6a1  mov     qword ptr [rsp+2C0h+dwOptions], r15
0x18004f6a6  mov     r9, rdi
0x18004f6a9  mov     rcx, [rcx+0D8h]
0x18004f6b0  call    WPP_SF_qS
0x18004f6b5  cmp     dword ptr [rdi+80h], 1
0x18004f6bc  jbe     short loc_18004F6DA
0x18004f6be  lea     rcx, [rdi+700h]; this
0x18004f6c5  xor     edx, edx; unsigned int
0x18004f6c7  call    ?Allocate@SensorGroupProperty@@QEAAJK@Z; SensorGroupProperty::Allocate(ulong)
0x18004f6cc  lea     rcx, [rdi+740h]; this
0x18004f6d3  xor     edx, edx; unsigned int
0x18004f6d5  call    ?Allocate@SensorGroupProperty@@QEAAJK@Z; SensorGroupProperty::Allocate(ulong)
0x18004f6da  xor     edx, edx
0x18004f6dc  lea     rcx, [rsp+2C0h+hKey]
0x18004f6e1  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18004f6e6  mov     esi, 20106h
0x18004f6eb  lea     r9, [rsp+2C0h+hKey]; HKEY *
0x18004f6f0  mov     edx, esi; unsigned int
0x18004f6f2  xor     r8d, r8d; bool *
0x18004f6f5  xor     ecx, ecx; unsigned __int16 *
0x18004f6f7  call    ?OpenSensorGroupRegistryKey@@YAJPEBGKPEA_NPEAPEAUHKEY__@@@Z; OpenSensorGroupRegistryKey(ushort const *,ulong,bool *,HKEY__ * *)
0x18004f6fc  mov     ebx, eax
0x18004f6fe  test    eax, eax
0x18004f700  jns     short loc_18004F71D
0x18004f702  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004f709  jb      loc_18004F9B9
0x18004f70f  mov     edx, 12Ah
0x18004f714  mov     [rsp+2C0h+dwOptions], eax
0x18004f718  jmp     loc_18004F663
0x18004f71d  xor     edx, edx
0x18004f71f  lea     rcx, [rsp+2C0h+var_268]
0x18004f724  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18004f729  mov     [rsp+2C0h+lpdwDisposition], r13; lpdwDisposition
0x18004f72e  lea     rcx, [rsp+2C0h+var_268]
0x18004f733  mov     [rsp+2C0h+phkResult], rcx; phkResult
0x18004f738  lea     rax, [rdi+98h]
0x18004f73f  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18004f744  xor     r9d, r9d; lpClass
0x18004f747  mov     [rsp+2C0h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18004f74c  xor     r8d, r8d; Reserved
0x18004f74f  mov     [rsp+2C0h+samDesired], esi; samDesired
0x18004f753  mov     rdx, r15; lpSubKey
0x18004f756  mov     [rsp+2C0h+dwOptions], r13d; dwOptions
0x18004f75b  call    cs:__imp_RegCreateKeyExW
0x18004f761  mov     ebx, eax
0x18004f763  test    eax, eax
0x18004f765  jz      short loc_18004F78D
0x18004f767  jle     short loc_18004F772
0x18004f769  movzx   ebx, ax
0x18004f76c  or      ebx, 80070000h
0x18004f772  test    ebx, ebx
0x18004f774  jns     short loc_18004F790
0x18004f776  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004f77d  jb      loc_18004F9B9
0x18004f783  mov     edx, 12Bh
0x18004f788  jmp     loc_18004F65F
0x18004f78d  mov     ebx, r13d
0x18004f790  mov     r14, r13
0x18004f793  mov     rsi, r13
0x18004f796  cmp     [rdi+rsi+11Ch], r13b
0x18004f79e  jz      loc_18004F89E
0x18004f7a4  mov     eax, [rdi+rsi+118h]
0x18004f7ab  test    eax, eax
0x18004f7ad  jz      loc_18004F89E
0x18004f7b3  mov     r9d, [rdi+rsi+124h]; unsigned int
0x18004f7bb  mov     rdx, [rdi+rsi+110h]; unsigned __int16 *
0x18004f7c3  test    r9d, r9d
0x18004f7c6  jnz     short loc_18004F7FD
0x18004f7c8  lea     rcx, [rdi+8]
0x18004f7cc  mov     rax, [rcx]
0x18004f7cf  mov     rax, [rax+78h]
0x18004f7d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f7d8  mov     ebx, eax
0x18004f7da  cmp     cs:byte_18008D62D, r12b
0x18004f7e1  jb      loc_18004F89B
0x18004f7e7  lea     rcx, [rdi+100h]
0x18004f7ee  add     rcx, rsi; this
0x18004f7f1  call    ?TraceSz@SensorGroupProperty@@QEAAPEBGXZ; SensorGroupProperty::TraceSz(void)
0x18004f7f6  mov     edx, 12Ch
0x18004f7fb  jmp     short loc_18004F834
0x18004f7fd  mov     r8, [rdi+rsi+128h]; unsigned __int8 *
0x18004f805  mov     rcx, r15; unsigned __int16 *
0x18004f808  mov     [rsp+2C0h+dwOptions], eax; unsigned int
0x18004f80c  call    ?WriteToReg@SensorGroupId@@SAJPEBG0PEBEKK@Z; SensorGroupId::WriteToReg(ushort const *,ushort const *,uchar const *,ulong,ulong)
0x18004f811  mov     ebx, eax
0x18004f813  test    eax, eax
0x18004f815  jns     short loc_18004F85C
0x18004f817  cmp     cs:byte_18008D62D, 1
0x18004f81e  jb      short loc_18004F89B
0x18004f820  lea     rcx, [rdi+100h]
0x18004f827  add     rcx, rsi; this
0x18004f82a  call    ?TraceSz@SensorGroupProperty@@QEAAPEBGXZ; SensorGroupProperty::TraceSz(void)
0x18004f82f  mov     edx, 12Dh
0x18004f834  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f83b  lea     r8, WPP_c6ec3a891c39353f20252a4447583601_Traceguids
0x18004f842  mov     qword ptr [rsp+2C0h+samDesired], rax
0x18004f847  mov     r9, rdi
0x18004f84a  mov     [rsp+2C0h+dwOptions], ebx
0x18004f84e  mov     rcx, [rcx+0D8h]
0x18004f855  call    WPP_SF_qDS
0x18004f85a  jmp     short loc_18004F89B
0x18004f85c  cmp     cs:byte_18008D62D, r12b
0x18004f863  jb      short loc_18004F89B
0x18004f865  lea     rcx, [rdi+100h]
0x18004f86c  add     rcx, rsi; this
0x18004f86f  call    ?TraceSz@SensorGroupProperty@@QEAAPEBGXZ; SensorGroupProperty::TraceSz(void)
0x18004f874  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f87b  lea     r8, WPP_c6ec3a891c39353f20252a4447583601_Traceguids
0x18004f882  mov     edx, 12Eh
0x18004f887  mov     qword ptr [rsp+2C0h+dwOptions], rax
0x18004f88c  mov     r9, rdi
0x18004f88f  mov     rcx, [rcx+0D8h]
0x18004f896  call    WPP_SF_qS
0x18004f89b  mov     ebx, r13d
0x18004f89e  inc     r14
0x18004f8a1  add     rsi, 40h ; '@'
0x18004f8a5  cmp     r14, 1Ah
0x18004f8a9  jnz     loc_18004F796
0x18004f8af  mov     r12d, [rdi+80h]
0x18004f8b6  mov     esi, r13d
0x18004f8b9  cmp     esi, r12d
0x18004f8bc  jnb     loc_18004F9B5
0x18004f8c2  xor     edx, edx; Val
0x18004f8c4  lea     rcx, [rsp+2C0h+var_250]; void *
0x18004f8c9  mov     r8d, 208h; Size
0x18004f8cf  call    memset_0
0x18004f8d4  mov     rax, [rdi+78h]
0x18004f8d8  mov     r13d, esi
0x18004f8db  mov     rcx, [rax+r13*8]
0x18004f8df  mov     rax, [rcx]
0x18004f8e2  mov     rax, [rax+18h]
0x18004f8e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f8eb  lea     r8, [rsp+2C0h+var_260]; unsigned __int64 *
0x18004f8f0  mov     [rsp+2C0h+var_260], 0
0x18004f8f9  mov     edx, 7FFFFFFFh; unsigned __int64
0x18004f8fe  mov     rcx, rax; unsigned __int16 *
0x18004f901  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18004f906  mov     ebx, eax
0x18004f908  test    eax, eax
0x18004f90a  js      loc_18004F9A2
0x18004f910  mov     r14, [rsp+2C0h+var_260]
0x18004f915  lea     r9, aDevice; "Device"
0x18004f91c  lea     r8, aSD; "%s%d"
0x18004f923  mov     [rsp+2C0h+dwOptions], esi
0x18004f927  mov     edx, 104h; unsigned __int64
0x18004f92c  lea     rcx, [rsp+2C0h+var_250]; unsigned __int16 *
0x18004f931  inc     r14
0x18004f934  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004f939  mov     ebx, eax
0x18004f93b  test    eax, eax
0x18004f93d  js      short loc_18004F98F
0x18004f93f  mov     rax, [rdi+78h]
0x18004f943  mov     rcx, [rax+r13*8]
0x18004f947  mov     rax, [rcx]
0x18004f94a  mov     rax, [rax+18h]
0x18004f94e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f953  lea     r9d, [r14+r14]; unsigned int
0x18004f957  mov     [rsp+2C0h+dwOptions], 1; unsigned int
0x18004f95f  mov     r8, rax; unsigned __int8 *
0x18004f962  lea     rdx, [rsp+2C0h+var_250]; unsigned __int16 *
0x18004f967  mov     rcx, r15; unsigned __int16 *
0x18004f96a  call    ?WriteToReg@SensorGroupId@@SAJPEBG0PEBEKK@Z; SensorGroupId::WriteToReg(ushort const *,ushort const *,uchar const *,ulong,ulong)
0x18004f96f  mov     ebx, eax
0x18004f971  test    eax, eax
0x18004f973  js      short loc_18004F97C
0x18004f975  inc     esi
0x18004f977  jmp     loc_18004F8B9
0x18004f97c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004f983  jb      short loc_18004F9B9
0x18004f985  mov     edx, 131h
0x18004f98a  jmp     loc_18004F714
0x18004f98f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004f996  jb      short loc_18004F9B9
0x18004f998  mov     edx, 130h
0x18004f99d  jmp     loc_18004F714
0x18004f9a2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004f9a9  jb      short loc_18004F9B9
0x18004f9ab  mov     edx, 12Fh
0x18004f9b0  jmp     loc_18004F714
0x18004f9b5  test    ebx, ebx
0x18004f9b7  jns     short loc_18004F9C9
0x18004f9b9  cmp     cs:byte_18008D62D, 1
0x18004f9c0  jb      short loc_18004F9F8
0x18004f9c2  mov     edx, 132h
0x18004f9c7  jmp     short loc_18004F9D7
0x18004f9c9  cmp     cs:byte_18008D62D, 8
0x18004f9d0  jb      short loc_18004F9F8
0x18004f9d2  mov     edx, 133h
0x18004f9d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f9de  lea     r8, WPP_c6ec3a891c39353f20252a4447583601_Traceguids
0x18004f9e5  mov     r9, rdi
0x18004f9e8  mov     [rsp+2C0h+dwOptions], ebx
0x18004f9ec  mov     rcx, [rcx+0D8h]
0x18004f9f3  call    WPP_SF_qD
0x18004f9f8  lea     rcx, [rsp+2C0h+hKey]
0x18004f9fd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004fa02  lea     rcx, [rsp+2C0h+var_268]
0x18004fa07  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004fa0c  mov     eax, ebx
0x18004fa0e  mov     rcx, [rbp+1C0h+var_40]
0x18004fa15  xor     rcx, rsp; StackCookie
0x18004fa18  call    __security_check_cookie
0x18004fa1d  mov     rbx, [rsp+2C0h+arg_10]
0x18004fa25  add     rsp, 290h
0x18004fa2c  pop     r15
0x18004fa2e  pop     r14
0x18004fa30  pop     r13
0x18004fa32  pop     r12
0x18004fa34  pop     rdi
0x18004fa35  pop     rsi
0x18004fa36  pop     rbp
0x18004fa37  retn
```
