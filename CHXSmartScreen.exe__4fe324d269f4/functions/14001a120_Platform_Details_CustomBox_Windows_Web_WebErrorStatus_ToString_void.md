# Platform::Details::CustomBox<Windows::Web::WebErrorStatus>::ToString(void)

- ea: `0x14001a120`
- end: `0x14001a298`
- name: `?ToString@?$CustomBox@W4WebErrorStatus@Web@Windows@@@Details@Platform@@UE$AAAPE$AAVString@3@XZ`
- size: `376`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x14001a2a0`
- `0x14001fac0`

## callees

- `0x1400039b6`
- `0x1400039c2`
- `0x1400086b0`
- `0x14001a120`
- `0x14001d710`
- `0x140031960`
- `0x140035010`

## import_xrefs

- `wincorlib!?get@FullName@Type@Platform@@QE$AAAPE$AAVString@3@XZ` at `0x14001a1c7`
- `wincorlib!?get@FullName@Type@Platform@@QE$AAAPE$AAVString@3@XZ` at `0x14001a1c7`
- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x14001a1b7`
- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x14001a1b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
HSTRING __fastcall Platform::Details::CustomBox<enum Windows::Web::WebErrorStatus>::ToString(__int64 a1)
{
  HSTRING v1; // rax
  HSTRING v2; // rbx
  HRESULT v3; // eax
  HSTRING v4; // rdi
  HRESULT v5; // eax
  HSTRING v6; // rbx
  HSTRING type_id; // rsi
  HSTRING v8; // rax
  HSTRING v9; // r14
  HRESULT v10; // eax
  HRESULT v11; // eax
  HSTRING v12; // rdi
  HSTRING newString; // [rsp+30h] [rbp-20h] BYREF
  HSTRING string; // [rsp+38h] [rbp-18h] BYREF
  HSTRING v16; // [rsp+40h] [rbp-10h] BYREF

  v1 = __abi_CustomToString((int *)(a1 + 48));
  v2 = v1;
  v16 = v1;
  if ( v1 )
  {
    newString = 0;
    v3 = WindowsDuplicateString_0(v1, &newString);
    if ( v3 < 0 )
      __abi_WinRTraiseException(v3);
    v4 = newString;
  }
  else
  {
    v4 = 0;
  }
  WindowsDeleteString_0(v2);
  if ( v4 )
  {
    string = 0;
    v5 = WindowsDuplicateString_0(v4, &string);
    if ( v5 < 0 )
      __abi_WinRTraiseException(v5);
    v6 = string;
  }
  else
  {
    type_id = (HSTRING)__abi_make_type_id(&_abi_typedesc_Windows_Web_WebErrorStatus);
    string = type_id;
    v8 = (HSTRING)Platform::Type::FullName::get(type_id);
    v9 = v8;
    if ( v8 )
    {
      v16 = 0;
      v10 = WindowsDuplicateString_0(v8, &v16);
      if ( v10 < 0 )
        __abi_WinRTraiseException(v10);
      v6 = v16;
    }
    else
    {
      v6 = 0;
    }
    WindowsDeleteString_0(v9);
    if ( type_id )
      (*(void (__fastcall **)(HSTRING))(*(_QWORD *)type_id + 16LL))(type_id);
  }
  WindowsDeleteString_0(v4);
  if ( v6 )
  {
    newString = 0;
    v11 = WindowsDuplicateString_0(v6, &newString);
    if ( v11 < 0 )
      __abi_WinRTraiseException(v11);
    v12 = newString;
  }
  else
  {
    v12 = 0;
  }
  WindowsDeleteString_0(v6);
  return v12;
}

