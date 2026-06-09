# FltpAllocateInitializeNameGenerationContext

- ea: `0x18000e2e0`
- end: `0x18000e5ce`
- name: `FltpAllocateInitializeNameGenerationContext`
- size: `750`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `10`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x18000dff0`
- `0x180058640`
- `0x18005aa30`
- `0x18005b4b0`
- `0x18005b920`
- `0x18005c8e0`
- `0x18005e010`
- `0x18005e410`
- `0x180065600`
- `0x180065e90`

## callees

- `0x180009f20`
- `0x18000afe0`
- `0x18000dcb0`
- `0x18000e2e0`
- `0x180024c40`
- `0x18006b960`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x18000e30d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x18000e52e`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x18000e30d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x18000e52e`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x18000e3b7`
- `ntoskrnl!IoGetTransactionParameterBlock` at `0x18000e3b7`

## pseudocode

```c
__int64 __fastcall FltpAllocateInitializeNameGenerationContext(
        PFLT_INSTANCE **a1,
        struct _FLT_INSTANCE *a2,
        struct _FILE_OBJECT *a3,
        struct _FLT_INSTANCE *a4,
        int a5,
        struct _FLT_INSTANCE *a6,
        struct _FLT_INSTANCE *a7,
        struct _FLT_INSTANCE *a8,
        int a9,
        __int64 a10,
        int a11)
{
  PFLT_INSTANCE *v15; // rax
  PFLT_INSTANCE *v16; // rsi
  unsigned int v17; // r15d
  unsigned int v18; // esi
  PFLT_INSTANCE *v19; // rcx
  int v20; // eax
  PTXN_PARAMETER_BLOCK TransactionParameterBlock; // rax
  PFLT_INSTANCE *v22; // rcx
  struct _FLT_INSTANCE *Volume; // r8
  __int64 result; // rax
  unsigned int IoTargetFromFileObject; // edi
  PFLT_INSTANCE *v26; // rcx
  int v27; // eax
  _OWORD *v28; // rax
  _OWORD *v29; // rsi
  int v30; // eax
  int v31; // eax
  __int64 v32[9]; // [rsp+40h] [rbp-48h] BYREF

  LOBYTE(a10) = 0;
  LOBYTE(v32[0]) = 0;
  v15 = (PFLT_INSTANCE *)ExAllocateFromNPagedLookasideList(&stru_18003F440);
  v16 = v15;
  v17 = -1073741670;
  if ( v15 )
  {
    memset(v15, 0, 0x100u);
    *a1 = v16;
    v18 = 0;
  }
  else
  {
    v18 = -1073741670;
  }
  if ( (int)FltpDbgStatus(v18, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 242, 0) < 0 )
    return v18;
  v19 = *a1;
  v19[8] = (PFLT_INSTANCE)a3;
  v19[10] = a4;
  *((_DWORD *)v19 + 27) = a5;
  v19[14] = a6;
  v19[11] = a7;
  v19[12] = a8;
  *((_DWORD *)v19 + 26) = a9;
  v20 = a11;
  v19[15] = 0;
  *((_DWORD *)v19 + 10) = v20;
  TransactionParameterBlock = IoGetTransactionParameterBlock(a3);
  v22 = *a1;
  (*a1)[9] = (PFLT_INSTANCE)TransactionParameterBlock;
  if ( TransactionParameterBlock && TransactionParameterBlock->TxFsContext != 0xFFFE )
  {
    v28 = ExAllocateFromNPagedLookasideList(&stru_18003F540);
    v29 = v28;
    if ( v28 )
    {
      v17 = 0;
      *v28 = 0;
    }
    else
    {
      v29 = 0;
    }
    v30 = FltpDbgStatus(v17, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 274, 0);
    v22 = *a1;
    if ( v30 < 0 )
    {
      FltpFreeNameGenerationContext(v22);
      result = v17;
      *a1 = 0;
      return result;
    }
    *(_DWORD *)v29 = -131056;
    *((_QWORD *)v29 + 1) = v22[9]->Base.RundownRef.Count;
    v22[9] = (PFLT_INSTANCE)v29;
    *((_DWORD *)v22 + 10) |= 0x800u;
  }
  if ( a2 )
  {
    v22[2] = a2;
    Volume = (struct _FLT_INSTANCE *)a2->Volume;
    v22[1] = Volume;
    *v22 = (PFLT_INSTANCE)a2->Volume->DeviceObject;
    v22[3] = Volume;
  }
  else
  {
    *((_DWORD *)v22 + 10) |= 0x200u;
    IoTargetFromFileObject = FltpGetIoTargetFromFileObject(
                               a3,
                               (__int64)(v22 + 3),
                               (__int64)(v22 + 4),
                               (__int64)&a10,
                               (__int64)v32);
    if ( (int)FltpDbgStatus(IoTargetFromFileObject, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 353, 0) >= 0 )
    {
      v26 = *a1;
      if ( !(*a1)[3] )
      {
        v31 = *((_DWORD *)v26 + 10);
        if ( (v31 & 1) != 0 )
          *((_DWORD *)v26 + 10) = v31 & 0xFFFFFBFD | 0x400;
        else
          IoTargetFromFileObject = -1071906811;
      }
    }
    v27 = FltpDbgStatus(IoTargetFromFileObject, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 382, 0);
    v22 = *a1;
    if ( v27 < 0 )
    {
      FltpFreeNameGenerationContext(v22);
      result = IoTargetFromFileObject;
      *a1 = 0;
      return result;
    }
    if ( (_BYTE)a10 )
    {
      if ( v22[2] )
      {
        if ( LOBYTE(v32[0]) )
          *((_DWORD *)v22 + 27) |= 0x1000000u;
      }
      else
      {
        FltGetTopInstance((PFLT_VOLUME)v22[1], v22 + 2);
        v22 = *a1;
        if ( (*a1)[2] )
          *((_DWORD *)v22 + 27) |= 0x1000000u;
      }
    }
    else
    {
      *((_DWORD *)v22 + 10) |= 0x400u;
    }
  }
  if ( a3 && (a3->Flags & 0x20000) != 0 )
    *((_DWORD *)v22 + 10) |= 0x20u;
  if ( (*((_DWORD *)v22 + 27) & 0xFF00) == 0x300 )
    *((_DWORD *)v22 + 10) |= 0x400u;
  return 0;
}

```

