# OcxDllRegisterServer

- ea: `0x180085eec`
- end: `0x180086275`
- name: `OcxDllRegisterServer`
- size: `905`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180072d10`

## callees

- `0x180012750`
- `0x180085cbc`
- `0x180085eec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180085f83`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180086015`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180085f83`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180086015`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180085fd7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18008604b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180086099`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180085fd7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18008604b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180086099`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800860a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800860b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800860c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800860ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800860d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180086102`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800860a9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800860b3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800860c4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800860ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800860d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180086102`

## string_xrefs

- `0x180086084`: `ThreadingModel`
- `0x180086029`: `oleaut32.dll`
- `0x180085f0b`: `CLSID`

## pseudocode

```c
__int64 __fastcall OcxDllRegisterServer(HKEY a1, int a2)
{
  int v2; // ebx
  const BYTE *v3; // rsi
  unsigned int i; // edi
  __int64 v5; // rax
  const BYTE *v6; // rcx
  const wchar_t *v7; // rax
  __int64 v8; // rax
  __int64 result; // rax
  __int64 v10; // r8
  unsigned int v11; // ebx
  __int64 v12; // r10
  __int64 v13; // r11
  __int64 v14; // r15
  __int64 v15; // r14
  __int64 v16; // r12
  __int64 v17; // r13
  _QWORD *v18; // rdi
  __int64 j; // rsi
  __int64 v20; // r9
  _QWORD *v21; // rdx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  HKEY v29; // [rsp+A8h] [rbp+50h] BYREF
  HKEY phkResult; // [rsp+B0h] [rbp+58h] BYREF
  HKEY hKey; // [rsp+B8h] [rbp+60h] BYREF

  hKey = 0;
  phkResult = 0;
  v29 = 0;
  v2 = OpenClassesRootKeyExW(L"CLSID", a2, &hKey);
  if ( v2 )
  {
LABEL_19:
    if ( v2 > 0 )
      return (unsigned __int16)v2 | 0x80070000;
    return (unsigned int)v2;
  }
  else
  {
    v3 = L"Both";
    for ( i = 0; i < 0xA; ++i )
    {
      v2 = RegCreateKeyExW(hKey, rgwszOACLSID[i], 0, 0, 0, 0x2000000u, 0, &phkResult, 0);
      if ( v2 )
        goto LABEL_18;
      v5 = -1;
      v6 = (const BYTE *)(rgwszOACLSID[i] + 39);
      do
        ++v5;
      while ( *(_WORD *)&v6[2 * v5] );
      v2 = RegSetValueExW(phkResult, &g_wszNull, 0, 1u, v6, 2 * v5 + 2);
      if ( v2 )
        goto LABEL_17;
      v2 = RegCreateKeyExW(phkResult, L"InprocServer32", 0, 0, 0, 0x2000000u, 0, &v29, 0);
      if ( v2 )
        goto LABEL_17;
      v2 = RegSetValueExW(v29, &g_wszNull, 0, 1u, L"oleaut32.dll", 0x1Au);
      if ( v2 )
        goto LABEL_16;
      v7 = L"Apartment";
      if ( i < 9 )
        v7 = (const wchar_t *)v3;
      v3 = (const BYTE *)v7;
      v8 = -1;
      do
        ++v8;
      while ( *(_WORD *)&v3[2 * v8] );
      v2 = RegSetValueExW(v29, L"ThreadingModel", 0, 1u, v3, 2 * v8 + 2);
      if ( v2 )
      {
LABEL_16:
        RegCloseKey(v29);
LABEL_17:
        RegCloseKey(phkResult);
LABEL_18:
        RegCloseKey(hKey);
        goto LABEL_19;
      }
      RegCloseKey(v29);
      RegCloseKey(phkResult);
    }
    RegCloseKey(hKey);
    v10 = *(_QWORD *)IID_IErrorInfo.Data4;
    v11 = 0;
    v12 = *(_QWORD *)&IID_IErrorInfo.Data1;
    v13 = *(_QWORD *)IID_ICreateErrorInfo.Data4;
    v14 = *(_QWORD *)IID_IPropertyBag.Data4;
    v15 = *(_QWORD *)&IID_ICreateErrorInfo.Data1;
    v16 = *(_QWORD *)&IID_IPropertyBag.Data1;
    v17 = *(_QWORD *)IID_IPropertyBag2.Data4;
    while ( v11 < 3 )
    {
      v18 = (_QWORD *)*((_QWORD *)&aProxyFileList + v11);
      if ( !v18 )
        break;
      for ( j = 0; *(_QWORD *)(*v18 + 8 * j); j = (unsigned int)(j + 1) )
      {
        v20 = *(_QWORD *)(v18[1] + 8 * j);
        v21 = *(_QWORD **)v20;
        if ( v11 )
          goto LABEL_47;
        v22 = *v21 - v12;
        if ( *v21 == v12 )
          v22 = v21[1] - v10;
        if ( !v22 )
          goto LABEL_47;
        v23 = *v21 - v15;
        if ( *v21 == v15 )
          v23 = v21[1] - v13;
        if ( !v23 )
          goto LABEL_47;
        v24 = *v21 - v16;
        if ( *v21 == v16 )
          v24 = v21[1] - v14;
        if ( !v24 )
          goto LABEL_47;
        v25 = *v21 - *(_QWORD *)&IID_IPropertyBag2.Data1;
        if ( *v21 == *(_QWORD *)&IID_IPropertyBag2.Data1 )
          v25 = v21[1] - v17;
        if ( !v25 )
          goto LABEL_47;
        v26 = *v21 - *(_QWORD *)&IID_IPersistPropertyBag2.Data1;
        if ( *v21 == *(_QWORD *)&IID_IPersistPropertyBag2.Data1 )
          v26 = v21[1] - *(_QWORD *)IID_IPersistPropertyBag2.Data4;
        if ( !v26 )
          goto LABEL_47;
        v27 = *v21 - *(_QWORD *)&IID_IErrorLog.Data1;
        if ( *v21 == *(_QWORD *)&IID_IErrorLog.Data1 )
          v27 = v21[1] - *(_QWORD *)IID_IErrorLog.Data4;
        if ( !v27 )
        {
LABEL_47:
          result = NdrpRegisterInterface(a1, (__int64)v21, *(const BYTE **)(v18[2] + 8 * j), v20, *(_DWORD *)(v20 + 16));
          if ( (int)result < 0 )
            return result;
          v10 = *(_QWORD *)IID_IErrorInfo.Data4;
          v12 = *(_QWORD *)&IID_IErrorInfo.Data1;
          v13 = *(_QWORD *)IID_ICreateErrorInfo.Data4;
          v15 = *(_QWORD *)&IID_ICreateErrorInfo.Data1;
          v14 = *(_QWORD *)IID_IPropertyBag.Data4;
          v16 = *(_QWORD *)&IID_IPropertyBag.Data1;
          v17 = *(_QWORD *)IID_IPropertyBag2.Data4;
        }
      }
      ++v11;
    }
    return 0;
  }
}

```

