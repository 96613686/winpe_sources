# CConstraintModelResourceManager::AcquireResourceHandle(_ResourceInfo *,ulong,ulong,int,unsigned __int64 *)

- ea: `0x180102afc`
- end: `0x180102d77`
- name: `?AcquireResourceHandle@CConstraintModelResourceManager@@AEAAJPEAU_ResourceInfo@@KKHPEA_K@Z`
- size: `635`
- prototype: `__int64 __fastcall(CConstraintModelResourceManager *__hidden this, struct _ResourceInfo *, unsigned int, unsigned int, int, unsigned __int64 *)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1800bab80`
- `0x180102db4`
- `0x180104860`
- `0x180104c70`

## callees

- `0x18000abd0`
- `0x1800324a0`
- `0x1800cf8c0`
- `0x1800e5ab0`
- `0x180102afc`
- `0x1801046b8`
- `0x1801058c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180102bba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180102be4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180102bba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180102be4`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180102c4f`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180102c4f`
- `RMCLIENT!RmAvailabilityCheck` at `0x180102bcb`
- `RMCLIENT!RmAvailabilityCheck` at `0x180102bcb`
- `RMCLIENT!RmGetNotification` at `0x180102c85`
- `RMCLIENT!RmGetNotification` at `0x180102c85`
- `RMCLIENT!RmReleaseResources` at `0x180102ca8`
- `RMCLIENT!RmReleaseResources` at `0x180102ca8`
- `RMCLIENT!RmAcquireResources` at `0x180102c1b`
- `RMCLIENT!RmAcquireResources` at `0x180102c1b`

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
        &WPP_664903f6d198305c70505aa11239cf7a_Traceguids,
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
0x180102afc  mov     [rsp-38h+arg_8], rbx
0x180102b01  push    rbp
0x180102b02  push    rsi
0x180102b03  push    rdi
0x180102b04  push    r12
0x180102b06  push    r13
0x180102b08  push    r14
0x180102b0a  push    r15
0x180102b0c  mov     rbp, rsp
0x180102b0f  sub     rsp, 80h
0x180102b16  mov     rax, cs:__security_cookie
0x180102b1d  xor     rax, rsp
0x180102b20  mov     [rbp+var_8], rax
0x180102b24  mov     r12, [rbp+arg_28]
0x180102b28  xor     r14d, r14d
0x180102b2b  mov     r13, rcx
0x180102b2e  mov     esi, r8d
0x180102b31  mov     rbx, rdx
0x180102b34  mov     [rbp+var_28], r14
0x180102b38  mov     [rbp+var_30], r14d
0x180102b3c  lea     eax, [r14+64h]
0x180102b40  cmp     r9d, eax
0x180102b43  lea     rcx, [r14-1]
0x180102b47  mov     r15d, eax
0x180102b4a  lea     eax, [r14+18h]
0x180102b4e  cmovbe  r15d, r9d
0x180102b52  mul     rsi
0x180102b55  cmovb   rax, rcx
0x180102b59  mov     rcx, rax; unsigned __int64
0x180102b5c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180102b61  mov     rdi, rax
0x180102b64  test    rax, rax
0x180102b67  jz      loc_180102CB0
0x180102b6d  mov     r8d, r14d
0x180102b70  test    esi, esi
0x180102b72  jz      short loc_180102BB4
0x180102b74  mov     r9d, r14d
0x180102b77  lea     r10d, [r14+64h]
0x180102b7b  imul    rcx, r9, 21Ch
0x180102b82  lea     rdx, [r9+r9*2]
0x180102b86  cmp     r15d, r10d
0x180102b89  mov     eax, [rcx+rbx]
0x180102b8c  mov     [rdi+rdx*8], eax
0x180102b8f  mov     eax, [rcx+rbx+4]
0x180102b93  mov     [rdi+rdx*8+8], rax
0x180102b98  mov     eax, r15d
0x180102b9b  cmova   eax, r10d
0x180102b9f  mov     [rdi+rdx*8+14h], r14w
0x180102ba5  inc     r8d
0x180102ba8  mov     [rdi+rdx*8+10h], eax
0x180102bac  inc     r9
0x180102baf  cmp     r8d, esi
0x180102bb2  jb      short loc_180102B7B
0x180102bb4  cmp     [rbp+arg_20], r14d
0x180102bb8  jz      short loc_180102BE0
0x180102bba  call    cs:__imp_GetCurrentProcessId
0x180102bc0  mov     r8d, r15d
0x180102bc3  mov     rdx, rdi
0x180102bc6  mov     r9d, eax
0x180102bc9  mov     ecx, esi
0x180102bcb  call    cs:__imp_RmAvailabilityCheck
0x180102bd1  mov     rcx, rdi; void *
0x180102bd4  mov     ebx, eax
0x180102bd6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180102bdb  jmp     loc_180102D4E
0x180102be0  mov     rbx, [r13+40h]
0x180102be4  call    cs:__imp_GetCurrentProcessId
0x180102bea  lea     rcx, [rbp+var_28]
0x180102bee  mov     r8d, r15d
0x180102bf1  mov     [rsp+80h+var_38], rcx
0x180102bf6  mov     r9d, eax
0x180102bf9  lea     rcx, [rbp+var_30]
0x180102bfd  mov     rdx, rdi
0x180102c00  mov     [rsp+80h+var_40], rcx
0x180102c05  mov     ecx, esi
0x180102c07  mov     [rsp+80h+var_48], r14d
0x180102c0c  mov     [rsp+80h+var_50], r14d
0x180102c11  mov     [rsp+80h+var_58], rbx
0x180102c16  mov     [rsp+80h+var_60], r13
0x180102c1b  call    cs:__imp_RmAcquireResources
0x180102c21  mov     ebx, eax
0x180102c23  test    eax, eax
0x180102c25  js      loc_180102CC0
0x180102c2b  cmp     [rbp+var_30], r14d
0x180102c2f  jz      short loc_180102C98
0x180102c31  mov     esi, 887C0079h
0x180102c36  mov     rcx, [r13+40h]
0x180102c3a  lea     rdx, [rbp+Handles]; lpHandles
0x180102c3e  xor     r8d, r8d; bWaitAll
0x180102c41  mov     [rbp+Handles], rcx
0x180102c45  mov     r9d, 3E8h; dwMilliseconds
0x180102c4b  lea     ecx, [r8+1]; nCount
0x180102c4f  call    cs:__imp_WaitForMultipleObjects
0x180102c55  test    eax, eax
0x180102c57  jnz     short loc_180102CA2
0x180102c59  mov     rcx, r13; this
0x180102c5c  call    ?ProcessRevokedResources@CConstraintModelResourceManager@@AEAAXXZ; CConstraintModelResourceManager::ProcessRevokedResources(void)
0x180102c61  xorps   xmm0, xmm0
0x180102c64  movups  [rbp+var_18], xmm0
0x180102c68  jmp     short loc_180102C7D
0x180102c6a  mov     eax, dword ptr [rbp+var_18]
0x180102c6d  test    eax, eax
0x180102c6f  jnz     short loc_180102C77
0x180102c71  lea     r14d, [rax+1]
0x180102c75  jmp     short loc_180102C7D
0x180102c77  cmp     eax, 1
0x180102c7a  cmovz   ebx, esi
0x180102c7d  mov     rcx, [rbp+var_28]
0x180102c81  lea     rdx, [rbp+var_18]
0x180102c85  call    cs:__imp_RmGetNotification
0x180102c8b  test    eax, eax
0x180102c8d  jns     short loc_180102C6A
0x180102c8f  test    ebx, ebx
0x180102c91  js      short loc_180102CA4
0x180102c93  test    r14d, r14d
0x180102c96  jz      short loc_180102C36
0x180102c98  mov     rax, [rbp+var_28]
0x180102c9c  mov     [r12], rax
0x180102ca0  jmp     short loc_180102CCA
0x180102ca2  mov     ebx, esi
0x180102ca4  mov     rcx, [rbp+var_28]
0x180102ca8  call    cs:__imp_RmReleaseResources
0x180102cae  jmp     short loc_180102CC5
0x180102cb0  cmp     [rbp+arg_20], r14d
0x180102cb4  jz      short loc_180102CC0
0x180102cb6  mov     ebx, 8007000Eh
0x180102cbb  jmp     loc_180102D4E
0x180102cc0  mov     ebx, 887C0079h
0x180102cc5  test    rdi, rdi
0x180102cc8  jz      short loc_180102CD2
0x180102cca  mov     rcx, rdi; void *
0x180102ccd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180102cd2  test    ebx, ebx
0x180102cd4  js      short loc_180102D14
0x180102cd6  mov     rcx, cs:WPP_GLOBAL_Control
0x180102cdd  lea     rax, WPP_GLOBAL_Control
0x180102ce4  cmp     rcx, rax
0x180102ce7  jz      short loc_180102D4E
0x180102ce9  test    dword ptr [rcx+1Ch], 100h
0x180102cf0  jz      short loc_180102D4E
0x180102cf2  cmp     byte ptr [rcx+19h], 4
0x180102cf6  jb      short loc_180102D4E
0x180102cf8  mov     rax, [r12]
0x180102cfc  mov     edx, 10h
0x180102d01  mov     rcx, [rcx+10h]
0x180102d05  mov     r9d, r15d
0x180102d08  mov     [rsp+80h+var_60], rax
0x180102d0d  call    WPP_SF_dI
0x180102d12  jmp     short loc_180102D4E
0x180102d14  mov     rcx, cs:WPP_GLOBAL_Control
0x180102d1b  lea     rax, WPP_GLOBAL_Control
0x180102d22  cmp     rcx, rax
0x180102d25  jz      short loc_180102D4E
0x180102d27  test    dword ptr [rcx+1Ch], 100h
0x180102d2e  jz      short loc_180102D4E
0x180102d30  cmp     byte ptr [rcx+19h], 4
0x180102d34  jb      short loc_180102D4E
0x180102d36  mov     rcx, [rcx+10h]
0x180102d3a  lea     r8, WPP_664903f6d198305c70505aa11239cf7a_Traceguids
0x180102d41  mov     edx, 11h
0x180102d46  mov     r9d, ebx
0x180102d49  call    WPP_SF_d
0x180102d4e  mov     eax, ebx
0x180102d50  mov     rcx, [rbp+var_8]
0x180102d54  xor     rcx, rsp; StackCookie
0x180102d57  call    __security_check_cookie
0x180102d5c  mov     rbx, [rsp+80h+arg_8]
0x180102d64  add     rsp, 80h
0x180102d6b  pop     r15
0x180102d6d  pop     r14
0x180102d6f  pop     r13
0x180102d71  pop     r12
0x180102d73  pop     rdi
0x180102d74  pop     rsi
0x180102d75  pop     rbp
0x180102d76  retn
```
