# SetErrorInfoInternal(ulong,...)

- ea: `0x180096f34`
- end: `0x180097270`
- name: `?SetErrorInfoInternal@@YAJKZZ`
- size: `828`
- prototype: `__int64(unsigned int, ...)`
- caller_count: `13`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003a344`
- `0x18003a4a0`
- `0x18003afbc`
- `0x18003d3d0`
- `0x180096048`
- `0x1800961b8`
- `0x1800963dc`
- `0x1800965d0`
- `0x1800967b0`
- `0x1800968c4`
- `0x180096a00`
- `0x180096b04`
- `0x180096c30`

## callees

- `0x180005eb8`
- `0x1800133fc`
- `0x180071f50`
- `0x180078454`
- `0x180096f34`
- `0x180097278`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009702f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180097075`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800970ed`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180097150`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800971c8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180097229`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180097257`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009702f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180097075`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800970ed`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180097150`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800971c8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180097229`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180097257`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180096f68`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180096f68`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180096fe4`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180096fe4`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800971e0`
- `OLEAUT32!__imp_SetErrorInfo` at `0x1800971e0`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x1800970a4`
- `OLEAUT32!__imp_CreateErrorInfo` at `0x1800970a4`

## string_xrefs

- `0x180096f61`: `AppxPackaging.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 SetErrorInfoInternal(DWORD a1, ...)
{
  Common *v1; // rcx
  HMODULE Library; // rsi
  int HResultFromLastError; // eax
  unsigned int v4; // ebx
  DWORD v5; // eax
  Common *v6; // rcx
  int v7; // eax
  void *v8; // rdx
  int v9; // eax
  HRESULT v10; // eax
  void *v11; // rdx
  int v12; // eax
  void *v13; // rdx
  ICreateErrorInfo *v14; // rbx
  HRESULT (__stdcall *QueryInterface)(ICreateErrorInfo *, const IID *const, void **); // rdi
  int v16; // eax
  void *v17; // rdx
  HRESULT v18; // eax
  void *v19; // rdx
  int lpBuffer; // [rsp+20h] [rbp-58h]
  int lpBuffera; // [rsp+20h] [rbp-58h]
  WCHAR Buffer[4]; // [rsp+40h] [rbp-38h] BYREF
  ICreateErrorInfo *pperrinfo; // [rsp+48h] [rbp-30h] BYREF
  IErrorInfo *perrinfo; // [rsp+50h] [rbp-28h] BYREF
  va_list Arguments[4]; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]
  __int64 v29; // [rsp+A8h] [rbp+30h] BYREF
  va_list va; // [rsp+A8h] [rbp+30h]
  va_list va1; // [rsp+B0h] [rbp+38h] BYREF

  va_start(va1, a1);
  va_start(va, a1);
  v29 = va_arg(va1, _QWORD);
  Arguments[1] = (va_list)-2LL;
  Library = LoadLibraryExW(L"AppxPackaging.dll", 0, 0x802u);
  if ( !Library )
  {
    HResultFromLastError = Common::GetHResultFromLastError(v1);
    v4 = HResultFromLastError;
    if ( HResultFromLastError < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x32,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\errorinfo.cpp",
        (const char *)(unsigned int)HResultFromLastError,
        lpBuffer);
    return v4;
  }
  *(_QWORD *)Buffer = 0;
  va_copy((va_list)Arguments, va);
  v5 = FormatMessageW(0x900u, Library, a1, 0, Buffer, 0, Arguments);
  Arguments[0] = 0;
  if ( !*(_QWORD *)Buffer )
  {
    v7 = Common::GetHResultFromLastError(v6);
    v4 = v7;
    if ( v7 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x41,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\errorinfo.cpp",
        (const char *)(unsigned int)v7,
        lpBuffera);
LABEL_8:
    Common::AutoHandleFreeHLocal(*(Common **)Buffer, v8);
    FreeLibrary(Library);
    return v4;
  }
  if ( !v5 )
  {
    v9 = Common::GetHResultFromLastError(v6);
    v4 = v9;
    if ( v9 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x42,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\errorinfo.cpp",
        (const char *)(unsigned int)v9,
        lpBuffera);
    goto LABEL_8;
  }
  pperrinfo = 0;
  perrinfo = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&pperrinfo);
  v10 = CreateErrorInfo(&pperrinfo);
  v4 = v10;
  if ( v10 >= 0 )
  {
    v12 = ((__int64 (__fastcall *)(ICreateErrorInfo *, _QWORD))pperrinfo->lpVtbl->SetDescription)(
            pperrinfo,
            *(_QWORD *)Buffer);
    v4 = v12;
    if ( v12 >= 0 )
    {
      v14 = pperrinfo;
      QueryInterface = pperrinfo->lpVtbl->QueryInterface;
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&perrinfo);
      v16 = ((__int64 (__fastcall *)(ICreateErrorInfo *, GUID *, IErrorInfo **))QueryInterface)(
              v14,
              &GUID_1cf2b120_547d_101b_8e65_08002b2bd119,
              &perrinfo);
      v4 = v16;
      if ( v16 >= 0 )
      {
        v18 = SetErrorInfo(0, perrinfo);
        v4 = v18;
        if ( v18 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x4A,
            (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\errorinfo.cpp",
            (const char *)(unsigned int)v18,
            lpBuffera);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&perrinfo);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&pperrinfo);
        Common::AutoHandleFreeHLocal(*(Common **)Buffer, v19);
        FreeLibrary(Library);
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x49,
          (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\errorinfo.cpp",
          (const char *)(unsigned int)v16,
          lpBuffera);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&perrinfo);
        Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&pperrinfo);
        Common::AutoHandleFreeHLocal(*(Common **)Buffer, v17);
        FreeLibrary(Library);
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x48,
        (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\errorinfo.cpp",
        (const char *)(unsigned int)v12,
        lpBuffera);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&perrinfo);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&pperrinfo);
      Common::AutoHandleFreeHLocal(*(Common **)Buffer, v13);
      FreeLibrary(Library);
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\errorinfo.cpp",
      (const char *)(unsigned int)v10,
      lpBuffera);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&perrinfo);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&pperrinfo);
    Common::AutoHandleFreeHLocal(*(Common **)Buffer, v11);
    FreeLibrary(Library);
  }
  return v4;
}

