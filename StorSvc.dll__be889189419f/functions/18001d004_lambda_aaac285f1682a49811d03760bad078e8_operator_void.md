# _lambda_aaac285f1682a49811d03760bad078e8_::operator()(void)

- ea: `0x18001d004`
- end: `0x18001d25a`
- name: `??R_lambda_aaac285f1682a49811d03760bad078e8_@@QEAA@XZ`
- size: `598`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001dc60`

## callees

- `0x180012734`
- `0x180014a00`
- `0x1800176ec`
- `0x180018d54`
- `0x18001d004`
- `0x18008a010`

## import_xrefs

- `storageusage!SetStoragePolicySettings` at `0x18001d1de`
- `storageusage!SetStoragePolicySettings` at `0x18001d1f2`
- `storageusage!SetStoragePolicySettings` at `0x18001d1de`
- `storageusage!SetStoragePolicySettings` at `0x18001d1f2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d076`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d076`
- `cldapi!CfGetSyncRootInfoByPath` at `0x18001d1c7`
- `cldapi!CfGetSyncRootInfoByPath` at `0x18001d1c7`

## string_xrefs

- `0x18001d09c`: `onecore\drivers\storage\storsvc\service\storagelowdisk.cpp`

## pseudocode

```c
__int64 __fastcall _lambda_aaac285f1682a49811d03760bad078e8_::operator()(__int64 a1)
{
  int v1; // eax
  unsigned int v2; // ebx
  __int64 v3; // rdi
  __int64 (__fastcall *v4)(__int64, __int64 *); // rbx
  unsigned int i; // esi
  __int64 v6; // rdi
  int (__fastcall *v7)(__int64, _QWORD, GUID *, __int64 *); // rbx
  __int64 v8; // rdi
  int (__fastcall *v9)(__int64, __int64 *); // rbx
  LPVOID v10; // rdi
  int (__fastcall *v11)(LPVOID, __int64, _QWORD, __int64 *); // rbx
  int ppv; // [rsp+20h] [rbp-39h]
  unsigned int v14; // [rsp+30h] [rbp-29h] BYREF
  __int64 v15; // [rsp+38h] [rbp-21h] BYREF
  LPVOID v16; // [rsp+40h] [rbp-19h] BYREF
  __int64 v17; // [rsp+48h] [rbp-11h] BYREF
  __int64 v18; // [rsp+50h] [rbp-9h] BYREF
  __int64 v19; // [rsp+58h] [rbp-1h] BYREF
  __int64 v20; // [rsp+60h] [rbp+7h]
  __int64 v21; // [rsp+68h] [rbp+Fh]
  __int64 v22; // [rsp+70h] [rbp+17h] BYREF
  __int64 v23; // [rsp+78h] [rbp+1Fh]
  __int64 v24; // [rsp+80h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  __int64 v26; // [rsp+C0h] [rbp+67h] BYREF
  __int64 v27; // [rsp+C8h] [rbp+6Fh] BYREF

  v26 = a1;
  v16 = 0;
  v18 = 0;
  v15 = 0;
  v17 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  v14 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v16);
  v1 = CoCreateInstance(&rclsid, 0, 1u, &GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64, &v16);
  v2 = v1;
  if ( v1 < 0 )
    goto LABEL_3;
  v1 = Microsoft::WRL::ComPtr<ISyncRootManager>::As<ISyncRootManagerPriv>(
         (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v16,
         (__int64)&v18);
  v2 = v1;
  if ( v1 < 0
    || (v3 = v18,
        v4 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v18 + 24LL),
        Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v15),
        v1 = v4(v3, &v15),
        v2 = v1,
        v1 < 0)
    || (v1 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v15 + 24LL))(v15, &v14), v2 = v1, v1 < 0) )
  {
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5D4,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagelowdisk.cpp",
      (const char *)(unsigned int)v1,
      ppv);
  }
  else
  {
    for ( i = 0; i < v14; ++i )
    {
      v6 = v15;
      v7 = *(int (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v15 + 32LL);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v17);
      if ( v7(v6, i, &GUID_ca01c124_2769_4576_bf12_8a54ee671a86, &v17) >= 0 )
      {
        v8 = v17;
        v9 = *(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v17 + 24LL);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v19);
        v20 = -1;
        v21 = -1;
        if ( v9(v8, &v19) >= 0 )
        {
          v10 = v16;
          v11 = *(int (__fastcall **)(LPVOID, __int64, _QWORD, __int64 *))(*(_QWORD *)v16 + 136LL);
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v22);
          v23 = -1;
          v24 = -1;
          if ( v11(v10, v19, 0, &v22) >= 0 )
          {
            v27 = 0;
            LODWORD(v26) = 0;
            if ( (int)CfGetSyncRootInfoByPath(v22, 0, &v27, 8, &v26) >= 0 )
            {
              SetStoragePolicySettings(1, v19);
              SetStoragePolicySettings(7, v19);
            }
          }
        }
      }
    }
    v2 = 0;
  }
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v22);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v19);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v17);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v15);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v18);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v16);
  return v2;
}

```

