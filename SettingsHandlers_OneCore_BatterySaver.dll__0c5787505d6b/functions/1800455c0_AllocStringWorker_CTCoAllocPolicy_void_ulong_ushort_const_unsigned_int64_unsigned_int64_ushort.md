# _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)

- ea: `0x1800455c0`
- end: `0x180045661`
- name: `??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z`
- size: `161`
- prototype: `__int64 __fastcall(SIZE_T, __int64, const unsigned __int16 *, unsigned __int64, __int64, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800458ec`

## callees

- `0x18001360c`
- `0x1800455c0`
- `0x180045aec`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180045619`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180045619`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _AllocStringWorker<CTCoAllocPolicy>(
        SIZE_T a1,
        __int64 a2,
        const unsigned __int16 *a3,
        unsigned __int64 a4,
        __int64 a5,
        unsigned __int16 **a6)
{
  unsigned __int16 **v6; // r14
  unsigned __int64 v7; // rsi
  signed int v10; // ebx
  unsigned __int16 *v11; // rax
  unsigned __int16 **v13; // [rsp+20h] [rbp-38h]
  unsigned __int64 *v14; // [rsp+28h] [rbp-30h]
  unsigned int v15; // [rsp+30h] [rbp-28h]
  SIZE_T cb; // [rsp+60h] [rbp+8h] BYREF

  cb = a1;
  v6 = a6;
  v7 = a4 + 1;
  *a6 = 0;
  if ( a4 + 1 < a4 )
  {
    return (unsigned int)-2147024362;
  }
  else
  {
    cb = 0;
    v10 = ULongLongMult(a4 + 1, 2u, &cb);
    if ( v10 >= 0 )
    {
      v11 = (unsigned __int16 *)CoTaskMemAlloc(cb);
      *v6 = v11;
      v10 = v11 == 0 ? 0x8007000E : 0;
      if ( v11 )
        StringCchCopyNExW(v11, v7, a3, a4, v13, v14, v15);
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800455c0  mov     rax, rsp
0x1800455c3  mov     [rax+10h], rbx
0x1800455c7  mov     [rax+18h], rbp
0x1800455cb  mov     [rax+8], rcx
0x1800455cf  push    rsi
0x1800455d0  push    rdi
0x1800455d1  push    r14
0x1800455d3  sub     rsp, 40h
0x1800455d7  mov     r14, [rsp+58h+arg_28]
0x1800455df  lea     rsi, [r9+1]
0x1800455e3  mov     rdi, r9
0x1800455e6  mov     rbp, r8
0x1800455e9  mov     qword ptr [r14], 0
0x1800455f0  cmp     rsi, r9
0x1800455f3  jb      short loc_180045647
0x1800455f5  lea     r8, [rax+8]; unsigned __int64 *
0x1800455f9  mov     qword ptr [rax+8], 0
0x180045601  mov     edx, 2; unsigned __int64
0x180045606  mov     rcx, rsi; unsigned __int64
0x180045609  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18004560e  mov     ebx, eax
0x180045610  test    eax, eax
0x180045612  js      short loc_18004564C
0x180045614  mov     rcx, [rsp+58h+cb]; cb
0x180045619  call    cs:__imp_CoTaskMemAlloc
0x18004561f  mov     rcx, rax
0x180045622  mov     [r14], rax
0x180045625  neg     rcx
0x180045628  sbb     ebx, ebx
0x18004562a  not     ebx
0x18004562c  and     ebx, 8007000Eh
0x180045632  jl      short loc_18004564C
0x180045634  mov     r9, rdi; unsigned __int64
0x180045637  mov     r8, rbp; unsigned __int16 *
0x18004563a  mov     rdx, rsi; unsigned __int64
0x18004563d  mov     rcx, rax; unsigned __int16 *
0x180045640  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x180045645  jmp     short loc_18004564C
0x180045647  mov     ebx, 80070216h
0x18004564c  mov     rbp, [rsp+58h+arg_10]
0x180045651  mov     eax, ebx
0x180045653  mov     rbx, [rsp+58h+arg_8]
0x180045658  add     rsp, 40h
0x18004565c  pop     r14
0x18004565e  pop     rdi
0x18004565f  pop     rsi
0x180045660  retn
```
