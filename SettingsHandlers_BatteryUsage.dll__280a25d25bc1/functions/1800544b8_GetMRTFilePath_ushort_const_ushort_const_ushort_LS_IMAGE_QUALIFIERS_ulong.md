# GetMRTFilePath(ushort const *,ushort const *,ushort * *,LS_IMAGE_QUALIFIERS *,ulong *)

- ea: `0x1800544b8`
- end: `0x180054670`
- name: `?GetMRTFilePath@@YAJPEBG0PEAPEAGPEAW4LS_IMAGE_QUALIFIERS@@PEAK@Z`
- size: `440`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, const unsigned __int16 *@<rdx>, unsigned __int16 **@<r8>, enum LS_IMAGE_QUALIFIERS *@<r9>, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180052848`

## callees

- `0x1800544b8`
- `0x1800549f0`
- `0x180054b38`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005451b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005451b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054631`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054631`

## pseudocode

```c
__int64 __fastcall GetMRTFilePath(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        enum LS_IMAGE_QUALIFIERS *a4,
        struct IResourceCandidate *a5)
{
  unsigned int *v5; // r14
  HRESULT v10; // ebx
  LPVOID pv; // [rsp+30h] [rbp-10h] BYREF
  __int64 v13; // [rsp+38h] [rbp-8h] BYREF
  LPVOID ppv; // [rsp+80h] [rbp+40h] BYREF
  __int64 v15; // [rsp+88h] [rbp+48h] BYREF

