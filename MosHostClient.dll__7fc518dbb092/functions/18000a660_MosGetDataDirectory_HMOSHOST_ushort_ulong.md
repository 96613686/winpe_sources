# MosGetDataDirectory(HMOSHOST__ *,ushort *,ulong)

- ea: `0x18000a660`
- end: `0x18000a6d5`
- name: `?MosGetDataDirectory@@YAJPEAUHMOSHOST__@@PEAGK@Z`
- size: `117`
- prototype: `__int64 __fastcall(struct HMOSHOST__ *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180006214`
- `0x18000895c`
- `0x18000a660`

## pseudocode

```c
__int64 __fastcall MosGetDataDirectory(struct HMOSHOST__ *a1, unsigned __int16 *a2)
{
  __int64 v2; // rdx
  int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !a1 )
  {
    v2 = 97;
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
    v2 = 98;
    goto LABEL_3;
  }
  v3 = wil::invoke_rpc_nothrow<long (&)(void *,unsigned short *,unsigned long),void * &,unsigned short * &,unsigned long &>();
  if ( v3 < 0 )
  {
    v2 = 103;
    goto LABEL_4;
  }
  return 0;
}

```

## disassembly

```asm
0x18000a660  mov     [rsp+arg_10], r8d
0x18000a665  mov     [rsp+arg_8], rdx
0x18000a66a  push    rbx; int
0x18000a66b  sub     rsp, 20h
0x18000a66f  test    rcx, rcx
0x18000a672  jnz     short loc_18000A694
0x18000a674  lea     edx, [rcx+61h]; void *
0x18000a677  mov     ebx, 80004003h
0x18000a67c  mov     rcx, [rsp+28h]; this
0x18000a681  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\maps\\moshost\\cli"...
0x18000a688  mov     r9d, ebx; char *
0x18000a68b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a690  mov     eax, ebx
0x18000a692  jmp     short loc_18000A6CF
0x18000a694  test    rdx, rdx
0x18000a697  jnz     short loc_18000A6A0
0x18000a699  mov     edx, 62h ; 'b'
0x18000a69e  jmp     short loc_18000A677
0x18000a6a0  mov     [rsp+28h+arg_0], rcx
0x18000a6a5  lea     r9, [rsp+28h+arg_10]
0x18000a6aa  lea     rcx, MosHostGetDataDirectory
0x18000a6b1  lea     r8, [rsp+28h+arg_8]
0x18000a6b6  lea     rdx, [rsp+28h+arg_0]
0x18000a6bb  call    ??$invoke_rpc_nothrow@A6AJPEAXPEAGK@ZAEAPEAXAEAPEAGAEAK@wil@@YAJA6AJPEAXPEAGK@ZAEAPEAXAEAPEAGAEAK@Z; wil::invoke_rpc_nothrow<long (&)(void *,ushort *,ulong),void * &,ushort * &,ulong &>(long (&)(void *,ushort *,ulong),void * &,ushort * &,ulong &)
0x18000a6c0  mov     ebx, eax
0x18000a6c2  test    eax, eax
0x18000a6c4  jns     short loc_18000A6CD
0x18000a6c6  mov     edx, 67h ; 'g'
0x18000a6cb  jmp     short loc_18000A67C
0x18000a6cd  xor     eax, eax
0x18000a6cf  add     rsp, 20h
0x18000a6d3  pop     rbx
0x18000a6d4  retn
```
