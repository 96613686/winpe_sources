# Windows::Networking::UX::CStaticIpConfig::AddAddressWithSkipChoice(HSTRING__ *,uint,uchar,uchar)

- ea: `0x1800125b0`
- end: `0x18001266f`
- name: `?AddAddressWithSkipChoice@CStaticIpConfig@UX@Networking@Windows@@UEAAJPEAUHSTRING__@@IEE@Z`
- size: `191`
- prototype: `__int64 __fastcall(Windows::Networking::UX::CStaticIpConfig *__hidden this, HSTRING, unsigned int, unsigned __int8, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1800125b0`
- `0x180019574`
- `0x18001a2d0`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800125d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012625`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800125d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012625`

## string_xrefs

- `0x18001260e`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`
- `0x180012653`: `onecoreuap\net\ux\uxmanager\lib\cstaticipconfig.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Networking::UX::CStaticIpConfig::AddAddressWithSkipChoice(
        Windows::Networking::UX::CStaticIpConfig *this,
        HSTRING a2,
        unsigned int a3,
        char a4,
        char a5)
{
  unsigned int v8; // ebx
  __int64 v9; // rcx
  int v10; // eax
  int v11; // eax
  HSTRING string; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v8 = 0;
  if ( !a4 )
  {
    WindowsDeleteString(0);
    string = 0;
    v8 = Windows::Networking::UX::CStaticIpConfig::ShortenIpString(v9, *((_DWORD *)this + 8), a2, &string);
    v10 = (*(__int64 (__fastcall **)(_QWORD, HSTRING))(**((_QWORD **)this + 5) + 104LL))(*((_QWORD *)this + 5), string);
    if ( v10 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x74,
        (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
        (const char *)(unsigned int)v10,
        (int)string);
    WindowsDeleteString(string);
  }
  if ( !a5 )
  {
    v11 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 6) + 104LL))(*((_QWORD *)this + 6), a3);
    if ( v11 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x79,
        (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\cstaticipconfig.cpp",
        (const char *)(unsigned int)v11,
        (int)string);
  }
  return v8;
}

```

## disassembly

```asm
0x1800125b0  push    rbx
0x1800125b2  push    rbp
0x1800125b3  push    rsi
0x1800125b4  push    rdi
0x1800125b5  sub     rsp, 38h
0x1800125b9  mov     esi, r8d
0x1800125bc  mov     rbp, rdx
0x1800125bf  mov     rdi, rcx
0x1800125c2  xor     ebx, ebx
0x1800125c4  test    r9b, r9b
0x1800125c7  jnz     short loc_18001262B
0x1800125c9  mov     [rsp+58h+string], rbx
0x1800125ce  xor     ecx, ecx; string
0x1800125d0  call    cs:__imp_WindowsDeleteString
0x1800125d6  mov     [rsp+58h+string], rbx; int
0x1800125db  lea     r9, [rsp+58h+string]
0x1800125e0  mov     r8, rbp
0x1800125e3  mov     edx, [rdi+20h]
0x1800125e6  call    ?ShortenIpString@CStaticIpConfig@UX@Networking@Windows@@AEAAJW4IpFamily@234@PEAUHSTRING__@@PEAPEAU6@@Z; Windows::Networking::UX::CStaticIpConfig::ShortenIpString(Windows::Networking::UX::IpFamily,HSTRING__ *,HSTRING__ * *)
0x1800125eb  mov     ebx, eax
0x1800125ed  mov     rcx, [rdi+28h]
0x1800125f1  mov     r8, [rcx]
0x1800125f4  mov     rdx, [rsp+58h+string]
0x1800125f9  mov     rax, [r8+68h]
0x1800125fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012602  mov     rcx, [rsp+58h]; this
0x180012607  test    eax, eax
0x180012609  jns     short loc_180012620
0x18001260b  mov     r9d, eax; char *
0x18001260e  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x180012615  mov     edx, 74h ; 't'; void *
0x18001261a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001261f  nop
0x180012620  mov     rcx, [rsp+58h+string]; string
0x180012625  call    cs:__imp_WindowsDeleteString
0x18001262b  cmp     [rsp+58h+arg_20], 0
0x180012633  jnz     short loc_180012664
0x180012635  mov     rcx, [rdi+30h]
0x180012639  mov     rax, [rcx]
0x18001263c  mov     edx, esi
0x18001263e  mov     rax, [rax+68h]
0x180012642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012647  test    eax, eax
0x180012649  jns     short loc_180012664
0x18001264b  mov     rcx, [rsp+58h]; this
0x180012650  mov     r9d, eax; char *
0x180012653  lea     r8, aOnecoreuapNetU; "onecoreuap\\net\\ux\\uxmanager\\lib\\cs"...
0x18001265a  mov     edx, 79h ; 'y'; void *
0x18001265f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180012664  mov     eax, ebx
0x180012666  add     rsp, 38h
0x18001266a  pop     rdi
0x18001266b  pop     rsi
0x18001266c  pop     rbp
0x18001266d  pop     rbx
0x18001266e  retn
```
