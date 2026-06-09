# SuCreatePool_CleanupPool

- ea: `0x1400151d4`
- end: `0x1400152bf`
- name: `SuCreatePool_CleanupPool`
- size: `235`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path`

## callers

- `0x140014f14`

## callees

- `0x1400151d4`
- `0x1400152c8`
- `0x1400161e4`

## import_xrefs

- `KERNEL32!LocalFree` at `0x14001523c`
- `KERNEL32!LocalFree` at `0x140015265`
- `KERNEL32!LocalFree` at `0x14001528b`
- `KERNEL32!LocalFree` at `0x14001523c`
- `KERNEL32!LocalFree` at `0x140015265`
- `KERNEL32!LocalFree` at `0x14001528b`
- `KERNEL32!SetLastError` at `0x1400152a9`
- `KERNEL32!SetLastError` at `0x1400152a9`
- `KERNEL32!GetLastError` at `0x14001520c`
- `KERNEL32!GetLastError` at `0x14001522d`
- `KERNEL32!GetLastError` at `0x140015250`
- `KERNEL32!GetLastError` at `0x140015279`
- `KERNEL32!GetLastError` at `0x14001529f`
- `KERNEL32!GetLastError` at `0x14001520c`
- `KERNEL32!GetLastError` at `0x14001522d`
- `KERNEL32!GetLastError` at `0x140015250`
- `KERNEL32!GetLastError` at `0x140015279`
- `KERNEL32!GetLastError` at `0x14001529f`

## pseudocode

```c
__int64 __fastcall SuCreatePool_CleanupPool(struct _SU_POOL_OBJECT *hMem)
{
  int v2; // ebp
  DWORD LastError; // edi
  unsigned int v4; // ebx
  HLOCAL v5; // rax
  HLOCAL v6; // rax
  HLOCAL v7; // rax
  unsigned int v9; // [rsp+48h] [rbp+10h] BYREF
  HLOCAL hMema; // [rsp+50h] [rbp+18h] BYREF
  HLOCAL v11; // [rsp+58h] [rbp+20h] BYREF

  v9 = 0;
  hMema = 0;
  v11 = 0;
  v2 = SuDeletePoolEx(hMem, &v9, &hMema);
  LastError = GetLastError();
  v4 = SuNormalizeDriveList(v9, (const struct _SP_DRIVE_INFO *)hMema, (unsigned int **)&v11);
  if ( v2 )
    LastError = GetLastError();
  else
    v4 = 0;
  v5 = LocalFree(hMem);
  if ( v4 )
  {
    v4 = v5 == 0;
    LastError = GetLastError();
  }
  if ( hMema )
  {
    v6 = LocalFree(hMema);
    if ( v4 )
    {
      v4 = v6 == 0;
      LastError = GetLastError();
    }
  }
  if ( v11 )
  {
    v7 = LocalFree(v11);
    if ( v4 )
    {
      v4 = v7 == 0;
      LastError = GetLastError();
    }
  }
  SetLastError(LastError);
  return v4;
}

```

## disassembly

```asm
0x1400151d4  mov     rax, rsp
0x1400151d7  mov     [rax+8], rbx
0x1400151db  push    rbp
0x1400151dc  push    rdi
0x1400151dd  push    r14
0x1400151df  sub     rsp, 20h
0x1400151e3  lea     r8, [rax+18h]; struct _SP_DRIVE_INFO **
0x1400151e7  mov     dword ptr [rax+10h], 0
0x1400151ee  lea     rdx, [rax+10h]; unsigned int *
0x1400151f2  mov     qword ptr [rax+18h], 0
0x1400151fa  mov     r14, rcx
0x1400151fd  mov     qword ptr [rax+20h], 0
0x140015205  call    ?SuDeletePoolEx@@YAHPEAU_SU_POOL_OBJECT@@PEAIPEAPEAU_SP_DRIVE_INFO@@@Z; SuDeletePoolEx(_SU_POOL_OBJECT *,uint *,_SP_DRIVE_INFO * *)
0x14001520a  mov     ebp, eax
0x14001520c  call    cs:__imp_GetLastError
0x140015212  mov     rdx, [rsp+38h+hMem]; struct _SP_DRIVE_INFO *
0x140015217  lea     r8, [rsp+38h+arg_18]; unsigned int **
0x14001521c  mov     ecx, [rsp+38h+arg_8]; unsigned int
0x140015220  mov     edi, eax
0x140015222  call    ?SuNormalizeDriveList@@YAHIPEBU_SP_DRIVE_INFO@@PEAPEAK@Z; SuNormalizeDriveList(uint,_SP_DRIVE_INFO const *,ulong * *)
0x140015227  mov     ebx, eax
0x140015229  test    ebp, ebp
0x14001522b  jz      short loc_140015237
0x14001522d  call    cs:__imp_GetLastError
0x140015233  mov     edi, eax
0x140015235  jmp     short loc_140015239
0x140015237  mov     ebx, ebp
0x140015239  mov     rcx, r14; hMem
0x14001523c  call    cs:__imp_LocalFree
0x140015242  xor     edx, edx
0x140015244  test    rax, rax
0x140015247  setz    dl
0x14001524a  test    ebx, ebx
0x14001524c  jz      short loc_140015258
0x14001524e  mov     ebx, edx
0x140015250  call    cs:__imp_GetLastError
0x140015256  mov     edi, eax
0x140015258  cmp     [rsp+38h+hMem], 0
0x14001525e  jz      short loc_140015281
0x140015260  mov     rcx, [rsp+38h+hMem]; hMem
0x140015265  call    cs:__imp_LocalFree
0x14001526b  xor     ecx, ecx
0x14001526d  test    rax, rax
0x140015270  setz    cl
0x140015273  test    ebx, ebx
0x140015275  jz      short loc_140015281
0x140015277  mov     ebx, ecx
0x140015279  call    cs:__imp_GetLastError
0x14001527f  mov     edi, eax
0x140015281  mov     rcx, [rsp+38h+arg_18]; hMem
0x140015286  test    rcx, rcx
0x140015289  jz      short loc_1400152A7
0x14001528b  call    cs:__imp_LocalFree
0x140015291  xor     ecx, ecx
0x140015293  test    rax, rax
0x140015296  setz    cl
0x140015299  test    ebx, ebx
0x14001529b  jz      short loc_1400152A7
0x14001529d  mov     ebx, ecx
0x14001529f  call    cs:__imp_GetLastError
0x1400152a5  mov     edi, eax
0x1400152a7  mov     ecx, edi; dwErrCode
0x1400152a9  call    cs:__imp_SetLastError
0x1400152af  mov     eax, ebx
0x1400152b1  mov     rbx, [rsp+38h+arg_0]
0x1400152b6  add     rsp, 20h
0x1400152ba  pop     r14
0x1400152bc  pop     rdi
0x1400152bd  pop     rbp
0x1400152be  retn
```
