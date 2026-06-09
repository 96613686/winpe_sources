# CCompatContextMenu::Initialize(_ITEMIDLIST const *,IDataObject *,HKEY__ *)

- ea: `0x1800094d0`
- end: `0x180009533`
- name: `?Initialize@CCompatContextMenu@@UEAAJPEFBU_ITEMIDLIST@@PEAUIDataObject@@PEAUHKEY__@@@Z`
- size: `99`
- prototype: `__int64 __fastcall(CCompatContextMenu *__hidden this, const struct _ITEMIDLIST *, struct IDataObject *, HKEY)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800094d0`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall CCompatContextMenu::Initialize(
        CCompatContextMenu *this,
        const struct _ITEMIDLIST *a2,
        struct IDataObject *a3,
        HKEY a4)
{
  unsigned int v6; // ebx
  __int64 v7; // rcx

  if ( a3 )
  {
    v7 = *((_QWORD *)this + 75);
    v6 = 0;
    if ( v7 )
      (*(void (__fastcall **)(__int64, const struct _ITEMIDLIST *, struct IDataObject *, HKEY))(*(_QWORD *)v7 + 16LL))(
        v7,
        a2,
        a3,
        a4);
    *((_QWORD *)this + 75) = a3;
    ((void (__fastcall *)(struct IDataObject *, const struct _ITEMIDLIST *, struct IDataObject *, HKEY))a3->lpVtbl->AddRef)(
      a3,
      a2,
      a3,
      a4);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v6;
}

```

## disassembly

```asm
0x1800094d0  mov     [rsp+arg_0], rbx
0x1800094d5  mov     [rsp+arg_8], rsi
0x1800094da  push    rdi
0x1800094db  sub     rsp, 20h
0x1800094df  mov     rdi, r8
0x1800094e2  mov     rsi, rcx
0x1800094e5  test    r8, r8
0x1800094e8  jnz     short loc_1800094F1
0x1800094ea  mov     ebx, 80070057h
0x1800094ef  jmp     short loc_180009521
0x1800094f1  mov     rcx, [rcx+258h]
0x1800094f8  xor     ebx, ebx
0x1800094fa  test    rcx, rcx
0x1800094fd  jz      short loc_18000950B
0x1800094ff  mov     rax, [rcx]
0x180009502  mov     rax, [rax+10h]
0x180009506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000950b  mov     [rsi+258h], rdi
0x180009512  mov     rcx, [rdi]
0x180009515  mov     rax, [rcx+8]
0x180009519  mov     rcx, rdi
0x18000951c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009521  mov     rsi, [rsp+28h+arg_8]
0x180009526  mov     eax, ebx
0x180009528  mov     rbx, [rsp+28h+arg_0]
0x18000952d  add     rsp, 20h
0x180009531  pop     rdi
0x180009532  retn
```
