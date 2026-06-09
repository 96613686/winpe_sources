# MosGetResourceDirectory(HMOSHOST__ *,ushort *,ulong)

- ea: `0x18000a6e0`
- end: `0x18000a755`
- name: `?MosGetResourceDirectory@@YAJPEAUHMOSHOST__@@PEAGK@Z`
- size: `117`
- prototype: `__int64 __fastcall(struct HMOSHOST__ *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180006214`
- `0x18000895c`
- `0x18000a6e0`

## pseudocode

```c
__int64 __fastcall MosGetResourceDirectory(struct HMOSHOST__ *a1, unsigned __int16 *a2)
{
  __int64 v2; // rdx
  int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !a1 )
  {
    v2 = 116;
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
    v2 = 117;
    goto LABEL_3;
  }
  v3 = wil::invoke_rpc_nothrow<long (&)(void *,unsigned short *,unsigned long),void * &,unsigned short * &,unsigned long &>();
  if ( v3 < 0 )
  {
    v2 = 122;
    goto LABEL_4;
  }
  return 0;
}

```

## disassembly

```asm
0x18000a6e0  mov     [rsp+arg_10], r8d
0x18000a6e5  mov     [rsp+arg_8], rdx
0x18000a6ea  push    rbx; int
0x18000a6eb  sub     rsp, 20h
0x18000a6ef  test    rcx, rcx
0x18000a6f2  jnz     short loc_18000A714
0x18000a6f4  lea     edx, [rcx+74h]; void *
0x18000a6f7  mov     ebx, 80004003h
0x18000a6fc  mov     rcx, [rsp+28h]; this
0x18000a701  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\maps\\moshost\\cli"...
0x18000a708  mov     r9d, ebx; char *
0x18000a70b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a710  mov     eax, ebx
0x18000a712  jmp     short loc_18000A74F
0x18000a714  test    rdx, rdx
0x18000a717  jnz     short loc_18000A720
0x18000a719  mov     edx, 75h ; 'u'
0x18000a71e  jmp     short loc_18000A6F7
0x18000a720  mov     [rsp+28h+arg_0], rcx
0x18000a725  lea     r9, [rsp+28h+arg_10]
0x18000a72a  lea     rcx, MosHostGetResourceDirectory
0x18000a731  lea     r8, [rsp+28h+arg_8]
0x18000a736  lea     rdx, [rsp+28h+arg_0]
0x18000a73b  call    ??$invoke_rpc_nothrow@A6AJPEAXPEAGK@ZAEAPEAXAEAPEAGAEAK@wil@@YAJA6AJPEAXPEAGK@ZAEAPEAXAEAPEAGAEAK@Z; wil::invoke_rpc_nothrow<long (&)(void *,ushort *,ulong),void * &,ushort * &,ulong &>(long (&)(void *,ushort *,ulong),void * &,ushort * &,ulong &)
0x18000a740  mov     ebx, eax
0x18000a742  test    eax, eax
0x18000a744  jns     short loc_18000A74D
0x18000a746  mov     edx, 7Ah ; 'z'
0x18000a74b  jmp     short loc_18000A6FC
0x18000a74d  xor     eax, eax
0x18000a74f  add     rsp, 20h
0x18000a753  pop     rbx
0x18000a754  retn
```
