# GEN_PROJECT::WriteOldBinary(IStorage *,char *,ushort)

- ea: `0x18016ab08`
- end: `0x18016ad1f`
- name: `?WriteOldBinary@GEN_PROJECT@@QEAAJPEAUIStorage@@PEADG@Z`
- size: `535`
- prototype: `__int64 __fastcall(GEN_PROJECT *__hidden this, struct IStorage *, char *, unsigned __int16)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18011fad8`

## callees

- `0x180024478`
- `0x18016ab08`
- `0x18017072c`
- `0x180174f88`
- `0x180379520`

## import_xrefs

- `MSVCR100!_mbscat_s` at `0x18016abdd`
- `MSVCR100!_mbscat_s` at `0x18016abf4`
- `MSVCR100!_mbscat_s` at `0x18016abdd`
- `MSVCR100!_mbscat_s` at `0x18016abf4`
- `MSVCR100!_mbscpy_s` at `0x18016abc2`
- `MSVCR100!_mbscpy_s` at `0x18016abc2`
- `MSVCR100!_splitpath_s` at `0x18016abaa`
- `MSVCR100!_splitpath_s` at `0x18016abaa`
- `KERNEL32!GetModuleFileNameA` at `0x18016ab54`
- `KERNEL32!GetModuleFileNameA` at `0x18016ab54`
- `KERNEL32!FreeLibrary` at `0x18016ad00`
- `KERNEL32!FreeLibrary` at `0x18016ad00`
- `KERNEL32!GetProcAddress` at `0x18016ac32`
- `KERNEL32!GetProcAddress` at `0x18016ac32`
- `ole32!StgCreateDocfile` at `0x18016ac66`
- `ole32!StgCreateDocfile` at `0x18016ac66`

## pseudocode

