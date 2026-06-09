# WaasMedic::RegSetValueFromVariant(HKEY__ *,ushort const *,ushort const *,tagVARIANT *,bool)

- ea: `0x1800271a4`
- end: `0x180027443`
- name: `?RegSetValueFromVariant@WaasMedic@@YAJPEAUHKEY__@@PEBG1PEAUtagVARIANT@@_N@Z`
- size: `671`
- prototype: `__int64 __fastcall(WaasMedic *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int16 *, struct tagVARIANT *, bool)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x180023260`
- `0x18003bb70`

## callees

- `0x180002504`
- `0x18000d04c`
- `0x180025d60`
- `0x180027110`
- `0x180027150`
- `0x1800271a4`
- `0x18002744c`
- `0x18002e81c`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800273c6`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800273c6`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800273e8`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800273e8`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002742e`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18002742e`

## string_xrefs

- `0x1800272a6`: `RegUtil: Error when attempting to set registry value from VARIANT. Sub key: [%s] Value name: [%s]. hr=0x%08X`

## pseudocode

```c
__int64 __fastcall WaasMedic::RegSetValueFromVariant(
        WaasMedic *this,
        HKEY a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct tagVARIANT *a5)
{
  unsigned int v9; // ecx
  int v10; // r15d
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  __int64 v16; // r9
  HRESULT v17; // eax
  HRESULT v18; // eax
  HRESULT v19; // ebx
  unsigned int v20; // ecx
  unsigned int v21; // ecx
  unsigned int v22; // ecx
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  __int64 v25; // rcx
  int v26; // r9d
  SAFEARRAY *v27; // r13
  __int64 cElements; // r12
  __int64 v29; // r8
  __int64 v30; // [rsp+20h] [rbp-51h]
  int v31; // [rsp+50h] [rbp-21h] BYREF
  const unsigned __int16 *v32; // [rsp+58h] [rbp-19h] BYREF
  HKEY v33; // [rsp+60h] [rbp-11h] BYREF
  unsigned __int16 *v34; // [rsp+68h] [rbp-9h] BYREF
  __int64 v35[10]; // [rsp+70h] [rbp-1h] BYREF
  void *ppvData; // [rsp+E8h] [rbp+77h] BYREF

  if ( !a4 )
    return 2147500035LL;
  v9 = *a4;
  v10 = (unsigned __int8)a5;
  if ( v9 > 0x2011 )
    goto LABEL_27;
  if ( v9 == 8209 )
  {
    v27 = (SAFEARRAY *)*((_QWORD *)a4 + 1);
    if ( SafeArrayGetDim(v27) == 1 )
    {
      ppvData = 0;
      cElements = v27->rgsabound[0].cElements;
      v19 = SafeArrayAccessData(v27, &ppvData);
      if ( v19 >= 0 )
      {
        v19 = WaasMedic::RegSetValue_Helper(this, a2, v29, a3, 3, ppvData, cElements, (_BYTE)v10);
        if ( v19 >= 0 )
        {
          v19 = SafeArrayUnaccessData(v27);
          if ( v19 >= 0 )
            return (unsigned int)v19;
        }
      }
LABEL_28:
      LODWORD(v30) = v19;
      LogLevelW(
        2u,
        L"RegUtil: Error when attempting to set registry value from VARIANT. Sub key: [%s] Value name: [%s]. hr=0x%08X",
        a2,
        a3,
        v30);
      v25 = *((_QWORD *)WaasMedic::TelemetryProvider::Instance() + 1);
      if ( *(_DWORD *)v25 > 5u
        && (*(_QWORD *)(v25 + 16) & 0x400000000000LL) != 0
        && (*(_QWORD *)(v25 + 24) & 0x400000000000LL) == *(_QWORD *)(v25 + 24) )
      {
        LODWORD(ppvData) = v19;
        v34 = &gc_pszVersionString;
        v31 = v10;
        v32 = a3;
        v33 = a2;
        v35[0] = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v25,
          (unsigned int)&unk_180092C2A,
          0,
          v26,
          (__int64)v35,
          (__int64)&v34,
          (__int64)&v33,
          (__int64)&v32,
          (__int64)&v31,
          (__int64)&ppvData);
      }
      return (unsigned int)v19;
    }
    goto LABEL_27;
  }
  if ( v9 > 0x10 )
  {
    v20 = v9 - 17;
    if ( !v20 )
    {
      v16 = *((unsigned __int8 *)a4 + 8);
      goto LABEL_36;
    }
    v21 = v20 - 1;
    if ( !v21 )
    {
      v16 = a4[4];
      goto LABEL_36;
    }
    v22 = v21 - 1;
    if ( !v22 )
      goto LABEL_15;
    v23 = v22 - 1;
    if ( !v23 || (v24 = v23 - 1) == 0 )
    {
      ppvData = (void *)*((_QWORD *)a4 + 1);
      v17 = WaasMedic::RegSetValue_Helper(this, a2, a3, a3, 11, &ppvData, 8, (_BYTE)a5);
      goto LABEL_37;
    }
    if ( v24 - 1 < 2 )
      goto LABEL_15;
LABEL_27:
    v19 = -2147024809;
    goto LABEL_28;
  }
  if ( v9 == 16 )
  {
    v16 = (unsigned int)*((char *)a4 + 8);
    goto LABEL_36;
  }
  if ( *a4 )
  {
    v11 = v9 - 1;
    if ( v11 )
    {
      v12 = v11 - 1;
      if ( !v12 )
      {
LABEL_14:
        v16 = (unsigned int)*((__int16 *)a4 + 4);
LABEL_36:
        v17 = WaasMedic::RegSetDwordValue(this, a2, a3, v16, (_BYTE)a5);
        goto LABEL_37;
      }
      v13 = v12 - 1;
      if ( !v13 )
        goto LABEL_15;
      v14 = v13 - 5;
      if ( v14 )
      {
        v15 = v14 - 2;
        if ( v15 )
        {
          if ( v15 == 1 )
            goto LABEL_14;
          goto LABEL_27;
        }
LABEL_15:
        v16 = *((unsigned int *)a4 + 2);
        goto LABEL_36;
      }
      v17 = WaasMedic::RegSetStringValue(this, a2, a3);
LABEL_37:
      v19 = v17;
      goto LABEL_38;
    }
  }
  v18 = WaasMedic::RegDelValue(this, a2, a3);
  v19 = 0;
  if ( v18 != -2147024894 )
    v19 = v18;
LABEL_38:
  if ( v19 < 0 )
    goto LABEL_28;
  return (unsigned int)v19;
}

```

