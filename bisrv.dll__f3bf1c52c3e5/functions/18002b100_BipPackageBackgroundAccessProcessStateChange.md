# BipPackageBackgroundAccessProcessStateChange

- ea: `0x18002b100`
- end: `0x18002b319`
- name: `BipPackageBackgroundAccessProcessStateChange`
- size: `537`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180014208`
- `0x180056ff0`

## callees

- `0x18002b100`
- `0x18006a8d4`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002b1d7`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002b234`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002b1d7`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18002b234`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002b270`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002b291`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002b270`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18002b291`
- `ntdll!TpPostWork` at `0x18002b211`
- `ntdll!TpPostWork` at `0x18002b211`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b1dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b23a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b1dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b23a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002b2de`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002b2fa`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002b2de`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002b2fa`

## pseudocode

```c
void __fastcall BipPackageBackgroundAccessProcessStateChange(__int64 a1)
{
  int *v1; // r14
  int *v2; // rcx
  int *v3; // rbx
  int *v4; // rax
  _QWORD *ThreadLocalStoragePointer; // rax
  unsigned int *v6; // r15
  int *v7; // r12
  unsigned int v8; // edi
  DWORD CurrentThreadId; // eax
  int v10; // eax
  __int64 v11; // rcx
  int v12; // esi
  char v13; // cl
  int v14; // esi
  int v15; // edi
  int v16; // edi
  int *v17; // rcx
  int *v18; // rax

  v1 = (int *)(a1 + 32);
  v2 = *(int **)(a1 + 32);
  if ( v2 != v1 )
  {
    v3 = 0;
    do
    {
      if ( v3 )
      {
        v4 = (int *)*((_QWORD *)v3 + 20);
        if ( v4 == v1 )
          return;
      }
      else
      {
        v4 = v2;
      }
      v3 = v4 - 40;
    }
    while ( *(v4 - 34) < 0 );
    if ( v4 != (int *)160 )
    {
      ThreadLocalStoragePointer = NtCurrentTeb()->ThreadLocalStoragePointer;
      v6 = (unsigned int *)(ThreadLocalStoragePointer[(unsigned int)tls_index] + 4LL);
      v7 = (int *)(ThreadLocalStoragePointer[(unsigned int)tls_index] + 8LL);
      do
      {
        v8 = 1 << v3[16];
        if ( *v6 >= v8 && IsDebuggerPresent() )
          BipSyncDebugPrintLockBug((struct _BI_LOCK *)(v3 + 14));
        RtlAcquireSRWLockExclusive(v3 + 14);
        CurrentThreadId = GetCurrentThreadId();
        *v7 |= v8;
        *v6 |= v8;
        v3[17] = CurrentThreadId;
        v3[126] |= 0x210u;
        v10 = v3[126];
        if ( (v10 & 1) == 0 )
        {
          v11 = *((_QWORD *)v3 + 60);
          v3[126] = v10 | 1;
          TpPostWork(v11);
          v12 = 1 << dword_1800C4608;
          if ( *v6 >= 1 << dword_1800C4608 )
          {
            if ( IsDebuggerPresent() )
              BipSyncDebugPrintLockBug((struct _BI_LOCK *)&qword_1800C4600);
          }
          RtlAcquireSRWLockExclusive(&qword_1800C4600);
          GetCurrentThreadId();
          v13 = dword_1800C4608;
          *v6 |= v12;
          v14 = *v7 | v12;
          ++dword_1800C4650;
          v15 = ~(1 << v13);
          dword_1800C460C = 0;
          *v7 = v15 & v14;
          RtlReleaseSRWLockExclusive(&qword_1800C4600);
          *v6 &= v15;
        }
        v16 = ~(1 << v3[16]);
        v3[17] = 0;
        *v7 &= v16;
        RtlReleaseSRWLockExclusive(v3 + 14);
        v17 = *(int **)v1;
        *v6 &= v16;
        if ( v17 == v1 )
          break;
        do
        {
          if ( v3 )
          {
            v18 = (int *)*((_QWORD *)v3 + 20);
            if ( v18 == v1 )
              return;
          }
          else
          {
            v18 = v17;
          }
          v3 = v18 - 40;
        }
        while ( *(v18 - 34) < 0 );
      }
      while ( v18 != (int *)160 );
    }
  }
}

