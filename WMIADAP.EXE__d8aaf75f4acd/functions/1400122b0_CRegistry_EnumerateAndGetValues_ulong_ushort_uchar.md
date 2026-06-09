# CRegistry::EnumerateAndGetValues(ulong &,ushort * &,uchar * &)

- ea: `0x1400122b0`
- end: `0x14001242a`
- name: `?EnumerateAndGetValues@CRegistry@@QEAAJAEAKAEAPEAGAEAPEAE@Z`
- size: `378`
- prototype: `__int64 __fastcall(CRegistry *__hidden this, unsigned int *, unsigned __int16 **, unsigned __int8 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000f91c`

## callees

- `0x14000298c`
- `0x1400122b0`

## import_xrefs

- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140012361`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1400123ce`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1400123da`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x140012361`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1400123ce`
- `wbemcomn!?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z` at `0x1400123da`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140012312`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140012350`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140012312`
- `wbemcomn!?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z` at `0x140012350`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1400123b4`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1400123b4`

## pseudocode

```c
__int64 __fastcall CRegistry::EnumerateAndGetValues(
        CRegistry *this,
        unsigned int *a2,
        unsigned __int16 **a3,
        unsigned __int8 **a4)
{
  __int64 v5; // rsi
  DWORD v6; // r12d
  __int64 v8; // r14
  unsigned __int16 *v11; // rax
  unsigned __int8 *lpData; // rax
  LSTATUS v13; // eax
  _WORD *v14; // rdx
  unsigned int v15; // r15d
  _BYTE *v16; // rcx
  DWORD Type[4]; // [rsp+40h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+90h] [rbp+40h] BYREF
  DWORD cchValueName; // [rsp+98h] [rbp+48h] BYREF
  int pExceptionObject; // [rsp+A0h] [rbp+50h] BYREF

  v5 = (unsigned int)(*((_DWORD *)this + 145) + 2);
  v6 = *a2;
  v8 = (unsigned int)(*((_DWORD *)this + 146) + 2);
  Type[0] = 0;
  cchValueName = v5;
  cbData = v8;
  v11 = (unsigned __int16 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul((unsigned int)(v5 + 2), 2u));
  *a3 = v11;
  if ( !v11 )
  {
    pExceptionObject = 0;
    throw (CHeap_Exception *)&pExceptionObject;
  }
  lpData = (unsigned __int8 *)CWin32DefaultArena::WbemMemAlloc(saturated_mul(cbData + 2, 2u));
  *a4 = lpData;
  if ( !lpData )
  {
    CWin32DefaultArena::WbemMemFree(*a3);
    *a3 = 0;
    pExceptionObject = 0;
    throw (CHeap_Exception *)&pExceptionObject;
  }
  v13 = RegEnumValueW(*((HKEY *)this + 1), v6, *a3, &cchValueName, 0, Type, lpData, &cbData);
  *a2 = v6;
  v14 = *a3;
  v15 = v13;
  if ( v13 )
  {
    CWin32DefaultArena::WbemMemFree(*a3);
    *a3 = 0;
    CWin32DefaultArena::WbemMemFree(*a4);
    *a4 = 0;
  }
  else
  {
    if ( cchValueName > (unsigned int)v5 )
      v14[v5] = 0;
    else
      v14[cchValueName] = 0;
    v16 = *a4;
    if ( cbData > (unsigned int)v8 )
      v16[v8] = 0;
    else
      v16[cbData] = 0;
  }
  return v15;
}

```

## disassembly

