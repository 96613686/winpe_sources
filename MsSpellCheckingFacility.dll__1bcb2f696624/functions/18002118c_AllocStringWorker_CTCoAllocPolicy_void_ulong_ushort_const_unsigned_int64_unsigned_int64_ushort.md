# _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)

- ea: `0x18002118c`
- end: `0x18002122d`
- name: `??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z`
- size: `161`
- prototype: `__int64 __fastcall(SIZE_T, __int64, const unsigned __int16 *, unsigned __int64, __int64, unsigned __int16 **)`
- caller_count: `11`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800206ec`
- `0x180070610`
- `0x1800706f0`
- `0x180070740`
- `0x180087320`
- `0x180094d80`
- `0x180094db0`
- `0x180094df0`
- `0x1800955a0`
- `0x1800955d0`
- `0x180095610`

## callees

- `0x18002118c`
- `0x1800385f8`
- `0x18003a098`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800211e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800211e5`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x18002118c  mov     rax, rsp
0x18002118f  mov     [rax+10h], rbx
0x180021193  mov     [rax+18h], rbp
0x180021197  mov     [rax+8], rcx
0x18002119b  push    rsi
0x18002119c  push    rdi
0x18002119d  push    r14
0x18002119f  sub     rsp, 40h
0x1800211a3  mov     r14, [rsp+58h+arg_28]
0x1800211ab  lea     rsi, [r9+1]
0x1800211af  mov     rdi, r9
0x1800211b2  mov     rbp, r8
0x1800211b5  mov     qword ptr [r14], 0
0x1800211bc  cmp     rsi, r9
0x1800211bf  jb      short loc_180021213
0x1800211c1  lea     r8, [rax+8]; unsigned __int64 *
0x1800211c5  mov     qword ptr [rax+8], 0
0x1800211cd  mov     edx, 2; unsigned __int64
0x1800211d2  mov     rcx, rsi; unsigned __int64
0x1800211d5  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800211da  mov     ebx, eax
0x1800211dc  test    eax, eax
0x1800211de  js      short loc_180021218
0x1800211e0  mov     rcx, [rsp+58h+cb]; cb
0x1800211e5  call    cs:__imp_CoTaskMemAlloc
0x1800211eb  mov     rcx, rax
0x1800211ee  mov     [r14], rax
0x1800211f1  neg     rcx
0x1800211f4  sbb     ebx, ebx
0x1800211f6  not     ebx
0x1800211f8  and     ebx, 8007000Eh
0x1800211fe  jl      short loc_180021218
0x180021200  mov     r9, rdi; unsigned __int64
0x180021203  mov     r8, rbp; unsigned __int16 *
0x180021206  mov     rdx, rsi; unsigned __int64
0x180021209  mov     rcx, rax; unsigned __int16 *
0x18002120c  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x180021211  jmp     short loc_180021218
0x180021213  mov     ebx, 80070216h
0x180021218  mov     rbp, [rsp+58h+arg_10]
0x18002121d  mov     eax, ebx
0x18002121f  mov     rbx, [rsp+58h+arg_8]
0x180021224  add     rsp, 40h
0x180021228  pop     r14
0x18002122a  pop     rdi
0x18002122b  pop     rsi
0x18002122c  retn
```
