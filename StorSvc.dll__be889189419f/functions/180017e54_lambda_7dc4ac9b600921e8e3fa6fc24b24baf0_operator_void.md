# _lambda_7dc4ac9b600921e8e3fa6fc24b24baf0_::operator()(void)

- ea: `0x180017e54`
- end: `0x1800180aa`
- name: `??R_lambda_7dc4ac9b600921e8e3fa6fc24b24baf0_@@QEAA@XZ`
- size: `598`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180018c00`

## callees

- `0x180012734`
- `0x180014a00`
- `0x1800176ec`
- `0x180017e54`
- `0x180018d54`
- `0x18008a010`

## import_xrefs

- `storageusage!SetStoragePolicySettings` at `0x18001802e`
- `storageusage!SetStoragePolicySettings` at `0x180018042`
- `storageusage!SetStoragePolicySettings` at `0x18001802e`
- `storageusage!SetStoragePolicySettings` at `0x180018042`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180017ec6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180017ec6`
- `cldapi!CfGetSyncRootInfoByPath` at `0x180018017`
- `cldapi!CfGetSyncRootInfoByPath` at `0x180018017`

## string_xrefs

- `0x180017eec`: `onecore\drivers\storage\storsvc\service\dsktoplowdisk.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall _lambda_7dc4ac9b600921e8e3fa6fc24b24baf0_::operator()(__int64 a1)
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
  v1 = CoCreateInstance(
         &GUID_f324e4f9_8496_40b2_a1ff_9617c1c9affe,
         0,
         1u,
         &GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64,
         &v16);
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
      (void *)0x790,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\dsktoplowdisk.cpp",
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
0x180017e54  mov     [rsp-8+arg_10], rbx
0x180017e59  mov     [rsp-8+arg_0], rcx
0x180017e5e  push    rbp
0x180017e5f  push    rsi
0x180017e60  push    rdi
0x180017e61  push    r12
0x180017e63  push    r14
0x180017e65  lea     rbp, [rsp-37h]
0x180017e6a  sub     rsp, 90h
0x180017e71  xor     r14d, r14d
0x180017e74  mov     [rbp+57h+var_70], r14
0x180017e78  mov     [rbp+57h+var_60], r14
0x180017e7c  mov     [rbp+57h+var_78], r14
0x180017e80  mov     [rbp+57h+var_68], r14
0x180017e84  mov     [rbp+57h+var_58], r14
0x180017e88  mov     [rbp+57h+var_50], r14
0x180017e8c  mov     [rbp+57h+var_48], r14
0x180017e90  mov     [rbp+57h+var_40], r14
0x180017e94  mov     [rbp+57h+var_38], r14
0x180017e98  mov     [rbp+57h+var_30], r14
0x180017e9c  mov     [rbp+57h+var_80], r14d
0x180017ea0  lea     rcx, [rbp+57h+var_70]
0x180017ea4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180017ea9  lea     rax, [rbp+57h+var_70]
0x180017ead  mov     qword ptr [rsp+0B0h+ppv], rax; int
0x180017eb2  lea     r9, _GUID_692d40a4_efa1_4089_88f8_15fd6f5f8b64; riid
0x180017eb9  xor     edx, edx; pUnkOuter
0x180017ebb  lea     r8d, [r14+1]; dwClsContext
0x180017ebf  lea     rcx, _GUID_f324e4f9_8496_40b2_a1ff_9617c1c9affe; rclsid
0x180017ec6  call    cs:__imp_CoCreateInstance
0x180017ecc  mov     ebx, eax
0x180017ece  test    eax, eax
0x180017ed0  js      short loc_180017EE5
0x180017ed2  lea     rdx, [rbp+57h+var_60]
0x180017ed6  lea     rcx, [rbp+57h+var_70]
0x180017eda  call    ??$As@UISyncRootManagerPriv@@@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UISyncRootManagerPriv@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<ISyncRootManager>::As<ISyncRootManagerPriv>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ISyncRootManagerPriv>>)
0x180017edf  mov     ebx, eax
0x180017ee1  test    eax, eax
0x180017ee3  jns     short loc_180017F02
0x180017ee5  mov     rcx, [rbp+5Fh]; this
0x180017ee9  mov     r9d, eax; char *
0x180017eec  lea     r8, aOnecoreDrivers_16; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180017ef3  mov     edx, 790h; void *
0x180017ef8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017efd  jmp     loc_180018056
0x180017f02  mov     rdi, [rbp+57h+var_60]
0x180017f06  mov     rax, [rdi]
0x180017f09  mov     rbx, [rax+18h]
0x180017f0d  lea     rcx, [rbp+57h+var_78]
0x180017f11  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180017f16  lea     rdx, [rbp+57h+var_78]
0x180017f1a  mov     rcx, rdi
0x180017f1d  mov     rax, rbx
0x180017f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f25  mov     ebx, eax
0x180017f27  test    eax, eax
0x180017f29  js      short loc_180017EE5
0x180017f2b  mov     rcx, [rbp+57h+var_78]
0x180017f2f  mov     rax, [rcx]
0x180017f32  lea     rdx, [rbp+57h+var_80]
0x180017f36  mov     rax, [rax+18h]
0x180017f3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f3f  mov     ebx, eax
0x180017f41  test    eax, eax
0x180017f43  js      short loc_180017EE5
0x180017f45  mov     esi, r14d
0x180017f48  cmp     [rbp+57h+var_80], r14d
0x180017f4c  jbe     loc_180018053
0x180017f52  or      r12, 0FFFFFFFFFFFFFFFFh
0x180017f56  mov     rdi, [rbp+57h+var_78]
0x180017f5a  mov     rax, [rdi]
0x180017f5d  mov     rbx, [rax+20h]
0x180017f61  lea     rcx, [rbp+57h+var_68]
0x180017f65  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180017f6a  lea     r9, [rbp+57h+var_68]
0x180017f6e  lea     r8, _GUID_ca01c124_2769_4576_bf12_8a54ee671a86
0x180017f75  mov     edx, esi
0x180017f77  mov     rcx, rdi
0x180017f7a  mov     rax, rbx
0x180017f7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f82  test    eax, eax
0x180017f84  js      loc_180018048
0x180017f8a  mov     rdi, [rbp+57h+var_68]
0x180017f8e  mov     rax, [rdi]
0x180017f91  mov     rbx, [rax+18h]
0x180017f95  lea     rcx, [rbp+57h+var_58]
0x180017f99  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180017f9e  mov     [rbp+57h+var_50], r12
0x180017fa2  mov     [rbp+57h+var_48], r12
0x180017fa6  lea     rdx, [rbp+57h+var_58]
0x180017faa  mov     rcx, rdi
0x180017fad  mov     rax, rbx
0x180017fb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017fb5  test    eax, eax
0x180017fb7  js      loc_180018048
0x180017fbd  mov     rdi, [rbp+57h+var_70]
0x180017fc1  mov     rax, [rdi]
0x180017fc4  mov     rbx, [rax+88h]
0x180017fcb  lea     rcx, [rbp+57h+var_40]
0x180017fcf  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180017fd4  mov     [rbp+57h+var_38], r12
0x180017fd8  mov     [rbp+57h+var_30], r12
0x180017fdc  lea     r9, [rbp+57h+var_40]
0x180017fe0  xor     r8d, r8d
0x180017fe3  mov     rdx, [rbp+57h+var_58]
0x180017fe7  mov     rcx, rdi
0x180017fea  mov     rax, rbx
0x180017fed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ff2  test    eax, eax
0x180017ff4  js      short loc_180018048
0x180017ff6  mov     [rbp+57h+arg_8], r14
0x180017ffa  mov     dword ptr [rbp+57h+arg_0], r14d
0x180017ffe  lea     rax, [rbp+57h+arg_0]
0x180018002  mov     qword ptr [rsp+0B0h+ppv], rax
0x180018007  mov     r9d, 8
0x18001800d  lea     r8, [rbp+57h+arg_8]
0x180018011  xor     edx, edx
0x180018013  mov     rcx, [rbp+57h+var_40]
0x180018017  call    cs:__imp_CfGetSyncRootInfoByPath
0x18001801d  test    eax, eax
0x18001801f  js      short loc_180018048
0x180018021  mov     r8d, 1
0x180018027  mov     rdx, [rbp+57h+var_58]
0x18001802b  mov     ecx, r8d
0x18001802e  call    cs:__imp_SetStoragePolicySettings
0x180018034  mov     r8d, 1Eh
0x18001803a  mov     rdx, [rbp+57h+var_58]
0x18001803e  lea     ecx, [r8-17h]
0x180018042  call    cs:__imp_SetStoragePolicySettings
0x180018048  inc     esi
0x18001804a  cmp     esi, [rbp+57h+var_80]
0x18001804d  jb      loc_180017F56
0x180018053  mov     ebx, r14d
0x180018056  lea     rcx, [rbp+57h+var_40]
0x18001805a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18001805f  nop
0x180018060  lea     rcx, [rbp+57h+var_58]
0x180018064  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180018069  nop
0x18001806a  lea     rcx, [rbp+57h+var_68]
0x18001806e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180018073  nop
0x180018074  lea     rcx, [rbp+57h+var_78]
0x180018078  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001807d  nop
0x18001807e  lea     rcx, [rbp+57h+var_60]
0x180018082  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180018087  nop
0x180018088  lea     rcx, [rbp+57h+var_70]
0x18001808c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180018091  mov     eax, ebx
0x180018093  mov     rbx, [rsp+0B0h+arg_10]
0x18001809b  add     rsp, 90h
0x1800180a2  pop     r14
0x1800180a4  pop     r12
0x1800180a6  pop     rdi
0x1800180a7  pop     rsi
0x1800180a8  pop     rbp
0x1800180a9  retn
```
