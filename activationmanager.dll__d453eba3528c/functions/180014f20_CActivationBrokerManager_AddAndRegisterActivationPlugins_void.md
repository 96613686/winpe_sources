# CActivationBrokerManager::_AddAndRegisterActivationPlugins(void)

- ea: `0x180014f20`
- end: `0x1800153da`
- name: `?_AddAndRegisterActivationPlugins@CActivationBrokerManager@@AEAAJXZ`
- size: `1210`
- prototype: `__int64 __fastcall(CActivationBrokerManager *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800153e0`

## callees

- `0x18000c9e0`
- `0x180011328`
- `0x180014f20`
- `0x180015a88`
- `0x180015b7c`
- `0x18004be80`
- `0x18005ae90`
- `0x18005b37c`
- `0x18005d2ad`
- `0x18006828c`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001514e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001528e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001514e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001528e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800150fc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001523c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800150fc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001523c`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180014fda`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180015066`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180014fda`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180015066`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800151a2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800151a2`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180014fba`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180015359`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180014fba`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180015359`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800153b2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800153b2`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001503d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001503d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014f83`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014f83`

## string_xrefs

- `0x180014f75`: `System\ActivationBroker\Plugins`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CActivationBrokerManager::_AddAndRegisterActivationPlugins(RTL_SRWLOCK *this)
{
  LSTATUS v2; // eax
  int i; // ebx
  DWORD v4; // r15d
  __int64 v5; // rcx
  LSTATUS ValueW; // eax
  bool v7; // sf
  char *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r8
  _DWORD *v11; // rbx
  GUID v12; // xmm1
  RTL_SRWLOCK *v13; // rdi
  int v14; // esi
  char *Ptr; // rdx
  PVOID v16; // rdx
  _QWORD *v17; // rcx
  char *v18; // rdx
  HRESULT v19; // ebx
  __int64 v20; // rbx
  _OWORD *v21; // rsi
  char *v22; // rax
  _DWORD *v23; // rdi
  GUID v24; // xmm1
  _QWORD *v25; // rcx
  __int64 v26; // rcx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcbData[4]; // [rsp+50h] [rbp-B0h] BYREF
  GUID pclsid; // [rsp+60h] [rbp-A0h] BYREF
  char v32[16]; // [rsp+70h] [rbp-90h] BYREF
  GUID Buf1; // [rsp+80h] [rbp-80h] BYREF
  GUID *p_pclsid; // [rsp+90h] [rbp-70h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  WCHAR Name[40]; // [rsp+A0h] [rbp-60h] BYREF
  OLECHAR pvData[40]; // [rsp+F0h] [rbp-10h] BYREF

  pclsid = 0;
  cchName = 39;
  hKey = 0;
  v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\ActivationBroker\\Plugins", 0, 0x20019u, &hKey);
  i = v2;
  if ( v2 )
  {
    if ( v2 > 0 )
      i = (unsigned __int16)v2 | 0x80070000;
  }
  else
  {
    v4 = 0;
    for ( i = RegEnumKeyExW(hKey, 0, Name, &cchName, 0, 0, 0, 0);
          !i;
          i = RegEnumKeyExW(hKey, v4, Name, &cchName, 0, 0, 0, 0) )
    {
      if ( CLSIDFromString(Name, &pclsid) >= 0 && memcmp_0(&pclsid, &GUID_NULL, 0x10u) )
      {
        pcbData[0] = 78;
        ValueW = RegGetValueW(hKey, Name, L"TypeID", 2u, 0, pvData, pcbData);
        v7 = ValueW < 0;
        if ( ValueW > 0 )
          v7 = 1;
        if ( !v7 )
        {
          Buf1 = 0;
          if ( CLSIDFromString(pvData, &Buf1) >= 0 )
          {
            if ( memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
            {
              v8 = (char *)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
              v11 = v8;
              if ( v8 )
              {
                v12 = pclsid;
                *(GUID *)(v8 + 8) = Buf1;
                *(GUID *)(v8 + 24) = v12;
                *((_QWORD *)v8 + 5) = 0;
                Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v8 + 40, v9, v10);
                *(_QWORD *)v11 = &CRefCountedObject<CActivationBrokerManager::_PluginInfo>::`vftable';
                v11[12] = 0;
              }
              else
              {
                v11 = 0;
              }
              if ( v11 )
              {
                (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v11 + 8LL))(v11);
                AcquireSRWLockExclusive(this + 26);
                v13 = this + 22;
                v14 = 0;
                Ptr = (char *)this[23].Ptr;
                if ( Ptr != this[25].Ptr
                  || (v14 = CTSimpleArray<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>,4294967294,CTPolicyLocalMem<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>>>::_EnsureCapacity(
                              v13,
                              Ptr + 1),
                      v14 >= 0) )
                {
                  ++this[23].Ptr;
                  v16 = v13->Ptr;
                  v17 = (char *)this[22].Ptr + 8 * ((__int64)this[23].Ptr - 1);
                  if ( v17 )
                  {
                    *v17 = v11;
                    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v17, v16, v10);
                  }
                }
                if ( this != (RTL_SRWLOCK *)-208LL )
                  ReleaseSRWLockExclusive(this + 26);
              }
              else
              {
                v14 = -2147024882;
              }
              if ( v11 )
                (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v11 + 16LL))(v11);
              if ( v14 >= 0 )
                goto LABEL_41;
            }
          }
        }
        *(_QWORD *)&Buf1.Data1 = 0;
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&Buf1);
        v19 = CoCreateInstance(&pclsid, 0, 1u, &GUID_75f91a54_fa3d_431d_8ee7_6bf000847e77, (LPVOID *)&Buf1);
        if ( v19 >= 0 )
        {
          v20 = *(_QWORD *)&Buf1.Data1;
          v21 = (_OWORD *)(*(__int64 (__fastcall **)(_QWORD, char *))(**(_QWORD **)&Buf1.Data1 + 24LL))(
                            *(_QWORD *)&Buf1.Data1,
                            v32);
          v22 = (char *)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
          v23 = v22;
          if ( v22 )
          {
            v24 = pclsid;
            *(_OWORD *)(v22 + 8) = *v21;
            *(GUID *)(v22 + 24) = v24;
            *((_QWORD *)v22 + 5) = v20;
            Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v22 + 40, v18, v10);
            *(_QWORD *)v23 = &CRefCountedObject<CActivationBrokerManager::_PluginInfo>::`vftable';
            v23[12] = 0;
          }
          else
          {
            v23 = 0;
          }
          if ( v23 )
          {
            (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v23 + 8LL))(v23);
            AcquireSRWLockExclusive(this + 26);
            v19 = 0;
            v18 = (char *)this[23].Ptr;
            if ( v18 != this[25].Ptr
              || (v19 = CTSimpleArray<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>,4294967294,CTPolicyLocalMem<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>>>::_EnsureCapacity(
                          &this[22],
                          v18 + 1),
                  v19 >= 0) )
            {
              v25 = (char *)this[22].Ptr + 8 * (__int64)this[23].Ptr++;
              if ( v25 )
              {
                *v25 = v23;
                Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(v25, v18, v10);
              }
            }
            if ( this != (RTL_SRWLOCK *)-208LL )
              ReleaseSRWLockExclusive(this + 26);
          }
          else
          {
            v19 = -2147024882;
          }
          if ( v23 )
            (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v23 + 16LL))(v23);
        }
        v26 = *(_QWORD *)&Buf1.Data1;
        if ( *(_QWORD *)&Buf1.Data1 )
        {
          *(_QWORD *)&Buf1.Data1 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        }
        if ( v19 < 0 )
        {
          if ( (byte_1800D1F01 & 4) != 0 )
            McTemplateU0qj_EventWriteTransfer(v26, v18, (unsigned int)v19, &pclsid);
        }
        else
        {
LABEL_41:
          if ( (byte_1800D1F01 & 8) != 0 )
          {
            p_pclsid = &pclsid;
            v35 = 16;
            McGenEventWrite_EventWriteTransfer(
              MICROSOFT_WINDOWS_APPMODEL_EXEC_PUBLISHER_Context,
              AM_CreatedActivationPlugin,
              v10,
              2);
          }
        }
      }
      cchName = 39;
      ++v4;
    }
    if ( i == 259 )
    {
      i = 0;
    }
    else
    {
      if ( i > 0 )
        i = (unsigned __int16)i | 0x80070000;
      if ( (byte_1800D1F01 & 4) != 0 )
        McTemplateU0q_EventWriteTransfer(v5, AM_FailedToReadActivationPlugins, (unsigned int)i);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)i;
}

```

## disassembly

```asm
0x180014f20  push    rbp
0x180014f22  push    rbx
0x180014f23  push    rsi
0x180014f24  push    rdi
0x180014f25  push    r12
0x180014f27  push    r13
0x180014f29  push    r14
0x180014f2b  push    r15
0x180014f2d  lea     rbp, [rsp-58h]
0x180014f32  sub     rsp, 158h
0x180014f39  mov     rax, cs:__security_cookie
0x180014f40  xor     rax, rsp
0x180014f43  mov     [rbp+90h+var_50], rax
0x180014f47  mov     r13, rcx
0x180014f4a  xorps   xmm0, xmm0
0x180014f4d  movups  xmmword ptr [rsp+190h+pclsid.Data1], xmm0
0x180014f52  mov     [rsp+190h+cchName], 27h ; '''
0x180014f5a  xor     r12d, r12d
0x180014f5d  mov     [rsp+190h+hKey], r12
0x180014f62  lea     rax, [rsp+190h+hKey]
0x180014f67  mov     [rsp+190h+phkResult], rax; phkResult
0x180014f6c  mov     r9d, 20019h; samDesired
0x180014f72  xor     r8d, r8d; ulOptions
0x180014f75  lea     rdx, aSystemActivati; "System\\ActivationBroker\\Plugins"
0x180014f7c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014f83  call    cs:__imp_RegOpenKeyExW
0x180014f89  mov     ebx, eax
0x180014f8b  test    eax, eax
0x180014f8d  jnz     loc_18001539D
0x180014f93  mov     r15d, r12d
0x180014f96  mov     [rsp+190h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180014f9b  mov     [rsp+190h+lpcchClass], r12; lpcchClass
0x180014fa0  mov     [rsp+190h+lpClass], r12; lpClass
0x180014fa5  mov     [rsp+190h+phkResult], r12; lpReserved
0x180014faa  lea     r9, [rsp+190h+cchName]; lpcchName
0x180014faf  lea     r8, [rbp+90h+Name]; lpName
0x180014fb3  xor     edx, edx; dwIndex
0x180014fb5  mov     rcx, [rsp+190h+hKey]; hKey
0x180014fba  call    cs:__imp_RegEnumKeyExW
0x180014fc0  mov     ebx, eax
0x180014fc2  test    eax, eax
0x180014fc4  jnz     loc_180015369
0x180014fca  lea     r14, ??_7?$CRefCountedObject@U_PluginInfo@CActivationBrokerManager@@@@6B@; const CRefCountedObject<CActivationBrokerManager::_PluginInfo>::`vftable'
0x180014fd1  lea     rdx, [rsp+190h+pclsid]; pclsid
0x180014fd6  lea     rcx, [rbp+90h+Name]; lpsz
0x180014fda  call    cs:__imp_CLSIDFromString
0x180014fe0  test    eax, eax
0x180014fe2  js      loc_180015329
0x180014fe8  mov     r8d, 10h; Size
0x180014fee  lea     rdx, GUID_NULL; Buf2
0x180014ff5  lea     rcx, [rsp+190h+pclsid]; Buf1
0x180014ffa  call    memcmp_0
0x180014fff  test    eax, eax
0x180015001  jz      loc_180015329
0x180015007  mov     [rsp+190h+pcbData], 4Eh ; 'N'
0x18001500f  lea     rax, [rsp+190h+pcbData]
0x180015014  mov     [rsp+190h+lpcchClass], rax; pcbData
0x180015019  lea     rax, [rbp+90h+pvData]
0x18001501d  mov     [rsp+190h+lpClass], rax; pvData
0x180015022  mov     [rsp+190h+phkResult], r12; pdwType
0x180015027  mov     r9d, 2; dwFlags
0x18001502d  lea     r8, aTypeid; "TypeID"
0x180015034  lea     rdx, [rbp+90h+Name]; lpSubKey
0x180015038  mov     rcx, [rsp+190h+hKey]; hkey
0x18001503d  call    cs:__imp_RegGetValueW
0x180015043  test    eax, eax
0x180015045  jle     short loc_180015051
0x180015047  movzx   eax, ax
0x18001504a  or      eax, 80070000h
0x18001504f  test    eax, eax
0x180015051  js      loc_180015178
0x180015057  xorps   xmm0, xmm0
0x18001505a  movups  xmmword ptr [rbp+90h+Buf1.Data1], xmm0
0x18001505e  lea     rdx, [rbp+90h+Buf1]; pclsid
0x180015062  lea     rcx, [rbp+90h+pvData]; lpsz
0x180015066  call    cs:__imp_CLSIDFromString
0x18001506c  test    eax, eax
0x18001506e  js      loc_180015178
0x180015074  mov     r8d, 10h; Size
0x18001507a  lea     rdx, GUID_NULL; Buf2
0x180015081  lea     rcx, [rbp+90h+Buf1]; Buf1
0x180015085  call    memcmp_0
0x18001508a  test    eax, eax
0x18001508c  jz      loc_180015178
0x180015092  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180015099  mov     ecx, 38h ; '8'; unsigned __int64
0x18001509e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800150a3  mov     rbx, rax
0x1800150a6  test    rax, rax
0x1800150a9  jz      short loc_1800150D1
0x1800150ab  movaps  xmm1, xmmword ptr [rsp+190h+pclsid.Data1]
0x1800150b0  movaps  xmm0, xmmword ptr [rbp+90h+Buf1.Data1]
0x1800150b4  movups  xmmword ptr [rax+8], xmm0
0x1800150b8  movups  xmmword ptr [rax+18h], xmm1
0x1800150bc  lea     rcx, [rax+28h]
0x1800150c0  mov     [rcx], r12
0x1800150c3  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x1800150c8  mov     [rbx], r14
0x1800150cb  mov     [rbx+30h], r12d
0x1800150cf  jmp     short loc_1800150D4
0x1800150d1  mov     rbx, r12
0x1800150d4  test    rbx, rbx
0x1800150d7  jz      short loc_1800150E9
0x1800150d9  mov     rax, [rbx]
0x1800150dc  mov     rcx, rbx
0x1800150df  mov     rax, [rax+8]
0x1800150e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800150e8  nop
0x1800150e9  test    rbx, rbx
0x1800150ec  jz      loc_18001520B
0x1800150f2  lea     r14, [r13+0D0h]
0x1800150f9  mov     rcx, r14; SRWLock
0x1800150fc  call    cs:__imp_AcquireSRWLockExclusive
0x180015102  lea     rdi, [r13+0B0h]
0x180015109  mov     esi, r12d
0x18001510c  mov     rdx, [rdi+8]
0x180015110  cmp     rdx, [rdi+18h]
0x180015114  jnz     short loc_180015127
0x180015116  inc     rdx
0x180015119  mov     rcx, rdi
0x18001511c  call    ?_EnsureCapacity@?$CTSimpleArray@V?$ComPtr@V?$CRefCountedObject@U_PluginInfo@CActivationBrokerManager@@@@@WRL@Microsoft@@$0PPPPPPPO@V?$CTPolicyLocalMem@V?$ComPtr@V?$CRefCountedObject@U_PluginInfo@CActivationBrokerManager@@@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@V?$CRefCountedObject@U_PluginInfo@CActivationBrokerManager@@@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardMergeHelper@V?$ComPtr@V?$CRefCountedObject@U_PluginInfo@CActivationBrokerManager@@@@@WRL@Microsoft@@@@@@QEAAJ_K0@Z; CTSimpleArray<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>,4294967294,CTPolicyLocalMem<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x180015121  mov     esi, eax
0x180015123  test    eax, eax
0x180015125  js      short loc_180015146
0x180015127  inc     qword ptr [rdi+8]
0x18001512b  mov     rcx, [rdi+8]
0x18001512f  mov     rdx, [rdi]
0x180015132  dec     rcx
0x180015135  lea     rcx, [rdx+rcx*8]
0x180015139  test    rcx, rcx
0x18001513c  jz      short loc_180015146
0x18001513e  mov     [rcx], rbx
0x180015141  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180015146  test    r14, r14
0x180015149  jz      short loc_180015154
0x18001514b  mov     rcx, r14; SRWLock
0x18001514e  call    cs:__imp_ReleaseSRWLockExclusive
0x180015154  lea     r14, ??_7?$CRefCountedObject@U_PluginInfo@CActivationBrokerManager@@@@6B@; const CRefCountedObject<CActivationBrokerManager::_PluginInfo>::`vftable'
0x18001515b  test    rbx, rbx
0x18001515e  jz      short loc_180015170
0x180015160  mov     rax, [rbx]
0x180015163  mov     rcx, rbx
0x180015166  mov     rax, [rax+10h]
0x18001516a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001516f  nop
0x180015170  test    esi, esi
0x180015172  jns     loc_1800152CE
0x180015178  mov     qword ptr [rbp+90h+Buf1.Data1], r12
0x18001517c  lea     rcx, [rbp+90h+Buf1]
0x180015180  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180015185  lea     rax, [rbp+90h+Buf1]
0x180015189  mov     [rsp+190h+phkResult], rax; ppv
0x18001518e  lea     r9, _GUID_75f91a54_fa3d_431d_8ee7_6bf000847e77; riid
0x180015195  xor     edx, edx; pUnkOuter
0x180015197  mov     r8d, 1; dwClsContext
0x18001519d  lea     rcx, [rsp+190h+pclsid]; rclsid
0x1800151a2  call    cs:__imp_CoCreateInstance
0x1800151a8  mov     ebx, eax
0x1800151aa  test    eax, eax
0x1800151ac  js      loc_1800152B0
0x1800151b2  mov     rbx, qword ptr [rbp+90h+Buf1.Data1]
0x1800151b6  mov     rax, [rbx]
0x1800151b9  lea     rdx, [rsp+190h+var_120]
0x1800151be  mov     rcx, rbx
0x1800151c1  mov     rax, [rax+18h]
0x1800151c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800151ca  mov     rsi, rax
0x1800151cd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800151d4  mov     ecx, 38h ; '8'; unsigned __int64
0x1800151d9  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800151de  mov     rdi, rax
0x1800151e1  test    rax, rax
0x1800151e4  jz      short loc_180015215
0x1800151e6  movaps  xmm1, xmmword ptr [rsp+190h+pclsid.Data1]
0x1800151eb  movups  xmm0, xmmword ptr [rsi]
0x1800151ee  movups  xmmword ptr [rax+8], xmm0
0x1800151f2  movups  xmmword ptr [rax+18h], xmm1
0x1800151f6  lea     rcx, [rax+28h]
0x1800151fa  mov     [rcx], rbx
0x1800151fd  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180015202  mov     [rdi], r14
0x180015205  mov     [rdi+30h], r12d
0x180015209  jmp     short loc_180015218
0x18001520b  mov     esi, 8007000Eh
0x180015210  jmp     loc_18001515B
0x180015215  mov     rdi, r12
0x180015218  test    rdi, rdi
0x18001521b  jz      short loc_18001522D
0x18001521d  mov     rax, [rdi]
0x180015220  mov     rcx, rdi
0x180015223  mov     rax, [rax+8]
0x180015227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001522c  nop
0x18001522d  test    rdi, rdi
0x180015230  jz      short loc_180015296
0x180015232  lea     r14, [r13+0D0h]
0x180015239  mov     rcx, r14; SRWLock
0x18001523c  call    cs:__imp_AcquireSRWLockExclusive
0x180015242  lea     rsi, [r13+0B0h]
0x180015249  mov     ebx, r12d
0x18001524c  mov     rdx, [rsi+8]
0x180015250  cmp     rdx, [rsi+18h]
0x180015254  jnz     short loc_180015267
0x180015256  inc     rdx
0x180015259  mov     rcx, rsi
0x18001525c  call    ?_EnsureCapacity@?$CTSimpleArray@V?$ComPtr@V?$CRefCountedObject@U_PluginInfo@CActivationBrokerManager@@@@@WRL@Microsoft@@$0PPPPPPPO@V?$CTPolicyLocalMem@V?$ComPtr@V?$CRefCountedObject@U_PluginInfo@CActivationBrokerManager@@@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardCompareHelper@V?$ComPtr@V?$CRefCountedObject@U_PluginInfo@CActivationBrokerManager@@@@@WRL@Microsoft@@@@V?$CSimpleArrayStandardMergeHelper@V?$ComPtr@V?$CRefCountedObject@U_PluginInfo@CActivationBrokerManager@@@@@WRL@Microsoft@@@@@@QEAAJ_K0@Z; CTSimpleArray<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>,4294967294,CTPolicyLocalMem<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>>,CSimpleArrayStandardCompareHelper<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>>,CSimpleArrayStandardMergeHelper<Microsoft::WRL::ComPtr<CRefCountedObject<CActivationBrokerManager::_PluginInfo>>>>::_EnsureCapacity(unsigned __int64,unsigned __int64)
0x180015261  mov     ebx, eax
0x180015263  test    eax, eax
0x180015265  js      short loc_180015286
0x180015267  inc     qword ptr [rsi+8]
0x18001526b  mov     rcx, [rsi+8]
0x18001526f  mov     rax, [rsi]
0x180015272  dec     rcx
0x180015275  lea     rcx, [rax+rcx*8]
0x180015279  test    rcx, rcx
0x18001527c  jz      short loc_180015286
0x18001527e  mov     [rcx], rdi
0x180015281  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180015286  test    r14, r14
0x180015289  jz      short loc_18001529B
0x18001528b  mov     rcx, r14; SRWLock
0x18001528e  call    cs:__imp_ReleaseSRWLockExclusive
0x180015294  jmp     short loc_18001529B
0x180015296  mov     ebx, 8007000Eh
0x18001529b  test    rdi, rdi
0x18001529e  jz      short loc_1800152B0
0x1800152a0  mov     rax, [rdi]
0x1800152a3  mov     rcx, rdi
0x1800152a6  mov     rax, [rax+10h]
0x1800152aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152af  nop
0x1800152b0  mov     rcx, qword ptr [rbp+90h+Buf1.Data1]
0x1800152b4  test    rcx, rcx
0x1800152b7  jz      short loc_1800152CA
0x1800152b9  mov     qword ptr [rbp+90h+Buf1.Data1], r12
0x1800152bd  mov     rax, [rcx]
0x1800152c0  mov     rax, [rax+10h]
0x1800152c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800152c9  nop
0x1800152ca  test    ebx, ebx
0x1800152cc  js      short loc_18001530C
0x1800152ce  test    cs:byte_1800D1F01, 8
0x1800152d5  jz      short loc_180015322
0x1800152d7  lea     rax, [rsp+190h+pclsid]
0x1800152dc  mov     [rbp+90h+var_100], rax
0x1800152e0  mov     [rbp+90h+var_F8], 10h
0x1800152e8  lea     rax, [rbp+90h+Buf1]
0x1800152ec  mov     [rsp+190h+phkResult], rax
0x1800152f1  mov     r9d, 2
0x1800152f7  lea     rdx, AM_CreatedActivationPlugin
0x1800152fe  lea     rcx, MICROSOFT_WINDOWS_APPMODEL_EXEC_PUBLISHER_Context
0x180015305  call    McGenEventWrite_EventWriteTransfer
0x18001530a  jmp     short loc_180015322
0x18001530c  test    cs:byte_1800D1F01, 4
0x180015313  jz      short loc_180015322
0x180015315  lea     r9, [rsp+190h+pclsid]
0x18001531a  mov     r8d, ebx
0x18001531d  call    McTemplateU0qj_EventWriteTransfer
0x180015322  lea     r14, ??_7?$CRefCountedObject@U_PluginInfo@CActivationBrokerManager@@@@6B@; const CRefCountedObject<CActivationBrokerManager::_PluginInfo>::`vftable'
0x180015329  mov     [rsp+190h+cchName], 27h ; '''
0x180015331  inc     r15d
0x180015334  mov     [rsp+190h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180015339  mov     [rsp+190h+lpcchClass], r12; lpcchClass
0x18001533e  mov     [rsp+190h+lpClass], r12; lpClass
0x180015343  mov     [rsp+190h+phkResult], r12; lpReserved
0x180015348  lea     r9, [rsp+190h+cchName]; lpcchName
0x18001534d  lea     r8, [rbp+90h+Name]; lpName
0x180015351  mov     edx, r15d; dwIndex
0x180015354  mov     rcx, [rsp+190h+hKey]; hKey
0x180015359  call    cs:__imp_RegEnumKeyExW
0x18001535f  mov     ebx, eax
0x180015361  test    eax, eax
0x180015363  jz      loc_180014FD1
0x180015369  cmp     ebx, 103h
0x18001536f  jz      short loc_180015398
0x180015371  test    ebx, ebx
0x180015373  jle     short loc_18001537E
0x180015375  movzx   ebx, bx
0x180015378  or      ebx, 80070000h
0x18001537e  test    cs:byte_1800D1F01, 4
0x180015385  jz      short loc_1800153A8
0x180015387  mov     r8d, ebx
0x18001538a  lea     rdx, AM_FailedToReadActivationPlugins
0x180015391  call    McTemplateU0q_EventWriteTransfer
0x180015396  jmp     short loc_1800153A8
0x180015398  mov     ebx, r12d
0x18001539b  jmp     short loc_1800153A8
0x18001539d  jle     short loc_1800153A8
0x18001539f  movzx   ebx, ax
0x1800153a2  or      ebx, 80070000h
0x1800153a8  mov     rcx, [rsp+190h+hKey]; hKey
0x1800153ad  test    rcx, rcx
0x1800153b0  jz      short loc_1800153B8
0x1800153b2  call    cs:__imp_RegCloseKey
0x1800153b8  mov     eax, ebx
0x1800153ba  mov     rcx, [rbp+90h+var_50]
0x1800153be  xor     rcx, rsp; StackCookie
0x1800153c1  call    __security_check_cookie
0x1800153c6  add     rsp, 158h
0x1800153cd  pop     r15
  ... truncated ...
```
