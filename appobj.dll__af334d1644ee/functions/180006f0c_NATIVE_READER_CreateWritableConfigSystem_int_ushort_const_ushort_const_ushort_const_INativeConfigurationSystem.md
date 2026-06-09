# NATIVE_READER::CreateWritableConfigSystem(int,ushort const *,ushort const *,ushort const *,INativeConfigurationSystem * *)

- ea: `0x180006f0c`
- end: `0x180007030`
- name: `?CreateWritableConfigSystem@NATIVE_READER@@SAJHPEBG00PEAPEAVINativeConfigurationSystem@@@Z`
- size: `292`
- prototype: `__int64 __fastcall(int, const unsigned __int16 *, OLECHAR *, const unsigned __int16 *, struct INativeConfigurationSystem **)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800082d0`
- `0x18000bd20`

## callees

- `0x180006f0c`
- `0x18000c284`
- `0x18000cc4c`
- `0x18000d214`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006f52`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006f52`

## pseudocode

```c
__int64 __fastcall NATIVE_READER::CreateWritableConfigSystem(
        int a1,
        const unsigned __int16 *a2,
        OLECHAR *a3,
        const unsigned __int16 *a4,
        struct INativeConfigurationSystem **a5)
{
  HRESULT v9; // ebx
  struct INativeConfigurationSystem *v10; // rcx
  struct INativeConfigurationSystem *v12; // [rsp+30h] [rbp-10h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-8h] BYREF

  ppv = 0;
  v12 = 0;
  v9 = CoCreateInstance(&CLSID_AppHostWritableAdminManager, 0, 1u, &GUID_fa7660f6_7b3f_4237_a8bf_ed0ad0dcbbd9, &ppv);
  if ( v9 < 0
    || (v9 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *))(*(_QWORD *)ppv + 72LL))(ppv, a2), v9 < 0)
    || (v9 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, struct INativeConfigurationSystem **))ppv)(
               ppv,
               &IID_INativeConfigurationSystem,
               &v12),
        v9 < 0)
    || (v9 = NATIVE_READER::SetManagedRuntimeVersion(a3, v12), v9 < 0)
    || a1 && (v9 = NATIVE_READER::SetConfigSystemToUseAdministrationConfig(v12), v9 < 0)
    || a4 && *a4 && (v9 = NATIVE_READER::SetPathMapper(a4, v12), v9 < 0) )
  {
    v10 = v12;
  }
  else
  {
    *a5 = v12;
    v10 = 0;
    v12 = 0;
  }
  if ( v10 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationSystem *))(*(_QWORD *)v10 + 16LL))(v10);
    v12 = 0;
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180006f0c  push    rbp
0x180006f0e  push    rbx
0x180006f0f  push    rsi
0x180006f10  push    rdi
0x180006f11  push    r12
0x180006f13  push    r14
0x180006f15  push    r15
0x180006f17  mov     rbp, rsp
0x180006f1a  sub     rsp, 40h
0x180006f1e  xor     r12d, r12d
0x180006f21  lea     rax, [rbp+var_8]
0x180006f25  mov     rdi, r9
0x180006f28  mov     [rbp+var_8], r12
0x180006f2c  mov     r14, r8
0x180006f2f  mov     [rbp+var_10], r12
0x180006f33  mov     r15, rdx
0x180006f36  mov     [rsp+40h+ppv], rax; ppv
0x180006f3b  mov     esi, ecx
0x180006f3d  lea     r8d, [r12+1]; dwClsContext
0x180006f42  lea     r9, _GUID_fa7660f6_7b3f_4237_a8bf_ed0ad0dcbbd9; riid
0x180006f49  xor     edx, edx; pUnkOuter
0x180006f4b  lea     rcx, CLSID_AppHostWritableAdminManager; rclsid
0x180006f52  call    cs:__imp_CoCreateInstance
0x180006f58  mov     ebx, eax
0x180006f5a  test    eax, eax
0x180006f5c  js      loc_180006FF1
0x180006f62  mov     rcx, [rbp+var_8]
0x180006f66  mov     rdx, r15
0x180006f69  mov     rax, [rcx]
0x180006f6c  mov     rax, [rax+48h]
0x180006f70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f75  mov     ebx, eax
0x180006f77  test    eax, eax
0x180006f79  js      short loc_180006FF1
0x180006f7b  mov     rcx, [rbp+var_8]
0x180006f7f  lea     r8, [rbp+var_10]
0x180006f83  lea     rdx, IID_INativeConfigurationSystem
0x180006f8a  mov     rax, [rcx]
0x180006f8d  mov     rax, [rax]
0x180006f90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f95  mov     ebx, eax
0x180006f97  test    eax, eax
0x180006f99  js      short loc_180006FF1
0x180006f9b  mov     rdx, [rbp+var_10]; struct INativeConfigurationSystem *
0x180006f9f  mov     rcx, r14; psz
0x180006fa2  call    ?SetManagedRuntimeVersion@NATIVE_READER@@CAJPEBGPEAVINativeConfigurationSystem@@@Z; NATIVE_READER::SetManagedRuntimeVersion(ushort const *,INativeConfigurationSystem *)
0x180006fa7  mov     ebx, eax
0x180006fa9  test    eax, eax
0x180006fab  js      short loc_180006FF1
0x180006fad  test    esi, esi
0x180006faf  jz      short loc_180006FC0
0x180006fb1  mov     rcx, [rbp+var_10]; struct INativeConfigurationSystem *
0x180006fb5  call    ?SetConfigSystemToUseAdministrationConfig@NATIVE_READER@@CAJPEAVINativeConfigurationSystem@@@Z; NATIVE_READER::SetConfigSystemToUseAdministrationConfig(INativeConfigurationSystem *)
0x180006fba  mov     ebx, eax
0x180006fbc  test    eax, eax
0x180006fbe  js      short loc_180006FF1
0x180006fc0  test    rdi, rdi
0x180006fc3  jz      short loc_180006FDD
0x180006fc5  cmp     [rdi], r12w
0x180006fc9  jz      short loc_180006FDD
0x180006fcb  mov     rdx, [rbp+var_10]; struct INativeConfigurationSystem *
0x180006fcf  mov     rcx, rdi; unsigned __int16 *
0x180006fd2  call    ?SetPathMapper@NATIVE_READER@@CAJPEBGPEAVINativeConfigurationSystem@@@Z; NATIVE_READER::SetPathMapper(ushort const *,INativeConfigurationSystem *)
0x180006fd7  mov     ebx, eax
0x180006fd9  test    eax, eax
0x180006fdb  js      short loc_180006FF1
0x180006fdd  mov     rcx, [rbp+arg_20]
0x180006fe1  mov     rax, [rbp+var_10]
0x180006fe5  mov     [rcx], rax
0x180006fe8  mov     rcx, r12
0x180006feb  mov     [rbp+var_10], rcx
0x180006fef  jmp     short loc_180006FF5
0x180006ff1  mov     rcx, [rbp+var_10]
0x180006ff5  test    rcx, rcx
0x180006ff8  jz      short loc_18000700A
0x180006ffa  mov     rax, [rcx]
0x180006ffd  mov     rax, [rax+10h]
0x180007001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007006  mov     [rbp+var_10], r12
0x18000700a  mov     rcx, [rbp+var_8]
0x18000700e  test    rcx, rcx
0x180007011  jz      short loc_18000701F
0x180007013  mov     rax, [rcx]
0x180007016  mov     rax, [rax+10h]
0x18000701a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000701f  mov     eax, ebx
0x180007021  add     rsp, 40h
0x180007025  pop     r15
0x180007027  pop     r14
0x180007029  pop     r12
0x18000702b  pop     rdi
0x18000702c  pop     rsi
0x18000702d  pop     rbx
0x18000702e  pop     rbp
0x18000702f  retn
```
