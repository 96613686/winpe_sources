# AslpFileGetVersionBlockImageOnly

- ea: `0x140055540`
- end: `0x1400557d4`
- name: `AslpFileGetVersionBlockImageOnly`
- size: `660`
- prototype: `__int64 __fastcall(_QWORD *, unsigned __int16 **, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140025b04`

## callees

- `0x140006c10`
- `0x140007b40`
- `0x1400355e8`
- `0x140035a68`
- `0x14003e364`
- `0x140045d44`
- `0x14004ae38`
- `0x14005498c`
- `0x140055540`

## string_xrefs

- `0x140055613`: `AslpFileGetImageResourceDirectoryRoot failed to get resource directory root [%x]`
- `0x14005566f`: `AslpFileGetVersionBlockFromResourceRoot failed to get version block from resource directory [%x]`

## pseudocode

```c
__int64 __fastcall AslpFileGetVersionBlockImageOnly(_QWORD *a1, unsigned __int16 **a2, __int64 a3, __int64 a4)
{
  __int64 v7; // rdx
  unsigned __int16 v8; // ax
  unsigned __int16 *v9; // rdx
  unsigned __int16 *v10; // rcx
  unsigned int v11; // ebx
  int v12; // eax
  __int64 v13; // rdx
  int ImageResourceDirectoryRoot; // eax
  const char *v15; // r9
  __int64 v16; // r8
  int VersionBlockFromResourceRoot; // eax
  unsigned __int64 v18; // r14
  __int64 v19; // rdx
  __int64 v20; // rcx
  unsigned __int16 *v21; // rax
  unsigned __int16 *v22; // rsi
  unsigned __int16 *v23; // rcx
  size_t Size[7]; // [rsp+40h] [rbp-38h] BYREF
  void *Src; // [rsp+90h] [rbp+18h] BYREF
  __int64 v28; // [rsp+98h] [rbp+20h] BYREF

  v28 = 0;
  Src = 0;
  Size[0] = 0;
  v7 = *(_QWORD *)(a4 + 72);
  if ( v7 )
  {
    v8 = *(_WORD *)(v7 + 2);
    v9 = (unsigned __int16 *)(v7 + 40);
    v10 = 0;
    if ( v8 >= 0x34u )
      v10 = v9;
    *a2 = v10;
    *a1 = *(_QWORD *)(a4 + 72);
    return 0;
  }
  v12 = AslFileMappingEnsure(a4);
  v11 = v12;
  if ( v12 < 0 )
  {
    AslLogCallPrintf(1, "AslpFileGetVersionBlockImageOnly", 2288, "AslFileMappingEnsure failed [%x]", v12);
    return v11;
  }
  if ( *(_DWORD *)(a4 + 64) != 6 )
    return (unsigned int)-1073741687;
  ImageResourceDirectoryRoot = AslpFileGetImageResourceDirectoryRoot(&v28, v13, a4);
  v11 = ImageResourceDirectoryRoot;
  if ( ImageResourceDirectoryRoot < 0 )
  {
    if ( (unsigned int)(ImageResourceDirectoryRoot + 1073741687) <= 2 )
      return v11;
    v15 = "AslpFileGetImageResourceDirectoryRoot failed to get resource directory root [%x]";
    v16 = 2315;
LABEL_12:
    AslLogCallPrintf(1, "AslpFileGetVersionBlockImageOnly", v16, v15, v11);
    return v11;
  }
  VersionBlockFromResourceRoot = AslpFileGetVersionBlockFromResourceRoot(&Src, Size, v28, a4);
  v11 = VersionBlockFromResourceRoot;
  if ( VersionBlockFromResourceRoot < 0 )
  {
    if ( (unsigned int)(VersionBlockFromResourceRoot + 1073741687) <= 2 )
      return v11;
    v15 = "AslpFileGetVersionBlockFromResourceRoot failed to get version block from resource directory [%x]";
    v16 = 2323;
    goto LABEL_12;
  }
  v18 = Size[0];
  if ( !Size[0] )
    return (unsigned int)-1073741687;
  if ( !Src )
  {
    AslLogCallPrintf(
      1,
      "AslpFileGetVersionBlockImageOnly",
      2335,
      "AslpFileGetVersionBlockFromResourceRoot returned null version block with status [%x]",
      VersionBlockFromResourceRoot);
    return (unsigned int)-1073741687;
  }
  if ( Size[0] > 0x7FFF )
  {
    AslLogCallPrintf(
      1,
      "AslpFileGetVersionBlockImageOnly",
      2341,
      "AslpFileGetVersionBlockFromResourceRoot returned version block size that is too large");
    return (unsigned int)-1073741687;
  }
  if ( !(unsigned __int8)AslpMemoryCheckBounds(Src, Size[0], *(_QWORD *)(a4 + 32), *(_QWORD *)(a4 + 40)) )
  {
    AslLogCallPrintf(1, "AslpFileGetVersionBlockImageOnly", 2350, "Version block out of range");
    return (unsigned int)-1073741687;
  }
  v21 = (unsigned __int16 *)AslAlloc(v20, v19, 1);
  v22 = v21;
  if ( v21 )
  {
    memmove(v21, Src, v18);
    if ( v18 < *v22 )
      *v22 = v18;
    v23 = v22 + 20;
    if ( v22[1] < 0x34u )
      v23 = 0;
    *a2 = v23;
    *a1 = v22;
    *(_QWORD *)(a4 + 72) = v22;
    return 0;
  }
  else
  {
    return (unsigned int)-1073741801;
  }
}

```