```

## disassembly

```asm
0x14001a120  mov     [rsp-18h+arg_8], rbx
0x14001a125  mov     [rsp-18h+arg_10], rsi
0x14001a12a  push    rbp
0x14001a12b  push    rdi
0x14001a12c  push    r14
0x14001a12e  mov     rbp, rsp
0x14001a131  sub     rsp, 50h
0x14001a135  mov     rax, cs:__security_cookie
0x14001a13c  xor     rax, rsp
0x14001a13f  mov     [rbp+var_8], rax
0x14001a143  add     rcx, 30h ; '0'
0x14001a147  call    ?__abi_CustomToString@@YAPE$AAVString@Platform@@PEAW4WebErrorStatus@Web@Windows@@@Z; __abi_CustomToString(Windows::Web::WebErrorStatus *)
0x14001a14c  mov     rbx, rax
0x14001a14f  mov     [rbp+var_10], rax
0x14001a153  test    rax, rax
0x14001a156  jz      short loc_14001A17A
0x14001a158  mov     [rbp+newString], 0
0x14001a160  lea     rdx, [rbp+newString]; newString
0x14001a164  mov     rcx, rax; string
0x14001a167  call    WindowsDuplicateString_0
0x14001a16c  test    eax, eax
0x14001a16e  js      loc_14001A280
0x14001a174  mov     rdi, [rbp+newString]
0x14001a178  jmp     short loc_14001A17C
0x14001a17a  xor     edi, edi
0x14001a17c  mov     [rbp+var_28], rdi
0x14001a180  mov     rcx, rbx; string
0x14001a183  call    WindowsDeleteString_0
0x14001a188  nop
0x14001a189  test    rdi, rdi
0x14001a18c  jz      short loc_14001A1B0
0x14001a18e  mov     [rbp+string], 0
0x14001a196  lea     rdx, [rbp+string]; newString
0x14001a19a  mov     rcx, rdi; string
0x14001a19d  call    WindowsDuplicateString_0
0x14001a1a2  test    eax, eax
0x14001a1a4  js      loc_14001A288
0x14001a1aa  mov     rbx, [rbp+string]
0x14001a1ae  jmp     short loc_14001A21B
0x14001a1b0  lea     rcx, __abi_typedesc_Windows_Web_WebErrorStatus
0x14001a1b7  call    cs:__imp_?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z; __abi_make_type_id(__abi_type_descriptor const &)
0x14001a1bd  mov     rsi, rax
0x14001a1c0  mov     [rbp+string], rax
0x14001a1c4  mov     rcx, rax
0x14001a1c7  call    cs:__imp_?get@FullName@Type@Platform@@QE$AAAPE$AAVString@3@XZ; Platform::Type::FullName::get(void)
0x14001a1cd  mov     r14, rax
0x14001a1d0  mov     [rbp+var_30], rax
0x14001a1d4  test    rax, rax
0x14001a1d7  jz      short loc_14001A1FB
0x14001a1d9  mov     [rbp+var_10], 0
0x14001a1e1  lea     rdx, [rbp+var_10]; newString
0x14001a1e5  mov     rcx, rax; string
0x14001a1e8  call    WindowsDuplicateString_0
0x14001a1ed  test    eax, eax
0x14001a1ef  js      loc_14001A290
0x14001a1f5  mov     rbx, [rbp+var_10]
0x14001a1f9  jmp     short loc_14001A1FD
0x14001a1fb  xor     ebx, ebx
0x14001a1fd  mov     rcx, r14; string
0x14001a200  call    WindowsDeleteString_0
0x14001a205  nop
0x14001a206  test    rsi, rsi
0x14001a209  jz      short loc_14001A21B
0x14001a20b  mov     rax, [rsi]
0x14001a20e  mov     rcx, rsi
0x14001a211  mov     rax, [rax+10h]
0x14001a215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001a21a  nop
0x14001a21b  mov     rcx, rdi; string
0x14001a21e  call    WindowsDeleteString_0
0x14001a223  mov     [rbp+var_30], rbx
0x14001a227  test    rbx, rbx
0x14001a22a  jz      short loc_14001A24A
0x14001a22c  mov     [rbp+newString], 0
0x14001a234  lea     rdx, [rbp+newString]; newString
0x14001a238  mov     rcx, rbx; string
0x14001a23b  call    WindowsDuplicateString_0
0x14001a240  test    eax, eax
0x14001a242  js      short loc_14001A278
0x14001a244  mov     rdi, [rbp+newString]
0x14001a248  jmp     short loc_14001A24C
0x14001a24a  xor     edi, edi
0x14001a24c  mov     rcx, rbx; string
0x14001a24f  call    WindowsDeleteString_0
0x14001a254  mov     rax, rdi
0x14001a257  mov     rcx, [rbp+var_8]
0x14001a25b  xor     rcx, rsp; StackCookie
0x14001a25e  call    __security_check_cookie
0x14001a263  lea     r11, [rsp+50h+var_s0]
0x14001a268  mov     rbx, [r11+28h]
0x14001a26c  mov     rsi, [r11+30h]
0x14001a270  mov     rsp, r11
0x14001a273  pop     r14
0x14001a275  pop     rdi
0x14001a276  pop     rbp
0x14001a277  retn
0x14001a278  mov     ecx, eax; int
0x14001a27a  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x14001a280  mov     ecx, eax; int
0x14001a282  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x14001a288  mov     ecx, eax; int
0x14001a28a  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
0x14001a290  mov     ecx, eax; int
0x14001a292  call    ?__abi_WinRTraiseException@@YAXJ@Z; __abi_WinRTraiseException(long)
```
