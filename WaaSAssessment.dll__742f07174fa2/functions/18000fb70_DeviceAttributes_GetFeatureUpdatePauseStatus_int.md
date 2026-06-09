# DeviceAttributes::GetFeatureUpdatePauseStatus(int &)

- ea: `0x18000fb70`
- end: `0x18000fcc6`
- name: `?GetFeatureUpdatePauseStatus@DeviceAttributes@@UEAAJAEAH@Z`
- size: `342`
- prototype: `__int64 __fastcall(DeviceAttributes *__hidden this, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000fb70`
- `0x18001752c`
- `0x180018ca8`
- `0x180019290`
- `0x1800194f4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000fba3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000fba3`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000fc76`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000fc88`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000fc76`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000fc88`

## string_xrefs

- `0x18000fc38`: `Feature Update Pause Start Time - %s`
- `0x18000fc60`: `Feature Update Pause End Time - %s`
- `0x18000fc92`: `Feature Updates are Paused`

## pseudocode

```c
__int64 __fastcall DeviceAttributes::GetFeatureUpdatePauseStatus(DeviceAttributes *this, int *a2)
{
  int v3; // ebx
  int v4; // r8d
  wchar_t *v5; // rsi
  wchar_t *v6; // r14
  int v7; // r8d
  FILETIME FileTime2; // [rsp+20h] [rbp-10h] BYREF
  FILETIME v10; // [rsp+28h] [rbp-8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+68h] [rbp+38h] BYREF
  struct tagEnterprisePolicyValue_V1 *v12; // [rsp+70h] [rbp+40h] BYREF
  struct tagEnterprisePolicyValue_V1 *v13; // [rsp+78h] [rbp+48h] BYREF

  v12 = 0;
  v13 = 0;
  SystemTimeAsFileTime = 0;
  *a2 = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v3 = ReadEnterprisePolicyValueWrapper(14, &v12);
  if ( v3 >= 0 )
  {
    v3 = ReadEnterprisePolicyValueWrapper(16, &v13);
    if ( v3 >= 0
      && *((_DWORD *)v12 + 1) == 1
      && *((_WORD *)v12 + 8) == 8
      && *((_DWORD *)v13 + 1) == 1
      && *((_WORD *)v13 + 8) == 8 )
    {
      FileTime2 = 0;
      v10 = 0;
      v5 = (wchar_t *)*((_QWORD *)v12 + 3);
      v6 = (wchar_t *)*((_QWORD *)v13 + 3);
      v3 = StringToFileTime(v5, &FileTime2, v4);
      if ( v3 >= 0 )
      {
        LogLevel(5u, L"Feature Update Pause Start Time - %s", v5);
        v3 = StringToFileTime(v6, &v10, v7);
        if ( v3 >= 0 )
        {
          LogLevel(5u, L"Feature Update Pause End Time - %s", v6);
          if ( CompareFileTime(&SystemTimeAsFileTime, &FileTime2) >= 0
            && CompareFileTime(&SystemTimeAsFileTime, &v10) < 0 )
          {
            *a2 = 1;
            LogLevel(4u, L"Feature Updates are Paused");
          }
        }
      }
    }
  }
  ReleaseEnterprisePolicyValueWrapper(&v12);
  ReleaseEnterprisePolicyValueWrapper(&v13);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18000fb70  push    rbp
0x18000fb72  push    rbx
0x18000fb73  push    rsi
0x18000fb74  push    rdi
0x18000fb75  push    r14
0x18000fb77  mov     rbp, rsp
0x18000fb7a  sub     rsp, 30h
0x18000fb7e  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000fb82  mov     [rbp+arg_10], 0
0x18000fb8a  mov     rdi, rdx
0x18000fb8d  mov     [rbp+arg_18], 0
0x18000fb95  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18000fb9d  mov     dword ptr [rdx], 0
0x18000fba3  call    cs:__imp_GetSystemTimeAsFileTime
0x18000fba9  lea     rdx, [rbp+arg_10]
0x18000fbad  mov     ecx, 0Eh
0x18000fbb2  call    ?ReadEnterprisePolicyValueWrapper@@YAJW4tagEnterprisePolicy@@PEAPEAUtagEnterprisePolicyValue_V1@@@Z; ReadEnterprisePolicyValueWrapper(tagEnterprisePolicy,tagEnterprisePolicyValue_V1 * *)
0x18000fbb7  mov     ebx, eax
0x18000fbb9  test    eax, eax
0x18000fbbb  js      loc_18000FCA7
0x18000fbc1  lea     rdx, [rbp+arg_18]
0x18000fbc5  mov     ecx, 10h
0x18000fbca  call    ?ReadEnterprisePolicyValueWrapper@@YAJW4tagEnterprisePolicy@@PEAPEAUtagEnterprisePolicyValue_V1@@@Z; ReadEnterprisePolicyValueWrapper(tagEnterprisePolicy,tagEnterprisePolicyValue_V1 * *)
0x18000fbcf  mov     ebx, eax
0x18000fbd1  test    eax, eax
0x18000fbd3  js      loc_18000FCA7
0x18000fbd9  mov     rax, [rbp+arg_10]
0x18000fbdd  cmp     dword ptr [rax+4], 1
0x18000fbe1  jnz     loc_18000FCA7
0x18000fbe7  cmp     word ptr [rax+10h], 8
0x18000fbec  jnz     loc_18000FCA7
0x18000fbf2  mov     rcx, [rbp+arg_18]
0x18000fbf6  cmp     dword ptr [rcx+4], 1
0x18000fbfa  jnz     loc_18000FCA7
0x18000fc00  cmp     word ptr [rcx+10h], 8
0x18000fc05  jnz     loc_18000FCA7
0x18000fc0b  mov     qword ptr [rbp+FileTime2.dwLowDateTime], 0
0x18000fc13  lea     rdx, [rbp+FileTime2]; struct _FILETIME *
0x18000fc17  mov     qword ptr [rbp+var_8.dwLowDateTime], 0
0x18000fc1f  mov     rsi, [rax+18h]
0x18000fc23  mov     r14, [rcx+18h]
0x18000fc27  mov     rcx, rsi; String
0x18000fc2a  call    ?StringToFileTime@@YAJPEBGPEAU_FILETIME@@H@Z; StringToFileTime(ushort const *,_FILETIME *,int)
0x18000fc2f  mov     ebx, eax
0x18000fc31  test    eax, eax
0x18000fc33  js      short loc_18000FCA7
0x18000fc35  mov     r8, rsi
0x18000fc38  lea     rdx, aFeatureUpdateP; "Feature Update Pause Start Time - %s"
0x18000fc3f  mov     esi, 5
0x18000fc44  mov     ecx, esi; unsigned __int8
0x18000fc46  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x18000fc4b  lea     rdx, [rbp+var_8]; struct _FILETIME *
0x18000fc4f  mov     rcx, r14; String
0x18000fc52  call    ?StringToFileTime@@YAJPEBGPEAU_FILETIME@@H@Z; StringToFileTime(ushort const *,_FILETIME *,int)
0x18000fc57  mov     ebx, eax
0x18000fc59  test    eax, eax
0x18000fc5b  js      short loc_18000FCA7
0x18000fc5d  mov     r8, r14
0x18000fc60  lea     rdx, aFeatureUpdateP_0; "Feature Update Pause End Time - %s"
0x18000fc67  mov     ecx, esi; unsigned __int8
0x18000fc69  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x18000fc6e  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x18000fc72  lea     rcx, [rbp+SystemTimeAsFileTime]; lpFileTime1
0x18000fc76  call    cs:__imp_CompareFileTime
0x18000fc7c  test    eax, eax
0x18000fc7e  js      short loc_18000FCA7
0x18000fc80  lea     rdx, [rbp+var_8]; lpFileTime2
0x18000fc84  lea     rcx, [rbp+SystemTimeAsFileTime]; lpFileTime1
0x18000fc88  call    cs:__imp_CompareFileTime
0x18000fc8e  test    eax, eax
0x18000fc90  jns     short loc_18000FCA7
0x18000fc92  lea     rdx, aFeatureUpdates; "Feature Updates are Paused"
0x18000fc99  mov     dword ptr [rdi], 1
0x18000fc9f  lea     ecx, [rsi-1]; unsigned __int8
0x18000fca2  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x18000fca7  lea     rcx, [rbp+arg_10]; struct tagEnterprisePolicyValue_V1 **
0x18000fcab  call    ?ReleaseEnterprisePolicyValueWrapper@@YAJPEAPEAUtagEnterprisePolicyValue_V1@@@Z; ReleaseEnterprisePolicyValueWrapper(tagEnterprisePolicyValue_V1 * *)
0x18000fcb0  lea     rcx, [rbp+arg_18]; struct tagEnterprisePolicyValue_V1 **
0x18000fcb4  call    ?ReleaseEnterprisePolicyValueWrapper@@YAJPEAPEAUtagEnterprisePolicyValue_V1@@@Z; ReleaseEnterprisePolicyValueWrapper(tagEnterprisePolicyValue_V1 * *)
0x18000fcb9  mov     eax, ebx
0x18000fcbb  add     rsp, 30h
0x18000fcbf  pop     r14
0x18000fcc1  pop     rdi
0x18000fcc2  pop     rsi
0x18000fcc3  pop     rbx
0x18000fcc4  pop     rbp
0x18000fcc5  retn
```
