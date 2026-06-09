# WaasMedic::EdgeUpdateRepairPlugin::DetectMissingEdgeUpdate(bool &)

- ea: `0x18000c228`
- end: `0x18000c477`
- name: `?DetectMissingEdgeUpdate@EdgeUpdateRepairPlugin@WaasMedic@@AEAAJAEA_N@Z`
- size: `591`
- prototype: `__int64 __fastcall(WaasMedic::EdgeUpdateRepairPlugin *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000c150`

## callees

- `0x1800012bc`
- `0x180003bb0`
- `0x180005ef1`
- `0x1800070cc`
- `0x180007590`
- `0x18000b6ec`
- `0x18000c228`
- `0x180016c9c`
- `0x18002543c`
- `0x180028894`
- `0x180028ec8`
- `0x18002acd8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c3b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000c3b1`

## string_xrefs

- `0x18000c274`: `Software\Microsoft\EdgeUpdate`
- `0x18000c2a7`: `Software\WOW6432Node\Microsoft\EdgeUpdate`
- `0x18000c2bd`: `Software\WOW6432Node\Microsoft\EdgeUpdate`
- `0x18000c2fc`: `EdgeUpdate: Regkey for EdgeUpdate does not exist %s`
- `0x18000c34a`: `EdgeUpdate: Path Value cannot be read under the regkey %s`
- `0x18000c393`: `EdgeUpdate: Path regkey exists but FileExists failed %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WaasMedic::EdgeUpdateRepairPlugin::DetectMissingEdgeUpdate(
        WaasMedic::EdgeUpdateRepairPlugin *this,
        bool *a2)
{
  __int64 v4; // r8
  _WORD *v5; // rbx
  __int64 v6; // rcx
  void **v7; // rdx
  __int64 v8; // rcx
  int v9; // esi
  int v10; // ebx
  void **v11; // r8
  void **v12; // rdx
  void *v13; // rdi
  void **v14; // r8
  __int64 v15; // rax
  const struct _tlgProvider_t *v16; // rax
  int v17; // r9d
  const struct _tlgProvider_t *v18; // r8
  __int64 v19; // rax
  _QWORD *v20; // rax
  LPVOID pv; // [rsp+40h] [rbp-19h] BYREF
  int v23; // [rsp+48h] [rbp-11h] BYREF
  _QWORD v24[2]; // [rsp+50h] [rbp-9h] BYREF
  _QWORD *v25; // [rsp+60h] [rbp+7h] BYREF
  void *v26[2]; // [rsp+68h] [rbp+Fh] BYREF
  __int64 v27; // [rsp+78h] [rbp+1Fh]
  unsigned __int64 v28; // [rsp+80h] [rbp+27h]

  *a2 = 0;
  *(_OWORD *)v26 = 0;
  v27 = 0;
  v28 = 0;
  std::wstring::_Construct<1,unsigned short const *>(v26, L"Software\\Microsoft\\EdgeUpdate", 29);
  if ( v28 < 0x29 )
  {
    std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
      v26,
      41,
      v4,
      L"Software\\WOW6432Node\\Microsoft\\EdgeUpdate");
  }
  else
  {
    v5 = v26[0];
    v27 = 41;
    memmove_0(v26[0], L"Software\\WOW6432Node\\Microsoft\\EdgeUpdate", 0x52u);
    v5[41] = 0;
  }
  v7 = v26;
  if ( v28 > 7 )
    v7 = (void **)v26[0];
  v9 = WaasMedic::RegKeyExists(v6, v7);
  if ( v9 < 0 )
  {
    v10 = 1;
    *a2 = 1;
    v11 = v26;
    if ( v28 > 7 )
      v11 = (void **)v26[0];
    LogLevelW(2u, L"EdgeUpdate: Regkey for EdgeUpdate does not exist %s", v11);
LABEL_23:
    v16 = WaasMedic::TelemetryProvider::Provider();
    v18 = v16;
    if ( *(_DWORD *)v16 > 5u )
    {
      v19 = *((_QWORD *)v16 + 3);
      if ( (*((_QWORD *)v18 + 2) & 0x400000000000LL) != 0 && (v19 & 0x400000000000LL) == v19 )
      {
        v23 = v9;
        LODWORD(pv) = v10;
        v20 = (_QWORD *)((char *)this + 120);
        if ( *((_QWORD *)this + 18) > 0xFu )
          v20 = (_QWORD *)*v20;
        v25 = v20;
        v24[0] = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v18,
          (unsigned int)byte_18008858B,
          (_DWORD)v18,
          v17,
          (__int64)v24,
          (__int64)&v25,
          (__int64)&pv,
          (__int64)&v23);
      }
    }
    goto LABEL_29;
  }
  pv = 0;
  v12 = v26;
  if ( v28 > 7 )
    v12 = (void **)v26[0];
  v9 = WaasMedic::RegQueryStringValue(v8, v12, L"path", &pv);
  v13 = pv;
  if ( v9 >= 0 )
  {
    v10 = 0;
    v24[0] = pv;
    v15 = -1;
    do
      ++v15;
    while ( *((_WORD *)pv + v15) );
    v24[1] = v15;
    if ( !(unsigned __int8)WaasMedic::FileExists(v24) )
    {
      *a2 = 1;
      LogLevelW(2u, L"EdgeUpdate: Path regkey exists but FileExists failed %s", v13);
      v10 = 4;
    }
  }
  else
  {
    v14 = v26;
    if ( v28 > 7 )
      v14 = (void **)v26[0];
    LogLevelW(2u, L"EdgeUpdate: Path Value cannot be read under the regkey %s", v14);
    *a2 = 1;
    v10 = 2;
  }
  if ( v13 )
    CoTaskMemFree(v13);
  if ( v10 )
    goto LABEL_23;
LABEL_29:
  std::wstring::~wstring(v26);
  return 0;
}

```

