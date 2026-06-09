# Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CreateMetadataEvent(_EVENT_TRACE const *,_GUID const &,_EVENT_DESCRIPTOR const &)

- ea: `0x18001c584`
- end: `0x18001c9c0`
- name: `?CreateMetadataEvent@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEBU_EVENT_TRACE@@AEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@@Z`
- size: `1084`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *__hidden this, const struct _EVENT_TRACE *, const struct _GUID *, const struct _EVENT_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18001da60`

## callees

- `0x180001870`
- `0x1800023d8`
- `0x1800023e4`
- `0x180002420`
- `0x18000b398`
- `0x18000b534`
- `0x1800163cc`
- `0x18001ad84`
- `0x18001bb1c`
- `0x18001c584`
- `0x18001f11c`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CreateMetadataEvent(
        Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *this,
        const struct _EVENT_TRACE *a2,
        const struct _GUID *a3,
        const struct _EVENT_DESCRIPTOR *a4)
{
  const struct _GUID *v5; // rbx
  __int64 (__fastcall *v8)(__int16 *, _QWORD, _QWORD, _QWORD, size_t *); // rax
  int v9; // eax
  __int64 (__fastcall *v10)(__int16 *, _QWORD, _QWORD, _QWORD, size_t *); // rax
  unsigned int v11; // ebx
  void *v12; // rcx
  void *v13; // rax
  __int64 (__fastcall *v14)(__int16 *, _QWORD, _QWORD, _QWORD, size_t *); // rax
  __int64 result; // rax
  __int64 v16; // rcx
  ULONGLONG Keyword; // rax
  __int64 v18; // rcx
  unsigned int v19; // r14d
  __int64 v20; // rax
  __int64 v21; // r15
  __int64 v22; // rbx
  __int64 v23; // r8
  char v24; // bl
  unsigned int v25; // ecx
  unsigned int v26; // r12d
  __int64 (__fastcall *v27)(__int16 *, __int64, __int64, __int64 *); // rax
  int v28; // eax
  unsigned int v29; // ebx
  void *v30; // rcx
  void *v31; // rax
  __int64 (__fastcall *v32)(__int16 *, __int64, __int64, __int64 *); // rax
  size_t Size; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v34; // [rsp+38h] [rbp-C8h] BYREF
  const struct _GUID *v35; // [rsp+40h] [rbp-C0h]
  _BYTE v36[24]; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v37; // [rsp+60h] [rbp-A0h] BYREF
  __m256i v38; // [rsp+70h] [rbp-90h]
  __int128 v39; // [rsp+90h] [rbp-70h]
  __int128 v40; // [rsp+A0h] [rbp-60h]
  __int64 v41; // [rsp+B0h] [rbp-50h]
  _OWORD v42[2]; // [rsp+C0h] [rbp-40h] BYREF
  __int16 v43; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v44[22]; // [rsp+E2h] [rbp-1Eh] BYREF
  struct _GUID v45; // [rsp+F8h] [rbp-8h]
  struct _EVENT_DESCRIPTOR v46; // [rsp+108h] [rbp+8h]

  v5 = a3;
  v35 = a3;
  memset_0(v44, 0, 0x6Eu);
  v43 = 112;
  v45 = *v5;
  v46 = *a4;
  LODWORD(Size) = *((_DWORD *)this + 16);
  v8 = (__int64 (__fastcall *)(__int16 *, _QWORD, _QWORD, _QWORD, size_t *))Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((char *)this + 288);
  v9 = v8(&v43, 0, 0, *((_QWORD *)this + 7), &Size);
  if ( v9 == 1168 )
  {
    v46.Keyword = 0;
    v10 = (__int64 (__fastcall *)(__int16 *, _QWORD, _QWORD, _QWORD, size_t *))Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((char *)this + 288);
    v9 = v10(&v43, 0, 0, *((_QWORD *)this + 7), &Size);
  }
  if ( v9 == 122 )
  {
    v11 = Size;
    if ( (unsigned int)Size <= *((_DWORD *)this + 16) )
      return 1;
    v12 = (void *)*((_QWORD *)this + 7);
    if ( v12 )
    {
      free(v12);
      v11 = Size;
    }
    v13 = o_malloc_0(v11);
    *((_QWORD *)this + 7) = v13;
    if ( !v13 )
      return 2147942414LL;
    *((_DWORD *)this + 16) = v11;
    v14 = (__int64 (__fastcall *)(__int16 *, _QWORD, _QWORD, _QWORD, size_t *))Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((char *)this + 288);
    v9 = v14(&v43, 0, 0, *((_QWORD *)this + 7), &Size);
    v5 = v35;
  }
  if ( v9 )
    return 1;
  v16 = *((_QWORD *)this + 7);
  if ( !*(_QWORD *)(v16 + 40) )
  {
    Keyword = a4->Keyword;
    if ( Keyword )
      *(_QWORD *)(v16 + 40) = Keyword;
  }
  v34 = *((_QWORD *)this + 7);
  Microsoft::Windows::Performance::CTraceEventInfoTransformImpl<Microsoft::Windows::Performance::CTraceEventInfoDelocalizer>::Transform(
    (_DWORD)this + 88,
    v34,
    Size,
    (unsigned int)&v34,
    (__int64)&Size);
  v37 = *(_OWORD *)&a2->Header.Size;
  v38 = *(__m256i *)&a2->Header.TimeStamp.LowPart;
  v39 = *(_OWORD *)&a2->InstanceId;
  v40 = *(_OWORD *)a2->ParentGuid.Data4;
  HIDWORD(v41) = HIDWORD(*(_QWORD *)&a2->MofLength);
  *(_OWORD *)&v38.m256i_u64[1] = EventMetadataGuid;
  DWORD1(v37) = 32;
  *((_QWORD *)&v40 + 1) = v34;
  LODWORD(v41) = Size;
  if ( (unsigned __int64)(unsigned int)Size + 48 > 0xFFB8
    || (result = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 192LL))(
                   *((_QWORD *)this + 2),
                   &v37,
                   0,
                   0),
        (int)result >= 0) )
  {
    if ( Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((char *)this + 320) )
    {
      v18 = *((_QWORD *)this + 7);
      if ( *(_DWORD *)(v18 + 100) )
      {
        v19 = 0;
        while ( 1 )
        {
          if ( (*(_BYTE *)(v18 + 24LL * v19 + 112) & 1) != 0 )
            goto LABEL_37;
          v20 = *(unsigned int *)(v18 + 24LL * v19 + 124);
          if ( !(_DWORD)v20 )
            goto LABEL_37;
          v21 = v18 + v20;
          v22 = std::map<_GUID,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState,Performance::lessGuid,std::allocator<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>>>::operator[](
                  (char *)this + 40,
                  v5)
              + 16;
          memset(v42, 0, sizeof(v42));
          v23 = -1;
          do
            ++v23;
          while ( *(_WORD *)(v21 + 2 * v23) );
          std::wstring::_Construct<1,unsigned short const *>(v42, v21);
          v24 = *(_BYTE *)(std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
                             v22,
                             v36,
                             v42)
                         + 8);
          std::wstring::~wstring(v42);
          if ( !v24 )
            break;
          v25 = *((_DWORD *)this + 20);
          v26 = v25 - 16;
          if ( v25 < 0x10 )
            v26 = 0;
          LODWORD(v34) = v26;
          v27 = (__int64 (__fastcall *)(__int16 *, __int64, __int64, __int64 *))Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((char *)this + 320);
          v28 = v27(&v43, v21, (*((_QWORD *)this + 9) + 16LL) & -(__int64)(*((_QWORD *)this + 9) != 0), &v34);
          if ( v28 == 122 )
          {
            v29 = v34;
            if ( (unsigned int)v34 <= v26 )
              break;
            v30 = (void *)*((_QWORD *)this + 9);
            if ( v30 )
            {
              free(v30);
              v29 = v34;
            }
            v31 = o_malloc_0(v29 + 16LL);
            *((_QWORD *)this + 9) = v31;
            if ( !v31 )
              return 2147942414LL;
            *((_DWORD *)this + 20) = v29 + 16;
            v32 = (__int64 (__fastcall *)(__int16 *, __int64, __int64, __int64 *))Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((char *)this + 320);
            v28 = v32(&v43, v21, *((_QWORD *)this + 9) + 16LL, &v34);
          }
          v5 = v35;
          if ( !v28 )
          {
            v37 = *(_OWORD *)&a2->Header.Size;
            v38 = *(__m256i *)&a2->Header.TimeStamp.LowPart;
            v39 = *(_OWORD *)&a2->InstanceId;
            v40 = *(_OWORD *)a2->ParentGuid.Data4;
            v41 = *(_QWORD *)&a2->MofLength;
            *(_OWORD *)&v38.m256i_u64[1] = EventMetadataGuid;
            DWORD1(v37) = 33;
            *(struct _GUID *)*((_QWORD *)this + 9) = *v35;
            *((_QWORD *)&v40 + 1) = *((_QWORD *)this + 9);
            LODWORD(v41) = v34 + 16;
            if ( (unsigned __int64)(unsigned int)(v34 + 16) + 48 <= 0xFFB8 )
            {
              result = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 192LL))(
                         *((_QWORD *)this + 2),
                         &v37,
                         0,
                         0);
              if ( (int)result < 0 )
                return result;
            }
          }
LABEL_37:
          ++v19;
          v18 = *((_QWORD *)this + 7);
          if ( v19 >= *(_DWORD *)(v18 + 100) )
            return 0;
        }
        v5 = v35;
        goto LABEL_37;
      }
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18001c584  push    rbp
0x18001c586  push    rbx
0x18001c587  push    rsi
0x18001c588  push    rdi
0x18001c589  push    r12
0x18001c58b  push    r13
0x18001c58d  push    r14
0x18001c58f  push    r15
0x18001c591  lea     rbp, [rsp-68h]
0x18001c596  sub     rsp, 168h
0x18001c59d  mov     rax, cs:__security_cookie
0x18001c5a4  xor     rax, rsp
0x18001c5a7  mov     [rbp+0A0h+var_50], rax
0x18001c5ab  mov     r15, r9
0x18001c5ae  mov     rbx, r8
0x18001c5b1  mov     [rsp+1A0h+var_160], rbx
0x18001c5b6  mov     rsi, rdx
0x18001c5b9  mov     rdi, rcx
0x18001c5bc  xor     edx, edx; Val
0x18001c5be  lea     r8d, [rdx+6Eh]; Size
0x18001c5c2  lea     rcx, [rbp+0A0h+var_BE]; void *
0x18001c5c6  call    memset_0
0x18001c5cb  mov     eax, 70h ; 'p'
0x18001c5d0  mov     [rbp+0A0h+var_C0], ax
0x18001c5d4  movups  xmm0, xmmword ptr [rbx]
0x18001c5d7  movdqu  [rbp+0A0h+var_A8], xmm0
0x18001c5dc  mov     rax, [r15]
0x18001c5df  mov     [rbp+0A0h+var_98], rax
0x18001c5e3  mov     rax, [r15+8]
0x18001c5e7  mov     [rbp+0A0h+var_90], rax
0x18001c5eb  mov     eax, [rdi+40h]
0x18001c5ee  mov     dword ptr [rsp+1A0h+Size], eax
0x18001c5f2  lea     r14, [rdi+120h]
0x18001c5f9  mov     rcx, r14
0x18001c5fc  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18001c601  lea     rcx, [rsp+1A0h+Size]
0x18001c606  mov     [rsp+1A0h+var_180], rcx
0x18001c60b  mov     r9, [rdi+38h]
0x18001c60f  xor     r8d, r8d
0x18001c612  xor     edx, edx
0x18001c614  lea     rcx, [rbp+0A0h+var_C0]
0x18001c618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c61d  xor     r12d, r12d
0x18001c620  cmp     eax, 490h
0x18001c625  jnz     short loc_18001C64F
0x18001c627  mov     [rbp+0A0h+var_90], r12
0x18001c62b  mov     rcx, r14
0x18001c62e  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18001c633  lea     rcx, [rsp+1A0h+Size]
0x18001c638  mov     [rsp+1A0h+var_180], rcx
0x18001c63d  mov     r9, [rdi+38h]
0x18001c641  xor     r8d, r8d
0x18001c644  xor     edx, edx
0x18001c646  lea     rcx, [rbp+0A0h+var_C0]
0x18001c64a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c64f  cmp     eax, 7Ah ; 'z'
0x18001c652  jnz     short loc_18001C6AF
0x18001c654  mov     ebx, dword ptr [rsp+1A0h+Size]
0x18001c658  cmp     ebx, [rdi+40h]
0x18001c65b  jbe     short loc_18001C6B3
0x18001c65d  mov     rcx, [rdi+38h]; Block
0x18001c661  test    rcx, rcx
0x18001c664  jz      short loc_18001C66F
0x18001c666  call    free
0x18001c66b  mov     ebx, dword ptr [rsp+1A0h+Size]
0x18001c66f  mov     ecx, ebx; Size
0x18001c671  call    _o_malloc_0
0x18001c676  mov     [rdi+38h], rax
0x18001c67a  test    rax, rax
0x18001c67d  jz      loc_18001C9B9
0x18001c683  mov     [rdi+40h], ebx
0x18001c686  mov     rcx, r14
0x18001c689  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18001c68e  lea     rcx, [rsp+1A0h+Size]
0x18001c693  mov     [rsp+1A0h+var_180], rcx
0x18001c698  mov     r9, [rdi+38h]
0x18001c69c  xor     r8d, r8d
0x18001c69f  xor     edx, edx
0x18001c6a1  lea     rcx, [rbp+0A0h+var_C0]
0x18001c6a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c6aa  mov     rbx, [rsp+1A0h+var_160]
0x18001c6af  test    eax, eax
0x18001c6b1  jz      short loc_18001C6BD
0x18001c6b3  mov     eax, 1
0x18001c6b8  jmp     loc_18001C999
0x18001c6bd  mov     rcx, [rdi+38h]
0x18001c6c1  cmp     [rcx+28h], r12
0x18001c6c5  jnz     short loc_18001C6D4
0x18001c6c7  mov     rax, [r15+8]
0x18001c6cb  test    rax, rax
0x18001c6ce  jz      short loc_18001C6D4
0x18001c6d0  mov     [rcx+28h], rax
0x18001c6d4  mov     rdx, [rdi+38h]
0x18001c6d8  mov     [rsp+1A0h+var_168], rdx
0x18001c6dd  lea     rcx, [rdi+58h]
0x18001c6e1  lea     rax, [rsp+1A0h+Size]
0x18001c6e6  mov     [rsp+1A0h+var_180], rax
0x18001c6eb  lea     r9, [rsp+1A0h+var_168]
0x18001c6f0  mov     r8d, dword ptr [rsp+1A0h+Size]
0x18001c6f5  call    ?Transform@?$CTraceEventInfoTransformImpl@VCTraceEventInfoDelocalizer@Performance@Windows@Microsoft@@@Performance@Windows@Microsoft@@IEAAJPEBU_TRACE_EVENT_INFO@@KPEAPEBU5@PEAK@Z; Microsoft::Windows::Performance::CTraceEventInfoTransformImpl<Microsoft::Windows::Performance::CTraceEventInfoDelocalizer>::Transform(_TRACE_EVENT_INFO const *,ulong,_TRACE_EVENT_INFO const * *,ulong *)
0x18001c6fa  movups  xmm0, xmmword ptr [rsi]
0x18001c6fd  movaps  [rsp+1A0h+var_140], xmm0
0x18001c702  movups  xmm1, xmmword ptr [rsi+10h]
0x18001c706  movaps  [rsp+1A0h+var_130], xmm1
0x18001c70b  movups  xmm0, xmmword ptr [rsi+20h]
0x18001c70f  movaps  [rbp+0A0h+var_120], xmm0
0x18001c713  movups  xmm1, xmmword ptr [rsi+30h]
0x18001c717  movaps  [rbp+0A0h+var_110], xmm1
0x18001c71b  movups  xmm0, xmmword ptr [rsi+40h]
0x18001c71f  movaps  [rbp+0A0h+var_100], xmm0
0x18001c723  movsd   xmm1, qword ptr [rsi+50h]
0x18001c728  movsd   [rbp+0A0h+var_F0], xmm1
0x18001c72d  movups  xmm0, cs:EventMetadataGuid
0x18001c734  movdqu  [rsp+1A0h+var_130+8], xmm0
0x18001c73a  mov     dword ptr [rsp+1A0h+var_140+4], 20h ; ' '
0x18001c742  mov     rax, [rsp+1A0h+var_168]
0x18001c747  mov     qword ptr [rbp+0A0h+var_100+8], rax
0x18001c74b  mov     eax, dword ptr [rsp+1A0h+Size]
0x18001c74f  mov     dword ptr [rbp+0A0h+var_F0], eax
0x18001c752  lea     rcx, [rax+30h]
0x18001c756  cmp     rcx, 0FFB8h
0x18001c75d  ja      short loc_18001C785
0x18001c75f  mov     rcx, [rdi+10h]
0x18001c763  mov     rax, [rcx]
0x18001c766  xor     r9d, r9d
0x18001c769  xor     r8d, r8d
0x18001c76c  lea     rdx, [rsp+1A0h+var_140]
0x18001c771  mov     rax, [rax+0C0h]
0x18001c778  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c77d  test    eax, eax
0x18001c77f  js      loc_18001C999
0x18001c785  lea     r13, [rdi+140h]
0x18001c78c  mov     rcx, r13
0x18001c78f  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18001c794  test    rax, rax
0x18001c797  jz      loc_18001C997
0x18001c79d  mov     rcx, [rdi+38h]
0x18001c7a1  cmp     [rcx+64h], r12d
0x18001c7a5  jbe     loc_18001C997
0x18001c7ab  mov     r14d, r12d
0x18001c7ae  mov     eax, r14d
0x18001c7b1  lea     rdx, [rax+rax*2]
0x18001c7b5  test    byte ptr [rcx+rdx*8+70h], 1
0x18001c7ba  jnz     loc_18001C986
0x18001c7c0  mov     eax, [rcx+rdx*8+7Ch]
0x18001c7c4  test    eax, eax
0x18001c7c6  jz      loc_18001C986
0x18001c7cc  lea     r15, [rcx+rax]
0x18001c7d0  lea     rcx, [rdi+28h]
0x18001c7d4  mov     rdx, rbx
0x18001c7d7  call    ??A?$map@U_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@UlessGuid@4@V?$allocator@U?$pair@$$CBU_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAAEAUCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEBU_GUID@@@Z; std::map<_GUID,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState,Performance::lessGuid,std::allocator<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>>>::operator[](_GUID const &)
0x18001c7dc  lea     rbx, [rax+10h]
0x18001c7e0  xorps   xmm0, xmm0
0x18001c7e3  movups  [rbp+0A0h+var_E0], xmm0
0x18001c7e7  xorps   xmm1, xmm1
0x18001c7ea  movdqu  [rbp+0A0h+var_D0], xmm1
0x18001c7ef  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001c7f3  inc     r8
0x18001c7f6  cmp     [r15+r8*2], r12w
0x18001c7fb  jnz     short loc_18001C7F3
0x18001c7fd  mov     rdx, r15
0x18001c800  lea     rcx, [rbp+0A0h+var_E0]
0x18001c804  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001c809  nop
0x18001c80a  lea     r8, [rbp+0A0h+var_E0]
0x18001c80e  lea     rdx, [rsp+1A0h+var_158]
0x18001c813  mov     rcx, rbx
0x18001c816  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring &&)
0x18001c81b  mov     bl, [rax+8]
0x18001c81e  lea     rcx, [rbp+0A0h+var_E0]
0x18001c822  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001c827  test    bl, bl
0x18001c829  jz      loc_18001C981
0x18001c82f  mov     ecx, [rdi+50h]
0x18001c832  lea     r12d, [rcx-10h]
0x18001c836  xor     eax, eax
0x18001c838  cmp     ecx, 10h
0x18001c83b  cmovb   r12d, eax
0x18001c83f  mov     dword ptr [rsp+1A0h+var_168], r12d
0x18001c844  mov     rcx, r13
0x18001c847  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18001c84c  mov     rcx, [rdi+48h]
0x18001c850  lea     rdx, [rcx+10h]
0x18001c854  neg     rcx
0x18001c857  sbb     r8, r8
0x18001c85a  and     r8, rdx
0x18001c85d  lea     r9, [rsp+1A0h+var_168]
0x18001c862  mov     rdx, r15
0x18001c865  lea     rcx, [rbp+0A0h+var_C0]
0x18001c869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c86e  cmp     eax, 7Ah ; 'z'
0x18001c871  jnz     short loc_18001C8D6
0x18001c873  mov     ebx, dword ptr [rsp+1A0h+var_168]
0x18001c877  cmp     ebx, r12d
0x18001c87a  jbe     loc_18001C97E
0x18001c880  mov     rcx, [rdi+48h]; Block
0x18001c884  xor     r12d, r12d
0x18001c887  test    rcx, rcx
0x18001c88a  jz      short loc_18001C895
0x18001c88c  call    free
0x18001c891  mov     ebx, dword ptr [rsp+1A0h+var_168]
0x18001c895  mov     ecx, ebx
0x18001c897  add     rcx, 10h; Size
0x18001c89b  call    _o_malloc_0
0x18001c8a0  mov     [rdi+48h], rax
0x18001c8a4  test    rax, rax
0x18001c8a7  jz      loc_18001C9B9
0x18001c8ad  lea     eax, [rbx+10h]
0x18001c8b0  mov     [rdi+50h], eax
0x18001c8b3  mov     rcx, r13
0x18001c8b6  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18001c8bb  mov     r8, [rdi+48h]
0x18001c8bf  add     r8, 10h
0x18001c8c3  lea     r9, [rsp+1A0h+var_168]
0x18001c8c8  mov     rdx, r15
0x18001c8cb  lea     rcx, [rbp+0A0h+var_C0]
0x18001c8cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c8d4  jmp     short loc_18001C8D9
0x18001c8d6  xor     r12d, r12d
0x18001c8d9  mov     rbx, [rsp+1A0h+var_160]
0x18001c8de  test    eax, eax
0x18001c8e0  jnz     loc_18001C986
0x18001c8e6  movups  xmm0, xmmword ptr [rsi]
0x18001c8e9  movaps  [rsp+1A0h+var_140], xmm0
0x18001c8ee  movups  xmm1, xmmword ptr [rsi+10h]
0x18001c8f2  movaps  [rsp+1A0h+var_130], xmm1
0x18001c8f7  movups  xmm0, xmmword ptr [rsi+20h]
0x18001c8fb  movaps  [rbp+0A0h+var_120], xmm0
0x18001c8ff  movups  xmm1, xmmword ptr [rsi+30h]
0x18001c903  movaps  [rbp+0A0h+var_110], xmm1
0x18001c907  movups  xmm0, xmmword ptr [rsi+40h]
0x18001c90b  movaps  [rbp+0A0h+var_100], xmm0
0x18001c90f  movsd   xmm1, qword ptr [rsi+50h]
0x18001c914  movsd   [rbp+0A0h+var_F0], xmm1
0x18001c919  movups  xmm0, cs:EventMetadataGuid
0x18001c920  movdqu  [rsp+1A0h+var_130+8], xmm0
0x18001c926  mov     dword ptr [rsp+1A0h+var_140+4], 21h ; '!'
0x18001c92e  movups  xmm0, xmmword ptr [rbx]
0x18001c931  mov     rax, [rdi+48h]
0x18001c935  movdqu  xmmword ptr [rax], xmm0
0x18001c939  mov     rax, [rdi+48h]
0x18001c93d  mov     qword ptr [rbp+0A0h+var_100+8], rax
0x18001c941  mov     eax, dword ptr [rsp+1A0h+var_168]
0x18001c945  add     eax, 10h
0x18001c948  mov     dword ptr [rbp+0A0h+var_F0], eax
0x18001c94b  mov     ecx, eax
0x18001c94d  add     rcx, 30h ; '0'
0x18001c951  cmp     rcx, 0FFB8h
0x18001c958  ja      short loc_18001C986
0x18001c95a  mov     rcx, [rdi+10h]
0x18001c95e  mov     rax, [rcx]
0x18001c961  xor     r9d, r9d
0x18001c964  xor     r8d, r8d
0x18001c967  lea     rdx, [rsp+1A0h+var_140]
0x18001c96c  mov     rax, [rax+0C0h]
0x18001c973  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c978  test    eax, eax
0x18001c97a  js      short loc_18001C999
0x18001c97c  jmp     short loc_18001C986
0x18001c97e  xor     r12d, r12d
0x18001c981  mov     rbx, [rsp+1A0h+var_160]
0x18001c986  inc     r14d
0x18001c989  mov     rcx, [rdi+38h]
0x18001c98d  cmp     r14d, [rcx+64h]
0x18001c991  jb      loc_18001C7AE
0x18001c997  xor     eax, eax
0x18001c999  mov     rcx, [rbp+0A0h+var_50]
0x18001c99d  xor     rcx, rsp; StackCookie
0x18001c9a0  call    __security_check_cookie
0x18001c9a5  add     rsp, 168h
0x18001c9ac  pop     r15
0x18001c9ae  pop     r14
0x18001c9b0  pop     r13
0x18001c9b2  pop     r12
0x18001c9b4  pop     rdi
0x18001c9b5  pop     rsi
0x18001c9b6  pop     rbx
0x18001c9b7  pop     rbp
0x18001c9b8  retn
0x18001c9b9  mov     eax, 8007000Eh
0x18001c9be  jmp     short loc_18001C999
```
