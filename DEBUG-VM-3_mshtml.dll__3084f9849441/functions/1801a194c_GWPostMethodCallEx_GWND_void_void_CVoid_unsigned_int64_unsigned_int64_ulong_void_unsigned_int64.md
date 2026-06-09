# _GWPostMethodCallEx(GWND *,void *,void (CVoid::*)(unsigned __int64),unsigned __int64,ulong,void (*)(unsigned __int64))

- ea: `0x1801a194c`
- end: `0x1801a208d`
- name: `?_GWPostMethodCallEx@@YAJPEAVGWND@@PEAXP8CVoid@@EAAX_K@Z2KP6AX2@Z@Z`
- size: `1857`
- prototype: `__int64 __usercall@<rax>(struct GWND *@<rcx>, int, __int64)`
- caller_count: `245`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18006d114`
- `0x1800ae820`
- `0x1800b0560`
- `0x1800d45f0`
- `0x1800f59d0`
- `0x1800f6cd4`
- `0x1801295a0`
- `0x18012d060`
- `0x18013aad0`
- `0x180140914`
- `0x180141104`
- `0x180144d1c`
- `0x18014742c`
- `0x18015111c`
- `0x18015cab4`
- `0x180161144`
- `0x180173580`
- `0x18019e298`
- `0x18019f8a0`
- `0x18019ff00`
- `0x1801a0c28`
- `0x1801a0e20`
- `0x1801a0f18`
- `0x1801a0fc0`
- `0x1801a1274`
- `0x1801a1410`
- `0x1801a16b0`
- `0x1801a281c`
- `0x1801a29a4`
- `0x1801a2d30`
- `0x1801a2d78`
- `0x1801a335c`
- `0x1801cc784`
- `0x180222f00`
- `0x180225dc0`
- `0x180296c10`
- `0x18029a428`
- `0x1802a08f0`
- `0x1802a0cf0`
- `0x1802a181c`
- `0x1802cc134`
- `0x1802fd584`
- `0x18034f380`
- `0x180357db0`
- `0x1803d4250`
- `0x1803e2084`
- `0x1803ea4dc`
- `0x1803ea960`
- `0x180494ed0`
- `0x1804956b4`

## callees

- `0x180146f6c`
- `0x1801a194c`
- `0x1801a23f4`
- `0x1801a2780`
- `0x1801a3478`
- `0x1801a3570`
- `0x1801c0b08`
- `0x1801cd19c`
- `0x1801cd614`
- `0x1801cd678`
- `0x1807691c0`
- `0x18079b8d4`
- `0x1807d659c`
- `0x1810d1010`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1801a1f19`
- `msvcrt!memcpy_s` at `0x1801a1f19`
- `KERNEL32!GetTickCount64` at `0x1801a1e57`
- `KERNEL32!GetTickCount64` at `0x1801a1e57`
- `KERNEL32!GetCurrentThreadId` at `0x1801a1b84`
- `KERNEL32!GetCurrentThreadId` at `0x1801a1f32`
- `KERNEL32!GetCurrentThreadId` at `0x1801a1b84`
- `KERNEL32!GetCurrentThreadId` at `0x1801a1f32`
- `KERNEL32!LeaveCriticalSection` at `0x1801a1b5d`
- `KERNEL32!LeaveCriticalSection` at `0x1801a1b5d`
- `KERNEL32!EnterCriticalSection` at `0x1801a1986`
- `KERNEL32!EnterCriticalSection` at `0x1801a1986`
- `USER32!PostMessageW` at `0x1801a1ae3`
- `USER32!PostMessageW` at `0x1801a1ae3`
- `USER32!GetWindowThreadProcessId` at `0x1801a1b7c`
- `USER32!GetWindowThreadProcessId` at `0x1801a1f2a`
- `USER32!GetWindowThreadProcessId` at `0x1801a1b7c`
- `USER32!GetWindowThreadProcessId` at `0x1801a1f2a`
- `USER32!SetTimer` at `0x1801a1f98`
- `USER32!SetTimer` at `0x1801a1fa7`
- `USER32!SetTimer` at `0x1801a1f98`
- `USER32!SetTimer` at `0x1801a1fa7`
- `USER32!RedrawWindow` at `0x1801a1b49`
- `USER32!RedrawWindow` at `0x1801a1b49`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801a1a5e`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801a1a6e`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801a1e12`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801a1e22`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801a1a5e`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801a1a6e`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801a1e12`
- `msIso!__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ` at `0x1801a1e22`

## pseudocode

```c
__int64 __fastcall _GWPostMethodCallEx(
        struct GWND *a1,
        unsigned __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  signed int LastWin32Error; // edi
  __int64 v8; // r9
  __int64 v9; // r8
  unsigned __int64 v10; // r12
  int v11; // r13d
  int v12; // ecx
  __int64 v13; // rbx
  __int64 v14; // r14
  unsigned int v15; // ebp
  unsigned int v16; // r15d
  __int64 v17; // r14
  __int64 v18; // rbp
  GUID v19; // xmm0
  __int64 v20; // r15
  unsigned __int64 v21; // rbx
  int v22; // r12d
  int v23; // ebp
  ULONGLONG *v24; // r14
  DWORD WindowThreadProcessId; // ebx
  unsigned int v27; // ecx
  unsigned int v28; // ebx
  unsigned __int64 v29; // rcx
  unsigned int v30; // edx
  const void *v31; // r13
  rsize_t v32; // r12
  __int64 v33; // rax
  int i; // edx
  __int64 v35; // rcx
  __int64 v36; // rax
  unsigned int v37; // ecx
  __int64 v38; // r15
  __int64 v39; // r13
  __int64 v40; // r13
  struct GWND *Gwnd; // rdi
  __int64 v42; // rcx
  int v43; // edx
  __int64 j; // rbx
  unsigned int UniqueID; // ebx
  __int64 v46; // rcx
  int v47; // r12d
  HWND v48; // rcx
  UINT_PTR v49; // rax
  __int64 v50; // rcx
  __int64 v51; // rbp
  __int64 v52; // r15
  int v53; // ecx
  GUID v54; // xmm0
  __int128 *UserInputId; // rax
  UINT_PTR v56; // rdx
  __int128 v57; // xmm0
  __int64 (__fastcall *v58)(_QWORD, UINT_PTR, __int64, _QWORD, _DWORD); // rax
  UINT_PTR v59; // rax
  void *v60; // rax
  DWORD v61; // ebx
  int v62; // [rsp+30h] [rbp-78h]
  int v63; // [rsp+34h] [rbp-74h]
  unsigned __int64 v64; // [rsp+38h] [rbp-70h]
  __int64 v65; // [rsp+40h] [rbp-68h]
  struct _RTL_CRITICAL_SECTION *lpCriticalSection; // [rsp+48h] [rbp-60h]
  _BYTE v67[88]; // [rsp+50h] [rbp-58h] BYREF

  lpCriticalSection = (struct _RTL_CRITICAL_SECTION *)((char *)a1 + 192);
  LastWin32Error = -2147467259;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)a1 + 192));
  v9 = *((_QWORD *)a1 + 17);
  if ( !v9 || !*((_QWORD *)a1 + 12) )
    goto LABEL_19;
  v10 = a2;
  if ( !a2 && !a6 )
  {
LABEL_91:
    LastWin32Error = 0;
    goto LABEL_19;
  }
  v11 = a5;
  if ( (a5 & 1) == 0 )
  {
    v8 = a4;
    for ( i = *(_DWORD *)(*((_QWORD *)a1 + 18) + 4 * (a2 % *((unsigned int *)qword_1813BF5B0 + *((int *)a1 + 38))));
          i >= 0;
          i = *(_DWORD *)(v36 + v35 + 56) )
    {
      v35 = *(_QWORD *)(v9 + 8);
      v36 = (__int64)i << 6;
      if ( *(_QWORD *)(v36 + v35) == a2 && *(_QWORD *)(v36 + v35 + 8) == a3 && *(_QWORD *)(v36 + v35 + 16) == a4 )
        goto LABEL_91;
    }
  }
  v12 = *(_DWORD *)(v9 + 4);
  v13 = *((int *)a1 + 38);
  v62 = v12;
  if ( v12 == *((_DWORD *)qword_1813BF5B0 + v13) )
  {
    MemoryProtection::HeapFree((MemoryProtection *)g_hProcessHeap, *((void **)a1 + 18), (void *)v9);
    *((_QWORD *)a1 + 18) = 0;
    *((_DWORD *)a1 + 38) = 0;
    LastWin32Error = AllocateMethodCallBuckets(a1, (int)v13 + 1);
    if ( LastWin32Error )
      goto LABEL_19;
    RehashMethodCalls(a1);
    v12 = v62;
  }
  v14 = *((_QWORD *)a1 + 17);
  v15 = v12 + 1;
  v16 = *(_DWORD *)v14 >> 2;
  if ( v12 + 1 <= v16 )
  {
    LastWin32Error = 0;
    goto LABEL_8;
  }
  if ( (v15 & 0x80000000) != 0 )
  {
    LastWin32Error = -2147024809;
    goto LABEL_19;
  }
  v28 = 4;
  if ( v15 < 4 )
    goto LABEL_29;
  if ( v15 <= 4 )
  {
LABEL_28:
    v28 = v12 + 1;
    goto LABEL_29;
  }
  v28 = v16 + (*(_DWORD *)v14 >> 3);
  if ( v28 >= v16 )
  {
    if ( v15 > v28 )
      goto LABEL_28;
LABEL_29:
    v29 = (unsigned __int64)v28 << 6;
    v30 = v28 << 6;
    if ( v29 > 0xFFFFFFFF )
      v30 = -1;
    LastWin32Error = v29 > 0xFFFFFFFF ? 0x80070216 : 0;
    if ( v29 > 0xFFFFFFFF )
      goto LABEL_37;
    v31 = *(const void **)(v14 + 8);
    v32 = v30;
    if ( (*(_BYTE *)v14 & 2) != 0 )
    {
      v60 = (void *)MemoryProtection::HeapAlloc<1>(g_hProcessHeap, v30, 0xFFFFFFFFLL, v8);
      *(_QWORD *)(v14 + 8) = v60;
      if ( !v60 )
      {
        *(_QWORD *)(v14 + 8) = v31;
LABEL_88:
        LastWin32Error = -2147024882;
        goto LABEL_36;
      }
      memcpy_s(v60, v32, v31, v16 << 6);
    }
    else
    {
      v33 = MemoryProtection::HeapReAlloc<1>(v29, *(_QWORD *)(v14 + 8), v30);
      if ( !v33 && v32 )
        goto LABEL_88;
      *(_QWORD *)(v14 + 8) = v33;
      LastWin32Error = 0;
    }
    *(_DWORD *)v14 &= 1u;
    *(_DWORD *)v14 |= 4 * v28;
LABEL_36:
    v11 = a5;
    v10 = a2;
LABEL_37:
    v12 = v62;
    goto LABEL_38;
  }
  LastWin32Error = -2147024362;
