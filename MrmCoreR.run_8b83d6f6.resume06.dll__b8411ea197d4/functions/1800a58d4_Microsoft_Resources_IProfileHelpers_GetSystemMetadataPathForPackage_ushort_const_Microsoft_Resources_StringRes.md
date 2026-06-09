# Microsoft::Resources::IProfileHelpers::GetSystemMetadataPathForPackage(ushort const *,Microsoft::Resources::StringResult *)

- ea: `0x1800a58d4`
- end: `0x1800a59c3`
- name: `?GetSystemMetadataPathForPackage@IProfileHelpers@Resources@Microsoft@@SAJPEBGPEAVStringResult@23@@Z`
- size: `239`
- prototype: `static int(const unsigned __int16 *, struct Microsoft::Resources::StringResult *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800172a0`
- `0x1800564e0`

## callees

- `0x180028510`
- `0x18002c8d0`
- `0x180086800`
- `0x18008680c`
- `0x1800a58d4`

## import_xrefs

- `KERNELBASE!GetSystemMetadataPathForPackage` at `0x1800a58f8`
- `KERNELBASE!GetSystemMetadataPathForPackage` at `0x1800a5958`
- `KERNELBASE!GetSystemMetadataPathForPackage` at `0x1800a58f8`
- `KERNELBASE!GetSystemMetadataPathForPackage` at `0x1800a5958`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::IProfileHelpers::GetSystemMetadataPathForPackage(
        const unsigned __int16 *a1,
        struct Microsoft::Resources::StringResult *a2)
{
  __int64 result; // rax
  unsigned __int64 v5; // rax
  void *v6; // rax
  void *v7; // rdi
  int SystemMetadataPathForPackage; // ebx
  int v9; // eax
  int v10; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned int v12; // [rsp+40h] [rbp+18h] BYREF

  v12 = 0;
  result = GetSystemMetadataPathForPackage(a1, &v12, 0);
  if ( (_DWORD)result == 122 )
  {
    v5 = 2LL * v12;
    if ( !is_mul_ok(v12, 2u) )
      v5 = -1;
    v6 = operator new[](v5, (const struct std::nothrow_t *)&unk_1800DFCD8);
    v7 = v6;
    if ( !v6 )
      return 2147942414LL;
    SystemMetadataPathForPackage = GetSystemMetadataPathForPackage(a1, &v12, v6);
    if ( SystemMetadataPathForPackage )
    {
      operator delete(v7);
      if ( SystemMetadataPathForPackage > 0 )
        return (unsigned __int16)SystemMetadataPathForPackage | 0x80070000;
    }
    else
    {
      v9 = DefStringResult_SetCopy(*(_QWORD *)a2, v7);
      SystemMetadataPathForPackage = v9;
      if ( v9 >= 0 )
      {
        operator delete(v7);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x929,
        (unsigned int)"onecoreuap\\base\\mrt\\mrm\\src\\clientprofiles.cpp",
        (const char *)(unsigned int)v9,
        v10);
    }
    return (unsigned int)SystemMetadataPathForPackage;
  }
  if ( (int)result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800a58d4  mov     rax, rsp
0x1800a58d7  mov     [rax+8], rbx
0x1800a58db  mov     [rax+10h], rsi
0x1800a58df  push    rdi; int
0x1800a58e0  sub     rsp, 20h
0x1800a58e4  mov     rsi, rdx
0x1800a58e7  mov     dword ptr [rax+18h], 0
0x1800a58ee  lea     rdx, [rax+18h]
0x1800a58f2  xor     r8d, r8d
0x1800a58f5  mov     rbx, rcx
0x1800a58f8  call    cs:__imp_GetSystemMetadataPathForPackage
0x1800a58fe  cmp     eax, 7Ah ; 'z'
0x1800a5901  jz      short loc_1800A5918
0x1800a5903  test    eax, eax
0x1800a5905  jle     loc_1800A59B3
0x1800a590b  movzx   eax, ax
0x1800a590e  or      eax, 80070000h
0x1800a5913  jmp     loc_1800A59B3
0x1800a5918  mov     ecx, [rsp+28h+arg_10]
0x1800a591c  mov     eax, 2
0x1800a5921  mul     rcx
0x1800a5924  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800a592b  lea     rdx, unk_1800DFCD8; struct std::nothrow_t *
0x1800a5932  cmovb   rax, rcx
0x1800a5936  mov     rcx, rax; unsigned __int64
0x1800a5939  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800a593e  mov     rdi, rax
0x1800a5941  test    rax, rax
0x1800a5944  jnz     short loc_1800A594D
0x1800a5946  mov     eax, 8007000Eh
0x1800a594b  jmp     short loc_1800A59B3
0x1800a594d  mov     r8, rdi
0x1800a5950  lea     rdx, [rsp+28h+arg_10]
0x1800a5955  mov     rcx, rbx
0x1800a5958  call    cs:__imp_GetSystemMetadataPathForPackage
0x1800a595e  mov     ebx, eax
0x1800a5960  test    eax, eax
0x1800a5962  jz      short loc_1800A597D
0x1800a5964  mov     rcx, rdi; Block
0x1800a5967  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a596c  test    ebx, ebx
0x1800a596e  jle     short loc_1800A5979
0x1800a5970  movzx   ebx, bx
0x1800a5973  or      ebx, 80070000h
0x1800a5979  mov     eax, ebx
0x1800a597b  jmp     short loc_1800A59B3
0x1800a597d  mov     rcx, [rsi]
0x1800a5980  mov     rdx, rdi
0x1800a5983  call    DefStringResult_SetCopy
0x1800a5988  mov     ebx, eax
0x1800a598a  test    eax, eax
0x1800a598c  jns     short loc_1800A59A9
0x1800a598e  mov     rcx, [rsp+28h]; this
0x1800a5993  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\mrt\\mrm\\src\\client"...
0x1800a599a  mov     r9d, eax; char *
0x1800a599d  mov     edx, 929h; void *
0x1800a59a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a59a7  jmp     short loc_1800A5979
0x1800a59a9  mov     rcx, rdi; Block
0x1800a59ac  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800a59b1  xor     eax, eax
0x1800a59b3  mov     rbx, [rsp+28h+arg_0]
0x1800a59b8  mov     rsi, [rsp+28h+arg_8]
0x1800a59bd  add     rsp, 20h
0x1800a59c1  pop     rdi
0x1800a59c2  retn
```
