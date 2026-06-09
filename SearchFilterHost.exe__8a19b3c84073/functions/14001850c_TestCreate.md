# TestCreate

- ea: `0x14001850c`
- end: `0x140018599`
- name: `TestCreate`
- size: `141`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140017c9c`
- `0x1400270ac`
- `0x14002fc40`

## callees

- `0x14001850c`
- `0x1400186d8`
- `0x14004f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001853e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001853e`

## string_xrefs

- `0x140018537`: `TestCreate`

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
0x14001850c  mov     [rsp+arg_0], rbx
0x140018511  mov     [rsp+arg_8], rsi
0x140018516  push    rdi
0x140018517  sub     rsp, 40h
0x14001851b  mov     r10, cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x140018522  mov     ebx, r9d
0x140018525  mov     dil, r8b
0x140018528  mov     esi, ecx
0x14001852a  test    r10, r10
0x14001852d  jnz     short loc_140018563
0x14001852f  call    tip_details_GetKernelBaseModuleHandle
0x140018534  mov     rcx, rax; hModule
0x140018537  lea     rdx, aTestcreate; "TestCreate"
0x14001853e  call    cs:__imp_GetProcAddress
0x140018544  mov     cs:?s_pfnTestCreate@?1??TestCreate@@9@4P6APEAUHTIPTEST__@@IW4TestRetrievalOptions@@W4TestStorage@@W4TestProperties@@PEBDPEAU_GUID@@@ZEA, rax; HTIPTEST__ * (*`TestCreate'::`2'::s_pfnTestCreate)(uint,TestRetrievalOptions,TestStorage,TestProperties,char const *,_GUID *)
0x14001854b  mov     r10, rax
0x14001854e  test    rax, rax
0x140018551  jnz     short loc_140018563
0x140018553  mov     rax, [rsp+48h+arg_28]
0x140018558  xorps   xmm0, xmm0
0x14001855b  movdqu  xmmword ptr [rax], xmm0
0x14001855f  xor     eax, eax
0x140018561  jmp     short loc_140018589
0x140018563  mov     rax, [rsp+48h+arg_28]
0x140018568  mov     r9d, ebx
0x14001856b  mov     [rsp+48h+var_20], rax
0x140018570  mov     r8b, dil
0x140018573  mov     rax, [rsp+48h+arg_20]
0x140018578  xor     edx, edx
0x14001857a  mov     [rsp+48h+var_28], rax
0x14001857f  mov     ecx, esi
0x140018581  mov     rax, r10
0x140018584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018589  mov     rbx, [rsp+48h+arg_0]
0x14001858e  mov     rsi, [rsp+48h+arg_8]
0x140018593  add     rsp, 40h
0x140018597  pop     rdi
0x140018598  retn
```
