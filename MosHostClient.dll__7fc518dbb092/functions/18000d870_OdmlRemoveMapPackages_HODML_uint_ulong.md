# OdmlRemoveMapPackages(HODML__ *,uint *,ulong)

- ea: `0x18000d870`
- end: `0x18000d8c7`
- name: `?OdmlRemoveMapPackages@@YAJPEAUHODML__@@PEAIK@Z`
- size: `87`
- prototype: `__int64 __fastcall(struct HODML__ *, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180006214`
- `0x18000895c`
- `0x18000d870`

## pseudocode

```c
__int64 __fastcall OdmlRemoveMapPackages(struct HODML__ *a1, unsigned int *a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = wil::invoke_rpc_nothrow<long (&)(void *,unsigned short *,unsigned long),void * &,unsigned short * &,unsigned long &>();
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x9F,
    (unsigned int)"onecoreuap\\windows\\maps\\moshost\\client\\odmlclient.cpp",
    (const char *)(unsigned int)v2,
    v5);
  return v3;
}

```

## disassembly

```asm
0x18000d870  mov     rax, rsp
0x18000d873  mov     [rax+18h], r8d
0x18000d877  mov     [rax+10h], rdx
0x18000d87b  push    rbx; int
0x18000d87c  sub     rsp, 20h
0x18000d880  mov     [rax+8], rcx
0x18000d884  lea     r9, [rax+18h]
0x18000d888  lea     rcx, OdmlSvcRemoveMapPackages
0x18000d88f  lea     r8, [rax+10h]
0x18000d893  lea     rdx, [rax+8]
0x18000d897  call    ??$invoke_rpc_nothrow@A6AJPEAXPEAGK@ZAEAPEAXAEAPEAGAEAK@wil@@YAJA6AJPEAXPEAGK@ZAEAPEAXAEAPEAGAEAK@Z; wil::invoke_rpc_nothrow<long (&)(void *,ushort *,ulong),void * &,ushort * &,ulong &>(long (&)(void *,ushort *,ulong),void * &,ushort * &,ulong &)
0x18000d89c  mov     ebx, eax
0x18000d89e  test    eax, eax
0x18000d8a0  jns     short loc_18000D8BF
0x18000d8a2  mov     rcx, [rsp+28h]; this
0x18000d8a7  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\maps\\moshost\\cli"...
0x18000d8ae  mov     r9d, eax; char *
0x18000d8b1  mov     edx, 9Fh; void *
0x18000d8b6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d8bb  mov     eax, ebx
0x18000d8bd  jmp     short loc_18000D8C1
0x18000d8bf  xor     eax, eax
0x18000d8c1  add     rsp, 20h
0x18000d8c5  pop     rbx
0x18000d8c6  retn
```
