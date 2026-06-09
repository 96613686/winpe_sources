# GetStorageDevices

- ea: `0x180007ef8`
- end: `0x1800081d1`
- name: `GetStorageDevices`
- size: `729`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x1800071b0`

## callees

- `0x180001c80`
- `0x180002802`
- `0x180002ab8`
- `0x18000694c`
- `0x180007bd4`
- `0x180007ef8`
- `0x180008374`
- `0x18000e7e0`
- `0x18000e7ec`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180008101`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180008101`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800080b7`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800080b7`
- `ZTrace_Maps!ZTraceReportIgnoreNoThis` at `0x180008002`
- `ZTrace_Maps!ZTraceReportIgnoreNoThis` at `0x180008002`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000811a`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180008185`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000811a`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x180008185`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180007f8f`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x180007f8f`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18000806f`
- `ZTrace_Maps!ZTraceHelperNoThis` at `0x18000806f`
- `ext-ms-win-storage-sense-l1-1-0!GetStorageDeviceInfo` at `0x180007fe9`
- `ext-ms-win-storage-sense-l1-1-0!GetStorageDeviceInfo` at `0x180007fe9`
- `ext-ms-win-storage-sense-l1-1-0!GetStorageInstanceCountForMaps` at `0x180007f76`
- `ext-ms-win-storage-sense-l1-1-0!GetStorageInstanceCountForMaps` at `0x180007f76`

## string_xrefs

- `0x180008111`: `GetExternalMosCacheDirectory`

## pseudocode

```c
__int64 __fastcall GetStorageDevices(__int64 a1, unsigned int a2)
{
  unsigned int v4; // ebx
  int v5; // r8d
  int StorageInstanceCountForMaps; // eax
  int v7; // r8d
  unsigned int v8; // eax
  unsigned int v9; // esi
  unsigned int i; // r15d
  int StorageDeviceInfo; // eax
  HRESULT v12; // eax
  __int64 v13; // rdx
  unsigned int v15; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v16; // [rsp+34h] [rbp-CCh]
  unsigned int Src; // [rsp+40h] [rbp-C0h] BYREF
  int v18; // [rsp+44h] [rbp-BCh]
  int v19; // [rsp+48h] [rbp-B8h]
  WCHAR pszPathOut[260]; // [rsp+4Ch] [rbp-B4h] BYREF
  unsigned int v21; // [rsp+254h] [rbp+154h]
  int v22; // [rsp+258h] [rbp+158h] BYREF
  WCHAR pszPathIn[262]; // [rsp+25Ch] [rbp+15Ch] BYREF
  int v24; // [rsp+468h] [rbp+368h]
  _BYTE Buf1[548]; // [rsp+47Ch] [rbp+37Ch] BYREF
  int v26; // [rsp+6A0h] [rbp+5A0h]
  int v27; // [rsp+6A8h] [rbp+5A8h]

  v15 = 0;
  v4 = 0;
  v16 = 0;
  if ( qword_1800184A8 )
  {
    v4 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)qword_1800184A8 + 24LL))(qword_1800184A8, 2);
    v16 = v4;
  }
  if ( !(unsigned __int8)IsSelectStorageVolumeExPresent() )
  {
    v5 = 306;
    goto LABEL_35;
  }
  StorageInstanceCountForMaps = GetStorageInstanceCountForMaps(a2, &v15);
  if ( StorageInstanceCountForMaps < 0 )
  {
    v7 = 307;
LABEL_7:
    v8 = ZTraceReportPropagationNoThis(StorageInstanceCountForMaps, "GetStorageDevices", v7);
    goto LABEL_36;
  }
  v9 = 0;
  for ( i = 0; i < v15; ++i )
  {
    memset_0(&Src, 0, 0x670u);
    v24 = 2;
    v22 = 1112;
    if ( !(unsigned __int8)IsSelectStorageVolumeExPresent() )
    {
      v5 = 318;
LABEL_35:
      v8 = ZTraceReportOriginationNoThis(-2147024769, "GetStorageDevices", v5);
LABEL_36:
      v9 = v8;
      break;
    }
    StorageDeviceInfo = GetStorageDeviceInfo(a2, i, &v22);
    if ( StorageDeviceInfo < 0 )
      ZTraceReportIgnoreNoThis(StorageDeviceInfo, "GetStorageDevices", 319);
    if ( (unsigned __int8)IsStorageDeviceMountedAndHasAPath(&v22) && (a2 != 1 || v26 == 12) )
    {
      if ( !memcmp_0(Buf1, &GUID_NULL, 0x10u) )
      {
        ZTraceHelperNoThis(
          0,
          "GetStorageDevices",
          331,
          "StorageId is invalid. Skipping storage. Type: %d | Instance: %lu",
          a2,
          v15);
      }
      else if ( (v27 & 0x2000) == 0 )
      {
        Src = i;
        v21 = a2;
        v19 = 0;
        if ( !a2 && !i )
        {
          v18 = 1;
LABEL_24:
          StorageInstanceCountForMaps = GetInternalMosCacheDirectory(pszPathOut, 0x104u);
          if ( StorageInstanceCountForMaps < 0 )
          {
            v7 = 360;
            goto LABEL_7;
          }
          goto LABEL_28;
        }
        v18 = 0;
        if ( a2 )
          goto LABEL_26;
        if ( !(unsigned __int8)RtlIsStateSeparationEnabled() )
        {
          if ( v18 )
            goto LABEL_24;
LABEL_26:
          v12 = PathCchCombine(pszPathOut, 0x104u, pszPathIn, L"MapData\\");
          if ( v12 < 0 )
          {
            StorageInstanceCountForMaps = ZTraceReportOriginationNoThis(v12, "GetExternalMosCacheDirectory", 166);
            if ( StorageInstanceCountForMaps < 0 )
            {
              v7 = 356;
              goto LABEL_7;
            }
          }
LABEL_28:
          v13 = *(_QWORD *)(a1 + 8);
          if ( v13 == *(_QWORD *)(a1 + 16) )
          {
            std::vector<_STORAGE_DEVICE_DATA>::_Emplace_reallocate<_STORAGE_DEVICE_DATA const &>(a1, v13, &Src);
          }
          else
          {
            memcpy_0(*(void **)(a1 + 8), &Src, 0x670u);
            *(_QWORD *)(a1 + 8) += 1648LL;
          }
        }
      }
    }
  }
  if ( qword_1800184A8 )
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)qword_1800184A8 + 24LL))(qword_1800184A8, v4);
  return v9;
}

```

