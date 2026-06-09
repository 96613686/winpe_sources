# CPaintBeat::UpdateWMTimer(void)

- ea: `0x1803756c8`
- end: `0x180375c77`
- name: `?UpdateWMTimer@CPaintBeat@@AEAAXXZ`
- size: `1455`
- prototype: `void __fastcall(CPaintBeat *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180374fe8`
- `0x1803764f0`

## callees

- `0x1801cd074`
- `0x1803756c8`
- `0x18037659c`
- `0x18079b8d4`
- `0x1810c2caa`
- `0x1810d1010`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x180375823`
- `KERNEL32!QueryPerformanceCounter` at `0x180375823`
- `KERNEL32!QueryPerformanceFrequency` at `0x180375be9`
- `KERNEL32!QueryPerformanceFrequency` at `0x180375be9`
- `KERNEL32!GetCurrentThreadId` at `0x180375b41`
- `KERNEL32!GetCurrentThreadId` at `0x180375ba3`
- `KERNEL32!GetCurrentThreadId` at `0x180375b41`
- `KERNEL32!GetCurrentThreadId` at `0x180375ba3`
- `USER32!GetWindowThreadProcessId` at `0x180375b39`
- `USER32!GetWindowThreadProcessId` at `0x180375b9b`
- `USER32!GetWindowThreadProcessId` at `0x180375b39`
- `USER32!GetWindowThreadProcessId` at `0x180375b9b`
- `USER32!SetTimer` at `0x180375b87`
- `USER32!SetTimer` at `0x180375bd7`
- `USER32!SetTimer` at `0x180375b87`
- `USER32!SetTimer` at `0x180375bd7`
- `USER32!KillTimer` at `0x1803757ef`
- `USER32!KillTimer` at `0x1803757ef`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180375a25`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180375a35`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180375a94`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180375aa4`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180375bb1`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180375a25`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180375a35`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180375a94`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180375aa4`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x180375bb1`

## pseudocode

```c
void __fastcall CPaintBeat::UpdateWMTimer(CPaintBeat *this)
{
  int v1; // r12d
  __int64 **v3; // rcx
  __int64 *v4; // rbx
  __int64 *i; // rax
  unsigned __int64 v6; // r14
  __int64 v7; // rbp
  __int64 v8; // rbp
  __int64 v9; // rbx
  int v10; // eax
  int v11; // esi
  __int64 v12; // rbx
  UINT_PTR v13; // rbx
  __int64 v14; // r9
  int v15; // ecx
  __int64 v16; // rsi
  LARGE_INTEGER v17; // r9
  LARGE_INTEGER v18; // r8
  unsigned __int64 v19; // r8
  UINT v20; // ebp
  __int64 v21; // r13
  _QWORD *ThreadLocalStoragePointer; // rax
  __int64 v23; // rbx
  __int64 v24; // rax
  __int64 v25; // r14
  UINT v26; // r15d
  __int64 v27; // rax
  int v28; // ecx
  __int64 j; // rsi
  CImplAry *v30; // rcx
  int v31; // r8d
  __int64 v32; // r10
  __int64 v33; // rcx
  __int64 v34; // r9
  unsigned int v35; // eax
  int v36; // edx
  __int64 v37; // r8
  unsigned int v38; // ebx
  __int64 v39; // rax
  int v40; // r15d
  HWND v41; // rcx
  UINT_PTR v42; // rax
  __int64 v43; // rcx
  __int64 v44; // r14
  __int64 v45; // rsi
  int v46; // ecx
  GUID v47; // xmm0
  HWND *v48; // r14
  __int128 v49; // xmm0
  __int64 (__fastcall *v50)(HWND, UINT_PTR, _QWORD, _QWORD, _DWORD); // rax
  UINT_PTR v51; // rdx
  HWND v52; // rcx
  DWORD v54; // ebx
  DWORD WindowThreadProcessId; // ebx
  LARGE_INTEGER PerformanceCount; // [rsp+80h] [rbp+8h] BYREF
  __int64 v57; // [rsp+88h] [rbp+10h]
  __int64 v58; // [rsp+90h] [rbp+18h]
  unsigned __int64 v59; // [rsp+98h] [rbp+20h]

  v1 = 0;
  v3 = (__int64 **)((char *)this + 288);
  v4 = 0;
  for ( i = *v3; i != (__int64 *)v3; i = (__int64 *)*i )
  {
    if ( !*((_BYTE *)i + 44) )
    {
      v4 = i;
      break;
    }
  }
  if ( v4 )
  {
    v6 = v4[7];
    v59 = v6;
    if ( *((_BYTE *)this + 101) && *((_QWORD *)this + 10) <= v6 )
      return;
    v16 = *((_QWORD *)this + 1);
    PerformanceCount.QuadPart = 0;
    QueryPerformanceCounter(&PerformanceCount);
    v17 = CQPCTick::s_qpcFrequency;
    if ( CQPCTick::s_qpcFrequency.QuadPart
      || (QueryPerformanceFrequency(&CQPCTick::s_qpcFrequency),
          v17 = CQPCTick::s_qpcFrequency,
          CQPCTick::s_qpcFrequency.QuadPart) )
    {
      v18 = PerformanceCount;
      if ( PerformanceCount.QuadPart && v17.QuadPart && v17.QuadPart != 1000 )
        v18.QuadPart = 1000 * (PerformanceCount.QuadPart % (unsigned __int64)v17.QuadPart) / v17.QuadPart
                     + 1000 * (PerformanceCount.QuadPart / (unsigned __int64)v17.QuadPart);
    }
    else
    {
      v18.QuadPart = 0;
    }
    v19 = v18.QuadPart - *(_QWORD *)(v16 + 536);
    v20 = 0;
    if ( v4[7] > v19 )
    {
      v20 = -1;
      if ( v6 - v19 < 0xFFFFFFFF )
        v20 = v6 - v19;
    }
    v21 = 0;
    ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
    v23 = 16;
    v57 = 16;
    v58 = ThreadLocalStoragePointer[(unsigned int)tls_index];
    v24 = *(_QWORD *)(v58 + 16);
    if ( v24 )
      v21 = *(_QWORD *)(v24 + 232);
    if ( *(_QWORD *)(v21 + 96) )
    {
      v25 = 0;
      if ( v24 )
        v25 = *(_QWORD *)(v24 + 232);
      v26 = v20;
      if ( v20 < 0xA )
        v26 = 10;
      v27 = *(_QWORD *)(v25 + 112);
      v28 = *(_DWORD *)(v27 + 4);
      for ( j = *(_QWORD *)(v27 + 8); ; j += 56 )
      {
        if ( v28 <= 0 )
          goto LABEL_45;
        if ( *(CPaintBeat **)j == this && *(_DWORD *)(j + 16) == 206 )
          break;
        --v28;
      }
      if ( *(_DWORD *)(j + 24) != v26 )
        *(_DWORD *)(j + 24) = v26;
      if ( *(_DWORD *)(j + 32) )
        goto LABEL_74;
      if ( *((_BYTE *)GlobalThreadState() + 16) )
      {
        v48 = (HWND *)(v25 + 96);
        v49 = *(_OWORD *)GlobalThreadState();
      }
      else
      {
        v48 = (HWND *)(v25 + 96);
        WindowThreadProcessId = GetWindowThreadProcessId(*v48, 0);
        v49 = WindowThreadProcessId == GetCurrentThreadId() ? *(_OWORD *)GlobalThreadState() : *(_OWORD *)&GUID_NULL;
        v23 = v57;
      }
      v50 = (__int64 (__fastcall *)(HWND, UINT_PTR, _QWORD, _QWORD, _DWORD))qword_181591D28;
      v51 = *(unsigned int *)(j + 20);
      *(_OWORD *)(j + 40) = v49;
      v52 = *v48;
      if ( v50 ? v50(v52, v51, v26, 0, *(_DWORD *)(j + 28)) : SetTimer(v52, v51, v26, 0) )
      {
LABEL_74:
        if ( (Microsoft_IEEnableBits & 0x100000) != 0 )
          McTemplateU0pqpq_EventWriteTransfer(
            v28,
            (unsigned int)MSHTML_FORMSTIMER_RESET,
            *(_QWORD *)j,
            *(_DWORD *)(j + 16),
            *(_QWORD *)(j + 8),
            *(_DWORD *)(j + 24));
LABEL_64:
        *((_QWORD *)this + 10) = v59;
        *((_BYTE *)this + 101) = 1;
        return;
      }
LABEL_45:
      v30 = *(CImplAry **)(v21 + 112);
      v31 = *((_DWORD *)v30 + 1) + 1;
      if ( (unsigned int)v31 > *(_DWORD *)v30 >> 2 )
      {
        if ( v31 < 0 )
          goto LABEL_89;
        v1 = CImplAry::EnsureSizeWorker(v30, 0x38u, v31);
        if ( v1 )
          goto LABEL_63;
      }
      v32 = v58;
      v33 = *(_QWORD *)(v58 + v23);
      if ( v33 )
        v33 = *(_QWORD *)(v33 + 232);
      v34 = *(_QWORD *)(v33 + 112);
LABEL_49:
      v35 = *(_DWORD *)(v33 + 104) + 1;
      *(_DWORD *)(v33 + 104) = v35;
      if ( v35 < 0x2002 )
      {
        *(_DWORD *)(v33 + 104) = 8194;
        v35 = 8194;
      }
      v36 = *(_DWORD *)(v34 + 4);
      v37 = *(_QWORD *)(v34 + 8);
      while ( v36 > 0 )
      {
        if ( v35 == *(_DWORD *)(v37 + 20) )
          goto LABEL_49;
        --v36;
        v37 += 56;
      }
      v38 = *(_DWORD *)(v33 + 104);
      if ( v20 < 0xA )
        v20 = 10;
      v39 = *(_QWORD *)(v32 + v57);
      v40 = *(unsigned __int8 *)(v39 + 583);
      if ( *(_BYTE *)(v39 + 583)
        || ((v41 = *(HWND *)(v21 + 96), !qword_181591D28)
          ? (v42 = SetTimer(v41, v38, v20, 0))
          : (v42 = ((__int64 (__fastcall *)(HWND, _QWORD, _QWORD))qword_181591D28)(v41, v38, v20)),
            v42) )
      {
        v43 = *(_QWORD *)(v21 + 112);
        v44 = *(_QWORD *)(v43 + 8);
        v45 = 56LL * *(int *)(v43 + 4);
        *(_QWORD *)(v45 + v44) = this;
        *(_QWORD *)(v45 + v44 + 8) = CPaintBeat::OnWMTimer;
        *(_DWORD *)(v45 + v44 + 20) = v38;
        *(_DWORD *)(v45 + v44 + 16) = 206;
        *(_DWORD *)(v45 + v44 + 24) = v20;
        *(_DWORD *)(v45 + v44 + 36) = 1;
        *(_DWORD *)(v45 + v44 + 32) = v40;
        *(_DWORD *)(v45 + v44 + 28) = 0;
        if ( *((_BYTE *)GlobalThreadState() + 16)
          || (v54 = GetWindowThreadProcessId(*(HWND *)(v21 + 96), 0), v54 == GetCurrentThreadId()) )
        {
          v47 = *(GUID *)GlobalThreadState();
        }
        else
        {
          v47 = GUID_NULL;
        }
        *(GUID *)(v45 + v44 + 40) = v47;
        ++*(_DWORD *)(*(_QWORD *)(v21 + 112) + 4LL);
        if ( (Microsoft_IEEnableBits & 0x100000) != 0 )
          McTemplateU0pqpq_EventWriteTransfer(
            v46,
            (unsigned int)MSHTML_FORMSTIMER_SET,
            (_DWORD)this,
            206,
            (char)CPaintBeat::OnWMTimer,
            v20);
LABEL_63:
        if ( v1 < 0 )
          goto LABEL_89;
        goto LABEL_64;
      }
    }
LABEL_89:
    CPaintBeat::StopWMTimer(this);
    return;
  }
  if ( *((_BYTE *)this + 101) )
  {
    v7 = *(_QWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 16LL);
    if ( v7 )
    {
      v8 = *(_QWORD *)(v7 + 232);
      if ( v8 )
      {
        v9 = *(_QWORD *)(v8 + 112);
        if ( v9 )
        {
          v10 = *(_DWORD *)(v9 + 4);
          v11 = 0;
          v12 = *(_QWORD *)(v9 + 8);
          while ( v10 > 0 )
          {
            if ( *(CPaintBeat **)v12 == this && *(_DWORD *)(v12 + 16) == 206 )
            {
              if ( (Microsoft_IEEnableBits & 0x100000) != 0 )
                McTemplateU0pqpq_EventWriteTransfer(
                  206,
                  (unsigned int)MSHTML_FORMSTIMER_KILL,
                  *(_QWORD *)v12,
                  206,
                  *(_QWORD *)(v12 + 8),
                  *(_DWORD *)(v12 + 24));
              v13 = *(unsigned int *)(v12 + 20);
              if ( v11 >= 0 )
              {
                v14 = *(_QWORD *)(v8 + 112);
                v15 = *(_DWORD *)(v14 + 4);
                if ( v11 < v15 )
                {
                  *(_DWORD *)(v14 + 4) = v15 - 1;
                  if ( v11 < (unsigned int)(v15 - 1) )
                    memmove_0(
                      (void *)(*(_QWORD *)(v14 + 8) + 56LL * v11),
                      (const void *)(*(_QWORD *)(v14 + 8) + 56LL * (v11 + 1)),
                      56LL * (unsigned int)(v15 - v11 - 1));
                }
              }
              KillTimer(*(HWND *)(v8 + 96), v13);
              break;
            }
            --v10;
            ++v11;
            v12 += 56;
          }
        }
      }
    }
    *((_BYTE *)this + 101) = 0;
    *((_QWORD *)this + 10) = 0;
  }
}

