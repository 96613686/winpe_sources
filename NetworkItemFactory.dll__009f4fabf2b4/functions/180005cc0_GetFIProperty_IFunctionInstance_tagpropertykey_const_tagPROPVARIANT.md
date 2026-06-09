# GetFIProperty(IFunctionInstance *,_tagpropertykey const &,tagPROPVARIANT *)

- ea: `0x180005cc0`
- end: `0x180005d33`
- name: `?GetFIProperty@@YAJPEAUIFunctionInstance@@AEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z`
- size: `115`
- prototype: `__int64 __fastcall(struct IFunctionInstance *, const struct _tagpropertykey *, struct tagPROPVARIANT *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180002ab8`
- `0x1800037f8`
- `0x180005b84`
- `0x180005bec`
- `0x180005c50`

## callees

- `0x180005cc0`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall GetFIProperty(
        struct IFunctionInstance *a1,
        const struct _tagpropertykey *a2,
        struct tagPROPVARIANT *a3)
{
  struct IFunctionInstanceVtbl *lpVtbl; // rax
  int v6; // ebx
  __int64 v8; // [rsp+50h] [rbp+8h] BYREF

  lpVtbl = a1->lpVtbl;
  v8 = 0;
  v6 = ((__int64 (__fastcall *)(struct IFunctionInstance *, _QWORD, __int64 *))lpVtbl->OpenPropertyStore)(a1, 0, &v8);
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(__int64, const struct _tagpropertykey *, struct tagPROPVARIANT *))(*(_QWORD *)v8 + 40LL))(
           v8,
           a2,
           a3);
    if ( v6 >= 0 && !a3->vt )
      v6 = -2147023288;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180005cc0  push    rbx
0x180005cc2  push    rbp
0x180005cc3  push    rsi
0x180005cc4  push    rdi
0x180005cc5  sub     rsp, 28h
0x180005cc9  mov     rax, [rcx]
0x180005ccc  mov     rdi, r8
0x180005ccf  mov     rsi, rdx
0x180005cd2  lea     r8, [rsp+48h+arg_0]
0x180005cd7  xor     ebp, ebp
0x180005cd9  xor     edx, edx
0x180005cdb  mov     [rsp+48h+arg_0], rbp
0x180005ce0  mov     rax, [rax+30h]
0x180005ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ce9  mov     ebx, eax
0x180005ceb  test    eax, eax
0x180005ced  js      short loc_180005D28
0x180005cef  mov     rcx, [rsp+48h+arg_0]
0x180005cf4  mov     r8, rdi
0x180005cf7  mov     rdx, rsi
0x180005cfa  mov     rax, [rcx]
0x180005cfd  mov     rax, [rax+28h]
0x180005d01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d06  mov     ebx, eax
0x180005d08  test    eax, eax
0x180005d0a  js      short loc_180005D17
0x180005d0c  cmp     [rdi], bp
0x180005d0f  mov     eax, 80070648h
0x180005d14  cmovz   ebx, eax
0x180005d17  mov     rcx, [rsp+48h+arg_0]
0x180005d1c  mov     rax, [rcx]
0x180005d1f  mov     rax, [rax+10h]
0x180005d23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d28  mov     eax, ebx
0x180005d2a  add     rsp, 28h
0x180005d2e  pop     rdi
0x180005d2f  pop     rsi
0x180005d30  pop     rbp
0x180005d31  pop     rbx
0x180005d32  retn
```
