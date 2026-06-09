# Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>::Make(HSTRING__ * const &,HSTRING__ * const &,Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0> * *)

- ea: `0x1800628f8`
- end: `0x1800629ce`
- name: `?Make@?$SimpleKeyValuePair@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U23456@$0A@@Internal@Collections@Foundation@Windows@@SAJAEBQEAUHSTRING__@@0PEAPEAV12345@@Z`
- size: `214`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180061810`
- `0x180063ee0`

## callees

- `0x18001b828`
- `0x18001f6f4`
- `0x18006007c`
- `0x1800628f8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180062991`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006299b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180062991`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006299b`

## pseudocode

```c
__int64 __fastcall Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>::Make(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v4; // rdi
  unsigned int v5; // ebx
  HSTRING v6; // rcx
  HSTRING v7; // rcx
  HSTRING newString; // [rsp+20h] [rbp-10h] BYREF
  __int64 v10; // [rsp+28h] [rbp-8h] BYREF
  HSTRING string; // [rsp+68h] [rbp+38h] BYREF

  *a3 = 0;
  Microsoft::WRL::Details::Make<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>,Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>::permission>(&v10);
  v4 = v10;
  if ( v10 )
  {
    XWinRT::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>(&newString);
    XWinRT::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>(&string);
    v5 = 0;
    v6 = *(HSTRING *)(v4 + 32);
    *(_QWORD *)(v4 + 32) = newString;
    newString = v6;
    v7 = *(HSTRING *)(v4 + 40);
    *(_QWORD *)(v4 + 40) = string;
    string = v7;
    WindowsDeleteString(v7);
    WindowsDeleteString(newString);
    v10 = 0;
    *a3 = v4;
  }
  else
  {
    v5 = -2147024882;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>::InternalRelease(&v10);
  return v5;
}

```

## disassembly

```asm
0x1800628f8  mov     [rsp-18h+arg_0], rbx
0x1800628fd  mov     [rsp-18h+arg_8], rsi
0x180062902  push    rbp
0x180062903  push    rdi
0x180062904  push    r14
0x180062906  mov     rbp, rsp
0x180062909  sub     rsp, 30h
0x18006290d  mov     rbx, rcx
0x180062910  mov     qword ptr [r8], 0
0x180062917  lea     rcx, [rbp+var_8]
0x18006291b  mov     rsi, r8
0x18006291e  mov     r14, rdx
0x180062921  call    ??$Make@V?$SimpleKeyValuePair@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U23456@$0A@@Internal@Collections@Foundation@Windows@@Upermission@12345@@Details@WRL@Microsoft@@YA?AV?$ComPtr@V?$SimpleKeyValuePair@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U23456@$0A@@Internal@Collections@Foundation@Windows@@@12@$$QEAUpermission@?$SimpleKeyValuePair@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U23456@$0A@@Internal@Collections@Foundation@Windows@@@Z; Microsoft::WRL::Details::Make<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>,Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>::permission>(Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>::permission &&)
0x180062926  mov     rdi, [rbp+var_8]
0x18006292a  test    rdi, rdi
0x18006292d  jnz     short loc_180062936
0x18006292f  mov     ebx, 8007000Eh
0x180062934  jmp     short loc_1800629B0
0x180062936  lea     r8, [rbp+arg_10]
0x18006293a  mov     [rbp+arg_10], 0
0x180062941  mov     rdx, rbx
0x180062944  lea     rcx, [rbp+newString]; newString
0x180062948  call    ??$?0PEAUHSTRING__@@@?$AutoValue@PEAUHSTRING__@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@XWinRT@@QEAA@AEBQEAUHSTRING__@@PEAJ@Z; XWinRT::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>(HSTRING__ * const &,long *)
0x18006294d  mov     ebx, [rbp+arg_10]
0x180062950  test    ebx, ebx
0x180062952  js      short loc_180062997
0x180062954  lea     r8, [rbp+arg_10]
0x180062958  mov     rdx, r14
0x18006295b  lea     rcx, [rbp+string]; newString
0x18006295f  call    ??$?0PEAUHSTRING__@@@?$AutoValue@PEAUHSTRING__@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@@XWinRT@@QEAA@AEBQEAUHSTRING__@@PEAJ@Z; XWinRT::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>::AutoValue<HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>(HSTRING__ * const &,long *)
0x180062964  mov     ebx, [rbp+arg_10]
0x180062967  test    ebx, ebx
0x180062969  js      short loc_18006298D
0x18006296b  mov     rcx, [rdi+20h]
0x18006296f  mov     rax, [rbp+newString]
0x180062973  mov     [rdi+20h], rax
0x180062977  mov     rax, [rbp+string]
0x18006297b  mov     [rbp+newString], rcx
0x18006297f  mov     rcx, [rdi+28h]
0x180062983  mov     [rdi+28h], rax
0x180062987  mov     [rbp+string], rcx
0x18006298b  jmp     short loc_180062991
0x18006298d  mov     rcx, [rbp+string]; string
0x180062991  call    cs:__imp_WindowsDeleteString
0x180062997  mov     rcx, [rbp+newString]; string
0x18006299b  call    cs:__imp_WindowsDeleteString
0x1800629a1  test    ebx, ebx
0x1800629a3  js      short loc_1800629B0
0x1800629a5  mov     [rbp+var_8], 0
0x1800629ad  mov     [rsi], rdi
0x1800629b0  lea     rcx, [rbp+var_8]
0x1800629b4  call    ?InternalRelease@?$ComPtr@V?$SimpleKeyValuePair@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U23456@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::SimpleKeyValuePair<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0>>::InternalRelease(void)
0x1800629b9  mov     rsi, [rsp+30h+arg_8]
0x1800629be  mov     eax, ebx
0x1800629c0  mov     rbx, [rsp+30h+arg_0]
0x1800629c5  add     rsp, 30h
0x1800629c9  pop     r14
0x1800629cb  pop     rdi
0x1800629cc  pop     rbp
0x1800629cd  retn
```
