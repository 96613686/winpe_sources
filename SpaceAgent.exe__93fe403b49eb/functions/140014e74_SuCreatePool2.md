# SuCreatePool2

- ea: `0x140014e74`
- end: `0x140014f0b`
- name: `SuCreatePool2`
- size: `151`
- prototype: `__int64 __fastcall(unsigned __int16 *, struct _SU_POOL_OBJECT **, struct _LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140014f14`

## callees

- `0x140008190`
- `0x14000a8dc`
- `0x14000b02c`
- `0x140014e74`

## import_xrefs

- `KERNEL32!LocalFree` at `0x140014ef0`
- `KERNEL32!LocalFree` at `0x140014ef0`

## pseudocode

```c
__int64 __fastcall SuCreatePool2(size_t *a1, struct _SU_POOL_OBJECT **a2, struct _LIST_ENTRY *a3)
{
  unsigned int PoolTemplate; // eax
  struct _SP_POOL_INFO *v7; // rbx
  unsigned int Pool; // edi
  int (__high *v9)(enum _SU_OPERATION, struct _LIST_ENTRY *, void *, void *, void *, void *); // r8
  void *v10; // r9
  HLOCAL hMem; // [rsp+58h] [rbp+10h] BYREF

  *a2 = 0;
  hMem = 0;
  PoolTemplate = SuGetPoolTemplate((__int64)a1, (__int64 *)a3, &hMem);
  v7 = (struct _SP_POOL_INFO *)hMem;
  Pool = PoolTemplate;
  if ( PoolTemplate )
  {
    StringCchCopyW((unsigned __int16 *)hMem + 12, 0x100u, a1);
    *((_DWORD *)v7 + 665) = 4096;
    *((_DWORD *)v7 + 666) = 4096;
    Pool = SuCreatePool(v7, a3, v9, v10, a2);
  }
  LocalFree(v7);
  return Pool;
}

```

## disassembly

```asm
0x140014e74  mov     rax, rsp
0x140014e77  mov     [rax+8], rbx
0x140014e7b  mov     [rax+18h], rbp
0x140014e7f  push    rsi
0x140014e80  push    rdi
0x140014e81  push    r14
0x140014e83  sub     rsp, 30h
0x140014e87  mov     rsi, r8
0x140014e8a  mov     qword ptr [rdx], 0
0x140014e91  mov     r14, rdx
0x140014e94  mov     qword ptr [rax+10h], 0
0x140014e9c  mov     rdx, rsi
0x140014e9f  lea     r8, [rax+10h]
0x140014ea3  mov     rbp, rcx
0x140014ea6  call    ?SuGetPoolTemplate@@YAHW4_SC_VERSION@@PEAU_LIST_ENTRY@@PEAPEAU_SP_POOL_INFO@@@Z; SuGetPoolTemplate(_SC_VERSION,_LIST_ENTRY *,_SP_POOL_INFO * *)
0x140014eab  mov     rbx, [rsp+48h+hMem]
0x140014eb0  mov     edi, eax
0x140014eb2  test    eax, eax
0x140014eb4  jz      short loc_140014EED
0x140014eb6  lea     rcx, [rbx+18h]; unsigned __int16 *
0x140014eba  mov     r8, rbp; unsigned __int16 *
0x140014ebd  mov     edx, 100h; unsigned __int64
0x140014ec2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140014ec7  mov     r11d, 1000h
0x140014ecd  mov     [rsp+48h+var_28], r14; struct _SU_POOL_OBJECT **
0x140014ed2  mov     [rbx+0A64h], r11d
0x140014ed9  mov     rdx, rsi; struct _LIST_ENTRY *
0x140014edc  mov     rcx, rbx; struct _SP_POOL_INFO *
0x140014edf  mov     [rbx+0A68h], r11d
0x140014ee6  call    ?SuCreatePool@@YAHPEAU_SP_POOL_INFO@@PEAU_LIST_ENTRY@@P6AHW4_SU_OPERATION@@1PEAX333@Z3PEAPEAU_SU_POOL_OBJECT@@@Z; SuCreatePool(_SP_POOL_INFO *,_LIST_ENTRY *,int (*)(_SU_OPERATION,_LIST_ENTRY *,void *,void *,void *,void *),void *,_SU_POOL_OBJECT * *)
0x140014eeb  mov     edi, eax
0x140014eed  mov     rcx, rbx; hMem
0x140014ef0  call    cs:__imp_LocalFree
0x140014ef6  mov     rbx, [rsp+48h+arg_0]
0x140014efb  mov     eax, edi
0x140014efd  mov     rbp, [rsp+48h+arg_10]
0x140014f02  add     rsp, 30h
0x140014f06  pop     r14
0x140014f08  pop     rdi
0x140014f09  pop     rsi
0x140014f0a  retn
```
