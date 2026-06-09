# Windows::UI::Composition::CompositorCommon::RegisterBatchObject(Windows::UI::Composition::CompositionBatchTypes,Windows::UI::Composition::BatchMember *)

- ea: `0x1800343d8`
- end: `0x180034581`
- name: `?RegisterBatchObject@CompositorCommon@Composition@UI@Windows@@QEAAXW4CompositionBatchTypes@234@PEAUBatchMember@234@@Z`
- size: `425`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002a700`

## callees

- `0x1800343d8`
- `0x1800348d0`
- `0x18009f34c`
- `0x1800ea11c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034410`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003445c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034472`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034528`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034410`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003445c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034472`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034528`

## pseudocode

```c
unsigned __int64 __fastcall Windows::UI::Composition::CompositorCommon::RegisterBatchObject(
        __int64 a1,
        int a2,
        __int64 *a3)
{
  int v5; // edx
  int v6; // edx
  __int64 v7; // rbx
  DWORD CurrentThreadId; // eax
  DWORD v9; // ecx
  __int64 v10; // rdi
  __int64 i; // rax
  int v12; // ebx
  struct Windows::UI::Composition::CompositionBatch *v13; // rsi
  unsigned int v14; // ebx
  DWORD v15; // eax
  __int64 v16; // rcx
  unsigned __int64 result; // rax
  DWORD v18; // ebp
  _DWORD *v19; // rax
  __int64 v20; // r8
  __int64 j; // rcx
  struct Windows::UI::Composition::CompositionBatch *v22; // [rsp+20h] [rbp-28h] BYREF
  struct Windows::UI::Composition::BatchSet *v23; // [rsp+68h] [rbp+20h] BYREF

  v5 = a2 - 1;
  if ( v5 )
  {
    v6 = v5 - 1;
    if ( v6 )
    {
      if ( v6 != 3 )
        goto LABEL_37;
      v7 = 664;
    }
    else
    {
      v7 = 736;
    }
  }
  else
  {
    v7 = 592;
  }
  CurrentThreadId = GetCurrentThreadId();
  v9 = CurrentThreadId;
  if ( *a3 || a3[1] )
LABEL_37:
    Microsoft::WRL2::FailFast::Do();
  v10 = v7 + a1;
  if ( CurrentThreadId == *(_DWORD *)(v10 + 64) )
  {
    *a3 = *(_QWORD *)(v10 + 16) | 1LL;
    *(_QWORD *)(v10 + 16) = a3;
  }
  for ( i = *(_QWORD *)(v10 + 32); i; i = *(_QWORD *)(i + 208) )
  {
    if ( *(_DWORD *)(i + 152) == v9 )
      ++*(_DWORD *)(i + 156);
  }
  v12 = *(_DWORD *)(v10 + 64);
  v13 = 0;
  v22 = 0;
  v23 = 0;
  if ( GetCurrentThreadId() != v12 )
  {
    Windows::UI::Composition::BatchController::CreateBatchSet(
      (Windows::UI::Composition::BatchController *)v10,
      &v23,
      &v22);
    result = (unsigned __int64)v23;
    v13 = v22;
    goto LABEL_16;
  }
  if ( !*(_QWORD *)(v10 + 8) )
  {
    *(_QWORD *)(v10 + 8) = 0;
    v14 = 0;
    v15 = GetCurrentThreadId();
    v16 = *(_QWORD *)(v10 + 32);
    if ( v16 )
    {
      do
      {
        if ( *(_DWORD *)(v16 + 152) == v15 )
        {
          if ( !v13 )
            v13 = (struct Windows::UI::Composition::CompositionBatch *)v16;
          ++v14;
        }
        v16 = *(_QWORD *)(v16 + 208);
      }
      while ( v16 );
      if ( v14 > 1 )
      {
        *(_QWORD *)(v10 + 8) = 0;
        v18 = GetCurrentThreadId();
        v19 = DefaultHeap::Alloc(8LL * (v14 - 1) + 16);
        *(_QWORD *)(v10 + 8) = v19;
        if ( v19 )
        {
          *v19 = 1;
          v20 = 0;
          v19[1] = v14;
          for ( j = *(_QWORD *)(v10 + 32); j; j = *(_QWORD *)(j + 208) )
          {
            if ( *(_DWORD *)(j + 152) == v18 )
            {
              *(_QWORD *)&v19[2 * v20 + 2] = j;
              v20 = (unsigned int)(v20 + 1);
            }
          }
          goto LABEL_14;
        }
        goto LABEL_37;
      }
    }
  }
LABEL_14:
  result = *(_QWORD *)(v10 + 8);
  if ( !result )
  {
LABEL_17:
    a3[1] = (__int64)v13;
    return result;
  }
  ++*(_DWORD *)result;
LABEL_16:
  if ( !result )
    goto LABEL_17;
  result |= 1u;
  a3[1] = result;
  return result;
}

```

## disassembly

