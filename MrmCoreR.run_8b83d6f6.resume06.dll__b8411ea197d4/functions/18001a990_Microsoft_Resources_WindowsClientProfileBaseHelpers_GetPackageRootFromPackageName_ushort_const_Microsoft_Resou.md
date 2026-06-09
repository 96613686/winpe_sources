# Microsoft::Resources::WindowsClientProfileBaseHelpers::GetPackageRootFromPackageName(ushort const *,Microsoft::Resources::StringResult *)

- ea: `0x18001a990`
- end: `0x18001aaa0`
- name: `?GetPackageRootFromPackageName@WindowsClientProfileBaseHelpers@Resources@Microsoft@@UEAAJPEBGPEAVStringResult@23@@Z`
- size: `272`
- prototype: `int(Microsoft::Resources::WindowsClientProfileBaseHelpers *__hidden this, const unsigned __int16 *, struct Microsoft::Resources::StringResult *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18001a990`
- `0x18001aaa8`
- `0x18001aafc`
- `0x180028510`
- `0x1800862f0`
- `0x180086800`
- `0x18008680c`

## import_xrefs

- `KERNELBASE!GetStagedPackagePathByFullName2` at `0x18001a9db`
- `KERNELBASE!GetStagedPackagePathByFullName2` at `0x18001a9db`
- `KERNELBASE!GetPackagePathByFullName2` at `0x18001aa32`
- `KERNELBASE!GetPackagePathByFullName2` at `0x18001aa32`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::WindowsClientProfileBaseHelpers::GetPackageRootFromPackageName(
        Microsoft::Resources::WindowsClientProfileBaseHelpers *this,
        Microsoft::Resources *a2,
        struct Microsoft::Resources::StringResult *a3)
{
  signed int StagedPackagePathByFullName2; // eax
  signed int PackagePathByFullName; // ebx
  unsigned int *v7; // rdi
  unsigned __int64 v9; // rax
  unsigned int *v10; // rax
  unsigned __int16 *v11; // r9
  unsigned __int16 v12[2]; // [rsp+20h] [rbp-248h] BYREF
  _BYTE Block[528]; // [rsp+30h] [rbp-238h] BYREF

  *(_DWORD *)v12 = 260;
  if ( Microsoft::Resources::HasPackageContentsCapability(this) )
    StagedPackagePathByFullName2 = GetStagedPackagePathByFullName2(a2, 2, v12, Block);
  else
    StagedPackagePathByFullName2 = GetPackagePathByFullName2(a2, 2, v12, Block);
  PackagePathByFullName = StagedPackagePathByFullName2;
  if ( StagedPackagePathByFullName2 == 122 )
  {
    v9 = 2LL * *(unsigned int *)v12;
    if ( !is_mul_ok(*(unsigned int *)v12, 2u) )
      v9 = -1;
    v10 = (unsigned int *)operator new[](v9, (const struct std::nothrow_t *)&unk_1800DFCD8);
    v7 = v10;
    if ( !v10 )
      return 2147942414LL;
    PackagePathByFullName = Microsoft::Resources::GetPackagePathByFullName(a2, v12, v10, v11);
  }
  else
  {
    v7 = (unsigned int *)Block;
  }
  if ( PackagePathByFullName )
  {
    if ( PackagePathByFullName > 0 )
      PackagePathByFullName = (unsigned __int16)PackagePathByFullName | 0x80070000;
  }
  else
  {
    PackagePathByFullName = DefStringResult_SetCopy(*(_QWORD *)a3, v7);
  }
  if ( v7 != (unsigned int *)Block )
    operator delete(v7);
  return (unsigned int)PackagePathByFullName;
}

