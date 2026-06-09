# LoadModuleWithFailureDiagnosis

- ea: `0x1800061a8`
- end: `0x180006359`
- name: `LoadModuleWithFailureDiagnosis`
- size: `433`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x180006140`
- `0x1800061a8`

## callees

- `0x180001f8b`
- `0x1800060c0`
- `0x1800060cc`
- `0x180006104`
- `0x1800061a8`
- `0x180006956`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800061c5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800061c5`
- `imagehlp!ImageDirectoryEntryToData` at `0x180006233`
- `imagehlp!ImageDirectoryEntryToData` at `0x180006233`
- `imagehlp!UnMapAndLoad` at `0x1800062a6`
- `imagehlp!UnMapAndLoad` at `0x1800062a6`
- `imagehlp!ImageRvaToVa` at `0x18000626d`
- `imagehlp!ImageRvaToVa` at `0x18000626d`
- `imagehlp!ImageNtHeader` at `0x180006259`
- `imagehlp!ImageNtHeader` at `0x180006259`
- `imagehlp!MapAndLoad` at `0x180006208`
- `imagehlp!MapAndLoad` at `0x180006208`

## pseudocode

```c
HMODULE __fastcall LoadModuleWithFailureDiagnosis(const CHAR *a1)
{
  HMODULE result; // rax
  signed int LastError_0; // eax
  _DWORD *v4; // rax
  _DWORD *v5; // rdi
  ULONG v6; // ebx
  struct _IMAGE_NT_HEADERS64 *v7; // rax
  PVOID v8; // rax
  signed int v9; // eax
  unsigned int v10; // eax
  unsigned int v11; // eax
  _LOADED_IMAGE LoadedImage; // [rsp+30h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  ULONG Size; // [rsp+A8h] [rbp+10h] BYREF

  result = LoadLibraryExA(a1, 0, 0x800u);
  if ( !result )
  {
    LastError_0 = GetLastError_0();
    if ( LastError_0 == 126 )
    {
      memset_0(&LoadedImage, 0, sizeof(LoadedImage));
      if ( MapAndLoad(a1, 0, &LoadedImage, 1, 1) )
      {
        Size = 0;
        v4 = ImageDirectoryEntryToData(LoadedImage.MappedAddress, 0, 1u, &Size);
        v5 = v4;
        if ( v4 && Size && v4[3] )
        {
          do
          {
            v6 = v5[3];
            v7 = ImageNtHeader(LoadedImage.MappedAddress);
            v8 = ImageRvaToVa(v7, LoadedImage.MappedAddress, v6, 0);
            if ( v8 )
              LoadModuleWithFailureDiagnosis(v8);
            v5 += 5;
          }
          while ( v5[3] );
        }
        UnMapAndLoad(&LoadedImage);
        wil::details::in1diag3::FailFast_UnexpectedMsg(
          retaddr,
          (void *)0x2F,
          (unsigned int)"onecoreuap\\inetcore\\lib\\isolation\\isoforwarder\\initonceimplementation.cpp",
          "%hs",
          a1);
      }
      v9 = GetLastError_0();
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
      v10 = wil::verify_hresult<long>((unsigned int)v9);
      wil::details::in1diag3::FailFast_HrMsg(
        retaddr,
        (void *)0x33,
        (unsigned int)"onecoreuap\\inetcore\\lib\\isolation\\isoforwarder\\initonceimplementation.cpp",
        (const char *)v10,
        (int)"%hs",
        a1);
    }
    if ( LastError_0 > 0 )
      LastError_0 = (unsigned __int16)LastError_0 | 0x80070000;
    v11 = wil::verify_hresult<long>((unsigned int)LastError_0);
    wil::details::in1diag3::FailFast_HrMsg(
      retaddr,
      (void *)0x38,
      (unsigned int)"onecoreuap\\inetcore\\lib\\isolation\\isoforwarder\\initonceimplementation.cpp",
      (const char *)v11,
      (int)"%hs",
      a1);
  }
  return result;
}

```

## disassembly

