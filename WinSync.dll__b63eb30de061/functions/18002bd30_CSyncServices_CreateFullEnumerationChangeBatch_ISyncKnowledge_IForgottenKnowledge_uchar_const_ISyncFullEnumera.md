# CSyncServices::CreateFullEnumerationChangeBatch(ISyncKnowledge *,IForgottenKnowledge *,uchar const *,ISyncFullEnumerationChangeBatch * *)

- ea: `0x18002bd30`
- end: `0x18002be7d`
- name: `?CreateFullEnumerationChangeBatch@CSyncServices@@UEAAJPEAUISyncKnowledge@@PEAUIForgottenKnowledge@@PEBEPEAPEAUISyncFullEnumerationChangeBatch@@@Z`
- size: `333`
- prototype: `__int64 __fastcall(CSyncServices *this, struct ISyncKnowledge *, struct IForgottenKnowledge *, const unsigned __int8 *, struct ISyncFullEnumerationChangeBatch **)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x18002be90`

## callees

- `0x18001a038`
- `0x18001ae20`
- `0x18002bd30`
- `0x18004dda4`
- `0x180094010`

## string_xrefs

- `0x18002bd6d`: `CSyncServices::CreateFullEnumerationChangeBatch`
- `0x18002be51`: `CSyncServices::CreateFullEnumerationChangeBatch`

## pseudocode

```c
__int64 __fastcall CSyncServices::CreateFullEnumerationChangeBatch(
        CSyncServices *this,
        struct ISyncKnowledge *a2,
        struct IForgottenKnowledge *a3,
        const unsigned __int8 *a4,
        struct ISyncFullEnumerationChangeBatch **a5)
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
      40,
      WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      "CSyncServices::CreateFullEnumerationChangeBatch");
    v9 = (PVOID *)WPP_GLOBAL_Control;
  }
  v10 = -2147217407;
  if ( *((_QWORD *)this + 6) )
  {
    v10 = -2147467261;
    if ( a5 )
    {
      if ( a3 )
      {
        v11 = (struct IdParameters *)*((_QWORD *)this + 6);
        v14 = 0;
        v10 = CSyncChangeBatch_CreateInstance(v11, a2, a3, 0, 1, a4, 0, &v14);
        if ( v10 >= 0 )
        {
          v12 = v14;
          v10 = (**(__int64 (__fastcall ***)(void *, GUID *, struct ISyncFullEnumerationChangeBatch **))v14)(
                  v14,
                  &GUID_ef64197d_4f44_4ea2_b355_4524713e3bed,
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
      41,
      (unsigned int)WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids,
      (unsigned int)"CSyncServices::CreateFullEnumerationChangeBatch",
      v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002bd30  push    rbx
0x18002bd32  push    rbp
0x18002bd33  push    rdi
0x18002bd34  push    r13
0x18002bd36  push    r14
0x18002bd38  push    r15
0x18002bd3a  sub     rsp, 48h
0x18002bd3e  mov     r14, r9
0x18002bd41  mov     rbx, r8
0x18002bd44  mov     r15, rdx
0x18002bd47  mov     rbp, rcx
0x18002bd4a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bd51  lea     r13, WPP_GLOBAL_Control
0x18002bd58  cmp     rcx, r13
0x18002bd5b  jz      short loc_18002BD8C
0x18002bd5d  test    byte ptr [rcx+1Ch], 2
0x18002bd61  jz      short loc_18002BD8C
0x18002bd63  cmp     byte ptr [rcx+19h], 5
0x18002bd67  jb      short loc_18002BD8C
0x18002bd69  mov     rcx, [rcx+10h]
0x18002bd6d  lea     r9, aCsyncservicesC_18; "CSyncServices::CreateFullEnumerationCha"...
0x18002bd74  mov     edx, 28h ; '('
0x18002bd79  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002bd80  call    WPP_SF_s
0x18002bd85  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bd8c  cmp     qword ptr [rbp+30h], 0
0x18002bd91  mov     edi, 80041001h
0x18002bd96  jz      loc_18002BE3C
0x18002bd9c  cmp     [rsp+78h+arg_20], 0
0x18002bda5  mov     edi, 80004003h
0x18002bdaa  jz      loc_18002BE3C
0x18002bdb0  test    rbx, rbx
0x18002bdb3  jz      loc_18002BE3C
0x18002bdb9  mov     rcx, [rbp+30h]; this
0x18002bdbd  lea     rax, [rsp+78h+arg_0]
0x18002bdc5  mov     [rsp+78h+var_40], rax; void **
0x18002bdca  xor     r9d, r9d; struct ISyncFilterInfo *
0x18002bdcd  mov     [rsp+78h+var_48], 0; int
0x18002bdd5  mov     r8, rbx; struct IForgottenKnowledge *
0x18002bdd8  mov     [rsp+78h+var_50], r14; unsigned __int8 *
0x18002bddd  mov     rdx, r15; struct ISyncKnowledge *
0x18002bde0  mov     [rsp+78h+var_58], 1; int
0x18002bde8  mov     [rsp+78h+arg_0], 0
0x18002bdf4  call    ?CSyncChangeBatch_CreateInstance@@YAJPEAVIdParameters@@PEAUISyncKnowledge@@PEAUIForgottenKnowledge@@PEAUISyncFilterInfo@@HPEBEHPEAPEAX@Z; CSyncChangeBatch_CreateInstance(IdParameters *,ISyncKnowledge *,IForgottenKnowledge *,ISyncFilterInfo *,int,uchar const *,int,void * *)
0x18002bdf9  mov     edi, eax
0x18002bdfb  test    eax, eax
0x18002bdfd  js      short loc_18002BE35
0x18002bdff  mov     rbx, [rsp+78h+arg_0]
0x18002be07  lea     rdx, _GUID_ef64197d_4f44_4ea2_b355_4524713e3bed
0x18002be0e  mov     r8, [rsp+78h+arg_20]
0x18002be16  mov     rcx, rbx
0x18002be19  mov     rax, [rbx]
0x18002be1c  mov     rax, [rax]
0x18002be1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be24  mov     edi, eax
0x18002be26  mov     rcx, rbx
0x18002be29  mov     rax, [rbx]
0x18002be2c  mov     rax, [rax+10h]
0x18002be30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be35  mov     rcx, cs:WPP_GLOBAL_Control
0x18002be3c  cmp     rcx, r13
0x18002be3f  jz      short loc_18002BE6D
0x18002be41  test    byte ptr [rcx+1Ch], 2
0x18002be45  jz      short loc_18002BE6D
0x18002be47  cmp     byte ptr [rcx+19h], 5
0x18002be4b  jb      short loc_18002BE6D
0x18002be4d  mov     rcx, [rcx+10h]
0x18002be51  lea     r9, aCsyncservicesC_18; "CSyncServices::CreateFullEnumerationCha"...
0x18002be58  mov     edx, 29h ; ')'
0x18002be5d  mov     [rsp+78h+var_58], edi
0x18002be61  lea     r8, WPP_3949be9dc30c34dae78cb18c6e9e78ff_Traceguids
0x18002be68  call    WPP_SF_sD
0x18002be6d  mov     eax, edi
0x18002be6f  add     rsp, 48h
0x18002be73  pop     r15
0x18002be75  pop     r14
0x18002be77  pop     r13
0x18002be79  pop     rdi
0x18002be7a  pop     rbp
0x18002be7b  pop     rbx
0x18002be7c  retn
```
