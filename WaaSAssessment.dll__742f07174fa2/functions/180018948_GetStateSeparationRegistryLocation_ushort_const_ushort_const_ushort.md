# GetStateSeparationRegistryLocation(ushort const *,ushort const *,ushort * *)

- ea: `0x180018948`
- end: `0x180018a48`
- name: `?GetStateSeparationRegistryLocation@@YAJPEBG0PEAPEAG@Z`
- size: `256`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180007b50`
- `0x1800083c0`
- `0x1800089d0`
- `0x180009180`
- `0x18000d300`
- `0x18000d690`

## callees

- `0x180018948`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018a2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180018a2d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800189d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800189d5`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800189a3`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180018a09`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x1800189a3`
- `api-ms-win-stateseparation-helpers-l1-1-0!GetPersistedRegistryLocationW` at `0x180018a09`

## pseudocode

```c
__int64 __fastcall GetStateSeparationRegistryLocation(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  signed int v6; // edi
  int PersistedRegistryLocationW; // eax
  __int64 v8; // r9
  unsigned __int64 v9; // rdx
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // rbx
  int v12; // eax
  unsigned __int16 *v13; // rax
  unsigned __int16 *v15; // [rsp+50h] [rbp+8h] BYREF

  LODWORD(v15) = 0;
  if ( !a1 || (v6 = 0, !a2) )
    v6 = -2147024809;
  if ( a3 )
  {
    if ( v6 >= 0 )
    {
      PersistedRegistryLocationW = GetPersistedRegistryLocationW(a1, a2, 0, 0, &v15);
      v6 = PersistedRegistryLocationW;
      if ( PersistedRegistryLocationW > 0 )
        v6 = (unsigned __int16)PersistedRegistryLocationW | 0x80070000;
      if ( v6 == -2147024662 )
      {
        v8 = (unsigned int)v15;
        v9 = 2LL * (unsigned int)v15;
        if ( v9 > (unsigned int)v15 && (unsigned int)v9 == v9 )
        {
          v10 = (unsigned __int16 *)CoTaskMemAlloc((unsigned int)v9);
          v8 = (unsigned int)v15;
          v11 = v10;
        }
        else
        {
          v11 = v15;
        }
        if ( v11 )
        {
          v12 = GetPersistedRegistryLocationW(a1, a2, v11, v8, &v15);
          v6 = v12;
          if ( v12 > 0 )
            v6 = (unsigned __int16)v12 | 0x80070000;
          if ( v6 >= 0 )
          {
            v13 = v11;
            v11 = 0;
            *a3 = v13;
          }
        }
        else
        {
          v6 = -2147024882;
        }
        CoTaskMemFree(v11);
      }
    }
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180018948  mov     [rsp+arg_8], rbx
0x18001894d  mov     [rsp+arg_10], rbp
0x180018952  push    rsi
0x180018953  push    rdi
0x180018954  push    r14
0x180018956  sub     rsp, 30h
0x18001895a  mov     dword ptr [rsp+48h+arg_0], 0
0x180018962  mov     r14, r8
0x180018965  mov     rsi, rdx
0x180018968  mov     rbp, rcx
0x18001896b  test    rcx, rcx
0x18001896e  jz      short loc_180018977
0x180018970  xor     edi, edi
0x180018972  test    rdx, rdx
0x180018975  jnz     short loc_18001897C
0x180018977  mov     edi, 80070057h
0x18001897c  test    r14, r14
0x18001897f  jnz     short loc_18001898B
0x180018981  mov     edi, 80004003h
0x180018986  jmp     loc_180018A33
0x18001898b  test    edi, edi
0x18001898d  js      loc_180018A33
0x180018993  lea     rax, [rsp+48h+arg_0]
0x180018998  xor     r9d, r9d
0x18001899b  xor     r8d, r8d
0x18001899e  mov     [rsp+48h+var_28], rax
0x1800189a3  call    cs:__imp_GetPersistedRegistryLocationW
0x1800189a9  mov     edi, eax
0x1800189ab  test    eax, eax
0x1800189ad  jle     short loc_1800189B8
0x1800189af  movzx   edi, ax
0x1800189b2  or      edi, 80070000h
0x1800189b8  cmp     edi, 800700EAh
0x1800189be  jnz     short loc_180018A33
0x1800189c0  mov     r9d, dword ptr [rsp+48h+arg_0]
0x1800189c5  lea     rdx, [r9+r9]
0x1800189c9  cmp     rdx, r9
0x1800189cc  jbe     short loc_1800189E5
0x1800189ce  mov     ecx, edx; cb
0x1800189d0  cmp     rcx, rdx
0x1800189d3  jnz     short loc_1800189E5
0x1800189d5  call    cs:__imp_CoTaskMemAlloc
0x1800189db  mov     r9d, dword ptr [rsp+48h+arg_0]
0x1800189e0  mov     rbx, rax
0x1800189e3  jmp     short loc_1800189EA
0x1800189e5  mov     rbx, [rsp+48h+arg_0]
0x1800189ea  test    rbx, rbx
0x1800189ed  jnz     short loc_1800189F6
0x1800189ef  mov     edi, 8007000Eh
0x1800189f4  jmp     short loc_180018A2A
0x1800189f6  lea     rax, [rsp+48h+arg_0]
0x1800189fb  mov     r8, rbx
0x1800189fe  mov     rdx, rsi
0x180018a01  mov     [rsp+48h+var_28], rax
0x180018a06  mov     rcx, rbp
0x180018a09  call    cs:__imp_GetPersistedRegistryLocationW
0x180018a0f  mov     edi, eax
0x180018a11  test    eax, eax
0x180018a13  jle     short loc_180018A1E
0x180018a15  movzx   edi, ax
0x180018a18  or      edi, 80070000h
0x180018a1e  test    edi, edi
0x180018a20  js      short loc_180018A2A
0x180018a22  mov     rax, rbx
0x180018a25  xor     ebx, ebx
0x180018a27  mov     [r14], rax
0x180018a2a  mov     rcx, rbx; pv
0x180018a2d  call    cs:__imp_CoTaskMemFree
0x180018a33  mov     rbx, [rsp+48h+arg_8]
0x180018a38  mov     eax, edi
0x180018a3a  mov     rbp, [rsp+48h+arg_10]
0x180018a3f  add     rsp, 30h
0x180018a43  pop     r14
0x180018a45  pop     rdi
0x180018a46  pop     rsi
0x180018a47  retn
```
