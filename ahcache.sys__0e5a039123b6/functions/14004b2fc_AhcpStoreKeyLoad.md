# AhcpStoreKeyLoad

- ea: `0x14004b2fc`
- end: `0x14004b4a5`
- name: `AhcpStoreKeyLoad`
- size: `425`
- prototype: `__int64 __fastcall(unsigned __int16 *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x14004b014`

## callees

- `0x140003830`
- `0x140007b40`
- `0x14003e364`
- `0x14004b2fc`
- `0x14005498c`

## string_xrefs

- `0x14004b470`: `Failed to read key length [%x]`
- `0x14004b443`: `Failed to read file name`

## pseudocode

```c
__int64 __fastcall AhcpStoreKeyLoad(unsigned __int16 *a1, _QWORD *a2)
{
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // rcx
  unsigned int v6; // ebx
  unsigned __int64 v7; // rax
  __int64 v8; // rcx
  unsigned __int16 *v9; // r8
  void *v10; // rax
  __int64 v11; // rsi
  unsigned __int64 v12; // rdx
  unsigned __int64 v13; // rcx
  unsigned __int64 v14; // rax

  v4 = a2[1];
  v5 = a2[4];
  if ( v5 > v4 || v5 + 2 < v5 || v5 + 2 > v4 )
  {
    v6 = -1073741811;
LABEL_21:
    AslLogCallPrintf(1, "AhcpStoreKeyLoad", 367, "Failed to read key length [%x]", v6);
    return v6;
  }
  *a1 = *(_WORD *)(v5 + a2[5]);
  v7 = a2[4];
  if ( v7 + 2 < v7 )
  {
    a2[4] = -1;
    v6 = -1073741675;
    goto LABEL_21;
  }
  a2[4] = v7 + 2;
  if ( UShortAdd(*a1, 2u, a1 + 1) >= 0 )
  {
    v10 = (void *)AslAlloc(v8, *v9, 1);
    *((_QWORD *)a1 + 1) = v10;
    if ( !v10 )
    {
      AslLogCallPrintf(1, "AhcpStoreKeyLoad", 384, "Failed to allocate memory for file name buffer");
      return (unsigned int)-1073741801;
    }
    v11 = *a1;
    if ( *a1 )
    {
      v12 = a2[1];
      v13 = a2[4];
      if ( v13 > v12 || v13 + v11 < v13 || v13 + v11 > v12 )
      {
        v6 = -1073741811;
      }
      else
      {
        memmove(v10, (const void *)(v13 + a2[5]), *a1);
        v14 = a2[4];
        if ( v11 + v14 >= v14 )
        {
          a2[4] = v11 + v14;
          goto LABEL_17;
        }
        a2[4] = -1;
        v6 = -1073741675;
      }
      AslLogCallPrintf(1, "AhcpStoreKeyLoad", 391, "Failed to read file name");
      return v6;
    }
LABEL_17:
    v6 = 0;
    *(_WORD *)((*a1 & 0xFFFE) + *((_QWORD *)a1 + 1)) = 0;
    return v6;
  }
  AslLogCallPrintf(1, "AhcpStoreKeyLoad", 372, "File name is too long");
  return (unsigned int)-1073741811;
}

```

## disassembly

