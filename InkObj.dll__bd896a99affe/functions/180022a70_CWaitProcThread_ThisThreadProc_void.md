# CWaitProcThread::ThisThreadProc(void)

- ea: `0x180022a70`
- end: `0x180022da6`
- name: `?ThisThreadProc@CWaitProcThread@@AEAAKXZ`
- size: `822`
- prototype: `unsigned int __fastcall(CWaitProcThread *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180066010`

## callees

- `0x180002740`
- `0x180022a70`
- `0x18002756c`
- `0x18002e2d8`
- `0x1800662b0`
- `0x18006653c`
- `0x180079728`
- `0x18010c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022ac4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022ac4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180022b84`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180022b7a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180022d8b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180022b7a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180022d8b`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180022ab6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180022ab6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022a91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022a91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180022b62`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180022b62`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180022b70`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180022b70`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180022d81`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180022d81`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180022b3d`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180022b3d`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180022c04`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180022c04`

## pseudocode

```c
__int64 __fastcall CWaitProcThread::ThisThreadProc(CWaitProcThread *this)
{
  CWaitProcThread *v1; // r14
  int v2; // edi
  HANDLE EventW; // rax
  signed int LastError; // eax
  ULONG *v5; // rsi
  DWORD v6; // r13d
  BOOL v7; // eax
  int v8; // ecx
  HANDLE CurrentThread; // rax
  signed int v10; // eax
  bool v11; // sf
  LPHANDLE *v12; // r15
  LPHANDLE *v13; // r12
  _DWORD *v14; // rbx
  ULONG v15; // esi
  HRESULT v16; // edi
  _DWORD *v17; // r8
  _DWORD *v18; // r9
  DWORD v19; // r10d
  unsigned int v20; // edi
  unsigned int v21; // esi
  char *v22; // rbx
  void *v23; // rcx
  ULONG *v25; // [rsp+38h] [rbp-80h]
  LPHANDLE *v27; // [rsp+48h] [rbp-70h]
  LPHANDLE *v28; // [rsp+50h] [rbp-68h]
  _DWORD *v29; // [rsp+58h] [rbp-60h]
  LPHANDLE *v30; // [rsp+60h] [rbp-58h]
  void **v31; // [rsp+70h] [rbp-48h]
  CWaitProcThread *v32; // [rsp+C0h] [rbp+8h] BYREF
  DWORD dwindex; // [rsp+C8h] [rbp+10h] BYREF
  DWORD v34; // [rsp+D0h] [rbp+18h]
  BOOL v35; // [rsp+D8h] [rbp+20h]

  v32 = this;
  v1 = this;
  v2 = 0;
  *((_DWORD *)this + 2) = GetCurrentThreadId();
  v31 = (void **)((char *)v1 + 24);
  if ( !*((_QWORD *)v1 + 3) )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    *((_QWORD *)v1 + 3) = EventW;
    if ( !EventW )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      if ( v2 < 0 )
      {
LABEL_9:
        v5 = (ULONG *)((char *)v1 + 56);
        v25 = (ULONG *)((char *)v1 + 56);
        v6 = *((_DWORD *)v1 + 14);
        v34 = v6;
        v7 = 0;
        if ( v2 >= 0 )
        {
          v2 = CoInitializeEx(0, 0);
          v7 = v2 >= 0;
        }
        v35 = v7;
        v8 = 0;
        if ( v2 != -2147417850 )
          v8 = v2;
        if ( v8 >= 0 )
        {
          CurrentThread = GetCurrentThread();
          SetThreadPriority(CurrentThread, 2);
          if ( SetEvent(*((HANDLE *)v1 + 2)) )
            goto LABEL_19;
          v10 = GetLastError();
          v11 = v10 < 0;
          if ( v10 > 0 )
            v11 = 1;
          if ( !v11 )
            goto LABEL_19;
        }
        goto LABEL_18;
      }
    }
  }
  if ( (unsigned __int8)Vector<void *,BasicAllocator<void *>>::reserve((char *)v1 + 48, 8) )
  {
    Vector<void *,BasicAllocator<void *>>::push_back((char *)v1 + 48, (char *)v1 + 24);
    goto LABEL_9;
  }
  v5 = (ULONG *)((char *)v1 + 56);
  v25 = (ULONG *)((char *)v1 + 56);
  v6 = *((_DWORD *)v1 + 14);
  v34 = v6;
  v35 = 0;
