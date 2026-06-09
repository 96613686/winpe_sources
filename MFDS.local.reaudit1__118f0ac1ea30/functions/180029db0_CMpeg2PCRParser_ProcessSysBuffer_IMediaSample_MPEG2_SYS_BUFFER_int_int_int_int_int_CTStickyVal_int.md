# CMpeg2PCRParser::ProcessSysBuffer(IMediaSample *,MPEG2_SYS_BUFFER *,int,int,int,int,int,CTStickyVal<int> *)

- ea: `0x180029db0`
- end: `0x18002a169`
- name: `?ProcessSysBuffer@CMpeg2PCRParser@@UEAAJPEAUIMediaSample@@PEAUMPEG2_SYS_BUFFER@@HHHHHPEAV?$CTStickyVal@H@@@Z`
- size: `953`
- prototype: `__int64 __usercall@<rax>(CCopyFrameParser *this@<rcx>, int, int, int, int, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180007f20`
- `0x180008d60`
- `0x18000a4e0`
- `0x18000acb0`
- `0x180029db0`
- `0x18002d514`
- `0x180074160`
- `0x18007c8e8`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029e4a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029ef5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029e4a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029ef5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029e1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029eca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a004`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a03b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029e1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029eca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a004`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a03b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029f40`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029f40`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180029e30`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180029edb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180029e30`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180029edb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a080`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a11a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a080`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002a11a`

## pseudocode

```c
__int64 __fastcall CMpeg2PCRParser::ProcessSysBuffer(
        CCopyFrameParser *this,
        struct IMediaSample *a2,
        __int64 a3,
        int a4,
        int a5,
        int a6,
        int a7,
        int a8,
        __int64 a9)
{
  CallStackTracing *v12; // rbx
  char *v13; // rdi
  DWORD LastError; // esi
  char *Value; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  int NewFrameBuffer; // ebp
  CallStackTracing *v19; // rbx
  GUID *v20; // rdi
  DWORD v21; // esi
  GUID *v22; // rax
  int v23; // eax
  int v24; // eax
  CallStackTracing *v26; // rcx
  __int64 v27; // rax
  CallStackTracing *v28; // rcx
  __int64 v29; // rax
  CallStackTracing *v30; // rax
  CallStackTracing *v31; // rax
  unsigned __int8 v32[16]; // [rsp+20h] [rbp-58h] BYREF

  *(_OWORD *)v32 = 0;
  if ( !CallStackTracing::s_wpInstance )
    CallStackTracing::InitInstance();
  v12 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v13 = (char *)CallStackTracing::s_wpInstance + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v12 + 3));
    if ( Value )
    {
      v13 = Value;
    }
    else if ( !GetLastError() )
    {
      v26 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v30 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v30;
        if ( v30 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v30 + 8LL))(v30, 2032) )
        {
          v26 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v26 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      v27 = (**(__int64 (__fastcall ***)(CallStackTracing *))v26)(v26);
      if ( v27 )
        v13 = (char *)v27;
    }
    SetLastError(LastError);
    v16 = *((unsigned int *)v13 + 497);
    if ( (unsigned int)v16 < *((_DWORD *)v13 + 498) )
    {
      v17 = 2 * v16;
      *(_QWORD *)&v13[8 * v17] = "CMpeg2PCRParser::ProcessSysBuffer";
      *(_DWORD *)&v13[8 * v17 + 8] = 2996;
    }
    ++*((_DWORD *)v13 + 497);
  }
  if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 115, &WPP_2790e164590a3ed111972434a23f3cea_Traceguids, this);
  if ( (unsigned int)(*(_DWORD *)(a3 + 56) - 2) <= 1 && *(_DWORD *)(a3 + 64) && *(_DWORD *)(a3 + 80) && !a4 )
  {
    *(_QWORD *)v32 = *(unsigned int *)(a3 + 112) + 300LL * *(_QWORD *)(a3 + 104);
    *(_DWORD *)&v32[12] = a8 - 177;
    NewFrameBuffer = CCopyFrameParser::GetNewFrameBuffer(this, a2);
    if ( NewFrameBuffer >= 0 )
    {
      *(_DWORD *)&v32[8] = *(_DWORD *)(a3 + 28) & 0x1FFF;
      if ( (unsigned int)CCopyFrameParser::CopyFrameBytes(this, v32, 0x10u) )
      {
        CBufferSourceManager::Complete((__int64)this + 48, a9);
      }
      else
      {
        if ( *((_DWORD *)this + 101) )
          *(_DWORD *)(a3 + 28) |= 0x2000u;
        CBufferSourceManager::AbortBuffer((CCopyFrameParser *)((char *)this + 48));
        NewFrameBuffer = -2147467259;
      }
    }
  }
  else
  {
    NewFrameBuffer = 0;
  }
  v19 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v20 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
    v21 = GetLastError();
    v22 = (GUID *)TlsGetValue(*((_DWORD *)v19 + 3));
    if ( v22 )
    {
      v20 = v22;
    }
    else if ( !GetLastError() )
    {
      v28 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v31;
        if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
        {
          v28 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v28 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      v29 = (**(__int64 (__fastcall ***)(CallStackTracing *))v28)(v28);
      if ( v29 )
        v20 = (GUID *)v29;
    }
    SetLastError(v21);
    v23 = *(_DWORD *)&v20[124].Data2;
    if ( v23 )
    {
      v24 = v23 - 1;
      *(_DWORD *)&v20[124].Data2 = v24;
      if ( !v24 )
      {
        *(_DWORD *)&v20[124].Data2 = 0;
        *(_QWORD *)&v20[126].Data1 = 0;
        *(_DWORD *)&v20[124].Data4[4] = 0;
        v20[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v20[126].Data4 = 0;
        v20[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  return (unsigned int)NewFrameBuffer;
}

```

## disassembly

```asm
0x180029db0  push    rbx
0x180029db2  push    rbp
0x180029db3  push    r13
0x180029db5  sub     rsp, 60h
0x180029db9  mov     rax, cs:__security_cookie
0x180029dc0  xor     rax, rsp
0x180029dc3  mov     [rsp+78h+var_48], rax
0x180029dc8  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x180029dd0  xorps   xmm0, xmm0
0x180029dd3  mov     [rsp+78h+var_28], r12
0x180029dd8  mov     ebp, r9d
0x180029ddb  mov     r12, [rsp+78h+arg_40]
0x180029de3  mov     [rsp+78h+var_30], r14
0x180029de8  mov     r14, r8
0x180029deb  mov     [rsp+78h+var_38], r15
0x180029df0  mov     r15, rcx
0x180029df3  movups  xmmword ptr [rsp+78h+var_58], xmm0
0x180029df8  jz      loc_18002A076
0x180029dfe  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180029e05  mov     [rsp+78h+arg_8], rsi
0x180029e0d  mov     [rsp+78h+var_20], rdi
0x180029e12  cmp     byte ptr [rbx+8], 0
0x180029e16  jz      short loc_180029E80
0x180029e18  lea     rdi, [rbx+0D0h]
0x180029e1f  call    cs:__imp_GetLastError
0x180029e26  nop     dword ptr [rax+rax+00h]
0x180029e2b  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180029e2e  mov     esi, eax
0x180029e30  call    cs:__imp_TlsGetValue
0x180029e37  nop     dword ptr [rax+rax+00h]
0x180029e3c  test    rax, rax
0x180029e3f  jz      loc_18002A004
0x180029e45  mov     rdi, rax
0x180029e48  mov     ecx, esi; dwErrCode
0x180029e4a  call    cs:__imp_SetLastError
0x180029e51  nop     dword ptr [rax+rax+00h]
0x180029e56  mov     eax, [rdi+7C4h]
0x180029e5c  cmp     eax, [rdi+7C8h]
0x180029e62  jnb     short loc_180029E7A
0x180029e64  add     rax, rax
0x180029e67  lea     rcx, aCmpeg2pcrparse_0; "CMpeg2PCRParser::ProcessSysBuffer"
0x180029e6e  mov     [rdi+rax*8], rcx
0x180029e72  mov     dword ptr [rdi+rax*8+8], 0BB4h
0x180029e7a  inc     dword ptr [rdi+7C4h]
0x180029e80  cmp     cs:byte_1800EACCB, 20h ; ' '
0x180029e87  jnb     loc_18002A0CF
0x180029e8d  mov     eax, [r14+38h]
0x180029e91  xor     r13d, r13d
0x180029e94  sub     eax, 2
0x180029e97  cmp     eax, 1
0x180029e9a  jbe     loc_180029F78
0x180029ea0  mov     ebp, r13d
0x180029ea3  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180029eaa  mov     r15, [rsp+78h+var_38]
0x180029eaf  mov     r14, [rsp+78h+var_30]
0x180029eb4  mov     r12, [rsp+78h+var_28]
0x180029eb9  cmp     [rbx+8], r13b
0x180029ebd  jz      loc_180029F52
0x180029ec3  lea     rdi, [rbx+0D0h]
0x180029eca  call    cs:__imp_GetLastError
0x180029ed1  nop     dword ptr [rax+rax+00h]
0x180029ed6  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180029ed9  mov     esi, eax
0x180029edb  call    cs:__imp_TlsGetValue
0x180029ee2  nop     dword ptr [rax+rax+00h]
0x180029ee7  test    rax, rax
0x180029eea  jz      loc_18002A03B
0x180029ef0  mov     rdi, rax
0x180029ef3  mov     ecx, esi; dwErrCode
0x180029ef5  call    cs:__imp_SetLastError
0x180029efc  nop     dword ptr [rax+rax+00h]
0x180029f01  mov     eax, [rdi+7C4h]
0x180029f07  test    eax, eax
0x180029f09  jz      short loc_180029F52
0x180029f0b  sub     eax, 1
0x180029f0e  mov     [rdi+7C4h], eax
0x180029f14  jnz     short loc_180029F52
0x180029f16  mov     [rdi+7C4h], r13d
0x180029f1d  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180029f24  mov     [rdi+7E0h], r13
0x180029f2b  mov     [rdi+7CCh], r13d
0x180029f32  movups  xmmword ptr [rdi+7D0h], xmm0
0x180029f39  mov     [rdi+7E8h], r13d
0x180029f40  call    cs:__imp_GetCurrentThreadId
0x180029f47  nop     dword ptr [rax+rax+00h]
0x180029f4c  mov     [rdi+7C0h], eax
0x180029f52  mov     rdi, [rsp+78h+var_20]
0x180029f57  mov     eax, ebp
0x180029f59  mov     rsi, [rsp+78h+arg_8]
0x180029f61  mov     rcx, [rsp+78h+var_48]
0x180029f66  xor     rcx, rsp; StackCookie
0x180029f69  call    __security_check_cookie
0x180029f6e  add     rsp, 60h
0x180029f72  pop     r13
0x180029f74  pop     rbp
0x180029f75  pop     rbx
0x180029f76  retn
0x180029f78  cmp     [r14+40h], r13d
0x180029f7c  jbe     loc_180029EA0
0x180029f82  cmp     [r14+50h], r13d
0x180029f86  jz      loc_180029EA0
0x180029f8c  test    ebp, ebp
0x180029f8e  jnz     loc_180029EA0
0x180029f94  mov     eax, [r14+70h]
0x180029f98  imul    rcx, [r14+68h], 12Ch
0x180029fa0  add     rcx, rax
0x180029fa3  mov     eax, [rsp+78h+arg_38]
0x180029faa  add     eax, 0FFFFFF4Fh
0x180029faf  mov     qword ptr [rsp+78h+var_58], rcx
0x180029fb4  mov     rcx, r15; this
0x180029fb7  mov     dword ptr [rsp+78h+var_58+0Ch], eax
0x180029fbb  call    ?GetNewFrameBuffer@CCopyFrameParser@@IEAAJPEAUIMediaSample@@@Z; CCopyFrameParser::GetNewFrameBuffer(IMediaSample *)
0x180029fc0  mov     ebp, eax
0x180029fc2  test    eax, eax
0x180029fc4  js      loc_180029EA3
0x180029fca  mov     ecx, [r14+1Ch]
0x180029fce  lea     rdx, [rsp+78h+var_58]; unsigned __int8 *
0x180029fd3  and     ecx, 1FFFh
0x180029fd9  mov     r8d, 10h; int
0x180029fdf  mov     dword ptr [rsp+78h+var_58+8], ecx
0x180029fe3  mov     rcx, r15; this
0x180029fe6  call    ?CopyFrameBytes@CCopyFrameParser@@IEAAHPEAEH@Z; CCopyFrameParser::CopyFrameBytes(uchar *,int)
0x180029feb  test    eax, eax
0x180029fed  jz      loc_18002A0F6
0x180029ff3  lea     rcx, [r15+30h]
0x180029ff7  mov     rdx, r12
0x180029ffa  call    ?Complete@CBufferSourceManager@@IEAAJPEAV?$CTStickyVal@H@@@Z; CBufferSourceManager::Complete(CTStickyVal<int> *)
0x180029fff  jmp     loc_180029EA3
0x18002a004  call    cs:__imp_GetLastError
0x18002a00b  nop     dword ptr [rax+rax+00h]
0x18002a010  test    eax, eax
0x18002a012  jnz     loc_180029E48
0x18002a018  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a01f  test    rcx, rcx
0x18002a022  jz      short loc_18002A080
0x18002a024  mov     rax, [rcx]
0x18002a027  mov     rax, [rax]
0x18002a02a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a02f  test    rax, rax
0x18002a032  cmovnz  rdi, rax
0x18002a036  jmp     loc_180029E48
0x18002a03b  call    cs:__imp_GetLastError
0x18002a042  nop     dword ptr [rax+rax+00h]
0x18002a047  test    eax, eax
0x18002a049  jnz     loc_180029EF3
0x18002a04f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a056  test    rcx, rcx
0x18002a059  jz      loc_18002A11A
0x18002a05f  mov     rax, [rcx]
0x18002a062  mov     rax, [rax]
0x18002a065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a06a  test    rax, rax
0x18002a06d  cmovnz  rdi, rax
0x18002a071  jmp     loc_180029EF3
0x18002a076  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002a07b  jmp     loc_180029DFE
0x18002a080  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002a087  nop     dword ptr [rax+rax+00h]
0x18002a08c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a093  mov     rcx, rax
0x18002a096  test    rax, rax
0x18002a099  jz      short loc_18002A0BC
0x18002a09b  mov     rax, [rax]
0x18002a09e  mov     edx, 7F0h
0x18002a0a3  mov     rax, [rax+8]
0x18002a0a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a0ac  test    eax, eax
0x18002a0ae  jz      short loc_18002A0BC
0x18002a0b0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a0b7  jmp     loc_18002A024
0x18002a0bc  lea     rcx, qword_1800EB130
0x18002a0c3  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a0ca  jmp     loc_18002A024
0x18002a0cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a0d6  lea     r8, WPP_2790e164590a3ed111972434a23f3cea_Traceguids
0x18002a0dd  mov     edx, 73h ; 's'
0x18002a0e2  mov     r9, r15
0x18002a0e5  mov     rcx, [rcx+88h]
0x18002a0ec  call    WPP_SF_q
0x18002a0f1  jmp     loc_180029E8D
0x18002a0f6  cmp     [r15+194h], r13d
0x18002a0fd  jz      short loc_18002A107
0x18002a0ff  or      dword ptr [r14+1Ch], 2000h
0x18002a107  lea     rcx, [r15+30h]; this
0x18002a10b  call    ?AbortBuffer@CBufferSourceManager@@IEAAXXZ; CBufferSourceManager::AbortBuffer(void)
0x18002a110  mov     ebp, 80004005h
0x18002a115  jmp     loc_180029EA3
0x18002a11a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002a121  nop     dword ptr [rax+rax+00h]
0x18002a126  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a12d  mov     rcx, rax
0x18002a130  test    rax, rax
0x18002a133  jz      short loc_18002A156
0x18002a135  mov     rax, [rax]
0x18002a138  mov     edx, 7F0h
0x18002a13d  mov     rax, [rax+8]
0x18002a141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a146  test    eax, eax
0x18002a148  jz      short loc_18002A156
0x18002a14a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a151  jmp     loc_18002A05F
0x18002a156  lea     rcx, qword_1800EB130
0x18002a15d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a164  jmp     loc_18002A05F
```
