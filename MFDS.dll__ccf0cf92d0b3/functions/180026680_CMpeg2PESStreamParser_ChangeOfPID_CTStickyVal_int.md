# CMpeg2PESStreamParser::ChangeOfPID(CTStickyVal<int> *)

- ea: `0x180026680`
- end: `0x180026963`
- name: `?ChangeOfPID@CMpeg2PESStreamParser@@UEAAJPEAV?$CTStickyVal@H@@@Z`
- size: `739`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800098e0`
- `0x180026680`
- `0x180051ce4`
- `0x18007c8e8`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800266e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026786`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800266e6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026786`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800266bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002675b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800267f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002682b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800266bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002675b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800267f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002682b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800267d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800267d1`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800266cc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002676c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800266cc`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002676c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026877`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026914`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026877`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180026914`

## pseudocode

```c
__int64 __fastcall CMpeg2PESStreamParser::ChangeOfPID(__int64 a1, __int64 a2)
{
  CallStackTracing *v2; // rbx
  char *v5; // rdi
  DWORD LastError; // esi
  char *Value; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  _DWORD *v10; // rdi
  GUID *v11; // rdi
  DWORD v12; // esi
  GUID *v13; // rax
  int v14; // eax
  int v15; // eax
  CallStackTracing *v17; // rcx
  __int64 v18; // rax
  CallStackTracing *v19; // rcx
  __int64 v20; // rax
  CallStackTracing *v21; // rax
  CallStackTracing *v22; // rax

  v2 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v2 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v2 + 8) )
  {
    v5 = (char *)v2 + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v2 + 3));
    if ( Value )
    {
      v5 = Value;
    }
    else if ( !GetLastError() )
    {
      v17 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v21 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v21;
        if ( v21 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v21 + 8LL))(v21, 2032) )
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
        v5 = (char *)v18;
    }
    SetLastError(LastError);
    v8 = *((unsigned int *)v5 + 497);
    v2 = CallStackTracing::s_wpInstance;
    if ( (unsigned int)v8 < *((_DWORD *)v5 + 498) )
    {
      v9 = 2 * v8;
      *(_QWORD *)&v5[8 * v9] = "CMpeg2PESStreamParser::ChangeOfPID";
      *(_DWORD *)&v5[8 * v9 + 8] = 2297;
    }
    ++*((_DWORD *)v5 + 497);
  }
  v10 = (_DWORD *)(a1 + 124);
  if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 17), 84, &WPP_2790e164590a3ed111972434a23f3cea_Traceguids, a1, *v10);
    v2 = CallStackTracing::s_wpInstance;
  }
  if ( *v10 )
  {
    CMpeg2PESStreamParser::CompletePESCollection_(a1, a2, a2);
    v2 = CallStackTracing::s_wpInstance;
    *v10 = 0;
  }
  if ( *((_BYTE *)v2 + 8) )
  {
    v11 = (GUID *)((char *)v2 + 208);
    v12 = GetLastError();
    v13 = (GUID *)TlsGetValue(*((_DWORD *)v2 + 3));
    if ( v13 )
    {
      v11 = v13;
    }
    else if ( !GetLastError() )
    {
      v19 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v22;
        if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
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
        v11 = (GUID *)v20;
    }
    SetLastError(v12);
    v14 = *(_DWORD *)&v11[124].Data2;
    if ( v14 )
    {
      v15 = v14 - 1;
      *(_DWORD *)&v11[124].Data2 = v15;
      if ( !v15 )
      {
        *(_DWORD *)&v11[124].Data2 = 0;
        *(_QWORD *)&v11[126].Data1 = 0;
        *(_DWORD *)&v11[124].Data4[4] = 0;
        v11[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v11[126].Data4 = 0;
        v11[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180026680  push    rbx
0x180026682  push    rdi
0x180026683  push    r15
0x180026685  sub     rsp, 30h
0x180026689  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026690  mov     [rsp+48h+arg_0], rbp
0x180026695  mov     rbp, rcx
0x180026698  mov     [rsp+48h+arg_10], r14
0x18002669d  mov     r14, rdx
0x1800266a0  test    rbx, rbx
0x1800266a3  jz      loc_180026866
0x1800266a9  cmp     byte ptr [rbx+8], 0
0x1800266ad  mov     [rsp+48h+arg_8], rsi
0x1800266b2  jz      short loc_180026723
0x1800266b4  lea     rdi, [rbx+0D0h]
0x1800266bb  call    cs:__imp_GetLastError
0x1800266c2  nop     dword ptr [rax+rax+00h]
0x1800266c7  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x1800266ca  mov     esi, eax
0x1800266cc  call    cs:__imp_TlsGetValue
0x1800266d3  nop     dword ptr [rax+rax+00h]
0x1800266d8  test    rax, rax
0x1800266db  jz      loc_1800267F4
0x1800266e1  mov     rdi, rax
0x1800266e4  mov     ecx, esi; dwErrCode
0x1800266e6  call    cs:__imp_SetLastError
0x1800266ed  nop     dword ptr [rax+rax+00h]
0x1800266f2  mov     eax, [rdi+7C4h]
0x1800266f8  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800266ff  cmp     eax, [rdi+7C8h]
0x180026705  jnb     short loc_18002671D
0x180026707  add     rax, rax
0x18002670a  lea     rcx, aCmpeg2pesstrea_12; "CMpeg2PESStreamParser::ChangeOfPID"
0x180026711  mov     [rdi+rax*8], rcx
0x180026715  mov     dword ptr [rdi+rax*8+8], 8F9h
0x18002671d  inc     dword ptr [rdi+7C4h]
0x180026723  cmp     cs:byte_1800EACCB, 20h ; ' '
0x18002672a  lea     rdi, [rbp+7Ch]
0x18002672e  jnb     loc_1800268C6
0x180026734  xor     r15d, r15d
0x180026737  cmp     [rdi], r15d
0x18002673a  jnz     loc_1800268FA
0x180026740  mov     r14, [rsp+48h+arg_10]
0x180026745  mov     rbp, [rsp+48h+arg_0]
0x18002674a  cmp     [rbx+8], r15b
0x18002674e  jz      loc_1800267E3
0x180026754  lea     rdi, [rbx+0D0h]
0x18002675b  call    cs:__imp_GetLastError
0x180026762  nop     dword ptr [rax+rax+00h]
0x180026767  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18002676a  mov     esi, eax
0x18002676c  call    cs:__imp_TlsGetValue
0x180026773  nop     dword ptr [rax+rax+00h]
0x180026778  test    rax, rax
0x18002677b  jz      loc_18002682B
0x180026781  mov     rdi, rax
0x180026784  mov     ecx, esi; dwErrCode
0x180026786  call    cs:__imp_SetLastError
0x18002678d  nop     dword ptr [rax+rax+00h]
0x180026792  mov     eax, [rdi+7C4h]
0x180026798  test    eax, eax
0x18002679a  jz      short loc_1800267E3
0x18002679c  sub     eax, 1
0x18002679f  mov     [rdi+7C4h], eax
0x1800267a5  jnz     short loc_1800267E3
0x1800267a7  mov     [rdi+7C4h], r15d
0x1800267ae  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800267b5  mov     [rdi+7E0h], r15
0x1800267bc  mov     [rdi+7CCh], r15d
0x1800267c3  movups  xmmword ptr [rdi+7D0h], xmm0
0x1800267ca  mov     [rdi+7E8h], r15d
0x1800267d1  call    cs:__imp_GetCurrentThreadId
0x1800267d8  nop     dword ptr [rax+rax+00h]
0x1800267dd  mov     [rdi+7C0h], eax
0x1800267e3  mov     rsi, [rsp+48h+arg_8]
0x1800267e8  xor     eax, eax
0x1800267ea  add     rsp, 30h
0x1800267ee  pop     r15
0x1800267f0  pop     rdi
0x1800267f1  pop     rbx
0x1800267f2  retn
0x1800267f4  call    cs:__imp_GetLastError
0x1800267fb  nop     dword ptr [rax+rax+00h]
0x180026800  test    eax, eax
0x180026802  jnz     loc_1800266E4
0x180026808  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002680f  test    rcx, rcx
0x180026812  jz      short loc_180026877
0x180026814  mov     rax, [rcx]
0x180026817  mov     rax, [rax]
0x18002681a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002681f  test    rax, rax
0x180026822  cmovnz  rdi, rax
0x180026826  jmp     loc_1800266E4
0x18002682b  call    cs:__imp_GetLastError
0x180026832  nop     dword ptr [rax+rax+00h]
0x180026837  test    eax, eax
0x180026839  jnz     loc_180026784
0x18002683f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026846  test    rcx, rcx
0x180026849  jz      loc_180026914
0x18002684f  mov     rax, [rcx]
0x180026852  mov     rax, [rax]
0x180026855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002685a  test    rax, rax
0x18002685d  cmovnz  rdi, rax
0x180026861  jmp     loc_180026784
0x180026866  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002686b  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180026872  jmp     loc_1800266A9
0x180026877  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002687e  nop     dword ptr [rax+rax+00h]
0x180026883  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002688a  mov     rcx, rax
0x18002688d  test    rax, rax
0x180026890  jz      short loc_1800268B3
0x180026892  mov     rax, [rax]
0x180026895  mov     edx, 7F0h
0x18002689a  mov     rax, [rax+8]
0x18002689e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800268a3  test    eax, eax
0x1800268a5  jz      short loc_1800268B3
0x1800268a7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800268ae  jmp     loc_180026814
0x1800268b3  lea     rcx, qword_1800EB130
0x1800268ba  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800268c1  jmp     loc_180026814
0x1800268c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800268cd  lea     r8, WPP_2790e164590a3ed111972434a23f3cea_Traceguids
0x1800268d4  mov     eax, [rdi]
0x1800268d6  mov     edx, 54h ; 'T'
0x1800268db  mov     r9, rbp
0x1800268de  mov     [rsp+48h+var_28], eax
0x1800268e2  mov     rcx, [rcx+88h]
0x1800268e9  call    WPP_SF_qD
0x1800268ee  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800268f5  jmp     loc_180026734
0x1800268fa  mov     r8, r14
0x1800268fd  mov     rcx, rbp
0x180026900  call    ?CompletePESCollection_@CMpeg2PESStreamParser@@IEAAHPEAUIMediaSample@@PEAV?$CTStickyVal@H@@@Z; CMpeg2PESStreamParser::CompletePESCollection_(IMediaSample *,CTStickyVal<int> *)
0x180026905  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002690c  mov     [rdi], r15d
0x18002690f  jmp     loc_180026740
0x180026914  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002691b  nop     dword ptr [rax+rax+00h]
0x180026920  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180026927  mov     rcx, rax
0x18002692a  test    rax, rax
0x18002692d  jz      short loc_180026950
0x18002692f  mov     rax, [rax]
0x180026932  mov     edx, 7F0h
0x180026937  mov     rax, [rax+8]
0x18002693b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026940  test    eax, eax
0x180026942  jz      short loc_180026950
0x180026944  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002694b  jmp     loc_18002684F
0x180026950  lea     rcx, qword_1800EB130
0x180026957  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002695e  jmp     loc_18002684F
```
