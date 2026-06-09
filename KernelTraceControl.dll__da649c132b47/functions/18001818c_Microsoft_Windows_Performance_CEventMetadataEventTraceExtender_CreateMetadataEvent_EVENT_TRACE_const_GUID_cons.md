# Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CreateMetadataEvent(_EVENT_TRACE const *,_GUID const &,_EVENT_DESCRIPTOR const &)

- ea: `0x18001818c`
- end: `0x1800185f8`
- name: `?CreateMetadataEvent@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEBU_EVENT_TRACE@@AEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@@Z`
- size: `1132`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *__hidden this, const struct _EVENT_TRACE *, const struct _GUID *, const struct _EVENT_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180017b30`

## callees

- `0x180013598`
- `0x18001818c`
- `0x1800185f8`
- `0x18001866c`
- `0x1800188a0`
- `0x180018cf4`
- `0x1800268f4`
- `0x180026e30`
- `0x180026f6c`
- `0x180027910`

## import_xrefs

- `msvcrt!malloc` at `0x18001828a`
- `msvcrt!malloc` at `0x1800184d5`
- `msvcrt!malloc` at `0x18001828a`
- `msvcrt!malloc` at `0x1800184d5`
- `msvcrt!free` at `0x18001827a`
- `msvcrt!free` at `0x1800184c1`
- `msvcrt!free` at `0x18001827a`
- `msvcrt!free` at `0x1800184c1`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CreateMetadataEvent(
        Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *this,
        const struct _EVENT_TRACE *a2,
        const struct _GUID *a3,
        const struct _EVENT_DESCRIPTOR *a4)
{
  __int64 v8; // rbx
  __int64 (__fastcall *v9)(__int16 *, _QWORD, _QWORD, __int64, size_t *); // rax
  int v10; // eax
  __int64 v11; // rbx
  __int64 (__fastcall *v12)(__int16 *, _QWORD, _QWORD, __int64, size_t *); // rax
  unsigned int v13; // ebx
  void *v14; // rax
  __int64 result; // rax
  void *v16; // rbx
  __int64 (__fastcall *v17)(__int16 *, _QWORD, _QWORD, void *, size_t *); // rax
  __int64 v18; // rax
  ULONGLONG Keyword; // rcx
  unsigned int i; // r14d
  __int64 v21; // rcx
  __int64 v22; // rax
  __int64 v23; // r12
  __int64 v24; // rax
  char v25; // bl
  unsigned int v26; // esi
  unsigned int v27; // esi
  __int64 v28; // rax
  __int64 v29; // rbx
  __int64 (__fastcall *v30)(__int16 *, __int64, __int64, unsigned int **); // rax
  int v31; // eax
  unsigned int v32; // ebx
  void *v33; // rax
  __int64 v34; // rbx
  __int64 (__fastcall *v35)(__int16 *, __int64, __int64, unsigned int **); // rax
  size_t Size; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int *v37; // [rsp+38h] [rbp-C8h] BYREF
  const struct _GUID *v38; // [rsp+40h] [rbp-C0h]
  __int64 v39; // [rsp+48h] [rbp-B8h]
  _BYTE v40[16]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v41; // [rsp+60h] [rbp-A0h] BYREF
  __m256i v42; // [rsp+70h] [rbp-90h]
  __int128 v43; // [rsp+90h] [rbp-70h]
  __int128 v44; // [rsp+A0h] [rbp-60h]
  __int64 v45; // [rsp+B0h] [rbp-50h]
  _BYTE v46[8]; // [rsp+C0h] [rbp-40h] BYREF
  void *Block; // [rsp+C8h] [rbp-38h]
  __int64 v48; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v49; // [rsp+E0h] [rbp-20h]
  __int16 v50; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v51[22]; // [rsp+F2h] [rbp-Eh] BYREF
  struct _GUID v52; // [rsp+108h] [rbp+8h]
  __int128 v53; // [rsp+118h] [rbp+18h]

  v39 = -2;
  v38 = a3;
  memset_0(v51, 0, 0x6Eu);
  v50 = 112;
  v52 = *a3;
  v53 = (__int128)*a4;
  LODWORD(Size) = *((_DWORD *)this + 18);
  v8 = *((_QWORD *)this + 8);
  v9 = (__int64 (__fastcall *)(__int16 *, _QWORD, _QWORD, __int64, size_t *))Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((char *)this + 304);
  v10 = v9(&v50, 0, 0, v8, &Size);
  if ( v10 == 1168 )
  {
    *((_QWORD *)&v53 + 1) = 0;
    v11 = *((_QWORD *)this + 8);
    v12 = (__int64 (__fastcall *)(__int16 *, _QWORD, _QWORD, __int64, size_t *))Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((char *)this + 304);
    v10 = v12(&v50, 0, 0, v11, &Size);
  }
  if ( v10 == 122 )
  {
    v13 = Size;
    if ( (unsigned int)Size <= *((_DWORD *)this + 18) )
      return 1;
    if ( *((_QWORD *)this + 8) )
    {
      free(*((void **)this + 8));
      *((_QWORD *)this + 8) = 0;
      v13 = Size;
    }
    v14 = malloc(v13);
    *((_QWORD *)this + 8) = v14;
    if ( !v14 )
      return 2147942414LL;
    *((_DWORD *)this + 18) = v13;
    v16 = v14;
    v17 = (__int64 (__fastcall *)(__int16 *, _QWORD, _QWORD, void *, size_t *))Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((char *)this + 304);
    v10 = v17(&v50, 0, 0, v16, &Size);
  }
  if ( v10 )
    return 1;
  v18 = *((_QWORD *)this + 8);
  if ( !*(_QWORD *)(v18 + 40) )
  {
    Keyword = a4->Keyword;
    if ( Keyword != *(_QWORD *)(v18 + 40) )
      *(_QWORD *)(v18 + 40) = Keyword;
  }
  v37 = (unsigned int *)*((_QWORD *)this + 8);
  Microsoft::Windows::Performance::CTraceEventInfoTransformImpl<Microsoft::Windows::Performance::CTraceEventInfoDelocalizer>::Transform(
    (_DWORD *)this + 24,
    v37,
    Size,
    &v37,
    &Size);
  v41 = *(_OWORD *)&a2->Header.Size;
  v42 = *(__m256i *)&a2->Header.TimeStamp.LowPart;
  v43 = *(_OWORD *)&a2->InstanceId;
  v44 = *(_OWORD *)a2->ParentGuid.Data4;
  HIDWORD(v45) = HIDWORD(*(_QWORD *)&a2->MofLength);
  *(_OWORD *)&v42.m256i_u64[1] = *(_OWORD *)EventMetadataGuid;
  DWORD1(v41) = 32;
  *((_QWORD *)&v44 + 1) = v37;
  LODWORD(v45) = Size;
  if ( (unsigned __int64)(unsigned int)Size + 48 > 0xFFB8
    || (result = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 192LL))(
                   *((_QWORD *)this + 2),
                   &v41,
                   0,
                   0),
        (int)result >= 0) )
  {
    if ( Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((char *)this + 336) )
    {
      for ( i = 0; i < *(_DWORD *)(*((_QWORD *)this + 8) + 100LL); ++i )
      {
        v21 = *((_QWORD *)this + 8);
        if ( (*(_BYTE *)(v21 + 24LL * i + 112) & 1) != 0 )
          continue;
        v22 = *(unsigned int *)(v21 + 24LL * i + 124);
        if ( !(_DWORD)v22 )
          continue;
        v23 = v21 + v22;
        v49 = 7;
        v48 = 0;
        LOWORD(Block) = 0;
        std::wstring::assign(v46, v21 + v22);
        v24 = std::map<_GUID,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState,Performance::lessGuid,std::allocator<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>>>::operator[](
                (char *)this + 40,
                v38);
        v25 = *(_BYTE *)(std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert(
                           v24 + 24,
                           v40,
                           v46)
                       + 8);
        if ( v49 >= 8 )
          operator delete(Block);
        v49 = 7;
        v48 = 0;
        LOWORD(Block) = 0;
        if ( !v25 )
          continue;
        v26 = *((_DWORD *)this + 22);
        if ( v26 < 0x10 )
          v27 = 0;
        else
          v27 = v26 - 16;
        LODWORD(v37) = v27;
        v28 = *((_QWORD *)this + 10);
        if ( v28 )
          v29 = v28 + 16;
        else
          v29 = 0;
        v30 = (__int64 (__fastcall *)(__int16 *, __int64, __int64, unsigned int **))Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((char *)this + 336);
        v31 = v30(&v50, v23, v29, &v37);
        if ( v31 == 122 )
        {
          v32 = (unsigned int)v37;
          if ( (unsigned int)v37 <= v27 )
            continue;
          if ( *((_QWORD *)this + 10) )
          {
            free(*((void **)this + 10));
            *((_QWORD *)this + 10) = 0;
            v32 = (unsigned int)v37;
          }
          v33 = malloc(v32 + 16LL);
          *((_QWORD *)this + 10) = v33;
          if ( !v33 )
            return 2147942414LL;
          *((_DWORD *)this + 22) = v32 + 16;
          v34 = *((_QWORD *)this + 10) + 16LL;
          v35 = (__int64 (__fastcall *)(__int16 *, __int64, __int64, unsigned int **))Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)((char *)this + 336);
          v31 = v35(&v50, v23, v34, &v37);
        }
        if ( !v31 )
        {
          v41 = *(_OWORD *)&a2->Header.Size;
          v42 = *(__m256i *)&a2->Header.TimeStamp.LowPart;
          v43 = *(_OWORD *)&a2->InstanceId;
          v44 = *(_OWORD *)a2->ParentGuid.Data4;
          v45 = *(_QWORD *)&a2->MofLength;
          *(_OWORD *)&v42.m256i_u64[1] = *(_OWORD *)EventMetadataGuid;
          DWORD1(v41) = 33;
          *(struct _GUID *)*((_QWORD *)this + 10) = *v38;
          *((_QWORD *)&v44 + 1) = *((_QWORD *)this + 10);
          LODWORD(v45) = (_DWORD)v37 + 16;
          if ( (unsigned __int64)(unsigned int)((_DWORD)v37 + 16) + 48 <= 0xFFB8 )
          {
            result = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 192LL))(
                       *((_QWORD *)this + 2),
                       &v41,
                       0,
                       0);
            if ( (int)result < 0 )
              return result;
          }
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
0x18001818c  push    rbp
0x18001818e  push    rbx
0x18001818f  push    rsi
0x180018190  push    rdi
0x180018191  push    r12
0x180018193  push    r13
0x180018195  push    r14
0x180018197  push    r15
0x180018199  lea     rbp, [rsp-78h]
0x18001819e  sub     rsp, 178h
0x1800181a5  mov     [rsp+1B0h+var_168], 0FFFFFFFFFFFFFFFEh
0x1800181ae  mov     rax, cs:__security_cookie
0x1800181b5  xor     rax, rsp
0x1800181b8  mov     [rbp+0B0h+var_50], rax
0x1800181bc  mov     r14, r9
0x1800181bf  mov     rbx, r8
0x1800181c2  mov     [rsp+1B0h+var_170], rbx
0x1800181c7  mov     r15, rdx
0x1800181ca  mov     rdi, rcx
0x1800181cd  xor     edx, edx; Val
0x1800181cf  lea     r8d, [rdx+6Eh]; Size
0x1800181d3  lea     rcx, [rbp+0B0h+var_BE]; void *
0x1800181d7  call    memset_0
0x1800181dc  mov     eax, 70h ; 'p'
0x1800181e1  mov     [rbp+0B0h+var_C0], ax
0x1800181e5  movups  xmm0, xmmword ptr [rbx]
0x1800181e8  movdqu  [rbp+0B0h+var_A8], xmm0
0x1800181ed  movups  xmm1, xmmword ptr [r14]
0x1800181f1  movdqu  [rbp+0B0h+var_98], xmm1
0x1800181f6  mov     eax, [rdi+48h]
0x1800181f9  mov     dword ptr [rsp+1B0h+Size], eax
0x1800181fd  mov     rbx, [rdi+40h]
0x180018201  lea     rsi, [rdi+130h]
0x180018208  mov     rcx, rsi
0x18001820b  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x180018210  lea     rcx, [rsp+1B0h+Size]
0x180018215  mov     [rsp+1B0h+var_190], rcx
0x18001821a  mov     r9, rbx
0x18001821d  xor     r8d, r8d
0x180018220  xor     edx, edx
0x180018222  lea     rcx, [rbp+0B0h+var_C0]
0x180018226  call    cs:__guard_dispatch_icall_fptr
0x18001822c  xor     r12d, r12d
0x18001822f  cmp     eax, 490h
0x180018234  jnz     short loc_180018262
0x180018236  mov     qword ptr [rbp+0B0h+var_98+8], r12
0x18001823a  mov     rbx, [rdi+40h]
0x18001823e  mov     rcx, rsi
0x180018241  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x180018246  lea     rcx, [rsp+1B0h+Size]
0x18001824b  mov     [rsp+1B0h+var_190], rcx
0x180018250  mov     r9, rbx
0x180018253  xor     r8d, r8d
0x180018256  xor     edx, edx
0x180018258  lea     rcx, [rbp+0B0h+var_C0]
0x18001825c  call    cs:__guard_dispatch_icall_fptr
0x180018262  cmp     eax, 7Ah ; 'z'
0x180018265  jnz     short loc_1800182CD
0x180018267  mov     ebx, dword ptr [rsp+1B0h+Size]
0x18001826b  cmp     ebx, [rdi+48h]
0x18001826e  jbe     short loc_1800182D3
0x180018270  cmp     [rdi+40h], r12
0x180018274  jz      short loc_180018288
0x180018276  mov     rcx, [rdi+40h]; Block
0x18001827a  call    cs:__imp_free
0x180018280  mov     [rdi+40h], r12
0x180018284  mov     ebx, dword ptr [rsp+1B0h+Size]
0x180018288  mov     ecx, ebx; Size
0x18001828a  call    cs:__imp_malloc
0x180018290  mov     [rdi+40h], rax
0x180018294  test    rax, rax
0x180018297  jnz     short loc_1800182A3
0x180018299  mov     eax, 8007000Eh
0x18001829e  jmp     loc_1800185D8
0x1800182a3  mov     [rdi+48h], ebx
0x1800182a6  mov     rbx, rax
0x1800182a9  mov     rcx, rsi
0x1800182ac  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x1800182b1  lea     rcx, [rsp+1B0h+Size]
0x1800182b6  mov     [rsp+1B0h+var_190], rcx
0x1800182bb  mov     r9, rbx
0x1800182be  xor     r8d, r8d
0x1800182c1  xor     edx, edx
0x1800182c3  lea     rcx, [rbp+0B0h+var_C0]
0x1800182c7  call    cs:__guard_dispatch_icall_fptr
0x1800182cd  xor     esi, esi
0x1800182cf  test    eax, eax
0x1800182d1  jz      short loc_1800182DD
0x1800182d3  mov     eax, 1
0x1800182d8  jmp     loc_1800185D8
0x1800182dd  mov     rax, [rdi+40h]
0x1800182e1  cmp     [rax+28h], rsi
0x1800182e5  jnz     short loc_1800182F5
0x1800182e7  mov     rcx, [r14+8]
0x1800182eb  cmp     rcx, [rax+28h]
0x1800182ef  jz      short loc_1800182F5
0x1800182f1  mov     [rax+28h], rcx
0x1800182f5  mov     rdx, [rdi+40h]
0x1800182f9  mov     [rsp+1B0h+var_178], rdx
0x1800182fe  lea     rcx, [rdi+60h]
0x180018302  lea     rax, [rsp+1B0h+Size]
0x180018307  mov     [rsp+1B0h+var_190], rax
0x18001830c  lea     r9, [rsp+1B0h+var_178]
0x180018311  mov     r8d, dword ptr [rsp+1B0h+Size]
0x180018316  call    ?Transform@?$CTraceEventInfoTransformImpl@VCTraceEventInfoDelocalizer@Performance@Windows@Microsoft@@@Performance@Windows@Microsoft@@IEAAJPEBU_TRACE_EVENT_INFO@@KPEAPEBU5@PEAK@Z; Microsoft::Windows::Performance::CTraceEventInfoTransformImpl<Microsoft::Windows::Performance::CTraceEventInfoDelocalizer>::Transform(_TRACE_EVENT_INFO const *,ulong,_TRACE_EVENT_INFO const * *,ulong *)
0x18001831b  movups  xmm0, xmmword ptr [r15]
0x18001831f  movaps  [rsp+1B0h+var_150], xmm0
0x180018324  movups  xmm1, xmmword ptr [r15+10h]
0x180018329  movaps  [rsp+1B0h+var_140], xmm1
0x18001832e  movups  xmm0, xmmword ptr [r15+20h]
0x180018333  movaps  [rbp+0B0h+var_130], xmm0
0x180018337  movups  xmm1, xmmword ptr [r15+30h]
0x18001833c  movaps  [rbp+0B0h+var_120], xmm1
0x180018340  movups  xmm0, xmmword ptr [r15+40h]
0x180018345  movaps  [rbp+0B0h+var_110], xmm0
0x180018349  movsd   xmm1, qword ptr [r15+50h]
0x18001834f  movsd   [rbp+0B0h+var_100], xmm1
0x180018354  movups  xmm0, xmmword ptr cs:EventMetadataGuid
0x18001835b  movdqu  [rsp+1B0h+var_140+8], xmm0
0x180018361  mov     dword ptr [rsp+1B0h+var_150+4], 20h ; ' '
0x180018369  mov     rax, [rsp+1B0h+var_178]
0x18001836e  mov     qword ptr [rbp+0B0h+var_110+8], rax
0x180018372  mov     eax, dword ptr [rsp+1B0h+Size]
0x180018376  mov     dword ptr [rbp+0B0h+var_100], eax
0x180018379  lea     rcx, [rax+30h]
0x18001837d  cmp     rcx, 0FFB8h
0x180018384  ja      short loc_1800183AD
0x180018386  mov     rcx, [rdi+10h]
0x18001838a  mov     rax, [rcx]
0x18001838d  xor     r9d, r9d
0x180018390  xor     r8d, r8d
0x180018393  lea     rdx, [rsp+1B0h+var_150]
0x180018398  mov     rax, [rax+0C0h]
0x18001839f  call    cs:__guard_dispatch_icall_fptr
0x1800183a5  test    eax, eax
0x1800183a7  js      loc_1800185D8
0x1800183ad  lea     r13, [rdi+150h]
0x1800183b4  mov     rcx, r13
0x1800183b7  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x1800183bc  test    rax, rax
0x1800183bf  jz      loc_1800185D6
0x1800183c5  mov     r14d, esi
0x1800183c8  mov     rax, [rdi+40h]
0x1800183cc  cmp     [rax+64h], esi
0x1800183cf  jbe     loc_1800185D6
0x1800183d5  mov     rcx, [rdi+40h]
0x1800183d9  mov     eax, r14d
0x1800183dc  lea     rdx, [rax+rax*2]
0x1800183e0  test    byte ptr [rcx+rdx*8+70h], 1
0x1800183e5  jnz     loc_1800185C5
0x1800183eb  mov     eax, [rcx+rdx*8+7Ch]
0x1800183ef  test    eax, eax
0x1800183f1  jz      loc_1800185C5
0x1800183f7  lea     r12, [rcx+rax]
0x1800183fb  mov     [rbp+0B0h+var_D0], 7
0x180018403  mov     [rbp+0B0h+var_D8], rsi
0x180018407  mov     word ptr [rbp+0B0h+Block], si
0x18001840b  mov     rdx, r12
0x18001840e  lea     rcx, [rbp+0B0h+var_F0]
0x180018412  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180018417  nop
0x180018418  lea     rcx, [rdi+28h]
0x18001841c  mov     rdx, [rsp+1B0h+var_170]
0x180018421  call    ??A?$map@U_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@UlessGuid@4@V?$allocator@U?$pair@$$CBU_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@std@@@std@@@std@@QEAAAEAUCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEBU_GUID@@@Z; std::map<_GUID,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState,Performance::lessGuid,std::allocator<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>>>::operator[](_GUID const &)
0x180018426  lea     rcx, [rax+18h]
0x18001842a  lea     r8, [rbp+0B0h+var_F0]
0x18001842e  lea     rdx, [rsp+1B0h+var_160]
0x180018433  call    ?insert@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@Viterator@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@@2@$0A@@std@@@std@@_N@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@2@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert(std::wstring const &)
0x180018438  mov     bl, [rax+8]
0x18001843b  cmp     [rbp+0B0h+var_D0], 8
0x180018440  jb      short loc_18001844B
0x180018442  mov     rcx, [rbp+0B0h+Block]; Block
0x180018446  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001844b  mov     [rbp+0B0h+var_D0], 7
0x180018453  mov     [rbp+0B0h+var_D8], rsi
0x180018457  mov     word ptr [rbp+0B0h+Block], si
0x18001845b  test    bl, bl
0x18001845d  jz      loc_1800185C5
0x180018463  mov     esi, [rdi+58h]
0x180018466  cmp     esi, 10h
0x180018469  jb      short loc_180018470
0x18001846b  add     esi, 0FFFFFFF0h
0x18001846e  jmp     short loc_180018472
0x180018470  xor     esi, esi
0x180018472  mov     dword ptr [rsp+1B0h+var_178], esi
0x180018476  mov     rax, [rdi+50h]
0x18001847a  test    rax, rax
0x18001847d  jz      short loc_180018485
0x18001847f  lea     rbx, [rax+10h]
0x180018483  jmp     short loc_180018487
0x180018485  xor     ebx, ebx
0x180018487  mov     rcx, r13
0x18001848a  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18001848f  lea     r9, [rsp+1B0h+var_178]
0x180018494  mov     r8, rbx
0x180018497  mov     rdx, r12
0x18001849a  lea     rcx, [rbp+0B0h+var_C0]
0x18001849e  call    cs:__guard_dispatch_icall_fptr
0x1800184a4  cmp     eax, 7Ah ; 'z'
0x1800184a7  jnz     short loc_180018515
0x1800184a9  mov     ebx, dword ptr [rsp+1B0h+var_178]
0x1800184ad  cmp     ebx, esi
0x1800184af  jbe     loc_1800185C3
0x1800184b5  xor     esi, esi
0x1800184b7  cmp     [rdi+50h], rsi
0x1800184bb  jz      short loc_1800184CF
0x1800184bd  mov     rcx, [rdi+50h]; Block
0x1800184c1  call    cs:__imp_free
0x1800184c7  mov     [rdi+50h], rsi
0x1800184cb  mov     ebx, dword ptr [rsp+1B0h+var_178]
0x1800184cf  mov     ecx, ebx
0x1800184d1  add     rcx, 10h; Size
0x1800184d5  call    cs:__imp_malloc
0x1800184db  mov     [rdi+50h], rax
0x1800184df  test    rax, rax
0x1800184e2  jz      loc_180018299
0x1800184e8  lea     eax, [rbx+10h]
0x1800184eb  mov     [rdi+58h], eax
0x1800184ee  mov     rbx, [rdi+50h]
0x1800184f2  add     rbx, 10h
0x1800184f6  mov     rcx, r13
0x1800184f9  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x1800184fe  lea     r9, [rsp+1B0h+var_178]
0x180018503  mov     r8, rbx
0x180018506  mov     rdx, r12
0x180018509  lea     rcx, [rbp+0B0h+var_C0]
0x18001850d  call    cs:__guard_dispatch_icall_fptr
0x180018513  jmp     short loc_180018517
0x180018515  xor     esi, esi
0x180018517  test    eax, eax
0x180018519  jnz     loc_1800185C5
0x18001851f  movups  xmm0, xmmword ptr [r15]
0x180018523  movaps  [rsp+1B0h+var_150], xmm0
0x180018528  movups  xmm1, xmmword ptr [r15+10h]
0x18001852d  movaps  [rsp+1B0h+var_140], xmm1
0x180018532  movups  xmm0, xmmword ptr [r15+20h]
0x180018537  movaps  [rbp+0B0h+var_130], xmm0
0x18001853b  movups  xmm1, xmmword ptr [r15+30h]
0x180018540  movaps  [rbp+0B0h+var_120], xmm1
0x180018544  movups  xmm0, xmmword ptr [r15+40h]
0x180018549  movaps  [rbp+0B0h+var_110], xmm0
0x18001854d  movsd   xmm1, qword ptr [r15+50h]
0x180018553  movsd   [rbp+0B0h+var_100], xmm1
0x180018558  movups  xmm0, xmmword ptr cs:EventMetadataGuid
0x18001855f  movdqu  [rsp+1B0h+var_140+8], xmm0
0x180018565  mov     dword ptr [rsp+1B0h+var_150+4], 21h ; '!'
0x18001856d  mov     rax, [rdi+50h]
0x180018571  mov     rcx, [rsp+1B0h+var_170]
0x180018576  movups  xmm0, xmmword ptr [rcx]
0x180018579  movdqu  xmmword ptr [rax], xmm0
0x18001857d  mov     rax, [rdi+50h]
0x180018581  mov     qword ptr [rbp+0B0h+var_110+8], rax
0x180018585  mov     eax, dword ptr [rsp+1B0h+var_178]
0x180018589  add     eax, 10h
0x18001858c  mov     dword ptr [rbp+0B0h+var_100], eax
0x18001858f  mov     ecx, eax
0x180018591  add     rcx, 30h ; '0'
0x180018595  cmp     rcx, 0FFB8h
0x18001859c  ja      short loc_1800185C5
0x18001859e  mov     rcx, [rdi+10h]
0x1800185a2  mov     rax, [rcx]
0x1800185a5  xor     r9d, r9d
0x1800185a8  xor     r8d, r8d
0x1800185ab  lea     rdx, [rsp+1B0h+var_150]
0x1800185b0  mov     rax, [rax+0C0h]
0x1800185b7  call    cs:__guard_dispatch_icall_fptr
0x1800185bd  test    eax, eax
0x1800185bf  js      short loc_1800185D8
0x1800185c1  jmp     short loc_1800185C5
0x1800185c3  xor     esi, esi
0x1800185c5  inc     r14d
0x1800185c8  mov     rax, [rdi+40h]
0x1800185cc  cmp     r14d, [rax+64h]
0x1800185d0  jb      loc_1800183D5
0x1800185d6  xor     eax, eax
0x1800185d8  mov     rcx, [rbp+0B0h+var_50]
0x1800185dc  xor     rcx, rsp; StackCookie
0x1800185df  call    __security_check_cookie
0x1800185e4  add     rsp, 178h
0x1800185eb  pop     r15
0x1800185ed  pop     r14
0x1800185ef  pop     r13
0x1800185f1  pop     r12
0x1800185f3  pop     rdi
0x1800185f4  pop     rsi
0x1800185f5  pop     rbx
0x1800185f6  pop     rbp
0x1800185f7  retn
```
