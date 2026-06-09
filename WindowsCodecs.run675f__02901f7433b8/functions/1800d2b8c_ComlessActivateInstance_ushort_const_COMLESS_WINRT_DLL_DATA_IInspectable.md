# ComlessActivateInstance(ushort const *,COMLESS_WINRT_DLL_DATA &,IInspectable * *)

- ea: `0x1800d2b8c`
- end: `0x1800d2d0d`
- name: `?ComlessActivateInstance@@YAJPEBGAEAUCOMLESS_WINRT_DLL_DATA@@PEAPEAUIInspectable@@@Z`
- size: `385`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct COMLESS_WINRT_DLL_DATA *, struct IInspectable **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18009d760`

## callees

- `0x18006ec2c`
- `0x18009a95c`
- `0x1800bd9d4`
- `0x1800d2b8c`
- `0x1800d2d14`
- `0x1800e5e60`
- `0x1800e709e`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d2c3e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d2c3e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d2bcd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d2bcd`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800d2ce0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800d2ce0`

## string_xrefs

- `0x1800d2bfe`: `DllGetActivationFactory`

## pseudocode

```c
__int64 __fastcall ComlessActivateInstance(const unsigned __int16 *a1, LPCWSTR *a2, struct IInspectable **a3)
{
  HMODULE v3; // rdi
  HMODULE Library; // rax
  unsigned int v7; // ebx
  FARPROC DllGetActivationFactory; // rsi
  __int64 (__fastcall *v9)(_QWORD, _QWORD); // rbx
  __int64 v10; // rax
  int v11; // eax
  _RTL_CRITICAL_SECTION *v13; // [rsp+20h] [rbp-58h] BYREF
  const unsigned __int16 *v14; // [rsp+28h] [rbp-50h] BYREF
  _BYTE v15[32]; // [rsp+30h] [rbp-48h] BYREF

  v3 = 0;
  v14 = a1;
  *a3 = 0;
  if ( !a2[1] )
  {
    Library = LoadLibraryExW(*a2, 0, 0x800u);
    v3 = Library;
    if ( !Library )
    {
      v7 = -2003292336;
      if ( (_DWORD)g_doStackCaptures )
        DoStackCapture(-2003292336);
      return v7;
    }
    DllGetActivationFactory = GetProcAddress_0(Library, "DllGetActivationFactory");
    if ( !DllGetActivationFactory )
    {
      v7 = -2003292336;
      if ( (_DWORD)g_doStackCaptures )
        DoStackCapture(-2003292336);
LABEL_19:
      FreeLibrary(v3);
      return v7;
    }
    v13 = &CCodecFactory::s_ComponentsLock;
    EnterCriticalSection(&CCodecFactory::s_ComponentsLock);
    if ( !a2[1] )
    {
      a2[1] = (LPCWSTR)v3;
      v3 = 0;
      a2[2] = (LPCWSTR)DllGetActivationFactory;
    }
    CGuard<CCriticalSection>::~CGuard<CCriticalSection>(&v13);
  }
  v9 = (__int64 (__fastcall *)(_QWORD, _QWORD))a2[2];
  if ( v9 )
  {
    v13 = 0;
    v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v15, &v14);
    v11 = v9(*(_QWORD *)(v10 + 24), &v13);
    v7 = v11;
    if ( v11 < 0
      || (v11 = (*(__int64 (__fastcall **)(_RTL_CRITICAL_SECTION *, struct IInspectable **))&v13->DebugInfo[1].Type)(
                  v13,
                  a3),
          v7 = v11,
          v11 < 0) )
    {
      if ( (_DWORD)g_doStackCaptures )
        DoStackCapture(v11);
    }
    wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(&v13);
  }
  else
  {
    v7 = -2003292336;
  }
  if ( v3 )
    goto LABEL_19;
  return v7;
}

