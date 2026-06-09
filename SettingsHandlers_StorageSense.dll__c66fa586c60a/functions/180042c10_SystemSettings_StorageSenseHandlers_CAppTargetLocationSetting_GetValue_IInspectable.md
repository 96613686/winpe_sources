# SystemSettings::StorageSenseHandlers::CAppTargetLocationSetting::GetValue(IInspectable * *)

- ea: `0x180042c10`
- end: `0x180042d72`
- name: `?GetValue@CAppTargetLocationSetting@StorageSenseHandlers@SystemSettings@@UEAAJPEAPEAUIInspectable@@@Z`
- size: `354`
- prototype: `int(SystemSettings::StorageSenseHandlers::CAppTargetLocationSetting *__hidden this, struct IInspectable **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000c964`
- `0x18000e6cc`
- `0x18001f468`
- `0x18002bd60`
- `0x180036b34`
- `0x180042c10`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180042d38`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x180042d38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042ce3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042d44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042ce3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042d44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180042d23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180042d23`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppTargetLocationSetting::GetValue(
        SystemSettings::StorageSenseHandlers::CAppTargetLocationSetting *this,
        struct IInspectable **a2)
{
  __int64 v4; // rcx
  unsigned int v5; // ebx
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, HSTRING *); // rbx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+28h]
  HSTRING string; // [rsp+50h] [rbp+30h] BYREF
  struct IInspectable *v14; // [rsp+58h] [rbp+38h] BYREF
  __int64 v15; // [rsp+60h] [rbp+40h] BYREF

  *a2 = 0;
  if ( !*((_QWORD *)this + 98) )
    (*(void (__fastcall **)(SystemSettings::StorageSenseHandlers::CAppTargetLocationSetting *, _QWORD))(*(_QWORD *)this + 264LL))(
      this,
      0);
  v4 = *((_QWORD *)this + 98);
  if ( v4 )
  {
    v14 = 0;
    v15 = 0;
    string = 0;
    v6 = Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::GetAt(
           v4,
           0,
           &v14);
    v5 = v6;
    if ( v6 >= 0 )
    {
      v6 = Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(
             (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v14,
             (__int64)&v15);
      v5 = v6;
      if ( v6 >= 0 )
      {
        v8 = v15;
        v9 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v15 + 152LL);
        WindowsDeleteString(string);
        string = 0;
        v6 = v9(v8, &string);
        v5 = v6;
        if ( v6 >= 0 )
        {
          Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v14);
          *a2 = v14;
          WindowsGetStringRawBuffer(string, 0);
          _o_wcscpy_s((char *)this + 240, 260);
          v5 = 0;
          goto LABEL_13;
        }
        v7 = 1060;
      }
      else
      {
        v7 = 1059;
      }
    }
    else
    {
      v7 = 1058;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appsizeslist.cpp",
      (const char *)(unsigned int)v6,
      savedregs);
LABEL_13:
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v15);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v14);
    return v5;
  }
  v5 = -2147418113;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x41A,
    (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\appsizeslist.cpp",
    (const char *)0x8000FFFFLL,
    savedregs);
  return v5;
}

