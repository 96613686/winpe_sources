# IAudioPlayHelper::CreateAudioHelper(std::unique_ptr<IAudioPlayHelper,std::default_delete<IAudioPlayHelper>> &)

- ea: `0x18001fce4`
- end: `0x18001ff3f`
- name: `?CreateAudioHelper@IAudioPlayHelper@@SAJAEAV?$unique_ptr@VIAudioPlayHelper@@U?$default_delete@VIAudioPlayHelper@@@std@@@std@@@Z`
- size: `603`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001cb70`

## callees

- `0x180004e9c`
- `0x18000c944`
- `0x18000c964`
- `0x18001fce4`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001fde5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001fde5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001fd92`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001fd92`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001fd75`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001fd75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fd87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fd87`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001fd9a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001fd9a`

## string_xrefs

- `0x18001fddb`: `DllGetClassObject`
- `0x18001fd52`: `onecoreuap\ds\nfc\product\semanagement\common\seeventmgr\src\audioplayhelper.cpp`
- `0x18001fdad`: `onecoreuap\ds\nfc\product\semanagement\common\seeventmgr\src\audioplayhelper.cpp`
- `0x18001fe4e`: `onecoreuap\ds\nfc\product\semanagement\common\seeventmgr\src\audioplayhelper.cpp`
- `0x18001fea3`: `onecoreuap\ds\nfc\product\semanagement\common\seeventmgr\src\audioplayhelper.cpp`
- `0x18001fed2`: `onecoreuap\ds\nfc\product\semanagement\common\seeventmgr\src\audioplayhelper.cpp`
- `0x18001fd6e`: `audioses.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall IAudioPlayHelper::CreateAudioHelper(void (__fastcall ****a1)(_QWORD, __int64))
{
  _QWORD *v2; // rdi
  int v3; // ebx
  HMODULE Library; // rsi
  const char *v5; // r9
  HMODULE v6; // r15
  DWORD LastError; // ebx
  FARPROC ProcAddress; // rax
  int v9; // eax
  void (__fastcall ***v10)(_QWORD, __int64); // rcx
  int v12; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  _QWORD *v14; // [rsp+68h] [rbp+38h] BYREF
  __int64 v15; // [rsp+70h] [rbp+40h] BYREF
  _QWORD *v16; // [rsp+78h] [rbp+48h]

  v2 = operator new(0x20u, (const struct std::nothrow_t *)std::nothrow);
  v14 = v2;
  if ( v2 )
  {
    *v2 = &AudioPlayHelper::`vftable';
    v2[1] = 0;
    v2[2] = 0;
    v2[3] = 0;
  }
  else
  {
    v2 = 0;
  }
  v16 = v2;
  if ( !v2 )
  {
    v3 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\seeventmgr\\src\\audioplayhelper.cpp",
      (const char *)0x8007000ELL,
      v12);
    return (unsigned int)v3;
  }
  Library = LoadLibraryExW(L"audioses.dll", 0, 0x800u);
  v6 = (HMODULE)v2[1];
  if ( v6 )
  {
    LastError = GetLastError();
    FreeLibrary(v6);
    SetLastError(LastError);
  }
  v2[1] = Library;
  if ( Library )
  {
    v14 = 0;
    v15 = 0;
    ProcAddress = GetProcAddress(Library, "DllGetClassObject");
    if ( ProcAddress )
    {
      v3 = ((__int64 (__fastcall *)(GUID *, GUID *, __int64 *))ProcAddress)(
             &CLSID_AudioPlayerFacade,
             &IID_IClassFactory,
             &v15);
      if ( v3 >= 0 )
      {
        v3 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, _QWORD **))(*(_QWORD *)v15 + 24LL))(
               v15,
               0,
               &GUID_4d19ad40_4049_4c52_aa2a_84e4e52e9ec2,
               &v14);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      }
      if ( v3 >= 0 )
      {
        v9 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, _QWORD *, _QWORD))(*v14 + 24LL))(
               v14,
               &GUID_81ef556b_a13d_4f0c_b88e_5eded83750f7,
               v2 + 2,
               0);
        v3 = v9;
        if ( v9 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x28,
            (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\seeventmgr\\src\\audioplayhelper.cpp",
            (const char *)(unsigned int)v9,
            v12);
          if ( v14 )
            (*(void (__fastcall **)(_QWORD *))(*v14 + 16LL))(v14);
          goto LABEL_22;
        }
        if ( v14 )
          (*(void (__fastcall **)(_QWORD *))(*v14 + 16LL))(v14);
        goto LABEL_25;
      }
    }
    else
    {
      v3 = -2147418113;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\seeventmgr\\src\\audioplayhelper.cpp",
      (const char *)(unsigned int)v3,
      v12);
    if ( v14 )
      (*(void (__fastcall **)(_QWORD *))(*v14 + 16LL))(v14);
    goto LABEL_22;
  }
  v3 = wil::details::in1diag3::Return_GetLastError(
         retaddr,
         (void *)0x21,
         (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\seeventmgr\\src\\audioplayhelper.cpp",
         v5);
  if ( v3 < 0 )
  {
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE,
      (unsigned int)"onecoreuap\\ds\\nfc\\product\\semanagement\\common\\seeventmgr\\src\\audioplayhelper.cpp",
      (const char *)(unsigned int)v3,
      v12);
    (*(void (__fastcall **)(_QWORD *, __int64))*v2)(v2, 1);
    return (unsigned int)v3;
  }
