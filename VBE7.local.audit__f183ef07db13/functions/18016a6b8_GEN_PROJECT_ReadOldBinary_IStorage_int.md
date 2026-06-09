# GEN_PROJECT::ReadOldBinary(IStorage *,int)

- ea: `0x18016a6b8`
- end: `0x18016aaff`
- name: `?ReadOldBinary@GEN_PROJECT@@QEAAJPEAUIStorage@@H@Z`
- size: `1095`
- prototype: `__int64 __fastcall(GEN_PROJECT *__hidden this, struct IStorage *, int)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18012ea10`

## callees

- `0x180024478`
- `0x1800e6178`
- `0x1800e6434`
- `0x1800e64b4`
- `0x1800f63f0`
- `0x1800fba64`
- `0x18011b20c`
- `0x18011dc7c`
- `0x18016a6b8`
- `0x1801706c0`
- `0x180174f88`
- `0x180379520`

## import_xrefs

- `MSVCR100!_mbscat_s` at `0x18016a814`
- `MSVCR100!_mbscat_s` at `0x18016a82c`
- `MSVCR100!_mbscat_s` at `0x18016a814`
- `MSVCR100!_mbscat_s` at `0x18016a82c`
- `MSVCR100!_mbscpy_s` at `0x18016a7f9`
- `MSVCR100!_mbscpy_s` at `0x18016a7f9`
- `MSVCR100!_splitpath_s` at `0x18016a7e1`
- `MSVCR100!_splitpath_s` at `0x18016a7e1`
- `KERNEL32!GetLastError` at `0x18016a96b`
- `KERNEL32!GetLastError` at `0x18016a96b`
- `KERNEL32!GetModuleFileNameA` at `0x18016a78b`
- `KERNEL32!GetModuleFileNameA` at `0x18016a78b`
- `KERNEL32!FreeLibrary` at `0x18016aae0`
- `KERNEL32!FreeLibrary` at `0x18016aae0`
- `KERNEL32!GetProcAddress` at `0x18016a952`
- `KERNEL32!GetProcAddress` at `0x18016a9e8`
- `KERNEL32!GetProcAddress` at `0x18016a952`
- `KERNEL32!GetProcAddress` at `0x18016a9e8`
- `ole32!CreateILockBytesOnHGlobal` at `0x18016a8d3`
- `ole32!CreateILockBytesOnHGlobal` at `0x18016a8d3`
- `ole32!StgCreateDocfileOnILockBytes` at `0x18016a903`
- `ole32!StgCreateDocfileOnILockBytes` at `0x18016a903`

## string_xrefs

- `0x18016a754`: `vbacv10d.dll`
- `0x18016a76a`: `vbacv10.dll`
- `0x18016a712`: `vbacv20.dll`

## pseudocode

