# BthLELib_SMPResolvePrivateAddressAtDispatch

- ea: `0x14015f424`
- end: `0x14015f7b5`
- name: `BthLELib_SMPResolvePrivateAddressAtDispatch`
- size: `913`
- prototype: `__int64 __fastcall(BCRYPT_ALG_HANDLE hAlgorithm)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140061900`
- `0x140067bfc`
- `0x14007cc90`

## callees

- `0x14015f1b0`
- `0x14015f298`
- `0x14015f308`
- `0x14015f3a4`
- `0x14015f424`
- `0x14015fa50`
- `0x140161a00`
- `0x140165540`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14015f756`
- `ntoskrnl!RtlCompareMemory` at `0x14015f756`
- `ksecdd!BCryptGetProperty` at `0x14015f485`
- `ksecdd!BCryptGetProperty` at `0x14015f485`
- `ksecdd!BCryptEncrypt` at `0x14015f6ef`
- `ksecdd!BCryptEncrypt` at `0x14015f6ef`
- `ksecdd!BCryptImportKey` at `0x14015f613`
- `ksecdd!BCryptImportKey` at `0x14015f613`

## pseudocode

```c
__int64 __fastcall BthLELib_SMPResolvePrivateAddressAtDispatch(
        BCRYPT_ALG_HANDLE hAlgorithm,
        _OWORD *a2,
        __int64 a3,
        bool *a4)
{
  int v8; // edx
  __int64 v9; // rcx
  NTSTATUS Property; // ebx
  int v11; // r8d
  unsigned int v12; // ebx
  unsigned __int8 *Pool; // rax
  int v14; // edx
  __int64 v15; // rcx
  int v16; // r8d
  UCHAR *v17; // rbx
  unsigned __int8 *v18; // rax
  int v19; // edx
  int v20; // r8d
  PUCHAR pbInput; // rcx
  int v22; // edx
  int v23; // r8d
  int v24; // r9d
  unsigned int v25; // edx
  __int64 v26; // rcx
  _BYTE Source2[4]; // [rsp+50h] [rbp-49h] BYREF
  _BYTE Source1[4]; // [rsp+54h] [rbp-45h] BYREF
  ULONG pcbResult; // [rsp+58h] [rbp-41h] BYREF
  __int16 v31; // [rsp+5Ch] [rbp-3Dh]
  UCHAR pbOutput[4]; // [rsp+60h] [rbp-39h] BYREF
  BCRYPT_KEY_HANDLE hKey; // [rsp+68h] [rbp-31h] BYREF
  PUCHAR pbKeyObject[2]; // [rsp+70h] [rbp-29h] BYREF
  PUCHAR v35[2]; // [rsp+80h] [rbp-19h] BYREF
  BCRYPT_KEY_HANDLE *p_hKey; // [rsp+90h] [rbp-9h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+98h] [rbp-1h] BYREF
  char v38; // [rsp+A0h] [rbp+7h]
  int v39; // [rsp+A8h] [rbp+Fh]
  __int16 v40; // [rsp+ACh] [rbp+13h]
  UCHAR v41[16]; // [rsp+B0h] [rbp+17h] BYREF

  *(_DWORD *)pbOutput = 0;
  pcbResult = 0;
  Property = BCryptGetProperty(hAlgorithm, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
  if ( Property >= 0 )
  {
    v12 = *(_DWORD *)pbOutput;
    pbKeyObject[0] = 0;
    pbKeyObject[1] = 0;
    Pool = (unsigned __int8 *)BthLELibAllocatePoolEx(v9, *(unsigned int *)pbOutput);
    unique_bthlelib_secure_pool::reset((unique_bthlelib_secure_pool *)pbKeyObject, Pool, v12);
    v17 = pbKeyObject[0];
    if ( !pbKeyObject[0] )
    {
      Property = -1073741670;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_sd(
          WPP_GLOBAL_Control->DeviceExtension,
          v14,
          v16,
          30,
          (__int64)WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids);
      goto LABEL_22;
    }
    v35[0] = 0;
    v35[1] = 0;
    v18 = (unsigned __int8 *)BthLELibAllocatePoolEx(v15, 28);
    unique_bthlelib_secure_pool::reset((unique_bthlelib_secure_pool *)v35, v18, 0x1Cu);
    pbInput = v35[0];
    if ( !v35[0] )
    {
      Property = -1073741670;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_sd(
          WPP_GLOBAL_Control->DeviceExtension,
          v19,
          v20,
          31,
          (__int64)WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids);
      goto LABEL_21;
    }
    *(_DWORD *)v35[0] = 1296188491;
    *((_DWORD *)pbInput + 1) = 1;
    *((_DWORD *)pbInput + 2) = 16;
    *(_OWORD *)(pbInput + 12) = *a2;
    p_hKey = &hKey;
    hKey = 0;
    phKey = 0;
    v38 = 1;
    Property = BCryptImportKey(hAlgorithm, 0, L"KeyDataBlob", &phKey, v17, *(ULONG *)pbOutput, pbInput, 0x1Cu, 0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&p_hKey);
    if ( Property >= 0 )
    {
      pcbResult = a3;
      v25 = 0;
      v31 = WORD2(a3);
      v39 = 0;
      v40 = 0;
      do
      {
        v26 = (int)v25++;
        *((_BYTE *)&v39 + v26) = *((_BYTE *)&pcbResult + v26);
      }
      while ( v25 < 6 );
      *(_OWORD *)v41 = 0;
      v41[13] = HIBYTE(v40);
      v41[14] = v40;
      v41[15] = HIBYTE(v39);
      pcbResult = 0;
      Property = BCryptEncrypt(hKey, v41, 0x10u, 0, 0, 0, v41, 0x10u, &pcbResult, 0);
      if ( Property >= 0 )
      {
        Source2[0] = v41[13];
        Source2[1] = v41[14];
        Source2[2] = v41[15];
        Source1[0] = BYTE2(v39);
        Source1[1] = BYTE1(v39);
        Source1[2] = v39;
        *a4 = RtlCompareMemory(Source1, Source2, 3u) == 3;
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hKey);
        Property = 0;
        goto LABEL_21;
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v24 = 33;
        goto LABEL_13;
      }
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v24 = 32;
LABEL_13:
      WPP_RECORDER_SF_sd(
        WPP_GLOBAL_Control->DeviceExtension,
        v22,
        v23,
        v24,
        (__int64)WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids);
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hKey);
LABEL_21:
    unique_bthlelib_secure_pool::~unique_bthlelib_secure_pool((unique_bthlelib_secure_pool *)v35);
LABEL_22:
    unique_bthlelib_secure_pool::~unique_bthlelib_secure_pool((unique_bthlelib_secure_pool *)pbKeyObject);
    return (unsigned int)Property;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_sd(
      WPP_GLOBAL_Control->DeviceExtension,
      v8,
      v11,
      29,
      (__int64)WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids);
  return (unsigned int)Property;
}

```

## disassembly

```asm
0x14015f424  mov     [rsp-8+arg_8], rbx
0x14015f429  mov     [rsp-8+arg_10], rsi
0x14015f42e  push    rbp
0x14015f42f  push    rdi
0x14015f430  push    r12
0x14015f432  push    r14
0x14015f434  push    r15
0x14015f436  lea     rbp, [rsp-37h]
0x14015f43b  sub     rsp, 0D0h
0x14015f442  mov     rax, cs:__security_cookie
0x14015f449  xor     rax, rsp
0x14015f44c  mov     [rbp+57h+var_30], rax
0x14015f450  xor     r12d, r12d
0x14015f453  lea     rax, [rbp+57h+var_98]
0x14015f457  mov     r15, r9
0x14015f45a  mov     [rsp+0F0h+dwFlags], r12d; dwFlags
0x14015f45f  mov     rdi, r8
0x14015f462  mov     dword ptr [rbp+57h+pbOutput], r12d
0x14015f466  mov     r14, rdx
0x14015f469  mov     [rbp+57h+var_98], r12d
0x14015f46d  lea     r9d, [r12+4]; cbOutput
0x14015f472  mov     [rsp+0F0h+pcbResult], rax; pcbResult
0x14015f477  lea     r8, [rbp+57h+pbOutput]; pbOutput
0x14015f47b  mov     rsi, rcx
0x14015f47e  lea     rdx, pszProperty; "ObjectLength"
0x14015f485  call    cs:__imp_BCryptGetProperty
0x14015f48c  nop     dword ptr [rax+rax+00h]
0x14015f491  mov     ebx, eax
0x14015f493  test    eax, eax
0x14015f495  jns     short loc_14015F4D5
0x14015f497  lea     rcx, WPP_RECORDER_INITIALIZED
0x14015f49e  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14015f4a5  jz      loc_14015F78A
0x14015f4ab  lea     rcx, WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids
0x14015f4b2  mov     dword ptr [rsp+0F0h+pbInput], eax
0x14015f4b6  mov     [rsp+0F0h+pcbResult], rcx
0x14015f4bb  lea     r9d, [r12+1Dh]
0x14015f4c0  mov     rcx, cs:WPP_GLOBAL_Control
0x14015f4c7  mov     rcx, [rcx+40h]
0x14015f4cb  call    WPP_RECORDER_SF_sd
0x14015f4d0  jmp     loc_14015F78A
0x14015f4d5  mov     ebx, dword ptr [rbp+57h+pbOutput]
0x14015f4d8  mov     edx, ebx
0x14015f4da  mov     [rbp+57h+pbKeyObject], r12
0x14015f4de  mov     [rbp+57h+var_78], r12
0x14015f4e2  call    BthLELibAllocatePoolEx
0x14015f4e7  mov     r8d, ebx; unsigned __int64
0x14015f4ea  lea     rcx, [rbp+57h+pbKeyObject]; this
0x14015f4ee  mov     rdx, rax; unsigned __int8 *
0x14015f4f1  call    ?reset@unique_bthlelib_secure_pool@@QEAAXPEAE_K@Z; unique_bthlelib_secure_pool::reset(uchar *,unsigned __int64)
0x14015f4f6  mov     rbx, [rbp+57h+pbKeyObject]
0x14015f4fa  test    rbx, rbx
0x14015f4fd  jnz     short loc_14015F543
0x14015f4ff  lea     rcx, WPP_RECORDER_INITIALIZED
0x14015f506  mov     ebx, 0C000009Ah
0x14015f50b  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14015f512  jz      loc_14015F781
0x14015f518  lea     rcx, WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids
0x14015f51f  mov     dword ptr [rsp+0F0h+pbInput], ebx
0x14015f523  mov     [rsp+0F0h+pcbResult], rcx
0x14015f528  mov     r9d, 1Eh
0x14015f52e  mov     rcx, cs:WPP_GLOBAL_Control
0x14015f535  mov     rcx, [rcx+40h]
0x14015f539  call    WPP_RECORDER_SF_sd
0x14015f53e  jmp     loc_14015F781
0x14015f543  mov     edx, 1Ch
0x14015f548  mov     [rbp+57h+var_70], r12
0x14015f54c  mov     [rbp+57h+var_68], r12
0x14015f550  call    BthLELibAllocatePoolEx
0x14015f555  mov     rdx, rax; unsigned __int8 *
0x14015f558  lea     rcx, [rbp+57h+var_70]; this
0x14015f55c  mov     r8d, 1Ch; unsigned __int64
0x14015f562  call    ?reset@unique_bthlelib_secure_pool@@QEAAXPEAE_K@Z; unique_bthlelib_secure_pool::reset(uchar *,unsigned __int64)
0x14015f567  mov     rcx, [rbp+57h+var_70]
0x14015f56b  test    rcx, rcx
0x14015f56e  jnz     short loc_14015F5B4
0x14015f570  lea     rcx, WPP_RECORDER_INITIALIZED
0x14015f577  mov     ebx, 0C000009Ah
0x14015f57c  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14015f583  jz      loc_14015F778
0x14015f589  lea     rcx, WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids
0x14015f590  mov     dword ptr [rsp+0F0h+pbInput], ebx
0x14015f594  mov     [rsp+0F0h+pcbResult], rcx
0x14015f599  mov     r9d, 1Fh
0x14015f59f  mov     rcx, cs:WPP_GLOBAL_Control
0x14015f5a6  mov     rcx, [rcx+40h]
0x14015f5aa  call    WPP_RECORDER_SF_sd
0x14015f5af  jmp     loc_14015F778
0x14015f5b4  mov     dword ptr [rcx], 4D42444Bh
0x14015f5ba  lea     rdx, [rbp+57h+hKey]
0x14015f5be  mov     dword ptr [rcx+4], 1
0x14015f5c5  lea     r9, [rbp+57h+phKey]; phKey
0x14015f5c9  mov     dword ptr [rcx+8], 10h
0x14015f5d0  lea     r8, pszBlobType; "KeyDataBlob"
0x14015f5d7  movups  xmm0, xmmword ptr [r14]
0x14015f5db  mov     [rsp+0F0h+var_B0], r12d; dwFlags
0x14015f5e0  mov     [rsp+0F0h+cbInput], 1Ch; cbInput
0x14015f5e8  movdqu  xmmword ptr [rcx+0Ch], xmm0
0x14015f5ed  mov     eax, dword ptr [rbp+57h+pbOutput]
0x14015f5f0  mov     [rsp+0F0h+pbInput], rcx; pbInput
0x14015f5f5  mov     rcx, rsi; hAlgorithm
0x14015f5f8  mov     [rbp+57h+var_60], rdx
0x14015f5fc  xor     edx, edx; hImportKey
0x14015f5fe  mov     [rsp+0F0h+dwFlags], eax; cbKeyObject
0x14015f602  mov     [rsp+0F0h+pcbResult], rbx; pbKeyObject
0x14015f607  mov     [rbp+57h+hKey], r12
0x14015f60b  mov     [rbp+57h+phKey], r12
0x14015f60f  mov     [rbp+57h+var_50], 1
0x14015f613  call    cs:__imp_BCryptImportKey
0x14015f61a  nop     dword ptr [rax+rax+00h]
0x14015f61f  lea     rcx, [rbp+57h+var_60]
0x14015f623  mov     ebx, eax
0x14015f625  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x14015f62a  test    ebx, ebx
0x14015f62c  jns     short loc_14015F672
0x14015f62e  lea     rcx, WPP_RECORDER_INITIALIZED
0x14015f635  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14015f63c  jz      short loc_14015F664
0x14015f63e  mov     r9d, 20h ; ' '
0x14015f644  mov     dword ptr [rsp+0F0h+pbInput], ebx
0x14015f648  lea     rcx, WPP_272f78d0e0f932ff6a8fef96cae1cc50_Traceguids
0x14015f64f  mov     [rsp+0F0h+pcbResult], rcx
0x14015f654  mov     rcx, cs:WPP_GLOBAL_Control
0x14015f65b  mov     rcx, [rcx+40h]
0x14015f65f  call    WPP_RECORDER_SF_sd
0x14015f664  lea     rcx, [rbp+57h+hKey]
0x14015f668  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14015f66d  jmp     loc_14015F778
0x14015f672  xor     eax, eax
0x14015f674  mov     [rbp+57h+var_98], edi
0x14015f677  shr     rdi, 20h
0x14015f67b  mov     edx, r12d
0x14015f67e  mov     [rbp+57h+var_94], di
0x14015f682  mov     [rbp+57h+var_48], eax
0x14015f685  mov     [rbp+57h+var_44], ax
0x14015f689  movsxd  rcx, edx
0x14015f68c  inc     edx
0x14015f68e  mov     al, byte ptr [rbp+rcx+57h+var_98]
0x14015f692  mov     byte ptr [rbp+rcx+57h+var_48], al
0x14015f696  cmp     edx, 6
0x14015f699  jb      short loc_14015F689
0x14015f69b  mov     al, byte ptr [rbp+57h+var_44+1]
0x14015f69e  lea     rdx, [rbp+57h+var_40]; pbInput
0x14015f6a2  mov     rcx, [rbp+57h+hKey]; hKey
0x14015f6a6  xorps   xmm0, xmm0
0x14015f6a9  mov     [rsp+0F0h+var_A8], r12d; dwFlags
0x14015f6ae  mov     r8d, 10h; cbInput
0x14015f6b4  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x14015f6b8  mov     [rbp+57h+var_40+0Dh], al
0x14015f6bb  xor     r9d, r9d; pPaddingInfo
0x14015f6be  mov     al, byte ptr [rbp+57h+var_44]
0x14015f6c1  mov     [rbp+57h+var_40+0Eh], al
0x14015f6c4  mov     al, byte ptr [rbp+57h+var_48+3]
0x14015f6c7  mov     [rbp+57h+var_40+0Fh], al
0x14015f6ca  lea     rax, [rbp+57h+var_98]
0x14015f6ce  mov     qword ptr [rsp+0F0h+var_B0], rax; pcbResult
0x14015f6d3  lea     rax, [rbp+57h+var_40]
0x14015f6d7  mov     [rsp+0F0h+cbInput], r8d; cbOutput
0x14015f6dc  mov     [rsp+0F0h+pbInput], rax; pbOutput
0x14015f6e1  mov     [rsp+0F0h+dwFlags], r12d; cbIV
0x14015f6e6  mov     [rsp+0F0h+pcbResult], r12; pbIV
0x14015f6eb  mov     [rbp+57h+var_98], r12d
0x14015f6ef  call    cs:__imp_BCryptEncrypt
0x14015f6f6  nop     dword ptr [rax+rax+00h]
0x14015f6fb  mov     ebx, eax
0x14015f6fd  test    eax, eax
0x14015f6ff  jns     short loc_14015F724
0x14015f701  lea     rcx, WPP_RECORDER_INITIALIZED
0x14015f708  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14015f70f  jz      loc_14015F664
0x14015f715  mov     r9d, 21h ; '!'
0x14015f71b  mov     dword ptr [rsp+0F0h+pbInput], eax
0x14015f71f  jmp     loc_14015F648
0x14015f724  mov     al, [rbp+57h+var_40+0Dh]
0x14015f727  lea     rdx, [rbp+57h+Source2]; Source2
0x14015f72b  mov     [rbp+57h+Source2], al
0x14015f72e  lea     rcx, [rbp+57h+Source1]; Source1
0x14015f732  mov     al, [rbp+57h+var_40+0Eh]
0x14015f735  mov     r8d, 3; Length
0x14015f73b  mov     [rbp+57h+var_9F], al
0x14015f73e  mov     al, [rbp+57h+var_40+0Fh]
0x14015f741  mov     [rbp+57h+var_9E], al
0x14015f744  mov     al, byte ptr [rbp+57h+var_48+2]
0x14015f747  mov     [rbp+57h+Source1], al
0x14015f74a  mov     al, byte ptr [rbp+57h+var_48+1]
0x14015f74d  mov     [rbp+57h+var_9B], al
0x14015f750  mov     al, byte ptr [rbp+57h+var_48]
0x14015f753  mov     [rbp+57h+var_9A], al
0x14015f756  call    cs:__imp_RtlCompareMemory
0x14015f75d  nop     dword ptr [rax+rax+00h]
0x14015f762  cmp     rax, 3
0x14015f766  lea     rcx, [rbp+57h+hKey]
0x14015f76a  setz    al
0x14015f76d  mov     [r15], al
0x14015f770  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&BCryptDestroyKey(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x14015f775  mov     ebx, r12d
0x14015f778  lea     rcx, [rbp+57h+var_70]; this
0x14015f77c  call    ??1unique_bthlelib_secure_pool@@QEAA@XZ; unique_bthlelib_secure_pool::~unique_bthlelib_secure_pool(void)
0x14015f781  lea     rcx, [rbp+57h+pbKeyObject]; this
0x14015f785  call    ??1unique_bthlelib_secure_pool@@QEAA@XZ; unique_bthlelib_secure_pool::~unique_bthlelib_secure_pool(void)
0x14015f78a  mov     eax, ebx
0x14015f78c  mov     rcx, [rbp+57h+var_30]
0x14015f790  xor     rcx, rsp; StackCookie
0x14015f793  call    __security_check_cookie
0x14015f798  lea     r11, [rsp+0F0h+var_20]
0x14015f7a0  mov     rbx, [r11+38h]
0x14015f7a4  mov     rsi, [r11+40h]
0x14015f7a8  mov     rsp, r11
0x14015f7ab  pop     r15
0x14015f7ad  pop     r14
0x14015f7af  pop     r12
0x14015f7b1  pop     rdi
0x14015f7b2  pop     rbp
0x14015f7b3  retn
```
