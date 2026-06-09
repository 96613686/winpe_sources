# DeviceCastle::Library::DeviceCastleInternal::GetAllCryptogramStorageKeyCharacteristics(DeviceCastle::Library::CallerIdentity &,_GetAllCryptogramStorageKeyCharacteristicsResult * *)

- ea: `0x18004affc`
- end: `0x18004b2a0`
- name: `?GetAllCryptogramStorageKeyCharacteristics@DeviceCastleInternal@Library@DeviceCastle@@QEAAJAEAVCallerIdentity@23@PEAPEAU_GetAllCryptogramStorageKeyCharacteristicsResult@@@Z`
- size: `676`
- prototype: `__int64 __fastcall(DeviceCastle::Library::DeviceCastleInternal *__hidden this, struct DeviceCastle::Library::CallerIdentity *, struct _GetAllCryptogramStorageKeyCharacteristicsResult **)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180042b70`

## callees

- `0x180005858`
- `0x1800106ac`
- `0x1800450e8`
- `0x180048ee4`
- `0x1800493a4`
- `0x180049458`
- `0x180049908`
- `0x18004affc`
- `0x18004d238`
- `0x18004d2cc`
- `0x18004db3c`
- `0x18004dc80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b13e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b215`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b229`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b252`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b266`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b13e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b215`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b229`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b252`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004b266`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall DeviceCastle::Library::DeviceCastleInternal::GetAllCryptogramStorageKeyCharacteristics(
        DeviceCastle::Library::DeviceCastleInternal *this,
        struct DeviceCastle::Library::CallerIdentity *a2,
        struct _GetAllCryptogramStorageKeyCharacteristicsResult **a3)
{
  int v6; // ebx
  __int64 v7; // r13
  __int64 v8; // r14
  unsigned __int64 v9; // rbx
  unsigned __int64 i; // rdi
  const unsigned __int16 *v11; // rax
  signed __int64 v12; // r12
  _QWORD *cotaskmem_string; // rax
  __int64 v14; // rdx
  LPVOID v15; // rcx
  struct _GetAllCryptogramStorageKeyCharacteristicsResult *v16; // rax
  unsigned __int64 v17; // r8
  void *v18; // rcx
  void *v19; // rcx
  void *v20; // rcx
  void *v21; // rcx
  LPVOID pv; // [rsp+20h] [rbp-40h] BYREF
  void *v24[2]; // [rsp+28h] [rbp-38h] BYREF
  void *v25; // [rsp+38h] [rbp-28h]
  __int128 v26; // [rsp+40h] [rbp-20h] BYREF
  __int64 v27; // [rsp+50h] [rbp-10h]
  LPVOID v28; // [rsp+B0h] [rbp+50h] BYREF
  LPVOID v29; // [rsp+B8h] [rbp+58h] BYREF

  v26 = 0;
  v27 = 0;
  if ( a3 )
  {
    *a3 = 0;
    v6 = DeviceCastle::Library::DeviceCastleInternal::VerifyAllStorageKeysStillExist(this, a2);
    if ( v6 >= 0 )
    {
      if ( (unsigned __int8)DeviceCastle::Library::Internal::DeviceCastleDatabase::GetAllKeys(
                              (char *)this + 176,
                              a2,
                              &v26) )
      {
        *(_OWORD *)v24 = 0;
        v25 = 0;
        wil::make_unique_cotaskmem<_GetAllCryptogramMaterialPackageCharacteristicsResult,>(&v29);
        v7 = *((_QWORD *)&v26 + 1);
        v8 = v26;
        v9 = (__int64)(*((_QWORD *)&v26 + 1) - v26) >> 4;
        wil::make_unique_cotaskmem<_CryptogramStorageKeyCharacteristics [0]>(&v28, v9);
        if ( v9 > 0xFFFFFFFF )
        {
          *(_DWORD *)v29 = -1;
          v6 = -2147024362;
          v20 = v28;
          v28 = 0;
          if ( v20 )
            CoTaskMemFree(v20);
          v21 = v29;
          v29 = 0;
          if ( v21 )
            CoTaskMemFree(v21);
          std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(v24);
        }
        else
        {
          *(_DWORD *)v29 = v9;
          std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::reserve(
            v24,
            (v7 - v8) >> 4);
          for ( i = 0; i < (v7 - v8) >> 4; ++i )
          {
            v11 = (const unsigned __int16 *)DeviceCastle::Library::UserSafeName(*(_QWORD *)(v8 + 16 * i) + 16LL, a2);
            if ( v11 )
            {
              v12 = ((char *)v24[1] - (char *)v24[0]) >> 3;
              cotaskmem_string = (_QWORD *)wil::make_cotaskmem_string((wil *)&pv, v11, 0xFFFFFFFFFFFFFFFFuLL);
              if ( v24[1] == v25 )
              {
                std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                  v24,
                  v24[1],
                  cotaskmem_string);
              }
              else
              {
                *(_QWORD *)v24[1] = *cotaskmem_string;
                *cotaskmem_string = 0;
                v24[1] = (char *)v24[1] + 8;
              }
              if ( pv )
                CoTaskMemFree(pv);
              v14 = 24 * i;
              *((_QWORD *)v28 + 3 * i) = *((_QWORD *)v24[0] + v12);
            }
            else
            {
              v14 = 24 * i;
              *((_QWORD *)v28 + 3 * i) = 0;
            }
            *(_QWORD *)((char *)v28 + v14 + 8) = *(_QWORD *)(*(_QWORD *)(v8 + 16 * i) + 184LL);
            *(_DWORD *)((char *)v28 + v14 + 16) = 1;
            *(_DWORD *)((char *)v28 + v14 + 20) = *(_DWORD *)(*(_QWORD *)(v8 + 16 * i) + 180LL);
          }
          v15 = v28;
          v28 = 0;
          *((_QWORD *)v29 + 1) = v15;
          v16 = (struct _GetAllCryptogramStorageKeyCharacteristicsResult *)v29;
          v29 = 0;
          *a3 = v16;
          v17 = (unsigned __int64)((char *)v24[1] - (char *)v24[0] + 7) >> 3;
          if ( v24[0] > v24[1] )
            v17 = 0;
          if ( v17 )
            memset_0(v24[0], 0, 8 * v17);
          v18 = v28;
          v28 = 0;
          if ( v18 )
            CoTaskMemFree(v18);
          v19 = v29;
          v29 = 0;
          if ( v19 )
            CoTaskMemFree(v19);
          std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(v24);
          v6 = 0;
        }
      }
      else
      {
        v6 = -2134834658;
      }
    }
  }
  else
  {
    v6 = -2147467261;
  }
  std::vector<std::shared_ptr<DeviceCastle::Library::Internal::CryptogramMaterialProtectionKeyInformation>>::~vector<std::shared_ptr<DeviceCastle::Library::Internal::CryptogramMaterialProtectionKeyInformation>>(&v26);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18004affc  mov     [rsp-38h+arg_0], rbx
0x18004b001  push    rbp
0x18004b002  push    rsi
0x18004b003  push    rdi
0x18004b004  push    r12
0x18004b006  push    r13
0x18004b008  push    r14
0x18004b00a  push    r15
0x18004b00c  mov     rbp, rsp
0x18004b00f  sub     rsp, 60h
0x18004b013  mov     r15, r8
0x18004b016  mov     rsi, rdx
0x18004b019  mov     rdi, rcx
0x18004b01c  xor     r12d, r12d
0x18004b01f  xorps   xmm0, xmm0
0x18004b022  movdqu  [rbp+var_20], xmm0
0x18004b027  mov     [rbp+var_10], r12
0x18004b02b  test    r8, r8
0x18004b02e  jnz     short loc_18004B03A
0x18004b030  mov     ebx, 80004003h
0x18004b035  jmp     loc_18004B27D
0x18004b03a  mov     [r8], r12
0x18004b03d  call    ?VerifyAllStorageKeysStillExist@DeviceCastleInternal@Library@DeviceCastle@@AEAAJAEAVCallerIdentity@23@@Z; DeviceCastle::Library::DeviceCastleInternal::VerifyAllStorageKeysStillExist(DeviceCastle::Library::CallerIdentity &)
0x18004b042  mov     ebx, eax
0x18004b044  test    eax, eax
0x18004b046  js      loc_18004B27D
0x18004b04c  lea     rcx, [rdi+0B0h]
0x18004b053  lea     r8, [rbp+var_20]
0x18004b057  mov     rdx, rsi
0x18004b05a  call    ?GetAllKeys@DeviceCastleDatabase@Internal@Library@DeviceCastle@@QEAA_NAEAVCallerIdentity@34@AEAV?$vector@V?$shared_ptr@VCryptogramMaterialProtectionKeyInformation@Internal@Library@DeviceCastle@@@std@@V?$allocator@V?$shared_ptr@VCryptogramMaterialProtectionKeyInformation@Internal@Library@DeviceCastle@@@std@@@2@@std@@@Z; DeviceCastle::Library::Internal::DeviceCastleDatabase::GetAllKeys(DeviceCastle::Library::CallerIdentity &,std::vector<std::shared_ptr<DeviceCastle::Library::Internal::CryptogramMaterialProtectionKeyInformation>> &)
0x18004b05f  test    al, al
0x18004b061  jz      loc_18004B278
0x18004b067  xorps   xmm0, xmm0
0x18004b06a  movdqu  xmmword ptr [rbp+var_38], xmm0
0x18004b06f  mov     [rbp+var_28], r12
0x18004b073  lea     rcx, [rbp+arg_18]
0x18004b077  call    ??$make_unique_cotaskmem@U_GetAllCryptogramMaterialPackageCharacteristicsResult@@$$V@wil@@YA?AV?$unique_ptr@U_GetAllCryptogramMaterialPackageCharacteristicsResult@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@XZ; wil::make_unique_cotaskmem<_GetAllCryptogramMaterialPackageCharacteristicsResult,>(void)
0x18004b07c  nop
0x18004b07d  mov     r13, qword ptr [rbp+var_20+8]
0x18004b081  mov     rbx, r13
0x18004b084  mov     r14, qword ptr [rbp+var_20]
0x18004b088  sub     rbx, r14
0x18004b08b  sar     rbx, 4
0x18004b08f  mov     rdx, rbx
0x18004b092  lea     rcx, [rbp+arg_10]
0x18004b096  call    ??$make_unique_cotaskmem@$$BY0A@U_CryptogramStorageKeyCharacteristics@@@wil@@YA?AV?$unique_ptr@$$BY0A@U_CryptogramStorageKeyCharacteristics@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem<_CryptogramStorageKeyCharacteristics [0]>(unsigned __int64)
0x18004b09b  nop
0x18004b09c  mov     rax, [rbp+arg_18]
0x18004b0a0  mov     ecx, 0FFFFFFFFh
0x18004b0a5  cmp     rbx, rcx
0x18004b0a8  ja      loc_18004B23E
0x18004b0ae  mov     [rax], ebx
0x18004b0b0  mov     rbx, r13
0x18004b0b3  sub     rbx, r14
0x18004b0b6  sar     rbx, 4
0x18004b0ba  mov     rdx, rbx
0x18004b0bd  lea     rcx, [rbp+var_38]
0x18004b0c1  call    ?reserve@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAAX_K@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::reserve(unsigned __int64)
0x18004b0c6  mov     rdi, r12
0x18004b0c9  test    rbx, rbx
0x18004b0cc  jz      loc_18004B1C1
0x18004b0d2  mov     rbx, rdi
0x18004b0d5  add     rbx, rbx
0x18004b0d8  mov     rcx, [r14+rbx*8]
0x18004b0dc  add     rcx, 10h
0x18004b0e0  mov     rdx, rsi
0x18004b0e3  call    DeviceCastle__Library__UserSafeName
0x18004b0e8  test    rax, rax
0x18004b0eb  jz      short loc_18004B165
0x18004b0ed  mov     r12, [rbp+var_38+8]
0x18004b0f1  sub     r12, [rbp+var_38]
0x18004b0f5  sar     r12, 3
0x18004b0f9  or      r8, 0FFFFFFFFFFFFFFFFh; unsigned __int64
0x18004b0fd  mov     rdx, rax; unsigned __int16 *
0x18004b100  lea     rcx, [rbp+pv]; this
0x18004b104  call    ?make_cotaskmem_string@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string(ushort const *,unsigned __int64)
0x18004b109  nop
0x18004b10a  mov     rdx, [rbp+var_38+8]
0x18004b10e  cmp     rdx, [rbp+var_28]
0x18004b112  jz      short loc_18004B128
0x18004b114  mov     rcx, [rax]
0x18004b117  mov     [rdx], rcx
0x18004b11a  mov     qword ptr [rax], 0
0x18004b121  add     [rbp+var_38+8], 8
0x18004b126  jmp     short loc_18004B135
0x18004b128  mov     r8, rax
0x18004b12b  lea     rcx, [rbp+var_38]
0x18004b12f  call    ??$_Emplace_reallocate@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAAPEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::_Emplace_reallocate<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18004b134  nop
0x18004b135  mov     rcx, [rbp+pv]; pv
0x18004b139  test    rcx, rcx
0x18004b13c  jz      short loc_18004B144
0x18004b13e  call    cs:__imp_CoTaskMemFree
0x18004b144  lea     rax, [rdi+rdi*2]
0x18004b148  lea     rdx, ds:0[rax*8]
0x18004b150  mov     rax, [rbp+var_38]
0x18004b154  mov     rcx, [rax+r12*8]
0x18004b158  mov     rax, [rbp+arg_10]
0x18004b15c  mov     [rdx+rax], rcx
0x18004b160  xor     r12d, r12d
0x18004b163  jmp     short loc_18004B179
0x18004b165  lea     rax, [rdi+rdi*2]
0x18004b169  lea     rdx, ds:0[rax*8]
0x18004b171  mov     rax, [rbp+arg_10]
0x18004b175  mov     [rdx+rax], r12
0x18004b179  mov     rax, [r14+rbx*8]
0x18004b17d  mov     rcx, [rax+0B8h]
0x18004b184  mov     rax, [rbp+arg_10]
0x18004b188  mov     [rdx+rax+8], rcx
0x18004b18d  mov     rax, [rbp+arg_10]
0x18004b191  mov     dword ptr [rdx+rax+10h], 1
0x18004b199  mov     rax, [r14+rbx*8]
0x18004b19d  mov     ecx, [rax+0B4h]
0x18004b1a3  mov     rax, [rbp+arg_10]
0x18004b1a7  mov     [rdx+rax+14h], ecx
0x18004b1ab  inc     rdi
0x18004b1ae  mov     rax, r13
0x18004b1b1  sub     rax, r14
0x18004b1b4  sar     rax, 4
0x18004b1b8  cmp     rdi, rax
0x18004b1bb  jb      loc_18004B0D2
0x18004b1c1  mov     rcx, [rbp+arg_10]
0x18004b1c5  mov     [rbp+arg_10], r12
0x18004b1c9  mov     rax, [rbp+arg_18]
0x18004b1cd  mov     [rax+8], rcx
0x18004b1d1  mov     rax, [rbp+arg_18]
0x18004b1d5  mov     [rbp+arg_18], r12
0x18004b1d9  mov     [r15], rax
0x18004b1dc  mov     rcx, [rbp+var_38]; void *
0x18004b1e0  mov     r8, [rbp+var_38+8]
0x18004b1e4  sub     r8, rcx
0x18004b1e7  add     r8, 7
0x18004b1eb  shr     r8, 3
0x18004b1ef  cmp     rcx, [rbp+var_38+8]
0x18004b1f3  cmova   r8, r12
0x18004b1f7  test    r8, r8
0x18004b1fa  jz      short loc_18004B208
0x18004b1fc  shl     r8, 3; Size
0x18004b200  xor     edx, edx; Val
0x18004b202  call    memset_0
0x18004b207  nop
0x18004b208  mov     rcx, [rbp+arg_10]; pv
0x18004b20c  mov     [rbp+arg_10], r12
0x18004b210  test    rcx, rcx
0x18004b213  jz      short loc_18004B21C
0x18004b215  call    cs:__imp_CoTaskMemFree
0x18004b21b  nop
0x18004b21c  mov     rcx, [rbp+arg_18]; pv
0x18004b220  mov     [rbp+arg_18], r12
0x18004b224  test    rcx, rcx
0x18004b227  jz      short loc_18004B230
0x18004b229  call    cs:__imp_CoTaskMemFree
0x18004b22f  nop
0x18004b230  lea     rcx, [rbp+var_38]
0x18004b234  call    ??1?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18004b239  mov     ebx, r12d
0x18004b23c  jmp     short loc_18004B27D
0x18004b23e  mov     [rax], ecx
0x18004b240  mov     ebx, 80070216h
0x18004b245  mov     rcx, [rbp+arg_10]; pv
0x18004b249  mov     [rbp+arg_10], r12
0x18004b24d  test    rcx, rcx
0x18004b250  jz      short loc_18004B259
0x18004b252  call    cs:__imp_CoTaskMemFree
0x18004b258  nop
0x18004b259  mov     rcx, [rbp+arg_18]; pv
0x18004b25d  mov     [rbp+arg_18], r12
0x18004b261  test    rcx, rcx
0x18004b264  jz      short loc_18004B26D
0x18004b266  call    cs:__imp_CoTaskMemFree
0x18004b26c  nop
0x18004b26d  lea     rcx, [rbp+var_38]
0x18004b271  call    ??1?$vector@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~vector<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18004b276  jmp     short loc_18004B27D
0x18004b278  mov     ebx, 80C1021Eh
0x18004b27d  lea     rcx, [rbp+var_20]
0x18004b281  call    ??1?$vector@V?$shared_ptr@VCryptogramMaterialProtectionKeyInformation@Internal@Library@DeviceCastle@@@std@@V?$allocator@V?$shared_ptr@VCryptogramMaterialProtectionKeyInformation@Internal@Library@DeviceCastle@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<DeviceCastle::Library::Internal::CryptogramMaterialProtectionKeyInformation>>::~vector<std::shared_ptr<DeviceCastle::Library::Internal::CryptogramMaterialProtectionKeyInformation>>(void)
0x18004b286  mov     eax, ebx
0x18004b288  mov     rbx, [rsp+60h+arg_0]
0x18004b290  add     rsp, 60h
0x18004b294  pop     r15
0x18004b296  pop     r14
0x18004b298  pop     r13
0x18004b29a  pop     r12
0x18004b29c  pop     rdi
0x18004b29d  pop     rsi
0x18004b29e  pop     rbp
0x18004b29f  retn
```
