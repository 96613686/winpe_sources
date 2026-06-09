# CalculateBindingToken(ushort const *,ushort const *,unsigned __int64,ushort *)

- ea: `0x180006340`
- end: `0x1800065db`
- name: `?CalculateBindingToken@@YAJPEBG0_KPEAG@Z`
- size: `667`
- prototype: `__int64 __fastcall(unsigned __int16 *, const unsigned __int16 *, __int64, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x180005c20`
- `0x180008ce0`

## callees

- `0x180006340`
- `0x1800065f0`
- `0x180006630`
- `0x180006700`
- `0x180006810`
- `0x1800069e0`
- `0x180006bf0`
- `0x180008ff0`
- `0x1800090e0`
- `0x180009850`
- `0x18000a1ec`
- `0x18000a210`
- `0x18000b6f4`
- `0x18000efc0`

## pseudocode

```c
__int64 __fastcall CalculateBindingToken(
        unsigned __int16 *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 *a4)
{
  PVOID *v7; // r10
  __int64 v8; // rax
  __int64 v9; // rdx
  unsigned __int16 *v10; // r8
  unsigned __int16 v11; // cx
  unsigned int v12; // ebx
  unsigned __int16 *v13; // rcx
  int v14; // eax
  MbaeHashCalculator *v15; // rax
  const unsigned __int16 *v16; // rdx
  MbaeHashCalculator *v17; // rdi
  const unsigned __int16 *HashHexString; // rax
  int v19; // eax
  __int64 v21; // rdx
  __int64 v22; // r9
  unsigned __int16 v23[72]; // [rsp+40h] [rbp-B8h] BYREF

  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_13b31187e0c23f8b4c6f84a6b6dbb855_Traceguids);
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x10) != 0 )
    {
      WPP_SF_SS(
        (unsigned int)v7[2],
        11,
        (unsigned int)WPP_13b31187e0c23f8b4c6f84a6b6dbb855_Traceguids,
        (_DWORD)a1,
        (__int64)a2);
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  v8 = 2147483646;
  v9 = 68;
  v10 = v23;
  do
  {
    if ( !v8 )
      break;
    v11 = *a1;
    if ( !*a1 )
      break;
    ++a1;
    *v10++ = v11;
    --v8;
    --v9;
  }
  while ( v9 );
  v12 = -2147024774;
  if ( v9 )
    v12 = 0;
  v13 = v10 - 1;
  if ( v9 )
    v13 = v10;
  *v13 = 0;
  if ( v9 )
  {
    if ( !a2 || (v14 = StringCchCatW(v23, 0x44u, a2), v12 = v14, v14 >= 0) )
    {
      v15 = (MbaeHashCalculator *)operator new(0x80u, (const struct std::nothrow_t *)&std::nothrow);
      if ( v15 )
        v17 = MbaeHashCalculator::MbaeHashCalculator(v15, v16);
      else
        v17 = 0;
      if ( v17 )
      {
        v12 = MbaeHashCalculator::Initialize(v17);
        if ( (v12 & 0x80000000) == 0 )
        {
          v12 = MbaeHashCalculator::Calculate(v17, v23);
          if ( (v12 & 0x80000000) == 0 )
          {
            HashHexString = MbaeHashCalculator::GetHashHexString(v17);
            v19 = StringCchCopyW(a4, 0x44u, HashHexString);
            v12 = v19;
            if ( v19 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                14,
                WPP_13b31187e0c23f8b4c6f84a6b6dbb855_Traceguids,
                (unsigned int)v19);
          }
        }
        MbaeHashCalculator::~MbaeHashCalculator(v17);
        operator delete(v17);
      }
      else
      {
        v12 = -2147024882;
      }
      goto LABEL_20;
    }
    v7 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      return v12;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_21;
    v21 = 13;
    v22 = (unsigned int)v14;
LABEL_34:
    WPP_SF_d(v7[2], v21, WPP_13b31187e0c23f8b4c6f84a6b6dbb855_Traceguids, v22);
LABEL_20:
    v7 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_21;
  }
  if ( v7 == &WPP_GLOBAL_Control )
    return v12;
  if ( (*((_BYTE *)v7 + 28) & 2) != 0 )
  {
    v21 = 12;
    v22 = v12;
    goto LABEL_34;
  }
LABEL_21:
  if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 0x10) != 0 )
    WPP_SF_d(v7[2], 15, WPP_13b31187e0c23f8b4c6f84a6b6dbb855_Traceguids, v12);
  return v12;
}

```

