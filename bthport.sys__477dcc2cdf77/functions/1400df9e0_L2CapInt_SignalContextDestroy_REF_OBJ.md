# L2CapInt_SignalContextDestroy(_REF_OBJ *)

- ea: `0x1400df9e0`
- end: `0x1400dfa87`
- name: `?L2CapInt_SignalContextDestroy@@YAXPEAU_REF_OBJ@@@Z`
- size: `167`
- prototype: `void __fastcall(struct _REF_OBJ *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x140005b4c`
- `0x1400df9e0`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400dfa61`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400dfa61`
- `ntoskrnl!IoFreeMdl` at `0x1400dfa45`
- `ntoskrnl!IoFreeMdl` at `0x1400dfa45`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400dfa74`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400dfa74`

## pseudocode

```c
void __fastcall L2CapInt_SignalContextDestroy(struct _REF_OBJ *a1)
{
  void (__fastcall **p_DestroyFunction)(_REF_OBJ *); // rbx
  bool v2; // dl
  struct _MDL *v3; // rcx

  p_DestroyFunction = &a1[-10].DestroyFunction;
  v2 = (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_q(
    WPP_GLOBAL_Control->AttachedDevice,
    v2,
    1,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    5,
    156,
    (__int64)WPP_6ff04b5cc55f3e31603028274367341f_Traceguids,
    p_DestroyFunction);
  v3 = (struct _MDL *)p_DestroyFunction[14];
  if ( v3 )
    IoFreeMdl(v3);
  if ( *((int *)p_DestroyFunction + 9) >= 0 )
    ExFreePoolWithTag(p_DestroyFunction, 0);
  else
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)*p_DestroyFunction + 112), p_DestroyFunction);
}

```

## disassembly

```asm
0x1400df9e0  push    rbx
0x1400df9e2  sub     rsp, 50h
0x1400df9e6  lea     rbx, [rcx-0E8h]
0x1400df9ed  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400df9f4  mov     eax, [rcx+2Ch]
0x1400df9f7  test    al, 10h
0x1400df9f9  jz      short loc_1400DFA05
0x1400df9fb  cmp     byte ptr [rcx+29h], 4
0x1400df9ff  jb      short loc_1400DFA05
0x1400dfa01  mov     dl, 1
0x1400dfa03  jmp     short loc_1400DFA07
0x1400dfa05  xor     dl, dl
0x1400dfa07  mov     r9, [rcx+40h]
0x1400dfa0b  lea     rax, WPP_6ff04b5cc55f3e31603028274367341f_Traceguids
0x1400dfa12  mov     rcx, [rcx+18h]
0x1400dfa16  mov     r8b, 1
0x1400dfa19  mov     [rsp+58h+var_18], rbx
0x1400dfa1e  mov     [rsp+58h+var_20], rax
0x1400dfa23  mov     [rsp+58h+var_28], 9Ch
0x1400dfa2a  mov     [rsp+58h+var_30], 5
0x1400dfa32  mov     [rsp+58h+var_38], 4
0x1400dfa37  call    WPP_RECORDER_AND_TRACE_SF_q
0x1400dfa3c  mov     rcx, [rbx+70h]; Mdl
0x1400dfa40  test    rcx, rcx
0x1400dfa43  jz      short loc_1400DFA51
0x1400dfa45  call    cs:__imp_IoFreeMdl
0x1400dfa4c  nop     dword ptr [rax+rax+00h]
0x1400dfa51  cmp     dword ptr [rbx+24h], 0
0x1400dfa55  jge     short loc_1400DFA6F
0x1400dfa57  mov     rcx, [rbx]
0x1400dfa5a  mov     rdx, rbx; Entry
0x1400dfa5d  add     rcx, 70h ; 'p'; Lookaside
0x1400dfa61  call    cs:__imp_ExFreeToLookasideListEx
0x1400dfa68  nop     dword ptr [rax+rax+00h]
0x1400dfa6d  jmp     short loc_1400DFA80
0x1400dfa6f  xor     edx, edx; Tag
0x1400dfa71  mov     rcx, rbx; P
0x1400dfa74  call    cs:__imp_ExFreePoolWithTag
0x1400dfa7b  nop     dword ptr [rax+rax+00h]
0x1400dfa80  add     rsp, 50h
0x1400dfa84  pop     rbx
0x1400dfa85  retn
```
