# ParseAppUserModelId(ushort const *,ushort * *,ushort * *)

- ea: `0x180046c84`
- end: `0x180046d66`
- name: `?ParseAppUserModelId@@YAJPEBGPEAPEAG1@Z`
- size: `226`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003106c`
- `0x18004a7a0`

## callees

- `0x180003390`
- `0x18001e19c`
- `0x180046c84`
- `0x180046d6c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046d3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180046d3d`

## pseudocode

```c
__int64 __fastcall ParseAppUserModelId(const unsigned __int16 *a1, LPVOID *a2, unsigned __int16 **a3)
{
  int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rsi
  int v9; // edi
  __int64 v10; // r9
  unsigned __int64 v12; // [rsp+20h] [rbp-168h]
  unsigned __int16 v13[72]; // [rsp+30h] [rbp-158h] BYREF
  unsigned __int16 v14[72]; // [rsp+C0h] [rbp-C8h] BYREF

  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  v5 = ParseAppUserModelId(a1, v13, (unsigned __int64)a3, v14, v12);
  v8 = -1;
  v9 = v5;
  if ( a2 && v5 >= 0 )
  {
    v10 = -1;
    do
      ++v10;
    while ( v13[v10] );
    v9 = _AllocStringWorker<CTCoAllocPolicy>(v7, v6, v13);
  }
  if ( a3 && v9 >= 0 )
  {
    do
      ++v8;
    while ( v14[v8] );
    v9 = _AllocStringWorker<CTCoAllocPolicy>(v7, v6, v14);
    if ( v9 < 0 && a2 )
    {
      CoTaskMemFree(*a2);
      *a2 = 0;
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180046c84  push    rbx
0x180046c86  push    rbp
0x180046c87  push    rsi
0x180046c88  push    rdi
0x180046c89  push    r14
0x180046c8b  sub     rsp, 160h
0x180046c92  mov     rax, cs:__security_cookie
0x180046c99  xor     rax, rsp
0x180046c9c  mov     [rsp+188h+var_38], rax
0x180046ca4  xor     ebp, ebp
0x180046ca6  mov     r14, r8
0x180046ca9  mov     rbx, rdx
0x180046cac  test    rdx, rdx
0x180046caf  jz      short loc_180046CB4
0x180046cb1  mov     [rdx], rbp
0x180046cb4  test    r14, r14
0x180046cb7  jz      short loc_180046CBC
0x180046cb9  mov     [r8], rbp
0x180046cbc  lea     r9, [rsp+188h+var_C8]; unsigned __int16 *
0x180046cc4  lea     rdx, [rsp+188h+var_158]; unsigned __int16 *
0x180046cc9  call    ?ParseAppUserModelId@@YAJPEBGPEAG_K12@Z; ParseAppUserModelId(ushort const *,ushort *,unsigned __int64,ushort *,unsigned __int64)
0x180046cce  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180046cd2  mov     edi, eax
0x180046cd4  test    rbx, rbx
0x180046cd7  jz      short loc_180046D00
0x180046cd9  test    eax, eax
0x180046cdb  js      short loc_180046D00
0x180046cdd  lea     rax, [rsp+188h+var_158]
0x180046ce2  mov     r9, rsi
0x180046ce5  inc     r9
0x180046ce8  cmp     [rax+r9*2], bp
0x180046ced  jnz     short loc_180046CE5
0x180046cef  lea     r8, [rsp+188h+var_158]
0x180046cf4  mov     [rsp+188h+var_160], rbx
0x180046cf9  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180046cfe  mov     edi, eax
0x180046d00  test    r14, r14
0x180046d03  jz      short loc_180046D46
0x180046d05  test    edi, edi
0x180046d07  js      short loc_180046D46
0x180046d09  lea     rax, [rsp+188h+var_C8]
0x180046d11  inc     rsi
0x180046d14  cmp     [rax+rsi*2], bp
0x180046d18  jnz     short loc_180046D11
0x180046d1a  mov     r9, rsi
0x180046d1d  mov     [rsp+188h+var_160], r14
0x180046d22  lea     r8, [rsp+188h+var_C8]
0x180046d2a  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180046d2f  mov     edi, eax
0x180046d31  test    eax, eax
0x180046d33  jns     short loc_180046D46
0x180046d35  test    rbx, rbx
0x180046d38  jz      short loc_180046D46
0x180046d3a  mov     rcx, [rbx]; pv
0x180046d3d  call    cs:__imp_CoTaskMemFree
0x180046d43  mov     [rbx], rbp
0x180046d46  mov     eax, edi
0x180046d48  mov     rcx, [rsp+188h+var_38]
0x180046d50  xor     rcx, rsp; StackCookie
0x180046d53  call    __security_check_cookie
0x180046d58  add     rsp, 160h
0x180046d5f  pop     r14
0x180046d61  pop     rdi
0x180046d62  pop     rsi
0x180046d63  pop     rbp
0x180046d64  pop     rbx
0x180046d65  retn
```
