# _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)

- ea: `0x180025054`
- end: `0x1800250f0`
- name: `??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000b500`

## callees

- `0x180016728`
- `0x180025054`
- `0x18004caa4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800250a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800250a8`

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
0x180025054  mov     rax, rsp
0x180025057  mov     [rax+10h], rbx
0x18002505b  mov     [rax+18h], rbp
0x18002505f  mov     [rax+8], rcx
0x180025063  push    rsi
0x180025064  push    rdi
0x180025065  push    r14
0x180025067  sub     rsp, 40h
0x18002506b  mov     r14, [rsp+58h+arg_28]
0x180025073  lea     rdi, [r9+1]
0x180025077  mov     rsi, r9
0x18002507a  mov     rbp, r8
0x18002507d  mov     qword ptr [r14], 0
0x180025084  cmp     rdi, r9
0x180025087  jb      short loc_1800250D6
0x180025089  lea     r8, [rax+8]; unsigned __int64 *
0x18002508d  mov     qword ptr [rax+8], 0
0x180025095  mov     rcx, rdi; unsigned __int64
0x180025098  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18002509d  mov     ebx, eax
0x18002509f  test    eax, eax
0x1800250a1  js      short loc_1800250DB
0x1800250a3  mov     rcx, [rsp+58h+cb]; cb
0x1800250a8  call    cs:__imp_CoTaskMemAlloc
0x1800250ae  mov     rcx, rax
0x1800250b1  mov     [r14], rax
0x1800250b4  neg     rcx
0x1800250b7  sbb     ebx, ebx
0x1800250b9  not     ebx
0x1800250bb  and     ebx, 8007000Eh
0x1800250c1  jl      short loc_1800250DB
0x1800250c3  mov     r9, rsi; unsigned __int64
0x1800250c6  mov     r8, rbp; unsigned __int16 *
0x1800250c9  mov     rdx, rdi; unsigned __int64
0x1800250cc  mov     rcx, rax; unsigned __int16 *
0x1800250cf  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x1800250d4  jmp     short loc_1800250DB
0x1800250d6  mov     ebx, 80070216h
0x1800250db  mov     rbp, [rsp+58h+arg_10]
0x1800250e0  mov     eax, ebx
0x1800250e2  mov     rbx, [rsp+58h+arg_8]
0x1800250e7  add     rsp, 40h
0x1800250eb  pop     r14
0x1800250ed  pop     rdi
0x1800250ee  pop     rsi
0x1800250ef  retn
```
