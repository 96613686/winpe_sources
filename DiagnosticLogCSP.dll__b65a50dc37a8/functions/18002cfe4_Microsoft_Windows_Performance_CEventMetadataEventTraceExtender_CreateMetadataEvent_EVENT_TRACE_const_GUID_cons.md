# Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CreateMetadataEvent(_EVENT_TRACE const *,_GUID const &,_EVENT_DESCRIPTOR const &)

- ea: `0x18002cfe4`
- end: `0x18002d43a`
- name: `?CreateMetadataEvent@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEBU_EVENT_TRACE@@AEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@@Z`
- size: `1110`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *__hidden this, const struct _EVENT_TRACE *, const struct _GUID *, const struct _EVENT_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18002d540`

## callees

- `0x180001b90`
- `0x18000265c`
- `0x18000a924`
- `0x1800103a8`
- `0x180012bf8`
- `0x18002834c`
- `0x18002cbb0`
- `0x18002cfe4`
- `0x18002df58`
- `0x180039010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002d0c3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002d2f8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002d0c3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002d2f8`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002d0d9`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002d312`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002d0d9`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002d312`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  __int64 v21; // r15
  __int64 v22; // rbx
  __int64 v23; // r8
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
          v21 = v18 + v20;
          v22 = std::map<_GUID,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState,Performance::lessGuid,std::allocator<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>>>::operator[](
                  (char *)this + 40,
                  a3)
              + 16;
          memset(v41, 0, sizeof(v41));
          v23 = -1;
          do
            ++v23;
          while ( *(_WORD *)(v21 + 2 * v23) );
          std::wstring::_Construct<1,unsigned short const *>(v41, v21, v23);
          v24 = *(_BYTE *)(std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
                             v22,
                             v35,
                             v41)
                         + 8);
          std::wstring::~wstring(v41);
          if ( !v24 )
            goto LABEL_35;
          v25 = *((_DWORD *)this + 20);
          v26 = v25 - 16;
          if ( v25 < 0x10 )
            v26 = 0;
          LODWORD(v34) = v26;
          v27 = Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((__int64 *)this + 40);
          v28 = ((__int64 (__fastcall *)(__int16 *, __int64, __int64, __int64 *))v27)(
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
            v28 = ((__int64 (__fastcall *)(__int16 *, __int64, __int64, __int64 *))v32)(
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
0x18002cfe4  push    rbp
0x18002cfe6  push    rbx
0x18002cfe7  push    rsi
0x18002cfe8  push    rdi
0x18002cfe9  push    r12
0x18002cfeb  push    r13
0x18002cfed  push    r14
0x18002cfef  push    r15
0x18002cff1  lea     rbp, [rsp-58h]
0x18002cff6  sub     rsp, 158h
0x18002cffd  mov     rax, cs:__security_cookie
0x18002d004  xor     rax, rsp
0x18002d007  mov     [rbp+90h+var_50], rax
0x18002d00b  mov     r14, r9
0x18002d00e  mov     r13, r8
0x18002d011  mov     rsi, rdx
0x18002d014  mov     rdi, rcx
0x18002d017  xor     edx, edx; Val
0x18002d019  lea     r8d, [rdx+6Eh]; Size
0x18002d01d  lea     rcx, [rbp+90h+var_BE]; void *
0x18002d021  call    memset_0
0x18002d026  mov     eax, 70h ; 'p'
0x18002d02b  mov     [rbp+90h+var_C0], ax
0x18002d02f  movups  xmm0, xmmword ptr [r13+0]
0x18002d034  movdqu  [rbp+90h+var_A8], xmm0
0x18002d039  mov     rax, [r14]
0x18002d03c  mov     [rbp+90h+var_98], rax
0x18002d040  mov     rax, [r14+8]
0x18002d044  mov     [rbp+90h+var_90], rax
0x18002d048  mov     eax, [rdi+40h]
0x18002d04b  mov     dword ptr [rsp+190h+Size], eax
0x18002d04f  lea     rbx, [rdi+120h]
0x18002d056  mov     rcx, rbx
0x18002d059  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18002d05e  lea     rcx, [rsp+190h+Size]
0x18002d063  mov     [rsp+190h+var_170], rcx
0x18002d068  mov     r9, [rdi+38h]
0x18002d06c  xor     r8d, r8d
0x18002d06f  xor     edx, edx
0x18002d071  lea     rcx, [rbp+90h+var_C0]
0x18002d075  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d07a  xor     r15d, r15d
0x18002d07d  cmp     eax, 490h
0x18002d082  jnz     short loc_18002D0AC
0x18002d084  mov     [rbp+90h+var_90], r15
0x18002d088  mov     rcx, rbx
0x18002d08b  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18002d090  lea     rcx, [rsp+190h+Size]
0x18002d095  mov     [rsp+190h+var_170], rcx
0x18002d09a  mov     r9, [rdi+38h]
0x18002d09e  xor     r8d, r8d
0x18002d0a1  xor     edx, edx
0x18002d0a3  lea     rcx, [rbp+90h+var_C0]
0x18002d0a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0ac  cmp     eax, 7Ah ; 'z'
0x18002d0af  jnz     short loc_18002D11D
0x18002d0b1  mov     eax, dword ptr [rsp+190h+Size]
0x18002d0b5  cmp     eax, [rdi+40h]
0x18002d0b8  jbe     short loc_18002D121
0x18002d0ba  mov     rcx, [rdi+38h]; Block
0x18002d0be  test    rcx, rcx
0x18002d0c1  jz      short loc_18002D0D7
0x18002d0c3  call    cs:__imp_free
0x18002d0ca  nop     dword ptr [rax+rax+00h]
0x18002d0cf  mov     [rdi+38h], r15
0x18002d0d3  mov     eax, dword ptr [rsp+190h+Size]
0x18002d0d7  mov     ecx, eax; Size
0x18002d0d9  call    cs:__imp_malloc
0x18002d0e0  nop     dword ptr [rax+rax+00h]
0x18002d0e5  mov     [rdi+38h], rax
0x18002d0e9  test    rax, rax
0x18002d0ec  jz      loc_18002D433
0x18002d0f2  mov     eax, dword ptr [rsp+190h+Size]
0x18002d0f6  mov     [rdi+40h], eax
0x18002d0f9  mov     rcx, rbx
0x18002d0fc  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18002d101  lea     rcx, [rsp+190h+Size]
0x18002d106  mov     [rsp+190h+var_170], rcx
0x18002d10b  mov     r9, [rdi+38h]
0x18002d10f  xor     r8d, r8d
0x18002d112  xor     edx, edx
0x18002d114  lea     rcx, [rbp+90h+var_C0]
0x18002d118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d11d  test    eax, eax
0x18002d11f  jz      short loc_18002D12B
0x18002d121  mov     eax, 1
0x18002d126  jmp     loc_18002D412
0x18002d12b  mov     rcx, [rdi+38h]
0x18002d12f  cmp     [rcx+28h], r15
0x18002d133  jnz     short loc_18002D142
0x18002d135  mov     rax, [r14+8]
0x18002d139  test    rax, rax
0x18002d13c  jz      short loc_18002D142
0x18002d13e  mov     [rcx+28h], rax
0x18002d142  mov     rdx, [rdi+38h]
0x18002d146  mov     [rsp+190h+var_158], rdx
0x18002d14b  lea     rcx, [rdi+58h]
0x18002d14f  lea     rax, [rsp+190h+Size]
0x18002d154  mov     [rsp+190h+var_170], rax
0x18002d159  lea     r9, [rsp+190h+var_158]
0x18002d15e  mov     r8d, dword ptr [rsp+190h+Size]
0x18002d163  call    ?Transform@?$CTraceEventInfoTransformImpl@VCTraceEventInfoDelocalizer@Performance@Windows@Microsoft@@@Performance@Windows@Microsoft@@IEAAJPEBU_TRACE_EVENT_INFO@@KPEAPEBU5@PEAK@Z; Microsoft::Windows::Performance::CTraceEventInfoTransformImpl<Microsoft::Windows::Performance::CTraceEventInfoDelocalizer>::Transform(_TRACE_EVENT_INFO const *,ulong,_TRACE_EVENT_INFO const * *,ulong *)
0x18002d168  movups  xmm0, xmmword ptr [rsi]
0x18002d16b  movaps  [rsp+190h+var_140], xmm0
0x18002d170  movups  xmm1, xmmword ptr [rsi+10h]
0x18002d174  movaps  [rsp+190h+var_130], xmm1
0x18002d179  movups  xmm0, xmmword ptr [rsi+20h]
0x18002d17d  movaps  [rsp+190h+var_120], xmm0
0x18002d182  movups  xmm1, xmmword ptr [rsi+30h]
0x18002d186  movaps  [rbp+90h+var_110], xmm1
0x18002d18a  movups  xmm0, xmmword ptr [rsi+40h]
0x18002d18e  movaps  [rbp+90h+var_100], xmm0
0x18002d192  movsd   xmm1, qword ptr [rsi+50h]
0x18002d197  movsd   [rbp+90h+var_F0], xmm1
0x18002d19c  movups  xmm0, cs:EventMetadataGuid
0x18002d1a3  movdqu  [rsp+190h+var_130+8], xmm0
0x18002d1a9  mov     dword ptr [rsp+190h+var_140+4], 20h ; ' '
0x18002d1b1  mov     rax, [rsp+190h+var_158]
0x18002d1b6  mov     qword ptr [rbp+90h+var_100+8], rax
0x18002d1ba  mov     eax, dword ptr [rsp+190h+Size]
0x18002d1be  mov     dword ptr [rbp+90h+var_F0], eax
0x18002d1c1  lea     rcx, [rax+30h]
0x18002d1c5  cmp     rcx, 0FFB8h
0x18002d1cc  ja      short loc_18002D1F4
0x18002d1ce  mov     rcx, [rdi+10h]
0x18002d1d2  mov     rax, [rcx]
0x18002d1d5  xor     r9d, r9d
0x18002d1d8  xor     r8d, r8d
0x18002d1db  lea     rdx, [rsp+190h+var_140]
0x18002d1e0  mov     rax, [rax+0C0h]
0x18002d1e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d1ec  test    eax, eax
0x18002d1ee  js      loc_18002D412
0x18002d1f4  lea     r12, [rdi+140h]
0x18002d1fb  mov     rcx, r12
0x18002d1fe  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18002d203  test    rax, rax
0x18002d206  jz      loc_18002D410
0x18002d20c  mov     rcx, [rdi+38h]
0x18002d210  cmp     [rcx+64h], r15d
0x18002d214  jbe     loc_18002D410
0x18002d21a  mov     r14d, r15d
0x18002d21d  mov     eax, r14d
0x18002d220  lea     rdx, [rax+rax*2]
0x18002d224  test    byte ptr [rcx+rdx*8+70h], 1
0x18002d229  jnz     loc_18002D3FF
0x18002d22f  mov     eax, [rcx+rdx*8+7Ch]
0x18002d233  test    eax, eax
0x18002d235  jz      loc_18002D3FF
0x18002d23b  lea     r15, [rcx+rax]
0x18002d23f  lea     rcx, [rdi+28h]
0x18002d243  mov     rdx, r13
0x18002d246  call    ??A?$map@U_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@UlessGuid@4@V?$allocator@U?$pair@$$CBU_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAAEAUCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEBU_GUID@@@Z; std::map<_GUID,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState,Performance::lessGuid,std::allocator<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>>>::operator[](_GUID const &)
0x18002d24b  lea     rbx, [rax+10h]
0x18002d24f  xorps   xmm0, xmm0
0x18002d252  movups  [rbp+90h+var_E0], xmm0
0x18002d256  xorps   xmm1, xmm1
0x18002d259  movdqu  [rbp+90h+var_D0], xmm1
0x18002d25e  or      r8, 0FFFFFFFFFFFFFFFFh
0x18002d262  xor     eax, eax
0x18002d264  inc     r8
0x18002d267  cmp     [r15+r8*2], ax
0x18002d26c  jnz     short loc_18002D264
0x18002d26e  mov     rdx, r15
0x18002d271  lea     rcx, [rbp+90h+var_E0]
0x18002d275  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002d27a  nop
0x18002d27b  lea     r8, [rbp+90h+var_E0]
0x18002d27f  lea     rdx, [rsp+190h+var_150]
0x18002d284  mov     rcx, rbx
0x18002d287  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring &&)
0x18002d28c  mov     bl, [rax+8]
0x18002d28f  lea     rcx, [rbp+90h+var_E0]
0x18002d293  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002d298  xor     eax, eax
0x18002d29a  test    bl, bl
0x18002d29c  jz      loc_18002D3FC
0x18002d2a2  mov     ecx, [rdi+50h]
0x18002d2a5  lea     ebx, [rcx-10h]
0x18002d2a8  cmp     ecx, 10h
0x18002d2ab  cmovb   ebx, eax
0x18002d2ae  mov     dword ptr [rsp+190h+var_158], ebx
0x18002d2b2  mov     rcx, r12
0x18002d2b5  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18002d2ba  mov     rcx, [rdi+48h]
0x18002d2be  lea     rdx, [rcx+10h]
0x18002d2c2  neg     rcx
0x18002d2c5  sbb     r8, r8
0x18002d2c8  and     r8, rdx
0x18002d2cb  lea     r9, [rsp+190h+var_158]
0x18002d2d0  mov     rdx, r15
0x18002d2d3  lea     rcx, [rbp+90h+var_C0]
0x18002d2d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d2dc  cmp     eax, 7Ah ; 'z'
0x18002d2df  jnz     short loc_18002D356
0x18002d2e1  mov     eax, dword ptr [rsp+190h+var_158]
0x18002d2e5  cmp     eax, ebx
0x18002d2e7  jbe     loc_18002D3FC
0x18002d2ed  mov     rcx, [rdi+48h]; Block
0x18002d2f1  xor     ebx, ebx
0x18002d2f3  test    rcx, rcx
0x18002d2f6  jz      short loc_18002D30C
0x18002d2f8  call    cs:__imp_free
0x18002d2ff  nop     dword ptr [rax+rax+00h]
0x18002d304  mov     [rdi+48h], rbx
0x18002d308  mov     eax, dword ptr [rsp+190h+var_158]
0x18002d30c  mov     ecx, eax
0x18002d30e  add     rcx, 10h; Size
0x18002d312  call    cs:__imp_malloc
0x18002d319  nop     dword ptr [rax+rax+00h]
0x18002d31e  mov     [rdi+48h], rax
0x18002d322  test    rax, rax
0x18002d325  jz      loc_18002D433
0x18002d32b  mov     eax, dword ptr [rsp+190h+var_158]
0x18002d32f  add     eax, 10h
0x18002d332  mov     [rdi+50h], eax
0x18002d335  mov     rcx, r12
0x18002d338  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18002d33d  mov     r8, [rdi+48h]
0x18002d341  add     r8, 10h
0x18002d345  lea     r9, [rsp+190h+var_158]
0x18002d34a  mov     rdx, r15
0x18002d34d  lea     rcx, [rbp+90h+var_C0]
0x18002d351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d356  xor     r15d, r15d
0x18002d359  test    eax, eax
0x18002d35b  jnz     loc_18002D3FF
0x18002d361  movups  xmm0, xmmword ptr [rsi]
0x18002d364  movaps  [rsp+190h+var_140], xmm0
0x18002d369  movups  xmm1, xmmword ptr [rsi+10h]
0x18002d36d  movaps  [rsp+190h+var_130], xmm1
0x18002d372  movups  xmm0, xmmword ptr [rsi+20h]
0x18002d376  movaps  [rsp+190h+var_120], xmm0
0x18002d37b  movups  xmm1, xmmword ptr [rsi+30h]
0x18002d37f  movaps  [rbp+90h+var_110], xmm1
0x18002d383  movups  xmm0, xmmword ptr [rsi+40h]
0x18002d387  movaps  [rbp+90h+var_100], xmm0
0x18002d38b  movsd   xmm1, qword ptr [rsi+50h]
0x18002d390  movsd   [rbp+90h+var_F0], xmm1
0x18002d395  movups  xmm0, cs:EventMetadataGuid
0x18002d39c  movdqu  [rsp+190h+var_130+8], xmm0
0x18002d3a2  mov     dword ptr [rsp+190h+var_140+4], 21h ; '!'
0x18002d3aa  movups  xmm0, xmmword ptr [r13+0]
0x18002d3af  mov     rax, [rdi+48h]
0x18002d3b3  movdqu  xmmword ptr [rax], xmm0
0x18002d3b7  mov     rax, [rdi+48h]
0x18002d3bb  mov     qword ptr [rbp+90h+var_100+8], rax
0x18002d3bf  mov     eax, dword ptr [rsp+190h+var_158]
0x18002d3c3  add     eax, 10h
0x18002d3c6  mov     dword ptr [rbp+90h+var_F0], eax
0x18002d3c9  mov     ecx, eax
0x18002d3cb  add     rcx, 30h ; '0'
0x18002d3cf  cmp     rcx, 0FFB8h
0x18002d3d6  ja      short loc_18002D3FF
0x18002d3d8  mov     rcx, [rdi+10h]
0x18002d3dc  mov     rax, [rcx]
0x18002d3df  xor     r9d, r9d
0x18002d3e2  xor     r8d, r8d
0x18002d3e5  lea     rdx, [rsp+190h+var_140]
0x18002d3ea  mov     rax, [rax+0C0h]
0x18002d3f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d3f6  test    eax, eax
0x18002d3f8  js      short loc_18002D412
0x18002d3fa  jmp     short loc_18002D3FF
0x18002d3fc  xor     r15d, r15d
0x18002d3ff  inc     r14d
0x18002d402  mov     rcx, [rdi+38h]
0x18002d406  cmp     r14d, [rcx+64h]
0x18002d40a  jb      loc_18002D21D
0x18002d410  xor     eax, eax
0x18002d412  mov     rcx, [rbp+90h+var_50]
0x18002d416  xor     rcx, rsp; StackCookie
0x18002d419  call    __security_check_cookie
0x18002d41e  add     rsp, 158h
0x18002d425  pop     r15
0x18002d427  pop     r14
0x18002d429  pop     r13
0x18002d42b  pop     r12
0x18002d42d  pop     rdi
0x18002d42e  pop     rsi
0x18002d42f  pop     rbx
0x18002d430  pop     rbp
0x18002d431  retn
0x18002d433  mov     eax, 8007000Eh
0x18002d438  jmp     short loc_18002D412
```
