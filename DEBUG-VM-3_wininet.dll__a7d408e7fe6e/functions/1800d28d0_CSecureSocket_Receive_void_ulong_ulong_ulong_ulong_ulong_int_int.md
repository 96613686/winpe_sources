# CSecureSocket::Receive(void * *,ulong *,ulong *,ulong *,ulong,ulong,int,int *)

- ea: `0x1800d28d0`
- end: `0x1800d2dfe`
- name: `?Receive@CSecureSocket@@UEAAKPEAPEAXPEAK11KKHPEAH@Z`
- size: `1326`
- prototype: `unsigned int __fastcall(CSecureSocket *__hidden this, void **, unsigned int *, unsigned int *, unsigned int *, unsigned int, unsigned int, int, int *)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting`

## callees

- `0x18005fa40`
- `0x1800d28d0`
- `0x1800d2e04`
- `0x18014b3b4`
- `0x1801e1790`
- `0x1801e3c24`
- `0x1801e3c78`
- `0x1801e4988`
- `0x1801e7088`
- `0x1801eb11c`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d2a23`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d2a23`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d29ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d29ef`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d2944`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d2944`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800d2bb6`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800d2bb6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d2caa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d2d77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d2caa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d2d77`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800d2a0f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800d2a0f`
- `ntdll!RtlGetLastNtStatus` at `0x1800d2bc7`
- `ntdll!RtlGetLastNtStatus` at `0x1800d2bc7`

## pseudocode