```

## disassembly

```asm
0x1800d2b8c  mov     [rsp+arg_18], rbx
0x1800d2b91  push    rsi
0x1800d2b92  push    rdi
0x1800d2b93  push    r14
0x1800d2b95  sub     rsp, 60h
0x1800d2b99  mov     rax, cs:__security_cookie
0x1800d2ba0  xor     rax, rsp
0x1800d2ba3  mov     [rsp+78h+var_28], rax
0x1800d2ba8  xor     edi, edi
0x1800d2baa  mov     [rsp+78h+var_50], rcx
0x1800d2baf  mov     [r8], rdi
0x1800d2bb2  mov     r14, r8
0x1800d2bb5  mov     rbx, rdx
0x1800d2bb8  cmp     [rdx+8], rdi
0x1800d2bbc  jnz     loc_1800D2C65
0x1800d2bc2  mov     rcx, [rbx]; lpLibFileName
0x1800d2bc5  xor     edx, edx; hFile
0x1800d2bc7  mov     r8d, 800h; dwFlags
0x1800d2bcd  call    cs:__imp_LoadLibraryExW
0x1800d2bd4  nop     dword ptr [rax+rax+00h]
0x1800d2bd9  mov     rdi, rax
0x1800d2bdc  test    rax, rax
0x1800d2bdf  jnz     short loc_1800D2BFE
0x1800d2be1  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x1800d2be7  mov     ebx, 88982F50h
0x1800d2bec  jz      loc_1800D2CEC
0x1800d2bf2  mov     ecx, ebx; int
0x1800d2bf4  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d2bf9  jmp     loc_1800D2CEC
0x1800d2bfe  lea     rdx, aDllgetactivati; "DllGetActivationFactory"
0x1800d2c05  mov     rcx, rdi; hModule
0x1800d2c08  call    GetProcAddress_0
0x1800d2c0d  mov     rsi, rax
0x1800d2c10  test    rax, rax
0x1800d2c13  jnz     short loc_1800D2C32
0x1800d2c15  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x1800d2c1b  mov     ebx, 88982F50h
0x1800d2c20  jz      loc_1800D2CDD
0x1800d2c26  mov     ecx, ebx; int
0x1800d2c28  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d2c2d  jmp     loc_1800D2CDD
0x1800d2c32  lea     rcx, ?s_ComponentsLock@CCodecFactory@@2VCCriticalSection@@A; lpCriticalSection
0x1800d2c39  mov     [rsp+78h+var_58], rcx
0x1800d2c3e  call    cs:__imp_EnterCriticalSection
0x1800d2c45  nop     dword ptr [rax+rax+00h]
0x1800d2c4a  cmp     qword ptr [rbx+8], 0
0x1800d2c4f  jnz     short loc_1800D2C5B
0x1800d2c51  mov     [rbx+8], rdi
0x1800d2c55  xor     edi, edi
0x1800d2c57  mov     [rbx+10h], rsi
0x1800d2c5b  lea     rcx, [rsp+78h+var_58]
0x1800d2c60  call    ??1?$CGuard@VCCriticalSection@@@@QEAA@XZ; CGuard<CCriticalSection>::~CGuard<CCriticalSection>(void)
0x1800d2c65  mov     rbx, [rbx+10h]
0x1800d2c69  test    rbx, rbx
0x1800d2c6c  jz      short loc_1800D2CD3
0x1800d2c6e  lea     rdx, [rsp+78h+var_50]
0x1800d2c73  mov     [rsp+78h+var_58], 0
0x1800d2c7c  lea     rcx, [rsp+78h+var_48]
0x1800d2c81  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800d2c86  lea     rdx, [rsp+78h+var_58]
0x1800d2c8b  mov     rcx, [rax+18h]
0x1800d2c8f  mov     rax, rbx
0x1800d2c92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2c97  mov     ebx, eax
0x1800d2c99  test    eax, eax
0x1800d2c9b  js      short loc_1800D2CB7
0x1800d2c9d  mov     rcx, [rsp+78h+var_58]
0x1800d2ca2  mov     rdx, r14
0x1800d2ca5  mov     rax, [rcx]
0x1800d2ca8  mov     rax, [rax+30h]
0x1800d2cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2cb1  mov     ebx, eax
0x1800d2cb3  test    eax, eax
0x1800d2cb5  jns     short loc_1800D2CC7
0x1800d2cb7  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800d2cbe  jz      short loc_1800D2CC7
0x1800d2cc0  mov     ecx, eax; int
0x1800d2cc2  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d2cc7  lea     rcx, [rsp+78h+var_58]
0x1800d2ccc  call    ??1?$com_ptr_t@UID2D1DeviceContext5@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(void)
0x1800d2cd1  jmp     short loc_1800D2CD8
0x1800d2cd3  mov     ebx, 88982F50h
0x1800d2cd8  test    rdi, rdi
0x1800d2cdb  jz      short loc_1800D2CEC
0x1800d2cdd  mov     rcx, rdi; hLibModule
0x1800d2ce0  call    cs:__imp_FreeLibrary
0x1800d2ce7  nop     dword ptr [rax+rax+00h]
0x1800d2cec  mov     eax, ebx
0x1800d2cee  mov     rcx, [rsp+78h+var_28]
0x1800d2cf3  xor     rcx, rsp; StackCookie
0x1800d2cf6  call    __security_check_cookie
0x1800d2cfb  mov     rbx, [rsp+78h+arg_18]
0x1800d2d03  add     rsp, 60h
0x1800d2d07  pop     r14
0x1800d2d09  pop     rdi
0x1800d2d0a  pop     rsi
0x1800d2d0b  retn
```
