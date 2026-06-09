# HTTP_REQUEST_HANDLE_OBJECT::ReadDataSocket(void *,ulong,ulong *,ulong)

- ea: `0x18005eee8`
- end: `0x18005f2e4`
- name: `?ReadDataSocket@HTTP_REQUEST_HANDLE_OBJECT@@QEAAKPEAXKPEAKK@Z`
- size: `1020`
- prototype: `unsigned int __fastcall(HTTP_REQUEST_HANDLE_OBJECT *__hidden this, void *, unsigned int, unsigned int *, unsigned int)`
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180031150`
- `0x180181a48`

## callees

- `0x18005eee8`
- `0x18005fa40`
- `0x1800d2e04`
- `0x18014b3b4`
- `0x1801d7098`
- `0x1801e1790`
- `0x1801e3c24`
- `0x1801e3c78`
- `0x1801e4988`
- `0x1801e7088`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f009`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005f009`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005efd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005efd6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005ef2b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18005ef2b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005f12f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005f12f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005f1cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005f23c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005f1cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005f23c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005eff5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18005eff5`
- `ntdll!RtlGetLastNtStatus` at `0x18005f140`
- `ntdll!RtlGetLastNtStatus` at `0x18005f140`

## pseudocode

```c
__int64 __fastcall HTTP_REQUEST_HANDLE_OBJECT::ReadDataSocket(
        HTTP_REQUEST_HANDLE_OBJECT *this,
        void *a2,
        int a3,
        unsigned int *a4,
        unsigned int a5)
{
  _QWORD *v9; // rax
  _QWORD *v10; // rdi
  DWORD LastError; // eax
  DWORD v12; // esi
  _QWORD *Value; // rbx
  __int64 v14; // rcx
  unsigned int v15; // eax
  unsigned int v16; // ebx
  __int64 v18; // rbx
  DWORD v19; // eax
  DWORD CurrentThreadId; // eax

  if ( (xmmword_180266B60 & 2) != 0 )
    WPP_SF_qdqD((_DWORD)this, 53, a3, (_DWORD)a2, a3, (__int64)a4);
  v9 = HeapAlloc(g_hWxProcessHeap, 0, 0xF8u);
  v10 = v9;
  if ( v9 )
  {
    memset_0(v9, 0, 0xF8u);
    *v10 = &CFsm::`vftable';
    if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
      WPP_SF_q(1032, 13, &WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids, v10);
    v10[4] = 0;
    *((_DWORD *)v10 + 10) = 12004;
    *((_DWORD *)v10 + 20) = 12004;
    *((_DWORD *)v10 + 21) = -1;
    *((_DWORD *)v10 + 22) = -1;
    *((_DWORD *)v10 + 23) = -1;
    v10[12] = CFsm_ReadDataSocket::RunSM;
    v10[7] = 0;
    v10[8] = 0;
    v10[9] = 0;
    v10[13] = this;
    *((_DWORD *)v10 + 28) = 0;
    v10[15] = 0;
    *((_DWORD *)v10 + 32) = -1;
    *(_QWORD *)((char *)v10 + 132) = 0;
    *(_QWORD *)((char *)v10 + 140) = 0;
    *(_QWORD *)((char *)v10 + 148) = 0;
    *((_DWORD *)v10 + 42) = 0;
    v10[20] = 0;
    *(_QWORD *)((char *)v10 + 188) = 0;
    LastError = GetLastError();
    v12 = LastError;
    if ( qword_180269EA8
      && LastError
      && LastError != 997
      && LastError != 12150
      && LastError != 12028
      && LastError != 122 )
    {
      v18 = 16LL * (unsigned __int8)(_InterlockedExchangeAdd(&dword_180269EA4, 1u) + 1);
      GetSystemTimeAsFileTime((LPFILETIME)(v18 + qword_180269EA8));
      *(_DWORD *)(v18 + qword_180269EA8 + 8) = v12;
      *(_DWORD *)(v18 + qword_180269EA8 + 12) = RtlGetLastNtStatus();
    }
    Value = TlsGetValue(InternetTlsIndex);
    if ( !Value )
    {
      if ( (BYTE1(xmmword_180266B60) & 0x20) != 0 )
      {
        CurrentThreadId = GetCurrentThreadId();
        WPP_SF_d(1037, 22, &WPP_269ea9d0988239ed4fc21e863914335a_Traceguids, CurrentThreadId);
      }
      Value = (_QWORD *)InternetCreateThreadInfo(1);
      if ( !Value && (BYTE1(xmmword_180266B60) & 0x20) != 0 )
        WPP_SF_(1037, 23, &WPP_269ea9d0988239ed4fc21e863914335a_Traceguids);
    }
    SetLastError(v12);
    v10[6] = Value;
    if ( Value )
    {
      v10[7] = Value[5];
      v10[8] = Value[6];
      v10[9] = Value[7];
      v10[10] = *((unsigned int *)Value + 19);
      *((_DWORD *)v10 + 22) = 4;
      *((_DWORD *)v10 + 10) = 0;
      if ( (BYTE1(xmmword_180266B60) & 2) != 0 )
        WPP_SF_qss(
          1033,
          17,
          (unsigned int)&WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids,
          (_DWORD)v10,
          (__int64)word_180222338,
          (__int64)word_180222338);
      v14 = v10[6];
      v10[4] = *(_QWORD *)(v14 + 80);
      *(_QWORD *)(v14 + 80) = v10;
      if ( (BYTE1(xmmword_180266B60) & 2) != 0 )
      {
        WPP_SF_q(1033, 18, &WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids, v10[4]);
        if ( (BYTE1(xmmword_180266B60) & 2) != 0 )
        {
          v19 = GetCurrentThreadId();
          WPP_SF_qD(1033, 19, &WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids, v10, v19);
          if ( (BYTE1(xmmword_180266B60) & 2) != 0 )
            WPP_SF_(1033, 20, &WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids);
        }
      }
    }
    else
    {
      *((_DWORD *)v10 + 10) = 12004;
    }
    if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
      WPP_SF_(1032, 14, &WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids);
    *v10 = &CFsm_OpenProxyTunnel::`vftable';
    if ( !*((_DWORD *)v10 + 10) )
    {
      v10[25] = a2;
      *((_DWORD *)v10 + 52) = a3;
      v10[27] = a4;
      *((_DWORD *)v10 + 56) = a5;
      *((_DWORD *)v10 + 58) = 0;
    }
  }
  else
  {
    v10 = 0;
  }
  v15 = DoFsm((struct CFsm *)v10);
  v16 = v15;
  if ( (xmmword_180266B60 & 2) != 0 )
    WPP_SF_d(1025, 54, &WPP_537423a7083730e445a863adf3f03e81_Traceguids, v15);
  return v16;
}

```