```

## disassembly

```asm
0x180096f34  mov     rax, rsp
0x180096f37  mov     [rax+8], ecx
0x180096f3a  mov     [rax+10h], rdx
0x180096f3e  mov     [rax+18h], r8
0x180096f42  mov     [rax+20h], r9
0x180096f46  push    rbp
0x180096f47  push    rbx
0x180096f48  push    rsi
0x180096f49  push    rdi
0x180096f4a  mov     rbp, rsp
0x180096f4d  sub     rsp, 78h
0x180096f51  mov     [rbp+var_18], 0FFFFFFFFFFFFFFFEh
0x180096f59  xor     edx, edx; hFile
0x180096f5b  mov     r8d, 802h; dwFlags
0x180096f61  lea     rcx, LibFileName; "AppxPackaging.dll"
0x180096f68  call    cs:__imp_LoadLibraryExW
0x180096f6f  nop     dword ptr [rax+rax+00h]
0x180096f74  mov     rsi, rax
0x180096f77  test    rax, rax
0x180096f7a  jnz     short loc_180096FA3
0x180096f7c  call    ?GetHResultFromLastError@Common@@YAJXZ; Common::GetHResultFromLastError(void)
0x180096f81  mov     ebx, eax
0x180096f83  test    eax, eax
0x180096f85  jns     short loc_180096F9E
0x180096f87  mov     rcx, [rbp+20h]; this
0x180096f8b  mov     r9d, eax; char *
0x180096f8e  lea     r8, aOnecorePrintsc_161; "onecore\\printscan\\appxpackaging\\lib"...
0x180096f95  lea     edx, [rsi+32h]; void *
0x180096f98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180096f9d  nop
0x180096f9e  jmp     loc_180097264
0x180096fa3  mov     qword ptr [rbp+Buffer], 0
0x180096fab  mov     [rbp+var_20], 0
0x180096fb3  lea     rax, [rbp+arg_8]
0x180096fb7  mov     [rbp+var_20], rax
0x180096fbb  lea     rax, [rbp+var_20]
0x180096fbf  mov     [rsp+78h+Arguments], rax; Arguments
0x180096fc4  mov     [rsp+78h+nSize], 0; nSize
0x180096fcc  lea     rax, [rbp+Buffer]
0x180096fd0  mov     [rsp+78h+lpBuffer], rax; int
0x180096fd5  xor     r9d, r9d; dwLanguageId
0x180096fd8  mov     r8d, [rbp+dwMessageId]; dwMessageId
0x180096fdc  mov     rdx, rsi; lpSource
0x180096fdf  mov     ecx, 900h; dwFlags
0x180096fe4  call    cs:__imp_FormatMessageW
0x180096feb  nop     dword ptr [rax+rax+00h]
0x180096ff0  mov     [rbp+var_20], 0
0x180096ff8  cmp     qword ptr [rbp+Buffer], 0
0x180096ffd  jnz     short loc_180097041
0x180096fff  call    ?GetHResultFromLastError@Common@@YAJXZ; Common::GetHResultFromLastError(void)
0x180097004  mov     ebx, eax
0x180097006  test    eax, eax
0x180097008  jns     short loc_180097022
0x18009700a  mov     rcx, [rbp+20h]; this
0x18009700e  mov     r9d, eax; char *
0x180097011  lea     r8, aOnecorePrintsc_161; "onecore\\printscan\\appxpackaging\\lib"...
0x180097018  mov     edx, 41h ; 'A'; void *
0x18009701d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180097022  mov     rcx, qword ptr [rbp+Buffer]; this
0x180097026  call    ?AutoHandleFreeHLocal@Common@@YAXPEAX@Z; Common::AutoHandleFreeHLocal(void *)
0x18009702b  nop
0x18009702c  mov     rcx, rsi; hLibModule
0x18009702f  call    cs:__imp_FreeLibrary
0x180097036  nop     dword ptr [rax+rax+00h]
0x18009703b  nop
0x18009703c  jmp     loc_180097264
0x180097041  test    eax, eax
0x180097043  jnz     short loc_180097087
0x180097045  call    ?GetHResultFromLastError@Common@@YAJXZ; Common::GetHResultFromLastError(void)
0x18009704a  mov     ebx, eax
0x18009704c  test    eax, eax
0x18009704e  jns     short loc_180097068
0x180097050  mov     rcx, [rbp+20h]; this
0x180097054  mov     r9d, eax; char *
0x180097057  lea     r8, aOnecorePrintsc_161; "onecore\\printscan\\appxpackaging\\lib"...
0x18009705e  mov     edx, 42h ; 'B'; void *
0x180097063  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180097068  mov     rcx, qword ptr [rbp+Buffer]; this
0x18009706c  call    ?AutoHandleFreeHLocal@Common@@YAXPEAX@Z; Common::AutoHandleFreeHLocal(void *)
0x180097071  nop
0x180097072  mov     rcx, rsi; hLibModule
0x180097075  call    cs:__imp_FreeLibrary
0x18009707c  nop     dword ptr [rax+rax+00h]
0x180097081  nop
0x180097082  jmp     loc_180097264
0x180097087  mov     [rbp+pperrinfo], 0
0x18009708f  mov     [rbp+perrinfo], 0
0x180097097  lea     rcx, [rbp+pperrinfo]
0x18009709b  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800970a0  lea     rcx, [rbp+pperrinfo]; pperrinfo
0x1800970a4  call    cs:__imp_CreateErrorInfo
0x1800970ab  nop     dword ptr [rax+rax+00h]
0x1800970b0  mov     ebx, eax
0x1800970b2  mov     rcx, [rbp+20h]; this
0x1800970b6  test    eax, eax
0x1800970b8  jns     short loc_1800970FF
0x1800970ba  mov     r9d, eax; char *
0x1800970bd  lea     r8, aOnecorePrintsc_161; "onecore\\printscan\\appxpackaging\\lib"...
0x1800970c4  mov     edx, 47h ; 'G'; void *
0x1800970c9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800970ce  lea     rcx, [rbp+perrinfo]
0x1800970d2  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800970d7  lea     rcx, [rbp+pperrinfo]
0x1800970db  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800970e0  mov     rcx, qword ptr [rbp+Buffer]; this
0x1800970e4  call    ?AutoHandleFreeHLocal@Common@@YAXPEAX@Z; Common::AutoHandleFreeHLocal(void *)
0x1800970e9  nop
0x1800970ea  mov     rcx, rsi; hLibModule
0x1800970ed  call    cs:__imp_FreeLibrary
0x1800970f4  nop     dword ptr [rax+rax+00h]
0x1800970f9  nop
0x1800970fa  jmp     loc_180097264
0x1800970ff  mov     rcx, [rbp+pperrinfo]
0x180097103  mov     rax, [rcx]
0x180097106  mov     rdx, qword ptr [rbp+Buffer]
0x18009710a  mov     rax, [rax+28h]
0x18009710e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097113  mov     ebx, eax
0x180097115  mov     rcx, [rbp+20h]; this
0x180097119  test    eax, eax
0x18009711b  jns     short loc_180097162
0x18009711d  mov     r9d, eax; char *
0x180097120  lea     r8, aOnecorePrintsc_161; "onecore\\printscan\\appxpackaging\\lib"...
0x180097127  mov     edx, 48h ; 'H'; void *
0x18009712c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180097131  lea     rcx, [rbp+perrinfo]
0x180097135  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18009713a  lea     rcx, [rbp+pperrinfo]
0x18009713e  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180097143  mov     rcx, qword ptr [rbp+Buffer]; this
0x180097147  call    ?AutoHandleFreeHLocal@Common@@YAXPEAX@Z; Common::AutoHandleFreeHLocal(void *)
0x18009714c  nop
0x18009714d  mov     rcx, rsi; hLibModule
0x180097150  call    cs:__imp_FreeLibrary
0x180097157  nop     dword ptr [rax+rax+00h]
0x18009715c  nop
0x18009715d  jmp     loc_180097264
0x180097162  mov     rbx, [rbp+pperrinfo]
0x180097166  mov     rax, [rbx]
0x180097169  mov     rdi, [rax]
0x18009716c  lea     rcx, [rbp+perrinfo]
0x180097170  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180097175  lea     r8, [rbp+perrinfo]
0x180097179  lea     rdx, _GUID_1cf2b120_547d_101b_8e65_08002b2bd119
0x180097180  mov     rcx, rbx
0x180097183  mov     rax, rdi
0x180097186  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009718b  mov     ebx, eax
0x18009718d  mov     rcx, [rbp+20h]; this
0x180097191  test    eax, eax
0x180097193  jns     short loc_1800971DA
0x180097195  mov     r9d, eax; char *
0x180097198  lea     r8, aOnecorePrintsc_161; "onecore\\printscan\\appxpackaging\\lib"...
0x18009719f  mov     edx, 49h ; 'I'; void *
0x1800971a4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800971a9  lea     rcx, [rbp+perrinfo]
0x1800971ad  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800971b2  lea     rcx, [rbp+pperrinfo]
0x1800971b6  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800971bb  mov     rcx, qword ptr [rbp+Buffer]; this
0x1800971bf  call    ?AutoHandleFreeHLocal@Common@@YAXPEAX@Z; Common::AutoHandleFreeHLocal(void *)
0x1800971c4  nop
0x1800971c5  mov     rcx, rsi; hLibModule
0x1800971c8  call    cs:__imp_FreeLibrary
0x1800971cf  nop     dword ptr [rax+rax+00h]
0x1800971d4  nop
0x1800971d5  jmp     loc_180097264
0x1800971da  mov     rdx, [rbp+perrinfo]; perrinfo
0x1800971de  xor     ecx, ecx; dwReserved
0x1800971e0  call    cs:__imp_SetErrorInfo
0x1800971e7  nop     dword ptr [rax+rax+00h]
0x1800971ec  mov     ebx, eax
0x1800971ee  mov     rcx, [rbp+20h]; this
0x1800971f2  test    eax, eax
0x1800971f4  jns     short loc_180097238
0x1800971f6  mov     r9d, eax; char *
0x1800971f9  lea     r8, aOnecorePrintsc_161; "onecore\\printscan\\appxpackaging\\lib"...
0x180097200  mov     edx, 4Ah ; 'J'; void *
0x180097205  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18009720a  lea     rcx, [rbp+perrinfo]
0x18009720e  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180097213  lea     rcx, [rbp+pperrinfo]
0x180097217  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18009721c  mov     rcx, qword ptr [rbp+Buffer]; this
0x180097220  call    ?AutoHandleFreeHLocal@Common@@YAXPEAX@Z; Common::AutoHandleFreeHLocal(void *)
0x180097225  nop
0x180097226  mov     rcx, rsi; hLibModule
0x180097229  call    cs:__imp_FreeLibrary
0x180097230  nop     dword ptr [rax+rax+00h]
0x180097235  nop
0x180097236  jmp     short loc_180097264
0x180097238  lea     rcx, [rbp+perrinfo]
0x18009723c  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x180097241  lea     rcx, [rbp+pperrinfo]
0x180097245  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x18009724a  mov     rcx, qword ptr [rbp+Buffer]; this
0x18009724e  call    ?AutoHandleFreeHLocal@Common@@YAXPEAX@Z; Common::AutoHandleFreeHLocal(void *)
0x180097253  nop
0x180097254  mov     rcx, rsi; hLibModule
0x180097257  call    cs:__imp_FreeLibrary
0x18009725e  nop     dword ptr [rax+rax+00h]
0x180097263  nop
0x180097264  mov     eax, ebx
0x180097266  add     rsp, 78h
0x18009726a  pop     rdi
0x18009726b  pop     rsi
0x18009726c  pop     rbx
0x18009726d  pop     rbp
0x18009726e  retn
```
