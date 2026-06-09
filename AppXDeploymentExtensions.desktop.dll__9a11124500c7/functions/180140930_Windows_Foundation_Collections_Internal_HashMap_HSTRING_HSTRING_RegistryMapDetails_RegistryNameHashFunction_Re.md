# Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Remove(HSTRING__ *)

- ea: `0x180140930`
- end: `0x180140ae5`
- name: `?Remove@?$HashMap@PEAUHSTRING__@@PEAU1@URegistryNameHashFunction@RegistryMapDetails@@URegistryNameEqualityPredicate@3@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U56789@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@6789@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@@Z`
- size: `437`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180025fe0`
- `0x180028e14`
- `0x180029d8c`
- `0x180029da8`
- `0x1800375f8`
- `0x180047e34`
- `0x180051654`
- `0x180140930`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180140a80`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180140a80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801409ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180140a01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180140a8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180140a9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801409ef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180140a01`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180140a8f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180140a9e`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1801409c7`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1801409c7`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::Remove(
        __int64 a1,
        __int64 a2)
{
  int v3; // esi
  HSTRING v4; // rbx
  HSTRING v5; // rdi
  __int64 v6; // r14
  __int64 v7; // r8
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // rcx
  RTL_SRWLOCK *v11; // rcx
  __int64 v13; // [rsp+78h] [rbp+48h] BYREF
  __int64 v14; // [rsp+80h] [rbp+50h] BYREF
  RTL_SRWLOCK *v15; // [rsp+88h] [rbp+58h] BYREF

  v13 = a2;
  v3 = Windows::Foundation::Collections::Internal::HashMap<_GUID,OSIntegration::DEH::ComInterfaceRegistration *,Windows::Foundation::Collections::Internal::DefaultHash<_GUID>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<_GUID>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<_GUID>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<OSIntegration::DEH::ComInterfaceRegistration *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<_GUID,OSIntegration::DEH::ComInterfaceRegistration *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<_GUID>>>::EnsureInitialized();
  if ( v3 >= 0 )
  {
    v4 = 0;
    LODWORD(v14) = 0;
    v5 = 0;
    XWinRT::SerializingLockPolicy::Write(&v15, a1 + 128, &v14);
    v3 = v14;
    if ( (int)v14 >= 0 )
    {
      XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(&v14, *(unsigned __int8 *)(a1 + 154), a1 + 156);
      v14 = 0;
      v3 = XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::Lookup(
             a1 + 40,
             &v13,
             &v14);
      if ( v3 >= 0 )
      {
        v6 = v14;
        if ( v14 )
        {
          v3 = XWinRT::SecureVersionTag::TagManager::ChangeVersion((XWinRT::SecureVersionTag::TagManager *)(a1 + 144));
          if ( v3 >= 0 )
          {
            v4 = *(HSTRING *)v6;
            WindowsDeleteString(0);
            v5 = *(HSTRING *)(v6 + 8);
            WindowsDeleteString(0);
            if ( v6 )
            {
              v7 = (unsigned int)(*(_DWORD *)(v6 + 24) % *(_DWORD *)(a1 + 64));
              v8 = *(_QWORD *)(a1 + 48);
              v9 = *(_QWORD *)(v8 + 8 * v7);
              if ( v6 == v9 )
              {
                v9 = 0;
              }
              else
              {
                while ( *(_QWORD *)(v9 + 16) != v6 )
                  v9 = *(_QWORD *)(v9 + 16);
              }
              v10 = *(_QWORD *)(v6 + 16);
              if ( v9 )
                *(_QWORD *)(v9 + 16) = v10;
              else
                *(_QWORD *)(v8 + 8 * v7) = v10;
              XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::FreeNode(
                a1 + 40,
                v6);
              v3 = 0;
            }
            else
            {
              v4 = 0;
              v3 = -2147418113;
              v5 = 0;
            }
          }
        }
        else
        {
          v3 = -2147483637;
          RoOriginateError(2147483659LL, 0);
        }
      }
    }
    if ( v15 )
    {
      v11 = v15 + 1;
      if ( LODWORD(v15->Ptr) == 1 )
        LODWORD(v11->Ptr) += 0x10000000;
      else
        ReleaseSRWLockExclusive(v11);
    }
    WindowsDeleteString(v5);
    WindowsDeleteString(v4);
  }
  if ( v3 >= 0 )
    return (unsigned int)Windows::Foundation::Collections::Internal::HashMapOptions<_GUID,OSIntegration::DEH::ComProxyStubRegistration *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<_GUID>,0,0,0>::RaiseEvent(
                           (unsigned __int8)v14,
                           *(unsigned __int8 *)(a1 + 153),
                           a1,
                           2,
                           v13);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180140930  mov     [rsp-38h+arg_8], rdx
0x180140935  push    rbp
0x180140936  push    rbx
0x180140937  push    rsi
0x180140938  push    rdi
0x180140939  push    r13
0x18014093b  push    r14
0x18014093d  push    r15
0x18014093f  mov     rbp, rsp
0x180140942  sub     rsp, 30h
0x180140946  mov     r15, rcx
0x180140949  call    ?EnsureInitialized@?$HashMap@U_GUID@@PEAVComInterfaceRegistration@DEH@OSIntegration@@U?$DefaultHash@U_GUID@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@U_GUID@@@6789@U?$DefaultLifetimeTraits@U_GUID@@@6789@U?$DefaultLifetimeTraits@PEAVComInterfaceRegistration@DEH@OSIntegration@@@6789@U?$DefaultHashMapOptions@U_GUID@@PEAVComInterfaceRegistration@DEH@OSIntegration@@U?$DefaultLifetimeTraits@U_GUID@@@Internal@Collections@Foundation@Windows@@@6789@@Internal@Collections@Foundation@Windows@@AEBAJXZ; Windows::Foundation::Collections::Internal::HashMap<_GUID,OSIntegration::DEH::ComInterfaceRegistration *,Windows::Foundation::Collections::Internal::DefaultHash<_GUID>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<_GUID>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<_GUID>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<OSIntegration::DEH::ComInterfaceRegistration *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<_GUID,OSIntegration::DEH::ComInterfaceRegistration *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<_GUID>>>::EnsureInitialized(void)
0x18014094e  mov     esi, eax
0x180140950  test    eax, eax
0x180140952  js      loc_180140AAA
0x180140958  xor     ebx, ebx
0x18014095a  lea     rdx, [r15+80h]
0x180140961  lea     r8, [rbp+arg_10]
0x180140965  mov     dword ptr [rbp+arg_10], ebx
0x180140968  lea     rcx, [rbp+arg_18]
0x18014096c  xor     edi, edi
0x18014096e  call    ?Write@SerializingLockPolicy@XWinRT@@SA?AV?$LockHolder@VComLock@XWinRT@@UAcquireWrite@detail@2@@detail@2@AEAVComLock@2@PEAJ@Z; XWinRT::SerializingLockPolicy::Write(XWinRT::ComLock &,long *)
0x180140973  mov     esi, dword ptr [rbp+arg_10]
0x180140976  test    esi, esi
0x180140978  js      loc_180140A66
0x18014097e  movzx   edx, byte ptr [r15+9Ah]
0x180140986  lea     r8, [r15+9Ch]
0x18014098d  lea     rcx, [rbp+arg_10]
0x180140991  call    ??0?$ReentrancyGuard@$0A@@detail@XWinRT@@QEAA@ZZ; XWinRT::detail::ReentrancyGuard<0>::ReentrancyGuard<0>(...)
0x180140996  lea     r8, [rbp+arg_10]
0x18014099a  mov     [rbp+arg_10], rbx
0x18014099e  lea     rdx, [rbp+arg_8]
0x1801409a2  lea     rcx, [r15+28h]
0x1801409a6  call    ?Lookup@?$XHashMap@PEAUHSTRING__@@PEAUIInspectable@@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAUIInspectable@@URegistryNameHashFunction@RegistryMapDetails@@URegistryNameEqualityPredicate@4@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@789Windows@@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIInspectable@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@789Windows@@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUIInspectable@@@XWinRT@@@XWinRT@@QEAAJAEBQEAUHSTRING__@@PEAPEAVCPair@12@@Z; XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::Lookup(HSTRING__ * const &,XWinRT::XHashMap<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,IInspectable *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,IInspectable *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<IInspectable *>>::CPair * *)
0x1801409ab  mov     esi, eax
0x1801409ad  test    eax, eax
0x1801409af  js      loc_180140A66
0x1801409b5  mov     r14, [rbp+arg_10]
0x1801409b9  test    r14, r14
0x1801409bc  jnz     short loc_1801409D8
0x1801409be  mov     esi, 8000000Bh
0x1801409c3  xor     edx, edx
0x1801409c5  mov     ecx, esi
0x1801409c7  call    cs:__imp_RoOriginateError
0x1801409ce  nop     dword ptr [rax+rax+00h]
0x1801409d3  jmp     loc_180140A66
0x1801409d8  lea     rcx, [r15+90h]; this
0x1801409df  call    ?ChangeVersion@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::ChangeVersion(void)
0x1801409e4  mov     esi, eax
0x1801409e6  test    eax, eax
0x1801409e8  js      short loc_180140A66
0x1801409ea  mov     rbx, [r14]
0x1801409ed  xor     ecx, ecx; string
0x1801409ef  call    cs:__imp_WindowsDeleteString
0x1801409f6  nop     dword ptr [rax+rax+00h]
0x1801409fb  mov     rdi, [r14+8]
0x1801409ff  xor     ecx, ecx; string
0x180140a01  call    cs:__imp_WindowsDeleteString
0x180140a08  nop     dword ptr [rax+rax+00h]
0x180140a0d  test    r14, r14
0x180140a10  jz      short loc_180140A5D
0x180140a12  mov     eax, [r14+18h]
0x180140a16  xor     edx, edx
0x180140a18  div     dword ptr [r15+40h]
0x180140a1c  mov     r8d, edx
0x180140a1f  mov     rdx, [r15+30h]
0x180140a23  mov     rax, [rdx+r8*8]
0x180140a27  cmp     r14, rax
0x180140a2a  jnz     short loc_180140A34
0x180140a2c  xor     eax, eax
0x180140a2e  jmp     short loc_180140A3A
0x180140a30  mov     rax, [rax+10h]
0x180140a34  cmp     [rax+10h], r14
0x180140a38  jnz     short loc_180140A30
0x180140a3a  mov     rcx, [r14+10h]
0x180140a3e  test    rax, rax
0x180140a41  jnz     short loc_180140A49
0x180140a43  mov     [rdx+r8*8], rcx
0x180140a47  jmp     short loc_180140A4D
0x180140a49  mov     [rax+10h], rcx
0x180140a4d  mov     rdx, r14
0x180140a50  lea     rcx, [r15+28h]
0x180140a54  call    ?FreeNode@?$XHashMap@PEAUHSTRING__@@PEAU1@UKeyTraits@?$HashMap@PEAUHSTRING__@@PEAU1@URegistryNameHashFunction@RegistryMapDetails@@URegistryNameEqualityPredicate@3@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U56789@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@6789@@Internal@Collections@Foundation@Windows@@V?$CElementTraits@PEAUHSTRING__@@@XWinRT@@@XWinRT@@AEAAJPEAVCNode@12@@Z; XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::FreeNode(XWinRT::XHashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::KeyTraits,XWinRT::CElementTraits<HSTRING__ *>>::CNode *)
0x180140a59  xor     esi, esi
0x180140a5b  jmp     short loc_180140A66
0x180140a5d  xor     ebx, ebx
0x180140a5f  mov     esi, 8000FFFFh
0x180140a64  xor     edi, edi
0x180140a66  mov     rax, [rbp+arg_18]
0x180140a6a  test    rax, rax
0x180140a6d  jz      short loc_180140A8C
0x180140a6f  cmp     dword ptr [rax], 1
0x180140a72  lea     rcx, [rax+8]; SRWLock
0x180140a76  jnz     short loc_180140A80
0x180140a78  add     dword ptr [rcx], 10000000h
0x180140a7e  jmp     short loc_180140A8C
0x180140a80  call    cs:__imp_ReleaseSRWLockExclusive
0x180140a87  nop     dword ptr [rax+rax+00h]
0x180140a8c  mov     rcx, rdi; string
0x180140a8f  call    cs:__imp_WindowsDeleteString
0x180140a96  nop     dword ptr [rax+rax+00h]
0x180140a9b  mov     rcx, rbx; string
0x180140a9e  call    cs:__imp_WindowsDeleteString
0x180140aa5  nop     dword ptr [rax+rax+00h]
0x180140aaa  test    esi, esi
0x180140aac  js      short loc_180140AD3
0x180140aae  mov     rax, [rbp+arg_8]
0x180140ab2  mov     r9d, 2
0x180140ab8  movzx   edx, byte ptr [r15+99h]
0x180140ac0  mov     r8, r15
0x180140ac3  movzx   ecx, byte ptr [rbp+arg_10]
0x180140ac7  mov     [rsp+30h+var_10], rax
0x180140acc  call    ?RaiseEvent@?$HashMapOptions@U_GUID@@PEAVComProxyStubRegistration@DEH@OSIntegration@@U?$DefaultLifetimeTraits@U_GUID@@@Internal@Collections@Foundation@Windows@@$0A@$0A@$0A@@Internal@Collections@Foundation@Windows@@SAJZZ; Windows::Foundation::Collections::Internal::HashMapOptions<_GUID,OSIntegration::DEH::ComProxyStubRegistration *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<_GUID>,0,0,0>::RaiseEvent(...)
0x180140ad1  mov     esi, eax
0x180140ad3  mov     eax, esi
0x180140ad5  add     rsp, 30h
0x180140ad9  pop     r15
0x180140adb  pop     r14
0x180140add  pop     r13
0x180140adf  pop     rdi
0x180140ae0  pop     rsi
0x180140ae1  pop     rbx
0x180140ae2  pop     rbp
0x180140ae3  retn
```
