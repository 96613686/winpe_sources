# HandleCreatePoolRequest(TASK_CREATE_POOL_REQUEST const *,_GUID *,uint *)

- ea: `0x1400183b4`
- end: `0x1400185ca`
- name: `?HandleCreatePoolRequest@@YAHPEBUTASK_CREATE_POOL_REQUEST@@PEAU_GUID@@PEAI@Z`
- size: `534`
- prototype: `__int64 __fastcall(const struct TASK_CREATE_POOL_REQUEST *, struct _GUID *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x140017d70`

## callees

- `0x1400148c4`
- `0x140014f14`
- `0x14001593c`
- `0x14001832c`
- `0x1400183b4`
- `0x1400185d0`
- `0x14001ed86`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1400184e9`
- `KERNEL32!LocalFree` at `0x14001850e`
- `KERNEL32!LocalFree` at `0x140018532`
- `KERNEL32!LocalFree` at `0x1400184e9`
- `KERNEL32!LocalFree` at `0x14001850e`
- `KERNEL32!LocalFree` at `0x140018532`
- `KERNEL32!SetLastError` at `0x140018416`
- `KERNEL32!SetLastError` at `0x1400184cf`
- `KERNEL32!SetLastError` at `0x14001859d`
- `KERNEL32!SetLastError` at `0x140018416`
- `KERNEL32!SetLastError` at `0x1400184cf`
- `KERNEL32!SetLastError` at `0x14001859d`
- `KERNEL32!GetLastError` at `0x1400184d9`
- `KERNEL32!GetLastError` at `0x1400184fd`
- `KERNEL32!GetLastError` at `0x140018522`
- `KERNEL32!GetLastError` at `0x140018546`
- `KERNEL32!GetLastError` at `0x1400184d9`
- `KERNEL32!GetLastError` at `0x1400184fd`
- `KERNEL32!GetLastError` at `0x140018522`
- `KERNEL32!GetLastError` at `0x140018546`

## pseudocode

```c
__int64 __fastcall HandleCreatePoolRequest(
        const struct TASK_CREATE_POOL_REQUEST *a1,
        struct _GUID *a2,
        unsigned int *a3)
{
  unsigned int *v4; // r14
  struct _SU_POOL_OBJECT *v5; // rdi
  unsigned int v8; // ebx
  DWORD v9; // ecx
  __int64 v10; // rcx
  unsigned int v11; // eax
  unsigned int v12; // eax
  int v13; // r9d
  unsigned int v14; // eax
  int v15; // r9d
  DWORD LastError; // esi
  HLOCAL v17; // rax
  HLOCAL v18; // rax
  HLOCAL v19; // rax
  __int128 v20; // xmm0
  __int64 v22; // [rsp+30h] [rbp-20h] BYREF
  int v23; // [rsp+38h] [rbp-18h]
  _BYTE v24[20]; // [rsp+3Ch] [rbp-14h]
  struct _SU_POOL_OBJECT *v25; // [rsp+98h] [rbp+48h] BYREF
  unsigned int *v26; // [rsp+A0h] [rbp+50h] BYREF
  HLOCAL hMem; // [rsp+A8h] [rbp+58h] BYREF

  *a3 = -1;
  v4 = 0;
  v5 = 0;
  v26 = 0;
  *a2 = GUID_NULL;
  hMem = 0;
  v25 = 0;
  v8 = IssueProgressStringResult(32883);
  if ( v8 )
  {
    if ( *(_QWORD *)a1 < 0x218u || (v10 = *((unsigned int *)a1 + 132), *(_QWORD *)a1 != 4 * v10 + 532) )
    {
      v9 = 24;
LABEL_4:
      v8 = 0;
      SetLastError(v9);
      goto LABEL_14;
    }
    v11 = SuInitializeDriveTemplateList(v10, (const unsigned int *)a1 + 133, (struct _SP_DRIVE_INFO **)&hMem, &v26);
    v4 = v26;
    v8 = v11;
    if ( !v11 )
      goto LABEL_14;
    v12 = SuNumberOfErrors(*((_DWORD *)a1 + 132), v26);
    if ( v13 == v12 )
    {
      v9 = 15;
      goto LABEL_4;
    }
    v8 = IssueProgressStringResult(32884);
    if ( v8 )
    {
      v8 = SuCreatePoolEx(
             (const unsigned __int16 *)a1 + 8,
             &v25,
             *((_DWORD *)a1 + 132),
             (struct _SP_DRIVE_INFO *)hMem,
             v4);
      if ( v8 )
      {
        v14 = SuNumberOfErrors(*((_DWORD *)a1 + 132), v4);
        if ( v15 != v14 )
        {
          v5 = v25;
          *a3 = v14;
          *a2 = *(struct _GUID *)((char *)v5 + 40);
          goto LABEL_14;
        }
        v8 = 0;
        SetLastError(0xFu);
      }
      v5 = v25;
    }
  }
LABEL_14:
  LastError = GetLastError();
  if ( v5 )
  {
    v17 = LocalFree(v5);
    if ( v8 )
    {
      v8 = v17 == 0;
      LastError = GetLastError();
    }
  }
  if ( hMem )
  {
    v18 = LocalFree(hMem);
    if ( v8 )
    {
      v8 = v18 == 0;
      LastError = GetLastError();
    }
  }
  if ( !v4 )
  {
LABEL_23:
    if ( v8 )
      goto LABEL_26;
    goto LABEL_24;
  }
  v19 = LocalFree(v4);
  if ( v8 )
  {
    v8 = v19 == 0;
    LastError = GetLastError();
    goto LABEL_23;
  }
LABEL_24:
  if ( memcmp_0(a2, &GUID_NULL, 0x10u) )
  {
    *(_DWORD *)&v24[16] = 0;
    *(_OWORD *)v24 = 0;
    v22 = 32;
    v20 = (__int128)*a2;
    v23 = 3;
    *(_OWORD *)&v24[4] = v20;
    HandleDestroyPoolRequest((const struct TASK_DESTROY_POOL_REQUEST *)&v22);
  }
LABEL_26:
  SetLastError(LastError);
  return v8;
}

