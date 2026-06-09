# Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CreateMetadataEvent(_EVENT_TRACE const *,_GUID const &,_EVENT_DESCRIPTOR const &)

- ea: `0x18002fed4`
- end: `0x1800302f7`
- name: `?CreateMetadataEvent@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@AEAAJPEBU_EVENT_TRACE@@AEBU_GUID@@AEBU_EVENT_DESCRIPTOR@@@Z`
- size: `1059`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *__hidden this, const struct _EVENT_TRACE *, const struct _GUID *, const struct _EVENT_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18003f890`

## callees

- `0x180009b40`
- `0x1800259c4`
- `0x180025ab8`
- `0x18002fed4`
- `0x180030300`
- `0x180038438`
- `0x18004ece0`
- `0x18004f964`
- `0x18007d0a8`
- `0x18008c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002ffbd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800301cd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18002ffbd`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800301cd`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002ffd1`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800301e5`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18002ffd1`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800301e5`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CreateMetadataEvent(
        Microsoft::Windows::Performance::CEventMetadataEventTraceExtender *this,
        const struct _EVENT_TRACE *a2,
        const struct _GUID *a3,
        const struct _EVENT_DESCRIPTOR *a4)
{
  __int64 (__fastcall *v8)(__int16 *, _QWORD, _QWORD, _QWORD, size_t *); // rax
  int v9; // eax
  __int64 (__fastcall *v10)(__int16 *, _QWORD, _QWORD, _QWORD, size_t *); // rax
  unsigned int v11; // eax
  void *v12; // rcx
  void *v13; // rax
  __int64 (__fastcall *v14)(__int16 *, _QWORD, _QWORD, _QWORD, size_t *); // rax
  __int64 result; // rax
  __int64 v16; // rcx
  ULONGLONG Keyword; // rax
  __int64 i; // rsi
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // r12
  __int64 v22; // rbx
  unsigned int v23; // ecx
  unsigned int v24; // ebx
  __int64 (__fastcall *v25)(__int16 *, __int64, __int64, _QWORD *); // rax
  int v26; // eax
  unsigned int v27; // eax
  void *v28; // rcx
  void *v29; // rax
  __int64 (__fastcall *v30)(__int16 *, __int64, __int64, _QWORD *); // rax
  size_t Size; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v32[2]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v33[16]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v34[24]; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v35; // [rsp+70h] [rbp-90h] BYREF
  __m256i v36; // [rsp+80h] [rbp-80h]
  __int128 v37; // [rsp+A0h] [rbp-60h]
  __int128 v38; // [rsp+B0h] [rbp-50h]
  __int64 v39; // [rsp+C0h] [rbp-40h]
  __int16 v40; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v41[22]; // [rsp+D2h] [rbp-2Eh] BYREF
  struct _GUID v42; // [rsp+E8h] [rbp-18h]
  struct _EVENT_DESCRIPTOR v43; // [rsp+F8h] [rbp-8h]
  _BYTE v44[32]; // [rsp+140h] [rbp+40h] BYREF

  v32[1] = -2;
  memset_0(v41, 0, 0x6Eu);
  v40 = 112;
  v42 = *a3;
  v43 = *a4;
  LODWORD(Size) = *((_DWORD *)this + 16);
  v8 = (__int64 (__fastcall *)(__int16 *, _QWORD, _QWORD, _QWORD, size_t *))Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,unsigned short const *,unsigned long),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,unsigned short const *,unsigned long)((char *)this + 288);
  v9 = v8(&v40, 0, 0, *((_QWORD *)this + 7), &Size);
  if ( v9 == 1168 )
  {
    v43.Keyword = 0;
    v10 = (__int64 (__fastcall *)(__int16 *, _QWORD, _QWORD, _QWORD, size_t *))Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,unsigned short const *,unsigned long),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,unsigned short const *,unsigned long)((char *)this + 288);
    v9 = v10(&v40, 0, 0, *((_QWORD *)this + 7), &Size);
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
    v14 = (__int64 (__fastcall *)(__int16 *, _QWORD, _QWORD, _QWORD, size_t *))Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,unsigned short const *,unsigned long),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,unsigned short const *,unsigned long)((char *)this + 288);
    v9 = v14(&v40, 0, 0, *((_QWORD *)this + 7), &Size);
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
  v32[0] = *((_QWORD *)this + 7);
  Microsoft::Windows::Performance::CTraceEventInfoTransformImpl<Microsoft::Windows::Performance::CTraceEventInfoDelocalizer>::Transform(
    (_DWORD)this + 88,
    v32[0],
    Size,
    (unsigned int)v32,
    (__int64)&Size);
  v35 = *(_OWORD *)&a2->Header.Size;
  v36 = *(__m256i *)&a2->Header.TimeStamp.LowPart;
  v37 = *(_OWORD *)&a2->InstanceId;
  v38 = *(_OWORD *)a2->ParentGuid.Data4;
  HIDWORD(v39) = HIDWORD(*(_QWORD *)&a2->MofLength);
  *(_OWORD *)&v36.m256i_u64[1] = EventMetadataGuid;
  DWORD1(v35) = 32;
  *((_QWORD *)&v38 + 1) = v32[0];
  LODWORD(v39) = Size;
  if ( (unsigned __int64)(unsigned int)Size + 48 > 0xFFB8
    || (result = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD, _QWORD))(**((_QWORD **)this + 2) + 192LL))(
                   *((_QWORD *)this + 2),
                   &v35,
                   0,
                   0),
        (int)result >= 0) )
  {
    if ( Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,unsigned short const *,unsigned long),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,unsigned short const *,unsigned long)((char *)this + 320) )
    {
      for ( i = 0; ; i = (unsigned int)(i + 1) )
      {
        v19 = *((_QWORD *)this + 7);
        if ( (unsigned int)i >= *(_DWORD *)(v19 + 100) )
          return 0;
        if ( (*(_BYTE *)(v19 + 24 * i + 112) & 1) == 0 )
        {
          v20 = *(unsigned int *)(v19 + 24 * i + 124);
          if ( (_DWORD)v20 )
          {
            v21 = v19 + v20;
            v22 = *(_QWORD *)std::map<_GUID,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState,Performance::lessGuid,std::allocator<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>>>::_Try_emplace<_GUID const &,>(
                               (char *)this + 40,
                               v33,
                               a3);
            std::wstring::wstring(v44, v21);
            LOBYTE(v22) = *(_BYTE *)(std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
                                       v22 + 64,
                                       v34,
                                       v44)
                                   + 8);
            std::wstring::~wstring(v44);
            if ( (_BYTE)v22 )
            {
              v23 = *((_DWORD *)this + 20);
              v24 = v23 - 16;
              if ( v23 < 0x10 )
                v24 = 0;
              LODWORD(v32[0]) = v24;
              v25 = (__int64 (__fastcall *)(__int16 *, __int64, __int64, _QWORD *))Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,unsigned short const *,unsigned long),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,unsigned short const *,unsigned long)((char *)this + 320);
              v26 = v25(&v40, v21, (*((_QWORD *)this + 9) + 16LL) & -(__int64)(*((_QWORD *)this + 9) != 0), v32);
              if ( v26 == 122 )
              {
                v27 = v32[0];
                if ( LODWORD(v32[0]) <= v24 )
                  continue;
                v28 = (void *)*((_QWORD *)this + 9);
                if ( v28 )
                {
                  free(v28);
                  *((_QWORD *)this + 9) = 0;
                  v27 = v32[0];
                }
                v29 = malloc(v27 + 16LL);
                *((_QWORD *)this + 9) = v29;
                if ( !v29 )
                  return 2147942414LL;
                *((_DWORD *)this + 20) = LODWORD(v32[0]) + 16;
                v30 = (__int64 (__fastcall *)(__int16 *, __int64, __int64, _QWORD *))Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,unsigned short const *,unsigned long),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,unsigned short const *,unsigned long)((char *)this + 320);
                v26 = v30(&v40, v21, *((_QWORD *)this + 9) + 16LL, v32);
              }
              if ( !v26 )
              {
                v35 = *(_OWORD *)&a2->Header.Size;
                v36 = *(__m256i *)&a2->Header.TimeStamp.LowPart;
                v37 = *(_OWORD *)&a2->InstanceId;
                v38 = *(_OWORD *)a2->ParentGuid.Data4;
                v39 = *(_QWORD *)&a2->MofLength;
                *(_OWORD *)&v36.m256i_u64[1] = EventMetadataGuid;
                DWORD1(v35) = 33;
                *(struct _GUID *)*((_QWORD *)this + 9) = *a3;
                *((_QWORD *)&v38 + 1) = *((_QWORD *)this + 9);
                LODWORD(v39) = LODWORD(v32[0]) + 16;
                if ( (unsigned __int64)(unsigned int)(LODWORD(v32[0]) + 16) + 48 <= 0xFFB8 )
                {
                  result = (*(__int64 (__fastcall **)(_QWORD, __int128 *, _QWORD, _QWORD))(**((_QWORD **)this + 2)
                                                                                         + 192LL))(
                             *((_QWORD *)this + 2),
                             &v35,
                             0,
                             0);
                  if ( (int)result < 0 )
                    return result;
                }
              }
            }
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
0x18002fed4  push    rbp
0x18002fed6  push    rbx
0x18002fed7  push    rsi
0x18002fed8  push    rdi
0x18002fed9  push    r12
0x18002fedb  push    r13
0x18002fedd  push    r14
0x18002fedf  push    r15
0x18002fee1  lea     rbp, [rsp-78h]
0x18002fee6  sub     rsp, 178h
0x18002feed  mov     [rsp+1B0h+var_170], 0FFFFFFFFFFFFFFFEh
0x18002fef6  mov     rax, cs:__security_cookie
0x18002fefd  xor     rax, rsp
0x18002ff00  mov     [rbp+0B0h+var_50], rax
0x18002ff04  mov     rsi, r9
0x18002ff07  mov     r13, r8
0x18002ff0a  mov     r14, rdx
0x18002ff0d  mov     rdi, rcx
0x18002ff10  xor     edx, edx; Val
0x18002ff12  lea     r8d, [rdx+6Eh]; Size
0x18002ff16  lea     rcx, [rbp+0B0h+var_DE]; void *
0x18002ff1a  call    memset_0
0x18002ff1f  mov     eax, 70h ; 'p'
0x18002ff24  mov     [rbp+0B0h+var_E0], ax
0x18002ff28  movups  xmm0, xmmword ptr [r13+0]
0x18002ff2d  movdqu  [rbp+0B0h+var_C8], xmm0
0x18002ff32  mov     rax, [rsi]
0x18002ff35  mov     [rbp+0B0h+var_B8], rax
0x18002ff39  mov     rax, [rsi+8]
0x18002ff3d  mov     [rbp+0B0h+var_B0], rax
0x18002ff41  mov     eax, [rdi+40h]
0x18002ff44  mov     dword ptr [rsp+1B0h+Size], eax
0x18002ff48  lea     rbx, [rdi+120h]
0x18002ff4f  mov     rcx, rbx
0x18002ff52  call    ??B?$CDelayLoadedImport@P6APEAXPEAXPEBGK@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6APEAXPEAXPEBGK@ZXZ; Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,ushort const *,ulong),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,ushort const *,ulong)(void)
0x18002ff57  lea     rcx, [rsp+1B0h+Size]
0x18002ff5c  mov     [rsp+1B0h+var_190], rcx
0x18002ff61  mov     r9, [rdi+38h]
0x18002ff65  xor     r8d, r8d
0x18002ff68  xor     edx, edx
0x18002ff6a  lea     rcx, [rbp+0B0h+var_E0]
0x18002ff6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff73  cmp     eax, 490h
0x18002ff78  jnz     short loc_18002FFA6
0x18002ff7a  mov     [rbp+0B0h+var_B0], 0
0x18002ff82  mov     rcx, rbx
0x18002ff85  call    ??B?$CDelayLoadedImport@P6APEAXPEAXPEBGK@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6APEAXPEAXPEBGK@ZXZ; Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,ushort const *,ulong),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,ushort const *,ulong)(void)
0x18002ff8a  lea     rcx, [rsp+1B0h+Size]
0x18002ff8f  mov     [rsp+1B0h+var_190], rcx
0x18002ff94  mov     r9, [rdi+38h]
0x18002ff98  xor     r8d, r8d
0x18002ff9b  xor     edx, edx
0x18002ff9d  lea     rcx, [rbp+0B0h+var_E0]
0x18002ffa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ffa6  cmp     eax, 7Ah ; 'z'
0x18002ffa9  jnz     short loc_18003000F
0x18002ffab  mov     eax, dword ptr [rsp+1B0h+Size]
0x18002ffaf  cmp     eax, [rdi+40h]
0x18002ffb2  jbe     short loc_180030013
0x18002ffb4  mov     rcx, [rdi+38h]; Block
0x18002ffb8  test    rcx, rcx
0x18002ffbb  jz      short loc_18002FFCF
0x18002ffbd  call    cs:__imp_free
0x18002ffc3  mov     qword ptr [rdi+38h], 0
0x18002ffcb  mov     eax, dword ptr [rsp+1B0h+Size]
0x18002ffcf  mov     ecx, eax; Size
0x18002ffd1  call    cs:__imp_malloc
0x18002ffd7  mov     [rdi+38h], rax
0x18002ffdb  test    rax, rax
0x18002ffde  jz      loc_1800302CE
0x18002ffe4  mov     eax, dword ptr [rsp+1B0h+Size]
0x18002ffe8  mov     [rdi+40h], eax
0x18002ffeb  mov     rcx, rbx
0x18002ffee  call    ??B?$CDelayLoadedImport@P6APEAXPEAXPEBGK@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6APEAXPEAXPEBGK@ZXZ; Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,ushort const *,ulong),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,ushort const *,ulong)(void)
0x18002fff3  lea     rcx, [rsp+1B0h+Size]
0x18002fff8  mov     [rsp+1B0h+var_190], rcx
0x18002fffd  mov     r9, [rdi+38h]
0x180030001  xor     r8d, r8d
0x180030004  xor     edx, edx
0x180030006  lea     rcx, [rbp+0B0h+var_E0]
0x18003000a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003000f  test    eax, eax
0x180030011  jz      short loc_18003001D
0x180030013  mov     eax, 1
0x180030018  jmp     loc_1800302D7
0x18003001d  mov     rcx, [rdi+38h]
0x180030021  cmp     qword ptr [rcx+28h], 0
0x180030026  jnz     short loc_180030035
0x180030028  mov     rax, [rsi+8]
0x18003002c  test    rax, rax
0x18003002f  jz      short loc_180030035
0x180030031  mov     [rcx+28h], rax
0x180030035  mov     rdx, [rdi+38h]
0x180030039  mov     [rsp+1B0h+var_178], rdx
0x18003003e  lea     rcx, [rdi+58h]
0x180030042  lea     rax, [rsp+1B0h+Size]
0x180030047  mov     [rsp+1B0h+var_190], rax
0x18003004c  lea     r9, [rsp+1B0h+var_178]
0x180030051  mov     r8d, dword ptr [rsp+1B0h+Size]
0x180030056  call    ?Transform@?$CTraceEventInfoTransformImpl@VCTraceEventInfoDelocalizer@Performance@Windows@Microsoft@@@Performance@Windows@Microsoft@@IEAAJPEBU_TRACE_EVENT_INFO@@KPEAPEBU5@PEAK@Z; Microsoft::Windows::Performance::CTraceEventInfoTransformImpl<Microsoft::Windows::Performance::CTraceEventInfoDelocalizer>::Transform(_TRACE_EVENT_INFO const *,ulong,_TRACE_EVENT_INFO const * *,ulong *)
0x18003005b  movups  xmm0, xmmword ptr [r14]
0x18003005f  movaps  [rsp+1B0h+var_140], xmm0
0x180030064  movups  xmm1, xmmword ptr [r14+10h]
0x180030069  movaps  [rbp+0B0h+var_130], xmm1
0x18003006d  movups  xmm0, xmmword ptr [r14+20h]
0x180030072  movaps  [rbp+0B0h+var_120], xmm0
0x180030076  movups  xmm1, xmmword ptr [r14+30h]
0x18003007b  movaps  [rbp+0B0h+var_110], xmm1
0x18003007f  movups  xmm0, xmmword ptr [r14+40h]
0x180030084  movaps  [rbp+0B0h+var_100], xmm0
0x180030088  movsd   xmm1, qword ptr [r14+50h]
0x18003008e  movsd   [rbp+0B0h+var_F0], xmm1
0x180030093  movups  xmm0, cs:EventMetadataGuid
0x18003009a  movdqu  [rbp+0B0h+var_130+8], xmm0
0x18003009f  mov     dword ptr [rsp+1B0h+var_140+4], 20h ; ' '
0x1800300a7  mov     rax, [rsp+1B0h+var_178]
0x1800300ac  mov     qword ptr [rbp+0B0h+var_100+8], rax
0x1800300b0  mov     eax, dword ptr [rsp+1B0h+Size]
0x1800300b4  mov     dword ptr [rbp+0B0h+var_F0], eax
0x1800300b7  lea     rcx, [rax+30h]
0x1800300bb  cmp     rcx, 0FFB8h
0x1800300c2  ja      short loc_1800300EA
0x1800300c4  mov     rcx, [rdi+10h]
0x1800300c8  mov     rax, [rcx]
0x1800300cb  xor     r9d, r9d
0x1800300ce  xor     r8d, r8d
0x1800300d1  lea     rdx, [rsp+1B0h+var_140]
0x1800300d6  mov     rax, [rax+0C0h]
0x1800300dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800300e2  test    eax, eax
0x1800300e4  js      loc_1800302D7
0x1800300ea  lea     r15, [rdi+140h]
0x1800300f1  mov     rcx, r15
0x1800300f4  call    ??B?$CDelayLoadedImport@P6APEAXPEAXPEBGK@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6APEAXPEAXPEBGK@ZXZ; Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,ushort const *,ulong),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,ushort const *,ulong)(void)
0x1800300f9  test    rax, rax
0x1800300fc  jz      loc_1800302D5
0x180030102  xor     esi, esi
0x180030104  mov     rcx, [rdi+38h]
0x180030108  cmp     esi, [rcx+64h]
0x18003010b  jnb     loc_1800302D5
0x180030111  lea     rdx, [rsi+rsi*2]
0x180030115  test    byte ptr [rcx+rdx*8+70h], 1
0x18003011a  jnz     loc_1800302C7
0x180030120  mov     eax, [rcx+rdx*8+7Ch]
0x180030124  test    eax, eax
0x180030126  jz      loc_1800302C7
0x18003012c  lea     r12, [rcx+rax]
0x180030130  lea     rcx, [rdi+28h]
0x180030134  mov     r8, r13
0x180030137  lea     rdx, [rsp+1B0h+var_168]
0x18003013c  call    ??$_Try_emplace@AEBU_GUID@@$$V@?$map@U_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@UlessGuid@4@V?$allocator@U?$pair@$$CBU_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@std@@@std@@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@UCProviderInfoState@CEventMetadataEventTraceExtender@Performance@Windows@Microsoft@@@std@@PEAX@std@@_N@1@AEBU_GUID@@@Z; std::map<_GUID,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState,Performance::lessGuid,std::allocator<std::pair<_GUID const,Microsoft::Windows::Performance::CEventMetadataEventTraceExtender::CProviderInfoState>>>::_Try_emplace<_GUID const &,>(_GUID const &)
0x180030141  mov     rbx, [rax]
0x180030144  mov     rdx, r12
0x180030147  lea     rcx, [rbp+0B0h+var_70]
0x18003014b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180030150  nop
0x180030151  lea     r8, [rbp+0B0h+var_70]
0x180030155  lea     rdx, [rsp+1B0h+var_158]
0x18003015a  lea     rcx, [rbx+40h]
0x18003015e  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@_N@1@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring &&)
0x180030163  mov     bl, [rax+8]
0x180030166  lea     rcx, [rbp+0B0h+var_70]
0x18003016a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003016f  test    bl, bl
0x180030171  jz      loc_1800302C7
0x180030177  mov     ecx, [rdi+50h]
0x18003017a  lea     ebx, [rcx-10h]
0x18003017d  xor     eax, eax
0x18003017f  cmp     ecx, 10h
0x180030182  cmovb   ebx, eax
0x180030185  mov     dword ptr [rsp+1B0h+var_178], ebx
0x180030189  mov     rcx, r15
0x18003018c  call    ??B?$CDelayLoadedImport@P6APEAXPEAXPEBGK@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6APEAXPEAXPEBGK@ZXZ; Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,ushort const *,ulong),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,ushort const *,ulong)(void)
0x180030191  mov     rcx, [rdi+48h]
0x180030195  lea     rdx, [rcx+10h]
0x180030199  neg     rcx
0x18003019c  sbb     r8, r8
0x18003019f  and     r8, rdx
0x1800301a2  lea     r9, [rsp+1B0h+var_178]
0x1800301a7  mov     rdx, r12
0x1800301aa  lea     rcx, [rbp+0B0h+var_E0]
0x1800301ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800301b3  cmp     eax, 7Ah ; 'z'
0x1800301b6  jnz     short loc_180030223
0x1800301b8  mov     eax, dword ptr [rsp+1B0h+var_178]
0x1800301bc  cmp     eax, ebx
0x1800301be  jbe     loc_1800302C7
0x1800301c4  mov     rcx, [rdi+48h]; Block
0x1800301c8  test    rcx, rcx
0x1800301cb  jz      short loc_1800301DF
0x1800301cd  call    cs:__imp_free
0x1800301d3  mov     qword ptr [rdi+48h], 0
0x1800301db  mov     eax, dword ptr [rsp+1B0h+var_178]
0x1800301df  mov     ecx, eax
0x1800301e1  add     rcx, 10h; Size
0x1800301e5  call    cs:__imp_malloc
0x1800301eb  mov     [rdi+48h], rax
0x1800301ef  test    rax, rax
0x1800301f2  jz      loc_1800302CE
0x1800301f8  mov     eax, dword ptr [rsp+1B0h+var_178]
0x1800301fc  add     eax, 10h
0x1800301ff  mov     [rdi+50h], eax
0x180030202  mov     rcx, r15
0x180030205  call    ??B?$CDelayLoadedImport@P6APEAXPEAXPEBGK@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6APEAXPEAXPEBGK@ZXZ; Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,ushort const *,ulong),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,ushort const *,ulong)(void)
0x18003020a  mov     r8, [rdi+48h]
0x18003020e  add     r8, 10h
0x180030212  lea     r9, [rsp+1B0h+var_178]
0x180030217  mov     rdx, r12
0x18003021a  lea     rcx, [rbp+0B0h+var_E0]
0x18003021e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030223  test    eax, eax
0x180030225  jnz     loc_1800302C7
0x18003022b  movups  xmm0, xmmword ptr [r14]
0x18003022f  movaps  [rsp+1B0h+var_140], xmm0
0x180030234  movups  xmm1, xmmword ptr [r14+10h]
0x180030239  movaps  [rbp+0B0h+var_130], xmm1
0x18003023d  movups  xmm0, xmmword ptr [r14+20h]
0x180030242  movaps  [rbp+0B0h+var_120], xmm0
0x180030246  movups  xmm1, xmmword ptr [r14+30h]
0x18003024b  movaps  [rbp+0B0h+var_110], xmm1
0x18003024f  movups  xmm0, xmmword ptr [r14+40h]
0x180030254  movaps  [rbp+0B0h+var_100], xmm0
0x180030258  movsd   xmm1, qword ptr [r14+50h]
0x18003025e  movsd   [rbp+0B0h+var_F0], xmm1
0x180030263  movups  xmm0, cs:EventMetadataGuid
0x18003026a  movdqu  [rbp+0B0h+var_130+8], xmm0
0x18003026f  mov     dword ptr [rsp+1B0h+var_140+4], 21h ; '!'
0x180030277  movups  xmm0, xmmword ptr [r13+0]
0x18003027c  mov     rax, [rdi+48h]
0x180030280  movdqu  xmmword ptr [rax], xmm0
0x180030284  mov     rax, [rdi+48h]
0x180030288  mov     qword ptr [rbp+0B0h+var_100+8], rax
0x18003028c  mov     eax, dword ptr [rsp+1B0h+var_178]
0x180030290  add     eax, 10h
0x180030293  mov     dword ptr [rbp+0B0h+var_F0], eax
0x180030296  mov     ecx, eax
0x180030298  add     rcx, 30h ; '0'
0x18003029c  cmp     rcx, 0FFB8h
0x1800302a3  ja      short loc_1800302C7
0x1800302a5  mov     rcx, [rdi+10h]
0x1800302a9  mov     rax, [rcx]
0x1800302ac  xor     r9d, r9d
0x1800302af  xor     r8d, r8d
0x1800302b2  lea     rdx, [rsp+1B0h+var_140]
0x1800302b7  mov     rax, [rax+0C0h]
0x1800302be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800302c3  test    eax, eax
0x1800302c5  js      short loc_1800302D7
0x1800302c7  inc     esi
0x1800302c9  jmp     loc_180030104
0x1800302ce  mov     eax, 8007000Eh
0x1800302d3  jmp     short loc_1800302D7
0x1800302d5  xor     eax, eax
0x1800302d7  mov     rcx, [rbp+0B0h+var_50]
0x1800302db  xor     rcx, rsp; StackCookie
0x1800302de  call    __security_check_cookie
0x1800302e3  add     rsp, 178h
0x1800302ea  pop     r15
0x1800302ec  pop     r14
0x1800302ee  pop     r13
0x1800302f0  pop     r12
0x1800302f2  pop     rdi
0x1800302f3  pop     rsi
0x1800302f4  pop     rbx
0x1800302f5  pop     rbp
0x1800302f6  retn
```