## disassembly

```asm
0x180007ef8  mov     [rsp-8+arg_10], rbx
0x180007efd  push    rbp
0x180007efe  push    rsi
0x180007eff  push    r13
0x180007f01  push    r14
0x180007f03  push    r15
0x180007f05  lea     rbp, [rsp-5C0h]
0x180007f0d  sub     rsp, 6C0h
0x180007f14  mov     rax, cs:__security_cookie
0x180007f1b  xor     rax, rsp
0x180007f1e  mov     [rbp+5E0h+var_30], rax
0x180007f25  mov     r14d, edx
0x180007f28  mov     r13, rcx
0x180007f2b  mov     [rsp+6E0h+var_6B0], 0
0x180007f33  xor     ebx, ebx
0x180007f35  mov     [rsp+6E0h+var_6AC], ebx
0x180007f39  mov     rcx, cs:qword_1800184A8
0x180007f40  test    rcx, rcx
0x180007f43  jz      short loc_180007F5A
0x180007f45  mov     rax, [rcx]
0x180007f48  lea     edx, [rbx+2]
0x180007f4b  mov     rax, [rax+18h]
0x180007f4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f54  mov     ebx, eax
0x180007f56  mov     [rsp+6E0h+var_6AC], eax
0x180007f5a  call    IsSelectStorageVolumeExPresent
0x180007f5f  test    al, al
0x180007f61  jnz     short loc_180007F6E
0x180007f63  mov     r8d, 132h
0x180007f69  jmp     loc_180008179
0x180007f6e  lea     rdx, [rsp+6E0h+var_6B0]
0x180007f73  mov     ecx, r14d
0x180007f76  call    cs:__imp_GetStorageInstanceCountForMaps
0x180007f7c  test    eax, eax
0x180007f7e  jns     short loc_180007F9A
0x180007f80  mov     r8d, 133h
0x180007f86  lea     rdx, aGetstoragedevi_2; "GetStorageDevices"
0x180007f8d  mov     ecx, eax
0x180007f8f  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x180007f95  jmp     loc_18000818B
0x180007f9a  xor     esi, esi
0x180007f9c  xor     r15d, r15d
0x180007f9f  cmp     [rsp+6E0h+var_6B0], esi
0x180007fa3  jbe     loc_18000818D
0x180007fa9  xor     edx, edx; Val
0x180007fab  mov     r8d, 670h; Size
0x180007fb1  lea     rcx, [rsp+6E0h+Src]; void *
0x180007fb6  call    memset_0
0x180007fbb  mov     [rbp+5E0h+var_278], 2
0x180007fc5  mov     [rbp+5E0h+var_488], 458h
0x180007fcf  call    IsSelectStorageVolumeExPresent
0x180007fd4  test    al, al
0x180007fd6  jz      loc_180008173
0x180007fdc  lea     r8, [rbp+5E0h+var_488]
0x180007fe3  mov     edx, r15d
0x180007fe6  mov     ecx, r14d
0x180007fe9  call    cs:__imp_GetStorageDeviceInfo
0x180007fef  test    eax, eax
0x180007ff1  jns     short loc_180008008
0x180007ff3  mov     r8d, 13Fh
0x180007ff9  lea     rdx, aGetstoragedevi_2; "GetStorageDevices"
0x180008000  mov     ecx, eax
0x180008002  call    cs:__imp_?ZTraceReportIgnoreNoThis@@YAXHPEBDH@Z; ZTraceReportIgnoreNoThis(int,char const *,int)
0x180008008  lea     rcx, [rbp+5E0h+var_488]
0x18000800f  call    IsStorageDeviceMountedAndHasAPath
0x180008014  test    al, al
0x180008016  jz      loc_180008158
0x18000801c  cmp     r14d, 1
0x180008020  jnz     short loc_18000802F
0x180008022  cmp     [rbp+5E0h+var_40], 0Ch
0x180008029  jnz     loc_180008158
0x18000802f  mov     r8d, 10h; Size
0x180008035  lea     rdx, GUID_NULL; Buf2
0x18000803c  lea     rcx, [rbp+5E0h+Buf1]; Buf1
0x180008043  call    memcmp_0
0x180008048  test    eax, eax
0x18000804a  jnz     short loc_18000807A
0x18000804c  mov     eax, [rsp+6E0h+var_6B0]
0x180008050  mov     [rsp+6E0h+var_6B8], eax
0x180008054  mov     [rsp+6E0h+var_6C0], r14d
0x180008059  lea     r9, aStorageidIsInv; "StorageId is invalid. Skipping storage."...
0x180008060  mov     r8d, 14Bh
0x180008066  lea     rdx, aGetstoragedevi_2; "GetStorageDevices"
0x18000806d  xor     ecx, ecx
0x18000806f  call    cs:__imp_?ZTraceHelperNoThis@@YAXW4ZTraceLevel@@PEBDH1ZZ; ZTraceHelperNoThis(ZTraceLevel,char const *,int,char const *,...)
0x180008075  jmp     loc_180008158
0x18000807a  test    [rbp+5E0h+var_38], 2000h
0x180008084  jnz     loc_180008158
0x18000808a  mov     [rsp+6E0h+Src], r15d
0x18000808f  mov     [rbp+5E0h+var_48C], r14d
0x180008096  mov     [rsp+6E0h+var_698], esi
0x18000809a  test    r14d, r14d
0x18000809d  jnz     short loc_1800080AE
0x18000809f  test    r15d, r15d
0x1800080a2  jnz     short loc_1800080AE
0x1800080a4  mov     [rsp+6E0h+var_69C], 1
0x1800080ac  jmp     short loc_1800080CB
0x1800080ae  mov     [rsp+6E0h+var_69C], esi
0x1800080b2  test    r14d, r14d
0x1800080b5  jnz     short loc_1800080E9
0x1800080b7  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800080bd  test    al, al
0x1800080bf  jnz     loc_180008158
0x1800080c5  cmp     [rsp+6E0h+var_69C], esi
0x1800080c9  jz      short loc_1800080E9
0x1800080cb  mov     edx, 104h; cchPathOut
0x1800080d0  lea     rcx, [rsp+6E0h+pszPathOut]; pszPathOut
0x1800080d5  call    GetInternalMosCacheDirectory
0x1800080da  test    eax, eax
0x1800080dc  jns     short loc_180008124
0x1800080de  mov     r8d, 168h
0x1800080e4  jmp     loc_180007F86
0x1800080e9  lea     r9, pszMore; "MapData\\"
0x1800080f0  lea     r8, [rbp+5E0h+pszPathIn]; pszPathIn
0x1800080f7  mov     edx, 104h; cchPathOut
0x1800080fc  lea     rcx, [rsp+6E0h+pszPathOut]; pszPathOut
0x180008101  call    cs:__imp_PathCchCombine
0x180008107  test    eax, eax
0x180008109  jns     short loc_180008124
0x18000810b  mov     r8d, 0A6h
0x180008111  lea     rdx, aGetexternalmos; "GetExternalMosCacheDirectory"
0x180008118  mov     ecx, eax
0x18000811a  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x180008120  test    eax, eax
0x180008122  js      short loc_180008168
0x180008124  mov     rdx, [r13+8]
0x180008128  cmp     rdx, [r13+10h]
0x18000812c  jz      short loc_18000814B
0x18000812e  mov     rcx, rdx; void *
0x180008131  lea     rdx, [rsp+6E0h+Src]; Src
0x180008136  mov     r8d, 670h; Size
0x18000813c  call    memcpy_0
0x180008141  add     qword ptr [r13+8], 670h
0x180008149  jmp     short loc_180008158
0x18000814b  lea     r8, [rsp+6E0h+Src]
0x180008150  mov     rcx, r13
0x180008153  call    ??$_Emplace_reallocate@AEBU_STORAGE_DEVICE_DATA@@@?$vector@U_STORAGE_DEVICE_DATA@@V?$allocator@U_STORAGE_DEVICE_DATA@@@std@@@std@@AEAAPEAU_STORAGE_DEVICE_DATA@@QEAU2@AEBU2@@Z; std::vector<_STORAGE_DEVICE_DATA>::_Emplace_reallocate<_STORAGE_DEVICE_DATA const &>(_STORAGE_DEVICE_DATA * const,_STORAGE_DEVICE_DATA const &)
0x180008158  inc     r15d
0x18000815b  cmp     r15d, [rsp+6E0h+var_6B0]
0x180008160  jb      loc_180007FA9
0x180008166  jmp     short loc_18000818D
0x180008168  mov     r8d, 164h
0x18000816e  jmp     loc_180007F86
0x180008173  mov     r8d, 13Eh
0x180008179  lea     rdx, aGetstoragedevi_2; "GetStorageDevices"
0x180008180  mov     ecx, 8007007Fh
0x180008185  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18000818b  mov     esi, eax
0x18000818d  mov     rcx, cs:qword_1800184A8
0x180008194  test    rcx, rcx
0x180008197  jz      short loc_1800081A8
0x180008199  mov     rax, [rcx]
0x18000819c  mov     edx, ebx
0x18000819e  mov     rax, [rax+18h]
0x1800081a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081a7  nop
0x1800081a8  mov     eax, esi
0x1800081aa  mov     rcx, [rbp+5E0h+var_30]
0x1800081b1  xor     rcx, rsp; StackCookie
0x1800081b4  call    __security_check_cookie
0x1800081b9  mov     rbx, [rsp+6E0h+arg_10]
0x1800081c1  add     rsp, 6C0h
0x1800081c8  pop     r15
0x1800081ca  pop     r14
0x1800081cc  pop     r13
0x1800081ce  pop     rsi
0x1800081cf  pop     rbp
0x1800081d0  retn
```
