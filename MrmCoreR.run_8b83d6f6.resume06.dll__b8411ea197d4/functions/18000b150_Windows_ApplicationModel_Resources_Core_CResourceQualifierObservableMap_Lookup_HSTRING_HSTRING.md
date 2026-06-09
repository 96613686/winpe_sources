# Windows::ApplicationModel::Resources::Core::CResourceQualifierObservableMap::Lookup(HSTRING__ *,HSTRING__ * *)

- ea: `0x18000b150`
- end: `0x18000b3da`
- name: `?Lookup@CResourceQualifierObservableMap@Core@Resources@ApplicationModel@Windows@@UEAAJPEAUHSTRING__@@PEAPEAU6@@Z`
- size: `650`
- prototype: `int(Windows::ApplicationModel::Resources::Core::CResourceQualifierObservableMap *__hidden this, HSTRING, HSTRING *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x18000892c`
- `0x18000b150`
- `0x18000c8a0`
- `0x18002c8d0`
- `0x180035518`
- `0x180083ad4`
- `0x1800862f0`
- `0x180086f7c`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b204`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000b204`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b374`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000b374`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000b263`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18000b263`

## string_xrefs

- `0x18000b2f8`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecontext.cpp`
- `0x18000b35a`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecontext.cpp`
- `0x18000b3ba`: `onecoreuap\base\mrt\runtime\com\winrt\core\winrtresourcecontext.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::ApplicationModel::Resources::Core::CResourceQualifierObservableMap::Lookup(
        Windows::ApplicationModel::Resources::Core::CResourceQualifierObservableMap *this,
        HSTRING a2,
        HSTRING *a3)
{
  _QWORD *v6; // rdi
  __int64 v7; // rcx
  unsigned int v8; // ebx
  Microsoft::Resources::Runtime::CContext *v9; // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  int AttributeValue; // eax
  HSTRING v12; // rbx
  unsigned __int64 v13; // rdx
  HRESULT v14; // eax
  int v15; // edi
  _QWORD *v16; // rcx
  _QWORD *v18; // rcx
  _QWORD *v19; // rcx
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+20h] [rbp-E0h]
  _QWORD *v22; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING v24; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR sourceString[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  *a3 = 0;
  memset_0(sourceString, 0, 0x208u);
  v22 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v22);
  v6 = 0;
  v22 = 0;
  v7 = *((_QWORD *)this + 9);
  if ( v7 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, GUID *, _QWORD **))(*(_QWORD *)v7 + 24LL))(
           v7,
           &GUID_2fa22f4b_707e_4b27_ad0d_d0d8cd468fd2,
           &v22);
    v6 = v22;
  }
  else
  {
    v8 = 0;
  }
  if ( (v8 & 0x80000000) != 0 )
  {
    if ( v8 != -2147024891 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x432,
        (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecontext.cpp",
        (const char *)v8,
        v20);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(&v22);
      return v8;
    }
  }
  else if ( v6 )
  {
    v9 = (Microsoft::Resources::Runtime::CContext *)v6[9];
    if ( !v9 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
    AttributeValue = Microsoft::Resources::Runtime::CContext::GetAttributeValue(
                       v9,
                       StringRawBuffer,
                       0x104u,
                       sourceString,
                       0);
    v8 = AttributeValue;
    if ( AttributeValue >= 0 )
    {
      v12 = 0;
      v24 = 0;
      string = 0;
      v13 = -1;
      do
        ++v13;
      while ( sourceString[v13] );
      if ( v13 > 0xFFFFFFFF )
      {
        v15 = -2147024362;
      }
      else
      {
        v14 = WindowsCreateString(sourceString, v13, &string);
        v15 = v14;
        if ( v14 >= 0 )
        {
          v15 = Windows::Internal::String::FreeAndAssignOnSuccess(v14, string, &v24);
          v12 = v24;
        }
      }
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x437,
          (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecontext.cpp",
          (const char *)(unsigned int)v15,
          v21);
        if ( v12 )
          WindowsDeleteString(v12);
        v19 = v22;
        if ( v22 )
        {
          v22 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v19 + 16LL))(v19);
        }
        return (unsigned int)v15;
      }
      else
      {
        *a3 = v12;
        v16 = v22;
        if ( v22 )
        {
          v22 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v16 + 16LL))(v16);
        }
        return 0;
      }
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x434,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\winrt\\core\\winrtresourcecontext.cpp",
      (const char *)(unsigned int)AttributeValue,
      v21);
    v18 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v18 + 16LL))(v18);
    }
    return v8;
  }
  if ( v6 )
  {
    v22 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v6 + 16LL))(v6);
  }
  return 2147942405LL;
}

```

