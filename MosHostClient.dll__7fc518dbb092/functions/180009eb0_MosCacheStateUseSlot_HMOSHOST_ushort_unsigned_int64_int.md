# MosCacheStateUseSlot(HMOSHOST__ *,ushort,unsigned __int64,int *)

- ea: `0x180009eb0`
- end: `0x180009f23`
- name: `?MosCacheStateUseSlot@@YAJPEAUHMOSHOST__@@G_KPEAH@Z`
- size: `115`
- prototype: `__int64 __fastcall(struct HMOSHOST__ *, __int16, __int64, int *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180006214`
- `0x180008784`
- `0x180009eb0`

## pseudocode

```c
__int64 __fastcall MosCacheStateUseSlot(struct HMOSHOST__ *a1, __int16 a2, __int64 a3, int *a4)
{
  int v4; // ebx
  __int64 v5; // rdx
  int v7; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  struct HMOSHOST__ *v9; // [rsp+40h] [rbp+8h] BYREF
  __int16 v10; // [rsp+48h] [rbp+10h] BYREF
  __int64 v11; // [rsp+50h] [rbp+18h] BYREF
  int *v12; // [rsp+58h] [rbp+20h] BYREF

  v12 = a4;
  v11 = a3;
  v10 = a2;
  if ( !a1 )
  {
    v4 = -2147467261;
    v5 = 255;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\windows\\maps\\moshost\\client\\moshostclient.cpp",
      (const char *)(unsigned int)v4,
      v7);
    return (unsigned int)v4;
  }
  v9 = a1;
  v4 = wil::invoke_rpc_nothrow<long (&)(void *,unsigned short,unsigned __int64,int *),void * &,unsigned short &,unsigned __int64 &,int * &>(
         (__int64)a1,
         (int)&v9,
         (int)&v10,
         (int)&v11,
         (__int64)&v12);
  if ( v4 < 0 )
  {
    v5 = 260;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x180009eb0  mov     [rsp+arg_18], r9
0x180009eb5  mov     [rsp+arg_10], r8
0x180009eba  mov     [rsp+arg_8], dx
0x180009ebf  push    rbx
0x180009ec0  sub     rsp, 30h
0x180009ec4  test    rcx, rcx
0x180009ec7  jnz     short loc_180009EEB
0x180009ec9  mov     ebx, 80004003h
0x180009ece  mov     edx, 0FFh; void *
0x180009ed3  mov     rcx, [rsp+38h]; this
0x180009ed8  lea     r8, aOnecoreuapWind_1; "onecoreuap\\windows\\maps\\moshost\\cli"...
0x180009edf  mov     r9d, ebx; char *
0x180009ee2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009ee7  mov     eax, ebx
0x180009ee9  jmp     short loc_180009F1D
0x180009eeb  lea     rax, [rsp+38h+arg_18]
0x180009ef0  mov     [rsp+38h+arg_0], rcx
0x180009ef5  lea     r9, [rsp+38h+arg_10]
0x180009efa  mov     qword ptr [rsp+38h+var_18], rax
0x180009eff  lea     r8, [rsp+38h+arg_8]
0x180009f04  lea     rdx, [rsp+38h+arg_0]
0x180009f09  call    ??$invoke_rpc_nothrow@A6AJPEAXG_KPEAH@ZAEAPEAXAEAGAEA_KAEAPEAH@wil@@YAJA6AJPEAXG_KPEAH@ZAEAPEAXAEAGAEA_KAEAPEAH@Z; wil::invoke_rpc_nothrow<long (&)(void *,ushort,unsigned __int64,int *),void * &,ushort &,unsigned __int64 &,int * &>(long (&)(void *,ushort,unsigned __int64,int *),void * &,ushort &,unsigned __int64 &,int * &)
0x180009f0e  mov     ebx, eax
0x180009f10  test    eax, eax
0x180009f12  jns     short loc_180009F1B
0x180009f14  mov     edx, 104h
0x180009f19  jmp     short loc_180009ED3
0x180009f1b  xor     eax, eax
0x180009f1d  add     rsp, 30h
0x180009f21  pop     rbx
0x180009f22  retn
```
