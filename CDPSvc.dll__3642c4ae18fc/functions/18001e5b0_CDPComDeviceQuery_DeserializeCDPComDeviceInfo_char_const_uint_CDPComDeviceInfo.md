# CDPComDeviceQuery::DeserializeCDPComDeviceInfo(char const *,uint,CDPComDeviceInfo *)

- ea: `0x18001e5b0`
- end: `0x18001e802`
- name: `?DeserializeCDPComDeviceInfo@CDPComDeviceQuery@@UEAAJPEBDIPEAUCDPComDeviceInfo@@@Z`
- size: `594`
- prototype: `__int64 __fastcall(CDPComDeviceQuery *__hidden this, const char *, unsigned int, struct CDPComDeviceInfo *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003e60`
- `0x18000e9e8`
- `0x180017a98`
- `0x180018970`
- `0x18001ddf8`
- `0x18001e5b0`
- `0x180023148`
- `0x18006a010`

## import_xrefs

- `cdp!CDPCreateDeviceQueryInternal` at `0x18001e6d1`
- `cdp!CDPCreateDeviceQueryInternal` at `0x18001e6d1`

## string_xrefs

- `0x18001e5f1`: `.\cdpcomdevicequery.cpp`
- `0x18001e6ff`: `.\cdpcomdevicequery.cpp`
- `0x18001e784`: `.\cdpcomdevicequery.cpp`

## pseudocode

```c
__int64 __fastcall CDPComDeviceQuery::DeserializeCDPComDeviceInfo(
        CDPComDeviceQuery *this,
        const char *a2,
        unsigned int a3,
        struct CDPComDeviceInfo *a4)
{
  __int64 v8; // rcx
  int v9; // r14d
  int v10; // edx
  int v11; // ecx
  __int64 v12; // rax
  int v13; // edi
  int v14; // edx
  int v15; // ecx
  int v16; // eax
  int v17; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v18; // [rsp+38h] [rbp-C8h] BYREF
  std::_Ref_count_base **v19; // [rsp+40h] [rbp-C0h]
  std::_Ref_count_base *v20[2]; // [rsp+48h] [rbp-B8h] BYREF
  std::_Ref_count_base *v21[2]; // [rsp+58h] [rbp-A8h] BYREF
  _OWORD v22[12]; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v23; // [rsp+158h] [rbp+58h] BYREF

  if ( !a2 )
  {
    v17 = 308;
LABEL_3:
    v23 = -2147467261;
LABEL_4:
    Log<long &,char const (&)[28],int>(
      (_DWORD)this,
      (_DWORD)a2,
      (unsigned int)&v23,
      (unsigned int)".\\cdpcomdevicequery.cpp",
      (__int64)&v17);
    return v23;
  }
  if ( !a3 )
  {
    v23 = -2147024809;
    v17 = 309;
    goto LABEL_4;
  }
  if ( !a4 )
  {
    v17 = 310;
    goto LABEL_3;
  }
  memset_0(v22, 0, sizeof(v22));
  *(_OWORD *)a4 = v22[0];
  *((_OWORD *)a4 + 1) = v22[1];
  *((_OWORD *)a4 + 2) = v22[2];
  *((_OWORD *)a4 + 3) = v22[3];
  *((_OWORD *)a4 + 4) = v22[4];
  *((_OWORD *)a4 + 5) = v22[5];
  *((_OWORD *)a4 + 6) = v22[6];
  *((_OWORD *)a4 + 7) = v22[7];
  *((_OWORD *)a4 + 8) = v22[8];
  *((_OWORD *)a4 + 9) = v22[9];
  *((_OWORD *)a4 + 10) = v22[10];
  *((_OWORD *)a4 + 11) = v22[11];
  *(_OWORD *)v20 = 0;
  v18 = 0;
  v19 = v20;
  LOBYTE(v8) = 1;
  v9 = CDPCreateDeviceQueryInternal(v8, 0, &v18);
  cdp::detail::address_of<ICDPDeviceQuery>::~address_of<ICDPDeviceQuery>(&v18);
  if ( v9 < 0 )
  {
    v23 = v9;
    v17 = 315;
    Log<long &,char const (&)[28],int>(
      v11,
      v10,
      (unsigned int)&v23,
      (unsigned int)".\\cdpcomdevicequery.cpp",
      (__int64)&v17);
LABEL_12:
    if ( v20[1] )
      std::_Ref_count_base::_Decref(v20[1]);
    return v23;
  }
  *(_OWORD *)v21 = 0;
  v12 = *(_QWORD *)v20[0];
  v18 = 0;
  v19 = v21;
  v13 = (*(__int64 (__fastcall **)(std::_Ref_count_base *, const char *, _QWORD, __int64 *))(v12 + 120))(
          v20[0],
          a2,
          a3,
          &v18);
  cdp::detail::address_of<ICDPDeviceInfo>::~address_of<ICDPDeviceInfo>(&v18);
  if ( v13 < 0 )
  {
    v23 = v13;
    v17 = 318;
    goto LABEL_16;
  }
  v16 = ComDeviceInfoFromCDPDeviceInfo_1(v21[0], a4);
  if ( v16 < 0 )
  {
    v23 = v16;
    v17 = 320;
LABEL_16:
    Log<long &,char const (&)[28],int>(
      v15,
      v14,
      (unsigned int)&v23,
      (unsigned int)".\\cdpcomdevicequery.cpp",
      (__int64)&v17);
    if ( v21[1] )
      std::_Ref_count_base::_Decref(v21[1]);
    goto LABEL_12;
  }
  if ( v21[1] )
    std::_Ref_count_base::_Decref(v21[1]);
  if ( v20[1] )
    std::_Ref_count_base::_Decref(v20[1]);
  return 0;
}

```

