# ComUtils::GitComLockableWrapper<ITablet>::GitComLockableWrapper<ITablet>(ATL::CComPtr<ITablet>,ComUtils::ComApartmentVerifier)

- ea: `0x18000a164`
- end: `0x18000a325`
- name: `??0?$GitComLockableWrapper@UITablet@@@ComUtils@@QEAA@V?$CComPtr@UITablet@@@ATL@@VComApartmentVerifier@1@@Z`
- size: `449`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008170`

## callees

- `0x180004484`
- `0x18000a164`
- `0x18000e4a0`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18000a1c7`
- `ole32!CoCreateInstance` at `0x18000a28c`
- `ole32!CoCreateInstance` at `0x18000a1c7`
- `ole32!CoCreateInstance` at `0x18000a28c`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall ComUtils::GitComLockableWrapper<ITablet>::GitComLockableWrapper<ITablet>(
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
         &GUID_1cb2efc3_abc7_4172_8fcb_3bc9cb93e29f,
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
0x18000a164  mov     [rsp-30h+arg_8], rdx
0x18000a169  push    rbp
0x18000a16a  push    rbx
0x18000a16b  push    rsi
0x18000a16c  push    rdi
0x18000a16d  push    r14
0x18000a16f  push    r15
0x18000a171  mov     rbp, rsp
0x18000a174  sub     rsp, 38h
0x18000a178  mov     rsi, rdx
0x18000a17b  mov     rdi, rcx
0x18000a17e  movaps  xmm0, xmmword ptr [r8]
0x18000a182  movdqu  xmmword ptr [rcx+4], xmm0
0x18000a187  mov     r14, [rdx]
0x18000a18a  xor     r15d, r15d
0x18000a18d  mov     [rbp+arg_0], r15d
0x18000a191  test    r14, r14
0x18000a194  jz      loc_18000A24C
0x18000a19a  mov     [rbp+arg_10], r15
0x18000a19e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000a1a5  test    rcx, rcx
0x18000a1a8  jnz     short loc_18000A1CF
0x18000a1aa  lea     rax, [rbp+arg_10]
0x18000a1ae  mov     [rsp+38h+ppv], rax; ppv
0x18000a1b3  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000a1ba  xor     edx, edx; pUnkOuter
0x18000a1bc  lea     r8d, [r15+1]; dwClsContext
0x18000a1c0  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000a1c7  call    cs:__imp_CoCreateInstance
0x18000a1cd  jmp     short loc_18000A1E0
0x18000a1cf  mov     rax, [rcx]
0x18000a1d2  lea     rdx, [rbp+arg_10]
0x18000a1d6  mov     rax, [rax+20h]
0x18000a1da  call    cs:__guard_dispatch_icall_fptr
0x18000a1e0  mov     ebx, eax
0x18000a1e2  test    eax, eax
0x18000a1e4  js      loc_18000A307
0x18000a1ea  mov     edx, [rbp+arg_0]
0x18000a1ed  test    edx, edx
0x18000a1ef  jz      short loc_18000A20D
0x18000a1f1  mov     rcx, [rbp+arg_10]
0x18000a1f5  mov     rax, [rcx]
0x18000a1f8  mov     rax, [rax+20h]
0x18000a1fc  call    cs:__guard_dispatch_icall_fptr
0x18000a202  mov     ebx, eax
0x18000a204  test    eax, eax
0x18000a206  jns     short loc_18000A20D
0x18000a208  jmp     loc_18000A307
0x18000a20d  mov     rcx, [rbp+arg_10]
0x18000a211  mov     rax, [rcx]
0x18000a214  lea     r9, [rbp+arg_0]
0x18000a218  lea     r8, _GUID_1cb2efc3_abc7_4172_8fcb_3bc9cb93e29f
0x18000a21f  mov     rdx, r14
0x18000a222  mov     rax, [rax+18h]
0x18000a226  call    cs:__guard_dispatch_icall_fptr
0x18000a22c  mov     ebx, eax
0x18000a22e  mov     rcx, [rbp+arg_10]
0x18000a232  test    rcx, rcx
0x18000a235  jz      short loc_18000A244
0x18000a237  mov     rax, [rcx]
0x18000a23a  mov     rax, [rax+10h]
0x18000a23e  call    cs:__guard_dispatch_icall_fptr
0x18000a244  test    ebx, ebx
0x18000a246  js      loc_18000A31D
0x18000a24c  mov     eax, [rbp+arg_0]
0x18000a24f  mov     [rbp+arg_0], r15d
0x18000a253  mov     [rdi], eax
0x18000a255  cmp     [rbp+arg_0], r15d
0x18000a259  jz      loc_18000A2E2
0x18000a25f  mov     [rbp+arg_18], r15
0x18000a263  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000a26a  test    rcx, rcx
0x18000a26d  jnz     short loc_18000A294
0x18000a26f  lea     rax, [rbp+arg_18]
0x18000a273  mov     [rsp+38h+ppv], rax; ppv
0x18000a278  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000a27f  xor     edx, edx; pUnkOuter
0x18000a281  lea     r8d, [rcx+1]; dwClsContext
0x18000a285  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000a28c  call    cs:__imp_CoCreateInstance
0x18000a292  jmp     short loc_18000A2A5
0x18000a294  mov     rax, [rcx]
0x18000a297  lea     rdx, [rbp+arg_18]
0x18000a29b  mov     rax, [rax+20h]
0x18000a29f  call    cs:__guard_dispatch_icall_fptr
0x18000a2a5  test    eax, eax
0x18000a2a7  jns     short loc_18000A2AB
0x18000a2a9  jmp     short loc_18000A2CB
0x18000a2ab  mov     rcx, [rbp+arg_18]
0x18000a2af  mov     rax, [rcx]
0x18000a2b2  mov     edx, [rbp+arg_0]
0x18000a2b5  mov     rax, [rax+20h]
0x18000a2b9  call    cs:__guard_dispatch_icall_fptr
0x18000a2bf  mov     ecx, [rbp+arg_0]
0x18000a2c2  test    eax, eax
0x18000a2c4  cmovns  ecx, r15d
0x18000a2c8  mov     [rbp+arg_0], ecx
0x18000a2cb  mov     rcx, [rbp+arg_18]
0x18000a2cf  test    rcx, rcx
0x18000a2d2  jz      short loc_18000A2E2
0x18000a2d4  mov     rax, [rcx]
0x18000a2d7  mov     rax, [rax+10h]
0x18000a2db  call    cs:__guard_dispatch_icall_fptr
0x18000a2e1  nop
0x18000a2e2  mov     rcx, [rsi]
0x18000a2e5  test    rcx, rcx
0x18000a2e8  jz      short loc_18000A2F7
0x18000a2ea  mov     rax, [rcx]
0x18000a2ed  mov     rax, [rax+10h]
0x18000a2f1  call    cs:__guard_dispatch_icall_fptr
0x18000a2f7  mov     rax, rdi
0x18000a2fa  add     rsp, 38h
0x18000a2fe  pop     r15
0x18000a300  pop     r14
0x18000a302  pop     rdi
0x18000a303  pop     rsi
0x18000a304  pop     rbx
0x18000a305  pop     rbp
0x18000a306  retn
0x18000a307  mov     rcx, [rbp+arg_10]
0x18000a30b  test    rcx, rcx
0x18000a30e  jz      short loc_18000A31D
0x18000a310  mov     rax, [rcx]
0x18000a313  mov     rax, [rax+10h]
0x18000a317  call    cs:__guard_dispatch_icall_fptr
0x18000a31d  mov     ecx, ebx; int
0x18000a31f  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
