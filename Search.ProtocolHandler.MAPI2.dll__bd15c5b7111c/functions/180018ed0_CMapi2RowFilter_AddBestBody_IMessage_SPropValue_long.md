# CMapi2RowFilter::AddBestBody(IMessage *,_SPropValue *,long)

- ea: `0x180018ed0`
- end: `0x180019474`
- name: `?AddBestBody@CMapi2RowFilter@@AEAAJPEAUIMessage@@PEAU_SPropValue@@J@Z`
- size: `1444`
- prototype: `__int64 __fastcall(CMapi2RowFilter *this, struct IMessage *, struct _SPropValue *)`
- caller_count: `1`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001bfb0`

## callees

- `0x180002300`
- `0x18000b9f0`
- `0x18000e684`
- `0x18000ea18`
- `0x18000ec8c`
- `0x180011884`
- `0x18001356c`
- `0x180013f10`
- `0x180014448`
- `0x180017940`
- `0x180018ed0`
- `0x18001a660`
- `0x18001a754`
- `0x1800204dc`
- `0x180020508`
- `0x18002b0c0`
- `0x18002b784`
- `0x18003a060`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180019144`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180019144`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180018fc4`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180018fc4`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180018fee`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180018fee`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_WrapCompressedRTFStream` at `0x1800192c3`
- `ext-ms-win-mapi-mapi32-l1-1-0!__imp_WrapCompressedRTFStream` at `0x1800192c3`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMapi2RowFilter::AddBestBody(CMapi2RowFilter *this, struct IMessage *a2, struct _SPropValue *a3)
{
  char *v6; // rdi
  HRESULT Error; // esi
  int ulPropTag; // eax
  int v9; // eax
  HGLOBAL v10; // rdi
  __int64 (__fastcall *v11)(LPSTREAM, __int64 *, LPSTREAM *, CFilterMapiFps **); // rbx
  _DWORD *v12; // rdi
  __int64 v13; // rdx
  __int64 v14; // r15
  GUID v15; // xmm0
  int v16; // ebx
  CFilterMapiFps *v17; // rbx
  CUnkSList *v18; // rcx
  struct CSingleLink *Link; // rax
  LPSTREAM ppstm; // [rsp+40h] [rbp-C0h] BYREF
  CFilterMapiFps *v22; // [rsp+48h] [rbp-B8h] BYREF
  LPSTREAM UncompressedRTFStream; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v24; // [rsp+58h] [rbp-A8h] BYREF
  struct _GUID v25; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v26; // [rsp+70h] [rbp-90h] BYREF
  int v27; // [rsp+78h] [rbp-88h]
  int v28; // [rsp+7Ch] [rbp-84h]
  _BYTE v29[8]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v30; // [rsp+88h] [rbp-78h]

  ppstm = 0;
  v6 = (char *)this + 12928;
  Error = 0;
  if ( !*((_DWORD *)this + 3237) )
  {
    if ( !a3 )
      goto LABEL_16;
    ulPropTag = (unsigned __int16)a3->ulPropTag;
    if ( ulPropTag == 31 )
    {
      ((void (__fastcall *)(_QWORD, _QWORD))CLMString::operator=)(v6, (CURRENCY)a3->Value.cur.int64);
      goto LABEL_60;
    }
    if ( ulPropTag == 30 )
    {
      ((void (__fastcall *)(_QWORD, _QWORD))TLMString<4096,4096,4294967295>::TLMString<4096,4096,4294967295>)(
        v29,
        (CURRENCY)a3->Value.cur.int64);
      CLMString::operator=(v6, v30);
      TLMString<4096,4096,4294967295>::~TLMString<4096,4096,4294967295>(v29);
      goto LABEL_60;
    }
    if ( (unsigned __int16)a3->ulPropTag != 258 )
      goto LABEL_16;
    v9 = 269680898;
    if ( (a3->ulPropTag & 0xFFFF0000) != 0x10130000 )
      v9 = 269025538;
    *((_DWORD *)this + 5948) = v9;
    if ( !*((_DWORD *)this + 5949) )
      goto LABEL_16;
    v10 = GlobalAlloc(0x42u, a3->Value.ul);
    if ( v10 || (Error = ResultFromLastError(), Error >= 0) )
    {
      Error = CreateStreamOnHGlobal(v10, 1, &ppstm);
      if ( Error < 0 )
      {
        GlobalFree(v10);
        goto LABEL_60;
      }
      LODWORD(UncompressedRTFStream) = 0;
      Error = (*(__int64 (__fastcall **)(LPSTREAM, LPBYTE, _QWORD, LPSTREAM *))(*(_QWORD *)ppstm + 32LL))(
                ppstm,
                a3->Value.bin.lpb,
                a3->Value.ul,
                &UncompressedRTFStream);
      if ( Error >= 0 )
      {
        v24 = 0;
        v22 = 0;
        Error = (*(__int64 (__fastcall **)(LPSTREAM, _QWORD, _QWORD, CFilterMapiFps **))(*(_QWORD *)ppstm + 40LL))(
                  ppstm,
                  0,
                  0,
                  &v22);
        if ( Error >= 0 )
        {
LABEL_16:
          UncompressedRTFStream = 0;
          v11 = *(__int64 (__fastcall **)(LPSTREAM, __int64 *, LPSTREAM *, CFilterMapiFps **))(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 2645) + 64LL) + 208LL)
                                                                                             + 256LL);
          if ( v11 && *((_DWORD *)this + 5948) == 269025538 )
          {
            v22 = (CFilterMapiFps *)8;
            if ( !ppstm )
              Error = ((__int64 (__fastcall *)(struct IMessage *, __int64, GUID *, _QWORD, int, LPSTREAM *))a2->lpVtbl->get_BCC)(
                        a2,
                        269025538,
                        &IID_IStream,
                        0,
                        8,
                        &ppstm);
            if ( Error >= 0 )
            {
              v28 = 0;
              v26 = 0x1000000000010LL;
              v27 = *((_DWORD *)this + 5420);
              Error = v11(ppstm, &v26, &UncompressedRTFStream, &v22);
              if ( Error >= 0 )
              {
                if ( HIDWORD(v22) == 1 )
                {
                  *((_DWORD *)this + 5948) = 269025538;
                }
                else if ( HIDWORD(v22) == 2 )
                {
                  TComPointer<IFilter>::operator=(&ppstm, UncompressedRTFStream);
                  *((_DWORD *)this + 5948) = 269680898;
                }
                else
                {
                  TComPointer<IFilter>::operator=(&ppstm, 0);
                  *((_DWORD *)this + 5948) = 268435487;
                }
              }
            }
          }
          if ( ppstm )
          {
            v12 = (_DWORD *)((char *)this + 23792);
          }
          else
          {
            if ( *((_DWORD *)this + 5949) )
              goto LABEL_35;
            v12 = (_DWORD *)((char *)this + 23792);
            if ( (*((_DWORD *)this + 5948) & 0xFFFF0000) == 0x10000000 )
              goto LABEL_35;
            Error = ((__int64 (__fastcall *)(struct IMessage *, __int64, GUID *, _QWORD, _DWORD, LPSTREAM *))a2->lpVtbl->get_BCC)(
                      a2,
                      269680898,
                      &IID_IStream,
                      0,
                      0,
                      &ppstm);
            if ( Error >= 0 )
              *v12 = 269680898;
            if ( !ppstm )
            {
LABEL_35:
              v12 = (_DWORD *)((char *)this + 23792);
              Error = ((__int64 (__fastcall *)(struct IMessage *, _QWORD, GUID *, _QWORD, int, LPSTREAM *))a2->lpVtbl->get_BCC)(
                        a2,
                        *((unsigned int *)this + 5948),
                        &IID_IStream,
                        0,
                        *((_DWORD *)this + 5949) != 0 ? 8 : 0,
                        &ppstm);
            }
            if ( Error == -2147221245 )
            {
              v13 = (unsigned int)*v12;
              if ( (_WORD)v13 == 31 )
              {
                v13 = v13 & 0xFFFF0000 | 0x1E;
                *v12 = v13;
              }
              Error = ((__int64 (__fastcall *)(struct IMessage *, __int64, GUID *, _QWORD, int, LPSTREAM *))a2->lpVtbl->get_BCC)(
                        a2,
                        v13,
                        &IID_IStream,
                        0,
                        8,
                        &ppstm);
            }
          }
          if ( Error < 0 )
            goto LABEL_59;
          *((_DWORD *)this + 3237) = 0;
          **((_WORD **)this + 1617) = 0;
          ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(&v26);
          v14 = 0;
          v24 = 0;
          v25 = 0;
          if ( (*v12 & 0xFFFF0000) == 0x10090000 )
          {
            if ( !UncompressedRTFStream )
              Error = WrapCompressedRTFStream(ppstm, 0, &UncompressedRTFStream);
            v15 = GUID_e20870e2_3ad1_4b64_87be_5ad5f17a53f0;
          }
          else
          {
            if ( *v12 == 268435487 )
            {
              v22 = 0;
              Error = ATL::CComObject<CFilterUnicode>::CreateInstance(&v22);
              if ( v22 )
              {
                TComPointer<IFilter>::operator=(&v24, v22);
                v14 = v24;
                v16 = *((_DWORD *)this + 5420);
                TComPointer<IFilter>::operator=(v24 + 32, ppstm);
                *(_DWORD *)(v14 + 28) = v16;
                *(_DWORD *)(v14 + 24) = 0;
              }
              goto LABEL_52;
            }
            if ( *v12 == 268435486 )
            {
              TComPointer<IFilter>::operator=(&UncompressedRTFStream, ppstm);
              v15 = GUID_317f3aa1_a5f5_4310_9401_bae5dac386c6;
            }
            else
            {
              TComPointer<IFilter>::operator=(&UncompressedRTFStream, ppstm);
              v15 = GUID_01cbcf66_a9ca_4449_84de_7f321232bbc7;
            }
          }
          v25 = v15;
LABEL_52:
          if ( !Error )
          {
            v22 = 0;
            if ( (int)ATL::CComObject<CFilterMapiFps>::CreateInstance(&v22) >= 0 )
            {
              TComNoUnkPointer<CMapi2RowFilter>::TComNoUnkPointer<CMapi2RowFilter>(&v22, v22);
              v17 = v22;
              if ( *v12 == 268435487 )
                CFilterMapiFps::Initialize(
                  v22,
                  (struct IFilter *)v14,
                  (const struct CMapi2FullPropSpec *)g_mfpsSearch_Contents);
              else
                CFilterMapiFps::Initialize(
                  v22,
                  *(struct IProtocolHandlerSite **)(*(_QWORD *)(*((_QWORD *)this + 2645) + 64LL) + 200LL),
                  UncompressedRTFStream,
                  0,
                  &v25,
                  (const struct CMapi2FullPropSpec *)g_mfpsSearch_Contents);
              Link = CUnkSList::CreateLink(v18, (struct IUnknown *)(((unsigned __int64)v17 + 8) & -(__int64)(v17 != 0)));
              CLnkList::InsertAfter(
                (CMapi2RowFilter *)((char *)this + 23976),
                (CMapi2RowFilter *)((char *)this + 23976),
                Link);
              *((_DWORD *)this + 5288) = 1;
              TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(&v22);
            }
          }
          TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(&v24);
          ATL::CStringData::Release((ATL::CStringData *)(v26 - 24));
LABEL_59:
          TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(&UncompressedRTFStream);
        }
      }
    }
  }