## disassembly

```asm
0x18001e5b0  mov     [rsp-8+arg_0], rbx
0x18001e5b5  mov     [rsp-8+arg_10], rsi
0x18001e5ba  push    rbp
0x18001e5bb  push    rdi
0x18001e5bc  push    r14
0x18001e5be  lea     rbp, [rsp-30h]
0x18001e5c3  sub     rsp, 130h
0x18001e5ca  mov     rbx, r9
0x18001e5cd  mov     edi, r8d
0x18001e5d0  mov     rsi, rdx
0x18001e5d3  test    rdx, rdx
0x18001e5d6  jnz     short loc_18001E609
0x18001e5d8  mov     [rsp+140h+var_110], 134h
0x18001e5e0  mov     [rbp+40h+arg_8], 80004003h
0x18001e5e7  lea     rax, [rsp+140h+var_110]
0x18001e5ec  mov     [rsp+140h+var_120], rax
0x18001e5f1  lea     r9, aCdpcomdevicequ; ".\\cdpcomdevicequery.cpp"
0x18001e5f8  lea     r8, [rbp+40h+arg_8]
0x18001e5fc  call    ??$Log@AEAJAEAY0BM@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BM@$$CBD$$QEAH@Z; Log<long &,char const (&)[28],int>(CDPLogLevel,char const *,long &,char const (&)[28],int &&)
0x18001e601  mov     eax, [rbp+40h+arg_8]
0x18001e604  jmp     loc_18001E7EA
0x18001e609  test    edi, edi
0x18001e60b  jnz     short loc_18001E61E
0x18001e60d  mov     [rbp+40h+arg_8], 80070057h
0x18001e614  mov     [rsp+140h+var_110], 135h
0x18001e61c  jmp     short loc_18001E5E7
0x18001e61e  test    rbx, rbx
0x18001e621  jnz     short loc_18001E62D
0x18001e623  mov     [rsp+140h+var_110], 136h
0x18001e62b  jmp     short loc_18001E5E0
0x18001e62d  xor     edx, edx; Val
0x18001e62f  mov     r8d, 0C0h; Size
0x18001e635  lea     rcx, [rsp+140h+var_D8]; void *
0x18001e63a  call    memset_0
0x18001e63f  movups  xmm0, [rsp+140h+var_D8]
0x18001e644  movups  xmmword ptr [rbx], xmm0
0x18001e647  movups  xmm1, [rsp+140h+var_C8]
0x18001e64c  movups  xmmword ptr [rbx+10h], xmm1
0x18001e650  movups  xmm0, [rbp+40h+var_B8]
0x18001e654  movups  xmmword ptr [rbx+20h], xmm0
0x18001e658  movups  xmm1, [rbp+40h+var_A8]
0x18001e65c  movups  xmmword ptr [rbx+30h], xmm1
0x18001e660  movups  xmm0, [rbp+40h+var_98]
0x18001e664  movups  xmmword ptr [rbx+40h], xmm0
0x18001e668  movups  xmm1, [rbp+40h+var_88]
0x18001e66c  movups  xmmword ptr [rbx+50h], xmm1
0x18001e670  movups  xmm0, [rbp+40h+var_78]
0x18001e674  movups  xmmword ptr [rbx+60h], xmm0
0x18001e678  movups  xmm1, [rbp+40h+var_68]
0x18001e67c  movups  xmmword ptr [rbx+70h], xmm1
0x18001e680  movups  xmm0, [rbp+40h+var_58]
0x18001e684  movups  xmmword ptr [rbx+80h], xmm0
0x18001e68b  movups  xmm1, [rbp+40h+var_48]
0x18001e68f  movups  xmmword ptr [rbx+90h], xmm1
0x18001e696  movups  xmm0, [rbp+40h+var_38]
0x18001e69a  movups  xmmword ptr [rbx+0A0h], xmm0
0x18001e6a1  movups  xmm1, [rbp+40h+var_28]
0x18001e6a5  movups  xmmword ptr [rbx+0B0h], xmm1
0x18001e6ac  xorps   xmm0, xmm0
0x18001e6af  movdqu  xmmword ptr [rsp+140h+var_F8], xmm0
0x18001e6b5  mov     [rsp+140h+var_108], 0
0x18001e6be  lea     rax, [rsp+140h+var_F8]
0x18001e6c3  mov     [rsp+140h+var_100], rax
0x18001e6c8  lea     r8, [rsp+140h+var_108]
0x18001e6cd  xor     edx, edx
0x18001e6cf  mov     cl, 1
0x18001e6d1  call    cs:__imp_CDPCreateDeviceQueryInternal
0x18001e6d7  mov     r14d, eax
0x18001e6da  lea     rcx, [rsp+140h+var_108]
0x18001e6df  call    ??1?$address_of@VICDPDeviceQuery@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPDeviceQuery>::~address_of<ICDPDeviceQuery>(void)
0x18001e6e4  test    r14d, r14d
0x18001e6e7  jns     short loc_18001E727
0x18001e6e9  mov     [rbp+40h+arg_8], r14d
0x18001e6ed  mov     [rsp+140h+var_110], 13Bh
0x18001e6f5  lea     rax, [rsp+140h+var_110]
0x18001e6fa  mov     [rsp+140h+var_120], rax
0x18001e6ff  lea     r9, aCdpcomdevicequ; ".\\cdpcomdevicequery.cpp"
0x18001e706  lea     r8, [rbp+40h+arg_8]
0x18001e70a  call    ??$Log@AEAJAEAY0BM@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BM@$$CBD$$QEAH@Z; Log<long &,char const (&)[28],int>(CDPLogLevel,char const *,long &,char const (&)[28],int &&)
0x18001e70f  mov     rcx, [rsp+140h+var_F8+8]; this
0x18001e714  test    rcx, rcx
0x18001e717  jz      loc_18001E601
0x18001e71d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001e722  jmp     loc_18001E601
0x18001e727  xorps   xmm0, xmm0
0x18001e72a  movdqu  xmmword ptr [rsp+140h+var_E8], xmm0
0x18001e730  mov     rcx, [rsp+140h+var_F8]
0x18001e735  mov     rax, [rcx]
0x18001e738  mov     [rsp+140h+var_108], 0
0x18001e741  lea     rdx, [rsp+140h+var_E8]
0x18001e746  mov     [rsp+140h+var_100], rdx
0x18001e74b  lea     r9, [rsp+140h+var_108]
0x18001e750  mov     r8d, edi
0x18001e753  mov     rdx, rsi
0x18001e756  mov     rax, [rax+78h]
0x18001e75a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e75f  mov     edi, eax
0x18001e761  lea     rcx, [rsp+140h+var_108]
0x18001e766  call    ??1?$address_of@VICDPDeviceInfo@@@detail@cdp@@QEAA@XZ; cdp::detail::address_of<ICDPDeviceInfo>::~address_of<ICDPDeviceInfo>(void)
0x18001e76b  test    edi, edi
0x18001e76d  jns     short loc_18001E7AC
0x18001e76f  mov     [rbp+40h+arg_8], edi
0x18001e772  mov     [rsp+140h+var_110], 13Eh
0x18001e77a  lea     rax, [rsp+140h+var_110]
0x18001e77f  mov     [rsp+140h+var_120], rax
0x18001e784  lea     r9, aCdpcomdevicequ; ".\\cdpcomdevicequery.cpp"
0x18001e78b  lea     r8, [rbp+40h+arg_8]
0x18001e78f  call    ??$Log@AEAJAEAY0BM@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BM@$$CBD$$QEAH@Z; Log<long &,char const (&)[28],int>(CDPLogLevel,char const *,long &,char const (&)[28],int &&)
0x18001e794  mov     rcx, [rsp+140h+var_E8+8]; this
0x18001e799  test    rcx, rcx
0x18001e79c  jz      loc_18001E70F
0x18001e7a2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001e7a7  jmp     loc_18001E70F
0x18001e7ac  mov     rdx, rbx
0x18001e7af  mov     rcx, [rsp+140h+var_E8]
0x18001e7b4  call    ComDeviceInfoFromCDPDeviceInfo_1
0x18001e7b9  test    eax, eax
0x18001e7bb  jns     short loc_18001E7CA
0x18001e7bd  mov     [rbp+40h+arg_8], eax
0x18001e7c0  mov     [rsp+140h+var_110], 140h
0x18001e7c8  jmp     short loc_18001E77A
0x18001e7ca  mov     rcx, [rsp+140h+var_E8+8]; this
0x18001e7cf  test    rcx, rcx
0x18001e7d2  jz      short loc_18001E7D9
0x18001e7d4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001e7d9  mov     rcx, [rsp+140h+var_F8+8]; this
0x18001e7de  test    rcx, rcx
0x18001e7e1  jz      short loc_18001E7E8
0x18001e7e3  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001e7e8  xor     eax, eax
0x18001e7ea  lea     r11, [rsp+140h+var_10]
0x18001e7f2  mov     rbx, [r11+20h]
0x18001e7f6  mov     rsi, [r11+30h]
0x18001e7fa  mov     rsp, r11
0x18001e7fd  pop     r14
0x18001e7ff  pop     rdi
0x18001e800  pop     rbp
0x18001e801  retn
```
