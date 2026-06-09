# LKRhash::CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool,bool,CLKRhashAllocator *)

- ea: `0x180007a34`
- end: `0x180007d0f`
- name: `??0CLKRHashTable@LKRhash@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N7PEAVCLKRhashAllocator@@@Z`
- size: `731`
- prototype: `__int64 __usercall@<rax>(LKRhash::CLKRHashTable *__hidden this@<rcx>, const char *@<rdx>, unsigned __int64 (*)(const void *)@<r8>, unsigned int (*)(unsigned __int64)@<r9>, bool (*)(unsigned __int64, unsigned __int64), void (*)(const void *, int), double, unsigned int, unsigned int, bool, bool, struct CLKRhashAllocator *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180004ca0`

## callees

- `0x1800077fc`
- `0x180007a34`
- `0x180007e18`
- `0x1800084e0`
- `0x180008564`
- `0x1800088a4`
- `0x18000b010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180007adc`
- `KERNEL32!GetCurrentThreadId` at `0x180007af6`
- `KERNEL32!GetCurrentThreadId` at `0x180007adc`
- `KERNEL32!GetCurrentThreadId` at `0x180007af6`

## pseudocode

```c
LKRhash::CLKRHashTable *__fastcall LKRhash::CLKRHashTable::CLKRHashTable(
        LKRhash::CLKRHashTable *this,
        const char *a2,
        unsigned __int64 (*a3)(const void *),
        unsigned int (*a4)(unsigned __int64),
        bool (*a5)(unsigned __int64, unsigned __int64),
        void (*a6)(const void *, int),
        double a7)
{
  const char *v9; // r8
  __int64 v10; // rdx
  __int64 v11; // rax
  char *v13; // rcx
  char *v14; // rax
  _QWORD *v15; // rbx
  _QWORD *v16; // rax
  unsigned __int64 v17; // rbx
  __int64 v18; // rax
  unsigned int i; // edx
  __int64 v20; // rcx
  unsigned int v21; // esi
  unsigned int v22; // r15d
  LKRhash::CLKRLinearHashTable *v23; // rcx
  LKRhash::CLKRLinearHashTable *v24; // rbx
  bool v26; // [rsp+48h] [rbp-80h]
  bool v27; // [rsp+50h] [rbp-78h]
  unsigned int v28; // [rsp+60h] [rbp-68h] BYREF
  unsigned int v29; // [rsp+68h] [rbp-60h] BYREF

  v28 = 0;
  v29 = 2;
  *((_QWORD *)this + 4) = a3;
  *((_QWORD *)this + 7) = &LKRhash::CLKRHashTable::sm_DefaultAllocator;
  v9 = a2;
  *(_DWORD *)this = 1414024012;
  v10 = 16;
  *((_DWORD *)this + 5) = 0;
  v11 = 2147483646;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 5) = a4;
  *((_DWORD *)this + 12) = -95;
  v13 = (char *)this + 4;
  do
  {
    if ( !v11 )
      break;
    if ( !*v9 )
      break;
    *v13++ = *v9++;
    --v11;
    --v10;
  }
  while ( v10 );
  v14 = v13 - 1;
  v15 = (_QWORD *)((char *)this + 64);
  if ( v10 )
    v14 = v13;
  *v14 = 0;
  if ( LKRhash::CLKRHashTable::sm_llGlobalList
    || _InterlockedCompareExchange(
         (volatile signed __int32 *)&LKRhash::CLKRHashTable::sm_llGlobalList,
         GetCurrentThreadId() & 0xFFFFFFFC | 1,
         0) )
  {
    if ( (LKRhash::CLKRHashTable::sm_llGlobalList & 0xFFFFFFFC) == (GetCurrentThreadId() & 0xFFFFFFFC) )
      _InterlockedExchange(
        (volatile __int32 *)&LKRhash::CLKRHashTable::sm_llGlobalList,
        LKRhash::CLKRHashTable::sm_llGlobalList + 1);
    else
      CSpinLock::_LockSpin((CSpinLock *)&LKRhash::CLKRHashTable::sm_llGlobalList);
  }
  *((_QWORD *)this + 9) = &off_180011058;
  v16 = off_180011058;
  *v15 = off_180011058;
  v16[1] = v15;
  off_180011058 = (_UNKNOWN *)((char *)this + 64);
  _InterlockedExchange(
    (volatile __int32 *)&LKRhash::CLKRHashTable::sm_llGlobalList,
    ((LKRhash::CLKRHashTable::sm_llGlobalList - 1) & 3) != 0 ? LKRhash::CLKRHashTable::sm_llGlobalList - 1 : 0);
  if ( a3 && a4 && a5 && a6 )
  {
    if ( byte_180011848 )
    {
      LKRhash::CLKRHashTable::NumSubTables(&v29, &v28);
      v17 = v28;
      *((_DWORD *)this + 12) = -98;
      if ( 8 * v17 < v17 )
      {
        *((_QWORD *)this + 3) = 0;
      }
      else
      {
        v18 = (***((__int64 (__fastcall ****)(_QWORD, __int64, __int64))this + 7))(*((_QWORD *)this + 7), 8 * v17, 5);
        *((_QWORD *)this + 3) = v18;
        if ( v18 )
        {
          *((_DWORD *)this + 5) = v17;
          for ( i = 0; i < (unsigned int)v17; LODWORD(v17) = *((_DWORD *)this + 5) )
          {
            v20 = i++;
            *(_QWORD *)(*((_QWORD *)this + 3) + 8 * v20) = 0;
          }
          v21 = 0;
          if ( (_DWORD)v17 )
          {
            v22 = v29;
            while ( 1 )
            {
              *(_QWORD *)(*((_QWORD *)this + 3) + 8LL * v21) = LKRhash::CLKRHashTable::_AllocateSubTable(
                                                                 this,
                                                                 a2,
                                                                 a3,
                                                                 a4,
                                                                 a5,
                                                                 a6,
                                                                 a7,
                                                                 v22,
                                                                 this,
                                                                 v26,
                                                                 v27);
              v23 = *(LKRhash::CLKRLinearHashTable **)(*((_QWORD *)this + 3) + 8LL * v21);
              if ( !v23 || !LKRhash::CLKRLinearHashTable::IsValid(v23) )
                break;
              LODWORD(v17) = *((_DWORD *)this + 5);
              if ( ++v21 >= (unsigned int)v17 )
                goto LABEL_27;
            }
            while ( v21 )
            {
              v24 = *(LKRhash::CLKRLinearHashTable **)(*((_QWORD *)this + 3) + 8LL * --v21);
              LKRhash::CLKRLinearHashTable::~CLKRLinearHashTable(v24);
              (*(void (__fastcall **)(_QWORD, LKRhash::CLKRLinearHashTable *, __int64))(**((_QWORD **)this + 7) + 8LL))(
                *((_QWORD *)this + 7),
                v24,
                6);
            }
            (*(void (__fastcall **)(_QWORD, _QWORD, __int64))(**((_QWORD **)this + 7) + 8LL))(
              *((_QWORD *)this + 7),
              *((_QWORD *)this + 3),
              5);
            *((_DWORD *)this + 5) = 0;
            *((_QWORD *)this + 3) = 0;
          }
          else
          {
LABEL_27:
            *((_DWORD *)this + 13) = v17 - 1;
            if ( (((_DWORD)v17 - 1) & (unsigned int)v17) != 0 )
              *((_DWORD *)this + 13) = -1;
            *((_DWORD *)this + 12) = 0;
          }
        }
      }
    }
    else
    {
      *((_DWORD *)this + 12) = -94;
    }
  }
  return this;
}

```

