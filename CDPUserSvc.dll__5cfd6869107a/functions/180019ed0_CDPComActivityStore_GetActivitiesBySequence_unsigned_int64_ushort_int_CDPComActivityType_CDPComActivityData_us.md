# CDPComActivityStore::GetActivitiesBySequence(unsigned __int64,ushort,int,CDPComActivityType,CDPComActivityData * *,ushort *,unsigned __int64 *)

- ea: `0x180019ed0`
- end: `0x18001a0dd`
- name: `?GetActivitiesBySequence@CDPComActivityStore@@UEAAJ_KGHW4CDPComActivityType@@PEAPEAUCDPComActivityData@@PEAGPEA_K@Z`
- size: `525`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x1800069c0`
- `0x180019ed0`
- `0x180023b70`
- `0x18002ca90`
- `0x18002cacc`
- `0x18002d1c8`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001a0bd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001a0bd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180019f59`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180019f59`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a09c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a09c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a00a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001a00a`

## pseudocode

```c
__int64 __fastcall CDPComActivityStore::GetActivitiesBySequence(
        __int64 a1,
        __int64 a2,
        unsigned __int16 a3,
        __int64 a4,
        unsigned int a5,
        _QWORD *a6,
        unsigned __int16 *a7,
        __int64 *a8)
{
  unsigned __int64 v8; // rbx
  __int64 v9; // rdi
  _QWORD *v10; // r15
  unsigned __int16 *v12; // r14
  RTL_SRWLOCK *v13; // r12
  int v14; // esi
  unsigned __int64 v15; // rbx
  void *v16; // r13
  __int64 v17; // r8
  LPVOID v18; // rbx
  unsigned __int16 v19; // di
  int v20; // edi
  __int64 v21; // rcx
  unsigned int v22; // [rsp+50h] [rbp-20h] BYREF
  int v23; // [rsp+58h] [rbp-18h] BYREF
  __int64 v24; // [rsp+60h] [rbp-10h] BYREF
  int v27; // [rsp+C8h] [rbp+58h]

  v27 = a4;
  v8 = a3;
  v9 = a2;
  v10 = a6;
  if ( !a6 )
  {
    v23 = 601;
LABEL_3:
    v22 = -2147467261;
    Log<long &,char const (&)[27],int>(a1, a2, &v22, a4, &v23);
    return v22;
  }
  v12 = a7;
  if ( !a7 )
  {
    v23 = 602;
    goto LABEL_3;
  }
  if ( !a8 )
  {
    v23 = 603;
    goto LABEL_3;
  }
  v13 = (RTL_SRWLOCK *)(a1 + 32);
  AcquireSRWLockShared((PSRWLOCK)(a1 + 32));
  *v12 = 0;
  *v10 = 0;
  v14 = 0;
  LOWORD(a6) = 0;
  v24 = v9;
  if ( (_WORD)v8 )
  {
    v15 = saturated_mul(v8, 8u);
    v16 = operator new[](v15);
    memset_0(v16, 0, v15);
    LOBYTE(v17) = v27 == 1;
    v14 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, _QWORD, void *, unsigned __int16, _QWORD **, __int64 *))(**(_QWORD **)(a1 + 16) + 64LL))(
            *(_QWORD *)(a1 + 16),
            v9,
            v17,
            a5,
            v16,
            a3,
            &a6,
            &v24);
    if ( v14 >= 0 && (_WORD)a6 )
    {
      v18 = CoTaskMemAlloc(232LL * (unsigned __int16)a6);
      if ( v18 )
      {
        v19 = 0;
        if ( (_WORD)a6 )
        {
          do
          {
            v14 = CDPActivityToComActivityData(*((__int64 **)v16 + v19), (__int64)v18 + 232 * v19);
            if ( v14 < 0 )
              break;
            ++v19;
          }
          while ( v19 < (unsigned __int16)a6 );
          v12 = a7;
        }
        *v10 = v18;
        *v12 = v19;
      }
      else
      {
        v14 = -2147024882;
      }
      v20 = 0;
      if ( (_WORD)a6 )
      {
        do
        {
          v21 = *((_QWORD *)v16 + v20);
          if ( v21 )
            (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v21 + 16LL))(v21, 0);
          ++v20;
        }
        while ( v20 < (unsigned __int16)a6 );
      }
    }
    operator delete(v16);
    v9 = v24;
  }
  *a8 = v9;
  if ( v13 )
    ReleaseSRWLockShared(v13);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x180019ed0  mov     rax, rsp
0x180019ed3  mov     [rax+10h], rbx
0x180019ed7  mov     [rax+20h], r9d
0x180019edb  mov     [rax+18h], r8w
0x180019ee0  mov     [rax+8], rcx
0x180019ee4  push    rbp
0x180019ee5  push    rsi
0x180019ee6  push    rdi
0x180019ee7  push    r12
0x180019ee9  push    r13
0x180019eeb  push    r14
0x180019eed  push    r15
0x180019eef  mov     rbp, rsp
0x180019ef2  sub     rsp, 70h
0x180019ef6  movzx   ebx, r8w
0x180019efa  mov     rdi, rdx
0x180019efd  mov     r15, [rbp+arg_28]
0x180019f01  xor     r13d, r13d
0x180019f04  test    r15, r15
0x180019f07  jnz     short loc_180019F31
0x180019f09  mov     [rbp+var_18], 259h
0x180019f10  mov     [rbp+var_20], 80004003h
0x180019f17  lea     rax, [rbp+var_18]
0x180019f1b  mov     [rsp+70h+var_50], rax
0x180019f20  lea     r8, [rbp+var_20]
0x180019f24  call    ??$Log@AEAJAEAY0BL@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BL@$$CBD$$QEAH@Z; Log<long &,char const (&)[27],int>(CDPLogLevel,char const *,long &,char const (&)[27],int &&)
0x180019f29  mov     eax, [rbp+var_20]
0x180019f2c  jmp     loc_18001A0C5
0x180019f31  mov     r14, [rbp+arg_30]
0x180019f35  test    r14, r14
0x180019f38  jnz     short loc_180019F43
0x180019f3a  mov     [rbp+var_18], 25Ah
0x180019f41  jmp     short loc_180019F10
0x180019f43  cmp     [rbp+arg_38], r13
0x180019f47  jnz     short loc_180019F52
0x180019f49  mov     [rbp+var_18], 25Bh
0x180019f50  jmp     short loc_180019F10
0x180019f52  lea     r12, [rcx+20h]
0x180019f56  mov     rcx, r12; SRWLock
0x180019f59  call    cs:__imp_AcquireSRWLockShared
0x180019f5f  mov     [r14], r13w
0x180019f63  mov     [r15], r13
0x180019f66  mov     esi, r13d
0x180019f69  mov     word ptr [rbp+arg_28], r13w
0x180019f6e  mov     [rbp+var_10], rdi
0x180019f72  test    bx, bx
0x180019f75  jz      loc_18001A0AE
0x180019f7b  mov     eax, 8
0x180019f80  mul     rbx
0x180019f83  mov     rbx, rax
0x180019f86  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180019f8d  cmovb   rbx, rax
0x180019f91  mov     rcx, rbx; unsigned __int64
0x180019f94  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180019f99  mov     r13, rax
0x180019f9c  mov     r8, rbx; Size
0x180019f9f  xor     edx, edx; Val
0x180019fa1  mov     rcx, rax; void *
0x180019fa4  call    memset_0
0x180019fa9  mov     rax, [rbp+arg_0]
0x180019fad  mov     rcx, [rax+10h]
0x180019fb1  mov     rax, [rcx]
0x180019fb4  cmp     [rbp+arg_18], 1
0x180019fb8  setz    r8b
0x180019fbc  lea     rdx, [rbp+var_10]
0x180019fc0  mov     [rsp+70h+var_38], rdx
0x180019fc5  lea     rdx, [rbp+arg_28]
0x180019fc9  mov     [rsp+70h+var_40], rdx
0x180019fce  movzx   edx, [rbp+arg_10]
0x180019fd2  mov     [rsp+70h+var_48], dx
0x180019fd7  mov     [rsp+70h+var_50], r13
0x180019fdc  mov     r9d, [rbp+arg_20]
0x180019fe0  mov     rdx, rdi
0x180019fe3  mov     rax, [rax+40h]
0x180019fe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019fec  mov     esi, eax
0x180019fee  test    eax, eax
0x180019ff0  js      loc_18001A0A2
0x180019ff6  movzx   ecx, word ptr [rbp+arg_28]
0x180019ffa  test    cx, cx
0x180019ffd  jz      loc_18001A0A2
0x18001a003  imul    rcx, 0E8h; cb
0x18001a00a  call    cs:__imp_CoTaskMemAlloc
0x18001a010  mov     rbx, rax
0x18001a013  xor     edx, edx
0x18001a015  test    rax, rax
0x18001a018  jz      short loc_18001A062
0x18001a01a  mov     edi, edx
0x18001a01c  cmp     dx, word ptr [rbp+arg_28]
0x18001a020  jnb     short loc_18001A053
0x18001a022  lea     r14d, [rdx+1]
0x18001a026  movzx   ecx, di
0x18001a029  imul    rdx, rcx, 0E8h
0x18001a030  add     rdx, rbx
0x18001a033  mov     rcx, [r13+rcx*8+0]
0x18001a038  call    CDPActivityToComActivityData
0x18001a03d  mov     esi, eax
0x18001a03f  test    eax, eax
0x18001a041  js      short loc_18001A04D
0x18001a043  add     di, r14w
0x18001a047  cmp     di, word ptr [rbp+arg_28]
0x18001a04b  jb      short loc_18001A026
0x18001a04d  mov     r14, [rbp+arg_30]
0x18001a051  xor     edx, edx
0x18001a053  mov     rax, rbx
0x18001a056  mov     rbx, rdx
0x18001a059  mov     [r15], rax
0x18001a05c  mov     [r14], di
0x18001a060  jmp     short loc_18001A067
0x18001a062  mov     esi, 8007000Eh
0x18001a067  mov     edi, edx
0x18001a069  cmp     dx, word ptr [rbp+arg_28]
0x18001a06d  jnb     short loc_18001A0A2
0x18001a06f  movsxd  rax, edi
0x18001a072  mov     rcx, [r13+rax*8+0]
0x18001a077  test    rcx, rcx
0x18001a07a  jz      short loc_18001A08A
0x18001a07c  mov     rax, [rcx]
0x18001a07f  mov     rax, [rax+10h]
0x18001a083  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a088  xor     edx, edx
0x18001a08a  inc     edi
0x18001a08c  movzx   eax, word ptr [rbp+arg_28]
0x18001a090  cmp     edi, eax
0x18001a092  jl      short loc_18001A06F
0x18001a094  test    rbx, rbx
0x18001a097  jz      short loc_18001A0A2
0x18001a099  mov     rcx, rbx; pv
0x18001a09c  call    cs:__imp_CoTaskMemFree
0x18001a0a2  mov     rcx, r13; Block
0x18001a0a5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001a0aa  mov     rdi, [rbp+var_10]
0x18001a0ae  mov     rax, [rbp+arg_38]
0x18001a0b2  mov     [rax], rdi
0x18001a0b5  test    r12, r12
0x18001a0b8  jz      short loc_18001A0C3
0x18001a0ba  mov     rcx, r12; SRWLock
0x18001a0bd  call    cs:__imp_ReleaseSRWLockShared
0x18001a0c3  mov     eax, esi
0x18001a0c5  mov     rbx, [rsp+70h+arg_8]
0x18001a0cd  add     rsp, 70h
0x18001a0d1  pop     r15
0x18001a0d3  pop     r14
0x18001a0d5  pop     r13
0x18001a0d7  pop     r12
0x18001a0d9  pop     rdi
0x18001a0da  pop     rsi
0x18001a0db  pop     rbp
0x18001a0dc  retn
```
