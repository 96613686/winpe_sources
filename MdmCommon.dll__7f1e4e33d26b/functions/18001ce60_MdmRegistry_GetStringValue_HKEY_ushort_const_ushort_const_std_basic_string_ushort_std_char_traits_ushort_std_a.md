# MdmRegistry::GetStringValue(HKEY__ *,ushort const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001ce60`
- end: `0x18001d0c9`
- name: `?GetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `617`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, const WCHAR *, _QWORD *)`
- caller_count: `11`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800036c0`
- `0x18001142c`
- `0x180011a78`
- `0x180012038`
- `0x180012578`
- `0x1800126e0`
- `0x180012848`
- `0x180012a24`
- `0x180012cd0`
- `0x180012e38`
- `0x180012e9c`

## callees

- `0x180006548`
- `0x18001c9ac`
- `0x18001ce60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001cf49`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d06c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001cf49`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d06c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d0b7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d0b7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ce8a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ce8a`

## string_xrefs

- `0x18001ced6`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmregistry.cpp`

## pseudocode

```c
__int64 __fastcall MdmRegistry::GetStringValue(HKEY a1, const WCHAR *a2, const WCHAR *a3, _QWORD *a4)
{
  int v6; // edx
  int v7; // ecx
  int v8; // edi
  _WORD *v9; // rax
  LSTATUS v10; // eax
  DWORD v11; // eax
  unsigned __int64 v12; // rdi
  __int64 v13; // rdx
  _QWORD *v14; // rax
  unsigned __int64 v15; // rcx
  _QWORD *v16; // r8
  _WORD *v17; // rdi
  LSTATUS v18; // eax
  __int64 v20; // [rsp+0h] [rbp-68h] BYREF
  PHKEY phkResult; // [rsp+20h] [rbp-48h]
  LPDWORD lpcbData; // [rsp+28h] [rbp-40h]
  DWORD Type; // [rsp+30h] [rbp-38h] BYREF
  int v24; // [rsp+34h] [rbp-34h]
  HKEY hKey; // [rsp+38h] [rbp-30h] BYREF
  DWORD cbData; // [rsp+88h] [rbp+20h] BYREF

  hKey = 0;
  v8 = RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey);
  a4[2] = 0;
  if ( a4[3] <= 7u )
    v9 = a4;
  else
    v9 = (_WORD *)*a4;
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    *v9 = 0;
    if ( (unsigned int)(v8 - 2) <= 1 )
    {
      v8 = -2147023728;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) == 0 )
        goto LABEL_54;
      lpcbData = (LPDWORD)"CBR(lRet != 2L && lRet != 3L)";
      LODWORD(phkResult) = 360;
      goto LABEL_7;
    }
    if ( v8 )
    {
      if ( v8 > 0 )
        v8 = (unsigned __int16)v8 | 0x80070000;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        lpcbData = (LPDWORD)"CBR(lRet == 0L)";
        LODWORD(phkResult) = 361;
LABEL_7:
        McTemplateU0dsqs_EventWriteTransfer(
          v7,
          v6,
          v8,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmregistry.cpp",
          (char)phkResult,
          (const char *)lpcbData);
      }
    }
    else
    {
      cbData = 0;
      Type = 0;
      v10 = RegQueryValueExW(hKey, a3, 0, &Type, 0, &cbData);
      v8 = v10;
      if ( !v10 )
      {
        if ( cbData )
        {
          if ( Type != 1 && cbData > 1 && (cbData & 1) == 0 )
          {
            v8 = -2147467259;
            if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
            {
              lpcbData = (LPDWORD)"CBR(dwType == ( 1ul ) || cbSize <= 1 || (cbSize & 0x1) != 0)";
              LODWORD(phkResult) = 383;
              goto LABEL_7;
            }
            goto LABEL_54;
          }
          v11 = (cbData - 1) >> 1;
          v12 = a4[2];
          v13 = v11;
          if ( v11 > v12 )
          {
            v15 = v11 - v12;
            if ( v15 > a4[3] - v12 )
            {
              std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,unsigned short>(a4);
            }
            else
            {
              a4[2] = v11;
              if ( a4[3] <= 7u )
                v16 = a4;
              else
                v16 = (_QWORD *)*a4;
              v17 = (_WORD *)v16 + v12;
              if ( v15 )
              {
                while ( v15 )
                {
                  *v17++ = 0;
                  --v15;
                }
              }
              *((_WORD *)v16 + v11) = 0;
            }
          }
          else
          {
            a4[2] = v11;
            if ( a4[3] <= 7u )
              v14 = a4;
            else
              v14 = (_QWORD *)*a4;
            *((_WORD *)v14 + v13) = 0;
          }
          if ( a4[3] > 7u )
            a4 = (_QWORD *)*a4;
          v18 = RegQueryValueExW(hKey, a3, 0, 0, (LPBYTE)a4, &cbData);
          v8 = v18;
          if ( v18 )
          {
            if ( v18 > 0 )
              v8 = (unsigned __int16)v18 | 0x80070000;
            if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
            {
              lpcbData = (LPDWORD)"CBR(lRet == 0L)";
              LODWORD(phkResult) = 405;
              goto LABEL_7;
            }
            goto LABEL_54;
          }
        }
        v8 = 0;
        goto LABEL_54;
      }
      if ( v10 > 0 )
        v8 = (unsigned __int16)v10 | 0x80070000;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
      {
        lpcbData = (LPDWORD)"CBR(lRet == 0L)";
        LODWORD(phkResult) = 375;
        goto LABEL_7;
      }
    }
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      v24 = -2147024882;
      if ( (Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v7,
          (unsigned int)&v20,
          -2147024882,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\mdmcommon\\lib\\mdmregistry.cpp",
          138,
          "CHR(((HRESULT)0x8007000EL))");
      v8 = v24;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18001D0A5);
    }
  }
LABEL_54:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001ce60  push    rbx
0x18001ce62  push    rsi
0x18001ce63  push    rdi
0x18001ce64  push    r14
0x18001ce66  sub     rsp, 48h
0x18001ce6a  mov     rsi, r9
0x18001ce6d  mov     r14, r8
0x18001ce70  xor     ebx, ebx
0x18001ce72  mov     [rsp+68h+hKey], rbx
0x18001ce77  lea     rax, [rsp+68h+hKey]
0x18001ce7c  mov     [rsp+68h+phkResult], rax; phkResult
0x18001ce81  mov     r9d, 20019h; samDesired
0x18001ce87  xor     r8d, r8d; ulOptions
0x18001ce8a  call    cs:__imp_RegOpenKeyExW
0x18001ce90  mov     edi, eax
0x18001ce92  mov     [rsi+10h], rbx
0x18001ce96  cmp     qword ptr [rsi+18h], 7
0x18001ce9b  jbe     short loc_18001CEA2
0x18001ce9d  mov     rax, [rsi]
0x18001cea0  jmp     short loc_18001CEA5
0x18001cea2  mov     rax, rsi
0x18001cea5  mov     [rax], bx
0x18001cea8  lea     eax, [rdi-2]
0x18001ceab  cmp     eax, 1
0x18001ceae  ja      short loc_18001CEEA
0x18001ceb0  mov     edi, 80070490h
0x18001ceb5  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001cebc  jz      loc_18001D0AD
0x18001cec2  lea     rax, aCbrLret2lLret3; "CBR(lRet != 2L && lRet != 3L)"
0x18001cec9  mov     [rsp+68h+lpcbData], rax
0x18001cece  mov     dword ptr [rsp+68h+phkResult], 168h
0x18001ced6  lea     r9, aOnecoreuapShel_0; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001cedd  mov     r8d, edi
0x18001cee0  call    McTemplateU0dsqs_EventWriteTransfer
0x18001cee5  jmp     loc_18001D0AD
0x18001ceea  test    edi, edi
0x18001ceec  jz      short loc_18001CF1C
0x18001ceee  jle     short loc_18001CEF9
0x18001cef0  movzx   edi, di
0x18001cef3  or      edi, 80070000h
0x18001cef9  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001cf00  jz      loc_18001D0AD
0x18001cf06  lea     rax, aCbrLret0l; "CBR(lRet == 0L)"
0x18001cf0d  mov     [rsp+68h+lpcbData], rax
0x18001cf12  mov     dword ptr [rsp+68h+phkResult], 169h
0x18001cf1a  jmp     short loc_18001CED6
0x18001cf1c  mov     [rsp+68h+cbData], ebx
0x18001cf23  mov     [rsp+68h+Type], ebx
0x18001cf27  lea     rax, [rsp+68h+cbData]
0x18001cf2f  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18001cf34  mov     [rsp+68h+phkResult], rbx; lpData
0x18001cf39  lea     r9, [rsp+68h+Type]; lpType
0x18001cf3e  xor     r8d, r8d; lpReserved
0x18001cf41  mov     rdx, r14; lpValueName
0x18001cf44  mov     rcx, [rsp+68h+hKey]; hKey
0x18001cf49  call    cs:__imp_RegQueryValueExW
0x18001cf4f  mov     edi, eax
0x18001cf51  test    eax, eax
0x18001cf53  jz      short loc_18001CF86
0x18001cf55  jle     short loc_18001CF60
0x18001cf57  movzx   edi, ax
0x18001cf5a  or      edi, 80070000h
0x18001cf60  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001cf67  jz      loc_18001D0AD
0x18001cf6d  lea     rax, aCbrLret0l; "CBR(lRet == 0L)"
0x18001cf74  mov     [rsp+68h+lpcbData], rax
0x18001cf79  mov     dword ptr [rsp+68h+phkResult], 177h
0x18001cf81  jmp     loc_18001CED6
0x18001cf86  mov     eax, [rsp+68h+cbData]
0x18001cf8d  test    eax, eax
0x18001cf8f  jz      loc_18001D0AB
0x18001cf95  cmp     [rsp+68h+Type], 1
0x18001cf9a  jz      short loc_18001CFD0
0x18001cf9c  cmp     eax, 1
0x18001cf9f  jbe     short loc_18001CFD0
0x18001cfa1  test    al, 1
0x18001cfa3  jnz     short loc_18001CFD0
0x18001cfa5  mov     edi, 80004005h
0x18001cfaa  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001cfb1  jz      loc_18001D0AD
0x18001cfb7  lea     rax, aCbrDwtype1ulCb; "CBR(dwType == ( 1ul ) || cbSize <= 1 ||"...
0x18001cfbe  mov     [rsp+68h+lpcbData], rax
0x18001cfc3  mov     dword ptr [rsp+68h+phkResult], 17Fh
0x18001cfcb  jmp     loc_18001CED6
0x18001cfd0  dec     eax
0x18001cfd2  shr     eax, 1
0x18001cfd4  mov     rdi, [rsi+10h]
0x18001cfd8  mov     edx, eax
0x18001cfda  cmp     rdx, rdi
0x18001cfdd  ja      short loc_18001CFF8
0x18001cfdf  mov     [rsi+10h], rdx
0x18001cfe3  cmp     qword ptr [rsi+18h], 7
0x18001cfe8  jbe     short loc_18001CFEF
0x18001cfea  mov     rax, [rsi]
0x18001cfed  jmp     short loc_18001CFF2
0x18001cfef  mov     rax, rsi
0x18001cff2  mov     [rax+rdx*2], bx
0x18001cff6  jmp     short loc_18001D042
0x18001cff8  mov     rcx, rdx
0x18001cffb  sub     rcx, rdi
0x18001cffe  mov     rax, [rsi+18h]
0x18001d002  sub     rax, rdi
0x18001d005  cmp     rcx, rax
0x18001d008  ja      short loc_18001D033
0x18001d00a  mov     [rsi+10h], rdx
0x18001d00e  cmp     qword ptr [rsi+18h], 7
0x18001d013  jbe     short loc_18001D01A
0x18001d015  mov     r8, [rsi]
0x18001d018  jmp     short loc_18001D01D
0x18001d01a  mov     r8, rsi
0x18001d01d  lea     rdi, [r8+rdi*2]
0x18001d021  test    rcx, rcx
0x18001d024  jz      short loc_18001D02C
0x18001d026  movzx   eax, bx
0x18001d029  rep stosw
0x18001d02c  mov     [r8+rdx*2], bx
0x18001d031  jmp     short loc_18001D042
0x18001d033  mov     r9, rcx
0x18001d036  mov     rdx, rcx
0x18001d039  mov     rcx, rsi; Src
0x18001d03c  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x18001d041  nop
0x18001d042  cmp     qword ptr [rsi+18h], 7
0x18001d047  jbe     short loc_18001D04C
0x18001d049  mov     rsi, [rsi]
0x18001d04c  lea     rax, [rsp+68h+cbData]
0x18001d054  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18001d059  mov     [rsp+68h+phkResult], rsi; lpData
0x18001d05e  xor     r9d, r9d; lpType
0x18001d061  xor     r8d, r8d; lpReserved
0x18001d064  mov     rdx, r14; lpValueName
0x18001d067  mov     rcx, [rsp+68h+hKey]; hKey
0x18001d06c  call    cs:__imp_RegQueryValueExW
0x18001d072  mov     edi, eax
0x18001d074  test    eax, eax
0x18001d076  jz      short loc_18001D0AB
0x18001d078  jle     short loc_18001D083
0x18001d07a  movzx   edi, ax
0x18001d07d  or      edi, 80070000h
0x18001d083  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001d08a  jz      short loc_18001D0AD
0x18001d08c  lea     rax, aCbrLret0l; "CBR(lRet == 0L)"
0x18001d093  mov     [rsp+68h+lpcbData], rax
0x18001d098  mov     dword ptr [rsp+68h+phkResult], 195h
0x18001d0a0  jmp     loc_18001CED6
0x18001d0a5  mov     edi, [rsp+68h+var_34]
0x18001d0a9  jmp     short loc_18001D0AD
0x18001d0ab  mov     edi, ebx
0x18001d0ad  mov     rcx, [rsp+68h+hKey]; hKey
0x18001d0b2  test    rcx, rcx
0x18001d0b5  jz      short loc_18001D0BD
0x18001d0b7  call    cs:__imp_RegCloseKey
0x18001d0bd  mov     eax, edi
0x18001d0bf  add     rsp, 48h
0x18001d0c3  pop     r14
0x18001d0c5  pop     rdi
0x18001d0c6  pop     rsi
0x18001d0c7  pop     rbx
0x18001d0c8  retn
```
