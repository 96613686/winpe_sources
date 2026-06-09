# MpConfigUtils::CSimpleMpConfig::GetCachedKey(ushort const *,MpConfigUtils::CRefCachedConfigKey * *)

- ea: `0x18000627c`
- end: `0x180006496`
- name: `?GetCachedKey@CSimpleMpConfig@MpConfigUtils@@AEBAJPEBGPEAPEAVCRefCachedConfigKey@2@@Z`
- size: `538`
- prototype: `__int64 __fastcall(MpConfigUtils::CSimpleMpConfig *this, unsigned __int16 **, struct MpConfigUtils::CRefCachedConfigKey **)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180006170`
- `0x1800065c0`
- `0x180006700`

## callees

- `0x180005f14`
- `0x18000627c`
- `0x180007d9c`
- `0x18000a010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800062e5`
- `msvcrt!_wcsicmp` at `0x1800062e5`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180006394`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180006394`
- `KERNEL32!LeaveCriticalSection` at `0x1800062d3`
- `KERNEL32!LeaveCriticalSection` at `0x180006443`
- `KERNEL32!LeaveCriticalSection` at `0x1800062d3`
- `KERNEL32!LeaveCriticalSection` at `0x180006443`
- `KERNEL32!EnterCriticalSection` at `0x1800062a9`
- `KERNEL32!EnterCriticalSection` at `0x180006432`
- `KERNEL32!EnterCriticalSection` at `0x1800062a9`
- `KERNEL32!EnterCriticalSection` at `0x180006432`
- `mpclient!MpConfigClose` at `0x1800063be`
- `mpclient!MpConfigClose` at `0x1800063be`
- `mpclient!MpConfigOpen` at `0x1800063d1`
- `mpclient!MpConfigOpen` at `0x1800063d1`

## pseudocode

```c
__int64 __fastcall MpConfigUtils::CSimpleMpConfig::GetCachedKey(
        MpConfigUtils::CSimpleMpConfig *this,
        unsigned __int16 **a2,
        struct MpConfigUtils::CRefCachedConfigKey **a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // rsi
  __int64 v7; // rbx
  int v8; // edi
  const unsigned __int16 *v9; // r8
  void (__fastcall ***v10)(_QWORD, __int64); // rcx
  __int64 v11; // rbx
  CommonUtil *v12; // rdi
  void *v13; // rcx
  __int64 v15; // rdi
  __int64 v16; // [rsp+50h] [rbp+8h] BYREF

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  *a3 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v7 = *((_QWORD *)this + 7);
  if ( v7 )
  {
    if ( *(_DWORD *)(v7 + 8) )
      _InterlockedAdd((volatile signed __int32 *)(v7 + 8), 1u);
    else
      *(_DWORD *)(v7 + 8) = 1;
  }
  LeaveCriticalSection(v3);
  if ( !v7 )
    goto LABEL_12;
  if ( _wcsicmp((const wchar_t *)a2, *(const wchar_t **)(v7 + 24)) )
  {
    if ( *(_DWORD *)(v7 + 8) == 1 )
    {
      *(_DWORD *)(v7 + 8) = 0;
    }
    else if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v7 + 8), 0xFFFFFFFF) > 1 )
    {
      goto LABEL_12;
    }
    (**(void (__fastcall ***)(__int64, __int64))v7)(v7, 1);
LABEL_12:
    v16 = 0;
    v8 = CommonUtil::CreateNewRefObject<MpConfigUtils::CRefCachedConfigKey>(&v16);
    if ( v8 >= 0 )
    {
      v11 = v16;
      v12 = (CommonUtil *)(v16 + 24);
      v13 = *(void **)(v16 + 24);
      if ( v13 )
      {
        operator delete[](v13);
        *(_QWORD *)v12 = 0;
      }
      v8 = CommonUtil::HrDuplicateStringW(v12, a2, v9);
      if ( v8 >= 0 )
      {
        if ( *(_QWORD *)(v11 + 16) )
        {
          MpConfigClose();
          *(_QWORD *)(v11 + 16) = 0;
        }
        v8 = MpConfigOpen(a2, v11 + 16);
        if ( v8 >= 0 )
        {
          if ( v11 )
          {
            if ( *(_DWORD *)(v11 + 8) )
              _InterlockedAdd((volatile signed __int32 *)(v11 + 8), 1u);
            else
              *(_DWORD *)(v11 + 8) = 1;
          }
          *a3 = (struct MpConfigUtils::CRefCachedConfigKey *)v11;
          EnterCriticalSection(v3);
          v15 = *((_QWORD *)this + 7);
          *((_QWORD *)this + 7) = v11;
          LeaveCriticalSection(v3);
          if ( !v15 )
            return 0;
          if ( *(_DWORD *)(v15 + 8) == 1 )
          {
            *(_DWORD *)(v15 + 8) = 0;
          }
          else if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v15 + 8), 0xFFFFFFFF) > 1 )
          {
            return 0;
          }
          (**(void (__fastcall ***)(__int64, __int64))v15)(v15, 1);
          return 0;
        }
      }
      if ( v11 )
      {
        if ( *(_DWORD *)(v11 + 8) == 1 )
        {
          *(_DWORD *)(v11 + 8) = 0;
        }
        else if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v11 + 8), 0xFFFFFFFF) > 1 )
        {
          return (unsigned int)v8;
        }
        (**(void (__fastcall ***)(__int64, __int64))v11)(v11, 1);
      }
    }
    else
    {
      v10 = (void (__fastcall ***)(_QWORD, __int64))v16;
      if ( v16 )
      {
        if ( *(_DWORD *)(v16 + 8) == 1 )
        {
          *(_DWORD *)(v16 + 8) = 0;
          goto LABEL_17;
        }
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v16 + 8), 0xFFFFFFFF) <= 1 )
        {
LABEL_17:
          if ( v10 )
            (**v10)(v10, 1);
        }
      }
    }
    return (unsigned int)v8;
  }
  *a3 = (struct MpConfigUtils::CRefCachedConfigKey *)v7;
  return 0;
}

```

