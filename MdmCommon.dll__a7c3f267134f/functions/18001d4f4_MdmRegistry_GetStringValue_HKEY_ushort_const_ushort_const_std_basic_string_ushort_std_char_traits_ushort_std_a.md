# MdmRegistry::GetStringValue(HKEY__ *,ushort const *,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001d4f4`
- end: `0x18001d776`
- name: `?GetStringValue@MdmRegistry@@SAJPEAUHKEY__@@PEBG1AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `642`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *, const WCHAR *, _QWORD *)`
- caller_count: `11`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800036d0`
- `0x180011800`
- `0x180011e50`
- `0x180012414`
- `0x180012954`
- `0x180012abc`
- `0x180012c24`
- `0x180012e08`
- `0x1800130b4`
- `0x18001321c`
- `0x180013280`

## callees

- `0x1800065c0`
- `0x18001d010`
- `0x18001d4f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d5e3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d70c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d5e3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d70c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d75d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d75d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d51e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d51e`

## string_xrefs

- `0x18001d570`: `onecoreuap\shell\devicedirectory\mdmcommon\lib\mdmregistry.cpp`

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
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18001D74B);
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
0x18001d4f4  push    rbx
0x18001d4f6  push    rsi
0x18001d4f7  push    rdi
0x18001d4f8  push    r14
0x18001d4fa  sub     rsp, 48h
0x18001d4fe  mov     rsi, r9
0x18001d501  mov     r14, r8
0x18001d504  xor     ebx, ebx
0x18001d506  mov     [rsp+68h+hKey], rbx
0x18001d50b  lea     rax, [rsp+68h+hKey]
0x18001d510  mov     [rsp+68h+phkResult], rax; phkResult
0x18001d515  mov     r9d, 20019h; samDesired
0x18001d51b  xor     r8d, r8d; ulOptions
0x18001d51e  call    cs:__imp_RegOpenKeyExW
0x18001d525  nop     dword ptr [rax+rax+00h]
0x18001d52a  mov     edi, eax
0x18001d52c  mov     [rsi+10h], rbx
0x18001d530  cmp     qword ptr [rsi+18h], 7
0x18001d535  jbe     short loc_18001D53C
0x18001d537  mov     rax, [rsi]
0x18001d53a  jmp     short loc_18001D53F
0x18001d53c  mov     rax, rsi
0x18001d53f  mov     [rax], bx
0x18001d542  lea     eax, [rdi-2]
0x18001d545  cmp     eax, 1
0x18001d548  ja      short loc_18001D584
0x18001d54a  mov     edi, 80070490h
0x18001d54f  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001d556  jz      loc_18001D753
0x18001d55c  lea     rax, aCbrLret2lLret3; "CBR(lRet != 2L && lRet != 3L)"
0x18001d563  mov     [rsp+68h+lpcbData], rax
0x18001d568  mov     dword ptr [rsp+68h+phkResult], 168h
0x18001d570  lea     r9, aOnecoreuapShel_0; "onecoreuap\\shell\\devicedirectory\\mdm"...
0x18001d577  mov     r8d, edi
0x18001d57a  call    McTemplateU0dsqs_EventWriteTransfer
0x18001d57f  jmp     loc_18001D753
0x18001d584  test    edi, edi
0x18001d586  jz      short loc_18001D5B6
0x18001d588  jle     short loc_18001D593
0x18001d58a  movzx   edi, di
0x18001d58d  or      edi, 80070000h
0x18001d593  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001d59a  jz      loc_18001D753
0x18001d5a0  lea     rax, aCbrLret0l; "CBR(lRet == 0L)"
0x18001d5a7  mov     [rsp+68h+lpcbData], rax
0x18001d5ac  mov     dword ptr [rsp+68h+phkResult], 169h
0x18001d5b4  jmp     short loc_18001D570
0x18001d5b6  mov     [rsp+68h+cbData], ebx
0x18001d5bd  mov     [rsp+68h+Type], ebx
0x18001d5c1  lea     rax, [rsp+68h+cbData]
0x18001d5c9  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18001d5ce  mov     [rsp+68h+phkResult], rbx; lpData
0x18001d5d3  lea     r9, [rsp+68h+Type]; lpType
0x18001d5d8  xor     r8d, r8d; lpReserved
0x18001d5db  mov     rdx, r14; lpValueName
0x18001d5de  mov     rcx, [rsp+68h+hKey]; hKey
0x18001d5e3  call    cs:__imp_RegQueryValueExW
0x18001d5ea  nop     dword ptr [rax+rax+00h]
0x18001d5ef  mov     edi, eax
0x18001d5f1  test    eax, eax
0x18001d5f3  jz      short loc_18001D626
0x18001d5f5  jle     short loc_18001D600
0x18001d5f7  movzx   edi, ax
0x18001d5fa  or      edi, 80070000h
0x18001d600  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001d607  jz      loc_18001D753
0x18001d60d  lea     rax, aCbrLret0l; "CBR(lRet == 0L)"
0x18001d614  mov     [rsp+68h+lpcbData], rax
0x18001d619  mov     dword ptr [rsp+68h+phkResult], 177h
0x18001d621  jmp     loc_18001D570
0x18001d626  mov     eax, [rsp+68h+cbData]
0x18001d62d  test    eax, eax
0x18001d62f  jz      loc_18001D751
0x18001d635  cmp     [rsp+68h+Type], 1
0x18001d63a  jz      short loc_18001D670
0x18001d63c  cmp     eax, 1
0x18001d63f  jbe     short loc_18001D670
0x18001d641  test    al, 1
0x18001d643  jnz     short loc_18001D670
0x18001d645  mov     edi, 80004005h
0x18001d64a  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001d651  jz      loc_18001D753
0x18001d657  lea     rax, aCbrDwtype1ulCb; "CBR(dwType == ( 1ul ) || cbSize <= 1 ||"...
0x18001d65e  mov     [rsp+68h+lpcbData], rax
0x18001d663  mov     dword ptr [rsp+68h+phkResult], 17Fh
0x18001d66b  jmp     loc_18001D570
0x18001d670  dec     eax
0x18001d672  shr     eax, 1
0x18001d674  mov     rdi, [rsi+10h]
0x18001d678  mov     edx, eax
0x18001d67a  cmp     rdx, rdi
0x18001d67d  ja      short loc_18001D698
0x18001d67f  mov     [rsi+10h], rdx
0x18001d683  cmp     qword ptr [rsi+18h], 7
0x18001d688  jbe     short loc_18001D68F
0x18001d68a  mov     rax, [rsi]
0x18001d68d  jmp     short loc_18001D692
0x18001d68f  mov     rax, rsi
0x18001d692  mov     [rax+rdx*2], bx
0x18001d696  jmp     short loc_18001D6E2
0x18001d698  mov     rcx, rdx
0x18001d69b  sub     rcx, rdi
0x18001d69e  mov     rax, [rsi+18h]
0x18001d6a2  sub     rax, rdi
0x18001d6a5  cmp     rcx, rax
0x18001d6a8  ja      short loc_18001D6D3
0x18001d6aa  mov     [rsi+10h], rdx
0x18001d6ae  cmp     qword ptr [rsi+18h], 7
0x18001d6b3  jbe     short loc_18001D6BA
0x18001d6b5  mov     r8, [rsi]
0x18001d6b8  jmp     short loc_18001D6BD
0x18001d6ba  mov     r8, rsi
0x18001d6bd  lea     rdi, [r8+rdi*2]
0x18001d6c1  test    rcx, rcx
0x18001d6c4  jz      short loc_18001D6CC
0x18001d6c6  movzx   eax, bx
0x18001d6c9  rep stosw
0x18001d6cc  mov     [r8+rdx*2], bx
0x18001d6d1  jmp     short loc_18001D6E2
0x18001d6d3  mov     r9, rcx
0x18001d6d6  mov     rdx, rcx
0x18001d6d9  mov     rcx, rsi; Src
0x18001d6dc  call    ??$_Reallocate_grow_by@V_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b70241e9b5ebaad244db3e52d52cab17_@@_KG@Z; std::wstring::_Reallocate_grow_by<_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort>(unsigned __int64,_lambda_b70241e9b5ebaad244db3e52d52cab17_,unsigned __int64,ushort)
0x18001d6e1  nop
0x18001d6e2  cmp     qword ptr [rsi+18h], 7
0x18001d6e7  jbe     short loc_18001D6EC
0x18001d6e9  mov     rsi, [rsi]
0x18001d6ec  lea     rax, [rsp+68h+cbData]
0x18001d6f4  mov     [rsp+68h+lpcbData], rax; lpcbData
0x18001d6f9  mov     [rsp+68h+phkResult], rsi; lpData
0x18001d6fe  xor     r9d, r9d; lpType
0x18001d701  xor     r8d, r8d; lpReserved
0x18001d704  mov     rdx, r14; lpValueName
0x18001d707  mov     rcx, [rsp+68h+hKey]; hKey
0x18001d70c  call    cs:__imp_RegQueryValueExW
0x18001d713  nop     dword ptr [rax+rax+00h]
0x18001d718  mov     edi, eax
0x18001d71a  test    eax, eax
0x18001d71c  jz      short loc_18001D751
0x18001d71e  jle     short loc_18001D729
0x18001d720  movzx   edi, ax
0x18001d723  or      edi, 80070000h
0x18001d729  test    byte ptr cs:Microsoft_Windows_DeviceDirectory_MdmCommon_ETWEnableBits, 1
0x18001d730  jz      short loc_18001D753
0x18001d732  lea     rax, aCbrLret0l; "CBR(lRet == 0L)"
0x18001d739  mov     [rsp+68h+lpcbData], rax
0x18001d73e  mov     dword ptr [rsp+68h+phkResult], 195h
0x18001d746  jmp     loc_18001D570
0x18001d74b  mov     edi, [rsp+68h+var_34]
0x18001d74f  jmp     short loc_18001D753
0x18001d751  mov     edi, ebx
0x18001d753  mov     rcx, [rsp+68h+hKey]; hKey
0x18001d758  test    rcx, rcx
0x18001d75b  jz      short loc_18001D769
0x18001d75d  call    cs:__imp_RegCloseKey
0x18001d764  nop     dword ptr [rax+rax+00h]
0x18001d769  mov     eax, edi
0x18001d76b  add     rsp, 48h
0x18001d76f  pop     r14
0x18001d771  pop     rdi
0x18001d772  pop     rsi
0x18001d773  pop     rbx
0x18001d774  retn
```
