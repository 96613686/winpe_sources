# CMediaSampleCopyBuffer::ReleaseCopyBuffer(unsigned __int64,uchar *,int)

- ea: `0x18002a810`
- end: `0x18002aae3`
- name: `?ReleaseCopyBuffer@CMediaSampleCopyBuffer@@UEAAJ_KPEAEH@Z`
- size: `723`
- prototype: `__int64 __fastcall(CMediaSampleCopyBuffer *__hidden this, unsigned __int64, unsigned __int8 *, int)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18002a810`
- `0x18007c8e8`
- `0x1800aa4ec`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a873`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a914`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a873`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a914`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a848`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a8e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a991`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a9c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a848`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a8e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a991`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a9c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a96d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002a96d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002a859`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002a8fa`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002a859`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18002a8fa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002aa14`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002aa94`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002aa14`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18002aa94`

## string_xrefs

- `0x18002a897`: `CMediaSampleCopyBuffer::ReleaseCopyBuffer`

## pseudocode

```c
__int64 __fastcall CMediaSampleCopyBuffer::ReleaseCopyBuffer(
        CMediaSampleCopyBuffer *this,
        __int64 a2,
        unsigned __int8 *a3,
        int a4)
{
  CallStackTracing *v4; // rdi
  char *v9; // rbx
  DWORD LastError; // ebp
  char *Value; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  GUID *v14; // rbx
  DWORD v15; // esi
  GUID *v16; // rax
  int v17; // eax
  int v18; // eax
  CallStackTracing *v20; // rcx
  __int64 v21; // rax
  CallStackTracing *v22; // rcx
  __int64 v23; // rax
  CallStackTracing *v24; // rax
  CallStackTracing *v25; // rax

  v4 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v4 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v4 + 8) )
  {
    v9 = (char *)v4 + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v4 + 3));
    if ( Value )
    {
      v9 = Value;
    }
    else if ( !GetLastError() )
    {
      v20 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v24;
        if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
        {
          v20 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v20 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      v21 = (**(__int64 (__fastcall ***)(CallStackTracing *))v20)(v20);
      if ( v21 )
        v9 = (char *)v21;
    }
    SetLastError(LastError);
    v12 = *((unsigned int *)v9 + 497);
    v4 = CallStackTracing::s_wpInstance;
    if ( (unsigned int)v12 < *((_DWORD *)v9 + 498) )
    {
      v13 = 2 * v12;
      *(_QWORD *)&v9[8 * v13] = "CMediaSampleCopyBuffer::ReleaseCopyBuffer";
      *(_DWORD *)&v9[8 * v13 + 8] = 472;
    }
    ++*((_DWORD *)v9 + 497);
  }
  if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
  {
    WPP_SF_qiqD(*((_QWORD *)WPP_GLOBAL_Control + 17), a2, a3, this, a2, a3, a4);
    v4 = CallStackTracing::s_wpInstance;
  }
  if ( a2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 16LL))(a2);
    v4 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v4 + 8) )
  {
    v14 = (GUID *)((char *)v4 + 208);
    v15 = GetLastError();
    v16 = (GUID *)TlsGetValue(*((_DWORD *)v4 + 3));
    if ( v16 )
    {
      v14 = v16;
    }
    else if ( !GetLastError() )
    {
      v22 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v25;
        if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
        {
          v22 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v22 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      v23 = (**(__int64 (__fastcall ***)(CallStackTracing *))v22)(v22);
      if ( v23 )
        v14 = (GUID *)v23;
    }
    SetLastError(v15);
    v17 = *(_DWORD *)&v14[124].Data2;
    if ( v17 )
    {
      v18 = v17 - 1;
      *(_DWORD *)&v14[124].Data2 = v18;
      if ( !v18 )
      {
        *(_DWORD *)&v14[124].Data2 = 0;
        *(_QWORD *)&v14[126].Data1 = 0;
        *(_DWORD *)&v14[124].Data4[4] = 0;
        v14[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v14[126].Data4 = 0;
        v14[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002a810  push    rbx
0x18002a812  push    rbp
0x18002a813  push    rsi
0x18002a814  push    rdi
0x18002a815  push    r12
0x18002a817  push    r14
0x18002a819  push    r15
0x18002a81b  sub     rsp, 40h
0x18002a81f  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a826  mov     r14d, r9d
0x18002a829  mov     r15, r8
0x18002a82c  mov     rsi, rdx
0x18002a82f  mov     r12, rcx
0x18002a832  test    rdi, rdi
0x18002a835  jz      loc_18002AA03
0x18002a83b  cmp     byte ptr [rdi+8], 0
0x18002a83f  jz      short loc_18002A8B0
0x18002a841  lea     rbx, [rdi+0D0h]
0x18002a848  call    cs:__imp_GetLastError
0x18002a84f  nop     dword ptr [rax+rax+00h]
0x18002a854  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18002a857  mov     ebp, eax
0x18002a859  call    cs:__imp_TlsGetValue
0x18002a860  nop     dword ptr [rax+rax+00h]
0x18002a865  test    rax, rax
0x18002a868  jz      loc_18002A991
0x18002a86e  mov     rbx, rax
0x18002a871  mov     ecx, ebp; dwErrCode
0x18002a873  call    cs:__imp_SetLastError
0x18002a87a  nop     dword ptr [rax+rax+00h]
0x18002a87f  mov     eax, [rbx+7C4h]
0x18002a885  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a88c  cmp     eax, [rbx+7C8h]
0x18002a892  jnb     short loc_18002A8AA
0x18002a894  add     rax, rax
0x18002a897  lea     rcx, aCmediasampleco_2; "CMediaSampleCopyBuffer::ReleaseCopyBuff"...
0x18002a89e  mov     [rbx+rax*8], rcx
0x18002a8a2  mov     dword ptr [rbx+rax*8+8], 1D8h
0x18002a8aa  inc     dword ptr [rbx+7C4h]
0x18002a8b0  cmp     cs:byte_1800EACCB, 20h ; ' '
0x18002a8b7  jnb     loc_18002AA63
0x18002a8bd  test    rsi, rsi
0x18002a8c0  jz      short loc_18002A8D8
0x18002a8c2  mov     rax, [rsi]
0x18002a8c5  mov     rcx, rsi
0x18002a8c8  mov     rax, [rax+10h]
0x18002a8cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a8d1  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a8d8  cmp     byte ptr [rdi+8], 0
0x18002a8dc  jz      loc_18002A97F
0x18002a8e2  lea     rbx, [rdi+0D0h]
0x18002a8e9  call    cs:__imp_GetLastError
0x18002a8f0  nop     dword ptr [rax+rax+00h]
0x18002a8f5  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18002a8f8  mov     esi, eax
0x18002a8fa  call    cs:__imp_TlsGetValue
0x18002a901  nop     dword ptr [rax+rax+00h]
0x18002a906  test    rax, rax
0x18002a909  jz      loc_18002A9C8
0x18002a90f  mov     rbx, rax
0x18002a912  mov     ecx, esi; dwErrCode
0x18002a914  call    cs:__imp_SetLastError
0x18002a91b  nop     dword ptr [rax+rax+00h]
0x18002a920  mov     eax, [rbx+7C4h]
0x18002a926  test    eax, eax
0x18002a928  jz      short loc_18002A97F
0x18002a92a  sub     eax, 1
0x18002a92d  mov     [rbx+7C4h], eax
0x18002a933  jnz     short loc_18002A97F
0x18002a935  mov     dword ptr [rbx+7C4h], 0
0x18002a93f  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18002a946  mov     qword ptr [rbx+7E0h], 0
0x18002a951  mov     dword ptr [rbx+7CCh], 0
0x18002a95b  movdqu  xmmword ptr [rbx+7D0h], xmm0
0x18002a963  mov     dword ptr [rbx+7E8h], 0
0x18002a96d  call    cs:__imp_GetCurrentThreadId
0x18002a974  nop     dword ptr [rax+rax+00h]
0x18002a979  mov     [rbx+7C0h], eax
0x18002a97f  xor     eax, eax
0x18002a981  add     rsp, 40h
0x18002a985  pop     r15
0x18002a987  pop     r14
0x18002a989  pop     r12
0x18002a98b  pop     rdi
0x18002a98c  pop     rsi
0x18002a98d  pop     rbp
0x18002a98e  pop     rbx
0x18002a98f  retn
0x18002a991  call    cs:__imp_GetLastError
0x18002a998  nop     dword ptr [rax+rax+00h]
0x18002a99d  test    eax, eax
0x18002a99f  jnz     loc_18002A871
0x18002a9a5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a9ac  test    rcx, rcx
0x18002a9af  jz      short loc_18002AA14
0x18002a9b1  mov     rax, [rcx]
0x18002a9b4  mov     rax, [rax]
0x18002a9b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a9bc  test    rax, rax
0x18002a9bf  cmovnz  rbx, rax
0x18002a9c3  jmp     loc_18002A871
0x18002a9c8  call    cs:__imp_GetLastError
0x18002a9cf  nop     dword ptr [rax+rax+00h]
0x18002a9d4  test    eax, eax
0x18002a9d6  jnz     loc_18002A912
0x18002a9dc  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002a9e3  test    rcx, rcx
0x18002a9e6  jz      loc_18002AA94
0x18002a9ec  mov     rax, [rcx]
0x18002a9ef  mov     rax, [rax]
0x18002a9f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a9f7  test    rax, rax
0x18002a9fa  cmovnz  rbx, rax
0x18002a9fe  jmp     loc_18002A912
0x18002aa03  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18002aa08  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002aa0f  jmp     loc_18002A83B
0x18002aa14  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002aa1b  nop     dword ptr [rax+rax+00h]
0x18002aa20  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002aa27  mov     rcx, rax
0x18002aa2a  test    rax, rax
0x18002aa2d  jz      short loc_18002AA50
0x18002aa2f  mov     rax, [rax]
0x18002aa32  mov     edx, 7F0h
0x18002aa37  mov     rax, [rax+8]
0x18002aa3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aa40  test    eax, eax
0x18002aa42  jz      short loc_18002AA50
0x18002aa44  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002aa4b  jmp     loc_18002A9B1
0x18002aa50  lea     rcx, qword_1800EB130
0x18002aa57  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002aa5e  jmp     loc_18002A9B1
0x18002aa63  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aa6a  mov     r9, r12
0x18002aa6d  mov     [rsp+78h+var_48], r14d
0x18002aa72  mov     [rsp+78h+var_50], r15
0x18002aa77  mov     [rsp+78h+var_58], rsi
0x18002aa7c  mov     rcx, [rcx+88h]
0x18002aa83  call    WPP_SF_qiqD
0x18002aa88  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002aa8f  jmp     loc_18002A8BD
0x18002aa94  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18002aa9b  nop     dword ptr [rax+rax+00h]
0x18002aaa0  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18002aaa7  mov     rcx, rax
0x18002aaaa  test    rax, rax
0x18002aaad  jz      short loc_18002AAD0
0x18002aaaf  mov     rax, [rax]
0x18002aab2  mov     edx, 7F0h
0x18002aab7  mov     rax, [rax+8]
0x18002aabb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002aac0  test    eax, eax
0x18002aac2  jz      short loc_18002AAD0
0x18002aac4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18002aacb  jmp     loc_18002A9EC
0x18002aad0  lea     rcx, qword_1800EB130
0x18002aad7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18002aade  jmp     loc_18002A9EC
```