## disassembly

```asm
0x180006340  mov     [rsp+arg_10], rbx
0x180006345  push    rbp
0x180006346  push    rsi
0x180006347  push    rdi
0x180006348  sub     rsp, 0E0h
0x18000634f  mov     rax, cs:__security_cookie
0x180006356  xor     rax, rsp
0x180006359  mov     [rsp+0F8h+var_28], rax
0x180006361  mov     rsi, r9
0x180006364  mov     rdi, rdx
0x180006367  mov     rbx, rcx
0x18000636a  lea     rbp, WPP_GLOBAL_Control
0x180006371  mov     r10, cs:WPP_GLOBAL_Control
0x180006378  cmp     r10, rbp
0x18000637b  jnz     loc_1800064C4
0x180006381  mov     eax, 7FFFFFFEh
0x180006386  mov     edx, 44h ; 'D'
0x18000638b  lea     r8, [rsp+0F8h+var_B8]
0x180006390  test    rax, rax
0x180006393  jz      short loc_1800063B2
0x180006395  movzx   ecx, word ptr [rbx]
0x180006398  test    cx, cx
0x18000639b  jz      short loc_1800063B2
0x18000639d  add     rbx, 2
0x1800063a1  mov     [r8], cx
0x1800063a5  add     r8, 2
0x1800063a9  dec     rax
0x1800063ac  sub     rdx, 1
0x1800063b0  jnz     short loc_180006390
0x1800063b2  mov     ebx, 8007007Ah
0x1800063b7  xor     eax, eax
0x1800063b9  test    rdx, rdx
0x1800063bc  cmovnz  ebx, eax
0x1800063bf  lea     rcx, [r8-2]
0x1800063c3  cmovnz  rcx, r8
0x1800063c7  mov     [rcx], ax
0x1800063ca  jz      loc_180006524
0x1800063d0  test    rdi, rdi
0x1800063d3  jz      short loc_1800063F1
0x1800063d5  mov     r8, rdi; unsigned __int16 *
0x1800063d8  mov     edx, 44h ; 'D'; unsigned __int64
0x1800063dd  lea     rcx, [rsp+0F8h+var_B8]; unsigned __int16 *
0x1800063e2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800063e7  mov     ebx, eax
0x1800063e9  test    eax, eax
0x1800063eb  js      loc_18000655F
0x1800063f1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800063f8  mov     ecx, 80h; unsigned __int64
0x1800063fd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006402  mov     [rsp+0F8h+var_C8], rax
0x180006407  test    rax, rax
0x18000640a  jz      loc_1800064BD
0x180006410  mov     rcx, rax; this
0x180006413  call    ??0MbaeHashCalculator@@QEAA@PEBG@Z; MbaeHashCalculator::MbaeHashCalculator(ushort const *)
0x180006418  mov     rdi, rax
0x18000641b  test    rdi, rdi
0x18000641e  jnz     loc_1800064AA
0x180006424  mov     ebx, 8007000Eh
0x180006429  jmp     short loc_180006475
0x18000642b  lea     rdx, [rsp+0F8h+var_B8]; unsigned __int16 *
0x180006430  mov     rcx, rdi; this
0x180006433  call    ?Calculate@MbaeHashCalculator@@QEAAJPEAG@Z; MbaeHashCalculator::Calculate(ushort *)
0x180006438  mov     ebx, eax
0x18000643a  test    eax, eax
0x18000643c  js      short loc_180006460
0x18000643e  mov     rcx, rdi; this
0x180006441  call    ?GetHashHexString@MbaeHashCalculator@@QEBAPEBGXZ; MbaeHashCalculator::GetHashHexString(void)
0x180006446  mov     r8, rax; unsigned __int16 *
0x180006449  mov     edx, 44h ; 'D'; unsigned __int64
0x18000644e  mov     rcx, rsi; unsigned __int16 *
0x180006451  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180006456  mov     ebx, eax
0x180006458  test    eax, eax
0x18000645a  js      loc_18000657C
0x180006460  mov     rcx, rdi; this
0x180006463  call    ??1MbaeHashCalculator@@QEAA@XZ; MbaeHashCalculator::~MbaeHashCalculator(void)
0x180006468  mov     edx, 80h
0x18000646d  mov     rcx, rdi; Block
0x180006470  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006475  mov     r10, cs:WPP_GLOBAL_Control
0x18000647c  cmp     r10, rbp
0x18000647f  jnz     loc_1800065B3
0x180006485  mov     eax, ebx
0x180006487  mov     rcx, [rsp+0F8h+var_28]
0x18000648f  xor     rcx, rsp; StackCookie
0x180006492  call    __security_check_cookie
0x180006497  mov     rbx, [rsp+0F8h+arg_10]
0x18000649f  add     rsp, 0E0h
0x1800064a6  pop     rdi
0x1800064a7  pop     rsi
0x1800064a8  pop     rbp
0x1800064a9  retn
0x1800064aa  mov     rcx, rdi; this
0x1800064ad  call    ?Initialize@MbaeHashCalculator@@QEAAJXZ; MbaeHashCalculator::Initialize(void)
0x1800064b2  mov     ebx, eax
0x1800064b4  test    eax, eax
0x1800064b6  js      short loc_180006460
0x1800064b8  jmp     loc_18000642B
0x1800064bd  xor     edi, edi
0x1800064bf  jmp     loc_18000641B
0x1800064c4  test    byte ptr [r10+1Ch], 10h
0x1800064c9  jz      short loc_1800064E7
0x1800064cb  mov     edx, 0Ah
0x1800064d0  lea     r8, WPP_13b31187e0c23f8b4c6f84a6b6dbb855_Traceguids
0x1800064d7  mov     rcx, [r10+10h]
0x1800064db  call    WPP_SF_
0x1800064e0  mov     r10, cs:WPP_GLOBAL_Control
0x1800064e7  cmp     r10, rbp
0x1800064ea  jz      loc_180006381
0x1800064f0  test    byte ptr [r10+1Ch], 10h
0x1800064f5  jz      loc_180006381
0x1800064fb  mov     edx, 0Bh
0x180006500  mov     [rsp+0F8h+var_D8], rdi
0x180006505  mov     r9, rbx
0x180006508  lea     r8, WPP_13b31187e0c23f8b4c6f84a6b6dbb855_Traceguids
0x18000650f  mov     rcx, [r10+10h]
0x180006513  call    WPP_SF_SS
0x180006518  mov     r10, cs:WPP_GLOBAL_Control
0x18000651f  jmp     loc_180006381
0x180006524  cmp     r10, rbp
0x180006527  jz      loc_180006485
0x18000652d  test    byte ptr [r10+1Ch], 2
0x180006532  jz      loc_18000647C
0x180006538  mov     edx, 0Ch
0x18000653d  mov     r9d, ebx
0x180006540  jmp     short loc_18000654A
0x180006542  mov     edx, 0Dh
0x180006547  mov     r9d, eax
0x18000654a  lea     r8, WPP_13b31187e0c23f8b4c6f84a6b6dbb855_Traceguids
0x180006551  mov     rcx, [r10+10h]
0x180006555  call    WPP_SF_d
0x18000655a  jmp     loc_180006475
0x18000655f  mov     r10, cs:WPP_GLOBAL_Control
0x180006566  cmp     r10, rbp
0x180006569  jz      loc_180006485
0x18000656f  test    byte ptr [r10+1Ch], 2
0x180006574  jz      loc_18000647C
0x18000657a  jmp     short loc_180006542
0x18000657c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006583  cmp     rcx, rbp
0x180006586  jz      loc_180006460
0x18000658c  test    byte ptr [rcx+1Ch], 2
0x180006590  jz      loc_180006460
0x180006596  mov     edx, 0Eh
0x18000659b  mov     r9d, eax
0x18000659e  lea     r8, WPP_13b31187e0c23f8b4c6f84a6b6dbb855_Traceguids
0x1800065a5  mov     rcx, [rcx+10h]
0x1800065a9  call    WPP_SF_d
0x1800065ae  jmp     loc_180006460
0x1800065b3  test    byte ptr [r10+1Ch], 10h
0x1800065b8  jz      loc_180006485
0x1800065be  mov     edx, 0Fh
0x1800065c3  mov     r9d, ebx
0x1800065c6  lea     r8, WPP_13b31187e0c23f8b4c6f84a6b6dbb855_Traceguids
0x1800065cd  mov     rcx, [r10+10h]
0x1800065d1  call    WPP_SF_d
0x1800065d6  jmp     loc_180006485
```
