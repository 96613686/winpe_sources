# AslpFileGetImageResourceDirectoryRoot

- ea: `0x180057380`
- end: `0x1800575bb`
- name: `AslpFileGetImageResourceDirectoryRoot`
- size: `571`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task`

## callers

- `0x18005844c`

## callees

- `0x1800543c0`
- `0x1800572b4`
- `0x180057380`
- `0x18005980c`

## string_xrefs

- `0x18005758a`: `AslpFileGetImageNtHeader failed to get image headers or headers are out of bounds [%x]`
- `0x1800573b4`: `AslpFileGetImageResourceDirectoryRoot`
- `0x18005749e`: `AslpFileGetImageResourceDirectoryRoot`
- `0x18005759b`: `AslpFileGetImageResourceDirectoryRoot`
- `0x180057492`: `Image PE optional header outside image`

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
0x180057380  mov     [rsp+arg_8], rdx
0x180057385  push    rbx
0x180057386  push    rbp
0x180057387  push    rsi
0x180057388  push    rdi
0x180057389  push    r14
0x18005738b  push    r15
0x18005738d  sub     rsp, 38h
0x180057391  cmp     dword ptr [r8+38h], 6
0x180057396  mov     rbp, r8
0x180057399  mov     r15, rcx
0x18005739c  mov     [rsp+68h+arg_8], 0
0x1800573a5  jz      short loc_1800573CF
0x1800573a7  lea     r9, aFileIsNotAPeIm; "File is not a PE image"
0x1800573ae  mov     r8d, 784h
0x1800573b4  lea     rdx, aAslpfilegetima_0; "AslpFileGetImageResourceDirectoryRoot"
0x1800573bb  mov     ecx, 1
0x1800573c0  call    AslLogCallPrintf
0x1800573c5  mov     eax, 0C00000BBh
0x1800573ca  jmp     loc_1800575AE
0x1800573cf  mov     rdi, [r8+20h]
0x1800573d3  lea     rcx, [rsp+68h+arg_8]
0x1800573d8  mov     r14, [r8+28h]
0x1800573dc  mov     rdx, rbp
0x1800573df  call    AslpFileGetImageNtHeader
0x1800573e4  mov     ebx, eax
0x1800573e6  test    eax, eax
0x1800573e8  js      loc_18005758A
0x1800573ee  mov     rcx, [rsp+68h+arg_8]
0x1800573f3  cmp     rcx, rdi
0x1800573f6  jb      loc_180057585
0x1800573fc  lea     rax, [rcx+8]
0x180057400  cmp     rcx, rax
0x180057403  ja      loc_180057585
0x180057409  lea     rbx, [r14+rdi]
0x18005740d  cmp     rcx, rbx
0x180057410  ja      loc_180057585
0x180057416  cmp     rax, rdi
0x180057419  jb      loc_180057585
0x18005741f  cmp     rax, rbx
0x180057422  ja      loc_180057585
0x180057428  cmp     rdi, rbx
0x18005742b  ja      loc_180057585
0x180057431  cmp     r14, 8
0x180057435  jb      loc_180057585
0x18005743b  lea     rax, [rcx+18h]
0x18005743f  mov     edx, 10Bh
0x180057444  cmp     [rax], dx
0x180057447  jnz     short loc_1800574B4
0x180057449  cmp     word ptr [rcx+14h], 60h ; '`'
0x18005744e  jb      loc_18005757E
0x180057454  cmp     rax, rdi
0x180057457  jb      short loc_18005748C
0x180057459  lea     rdx, [rax+0E0h]
0x180057460  cmp     rax, rdx
0x180057463  ja      short loc_18005748C
0x180057465  cmp     rax, rbx
0x180057468  ja      short loc_18005748C
0x18005746a  cmp     rdx, rdi
0x18005746d  jb      short loc_18005748C
0x18005746f  cmp     rdx, rbx
0x180057472  ja      short loc_18005748C
0x180057474  cmp     r14, 0E0h
0x18005747b  jb      short loc_18005748C
0x18005747d  mov     eax, [rcx+74h]
0x180057480  lea     rsi, [rcx+88h]
0x180057487  jmp     loc_18005750F
0x18005748c  mov     r8d, 7A3h
0x180057492  lea     r9, aImagePeOptiona; "Image PE optional header outside image"
0x180057499  mov     ecx, 1
0x18005749e  lea     rdx, aAslpfilegetima_0; "AslpFileGetImageResourceDirectoryRoot"
0x1800574a5  call    AslLogCallPrintf
0x1800574aa  mov     eax, 0C000022Eh
0x1800574af  jmp     loc_1800575AE
0x1800574b4  mov     edx, 20Bh
0x1800574b9  cmp     [rax], dx
0x1800574bc  jnz     loc_18005757E
0x1800574c2  cmp     word ptr [rcx+14h], 70h ; 'p'
0x1800574c7  jb      loc_18005757E
0x1800574cd  cmp     rax, rdi
0x1800574d0  jb      loc_180057573
0x1800574d6  lea     rdx, [rax+0F0h]
0x1800574dd  cmp     rax, rdx
0x1800574e0  ja      loc_180057573
0x1800574e6  cmp     rax, rbx
0x1800574e9  ja      loc_180057573
0x1800574ef  cmp     rdx, rdi
0x1800574f2  jb      short loc_180057573
0x1800574f4  cmp     rdx, rbx
0x1800574f7  ja      short loc_180057573
0x1800574f9  cmp     r14, 0F0h
0x180057500  jb      short loc_180057573
0x180057502  mov     eax, [rcx+84h]
0x180057508  lea     rsi, [rcx+98h]
0x18005750f  cmp     eax, 2
0x180057512  jbe     short loc_18005756C
0x180057514  cmp     dword ptr [rsi+4], 10h
0x180057518  jb      short loc_18005756C
0x18005751a  mov     r8d, [rsi]
0x18005751d  test    r8d, r8d
0x180057520  jz      short loc_18005756C
0x180057522  mov     rdx, rbp
0x180057525  call    AslpImageRvaToVa
0x18005752a  test    rax, rax
0x18005752d  jz      short loc_18005755B
0x18005752f  cmp     rax, rdi
0x180057532  jb      short loc_18005755B
0x180057534  mov     edx, [rsi+4]
0x180057537  lea     rcx, [rdx+rax]
0x18005753b  cmp     rax, rcx
0x18005753e  ja      short loc_18005755B
0x180057540  cmp     rax, rbx
0x180057543  ja      short loc_18005755B
0x180057545  cmp     rcx, rdi
0x180057548  jb      short loc_18005755B
0x18005754a  cmp     rcx, rbx
0x18005754d  ja      short loc_18005755B
0x18005754f  cmp     rdx, r14
0x180057552  ja      short loc_18005755B
0x180057554  mov     [r15], rax
0x180057557  xor     eax, eax
0x180057559  jmp     short loc_1800575AE
0x18005755b  neg     rax
0x18005755e  sbb     eax, eax
0x180057560  and     eax, 1A5h
0x180057565  add     eax, 0C0000089h
0x18005756a  jmp     short loc_1800575AE
0x18005756c  mov     eax, 0C0000089h
0x180057571  jmp     short loc_1800575AE
0x180057573  mov     r8d, 7B3h
0x180057579  jmp     loc_180057492
0x18005757e  mov     eax, 0C000007Bh
0x180057583  jmp     short loc_1800575AE
0x180057585  mov     ebx, 0C000022Eh
0x18005758a  lea     r9, aAslpfilegetima_2; "AslpFileGetImageNtHeader failed to get "...
0x180057591  mov     [rsp+68h+var_48], ebx
0x180057595  mov     r8d, 791h
0x18005759b  lea     rdx, aAslpfilegetima_0; "AslpFileGetImageResourceDirectoryRoot"
0x1800575a2  mov     ecx, 1
0x1800575a7  call    AslLogCallPrintf
0x1800575ac  mov     eax, ebx
0x1800575ae  add     rsp, 38h
0x1800575b2  pop     r15
0x1800575b4  pop     r14
0x1800575b6  pop     rdi
0x1800575b7  pop     rsi
0x1800575b8  pop     rbp
0x1800575b9  pop     rbx
0x1800575ba  retn
```
