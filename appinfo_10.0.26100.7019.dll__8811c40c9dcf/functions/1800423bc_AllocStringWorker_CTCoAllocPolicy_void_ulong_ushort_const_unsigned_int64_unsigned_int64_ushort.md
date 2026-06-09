# _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)

- ea: `0x1800423bc`
- end: `0x180042458`
- name: `??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180042460`

## callees

- `0x1800423bc`
- `0x1800424f4`
- `0x180042614`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004240b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004240b`

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
  unsigned __int16 **v6; // rdi
  unsigned __int64 v7; // rbp
  unsigned int v8; // ebx
  int v11; // eax
  unsigned __int16 *v12; // rax
  unsigned __int16 **v14; // [rsp+20h] [rbp-38h]
  unsigned __int64 *v15; // [rsp+28h] [rbp-30h]
  unsigned int v16; // [rsp+30h] [rbp-28h]
  SIZE_T cb; // [rsp+60h] [rbp+8h] BYREF

  cb = a1;
  v6 = a6;
  v7 = a4 + 1;
  v8 = 0;
  *a6 = 0;
  if ( a4 + 1 < a4 )
  {
    return (unsigned int)-2147024362;
  }
  else
  {
    *v6 = 0;
    cb = 0;
    v11 = ULongLongMult(a4 + 1, a2, &cb);
    if ( v11 < 0 )
    {
      return (unsigned int)v11;
    }
    else
    {
      v12 = (unsigned __int16 *)CoTaskMemAlloc(cb);
      *v6 = v12;
      if ( v12 )
        StringCchCopyNExW(v12, v7, a3, a4, v14, v15, v16);
      else
        return (unsigned int)-2147024882;
    }
  }
  return v8;
}

```

## disassembly

```asm
0x1800423bc  mov     rax, rsp
0x1800423bf  mov     [rax+10h], rbx
0x1800423c3  mov     [rax+18h], rbp
0x1800423c7  mov     [rax+8], rcx
0x1800423cb  push    rsi
0x1800423cc  push    rdi
0x1800423cd  push    r14
0x1800423cf  sub     rsp, 40h
0x1800423d3  mov     rdi, [rsp+58h+arg_28]
0x1800423db  lea     rbp, [r9+1]
0x1800423df  xor     ebx, ebx
0x1800423e1  mov     rsi, r9
0x1800423e4  mov     r14, r8
0x1800423e7  mov     [rdi], rbx
0x1800423ea  cmp     rbp, r9
0x1800423ed  jb      short loc_18004243D
0x1800423ef  lea     r8, [rax+8]; unsigned __int64 *
0x1800423f3  mov     [rdi], rbx
0x1800423f6  mov     rcx, rbp; unsigned __int64
0x1800423f9  mov     [rax+8], rbx
0x1800423fd  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180042402  test    eax, eax
0x180042404  js      short loc_180042439
0x180042406  mov     rcx, [rsp+58h+cb]; cb
0x18004240b  call    cs:__imp_CoTaskMemAlloc
0x180042412  nop     dword ptr [rax+rax+00h]
0x180042417  mov     [rdi], rax
0x18004241a  test    rax, rax
0x18004241d  jz      short loc_180042432
0x18004241f  mov     r9, rsi; unsigned __int64
0x180042422  mov     r8, r14; unsigned __int16 *
0x180042425  mov     rdx, rbp; unsigned __int64
0x180042428  mov     rcx, rax; unsigned __int16 *
0x18004242b  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x180042430  jmp     short loc_180042442
0x180042432  mov     ebx, 8007000Eh
0x180042437  jmp     short loc_180042442
0x180042439  mov     ebx, eax
0x18004243b  jmp     short loc_180042442
0x18004243d  mov     ebx, 80070216h
0x180042442  mov     rbp, [rsp+58h+arg_10]
0x180042447  mov     eax, ebx
0x180042449  mov     rbx, [rsp+58h+arg_8]
0x18004244e  add     rsp, 40h
0x180042452  pop     r14
0x180042454  pop     rdi
0x180042455  pop     rsi
0x180042456  retn
```