LABEL_18:
  *((_DWORD *)v1 + 8) = 0;
LABEL_19:
  v30 = (LPHANDLE *)((char *)v1 + 48);
  v12 = (LPHANDLE *)((char *)v1 + 48);
  v27 = (LPHANDLE *)((char *)v1 + 48);
  v13 = (LPHANDLE *)((char *)v1 + 48);
  while ( 1 )
  {
    v14 = (_DWORD *)((char *)v1 + 32);
    v29 = (_DWORD *)((char *)v1 + 32);
    if ( !*((_DWORD *)v1 + 8) )
      break;
    v15 = *v5;
    dwindex = 0;
    v13 = v12;
    v28 = v12;
    v16 = CoWaitForMultipleHandles(2u, 0xFFFFFFFF, v15, *v12, &dwindex);
    if ( dwindex )
    {
      if ( v6 <= dwindex && dwindex < v15 )
      {
        v17 = (_DWORD *)*((_QWORD *)v1 + 9);
        v18 = &v17[4 * *((_QWORD *)this + 10)];
        try
        {
          while ( v18 != v17 )
          {
            v19 = v17[2];
            if ( dwindex >= v19 && dwindex < v19 + v17[3] && *(_QWORD *)v17 )
            {
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v17 + 32LL))(*(_QWORD *)v17);
              goto LABEL_58;
            }
            v17 += 4;
          }
        }
        catch ( ... )
        {
          v1 = v32;
          v6 = v34;
          v12 = v27;
          v13 = v28;
          v14 = v29;
          goto LABEL_33;
        }
LABEL_58:
        ;
      }
    }
    else
    {
      *v14 = 0;
    }
LABEL_33:
    if ( v16 == -2147024890 )
    {
      if ( *v14 )
        *v14 = CWaitProcThread::RebuildMasterList(v1);
    }
    v5 = v25;
  }
  v20 = *((_DWORD *)this + 20);
  if ( v20 )
  {
    v21 = 0;
    v22 = (char *)v1 + 72;
    do
    {
      LODWORD(v32) = 0;
      CWaitProcThread::WaitObjWrapper::RemoveFromMasterList(*(_QWORD *)v22 + 16LL * v21++, v13, &v32);
      v13 = v30;
    }
    while ( v21 < v20 );
  }
  else
  {
    v22 = (char *)this + 72;
  }
  if ( *((_QWORD *)v22 + 1) )
    *((_QWORD *)v22 + 1) = 0;
  if ( *(_QWORD *)v22 )
  {
    WinFree(*(void **)v22);
    *(_QWORD *)v22 = 0;
  }
  *((_QWORD *)v22 + 2) = 0;
  if ( *((_QWORD *)v1 + 7) )
    *((_QWORD *)v1 + 7) = 0;
  v23 = (void *)*((_QWORD *)v1 + 6);
  if ( v23 )
  {
    WinFree(v23);
    *((_QWORD *)v1 + 6) = 0;
  }
  *((_QWORD *)v1 + 8) = 0;
  if ( *((_QWORD *)v1 + 3) )
  {
    SafeCloseHandle(v31);
    *((_QWORD *)v1 + 3) = 0;
  }
  if ( v35 )
    CoUninitialize();
  SetEvent(*((HANDLE *)v1 + 5));
  return 0;
}

