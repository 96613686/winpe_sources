# CConstraintModelResourceManager::AcquireResourceHandle(_ResourceInfo *,ulong,ulong,int,unsigned __int64 *)

- ea: `0x180102d8c`
- end: `0x180103007`
- name: `?AcquireResourceHandle@CConstraintModelResourceManager@@AEAAJPEAU_ResourceInfo@@KKHPEA_K@Z`
- size: `635`
- prototype: `__int64 __fastcall(CConstraintModelResourceManager *__hidden this, struct _ResourceInfo *, unsigned int, unsigned int, int, unsigned __int64 *)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800b9030`
- `0x180103044`
- `0x180104af0`
- `0x180104f00`

## callees

- `0x18000ad20`
- `0x180032600`
- `0x1800cd8d0`
- `0x1800e5330`
- `0x180102d8c`
- `0x180104948`
- `0x180105b50`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180102e4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180102e74`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180102e4a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180102e74`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180102edf`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180102edf`
- `RMCLIENT!RmReleaseResources` at `0x180102f38`
- `RMCLIENT!RmReleaseResources` at `0x180102f38`
- `RMCLIENT!RmAvailabilityCheck` at `0x180102e5b`
- `RMCLIENT!RmAvailabilityCheck` at `0x180102e5b`
- `RMCLIENT!RmAcquireResources` at `0x180102eab`
- `RMCLIENT!RmAcquireResources` at `0x180102eab`
- `RMCLIENT!RmGetNotification` at `0x180102f15`
- `RMCLIENT!RmGetNotification` at `0x180102f15`

## pseudocode

