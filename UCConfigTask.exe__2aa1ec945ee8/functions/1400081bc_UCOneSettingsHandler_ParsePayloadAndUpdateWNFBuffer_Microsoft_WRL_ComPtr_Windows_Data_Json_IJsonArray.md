# UCOneSettingsHandler::ParsePayloadAndUpdateWNFBuffer(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonArray>)

- ea: `0x1400081bc`
- end: `0x14000863c`
- name: `?ParsePayloadAndUpdateWNFBuffer@UCOneSettingsHandler@@CAJV?$ComPtr@UIJsonArray@Json@Data@Windows@@@WRL@Microsoft@@@Z`
- size: `1152`
- prototype: `__int64 __fastcall(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140007ef4`

## callees

- `0x1400014c0`
- `0x14000178c`
- `0x140007d10`
- `0x140007d90`
- `0x140007e80`
- `0x140007eac`
- `0x140008190`
- `0x1400081bc`
- `0x140009010`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x140008437`
- `ntdll!RtlPublishWnfStateData` at `0x140008437`
- `ntdll!RtlNtStatusToDosError` at `0x14000843f`
- `ntdll!RtlNtStatusToDosError` at `0x14000843f`

## string_xrefs

- `0x140008325`: `CodePathIndex`

## pseudocode

```c
__int64 __fastcall UCOneSettingsHandler::ParsePayloadAndUpdateWNFBuffer(
        __int64 (__fastcall ****a1)(_QWORD, GUID *, __int64 *))
{
  __int64 (__fastcall ***v2)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v3)(_QWORD, GUID *, __int64 *); // rbx
  signed int Named; // ebx
  __int64 (__fastcall ***v5)(_QWORD, GUID *, __int64 *); // rcx
  __int64 (__fastcall ***v6)(_QWORD, GUID *, __int64 *); // rcx
  unsigned int v7; // r13d
  _DWORD *v8; // r12
  unsigned int v9; // r14d
  __int64 (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall *v11)(_QWORD, GUID *, __int64 *); // rbx
  char *v12; // r15
  __int64 v13; // rdx
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, __int64, _DWORD *); // rbx
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, __int64, char *); // rbx
  NTSTATUS v18; // eax
  signed int v19; // eax
  __int64 (__fastcall ***v20)(_QWORD, GUID *, __int64 *); // rcx
  __int64 (__fastcall ***v22)(_QWORD, GUID *, __int64 *); // rcx
  __int64 (__fastcall ***v23)(_QWORD, GUID *, __int64 *); // rcx
  __int64 (__fastcall ***v24)(_QWORD, GUID *, __int64 *); // rcx
  __int64 (__fastcall ***v25)(_QWORD, GUID *, __int64 *); // rcx
  __int64 (__fastcall ***v26)(_QWORD, GUID *, __int64 *); // rcx
  __int64 (__fastcall ***v27)(_QWORD, GUID *, __int64 *); // rcx
  __int64 (__fastcall ***v28)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v29; // [rsp+30h] [rbp-39h] BYREF
  __int64 v30; // [rsp+38h] [rbp-31h] BYREF
  unsigned int v31; // [rsp+40h] [rbp-29h] BYREF
  _QWORD v32[2]; // [rsp+48h] [rbp-21h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-11h] BYREF
  __int64 v34; // [rsp+70h] [rbp+7h]

  v32[1] = a1;
  v30 = 0;
  v2 = *a1;
  v3 = ***a1;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v30);
  Named = v3(v2, &GUID_d44662bc_dce3_59a8_9272_4b210f33908b, &v30);
  if ( Named >= 0 )
  {
    v31 = 0;
    Named = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v30 + 56LL))(v30, &v31);
    if ( Named >= 0 )
    {
      v7 = 20 * (v31 - 1) + 28;
      v8 = operator new[](v7);
      v32[0] = v8;
      *v8 = 1;
      v8[1] = v31;
      v9 = 0;
      if ( v31 )
      {
        while ( 1 )
        {
          v29 = 0;
          v10 = *a1;
          v11 = (**a1)[6];
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v29);
          Named = v11(v10, (GUID *)v9, &v29);
          if ( Named < 0 )
            break;
          v12 = (char *)&v8[5 * v9];
          Named = IJsonObjectGetNamedInteger<unsigned long>(v29, L"Id", v12 + 8);
          if ( Named < 0 )
          {
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v29);
            std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(v32);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v30);
            v27 = *a1;
            if ( *a1 )
            {
              *a1 = 0;
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v27)[2])(v27);
            }
            return (unsigned int)Named;
          }
          Named = IJsonObjectGetNamedInteger<unsigned long>(v29, L"CodePathIndex", v12 + 12);
          if ( Named < 0 )
          {
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v29);
            std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(v32);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v30);
            v26 = *a1;
            if ( *a1 )
            {
              *a1 = 0;
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v26)[2])(v26);
            }
            return (unsigned int)Named;
          }
          Named = IJsonObjectGetNamedInteger<unsigned long>(v29, L"ErrorCode", v12 + 16);
          if ( Named < 0 )
          {
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v29);
            std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(v32);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v30);
            v25 = *a1;
            if ( *a1 )
            {
              *a1 = 0;
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v25)[2])(v25);
            }
            return (unsigned int)Named;
          }
          Named = IJsonObjectGetNamedInteger<enum _UC_ONESETTINGS_CONFIG_V1_FLAGS>(v29, v13, v12 + 20);
          if ( Named < 0 )
          {
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v29);
            std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(v32);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v30);
            v24 = *a1;
            if ( *a1 )
            {
              *a1 = 0;
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v24)[2])(v24);
            }
            return (unsigned int)Named;
          }
          v14 = v29;
          v15 = *(__int64 (__fastcall **)(__int64, __int64, _DWORD *))(*(_QWORD *)v29 + 96LL);
          v34 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"IsDumpCollect", 0xEu, 0xDu);
          Named = v15(v14, v34, (_DWORD *)v12 + 6);
          if ( Named < 0 )
          {
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v29);
            std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(v32);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v30);
            v23 = *a1;
            if ( *a1 )
            {
              *a1 = 0;
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v23)[2])(v23);
            }
            return (unsigned int)Named;
          }
          v16 = v29;
          v17 = *(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)v29 + 96LL);
          v34 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"SkipEventLogging", 0x11u, 0x10u);
          Named = v17(v16, v34, v12 + 25);
          if ( Named < 0 )
          {
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v29);
            std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(v32);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v30);
            v22 = *a1;
            if ( *a1 )
            {
              *a1 = 0;
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v22)[2])(v22);
            }
            return (unsigned int)Named;
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v29);
          if ( ++v9 >= v31 )
            goto LABEL_18;
        }
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v29);
        std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(v32);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v30);
        v28 = *a1;
        if ( *a1 )
        {
          *a1 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v28)[2])(v28);
        }
      }
      else
      {
LABEL_18:
        v18 = RtlPublishWnfStateData(WNF_UCP_CLIENT_CONFIG_BUFFER, 0, v8, v7, 0);
        v19 = RtlNtStatusToDosError(v18);
        Named = v19;
        if ( v19 > 0 )
          Named = (unsigned __int16)v19 | 0x80070000;
        std::unique_ptr<unsigned char [0]>::~unique_ptr<unsigned char [0]>(v32);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v30);
        v20 = *a1;
        if ( *a1 )
        {
          *a1 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v20)[2])(v20);
        }
      }
    }
    else
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v30);
      v6 = *a1;
      if ( *a1 )
      {
        *a1 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v6)[2])(v6);
      }
    }
  }
  else
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(&v30);
    v5 = *a1;
    if ( *a1 )
    {
      *a1 = 0;
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v5)[2])(v5);
    }
  }
  return (unsigned int)Named;
}

