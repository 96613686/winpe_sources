# DsmSetupRecorder::RecordInstallResults(void)

- ea: `0x180009928`
- end: `0x180009f13`
- name: `?RecordInstallResults@DsmSetupRecorder@@QEAAJXZ`
- size: `1515`
- prototype: `__int64 __fastcall(DsmSetupRecorder *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180008e20`

## callees

- `0x180002a24`
- `0x180005100`
- `0x1800080f0`
- `0x180009928`
- `0x18000c8b8`
- `0x18000e3cc`
- `0x1800112a4`
- `0x180015474`
- `0x180021998`
- `0x180022070`
- `0x180027ba8`
- `0x1800316a8`
- `0x1800317d0`
- `0x18003ee30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009983`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180009983`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000994b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000994b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009b2a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180009b2a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009a76`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009ebd`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009a76`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180009ebd`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800099ea`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800099ea`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180009b64`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180009b64`

## string_xrefs

- `0x180009962`: `onecoreuap\base\devices\setup\dsm\service\setuprecorder.cpp`
- `0x1800099b1`: `onecoreuap\base\devices\setup\dsm\service\setuprecorder.cpp`
- `0x1800099fa`: `onecoreuap\base\devices\setup\dsm\service\setuprecorder.cpp`
- `0x180009a66`: `onecoreuap\base\devices\setup\dsm\service\setuprecorder.cpp`
- `0x180009ef1`: `onecoreuap\base\devices\setup\dsm\service\setuprecorder.cpp`

## pseudocode

```c
__int64 __fastcall DsmSetupRecorder::RecordInstallResults(DsmSetupRecorder *this)
{
  RTL_SRWLOCK *v1; // rbx
  unsigned int i; // edx
  unsigned int v5; // ebx
  HRESULT v6; // eax
  int DevnodeList; // eax
  __int64 v8; // r9
  __int64 v9; // rdx
  unsigned int ulVal; // ecx
  const unsigned __int16 *v11; // rsi
  unsigned int j; // r14d
  int DeviceObjectStringProperty; // eax
  DsmSetupRecorder *v14; // rcx
  unsigned __int64 v15; // r14
  unsigned __int64 v16; // r15
  unsigned __int64 ElapsedMilliSeconds; // r12
  unsigned __int64 v18; // r13
  unsigned __int64 v19; // rbx
  PVOID *v20; // r10
  int bIgnoreCase; // [rsp+20h] [rbp-59h]
  int bIgnoreCasea; // [rsp+20h] [rbp-59h]
  __int64 v23; // [rsp+28h] [rbp-51h]
  __int64 v24; // [rsp+30h] [rbp-49h]
  RTL_SRWLOCK *v25; // [rsp+70h] [rbp-9h] BYREF
  struct tagPROPVARIANT pvar[3]; // [rsp+78h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  LPOLESTR lpsz; // [rsp+E0h] [rbp+67h] BYREF
  LPCWCH lpString1; // [rsp+E8h] [rbp+6Fh] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+F0h] [rbp+77h] BYREF
  unsigned __int64 v31; // [rsp+F8h] [rbp+7Fh]

  v1 = (RTL_SRWLOCK *)((char *)this + 8);
  AcquireSRWLockExclusive((PSRWLOCK)this + 1);
  v25 = v1;
  if ( *((_BYTE *)this + 4) )
  {
    for ( i = 0; i < 5; ++i )
    {
      if ( *((_BYTE *)this + 40 * (int)i + 128) )
      {
        v5 = -2147418113;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB7,
          (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\setuprecorder.cpp",
          (const char *)0x8000FFFFLL,
          bIgnoreCase);
        goto LABEL_57;
      }
    }
    *((_BYTE *)this + 4) = 0;
    lpsz = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &lpsz,
      0);
    v6 = StringFromCLSID((const IID *const)this + 1, &lpsz);
    v5 = v6;
    if ( v6 >= 0 )
    {
      if ( !IsContainerConnected(lpsz) )
      {
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpsz);
        v5 = 0;
        goto LABEL_57;
      }
      memset(pvar, 0, 24);
      DevnodeList = CDsmDeviceScan::GetDevnodeList(lpsz, pvar);
      v5 = DevnodeList;
      if ( DevnodeList >= 0 )
      {
        ulVal = pvar[0].ulVal;
        if ( pvar[0].lVal )
        {
          v11 = (const unsigned __int16 *)*((_QWORD *)this + 7);
          if ( !v11 )
          {
            v11 = (const unsigned __int16 *)*((_QWORD *)this + 8);
            if ( !v11 )
            {
              v11 = (const unsigned __int16 *)*((_QWORD *)this + 9);
              if ( !v11 )
                v11 = *pvar[0].cabstr.pElems;
            }
          }
          if ( (*((_BYTE *)this + 48) & 4) == 0 )
          {
            for ( j = 0; j < ulVal; ++j )
            {
              lpString1 = 0;
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                &lpString1,
                0);
              DeviceObjectStringProperty = GetDeviceObjectStringProperty(
                                             3,
                                             *(_QWORD *)&pvar[0].bstrblobVal.pData[8 * j],
                                             &DEVPKEY_Device_EnumeratorName,
                                             0,
                                             &lpString1,
                                             v23,
                                             v24);
              v5 = DeviceObjectStringProperty;
              if ( DeviceObjectStringProperty < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xE3,
                  (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\setuprecorder.cpp",
                  (const char *)(unsigned int)DeviceObjectStringProperty,
                  bIgnoreCasea);
                wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpString1);
                goto LABEL_18;
              }
              if ( CompareStringOrdinal(lpString1, -1, L"USB", -1, 1) == 2 )
              {
                *((_DWORD *)this + 9) = DsmSetupRecorder::GetDiscoveryMethodPosition(v14, lpString1);
                wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpString1);
                break;
              }
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpString1);
              ulVal = pvar[0].ulVal;
            }
          }
          UnbiasedTime = 0;
          QueryUnbiasedInterruptTime(&UnbiasedTime);
          v15 = (*((_QWORD *)this + 11) - *((_QWORD *)this + 10)) / 0x2710uLL;
          v16 = (UnbiasedTime - *((_QWORD *)this + 11)) / 0x2710;
          ElapsedMilliSeconds = CDsmTimer::GetElapsedMilliSeconds((DsmSetupRecorder *)((char *)this + 136), 1);
          v18 = CDsmTimer::GetElapsedMilliSeconds((DsmSetupRecorder *)((char *)this + 216), 1);
          v31 = CDsmTimer::GetElapsedMilliSeconds((DsmSetupRecorder *)((char *)this + 176), 1);
          v19 = CDsmTimer::GetElapsedMilliSeconds((DsmSetupRecorder *)((char *)this + 256), 1);
          v20 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                10,
                &WPP_b9560f17487330341036212e32e12e38_Traceguids,
                *((unsigned int *)this + 8));
              v20 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v20 != &WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)v20 + 28) & 1) != 0 )
              {
                WPP_SF_S(v20[2], 11, &WPP_b9560f17487330341036212e32e12e38_Traceguids, v11);
                v20 = (PVOID *)WPP_GLOBAL_Control;
              }
              if ( v20 != &WPP_GLOBAL_Control )
              {
                if ( (*((_BYTE *)v20 + 28) & 1) != 0 )
                {
                  WPP_SF_ID(v20[2], 12);
                  v20 = (PVOID *)WPP_GLOBAL_Control;
                }
                if ( v20 != &WPP_GLOBAL_Control )
                {
                  if ( (*((_BYTE *)v20 + 28) & 1) != 0 )
                  {
                    WPP_SF_ID(v20[2], 13);
                    v20 = (PVOID *)WPP_GLOBAL_Control;
                  }
                  if ( v20 != &WPP_GLOBAL_Control )
                  {
                    if ( (*((_BYTE *)v20 + 28) & 1) != 0 )
                    {
                      WPP_SF_ID(v20[2], 14);
                      v20 = (PVOID *)WPP_GLOBAL_Control;
                    }
                    if ( v20 != &WPP_GLOBAL_Control )
                    {
                      if ( (*((_BYTE *)v20 + 28) & 1) != 0 )
                      {
                        WPP_SF_ID(v20[2], 15);
                        v20 = (PVOID *)WPP_GLOBAL_Control;
                      }
                      if ( v20 != &WPP_GLOBAL_Control )
                      {
                        if ( (*((_BYTE *)v20 + 28) & 1) != 0 )
                        {
                          WPP_SF_ID(v20[2], 16);
                          v20 = (PVOID *)WPP_GLOBAL_Control;
                        }
                        if ( v20 != &WPP_GLOBAL_Control && (*((_BYTE *)v20 + 28) & 1) != 0 )
                          WPP_SF_ID(v20[2], 17);
                      }
                    }
                  }
                }
              }
            }
          }
          LogDeviceSetupEvent(
            (struct _GUID *)this + 1,
            v11,
            *((_DWORD *)this + 8),
            *((_DWORD *)this + 9),
            *((_DWORD *)this + 10),
            *((_DWORD *)this + 12),
            *(_DWORD *)this,
            *((_DWORD *)this + 11),
            v15,
            v16,
            ElapsedMilliSeconds,
            v18,
            v31,
            v19);
          PropVariantClear((PROPVARIANT *)pvar);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpsz);
          v5 = 0;
          goto LABEL_57;
        }
        v5 = -2147418113;
        v9 = 196;
        v8 = 2147549183LL;
      }
      else
      {
        v8 = (unsigned int)DevnodeList;
        v9 = 195;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\setuprecorder.cpp",
        (const char *)v8,
        bIgnoreCase);
