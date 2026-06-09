# RDP::AI::MachineLearning::Details::GetActivationFactory(ushort const *,_GUID const &,void * *)

- ea: `0x1800e9a28`
- end: `0x1800e9b59`
- name: `?GetActivationFactory@Details@MachineLearning@AI@RDP@@YAJPEBGAEBU_GUID@@PEAPEAX@Z`
- size: `305`
- prototype: `__int64 __fastcall(PCWSTR sourceString, const unsigned __int16 *, const struct _GUID *, void **)`
- caller_count: `5`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800e825c`
- `0x1800e9fa0`
- `0x1800ea0e8`
- `0x1800ea200`
- `0x1800ea3ec`

## callees

- `0x18007e9e0`
- `0x1800e87f4`
- `0x1800e9a28`
- `0x18019c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e9a6f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e9a6f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800e9a98`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800e9add`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800e9a98`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800e9add`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800e9a5c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800e9a5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e9a80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e9a80`

## string_xrefs

- `0x1800e9a55`: `windows.ai.machinelearning.dll`
- `0x1800e9a65`: `DllGetActivationFactory`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RDP::AI::MachineLearning::Details::GetActivationFactory(
        PCWSTR sourceString,
        const unsigned __int16 *a2,
        const struct _GUID *a3,
        void **a4)
{
  HMODULE Library; // rdi
  FARPROC ProcAddress; // rsi
  signed int LastError; // eax
  signed int v10; // ebx
  __int64 v11; // r8
  __int64 v12; // rax
  __int64 (__fastcall ***v13)(_QWORD, const unsigned __int16 *, const struct _GUID *); // rcx
  __int64 (__fastcall ***v14)(_QWORD, const unsigned __int16 *, const struct _GUID *); // rcx
  __int64 (__fastcall ***v16)(_QWORD, const unsigned __int16 *, const struct _GUID *); // [rsp+20h] [rbp-58h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-50h] BYREF

  Library = LoadLibraryExW(L"windows.ai.machinelearning.dll", 0, 0);
  ProcAddress = GetProcAddress(Library, "DllGetActivationFactory");
  if ( ProcAddress )
  {
    v16 = 0;
    v11 = -1;
    do
      ++v11;
    while ( sourceString[v11] );
    v12 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, sourceString, v11);
    v10 = ((__int64 (__fastcall *)(_QWORD, __int64 (__fastcall ****)(_QWORD, const unsigned __int16 *, const struct _GUID *)))ProcAddress)(
            *(_QWORD *)(v12 + 24),
            &v16);
    if ( v10 >= 0 )
    {
      v10 = (**v16)(v16, a2, a3);
      v14 = v16;
      if ( v16 )
      {
        v16 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, const unsigned __int16 *, const struct _GUID *)))(*v14)[2])(v14);
      }
    }
    else
    {
      FreeLibrary(Library);
      v13 = v16;
      if ( v16 )
      {
        v16 = 0;
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, const unsigned __int16 *, const struct _GUID *)))(*v13)[2])(v13);
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
    FreeLibrary(Library);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800e9a28  mov     [rsp+arg_18], rbx
0x1800e9a2d  push    rbp
0x1800e9a2e  push    rsi
0x1800e9a2f  push    rdi
0x1800e9a30  push    r14
0x1800e9a32  push    r15
0x1800e9a34  sub     rsp, 50h
0x1800e9a38  mov     rax, cs:__security_cookie
0x1800e9a3f  xor     rax, rsp
0x1800e9a42  mov     [rsp+78h+var_30], rax
0x1800e9a47  mov     r14, r8
0x1800e9a4a  mov     rbp, rdx
0x1800e9a4d  mov     rbx, rcx
0x1800e9a50  xor     r8d, r8d; dwFlags
0x1800e9a53  xor     edx, edx; hFile
0x1800e9a55  lea     rcx, ?MachineLearningDll@Details@MachineLearning@AI@RDP@@3QBGB; "windows.ai.machinelearning.dll"
0x1800e9a5c  call    cs:__imp_LoadLibraryExW
0x1800e9a62  mov     rdi, rax
0x1800e9a65  lea     rdx, aDllgetactivati; "DllGetActivationFactory"
0x1800e9a6c  mov     rcx, rax; hModule
0x1800e9a6f  call    cs:__imp_GetProcAddress
0x1800e9a75  mov     rsi, rax
0x1800e9a78  xor     r15d, r15d
0x1800e9a7b  test    rax, rax
0x1800e9a7e  jnz     short loc_1800E9AA3
0x1800e9a80  call    cs:__imp_GetLastError
0x1800e9a86  mov     ebx, eax
0x1800e9a88  test    eax, eax
0x1800e9a8a  jle     short loc_1800E9A95
0x1800e9a8c  movzx   ebx, ax
0x1800e9a8f  or      ebx, 80070000h
0x1800e9a95  mov     rcx, rdi; hLibModule
0x1800e9a98  call    cs:__imp_FreeLibrary
0x1800e9a9e  jmp     loc_1800E9B36
0x1800e9aa3  mov     [rsp+78h+var_58], r15
0x1800e9aa8  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800e9aac  inc     r8; unsigned int
0x1800e9aaf  cmp     [rbx+r8*2], r15w
0x1800e9ab4  jnz     short loc_1800E9AAC
0x1800e9ab6  mov     rdx, rbx; sourceString
0x1800e9ab9  lea     rcx, [rsp+78h+hstringHeader]; hstringHeader
0x1800e9abe  call    ??0HStringReference@Wrappers@WRL@Microsoft@@QEAA@PEBGI@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const *,uint)
0x1800e9ac3  lea     rdx, [rsp+78h+var_58]
0x1800e9ac8  mov     rcx, [rax+18h]
0x1800e9acc  mov     rax, rsi
0x1800e9acf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9ad4  mov     ebx, eax
0x1800e9ad6  test    eax, eax
0x1800e9ad8  jns     short loc_1800E9B02
0x1800e9ada  mov     rcx, rdi; hLibModule
0x1800e9add  call    cs:__imp_FreeLibrary
0x1800e9ae3  nop
0x1800e9ae4  mov     rcx, [rsp+78h+var_58]
0x1800e9ae9  test    rcx, rcx
0x1800e9aec  jz      short loc_1800E9B00
0x1800e9aee  mov     [rsp+78h+var_58], r15
0x1800e9af3  mov     rdx, [rcx]
0x1800e9af6  mov     rax, [rdx+10h]
0x1800e9afa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9aff  nop
0x1800e9b00  jmp     short loc_1800E9B36
0x1800e9b02  mov     rcx, [rsp+78h+var_58]
0x1800e9b07  mov     rax, [rcx]
0x1800e9b0a  mov     r8, r14
0x1800e9b0d  mov     rdx, rbp
0x1800e9b10  mov     rax, [rax]
0x1800e9b13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9b18  mov     ebx, eax
0x1800e9b1a  mov     rcx, [rsp+78h+var_58]
0x1800e9b1f  test    rcx, rcx
0x1800e9b22  jz      short loc_1800E9B36
0x1800e9b24  mov     [rsp+78h+var_58], r15
0x1800e9b29  mov     rdx, [rcx]
0x1800e9b2c  mov     rax, [rdx+10h]
0x1800e9b30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e9b35  nop
0x1800e9b36  mov     eax, ebx
0x1800e9b38  mov     rcx, [rsp+78h+var_30]
0x1800e9b3d  xor     rcx, rsp; StackCookie
0x1800e9b40  call    __security_check_cookie
0x1800e9b45  mov     rbx, [rsp+78h+arg_18]
0x1800e9b4d  add     rsp, 50h
0x1800e9b51  pop     r15
0x1800e9b53  pop     r14
0x1800e9b55  pop     rdi
0x1800e9b56  pop     rsi
0x1800e9b57  pop     rbp
0x1800e9b58  retn
```
