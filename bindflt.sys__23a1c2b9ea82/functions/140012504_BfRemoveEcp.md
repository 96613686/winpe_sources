# BfRemoveEcp

- ea: `0x140012504`
- end: `0x140012568`
- name: `BfRemoveEcp`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140022e5c`

## callees

- `0x140012504`

## import_xrefs

- `FLTMGR!FltRemoveExtraCreateParameter` at `0x140012533`
- `FLTMGR!FltRemoveExtraCreateParameter` at `0x140012533`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14001254e`
- `FLTMGR!FltFreeExtraCreateParameter` at `0x14001254e`

## pseudocode

```c
__int64 __fastcall BfRemoveEcp(__int64 a1, struct _ECP_LIST *a2, const GUID *a3)
{
  struct _FLT_FILTER *v4; // rcx
  NTSTATUS v5; // ebx
  ULONG v7; // [rsp+40h] [rbp+8h] BYREF
  PVOID EcpContext; // [rsp+58h] [rbp+20h] BYREF

  EcpContext = 0;
  v4 = *(struct _FLT_FILTER **)(a1 + 8);
  v7 = 0;
  v5 = FltRemoveExtraCreateParameter(v4, a2, a3, &EcpContext, &v7);
  if ( v5 >= 0 )
    FltFreeExtraCreateParameter(*(PFLT_FILTER *)(a1 + 8), EcpContext);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140012504  mov     r11, rsp
0x140012507  mov     [r11+10h], rbx
0x14001250b  push    rdi
0x14001250c  sub     rsp, 30h
0x140012510  mov     rdi, rcx
0x140012513  mov     qword ptr [r11+20h], 0
0x14001251b  mov     rcx, [rcx+8]; Filter
0x14001251f  lea     rax, [r11+8]
0x140012523  lea     r9, [r11+20h]; EcpContext
0x140012527  mov     [r11-18h], rax
0x14001252b  mov     [rsp+38h+arg_0], 0
0x140012533  call    cs:__imp_FltRemoveExtraCreateParameter
0x14001253a  nop     dword ptr [rax+rax+00h]
0x14001253f  mov     ebx, eax
0x140012541  test    eax, eax
0x140012543  js      short loc_14001255A
0x140012545  mov     rdx, [rsp+38h+EcpContext]; EcpContext
0x14001254a  mov     rcx, [rdi+8]; Filter
0x14001254e  call    cs:__imp_FltFreeExtraCreateParameter
0x140012555  nop     dword ptr [rax+rax+00h]
0x14001255a  mov     eax, ebx
0x14001255c  mov     rbx, [rsp+38h+arg_8]
0x140012561  add     rsp, 30h
0x140012565  pop     rdi
0x140012566  retn
```
