# Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1>::Make(HSTRING__ * const &,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus const &,Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1> * *)

- ea: `0x1800186d4`
- end: `0x1800187aa`
- name: `?Make@?$SimpleKeyValuePair@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@U?$DefaultLifetimeTraits@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@89Foundation@6@$00@Internal@Collections@Foundation@Windows@@SAJAEBQEAUHSTRING__@@AEBW4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@5@PEAPEAV12345@@Z`
- size: `214`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180016ed0`
- `0x18001b790`

## callees

- `0x1800041ac`
- `0x1800111ac`
- `0x180013a84`
- `0x180018224`
- `0x1800186d4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180018750`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180018750`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001877a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001877a`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1>::Make(
        HSTRING *a1,
        int *a2,
        __int64 *a3)
{
  HSTRING v6; // rax
  __int64 v7; // rbx
  HRESULT v8; // edi
  HSTRING v9; // rcx
  int v10; // edx
  __int64 v12; // [rsp+50h] [rbp+18h] BYREF
  HSTRING newString; // [rsp+58h] [rbp+20h] BYREF

  *a3 = 0;
  v12 = 0;
  v6 = (HSTRING)operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
  newString = v6;
  if ( v6 )
  {
    v7 = Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1>::SimpleKeyValuePair<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1>((__int64)v6);
    v12 = v7;
    newString = 0;
  }
  else
  {
    v7 = 0;
  }
  Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>((void **)&newString);
  if ( v7 )
  {
    v8 = WindowsDuplicateString(*a1, &newString);
    if ( v8 >= 0 )
    {
      v10 = *a2;
      v8 = 0;
      v9 = *(HSTRING *)(v7 + 64);
      *(_QWORD *)(v7 + 64) = newString;
      *(_DWORD *)(v7 + 72) = v10;
    }
    else
    {
      v9 = 0;
    }
    newString = v9;
    WindowsDeleteString(v9);
    if ( v8 >= 0 )
    {
      v12 = 0;
      *a3 = v7;
    }
  }
  else
  {
    v8 = -2147024882;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1>>::InternalRelease(&v12);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800186d4  mov     [rsp+arg_0], rbx
0x1800186d9  push    rsi
0x1800186da  push    rdi
0x1800186db  push    r14
0x1800186dd  sub     rsp, 20h
0x1800186e1  mov     r14, rdx
0x1800186e4  mov     qword ptr [r8], 0
0x1800186eb  mov     rdi, rcx
0x1800186ee  mov     [rsp+38h+arg_10], 0
0x1800186f7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800186fe  mov     ecx, 50h ; 'P'; unsigned __int64
0x180018703  mov     rsi, r8
0x180018706  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001870b  mov     [rsp+38h+newString], rax
0x180018710  test    rax, rax
0x180018713  jz      short loc_180018730
0x180018715  mov     rcx, rax
0x180018718  call    ??0?$SimpleKeyValuePair@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@U?$DefaultLifetimeTraits@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@89Foundation@6@$00@Internal@Collections@Foundation@Windows@@QEAA@Upermission@01234@@Z; Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1>::SimpleKeyValuePair<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1>(Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1>::permission)
0x18001871d  mov     rbx, rax
0x180018720  mov     [rsp+38h+arg_10], rax
0x180018725  mov     [rsp+38h+newString], 0
0x18001872e  jmp     short loc_180018732
0x180018730  xor     ebx, ebx
0x180018732  lea     rcx, [rsp+38h+newString]
0x180018737  call    ??1?$MakeAllocator@V?$CTaskWrapper@V_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_@@@ComTaskPool@Internal@Windows@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>::~MakeAllocator<Windows::Internal::ComTaskPool::CTaskWrapper<_lambda_c2fd7731c5ae0d37e65ea73be67c0f1b_>>(void)
0x18001873c  test    rbx, rbx
0x18001873f  jnz     short loc_180018748
0x180018741  mov     edi, 8007000Eh
0x180018746  jmp     short loc_180018790
0x180018748  mov     rcx, [rdi]; string
0x18001874b  lea     rdx, [rsp+38h+newString]; newString
0x180018750  call    cs:__imp_WindowsDuplicateString
0x180018756  mov     edi, eax
0x180018758  test    eax, eax
0x18001875a  jns     short loc_180018760
0x18001875c  xor     ecx, ecx
0x18001875e  jmp     short loc_180018775
0x180018760  mov     edx, [r14]
0x180018763  xor     edi, edi
0x180018765  mov     rcx, [rbx+40h]; string
0x180018769  mov     rax, [rsp+38h+newString]
0x18001876e  mov     [rbx+40h], rax
0x180018772  mov     [rbx+48h], edx
0x180018775  mov     [rsp+38h+newString], rcx
0x18001877a  call    cs:__imp_WindowsDeleteString
0x180018780  test    edi, edi
0x180018782  js      short loc_180018790
0x180018784  mov     [rsp+38h+arg_10], 0
0x18001878d  mov     [rsi], rbx
0x180018790  lea     rcx, [rsp+38h+arg_10]
0x180018795  call    ?InternalRelease@?$ComPtr@V?$SimpleKeyValuePair@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@U?$DefaultLifetimeTraits@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@89Foundation@6@$00@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,1>>::InternalRelease(void)
0x18001879a  mov     rbx, [rsp+38h+arg_0]
0x18001879f  mov     eax, edi
0x1800187a1  add     rsp, 20h
0x1800187a5  pop     r14
0x1800187a7  pop     rdi
0x1800187a8  pop     rsi
0x1800187a9  retn
```
