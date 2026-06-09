# CXAMLHostWindow::_FindXamlElement(ushort const *,IInspectable * *)

- ea: `0x18002e89c`
- end: `0x18002ea17`
- name: `?_FindXamlElement@CXAMLHostWindow@@AEAAJPEBGPEAPEAUIInspectable@@@Z`
- size: `379`
- prototype: `int(CXAMLHostWindow *__hidden this, const unsigned __int16 *, struct IInspectable **)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002ec1c`

## callees

- `0x180007b3c`
- `0x180015084`
- `0x1800204e0`
- `0x18002b230`
- `0x18002e89c`
- `0x180030ba0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e944`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002e944`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002e957`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002e957`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002e930`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002e930`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CXAMLHostWindow::_FindXamlElement(
        CXAMLHostWindow *this,
        const unsigned __int16 *a2,
        struct IInspectable **a3)
{
  const unsigned __int16 *v4; // rdi
  unsigned int v5; // ebx
  struct IInspectable *v6; // rsi
  const WCHAR *v7; // r12
  const unsigned __int16 *v8; // rax
  unsigned __int16 v9; // cx
  const unsigned __int16 *v10; // r14
  bool v11; // r15
  HSTRING v12; // rbx
  const unsigned __int16 *StringRawBuffer; // rbx
  int ElementByName; // eax
  const unsigned __int16 *v15; // rax
  struct IInspectable *v17; // [rsp+60h] [rbp+40h] BYREF
  HSTRING string; // [rsp+68h] [rbp+48h] BYREF
  HSTRING v19; // [rsp+70h] [rbp+50h] BYREF

  v4 = a2;
  v5 = 0;
  *a3 = 0;
  v6 = (struct IInspectable *)*((_QWORD *)this + 31);
  v17 = v6;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v17, a2);
  v7 = v4;
  v8 = v4;
  while ( v4 )
  {
    v9 = *v4;
    if ( !*v4 )
      break;
    if ( v9 == 46 )
      v8 = v4;
    v10 = v8;
    v11 = v9 == 46;
    if ( *++v4 )
    {
      if ( v9 != 46 )
        goto LABEL_13;
    }
    else
    {
      v10 = v4;
      v11 = 1;
    }
    v19 = 0;
    string = 0;
    if ( WindowsCreateString(v7, v10 - v7, &string) >= 0 )
    {
      v12 = string;
      v19 = string;
      WindowsDeleteString(0);
      string = 0;
      StringRawBuffer = WindowsGetStringRawBuffer(v12, 0);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&string);
      ElementByName = FindElementByName(
                        v6,
                        StringRawBuffer,
                        &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90,
                        (void **)&string);
      v5 = 0;
      if ( ElementByName < 0 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v17);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&string);
        Windows::Internal::String::~String((Windows::Internal::String *)&v19);
        v6 = v17;
        break;
      }
      Microsoft::WRL::ComPtr<IInspectable>::operator=(&v17, &string);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&string);
      v6 = v17;
    }
    Windows::Internal::String::~String((Windows::Internal::String *)&v19);
LABEL_13:
    v15 = v4;
    if ( !v11 )
      v15 = v7;
    v7 = v15;
    v8 = v4;
    if ( !v11 )
      v8 = v10;
  }
  if ( v6 )
  {
    v17 = 0;
    *a3 = v6;
  }
  else
  {
    v5 = -2147024809;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(&v17);
  return v5;
}

```

## disassembly