  v5 = (unsigned int *)a5;
  *a3 = 0;
  *(_DWORD *)a4 = 0;
  ppv = 0;
  *v5 = 100;
  v10 = CoCreateInstance(&CLSID_MrtResourceManager, 0, 1u, &GUID_130a2f65_2be7_4309_9a58_a9052ff2b61c, &ppv);
  if ( v10 >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *))(*(_QWORD *)ppv + 40LL))(ppv, a1);
    if ( v10 >= 0 )
    {
      v13 = 0;
      v10 = (*(__int64 (__fastcall **)(LPVOID, GUID *, __int64 *))(*(_QWORD *)ppv + 56LL))(
              ppv,
              &GUID_6e21e72b_b9b0_42ae_a686_983cf784edcd,
              &v13);
      if ( v10 >= 0 )
      {
        pv = 0;
        v10 = _ValidateAndConvertMsAppxUri(a1, a2, (unsigned __int16 **)&pv);
        if ( v10 >= 0 )
        {
          v15 = 0;
          v10 = (*(__int64 (__fastcall **)(__int64, LPVOID, GUID *, __int64 *))(*(_QWORD *)v13 + 88LL))(
                  v13,
                  pv,
                  &GUID_c2ac6f97_54f2_445a_8f62_d87b9537f9b2,
                  &v15);
          if ( v10 >= 0 )
          {
            a5 = 0;
            v10 = (*(__int64 (__fastcall **)(__int64, struct IResourceCandidate **))(*(_QWORD *)v15 + 48LL))(v15, &a5);
            if ( v10 >= 0 )
            {
              v10 = (*(__int64 (__fastcall **)(struct IResourceCandidate *, unsigned __int16 **))(*(_QWORD *)a5 + 32LL))(
                      a5,
                      a3);
              if ( v10 >= 0 )
                _GetImageResourceQualifiers(a5, a4, v5);
              (*(void (__fastcall **)(struct IResourceCandidate *))(*(_QWORD *)a5 + 16LL))(a5);
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
          }
          CoTaskMemFree(pv);
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
      }
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800544b8  mov     [rsp-28h+arg_0], rbx
0x1800544bd  mov     [rsp-28h+arg_8], rsi
0x1800544c2  push    rbp
0x1800544c3  push    rdi
0x1800544c4  push    r12
0x1800544c6  push    r14
0x1800544c8  push    r15
0x1800544ca  mov     rbp, rsp
0x1800544cd  sub     rsp, 40h
0x1800544d1  mov     r14, [rbp+arg_20]
0x1800544d5  lea     rax, [rbp+arg_10]
0x1800544d9  mov     qword ptr [r8], 0
0x1800544e0  mov     r15, rdx
0x1800544e3  mov     dword ptr [r9], 0
0x1800544ea  xor     edx, edx; pUnkOuter
0x1800544ec  mov     rsi, r9
0x1800544ef  mov     [rbp+arg_10], 0
0x1800544f7  mov     r12, r8
0x1800544fa  mov     dword ptr [r14], 64h ; 'd'
0x180054501  mov     rdi, rcx
0x180054504  mov     [rsp+40h+ppv], rax; ppv
0x180054509  lea     r8d, [rdx+1]; dwClsContext
0x18005450d  lea     r9, _GUID_130a2f65_2be7_4309_9a58_a9052ff2b61c; riid
0x180054514  lea     rcx, CLSID_MrtResourceManager; rclsid
0x18005451b  call    cs:__imp_CoCreateInstance
0x180054521  mov     ebx, eax
0x180054523  test    eax, eax
0x180054525  js      loc_180054657
0x18005452b  mov     rcx, [rbp+arg_10]
0x18005452f  mov     rdx, rdi
0x180054532  mov     rax, [rcx]
0x180054535  mov     rax, [rax+28h]
0x180054539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005453e  mov     ebx, eax
0x180054540  test    eax, eax
0x180054542  js      loc_180054647
0x180054548  mov     rcx, [rbp+arg_10]
0x18005454c  lea     r8, [rbp+var_8]
0x180054550  mov     [rbp+var_8], 0
0x180054558  lea     rdx, _GUID_6e21e72b_b9b0_42ae_a686_983cf784edcd
0x18005455f  mov     rax, [rcx]
0x180054562  mov     rax, [rax+38h]
0x180054566  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005456b  mov     ebx, eax
0x18005456d  test    eax, eax
0x18005456f  js      loc_180054647
0x180054575  lea     r8, [rbp+pv]; unsigned __int16 **
0x180054579  mov     [rbp+pv], 0
0x180054581  mov     rdx, r15; unsigned __int16 *
0x180054584  mov     rcx, rdi; unsigned __int16 *
0x180054587  call    ?_ValidateAndConvertMsAppxUri@@YAJPEBG0PEAPEAG@Z; _ValidateAndConvertMsAppxUri(ushort const *,ushort const *,ushort * *)
0x18005458c  mov     ebx, eax
0x18005458e  test    eax, eax
0x180054590  js      loc_180054637
0x180054596  mov     rcx, [rbp+var_8]
0x18005459a  lea     r9, [rbp+arg_18]
0x18005459e  mov     rdx, [rbp+pv]
0x1800545a2  lea     r8, _GUID_c2ac6f97_54f2_445a_8f62_d87b9537f9b2
0x1800545a9  mov     [rbp+arg_18], 0
0x1800545b1  mov     rax, [rcx]
0x1800545b4  mov     rax, [rax+58h]
0x1800545b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800545bd  mov     ebx, eax
0x1800545bf  test    eax, eax
0x1800545c1  js      short loc_18005462D
0x1800545c3  mov     rcx, [rbp+arg_18]
0x1800545c7  lea     rdx, [rbp+arg_20]
0x1800545cb  mov     [rbp+arg_20], 0
0x1800545d3  mov     rax, [rcx]
0x1800545d6  mov     rax, [rax+30h]
0x1800545da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800545df  mov     ebx, eax
0x1800545e1  test    eax, eax
0x1800545e3  js      short loc_18005461D
0x1800545e5  mov     rcx, [rbp+arg_20]
0x1800545e9  mov     rdx, r12
0x1800545ec  mov     rax, [rcx]
0x1800545ef  mov     rax, [rax+20h]
0x1800545f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800545f8  mov     ebx, eax
0x1800545fa  test    eax, eax
0x1800545fc  js      short loc_18005460D
0x1800545fe  mov     rcx, [rbp+arg_20]; struct IResourceCandidate *
0x180054602  mov     r8, r14; unsigned int *
0x180054605  mov     rdx, rsi; enum LS_IMAGE_QUALIFIERS *
0x180054608  call    ?_GetImageResourceQualifiers@@YAXPEAUIResourceCandidate@@PEAW4LS_IMAGE_QUALIFIERS@@PEAK@Z; _GetImageResourceQualifiers(IResourceCandidate *,LS_IMAGE_QUALIFIERS *,ulong *)
0x18005460d  mov     rcx, [rbp+arg_20]
0x180054611  mov     rax, [rcx]
0x180054614  mov     rax, [rax+10h]
0x180054618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005461d  mov     rcx, [rbp+arg_18]
0x180054621  mov     rax, [rcx]
0x180054624  mov     rax, [rax+10h]
0x180054628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005462d  mov     rcx, [rbp+pv]; pv
0x180054631  call    cs:__imp_CoTaskMemFree
0x180054637  mov     rcx, [rbp+var_8]
0x18005463b  mov     rax, [rcx]
0x18005463e  mov     rax, [rax+10h]
0x180054642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054647  mov     rcx, [rbp+arg_10]
0x18005464b  mov     rax, [rcx]
0x18005464e  mov     rax, [rax+10h]
0x180054652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054657  mov     rsi, [rsp+40h+arg_8]
0x18005465c  mov     eax, ebx
0x18005465e  mov     rbx, [rsp+40h+arg_0]
0x180054663  add     rsp, 40h
0x180054667  pop     r15
0x180054669  pop     r14
0x18005466b  pop     r12
0x18005466d  pop     rdi
0x18005466e  pop     rbp
0x18005466f  retn
```
