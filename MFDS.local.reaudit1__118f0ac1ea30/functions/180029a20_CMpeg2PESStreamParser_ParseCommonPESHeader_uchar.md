# CMpeg2PESStreamParser::ParseCommonPESHeader_(uchar *)

- ea: `0x180029a20`
- end: `0x180029da8`
- name: `?ParseCommonPESHeader_@CMpeg2PESStreamParser@@IEAAHPEAE@Z`
- size: `904`
- prototype: `__int64 __fastcall(CMpeg2PESStreamParser *__hidden this, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800a8a40`

## callees

- `0x18001a29c`
- `0x180029a20`
- `0x18002d514`
- `0x180051ce4`
- `0x18007c8e8`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029a85`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029b6c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029a85`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029b6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029a5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029b41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029bde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029c15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029a5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029b41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029bde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029c15`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029bb7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180029bb7`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180029a6b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180029b52`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180029a6b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180029b52`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180029c5a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180029d59`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180029c5a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180029d59`

## string_xrefs

- `0x180029aa2`: `CMpeg2PESStreamParser::ParseCommonPESHeader_`

## pseudocode

```c
_BOOL8 __fastcall CMpeg2PESStreamParser::ParseCommonPESHeader_(CMpeg2PESStreamParser *this, unsigned __int8 *a2)
{
  CallStackTracing *v4; // rbx
  char *v5; // rdi
  DWORD LastError; // esi
  char *Value; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  int v10; // r8d
  CallStackTracing *v11; // rbx
  BOOL v12; // esi
  GUID *v13; // rdi
  DWORD v14; // ebp
  GUID *v15; // rax
  int v16; // eax
  int v17; // eax
  CallStackTracing *v19; // rcx
  __int64 v20; // rax
  CallStackTracing *v21; // rcx
  __int64 v22; // rax
  CallStackTracing *v23; // rax
  __int64 v24; // rcx
  CallStackTracing *v25; // rax
  __int128 v26; // [rsp+30h] [rbp-48h] BYREF
  __int64 v27; // [rsp+40h] [rbp-38h]

  if ( !CallStackTracing::s_wpInstance )
    CallStackTracing::InitInstance();
  v4 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v5 = (char *)CallStackTracing::s_wpInstance + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v4 + 3));
    if ( Value )
    {
      v5 = Value;
    }
    else if ( !GetLastError() )
    {
      v19 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v23;
        if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
        {
          v19 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v19 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      v20 = (**(__int64 (__fastcall ***)(CallStackTracing *))v19)(v19);
      if ( v20 )
        v5 = (char *)v20;
    }
    SetLastError(LastError);
    v8 = *((unsigned int *)v5 + 497);
    if ( (unsigned int)v8 < *((_DWORD *)v5 + 498) )
    {
      v9 = 2 * v8;
      *(_QWORD *)&v5[8 * v9] = "CMpeg2PESStreamParser::ParseCommonPESHeader_";
      *(_DWORD *)&v5[8 * v9 + 8] = 1248;
    }
    ++*((_DWORD *)v5 + 497);
  }
  if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 17), 50, &WPP_2790e164590a3ed111972434a23f3cea_Traceguids, this);
  v10 = *(_DWORD *)a2 & 0xFF00 | ((unsigned __int8)*(_DWORD *)a2 << 16) | (unsigned __int8)BYTE2(*(_DWORD *)a2);
  *((_DWORD *)this + 104) = v10;
  *((_DWORD *)this + 105) = a2[3];
  *((_DWORD *)this + 106) = HIBYTE(*((unsigned __int16 *)a2 + 2)) | ((unsigned __int8)*((_WORD *)a2 + 2) << 8);
  if ( v10 != 1 )
  {
    v26 = 0;
    BYTE10(v26) = BYTE2(v10);
    v24 = *((_QWORD *)this + 67) + 8504LL;
    v27 = 0;
    WORD4(v26) = v10;
    BYTE11(v26) = HIBYTE(v10);
    Mpeg2DemuxTrace::CTeHomeETWEvent<EH_MPEG2_ERROR_EVENT>::TraceEvent(v24, &v26);
    if ( byte_1800EACCB )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 17),
        51,
        &WPP_2790e164590a3ed111972434a23f3cea_Traceguids,
        this,
        *((_DWORD *)this + 104));
  }
  v11 = CallStackTracing::s_wpInstance;
  v12 = *((_DWORD *)this + 104) == 1;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v13 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
    v14 = GetLastError();
    v15 = (GUID *)TlsGetValue(*((_DWORD *)v11 + 3));
    if ( v15 )
    {
      v13 = v15;
    }
    else if ( !GetLastError() )
    {
      v21 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v25;
        if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
        {
          v21 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v21 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      v22 = (**(__int64 (__fastcall ***)(CallStackTracing *))v21)(v21);
      if ( v22 )
        v13 = (GUID *)v22;
    }
    SetLastError(v14);
    v16 = *(_DWORD *)&v13[124].Data2;
    if ( v16 )
    {
      v17 = v16 - 1;
      *(_DWORD *)&v13[124].Data2 = v17;
      if ( !v17 )
      {
        *(_DWORD *)&v13[124].Data2 = 0;
        *(_QWORD *)&v13[126].Data1 = 0;
        *(_DWORD *)&v13[124].Data4[4] = 0;
        v13[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v13[126].Data4 = 0;
        v13[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  return v12;
}

```

