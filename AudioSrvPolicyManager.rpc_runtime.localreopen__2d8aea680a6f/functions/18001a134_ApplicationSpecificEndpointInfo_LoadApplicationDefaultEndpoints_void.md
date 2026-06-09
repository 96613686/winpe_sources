# ApplicationSpecificEndpointInfo::LoadApplicationDefaultEndpoints(void)

- ea: `0x18001a134`
- end: `0x18001a3f3`
- name: `?LoadApplicationDefaultEndpoints@ApplicationSpecificEndpointInfo@@AEAAJXZ`
- size: `703`
- prototype: `__int64 __fastcall(ApplicationSpecificEndpointInfo *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180019ed0`

## callees

- `0x18000a384`
- `0x18000b9c0`
- `0x18000e37c`
- `0x180012844`
- `0x180019a80`
- `0x18001a134`
- `0x18002b724`
- `0x180031960`
- `0x18004620c`
- `0x180046cf4`
- `0x1800473b0`
- `0x180047570`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a2ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a2f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a30c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a348`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a37c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a38c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a2ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a2f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a30c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a348`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a37c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a38c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a31b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a39b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a3e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a31b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a39b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001a3e9`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001a228`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18001a228`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001a1c5`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001a1c5`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall ApplicationSpecificEndpointInfo::LoadApplicationDefaultEndpoints(
        ApplicationSpecificEndpointInfo *this)
{
  int AppKey; // eax
  HKEY v3; // rbx
  WCHAR *v4; // rsi
  DWORD i; // r14d
  unsigned int v6; // eax
  LSTATUS Key; // eax
  unsigned int v8; // edi
  int v9; // eax
  void *v10; // rdi
  int updated; // eax
  unsigned int v12; // r15d
  int lpcSubKeys; // [rsp+20h] [rbp-89h]
  unsigned int lpcSubKeysa; // [rsp+20h] [rbp-89h]
  DWORD cbMaxValueNameLen; // [rsp+60h] [rbp-49h] BYREF
  DWORD cValues; // [rsp+64h] [rbp-45h] BYREF
  DWORD cchValueName; // [rsp+68h] [rbp-41h] BYREF
  enum __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001 v19; // [rsp+6Ch] [rbp-3Dh] BYREF
  unsigned int v20; // [rsp+70h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-31h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-29h] BYREF
  LPWSTR lpValueName; // [rsp+88h] [rbp-21h] BYREF
  _BYTE v24[32]; // [rsp+90h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  hKey = 0;
  AppKey = ApplicationSpecificEndpointInfo::GetAppKey(this, 0x20019u, 0, &hKey);
  v3 = hKey;
  if ( AppKey < 0
    || (cValues = 0,
        cbMaxValueNameLen = 0,
        RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0)) )
  {
LABEL_31:
    if ( v3 )
      RegCloseKey(v3);
    return 0;
  }
  wil::make_unique_cotaskmem_nothrow<unsigned short [0]>(&lpValueName, ++cbMaxValueNameLen);
  v4 = lpValueName;
  if ( lpValueName )
  {
    for ( i = 0; i < cValues; ++i )
    {
      cchValueName = cbMaxValueNameLen;
      v6 = RegEnumValueW(v3, i, v4, &cchValueName, 0, 0, 0, 0);
      if ( v6 )
      {
        v8 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x1B9,
               (unsigned int)"avcore\\audiocore\\server\\audiosrv\\applicationspecificendpointinfo\\applicationspecificendpointinfo.cpp",
               (const char *)v6,
               lpcSubKeysa);
LABEL_27:
        if ( v4 )
          CoTaskMemFree(v4);
        goto LABEL_35;
      }
      if ( cchValueName )
      {
        std::wstring::wstring(v24, v4);
        if ( std::wstring::find(v24) == -1 )
        {
          pv = 0;
          v20 = 0;
          v19 = eRender;
          Key = ApplicationSpecificEndpointInfo::ReadKey(v3, v4, (unsigned __int16 **)&pv);
          v8 = Key;
          if ( Key < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1CA,
              (unsigned int)"avcore\\audiocore\\server\\audiosrv\\applicationspecificendpointinfo\\applicationspecificendpointinfo.cpp",
              (const char *)(unsigned int)Key,
              lpcSubKeysa);
            if ( pv )
              CoTaskMemFree(pv);
            std::wstring::~wstring(v24);
            goto LABEL_27;
          }
          v9 = ApplicationSpecificEndpointInfo::ReadEndpointDataFromKey(
                 v4,
                 &v19,
                 (enum __MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001 *)&v20);
          v10 = pv;
          if ( v9 >= 0 )
          {
            updated = ApplicationSpecificEndpointInfo::UpdateState(this, v20, (unsigned int)v19, pv);
            v12 = updated;
            if ( updated < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1D4,
                (unsigned int)"avcore\\audiocore\\server\\audiosrv\\applicationspecificendpointinfo\\applicationspecificendpointinfo.cpp",
                (const char *)(unsigned int)updated,
                lpcSubKeysa);
              if ( v10 )
                CoTaskMemFree(v10);
              std::wstring::~wstring(v24);
              if ( v4 )
                CoTaskMemFree(v4);
              if ( v3 )
                RegCloseKey(v3);
              return v12;
            }
          }
          if ( v10 )
            CoTaskMemFree(v10);
        }
        std::wstring::~wstring(v24);
      }
    }
    if ( v4 )
      CoTaskMemFree(v4);
    goto LABEL_31;
  }
  v8 = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1A8,
    (unsigned int)"avcore\\audiocore\\server\\audiosrv\\applicationspecificendpointinfo\\applicationspecificendpointinfo.cpp",
    (const char *)0x8007000ELL,
    lpcSubKeys);
LABEL_35:
  if ( v3 )
    RegCloseKey(v3);
  return v8;
}

```

