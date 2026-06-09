# ComUtils::GitComLockableWrapper<ITabletManager>::GitComLockableWrapper<ITabletManager>(ATL::CComPtr<ITabletManager>,ComUtils::ComApartmentVerifier)

- ea: `0x18000c198`
- end: `0x18000c359`
- name: `??0?$GitComLockableWrapper@UITabletManager@@@ComUtils@@QEAA@V?$CComPtr@UITabletManager@@@ATL@@VComApartmentVerifier@1@@Z`
- size: `449`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a49c`

## callees

- `0x180004484`
- `0x18000c198`
- `0x18000e4a0`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000c1fb`
- `ole32!CoCreateInstance` at `0x18000c2c0`
- `ole32!CoCreateInstance` at `0x18000c1fb`
- `ole32!CoCreateInstance` at `0x18000c2c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall ComUtils::GitComLockableWrapper<ITabletManager>::GitComLockableWrapper<ITabletManager>(
        __int64 a1,
        _QWORD *a2,
        _OWORD *a3)
{
  __int64 v5; // r14
  HRESULT v6; // eax
  int v7; // ebx
  unsigned int v8; // eax
  HRESULT v9; // eax
  int v10; // eax
  unsigned int v11; // ecx
  unsigned int v13; // [rsp+70h] [rbp+38h] BYREF
  _QWORD *v14; // [rsp+78h] [rbp+40h]
  LPVOID ppv; // [rsp+80h] [rbp+48h] BYREF
  LPVOID v16; // [rsp+88h] [rbp+50h] BYREF

  v14 = a2;
  *(_OWORD *)(a1 + 4) = *a3;
  v5 = *a2;
  v13 = 0;
  if ( !v5 )
    goto LABEL_11;
  ppv = 0;
  if ( ATL::_pAtlModule )
    v6 = (*(__int64 (__fastcall **)(struct ATL::CAtlModule *, LPVOID *))(*(_QWORD *)ATL::_pAtlModule + 32LL))(
           ATL::_pAtlModule,
           &ppv);
  else
    v6 = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv);
  v7 = v6;
  if ( v6 < 0 || v13 && (v7 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 32LL))(ppv), v7 < 0) )
  {
    if ( ppv )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
LABEL_26:
    ATL::AtlThrowImpl(v7);
  }
  v7 = (*(__int64 (__fastcall **)(LPVOID, __int64, GUID *, unsigned int *))(*(_QWORD *)ppv + 24LL))(
         ppv,
         v5,
         &GUID_764de8aa_1867_47c1_8f6a_122445abd89a,
         &v13);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( v7 < 0 )
    goto LABEL_26;
LABEL_11:
  v8 = v13;
  v13 = 0;
  *(_DWORD *)a1 = v8;
  if ( v13 )
  {
    v16 = 0;
    if ( ATL::_pAtlModule )
      v9 = (*(__int64 (__fastcall **)(struct ATL::CAtlModule *, LPVOID *))(*(_QWORD *)ATL::_pAtlModule + 32LL))(
             ATL::_pAtlModule,
             &v16);
    else
      v9 = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &v16);
    if ( v9 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v16 + 32LL))(v16, v13);
      v11 = v13;
      if ( v10 >= 0 )
        v11 = 0;
      v13 = v11;
    }
    if ( v16 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
  }
  if ( *a2 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
  return a1;
}

```

## disassembly

