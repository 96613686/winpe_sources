# FSQueryForCLSIDFromDeviceInterfaceRegistry(ushort const *,ushort const *,_GUID *)

- ea: `0x180042058`
- end: `0x1800421f3`
- name: `?FSQueryForCLSIDFromDeviceInterfaceRegistry@@YAJPEBG0PEAU_GUID@@@Z`
- size: `411`
- prototype: `__int64 __fastcall(LPCWSTR pszDeviceInterface, LPCWSTR lpValueName, struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180041778`

## callees

- `0x1800019f0`
- `0x180006a98`
- `0x180006cc0`
- `0x18000723c`
- `0x18000d1e0`
- `0x180040a10`
- `0x180042058`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800421a5`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800421a5`

## pseudocode

```c
__int64 __fastcall FSQueryForCLSIDFromDeviceInterfaceRegistry(
        LPCWSTR pszDeviceInterface,
        LPCWSTR lpValueName,
        struct _GUID *a3)
{
  unsigned int v6; // edi
  __int64 v7; // rdx
  DWORD v8; // edi
  const struct std::nothrow_t *unique; // rax
  int v10; // eax
  __int64 v11; // rdx
  unsigned int *v13; // [rsp+28h] [rbp-38h]
  unsigned int *v14; // [rsp+28h] [rbp-38h]
  unsigned int v15; // [rsp+30h] [rbp-30h] BYREF
  LPCOLESTR lpsz; // [rsp+38h] [rbp-28h] BYREF
  __int64 v17; // [rsp+40h] [rbp-20h] BYREF
  GUID iid; // [rsp+48h] [rbp-18h] BYREF

  v15 = 0;
  lpsz = 0;
  iid = GUID_00000000_0000_0000_0000_000000000000;
  if ( !pszDeviceInterface )
  {
    v6 = -2147024809;
    if ( g_wppLevels )
    {
      v7 = 150;
LABEL_4:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids, 0, v6);
      goto LABEL_23;
    }
    goto LABEL_23;
  }
  if ( !a3 )
  {
    v6 = -2147467261;
    if ( g_wppLevels )
    {
      v7 = 151;
      goto LABEL_4;
    }
    goto LABEL_23;
  }
  *a3 = GUID_00000000_0000_0000_0000_000000000000;
  if ( (unsigned int)FSGetDeviceInterfaceRegistryEntry2(pszDeviceInterface, lpValueName, 0, 0, &v15, v13) != -1072860816
    || (v8 = v15, v15 <= 2) )
  {
    v6 = -1072875819;
    goto LABEL_23;
  }
  unique = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned char [0]>(&v17, v15);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=((void **)&lpsz, unique);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v17);
  if ( !lpsz )
  {
    v6 = -2147024882;
    if ( g_wppLevels )
    {
      v7 = 152;
      goto LABEL_4;
    }
    goto LABEL_23;
  }
  v10 = FSGetDeviceInterfaceRegistryEntry2(pszDeviceInterface, lpValueName, (LPBYTE)lpsz, v8, &v15, v14);
  v6 = v10;
  if ( v10 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_23;
    v11 = 153;
LABEL_17:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids, 0, v10);
    goto LABEL_23;
  }
  v10 = IIDFromString(lpsz, &iid);
  v6 = v10;
  if ( v10 >= 0 )
  {
    *a3 = iid;
    goto LABEL_23;
  }
  if ( g_wppLevels )
  {
    v11 = 154;
    goto LABEL_17;
  }
LABEL_23:
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&lpsz);
  return v6;
}

```

## disassembly

