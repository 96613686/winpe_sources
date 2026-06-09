# OdmlSetAutoUpdateEnabled(HODML__ *,int)

- ea: `0x18000d8d0`
- end: `0x18000d91e`
- name: `?OdmlSetAutoUpdateEnabled@@YAJPEAUHODML__@@H@Z`
- size: `78`
- prototype: `__int64 __fastcall(struct HODML__ *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180006214`
- `0x180008804`
- `0x18000d8d0`

## pseudocode

```c
__int64 __fastcall OdmlSetAutoUpdateEnabled(struct HODML__ *a1)
{
  int v1; // eax
  unsigned int v2; // ebx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = wil::invoke_rpc_nothrow<long (&)(void *,unsigned int),void * &,unsigned int &>();
  v2 = v1;
  if ( v1 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xCE,
    (unsigned int)"onecoreuap\\windows\\maps\\moshost\\client\\odmlclient.cpp",
    (const char *)(unsigned int)v1,
    v4);
  return v2;
}

```

## disassembly

```asm
0x18000d8d0  mov     rax, rsp
0x18000d8d3  mov     [rax+10h], edx
0x18000d8d6  push    rbx; int
0x18000d8d7  sub     rsp, 20h
0x18000d8db  mov     [rax+8], rcx
0x18000d8df  lea     r8, [rax+10h]
0x18000d8e3  lea     rcx, OdmlSvcSetAutoUpdateEnabled
0x18000d8ea  lea     rdx, [rax+8]
0x18000d8ee  call    ??$invoke_rpc_nothrow@A6AJPEAXI@ZAEAPEAXAEAI@wil@@YAJA6AJPEAXI@ZAEAPEAXAEAI@Z; wil::invoke_rpc_nothrow<long (&)(void *,uint),void * &,uint &>(long (&)(void *,uint),void * &,uint &)
0x18000d8f3  mov     ebx, eax
0x18000d8f5  test    eax, eax
0x18000d8f7  jns     short loc_18000D916
0x18000d8f9  mov     rcx, [rsp+28h]; this
0x18000d8fe  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\maps\\moshost\\cli"...
0x18000d905  mov     r9d, eax; char *
0x18000d908  mov     edx, 0CEh; void *
0x18000d90d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d912  mov     eax, ebx
0x18000d914  jmp     short loc_18000D918
0x18000d916  xor     eax, eax
0x18000d918  add     rsp, 20h
0x18000d91c  pop     rbx
0x18000d91d  retn
```
