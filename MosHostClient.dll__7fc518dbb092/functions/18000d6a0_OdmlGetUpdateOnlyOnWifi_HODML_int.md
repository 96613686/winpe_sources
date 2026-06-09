# OdmlGetUpdateOnlyOnWifi(HODML__ *,int *)

- ea: `0x18000d6a0`
- end: `0x18000d6ef`
- name: `?OdmlGetUpdateOnlyOnWifi@@YAJPEAUHODML__@@PEAH@Z`
- size: `79`
- prototype: `__int64 __fastcall(struct HODML__ *, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180006214`
- `0x18000c954`
- `0x18000d6a0`

## pseudocode

```c
__int64 __fastcall OdmlGetUpdateOnlyOnWifi(struct HODML__ *a1, int *a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = wil::invoke_rpc_nothrow<long (&)(void *,int *),void * &,int * &>();
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xF2,
    (unsigned int)"onecoreuap\\windows\\maps\\moshost\\client\\odmlclient.cpp",
    (const char *)(unsigned int)v2,
    v5);
  return v3;
}

```

## disassembly

```asm
0x18000d6a0  mov     rax, rsp
0x18000d6a3  mov     [rax+10h], rdx
0x18000d6a7  push    rbx; int
0x18000d6a8  sub     rsp, 20h
0x18000d6ac  mov     [rax+8], rcx
0x18000d6b0  lea     r8, [rax+10h]
0x18000d6b4  lea     rcx, OdmlSvcGetUpdateOnlyOnWifi
0x18000d6bb  lea     rdx, [rax+8]
0x18000d6bf  call    ??$invoke_rpc_nothrow@A6AJPEAXPEAH@ZAEAPEAXAEAPEAH@wil@@YAJA6AJPEAXPEAH@ZAEAPEAXAEAPEAH@Z; wil::invoke_rpc_nothrow<long (&)(void *,int *),void * &,int * &>(long (&)(void *,int *),void * &,int * &)
0x18000d6c4  mov     ebx, eax
0x18000d6c6  test    eax, eax
0x18000d6c8  jns     short loc_18000D6E7
0x18000d6ca  mov     rcx, [rsp+28h]; this
0x18000d6cf  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\maps\\moshost\\cli"...
0x18000d6d6  mov     r9d, eax; char *
0x18000d6d9  mov     edx, 0F2h; void *
0x18000d6de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d6e3  mov     eax, ebx
0x18000d6e5  jmp     short loc_18000D6E9
0x18000d6e7  xor     eax, eax
0x18000d6e9  add     rsp, 20h
0x18000d6ed  pop     rbx
0x18000d6ee  retn
```
