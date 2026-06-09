# Windows::Internal::Storage::Cloud::CloudStore::LoadAndResolveInternal(ushort const *,Windows::Storage::Streams::IBuffer *,unsigned __int64,Windows::Storage::Streams::IBuffer *,unsigned __int64,Windows::Storage::Streams::IBuffer * *,unsigned __int64 *,Windows::Storage::Streams::IBuffer * *,unsigned __int64 *)

- ea: `0x18003a478`
- end: `0x18003ac55`
- name: `?LoadAndResolveInternal@CloudStore@Cloud@Storage@Internal@Windows@@AEAAJPEBGPEAUIBuffer@Streams@35@_K12PEAPEAU6735@PEA_K34@Z`
- size: `2013`
- prototype: `__int64 __fastcall(Windows::Internal::Storage::Cloud::CloudStore *__hidden this, const unsigned __int16 *, struct Windows::Storage::Streams::IBuffer *, unsigned __int64, struct Windows::Storage::Streams::IBuffer *, unsigned __int64, struct Windows::Storage::Streams::IBuffer **, unsigned __int64 *, struct Windows::Storage::Streams::IBuffer **, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800393b4`
- `0x1800608ac`

## callees

- `0x18000f4b4`
- `0x180019720`
- `0x180021e20`
- `0x1800238d0`
- `0x180023fd4`
- `0x180024fd0`
- `0x18003a478`
- `0x18005ac7c`
- `0x18005b770`
- `0x18005b8a4`
- `0x18005d938`
- `0x18005f7bc`
- `0x1800a63c8`
- `0x1800c8458`
- `0x1800d19b8`
- `0x1800e93e0`
- `0x1801201a0`
- `0x18016b818`
- `0x180208010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a596`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a6a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a7b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a8bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a989`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a596`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a6a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a7b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a835`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a8bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a989`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall Windows::Internal::Storage::Cloud::CloudStore::LoadAndResolveInternal(
        __int64 **this,
        const unsigned __int16 *a2,
        struct Windows::Storage::Streams::IBuffer *a3,
        __int64 a4,
        struct Windows::Storage::Streams::IBuffer *a5,
        unsigned __int64 a6,
        struct Windows::Storage::Streams::IBuffer **a7,
        unsigned __int64 *a8,
        struct Windows::Storage::Streams::IBuffer **a9,
        unsigned __int64 *a10)
{
  struct Windows::Storage::Streams::IBuffer *v10; // r12
  struct Windows::Storage::Streams::IBuffer *v13; // r15
  char v14; // bl
  int v15; // eax
  const char *v16; // r9
  int v17; // edi
  void *v18; // rcx
  unsigned int v19; // esi
  _QWORD *v20; // rax
  unsigned int v21; // ecx
  unsigned __int64 v22; // rsi
  int v23; // eax
  unsigned int v24; // ebx
  void *v25; // rcx
  unsigned __int64 v26; // rcx
  unsigned __int64 v27; // rcx
  __int64 result; // rax
  __int64 *v29; // rdi
  __int64 (__fastcall *v30)(__int64 *, const unsigned __int16 *, struct Windows::Storage::Streams::IBuffer *, __int64); // rbx
  int v31; // eax
  unsigned int v32; // ebx
  void *v33; // rcx
  unsigned __int64 v34; // rcx
  unsigned __int64 v35; // rcx
  LPVOID v36; // r8
  int v37; // edi
  __int64 v38; // r12
  _QWORD *v39; // r15
  void *v40; // rcx
  unsigned __int64 v41; // rcx
  unsigned __int64 v42; // rcx
  unsigned __int64 v43; // rdi
  unsigned __int64 v44; // rax
  struct Windows::Storage::Streams::IBuffer *v45; // rax
  unsigned __int64 v46; // rcx
  void *v47; // rax
  unsigned __int64 v48; // rcx
  _QWORD *v49; // rax
  __int64 v50; // rcx
  _QWORD *v51; // rax
  __int64 v52; // rcx
  _QWORD *v53; // rax
  int v54; // ecx
  bool v55; // zf
  unsigned __int64 v56; // rbx
  int v57; // [rsp+20h] [rbp-128h]
  int v58; // [rsp+20h] [rbp-128h]
  unsigned int v59; // [rsp+60h] [rbp-E8h] BYREF
  unsigned __int64 v60; // [rsp+68h] [rbp-E0h] BYREF
  int v61[2]; // [rsp+70h] [rbp-D8h] BYREF
  unsigned __int64 v62; // [rsp+78h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+80h] [rbp-C8h] BYREF
  unsigned __int64 v64; // [rsp+88h] [rbp-C0h]
  struct Windows::Storage::Streams::IBuffer *v65; // [rsp+90h] [rbp-B8h]
  struct Windows::Storage::Streams::IBuffer *v66; // [rsp+98h] [rbp-B0h]
  __int64 v67; // [rsp+A0h] [rbp-A8h]
  struct Windows::Storage::Streams::IBuffer **v68; // [rsp+A8h] [rbp-A0h]
  unsigned __int64 *v69; // [rsp+B0h] [rbp-98h]
  struct Windows::Storage::Streams::IBuffer **v70; // [rsp+B8h] [rbp-90h]
  unsigned __int64 *v71; // [rsp+C0h] [rbp-88h]
  _QWORD *p_pv; // [rsp+C8h] [rbp-80h] BYREF
  int v73[2]; // [rsp+D0h] [rbp-78h] BYREF
  char v74; // [rsp+D8h] [rbp-70h]
  unsigned __int64 v75; // [rsp+E0h] [rbp-68h]
  _BYTE v76[32]; // [rsp+E8h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  v67 = a4;
  v10 = a3;
  v66 = a3;
  v13 = a5;
  v65 = a5;
  v68 = a7;
  v69 = a8;
  v70 = a9;
  v71 = a10;
  v14 = 0;
  *a7 = 0;
  *a8 = 0;
  *a9 = 0;
  *a10 = 0;
  *(_QWORD *)v61 = 0;
  v62 = 0;
  v60 = 0;
  v64 = 0;
  pv = 0;
  v59 = 0;
  p_pv = &pv;
  *(_QWORD *)v73 = 0;
  v74 = 1;
  v15 = Windows::Internal::Storage::Cloud::CloudStore::LoadInternal(this, a2, (unsigned __int8 **)v73, &v59, &v62);
  v17 = v15;
  if ( v74 )
  {
    v18 = (void *)*p_pv;
    *p_pv = *(_QWORD *)v73;
    if ( v18 )
      CoTaskMemFree(v18);
  }
  try
  {
    if ( v17 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1211,
        (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
        (const char *)(unsigned int)v17,
        v57);
      if ( (Microsoft_Windows_CloudStoreEnableBits & 1) != 0 )
      {
        std::wstring::wstring(&p_pv);
        v59 = 64;
        v49 = (_QWORD *)WideStringToUtf8String(v76, &p_pv);
        v14 = -64;
        if ( v49[3] > 0xFu )
          v49 = (_QWORD *)*v49;
        McTemplateU0sq_EventWriteTransfer(v50, HealingStore, v49, (unsigned int)v17);
      }
      if ( v14 < 0 )
      {
        v14 &= ~0x80u;
        std::string::_Tidy_deallocate(v76);
      }
      v55 = (v14 & 0x40) == 0;
    }
    else
    {
      v19 = v59;
      if ( v59 )
      {
        p_pv = v61;
        *(_QWORD *)v73 = 0;
        v74 = 1;
        v36 = pv;
        pv = 0;
        v37 = Windows::Storage::Streams::MakeCBuffer<void (*)(void *)>(
                v59,
                v59,
                (__int64)v36,
                (void (__fastcall *)(__int64))CoTaskMemFree,
                v73);
        if ( v74 )
        {
          v38 = *(_QWORD *)v73;
          v39 = p_pv;
          if ( *p_pv )
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*p_pv + 16LL))(*p_pv);
          *v39 = v38;
          v13 = v65;
          v10 = v66;
        }
        if ( v37 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1215,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
            (const char *)(unsigned int)v37,
            v57);
          v40 = pv;
          pv = 0;
          if ( v40 )
            CoTaskMemFree(v40);
          v41 = v60;
          if ( v60 )
          {
            v60 = 0;
            (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v41 + 16LL))(v41);
          }
          v42 = *(_QWORD *)v61;
          if ( *(_QWORD *)v61 )
          {
            *(_QWORD *)v61 = 0;
            (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v42 + 16LL))(v42);
          }
          return (unsigned int)v37;
        }
      }
      if ( !v13 )
      {
        v22 = v62;
        v43 = a6;
        if ( v62 > a6 )
        {
          if ( (Microsoft_Windows_CloudStoreEnableBits & 2) != 0 )
          {
            std::wstring::wstring(&p_pv);
            v59 = 16;
            v53 = (_QWORD *)WideStringToUtf8String(v76, &p_pv);
            v14 = 48;
            if ( v53[3] > 0xFu )
              v53 = (_QWORD *)*v53;
            McTemplateU0sxx_EventWriteTransfer(v54, (unsigned int)Debug_DeleteChangeConflict, (_DWORD)v53, v22, a6);
          }
          if ( (v14 & 0x20) != 0 )
          {
            v14 &= ~0x20u;
            std::string::_Tidy_deallocate(v76);
          }
          if ( (v14 & 0x10) != 0 )
            std::wstring::~wstring(&p_pv);
          v56 = *(_QWORD *)v61;
          if ( v60 != *(_QWORD *)v61 )
          {
            v62 = *(_QWORD *)v61;
            Microsoft::WRL::ComPtr<Windows::Storage::Streams::IBuffer>::InternalAddRef(&v62);
            v62 = v60;
            v60 = v56;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
          }
          v43 = v22;
          v64 = v22;
          goto LABEL_49;
        }
        if ( v60 )
        {
          v62 = 0;
          Microsoft::WRL::ComPtr<Windows::Storage::Streams::IBuffer>::InternalAddRef(&v62);
          v62 = v60;
          v60 = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v62);
        }