## disassembly

```asm
0x18005eee8  push    rbx
0x18005eeea  push    rbp
0x18005eeeb  push    rsi
0x18005eeec  push    rdi
0x18005eeed  push    r12
0x18005eeef  push    r13
0x18005eef1  push    r14
0x18005eef3  push    r15
0x18005eef5  sub     rsp, 48h
0x18005eef9  mov     rbp, r9
0x18005eefc  mov     r14d, r8d
0x18005eeff  mov     r15, rdx
0x18005ef02  mov     rbx, rcx
0x18005ef05  test    byte ptr cs:xmmword_180266B60, 2
0x18005ef0c  mov     r12d, [rsp+88h+arg_20]
0x18005ef14  jnz     loc_18005F299
0x18005ef1a  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x18005ef21  mov     esi, 0F8h
0x18005ef26  mov     r8d, esi; dwBytes
0x18005ef29  xor     edx, edx; dwFlags
0x18005ef2b  call    cs:__imp_HeapAlloc
0x18005ef31  xor     r13d, r13d
0x18005ef34  mov     rdi, rax
0x18005ef37  test    rax, rax
0x18005ef3a  jz      loc_18005F156
0x18005ef40  mov     r8d, esi; Size
0x18005ef43  xor     edx, edx; Val
0x18005ef45  mov     rcx, rax; void *
0x18005ef48  call    memset_0
0x18005ef4d  lea     rax, ??_7CFsm@@6B@; const CFsm::`vftable'
0x18005ef54  mov     [rdi], rax
0x18005ef57  test    byte ptr cs:xmmword_180266B60+1, 1
0x18005ef5e  jnz     loc_18005F2BA
0x18005ef64  mov     eax, 2EE4h
0x18005ef69  mov     [rdi+20h], r13
0x18005ef6d  mov     [rdi+28h], eax
0x18005ef70  mov     [rdi+50h], eax
0x18005ef73  or      eax, 0FFFFFFFFh
0x18005ef76  mov     [rdi+54h], eax
0x18005ef79  mov     [rdi+58h], eax
0x18005ef7c  mov     [rdi+5Ch], eax
0x18005ef7f  lea     rax, ?RunSM@CFsm_ReadDataSocket@@SAKPEAVCFsm@@@Z; CFsm_ReadDataSocket::RunSM(CFsm *)
0x18005ef86  mov     [rdi+60h], rax
0x18005ef8a  mov     [rdi+38h], r13
0x18005ef8e  mov     [rdi+40h], r13
0x18005ef92  mov     [rdi+48h], r13
0x18005ef96  mov     [rdi+68h], rbx
0x18005ef9a  mov     [rdi+70h], r13d
0x18005ef9e  mov     [rdi+78h], r13
0x18005efa2  mov     dword ptr [rdi+80h], 0FFFFFFFFh
0x18005efac  mov     [rdi+84h], r13
0x18005efb3  mov     [rdi+8Ch], r13
0x18005efba  mov     [rdi+94h], r13
0x18005efc1  mov     [rdi+0A8h], r13d
0x18005efc8  mov     [rdi+0A0h], r13
0x18005efcf  mov     [rdi+0BCh], r13
0x18005efd6  call    cs:__imp_GetLastError
0x18005efdc  cmp     cs:qword_180269EA8, r13
0x18005efe3  mov     esi, eax
0x18005efe5  jz      short loc_18005EFEF
0x18005efe7  test    eax, eax
0x18005efe9  jnz     loc_18005F0E2
0x18005efef  mov     ecx, cs:?InternetTlsIndex@@3KA; dwTlsIndex
0x18005eff5  call    cs:__imp_TlsGetValue
0x18005effb  mov     rbx, rax
0x18005effe  test    rax, rax
0x18005f001  jz      loc_18005F15E
0x18005f007  mov     ecx, esi; dwErrCode
0x18005f009  call    cs:__imp_SetLastError
0x18005f00f  mov     [rdi+30h], rbx
0x18005f013  test    rbx, rbx
0x18005f016  jz      loc_18005F2D8
0x18005f01c  mov     rax, [rbx+28h]
0x18005f020  mov     [rdi+38h], rax
0x18005f024  mov     rax, [rbx+30h]
0x18005f028  mov     [rdi+40h], rax
0x18005f02c  mov     rax, [rbx+38h]
0x18005f030  mov     [rdi+48h], rax
0x18005f034  mov     eax, [rbx+4Ch]
0x18005f037  mov     [rdi+50h], eax
0x18005f03a  mov     [rdi+54h], r13d
0x18005f03e  mov     dword ptr [rdi+58h], 4
0x18005f045  mov     [rdi+28h], r13d
0x18005f049  test    byte ptr cs:xmmword_180266B60+1, 2
0x18005f050  mov     ebx, 409h
0x18005f055  jnz     loc_18005F210
0x18005f05b  mov     rcx, [rdi+30h]
0x18005f05f  mov     rax, [rcx+50h]
0x18005f063  mov     [rdi+20h], rax
0x18005f067  mov     [rcx+50h], rdi
0x18005f06b  test    byte ptr cs:xmmword_180266B60+1, 2
0x18005f072  jnz     loc_18005F1A7
0x18005f078  test    byte ptr cs:xmmword_180266B60+1, 1
0x18005f07f  jnz     loc_18005F260
0x18005f085  lea     rax, ??_7CFsm_OpenProxyTunnel@@6B@; const CFsm_OpenProxyTunnel::`vftable'
0x18005f08c  mov     [rdi], rax
0x18005f08f  cmp     [rdi+28h], r13d
0x18005f093  jnz     short loc_18005F0B8
0x18005f095  mov     [rdi+0C8h], r15
0x18005f09c  mov     [rdi+0D0h], r14d
0x18005f0a3  mov     [rdi+0D8h], rbp
0x18005f0aa  mov     [rdi+0E0h], r12d
0x18005f0b1  mov     [rdi+0E8h], r13d
0x18005f0b8  mov     rcx, rdi; this
0x18005f0bb  call    ?DoFsm@@YAKPEAVCFsm@@@Z; DoFsm(CFsm *)
0x18005f0c0  mov     ebx, eax
0x18005f0c2  test    byte ptr cs:xmmword_180266B60, 2
0x18005f0c9  jnz     loc_18005F27B
0x18005f0cf  mov     eax, ebx
0x18005f0d1  add     rsp, 48h
0x18005f0d5  pop     r15
0x18005f0d7  pop     r14
0x18005f0d9  pop     r13
0x18005f0db  pop     r12
0x18005f0dd  pop     rdi
0x18005f0de  pop     rsi
0x18005f0df  pop     rbp
0x18005f0e0  pop     rbx
0x18005f0e1  retn
0x18005f0e2  cmp     esi, 3E5h
0x18005f0e8  jz      loc_18005EFEF
0x18005f0ee  cmp     esi, 2F76h
0x18005f0f4  jz      loc_18005EFEF
0x18005f0fa  cmp     esi, 2EFCh
0x18005f100  jz      loc_18005EFEF
0x18005f106  cmp     esi, 7Ah ; 'z'
0x18005f109  jz      loc_18005EFEF
0x18005f10f  mov     eax, 1
0x18005f114  lock xadd cs:dword_180269EA4, eax
0x18005f11c  mov     rcx, cs:qword_180269EA8
0x18005f123  inc     eax
0x18005f125  movzx   ebx, al
0x18005f128  shl     rbx, 4
0x18005f12c  add     rcx, rbx; lpSystemTimeAsFileTime
0x18005f12f  call    cs:__imp_GetSystemTimeAsFileTime
0x18005f135  mov     rax, cs:qword_180269EA8
0x18005f13c  mov     [rbx+rax+8], esi
0x18005f140  call    cs:__imp_RtlGetLastNtStatus
0x18005f146  mov     rcx, cs:qword_180269EA8
0x18005f14d  mov     [rbx+rcx+0Ch], eax
0x18005f151  jmp     loc_18005EFEF
0x18005f156  mov     rdi, r13
0x18005f159  jmp     loc_18005F0B8
0x18005f15e  test    byte ptr cs:xmmword_180266B60+1, 20h
0x18005f165  jnz     loc_18005F23C
0x18005f16b  mov     ecx, 1
0x18005f170  call    InternetCreateThreadInfo
0x18005f175  mov     rbx, rax
0x18005f178  test    rax, rax
0x18005f17b  jnz     loc_18005F007
0x18005f181  test    byte ptr cs:xmmword_180266B60+1, 20h
0x18005f188  jz      loc_18005F007
0x18005f18e  lea     edx, [rax+17h]
0x18005f191  mov     ecx, 40Dh
0x18005f196  lea     r8, WPP_269ea9d0988239ed4fc21e863914335a_Traceguids
0x18005f19d  call    WPP_SF_
0x18005f1a2  jmp     loc_18005F007
0x18005f1a7  mov     r9, [rdi+20h]
0x18005f1ab  lea     r8, WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids
0x18005f1b2  mov     edx, 12h
0x18005f1b7  mov     ecx, ebx
0x18005f1b9  call    WPP_SF_q
0x18005f1be  test    byte ptr cs:xmmword_180266B60+1, 2
0x18005f1c5  jz      loc_18005F078
0x18005f1cb  call    cs:__imp_GetCurrentThreadId
0x18005f1d1  mov     edx, 13h
0x18005f1d6  lea     r8, WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids
0x18005f1dd  mov     ecx, ebx
0x18005f1df  mov     dword ptr [rsp+88h+var_68], eax
0x18005f1e3  mov     r9, rdi
0x18005f1e6  call    WPP_SF_qD
0x18005f1eb  test    byte ptr cs:xmmword_180266B60+1, 2
0x18005f1f2  jz      loc_18005F078
0x18005f1f8  mov     edx, 14h
0x18005f1fd  lea     r8, WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids
0x18005f204  mov     ecx, ebx
0x18005f206  call    WPP_SF_
0x18005f20b  jmp     loc_18005F078
0x18005f210  lea     rax, word_180222338
0x18005f217  mov     edx, 11h
0x18005f21c  mov     [rsp+88h+var_60], rax
0x18005f221  lea     r8, WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids
0x18005f228  mov     ecx, ebx
0x18005f22a  mov     [rsp+88h+var_68], rax
0x18005f22f  mov     r9, rdi
0x18005f232  call    WPP_SF_qss
0x18005f237  jmp     loc_18005F05B
0x18005f23c  call    cs:__imp_GetCurrentThreadId
0x18005f242  mov     edx, 16h
0x18005f247  lea     r8, WPP_269ea9d0988239ed4fc21e863914335a_Traceguids
0x18005f24e  mov     r9d, eax
0x18005f251  mov     ecx, 40Dh
0x18005f256  call    WPP_SF_d
0x18005f25b  jmp     loc_18005F16B
0x18005f260  mov     edx, 0Eh
0x18005f265  lea     r8, WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids
0x18005f26c  mov     ecx, 408h
0x18005f271  call    WPP_SF_
0x18005f276  jmp     loc_18005F085
0x18005f27b  mov     edx, 36h ; '6'
0x18005f280  lea     r8, WPP_537423a7083730e445a863adf3f03e81_Traceguids
0x18005f287  mov     ecx, 401h
0x18005f28c  mov     r9d, ebx
0x18005f28f  call    WPP_SF_d
0x18005f294  jmp     loc_18005F0CF
0x18005f299  mov     [rsp+88h+var_58], r12d
0x18005f29e  mov     edx, 35h ; '5'
0x18005f2a3  mov     [rsp+88h+var_60], rbp
0x18005f2a8  mov     r9, r15
0x18005f2ab  mov     dword ptr [rsp+88h+var_68], r14d
0x18005f2b0  call    WPP_SF_qdqD
0x18005f2b5  jmp     loc_18005EF1A
0x18005f2ba  mov     edx, 0Dh
0x18005f2bf  lea     r8, WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids
0x18005f2c6  mov     ecx, 408h
0x18005f2cb  mov     r9, rdi
0x18005f2ce  call    WPP_SF_q
0x18005f2d3  jmp     loc_18005EF64
0x18005f2d8  mov     dword ptr [rdi+28h], 2EE4h
0x18005f2df  jmp     loc_18005F078
```
