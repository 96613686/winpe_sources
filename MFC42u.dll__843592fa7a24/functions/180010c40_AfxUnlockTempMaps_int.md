# AfxUnlockTempMaps(int)

- ea: `0x180010c40`
- end: `0x18001135d`
- name: `?AfxUnlockTempMaps@@YAHH@Z`
- size: `1821`
- prototype: `__int64 __fastcall(int)`
- caller_count: `6`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x18000a210`
- `0x18000f990`
- `0x180013db0`
- `0x180014040`
- `0x1800273b0`
- `0x180050a20`

## callees

- `0x18000f800`
- `0x180010c40`
- `0x180012bec`
- `0x180012eb0`
- `0x180013330`
- `0x1800136f0`
- `0x18001f110`
- `0x18002d800`
- `0x18002da20`
- `0x1800d7010`

## import_xrefs

- `msvcrt!_msize` at `0x18001112d`
- `msvcrt!_msize` at `0x180011345`
- `msvcrt!_msize` at `0x18001112d`
- `msvcrt!_msize` at `0x180011345`
- `msvcrt!free` at `0x180010d60`
- `msvcrt!free` at `0x180010d7e`
- `msvcrt!free` at `0x180010e40`
- `msvcrt!free` at `0x180010e5e`
- `msvcrt!free` at `0x180010f20`
- `msvcrt!free` at `0x180010f3e`
- `msvcrt!free` at `0x180011000`
- `msvcrt!free` at `0x18001101e`
- `msvcrt!free` at `0x18001104c`
- `msvcrt!free` at `0x18001106a`
- `msvcrt!free` at `0x180011352`
- `msvcrt!free` at `0x180010d60`
- `msvcrt!free` at `0x180010d7e`
- `msvcrt!free` at `0x180010e40`
- `msvcrt!free` at `0x180010e5e`
- `msvcrt!free` at `0x180010f20`
- `msvcrt!free` at `0x180010f3e`
- `msvcrt!free` at `0x180011000`
- `msvcrt!free` at `0x18001101e`
- `msvcrt!free` at `0x18001104c`
- `msvcrt!free` at `0x18001106a`
- `msvcrt!free` at `0x180011352`
- `msvcrt!malloc` at `0x18001116e`
- `msvcrt!malloc` at `0x180011185`
- `msvcrt!malloc` at `0x18001116e`
- `msvcrt!malloc` at `0x180011185`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800110bb`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800110bb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800110aa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800110aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800110dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800110ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800110dc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800110ec`

## pseudocode

```c
_BOOL8 __fastcall AfxUnlockTempMaps(int a1)
{
  struct AFX_MODULE_THREAD_STATE *ModuleThreadState; // rax
  struct AFX_MODULE_THREAD_STATE *v3; // rsi
  int v4; // edx
  int v5; // edx
  __int64 v6; // rcx
  void (__fastcall *v7)(_QWORD, _QWORD); // rax
  __int64 v8; // rdi
  __int64 v9; // rbp
  __int64 v10; // rbx
  __int64 v11; // r8
  unsigned int v12; // edx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  __int64 i; // rdx
  __int64 v16; // rcx
  __int64 v17; // rax
  void *v18; // rcx
  _QWORD *v19; // rcx
  _QWORD *v20; // rbx
  __int64 v21; // rdi
  __int64 v22; // rbx
  __int64 v23; // r8
  unsigned int v24; // edx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  __int64 j; // rdx
  __int64 v28; // rcx
  __int64 v29; // rax
  void *v30; // rcx
  _QWORD *v31; // rcx
  _QWORD *v32; // rbx
  __int64 v33; // rdi
  __int64 v34; // rbx
  __int64 v35; // r8
  unsigned int v36; // edx
  unsigned int v37; // ecx
  unsigned int v38; // ecx
  __int64 k; // rdx
  __int64 v40; // rcx
  __int64 v41; // rax
  void *v42; // rcx
  _QWORD *v43; // rcx
  _QWORD *v44; // rbx
  __int64 v45; // rdi
  __int64 v46; // rbx
  __int64 v47; // r8
  unsigned int v48; // edx
  unsigned int v49; // ecx
  unsigned int v50; // ecx
  __int64 m; // rdx
  __int64 v52; // rcx
  __int64 v53; // rax
  void *v54; // rcx
  _QWORD *v55; // rcx
  _QWORD *v56; // rbx
  __int64 v57; // rdi
  void *v58; // rcx
  _QWORD *v59; // rcx
  _QWORD *v60; // rbx
  struct AFX_MODULE_STATE *ModuleState; // rax
  struct _RTL_CRITICAL_SECTION *v62; // rdi
  __int64 v63; // rbp
  int v64; // ebx
  _DWORD *Value; // rax
  struct _RTL_CRITICAL_SECTION *v66; // rcx
  void **Object; // rdi
  void *v68; // rcx
  size_t v69; // rbx
  void *v71; // rcx
  size_t v72; // rbx
  void *v73; // rax
  void *v74; // rax
  __int64 v75; // r8
  unsigned int v76; // edx
  unsigned int v77; // ecx
  unsigned int v78; // ecx
  __int64 n; // rdx
  __int64 v80; // rcx
  __int64 v81; // rax

  ModuleThreadState = AfxGetModuleThreadState();
  v3 = ModuleThreadState;
  v4 = *((_DWORD *)ModuleThreadState + 8);
  if ( !v4 )
    return *((_DWORD *)v3 + 8) != 0;
  v5 = v4 - 1;
  *((_DWORD *)ModuleThreadState + 8) = v5;
  if ( v5 )
    return *((_DWORD *)v3 + 8) != 0;
  if ( a1 )
  {
    if ( a1 != -1 )
    {
      v6 = *((_QWORD *)AfxGetModuleThreadState() + 1);
      if ( v6 || (v6 = *((_QWORD *)AfxGetModuleState() + 1)) != 0 )
      {
        v7 = *(void (__fastcall **)(_QWORD, _QWORD))(v6 + 168);
        if ( v7 )
          v7(0, 0);
      }
    }
    v8 = *((_QWORD *)v3 + 8);
    v9 = -1;
    if ( v8 )
    {
      if ( *(_QWORD *)(v8 + 80) )
      {
        v10 = -1;
        do
        {
          v11 = v10;
          if ( v10 == -1 )
          {
            v12 = *(_DWORD *)(v8 + 72);
            if ( v12 )
            {
              v13 = 0;
              while ( 1 )
              {
                v11 = *(_QWORD *)(*(_QWORD *)(v8 + 64) + 8LL * v13);
                if ( v11 )
                  break;
                if ( ++v13 >= v12 )
                {
                  v16 = 0;
                  v10 = 0;
                  goto LABEL_20;
                }
              }
            }
          }
          v10 = *(_QWORD *)v11;
          if ( !*(_QWORD *)v11 )
          {
            v14 = *(_DWORD *)(v8 + 72);
            for ( i = (*(_DWORD *)(v11 + 8) >> 4) % v14 + 1; (unsigned int)i < v14; i = (unsigned int)(i + 1) )
            {
              v10 = *(_QWORD *)(*(_QWORD *)(v8 + 64) + 8 * i);
              if ( v10 )
                break;
            }
          }
          v16 = *(_QWORD *)(v11 + 16);
LABEL_20:
          v17 = *(_QWORD *)(v8 + 120);
          *(_QWORD *)(v17 + v16) = 0;
          if ( *(_DWORD *)(v8 + 128) == 2 )
            *(_QWORD *)(v17 + v16 + 8) = 0;
          if ( v16 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v16 + 8LL))(v16, 1);
        }
        while ( v10 );
      }
      v18 = *(void **)(v8 + 64);
      if ( v18 )
      {
        free(v18);
        *(_QWORD *)(v8 + 64) = 0;
      }
      v19 = *(_QWORD **)(v8 + 96);
      *(_QWORD *)(v8 + 80) = 0;
      *(_QWORD *)(v8 + 88) = 0;
      if ( v19 )
      {
        do
        {
          v20 = (_QWORD *)*v19;
          free(v19);
          v19 = v20;
        }
        while ( v20 );
      }
      *(_QWORD *)(v8 + 96) = 0;
    }
    v21 = *((_QWORD *)v3 + 7);
    if ( v21 )
    {
      if ( *(_QWORD *)(v21 + 80) )
      {
        v22 = -1;
        do
        {
          v23 = v22;
          if ( v22 == -1 )
          {
            v24 = *(_DWORD *)(v21 + 72);
            if ( v24 )
            {
              v25 = 0;
              while ( 1 )
              {
                v23 = *(_QWORD *)(*(_QWORD *)(v21 + 64) + 8LL * v25);
                if ( v23 )
                  break;
                if ( ++v25 >= v24 )
                {
                  v28 = 0;
                  v22 = 0;
                  goto LABEL_42;
                }
              }
            }
          }
          v22 = *(_QWORD *)v23;
          if ( !*(_QWORD *)v23 )
          {
            v26 = *(_DWORD *)(v21 + 72);
            for ( j = (*(_DWORD *)(v23 + 8) >> 4) % v26 + 1; (unsigned int)j < v26; j = (unsigned int)(j + 1) )
            {
              v22 = *(_QWORD *)(*(_QWORD *)(v21 + 64) + 8 * j);
              if ( v22 )
                break;
            }
          }
          v28 = *(_QWORD *)(v23 + 16);
LABEL_42:
          v29 = *(_QWORD *)(v21 + 120);
          *(_QWORD *)(v29 + v28) = 0;
          if ( *(_DWORD *)(v21 + 128) == 2 )
            *(_QWORD *)(v29 + v28 + 8) = 0;
          if ( v28 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v28 + 8LL))(v28, 1);
        }
        while ( v22 );
      }
      v30 = *(void **)(v21 + 64);
      if ( v30 )
      {
        free(v30);
        *(_QWORD *)(v21 + 64) = 0;
      }
      v31 = *(_QWORD **)(v21 + 96);
      *(_QWORD *)(v21 + 80) = 0;
      *(_QWORD *)(v21 + 88) = 0;
      if ( v31 )
      {
        do
        {
          v32 = (_QWORD *)*v31;
          free(v31);
          v31 = v32;
        }
        while ( v32 );
      }
      *(_QWORD *)(v21 + 96) = 0;
    }
    v33 = *((_QWORD *)v3 + 6);
    if ( v33 )
    {
      if ( *(_QWORD *)(v33 + 80) )
      {
        v34 = -1;
        do
        {
          v35 = v34;
          if ( v34 == -1 )
          {
            v36 = *(_DWORD *)(v33 + 72);
            if ( v36 )
            {
              v37 = 0;
              while ( 1 )
              {
                v35 = *(_QWORD *)(*(_QWORD *)(v33 + 64) + 8LL * v37);
                if ( v35 )
                  break;
                if ( ++v37 >= v36 )
                {
                  v40 = 0;
                  v34 = 0;
                  goto LABEL_64;
                }
              }
            }
          }
          v34 = *(_QWORD *)v35;
          if ( !*(_QWORD *)v35 )
          {
            v38 = *(_DWORD *)(v33 + 72);
            for ( k = (*(_DWORD *)(v35 + 8) >> 4) % v38 + 1; (unsigned int)k < v38; k = (unsigned int)(k + 1) )
            {
              v34 = *(_QWORD *)(*(_QWORD *)(v33 + 64) + 8 * k);
              if ( v34 )
                break;
            }
          }
          v40 = *(_QWORD *)(v35 + 16);
LABEL_64:
          v41 = *(_QWORD *)(v33 + 120);
          *(_QWORD *)(v41 + v40) = 0;
          if ( *(_DWORD *)(v33 + 128) == 2 )
            *(_QWORD *)(v41 + v40 + 8) = 0;
          if ( v40 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v40 + 8LL))(v40, 1);
        }
        while ( v34 );
      }
      v42 = *(void **)(v33 + 64);
      if ( v42 )
      {
        free(v42);
        *(_QWORD *)(v33 + 64) = 0;
      }
      v43 = *(_QWORD **)(v33 + 96);
      *(_QWORD *)(v33 + 80) = 0;
      *(_QWORD *)(v33 + 88) = 0;
      if ( v43 )
      {
        do
        {
          v44 = (_QWORD *)*v43;
          free(v43);
          v43 = v44;
        }
        while ( v44 );
      }
      *(_QWORD *)(v33 + 96) = 0;
    }
    v45 = *((_QWORD *)v3 + 5);
    if ( v45 )
    {
      if ( *(_QWORD *)(v45 + 80) )
      {
        v46 = -1;
        do
        {
          v47 = v46;
          if ( v46 == -1 )
          {
            v48 = *(_DWORD *)(v45 + 72);
            if ( v48 )
            {
              v49 = 0;
              while ( 1 )
              {
                v47 = *(_QWORD *)(*(_QWORD *)(v45 + 64) + 8LL * v49);
                if ( v47 )
                  break;
                if ( ++v49 >= v48 )
                {
                  v52 = 0;
                  v46 = 0;
                  goto LABEL_86;
                }
              }
            }
          }
          v46 = *(_QWORD *)v47;
          if ( !*(_QWORD *)v47 )
          {
            v50 = *(_DWORD *)(v45 + 72);
            for ( m = (*(_DWORD *)(v47 + 8) >> 4) % v50 + 1; (unsigned int)m < v50; m = (unsigned int)(m + 1) )
            {
              v46 = *(_QWORD *)(*(_QWORD *)(v45 + 64) + 8 * m);
              if ( v46 )
                break;
            }
          }
          v52 = *(_QWORD *)(v47 + 16);
LABEL_86:
          v53 = *(_QWORD *)(v45 + 120);
          *(_QWORD *)(v53 + v52) = 0;
          if ( *(_DWORD *)(v45 + 128) == 2 )
            *(_QWORD *)(v53 + v52 + 8) = 0;
          if ( v52 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v52 + 8LL))(v52, 1);
        }
        while ( v46 );
      }
      v54 = *(void **)(v45 + 64);
      if ( v54 )
      {
        free(v54);
        *(_QWORD *)(v45 + 64) = 0;
      }
      v55 = *(_QWORD **)(v45 + 96);
      *(_QWORD *)(v45 + 80) = 0;
      *(_QWORD *)(v45 + 88) = 0;
      if ( v55 )
      {
        do
        {
          v56 = (_QWORD *)*v55;
          free(v55);
          v55 = v56;
        }
        while ( v56 );
      }
      *(_QWORD *)(v45 + 96) = 0;
    }
    v57 = *((_QWORD *)v3 + 9);
    if ( v57 )
    {
      if ( *(_QWORD *)(v57 + 80) )
      {
        do
        {
          v75 = v9;
          if ( v9 == -1 )
          {
            v76 = *(_DWORD *)(v57 + 72);
            if ( v76 )
            {
              v77 = 0;
              while ( 1 )
              {
                v75 = *(_QWORD *)(*(_QWORD *)(v57 + 64) + 8LL * v77);
                if ( v75 )
                  break;
                if ( ++v77 >= v76 )
                {
                  v80 = 0;
                  v9 = 0;
                  goto LABEL_133;
                }
              }
            }
          }
          v9 = *(_QWORD *)v75;
          if ( !*(_QWORD *)v75 )
          {
            v78 = *(_DWORD *)(v57 + 72);
            for ( n = (*(_DWORD *)(v75 + 8) >> 4) % v78 + 1; (unsigned int)n < v78; n = (unsigned int)(n + 1) )
            {
              v9 = *(_QWORD *)(*(_QWORD *)(v57 + 64) + 8 * n);
              if ( v9 )
                break;
            }
          }
          v80 = *(_QWORD *)(v75 + 16);
LABEL_133:
          v81 = *(_QWORD *)(v57 + 120);
          *(_QWORD *)(v80 + v81) = 0;
          if ( *(_DWORD *)(v57 + 128) == 2 )
            *(_QWORD *)(v80 + v81 + 8) = 0;
          if ( v80 )
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v80 + 8LL))(v80, 1);
        }
        while ( v9 );
      }
      v58 = *(void **)(v57 + 64);
      if ( v58 )
      {
        free(v58);
        *(_QWORD *)(v57 + 64) = 0;
      }
      v59 = *(_QWORD **)(v57 + 96);
      *(_QWORD *)(v57 + 80) = 0;
      *(_QWORD *)(v57 + 88) = 0;
      if ( v59 )
      {
        do
        {
          v60 = (_QWORD *)*v59;
          free(v59);
          v59 = v60;
        }
        while ( v60 );
      }
      *(_QWORD *)(v57 + 96) = 0;
    }
  }
  ModuleState = AfxGetModuleState();
  v62 = (struct _RTL_CRITICAL_SECTION *)_afxThreadData;
  v63 = *((_QWORD *)ModuleState + 1);
  if ( !_afxThreadData )
  {
    _afxThreadData = CThreadSlotData::CThreadSlotData((CThreadSlotData *)&__afxThreadData);
    v62 = (struct _RTL_CRITICAL_SECTION *)_afxThreadData;
    if ( !_afxThreadData )
LABEL_142:
      AfxThrowInvalidArgException();
  }
  v64 = _afxThreadState;
  if ( !_afxThreadState )
  {
    _afxThreadState = CThreadSlotData::AllocSlot((CThreadSlotData *)v62);
    v64 = _afxThreadState;
    if ( !_afxThreadState )
      goto LABEL_142;
    v62 = (struct _RTL_CRITICAL_SECTION *)_afxThreadData;
  }
  EnterCriticalSection(v62 + 1);
  if ( v64 <= 0 || v64 >= v62->RecursionCount || (Value = TlsGetValue((DWORD)v62->DebugInfo)) == 0 || v64 >= Value[4] )
  {
    LeaveCriticalSection(v62 + 1);
LABEL_112:
    Object = (void **)CThreadLocal<_AFX_THREAD_STATE>::CreateObject();
    CThreadSlotData::SetValue(_afxThreadData, _afxThreadState, Object);
    if ( !Object )
      goto LABEL_142;
    goto LABEL_113;
  }
  _mm_lfence();
  v66 = v62 + 1;
  Object = *(void ***)(*((_QWORD *)Value + 3) + 8LL * v64);
  LeaveCriticalSection(v66);
  if ( !Object )
    goto LABEL_112;
