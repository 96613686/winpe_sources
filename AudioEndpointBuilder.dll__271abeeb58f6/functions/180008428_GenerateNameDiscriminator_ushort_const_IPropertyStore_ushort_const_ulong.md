# GenerateNameDiscriminator(ushort const *,IPropertyStore *,ushort const *,ulong *)

- ea: `0x180008428`
- end: `0x180008994`
- name: `?GenerateNameDiscriminator@@YAJPEBGPEAUIPropertyStore@@0PEAK@Z`
- size: `1388`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct IPropertyStore *, const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000ecf0`
- `0x18002d094`

## callees

- `0x180006b0c`
- `0x180008404`
- `0x180008428`
- `0x180010da8`
- `0x18003512c`
- `0x18003514c`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008708`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008756`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008708`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180008756`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800084b9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800084c4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800087ad`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800087b8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000883d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008848`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008896`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800088a1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800088d9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800088e4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008959`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008964`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800084b9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800084c4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800087ad`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800087b8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000883d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008848`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008896`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800088a1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800088d9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800088e4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008959`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008964`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800086ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800087a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008832`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000888b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800086ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800087a2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008832`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000888b`

## string_xrefs

- `0x1800084a3`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180008541`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180008817`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18000886f`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall GenerateNameDiscriminator(
        const unsigned __int16 *a1,
        struct IPropertyStore *a2,
        const unsigned __int16 *a3,
        unsigned int *a4)
{
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rdx
  __int64 v10; // rbx
  __int64 (__fastcall *v11)(__int64, GUID *, __int64 **); // rdi
  __int64 *v12; // rcx
  unsigned __int64 v13; // r13
  int v14; // edi
  unsigned int i; // r15d
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rbx
  __int64 (__fastcall *v19)(__int64, _QWORD, __int64 *); // rsi
  __int64 v20; // rcx
  int v21; // eax
  unsigned int v22; // esi
  __int64 v23; // r14
  __int64 (__fastcall *v24)(__int64, LPVOID *); // r12
  void *v25; // rbx
  int v26; // r14d
  unsigned __int64 v27; // rax
  __int64 v28; // rdx
  int v30; // [rsp+28h] [rbp-99h]
  __int64 v31; // [rsp+38h] [rbp-89h] BYREF
  LPVOID v32; // [rsp+40h] [rbp-81h] BYREF
  __int64 v33; // [rsp+48h] [rbp-79h] BYREF
  __int64 *v34; // [rsp+50h] [rbp-71h] BYREF
  __int64 v35; // [rsp+58h] [rbp-69h] BYREF
  unsigned int v36; // [rsp+60h] [rbp-61h] BYREF
  unsigned int v37; // [rsp+64h] [rbp-5Dh]
  LPCWCH lpString2[2]; // [rsp+68h] [rbp-59h] BYREF
  __int64 v39; // [rsp+78h] [rbp-49h]
  PROPVARIANT v40[2]; // [rsp+80h] [rbp-41h] BYREF
  __int64 v41; // [rsp+90h] [rbp-31h]
  PROPVARIANT pvar[2]; // [rsp+98h] [rbp-29h] BYREF
  __int64 v43; // [rsp+A8h] [rbp-19h]
  PROPVARIANT v44[2]; // [rsp+B0h] [rbp-11h] BYREF
  __int64 v45; // [rsp+C0h] [rbp-1h]
  _BYTE v46[80]; // [rsp+C8h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+120h] [rbp+5Fh]

  v36 = 0;
  v35 = 0;
  v34 = 0;
  *(_OWORD *)v44 = 0;
  v45 = 0;
  *(_OWORD *)pvar = 0;
  v43 = 0;
  *a4 = 0;
  v5 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))a2->lpVtbl->GetValue)(
         a2,
         PKEY_Endpoint_NameDiscriminator,
         v44);
  v6 = v5;
  if ( v5 >= 0 )
  {
    if ( LOWORD(v44[0]) == 19 )
    {
      *a4 = (unsigned int)v44[1];
LABEL_71:
      v6 = 0;
      goto LABEL_72;
    }
    v7 = v35;
    v35 = 0;
    if ( v7 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    v8 = wil::com_query_to_nothrow<IPnpDeviceEnumerator,IMMDeviceEnumerator * &>(v7, &v35);
    v6 = v8;
    if ( v8 >= 0 )
    {
      v10 = v35;
      v11 = *(__int64 (__fastcall **)(__int64, GUID *, __int64 **))(*(_QWORD *)v35 + 24LL);
      v12 = v34;
      v34 = 0;
      if ( v12 )
        (*(void (__fastcall **)(__int64 *))(*v12 + 16))(v12);
      v8 = v11(v10, &GUID_6994ad04_93ef_11d0_a3cc_00a0c9223196, &v34);
      v6 = v8;
      if ( v8 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v34 + 24))(v34, &v36);
        v6 = v8;
        if ( v8 >= 0 )
        {
          v37 = 0;
          v13 = 0;
          v14 = 0;
          for ( i = 0; i < v36; ++i )
          {
            v33 = 0;
            v31 = 0;
            *(_OWORD *)v40 = 0;
            v41 = 0;
            *(_OWORD *)lpString2 = 0;
            v39 = 0;
            v32 = 0;
            v16 = *v34;
            v33 = 0;
            v17 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v16 + 32))(v34, i, &v33);
            v6 = v17;
            if ( v17 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x28B,
                (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
                (const char *)(unsigned int)v17,
                v30);
              if ( v32 )
                CoTaskMemFree(v32);
              PropVariantClear((PROPVARIANT *)lpString2);
              PropVariantClear(v40);
              if ( v31 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
              if ( v33 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
              PropVariantClear(pvar);
              PropVariantClear(v44);
              if ( v34 )
                (*(void (__fastcall **)(__int64 *))(*v34 + 16))(v34);
              if ( v35 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
              return v6;
            }
            v18 = v33;
            v19 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v33 + 32LL);
            v20 = v31;
            v31 = 0;
            if ( v20 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
            v21 = v19(v18, 0, &v31);
            v6 = v21;
            if ( v21 < 0 )
            {
              v28 = 654;
              goto LABEL_54;
            }
            v21 = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v31 + 40LL))(
                    v31,
                    PKEY_Endpoint_NameDiscriminator,
                    v40);
            v6 = v21;
            if ( v21 < 0 )
            {
              v28 = 658;
              goto LABEL_54;
            }
            v22 = 0;
            if ( LOWORD(v40[0]) == 19 )
              v22 = (unsigned int)v40[1];
            v23 = v33;
            v24 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v33 + 40LL);
            v25 = v32;
            if ( v32 )
            {
              wil::last_error_context::last_error_context((wil::last_error_context *)v46);
              CoTaskMemFree(v25);
              wil::last_error_context::~last_error_context((wil::last_error_context *)v46);
            }
            v32 = 0;
            v21 = v24(v23, &v32);
            v6 = v21;
            if ( v21 < 0 )
            {
              v28 = 662;
              goto LABEL_54;
            }
            v26 = CompareStringOrdinal(a1, -1, (LPCWCH)v32, -1, 1);
            v21 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, LPCWCH *))(*(_QWORD *)v31 + 40LL))(
                    v31,
                    &PKEY_NAME,
                    lpString2);
            v6 = v21;
            if ( v21 < 0 )
            {
              v28 = 666;
LABEL_54:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v28,
                (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
                (const char *)(unsigned int)v21,
                v30);
              if ( v32 )
                CoTaskMemFree(v32);
              PropVariantClear((PROPVARIANT *)lpString2);
              PropVariantClear(v40);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
              ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
              goto LABEL_72;
            }
            if ( LOWORD(lpString2[0]) == 31 && CompareStringOrdinal(a3, -1, lpString2[1], -1, 1) == 2 && v26 != 2 )
            {
              v13 |= 1LL << v22;
              if ( v37 > v22 )
                v22 = v37;
              v37 = v22;
              v27 = v13;
              v14 = 0;
              if ( (v13 & 1) != 0 )
              {
                while ( v14 < 64 )
                {
                  v27 >>= 1;
                  ++v14;
                  if ( (v27 & 1) == 0 )
                  {
                    if ( v14 < 64 )
                      goto LABEL_43;
                    break;
                  }
                }
                v14 = v22 + 1;
              }
            }
LABEL_43:
            if ( v32 )
              CoTaskMemFree(v32);
            PropVariantClear((PROPVARIANT *)lpString2);
            PropVariantClear(v40);
            if ( v31 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
            if ( v33 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
          }
          LOWORD(pvar[0]) = 19;
          LODWORD(pvar[1]) = v14;
          v8 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))a2->lpVtbl->SetValue)(
                 a2,
                 PKEY_Endpoint_NameDiscriminator,
                 pvar);
          v6 = v8;
          if ( v8 < 0 )
          {
            v9 = 685;
            goto LABEL_13;
          }
          *a4 = v14;
          goto LABEL_71;
        }
        v9 = 637;
      }
      else
      {
        v9 = 634;
      }
    }
    else
    {
      v9 = 632;
    }
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v8,
      v30);
LABEL_72:
    PropVariantClear(pvar);
    PropVariantClear(v44);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v34);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
    return v6;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x26C,
    (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
    (const char *)(unsigned int)v5,
    v30);
  PropVariantClear(pvar);
  PropVariantClear(v44);
  if ( v34 )
    (*(void (__fastcall **)(__int64 *))(*v34 + 16))(v34);
  if ( v35 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  return v6;
}

```