```asm
0x1400122b0  mov     [rsp-38h+arg_18], rbx
0x1400122b5  push    rbp
0x1400122b6  push    rsi
0x1400122b7  push    rdi
0x1400122b8  push    r12
0x1400122ba  push    r13
0x1400122bc  push    r14
0x1400122be  push    r15
0x1400122c0  mov     rbp, rsp
0x1400122c3  sub     rsp, 50h
0x1400122c7  mov     esi, [rcx+244h]
0x1400122cd  mov     r15, rcx
0x1400122d0  mov     r14d, [rcx+248h]
0x1400122d7  add     esi, 2
0x1400122da  mov     r12d, [rdx]
0x1400122dd  mov     rdi, r8
0x1400122e0  add     r14d, 2
0x1400122e4  mov     [rbp+Type], 0
0x1400122eb  mov     r13, rdx
0x1400122ee  mov     [rbp+cchValueName], esi
0x1400122f1  lea     r8d, [rsi+2]
0x1400122f5  mov     [rbp+cbData], r14d
0x1400122f9  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140012300  mov     eax, 2
0x140012305  mul     r8
0x140012308  mov     rbx, r9
0x14001230b  cmovb   rax, rcx
0x14001230f  mov     rcx, rax
0x140012312  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x140012318  mov     [rdi], rax
0x14001231b  test    rax, rax
0x14001231e  jnz     short loc_140012334
0x140012320  lea     rdx, _TI1?AVCHeap_Exception@@; pThrowInfo
0x140012327  mov     [rbp+pExceptionObject], eax
0x14001232a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x14001232e  call    _CxxThrowException_0
0x140012334  mov     edx, [rbp+cbData]
0x140012337  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14001233e  add     edx, 2
0x140012341  mov     eax, 2
0x140012346  mul     rdx
0x140012349  cmovb   rax, rcx
0x14001234d  mov     rcx, rax
0x140012350  call    cs:__imp_?WbemMemAlloc@CWin32DefaultArena@@SAPEAX_K@Z; CWin32DefaultArena::WbemMemAlloc(unsigned __int64)
0x140012356  mov     [rbx], rax
0x140012359  test    rax, rax
0x14001235c  jnz     short loc_140012386
0x14001235e  mov     rcx, [rdi]
0x140012361  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x140012367  lea     rdx, _TI1?AVCHeap_Exception@@; pThrowInfo
0x14001236e  mov     qword ptr [rdi], 0
0x140012375  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x140012379  mov     [rbp+pExceptionObject], 0
0x140012380  call    _CxxThrowException_0
0x140012386  mov     r8, [rdi]; lpValueName
0x140012389  lea     rcx, [rbp+cbData]
0x14001238d  mov     [rsp+50h+lpcbData], rcx; lpcbData
0x140012392  lea     r9, [rbp+cchValueName]; lpcchValueName
0x140012396  mov     rcx, [r15+8]; hKey
0x14001239a  mov     edx, r12d; dwIndex
0x14001239d  mov     [rsp+50h+lpData], rax; lpData
0x1400123a2  lea     rax, [rbp+Type]
0x1400123a6  mov     [rsp+50h+lpType], rax; lpType
0x1400123ab  mov     [rsp+50h+lpReserved], 0; lpReserved
0x1400123b4  call    cs:__imp_RegEnumValueW
0x1400123ba  mov     [r13+0], r12d
0x1400123be  xor     r12d, r12d
0x1400123c1  mov     rdx, [rdi]
0x1400123c4  mov     r15d, eax
0x1400123c7  test    eax, eax
0x1400123c9  jz      short loc_1400123E5
0x1400123cb  mov     rcx, rdx
0x1400123ce  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1400123d4  mov     [rdi], r12
0x1400123d7  mov     rcx, [rbx]
0x1400123da  call    cs:__imp_?WbemMemFree@CWin32DefaultArena@@SAHPEAX@Z; CWin32DefaultArena::WbemMemFree(void *)
0x1400123e0  mov     [rbx], r12
0x1400123e3  jmp     short loc_14001240F
0x1400123e5  cmp     [rbp+cchValueName], esi
0x1400123e8  ja      short loc_1400123F4
0x1400123ea  mov     ecx, [rbp+cchValueName]
0x1400123ed  mov     [rdx+rcx*2], r12w
0x1400123f2  jmp     short loc_1400123F9
0x1400123f4  mov     [rdx+rsi*2], r12w
0x1400123f9  mov     rcx, [rbx]
0x1400123fc  cmp     [rbp+cbData], r14d
0x140012400  ja      short loc_14001240B
0x140012402  mov     eax, [rbp+cbData]
0x140012405  mov     [rax+rcx], r12b
0x140012409  jmp     short loc_14001240F
0x14001240b  mov     [r14+rcx], r12b
0x14001240f  mov     rbx, [rsp+50h+arg_18]
0x140012417  mov     eax, r15d
0x14001241a  add     rsp, 50h
0x14001241e  pop     r15
0x140012420  pop     r14
0x140012422  pop     r13
0x140012424  pop     r12
0x140012426  pop     rdi
0x140012427  pop     rsi
0x140012428  pop     rbp
0x140012429  retn
```
