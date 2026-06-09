# CreateStorageItemVectorFromShellItemArray(IShellItemArray *,ushort const *,ulong,Windows::Foundation::Collections::IVector<Windows::Storage::IStorageItem *> * *)

- ea: `0x180023334`
- end: `0x1800234f1`
- name: `?CreateStorageItemVectorFromShellItemArray@@YAJPEAUIShellItemArray@@PEBGKPEAPEAU?$IVector@PEAUIStorageItem@Storage@Windows@@@Collections@Foundation@Windows@@@Z`
- size: `445`
- prototype: `__int64 __fastcall(__int64 *, __int64, unsigned int, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180098c1c`

## callees

- `0x180010a34`
- `0x180011328`
- `0x180023334`
- `0x18004b620`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-storage-exports-external-l1-1-0!STORAGE_CreateStorageItemFromShellItem_FullTrustCaller` at `0x180023457`
- `api-ms-win-storage-exports-external-l1-1-0!STORAGE_CreateStorageItemFromShellItem_FullTrustCaller` at `0x180023457`
- `api-ms-win-storage-exports-external-l1-1-0!STORAGE_CreateStorageItemFromShellItem_FullTrustCaller_ForPackage` at `0x180023444`
- `api-ms-win-storage-exports-external-l1-1-0!STORAGE_CreateStorageItemFromShellItem_FullTrustCaller_ForPackage` at `0x180023444`
- `api-ms-win-storage-exports-external-l1-1-0!STORAGE_CreateStorageItemFromShellItem_FullTrustCaller_UseImplicitFlagsAndPackage` at `0x180023413`
- `api-ms-win-storage-exports-external-l1-1-0!STORAGE_CreateStorageItemFromShellItem_FullTrustCaller_UseImplicitFlagsAndPackage` at `0x180023413`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall CreateStorageItemVectorFromShellItemArray(__int64 *a1, __int64 a2, unsigned int a3, _QWORD *a4)
{
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rdi
  int v10; // ebx
  __int64 v11; // rax
  unsigned int v12; // esi
  __int64 v13; // rax
  __int64 (__fastcall *v14)(__int64 *, _QWORD, _QWORD *); // rbx
  int v15; // eax
  __int64 v16; // rcx
  _QWORD v18[2]; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v19; // [rsp+80h] [rbp+40h] BYREF
  __int64 v20; // [rsp+88h] [rbp+48h] BYREF

  v19 = a3;
  *a4 = 0;
  v20 = 0;
  Microsoft::WRL::ComPtr<Execution::IExecutionServicesEventCallback>::InternalRelease(&v20);
  v8 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Storage::IStorageItem,Windows::Foundation::Collections::Internal::AgileVector<Windows::Storage::IStorageItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Storage::IStorageItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::IStorageItem *>,0>>(
         v7,
         &v20);
  v9 = v20;
  v10 = v8;
  if ( v8 >= 0 )
  {
    v11 = *a1;
    v19 = 0;
    v12 = 0;
    v10 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(v11 + 56))(a1, &v19);
    if ( v10 >= 0 )
    {
      while ( v12 < v19 )
      {
        v13 = *a1;
        v18[0] = 0;
        v14 = *(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD *))(v13 + 64);
        Microsoft::WRL::ComPtr<Execution::IExecutionServicesEventCallback>::InternalRelease(v18);
        v10 = v14(a1, v12, v18);
        if ( v10 >= 0 )
        {
          v20 = 0;
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v20);
          if ( (int)STORAGE_CreateStorageItemFromShellItem_FullTrustCaller_UseImplicitFlagsAndPackage(
                      v18[0],
                      1,
                      &GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30,
                      &v20) >= 0
            || ((Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v20), !a2)
              ? (v15 = STORAGE_CreateStorageItemFromShellItem_FullTrustCaller(
                         v18[0],
                         1,
                         &GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30,
                         &v20))
              : (v15 = STORAGE_CreateStorageItemFromShellItem_FullTrustCaller_ForPackage(
                         v18[0],
                         1,
                         a2,
                         &GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30,
                         &v20)),
                v10 = v15,
                v15 >= 0) )
          {
            v10 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v9 + 104LL))(v9, v20);
          }
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v20);
        }
        v16 = v18[0];
        if ( v18[0] )
        {
          v18[0] = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
        }
        ++v12;
        if ( v10 < 0 )
          goto LABEL_17;
      }
      v10 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v9)(
              v9,
              &GUID_802508e2_9c2c_5b91_89a8_39bcf7223344,
              a4);
    }
  }
LABEL_17:
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180023334  mov     [rsp-28h+arg_0], rbx
0x180023339  mov     [rsp-28h+arg_8], rsi
0x18002333e  mov     [rsp-28h+arg_10], r8d
0x180023343  push    rbp
0x180023344  push    rdi
0x180023345  push    r12
0x180023347  push    r14
0x180023349  push    r15
0x18002334b  mov     rbp, rsp
0x18002334e  sub     rsp, 40h
0x180023352  mov     r14, rcx
0x180023355  mov     qword ptr [r9], 0
0x18002335c  lea     rcx, [rbp+arg_18]
0x180023360  mov     [rbp+arg_18], 0
0x180023368  mov     r12, r9
0x18002336b  mov     r15, rdx
0x18002336e  call    ?InternalRelease@?$ComPtr@UIExecutionServicesEventCallback@Execution@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Execution::IExecutionServicesEventCallback>::InternalRelease(void)
0x180023373  lea     rdx, [rbp+arg_18]
0x180023377  call    ??$CreateExternalObjectVector@UIStorageItem@Storage@Windows@@V?$AgileVector@PEAUIStorageItem@Storage@Windows@@U?$DefaultEqualityPredicate@PEAUIStorageItem@Storage@Windows@@@Internal@Collections@Foundation@3@U?$DefaultLifetimeTraits@PEAUIStorageItem@Storage@Windows@@@5673@$0A@@Internal@Collections@Foundation@3@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAUIStorageItem@Storage@Windows@@U?$DefaultEqualityPredicate@PEAUIStorageItem@Storage@Windows@@@Internal@Collections@Foundation@3@U?$DefaultLifetimeTraits@PEAUIStorageItem@Storage@Windows@@@5673@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Storage::IStorageItem,Windows::Foundation::Collections::Internal::AgileVector<Windows::Storage::IStorageItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Storage::IStorageItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::IStorageItem *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Storage::IStorageItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Storage::IStorageItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Storage::IStorageItem *>,0> * *)
0x18002337c  mov     rdi, [rbp+arg_18]
0x180023380  mov     ebx, eax
0x180023382  test    eax, eax
0x180023384  js      loc_1800234C4
0x18002338a  mov     rax, [r14]
0x18002338d  lea     rdx, [rbp+arg_10]
0x180023391  mov     rcx, r14
0x180023394  mov     [rbp+arg_10], 0
0x18002339b  mov     rax, [rax+38h]
0x18002339f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800233a4  xor     esi, esi
0x1800233a6  mov     ebx, eax
0x1800233a8  test    eax, eax
0x1800233aa  js      loc_1800234C4
0x1800233b0  cmp     esi, [rbp+arg_10]
0x1800233b3  jnb     loc_1800234AA
0x1800233b9  mov     rax, [r14]
0x1800233bc  lea     rcx, [rbp+var_10]
0x1800233c0  mov     [rbp+var_10], 0
0x1800233c8  mov     rbx, [rax+40h]
0x1800233cc  call    ?InternalRelease@?$ComPtr@UIExecutionServicesEventCallback@Execution@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Execution::IExecutionServicesEventCallback>::InternalRelease(void)
0x1800233d1  lea     r8, [rbp+var_10]
0x1800233d5  mov     edx, esi
0x1800233d7  mov     rcx, r14
0x1800233da  mov     rax, rbx
0x1800233dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800233e2  mov     ebx, eax
0x1800233e4  test    eax, eax
0x1800233e6  js      loc_180023481
0x1800233ec  lea     rcx, [rbp+arg_18]
0x1800233f0  mov     [rbp+arg_18], 0
0x1800233f8  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800233fd  mov     rcx, [rbp+var_10]
0x180023401  lea     r9, [rbp+arg_18]
0x180023405  mov     ebx, 1
0x18002340a  lea     r8, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
0x180023411  mov     edx, ebx
0x180023413  call    cs:__imp_STORAGE_CreateStorageItemFromShellItem_FullTrustCaller_UseImplicitFlagsAndPackage
0x180023419  test    eax, eax
0x18002341b  jns     short loc_180023463
0x18002341d  lea     rcx, [rbp+arg_18]
0x180023421  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180023426  mov     rcx, [rbp+var_10]
0x18002342a  mov     edx, ebx
0x18002342c  test    r15, r15
0x18002342f  jz      short loc_18002344C
0x180023431  lea     rax, [rbp+arg_18]
0x180023435  mov     r8, r15
0x180023438  lea     r9, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
0x18002343f  mov     [rsp+40h+var_20], rax
0x180023444  call    cs:__imp_STORAGE_CreateStorageItemFromShellItem_FullTrustCaller_ForPackage
0x18002344a  jmp     short loc_18002345D
0x18002344c  lea     r9, [rbp+arg_18]
0x180023450  lea     r8, _GUID_4207a996_ca2f_42f7_bde8_8b10457a7f30
0x180023457  call    cs:__imp_STORAGE_CreateStorageItemFromShellItem_FullTrustCaller
0x18002345d  mov     ebx, eax
0x18002345f  test    eax, eax
0x180023461  js      short loc_180023478
0x180023463  mov     rax, [rdi]
0x180023466  mov     rcx, rdi
0x180023469  mov     rdx, [rbp+arg_18]
0x18002346d  mov     rax, [rax+68h]
0x180023471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023476  mov     ebx, eax
0x180023478  lea     rcx, [rbp+arg_18]
0x18002347c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180023481  mov     rcx, [rbp+var_10]
0x180023485  test    rcx, rcx
0x180023488  jz      short loc_18002349E
0x18002348a  mov     [rbp+var_10], 0
0x180023492  mov     rax, [rcx]
0x180023495  mov     rax, [rax+10h]
0x180023499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002349e  inc     esi
0x1800234a0  test    ebx, ebx
0x1800234a2  jns     loc_1800233B0
0x1800234a8  jmp     short loc_1800234C4
0x1800234aa  mov     rax, [rdi]
0x1800234ad  lea     rdx, _GUID_802508e2_9c2c_5b91_89a8_39bcf7223344
0x1800234b4  mov     r8, r12
0x1800234b7  mov     rcx, rdi
0x1800234ba  mov     rax, [rax]
0x1800234bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800234c2  mov     ebx, eax
0x1800234c4  test    rdi, rdi
0x1800234c7  jz      short loc_1800234D8
0x1800234c9  mov     rax, [rdi]
0x1800234cc  mov     rcx, rdi
0x1800234cf  mov     rax, [rax+10h]
0x1800234d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800234d8  mov     rsi, [rsp+40h+arg_8]
0x1800234dd  mov     eax, ebx
0x1800234df  mov     rbx, [rsp+40h+arg_0]
0x1800234e4  add     rsp, 40h
0x1800234e8  pop     r15
0x1800234ea  pop     r14
0x1800234ec  pop     r12
0x1800234ee  pop     rdi
0x1800234ef  pop     rbp
0x1800234f0  retn
```
