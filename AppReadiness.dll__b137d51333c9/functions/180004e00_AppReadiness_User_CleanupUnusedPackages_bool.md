# AppReadiness::User::CleanupUnusedPackages(bool)

- ea: `0x180004e00`
- end: `0x180005060`
- name: `?CleanupUnusedPackages@User@AppReadiness@@IEAAX_N@Z`
- size: `608`
- prototype: `void __fastcall(AppReadiness::User *__hidden this, bool)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180010afc`

## callees

- `0x180004e00`
- `0x180005270`
- `0x18000a470`
- `0x1800284a4`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004eff`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180004eff`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004e2c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180004e2c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180005041`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180005041`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall AppReadiness::User::CleanupUnusedPackages(RTL_SRWLOCK *this, char a2)
{
  RTL_SRWLOCK *v4; // r12
  _QWORD *Ptr; // rbx
  _QWORD *v6; // r14
  _QWORD *v7; // r15
  _QWORD *v8; // r15
  __int64 *v9; // rbp
  __int64 *i; // rsi
  __int64 v11; // rax
  __int64 v12; // rcx
  volatile signed __int32 *v13; // r14
  std::_Ref_count_base *v14; // rcx
  __int64 v15; // rsi
  __int64 *v16; // r8
  std::_Ref_count_base *v17; // rbp
  __int64 v18; // rdx
  signed __int32 v19; // eax
  signed __int32 v20; // ett
  __int64 v21; // rax
  char v22; // si
  _QWORD *v23; // r8
  RTL_SRWLOCK *v24; // r9
  const WCHAR *v25; // r8
  const WCHAR *v26; // rcx
  _BYTE v27[8]; // [rsp+40h] [rbp-58h] BYREF
  std::_Ref_count_base *v28; // [rsp+48h] [rbp-50h]

  if ( HIDWORD(this[47].Ptr) == 2 )
  {
    v4 = this + 7;
    AcquireSRWLockExclusive(this + 7);
    Ptr = this[15].Ptr;
    while ( Ptr != this[16].Ptr )
    {
      if ( !a2 && (*(_BYTE *)(*Ptr + 140LL) & 2) != 0 )
      {
LABEL_18:
        Ptr += 2;
      }
      else
      {
        v6 = this[41].Ptr;
        v7 = this[42].Ptr;
        while ( v6 != v7 )
        {
          v15 = *Ptr;
          v16 = (__int64 *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*v6 + 80LL))(*v6, v27);
          v17 = 0;
          v18 = v16[1];
          if ( v18 )
          {
            v19 = *(_DWORD *)(v18 + 8);
            while ( v19 )
            {
              v20 = v19;
              v19 = _InterlockedCompareExchange((volatile signed __int32 *)(v18 + 8), v19 + 1, v19);
              if ( v20 == v19 )
              {
                v21 = *v16;
                v17 = (std::_Ref_count_base *)v16[1];
                if ( *v16 )
                {
                  if ( v15 == v21 )
                    goto LABEL_45;
                  v25 = (const WCHAR *)(v21 + 72);
                  if ( *(_QWORD *)(v21 + 96) > 7u )
                    v25 = *(const WCHAR **)v25;
                  v26 = (const WCHAR *)(v15 + 72);
                  if ( *(_QWORD *)(v15 + 96) > 7u )
                    v26 = *(const WCHAR **)v26;
                  if ( CompareStringOrdinal(v26, -1, v25, -1, 1) == 2 )
                  {
LABEL_45:
                    v22 = 1;
                    goto LABEL_28;
                  }
                }
                break;
              }
            }
          }
          v22 = 0;
LABEL_28:
          if ( v17 )
            std::_Ref_count_base::_Decref(v17);
          if ( v28 )
            std::_Ref_count_base::_Decwref(v28);
          if ( v22 )
            goto LABEL_18;
          ++v6;
        }
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          v23 = (_QWORD *)(*Ptr + 40LL);
          if ( *(_QWORD *)(*Ptr + 64LL) > 7u )
            v23 = (_QWORD *)*v23;
          v24 = this + 8;
          if ( this[11].Ptr > (PVOID)7 )
            v24 = (RTL_SRWLOCK *)v24->Ptr;
          WPP_SF_SSLL(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            23,
            (unsigned int)&WPP_2779cad321383337b9ccea6dca676a06_Traceguids,
            (_DWORD)v24,
            (__int64)v23,
            (*(_DWORD *)(*Ptr + 140LL) & 2) != 0,
            a2);
        }
        v8 = Ptr;
        v9 = (__int64 *)this[16].Ptr;
        for ( i = Ptr + 2; i != v9; i += 2 )
        {
          v11 = *i;
          v12 = i[1];
          *i = 0;
          i[1] = 0;
          *v8 = v11;
          v13 = (volatile signed __int32 *)v8[1];
          v8[1] = v12;
          if ( v13 )
          {
            if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
              std::_Ref_count_base::_Decwref((std::_Ref_count_base *)v13);
            }
          }
          v8 += 2;
        }
        v14 = (std::_Ref_count_base *)*((_QWORD *)this[16].Ptr - 1);
        if ( v14 )
          std::_Ref_count_base::_Decref(v14);
        this[16].Ptr = (char *)this[16].Ptr - 16;
      }
    }
    if ( v4 )
      ReleaseSRWLockExclusive(v4);
  }
}

