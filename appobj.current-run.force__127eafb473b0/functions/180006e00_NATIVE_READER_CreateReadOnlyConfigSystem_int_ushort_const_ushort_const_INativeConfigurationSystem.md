# NATIVE_READER::CreateReadOnlyConfigSystem(int,ushort const *,ushort const *,INativeConfigurationSystem * *)

- ea: `0x180006e00`
- end: `0x180006f03`
- name: `?CreateReadOnlyConfigSystem@NATIVE_READER@@SAJHPEBG0PEAPEAVINativeConfigurationSystem@@@Z`
- size: `259`
- prototype: `static int(int, const unsigned __int16 *, const unsigned __int16 *, struct INativeConfigurationSystem **)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800082d0`
- `0x18000ab4c`
- `0x18000bd20`

## callees

- `0x180006e00`
- `0x18000c284`
- `0x18000cc4c`
- `0x18000d214`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006e46`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006e46`

## pseudocode

```c
__int64 __fastcall NATIVE_READER::CreateReadOnlyConfigSystem(
        int a1,
        OLECHAR *a2,
        const unsigned __int16 *a3,
        struct INativeConfigurationSystem **a4)
{
  HRESULT v8; // ebx
  struct INativeConfigurationSystem *v9; // rcx
  struct INativeConfigurationSystem *v11; // [rsp+30h] [rbp-10h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-8h] BYREF

  ppv = 0;
  v11 = 0;
  v8 = CoCreateInstance(&CLSID_AppHostAdminManager, 0, 1u, &GUID_9be77978_73ed_4a9a_87fd_13f09fec1b13, &ppv);
  if ( v8 < 0
    || (v8 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, struct INativeConfigurationSystem **))ppv)(
               ppv,
               &IID_INativeConfigurationSystem,
               &v11),
        v8 < 0)
    || (v8 = NATIVE_READER::SetManagedRuntimeVersion(a2, v11), v8 < 0)
    || a1 && (v8 = NATIVE_READER::SetConfigSystemToUseAdministrationConfig(v11), v8 < 0)
    || a3 && *a3 && (v8 = NATIVE_READER::SetPathMapper(a3, v11), v8 < 0) )
  {
    v9 = v11;
  }
  else
  {
    v9 = 0;
    *a4 = v11;
    v11 = 0;
  }
  if ( v9 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationSystem *))(*(_QWORD *)v9 + 16LL))(v9);
    v11 = 0;
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180006e00  push    rbp
0x180006e02  push    rbx
0x180006e03  push    rsi
0x180006e04  push    rdi
0x180006e05  push    r12
0x180006e07  push    r14
0x180006e09  push    r15
0x180006e0b  mov     rbp, rsp
0x180006e0e  sub     rsp, 40h
0x180006e12  xor     r12d, r12d
0x180006e15  lea     rax, [rbp+var_8]
0x180006e19  mov     r15, r9
0x180006e1c  mov     [rbp+var_8], r12
0x180006e20  mov     rdi, r8
0x180006e23  mov     [rbp+var_10], r12
0x180006e27  mov     r14, rdx
0x180006e2a  mov     [rsp+40h+ppv], rax; ppv
0x180006e2f  mov     esi, ecx
0x180006e31  lea     r8d, [r12+1]; dwClsContext
0x180006e36  lea     r9, _GUID_9be77978_73ed_4a9a_87fd_13f09fec1b13; riid
0x180006e3d  xor     edx, edx; pUnkOuter
0x180006e3f  lea     rcx, CLSID_AppHostAdminManager; rclsid
0x180006e46  call    cs:__imp_CoCreateInstance
0x180006e4c  mov     ebx, eax
0x180006e4e  test    eax, eax
0x180006e50  js      short loc_180006EC4
0x180006e52  mov     rcx, [rbp+var_8]
0x180006e56  lea     r8, [rbp+var_10]
0x180006e5a  lea     rdx, IID_INativeConfigurationSystem
0x180006e61  mov     rax, [rcx]
0x180006e64  mov     rax, [rax]
0x180006e67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e6c  mov     ebx, eax
0x180006e6e  test    eax, eax
0x180006e70  js      short loc_180006EC4
0x180006e72  mov     rdx, [rbp+var_10]; struct INativeConfigurationSystem *
0x180006e76  mov     rcx, r14; psz
0x180006e79  call    ?SetManagedRuntimeVersion@NATIVE_READER@@CAJPEBGPEAVINativeConfigurationSystem@@@Z; NATIVE_READER::SetManagedRuntimeVersion(ushort const *,INativeConfigurationSystem *)
0x180006e7e  mov     ebx, eax
0x180006e80  test    eax, eax
0x180006e82  js      short loc_180006EC4
0x180006e84  test    esi, esi
0x180006e86  jz      short loc_180006E97
0x180006e88  mov     rcx, [rbp+var_10]; struct INativeConfigurationSystem *
0x180006e8c  call    ?SetConfigSystemToUseAdministrationConfig@NATIVE_READER@@CAJPEAVINativeConfigurationSystem@@@Z; NATIVE_READER::SetConfigSystemToUseAdministrationConfig(INativeConfigurationSystem *)
0x180006e91  mov     ebx, eax
0x180006e93  test    eax, eax
0x180006e95  js      short loc_180006EC4
0x180006e97  test    rdi, rdi
0x180006e9a  jz      short loc_180006EB4
0x180006e9c  cmp     [rdi], r12w
0x180006ea0  jz      short loc_180006EB4
0x180006ea2  mov     rdx, [rbp+var_10]; struct INativeConfigurationSystem *
0x180006ea6  mov     rcx, rdi; unsigned __int16 *
0x180006ea9  call    ?SetPathMapper@NATIVE_READER@@CAJPEBGPEAVINativeConfigurationSystem@@@Z; NATIVE_READER::SetPathMapper(ushort const *,INativeConfigurationSystem *)
0x180006eae  mov     ebx, eax
0x180006eb0  test    eax, eax
0x180006eb2  js      short loc_180006EC4
0x180006eb4  mov     rax, [rbp+var_10]
0x180006eb8  mov     rcx, r12
0x180006ebb  mov     [r15], rax
0x180006ebe  mov     [rbp+var_10], rcx
0x180006ec2  jmp     short loc_180006EC8
0x180006ec4  mov     rcx, [rbp+var_10]
0x180006ec8  test    rcx, rcx
0x180006ecb  jz      short loc_180006EDD
0x180006ecd  mov     rax, [rcx]
0x180006ed0  mov     rax, [rax+10h]
0x180006ed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ed9  mov     [rbp+var_10], r12
0x180006edd  mov     rcx, [rbp+var_8]
0x180006ee1  test    rcx, rcx
0x180006ee4  jz      short loc_180006EF2
0x180006ee6  mov     rax, [rcx]
0x180006ee9  mov     rax, [rax+10h]
0x180006eed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ef2  mov     eax, ebx
0x180006ef4  add     rsp, 40h
0x180006ef8  pop     r15
0x180006efa  pop     r14
0x180006efc  pop     r12
0x180006efe  pop     rdi
0x180006eff  pop     rsi
0x180006f00  pop     rbx
0x180006f01  pop     rbp
0x180006f02  retn
```
