# PrivilegedAppAccessCheck(ulong,ushort const *)

- ea: `0x18000e1e8`
- end: `0x18000e49f`
- name: `?PrivilegedAppAccessCheck@@YAJKPEBG@Z`
- size: `695`
- prototype: `__int64 __fastcall(DWORD dwProcessId, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18000e6a0`

## callees

- `0x180009850`
- `0x18000b6f4`
- `0x18000dee0`
- `0x18000df04`
- `0x18000e1e8`
- `0x18000e5f4`
- `0x180010414`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000e3f2`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000e3f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e3bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e3bf`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000e38a`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000e38a`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18000e2fe`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18000e427`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18000e2fe`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjectProperties` at `0x18000e427`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x18000e286`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x18000e33d`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x18000e286`
- `api-ms-win-devices-query-l1-1-0!DevGetObjectProperties` at `0x18000e33d`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000e2e8`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18000e2e8`

## pseudocode

```c
__int64 __fastcall PrivilegedAppAccessCheck(DWORD dwProcessId, const unsigned __int16 *a2)
{
  __int64 v3; // rdi
  int ObjectProperties; // ebx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  _WORD *v10; // rsi
  char *v11; // rbx
  unsigned __int16 **v12; // r8
  signed int LastError; // eax
  __int64 v14; // rax
  unsigned int v16; // [rsp+40h] [rbp-49h] BYREF
  __int64 v17; // [rsp+48h] [rbp-41h] BYREF
  __int64 v18; // [rsp+50h] [rbp-39h] BYREF
  LPOLESTR lpsz; // [rsp+58h] [rbp-31h] BYREF
  IID rclsid; // [rsp+60h] [rbp-29h] BYREF
  DEVPROPKEY v21; // [rsp+70h] [rbp-19h] BYREF
  int v22; // [rsp+84h] [rbp-5h]
  __int64 v23; // [rsp+88h] [rbp-1h]
  DEVPROPKEY v24; // [rsp+90h] [rbp+7h] BYREF
  int v25; // [rsp+A4h] [rbp+1Bh]
  __int64 v26; // [rsp+A8h] [rbp+1Fh]

  v21 = DEVPKEY_Device_ContainerId;
  v22 = 0;
  v23 = 0;
  v24 = DEVPKEY_DeviceContainer_PrivilegedPackageFamilyNames;
  v25 = 0;
  v26 = 0;
  v16 = 0;
  v17 = 0;
  lpsz = 0;
  v3 = 0;
  v18 = 0;
  ObjectProperties = DevGetObjectProperties(1, a2, 0, 1, &v21, &v16, &v17);
  if ( ObjectProperties < 0 )
    goto LABEL_28;
  v5 = v17;
  v6 = v16;
  if ( v16 != 1 || *(_DWORD *)(v17 + 16) != 2 )
    goto LABEL_9;
  v7 = *(_QWORD *)v17 - *(_QWORD *)&DEVPKEY_Device_ContainerId.fmtid.Data1;
  if ( *(_QWORD *)v17 == *(_QWORD *)&DEVPKEY_Device_ContainerId.fmtid.Data1 )
    v7 = *(_QWORD *)(v17 + 8) - *(_QWORD *)DEVPKEY_Device_ContainerId.fmtid.Data4;
  if ( !v7 && *(_DWORD *)(v17 + 32) == 13 )
  {
    rclsid = *(IID *)*(_QWORD *)(v17 + 40);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &lpsz,
      0);
    ObjectProperties = StringFromCLSID(&rclsid, &lpsz);
    v6 = v16;
    v5 = v17;
  }
  else
  {
LABEL_9:
    ObjectProperties = -2147418113;
  }
  DevFreeObjectProperties(v6, v5);
  v16 = 0;
  v17 = 0;
  if ( ObjectProperties >= 0 )
  {
    ObjectProperties = DevGetObjectProperties(2, lpsz, 0, 1, &v24, &v16, &v17);
    if ( ObjectProperties >= 0 )
    {
      v8 = v17;
      v9 = v16;
      if ( v16 != 1 || *(_DWORD *)(v17 + 32) != 8210 || !*(_DWORD *)(v17 + 36) || (v10 = *(_WORD **)(v17 + 40)) == 0 )
      {
        ObjectProperties = -2147418113;
        goto LABEL_29;
      }
      v11 = (char *)OpenProcess(0x1000u, 0, dwProcessId);
      *(_QWORD *)&rclsid.Data1 = v11;
      if ( (unsigned __int64)(v11 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
      {
        LastError = GetLastError();
        ObjectProperties = LastError;
        if ( LastError > 0 )
          ObjectProperties = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &v18,
          0);
        ObjectProperties = CallerIdentity::GetPackageFamilyNameFromProcess(v11, &v18, v12);
        v3 = v18;
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&rclsid);
      if ( ObjectProperties >= 0 )
      {
        ObjectProperties = -2147024891;
        while ( *v10 )
        {
          if ( !(unsigned int)_o__wcsicmp(v10, v3) )
          {
            ObjectProperties = 0;
            break;
          }
          v14 = -1;
          do
            ++v14;
          while ( v10[v14] );
          v10 += v14 + 1;
        }
      }
    }
LABEL_28:
    v8 = v17;
    v9 = v16;
LABEL_29:
    if ( (_DWORD)v9 && v8 )
      DevFreeObjectProperties(v9, v8);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      &WPP_bfb02dd78cf433073ae18b437e1fe663_Traceguids,
      (unsigned int)ObjectProperties);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v18);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&lpsz);
  return (unsigned int)ObjectProperties;
}