## disassembly

```asm
0x140055540  mov     rax, rsp
0x140055543  mov     [rax+10h], rbx
0x140055547  mov     [rax+18h], r8
0x14005554b  mov     [rax+8], rcx
0x14005554f  push    rsi
0x140055550  push    rdi
0x140055551  push    r13
0x140055553  push    r14
0x140055555  push    r15
0x140055557  sub     rsp, 50h
0x14005555b  mov     r15, r9
0x14005555e  mov     r13, rdx
0x140055561  mov     r8, rcx
0x140055564  xor     edi, edi
0x140055566  mov     [rax+20h], rdi
0x14005556a  mov     [rax+18h], rdi
0x14005556e  mov     esi, edi
0x140055570  mov     [rax-40h], rdi
0x140055574  mov     [rax-38h], rdi
0x140055578  mov     rdx, [r9+48h]
0x14005557c  test    rdx, rdx
0x14005557f  jz      short loc_1400555A5
0x140055581  movzx   eax, word ptr [rdx+2]
0x140055585  add     rdx, 28h ; '('
0x140055589  mov     ecx, edi
0x14005558b  cmp     ax, 34h ; '4'
0x14005558f  cmovnb  rcx, rdx
0x140055593  mov     [r13+0], rcx
0x140055597  mov     rax, [r9+48h]
0x14005559b  mov     [r8], rax
0x14005559e  mov     ebx, edi
0x1400555a0  jmp     loc_1400557AF
0x1400555a5  mov     rcx, r15
0x1400555a8  call    AslFileMappingEnsure
0x1400555ad  mov     ebx, eax
0x1400555af  test    eax, eax
0x1400555b1  jns     short loc_1400555DA
0x1400555b3  mov     [rsp+78h+var_58], eax
0x1400555b7  lea     r9, aAslfilemapping_1; "AslFileMappingEnsure failed [%x]"
0x1400555be  mov     r8d, 8F0h
0x1400555c4  lea     rdx, aAslpfilegetver_8; "AslpFileGetVersionBlockImageOnly"
0x1400555cb  mov     ecx, 1
0x1400555d0  call    AslLogCallPrintf
0x1400555d5  jmp     loc_1400557AF
0x1400555da  cmp     dword ptr [r15+40h], 6
0x1400555df  jz      short loc_1400555EB
0x1400555e1  mov     ebx, 0C0000089h
0x1400555e6  jmp     loc_1400557AF
0x1400555eb  mov     r8, r15
0x1400555ee  lea     rcx, [rsp+78h+arg_18]
0x1400555f6  call    AslpFileGetImageResourceDirectoryRoot
0x1400555fb  mov     ebx, eax
0x1400555fd  mov     [rsp+78h+var_48], eax
0x140055601  test    eax, eax
0x140055603  jns     short loc_14005563A
0x140055605  add     eax, 3FFFFF77h
0x14005560a  cmp     eax, 2
0x14005560d  jbe     loc_140055780
0x140055613  lea     r9, aAslpfilegetima; "AslpFileGetImageResourceDirectoryRoot f"...
0x14005561a  mov     r8d, 90Bh
0x140055620  mov     [rsp+78h+var_58], ebx
0x140055624  lea     rdx, aAslpfilegetver_8; "AslpFileGetVersionBlockImageOnly"
0x14005562b  mov     ecx, 1
0x140055630  call    AslLogCallPrintf
0x140055635  jmp     loc_140055780
0x14005563a  mov     r9, r15
0x14005563d  mov     r8, [rsp+78h+arg_18]
0x140055645  lea     rdx, [rsp+78h+Size]
0x14005564a  lea     rcx, [rsp+78h+Src]
0x140055652  call    AslpFileGetVersionBlockFromResourceRoot
0x140055657  mov     ebx, eax
0x140055659  mov     [rsp+78h+var_48], eax
0x14005565d  test    eax, eax
0x14005565f  jns     short loc_14005567E
0x140055661  add     eax, 3FFFFF77h
0x140055666  cmp     eax, 2
0x140055669  jbe     loc_140055780
0x14005566f  lea     r9, aAslpfilegetver_6; "AslpFileGetVersionBlockFromResourceRoot"...
0x140055676  mov     r8d, 913h
0x14005567c  jmp     short loc_140055620
0x14005567e  mov     r14, [rsp+78h+Size]
0x140055683  test    r14, r14
0x140055686  jnz     short loc_140055692
0x140055688  mov     ebx, 0C0000089h
0x14005568d  jmp     loc_14005577C
0x140055692  cmp     [rsp+78h+Src], rdi
0x14005569a  jnz     short loc_1400556C0
0x14005569c  mov     [rsp+78h+var_58], ebx
0x1400556a0  lea     r9, aAslpfilegetver; "AslpFileGetVersionBlockFromResourceRoot"...
0x1400556a7  mov     r8d, 91Fh
0x1400556ad  lea     rdx, aAslpfilegetver_8; "AslpFileGetVersionBlockImageOnly"
0x1400556b4  mov     ecx, 1
0x1400556b9  call    AslLogCallPrintf
0x1400556be  jmp     short loc_140055688
0x1400556c0  cmp     r14, 7FFFh
0x1400556c7  jbe     short loc_1400556E9
0x1400556c9  lea     r9, aAslpfilegetver_2; "AslpFileGetVersionBlockFromResourceRoot"...
0x1400556d0  mov     r8d, 925h
0x1400556d6  lea     rdx, aAslpfilegetver_8; "AslpFileGetVersionBlockImageOnly"
0x1400556dd  mov     ecx, 1
0x1400556e2  call    AslLogCallPrintf
0x1400556e7  jmp     short loc_140055688
0x1400556e9  mov     r9, [r15+28h]
0x1400556ed  mov     r8, [r15+20h]
0x1400556f1  mov     rdx, r14
0x1400556f4  mov     rcx, [rsp+78h+Src]
0x1400556fc  call    AslpMemoryCheckBounds
0x140055701  test    al, al
0x140055703  jnz     short loc_140055714
0x140055705  lea     r9, aVersionBlockOu; "Version block out of range"
0x14005570c  mov     r8d, 92Eh
0x140055712  jmp     short loc_1400556D6
0x140055714  mov     r8d, 1
0x14005571a  call    AslAlloc
0x14005571f  mov     rsi, rax
0x140055722  mov     [rsp+78h+var_40], rax
0x140055727  test    rax, rax
0x14005572a  jnz     short loc_140055733
0x14005572c  mov     ebx, 0C0000017h
0x140055731  jmp     short loc_14005577C
0x140055733  mov     r8, r14; Size
0x140055736  mov     rdx, [rsp+78h+Src]; Src
0x14005573e  mov     rcx, rsi; void *
0x140055741  call    memmove
0x140055746  movzx   eax, word ptr [rsi]
0x140055749  cmp     r14, rax
0x14005574c  jnb     short loc_140055752
0x14005574e  mov     [rsi], r14w
0x140055752  lea     rcx, [rsi+28h]
0x140055756  cmp     word ptr [rsi+2], 34h ; '4'
0x14005575b  cmovb   rcx, rdi
0x14005575f  mov     [r13+0], rcx
0x140055763  mov     rax, [rsp+78h+arg_0]
0x14005576b  mov     [rax], rsi
0x14005576e  mov     [r15+48h], rsi
0x140055772  mov     rsi, rdi
0x140055775  mov     [rsp+78h+var_40], rdi
0x14005577a  mov     ebx, edi
0x14005577c  mov     [rsp+78h+var_48], ebx
0x140055780  jmp     short loc_1400557AF
0x140055782  mov     ebx, eax
0x140055784  mov     [rsp+78h+var_48], eax
0x140055788  mov     [rsp+78h+var_58], eax
0x14005578c  lea     r9, aExceptionEncou_0; "Exception encountered [%x]"
0x140055793  mov     r8d, 966h
0x140055799  lea     rdx, aAslpfilegetver_8; "AslpFileGetVersionBlockImageOnly"
0x1400557a0  mov     ecx, 1
0x1400557a5  call    AslLogCallPrintf
0x1400557aa  mov     rsi, [rsp+78h+var_40]
0x1400557af  test    rsi, rsi
0x1400557b2  jz      short loc_1400557BC
0x1400557b4  mov     rdx, rsi
0x1400557b7  call    AslFree
0x1400557bc  mov     eax, ebx
0x1400557be  mov     rbx, [rsp+78h+arg_8]
0x1400557c6  add     rsp, 50h
0x1400557ca  pop     r15
0x1400557cc  pop     r14
0x1400557ce  pop     r13
0x1400557d0  pop     rdi
0x1400557d1  pop     rsi
0x1400557d2  retn
0x14005bf50  push    rbp
0x14005bf52  sub     rsp, 30h
0x14005bf56  mov     rbp, rdx
0x14005bf59  mov     eax, 1
0x14005bf5e  add     rsp, 30h
0x14005bf62  pop     rbp
0x14005bf63  retn
```
