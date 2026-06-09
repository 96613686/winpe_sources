# RegKey::GetStringOrMultiString(ushort const *)

- ea: `0x18000e6f8`
- end: `0x18000ec7e`
- name: `?GetStringOrMultiString@RegKey@@QEBA?AV?$optional@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@PEBG@Z`
- size: `1414`
- prototype: `__int64 __fastcall(HKEY *, __int64, const WCHAR *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task`

## callers

- `0x18000f6e0`

## callees

- `0x1800012e0`
- `0x1800012f0`
- `0x18000131c`
- `0x180001f74`
- `0x180002020`
- `0x1800021e4`
- `0x180002370`
- `0x180002fe0`
- `0x18000365c`
- `0x180004cfc`
- `0x18000a674`
- `0x18000db50`
- `0x18000dc74`
- `0x18000de14`
- `0x18000df1c`
- `0x18000e6f8`
- `0x18000ec84`
- `0x18000f0bc`
- `0x18000f1c0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000e9dc`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18000e9dc`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e782`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e808`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e782`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000e808`

## string_xrefs

- `0x18000ec6c`: `onecore\base\time\autotime\timeservice\regkey.cpp`

## pseudocode

```c
__int64 __fastcall RegKey::GetStringOrMultiString(HKEY *a1, __int64 a2, const WCHAR *a3)
{
  __int64 v3; // rsi
  WCHAR *pvData; // r14
  __int64 v5; // r15
  LSTATUS ValueW; // eax
  unsigned int v7; // r8d
  unsigned int v8; // ebx
  DWORD v9; // ebx
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  _QWORD *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rax
  const wchar_t *v23; // r13
  const wchar_t *v24; // rbx
  size_t v25; // r12
  __int64 v26; // r8
  __int64 v27; // r9
  __int16 *v28; // rdx
  _QWORD *v29; // rax
  __int64 v30; // r8
  __int64 v31; // r9
  _QWORD *v32; // rax
  __int64 v33; // r8
  __int64 v34; // r9
  const char *v35; // r9
  unsigned int pdwType; // [rsp+20h] [rbp-C8h]
  __int128 v37; // [rsp+40h] [rbp-A8h] BYREF
  __int64 v38; // [rsp+50h] [rbp-98h]
  __int64 v39; // [rsp+58h] [rbp-90h] BYREF
  int v40; // [rsp+60h] [rbp-88h]
  HKEY hkey[2]; // [rsp+68h] [rbp-80h] BYREF
  WCHAR *v42; // [rsp+78h] [rbp-70h] BYREF
  __int64 v43; // [rsp+88h] [rbp-60h] BYREF
  __int16 v44; // [rsp+90h] [rbp-58h]
  char v45; // [rsp+A0h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]
  DWORD pcbData; // [rsp+F0h] [rbp+8h] BYREF
  __int64 v48; // [rsp+F8h] [rbp+10h]
  const WCHAR *v49; // [rsp+100h] [rbp+18h] BYREF
  DWORD v50; // [rsp+108h] [rbp+20h] BYREF

  v49 = a3;
  v48 = a2;
  v3 = a2;
  pcbData = 0;
  pvData = 0;
  v42 = 0;
  v50 = 0;
  hkey[0] = a1[1];
  hkey[1] = *a1;
  v5 = hkey[0] == 0;
  while ( 1 )
  {
    pcbData = 0;
    ValueW = RegGetValueW(hkey[v5], 0, L"NTP Servers", 0x22u, &v50, 0, &pcbData);
    v8 = ValueW;
    if ( ValueW != 2 )
      break;
    if ( (unsigned __int64)++v5 >= 2 )
      goto LABEL_7;
  }
  if ( ValueW
    || (v9 = pcbData,
        pvData = (WCHAR *)operator new[](pcbData),
        memset_0(pvData, 0, v9),
        v49 = 0,
        v42 = pvData,
        std::unique_ptr<char [0]>::~unique_ptr<char [0]>((void **)&v49),
        v8 = RegGetValueW(hkey[v5], 0, L"NTP Servers", 0x22u, &v50, pvData, &pcbData),
        v8 != 2) )
  {
    if ( v8 )
    {
      if ( (unsigned int)dword_18001C010 > 2 && tlgKeywordOn((__int64)&dword_18001C010, 2) )
      {
        LODWORD(v39) = v8;
        LOBYTE(v49) = v5 == 0;
        v29 = _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(hkey, (__int64)L"NTP Servers");
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
          (__int64)&v49,
          (__int64)&byte_180017467,
          v30,
          v31,
          v29);
      }
      wil::details::in1diag3::Throw_Win32(retaddr, (void *)0x14D, v7, (const char *)v8, pdwType);
    }
    v14 = pcbData >> 1;
    pcbData >>= 1;
    v37 = 0;
    v38 = 0;
    v49 = pvData;
    if ( v50 != 7 )
    {
      if ( (_DWORD)v14 )
      {
        v15 = (unsigned int)(v14 - 1);
        if ( !pvData[v15] )
          pcbData = v15;
      }
      std::vector<std::wstring>::_Emplace_reallocate<unsigned short const * &,unsigned long &>(&v37, 0, &v49, &pcbData);
      if ( (unsigned int)dword_18001C010 > 4 && tlgKeywordOn((__int64)&dword_18001C010, 2) )
      {
        v19 = (_QWORD *)(*((_QWORD *)&v37 + 1) - 32LL);
        if ( *(_QWORD *)(*((_QWORD *)&v37 + 1) - 32LL + 24) > 7u )
          v19 = (_QWORD *)*v19;
        v39 = (__int64)v19;
        LOBYTE(v49) = v5 == 0;
        hkey[0] = (HKEY)L"NTP Servers";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
          v16,
          (__int64)byte_180017699,
          v17,
          v18,
          hkey,
          (__int64)&v49,
          &v39);
      }
      goto LABEL_22;
    }
    if ( (unsigned int)v14 < 2 || pvData[(unsigned int)(v14 - 2)] || pvData[(unsigned int)(v14 - 1)] )
      goto LABEL_64;
    if ( (_DWORD)v14 != 2 )
    {
      v23 = &pvData[v14];
      if ( pvData < v23 )
      {
        v24 = pvData;
        while ( v24 )
        {
          v25 = wcsnlen(v24, v23 - pvData);
          v39 = v25;
          if ( !v25 )
            break;
          if ( *((_QWORD *)&v37 + 1) == v38 )
          {
            std::vector<std::wstring>::_Emplace_reallocate<unsigned short const * &,unsigned __int64 &>(
              &v37,
              *((_QWORD *)&v37 + 1),
              &v49,
              &v39);
            pvData = (WCHAR *)v49;
            v25 = v39;
          }
          else
          {
            std::wstring::wstring(*((_QWORD *)&v37 + 1), v24, v25);
            *((_QWORD *)&v37 + 1) += 32LL;
          }
          pvData += v25 + 1;
          v49 = pvData;
          v24 = pvData;
          if ( pvData >= v23 )
            goto LABEL_35;
        }
        if ( v24 + 1 != v23 )
        {
LABEL_64:
          if ( (unsigned int)dword_18001C010 > 2 && tlgKeywordOn((__int64)&dword_18001C010, 2) )
          {
            LOBYTE(v49) = v5 == 0;
            v32 = _tlgTypeMapBase<unsigned short *,void>::_tlgWrapAuto(hkey, (__int64)L"NTP Servers");
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>>(
              (__int64)&v49,
              (__int64)byte_18001733B,
              v33,
              v34,
              v32);
          }
          v35 = (const char *)(unsigned int)wil::verify_hresult<long>(2147746131LL);
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x192,
            (int)"onecore\\base\\time\\autotime\\timeservice\\regkey.cpp",
            v35,
            pdwType);
        }
      }
    }
