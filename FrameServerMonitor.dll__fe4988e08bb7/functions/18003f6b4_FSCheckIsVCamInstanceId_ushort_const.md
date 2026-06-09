# FSCheckIsVCamInstanceId(ushort const *)

- ea: `0x18003f6b4`
- end: `0x18003f7e4`
- name: `?FSCheckIsVCamInstanceId@@YAJPEBG@Z`
- size: `304`
- prototype: `__int64 __fastcall(LPCWSTR pszDeviceInterface)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18004203c`

## callees

- `0x180002346`
- `0x1800060f8`
- `0x180006a98`
- `0x180006cc0`
- `0x18000723c`
- `0x18000d1e0`
- `0x18003f6b4`
- `0x180040914`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003f7bf`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003f7bf`

## pseudocode

```c
__int64 __fastcall FSCheckIsVCamInstanceId(LPCWSTR pszDeviceInterface)
{
  int v2; // edi
  __int64 v3; // rdi
  const struct std::nothrow_t *unique; // rax
  unsigned int v6; // [rsp+50h] [rbp+8h] BYREF
  LPCWCH lpString2; // [rsp+58h] [rbp+10h] BYREF
  __int64 v8; // [rsp+60h] [rbp+18h] BYREF

  lpString2 = 0;
  v6 = 0;
  if ( pszDeviceInterface )
  {
    v2 = FSGetDeviceInterfaceProperty(
           pszDeviceInterface,
           (DEVPROPKEY *)&DEVPKEY_DeviceInterface_ReferenceString,
           0,
           0,
           &v6);
    if ( v2 >= 0 )
    {
      v3 = v6;
      unique = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned char [0]>(&v8, v6 + 2LL);
      wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(
        (void **)&lpString2,
        unique);
      wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v8);
      if ( lpString2 )
      {
        memset_0((void *)lpString2, 0, v3 + 2);
        v2 = FSGetDeviceInterfaceProperty(
               pszDeviceInterface,
               (DEVPROPKEY *)&DEVPKEY_DeviceInterface_ReferenceString,
               (PBYTE)lpString2,
               (int)v3 + 2,
               &v6);
        if ( v2 >= 0 && CompareStringOrdinal(L"{FCEBBA03-9D13-4C13-9940-CC84FCD132D1}", -1, lpString2, -1, 1) != 2 )
          v2 = -1072875819;
      }
      else
      {
        v2 = -2147024882;
        if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            57,
            &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids,
            0,
            -2147024882);
      }
    }
  }
  else
  {
    v2 = -2147024809;
  }
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&lpString2);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18003f6b4  push    rbp
0x18003f6b6  push    rsi
0x18003f6b7  push    rdi
0x18003f6b8  sub     rsp, 30h
0x18003f6bc  mov     [rsp+48h+lpString2], 0
0x18003f6c5  mov     rsi, rcx
0x18003f6c8  mov     [rsp+48h+arg_0], 0
0x18003f6d0  test    rcx, rcx
0x18003f6d3  jnz     short loc_18003F6DF
0x18003f6d5  mov     edi, 80070057h
0x18003f6da  jmp     loc_18003F7D0
0x18003f6df  lea     rax, [rsp+48h+arg_0]
0x18003f6e4  xor     r9d, r9d; unsigned int
0x18003f6e7  xor     r8d, r8d; PropertyBuffer
0x18003f6ea  mov     qword ptr [rsp+48h+bIgnoreCase], rax; unsigned int *
0x18003f6ef  lea     rdx, DEVPKEY_DeviceInterface_ReferenceString; PropertyKey
0x18003f6f6  call    ?FSGetDeviceInterfaceProperty@@YAJPEBGPEBU_DEVPROPKEY@@PEAEKPEAK@Z; FSGetDeviceInterfaceProperty(ushort const *,_DEVPROPKEY const *,uchar *,ulong,ulong *)
0x18003f6fb  mov     edi, eax
0x18003f6fd  test    eax, eax
0x18003f6ff  js      loc_18003F7D0
0x18003f705  mov     edi, [rsp+48h+arg_0]
0x18003f709  lea     rcx, [rsp+48h+arg_10]
0x18003f70e  lea     rdx, [rdi+2]
0x18003f712  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18003f717  mov     rdx, rax
0x18003f71a  lea     rcx, [rsp+48h+lpString2]
0x18003f71f  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x18003f724  lea     rcx, [rsp+48h+arg_10]
0x18003f729  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18003f72e  cmp     [rsp+48h+lpString2], 0
0x18003f734  jnz     short loc_18003F76D
0x18003f736  mov     edi, 8007000Eh
0x18003f73b  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x18003f740  cmp     al, 1
0x18003f742  jb      loc_18003F7D0
0x18003f748  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f74f  lea     r8, WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids
0x18003f756  mov     edx, 39h ; '9'
0x18003f75b  mov     [rsp+48h+bIgnoreCase], edi
0x18003f75f  xor     r9d, r9d
0x18003f762  mov     rcx, [rcx+10h]
0x18003f766  call    WPP_SF_qD
0x18003f76b  jmp     short loc_18003F7D0
0x18003f76d  mov     rcx, [rsp+48h+lpString2]; void *
0x18003f772  lea     r8, [rdi+2]; Size
0x18003f776  xor     edx, edx; Val
0x18003f778  call    memset_0
0x18003f77d  mov     r8, [rsp+48h+lpString2]; PropertyBuffer
0x18003f782  lea     rax, [rsp+48h+arg_0]
0x18003f787  lea     r9d, [rdi+2]; unsigned int
0x18003f78b  mov     qword ptr [rsp+48h+bIgnoreCase], rax; unsigned int *
0x18003f790  lea     rdx, DEVPKEY_DeviceInterface_ReferenceString; PropertyKey
0x18003f797  mov     rcx, rsi; pszDeviceInterface
0x18003f79a  call    ?FSGetDeviceInterfaceProperty@@YAJPEBGPEBU_DEVPROPKEY@@PEAEKPEAK@Z; FSGetDeviceInterfaceProperty(ushort const *,_DEVPROPKEY const *,uchar *,ulong,ulong *)
0x18003f79f  mov     edi, eax
0x18003f7a1  test    eax, eax
0x18003f7a3  js      short loc_18003F7D0
0x18003f7a5  mov     r8, [rsp+48h+lpString2]; lpString2
0x18003f7aa  lea     rcx, aFcebba039d134c; "{FCEBBA03-9D13-4C13-9940-CC84FCD132D1}"
0x18003f7b1  or      edx, 0FFFFFFFFh; cchCount1
0x18003f7b4  mov     [rsp+48h+bIgnoreCase], 1; bIgnoreCase
0x18003f7bc  mov     r9d, edx; cchCount2
0x18003f7bf  call    cs:__imp_CompareStringOrdinal
0x18003f7c5  cmp     eax, 2
0x18003f7c8  mov     ecx, 0C00D36D5h
0x18003f7cd  cmovnz  edi, ecx
0x18003f7d0  lea     rcx, [rsp+48h+lpString2]
0x18003f7d5  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18003f7da  mov     eax, edi
0x18003f7dc  add     rsp, 30h
0x18003f7e0  pop     rdi
0x18003f7e1  pop     rsi
0x18003f7e2  pop     rbp
0x18003f7e3  retn
```