LABEL_38:
  if ( LastWin32Error )
    goto LABEL_19;
LABEL_8:
  v17 = (__int64)v12 << 6;
  *(_DWORD *)(*((_QWORD *)a1 + 17) + 4LL) = v15;
  v18 = *(_QWORD *)(*((_QWORD *)a1 + 17) + 8LL);
  *(_QWORD *)(v17 + v18 + 8) = a3;
  *(_QWORD *)(v17 + v18 + 16) = a4;
  *(_QWORD *)(v17 + v18 + 24) = a6;
  *(_QWORD *)(v17 + v18) = v10;
  *(_DWORD *)(v17 + v18 + 32) = v11;
  *(_DWORD *)(v17 + v18 + 36) = *((_DWORD *)a1 + 32);
  if ( *((_BYTE *)GlobalThreadState() + 16)
    || (WindowThreadProcessId = GetWindowThreadProcessId(*((HWND *)a1 + 12), 0),
        WindowThreadProcessId == GetCurrentThreadId()) )
  {
    v19 = *(GUID *)GlobalThreadState();
  }
  else
  {
    v19 = GUID_NULL;
  }
  *(GUID *)(v17 + v18 + 40) = v19;
  v20 = *((_QWORD *)a1 + 18);
  v65 = v20;
  v21 = v10 % *((unsigned int *)qword_1813BF5B0 + *((int *)a1 + 38));
  v64 = v21;
  v22 = *(_DWORD *)(v20 + 4 * v21);
  *(_DWORD *)(v17 + v18 + 56) = v22;
  v23 = v62;
  *(_DWORD *)(v20 + 4 * v21) = v62;
  v63 = v22;
  if ( (v11 & 2) != 0 )
  {
    v24 = (ULONGLONG *)((char *)a1 + 304);
    if ( *((_BYTE *)a1 + 320) )
    {
      if ( (unsigned __int16)*((_DWORD *)a1 + 31) )
      {
        v37 = *((unsigned __int16 *)a1 + 63);
        if ( (unsigned __int16)*((_DWORD *)a1 + 31) > v37 || v37 >= *((_DWORD *)a1 + 33) )
        {
          LastWin32Error = 0;
          goto LABEL_19;
        }
      }
      LastWin32Error = CGwndPaintRequest::SetupWatchdogTimer((struct GWND *)((char *)a1 + 304));
      if ( LastWin32Error >= 0 )
      {
        if ( *((_BYTE *)a1 + 322) )
        {
LABEL_18:
          RedrawWindow(*((HWND *)a1 + 12), 0, 0, 2u);
          ++*((_WORD *)a1 + 62);
          goto LABEL_19;
        }
        v38 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
        v39 = *(_QWORD *)(v38 + 16);
        if ( v39 )
          v40 = *(_QWORD *)(v39 + 232);
        else
          v40 = 0;
        if ( *(_QWORD *)(v40 + 96) )
        {
          Gwnd = GetGwnd();
          v42 = *((_QWORD *)Gwnd + 14);
          v43 = *(_DWORD *)(v42 + 4);
          for ( j = *(_QWORD *)(v42 + 8); ; j += 56 )
          {
            if ( v43 <= 0 )
              goto LABEL_60;
            if ( *(ULONGLONG **)j == v24 && *(_DWORD *)(j + 16) == 52738 )
              break;
            --v43;
          }
          if ( *(_DWORD *)(j + 24) != 300 )
            *(_DWORD *)(j + 24) = 300;
          if ( *(_DWORD *)(j + 32)
            || ((UserInputId = (__int128 *)GetUserInputId(v67, Gwnd),
                 v56 = *(unsigned int *)(j + 20),
                 v57 = *UserInputId,
                 v58 = (__int64 (__fastcall *)(_QWORD, UINT_PTR, __int64, _QWORD, _DWORD))qword_181591D28,
                 *(_OWORD *)(j + 40) = v57,
                 !v58)
              ? (v59 = SetTimer(*((HWND *)Gwnd + 12), v56, 0x12Cu, 0))
              : (v59 = v58(*((_QWORD *)Gwnd + 12), v56, 300, 0, *(_DWORD *)(j + 28))),
                v59) )
          {
            if ( (Microsoft_IEEnableBits & 0x100000) != 0 )
              McTemplateU0pqpq_EventWriteTransfer(
                v42,
                (unsigned int)MSHTML_FORMSTIMER_RESET,
                *(_QWORD *)j,
                *(_DWORD *)(j + 16),
                *(_QWORD *)(j + 8),
                *(_DWORD *)(j + 24));
            LastWin32Error = 0;
            goto LABEL_70;
          }
LABEL_60:
          LastWin32Error = CImplAry::EnsureSize(
                             *(CImplAry **)(v40 + 112),
                             0x38u,
                             *(_DWORD *)(*(_QWORD *)(v40 + 112) + 4LL) + 1);
          if ( LastWin32Error )
          {
LABEL_69:
            if ( LastWin32Error < 0 )
              goto LABEL_101;
            goto LABEL_70;
          }
          UniqueID = GetUniqueID();
          v46 = *(_QWORD *)(v38 + 16);
          v47 = *(unsigned __int8 *)(v46 + 583);
          if ( *(_BYTE *)(v46 + 583)
            || ((v48 = *(HWND *)(v40 + 96), !qword_181591D28)
              ? (v49 = SetTimer(v48, UniqueID, 0x12Cu, 0))
              : (v49 = ((__int64 (__fastcall *)(HWND, _QWORD, __int64))qword_181591D28)(v48, UniqueID, 300)),
                v49) )
          {
            v50 = *(_QWORD *)(v40 + 112);
            v51 = *(_QWORD *)(v50 + 8);
            v52 = 56LL * *(int *)(v50 + 4);
            *(_DWORD *)(v52 + v51 + 32) = v47;
            *(_QWORD *)(v52 + v51) = v24;
            *(_QWORD *)(v52 + v51 + 8) = CGwndPaintRequest::OnStarveCheckTimer;
            *(_DWORD *)(v52 + v51 + 20) = UniqueID;
            *(_DWORD *)(v52 + v51 + 16) = 52738;
            *(_QWORD *)(v52 + v51 + 24) = 300;
            *(_DWORD *)(v52 + v51 + 36) = 1;
            if ( *((_BYTE *)GlobalThreadState() + 16)
              || (v61 = GetWindowThreadProcessId(*(HWND *)(v40 + 96), 0), v61 == GetCurrentThreadId()) )
            {
              v54 = *(GUID *)GlobalThreadState();
            }
            else
            {
              v54 = GUID_NULL;
            }
            *(GUID *)(v52 + v51 + 40) = v54;
            ++*(_DWORD *)(*(_QWORD *)(v40 + 112) + 4LL);
            if ( (Microsoft_IEEnableBits & 0x100000) != 0 )
            {
              McTemplateU0pqpq_EventWriteTransfer(
                v53,
                (unsigned int)MSHTML_FORMSTIMER_SET,
                (_DWORD)a1 + 304,
                52738,
                (char)CGwndPaintRequest::OnStarveCheckTimer,
                44);
LABEL_70:
              *((_BYTE *)a1 + 322) = 1;
              *v24 = GetTickCount64();
              *((_QWORD *)a1 + 39) = 0;
              goto LABEL_18;
            }
            v23 = v62;
            goto LABEL_69;
          }
        }
        LastWin32Error = -2147467259;
      }
    }
    else
    {
      LastWin32Error = -2147418113;
    }
LABEL_101:
    *(_DWORD *)(*((_QWORD *)a1 + 17) + 4LL) = v23;
    *(_DWORD *)(v65 + 4 * v64) = v63;
    goto LABEL_19;
  }
  if ( !(unsigned __int16)*((_DWORD *)a1 + 30)
    || (v27 = *((unsigned __int16 *)a1 + 61), v27 < *((_DWORD *)a1 + 33))
    && (unsigned __int16)*((_DWORD *)a1 + 30) <= v27 )
  {
    if ( PostMessageW(*((HWND *)a1 + 12), 0x8002u, 0, 0) )
    {
      ++*((_WORD *)a1 + 60);
    }
    else
    {
      LastWin32Error = GetLastWin32Error();
      *(_DWORD *)(*((_QWORD *)a1 + 17) + 4LL) = v62;
      *(_DWORD *)(v20 + 4 * v21) = v22;
    }
  }
