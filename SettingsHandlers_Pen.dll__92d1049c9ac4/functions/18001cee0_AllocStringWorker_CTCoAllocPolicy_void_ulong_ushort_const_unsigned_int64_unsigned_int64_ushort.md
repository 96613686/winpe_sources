# _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)

- ea: `0x18001cee0`
- end: `0x18001cf81`
- name: `??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800284f8`

## callees

- `0x180019590`
- `0x18001cee0`
- `0x180030698`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001cf39`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001cf39`

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
0x18001cee0  mov     rax, rsp
0x18001cee3  mov     [rax+10h], rbx
0x18001cee7  mov     [rax+18h], rbp
0x18001ceeb  mov     [rax+8], rcx
0x18001ceef  push    rsi
0x18001cef0  push    rdi
0x18001cef1  push    r14
0x18001cef3  sub     rsp, 40h
0x18001cef7  mov     r14, [rsp+58h+arg_28]
0x18001ceff  lea     rsi, [r9+1]
0x18001cf03  mov     rdi, r9
0x18001cf06  mov     rbp, r8
0x18001cf09  mov     qword ptr [r14], 0
0x18001cf10  cmp     rsi, r9
0x18001cf13  jb      short loc_18001CF67
0x18001cf15  lea     r8, [rax+8]; unsigned __int64 *
0x18001cf19  mov     qword ptr [rax+8], 0
0x18001cf21  mov     edx, 2; unsigned __int64
0x18001cf26  mov     rcx, rsi; unsigned __int64
0x18001cf29  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18001cf2e  mov     ebx, eax
0x18001cf30  test    eax, eax
0x18001cf32  js      short loc_18001CF6C
0x18001cf34  mov     rcx, [rsp+58h+cb]; cb
0x18001cf39  call    cs:__imp_CoTaskMemAlloc
0x18001cf3f  mov     rcx, rax
0x18001cf42  mov     [r14], rax
0x18001cf45  neg     rcx
0x18001cf48  sbb     ebx, ebx
0x18001cf4a  not     ebx
0x18001cf4c  and     ebx, 8007000Eh
0x18001cf52  jl      short loc_18001CF6C
0x18001cf54  mov     r9, rdi; unsigned __int64
0x18001cf57  mov     r8, rbp; unsigned __int16 *
0x18001cf5a  mov     rdx, rsi; unsigned __int64
0x18001cf5d  mov     rcx, rax; unsigned __int16 *
0x18001cf60  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x18001cf65  jmp     short loc_18001CF6C
0x18001cf67  mov     ebx, 80070216h
0x18001cf6c  mov     rbp, [rsp+58h+arg_10]
0x18001cf71  mov     eax, ebx
0x18001cf73  mov     rbx, [rsp+58h+arg_8]
0x18001cf78  add     rsp, 40h
0x18001cf7c  pop     r14
0x18001cf7e  pop     rdi
0x18001cf7f  pop     rsi
0x18001cf80  retn
```
