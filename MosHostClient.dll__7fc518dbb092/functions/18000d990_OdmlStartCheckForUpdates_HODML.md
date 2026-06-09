# OdmlStartCheckForUpdates(HODML__ *)

- ea: `0x18000d990`
- end: `0x18000d9d7`
- name: `?OdmlStartCheckForUpdates@@YAJPEAUHODML__@@@Z`
- size: `71`
- prototype: `__int64 __fastcall(struct HODML__ *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180006214`
- `0x18000c864`
- `0x18000d990`

## pseudocode

```c
__int64 __fastcall OdmlStartCheckForUpdates(struct HODML__ *a1)
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
    (void *)0x3C,
    (unsigned int)"onecoreuap\\windows\\maps\\moshost\\client\\odmlclient.cpp",
    (const char *)(unsigned int)v1,
    v4);
  return v2;
}

```

## disassembly

```asm
0x18000d990  push    rbx; int
0x18000d992  sub     rsp, 20h
0x18000d996  mov     [rsp+28h+arg_0], rcx
0x18000d99b  lea     rdx, [rsp+28h+arg_0]
0x18000d9a0  lea     rcx, OdmlSvcStartCheckForUpdates
0x18000d9a7  call    ??$invoke_rpc_nothrow@A6AJPEAX@ZAEAPEAX@wil@@YAJA6AJPEAX@ZAEAPEAX@Z; wil::invoke_rpc_nothrow<long (&)(void *),void * &>(long (&)(void *),void * &)
0x18000d9ac  mov     ebx, eax
0x18000d9ae  test    eax, eax
0x18000d9b0  jns     short loc_18000D9CF
0x18000d9b2  mov     rcx, [rsp+28h]; this
0x18000d9b7  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\maps\\moshost\\cli"...
0x18000d9be  mov     r9d, eax; char *
0x18000d9c1  mov     edx, 3Ch ; '<'; void *
0x18000d9c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d9cb  mov     eax, ebx
0x18000d9cd  jmp     short loc_18000D9D1
0x18000d9cf  xor     eax, eax
0x18000d9d1  add     rsp, 20h
0x18000d9d5  pop     rbx
0x18000d9d6  retn
```
