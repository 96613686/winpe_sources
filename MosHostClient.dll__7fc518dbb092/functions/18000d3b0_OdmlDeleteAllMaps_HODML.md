# OdmlDeleteAllMaps(HODML__ *)

- ea: `0x18000d3b0`
- end: `0x18000d3f7`
- name: `?OdmlDeleteAllMaps@@YAJPEAUHODML__@@@Z`
- size: `71`
- prototype: `__int64 __fastcall(struct HODML__ *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180006214`
- `0x18000c864`
- `0x18000d3b0`

## pseudocode

```c
__int64 __fastcall OdmlDeleteAllMaps(struct HODML__ *a1)
{
  int v1; // eax
  unsigned int v2; // ebx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = wil::invoke_rpc_nothrow<long (&)(void *),void * &>();
  v2 = v1;
  if ( v1 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xB5,
    (unsigned int)"onecoreuap\\windows\\maps\\moshost\\client\\odmlclient.cpp",
    (const char *)(unsigned int)v1,
    v4);
  return v2;
}

```

## disassembly

```asm
0x18000d3b0  push    rbx; int
0x18000d3b2  sub     rsp, 20h
0x18000d3b6  mov     [rsp+28h+arg_0], rcx
0x18000d3bb  lea     rdx, [rsp+28h+arg_0]
0x18000d3c0  lea     rcx, OdmlSvcDeleteAllMaps
0x18000d3c7  call    ??$invoke_rpc_nothrow@A6AJPEAX@ZAEAPEAX@wil@@YAJA6AJPEAX@ZAEAPEAX@Z; wil::invoke_rpc_nothrow<long (&)(void *),void * &>(long (&)(void *),void * &)
0x18000d3cc  mov     ebx, eax
0x18000d3ce  test    eax, eax
0x18000d3d0  jns     short loc_18000D3EF
0x18000d3d2  mov     rcx, [rsp+28h]; this
0x18000d3d7  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\maps\\moshost\\cli"...
0x18000d3de  mov     r9d, eax; char *
0x18000d3e1  mov     edx, 0B5h; void *
0x18000d3e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d3eb  mov     eax, ebx
0x18000d3ed  jmp     short loc_18000D3F1
0x18000d3ef  xor     eax, eax
0x18000d3f1  add     rsp, 20h
0x18000d3f5  pop     rbx
0x18000d3f6  retn
```
