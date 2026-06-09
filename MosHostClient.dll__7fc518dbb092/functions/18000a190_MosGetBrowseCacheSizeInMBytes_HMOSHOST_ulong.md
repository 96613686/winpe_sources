# MosGetBrowseCacheSizeInMBytes(HMOSHOST__ *,ulong *)

- ea: `0x18000a190`
- end: `0x18000a1f6`
- name: `?MosGetBrowseCacheSizeInMBytes@@YAJPEAUHMOSHOST__@@PEAK@Z`
- size: `102`
- prototype: `__int64 __fastcall(struct HMOSHOST__ *, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180006214`
- `0x180008a44`
- `0x18000a190`

## pseudocode

```c
__int64 __fastcall MosGetBrowseCacheSizeInMBytes(struct HMOSHOST__ *a1, unsigned int *a2)
{
  __int64 v2; // rdx
  int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !a1 )
  {
    v2 = 134;
LABEL_3:
    v3 = -2147467261;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v2,
      (unsigned int)"onecoreuap\\windows\\maps\\moshost\\client\\moshostclient.cpp",
      (const char *)(unsigned int)v3,
      v5);
    return (unsigned int)v3;
  }
  if ( !a2 )
  {
    v2 = 135;
    goto LABEL_3;
  }
  v3 = wil::invoke_rpc_nothrow<long (&)(void *,unsigned long *),void * &,unsigned long * &>();
  if ( v3 < 0 )
  {
    v2 = 140;
    goto LABEL_4;
  }
  return 0;
}

```

## disassembly

```asm
0x18000a190  mov     [rsp+arg_8], rdx
0x18000a195  push    rbx; int
0x18000a196  sub     rsp, 20h
0x18000a19a  test    rcx, rcx
0x18000a19d  jnz     short loc_18000A1C1
0x18000a19f  mov     edx, 86h; void *
0x18000a1a4  mov     ebx, 80004003h
0x18000a1a9  mov     rcx, [rsp+28h]; this
0x18000a1ae  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\maps\\moshost\\cli"...
0x18000a1b5  mov     r9d, ebx; char *
0x18000a1b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a1bd  mov     eax, ebx
0x18000a1bf  jmp     short loc_18000A1F0
0x18000a1c1  test    rdx, rdx
0x18000a1c4  jnz     short loc_18000A1CD
0x18000a1c6  mov     edx, 87h
0x18000a1cb  jmp     short loc_18000A1A4
0x18000a1cd  lea     r8, [rsp+28h+arg_8]
0x18000a1d2  mov     [rsp+28h+arg_0], rcx
0x18000a1d7  lea     rdx, [rsp+28h+arg_0]
0x18000a1dc  call    ??$invoke_rpc_nothrow@A6AJPEAXPEAK@ZAEAPEAXAEAPEAK@wil@@YAJA6AJPEAXPEAK@ZAEAPEAXAEAPEAK@Z; wil::invoke_rpc_nothrow<long (&)(void *,ulong *),void * &,ulong * &>(long (&)(void *,ulong *),void * &,ulong * &)
0x18000a1e1  mov     ebx, eax
0x18000a1e3  test    eax, eax
0x18000a1e5  jns     short loc_18000A1EE
0x18000a1e7  mov     edx, 8Ch
0x18000a1ec  jmp     short loc_18000A1A9
0x18000a1ee  xor     eax, eax
0x18000a1f0  add     rsp, 20h
0x18000a1f4  pop     rbx
0x18000a1f5  retn
```