LABEL_113:
  if ( v63 )
  {
    v68 = Object[3];
    if ( !v68 || (v69 = *(_QWORD *)(v63 + 344), _msize(v68) < v69) )
    {
      if ( *(_QWORD *)(v63 + 344) )
      {
        v71 = Object[3];
        v72 = 0;
        if ( v71 )
        {
          v72 = _msize(v71);
          free(Object[3]);
        }
        v73 = malloc(*(_QWORD *)(v63 + 344));
        Object[3] = v73;
        if ( !v73 )
        {
          if ( v72 )
          {
            v74 = malloc(v72);
            Object[3] = v74;
            if ( !v74 )
              AfxThrowMemoryException();
          }
        }
      }
    }
  }
  return *((_DWORD *)v3 + 8) != 0;
}

```

## disassembly

```asm
0x180010c40  push    rbx
0x180010c42  push    rbp
0x180010c43  push    rsi
0x180010c44  push    rdi
0x180010c45  push    r14
0x180010c47  push    r15
0x180010c49  sub     rsp, 28h
0x180010c4d  mov     ebx, ecx
0x180010c4f  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x180010c54  xor     r15d, r15d
0x180010c57  mov     rsi, rax
0x180010c5a  mov     edx, [rax+20h]
0x180010c5d  test    edx, edx
0x180010c5f  jz      loc_180011138
0x180010c65  sub     edx, 1
0x180010c68  mov     [rax+20h], edx
0x180010c6b  jnz     loc_180011138
0x180010c71  test    ebx, ebx
0x180010c73  jz      loc_18001107C
0x180010c79  cmp     ebx, 0FFFFFFFFh
0x180010c7c  jz      short loc_180010CA0
0x180010c7e  call    ?AfxGetModuleThreadState@@YAPEAVAFX_MODULE_THREAD_STATE@@XZ; AfxGetModuleThreadState(void)
0x180010c83  mov     rcx, [rax+8]
0x180010c87  test    rcx, rcx
0x180010c8a  jz      loc_18001124A
0x180010c90  mov     rax, [rcx+0A8h]
0x180010c97  test    rax, rax
0x180010c9a  jnz     loc_18001123C
0x180010ca0  mov     rdi, [rsi+40h]
0x180010ca4  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x180010cab  test    rdi, rdi
0x180010cae  jz      loc_180010D90
0x180010cb4  cmp     [rdi+50h], r15
0x180010cb8  jz      loc_180010D57
0x180010cbe  mov     rbx, rbp
0x180010cc1  mov     r8, rbx
0x180010cc4  cmp     rbx, rbp
0x180010cc7  jnz     short loc_180010CEF
0x180010cc9  mov     edx, [rdi+48h]
0x180010ccc  test    edx, edx
0x180010cce  jz      short loc_180010CEF
0x180010cd0  mov     r9, [rdi+40h]
0x180010cd4  mov     ecx, r15d
0x180010cd7  nop     word ptr [rax+rax+00000000h]
0x180010ce0  mov     eax, ecx
0x180010ce2  mov     r8, [r9+rax*8]
0x180010ce6  test    r8, r8
0x180010ce9  jz      loc_1800112B8
0x180010cef  mov     rbx, [r8]
0x180010cf2  test    rbx, rbx
0x180010cf5  jnz     short loc_180010D1F
0x180010cf7  mov     ecx, [rdi+48h]
0x180010cfa  xor     edx, edx
0x180010cfc  mov     eax, [r8+8]
0x180010d00  shr     eax, 4
0x180010d03  div     ecx
0x180010d05  inc     edx
0x180010d07  cmp     edx, ecx
0x180010d09  jnb     short loc_180010D1F
0x180010d0b  mov     r9, [rdi+40h]
0x180010d0f  nop
0x180010d10  mov     rbx, [r9+rdx*8]
0x180010d14  test    rbx, rbx
0x180010d17  jnz     short loc_180010D1F
0x180010d19  inc     edx
0x180010d1b  cmp     edx, ecx
0x180010d1d  jb      short loc_180010D10
0x180010d1f  mov     rcx, [r8+10h]
0x180010d23  mov     rax, [rdi+78h]
0x180010d27  mov     [rax+rcx], r15
0x180010d2b  cmp     dword ptr [rdi+80h], 2
0x180010d32  jz      loc_180011286
0x180010d38  test    rcx, rcx
0x180010d3b  jz      short loc_180010D4E
0x180010d3d  mov     rax, [rcx]
0x180010d40  mov     edx, 1
0x180010d45  mov     rax, [rax+8]
0x180010d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d4e  test    rbx, rbx
0x180010d51  jnz     loc_180010CC1
0x180010d57  mov     rcx, [rdi+40h]; Block
0x180010d5b  test    rcx, rcx
0x180010d5e  jz      short loc_180010D6A
0x180010d60  call    cs:__imp_free
0x180010d66  mov     [rdi+40h], r15
0x180010d6a  mov     rcx, [rdi+60h]; Block
0x180010d6e  mov     [rdi+50h], r15
0x180010d72  mov     [rdi+58h], r15
0x180010d76  test    rcx, rcx
0x180010d79  jz      short loc_180010D8C
0x180010d7b  mov     rbx, [rcx]
0x180010d7e  call    cs:__imp_free
0x180010d84  mov     rcx, rbx
0x180010d87  test    rbx, rbx
0x180010d8a  jnz     short loc_180010D7B
0x180010d8c  mov     [rdi+60h], r15
0x180010d90  mov     rdi, [rsi+38h]
0x180010d94  test    rdi, rdi
0x180010d97  jz      loc_180010E70
0x180010d9d  cmp     [rdi+50h], r15
0x180010da1  jz      loc_180010E37
0x180010da7  mov     rbx, rbp
0x180010daa  mov     r8, rbx
0x180010dad  cmp     rbx, rbp
0x180010db0  jnz     short loc_180010DCF
0x180010db2  mov     edx, [rdi+48h]
0x180010db5  test    edx, edx
0x180010db7  jz      short loc_180010DCF
0x180010db9  mov     r9, [rdi+40h]
0x180010dbd  mov     ecx, r15d
0x180010dc0  mov     eax, ecx
0x180010dc2  mov     r8, [r9+rax*8]
0x180010dc6  test    r8, r8
0x180010dc9  jz      loc_1800112CD
0x180010dcf  mov     rbx, [r8]
0x180010dd2  test    rbx, rbx
0x180010dd5  jnz     short loc_180010DFF
0x180010dd7  mov     ecx, [rdi+48h]
0x180010dda  xor     edx, edx
0x180010ddc  mov     eax, [r8+8]
0x180010de0  shr     eax, 4
0x180010de3  div     ecx
0x180010de5  inc     edx
0x180010de7  cmp     edx, ecx
0x180010de9  jnb     short loc_180010DFF
0x180010deb  mov     r9, [rdi+40h]
0x180010def  nop
0x180010df0  mov     rbx, [r9+rdx*8]
0x180010df4  test    rbx, rbx
0x180010df7  jnz     short loc_180010DFF
0x180010df9  inc     edx
0x180010dfb  cmp     edx, ecx
0x180010dfd  jb      short loc_180010DF0
0x180010dff  mov     rcx, [r8+10h]
0x180010e03  mov     rax, [rdi+78h]
0x180010e07  mov     [rax+rcx], r15
0x180010e0b  cmp     dword ptr [rdi+80h], 2
0x180010e12  jz      loc_180011290
0x180010e18  test    rcx, rcx
0x180010e1b  jz      short loc_180010E2E
0x180010e1d  mov     rax, [rcx]
0x180010e20  mov     edx, 1
0x180010e25  mov     rax, [rax+8]
0x180010e29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e2e  test    rbx, rbx
0x180010e31  jnz     loc_180010DAA
0x180010e37  mov     rcx, [rdi+40h]; Block
0x180010e3b  test    rcx, rcx
0x180010e3e  jz      short loc_180010E4A
0x180010e40  call    cs:__imp_free
0x180010e46  mov     [rdi+40h], r15
0x180010e4a  mov     rcx, [rdi+60h]; Block
0x180010e4e  mov     [rdi+50h], r15
0x180010e52  mov     [rdi+58h], r15
0x180010e56  test    rcx, rcx
0x180010e59  jz      short loc_180010E6C
0x180010e5b  mov     rbx, [rcx]
0x180010e5e  call    cs:__imp_free
0x180010e64  mov     rcx, rbx
0x180010e67  test    rbx, rbx
0x180010e6a  jnz     short loc_180010E5B
0x180010e6c  mov     [rdi+60h], r15
0x180010e70  mov     rdi, [rsi+30h]
0x180010e74  test    rdi, rdi
0x180010e77  jz      loc_180010F50
0x180010e7d  cmp     [rdi+50h], r15
0x180010e81  jz      loc_180010F17
0x180010e87  mov     rbx, rbp
0x180010e8a  mov     r8, rbx
0x180010e8d  cmp     rbx, rbp
0x180010e90  jnz     short loc_180010EAF
0x180010e92  mov     edx, [rdi+48h]
0x180010e95  test    edx, edx
0x180010e97  jz      short loc_180010EAF
0x180010e99  mov     r9, [rdi+40h]
0x180010e9d  mov     ecx, r15d
0x180010ea0  mov     eax, ecx
0x180010ea2  mov     r8, [r9+rax*8]
0x180010ea6  test    r8, r8
0x180010ea9  jz      loc_1800112E2
0x180010eaf  mov     rbx, [r8]
0x180010eb2  test    rbx, rbx
0x180010eb5  jnz     short loc_180010EDF
0x180010eb7  mov     ecx, [rdi+48h]
0x180010eba  xor     edx, edx
0x180010ebc  mov     eax, [r8+8]
0x180010ec0  shr     eax, 4
0x180010ec3  div     ecx
0x180010ec5  inc     edx
0x180010ec7  cmp     edx, ecx
0x180010ec9  jnb     short loc_180010EDF
0x180010ecb  mov     r9, [rdi+40h]
0x180010ecf  nop
0x180010ed0  mov     rbx, [r9+rdx*8]
0x180010ed4  test    rbx, rbx
0x180010ed7  jnz     short loc_180010EDF
0x180010ed9  inc     edx
0x180010edb  cmp     edx, ecx
0x180010edd  jb      short loc_180010ED0
0x180010edf  mov     rcx, [r8+10h]
0x180010ee3  mov     rax, [rdi+78h]
0x180010ee7  mov     [rax+rcx], r15
0x180010eeb  cmp     dword ptr [rdi+80h], 2
0x180010ef2  jz      loc_18001129A
0x180010ef8  test    rcx, rcx
0x180010efb  jz      short loc_180010F0E
0x180010efd  mov     rax, [rcx]
0x180010f00  mov     edx, 1
0x180010f05  mov     rax, [rax+8]
0x180010f09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f0e  test    rbx, rbx
0x180010f11  jnz     loc_180010E8A
0x180010f17  mov     rcx, [rdi+40h]; Block
0x180010f1b  test    rcx, rcx
0x180010f1e  jz      short loc_180010F2A
0x180010f20  call    cs:__imp_free
0x180010f26  mov     [rdi+40h], r15
0x180010f2a  mov     rcx, [rdi+60h]; Block
0x180010f2e  mov     [rdi+50h], r15
0x180010f32  mov     [rdi+58h], r15
0x180010f36  test    rcx, rcx
0x180010f39  jz      short loc_180010F4C
0x180010f3b  mov     rbx, [rcx]
0x180010f3e  call    cs:__imp_free
0x180010f44  mov     rcx, rbx
0x180010f47  test    rbx, rbx
0x180010f4a  jnz     short loc_180010F3B
0x180010f4c  mov     [rdi+60h], r15
0x180010f50  mov     rdi, [rsi+28h]
0x180010f54  test    rdi, rdi
0x180010f57  jz      loc_180011030
0x180010f5d  cmp     [rdi+50h], r15
0x180010f61  jz      loc_180010FF7
0x180010f67  mov     rbx, rbp
0x180010f6a  mov     r8, rbx
0x180010f6d  cmp     rbx, rbp
0x180010f70  jnz     short loc_180010F8F
0x180010f72  mov     edx, [rdi+48h]
0x180010f75  test    edx, edx
0x180010f77  jz      short loc_180010F8F
0x180010f79  mov     r9, [rdi+40h]
0x180010f7d  mov     ecx, r15d
0x180010f80  mov     eax, ecx
0x180010f82  mov     r8, [r9+rax*8]
0x180010f86  test    r8, r8
0x180010f89  jz      loc_1800112F7
0x180010f8f  mov     rbx, [r8]
0x180010f92  test    rbx, rbx
0x180010f95  jnz     short loc_180010FBF
0x180010f97  mov     ecx, [rdi+48h]
0x180010f9a  xor     edx, edx
0x180010f9c  mov     eax, [r8+8]
0x180010fa0  shr     eax, 4
0x180010fa3  div     ecx
0x180010fa5  inc     edx
0x180010fa7  cmp     edx, ecx
0x180010fa9  jnb     short loc_180010FBF
0x180010fab  mov     r9, [rdi+40h]
0x180010faf  nop
0x180010fb0  mov     rbx, [r9+rdx*8]
0x180010fb4  test    rbx, rbx
0x180010fb7  jnz     short loc_180010FBF
0x180010fb9  inc     edx
0x180010fbb  cmp     edx, ecx
0x180010fbd  jb      short loc_180010FB0
0x180010fbf  mov     rcx, [r8+10h]
0x180010fc3  mov     rax, [rdi+78h]
0x180010fc7  mov     [rax+rcx], r15
0x180010fcb  cmp     dword ptr [rdi+80h], 2
0x180010fd2  jz      loc_1800112A4
0x180010fd8  test    rcx, rcx
0x180010fdb  jz      short loc_180010FEE
0x180010fdd  mov     rax, [rcx]
0x180010fe0  mov     edx, 1
0x180010fe5  mov     rax, [rax+8]
0x180010fe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fee  test    rbx, rbx
0x180010ff1  jnz     loc_180010F6A
0x180010ff7  mov     rcx, [rdi+40h]; Block
0x180010ffb  test    rcx, rcx
0x180010ffe  jz      short loc_18001100A
0x180011000  call    cs:__imp_free
0x180011006  mov     [rdi+40h], r15
0x18001100a  mov     rcx, [rdi+60h]; Block
0x18001100e  mov     [rdi+50h], r15
0x180011012  mov     [rdi+58h], r15
0x180011016  test    rcx, rcx
0x180011019  jz      short loc_18001102C
0x18001101b  mov     rbx, [rcx]
0x18001101e  call    cs:__imp_free
0x180011024  mov     rcx, rbx
0x180011027  test    rbx, rbx
0x18001102a  jnz     short loc_18001101B
0x18001102c  mov     [rdi+60h], r15
0x180011030  mov     rdi, [rsi+48h]
0x180011034  test    rdi, rdi
0x180011037  jz      short loc_18001107C
0x180011039  cmp     [rdi+50h], r15
0x18001103d  jnz     loc_1800111A0
0x180011043  mov     rcx, [rdi+40h]; Block
  ... truncated ...
```