## disassembly

```asm
0x18001d004  mov     [rsp-8+arg_10], rbx
0x18001d009  mov     [rsp-8+arg_0], rcx
0x18001d00e  push    rbp
0x18001d00f  push    rsi
0x18001d010  push    rdi
0x18001d011  push    r12
0x18001d013  push    r14
0x18001d015  lea     rbp, [rsp-37h]
0x18001d01a  sub     rsp, 90h
0x18001d021  xor     r14d, r14d
0x18001d024  mov     [rbp+57h+var_70], r14
0x18001d028  mov     [rbp+57h+var_60], r14
0x18001d02c  mov     [rbp+57h+var_78], r14
0x18001d030  mov     [rbp+57h+var_68], r14
0x18001d034  mov     [rbp+57h+var_58], r14
0x18001d038  mov     [rbp+57h+var_50], r14
0x18001d03c  mov     [rbp+57h+var_48], r14
0x18001d040  mov     [rbp+57h+var_40], r14
0x18001d044  mov     [rbp+57h+var_38], r14
0x18001d048  mov     [rbp+57h+var_30], r14
0x18001d04c  mov     [rbp+57h+var_80], r14d
0x18001d050  lea     rcx, [rbp+57h+var_70]
0x18001d054  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d059  lea     rax, [rbp+57h+var_70]
0x18001d05d  mov     qword ptr [rsp+0B0h+ppv], rax; int
0x18001d062  lea     r9, _GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64; riid
0x18001d069  xor     edx, edx; pUnkOuter
0x18001d06b  lea     r8d, [r14+1]; dwClsContext
0x18001d06f  lea     rcx, rclsid; rclsid
0x18001d076  call    cs:__imp_CoCreateInstance
0x18001d07c  mov     ebx, eax
0x18001d07e  test    eax, eax
0x18001d080  js      short loc_18001D095
0x18001d082  lea     rdx, [rbp+57h+var_60]
0x18001d086  lea     rcx, [rbp+57h+var_70]
0x18001d08a  call    ??$As@UISyncRootManagerPriv@@@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UISyncRootManagerPriv@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<ISyncRootManager>::As<ISyncRootManagerPriv>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ISyncRootManagerPriv>>)
0x18001d08f  mov     ebx, eax
0x18001d091  test    eax, eax
0x18001d093  jns     short loc_18001D0B2
0x18001d095  mov     rcx, [rbp+5Fh]; this
0x18001d099  mov     r9d, eax; char *
0x18001d09c  lea     r8, aOnecoreDrivers_7; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18001d0a3  mov     edx, 5D4h; void *
0x18001d0a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d0ad  jmp     loc_18001D206
0x18001d0b2  mov     rdi, [rbp+57h+var_60]
0x18001d0b6  mov     rax, [rdi]
0x18001d0b9  mov     rbx, [rax+18h]
0x18001d0bd  lea     rcx, [rbp+57h+var_78]
0x18001d0c1  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d0c6  lea     rdx, [rbp+57h+var_78]
0x18001d0ca  mov     rcx, rdi
0x18001d0cd  mov     rax, rbx
0x18001d0d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d0d5  mov     ebx, eax
0x18001d0d7  test    eax, eax
0x18001d0d9  js      short loc_18001D095
0x18001d0db  mov     rcx, [rbp+57h+var_78]
0x18001d0df  mov     rax, [rcx]
0x18001d0e2  lea     rdx, [rbp+57h+var_80]
0x18001d0e6  mov     rax, [rax+18h]
0x18001d0ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d0ef  mov     ebx, eax
0x18001d0f1  test    eax, eax
0x18001d0f3  js      short loc_18001D095
0x18001d0f5  mov     esi, r14d
0x18001d0f8  cmp     [rbp+57h+var_80], r14d
0x18001d0fc  jbe     loc_18001D203
0x18001d102  or      r12, 0FFFFFFFFFFFFFFFFh
0x18001d106  mov     rdi, [rbp+57h+var_78]
0x18001d10a  mov     rax, [rdi]
0x18001d10d  mov     rbx, [rax+20h]
0x18001d111  lea     rcx, [rbp+57h+var_68]
0x18001d115  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d11a  lea     r9, [rbp+57h+var_68]
0x18001d11e  lea     r8, _GUID_ca01c124_2769_4576_bf12_8a54ee671a86
0x18001d125  mov     edx, esi
0x18001d127  mov     rcx, rdi
0x18001d12a  mov     rax, rbx
0x18001d12d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d132  test    eax, eax
0x18001d134  js      loc_18001D1F8
0x18001d13a  mov     rdi, [rbp+57h+var_68]
0x18001d13e  mov     rax, [rdi]
0x18001d141  mov     rbx, [rax+18h]
0x18001d145  lea     rcx, [rbp+57h+var_58]
0x18001d149  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001d14e  mov     [rbp+57h+var_50], r12
0x18001d152  mov     [rbp+57h+var_48], r12
0x18001d156  lea     rdx, [rbp+57h+var_58]
0x18001d15a  mov     rcx, rdi
0x18001d15d  mov     rax, rbx
0x18001d160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d165  test    eax, eax
0x18001d167  js      loc_18001D1F8
0x18001d16d  mov     rdi, [rbp+57h+var_70]
0x18001d171  mov     rax, [rdi]
0x18001d174  mov     rbx, [rax+88h]
0x18001d17b  lea     rcx, [rbp+57h+var_40]
0x18001d17f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001d184  mov     [rbp+57h+var_38], r12
0x18001d188  mov     [rbp+57h+var_30], r12
0x18001d18c  lea     r9, [rbp+57h+var_40]
0x18001d190  xor     r8d, r8d
0x18001d193  mov     rdx, [rbp+57h+var_58]
0x18001d197  mov     rcx, rdi
0x18001d19a  mov     rax, rbx
0x18001d19d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1a2  test    eax, eax
0x18001d1a4  js      short loc_18001D1F8
0x18001d1a6  mov     [rbp+57h+arg_8], r14
0x18001d1aa  mov     dword ptr [rbp+57h+arg_0], r14d
0x18001d1ae  lea     rax, [rbp+57h+arg_0]
0x18001d1b2  mov     qword ptr [rsp+0B0h+ppv], rax
0x18001d1b7  mov     r9d, 8
0x18001d1bd  lea     r8, [rbp+57h+arg_8]
0x18001d1c1  xor     edx, edx
0x18001d1c3  mov     rcx, [rbp+57h+var_40]
0x18001d1c7  call    cs:__imp_CfGetSyncRootInfoByPath
0x18001d1cd  test    eax, eax
0x18001d1cf  js      short loc_18001D1F8
0x18001d1d1  mov     r8d, 1
0x18001d1d7  mov     rdx, [rbp+57h+var_58]
0x18001d1db  mov     ecx, r8d
0x18001d1de  call    cs:__imp_SetStoragePolicySettings
0x18001d1e4  mov     r8d, 1Eh
0x18001d1ea  mov     rdx, [rbp+57h+var_58]
0x18001d1ee  lea     ecx, [r8-17h]
0x18001d1f2  call    cs:__imp_SetStoragePolicySettings
0x18001d1f8  inc     esi
0x18001d1fa  cmp     esi, [rbp+57h+var_80]
0x18001d1fd  jb      loc_18001D106
0x18001d203  mov     ebx, r14d
0x18001d206  lea     rcx, [rbp+57h+var_40]
0x18001d20a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001d20f  nop
0x18001d210  lea     rcx, [rbp+57h+var_58]
0x18001d214  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001d219  nop
0x18001d21a  lea     rcx, [rbp+57h+var_68]
0x18001d21e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d223  nop
0x18001d224  lea     rcx, [rbp+57h+var_78]
0x18001d228  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d22d  nop
0x18001d22e  lea     rcx, [rbp+57h+var_60]
0x18001d232  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d237  nop
0x18001d238  lea     rcx, [rbp+57h+var_70]
0x18001d23c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001d241  mov     eax, ebx
0x18001d243  mov     rbx, [rsp+0B0h+arg_10]
0x18001d24b  add     rsp, 90h
0x18001d252  pop     r14
0x18001d254  pop     r12
0x18001d256  pop     rdi
0x18001d257  pop     rsi
0x18001d258  pop     rbp
0x18001d259  retn
```
