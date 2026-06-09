# MosCacheStateSnapshot(HMOSHOST__ *,uchar)

- ea: `0x180009de0`
- end: `0x180009e39`
- name: `?MosCacheStateSnapshot@@YAJPEAUHMOSHOST__@@E@Z`
- size: `89`
- prototype: `__int64 __fastcall(struct HMOSHOST__ *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180006214`
- `0x180008674`
- `0x180009de0`

## pseudocode

```c
__int64 __fastcall MosCacheStateSnapshot(struct HMOSHOST__ *a1)
{
  int v1; // ebx
  __int64 v2; // rdx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !a1 )
  {
    v1 = -2147467261;
    v2 = 307;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v2,
      (unsigned int)"onecoreuap\\windows\\maps\\moshost\\client\\moshostclient.cpp",
      (const char *)(unsigned int)v1,
      v4);
    return (unsigned int)v1;
  }
  v1 = wil::invoke_rpc_nothrow<long (&)(void *,unsigned char),void * &,unsigned char &>();
  if ( v1 < 0 )
  {
    v2 = 312;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180009de0  mov     [rsp+arg_8], dl
0x180009de4  push    rbx; int
0x180009de5  sub     rsp, 20h
0x180009de9  test    rcx, rcx
0x180009dec  jnz     short loc_180009E10
0x180009dee  mov     ebx, 80004003h
0x180009df3  mov     edx, 133h; void *
0x180009df8  mov     rcx, [rsp+28h]; this
0x180009dfd  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\maps\\moshost\\cli"...
0x180009e04  mov     r9d, ebx; char *
0x180009e07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009e0c  mov     eax, ebx
0x180009e0e  jmp     short loc_180009E33
0x180009e10  lea     r8, [rsp+28h+arg_8]
0x180009e15  mov     [rsp+28h+arg_0], rcx
0x180009e1a  lea     rdx, [rsp+28h+arg_0]
0x180009e1f  call    ??$invoke_rpc_nothrow@A6AJPEAXE@ZAEAPEAXAEAE@wil@@YAJA6AJPEAXE@ZAEAPEAXAEAE@Z; wil::invoke_rpc_nothrow<long (&)(void *,uchar),void * &,uchar &>(long (&)(void *,uchar),void * &,uchar &)
0x180009e24  mov     ebx, eax
0x180009e26  test    eax, eax
0x180009e28  jns     short loc_180009E31
0x180009e2a  mov     edx, 138h
0x180009e2f  jmp     short loc_180009DF8
0x180009e31  xor     eax, eax
0x180009e33  add     rsp, 20h
0x180009e37  pop     rbx
0x180009e38  retn
```
