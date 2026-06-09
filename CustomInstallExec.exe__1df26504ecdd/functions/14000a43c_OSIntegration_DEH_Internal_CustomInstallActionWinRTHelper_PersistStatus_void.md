# OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::PersistStatus(void)

- ea: `0x14000a43c`
- end: `0x14000a4e8`
- name: `?PersistStatus@CustomInstallActionWinRTHelper@Internal@DEH@OSIntegration@@QEAAXXZ`
- size: `172`
- prototype: `void __fastcall(OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper *this, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x140008bc4`

## callees

- `0x140007d78`
- `0x14000a43c`
- `0x14000b7a8`
- `0x14000b854`
- `0x14000f010`

## string_xrefs

- `0x14000a483`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`
- `0x14000a4b8`: `onecore\admin\appmodel\osim\src\deh\appx\custominstall\installhelper\installactionwinrthelper.cpp`

## pseudocode

```c
void __fastcall OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper::PersistStatus(
        OSIntegration::DEH::Internal::CustomInstallActionWinRTHelper *this,
        __int64 a2,
        unsigned int a3)
{
  int v3; // eax
  __int64 v5; // rdx
  int v6; // eax
  int v7; // eax
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = *((_DWORD *)this + 19);
  if ( v3 != *((_DWORD *)this + 24) )
  {
    if ( v3 )
    {
      v5 = 1;
      if ( v3 != 1 )
      {
        v5 = 2;
        if ( v3 != 2 )
          wil::details::in1diag3::Throw_Hr(retaddr, (void *)0x77, a3, (const char *)0x8000FFFFLL, v8);
      }
    }
    else
    {
      v5 = 0;
    }
    v6 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 11) + 248LL))(*((_QWORD *)this + 11), v5);
    if ( v6 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x150,
        (int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
        (const char *)(unsigned int)v6,
        v8);
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)OSIntegration::DEH::Internal::SRStatics::s_customInstallWorkStatics
                                                    + 56LL))(
           OSIntegration::DEH::Internal::SRStatics::s_customInstallWorkStatics,
           *((_QWORD *)this + 11));
    if ( v7 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x151,
        (int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\custominstall\\installhelper\\installactionwinrthelper.cpp",
        (const char *)(unsigned int)v7);
  }
}

```

## disassembly

```asm
0x14000a43c  push    rbx; int
0x14000a43e  sub     rsp, 20h
0x14000a442  mov     eax, [rcx+4Ch]
0x14000a445  mov     rbx, rcx
0x14000a448  cmp     eax, [rcx+60h]
0x14000a44b  jz      short loc_14000A4CC
0x14000a44d  test    eax, eax
0x14000a44f  jnz     short loc_14000A455
0x14000a451  xor     edx, edx
0x14000a453  jmp     short loc_14000A467
0x14000a455  mov     edx, 1
0x14000a45a  cmp     eax, edx
0x14000a45c  jz      short loc_14000A467
0x14000a45e  mov     edx, 2
0x14000a463  cmp     eax, edx
0x14000a465  jnz     short loc_14000A4D2
0x14000a467  mov     rcx, [rcx+58h]
0x14000a46b  mov     rax, [rcx]
0x14000a46e  mov     rax, [rax+0F8h]
0x14000a475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a47a  test    eax, eax
0x14000a47c  jns     short loc_14000A498
0x14000a47e  mov     rcx, [rsp+28h]; this
0x14000a483  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x14000a48a  mov     r9d, eax; char *
0x14000a48d  mov     edx, 150h; void *
0x14000a492  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000a498  mov     rcx, cs:?s_customInstallWorkStatics@SRStatics@Internal@DEH@OSIntegration@@1V?$ComPtr@UICustomInstallWorkStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ICustomInstallWorkStatics> OSIntegration::DEH::Internal::SRStatics::s_customInstallWorkStatics
0x14000a49f  mov     rdx, [rbx+58h]
0x14000a4a3  mov     rax, [rcx]
0x14000a4a6  mov     rax, [rax+38h]
0x14000a4aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a4af  test    eax, eax
0x14000a4b1  jns     short loc_14000A4CC
0x14000a4b3  mov     rcx, [rsp+28h]; this
0x14000a4b8  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x14000a4bf  mov     r9d, eax; char *
0x14000a4c2  mov     edx, 151h; void *
0x14000a4c7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000a4cc  add     rsp, 20h
0x14000a4d0  pop     rbx
0x14000a4d1  retn
0x14000a4d2  mov     rcx, [rsp+28h]; this
0x14000a4d7  mov     edx, 77h ; 'w'; void *
0x14000a4dc  mov     r9d, 8000FFFFh; char *
0x14000a4e2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