## disassembly

```asm
0x180007a34  mov     rax, rsp
0x180007a37  mov     [rax+10h], rdx
0x180007a3b  push    rbx
0x180007a3c  push    rbp
0x180007a3d  push    rsi
0x180007a3e  push    rdi
0x180007a3f  push    r12
0x180007a41  push    r13
0x180007a43  push    r14
0x180007a45  push    r15
0x180007a47  sub     rsp, 88h
0x180007a4e  xor     r15d, r15d
0x180007a51  movaps  xmmword ptr [rax-58h], xmm6
0x180007a55  mov     [rax-68h], r15d
0x180007a59  mov     r13, r8
0x180007a5c  mov     dword ptr [rax-60h], 2
0x180007a63  mov     rdi, rcx
0x180007a66  lea     rax, ?sm_DefaultAllocator@CLKRHashTable@LKRhash@@0VCLKRhashDefaultAllocator@@A; CLKRhashDefaultAllocator LKRhash::CLKRHashTable::sm_DefaultAllocator
0x180007a6d  mov     [rcx+20h], r8
0x180007a71  mov     [rcx+38h], rax
0x180007a75  mov     r8, rdx
0x180007a78  mov     dword ptr [rcx], 54484B4Ch
0x180007a7e  lea     edx, [r15+10h]
0x180007a82  mov     [rcx+14h], r15d
0x180007a86  mov     eax, 7FFFFFFEh
0x180007a8b  mov     [rcx+18h], r15
0x180007a8f  mov     r12, r9
0x180007a92  mov     [rcx+28h], r9
0x180007a96  mov     dword ptr [rcx+30h], 0FFFFFFA1h
0x180007a9d  add     rcx, 4
0x180007aa1  test    rax, rax
0x180007aa4  jz      short loc_180007AC0
0x180007aa6  mov     r9b, [r8]
0x180007aa9  test    r9b, r9b
0x180007aac  jz      short loc_180007AC0
0x180007aae  mov     [rcx], r9b
0x180007ab1  inc     r8
0x180007ab4  inc     rcx
0x180007ab7  dec     rax
0x180007aba  sub     rdx, 1
0x180007abe  jnz     short loc_180007AA1
0x180007ac0  test    rdx, rdx
0x180007ac3  lea     rax, [rcx-1]
0x180007ac7  lea     rbx, [rdi+40h]
0x180007acb  cmovnz  rax, rcx
0x180007acf  mov     [rax], r15b
0x180007ad2  mov     eax, cs:?sm_llGlobalList@CLKRHashTable@LKRhash@@0VCLockedDoubleList@@A; CLockedDoubleList LKRhash::CLKRHashTable::sm_llGlobalList
0x180007ad8  test    eax, eax
0x180007ada  jnz     short loc_180007AF6
0x180007adc  call    cs:__imp_GetCurrentThreadId
0x180007ae2  mov     ecx, eax
0x180007ae4  and     ecx, 0FFFFFFFDh
0x180007ae7  or      ecx, 1
0x180007aea  xor     eax, eax
0x180007aec  lock cmpxchg cs:?sm_llGlobalList@CLKRHashTable@LKRhash@@0VCLockedDoubleList@@A, ecx; CLockedDoubleList LKRhash::CLKRHashTable::sm_llGlobalList
0x180007af4  jz      short loc_180007B28
0x180007af6  call    cs:__imp_GetCurrentThreadId
0x180007afc  mov     ecx, cs:?sm_llGlobalList@CLKRHashTable@LKRhash@@0VCLockedDoubleList@@A; CLockedDoubleList LKRhash::CLKRHashTable::sm_llGlobalList
0x180007b02  and     eax, 0FFFFFFFCh
0x180007b05  and     ecx, 0FFFFFFFCh
0x180007b08  cmp     ecx, eax
0x180007b0a  jnz     short loc_180007B1C
0x180007b0c  mov     eax, cs:?sm_llGlobalList@CLKRHashTable@LKRhash@@0VCLockedDoubleList@@A; CLockedDoubleList LKRhash::CLKRHashTable::sm_llGlobalList
0x180007b12  inc     eax
0x180007b14  xchg    eax, cs:?sm_llGlobalList@CLKRHashTable@LKRhash@@0VCLockedDoubleList@@A; CLockedDoubleList LKRhash::CLKRHashTable::sm_llGlobalList
0x180007b1a  jmp     short loc_180007B28
0x180007b1c  lea     rcx, ?sm_llGlobalList@CLKRHashTable@LKRhash@@0VCLockedDoubleList@@A; this
0x180007b23  call    ?_LockSpin@CSpinLock@@AEAAXXZ; CSpinLock::_LockSpin(void)
0x180007b28  lea     rax, off_180011058
0x180007b2f  mov     [rbx+8], rax
0x180007b33  mov     rax, cs:off_180011058
0x180007b3a  mov     [rbx], rax
0x180007b3d  mov     [rax+8], rbx
0x180007b41  mov     edx, cs:?sm_llGlobalList@CLKRHashTable@LKRhash@@0VCLockedDoubleList@@A; CLockedDoubleList LKRhash::CLKRHashTable::sm_llGlobalList
0x180007b47  dec     edx
0x180007b49  mov     cs:off_180011058, rbx
0x180007b50  mov     eax, edx
0x180007b52  and     al, 3
0x180007b54  neg     al
0x180007b56  sbb     ecx, ecx
0x180007b58  and     ecx, edx
0x180007b5a  xchg    ecx, cs:?sm_llGlobalList@CLKRHashTable@LKRhash@@0VCLockedDoubleList@@A; CLockedDoubleList LKRhash::CLKRHashTable::sm_llGlobalList
0x180007b60  test    r13, r13
0x180007b63  jz      loc_180007CF3
0x180007b69  test    r12, r12
0x180007b6c  jz      loc_180007CF3
0x180007b72  mov     rbp, [rsp+0C8h+arg_20]
0x180007b7a  test    rbp, rbp
0x180007b7d  jz      loc_180007CF3
0x180007b83  mov     r14, [rsp+0C8h+arg_28]
0x180007b8b  test    r14, r14
0x180007b8e  jz      loc_180007CF3
0x180007b94  cmp     cs:byte_180011848, r15b
0x180007b9b  jnz     short loc_180007BA9
0x180007b9d  mov     dword ptr [rdi+30h], 0FFFFFFA2h
0x180007ba4  jmp     loc_180007CF3
0x180007ba9  lea     rdx, [rsp+0C8h+var_68]
0x180007bae  lea     rcx, [rsp+0C8h+var_60]
0x180007bb3  call    ?NumSubTables@CLKRHashTable@LKRhash@@SA?AW4LK_TABLESIZE@2@AEAK0_N@Z; LKRhash::CLKRHashTable::NumSubTables(ulong &,ulong &,bool)
0x180007bb8  mov     ebx, [rsp+0C8h+var_68]
0x180007bbc  mov     dword ptr [rdi+30h], 0FFFFFF9Eh
0x180007bc3  lea     rdx, ds:0[rbx*8]
0x180007bcb  cmp     rdx, rbx
0x180007bce  jb      loc_180007CEF
0x180007bd4  mov     rcx, [rdi+38h]
0x180007bd8  mov     r8d, 5
0x180007bde  mov     rax, [rcx]
0x180007be1  mov     rax, [rax]
0x180007be4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007be9  mov     [rdi+18h], rax
0x180007bed  test    rax, rax
0x180007bf0  jz      loc_180007CF3
0x180007bf6  mov     [rdi+14h], ebx
0x180007bf9  mov     edx, r15d
0x180007bfc  test    ebx, ebx
0x180007bfe  jz      short loc_180007C13
0x180007c00  mov     rax, [rdi+18h]
0x180007c04  mov     ecx, edx
0x180007c06  inc     edx
0x180007c08  mov     [rax+rcx*8], r15
0x180007c0c  mov     ebx, [rdi+14h]
0x180007c0f  cmp     edx, ebx
0x180007c11  jb      short loc_180007C00
0x180007c13  mov     esi, r15d
0x180007c16  test    ebx, ebx
0x180007c18  jz      short loc_180007C84
0x180007c1a  mov     r15d, [rsp+0C8h+var_60]
0x180007c1f  movsd   xmm6, [rsp+0C8h+arg_30]
0x180007c28  mov     rdx, [rsp+0C8h+arg_8]; char *
0x180007c30  mov     r9, r12; unsigned int (*)(unsigned __int64)
0x180007c33  mov     [rsp+0C8h+var_88], rdi; struct LKRhash::CLKRHashTable *
0x180007c38  mov     r8, r13; unsigned __int64 (*)(const void *)
0x180007c3b  mov     [rsp+0C8h+var_90], r15d; unsigned int
0x180007c40  mov     rcx, rdi; this
0x180007c43  movsd   [rsp+0C8h+var_98], xmm6; double
0x180007c49  mov     [rsp+0C8h+var_A0], r14; void (*)(const void *, int)
0x180007c4e  mov     [rsp+0C8h+var_A8], rbp; bool (*)(unsigned __int64, unsigned __int64)
0x180007c53  call    ?_AllocateSubTable@CLKRHashTable@LKRhash@@AEAAQEAVCLKRLinearHashTable@2@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKPEAV12@_N8@Z; LKRhash::CLKRHashTable::_AllocateSubTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,LKRhash::CLKRHashTable *,bool,bool)
0x180007c58  mov     rcx, [rdi+18h]
0x180007c5c  mov     edx, esi
0x180007c5e  mov     [rcx+rdx*8], rax
0x180007c62  mov     rax, [rdi+18h]
0x180007c66  mov     rcx, [rax+rdx*8]; this
0x180007c6a  test    rcx, rcx
0x180007c6d  jz      short loc_180007CC6
0x180007c6f  call    ?IsValid@CLKRLinearHashTable@LKRhash@@QEBA_NXZ; LKRhash::CLKRLinearHashTable::IsValid(void)
0x180007c74  test    al, al
0x180007c76  jz      short loc_180007CC6
0x180007c78  mov     ebx, [rdi+14h]
0x180007c7b  inc     esi
0x180007c7d  cmp     esi, ebx
0x180007c7f  jb      short loc_180007C28
0x180007c81  xor     r15d, r15d
0x180007c84  lea     eax, [rbx-1]
0x180007c87  mov     [rdi+34h], eax
0x180007c8a  test    ebx, eax
0x180007c8c  jz      short loc_180007C95
0x180007c8e  mov     dword ptr [rdi+34h], 0FFFFFFFFh
0x180007c95  mov     [rdi+30h], r15d
0x180007c99  jmp     short loc_180007CF3
0x180007c9b  mov     rax, [rdi+18h]
0x180007c9f  dec     esi
0x180007ca1  mov     rbx, [rax+rsi*8]
0x180007ca5  mov     rcx, rbx; this
0x180007ca8  call    ??1CLKRLinearHashTable@LKRhash@@QEAA@XZ; LKRhash::CLKRLinearHashTable::~CLKRLinearHashTable(void)
0x180007cad  mov     rcx, [rdi+38h]
0x180007cb1  mov     r8d, 6
0x180007cb7  mov     rdx, rbx
0x180007cba  mov     rax, [rcx]
0x180007cbd  mov     rax, [rax+8]
0x180007cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cc6  test    esi, esi
0x180007cc8  jnz     short loc_180007C9B
0x180007cca  mov     rcx, [rdi+38h]
0x180007cce  lea     r8d, [rsi+5]
0x180007cd2  mov     rdx, [rdi+18h]
0x180007cd6  mov     rax, [rcx]
0x180007cd9  mov     rax, [rax+8]
0x180007cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ce2  mov     [rdi+14h], esi
0x180007ce5  mov     qword ptr [rdi+18h], 0
0x180007ced  jmp     short loc_180007CF3
0x180007cef  mov     [rdi+18h], r15
0x180007cf3  movaps  xmm6, [rsp+0C8h+var_58]
0x180007cf8  mov     rax, rdi
0x180007cfb  add     rsp, 88h
0x180007d02  pop     r15
0x180007d04  pop     r14
0x180007d06  pop     r13
0x180007d08  pop     r12
0x180007d0a  pop     rdi
0x180007d0b  pop     rsi
0x180007d0c  pop     rbp
0x180007d0d  pop     rbx
0x180007d0e  retn
```
