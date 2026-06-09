# CDataSrc::ParseProviderString(void)

- ea: `0x18008fe60`
- end: `0x1800900bc`
- name: `?ParseProviderString@CDataSrc@@AEAAXXZ`
- size: `604`
- prototype: `void __fastcall(CDataSrc *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180094870`

## callees

- `0x18005f550`
- `0x18008fe60`
- `0x180090c90`
- `0x1800f8324`
- `0x1800f8424`
- `0x18017504c`
- `0x180188d90`
- `0x18018a123`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008ff24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008ffc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009006a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008ff24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008ffc7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009006a`
- `OLEAUT32!__imp_VariantClear` at `0x18008ff1a`
- `OLEAUT32!__imp_VariantClear` at `0x18008ffbd`
- `OLEAUT32!__imp_VariantClear` at `0x180090060`
- `OLEAUT32!__imp_VariantClear` at `0x18008ff1a`
- `OLEAUT32!__imp_VariantClear` at `0x18008ffbd`
- `OLEAUT32!__imp_VariantClear` at `0x180090060`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CDataSrc::ParseProviderString(CDataSrc *this)
{
  CDataSrc *v2; // r12
  int Properties; // r15d
  void *v4; // rbx
  VARIANTARG *v5; // rsi
  int v6; // r15d
  void *v7; // rbx
  VARIANTARG *v8; // rsi
  int v9; // r15d
  void *v10; // rbx
  VARIANTARG *v11; // rsi
  unsigned int v12[2]; // [rsp+30h] [rbp-50h] BYREF
  unsigned int v13[2]; // [rsp+38h] [rbp-48h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-40h] BYREF
  VARIANTARG *v15; // [rsp+48h] [rbp-38h]
  struct tagDBPROPIDSET v16; // [rsp+50h] [rbp-30h] BYREF

  pv = 0;
  v12[0] = 160;
  *((_DWORD *)&v16.guidPropertySet + 4) = 0;
  v16.rgPropertyIDs = v12;
  v16.cPropertyIDs = 1;
  v16.guidPropertySet = DBPROPSET_DBINIT;
  v13[0] = 0;
  v2 = (CDataSrc *)((char *)this + 8);
  Properties = CDataSrc::GetProperties((CDataSrc *)((char *)this + 8), 1u, &v16, v13, (struct tagDBPROPSET **)&pv);
  v4 = pv;
  if ( pv )
  {
    *(_QWORD *)v13 = pv;
    v5 = *(VARIANTARG **)pv;
    *(_QWORD *)v12 = v5;
    v15 = v5 + 2;
    Properties = CDataSrc::ResolveApplicationFromString(this, (const struct tagDBPROPSET *)pv);
    if ( v5 != (VARIANTARG *)-48LL )
      VariantClear(v5 + 2);
    CoTaskMemFree(v5);
    CoTaskMemFree_0(v4);
  }
  if ( Properties < 0 )
  {
    v13[0] = 0x20000;
    *((_DWORD *)&v16.guidPropertySet + 4) = 0;
    v16.rgPropertyIDs = v13;
    v16.cPropertyIDs = 1;
    v16.guidPropertySet = DBPROPSET_DBINIT;
    v12[0] = 0;
    v6 = CDataSrc::GetProperties(v2, 1u, &v16, v12, (struct tagDBPROPSET **)&pv);
    v7 = pv;
    if ( pv )
    {
      v15 = (VARIANTARG *)pv;
      v8 = *(VARIANTARG **)pv;
      *(_QWORD *)v13 = v8;
      *(_QWORD *)v12 = v8 + 2;
      v6 = CDataSrc::ResolveApplicationFromSingleConfig(this, (const struct tagDBPROPSET *)pv);
      if ( v8 != (VARIANTARG *)-48LL )
        VariantClear(v8 + 2);
      CoTaskMemFree(v8);
      CoTaskMemFree_0(v7);
    }
    if ( v6 < 0 )
    {
      v13[0] = 0x10000;
      *((_DWORD *)&v16.guidPropertySet + 4) = 0;
      v16.rgPropertyIDs = v13;
      v16.cPropertyIDs = 1;
      v16.guidPropertySet = DBPROPSET_DBINIT;
      v12[0] = 0;
      v9 = CDataSrc::GetProperties(v2, 1u, &v16, v12, (struct tagDBPROPSET **)&pv);
      v10 = pv;
      if ( pv )
      {
        v15 = (VARIANTARG *)pv;
        v11 = *(VARIANTARG **)pv;
        *(_QWORD *)v13 = v11;
        *(_QWORD *)v12 = v11 + 2;
        v9 = CDataSrc::ResolveApplicationFromMultiConfigs(this, (const struct tagDBPROPSET *)pv);
        if ( v11 != (VARIANTARG *)-48LL )
          VariantClear(v11 + 2);
        CoTaskMemFree(v11);
        CoTaskMemFree_0(v10);
      }
      if ( v9 < 0 )
        std::wstring::_Assign<wchar_t>((char *)this + 80, L"Windows", 7);
    }
  }
}

```

