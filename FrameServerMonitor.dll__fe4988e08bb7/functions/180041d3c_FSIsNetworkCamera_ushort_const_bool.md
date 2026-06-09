# FSIsNetworkCamera(ushort const *,bool *)

- ea: `0x180041d3c`
- end: `0x180041e89`
- name: `?FSIsNetworkCamera@@YAJPEBGPEA_N@Z`
- size: `333`
- prototype: `__int64 __fastcall(LPCWSTR pszDeviceInterface, bool *)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800120e0`
- `0x1800124f4`

## callees

- `0x180002346`
- `0x1800060f8`
- `0x180006a98`
- `0x180006cc0`
- `0x18000723c`
- `0x18000d1e0`
- `0x180040914`
- `0x180041d3c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180041e61`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180041e61`

## pseudocode

```c
__int64 __fastcall FSIsNetworkCamera(LPCWSTR pszDeviceInterface, bool *a2)
{
  signed int v4; // edi
  __int64 v5; // rdi
  const struct std::nothrow_t *unique; // rax
  unsigned int v8; // [rsp+50h] [rbp+8h] BYREF
  LPCWCH lpString2; // [rsp+60h] [rbp+18h] BYREF
  __int64 v10; // [rsp+68h] [rbp+20h] BYREF

  lpString2 = 0;
  v8 = 0;
  if ( pszDeviceInterface )
  {
    if ( a2 )
    {
      *a2 = 0;
      v4 = FSGetDeviceInterfaceProperty(
             pszDeviceInterface,
             (DEVPROPKEY *)&DEVPKEY_DeviceInterface_ReferenceString,
             0,
             0,
             &v8);
      if ( v4 >= 0 )
      {
        v5 = v8;
        unique = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned char [0]>(&v10, v8 + 2LL);
        wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(
          (void **)&lpString2,
          unique);
        wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v10);
        if ( lpString2 )
        {
          memset_0((void *)lpString2, 0, v5 + 2);
          v4 = FSGetDeviceInterfaceProperty(
                 pszDeviceInterface,
                 (DEVPROPKEY *)&DEVPKEY_DeviceInterface_ReferenceString,
                 (PBYTE)lpString2,
                 v5 + 2,
                 &v8);
          if ( v4 >= 0 && CompareStringOrdinal(L"{F5E9E279-06E1-4094-96C4-B43B37852EB2}", -1, lpString2, -1, 1) == 2 )
            *a2 = 1;
        }
        else
        {
          v4 = -2147024882;
          if ( _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel() )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              100,
              &WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids,
              0,
              -2147024882);
        }
      }
    }
    else
    {
      v4 = -2147467261;
    }
  }
  else
  {
    v4 = -2147024809;
  }
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&lpString2);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180041d3c  mov     [rsp+arg_8], rbp
0x180041d41  push    rsi
0x180041d42  push    rdi
0x180041d43  push    r14
0x180041d45  sub     rsp, 30h
0x180041d49  mov     [rsp+48h+lpString2], 0
0x180041d52  mov     rsi, rdx
0x180041d55  mov     [rsp+48h+arg_0], 0
0x180041d5d  mov     rbp, rcx
0x180041d60  test    rcx, rcx
0x180041d63  jnz     short loc_180041D6F
0x180041d65  mov     edi, 80070057h
0x180041d6a  jmp     loc_180041E6F
0x180041d6f  test    rsi, rsi
0x180041d72  jnz     short loc_180041D7E
0x180041d74  mov     edi, 80004003h
0x180041d79  jmp     loc_180041E6F
0x180041d7e  mov     byte ptr [rdx], 0
0x180041d81  lea     rax, [rsp+48h+arg_0]
0x180041d86  lea     rdx, DEVPKEY_DeviceInterface_ReferenceString; PropertyKey
0x180041d8d  mov     qword ptr [rsp+48h+bIgnoreCase], rax; unsigned int *
0x180041d92  xor     r9d, r9d; unsigned int
0x180041d95  xor     r8d, r8d; PropertyBuffer
0x180041d98  call    ?FSGetDeviceInterfaceProperty@@YAJPEBGPEBU_DEVPROPKEY@@PEAEKPEAK@Z; FSGetDeviceInterfaceProperty(ushort const *,_DEVPROPKEY const *,uchar *,ulong,ulong *)
0x180041d9d  mov     edi, eax
0x180041d9f  test    eax, eax
0x180041da1  js      loc_180041E6F
0x180041da7  mov     edi, [rsp+48h+arg_0]
0x180041dab  lea     rcx, [rsp+48h+arg_18]
0x180041db0  lea     rdx, [rdi+2]
0x180041db4  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x180041db9  mov     rdx, rax
0x180041dbc  lea     rcx, [rsp+48h+lpString2]
0x180041dc1  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x180041dc6  lea     rcx, [rsp+48h+arg_18]
0x180041dcb  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x180041dd0  cmp     [rsp+48h+lpString2], 0
0x180041dd6  jnz     short loc_180041E0F
0x180041dd8  mov     edi, 8007000Eh
0x180041ddd  call    ?GetLevel@_MFControlLevel_CTRLGUID_MF_PLATFORM@@SAEXZ; _MFControlLevel_CTRLGUID_MF_PLATFORM::GetLevel(void)
0x180041de2  cmp     al, 1
0x180041de4  jb      loc_180041E6F
0x180041dea  mov     rcx, cs:WPP_GLOBAL_Control
0x180041df1  lea     r8, WPP_7b4a1a05ed4c337521a6f7c140b95e15_Traceguids
0x180041df8  mov     edx, 64h ; 'd'
0x180041dfd  mov     [rsp+48h+bIgnoreCase], edi
0x180041e01  xor     r9d, r9d
0x180041e04  mov     rcx, [rcx+10h]
0x180041e08  call    WPP_SF_qD
0x180041e0d  jmp     short loc_180041E6F
0x180041e0f  mov     rcx, [rsp+48h+lpString2]; void *
0x180041e14  lea     r8, [rdi+2]; Size
0x180041e18  xor     edx, edx; Val
0x180041e1a  call    memset_0
0x180041e1f  mov     r8, [rsp+48h+lpString2]; PropertyBuffer
0x180041e24  lea     rax, [rsp+48h+arg_0]
0x180041e29  lea     r9d, [rdi+2]; unsigned int
0x180041e2d  mov     qword ptr [rsp+48h+bIgnoreCase], rax; unsigned int *
0x180041e32  lea     rdx, DEVPKEY_DeviceInterface_ReferenceString; PropertyKey
0x180041e39  mov     rcx, rbp; pszDeviceInterface
0x180041e3c  call    ?FSGetDeviceInterfaceProperty@@YAJPEBGPEBU_DEVPROPKEY@@PEAEKPEAK@Z; FSGetDeviceInterfaceProperty(ushort const *,_DEVPROPKEY const *,uchar *,ulong,ulong *)
0x180041e41  mov     edi, eax
0x180041e43  test    eax, eax
0x180041e45  js      short loc_180041E6F
0x180041e47  mov     r8, [rsp+48h+lpString2]; lpString2
0x180041e4c  lea     rcx, aF5e9e27906e140; "{F5E9E279-06E1-4094-96C4-B43B37852EB2}"
0x180041e53  or      edx, 0FFFFFFFFh; cchCount1
0x180041e56  mov     [rsp+48h+bIgnoreCase], 1; bIgnoreCase
0x180041e5e  mov     r9d, edx; cchCount2
0x180041e61  call    cs:__imp_CompareStringOrdinal
0x180041e67  cmp     eax, 2
0x180041e6a  jnz     short loc_180041E6F
0x180041e6c  mov     byte ptr [rsi], 1
0x180041e6f  lea     rcx, [rsp+48h+lpString2]
0x180041e74  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x180041e79  mov     rbp, [rsp+48h+arg_8]
0x180041e7e  mov     eax, edi
0x180041e80  add     rsp, 30h
0x180041e84  pop     r14
0x180041e86  pop     rdi
0x180041e87  pop     rsi
0x180041e88  retn
```
