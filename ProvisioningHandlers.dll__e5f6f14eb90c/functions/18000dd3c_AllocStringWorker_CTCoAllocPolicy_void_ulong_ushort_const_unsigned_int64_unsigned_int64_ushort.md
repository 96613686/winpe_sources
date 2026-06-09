# _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)

- ea: `0x18000dd3c`
- end: `0x18000dde4`
- name: `??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z`
- size: `168`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180014cd4`
- `0x180017378`

## callees

- `0x18000dd3c`
- `0x18001e3a0`
- `0x18001e530`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dd95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000dd95`

## pseudocode

```c
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
0x18000dd3c  mov     rax, rsp
0x18000dd3f  mov     [rax+10h], rbx
0x18000dd43  mov     [rax+18h], rbp
0x18000dd47  mov     [rax+8], rcx
0x18000dd4b  push    rsi
0x18000dd4c  push    rdi
0x18000dd4d  push    r14
0x18000dd4f  sub     rsp, 40h
0x18000dd53  mov     r14, [rsp+58h+arg_28]
0x18000dd5b  lea     rsi, [r9+1]
0x18000dd5f  mov     rdi, r9
0x18000dd62  mov     rbp, r8
0x18000dd65  mov     qword ptr [r14], 0
0x18000dd6c  cmp     rsi, r9
0x18000dd6f  jb      short loc_18000DDC9
0x18000dd71  lea     r8, [rax+8]; unsigned __int64 *
0x18000dd75  mov     qword ptr [rax+8], 0
0x18000dd7d  mov     edx, 2; unsigned __int64
0x18000dd82  mov     rcx, rsi; unsigned __int64
0x18000dd85  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18000dd8a  mov     ebx, eax
0x18000dd8c  test    eax, eax
0x18000dd8e  js      short loc_18000DDCE
0x18000dd90  mov     rcx, [rsp+58h+cb]; cb
0x18000dd95  call    cs:__imp_CoTaskMemAlloc
0x18000dd9c  nop     dword ptr [rax+rax+00h]
0x18000dda1  mov     rcx, rax
0x18000dda4  mov     [r14], rax
0x18000dda7  neg     rcx
0x18000ddaa  sbb     ebx, ebx
0x18000ddac  not     ebx
0x18000ddae  and     ebx, 8007000Eh
0x18000ddb4  jl      short loc_18000DDCE
0x18000ddb6  mov     r9, rdi; unsigned __int64
0x18000ddb9  mov     r8, rbp; unsigned __int16 *
0x18000ddbc  mov     rdx, rsi; unsigned __int64
0x18000ddbf  mov     rcx, rax; unsigned __int16 *
0x18000ddc2  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x18000ddc7  jmp     short loc_18000DDCE
0x18000ddc9  mov     ebx, 80070216h
0x18000ddce  mov     rbp, [rsp+58h+arg_10]
0x18000ddd3  mov     eax, ebx
0x18000ddd5  mov     rbx, [rsp+58h+arg_8]
0x18000ddda  add     rsp, 40h
0x18000ddde  pop     r14
0x18000dde0  pop     rdi
0x18000dde1  pop     rsi
0x18000dde2  retn
```
