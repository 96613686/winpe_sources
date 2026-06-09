# TestCreate

- ea: `0x180021914`
- end: `0x1800219a1`
- name: `TestCreate`
- size: `141`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180020e54`
- `0x180020f74`

## callees

- `0x180021914`
- `0x180021ae0`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021946`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180021946`

## string_xrefs

- `0x18002193f`: `TestCreate`

## pseudocode

```c
__int64 __fastcall TestCreate(unsigned int a1, __int64 a2, __int64 a3, unsigned int a4, __int64 a5, _OWORD *a6)
{
  __int64 (__fastcall *v6)(_QWORD, _QWORD, __int64, _QWORD, __int64, _OWORD *); // r10
  char v8; // di
  HMODULE KernelBaseModuleHandle; // rax

  v6 = (__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, __int64, _OWORD *))`TestCreate'::`2'::s_pfnTestCreate;
  v8 = a3;
  if ( `TestCreate'::`2'::s_pfnTestCreate
    || (KernelBaseModuleHandle = (HMODULE)tip_details_GetKernelBaseModuleHandle(),
        `TestCreate'::`2'::s_pfnTestCreate = (__int64)GetProcAddress(KernelBaseModuleHandle, "TestCreate"),
        (v6 = (__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, __int64, _OWORD *))`TestCreate'::`2'::s_pfnTestCreate) != 0) )
  {
    LOBYTE(a3) = v8;
    return v6(a1, 0, a3, a4, a5, a6);
  }
  else
  {
    *a6 = 0;
    return 0;
  }
}

```

## disassembly

```asm
0x180021914  mov     [rsp+arg_0], rbx
0x180021919  mov     [rsp+arg_8], rsi
0x18002191e  push    rdi
0x18002191f  sub     rsp, 40h
0x180021923  mov     r10, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x18002192a  mov     ebx, r9d
0x18002192d  mov     dil, r8b
0x180021930  mov     esi, ecx
0x180021932  test    r10, r10
0x180021935  jnz     short loc_18002196B
0x180021937  call    tip_details_GetKernelBaseModuleHandle
0x18002193c  mov     rcx, rax; hModule
0x18002193f  lea     rdx, aTestcreate; "TestCreate"
0x180021946  call    cs:__imp_GetProcAddress
0x18002194c  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x180021953  mov     r10, rax
0x180021956  test    rax, rax
0x180021959  jnz     short loc_18002196B
0x18002195b  mov     rax, [rsp+48h+arg_28]
0x180021960  xorps   xmm0, xmm0
0x180021963  movdqu  xmmword ptr [rax], xmm0
0x180021967  xor     eax, eax
0x180021969  jmp     short loc_180021991
0x18002196b  mov     rax, [rsp+48h+arg_28]
0x180021970  mov     r9d, ebx
0x180021973  mov     [rsp+48h+var_20], rax
0x180021978  mov     r8b, dil
0x18002197b  mov     rax, [rsp+48h+arg_20]
0x180021980  xor     edx, edx
0x180021982  mov     [rsp+48h+var_28], rax
0x180021987  mov     ecx, esi
0x180021989  mov     rax, r10
0x18002198c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021991  mov     rbx, [rsp+48h+arg_0]
0x180021996  mov     rsi, [rsp+48h+arg_8]
0x18002199b  add     rsp, 40h
0x18002199f  pop     rdi
0x1800219a0  retn
```