```

## disassembly

```asm
0x1803756c8  push    rbx
0x1803756ca  push    rbp
0x1803756cb  push    rsi
0x1803756cc  push    rdi
0x1803756cd  push    r12
0x1803756cf  push    r13
0x1803756d1  push    r14
0x1803756d3  push    r15
0x1803756d5  sub     rsp, 38h
0x1803756d9  xor     r12d, r12d
0x1803756dc  mov     rdi, rcx
0x1803756df  add     rcx, 120h
0x1803756e6  mov     ebx, r12d
0x1803756e9  mov     rax, [rcx]
0x1803756ec  cmp     rax, rcx
0x1803756ef  jz      short loc_1803756FE
0x1803756f1  cmp     [rax+2Ch], r12b
0x1803756f5  jnz     loc_180375B60
0x1803756fb  mov     rbx, rax
0x1803756fe  test    rbx, rbx
0x180375701  jz      short loc_180375734
0x180375703  mov     r14, [rbx+38h]
0x180375707  mov     [rsp+78h+arg_18], r14
0x18037570f  cmp     [rdi+65h], r12b
0x180375713  jz      loc_18037580F
0x180375719  cmp     [rdi+50h], r14
0x18037571d  ja      loc_18037580F
0x180375723  add     rsp, 38h
0x180375727  pop     r15
0x180375729  pop     r14
0x18037572b  pop     r13
0x18037572d  pop     r12
0x18037572f  pop     rdi
0x180375730  pop     rsi
0x180375731  pop     rbp
0x180375732  pop     rbx
0x180375733  retn
0x180375734  cmp     [rdi+65h], r12b
0x180375738  jz      short loc_180375723
0x18037573a  mov     edx, cs:_tls_index
0x180375740  mov     rax, gs:58h
0x180375749  mov     r8d, 10h
0x18037574f  mov     rax, [rax+rdx*8]
0x180375753  mov     rbp, [r8+rax]
0x180375757  test    rbp, rbp
0x18037575a  jz      loc_1803757F5
0x180375760  mov     rbp, [rbp+0E8h]
0x180375767  test    rbp, rbp
0x18037576a  jz      loc_1803757F5
0x180375770  mov     rbx, [rbp+70h]
0x180375774  test    rbx, rbx
0x180375777  jz      short loc_1803757F5
0x180375779  mov     eax, [rbx+4]
0x18037577c  mov     esi, r12d
0x18037577f  mov     rbx, [rbx+8]
0x180375783  mov     ecx, 0CEh
0x180375788  test    eax, eax
0x18037578a  jle     short loc_1803757F5
0x18037578c  cmp     [rbx], rdi
0x18037578f  jnz     short loc_180375802
0x180375791  cmp     [rbx+10h], ecx
0x180375794  jnz     short loc_180375802
0x180375796  test    byte ptr cs:Microsoft_IEEnableBits+2, 10h
0x18037579d  jnz     loc_180375C07
0x1803757a3  mov     ebx, [rbx+14h]
0x1803757a6  test    esi, esi
0x1803757a8  js      short loc_1803757E8
0x1803757aa  mov     r9, [rbp+70h]
0x1803757ae  mov     ecx, [r9+4]
0x1803757b2  cmp     esi, ecx
0x1803757b4  jge     short loc_1803757E8
0x1803757b6  lea     eax, [rcx-1]
0x1803757b9  mov     [r9+4], eax
0x1803757bd  cmp     esi, eax
0x1803757bf  jnb     short loc_1803757E8
0x1803757c1  sub     ecx, esi
0x1803757c3  lea     eax, [rcx-1]
0x1803757c6  imul    r8, rax, 38h ; '8'; Size
0x1803757ca  lea     eax, [rsi+1]
0x1803757cd  movsxd  rdx, eax
0x1803757d0  movsxd  rax, esi
0x1803757d3  imul    rcx, rax, 38h ; '8'
0x1803757d7  imul    rdx, 38h ; '8'
0x1803757db  add     rcx, [r9+8]; void *
0x1803757df  add     rdx, [r9+8]; Src
0x1803757e3  call    memmove_0
0x1803757e8  mov     rcx, [rbp+60h]; hWnd
0x1803757ec  mov     rdx, rbx; uIDEvent
0x1803757ef  call    cs:__imp_KillTimer
0x1803757f5  mov     [rdi+65h], r12b
0x1803757f9  mov     [rdi+50h], r12
0x1803757fd  jmp     loc_180375723
0x180375802  dec     eax
0x180375804  inc     esi
0x180375806  add     rbx, 38h ; '8'
0x18037580a  jmp     loc_180375788
0x18037580f  mov     rsi, [rdi+8]
0x180375813  lea     rcx, [rsp+78h+PerformanceCount]; lpPerformanceCount
0x18037581b  mov     qword ptr [rsp+78h+PerformanceCount], r12
0x180375823  call    cs:__imp_QueryPerformanceCounter
0x180375829  mov     r9, qword ptr cs:?s_qpcFrequency@CQPCTick@@0_KA; unsigned __int64 CQPCTick::s_qpcFrequency ...
0x180375830  test    r9, r9
0x180375833  jz      loc_180375BE2
0x180375839  mov     r8, qword ptr [rsp+78h+PerformanceCount]
0x180375841  test    r8, r8
0x180375844  jz      short loc_18037587C
0x180375846  test    r9, r9
0x180375849  jz      short loc_18037587C
0x18037584b  cmp     r9, 3E8h
0x180375852  jz      short loc_18037587C
0x180375854  xor     edx, edx
0x180375856  mov     rax, r8
0x180375859  div     r9
0x18037585c  xor     edx, edx
0x18037585e  mov     rcx, rax
0x180375861  imul    rax, r9
0x180375865  sub     r8, rax
0x180375868  imul    rax, r8, 3E8h
0x18037586f  imul    r8, rcx, 3E8h
0x180375876  div     r9
0x180375879  add     r8, rax
0x18037587c  sub     r8, [rsi+218h]
0x180375883  mov     ebp, r12d
0x180375886  cmp     [rbx+38h], r8
0x18037588a  jbe     short loc_1803758A0
0x18037588c  mov     rax, r14
0x18037588f  mov     ebp, 0FFFFFFFFh
0x180375894  sub     rax, r8
0x180375897  cmp     rax, rbp
0x18037589a  jb      loc_180375C58
0x1803758a0  mov     ecx, cs:_tls_index
0x1803758a6  mov     r13, r12
0x1803758a9  mov     rax, gs:58h
0x1803758b2  mov     r8d, 10h
0x1803758b8  mov     ebx, r8d
0x1803758bb  mov     [rsp+78h+arg_8], rbx
0x1803758c3  mov     rax, [rax+rcx*8]
0x1803758c7  mov     [rsp+78h+arg_10], rax
0x1803758cf  mov     rax, [rax+r8]
0x1803758d3  test    rax, rax
0x1803758d6  jz      short loc_1803758DF
0x1803758d8  mov     r13, [rax+0E8h]
0x1803758df  cmp     [r13+60h], r12
0x1803758e3  jz      loc_180375BC7
0x1803758e9  mov     r14, r12
0x1803758ec  test    rax, rax
0x1803758ef  jz      short loc_1803758F8
0x1803758f1  mov     r14, [rax+0E8h]
0x1803758f8  mov     eax, 0Ah
0x1803758fd  mov     r15d, ebp
0x180375900  cmp     ebp, eax
0x180375902  cmovb   r15d, eax
0x180375906  mov     rax, [r14+70h]
0x18037590a  mov     ecx, [rax+4]
0x18037590d  mov     rsi, [rax+8]
0x180375911  test    ecx, ecx
0x180375913  jle     short loc_180375926
0x180375915  cmp     [rsi], rdi
0x180375918  jz      loc_180375A77
0x18037591e  dec     ecx
0x180375920  add     rsi, 38h ; '8'
0x180375924  jmp     short loc_180375911
0x180375926  mov     rcx, [r13+70h]; this
0x18037592a  mov     r8d, [rcx+4]
0x18037592e  mov     eax, [rcx]
0x180375930  inc     r8d; int
0x180375933  shr     eax, 2
0x180375936  cmp     r8d, eax
0x180375939  ja      loc_180375B68
0x18037593f  mov     r10, [rsp+78h+arg_10]
0x180375947  mov     rcx, [r10+rbx]
0x18037594b  test    rcx, rcx
0x18037594e  jz      loc_180375B5B
0x180375954  mov     rcx, [rcx+0E8h]
0x18037595b  mov     r9, [rcx+70h]
0x18037595f  mov     r11d, 2002h
0x180375965  mov     eax, [rcx+68h]
0x180375968  inc     eax
0x18037596a  mov     [rcx+68h], eax
0x18037596d  cmp     eax, r11d
0x180375970  jb      loc_180375C6B
0x180375976  mov     edx, [r9+4]
0x18037597a  mov     r8, [r9+8]
0x18037597e  test    edx, edx
0x180375980  jg      loc_180375B1E
0x180375986  mov     ebx, [rcx+68h]
0x180375989  mov     eax, 0Ah
0x18037598e  cmp     ebp, eax
0x180375990  cmovb   ebp, eax
0x180375993  mov     rax, [rsp+78h+arg_8]
0x18037599b  mov     rax, [r10+rax]
0x18037599f  movzx   r15d, byte ptr [rax+247h]
0x1803759a7  test    r15d, r15d
0x1803759aa  jnz     short loc_1803759DB
0x1803759ac  mov     rax, cs:qword_181591D28
0x1803759b3  xor     r9d, r9d; lpTimerFunc
0x1803759b6  mov     rcx, [r13+60h]; hWnd
0x1803759ba  mov     edx, ebx; nIDEvent
0x1803759bc  mov     r8d, ebp; uElapse
0x1803759bf  test    rax, rax
0x1803759c2  jz      loc_180375B87
0x1803759c8  mov     dword ptr [rsp+78h+var_58], r9d
0x1803759cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1803759d2  test    rax, rax
0x1803759d5  jz      loc_180375BC7
0x1803759db  mov     rcx, [r13+70h]
0x1803759df  movsxd  rax, dword ptr [rcx+4]
0x1803759e3  mov     r14, [rcx+8]
0x1803759e7  imul    rsi, rax, 38h ; '8'
0x1803759eb  lea     rax, ?OnWMTimer@CPaintBeat@@AEAAJI@Z; CPaintBeat::OnWMTimer(uint)
0x1803759f2  mov     [rsi+r14], rdi
0x1803759f6  mov     [rsi+r14+8], rax
0x1803759fb  mov     [rsi+r14+14h], ebx
0x180375a00  mov     dword ptr [rsi+r14+10h], 0CEh
0x180375a09  mov     [rsi+r14+18h], ebp
0x180375a0e  mov     dword ptr [rsi+r14+24h], 1
0x180375a17  mov     [rsi+r14+20h], r15d
0x180375a1c  mov     dword ptr [rsi+r14+1Ch], 0
0x180375a25  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180375a2b  cmp     byte ptr [rax+10h], 0
0x180375a2f  jz      loc_180375B33
0x180375a35  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180375a3b  movups  xmm0, xmmword ptr [rax]
0x180375a3e  movdqu  xmmword ptr [rsi+r14+28h], xmm0
0x180375a45  mov     rax, [r13+70h]
0x180375a49  inc     dword ptr [rax+4]
0x180375a4c  test    byte ptr cs:Microsoft_IEEnableBits+2, 10h
0x180375a53  jnz     loc_180375C2E
0x180375a59  test    r12d, r12d
0x180375a5c  js      loc_180375BC7
0x180375a62  mov     rax, [rsp+78h+arg_18]
0x180375a6a  mov     [rdi+50h], rax
0x180375a6e  mov     byte ptr [rdi+65h], 1
0x180375a72  jmp     loc_180375723
0x180375a77  cmp     dword ptr [rsi+10h], 0CEh
0x180375a7e  jnz     loc_18037591E
0x180375a84  cmp     [rsi+18h], r15d
0x180375a88  jz      short loc_180375A8E
0x180375a8a  mov     [rsi+18h], r15d
0x180375a8e  cmp     [rsi+20h], r12d
0x180375a92  jnz     short loc_180375AE9
0x180375a94  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180375a9a  cmp     [rax+10h], r12b
0x180375a9e  jz      loc_180375B92
0x180375aa4  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x180375aaa  add     r14, 60h ; '`'
0x180375aae  movups  xmm0, xmmword ptr [rax]
0x180375ab1  mov     rax, cs:qword_181591D28
0x180375ab8  mov     r8d, r15d; uElapse
0x180375abb  mov     edx, [rsi+14h]; nIDEvent
0x180375abe  movdqu  xmmword ptr [rsi+28h], xmm0
0x180375ac3  mov     rcx, [r14]; hWnd
0x180375ac6  test    rax, rax
0x180375ac9  jz      loc_180375BD4
0x180375acf  mov     r9d, [rsi+1Ch]
0x180375ad3  mov     dword ptr [rsp+78h+var_58], r9d
0x180375ad8  xor     r9d, r9d
0x180375adb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180375ae0  test    rax, rax
0x180375ae3  jz      loc_180375926
0x180375ae9  test    byte ptr cs:Microsoft_IEEnableBits+2, 10h
0x180375af0  jz      loc_180375A62
0x180375af6  mov     eax, [rsi+18h]
0x180375af9  lea     rdx, MSHTML_FORMSTIMER_RESET
0x180375b00  mov     r9d, [rsi+10h]
0x180375b04  mov     r8, [rsi]
0x180375b07  mov     [rsp+78h+var_50], eax
0x180375b0b  mov     rax, [rsi+8]
0x180375b0f  mov     [rsp+78h+var_58], rax
0x180375b14  call    McTemplateU0pqpq_EventWriteTransfer
0x180375b19  jmp     loc_180375A62
0x180375b1e  cmp     eax, [r8+14h]
0x180375b22  jz      loc_180375965
0x180375b28  dec     edx
0x180375b2a  add     r8, 38h ; '8'
0x180375b2e  jmp     loc_18037597E
0x180375b33  mov     rcx, [r13+60h]; hWnd
0x180375b37  xor     edx, edx; lpdwProcessId
0x180375b39  call    cs:__imp_GetWindowThreadProcessId
0x180375b3f  mov     ebx, eax
0x180375b41  call    cs:__imp_GetCurrentThreadId
0x180375b47  cmp     ebx, eax
0x180375b49  jz      loc_180375A35
0x180375b4f  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180375b56  jmp     loc_180375A3E
0x180375b5b  jmp     loc_18037595B
0x180375b60  mov     rax, [rax]
0x180375b63  jmp     loc_1803756EC
0x180375b68  test    r8d, r8d
0x180375b6b  js      short loc_180375BC7
0x180375b6d  mov     edx, 38h ; '8'; unsigned __int64
0x180375b72  call    ?EnsureSizeWorker@CImplAry@@AEAAJ_KJ@Z; CImplAry::EnsureSizeWorker(unsigned __int64,long)
0x180375b77  mov     r12d, eax
0x180375b7a  test    eax, eax
0x180375b7c  jz      loc_18037593F
0x180375b82  jmp     loc_180375A59
0x180375b87  call    cs:__imp_SetTimer
0x180375b8d  jmp     loc_1803759D2
0x180375b92  add     r14, 60h ; '`'
0x180375b96  xor     edx, edx; lpdwProcessId
  ... truncated ...
```