## disassembly

```asm
0x1800271a4  push    rbp
0x1800271a6  push    rbx
0x1800271a7  push    rsi
0x1800271a8  push    rdi
0x1800271a9  push    r12
0x1800271ab  push    r13
0x1800271ad  push    r14
0x1800271af  push    r15
0x1800271b1  lea     rbp, [rsp-17h]
0x1800271b6  sub     rsp, 88h
0x1800271bd  mov     rdi, r8
0x1800271c0  mov     rsi, rdx
0x1800271c3  mov     r14, rcx
0x1800271c6  test    r9, r9
0x1800271c9  jnz     short loc_1800271D5
0x1800271cb  mov     eax, 80004003h
0x1800271d0  jmp     loc_180027353
0x1800271d5  movzx   ecx, word ptr [r9]
0x1800271d9  mov     eax, 2011h
0x1800271de  movzx   r15d, byte ptr [rbp+4Fh+arg_20]
0x1800271e3  cmp     ecx, eax
0x1800271e5  ja      loc_180027297
0x1800271eb  jz      loc_1800273BF
0x1800271f1  cmp     ecx, 10h
0x1800271f4  ja      short loc_180027264
0x1800271f6  jz      short loc_18002725A
0x1800271f8  test    ecx, ecx
0x1800271fa  jz      short loc_180027243
0x1800271fc  sub     ecx, 1
0x1800271ff  jz      short loc_180027243
0x180027201  sub     ecx, 1
0x180027204  jz      short loc_18002721A
0x180027206  sub     ecx, 1
0x180027209  jz      short loc_180027224
0x18002720b  sub     ecx, 5
0x18002720e  jz      short loc_18002722D
0x180027210  sub     ecx, 2
0x180027213  jz      short loc_180027224
0x180027215  cmp     ecx, 1
0x180027218  jnz     short loc_180027297
0x18002721a  movsx   r9d, word ptr [r9+8]
0x18002721f  jmp     loc_1800273A7
0x180027224  mov     r9d, [r9+8]
0x180027228  jmp     loc_1800273A7
0x18002722d  mov     r9, [r9+8]
0x180027231  mov     rcx, r14
0x180027234  mov     byte ptr [rsp+0C0h+var_A0], r15b
0x180027239  call    ?RegSetStringValue@WaasMedic@@YAJPEAUHKEY__@@PEBG11_NW4RegistryHiveType@1@@Z; WaasMedic::RegSetStringValue(HKEY__ *,ushort const *,ushort const *,ushort const *,bool,WaasMedic::RegistryHiveType)
0x18002723e  jmp     loc_1800273B4
0x180027243  mov     rcx, r14
0x180027246  call    ?RegDelValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1W4RegistryHiveType@1@@Z; WaasMedic::RegDelValue(HKEY__ *,ushort const *,ushort const *,WaasMedic::RegistryHiveType)
0x18002724b  xor     ebx, ebx
0x18002724d  cmp     eax, 80070002h
0x180027252  cmovnz  ebx, eax
0x180027255  jmp     loc_1800273B6
0x18002725a  movsx   r9d, byte ptr [r9+8]
0x18002725f  jmp     loc_1800273A7
0x180027264  sub     ecx, 11h
0x180027267  jz      loc_1800273A2
0x18002726d  sub     ecx, 1
0x180027270  jz      loc_18002739B
0x180027276  sub     ecx, 1
0x180027279  jz      short loc_180027224
0x18002727b  sub     ecx, 1
0x18002727e  jz      loc_180027367
0x180027284  sub     ecx, 1
0x180027287  jz      loc_180027367
0x18002728d  sub     ecx, 1
0x180027290  jz      short loc_180027224
0x180027292  cmp     ecx, 1
0x180027295  jz      short loc_180027224
0x180027297  mov     ebx, 80070057h
0x18002729c  mov     r9, rdi
0x18002729f  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x1800272a3  mov     r8, rsi
0x1800272a6  lea     rdx, aRegutilErrorWh_6; "RegUtil: Error when attempting to set r"...
0x1800272ad  mov     ecx, 2; unsigned __int8
0x1800272b2  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800272b7  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x1800272bc  mov     rcx, [rax+8]
0x1800272c0  mov     eax, [rcx]
0x1800272c2  cmp     eax, 5
0x1800272c5  jbe     loc_180027351
0x1800272cb  mov     rdx, [rcx+18h]
0x1800272cf  mov     r8, 400000000000h
0x1800272d9  mov     rax, [rcx+10h]
0x1800272dd  test    r8, rax
0x1800272e0  jz      short loc_180027351
0x1800272e2  mov     rax, rdx
0x1800272e5  and     rax, r8
0x1800272e8  cmp     rax, rdx
0x1800272eb  jnz     short loc_180027351
0x1800272ed  lea     rax, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x1800272f4  mov     dword ptr [rbp+4Fh+ppvData], ebx
0x1800272f7  mov     [rbp+4Fh+var_58], rax
0x1800272fb  lea     rdx, unk_180092C2A
0x180027302  lea     rax, [rbp+4Fh+ppvData]
0x180027306  mov     [rbp+4Fh+var_70], r15d
0x18002730a  mov     [rsp+0C0h+var_78], rax
0x18002730f  lea     rax, [rbp+4Fh+var_70]
0x180027313  mov     [rsp+0C0h+var_80], rax
0x180027318  lea     rax, [rbp+4Fh+var_68]
0x18002731c  mov     [rsp+0C0h+var_88], rax
0x180027321  lea     rax, [rbp+4Fh+var_60]
0x180027325  mov     [rsp+0C0h+var_90], rax
0x18002732a  lea     rax, [rbp+4Fh+var_58]
0x18002732e  mov     [rsp+0C0h+var_98], rax
0x180027333  lea     rax, [rbp+4Fh+var_50]
0x180027337  mov     [rsp+0C0h+var_A0], rax
0x18002733c  mov     [rbp+4Fh+var_68], rdi
0x180027340  mov     [rbp+4Fh+var_60], rsi
0x180027344  mov     [rbp+4Fh+var_50], 1000000h
0x18002734c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U2@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@44AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180027351  mov     eax, ebx
0x180027353  add     rsp, 88h
0x18002735a  pop     r15
0x18002735c  pop     r14
0x18002735e  pop     r13
0x180027360  pop     r12
0x180027362  pop     rdi
0x180027363  pop     rsi
0x180027364  pop     rbx
0x180027365  pop     rbp
0x180027366  retn
0x180027367  mov     rax, [r9+8]
0x18002736b  mov     rcx, r14
0x18002736e  mov     byte ptr [rsp+0C0h+var_88], r15b
0x180027373  mov     r9, rdi
0x180027376  mov     [rbp+4Fh+ppvData], rax
0x18002737a  lea     rax, [rbp+4Fh+ppvData]
0x18002737e  mov     [rsp+0C0h+var_90], 8
0x180027387  mov     [rsp+0C0h+var_98], rax
0x18002738c  mov     dword ptr [rsp+0C0h+var_A0], 0Bh
0x180027394  call    WaasMedic__RegSetValue_Helper
0x180027399  jmp     short loc_1800273B4
0x18002739b  movzx   r9d, word ptr [r9+8]
0x1800273a0  jmp     short loc_1800273A7
0x1800273a2  movzx   r9d, byte ptr [r9+8]
0x1800273a7  mov     rcx, r14
0x1800273aa  mov     byte ptr [rsp+0C0h+var_A0], r15b
0x1800273af  call    ?RegSetDwordValue@WaasMedic@@YAJPEAUHKEY__@@PEBG1K_NW4RegistryHiveType@1@@Z; WaasMedic::RegSetDwordValue(HKEY__ *,ushort const *,ushort const *,ulong,bool,WaasMedic::RegistryHiveType)
0x1800273b4  mov     ebx, eax
0x1800273b6  test    ebx, ebx
0x1800273b8  jns     short loc_180027351
0x1800273ba  jmp     loc_18002729C
0x1800273bf  mov     r13, [r9+8]
0x1800273c3  mov     rcx, r13; psa
0x1800273c6  call    cs:__imp_SafeArrayGetDim
0x1800273cc  cmp     eax, 1
0x1800273cf  jnz     loc_180027297
0x1800273d5  mov     [rbp+4Fh+ppvData], 0
0x1800273dd  lea     rdx, [rbp+4Fh+ppvData]; ppvData
0x1800273e1  mov     r12d, [r13+18h]
0x1800273e5  mov     rcx, r13; psa
0x1800273e8  call    cs:__imp_SafeArrayAccessData
0x1800273ee  mov     ebx, eax
0x1800273f0  test    eax, eax
0x1800273f2  js      loc_18002729C
0x1800273f8  mov     rdx, [rbp+4Fh+ppvData]
0x1800273fc  mov     r9, rdi
0x1800273ff  mov     byte ptr [rsp+0C0h+var_88], r15b
0x180027404  mov     rcx, r14
0x180027407  mov     [rsp+0C0h+var_90], r12
0x18002740c  mov     [rsp+0C0h+var_98], rdx
0x180027411  mov     rdx, rsi
0x180027414  mov     dword ptr [rsp+0C0h+var_A0], 3
0x18002741c  call    WaasMedic__RegSetValue_Helper
0x180027421  mov     ebx, eax
0x180027423  test    eax, eax
0x180027425  js      loc_18002729C
0x18002742b  mov     rcx, r13; psa
0x18002742e  call    cs:__imp_SafeArrayUnaccessData
0x180027434  mov     ebx, eax
0x180027436  test    eax, eax
0x180027438  js      loc_18002729C
0x18002743e  jmp     loc_180027351
```
