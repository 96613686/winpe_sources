# SuDeletePoolEx_GetDrives

- ea: `0x140015368`
- end: `0x14001551d`
- name: `SuDeletePoolEx_GetDrives`
- size: `437`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400152c8`

## callees

- `0x1400083dc`
- `0x140008454`
- `0x14000df58`
- `0x140014770`
- `0x140015368`
- `0x14001ed92`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140015415`
- `KERNEL32!LocalFree` at `0x1400154a8`
- `KERNEL32!LocalFree` at `0x1400154e7`
- `KERNEL32!LocalFree` at `0x140015415`
- `KERNEL32!LocalFree` at `0x1400154a8`
- `KERNEL32!LocalFree` at `0x1400154e7`
- `KERNEL32!SetLastError` at `0x14001547f`
- `KERNEL32!SetLastError` at `0x140015504`
- `KERNEL32!SetLastError` at `0x14001547f`
- `KERNEL32!SetLastError` at `0x140015504`
- `KERNEL32!GetLastError` at `0x14001539e`
- `KERNEL32!GetLastError` at `0x140015466`
- `KERNEL32!GetLastError` at `0x140015485`
- `KERNEL32!GetLastError` at `0x1400154bc`
- `KERNEL32!GetLastError` at `0x1400154d8`
- `KERNEL32!GetLastError` at `0x14001539e`
- `KERNEL32!GetLastError` at `0x140015466`
- `KERNEL32!GetLastError` at `0x140015485`
- `KERNEL32!GetLastError` at `0x1400154bc`
- `KERNEL32!GetLastError` at `0x1400154d8`
- `KERNEL32!LocalAlloc` at `0x1400153bb`
- `KERNEL32!LocalAlloc` at `0x1400153bb`

## pseudocode

```c
__int64 __fastcall SuDeletePoolEx_GetDrives(struct _SU_POOL_OBJECT *a1, unsigned int *a2, _QWORD *a3)
{
  unsigned int v4; // r14d
  char *v5; // rdi
  __int64 *FirstDrive; // r15
  unsigned int Next; // ebx
  HLOCAL v9; // rbp
  char *v10; // rbx
  HLOCAL v11; // rax
  unsigned int v12; // r8d
  int v13; // eax
  DWORD LastError; // esi
  HLOCAL v15; // rax
  unsigned int Close; // eax
  void *v18; // [rsp+20h] [rbp-58h] BYREF
  HLOCAL hMem; // [rsp+98h] [rbp+20h] BYREF

  hMem = 0;
  v4 = 0;
  v5 = 0;
  FirstDrive = (__int64 *)SuFindFirstDrive(a1, (struct _SU_DRIVE_OBJECT **)&hMem);
  if ( FirstDrive == (__int64 *)-1LL )
  {
    if ( GetLastError() != 18 )
    {
LABEL_3:
      Next = 0;
      goto LABEL_13;
    }
  }
  else
  {
    v18 = LocalAlloc(0, 0xC30u);
    v5 = (char *)v18;
    if ( !v18 )
      goto LABEL_3;
    while ( 1 )
    {
      v9 = hMem;
      if ( *((_DWORD *)hMem + 19) < 0xC30u )
      {
        Next = 0;
        SetLastError(0xDu);
        goto LABEL_13;
      }
      v10 = &v5[3120 * v4];
      memcpy_0(v10, (char *)hMem + 72, 0xC30u);
      *((_DWORD *)v10 + 1) = 3120;
      *((_DWORD *)v10 + 742) = 0;
      ++v4;
      v11 = LocalFree(v9);
      hMem = 0;
      if ( v11 )
        goto LABEL_3;
      Next = SuFindNext(FirstDrive, (struct _SU_OBJECT **)&hMem);
      if ( !Next )
        break;
      v13 = LocalReAllocEx(&v18, 3120 * (v4 + 1LL), v12);
      v5 = (char *)v18;
      Next = v13;
      if ( !v13 )
        goto LABEL_13;
    }
    if ( GetLastError() != 18 )
      goto LABEL_13;
  }
  Next = 1;
LABEL_13:
  LastError = GetLastError();
  if ( LastError == 18 )
    LastError = 2;
  if ( hMem )
  {
    v15 = LocalFree(hMem);
    if ( Next )
    {
      Next = v15 == 0;
      LastError = GetLastError();
    }
  }
  if ( FirstDrive != (__int64 *)-1LL )
  {
    Close = SuFindClose((char *)FirstDrive);
    if ( !Next )
      goto LABEL_22;
    Next = Close;
    LastError = GetLastError();
  }
  if ( Next )
  {
    *a3 = v5;
    goto LABEL_24;
  }
LABEL_22:
  LocalFree(v5);
  v4 = 0;
  *a3 = 0;
LABEL_24:
  *a2 = v4;
  SetLastError(LastError);
  return Next;
}

```

## disassembly