## disassembly

```asm
0x18001a134  push    rbp
0x18001a136  push    rbx
0x18001a137  push    rsi
0x18001a138  push    rdi
0x18001a139  push    r12
0x18001a13b  push    r13
0x18001a13d  push    r14
0x18001a13f  push    r15
0x18001a141  lea     rbp, [rsp-1Fh]
0x18001a146  sub     rsp, 0C8h
0x18001a14d  mov     rax, cs:__security_cookie
0x18001a154  xor     rax, rsp
0x18001a157  mov     [rbp+57h+var_50], rax
0x18001a15b  mov     r12, rcx
0x18001a15e  xor     r13d, r13d
0x18001a161  mov     [rbp+57h+hKey], r13
0x18001a165  lea     r9, [rbp+57h+hKey]; HKEY *
0x18001a169  xor     r8d, r8d; bool
0x18001a16c  mov     edx, 20019h; unsigned int
0x18001a171  call    ?GetAppKey@ApplicationSpecificEndpointInfo@@AEAAJK_NPEAPEAUHKEY__@@@Z; ApplicationSpecificEndpointInfo::GetAppKey(ulong,bool,HKEY__ * *)
0x18001a176  mov     rbx, [rbp+57h+hKey]
0x18001a17a  test    eax, eax
0x18001a17c  js      loc_18001A393
0x18001a182  mov     [rbp+57h+cValues], r13d
0x18001a186  mov     [rbp+57h+cbMaxValueNameLen], r13d
0x18001a18a  mov     [rsp+100h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18001a18f  mov     [rsp+100h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18001a194  mov     [rsp+100h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x18001a199  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x18001a19d  mov     [rsp+100h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x18001a1a2  lea     rax, [rbp+57h+cValues]
0x18001a1a6  mov     [rsp+100h+lpcValues], rax; lpcValues
0x18001a1ab  mov     [rsp+100h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18001a1b0  mov     [rsp+100h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x18001a1b5  mov     [rsp+100h+lpcSubKeys], r13; int
0x18001a1ba  xor     r9d, r9d; lpReserved
0x18001a1bd  xor     r8d, r8d; lpcchClass
0x18001a1c0  xor     edx, edx; lpClass
0x18001a1c2  mov     rcx, rbx; hKey
0x18001a1c5  call    cs:__imp_RegQueryInfoKeyW
0x18001a1cb  test    eax, eax
0x18001a1cd  jnz     loc_18001A393
0x18001a1d3  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x18001a1d6  inc     eax
0x18001a1d8  mov     [rbp+57h+cbMaxValueNameLen], eax
0x18001a1db  mov     edx, eax
0x18001a1dd  lea     rcx, [rbp+57h+lpValueName]
0x18001a1e1  call    ??$make_unique_cotaskmem_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_cotaskmem_nothrow<ushort [0]>(unsigned __int64)
0x18001a1e6  nop
0x18001a1e7  mov     rsi, [rbp+57h+lpValueName]
0x18001a1eb  test    rsi, rsi
0x18001a1ee  jz      loc_18001A3C3
0x18001a1f4  mov     r14d, r13d
0x18001a1f7  cmp     r14d, [rbp+57h+cValues]
0x18001a1fb  jnb     loc_18001A384
0x18001a201  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x18001a204  mov     [rbp+57h+cchValueName], eax
0x18001a207  mov     [rsp+100h+lpcValues], r13; lpcbData
0x18001a20c  mov     [rsp+100h+lpcbMaxClassLen], r13; lpData
0x18001a211  mov     [rsp+100h+lpcbMaxSubKeyLen], r13; lpType
0x18001a216  mov     [rsp+100h+lpcSubKeys], r13; unsigned int
0x18001a21b  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x18001a21f  mov     r8, rsi; lpValueName
0x18001a222  mov     edx, r14d; dwIndex
0x18001a225  mov     rcx, rbx; hKey
0x18001a228  call    cs:__imp_RegEnumValueW
0x18001a22e  test    eax, eax
0x18001a230  jnz     loc_18001A35A
0x18001a236  cmp     [rbp+57h+cchValueName], r13d
0x18001a23a  jz      loc_18001A2CA
0x18001a240  mov     rdx, rsi
0x18001a243  lea     rcx, [rbp+57h+var_70]
0x18001a247  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001a24c  nop
0x18001a24d  lea     rcx, [rbp+57h+var_70]
0x18001a251  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KQEBG_K@Z; std::wstring::find(ushort const * const,unsigned __int64)
0x18001a256  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001a25a  jnz     short loc_18001A2C1
0x18001a25c  mov     [rbp+57h+pv], r13
0x18001a260  mov     [rbp+57h+var_90], r13d
0x18001a264  mov     [rbp+57h+var_94], r13d
0x18001a268  lea     r8, [rbp+57h+pv]; unsigned __int16 **
0x18001a26c  mov     rdx, rsi; lpValue
0x18001a26f  mov     rcx, rbx; hkey
0x18001a272  call    ?ReadKey@ApplicationSpecificEndpointInfo@@CAJPEAUHKEY__@@PEBGPEAPEAG@Z; ApplicationSpecificEndpointInfo::ReadKey(HKEY__ *,ushort const *,ushort * *)
0x18001a277  mov     edi, eax
0x18001a279  test    eax, eax
0x18001a27b  js      loc_18001A326
0x18001a281  lea     r8, [rbp+57h+var_90]; enum __MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001 *
0x18001a285  lea     rdx, [rbp+57h+var_94]; enum __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001 *
0x18001a289  mov     rcx, rsi; unsigned __int16 *
0x18001a28c  call    ?ReadEndpointDataFromKey@ApplicationSpecificEndpointInfo@@CAJPEBGPEAW4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@PEAW4__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001@@@Z; ApplicationSpecificEndpointInfo::ReadEndpointDataFromKey(ushort const *,__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001 *,__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001 *)
0x18001a291  mov     rdi, [rbp+57h+pv]
0x18001a295  test    eax, eax
0x18001a297  js      short loc_18001A2B2
0x18001a299  mov     r9, rdi
0x18001a29c  mov     r8d, [rbp+57h+var_94]
0x18001a2a0  mov     edx, [rbp+57h+var_90]
0x18001a2a3  mov     rcx, r12
0x18001a2a6  call    ?UpdateState@ApplicationSpecificEndpointInfo@@AEAAJW4__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001@@W4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@PEBG@Z; ApplicationSpecificEndpointInfo::UpdateState(__MIDL___MIDL_itf_mmdeviceapip_0000_0000_0001,__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001,ushort const *)
0x18001a2ab  mov     r15d, eax
0x18001a2ae  test    eax, eax
0x18001a2b0  js      short loc_18001A2D2
0x18001a2b2  test    rdi, rdi
0x18001a2b5  jz      short loc_18001A2C1
0x18001a2b7  mov     rcx, rdi; pv
0x18001a2ba  call    cs:__imp_CoTaskMemFree
0x18001a2c0  nop
0x18001a2c1  lea     rcx, [rbp+57h+var_70]
0x18001a2c5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001a2ca  inc     r14d
0x18001a2cd  jmp     loc_18001A1F7
0x18001a2d2  mov     rcx, [rbp+5Fh]; this
0x18001a2d6  mov     r9d, r15d; char *
0x18001a2d9  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\ap"...
0x18001a2e0  mov     edx, 1D4h; void *
0x18001a2e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a2ea  nop
0x18001a2eb  test    rdi, rdi
0x18001a2ee  jz      short loc_18001A2FA
0x18001a2f0  mov     rcx, rdi; pv
0x18001a2f3  call    cs:__imp_CoTaskMemFree
0x18001a2f9  nop
0x18001a2fa  lea     rcx, [rbp+57h+var_70]
0x18001a2fe  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001a303  nop
0x18001a304  test    rsi, rsi
0x18001a307  jz      short loc_18001A313
0x18001a309  mov     rcx, rsi; pv
0x18001a30c  call    cs:__imp_CoTaskMemFree
0x18001a312  nop
0x18001a313  test    rbx, rbx
0x18001a316  jz      short loc_18001A321
0x18001a318  mov     rcx, rbx; hKey
0x18001a31b  call    cs:__imp_RegCloseKey
0x18001a321  mov     eax, r15d
0x18001a324  jmp     short loc_18001A3A3
0x18001a326  mov     rcx, [rbp+5Fh]; this
0x18001a32a  mov     r9d, edi; char *
0x18001a32d  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\ap"...
0x18001a334  mov     edx, 1CAh; void *
0x18001a339  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a33e  nop
0x18001a33f  mov     rcx, [rbp+57h+pv]; pv
0x18001a343  test    rcx, rcx
0x18001a346  jz      short loc_18001A34F
0x18001a348  call    cs:__imp_CoTaskMemFree
0x18001a34e  nop
0x18001a34f  lea     rcx, [rbp+57h+var_70]
0x18001a353  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001a358  jmp     short loc_18001A374
0x18001a35a  mov     rcx, [rbp+5Fh]; this
0x18001a35e  mov     r9d, eax; char *
0x18001a361  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\ap"...
0x18001a368  mov     edx, 1B9h; void *
0x18001a36d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001a372  mov     edi, eax
0x18001a374  test    rsi, rsi
0x18001a377  jz      short loc_18001A3E1
0x18001a379  mov     rcx, rsi; pv
0x18001a37c  call    cs:__imp_CoTaskMemFree
0x18001a382  jmp     short loc_18001A3E1
0x18001a384  test    rsi, rsi
0x18001a387  jz      short loc_18001A393
0x18001a389  mov     rcx, rsi; pv
0x18001a38c  call    cs:__imp_CoTaskMemFree
0x18001a392  nop
0x18001a393  test    rbx, rbx
0x18001a396  jz      short loc_18001A3A1
0x18001a398  mov     rcx, rbx; hKey
0x18001a39b  call    cs:__imp_RegCloseKey
0x18001a3a1  xor     eax, eax
0x18001a3a3  mov     rcx, [rbp+57h+var_50]
0x18001a3a7  xor     rcx, rsp; StackCookie
0x18001a3aa  call    __security_check_cookie
0x18001a3af  add     rsp, 0C8h
0x18001a3b6  pop     r15
0x18001a3b8  pop     r14
0x18001a3ba  pop     r13
0x18001a3bc  pop     r12
0x18001a3be  pop     rdi
0x18001a3bf  pop     rsi
0x18001a3c0  pop     rbx
0x18001a3c1  pop     rbp
0x18001a3c2  retn
0x18001a3c3  mov     rcx, [rbp+5Fh]; this
0x18001a3c7  mov     edi, 8007000Eh
0x18001a3cc  mov     r9d, edi; char *
0x18001a3cf  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audiosrv\\ap"...
0x18001a3d6  mov     edx, 1A8h; void *
0x18001a3db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a3e0  nop
0x18001a3e1  test    rbx, rbx
0x18001a3e4  jz      short loc_18001A3EF
0x18001a3e6  mov     rcx, rbx; hKey
0x18001a3e9  call    cs:__imp_RegCloseKey
0x18001a3ef  mov     eax, edi
0x18001a3f1  jmp     short loc_18001A3A3
```
