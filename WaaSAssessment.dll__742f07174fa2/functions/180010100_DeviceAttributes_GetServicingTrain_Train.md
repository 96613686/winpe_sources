# DeviceAttributes::GetServicingTrain(Train &)

- ea: `0x180010100`
- end: `0x180010412`
- name: `?GetServicingTrain@DeviceAttributes@@UEAAJAEAW4Train@@@Z`
- size: `786`
- prototype: `__int64 __fastcall(DeviceAttributes *__hidden this, enum Train *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x180010100`
- `0x18001752c`
- `0x18001972e`
- `0x180019760`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010162`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010162`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180010210`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180010210`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x180010236`
- `api-ms-win-core-sysinfo-l1-2-0!GetProductInfo` at `0x180010236`

## pseudocode

```c
__int64 __fastcall DeviceAttributes::GetServicingTrain(DeviceAttributes *this, enum Train *a2)
{
  HRESULT v4; // ebx
  __int16 v5; // cx
  __int16 v6; // ax
  DWORD v7; // eax
  DWORD v8; // eax
  DWORD v9; // eax
  DWORD v10; // eax
  DWORD v11; // eax
  bool v12; // zf
  DWORD v13; // eax
  bool v14; // zf
  DWORD v15; // eax
  bool v16; // zf
  bool v17; // zf
  DWORD v18; // eax
  bool v19; // zf
  DWORD v20; // eax
  DWORD v21; // eax
  DWORD v22; // eax
  DWORD v23; // eax
  DWORD v24; // eax
  DWORD v25; // eax
  DWORD v26; // eax
  DWORD v27; // eax
  DWORD v28; // eax
  DWORD v29; // eax
  DWORD v30; // eax
  DWORD v31; // eax
  DWORD v32; // eax
  DWORD v33; // eax
  LPVOID v34; // rcx
  __int16 v36[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int16 v37; // [rsp+34h] [rbp-CCh] BYREF
  DWORD pdwReturnedProductType; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-C0h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v41; // [rsp+164h] [rbp+64h]
  unsigned __int16 v42; // [rsp+166h] [rbp+66h]

  v36[0] = 0;
  ppv = 0;
  v37 = -1;
  v4 = CoCreateInstance(&CLSID_FlightSettingsAPIBroker, 0, 1u, &GUID_e833feb2_c58a_45e4_8d93_08874744febb, &ppv);
  if ( v4 < 0
    || (v4 = (*(__int64 (__fastcall **)(LPVOID, __int16 *))(*(_QWORD *)ppv + 24LL))(ppv, v36), v4 < 0)
    || (v4 = (*(__int64 (__fastcall **)(LPVOID, __int16 *))(*(_QWORD *)ppv + 112LL))(ppv, &v37), v4 < 0) )
  {
    LogLevel(2u, L"Flight Settings API Failed - 0x%x", (unsigned int)v4);
    v5 = 0;
    v6 = -1;
    v36[0] = 0;
    v4 = 0;
    v37 = -1;
  }
  else
  {
    v5 = v36[0];
    v6 = v37;
  }
  if ( v5 != -1 && v6 )
  {
    pdwReturnedProductType = 0;
    memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
    VersionInformation.dwOSVersionInfoSize = 284;
    if ( GetVersionExW(&VersionInformation)
      && GetProductInfo(
           VersionInformation.dwMajorVersion,
           VersionInformation.dwMinorVersion,
           v41,
           v42,
           &pdwReturnedProductType) )
    {
      v7 = pdwReturnedProductType;
    }
    else
    {
      v7 = 0;
      pdwReturnedProductType = 0;
    }
    if ( v7 <= 0xBF )
    {
      if ( v7 == 191 )
        goto LABEL_67;
      if ( v7 <= 0x29 )
      {
        if ( v7 == 41 )
          goto LABEL_67;
        if ( v7 <= 0x17 )
        {
          if ( v7 == 23 )
            goto LABEL_67;
          if ( v7 <= 0xF )
          {
            if ( v7 == 15 )
              goto LABEL_67;
            v8 = v7 - 7;
            if ( !v8 )
              goto LABEL_67;
            v9 = v8 - 1;
            if ( !v9 )
              goto LABEL_67;
            v10 = v9 - 1;
            if ( !v10 )
              goto LABEL_67;
            v11 = v10 - 1;
            if ( !v11 )
              goto LABEL_67;
            v13 = v11 - 2;
            v12 = v13 == 0;
            goto LABEL_25;
          }
          v18 = v7 - 17;
          v17 = v18 == 0;
          goto LABEL_30;
        }
        if ( v7 > 0x22 )
        {
          v18 = v7 - 35;
          v17 = v18 == 0;
LABEL_30:
          if ( v17 )
            goto LABEL_67;
          v20 = v18 - 1;
          v19 = v20 == 0;
          goto LABEL_32;
        }
        if ( v7 == 34 )
          goto LABEL_67;
        v22 = v7 - 24;
        if ( !v22 )
          goto LABEL_67;
        v23 = v22 - 1;
        if ( !v23 )
          goto LABEL_67;
        v20 = v23 - 4;
        v19 = v20 == 0;
LABEL_32:
        if ( v19 )
          goto LABEL_67;
        v21 = v20 - 1;
        if ( !v21 )
          goto LABEL_67;
        v13 = v21 - 1;
        v12 = v13 == 0;
LABEL_25:
        if ( v12 )
          goto LABEL_67;
        v15 = v13 - 1;
        v14 = v15 == 0;
        goto LABEL_27;
      }
      if ( v7 > 0x7D )
      {
        v32 = v7 - 126;
        if ( !v32 )
          goto LABEL_67;
        v15 = v32 - 3;
        v14 = v15 == 0;
      }
      else
      {
        if ( v7 == 125 )
          goto LABEL_67;
        if ( v7 <= 0x3B )
        {
          if ( v7 == 59 )
            goto LABEL_67;
          if ( v7 > 0x33 )
          {
            v20 = v7 - 52;
            v19 = v20 == 0;
            goto LABEL_32;
          }
          if ( v7 == 51 )
            goto LABEL_67;
          v24 = v7 - 42;
          if ( !v24 )
            goto LABEL_67;
          v25 = v24 - 1;
          if ( !v25 )
            goto LABEL_67;
          v26 = v25 - 1;
          if ( !v26 )
            goto LABEL_67;
          v27 = v26 - 1;
          if ( !v27 )
            goto LABEL_67;
          v28 = v27 - 1;
          if ( !v28 )
            goto LABEL_67;
          v16 = v28 == 4;
LABEL_65:
          if ( !v16 )
          {
            v4 = (*(__int64 (__fastcall **)(DeviceAttributes *, enum Train *))(*(_QWORD *)this + 32LL))(this, a2);
            goto LABEL_69;
          }
          goto LABEL_67;
        }
        if ( v7 <= 0x4C )
        {
          if ( v7 == 76 )
            goto LABEL_67;
          v20 = v7 - 60;
          v19 = v20 == 0;
          goto LABEL_32;
        }
        v29 = v7 - 77;
        if ( !v29 )
          goto LABEL_67;
        v30 = v29 - 2;
        if ( !v30 )
          goto LABEL_67;
        v31 = v30 - 1;
        if ( !v31 )
          goto LABEL_67;
        v15 = v31 - 15;
        v14 = v15 == 0;
      }
LABEL_27:
      if ( !v14 )
      {
        v16 = v15 == 1;
        goto LABEL_65;
      }
LABEL_67:
      *(_DWORD *)a2 = 3;
      LogLevel(4u, L"Train = LTSB");
      goto LABEL_69;
    }
    v33 = v7 - 205;
    if ( !v33 )
      goto LABEL_67;
    v16 = v33 == 2;
    goto LABEL_65;
  }
  LogLevel(4u, L"Train = AB");
  *(_DWORD *)a2 = 0;
  *((_DWORD *)this + 527) = 1;
LABEL_69:
  v34 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v34 + 16LL))(v34);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180010100  mov     [rsp-8+arg_10], rbx
