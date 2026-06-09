# ComlessActivateInstance(ushort const *,COMLESS_WINRT_DLL_DATA &,IInspectable * *)

- ea: `0x1800d02ac`
- end: `0x1800d041a`
- name: `?ComlessActivateInstance@@YAJPEBGAEAUCOMLESS_WINRT_DLL_DATA@@PEAPEAUIInspectable@@@Z`
- size: `366`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct COMLESS_WINRT_DLL_DATA *, struct IInspectable **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18009c21c`

## callees

- `0x18007d6cc`
- `0x180098f08`
- `0x1800bb784`
- `0x1800d02ac`
- `0x1800d0420`
- `0x1800e2f90`
- `0x1800e41ae`
- `0x1801ca010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d0358`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800d0358`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d02ed`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800d02ed`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800d03f4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800d03f4`

## string_xrefs

- `0x1800d0318`: `DllGetActivationFactory`

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
0x1800d02ac  mov     [rsp+arg_18], rbx
0x1800d02b1  push    rsi
0x1800d02b2  push    rdi
0x1800d02b3  push    r14
0x1800d02b5  sub     rsp, 60h
0x1800d02b9  mov     rax, cs:__security_cookie
0x1800d02c0  xor     rax, rsp
0x1800d02c3  mov     [rsp+78h+var_28], rax
0x1800d02c8  xor     edi, edi
0x1800d02ca  mov     [rsp+78h+var_50], rcx
0x1800d02cf  mov     [r8], rdi
0x1800d02d2  mov     r14, r8
0x1800d02d5  mov     rbx, rdx
0x1800d02d8  cmp     [rdx+8], rdi
0x1800d02dc  jnz     loc_1800D0379
0x1800d02e2  mov     rcx, [rbx]; lpLibFileName
0x1800d02e5  xor     edx, edx; hFile
0x1800d02e7  mov     r8d, 800h; dwFlags
0x1800d02ed  call    cs:__imp_LoadLibraryExW
0x1800d02f3  mov     rdi, rax
0x1800d02f6  test    rax, rax
0x1800d02f9  jnz     short loc_1800D0318
0x1800d02fb  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x1800d0301  mov     ebx, 88982F50h
0x1800d0306  jz      loc_1800D03FA
0x1800d030c  mov     ecx, ebx; int
0x1800d030e  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d0313  jmp     loc_1800D03FA
0x1800d0318  lea     rdx, aDllgetactivati; "DllGetActivationFactory"
0x1800d031f  mov     rcx, rdi; hModule
0x1800d0322  call    GetProcAddress_0
0x1800d0327  mov     rsi, rax
0x1800d032a  test    rax, rax
0x1800d032d  jnz     short loc_1800D034C
0x1800d032f  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x1800d0335  mov     ebx, 88982F50h
0x1800d033a  jz      loc_1800D03F1
0x1800d0340  mov     ecx, ebx; int
0x1800d0342  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d0347  jmp     loc_1800D03F1
0x1800d034c  lea     rcx, ?s_ComponentsLock@CCodecFactory@@2VCCriticalSection@@A; lpCriticalSection
0x1800d0353  mov     [rsp+78h+var_58], rcx
0x1800d0358  call    cs:__imp_EnterCriticalSection
0x1800d035e  cmp     qword ptr [rbx+8], 0
0x1800d0363  jnz     short loc_1800D036F
0x1800d0365  mov     [rbx+8], rdi
0x1800d0369  xor     edi, edi
0x1800d036b  mov     [rbx+10h], rsi
0x1800d036f  lea     rcx, [rsp+78h+var_58]
0x1800d0374  call    ??1?$CGuard@VCCriticalSection@@@@QEAA@XZ; CGuard<CCriticalSection>::~CGuard<CCriticalSection>(void)
0x1800d0379  mov     rbx, [rbx+10h]
0x1800d037d  test    rbx, rbx
0x1800d0380  jz      short loc_1800D03E7
0x1800d0382  lea     rdx, [rsp+78h+var_50]
0x1800d0387  mov     [rsp+78h+var_58], 0
0x1800d0390  lea     rcx, [rsp+78h+var_48]
0x1800d0395  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800d039a  lea     rdx, [rsp+78h+var_58]
0x1800d039f  mov     rcx, [rax+18h]
0x1800d03a3  mov     rax, rbx
0x1800d03a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d03ab  mov     ebx, eax
0x1800d03ad  test    eax, eax
0x1800d03af  js      short loc_1800D03CB
0x1800d03b1  mov     rcx, [rsp+78h+var_58]
0x1800d03b6  mov     rdx, r14
0x1800d03b9  mov     rax, [rcx]
0x1800d03bc  mov     rax, [rax+30h]
0x1800d03c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d03c5  mov     ebx, eax
0x1800d03c7  test    eax, eax
0x1800d03c9  jns     short loc_1800D03DB
0x1800d03cb  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1800d03d2  jz      short loc_1800D03DB
0x1800d03d4  mov     ecx, eax; int
0x1800d03d6  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800d03db  lea     rcx, [rsp+78h+var_58]
0x1800d03e0  call    ??1?$com_ptr_t@UID2D1DeviceContext5@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>::~com_ptr_t<ID2D1DeviceContext5,wil::err_returncode_policy>(void)
0x1800d03e5  jmp     short loc_1800D03EC
0x1800d03e7  mov     ebx, 88982F50h
0x1800d03ec  test    rdi, rdi
0x1800d03ef  jz      short loc_1800D03FA
0x1800d03f1  mov     rcx, rdi; hLibModule
0x1800d03f4  call    cs:__imp_FreeLibrary
0x1800d03fa  mov     eax, ebx
0x1800d03fc  mov     rcx, [rsp+78h+var_28]
0x1800d0401  xor     rcx, rsp; StackCookie
0x1800d0404  call    __security_check_cookie
0x1800d0409  mov     rbx, [rsp+78h+arg_18]
0x1800d0411  add     rsp, 60h
0x1800d0415  pop     r14
0x1800d0417  pop     rdi
0x1800d0418  pop     rsi
0x1800d0419  retn
```
