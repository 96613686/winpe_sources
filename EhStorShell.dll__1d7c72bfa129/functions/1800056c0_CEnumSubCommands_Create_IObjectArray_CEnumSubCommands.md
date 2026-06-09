# CEnumSubCommands::Create(IObjectArray *,CEnumSubCommands * *)

- ea: `0x1800056c0`
- end: `0x180005759`
- name: `?Create@CEnumSubCommands@@SAJPEAUIObjectArray@@PEAPEAV1@@Z`
- size: `153`
- prototype: `__int64 __fastcall(struct IObjectArray *, struct CEnumSubCommands **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000a890`

## callees

- `0x1800056c0`
- `0x180006b8c`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall CEnumSubCommands::Create(struct IObjectArray *a1, struct CEnumSubCommands **a2)
{
  _DWORD *v4; // rbx

  v4 = operator new(0x30u);
  if ( v4 )
  {
    *(_QWORD *)v4 = &CEnumSubCommands::`vftable';
    v4[2] = 1;
    *((_QWORD *)v4 + 2) = a1;
    if ( a1 )
      ((void (__fastcall *)(struct IObjectArray *))a1->lpVtbl->AddRef)(a1);
    *((_QWORD *)v4 + 4) = 0;
    v4[6] = 0;
    v4[10] = 0;
    *a2 = (struct CEnumSubCommands *)v4;
    return v4 == 0 ? 0x8007000E : 0;
  }
  else
  {
    *a2 = 0;
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x1800056c0  mov     [rsp+arg_0], rbx
0x1800056c5  mov     [rsp+arg_10], rsi
0x1800056ca  push    rdi
0x1800056cb  sub     rsp, 20h
0x1800056cf  mov     rsi, rdx
0x1800056d2  mov     rdi, rcx
0x1800056d5  mov     ecx, 30h ; '0'; Size
0x1800056da  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800056df  mov     rbx, rax
0x1800056e2  mov     [rsp+28h+arg_8], rax
0x1800056e7  test    rax, rax
0x1800056ea  jz      short loc_18000573D
0x1800056ec  lea     rax, ??_7CEnumSubCommands@@6B@; const CEnumSubCommands::`vftable'
0x1800056f3  mov     [rbx], rax
0x1800056f6  mov     dword ptr [rbx+8], 1
0x1800056fd  mov     [rbx+10h], rdi
0x180005701  test    rdi, rdi
0x180005704  jz      short loc_180005716
0x180005706  mov     rax, [rdi]
0x180005709  mov     rcx, rdi
0x18000570c  mov     rax, [rax+8]
0x180005710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005715  nop
0x180005716  mov     qword ptr [rbx+20h], 0
0x18000571e  mov     dword ptr [rbx+18h], 0
0x180005725  mov     dword ptr [rbx+28h], 0
0x18000572c  mov     [rsi], rbx
0x18000572f  neg     rbx
0x180005732  sbb     eax, eax
0x180005734  not     eax
0x180005736  and     eax, 8007000Eh
0x18000573b  jmp     short loc_180005749
0x18000573d  mov     qword ptr [rsi], 0
0x180005744  mov     eax, 8007000Eh
0x180005749  mov     rbx, [rsp+28h+arg_0]
0x18000574e  mov     rsi, [rsp+28h+arg_10]
0x180005753  add     rsp, 20h
0x180005757  pop     rdi
0x180005758  retn
```
