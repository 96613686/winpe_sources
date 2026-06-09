# Mpeg2DemuxAttributes::CMediaSampleWrapper::Release(void)

- ea: `0x180010e60`
- end: `0x180011178`
- name: `?Release@CMediaSampleWrapper@Mpeg2DemuxAttributes@@UEAAKXZ`
- size: `792`
- prototype: `unsigned int __fastcall(Mpeg2DemuxAttributes::CMediaSampleWrapper *__hidden this)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x1800107b0`
- `0x180010b8c`
- `0x1800141a0`
- `0x18009add0`
- `0x18009ade0`

## callees

- `0x180010e60`
- `0x180051ce4`
- `0x18007c8e8`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010ee2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010f9c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010ee2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010f9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010eb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010f71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001101e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011055`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010eb7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010f71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001101e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011055`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010fe7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010fe7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180010ec8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180010f82`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180010ec8`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180010f82`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800110a1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180011129`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800110a1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180011129`

## pseudocode

```c
__int64 __fastcall Mpeg2DemuxAttributes::CMediaSampleWrapper::Release(Mpeg2DemuxAttributes::CMediaSampleWrapper *this)
{
  unsigned __int32 v2; // edi
  CallStackTracing *v3; // rbx
  char *v4; // rsi
  DWORD LastError; // ebp
  char *Value; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  GUID *v9; // rsi
  DWORD v10; // ebp
  GUID *v11; // rax
  int v12; // eax
  int v13; // eax
  CallStackTracing *v15; // rcx
  __int64 v16; // rax
  CallStackTracing *v17; // rcx
  __int64 v18; // rax
  CallStackTracing *v19; // rax
  CallStackTracing *v20; // rax

  if ( *((_DWORD *)this + 88) == 1 )
  {
    v2 = 0;
    *((_DWORD *)this + 88) = 0;
  }
  else
  {
    v2 = _InterlockedDecrement((volatile signed __int32 *)this + 88);
  }
  v3 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v3 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v3 + 8) )
  {
    v4 = (char *)v3 + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v3 + 3));
    if ( Value )
    {
      v4 = Value;
    }
    else if ( !GetLastError() )
    {
      v15 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v19 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v19;
        if ( v19 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v19 + 8LL))(v19, 2032) )
        {
          v15 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v15 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      v16 = (**(__int64 (__fastcall ***)(CallStackTracing *))v15)(v15);
      if ( v16 )
        v4 = (char *)v16;
    }
    SetLastError(LastError);
    v7 = *((unsigned int *)v4 + 497);
    v3 = CallStackTracing::s_wpInstance;
    if ( (unsigned int)v7 < *((_DWORD *)v4 + 498) )
    {
      v8 = 2 * v7;
      *(_QWORD *)&v4[8 * v8] = "Mpeg2DemuxAttributes::CMediaSampleWrapper::Release";
      *(_DWORD *)&v4[8 * v8 + 8] = 2399;
    }
    ++*((_DWORD *)v4 + 497);
  }
  if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
  {
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 17),
      37,
      &WPP_ea15c8c7cf393e7e63170f2c53fa20e3_Traceguids,
      this,
      *((_DWORD *)this + 88));
    v3 = CallStackTracing::s_wpInstance;
  }
  if ( !v2 )
  {
    (*(void (__fastcall **)(Mpeg2DemuxAttributes::CMediaSampleWrapper *))(*(_QWORD *)this + 184LL))(this);
    (*(void (__fastcall **)(Mpeg2DemuxAttributes::CMediaSampleWrapper *))(*(_QWORD *)this + 168LL))(this);
    v3 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v3 + 8) )
  {
    v9 = (GUID *)((char *)v3 + 208);
    v10 = GetLastError();
    v11 = (GUID *)TlsGetValue(*((_DWORD *)v3 + 3));
    if ( v11 )
    {
      v9 = v11;
    }
    else if ( !GetLastError() )
    {
      v17 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v20 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v20;
        if ( v20 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v20 + 8LL))(v20, 2032) )
        {
          v17 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v17 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      v18 = (**(__int64 (__fastcall ***)(CallStackTracing *))v17)(v17);
      if ( v18 )
        v9 = (GUID *)v18;
    }
    SetLastError(v10);
    v12 = *(_DWORD *)&v9[124].Data2;
    if ( v12 )
    {
      v13 = v12 - 1;
      *(_DWORD *)&v9[124].Data2 = v13;
      if ( !v13 )
      {
        *(_DWORD *)&v9[124].Data2 = 0;
        *(_QWORD *)&v9[126].Data1 = 0;
        *(_DWORD *)&v9[124].Data4[4] = 0;
        v9[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v9[126].Data4 = 0;
        v9[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  return v2;
}

```

## disassembly

```asm
0x180010e60  push    rbx
0x180010e62  push    rdi
0x180010e63  push    r15
0x180010e65  sub     rsp, 30h
0x180010e69  xor     r15d, r15d
0x180010e6c  mov     [rsp+48h+arg_10], r14
0x180010e71  cmp     dword ptr [rcx+160h], 1
0x180010e78  mov     r14, rcx
0x180010e7b  jz      loc_18001100F
0x180010e81  mov     edi, 0FFFFFFFFh
0x180010e86  lock xadd [rcx+160h], edi
0x180010e8e  dec     edi
0x180010e90  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010e97  test    rbx, rbx
0x180010e9a  jz      loc_180011090
0x180010ea0  mov     [rsp+48h+arg_0], rbp
0x180010ea5  mov     [rsp+48h+arg_8], rsi
0x180010eaa  cmp     [rbx+8], r15b
0x180010eae  jz      short loc_180010F1F
0x180010eb0  lea     rsi, [rbx+0D0h]
0x180010eb7  call    cs:__imp_GetLastError
0x180010ebe  nop     dword ptr [rax+rax+00h]
0x180010ec3  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180010ec6  mov     ebp, eax
0x180010ec8  call    cs:__imp_TlsGetValue
0x180010ecf  nop     dword ptr [rax+rax+00h]
0x180010ed4  test    rax, rax
0x180010ed7  jz      loc_18001101E
0x180010edd  mov     rsi, rax
0x180010ee0  mov     ecx, ebp; dwErrCode
0x180010ee2  call    cs:__imp_SetLastError
0x180010ee9  nop     dword ptr [rax+rax+00h]
0x180010eee  mov     eax, [rsi+7C4h]
0x180010ef4  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010efb  cmp     eax, [rsi+7C8h]
0x180010f01  jnb     short loc_180010F19
0x180010f03  add     rax, rax
0x180010f06  lea     rcx, aMpeg2demuxattr; "Mpeg2DemuxAttributes::CMediaSampleWrapp"...
0x180010f0d  mov     [rsi+rax*8], rcx
0x180010f11  mov     dword ptr [rsi+rax*8+8], 95Fh
0x180010f19  inc     dword ptr [rsi+7C4h]
0x180010f1f  cmp     cs:byte_1800EACCB, 20h ; ' '
0x180010f26  jnb     loc_1800110F0
0x180010f2c  test    edi, edi
0x180010f2e  jnz     short loc_180010F5B
0x180010f30  mov     rax, [r14]
0x180010f33  mov     rcx, r14
0x180010f36  mov     rax, [rax+0B8h]
0x180010f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f42  mov     rax, [r14]
0x180010f45  mov     rcx, r14
0x180010f48  mov     rax, [rax+0A8h]
0x180010f4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f54  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180010f5b  mov     r14, [rsp+48h+arg_10]
0x180010f60  cmp     [rbx+8], r15b
0x180010f64  jz      loc_180010FF9
0x180010f6a  lea     rsi, [rbx+0D0h]
0x180010f71  call    cs:__imp_GetLastError
0x180010f78  nop     dword ptr [rax+rax+00h]
0x180010f7d  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180010f80  mov     ebp, eax
0x180010f82  call    cs:__imp_TlsGetValue
0x180010f89  nop     dword ptr [rax+rax+00h]
0x180010f8e  test    rax, rax
0x180010f91  jz      loc_180011055
0x180010f97  mov     rsi, rax
0x180010f9a  mov     ecx, ebp; dwErrCode
0x180010f9c  call    cs:__imp_SetLastError
0x180010fa3  nop     dword ptr [rax+rax+00h]
0x180010fa8  mov     eax, [rsi+7C4h]
0x180010fae  test    eax, eax
0x180010fb0  jz      short loc_180010FF9
0x180010fb2  sub     eax, 1
0x180010fb5  mov     [rsi+7C4h], eax
0x180010fbb  jnz     short loc_180010FF9
0x180010fbd  mov     [rsi+7C4h], r15d
0x180010fc4  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180010fcb  mov     [rsi+7E0h], r15
0x180010fd2  mov     [rsi+7CCh], r15d
0x180010fd9  movups  xmmword ptr [rsi+7D0h], xmm0
0x180010fe0  mov     [rsi+7E8h], r15d
0x180010fe7  call    cs:__imp_GetCurrentThreadId
0x180010fee  nop     dword ptr [rax+rax+00h]
0x180010ff3  mov     [rsi+7C0h], eax
0x180010ff9  mov     rsi, [rsp+48h+arg_8]
0x180010ffe  mov     eax, edi
0x180011000  mov     rbp, [rsp+48h+arg_0]
0x180011005  add     rsp, 30h
0x180011009  pop     r15
0x18001100b  pop     rdi
0x18001100c  pop     rbx
0x18001100d  retn
0x18001100f  mov     edi, r15d
0x180011012  mov     [rcx+160h], r15d
0x180011019  jmp     loc_180010E90
0x18001101e  call    cs:__imp_GetLastError
0x180011025  nop     dword ptr [rax+rax+00h]
0x18001102a  test    eax, eax
0x18001102c  jnz     loc_180010EE0
0x180011032  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180011039  test    rcx, rcx
0x18001103c  jz      short loc_1800110A1
0x18001103e  mov     rax, [rcx]
0x180011041  mov     rax, [rax]
0x180011044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011049  test    rax, rax
0x18001104c  cmovnz  rsi, rax
0x180011050  jmp     loc_180010EE0
0x180011055  call    cs:__imp_GetLastError
0x18001105c  nop     dword ptr [rax+rax+00h]
0x180011061  test    eax, eax
0x180011063  jnz     loc_180010F9A
0x180011069  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180011070  test    rcx, rcx
0x180011073  jz      loc_180011129
0x180011079  mov     rax, [rcx]
0x18001107c  mov     rax, [rax]
0x18001107f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011084  test    rax, rax
0x180011087  cmovnz  rsi, rax
0x18001108b  jmp     loc_180010F9A
0x180011090  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180011095  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001109c  jmp     loc_180010EA0
0x1800110a1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800110a8  nop     dword ptr [rax+rax+00h]
0x1800110ad  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800110b4  mov     rcx, rax
0x1800110b7  test    rax, rax
0x1800110ba  jz      short loc_1800110DD
0x1800110bc  mov     rax, [rax]
0x1800110bf  mov     edx, 7F0h
0x1800110c4  mov     rax, [rax+8]
0x1800110c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110cd  test    eax, eax
0x1800110cf  jz      short loc_1800110DD
0x1800110d1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800110d8  jmp     loc_18001103E
0x1800110dd  lea     rcx, qword_1800EB130
0x1800110e4  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800110eb  jmp     loc_18001103E
0x1800110f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800110f7  lea     r8, WPP_ea15c8c7cf393e7e63170f2c53fa20e3_Traceguids
0x1800110fe  mov     eax, [r14+160h]
0x180011105  mov     edx, 25h ; '%'
0x18001110a  mov     r9, r14
0x18001110d  mov     [rsp+48h+var_28], eax
0x180011111  mov     rcx, [rcx+88h]
0x180011118  call    WPP_SF_qD
0x18001111d  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180011124  jmp     loc_180010F2C
0x180011129  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180011130  nop     dword ptr [rax+rax+00h]
0x180011135  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001113c  mov     rcx, rax
0x18001113f  test    rax, rax
0x180011142  jz      short loc_180011165
0x180011144  mov     rax, [rax]
0x180011147  mov     edx, 7F0h
0x18001114c  mov     rax, [rax+8]
0x180011150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011155  test    eax, eax
0x180011157  jz      short loc_180011165
0x180011159  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180011160  jmp     loc_180011079
0x180011165  lea     rcx, qword_1800EB130
0x18001116c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180011173  jmp     loc_180011079
```
