# CAudioTimeCompression::ProcessSample(IMediaSample *,double)

- ea: `0x18004f800`
- end: `0x18004fad9`
- name: `?ProcessSample@CAudioTimeCompression@@QEAAJPEAUIMediaSample@@N@Z`
- size: `729`
- prototype: `__int64 __fastcall(CAudioTimeCompression *__hidden this, struct IMediaSample *, double)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000b690`

## callees

- `0x18004f4c0`
- `0x18004f800`
- `0x180088708`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f92f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f9a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fab6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f92f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004f9a5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004fab6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f83b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f8c9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f83b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004f8c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAudioTimeCompression::ProcessSample(
        CAudioTimeCompression *this,
        struct IMediaSample *a2,
        double a3)
{
  struct _RTL_CRITICAL_SECTION *v5; // rbp
  int v6; // ebx
  int v7; // r15d
  int v8; // eax
  int v9; // ebx
  __int64 v10; // rax
  __int64 v11; // rax
  int v12; // ecx
  __int64 v13; // rcx
  int v14; // ebx
  int v15; // r14d
  __int64 v16; // r8
  const void *v17; // rdx
  unsigned __int8 *v19; // [rsp+80h] [rbp+8h] BYREF
  __int64 v20; // [rsp+88h] [rbp+10h] BYREF
  __int64 v21; // [rsp+98h] [rbp+20h] BYREF

  v21 = 0;
  v20 = 0;
  v19 = 0;
  v5 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 224);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 224));
  if ( !a2 )
    goto LABEL_23;
  v6 = ((__int64 (__fastcall *)(struct IMediaSample *, unsigned __int8 **))a2->lpVtbl->GetPointer)(a2, &v19);
  if ( v6 < 0 || !v19 )
    goto LABEL_40;
  v7 = ((__int64 (__fastcall *)(struct IMediaSample *))a2->lpVtbl->GetSize)(a2);
  if ( !v7
    || (v8 = ((__int64 (__fastcall *)(struct IMediaSample *))a2->lpVtbl->GetActualDataLength)(a2), (v9 = v8) == 0)
    || v8 > v7 )
  {
LABEL_39:
    v6 = -2147467259;
    goto LABEL_40;
  }
  if ( a3 != *((double *)this + 3) )
  {
    EnterCriticalSection(v5);
    if ( a3 < 0.501 || a3 > 2.0 )
    {
      LeaveCriticalSection(v5);
      goto LABEL_23;
    }
    if ( a3 != *((double *)this + 3) )
    {
      v10 = *((_QWORD *)this + 10);
      if ( v10 )
      {
        *(_DWORD *)(v10 + 8) = 0;
        *(_QWORD *)v10 = 0;
      }
      v11 = *((_QWORD *)this + 11);
      if ( v11 )
      {
        *(_DWORD *)(v11 + 8) = 0;
        *(_QWORD *)v11 = 0;
      }
      *((_QWORD *)this + 12) = 0;
      *((_QWORD *)this + 13) = 0;
      *((_QWORD *)this + 27) = 0;
      *((double *)this + 3) = a3;
    }
    LeaveCriticalSection(v5);
  }
  if ( v9 < 0 )
  {
LABEL_23:
    v6 = -2147024809;
    goto LABEL_40;
  }
  v12 = *((unsigned __int16 *)this + 8) * (*((_DWORD *)this + 13) - *((_DWORD *)this + 14));
  if ( v12 * ((int)((double)v9 / *((double *)this + 3)) / v12 + 2) > v7 )
    goto LABEL_39;
  v6 = CAudioTimeCompression::ProcessInput(this, v9, v19);
  if ( v6 >= 0 )
  {
    if ( v19 )
    {
      v13 = *((_QWORD *)this + 11);
      if ( v13 && (v14 = *((_DWORD *)this + 26) - *((_DWORD *)this + 24), v14 >= 0) )
      {
        if ( v14 )
        {
          if ( v14 > v7 / *((unsigned __int16 *)this + 8) )
            v14 = v7 / *((unsigned __int16 *)this + 8);
          v15 = v14 * *((unsigned __int16 *)this + 8);
          v16 = *((_QWORD *)this + 12) - *(_QWORD *)v13;
          if ( v16 < 0 || v16 >= *(int *)(v13 + 8) )
            v17 = 0;
          else
            v17 = (const void *)(*(_QWORD *)(v13 + 24) + v16 * *(int *)(v13 + 12));
          memmove_0(v19, v17, v15);
          *((_QWORD *)this + 12) += v14;
        }
        else
        {
          v15 = 0;
        }
        v6 = ((__int64 (__fastcall *)(struct IMediaSample *, _QWORD))a2->lpVtbl->SetActualDataLength)(
               a2,
               (unsigned int)v15);
        if ( v6 >= 0 )
        {
          v6 = ((__int64 (__fastcall *)(struct IMediaSample *, __int64 *, __int64 *))a2->lpVtbl->GetTime)(
                 a2,
                 &v21,
                 &v20);
          if ( !v6 )
          {
            v20 = v21 + 10000000LL * v15 / *((unsigned int *)this + 3);
            v6 = ((__int64 (__fastcall *)(struct IMediaSample *, __int64 *, __int64 *))a2->lpVtbl->SetTime)(
                   a2,
                   &v21,
                   &v20);
          }
        }
      }
      else
      {
        v6 = -2147418113;
      }
    }
    else
    {
      v6 = -2147024882;
    }
  }