```

## disassembly

```asm
0x1400081bc  push    rbp
0x1400081be  push    rbx
0x1400081bf  push    rsi
0x1400081c0  push    rdi
0x1400081c1  push    r12
0x1400081c3  push    r13
0x1400081c5  push    r14
0x1400081c7  push    r15
0x1400081c9  lea     rbp, [rsp-1Fh]
0x1400081ce  sub     rsp, 88h
0x1400081d5  mov     rax, cs:__security_cookie
0x1400081dc  xor     rax, rsp
0x1400081df  mov     [rbp+57h+var_48], rax
0x1400081e3  mov     rsi, rcx
0x1400081e6  mov     [rbp+57h+var_70], rcx
0x1400081ea  xor     r15d, r15d
0x1400081ed  mov     [rbp+57h+var_88], r15
0x1400081f1  mov     rdi, [rcx]
0x1400081f4  mov     rax, [rdi]
0x1400081f7  mov     rbx, [rax]
0x1400081fa  lea     rcx, [rbp+57h+var_88]
0x1400081fe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x140008203  lea     r8, [rbp+57h+var_88]
0x140008207  lea     rdx, _GUID_d44662bc_dce3_59a8_9272_4b210f33908b
0x14000820e  mov     rcx, rdi
0x140008211  mov     rax, rbx
0x140008214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008219  mov     ebx, eax
0x14000821b  test    eax, eax
0x14000821d  jns     short loc_140008246
0x14000821f  lea     rcx, [rbp+57h+var_88]
0x140008223  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x140008228  nop
0x140008229  mov     rcx, [rsi]
0x14000822c  test    rcx, rcx
0x14000822f  jz      short loc_140008241
0x140008231  mov     [rsi], r15
0x140008234  mov     rax, [rcx]
0x140008237  mov     rax, [rax+10h]
0x14000823b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008240  nop
0x140008241  jmp     loc_140008480
0x140008246  mov     [rbp+57h+var_80], r15d
0x14000824a  mov     rcx, [rbp+57h+var_88]
0x14000824e  mov     rax, [rcx]
0x140008251  lea     rdx, [rbp+57h+var_80]
0x140008255  mov     rax, [rax+38h]
0x140008259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000825e  mov     ebx, eax
0x140008260  test    eax, eax
0x140008262  jns     short loc_14000828B
0x140008264  lea     rcx, [rbp+57h+var_88]
0x140008268  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x14000826d  nop
0x14000826e  mov     rcx, [rsi]
0x140008271  test    rcx, rcx
0x140008274  jz      short loc_140008286
0x140008276  mov     [rsi], r15
0x140008279  mov     rax, [rcx]
0x14000827c  mov     rax, [rax+10h]
0x140008280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008285  nop
0x140008286  jmp     loc_140008480
0x14000828b  mov     eax, [rbp+57h+var_80]
0x14000828e  dec     eax
0x140008290  lea     ecx, [rax+rax*4]
0x140008293  lea     r13d, ds:1Ch[rcx*4]
0x14000829b  mov     ecx, r13d; unsigned __int64
0x14000829e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1400082a3  mov     r12, rax
0x1400082a6  mov     [rbp+57h+var_78], rax
0x1400082aa  mov     dword ptr [rax], 1
0x1400082b0  mov     ecx, [rbp+57h+var_80]
0x1400082b3  mov     [rax+4], ecx
0x1400082b6  mov     r14d, r15d
0x1400082b9  cmp     [rbp+57h+var_80], r15d
0x1400082bd  jbe     loc_140008423
0x1400082c3  mov     [rbp+57h+var_90], r15
0x1400082c7  mov     rdi, [rsi]
0x1400082ca  mov     rax, [rdi]
0x1400082cd  mov     rbx, [rax+30h]
0x1400082d1  lea     rcx, [rbp+57h+var_90]
0x1400082d5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x1400082da  lea     r8, [rbp+57h+var_90]
0x1400082de  mov     edx, r14d
0x1400082e1  mov     rcx, rdi
0x1400082e4  mov     rax, rbx
0x1400082e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400082ec  mov     ebx, eax
0x1400082ee  test    eax, eax
0x1400082f0  js      loc_140008601
0x1400082f6  mov     eax, r14d
0x1400082f9  lea     rcx, [rax+rax*4]
0x1400082fd  lea     r15, [r12+rcx*4]
0x140008301  lea     r8, [r15+8]
0x140008305  lea     rdx, aId; "Id"
0x14000830c  mov     rcx, [rbp+57h+var_90]
0x140008310  call    ??$IJsonObjectGetNamedInteger@K@@YAJPEAUIJsonObject@Json@Data@Windows@@PEBGPEAK@Z; IJsonObjectGetNamedInteger<ulong>(Windows::Data::Json::IJsonObject *,ushort const *,ulong *)
0x140008315  mov     ebx, eax
0x140008317  xor     edi, edi
0x140008319  test    eax, eax
0x14000831b  js      loc_1400085C6
0x140008321  lea     r8, [r15+0Ch]
0x140008325  lea     rdx, aCodepathindex; "CodePathIndex"
0x14000832c  mov     rcx, [rbp+57h+var_90]
0x140008330  call    ??$IJsonObjectGetNamedInteger@K@@YAJPEAUIJsonObject@Json@Data@Windows@@PEBGPEAK@Z; IJsonObjectGetNamedInteger<ulong>(Windows::Data::Json::IJsonObject *,ushort const *,ulong *)
0x140008335  mov     ebx, eax
0x140008337  test    eax, eax
0x140008339  js      loc_14000858B
0x14000833f  lea     r8, [r15+10h]
0x140008343  lea     rdx, aErrorcode; "ErrorCode"
0x14000834a  mov     rcx, [rbp+57h+var_90]
0x14000834e  call    ??$IJsonObjectGetNamedInteger@K@@YAJPEAUIJsonObject@Json@Data@Windows@@PEBGPEAK@Z; IJsonObjectGetNamedInteger<ulong>(Windows::Data::Json::IJsonObject *,ushort const *,ulong *)
0x140008353  mov     ebx, eax
0x140008355  test    eax, eax
0x140008357  js      loc_140008550
0x14000835d  lea     r8, [r15+14h]
0x140008361  mov     rcx, [rbp+57h+var_90]
0x140008365  call    ??$IJsonObjectGetNamedInteger@W4_UC_ONESETTINGS_CONFIG_V1_FLAGS@@@@YAJPEAUIJsonObject@Json@Data@Windows@@PEBGPEAW4_UC_ONESETTINGS_CONFIG_V1_FLAGS@@@Z; IJsonObjectGetNamedInteger<_UC_ONESETTINGS_CONFIG_V1_FLAGS>(Windows::Data::Json::IJsonObject *,ushort const *,_UC_ONESETTINGS_CONFIG_V1_FLAGS *)
0x14000836a  mov     ebx, eax
0x14000836c  test    eax, eax
0x14000836e  js      loc_140008515
0x140008374  mov     rdi, [rbp+57h+var_90]
0x140008378  mov     rax, [rdi]
0x14000837b  mov     rbx, [rax+60h]
0x14000837f  mov     [rbp+57h+var_50], 0
0x140008387  mov     r9d, 0Dh; unsigned int
0x14000838d  lea     r8d, [r9+1]; unsigned int
0x140008391  lea     rdx, aIsdumpcollect; "IsDumpCollect"
0x140008398  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x14000839c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1400083a1  nop
0x1400083a2  lea     r8, [r15+18h]
0x1400083a6  mov     rdx, [rbp+57h+var_50]
0x1400083aa  mov     rcx, rdi
0x1400083ad  mov     rax, rbx
0x1400083b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400083b5  mov     ebx, eax
0x1400083b7  test    eax, eax
0x1400083b9  js      loc_1400084D6
0x1400083bf  mov     rdi, [rbp+57h+var_90]
0x1400083c3  mov     rax, [rdi]
0x1400083c6  mov     rbx, [rax+60h]
0x1400083ca  mov     [rbp+57h+var_50], 0
0x1400083d2  mov     r9d, 10h; unsigned int
0x1400083d8  lea     r8d, [r9+1]; unsigned int
0x1400083dc  lea     rdx, aSkipeventloggi; "SkipEventLogging"
0x1400083e3  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x1400083e7  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1400083ec  nop
0x1400083ed  lea     r8, [r15+19h]
0x1400083f1  mov     rdx, [rbp+57h+var_50]
0x1400083f5  mov     rcx, rdi
0x1400083f8  mov     rax, rbx
0x1400083fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008400  mov     ebx, eax
0x140008402  xor     r15d, r15d
0x140008405  lea     rcx, [rbp+57h+var_90]
0x140008409  test    eax, eax
0x14000840b  js      loc_1400084A2
0x140008411  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x140008416  inc     r14d
0x140008419  cmp     r14d, [rbp+57h+var_80]
0x14000841d  jb      loc_1400082C3
0x140008423  mov     [rsp+0C0h+var_A0], r15
0x140008428  mov     r9d, r13d
0x14000842b  mov     r8, r12
0x14000842e  xor     edx, edx
0x140008430  mov     rcx, cs:WNF_UCP_CLIENT_CONFIG_BUFFER
0x140008437  call    cs:__imp_RtlPublishWnfStateData
0x14000843d  mov     ecx, eax; Status
0x14000843f  call    cs:__imp_RtlNtStatusToDosError
0x140008445  mov     ebx, eax
0x140008447  test    eax, eax
0x140008449  jle     short loc_140008454
0x14000844b  movzx   ebx, ax
0x14000844e  or      ebx, 80070000h
0x140008454  lea     rcx, [rbp+57h+var_78]
0x140008458  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x14000845d  nop
0x14000845e  lea     rcx, [rbp+57h+var_88]
0x140008462  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x140008467  nop
0x140008468  mov     rcx, [rsi]
0x14000846b  test    rcx, rcx
0x14000846e  jz      short loc_140008480
0x140008470  mov     [rsi], r15
0x140008473  mov     rdx, [rcx]
0x140008476  mov     rax, [rdx+10h]
0x14000847a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000847f  nop
0x140008480  mov     eax, ebx
0x140008482  mov     rcx, [rbp+57h+var_48]
0x140008486  xor     rcx, rsp; StackCookie
0x140008489  call    __security_check_cookie
0x14000848e  add     rsp, 88h
0x140008495  pop     r15
0x140008497  pop     r14
0x140008499  pop     r13
0x14000849b  pop     r12
0x14000849d  pop     rdi
0x14000849e  pop     rsi
0x14000849f  pop     rbx
0x1400084a0  pop     rbp
0x1400084a1  retn
0x1400084a2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x1400084a7  nop
0x1400084a8  lea     rcx, [rbp+57h+var_78]
0x1400084ac  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x1400084b1  nop
0x1400084b2  lea     rcx, [rbp+57h+var_88]
0x1400084b6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x1400084bb  nop
0x1400084bc  mov     rcx, [rsi]
0x1400084bf  test    rcx, rcx
0x1400084c2  jz      short loc_1400084D4
0x1400084c4  mov     [rsi], r15
0x1400084c7  mov     rax, [rcx]
0x1400084ca  mov     rax, [rax+10h]
0x1400084ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400084d3  nop
0x1400084d4  jmp     short loc_140008480
0x1400084d6  lea     rcx, [rbp+57h+var_90]
0x1400084da  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x1400084df  nop
0x1400084e0  lea     rcx, [rbp+57h+var_78]
0x1400084e4  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x1400084e9  nop
0x1400084ea  lea     rcx, [rbp+57h+var_88]
0x1400084ee  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x1400084f3  nop
0x1400084f4  mov     rcx, [rsi]
0x1400084f7  test    rcx, rcx
0x1400084fa  jz      short loc_140008510
0x1400084fc  mov     qword ptr [rsi], 0
0x140008503  mov     rax, [rcx]
0x140008506  mov     rax, [rax+10h]
0x14000850a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000850f  nop
0x140008510  jmp     loc_140008480
0x140008515  lea     rcx, [rbp+57h+var_90]
0x140008519  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x14000851e  nop
0x14000851f  lea     rcx, [rbp+57h+var_78]
0x140008523  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x140008528  nop
0x140008529  lea     rcx, [rbp+57h+var_88]
0x14000852d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x140008532  nop
0x140008533  mov     rcx, [rsi]
0x140008536  test    rcx, rcx
0x140008539  jz      short loc_14000854B
0x14000853b  mov     [rsi], rdi
0x14000853e  mov     rax, [rcx]
0x140008541  mov     rax, [rax+10h]
0x140008545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000854a  nop
0x14000854b  jmp     loc_140008480
0x140008550  lea     rcx, [rbp+57h+var_90]
0x140008554  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x140008559  nop
0x14000855a  lea     rcx, [rbp+57h+var_78]
0x14000855e  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x140008563  nop
0x140008564  lea     rcx, [rbp+57h+var_88]
0x140008568  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x14000856d  nop
0x14000856e  mov     rcx, [rsi]
0x140008571  test    rcx, rcx
0x140008574  jz      short loc_140008586
0x140008576  mov     [rsi], rdi
0x140008579  mov     rax, [rcx]
0x14000857c  mov     rax, [rax+10h]
0x140008580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008585  nop
0x140008586  jmp     loc_140008480
0x14000858b  lea     rcx, [rbp+57h+var_90]
0x14000858f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x140008594  nop
0x140008595  lea     rcx, [rbp+57h+var_78]
0x140008599  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x14000859e  nop
0x14000859f  lea     rcx, [rbp+57h+var_88]
0x1400085a3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x1400085a8  nop
0x1400085a9  mov     rcx, [rsi]
0x1400085ac  test    rcx, rcx
0x1400085af  jz      short loc_1400085C1
0x1400085b1  mov     [rsi], rdi
0x1400085b4  mov     rax, [rcx]
0x1400085b7  mov     rax, [rax+10h]
0x1400085bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400085c0  nop
0x1400085c1  jmp     loc_140008480
0x1400085c6  lea     rcx, [rbp+57h+var_90]
0x1400085ca  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x1400085cf  nop
0x1400085d0  lea     rcx, [rbp+57h+var_78]
0x1400085d4  call    ??1?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAA@XZ; std::unique_ptr<uchar [0]>::~unique_ptr<uchar [0]>(void)
0x1400085d9  nop
  ... truncated ...
```
