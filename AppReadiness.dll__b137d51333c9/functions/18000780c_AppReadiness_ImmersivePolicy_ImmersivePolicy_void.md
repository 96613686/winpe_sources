# AppReadiness::ImmersivePolicy::ImmersivePolicy(void)

- ea: `0x18000780c`
- end: `0x1800078ad`
- name: `??0ImmersivePolicy@AppReadiness@@QEAA@XZ`
- size: `161`
- prototype: `AppReadiness::ImmersivePolicy *__fastcall(AppReadiness::ImmersivePolicy *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180006f40`
- `0x180007b70`

## callees

- `0x18000780c`
- `0x180027a4c`
- `0x18003ecb4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000783a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000783a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000784a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000784a`

## string_xrefs

- `0x180007833`: `iuilp.dll`
- `0x18000786c`: `onecoreuap\shell\appreadiness\src\core\ImmersivePolicy.h`
- `0x180007878`: `AppReadiness::ImmersivePolicy::ImmersivePolicy`
- `0x18000787f`: `ResultFromWin32Handle(LoadLibraryEx(L"iuilp.dll", nullptr, LOAD_LIBRARY_SEARCH_SYSTEM32), reinterpret_cast<HANDLE*>(m_policyHandle.GetAddressOf()))`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
AppReadiness::ImmersivePolicy *__fastcall AppReadiness::ImmersivePolicy::ImmersivePolicy(
        AppReadiness::ImmersivePolicy *this)
{
  HMODULE Library; // rax
  signed int LastError; // eax
  bool v4; // sf
  _BYTE pExceptionObject[56]; // [rsp+30h] [rbp-38h] BYREF

  *(_QWORD *)this = &Microsoft::WRL::Wrappers::HandleT<AppReadiness::HandleTraits::ModuleHandleTraits>::`vftable';
  *((_QWORD *)this + 1) = 0;
  Library = LoadLibraryExW(L"iuilp.dll", 0, 0x800u);
  *((_QWORD *)this + 1) = Library;
  if ( Library == (HMODULE)-1LL )
  {
    LastError = GetLastError();
    v4 = LastError < 0;
    if ( LastError <= 0 )
      goto LABEL_6;
    LastError = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    LastError = 0;
  }
  v4 = LastError < 0;
LABEL_6:
  if ( v4 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)pExceptionObject,
      LastError,
      "ResultFromWin32Handle(LoadLibraryEx(L\"iuilp.dll\", nullptr, LOAD_LIBRARY_SEARCH_SYSTEM32), reinterpret_cast<HANDL"
      "E*>(m_policyHandle.GetAddressOf()))",
      "AppReadiness::ImmersivePolicy::ImmersivePolicy",
      "onecoreuap\\shell\\appreadiness\\src\\core\\ImmersivePolicy.h",
      31);
    throw (Windows::HResultException *)pExceptionObject;
  }
  return this;
}

```

## disassembly

```asm
0x18000780c  mov     [rsp+arg_0], rcx
0x180007811  push    rbx
0x180007812  sub     rsp, 60h
0x180007816  mov     rbx, rcx
0x180007819  lea     rax, ??_7?$HandleT@UModuleHandleTraits@HandleTraits@AppReadiness@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<AppReadiness::HandleTraits::ModuleHandleTraits>::`vftable'
0x180007820  mov     [rcx], rax
0x180007823  mov     qword ptr [rcx+8], 0
0x18000782b  xor     edx, edx; hFile
0x18000782d  mov     r8d, 800h; dwFlags
0x180007833  lea     rcx, LibFileName; "iuilp.dll"
0x18000783a  call    cs:__imp_LoadLibraryExW
0x180007840  mov     [rbx+8], rax
0x180007844  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180007848  jnz     short loc_18000785E
0x18000784a  call    cs:__imp_GetLastError
0x180007850  test    eax, eax
0x180007852  jle     short loc_180007862
0x180007854  movzx   eax, ax
0x180007857  or      eax, 80070000h
0x18000785c  jmp     short loc_180007860
0x18000785e  xor     eax, eax
0x180007860  test    eax, eax
0x180007862  jns     short loc_1800078A4
0x180007864  mov     [rsp+68h+var_40], 1Fh; int
0x18000786c  lea     rcx, aOnecoreuapShel_20; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180007873  mov     [rsp+68h+var_48], rcx; char *
0x180007878  lea     r9, aAppreadinessIm; "AppReadiness::ImmersivePolicy::Immersiv"...
0x18000787f  lea     r8, aResultfromwin3_5; "ResultFromWin32Handle(LoadLibraryEx(L\""...
0x180007886  mov     edx, eax; int
0x180007888  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18000788d  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180007892  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x180007899  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000789e  call    _CxxThrowException_0
0x1800078a4  mov     rax, rbx
0x1800078a7  add     rsp, 60h
0x1800078ab  pop     rbx
0x1800078ac  retn
```