LABEL_19:
  LeaveCriticalSection(lpCriticalSection);
  return (unsigned int)LastWin32Error;
}

```

## disassembly

```asm
0x1801a194c  mov     rax, rsp
0x1801a194f  mov     [rax+20h], r9
0x1801a1953  mov     [rax+18h], r8
0x1801a1957  mov     [rax+10h], rdx
0x1801a195b  mov     [rax+8], rcx
0x1801a195f  push    rbx
0x1801a1960  push    rbp
0x1801a1961  push    rsi
0x1801a1962  push    rdi
0x1801a1963  push    r12
0x1801a1965  push    r13
0x1801a1967  push    r14
0x1801a1969  push    r15
0x1801a196b  sub     rsp, 68h
0x1801a196f  lea     rax, [rcx+0C0h]
0x1801a1976  mov     rsi, rcx
0x1801a1979  mov     rcx, rax; lpCriticalSection
0x1801a197c  mov     [rsp+0A8h+lpCriticalSection], rax
0x1801a1981  mov     edi, 80004005h
0x1801a1986  call    cs:__imp_EnterCriticalSection
0x1801a198c  mov     r8, [rsi+88h]; void *
0x1801a1993  xor     ebp, ebp
0x1801a1995  test    r8, r8
0x1801a1998  jz      loc_1801A1B58
0x1801a199e  cmp     [rsi+60h], rbp
0x1801a19a2  jz      loc_1801A1B58
0x1801a19a8  mov     r12, [rsp+0A8h+arg_8]
0x1801a19b0  test    r12, r12
0x1801a19b3  jz      loc_1801A2026
0x1801a19b9  mov     r13d, [rsp+0A8h+arg_20]
0x1801a19c1  lea     r11, qword_1813BF5B0
0x1801a19c8  test    r13b, 1
0x1801a19cc  jz      loc_1801A1C4F
0x1801a19d2  mov     ecx, [r8+4]
0x1801a19d6  movsxd  rbx, dword ptr [rsi+98h]
0x1801a19dd  mov     [rsp+0A8h+var_78], ecx
0x1801a19e1  cmp     ecx, [r11+rbx*4]
0x1801a19e5  jz      loc_1801A1FE0
0x1801a19eb  mov     r14, [rsi+88h]
0x1801a19f2  lea     ebp, [rcx+1]
0x1801a19f5  mov     r15d, [r14]
0x1801a19f8  shr     r15d, 2
0x1801a19fc  cmp     ebp, r15d
0x1801a19ff  ja      loc_1801A1BB4
0x1801a1a05  xor     edi, edi
0x1801a1a07  mov     rax, [rsi+88h]
0x1801a1a0e  movsxd  r14, ecx
0x1801a1a11  shl     r14, 6
0x1801a1a15  mov     [rax+4], ebp
0x1801a1a18  mov     rax, [rsi+88h]
0x1801a1a1f  mov     rbp, [rax+8]
0x1801a1a23  mov     rax, [rsp+0A8h+arg_10]
0x1801a1a2b  mov     [r14+rbp+8], rax
0x1801a1a30  mov     rax, [rsp+0A8h+arg_18]
0x1801a1a38  mov     [r14+rbp+10h], rax
0x1801a1a3d  mov     rax, [rsp+0A8h+arg_28]
0x1801a1a45  mov     [r14+rbp+18h], rax
0x1801a1a4a  mov     [r14+rbp], r12
0x1801a1a4e  mov     [r14+rbp+20h], r13d
0x1801a1a53  mov     eax, [rsi+80h]
0x1801a1a59  mov     [r14+rbp+24h], eax
0x1801a1a5e  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1801a1a64  cmp     byte ptr [rax+10h], 0
0x1801a1a68  jz      loc_1801A1B76
0x1801a1a6e  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1801a1a74  movups  xmm0, xmmword ptr [rax]
0x1801a1a77  movdqu  xmmword ptr [r14+rbp+28h], xmm0
0x1801a1a7e  movsxd  rax, dword ptr [rsi+98h]
0x1801a1a85  lea     rcx, qword_1813BF5B0
0x1801a1a8c  mov     r15, [rsi+90h]
0x1801a1a93  xor     edx, edx
0x1801a1a95  mov     [rsp+0A8h+var_68], r15
0x1801a1a9a  mov     ecx, [rcx+rax*4]
0x1801a1a9d  mov     rax, r12
0x1801a1aa0  div     rcx
0x1801a1aa3  mov     ebx, edx
0x1801a1aa5  mov     [rsp+0A8h+var_70], rbx
0x1801a1aaa  mov     r12d, [r15+rbx*4]
0x1801a1aae  mov     [r14+rbp+38h], r12d
0x1801a1ab3  mov     ebp, [rsp+0A8h+var_78]
0x1801a1ab7  mov     [r15+rbx*4], ebp
0x1801a1abb  mov     [rsp+0A8h+var_74], r12d
0x1801a1ac0  test    r13b, 2
0x1801a1ac4  jnz     short loc_1801A1AFC
0x1801a1ac6  mov     eax, [rsi+78h]
0x1801a1ac9  and     eax, 0FFFFh
0x1801a1ace  jnz     loc_1801A1B9E
0x1801a1ad4  mov     rcx, [rsi+60h]; hWnd
0x1801a1ad8  xor     r9d, r9d; lParam
0x1801a1adb  xor     r8d, r8d; wParam
0x1801a1ade  mov     edx, 8002h; Msg
0x1801a1ae3  call    cs:__imp_PostMessageW
0x1801a1ae9  test    eax, eax
0x1801a1aeb  jz      loc_1801A1F7E
0x1801a1af1  mov     eax, 1
0x1801a1af6  add     [rsi+78h], ax
0x1801a1afa  jmp     short loc_1801A1B58
0x1801a1afc  lea     r14, [rsi+130h]
0x1801a1b03  xor     r12d, r12d
0x1801a1b06  cmp     [r14+10h], r12b
0x1801a1b0a  jz      loc_1801A2039
0x1801a1b10  mov     eax, [rsi+7Ch]
0x1801a1b13  and     eax, 0FFFFh
0x1801a1b18  jnz     loc_1801A1CB0
0x1801a1b1e  mov     rcx, r14; this
0x1801a1b21  call    ?SetupWatchdogTimer@CGwndPaintRequest@@AEAAJXZ; CGwndPaintRequest::SetupWatchdogTimer(void)
0x1801a1b26  mov     edi, eax
0x1801a1b28  test    eax, eax
0x1801a1b2a  js      loc_1801A203E
0x1801a1b30  cmp     [r14+12h], r12b
0x1801a1b34  jz      loc_1801A1CF9
0x1801a1b3a  mov     rcx, [rsi+60h]; hWnd
0x1801a1b3e  mov     r9d, 2; flags
0x1801a1b44  xor     r8d, r8d; hrgnUpdate
0x1801a1b47  xor     edx, edx; lprcUpdate
0x1801a1b49  call    cs:__imp_RedrawWindow
0x1801a1b4f  mov     eax, 1
0x1801a1b54  add     [rsi+7Ch], ax
0x1801a1b58  mov     rcx, [rsp+0A8h+lpCriticalSection]; lpCriticalSection
0x1801a1b5d  call    cs:__imp_LeaveCriticalSection
0x1801a1b63  mov     eax, edi
0x1801a1b65  add     rsp, 68h
0x1801a1b69  pop     r15
0x1801a1b6b  pop     r14
0x1801a1b6d  pop     r13
0x1801a1b6f  pop     r12
0x1801a1b71  pop     rdi
0x1801a1b72  pop     rsi
0x1801a1b73  pop     rbp
0x1801a1b74  pop     rbx
0x1801a1b75  retn
0x1801a1b76  mov     rcx, [rsi+60h]; hWnd
0x1801a1b7a  xor     edx, edx; lpdwProcessId
0x1801a1b7c  call    cs:__imp_GetWindowThreadProcessId
0x1801a1b82  mov     ebx, eax
0x1801a1b84  call    cs:__imp_GetCurrentThreadId
0x1801a1b8a  cmp     ebx, eax
0x1801a1b8c  jz      loc_1801A1A6E
0x1801a1b92  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1801a1b99  jmp     loc_1801A1A77
0x1801a1b9e  movzx   ecx, word ptr [rsi+7Ah]
0x1801a1ba2  cmp     ecx, [rsi+84h]
0x1801a1ba8  jnb     short loc_1801A1B58
0x1801a1baa  cmp     eax, ecx
0x1801a1bac  jbe     loc_1801A1AD4
0x1801a1bb2  jmp     short loc_1801A1B58
0x1801a1bb4  test    ebp, ebp
0x1801a1bb6  js      loc_1801A1F62
0x1801a1bbc  mov     ebx, 4
0x1801a1bc1  cmp     ebp, ebx
0x1801a1bc3  jb      short loc_1801A1BCD
0x1801a1bc5  ja      loc_1801A1CCC
0x1801a1bcb  mov     ebx, ebp
0x1801a1bcd  mov     ecx, ebx
0x1801a1bcf  mov     r8d, 0FFFFFFFFh
0x1801a1bd5  shl     rcx, 6
0x1801a1bd9  mov     edx, ecx
0x1801a1bdb  cmp     rcx, r8
0x1801a1bde  ja      loc_1801A1CA8
0x1801a1be4  cmp     r8, rcx
0x1801a1be7  mov     edi, 80070216h
0x1801a1bec  sbb     eax, eax
0x1801a1bee  and     edi, eax
0x1801a1bf0  cmp     rcx, r8
0x1801a1bf3  ja      short loc_1801A1C3E
0x1801a1bf5  test    byte ptr [r14], 2
0x1801a1bf9  mov     r13, [r14+8]
0x1801a1bfd  mov     r12d, edx
0x1801a1c00  jnz     loc_1801A1EF1
0x1801a1c06  mov     r8d, r12d
0x1801a1c09  mov     rdx, r13
0x1801a1c0c  call    ??$HeapReAlloc@$00@MemoryProtection@@YAPEAXPEAX0_K@Z; MemoryProtection::HeapReAlloc<1>(void *,void *,unsigned __int64)
0x1801a1c11  test    rax, rax
0x1801a1c14  jz      loc_1801A1CEB
0x1801a1c1a  mov     [r14+8], rax
0x1801a1c1e  xor     edi, edi
0x1801a1c20  and     dword ptr [r14], 1
0x1801a1c24  lea     eax, ds:0[rbx*4]
0x1801a1c2b  or      [r14], eax
0x1801a1c2e  mov     r13d, [rsp+0A8h+arg_20]
0x1801a1c36  mov     r12, [rsp+0A8h+arg_8]
0x1801a1c3e  mov     ecx, [rsp+0A8h+var_78]
0x1801a1c42  test    edi, edi
0x1801a1c44  jz      loc_1801A1A07
0x1801a1c4a  jmp     loc_1801A1B58
0x1801a1c4f  movsxd  rax, dword ptr [rsi+98h]
0x1801a1c56  xor     edx, edx
0x1801a1c58  mov     r9, [rsp+0A8h+arg_18]
0x1801a1c60  mov     r10, [rsp+0A8h+arg_10]
0x1801a1c68  mov     ecx, [r11+rax*4]
0x1801a1c6c  mov     rax, r12
0x1801a1c6f  div     rcx
0x1801a1c72  mov     rax, [rsi+90h]
0x1801a1c79  mov     ecx, edx
0x1801a1c7b  mov     edx, [rax+rcx*4]
0x1801a1c7e  test    edx, edx
0x1801a1c80  js      loc_1801A19D2
0x1801a1c86  mov     rcx, [r8+8]
0x1801a1c8a  movsxd  rax, edx
0x1801a1c8d  shl     rax, 6
0x1801a1c91  cmp     [rax+rcx], r12
0x1801a1c95  jnz     short loc_1801A1CA2
0x1801a1c97  cmp     [rax+rcx+8], r10
0x1801a1c9c  jz      loc_1801A1F6C
0x1801a1ca2  mov     edx, [rax+rcx+38h]
0x1801a1ca6  jmp     short loc_1801A1C7E
0x1801a1ca8  mov     edx, r8d
0x1801a1cab  jmp     loc_1801A1BE4
0x1801a1cb0  movzx   ecx, word ptr [rsi+7Eh]
0x1801a1cb4  cmp     eax, ecx
0x1801a1cb6  ja      short loc_1801A1CC4
0x1801a1cb8  cmp     ecx, [rsi+84h]
0x1801a1cbe  jb      loc_1801A1B1E
0x1801a1cc4  mov     edi, r12d
0x1801a1cc7  jmp     loc_1801A1B58
0x1801a1ccc  mov     ebx, [r14]
0x1801a1ccf  shr     ebx, 3
0x1801a1cd2  add     ebx, r15d
0x1801a1cd5  cmp     ebx, r15d
0x1801a1cd8  jb      loc_1801A1E6D
0x1801a1cde  cmp     ebp, ebx
0x1801a1ce0  jbe     loc_1801A1BCD
0x1801a1ce6  jmp     loc_1801A1BCB
0x1801a1ceb  test    r12, r12
0x1801a1cee  jz      loc_1801A1C1A
0x1801a1cf4  jmp     loc_1801A1F58
0x1801a1cf9  mov     ecx, cs:_tls_index
0x1801a1cff  mov     rax, gs:58h
0x1801a1d08  mov     edx, 10h
0x1801a1d0d  mov     r15, [rax+rcx*8]
0x1801a1d11  mov     r13, [r15+rdx]
0x1801a1d15  test    r13, r13
0x1801a1d18  jz      loc_1801A1F4C
0x1801a1d1e  mov     r13, [r13+0E8h]
0x1801a1d25  cmp     [r13+60h], r12
0x1801a1d29  jz      loc_1801A205E
0x1801a1d2f  call    ?GetGwnd@@YAPEAVGWND@@XZ; GetGwnd(void)
0x1801a1d34  mov     rdi, rax
0x1801a1d37  mov     rcx, [rax+70h]
0x1801a1d3b  mov     edx, [rcx+4]
0x1801a1d3e  mov     rbx, [rcx+8]
0x1801a1d42  mov     eax, 12Ch
0x1801a1d47  test    edx, edx
0x1801a1d49  jle     short loc_1801A1D5C
0x1801a1d4b  cmp     [rbx], r14
0x1801a1d4e  jz      loc_1801A1E77
0x1801a1d54  dec     edx
0x1801a1d56  add     rbx, 38h ; '8'
0x1801a1d5a  jmp     short loc_1801A1D42
0x1801a1d5c  mov     rcx, [r13+70h]; this
0x1801a1d60  mov     edx, 38h ; '8'; unsigned __int64
0x1801a1d65  mov     r8d, [rcx+4]
0x1801a1d69  inc     r8d; int
0x1801a1d6c  call    ?EnsureSize@CImplAry@@IEAAJ_KJ@Z; CImplAry::EnsureSize(unsigned __int64,long)
0x1801a1d71  mov     edi, eax
0x1801a1d73  test    eax, eax
0x1801a1d75  jnz     loc_1801A1E4A
0x1801a1d7b  call    GetUniqueID
0x1801a1d80  mov     ecx, 10h
0x1801a1d85  mov     ebx, eax
0x1801a1d87  mov     rcx, [r15+rcx]
0x1801a1d8b  movzx   r12d, byte ptr [rcx+247h]
0x1801a1d93  test    r12d, r12d
0x1801a1d96  jnz     short loc_1801A1DCA
0x1801a1d98  mov     rax, cs:qword_181591D28
0x1801a1d9f  xor     r9d, r9d; lpTimerFunc
0x1801a1da2  mov     rcx, [r13+60h]; hWnd
0x1801a1da6  mov     edx, ebx; nIDEvent
0x1801a1da8  mov     r8d, 12Ch; uElapse
0x1801a1dae  test    rax, rax
0x1801a1db1  jz      loc_1801A1F98
0x1801a1db7  mov     dword ptr [rsp+0A8h+var_88], r9d
0x1801a1dbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801a1dc1  test    rax, rax
0x1801a1dc4  jz      loc_1801A205E
0x1801a1dca  mov     rcx, [r13+70h]
0x1801a1dce  movsxd  rax, dword ptr [rcx+4]
0x1801a1dd2  mov     rbp, [rcx+8]
0x1801a1dd6  imul    r15, rax, 38h ; '8'
0x1801a1dda  lea     rax, ?OnStarveCheckTimer@CGwndPaintRequest@@QEAAJI@Z; CGwndPaintRequest::OnStarveCheckTimer(uint)
0x1801a1de1  mov     [r15+rbp+20h], r12d
0x1801a1de6  xor     r12d, r12d
0x1801a1de9  mov     [r15+rbp], r14
0x1801a1ded  mov     [r15+rbp+8], rax
0x1801a1df2  mov     [r15+rbp+14h], ebx
0x1801a1df7  mov     dword ptr [r15+rbp+10h], 0CE02h
0x1801a1e00  mov     qword ptr [r15+rbp+18h], 12Ch
0x1801a1e09  mov     dword ptr [r15+rbp+24h], 1
0x1801a1e12  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1801a1e18  cmp     [rax+10h], r12b
0x1801a1e1c  jz      loc_1801A1F24
0x1801a1e22  call    cs:__imp_?GlobalThreadState@@YAPEAUIE_GLOBAL_THREAD_STATE@@XZ; GlobalThreadState(void)
0x1801a1e28  movups  xmm0, xmmword ptr [rax]
0x1801a1e2b  movdqu  xmmword ptr [r15+rbp+28h], xmm0
0x1801a1e32  mov     rax, [r13+70h]
0x1801a1e36  inc     dword ptr [rax+4]
0x1801a1e39  test    byte ptr cs:Microsoft_IEEnableBits+2, 10h
0x1801a1e40  jnz     loc_1801A1FB2
0x1801a1e46  mov     ebp, [rsp+0A8h+var_78]
0x1801a1e4a  test    edi, edi
  ... truncated ...
```