## disassembly

```asm
0x180029a20  push    rbx
0x180029a22  push    rbp
0x180029a23  push    rsi
0x180029a24  push    r14
0x180029a26  sub     rsp, 58h
0x180029a2a  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x180029a32  mov     r14, rdx
0x180029a35  mov     rbp, rcx
0x180029a38  jz      loc_180029C50
0x180029a3e  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180029a45  mov     [rsp+78h+arg_0], rdi
0x180029a4d  cmp     byte ptr [rbx+8], 0
0x180029a51  jz      short loc_180029ABB
0x180029a53  lea     rdi, [rbx+0D0h]
0x180029a5a  call    cs:__imp_GetLastError
0x180029a61  nop     dword ptr [rax+rax+00h]
0x180029a66  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180029a69  mov     esi, eax
0x180029a6b  call    cs:__imp_TlsGetValue
0x180029a72  nop     dword ptr [rax+rax+00h]
0x180029a77  test    rax, rax
0x180029a7a  jz      loc_180029BDE
0x180029a80  mov     rdi, rax
0x180029a83  mov     ecx, esi; dwErrCode
0x180029a85  call    cs:__imp_SetLastError
0x180029a8c  nop     dword ptr [rax+rax+00h]
0x180029a91  mov     eax, [rdi+7C4h]
0x180029a97  cmp     eax, [rdi+7C8h]
0x180029a9d  jnb     short loc_180029AB5
0x180029a9f  add     rax, rax
0x180029aa2  lea     rcx, aCmpeg2pesstrea_3; "CMpeg2PESStreamParser::ParseCommonPESHe"...
0x180029aa9  mov     [rdi+rax*8], rcx
0x180029aad  mov     dword ptr [rdi+rax*8+8], 4E0h
0x180029ab5  inc     dword ptr [rdi+7C4h]
0x180029abb  cmp     cs:byte_1800EACCB, 20h ; ' '
0x180029ac2  jnb     loc_180029CA9
0x180029ac8  mov     ecx, [r14]
0x180029acb  mov     eax, ecx
0x180029acd  shr     eax, 10h
0x180029ad0  movzx   r8d, al
0x180029ad4  movzx   eax, cl
0x180029ad7  and     ecx, 0FF00h
0x180029add  shl     eax, 10h
0x180029ae0  or      r8d, eax
0x180029ae3  or      r8d, ecx
0x180029ae6  mov     [rbp+1A0h], r8d
0x180029aed  movzx   eax, byte ptr [r14+3]
0x180029af2  mov     [rbp+1A4h], eax
0x180029af8  movzx   ecx, word ptr [r14+4]
0x180029afd  movzx   eax, cl
0x180029b00  shl     eax, 8
0x180029b03  shr     ecx, 8
0x180029b06  or      eax, ecx
0x180029b08  mov     [rbp+1A8h], eax
0x180029b0e  cmp     r8d, 1
0x180029b12  jnz     loc_180029CD0
0x180029b18  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180029b1f  xor     r14d, r14d
0x180029b22  cmp     dword ptr [rbp+1A0h], 1
0x180029b29  mov     esi, r14d
0x180029b2c  setz    sil
0x180029b30  cmp     [rbx+8], r14b
0x180029b34  jz      loc_180029BC9
0x180029b3a  lea     rdi, [rbx+0D0h]
0x180029b41  call    cs:__imp_GetLastError
0x180029b48  nop     dword ptr [rax+rax+00h]
0x180029b4d  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x180029b50  mov     ebp, eax
0x180029b52  call    cs:__imp_TlsGetValue
0x180029b59  nop     dword ptr [rax+rax+00h]
0x180029b5e  test    rax, rax
0x180029b61  jz      loc_180029C15
0x180029b67  mov     rdi, rax
0x180029b6a  mov     ecx, ebp; dwErrCode
0x180029b6c  call    cs:__imp_SetLastError
0x180029b73  nop     dword ptr [rax+rax+00h]
0x180029b78  mov     eax, [rdi+7C4h]
0x180029b7e  test    eax, eax
0x180029b80  jz      short loc_180029BC9
0x180029b82  sub     eax, 1
0x180029b85  mov     [rdi+7C4h], eax
0x180029b8b  jnz     short loc_180029BC9
0x180029b8d  mov     [rdi+7C4h], r14d
0x180029b94  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180029b9b  mov     [rdi+7E0h], r14
0x180029ba2  mov     [rdi+7CCh], r14d
0x180029ba9  movups  xmmword ptr [rdi+7D0h], xmm0
0x180029bb0  mov     [rdi+7E8h], r14d
0x180029bb7  call    cs:__imp_GetCurrentThreadId
0x180029bbe  nop     dword ptr [rax+rax+00h]
0x180029bc3  mov     [rdi+7C0h], eax
0x180029bc9  mov     rdi, [rsp+78h+arg_0]
0x180029bd1  mov     eax, esi
0x180029bd3  add     rsp, 58h
0x180029bd7  pop     r14
0x180029bd9  pop     rsi
0x180029bda  pop     rbp
0x180029bdb  pop     rbx
0x180029bdc  retn
0x180029bde  call    cs:__imp_GetLastError
0x180029be5  nop     dword ptr [rax+rax+00h]
0x180029bea  test    eax, eax
0x180029bec  jnz     loc_180029A83
0x180029bf2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180029bf9  test    rcx, rcx
0x180029bfc  jz      short loc_180029C5A
0x180029bfe  mov     rax, [rcx]
0x180029c01  mov     rax, [rax]
0x180029c04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c09  test    rax, rax
0x180029c0c  cmovnz  rdi, rax
0x180029c10  jmp     loc_180029A83
0x180029c15  call    cs:__imp_GetLastError
0x180029c1c  nop     dword ptr [rax+rax+00h]
0x180029c21  test    eax, eax
0x180029c23  jnz     loc_180029B6A
0x180029c29  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180029c30  test    rcx, rcx
0x180029c33  jz      loc_180029D59
0x180029c39  mov     rax, [rcx]
0x180029c3c  mov     rax, [rax]
0x180029c3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c44  test    rax, rax
0x180029c47  cmovnz  rdi, rax
0x180029c4b  jmp     loc_180029B6A
0x180029c50  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180029c55  jmp     loc_180029A3E
0x180029c5a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180029c61  nop     dword ptr [rax+rax+00h]
0x180029c66  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180029c6d  mov     rcx, rax
0x180029c70  test    rax, rax
0x180029c73  jz      short loc_180029C96
0x180029c75  mov     rax, [rax]
0x180029c78  mov     edx, 7F0h
0x180029c7d  mov     rax, [rax+8]
0x180029c81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029c86  test    eax, eax
0x180029c88  jz      short loc_180029C96
0x180029c8a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180029c91  jmp     loc_180029BFE
0x180029c96  lea     rcx, qword_1800EB130
0x180029c9d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180029ca4  jmp     loc_180029BFE
0x180029ca9  mov     rcx, cs:WPP_GLOBAL_Control
0x180029cb0  lea     r8, WPP_2790e164590a3ed111972434a23f3cea_Traceguids
0x180029cb7  mov     edx, 32h ; '2'
0x180029cbc  mov     r9, rbp
0x180029cbf  mov     rcx, [rcx+88h]
0x180029cc6  call    WPP_SF_q
0x180029ccb  jmp     loc_180029AC8
0x180029cd0  mov     ecx, r8d
0x180029cd3  mov     edx, r8d
0x180029cd6  shr     ecx, 10h
0x180029cd9  xorps   xmm0, xmm0
0x180029cdc  movups  [rsp+78h+var_48], xmm0
0x180029ce1  mov     byte ptr [rsp+78h+var_48+0Ah], cl
0x180029ce5  mov     eax, r8d
0x180029ce8  mov     rcx, [rbp+218h]
0x180029cef  xor     r9d, r9d
0x180029cf2  shr     edx, 8
0x180029cf5  add     rcx, 2138h
0x180029cfc  shr     eax, 18h
0x180029cff  mov     byte ptr [rsp+78h+var_48+9], dl
0x180029d03  lea     rdx, [rsp+78h+var_48]
0x180029d08  mov     [rsp+78h+var_38], r9
0x180029d0d  mov     byte ptr [rsp+78h+var_48+8], r8b
0x180029d12  mov     byte ptr [rsp+78h+var_48+0Bh], al
0x180029d16  call    ?TraceEvent@?$CTeHomeETWEvent@UEH_MPEG2_ERROR_EVENT@@@Mpeg2DemuxTrace@@QEAAXPEAUEH_MPEG2_ERROR_EVENT@@@Z; Mpeg2DemuxTrace::CTeHomeETWEvent<EH_MPEG2_ERROR_EVENT>::TraceEvent(EH_MPEG2_ERROR_EVENT *)
0x180029d1b  cmp     cs:byte_1800EACCB, 1
0x180029d22  jb      loc_180029B18
0x180029d28  mov     rcx, cs:WPP_GLOBAL_Control
0x180029d2f  lea     r8, WPP_2790e164590a3ed111972434a23f3cea_Traceguids
0x180029d36  mov     eax, [rbp+1A0h]
0x180029d3c  mov     edx, 33h ; '3'
0x180029d41  mov     r9, rbp
0x180029d44  mov     [rsp+78h+var_58], eax
0x180029d48  mov     rcx, [rcx+88h]
0x180029d4f  call    WPP_SF_qD
0x180029d54  jmp     loc_180029B18
0x180029d59  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180029d60  nop     dword ptr [rax+rax+00h]
0x180029d65  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180029d6c  mov     rcx, rax
0x180029d6f  test    rax, rax
0x180029d72  jz      short loc_180029D95
0x180029d74  mov     rax, [rax]
0x180029d77  mov     edx, 7F0h
0x180029d7c  mov     rax, [rax+8]
0x180029d80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029d85  test    eax, eax
0x180029d87  jz      short loc_180029D95
0x180029d89  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180029d90  jmp     loc_180029C39
0x180029d95  lea     rcx, qword_1800EB130
0x180029d9c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180029da3  jmp     loc_180029C39
```