LABEL_48:
        v64 = v43;
LABEL_49:
        v44 = *(_QWORD *)v61;
        *(_QWORD *)v61 = 0;
        *v68 = (struct Windows::Storage::Streams::IBuffer *)v44;
        *v69 = v22;
        v45 = (struct Windows::Storage::Streams::IBuffer *)v60;
        v46 = 0;
        v60 = 0;
        *v70 = v45;
        *v71 = v43;
        v47 = pv;
        pv = 0;
        if ( v47 )
        {
          CoTaskMemFree(v47);
          v46 = v60;
        }
        if ( v46 )
        {
          v60 = 0;
          (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v46 + 16LL))(v46);
        }
        v48 = *(_QWORD *)v61;
        if ( *(_QWORD *)v61 )
        {
          *(_QWORD *)v61 = 0;
          (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v48 + 16LL))(v48);
        }
        return 0;
      }
      if ( v19 )
      {
        if ( (Microsoft_Windows_CloudStoreEnableBits & 2) != 0 )
        {
          std::wstring::wstring(&p_pv);
          v59 = 1;
          v20 = (_QWORD *)WideStringToUtf8String(v76, &p_pv);
          v14 = 3;
          v21 = v19;
          v22 = v62;
          if ( v20[3] > 0xFu )
            v20 = (_QWORD *)*v20;
          McTemplateU0sxx_EventWriteTransfer(v21, (unsigned int)Debug_SavingWithTheirsData, (_DWORD)v20, v62, v21);
        }
        else
        {
          v22 = v62;
        }
        if ( (v14 & 2) != 0 )
        {
          v14 &= ~2u;
          std::string::_Tidy_deallocate(v76);
        }
        if ( (v14 & 1) != 0 && v75 > 7 )
          std::_Deallocate<16>(p_pv, (const struct std::nothrow_t *)(2 * v75 + 2));
        v23 = Windows::Internal::Storage::Cloud::CloudStore::EnsureTypeServices((Windows::Internal::Storage::Cloud::CloudStore *)this);
        v24 = v23;
        if ( v23 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1222,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
            (const char *)(unsigned int)v23,
            v57);
          v25 = pv;
          pv = 0;
          if ( v25 )
            CoTaskMemFree(v25);
          v26 = v60;
          if ( v60 )
          {
            v60 = 0;
            (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v26 + 16LL))(v26);
          }
          v27 = *(_QWORD *)v61;
          if ( *(_QWORD *)v61 )
          {
            *(_QWORD *)v61 = 0;
            (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v27 + 16LL))(v27);
          }
          return v24;
        }
        v29 = this[60];
        v30 = *(__int64 (__fastcall **)(__int64 *, const unsigned __int16 *, struct Windows::Storage::Streams::IBuffer *, __int64))(*v29 + 24);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v60);
        v58 = v61[0];
        v31 = v30(v29, a2, v10, v67);
        v32 = v31;
        if ( v31 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x122C,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
            (const char *)(unsigned int)v31,
            v58);
          v33 = pv;
          pv = 0;
          if ( v33 )
            CoTaskMemFree(v33);
          v34 = v60;
          if ( v60 )
          {
            v60 = 0;
            (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v34 + 16LL))(v34);
          }
          v35 = *(_QWORD *)v61;
          if ( *(_QWORD *)v61 )
          {
            *(_QWORD *)v61 = 0;
            (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v35 + 16LL))(v35);
          }
          return v32;
        }
        v43 = v64;
        goto LABEL_49;
      }
      if ( (Microsoft_Windows_CloudStoreEnableBits & 2) != 0 )
      {
        std::wstring::wstring(&p_pv);
        v59 = 4;
        v51 = (_QWORD *)WideStringToUtf8String(v76, &p_pv);
        v14 = 12;
        if ( v51[3] > 0xFu )
          v51 = (_QWORD *)*v51;
        McTemplateU0s_EventWriteTransfer(v52, Debug_SavingWithoutTheirsData, v51);
      }
      if ( (v14 & 8) != 0 )
      {
        v14 &= ~8u;
        std::string::_Tidy_deallocate(v76);
      }
      v55 = (v14 & 4) == 0;
    }
    if ( !v55 )
      std::wstring::~wstring(&p_pv);
    Microsoft::WRL::ComPtr<Windows::Storage::Streams::IBuffer>::operator=(&v60, v13);
    v43 = a6;
    v22 = v62;
    goto LABEL_48;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x125C,
                           (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\api\\src\\cloudstore.cpp",
                           v16);
  }
  return result;
}

