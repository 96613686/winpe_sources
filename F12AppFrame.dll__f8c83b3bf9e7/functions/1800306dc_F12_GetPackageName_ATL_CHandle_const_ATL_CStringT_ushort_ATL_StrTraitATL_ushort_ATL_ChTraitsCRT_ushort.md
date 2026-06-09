# F12::GetPackageName(ATL::CHandle const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x1800306dc`
- end: `0x180030802`
- name: `?GetPackageName@F12@@YAJAEBVCHandle@ATL@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z`
- size: `294`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180014740`

## callees

- `0x180003858`
- `0x1800039ec`
- `0x1800042a4`
- `0x1800306dc`
- `0x180035010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18003072b`
- `KERNEL32!GetProcAddress` at `0x18003072b`
- `KERNEL32!GetModuleHandleW` at `0x180030716`
- `KERNEL32!GetModuleHandleW` at `0x180030716`

## string_xrefs

- `0x18003070f`: `kernel32.dll`

## pseudocode

```c
__int64 __fastcall F12::GetPackageName(_QWORD *a1, int **a2)
{
  unsigned int v4; // esi
  FARPROC ProcAddress; // rbx
  HMODULE ModuleHandleW; // rax
  __int64 v7; // rcx
  int v8; // eax
  int *v9; // rcx
  int v10; // r8d
  __int64 v11; // rax
  int v13; // [rsp+50h] [rbp+18h] BYREF

  v4 = -2147467259;
  ATL::CSimpleStringT<unsigned short,0>::Empty(a2);
  ProcAddress = (FARPROC)qword_1800508A8;
  if ( qword_1800508A8
    || ((ModuleHandleW = GetModuleHandleW(L"kernel32.dll")) == 0
      ? (ProcAddress = (FARPROC)qword_1800508A8)
      : (FARPROC)(ProcAddress = GetProcAddress(ModuleHandleW, "GetPackageFullName"),
                  qword_1800508A8 = (__int64)ProcAddress),
        ProcAddress) )
  {
    v7 = *a1;
    if ( *a1 )
    {
      v13 = 0;
      if ( ((unsigned int (__fastcall *)(__int64, int *, _QWORD))ProcAddress)(v7, &v13, 0) == 122 )
      {
        if ( ((*(*a2 - 3) - (v13 + 1)) | (1 - *(*a2 - 2))) < 0 )
          ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(a2);
        v8 = ((__int64 (__fastcall *)(_QWORD, int *, int *))ProcAddress)(*a1, &v13, *a2);
        v9 = *a2;
        v10 = v8;
        if ( *a2 )
        {
          v11 = -1;
          do
            ++v11;
          while ( *((_WORD *)v9 + v11) );
          if ( (int)v11 < 0 )
            goto LABEL_19;
        }
        else
        {
          LODWORD(v11) = 0;
        }
        if ( (int)v11 <= *(v9 - 3) )
        {
          *(v9 - 4) = v11;
          *((_WORD *)*a2 + (unsigned int)v11) = 0;
          if ( !v10 )
            return 0;
          return v4;
        }
LABEL_19:
        ATL::AtlThrowImpl(-2147024809);
      }
    }
  }
  return v4;
}

```

## disassembly

```asm
0x1800306dc  mov     [rsp+arg_0], rbx
0x1800306e1  mov     [rsp+arg_8], rbp
0x1800306e6  push    rsi
0x1800306e7  push    rdi
0x1800306e8  push    r14
0x1800306ea  sub     rsp, 20h
0x1800306ee  mov     r14, rcx
0x1800306f1  mov     rdi, rdx
0x1800306f4  mov     rcx, rdx
0x1800306f7  mov     esi, 80004005h
0x1800306fc  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180030701  mov     rbx, cs:qword_1800508A8
0x180030708  xor     ebp, ebp
0x18003070a  test    rbx, rbx
0x18003070d  jnz     short loc_18003074D
0x18003070f  lea     rcx, aKernel32Dll_0; "kernel32.dll"
0x180030716  call    cs:__imp_GetModuleHandleW
0x18003071c  test    rax, rax
0x18003071f  jz      short loc_18003073D
0x180030721  lea     rdx, aGetpackagefull; "GetPackageFullName"
0x180030728  mov     rcx, rax; hModule
0x18003072b  call    cs:__imp_GetProcAddress
0x180030731  mov     rbx, rax
0x180030734  mov     cs:qword_1800508A8, rax
0x18003073b  jmp     short loc_180030744
0x18003073d  mov     rbx, cs:qword_1800508A8
0x180030744  test    rbx, rbx
0x180030747  jz      loc_1800307E2
0x18003074d  mov     rcx, [r14]
0x180030750  test    rcx, rcx
0x180030753  jz      loc_1800307E2
0x180030759  xor     r8d, r8d
0x18003075c  mov     [rsp+38h+arg_10], ebp
0x180030760  lea     rdx, [rsp+38h+arg_10]
0x180030765  mov     rax, rbx
0x180030768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003076d  cmp     eax, 7Ah ; 'z'
0x180030770  jnz     short loc_1800307E2
0x180030772  mov     rax, [rdi]
0x180030775  mov     r8d, 1
0x18003077b  mov     edx, [rsp+38h+arg_10]
0x18003077f  inc     edx
0x180030781  mov     ecx, [rax-0Ch]
0x180030784  sub     r8d, [rax-8]
0x180030788  sub     ecx, edx
0x18003078a  or      r8d, ecx
0x18003078d  jge     short loc_180030797
0x18003078f  mov     rcx, rdi
0x180030792  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x180030797  mov     r8, [rdi]
0x18003079a  lea     rdx, [rsp+38h+arg_10]
0x18003079f  mov     rcx, [r14]
0x1800307a2  mov     rax, rbx
0x1800307a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800307aa  mov     rcx, [rdi]
0x1800307ad  mov     r8d, eax
0x1800307b0  test    rcx, rcx
0x1800307b3  jnz     short loc_1800307B9
0x1800307b5  mov     eax, ebp
0x1800307b7  jmp     short loc_1800307CA
0x1800307b9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800307bd  inc     rax
0x1800307c0  cmp     [rcx+rax*2], bp
0x1800307c4  jnz     short loc_1800307BD
0x1800307c6  test    eax, eax
0x1800307c8  js      short loc_1800307F7
0x1800307ca  cmp     eax, [rcx-0Ch]
0x1800307cd  jg      short loc_1800307F7
0x1800307cf  mov     [rcx-10h], eax
0x1800307d2  mov     rcx, [rdi]
0x1800307d5  mov     edx, eax
0x1800307d7  mov     [rcx+rdx*2], bp
0x1800307db  test    r8d, r8d
0x1800307de  jnz     short loc_1800307E2
0x1800307e0  mov     esi, ebp
0x1800307e2  mov     rbx, [rsp+38h+arg_0]
0x1800307e7  mov     eax, esi
0x1800307e9  mov     rbp, [rsp+38h+arg_8]
0x1800307ee  add     rsp, 20h
0x1800307f2  pop     r14
0x1800307f4  pop     rdi
0x1800307f5  pop     rsi
0x1800307f6  retn
0x1800307f7  mov     ecx, 80070057h; int
0x1800307fc  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
