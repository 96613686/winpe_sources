# CMtfPredictionCandidate::Deserialize(IStream *)

- ea: `0x1800263c0`
- end: `0x1800268d9`
- name: `?Deserialize@CMtfPredictionCandidate@@UEAAJPEAUIStream@@@Z`
- size: `1305`
- prototype: `__int64 __fastcall(CMtfPredictionCandidate *__hidden this, struct IStream *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001fc4`
- `0x180002d88`
- `0x1800251b8`
- `0x1800263c0`
- `0x18002af7c`
- `0x18002bca0`
- `0x18002f010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x1800264a9`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800264a9`
- `OLEAUT32!__imp_SysFreeString` at `0x18002646d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002647f`
- `OLEAUT32!__imp_SysFreeString` at `0x18002646d`
- `OLEAUT32!__imp_SysFreeString` at `0x18002647f`

## pseudocode

```c
__int64 __fastcall CMtfPredictionCandidate::Deserialize(CMtfPredictionCandidate *this, struct IStream *a2)
{
  int v4; // ebx
  void *v5; // rbx
  __int64 v6; // rcx
  unsigned int i; // r13d
  char *v8; // rdi
  bool v9; // al
  __int64 v10; // rcx
  __int64 v11; // r14
  __int64 *v12; // rdx
  _QWORD *v13; // rax
  _QWORD *v14; // rdi
  __int64 *v15; // r14
  bool v16; // al
  __int64 v17; // rcx
  __int64 v18; // rdi
  CMtfPredictionCandidate *v19; // rax
  CMtfPredictionCandidate *v20; // r14
  bool v21; // al
  __int64 v22; // rcx
  char v24[8]; // [rsp+30h] [rbp-88h] BYREF
  __int64 v25; // [rsp+38h] [rbp-80h] BYREF
  __int64 v26; // [rsp+40h] [rbp-78h] BYREF
  __int64 v27; // [rsp+48h] [rbp-70h] BYREF
  _QWORD *v28; // [rsp+50h] [rbp-68h] BYREF
  _QWORD v29[2]; // [rsp+58h] [rbp-60h] BYREF
  unsigned __int64 v30[2]; // [rsp+68h] [rbp-50h] BYREF
  int v31; // [rsp+78h] [rbp-40h]

  v25 = 0;
  v26 = 0;
  (*(void (__fastcall **)(char *))(*((_QWORD *)this - 5) + 80LL))((char *)this - 40);
  *(_OWORD *)v30 = 0;
  v31 = 0;
  v4 = (*(__int64 (__fastcall **)(struct IStream *, unsigned __int64 *, __int64))(*(_QWORD *)a2 + 24LL))(a2, v30, 20);
  if ( v4 >= 0 )
  {
    *(_QWORD *)((char *)this + 60) = v30[0];
    *((_DWORD *)this + 17) = v30[1];
    *((_WORD *)this + 36) = WORD2(v30[1]);
    *((_BYTE *)this + 76) = 0;
    SysFreeString(*((BSTR *)this + 6));
    *((_QWORD *)this + 6) = 0;
    SysFreeString(*((BSTR *)this + 5));
    *((_QWORD *)this + 5) = 0;
    if ( !LODWORD(v30[1])
      || ((v5 = operator new[](LODWORD(v30[1])), v5 == *((void **)this + 4))
        ? (v5 = (void *)*((_QWORD *)this + 4))
        : (void *)(operator delete[](*((void **)this + 4)), *((_QWORD *)this + 4) = v5),
          v4 = (*(__int64 (__fastcall **)(struct IStream *, void *, _QWORD, _QWORD))(*(_QWORD *)a2 + 24LL))(
                 a2,
                 v5,
                 LODWORD(v30[1]),
                 0),
          v4 >= 0) )
    {
      if ( !(_BYTE)v31
        || (v4 = ((__int64 (__fastcall *)(GUID *, _QWORD, __int64, GUID *, __int64 *))Hooked_CoCreateInstance)(
                   &CLSID_MtfPropertyBag,
                   0,
                   1,
                   &GUID_06445657_3a07_492d_94c3_052034ef2d12,
                   &v26),
            v4 >= 0)
        && (v4 = (*(__int64 (__fastcall **)(__int64, struct IStream *))(*(_QWORD *)v26 + 40LL))(v26, a2), v4 >= 0)
        && (v4 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v26)(
                   v26,
                   &GUID_47445657_8d68_4b3b_b716_b0debdd9b3f5,
                   &v25),
            v4 >= 0) )
      {
        v6 = *((_QWORD *)this + 10);
        if ( v6 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
        *((_QWORD *)this + 10) = v25;
        v25 = 0;
        for ( i = 0; ; ++i )
        {
          if ( i >= HIWORD(v30[1]) )
            goto LABEL_70;
          v24[0] = 0;
          v4 = (*(__int64 (__fastcall **)(struct IStream *, char *, __int64, _QWORD))(*(_QWORD *)a2 + 24LL))(
                 a2,
                 v24,
                 1,
                 0);
          if ( v4 < 0 )
            goto LABEL_70;
          if ( v24[0] == 1 )
            break;
          if ( v24[0] != 2 )
          {
            if ( v24[0] != 3 )
            {
              v4 = -2147418113;
              goto LABEL_70;
            }
            v19 = (CMtfPredictionCandidate *)operator new(0x98u);
            if ( v19 )
              v20 = CMtfPredictionCandidate::CMtfPredictionCandidate(v19);
            else
              v20 = 0;
            v4 = (*(__int64 (__fastcall **)(__int64, struct IStream *))(*((_QWORD *)v20 + 5) + 40LL))(
                   (__int64)v20 + 40,
                   a2);
            if ( v4 < 0 )
            {
              if ( v20 )
                (*(void (__fastcall **)(CMtfPredictionCandidate *))(*(_QWORD *)v20 + 16LL))(v20);
              goto LABEL_70;
            }
            v8 = (char *)this + 8;
            if ( v20 )
              v20 = (CMtfPredictionCandidate *)((char *)v20 + 8);
            v29[0] = v20;
            v21 = (unsigned __int64)v29 < *((_QWORD *)this + 2) && *(_QWORD *)v8 <= (unsigned __int64)v29;
            v22 = *((_QWORD *)this + 3);
            if ( v21 )
            {
              v11 = *(_QWORD *)v8;
              if ( *((_QWORD *)this + 2) == v22 )
                std::vector<IMtfSuggestionListElement *>::_Reserve((char *)this + 8, 1);
              v12 = v29;
LABEL_25:
              **((_QWORD **)v8 + 1) = *(_QWORD *)(*(_QWORD *)v8 + 8 * (((__int64)v12 - v11) >> 3));
            }
            else
            {
              if ( *((_QWORD *)this + 2) == v22 )
                std::vector<IMtfSuggestionListElement *>::_Reserve((char *)this + 8, 1);
              **((_QWORD **)this + 2) = v20;
            }
            goto LABEL_65;
          }
          v13 = operator new(0x50u);
          v14 = v13;
          if ( v13 )
          {
            *v13 = &MtfPrimitiveImpl::`vftable'{for `IMtfSuggestionListElement'};
            v13[1] = &MtfPrimitiveImpl::`vftable'{for `IMtfSuggestionCandidatePrimitive'};
            v13[2] = &MtfPrimitiveImpl::`vftable'{for `IMtfPrimitive'};
            v13[3] = &MtfPrimitiveImpl::`vftable'{for `IMtfSerializable'};
            v13[4] = 0;
            v13[5] = 0;
            v13[6] = 0;
            v13[7] = 1;
            v13[8] = 0;
            *((_DWORD *)v13 + 18) = -65536;
            *((_WORD *)v13 + 38) = -1;
            _InterlockedAdd(&g_cRefDll, 1u);
          }
          v4 = (*(__int64 (__fastcall **)(_QWORD *, struct IStream *))(v13[3] + 40LL))(v13 + 3, a2);
          if ( v4 < 0 )
          {
            if ( v14 )
              (*(void (__fastcall **)(_QWORD *))(*v14 + 16LL))(v14);
            goto LABEL_70;
          }
          v15 = (__int64 *)((char *)this + 8);
          v28 = v14;
          v16 = (unsigned __int64)&v28 < *((_QWORD *)this + 2) && *v15 <= (unsigned __int64)&v28;
          v17 = *((_QWORD *)this + 3);
          if ( v16 )
          {
            v18 = *v15;
            if ( *((_QWORD *)this + 2) == v17 )
              std::vector<IMtfSuggestionListElement *>::_Reserve((char *)this + 8, 1);
            **((_QWORD **)this + 2) = *(_QWORD *)(*((_QWORD *)this + 1) + 8 * (((__int64)&v29[-1] - v18) >> 3));
          }
          else
          {
            if ( *((_QWORD *)this + 2) == v17 )
              std::vector<IMtfSuggestionListElement *>::_Reserve((char *)this + 8, 1);
            **((_QWORD **)this + 2) = v14;
          }
          *((_QWORD *)this + 2) += 8LL;
LABEL_66:
          ;
        }
        v8 = (char *)this + 8;
        v27 = 0;
        v9 = (unsigned __int64)&v27 < *((_QWORD *)this + 2) && *(_QWORD *)v8 <= (unsigned __int64)&v27;
        v10 = *((_QWORD *)this + 3);
        if ( v9 )
        {
          v11 = *(_QWORD *)v8;
          if ( *((_QWORD *)this + 2) == v10 )
            std::vector<IMtfSuggestionListElement *>::_Reserve((char *)this + 8, 1);
          v12 = &v27;
          goto LABEL_25;
        }
        if ( *((_QWORD *)this + 2) == v10 )
          std::vector<IMtfSuggestionListElement *>::_Reserve((char *)this + 8, 1);
        **((_QWORD **)this + 2) = 0;
LABEL_65:
        *((_QWORD *)v8 + 1) += 8LL;
        goto LABEL_66;
      }
    }
  }
LABEL_70:
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800263c0  mov     r11, rsp
0x1800263c3  mov     [r11+18h], rbx
0x1800263c7  mov     [r11+20h], rsi
0x1800263cb  push    rdi
0x1800263cc  push    r12
0x1800263ce  push    r13
0x1800263d0  push    r14
0x1800263d2  push    r15
0x1800263d4  sub     rsp, 90h
0x1800263db  mov     rax, cs:__security_cookie
0x1800263e2  xor     rax, rsp
0x1800263e5  mov     [rsp+0B8h+var_38], rax
0x1800263ed  mov     r12, rdx
0x1800263f0  mov     rsi, rcx
0x1800263f3  mov     qword ptr [r11-80h], 0
0x1800263fb  mov     qword ptr [r11-78h], 0
0x180026403  add     rcx, 0FFFFFFFFFFFFFFD8h
0x180026407  mov     rax, [rcx]
0x18002640a  mov     rax, [rax+50h]
0x18002640e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026413  xorps   xmm0, xmm0
0x180026416  xor     eax, eax
0x180026418  movups  xmmword ptr [rsp+0B8h+var_50], xmm0
0x18002641d  mov     [rsp+0B8h+var_40], eax
0x180026421  mov     rax, [r12]
0x180026425  xor     r9d, r9d
0x180026428  lea     r8d, [r9+14h]
0x18002642c  lea     rdx, [rsp+0B8h+var_50]
0x180026431  mov     rcx, r12
0x180026434  mov     rax, [rax+18h]
0x180026438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002643d  mov     ebx, eax
0x18002643f  test    eax, eax
0x180026441  js      loc_180026876
0x180026447  mov     eax, dword ptr [rsp+0B8h+var_50]
0x18002644b  mov     [rsi+3Ch], eax
0x18002644e  mov     eax, dword ptr [rsp+0B8h+var_50+4]
0x180026452  mov     [rsi+40h], eax
0x180026455  mov     eax, dword ptr [rsp+0B8h+var_50+8]
0x180026459  mov     [rsi+44h], eax
0x18002645c  movzx   eax, word ptr [rsp+0B8h+var_50+0Ch]
0x180026461  mov     [rsi+48h], ax
0x180026465  mov     byte ptr [rsi+4Ch], 0
0x180026469  mov     rcx, [rsi+30h]; bstrString
0x18002646d  call    cs:__imp_SysFreeString
0x180026473  mov     qword ptr [rsi+30h], 0
0x18002647b  mov     rcx, [rsi+28h]; bstrString
0x18002647f  call    cs:__imp_SysFreeString
0x180026485  mov     qword ptr [rsi+28h], 0
0x18002648d  mov     eax, dword ptr [rsp+0B8h+var_50+8]
0x180026491  test    eax, eax
0x180026493  jz      short loc_1800264DE
0x180026495  mov     ecx, eax; unsigned __int64
0x180026497  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002649c  mov     rbx, rax
0x18002649f  cmp     rax, [rsi+20h]
0x1800264a3  jz      short loc_1800264B5
0x1800264a5  mov     rcx, [rsi+20h]
0x1800264a9  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800264af  mov     [rsi+20h], rbx
0x1800264b3  jmp     short loc_1800264B9
0x1800264b5  mov     rbx, [rsi+20h]
0x1800264b9  mov     rax, [r12]
0x1800264bd  xor     r9d, r9d
0x1800264c0  mov     r8d, dword ptr [rsp+0B8h+var_50+8]
0x1800264c5  mov     rdx, rbx
0x1800264c8  mov     rcx, r12
0x1800264cb  mov     rax, [rax+18h]
0x1800264cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800264d4  mov     ebx, eax
0x1800264d6  test    eax, eax
0x1800264d8  js      loc_180026876
0x1800264de  mov     r15d, 1
0x1800264e4  cmp     byte ptr [rsp+0B8h+var_40], 0
0x1800264e9  jz      short loc_180026562
0x1800264eb  lea     rax, [rsp+0B8h+var_78]
0x1800264f0  mov     [rsp+0B8h+var_98], rax
0x1800264f5  lea     r9, _GUID_06445657_3a07_492d_94c3_052034ef2d12
0x1800264fc  mov     r8d, r15d
0x1800264ff  xor     edx, edx
0x180026501  lea     rcx, CLSID_MtfPropertyBag
0x180026508  mov     rax, cs:?Hooked_CoCreateInstance@@3P6AJAEBU_GUID@@PEAUIUnknown@@K0PEAPEAX@ZEA; long (*Hooked_CoCreateInstance)(_GUID const &,IUnknown *,ulong,_GUID const &,void * *)
0x18002650f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026514  mov     ebx, eax
0x180026516  test    eax, eax
0x180026518  js      loc_180026876
0x18002651e  mov     rcx, [rsp+0B8h+var_78]
0x180026523  mov     rax, [rcx]
0x180026526  mov     rdx, r12
0x180026529  mov     rax, [rax+28h]
0x18002652d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026532  mov     ebx, eax
0x180026534  test    eax, eax
0x180026536  js      loc_180026876
0x18002653c  mov     rcx, [rsp+0B8h+var_78]
0x180026541  mov     rax, [rcx]
0x180026544  lea     r8, [rsp+0B8h+var_80]
0x180026549  lea     rdx, _GUID_47445657_8d68_4b3b_b716_b0debdd9b3f5
0x180026550  mov     rax, [rax]
0x180026553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026558  mov     ebx, eax
0x18002655a  test    eax, eax
0x18002655c  js      loc_180026876
0x180026562  mov     rcx, [rsi+50h]
0x180026566  test    rcx, rcx
0x180026569  jz      short loc_180026577
0x18002656b  mov     rax, [rcx]
0x18002656e  mov     rax, [rax+10h]
0x180026572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026577  mov     rax, [rsp+0B8h+var_80]
0x18002657c  mov     [rsi+50h], rax
0x180026580  mov     [rsp+0B8h+var_80], 0
0x180026589  xor     r13d, r13d
0x18002658c  mov     r14d, 0FFFFh
0x180026592  movzx   eax, word ptr [rsp+0B8h+var_50+0Eh]
0x180026597  cmp     r13d, eax
0x18002659a  jnb     loc_180026876
0x1800265a0  mov     [rsp+0B8h+var_88], 0
0x1800265a5  mov     rax, [r12]
0x1800265a9  xor     r9d, r9d
0x1800265ac  mov     r8d, r15d
0x1800265af  lea     rdx, [rsp+0B8h+var_88]
0x1800265b4  mov     rcx, r12
0x1800265b7  mov     rax, [rax+18h]
0x1800265bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800265c0  mov     ebx, eax
0x1800265c2  test    eax, eax
0x1800265c4  js      loc_180026876
0x1800265ca  mov     al, [rsp+0B8h+var_88]
0x1800265ce  cmp     al, r15b
0x1800265d1  jnz     loc_18002665C
0x1800265d7  lea     rdi, [rsi+8]
0x1800265db  mov     [rsp+0B8h+var_70], 0
0x1800265e4  lea     rax, [rsp+0B8h+var_70]
0x1800265e9  cmp     rax, [rsi+10h]
0x1800265ed  jnb     short loc_1800265FE
0x1800265ef  lea     rax, [rsp+0B8h+var_70]
0x1800265f4  cmp     [rdi], rax
0x1800265f7  ja      short loc_1800265FE
0x1800265f9  mov     al, r15b
0x1800265fc  jmp     short loc_180026600
0x1800265fe  xor     al, al
0x180026600  mov     rcx, [rsi+18h]
0x180026604  test    al, al
0x180026606  jz      short loc_18002663B
0x180026608  mov     r14, [rdi]
0x18002660b  cmp     [rsi+10h], rcx
0x18002660f  jnz     short loc_18002661C
0x180026611  mov     rdx, r15
0x180026614  mov     rcx, rdi
0x180026617  call    ?_Reserve@?$vector@PEAUIMtfSuggestionListElement@@V?$allocator@PEAUIMtfSuggestionListElement@@@std@@@std@@IEAAX_K@Z; std::vector<IMtfSuggestionListElement *>::_Reserve(unsigned __int64)
0x18002661c  lea     rdx, [rsp+0B8h+var_70]
0x180026621  sub     rdx, r14
0x180026624  sar     rdx, 3
0x180026628  mov     rax, [rdi]
0x18002662b  mov     rcx, [rdi+8]
0x18002662f  mov     rax, [rax+rdx*8]
0x180026633  mov     [rcx], rax
0x180026636  jmp     loc_180026848
0x18002663b  cmp     [rsi+10h], rcx
0x18002663f  jnz     short loc_18002664C
0x180026641  mov     rdx, r15
0x180026644  mov     rcx, rdi
0x180026647  call    ?_Reserve@?$vector@PEAUIMtfSuggestionListElement@@V?$allocator@PEAUIMtfSuggestionListElement@@@std@@@std@@IEAAX_K@Z; std::vector<IMtfSuggestionListElement *>::_Reserve(unsigned __int64)
0x18002664c  mov     rax, [rdi+8]
0x180026650  mov     qword ptr [rax], 0
0x180026657  jmp     loc_18002684E
0x18002665c  cmp     al, 2
0x18002665e  jnz     loc_18002679C
0x180026664  mov     ecx, 50h ; 'P'; Size
0x180026669  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002666e  mov     rdi, rax
0x180026671  test    rdi, rdi
0x180026674  jz      short loc_1800266DD
0x180026676  lea     rax, ??_7MtfPrimitiveImpl@@6BIMtfSuggestionListElement@@@; const MtfPrimitiveImpl::`vftable'{for `IMtfSuggestionListElement'}
0x18002667d  mov     [rdi], rax
0x180026680  lea     rax, ??_7MtfPrimitiveImpl@@6BIMtfSuggestionCandidatePrimitive@@@; const MtfPrimitiveImpl::`vftable'{for `IMtfSuggestionCandidatePrimitive'}
0x180026687  mov     [rdi+8], rax
0x18002668b  lea     rax, ??_7MtfPrimitiveImpl@@6BIMtfPrimitive@@@; const MtfPrimitiveImpl::`vftable'{for `IMtfPrimitive'}
0x180026692  mov     [rdi+10h], rax
0x180026696  lea     rax, ??_7MtfPrimitiveImpl@@6BIMtfSerializable@@@; const MtfPrimitiveImpl::`vftable'{for `IMtfSerializable'}
0x18002669d  mov     [rdi+18h], rax
0x1800266a1  mov     qword ptr [rdi+20h], 0
0x1800266a9  mov     qword ptr [rdi+28h], 0
0x1800266b1  mov     qword ptr [rdi+30h], 0
0x1800266b9  mov     qword ptr [rdi+38h], 1
0x1800266c1  mov     qword ptr [rdi+40h], 0
0x1800266c9  mov     dword ptr [rdi+48h], 0FFFF0000h
0x1800266d0  mov     [rdi+4Ch], r14w
0x1800266d5  lock add cs:?g_cRefDll@@3JA, r15d; long g_cRefDll
0x1800266dd  lea     rcx, [rdi+18h]
0x1800266e1  mov     rax, [rcx]
0x1800266e4  mov     rdx, r12
0x1800266e7  mov     rax, [rax+28h]
0x1800266eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800266f0  mov     ebx, eax
0x1800266f2  test    eax, eax
0x1800266f4  js      loc_18002677F
0x1800266fa  lea     r14, [rsi+8]
0x1800266fe  mov     [rsp+0B8h+var_68], rdi
0x180026703  lea     rax, [rsp+0B8h+var_68]
0x180026708  cmp     rax, [rsi+10h]
0x18002670c  jnb     short loc_18002671D
0x18002670e  lea     rax, [rsp+0B8h+var_68]
0x180026713  cmp     [r14], rax
0x180026716  ja      short loc_18002671D
0x180026718  mov     al, r15b
0x18002671b  jmp     short loc_18002671F
0x18002671d  xor     al, al
0x18002671f  mov     rcx, [rsi+18h]
0x180026723  test    al, al
0x180026725  jz      short loc_180026757
0x180026727  mov     rdi, [r14]
0x18002672a  cmp     [rsi+10h], rcx
0x18002672e  jnz     short loc_18002673B
0x180026730  mov     rdx, r15
0x180026733  mov     rcx, r14
0x180026736  call    ?_Reserve@?$vector@PEAUIMtfSuggestionListElement@@V?$allocator@PEAUIMtfSuggestionListElement@@@std@@@std@@IEAAX_K@Z; std::vector<IMtfSuggestionListElement *>::_Reserve(unsigned __int64)
0x18002673b  lea     rdx, [rsp+0B8h+var_68]
0x180026740  sub     rdx, rdi
0x180026743  sar     rdx, 3
0x180026747  mov     rax, [r14]
0x18002674a  mov     rcx, [r14+8]
0x18002674e  mov     rax, [rax+rdx*8]
0x180026752  mov     [rcx], rax
0x180026755  jmp     short loc_18002676F
0x180026757  cmp     [rsi+10h], rcx
0x18002675b  jnz     short loc_180026768
0x18002675d  mov     rdx, r15
0x180026760  mov     rcx, r14
0x180026763  call    ?_Reserve@?$vector@PEAUIMtfSuggestionListElement@@V?$allocator@PEAUIMtfSuggestionListElement@@@std@@@std@@IEAAX_K@Z; std::vector<IMtfSuggestionListElement *>::_Reserve(unsigned __int64)
0x180026768  mov     rax, [r14+8]
0x18002676c  mov     [rax], rdi
0x18002676f  add     qword ptr [r14+8], 8
0x180026774  mov     r14d, 0FFFFh
0x18002677a  jmp     loc_180026853
0x18002677f  test    rdi, rdi
0x180026782  jz      loc_180026876
0x180026788  mov     rax, [rdi]
0x18002678b  mov     rcx, rdi
0x18002678e  mov     rax, [rax+10h]
0x180026792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026797  jmp     loc_180026876
0x18002679c  cmp     al, 3
0x18002679e  jnz     loc_180026871
0x1800267a4  mov     ecx, 98h; Size
0x1800267a9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800267ae  test    rax, rax
0x1800267b1  jz      short loc_1800267C0
0x1800267b3  mov     rcx, rax; this
0x1800267b6  call    ??0CMtfPredictionCandidate@@QEAA@XZ; CMtfPredictionCandidate::CMtfPredictionCandidate(void)
0x1800267bb  mov     r14, rax
0x1800267be  jmp     short loc_1800267C3
0x1800267c0  xor     r14d, r14d
0x1800267c3  lea     rcx, [r14+28h]
0x1800267c7  mov     rax, [rcx]
0x1800267ca  mov     rdx, r12
0x1800267cd  mov     rax, [rax+28h]
0x1800267d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800267d6  mov     ebx, eax
0x1800267d8  test    eax, eax
0x1800267da  js      short loc_18002685B
0x1800267dc  lea     rdi, [rsi+8]
0x1800267e0  test    r14, r14
0x1800267e3  jz      short loc_1800267E9
0x1800267e5  add     r14, 8
0x1800267e9  mov     [rsp+0B8h+var_60], r14
0x1800267ee  lea     rax, [rsp+0B8h+var_60]
0x1800267f3  cmp     rax, [rdi+8]
0x1800267f7  jnb     short loc_180026808
0x1800267f9  lea     rax, [rsp+0B8h+var_60]
0x1800267fe  cmp     [rdi], rax
0x180026801  ja      short loc_180026808
0x180026803  mov     al, r15b
0x180026806  jmp     short loc_18002680A
0x180026808  xor     al, al
0x18002680a  mov     rcx, [rsi+18h]
0x18002680e  test    al, al
0x180026810  jz      short loc_180026830
0x180026812  mov     r14, [rdi]
0x180026815  cmp     [rdi+8], rcx
0x180026819  jnz     short loc_180026826
0x18002681b  mov     rdx, r15
0x18002681e  mov     rcx, rdi
0x180026821  call    ?_Reserve@?$vector@PEAUIMtfSuggestionListElement@@V?$allocator@PEAUIMtfSuggestionListElement@@@std@@@std@@IEAAX_K@Z; std::vector<IMtfSuggestionListElement *>::_Reserve(unsigned __int64)
0x180026826  lea     rdx, [rsp+0B8h+var_60]
0x18002682b  jmp     loc_180026621
0x180026830  cmp     [rdi+8], rcx
0x180026834  jnz     short loc_180026841
0x180026836  mov     rdx, r15
0x180026839  mov     rcx, rdi
0x18002683c  call    ?_Reserve@?$vector@PEAUIMtfSuggestionListElement@@V?$allocator@PEAUIMtfSuggestionListElement@@@std@@@std@@IEAAX_K@Z; std::vector<IMtfSuggestionListElement *>::_Reserve(unsigned __int64)
0x180026841  mov     rax, [rdi+8]
0x180026845  mov     [rax], r14
0x180026848  mov     r14d, 0FFFFh
0x18002684e  add     qword ptr [rdi+8], 8
0x180026853  add     r13d, r15d
0x180026856  jmp     loc_180026592
0x18002685b  test    r14, r14
0x18002685e  jz      short loc_180026876
  ... truncated ...
```
