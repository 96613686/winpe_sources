# GmoMigrationSmb::Initialize(IMemoryManager *,IProcessorManager *,VmMigrationConnection *,MigrationManager *)

- ea: `0x1400c5ee0`
- end: `0x1400c6020`
- name: `?Initialize@GmoMigrationSmb@@MEAAJPEAUIMemoryManager@@PEAUIProcessorManager@@PEAVVmMigrationConnection@@PEAVMigrationManager@@@Z`
- size: `320`
- prototype: `__int64 __fastcall(GmoMigrationSmb *__hidden this, struct IMemoryManager *, struct IProcessorManager *, struct VmMigrationConnection *, struct MigrationManager *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1400c38f8`

## callees

- `0x140055af0`
- `0x14006af38`
- `0x1400c5ee0`
- `0x1400c6030`
- `0x140132940`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400c5f2b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400c5f2b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400c5f7d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1400c5f7d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400c5f4b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400c5f4b`

## string_xrefs

- `0x1400c5f41`: `NetpWkstaClientGetSmbClientCapabilities`
- `0x1400c5f24`: `wkscli.dll`

## pseudocode

```c
__int64 __fastcall GmoMigrationSmb::Initialize(
        GmoMigrationSmb *this,
        struct IMemoryManager *a2,
        struct IProcessorManager *a3,
        struct VmMigrationConnection *a4,
        struct MigrationManager *a5)
{
  HMODULE Library; // rax
  HMODULE v10; // rsi
  BOOL v11; // edi
  FARPROC ProcAddress; // rax
  unsigned int v13; // edi
  int v14; // eax
  const struct Vml::ExceptionTraceParameters *v15; // r8
  int v17; // [rsp+20h] [rbp-58h]
  int v18; // [rsp+30h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  if ( *((_DWORD *)this + 252) )
  {
    Library = LoadLibraryExW(L"wkscli.dll", 0, 0x800u);
    v10 = Library;
    v11 = 0;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "NetpWkstaClientGetSmbClientCapabilities");
      if ( ProcAddress )
      {
        v18 = 0;
        if ( !((unsigned int (__fastcall *)(_QWORD, int *))ProcAddress)(0, &v18) )
          v11 = (v18 & 1) != 0;
      }
      FreeLibrary(v10);
    }
    *((_DWORD *)this + 252) = v11;
  }
  v13 = 0;
  try
  {
    Vml::VmReferencePtr<WorkerConfiguration,Vml::VmUserReferenceTraits>::Reset((char *)this + 984, a5);
    v14 = GmoMigration::Initialize(this, a2, a3, a4, a5);
    if ( v14 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x15B,
        (unsigned int)"onecore\\vm\\worker\\migration\\gmomigrationsmb.cpp",
        (const char *)(unsigned int)v14,
        v17);
    (*(void (__fastcall **)(_QWORD, unsigned __int64))(**((_QWORD **)this + 124) + 224LL))(
      *((_QWORD *)this + 124),
      ((unsigned __int64)this + 928) & -(__int64)(this != 0));
  }
  catch ( ... )
  {
    return (unsigned int)Vml::GetHResultFromThrownExceptionAndTrace(
                           (Vml *)0x41E2,
                           (unsigned __int16)&off_1402DB588,
                           v15);
  }
  return v13;
}