```c
__int64 __fastcall GEN_PROJECT::WriteOldBinary(GEN_PROJECT *this, struct IStorage *a2, char *a3, unsigned __int16 a4)
{
  HRESULT v5; // [rsp+50h] [rbp-940h]
  IStorage *ppstgOpen; // [rsp+58h] [rbp-938h] BYREF
  char Drive[8]; // [rsp+60h] [rbp-930h] BYREF
  HMODULE hModule; // [rsp+68h] [rbp-928h]
  FARPROC ProcAddress; // [rsp+70h] [rbp-920h]
  char Dir[256]; // [rsp+80h] [rbp-910h] BYREF
  CHAR Filename[2048]; // [rsp+180h] [rbp-810h] BYREF

  ProcAddress = 0;
  if ( GetModuleFileNameA(g_hinst, Filename, 0x800u) )
  {
    _splitpath_s(Filename, Drive, 3u, Dir, 0x100u, 0, 0, 0, 0);
    _mbscpy_s((unsigned __int8 *)Filename, 0x800u, (const unsigned __int8 *)Drive);
    _mbscat_s((unsigned __int8 *)Filename, 0x800u, (const unsigned __int8 *)Dir);
    _mbscat_s((unsigned __int8 *)Filename, 0x800u, (const unsigned __int8 *)a3);
    a3 = Filename;
  }
  hModule = (HMODULE)IsolationAwareLoadLibraryA(a3);
  if ( (unsigned __int64)hModule < 0x20 )
    return HresultOfLoadLibraryErr();
  ProcAddress = GetProcAddress(hModule, "ConvertToBinary");
  if ( ProcAddress )
  {
    v5 = StgCreateDocfile(0, 0x4001012u, 0, &ppstgOpen);
    if ( v5 >= 0 )
    {
      v5 = GEN_PROJECT::WriteCanonicalProject(this, ppstgOpen, 0, 0, 0);
      if ( v5 >= 0 )
      {
        ((void (__fastcall *)(IStorage *, _QWORD))ppstgOpen->lpVtbl->Commit)(ppstgOpen, 0);
        v5 = ((__int64 (__fastcall *)(struct IStorage *, IStorage *, _QWORD))ProcAddress)(a2, ppstgOpen, a4);
      }
      if ( ppstgOpen )
        ((void (__fastcall *)(IStorage *))ppstgOpen->lpVtbl->Release)(ppstgOpen);
    }
  }
  else
  {
    v5 = -2147312566;
  }
  if ( hModule )
    FreeLibrary(hModule);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18016ab08  mov     [rsp-8+arg_18], r9w
0x18016ab0e  mov     [rsp-8+Src], r8
0x18016ab13  mov     [rsp-8+arg_8], rdx
0x18016ab18  mov     [rsp-8+arg_0], rcx
0x18016ab1d  push    rbp
0x18016ab1e  mov     rbp, rsp
0x18016ab21  sub     rsp, 990h
0x18016ab28  mov     rax, cs:__security_cookie
0x18016ab2f  xor     rax, rsp
0x18016ab32  mov     [rbp+var_10], rax
0x18016ab36  mov     [rsp+990h+var_920], 0
0x18016ab3f  mov     r8d, 800h; nSize
0x18016ab45  lea     rdx, [rsp+990h+Filename]; lpFilename
0x18016ab4d  mov     rcx, cs:g_hinst; hModule
0x18016ab54  call    cs:__imp_GetModuleFileNameA
0x18016ab5a  test    eax, eax
0x18016ab5c  jz      loc_18016AC06
0x18016ab62  mov     [rsp+990h+ExtCount], 0; ExtCount
0x18016ab6b  mov     [rsp+990h+Ext], 0; Ext
0x18016ab74  mov     [rsp+990h+FilenameCount], 0; FilenameCount
0x18016ab7d  mov     [rsp+990h+var_968], 0; Filename
0x18016ab86  mov     [rsp+990h+DirCount], 100h; DirCount
0x18016ab8f  lea     r9, [rsp+990h+Dir]; Dir
0x18016ab97  mov     r8d, 3; DriveCount
0x18016ab9d  lea     rdx, [rsp+990h+Drive]; Drive
0x18016aba2  lea     rcx, [rsp+990h+Filename]; FullPath
0x18016abaa  call    cs:__imp__splitpath_s
0x18016abb0  lea     r8, [rsp+990h+Drive]; Src
0x18016abb5  mov     edx, 800h; SizeInBytes
0x18016abba  lea     rcx, [rsp+990h+Filename]; Dst
0x18016abc2  call    cs:__imp__mbscpy_s
0x18016abc8  lea     r8, [rsp+990h+Dir]; Src
0x18016abd0  mov     edx, 800h; SizeInBytes
0x18016abd5  lea     rcx, [rsp+990h+Filename]; Dst
0x18016abdd  call    cs:__imp__mbscat_s
0x18016abe3  mov     r8, [rbp+Src]; Src
0x18016abe7  mov     edx, 800h; SizeInBytes
0x18016abec  lea     rcx, [rsp+990h+Filename]; Dst
0x18016abf4  call    cs:__imp__mbscat_s
0x18016abfa  lea     rax, [rsp+990h+Filename]
0x18016ac02  mov     [rbp+Src], rax
0x18016ac06  mov     rcx, [rbp+Src]
0x18016ac0a  call    IsolationAwareLoadLibraryA
0x18016ac0f  mov     [rsp+990h+hModule], rax
0x18016ac14  cmp     [rsp+990h+hModule], 20h ; ' '
0x18016ac1a  jnb     short loc_18016AC26
0x18016ac1c  call    HresultOfLoadLibraryErr
0x18016ac21  jmp     loc_18016AD0A
0x18016ac26  lea     rdx, aConverttobinar; "ConvertToBinary"
0x18016ac2d  mov     rcx, [rsp+990h+hModule]; hModule
0x18016ac32  call    cs:__imp_GetProcAddress
0x18016ac38  mov     [rsp+990h+var_920], rax
0x18016ac3d  cmp     [rsp+990h+var_920], 0
0x18016ac43  jnz     short loc_18016AC57
0x18016ac45  mov     [rsp+990h+var_940], 80029C4Ah
0x18016ac4d  jmp     loc_18016ACF3
0x18016ac52  jmp     loc_18016ACF3
0x18016ac57  lea     r9, [rsp+990h+ppstgOpen]; ppstgOpen
0x18016ac5c  xor     r8d, r8d; reserved
0x18016ac5f  mov     edx, 4001012h; grfMode
0x18016ac64  xor     ecx, ecx; pwcsName
0x18016ac66  call    cs:__imp_StgCreateDocfile
0x18016ac6c  mov     [rsp+990h+var_940], eax
0x18016ac70  cmp     [rsp+990h+var_940], 0
0x18016ac75  jge     short loc_18016AC7B
0x18016ac77  jmp     short loc_18016ACF3
0x18016ac79  jmp     short loc_18016ACF3
0x18016ac7b  mov     [rsp+990h+DirCount], 0; struct IVbaProvideStorage *
0x18016ac84  xor     r9d, r9d; int
0x18016ac87  xor     r8d, r8d; struct IStream *
0x18016ac8a  mov     rdx, [rsp+990h+ppstgOpen]; struct IStorage *
0x18016ac8f  mov     rcx, [rbp+arg_0]; this
0x18016ac93  call    ?WriteCanonicalProject@GEN_PROJECT@@QEAAJPEAUIStorage@@PEAUIStream@@HPEAUIVbaProvideStorage@@@Z; GEN_PROJECT::WriteCanonicalProject(IStorage *,IStream *,int,IVbaProvideStorage *)
0x18016ac98  mov     [rsp+990h+var_940], eax
0x18016ac9c  mov     eax, [rsp+990h+var_940]
0x18016aca0  mov     [rsp+990h+var_940], eax
0x18016aca4  cmp     [rsp+990h+var_940], 0
0x18016aca9  jge     short loc_18016ACAF
0x18016acab  jmp     short loc_18016ACDB
0x18016acad  jmp     short loc_18016ACDB
0x18016acaf  mov     rax, [rsp+990h+ppstgOpen]
0x18016acb4  mov     rax, [rax]
0x18016acb7  xor     edx, edx
0x18016acb9  mov     rcx, [rsp+990h+ppstgOpen]
0x18016acbe  call    qword ptr [rax+48h]
0x18016acc1  mov     [rsp+990h+var_940], eax
0x18016acc5  movzx   r8d, [rbp+arg_18]
0x18016acca  mov     rdx, [rsp+990h+ppstgOpen]
0x18016accf  mov     rcx, [rbp+arg_8]
0x18016acd3  call    [rsp+990h+var_920]
0x18016acd7  mov     [rsp+990h+var_940], eax
0x18016acdb  cmp     [rsp+990h+ppstgOpen], 0
0x18016ace1  jz      short loc_18016ACF3
0x18016ace3  mov     rax, [rsp+990h+ppstgOpen]
0x18016ace8  mov     rax, [rax]
0x18016aceb  mov     rcx, [rsp+990h+ppstgOpen]
0x18016acf0  call    qword ptr [rax+10h]
0x18016acf3  cmp     [rsp+990h+hModule], 0
0x18016acf9  jz      short loc_18016AD06
0x18016acfb  mov     rcx, [rsp+990h+hModule]; hLibModule
0x18016ad00  call    cs:__imp_FreeLibrary
0x18016ad06  mov     eax, [rsp+990h+var_940]
0x18016ad0a  mov     rcx, [rbp+var_10]
0x18016ad0e  xor     rcx, rsp; StackCookie
0x18016ad11  call    __security_check_cookie
0x18016ad16  add     rsp, 990h
0x18016ad1d  pop     rbp
0x18016ad1e  retn
```
