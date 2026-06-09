# MosCacheStateUnuseSlot(HMOSHOST__ *,int)

- ea: `0x180009e40`
- end: `0x180009ea0`
- name: `?MosCacheStateUnuseSlot@@YAJPEAUHMOSHOST__@@H@Z`
- size: `96`
- prototype: `__int64 __fastcall(struct HMOSHOST__ *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180006214`
- `0x180008804`
- `0x180009e40`

## pseudocode

```c
__int64 __fastcall MosCacheStateUnuseSlot(struct HMOSHOST__ *a1)
{
  int v1; // ebx
  __int64 v2; // rdx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !a1 )
  {
    v1 = -2147467261;
    v2 = 272;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v2,
      (unsigned int)"onecoreuap\\windows\\maps\\moshost\\client\\moshostclient.cpp",
      (const char *)(unsigned int)v1,
      v4);
    return (unsigned int)v1;
  }
  v1 = wil::invoke_rpc_nothrow<long (&)(void *,unsigned int),void * &,unsigned int &>();
  if ( v1 < 0 )
  {
    v2 = 277;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180009e40  mov     [rsp+arg_8], edx
0x180009e44  push    rbx; int
0x180009e45  sub     rsp, 20h
0x180009e49  test    rcx, rcx
0x180009e4c  jnz     short loc_180009E70
0x180009e4e  mov     ebx, 80004003h
0x180009e53  mov     edx, 110h; void *
0x180009e58  mov     rcx, [rsp+28h]; this
0x180009e5d  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\maps\\moshost\\cli"...
0x180009e64  mov     r9d, ebx; char *
0x180009e67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009e6c  mov     eax, ebx
0x180009e6e  jmp     short loc_180009E9A
0x180009e70  mov     [rsp+28h+arg_0], rcx
0x180009e75  lea     r8, [rsp+28h+arg_8]
0x180009e7a  lea     rcx, MosHostCacheStateUnuseSlot
0x180009e81  lea     rdx, [rsp+28h+arg_0]
0x180009e86  call    ??$invoke_rpc_nothrow@A6AJPEAXI@ZAEAPEAXAEAI@wil@@YAJA6AJPEAXI@ZAEAPEAXAEAI@Z; wil::invoke_rpc_nothrow<long (&)(void *,uint),void * &,uint &>(long (&)(void *,uint),void * &,uint &)
0x180009e8b  mov     ebx, eax
0x180009e8d  test    eax, eax
0x180009e8f  jns     short loc_180009E98
0x180009e91  mov     edx, 115h
0x180009e96  jmp     short loc_180009E58
0x180009e98  xor     eax, eax
0x180009e9a  add     rsp, 20h
0x180009e9e  pop     rbx
0x180009e9f  retn
```