LABEL_25:
  v10 = *a1;
  *a1 = (void (__fastcall ***)(_QWORD, __int64))v2;
  if ( v10 )
    (**v10)(v10, 1);
  return 0;
}

```

## disassembly

```asm
0x18001fce4  mov     [rsp-28h+arg_0], rbx
0x18001fce9  push    rbp
0x18001fcea  push    rsi
0x18001fceb  push    rdi
0x18001fcec  push    r14
0x18001fcee  push    r15
0x18001fcf0  mov     rbp, rsp
0x18001fcf3  sub     rsp, 30h
0x18001fcf7  mov     r14, rcx
0x18001fcfa  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001fd01  mov     ecx, 20h ; ' '; unsigned __int64
0x18001fd06  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001fd0b  mov     rdi, rax
0x18001fd0e  mov     [rbp+arg_8], rax
0x18001fd12  test    rax, rax
0x18001fd15  jz      short loc_18001FD3B
0x18001fd17  lea     rax, ??_7AudioPlayHelper@@6B@; const AudioPlayHelper::`vftable'
0x18001fd1e  mov     [rdi], rax
0x18001fd21  mov     qword ptr [rdi+8], 0
0x18001fd29  mov     qword ptr [rdi+10h], 0
0x18001fd31  mov     qword ptr [rdi+18h], 0
0x18001fd39  jmp     short loc_18001FD3D
0x18001fd3b  xor     edi, edi
0x18001fd3d  mov     [rbp+arg_18], rdi
0x18001fd41  test    rdi, rdi
0x18001fd44  jnz     short loc_18001FD66
0x18001fd46  mov     rcx, [rbp+28h]; this
0x18001fd4a  mov     ebx, 8007000Eh
0x18001fd4f  mov     r9d, ebx; char *
0x18001fd52  lea     r8, aOnecoreuapDsNf_33; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x18001fd59  lea     edx, [rdi+0Ch]; void *
0x18001fd5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fd61  jmp     loc_18001FF2C
0x18001fd66  xor     edx, edx; hFile
0x18001fd68  mov     r8d, 800h; dwFlags
0x18001fd6e  lea     rcx, aAudiosesDll; "audioses.dll"
0x18001fd75  call    cs:__imp_LoadLibraryExW
0x18001fd7b  mov     rsi, rax
0x18001fd7e  mov     r15, [rdi+8]
0x18001fd82  test    r15, r15
0x18001fd85  jz      short loc_18001FDA0
0x18001fd87  call    cs:__imp_GetLastError
0x18001fd8d  mov     ebx, eax
0x18001fd8f  mov     rcx, r15; hLibModule
0x18001fd92  call    cs:__imp_FreeLibrary
0x18001fd98  mov     ecx, ebx; dwErrCode
0x18001fd9a  call    cs:__imp_SetLastError
0x18001fda0  mov     [rdi+8], rsi
0x18001fda4  test    rsi, rsi
0x18001fda7  jnz     short loc_18001FDCB
0x18001fda9  mov     rcx, [rbp+28h]; this
0x18001fdad  lea     r8, aOnecoreuapDsNf_33; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x18001fdb4  lea     edx, [rsi+21h]; void *
0x18001fdb7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001fdbc  mov     ebx, eax
0x18001fdbe  test    eax, eax
0x18001fdc0  jns     loc_18001FF0F
0x18001fdc6  jmp     loc_18001FECB
0x18001fdcb  mov     [rbp+arg_8], 0
0x18001fdd3  mov     [rbp+arg_10], 0
0x18001fddb  lea     rdx, aDllgetclassobj_0; "DllGetClassObject"
0x18001fde2  mov     rcx, rsi; hModule
0x18001fde5  call    cs:__imp_GetProcAddress
0x18001fdeb  test    rax, rax
0x18001fdee  jnz     short loc_18001FDF7
0x18001fdf0  mov     ebx, 8000FFFFh
0x18001fdf5  jmp     short loc_18001FE47
0x18001fdf7  lea     r8, [rbp+arg_10]
0x18001fdfb  lea     rdx, IID_IClassFactory
0x18001fe02  lea     rcx, CLSID_AudioPlayerFacade
0x18001fe09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe0e  mov     ebx, eax
0x18001fe10  test    eax, eax
0x18001fe12  js      short loc_18001FE43
0x18001fe14  mov     rcx, [rbp+arg_10]
0x18001fe18  mov     rax, [rcx]
0x18001fe1b  lea     r9, [rbp+arg_8]
0x18001fe1f  lea     r8, _GUID_4d19ad40_4049_4c52_aa2a_84e4e52e9ec2
0x18001fe26  xor     edx, edx
0x18001fe28  mov     rax, [rax+18h]
0x18001fe2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe31  mov     ebx, eax
0x18001fe33  mov     rcx, [rbp+arg_10]
0x18001fe37  mov     rax, [rcx]
0x18001fe3a  mov     rax, [rax+10h]
0x18001fe3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe43  test    ebx, ebx
0x18001fe45  jns     short loc_18001FE78
0x18001fe47  mov     rcx, [rbp+28h]; this
0x18001fe4b  mov     r9d, ebx; char *
0x18001fe4e  lea     r8, aOnecoreuapDsNf_33; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x18001fe55  mov     edx, 24h ; '$'; void *
0x18001fe5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fe5f  nop
0x18001fe60  mov     rcx, [rbp+arg_8]
0x18001fe64  test    rcx, rcx
0x18001fe67  jz      short loc_18001FE76
0x18001fe69  mov     rax, [rcx]
0x18001fe6c  mov     rax, [rax+10h]
0x18001fe70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe75  nop
0x18001fe76  jmp     short loc_18001FECB
0x18001fe78  mov     rcx, [rbp+arg_8]
0x18001fe7c  mov     rax, [rcx]
0x18001fe7f  lea     r8, [rdi+10h]
0x18001fe83  xor     r9d, r9d
0x18001fe86  lea     rdx, _GUID_81ef556b_a13d_4f0c_b88e_5eded83750f7
0x18001fe8d  mov     rax, [rax+18h]
0x18001fe91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fe96  mov     ebx, eax
0x18001fe98  test    eax, eax
0x18001fe9a  jns     short loc_18001FEF9
0x18001fe9c  mov     rcx, [rbp+28h]; this
0x18001fea0  mov     r9d, eax; char *
0x18001fea3  lea     r8, aOnecoreuapDsNf_33; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x18001feaa  mov     edx, 28h ; '('; void *
0x18001feaf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001feb4  nop
0x18001feb5  mov     rcx, [rbp+arg_8]
0x18001feb9  test    rcx, rcx
0x18001febc  jz      short loc_18001FECB
0x18001febe  mov     rax, [rcx]
0x18001fec1  mov     rax, [rax+10h]
0x18001fec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001feca  nop
0x18001fecb  mov     rcx, [rbp+28h]; this
0x18001fecf  mov     r9d, ebx; char *
0x18001fed2  lea     r8, aOnecoreuapDsNf_33; "onecoreuap\\ds\\nfc\\product\\semanagem"...
0x18001fed9  mov     edx, 0Eh; void *
0x18001fede  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fee3  nop
0x18001fee4  mov     rax, [rdi]
0x18001fee7  mov     edx, 1
0x18001feec  mov     rcx, rdi
0x18001feef  mov     rax, [rax]
0x18001fef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fef7  jmp     short loc_18001FF2C
0x18001fef9  mov     rcx, [rbp+arg_8]
0x18001fefd  test    rcx, rcx
0x18001ff00  jz      short loc_18001FF0F
0x18001ff02  mov     rax, [rcx]
0x18001ff05  mov     rax, [rax+10h]
0x18001ff09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff0e  nop
0x18001ff0f  mov     rcx, [r14]
0x18001ff12  mov     [r14], rdi
0x18001ff15  test    rcx, rcx
0x18001ff18  jz      short loc_18001FF2A
0x18001ff1a  mov     rax, [rcx]
0x18001ff1d  mov     edx, 1
0x18001ff22  mov     rax, [rax]
0x18001ff25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ff2a  xor     ebx, ebx
0x18001ff2c  mov     eax, ebx
0x18001ff2e  mov     rbx, [rsp+30h+arg_0]
0x18001ff33  add     rsp, 30h
0x18001ff37  pop     r15
0x18001ff39  pop     r14
0x18001ff3b  pop     rdi
0x18001ff3c  pop     rsi
0x18001ff3d  pop     rbp
0x18001ff3e  retn
```
