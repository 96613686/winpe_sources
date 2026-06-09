# CmsTerminateProcess

- ea: `0x180009800`
- end: `0x180009856`
- name: `CmsTerminateProcess`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x18000230c`
- `0x1800066e4`
- `0x180009800`

## string_xrefs

- `0x180009836`: `onecore\base\gendrv\silos\clem\client\dll\api.cpp`

## pseudocode

```c
__int64 __fastcall CmsTerminateProcess(__int64 a1, __int64 *a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF
  __int64 v8; // [rsp+38h] [rbp+10h] BYREF

  v7 = *a2;
  v8 = *(_QWORD *)(a1 + 8);
  v2 = Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int *),void *,int * &>(
         (__int64 (__fastcall *)(_QWORD, _QWORD))CmsRpcClt_TerminateProcess,
         &v8,
         &v7);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x3A1,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\client\\dll\\api.cpp",
    (const char *)(unsigned int)v2,
    v5);
  return v3;
}

```

## disassembly

```asm
0x180009800  mov     r11, rsp
0x180009803  push    rbx; int
0x180009804  sub     rsp, 20h
0x180009808  mov     rax, [rdx]
0x18000980b  lea     r8, [r11+8]
0x18000980f  mov     [r11+8], rax
0x180009813  lea     rdx, [r11+10h]
0x180009817  mov     rax, [rcx+8]
0x18000981b  lea     rcx, CmsRpcClt_TerminateProcess
0x180009822  mov     [r11+10h], rax
0x180009826  call    ??$InvokeStubFunction@P6AJPEAXPEAH@ZPEAXAEAPEAH@Rpc@Manager@Container@@YAJP6AJPEAXPEAH@Z$$QEAPEAXAEAPEAH@Z; Container::Manager::Rpc::InvokeStubFunction<long (*)(void *,int *),void *,int * &>(long (*)(void *,int *),void * &&,int * &)
0x18000982b  mov     ebx, eax
0x18000982d  test    eax, eax
0x18000982f  jns     short loc_18000984E
0x180009831  mov     rcx, [rsp+28h]; this
0x180009836  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\cli"...
0x18000983d  mov     r9d, eax; char *
0x180009840  mov     edx, 3A1h; void *
0x180009845  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000984a  mov     eax, ebx
0x18000984c  jmp     short loc_180009850
0x18000984e  xor     eax, eax
0x180009850  add     rsp, 20h
0x180009854  pop     rbx
0x180009855  retn
```
