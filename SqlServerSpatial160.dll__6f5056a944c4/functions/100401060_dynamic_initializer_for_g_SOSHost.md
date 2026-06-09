# _dynamic_initializer_for__g_SOSHost__

- ea: `0x100401060`
- end: `0x100401100`
- name: `_dynamic_initializer_for__g_SOSHost__`
- size: `160`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x100401060`
- `0x100429990`
- `0x1004692f0`
- `0x100469a74`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x100401080`
- `KERNEL32!GetProcAddress` at `0x100401080`
- `KERNEL32!GetModuleHandleW` at `0x10040106b`
- `KERNEL32!GetModuleHandleW` at `0x10040106b`
- `KERNEL32!GetLastError` at `0x1004010ab`
- `KERNEL32!GetLastError` at `0x1004010ab`

## string_xrefs

- `0x100401064`: `SQLOS.DLL`
- `0x100401076`: `CreateVersionedSOSHostObject`

## pseudocode

```c
int dynamic_initializer_for__g_SOSHost__()
{
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  unsigned int v2; // ecx
  signed int LastError; // eax
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  ModuleHandleW = GetModuleHandleW(L"SQLOS.DLL");
  if ( ModuleHandleW )
  {
    ProcAddress = GetProcAddress(ModuleHandleW, "CreateVersionedSOSHostObject");
    if ( ProcAddress )
    {
      v2 = ((__int64 (__fastcall *)(GUID *, __int64, const wchar_t *, void *))ProcAddress)(
             &GUID_61dd042f_ec99_427f_92be_09c9a29161f3,
             66,
             L"Spatial Host",
             &g_SOSHost);
    }
    else
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( (int)(v2 + 0x80000000) >= 0 && v2 != -2147221497 )
    {
      std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
      throw (std::bad_alloc *)pExceptionObject;
    }
  }
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__g_SOSHost__);
}

```

## disassembly

```asm
0x100401060  sub     rsp, 48h
0x100401064  lea     rcx, ModuleName; "SQLOS.DLL"
0x10040106b  call    cs:__imp_GetModuleHandleW
0x100401071  test    rax, rax
0x100401074  jz      short loc_1004010D4
0x100401076  lea     rdx, ProcName; "CreateVersionedSOSHostObject"
0x10040107d  mov     rcx, rax; hModule
0x100401080  call    cs:__imp_GetProcAddress
0x100401086  test    rax, rax
0x100401089  jz      short loc_1004010AB
0x10040108b  lea     r9, ?g_SOSHost@@3VSOS_AutoHost@@A; SOS_AutoHost g_SOSHost
0x100401092  mov     edx, 42h ; 'B'
0x100401097  lea     r8, aSpatialHost; "Spatial Host"
0x10040109e  lea     rcx, _GUID_61dd042f_ec99_427f_92be_09c9a29161f3
0x1004010a5  call    rax
0x1004010a7  mov     ecx, eax
0x1004010a9  jmp     short loc_1004010C0
0x1004010ab  call    cs:__imp_GetLastError
0x1004010b1  mov     ecx, eax
0x1004010b3  test    eax, eax
0x1004010b5  jle     short loc_1004010C0
0x1004010b7  movzx   ecx, ax
0x1004010ba  or      ecx, 80070000h
0x1004010c0  mov     edx, 80000000h
0x1004010c5  lea     eax, [rcx+rdx]
0x1004010c8  test    edx, eax
0x1004010ca  jnz     short loc_1004010D4
0x1004010cc  cmp     ecx, 80040007h
0x1004010d2  jnz     short loc_1004010E4
0x1004010d4  lea     rcx, _dynamic_atexit_destructor_for__g_SOSHost__
0x1004010db  add     rsp, 48h
0x1004010df  jmp     atexit
0x1004010e4  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1004010e9  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x1004010ee  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1004010f5  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1004010fa  call    _CxxThrowException_0
```
