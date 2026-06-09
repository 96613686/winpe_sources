# CSyncServices::CreateDestinationChangeVersionsBuilder(IDestinationChangeVersionsBuilder * *)

- ea: `0x18002b570`
- end: `0x18002b691`
- name: `?CreateDestinationChangeVersionsBuilder@CSyncServices@@UEAAJPEAPEAUIDestinationChangeVersionsBuilder@@@Z`
- size: `289`
- prototype: `__int64 __fastcall(CSyncServices *__hidden this, struct IDestinationChangeVersionsBuilder **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18002b6a0`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18002b570`
- `0x18004dda4`
- `0x180094010`

## string_xrefs

- `0x18002b5a3`: `CSyncServices::CreateDestinationChangeVersionsBuilder`
- `0x18002b669`: `CSyncServices::CreateDestinationChangeVersionsBuilder`

## pseudocode

```c
__int64 __fastcall CSyncServices::CreateDestinationChangeVersionsBuilder(
        CSyncServices *this,
        struct IDestinationChangeVersionsBuilder **a2)
{
  PVOID *v4; // rcx
  int v5; // edi
  struct IdParameters *v6; // rcx
  void *v7; // rbx
  void *v9; // [rsp+70h] [rbp+8h] BYREF

  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      48,
      WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      "CSyncServices::CreateDestinationChangeVersionsBuilder");
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  v5 = -2147217407;
  if ( *((_QWORD *)this + 6) )
  {
    v5 = -2147467261;
    if ( a2 )
    {
      v6 = (struct IdParameters *)*((_QWORD *)this + 6);
      v9 = 0;
      v5 = CSyncChangeBatch_CreateInstance(v6, 0, 0, 0, 0, 0, 1, &v9);
      if ( v5 >= 0 )
      {
        v7 = v9;
        v5 = (**(__int64 (__fastcall ***)(void *, GUID *, struct IDestinationChangeVersionsBuilder **))v9)(
               v9,
               &IID_IDestinationChangeVersionsBuilder,
               a2);
        (*(void (__fastcall **)(void *))(*(_QWORD *)v7 + 16LL))(v7);
      }
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 2) != 0 && *((_BYTE *)v4 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v4[2],
      49,
      (unsigned int)WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      (unsigned int)"CSyncServices::CreateDestinationChangeVersionsBuilder",
      v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18002b570  push    rbx
0x18002b572  push    rsi
0x18002b573  push    rdi
0x18002b574  push    r14
0x18002b576  sub     rsp, 48h
0x18002b57a  mov     rsi, rdx
0x18002b57d  mov     rbx, rcx
0x18002b580  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b587  lea     r14, WPP_GLOBAL_Control
0x18002b58e  cmp     rcx, r14
0x18002b591  jz      short loc_18002B5C2
0x18002b593  test    byte ptr [rcx+1Ch], 2
0x18002b597  jz      short loc_18002B5C2
0x18002b599  cmp     byte ptr [rcx+19h], 5
0x18002b59d  jb      short loc_18002B5C2
0x18002b59f  mov     rcx, [rcx+10h]
0x18002b5a3  lea     r9, aCsyncservicesC_0; "CSyncServices::CreateDestinationChangeV"...
0x18002b5aa  mov     edx, 30h ; '0'
0x18002b5af  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002b5b6  call    WPP_SF_s
0x18002b5bb  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b5c2  cmp     qword ptr [rbx+30h], 0
0x18002b5c7  mov     edi, 80041001h
0x18002b5cc  jz      loc_18002B654
0x18002b5d2  mov     edi, 80004003h
0x18002b5d7  test    rsi, rsi
0x18002b5da  jz      short loc_18002B654
0x18002b5dc  mov     rcx, [rbx+30h]; this
0x18002b5e0  lea     rax, [rsp+68h+arg_0]
0x18002b5e5  mov     [rsp+68h+var_30], rax; void **
0x18002b5ea  xor     r9d, r9d; struct ISyncFilterInfo *
0x18002b5ed  mov     [rsp+68h+var_38], 1; int
0x18002b5f5  xor     r8d, r8d; struct IForgottenKnowledge *
0x18002b5f8  mov     [rsp+68h+var_40], 0; unsigned __int8 *
0x18002b601  xor     edx, edx; struct ISyncKnowledge *
0x18002b603  mov     [rsp+68h+var_48], 0; int
0x18002b60b  mov     [rsp+68h+arg_0], 0
0x18002b614  call    ?CSyncChangeBatch_CreateInstance@@YAJPEAVIdParameters@@PEAUISyncKnowledge@@PEAUIForgottenKnowledge@@PEAUISyncFilterInfo@@HPEBEHPEAPEAX@Z; CSyncChangeBatch_CreateInstance(IdParameters *,ISyncKnowledge *,IForgottenKnowledge *,ISyncFilterInfo *,int,uchar const *,int,void * *)
0x18002b619  mov     edi, eax
0x18002b61b  test    eax, eax
0x18002b61d  js      short loc_18002B64D
0x18002b61f  mov     rbx, [rsp+68h+arg_0]
0x18002b624  lea     rdx, IID_IDestinationChangeVersionsBuilder
0x18002b62b  mov     r8, rsi
0x18002b62e  mov     rcx, rbx
0x18002b631  mov     rax, [rbx]
0x18002b634  mov     rax, [rax]
0x18002b637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b63c  mov     edi, eax
0x18002b63e  mov     rcx, rbx
0x18002b641  mov     rax, [rbx]
0x18002b644  mov     rax, [rax+10h]
0x18002b648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b64d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b654  cmp     rcx, r14
0x18002b657  jz      short loc_18002B685
0x18002b659  test    byte ptr [rcx+1Ch], 2
0x18002b65d  jz      short loc_18002B685
0x18002b65f  cmp     byte ptr [rcx+19h], 5
0x18002b663  jb      short loc_18002B685
0x18002b665  mov     rcx, [rcx+10h]
0x18002b669  lea     r9, aCsyncservicesC_0; "CSyncServices::CreateDestinationChangeV"...
0x18002b670  mov     edx, 31h ; '1'
0x18002b675  mov     [rsp+68h+var_48], edi
0x18002b679  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002b680  call    WPP_SF_sD
0x18002b685  mov     eax, edi
0x18002b687  add     rsp, 48h
0x18002b68b  pop     r14
0x18002b68d  pop     rdi
0x18002b68e  pop     rsi
0x18002b68f  pop     rbx
0x18002b690  retn
```
