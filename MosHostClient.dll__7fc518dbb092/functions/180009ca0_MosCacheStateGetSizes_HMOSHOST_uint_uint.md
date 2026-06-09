# MosCacheStateGetSizes(HMOSHOST__ *,uint *,uint *)

- ea: `0x180009ca0`
- end: `0x180009d04`
- name: `?MosCacheStateGetSizes@@YAJPEAUHMOSHOST__@@PEAI1@Z`
- size: `100`
- prototype: `__int64 __fastcall(struct HMOSHOST__ *, unsigned int *, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180006214`
- `0x1800089cc`
- `0x180009ca0`

## pseudocode

```c
__int64 __fastcall MosCacheStateGetSizes(struct HMOSHOST__ *a1, unsigned int *a2, unsigned int *a3)
{
  int v3; // ebx
  __int64 v4; // rdx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  struct HMOSHOST__ *v8; // [rsp+30h] [rbp+8h] BYREF
  unsigned int *v9; // [rsp+38h] [rbp+10h] BYREF
  unsigned int *v10; // [rsp+40h] [rbp+18h] BYREF

  v10 = a3;
  v9 = a2;
  if ( !a1 )
  {
    v3 = -2147467261;
    v4 = 236;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\windows\\maps\\moshost\\client\\moshostclient.cpp",
      (const char *)(unsigned int)v3,
      v6);
    return (unsigned int)v3;
  }
  v8 = a1;
  v3 = wil::invoke_rpc_nothrow<long (&)(void *,unsigned int *,unsigned int *),void * &,unsigned int * &,unsigned int * &>(
         (__int64)a1,
         &v8,
         &v9,
         &v10);
  if ( v3 < 0 )
  {
    v4 = 241;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180009ca0  mov     [rsp+arg_10], r8
0x180009ca5  mov     [rsp+arg_8], rdx
0x180009caa  push    rbx; int
0x180009cab  sub     rsp, 20h
0x180009caf  test    rcx, rcx
0x180009cb2  jnz     short loc_180009CD6
0x180009cb4  mov     ebx, 80004003h
0x180009cb9  mov     edx, 0ECh; void *
0x180009cbe  mov     rcx, [rsp+28h]; this
0x180009cc3  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\maps\\moshost\\cli"...
0x180009cca  mov     r9d, ebx; char *
0x180009ccd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009cd2  mov     eax, ebx
0x180009cd4  jmp     short loc_180009CFE
0x180009cd6  lea     r9, [rsp+28h+arg_10]
0x180009cdb  mov     [rsp+28h+arg_0], rcx
0x180009ce0  lea     r8, [rsp+28h+arg_8]
0x180009ce5  lea     rdx, [rsp+28h+arg_0]
0x180009cea  call    ??$invoke_rpc_nothrow@A6AJPEAXPEAI1@ZAEAPEAXAEAPEAIAEAPEAI@wil@@YAJA6AJPEAXPEAI1@ZAEAPEAXAEAPEAI4@Z; wil::invoke_rpc_nothrow<long (&)(void *,uint *,uint *),void * &,uint * &,uint * &>(long (&)(void *,uint *,uint *),void * &,uint * &,uint * &)
0x180009cef  mov     ebx, eax
0x180009cf1  test    eax, eax
0x180009cf3  jns     short loc_180009CFC
0x180009cf5  mov     edx, 0F1h
0x180009cfa  jmp     short loc_180009CBE
0x180009cfc  xor     eax, eax
0x180009cfe  add     rsp, 20h
0x180009d02  pop     rbx
0x180009d03  retn
```
