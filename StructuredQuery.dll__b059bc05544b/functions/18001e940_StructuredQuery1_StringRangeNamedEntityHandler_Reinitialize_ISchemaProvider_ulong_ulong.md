# StructuredQuery1::StringRangeNamedEntityHandler::Reinitialize(ISchemaProvider *,ulong,ulong)

- ea: `0x18001e940`
- end: `0x18001ebbb`
- name: `?Reinitialize@StringRangeNamedEntityHandler@StructuredQuery1@@UEAAJPEAUISchemaProvider@@KK@Z`
- size: `635`
- prototype: `__int64 __fastcall(StructuredQuery1::StringRangeNamedEntityHandler *__hidden this, struct ISchemaProvider *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18001b2b4`
- `0x18001cf9c`
- `0x18001e940`
- `0x18001ebc4`
- `0x180020250`
- `0x1800204a4`
- `0x180020540`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eb88`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eb88`
- `PROPSYS!PSGetPropertyDescription` at `0x18001e9ca`
- `PROPSYS!PSGetPropertyDescription` at `0x18001e9ca`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall StructuredQuery1::StringRangeNamedEntityHandler::Reinitialize(
        StructuredQuery1::StringRangeNamedEntityHandler *this,
        struct ISchemaProvider *a2,
        wchar_t **a3)
{
  unsigned int v3; // r12d
  unsigned int *v5; // rsi
  void **v6; // r14
  __int64 v7; // rcx
  int SharedLanguageResourcePool; // ebx
  unsigned __int64 v10; // rcx
  unsigned int i; // edi
  __int64 v12; // [rsp+40h] [rbp-29h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-21h] BYREF
  __int64 v14; // [rsp+50h] [rbp-19h] BYREF
  void *ppv; // [rsp+58h] [rbp-11h] BYREF
  struct ILanguageResourcePool *v16; // [rsp+60h] [rbp-9h] BYREF
  wchar_t v17[4]; // [rsp+68h] [rbp-1h] BYREF
  _QWORD v18[10]; // [rsp+70h] [rbp+7h] BYREF
  __int64 v19; // [rsp+D0h] [rbp+67h] BYREF

  v3 = (unsigned int)a3;
  *((_DWORD *)this + 6) = 0;
  v5 = (unsigned int *)((char *)this + 28);
  v6 = (void **)((char *)this + 32);
  StructuredQuery1::ClearRangeInfoArray((StructuredQuery1 *)*((unsigned int *)this + 7), *((_QWORD **)this + 4), a3);
  *v5 = 0;
  *v6 = 0;
  v16 = 0;
  SharedLanguageResourcePool = GetSharedLanguageResourcePool(v7, &v16);
  if ( SharedLanguageResourcePool >= 0 )
  {
    *(_DWORD *)v17 = v3;
    v18[0] = 0;
    SharedLanguageResourcePool = StructuredQuery1::Tokenizer::Initialize((StructuredQuery1::Tokenizer *)v17, v16);
    if ( SharedLanguageResourcePool >= 0 )
    {
      ppv = 0;
      SharedLanguageResourcePool = PSGetPropertyDescription(
                                     &PKEY_ItemNameDisplay,
                                     &GUID_d1b46fc1_89ed_4e23_a8c5_31cb35cd5001,
                                     &ppv);
      if ( SharedLanguageResourcePool >= 0 )
      {
        v19 = 0;
        SharedLanguageResourcePool = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD, _QWORD, GUID *, __int64 *))(*(_QWORD *)ppv + 32LL))(
                                       ppv,
                                       v3,
                                       0,
                                       0,
                                       &GUID_a99400f4_3d84_4557_94ba_1242fb2cc9a6,
                                       &v19);
        if ( SharedLanguageResourcePool >= 0 )
        {
          SharedLanguageResourcePool = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v19 + 24LL))(
                                         v19,
                                         v5);
          if ( SharedLanguageResourcePool >= 0 )
          {
            v10 = *v5;
            *v6 = 0;
            v14 = 0;
            if ( is_mul_ok(v10, 0x18u) )
            {
              SharedLanguageResourcePool = CTCoAllocPolicy::Alloc((IMalloc *)v10, 1, 24 * v10, v6);
              for ( i = 0; SharedLanguageResourcePool >= 0; ++i )
              {
                if ( i >= *v5 )
                  break;
                v14 = 0;
                SharedLanguageResourcePool = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v19 + 32LL))(
                                               v19,
                                               i,
                                               &GUID_11e1fbf9_2d56_4a6b_8db3_7cd193a471f2,
                                               &v14);
                if ( SharedLanguageResourcePool >= 0 )
                {
                  pv = 0;
                  SharedLanguageResourcePool = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v14 + 56LL))(
                                                 v14,
                                                 &pv);
                  if ( SharedLanguageResourcePool >= 0 )
                  {
                    SharedLanguageResourcePool = StructuredQuery1::ParseKeywords(
                                                   (wchar_t *)pv,
                                                   v17,
                                                   (struct StructuredQuery1::Tokenizer *)((char *)*v6 + 24 * i + 8),
                                                   (wchar_t ***)*v6 + 3 * i);
                    if ( SharedLanguageResourcePool >= 0 )
                    {
                      v12 = 0;
                      SharedLanguageResourcePool = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v19 + 40LL))(
                                                     v19,
                                                     i,
                                                     &GUID_fca2857d_1760_4ad3_8c63_c9b602fcbaea,
                                                     &v12);
                      if ( SharedLanguageResourcePool >= 0 )
                      {
                        SharedLanguageResourcePool = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 88LL))(
                                                       v12,
                                                       (__int64)*v6 + 24 * i + 16);
                        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
                      }
                    }
                    CoTaskMemFree(pv);
                  }
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
                }
              }
            }
            else
            {
              SharedLanguageResourcePool = -2147024362;
            }
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        }
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
      }
      *((_DWORD *)this + 6) = v3;
    }
    (*(void (__fastcall **)(struct ILanguageResourcePool *))(*(_QWORD *)v16 + 16LL))(v16);
    IUnknown_SafeReleaseAndNullPtr<GrowableBuffer<tagHITRANGE>>(v18);
  }
  return (unsigned int)SharedLanguageResourcePool;
}

