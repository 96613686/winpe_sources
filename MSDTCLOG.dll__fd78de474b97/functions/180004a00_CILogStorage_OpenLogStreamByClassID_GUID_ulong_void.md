# CILogStorage::OpenLogStreamByClassID(_GUID,ulong,void * *)

- ea: `0x180004a00`
- end: `0x180004c9f`
- name: `?OpenLogStreamByClassID@CILogStorage@@UEAAJU_GUID@@KPEAPEAX@Z`
- size: `671`
- prototype: `__int64 __fastcall(CILogStorage *__hidden this, struct _GUID *__struct_ptr, unsigned int, void **)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation`

## callees

- `0x1800012c0`
- `0x1800044c8`
- `0x180004a00`
- `0x180006248`
- `0x180008248`
- `0x18000c918`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004b91`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180004b91`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CILogStorage::OpenLogStreamByClassID(CILogStorage *this, struct _GUID *a2, int a3, void **a4)
{
  struct _STRMTBL *v7; // rdi
  unsigned int v8; // r14d
  struct _GUID v9; // xmm0
  __int64 v10; // rax
  __int64 v11; // r8
  int v12; // ecx
  unsigned __int16 v13; // dx
  unsigned __int16 v14; // r10
  __int64 result; // rax
  CLogStream *v16; // rbx
  struct _STRMTBL *v17; // rax
  unsigned int v18; // edi
  void *v19; // rcx
  __int64 v20; // rdx
  int v21; // r9d
  int v22; // r8d
  __int64 v23; // rcx
  struct _GUID v24; // [rsp+20h] [rbp-38h] BYREF
  struct _STRMTBL *v25; // [rsp+78h] [rbp+20h] BYREF

  v7 = 0;
  v25 = 0;
  if ( !a4 )
    return 2147942487LL;
  v8 = 0;
  v9 = *a2;
  v24 = *a2;
  v10 = *((_QWORD *)this + 1);
  v11 = *(_QWORD *)(v10 + 296);
  v12 = 0;
  v13 = 0;
  v14 = *(_WORD *)(*(_QWORD *)(v10 + 400) + 88LL);
  if ( v14 )
  {
    while ( !v12 )
    {
      if ( *(_QWORD *)&v24.Data1 == *(_QWORD *)v11 && *(_QWORD *)v24.Data4 == *(_QWORD *)(v11 + 8) )
      {
        v12 = 1;
        v7 = (struct _STRMTBL *)v11;
        v25 = (struct _STRMTBL *)v11;
        v8 = v13 + 1;
      }
      else
      {
        v12 = 0;
        v11 += 44;
      }
      if ( ++v13 >= v14 )
      {
        if ( v12 )
          break;
        goto LABEL_10;
      }
    }
  }
  else
  {
LABEL_10:
    v7 = 0;
    v25 = 0;
    v8 = 0;
  }
  if ( !v7 )
  {
    if ( a3 == 2 )
    {
      v24 = v9;
      result = CILogStorage::AddStream(this, &v24, &v25);
      if ( (_DWORD)result )
        return result;
      v7 = v25;
      goto LABEL_15;
    }
    return 2147942487LL;
  }
LABEL_15:
  v16 = *(CLogStream **)((char *)v7 + 20);
  if ( !v16 )
  {
    v17 = (struct _STRMTBL *)operator new(0x260u);
    v25 = v17;
    if ( v17 )
      v16 = CLogStream::CLogStream(v17, *((struct CLogMgr **)this + 1), v8);
    else
      v16 = 0;
    *(_QWORD *)((char *)v7 + 20) = v16;
    if ( !v16 )
      return 2147942414LL;
    (*(void (__fastcall **)(CLogStream *))(*(_QWORD *)v16 + 8LL))(v16);
  }
  if ( a3 == 1 )
  {
    v18 = (**(__int64 (__fastcall ***)(CLogStream *, GUID *, void **))v16)(v16, &IID_ILogRead, a4);
    if ( !v18 && *((_DWORD *)v16 + 150) == -1 && *((_DWORD *)v16 + 151) == -1 )
    {
      CLogMgr::CrashShutDown(*((CLogMgr **)this + 1));
      v19 = *(void **)(*((_QWORD *)this + 1) + 584LL);
      if ( v19 )
      {
        if ( WaitForSingleObject(v19, 0x1388u) )
          v18 = -2147467259;
      }
      v20 = *((_QWORD *)this + 1);
      *((_DWORD *)v16 + 150) = *(_DWORD *)(*(_QWORD *)(v20 + 400) + 24LL);
      *((_DWORD *)v16 + 151) = *(_DWORD *)(*(_QWORD *)(v20 + 400) + 28LL);
      *(_DWORD *)(*(_QWORD *)(v20 + 400) + 24LL) = *(_DWORD *)(*(_QWORD *)(v20 + 400) + 48LL);
      *(_DWORD *)(*(_QWORD *)(v20 + 400) + 28LL) = *(_DWORD *)(*(_QWORD *)(v20 + 400) + 52LL);
      **(_DWORD **)(v20 + 392) = *(_DWORD *)(*(_QWORD *)(v20 + 400) + 52LL);
    }
  }
  else if ( a3 == 2 )
  {
    v18 = (**(__int64 (__fastcall ***)(CLogStream *, GUID *, void **))v16)(v16, &IID_ILogWrite, a4);
    if ( !v18 )
    {
      v21 = *((_DWORD *)v16 + 150);
      if ( v21 != -1 )
      {
        v22 = *((_DWORD *)v16 + 151);
        if ( v22 != -1 )
        {
          v23 = *((_QWORD *)this + 1);
          *(_DWORD *)(*(_QWORD *)(v23 + 400) + 24LL) = v21;
          *(_DWORD *)(*(_QWORD *)(v23 + 400) + 28LL) = v22;
          **(_DWORD **)(v23 + 392) = v22;
        }
      }
    }
    *((_DWORD *)v16 + 150) = -1;
    *((_DWORD *)v16 + 151) = -1;
    CLogMgr::_StartFlushThread(*((CLogMgr **)this + 1));
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v18;
}

```

## disassembly

```asm
0x180004a00  mov     r11, rsp
0x180004a03  mov     [r11+8], rbx
0x180004a07  mov     [r11+10h], rbp
0x180004a0b  push    rsi
0x180004a0c  push    rdi
0x180004a0d  push    r12
0x180004a0f  push    r14
0x180004a11  push    r15
0x180004a13  sub     rsp, 30h
0x180004a17  mov     r15, r9
0x180004a1a  mov     ebp, r8d
0x180004a1d  mov     rsi, rcx
0x180004a20  xor     edi, edi
0x180004a22  mov     [r11+20h], rdi
0x180004a26  test    r9, r9
0x180004a29  jz      loc_180004C83
0x180004a2f  xor     r14d, r14d
0x180004a32  movups  xmm0, xmmword ptr [rdx]
0x180004a35  movdqu  xmmword ptr [rsp+58h+var_38.Data1], xmm0
0x180004a3b  mov     rax, [rcx+8]
0x180004a3f  mov     r8, [rax+128h]
0x180004a46  xor     ecx, ecx
0x180004a48  xor     edx, edx
0x180004a4a  mov     rax, [rax+190h]
0x180004a51  movzx   r10d, word ptr [rax+58h]
0x180004a56  xor     eax, eax
0x180004a58  lea     r12d, [rdi+1]
0x180004a5c  cmp     ax, r10w
0x180004a60  jnb     short loc_180004AA1
0x180004a62  mov     rax, [r11-30h]
0x180004a66  mov     r11, [r11-38h]
0x180004a6a  test    ecx, ecx
0x180004a6c  jnz     short loc_180004AAB
0x180004a6e  cmp     r11, [r8]
0x180004a71  jnz     short loc_180004A8D
0x180004a73  cmp     rax, [r8+8]
0x180004a77  jnz     short loc_180004A8D
0x180004a79  mov     ecx, r12d
0x180004a7c  mov     rdi, r8
0x180004a7f  mov     [rsp+58h+arg_18], r8
0x180004a84  movzx   r14d, dx
0x180004a88  add     r14d, r12d
0x180004a8b  jmp     short loc_180004A93
0x180004a8d  xor     ecx, ecx
0x180004a8f  add     r8, 2Ch ; ','
0x180004a93  add     dx, r12w
0x180004a97  cmp     dx, r10w
0x180004a9b  jb      short loc_180004A6A
0x180004a9d  test    ecx, ecx
0x180004a9f  jnz     short loc_180004AAB
0x180004aa1  xor     edi, edi
0x180004aa3  mov     [rsp+58h+arg_18], rdi
0x180004aa8  xor     r14d, r14d
0x180004aab  test    rdi, rdi
0x180004aae  jnz     short loc_180004ADE
0x180004ab0  cmp     ebp, 2
0x180004ab3  jnz     loc_180004C83
0x180004ab9  movdqu  xmmword ptr [rsp+58h+var_38.Data1], xmm0
0x180004abf  lea     r8, [rsp+58h+arg_18]; struct _STRMTBL **
0x180004ac4  lea     rdx, [rsp+58h+var_38]; struct _GUID
0x180004ac9  mov     rcx, rsi; this
0x180004acc  call    ?AddStream@CILogStorage@@AEAAJU_GUID@@PEAPEAU_STRMTBL@@@Z; CILogStorage::AddStream(_GUID,_STRMTBL * *)
0x180004ad1  test    eax, eax
0x180004ad3  jnz     loc_180004C88
0x180004ad9  mov     rdi, [rsp+58h+arg_18]
0x180004ade  mov     rbx, [rdi+14h]
0x180004ae2  test    rbx, rbx
0x180004ae5  jnz     short loc_180004B2D
0x180004ae7  mov     ecx, 260h; Size
0x180004aec  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004af1  mov     [rsp+58h+arg_18], rax
0x180004af6  test    rax, rax
0x180004af9  jz      short loc_180004B0F
0x180004afb  mov     r8d, r14d; unsigned int
0x180004afe  mov     rdx, [rsi+8]; struct CLogMgr *
0x180004b02  mov     rcx, rax; this
0x180004b05  call    ??0CLogStream@@QEAA@PEAVCLogMgr@@K@Z; CLogStream::CLogStream(CLogMgr *,ulong)
0x180004b0a  mov     rbx, rax
0x180004b0d  jmp     short loc_180004B11
0x180004b0f  xor     ebx, ebx
0x180004b11  mov     [rdi+14h], rbx
0x180004b15  test    rbx, rbx
0x180004b18  jz      loc_180004BF7
0x180004b1e  mov     rax, [rbx]
0x180004b21  mov     rcx, rbx
0x180004b24  mov     rax, [rax+8]
0x180004b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b2d  cmp     ebp, r12d
0x180004b30  jnz     loc_180004C01
0x180004b36  mov     rax, [rbx]
0x180004b39  mov     r8, r15
0x180004b3c  lea     rdx, IID_ILogRead
0x180004b43  mov     rcx, rbx
0x180004b46  mov     rax, [rax]
0x180004b49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b4e  mov     edi, eax
0x180004b50  test    eax, eax
0x180004b52  jnz     loc_180004C7F
0x180004b58  or      edx, 0FFFFFFFFh
0x180004b5b  cmp     [rbx+258h], edx
0x180004b61  jnz     loc_180004C7F
0x180004b67  cmp     [rbx+25Ch], edx
0x180004b6d  jnz     loc_180004C7F
0x180004b73  mov     rcx, [rsi+8]; this
0x180004b77  call    ?CrashShutDown@CLogMgr@@QEAAJXZ; CLogMgr::CrashShutDown(void)
0x180004b7c  mov     rax, [rsi+8]
0x180004b80  mov     rcx, [rax+248h]; hHandle
0x180004b87  test    rcx, rcx
0x180004b8a  jz      short loc_180004BA1
0x180004b8c  mov     edx, 1388h; dwMilliseconds
0x180004b91  call    cs:__imp_WaitForSingleObject
0x180004b97  mov     ecx, 80004005h
0x180004b9c  test    eax, eax
0x180004b9e  cmovnz  edi, ecx
0x180004ba1  mov     rdx, [rsi+8]
0x180004ba5  mov     rax, [rdx+190h]
0x180004bac  mov     ecx, [rax+18h]
0x180004baf  mov     [rbx+258h], ecx
0x180004bb5  mov     rax, [rdx+190h]
0x180004bbc  mov     ecx, [rax+1Ch]
0x180004bbf  mov     [rbx+25Ch], ecx
0x180004bc5  mov     rcx, [rdx+190h]
0x180004bcc  mov     eax, [rcx+30h]
0x180004bcf  mov     [rcx+18h], eax
0x180004bd2  mov     rcx, [rdx+190h]
0x180004bd9  mov     eax, [rcx+34h]
0x180004bdc  mov     [rcx+1Ch], eax
0x180004bdf  mov     rax, [rdx+190h]
0x180004be6  mov     rcx, [rdx+188h]
0x180004bed  mov     eax, [rax+34h]
0x180004bf0  mov     [rcx], eax
0x180004bf2  jmp     loc_180004C7F
0x180004bf7  mov     eax, 8007000Eh
0x180004bfc  jmp     loc_180004C88
0x180004c01  cmp     ebp, 2
0x180004c04  jnz     short loc_180004C7A
0x180004c06  mov     rax, [rbx]
0x180004c09  mov     r8, r15
0x180004c0c  lea     rdx, IID_ILogWrite
0x180004c13  mov     rcx, rbx
0x180004c16  mov     rax, [rax]
0x180004c19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c1e  mov     edi, eax
0x180004c20  or      edx, 0FFFFFFFFh
0x180004c23  test    eax, eax
0x180004c25  jnz     short loc_180004C63
0x180004c27  mov     r9d, [rbx+258h]
0x180004c2e  cmp     r9d, edx
0x180004c31  jz      short loc_180004C63
0x180004c33  mov     r8d, [rbx+25Ch]
0x180004c3a  cmp     r8d, edx
0x180004c3d  jz      short loc_180004C63
0x180004c3f  mov     rcx, [rsi+8]
0x180004c43  mov     rax, [rcx+190h]
0x180004c4a  mov     [rax+18h], r9d
0x180004c4e  mov     rax, [rcx+190h]
0x180004c55  mov     [rax+1Ch], r8d
0x180004c59  mov     rax, [rcx+188h]
0x180004c60  mov     [rax], r8d
0x180004c63  mov     [rbx+258h], edx
0x180004c69  mov     [rbx+25Ch], edx
0x180004c6f  mov     rcx, [rsi+8]; this
0x180004c73  call    ?_StartFlushThread@CLogMgr@@AEAAXXZ; CLogMgr::_StartFlushThread(void)
0x180004c78  jmp     short loc_180004C7F
0x180004c7a  mov     edi, 80070057h
0x180004c7f  mov     eax, edi
0x180004c81  jmp     short loc_180004C88
0x180004c83  mov     eax, 80070057h
0x180004c88  mov     rbx, [rsp+58h+arg_0]
0x180004c8d  mov     rbp, [rsp+58h+arg_8]
0x180004c92  add     rsp, 30h
0x180004c96  pop     r15
0x180004c98  pop     r14
0x180004c9a  pop     r12
0x180004c9c  pop     rdi
0x180004c9d  pop     rsi
0x180004c9e  retn
```