```asm
0x1800343d8  mov     [rsp+arg_0], rbx
0x1800343dd  mov     [rsp+arg_8], rbp
0x1800343e2  push    rsi
0x1800343e3  push    rdi
0x1800343e4  push    r14
0x1800343e6  sub     rsp, 30h
0x1800343ea  mov     r14, r8
0x1800343ed  mov     rdi, rcx
0x1800343f0  sub     edx, 1
0x1800343f3  jz      loc_1800344A8
0x1800343f9  sub     edx, 1
0x1800343fc  jz      loc_1800344D6
0x180034402  cmp     edx, 3
0x180034405  jnz     loc_18003457B
0x18003440b  mov     ebx, 298h
0x180034410  call    cs:__imp_GetCurrentThreadId
0x180034416  cmp     qword ptr [r14], 0
0x18003441a  mov     ecx, eax
0x18003441c  jnz     loc_18003457B
0x180034422  cmp     qword ptr [r14+8], 0
0x180034427  jnz     loc_18003457B
0x18003442d  add     rdi, rbx
0x180034430  cmp     eax, [rdi+40h]
0x180034433  jnz     short loc_180034444
0x180034435  mov     rax, [rdi+10h]
0x180034439  or      rax, 1
0x18003443d  mov     [r14], rax
0x180034440  mov     [rdi+10h], r14
0x180034444  mov     rax, [rdi+20h]
0x180034448  test    rax, rax
0x18003444b  jnz     short loc_1800344B2
0x18003444d  mov     ebx, [rdi+40h]
0x180034450  xor     esi, esi
0x180034452  mov     [rsp+48h+var_28], rsi
0x180034457  mov     [rsp+48h+arg_18], rax
0x18003445c  call    cs:__imp_GetCurrentThreadId
0x180034462  cmp     eax, ebx
0x180034464  jnz     short loc_1800344E0
0x180034466  cmp     [rdi+8], rsi
0x18003446a  jnz     short loc_180034481
0x18003446c  mov     [rdi+8], rsi
0x180034470  xor     ebx, ebx
0x180034472  call    cs:__imp_GetCurrentThreadId
0x180034478  mov     rcx, [rdi+20h]
0x18003447c  test    rcx, rcx
0x18003447f  jnz     short loc_1800344FE
0x180034481  mov     rax, [rdi+8]
0x180034485  test    rax, rax
0x180034488  jz      short loc_180034491
0x18003448a  inc     dword ptr [rax]
0x18003448c  test    rax, rax
0x18003448f  jnz     short loc_1800344CC
0x180034491  mov     [r14+8], rsi
0x180034495  mov     rbx, [rsp+48h+arg_0]
0x18003449a  mov     rbp, [rsp+48h+arg_8]
0x18003449f  add     rsp, 30h
0x1800344a3  pop     r14
0x1800344a5  pop     rdi
0x1800344a6  pop     rsi
0x1800344a7  retn
0x1800344a8  mov     ebx, 250h
0x1800344ad  jmp     loc_180034410
0x1800344b2  cmp     [rax+98h], ecx
0x1800344b8  jnz     short loc_1800344C0
0x1800344ba  inc     dword ptr [rax+9Ch]
0x1800344c0  mov     rax, [rax+0D0h]
0x1800344c7  jmp     loc_180034448
0x1800344cc  or      rax, 1
0x1800344d0  mov     [r14+8], rax
0x1800344d4  jmp     short loc_180034495
0x1800344d6  mov     ebx, 2E0h
0x1800344db  jmp     loc_180034410
0x1800344e0  lea     r8, [rsp+48h+var_28]; struct Windows::UI::Composition::CompositionBatch **
0x1800344e5  mov     rcx, rdi; this
0x1800344e8  lea     rdx, [rsp+48h+arg_18]; struct Windows::UI::Composition::BatchSet **
0x1800344ed  call    ?CreateBatchSet@BatchController@Composition@UI@Windows@@AEAAXPEAPEAUBatchSet@234@PEAPEAVCompositionBatch@234@@Z; Windows::UI::Composition::BatchController::CreateBatchSet(Windows::UI::Composition::BatchSet * *,Windows::UI::Composition::CompositionBatch * *)
0x1800344f2  mov     rax, [rsp+48h+arg_18]
0x1800344f7  mov     rsi, [rsp+48h+var_28]
0x1800344fc  jmp     short loc_18003448C
0x1800344fe  cmp     [rcx+98h], eax
0x180034504  jnz     short loc_18003450F
0x180034506  test    rsi, rsi
0x180034509  cmovz   rsi, rcx
0x18003450d  inc     ebx
0x18003450f  mov     rcx, [rcx+0D0h]
0x180034516  test    rcx, rcx
0x180034519  jnz     short loc_1800344FE
0x18003451b  cmp     ebx, 1
0x18003451e  jbe     loc_180034481
0x180034524  mov     [rdi+8], rcx
0x180034528  call    cs:__imp_GetCurrentThreadId
0x18003452e  lea     ecx, [rbx-1]
0x180034531  mov     ebp, eax
0x180034533  lea     rcx, ds:10h[rcx*8]; unsigned __int64
0x18003453b  call    ?Alloc@DefaultHeap@@SAPEAX_K@Z; DefaultHeap::Alloc(unsigned __int64)
0x180034540  mov     [rdi+8], rax
0x180034544  test    rax, rax
0x180034547  jz      short loc_18003457B
0x180034549  mov     dword ptr [rax], 1
0x18003454f  xor     r8d, r8d
0x180034552  mov     [rax+4], ebx
0x180034555  mov     rcx, [rdi+20h]
0x180034559  test    rcx, rcx
0x18003455c  jz      loc_180034481
0x180034562  cmp     [rcx+98h], ebp
0x180034568  jnz     short loc_180034572
0x18003456a  mov     [rax+r8*8+8], rcx
0x18003456f  inc     r8d
0x180034572  mov     rcx, [rcx+0D0h]
0x180034579  jmp     short loc_180034559
0x18003457b  call    ?Do@FailFast@WRL2@Microsoft@@SAXXZ; Microsoft::WRL2::FailFast::Do(void)
```
