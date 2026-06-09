# CSyncServices::CreateChangeBatch(ISyncKnowledge *,IForgottenKnowledge *,ISyncChangeBatch * *)

- ea: `0x18002b230`
- end: `0x18002b36b`
- name: `?CreateChangeBatch@CSyncServices@@UEAAJPEAUISyncKnowledge@@PEAUIForgottenKnowledge@@PEAPEAUISyncChangeBatch@@@Z`
- size: `315`
- prototype: `__int64 __fastcall(CSyncServices *this, struct ISyncKnowledge *, struct IForgottenKnowledge *, struct ISyncChangeBatch **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18002b380`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18002b230`
- `0x18004dda4`
- `0x180094010`

## string_xrefs

- `0x18002b26c`: `CSyncServices::CreateChangeBatch`
- `0x18002b340`: `CSyncServices::CreateChangeBatch`

## pseudocode

```c
__int64 __fastcall CSyncServices::CreateChangeBatch(
        CSyncServices *this,
        struct ISyncKnowledge *a2,
        struct IForgottenKnowledge *a3,
        struct ISyncChangeBatch **a4)
{
  PVOID *v8; // rcx
  int v9; // edi
  struct IdParameters *v10; // rcx
  void *v11; // rbx
  void *v13; // [rsp+80h] [rbp+8h] BYREF

  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      38,
      WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      "CSyncServices::CreateChangeBatch");
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  v9 = -2147217407;
  if ( *((_QWORD *)this + 6) )
  {
    v9 = -2147467261;
    if ( a4 )
    {
      v10 = (struct IdParameters *)*((_QWORD *)this + 6);
      v13 = 0;
      v9 = CSyncChangeBatch_CreateInstance(v10, a2, a3, 0, 0, 0, 0, &v13);
      if ( v9 >= 0 )
      {
        v11 = v13;
        v9 = (**(__int64 (__fastcall ***)(void *, GUID *, struct ISyncChangeBatch **))v13)(
               v13,
               &GUID_70c64dee_380f_4c2e_8f70_31c55bd5f9b3,
               a4);
        (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 16LL))(v11);
      }
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 2) != 0 && *((_BYTE *)v8 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v8[2],
      39,
      (unsigned int)WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      (unsigned int)"CSyncServices::CreateChangeBatch",
      v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002b230  push    rbx
0x18002b232  push    rbp
0x18002b233  push    rsi
0x18002b234  push    rdi
0x18002b235  push    r12
0x18002b237  push    r14
0x18002b239  sub     rsp, 48h
0x18002b23d  mov     rsi, r9
0x18002b240  mov     rbp, r8
0x18002b243  mov     r14, rdx
0x18002b246  mov     rbx, rcx
0x18002b249  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b250  lea     r12, WPP_GLOBAL_Control
0x18002b257  cmp     rcx, r12
0x18002b25a  jz      short loc_18002B28B
0x18002b25c  test    byte ptr [rcx+1Ch], 2
0x18002b260  jz      short loc_18002B28B
0x18002b262  cmp     byte ptr [rcx+19h], 5
0x18002b266  jb      short loc_18002B28B
0x18002b268  mov     rcx, [rcx+10h]
0x18002b26c  lea     r9, aCsyncservicesC_14; "CSyncServices::CreateChangeBatch"
0x18002b273  mov     edx, 26h ; '&'
0x18002b278  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002b27f  call    WPP_SF_s
0x18002b284  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b28b  cmp     qword ptr [rbx+30h], 0
0x18002b290  mov     edi, 80041001h
0x18002b295  jz      loc_18002B32B
0x18002b29b  mov     edi, 80004003h
0x18002b2a0  test    rsi, rsi
0x18002b2a3  jz      loc_18002B32B
0x18002b2a9  mov     rcx, [rbx+30h]; this
0x18002b2ad  lea     rax, [rsp+78h+arg_0]
0x18002b2b5  mov     [rsp+78h+var_40], rax; void **
0x18002b2ba  xor     r9d, r9d; struct ISyncFilterInfo *
0x18002b2bd  mov     [rsp+78h+var_48], 0; int
0x18002b2c5  mov     r8, rbp; struct IForgottenKnowledge *
0x18002b2c8  mov     [rsp+78h+var_50], 0; unsigned __int8 *
0x18002b2d1  mov     rdx, r14; struct ISyncKnowledge *
0x18002b2d4  mov     [rsp+78h+var_58], 0; int
0x18002b2dc  mov     [rsp+78h+arg_0], 0
0x18002b2e8  call    ?CSyncChangeBatch_CreateInstance@@YAJPEAVIdParameters@@PEAUISyncKnowledge@@PEAUIForgottenKnowledge@@PEAUISyncFilterInfo@@HPEBEHPEAPEAX@Z; CSyncChangeBatch_CreateInstance(IdParameters *,ISyncKnowledge *,IForgottenKnowledge *,ISyncFilterInfo *,int,uchar const *,int,void * *)
0x18002b2ed  mov     edi, eax
0x18002b2ef  test    eax, eax
0x18002b2f1  js      short loc_18002B324
0x18002b2f3  mov     rbx, [rsp+78h+arg_0]
0x18002b2fb  lea     rdx, _GUID_70c64dee_380f_4c2e_8f70_31c55bd5f9b3
0x18002b302  mov     r8, rsi
0x18002b305  mov     rcx, rbx
0x18002b308  mov     rax, [rbx]
0x18002b30b  mov     rax, [rax]
0x18002b30e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b313  mov     edi, eax
0x18002b315  mov     rcx, rbx
0x18002b318  mov     rax, [rbx]
0x18002b31b  mov     rax, [rax+10h]
0x18002b31f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b324  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b32b  cmp     rcx, r12
0x18002b32e  jz      short loc_18002B35C
0x18002b330  test    byte ptr [rcx+1Ch], 2
0x18002b334  jz      short loc_18002B35C
0x18002b336  cmp     byte ptr [rcx+19h], 5
0x18002b33a  jb      short loc_18002B35C
0x18002b33c  mov     rcx, [rcx+10h]
0x18002b340  lea     r9, aCsyncservicesC_14; "CSyncServices::CreateChangeBatch"
0x18002b347  mov     edx, 27h ; '''
0x18002b34c  mov     [rsp+78h+var_58], edi
0x18002b350  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002b357  call    WPP_SF_sD
0x18002b35c  mov     eax, edi
0x18002b35e  add     rsp, 48h
0x18002b362  pop     r14
0x18002b364  pop     r12
0x18002b366  pop     rdi
0x18002b367  pop     rsi
0x18002b368  pop     rbp
0x18002b369  pop     rbx
0x18002b36a  retn
```
