# RegisterClassW(ushort const *,tagCLASS_DATA const *)

- ea: `0x1800b07a0`
- end: `0x1800b090d`
- name: `?RegisterClassW@@YAJPEBGPEBUtagCLASS_DATA@@@Z`
- size: `365`
- prototype: `HRESULT __fastcall(const wchar_t *pclassdata, const tagCLASS_DATA *wszDllName)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800b0a68`

## callees

- `0x180052390`
- `0x1800b0710`
- `0x1800b07a0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b08d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b08e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b08d4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b08e4`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800b07e5`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800b07e5`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x1800b07fa`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x1800b0895`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x1800b07fa`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x1800b0895`

## string_xrefs

- `0x1800b081b`: `CLSID`
- `0x1800b08b6`: `CLSID`

## pseudocode

```c
__int64 __fastcall RegisterClassW(const wchar_t *pclassdata, const tagCLASS_DATA *wszDllName)
{
  LSTATUS v3; // eax
  signed int v4; // ebx
  LSTATUS v5; // eax
  HKEY__ *hkGuid; // [rsp+20h] [rbp-19h] BYREF
  HKEY__ *hk; // [rsp+28h] [rbp-11h] BYREF
  wchar_t rgwchClsid[40]; // [rsp+30h] [rbp-9h] BYREF

  hk = (HKEY__ *)-1LL;
  hkGuid = (HKEY__ *)-1LL;
  StringFromGUID2(wszDllName->pclsid, rgwchClsid, 39);
  v3 = RegCreateKeyW(g_hkClsid, rgwchClsid, &hkGuid);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x80070000;
  if ( v4 >= 0 )
  {
    v4 = HrRegSetValueW(hkGuid, L"CLSID", wszDllName->wszName);
    if ( v4 >= 0 )
    {
      v4 = HrRegSetValueW(hkGuid, &value, wszDllName->wszName);
      if ( v4 >= 0 )
      {
        v4 = HrRegSetValueW(hkGuid, L"InprocServer32", wszDllFileName);
        if ( v4 >= 0 )
        {
          v4 = HrRegSetValueW(hkGuid, L"ProgID", wszDllName->wszProgId);
          if ( v4 >= 0 )
          {
            v5 = RegCreateKeyW(g_hkRoot, wszDllName->wszProgId, &hk);
            v4 = v5;
            if ( v5 > 0 )
              v4 = (unsigned __int16)v5 | 0x80070000;
            if ( v4 >= 0 )
            {
              v4 = HrRegSetValueW(hk, L"CLSID", rgwchClsid);
              if ( v4 >= 0 )
                v4 = 0;
            }
          }
        }
      }
    }
  }
  if ( hk != (HKEY__ *)-1LL )
    RegCloseKey(hk);
  if ( hkGuid != (HKEY__ *)-1LL )
    RegCloseKey(hkGuid);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800b07a0  mov     [rsp-8+arg_0], rbx
0x1800b07a5  mov     [rsp-8+arg_10], rdi
0x1800b07aa  push    rbp
0x1800b07ab  lea     rbp, [rsp-57h]
0x1800b07b0  sub     rsp, 90h
0x1800b07b7  mov     rax, cs:__security_cookie
0x1800b07be  xor     rax, rsp
0x1800b07c1  mov     [rbp+57h+var_10], rax
0x1800b07c5  mov     rdi, pclassdata
0x1800b07c8  mov     [rbp+57h+hk], 0FFFFFFFFFFFFFFFFh
0x1800b07d0  mov     r8d, 27h ; '''; cchMax
0x1800b07d6  mov     [rbp+57h+hkGuid], 0FFFFFFFFFFFFFFFFh
0x1800b07de  lea     pclassdata, [rbp+57h+rgwchClsid]; lpsz
0x1800b07e2  mov     rcx, [rdi]; rguid
0x1800b07e5  call    cs:__imp_StringFromGUID2
0x1800b07eb  mov     rcx, cs:?g_hkClsid@@3PEAUHKEY__@@EA; hKey
0x1800b07f2  lea     r8, [rbp+57h+hkGuid]; phkResult
0x1800b07f6  lea     pclassdata, [rbp+57h+rgwchClsid]; lpSubKey
0x1800b07fa  call    cs:__imp_RegCreateKeyW
0x1800b0800  mov     ebx, eax
0x1800b0802  test    eax, eax
0x1800b0804  jle     short loc_1800B080F
0x1800b0806  movzx   ebx, ax
0x1800b0809  or      ebx, 80070000h
0x1800b080f  test    ebx, ebx
0x1800b0811  js      $Error_7
0x1800b0817  mov     r8, [rdi+8]; wszVal
0x1800b081b  lea     pclassdata, aClsid_1; "CLSID"
0x1800b0822  mov     rcx, [rbp+57h+hkGuid]; hk
0x1800b0826  call    ?HrRegSetValueW@@YAJPEAUHKEY__@@PEBG1@Z; HrRegSetValueW(HKEY__ *,ushort const *,ushort const *)
0x1800b082b  mov     ebx, eax
0x1800b082d  test    eax, eax
0x1800b082f  js      $Error_7
0x1800b0835  mov     r8, [rdi+8]; wszVal
0x1800b0839  lea     pclassdata, value; wszSubKey
0x1800b0840  mov     rcx, [rbp+57h+hkGuid]; hk
0x1800b0844  call    ?HrRegSetValueW@@YAJPEAUHKEY__@@PEBG1@Z; HrRegSetValueW(HKEY__ *,ushort const *,ushort const *)
0x1800b0849  mov     ebx, eax
0x1800b084b  test    eax, eax
0x1800b084d  js      short $Error_7
0x1800b084f  mov     rcx, [rbp+57h+hkGuid]; hk
0x1800b0853  lea     r8, wszDllFileName; wszVal
0x1800b085a  lea     pclassdata, aInprocserver32; "InprocServer32"
0x1800b0861  call    ?HrRegSetValueW@@YAJPEAUHKEY__@@PEBG1@Z; HrRegSetValueW(HKEY__ *,ushort const *,ushort const *)
0x1800b0866  mov     ebx, eax
0x1800b0868  test    eax, eax
0x1800b086a  js      short $Error_7
0x1800b086c  mov     r8, [rdi+10h]; wszVal
0x1800b0870  lea     pclassdata, aProgid; "ProgID"
0x1800b0877  mov     rcx, [rbp+57h+hkGuid]; hk
0x1800b087b  call    ?HrRegSetValueW@@YAJPEAUHKEY__@@PEBG1@Z; HrRegSetValueW(HKEY__ *,ushort const *,ushort const *)
0x1800b0880  mov     ebx, eax
0x1800b0882  test    eax, eax
0x1800b0884  js      short $Error_7
0x1800b0886  mov     pclassdata, [rdi+10h]; lpSubKey
0x1800b088a  lea     r8, [rbp+57h+hk]; phkResult
0x1800b088e  mov     rcx, cs:?g_hkRoot@@3PEAUHKEY__@@EA; hKey
0x1800b0895  call    cs:__imp_RegCreateKeyW
0x1800b089b  mov     ebx, eax
0x1800b089d  test    eax, eax
0x1800b089f  jle     short loc_1800B08AA
0x1800b08a1  movzx   ebx, ax
0x1800b08a4  or      ebx, 80070000h
0x1800b08aa  test    ebx, ebx
0x1800b08ac  js      short $Error_7
0x1800b08ae  mov     rcx, [rbp+57h+hk]; hk
0x1800b08b2  lea     r8, [rbp+57h+rgwchClsid]; wszVal
0x1800b08b6  lea     pclassdata, aClsid_1; "CLSID"
0x1800b08bd  call    ?HrRegSetValueW@@YAJPEAUHKEY__@@PEBG1@Z; HrRegSetValueW(HKEY__ *,ushort const *,ushort const *)
0x1800b08c2  mov     ebx, eax
0x1800b08c4  test    eax, eax
0x1800b08c6  js      short $Error_7
0x1800b08c8  xor     ebx, ebx
0x1800b08ca  mov     rcx, [rbp+57h+hk]; hKey
0x1800b08ce  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800b08d2  jz      short loc_1800B08DA
0x1800b08d4  call    cs:__imp_RegCloseKey
0x1800b08da  mov     rcx, [rbp+57h+hkGuid]; hKey
0x1800b08de  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800b08e2  jz      short loc_1800B08EA
0x1800b08e4  call    cs:__imp_RegCloseKey
0x1800b08ea  mov     eax, ebx
0x1800b08ec  mov     rcx, [rbp+57h+var_10]
0x1800b08f0  xor     rcx, rsp; StackCookie
0x1800b08f3  call    __security_check_cookie
0x1800b08f8  lea     r11, [rsp+90h+var_s0]
0x1800b0900  mov     rbx, [r11+10h]
0x1800b0904  mov     rdi, [r11+20h]
0x1800b0908  mov     rsp, r11
0x1800b090b  pop     rbp
0x1800b090c  retn
```
