# HDriver_CoCreateInstance

- ea: `0x180037668`
- end: `0x180037723`
- name: `HDriver_CoCreateInstance`
- size: `187`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, _QWORD *, HMODULE hModule)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180037544`

## callees

- `0x180037668`
- `0x180077010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800376a8`
- `KERNEL32!GetProcAddress` at `0x1800376a8`

## string_xrefs

- `0x1800376a1`: `DllGetClassObject`

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
0x180037668  mov     rax, rsp
0x18003766b  mov     [rax+8], rbx
0x18003766f  mov     [rax+10h], rsi
0x180037673  mov     [rax+20h], r9
0x180037677  push    rdi
0x180037678  sub     rsp, 30h
0x18003767c  mov     rsi, [rsp+38h+arg_20]
0x180037681  mov     ebx, 80004005h
0x180037686  mov     rcx, [rsp+38h+hModule]; hModule
0x18003768b  mov     edi, ebx
0x18003768d  mov     qword ptr [rax+20h], 0
0x180037695  mov     qword ptr [rsi], 0
0x18003769c  test    rcx, rcx
0x18003769f  jz      short loc_18003770E
0x1800376a1  lea     rdx, aDllgetclassobj; "DllGetClassObject"
0x1800376a8  call    cs:__imp_GetProcAddress
0x1800376af  nop     dword ptr [rax+rax+00h]
0x1800376b4  test    rax, rax
0x1800376b7  jz      short loc_18003770E
0x1800376b9  lea     r8, [rsp+38h+arg_18]
0x1800376be  lea     rdx, IID_IClassFactory
0x1800376c5  lea     rcx, CLSID_OEMRENDER
0x1800376cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800376d1  mov     edi, eax
0x1800376d3  test    eax, eax
0x1800376d5  js      short loc_18003770E
0x1800376d7  mov     rcx, [rsp+38h+arg_18]
0x1800376dc  test    rcx, rcx
0x1800376df  jz      short loc_180037710
0x1800376e1  mov     rax, [rcx]
0x1800376e4  lea     r8, IID_IUnknown
0x1800376eb  mov     r9, rsi
0x1800376ee  xor     edx, edx
0x1800376f0  mov     rax, [rax+18h]
0x1800376f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800376f9  mov     rcx, [rsp+38h+arg_18]
0x1800376fe  mov     ebx, eax
0x180037700  mov     rdx, [rcx]
0x180037703  mov     rax, [rdx+10h]
0x180037707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003770c  jmp     short loc_180037710
0x18003770e  mov     ebx, edi
0x180037710  mov     rsi, [rsp+38h+arg_8]
0x180037715  mov     eax, ebx
0x180037717  mov     rbx, [rsp+38h+arg_0]
0x18003771c  add     rsp, 30h
0x180037720  pop     rdi
0x180037721  retn
```