## disassembly

```asm
0x18000b150  mov     [rsp-8+arg_8], rbx
0x18000b155  push    rbp
0x18000b156  push    rsi
0x18000b157  push    rdi
0x18000b158  push    r14
0x18000b15a  push    r15
0x18000b15c  lea     rbp, [rsp-170h]
0x18000b164  sub     rsp, 270h
0x18000b16b  mov     rax, cs:__security_cookie
0x18000b172  xor     rax, rsp
0x18000b175  mov     [rbp+190h+var_30], rax
0x18000b17c  mov     rsi, r8
0x18000b17f  mov     r14, rdx
0x18000b182  mov     rbx, rcx
0x18000b185  xor     r15d, r15d
0x18000b188  mov     [r8], r15
0x18000b18b  xor     edx, edx; Val
0x18000b18d  mov     r8d, 208h; Size
0x18000b193  lea     rcx, [rsp+290h+sourceString]; void *
0x18000b198  call    memset_0
0x18000b19d  mov     [rsp+290h+var_260], r15
0x18000b1a2  lea     rcx, [rsp+290h+var_260]
0x18000b1a7  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x18000b1ac  nop
0x18000b1ad  mov     edi, r15d
0x18000b1b0  mov     [rsp+290h+var_260], r15
0x18000b1b5  mov     rcx, [rbx+48h]
0x18000b1b9  test    rcx, rcx
0x18000b1bc  jz      loc_18000B39E
0x18000b1c2  mov     rax, [rcx]
0x18000b1c5  lea     r8, [rsp+290h+var_260]
0x18000b1ca  lea     rdx, _GUID_2fa22f4b_707e_4b27_ad0d_d0d8cd468fd2
0x18000b1d1  mov     rax, [rax+18h]
0x18000b1d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1da  mov     ebx, eax
0x18000b1dc  mov     rdi, [rsp+290h+var_260]
0x18000b1e1  test    ebx, ebx
0x18000b1e3  js      loc_18000B2DD
0x18000b1e9  test    rdi, rdi
0x18000b1ec  jz      loc_18000B32A
0x18000b1f2  mov     rbx, [rdi+48h]
0x18000b1f6  test    rbx, rbx
0x18000b1f9  jz      loc_18000B3A6
0x18000b1ff  xor     edx, edx; length
0x18000b201  mov     rcx, r14; string
0x18000b204  call    cs:__imp_WindowsGetStringRawBuffer
0x18000b20a  mov     qword ptr [rsp+290h+var_270], r15; int
0x18000b20f  lea     r9, [rsp+290h+sourceString]; unsigned __int16 *
0x18000b214  mov     r8d, 104h; unsigned __int64
0x18000b21a  mov     rdx, rax; unsigned __int16 *
0x18000b21d  mov     rcx, rbx; this
0x18000b220  call    ?GetAttributeValue@CContext@Runtime@Resources@Microsoft@@QEBAJPEBG_KPEAGPEA_K@Z; Microsoft::Resources::Runtime::CContext::GetAttributeValue(ushort const *,unsigned __int64,ushort *,unsigned __int64 *)
0x18000b225  mov     ebx, eax
0x18000b227  test    eax, eax
0x18000b229  js      loc_18000B2EE
0x18000b22f  mov     rbx, r15
0x18000b232  mov     [rsp+290h+var_250], rbx
0x18000b237  mov     [rsp+290h+string], r15
0x18000b23c  lea     rax, [rsp+290h+sourceString]
0x18000b241  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000b245  inc     rdx; length
0x18000b248  cmp     [rax+rdx*2], r15w
0x18000b24d  jnz     short loc_18000B245
0x18000b24f  mov     eax, 0FFFFFFFFh
0x18000b254  cmp     rdx, rax
0x18000b257  ja      short loc_18000B2D6
0x18000b259  lea     r8, [rsp+290h+string]; string
0x18000b25e  lea     rcx, [rsp+290h+sourceString]; sourceString
0x18000b263  call    cs:__imp_WindowsCreateString
0x18000b269  mov     edi, eax
0x18000b26b  test    eax, eax
0x18000b26d  js      short loc_18000B287
0x18000b26f  lea     r8, [rsp+290h+var_250]; HSTRING *
0x18000b274  mov     rdx, [rsp+290h+string]; HSTRING
0x18000b279  mov     ecx, eax; int
0x18000b27b  call    ?FreeAndAssignOnSuccess@String@Internal@Windows@@CAJJPEAUHSTRING__@@PEAPEAU4@@Z; Windows::Internal::String::FreeAndAssignOnSuccess(long,HSTRING__ *,HSTRING__ * *)
0x18000b280  mov     edi, eax
0x18000b282  mov     rbx, [rsp+290h+var_250]
0x18000b287  test    edi, edi
0x18000b289  js      loc_18000B350
0x18000b28f  mov     [rsi], rbx
0x18000b292  mov     rcx, [rsp+290h+var_260]
0x18000b297  test    rcx, rcx
0x18000b29a  jz      short loc_18000B2AE
0x18000b29c  mov     [rsp+290h+var_260], r15
0x18000b2a1  mov     rax, [rcx]
0x18000b2a4  mov     rax, [rax+10h]
0x18000b2a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2ad  nop
0x18000b2ae  xor     eax, eax
0x18000b2b0  mov     rcx, [rbp+190h+var_30]
0x18000b2b7  xor     rcx, rsp; StackCookie
0x18000b2ba  call    __security_check_cookie
0x18000b2bf  mov     rbx, [rsp+290h+arg_8]
0x18000b2c7  add     rsp, 270h
0x18000b2ce  pop     r15
0x18000b2d0  pop     r14
0x18000b2d2  pop     rdi
0x18000b2d3  pop     rsi
0x18000b2d4  pop     rbp
0x18000b2d5  retn
0x18000b2d6  mov     edi, 80070216h
0x18000b2db  jmp     short loc_18000B287
0x18000b2dd  mov     esi, 80070005h
0x18000b2e2  cmp     ebx, esi
0x18000b2e4  jnz     loc_18000B3B0
0x18000b2ea  mov     esi, ebx
0x18000b2ec  jmp     short loc_18000B32F
0x18000b2ee  mov     rcx, [rbp+198h]; this
0x18000b2f5  mov     r9d, ebx; char *
0x18000b2f8  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x18000b2ff  mov     edx, 434h; void *
0x18000b304  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b309  nop
0x18000b30a  mov     rcx, [rsp+290h+var_260]
0x18000b30f  test    rcx, rcx
0x18000b312  jz      short loc_18000B326
0x18000b314  mov     [rsp+290h+var_260], r15
0x18000b319  mov     rax, [rcx]
0x18000b31c  mov     rax, [rax+10h]
0x18000b320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b325  nop
0x18000b326  mov     eax, ebx
0x18000b328  jmp     short loc_18000B2B0
0x18000b32a  mov     esi, 80070005h
0x18000b32f  test    rdi, rdi
0x18000b332  jz      short loc_18000B349
0x18000b334  mov     [rsp+290h+var_260], r15
0x18000b339  mov     rdx, [rdi]
0x18000b33c  mov     rcx, rdi
0x18000b33f  mov     rax, [rdx+10h]
0x18000b343  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b348  nop
0x18000b349  mov     eax, esi
0x18000b34b  jmp     loc_18000B2B0
0x18000b350  mov     rcx, [rbp+198h]; this
0x18000b357  mov     r9d, edi; char *
0x18000b35a  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x18000b361  mov     edx, 437h; void *
0x18000b366  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b36b  nop
0x18000b36c  test    rbx, rbx
0x18000b36f  jz      short loc_18000B37B
0x18000b371  mov     rcx, rbx; string
0x18000b374  call    cs:__imp_WindowsDeleteString
0x18000b37a  nop
0x18000b37b  mov     rcx, [rsp+290h+var_260]
0x18000b380  test    rcx, rcx
0x18000b383  jz      short loc_18000B397
0x18000b385  mov     [rsp+290h+var_260], r15
0x18000b38a  mov     rax, [rcx]
0x18000b38d  mov     rax, [rax+10h]
0x18000b391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b396  nop
0x18000b397  mov     eax, edi
0x18000b399  jmp     loc_18000B2B0
0x18000b39e  mov     ebx, r15d
0x18000b3a1  jmp     loc_18000B1E1
0x18000b3a6  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18000b3ab  jmp     loc_18000B1FF
0x18000b3b0  mov     rcx, [rbp+198h]; this
0x18000b3b7  mov     r9d, ebx; char *
0x18000b3ba  lea     r8, aOnecoreuapBase_34; "onecoreuap\\base\\mrt\\runtime\\com\\wi"...
0x18000b3c1  mov     edx, 432h; void *
0x18000b3c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b3cb  lea     rcx, [rsp+290h+var_260]
0x18000b3d0  call    ?InternalRelease@?$ComPtr@U?$IIterator@PEAVResourceQualifier@Core@Resources@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterator<Windows::ApplicationModel::Resources::Core::ResourceQualifier *>>::InternalRelease(void)
0x18000b3d5  jmp     loc_18000B326
```