## disassembly

```asm
0x180008428  mov     rax, rsp
0x18000842b  mov     [rax+20h], r9
0x18000842f  mov     [rax+18h], r8
0x180008433  mov     [rax+10h], rdx
0x180008437  mov     [rax+8], rcx
0x18000843b  push    rbp
0x18000843c  push    rbx
0x18000843d  push    rsi
0x18000843e  push    rdi
0x18000843f  push    r12
0x180008441  push    r13
0x180008443  push    r14
0x180008445  push    r15
0x180008447  lea     rbp, [rax-5Fh]
0x18000844b  sub     rsp, 0D8h
0x180008452  mov     rsi, r9
0x180008455  mov     rcx, rdx
0x180008458  xor     r12d, r12d
0x18000845b  mov     [rbp+57h+var_B8], r12d
0x18000845f  mov     [rbp+57h+var_C0], r12
0x180008463  mov     [rbp+57h+var_C8], r12
0x180008467  xorps   xmm0, xmm0
0x18000846a  xor     eax, eax
0x18000846c  movups  xmmword ptr [rbp+57h+var_68], xmm0
0x180008470  mov     [rbp+57h+var_58], rax
0x180008474  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180008478  mov     [rbp+57h+var_70], rax
0x18000847c  mov     [r9], r12d
0x18000847f  mov     rax, [rdx]
0x180008482  lea     r8, [rbp+57h+var_68]
0x180008486  lea     rdx, PKEY_Endpoint_NameDiscriminator
0x18000848d  mov     rax, [rax+28h]
0x180008491  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008496  mov     ebx, eax
0x180008498  test    eax, eax
0x18000849a  jns     short loc_1800084FC
0x18000849c  mov     rcx, [rbp+5Fh]; this
0x1800084a0  mov     r9d, eax; char *
0x1800084a3  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x1800084aa  mov     edx, 26Ch; void *
0x1800084af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800084b4  nop
0x1800084b5  lea     rcx, [rbp+57h+pvar]; pvar
0x1800084b9  call    cs:__imp_PropVariantClear
0x1800084bf  nop
0x1800084c0  lea     rcx, [rbp+57h+var_68]; pvar
0x1800084c4  call    cs:__imp_PropVariantClear
0x1800084ca  nop
0x1800084cb  mov     rcx, [rbp+57h+var_C8]
0x1800084cf  test    rcx, rcx
0x1800084d2  jz      short loc_1800084E1
0x1800084d4  mov     rax, [rcx]
0x1800084d7  mov     rax, [rax+10h]
0x1800084db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084e0  nop
0x1800084e1  mov     rcx, [rbp+57h+var_C0]
0x1800084e5  test    rcx, rcx
0x1800084e8  jz      short loc_1800084F7
0x1800084ea  mov     rax, [rcx]
0x1800084ed  mov     rax, [rax+10h]
0x1800084f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084f6  nop
0x1800084f7  jmp     loc_18000897E
0x1800084fc  mov     r14d, 13h
0x180008502  cmp     word ptr [rbp+57h+var_68], r14w
0x180008507  jnz     short loc_180008513
0x180008509  mov     eax, dword ptr [rbp+57h+var_68+8]
0x18000850c  mov     [rsi], eax
0x18000850e  jmp     loc_180008952
0x180008513  mov     rcx, [rbp+57h+var_C0]
0x180008517  mov     [rbp+57h+var_C0], r12
0x18000851b  test    rcx, rcx
0x18000851e  jz      short loc_18000852D
0x180008520  mov     rax, [rcx]
0x180008523  mov     rax, [rax+10h]
0x180008527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000852c  nop
0x18000852d  lea     rdx, [rbp+57h+var_C0]
0x180008531  call    ??$com_query_to_nothrow@UIPnpDeviceEnumerator@@AEAPEAUIMMDeviceEnumerator@@@wil@@YAJAEAPEAUIMMDeviceEnumerator@@PEAPEAUIPnpDeviceEnumerator@@@Z; wil::com_query_to_nothrow<IPnpDeviceEnumerator,IMMDeviceEnumerator * &>(IMMDeviceEnumerator * &,IPnpDeviceEnumerator * *)
0x180008536  mov     ebx, eax
0x180008538  test    eax, eax
0x18000853a  jns     short loc_180008559
0x18000853c  mov     edx, 278h; void *
0x180008541  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180008548  mov     r9d, eax; char *
0x18000854b  mov     rcx, [rbp+5Fh]; this
0x18000854f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008554  jmp     loc_180008955
0x180008559  mov     rbx, [rbp+57h+var_C0]
0x18000855d  mov     rax, [rbx]
0x180008560  mov     rdi, [rax+18h]
0x180008564  mov     rcx, [rbp+57h+var_C8]
0x180008568  mov     [rbp+57h+var_C8], r12
0x18000856c  test    rcx, rcx
0x18000856f  jz      short loc_18000857E
0x180008571  mov     rdx, [rcx]
0x180008574  mov     rax, [rdx+10h]
0x180008578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000857d  nop
0x18000857e  lea     r8, [rbp+57h+var_C8]
0x180008582  lea     rdx, _GUID_6994ad04_93ef_11d0_a3cc_00a0c9223196
0x180008589  mov     rcx, rbx
0x18000858c  mov     rax, rdi
0x18000858f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008594  mov     ebx, eax
0x180008596  test    eax, eax
0x180008598  jns     short loc_1800085A1
0x18000859a  mov     edx, 27Ah
0x18000859f  jmp     short loc_180008541
0x1800085a1  mov     rcx, [rbp+57h+var_C8]
0x1800085a5  mov     rax, [rcx]
0x1800085a8  lea     rdx, [rbp+57h+var_B8]
0x1800085ac  mov     rax, [rax+18h]
0x1800085b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085b5  mov     ebx, eax
0x1800085b7  test    eax, eax
0x1800085b9  jns     short loc_1800085C5
0x1800085bb  mov     edx, 27Dh
0x1800085c0  jmp     loc_180008541
0x1800085c5  mov     [rbp+57h+var_B4], r12d
0x1800085c9  mov     r13, r12
0x1800085cc  mov     edi, r12d
0x1800085cf  mov     r15d, r12d
0x1800085d2  cmp     r15d, [rbp+57h+var_B8]
0x1800085d6  jnb     loc_180008919
0x1800085dc  mov     [rbp+57h+var_D0], r12
0x1800085e0  mov     [rsp+110h+var_E0], r12
0x1800085e5  xorps   xmm0, xmm0
0x1800085e8  xor     eax, eax
0x1800085ea  movups  xmmword ptr [rbp+57h+var_98], xmm0
0x1800085ee  mov     [rbp+57h+var_88], rax
0x1800085f2  movups  xmmword ptr [rbp+57h+lpString2], xmm0
0x1800085f6  mov     [rbp+57h+var_A0], rax
0x1800085fa  mov     [rsp+110h+var_D8], r12
0x1800085ff  mov     rcx, [rbp+57h+var_C8]
0x180008603  mov     rax, [rcx]
0x180008606  mov     [rbp+57h+var_D0], r12
0x18000860a  lea     r8, [rbp+57h+var_D0]
0x18000860e  mov     edx, r15d
0x180008611  mov     rax, [rax+20h]
0x180008615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000861a  mov     ebx, eax
0x18000861c  test    eax, eax
0x18000861e  js      loc_180008868
0x180008624  mov     rbx, [rbp+57h+var_D0]
0x180008628  mov     rax, [rbx]
0x18000862b  mov     rsi, [rax+20h]
0x18000862f  mov     rcx, [rsp+110h+var_E0]
0x180008634  mov     [rsp+110h+var_E0], r12
0x180008639  test    rcx, rcx
0x18000863c  jz      short loc_18000864B
0x18000863e  mov     rdx, [rcx]
0x180008641  mov     rax, [rdx+10h]
0x180008645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000864a  nop
0x18000864b  lea     r8, [rsp+110h+var_E0]
0x180008650  xor     edx, edx
0x180008652  mov     rcx, rbx
0x180008655  mov     rax, rsi
0x180008658  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000865d  mov     ebx, eax
0x18000865f  test    eax, eax
0x180008661  js      loc_18000880F
0x180008667  mov     rcx, [rsp+110h+var_E0]
0x18000866c  mov     rax, [rcx]
0x18000866f  lea     r8, [rbp+57h+var_98]
0x180008673  lea     rdx, PKEY_Endpoint_NameDiscriminator
0x18000867a  mov     rax, [rax+28h]
0x18000867e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008683  mov     ebx, eax
0x180008685  test    eax, eax
0x180008687  js      loc_180008808
0x18000868d  mov     esi, r12d
0x180008690  cmp     word ptr [rbp+57h+var_98], r14w
0x180008695  cmovz   esi, dword ptr [rbp+57h+var_98+8]
0x180008699  mov     r14, [rbp+57h+var_D0]
0x18000869d  mov     rax, [r14]
0x1800086a0  mov     r12, [rax+28h]
0x1800086a4  mov     rbx, [rsp+110h+var_D8]
0x1800086a9  test    rbx, rbx
0x1800086ac  jz      short loc_1800086C9
0x1800086ae  lea     rcx, [rbp+57h+var_50]; this
0x1800086b2  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800086b7  mov     rcx, rbx; pv
0x1800086ba  call    cs:__imp_CoTaskMemFree
0x1800086c0  lea     rcx, [rbp+57h+var_50]; this
0x1800086c4  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800086c9  mov     [rsp+110h+var_D8], 0
0x1800086d2  lea     rdx, [rsp+110h+var_D8]
0x1800086d7  mov     rcx, r14
0x1800086da  mov     rax, r12
0x1800086dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086e2  mov     ebx, eax
0x1800086e4  xor     r12d, r12d
0x1800086e7  test    eax, eax
0x1800086e9  js      loc_180008801
0x1800086ef  mov     dword ptr [rsp+20h], 1; bIgnoreCase
0x1800086f7  or      eax, 0FFFFFFFFh
0x1800086fa  mov     r9d, eax; cchCount2
0x1800086fd  mov     r8, [rsp+110h+var_D8]; lpString2
0x180008702  mov     edx, eax; cchCount1
0x180008704  mov     rcx, [rbp+57h+lpString1]; lpString1
0x180008708  call    cs:__imp_CompareStringOrdinal
0x18000870e  mov     r14d, eax
0x180008711  mov     rcx, [rsp+110h+var_E0]
0x180008716  mov     rdx, [rcx]
0x180008719  mov     rax, [rdx+28h]
0x18000871d  lea     r8, [rbp+57h+lpString2]
0x180008721  lea     rdx, PKEY_NAME
0x180008728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000872d  mov     ebx, eax
0x18000872f  test    eax, eax
0x180008731  js      loc_1800087FA
0x180008737  cmp     word ptr [rbp+57h+lpString2], 1Fh
0x18000873c  jnz     short loc_180008798
0x18000873e  mov     dword ptr [rsp+20h], 1; bIgnoreCase
0x180008746  or      ebx, 0FFFFFFFFh
0x180008749  mov     r9d, ebx; cchCount2
0x18000874c  mov     r8, [rbp+57h+lpString2+8]; lpString2
0x180008750  mov     edx, ebx; cchCount1
0x180008752  mov     rcx, [rbp+57h+arg_10]; lpString1
0x180008756  call    cs:__imp_CompareStringOrdinal
0x18000875c  cmp     eax, 2
0x18000875f  jnz     short loc_180008798
0x180008761  cmp     r14d, eax
0x180008764  jz      short loc_180008798
0x180008766  mov     eax, esi
0x180008768  bts     r13, rax
0x18000876c  cmp     [rbp+57h+var_B4], esi
0x18000876f  cmova   esi, [rbp+57h+var_B4]
0x180008773  mov     [rbp+57h+var_B4], esi
0x180008776  mov     rax, r13
0x180008779  mov     edi, r12d
0x18000877c  test    r13b, 1
0x180008780  jz      short loc_180008798
0x180008782  cmp     edi, 40h ; '@'
0x180008785  jge     short loc_180008795
0x180008787  shr     rax, 1
0x18000878a  inc     edi
0x18000878c  test    al, 1
0x18000878e  jnz     short loc_180008782
0x180008790  cmp     edi, 40h ; '@'
0x180008793  jl      short loc_180008798
0x180008795  lea     edi, [rsi+1]
0x180008798  mov     rcx, [rsp+110h+var_D8]; pv
0x18000879d  test    rcx, rcx
0x1800087a0  jz      short loc_1800087A9
0x1800087a2  call    cs:__imp_CoTaskMemFree
0x1800087a8  nop
0x1800087a9  lea     rcx, [rbp+57h+lpString2]; pvar
0x1800087ad  call    cs:__imp_PropVariantClear
0x1800087b3  nop
0x1800087b4  lea     rcx, [rbp+57h+var_98]; pvar
0x1800087b8  call    cs:__imp_PropVariantClear
0x1800087be  nop
0x1800087bf  mov     rcx, [rsp+110h+var_E0]
0x1800087c4  test    rcx, rcx
0x1800087c7  jz      short loc_1800087D6
0x1800087c9  mov     rax, [rcx]
0x1800087cc  mov     rax, [rax+10h]
0x1800087d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087d5  nop
0x1800087d6  mov     rcx, [rbp+57h+var_D0]
0x1800087da  test    rcx, rcx
0x1800087dd  jz      short loc_1800087EC
0x1800087df  mov     rax, [rcx]
0x1800087e2  mov     rax, [rax+10h]
0x1800087e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087eb  nop
0x1800087ec  inc     r15d
0x1800087ef  mov     r14d, 13h
0x1800087f5  jmp     loc_1800085D2
0x1800087fa  mov     edx, 29Ah
0x1800087ff  jmp     short loc_180008814
0x180008801  mov     edx, 296h
0x180008806  jmp     short loc_180008814
0x180008808  mov     edx, 292h
0x18000880d  jmp     short loc_180008814
0x18000880f  mov     edx, 28Eh; void *
0x180008814  mov     r9d, eax; char *
0x180008817  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18000881e  mov     rcx, [rbp+5Fh]; this
0x180008822  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008827  nop
0x180008828  mov     rcx, [rsp+110h+var_D8]; pv
0x18000882d  test    rcx, rcx
0x180008830  jz      short loc_180008839
0x180008832  call    cs:__imp_CoTaskMemFree
0x180008838  nop
0x180008839  lea     rcx, [rbp+57h+lpString2]; pvar
0x18000883d  call    cs:__imp_PropVariantClear
0x180008843  nop
0x180008844  lea     rcx, [rbp+57h+var_98]; pvar
0x180008848  call    cs:__imp_PropVariantClear
0x18000884e  nop
0x18000884f  lea     rcx, [rsp+110h+var_E0]
0x180008854  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180008859  nop
0x18000885a  lea     rcx, [rbp+57h+var_D0]
0x18000885e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
  ... truncated ...
```
