# ?CreateFromString@?QIXamlType@Markup@Xaml@UI@Windows@@XamlSystemBaseType@InfoProvider@XamlTypeInfo@@UE$AAAPE$AAVObject@Platform@@PE$AAVString@Platform@@@Z

- ea: `0x140025200`
- end: `0x140025244`
- name: `?CreateFromString@?QIXamlType@Markup@Xaml@UI@Windows@@XamlSystemBaseType@InfoProvider@XamlTypeInfo@@UE$AAAPE$AAVObject@Platform@@PE$AAVString@Platform@@@Z`
- size: `68`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140025250`
- `0x140026980`

## callees

- `0x140003330`
- `0x1400088b4`

## import_xrefs

- `wincorlib!??0NotImplementedException@Platform@@QE$AAA@XZ` at `0x14002521a`
- `wincorlib!??0NotImplementedException@Platform@@QE$AAA@XZ` at `0x14002521a`
- `wincorlib!?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14002520c`
- `wincorlib!?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14002520c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __noreturn _CreateFromString__QIXamlType_Markup_Xaml_UI_Windows__XamlSystemBaseType_InfoProvider_XamlTypeInfo__UE_AAAPE_AAVObject_Platform__PE_AAVString_Platform___Z()
{
  __int64 pExceptionObject; // [rsp+40h] [rbp+18h] BYREF
  void *Exception; // [rsp+48h] [rbp+20h]

  Exception = Platform::Details::Heap::AllocateException(0x68u, 0x90u);
  Exception = (void *)Platform::NotImplementedException::NotImplementedException(Exception);
  pExceptionObject = __abi_winrt_ptr_ctor(Exception);
  throw (Platform::NotImplementedException **)&pExceptionObject;
}

```

## disassembly

```asm
0x140025200  sub     rsp, 28h
0x140025204  mov     edx, 90h
0x140025209  lea     ecx, [rdx-28h]
0x14002520c  call    cs:__imp_?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::AllocateException(unsigned __int64,unsigned __int64)
0x140025212  mov     [rsp+28h+arg_18], rax
0x140025217  mov     rcx, rax
0x14002521a  call    cs:__imp_??0NotImplementedException@Platform@@QE$AAA@XZ; Platform::NotImplementedException::NotImplementedException(void)
0x140025220  mov     [rsp+28h+arg_18], rax
0x140025225  mov     rcx, rax
0x140025228  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x14002522d  mov     [rsp+28h+pExceptionObject], rax
0x140025232  lea     rdx, _TI11PE$AAVNotImplementedException@Platform@@; pThrowInfo
0x140025239  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x14002523e  call    _CxxThrowException_0
```
