# _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)

- ea: `0x180044488`
- end: `0x180044524`
- name: `??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004452c`

## callees

- `0x180044488`
- `0x1800445c0`
- `0x1800446e0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800444d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800444d7`

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
0x180044488  mov     rax, rsp
0x18004448b  mov     [rax+10h], rbx
0x18004448f  mov     [rax+18h], rbp
0x180044493  mov     [rax+8], rcx
0x180044497  push    rsi
0x180044498  push    rdi
0x180044499  push    r14
0x18004449b  sub     rsp, 40h
0x18004449f  mov     rdi, [rsp+58h+arg_28]
0x1800444a7  lea     rbp, [r9+1]
0x1800444ab  xor     ebx, ebx
0x1800444ad  mov     rsi, r9
0x1800444b0  mov     r14, r8
0x1800444b3  mov     [rdi], rbx
0x1800444b6  cmp     rbp, r9
0x1800444b9  jb      short loc_180044509
0x1800444bb  lea     r8, [rax+8]; unsigned __int64 *
0x1800444bf  mov     [rdi], rbx
0x1800444c2  mov     rcx, rbp; unsigned __int64
0x1800444c5  mov     [rax+8], rbx
0x1800444c9  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x1800444ce  test    eax, eax
0x1800444d0  js      short loc_180044505
0x1800444d2  mov     rcx, [rsp+58h+cb]; cb
0x1800444d7  call    cs:__imp_CoTaskMemAlloc
0x1800444de  nop     dword ptr [rax+rax+00h]
0x1800444e3  mov     [rdi], rax
0x1800444e6  test    rax, rax
0x1800444e9  jz      short loc_1800444FE
0x1800444eb  mov     r9, rsi; unsigned __int64
0x1800444ee  mov     r8, r14; unsigned __int16 *
0x1800444f1  mov     rdx, rbp; unsigned __int64
0x1800444f4  mov     rcx, rax; unsigned __int16 *
0x1800444f7  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x1800444fc  jmp     short loc_18004450E
0x1800444fe  mov     ebx, 8007000Eh
0x180044503  jmp     short loc_18004450E
0x180044505  mov     ebx, eax
0x180044507  jmp     short loc_18004450E
0x180044509  mov     ebx, 80070216h
0x18004450e  mov     rbp, [rsp+58h+arg_10]
0x180044513  mov     eax, ebx
0x180044515  mov     rbx, [rsp+58h+arg_8]
0x18004451a  add     rsp, 40h
0x18004451e  pop     r14
0x180044520  pop     rdi
0x180044521  pop     rsi
0x180044522  retn
```
