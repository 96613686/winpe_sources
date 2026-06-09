# GetSystemStoreEntryFromCID(ICloudAPContext *,ushort const *,ATL::CRegKey &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x18000f420`
- end: `0x18000f76f`
- name: `?GetSystemStoreEntryFromCID@@YAJPEAVICloudAPContext@@PEBGAEAVCRegKey@ATL@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z`
- size: `847`
- prototype: `__int64 __fastcall(__int64, __int64, ATL::CRegKey *, _QWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180014ff0`

## callees

- `0x180003160`
- `0x180003b14`
- `0x180008440`
- `0x18000baac`
- `0x18000e0c4`
- `0x18000e564`
- `0x18000f420`
- `0x180010db0`
- `0x1800267c0`
- `0x180032010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000f698`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18000f698`

## string_xrefs

- `0x18000f4b4`: `onecoreuap\ds\ext\live\identity\cloudapplugin\utils.cpp`
- `0x18000f707`: `onecoreuap\ds\ext\live\identity\cloudapplugin\utils.cpp`

## pseudocode

```c
__int64 __fastcall GetSystemStoreEntryFromCID(__int64 a1, __int64 a2, ATL::CRegKey *a3, _QWORD *a4)
{
  __int64 v8; // rdx
  int v9; // r8d
  signed int v10; // ebx
  __int64 v11; // rdi
  __int64 v12; // rax
  __int64 v13; // rbx
  int v14; // eax
  unsigned int v15; // r14d
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  __int64 v20; // rax
  __int64 v21; // r8
  const unsigned __int16 *v23; // [rsp+20h] [rbp-E0h]
  __int64 v24; // [rsp+20h] [rbp-E0h]
  signed int v25; // [rsp+40h] [rbp-C0h] BYREF
  int v26; // [rsp+44h] [rbp-BCh] BYREF
  int v27; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v28; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v29[3]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v30[3]; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v31[3]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v32[4]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v33[128]; // [rsp+C0h] [rbp-40h] BYREF
  _WORD v34[256]; // [rsp+140h] [rbp+40h] BYREF

  v25 = 0;
  memset(v30, 0, sizeof(v30));
  memset(v29, 0, sizeof(v29));
  memset(v31, 0, sizeof(v31));
  v28 = 0;
  v32[0] = "GetSystemStoreEntryFromCID";
  v32[1] = &v25;
  v32[2] = 0;
  v32[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\utils.cpp",
    "GetSystemStoreEntryFromCID",
    (const char *)0x430,
    0,
    v23);
  if ( !a2 )
  {
    v10 = -1073741811;
LABEL_3:
    v25 = v10;
    goto LABEL_29;
  }
  v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
  v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
  ATL::CRegKey::Close(a3);
  ATL::CSimpleStringT<unsigned short,0>::Empty(a4);
  v14 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v13 + 72LL))(v13, 131097, &v28);
  v10 = v14;
  if ( v14 > 0 )
    v10 = (unsigned __int16)v14 | 0xC0070000;
  v25 = v10;
  if ( v10 >= 0 )
  {
    v15 = 0;
    v31[0] = v28;
    v16 = (*(__int64 (__fastcall **)(__int64, _QWORD *, __int64, const wchar_t *, int))(*(_QWORD *)v11 + 72LL))(
            v11,
            v30,
            v28,
            L"Software\\Microsoft\\IdentityCRL\\StoredIdentities",
            131097);
    v10 = v16;
    if ( v16 > 0 )
      v10 = (unsigned __int16)v16 | 0xC0070000;
    v25 = v10;
    if ( v10 >= 0 )
    {
      while ( 1 )
      {
        v27 = 256;
        memset_0(v34, 0, sizeof(v34));
        memset_0(v33, 0, sizeof(v33));
        v26 = 64;
        v17 = (*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD, _WORD *, int *, _QWORD))(*(_QWORD *)v11 + 80LL))(
                v11,
                v30,
                v15,
                v34,
                &v27,
                0);
        v10 = v17;
        if ( v17 == 259 )
          break;
        if ( v17 > 0 )
          v10 = (unsigned __int16)v17 | 0xC0070000;
        v25 = v10;
        if ( v10 < 0 )
          goto LABEL_29;
        v18 = (*(__int64 (__fastcall **)(__int64, _QWORD *, _QWORD, _WORD *, int))(*(_QWORD *)v11 + 72LL))(
                v11,
                v29,
                v30[0],
                v34,
                131097);
        v10 = v18;
        if ( v18 > 0 )
          v10 = (unsigned __int16)v18 | 0xC0070000;
        v25 = v10;
        if ( v10 < 0 )
          goto LABEL_29;
        ++v15;
        v19 = (*(__int64 (__fastcall **)(__int64, _QWORD *, const wchar_t *, _BYTE *, int *))(*(_QWORD *)v11 + 56LL))(
                v11,
                v29,
                L"CID",
                v33,
                &v26);
        if ( v19 || !v26 )
        {
          LODWORD(v24) = v19;
          TracePrintW(
            2u,
            "onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\utils.cpp",
            0x47Du,
            L"Query for CID failed with %d, continuing...",
            v24);
        }
        else if ( !(unsigned int)_o__wcsicmp(a2, v33) )
        {
          if ( *(_QWORD *)a3 != v29[0] )
          {
            ATL::CRegKey::Close(a3);
            v20 = v29[0];
            v29[0] = 0;
            *(_QWORD *)a3 = v20;
          }
          v21 = -1;
          do
            ++v21;
          while ( v34[v21] );
          ATL::CSimpleStringT<unsigned short,0>::SetString(a4, v34, v21);
          break;
        }
      }
      if ( *(_DWORD *)(*a4 - 16LL) )
      {
        v10 = v25;
        goto LABEL_29;
      }
      v10 = -1073741275;
      goto LABEL_3;
    }
  }
