# AIFabricHelpers::SessionWrapper<winrt::Microsoft::Windows::SemanticSearch::Tokenizer,winrt::Microsoft::Windows::SemanticSearch::implementation::Tokenizer,winrt::Microsoft::Windows::SemanticSearchInternal::ITokenizerSession2,0>::SetSessionHostProcessId(void)

- ea: `0x180018fe0`
- end: `0x1800190da`
- name: `?SetSessionHostProcessId@?$SessionWrapper@UTokenizer@SemanticSearch@Windows@Microsoft@winrt@@U1implementation@2345@UITokenizerSession2@SemanticSearchInternal@345@$0A@@AIFabricHelpers@@QEAAXXZ`
- size: `250`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `8`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018760`
- `0x180018900`
- `0x18001ce90`
- `0x18001d020`
- `0x180033560`
- `0x180036220`
- `0x1800403f0`
- `0x1800408b0`

## callees

- `0x180002bb0`
- `0x180009580`
- `0x180018fe0`
- `0x18004c070`
- `0x18005e260`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180019099`
- `KERNEL32!GetCurrentProcessId` at `0x180019099`

## string_xrefs

- `0x180019064`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Windows.PrivateCommon.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
DWORD __fastcall AIFabricHelpers::SessionWrapper<winrt::Microsoft::Windows::SemanticSearch::Tokenizer,winrt::Microsoft::Windows::SemanticSearch::implementation::Tokenizer,winrt::Microsoft::Windows::SemanticSearchInternal::ITokenizerSession2,0>::SetSessionHostProcessId(
        __int64 a1)
{
  __int64 (__fastcall ***v2)(_QWORD, __int64 *, __int64 *); // rcx
  __int64 v3; // rcx
  int v4; // eax
  int v5; // eax
  DWORD result; // eax
  _QWORD v7[2]; // [rsp+20h] [rbp-38h] BYREF
  int v8; // [rsp+30h] [rbp-28h] BYREF
  const char *v9; // [rsp+38h] [rbp-20h]
  __int64 v10; // [rsp+40h] [rbp-18h] BYREF

  if ( *(_BYTE *)a1 )
  {
    v2 = *(__int64 (__fastcall ****)(_QWORD, __int64 *, __int64 *))(a1 + 24);
    if ( v2 )
    {
      v10 = 0;
      LODWORD(v7[0]) = 2121;
      v7[1] = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\base.h";
      v4 = (**v2)(v2, winrt::impl::guid_v<winrt::Microsoft::Windows::PrivateCommon::IGetSessionHostProcessId>, &v10);
      if ( v4 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v4, v7);
      }
      v3 = v10;
      v7[0] = v10;
    }
    else
    {
      v7[0] = 0;
      v3 = 0;
    }
    LODWORD(v10) = 0;
    v8 = 20;
    v9 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\M"
         "icrosoft.Windows.PrivateCommon.h";
    v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v3 + 48LL))(v3, &v10);
    if ( v5 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v5, &v8);
    }
    *(_DWORD *)(a1 + 4) = v10;
    return winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v7);
  }
  else
  {
    result = GetCurrentProcessId();
    *(_DWORD *)(a1 + 4) = result;
  }
  return result;
}

```

## disassembly

```asm
0x180018fe0  mov     [rsp+arg_8], rbx
0x180018fe5  push    rdi
0x180018fe6  sub     rsp, 50h
0x180018fea  mov     rax, cs:__security_cookie
0x180018ff1  xor     rax, rsp
0x180018ff4  mov     [rsp+58h+var_10], rax
0x180018ff9  mov     rbx, rcx
0x180018ffc  xor     edi, edi
0x180018ffe  cmp     [rcx], dil
0x180019001  jz      loc_180019099
0x180019007  mov     rcx, [rcx+18h]
0x18001900b  test    rcx, rcx
0x18001900e  jnz     short loc_180019019
0x180019010  mov     [rsp+58h+var_38], rdi
0x180019015  mov     ecx, edi
0x180019017  jmp     short loc_180019058
0x180019019  mov     [rsp+58h+var_18], rdi
0x18001901e  mov     dword ptr [rsp+58h+var_38], 849h
0x180019026  lea     rax, aCW1SProductApi_4; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18001902d  mov     [rsp+58h+var_30], rax
0x180019032  mov     rax, [rcx]
0x180019035  lea     r8, [rsp+58h+var_18]
0x18001903a  lea     rdx, ??$guid_v@UIGetSessionHostProcessId@PrivateCommon@Windows@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Windows::PrivateCommon::IGetSessionHostProcessId>
0x180019041  mov     rax, [rax]
0x180019044  call    cs:__guard_dispatch_icall_fptr
0x18001904a  test    eax, eax
0x18001904c  js      short loc_1800190CA
0x18001904e  mov     rcx, [rsp+58h+var_18]
0x180019053  mov     [rsp+58h+var_38], rcx
0x180019058  mov     dword ptr [rsp+58h+var_18], edi
0x18001905c  mov     [rsp+58h+var_28], 14h
0x180019064  lea     rax, aCW1SProductApi_14; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18001906b  mov     [rsp+58h+var_20], rax
0x180019070  mov     rax, [rcx]
0x180019073  lea     rdx, [rsp+58h+var_18]
0x180019078  mov     rax, [rax+30h]
0x18001907c  call    cs:__guard_dispatch_icall_fptr
0x180019082  test    eax, eax
0x180019084  js      short loc_1800190BA
0x180019086  mov     eax, dword ptr [rsp+58h+var_18]
0x18001908a  mov     [rbx+4], eax
0x18001908d  lea     rcx, [rsp+58h+var_38]
0x180019092  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180019097  jmp     short loc_1800190A2
0x180019099  call    cs:__imp_GetCurrentProcessId
0x18001909f  mov     [rbx+4], eax
0x1800190a2  mov     rcx, [rsp+58h+var_10]
0x1800190a7  xor     rcx, rsp; StackCookie
0x1800190aa  call    __security_check_cookie
0x1800190af  mov     rbx, [rsp+58h+arg_8]
0x1800190b4  add     rsp, 50h
0x1800190b8  pop     rdi
0x1800190b9  retn
0x1800190ba  lfence
0x1800190bd  lea     rdx, [rsp+58h+var_28]
0x1800190c2  mov     ecx, eax
0x1800190c4  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800190ca  lfence
0x1800190cd  lea     rdx, [rsp+58h+var_38]
0x1800190d2  mov     ecx, eax
0x1800190d4  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
