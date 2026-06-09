# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(uint)

- ea: `0x18000b484`
- end: `0x18000b588`
- name: `?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHI@Z`
- size: `260`
- prototype: `__int64 __fastcall(ATL::CAtlBaseModule *, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18000ae58`
- `0x18000b3e4`

## callees

- `0x180006d90`
- `0x18000b484`
- `0x18000b590`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18000b50c`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18000b50c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000b4e6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000b4e6`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000b4d2`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000b4d2`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18000b4f8`
- `api-ms-win-core-libraryloader-l1-2-0!LockResource` at `0x18000b4f8`

## pseudocode

```c
__int64 __fastcall ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
        ATL::CAtlBaseModule *a1,
        unsigned int a2)
{
  HMODULE HInstanceAt; // rdi
  int v5; // ebp
  HRSRC Resource; // rax
  ATL::CAtlBaseModule *v7; // rcx
  HRSRC v8; // rsi
  HGLOBAL v9; // rax
  __int64 v10; // rax
  ATL::CAtlBaseModule *v11; // rbx
  int v12; // edx
  int v13; // edx

  HInstanceAt = ATL::CAtlBaseModule::GetHInstanceAt(a1, 0);
  v5 = 1;
  if ( !HInstanceAt )
    return 0;
  while ( 1 )
  {
    Resource = FindResourceExW(HInstanceAt, (LPCWSTR)6, (LPCWSTR)(unsigned __int16)((a2 >> 4) + 1), 0);
    v8 = Resource;
    if ( Resource )
      break;
LABEL_12:
    v13 = v5++;
    HInstanceAt = ATL::CAtlBaseModule::GetHInstanceAt(v7, v13);
    if ( !HInstanceAt )
      return 0;
  }
  v9 = LoadResource(HInstanceAt, Resource);
  if ( !v9 )
    goto LABEL_4;
  v11 = (ATL::CAtlBaseModule *)LockResource(v9);
  if ( !v11 )
    goto LABEL_4;
  v7 = (ATL::CAtlBaseModule *)((char *)v11 + SizeofResource(HInstanceAt, v8));
  v12 = a2 & 0xF;
  if ( (a2 & 0xF) != 0 )
  {
    while ( v11 < v7 )
    {
      v11 = (ATL::CAtlBaseModule *)((char *)v11 + 2 * *(unsigned __int16 *)v11 + 2);
      if ( !--v12 )
        goto LABEL_9;
    }
    goto LABEL_4;
  }
LABEL_9:
  if ( v11 >= v7 )
  {
LABEL_4:
    v10 = 0;
    goto LABEL_11;
  }
  v10 = (unsigned __int64)v11 & -(__int64)(*(_WORD *)v11 != 0);
LABEL_11:
  if ( !v10 )
    goto LABEL_12;
  return ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::LoadStringW(
           a1,
           HInstanceAt,
           a2);
}

```

## disassembly

```asm
0x18000b484  push    rbx
0x18000b486  push    rbp
0x18000b487  push    rsi
0x18000b488  push    rdi
0x18000b489  push    r12
0x18000b48b  push    r13
0x18000b48d  push    r14
0x18000b48f  push    r15
0x18000b491  sub     rsp, 28h
0x18000b495  mov     r14d, edx
0x18000b498  mov     r15, rcx
0x18000b49b  xor     edx, edx; int
0x18000b49d  call    ?GetHInstanceAt@CAtlBaseModule@ATL@@QEAAPEAUHINSTANCE__@@H@Z; ATL::CAtlBaseModule::GetHInstanceAt(int)
0x18000b4a2  mov     r13d, 1
0x18000b4a8  mov     rdi, rax
0x18000b4ab  mov     ebp, r13d
0x18000b4ae  test    rax, rax
0x18000b4b1  jz      loc_18000B560
0x18000b4b7  mov     eax, r14d
0x18000b4ba  shr     eax, 4
0x18000b4bd  add     ax, r13w
0x18000b4c1  movzx   r12d, ax
0x18000b4c5  xor     r9d, r9d; wLanguage
0x18000b4c8  mov     r8, r12; lpName
0x18000b4cb  mov     rcx, rdi; hModule
0x18000b4ce  lea     edx, [r9+6]; lpType
0x18000b4d2  call    cs:__imp_FindResourceExW
0x18000b4d8  mov     rsi, rax
0x18000b4db  test    rax, rax
0x18000b4de  jz      short loc_18000B54A
0x18000b4e0  mov     rdx, rax; hResInfo
0x18000b4e3  mov     rcx, rdi; hModule
0x18000b4e6  call    cs:__imp_LoadResource
0x18000b4ec  test    rax, rax
0x18000b4ef  jnz     short loc_18000B4F5
0x18000b4f1  xor     eax, eax
0x18000b4f3  jmp     short loc_18000B545
0x18000b4f5  mov     rcx, rax; hResData
0x18000b4f8  call    cs:__imp_LockResource
0x18000b4fe  mov     rbx, rax
0x18000b501  test    rax, rax
0x18000b504  jz      short loc_18000B4F1
0x18000b506  mov     rdx, rsi; hResInfo
0x18000b509  mov     rcx, rdi; hModule
0x18000b50c  call    cs:__imp_SizeofResource
0x18000b512  mov     ecx, eax
0x18000b514  mov     edx, r14d
0x18000b517  add     rcx, rbx; this
0x18000b51a  and     edx, 0Fh
0x18000b51d  jbe     short loc_18000B534
0x18000b51f  cmp     rbx, rcx
0x18000b522  jnb     short loc_18000B4F1
0x18000b524  movzx   eax, word ptr [rbx]
0x18000b527  lea     rbx, [rbx+rax*2]
0x18000b52b  add     rbx, 2
0x18000b52f  add     edx, 0FFFFFFFFh
0x18000b532  jnz     short loc_18000B51F
0x18000b534  cmp     rbx, rcx
0x18000b537  jnb     short loc_18000B4F1
0x18000b539  movzx   eax, word ptr [rbx]
0x18000b53c  neg     ax
0x18000b53f  sbb     rax, rax
0x18000b542  and     rax, rbx
0x18000b545  test    rax, rax
0x18000b548  jnz     short loc_18000B573
0x18000b54a  mov     edx, ebp; int
0x18000b54c  add     ebp, r13d
0x18000b54f  call    ?GetHInstanceAt@CAtlBaseModule@ATL@@QEAAPEAUHINSTANCE__@@H@Z; ATL::CAtlBaseModule::GetHInstanceAt(int)
0x18000b554  mov     rdi, rax
0x18000b557  test    rax, rax
0x18000b55a  jnz     loc_18000B4C5
0x18000b560  xor     eax, eax
0x18000b562  add     rsp, 28h
0x18000b566  pop     r15
0x18000b568  pop     r14
0x18000b56a  pop     r13
0x18000b56c  pop     r12
0x18000b56e  pop     rdi
0x18000b56f  pop     rsi
0x18000b570  pop     rbp
0x18000b571  pop     rbx
0x18000b572  retn
0x18000b573  test    rdi, rdi
0x18000b576  jz      short loc_18000B560
0x18000b578  mov     r8d, r14d
0x18000b57b  mov     rdx, rdi
0x18000b57e  mov     rcx, r15
0x18000b581  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEAUHINSTANCE__@@I@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(HINSTANCE__ *,uint)
0x18000b586  jmp     short loc_18000B562
```