```c
__int64 __fastcall CConstraintModelResourceManager::AcquireResourceHandle(
        CConstraintModelResourceManager *this,
        struct _ResourceInfo *a2,
        unsigned int a3,
        unsigned int a4,
        int a5,
        unsigned __int64 *a6)
{
  int v6; // r14d
  unsigned int v10; // r15d
  _DWORD *v11; // rdi
  __int64 v12; // r8
  unsigned int v13; // r8d
  __int64 v14; // r9
  __int64 v15; // rdx
  DWORD CurrentProcessId; // eax
  int v17; // ebx
  __int64 v18; // rbx
  DWORD v19; // eax
  int v21; // [rsp+50h] [rbp-30h] BYREF
  unsigned __int64 v22; // [rsp+58h] [rbp-28h] BYREF
  HANDLE Handles; // [rsp+60h] [rbp-20h] BYREF
  __int128 v24; // [rsp+68h] [rbp-18h] BYREF

  v6 = 0;
  v22 = 0;
  v21 = 0;
  v10 = 100;
  if ( a4 <= 0x64 )
    v10 = a4;
  v11 = operator new(saturated_mul(a3, 0x18u));
  if ( !v11 )
  {
    if ( a5 )
      return (unsigned int)-2147024882;
LABEL_25:
    v17 = -2005139335;
    goto LABEL_26;
  }
  v13 = 0;
  if ( a3 )
  {
    v14 = 0;
    do
    {
      v15 = 3 * v14;
      v11[2 * v15] = *((_DWORD *)a2 + 135 * v14);
      *(_QWORD *)&v11[2 * v15 + 2] = *((unsigned int *)a2 + 135 * v14 + 1);
      LOWORD(v11[6 * v14 + 5]) = 0;
      ++v13;
      v11[6 * v14++ + 4] = v10;
    }
    while ( v13 < a3 );
  }
  if ( a5 )
  {
    CurrentProcessId = GetCurrentProcessId();
    v17 = RmAvailabilityCheck(a3, v11, v10, CurrentProcessId);
    operator delete(v11);
    return (unsigned int)v17;
  }
  v18 = *((_QWORD *)this + 8);
  v19 = GetCurrentProcessId();
  v17 = RmAcquireResources(a3, v11, v10, v19, this, v18, 0, 0, &v21, &v22);
  if ( v17 < 0 )
    goto LABEL_25;
  if ( v21 )
  {
    while ( 1 )
    {
      Handles = (HANDLE)*((_QWORD *)this + 8);
      if ( WaitForMultipleObjects(1u, &Handles, 0, 0x3E8u) )
        break;
      CConstraintModelResourceManager::ProcessRevokedResources(this);
      v24 = 0;
      while ( (int)RmGetNotification(v22, &v24) >= 0 )
      {
        if ( (_DWORD)v24 )
        {
          if ( (_DWORD)v24 == 1 )
            v17 = -2005139335;
        }
        else
        {
          v6 = 1;
        }
      }
      if ( v17 < 0 )
        goto LABEL_22;
      if ( v6 )
        goto LABEL_20;
    }
    v17 = -2005139335;
LABEL_22:
    RmReleaseResources(v22);
LABEL_26:
    if ( !v11 )
      goto LABEL_28;
    goto LABEL_27;
  }
LABEL_20:
  *a6 = v22;
LABEL_27:
  operator delete(v11);
LABEL_28:
  if ( v17 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        WPP_664903f6d198305c70505aa11239cf7a_Traceguids,
        (unsigned int)v17);
    }
  }
  else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_dI(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, v12, v10, *a6);
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x180102d8c  mov     [rsp-38h+arg_8], rbx
0x180102d91  push    rbp
0x180102d92  push    rsi
0x180102d93  push    rdi
0x180102d94  push    r12
0x180102d96  push    r13
0x180102d98  push    r14
0x180102d9a  push    r15
0x180102d9c  mov     rbp, rsp
0x180102d9f  sub     rsp, 80h
0x180102da6  mov     rax, cs:__security_cookie
0x180102dad  xor     rax, rsp
0x180102db0  mov     [rbp+var_8], rax
0x180102db4  mov     r12, [rbp+arg_28]
0x180102db8  xor     r14d, r14d
0x180102dbb  mov     r13, rcx
0x180102dbe  mov     esi, r8d
0x180102dc1  mov     rbx, rdx
0x180102dc4  mov     [rbp+var_28], r14
0x180102dc8  mov     [rbp+var_30], r14d
0x180102dcc  lea     eax, [r14+64h]
0x180102dd0  cmp     r9d, eax
0x180102dd3  lea     rcx, [r14-1]
0x180102dd7  mov     r15d, eax
0x180102dda  lea     eax, [r14+18h]
0x180102dde  cmovbe  r15d, r9d
0x180102de2  mul     rsi
0x180102de5  cmovb   rax, rcx
0x180102de9  mov     rcx, rax; unsigned __int64
0x180102dec  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180102df1  mov     rdi, rax
0x180102df4  test    rax, rax
0x180102df7  jz      loc_180102F40
0x180102dfd  mov     r8d, r14d
0x180102e00  test    esi, esi
0x180102e02  jz      short loc_180102E44
0x180102e04  mov     r9d, r14d
0x180102e07  lea     r10d, [r14+64h]
0x180102e0b  imul    rcx, r9, 21Ch
0x180102e12  lea     rdx, [r9+r9*2]
0x180102e16  cmp     r15d, r10d
0x180102e19  mov     eax, [rcx+rbx]
0x180102e1c  mov     [rdi+rdx*8], eax
0x180102e1f  mov     eax, [rcx+rbx+4]
0x180102e23  mov     [rdi+rdx*8+8], rax
0x180102e28  mov     eax, r15d
0x180102e2b  cmova   eax, r10d
0x180102e2f  mov     [rdi+rdx*8+14h], r14w
0x180102e35  inc     r8d
0x180102e38  mov     [rdi+rdx*8+10h], eax
0x180102e3c  inc     r9
0x180102e3f  cmp     r8d, esi
0x180102e42  jb      short loc_180102E0B
0x180102e44  cmp     [rbp+arg_20], r14d
0x180102e48  jz      short loc_180102E70
0x180102e4a  call    cs:__imp_GetCurrentProcessId
0x180102e50  mov     r8d, r15d
0x180102e53  mov     rdx, rdi
0x180102e56  mov     r9d, eax
0x180102e59  mov     ecx, esi
0x180102e5b  call    cs:__imp_RmAvailabilityCheck
0x180102e61  mov     rcx, rdi; void *
0x180102e64  mov     ebx, eax
0x180102e66  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180102e6b  jmp     loc_180102FDE
0x180102e70  mov     rbx, [r13+40h]
0x180102e74  call    cs:__imp_GetCurrentProcessId
0x180102e7a  lea     rcx, [rbp+var_28]
0x180102e7e  mov     r8d, r15d
0x180102e81  mov     [rsp+80h+var_38], rcx
0x180102e86  mov     r9d, eax
0x180102e89  lea     rcx, [rbp+var_30]
0x180102e8d  mov     rdx, rdi
0x180102e90  mov     [rsp+80h+var_40], rcx
0x180102e95  mov     ecx, esi
0x180102e97  mov     [rsp+80h+var_48], r14d
0x180102e9c  mov     [rsp+80h+var_50], r14d
0x180102ea1  mov     [rsp+80h+var_58], rbx
0x180102ea6  mov     [rsp+80h+var_60], r13
0x180102eab  call    cs:__imp_RmAcquireResources
0x180102eb1  mov     ebx, eax
0x180102eb3  test    eax, eax
0x180102eb5  js      loc_180102F50
0x180102ebb  cmp     [rbp+var_30], r14d
0x180102ebf  jz      short loc_180102F28
0x180102ec1  mov     esi, 887C0079h
0x180102ec6  mov     rcx, [r13+40h]
0x180102eca  lea     rdx, [rbp+Handles]; lpHandles
0x180102ece  xor     r8d, r8d; bWaitAll
0x180102ed1  mov     [rbp+Handles], rcx
0x180102ed5  mov     r9d, 3E8h; dwMilliseconds
0x180102edb  lea     ecx, [r8+1]; nCount
0x180102edf  call    cs:__imp_WaitForMultipleObjects
0x180102ee5  test    eax, eax
0x180102ee7  jnz     short loc_180102F32
0x180102ee9  mov     rcx, r13; this
0x180102eec  call    ?ProcessRevokedResources@CConstraintModelResourceManager@@AEAAXXZ; CConstraintModelResourceManager::ProcessRevokedResources(void)
0x180102ef1  xorps   xmm0, xmm0
0x180102ef4  movups  [rbp+var_18], xmm0
0x180102ef8  jmp     short loc_180102F0D
0x180102efa  mov     eax, dword ptr [rbp+var_18]
0x180102efd  test    eax, eax
0x180102eff  jnz     short loc_180102F07
0x180102f01  lea     r14d, [rax+1]
0x180102f05  jmp     short loc_180102F0D
0x180102f07  cmp     eax, 1
0x180102f0a  cmovz   ebx, esi
0x180102f0d  mov     rcx, [rbp+var_28]
0x180102f11  lea     rdx, [rbp+var_18]
0x180102f15  call    cs:__imp_RmGetNotification
0x180102f1b  test    eax, eax
0x180102f1d  jns     short loc_180102EFA
0x180102f1f  test    ebx, ebx
0x180102f21  js      short loc_180102F34
0x180102f23  test    r14d, r14d
0x180102f26  jz      short loc_180102EC6
0x180102f28  mov     rax, [rbp+var_28]
0x180102f2c  mov     [r12], rax
0x180102f30  jmp     short loc_180102F5A
0x180102f32  mov     ebx, esi
0x180102f34  mov     rcx, [rbp+var_28]
0x180102f38  call    cs:__imp_RmReleaseResources
0x180102f3e  jmp     short loc_180102F55
0x180102f40  cmp     [rbp+arg_20], r14d
0x180102f44  jz      short loc_180102F50
0x180102f46  mov     ebx, 8007000Eh
0x180102f4b  jmp     loc_180102FDE
0x180102f50  mov     ebx, 887C0079h
0x180102f55  test    rdi, rdi
0x180102f58  jz      short loc_180102F62
0x180102f5a  mov     rcx, rdi; void *
0x180102f5d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180102f62  test    ebx, ebx
0x180102f64  js      short loc_180102FA4
0x180102f66  mov     rcx, cs:WPP_GLOBAL_Control
0x180102f6d  lea     rax, WPP_GLOBAL_Control
0x180102f74  cmp     rcx, rax
0x180102f77  jz      short loc_180102FDE
0x180102f79  test    dword ptr [rcx+1Ch], 100h
0x180102f80  jz      short loc_180102FDE
0x180102f82  cmp     byte ptr [rcx+19h], 4
0x180102f86  jb      short loc_180102FDE
0x180102f88  mov     rax, [r12]
0x180102f8c  mov     edx, 10h
0x180102f91  mov     rcx, [rcx+10h]
0x180102f95  mov     r9d, r15d
0x180102f98  mov     [rsp+80h+var_60], rax
0x180102f9d  call    WPP_SF_dI
0x180102fa2  jmp     short loc_180102FDE
0x180102fa4  mov     rcx, cs:WPP_GLOBAL_Control
0x180102fab  lea     rax, WPP_GLOBAL_Control
0x180102fb2  cmp     rcx, rax
0x180102fb5  jz      short loc_180102FDE
0x180102fb7  test    dword ptr [rcx+1Ch], 100h
0x180102fbe  jz      short loc_180102FDE
0x180102fc0  cmp     byte ptr [rcx+19h], 4
0x180102fc4  jb      short loc_180102FDE
0x180102fc6  mov     rcx, [rcx+10h]
0x180102fca  lea     r8, WPP_664903f6d198305c70505aa11239cf7a_Traceguids
0x180102fd1  mov     edx, 11h
0x180102fd6  mov     r9d, ebx
0x180102fd9  call    WPP_SF_d
0x180102fde  mov     eax, ebx
0x180102fe0  mov     rcx, [rbp+var_8]
0x180102fe4  xor     rcx, rsp; StackCookie
0x180102fe7  call    __security_check_cookie
0x180102fec  mov     rbx, [rsp+80h+arg_8]
0x180102ff4  add     rsp, 80h
0x180102ffb  pop     r15
0x180102ffd  pop     r14
0x180102fff  pop     r13
0x180103001  pop     r12
0x180103003  pop     rdi
0x180103004  pop     rsi
0x180103005  pop     rbp
0x180103006  retn
```
