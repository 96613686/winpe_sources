# ParseSettingsMasterDatastoreXML(IStream *,__MIDL___MIDL_itf_mvprovisiondata_0000_0000_0003)

- ea: `0x18000b31c`
- end: `0x18000b6d2`
- name: `?ParseSettingsMasterDatastoreXML@@YA?AV?$vector@V?$shared_ptr@VCConfigSource@@@std@@V?$allocator@V?$shared_ptr@VCConfigSource@@@std@@@2@@std@@PEAUIStream@@W4__MIDL___MIDL_itf_mvprovisiondata_0000_0000_0003@@@Z`
- size: `950`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x1800095e8`

## callees

- `0x180009068`
- `0x18000a268`
- `0x18000a2e4`
- `0x18000a94c`
- `0x18000a9f0`
- `0x18000b31c`
- `0x18000b6d8`
- `0x18000b8f8`
- `0x180010d44`
- `0x180012010`

## import_xrefs

- `XmlLite!CreateXmlReader` at `0x18000b3f3`
- `XmlLite!CreateXmlReader` at `0x18000b3f3`

## string_xrefs

- `0x18000b657`: `onecoreuap\admin\prov\multivariant\datastore\src\masterdatastoreparse.cpp`
- `0x18000b66c`: `onecoreuap\admin\prov\multivariant\datastore\src\masterdatastoreparse.cpp`
- `0x18000b681`: `onecoreuap\admin\prov\multivariant\datastore\src\masterdatastoreparse.cpp`
- `0x18000b696`: `onecoreuap\admin\prov\multivariant\datastore\src\masterdatastoreparse.cpp`
- `0x18000b6ab`: `onecoreuap\admin\prov\multivariant\datastore\src\masterdatastoreparse.cpp`
- `0x18000b6c0`: `onecoreuap\admin\prov\multivariant\datastore\src\masterdatastoreparse.cpp`

## pseudocode

```c
__int64 __fastcall ParseSettingsMasterDatastoreXML(__int64 a1, __int64 a2, int a3)
{
  volatile signed __int32 *v5; // rdi
  void *v6; // rcx
  HRESULT v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  __int64 v12; // rsi
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rdi
  __int64 *v15; // r8
  __int64 *v16; // rdx
  __int64 v17; // rcx
  volatile signed __int32 *v18; // rdi
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rcx
  volatile signed __int32 *v22; // rdi
  void *v23; // rcx
  __int128 v25; // [rsp+28h] [rbp-48h] BYREF
  __int128 v26; // [rsp+38h] [rbp-38h] BYREF
  _DWORD v27[4]; // [rsp+48h] [rbp-28h] BYREF
  __int128 v28; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  int v30; // [rsp+B0h] [rbp+40h] BYREF
  void *ppvObject; // [rsp+B8h] [rbp+48h] BYREF

  ppvObject = 0;
  v30 = 0;
  v28 = 0;
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 16) = 0;
  v27[0] = a3;
  v27[2] = 1;
  v26 = 0;
  std::shared_ptr<CConfigSource>::_Resetp<CConfigSource>(&v26);
  std::shared_ptr<CConfigSet>::operator=(&v28, (__int64 *)&v26);
  v5 = (volatile signed __int32 *)*((_QWORD *)&v26 + 1);
  if ( *((_QWORD *)&v26 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v26 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
      if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
    }
  }
  v6 = ppvObject;
  if ( ppvObject )
  {
    ppvObject = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v6 + 16LL))(v6);
  }
  v7 = CreateXmlReader(&GUID_7279fc81_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x140,
      (int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\masterdatastoreparse.cpp",
      (const char *)(unsigned int)v7,
      1);
  v8 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 4);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x143,
      (int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\masterdatastoreparse.cpp",
      (const char *)(unsigned int)v8,
      1);
  v9 = (*(__int64 (__fastcall **)(void *, __int64))(*(_QWORD *)ppvObject + 24LL))(ppvObject, a2);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x146,
      (int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\masterdatastoreparse.cpp",
      (const char *)(unsigned int)v9,
      1);
  while ( 1 )
  {
    v10 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)ppvObject + 48LL))(ppvObject, &v30);
    if ( v10 )
      break;
    if ( v30 == 1 )
    {
      v20 = ProcessNewXmlElement((struct IXmlReader *)ppvObject, (struct MasterDatastoreContext *)v27);
      if ( v20 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x14E,
          (int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\masterdatastoreparse.cpp",
          (const char *)(unsigned int)v20,
          1);
    }
    else if ( v30 == 15 )
    {
      v25 = 0;
      v11 = ProcessEndXmlElement(ppvObject, v27, &v25);
      if ( v11 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x155,
          (int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\masterdatastoreparse.cpp",
          (const char *)(unsigned int)v11,
          1);
      v12 = v25;
      if ( !(_QWORD)v25 )
        goto LABEL_22;
      v13 = *(_QWORD *)(a1 + 8);
      if ( (unsigned __int64)&v25 < v13 && *(_QWORD *)a1 <= (unsigned __int64)&v25 )
      {
        v14 = (unsigned __int64)&v25 - *(_QWORD *)a1;
        if ( v13 == *(_QWORD *)(a1 + 16) )
          std::vector<std::shared_ptr<CConfigSource>>::_Reserve((_QWORD *)a1);
        v15 = (__int64 *)((v14 & 0xFFFFFFFFFFFFFFF0uLL) + *(_QWORD *)a1);
        v16 = *(__int64 **)(a1 + 8);
        *v16 = 0;
        v16[1] = 0;
        if ( v16 != v15 )
        {
          v16[1] = v15[1];
          v15[1] = 0;
          v17 = *v16;
          *v16 = *v15;
          *v15 = v17;
        }
        *(_QWORD *)(a1 + 8) += 16LL;
LABEL_22:
        v18 = (volatile signed __int32 *)*((_QWORD *)&v25 + 1);
        goto LABEL_23;
      }
      if ( v13 == *(_QWORD *)(a1 + 16) )
        std::vector<std::shared_ptr<CConfigSource>>::_Reserve((_QWORD *)a1);
      v19 = *(_QWORD *)(a1 + 8);
      *(_QWORD *)v19 = 0;
      *(_QWORD *)(v19 + 8) = 0;
      if ( (__int128 *)v19 == &v25 )
      {
        v18 = (volatile signed __int32 *)*((_QWORD *)&v25 + 1);
      }
      else
      {
        *(_QWORD *)(v19 + 8) = *((_QWORD *)&v25 + 1);
        v18 = 0;
        *(_QWORD *)v19 = v12;
        *(_QWORD *)&v25 = 0;
      }
      *(_QWORD *)(a1 + 8) += 16LL;
LABEL_23:
      if ( v18 && _InterlockedExchangeAdd(v18 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
        if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
      }
    }
  }
  if ( v10 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x160,
      (int)"onecoreuap\\admin\\prov\\multivariant\\datastore\\src\\masterdatastoreparse.cpp",
      (const char *)(unsigned int)v10,
      1);
  ____Sort_PEAV__shared_ptr_VCConfigSource___std___JP6AHV__shared_ptr___CBVCConfigSource___2_0__E_std__YAXPEAV__shared_ptr_VCConfigSource___0_0_JP6AHV__shared_ptr___CBVCConfigSource___0_2__E_Z(
    *(__int64 **)a1,
    *(__int64 **)(a1 + 8),
    (__int64)(*(_QWORD *)(a1 + 8) - *(_QWORD *)a1) >> 4);
  if ( (_QWORD)v28 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v21);
  v22 = (volatile signed __int32 *)*((_QWORD *)&v28 + 1);
  if ( *((_QWORD *)&v28 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v28 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
      if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
    }
  }
  v23 = ppvObject;
  if ( ppvObject )
  {
    ppvObject = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v23 + 16LL))(v23);
  }
  return a1;
}

