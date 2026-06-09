# MetaBaseGetDataPaths(IMSAdminBaseW *,ulong,ulong,uchar * *)

- ea: `0x180014270`
- end: `0x18001436c`
- name: `?MetaBaseGetDataPaths@@YAJPEAUIMSAdminBaseW@@KKPEAPEAE@Z`
- size: `252`
- prototype: `__int64 __fastcall(struct IMSAdminBaseW *, unsigned int, unsigned int, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005cd0`

## callees

- `0x18001201c`
- `0x180014270`
- `0x18001e010`

## import_xrefs

- `ACTIVEDS!__imp_AllocADsMem` at `0x1800142df`
- `ACTIVEDS!__imp_AllocADsMem` at `0x1800142df`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180014346`
- `ACTIVEDS!__imp_FreeADsMem` at `0x180014346`

## pseudocode

```c
__int64 __fastcall MetaBaseGetDataPaths(struct IMSAdminBaseW *a1, __int64 a2, unsigned int a3, unsigned __int8 **a4)
{
  struct IMSAdminBaseWVtbl *lpVtbl; // rax
  unsigned int v8; // r15d
  void *v9; // rdi
  int LastError; // ebx
  __int64 result; // rax
  int v12; // [rsp+80h] [rbp+8h] BYREF

  lpVtbl = a1->lpVtbl;
  v12 = 0;
  v8 = a2;
  ((void (__fastcall *)(struct IMSAdminBaseW *, __int64, const OLECHAR *, _QWORD, _DWORD, _DWORD, const OLECHAR *, int *))lpVtbl->GetDataPaths)(
    a1,
    a2,
    &psz,
    a3,
    0,
    0,
    &psz,
    &v12);
  v9 = AllocADsMem(2 * v12);
  if ( !v9 )
  {
    LastError = HResultGetLastError();
    if ( LastError < 0 )
      return (unsigned int)LastError;
  }
  result = ((__int64 (__fastcall *)(struct IMSAdminBaseW *, _QWORD, const OLECHAR *, _QWORD, _DWORD, int, void *, int *))a1->lpVtbl->GetDataPaths)(
             a1,
             v8,
             &psz,
             a3,
             0,
             v12,
             v9,
             &v12);
  LastError = result;
  if ( (int)result < 0 )
  {
    if ( v9 )
      FreeADsMem(v9);
    return (unsigned int)LastError;
  }
  *a4 = (unsigned __int8 *)v9;
  return result;
}

```

## disassembly

```asm
0x180014270  mov     r11, rsp
0x180014273  mov     [r11+10h], rbx
0x180014277  mov     [r11+18h], rbp
0x18001427b  push    rsi
0x18001427c  push    rdi
0x18001427d  push    r13
0x18001427f  push    r14
0x180014281  push    r15
0x180014283  sub     rsp, 50h
0x180014287  mov     rax, [rcx]
0x18001428a  lea     r13, psz
0x180014291  mov     rsi, rcx
0x180014294  mov     dword ptr [r11+8], 0
0x18001429c  lea     rcx, [r11+8]
0x1800142a0  mov     r14, r9
0x1800142a3  mov     [r11-40h], rcx
0x1800142a7  mov     ebp, r8d
0x1800142aa  mov     rax, [rax+80h]
0x1800142b1  mov     r9d, r8d
0x1800142b4  mov     [r11-48h], r13
0x1800142b8  mov     r8, r13
0x1800142bb  mov     [rsp+78h+var_50], 0
0x1800142c3  mov     rcx, rsi
0x1800142c6  mov     [rsp+78h+var_58], 0
0x1800142ce  mov     r15d, edx
0x1800142d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142d6  mov     ecx, [rsp+78h+arg_0]
0x1800142dd  add     ecx, ecx; cb
0x1800142df  call    cs:__imp_AllocADsMem
0x1800142e5  mov     rdi, rax
0x1800142e8  test    rax, rax
0x1800142eb  jnz     short loc_1800142F8
0x1800142ed  call    ?HResultGetLastError@@YAJXZ; HResultGetLastError(void)
0x1800142f2  mov     ebx, eax
0x1800142f4  test    eax, eax
0x1800142f6  js      short loc_18001434C
0x1800142f8  mov     rcx, [rsi]
0x1800142fb  mov     r9d, ebp
0x1800142fe  mov     edx, [rsp+78h+arg_0]
0x180014305  mov     r8, r13
0x180014308  mov     rax, [rcx+80h]
0x18001430f  lea     rcx, [rsp+78h+arg_0]
0x180014317  mov     [rsp+78h+var_40], rcx
0x18001431c  mov     rcx, rsi
0x18001431f  mov     [rsp+78h+var_48], rdi
0x180014324  mov     [rsp+78h+var_50], edx
0x180014328  mov     edx, r15d
0x18001432b  mov     [rsp+78h+var_58], 0
0x180014333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014338  mov     ebx, eax
0x18001433a  test    eax, eax
0x18001433c  jns     short loc_180014350
0x18001433e  test    rdi, rdi
0x180014341  jz      short loc_18001434C
0x180014343  mov     rcx, rdi; pMem
0x180014346  call    cs:__imp_FreeADsMem
0x18001434c  mov     eax, ebx
0x18001434e  jmp     short loc_180014353
0x180014350  mov     [r14], rdi
0x180014353  lea     r11, [rsp+78h+var_28]
0x180014358  mov     rbx, [r11+38h]
0x18001435c  mov     rbp, [r11+40h]
0x180014360  mov     rsp, r11
0x180014363  pop     r15
0x180014365  pop     r14
0x180014367  pop     r13
0x180014369  pop     rdi
0x18001436a  pop     rsi
0x18001436b  retn
```
