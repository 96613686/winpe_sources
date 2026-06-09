# DispMarshalInterface

- ea: `0x1800987d4`
- end: `0x18009886a`
- name: `DispMarshalInterface`
- size: `150`
- prototype: `__int64 __fastcall(LPSTREAM pStm, IID *riid, LPUNKNOWN pUnk)`
- caller_count: `14`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180081b4c`
- `0x180082294`
- `0x180082868`
- `0x180082974`
- `0x1800838b8`
- `0x180083b94`
- `0x1800844b8`
- `0x180084d94`
- `0x180084e28`
- `0x180084ef8`
- `0x180085524`
- `0x18008575c`
- `0x1800975dc`
- `0x180098304`

## callees

- `0x1800987d4`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18009884d`
- `api-ms-win-core-com-l1-1-0!CoMarshalInterface` at `0x18009884d`

## pseudocode

```c
HRESULT __fastcall DispMarshalInterface(LPSTREAM pStm, IID *riid, LPUNKNOWN pUnk)
{
  __int64 (__fastcall *v6)(LPSTREAM, char *, __int64); // rax
  int v7; // ecx
  HRESULT result; // eax
  char v9; // [rsp+50h] [rbp+18h] BYREF

  v6 = *(__int64 (__fastcall **)(LPSTREAM, char *, __int64))(*(_QWORD *)pStm + 32LL);
  if ( pUnk )
  {
    v9 = 0;
    result = v6(pStm, &v9, 1);
    if ( result > -1 )
    {
      result = CoMarshalInterface(pStm, riid, pUnk, 0, 0, 0);
      if ( result >= 0 )
        return 0;
    }
  }
  else
  {
    v9 = 1;
    v7 = ((__int64 (__fastcall *)(LPSTREAM, char *))v6)(pStm, &v9);
    if ( v7 )
    {
      result = 0;
      if ( v7 < 0 )
        return v7;
    }
    else
    {
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800987d4  mov     [rsp+arg_0], rbx
0x1800987d9  mov     [rsp+arg_8], rsi
0x1800987de  push    rdi
0x1800987df  sub     rsp, 30h
0x1800987e3  mov     rax, [rcx]
0x1800987e6  xor     r9d, r9d
0x1800987e9  mov     rdi, r8
0x1800987ec  mov     rsi, rdx
0x1800987ef  test    r8, r8
0x1800987f2  lea     rdx, [rsp+38h+arg_10]
0x1800987f7  mov     rbx, rcx
0x1800987fa  mov     rax, [rax+20h]
0x1800987fe  lea     r8d, [r9+1]
0x180098802  jnz     short loc_180098821
0x180098804  mov     [rsp+38h+arg_10], r8b
0x180098809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009880e  mov     ecx, eax
0x180098810  test    eax, eax
0x180098812  jz      short loc_18009881D
0x180098814  xor     eax, eax
0x180098816  test    ecx, ecx
0x180098818  cmovs   eax, ecx
0x18009881b  jmp     short loc_18009885A
0x18009881d  xor     eax, eax
0x18009881f  jmp     short loc_18009885A
0x180098821  mov     [rsp+38h+arg_10], 0
0x180098826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009882b  cmp     eax, 0FFFFFFFFh
0x18009882e  jle     short loc_18009885A
0x180098830  mov     [rsp+38h+mshlflags], 0; mshlflags
0x180098838  xor     r9d, r9d; dwDestContext
0x18009883b  mov     r8, rdi; pUnk
0x18009883e  mov     [rsp+38h+pvDestContext], 0; pvDestContext
0x180098847  mov     rdx, rsi; riid
0x18009884a  mov     rcx, rbx; pStm
0x18009884d  call    cs:__imp_CoMarshalInterface
0x180098853  xor     ecx, ecx
0x180098855  test    eax, eax
0x180098857  cmovns  eax, ecx
0x18009885a  mov     rbx, [rsp+38h+arg_0]
0x18009885f  mov     rsi, [rsp+38h+arg_8]
0x180098864  add     rsp, 30h
0x180098868  pop     rdi
0x180098869  retn
```