```

## disassembly

```asm
0x18001a990  mov     [rsp+arg_0], rbx
0x18001a995  push    rsi
0x18001a996  push    rdi
0x18001a997  push    r14
0x18001a999  sub     rsp, 250h
0x18001a9a0  mov     rax, cs:__security_cookie
0x18001a9a7  xor     rax, rsp
0x18001a9aa  mov     [rsp+268h+var_28], rax
0x18001a9b2  mov     r14, r8
0x18001a9b5  mov     dword ptr [rsp+268h+var_248], 104h
0x18001a9bd  mov     rsi, rdx
0x18001a9c0  call    ?HasPackageContentsCapability@Resources@Microsoft@@YA_NXZ; Microsoft::Resources::HasPackageContentsCapability(void)
0x18001a9c5  lea     r9, [rsp+268h+Block]
0x18001a9ca  mov     edx, 2
0x18001a9cf  lea     r8, [rsp+268h+var_248]
0x18001a9d4  mov     rcx, rsi
0x18001a9d7  test    al, al
0x18001a9d9  jz      short loc_18001AA32
0x18001a9db  call    cs:__imp_GetStagedPackagePathByFullName2
0x18001a9e1  mov     ebx, eax
0x18001a9e3  cmp     eax, 7Ah ; 'z'
0x18001a9e6  jz      short loc_18001AA47
0x18001a9e8  lea     rdi, [rsp+268h+Block]
0x18001a9ed  test    ebx, ebx
0x18001a9ef  jnz     short loc_18001AA3A
0x18001a9f1  mov     rcx, [r14]
0x18001a9f4  mov     rdx, rdi
0x18001a9f7  call    DefStringResult_SetCopy
0x18001a9fc  mov     ebx, eax
0x18001a9fe  lea     rax, [rsp+268h+Block]
0x18001aa03  cmp     rdi, rax
0x18001aa06  jnz     loc_18001AA93
0x18001aa0c  mov     eax, ebx
0x18001aa0e  mov     rcx, [rsp+268h+var_28]
0x18001aa16  xor     rcx, rsp; StackCookie
0x18001aa19  call    __security_check_cookie
0x18001aa1e  mov     rbx, [rsp+268h+arg_0]
0x18001aa26  add     rsp, 250h
0x18001aa2d  pop     r14
0x18001aa2f  pop     rdi
0x18001aa30  pop     rsi
0x18001aa31  retn
0x18001aa32  call    cs:__imp_GetPackagePathByFullName2
0x18001aa38  jmp     short loc_18001A9E1
0x18001aa3a  jle     short loc_18001A9FE
0x18001aa3c  movzx   ebx, bx
0x18001aa3f  or      ebx, 80070000h
0x18001aa45  jmp     short loc_18001A9FE
0x18001aa47  mov     ecx, dword ptr [rsp+268h+var_248]
0x18001aa4b  mov     eax, 2
0x18001aa50  mul     rcx
0x18001aa53  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001aa5a  lea     rdx, unk_1800DFCD8; struct std::nothrow_t *
0x18001aa61  cmovb   rax, rcx
0x18001aa65  mov     rcx, rax; unsigned __int64
0x18001aa68  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001aa6d  mov     rdi, rax
0x18001aa70  test    rax, rax
0x18001aa73  jnz     short loc_18001AA7C
0x18001aa75  mov     eax, 8007000Eh
0x18001aa7a  jmp     short loc_18001AA0E
0x18001aa7c  mov     r8, rax; unsigned int *
0x18001aa7f  lea     rdx, [rsp+268h+var_248]; unsigned __int16 *
0x18001aa84  mov     rcx, rsi; this
0x18001aa87  call    ?GetPackagePathByFullName@Resources@Microsoft@@YAJPEBGPEAIPEAG@Z; Microsoft::Resources::GetPackagePathByFullName(ushort const *,uint *,ushort *)
0x18001aa8c  mov     ebx, eax
0x18001aa8e  jmp     loc_18001A9ED
0x18001aa93  mov     rcx, rdi; Block
0x18001aa96  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001aa9b  jmp     loc_18001AA0C
```