LABEL_40:
  LeaveCriticalSection(v5);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18004f800  mov     rax, rsp
0x18004f803  push    rbx
0x18004f804  push    rbp
0x18004f805  push    rsi
0x18004f806  push    rdi
0x18004f807  push    r12
0x18004f809  push    r14
0x18004f80b  push    r15
0x18004f80d  sub     rsp, 40h
0x18004f811  movaps  xmmword ptr [rax-48h], xmm6
0x18004f815  movaps  xmm6, xmm2
0x18004f818  mov     rsi, rdx
0x18004f81b  mov     rdi, rcx
0x18004f81e  xor     r12d, r12d
0x18004f821  mov     [rax+20h], r12
0x18004f825  mov     [rax+10h], r12
0x18004f829  mov     [rax+8], r12
0x18004f82d  lea     rbp, [rcx+0E0h]
0x18004f834  mov     [rax-58h], rbp
0x18004f838  mov     rcx, rbp; lpCriticalSection
0x18004f83b  call    cs:__imp_EnterCriticalSection
0x18004f842  nop     dword ptr [rax+rax+00h]
0x18004f847  nop
0x18004f848  test    rsi, rsi
0x18004f84b  jz      loc_18004F9B1
0x18004f851  mov     rax, [rsi]
0x18004f854  lea     rdx, [rsp+78h+arg_0]
0x18004f85c  mov     rcx, rsi
0x18004f85f  mov     rax, [rax+18h]
0x18004f863  call    cs:__guard_dispatch_icall_fptr
0x18004f869  mov     ebx, eax
0x18004f86b  test    eax, eax
0x18004f86d  js      loc_18004FAB3
0x18004f873  cmp     [rsp+78h+arg_0], r12
0x18004f87b  jz      loc_18004FAB3
0x18004f881  mov     rax, [rsi]
0x18004f884  mov     rcx, rsi
0x18004f887  mov     rax, [rax+20h]
0x18004f88b  call    cs:__guard_dispatch_icall_fptr
0x18004f891  mov     r15d, eax
0x18004f894  test    eax, eax
0x18004f896  jz      loc_18004FAAE
0x18004f89c  mov     rax, [rsi]
0x18004f89f  mov     rcx, rsi
0x18004f8a2  mov     rax, [rax+58h]
0x18004f8a6  call    cs:__guard_dispatch_icall_fptr
0x18004f8ac  mov     ebx, eax
0x18004f8ae  test    eax, eax
0x18004f8b0  jz      loc_18004FAAE
0x18004f8b6  cmp     eax, r15d
0x18004f8b9  jg      loc_18004FAAE
0x18004f8bf  ucomisd xmm6, qword ptr [rdi+18h]
0x18004f8c4  jz      short loc_18004F93B
0x18004f8c6  mov     rcx, rbp; lpCriticalSection
0x18004f8c9  call    cs:__imp_EnterCriticalSection
0x18004f8d0  nop     dword ptr [rax+rax+00h]
0x18004f8d5  comisd  xmm6, cs:__real@3fe0083126e978d5
0x18004f8dd  jb      loc_18004F9A2
0x18004f8e3  comisd  xmm6, cs:__real@4000000000000000
0x18004f8eb  ja      loc_18004F9A2
0x18004f8f1  ucomisd xmm6, qword ptr [rdi+18h]
0x18004f8f6  jz      short loc_18004F92C
0x18004f8f8  mov     rax, [rdi+50h]
0x18004f8fc  test    rax, rax
0x18004f8ff  jz      short loc_18004F908
0x18004f901  mov     [rax+8], r12d
0x18004f905  mov     [rax], r12
0x18004f908  mov     rax, [rdi+58h]
0x18004f90c  test    rax, rax
0x18004f90f  jz      short loc_18004F918
0x18004f911  mov     [rax+8], r12d
0x18004f915  mov     [rax], r12
0x18004f918  mov     [rdi+60h], r12
0x18004f91c  mov     [rdi+68h], r12
0x18004f920  mov     [rdi+0D8h], r12
0x18004f927  movsd   qword ptr [rdi+18h], xmm6
0x18004f92c  mov     rcx, rbp; lpCriticalSection
0x18004f92f  call    cs:__imp_LeaveCriticalSection
0x18004f936  nop     dword ptr [rax+rax+00h]
0x18004f93b  test    ebx, ebx
0x18004f93d  js      short loc_18004F9B1
0x18004f93f  mov     ecx, [rdi+34h]
0x18004f942  sub     ecx, [rdi+38h]
0x18004f945  movzx   eax, word ptr [rdi+10h]
0x18004f949  imul    ecx, eax
0x18004f94c  movd    xmm0, ebx
0x18004f950  cvtdq2pd xmm0, xmm0
0x18004f954  divsd   xmm0, qword ptr [rdi+18h]
0x18004f959  cvttsd2si eax, xmm0
0x18004f95d  cdq
0x18004f95e  idiv    ecx
0x18004f960  add     eax, 2
0x18004f963  imul    eax, ecx
0x18004f966  cmp     eax, r15d
0x18004f969  jg      loc_18004FAAE
0x18004f96f  mov     r8, [rsp+78h+arg_0]; unsigned __int8 *
0x18004f977  mov     edx, ebx; int
0x18004f979  mov     rcx, rdi; this
0x18004f97c  call    ?ProcessInput@CAudioTimeCompression@@QEAAJHPEAE@Z; CAudioTimeCompression::ProcessInput(int,uchar *)
0x18004f981  mov     ebx, eax
0x18004f983  test    eax, eax
0x18004f985  js      loc_18004FAB3
0x18004f98b  mov     r9, [rsp+78h+arg_0]
0x18004f993  test    r9, r9
0x18004f996  jnz     short loc_18004F9BB
0x18004f998  mov     ebx, 8007000Eh
0x18004f99d  jmp     loc_18004FAB3
0x18004f9a2  mov     rcx, rbp; lpCriticalSection
0x18004f9a5  call    cs:__imp_LeaveCriticalSection
0x18004f9ac  nop     dword ptr [rax+rax+00h]
0x18004f9b1  mov     ebx, 80070057h
0x18004f9b6  jmp     loc_18004FAB3
0x18004f9bb  mov     rcx, [rdi+58h]
0x18004f9bf  test    rcx, rcx
0x18004f9c2  jz      short loc_18004F9CC
0x18004f9c4  mov     ebx, [rdi+68h]
0x18004f9c7  sub     ebx, [rdi+60h]
0x18004f9ca  jns     short loc_18004F9D6
0x18004f9cc  mov     ebx, 8000FFFFh
0x18004f9d1  jmp     loc_18004FAB3
0x18004f9d6  test    ebx, ebx
0x18004f9d8  jnz     short loc_18004F9DF
0x18004f9da  mov     r14d, r12d
0x18004f9dd  jmp     short loc_18004FA29
0x18004f9df  movzx   r14d, word ptr [rdi+10h]
0x18004f9e4  mov     eax, r15d
0x18004f9e7  cdq
0x18004f9e8  idiv    r14d
0x18004f9eb  cmp     ebx, eax
0x18004f9ed  cmovg   ebx, eax
0x18004f9f0  imul    r14d, ebx
0x18004f9f4  mov     r8, [rdi+60h]
0x18004f9f8  sub     r8, [rcx]
0x18004f9fb  js      short loc_18004FA14
0x18004f9fd  movsxd  rax, dword ptr [rcx+8]
0x18004fa01  cmp     r8, rax
0x18004fa04  jge     short loc_18004FA14
0x18004fa06  movsxd  rdx, dword ptr [rcx+0Ch]
0x18004fa0a  imul    rdx, r8
0x18004fa0e  add     rdx, [rcx+18h]
0x18004fa12  jmp     short loc_18004FA17
0x18004fa14  mov     rdx, r12; Src
0x18004fa17  movsxd  r8, r14d; Size
0x18004fa1a  mov     rcx, r9; void *
0x18004fa1d  call    memmove_0
0x18004fa22  movsxd  rax, ebx
0x18004fa25  add     [rdi+60h], rax
0x18004fa29  mov     rax, [rsi]
0x18004fa2c  mov     edx, r14d
0x18004fa2f  mov     rcx, rsi
0x18004fa32  mov     rax, [rax+60h]
0x18004fa36  call    cs:__guard_dispatch_icall_fptr
0x18004fa3c  mov     ebx, eax
0x18004fa3e  test    eax, eax
0x18004fa40  js      short loc_18004FAB3
0x18004fa42  mov     rax, [rsi]
0x18004fa45  lea     r8, [rsp+78h+arg_8]
0x18004fa4d  lea     rdx, [rsp+78h+arg_18]
0x18004fa55  mov     rcx, rsi
0x18004fa58  mov     rax, [rax+28h]
0x18004fa5c  call    cs:__guard_dispatch_icall_fptr
0x18004fa62  mov     ebx, eax
0x18004fa64  test    eax, eax
0x18004fa66  jnz     short loc_18004FAB3
0x18004fa68  movsxd  rax, r14d
0x18004fa6b  imul    rax, 989680h
0x18004fa72  mov     ecx, [rdi+0Ch]
0x18004fa75  cqo
0x18004fa77  idiv    rcx
0x18004fa7a  add     rax, [rsp+78h+arg_18]
0x18004fa82  mov     [rsp+78h+arg_8], rax
0x18004fa8a  mov     rax, [rsi]
0x18004fa8d  lea     r8, [rsp+78h+arg_8]
0x18004fa95  lea     rdx, [rsp+78h+arg_18]
0x18004fa9d  mov     rcx, rsi
0x18004faa0  mov     rax, [rax+30h]
0x18004faa4  call    cs:__guard_dispatch_icall_fptr
0x18004faaa  mov     ebx, eax
0x18004faac  jmp     short loc_18004FAB3
0x18004faae  mov     ebx, 80004005h
0x18004fab3  mov     rcx, rbp; lpCriticalSection
0x18004fab6  call    cs:__imp_LeaveCriticalSection
0x18004fabd  nop     dword ptr [rax+rax+00h]
0x18004fac2  mov     eax, ebx
0x18004fac4  movaps  xmm6, [rsp+78h+var_48]
0x18004fac9  add     rsp, 40h
0x18004facd  pop     r15
0x18004facf  pop     r14
0x18004fad1  pop     r12
0x18004fad3  pop     rdi
0x18004fad4  pop     rsi
0x18004fad5  pop     rbp
0x18004fad6  pop     rbx
0x18004fad7  retn
```
