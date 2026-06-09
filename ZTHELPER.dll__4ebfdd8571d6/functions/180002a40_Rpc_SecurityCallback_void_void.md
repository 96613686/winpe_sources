# Rpc_SecurityCallback(void *,void *)

- ea: `0x180002a40`
- end: `0x180002a82`
- name: `?Rpc_SecurityCallback@@YAJPEAX0@Z`
- size: `66`
- prototype: `__int64 __fastcall(void *, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000292c`
- `0x180002a40`
- `0x180015094`

## pseudocode

```c
__int64 __fastcall Rpc_SecurityCallback(void *a1, void *a2)
{
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_q(1026, 14, WPP_a6e3050920603bba2dcfbddedbe1bd89_Traceguids, a2);
  return (unsigned int)Rpc_IsProtoLpc(a2) == 0 ? 5 : 0;
}

```

## disassembly

```asm
0x180002a40  push    rbx
0x180002a42  sub     rsp, 20h
0x180002a46  mov     rbx, rdx
0x180002a49  test    byte ptr cs:xmmword_18001F260, 4
0x180002a50  jz      short loc_180002A6B
0x180002a52  mov     edx, 0Eh
0x180002a57  lea     r8, WPP_a6e3050920603bba2dcfbddedbe1bd89_Traceguids
0x180002a5e  mov     ecx, 402h
0x180002a63  mov     r9, rbx
0x180002a66  call    WPP_SF_q
0x180002a6b  mov     rcx, rbx; Binding
0x180002a6e  call    ?Rpc_IsProtoLpc@@YAHPEAX@Z; Rpc_IsProtoLpc(void *)
0x180002a73  neg     eax
0x180002a75  sbb     eax, eax
0x180002a77  not     eax
0x180002a79  and     eax, 5
0x180002a7c  add     rsp, 20h
0x180002a80  pop     rbx
0x180002a81  retn
```