LABEL_35:
    if ( (unsigned int)dword_18001C010 <= 4 || !tlgKeywordOn((__int64)&dword_18001C010, 2) )
      goto LABEL_22;
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      RegKey::GetTlgPackedData(&v43, &v37);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
      {
        v3 = v48;
        __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18000EB75);
        goto LABEL_22;
      }
    }
    if ( v45 )
    {
      if ( (unsigned int)dword_18001C010 <= 4 || !tlgKeywordOn((__int64)&dword_18001C010, 2) )
        goto LABEL_48;
      v28 = (__int16 *)byte_180017653;
    }
    else
    {
      if ( (unsigned int)dword_18001C010 <= 4 || !tlgKeywordOn((__int64)&dword_18001C010, 2) )
        goto LABEL_48;
      v28 = &word_1800172F6;
    }
    v40 = (unsigned __int16)(v44 - v43);
    hkey[0] = (HKEY)L"NTP Servers";
    v39 = v43;
    LOBYTE(v49) = v5 == 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperPtrSize>(
      v43,
      (__int64)v28,
      v26,
      v27,
      hkey);
LABEL_48:
    std::vector<unsigned char>::_Tidy(&v43);
LABEL_22:
    v20 = v38;
    v38 = 0;
    v21 = *((_QWORD *)&v37 + 1);
    v22 = v37;
    v37 = 0u;
    *(_QWORD *)v3 = v22;
    *(_QWORD *)(v3 + 8) = v21;
    *(_QWORD *)(v3 + 16) = v20;
    *(_BYTE *)(v3 + 24) = 1;
    goto LABEL_11;
  }
