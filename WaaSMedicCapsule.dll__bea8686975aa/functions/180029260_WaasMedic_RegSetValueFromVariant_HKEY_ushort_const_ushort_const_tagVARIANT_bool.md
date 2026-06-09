# WaasMedic::RegSetValueFromVariant(HKEY__ *,ushort const *,ushort const *,tagVARIANT *,bool)

- ea: `0x180029260`
- end: `0x1800294f9`
- name: `?RegSetValueFromVariant@WaasMedic@@YAJPEAUHKEY__@@PEBG1PEAUtagVARIANT@@_N@Z`
- size: `665`
- prototype: `__int64 __fastcall(WaasMedic *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int16 *, struct tagVARIANT *, bool)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x180021570`

## callees

- `0x180002278`
- `0x180016c9c`
- `0x18002543c`
- `0x180027c3c`
- `0x180029168`
- `0x180029214`
- `0x180029260`
- `0x180029500`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18002947f`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x18002947f`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800294a1`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800294a1`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800294e4`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800294e4`

## string_xrefs

- `0x18002935e`: `RegUtil: Error when attempting to set registry value from VARIANT. Sub key: [%s] Value name: [%s]. hr=0x%08X`

## pseudocode

```c
__int64 __fastcall WaasMedic::RegSetValueFromVariant(
        WaasMedic *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct tagVARIANT *a5)
{
  __int64 v8; // rcx
  int v9; // r14d
  int v10; // ecx
  __int64 v11; // rcx
  __int64 v12; // r9
  HRESULT v13; // eax
  HRESULT v14; // eax
  HRESULT v15; // ebx
  __int64 v16; // rcx
  const struct _tlgProvider_t *v17; // rax
  int v18; // r9d
  const struct _tlgProvider_t *v19; // r8
  __int64 v20; // rax
  SAFEARRAY *v21; // r15
  __int64 cElements; // r12
  __int64 v23; // r8
  __int64 v24; // [rsp+20h] [rbp-50h]
  const unsigned __int16 *v25; // [rsp+50h] [rbp-20h] BYREF
  HKEY v26; // [rsp+58h] [rbp-18h] BYREF
  unsigned __int16 *v27; // [rsp+60h] [rbp-10h] BYREF
  __int64 v28; // [rsp+68h] [rbp-8h] BYREF
  void *ppvData; // [rsp+A0h] [rbp+30h] BYREF
  int v30; // [rsp+B8h] [rbp+48h] BYREF

  ppvData = this;
  if ( !a4 )
    return 2147500035LL;
  v8 = *a4;
  v9 = (unsigned __int8)a5;
  if ( (unsigned int)v8 > 0x2011 )
    goto LABEL_27;
  if ( (_DWORD)v8 == 8209 )
  {
    v21 = (SAFEARRAY *)*((_QWORD *)a4 + 1);
    if ( SafeArrayGetDim(v21) == 1 )
    {
      ppvData = 0;
      cElements = v21->rgsabound[0].cElements;
      v15 = SafeArrayAccessData(v21, &ppvData);
      if ( v15 >= 0 )
      {
        v15 = WaasMedic::RegSetValue_Helper(ppvData, a2, v23, a3, 3, ppvData, cElements, (_BYTE)v9);
        if ( v15 >= 0 )
        {
          v15 = SafeArrayUnaccessData(v21);
          if ( v15 >= 0 )
            return (unsigned int)v15;
        }
      }
LABEL_28:
      LODWORD(v24) = v15;
      LogLevelW(
        2u,
        L"RegUtil: Error when attempting to set registry value from VARIANT. Sub key: [%s] Value name: [%s]. hr=0x%08X",
        a2,
        a3,
        v24);
      v17 = WaasMedic::TelemetryProvider::Provider();
      v19 = v17;
      if ( *(_DWORD *)v17 > 5u )
      {
        v20 = *((_QWORD *)v17 + 3);
        if ( (*((_QWORD *)v19 + 2) & 0x400000000000LL) != 0 && (v20 & 0x400000000000LL) == v20 )
        {
          LODWORD(ppvData) = v15;
          v27 = &gc_pszVersionString;
          v30 = v9;
          v25 = a3;
          v26 = a2;
          v28 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            (_DWORD)v19,
            (unsigned int)&byte_180089117,
            (_DWORD)v19,
            v18,
            (__int64)&v28,
            (__int64)&v27,
            (__int64)&v26,
            (__int64)&v25,
            (__int64)&v30,
            (__int64)&ppvData);
        }
      }
      return (unsigned int)v15;
    }
    goto LABEL_27;
  }
  if ( (unsigned int)v8 > 0x10 )
  {
    v8 = (unsigned int)(v8 - 17);
    if ( !(_DWORD)v8 )
    {
      v12 = *((unsigned __int8 *)a4 + 8);
      goto LABEL_36;
    }
    v8 = (unsigned int)(v8 - 1);
    if ( !(_DWORD)v8 )
    {
      v12 = a4[4];
      goto LABEL_36;
    }
    v8 = (unsigned int)(v8 - 1);
    if ( !(_DWORD)v8 )
      goto LABEL_15;
    v16 = (unsigned int)(v8 - 1);
    if ( !(_DWORD)v16 || (v16 = (unsigned int)(v16 - 1), !(_DWORD)v16) )
    {
      ppvData = (void *)*((_QWORD *)a4 + 1);
      v13 = WaasMedic::RegSetValue_Helper(v16, a2, a3, a3, 11, &ppvData, 8, (_BYTE)a5);
      goto LABEL_37;
    }
    v8 = (unsigned int)(v16 - 1);
    if ( (unsigned int)v8 < 2 )
      goto LABEL_15;
LABEL_27:
    v15 = -2147024809;
    goto LABEL_28;
  }
  if ( (_DWORD)v8 == 16 )
  {
    v12 = (unsigned int)*((char *)a4 + 8);
    goto LABEL_36;
  }
  if ( *a4 )
  {
    v10 = v8 - 1;
    if ( v10 )
    {
      v8 = (unsigned int)(v10 - 1);
      if ( !(_DWORD)v8 )
      {
LABEL_14:
        v12 = (unsigned int)*((__int16 *)a4 + 4);
LABEL_36:
        v13 = WaasMedic::RegSetDwordValue(v8, a2, a3, v12);
        goto LABEL_37;
      }
      v8 = (unsigned int)(v8 - 1);
      if ( !(_DWORD)v8 )
        goto LABEL_15;
      v11 = (unsigned int)(v8 - 5);
      if ( (_DWORD)v11 )
      {
        v8 = (unsigned int)(v11 - 2);
        if ( (_DWORD)v8 )
        {
          if ( (_DWORD)v8 == 1 )
            goto LABEL_14;
          goto LABEL_27;
        }
LABEL_15:
        v12 = *((unsigned int *)a4 + 2);
        goto LABEL_36;
      }
      v13 = WaasMedic::RegSetStringValue(v11, a2, a3, *((_QWORD *)a4 + 1), (_BYTE)a5);
LABEL_37:
      v15 = v13;
      goto LABEL_38;
    }
  }
  v14 = WaasMedic::RegDelValue();
  v15 = 0;
  if ( v14 != -2147024894 )
    v15 = v14;
LABEL_38:
  if ( v15 < 0 )
    goto LABEL_28;
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180029260  mov     [rsp-28h+arg_8], rbx
0x180029265  mov     [rsp-28h+arg_10], rsi
0x18002926a  mov     [rsp-28h+ppvData], rcx
0x18002926f  push    rbp
0x180029270  push    rdi
0x180029271  push    r12
0x180029273  push    r14
0x180029275  push    r15
0x180029277  mov     rbp, rsp
0x18002927a  sub     rsp, 70h
0x18002927e  mov     rdi, r8
0x180029281  mov     rsi, rdx
0x180029284  test    r9, r9
0x180029287  jnz     short loc_180029293
0x180029289  mov     eax, 80004003h
0x18002928e  jmp     loc_18002940D
0x180029293  movzx   ecx, word ptr [r9]
0x180029297  mov     eax, 2011h
0x18002929c  movzx   r14d, byte ptr [rbp+arg_20]
0x1800292a1  cmp     ecx, eax
0x1800292a3  ja      loc_18002934F
0x1800292a9  jz      loc_180029478
0x1800292af  cmp     ecx, 10h
0x1800292b2  ja      short loc_18002931C
0x1800292b4  jz      short loc_180029312
0x1800292b6  test    ecx, ecx
0x1800292b8  jz      short loc_1800292FE
0x1800292ba  sub     ecx, 1
0x1800292bd  jz      short loc_1800292FE
0x1800292bf  sub     ecx, 1
0x1800292c2  jz      short loc_1800292D8
0x1800292c4  sub     ecx, 1
0x1800292c7  jz      short loc_1800292E2
0x1800292c9  sub     ecx, 5
0x1800292cc  jz      short loc_1800292EB
0x1800292ce  sub     ecx, 2
0x1800292d1  jz      short loc_1800292E2
0x1800292d3  cmp     ecx, 1
0x1800292d6  jnz     short loc_18002934F
0x1800292d8  movsx   r9d, word ptr [r9+8]
0x1800292dd  jmp     loc_180029463
0x1800292e2  mov     r9d, [r9+8]
0x1800292e6  jmp     loc_180029463
0x1800292eb  mov     r9, [r9+8]
0x1800292ef  mov     byte ptr [rsp+70h+var_50], r14b
0x1800292f4  call    ?RegSetStringValue@WaasMedic@@YAJPEAUHKEY__@@PEBG11_NW4RegistryHiveType@1@@Z; WaasMedic::RegSetStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,bool,WaasMedic::RegistryHiveType)
0x1800292f9  jmp     loc_18002946D
0x1800292fe  call    ?RegDelValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1W4RegistryHiveType@1@@Z; WaasMedic::RegDelValue(HKEY__ *,ushort const *,ushort const *,WaasMedic::RegistryHiveType)
0x180029303  xor     ebx, ebx
0x180029305  cmp     eax, 80070002h
0x18002930a  cmovnz  ebx, eax
0x18002930d  jmp     loc_18002946F
0x180029312  movsx   r9d, byte ptr [r9+8]
0x180029317  jmp     loc_180029463
0x18002931c  sub     ecx, 11h
0x18002931f  jz      loc_18002945E
0x180029325  sub     ecx, 1
0x180029328  jz      loc_180029457
0x18002932e  sub     ecx, 1
0x180029331  jz      short loc_1800292E2
0x180029333  sub     ecx, 1
0x180029336  jz      loc_180029426
0x18002933c  sub     ecx, 1
0x18002933f  jz      loc_180029426
0x180029345  sub     ecx, 1
0x180029348  jz      short loc_1800292E2
0x18002934a  cmp     ecx, 1
0x18002934d  jz      short loc_1800292E2
0x18002934f  mov     ebx, 80070057h
0x180029354  mov     r9, rdi
0x180029357  mov     dword ptr [rsp+70h+var_50], ebx
0x18002935b  mov     r8, rsi
0x18002935e  lea     rdx, aRegutilErrorWh_6; "RegUtil: Error when attempting to set r"...
0x180029365  mov     ecx, 2; unsigned __int8
0x18002936a  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002936f  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x180029374  mov     r8, rax
0x180029377  mov     ecx, [rax]
0x180029379  cmp     ecx, 5
0x18002937c  jbe     loc_18002940B
0x180029382  mov     rax, [rax+18h]
0x180029386  mov     rdx, 400000000000h
0x180029390  mov     rcx, [r8+10h]
0x180029394  test    rdx, rcx
0x180029397  jz      short loc_18002940B
0x180029399  mov     rcx, rax
0x18002939c  and     rcx, rdx
0x18002939f  cmp     rcx, rax
0x1800293a2  jnz     short loc_18002940B
0x1800293a4  lea     rax, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x1800293ab  mov     dword ptr [rbp+ppvData], ebx
0x1800293ae  mov     [rbp+var_10], rax
0x1800293b2  lea     rdx, byte_180089117
0x1800293b9  lea     rax, [rbp+ppvData]
0x1800293bd  mov     [rbp+arg_18], r14d
0x1800293c1  mov     [rsp+70h+var_28], rax
0x1800293c6  mov     rcx, r8
0x1800293c9  lea     rax, [rbp+arg_18]
0x1800293cd  mov     [rbp+var_20], rdi
0x1800293d1  mov     [rsp+70h+var_30], rax
0x1800293d6  lea     rax, [rbp+var_20]
0x1800293da  mov     [rsp+70h+var_38], rax
0x1800293df  lea     rax, [rbp+var_18]
0x1800293e3  mov     [rsp+70h+var_40], rax
0x1800293e8  lea     rax, [rbp+var_10]
0x1800293ec  mov     [rsp+70h+var_48], rax
0x1800293f1  lea     rax, [rbp+var_8]
0x1800293f5  mov     [rsp+70h+var_50], rax
0x1800293fa  mov     [rbp+var_18], rsi
0x1800293fe  mov     [rbp+var_8], 1000000h
0x180029406  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U2@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@44AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18002940b  mov     eax, ebx
0x18002940d  lea     r11, [rsp+70h+var_s0]
0x180029412  mov     rbx, [r11+38h]
0x180029416  mov     rsi, [r11+40h]
0x18002941a  mov     rsp, r11
0x18002941d  pop     r15
0x18002941f  pop     r14
0x180029421  pop     r12
0x180029423  pop     rdi
0x180029424  pop     rbp
0x180029425  retn
0x180029426  mov     rax, [r9+8]
0x18002942a  mov     r9, rdi
0x18002942d  mov     byte ptr [rsp+70h+var_38], r14b
0x180029432  mov     [rbp+ppvData], rax
0x180029436  lea     rax, [rbp+ppvData]
0x18002943a  mov     [rsp+70h+var_40], 8
0x180029443  mov     [rsp+70h+var_48], rax
0x180029448  mov     dword ptr [rsp+70h+var_50], 0Bh
0x180029450  call    WaasMedic__RegSetValue_Helper
0x180029455  jmp     short loc_18002946D
0x180029457  movzx   r9d, word ptr [r9+8]
0x18002945c  jmp     short loc_180029463
0x18002945e  movzx   r9d, byte ptr [r9+8]
0x180029463  mov     byte ptr [rsp+70h+var_50], r14b
0x180029468  call    ?RegSetDwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1K_NW4RegistryHiveType@1@@Z; WaasMedic::RegSetDwordValue(HKEY__ *,ushort const *,ushort const *,ulong,bool,WaasMedic::RegistryHiveType)
0x18002946d  mov     ebx, eax
0x18002946f  test    ebx, ebx
0x180029471  jns     short loc_18002940B
0x180029473  jmp     loc_180029354
0x180029478  mov     r15, [r9+8]
0x18002947c  mov     rcx, r15; psa
0x18002947f  call    cs:__imp_SafeArrayGetDim
0x180029485  cmp     eax, 1
0x180029488  jnz     loc_18002934F
0x18002948e  mov     [rbp+ppvData], 0
0x180029496  lea     rdx, [rbp+ppvData]; ppvData
0x18002949a  mov     r12d, [r15+18h]
0x18002949e  mov     rcx, r15; psa
0x1800294a1  call    cs:__imp_SafeArrayAccessData
0x1800294a7  mov     ebx, eax
0x1800294a9  test    eax, eax
0x1800294ab  js      loc_180029354
0x1800294b1  mov     rcx, [rbp+ppvData]
0x1800294b5  mov     r9, rdi
0x1800294b8  mov     byte ptr [rsp+70h+var_38], r14b
0x1800294bd  mov     rdx, rsi
0x1800294c0  mov     [rsp+70h+var_40], r12
0x1800294c5  mov     [rsp+70h+var_48], rcx
0x1800294ca  mov     dword ptr [rsp+70h+var_50], 3
0x1800294d2  call    WaasMedic__RegSetValue_Helper
0x1800294d7  mov     ebx, eax
0x1800294d9  test    eax, eax
0x1800294db  js      loc_180029354
0x1800294e1  mov     rcx, r15; psa
0x1800294e4  call    cs:__imp_SafeArrayUnaccessData
0x1800294ea  mov     ebx, eax
0x1800294ec  test    eax, eax
0x1800294ee  js      loc_180029354
0x1800294f4  jmp     loc_18002940B
```
