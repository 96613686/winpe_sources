# CPropertyCache::unboundgetproperty(ulong,ulong *,ulong *,ulong *,_iistype * *)

- ea: `0x180011034`
- end: `0x1800110b6`
- name: `?unboundgetproperty@CPropertyCache@@QEAAJKPEAK00PEAPEAU_iistype@@@Z`
- size: `130`
- prototype: `__int64 __fastcall(CPropertyCache *__hidden this, unsigned int, unsigned int *, unsigned int *, unsigned int *, struct _iistype **)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180006b00`
- `0x180006d90`

## callees

- `0x180010e8c`
- `0x180011034`
- `0x1800183ac`

## pseudocode

```c
__int64 __fastcall CPropertyCache::unboundgetproperty(
        CPropertyCache *this,
        unsigned int a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned int *a5,
        struct _iistype **a6)
{
  unsigned int v6; // edx
  __int64 v7; // r8
  unsigned int *v8; // r9
  _DWORD *v9; // r10
  __int64 v11; // r8
  __int64 v12; // rdx
  struct _iistype *v13; // rcx
  int v14; // eax
  unsigned int v15; // edx

  if ( !(unsigned int)CPropertyCache::index_valid(this, a2) )
    return 2147504141LL;
  v11 = *(_QWORD *)(v7 + 32);
  v12 = 544LL * v6;
  *a5 = *(_DWORD *)(v12 + v11 + 520);
  v13 = *(struct _iistype **)(v12 + v11 + 536);
  if ( v13 )
  {
    v14 = *(_DWORD *)(v12 + v11 + 528);
    v15 = *(_DWORD *)(v12 + v11 + 524);
    *v9 = v14;
    *v8 = v15;
    return IISTypeCopyConstruct(v13, v15, a6);
  }
  else
  {
    *v8 = 0;
    *v9 = 0;
    *a6 = 0;
    return 1;
  }
}

```

## disassembly

```asm
0x180011034  sub     rsp, 28h
0x180011038  mov     r10, r8
0x18001103b  mov     r8, rcx
0x18001103e  call    ?index_valid@CPropertyCache@@QEAAHK@Z; CPropertyCache::index_valid(ulong)
0x180011043  xor     r11d, r11d
0x180011046  test    eax, eax
0x180011048  jnz     short loc_180011051
0x18001104a  mov     eax, 8000500Dh
0x18001104f  jmp     short loc_1800110B1
0x180011051  mov     r8, [r8+20h]
0x180011055  mov     eax, edx
0x180011057  imul    rdx, rax, 220h
0x18001105e  mov     rax, [rsp+28h+arg_20]
0x180011063  mov     ecx, [rdx+r8+208h]
0x18001106b  mov     [rax], ecx
0x18001106d  mov     rcx, [rdx+r8+218h]; struct _iistype *
0x180011075  test    rcx, rcx
0x180011078  jz      short loc_18001109E
0x18001107a  mov     eax, [rdx+r8+210h]
0x180011082  mov     edx, [rdx+r8+20Ch]; unsigned int
0x18001108a  mov     r8, [rsp+28h+arg_28]; struct _iistype **
0x18001108f  mov     [r10], eax
0x180011092  mov     [r9], edx
0x180011095  add     rsp, 28h
0x180011099  jmp     ?IISTypeCopyConstruct@@YAJPEAU_iistype@@KPEAPEAU1@@Z; IISTypeCopyConstruct(_iistype *,ulong,_iistype * *)
0x18001109e  mov     rax, [rsp+28h+arg_28]
0x1800110a3  mov     [r9], r11d
0x1800110a6  mov     [r10], r11d
0x1800110a9  mov     [rax], r11
0x1800110ac  mov     eax, 1
0x1800110b1  add     rsp, 28h
0x1800110b5  retn
```