## disassembly

```asm
0x18008fe60  mov     [rsp-28h+arg_8], rbx
0x18008fe65  mov     [rsp-28h+arg_10], rsi
0x18008fe6a  push    rbp
0x18008fe6b  push    rdi
0x18008fe6c  push    r12
0x18008fe6e  push    r14
0x18008fe70  push    r15
0x18008fe72  mov     rbp, rsp
0x18008fe75  sub     rsp, 80h
0x18008fe7c  mov     rax, cs:__security_cookie
0x18008fe83  xor     rax, rsp
0x18008fe86  mov     [rbp+var_10], rax
0x18008fe8a  mov     r14, rcx
0x18008fe8d  mov     [rbp+pv], 0
0x18008fe95  movups  xmm0, xmmword ptr cs:DBPROPSET_DBINIT.Data1
0x18008fe9c  mov     [rbp+var_50], 0A0h
0x18008fea3  mov     dword ptr [rbp+var_30+1Ch], 0
0x18008feaa  lea     rax, [rbp+var_50]
0x18008feae  mov     [rbp+var_30.rgPropertyIDs], rax
0x18008feb2  mov     edi, 1
0x18008feb7  mov     [rbp+var_30.cPropertyIDs], edi
0x18008feba  movdqu  xmmword ptr [rbp+var_30.guidPropertySet.Data1], xmm0
0x18008febf  mov     [rbp+var_48], 0
0x18008fec6  lea     r12, [rcx+8]
0x18008feca  lea     rax, [rbp+pv]
0x18008fece  mov     [rsp+80h+var_60], rax; struct tagDBPROPSET **
0x18008fed3  lea     r9, [rbp+var_48]; unsigned int *
0x18008fed7  lea     r8, [rbp+var_30]; struct tagDBPROPIDSET *
0x18008fedb  mov     edx, edi; unsigned int
0x18008fedd  mov     rcx, r12; this
0x18008fee0  call    ?GetProperties@CDataSrc@@UEAAJKQEBUtagDBPROPIDSET@@PEAKPEAPEAUtagDBPROPSET@@@Z; CDataSrc::GetProperties(ulong,tagDBPROPIDSET const * const,ulong *,tagDBPROPSET * *)
0x18008fee5  mov     r15d, eax
0x18008fee8  mov     rbx, [rbp+pv]
0x18008feec  test    rbx, rbx
0x18008feef  jz      short loc_18008FF38
0x18008fef1  mov     qword ptr [rbp+var_48], rbx
0x18008fef5  mov     rsi, [rbx]
0x18008fef8  mov     qword ptr [rbp+var_50], rsi
0x18008fefc  lea     rdi, [rsi+30h]
0x18008ff00  mov     [rbp+var_38], rdi
0x18008ff04  mov     rdx, rbx; struct tagDBPROPSET *
0x18008ff07  mov     rcx, r14; this
0x18008ff0a  call    ?ResolveApplicationFromString@CDataSrc@@AEAAJPEBUtagDBPROPSET@@@Z; CDataSrc::ResolveApplicationFromString(tagDBPROPSET const *)
0x18008ff0f  mov     r15d, eax
0x18008ff12  test    rdi, rdi
0x18008ff15  jz      short loc_18008FF21
0x18008ff17  mov     rcx, rdi; pvarg
0x18008ff1a  call    cs:__imp_VariantClear
0x18008ff20  nop
0x18008ff21  mov     rcx, rsi; pv
0x18008ff24  call    cs:__imp_CoTaskMemFree
0x18008ff2a  nop
0x18008ff2b  mov     rcx, rbx; pv
0x18008ff2e  call    CoTaskMemFree_0
0x18008ff33  mov     edi, 1
0x18008ff38  test    r15d, r15d
0x18008ff3b  jns     loc_180090094
0x18008ff41  movups  xmm0, xmmword ptr cs:DBPROPSET_DBINIT.Data1
0x18008ff48  mov     [rbp+var_48], 20000h
0x18008ff4f  mov     dword ptr [rbp+var_30+1Ch], 0
0x18008ff56  lea     rax, [rbp+var_48]
0x18008ff5a  mov     [rbp+var_30.rgPropertyIDs], rax
0x18008ff5e  mov     [rbp+var_30.cPropertyIDs], edi
0x18008ff61  movdqu  xmmword ptr [rbp+var_30.guidPropertySet.Data1], xmm0
0x18008ff66  mov     [rbp+var_50], 0
0x18008ff6d  lea     rax, [rbp+pv]
0x18008ff71  mov     [rsp+80h+var_60], rax; struct tagDBPROPSET **
0x18008ff76  lea     r9, [rbp+var_50]; unsigned int *
0x18008ff7a  lea     r8, [rbp+var_30]; struct tagDBPROPIDSET *
0x18008ff7e  mov     edx, edi; unsigned int
0x18008ff80  mov     rcx, r12; this
0x18008ff83  call    ?GetProperties@CDataSrc@@UEAAJKQEBUtagDBPROPIDSET@@PEAKPEAPEAUtagDBPROPSET@@@Z; CDataSrc::GetProperties(ulong,tagDBPROPIDSET const * const,ulong *,tagDBPROPSET * *)
0x18008ff88  mov     r15d, eax
0x18008ff8b  mov     rbx, [rbp+pv]
0x18008ff8f  test    rbx, rbx
0x18008ff92  jz      short loc_18008FFDB
0x18008ff94  mov     [rbp+var_38], rbx
0x18008ff98  mov     rsi, [rbx]
0x18008ff9b  mov     qword ptr [rbp+var_48], rsi
0x18008ff9f  lea     rdi, [rsi+30h]
0x18008ffa3  mov     qword ptr [rbp+var_50], rdi
0x18008ffa7  mov     rdx, rbx; struct tagDBPROPSET *
0x18008ffaa  mov     rcx, r14; this
0x18008ffad  call    ?ResolveApplicationFromSingleConfig@CDataSrc@@AEAAJPEBUtagDBPROPSET@@@Z; CDataSrc::ResolveApplicationFromSingleConfig(tagDBPROPSET const *)
0x18008ffb2  mov     r15d, eax
0x18008ffb5  test    rdi, rdi
0x18008ffb8  jz      short loc_18008FFC4
0x18008ffba  mov     rcx, rdi; pvarg
0x18008ffbd  call    cs:__imp_VariantClear
0x18008ffc3  nop
0x18008ffc4  mov     rcx, rsi; pv
0x18008ffc7  call    cs:__imp_CoTaskMemFree
0x18008ffcd  nop
0x18008ffce  mov     rcx, rbx; pv
0x18008ffd1  call    CoTaskMemFree_0
0x18008ffd6  mov     edi, 1
0x18008ffdb  test    r15d, r15d
0x18008ffde  jns     loc_180090094
0x18008ffe4  movups  xmm0, xmmword ptr cs:DBPROPSET_DBINIT.Data1
0x18008ffeb  mov     [rbp+var_48], 10000h
0x18008fff2  mov     dword ptr [rbp+var_30+1Ch], 0
0x18008fff9  lea     rax, [rbp+var_48]
0x18008fffd  mov     [rbp+var_30.rgPropertyIDs], rax
0x180090001  mov     [rbp+var_30.cPropertyIDs], edi
0x180090004  movdqu  xmmword ptr [rbp+var_30.guidPropertySet.Data1], xmm0
0x180090009  mov     [rbp+var_50], 0
0x180090010  lea     rax, [rbp+pv]
0x180090014  mov     [rsp+80h+var_60], rax; struct tagDBPROPSET **
0x180090019  lea     r9, [rbp+var_50]; unsigned int *
0x18009001d  lea     r8, [rbp+var_30]; struct tagDBPROPIDSET *
0x180090021  mov     edx, edi; unsigned int
0x180090023  mov     rcx, r12; this
0x180090026  call    ?GetProperties@CDataSrc@@UEAAJKQEBUtagDBPROPIDSET@@PEAKPEAPEAUtagDBPROPSET@@@Z; CDataSrc::GetProperties(ulong,tagDBPROPIDSET const * const,ulong *,tagDBPROPSET * *)
0x18009002b  mov     r15d, eax
0x18009002e  mov     rbx, [rbp+pv]
0x180090032  test    rbx, rbx
0x180090035  jz      short loc_180090079
0x180090037  mov     [rbp+var_38], rbx
0x18009003b  mov     rsi, [rbx]
0x18009003e  mov     qword ptr [rbp+var_48], rsi
0x180090042  lea     rdi, [rsi+30h]
0x180090046  mov     qword ptr [rbp+var_50], rdi
0x18009004a  mov     rdx, rbx; struct tagDBPROPSET *
0x18009004d  mov     rcx, r14; this
0x180090050  call    ?ResolveApplicationFromMultiConfigs@CDataSrc@@AEAAJPEBUtagDBPROPSET@@@Z; CDataSrc::ResolveApplicationFromMultiConfigs(tagDBPROPSET const *)
0x180090055  mov     r15d, eax
0x180090058  test    rdi, rdi
0x18009005b  jz      short loc_180090067
0x18009005d  mov     rcx, rdi; pvarg
0x180090060  call    cs:__imp_VariantClear
0x180090066  nop
0x180090067  mov     rcx, rsi; pv
0x18009006a  call    cs:__imp_CoTaskMemFree
0x180090070  nop
0x180090071  mov     rcx, rbx; pv
0x180090074  call    CoTaskMemFree_0
0x180090079  test    r15d, r15d
0x18009007c  jns     short loc_180090094
0x18009007e  lea     rcx, [r14+50h]
0x180090082  mov     r8d, 7
0x180090088  lea     rdx, aWindows; "Windows"
0x18009008f  call    ??$_Assign@_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@QEB_W_K@Z; std::wstring::_Assign<wchar_t>(wchar_t const * const,unsigned __int64)
0x180090094  mov     rcx, [rbp+var_10]
0x180090098  xor     rcx, rsp; StackCookie
0x18009009b  call    __security_check_cookie
0x1800900a0  lea     r11, [rsp+80h+var_s0]
0x1800900a8  mov     rbx, [r11+38h]
0x1800900ac  mov     rsi, [r11+40h]
0x1800900b0  mov     rsp, r11
0x1800900b3  pop     r15
0x1800900b5  pop     r14
0x1800900b7  pop     r12
0x1800900b9  pop     rdi
0x1800900ba  pop     rbp
0x1800900bb  retn
```
