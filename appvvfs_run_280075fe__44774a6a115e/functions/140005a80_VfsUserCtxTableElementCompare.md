# VfsUserCtxTableElementCompare

- ea: `0x140005a80`
- end: `0x140005b06`
- name: `VfsUserCtxTableElementCompare`
- size: `134`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140005a80`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140005acf`
- `ntoskrnl!RtlCompareMemory` at `0x140005acf`
- `ntoskrnl!RtlLengthSid` at `0x140005a98`
- `ntoskrnl!RtlLengthSid` at `0x140005aa9`
- `ntoskrnl!RtlLengthSid` at `0x140005a98`
- `ntoskrnl!RtlLengthSid` at `0x140005aa9`

## pseudocode

```c
__int64 __fastcall VfsUserCtxTableElementCompare(struct _RTL_AVL_TABLE *Table, PVOID FirstStruct, PVOID SecondStruct)
{
  SIZE_T v5; // rbx
  ULONG v6; // eax
  SIZE_T v8; // rax

  v5 = RtlLengthSid(FirstStruct);
  v6 = RtlLengthSid(SecondStruct);
  if ( (unsigned int)v5 < v6 )
    return 0;
  if ( (unsigned int)v5 > v6 )
    return 1;
  v8 = RtlCompareMemory(FirstStruct, SecondStruct, v5);
  if ( v8 == v5 )
    return 2;
  else
    return *((_BYTE *)FirstStruct + v8) >= *((_BYTE *)SecondStruct + v8);
}

```

## disassembly

```asm
0x140005a80  mov     [rsp+arg_0], rbx
0x140005a85  mov     [rsp+arg_8], rsi
0x140005a8a  push    rdi
0x140005a8b  sub     rsp, 20h
0x140005a8f  mov     rcx, rdx; Sid
0x140005a92  mov     rdi, r8
0x140005a95  mov     rsi, rdx
0x140005a98  call    cs:__imp_RtlLengthSid
0x140005a9f  nop     dword ptr [rax+rax+00h]
0x140005aa4  mov     rcx, rdi; Sid
0x140005aa7  mov     ebx, eax
0x140005aa9  call    cs:__imp_RtlLengthSid
0x140005ab0  nop     dword ptr [rax+rax+00h]
0x140005ab5  cmp     ebx, eax
0x140005ab7  jnb     short loc_140005ABD
0x140005ab9  xor     eax, eax
0x140005abb  jmp     short loc_140005AF5
0x140005abd  jbe     short loc_140005AC6
0x140005abf  mov     eax, 1
0x140005ac4  jmp     short loc_140005AF5
0x140005ac6  mov     r8, rbx; Length
0x140005ac9  mov     rdx, rdi; Source2
0x140005acc  mov     rcx, rsi; Source1
0x140005acf  call    cs:__imp_RtlCompareMemory
0x140005ad6  nop     dword ptr [rax+rax+00h]
0x140005adb  mov     rdx, rax
0x140005ade  cmp     rax, rbx
0x140005ae1  jnz     short loc_140005AEA
0x140005ae3  mov     eax, 2
0x140005ae8  jmp     short loc_140005AF5
0x140005aea  mov     cl, [rdx+rdi]
0x140005aed  xor     eax, eax
0x140005aef  cmp     [rdx+rsi], cl
0x140005af2  setnb   al
0x140005af5  mov     rbx, [rsp+28h+arg_0]
0x140005afa  mov     rsi, [rsp+28h+arg_8]
0x140005aff  add     rsp, 20h
0x140005b03  pop     rdi
0x140005b04  retn
```
