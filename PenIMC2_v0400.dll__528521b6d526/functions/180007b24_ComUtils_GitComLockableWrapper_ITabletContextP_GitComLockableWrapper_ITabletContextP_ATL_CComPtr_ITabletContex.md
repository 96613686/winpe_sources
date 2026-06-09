# ComUtils::GitComLockableWrapper<ITabletContextP>::GitComLockableWrapper<ITabletContextP>(ATL::CComPtr<ITabletContextP>,ComUtils::ComApartmentVerifier)

- ea: `0x180007b24`
- end: `0x180007ce5`
- name: `??0?$GitComLockableWrapper@UITabletContextP@@@ComUtils@@QEAA@V?$CComPtr@UITabletContextP@@@ATL@@VComApartmentVerifier@1@@Z`
- size: `449`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800062a0`

## callees

- `0x180004484`
- `0x180007b24`
- `0x18000e4a0`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180007b87`
- `ole32!CoCreateInstance` at `0x180007c4c`
- `ole32!CoCreateInstance` at `0x180007b87`
- `ole32!CoCreateInstance` at `0x180007c4c`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall ComUtils::GitComLockableWrapper<ITabletContextP>::GitComLockableWrapper<ITabletContextP>(
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
         &GUID_22f74d0a_694f_4f47_a5ce_ae08a6409ac8,
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
0x180007b24  mov     [rsp-30h+arg_8], rdx
0x180007b29  push    rbp
0x180007b2a  push    rbx
0x180007b2b  push    rsi
0x180007b2c  push    rdi
0x180007b2d  push    r14
0x180007b2f  push    r15
0x180007b31  mov     rbp, rsp
0x180007b34  sub     rsp, 38h
0x180007b38  mov     rsi, rdx
0x180007b3b  mov     rdi, rcx
0x180007b3e  movaps  xmm0, xmmword ptr [r8]
0x180007b42  movdqu  xmmword ptr [rcx+4], xmm0
0x180007b47  mov     r14, [rdx]
0x180007b4a  xor     r15d, r15d
0x180007b4d  mov     [rbp+arg_0], r15d
0x180007b51  test    r14, r14
0x180007b54  jz      loc_180007C0C
0x180007b5a  mov     [rbp+arg_10], r15
0x180007b5e  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007b65  test    rcx, rcx
0x180007b68  jnz     short loc_180007B8F
0x180007b6a  lea     rax, [rbp+arg_10]
0x180007b6e  mov     [rsp+38h+ppv], rax; ppv
0x180007b73  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180007b7a  xor     edx, edx; pUnkOuter
0x180007b7c  lea     r8d, [r15+1]; dwClsContext
0x180007b80  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180007b87  call    cs:__imp_CoCreateInstance
0x180007b8d  jmp     short loc_180007BA0
0x180007b8f  mov     rax, [rcx]
0x180007b92  lea     rdx, [rbp+arg_10]
0x180007b96  mov     rax, [rax+20h]
0x180007b9a  call    cs:__guard_dispatch_icall_fptr
0x180007ba0  mov     ebx, eax
0x180007ba2  test    eax, eax
0x180007ba4  js      loc_180007CC7
0x180007baa  mov     edx, [rbp+arg_0]
0x180007bad  test    edx, edx
0x180007baf  jz      short loc_180007BCD
0x180007bb1  mov     rcx, [rbp+arg_10]
0x180007bb5  mov     rax, [rcx]
0x180007bb8  mov     rax, [rax+20h]
0x180007bbc  call    cs:__guard_dispatch_icall_fptr
0x180007bc2  mov     ebx, eax
0x180007bc4  test    eax, eax
0x180007bc6  jns     short loc_180007BCD
0x180007bc8  jmp     loc_180007CC7
0x180007bcd  mov     rcx, [rbp+arg_10]
0x180007bd1  mov     rax, [rcx]
0x180007bd4  lea     r9, [rbp+arg_0]
0x180007bd8  lea     r8, _GUID_22f74d0a_694f_4f47_a5ce_ae08a6409ac8
0x180007bdf  mov     rdx, r14
0x180007be2  mov     rax, [rax+18h]
0x180007be6  call    cs:__guard_dispatch_icall_fptr
0x180007bec  mov     ebx, eax
0x180007bee  mov     rcx, [rbp+arg_10]
0x180007bf2  test    rcx, rcx
0x180007bf5  jz      short loc_180007C04
0x180007bf7  mov     rax, [rcx]
0x180007bfa  mov     rax, [rax+10h]
0x180007bfe  call    cs:__guard_dispatch_icall_fptr
0x180007c04  test    ebx, ebx
0x180007c06  js      loc_180007CDD
0x180007c0c  mov     eax, [rbp+arg_0]
0x180007c0f  mov     [rbp+arg_0], r15d
0x180007c13  mov     [rdi], eax
0x180007c15  cmp     [rbp+arg_0], r15d
0x180007c19  jz      loc_180007CA2
0x180007c1f  mov     [rbp+arg_18], r15
0x180007c23  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180007c2a  test    rcx, rcx
0x180007c2d  jnz     short loc_180007C54
0x180007c2f  lea     rax, [rbp+arg_18]
0x180007c33  mov     [rsp+38h+ppv], rax; ppv
0x180007c38  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180007c3f  xor     edx, edx; pUnkOuter
0x180007c41  lea     r8d, [rcx+1]; dwClsContext
0x180007c45  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180007c4c  call    cs:__imp_CoCreateInstance
0x180007c52  jmp     short loc_180007C65
0x180007c54  mov     rax, [rcx]
0x180007c57  lea     rdx, [rbp+arg_18]
0x180007c5b  mov     rax, [rax+20h]
0x180007c5f  call    cs:__guard_dispatch_icall_fptr
0x180007c65  test    eax, eax
0x180007c67  jns     short loc_180007C6B
0x180007c69  jmp     short loc_180007C8B
0x180007c6b  mov     rcx, [rbp+arg_18]
0x180007c6f  mov     rax, [rcx]
0x180007c72  mov     edx, [rbp+arg_0]
0x180007c75  mov     rax, [rax+20h]
0x180007c79  call    cs:__guard_dispatch_icall_fptr
0x180007c7f  mov     ecx, [rbp+arg_0]
0x180007c82  test    eax, eax
0x180007c84  cmovns  ecx, r15d
0x180007c88  mov     [rbp+arg_0], ecx
0x180007c8b  mov     rcx, [rbp+arg_18]
0x180007c8f  test    rcx, rcx
0x180007c92  jz      short loc_180007CA2
0x180007c94  mov     rax, [rcx]
0x180007c97  mov     rax, [rax+10h]
0x180007c9b  call    cs:__guard_dispatch_icall_fptr
0x180007ca1  nop
0x180007ca2  mov     rcx, [rsi]
0x180007ca5  test    rcx, rcx
0x180007ca8  jz      short loc_180007CB7
0x180007caa  mov     rax, [rcx]
0x180007cad  mov     rax, [rax+10h]
0x180007cb1  call    cs:__guard_dispatch_icall_fptr
0x180007cb7  mov     rax, rdi
0x180007cba  add     rsp, 38h
0x180007cbe  pop     r15
0x180007cc0  pop     r14
0x180007cc2  pop     rdi
0x180007cc3  pop     rsi
0x180007cc4  pop     rbx
0x180007cc5  pop     rbp
0x180007cc6  retn
0x180007cc7  mov     rcx, [rbp+arg_10]
0x180007ccb  test    rcx, rcx
0x180007cce  jz      short loc_180007CDD
0x180007cd0  mov     rax, [rcx]
0x180007cd3  mov     rax, [rax+10h]
0x180007cd7  call    cs:__guard_dispatch_icall_fptr
0x180007cdd  mov     ecx, ebx; int
0x180007cdf  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
