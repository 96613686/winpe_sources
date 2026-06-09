# MosCacheStateSetMaxSize(HMOSHOST__ *,uint)

- ea: `0x180009d10`
- end: `0x180009d5e`
- name: `?MosCacheStateSetMaxSize@@YAJPEAUHMOSHOST__@@I@Z`
- size: `78`
- prototype: `__int64 __fastcall(struct HMOSHOST__ *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180006214`
- `0x180008804`
- `0x180009d10`

## pseudocode

```c
__int64 __fastcall MosCacheStateSetMaxSize(struct HMOSHOST__ *a1)
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
    (void *)0xDF,
    (unsigned int)"onecoreuap\\windows\\maps\\moshost\\client\\moshostclient.cpp",
    (const char *)(unsigned int)v1,
    v4);
  return v2;
}

```

## disassembly

```asm
0x180009d10  mov     rax, rsp
0x180009d13  mov     [rax+10h], edx
0x180009d16  push    rbx; int
0x180009d17  sub     rsp, 20h
0x180009d1b  mov     [rax+8], rcx
0x180009d1f  lea     r8, [rax+10h]
0x180009d23  lea     rcx, MosHostCacheStateSetMaxSize
0x180009d2a  lea     rdx, [rax+8]
0x180009d2e  call    ??$invoke_rpc_nothrow@A6AJPEAXI@ZAEAPEAXAEAI@wil@@YAJA6AJPEAXI@ZAEAPEAXAEAI@Z; wil::invoke_rpc_nothrow<long (&)(void *,uint),void * &,uint &>(long (&)(void *,uint),void * &,uint &)
0x180009d33  mov     ebx, eax
0x180009d35  test    eax, eax
0x180009d37  jns     short loc_180009D56
0x180009d39  mov     rcx, [rsp+28h]; this
0x180009d3e  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\maps\\moshost\\cli"...
0x180009d45  mov     r9d, eax; char *
0x180009d48  mov     edx, 0DFh; void *
0x180009d4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009d52  mov     eax, ebx
0x180009d54  jmp     short loc_180009D58
0x180009d56  xor     eax, eax
0x180009d58  add     rsp, 20h
0x180009d5c  pop     rbx
0x180009d5d  retn
```
