# MosCacheStateSetSlotSize(HMOSHOST__ *,int,uint)

- ea: `0x180009d70`
- end: `0x180009dd3`
- name: `?MosCacheStateSetSlotSize@@YAJPEAUHMOSHOST__@@HI@Z`
- size: `99`
- prototype: `__int64 __fastcall(struct HMOSHOST__ *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180006214`
- `0x180008874`
- `0x180009d70`

## pseudocode

```c
__int64 __fastcall MosCacheStateSetSlotSize(struct HMOSHOST__ *a1)
{
  int v1; // ebx
  __int64 v2; // rdx
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !a1 )
  {
    v1 = -2147467261;
    v2 = 290;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v2,
      (unsigned int)"onecoreuap\\windows\\maps\\moshost\\client\\moshostclient.cpp",
      (const char *)(unsigned int)v1,
      v4);
    return (unsigned int)v1;
  }
  v1 = wil::invoke_rpc_nothrow<long (&)(void *,int,unsigned int),void * &,int &,unsigned int &>();
  if ( v1 < 0 )
  {
    v2 = 295;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180009d70  mov     [rsp+arg_10], r8d
0x180009d75  mov     [rsp+arg_8], edx
0x180009d79  push    rbx; int
0x180009d7a  sub     rsp, 20h
0x180009d7e  test    rcx, rcx
0x180009d81  jnz     short loc_180009DA5
0x180009d83  mov     ebx, 80004003h
0x180009d88  mov     edx, 122h; void *
0x180009d8d  mov     rcx, [rsp+28h]; this
0x180009d92  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\maps\\moshost\\cli"...
0x180009d99  mov     r9d, ebx; char *
0x180009d9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009da1  mov     eax, ebx
0x180009da3  jmp     short loc_180009DCD
0x180009da5  lea     r9, [rsp+28h+arg_10]
0x180009daa  mov     [rsp+28h+arg_0], rcx
0x180009daf  lea     r8, [rsp+28h+arg_8]
0x180009db4  lea     rdx, [rsp+28h+arg_0]
0x180009db9  call    ??$invoke_rpc_nothrow@A6AJPEAXHI@ZAEAPEAXAEAHAEAI@wil@@YAJA6AJPEAXHI@ZAEAPEAXAEAHAEAI@Z; wil::invoke_rpc_nothrow<long (&)(void *,int,uint),void * &,int &,uint &>(long (&)(void *,int,uint),void * &,int &,uint &)
0x180009dbe  mov     ebx, eax
0x180009dc0  test    eax, eax
0x180009dc2  jns     short loc_180009DCB
0x180009dc4  mov     edx, 127h
0x180009dc9  jmp     short loc_180009D8D
0x180009dcb  xor     eax, eax
0x180009dcd  add     rsp, 20h
0x180009dd1  pop     rbx
0x180009dd2  retn
```
