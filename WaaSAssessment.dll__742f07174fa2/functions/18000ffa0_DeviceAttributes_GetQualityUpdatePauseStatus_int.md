# DeviceAttributes::GetQualityUpdatePauseStatus(int &)

- ea: `0x18000ffa0`
- end: `0x1800100f6`
- name: `?GetQualityUpdatePauseStatus@DeviceAttributes@@UEAAJAEAH@Z`
- size: `342`
- prototype: `__int64 __fastcall(DeviceAttributes *__hidden this, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000ffa0`
- `0x18001752c`
- `0x180018ca8`
- `0x180019290`
- `0x1800194f4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000ffd3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000ffd3`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800100a6`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800100b8`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800100a6`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800100b8`

## string_xrefs

- `0x180010068`: `Quality Update Pause Start Time - %s`
- `0x180010090`: `Quality Update Pause End Time - %s`
- `0x1800100c2`: `Quality Updates are Paused`

## pseudocode

```c
__int64 __fastcall DeviceAttributes::GetQualityUpdatePauseStatus(DeviceAttributes *this, int *a2)
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
  v3 = ReadEnterprisePolicyValueWrapper(13, &v12);
  if ( v3 >= 0 )
  {
    v3 = ReadEnterprisePolicyValueWrapper(15, &v13);
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
        LogLevel(5u, L"Quality Update Pause Start Time - %s", v5);
        v3 = StringToFileTime(v6, &v10, v7);
        if ( v3 >= 0 )
        {
          LogLevel(5u, L"Quality Update Pause End Time - %s", v6);
          if ( CompareFileTime(&SystemTimeAsFileTime, &FileTime2) >= 0
            && CompareFileTime(&SystemTimeAsFileTime, &v10) < 0 )
          {
            *a2 = 1;
            LogLevel(4u, L"Quality Updates are Paused");
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
0x18000ffa0  push    rbp
0x18000ffa2  push    rbx
0x18000ffa3  push    rsi
0x18000ffa4  push    rdi
0x18000ffa5  push    r14
0x18000ffa7  mov     rbp, rsp
0x18000ffaa  sub     rsp, 30h
0x18000ffae  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000ffb2  mov     [rbp+arg_10], 0
0x18000ffba  mov     rdi, rdx
0x18000ffbd  mov     [rbp+arg_18], 0
0x18000ffc5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18000ffcd  mov     dword ptr [rdx], 0
0x18000ffd3  call    cs:__imp_GetSystemTimeAsFileTime
0x18000ffd9  lea     rdx, [rbp+arg_10]
0x18000ffdd  mov     ecx, 0Dh
0x18000ffe2  call    ?ReadEnterprisePolicyValueWrapper@@YAJW4tagEnterprisePolicy@@PEAPEAUtagEnterprisePolicyValue_V1@@@Z; ReadEnterprisePolicyValueWrapper(tagEnterprisePolicy,tagEnterprisePolicyValue_V1 * *)
0x18000ffe7  mov     ebx, eax
0x18000ffe9  test    eax, eax
0x18000ffeb  js      loc_1800100D7
0x18000fff1  lea     rdx, [rbp+arg_18]
0x18000fff5  mov     ecx, 0Fh
0x18000fffa  call    ?ReadEnterprisePolicyValueWrapper@@YAJW4tagEnterprisePolicy@@PEAPEAUtagEnterprisePolicyValue_V1@@@Z; ReadEnterprisePolicyValueWrapper(tagEnterprisePolicy,tagEnterprisePolicyValue_V1 * *)
0x18000ffff  mov     ebx, eax
0x180010001  test    eax, eax
0x180010003  js      loc_1800100D7
0x180010009  mov     rax, [rbp+arg_10]
0x18001000d  cmp     dword ptr [rax+4], 1
0x180010011  jnz     loc_1800100D7
0x180010017  cmp     word ptr [rax+10h], 8
0x18001001c  jnz     loc_1800100D7
0x180010022  mov     rcx, [rbp+arg_18]
0x180010026  cmp     dword ptr [rcx+4], 1
0x18001002a  jnz     loc_1800100D7
0x180010030  cmp     word ptr [rcx+10h], 8
0x180010035  jnz     loc_1800100D7
0x18001003b  mov     qword ptr [rbp+FileTime2.dwLowDateTime], 0
0x180010043  lea     rdx, [rbp+FileTime2]; struct _FILETIME *
0x180010047  mov     qword ptr [rbp+var_8.dwLowDateTime], 0
0x18001004f  mov     rsi, [rax+18h]
0x180010053  mov     r14, [rcx+18h]
0x180010057  mov     rcx, rsi; String
0x18001005a  call    ?StringToFileTime@@YAJPEBGPEAU_FILETIME@@H@Z; StringToFileTime(ushort const *,_FILETIME *,int)
0x18001005f  mov     ebx, eax
0x180010061  test    eax, eax
0x180010063  js      short loc_1800100D7
0x180010065  mov     r8, rsi
0x180010068  lea     rdx, aQualityUpdateP_0; "Quality Update Pause Start Time - %s"
0x18001006f  mov     esi, 5
0x180010074  mov     ecx, esi; unsigned __int8
0x180010076  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x18001007b  lea     rdx, [rbp+var_8]; struct _FILETIME *
0x18001007f  mov     rcx, r14; String
0x180010082  call    ?StringToFileTime@@YAJPEBGPEAU_FILETIME@@H@Z; StringToFileTime(ushort const *,_FILETIME *,int)
0x180010087  mov     ebx, eax
0x180010089  test    eax, eax
0x18001008b  js      short loc_1800100D7
0x18001008d  mov     r8, r14
0x180010090  lea     rdx, aQualityUpdateP; "Quality Update Pause End Time - %s"
0x180010097  mov     ecx, esi; unsigned __int8
0x180010099  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x18001009e  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x1800100a2  lea     rcx, [rbp+SystemTimeAsFileTime]; lpFileTime1
0x1800100a6  call    cs:__imp_CompareFileTime
0x1800100ac  test    eax, eax
0x1800100ae  js      short loc_1800100D7
0x1800100b0  lea     rdx, [rbp+var_8]; lpFileTime2
0x1800100b4  lea     rcx, [rbp+SystemTimeAsFileTime]; lpFileTime1
0x1800100b8  call    cs:__imp_CompareFileTime
0x1800100be  test    eax, eax
0x1800100c0  jns     short loc_1800100D7
0x1800100c2  lea     rdx, aQualityUpdates; "Quality Updates are Paused"
0x1800100c9  mov     dword ptr [rdi], 1
0x1800100cf  lea     ecx, [rsi-1]; unsigned __int8
0x1800100d2  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x1800100d7  lea     rcx, [rbp+arg_10]; struct tagEnterprisePolicyValue_V1 **
0x1800100db  call    ?ReleaseEnterprisePolicyValueWrapper@@YAJPEAPEAUtagEnterprisePolicyValue_V1@@@Z; ReleaseEnterprisePolicyValueWrapper(tagEnterprisePolicyValue_V1 * *)
0x1800100e0  lea     rcx, [rbp+arg_18]; struct tagEnterprisePolicyValue_V1 **
0x1800100e4  call    ?ReleaseEnterprisePolicyValueWrapper@@YAJPEAPEAUtagEnterprisePolicyValue_V1@@@Z; ReleaseEnterprisePolicyValueWrapper(tagEnterprisePolicyValue_V1 * *)
0x1800100e9  mov     eax, ebx
0x1800100eb  add     rsp, 30h
0x1800100ef  pop     r14
0x1800100f1  pop     rdi
0x1800100f2  pop     rsi
0x1800100f3  pop     rbx
0x1800100f4  pop     rbp
0x1800100f5  retn
```