```asm
0x18000c198  mov     [rsp-30h+arg_8], rdx
0x18000c19d  push    rbp
0x18000c19e  push    rbx
0x18000c19f  push    rsi
0x18000c1a0  push    rdi
0x18000c1a1  push    r14
0x18000c1a3  push    r15
0x18000c1a5  mov     rbp, rsp
0x18000c1a8  sub     rsp, 38h
0x18000c1ac  mov     rsi, rdx
0x18000c1af  mov     rdi, rcx
0x18000c1b2  movaps  xmm0, xmmword ptr [r8]
0x18000c1b6  movdqu  xmmword ptr [rcx+4], xmm0
0x18000c1bb  mov     r14, [rdx]
0x18000c1be  xor     r15d, r15d
0x18000c1c1  mov     [rbp+arg_0], r15d
0x18000c1c5  test    r14, r14
0x18000c1c8  jz      loc_18000C280
0x18000c1ce  mov     [rbp+arg_10], r15
0x18000c1d2  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000c1d9  test    rcx, rcx
0x18000c1dc  jnz     short loc_18000C203
0x18000c1de  lea     rax, [rbp+arg_10]
0x18000c1e2  mov     [rsp+38h+ppv], rax; ppv
0x18000c1e7  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000c1ee  xor     edx, edx; pUnkOuter
0x18000c1f0  lea     r8d, [r15+1]; dwClsContext
0x18000c1f4  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000c1fb  call    cs:__imp_CoCreateInstance
0x18000c201  jmp     short loc_18000C214
0x18000c203  mov     rax, [rcx]
0x18000c206  lea     rdx, [rbp+arg_10]
0x18000c20a  mov     rax, [rax+20h]
0x18000c20e  call    cs:__guard_dispatch_icall_fptr
0x18000c214  mov     ebx, eax
0x18000c216  test    eax, eax
0x18000c218  js      loc_18000C33B
0x18000c21e  mov     edx, [rbp+arg_0]
0x18000c221  test    edx, edx
0x18000c223  jz      short loc_18000C241
0x18000c225  mov     rcx, [rbp+arg_10]
0x18000c229  mov     rax, [rcx]
0x18000c22c  mov     rax, [rax+20h]
0x18000c230  call    cs:__guard_dispatch_icall_fptr
0x18000c236  mov     ebx, eax
0x18000c238  test    eax, eax
0x18000c23a  jns     short loc_18000C241
0x18000c23c  jmp     loc_18000C33B
0x18000c241  mov     rcx, [rbp+arg_10]
0x18000c245  mov     rax, [rcx]
0x18000c248  lea     r9, [rbp+arg_0]
0x18000c24c  lea     r8, _GUID_764de8aa_1867_47c1_8f6a_122445abd89a
0x18000c253  mov     rdx, r14
0x18000c256  mov     rax, [rax+18h]
0x18000c25a  call    cs:__guard_dispatch_icall_fptr
0x18000c260  mov     ebx, eax
0x18000c262  mov     rcx, [rbp+arg_10]
0x18000c266  test    rcx, rcx
0x18000c269  jz      short loc_18000C278
0x18000c26b  mov     rax, [rcx]
0x18000c26e  mov     rax, [rax+10h]
0x18000c272  call    cs:__guard_dispatch_icall_fptr
0x18000c278  test    ebx, ebx
0x18000c27a  js      loc_18000C351
0x18000c280  mov     eax, [rbp+arg_0]
0x18000c283  mov     [rbp+arg_0], r15d
0x18000c287  mov     [rdi], eax
0x18000c289  cmp     [rbp+arg_0], r15d
0x18000c28d  jz      loc_18000C316
0x18000c293  mov     [rbp+arg_18], r15
0x18000c297  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000c29e  test    rcx, rcx
0x18000c2a1  jnz     short loc_18000C2C8
0x18000c2a3  lea     rax, [rbp+arg_18]
0x18000c2a7  mov     [rsp+38h+ppv], rax; ppv
0x18000c2ac  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000c2b3  xor     edx, edx; pUnkOuter
0x18000c2b5  lea     r8d, [rcx+1]; dwClsContext
0x18000c2b9  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000c2c0  call    cs:__imp_CoCreateInstance
0x18000c2c6  jmp     short loc_18000C2D9
0x18000c2c8  mov     rax, [rcx]
0x18000c2cb  lea     rdx, [rbp+arg_18]
0x18000c2cf  mov     rax, [rax+20h]
0x18000c2d3  call    cs:__guard_dispatch_icall_fptr
0x18000c2d9  test    eax, eax
0x18000c2db  jns     short loc_18000C2DF
0x18000c2dd  jmp     short loc_18000C2FF
0x18000c2df  mov     rcx, [rbp+arg_18]
0x18000c2e3  mov     rax, [rcx]
0x18000c2e6  mov     edx, [rbp+arg_0]
0x18000c2e9  mov     rax, [rax+20h]
0x18000c2ed  call    cs:__guard_dispatch_icall_fptr
0x18000c2f3  mov     ecx, [rbp+arg_0]
0x18000c2f6  test    eax, eax
0x18000c2f8  cmovns  ecx, r15d
0x18000c2fc  mov     [rbp+arg_0], ecx
0x18000c2ff  mov     rcx, [rbp+arg_18]
0x18000c303  test    rcx, rcx
0x18000c306  jz      short loc_18000C316
0x18000c308  mov     rax, [rcx]
0x18000c30b  mov     rax, [rax+10h]
0x18000c30f  call    cs:__guard_dispatch_icall_fptr
0x18000c315  nop
0x18000c316  mov     rcx, [rsi]
0x18000c319  test    rcx, rcx
0x18000c31c  jz      short loc_18000C32B
0x18000c31e  mov     rax, [rcx]
0x18000c321  mov     rax, [rax+10h]
0x18000c325  call    cs:__guard_dispatch_icall_fptr
0x18000c32b  mov     rax, rdi
0x18000c32e  add     rsp, 38h
0x18000c332  pop     r15
0x18000c334  pop     r14
0x18000c336  pop     rdi
0x18000c337  pop     rsi
0x18000c338  pop     rbx
0x18000c339  pop     rbp
0x18000c33a  retn
0x18000c33b  mov     rcx, [rbp+arg_10]
0x18000c33f  test    rcx, rcx
0x18000c342  jz      short loc_18000C351
0x18000c344  mov     rax, [rcx]
0x18000c347  mov     rax, [rax+10h]
0x18000c34b  call    cs:__guard_dispatch_icall_fptr
0x18000c351  mov     ecx, ebx; int
0x18000c353  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