LABEL_18:
      PropVariantClear((PROPVARIANT *)pvar);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBC,
        (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\setuprecorder.cpp",
        (const char *)(unsigned int)v6,
        bIgnoreCase);
    }
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpsz);
LABEL_57:
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v25);
    return v5;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xB4,
    (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\setuprecorder.cpp",
    (const char *)0x80004004LL,
    bIgnoreCase);
  if ( v1 )
    ReleaseSRWLockExclusive(v1);
  return 2147500036LL;
}

```

## disassembly

```asm
0x180009928  push    rbp
0x18000992a  push    rbx
0x18000992b  push    rsi
0x18000992c  push    rdi
0x18000992d  push    r12
0x18000992f  push    r13
0x180009931  push    r14
0x180009933  push    r15
0x180009935  lea     rbp, [rsp-1Fh]
0x18000993a  sub     rsp, 98h
0x180009941  lea     rbx, [rcx+8]
0x180009945  mov     rdi, rcx
0x180009948  mov     rcx, rbx; SRWLock
0x18000994b  call    cs:__imp_AcquireSRWLockExclusive
0x180009951  xor     r15d, r15d
0x180009954  mov     [rbp+57h+var_60], rbx
0x180009958  cmp     [rdi+4], r15b
0x18000995c  jnz     short loc_180009990
0x18000995e  mov     rcx, [rbp+5Fh]; this
0x180009962  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x180009969  mov     edi, 80004004h
0x18000996e  mov     edx, 0B4h; void *
0x180009973  mov     r9d, edi; char *
0x180009976  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000997b  test    rbx, rbx
0x18000997e  jz      short loc_180009989
0x180009980  mov     rcx, rbx; SRWLock
0x180009983  call    cs:__imp_ReleaseSRWLockExclusive
0x180009989  mov     eax, edi
0x18000998b  jmp     loc_180009ED9
0x180009990  mov     edx, r15d
0x180009993  cmp     edx, 5
0x180009996  jnb     short loc_1800099CF
0x180009998  movsxd  rax, edx
0x18000999b  lea     rcx, [rax+rax*4]
0x18000999f  cmp     [rdi+rcx*8+80h], r15b
0x1800099a7  jnz     short loc_1800099AD
0x1800099a9  inc     edx
0x1800099ab  jmp     short loc_180009993
0x1800099ad  mov     rcx, [rbp+5Fh]; this
0x1800099b1  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x1800099b8  mov     ebx, 8000FFFFh
0x1800099bd  mov     edx, 0B7h; void *
0x1800099c2  mov     r9d, ebx; char *
0x1800099c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800099ca  jmp     loc_180009ECE
0x1800099cf  xor     edx, edx
0x1800099d1  mov     [rdi+4], r15b
0x1800099d5  lea     rcx, [rbp+57h+lpsz]
0x1800099d9  mov     [rbp+57h+lpsz], r15
0x1800099dd  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800099e2  lea     rcx, [rdi+10h]; rclsid
0x1800099e6  lea     rdx, [rbp+57h+lpsz]; lplpsz
0x1800099ea  call    cs:__imp_StringFromCLSID
0x1800099f0  mov     ebx, eax
0x1800099f2  test    eax, eax
0x1800099f4  jns     short loc_180009A1C
0x1800099f6  mov     rcx, [rbp+5Fh]; this
0x1800099fa  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x180009a01  mov     r9d, eax; char *
0x180009a04  mov     edx, 0BCh; void *
0x180009a09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009a0e  lea     rcx, [rbp+57h+lpsz]
0x180009a12  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180009a17  jmp     loc_180009ECE
0x180009a1c  mov     rcx, [rbp+57h+lpsz]; unsigned __int16 *
0x180009a20  call    ?IsContainerConnected@@YA_NPEBG@Z; IsContainerConnected(ushort const *)
0x180009a25  test    al, al
0x180009a27  jnz     short loc_180009A3A
0x180009a29  lea     rcx, [rbp+57h+lpsz]
0x180009a2d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180009a32  mov     ebx, r15d
0x180009a35  jmp     loc_180009ECE
0x180009a3a  mov     rcx, [rbp+57h+lpsz]; lpsz
0x180009a3e  lea     rdx, [rbp+57h+pvar]; struct tagPROPVARIANT *
0x180009a42  xorps   xmm0, xmm0
0x180009a45  xor     eax, eax
0x180009a47  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180009a4b  mov     [rbp+57h+var_48], rax
0x180009a4f  call    ?GetDevnodeList@CDsmDeviceScan@@SAJPEBGPEAUtagPROPVARIANT@@@Z; CDsmDeviceScan::GetDevnodeList(ushort const *,tagPROPVARIANT *)
0x180009a54  mov     ebx, eax
0x180009a56  test    eax, eax
0x180009a58  jns     short loc_180009A7E
0x180009a5a  mov     r9d, eax; char *
0x180009a5d  mov     edx, 0C3h; void *
0x180009a62  mov     rcx, [rbp+5Fh]; this
0x180009a66  lea     r8, aOnecoreuapBase_14; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x180009a6d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009a72  lea     rcx, [rbp+57h+pvar]; pvar
0x180009a76  call    cs:__imp_PropVariantClear
0x180009a7c  jmp     short loc_180009A0E
0x180009a7e  mov     rcx, [rbp+57h+pvar+8]
0x180009a82  test    ecx, ecx
0x180009a84  jnz     short loc_180009A95
0x180009a86  mov     ebx, 8000FFFFh
0x180009a8b  mov     edx, 0C4h
0x180009a90  mov     r9d, ebx
0x180009a93  jmp     short loc_180009A62
0x180009a95  mov     rsi, [rdi+38h]
0x180009a99  test    rsi, rsi
0x180009a9c  jnz     short loc_180009AB7
0x180009a9e  mov     rsi, [rdi+40h]
0x180009aa2  test    rsi, rsi
0x180009aa5  jnz     short loc_180009AB7
0x180009aa7  mov     rsi, [rdi+48h]
0x180009aab  test    rsi, rsi
0x180009aae  jnz     short loc_180009AB7
0x180009ab0  mov     rax, [rbp+57h+var_48]
0x180009ab4  mov     rsi, [rax]
0x180009ab7  test    byte ptr [rdi+30h], 4
0x180009abb  jnz     loc_180009B5C
0x180009ac1  mov     r14d, r15d
0x180009ac4  or      r12d, 0FFFFFFFFh
0x180009ac8  cmp     r14d, ecx
0x180009acb  jnb     loc_180009B5C
0x180009ad1  xor     edx, edx
0x180009ad3  mov     [rbp+57h+lpString1], r15
0x180009ad7  lea     rcx, [rbp+57h+lpString1]
0x180009adb  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180009ae0  mov     rdx, [rbp+57h+var_48]
0x180009ae4  lea     rcx, [rbp+57h+lpString1]
0x180009ae8  mov     eax, r14d
0x180009aeb  lea     r8, DEVPKEY_Device_EnumeratorName
0x180009af2  xor     r9d, r9d
0x180009af5  mov     qword ptr [rsp+0D0h+bIgnoreCase], rcx; int
0x180009afa  mov     rdx, [rdx+rax*8]
0x180009afe  lea     ecx, [r9+3]
0x180009b02  call    ?GetDeviceObjectStringProperty@@YAJW4_DEV_OBJECT_TYPE@@PEBGAEBU_DEVPROPKEY@@_NPEAPEAG@Z; GetDeviceObjectStringProperty(_DEV_OBJECT_TYPE,ushort const *,_DEVPROPKEY const &,bool,ushort * *)
0x180009b07  mov     ebx, eax
0x180009b09  test    eax, eax
0x180009b0b  js      loc_180009EED
0x180009b11  mov     rcx, [rbp+57h+lpString1]; lpString1
0x180009b15  lea     r8, String2; "USB"
0x180009b1c  mov     r9d, r12d; cchCount2
0x180009b1f  mov     [rsp+0D0h+bIgnoreCase], 1; bIgnoreCase
0x180009b27  mov     edx, r12d; cchCount1
0x180009b2a  call    cs:__imp_CompareStringOrdinal
0x180009b30  cmp     eax, 2
0x180009b33  jz      short loc_180009B47
0x180009b35  lea     rcx, [rbp+57h+lpString1]
0x180009b39  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180009b3e  mov     rcx, [rbp+57h+pvar+8]
0x180009b42  inc     r14d
0x180009b45  jmp     short loc_180009AC8
0x180009b47  mov     rdx, [rbp+57h+lpString1]; unsigned __int16 *
0x180009b4b  call    ?GetDiscoveryMethodPosition@DsmSetupRecorder@@AEAAKPEBG@Z; DsmSetupRecorder::GetDiscoveryMethodPosition(ushort const *)
0x180009b50  lea     rcx, [rbp+57h+lpString1]
0x180009b54  mov     [rdi+24h], eax
0x180009b57  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180009b5c  lea     rcx, [rbp+57h+UnbiasedTime]; UnbiasedTime
0x180009b60  mov     [rbp+57h+UnbiasedTime], r15
0x180009b64  call    cs:__imp_QueryUnbiasedInterruptTime
0x180009b6a  mov     rcx, [rdi+58h]
0x180009b6e  mov     r8, 346DC5D63886594Bh
0x180009b78  sub     rcx, [rdi+50h]
0x180009b7c  mov     rax, r8
0x180009b7f  mul     rcx
0x180009b82  mov     rcx, [rbp+57h+UnbiasedTime]
0x180009b86  mov     rax, r8
0x180009b89  sub     rcx, [rdi+58h]
0x180009b8d  mov     r14, rdx
0x180009b90  mul     rcx
0x180009b93  lea     rcx, [rdi+88h]; this
0x180009b9a  shr     r14, 0Bh
0x180009b9e  mov     r15, rdx
0x180009ba1  mov     dl, 1; bool
0x180009ba3  shr     r15, 0Bh
0x180009ba7  call    ?GetElapsedMilliSeconds@CDsmTimer@@QEAA_K_N@Z; CDsmTimer::GetElapsedMilliSeconds(bool)
0x180009bac  mov     dl, 1; bool
0x180009bae  lea     rcx, [rdi+0D8h]; this
0x180009bb5  mov     r12, rax
0x180009bb8  call    ?GetElapsedMilliSeconds@CDsmTimer@@QEAA_K_N@Z; CDsmTimer::GetElapsedMilliSeconds(bool)
0x180009bbd  mov     dl, 1; bool
0x180009bbf  lea     rcx, [rdi+0B0h]; this
0x180009bc6  mov     r13, rax
0x180009bc9  call    ?GetElapsedMilliSeconds@CDsmTimer@@QEAA_K_N@Z; CDsmTimer::GetElapsedMilliSeconds(bool)
0x180009bce  mov     dl, 1; bool
0x180009bd0  mov     [rbp+57h+arg_18], rax
0x180009bd4  lea     rcx, [rdi+100h]; this
0x180009bdb  call    ?GetElapsedMilliSeconds@CDsmTimer@@QEAA_K_N@Z; CDsmTimer::GetElapsedMilliSeconds(bool)
0x180009be0  mov     rbx, rax
0x180009be3  mov     r10, cs:WPP_GLOBAL_Control
0x180009bea  lea     rax, WPP_GLOBAL_Control
0x180009bf1  cmp     r10, rax
0x180009bf4  jz      loc_180009E68
0x180009bfa  test    byte ptr [r10+1Ch], 1
0x180009bff  jz      short loc_180009C28
0x180009c01  mov     r9d, [rdi+20h]
0x180009c05  lea     r8, WPP_b9560f17487330341036212e32e12e38_Traceguids
0x180009c0c  mov     rcx, [r10+10h]
0x180009c10  mov     edx, 0Ah
0x180009c15  call    WPP_SF_d
0x180009c1a  mov     r10, cs:WPP_GLOBAL_Control
0x180009c21  lea     rax, WPP_GLOBAL_Control
0x180009c28  cmp     r10, rax
0x180009c2b  jz      loc_180009E68
0x180009c31  test    byte ptr [r10+1Ch], 1
0x180009c36  jz      short loc_180009C5E
0x180009c38  mov     rcx, [r10+10h]
0x180009c3c  lea     r8, WPP_b9560f17487330341036212e32e12e38_Traceguids
0x180009c43  mov     edx, 0Bh
0x180009c48  mov     r9, rsi
0x180009c4b  call    WPP_SF_S
0x180009c50  mov     r10, cs:WPP_GLOBAL_Control
0x180009c57  lea     rax, WPP_GLOBAL_Control
0x180009c5e  cmp     r10, rax
0x180009c61  jz      loc_180009E68
0x180009c67  test    byte ptr [r10+1Ch], 1
0x180009c6c  mov     rcx, 624DD2F1A9FBE77h
0x180009c76  jz      short loc_180009CC4
0x180009c78  mov     rax, rcx
0x180009c7b  mov     r9, r14
0x180009c7e  mul     r14
0x180009c81  mov     ecx, r14d
0x180009c84  sub     r9, rdx
0x180009c87  shr     r9, 1
0x180009c8a  add     r9, rdx
0x180009c8d  mov     edx, 0Ch
0x180009c92  shr     r9, 9
0x180009c96  imul    eax, r9d, 3E8h
0x180009c9d  sub     ecx, eax
0x180009c9f  mov     [rsp+0D0h+bIgnoreCase], ecx
0x180009ca3  mov     rcx, [r10+10h]
0x180009ca7  call    WPP_SF_ID
0x180009cac  mov     r10, cs:WPP_GLOBAL_Control
0x180009cb3  lea     rax, WPP_GLOBAL_Control
0x180009cba  mov     rcx, 624DD2F1A9FBE77h
0x180009cc4  cmp     r10, rax
0x180009cc7  jz      loc_180009E68
0x180009ccd  test    byte ptr [r10+1Ch], 1
0x180009cd2  jz      short loc_180009D16
0x180009cd4  mov     rax, rcx
0x180009cd7  mov     r9, r15
0x180009cda  mul     r15
0x180009cdd  mov     ecx, r15d
0x180009ce0  sub     r9, rdx
0x180009ce3  shr     r9, 1
0x180009ce6  add     r9, rdx
0x180009ce9  mov     edx, 0Dh
0x180009cee  shr     r9, 9
0x180009cf2  imul    eax, r9d, 3E8h
0x180009cf9  sub     ecx, eax
0x180009cfb  mov     [rsp+0D0h+bIgnoreCase], ecx
0x180009cff  mov     rcx, [r10+10h]
0x180009d03  call    WPP_SF_ID
0x180009d08  mov     r10, cs:WPP_GLOBAL_Control
0x180009d0f  lea     rax, WPP_GLOBAL_Control
0x180009d16  cmp     r10, rax
0x180009d19  jz      loc_180009E68
0x180009d1f  test    byte ptr [r10+1Ch], 1
0x180009d24  jz      short loc_180009D6F
0x180009d26  mov     ecx, r12d
0x180009d29  mov     rax, 624DD2F1A9FBE77h
0x180009d33  mul     r12
0x180009d36  mov     r9, r12
0x180009d39  sub     r9, rdx
0x180009d3c  shr     r9, 1
0x180009d3f  add     r9, rdx
0x180009d42  mov     edx, 0Eh
0x180009d47  shr     r9, 9
0x180009d4b  imul    eax, r9d, 3E8h
0x180009d52  sub     ecx, eax
0x180009d54  mov     [rsp+0D0h+bIgnoreCase], ecx
0x180009d58  mov     rcx, [r10+10h]
0x180009d5c  call    WPP_SF_ID
0x180009d61  mov     r10, cs:WPP_GLOBAL_Control
0x180009d68  lea     rax, WPP_GLOBAL_Control
0x180009d6f  cmp     r10, rax
0x180009d72  jz      loc_180009E68
0x180009d78  test    byte ptr [r10+1Ch], 1
0x180009d7d  jz      short loc_180009DC8
0x180009d7f  mov     ecx, r13d
0x180009d82  mov     rax, 624DD2F1A9FBE77h
0x180009d8c  mul     r13
0x180009d8f  mov     r9, r13
0x180009d92  sub     r9, rdx
0x180009d95  shr     r9, 1
0x180009d98  add     r9, rdx
0x180009d9b  mov     edx, 0Fh
0x180009da0  shr     r9, 9
0x180009da4  imul    eax, r9d, 3E8h
0x180009dab  sub     ecx, eax
0x180009dad  mov     [rsp+0D0h+bIgnoreCase], ecx
0x180009db1  mov     rcx, [r10+10h]
0x180009db5  call    WPP_SF_ID
0x180009dba  mov     r10, cs:WPP_GLOBAL_Control
0x180009dc1  lea     rax, WPP_GLOBAL_Control
0x180009dc8  cmp     r10, rax
0x180009dcb  jz      loc_180009E68
0x180009dd1  test    byte ptr [r10+1Ch], 1
0x180009dd6  jz      short loc_180009E22
0x180009dd8  mov     rcx, [rbp+57h+arg_18]
0x180009ddc  mov     rax, 624DD2F1A9FBE77h
0x180009de6  mul     rcx
0x180009de9  mov     r9, rcx
0x180009dec  sub     r9, rdx
0x180009def  shr     r9, 1
0x180009df2  add     r9, rdx
0x180009df5  mov     edx, 10h
0x180009dfa  shr     r9, 9
  ... truncated ...
```
