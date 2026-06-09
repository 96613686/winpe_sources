# CopyFile2ProgressRoutine(COPYFILE2_MESSAGE const *,void *)

- ea: `0x14001e4e0`
- end: `0x14001e53c`
- name: `?CopyFile2ProgressRoutine@@YA?AW4_COPYFILE2_MESSAGE_ACTION@@PEBUCOPYFILE2_MESSAGE@@PEAX@Z`
- size: `92`
- prototype: `enum _COPYFILE2_MESSAGE_ACTION __fastcall(const struct COPYFILE2_MESSAGE *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x14001da4c`
- `0x14001e4e0`

## import_xrefs

- `RPCRT4!RpcServerTestCancel` at `0x14001e525`
- `RPCRT4!RpcServerTestCancel` at `0x14001e525`

## pseudocode

```c
__int64 __fastcall CopyFile2ProgressRoutine(const struct COPYFILE2_MESSAGE *a1, RPC_BINDING_HANDLE *a2)
{
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids);
    return 1;
  }
  if ( !RpcServerTestCancel(a2[1]) )
  {
    *(_BYTE *)a2 = 1;
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x14001e4e0  push    rbx
0x14001e4e2  sub     rsp, 20h
0x14001e4e6  mov     rbx, rdx
0x14001e4e9  test    rdx, rdx
0x14001e4ec  jnz     short loc_14001E521
0x14001e4ee  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e4f5  lea     rax, WPP_GLOBAL_Control
0x14001e4fc  cmp     rcx, rax
0x14001e4ff  jz      short loc_14001E51A
0x14001e501  test    byte ptr [rcx+1Ch], 1
0x14001e505  jz      short loc_14001E51A
0x14001e507  mov     rcx, [rcx+10h]
0x14001e50b  lea     edx, [rbx+24h]
0x14001e50e  lea     r8, WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids
0x14001e515  call    WPP_SF_
0x14001e51a  mov     eax, 1
0x14001e51f  jmp     short loc_14001E536
0x14001e521  mov     rcx, [rdx+8]; BindingHandle
0x14001e525  call    cs:__imp_RpcServerTestCancel
0x14001e52b  test    eax, eax
0x14001e52d  jnz     short loc_14001E534
0x14001e52f  mov     byte ptr [rbx], 1
0x14001e532  jmp     short loc_14001E51A
0x14001e534  xor     eax, eax
0x14001e536  add     rsp, 20h
0x14001e53a  pop     rbx
0x14001e53b  retn
```