```

## disassembly

```asm
0x18002b100  push    r14
0x18002b102  sub     rsp, 40h
0x18002b106  lea     r14, [rcx+20h]
0x18002b10a  mov     rcx, [rcx+20h]
0x18002b10e  cmp     rcx, r14
0x18002b111  jz      short loc_18002B150
0x18002b113  mov     [rsp+48h+arg_0], rbx
0x18002b118  mov     [rsp+48h+var_20], r13
0x18002b11d  xor     r13d, r13d
0x18002b120  mov     ebx, r13d
0x18002b123  test    rbx, rbx
0x18002b126  jnz     short loc_18002B157
0x18002b128  mov     rax, rcx
0x18002b12b  jmp     short loc_18002B163
0x18002b12d  mov     rsi, [rsp+48h+arg_10]
0x18002b132  mov     r12, [rsp+48h+var_18]
0x18002b137  mov     rdi, [rsp+48h+var_10]
0x18002b13c  mov     rbp, [rsp+48h+arg_8]
0x18002b141  mov     r15, [rsp+48h+var_28]
0x18002b146  mov     rbx, [rsp+48h+arg_0]
0x18002b14b  mov     r13, [rsp+48h+var_20]
0x18002b150  add     rsp, 40h
0x18002b154  pop     r14
0x18002b156  retn
0x18002b157  mov     rax, [rbx+0A0h]
0x18002b15e  cmp     rax, r14
0x18002b161  jz      short loc_18002B146
0x18002b163  lea     rbx, [rax-0A0h]
0x18002b16a  cmp     [rax-88h], r13d
0x18002b171  jl      short loc_18002B123
0x18002b173  test    rbx, rbx
0x18002b176  jz      short loc_18002B146
0x18002b178  mov     ecx, cs:_tls_index
0x18002b17e  mov     rax, gs:58h
0x18002b187  mov     [rsp+48h+arg_8], rbp
0x18002b18c  mov     [rsp+48h+var_10], rdi
0x18002b191  mov     [rsp+48h+var_18], r12
0x18002b196  mov     [rsp+48h+var_28], r15
0x18002b19b  mov     r15d, 4
0x18002b1a1  add     r15, [rax+rcx*8]
0x18002b1a5  mov     r12d, 8
0x18002b1ab  add     r12, [rax+rcx*8]
0x18002b1af  mov     [rsp+48h+arg_10], rsi
0x18002b1b4  nop     dword ptr [rax+00h]
0x18002b1b8  nop     dword ptr [rax+rax+00000000h]
0x18002b1c0  mov     ecx, [rbx+40h]
0x18002b1c3  mov     edi, 1
0x18002b1c8  shl     edi, cl
0x18002b1ca  cmp     [r15], edi
0x18002b1cd  jnb     loc_18002B2DE
0x18002b1d3  lea     rcx, [rbx+38h]
0x18002b1d7  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002b1dd  call    cs:__imp_GetCurrentThreadId
0x18002b1e3  or      [r12], edi
0x18002b1e7  or      [r15], edi
0x18002b1ea  mov     [rbx+44h], eax
0x18002b1ed  or      dword ptr [rbx+1F8h], 210h
0x18002b1f7  mov     eax, [rbx+1F8h]
0x18002b1fd  test    al, 1
0x18002b1ff  jnz     short loc_18002B279
0x18002b201  mov     rcx, [rbx+1E0h]
0x18002b208  or      eax, 1
0x18002b20b  mov     [rbx+1F8h], eax
0x18002b211  call    cs:__imp_TpPostWork
0x18002b217  mov     ecx, cs:dword_1800C4608
0x18002b21d  mov     esi, 1
0x18002b222  shl     esi, cl
0x18002b224  cmp     [r15], esi
0x18002b227  jnb     loc_18002B2FA
0x18002b22d  lea     rcx, qword_1800C4600
0x18002b234  call    cs:__imp_RtlAcquireSRWLockExclusive
0x18002b23a  call    cs:__imp_GetCurrentThreadId
0x18002b240  mov     ecx, cs:dword_1800C4608
0x18002b246  mov     edi, 1
0x18002b24b  or      [r15], esi
0x18002b24e  or      esi, [r12]
0x18002b252  inc     cs:dword_1800C4650
0x18002b258  shl     edi, cl
0x18002b25a  lea     rcx, qword_1800C4600
0x18002b261  not     edi
0x18002b263  mov     cs:dword_1800C460C, r13d
0x18002b26a  and     esi, edi
0x18002b26c  mov     [r12], esi
0x18002b270  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002b276  and     [r15], edi
0x18002b279  mov     ecx, [rbx+40h]
0x18002b27c  mov     edi, 1
0x18002b281  shl     edi, cl
0x18002b283  lea     rcx, [rbx+38h]
0x18002b287  not     edi
0x18002b289  mov     [rbx+44h], r13d
0x18002b28d  and     [r12], edi
0x18002b291  call    cs:__imp_RtlReleaseSRWLockExclusive
0x18002b297  mov     rcx, [r14]
0x18002b29a  and     [r15], edi
0x18002b29d  cmp     rcx, r14
0x18002b2a0  jz      loc_18002B12D
0x18002b2a6  test    rbx, rbx
0x18002b2a9  jnz     short loc_18002B2B0
0x18002b2ab  mov     rax, rcx
0x18002b2ae  jmp     short loc_18002B2C0
0x18002b2b0  mov     rax, [rbx+0A0h]
0x18002b2b7  cmp     rax, r14
0x18002b2ba  jz      loc_18002B12D
0x18002b2c0  lea     rbx, [rax-0A0h]
0x18002b2c7  cmp     [rax-88h], r13d
0x18002b2ce  jl      short loc_18002B2A6
0x18002b2d0  test    rbx, rbx
0x18002b2d3  jnz     loc_18002B1C0
0x18002b2d9  jmp     loc_18002B12D
0x18002b2de  call    cs:__imp_IsDebuggerPresent
0x18002b2e4  test    eax, eax
0x18002b2e6  jz      loc_18002B1D3
0x18002b2ec  lea     rcx, [rbx+38h]; struct _BI_LOCK *
0x18002b2f0  call    ?BipSyncDebugPrintLockBug@@YAXPEAU_BI_LOCK@@@Z; BipSyncDebugPrintLockBug(_BI_LOCK *)
0x18002b2f5  jmp     loc_18002B1D3
0x18002b2fa  call    cs:__imp_IsDebuggerPresent
0x18002b300  test    eax, eax
0x18002b302  jz      loc_18002B22D
0x18002b308  lea     rcx, qword_1800C4600; struct _BI_LOCK *
0x18002b30f  call    ?BipSyncDebugPrintLockBug@@YAXPEAU_BI_LOCK@@@Z; BipSyncDebugPrintLockBug(_BI_LOCK *)
0x18002b314  jmp     loc_18002B22D
```
