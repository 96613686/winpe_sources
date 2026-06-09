# AslpFileGetImageResourceDirectoryRoot

- ea: `0x18004e6a4`
- end: `0x18004e8df`
- name: `AslpFileGetImageResourceDirectoryRoot`
- size: `571`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task`

## callers

- `0x18004f770`

## callees

- `0x18004c020`
- `0x18004e5d8`
- `0x18004e6a4`
- `0x180051438`

## string_xrefs

- `0x18004e6d8`: `AslpFileGetImageResourceDirectoryRoot`
- `0x18004e7c2`: `AslpFileGetImageResourceDirectoryRoot`
- `0x18004e8bf`: `AslpFileGetImageResourceDirectoryRoot`
- `0x18004e8ae`: `AslpFileGetImageNtHeader failed to get image headers or headers are out of bounds [%x]`
- `0x18004e7b6`: `Image PE optional header outside image`

## pseudocode

```c
__int64 __fastcall AslpFileGetImageResourceDirectoryRoot(unsigned __int64 *a1, unsigned __int64 a2, __int64 a3)
{
  bool v3; // zf
  unsigned __int64 v7; // rdi
  unsigned __int64 v8; // r14
  int ImageNtHeader; // ebx
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rbx
  _WORD *v12; // rax
  unsigned __int64 v13; // rdx
  unsigned int v14; // eax
  _DWORD *v15; // rsi
  __int64 v16; // r8
  unsigned __int64 v17; // rdx
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // [rsp+78h] [rbp+10h] BYREF

  v21 = a2;
  v3 = *(_DWORD *)(a3 + 56) == 6;
  v21 = 0;
  if ( !v3 )
  {
    AslLogCallPrintf(1, "AslpFileGetImageResourceDirectoryRoot", 1924, "File is not a PE image");
    return 3221225659LL;
  }
  v7 = *(_QWORD *)(a3 + 32);
  v8 = *(_QWORD *)(a3 + 40);
  ImageNtHeader = AslpFileGetImageNtHeader(&v21, a3);
  if ( ImageNtHeader < 0 )
    goto LABEL_47;
  if ( v21 < v7
    || (v10 = v21 + 8, v21 >= v21 + 8)
    || (v11 = v8 + v7, v21 > v8 + v7)
    || v10 < v7
    || v10 > v11
    || v7 > v11
    || v8 < 8 )
  {
    ImageNtHeader = -1073741266;
LABEL_47:
    AslLogCallPrintf(
      1,
      "AslpFileGetImageResourceDirectoryRoot",
      1937,
      "AslpFileGetImageNtHeader failed to get image headers or headers are out of bounds [%x]",
      ImageNtHeader);
    return (unsigned int)ImageNtHeader;
  }
  v12 = (_WORD *)(v21 + 24);
  if ( *(_WORD *)(v21 + 24) != 267 )
  {
    if ( *v12 == 523 && *(_WORD *)(v21 + 20) >= 0x70u )
    {
      if ( (unsigned __int64)v12 >= v7 )
      {
        v17 = v21 + 264;
        if ( v21 + 24 < v21 + 264 && (unsigned __int64)v12 <= v11 && v17 >= v7 && v17 <= v11 && v8 >= 0xF0 )
        {
          v14 = *(_DWORD *)(v21 + 132);
          v15 = (_DWORD *)(v21 + 152);
          goto LABEL_31;
        }
      }
      v16 = 1971;
LABEL_21:
      AslLogCallPrintf(1, "AslpFileGetImageResourceDirectoryRoot", v16, "Image PE optional header outside image");
      return 3221226030LL;
    }
    return 3221225595LL;
  }
  if ( *(_WORD *)(v21 + 20) < 0x60u )
    return 3221225595LL;
  if ( (unsigned __int64)v12 < v7
    || (v13 = v21 + 248, v21 + 24 >= v21 + 248)
    || (unsigned __int64)v12 > v11
    || v13 < v7
    || v13 > v11
    || v8 < 0xE0 )
  {
    v16 = 1955;
    goto LABEL_21;
  }
  v14 = *(_DWORD *)(v21 + 116);
  v15 = (_DWORD *)(v21 + 136);
LABEL_31:
  if ( v14 <= 2 || v15[1] < 0x10u || !*v15 )
    return 3221225609LL;
  v18 = AslpImageRvaToVa(v21, a3);
  if ( !v18 )
    return v18 != 0 ? -1073741266 : -1073741687;
  if ( v18 < v7 )
    return v18 != 0 ? -1073741266 : -1073741687;
  v19 = (unsigned int)v15[1];
  v20 = v19 + v18;
  if ( v18 > v19 + v18 || v18 > v11 || v20 < v7 || v20 > v11 || v19 > v8 )
    return v18 != 0 ? -1073741266 : -1073741687;
  *a1 = v18;
  return 0;
}

