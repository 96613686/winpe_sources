# DoDeleteDataAsync

- ea: `0x180009670`
- end: `0x1800096c4`
- name: `DoDeleteDataAsync`
- size: `84`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180006214`
- `0x180008b2c`
- `0x180009670`

## pseudocode

```c
__int64 __fastcall DoDeleteDataAsync(__int64 a1, __int64 a2, __int64 a3)
{
  int v3; // eax
  unsigned int v4; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v7; // [rsp+40h] [rbp+8h] BYREF
  __int64 v8; // [rsp+48h] [rbp+10h] BYREF

  v7 = a1;
  v8 = a2;
  v3 = wil::invoke_rpc_nothrow<void (&)(_RPC_ASYNC_STATE *,void *,int,int),_RPC_ASYNC_STATE * &,void * &,int &,int &>(
         a1,
         (int)&v7,
         (int)&v8,
         (int)a3 + 68,
         a3 + 64);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x15C,
    (int)"onecoreuap\\windows\\maps\\moshost\\client\\moshostclient.cpp",
    (const char *)(unsigned int)v3);
  return v4;
}

```

## disassembly

```asm
0x180009670  mov     r11, rsp
0x180009673  mov     [r11+8], rcx
0x180009677  push    rbx
0x180009678  sub     rsp, 30h
0x18000967c  lea     rax, [r8+40h]
0x180009680  mov     [r11+10h], rdx
0x180009684  lea     r9, [rax+4]
0x180009688  mov     [r11-18h], rax
0x18000968c  lea     r8, [r11+10h]
0x180009690  lea     rdx, [r11+8]
0x180009694  call    ??$invoke_rpc_nothrow@A6AXPEAU_RPC_ASYNC_STATE@@PEAXHH@ZAEAPEAU1@AEAPEAXAEAHAEAH@wil@@YAJA6AXPEAU_RPC_ASYNC_STATE@@PEAXHH@ZAEAPEAU1@AEAPEAXAEAH5@Z; wil::invoke_rpc_nothrow<void (&)(_RPC_ASYNC_STATE *,void *,int,int),_RPC_ASYNC_STATE * &,void * &,int &,int &>(void (&)(_RPC_ASYNC_STATE *,void *,int,int),_RPC_ASYNC_STATE * &,void * &,int &,int &)
0x180009699  mov     ebx, eax
0x18000969b  test    eax, eax
0x18000969d  jns     short loc_1800096BC
0x18000969f  mov     rcx, [rsp+38h]; this
0x1800096a4  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\maps\\moshost\\cli"...
0x1800096ab  mov     r9d, eax; char *
0x1800096ae  mov     edx, 15Ch; void *
0x1800096b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800096b8  mov     eax, ebx
0x1800096ba  jmp     short loc_1800096BE
0x1800096bc  xor     eax, eax
0x1800096be  add     rsp, 30h
0x1800096c2  pop     rbx
0x1800096c3  retn
```