```asm
0x1800061a8  mov     [rsp+arg_0], rbx
0x1800061ad  mov     [rsp+arg_10], rsi
0x1800061b2  push    rdi
0x1800061b3  sub     rsp, 90h
0x1800061ba  xor     edx, edx; hFile
0x1800061bc  mov     r8d, 800h; dwFlags
0x1800061c2  mov     rsi, rcx
0x1800061c5  call    cs:__imp_LoadLibraryExA
0x1800061cb  test    rax, rax
0x1800061ce  jnz     loc_18000628C
0x1800061d4  call    GetLastError_0
0x1800061d9  cmp     eax, 7Eh ; '~'
0x1800061dc  jnz     loc_180006318
0x1800061e2  xor     edx, edx; Val
0x1800061e4  lea     r8d, [rax-26h]; Size
0x1800061e8  lea     rcx, [rsp+98h+LoadedImage]; void *
0x1800061ed  call    memset_0
0x1800061f2  mov     ebx, 1
0x1800061f7  lea     r8, [rsp+98h+LoadedImage]; LoadedImage
0x1800061fc  mov     r9d, ebx; DotDll
0x1800061ff  mov     [rsp+98h+ReadOnly], ebx; ReadOnly
0x180006203  xor     edx, edx; DllPath
0x180006205  mov     rcx, rsi; ImageName
0x180006208  call    cs:__imp_MapAndLoad
0x18000620e  test    eax, eax
0x180006210  jz      loc_1800062D2
0x180006216  mov     rcx, [rsp+98h+LoadedImage.MappedAddress]; Base
0x18000621b  lea     r9, [rsp+98h+Size]; Size
0x180006223  mov     r8d, ebx; DirectoryEntry
0x180006226  mov     [rsp+98h+Size], 0
0x180006231  xor     edx, edx; MappedAsImage
0x180006233  call    cs:__imp_ImageDirectoryEntryToData
0x180006239  mov     rdi, rax
0x18000623c  test    rax, rax
0x18000623f  jz      short loc_1800062A1
0x180006241  cmp     [rsp+98h+Size], 0
0x180006249  jz      short loc_1800062A1
0x18000624b  cmp     dword ptr [rax+0Ch], 0
0x18000624f  jz      short loc_1800062A1
0x180006251  mov     rcx, [rsp+98h+LoadedImage.MappedAddress]; Base
0x180006256  mov     ebx, [rdi+0Ch]
0x180006259  call    cs:__imp_ImageNtHeader
0x18000625f  mov     rdx, [rsp+98h+LoadedImage.MappedAddress]; Base
0x180006264  xor     r9d, r9d; LastRvaSection
0x180006267  mov     rcx, rax; NtHeaders
0x18000626a  mov     r8d, ebx; Rva
0x18000626d  call    cs:__imp_ImageRvaToVa
0x180006273  test    rax, rax
0x180006276  jz      short loc_180006280
0x180006278  mov     rcx, rax
0x18000627b  call    LoadModuleWithFailureDiagnosis
0x180006280  add     rdi, 14h
0x180006284  cmp     dword ptr [rdi+0Ch], 0
0x180006288  jz      short loc_1800062A1
0x18000628a  jmp     short loc_180006251
0x18000628c  lea     r11, [rsp+98h+var_8]
0x180006294  mov     rbx, [r11+10h]
0x180006298  mov     rsi, [r11+20h]
0x18000629c  mov     rsp, r11
0x18000629f  pop     rdi
0x1800062a0  retn
0x1800062a1  lea     rcx, [rsp+98h+LoadedImage]; LoadedImage
0x1800062a6  call    cs:__imp_UnMapAndLoad
0x1800062ac  mov     rcx, [rsp+98h]; this
0x1800062b4  lea     r9, aHs; "%hs"
0x1800062bb  lea     r8, aOnecoreuapInet; "onecoreuap\\inetcore\\lib\\isolation\\i"...
0x1800062c2  mov     qword ptr [rsp+98h+ReadOnly], rsi; char *
0x1800062c7  mov     edx, 2Fh ; '/'; void *
0x1800062cc  call    ?FailFast_UnexpectedMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::FailFast_UnexpectedMsg(void *,uint,char const *,char const *,...)
0x1800062d2  call    GetLastError_0
0x1800062d7  test    eax, eax
0x1800062d9  jle     short loc_1800062E3
0x1800062db  movzx   eax, ax
0x1800062de  or      eax, 80070000h
0x1800062e3  mov     ecx, eax
0x1800062e5  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800062ea  mov     rcx, [rsp+98h]; this
0x1800062f2  lea     r8, aOnecoreuapInet; "onecoreuap\\inetcore\\lib\\isolation\\i"...
0x1800062f9  mov     r9d, eax; char *
0x1800062fc  mov     [rsp+98h+var_70], rsi; char *
0x180006301  lea     rax, aHs; "%hs"
0x180006308  mov     edx, 33h ; '3'; void *
0x18000630d  mov     qword ptr [rsp+98h+ReadOnly], rax; int
0x180006312  call    ?FailFast_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::FailFast_HrMsg(void *,uint,char const *,long,char const *,...)
0x180006318  test    eax, eax
0x18000631a  jle     short loc_180006324
0x18000631c  movzx   eax, ax
0x18000631f  or      eax, 80070000h
0x180006324  mov     ecx, eax
0x180006326  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18000632b  mov     rcx, [rsp+98h]; this
0x180006333  lea     r8, aOnecoreuapInet; "onecoreuap\\inetcore\\lib\\isolation\\i"...
0x18000633a  mov     r9d, eax; char *
0x18000633d  mov     [rsp+98h+var_70], rsi; char *
0x180006342  lea     rax, aHs; "%hs"
0x180006349  mov     edx, 38h ; '8'; void *
0x18000634e  mov     qword ptr [rsp+98h+ReadOnly], rax; int
0x180006353  call    ?FailFast_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::FailFast_HrMsg(void *,uint,char const *,long,char const *,...)
```