```

## disassembly

```asm
0x1400c5ee0  push    rbx
0x1400c5ee2  push    rsi
0x1400c5ee3  push    rdi
0x1400c5ee4  push    r12
0x1400c5ee6  push    r13
0x1400c5ee8  push    r14
0x1400c5eea  push    r15
0x1400c5eec  sub     rsp, 40h
0x1400c5ef0  mov     rax, cs:__security_cookie
0x1400c5ef7  xor     rax, rsp
0x1400c5efa  mov     [rsp+78h+var_40], rax
0x1400c5eff  mov     r13, r9
0x1400c5f02  mov     r12, r8
0x1400c5f05  mov     r15, rdx
0x1400c5f08  mov     rbx, rcx
0x1400c5f0b  mov     r14, [rsp+78h+arg_20]
0x1400c5f13  cmp     dword ptr [rcx+3F0h], 0
0x1400c5f1a  jz      short loc_1400C5F8F
0x1400c5f1c  xor     edx, edx; hFile
0x1400c5f1e  mov     r8d, 800h; dwFlags
0x1400c5f24  lea     rcx, LibFileName; "wkscli.dll"
0x1400c5f2b  call    cs:__imp_LoadLibraryExW
0x1400c5f32  nop     dword ptr [rax+rax+00h]
0x1400c5f37  mov     rsi, rax
0x1400c5f3a  xor     edi, edi
0x1400c5f3c  test    rax, rax
0x1400c5f3f  jz      short loc_1400C5F89
0x1400c5f41  lea     rdx, aNetpwkstaclien; "NetpWkstaClientGetSmbClientCapabilities"
0x1400c5f48  mov     rcx, rax; hModule
0x1400c5f4b  call    cs:__imp_GetProcAddress
0x1400c5f52  nop     dword ptr [rax+rax+00h]
0x1400c5f57  test    rax, rax
0x1400c5f5a  jz      short loc_1400C5F7A
0x1400c5f5c  mov     [rsp+78h+var_48], edi
0x1400c5f60  lea     rdx, [rsp+78h+var_48]
0x1400c5f65  xor     ecx, ecx
0x1400c5f67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400c5f6c  test    eax, eax
0x1400c5f6e  jnz     short loc_1400C5F7A
0x1400c5f70  lea     eax, [rdi+1]
0x1400c5f73  test    byte ptr [rsp+78h+var_48], al
0x1400c5f77  cmovnz  edi, eax
0x1400c5f7a  mov     rcx, rsi; hLibModule
0x1400c5f7d  call    cs:__imp_FreeLibrary
0x1400c5f84  nop     dword ptr [rax+rax+00h]
0x1400c5f89  mov     [rbx+3F0h], edi
0x1400c5f8f  xor     edi, edi
0x1400c5f91  lea     rcx, [rbx+3D8h]
0x1400c5f98  mov     rdx, r14
0x1400c5f9b  call    ?Reset@?$VmReferencePtr@VWorkerConfiguration@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAXPEAVWorkerConfiguration@@@Z; Vml::VmReferencePtr<WorkerConfiguration,Vml::VmUserReferenceTraits>::Reset(WorkerConfiguration *)
0x1400c5fa0  mov     qword ptr [rsp+78h+var_58], r14; int
0x1400c5fa5  mov     r9, r13; struct VmMigrationConnection *
0x1400c5fa8  mov     r8, r12; struct IProcessorManager *
0x1400c5fab  mov     rdx, r15; struct IMemoryManager *
0x1400c5fae  mov     rcx, rbx; this
0x1400c5fb1  call    ?Initialize@GmoMigration@@MEAAJPEAUIMemoryManager@@PEAUIProcessorManager@@PEAVVmMigrationConnection@@PEAVMigrationManager@@@Z; GmoMigration::Initialize(IMemoryManager *,IProcessorManager *,VmMigrationConnection *,MigrationManager *)
0x1400c5fb6  mov     rcx, [rsp+78h]; this
0x1400c5fbb  test    eax, eax
0x1400c5fbd  jns     short loc_1400C5FD3
0x1400c5fbf  mov     r9d, eax; char *
0x1400c5fc2  lea     r8, aOnecoreVmWorke_74; "onecore\\vm\\worker\\migration\\gmomigr"...
0x1400c5fc9  mov     edx, 15Bh; void *
0x1400c5fce  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1400c5fd3  mov     rcx, [rbx+3E0h]
0x1400c5fda  mov     r8, [rcx]
0x1400c5fdd  lea     rax, [rbx+3A0h]
0x1400c5fe4  neg     rbx
0x1400c5fe7  sbb     rdx, rdx
0x1400c5fea  and     rdx, rax
0x1400c5fed  mov     rax, [r8+0E0h]
0x1400c5ff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400c5ff9  nop
0x1400c5ffa  jmp     short loc_1400C6000
0x1400c5ffc  mov     edi, [rsp+78h+var_48]
0x1400c6000  mov     eax, edi
0x1400c6002  mov     rcx, [rsp+78h+var_40]
0x1400c6007  xor     rcx, rsp; StackCookie
0x1400c600a  call    __security_check_cookie
0x1400c600f  add     rsp, 40h
0x1400c6013  pop     r15
0x1400c6015  pop     r14
0x1400c6017  pop     r13
0x1400c6019  pop     r12
0x1400c601b  pop     rdi
0x1400c601c  pop     rsi
0x1400c601d  pop     rbx
0x1400c601e  retn
```
