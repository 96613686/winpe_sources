# HDriver_CoCreateInstance

- ea: `0x180036c38`
- end: `0x180036cec`
- name: `HDriver_CoCreateInstance`
- size: `180`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, HMODULE hModule)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180036b14`

## callees

- `0x180036c38`
- `0x180075010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180036c78`
- `KERNEL32!GetProcAddress` at `0x180036c78`

## string_xrefs

- `0x180036c71`: `DllGetClassObject`

## pseudocode

```c
__int64 __fastcall HDriver_CoCreateInstance(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        HMODULE hModule)
{
  _QWORD *v6; // rsi
  unsigned int v7; // ebx
  HMODULE v8; // rcx
  int v9; // edi
  FARPROC ProcAddress; // rax
  __int64 v12; // [rsp+58h] [rbp+20h] BYREF

  v6 = a5;
  v7 = -2147467259;
  v8 = hModule;
  v9 = -2147467259;
  v12 = 0;
  *a5 = 0;
  if ( v8
    && (ProcAddress = GetProcAddress(v8, "DllGetClassObject")) != 0
    && (v9 = ((__int64 (__fastcall *)(GUID *, GUID *, __int64 *))ProcAddress)(
               &CLSID_OEMRENDER,
               &IID_IClassFactory,
               &v12),
        v9 >= 0) )
  {
    if ( v12 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, _QWORD *))(*(_QWORD *)v12 + 24LL))(
             v12,
             0,
             &IID_IUnknown,
             v6);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
  }
  else
  {
    return (unsigned int)v9;
  }
  return v7;
}

```

## disassembly

```asm
0x180036c38  mov     rax, rsp
0x180036c3b  mov     [rax+8], rbx
0x180036c3f  mov     [rax+10h], rsi
0x180036c43  mov     [rax+20h], r9
0x180036c47  push    rdi
0x180036c48  sub     rsp, 30h
0x180036c4c  mov     rsi, [rsp+38h+arg_20]
0x180036c51  mov     ebx, 80004005h
0x180036c56  mov     rcx, [rsp+38h+hModule]; hModule
0x180036c5b  mov     edi, ebx
0x180036c5d  mov     qword ptr [rax+20h], 0
0x180036c65  mov     qword ptr [rsi], 0
0x180036c6c  test    rcx, rcx
0x180036c6f  jz      short loc_180036CD8
0x180036c71  lea     rdx, aDllgetclassobj; "DllGetClassObject"
0x180036c78  call    cs:__imp_GetProcAddress
0x180036c7e  test    rax, rax
0x180036c81  jz      short loc_180036CD8
0x180036c83  lea     r8, [rsp+38h+arg_18]
0x180036c88  lea     rdx, IID_IClassFactory
0x180036c8f  lea     rcx, CLSID_OEMRENDER
0x180036c96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036c9b  mov     edi, eax
0x180036c9d  test    eax, eax
0x180036c9f  js      short loc_180036CD8
0x180036ca1  mov     rcx, [rsp+38h+arg_18]
0x180036ca6  test    rcx, rcx
0x180036ca9  jz      short loc_180036CDA
0x180036cab  mov     rax, [rcx]
0x180036cae  lea     r8, IID_IUnknown
0x180036cb5  mov     r9, rsi
0x180036cb8  xor     edx, edx
0x180036cba  mov     rax, [rax+18h]
0x180036cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036cc3  mov     rcx, [rsp+38h+arg_18]
0x180036cc8  mov     ebx, eax
0x180036cca  mov     rdx, [rcx]
0x180036ccd  mov     rax, [rdx+10h]
0x180036cd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036cd6  jmp     short loc_180036CDA
0x180036cd8  mov     ebx, edi
0x180036cda  mov     rsi, [rsp+38h+arg_8]
0x180036cdf  mov     eax, ebx
0x180036ce1  mov     rbx, [rsp+38h+arg_0]
0x180036ce6  add     rsp, 30h
0x180036cea  pop     rdi
0x180036ceb  retn
```
