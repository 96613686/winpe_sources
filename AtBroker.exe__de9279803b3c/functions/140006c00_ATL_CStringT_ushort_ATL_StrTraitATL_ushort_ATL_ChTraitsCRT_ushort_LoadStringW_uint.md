# ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(uint)

- ea: `0x140006c00`
- end: `0x140006d04`
- name: `?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHI@Z`
- size: `260`
- prototype: `__int64 __fastcall(ATL::CAtlBaseModule *, unsigned int)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x14000b250`
- `0x14000c19c`
- `0x14000ced0`
- `0x14000ea38`
- `0x140010c6c`

## callees

- `0x140006c00`
- `0x140006d0c`
- `0x14000bcc0`

## import_xrefs

- `KERNEL32!SizeofResource` at `0x140006c88`
- `KERNEL32!SizeofResource` at `0x140006c88`
- `KERNEL32!LockResource` at `0x140006c74`
- `KERNEL32!LockResource` at `0x140006c74`
- `KERNEL32!FindResourceExW` at `0x140006c4e`
- `KERNEL32!FindResourceExW` at `0x140006c4e`
- `KERNEL32!LoadResource` at `0x140006c62`
- `KERNEL32!LoadResource` at `0x140006c62`

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
0x140006c00  push    rbx
0x140006c02  push    rbp
0x140006c03  push    rsi
0x140006c04  push    rdi
0x140006c05  push    r12
0x140006c07  push    r13
0x140006c09  push    r14
0x140006c0b  push    r15
0x140006c0d  sub     rsp, 28h
0x140006c11  mov     r14d, edx
0x140006c14  mov     r15, rcx
0x140006c17  xor     edx, edx; int
0x140006c19  call    ?GetHInstanceAt@CAtlBaseModule@ATL@@QEAAPEAUHINSTANCE__@@H@Z; ATL::CAtlBaseModule::GetHInstanceAt(int)
0x140006c1e  mov     r13d, 1
0x140006c24  mov     rdi, rax
0x140006c27  mov     ebp, r13d
0x140006c2a  test    rax, rax
0x140006c2d  jz      loc_140006CDC
0x140006c33  mov     eax, r14d
0x140006c36  shr     eax, 4
0x140006c39  add     ax, r13w
0x140006c3d  movzx   r12d, ax
0x140006c41  xor     r9d, r9d; wLanguage
0x140006c44  mov     r8, r12; lpName
0x140006c47  mov     rcx, rdi; hModule
0x140006c4a  lea     edx, [r9+6]; lpType
0x140006c4e  call    cs:__imp_FindResourceExW
0x140006c54  mov     rsi, rax
0x140006c57  test    rax, rax
0x140006c5a  jz      short loc_140006CC6
0x140006c5c  mov     rdx, rax; hResInfo
0x140006c5f  mov     rcx, rdi; hModule
0x140006c62  call    cs:__imp_LoadResource
0x140006c68  test    rax, rax
0x140006c6b  jnz     short loc_140006C71
0x140006c6d  xor     eax, eax
0x140006c6f  jmp     short loc_140006CC1
0x140006c71  mov     rcx, rax; hResData
0x140006c74  call    cs:__imp_LockResource
0x140006c7a  mov     rbx, rax
0x140006c7d  test    rax, rax
0x140006c80  jz      short loc_140006C6D
0x140006c82  mov     rdx, rsi; hResInfo
0x140006c85  mov     rcx, rdi; hModule
0x140006c88  call    cs:__imp_SizeofResource
0x140006c8e  mov     ecx, eax
0x140006c90  mov     edx, r14d
0x140006c93  add     rcx, rbx; this
0x140006c96  and     edx, 0Fh
0x140006c99  jbe     short loc_140006CB0
0x140006c9b  cmp     rbx, rcx
0x140006c9e  jnb     short loc_140006C6D
0x140006ca0  movzx   eax, word ptr [rbx]
0x140006ca3  lea     rbx, [rbx+rax*2]
0x140006ca7  add     rbx, 2
0x140006cab  add     edx, 0FFFFFFFFh
0x140006cae  jnz     short loc_140006C9B
0x140006cb0  cmp     rbx, rcx
0x140006cb3  jnb     short loc_140006C6D
0x140006cb5  movzx   eax, word ptr [rbx]
0x140006cb8  neg     ax
0x140006cbb  sbb     rax, rax
0x140006cbe  and     rax, rbx
0x140006cc1  test    rax, rax
0x140006cc4  jnz     short loc_140006CEF
0x140006cc6  mov     edx, ebp; int
0x140006cc8  add     ebp, r13d
0x140006ccb  call    ?GetHInstanceAt@CAtlBaseModule@ATL@@QEAAPEAUHINSTANCE__@@H@Z; ATL::CAtlBaseModule::GetHInstanceAt(int)
0x140006cd0  mov     rdi, rax
0x140006cd3  test    rax, rax
0x140006cd6  jnz     loc_140006C41
0x140006cdc  xor     eax, eax
0x140006cde  add     rsp, 28h
0x140006ce2  pop     r15
0x140006ce4  pop     r14
0x140006ce6  pop     r13
0x140006ce8  pop     r12
0x140006cea  pop     rdi
0x140006ceb  pop     rsi
0x140006cec  pop     rbp
0x140006ced  pop     rbx
0x140006cee  retn
0x140006cef  test    rdi, rdi
0x140006cf2  jz      short loc_140006CDC
0x140006cf4  mov     r8d, r14d
0x140006cf7  mov     rdx, rdi
0x140006cfa  mov     rcx, r15
0x140006cfd  call    ?LoadStringW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEAUHINSTANCE__@@I@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::LoadStringW(HINSTANCE__ *,uint)
0x140006d02  jmp     short loc_140006CDE
```