## disassembly

```asm
0x18000e2e0  push    rbx
0x18000e2e2  push    rbp
0x18000e2e3  push    rsi
0x18000e2e4  push    rdi
0x18000e2e5  push    r14
0x18000e2e7  push    r15
0x18000e2e9  sub     rsp, 58h
0x18000e2ed  mov     r14, rcx
0x18000e2f0  mov     byte ptr [rsp+88h+arg_48], 0
0x18000e2f8  lea     rcx, stru_18003F440; Lookaside
0x18000e2ff  mov     byte ptr [rsp+88h+var_48], 0
0x18000e304  mov     rbp, r9
0x18000e307  mov     rbx, r8
0x18000e30a  mov     rdi, rdx
0x18000e30d  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x18000e314  nop     dword ptr [rax+rax+00h]
0x18000e319  mov     rsi, rax
0x18000e31c  mov     r15d, 0C000009Ah
0x18000e322  test    rax, rax
0x18000e325  jz      loc_18000E54D
0x18000e32b  xor     edx, edx; Val
0x18000e32d  mov     r8d, 100h; Size
0x18000e333  mov     rcx, rax; void *
0x18000e336  call    memset
0x18000e33b  mov     [r14], rsi
0x18000e33e  xor     esi, esi
0x18000e340  mov     r8d, 0F2h
0x18000e346  lea     rdx, aMinkernelFsFil_25; "minkernel\\fs\\filtermgr\\filter\\names"...
0x18000e34d  xor     r9d, r9d
0x18000e350  mov     ecx, esi
0x18000e352  call    FltpDbgStatus
0x18000e357  test    eax, eax
0x18000e359  js      loc_18000E555
0x18000e35f  mov     rcx, [r14]
0x18000e362  mov     eax, [rsp+88h+arg_20]
0x18000e369  mov     [rcx+40h], rbx
0x18000e36d  mov     [rcx+50h], rbp
0x18000e371  mov     [rcx+6Ch], eax
0x18000e374  mov     rax, [rsp+88h+arg_28]
0x18000e37c  mov     [rcx+70h], rax
0x18000e380  mov     rax, [rsp+88h+arg_30]
0x18000e388  mov     [rcx+58h], rax
0x18000e38c  mov     rax, [rsp+88h+arg_38]
0x18000e394  mov     [rcx+60h], rax
0x18000e398  mov     eax, [rsp+88h+arg_40]
0x18000e39f  mov     [rcx+68h], eax
0x18000e3a2  mov     eax, [rsp+88h+arg_50]
0x18000e3a9  mov     qword ptr [rcx+78h], 0
0x18000e3b1  mov     [rcx+28h], eax
0x18000e3b4  mov     rcx, rbx; FileObject
0x18000e3b7  call    cs:__imp_IoGetTransactionParameterBlock
0x18000e3be  nop     dword ptr [rax+rax+00h]
0x18000e3c3  mov     rcx, [r14]
0x18000e3c6  mov     [rcx+48h], rax
0x18000e3ca  test    rax, rax
0x18000e3cd  jnz     loc_18000E55C
0x18000e3d3  lea     r9, [rcx+18h]
0x18000e3d7  test    rdi, rdi
0x18000e3da  jz      short loc_18000E42B
0x18000e3dc  mov     [rcx+10h], rdi
0x18000e3e0  mov     r8, [rdi+40h]
0x18000e3e4  mov     [rcx+8], r8
0x18000e3e8  mov     rax, [rdi+40h]
0x18000e3ec  mov     rdx, [rax+40h]
0x18000e3f0  mov     [rcx], rdx
0x18000e3f3  mov     [r9], r8
0x18000e3f6  test    rbx, rbx
0x18000e3f9  jz      short loc_18000E408
0x18000e3fb  mov     eax, [rbx+50h]
0x18000e3fe  bt      eax, 11h
0x18000e402  jb      loc_18000E51E
0x18000e408  mov     eax, [rcx+6Ch]
0x18000e40b  and     eax, 0FF00h
0x18000e410  cmp     eax, 300h
0x18000e415  jz      loc_18000E4EF
0x18000e41b  xor     eax, eax
0x18000e41d  add     rsp, 58h
0x18000e421  pop     r15
0x18000e423  pop     r14
0x18000e425  pop     rdi
0x18000e426  pop     rsi
0x18000e427  pop     rbp
0x18000e428  pop     rbx
0x18000e429  retn
0x18000e42b  or      dword ptr [rcx+28h], 200h
0x18000e432  lea     rax, [rcx+20h]
0x18000e436  lea     r8, [rsp+88h+var_48]
0x18000e43b  mov     rdx, rcx
0x18000e43e  mov     [rsp+88h+var_50], r8; __int64
0x18000e443  lea     r8, [rsp+88h+arg_48]
0x18000e44b  mov     [rsp+88h+var_58], r8; __int64
0x18000e450  lea     r8, [rcx+8]
0x18000e454  mov     [rsp+88h+var_60], rax; __int64
0x18000e459  mov     [rsp+88h+var_68], r9; __int64
0x18000e45e  lea     r9, [rcx+10h]
0x18000e462  mov     rcx, rbx; FileObject
0x18000e465  call    FltpGetIoTargetFromFileObject
0x18000e46a  mov     r8d, 161h
0x18000e470  lea     rdx, aMinkernelFsFil_25; "minkernel\\fs\\filtermgr\\filter\\names"...
0x18000e477  xor     r9d, r9d
0x18000e47a  mov     ecx, eax
0x18000e47c  mov     edi, eax
0x18000e47e  call    FltpDbgStatus
0x18000e483  test    eax, eax
0x18000e485  js      short loc_18000E495
0x18000e487  mov     rcx, [r14]
0x18000e48a  cmp     qword ptr [rcx+18h], 0
0x18000e48f  jz      loc_18000E5A6
0x18000e495  mov     r8d, 17Eh
0x18000e49b  lea     rdx, aMinkernelFsFil_25; "minkernel\\fs\\filtermgr\\filter\\names"...
0x18000e4a2  xor     r9d, r9d
0x18000e4a5  mov     ecx, edi
0x18000e4a7  call    FltpDbgStatus
0x18000e4ac  mov     rcx, [r14]; Entry
0x18000e4af  test    eax, eax
0x18000e4b1  js      loc_18000E5BB
0x18000e4b7  cmp     byte ptr [rsp+88h+arg_48], 0
0x18000e4bf  jz      short loc_18000E512
0x18000e4c1  cmp     qword ptr [rcx+10h], 0
0x18000e4c6  lea     rdx, [rcx+10h]; Instance
0x18000e4ca  jnz     short loc_18000E4FB
0x18000e4cc  mov     rcx, [rcx+8]; Volume
0x18000e4d0  call    FltGetTopInstance
0x18000e4d5  mov     rcx, [r14]
0x18000e4d8  cmp     qword ptr [rcx+10h], 0
0x18000e4dd  jz      loc_18000E3F6
0x18000e4e3  or      dword ptr [rcx+6Ch], 1000000h
0x18000e4ea  jmp     loc_18000E3F6
0x18000e4ef  or      dword ptr [rcx+28h], 400h
0x18000e4f6  jmp     loc_18000E41B
0x18000e4fb  cmp     byte ptr [rsp+88h+var_48], 0
0x18000e500  jz      loc_18000E3F6
0x18000e506  or      dword ptr [rcx+6Ch], 1000000h
0x18000e50d  jmp     loc_18000E3F6
0x18000e512  or      dword ptr [rcx+28h], 400h
0x18000e519  jmp     loc_18000E3F6
0x18000e51e  or      dword ptr [rcx+28h], 20h
0x18000e522  jmp     loc_18000E408
0x18000e527  lea     rcx, stru_18003F540; Lookaside
0x18000e52e  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x18000e535  nop     dword ptr [rax+rax+00h]
0x18000e53a  mov     rsi, rax
0x18000e53d  test    rax, rax
0x18000e540  jz      short loc_18000E56D
0x18000e542  xorps   xmm0, xmm0
0x18000e545  xor     r15d, r15d
0x18000e548  movups  xmmword ptr [rax], xmm0
0x18000e54b  jmp     short loc_18000E56F
0x18000e54d  mov     esi, r15d
0x18000e550  jmp     loc_18000E340
0x18000e555  mov     eax, esi
0x18000e557  jmp     loc_18000E41D
0x18000e55c  mov     ebp, 0FFFEh
0x18000e561  cmp     [rax+2], bp
0x18000e565  jz      loc_18000E3D3
0x18000e56b  jmp     short loc_18000E527
0x18000e56d  xor     esi, esi
0x18000e56f  mov     r8d, 112h
0x18000e575  lea     rdx, aMinkernelFsFil_25; "minkernel\\fs\\filtermgr\\filter\\names"...
0x18000e57c  xor     r9d, r9d
0x18000e57f  mov     ecx, r15d
0x18000e582  call    FltpDbgStatus
0x18000e587  mov     rcx, [r14]; Entry
0x18000e58a  test    eax, eax
0x18000e58c  jns     loc_180025B46
0x18000e592  call    FltpFreeNameGenerationContext
0x18000e597  mov     eax, r15d
0x18000e59a  mov     qword ptr [r14], 0
0x18000e5a1  jmp     loc_18000E41D
0x18000e5a6  mov     eax, [rcx+28h]
0x18000e5a9  test    al, 1
0x18000e5ab  jnz     loc_180025B68
0x18000e5b1  mov     edi, 0C01C0005h
0x18000e5b6  jmp     loc_18000E495
0x18000e5bb  call    FltpFreeNameGenerationContext
0x18000e5c0  mov     eax, edi
0x18000e5c2  mov     qword ptr [r14], 0
0x18000e5c9  jmp     loc_18000E41D
0x180025b46  mov     dword ptr [rsi], 0FFFE0010h
0x180025b4c  mov     rax, [rcx+48h]
0x180025b50  mov     rdx, [rax+8]
0x180025b54  mov     [rsi+8], rdx
0x180025b58  mov     [rcx+48h], rsi
0x180025b5c  or      dword ptr [rcx+28h], 800h
0x180025b63  jmp     loc_18000E3D3
0x180025b68  and     eax, 0FFFFFFFDh
0x180025b6b  bts     eax, 0Ah
0x180025b6f  mov     [rcx+28h], eax
0x180025b72  jmp     loc_18000E495
```
