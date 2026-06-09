# _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)

- ea: `0x180043f48`
- end: `0x180043fe4`
- name: `??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z`
- size: `156`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180043fec`

## callees

- `0x180043f48`
- `0x180044080`
- `0x1800441a0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180043f97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180043f97`

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
0x180043f48  mov     rax, rsp
0x180043f4b  mov     [rax+10h], rbx
0x180043f4f  mov     [rax+18h], rbp
0x180043f53  mov     [rax+8], rcx
0x180043f57  push    rsi
0x180043f58  push    rdi
0x180043f59  push    r14
0x180043f5b  sub     rsp, 40h
0x180043f5f  mov     rdi, [rsp+58h+arg_28]
0x180043f67  lea     rbp, [r9+1]
0x180043f6b  xor     ebx, ebx
0x180043f6d  mov     rsi, r9
0x180043f70  mov     r14, r8
0x180043f73  mov     [rdi], rbx
0x180043f76  cmp     rbp, r9
0x180043f79  jb      short loc_180043FC9
0x180043f7b  lea     r8, [rax+8]; unsigned __int64 *
0x180043f7f  mov     [rdi], rbx
0x180043f82  mov     rcx, rbp; unsigned __int64
0x180043f85  mov     [rax+8], rbx
0x180043f89  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180043f8e  test    eax, eax
0x180043f90  js      short loc_180043FC5
0x180043f92  mov     rcx, [rsp+58h+cb]; cb
0x180043f97  call    cs:__imp_CoTaskMemAlloc
0x180043f9e  nop     dword ptr [rax+rax+00h]
0x180043fa3  mov     [rdi], rax
0x180043fa6  test    rax, rax
0x180043fa9  jz      short loc_180043FBE
0x180043fab  mov     r9, rsi; unsigned __int64
0x180043fae  mov     r8, r14; unsigned __int16 *
0x180043fb1  mov     rdx, rbp; unsigned __int64
0x180043fb4  mov     rcx, rax; unsigned __int16 *
0x180043fb7  call    ?StringCchCopyNExW@@YAJPEAG_KPEBG1PEAPEAGPEA_KK@Z; StringCchCopyNExW(ushort *,unsigned __int64,ushort const *,unsigned __int64,ushort * *,unsigned __int64 *,ulong)
0x180043fbc  jmp     short loc_180043FCE
0x180043fbe  mov     ebx, 8007000Eh
0x180043fc3  jmp     short loc_180043FCE
0x180043fc5  mov     ebx, eax
0x180043fc7  jmp     short loc_180043FCE
0x180043fc9  mov     ebx, 80070216h
0x180043fce  mov     rbp, [rsp+58h+arg_10]
0x180043fd3  mov     eax, ebx
0x180043fd5  mov     rbx, [rsp+58h+arg_8]
0x180043fda  add     rsp, 40h
0x180043fde  pop     r14
0x180043fe0  pop     rdi
0x180043fe1  pop     rsi
0x180043fe2  retn
```