```asm
0x18002e89c  mov     [rsp-38h+arg_18], rbx
0x18002e8a1  push    rbp
0x18002e8a2  push    rsi
0x18002e8a3  push    rdi
0x18002e8a4  push    r12
0x18002e8a6  push    r13
0x18002e8a8  push    r14
0x18002e8aa  push    r15
0x18002e8ac  mov     rbp, rsp
0x18002e8af  sub     rsp, 20h
0x18002e8b3  mov     r13, r8
0x18002e8b6  mov     rdi, rdx
0x18002e8b9  xor     ebx, ebx
0x18002e8bb  mov     [r8], rbx
0x18002e8be  mov     rsi, [rcx+0F8h]
0x18002e8c5  mov     [rbp+arg_0], rsi
0x18002e8c9  lea     rcx, [rbp+arg_0]
0x18002e8cd  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18002e8d2  nop
0x18002e8d3  mov     r12, rdi
0x18002e8d6  mov     rax, rdi
0x18002e8d9  test    rdi, rdi
0x18002e8dc  jz      loc_18002E9DF
0x18002e8e2  movzx   ecx, word ptr [rdi]
0x18002e8e5  test    cx, cx
0x18002e8e8  jz      loc_18002E9DF
0x18002e8ee  cmp     cx, 2Eh ; '.'
0x18002e8f2  cmovz   rax, rdi
0x18002e8f6  mov     r14, rax
0x18002e8f9  setz    r15b
0x18002e8fd  add     rdi, 2
0x18002e901  cmp     [rdi], bx
0x18002e904  jnz     short loc_18002E90E
0x18002e906  mov     r14, rdi
0x18002e909  mov     r15b, 1
0x18002e90c  jmp     short loc_18002E918
0x18002e90e  cmp     cx, 2Eh ; '.'
0x18002e912  jnz     loc_18002E9A9
0x18002e918  mov     [rbp+arg_10], rbx
0x18002e91c  mov     [rbp+string], rbx
0x18002e920  mov     rdx, r14
0x18002e923  sub     rdx, r12
0x18002e926  sar     rdx, 1; length
0x18002e929  lea     r8, [rbp+string]; string
0x18002e92d  mov     rcx, r12; sourceString
0x18002e930  call    cs:__imp_WindowsCreateString
0x18002e936  test    eax, eax
0x18002e938  js      short loc_18002E9A0
0x18002e93a  mov     rbx, [rbp+string]
0x18002e93e  mov     [rbp+arg_10], rbx
0x18002e942  xor     ecx, ecx; string
0x18002e944  call    cs:__imp_WindowsDeleteString
0x18002e94a  mov     [rbp+string], 0
0x18002e952  xor     edx, edx; length
0x18002e954  mov     rcx, rbx; string
0x18002e957  call    cs:__imp_WindowsGetStringRawBuffer
0x18002e95d  mov     rbx, rax
0x18002e960  lea     rcx, [rbp+string]
0x18002e964  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002e969  lea     r9, [rbp+string]; void **
0x18002e96d  lea     r8, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; struct _GUID *
0x18002e974  mov     rdx, rbx; unsigned __int16 *
0x18002e977  mov     rcx, rsi; struct IInspectable *
0x18002e97a  call    ?FindElementByName@@YAJPEAUIInspectable@@PEBGAEBU_GUID@@PEAPEAX@Z; FindElementByName(IInspectable *,ushort const *,_GUID const &,void * *)
0x18002e97f  xor     ebx, ebx
0x18002e981  lea     rcx, [rbp+arg_0]
0x18002e985  test    eax, eax
0x18002e987  js      short loc_18002E9C2
0x18002e989  lea     rdx, [rbp+string]
0x18002e98d  call    ??4?$ComPtr@UIInspectable@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<IInspectable>::operator=(Microsoft::WRL::ComPtr<IInspectable> const &)
0x18002e992  nop
0x18002e993  lea     rcx, [rbp+string]
0x18002e997  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002e99c  mov     rsi, [rbp+arg_0]
0x18002e9a0  lea     rcx, [rbp+arg_10]; this
0x18002e9a4  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18002e9a9  mov     rax, rdi
0x18002e9ac  test    r15b, r15b
0x18002e9af  cmovz   rax, r12
0x18002e9b3  mov     r12, rax
0x18002e9b6  mov     rax, rdi
0x18002e9b9  cmovz   rax, r14
0x18002e9bd  jmp     loc_18002E8D9
0x18002e9c2  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002e9c7  nop
0x18002e9c8  lea     rcx, [rbp+string]
0x18002e9cc  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002e9d1  nop
0x18002e9d2  lea     rcx, [rbp+arg_10]; this
0x18002e9d6  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18002e9db  mov     rsi, [rbp+arg_0]
0x18002e9df  test    rsi, rsi
0x18002e9e2  jz      short loc_18002E9F2
0x18002e9e4  mov     [rbp+arg_0], 0
0x18002e9ec  mov     [r13+0], rsi
0x18002e9f0  jmp     short loc_18002E9F7
0x18002e9f2  mov     ebx, 80070057h
0x18002e9f7  lea     rcx, [rbp+arg_0]
0x18002e9fb  call    ?InternalRelease@?$ComPtr@U?$VectorChangedEventHandler@PEAVSearchSuggestion@Core@Search@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::VectorChangedEventHandler<Windows::ApplicationModel::Search::Core::SearchSuggestion *>>::InternalRelease(void)
0x18002ea00  mov     eax, ebx
0x18002ea02  mov     rbx, [rsp+20h+arg_18]
0x18002ea07  add     rsp, 20h
0x18002ea0b  pop     r15
0x18002ea0d  pop     r14
0x18002ea0f  pop     r13
0x18002ea11  pop     r12
0x18002ea13  pop     rdi
0x18002ea14  pop     rsi
0x18002ea15  pop     rbp
0x18002ea16  retn
```
