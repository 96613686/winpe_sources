# DependencyLocator::Internal::ExternalDependencyStorage::GetLocalStorageFromModule(ushort const *,void (*)(HINSTANCE__ * const,ushort const *),bool)

- ea: `0x180268f08`
- end: `0x1802692fb`
- name: `?GetLocalStorageFromModule@ExternalDependencyStorage@Internal@DependencyLocator@@QEAAPEAUILocalDependencyStorage@23@PEBGP6AXQEAUHINSTANCE__@@0@Z_N@Z`
- size: `1011`
- prototype: `DependencyLocator::Internal::ILocalDependencyStorage *__fastcall(DependencyLocator::Internal::ExternalDependencyStorage *this, const wchar_t *moduleName, void (__fastcall *pfnTelemetryProc)(HINSTANCE__ *const, const wchar_t *), bool allowLoadingModule)`
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180268e3c`
- `0x180268ec0`

## callees

- `0x180004bc0`
- `0x180131190`
- `0x1801e5458`
- `0x180268f08`
- `0x180269304`
- `0x1802693ac`
- `0x180269498`
- `0x180687744`
- `0x1806877a8`
- `0x180687890`
- `0x1806c5050`
- `0x180c0e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1802690c8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1802690c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1802690f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1802690f3`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180268ff5`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18026906d`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x180268ff5`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18026906d`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180269230`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180269270`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1802692b0`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1802692ea`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180269230`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x180269270`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1802692b0`
- `api-ms-win-core-winrt-errorprivate-l1-1-0!RoFailFastWithErrorContextInternal2` at `0x1802692ea`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180268f7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026908e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026913f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802691f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180268f7a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026908e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18026913f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1802691f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180268f68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180268f68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180268fb4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180268fc4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18026902d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18026903e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180268fb4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180268fc4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18026902d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18026903e`

## pseudocode

```c
DependencyLocator::Internal::ILocalDependencyStorage *__fastcall DependencyLocator::Internal::ExternalDependencyStorage::GetLocalStorageFromModule(
        DependencyLocator::Internal::ExternalDependencyStorage *this,
        const wchar_t *moduleName,
        void (__fastcall *pfnTelemetryProc)(HINSTANCE__ *const, const wchar_t *),
        bool allowLoadingModule)
{
  HSTRING__ *v6; // rbx
  unsigned __int64 v7; // rdx
  int v8; // edi
  std::map<Windows::Internal::String,DependencyLocator::Internal::ILocalDependencyStorage *,DependencyLocator::Internal::ExternalDependencyStorage::stringcomparer<196624>,XcpAllocation::LeakIgnoringAllocator<std::pair<Windows::Internal::String,DependencyLocator::Internal::ILocalDependencyStorage *> > > *p_modules; // r15
  std::_Tree_node<std::pair<Windows::Internal::String const ,DependencyLocator::Internal::ILocalDependencyStorage *>,void *> *Myhead; // rsi
  std::_Tree_node<std::pair<Windows::Internal::String const ,DependencyLocator::Internal::ILocalDependencyStorage *>,void *> *i; // r14
  HSTRING hstring; // rcx
  const wchar_t *StringRawBuffer; // rdi
  const wchar_t *lpString2; // rax
  const wchar_t *v15; // rdi
  const wchar_t *v16; // rax
  DependencyLocator::Internal::ILocalDependencyStorage *second; // rdi
  HMODULE Library; // rdi
  __int64 (*ProcAddress)(void); // rdi
  HRESULT v21; // ecx
  __int64 v22; // r14
  std::_Tree_find_result<std::_Tree_node<std::pair<Windows::Internal::String const ,DependencyLocator::Internal::ILocalDependencyStorage *>,void *> *> *v23; // rax
  std::_Tree_id<std::_Tree_node<std::pair<Windows::Internal::String const ,DependencyLocator::Internal::ILocalDependencyStorage *>,void *> *> Location; // xmm6
  std::_Tree<std::_Tmap_traits<Windows::Internal::String,DependencyLocator::Internal::ILocalDependencyStorage *,DependencyLocator::Internal::ExternalDependencyStorage::stringcomparer<196624>,XcpAllocation::LeakIgnoringAllocator<std::pair<Windows::Internal::String,DependencyLocator::Internal::ILocalDependencyStorage *> >,0> > *v25; // rcx
  const char *v26; // rcx
  std::_Tree_node<std::pair<Windows::Internal::String const ,DependencyLocator::Internal::ILocalDependencyStorage *>,void *> *v27; // rdi
  std::_Tree_node<std::pair<Windows::Internal::String const ,DependencyLocator::Internal::ILocalDependencyStorage *>,void *> *FailFast; // rax
  Windows::Internal::String _Keyval; // [rsp+58h] [rbp-29h] BYREF
  __int64 v30; // [rsp+60h] [rbp-21h]
  std::_Tree_find_result<std::_Tree_node<std::pair<Windows::Internal::String const ,DependencyLocator::Internal::ILocalDependencyStorage *>,void *> *> result; // [rsp+68h] [rbp-19h] BYREF
  HSTRING cStowedExceptions; // [rsp+E8h] [rbp+67h] BYREF
  _STOWED_EXCEPTION_INFORMATION_V2 **ppStowedExceptions; // [rsp+F0h] [rbp+6Fh] BYREF
  void (__fastcall *v34)(HINSTANCE__ *const, const wchar_t *); // [rsp+F8h] [rbp+77h]
  bool v35; // [rsp+100h] [rbp+7Fh]

  v35 = allowLoadingModule;
  v34 = pfnTelemetryProc;
  v6 = 0;
  if ( !moduleName )
  {
    v8 = -2147467261;
LABEL_41:
    OnFailure_2990_(v8);
    ppStowedExceptions = 0;
    LODWORD(cStowedExceptions) = 0;
    TraceForFailFast(v8);
    GetStowedExceptionsForFailFast(&ppStowedExceptions, (unsigned int *)&cStowedExceptions);
    RoFailFastWithErrorContextInternal2(v8, (unsigned int)cStowedExceptions, ppStowedExceptions);
    goto LABEL_8;
  }
  cStowedExceptions = 0;
  v7 = -1;
  do
    ++v7;
  while ( moduleName[v7] );
  if ( v7 > 0xFFFFFFFF )
  {
    v8 = -2147024362;
  }
  else
  {
    v8 = WindowsCreateString(moduleName, v7, &cStowedExceptions);
    if ( v8 >= 0 )
    {
      v6 = cStowedExceptions;
      WindowsDeleteString(0);
    }
  }
  if ( v8 < 0 )
    goto LABEL_41;
LABEL_8:
  p_modules = &this->modules;
  Myhead = this->modules._Mypair._Myval2._Myval2._Myhead;
  *((_DWORD *)&result._Location._Child + 1) = 0;
  for ( i = Myhead->_Parent; !i->_Isnil; i = i->_Left )
  {
    hstring = i->_Myval.first._hstring;
    LODWORD(ppStowedExceptions) = 0;
    LODWORD(cStowedExceptions) = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(hstring, (UINT32 *)&ppStowedExceptions);
    lpString2 = WindowsGetStringRawBuffer(v6, (UINT32 *)&cStowedExceptions);
    if ( CompareStringEx(
           0,
           0x30010u,
           StringRawBuffer,
           (int)ppStowedExceptions,
           lpString2,
           (int)cStowedExceptions,
           0,
           0,
           0) == 1 )
      i = (std::_Tree_node<std::pair<Windows::Internal::String const ,DependencyLocator::Internal::ILocalDependencyStorage *>,void *> *)((char *)i + 16);
    else
      Myhead = i;
  }
  if ( Myhead->_Isnil
    || (LODWORD(ppStowedExceptions) = 0,
        LODWORD(cStowedExceptions) = 0,
        v15 = WindowsGetStringRawBuffer(v6, (UINT32 *)&ppStowedExceptions),
        v16 = WindowsGetStringRawBuffer(Myhead->_Myval.first._hstring, (UINT32 *)&cStowedExceptions),
        CompareStringEx(0, 0x30010u, v15, (int)ppStowedExceptions, v16, (int)cStowedExceptions, 0, 0, 0) == 1) )
  {
    Myhead = p_modules->_Mypair._Myval2._Myval2._Myhead;
  }
  else if ( Myhead != p_modules->_Mypair._Myval2._Myval2._Myhead )
  {
    second = Myhead->_Myval.second;
    if ( second )
    {
      if ( v6 )
        WindowsDeleteString(v6);
      return second;
    }
  }
  if ( v35 )
  {
    Library = LoadLibraryExW(moduleName, 0, 0);
    if ( !Library )
    {
      OnFailure_2990_(-2147023728);
      ppStowedExceptions = 0;
      LODWORD(cStowedExceptions) = 0;
      TraceForFailFast(-2147023728);
      GetStowedExceptionsForFailFast(&ppStowedExceptions, (unsigned int *)&cStowedExceptions);
      RoFailFastWithErrorContextInternal2(-2147023728, (unsigned int)cStowedExceptions, ppStowedExceptions);
    }
    v34(Library, moduleName);
    ProcAddress = GetProcAddress(Library, "GetDependencyLocatorStorage");
    if ( !ProcAddress )
    {
      OnFailure_2990_(-2147023728);
      ppStowedExceptions = 0;
      LODWORD(cStowedExceptions) = 0;
      TraceForFailFast(-2147023728);
      GetStowedExceptionsForFailFast(&ppStowedExceptions, (unsigned int *)&cStowedExceptions);
      RoFailFastWithErrorContextInternal2(-2147023728, (unsigned int)cStowedExceptions, ppStowedExceptions);
    }
    v22 = ProcAddress();
    if ( !v22 )
    {
      OnFailure_901_(v21);
      ppStowedExceptions = 0;
      LODWORD(cStowedExceptions) = 0;
      TraceForFailFast(-2147467261);
      GetStowedExceptionsForFailFast(&ppStowedExceptions, (unsigned int *)&cStowedExceptions);
      RoFailFastWithErrorContextInternal2(-2147467261, (unsigned int)cStowedExceptions, ppStowedExceptions);
    }
    (*(void (__fastcall **)(__int64, DependencyLocator::Internal::ExternalDependencyStorage *))(*(_QWORD *)v22 + 8LL))(
      v22,
      this);
    if ( Myhead == p_modules->_Mypair._Myval2._Myval2._Myhead )
    {
      _Keyval._hstring = v6;
      v30 = v22;
      v23 = std::_Tree<std::_Tmap_traits<Windows::Internal::String,DependencyLocator::Internal::ILocalDependencyStorage *,DependencyLocator::Internal::ExternalDependencyStorage::stringcomparer<196624>,XcpAllocation::LeakIgnoringAllocator<std::pair<Windows::Internal::String,DependencyLocator::Internal::ILocalDependencyStorage *>>,0>>::_Find_lower_bound<Windows::Internal::String>(
              &this->modules,
              &result,
              &_Keyval);
      Location = v23->_Location;
      if ( !std::_Tree<std::_Tmap_traits<Windows::Internal::String,DependencyLocator::Internal::ILocalDependencyStorage *,DependencyLocator::Internal::ExternalDependencyStorage::stringcomparer<196624>,XcpAllocation::LeakIgnoringAllocator<std::pair<Windows::Internal::String,DependencyLocator::Internal::ILocalDependencyStorage *>>,0>>::_Lower_bound_duplicate<Windows::Internal::String>(
              v25,
              v23->_Bound,
              &_Keyval) )
      {
        if ( this->modules._Mypair._Myval2._Myval2._Mysize == 0x555555555555555LL )
          std::_Xlength_error(v26);
        v27 = p_modules->_Mypair._Myval2._Myval2._Myhead;
        FailFast = (std::_Tree_node<std::pair<Windows::Internal::String const ,DependencyLocator::Internal::ILocalDependencyStorage *>,void *> *)XcpAllocation::OSMemoryAllocateFailFast(0x30u);
        _Keyval._hstring = 0;
        result._Location = Location;
        FailFast->_Myval.first._hstring = v6;
        FailFast->_Myval.second = (DependencyLocator::Internal::ILocalDependencyStorage *)v22;
        FailFast->_Left = v27;
        FailFast->_Parent = v27;
        FailFast->_Right = v27;
        *(_WORD *)&FailFast->_Color = 0;
        std::_Tree_val<std::_Tree_simple_types<std::pair<Windows::Internal::String const,DependencyLocator::Internal::ILocalDependencyStorage *>>>::_Insert_node(
          &this->modules._Mypair._Myval2._Myval2,
          &result._Location,
          FailFast);
      }
      Windows::Internal::String::~String(&_Keyval);
    }
    else
    {
      Myhead->_Myval.second = (DependencyLocator::Internal::ILocalDependencyStorage *)v22;
      if ( v6 )
        WindowsDeleteString(v6);
    }
    return (DependencyLocator::Internal::ILocalDependencyStorage *)v22;
  }
  else
  {
    if ( v6 )
      WindowsDeleteString(v6);
    return 0;
  }
}