```

## disassembly

```asm
0x180042c10  push    rbp
0x180042c12  push    rbx
0x180042c13  push    rsi
0x180042c14  push    rdi
0x180042c15  push    r14; int
0x180042c17  mov     rbp, rsp
0x180042c1a  sub     rsp, 20h
0x180042c1e  mov     r14, rdx
0x180042c21  mov     rsi, rcx
0x180042c24  mov     qword ptr [rdx], 0
0x180042c2b  cmp     qword ptr [rcx+310h], 0
0x180042c33  jnz     short loc_180042C46
0x180042c35  mov     rax, [rcx]
0x180042c38  xor     edx, edx
0x180042c3a  mov     rax, [rax+108h]
0x180042c41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042c46  mov     rcx, [rsi+310h]
0x180042c4d  test    rcx, rcx
0x180042c50  jnz     short loc_180042C74
0x180042c52  mov     rcx, [rbp+28h]; this
0x180042c56  mov     ebx, 8000FFFFh
0x180042c5b  mov     r9d, ebx; char *
0x180042c5e  lea     r8, aOnecoreuapShel_29; "onecoreuap\\shell\\coresettinghandlers"...
0x180042c65  mov     edx, 41Ah; void *
0x180042c6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042c6f  jmp     loc_180042D65
0x180042c74  mov     [rbp+arg_8], 0
0x180042c7c  mov     [rbp+arg_10], 0
0x180042c84  mov     [rbp+string], 0
0x180042c8c  lea     r8, [rbp+arg_8]
0x180042c90  xor     edx, edx
0x180042c92  call    ?GetAt@?$Vector@PEAUIInspectable@@U?$DefaultEqualityPredicate@PEAUIInspectable@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUIInspectable@@@3456@U?$VectorOptions@PEAUIInspectable@@$00$00$0A@@3456@@Internal@Collections@Foundation@Windows@@UEAAJIPEAPEAUIInspectable@@@Z; Windows::Foundation::Collections::Internal::Vector<IInspectable *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<IInspectable *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<IInspectable *>,Windows::Foundation::Collections::Internal::VectorOptions<IInspectable *,1,1,0>>::GetAt(uint,IInspectable * *)
0x180042c97  mov     ebx, eax
0x180042c99  test    eax, eax
0x180042c9b  jns     short loc_180042CA4
0x180042c9d  mov     edx, 422h
0x180042ca2  jmp     short loc_180042CBC
0x180042ca4  lea     rdx, [rbp+arg_10]
0x180042ca8  lea     rcx, [rbp+arg_8]
0x180042cac  call    ??$As@UIPropertyValue@Foundation@Windows@@@?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIPropertyValue@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IInspectable>::As<Windows::Foundation::IPropertyValue>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValue>>)
0x180042cb1  mov     ebx, eax
0x180042cb3  test    eax, eax
0x180042cb5  jns     short loc_180042CD1
0x180042cb7  mov     edx, 423h; void *
0x180042cbc  mov     rcx, [rbp+28h]; this
0x180042cc0  mov     r9d, eax; char *
0x180042cc3  lea     r8, aOnecoreuapShel_29; "onecoreuap\\shell\\coresettinghandlers"...
0x180042cca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042ccf  jmp     short loc_180042D40
0x180042cd1  mov     rdi, [rbp+arg_10]
0x180042cd5  mov     rax, [rdi]
0x180042cd8  mov     rbx, [rax+98h]
0x180042cdf  mov     rcx, [rbp+string]; string
0x180042ce3  call    cs:__imp_WindowsDeleteString
0x180042ce9  mov     [rbp+string], 0
0x180042cf1  lea     rdx, [rbp+string]
0x180042cf5  mov     rcx, rdi
0x180042cf8  mov     rax, rbx
0x180042cfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042d00  mov     ebx, eax
0x180042d02  test    eax, eax
0x180042d04  jns     short loc_180042D0D
0x180042d06  mov     edx, 424h
0x180042d0b  jmp     short loc_180042CBC
0x180042d0d  lea     rcx, [rbp+arg_8]
0x180042d11  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180042d16  mov     rax, [rbp+arg_8]
0x180042d1a  mov     [r14], rax
0x180042d1d  xor     edx, edx; length
0x180042d1f  mov     rcx, [rbp+string]; string
0x180042d23  call    cs:__imp_WindowsGetStringRawBuffer
0x180042d29  lea     rcx, [rsi+0F0h]
0x180042d30  mov     r8, rax
0x180042d33  mov     edx, 104h
0x180042d38  call    cs:__imp__o_wcscpy_s
0x180042d3e  xor     ebx, ebx
0x180042d40  mov     rcx, [rbp+string]; string
0x180042d44  call    cs:__imp_WindowsDeleteString
0x180042d4a  mov     [rbp+string], 0
0x180042d52  lea     rcx, [rbp+arg_10]
0x180042d56  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180042d5b  nop
0x180042d5c  lea     rcx, [rbp+arg_8]
0x180042d60  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x180042d65  mov     eax, ebx
0x180042d67  add     rsp, 20h
0x180042d6b  pop     r14
0x180042d6d  pop     rdi
0x180042d6e  pop     rsi
0x180042d6f  pop     rbx
0x180042d70  pop     rbp
0x180042d71  retn
```
