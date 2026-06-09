# CSyncServices::CreateFilteredEnumerationChangeBatch(ISyncFilterInfo *,ISyncKnowledge *,IForgottenKnowledge *,ISyncChangeBatch * *)

- ea: `0x18002b960`
- end: `0x18002baba`
- name: `?CreateFilteredEnumerationChangeBatch@CSyncServices@@UEAAJPEAUISyncFilterInfo@@PEAUISyncKnowledge@@PEAUIForgottenKnowledge@@PEAPEAUISyncChangeBatch@@@Z`
- size: `346`
- prototype: `__int64 __fastcall(CSyncServices *this, struct ISyncFilterInfo *, struct ISyncKnowledge *, struct IForgottenKnowledge *, struct ISyncChangeBatch **)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18002b960`
- `0x18004dda4`
- `0x180094010`

## string_xrefs

- `0x18002b99d`: `CSyncServices::CreateFilteredEnumerationChangeBatch`
- `0x18002ba8e`: `CSyncServices::CreateFilteredEnumerationChangeBatch`

## pseudocode

```c
__int64 __fastcall CSyncServices::CreateFilteredEnumerationChangeBatch(
        CSyncServices *this,
        struct ISyncFilterInfo *a2,
        struct ISyncKnowledge *a3,
        struct IForgottenKnowledge *a4,
        struct ISyncChangeBatch **a5)
{
  PVOID *v9; // rcx
  int v10; // edi
  struct IdParameters *v11; // rcx
  void *v12; // rbx
  void *v14; // [rsp+80h] [rbp+8h] BYREF

  v9 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      "CSyncServices::CreateFilteredEnumerationChangeBatch");
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  v10 = -2147217407;
  if ( *((_QWORD *)this + 6) )
  {
    v10 = -2147467261;
    if ( a5 )
    {
      if ( a3 && a2 )
      {
        v11 = (struct IdParameters *)*((_QWORD *)this + 6);
        v14 = 0;
        v10 = CSyncChangeBatch_CreateInstance(v11, a3, a4, a2, 0, 0, 0, &v14);
        if ( v10 >= 0 )
        {
          v12 = v14;
          v10 = (**(__int64 (__fastcall ***)(void *, GUID *, struct ISyncChangeBatch **))v14)(
                  v14,
                  &GUID_70c64dee_380f_4c2e_8f70_31c55bd5f9b3,
                  a5);
          (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 16LL))(v12);
        }
        v9 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
  }
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 2) != 0 && *((_BYTE *)v9 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v9[2],
      23,
      (unsigned int)WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      (unsigned int)"CSyncServices::CreateFilteredEnumerationChangeBatch",
      v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002b960  push    rbx
0x18002b962  push    rbp
0x18002b963  push    rdi
0x18002b964  push    r13
0x18002b966  push    r14
0x18002b968  push    r15
0x18002b96a  sub     rsp, 48h
0x18002b96e  mov     r15, r9
0x18002b971  mov     rbx, r8
0x18002b974  mov     rbp, rdx
0x18002b977  mov     r14, rcx
0x18002b97a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b981  lea     r13, WPP_GLOBAL_Control
0x18002b988  cmp     rcx, r13
0x18002b98b  jz      short loc_18002B9BC
0x18002b98d  test    byte ptr [rcx+1Ch], 2
0x18002b991  jz      short loc_18002B9BC
0x18002b993  cmp     byte ptr [rcx+19h], 5
0x18002b997  jb      short loc_18002B9BC
0x18002b999  mov     rcx, [rcx+10h]
0x18002b99d  lea     r9, aCsyncservicesC_16; "CSyncServices::CreateFilteredEnumeratio"...
0x18002b9a4  mov     edx, 16h
0x18002b9a9  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002b9b0  call    WPP_SF_s
0x18002b9b5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b9bc  cmp     qword ptr [r14+30h], 0
0x18002b9c1  mov     edi, 80041001h
0x18002b9c6  jz      loc_18002BA79
0x18002b9cc  cmp     [rsp+78h+arg_20], 0
0x18002b9d5  mov     edi, 80004003h
0x18002b9da  jz      loc_18002BA79
0x18002b9e0  test    rbx, rbx
0x18002b9e3  jz      loc_18002BA79
0x18002b9e9  test    rbp, rbp
0x18002b9ec  jz      loc_18002BA79
0x18002b9f2  mov     rcx, [r14+30h]; this
0x18002b9f6  lea     rax, [rsp+78h+arg_0]
0x18002b9fe  mov     [rsp+78h+var_40], rax; void **
0x18002ba03  mov     r9, rbp; struct ISyncFilterInfo *
0x18002ba06  mov     [rsp+78h+var_48], 0; int
0x18002ba0e  mov     r8, r15; struct IForgottenKnowledge *
0x18002ba11  mov     [rsp+78h+var_50], 0; unsigned __int8 *
0x18002ba1a  mov     rdx, rbx; struct ISyncKnowledge *
0x18002ba1d  mov     [rsp+78h+var_58], 0; int
0x18002ba25  mov     [rsp+78h+arg_0], 0
0x18002ba31  call    ?CSyncChangeBatch_CreateInstance@@YAJPEAVIdParameters@@PEAUISyncKnowledge@@PEAUIForgottenKnowledge@@PEAUISyncFilterInfo@@HPEBEHPEAPEAX@Z; CSyncChangeBatch_CreateInstance(IdParameters *,ISyncKnowledge *,IForgottenKnowledge *,ISyncFilterInfo *,int,uchar const *,int,void * *)
0x18002ba36  mov     edi, eax
0x18002ba38  test    eax, eax
0x18002ba3a  js      short loc_18002BA72
0x18002ba3c  mov     rbx, [rsp+78h+arg_0]
0x18002ba44  lea     rdx, _GUID_70c64dee_380f_4c2e_8f70_31c55bd5f9b3
0x18002ba4b  mov     r8, [rsp+78h+arg_20]
0x18002ba53  mov     rcx, rbx
0x18002ba56  mov     rax, [rbx]
0x18002ba59  mov     rax, [rax]
0x18002ba5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba61  mov     edi, eax
0x18002ba63  mov     rcx, rbx
0x18002ba66  mov     rax, [rbx]
0x18002ba69  mov     rax, [rax+10h]
0x18002ba6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba72  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ba79  cmp     rcx, r13
0x18002ba7c  jz      short loc_18002BAAA
0x18002ba7e  test    byte ptr [rcx+1Ch], 2
0x18002ba82  jz      short loc_18002BAAA
0x18002ba84  cmp     byte ptr [rcx+19h], 5
0x18002ba88  jb      short loc_18002BAAA
0x18002ba8a  mov     rcx, [rcx+10h]
0x18002ba8e  lea     r9, aCsyncservicesC_16; "CSyncServices::CreateFilteredEnumeratio"...
0x18002ba95  mov     edx, 17h
0x18002ba9a  mov     [rsp+78h+var_58], edi
0x18002ba9e  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002baa5  call    WPP_SF_sD
0x18002baaa  mov     eax, edi
0x18002baac  add     rsp, 48h
0x18002bab0  pop     r15
0x18002bab2  pop     r14
0x18002bab4  pop     r13
0x18002bab6  pop     rdi
0x18002bab7  pop     rbp
0x18002bab8  pop     rbx
0x18002bab9  retn
```
