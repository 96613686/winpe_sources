# OdmlSetUpdateOnlyOnWifi(HODML__ *,int)

- ea: `0x18000d930`
- end: `0x18000d97e`
- name: `?OdmlSetUpdateOnlyOnWifi@@YAJPEAUHODML__@@H@Z`
- size: `78`
- prototype: `__int64 __fastcall(struct HODML__ *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x180006214`
- `0x180008804`
- `0x18000d930`

## pseudocode

```c
__int64 __fastcall OdmlSetUpdateOnlyOnWifi(struct HODML__ *a1)
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
    (void *)0xE6,
    (unsigned int)"onecoreuap\\windows\\maps\\moshost\\client\\odmlclient.cpp",
    (const char *)(unsigned int)v1,
    v4);
  return v2;
}

```

## disassembly

```asm
0x18000d930  mov     rax, rsp
0x18000d933  mov     [rax+10h], edx
0x18000d936  push    rbx; int
0x18000d937  sub     rsp, 20h
0x18000d93b  mov     [rax+8], rcx
0x18000d93f  lea     r8, [rax+10h]
0x18000d943  lea     rcx, OdmlSvcSetUpdateOnlyOnWifi
0x18000d94a  lea     rdx, [rax+8]
0x18000d94e  call    ??$invoke_rpc_nothrow@A6AJPEAXI@ZAEAPEAXAEAI@wil@@YAJA6AJPEAXI@ZAEAPEAXAEAI@Z; wil::invoke_rpc_nothrow<long (&)(void *,uint),void * &,uint &>(long (&)(void *,uint),void * &,uint &)
0x18000d953  mov     ebx, eax
0x18000d955  test    eax, eax
0x18000d957  jns     short loc_18000D976
0x18000d959  mov     rcx, [rsp+28h]; this
0x18000d95e  lea     r8, aOnecoreuapWind_5; "onecoreuap\\windows\\maps\\moshost\\cli"...
0x18000d965  mov     r9d, eax; char *
0x18000d968  mov     edx, 0E6h; void *
0x18000d96d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d972  mov     eax, ebx
0x18000d974  jmp     short loc_18000D978
0x18000d976  xor     eax, eax
0x18000d978  add     rsp, 20h
0x18000d97c  pop     rbx
0x18000d97d  retn
```
