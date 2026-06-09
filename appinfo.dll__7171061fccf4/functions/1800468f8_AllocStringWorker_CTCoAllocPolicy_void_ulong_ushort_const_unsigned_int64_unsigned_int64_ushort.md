# _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)

- ea: `0x1800468f8`
- end: `0x180046994`
- name: `??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z`
- size: `156`
- prototype: `__int64 __fastcall(SIZE_T, unsigned __int64, const unsigned __int16 *, unsigned __int64, __int64, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004699c`

## callees

- `0x1800468f8`
- `0x180046a2c`
- `0x180046b4c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004694c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004694c`

## pseudocode

```c
__int64 __fastcall _AllocStringWorker<CTCoAllocPolicy>(
        SIZE_T a1,
        unsigned __int64 a2,
        const unsigned __int16 *a3,
        unsigned __int64 a4,
        __int64 a5,
        unsigned __int16 **a6)
{
  unsigned __int16 **v6; // r14
  unsigned __int64 v7; // rdi
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
    v10 = ULongLongMult(v7, a2, &cb);
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
0x1800468f8  mov     rax, rsp
0x1800468fb  mov     [rax+10h], rbx
0x1800468ff  mov     [rax+18h], rbp
0x180046903  mov     [rax+8], rcx
0x180046907  push    rsi
0x180046908  push    rdi
0x180046909  push    r14
0x18004690b  sub     rsp, 40h
0x18004690f  mov     r14, [rsp+58h+arg_28]
0x180046917  lea     rdi, [r9+1]
0x18004691b  mov     rsi, r9
0x18004691e  mov     rbp, r8
0x180046921  mov     qword ptr [r14], 0
0x180046928  cmp     rdi, r9
0x18004692b  jb      short loc_18004697A
0x18004692d  lea     r8, [rax+8]; unsigned __int64 *
0x180046931  mov     qword ptr [rax+8], 0
0x180046939  mov     rcx, rdi; unsigned __int64
0x18004693c  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180046941  mov     ebx, eax
0x180046943  test    eax, eax
0x180046945  js      short loc_18004697F
0x180046947  mov     rcx, [rsp+58h+cb]; cb
0x18004694c  call    cs:__imp_CoTaskMemAlloc
0x180046952  mov     rcx, rax
0x180046955  mov     [r14], rax
0x180046958  neg     rcx
0x18004695b  sbb     ebx, ebx
0x18004695d  not     ebx
0x18004695f  and     ebx, 8007000Eh
0x180046965  jl      short loc_18004697F
0x180046967  mov     r9, rsi; unsigned __int64
0x18004696a  mov     r8, rbp; unsigned __int16 *
0x18004696d  mov     rdx, rdi; unsigned __int64
0x180046970  mov     rcx, rax; unsigned __int16 *
0x180046973  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x180046978  jmp     short loc_18004697F
0x18004697a  mov     ebx, 80070216h
0x18004697f  mov     rbp, [rsp+58h+arg_10]
0x180046984  mov     eax, ebx
0x180046986  mov     rbx, [rsp+58h+arg_8]
0x18004698b  add     rsp, 40h
0x18004698f  pop     r14
0x180046991  pop     rdi
0x180046992  pop     rsi
0x180046993  retn
```