## disassembly

```asm
0x18000627c  mov     [rsp+arg_8], rbx
0x180006281  mov     [rsp+arg_10], rbp
0x180006286  push    rsi
0x180006287  push    rdi
0x180006288  push    r13
0x18000628a  push    r14
0x18000628c  push    r15
0x18000628e  sub     rsp, 20h
0x180006292  lea     rsi, [rcx+10h]
0x180006296  mov     qword ptr [r8], 0
0x18000629d  mov     rbp, rcx
0x1800062a0  mov     r14, r8
0x1800062a3  mov     rcx, rsi; lpCriticalSection
0x1800062a6  mov     r15, rdx
0x1800062a9  call    cs:__imp_EnterCriticalSection
0x1800062af  mov     rbx, [rbp+38h]
0x1800062b3  mov     r13d, 1
0x1800062b9  test    rbx, rbx
0x1800062bc  jz      short loc_1800062D0
0x1800062be  mov     eax, [rbx+8]
0x1800062c1  test    eax, eax
0x1800062c3  jnz     short loc_1800062CB
0x1800062c5  mov     [rbx+8], r13d
0x1800062c9  jmp     short loc_1800062D0
0x1800062cb  lock add [rbx+8], r13d
0x1800062d0  mov     rcx, rsi; lpCriticalSection
0x1800062d3  call    cs:__imp_LeaveCriticalSection
0x1800062d9  test    rbx, rbx
0x1800062dc  jz      short loc_180006326
0x1800062de  mov     rdx, [rbx+18h]; String2
0x1800062e2  mov     rcx, r15; String1
0x1800062e5  call    cs:__imp__wcsicmp
0x1800062eb  test    eax, eax
0x1800062ed  jnz     short loc_1800062F7
0x1800062ef  mov     [r14], rbx
0x1800062f2  jmp     loc_18000647D
0x1800062f7  mov     eax, [rbx+8]
0x1800062fa  cmp     eax, r13d
0x1800062fd  jnz     short loc_180006308
0x1800062ff  mov     dword ptr [rbx+8], 0
0x180006306  jmp     short loc_180006315
0x180006308  or      eax, 0FFFFFFFFh
0x18000630b  lock xadd [rbx+8], eax
0x180006310  sub     eax, r13d
0x180006313  jg      short loc_180006326
0x180006315  mov     rax, [rbx]
0x180006318  mov     edx, r13d
0x18000631b  mov     rcx, rbx
0x18000631e  mov     rax, [rax]
0x180006321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006326  lea     rcx, [rsp+48h+arg_0]
0x18000632b  mov     [rsp+48h+arg_0], 0
0x180006334  call    ??$CreateNewRefObject@VCRefCachedConfigKey@MpConfigUtils@@@CommonUtil@@YAJPEAPEAVCRefCachedConfigKey@MpConfigUtils@@@Z; CommonUtil::CreateNewRefObject<MpConfigUtils::CRefCachedConfigKey>(MpConfigUtils::CRefCachedConfigKey * *)
0x180006339  mov     edi, eax
0x18000633b  test    eax, eax
0x18000633d  jns     short loc_180006383
0x18000633f  mov     rcx, [rsp+48h+arg_0]
0x180006344  test    rcx, rcx
0x180006347  jz      loc_180006411
0x18000634d  mov     eax, [rcx+8]
0x180006350  cmp     eax, r13d
0x180006353  jnz     short loc_18000635E
0x180006355  mov     dword ptr [rcx+8], 0
0x18000635c  jmp     short loc_18000636F
0x18000635e  or      eax, 0FFFFFFFFh
0x180006361  lock xadd [rcx+8], eax
0x180006366  sub     eax, r13d
0x180006369  jg      loc_180006411
0x18000636f  test    rcx, rcx
0x180006372  jz      loc_180006411
0x180006378  mov     rax, [rcx]
0x18000637b  mov     rax, [rax]
0x18000637e  jmp     loc_180006409
0x180006383  mov     rbx, [rsp+48h+arg_0]
0x180006388  lea     rdi, [rbx+18h]
0x18000638c  mov     rcx, [rdi]
0x18000638f  test    rcx, rcx
0x180006392  jz      short loc_1800063A1
0x180006394  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000639a  mov     qword ptr [rdi], 0
0x1800063a1  mov     rdx, r15; unsigned __int16 **
0x1800063a4  mov     rcx, rdi; this
0x1800063a7  call    ?HrDuplicateStringW@CommonUtil@@YAJPEAPEAGPEBG@Z; CommonUtil::HrDuplicateStringW(ushort * *,ushort const *)
0x1800063ac  mov     edi, eax
0x1800063ae  test    eax, eax
0x1800063b0  js      short loc_1800063DD
0x1800063b2  lea     rdi, [rbx+10h]
0x1800063b6  mov     rcx, [rdi]
0x1800063b9  test    rcx, rcx
0x1800063bc  jz      short loc_1800063CB
0x1800063be  call    cs:__imp_MpConfigClose
0x1800063c4  mov     qword ptr [rdi], 0
0x1800063cb  mov     rdx, rdi
0x1800063ce  mov     rcx, r15
0x1800063d1  call    cs:__imp_MpConfigOpen
0x1800063d7  mov     edi, eax
0x1800063d9  test    eax, eax
0x1800063db  jns     short loc_180006415
0x1800063dd  test    rbx, rbx
0x1800063e0  jz      short loc_180006411
0x1800063e2  mov     eax, [rbx+8]
0x1800063e5  cmp     eax, r13d
0x1800063e8  jnz     short loc_1800063F3
0x1800063ea  mov     dword ptr [rbx+8], 0
0x1800063f1  jmp     short loc_180006400
0x1800063f3  or      eax, 0FFFFFFFFh
0x1800063f6  lock xadd [rbx+8], eax
0x1800063fb  sub     eax, r13d
0x1800063fe  jg      short loc_180006411
0x180006400  mov     rdx, [rbx]
0x180006403  mov     rcx, rbx
0x180006406  mov     rax, [rdx]
0x180006409  mov     edx, r13d
0x18000640c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006411  mov     eax, edi
0x180006413  jmp     short loc_18000647F
0x180006415  test    rbx, rbx
0x180006418  jz      short loc_18000642C
0x18000641a  mov     eax, [rbx+8]
0x18000641d  test    eax, eax
0x18000641f  jnz     short loc_180006427
0x180006421  mov     [rbx+8], r13d
0x180006425  jmp     short loc_18000642C
0x180006427  lock add [rbx+8], r13d
0x18000642c  mov     rcx, rsi; lpCriticalSection
0x18000642f  mov     [r14], rbx
0x180006432  call    cs:__imp_EnterCriticalSection
0x180006438  mov     rdi, [rbp+38h]
0x18000643c  mov     rcx, rsi; lpCriticalSection
0x18000643f  mov     [rbp+38h], rbx
0x180006443  call    cs:__imp_LeaveCriticalSection
0x180006449  test    rdi, rdi
0x18000644c  jz      short loc_18000647D
0x18000644e  mov     eax, [rdi+8]
0x180006451  cmp     eax, r13d
0x180006454  jnz     short loc_18000645F
0x180006456  mov     dword ptr [rdi+8], 0
0x18000645d  jmp     short loc_18000646C
0x18000645f  or      eax, 0FFFFFFFFh
0x180006462  lock xadd [rdi+8], eax
0x180006467  sub     eax, r13d
0x18000646a  jg      short loc_18000647D
0x18000646c  mov     rax, [rdi]
0x18000646f  mov     edx, r13d
0x180006472  mov     rcx, rdi
0x180006475  mov     rax, [rax]
0x180006478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000647d  xor     eax, eax
0x18000647f  mov     rbx, [rsp+48h+arg_8]
0x180006484  mov     rbp, [rsp+48h+arg_10]
0x180006489  add     rsp, 20h
0x18000648d  pop     r15
0x18000648f  pop     r14
0x180006491  pop     r13
0x180006493  pop     rdi
0x180006494  pop     rsi
0x180006495  retn
```