```

## disassembly

```asm
0x180022a70  mov     [rsp+arg_0], rcx
0x180022a75  push    rbx
0x180022a76  push    rsi
0x180022a77  push    rdi
0x180022a78  push    r12
0x180022a7a  push    r13
0x180022a7c  push    r14
0x180022a7e  push    r15
0x180022a80  sub     rsp, 80h
0x180022a87  mov     r14, rcx
0x180022a8a  mov     [rsp+0B8h+var_78], rcx
0x180022a8f  xor     edi, edi
0x180022a91  call    cs:__imp_GetCurrentThreadId
0x180022a97  mov     [r14+8], eax
0x180022a9b  lea     rbx, [r14+18h]
0x180022a9f  mov     [rsp+0B8h+var_48], rbx
0x180022aa4  cmp     [rbx], rdi
0x180022aa7  jnz     short loc_180022ADD
0x180022aa9  xor     r9d, r9d; lpName
0x180022aac  xor     r8d, r8d; bInitialState
0x180022aaf  mov     edx, 1; bManualReset
0x180022ab4  xor     ecx, ecx; lpEventAttributes
0x180022ab6  call    cs:__imp_CreateEventW
0x180022abc  mov     [rbx], rax
0x180022abf  test    rax, rax
0x180022ac2  jnz     short loc_180022ADD
0x180022ac4  call    cs:__imp_GetLastError
0x180022aca  mov     edi, eax
0x180022acc  test    eax, eax
0x180022ace  jle     short loc_180022AD9
0x180022ad0  movzx   edi, ax
0x180022ad3  or      edi, 80070000h
0x180022ad9  test    edi, edi
0x180022adb  js      short loc_180022B1F
0x180022add  mov     edx, 8
0x180022ae2  lea     rcx, [r14+30h]
0x180022ae6  call    ?reserve@?$Vector@PEAXV?$BasicAllocator@PEAX@@@@QEAA_N_K@Z; Vector<void *,BasicAllocator<void *>>::reserve(unsigned __int64)
0x180022aeb  test    al, al
0x180022aed  jnz     short loc_180022B13
0x180022aef  lea     rsi, [r14+38h]
0x180022af3  mov     [rsp+0B8h+var_80], rsi
0x180022af8  mov     r13d, [rsi]
0x180022afb  mov     [rsp+0B8h+arg_10], r13d
0x180022b03  mov     [rsp+0B8h+arg_18], 0
0x180022b0e  jmp     loc_180022B9A
0x180022b13  mov     rdx, rbx
0x180022b16  lea     rcx, [r14+30h]
0x180022b1a  call    ?push_back@?$Vector@PEAXV?$BasicAllocator@PEAX@@@@QEAA_NAEBQEAX@Z; Vector<void *,BasicAllocator<void *>>::push_back(void * const &)
0x180022b1f  lea     rsi, [r14+38h]
0x180022b23  mov     [rsp+0B8h+var_80], rsi
0x180022b28  mov     r13d, [rsi]
0x180022b2b  mov     [rsp+0B8h+arg_10], r13d
0x180022b33  xor     eax, eax
0x180022b35  test    edi, edi
0x180022b37  js      short loc_180022B4C
0x180022b39  xor     edx, edx; dwCoInit
0x180022b3b  xor     ecx, ecx; pvReserved
0x180022b3d  call    cs:__imp_CoInitializeEx
0x180022b43  mov     edi, eax
0x180022b45  xor     eax, eax
0x180022b47  test    edi, edi
0x180022b49  setns   al
0x180022b4c  mov     [rsp+0B8h+arg_18], eax
0x180022b53  xor     ecx, ecx
0x180022b55  cmp     edi, 80010106h
0x180022b5b  cmovnz  ecx, edi
0x180022b5e  test    ecx, ecx
0x180022b60  js      short loc_180022B9A
0x180022b62  call    cs:__imp_GetCurrentThread
0x180022b68  mov     rcx, rax; hThread
0x180022b6b  mov     edx, 2; nPriority
0x180022b70  call    cs:__imp_SetThreadPriority
0x180022b76  mov     rcx, [r14+10h]; hEvent
0x180022b7a  call    cs:__imp_SetEvent
0x180022b80  test    eax, eax
0x180022b82  jnz     short loc_180022BA2
0x180022b84  call    cs:__imp_GetLastError
0x180022b8a  test    eax, eax
0x180022b8c  jle     short loc_180022B98
0x180022b8e  movzx   eax, ax
0x180022b91  or      eax, 80070000h
0x180022b96  test    eax, eax
0x180022b98  jns     short loc_180022BA2
0x180022b9a  mov     dword ptr [r14+20h], 0
0x180022ba2  lea     rax, [r14+30h]
0x180022ba6  mov     [rsp+0B8h+var_58], rax
0x180022bab  mov     r15, rax
0x180022bae  mov     [rsp+0B8h+var_70], rax
0x180022bb3  mov     r12, rax
0x180022bb6  nop     word ptr [rax+rax+00000000h]
0x180022bc0  lea     rbx, [r14+20h]
0x180022bc4  mov     [rsp+0B8h+var_60], rbx
0x180022bc9  cmp     dword ptr [rbx], 0
0x180022bcc  jz      loc_180022CBC
0x180022bd2  mov     esi, [rsi]
0x180022bd4  mov     [rsp+0B8h+dwindex], 0
0x180022bdf  mov     r12, r15
0x180022be2  mov     [rsp+0B8h+var_68], r15
0x180022be7  lea     rax, [rsp+0B8h+dwindex]
0x180022bef  mov     [rsp+0B8h+lpdwindex], rax; lpdwindex
0x180022bf4  mov     r9, [r15]; pHandles
0x180022bf7  mov     r8d, esi; cHandles
0x180022bfa  mov     edx, 0FFFFFFFFh; dwTimeout
0x180022bff  mov     ecx, 2; dwFlags
0x180022c04  call    cs:__imp_CoWaitForMultipleHandles
0x180022c0a  mov     edi, eax
0x180022c0c  mov     [rsp+0B8h+var_88], eax
0x180022c10  mov     edx, [rsp+0B8h+dwindex]
0x180022c17  test    edx, edx
0x180022c19  jnz     short loc_180022C1F
0x180022c1b  mov     [rbx], edx
0x180022c1d  jmp     short loc_180022C98
0x180022c1f  cmp     r13d, edx
0x180022c22  ja      short loc_180022C98
0x180022c24  cmp     edx, esi
0x180022c26  jnb     short loc_180022C98
0x180022c28  mov     r8, [r14+48h]
0x180022c2c  mov     rax, [rsp+0B8h+var_78]
0x180022c31  mov     r9, [rax+50h]
0x180022c35  shl     r9, 4
0x180022c39  add     r9, r8
0x180022c3c  cmp     r9, r8
0x180022c3f  jz      short loc_180022C6D
0x180022c41  mov     r10d, [r8+8]
0x180022c45  cmp     edx, r10d
0x180022c48  jb      short loc_180022C6F
0x180022c4a  mov     ecx, [r8+0Ch]
0x180022c4e  add     ecx, r10d
0x180022c51  cmp     edx, ecx
0x180022c53  jnb     short loc_180022C6F
0x180022c55  mov     rcx, [r8]
0x180022c58  test    rcx, rcx
0x180022c5b  jz      short loc_180022C6F
0x180022c5d  mov     rax, [rcx]
0x180022c60  sub     edx, r10d
0x180022c63  mov     rax, [rax+20h]
0x180022c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c6c  nop
0x180022c6d  jmp     short loc_180022C98
0x180022c6f  add     r8, 10h
0x180022c73  jmp     short loc_180022C3C
0x180022c75  mov     r14, [rsp+0B8h+arg_0]
0x180022c7d  mov     edi, [rsp+0B8h+var_88]
0x180022c81  mov     r13d, [rsp+0B8h+arg_10]
0x180022c89  mov     r15, [rsp+0B8h+var_70]
0x180022c8e  mov     r12, [rsp+0B8h+var_68]
0x180022c93  mov     rbx, [rsp+0B8h+var_60]
0x180022c98  cmp     edi, 80070006h
0x180022c9e  jnz     short loc_180022CB2
0x180022ca0  cmp     dword ptr [rbx], 0
0x180022ca3  jz      short loc_180022CB2
0x180022ca5  mov     rcx, r14; this
0x180022ca8  call    ?RebuildMasterList@CWaitProcThread@@AEAA_NXZ; CWaitProcThread::RebuildMasterList(void)
0x180022cad  movzx   eax, al
0x180022cb0  mov     [rbx], eax
0x180022cb2  mov     rsi, [rsp+0B8h+var_80]
0x180022cb7  jmp     loc_180022BC0
0x180022cbc  mov     rax, [rsp+0B8h+var_78]
0x180022cc1  mov     edi, [rax+50h]
0x180022cc4  test    edi, edi
0x180022cc6  jz      short loc_180022D02
0x180022cc8  xor     esi, esi
0x180022cca  lea     rbx, [r14+48h]
0x180022cce  mov     r15, [rsp+0B8h+var_58]
0x180022cd3  mov     dword ptr [rsp+0B8h+arg_0], 0
0x180022cde  mov     ecx, esi
0x180022ce0  shl     rcx, 4
0x180022ce4  add     rcx, [rbx]
0x180022ce7  lea     r8, [rsp+0B8h+arg_0]
0x180022cef  mov     rdx, r12
0x180022cf2  call    ?RemoveFromMasterList@WaitObjWrapper@CWaitProcThread@@QEAAJAEAV?$Vector@PEAXV?$BasicAllocator@PEAX@@@@AEAK@Z; CWaitProcThread::WaitObjWrapper::RemoveFromMasterList(Vector<void *,BasicAllocator<void *>> &,ulong &)
0x180022cf7  inc     esi
0x180022cf9  mov     r12, r15
0x180022cfc  cmp     esi, edi
0x180022cfe  jb      short loc_180022CD3
0x180022d00  jmp     short loc_180022D06
0x180022d02  lea     rbx, [rax+48h]
0x180022d06  cmp     qword ptr [rbx+8], 0
0x180022d0b  jbe     short loc_180022D15
0x180022d0d  mov     qword ptr [rbx+8], 0
0x180022d15  mov     rcx, [rbx]; void *
0x180022d18  test    rcx, rcx
0x180022d1b  jz      short loc_180022D29
0x180022d1d  call    ?WinFree@@YAXPEAX@Z; WinFree(void *)
0x180022d22  mov     qword ptr [rbx], 0
0x180022d29  mov     qword ptr [rbx+10h], 0
0x180022d31  cmp     qword ptr [r14+38h], 0
0x180022d36  jbe     short loc_180022D40
0x180022d38  mov     qword ptr [r14+38h], 0
0x180022d40  mov     rcx, [r14+30h]; void *
0x180022d44  test    rcx, rcx
0x180022d47  jz      short loc_180022D56
0x180022d49  call    ?WinFree@@YAXPEAX@Z; WinFree(void *)
0x180022d4e  mov     qword ptr [r14+30h], 0
0x180022d56  mov     qword ptr [r14+40h], 0
0x180022d5e  cmp     qword ptr [r14+18h], 0
0x180022d63  jz      short loc_180022D77
0x180022d65  mov     rcx, [rsp+0B8h+var_48]; void **
0x180022d6a  call    ?SafeCloseHandle@@YAXPEAPEAX@Z; SafeCloseHandle(void * *)
0x180022d6f  mov     qword ptr [r14+18h], 0
0x180022d77  cmp     [rsp+0B8h+arg_18], 0
0x180022d7f  jz      short loc_180022D87
0x180022d81  call    cs:__imp_CoUninitialize
0x180022d87  mov     rcx, [r14+28h]; hEvent
0x180022d8b  call    cs:__imp_SetEvent
0x180022d91  xor     eax, eax
0x180022d93  add     rsp, 80h
0x180022d9a  pop     r15
0x180022d9c  pop     r14
0x180022d9e  pop     r13
0x180022da0  pop     r12
0x180022da2  pop     rdi
0x180022da3  pop     rsi
0x180022da4  pop     rbx
0x180022da5  retn
```