0x180010105  push    rbp
0x180010106  push    rsi
0x180010107  push    rdi
0x180010108  push    r12
0x18001010a  push    r14
0x18001010c  lea     rbp, [rsp-80h]
0x180010111  sub     rsp, 180h
0x180010118  mov     rax, cs:__security_cookie
0x18001011f  xor     rax, rsp
0x180010122  mov     [rbp+0A0h+var_30], rax
0x180010126  xor     r14d, r14d
0x180010129  lea     rax, [rsp+1A0h+var_160]
0x18001012e  mov     rdi, rdx
0x180010131  mov     [rsp+1A0h+var_170], r14w
0x180010137  mov     rsi, rcx
0x18001013a  mov     [rsp+1A0h+var_160], r14
0x18001013f  or      r12d, 0FFFFFFFFh
0x180010143  mov     [rsp+1A0h+ppv], rax; ppv
0x180010148  lea     r8d, [r14+1]; dwClsContext
0x18001014c  mov     [rsp+1A0h+var_16C], r12w
0x180010152  lea     r9, _GUID_e833feb2_c58a_45e4_8d93_08874744febb; riid
0x180010159  xor     edx, edx; pUnkOuter
0x18001015b  lea     rcx, CLSID_FlightSettingsAPIBroker; rclsid
0x180010162  call    cs:__imp_CoCreateInstance
0x180010168  mov     ebx, eax
0x18001016a  test    eax, eax
0x18001016c  js      short loc_1800101B2
0x18001016e  mov     rcx, [rsp+1A0h+var_160]
0x180010173  lea     rdx, [rsp+1A0h+var_170]
0x180010178  mov     rax, [rcx]
0x18001017b  mov     rax, [rax+18h]
0x18001017f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010184  mov     ebx, eax
0x180010186  test    eax, eax
0x180010188  js      short loc_1800101B2
0x18001018a  mov     rcx, [rsp+1A0h+var_160]
0x18001018f  lea     rdx, [rsp+1A0h+var_16C]
0x180010194  mov     rax, [rcx]
0x180010197  mov     rax, [rax+70h]
0x18001019b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101a0  mov     ebx, eax
0x1800101a2  test    eax, eax
0x1800101a4  js      short loc_1800101B2
0x1800101a6  movzx   ecx, [rsp+1A0h+var_170]
0x1800101ab  movzx   eax, [rsp+1A0h+var_16C]
0x1800101b0  jmp     short loc_1800101D9
0x1800101b2  mov     r8d, ebx
0x1800101b5  lea     rdx, aFlightSettings; "Flight Settings API Failed - 0x%x"
0x1800101bc  mov     ecx, 2; unsigned __int8
0x1800101c1  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x1800101c6  mov     ecx, r14d
0x1800101c9  mov     eax, r12d
0x1800101cc  mov     [rsp+1A0h+var_170], cx
0x1800101d1  mov     ebx, r14d
0x1800101d4  mov     [rsp+1A0h+var_16C], ax
0x1800101d9  cmp     cx, r12w
0x1800101dd  jz      loc_1800103B4
0x1800101e3  test    ax, ax
0x1800101e6  jz      loc_1800103B4
0x1800101ec  xor     edx, edx; Val
0x1800101ee  mov     [rsp+1A0h+pdwReturnedProductType], r14d
0x1800101f3  mov     r8d, 118h; Size
0x1800101f9  lea     rcx, [rsp+1A0h+VersionInformation.dwMajorVersion]; void *
0x1800101fe  call    memset_0
0x180010203  lea     rcx, [rsp+1A0h+VersionInformation]; lpVersionInformation
0x180010208  mov     [rsp+1A0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180010210  call    cs:__imp_GetVersionExW
0x180010216  test    eax, eax
0x180010218  jz      short loc_180010246
0x18001021a  movzx   r9d, [rbp+0A0h+var_3A]; dwSpMinorVersion
0x18001021f  lea     rax, [rsp+1A0h+pdwReturnedProductType]
0x180010224  movzx   r8d, [rbp+0A0h+var_3C]; dwSpMajorVersion
0x180010229  mov     edx, [rsp+1A0h+VersionInformation.dwMinorVersion]; dwOSMinorVersion
0x18001022d  mov     ecx, [rsp+1A0h+VersionInformation.dwMajorVersion]; dwOSMajorVersion
0x180010231  mov     [rsp+1A0h+ppv], rax; pdwReturnedProductType
0x180010236  call    cs:__imp_GetProductInfo
0x18001023c  test    eax, eax
0x18001023e  jz      short loc_180010246
0x180010240  mov     eax, [rsp+1A0h+pdwReturnedProductType]
0x180010244  jmp     short loc_18001024D
0x180010246  mov     eax, r14d
0x180010249  mov     [rsp+1A0h+pdwReturnedProductType], eax
0x18001024d  mov     ecx, 0BFh
0x180010252  cmp     eax, ecx
0x180010254  ja      loc_180010379
0x18001025a  jz      loc_18001039B
0x180010260  cmp     eax, 29h ; ')'
0x180010263  ja      loc_18001030A
0x180010269  jz      loc_18001039B
0x18001026f  cmp     eax, 17h
0x180010272  ja      short loc_1800102E3
0x180010274  jz      loc_18001039B
0x18001027a  cmp     eax, 0Fh
0x18001027d  ja      short loc_1800102C3
0x18001027f  jz      loc_18001039B
0x180010285  sub     eax, 7
0x180010288  jz      loc_18001039B
0x18001028e  sub     eax, 1
0x180010291  jz      loc_18001039B
0x180010297  sub     eax, 1
0x18001029a  jz      loc_18001039B
0x1800102a0  sub     eax, 1
0x1800102a3  jz      loc_18001039B
0x1800102a9  sub     eax, 2
0x1800102ac  jz      loc_18001039B
0x1800102b2  sub     eax, 1
0x1800102b5  jz      loc_18001039B
0x1800102bb  cmp     eax, 1
0x1800102be  jmp     loc_180010383
0x1800102c3  sub     eax, 11h
0x1800102c6  jz      loc_18001039B
0x1800102cc  sub     eax, 1
0x1800102cf  jz      loc_18001039B
0x1800102d5  sub     eax, 1
0x1800102d8  jz      loc_18001039B
0x1800102de  sub     eax, 1
0x1800102e1  jmp     short loc_1800102AC
0x1800102e3  cmp     eax, 22h ; '"'
0x1800102e6  ja      short loc_180010305
0x1800102e8  jz      loc_18001039B
0x1800102ee  sub     eax, 18h
0x1800102f1  jz      loc_18001039B
0x1800102f7  sub     eax, 1
0x1800102fa  jz      loc_18001039B
0x180010300  sub     eax, 4
0x180010303  jmp     short loc_1800102CF
0x180010305  sub     eax, 23h ; '#'
0x180010308  jmp     short loc_1800102C6
0x18001030a  cmp     eax, 7Dh ; '}'
0x18001030d  ja      short loc_18001036C
0x18001030f  jz      loc_18001039B
0x180010315  cmp     eax, 3Bh ; ';'
0x180010318  ja      short loc_180010346
0x18001031a  jz      short loc_18001039B
0x18001031c  cmp     eax, 33h ; '3'
0x18001031f  ja      short loc_180010341
0x180010321  jz      short loc_18001039B
0x180010323  sub     eax, 2Ah ; '*'
0x180010326  jz      short loc_18001039B
0x180010328  sub     eax, 1
0x18001032b  jz      short loc_18001039B
0x18001032d  sub     eax, 1
0x180010330  jz      short loc_18001039B
0x180010332  sub     eax, 1
0x180010335  jz      short loc_18001039B
0x180010337  sub     eax, 1
0x18001033a  jz      short loc_18001039B
0x18001033c  cmp     eax, 4
0x18001033f  jmp     short loc_180010383
0x180010341  sub     eax, 34h ; '4'
0x180010344  jmp     short loc_1800102CF
0x180010346  cmp     eax, 4Ch ; 'L'
0x180010349  ja      short loc_180010355
0x18001034b  jz      short loc_18001039B
0x18001034d  sub     eax, 3Ch ; '<'
0x180010350  jmp     loc_1800102CF
0x180010355  sub     eax, 4Dh ; 'M'
0x180010358  jz      short loc_18001039B
0x18001035a  sub     eax, 2
0x18001035d  jz      short loc_18001039B
0x18001035f  sub     eax, 1
0x180010362  jz      short loc_18001039B
0x180010364  sub     eax, 0Fh
0x180010367  jmp     loc_1800102B5
0x18001036c  sub     eax, 7Eh ; '~'
0x18001036f  jz      short loc_18001039B
0x180010371  sub     eax, 3
0x180010374  jmp     loc_1800102B5
0x180010379  sub     eax, 0CDh
0x18001037e  jz      short loc_18001039B
0x180010380  cmp     eax, 2
0x180010383  jz      short loc_18001039B
0x180010385  mov     rax, [rsi]
0x180010388  mov     rdx, rdi
0x18001038b  mov     rcx, rsi
0x18001038e  mov     rax, [rax+20h]
0x180010392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010397  mov     ebx, eax
0x180010399  jmp     short loc_1800103D2
0x18001039b  lea     rdx, aTrainLtsb; "Train = LTSB"
0x1800103a2  mov     dword ptr [rdi], 3
0x1800103a8  mov     ecx, 4; unsigned __int8
0x1800103ad  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x1800103b2  jmp     short loc_1800103D2
0x1800103b4  lea     rdx, aTrainAb; "Train = AB"
0x1800103bb  mov     ecx, 4; unsigned __int8
0x1800103c0  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x1800103c5  mov     [rdi], r14d
0x1800103c8  mov     dword ptr [rsi+83Ch], 1
0x1800103d2  mov     rcx, [rsp+1A0h+var_160]
0x1800103d7  test    rcx, rcx
0x1800103da  jz      short loc_1800103ED
0x1800103dc  mov     [rsp+1A0h+var_160], r14
0x1800103e1  mov     rax, [rcx]
0x1800103e4  mov     rax, [rax+10h]
0x1800103e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103ed  mov     eax, ebx
0x1800103ef  mov     rcx, [rbp+0A0h+var_30]
0x1800103f3  xor     rcx, rsp; StackCookie
0x1800103f6  call    __security_check_cookie
0x1800103fb  mov     rbx, [rsp+1A0h+arg_10]
0x180010403  add     rsp, 180h
0x18001040a  pop     r14
0x18001040c  pop     r12
0x18001040e  pop     rdi
0x18001040f  pop     rsi
0x180010410  pop     rbp
0x180010411  retn
```