```asm
0x180042058  push    rbp
0x18004205a  push    rsi
0x18004205b  push    rdi
0x18004205c  push    r14
0x18004205e  push    r15
0x180042060  mov     rbp, rsp
0x180042063  sub     rsp, 60h
0x180042067  mov     rax, cs:__security_cookie
0x18004206e  xor     rax, rsp
0x180042071  mov     [rbp+var_8], rax
0x180042075  mov     [rbp+var_30], 0
0x18004207c  mov     rsi, r8
0x18004207f  mov     [rbp+lpsz], 0
0x180042087  mov     r15, rdx
0x18004208a  mov     r14, rcx
0x18004208d  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180042094  movdqu  xmmword ptr [rbp+iid.Data1], xmm0
0x180042099  test    rcx, rcx
0x18004209c  jnz     short loc_1800420D8
0x18004209e  mov     edi, 80070057h
0x1800420a3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800420aa  jb      loc_1800421D0
0x1800420b0  mov     edx, 96h
0x1800420b5  mov     dword ptr [rsp+60h+var_40], edi
0x1800420b9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800420c0  lea     r8, WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids
0x1800420c7  xor     r9d, r9d
0x1800420ca  mov     rcx, [rcx+10h]
0x1800420ce  call    WPP_SF_qD
0x1800420d3  jmp     loc_1800421D0
0x1800420d8  test    rsi, rsi
0x1800420db  jnz     short loc_1800420F6
0x1800420dd  mov     edi, 80004003h
0x1800420e2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800420e9  jb      loc_1800421D0
0x1800420ef  mov     edx, 97h; lpValueName
0x1800420f4  jmp     short loc_1800420B5
0x1800420f6  movdqu  xmmword ptr [r8], xmm0
0x1800420fb  lea     rax, [rbp+var_30]
0x1800420ff  xor     r8d, r8d; lpData
0x180042102  xor     r9d, r9d; unsigned int
0x180042105  mov     [rsp+60h+var_40], rax; unsigned int *
0x18004210a  call    ?FSGetDeviceInterfaceRegistryEntry2@@YAJPEBG0PEAEKPEAK2@Z; FSGetDeviceInterfaceRegistryEntry2(ushort const *,ushort const *,uchar *,ulong,ulong *,ulong *)
0x18004210f  cmp     eax, 0C00D7170h
0x180042114  jnz     loc_1800421CB
0x18004211a  mov     edi, [rbp+var_30]
0x18004211d  cmp     edi, 2
0x180042120  jbe     loc_1800421CB
0x180042126  mov     edx, edi
0x180042128  lea     rcx, [rbp+var_20]
0x18004212c  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x180042131  mov     rdx, rax
0x180042134  lea     rcx, [rbp+lpsz]
0x180042138  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x18004213d  lea     rcx, [rbp+var_20]
0x180042141  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x180042146  cmp     [rbp+lpsz], 0
0x18004214b  jnz     short loc_180042165
0x18004214d  mov     edi, 8007000Eh
0x180042152  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180042159  jb      short loc_1800421D0
0x18004215b  mov     edx, 98h
0x180042160  jmp     loc_1800420B5
0x180042165  mov     r8, [rbp+lpsz]; lpData
0x180042169  lea     rax, [rbp+var_30]
0x18004216d  mov     r9d, edi; unsigned int
0x180042170  mov     [rsp+60h+var_40], rax; unsigned int *
0x180042175  mov     rdx, r15; lpValueName
0x180042178  mov     rcx, r14; pszDeviceInterface
0x18004217b  call    ?FSGetDeviceInterfaceRegistryEntry2@@YAJPEBG0PEAEKPEAK2@Z; FSGetDeviceInterfaceRegistryEntry2(ushort const *,ushort const *,uchar *,ulong,ulong *,ulong *)
0x180042180  mov     edi, eax
0x180042182  test    eax, eax
0x180042184  jns     short loc_18004219D
0x180042186  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004218d  jb      short loc_1800421D0
0x18004218f  mov     edx, 99h
0x180042194  mov     dword ptr [rsp+60h+var_40], eax
0x180042198  jmp     loc_1800420B9
0x18004219d  mov     rcx, [rbp+lpsz]; lpsz
0x1800421a1  lea     rdx, [rbp+iid]; lpiid
0x1800421a5  call    cs:__imp_IIDFromString
0x1800421ab  mov     edi, eax
0x1800421ad  test    eax, eax
0x1800421af  jns     short loc_1800421C1
0x1800421b1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800421b8  jb      short loc_1800421D0
0x1800421ba  mov     edx, 9Ah
0x1800421bf  jmp     short loc_180042194
0x1800421c1  movups  xmm0, xmmword ptr [rbp+iid.Data1]
0x1800421c5  movdqu  xmmword ptr [rsi], xmm0
0x1800421c9  jmp     short loc_1800421D0
0x1800421cb  mov     edi, 0C00D36D5h
0x1800421d0  lea     rcx, [rbp+lpsz]
0x1800421d4  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x1800421d9  mov     eax, edi
0x1800421db  mov     rcx, [rbp+var_8]
0x1800421df  xor     rcx, rsp; StackCookie
0x1800421e2  call    __security_check_cookie
0x1800421e7  add     rsp, 60h
0x1800421eb  pop     r15
0x1800421ed  pop     r14
0x1800421ef  pop     rdi
0x1800421f0  pop     rsi
0x1800421f1  pop     rbp
0x1800421f2  retn
```
