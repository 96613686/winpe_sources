# DdcRegistry::GetStringValue(HKEY__ *,ushort const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001bbe8`
- end: `0x18001be3e`
- name: `?GetStringValue@DdcRegistry@@SAJPEAUHKEY__@@PEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `598`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, const WCHAR *, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016aa4`
- `0x180023c64`

## callees

- `0x180004d5c`
- `0x1800050b8`
- `0x18001b728`
- `0x18001bbe8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001be28`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001be28`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bc1f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001bc1f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001bcd1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001bddd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001bcd1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001bddd`

## string_xrefs

- `0x18001bc64`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcregistry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DdcRegistry::GetStringValue(__int64 a1, const WCHAR *a2, const WCHAR *a3, __int64 a4)
{
  int v6; // edi
  _WORD *v7; // rax
  int v8; // edx
  int v9; // ecx
  LSTATUS v10; // eax
  int v11; // edx
  unsigned int v12; // eax
  unsigned __int64 v13; // rdi
  __int64 v14; // rax
  __int64 v15; // r8
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // r9
  _WORD *v19; // rdi
  __int64 i; // rcx
  BYTE *lpData; // rax
  LSTATUS Value; // eax
  int v23; // edx
  __int64 v25; // [rsp+0h] [rbp-58h] BYREF
  int v26; // [rsp+30h] [rbp-28h]
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  __int64 cbData; // [rsp+60h] [rbp+8h] BYREF
  DWORD Type; // [rsp+78h] [rbp+20h] BYREF

  cbData = a1;
  hKey = 0;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x20019u, &hKey);
  *(_QWORD *)(a4 + 16) = 0;
  v7 = (_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    *v7 = 0;
    if ( (unsigned int)(v6 - 2) <= 1 )
    {
      v6 = -2147023728;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v9,
          v8,
          -2147023728,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistry.cpp",
          250,
          "CBR(lRet != 2L && lRet != 3L)");
      goto LABEL_44;
    }
    if ( v6 )
    {
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v9,
          v8,
          v6,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistry.cpp",
          251,
          "CBR(lRet == 0L)");
      goto LABEL_44;
    }
    LODWORD(cbData) = 0;
    Type = 0;
    v10 = RegQueryValueExW(hKey, a3, 0, &Type, 0, (LPDWORD)&cbData);
    v6 = v10;
    if ( v10 )
    {
      if ( v10 > 0 )
        v6 = (unsigned __int16)v10 | 0x80070000;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v9,
          v11,
          v6,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistry.cpp",
          9,
          "CBR(lRet == 0L)");
      goto LABEL_44;
    }
    if ( !(_DWORD)cbData )
      goto LABEL_35;
    if ( Type != 1 && (unsigned int)cbData > 1 && (cbData & 1) == 0 )
    {
      v6 = -2147467259;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v9,
          v11,
          -2147467259,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistry.cpp",
          17,
          "CBR(dwType == ( 1ul ) || cbSize <= 1 || (cbSize & 0x1) != 0)");
      goto LABEL_44;
    }
    v12 = (unsigned int)(cbData - 1) >> 1;
    v13 = *(_QWORD *)(a4 + 16);
    if ( v12 > v13 )
    {
      if ( v12 - v13 > *(_QWORD *)(a4 + 24) - v13 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,unsigned short>(
          a4,
          v12 - v13,
          v12,
          v12 - v13);
      }
      else
      {
        *(_QWORD *)(a4 + 16) = v12;
        v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
        v19 = (_WORD *)(v18 + 2 * v13);
        if ( v16 )
        {
          for ( i = v16; i; --i )
            *v19++ = 0;
        }
        *(_WORD *)(v18 + 2 * v17) = 0;
      }
    }
    else
    {
      *(_QWORD *)(a4 + 16) = v12;
      v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
      *(_WORD *)(v14 + 2 * v15) = 0;
    }
    lpData = (BYTE *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr();
    Value = RegQueryValueExW(hKey, a3, 0, 0, lpData, (LPDWORD)&cbData);
    v6 = Value;
    if ( !Value )
    {
LABEL_35:
      v6 = 0;
      goto LABEL_44;
    }
    if ( Value > 0 )
      v6 = (unsigned __int16)Value | 0x80070000;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v9,
        v23,
        v6,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistry.cpp",
        39,
        "CBR(lRet == 0L)");
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      v26 = -2147024882;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v9,
          (unsigned int)&v25,
          -2147024882,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcregistry.cpp",
          28,
          "CHR(((HRESULT)0x8007000EL))");
      v6 = v26;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18001BE16);
    }
  }
