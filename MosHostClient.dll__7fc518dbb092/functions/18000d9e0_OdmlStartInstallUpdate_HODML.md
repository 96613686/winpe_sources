# OdmlStartInstallUpdate(HODML__ *)

- ea: `0x18000d9e0`
- end: `0x18000da27`
- name: `?OdmlStartInstallUpdate@@YAJPEAUHODML__@@@Z`
- size: `71`
- prototype: `__int64 __fastcall(struct HODML__ *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180006214`
- `0x18000c864`
- `0x18000d9e0`

## pseudocode

```c
__int64 __fastcall OdmlStartInstallUpdate(struct HODML__ *a1)
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
    (void *)0x46,
    (unsigned int)"onecoreuap\\windows\\maps\\moshost\\client\\odmlclient.cpp",
    (const char *)(unsigned int)v1,
    v4);
  return v2;
}

```

## disassembly

```asm
0x18000d9e0  push    rbx; int
0x18000d9e2  sub     rsp, 20h
0x18000d9e6  mov     [rsp+28h+arg_0], rcx
0x18000d9eb  lea     rdx, [rsp+28h+arg_0]
0x18000d9f0  lea     rcx, OdmlSvcStartInstallUpdate
0x18000d9f7  call    ??$invoke_rpc_nothrow@A6AJPEAX@ZAEAPEAX@wil@@YAJA6AJPEAX@ZAEAPEAX@Z; wil::invoke_rpc_nothrow<long (&)(void *),void * &>(long (&)(void *),void * &)
0x18000d9fc  mov     ebx, eax
0x18000d9fe  test    eax, eax
0x18000da00  jns     short loc_18000DA1F
0x18000da02  mov     rcx, [rsp+28h]; this
0x18000da07  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\maps\\moshost\\cli"...
0x18000da0e  mov     r9d, eax; char *
0x18000da11  mov     edx, 46h ; 'F'; void *
0x18000da16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000da1b  mov     eax, ebx
0x18000da1d  jmp     short loc_18000DA21
0x18000da1f  xor     eax, eax
0x18000da21  add     rsp, 20h
0x18000da25  pop     rbx
0x18000da26  retn
```