```

## disassembly

```asm
0x1400183b4  push    rbp
0x1400183b6  push    rbx
0x1400183b7  push    rsi
0x1400183b8  push    rdi
0x1400183b9  push    r12
0x1400183bb  push    r14
0x1400183bd  push    r15
0x1400183bf  mov     rbp, rsp
0x1400183c2  sub     rsp, 50h
0x1400183c6  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1400183cd  mov     rsi, rcx
0x1400183d0  mov     dword ptr [r8], 0FFFFFFFFh
0x1400183d7  xor     r14d, r14d
0x1400183da  xor     edi, edi
0x1400183dc  mov     ecx, 8073h
0x1400183e1  mov     [rbp+arg_10], r14
0x1400183e5  movdqu  xmmword ptr [rdx], xmm0
0x1400183e9  mov     r12, r8
0x1400183ec  mov     [rbp+hMem], r14
0x1400183f0  mov     r15, rdx
0x1400183f3  mov     [rbp+arg_8], rdi
0x1400183f7  call    IssueProgressStringResult
0x1400183fc  mov     ebx, eax
0x1400183fe  test    eax, eax
0x140018400  jz      loc_1400184D9
0x140018406  cmp     qword ptr [rsi], 218h
0x14001840d  jnb     short loc_140018421
0x14001840f  mov     ecx, 18h; dwErrCode
0x140018414  xor     ebx, ebx
0x140018416  call    cs:__imp_SetLastError
0x14001841c  jmp     loc_1400184D9
0x140018421  mov     ecx, [rsi+210h]; unsigned int
0x140018427  lea     rax, ds:214h[rcx*4]
0x14001842f  cmp     [rsi], rax
0x140018432  jnz     short loc_14001840F
0x140018434  lea     rdx, [rsi+214h]; unsigned int *
0x14001843b  lea     r9, [rbp+arg_10]; unsigned int **
0x14001843f  lea     r8, [rbp+hMem]; struct _SP_DRIVE_INFO **
0x140018443  call    ?SuInitializeDriveTemplateList@@YAHIPEBKPEAPEAU_SP_DRIVE_INFO@@PEAPEAK@Z; SuInitializeDriveTemplateList(uint,ulong const *,_SP_DRIVE_INFO * *,ulong * *)
0x140018448  mov     r14, [rbp+arg_10]
0x14001844c  mov     ebx, eax
0x14001844e  test    eax, eax
0x140018450  jz      loc_1400184D9
0x140018456  mov     r9d, [rsi+210h]
0x14001845d  mov     rdx, r14; unsigned int *
0x140018460  mov     ecx, r9d; unsigned int
0x140018463  call    ?SuNumberOfErrors@@YAIIPEBK@Z; SuNumberOfErrors(uint,ulong const *)
0x140018468  sub     r9d, eax
0x14001846b  cmp     r9d, 1
0x14001846f  jnb     short loc_140018478
0x140018471  mov     ecx, 0Fh
0x140018476  jmp     short loc_140018414
0x140018478  mov     ecx, 8074h
0x14001847d  call    IssueProgressStringResult
0x140018482  mov     ebx, eax
0x140018484  test    eax, eax
0x140018486  jz      short loc_1400184D9
0x140018488  mov     r9, [rbp+hMem]; struct _SP_DRIVE_INFO *
0x14001848c  lea     rcx, [rsi+10h]; unsigned __int16 *
0x140018490  mov     r8d, [rsi+210h]; unsigned int
0x140018497  lea     rdx, [rbp+arg_8]; struct _SU_POOL_OBJECT **
0x14001849b  mov     [rsp+50h+var_30], r14; unsigned int *
0x1400184a0  call    ?SuCreatePoolEx@@YAHPEBGPEAPEAU_SU_POOL_OBJECT@@IPEAU_SP_DRIVE_INFO@@PEAK@Z; SuCreatePoolEx(ushort const *,_SU_POOL_OBJECT * *,uint,_SP_DRIVE_INFO *,ulong *)
0x1400184a5  mov     ebx, eax
0x1400184a7  test    eax, eax
0x1400184a9  jz      short loc_1400184D5
0x1400184ab  mov     r9d, [rsi+210h]
0x1400184b2  mov     rdx, r14; unsigned int *
0x1400184b5  mov     ecx, r9d; unsigned int
0x1400184b8  call    ?SuNumberOfErrors@@YAIIPEBK@Z; SuNumberOfErrors(uint,ulong const *)
0x1400184bd  sub     r9d, eax
0x1400184c0  cmp     r9d, 1
0x1400184c4  jnb     loc_1400185B4
0x1400184ca  xor     ebx, ebx
0x1400184cc  lea     ecx, [rbx+0Fh]; dwErrCode
0x1400184cf  call    cs:__imp_SetLastError
0x1400184d5  mov     rdi, [rbp+arg_8]
0x1400184d9  call    cs:__imp_GetLastError
0x1400184df  mov     esi, eax
0x1400184e1  test    rdi, rdi
0x1400184e4  jz      short loc_140018505
0x1400184e6  mov     rcx, rdi; hMem
0x1400184e9  call    cs:__imp_LocalFree
0x1400184ef  xor     ecx, ecx
0x1400184f1  test    rax, rax
0x1400184f4  setz    cl
0x1400184f7  test    ebx, ebx
0x1400184f9  jz      short loc_140018505
0x1400184fb  mov     ebx, ecx
0x1400184fd  call    cs:__imp_GetLastError
0x140018503  mov     esi, eax
0x140018505  mov     rcx, [rbp+hMem]; hMem
0x140018509  test    rcx, rcx
0x14001850c  jz      short loc_14001852A
0x14001850e  call    cs:__imp_LocalFree
0x140018514  xor     ecx, ecx
0x140018516  test    rax, rax
0x140018519  setz    cl
0x14001851c  test    ebx, ebx
0x14001851e  jz      short loc_14001852A
0x140018520  mov     ebx, ecx
0x140018522  call    cs:__imp_GetLastError
0x140018528  mov     esi, eax
0x14001852a  test    r14, r14
0x14001852d  jz      short loc_14001854E
0x14001852f  mov     rcx, r14; hMem
0x140018532  call    cs:__imp_LocalFree
0x140018538  xor     ecx, ecx
0x14001853a  test    rax, rax
0x14001853d  setz    cl
0x140018540  test    ebx, ebx
0x140018542  jz      short loc_140018552
0x140018544  mov     ebx, ecx
0x140018546  call    cs:__imp_GetLastError
0x14001854c  mov     esi, eax
0x14001854e  test    ebx, ebx
0x140018550  jnz     short loc_14001859B
0x140018552  mov     r8d, 10h; Size
0x140018558  lea     rdx, GUID_NULL; Buf2
0x14001855f  mov     rcx, r15; Buf1
0x140018562  call    memcmp_0
0x140018567  test    eax, eax
0x140018569  jz      short loc_14001859B
0x14001856b  xorps   xmm0, xmm0
0x14001856e  mov     [rbp+var_4], 0
0x140018575  movdqu  [rbp+var_14], xmm0
0x14001857a  lea     rcx, [rbp+var_20]; struct TASK_DESTROY_POOL_REQUEST *
0x14001857e  mov     [rbp+var_20], 20h ; ' '
0x140018586  movups  xmm0, xmmword ptr [r15]
0x14001858a  mov     [rbp+var_18], 3
0x140018591  movdqu  [rbp+var_14+4], xmm0
0x140018596  call    ?HandleDestroyPoolRequest@@YAHPEBUTASK_DESTROY_POOL_REQUEST@@@Z; HandleDestroyPoolRequest(TASK_DESTROY_POOL_REQUEST const *)
0x14001859b  mov     ecx, esi; dwErrCode
0x14001859d  call    cs:__imp_SetLastError
0x1400185a3  mov     eax, ebx
0x1400185a5  add     rsp, 50h
0x1400185a9  pop     r15
0x1400185ab  pop     r14
0x1400185ad  pop     r12
0x1400185af  pop     rdi
0x1400185b0  pop     rsi
0x1400185b1  pop     rbx
0x1400185b2  pop     rbp
0x1400185b3  retn
0x1400185b4  mov     rdi, [rbp+arg_8]
0x1400185b8  mov     [r12], eax
0x1400185bc  movups  xmm0, xmmword ptr [rdi+28h]
0x1400185c0  movdqu  xmmword ptr [r15], xmm0
0x1400185c5  jmp     loc_1400184D9
```