## disassembly

```asm
0x18000c228  mov     [rsp-8+arg_0], rbx
0x18000c22d  mov     [rsp-8+arg_10], rsi
0x18000c232  push    rbp
0x18000c233  push    rdi
0x18000c234  push    r12
0x18000c236  push    r14
0x18000c238  push    r15
0x18000c23a  lea     rbp, [rsp-37h]
0x18000c23f  sub     rsp, 90h
0x18000c246  mov     rax, cs:__security_cookie
0x18000c24d  xor     rax, rsp
0x18000c250  mov     [rbp+57h+var_28], rax
0x18000c254  mov     r14, rdx
0x18000c257  mov     r15, rcx
0x18000c25a  xor     r12d, r12d
0x18000c25d  mov     [rdx], r12b
0x18000c260  xorps   xmm0, xmm0
0x18000c263  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x18000c267  mov     [rbp+57h+var_38], r12
0x18000c26b  mov     [rbp+57h+var_30], r12
0x18000c26f  lea     r8d, [r12+1Dh]
0x18000c274  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\EdgeUpdate"
0x18000c27b  lea     rcx, [rbp+57h+var_48]
0x18000c27f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000c284  nop
0x18000c285  lea     edx, [r12+29h]
0x18000c28a  cmp     [rbp+57h+var_30], rdx
0x18000c28e  jb      short loc_18000C2BD
0x18000c290  lea     rbx, [rbp+57h+var_48]
0x18000c294  cmp     [rbp+57h+var_30], 7
0x18000c299  cmova   rbx, [rbp+57h+var_48]
0x18000c29e  mov     [rbp+57h+var_38], rdx
0x18000c2a2  lea     r8d, [r12+52h]; Size
0x18000c2a7  lea     rdx, aSoftwareWow643; "Software\\WOW6432Node\\Microsoft\\EdgeU"...
0x18000c2ae  mov     rcx, rbx; void *
0x18000c2b1  call    memmove_0
0x18000c2b6  mov     [rbx+52h], r12w
0x18000c2bb  jmp     short loc_18000C2CD
0x18000c2bd  lea     r9, aSoftwareWow643; "Software\\WOW6432Node\\Microsoft\\EdgeU"...
0x18000c2c4  lea     rcx, [rbp+57h+var_48]
0x18000c2c8  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18000c2cd  lea     rdx, [rbp+57h+var_48]
0x18000c2d1  cmp     [rbp+57h+var_30], 7
0x18000c2d6  cmova   rdx, [rbp+57h+var_48]
0x18000c2db  call    ?RegKeyExists@WaasMedic@@YAJPEAUHKEY__@@PEBGW4RegistryHiveType@1@@Z; WaasMedic::RegKeyExists(HKEY__ *,ushort const *,WaasMedic::RegistryHiveType)
0x18000c2e0  mov     esi, eax
0x18000c2e2  test    eax, eax
0x18000c2e4  jns     short loc_18000C310
0x18000c2e6  mov     ebx, 1
0x18000c2eb  mov     [r14], bl
0x18000c2ee  lea     r8, [rbp+57h+var_48]
0x18000c2f2  cmp     [rbp+57h+var_30], 7
0x18000c2f7  cmova   r8, [rbp+57h+var_48]
0x18000c2fc  lea     rdx, aEdgeupdateRegk; "EdgeUpdate: Regkey for EdgeUpdate does "...
0x18000c303  lea     ecx, [rbx+1]; unsigned __int8
0x18000c306  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18000c30b  jmp     loc_18000C3BF
0x18000c310  mov     [rbp+57h+pv], r12
0x18000c314  lea     rdx, [rbp+57h+var_48]
0x18000c318  cmp     [rbp+57h+var_30], 7
0x18000c31d  cmova   rdx, [rbp+57h+var_48]
0x18000c322  lea     r9, [rbp+57h+pv]
0x18000c326  lea     r8, aPath_0; "path"
0x18000c32d  call    ?RegQueryStringValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1PEAPEAGW4RegistryHiveType@1@@Z; WaasMedic::RegQueryStringValue(HKEY__ *,ushort const *,ushort const *,ushort * *,WaasMedic::RegistryHiveType)
0x18000c332  mov     esi, eax
0x18000c334  mov     rdi, [rbp+57h+pv]
0x18000c338  test    eax, eax
0x18000c33a  jns     short loc_18000C366
0x18000c33c  lea     r8, [rbp+57h+var_48]
0x18000c340  cmp     [rbp+57h+var_30], 7
0x18000c345  cmova   r8, [rbp+57h+var_48]
0x18000c34a  lea     rdx, aEdgeupdatePath_0; "EdgeUpdate: Path Value cannot be read u"...
0x18000c351  mov     ecx, 2; unsigned __int8
0x18000c356  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18000c35b  mov     byte ptr [r14], 1
0x18000c35f  mov     ebx, 2
0x18000c364  jmp     short loc_18000C3A9
0x18000c366  mov     ebx, r12d
0x18000c369  mov     [rbp+57h+var_60], rdi
0x18000c36d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c371  inc     rax
0x18000c374  cmp     [rdi+rax*2], r12w
0x18000c379  jnz     short loc_18000C371
0x18000c37b  mov     [rbp+57h+var_58], rax
0x18000c37f  lea     rcx, [rbp+57h+var_60]
0x18000c383  call    ?FileExists@WaasMedic@@YA_NAEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@@Z; WaasMedic::FileExists(std::basic_string_view<ushort> const &)
0x18000c388  test    al, al
0x18000c38a  jnz     short loc_18000C3A9
0x18000c38c  mov     byte ptr [r14], 1
0x18000c390  mov     r8, rdi
0x18000c393  lea     rdx, aEdgeupdatePath; "EdgeUpdate: Path regkey exists but File"...
0x18000c39a  mov     ecx, 2; unsigned __int8
0x18000c39f  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18000c3a4  mov     ebx, 4
0x18000c3a9  test    rdi, rdi
0x18000c3ac  jz      short loc_18000C3B7
0x18000c3ae  mov     rcx, rdi; pv
0x18000c3b1  call    cs:__imp_CoTaskMemFree
0x18000c3b7  test    ebx, ebx
0x18000c3b9  jz      loc_18000C444
0x18000c3bf  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x18000c3c4  mov     r8, rax
0x18000c3c7  mov     ecx, [rax]
0x18000c3c9  cmp     ecx, 5
0x18000c3cc  jbe     short loc_18000C444
0x18000c3ce  mov     rax, [rax+18h]
0x18000c3d2  mov     rcx, [r8+10h]
0x18000c3d6  mov     rdx, 400000000000h
0x18000c3e0  test    rdx, rcx
0x18000c3e3  jz      short loc_18000C444
0x18000c3e5  mov     rcx, rax
0x18000c3e8  and     rcx, rdx
0x18000c3eb  cmp     rcx, rax
0x18000c3ee  jnz     short loc_18000C444
0x18000c3f0  mov     [rbp+57h+var_68], esi
0x18000c3f3  mov     dword ptr [rbp+57h+pv], ebx
0x18000c3f6  lea     rax, [r15+78h]
0x18000c3fa  cmp     qword ptr [rax+18h], 0Fh
0x18000c3ff  jbe     short loc_18000C404
0x18000c401  mov     rax, [rax]
0x18000c404  mov     [rbp+57h+var_50], rax
0x18000c408  mov     [rbp+57h+var_60], 1000000h
0x18000c410  lea     rax, [rbp+57h+var_68]
0x18000c414  mov     [rsp+0B0h+var_78], rax
0x18000c419  lea     rax, [rbp+57h+pv]
0x18000c41d  mov     [rsp+0B0h+var_80], rax
0x18000c422  lea     rax, [rbp+57h+var_50]
0x18000c426  mov     [rsp+0B0h+var_88], rax
0x18000c42b  lea     rax, [rbp+57h+var_60]
0x18000c42f  mov     [rsp+0B0h+var_90], rax
0x18000c434  lea     rdx, byte_18008858B
0x18000c43b  mov     rcx, r8
0x18000c43e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000c443  nop
0x18000c444  lea     rcx, [rbp+57h+var_48]; void *
0x18000c448  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000c44d  xor     eax, eax
0x18000c44f  mov     rcx, [rbp+57h+var_28]
0x18000c453  xor     rcx, rsp; StackCookie
0x18000c456  call    __security_check_cookie
0x18000c45b  lea     r11, [rsp+0B0h+var_20]
0x18000c463  mov     rbx, [r11+30h]
0x18000c467  mov     rsi, [r11+40h]
0x18000c46b  mov     rsp, r11
0x18000c46e  pop     r15
0x18000c470  pop     r14
0x18000c472  pop     r12
0x18000c474  pop     rdi
0x18000c475  pop     rbp
0x18000c476  retn
```
