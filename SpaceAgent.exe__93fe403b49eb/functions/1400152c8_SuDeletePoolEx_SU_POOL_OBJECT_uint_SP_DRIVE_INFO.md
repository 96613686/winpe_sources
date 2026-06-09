# SuDeletePoolEx(_SU_POOL_OBJECT *,uint *,_SP_DRIVE_INFO * *)

- ea: `0x1400152c8`
- end: `0x14001535f`
- name: `?SuDeletePoolEx@@YAHPEAU_SU_POOL_OBJECT@@PEAIPEAPEAU_SP_DRIVE_INFO@@@Z`
- size: `151`
- prototype: `__int64 __fastcall(struct _SU_POOL_OBJECT *, unsigned int *, HLOCAL *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400151d4`
- `0x1400185d0`

## callees

- `0x14000ad60`
- `0x1400152c8`
- `0x140015368`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140015329`
- `KERNEL32!LocalFree` at `0x140015329`
- `KERNEL32!SetLastError` at `0x14001534e`
- `KERNEL32!SetLastError` at `0x14001534e`
- `KERNEL32!GetLastError` at `0x1400152fe`
- `KERNEL32!GetLastError` at `0x140015313`
- `KERNEL32!GetLastError` at `0x1400152fe`
- `KERNEL32!GetLastError` at `0x140015313`

## pseudocode

```c
__int64 __fastcall SuDeletePoolEx(struct _SU_POOL_OBJECT *a1, unsigned int *a2, HLOCAL *a3)
{
  int (__high *v6)(enum _SU_OPERATION, struct _LIST_ENTRY *, void *, void *, void *, void *); // rdx
  unsigned int v7; // ebx
  void *v8; // r8
  DWORD LastError; // ebp
  HLOCAL hMem[7]; // [rsp+20h] [rbp-38h] BYREF
  unsigned int v12; // [rsp+78h] [rbp+20h] BYREF

  v12 = 0;
  hMem[0] = 0;
  v7 = SuDeletePoolEx_GetDrives(a1, &v12, hMem);
  if ( v7 || GetLastError() == 2 )
    v7 = SuDeletePool(a1, v6, v8);
  LastError = GetLastError();
  if ( v7 )
  {
    *a2 = v12;
    *a3 = hMem[0];
  }
  else
  {
    if ( hMem[0] )
      LocalFree(hMem[0]);
    *a2 = 0;
    *a3 = 0;
  }
  SetLastError(LastError);
  return v7;
}

```

## disassembly

```asm
0x1400152c8  mov     rax, rsp
0x1400152cb  push    rbx
0x1400152cc  push    rbp
0x1400152cd  push    rsi
0x1400152ce  push    rdi
0x1400152cf  sub     rsp, 38h
0x1400152d3  mov     rdi, r8
0x1400152d6  mov     dword ptr [rax+20h], 0
0x1400152dd  mov     rsi, rdx
0x1400152e0  mov     qword ptr [rax-38h], 0
0x1400152e8  lea     r8, [rax-38h]
0x1400152ec  mov     rbp, rcx
0x1400152ef  lea     rdx, [rax+20h]
0x1400152f3  call    SuDeletePoolEx_GetDrives
0x1400152f8  mov     ebx, eax
0x1400152fa  test    eax, eax
0x1400152fc  jnz     short loc_140015309
0x1400152fe  call    cs:__imp_GetLastError
0x140015304  cmp     eax, 2
0x140015307  jnz     short loc_140015313
0x140015309  mov     rcx, rbp; struct _SU_POOL_OBJECT *
0x14001530c  call    ?SuDeletePool@@YAHPEAU_SU_POOL_OBJECT@@P6AHW4_SU_OPERATION@@PEAU_LIST_ENTRY@@PEAX333@Z3@Z; SuDeletePool(_SU_POOL_OBJECT *,int (*)(_SU_OPERATION,_LIST_ENTRY *,void *,void *,void *,void *),void *)
0x140015311  mov     ebx, eax
0x140015313  call    cs:__imp_GetLastError
0x140015319  mov     ebp, eax
0x14001531b  test    ebx, ebx
0x14001531d  jnz     short loc_14001533E
0x14001531f  mov     rcx, [rsp+58h+hMem]; hMem
0x140015324  test    rcx, rcx
0x140015327  jz      short loc_14001532F
0x140015329  call    cs:__imp_LocalFree
0x14001532f  mov     dword ptr [rsi], 0
0x140015335  mov     qword ptr [rdi], 0
0x14001533c  jmp     short loc_14001534C
0x14001533e  mov     eax, [rsp+58h+arg_18]
0x140015342  mov     [rsi], eax
0x140015344  mov     rax, [rsp+58h+hMem]
0x140015349  mov     [rdi], rax
0x14001534c  mov     ecx, ebp; dwErrCode
0x14001534e  call    cs:__imp_SetLastError
0x140015354  mov     eax, ebx
0x140015356  add     rsp, 38h
0x14001535a  pop     rdi
0x14001535b  pop     rsi
0x14001535c  pop     rbp
0x14001535d  pop     rbx
0x14001535e  retn
```