```c
__int64 __fastcall GEN_PROJECT::ReadOldBinary(GEN_PROJECT *this, struct IStorage *a2, int a3)
{
  struct EBAPP *v3; // rax
  struct EBAPP *v5; // rax
  struct EBAPP *v6; // rax
  ExecProj *v7; // rax
  struct IVbaProvideStorage *v8; // rax
  memoryBlock *v9; // rax
  struct memoryAlloc *v10; // rax
  struct EBAPP *v11; // rax
  HRESULT CanonicalProject; // [rsp+50h] [rbp-980h]
  IStorage *ppstgOpen; // [rsp+58h] [rbp-978h] BYREF
  int v14; // [rsp+60h] [rbp-970h]
  unsigned __int8 *Src; // [rsp+68h] [rbp-968h]
  HMODULE hModule; // [rsp+70h] [rbp-960h]
  char Drive[8]; // [rsp+78h] [rbp-958h] BYREF
  LPLOCKBYTES pplkbyt; // [rsp+80h] [rbp-950h] BYREF
  FARPROC v19; // [rsp+88h] [rbp-948h]
  CHAR Filename[2048]; // [rsp+90h] [rbp-940h] BYREF
  FARPROC ProcAddress; // [rsp+890h] [rbp-140h]
  __int64 v22; // [rsp+898h] [rbp-138h]
  DWORD LastError; // [rsp+8A0h] [rbp-130h]
  __int64 v24; // [rsp+8A8h] [rbp-128h]
  __int64 v25; // [rsp+8B0h] [rbp-120h]
  char Dir[256]; // [rsp+8C0h] [rbp-110h] BYREF

  v25 = 0;
  pplkbyt = 0;
  v24 = 0;
  v14 = 0;
  if ( a3 )
  {
    Src = "vbacv20.dll";
    v3 = PebappCur();
    (*(void (__fastcall **)(__int64, __int64))(*((_QWORD *)v3 + 7) + 184LL))(45, 2);
  }
  else if ( (unsigned int)IsDBCS(*((unsigned int *)this + 138)) )
  {
    v14 = 1;
    Src = "vbacv10d.dll";
  }
  else
  {
    v14 = 0;
    Src = "vbacv10.dll";
  }
  if ( GetModuleFileNameA(g_hinst, Filename, 0x800u) )
  {
    _splitpath_s(Filename, Drive, 3u, Dir, 0x100u, 0, 0, 0, 0);
    _mbscpy_s((unsigned __int8 *)Filename, 0x800u, (const unsigned __int8 *)Drive);
    _mbscat_s((unsigned __int8 *)Filename, 0x800u, (const unsigned __int8 *)Dir);
    _mbscat_s((unsigned __int8 *)Filename, 0x800u, Src);
    Src = (unsigned __int8 *)Filename;
  }
  hModule = (HMODULE)IsolationAwareLoadLibraryA(Src);
  if ( (unsigned __int64)hModule < 0x20 )
    return HresultOfLoadLibraryErr();
  if ( a3 )
  {
    v5 = PebappCur();
    (*(void (__fastcall **)(__int64, __int64))(*((_QWORD *)v5 + 7) + 184LL))(45, 2);
  }
  else
  {
    v6 = PebappCur();
    if ( v14 )
      (*(void (__fastcall **)(__int64, __int64))(*((_QWORD *)v6 + 7) + 184LL))(45, 1);
    else
      (*(void (__fastcall **)(__int64, _QWORD))(*((_QWORD *)v6 + 7) + 184LL))(45, 0);
  }
  CanonicalProject = CreateILockBytesOnHGlobal(0, 1, &pplkbyt);
  if ( CanonicalProject >= 0 )
  {
    CanonicalProject = StgCreateDocfileOnILockBytes(pplkbyt, 0x1012u, 0, &ppstgOpen);
    ((void (__fastcall *)(LPLOCKBYTES))pplkbyt->lpVtbl->Release)(pplkbyt);
    if ( CanonicalProject >= 0 )
    {
      if ( a3 )
      {
        ProcAddress = GetProcAddress(hModule, "Convert94ToAscii");
        if ( !ProcAddress )
        {
          LastError = GetLastError();
          CanonicalProject = -2147312566;
          goto LABEL_30;
        }
        v22 = *((_QWORD *)PebappCur() + 7);
        v7 = GEN_PROJECT::Pexecproj(this);
        v8 = ExecProj::Pprovidestg(v7);
        CanonicalProject = ((__int64 (__fastcall *)(struct IStorage *, IStorage *, struct IVbaProvideStorage *, _QWORD, int))ProcAddress)(
                             a2,
                             ppstgOpen,
                             v8,
                             *(_QWORD *)(v22 + 184),
                             35);
      }
      else
      {
        v19 = GetProcAddress(hModule, "ConvertToAscii");
        if ( !v19 )
        {
          CanonicalProject = -2147312566;
          goto LABEL_30;
        }
        v9 = GEN_PROJECT::Pexecproj(this);
        v10 = memoryBlock::Pma(v9);
        CanonicalProject = ((__int64 (__fastcall *)(struct IStorage *, IStorage *, char *))v19)(
                             a2,
                             ppstgOpen,
                             (char *)v10 + 3);
      }
      if ( CanonicalProject == (unsigned int)HresultOfEberr(57077) )
      {
        EbShowError(57077);
        CanonicalProject = 0;
      }
      if ( CanonicalProject >= 0 )
      {
        ((void (__fastcall *)(IStorage *, _QWORD))ppstgOpen->lpVtbl->Commit)(ppstgOpen, 0);
        CanonicalProject = GEN_PROJECT::ReadCanonicalProject(this, ppstgOpen, 0, 0);
        v11 = PebappCur();
        (*(void (__fastcall **)(__int64, __int64))(*((_QWORD *)v11 + 7) + 184LL))(35, 100);
      }
      if ( ppstgOpen )
        ((void (__fastcall *)(IStorage *))ppstgOpen->lpVtbl->Release)(ppstgOpen);
    }
  }
LABEL_30:
  if ( hModule )
    FreeLibrary(hModule);
  return (unsigned int)CanonicalProject;
}

```

