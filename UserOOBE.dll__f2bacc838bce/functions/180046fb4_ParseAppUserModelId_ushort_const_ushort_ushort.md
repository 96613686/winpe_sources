# ParseAppUserModelId(ushort const *,ushort * *,ushort * *)

- ea: `0x180046fb4`
- end: `0x18004709f`
- name: `?ParseAppUserModelId@@YAJPEBGPEAPEAG1@Z`
- size: `235`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800423bc`
- `0x18004b254`

## callees

- `0x1800032b0`
- `0x180022a84`
- `0x180046fb4`
- `0x1800470a8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047076`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047076`

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
  unsigned __int16 v12[72]; // [rsp+30h] [rbp-158h] BYREF
  unsigned __int16 v13[72]; // [rsp+C0h] [rbp-C8h] BYREF

  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = 0;
  v5 = ParseAppUserModelId(a1, v12, (unsigned __int64)a3, v13, 0x41u);
  v8 = -1;
  v9 = v5;
  if ( a2 && v5 >= 0 )
  {
    v10 = -1;
    do
      ++v10;
    while ( v12[v10] );
    v9 = _AllocStringWorker<CTCoAllocPolicy>(v7, v6, v12, v10);
  }
  if ( a3 && v9 >= 0 )
  {
    do
      ++v8;
    while ( v13[v8] );
    v9 = _AllocStringWorker<CTCoAllocPolicy>(v7, v6, v13, v8);
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
0x180046fb4  push    rbx
0x180046fb6  push    rbp
0x180046fb7  push    rsi
0x180046fb8  push    rdi
0x180046fb9  push    r14
0x180046fbb  sub     rsp, 160h
0x180046fc2  mov     rax, cs:__security_cookie
0x180046fc9  xor     rax, rsp
0x180046fcc  mov     [rsp+188h+var_38], rax
0x180046fd4  xor     ebp, ebp
0x180046fd6  mov     r14, r8
0x180046fd9  mov     rbx, rdx
0x180046fdc  test    rdx, rdx
0x180046fdf  jz      short loc_180046FE4
0x180046fe1  mov     [rdx], rbp
0x180046fe4  test    r14, r14
0x180046fe7  jz      short loc_180046FEC
0x180046fe9  mov     [r8], rbp
0x180046fec  lea     r9, [rsp+188h+var_C8]; unsigned __int16 *
0x180046ff4  mov     [rsp+188h+var_168], 41h ; 'A'; unsigned __int64
0x180046ffd  lea     rdx, [rsp+188h+var_158]; unsigned __int16 *
0x180047002  call    ?ParseAppUserModelId@@YAJPEBGPEAG_K12@Z; ParseAppUserModelId(ushort const *,ushort *,unsigned __int64,ushort *,unsigned __int64)
0x180047007  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18004700b  mov     edi, eax
0x18004700d  test    rbx, rbx
0x180047010  jz      short loc_180047039
0x180047012  test    eax, eax
0x180047014  js      short loc_180047039
0x180047016  lea     rax, [rsp+188h+var_158]
0x18004701b  mov     r9, rsi
0x18004701e  inc     r9
0x180047021  cmp     [rax+r9*2], bp
0x180047026  jnz     short loc_18004701E
0x180047028  lea     r8, [rsp+188h+var_158]
0x18004702d  mov     [rsp+188h+var_160], rbx
0x180047032  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180047037  mov     edi, eax
0x180047039  test    r14, r14
0x18004703c  jz      short loc_18004707F
0x18004703e  test    edi, edi
0x180047040  js      short loc_18004707F
0x180047042  lea     rax, [rsp+188h+var_C8]
0x18004704a  inc     rsi
0x18004704d  cmp     [rax+rsi*2], bp
0x180047051  jnz     short loc_18004704A
0x180047053  mov     r9, rsi
0x180047056  mov     [rsp+188h+var_160], r14
0x18004705b  lea     r8, [rsp+188h+var_C8]
0x180047063  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180047068  mov     edi, eax
0x18004706a  test    eax, eax
0x18004706c  jns     short loc_18004707F
0x18004706e  test    rbx, rbx
0x180047071  jz      short loc_18004707F
0x180047073  mov     rcx, [rbx]; pv
0x180047076  call    cs:__imp_CoTaskMemFree
0x18004707c  mov     [rbx], rbp
0x18004707f  mov     eax, edi
0x180047081  mov     rcx, [rsp+188h+var_38]
0x180047089  xor     rcx, rsp; StackCookie
0x18004708c  call    __security_check_cookie
0x180047091  add     rsp, 160h
0x180047098  pop     r14
0x18004709a  pop     rdi
0x18004709b  pop     rsi
0x18004709c  pop     rbp
0x18004709d  pop     rbx
0x18004709e  retn
```