```asm
0x14004b2fc  mov     [rsp+arg_0], rbx
0x14004b301  mov     [rsp+arg_8], rsi
0x14004b306  push    rdi
0x14004b307  sub     rsp, 30h
0x14004b30b  mov     rbx, rdx
0x14004b30e  mov     rdi, rcx
0x14004b311  mov     rdx, [rdx+8]
0x14004b315  mov     rcx, [rbx+20h]
0x14004b319  cmp     rcx, rdx
0x14004b31c  jbe     short loc_14004B328
0x14004b31e  mov     ebx, 0C000000Dh
0x14004b323  jmp     loc_14004B470
0x14004b328  lea     rax, [rcx+2]
0x14004b32c  cmp     rax, rcx
0x14004b32f  jb      short loc_14004B31E
0x14004b331  cmp     rax, rdx
0x14004b334  ja      short loc_14004B31E
0x14004b336  mov     rax, [rbx+28h]
0x14004b33a  movzx   ecx, word ptr [rcx+rax]
0x14004b33e  mov     [rdi], cx
0x14004b341  mov     rax, [rbx+20h]
0x14004b345  lea     rcx, [rax+2]
0x14004b349  cmp     rcx, rax
0x14004b34c  jb      loc_14004B463
0x14004b352  mov     [rbx+20h], rcx
0x14004b356  lea     r8, [rdi+2]; pusResult
0x14004b35a  movzx   ecx, word ptr [rdi]; usAugend
0x14004b35d  mov     edx, 2; usAddend
0x14004b362  call    UShortAdd
0x14004b367  test    eax, eax
0x14004b369  jns     short loc_14004B393
0x14004b36b  lea     r9, aFileNameIsTooL; "File name is too long"
0x14004b372  mov     r8d, 174h
0x14004b378  lea     rdx, aAhcpstorekeylo; "AhcpStoreKeyLoad"
0x14004b37f  mov     ecx, 1
0x14004b384  call    AslLogCallPrintf
0x14004b389  mov     ebx, 0C000000Dh
0x14004b38e  jmp     loc_14004B492
0x14004b393  movzx   edx, word ptr [r8]
0x14004b397  mov     r8d, 1
0x14004b39d  call    AslAlloc
0x14004b3a2  mov     [rdi+8], rax
0x14004b3a6  mov     r9, rax
0x14004b3a9  test    rax, rax
0x14004b3ac  jnz     short loc_14004B3D4
0x14004b3ae  lea     r9, aFailedToAlloca_13; "Failed to allocate memory for file name"...
0x14004b3b5  mov     r8d, 180h
0x14004b3bb  lea     rdx, aAhcpstorekeylo; "AhcpStoreKeyLoad"
0x14004b3c2  lea     ecx, [rax+1]
0x14004b3c5  call    AslLogCallPrintf
0x14004b3ca  mov     ebx, 0C0000017h
0x14004b3cf  jmp     loc_14004B492
0x14004b3d4  movzx   esi, word ptr [rdi]
0x14004b3d7  test    rsi, rsi
0x14004b3da  jz      short loc_14004B421
0x14004b3dc  mov     rdx, [rbx+8]
0x14004b3e0  mov     rcx, [rbx+20h]
0x14004b3e4  cmp     rcx, rdx
0x14004b3e7  jbe     short loc_14004B3F0
0x14004b3e9  mov     ebx, 0C000000Dh
0x14004b3ee  jmp     short loc_14004B443
0x14004b3f0  lea     rax, [rcx+rsi]
0x14004b3f4  cmp     rax, rcx
0x14004b3f7  jb      short loc_14004B3E9
0x14004b3f9  cmp     rax, rdx
0x14004b3fc  ja      short loc_14004B3E9
0x14004b3fe  mov     rdx, [rbx+28h]
0x14004b402  mov     r8, rsi; Size
0x14004b405  add     rdx, rcx; Src
0x14004b408  mov     rcx, r9; void *
0x14004b40b  call    memmove
0x14004b410  mov     rax, [rbx+20h]
0x14004b414  lea     rcx, [rsi+rax]
0x14004b418  cmp     rcx, rax
0x14004b41b  jb      short loc_14004B436
0x14004b41d  mov     [rbx+20h], rcx
0x14004b421  movzx   edx, word ptr [rdi]
0x14004b424  xor     eax, eax
0x14004b426  mov     rcx, [rdi+8]
0x14004b42a  and     rdx, 0FFFFFFFFFFFFFFFEh
0x14004b42e  xor     ebx, ebx
0x14004b430  mov     [rdx+rcx], ax
0x14004b434  jmp     short loc_14004B492
0x14004b436  mov     qword ptr [rbx+20h], 0FFFFFFFFFFFFFFFFh
0x14004b43e  mov     ebx, 0C0000095h
0x14004b443  lea     r9, aFailedToReadFi; "Failed to read file name"
0x14004b44a  mov     r8d, 187h
0x14004b450  lea     rdx, aAhcpstorekeylo; "AhcpStoreKeyLoad"
0x14004b457  mov     ecx, 1
0x14004b45c  call    AslLogCallPrintf
0x14004b461  jmp     short loc_14004B492
0x14004b463  mov     qword ptr [rbx+20h], 0FFFFFFFFFFFFFFFFh
0x14004b46b  mov     ebx, 0C0000095h
0x14004b470  lea     r9, aFailedToReadKe_0; "Failed to read key length [%x]"
0x14004b477  mov     [rsp+38h+var_18], ebx
0x14004b47b  mov     r8d, 16Fh
0x14004b481  lea     rdx, aAhcpstorekeylo; "AhcpStoreKeyLoad"
0x14004b488  mov     ecx, 1
0x14004b48d  call    AslLogCallPrintf
0x14004b492  mov     rsi, [rsp+38h+arg_8]
0x14004b497  mov     eax, ebx
0x14004b499  mov     rbx, [rsp+38h+arg_0]
0x14004b49e  add     rsp, 30h
0x14004b4a2  pop     rdi
0x14004b4a3  retn
```