```

## disassembly

```asm
0x180004e00  push    rbx
0x180004e02  push    rbp
0x180004e03  push    rsi
0x180004e04  push    rdi
0x180004e05  push    r12
0x180004e07  push    r13
0x180004e09  push    r14
0x180004e0b  push    r15
0x180004e0d  sub     rsp, 58h
0x180004e11  movzx   r13d, dl
0x180004e15  mov     rdi, rcx
0x180004e18  cmp     dword ptr [rcx+17Ch], 2
0x180004e1f  jnz     loc_180004F05
0x180004e25  lea     r12, [rcx+38h]
0x180004e29  mov     rcx, r12; SRWLock
0x180004e2c  call    cs:__imp_AcquireSRWLockExclusive
0x180004e32  mov     [rsp+98h+arg_0], r12
0x180004e3a  mov     rbx, [rdi+78h]
0x180004e3e  cmp     rbx, [rdi+80h]
0x180004e45  jz      loc_180004EF7
0x180004e4b  test    r13b, r13b
0x180004e4e  jnz     short loc_180004E60
0x180004e50  mov     rax, [rbx]
0x180004e53  test    byte ptr [rax+8Ch], 2
0x180004e5a  jnz     loc_180004F16
0x180004e60  mov     r14, [rdi+148h]
0x180004e67  mov     r15, [rdi+150h]
0x180004e6e  cmp     r14, r15
0x180004e71  jnz     loc_180004F41
0x180004e77  lea     rax, WPP_GLOBAL_Control
0x180004e7e  mov     r10, cs:WPP_GLOBAL_Control
0x180004e85  cmp     r10, rax
0x180004e88  jnz     loc_180004FB8
0x180004e8e  mov     r15, rbx
0x180004e91  mov     rbp, [rdi+80h]
0x180004e98  lea     rsi, [rbx+10h]
0x180004e9c  cmp     rsi, rbp
0x180004e9f  jz      short loc_180004F1F
0x180004ea1  mov     rax, [rsi]
0x180004ea4  mov     rcx, [rsi+8]
0x180004ea8  mov     qword ptr [rsi], 0
0x180004eaf  mov     qword ptr [rsi+8], 0
0x180004eb7  mov     [r15], rax
0x180004eba  mov     r14, [r15+8]
0x180004ebe  mov     [r15+8], rcx
0x180004ec2  test    r14, r14
0x180004ec5  jz      short loc_180004ED5
0x180004ec7  or      eax, 0FFFFFFFFh
0x180004eca  lock xadd [r14+8], eax
0x180004ed0  cmp     eax, 1
0x180004ed3  jz      short loc_180004EDF
0x180004ed5  add     r15, 10h
0x180004ed9  add     rsi, 10h
0x180004edd  jmp     short loc_180004E9C
0x180004edf  mov     rax, [r14]
0x180004ee2  mov     rcx, r14
0x180004ee5  mov     rax, [rax]
0x180004ee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004eed  mov     rcx, r14; this
0x180004ef0  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180004ef5  jmp     short loc_180004ED5
0x180004ef7  test    r12, r12
0x180004efa  jz      short loc_180004F05
0x180004efc  mov     rcx, r12; SRWLock
0x180004eff  call    cs:__imp_ReleaseSRWLockExclusive
0x180004f05  add     rsp, 58h
0x180004f09  pop     r15
0x180004f0b  pop     r14
0x180004f0d  pop     r13
0x180004f0f  pop     r12
0x180004f11  pop     rdi
0x180004f12  pop     rsi
0x180004f13  pop     rbp
0x180004f14  pop     rbx
0x180004f15  retn
0x180004f16  add     rbx, 10h
0x180004f1a  jmp     loc_180004E3E
0x180004f1f  mov     rax, [rdi+80h]
0x180004f26  mov     rcx, [rax-8]; this
0x180004f2a  test    rcx, rcx
0x180004f2d  jz      short loc_180004F34
0x180004f2f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180004f34  add     qword ptr [rdi+80h], 0FFFFFFFFFFFFFFF0h
0x180004f3c  jmp     loc_180004E3E
0x180004f41  mov     rsi, [rbx]
0x180004f44  mov     rcx, [r14]
0x180004f47  mov     rax, [rcx]
0x180004f4a  lea     rdx, [rsp+98h+var_58]
0x180004f4f  mov     rax, [rax+50h]
0x180004f53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f58  mov     r8, rax
0x180004f5b  xor     ebp, ebp
0x180004f5d  mov     rdx, [rax+8]
0x180004f61  test    rdx, rdx
0x180004f64  jz      short loc_180004F87
0x180004f66  mov     eax, [rdx+8]
0x180004f69  test    eax, eax
0x180004f6b  jz      short loc_180004F87
0x180004f6d  lea     ecx, [rax+1]
0x180004f70  lock cmpxchg [rdx+8], ecx
0x180004f75  jnz     short loc_180004F69
0x180004f77  mov     rax, [r8]
0x180004f7a  mov     rbp, [r8+8]
0x180004f7e  test    rax, rax
0x180004f81  jnz     loc_180005058
0x180004f87  xor     sil, sil
0x180004f8a  test    rbp, rbp
0x180004f8d  jz      short loc_180004F97
0x180004f8f  mov     rcx, rbp; this
0x180004f92  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180004f97  mov     rcx, [rsp+98h+var_50]; this
0x180004f9c  test    rcx, rcx
0x180004f9f  jz      short loc_180004FA6
0x180004fa1  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180004fa6  test    sil, sil
0x180004fa9  jnz     loc_180004F16
0x180004faf  add     r14, 8
0x180004fb3  jmp     loc_180004E6E
0x180004fb8  test    byte ptr [r10+1Ch], 4
0x180004fbd  jz      loc_180004E8E
0x180004fc3  mov     rax, [rbx]
0x180004fc6  mov     ecx, [rax+8Ch]
0x180004fcc  shr     ecx, 1
0x180004fce  and     ecx, 1
0x180004fd1  lea     r8, [rax+28h]
0x180004fd5  cmp     qword ptr [rax+40h], 7
0x180004fda  jbe     short loc_180004FDF
0x180004fdc  mov     r8, [r8]
0x180004fdf  lea     r9, [rdi+40h]
0x180004fe3  cmp     qword ptr [rdi+58h], 7
0x180004fe8  jbe     short loc_180004FED
0x180004fea  mov     r9, [r9]
0x180004fed  mov     edx, 17h
0x180004ff2  mov     [rsp+98h+var_68], r13d
0x180004ff7  mov     [rsp+98h+var_70], ecx
0x180004ffb  mov     qword ptr [rsp+98h+bIgnoreCase], r8
0x180005000  lea     r8, WPP_2779cad321383337b9ccea6dca676a06_Traceguids
0x180005007  mov     rcx, [r10+10h]
0x18000500b  call    WPP_SF_SSLL
0x180005010  jmp     loc_180004E8E
0x180005015  lea     r8, [rax+48h]
0x180005019  cmp     qword ptr [rax+60h], 7
0x18000501e  jbe     short loc_180005023
0x180005020  mov     r8, [r8]; lpString2
0x180005023  lea     rcx, [rsi+48h]
0x180005027  cmp     qword ptr [rsi+60h], 7
0x18000502c  jbe     short loc_180005031
0x18000502e  mov     rcx, [rcx]; lpString1
0x180005031  mov     [rsp+98h+bIgnoreCase], 1; bIgnoreCase
0x180005039  or      eax, 0FFFFFFFFh
0x18000503c  mov     r9d, eax; cchCount2
0x18000503f  mov     edx, eax; cchCount1
0x180005041  call    cs:__imp_CompareStringOrdinal
0x180005047  cmp     eax, 2
0x18000504a  jnz     loc_180004F87
0x180005050  mov     sil, 1
0x180005053  jmp     loc_180004F8A
0x180005058  cmp     rsi, rax
0x18000505b  jz      short loc_180005050
0x18000505d  jmp     short loc_180005015
```