## disassembly

```asm
0x180085eec  mov     [rsp-40h+arg_0], rcx
0x180085ef1  push    rbp
0x180085ef2  push    rbx
0x180085ef3  push    rsi
0x180085ef4  push    rdi
0x180085ef5  push    r12
0x180085ef7  push    r13
0x180085ef9  push    r14
0x180085efb  push    r15
0x180085efd  mov     rbp, rsp
0x180085f00  sub     rsp, 58h
0x180085f04  xor     r15d, r15d
0x180085f07  lea     r8, [rbp+hKey]
0x180085f0b  lea     rcx, aClsid; "CLSID"
0x180085f12  mov     [rbp+hKey], r15
0x180085f16  mov     [rbp+arg_10], r15
0x180085f1a  mov     [rbp+arg_8], r15
0x180085f1e  call    OpenClassesRootKeyExW
0x180085f23  mov     ebx, eax
0x180085f25  test    eax, eax
0x180085f27  jnz     loc_1800860DE
0x180085f2d  lea     rsi, aBoth; "Both"
0x180085f34  mov     edi, r15d
0x180085f37  mov     r13d, 2000000h
0x180085f3d  or      r12, 0FFFFFFFFFFFFFFFFh
0x180085f41  lea     rcx, __ImageBase
0x180085f48  cmp     edi, 0Ah
0x180085f4b  jnb     loc_1800860FE
0x180085f51  mov     [rsp+58h+lpdwDisposition], r15; lpdwDisposition
0x180085f56  lea     rax, [rbp+arg_10]
0x180085f5a  mov     [rsp+58h+phkResult], rax; phkResult
0x180085f5f  xor     r9d, r9d; lpClass
0x180085f62  mov     [rsp+58h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180085f67  xor     r8d, r8d; Reserved
0x180085f6a  mov     r14d, edi
0x180085f6d  mov     [rsp+58h+samDesired], r13d; samDesired
0x180085f72  mov     [rsp+58h+dwOptions], r15d; dwOptions
0x180085f77  mov     rdx, ds:rva rgwszOACLSID[rcx+r14*8]; lpSubKey
0x180085f7f  mov     rcx, [rbp+hKey]; hKey
0x180085f83  call    cs:__imp_RegCreateKeyExW
0x180085f89  mov     ebx, eax
0x180085f8b  test    eax, eax
0x180085f8d  jnz     loc_1800860D4
0x180085f93  lea     rax, __ImageBase
0x180085f9a  mov     rcx, ds:rva rgwszOACLSID[rax+r14*8]
0x180085fa2  mov     rax, r12
0x180085fa5  add     rcx, 4Eh ; 'N'
0x180085fa9  inc     rax
0x180085fac  cmp     [rcx+rax*2], r15w
0x180085fb1  jnz     short loc_180085FA9
0x180085fb3  lea     eax, ds:2[rax*2]
0x180085fba  mov     r9d, 1; dwType
0x180085fc0  mov     [rsp+58h+samDesired], eax; cbData
0x180085fc4  lea     rdx, g_wszNull; lpValueName
0x180085fcb  mov     qword ptr [rsp+58h+dwOptions], rcx; lpData
0x180085fd0  xor     r8d, r8d; Reserved
0x180085fd3  mov     rcx, [rbp+arg_10]; hKey
0x180085fd7  call    cs:__imp_RegSetValueExW
0x180085fdd  mov     ebx, eax
0x180085fdf  test    eax, eax
0x180085fe1  jnz     loc_1800860CA
0x180085fe7  mov     rcx, [rbp+arg_10]; hKey
0x180085feb  lea     rax, [rbp+arg_8]
0x180085fef  mov     [rsp+58h+lpdwDisposition], r15; lpdwDisposition
0x180085ff4  lea     rdx, aInprocserver32; "InprocServer32"
0x180085ffb  mov     [rsp+58h+phkResult], rax; phkResult
0x180086000  xor     r9d, r9d; lpClass
0x180086003  mov     [rsp+58h+lpSecurityAttributes], r15; lpSecurityAttributes
0x180086008  xor     r8d, r8d; Reserved
0x18008600b  mov     [rsp+58h+samDesired], r13d; samDesired
0x180086010  mov     [rsp+58h+dwOptions], r15d; dwOptions
0x180086015  call    cs:__imp_RegCreateKeyExW
0x18008601b  mov     ebx, eax
0x18008601d  test    eax, eax
0x18008601f  jnz     loc_1800860CA
0x180086025  mov     rcx, [rbp+arg_8]; hKey
0x180086029  lea     rax, wszDllFileName; "oleaut32.dll"
0x180086030  mov     [rsp+58h+samDesired], 1Ah; cbData
0x180086038  lea     r9d, [rbx+1]; dwType
0x18008603c  xor     r8d, r8d; Reserved
0x18008603f  mov     qword ptr [rsp+58h+dwOptions], rax; lpData
0x180086044  lea     rdx, g_wszNull; lpValueName
0x18008604b  call    cs:__imp_RegSetValueExW
0x180086051  mov     ebx, eax
0x180086053  test    eax, eax
0x180086055  jnz     short loc_1800860C0
0x180086057  cmp     edi, 9
0x18008605a  lea     rax, aApartment; "Apartment"
0x180086061  cmovb   rax, rsi
0x180086065  mov     rsi, rax
0x180086068  mov     rax, r12
0x18008606b  inc     rax
0x18008606e  cmp     [rsi+rax*2], r15w
0x180086073  jnz     short loc_18008606B
0x180086075  mov     rcx, [rbp+arg_8]; hKey
0x180086079  lea     eax, ds:2[rax*2]
0x180086080  mov     [rsp+58h+samDesired], eax; cbData
0x180086084  lea     rdx, aThreadingmodel; "ThreadingModel"
0x18008608b  mov     r9d, 1; dwType
0x180086091  mov     qword ptr [rsp+58h+dwOptions], rsi; lpData
0x180086096  xor     r8d, r8d; Reserved
0x180086099  call    cs:__imp_RegSetValueExW
0x18008609f  mov     ebx, eax
0x1800860a1  test    eax, eax
0x1800860a3  jnz     short loc_1800860C0
0x1800860a5  mov     rcx, [rbp+arg_8]; hKey
0x1800860a9  call    cs:__imp_RegCloseKey
0x1800860af  mov     rcx, [rbp+arg_10]; hKey
0x1800860b3  call    cs:__imp_RegCloseKey
0x1800860b9  inc     edi
0x1800860bb  jmp     loc_180085F41
0x1800860c0  mov     rcx, [rbp+arg_8]; hKey
0x1800860c4  call    cs:__imp_RegCloseKey
0x1800860ca  mov     rcx, [rbp+arg_10]; hKey
0x1800860ce  call    cs:__imp_RegCloseKey
0x1800860d4  mov     rcx, [rbp+hKey]; hKey
0x1800860d8  call    cs:__imp_RegCloseKey
0x1800860de  test    ebx, ebx
0x1800860e0  jle     short loc_1800860EB
0x1800860e2  movzx   ebx, bx
0x1800860e5  or      ebx, 80070000h
0x1800860eb  mov     eax, ebx
0x1800860ed  add     rsp, 58h
0x1800860f1  pop     r15
0x1800860f3  pop     r14
0x1800860f5  pop     r13
0x1800860f7  pop     r12
0x1800860f9  pop     rdi
0x1800860fa  pop     rsi
0x1800860fb  pop     rbx
0x1800860fc  pop     rbp
0x1800860fd  retn
0x1800860fe  mov     rcx, [rbp+hKey]; hKey
0x180086102  call    cs:__imp_RegCloseKey
0x180086108  mov     r8, qword ptr cs:IID_IErrorInfo.Data4
0x18008610f  mov     ebx, r15d
0x180086112  mov     r10, qword ptr cs:IID_IErrorInfo.Data1
0x180086119  mov     r11, qword ptr cs:IID_ICreateErrorInfo.Data4
0x180086120  mov     r15, qword ptr cs:IID_IPropertyBag.Data4
0x180086127  mov     r14, qword ptr cs:IID_ICreateErrorInfo.Data1
0x18008612e  mov     r12, qword ptr cs:IID_IPropertyBag.Data1
0x180086135  mov     r13, qword ptr cs:IID_IPropertyBag2.Data4
0x18008613c  cmp     ebx, 3
0x18008613f  jnb     loc_18008626E
0x180086145  mov     eax, ebx
0x180086147  lea     rcx, __ImageBase
0x18008614e  mov     rdi, ds:rva aProxyFileList[rcx+rax*8]
0x180086156  test    rdi, rdi
0x180086159  jz      loc_18008626E
0x18008615f  xor     esi, esi
0x180086161  mov     rax, [rdi]
0x180086164  cmp     qword ptr [rax+rsi*8], 0
0x180086169  jz      loc_180086267
0x18008616f  mov     rax, [rdi+8]
0x180086173  mov     r9, [rax+rsi*8]
0x180086177  mov     rdx, [r9]
0x18008617a  test    ebx, ebx
0x18008617c  jnz     loc_18008620E
0x180086182  mov     rax, [rdx]
0x180086185  sub     rax, r10
0x180086188  jnz     short loc_180086191
0x18008618a  mov     rax, [rdx+8]
0x18008618e  sub     rax, r8
0x180086191  test    rax, rax
0x180086194  jz      short loc_18008620E
0x180086196  mov     rax, [rdx]
0x180086199  sub     rax, r14
0x18008619c  jnz     short loc_1800861A5
0x18008619e  mov     rax, [rdx+8]
0x1800861a2  sub     rax, r11
0x1800861a5  test    rax, rax
0x1800861a8  jz      short loc_18008620E
0x1800861aa  mov     rax, [rdx]
0x1800861ad  sub     rax, r12
0x1800861b0  jnz     short loc_1800861B9
0x1800861b2  mov     rax, [rdx+8]
0x1800861b6  sub     rax, r15
0x1800861b9  test    rax, rax
0x1800861bc  jz      short loc_18008620E
0x1800861be  mov     rax, [rdx]
0x1800861c1  sub     rax, qword ptr cs:IID_IPropertyBag2.Data1
0x1800861c8  jnz     short loc_1800861D1
0x1800861ca  mov     rax, [rdx+8]
0x1800861ce  sub     rax, r13
0x1800861d1  test    rax, rax
0x1800861d4  jz      short loc_18008620E
0x1800861d6  mov     rax, [rdx]
0x1800861d9  sub     rax, qword ptr cs:IID_IPersistPropertyBag2.Data1
0x1800861e0  jnz     short loc_1800861ED
0x1800861e2  mov     rax, [rdx+8]
0x1800861e6  sub     rax, qword ptr cs:IID_IPersistPropertyBag2.Data4
0x1800861ed  test    rax, rax
0x1800861f0  jz      short loc_18008620E
0x1800861f2  mov     rax, [rdx]
0x1800861f5  sub     rax, qword ptr cs:IID_IErrorLog.Data1
0x1800861fc  jnz     short loc_180086209
0x1800861fe  mov     rax, [rdx+8]
0x180086202  sub     rax, qword ptr cs:IID_IErrorLog.Data4
0x180086209  test    rax, rax
0x18008620c  jnz     short loc_180086260
0x18008620e  mov     r8, [rdi+10h]
0x180086212  mov     eax, [r9+10h]
0x180086216  mov     rcx, [rbp+arg_0]; hKey
0x18008621a  mov     [rsp+58h+dwOptions], eax; int
0x18008621e  mov     r8, [r8+rsi*8]
0x180086222  call    NdrpRegisterInterface
0x180086227  test    eax, eax
0x180086229  js      loc_1800860ED
0x18008622f  mov     r8, qword ptr cs:IID_IErrorInfo.Data4
0x180086236  mov     r10, qword ptr cs:IID_IErrorInfo.Data1
0x18008623d  mov     r11, qword ptr cs:IID_ICreateErrorInfo.Data4
0x180086244  mov     r14, qword ptr cs:IID_ICreateErrorInfo.Data1
0x18008624b  mov     r15, qword ptr cs:IID_IPropertyBag.Data4
0x180086252  mov     r12, qword ptr cs:IID_IPropertyBag.Data1
0x180086259  mov     r13, qword ptr cs:IID_IPropertyBag2.Data4
0x180086260  inc     esi
0x180086262  jmp     loc_180086161
0x180086267  inc     ebx
0x180086269  jmp     loc_18008613C
0x18008626e  xor     eax, eax
0x180086270  jmp     loc_1800860ED
```