```

## disassembly

```asm
0x180268f08  mov     rax, rsp
0x180268f0b  mov     [rax+20h], allowLoadingModule
0x180268f0f  mov     [rax+18h], pfnTelemetryProc
0x180268f13  push    rbp
0x180268f14  push    rbx
0x180268f15  push    rsi
0x180268f16  push    rdi
0x180268f17  push    r12
0x180268f19  push    r13
0x180268f1b  push    r14
0x180268f1d  push    r15
0x180268f1f  lea     rbp, [rax-5Fh]
0x180268f23  sub     rsp, 98h
0x180268f2a  xor     esi, esi
0x180268f2c  movaps  xmmword ptr [rax-58h], xmm6
0x180268f30  mov     r12, moduleName
0x180268f33  mov     r13, this
0x180268f36  mov     ebx, esi
0x180268f38  test    moduleName, moduleName
0x180268f3b  jz      loc_180269200
0x180268f41  mov     [rbp+57h+cStowedExceptions], rsi
0x180268f45  or      moduleName, 0FFFFFFFFFFFFFFFFh
0x180268f49  inc     moduleName; length
0x180268f4c  cmp     [r12+moduleName*2], si
0x180268f51  jnz     short loc_180268F49
0x180268f53  mov     eax, 0FFFFFFFFh
0x180268f58  cmp     moduleName, rax
0x180268f5b  ja      loc_18026914D
0x180268f61  lea     pfnTelemetryProc, [rbp+57h+cStowedExceptions]; string
0x180268f65  mov     this, r12; sourceString
0x180268f68  call    cs:__imp_WindowsCreateString
0x180268f6e  mov     edi, eax
0x180268f70  test    eax, eax
0x180268f72  js      short loc_180268F80
0x180268f74  mov     rbx, [rbp+57h+cStowedExceptions]
0x180268f78  xor     ecx, ecx; string
0x180268f7a  call    cs:__imp_WindowsDeleteString
0x180268f80  test    edi, edi
0x180268f82  js      loc_180269205
0x180268f88  xor     eax, eax
0x180268f8a  lea     r15, [r13+8]
0x180268f8e  mov     rsi, [r15]
0x180268f91  mov     dword ptr [rbp+57h+result._Location+0Ch], eax
0x180268f94  mov     r14, [rsi+8]
0x180268f98  cmp     [r14+19h], al
0x180268f9c  jnz     short loc_180269011
0x180268f9e  mov     this, [r14+20h]; string
0x180268fa2  lea     moduleName, [rbp+57h+ppStowedExceptions]; length
0x180268fa6  mov     dword ptr [rbp+57h+ppStowedExceptions], 0
0x180268fad  mov     dword ptr [rbp+57h+cStowedExceptions], 0
0x180268fb4  call    cs:__imp_WindowsGetStringRawBuffer
0x180268fba  lea     moduleName, [rbp+57h+cStowedExceptions]; length
0x180268fbe  mov     this, rbx; string
0x180268fc1  mov     rdi, rax
0x180268fc4  call    cs:__imp_WindowsGetStringRawBuffer
0x180268fca  mov     r9d, dword ptr [rbp+57h+ppStowedExceptions]; cchCount1
0x180268fce  xor     ecx, ecx
0x180268fd0  mov     [rsp+40h], this; lParam
0x180268fd5  mov     pfnTelemetryProc, rdi; lpString1
0x180268fd8  mov     [rsp+0D0h+lpReserved], this; lpReserved
0x180268fdd  mov     edx, 30010h; dwCmpFlags
0x180268fe2  mov     [rsp+0D0h+lpVersionInformation], this; lpVersionInformation
0x180268fe7  mov     ecx, dword ptr [rbp+57h+cStowedExceptions]
0x180268fea  mov     [rsp+0D0h+cchCount2], ecx; cchCount2
0x180268fee  xor     ecx, ecx; lpLocaleName
0x180268ff0  mov     [rsp+0D0h+lpString2], rax; lpString2
0x180268ff5  call    cs:__imp_CompareStringEx
0x180268ffb  cmp     eax, 1
0x180268ffe  jz      loc_180269157
0x180269004  mov     rsi, r14
0x180269007  mov     r14, [r14]
0x18026900a  cmp     byte ptr [r14+19h], 0
0x18026900f  jz      short loc_180268F9E
0x180269011  xor     r14d, r14d
0x180269014  cmp     [rsi+19h], r14b
0x180269018  jnz     loc_1802690B3
0x18026901e  lea     moduleName, [rbp+57h+ppStowedExceptions]; length
0x180269022  mov     dword ptr [rbp+57h+ppStowedExceptions], r14d
0x180269026  mov     this, rbx; string
0x180269029  mov     dword ptr [rbp+57h+cStowedExceptions], r14d
0x18026902d  call    cs:__imp_WindowsGetStringRawBuffer
0x180269033  mov     this, [rsi+20h]; string
0x180269037  lea     moduleName, [rbp+57h+cStowedExceptions]; length
0x18026903b  mov     rdi, rax
0x18026903e  call    cs:__imp_WindowsGetStringRawBuffer
0x180269044  mov     ecx, dword ptr [rbp+57h+cStowedExceptions]
0x180269047  mov     pfnTelemetryProc, rdi; lpString1
0x18026904a  mov     r9d, dword ptr [rbp+57h+ppStowedExceptions]; cchCount1
0x18026904e  mov     edx, 30010h; dwCmpFlags
0x180269053  mov     [rsp+40h], r14; lParam
0x180269058  mov     [rsp+0D0h+lpReserved], r14; lpReserved
0x18026905d  mov     [rsp+0D0h+lpVersionInformation], r14; lpVersionInformation
0x180269062  mov     [rsp+0D0h+cchCount2], ecx; cchCount2
0x180269066  xor     ecx, ecx; lpLocaleName
0x180269068  mov     [rsp+0D0h+lpString2], rax; lpString2
0x18026906d  call    cs:__imp_CompareStringEx
0x180269073  cmp     eax, 1
0x180269076  jz      short loc_1802690B3
0x180269078  cmp     rsi, [r15]
0x18026907b  jz      short loc_1802690B6
0x18026907d  mov     rdi, [rsi+28h]
0x180269081  test    rdi, rdi
0x180269084  jz      short loc_1802690B6
0x180269086  test    rbx, rbx
0x180269089  jz      short loc_180269094
0x18026908b  mov     this, rbx; string
0x18026908e  call    cs:__imp_WindowsDeleteString
0x180269094  mov     rax, rdi
0x180269097  movaps  xmm6, [rsp+0D0h+var_58+8]
0x18026909f  add     rsp, 98h
0x1802690a6  pop     r15
0x1802690a8  pop     r14
0x1802690aa  pop     r13
0x1802690ac  pop     r12
0x1802690ae  pop     rdi
0x1802690af  pop     rsi
0x1802690b0  pop     rbx
0x1802690b1  pop     rbp
0x1802690b2  retn
0x1802690b3  mov     rsi, [r15]
0x1802690b6  cmp     [rbp+57h+arg_18], r14b
0x1802690ba  jz      loc_1802691EB
0x1802690c0  xor     r8d, r8d; dwFlags
0x1802690c3  xor     edx, edx; hFile
0x1802690c5  mov     this, r12; lpLibFileName
0x1802690c8  call    cs:__imp_LoadLibraryExW
0x1802690ce  mov     rdi, rax
0x1802690d1  test    rax, rax
0x1802690d4  jz      loc_18026923B
0x1802690da  mov     rax, [rbp+57h+arg_10]
0x1802690de  mov     moduleName, r12
0x1802690e1  mov     this, rdi
0x1802690e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802690e9  lea     moduleName, aGetdependencyl; "GetDependencyLocatorStorage"
0x1802690f0  mov     this, rdi; hModule
0x1802690f3  call    cs:__imp_GetProcAddress
0x1802690f9  mov     rdi, rax
0x1802690fc  test    rax, rax
0x1802690ff  jz      loc_18026927B
0x180269105  mov     rax, rdi
0x180269108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026910d  xor     r12d, r12d
0x180269110  mov     r14, rax
0x180269113  test    rax, rax
0x180269116  jz      loc_1802692BB
0x18026911c  mov     rax, [r14]
0x18026911f  mov     moduleName, r13
0x180269122  mov     this, r14
0x180269125  mov     rax, [rax+8]
0x180269129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18026912e  cmp     rsi, [r15]
0x180269131  jz      short loc_180269160
0x180269133  mov     [rsi+28h], r14
0x180269137  test    rbx, rbx
0x18026913a  jz      short loc_180269145
0x18026913c  mov     this, rbx; string
0x18026913f  call    cs:__imp_WindowsDeleteString
0x180269145  mov     rax, r14
0x180269148  jmp     loc_180269097
0x18026914d  mov     edi, 80070216h
0x180269152  jmp     loc_180268F80
0x180269157  add     r14, 10h
0x18026915b  jmp     loc_180269007
0x180269160  lea     pfnTelemetryProc, [rbp+57h+_Keyval]; _Keyval
0x180269164  mov     [rbp+57h+_Keyval._hstring], rbx
0x180269168  lea     moduleName, [rbp+57h+result]; result
0x18026916c  mov     [rbp+57h+var_78], r14
0x180269170  mov     this, r15; this
0x180269173  call    ??$_Find_lower_bound@VString@Internal@Windows@@@?$_Tree@V?$_Tmap_traits@VString@Internal@Windows@@PEAUILocalDependencyStorage@2DependencyLocator@@V?$stringcomparer@$0DAABA@@ExternalDependencyStorage@25@U?$LeakIgnoringAllocator@U?$pair@VString@Internal@Windows@@PEAUILocalDependencyStorage@2DependencyLocator@@@std@@@XcpAllocation@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBVString@Internal@Windows@@PEAUILocalDependencyStorage@2DependencyLocator@@@std@@PEAX@std@@@1@AEBVString@Internal@Windows@@@Z; std::_Tree<std::_Tmap_traits<Windows::Internal::String,DependencyLocator::Internal::ILocalDependencyStorage *,DependencyLocator::Internal::ExternalDependencyStorage::stringcomparer<196624>,XcpAllocation::LeakIgnoringAllocator<std::pair<Windows::Internal::String,DependencyLocator::Internal::ILocalDependencyStorage *>>,0>>::_Find_lower_bound<Windows::Internal::String>(Windows::Internal::String const &)
0x180269178  lea     pfnTelemetryProc, [rbp+57h+_Keyval]; _Keyval
0x18026917c  mov     moduleName, [rax+10h]; _Bound
0x180269180  movups  xmm6, xmmword ptr [rax]
0x180269183  call    ??$_Lower_bound_duplicate@VString@Internal@Windows@@@?$_Tree@V?$_Tmap_traits@VString@Internal@Windows@@PEAUILocalDependencyStorage@2DependencyLocator@@V?$stringcomparer@$0DAABA@@ExternalDependencyStorage@25@U?$LeakIgnoringAllocator@U?$pair@VString@Internal@Windows@@PEAUILocalDependencyStorage@2DependencyLocator@@@std@@@XcpAllocation@@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBVString@Internal@Windows@@PEAUILocalDependencyStorage@2DependencyLocator@@@std@@PEAX@1@AEBVString@Internal@Windows@@@Z; std::_Tree<std::_Tmap_traits<Windows::Internal::String,DependencyLocator::Internal::ILocalDependencyStorage *,DependencyLocator::Internal::ExternalDependencyStorage::stringcomparer<196624>,XcpAllocation::LeakIgnoringAllocator<std::pair<Windows::Internal::String,DependencyLocator::Internal::ILocalDependencyStorage *>>,0>>::_Lower_bound_duplicate<Windows::Internal::String>(std::_Tree_node<std::pair<Windows::Internal::String const,DependencyLocator::Internal::ILocalDependencyStorage *>,void *> * const,Windows::Internal::String const &)
0x180269188  test    al, al
0x18026918a  jnz     short loc_1802691DD
0x18026918c  mov     rax, 555555555555555h
0x180269196  cmp     [r15+8], rax
0x18026919a  jz      loc_1802692F5
0x1802691a0  mov     rdi, [r15]
0x1802691a3  mov     ecx, 30h ; '0'; cSize
0x1802691a8  call    ?OSMemoryAllocateFailFast@XcpAllocation@@YAPEAX_K@Z; XcpAllocation::OSMemoryAllocateFailFast(unsigned __int64)
0x1802691ad  mov     pfnTelemetryProc, rax
0x1802691b0  mov     [rbp+57h+_Keyval._hstring], r12
0x1802691b4  lea     moduleName, [rbp+57h+result]
0x1802691b8  mov     this, r15
0x1802691bb  movdqu  xmmword ptr [rbp+57h+result._Location._Parent], xmm6
0x1802691c0  mov     [rax+20h], rbx
0x1802691c4  mov     [rax+28h], r14
0x1802691c8  mov     [rax], rdi
0x1802691cb  mov     [rax+8], rdi
0x1802691cf  mov     [rax+10h], rdi
0x1802691d3  mov     [rax+18h], r12w
0x1802691d8  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVString@Internal@Windows@@PEAUILocalDependencyStorage@2DependencyLocator@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBVString@Internal@Windows@@PEAUILocalDependencyStorage@2DependencyLocator@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBVString@Internal@Windows@@PEAUILocalDependencyStorage@2DependencyLocator@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<Windows::Internal::String const,DependencyLocator::Internal::ILocalDependencyStorage *>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<Windows::Internal::String const,DependencyLocator::Internal::ILocalDependencyStorage *>,void *> *>,std::_Tree_node<std::pair<Windows::Internal::String const,DependencyLocator::Internal::ILocalDependencyStorage *>,void *> * const)
0x1802691dd  lea     this, [rbp+57h+_Keyval]; this
0x1802691e1  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1802691e6  jmp     loc_180269145
0x1802691eb  test    rbx, rbx
0x1802691ee  jz      short loc_1802691F9
0x1802691f0  mov     this, rbx; string
0x1802691f3  call    cs:__imp_WindowsDeleteString
0x1802691f9  xor     eax, eax
0x1802691fb  jmp     loc_180269097
0x180269200  mov     edi, 80004003h
0x180269205  mov     ecx, edi; failedFrameHR
0x180269207  call    OnFailure_2990_
0x18026920c  mov     ecx, edi; errorCode
0x18026920e  mov     [rbp+57h+ppStowedExceptions], rsi
0x180269212  mov     dword ptr [rbp+57h+cStowedExceptions], esi
0x180269215  call    TraceForFailFast
0x18026921a  lea     moduleName, [rbp+57h+cStowedExceptions]; pcStowedExceptions
0x18026921e  lea     this, [rbp+57h+ppStowedExceptions]; pppStowedExceptions
0x180269222  call    GetStowedExceptionsForFailFast
0x180269227  mov     pfnTelemetryProc, [rbp+57h+ppStowedExceptions]
0x18026922b  mov     ecx, edi
0x18026922d  mov     edx, dword ptr [rbp+57h+cStowedExceptions]
0x180269230  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x180269236  jmp     loc_180268F88
0x18026923b  mov     ecx, 80070490h; failedFrameHR
0x180269240  call    OnFailure_2990_
0x180269245  mov     ecx, 80070490h; errorCode
0x18026924a  mov     [rbp+57h+ppStowedExceptions], r14
0x18026924e  mov     dword ptr [rbp+57h+cStowedExceptions], r14d
0x180269252  call    TraceForFailFast
0x180269257  lea     moduleName, [rbp+57h+cStowedExceptions]; pcStowedExceptions
0x18026925b  lea     this, [rbp+57h+ppStowedExceptions]; pppStowedExceptions
0x18026925f  call    GetStowedExceptionsForFailFast
0x180269264  mov     pfnTelemetryProc, [rbp+57h+ppStowedExceptions]
0x180269268  mov     ecx, 80070490h
0x18026926d  mov     edx, dword ptr [rbp+57h+cStowedExceptions]
0x180269270  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x180269276  jmp     loc_1802690DA
0x18026927b  mov     r12d, 80070490h
0x180269281  mov     ecx, r12d; failedFrameHR
0x180269284  call    OnFailure_2990_
0x180269289  mov     ecx, r12d; errorCode
0x18026928c  mov     [rbp+57h+ppStowedExceptions], r14
0x180269290  mov     dword ptr [rbp+57h+cStowedExceptions], r14d
0x180269294  call    TraceForFailFast
0x180269299  lea     moduleName, [rbp+57h+cStowedExceptions]; pcStowedExceptions
0x18026929d  lea     this, [rbp+57h+ppStowedExceptions]; pppStowedExceptions
0x1802692a1  call    GetStowedExceptionsForFailFast
0x1802692a6  mov     pfnTelemetryProc, [rbp+57h+ppStowedExceptions]
0x1802692aa  mov     ecx, r12d
0x1802692ad  mov     edx, dword ptr [rbp+57h+cStowedExceptions]
0x1802692b0  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x1802692b6  jmp     loc_180269105
0x1802692bb  call    OnFailure_901_
0x1802692c0  mov     edi, 80004003h
0x1802692c5  mov     [rbp+57h+ppStowedExceptions], r12
0x1802692c9  mov     ecx, edi; errorCode
0x1802692cb  mov     dword ptr [rbp+57h+cStowedExceptions], r12d
0x1802692cf  call    TraceForFailFast
0x1802692d4  lea     moduleName, [rbp+57h+cStowedExceptions]; pcStowedExceptions
0x1802692d8  lea     this, [rbp+57h+ppStowedExceptions]; pppStowedExceptions
0x1802692dc  call    GetStowedExceptionsForFailFast
0x1802692e1  mov     pfnTelemetryProc, [rbp+57h+ppStowedExceptions]
0x1802692e5  mov     ecx, edi
0x1802692e7  mov     edx, dword ptr [rbp+57h+cStowedExceptions]
0x1802692ea  call    cs:__imp_?RoFailFastWithErrorContextInternal2@@YAXJKQEAPEAU_STOWED_EXCEPTION_INFORMATION_V2@@@Z; RoFailFastWithErrorContextInternal2(long,ulong,_STOWED_EXCEPTION_INFORMATION_V2 * * const)
0x1802692f0  jmp     loc_18026911C
0x1802692f5  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
```