```c
__int64 __fastcall CSecureSocket::Receive(
        CSecureSocket *this,
        void **a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned int *a5,
        unsigned int a6,
        unsigned int a7,
        int a8,
        int *a9)
{
  _QWORD *v13; // rax
  _QWORD *v14; // rdi
  DWORD LastError; // eax
  DWORD v16; // esi
  _QWORD *Value; // rbx
  __int64 v18; // rcx
  unsigned int v19; // eax
  unsigned int v20; // ebx
  __int64 v22; // rbx
  DWORD v23; // eax
  DWORD CurrentThreadId; // eax

  if ( (xmmword_180266B60 & 8) != 0 )
    WPP_SF_qqqdqdqddDql(
      (_DWORD)this,
      99,
      (unsigned int)&WPP_e8a3628f009531a5195349498ae73e2f_Traceguids,
      (_DWORD)a2,
      (__int64)*a2,
      (__int64)a3,
      *a3,
      (__int64)a4,
      *a4,
      (__int64)a5,
      *a5,
      a6,
      a7,
      (__int64)a9,
      *a9);
  if ( (*(unsigned int (__fastcall **)(CSecureSocket *))(*(_QWORD *)this + 152LL))(this)
    || (*(unsigned int (__fastcall **)(CSecureSocket *))(*(_QWORD *)this + 160LL))(this) )
  {
    v13 = HeapAlloc(g_hWxProcessHeap, 0, 0x150u);
    v14 = v13;
    if ( v13 )
    {
      memset_0(v13, 0, 0x150u);
      *v14 = &CFsm::`vftable';
      if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
        WPP_SF_q(1032, 13, &WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids, v14);
      v14[4] = 0;
      *((_DWORD *)v14 + 10) = 12004;
      *((_DWORD *)v14 + 20) = 12004;
      *((_DWORD *)v14 + 21) = -1;
      *((_DWORD *)v14 + 22) = -1;
      *((_DWORD *)v14 + 23) = -1;
      v14[12] = CFsm_SecureReceive::RunSM;
      v14[7] = 0;
      v14[8] = 0;
      v14[9] = 0;
      v14[13] = this;
      *((_DWORD *)v14 + 28) = 0;
      v14[15] = 0;
      *((_DWORD *)v14 + 32) = -1;
      *(_QWORD *)((char *)v14 + 132) = 0;
      *(_QWORD *)((char *)v14 + 140) = 0;
      *(_QWORD *)((char *)v14 + 148) = 0;
      *((_DWORD *)v14 + 42) = 0;
      v14[20] = 0;
      *(_QWORD *)((char *)v14 + 188) = 0;
      LastError = GetLastError();
      v16 = LastError;
      if ( qword_180269EA8
        && LastError
        && LastError != 997
        && LastError != 12150
        && LastError != 12028
        && LastError != 122 )
      {
        v22 = 16LL * (unsigned __int8)(_InterlockedExchangeAdd(&dword_180269EA4, 1u) + 1);
        GetSystemTimeAsFileTime((LPFILETIME)(v22 + qword_180269EA8));
        *(_DWORD *)(v22 + qword_180269EA8 + 8) = v16;
        *(_DWORD *)(v22 + qword_180269EA8 + 12) = RtlGetLastNtStatus();
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
      SetLastError(v16);
      v14[6] = Value;
      if ( Value )
      {
        v14[7] = Value[5];
        v14[8] = Value[6];
        v14[9] = Value[7];
        v14[10] = *((unsigned int *)Value + 19);
        *((_DWORD *)v14 + 22) = 4;
        *((_DWORD *)v14 + 10) = 0;
        if ( (BYTE1(xmmword_180266B60) & 2) != 0 )
          WPP_SF_qss(
            1033,
            17,
            (unsigned int)&WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids,
            (_DWORD)v14,
            (__int64)word_180222338,
            (__int64)word_180222338);
        v18 = v14[6];
        v14[4] = *(_QWORD *)(v18 + 80);
        *(_QWORD *)(v18 + 80) = v14;
        if ( (BYTE1(xmmword_180266B60) & 2) != 0 )
        {
          WPP_SF_q(1033, 18, &WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids, v14[4]);
          if ( (BYTE1(xmmword_180266B60) & 2) != 0 )
          {
            v23 = GetCurrentThreadId();
            WPP_SF_qD(1033, 19, &WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids, v14, v23);
            if ( (BYTE1(xmmword_180266B60) & 2) != 0 )
              WPP_SF_(1033, 20, &WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids);
          }
        }
      }
      else
      {
        *((_DWORD *)v14 + 10) = 12004;
      }
      if ( (BYTE1(xmmword_180266B60) & 1) != 0 )
        WPP_SF_(1032, 14, &WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids);
      *v14 = &CFsm_SecureReceive::`vftable';
      if ( !*((_DWORD *)v14 + 10) )
      {
        *((_DWORD *)v14 + 58) = a6;
        *((_DWORD *)v14 + 59) = a7;
        *((_DWORD *)v14 + 60) = a8;
        v14[25] = a2;
        v14[26] = a3;
        v14[27] = a4;
        v14[28] = a5;
        v14[31] = a9;
        v14[32] = *a2;
        *((_DWORD *)v14 + 66) = *a3;
        *((_DWORD *)v14 + 67) = *a4;
        v14[34] = *a5;
        v14[36] = 0;
        *((_DWORD *)v14 + 74) = 0;
        *((_DWORD *)v14 + 83) = 0;
      }
    }
    else
    {
      v14 = 0;
    }
    v19 = DoFsm((struct CFsm *)v14);
  }
  else
  {
    v19 = (*(__int64 (__fastcall **)(_QWORD, void **, unsigned int *, unsigned int *, unsigned int *, unsigned int, unsigned int, int, int *))(**((_QWORD **)this + 38) + 88LL))(
            *((_QWORD *)this + 38),
            a2,
            a3,
            a4,
            a5,
            a6,
            a7,
            a8,
            a9);
  }
  v20 = v19;
  if ( (xmmword_180266B60 & 8) != 0 )
    WPP_SF_d(1027, 100, &WPP_e8a3628f009531a5195349498ae73e2f_Traceguids, v19);
  return v20;
}

```

## disassembly

```asm
0x1800d28d0  push    rbx
0x1800d28d2  push    rbp
0x1800d28d3  push    rsi
0x1800d28d4  push    rdi
0x1800d28d5  push    r12
0x1800d28d7  push    r13
0x1800d28d9  push    r14
0x1800d28db  push    r15
0x1800d28dd  sub     rsp, 88h
0x1800d28e4  mov     r14, r9
0x1800d28e7  mov     r15, r8
0x1800d28ea  mov     rbp, rdx
0x1800d28ed  mov     rbx, rcx
0x1800d28f0  test    byte ptr cs:xmmword_180266B60, 8
0x1800d28f7  mov     r13, [rsp+0C8h+arg_40]
0x1800d28ff  mov     r12, [rsp+0C8h+arg_20]
0x1800d2907  mov     edi, [rsp+0C8h+arg_30]
0x1800d290e  mov     esi, [rsp+0C8h+arg_28]
0x1800d2915  jnz     loc_1800D2D1B
0x1800d291b  mov     rax, [rbx]
0x1800d291e  mov     rcx, rbx
0x1800d2921  mov     rax, [rax+98h]
0x1800d2928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d292d  test    eax, eax
0x1800d292f  jz      loc_1800D2BDD
0x1800d2935  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x1800d293c  xor     edx, edx; dwFlags
0x1800d293e  mov     r8d, 150h; dwBytes
0x1800d2944  call    cs:__imp_HeapAlloc
0x1800d294a  xor     esi, esi
0x1800d294c  mov     rdi, rax
0x1800d294f  test    rax, rax
0x1800d2952  jz      loc_1800D2C35
0x1800d2958  xor     edx, edx; Val
0x1800d295a  mov     r8d, 150h; Size
0x1800d2960  mov     rcx, rax; void *
0x1800d2963  call    memset_0
0x1800d2968  lea     rax, ??_7CFsm@@6B@; const CFsm::`vftable'
0x1800d296f  mov     [rdi], rax
0x1800d2972  test    byte ptr cs:xmmword_180266B60+1, 1
0x1800d2979  jnz     loc_1800D2DB6
0x1800d297f  mov     eax, 2EE4h
0x1800d2984  mov     [rdi+20h], rsi
0x1800d2988  mov     [rdi+28h], eax
0x1800d298b  mov     [rdi+50h], eax
0x1800d298e  or      eax, 0FFFFFFFFh
0x1800d2991  mov     [rdi+54h], eax
0x1800d2994  mov     [rdi+58h], eax
0x1800d2997  mov     [rdi+5Ch], eax
0x1800d299a  lea     rax, ?RunSM@CFsm_SecureReceive@@SAKPEAVCFsm@@@Z; CFsm_SecureReceive::RunSM(CFsm *)
0x1800d29a1  mov     [rdi+60h], rax
0x1800d29a5  mov     [rdi+38h], rsi
0x1800d29a9  mov     [rdi+40h], rsi
0x1800d29ad  mov     [rdi+48h], rsi
0x1800d29b1  mov     [rdi+68h], rbx
0x1800d29b5  mov     [rdi+70h], esi
0x1800d29b8  mov     [rdi+78h], rsi
0x1800d29bc  mov     dword ptr [rdi+80h], 0FFFFFFFFh
0x1800d29c6  mov     [rdi+84h], rsi
0x1800d29cd  mov     [rdi+8Ch], rsi
0x1800d29d4  mov     [rdi+94h], rsi
0x1800d29db  mov     [rdi+0A8h], esi
0x1800d29e1  mov     [rdi+0A0h], rsi
0x1800d29e8  mov     [rdi+0BCh], rsi
0x1800d29ef  call    cs:__imp_GetLastError
0x1800d29f5  cmp     cs:qword_180269EA8, 0
0x1800d29fd  mov     esi, eax
0x1800d29ff  jz      short loc_1800D2A09
0x1800d2a01  test    eax, eax
0x1800d2a03  jnz     loc_1800D2B69
0x1800d2a09  mov     ecx, cs:?InternetTlsIndex@@3KA; dwTlsIndex
0x1800d2a0f  call    cs:__imp_TlsGetValue
0x1800d2a15  mov     rbx, rax
0x1800d2a18  test    rax, rax
0x1800d2a1b  jz      loc_1800D2C3D
0x1800d2a21  mov     ecx, esi; dwErrCode
0x1800d2a23  call    cs:__imp_SetLastError
0x1800d2a29  xor     esi, esi
0x1800d2a2b  mov     [rdi+30h], rbx
0x1800d2a2f  test    rbx, rbx
0x1800d2a32  jz      loc_1800D2DD4
0x1800d2a38  mov     rax, [rbx+28h]
0x1800d2a3c  mov     [rdi+38h], rax
0x1800d2a40  mov     rax, [rbx+30h]
0x1800d2a44  mov     [rdi+40h], rax
0x1800d2a48  mov     rax, [rbx+38h]
0x1800d2a4c  mov     [rdi+48h], rax
0x1800d2a50  mov     eax, [rbx+4Ch]
0x1800d2a53  mov     [rdi+50h], eax
0x1800d2a56  mov     [rdi+54h], esi
0x1800d2a59  mov     dword ptr [rdi+58h], 4
0x1800d2a60  mov     [rdi+28h], esi
0x1800d2a63  test    byte ptr cs:xmmword_180266B60+1, 2
0x1800d2a6a  mov     ebx, 409h
0x1800d2a6f  jnz     loc_1800D2CEF
0x1800d2a75  mov     rcx, [rdi+30h]
0x1800d2a79  mov     rax, [rcx+50h]
0x1800d2a7d  mov     [rdi+20h], rax
0x1800d2a81  mov     [rcx+50h], rdi
0x1800d2a85  test    byte ptr cs:xmmword_180266B60+1, 2
0x1800d2a8c  jnz     loc_1800D2C86
0x1800d2a92  test    byte ptr cs:xmmword_180266B60+1, 1
0x1800d2a99  jnz     loc_1800D2D9B
0x1800d2a9f  lea     rax, ??_7CFsm_SecureReceive@@6B@; const CFsm_SecureReceive::`vftable'
0x1800d2aa6  mov     [rdi], rax
0x1800d2aa9  cmp     [rdi+28h], esi
0x1800d2aac  jnz     loc_1800D2B3C
0x1800d2ab2  mov     eax, [rsp+0C8h+arg_28]
0x1800d2ab9  mov     [rdi+0E8h], eax
0x1800d2abf  mov     eax, [rsp+0C8h+arg_30]
0x1800d2ac6  mov     [rdi+0ECh], eax
0x1800d2acc  mov     eax, [rsp+0C8h+arg_38]
0x1800d2ad3  mov     [rdi+0F0h], eax
0x1800d2ad9  mov     [rdi+0C8h], rbp
0x1800d2ae0  mov     [rdi+0D0h], r15
0x1800d2ae7  mov     [rdi+0D8h], r14
0x1800d2aee  mov     [rdi+0E0h], r12
0x1800d2af5  mov     [rdi+0F8h], r13
0x1800d2afc  mov     rax, [rbp+0]
0x1800d2b00  mov     [rdi+100h], rax
0x1800d2b07  mov     eax, [r15]
0x1800d2b0a  mov     [rdi+108h], eax
0x1800d2b10  mov     eax, [r14]
0x1800d2b13  mov     [rdi+10Ch], eax
0x1800d2b19  mov     eax, [r12]
0x1800d2b1d  mov     [rdi+110h], eax
0x1800d2b23  mov     [rdi+114h], esi
0x1800d2b29  mov     [rdi+120h], rsi
0x1800d2b30  mov     [rdi+128h], esi
0x1800d2b36  mov     [rdi+14Ch], esi
0x1800d2b3c  mov     rcx, rdi; this
0x1800d2b3f  call    ?DoFsm@@YAKPEAVCFsm@@@Z; DoFsm(CFsm *)
0x1800d2b44  mov     ebx, eax
0x1800d2b46  test    byte ptr cs:xmmword_180266B60, 8
0x1800d2b4d  jnz     loc_1800D2DE0
0x1800d2b53  mov     eax, ebx
0x1800d2b55  add     rsp, 88h
0x1800d2b5c  pop     r15
0x1800d2b5e  pop     r14
0x1800d2b60  pop     r13
0x1800d2b62  pop     r12
0x1800d2b64  pop     rdi
0x1800d2b65  pop     rsi
0x1800d2b66  pop     rbp
0x1800d2b67  pop     rbx
0x1800d2b68  retn
0x1800d2b69  cmp     esi, 3E5h
0x1800d2b6f  jz      loc_1800D2A09
0x1800d2b75  cmp     esi, 2F76h
0x1800d2b7b  jz      loc_1800D2A09
0x1800d2b81  cmp     esi, 2EFCh
0x1800d2b87  jz      loc_1800D2A09
0x1800d2b8d  cmp     esi, 7Ah ; 'z'
0x1800d2b90  jz      loc_1800D2A09
0x1800d2b96  mov     eax, 1
0x1800d2b9b  lock xadd cs:dword_180269EA4, eax
0x1800d2ba3  mov     rcx, cs:qword_180269EA8
0x1800d2baa  inc     eax
0x1800d2bac  movzx   ebx, al
0x1800d2baf  shl     rbx, 4
0x1800d2bb3  add     rcx, rbx; lpSystemTimeAsFileTime
0x1800d2bb6  call    cs:__imp_GetSystemTimeAsFileTime
0x1800d2bbc  mov     rax, cs:qword_180269EA8
0x1800d2bc3  mov     [rbx+rax+8], esi
0x1800d2bc7  call    cs:__imp_RtlGetLastNtStatus
0x1800d2bcd  mov     rcx, cs:qword_180269EA8
0x1800d2bd4  mov     [rbx+rcx+0Ch], eax
0x1800d2bd8  jmp     loc_1800D2A09
0x1800d2bdd  mov     rax, [rbx]
0x1800d2be0  mov     rcx, rbx
0x1800d2be3  mov     rax, [rax+0A0h]
0x1800d2bea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2bef  test    eax, eax
0x1800d2bf1  jnz     loc_1800D2935
0x1800d2bf7  mov     rcx, [rbx+130h]
0x1800d2bfe  mov     r9, r14
0x1800d2c01  mov     edx, [rsp+0C8h+arg_38]
0x1800d2c08  mov     r8, r15
0x1800d2c0b  mov     [rsp+0C8h+var_88], r13
0x1800d2c10  mov     dword ptr [rsp+0C8h+var_90], edx
0x1800d2c14  mov     rdx, rbp
0x1800d2c17  mov     rax, [rcx]
0x1800d2c1a  mov     [rsp+0C8h+var_98], edi
0x1800d2c1e  mov     dword ptr [rsp+0C8h+var_A0], esi
0x1800d2c22  mov     [rsp+0C8h+var_A8], r12
0x1800d2c27  mov     rax, [rax+58h]
0x1800d2c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2c30  jmp     loc_1800D2B44
0x1800d2c35  mov     rdi, rsi
0x1800d2c38  jmp     loc_1800D2B3C
0x1800d2c3d  test    byte ptr cs:xmmword_180266B60+1, 20h
0x1800d2c44  jnz     loc_1800D2D77
0x1800d2c4a  mov     ecx, 1
0x1800d2c4f  call    InternetCreateThreadInfo
0x1800d2c54  mov     rbx, rax
0x1800d2c57  test    rax, rax
0x1800d2c5a  jnz     loc_1800D2A21
0x1800d2c60  test    byte ptr cs:xmmword_180266B60+1, 20h
0x1800d2c67  jz      loc_1800D2A21
0x1800d2c6d  lea     edx, [rax+17h]
0x1800d2c70  mov     ecx, 40Dh
0x1800d2c75  lea     r8, WPP_269ea9d0988239ed4fc21e863914335a_Traceguids
0x1800d2c7c  call    WPP_SF_
0x1800d2c81  jmp     loc_1800D2A21
0x1800d2c86  mov     r9, [rdi+20h]
0x1800d2c8a  lea     r8, WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids
0x1800d2c91  mov     edx, 12h
0x1800d2c96  mov     ecx, ebx
0x1800d2c98  call    WPP_SF_q
0x1800d2c9d  test    byte ptr cs:xmmword_180266B60+1, 2
0x1800d2ca4  jz      loc_1800D2A92
0x1800d2caa  call    cs:__imp_GetCurrentThreadId
0x1800d2cb0  mov     edx, 13h
0x1800d2cb5  lea     r8, WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids
0x1800d2cbc  mov     ecx, ebx
0x1800d2cbe  mov     dword ptr [rsp+0C8h+var_A8], eax
0x1800d2cc2  mov     r9, rdi
0x1800d2cc5  call    WPP_SF_qD
0x1800d2cca  test    byte ptr cs:xmmword_180266B60+1, 2
0x1800d2cd1  jz      loc_1800D2A92
0x1800d2cd7  mov     edx, 14h
0x1800d2cdc  lea     r8, WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids
0x1800d2ce3  mov     ecx, ebx
0x1800d2ce5  call    WPP_SF_
0x1800d2cea  jmp     loc_1800D2A92
0x1800d2cef  lea     rax, word_180222338
0x1800d2cf6  mov     edx, 11h
0x1800d2cfb  mov     [rsp+0C8h+var_A0], rax
0x1800d2d00  lea     r8, WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids
0x1800d2d07  mov     ecx, ebx
0x1800d2d09  mov     [rsp+0C8h+var_A8], rax
0x1800d2d0e  mov     r9, rdi
0x1800d2d11  call    WPP_SF_qss
0x1800d2d16  jmp     loc_1800D2A75
0x1800d2d1b  mov     eax, [r13+0]
0x1800d2d1f  mov     edx, 63h ; 'c'
0x1800d2d24  mov     [rsp+0C8h+var_58], eax
0x1800d2d28  mov     eax, [r12]
0x1800d2d2c  mov     [rsp+0C8h+var_60], r13
0x1800d2d31  mov     [rsp+0C8h+var_68], edi
0x1800d2d35  mov     [rsp+0C8h+var_70], esi
0x1800d2d39  mov     [rsp+0C8h+var_78], eax
0x1800d2d3d  mov     eax, [r9]
0x1800d2d40  mov     r9, rbp
0x1800d2d43  mov     [rsp+0C8h+var_80], r12
0x1800d2d48  mov     dword ptr [rsp+0C8h+var_88], eax
0x1800d2d4c  mov     eax, [r8]
0x1800d2d4f  lea     r8, WPP_e8a3628f009531a5195349498ae73e2f_Traceguids
0x1800d2d56  mov     [rsp+0C8h+var_90], r14
0x1800d2d5b  mov     [rsp+0C8h+var_98], eax
0x1800d2d5f  mov     rax, [rbp+0]
0x1800d2d63  mov     [rsp+0C8h+var_A0], r15
0x1800d2d68  mov     [rsp+0C8h+var_A8], rax
0x1800d2d6d  call    WPP_SF_qqqdqdqddDql
0x1800d2d72  jmp     loc_1800D291B
0x1800d2d77  call    cs:__imp_GetCurrentThreadId
0x1800d2d7d  mov     edx, 16h
0x1800d2d82  lea     r8, WPP_269ea9d0988239ed4fc21e863914335a_Traceguids
0x1800d2d89  mov     r9d, eax
0x1800d2d8c  mov     ecx, 40Dh
0x1800d2d91  call    WPP_SF_d
0x1800d2d96  jmp     loc_1800D2C4A
0x1800d2d9b  mov     edx, 0Eh
0x1800d2da0  lea     r8, WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids
0x1800d2da7  mov     ecx, 408h
0x1800d2dac  call    WPP_SF_
0x1800d2db1  jmp     loc_1800D2A9F
0x1800d2db6  mov     edx, 0Dh
0x1800d2dbb  lea     r8, WPP_20d22b0870563ebb3b8b6e290da95fd0_Traceguids
0x1800d2dc2  mov     ecx, 408h
0x1800d2dc7  mov     r9, rdi
0x1800d2dca  call    WPP_SF_q
0x1800d2dcf  jmp     loc_1800D297F
0x1800d2dd4  mov     dword ptr [rdi+28h], 2EE4h
0x1800d2ddb  jmp     loc_1800D2A92
0x1800d2de0  mov     edx, 64h ; 'd'
0x1800d2de5  lea     r8, WPP_e8a3628f009531a5195349498ae73e2f_Traceguids
0x1800d2dec  mov     ecx, 403h
0x1800d2df1  mov     r9d, ebx
0x1800d2df4  call    WPP_SF_d
0x1800d2df9  jmp     loc_1800D2B53
```
