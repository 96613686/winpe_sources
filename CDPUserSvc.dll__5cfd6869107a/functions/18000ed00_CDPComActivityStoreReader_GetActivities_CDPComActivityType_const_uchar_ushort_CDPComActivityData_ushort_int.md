# CDPComActivityStoreReader::GetActivities(CDPComActivityType const *,uchar,ushort,CDPComActivityData * *,ushort *,int *)

- ea: `0x18000ed00`
- end: `0x18000efa8`
- name: `?GetActivities@CDPComActivityStoreReader@@UEAAJPEBW4CDPComActivityType@@EGPEAPEAUCDPComActivityData@@PEAGPEAH@Z`
- size: `680`
- prototype: `__int64 __fastcall(CDPComActivityStoreReader *__hidden this, const enum CDPComActivityType *, unsigned __int8, unsigned __int16, struct CDPComActivityData **, unsigned __int16 *, int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x18000ed00`
- `0x18000efb0`
- `0x1800250a4`
- `0x18002c570`
- `0x18002ca90`
- `0x18002cacc`
- `0x18002d1b0`
- `0x18002d1c8`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000ed8c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000ef61`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000ed8c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000ef61`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000eeae`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000eeae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ede1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ede1`

## pseudocode

```c
__int64 __fastcall CDPComActivityStoreReader::GetActivities(
        CDPComActivityStoreReader *this,
        const enum CDPComActivityType *a2,
        unsigned __int8 a3,
        __int64 a4,
        struct CDPComActivityData **a5,
        unsigned __int16 *a6,
        int *a7)
{
  unsigned __int64 v7; // r15
  char v10; // cl
  struct CDPComActivityData *v11; // rbx
  int v12; // edi
  int v13; // ebx
  __int64 v14; // rcx
  unsigned __int64 v15; // rbx
  void *v16; // r12
  RTL_SRWLOCK *v17; // rbx
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r9
  unsigned __int16 i; // r14
  unsigned int v23; // [rsp+40h] [rbp-71h] BYREF
  _BYTE v24[4]; // [rsp+44h] [rbp-6Dh] BYREF
  int *v25; // [rsp+48h] [rbp-69h] BYREF
  _QWORD v26[2]; // [rsp+50h] [rbp-61h] BYREF
  _OWORD v27[4]; // [rsp+60h] [rbp-51h] BYREF
  int v28; // [rsp+A0h] [rbp-11h]

  v7 = (unsigned __int16)a4;
  v26[0] = this;
  v25 = a7;
  if ( !a2 )
  {
    LODWORD(v25) = 55;
LABEL_31:
    v23 = -2147467261;
    Log<long &,char const (&)[33],int>((__int64)this, (__int64)a2, &v23, a4, &v25);
    return v23;
  }
  if ( !a5 )
  {
    LODWORD(v25) = 56;
    goto LABEL_31;
  }
  if ( (unsigned __int8)(a3 - 1) > 0x10u || !a6 )
  {
    LODWORD(v25) = -2147024809;
    LODWORD(v26[0]) = 57;
    Log<long &,char const (&)[33],int>((__int64)this, (__int64)a2, &v25, a4, v26);
    return (unsigned int)v25;
  }
  *a6 = 0;
  *a5 = 0;
  v12 = 0;
  if ( !(_WORD)a4 )
    return (unsigned int)v12;
  memset(v27, 0, sizeof(v27));
  v28 = 0;
  memcpy_0(v27, a2, 4LL * a3);
  v15 = saturated_mul(v7, 8u);
  v16 = operator new[](v15);
  memset_0(v16, 0, v15);
  v24[0] = 0;
  LOWORD(v23) = 0;
  v17 = (RTL_SRWLOCK *)(v26[0] + 72LL);
  AcquireSRWLockShared((PSRWLOCK)(v26[0] + 72LL));
  v18 = (*(__int64 (__fastcall **)(_QWORD, _OWORD *, _QWORD, void *, _WORD, unsigned int *, _BYTE *))(**(_QWORD **)(v26[0] + 56LL) + 24LL))(
          *(_QWORD *)(v26[0] + 56LL),
          v27,
          a3,
          v16,
          v7,
          &v23,
          v24);
  if ( v18 >= 0 )
  {
    if ( v17 )
      ReleaseSRWLockShared(v17);
    v10 = v24[0];
    *v25 = v24[0];
    if ( !v10 && (_WORD)v23 )
    {
      v11 = (struct CDPComActivityData *)CoTaskMemAlloc(232LL * (unsigned __int16)v23);
      if ( v11 )
      {
        for ( i = 0; i < (unsigned __int16)v23; ++i )
        {
          v12 = CDPActivityToComActivityData_0(*((__int64 **)v16 + i), (__int64)v11 + 232 * i);
          if ( v12 < 0 )
            break;
        }
        *a5 = v11;
        *a6 = i;
      }
      else
      {
        v12 = -2147024882;
      }
      v13 = 0;
      if ( (_WORD)v23 )
      {
        do
        {
          v14 = *((_QWORD *)v16 + v13);
          if ( v14 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
          ++v13;
        }
        while ( v13 < (unsigned __int16)v23 );
      }
    }
    operator delete(v16);
    return (unsigned int)v12;
  }
  LODWORD(v25) = v18;
  LODWORD(v26[0]) = 78;
  Log<long &,char const (&)[33],int>(v20, v19, &v25, v21, v26);
  if ( v17 )
    ReleaseSRWLockShared(v17);
  operator delete(v16);
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x18000ed00  mov     [rsp-8+arg_8], rbx
0x18000ed05  push    rbp
0x18000ed06  push    rsi
0x18000ed07  push    rdi
0x18000ed08  push    r12
0x18000ed0a  push    r13
0x18000ed0c  push    r14
0x18000ed0e  push    r15
0x18000ed10  lea     rbp, [rsp-0Fh]
0x18000ed15  sub     rsp, 0C0h
0x18000ed1c  mov     rax, cs:__security_cookie
0x18000ed23  xor     rax, rsp
0x18000ed26  mov     [rbp+3Fh+var_40], rax
0x18000ed2a  movzx   r15d, r9w
0x18000ed2e  movzx   r14d, r8b
0x18000ed32  mov     [rbp+3Fh+var_A0], rcx
0x18000ed36  mov     rsi, [rbp+3Fh+arg_20]
0x18000ed3a  mov     r13, [rbp+3Fh+arg_28]
0x18000ed3e  mov     rax, [rbp+3Fh+arg_30]
0x18000ed42  mov     [rbp+3Fh+var_A8], rax
0x18000ed46  test    rdx, rdx
0x18000ed49  jz      loc_18000EF77
0x18000ed4f  test    rsi, rsi
0x18000ed52  jz      loc_18000EF80
0x18000ed58  lea     eax, [r14-1]
0x18000ed5c  cmp     al, 10h
0x18000ed5e  jbe     loc_18000EE26
0x18000ed64  mov     dword ptr [rbp+3Fh+var_A8], 80070057h
0x18000ed6b  mov     dword ptr [rbp+3Fh+var_A0], 39h ; '9'
0x18000ed72  lea     rax, [rbp+3Fh+var_A0]
0x18000ed76  mov     [rsp+0F0h+var_D0], rax
0x18000ed7b  lea     r8, [rbp+3Fh+var_A8]
0x18000ed7f  call    ??$Log@AEAJAEAY0CB@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CB@$$CBD$$QEAH@Z; Log<long &,char const (&)[33],int>(CDPLogLevel,char const *,long &,char const (&)[33],int &&)
0x18000ed84  mov     eax, dword ptr [rbp+3Fh+var_A8]
0x18000ed87  jmp     short loc_18000EDB3
0x18000ed89  mov     rcx, rbx; SRWLock
0x18000ed8c  call    cs:__imp_ReleaseSRWLockShared
0x18000ed92  movzx   ecx, [rbp+3Fh+var_AC]
0x18000ed96  mov     rdx, [rbp+3Fh+var_A8]
0x18000ed9a  mov     [rdx], ecx
0x18000ed9c  test    cl, cl
0x18000ed9e  jnz     short loc_18000EDA9
0x18000eda0  movzx   eax, word ptr [rbp+3Fh+var_B0]
0x18000eda4  test    ax, ax
0x18000eda7  jnz     short loc_18000EDDA
0x18000eda9  mov     rcx, r12; Block
0x18000edac  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000edb1  mov     eax, edi
0x18000edb3  mov     rcx, [rbp+3Fh+var_40]
0x18000edb7  xor     rcx, rsp; StackCookie
0x18000edba  call    __security_check_cookie
0x18000edbf  mov     rbx, [rsp+0F0h+arg_8]
0x18000edc7  add     rsp, 0C0h
0x18000edce  pop     r15
0x18000edd0  pop     r14
0x18000edd2  pop     r13
0x18000edd4  pop     r12
0x18000edd6  pop     rdi
0x18000edd7  pop     rsi
0x18000edd8  pop     rbp
0x18000edd9  retn
0x18000edda  imul    rcx, rax, 0E8h; cb
0x18000ede1  call    cs:__imp_CoTaskMemAlloc
0x18000ede7  mov     rbx, rax
0x18000edea  test    rax, rax
0x18000eded  jnz     loc_18000EEFD
0x18000edf3  mov     edi, 8007000Eh
0x18000edf8  xor     ebx, ebx
0x18000edfa  xor     eax, eax
0x18000edfc  cmp     ax, word ptr [rbp+3Fh+var_B0]
0x18000ee00  jnb     short loc_18000EDA9
0x18000ee02  movsxd  rax, ebx
0x18000ee05  mov     rcx, [r12+rax*8]
0x18000ee09  test    rcx, rcx
0x18000ee0c  jz      short loc_18000EE1A
0x18000ee0e  mov     rax, [rcx]
0x18000ee11  mov     rax, [rax+10h]
0x18000ee15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee1a  inc     ebx
0x18000ee1c  movzx   eax, word ptr [rbp+3Fh+var_B0]
0x18000ee20  cmp     ebx, eax
0x18000ee22  jl      short loc_18000EE02
0x18000ee24  jmp     short loc_18000EDA9
0x18000ee26  test    r13, r13
0x18000ee29  jz      loc_18000ED64
0x18000ee2f  xor     eax, eax
0x18000ee31  mov     [r13+0], ax
0x18000ee36  mov     [rsi], rax
0x18000ee39  xor     edi, edi
0x18000ee3b  test    r15w, r15w
0x18000ee3f  jz      loc_18000EDB1
0x18000ee45  xorps   xmm0, xmm0
0x18000ee48  movups  [rbp+3Fh+var_90], xmm0
0x18000ee4c  movups  [rbp+3Fh+var_80], xmm0
0x18000ee50  movups  [rbp+3Fh+var_70], xmm0
0x18000ee54  movups  [rbp+3Fh+var_60], xmm0
0x18000ee58  mov     [rbp+3Fh+var_50], eax
0x18000ee5b  mov     r8, r14
0x18000ee5e  shl     r8, 2; Size
0x18000ee62  lea     rcx, [rbp+3Fh+var_90]; void *
0x18000ee66  call    memcpy_0
0x18000ee6b  mov     eax, 8
0x18000ee70  mul     r15
0x18000ee73  mov     rbx, rax
0x18000ee76  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000ee7d  cmovb   rbx, rax
0x18000ee81  mov     rcx, rbx; unsigned __int64
0x18000ee84  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000ee89  mov     r12, rax
0x18000ee8c  mov     r8, rbx; Size
0x18000ee8f  xor     edx, edx; Val
0x18000ee91  mov     rcx, rax; void *
0x18000ee94  call    memset_0
0x18000ee99  mov     [rbp+3Fh+var_AC], dil
0x18000ee9d  xor     eax, eax
0x18000ee9f  mov     word ptr [rbp+3Fh+var_B0], ax
0x18000eea3  mov     rbx, [rbp+3Fh+var_A0]
0x18000eea7  add     rbx, 48h ; 'H'
0x18000eeab  mov     rcx, rbx; SRWLock
0x18000eeae  call    cs:__imp_AcquireSRWLockShared
0x18000eeb4  mov     rax, [rbp+3Fh+var_A0]
0x18000eeb8  mov     rcx, [rax+38h]
0x18000eebc  mov     rax, [rcx]
0x18000eebf  lea     rdx, [rbp+3Fh+var_AC]
0x18000eec3  mov     [rsp+0F0h+var_C0], rdx
0x18000eec8  lea     rdx, [rbp+3Fh+var_B0]
0x18000eecc  mov     [rsp+0F0h+var_C8], rdx
0x18000eed1  mov     word ptr [rsp+0F0h+var_D0], r15w
0x18000eed7  mov     r9, r12
0x18000eeda  movzx   r8d, r14b
0x18000eede  lea     rdx, [rbp+3Fh+var_90]
0x18000eee2  mov     rax, [rax+18h]
0x18000eee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eeeb  test    eax, eax
0x18000eeed  js      short loc_18000EF3D
0x18000eeef  test    rbx, rbx
0x18000eef2  jnz     loc_18000ED89
0x18000eef8  jmp     loc_18000ED92
0x18000eefd  xor     r14d, r14d
0x18000ef00  xor     eax, eax
0x18000ef02  cmp     ax, word ptr [rbp+3Fh+var_B0]
0x18000ef06  jnb     short loc_18000EF30
0x18000ef08  movzx   ecx, r14w
0x18000ef0c  imul    rdx, rcx, 0E8h
0x18000ef13  add     rdx, rbx
0x18000ef16  mov     rcx, [r12+rcx*8]
0x18000ef1a  call    CDPActivityToComActivityData_0
0x18000ef1f  mov     edi, eax
0x18000ef21  test    eax, eax
0x18000ef23  js      short loc_18000EF30
0x18000ef25  inc     r14w
0x18000ef29  cmp     r14w, word ptr [rbp+3Fh+var_B0]
0x18000ef2e  jb      short loc_18000EF08
0x18000ef30  mov     [rsi], rbx
0x18000ef33  mov     [r13+0], r14w
0x18000ef38  jmp     loc_18000EDF8
0x18000ef3d  mov     dword ptr [rbp+3Fh+var_A8], eax
0x18000ef40  mov     dword ptr [rbp+3Fh+var_A0], 4Eh ; 'N'
0x18000ef47  lea     rax, [rbp+3Fh+var_A0]
0x18000ef4b  mov     [rsp+0F0h+var_D0], rax
0x18000ef50  lea     r8, [rbp+3Fh+var_A8]
0x18000ef54  call    ??$Log@AEAJAEAY0CB@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CB@$$CBD$$QEAH@Z; Log<long &,char const (&)[33],int>(CDPLogLevel,char const *,long &,char const (&)[33],int &&)
0x18000ef59  test    rbx, rbx
0x18000ef5c  jz      short loc_18000EF67
0x18000ef5e  mov     rcx, rbx; SRWLock
0x18000ef61  call    cs:__imp_ReleaseSRWLockShared
0x18000ef67  mov     rcx, r12; Block
0x18000ef6a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000ef6f  mov     eax, dword ptr [rbp+3Fh+var_A8]
0x18000ef72  jmp     loc_18000EDB3
0x18000ef77  mov     dword ptr [rbp+3Fh+var_A8], 37h ; '7'
0x18000ef7e  jmp     short loc_18000EF87
0x18000ef80  mov     dword ptr [rbp+3Fh+var_A8], 38h ; '8'
0x18000ef87  mov     [rbp+3Fh+var_B0], 80004003h
0x18000ef8e  lea     rax, [rbp+3Fh+var_A8]
0x18000ef92  mov     [rsp+0F0h+var_D0], rax
0x18000ef97  lea     r8, [rbp+3Fh+var_B0]
0x18000ef9b  call    ??$Log@AEAJAEAY0CB@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0CB@$$CBD$$QEAH@Z; Log<long &,char const (&)[33],int>(CDPLogLevel,char const *,long &,char const (&)[33],int &&)
0x18000efa0  mov     eax, [rbp+3Fh+var_B0]
0x18000efa3  jmp     loc_18000EDB3
```