LABEL_7:
  if ( (unsigned int)dword_18001C010 > 4 && tlgKeywordOn((__int64)&dword_18001C010, 2) )
  {
    v49 = L"NTP Servers";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      v10,
      (__int64)word_18001742A,
      v11,
      v12,
      &v49);
  }
  *(_BYTE *)(v3 + 24) = 0;
LABEL_11:
  std::unique_ptr<char [0]>::~unique_ptr<char [0]>((void **)&v42);
  return v3;
}

```

## disassembly

```asm
0x18000e6f8  mov     rax, rsp
0x18000e6fb  mov     [rax+18h], r8
0x18000e6ff  mov     [rax+10h], rdx
0x18000e703  push    rbx
0x18000e704  push    rsi
0x18000e705  push    rdi
0x18000e706  push    r12
0x18000e708  push    r13
0x18000e70a  push    r14
0x18000e70c  push    r15
0x18000e70e  sub     rsp, 0B0h
0x18000e715  mov     rsi, rdx
0x18000e718  xor     edi, edi
0x18000e71a  mov     [rax+8], edi
0x18000e71d  mov     r14d, edi
0x18000e720  mov     [rax-70h], rdi
0x18000e724  mov     [rax+20h], edi
0x18000e727  mov     r8, [rcx+8]
0x18000e72b  mov     [rax-80h], r8
0x18000e72f  mov     rax, [rcx]
0x18000e732  mov     [rsp+0E8h+var_78], rax
0x18000e737  mov     r15d, edi
0x18000e73a  test    r8, r8
0x18000e73d  setz    r15b
0x18000e741  lea     r12, Value; "NTP Servers"
0x18000e748  lea     r13d, [rdi+2]
0x18000e74c  mov     [rsp+0E8h+arg_0], edi
0x18000e753  lea     rax, [rsp+0E8h+arg_0]
0x18000e75b  mov     [rsp+0E8h+pcbData], rax; pcbData
0x18000e760  mov     [rsp+0E8h+pvData], rdi; pvData
0x18000e765  lea     rax, [rsp+0E8h+arg_18]
0x18000e76d  mov     [rsp+0E8h+pdwType], rax; pdwType
0x18000e772  mov     r9d, 22h ; '"'; dwFlags
0x18000e778  mov     r8, r12; lpValue
0x18000e77b  xor     edx, edx; lpSubKey
0x18000e77d  mov     rcx, [rsp+r15*8+0E8h+hkey]; hkey
0x18000e782  call    cs:__imp_RegGetValueW
0x18000e788  mov     ebx, eax
0x18000e78a  cmp     eax, r13d
0x18000e78d  jnz     short loc_18000E799
0x18000e78f  inc     r15
0x18000e792  cmp     r15, r13
0x18000e795  jb      short loc_18000E74C
0x18000e797  jmp     short loc_18000E815
0x18000e799  test    eax, eax
0x18000e79b  jnz     loc_18000E878
0x18000e7a1  mov     ebx, [rsp+0E8h+arg_0]
0x18000e7a8  mov     ecx, ebx; unsigned __int64
0x18000e7aa  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000e7af  mov     r14, rax
0x18000e7b2  mov     r8d, ebx; Size
0x18000e7b5  xor     edx, edx; Val
0x18000e7b7  mov     rcx, rax; void *
0x18000e7ba  call    memset_0
0x18000e7bf  mov     [rsp+0E8h+arg_10], rdi
0x18000e7c7  mov     [rsp+0E8h+var_70], r14
0x18000e7cc  lea     rcx, [rsp+0E8h+arg_10]
0x18000e7d4  call    ??1?$unique_ptr@$$BY0A@DU?$default_delete@$$BY0A@D@std@@@std@@QEAA@XZ; std::unique_ptr<char [0]>::~unique_ptr<char [0]>(void)
0x18000e7d9  lea     rax, [rsp+0E8h+arg_0]
0x18000e7e1  mov     [rsp+0E8h+pcbData], rax; pcbData
0x18000e7e6  mov     [rsp+0E8h+pvData], r14; pvData
0x18000e7eb  lea     rax, [rsp+0E8h+arg_18]
0x18000e7f3  mov     [rsp+0E8h+pdwType], rax; pdwType
0x18000e7f8  mov     r9d, 22h ; '"'; dwFlags
0x18000e7fe  mov     r8, r12; lpValue
0x18000e801  xor     edx, edx; lpSubKey
0x18000e803  mov     rcx, [rsp+r15*8+0E8h+hkey]; hkey
0x18000e808  call    cs:__imp_RegGetValueW
0x18000e80e  mov     ebx, eax
0x18000e810  cmp     eax, r13d
0x18000e813  jnz     short loc_18000E878
0x18000e815  mov     eax, cs:dword_18001C010
0x18000e81b  cmp     eax, 4
0x18000e81e  jbe     short loc_18000E854
0x18000e820  mov     rdx, r13
0x18000e823  lea     rcx, dword_18001C010
0x18000e82a  call    _tlgKeywordOn
0x18000e82f  test    al, al
0x18000e831  jz      short loc_18000E854
0x18000e833  mov     [rsp+0E8h+arg_10], r12
0x18000e83b  lea     rax, [rsp+0E8h+arg_10]
0x18000e843  mov     [rsp+0E8h+pdwType], rax
0x18000e848  lea     rdx, word_18001742A
0x18000e84f  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18000e854  mov     [rsi+18h], dil
0x18000e858  lea     rcx, [rsp+0E8h+var_70]
0x18000e85d  call    ??1?$unique_ptr@$$BY0A@DU?$default_delete@$$BY0A@D@std@@@std@@QEAA@XZ; std::unique_ptr<char [0]>::~unique_ptr<char [0]>(void)
0x18000e862  mov     rax, rsi
0x18000e865  add     rsp, 0B0h
0x18000e86c  pop     r15
0x18000e86e  pop     r14
0x18000e870  pop     r13
0x18000e872  pop     r12
0x18000e874  pop     rdi
0x18000e875  pop     rsi
0x18000e876  pop     rbx
0x18000e877  retn
0x18000e878  test    ebx, ebx
0x18000e87a  jnz     loc_18000EB84
0x18000e880  mov     edx, [rsp+0E8h+arg_0]
0x18000e887  shr     edx, 1
0x18000e889  mov     [rsp+0E8h+arg_0], edx
0x18000e890  xorps   xmm0, xmm0
0x18000e893  movdqu  [rsp+0E8h+var_A8], xmm0
0x18000e899  mov     [rsp+0E8h+var_98], rdi
0x18000e89e  mov     [rsp+0E8h+arg_10], r14
0x18000e8a6  cmp     [rsp+0E8h+arg_18], 7
0x18000e8ae  jz      loc_18000E989
0x18000e8b4  test    edx, edx
0x18000e8b6  jz      short loc_18000E8C8
0x18000e8b8  dec     edx
0x18000e8ba  cmp     [r14+rdx*2], di
0x18000e8bf  jnz     short loc_18000E8C8
0x18000e8c1  mov     [rsp+0E8h+arg_0], edx
0x18000e8c8  lea     r9, [rsp+0E8h+arg_0]
0x18000e8d0  lea     r8, [rsp+0E8h+arg_10]
0x18000e8d8  xor     edx, edx
0x18000e8da  lea     rcx, [rsp+0E8h+var_A8]
0x18000e8df  call    ??$_Emplace_reallocate@AEAPEBGAEAK@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEAPEBGAEAK@Z; std::vector<std::wstring>::_Emplace_reallocate<ushort const * &,ulong &>(std::wstring * const,ushort const * &,ulong &)
0x18000e8e4  mov     eax, cs:dword_18001C010
0x18000e8ea  cmp     eax, 4
0x18000e8ed  jbe     short loc_18000E957
0x18000e8ef  mov     rdx, r13
0x18000e8f2  lea     rcx, dword_18001C010
0x18000e8f9  call    _tlgKeywordOn
0x18000e8fe  test    al, al
0x18000e900  jz      short loc_18000E957
0x18000e902  mov     rax, qword ptr [rsp+0E8h+var_A8+8]
0x18000e907  add     rax, 0FFFFFFFFFFFFFFE0h
0x18000e90b  cmp     qword ptr [rax+18h], 7
0x18000e910  jbe     short loc_18000E915
0x18000e912  mov     rax, [rax]
0x18000e915  mov     [rsp+0E8h+var_90], rax
0x18000e91a  test    r15, r15
0x18000e91d  setz    byte ptr [rsp+0E8h+arg_10]
0x18000e925  mov     [rsp+0E8h+hkey], r12
0x18000e92a  lea     rax, [rsp+0E8h+var_90]
0x18000e92f  mov     [rsp+0E8h+pcbData], rax
0x18000e934  lea     rax, [rsp+0E8h+arg_10]
0x18000e93c  mov     [rsp+0E8h+pvData], rax
0x18000e941  lea     rax, [rsp+0E8h+hkey]
0x18000e946  mov     [rsp+0E8h+pdwType], rax
0x18000e94b  lea     rdx, byte_180017699
0x18000e952  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &)
0x18000e957  mov     rdx, [rsp+0E8h+var_98]
0x18000e95c  mov     [rsp+0E8h+var_98], rdi
0x18000e961  mov     rcx, qword ptr [rsp+0E8h+var_A8+8]
0x18000e966  mov     qword ptr [rsp+0E8h+var_A8+8], rdi
0x18000e96b  mov     rax, qword ptr [rsp+0E8h+var_A8]
0x18000e970  mov     qword ptr [rsp+0E8h+var_A8], rdi
0x18000e975  mov     [rsi], rax
0x18000e978  mov     [rsi+8], rcx
0x18000e97c  mov     [rsi+10h], rdx
0x18000e980  mov     byte ptr [rsi+18h], 1
0x18000e984  jmp     loc_18000E858
0x18000e989  cmp     edx, r13d
0x18000e98c  jb      loc_18000EC03
0x18000e992  lea     eax, [rdx-2]
0x18000e995  cmp     [r14+rax*2], di
0x18000e99a  jnz     loc_18000EC03
0x18000e9a0  lea     eax, [rdx-1]
0x18000e9a3  cmp     [r14+rax*2], di
0x18000e9a8  jnz     loc_18000EC03
0x18000e9ae  cmp     edx, r13d
0x18000e9b1  jz      loc_18000EA5E
0x18000e9b7  lea     r13, [r14+rdx*2]
0x18000e9bb  cmp     r14, r13
0x18000e9be  jnb     loc_18000EA58
0x18000e9c4  mov     rbx, r14
0x18000e9c7  test    rbx, rbx
0x18000e9ca  jz      loc_18000EACF
0x18000e9d0  mov     rdx, r13
0x18000e9d3  sub     rdx, r14
0x18000e9d6  sar     rdx, 1; MaxCount
0x18000e9d9  mov     rcx, rbx; Source
0x18000e9dc  call    cs:__imp_wcsnlen
0x18000e9e2  mov     r12, rax
0x18000e9e5  mov     [rsp+0E8h+var_90], rax
0x18000e9ea  test    rax, rax
0x18000e9ed  jz      loc_18000EACF
0x18000e9f3  mov     rax, qword ptr [rsp+0E8h+var_A8+8]
0x18000e9f8  cmp     rax, [rsp+0E8h+var_98]
0x18000e9fd  jz      short loc_18000EA15
0x18000e9ff  mov     r8, r12
0x18000ea02  mov     rdx, rbx
0x18000ea05  mov     rcx, rax
0x18000ea08  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x18000ea0d  add     qword ptr [rsp+0E8h+var_A8+8], 20h ; ' '
0x18000ea13  jmp     short loc_18000EA3C
0x18000ea15  lea     r9, [rsp+0E8h+var_90]
0x18000ea1a  lea     r8, [rsp+0E8h+arg_10]
0x18000ea22  mov     rdx, rax
0x18000ea25  lea     rcx, [rsp+0E8h+var_A8]
0x18000ea2a  call    ??$_Emplace_reallocate@AEAPEBGAEA_K@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEAPEBGAEA_K@Z; std::vector<std::wstring>::_Emplace_reallocate<ushort const * &,unsigned __int64 &>(std::wstring * const,ushort const * &,unsigned __int64 &)
0x18000ea2f  mov     r14, [rsp+0E8h+arg_10]
0x18000ea37  mov     r12, [rsp+0E8h+var_90]
0x18000ea3c  lea     r14, [r14+r12*2]
0x18000ea40  add     r14, 2
0x18000ea44  mov     [rsp+0E8h+arg_10], r14
0x18000ea4c  mov     rbx, r14
0x18000ea4f  cmp     r14, r13
0x18000ea52  jb      loc_18000E9C7
0x18000ea58  mov     r13d, 2
0x18000ea5e  mov     eax, cs:dword_18001C010
0x18000ea64  cmp     eax, 4
0x18000ea67  jbe     loc_18000E957
0x18000ea6d  mov     rdx, r13
0x18000ea70  lea     rcx, dword_18001C010
0x18000ea77  call    _tlgKeywordOn
0x18000ea7c  test    al, al
0x18000ea7e  jz      loc_18000E957
0x18000ea84  lea     rdx, [rsp+0E8h+var_A8]
0x18000ea89  lea     rcx, [rsp+0E8h+var_60]
0x18000ea91  call    ?GetTlgPackedData@RegKey@@CA?AU?$pair@V?$vector@EV?$allocator@E@std@@@std@@_N@std@@AEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@3@@Z; RegKey::GetTlgPackedData(std::vector<std::wstring> const &)
0x18000ea96  mov     eax, cs:dword_18001C010
0x18000ea9c  cmp     [rsp+0E8h+var_48], dil
0x18000eaa4  jnz     short loc_18000EAE7
0x18000eaa6  cmp     eax, 4
0x18000eaa9  jbe     loc_18000EB62
0x18000eaaf  mov     rdx, r13
0x18000eab2  lea     rcx, dword_18001C010
0x18000eab9  call    _tlgKeywordOn
0x18000eabe  test    al, al
0x18000eac0  jz      loc_18000EB62
0x18000eac6  lea     rdx, word_1800172F6
0x18000eacd  jmp     short loc_18000EB06
0x18000eacf  lea     rax, [rbx+2]
0x18000ead3  cmp     rax, r13
0x18000ead6  mov     r13d, 2
0x18000eadc  jnz     loc_18000EBFC
0x18000eae2  jmp     loc_18000EA5E
0x18000eae7  cmp     eax, 4
0x18000eaea  jbe     short loc_18000EB62
0x18000eaec  mov     rdx, r13
0x18000eaef  lea     rcx, dword_18001C010
0x18000eaf6  call    _tlgKeywordOn
0x18000eafb  test    al, al
0x18000eafd  jz      short loc_18000EB62
0x18000eaff  lea     rdx, byte_180017653
0x18000eb06  mov     rcx, [rsp+0E8h+var_60]
0x18000eb0e  movzx   eax, [rsp+0E8h+var_58]
0x18000eb16  sub     ax, cx
0x18000eb19  movzx   eax, ax
0x18000eb1c  mov     [rsp+0E8h+var_88], eax
0x18000eb20  lea     rax, Value; "NTP Servers"
0x18000eb27  mov     [rsp+0E8h+hkey], rax
0x18000eb2c  lea     rax, [rsp+0E8h+var_90]
0x18000eb31  mov     [rsp+0E8h+pcbData], rax
0x18000eb36  lea     rax, [rsp+0E8h+arg_10]
0x18000eb3e  mov     [rsp+0E8h+pvData], rax
0x18000eb43  lea     rax, [rsp+0E8h+hkey]
0x18000eb48  test    r15, r15
0x18000eb4b  mov     [rsp+0E8h+pdwType], rax
0x18000eb50  mov     [rsp+0E8h+var_90], rcx
0x18000eb55  setz    byte ptr [rsp+0E8h+arg_10]
0x18000eb5d  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@U_tlgWrapperPtrSize@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@AEBU_tlgWrapperPtrSize@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperPtrSize>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperPtrSize const &)
0x18000eb62  lea     rcx, [rsp+0E8h+var_60]
0x18000eb6a  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18000eb6f  nop
0x18000eb70  jmp     loc_18000E957
0x18000eb75  xor     edi, edi
0x18000eb77  mov     rsi, [rsp+0E8h+arg_8]
0x18000eb7f  jmp     loc_18000E957
0x18000eb84  mov     eax, cs:dword_18001C010
0x18000eb8a  cmp     eax, r13d
0x18000eb8d  jbe     short loc_18000EBE6
0x18000eb8f  mov     rdx, r13
0x18000eb92  lea     rcx, dword_18001C010
0x18000eb99  call    _tlgKeywordOn
0x18000eb9e  test    al, al
0x18000eba0  jz      short loc_18000EBE6
0x18000eba2  mov     dword ptr [rsp+0E8h+var_90], ebx
0x18000eba6  test    r15, r15
0x18000eba9  setz    byte ptr [rsp+0E8h+arg_10]
0x18000ebb1  mov     rdx, r12
0x18000ebb4  lea     rcx, [rsp+0E8h+hkey]
0x18000ebb9  call    ?_tlgWrapAuto@?$_tlgTypeMapBase@PEAGX@@SA?AU?$_tlgWrapSz@G@@PEBG@Z; _tlgTypeMapBase<ushort *,void>::_tlgWrapAuto(ushort const *)
0x18000ebbe  lea     rcx, [rsp+0E8h+var_90]
0x18000ebc3  mov     [rsp+0E8h+pcbData], rcx
0x18000ebc8  lea     rcx, [rsp+0E8h+arg_10]
0x18000ebd0  mov     [rsp+0E8h+pvData], rcx
0x18000ebd5  mov     [rsp+0E8h+pdwType], rax; unsigned int
0x18000ebda  lea     rdx, byte_180017467
0x18000ebe1  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &)
0x18000ebe6  mov     rcx, [rsp+0E8h]; this
0x18000ebee  mov     r9d, ebx; char *
0x18000ebf1  mov     edx, 14Dh; void *
0x18000ebf6  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18000ebfc  lea     r12, Value; "NTP Servers"
0x18000ec03  mov     eax, cs:dword_18001C010
0x18000ec09  cmp     eax, r13d
0x18000ec0c  jbe     short loc_18000EC57
0x18000ec0e  mov     rdx, r13
0x18000ec11  lea     rcx, dword_18001C010
0x18000ec18  call    _tlgKeywordOn
0x18000ec1d  test    al, al
0x18000ec1f  jz      short loc_18000EC57
0x18000ec21  test    r15, r15
0x18000ec24  setz    byte ptr [rsp+0E8h+arg_10]
0x18000ec2c  mov     rdx, r12
  ... truncated ...
```
