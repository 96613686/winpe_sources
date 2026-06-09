# HttpAddFragmentToCache

- ea: `0x180008170`
- end: `0x180008267`
- name: `HttpAddFragmentToCache`
- size: `247`
- prototype: `ULONG __stdcall(HANDLE RequestQueueHandle, PCWSTR UrlPrefix, PHTTP_DATA_CHUNK DataChunk, PHTTP_CACHE_POLICY CachePolicy, LPOVERLAPPED Overlapped)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180002940`
- `0x180008170`
- `0x18000b424`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800081c6`
- `ntdll!RtlNtStatusToDosError` at `0x1800081c6`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800081ba`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800081ba`

## pseudocode

```c
ULONG __stdcall HttpAddFragmentToCache(
        HANDLE RequestQueueHandle,
        PCWSTR UrlPrefix,
        PHTTP_DATA_CHUNK DataChunk,
        PHTTP_CACHE_POLICY CachePolicy,
        LPOVERLAPPED Overlapped)
{
  int inited; // eax
  __int64 v9; // rcx
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int64 v13; // [rsp+20h] [rbp-68h]
  struct _UNICODE_STRING v14; // [rsp+40h] [rbp-48h] BYREF
  __int128 v15; // [rsp+50h] [rbp-38h]
  __int128 v16; // [rsp+60h] [rbp-28h]
  struct _HTTP_CACHE_POLICY v17; // [rsp+70h] [rbp-18h]

  v14 = 0;
  v15 = 0;
  v16 = 0;
  v17 = 0;
  if ( !DataChunk || !CachePolicy )
    return 87;
  inited = RtlInitUnicodeStringEx(&v14, UrlPrefix);
  if ( inited < 0 )
    return RtlNtStatusToDosError(inited);
  v11 = *(_OWORD *)&DataChunk->DataChunkType;
  v12 = *(_OWORD *)&DataChunk->FromFragmentCacheEx.ByteRange.Length.LowPart;
  v17 = *CachePolicy;
  v15 = v11;
  v16 = v12;
  if ( (byte_1800126A3 & 4) != 0 )
    WPP_SF_dL(
      v9,
      16,
      WPP_88109d8d3e5b32c3c016118f2408fbcf_Traceguids,
      (unsigned int)CachePolicy->Policy,
      CachePolicy->SecondsToLive);
  LODWORD(v13) = 56;
  return ((__int64 (__fastcall *)(HANDLE, LPOVERLAPPED, __int64, struct _UNICODE_STRING *, __int64, _QWORD, _DWORD, _QWORD))HttpApiDeviceControl)(
           RequestQueueHandle,
           Overlapped,
           1196120,
           &v14,
           v13,
           0,
           0,
           0);
}

```

## disassembly

```asm
0x180008170  mov     r11, rsp
0x180008173  mov     [r11+8], rbx
0x180008177  mov     [r11+10h], rsi
0x18000817b  push    rdi
0x18000817c  sub     rsp, 80h
0x180008183  xorps   xmm0, xmm0
0x180008186  xor     eax, eax
0x180008188  mov     rbx, r9
0x18000818b  mov     rdi, r8
0x18000818e  mov     rsi, rcx
0x180008191  movups  [rsp+88h+var_48], xmm0
0x180008196  movups  [rsp+88h+var_38], xmm0
0x18000819b  movups  [rsp+88h+var_28], xmm0
0x1800081a0  mov     [r11-18h], rax
0x1800081a4  test    r8, r8
0x1800081a7  jz      loc_18000824D
0x1800081ad  test    rbx, rbx
0x1800081b0  jz      loc_18000824D
0x1800081b6  lea     rcx, [r11-48h]; DestinationString
0x1800081ba  call    cs:__imp_RtlInitUnicodeStringEx
0x1800081c0  test    eax, eax
0x1800081c2  jns     short loc_1800081D1
0x1800081c4  mov     ecx, eax; Status
0x1800081c6  call    cs:__imp_RtlNtStatusToDosError
0x1800081cc  jmp     loc_180008252
0x1800081d1  movups  xmm0, xmmword ptr [rdi]
0x1800081d4  mov     rax, [rbx]
0x1800081d7  movups  xmm1, xmmword ptr [rdi+10h]
0x1800081db  mov     [rsp+88h+var_18], rax
0x1800081e0  movups  [rsp+88h+var_38], xmm0
0x1800081e5  movups  [rsp+88h+var_28], xmm1
0x1800081ea  test    cs:byte_1800126A3, 4
0x1800081f1  jz      short loc_18000820E
0x1800081f3  mov     eax, [rbx+4]
0x1800081f6  lea     r8, WPP_88109d8d3e5b32c3c016118f2408fbcf_Traceguids
0x1800081fd  mov     r9d, [rbx]
0x180008200  mov     edx, 10h
0x180008205  mov     dword ptr [rsp+88h+var_68], eax
0x180008209  call    WPP_SF_dL
0x18000820e  mov     rdx, [rsp+88h+Overlapped]
0x180008216  lea     r9, [rsp+88h+var_48]
0x18000821b  mov     [rsp+88h+var_50], 0
0x180008224  mov     r8d, 124058h
0x18000822a  mov     [rsp+88h+var_58], 0
0x180008232  mov     rcx, rsi
0x180008235  mov     [rsp+88h+var_60], 0
0x18000823e  mov     dword ptr [rsp+88h+var_68], 38h ; '8'
0x180008246  call    HttpApiDeviceControl
0x18000824b  jmp     short loc_180008252
0x18000824d  mov     eax, 57h ; 'W'
0x180008252  lea     r11, [rsp+88h+var_8]
0x18000825a  mov     rbx, [r11+10h]
0x18000825e  mov     rsi, [r11+18h]
0x180008262  mov     rsp, r11
0x180008265  pop     rdi
0x180008266  retn
```
