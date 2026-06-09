# Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::AllocateAndCopyElements(Windows::UI::Xaml::Markup::XmlnsDefinition const *,uint)

- ea: `0x14000bf34`
- end: `0x14000bfd2`
- name: `?AllocateAndCopyElements@?$WriteOnlyArray@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@Platform@@KAPEAVXmlnsDefinition@Markup@Xaml@UI@Windows@@PEBV34567@I@Z`
- size: `158`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x14000b168`
- `0x14000b304`

## callees

- `0x14000342d`
- `0x1400039f2`
- `0x140008900`
- `0x14000bf34`

## import_xrefs

- `wincorlib!?__abi_WinRTraiseInvalidCastException@@YAXXZ` at `0x14000bf56`
- `wincorlib!?__abi_WinRTraiseInvalidCastException@@YAXXZ` at `0x14000bf56`
- `wincorlib!?__abi_WinRTraiseOutOfMemoryException@@YAXXZ` at `0x14000bf74`
- `wincorlib!?__abi_WinRTraiseOutOfMemoryException@@YAXXZ` at `0x14000bf74`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char *__fastcall Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::AllocateAndCopyElements(
        __int64 a1,
        unsigned int a2)
{
  __int64 v2; // rsi
  char *v4; // rdi
  char *v5; // rax
  unsigned int v6; // r15d
  __int64 v7; // rbp

  v2 = a2;
  if ( !a2 )
    return 0;
  if ( a2 > 0xFFFFFFF )
  {
    __abi_WinRTraiseInvalidCastException();
    __debugbreak();
  }
  v5 = (char *)_Platform_CoTaskMemAlloc(16LL * a2);
  v4 = v5;
  if ( !v5 )
  {
    __abi_WinRTraiseOutOfMemoryException();
    __debugbreak();
  }
  memset_0(v5, 0, 16 * v2);
  v6 = 0;
  if ( (_DWORD)v2 )
  {
    v7 = 0;
    do
    {
      __abi_winrt_ptrto_string_assign(&v4[16 * v7], *(_QWORD *)(16 * v7 + a1));
      __abi_winrt_ptrto_string_assign(&v4[16 * v7 + 8], *(_QWORD *)(16 * v7 + a1 + 8));
      ++v6;
      ++v7;
    }
    while ( v6 < (unsigned int)v2 );
  }
  return v4;
}

```

## disassembly

```asm
0x14000bf34  push    rbx
0x14000bf36  push    rbp
0x14000bf37  push    rsi
0x14000bf38  push    rdi
0x14000bf39  push    r14
0x14000bf3b  push    r15
0x14000bf3d  sub     rsp, 28h
0x14000bf41  mov     esi, edx
0x14000bf43  mov     r14, rcx
0x14000bf46  test    edx, edx
0x14000bf48  jnz     short loc_14000BF4E
0x14000bf4a  xor     edi, edi
0x14000bf4c  jmp     short loc_14000BFC2
0x14000bf4e  cmp     esi, 0FFFFFFFh
0x14000bf54  jbe     short loc_14000BF5D
0x14000bf56  call    cs:__imp_?__abi_WinRTraiseInvalidCastException@@YAXXZ; __abi_WinRTraiseInvalidCastException(void)
0x14000bf5c  int     3; Trap to Debugger
0x14000bf5d  mov     rbx, rsi
0x14000bf60  shl     rbx, 4
0x14000bf64  mov     rcx, rbx; cb
0x14000bf67  call    __Platform_CoTaskMemAlloc
0x14000bf6c  mov     rdi, rax
0x14000bf6f  test    rax, rax
0x14000bf72  jnz     short loc_14000BF7B
0x14000bf74  call    cs:__imp_?__abi_WinRTraiseOutOfMemoryException@@YAXXZ; __abi_WinRTraiseOutOfMemoryException(void)
0x14000bf7a  int     3; Trap to Debugger
0x14000bf7b  mov     r8, rbx; Size
0x14000bf7e  xor     edx, edx; Val
0x14000bf80  mov     rcx, rdi; void *
0x14000bf83  call    memset_0
0x14000bf88  xor     r15d, r15d
0x14000bf8b  test    esi, esi
0x14000bf8d  jz      short loc_14000BFC2
0x14000bf8f  xor     ebp, ebp
0x14000bf91  mov     rbx, rbp
0x14000bf94  shl     rbx, 4
0x14000bf98  lea     rcx, [rbx+rdi]
0x14000bf9c  mov     rdx, [rbx+r14]
0x14000bfa0  call    ?__abi_winrt_ptrto_string_assign@@YAPEAXPEAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_assign(void * *,Platform::String const volatile *)
0x14000bfa5  lea     rcx, [rdi+8]
0x14000bfa9  add     rcx, rbx
0x14000bfac  mov     rdx, [rbx+r14+8]
0x14000bfb1  call    ?__abi_winrt_ptrto_string_assign@@YAPEAXPEAPEAXPE$ADVString@Platform@@@Z; __abi_winrt_ptrto_string_assign(void * *,Platform::String const volatile *)
0x14000bfb6  nop
0x14000bfb7  inc     r15d
0x14000bfba  inc     rbp
0x14000bfbd  cmp     r15d, esi
0x14000bfc0  jb      short loc_14000BF91
0x14000bfc2  mov     rax, rdi
0x14000bfc5  add     rsp, 28h
0x14000bfc9  pop     r15
0x14000bfcb  pop     r14
0x14000bfcd  pop     rdi
0x14000bfce  pop     rsi
0x14000bfcf  pop     rbp
0x14000bfd0  pop     rbx
0x14000bfd1  retn
```