LABEL_60:
  TComNoUnkPointer<CFilterMapiFps>::~TComNoUnkPointer<CFilterMapiFps>(&ppstm);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180018ed0  mov     [rsp-8+arg_18], rbx
0x180018ed5  push    rbp
0x180018ed6  push    rsi
0x180018ed7  push    rdi
0x180018ed8  push    r12
0x180018eda  push    r13
0x180018edc  push    r14
0x180018ede  push    r15
0x180018ee0  lea     rbp, [rsp-1FB0h]
0x180018ee8  mov     eax, 20B0h
0x180018eed  call    _alloca_probe
0x180018ef2  sub     rsp, rax
0x180018ef5  mov     rax, cs:__security_cookie
0x180018efc  xor     rax, rsp
0x180018eff  mov     [rbp+1FE0h+var_40], rax
0x180018f06  mov     rbx, r8
0x180018f09  mov     r15, rdx
0x180018f0c  mov     r14, rcx
0x180018f0f  xor     r12d, r12d
0x180018f12  mov     [rsp+20E0h+ppstm], r12
0x180018f17  lea     rdi, [rcx+3280h]
0x180018f1e  mov     esi, r12d
0x180018f21  cmp     [rdi+14h], r12d
0x180018f25  ja      loc_18001943E
0x180018f2b  mov     r13d, 10090102h
0x180018f31  test    rbx, rbx
0x180018f34  jz      loc_18001905B
0x180018f3a  mov     eax, [r8]
0x180018f3d  movzx   eax, ax
0x180018f40  cmp     eax, 1Fh
0x180018f43  jnz     short loc_180018F56
0x180018f45  mov     rdx, [r8+8]
0x180018f49  mov     rcx, rdi
0x180018f4c  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x180018f51  jmp     loc_18001943E
0x180018f56  cmp     eax, 1Eh
0x180018f59  jnz     short loc_180018F84
0x180018f5b  mov     rdx, [r8+8]
0x180018f5f  lea     rcx, [rbp+1FE0h+var_2060]
0x180018f63  call    ??0?$TLMString@$0BAAA@$0BAAA@$0PPPPPPPP@@@QEAA@PEBD@Z; TLMString<4096,4096,4294967295>::TLMString<4096,4096,4294967295>(char const *)
0x180018f68  nop
0x180018f69  mov     rdx, [rbp+1FE0h+var_2058]
0x180018f6d  mov     rcx, rdi
0x180018f70  call    ??4CLMString@@QEAAXPEB_W@Z; CLMString::operator=(wchar_t const *)
0x180018f75  nop
0x180018f76  lea     rcx, [rbp+1FE0h+var_2060]
0x180018f7a  call    ??1?$TLMString@$0BAAA@$0BAAA@$0PPPPPPPP@@@UEAA@XZ; TLMString<4096,4096,4294967295>::~TLMString<4096,4096,4294967295>(void)
0x180018f7f  jmp     loc_18001943E
0x180018f84  mov     ecx, [r8]
0x180018f87  cmp     cx, 102h
0x180018f8c  jnz     loc_18001905B
0x180018f92  and     ecx, 0FFFF0000h
0x180018f98  mov     eax, 10130102h
0x180018f9d  cmp     ecx, 10130000h
0x180018fa3  cmovnz  eax, r13d
0x180018fa7  mov     [r14+5CF0h], eax
0x180018fae  cmp     [r14+5CF4h], r12d
0x180018fb5  jz      loc_18001905B
0x180018fbb  mov     edx, [r8+8]; dwBytes
0x180018fbf  mov     ecx, 42h ; 'B'; uFlags
0x180018fc4  call    cs:__imp_GlobalAlloc
0x180018fca  mov     rdi, rax
0x180018fcd  test    rax, rax
0x180018fd0  jnz     short loc_180018FE1
0x180018fd2  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x180018fd7  mov     esi, eax
0x180018fd9  test    eax, eax
0x180018fdb  js      loc_18001943E
0x180018fe1  lea     r8, [rsp+20E0h+ppstm]; ppstm
0x180018fe6  mov     edx, 1; fDeleteOnRelease
0x180018feb  mov     rcx, rdi; hGlobal
0x180018fee  call    cs:__imp_CreateStreamOnHGlobal
0x180018ff4  mov     esi, eax
0x180018ff6  test    eax, eax
0x180018ff8  js      loc_180019141
0x180018ffe  mov     dword ptr [rsp+20E0h+UncompressedRTFStream], r12d
0x180019003  mov     rcx, [rsp+20E0h+ppstm]
0x180019008  mov     rax, [rcx]
0x18001900b  lea     r9, [rsp+20E0h+UncompressedRTFStream]
0x180019010  mov     r8d, [rbx+8]
0x180019014  mov     rdx, [rbx+10h]
0x180019018  mov     rax, [rax+20h]
0x18001901c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019021  mov     esi, eax
0x180019023  test    eax, eax
0x180019025  js      loc_18001943E
0x18001902b  mov     [rsp+20E0h+var_2088], r12
0x180019030  mov     [rsp+20E0h+var_2098], r12
0x180019035  mov     rcx, [rsp+20E0h+ppstm]
0x18001903a  mov     rax, [rcx]
0x18001903d  lea     r9, [rsp+20E0h+var_2098]
0x180019042  xor     r8d, r8d
0x180019045  mov     rdx, r12
0x180019048  mov     rax, [rax+28h]
0x18001904c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019051  mov     esi, eax
0x180019053  test    eax, eax
0x180019055  js      loc_18001943E
0x18001905b  mov     [rsp+20E0h+UncompressedRTFStream], r12
0x180019060  mov     rax, [r14+52A8h]
0x180019067  mov     rcx, [rax+40h]
0x18001906b  mov     rax, [rcx+0D0h]
0x180019072  mov     rbx, [rax+100h]
0x180019079  mov     edx, 8
0x18001907e  test    rbx, rbx
0x180019081  jz      loc_18001916D
0x180019087  cmp     [r14+5CF0h], r13d
0x18001908e  jnz     loc_18001916D
0x180019094  mov     [rsp+20E0h+var_2098], r12
0x180019099  mov     dword ptr [rsp+20E0h+var_2098], edx
0x18001909d  cmp     [rsp+20E0h+ppstm], r12
0x1800190a2  jnz     short loc_1800190D0
0x1800190a4  mov     rax, [r15]
0x1800190a7  lea     rcx, [rsp+20E0h+ppstm]
0x1800190ac  mov     [rsp+20E0h+var_20B8], rcx
0x1800190b1  mov     dword ptr [rsp+20E0h+var_20C0], edx
0x1800190b5  xor     r9d, r9d
0x1800190b8  lea     r8, IID_IStream
0x1800190bf  mov     edx, r13d
0x1800190c2  mov     rcx, r15
0x1800190c5  mov     rax, [rax+38h]
0x1800190c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800190ce  mov     esi, eax
0x1800190d0  test    esi, esi
0x1800190d2  js      loc_18001916D
0x1800190d8  mov     [rsp+20E0h+var_2064], r12d
0x1800190dd  mov     dword ptr [rsp+20E0h+var_2070], 10h
0x1800190e5  mov     dword ptr [rsp+20E0h+var_2070+4], 10000h
0x1800190ed  mov     ecx, [r14+54B0h]
0x1800190f4  mov     [rsp+20E0h+var_2068], ecx
0x1800190f8  lea     r9, [rsp+20E0h+var_2098]
0x1800190fd  lea     r8, [rsp+20E0h+UncompressedRTFStream]
0x180019102  lea     rdx, [rsp+20E0h+var_2070]
0x180019107  mov     rcx, [rsp+20E0h+ppstm]
0x18001910c  mov     rax, rbx
0x18001910f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019114  mov     esi, eax
0x180019116  test    eax, eax
0x180019118  js      short loc_18001916D
0x18001911a  mov     eax, dword ptr [rsp+20E0h+var_2098+4]
0x18001911e  sub     eax, 1
0x180019121  jz      short loc_180019166
0x180019123  lea     rcx, [rsp+20E0h+ppstm]
0x180019128  cmp     eax, 1
0x18001912b  jz      short loc_18001914F
0x18001912d  xor     edx, edx
0x18001912f  call    ??4?$TComPointer@UIFilter@@@@QEAAPEAUIFilter@@PEAU1@@Z; TComPointer<IFilter>::operator=(IFilter *)
0x180019134  mov     dword ptr [r14+5CF0h], 1000001Fh
0x18001913f  jmp     short loc_18001916D
0x180019141  mov     rcx, rdi; hMem
0x180019144  call    cs:__imp_GlobalFree
0x18001914a  jmp     loc_18001943E
0x18001914f  mov     rdx, [rsp+20E0h+UncompressedRTFStream]
0x180019154  call    ??4?$TComPointer@UIFilter@@@@QEAAPEAUIFilter@@PEAU1@@Z; TComPointer<IFilter>::operator=(IFilter *)
0x180019159  mov     dword ptr [r14+5CF0h], 10130102h
0x180019164  jmp     short loc_18001916D
0x180019166  mov     [r14+5CF0h], r13d
0x18001916d  cmp     [rsp+20E0h+ppstm], r12
0x180019172  jz      short loc_180019180
0x180019174  lea     rdi, [r14+5CF0h]
0x18001917b  jmp     loc_180019266
0x180019180  cmp     [r14+5CF4h], r12d
0x180019187  jnz     short loc_1800191DE
0x180019189  lea     rdi, [r14+5CF0h]
0x180019190  mov     eax, [rdi]
0x180019192  and     eax, 0FFFF0000h
0x180019197  cmp     eax, 10000000h
0x18001919c  jz      short loc_1800191DE
0x18001919e  mov     rax, [r15]
0x1800191a1  lea     rcx, [rsp+20E0h+ppstm]
0x1800191a6  mov     [rsp+20E0h+var_20B8], rcx
0x1800191ab  mov     dword ptr [rsp+20E0h+var_20C0], r12d
0x1800191b0  xor     r9d, r9d
0x1800191b3  lea     r8, IID_IStream
0x1800191ba  mov     edx, 10130102h
0x1800191bf  mov     rcx, r15
0x1800191c2  mov     rax, [rax+38h]
0x1800191c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191cb  mov     esi, eax
0x1800191cd  test    eax, eax
0x1800191cf  js      short loc_1800191D7
0x1800191d1  mov     dword ptr [rdi], 10130102h
0x1800191d7  cmp     [rsp+20E0h+ppstm], r12
0x1800191dc  jnz     short loc_18001921E
0x1800191de  lea     rdi, [r14+5CF0h]
0x1800191e5  mov     rcx, [r15]
0x1800191e8  mov     eax, [r14+5CF4h]
0x1800191ef  neg     eax
0x1800191f1  sbb     edx, edx
0x1800191f3  and     edx, 8
0x1800191f6  mov     rax, [rcx+38h]
0x1800191fa  lea     rcx, [rsp+20E0h+ppstm]
0x1800191ff  mov     [rsp+20E0h+var_20B8], rcx
0x180019204  mov     dword ptr [rsp+20E0h+var_20C0], edx
0x180019208  xor     r9d, r9d
0x18001920b  lea     r8, IID_IStream
0x180019212  mov     edx, [rdi]
0x180019214  mov     rcx, r15
0x180019217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001921c  mov     esi, eax
0x18001921e  cmp     esi, 80040103h
0x180019224  jnz     short loc_180019266
0x180019226  mov     edx, [rdi]
0x180019228  cmp     dx, 1Fh
0x18001922c  jnz     short loc_180019239
0x18001922e  and     edx, 0FFFF001Eh
0x180019234  or      edx, 1Eh
0x180019237  mov     [rdi], edx
0x180019239  mov     rax, [r15]
0x18001923c  lea     rcx, [rsp+20E0h+ppstm]
0x180019241  mov     [rsp+20E0h+var_20B8], rcx
0x180019246  mov     dword ptr [rsp+20E0h+var_20C0], 8
0x18001924e  xor     r9d, r9d
0x180019251  lea     r8, IID_IStream
0x180019258  mov     rcx, r15
0x18001925b  mov     rax, [rax+38h]
0x18001925f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019264  mov     esi, eax
0x180019266  test    esi, esi
0x180019268  js      loc_180019433
0x18001926e  mov     [r14+3294h], r12d
0x180019275  mov     rcx, [r14+3288h]
0x18001927c  mov     [rcx], r12w
0x180019280  lea     rdx, dword_1800444C4
0x180019287  lea     rcx, [rsp+20E0h+var_2070]
0x18001928c  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@PEB_W@Z; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(wchar_t const *)
0x180019291  nop
0x180019292  mov     r15, r12
0x180019295  mov     [rsp+20E0h+var_2088], r12
0x18001929a  xorps   xmm0, xmm0
0x18001929d  movups  xmmword ptr [rsp+20E0h+var_2080.Data1], xmm0
0x1800192a2  mov     eax, [rdi]
0x1800192a4  and     eax, 0FFFF0000h
0x1800192a9  cmp     eax, 10090000h
0x1800192ae  jnz     short loc_1800192D4
0x1800192b0  cmp     [rsp+20E0h+UncompressedRTFStream], r12
0x1800192b5  jnz     short loc_1800192CB
0x1800192b7  lea     r8, [rsp+20E0h+UncompressedRTFStream]; lpUncompressedRTFStream
0x1800192bc  xor     edx, edx; ulFlags
0x1800192be  mov     rcx, [rsp+20E0h+ppstm]; lpCompressedRTFStream
0x1800192c3  call    cs:__imp_WrapCompressedRTFStream
0x1800192c9  mov     esi, eax
0x1800192cb  movups  xmm0, xmmword ptr cs:_GUID_e20870e2_3ad1_4b64_87be_5ad5f17a53f0.Data1
0x1800192d2  jmp     short loc_180019351
0x1800192d4  cmp     dword ptr [rdi], 1000001Fh
0x1800192da  jnz     short loc_180019325
0x1800192dc  mov     [rsp+20E0h+var_2098], r12
0x1800192e1  lea     rcx, [rsp+20E0h+var_2098]
0x1800192e6  call    ?CreateInstance@?$CComObject@VCFilterUnicode@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CFilterUnicode>::CreateInstance(ATL::CComObject<CFilterUnicode> * *)
0x1800192eb  mov     esi, eax
0x1800192ed  mov     rdx, [rsp+20E0h+var_2098]
0x1800192f2  test    rdx, rdx
0x1800192f5  jz      short loc_180019357
0x1800192f7  lea     rcx, [rsp+20E0h+var_2088]
0x1800192fc  call    ??4?$TComPointer@UIFilter@@@@QEAAPEAUIFilter@@PEAU1@@Z; TComPointer<IFilter>::operator=(IFilter *)
0x180019301  mov     r15, [rsp+20E0h+var_2088]
0x180019306  mov     ebx, [r14+54B0h]
0x18001930d  lea     rcx, [r15+20h]
0x180019311  mov     rdx, [rsp+20E0h+ppstm]
0x180019316  call    ??4?$TComPointer@UIFilter@@@@QEAAPEAUIFilter@@PEAU1@@Z; TComPointer<IFilter>::operator=(IFilter *)
0x18001931b  mov     [r15+1Ch], ebx
0x18001931f  mov     [r15+18h], r12d
0x180019323  jmp     short loc_180019357
0x180019325  mov     rdx, [rsp+20E0h+ppstm]
0x18001932a  lea     rcx, [rsp+20E0h+UncompressedRTFStream]
0x18001932f  cmp     dword ptr [rdi], 1000001Eh
0x180019335  jnz     short loc_180019345
0x180019337  call    ??4?$TComPointer@UIFilter@@@@QEAAPEAUIFilter@@PEAU1@@Z; TComPointer<IFilter>::operator=(IFilter *)
0x18001933c  movups  xmm0, xmmword ptr cs:_GUID_317f3aa1_a5f5_4310_9401_bae5dac386c6.Data1
0x180019343  jmp     short loc_180019351
0x180019345  call    ??4?$TComPointer@UIFilter@@@@QEAAPEAUIFilter@@PEAU1@@Z; TComPointer<IFilter>::operator=(IFilter *)
0x18001934a  movups  xmm0, xmmword ptr cs:_GUID_01cbcf66_a9ca_4449_84de_7f321232bbc7.Data1
0x180019351  movdqu  xmmword ptr [rsp+20E0h+var_2080.Data1], xmm0
0x180019357  test    esi, esi
0x180019359  jnz     loc_180019419
0x18001935f  mov     [rsp+20E0h+var_2098], r12
0x180019364  lea     rcx, [rsp+20E0h+var_2098]
0x180019369  call    ?CreateInstance@?$CComObject@VCFilterMapiFps@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CFilterMapiFps>::CreateInstance(ATL::CComObject<CFilterMapiFps> * *)
0x18001936e  test    eax, eax
0x180019370  js      loc_180019419
0x180019376  mov     rdx, [rsp+20E0h+var_2098]
0x18001937b  lea     rcx, [rsp+20E0h+var_2098]
0x180019380  call    ??0?$TComNoUnkPointer@VCMapi2RowFilter@@@@QEAA@PEAVCMapi2RowFilter@@@Z; TComNoUnkPointer<CMapi2RowFilter>::TComNoUnkPointer<CMapi2RowFilter>(CMapi2RowFilter *)
0x180019385  nop
0x180019386  mov     rbx, [rsp+20E0h+var_2098]
0x18001938b  mov     rcx, rbx; this
0x18001938e  cmp     dword ptr [rdi], 1000001Fh
0x180019394  jnz     short loc_1800193A7
0x180019396  lea     r8, ?g_mfpsSearch_Contents@@3VCMapi2FullPropSpec@@B; struct CMapi2FullPropSpec *
0x18001939d  mov     rdx, r15; struct IFilter *
0x1800193a0  call    ?Initialize@CFilterMapiFps@@QEAAXPEAUIFilter@@PEBVCMapi2FullPropSpec@@@Z; CFilterMapiFps::Initialize(IFilter *,CMapi2FullPropSpec const *)
0x1800193a5  jmp     short loc_1800193DC
0x1800193a7  mov     rax, [r14+52A8h]
0x1800193ae  mov     rdx, [rax+40h]
0x1800193b2  lea     rax, ?g_mfpsSearch_Contents@@3VCMapi2FullPropSpec@@B; CMapi2FullPropSpec const g_mfpsSearch_Contents
0x1800193b9  mov     [rsp+20E0h+var_20B8], rax; struct CMapi2FullPropSpec *
0x1800193be  lea     rax, [rsp+20E0h+var_2080]
0x1800193c3  mov     [rsp+20E0h+var_20C0], rax; struct _GUID *
0x1800193c8  xor     r9d, r9d; wchar_t *
0x1800193cb  mov     r8, [rsp+20E0h+UncompressedRTFStream]; struct IStream *
  ... truncated ...
```