LABEL_44:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001bbe8  mov     r11, rsp
0x18001bbeb  mov     [r11+10h], rbx
0x18001bbef  mov     [r11+8], rcx
0x18001bbf3  push    rsi
0x18001bbf4  push    rdi
0x18001bbf5  push    r14
0x18001bbf7  sub     rsp, 40h
0x18001bbfb  mov     rsi, r9
0x18001bbfe  mov     r14, r8
0x18001bc01  xor     ebx, ebx
0x18001bc03  mov     [r11-20h], rbx
0x18001bc07  lea     rax, [r11-20h]
0x18001bc0b  mov     [r11-38h], rax
0x18001bc0f  mov     r9d, 20019h; samDesired
0x18001bc15  xor     r8d, r8d; ulOptions
0x18001bc18  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001bc1f  call    cs:__imp_RegOpenKeyExW
0x18001bc25  mov     edi, eax
0x18001bc27  mov     [rsi+10h], rbx
0x18001bc2b  mov     rcx, rsi
0x18001bc2e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001bc33  mov     [rax], bx
0x18001bc36  lea     eax, [rdi-2]
0x18001bc39  cmp     eax, 1
0x18001bc3c  ja      short loc_18001BC78
0x18001bc3e  mov     edi, 80070490h
0x18001bc43  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001bc4a  jz      loc_18001BE1E
0x18001bc50  lea     rax, aCbrLret2lLret3; "CBR(lRet != 2L && lRet != 3L)"
0x18001bc57  mov     [rsp+58h+lpcbData], rax
0x18001bc5c  mov     dword ptr [rsp+58h+lpData], 0FAh
0x18001bc64  lea     r9, aOnecoreuapShel_0; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18001bc6b  mov     r8d, edi
0x18001bc6e  call    McTemplateU0dsqs_EventWriteTransfer
0x18001bc73  jmp     loc_18001BE1E
0x18001bc78  test    edi, edi
0x18001bc7a  jz      short loc_18001BCAA
0x18001bc7c  jle     short loc_18001BC87
0x18001bc7e  movzx   edi, di
0x18001bc81  or      edi, 80070000h
0x18001bc87  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001bc8e  jz      loc_18001BE1E
0x18001bc94  lea     rax, aCbrLret0l; "CBR(lRet == 0L)"
0x18001bc9b  mov     [rsp+58h+lpcbData], rax
0x18001bca0  mov     dword ptr [rsp+58h+lpData], 0FBh
0x18001bca8  jmp     short loc_18001BC64
0x18001bcaa  mov     dword ptr [rsp+58h+cbData], ebx
0x18001bcae  mov     [rsp+58h+Type], ebx
0x18001bcb2  lea     rax, [rsp+58h+cbData]
0x18001bcb7  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18001bcbc  mov     [rsp+58h+lpData], rbx; lpData
0x18001bcc1  lea     r9, [rsp+58h+Type]; lpType
0x18001bcc6  xor     r8d, r8d; lpReserved
0x18001bcc9  mov     rdx, r14; lpValueName
0x18001bccc  mov     rcx, [rsp+58h+hKey]; hKey
0x18001bcd1  call    cs:__imp_RegQueryValueExW
0x18001bcd7  mov     edi, eax
0x18001bcd9  test    eax, eax
0x18001bcdb  jz      short loc_18001BD0E
0x18001bcdd  jle     short loc_18001BCE8
0x18001bcdf  movzx   edi, ax
0x18001bce2  or      edi, 80070000h
0x18001bce8  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001bcef  jz      loc_18001BE1E
0x18001bcf5  lea     rax, aCbrLret0l; "CBR(lRet == 0L)"
0x18001bcfc  mov     [rsp+58h+lpcbData], rax
0x18001bd01  mov     dword ptr [rsp+58h+lpData], 109h
0x18001bd09  jmp     loc_18001BC64
0x18001bd0e  mov     eax, dword ptr [rsp+58h+cbData]
0x18001bd12  test    eax, eax
0x18001bd14  jz      loc_18001BE1C
0x18001bd1a  cmp     [rsp+58h+Type], 1
0x18001bd1f  jz      short loc_18001BD55
0x18001bd21  cmp     eax, 1
0x18001bd24  jbe     short loc_18001BD55
0x18001bd26  test    al, 1
0x18001bd28  jnz     short loc_18001BD55
0x18001bd2a  mov     edi, 80004005h
0x18001bd2f  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001bd36  jz      loc_18001BE1E
0x18001bd3c  lea     rax, aCbrDwtype1ulCb; "CBR(dwType == ( 1ul ) || cbSize <= 1 ||"...
0x18001bd43  mov     [rsp+58h+lpcbData], rax
0x18001bd48  mov     dword ptr [rsp+58h+lpData], 111h
0x18001bd50  jmp     loc_18001BC64
0x18001bd55  dec     eax
0x18001bd57  shr     eax, 1
0x18001bd59  mov     rdi, [rsi+10h]
0x18001bd5d  mov     r8d, eax
0x18001bd60  mov     rcx, rsi
0x18001bd63  cmp     r8, rdi
0x18001bd66  ja      short loc_18001BD78
0x18001bd68  mov     [rsi+10h], r8
0x18001bd6c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001bd71  mov     [rax+r8*2], bx
0x18001bd76  jmp     short loc_18001BDB8
0x18001bd78  mov     rdx, r8
0x18001bd7b  sub     rdx, rdi
0x18001bd7e  mov     rax, [rsi+18h]
0x18001bd82  sub     rax, rdi
0x18001bd85  cmp     rdx, rax
0x18001bd88  ja      short loc_18001BDAF
0x18001bd8a  mov     [rsi+10h], r8
0x18001bd8e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001bd93  mov     r9, rax
0x18001bd96  lea     rdi, [rax+rdi*2]
0x18001bd9a  test    rdx, rdx
0x18001bd9d  jz      short loc_18001BDA8
0x18001bd9f  movzx   eax, bx
0x18001bda2  mov     rcx, rdx
0x18001bda5  rep stosw
0x18001bda8  mov     [r9+r8*2], bx
0x18001bdad  jmp     short loc_18001BDB8
0x18001bdaf  mov     r9, rdx
0x18001bdb2  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x18001bdb7  nop
0x18001bdb8  mov     rcx, rsi
0x18001bdbb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001bdc0  lea     rcx, [rsp+58h+cbData]
0x18001bdc5  mov     [rsp+58h+lpcbData], rcx; lpcbData
0x18001bdca  mov     [rsp+58h+lpData], rax; lpData
0x18001bdcf  xor     r9d, r9d; lpType
0x18001bdd2  xor     r8d, r8d; lpReserved
0x18001bdd5  mov     rdx, r14; lpValueName
0x18001bdd8  mov     rcx, [rsp+58h+hKey]; hKey
0x18001bddd  call    cs:__imp_RegQueryValueExW
0x18001bde3  mov     edi, eax
0x18001bde5  test    eax, eax
0x18001bde7  jz      short loc_18001BE1C
0x18001bde9  jle     short loc_18001BDF4
0x18001bdeb  movzx   edi, ax
0x18001bdee  or      edi, 80070000h
0x18001bdf4  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18001bdfb  jz      short loc_18001BE1E
0x18001bdfd  lea     rax, aCbrLret0l; "CBR(lRet == 0L)"
0x18001be04  mov     [rsp+58h+lpcbData], rax
0x18001be09  mov     dword ptr [rsp+58h+lpData], 127h
0x18001be11  jmp     loc_18001BC64
0x18001be16  mov     edi, [rsp+58h+var_28]
0x18001be1a  jmp     short loc_18001BE1E
0x18001be1c  mov     edi, ebx
0x18001be1e  mov     rcx, [rsp+58h+hKey]; hKey
0x18001be23  test    rcx, rcx
0x18001be26  jz      short loc_18001BE2E
0x18001be28  call    cs:__imp_RegCloseKey
0x18001be2e  mov     eax, edi
0x18001be30  mov     rbx, [rsp+58h+arg_8]
0x18001be35  add     rsp, 40h
0x18001be39  pop     r14
0x18001be3b  pop     rdi
0x18001be3c  pop     rsi
0x18001be3d  retn
```
