# Windows::Networking::UX::Internal::MBStateMachine::EnterPin(void)

- ea: `0x18004d970`
- end: `0x18004da71`
- name: `?EnterPin@MBStateMachine@Internal@UX@Networking@Windows@@UEAAJXZ`
- size: `257`
- prototype: `int(Windows::Networking::UX::Internal::MBStateMachine *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180005fc0`
- `0x180008c84`
- `0x18000ccb0`
- `0x18001664c`
- `0x18001cb10`
- `0x18004d970`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004da05`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004da05`

## pseudocode

```c
__int64 __fastcall Windows::Networking::UX::Internal::MBStateMachine::EnterPin(
        Windows::Networking::UX::Internal::MBStateMachine *this)
{
  HSTRING v2; // rbx
  unsigned __int64 v3; // rcx
  int v4; // ebx
  int v6; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned int v8; // [rsp+40h] [rbp+8h] BYREF
  HSTRING string; // [rsp+48h] [rbp+10h] BYREF

  MBSettingUXLogging::Verbose("Windows::Networking::UX::Internal::MBStateMachine::EnterPin", 464, "Enter");
  if ( *((_QWORD *)this + 4) )
  {
    v2 = 0;
    v8 = 0;
    string = 0;
    v3 = -1;
    do
      ++v3;
    while ( *((_WORD *)this + v3 + 92) );
    if ( (int)ULongLongToUInt(v3, &v8) >= 0 )
    {
      Microsoft::WRL::Wrappers::HString::Set(&string, (const unsigned __int16 *)this + 92, v8);
      v2 = string;
    }
    v4 = (*(__int64 (__fastcall **)(_QWORD, __int64, HSTRING))(**((_QWORD **)this + 4) + 360LL))(
           *((_QWORD *)this + 4),
           1,
           v2);
    WindowsDeleteString(string);
  }
  else
  {
    MBSettingUXLogging::Error(
      "Windows::Networking::UX::Internal::MBStateMachine::EnterPin",
      0x1DBu,
      "MBCategory is null");
    v4 = -2147467259;
  }
  MBSettingUXLogging::Verbose(
    "Windows::Networking::UX::Internal::MBStateMachine::EnterPin",
    479,
    "Exit, result=0x%x",
    v4);
  if ( v4 < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E0,
      (unsigned int)"onecoreuap\\net\\ux\\mbmediamanager\\statemachine\\lib\\mbstatemachine.cpp",
      (const char *)(unsigned int)v4,
      v6);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18004d970  mov     [rsp+arg_10], rbx
0x18004d975  push    rbp
0x18004d976  push    rsi
0x18004d977  push    rdi; int
0x18004d978  sub     rsp, 20h
0x18004d97c  mov     rdi, rcx
0x18004d97f  lea     r8, aEnter; "Enter"
0x18004d986  lea     rcx, aWindowsNetwork_64; "Windows::Networking::UX::Internal::MBSt"...
0x18004d98d  mov     edx, 1D0h; unsigned int
0x18004d992  call    ?Verbose@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Verbose(char const *,ulong,char const *,...)
0x18004d997  xor     ebp, ebp
0x18004d999  cmp     [rdi+20h], rbp
0x18004d99d  jz      short loc_18004DA0D
0x18004d99f  mov     ebx, ebp
0x18004d9a1  mov     [rsp+38h+arg_0], ebp
0x18004d9a5  mov     [rsp+38h+string], rbx
0x18004d9aa  lea     rsi, [rdi+0B8h]
0x18004d9b1  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004d9b5  inc     rcx; unsigned __int64
0x18004d9b8  cmp     [rsi+rcx*2], bp
0x18004d9bc  jnz     short loc_18004D9B5
0x18004d9be  lea     rdx, [rsp+38h+arg_0]; unsigned int *
0x18004d9c3  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18004d9c8  test    eax, eax
0x18004d9ca  js      short loc_18004D9E3
0x18004d9cc  mov     r8d, [rsp+38h+arg_0]; unsigned int
0x18004d9d1  lea     rcx, [rsp+38h+string]; this
0x18004d9d6  mov     rdx, rsi; unsigned __int16 *
0x18004d9d9  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z; Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)
0x18004d9de  mov     rbx, [rsp+38h+string]
0x18004d9e3  mov     rcx, [rdi+20h]
0x18004d9e7  mov     r8, rbx
0x18004d9ea  mov     edx, 1
0x18004d9ef  mov     rax, [rcx]
0x18004d9f2  mov     rax, [rax+168h]
0x18004d9f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d9fe  mov     rcx, [rsp+38h+string]; string
0x18004da03  mov     ebx, eax
0x18004da05  call    cs:__imp_WindowsDeleteString
0x18004da0b  jmp     short loc_18004DA2A
0x18004da0d  lea     r8, aMbcategoryIsNu; "MBCategory is null"
0x18004da14  mov     edx, 1DBh; unsigned int
0x18004da19  lea     rcx, aWindowsNetwork_64; "Windows::Networking::UX::Internal::MBSt"...
0x18004da20  call    ?Error@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Error(char const *,ulong,char const *,...)
0x18004da25  mov     ebx, 80004005h
0x18004da2a  mov     r9d, ebx
0x18004da2d  lea     r8, aExitResult0xX_2; "Exit, result=0x%x"
0x18004da34  mov     edx, 1DFh; unsigned int
0x18004da39  lea     rcx, aWindowsNetwork_64; "Windows::Networking::UX::Internal::MBSt"...
0x18004da40  call    ?Verbose@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Verbose(char const *,ulong,char const *,...)
0x18004da45  test    ebx, ebx
0x18004da47  jns     short loc_18004DA62
0x18004da49  mov     rcx, [rsp+38h]; this
0x18004da4e  lea     r8, aOnecoreuapNetU_7; "onecoreuap\\net\\ux\\mbmediamanager\\st"...
0x18004da55  mov     r9d, ebx; char *
0x18004da58  mov     edx, 1E0h; void *
0x18004da5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004da62  mov     eax, ebx
0x18004da64  mov     rbx, [rsp+38h+arg_10]
0x18004da69  add     rsp, 20h
0x18004da6d  pop     rdi
0x18004da6e  pop     rsi
0x18004da6f  pop     rbp
0x18004da70  retn
```
