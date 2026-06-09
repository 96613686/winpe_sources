# Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CreateMetadataEvent(_EVENT_TRACE const *,_GUID const &,_EVENT_DESCRIPTOR const &)

- ea: `0x18002bccc`
- end: `0x18002c109`
- name: `?CreateMetadataEvent@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEBU_EVENT_TRACE@@AEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@@Z`
- size: `1085`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *__hidden this, const struct _EVENT_TRACE *, const struct _GUID *, const struct _EVENT_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18002c210`

## callees

- `0x180001b60`
- `0x18000262c`
- `0x18000a600`
- `0x18000fb98`
- `0x180012238`
- `0x1800271c8`
- `0x18002b8a0`
- `0x18002bccc`
- `0x18002cc18`
- `0x180037010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002bdab`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002bfd4`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002bdab`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002bfd4`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002bdbb`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002bfe8`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002bdbb`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002bfe8`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CreateMetadataEvent(
        Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *this,
        const struct _EVENT_TRACE *a2,
        const struct _GUID *a3,
        const struct _EVENT_DESCRIPTOR *a4)
{
  FARPROC v8; // rax
  int v9; // eax
  FARPROC v10; // rax
  unsigned int v11; // eax
  void *v12; // rcx
  void *v13; // rax
  FARPROC v14; // rax
  __int64 result; // rax
  __int64 v16; // rcx
  ULONGLONG Keyword; // rax
  __int64 v18; // rcx
  unsigned int i; // r14d
  __int64 v20; // rax
  _WORD *v21; // r15
  __int64 v22; // rbx
  unsigned __int64 v23; // r8
  char v24; // bl
  unsigned int v25; // ecx
  unsigned int v26; // ebx
  FARPROC v27; // rax
  int v28; // eax
  unsigned int v29; // eax
  void *v30; // rcx
  void *v31; // rax
  FARPROC v32; // rax
  size_t Size; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v34; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v35[16]; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v36; // [rsp+50h] [rbp-B0h] BYREF
  __m256i v37; // [rsp+60h] [rbp-A0h]
  __int128 v38; // [rsp+80h] [rbp-80h]
  __int128 v39; // [rsp+90h] [rbp-70h]
  __int64 v40; // [rsp+A0h] [rbp-60h]
  _OWORD v41[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int16 v42; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v43[22]; // [rsp+D2h] [rbp-2Eh] BYREF
  struct _GUID v44; // [rsp+E8h] [rbp-18h]
  struct _EVENT_DESCRIPTOR v45; // [rsp+F8h] [rbp-8h]

  memset_0(v43, 0, 0x6Eu);
  v42 = 112;
  v44 = *a3;
  v45 = *a4;
  LODWORD(Size) = *((_DWORD *)this + 16);
  v8 = Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((__int64 *)this + 36);
  v9 = ((__int64 (__fastcall *)(__int16 *, _QWORD, _QWORD, _QWORD, size_t *))v8)(
         &v42,
         0,
         0,
         *((_QWORD *)this + 7),
         &Size);
  if ( v9 == 1168 )
  {
    v45.Keyword = 0;
    v10 = Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((__int64 *)this + 36);
    v9 = ((__int64 (__fastcall *)(__int16 *, _QWORD, _QWORD, _QWORD, size_t *))v10)(
           &v42,
           0,
           0,
           *((_QWORD *)this + 7),
           &Size);
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
      *((_QWORD *)this + 7) = 0;
      v11 = Size;
    }
    v13 = malloc(v11);
    *((_QWORD *)this + 7) = v13;
    if ( !v13 )
      return 2147942414LL;
    *((_DWORD *)this + 16) = Size;
    v14 = Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((__int64 *)this + 36);
    v9 = ((__int64 (__fastcall *)(__int16 *, _QWORD, _QWORD, _QWORD, size_t *))v14)(
           &v42,
           0,
           0,
           *((_QWORD *)this + 7),
           &Size);
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
  v36 = *(_OWORD *)&a2->Header.Size;
  v37 = *(__m256i *)&a2->Header.TimeStamp.LowPart;
  v38 = *(_OWORD *)&a2->InstanceId;
  v39 = *(_OWORD *)a2->ParentGuid.Data4;
  HIDWORD(v40) = HIDWORD(*(_QWORD *)&a2->MofLength);
  *(_OWORD *)&v37.m256i_u64[1] = EventMetadataGuid;
  DWORD1(v36) = 32;
  *((_QWORD *)&v39 + 1) = v34;
  LODWORD(v40) = Size;
  if ( (unsigned __int64)(unsigned int)Size + 48 > 0xFFB8
    || (result = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 192LL))(
                   *((_QWORD *)this + 2),
                   &v36,
                   0,
                   0),
        (int)result >= 0) )
  {
    if ( Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((__int64 *)this + 40) )
    {
      v18 = *((_QWORD *)this + 7);
      if ( *(_DWORD *)(v18 + 100) )
      {
        for ( i = 0; i < *(_DWORD *)(v18 + 100); ++i )
        {
          if ( (*(_BYTE *)(v18 + 24LL * i + 112) & 1) != 0 )
            goto LABEL_35;
          v20 = *(unsigned int *)(v18 + 24LL * i + 124);
          if ( !(_DWORD)v20 )
            goto LABEL_35;
          v21 = (_WORD *)(v18 + v20);
          v22 = std::map<_GUID,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState,Performance::lessGuid,std::allocator<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>>>::operator[](
                  (char *)this + 40,
                  a3)
              + 16;
          memset(v41, 0, sizeof(v41));
          v23 = -1;
          do
            ++v23;
          while ( v21[v23] );
          std::wstring::_Construct<1,unsigned short const *>((char **)v41, v21, v23);
          v24 = *(_BYTE *)(std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
                             v22,
                             v35,
                             v41)
                         + 8);
          std::wstring::~wstring((char **)v41);
          if ( !v24 )
            goto LABEL_35;
          v25 = *((_DWORD *)this + 20);
          v26 = v25 - 16;
          if ( v25 < 0x10 )
            v26 = 0;
          LODWORD(v34) = v26;
          v27 = Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((__int64 *)this + 40);
          v28 = ((__int64 (__fastcall *)(__int16 *, _WORD *, __int64, __int64 *))v27)(
                  &v42,
                  v21,
                  (*((_QWORD *)this + 9) + 16LL) & -(__int64)(*((_QWORD *)this + 9) != 0),
                  &v34);
          if ( v28 == 122 )
          {
            v29 = v34;
            if ( (unsigned int)v34 <= v26 )
              goto LABEL_35;
            v30 = (void *)*((_QWORD *)this + 9);
            if ( v30 )
            {
              free(v30);
              *((_QWORD *)this + 9) = 0;
              v29 = v34;
            }
            v31 = malloc(v29 + 16LL);
            *((_QWORD *)this + 9) = v31;
            if ( !v31 )
              return 2147942414LL;
            *((_DWORD *)this + 20) = v34 + 16;
            v32 = Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((__int64 *)this + 40);
            v28 = ((__int64 (__fastcall *)(__int16 *, _WORD *, __int64, __int64 *))v32)(
                    &v42,
                    v21,
                    *((_QWORD *)this + 9) + 16LL,
                    &v34);
          }
          if ( !v28 )
          {
            v36 = *(_OWORD *)&a2->Header.Size;
            v37 = *(__m256i *)&a2->Header.TimeStamp.LowPart;
            v38 = *(_OWORD *)&a2->InstanceId;
            v39 = *(_OWORD *)a2->ParentGuid.Data4;
            v40 = *(_QWORD *)&a2->MofLength;
            *(_OWORD *)&v37.m256i_u64[1] = EventMetadataGuid;
            DWORD1(v36) = 33;
            *(struct _GUID *)*((_QWORD *)this + 9) = *a3;
            *((_QWORD *)&v39 + 1) = *((_QWORD *)this + 9);
            LODWORD(v40) = v34 + 16;
            if ( (unsigned __int64)(unsigned int)(v34 + 16) + 48 <= 0xFFB8 )
            {
              result = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 192LL))(
                         *((_QWORD *)this + 2),
                         &v36,
                         0,
                         0);
              if ( (int)result < 0 )
                return result;
            }
          }
LABEL_35:
          v18 = *((_QWORD *)this + 7);
        }
      }
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18002bccc  push    rbp
0x18002bcce  push    rbx
0x18002bccf  push    rsi
0x18002bcd0  push    rdi
0x18002bcd1  push    r12
0x18002bcd3  push    r13
0x18002bcd5  push    r14
0x18002bcd7  push    r15
0x18002bcd9  lea     rbp, [rsp-58h]
0x18002bcde  sub     rsp, 158h
0x18002bce5  mov     rax, cs:__security_cookie
0x18002bcec  xor     rax, rsp
0x18002bcef  mov     [rbp+90h+var_50], rax
0x18002bcf3  mov     r14, r9
0x18002bcf6  mov     r13, r8
0x18002bcf9  mov     rsi, rdx
0x18002bcfc  mov     rdi, rcx
0x18002bcff  xor     edx, edx; Val
0x18002bd01  lea     r8d, [rdx+6Eh]; Size
0x18002bd05  lea     rcx, [rbp+90h+var_BE]; void *
0x18002bd09  call    memset_0
0x18002bd0e  mov     eax, 70h ; 'p'
0x18002bd13  mov     [rbp+90h+var_C0], ax
0x18002bd17  movups  xmm0, xmmword ptr [r13+0]
0x18002bd1c  movdqu  [rbp+90h+var_A8], xmm0
0x18002bd21  mov     rax, [r14]
0x18002bd24  mov     [rbp+90h+var_98], rax
0x18002bd28  mov     rax, [r14+8]
0x18002bd2c  mov     [rbp+90h+var_90], rax
0x18002bd30  mov     eax, [rdi+40h]
0x18002bd33  mov     dword ptr [rsp+190h+Size], eax
0x18002bd37  lea     rbx, [rdi+120h]
0x18002bd3e  mov     rcx, rbx
0x18002bd41  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18002bd46  lea     rcx, [rsp+190h+Size]
0x18002bd4b  mov     [rsp+190h+var_170], rcx
0x18002bd50  mov     r9, [rdi+38h]
0x18002bd54  xor     r8d, r8d
0x18002bd57  xor     edx, edx
0x18002bd59  lea     rcx, [rbp+90h+var_C0]
0x18002bd5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd62  xor     r15d, r15d
0x18002bd65  cmp     eax, 490h
0x18002bd6a  jnz     short loc_18002BD94
0x18002bd6c  mov     [rbp+90h+var_90], r15
0x18002bd70  mov     rcx, rbx
0x18002bd73  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18002bd78  lea     rcx, [rsp+190h+Size]
0x18002bd7d  mov     [rsp+190h+var_170], rcx
0x18002bd82  mov     r9, [rdi+38h]
0x18002bd86  xor     r8d, r8d
0x18002bd89  xor     edx, edx
0x18002bd8b  lea     rcx, [rbp+90h+var_C0]
0x18002bd8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd94  cmp     eax, 7Ah ; 'z'
0x18002bd97  jnz     short loc_18002BDF9
0x18002bd99  mov     eax, dword ptr [rsp+190h+Size]
0x18002bd9d  cmp     eax, [rdi+40h]
0x18002bda0  jbe     short loc_18002BDFD
0x18002bda2  mov     rcx, [rdi+38h]; Block
0x18002bda6  test    rcx, rcx
0x18002bda9  jz      short loc_18002BDB9
0x18002bdab  call    cs:__imp_free
0x18002bdb1  mov     [rdi+38h], r15
0x18002bdb5  mov     eax, dword ptr [rsp+190h+Size]
0x18002bdb9  mov     ecx, eax; Size
0x18002bdbb  call    cs:__imp_malloc
0x18002bdc1  mov     [rdi+38h], rax
0x18002bdc5  test    rax, rax
0x18002bdc8  jz      loc_18002C102
0x18002bdce  mov     eax, dword ptr [rsp+190h+Size]
0x18002bdd2  mov     [rdi+40h], eax
0x18002bdd5  mov     rcx, rbx
0x18002bdd8  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18002bddd  lea     rcx, [rsp+190h+Size]
0x18002bde2  mov     [rsp+190h+var_170], rcx
0x18002bde7  mov     r9, [rdi+38h]
0x18002bdeb  xor     r8d, r8d
0x18002bdee  xor     edx, edx
0x18002bdf0  lea     rcx, [rbp+90h+var_C0]
0x18002bdf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bdf9  test    eax, eax
0x18002bdfb  jz      short loc_18002BE07
0x18002bdfd  mov     eax, 1
0x18002be02  jmp     loc_18002C0E2
0x18002be07  mov     rcx, [rdi+38h]
0x18002be0b  cmp     [rcx+28h], r15
0x18002be0f  jnz     short loc_18002BE1E
0x18002be11  mov     rax, [r14+8]
0x18002be15  test    rax, rax
0x18002be18  jz      short loc_18002BE1E
0x18002be1a  mov     [rcx+28h], rax
0x18002be1e  mov     rdx, [rdi+38h]
0x18002be22  mov     [rsp+190h+var_158], rdx
0x18002be27  lea     rcx, [rdi+58h]
0x18002be2b  lea     rax, [rsp+190h+Size]
0x18002be30  mov     [rsp+190h+var_170], rax
0x18002be35  lea     r9, [rsp+190h+var_158]
0x18002be3a  mov     r8d, dword ptr [rsp+190h+Size]
0x18002be3f  call    ?Transform@?$CTraceEventInfoTransformImpl@VCTraceEventInfoDelocalizer@Performance@Windows@Microsoft@@@Performance@Windows@Microsoft@@IEAAJPEBU_TRACE_EVENT_INFO@@KPEAPEBU5@PEAK@Z; Microsoft::Windows::Performance::CTraceEventInfoTransformImpl<Microsoft::Windows::Performance::CTraceEventInfoDelocalizer>::Transform(_TRACE_EVENT_INFO const *,ulong,_TRACE_EVENT_INFO const * *,ulong *)
0x18002be44  movups  xmm0, xmmword ptr [rsi]
0x18002be47  movaps  [rsp+190h+var_140], xmm0
0x18002be4c  movups  xmm1, xmmword ptr [rsi+10h]
0x18002be50  movaps  [rsp+190h+var_130], xmm1
0x18002be55  movups  xmm0, xmmword ptr [rsi+20h]
0x18002be59  movaps  [rsp+190h+var_120], xmm0
0x18002be5e  movups  xmm1, xmmword ptr [rsi+30h]
0x18002be62  movaps  [rbp+90h+var_110], xmm1
0x18002be66  movups  xmm0, xmmword ptr [rsi+40h]
0x18002be6a  movaps  [rbp+90h+var_100], xmm0
0x18002be6e  movsd   xmm1, qword ptr [rsi+50h]
0x18002be73  movsd   [rbp+90h+var_F0], xmm1
0x18002be78  movups  xmm0, cs:EventMetadataGuid
0x18002be7f  movdqu  [rsp+190h+var_130+8], xmm0
0x18002be85  mov     dword ptr [rsp+190h+var_140+4], 20h ; ' '
0x18002be8d  mov     rax, [rsp+190h+var_158]
0x18002be92  mov     qword ptr [rbp+90h+var_100+8], rax
0x18002be96  mov     eax, dword ptr [rsp+190h+Size]
0x18002be9a  mov     dword ptr [rbp+90h+var_F0], eax
0x18002be9d  lea     rcx, [rax+30h]
0x18002bea1  cmp     rcx, 0FFB8h
0x18002bea8  ja      short loc_18002BED0
0x18002beaa  mov     rcx, [rdi+10h]
0x18002beae  mov     rax, [rcx]
0x18002beb1  xor     r9d, r9d
0x18002beb4  xor     r8d, r8d
0x18002beb7  lea     rdx, [rsp+190h+var_140]
0x18002bebc  mov     rax, [rax+0C0h]
0x18002bec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bec8  test    eax, eax
0x18002beca  js      loc_18002C0E2
0x18002bed0  lea     r12, [rdi+140h]
0x18002bed7  mov     rcx, r12
0x18002beda  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18002bedf  test    rax, rax
0x18002bee2  jz      loc_18002C0E0
0x18002bee8  mov     rcx, [rdi+38h]
0x18002beec  cmp     [rcx+64h], r15d
0x18002bef0  jbe     loc_18002C0E0
0x18002bef6  mov     r14d, r15d
0x18002bef9  mov     eax, r14d
0x18002befc  lea     rdx, [rax+rax*2]
0x18002bf00  test    byte ptr [rcx+rdx*8+70h], 1
0x18002bf05  jnz     loc_18002C0CF
0x18002bf0b  mov     eax, [rcx+rdx*8+7Ch]
0x18002bf0f  test    eax, eax
0x18002bf11  jz      loc_18002C0CF
0x18002bf17  lea     r15, [rcx+rax]
0x18002bf1b  lea     rcx, [rdi+28h]
0x18002bf1f  mov     rdx, r13
0x18002bf22  call    ??A?$map@U_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@UlessGuid@4@V?$allocator@U?$pair@$$CBU_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAAEAUCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEBU_GUID@@@Z; std::map<_GUID,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState,Performance::lessGuid,std::allocator<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>>>::operator[](_GUID const &)
0x18002bf27  lea     rbx, [rax+10h]
0x18002bf2b  xorps   xmm0, xmm0
0x18002bf2e  movups  [rbp+90h+var_E0], xmm0
0x18002bf32  xorps   xmm1, xmm1
0x18002bf35  movdqu  [rbp+90h+var_D0], xmm1
0x18002bf3a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002bf3e  xor     eax, eax
0x18002bf40  inc     r8
0x18002bf43  cmp     [r15+r8*2], ax
0x18002bf48  jnz     short loc_18002BF40
0x18002bf4a  mov     rdx, r15
0x18002bf4d  lea     rcx, [rbp+90h+var_E0]
0x18002bf51  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002bf56  nop
0x18002bf57  lea     r8, [rbp+90h+var_E0]
0x18002bf5b  lea     rdx, [rsp+190h+var_150]
0x18002bf60  mov     rcx, rbx
0x18002bf63  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring &&)
0x18002bf68  mov     bl, [rax+8]
0x18002bf6b  lea     rcx, [rbp+90h+var_E0]
0x18002bf6f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002bf74  xor     eax, eax
0x18002bf76  test    bl, bl
0x18002bf78  jz      loc_18002C0CC
0x18002bf7e  mov     ecx, [rdi+50h]
0x18002bf81  lea     ebx, [rcx-10h]
0x18002bf84  cmp     ecx, 10h
0x18002bf87  cmovb   ebx, eax
0x18002bf8a  mov     dword ptr [rsp+190h+var_158], ebx
0x18002bf8e  mov     rcx, r12
0x18002bf91  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18002bf96  mov     rcx, [rdi+48h]
0x18002bf9a  lea     rdx, [rcx+10h]
0x18002bf9e  neg     rcx
0x18002bfa1  sbb     r8, r8
0x18002bfa4  and     r8, rdx
0x18002bfa7  lea     r9, [rsp+190h+var_158]
0x18002bfac  mov     rdx, r15
0x18002bfaf  lea     rcx, [rbp+90h+var_C0]
0x18002bfb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bfb8  cmp     eax, 7Ah ; 'z'
0x18002bfbb  jnz     short loc_18002C026
0x18002bfbd  mov     eax, dword ptr [rsp+190h+var_158]
0x18002bfc1  cmp     eax, ebx
0x18002bfc3  jbe     loc_18002C0CC
0x18002bfc9  mov     rcx, [rdi+48h]; Block
0x18002bfcd  xor     ebx, ebx
0x18002bfcf  test    rcx, rcx
0x18002bfd2  jz      short loc_18002BFE2
0x18002bfd4  call    cs:__imp_free
0x18002bfda  mov     [rdi+48h], rbx
0x18002bfde  mov     eax, dword ptr [rsp+190h+var_158]
0x18002bfe2  mov     ecx, eax
0x18002bfe4  add     rcx, 10h; Size
0x18002bfe8  call    cs:__imp_malloc
0x18002bfee  mov     [rdi+48h], rax
0x18002bff2  test    rax, rax
0x18002bff5  jz      loc_18002C102
0x18002bffb  mov     eax, dword ptr [rsp+190h+var_158]
0x18002bfff  add     eax, 10h
0x18002c002  mov     [rdi+50h], eax
0x18002c005  mov     rcx, r12
0x18002c008  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18002c00d  mov     r8, [rdi+48h]
0x18002c011  add     r8, 10h
0x18002c015  lea     r9, [rsp+190h+var_158]
0x18002c01a  mov     rdx, r15
0x18002c01d  lea     rcx, [rbp+90h+var_C0]
0x18002c021  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c026  xor     r15d, r15d
0x18002c029  test    eax, eax
0x18002c02b  jnz     loc_18002C0CF
0x18002c031  movups  xmm0, xmmword ptr [rsi]
0x18002c034  movaps  [rsp+190h+var_140], xmm0
0x18002c039  movups  xmm1, xmmword ptr [rsi+10h]
0x18002c03d  movaps  [rsp+190h+var_130], xmm1
0x18002c042  movups  xmm0, xmmword ptr [rsi+20h]
0x18002c046  movaps  [rsp+190h+var_120], xmm0
0x18002c04b  movups  xmm1, xmmword ptr [rsi+30h]
0x18002c04f  movaps  [rbp+90h+var_110], xmm1
0x18002c053  movups  xmm0, xmmword ptr [rsi+40h]
0x18002c057  movaps  [rbp+90h+var_100], xmm0
0x18002c05b  movsd   xmm1, qword ptr [rsi+50h]
0x18002c060  movsd   [rbp+90h+var_F0], xmm1
0x18002c065  movups  xmm0, cs:EventMetadataGuid
0x18002c06c  movdqu  [rsp+190h+var_130+8], xmm0
0x18002c072  mov     dword ptr [rsp+190h+var_140+4], 21h ; '!'
0x18002c07a  movups  xmm0, xmmword ptr [r13+0]
0x18002c07f  mov     rax, [rdi+48h]
0x18002c083  movdqu  xmmword ptr [rax], xmm0
0x18002c087  mov     rax, [rdi+48h]
0x18002c08b  mov     qword ptr [rbp+90h+var_100+8], rax
0x18002c08f  mov     eax, dword ptr [rsp+190h+var_158]
0x18002c093  add     eax, 10h
0x18002c096  mov     dword ptr [rbp+90h+var_F0], eax
0x18002c099  mov     ecx, eax
0x18002c09b  add     rcx, 30h ; '0'
0x18002c09f  cmp     rcx, 0FFB8h
0x18002c0a6  ja      short loc_18002C0CF
0x18002c0a8  mov     rcx, [rdi+10h]
0x18002c0ac  mov     rax, [rcx]
0x18002c0af  xor     r9d, r9d
0x18002c0b2  xor     r8d, r8d
0x18002c0b5  lea     rdx, [rsp+190h+var_140]
0x18002c0ba  mov     rax, [rax+0C0h]
0x18002c0c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c0c6  test    eax, eax
0x18002c0c8  js      short loc_18002C0E2
0x18002c0ca  jmp     short loc_18002C0CF
0x18002c0cc  xor     r15d, r15d
0x18002c0cf  inc     r14d
0x18002c0d2  mov     rcx, [rdi+38h]
0x18002c0d6  cmp     r14d, [rcx+64h]
0x18002c0da  jb      loc_18002BEF9
0x18002c0e0  xor     eax, eax
0x18002c0e2  mov     rcx, [rbp+90h+var_50]
0x18002c0e6  xor     rcx, rsp; StackCookie
0x18002c0e9  call    __security_check_cookie
0x18002c0ee  add     rsp, 158h
0x18002c0f5  pop     r15
0x18002c0f7  pop     r14
0x18002c0f9  pop     r13
0x18002c0fb  pop     r12
0x18002c0fd  pop     rdi
0x18002c0fe  pop     rsi
0x18002c0ff  pop     rbx
0x18002c100  pop     rbp
0x18002c101  retn
0x18002c102  mov     eax, 8007000Eh
0x18002c107  jmp     short loc_18002C0E2
```