```

## disassembly

```asm
0x18000e1e8  mov     [rsp-8+arg_10], rbx
0x18000e1ed  push    rbp
0x18000e1ee  push    rsi
0x18000e1ef  push    rdi
0x18000e1f0  push    r14
0x18000e1f2  push    r15
0x18000e1f4  lea     rbp, [rsp-37h]
0x18000e1f9  sub     rsp, 0C0h
0x18000e200  mov     rax, cs:__security_cookie
0x18000e207  xor     rax, rsp
0x18000e20a  mov     [rbp+57h+var_30], rax
0x18000e20e  mov     r14d, ecx
0x18000e211  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_ContainerId.fmtid.Data1
0x18000e218  movups  [rbp+57h+var_70], xmm0
0x18000e21c  mov     eax, cs:DEVPKEY_Device_ContainerId.pid
0x18000e222  mov     [rbp+57h+var_60], eax
0x18000e225  xor     r15d, r15d
0x18000e228  mov     [rbp+57h+var_5C], r15d
0x18000e22c  mov     [rbp+57h+var_58], r15
0x18000e230  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceContainer_PrivilegedPackageFamilyNames.fmtid.Data1
0x18000e237  movups  [rbp+57h+var_50], xmm0
0x18000e23b  mov     eax, cs:DEVPKEY_DeviceContainer_PrivilegedPackageFamilyNames.pid
0x18000e241  mov     [rbp+57h+var_40], eax
0x18000e244  mov     [rbp+57h+var_3C], r15d
0x18000e248  mov     [rbp+57h+var_38], r15
0x18000e24c  mov     [rbp+57h+var_A0], r15d
0x18000e250  mov     [rbp+57h+var_98], r15
0x18000e254  mov     [rbp+57h+lpsz], r15
0x18000e258  mov     edi, r15d
0x18000e25b  mov     [rbp+57h+var_90], r15
0x18000e25f  lea     rax, [rbp+57h+var_98]
0x18000e263  mov     [rsp+0E0h+var_B0], rax
0x18000e268  lea     rax, [rbp+57h+var_A0]
0x18000e26c  mov     [rsp+0E0h+var_B8], rax
0x18000e271  lea     rax, [rbp+57h+var_70]
0x18000e275  mov     [rsp+0E0h+var_C0], rax
0x18000e27a  lea     esi, [r15+1]
0x18000e27e  mov     r9d, esi
0x18000e281  xor     r8d, r8d
0x18000e284  mov     ecx, esi
0x18000e286  call    cs:__imp_DevGetObjectProperties
0x18000e28c  mov     ebx, eax
0x18000e28e  test    eax, eax
0x18000e290  js      loc_18000E417
0x18000e296  mov     rdx, [rbp+57h+var_98]
0x18000e29a  mov     ecx, [rbp+57h+var_A0]
0x18000e29d  cmp     ecx, esi
0x18000e29f  jnz     short loc_18000E2F9
0x18000e2a1  cmp     dword ptr [rdx+10h], 2
0x18000e2a5  jnz     short loc_18000E2F9
0x18000e2a7  mov     rax, [rdx]
0x18000e2aa  sub     rax, qword ptr cs:DEVPKEY_Device_ContainerId.fmtid.Data1
0x18000e2b1  jnz     short loc_18000E2BE
0x18000e2b3  mov     rax, [rdx+8]
0x18000e2b7  sub     rax, qword ptr cs:DEVPKEY_Device_ContainerId.fmtid.Data4
0x18000e2be  test    rax, rax
0x18000e2c1  jnz     short loc_18000E2F9
0x18000e2c3  cmp     dword ptr [rdx+20h], 0Dh
0x18000e2c7  jnz     short loc_18000E2F9
0x18000e2c9  mov     rax, [rdx+28h]
0x18000e2cd  movups  xmm0, xmmword ptr [rax]
0x18000e2d0  movdqu  xmmword ptr [rbp+57h+rclsid.Data1], xmm0
0x18000e2d5  xor     edx, edx
0x18000e2d7  lea     rcx, [rbp+57h+lpsz]
0x18000e2db  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18000e2e0  lea     rdx, [rbp+57h+lpsz]; lplpsz
0x18000e2e4  lea     rcx, [rbp+57h+rclsid]; rclsid
0x18000e2e8  call    cs:__imp_StringFromCLSID
0x18000e2ee  mov     ebx, eax
0x18000e2f0  mov     ecx, [rbp+57h+var_A0]
0x18000e2f3  mov     rdx, [rbp+57h+var_98]
0x18000e2f7  jmp     short loc_18000E2FE
0x18000e2f9  mov     ebx, 8000FFFFh
0x18000e2fe  call    cs:__imp_DevFreeObjectProperties
0x18000e304  mov     [rbp+57h+var_A0], r15d
0x18000e308  mov     [rbp+57h+var_98], r15
0x18000e30c  test    ebx, ebx
0x18000e30e  js      loc_18000E42D
0x18000e314  lea     rax, [rbp+57h+var_98]
0x18000e318  mov     [rsp+0E0h+var_B0], rax
0x18000e31d  lea     rax, [rbp+57h+var_A0]
0x18000e321  mov     [rsp+0E0h+var_B8], rax
0x18000e326  lea     rax, [rbp+57h+var_50]
0x18000e32a  mov     [rsp+0E0h+var_C0], rax
0x18000e32f  mov     r9d, esi
0x18000e332  xor     r8d, r8d
0x18000e335  mov     rdx, [rbp+57h+lpsz]
0x18000e339  lea     ecx, [r8+2]
0x18000e33d  call    cs:__imp_DevGetObjectProperties
0x18000e343  mov     ebx, eax
0x18000e345  test    eax, eax
0x18000e347  js      loc_18000E417
0x18000e34d  mov     rdx, [rbp+57h+var_98]
0x18000e351  mov     ecx, [rbp+57h+var_A0]
0x18000e354  cmp     ecx, esi
0x18000e356  jnz     loc_18000E497
0x18000e35c  cmp     dword ptr [rdx+20h], 2012h
0x18000e363  jnz     loc_18000E497
0x18000e369  cmp     [rdx+24h], r15d
0x18000e36d  jz      loc_18000E497
0x18000e373  mov     rsi, [rdx+28h]
0x18000e377  test    rsi, rsi
0x18000e37a  jz      loc_18000E497
0x18000e380  mov     r8d, r14d; dwProcessId
0x18000e383  xor     edx, edx; bInheritHandle
0x18000e385  mov     ecx, 1000h; dwDesiredAccess
0x18000e38a  call    cs:__imp_OpenProcess
0x18000e390  mov     rbx, rax
0x18000e393  mov     qword ptr [rbp+57h+rclsid.Data1], rax
0x18000e397  dec     rax
0x18000e39a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000e39e  ja      short loc_18000E3BF
0x18000e3a0  xor     edx, edx
0x18000e3a2  lea     rcx, [rbp+57h+var_90]
0x18000e3a6  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18000e3ab  lea     rdx, [rbp+57h+var_90]; void *
0x18000e3af  mov     rcx, rbx; hProcess
0x18000e3b2  call    ?GetPackageFamilyNameFromProcess@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetPackageFamilyNameFromProcess(void *,ushort * *)
0x18000e3b7  mov     ebx, eax
0x18000e3b9  mov     rdi, [rbp+57h+var_90]
0x18000e3bd  jmp     short loc_18000E3D4
0x18000e3bf  call    cs:__imp_GetLastError
0x18000e3c5  mov     ebx, eax
0x18000e3c7  test    eax, eax
0x18000e3c9  jle     short loc_18000E3D4
0x18000e3cb  movzx   ebx, ax
0x18000e3ce  or      ebx, 80070000h
0x18000e3d4  lea     rcx, [rbp+57h+rclsid]
0x18000e3d8  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18000e3dd  test    ebx, ebx
0x18000e3df  js      short loc_18000E417
0x18000e3e1  mov     ebx, 80070005h
0x18000e3e6  cmp     [rsi], r15w
0x18000e3ea  jz      short loc_18000E417
0x18000e3ec  mov     rdx, rdi
0x18000e3ef  mov     rcx, rsi
0x18000e3f2  call    cs:__imp__o__wcsicmp
0x18000e3f8  test    eax, eax
0x18000e3fa  jz      short loc_18000E414
0x18000e3fc  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e400  inc     rax
0x18000e403  cmp     [rsi+rax*2], r15w
0x18000e408  jnz     short loc_18000E400
0x18000e40a  lea     rsi, [rsi+rax*2]
0x18000e40e  add     rsi, 2
0x18000e412  jmp     short loc_18000E3E6
0x18000e414  mov     ebx, r15d
0x18000e417  mov     rdx, [rbp+57h+var_98]
0x18000e41b  mov     ecx, [rbp+57h+var_A0]
0x18000e41e  test    ecx, ecx
0x18000e420  jz      short loc_18000E42D
0x18000e422  test    rdx, rdx
0x18000e425  jz      short loc_18000E42D
0x18000e427  call    cs:__imp_DevFreeObjectProperties
0x18000e42d  lea     rax, WPP_GLOBAL_Control
0x18000e434  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e43b  cmp     rcx, rax
0x18000e43e  jz      short loc_18000E45F
0x18000e440  test    byte ptr [rcx+1Ch], 10h
0x18000e444  jz      short loc_18000E45F
0x18000e446  mov     edx, 0Ch
0x18000e44b  mov     r9d, ebx
0x18000e44e  lea     r8, WPP_bfb02dd78cf433073ae18b437e1fe663_Traceguids
0x18000e455  mov     rcx, [rcx+10h]
0x18000e459  call    WPP_SF_d
0x18000e45e  nop
0x18000e45f  lea     rcx, [rbp+57h+var_90]
0x18000e463  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000e468  nop
0x18000e469  lea     rcx, [rbp+57h+lpsz]
0x18000e46d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000e472  mov     eax, ebx
0x18000e474  mov     rcx, [rbp+57h+var_30]
0x18000e478  xor     rcx, rsp; StackCookie
0x18000e47b  call    __security_check_cookie
0x18000e480  mov     rbx, [rsp+0E0h+arg_10]
0x18000e488  add     rsp, 0C0h
0x18000e48f  pop     r15
0x18000e491  pop     r14
0x18000e493  pop     rdi
0x18000e494  pop     rsi
0x18000e495  pop     rbp
0x18000e496  retn
0x18000e497  mov     ebx, 8000FFFFh
0x18000e49c  jmp     short loc_18000E41E
```