```asm
0x140015368  mov     rax, rsp
0x14001536b  push    rbx
0x14001536c  push    rbp
0x14001536d  push    rsi
0x14001536e  push    rdi
0x14001536f  push    r12
0x140015371  push    r13
0x140015373  push    r14
0x140015375  push    r15
0x140015377  sub     rsp, 38h
0x14001537b  xor     esi, esi
0x14001537d  mov     r13, rdx
0x140015380  lea     rdx, [rax+20h]; struct _SU_DRIVE_OBJECT **
0x140015384  mov     [rax+20h], rsi
0x140015388  mov     r14d, esi
0x14001538b  mov     edi, esi
0x14001538d  mov     r12, r8
0x140015390  call    ?SuFindFirstDrive@@YAPEAXPEAU_SU_POOL_OBJECT@@PEAPEAU_SU_DRIVE_OBJECT@@@Z; SuFindFirstDrive(_SU_POOL_OBJECT *,_SU_DRIVE_OBJECT * *)
0x140015395  mov     r15, rax
0x140015398  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14001539c  jnz     short loc_1400153B4
0x14001539e  call    cs:__imp_GetLastError
0x1400153a4  cmp     eax, 12h
0x1400153a7  jz      loc_140015471
0x1400153ad  mov     ebx, esi
0x1400153af  jmp     loc_140015485
0x1400153b4  mov     edx, 0C30h; uBytes
0x1400153b9  xor     ecx, ecx; uFlags
0x1400153bb  call    cs:__imp_LocalAlloc
0x1400153c1  mov     [rsp+78h+var_58], rax
0x1400153c6  mov     rdi, rax
0x1400153c9  test    rax, rax
0x1400153cc  jz      short loc_1400153AD
0x1400153ce  mov     rbp, [rsp+78h+hMem]
0x1400153d6  cmp     dword ptr [rbp+4Ch], 0C30h
0x1400153dd  jb      loc_140015478
0x1400153e3  mov     eax, r14d
0x1400153e6  lea     rdx, [rbp+48h]; Src
0x1400153ea  imul    rbx, rax, 0C30h
0x1400153f1  mov     r8d, 0C30h; Size
0x1400153f7  add     rbx, rdi
0x1400153fa  mov     rcx, rbx; void *
0x1400153fd  call    memcpy_0
0x140015402  mov     dword ptr [rbx+4], 0C30h
0x140015409  mov     rcx, rbp; hMem
0x14001540c  mov     [rbx+0B98h], esi
0x140015412  inc     r14d
0x140015415  call    cs:__imp_LocalFree
0x14001541b  mov     [rsp+78h+hMem], rsi
0x140015423  test    rax, rax
0x140015426  jnz     short loc_1400153AD
0x140015428  lea     rdx, [rsp+78h+hMem]; struct _SU_OBJECT **
0x140015430  mov     rcx, r15; void *
0x140015433  call    ?SuFindNext@@YAHPEAXPEAPEAU_SU_OBJECT@@@Z; SuFindNext(void *,_SU_OBJECT * *)
0x140015438  mov     ebx, eax
0x14001543a  test    eax, eax
0x14001543c  jz      short loc_140015466
0x14001543e  mov     eax, r14d
0x140015441  lea     rcx, [rsp+78h+var_58]; void **
0x140015446  inc     rax
0x140015449  imul    rdx, rax, 0C30h; unsigned __int64
0x140015450  call    ?LocalReAllocEx@@YAHPEAPEAX_KI@Z; LocalReAllocEx(void * *,unsigned __int64,uint)
0x140015455  mov     rdi, [rsp+78h+var_58]
0x14001545a  mov     ebx, eax
0x14001545c  test    eax, eax
0x14001545e  jnz     loc_1400153CE
0x140015464  jmp     short loc_140015485
0x140015466  call    cs:__imp_GetLastError
0x14001546c  cmp     eax, 12h
0x14001546f  jnz     short loc_140015485
0x140015471  mov     ebx, 1
0x140015476  jmp     short loc_140015485
0x140015478  mov     ecx, 0Dh; dwErrCode
0x14001547d  mov     ebx, esi
0x14001547f  call    cs:__imp_SetLastError
0x140015485  call    cs:__imp_GetLastError
0x14001548b  mov     rbp, [rsp+78h+hMem]
0x140015493  mov     esi, eax
0x140015495  cmp     esi, 12h
0x140015498  mov     eax, 2
0x14001549d  cmovz   esi, eax
0x1400154a0  test    rbp, rbp
0x1400154a3  jz      short loc_1400154C4
0x1400154a5  mov     rcx, rbp; hMem
0x1400154a8  call    cs:__imp_LocalFree
0x1400154ae  xor     ecx, ecx
0x1400154b0  test    rax, rax
0x1400154b3  setz    cl
0x1400154b6  test    ebx, ebx
0x1400154b8  jz      short loc_1400154C4
0x1400154ba  mov     ebx, ecx
0x1400154bc  call    cs:__imp_GetLastError
0x1400154c2  mov     esi, eax
0x1400154c4  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x1400154c8  jz      short loc_1400154E0
0x1400154ca  mov     rcx, r15; hMem
0x1400154cd  call    ?SuFindClose@@YAHPEAX@Z; SuFindClose(void *)
0x1400154d2  test    ebx, ebx
0x1400154d4  jz      short loc_1400154E4
0x1400154d6  mov     ebx, eax
0x1400154d8  call    cs:__imp_GetLastError
0x1400154de  mov     esi, eax
0x1400154e0  test    ebx, ebx
0x1400154e2  jnz     short loc_1400154FA
0x1400154e4  mov     rcx, rdi; hMem
0x1400154e7  call    cs:__imp_LocalFree
0x1400154ed  xor     r14d, r14d
0x1400154f0  mov     qword ptr [r12], 0
0x1400154f8  jmp     short loc_1400154FE
0x1400154fa  mov     [r12], rdi
0x1400154fe  mov     ecx, esi; dwErrCode
0x140015500  mov     [r13+0], r14d
0x140015504  call    cs:__imp_SetLastError
0x14001550a  mov     eax, ebx
0x14001550c  add     rsp, 38h
0x140015510  pop     r15
0x140015512  pop     r14
0x140015514  pop     r13
0x140015516  pop     r12
0x140015518  pop     rdi
0x140015519  pop     rsi
0x14001551a  pop     rbp
0x14001551b  pop     rbx
0x14001551c  retn
```