## disassembly

```asm
0x18016a6b8  mov     [rsp-8+arg_10], r8d
0x18016a6bd  mov     [rsp-8+arg_8], rdx
0x18016a6c2  mov     [rsp-8+arg_0], rcx
0x18016a6c7  push    rbp
0x18016a6c8  mov     rbp, rsp
0x18016a6cb  sub     rsp, 9D0h
0x18016a6d2  mov     rax, cs:__security_cookie
0x18016a6d9  xor     rax, rsp
0x18016a6dc  mov     [rbp+var_10], rax
0x18016a6e0  mov     [rsp+9D0h+var_120], 0
0x18016a6ec  mov     [rsp+9D0h+pplkbyt], 0
0x18016a6f8  mov     [rsp+9D0h+var_128], 0
0x18016a704  mov     [rsp+9D0h+var_970], 0
0x18016a70c  cmp     [rbp+arg_10], 0
0x18016a710  jz      short loc_18016A739
0x18016a712  lea     rax, aVbacv20Dll; "vbacv20.dll"
0x18016a719  mov     [rsp+9D0h+Src], rax
0x18016a71e  call    ?PebappCur@@YAPEAVEBAPP@@XZ; PebappCur(void)
0x18016a723  mov     rax, [rax+38h]
0x18016a727  mov     edx, 2
0x18016a72c  mov     ecx, 2Dh ; '-'
0x18016a731  call    qword ptr [rax+0B8h]
0x18016a737  jmp     short loc_18016A776
0x18016a739  mov     rax, [rbp+arg_0]
0x18016a73d  mov     ecx, [rax+228h]
0x18016a743  call    IsDBCS
0x18016a748  test    eax, eax
0x18016a74a  jz      short loc_18016A762
0x18016a74c  mov     [rsp+9D0h+var_970], 1
0x18016a754  lea     rax, aVbacv10dDll; "vbacv10d.dll"
0x18016a75b  mov     [rsp+9D0h+Src], rax
0x18016a760  jmp     short loc_18016A776
0x18016a762  mov     [rsp+9D0h+var_970], 0
0x18016a76a  lea     rax, aVbacv10Dll; "vbacv10.dll"
0x18016a771  mov     [rsp+9D0h+Src], rax
0x18016a776  mov     r8d, 800h; nSize
0x18016a77c  lea     rdx, [rsp+9D0h+Filename]; lpFilename
0x18016a784  mov     rcx, cs:g_hinst; hModule
0x18016a78b  call    cs:__imp_GetModuleFileNameA
0x18016a791  test    eax, eax
0x18016a793  jz      loc_18016A83F
0x18016a799  mov     [rsp+9D0h+ExtCount], 0; ExtCount
0x18016a7a2  mov     [rsp+9D0h+Ext], 0; Ext
0x18016a7ab  mov     [rsp+9D0h+FilenameCount], 0; FilenameCount
0x18016a7b4  mov     [rsp+9D0h+var_9A8], 0; Filename
0x18016a7bd  mov     [rsp+9D0h+DirCount], 100h; DirCount
0x18016a7c6  lea     r9, [rsp+9D0h+Dir]; Dir
0x18016a7ce  mov     r8d, 3; DriveCount
0x18016a7d4  lea     rdx, [rsp+9D0h+Drive]; Drive
0x18016a7d9  lea     rcx, [rsp+9D0h+Filename]; FullPath
0x18016a7e1  call    cs:__imp__splitpath_s
0x18016a7e7  lea     r8, [rsp+9D0h+Drive]; Src
0x18016a7ec  mov     edx, 800h; SizeInBytes
0x18016a7f1  lea     rcx, [rsp+9D0h+Filename]; Dst
0x18016a7f9  call    cs:__imp__mbscpy_s
0x18016a7ff  lea     r8, [rsp+9D0h+Dir]; Src
0x18016a807  mov     edx, 800h; SizeInBytes
0x18016a80c  lea     rcx, [rsp+9D0h+Filename]; Dst
0x18016a814  call    cs:__imp__mbscat_s
0x18016a81a  mov     r8, [rsp+9D0h+Src]; Src
0x18016a81f  mov     edx, 800h; SizeInBytes
0x18016a824  lea     rcx, [rsp+9D0h+Filename]; Dst
0x18016a82c  call    cs:__imp__mbscat_s
0x18016a832  lea     rax, [rsp+9D0h+Filename]
0x18016a83a  mov     [rsp+9D0h+Src], rax
0x18016a83f  mov     rcx, [rsp+9D0h+Src]
0x18016a844  call    IsolationAwareLoadLibraryA
0x18016a849  mov     [rsp+9D0h+hModule], rax
0x18016a84e  cmp     [rsp+9D0h+hModule], 20h ; ' '
0x18016a854  jnb     short loc_18016A86B
0x18016a856  xor     eax, eax
0x18016a858  test    eax, eax
0x18016a85a  jz      short loc_18016A861
0x18016a85c  jmp     loc_18016A762
0x18016a861  call    HresultOfLoadLibraryErr
0x18016a866  jmp     loc_18016AAEA
0x18016a86b  cmp     [rbp+arg_10], 0
0x18016a86f  jz      short loc_18016A88C
0x18016a871  call    ?PebappCur@@YAPEAVEBAPP@@XZ; PebappCur(void)
0x18016a876  mov     rax, [rax+38h]
0x18016a87a  mov     edx, 2
0x18016a87f  mov     ecx, 2Dh ; '-'
0x18016a884  call    qword ptr [rax+0B8h]
0x18016a88a  jmp     short loc_18016A8C4
0x18016a88c  cmp     [rsp+9D0h+var_970], 0
0x18016a891  jz      short loc_18016A8AE
0x18016a893  call    ?PebappCur@@YAPEAVEBAPP@@XZ; PebappCur(void)
0x18016a898  mov     rax, [rax+38h]
0x18016a89c  mov     edx, 1
0x18016a8a1  mov     ecx, 2Dh ; '-'
0x18016a8a6  call    qword ptr [rax+0B8h]
0x18016a8ac  jmp     short loc_18016A8C4
0x18016a8ae  call    ?PebappCur@@YAPEAVEBAPP@@XZ; PebappCur(void)
0x18016a8b3  mov     rax, [rax+38h]
0x18016a8b7  xor     edx, edx
0x18016a8b9  mov     ecx, 2Dh ; '-'
0x18016a8be  call    qword ptr [rax+0B8h]
0x18016a8c4  lea     r8, [rsp+9D0h+pplkbyt]; pplkbyt
0x18016a8cc  mov     edx, 1; fDeleteOnRelease
0x18016a8d1  xor     ecx, ecx; hGlobal
0x18016a8d3  call    cs:__imp_CreateILockBytesOnHGlobal
0x18016a8d9  mov     [rsp+9D0h+var_980], eax
0x18016a8dd  cmp     [rsp+9D0h+var_980], 0
0x18016a8e2  jge     short loc_18016A8EE
0x18016a8e4  jmp     loc_18016AAD3
0x18016a8e9  jmp     loc_18016AAD3
0x18016a8ee  lea     r9, [rsp+9D0h+ppstgOpen]; ppstgOpen
0x18016a8f3  xor     r8d, r8d; reserved
0x18016a8f6  mov     edx, 1012h; grfMode
0x18016a8fb  mov     rcx, [rsp+9D0h+pplkbyt]; plkbyt
0x18016a903  call    cs:__imp_StgCreateDocfileOnILockBytes
0x18016a909  mov     [rsp+9D0h+var_980], eax
0x18016a90d  mov     rax, [rsp+9D0h+pplkbyt]
0x18016a915  mov     rax, [rax]
0x18016a918  mov     rcx, [rsp+9D0h+pplkbyt]
0x18016a920  call    qword ptr [rax+10h]
0x18016a923  mov     eax, [rsp+9D0h+var_980]
0x18016a927  mov     [rsp+9D0h+var_980], eax
0x18016a92b  cmp     [rsp+9D0h+var_980], 0
0x18016a930  jge     short loc_18016A93C
0x18016a932  jmp     loc_18016AAD3
0x18016a937  jmp     loc_18016AAD3
0x18016a93c  cmp     [rbp+arg_10], 0
0x18016a940  jz      loc_18016A9DC
0x18016a946  lea     rdx, aConvert94toasc; "Convert94ToAscii"
0x18016a94d  mov     rcx, [rsp+9D0h+hModule]; hModule
0x18016a952  call    cs:__imp_GetProcAddress
0x18016a958  mov     [rsp+9D0h+var_140], rax
0x18016a960  cmp     [rsp+9D0h+var_140], 0
0x18016a969  jnz     short loc_18016A98A
0x18016a96b  call    cs:__imp_GetLastError
0x18016a971  mov     [rsp+9D0h+var_130], eax
0x18016a978  mov     [rsp+9D0h+var_980], 80029C4Ah
0x18016a980  jmp     loc_18016AAD3
0x18016a985  jmp     loc_18016AAD3
0x18016a98a  call    ?PebappCur@@YAPEAVEBAPP@@XZ; PebappCur(void)
0x18016a98f  mov     rax, [rax+38h]
0x18016a993  mov     [rsp+9D0h+var_138], rax
0x18016a99b  mov     rcx, [rbp+arg_0]; this
0x18016a99f  call    ?Pexecproj@GEN_PROJECT@@QEBAPEAUExecProj@@XZ; GEN_PROJECT::Pexecproj(void)
0x18016a9a4  mov     rcx, rax; this
0x18016a9a7  call    ?Pprovidestg@ExecProj@@QEAAPEAUIVbaProvideStorage@@XZ; ExecProj::Pprovidestg(void)
0x18016a9ac  mov     dword ptr [rsp+9D0h+DirCount], 23h ; '#'
0x18016a9b4  mov     rcx, [rsp+9D0h+var_138]
0x18016a9bc  mov     r9, [rcx+0B8h]
0x18016a9c3  mov     r8, rax
0x18016a9c6  mov     rdx, [rsp+9D0h+ppstgOpen]
0x18016a9cb  mov     rcx, [rbp+arg_8]
0x18016a9cf  call    [rsp+9D0h+var_140]
0x18016a9d6  mov     [rsp+9D0h+var_980], eax
0x18016a9da  jmp     short loc_18016AA3F
0x18016a9dc  lea     rdx, aConverttoascii; "ConvertToAscii"
0x18016a9e3  mov     rcx, [rsp+9D0h+hModule]; hModule
0x18016a9e8  call    cs:__imp_GetProcAddress
0x18016a9ee  mov     [rsp+9D0h+var_948], rax
0x18016a9f6  cmp     [rsp+9D0h+var_948], 0
0x18016a9ff  jnz     short loc_18016AA13
0x18016aa01  mov     [rsp+9D0h+var_980], 80029C4Ah
0x18016aa09  jmp     loc_18016AAD3
0x18016aa0e  jmp     loc_18016AAD3
0x18016aa13  mov     rcx, [rbp+arg_0]; this
0x18016aa17  call    ?Pexecproj@GEN_PROJECT@@QEBAPEAUExecProj@@XZ; GEN_PROJECT::Pexecproj(void)
0x18016aa1c  mov     rcx, rax; this
0x18016aa1f  call    ?Pma@memoryBlock@@QEAAPEAUmemoryAlloc@@XZ; memoryBlock::Pma(void)
0x18016aa24  add     rax, 3
0x18016aa28  mov     r8, rax
0x18016aa2b  mov     rdx, [rsp+9D0h+ppstgOpen]
0x18016aa30  mov     rcx, [rbp+arg_8]
0x18016aa34  call    [rsp+9D0h+var_948]
0x18016aa3b  mov     [rsp+9D0h+var_980], eax
0x18016aa3f  mov     ecx, 0DEF5h
0x18016aa44  call    HresultOfEberr
0x18016aa49  cmp     [rsp+9D0h+var_980], eax
0x18016aa4d  jnz     short loc_18016AA61
0x18016aa4f  mov     ecx, 0DEF5h
0x18016aa54  call    EbShowError
0x18016aa59  mov     [rsp+9D0h+var_980], 0
0x18016aa61  mov     eax, [rsp+9D0h+var_980]
0x18016aa65  mov     [rsp+9D0h+var_980], eax
0x18016aa69  cmp     [rsp+9D0h+var_980], 0
0x18016aa6e  jge     short loc_18016AA74
0x18016aa70  jmp     short loc_18016AABB
0x18016aa72  jmp     short loc_18016AABB
0x18016aa74  mov     rax, [rsp+9D0h+ppstgOpen]
0x18016aa79  mov     rax, [rax]
0x18016aa7c  xor     edx, edx
0x18016aa7e  mov     rcx, [rsp+9D0h+ppstgOpen]
0x18016aa83  call    qword ptr [rax+48h]
0x18016aa86  mov     [rsp+9D0h+var_980], eax
0x18016aa8a  xor     r9d, r9d; int
0x18016aa8d  xor     r8d, r8d; struct IStream *
0x18016aa90  mov     rdx, [rsp+9D0h+ppstgOpen]; struct IStorage *
0x18016aa95  mov     rcx, [rbp+arg_0]; this
0x18016aa99  call    ?ReadCanonicalProject@GEN_PROJECT@@QEAAJPEAUIStorage@@PEAUIStream@@H@Z; GEN_PROJECT::ReadCanonicalProject(IStorage *,IStream *,int)
0x18016aa9e  mov     [rsp+9D0h+var_980], eax
0x18016aaa2  call    ?PebappCur@@YAPEAVEBAPP@@XZ; PebappCur(void)
0x18016aaa7  mov     rax, [rax+38h]
0x18016aaab  mov     edx, 64h ; 'd'
0x18016aab0  mov     ecx, 23h ; '#'
0x18016aab5  call    qword ptr [rax+0B8h]
0x18016aabb  cmp     [rsp+9D0h+ppstgOpen], 0
0x18016aac1  jz      short loc_18016AAD3
0x18016aac3  mov     rax, [rsp+9D0h+ppstgOpen]
0x18016aac8  mov     rax, [rax]
0x18016aacb  mov     rcx, [rsp+9D0h+ppstgOpen]
0x18016aad0  call    qword ptr [rax+10h]
0x18016aad3  cmp     [rsp+9D0h+hModule], 0
0x18016aad9  jz      short loc_18016AAE6
0x18016aadb  mov     rcx, [rsp+9D0h+hModule]; hLibModule
0x18016aae0  call    cs:__imp_FreeLibrary
0x18016aae6  mov     eax, [rsp+9D0h+var_980]
0x18016aaea  mov     rcx, [rbp+var_10]
0x18016aaee  xor     rcx, rsp; StackCookie
0x18016aaf1  call    __security_check_cookie
0x18016aaf6  add     rsp, 9D0h
0x18016aafd  pop     rbp
0x18016aafe  retn
```