```

## disassembly

```asm
0x18001e940  push    rbp
0x18001e942  push    rbx
0x18001e943  push    rsi
0x18001e944  push    rdi
0x18001e945  push    r12
0x18001e947  push    r13
0x18001e949  push    r14
0x18001e94b  push    r15
0x18001e94d  lea     rbp, [rsp-1Fh]
0x18001e952  sub     rsp, 88h
0x18001e959  mov     r12d, r8d
0x18001e95c  mov     r15, rcx
0x18001e95f  xor     r13d, r13d
0x18001e962  mov     [rcx+18h], r13d
0x18001e966  lea     rsi, [rcx+1Ch]
0x18001e96a  lea     r14, [rcx+20h]
0x18001e96e  mov     rdx, [r14]; unsigned int
0x18001e971  mov     ecx, [rsi]; this
0x18001e973  call    ?ClearRangeInfoArray@StructuredQuery1@@YAXIPEAURANGE_INFO@1@@Z; StructuredQuery1::ClearRangeInfoArray(uint,StructuredQuery1::RANGE_INFO *)
0x18001e978  mov     [rsi], r13d
0x18001e97b  mov     [r14], r13
0x18001e97e  mov     [rbp+57h+var_60], r13
0x18001e982  lea     rdx, [rbp+57h+var_60]
0x18001e986  call    GetSharedLanguageResourcePool
0x18001e98b  mov     ebx, eax
0x18001e98d  test    eax, eax
0x18001e98f  js      loc_18001EA66
0x18001e995  mov     dword ptr [rbp+57h+var_58], r12d
0x18001e999  mov     [rbp+57h+var_50], r13
0x18001e99d  mov     rdx, [rbp+57h+var_60]; struct ILanguageResourcePool *
0x18001e9a1  lea     rcx, [rbp+57h+var_58]; this
0x18001e9a5  call    ?Initialize@Tokenizer@StructuredQuery1@@QEAAJPEAUILanguageResourcePool@@@Z; StructuredQuery1::Tokenizer::Initialize(ILanguageResourcePool *)
0x18001e9aa  mov     ebx, eax
0x18001e9ac  test    eax, eax
0x18001e9ae  js      loc_18001EA4B
0x18001e9b4  mov     [rbp+57h+ppv], r13
0x18001e9b8  lea     r8, [rbp+57h+ppv]; ppv
0x18001e9bc  lea     rdx, _GUID_d1b46fc1_89ed_4e23_a8c5_31cb35cd5001; riid
0x18001e9c3  lea     rcx, PKEY_ItemNameDisplay; propkey
0x18001e9ca  call    cs:__imp_PSGetPropertyDescription
0x18001e9d0  mov     ebx, eax
0x18001e9d2  test    eax, eax
0x18001e9d4  js      short loc_18001EA47
0x18001e9d6  mov     [rbp+57h+arg_0], r13
0x18001e9da  mov     rcx, [rbp+57h+ppv]
0x18001e9de  mov     rax, [rcx]
0x18001e9e1  lea     rdx, [rbp+57h+arg_0]
0x18001e9e5  mov     [rsp+0C0h+var_98], rdx
0x18001e9ea  lea     rdx, _GUID_a99400f4_3d84_4557_94ba_1242fb2cc9a6
0x18001e9f1  mov     [rsp+0C0h+var_A0], rdx; unsigned int *
0x18001e9f6  xor     r9d, r9d
0x18001e9f9  xor     r8d, r8d
0x18001e9fc  mov     edx, r12d
0x18001e9ff  mov     rax, [rax+20h]
0x18001ea03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea08  mov     ebx, eax
0x18001ea0a  test    eax, eax
0x18001ea0c  js      short loc_18001EA37
0x18001ea0e  mov     rcx, [rbp+57h+arg_0]
0x18001ea12  mov     rax, [rcx]
0x18001ea15  mov     rdx, rsi
0x18001ea18  mov     rax, [rax+18h]
0x18001ea1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea21  mov     ebx, eax
0x18001ea23  test    eax, eax
0x18001ea25  jns     short loc_18001EA7C
0x18001ea27  mov     rcx, [rbp+57h+arg_0]
0x18001ea2b  mov     rax, [rcx]
0x18001ea2e  mov     rax, [rax+10h]
0x18001ea32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea37  mov     rcx, [rbp+57h+ppv]
0x18001ea3b  mov     rax, [rcx]
0x18001ea3e  mov     rax, [rax+10h]
0x18001ea42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea47  mov     [r15+18h], r12d
0x18001ea4b  mov     rcx, [rbp+57h+var_60]
0x18001ea4f  mov     rax, [rcx]
0x18001ea52  mov     rax, [rax+10h]
0x18001ea56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea5b  nop
0x18001ea5c  lea     rcx, [rbp+57h+var_50]
0x18001ea60  call    ??$IUnknown_SafeReleaseAndNullPtr@V?$GrowableBuffer@UtagHITRANGE@@@@@@YAXAEAPEAV?$GrowableBuffer@UtagHITRANGE@@@@@Z; IUnknown_SafeReleaseAndNullPtr<GrowableBuffer<tagHITRANGE>>(GrowableBuffer<tagHITRANGE> * &)
0x18001ea65  nop
0x18001ea66  mov     eax, ebx
0x18001ea68  add     rsp, 88h
0x18001ea6f  pop     r15
0x18001ea71  pop     r14
0x18001ea73  pop     r13
0x18001ea75  pop     r12
0x18001ea77  pop     rdi
0x18001ea78  pop     rsi
0x18001ea79  pop     rbx
0x18001ea7a  pop     rbp
0x18001ea7b  retn
0x18001ea7c  mov     ecx, [rsi]; void *
0x18001ea7e  mov     [r14], r13
0x18001ea81  mov     [rbp+57h+var_70], r13
0x18001ea85  mov     eax, 18h
0x18001ea8a  mul     rcx
0x18001ea8d  test    rdx, rdx
0x18001ea90  jnz     loc_18001EBB0
0x18001ea96  mov     r9, r14; void **
0x18001ea99  mov     r8, rax; unsigned __int64
0x18001ea9c  mov     edx, 1; unsigned int
0x18001eaa1  call    ?Alloc@CTCoAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTCoAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18001eaa6  mov     ebx, eax
0x18001eaa8  mov     edi, r13d
0x18001eaab  test    eax, eax
0x18001eaad  js      loc_18001EA27
0x18001eab3  cmp     edi, [rsi]
0x18001eab5  jnb     loc_18001EA27
0x18001eabb  mov     [rbp+57h+var_70], r13
0x18001eabf  mov     rcx, [rbp+57h+arg_0]
0x18001eac3  mov     rax, [rcx]
0x18001eac6  lea     r9, [rbp+57h+var_70]
0x18001eaca  lea     r8, _GUID_11e1fbf9_2d56_4a6b_8db3_7cd193a471f2
0x18001ead1  mov     edx, edi
0x18001ead3  mov     rax, [rax+20h]
0x18001ead7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eadc  mov     ebx, eax
0x18001eade  test    eax, eax
0x18001eae0  js      loc_18001EBA1
0x18001eae6  mov     [rbp+57h+pv], r13
0x18001eaea  mov     rcx, [rbp+57h+var_70]
0x18001eaee  mov     rax, [rcx]
0x18001eaf1  lea     rdx, [rbp+57h+pv]
0x18001eaf5  mov     rax, [rax+38h]
0x18001eaf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eafe  mov     ebx, eax
0x18001eb00  test    eax, eax
0x18001eb02  js      loc_18001EB91
0x18001eb08  mov     eax, edi
0x18001eb0a  lea     r13, [rax+rax*2]
0x18001eb0e  mov     rax, [r14]
0x18001eb11  lea     r9, [rax+r13*8]; wchar_t ***
0x18001eb15  lea     r8, [r9+8]; struct StructuredQuery1::Tokenizer *
0x18001eb19  lea     rdx, [rbp+57h+var_58]; wchar_t *
0x18001eb1d  mov     rcx, [rbp+57h+pv]; this
0x18001eb21  call    ?ParseKeywords@StructuredQuery1@@YAJPEB_WPEAVTokenizer@1@PEAPEAPEA_WPEAK@Z; StructuredQuery1::ParseKeywords(wchar_t const *,StructuredQuery1::Tokenizer *,wchar_t * * *,ulong *)
0x18001eb26  mov     ebx, eax
0x18001eb28  test    eax, eax
0x18001eb2a  js      short loc_18001EB84
0x18001eb2c  mov     [rbp+57h+var_80], 0
0x18001eb34  mov     rcx, [rbp+57h+arg_0]
0x18001eb38  mov     rax, [rcx]
0x18001eb3b  lea     r9, [rbp+57h+var_80]
0x18001eb3f  lea     r8, _GUID_fca2857d_1760_4ad3_8c63_c9b602fcbaea
0x18001eb46  mov     edx, edi
0x18001eb48  mov     rax, [rax+28h]
0x18001eb4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb51  mov     ebx, eax
0x18001eb53  test    eax, eax
0x18001eb55  js      short loc_18001EB84
0x18001eb57  mov     rcx, [rbp+57h+var_80]
0x18001eb5b  mov     r8, [rcx]
0x18001eb5e  mov     rdx, [r14]
0x18001eb61  add     rdx, 10h
0x18001eb65  lea     rdx, [rdx+r13*8]
0x18001eb69  mov     rax, [r8+58h]
0x18001eb6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb72  mov     ebx, eax
0x18001eb74  mov     rcx, [rbp+57h+var_80]
0x18001eb78  mov     rax, [rcx]
0x18001eb7b  mov     rax, [rax+10h]
0x18001eb7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb84  mov     rcx, [rbp+57h+pv]; pv
0x18001eb88  call    cs:__imp_CoTaskMemFree
0x18001eb8e  xor     r13d, r13d
0x18001eb91  mov     rcx, [rbp+57h+var_70]
0x18001eb95  mov     rax, [rcx]
0x18001eb98  mov     rax, [rax+10h]
0x18001eb9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eba1  inc     edi
0x18001eba3  test    ebx, ebx
0x18001eba5  jns     loc_18001EAB3
0x18001ebab  jmp     loc_18001EA27
0x18001ebb0  mov     ebx, 80070216h
0x18001ebb5  jmp     loc_18001EA27
```