```

## disassembly

```asm
0x18000b31c  mov     [rsp-28h+arg_8], rbx
0x18000b321  mov     [rsp-28h+arg_0], rcx
0x18000b326  push    rbp
0x18000b327  push    rsi
0x18000b328  push    rdi
0x18000b329  push    r14
0x18000b32b  push    r15
0x18000b32d  mov     rbp, rsp
0x18000b330  sub     rsp, 70h
0x18000b334  mov     rsi, rdx
0x18000b337  mov     rbx, rcx
0x18000b33a  xor     r14d, r14d
0x18000b33d  mov     [rbp+var_50], r14d
0x18000b341  mov     [rbp+ppvObject], r14
0x18000b345  mov     [rbp+arg_10], r14d
0x18000b349  xorps   xmm0, xmm0
0x18000b34c  movdqu  [rbp+var_18], xmm0
0x18000b351  mov     [rcx], r14
0x18000b354  mov     [rcx+8], r14
0x18000b358  mov     [rcx+10h], r14
0x18000b35c  lea     eax, [r14+1]
0x18000b360  mov     [rbp+var_50], eax
0x18000b363  mov     [rbp+var_28], r8d
0x18000b367  mov     [rbp+var_20], eax
0x18000b36a  movdqu  [rbp+var_38], xmm0
0x18000b36f  lea     rcx, [rbp+var_38]
0x18000b373  call    ??$_Resetp@VCConfigSource@@@?$shared_ptr@VCConfigSource@@@std@@AEAAXPEAVCConfigSource@@@Z; std::shared_ptr<CConfigSource>::_Resetp<CConfigSource>(CConfigSource *)
0x18000b378  lea     rdx, [rbp+var_38]
0x18000b37c  lea     rcx, [rbp+var_18]
0x18000b380  call    ??4?$shared_ptr@VCConfigSet@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CConfigSet>::operator=(std::shared_ptr<CConfigSet> &&)
0x18000b385  nop
0x18000b386  or      r15d, 0FFFFFFFFh
0x18000b38a  mov     rdi, qword ptr [rbp+var_38+8]
0x18000b38e  test    rdi, rdi
0x18000b391  jz      short loc_18000B3CB
0x18000b393  mov     eax, r15d
0x18000b396  lock xadd [rdi+8], eax
0x18000b39b  add     eax, r15d
0x18000b39e  jnz     short loc_18000B3CB
0x18000b3a0  mov     rax, [rdi]
0x18000b3a3  mov     rcx, rdi
0x18000b3a6  mov     rax, [rax]
0x18000b3a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3ae  mov     eax, r15d
0x18000b3b1  lock xadd [rdi+0Ch], eax
0x18000b3b6  add     eax, r15d
0x18000b3b9  jnz     short loc_18000B3CB
0x18000b3bb  mov     rax, [rdi]
0x18000b3be  mov     rcx, rdi
0x18000b3c1  mov     rax, [rax+8]
0x18000b3c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3ca  nop
0x18000b3cb  mov     rcx, [rbp+ppvObject]
0x18000b3cf  test    rcx, rcx
0x18000b3d2  jz      short loc_18000B3E5
0x18000b3d4  mov     [rbp+ppvObject], r14
0x18000b3d8  mov     rax, [rcx]
0x18000b3db  mov     rax, [rax+10h]
0x18000b3df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3e4  nop
0x18000b3e5  xor     r8d, r8d; pMalloc
0x18000b3e8  lea     rdx, [rbp+ppvObject]; ppvObject
0x18000b3ec  lea     rcx, _GUID_7279fc81_709d_4095_b63d_69fe4b0d9030; riid
0x18000b3f3  call    cs:__imp_CreateXmlReader
0x18000b3f9  mov     rcx, [rbp+28h]; this
0x18000b3fd  test    eax, eax
0x18000b3ff  js      loc_18000B67E
0x18000b405  mov     rcx, [rbp+ppvObject]
0x18000b409  mov     rax, [rcx]
0x18000b40c  xor     r8d, r8d
0x18000b40f  lea     edx, [r8+4]
0x18000b413  mov     rax, [rax+28h]
0x18000b417  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b41c  mov     rcx, [rbp+28h]; this
0x18000b420  test    eax, eax
0x18000b422  js      loc_18000B693
0x18000b428  mov     rcx, [rbp+ppvObject]
0x18000b42c  mov     rax, [rcx]
0x18000b42f  mov     rdx, rsi
0x18000b432  mov     rax, [rax+18h]
0x18000b436  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b43b  mov     rcx, [rbp+28h]; this
0x18000b43f  test    eax, eax
0x18000b441  js      loc_18000B6A8
0x18000b447  mov     rcx, [rbp+ppvObject]
0x18000b44b  mov     rax, [rcx]
0x18000b44e  lea     rdx, [rbp+arg_10]
0x18000b452  mov     rax, [rax+30h]
0x18000b456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b45b  test    eax, eax
0x18000b45d  jnz     loc_18000B5B4
0x18000b463  mov     ecx, [rbp+arg_10]
0x18000b466  sub     ecx, 1
0x18000b469  jz      loc_18000B596
0x18000b46f  cmp     ecx, 0Eh
0x18000b472  jnz     short loc_18000B447
0x18000b474  xorps   xmm0, xmm0
0x18000b477  movdqu  [rbp+var_48], xmm0
0x18000b47c  lea     r8, [rbp+var_48]
0x18000b480  lea     rdx, [rbp+var_28]
0x18000b484  mov     rcx, [rbp+ppvObject]
0x18000b488  call    ?ProcessEndXmlElement@@YAJPEAUIXmlReader@@PEAUMasterDatastoreContext@@AEAV?$shared_ptr@VCConfigSource@@@std@@@Z; ProcessEndXmlElement(IXmlReader *,MasterDatastoreContext *,std::shared_ptr<CConfigSource> &)
0x18000b48d  mov     rcx, [rbp+28h]; this
0x18000b491  test    eax, eax
0x18000b493  js      loc_18000B6BD
0x18000b499  mov     rsi, qword ptr [rbp+var_48]
0x18000b49d  test    rsi, rsi
0x18000b4a0  jz      short loc_18000B50C
0x18000b4a2  mov     rax, [rbx+8]
0x18000b4a6  lea     rcx, [rbp+var_48]
0x18000b4aa  cmp     rcx, rax
0x18000b4ad  jnb     loc_18000B552
0x18000b4b3  lea     rcx, [rbp+var_48]
0x18000b4b7  cmp     [rbx], rcx
0x18000b4ba  ja      loc_18000B552
0x18000b4c0  lea     rdi, [rbp+var_48]
0x18000b4c4  sub     rdi, [rbx]
0x18000b4c7  cmp     rax, [rbx+10h]
0x18000b4cb  jnz     short loc_18000B4D5
0x18000b4cd  mov     rcx, rbx
0x18000b4d0  call    ?_Reserve@?$vector@V?$shared_ptr@VCConfigSource@@@std@@V?$allocator@V?$shared_ptr@VCConfigSource@@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::shared_ptr<CConfigSource>>::_Reserve(unsigned __int64)
0x18000b4d5  and     rdi, 0FFFFFFFFFFFFFFF0h
0x18000b4d9  mov     r8, [rbx]
0x18000b4dc  add     r8, rdi
0x18000b4df  mov     rdx, [rbx+8]
0x18000b4e3  mov     [rdx], r14
0x18000b4e6  mov     [rdx+8], r14
0x18000b4ea  cmp     rdx, r8
0x18000b4ed  jz      short loc_18000B507
0x18000b4ef  mov     rax, [r8+8]
0x18000b4f3  mov     [rdx+8], rax
0x18000b4f7  mov     [r8+8], r14
0x18000b4fb  mov     rcx, [rdx]
0x18000b4fe  mov     rax, [r8]
0x18000b501  mov     [rdx], rax
0x18000b504  mov     [r8], rcx
0x18000b507  add     qword ptr [rbx+8], 10h
0x18000b50c  mov     rdi, qword ptr [rbp+var_48+8]
0x18000b510  test    rdi, rdi
0x18000b513  jz      short loc_18000B54D
0x18000b515  mov     eax, r15d
0x18000b518  lock xadd [rdi+8], eax
0x18000b51d  add     eax, r15d
0x18000b520  jnz     short loc_18000B54D
0x18000b522  mov     rax, [rdi]
0x18000b525  mov     rcx, rdi
0x18000b528  mov     rax, [rax]
0x18000b52b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b530  mov     eax, r15d
0x18000b533  lock xadd [rdi+0Ch], eax
0x18000b538  add     eax, r15d
0x18000b53b  jnz     short loc_18000B54D
0x18000b53d  mov     rax, [rdi]
0x18000b540  mov     rcx, rdi
0x18000b543  mov     rax, [rax+8]
0x18000b547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b54c  nop
0x18000b54d  jmp     loc_18000B447
0x18000b552  cmp     rax, [rbx+10h]
0x18000b556  jnz     short loc_18000B560
0x18000b558  mov     rcx, rbx
0x18000b55b  call    ?_Reserve@?$vector@V?$shared_ptr@VCConfigSource@@@std@@V?$allocator@V?$shared_ptr@VCConfigSource@@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::shared_ptr<CConfigSource>>::_Reserve(unsigned __int64)
0x18000b560  mov     rcx, [rbx+8]
0x18000b564  mov     [rcx], r14
0x18000b567  mov     [rcx+8], r14
0x18000b56b  lea     rax, [rbp+var_48]
0x18000b56f  cmp     rcx, rax
0x18000b572  jz      short loc_18000B588
0x18000b574  mov     rax, qword ptr [rbp+var_48+8]
0x18000b578  mov     [rcx+8], rax
0x18000b57c  mov     rdi, r14
0x18000b57f  mov     [rcx], rsi
0x18000b582  mov     qword ptr [rbp+var_48], r14
0x18000b586  jmp     short loc_18000B58C
0x18000b588  mov     rdi, qword ptr [rbp+var_48+8]
0x18000b58c  add     qword ptr [rbx+8], 10h
0x18000b591  jmp     loc_18000B510
0x18000b596  lea     rdx, [rbp+var_28]; struct MasterDatastoreContext *
0x18000b59a  mov     rcx, [rbp+ppvObject]; struct IXmlReader *
0x18000b59e  call    ?ProcessNewXmlElement@@YAJPEAUIXmlReader@@PEAUMasterDatastoreContext@@@Z; ProcessNewXmlElement(IXmlReader *,MasterDatastoreContext *)
0x18000b5a3  mov     rcx, [rbp+28h]; this
0x18000b5a7  test    eax, eax
0x18000b5a9  js      loc_18000B669
0x18000b5af  jmp     loc_18000B447
0x18000b5b4  mov     rcx, [rbp+28h]; this
0x18000b5b8  test    eax, eax
0x18000b5ba  js      loc_18000B654
0x18000b5c0  mov     rdx, [rbx+8]
0x18000b5c4  mov     r8, rdx
0x18000b5c7  sub     r8, [rbx]
0x18000b5ca  sar     r8, 4
0x18000b5ce  mov     rcx, [rbx]
0x18000b5d1  call    ??$_Sort@PEAV?$shared_ptr@VCConfigSource@@@std@@_JP6AHV?$shared_ptr@$$CBVCConfigSource@@@2@0@_E@std@@YAXPEAV?$shared_ptr@VCConfigSource@@@0@0_JP6AHV?$shared_ptr@$$CBVCConfigSource@@@0@2@_E@Z
0x18000b5d6  cmp     qword ptr [rbp+var_18], r14
0x18000b5da  jz      short loc_18000B5E2
0x18000b5dc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b5e1  nop
0x18000b5e2  mov     rdi, qword ptr [rbp+var_18+8]
0x18000b5e6  test    rdi, rdi
0x18000b5e9  jz      short loc_18000B623
0x18000b5eb  mov     eax, r15d
0x18000b5ee  lock xadd [rdi+8], eax
0x18000b5f3  add     eax, r15d
0x18000b5f6  jnz     short loc_18000B623
0x18000b5f8  mov     rax, [rdi]
0x18000b5fb  mov     rcx, rdi
0x18000b5fe  mov     rax, [rax]
0x18000b601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b606  mov     eax, r15d
0x18000b609  lock xadd [rdi+0Ch], eax
0x18000b60e  add     eax, r15d
0x18000b611  jnz     short loc_18000B623
0x18000b613  mov     rax, [rdi]
0x18000b616  mov     rcx, rdi
0x18000b619  mov     rax, [rax+8]
0x18000b61d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b622  nop
0x18000b623  mov     rcx, [rbp+ppvObject]
0x18000b627  test    rcx, rcx
0x18000b62a  jz      short loc_18000B63D
0x18000b62c  mov     [rbp+ppvObject], r14
0x18000b630  mov     rax, [rcx]
0x18000b633  mov     rax, [rax+10h]
0x18000b637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b63c  nop
0x18000b63d  mov     rax, rbx
0x18000b640  mov     rbx, [rsp+70h+arg_8]
0x18000b648  add     rsp, 70h
0x18000b64c  pop     r15
0x18000b64e  pop     r14
0x18000b650  pop     rdi
0x18000b651  pop     rsi
0x18000b652  pop     rbp
0x18000b653  retn
0x18000b654  mov     r9d, eax; char *
0x18000b657  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000b65e  mov     edx, 160h; void *
0x18000b663  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000b669  mov     r9d, eax; char *
0x18000b66c  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000b673  mov     edx, 14Eh; void *
0x18000b678  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000b67e  mov     r9d, eax; char *
0x18000b681  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000b688  mov     edx, 140h; void *
0x18000b68d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000b693  mov     r9d, eax; char *
0x18000b696  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000b69d  mov     edx, 143h; void *
0x18000b6a2  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000b6a8  mov     r9d, eax; char *
0x18000b6ab  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000b6b2  mov     edx, 146h; void *
0x18000b6b7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000b6bd  mov     r9d, eax; char *
0x18000b6c0  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18000b6c7  mov     edx, 155h; void *
0x18000b6cc  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
