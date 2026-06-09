# CSyncServices::CreateFilteredFullEnumerationChangeBatch(ISyncFilterInfo *,ISyncKnowledge *,IForgottenKnowledge *,uchar const *,ISyncFullEnumerationChangeBatch * *)

- ea: `0x18002bac0`
- end: `0x18002bc1e`
- name: `?CreateFilteredFullEnumerationChangeBatch@CSyncServices@@UEAAJPEAUISyncFilterInfo@@PEAUISyncKnowledge@@PEAUIForgottenKnowledge@@PEBEPEAPEAUISyncFullEnumerationChangeBatch@@@Z`
- size: `350`
- prototype: `__int64 __fastcall(CSyncServices *this, struct ISyncFilterInfo *, struct ISyncKnowledge *, struct IForgottenKnowledge *, unsigned __int8 *, struct ISyncFullEnumerationChangeBatch **)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18002bac0`
- `0x18004dda4`
- `0x180094010`

## string_xrefs

- `0x18002bafd`: `CSyncServices::CreateFilteredFullEnumerationChangeBatch`
- `0x18002bbf2`: `CSyncServices::CreateFilteredFullEnumerationChangeBatch`

## pseudocode

```c
__int64 __fastcall CSyncServices::CreateFilteredFullEnumerationChangeBatch(
        CSyncServices *this,
        struct ISyncFilterInfo *a2,
        struct ISyncKnowledge *a3,
        struct IForgottenKnowledge *a4,
        unsigned __int8 *a5,
        struct ISyncFullEnumerationChangeBatch **a6)
{
  PVOID *v10; // rcx
  int v11; // edi
  struct IdParameters *v12; // rcx
  void *v13; // rbx
  void *v15; // [rsp+80h] [rbp+8h] BYREF

  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      "CSyncServices::CreateFilteredFullEnumerationChangeBatch");
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  v11 = -2147217407;
  if ( *((_QWORD *)this + 6) )
  {
    v11 = -2147467261;
    if ( a6 )
    {
      if ( a4 && a2 )
      {
        v12 = (struct IdParameters *)*((_QWORD *)this + 6);
        v15 = 0;
        v11 = CSyncChangeBatch_CreateInstance(v12, a3, a4, a2, 1, a5, 0, &v15);
        if ( v11 >= 0 )
        {
          v13 = v15;
          v11 = (**(__int64 (__fastcall ***)(void *, GUID *, struct ISyncFullEnumerationChangeBatch **))v15)(
                  v15,
                  &GUID_ef64197d_4f44_4ea2_b355_4524713e3bed,
                  a6);
          (*(void (__fastcall **)(void *))(*(_QWORD *)v13 + 16LL))(v13);
        }
        v10 = (PVOID *)WPP_GLOBAL_Control;
      }
    }
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 2) != 0 && *((_BYTE *)v10 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v10[2],
      25,
      (unsigned int)WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      (unsigned int)"CSyncServices::CreateFilteredFullEnumerationChangeBatch",
      v11);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18002bac0  push    rbx
0x18002bac2  push    rbp
0x18002bac3  push    rdi
0x18002bac4  push    r13
0x18002bac6  push    r14
0x18002bac8  push    r15
0x18002baca  sub     rsp, 48h
0x18002bace  mov     rbx, r9
0x18002bad1  mov     r15, r8
0x18002bad4  mov     rbp, rdx
0x18002bad7  mov     r14, rcx
0x18002bada  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bae1  lea     r13, WPP_GLOBAL_Control
0x18002bae8  cmp     rcx, r13
0x18002baeb  jz      short loc_18002BB1C
0x18002baed  test    byte ptr [rcx+1Ch], 2
0x18002baf1  jz      short loc_18002BB1C
0x18002baf3  cmp     byte ptr [rcx+19h], 5
0x18002baf7  jb      short loc_18002BB1C
0x18002baf9  mov     rcx, [rcx+10h]
0x18002bafd  lea     r9, aCsyncservicesC; "CSyncServices::CreateFilteredFullEnumer"...
0x18002bb04  mov     edx, 18h
0x18002bb09  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002bb10  call    WPP_SF_s
0x18002bb15  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bb1c  cmp     qword ptr [r14+30h], 0
0x18002bb21  mov     edi, 80041001h
0x18002bb26  jz      loc_18002BBDD
0x18002bb2c  cmp     [rsp+78h+arg_28], 0
0x18002bb35  mov     edi, 80004003h
0x18002bb3a  jz      loc_18002BBDD
0x18002bb40  test    rbx, rbx
0x18002bb43  jz      loc_18002BBDD
0x18002bb49  test    rbp, rbp
0x18002bb4c  jz      loc_18002BBDD
0x18002bb52  mov     rcx, [r14+30h]; this
0x18002bb56  lea     rax, [rsp+78h+arg_0]
0x18002bb5e  mov     [rsp+78h+var_40], rax; void **
0x18002bb63  mov     r9, rbp; struct ISyncFilterInfo *
0x18002bb66  mov     rax, [rsp+78h+arg_20]
0x18002bb6e  mov     r8, rbx; struct IForgottenKnowledge *
0x18002bb71  mov     [rsp+78h+var_48], 0; int
0x18002bb79  mov     rdx, r15; struct ISyncKnowledge *
0x18002bb7c  mov     [rsp+78h+var_50], rax; unsigned __int8 *
0x18002bb81  mov     [rsp+78h+var_58], 1; int
0x18002bb89  mov     [rsp+78h+arg_0], 0
0x18002bb95  call    ?CSyncChangeBatch_CreateInstance@@YAJPEAVIdParameters@@PEAUISyncKnowledge@@PEAUIForgottenKnowledge@@PEAUISyncFilterInfo@@HPEBEHPEAPEAX@Z; CSyncChangeBatch_CreateInstance(IdParameters *,ISyncKnowledge *,IForgottenKnowledge *,ISyncFilterInfo *,int,uchar const *,int,void * *)
0x18002bb9a  mov     edi, eax
0x18002bb9c  test    eax, eax
0x18002bb9e  js      short loc_18002BBD6
0x18002bba0  mov     rbx, [rsp+78h+arg_0]
0x18002bba8  lea     rdx, _GUID_ef64197d_4f44_4ea2_b355_4524713e3bed
0x18002bbaf  mov     r8, [rsp+78h+arg_28]
0x18002bbb7  mov     rcx, rbx
0x18002bbba  mov     rax, [rbx]
0x18002bbbd  mov     rax, [rax]
0x18002bbc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bbc5  mov     edi, eax
0x18002bbc7  mov     rcx, rbx
0x18002bbca  mov     rax, [rbx]
0x18002bbcd  mov     rax, [rax+10h]
0x18002bbd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bbd6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bbdd  cmp     rcx, r13
0x18002bbe0  jz      short loc_18002BC0E
0x18002bbe2  test    byte ptr [rcx+1Ch], 2
0x18002bbe6  jz      short loc_18002BC0E
0x18002bbe8  cmp     byte ptr [rcx+19h], 5
0x18002bbec  jb      short loc_18002BC0E
0x18002bbee  mov     rcx, [rcx+10h]
0x18002bbf2  lea     r9, aCsyncservicesC; "CSyncServices::CreateFilteredFullEnumer"...
0x18002bbf9  mov     edx, 19h
0x18002bbfe  mov     [rsp+78h+var_58], edi
0x18002bc02  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002bc09  call    WPP_SF_sD
0x18002bc0e  mov     eax, edi
0x18002bc10  add     rsp, 48h
0x18002bc14  pop     r15
0x18002bc16  pop     r14
0x18002bc18  pop     r13
0x18002bc1a  pop     rdi
0x18002bc1b  pop     rbp
0x18002bc1c  pop     rbx
0x18002bc1d  retn
```