```

## disassembly

```asm
0x18003a478  mov     r11, rsp
0x18003a47b  push    rbx
0x18003a47c  push    rsi
0x18003a47d  push    rdi
0x18003a47e  push    r12
0x18003a480  push    r13
0x18003a482  push    r14
0x18003a484  push    r15
0x18003a486  sub     rsp, 110h
0x18003a48d  mov     rax, cs:__security_cookie
0x18003a494  xor     rax, rsp
0x18003a497  mov     [rsp+148h+var_40], rax
0x18003a49f  mov     [rsp+148h+var_A8], r9
0x18003a4a7  mov     r12, r8
0x18003a4aa  mov     [rsp+148h+var_B0], r8
0x18003a4b2  mov     r14, rdx
0x18003a4b5  mov     r13, rcx
0x18003a4b8  mov     r15, [rsp+148h+arg_20]
0x18003a4c0  mov     [rsp+148h+var_B8], r15
0x18003a4c8  mov     rax, [rsp+148h+arg_30]
0x18003a4d0  mov     [rsp+148h+var_A0], rax
0x18003a4d8  mov     rcx, [rsp+148h+arg_38]
0x18003a4e0  mov     [rsp+148h+var_98], rcx
0x18003a4e8  mov     rdx, [rsp+148h+arg_40]
0x18003a4f0  mov     [rsp+148h+var_90], rdx
0x18003a4f8  mov     r8, [rsp+148h+arg_48]
0x18003a500  mov     [rsp+148h+var_88], r8
0x18003a508  xor     esi, esi
0x18003a50a  mov     ebx, esi
0x18003a50c  mov     [rsp+148h+var_E8], ebx
0x18003a510  mov     [rax], rsi
0x18003a513  mov     [rcx], rsi
0x18003a516  mov     [rdx], rsi
0x18003a519  mov     [r8], rsi
0x18003a51c  mov     qword ptr [rsp+148h+var_D8], rsi
0x18003a521  mov     [rsp+148h+var_D0], rsi
0x18003a526  mov     [rsp+148h+var_E0], rsi
0x18003a52b  mov     [r11-0C0h], rsi
0x18003a532  mov     [r11-0C8h], rsi
0x18003a539  mov     [rsp+148h+var_E8], esi
0x18003a53d  lea     rax, [r11-0C8h]
0x18003a544  mov     [r11-80h], rax
0x18003a548  mov     [r11-78h], rsi
0x18003a54c  mov     byte ptr [r11-70h], 1
0x18003a551  lea     rax, [rsp+148h+var_D0]
0x18003a556  mov     [rsp+148h+var_128], rax; int
0x18003a55b  lea     r9, [rsp+148h+var_E8]; unsigned int *
0x18003a560  lea     r8, [r11-78h]; unsigned __int8 **
0x18003a564  mov     rdx, r14; unsigned __int16 *
0x18003a567  mov     rcx, r13; this
0x18003a56a  call    ?LoadInternal@CloudStore@Cloud@Storage@Internal@Windows@@AEAAJPEBGPEAPEAEPEAKPEA_K@Z; Windows::Internal::Storage::Cloud::CloudStore::LoadInternal(ushort const *,uchar * *,ulong *,unsigned __int64 *)
0x18003a56f  mov     edi, eax
0x18003a571  cmp     [rsp+148h+var_70], sil
0x18003a579  jz      short loc_18003A59C
0x18003a57b  mov     r8, [rsp+148h+var_80]
0x18003a583  mov     rcx, [r8]; pv
0x18003a586  mov     rdx, qword ptr [rsp+148h+var_78]
0x18003a58e  mov     [r8], rdx
0x18003a591  test    rcx, rcx
0x18003a594  jz      short loc_18003A59C
0x18003a596  call    cs:__imp_CoTaskMemFree
0x18003a59c  mov     rcx, [rsp+148h]; this
0x18003a5a4  test    edi, edi
0x18003a5a6  js      loc_18003AAFF
0x18003a5ac  mov     esi, [rsp+148h+var_E8]
0x18003a5b0  xor     edi, edi
0x18003a5b2  test    esi, esi
0x18003a5b4  jnz     loc_18003A7FB
0x18003a5ba  test    r15, r15
0x18003a5bd  jz      loc_18003A902
0x18003a5c3  test    esi, esi
0x18003a5c5  jz      loc_18003AB4C
0x18003a5cb  test    cs:Microsoft_Windows_CloudStoreEnableBits, 2
0x18003a5d2  jz      loc_18003A9DB
0x18003a5d8  mov     rdx, r14
0x18003a5db  lea     rcx, [rsp+148h+var_80]
0x18003a5e3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003a5e8  nop
0x18003a5e9  mov     [rsp+148h+var_E8], 1
0x18003a5f1  lea     rdx, [rsp+148h+var_80]
0x18003a5f9  lea     rcx, [rsp+148h+var_60]
0x18003a601  call    ?WideStringToUtf8String@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; WideStringToUtf8String(std::wstring const &)
0x18003a606  mov     ebx, 3
0x18003a60b  mov     rcx, rsi
0x18003a60e  mov     rsi, [rsp+148h+var_D0]
0x18003a613  cmp     qword ptr [rax+18h], 0Fh
0x18003a618  jbe     short loc_18003A61D
0x18003a61a  mov     rax, [rax]
0x18003a61d  mov     [rsp+148h+var_128], rcx; int
0x18003a622  mov     r9, rsi
0x18003a625  mov     r8, rax
0x18003a628  lea     rdx, Debug_SavingWithTheirsData
0x18003a62f  call    McTemplateU0sxx_EventWriteTransfer
0x18003a634  test    bl, 2
0x18003a637  jnz     loc_18003A9EC
0x18003a63d  test    bl, 1
0x18003a640  jz      short loc_18003A665
0x18003a642  mov     rdx, [rsp+148h+var_68]
0x18003a64a  cmp     rdx, 7
0x18003a64e  jbe     short loc_18003A665
0x18003a650  lea     rdx, ds:2[rdx*2]
0x18003a658  mov     rcx, [rsp+148h+var_80]
0x18003a660  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18003a665  mov     rcx, r13; this
0x18003a668  call    ?EnsureTypeServices@CloudStore@Cloud@Storage@Internal@Windows@@AEAAJXZ; Windows::Internal::Storage::Cloud::CloudStore::EnsureTypeServices(void)
0x18003a66d  mov     ebx, eax
0x18003a66f  test    eax, eax
0x18003a671  jns     loc_18003A70D
0x18003a677  mov     rcx, [rsp+148h]; this
0x18003a67f  mov     r9d, eax; char *
0x18003a682  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18003a689  mov     edx, 1222h; void *
0x18003a68e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a693  nop
0x18003a694  mov     rcx, [rsp+148h+pv]; pv
0x18003a69c  mov     [rsp+148h+pv], rdi
0x18003a6a4  test    rcx, rcx
0x18003a6a7  jz      short loc_18003A6B0
0x18003a6a9  call    cs:__imp_CoTaskMemFree
0x18003a6af  nop
0x18003a6b0  mov     rcx, [rsp+148h+var_E0]
0x18003a6b5  test    rcx, rcx
0x18003a6b8  jz      short loc_18003A6CC
0x18003a6ba  mov     [rsp+148h+var_E0], rdi
0x18003a6bf  mov     rax, [rcx]
0x18003a6c2  mov     rax, [rax+10h]
0x18003a6c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a6cb  nop
0x18003a6cc  mov     rcx, qword ptr [rsp+148h+var_D8]
0x18003a6d1  test    rcx, rcx
0x18003a6d4  jz      short loc_18003A6E8
0x18003a6d6  mov     qword ptr [rsp+148h+var_D8], rdi
0x18003a6db  mov     rax, [rcx]
0x18003a6de  mov     rax, [rax+10h]
0x18003a6e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a6e7  nop
0x18003a6e8  mov     eax, ebx
0x18003a6ea  mov     rcx, [rsp+148h+var_40]
0x18003a6f2  xor     rcx, rsp; StackCookie
0x18003a6f5  call    __security_check_cookie
0x18003a6fa  add     rsp, 110h
0x18003a701  pop     r15
0x18003a703  pop     r14
0x18003a705  pop     r13
0x18003a707  pop     r12
0x18003a709  pop     rdi
0x18003a70a  pop     rsi
0x18003a70b  pop     rbx
0x18003a70c  retn
0x18003a70d  mov     rdi, [r13+1E0h]
0x18003a714  mov     rax, [rdi]
0x18003a717  mov     rbx, [rax+18h]
0x18003a71b  lea     rcx, [rsp+148h+var_E0]
0x18003a720  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003a725  mov     r10, qword ptr [rsp+148h+var_D8]
0x18003a72a  lea     rax, [rsp+148h+var_C0]
0x18003a732  mov     [rsp+148h+var_100], rax
0x18003a737  lea     rax, [rsp+148h+var_E0]
0x18003a73c  mov     [rsp+148h+var_108], rax
0x18003a741  mov     rdx, [rsp+148h+arg_28]
0x18003a749  mov     [rsp+148h+var_110], rdx
0x18003a74e  mov     [rsp+148h+var_118], r15
0x18003a753  mov     [rsp+148h+var_120], rsi
0x18003a758  mov     [rsp+148h+var_128], r10; int
0x18003a75d  mov     r9, [rsp+148h+var_A8]
0x18003a765  mov     r8, r12
0x18003a768  mov     rdx, r14
0x18003a76b  mov     rcx, rdi
0x18003a76e  mov     rax, rbx
0x18003a771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a776  mov     ebx, eax
0x18003a778  xor     r14d, r14d
0x18003a77b  test    eax, eax
0x18003a77d  jns     loc_18003A9CE
0x18003a783  mov     rcx, [rsp+148h]; this
0x18003a78b  mov     r9d, eax; char *
0x18003a78e  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18003a795  mov     edx, 122Ch; void *
0x18003a79a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a79f  nop
0x18003a7a0  mov     rcx, [rsp+148h+pv]; pv
0x18003a7a8  mov     [rsp+148h+pv], r14
0x18003a7b0  test    rcx, rcx
0x18003a7b3  jz      short loc_18003A7BC
0x18003a7b5  call    cs:__imp_CoTaskMemFree
0x18003a7bb  nop
0x18003a7bc  mov     rcx, [rsp+148h+var_E0]
0x18003a7c1  test    rcx, rcx
0x18003a7c4  jz      short loc_18003A7D8
0x18003a7c6  mov     [rsp+148h+var_E0], r14
0x18003a7cb  mov     rax, [rcx]
0x18003a7ce  mov     rax, [rax+10h]
0x18003a7d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a7d7  nop
0x18003a7d8  mov     rcx, qword ptr [rsp+148h+var_D8]
0x18003a7dd  test    rcx, rcx
0x18003a7e0  jz      short loc_18003A7F4
0x18003a7e2  mov     qword ptr [rsp+148h+var_D8], r14
0x18003a7e7  mov     rax, [rcx]
0x18003a7ea  mov     rax, [rax+10h]
0x18003a7ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a7f3  nop
0x18003a7f4  mov     eax, ebx
0x18003a7f6  jmp     loc_18003A6EA
0x18003a7fb  lea     rax, [rsp+148h+var_D8]
0x18003a800  mov     [rsp+148h+var_80], rax
0x18003a808  mov     qword ptr [rsp+148h+var_78], rdi
0x18003a810  mov     [rsp+148h+var_70], 1
0x18003a818  mov     r8, [rsp+148h+pv]
0x18003a820  mov     [rsp+148h+pv], rdi
0x18003a828  lea     rax, [rsp+148h+var_78]
0x18003a830  mov     [rsp+148h+var_128], rax; int
0x18003a835  mov     r9, cs:__imp_CoTaskMemFree
0x18003a83c  mov     edx, esi
0x18003a83e  mov     ecx, esi
0x18003a840  call    ??$MakeCBuffer@P6AXPEAX@Z@Streams@Storage@Windows@@YAJIIPEAEP6AXPEAX@ZPEAPEAUIBuffer@012@@Z; Windows::Storage::Streams::MakeCBuffer<void (*)(void *)>(uint,uint,uchar *,void (*)(void *),Windows::Storage::Streams::IBuffer * *)
0x18003a845  mov     edi, eax
0x18003a847  cmp     [rsp+148h+var_70], 0
0x18003a84f  jz      short loc_18003A880
0x18003a851  mov     r12, qword ptr [rsp+148h+var_78]
0x18003a859  mov     r15, [rsp+148h+var_80]
0x18003a861  mov     rcx, [r15]
0x18003a864  test    rcx, rcx
0x18003a867  jnz     loc_18003AB3B
0x18003a86d  mov     [r15], r12
0x18003a870  mov     r15, [rsp+148h+var_B8]
0x18003a878  mov     r12, [rsp+148h+var_B0]
0x18003a880  test    edi, edi
0x18003a882  jns     loc_18003A9E5
0x18003a888  mov     rcx, [rsp+148h]; this
0x18003a890  mov     r9d, edi; char *
0x18003a893  lea     r8, aOnecoreuapShel_44; "onecoreuap\\shell\\cloudstore\\store\\a"...
0x18003a89a  mov     edx, 1215h; void *
0x18003a89f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a8a4  nop
0x18003a8a5  mov     rcx, [rsp+148h+pv]; pv
0x18003a8ad  xor     ebx, ebx
0x18003a8af  mov     [rsp+148h+pv], rbx
0x18003a8b7  test    rcx, rcx
0x18003a8ba  jz      short loc_18003A8C3
0x18003a8bc  call    cs:__imp_CoTaskMemFree
0x18003a8c2  nop
0x18003a8c3  mov     rcx, [rsp+148h+var_E0]
0x18003a8c8  test    rcx, rcx
0x18003a8cb  jz      short loc_18003A8DF
0x18003a8cd  mov     [rsp+148h+var_E0], rbx
0x18003a8d2  mov     rax, [rcx]
0x18003a8d5  mov     rax, [rax+10h]
0x18003a8d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a8de  nop
0x18003a8df  mov     rcx, qword ptr [rsp+148h+var_D8]
0x18003a8e4  test    rcx, rcx
0x18003a8e7  jz      short loc_18003A8FB
0x18003a8e9  mov     qword ptr [rsp+148h+var_D8], rbx
0x18003a8ee  mov     rax, [rcx]
0x18003a8f1  mov     rax, [rax+10h]
0x18003a8f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a8fa  nop
0x18003a8fb  mov     eax, edi
0x18003a8fd  jmp     loc_18003A6EA
0x18003a902  mov     rsi, [rsp+148h+var_D0]
0x18003a907  mov     rdi, [rsp+148h+arg_28]
0x18003a90f  cmp     rsi, rdi
0x18003a912  ja      loc_18003ABA3
0x18003a918  xor     r14d, r14d
0x18003a91b  cmp     [rsp+148h+var_E0], r14
0x18003a920  jnz     loc_18003AC1F
0x18003a926  mov     [rsp+148h+var_C0], rdi
0x18003a92e  mov     rax, qword ptr [rsp+148h+var_D8]
0x18003a933  mov     qword ptr [rsp+148h+var_D8], r14
0x18003a938  mov     rcx, [rsp+148h+var_A0]
0x18003a940  mov     [rcx], rax
0x18003a943  mov     rax, [rsp+148h+var_98]
0x18003a94b  mov     [rax], rsi
0x18003a94e  mov     rax, [rsp+148h+var_E0]
0x18003a953  mov     rcx, r14
0x18003a956  mov     [rsp+148h+var_E0], rcx
0x18003a95b  mov     rdx, [rsp+148h+var_90]
0x18003a963  mov     [rdx], rax
0x18003a966  mov     rax, [rsp+148h+var_88]
0x18003a96e  mov     [rax], rdi
0x18003a971  mov     rax, [rsp+148h+pv]
0x18003a979  mov     [rsp+148h+pv], r14
0x18003a981  test    rax, rax
0x18003a984  jz      short loc_18003A994
0x18003a986  mov     rcx, rax; pv
0x18003a989  call    cs:__imp_CoTaskMemFree
0x18003a98f  mov     rcx, [rsp+148h+var_E0]
0x18003a994  test    rcx, rcx
0x18003a997  jz      short loc_18003A9AB
0x18003a999  mov     [rsp+148h+var_E0], r14
0x18003a99e  mov     rax, [rcx]
0x18003a9a1  mov     rax, [rax+10h]
0x18003a9a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a9aa  nop
0x18003a9ab  mov     rcx, qword ptr [rsp+148h+var_D8]
0x18003a9b0  test    rcx, rcx
0x18003a9b3  jz      short loc_18003A9C7
0x18003a9b5  mov     qword ptr [rsp+148h+var_D8], r14
0x18003a9ba  mov     rax, [rcx]
  ... truncated ...
```