```

## disassembly

```asm
0x18004e6a4  mov     [rsp+arg_8], rdx
0x18004e6a9  push    rbx
0x18004e6aa  push    rbp
0x18004e6ab  push    rsi
0x18004e6ac  push    rdi
0x18004e6ad  push    r14
0x18004e6af  push    r15
0x18004e6b1  sub     rsp, 38h
0x18004e6b5  cmp     dword ptr [r8+38h], 6
0x18004e6ba  mov     rbp, r8
0x18004e6bd  mov     r15, rcx
0x18004e6c0  mov     [rsp+68h+arg_8], 0
0x18004e6c9  jz      short loc_18004E6F3
0x18004e6cb  lea     r9, aFileIsNotAPeIm; "File is not a PE image"
0x18004e6d2  mov     r8d, 784h
0x18004e6d8  lea     rdx, aAslpfilegetima_0; "AslpFileGetImageResourceDirectoryRoot"
0x18004e6df  mov     ecx, 1
0x18004e6e4  call    AslLogCallPrintf
0x18004e6e9  mov     eax, 0C00000BBh
0x18004e6ee  jmp     loc_18004E8D2
0x18004e6f3  mov     rdi, [r8+20h]
0x18004e6f7  lea     rcx, [rsp+68h+arg_8]
0x18004e6fc  mov     r14, [r8+28h]
0x18004e700  mov     rdx, rbp
0x18004e703  call    AslpFileGetImageNtHeader
0x18004e708  mov     ebx, eax
0x18004e70a  test    eax, eax
0x18004e70c  js      loc_18004E8AE
0x18004e712  mov     rcx, [rsp+68h+arg_8]
0x18004e717  cmp     rcx, rdi
0x18004e71a  jb      loc_18004E8A9
0x18004e720  lea     rax, [rcx+8]
0x18004e724  cmp     rcx, rax
0x18004e727  ja      loc_18004E8A9
0x18004e72d  lea     rbx, [r14+rdi]
0x18004e731  cmp     rcx, rbx
0x18004e734  ja      loc_18004E8A9
0x18004e73a  cmp     rax, rdi
0x18004e73d  jb      loc_18004E8A9
0x18004e743  cmp     rax, rbx
0x18004e746  ja      loc_18004E8A9
0x18004e74c  cmp     rdi, rbx
0x18004e74f  ja      loc_18004E8A9
0x18004e755  cmp     r14, 8
0x18004e759  jb      loc_18004E8A9
0x18004e75f  lea     rax, [rcx+18h]
0x18004e763  mov     edx, 10Bh
0x18004e768  cmp     [rax], dx
0x18004e76b  jnz     short loc_18004E7D8
0x18004e76d  cmp     word ptr [rcx+14h], 60h ; '`'
0x18004e772  jb      loc_18004E8A2
0x18004e778  cmp     rax, rdi
0x18004e77b  jb      short loc_18004E7B0
0x18004e77d  lea     rdx, [rax+0E0h]
0x18004e784  cmp     rax, rdx
0x18004e787  ja      short loc_18004E7B0
0x18004e789  cmp     rax, rbx
0x18004e78c  ja      short loc_18004E7B0
0x18004e78e  cmp     rdx, rdi
0x18004e791  jb      short loc_18004E7B0
0x18004e793  cmp     rdx, rbx
0x18004e796  ja      short loc_18004E7B0
0x18004e798  cmp     r14, 0E0h
0x18004e79f  jb      short loc_18004E7B0
0x18004e7a1  mov     eax, [rcx+74h]
0x18004e7a4  lea     rsi, [rcx+88h]
0x18004e7ab  jmp     loc_18004E833
0x18004e7b0  mov     r8d, 7A3h
0x18004e7b6  lea     r9, aImagePeOptiona; "Image PE optional header outside image"
0x18004e7bd  mov     ecx, 1
0x18004e7c2  lea     rdx, aAslpfilegetima_0; "AslpFileGetImageResourceDirectoryRoot"
0x18004e7c9  call    AslLogCallPrintf
0x18004e7ce  mov     eax, 0C000022Eh
0x18004e7d3  jmp     loc_18004E8D2
0x18004e7d8  mov     edx, 20Bh
0x18004e7dd  cmp     [rax], dx
0x18004e7e0  jnz     loc_18004E8A2
0x18004e7e6  cmp     word ptr [rcx+14h], 70h ; 'p'
0x18004e7eb  jb      loc_18004E8A2
0x18004e7f1  cmp     rax, rdi
0x18004e7f4  jb      loc_18004E897
0x18004e7fa  lea     rdx, [rax+0F0h]
0x18004e801  cmp     rax, rdx
0x18004e804  ja      loc_18004E897
0x18004e80a  cmp     rax, rbx
0x18004e80d  ja      loc_18004E897
0x18004e813  cmp     rdx, rdi
0x18004e816  jb      short loc_18004E897
0x18004e818  cmp     rdx, rbx
0x18004e81b  ja      short loc_18004E897
0x18004e81d  cmp     r14, 0F0h
0x18004e824  jb      short loc_18004E897
0x18004e826  mov     eax, [rcx+84h]
0x18004e82c  lea     rsi, [rcx+98h]
0x18004e833  cmp     eax, 2
0x18004e836  jbe     short loc_18004E890
0x18004e838  cmp     dword ptr [rsi+4], 10h
0x18004e83c  jb      short loc_18004E890
0x18004e83e  mov     r8d, [rsi]
0x18004e841  test    r8d, r8d
0x18004e844  jz      short loc_18004E890
0x18004e846  mov     rdx, rbp
0x18004e849  call    AslpImageRvaToVa
0x18004e84e  test    rax, rax
0x18004e851  jz      short loc_18004E87F
0x18004e853  cmp     rax, rdi
0x18004e856  jb      short loc_18004E87F
0x18004e858  mov     edx, [rsi+4]
0x18004e85b  lea     rcx, [rdx+rax]
0x18004e85f  cmp     rax, rcx
0x18004e862  ja      short loc_18004E87F
0x18004e864  cmp     rax, rbx
0x18004e867  ja      short loc_18004E87F
0x18004e869  cmp     rcx, rdi
0x18004e86c  jb      short loc_18004E87F
0x18004e86e  cmp     rcx, rbx
0x18004e871  ja      short loc_18004E87F
0x18004e873  cmp     rdx, r14
0x18004e876  ja      short loc_18004E87F
0x18004e878  mov     [r15], rax
0x18004e87b  xor     eax, eax
0x18004e87d  jmp     short loc_18004E8D2
0x18004e87f  neg     rax
0x18004e882  sbb     eax, eax
0x18004e884  and     eax, 1A5h
0x18004e889  add     eax, 0C0000089h
0x18004e88e  jmp     short loc_18004E8D2
0x18004e890  mov     eax, 0C0000089h
0x18004e895  jmp     short loc_18004E8D2
0x18004e897  mov     r8d, 7B3h
0x18004e89d  jmp     loc_18004E7B6
0x18004e8a2  mov     eax, 0C000007Bh
0x18004e8a7  jmp     short loc_18004E8D2
0x18004e8a9  mov     ebx, 0C000022Eh
0x18004e8ae  lea     r9, aAslpfilegetima_2; "AslpFileGetImageNtHeader failed to get "...
0x18004e8b5  mov     [rsp+68h+var_48], ebx
0x18004e8b9  mov     r8d, 791h
0x18004e8bf  lea     rdx, aAslpfilegetima_0; "AslpFileGetImageResourceDirectoryRoot"
0x18004e8c6  mov     ecx, 1
0x18004e8cb  call    AslLogCallPrintf
0x18004e8d0  mov     eax, ebx
0x18004e8d2  add     rsp, 38h
0x18004e8d6  pop     r15
0x18004e8d8  pop     r14
0x18004e8da  pop     rdi
0x18004e8db  pop     rsi
0x18004e8dc  pop     rbp
0x18004e8dd  pop     rbx
0x18004e8de  retn
```
