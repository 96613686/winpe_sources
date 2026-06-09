# CopyFileExWProgressRoutine(_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,_LARGE_INTEGER,ulong,ulong,void *,void *,void *)

- ea: `0x14001e540`
- end: `0x14001e59e`
- name: `?CopyFileExWProgressRoutine@@YAKT_LARGE_INTEGER@@000KKPEAX11@Z`
- size: `94`
- prototype: `unsigned int __fastcall(union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, union _LARGE_INTEGER, unsigned int, unsigned int, void *, void *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops`

## callees

- `0x14001da4c`
- `0x14001e540`

## import_xrefs

- `RPCRT4!RpcServerTestCancel` at `0x14001e587`
- `RPCRT4!RpcServerTestCancel` at `0x14001e587`

## pseudocode

```c
__int64 __fastcall CopyFileExWProgressRoutine(
        union _LARGE_INTEGER a1,
        union _LARGE_INTEGER a2,
        union _LARGE_INTEGER a3,
        union _LARGE_INTEGER a4,
        unsigned int a5,
        unsigned int a6,
        void *a7,
        void *a8,
        RPC_BINDING_HANDLE *a9)
{
  if ( !a9 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 35, &WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids);
    return 1;
  }
  if ( !RpcServerTestCancel(a9[1]) )
  {
    *(_BYTE *)a9 = 1;
    return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x14001e540  push    rbx
0x14001e542  sub     rsp, 20h
0x14001e546  mov     rbx, [rsp+28h+arg_40]
0x14001e54b  test    rbx, rbx
0x14001e54e  jnz     short loc_14001E583
0x14001e550  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e557  lea     rax, WPP_GLOBAL_Control
0x14001e55e  cmp     rcx, rax
0x14001e561  jz      short loc_14001E57C
0x14001e563  test    byte ptr [rcx+1Ch], 1
0x14001e567  jz      short loc_14001E57C
0x14001e569  mov     rcx, [rcx+10h]
0x14001e56d  lea     edx, [rbx+23h]
0x14001e570  lea     r8, WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids
0x14001e577  call    WPP_SF_
0x14001e57c  mov     eax, 1
0x14001e581  jmp     short loc_14001E598
0x14001e583  mov     rcx, [rbx+8]; BindingHandle
0x14001e587  call    cs:__imp_RpcServerTestCancel
0x14001e58d  test    eax, eax
0x14001e58f  jnz     short loc_14001E596
0x14001e591  mov     byte ptr [rbx], 1
0x14001e594  jmp     short loc_14001E57C
0x14001e596  xor     eax, eax
0x14001e598  add     rsp, 20h
0x14001e59c  pop     rbx
0x14001e59d  retn
```