LABEL_29:
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v32, v8, v9);
  ATL::CRegKey::Close((ATL::CRegKey *)v31);
  ATL::CRegKey::Close((ATL::CRegKey *)v29);
  ATL::CRegKey::Close((ATL::CRegKey *)v30);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000f420  push    rbp
0x18000f422  push    rbx
0x18000f423  push    rsi
0x18000f424  push    rdi
0x18000f425  push    r12
0x18000f427  push    r13
0x18000f429  push    r14
0x18000f42b  push    r15
0x18000f42d  lea     rbp, [rsp-258h]
0x18000f435  sub     rsp, 358h
0x18000f43c  mov     rax, cs:__security_cookie
0x18000f443  xor     rax, rsp
0x18000f446  mov     [rbp+290h+var_50], rax
0x18000f44d  mov     r15, r9
0x18000f450  mov     rsi, r8
0x18000f453  mov     r12, rdx
0x18000f456  mov     rbx, rcx
0x18000f459  xor     r13d, r13d
0x18000f45c  mov     [rsp+390h+var_350], r13d
0x18000f461  mov     [rsp+390h+var_320], r13
0x18000f466  mov     [rsp+390h+var_318], r13
0x18000f46b  mov     [rbp+290h+var_310], r13
0x18000f46f  mov     [rsp+390h+var_338], r13
0x18000f474  mov     [rsp+390h+var_330], r13
0x18000f479  mov     [rsp+390h+var_328], r13
0x18000f47e  mov     [rbp+290h+var_308], r13
0x18000f482  mov     [rbp+290h+var_300], r13
0x18000f486  mov     [rbp+290h+var_2F8], r13
0x18000f48a  mov     [rsp+390h+var_340], r13
0x18000f48f  lea     rdx, aGetsystemstore_0; "GetSystemStoreEntryFromCID"
0x18000f496  mov     [rbp+290h+var_2F0], rdx
0x18000f49a  lea     rax, [rsp+390h+var_350]
0x18000f49f  mov     [rbp+290h+var_2E8], rax
0x18000f4a3  mov     [rbp+290h+var_2E0], r13
0x18000f4a7  mov     [rbp+290h+var_2D8], r13
0x18000f4ab  xor     r9d, r9d; unsigned int
0x18000f4ae  mov     r8d, 430h; char *
0x18000f4b4  lea     rcx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x18000f4bb  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18000f4c0  nop
0x18000f4c1  test    r12, r12
0x18000f4c4  jnz     short loc_18000F4D4
0x18000f4c6  mov     ebx, 0C000000Dh
0x18000f4cb  mov     [rsp+390h+var_350], ebx
0x18000f4cf  jmp     loc_18000F721
0x18000f4d4  mov     rax, [rbx]
0x18000f4d7  mov     rcx, rbx
0x18000f4da  mov     rax, [rax+10h]
0x18000f4de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4e3  mov     rdi, rax
0x18000f4e6  mov     rdx, [rbx]
0x18000f4e9  mov     rcx, rbx
0x18000f4ec  mov     rax, [rdx+8]
0x18000f4f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4f5  mov     rdx, rax
0x18000f4f8  mov     rcx, [rax]
0x18000f4fb  mov     rax, [rcx+8]
0x18000f4ff  mov     rcx, rdx
0x18000f502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f507  mov     rbx, rax
0x18000f50a  mov     rcx, rsi; this
0x18000f50d  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000f512  mov     rcx, r15
0x18000f515  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18000f51a  mov     rcx, [rbx]
0x18000f51d  mov     rax, [rcx+48h]
0x18000f521  lea     r8, [rsp+390h+var_340]
0x18000f526  mov     edx, 20019h
0x18000f52b  mov     rcx, rbx
0x18000f52e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f533  mov     ebx, eax
0x18000f535  test    eax, eax
0x18000f537  jle     short loc_18000F542
0x18000f539  movzx   ebx, ax
0x18000f53c  or      ebx, 0C0070000h
0x18000f542  mov     [rsp+390h+var_350], ebx
0x18000f546  test    ebx, ebx
0x18000f548  js      loc_18000F721
0x18000f54e  mov     r14d, r13d
0x18000f551  mov     r8, [rsp+390h+var_340]
0x18000f556  mov     [rbp+290h+var_308], r8
0x18000f55a  mov     rax, [rdi]
0x18000f55d  mov     dword ptr [rsp+390h+var_370], 20019h
0x18000f565  lea     r9, aSoftwareMicros_1; "Software\\Microsoft\\IdentityCRL\\Store"...
0x18000f56c  lea     rdx, [rsp+390h+var_320]
0x18000f571  mov     rcx, rdi
0x18000f574  mov     rax, [rax+48h]
0x18000f578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f57d  mov     ebx, eax
0x18000f57f  test    eax, eax
0x18000f581  jle     short loc_18000F58C
0x18000f583  movzx   ebx, ax
0x18000f586  or      ebx, 0C0070000h
0x18000f58c  mov     [rsp+390h+var_350], ebx
0x18000f590  test    ebx, ebx
0x18000f592  js      loc_18000F721
0x18000f598  mov     [rsp+390h+var_348], 100h
0x18000f5a0  xor     edx, edx; Val
0x18000f5a2  mov     r8d, 200h; Size
0x18000f5a8  lea     rcx, [rbp+290h+var_250]; void *
0x18000f5ac  call    memset_0
0x18000f5b1  xor     edx, edx; Val
0x18000f5b3  mov     r8d, 80h; Size
0x18000f5b9  lea     rcx, [rbp+290h+var_2D0]; void *
0x18000f5bd  call    memset_0
0x18000f5c2  mov     [rsp+390h+var_34C], 40h ; '@'
0x18000f5ca  mov     rax, [rdi]
0x18000f5cd  mov     [rsp+390h+var_368], r13
0x18000f5d2  lea     rcx, [rsp+390h+var_348]
0x18000f5d7  mov     [rsp+390h+var_370], rcx
0x18000f5dc  lea     r9, [rbp+290h+var_250]
0x18000f5e0  mov     r8d, r14d
0x18000f5e3  lea     rdx, [rsp+390h+var_320]
0x18000f5e8  mov     rcx, rdi
0x18000f5eb  mov     rax, [rax+50h]
0x18000f5ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5f4  mov     ebx, eax
0x18000f5f6  cmp     eax, 103h
0x18000f5fb  jz      loc_18000F6E3
0x18000f601  test    eax, eax
0x18000f603  jle     short loc_18000F60E
0x18000f605  movzx   ebx, ax
0x18000f608  or      ebx, 0C0070000h
0x18000f60e  mov     [rsp+390h+var_350], ebx
0x18000f612  test    ebx, ebx
0x18000f614  js      loc_18000F721
0x18000f61a  mov     rax, [rdi]
0x18000f61d  mov     dword ptr [rsp+390h+var_370], 20019h
0x18000f625  lea     r9, [rbp+290h+var_250]
0x18000f629  mov     r8, [rsp+390h+var_320]
0x18000f62e  lea     rdx, [rsp+390h+var_338]
0x18000f633  mov     rcx, rdi
0x18000f636  mov     rax, [rax+48h]
0x18000f63a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f63f  mov     ebx, eax
0x18000f641  test    eax, eax
0x18000f643  jle     short loc_18000F64E
0x18000f645  movzx   ebx, ax
0x18000f648  or      ebx, 0C0070000h
0x18000f64e  mov     [rsp+390h+var_350], ebx
0x18000f652  test    ebx, ebx
0x18000f654  js      loc_18000F721
0x18000f65a  inc     r14d
0x18000f65d  mov     rax, [rdi]
0x18000f660  lea     rcx, [rsp+390h+var_34C]
0x18000f665  mov     [rsp+390h+var_370], rcx
0x18000f66a  lea     r9, [rbp+290h+var_2D0]
0x18000f66e  lea     r8, aCid; "CID"
0x18000f675  lea     rdx, [rsp+390h+var_338]
0x18000f67a  mov     rcx, rdi
0x18000f67d  mov     rax, [rax+38h]
0x18000f681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f686  test    eax, eax
0x18000f688  jnz     short loc_18000F6F6
0x18000f68a  cmp     [rsp+390h+var_34C], r13d
0x18000f68f  jz      short loc_18000F6F6
0x18000f691  lea     rdx, [rbp+290h+var_2D0]
0x18000f695  mov     rcx, r12
0x18000f698  call    cs:__imp__o__wcsicmp
0x18000f69e  test    eax, eax
0x18000f6a0  jnz     loc_18000F598
0x18000f6a6  mov     rax, [rsp+390h+var_338]
0x18000f6ab  cmp     [rsi], rax
0x18000f6ae  jz      short loc_18000F6C5
0x18000f6b0  mov     rcx, rsi; this
0x18000f6b3  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000f6b8  mov     rax, [rsp+390h+var_338]
0x18000f6bd  mov     [rsp+390h+var_338], r13
0x18000f6c2  mov     [rsi], rax
0x18000f6c5  lea     rax, [rbp+290h+var_250]
0x18000f6c9  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000f6cd  inc     r8
0x18000f6d0  cmp     [rax+r8*2], r13w
0x18000f6d5  jnz     short loc_18000F6CD
0x18000f6d7  lea     rdx, [rbp+290h+var_250]
0x18000f6db  mov     rcx, r15
0x18000f6de  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18000f6e3  mov     rax, [r15]
0x18000f6e6  cmp     [rax-10h], r13d
0x18000f6ea  jnz     short loc_18000F71D
0x18000f6ec  mov     ebx, 0C0000225h
0x18000f6f1  jmp     loc_18000F4CB
0x18000f6f6  mov     dword ptr [rsp+390h+var_370], eax
0x18000f6fa  lea     r9, aQueryForCidFai; "Query for CID failed with %d, continuin"...
0x18000f701  mov     r8d, 47Dh; unsigned int
0x18000f707  lea     rdx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x18000f70e  mov     ecx, 2; unsigned __int8
0x18000f713  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18000f718  jmp     loc_18000F598
0x18000f71d  mov     ebx, [rsp+390h+var_350]
0x18000f721  lea     rcx, [rbp+290h+var_2F0]
0x18000f725  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18000f72a  nop
0x18000f72b  lea     rcx, [rbp+290h+var_308]; this
0x18000f72f  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000f734  nop
0x18000f735  lea     rcx, [rsp+390h+var_338]; this
0x18000f73a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000f73f  nop
0x18000f740  lea     rcx, [rsp+390h+var_320]; this
0x18000f745  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000f74a  mov     eax, ebx
0x18000f74c  mov     rcx, [rbp+290h+var_50]
0x18000f753  xor     rcx, rsp; StackCookie
0x18000f756  call    __security_check_cookie
0x18000f75b  add     rsp, 358h
0x18000f762  pop     r15
0x18000f764  pop     r14
0x18000f766  pop     r13
0x18000f768  pop     r12
0x18000f76a  pop     rdi
0x18000f76b  pop     rsi
0x18000f76c  pop     rbx
0x18000f76d  pop     rbp
0x18000f76e  retn
```
