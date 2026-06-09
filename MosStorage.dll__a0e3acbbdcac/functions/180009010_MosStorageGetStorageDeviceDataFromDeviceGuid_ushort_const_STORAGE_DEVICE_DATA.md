# MosStorageGetStorageDeviceDataFromDeviceGuid(ushort const *,_STORAGE_DEVICE_DATA *)

- ea: `0x180009010`
- end: `0x18000908f`
- name: `?MosStorageGetStorageDeviceDataFromDeviceGuid@@YAJPEBGPEAU_STORAGE_DEVICE_DATA@@@Z`
- size: `127`
- prototype: `int __fastcall(const unsigned __int16 *, struct _STORAGE_DEVICE_DATA *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000733c`
- `0x180009650`

## callees

- `0x180001c80`
- `0x180007c90`
- `0x180009010`

## import_xrefs

- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000904e`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000904e`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180009035`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180009035`

## pseudocode

```c
int __fastcall MosStorageGetStorageDeviceDataFromDeviceGuid(
        const unsigned __int16 *a1,
        struct _STORAGE_DEVICE_DATA *a2)
{
  int StorageDeviceDataFromDeviceGuid; // eax
  int v4; // r8d
  GUID v6; // [rsp+20h] [rbp-38h] BYREF
  GUID pclsid; // [rsp+30h] [rbp-28h] BYREF

  pclsid = 0;
  StorageDeviceDataFromDeviceGuid = CLSIDFromString(a1, &pclsid);
  if ( StorageDeviceDataFromDeviceGuid < 0 )
  {
    v4 = 548;
    return ZTraceReportPropagationNoThis(
             StorageDeviceDataFromDeviceGuid,
             "MosStorageGetStorageDeviceDataFromDeviceGuid",
             v4);
  }
  v6 = pclsid;
  StorageDeviceDataFromDeviceGuid = GetStorageDeviceDataFromDeviceGuid(&v6, a2);
  if ( StorageDeviceDataFromDeviceGuid < 0 )
  {
    v4 = 549;
    return ZTraceReportPropagationNoThis(
             StorageDeviceDataFromDeviceGuid,
             "MosStorageGetStorageDeviceDataFromDeviceGuid",
             v4);
  }
  return 0;
}

```

## disassembly

```asm
0x180009010  push    rbx
0x180009012  sub     rsp, 50h
0x180009016  mov     rax, cs:__security_cookie
0x18000901d  xor     rax, rsp
0x180009020  mov     [rsp+58h+var_18], rax
0x180009025  mov     rbx, rdx
0x180009028  xorps   xmm0, xmm0
0x18000902b  lea     rdx, [rsp+58h+pclsid]; pclsid
0x180009030  movups  xmmword ptr [rsp+58h+pclsid.Data1], xmm0
0x180009035  call    cs:__imp_CLSIDFromString
0x18000903b  test    eax, eax
0x18000903d  jns     short loc_180009056
0x18000903f  mov     r8d, 224h
0x180009045  lea     rdx, aMosstoragegets_2; "MosStorageGetStorageDeviceDataFromDevic"...
0x18000904c  mov     ecx, eax
0x18000904e  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180009054  jmp     short loc_18000907C
0x180009056  movaps  xmm0, xmmword ptr [rsp+58h+pclsid.Data1]
0x18000905b  lea     rcx, [rsp+58h+var_38]
0x180009060  mov     rdx, rbx
0x180009063  movdqa  [rsp+58h+var_38], xmm0
0x180009069  call    GetStorageDeviceDataFromDeviceGuid
0x18000906e  test    eax, eax
0x180009070  jns     short loc_18000907A
0x180009072  mov     r8d, 225h
0x180009078  jmp     short loc_180009045
0x18000907a  xor     eax, eax
0x18000907c  mov     rcx, [rsp+58h+var_18]
0x180009081  xor     rcx, rsp; StackCookie
0x180009084  call    __security_check_cookie
0x180009089  add     rsp, 50h
0x18000908d  pop     rbx
0x18000908e  retn
```
