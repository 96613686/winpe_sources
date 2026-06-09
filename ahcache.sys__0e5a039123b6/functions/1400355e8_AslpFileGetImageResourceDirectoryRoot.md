# AslpFileGetImageResourceDirectoryRoot

- ea: `0x1400355e8`
- end: `0x1400357b0`
- name: `AslpFileGetImageResourceDirectoryRoot`
- size: `456`
- prototype: `__int64 __fastcall(__int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task`

## callers

- `0x140055540`

## callees

- `0x140006c10`
- `0x1400355e8`
- `0x140036568`
- `0x14003e364`
- `0x140051e8c`

## string_xrefs

- `0x140035621`: `AslpFileGetImageResourceDirectoryRoot`
- `0x1400356b8`: `AslpFileGetImageResourceDirectoryRoot`
- `0x140035789`: `AslpFileGetImageResourceDirectoryRoot`
- `0x140035778`: `AslpFileGetImageNtHeader failed to get image headers or headers are out of bounds [%x]`
- `0x1400356ac`: `Image PE optional header outside image`

## pseudocode

```c
__int64 __fastcall AslpFileGetImageResourceDirectoryRoot(__int64 *a1, __int64 a2, __int64 a3)
{
  bool v3; // zf
  __int64 v7; // rsi
  __int64 v8; // rbp
  int ImageNtHeader; // ebx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // r11
  __int64 v13; // rcx
  __int16 v14; // ax
  unsigned int *v15; // r11
  __int64 v16; // r8
  unsigned int v17; // eax
  _DWORD *v18; // rbx
  __int64 v19; // rcx
  __int64 v20; // [rsp+58h] [rbp+10h] BYREF

  v20 = a2;
  v3 = *(_DWORD *)(a3 + 64) == 6;
  v20 = 0;
  if ( !v3 )
  {
    AslLogCallPrintf(1, "AslpFileGetImageResourceDirectoryRoot", 1924, "File is not a PE image");
    return 3221225659LL;
  }
  v7 = *(_QWORD *)(a3 + 32);
  v8 = *(_QWORD *)(a3 + 40);
  ImageNtHeader = AslpFileGetImageNtHeader(&v20, a3);
  if ( ImageNtHeader < 0 )
    goto LABEL_26;
  if ( !(unsigned __int8)AslpMemoryCheckBounds(v20, 8, v7, v8) )
  {
    ImageNtHeader = -1073741266;
LABEL_26:
    AslLogCallPrintf(
      1,
      "AslpFileGetImageResourceDirectoryRoot",
      1937,
      "AslpFileGetImageNtHeader failed to get image headers or headers are out of bounds [%x]",
      ImageNtHeader);
    return (unsigned int)ImageNtHeader;
  }
  v13 = v12 + 24;
  v14 = *(_WORD *)(v12 + 24);
  if ( v14 != 267 )
  {
    if ( v14 == 523 && *(_WORD *)(v12 + 20) >= 0x70u )
    {
      if ( !(unsigned __int8)AslpMemoryCheckBounds(v13, 240, v10, v11) )
      {
        v16 = 1971;
        goto LABEL_9;
      }
      v17 = v15[33];
      v18 = v15 + 38;
      goto LABEL_16;
    }
    return 3221225595LL;
  }
  if ( *(_WORD *)(v12 + 20) < 0x60u )
    return 3221225595LL;
  if ( !(unsigned __int8)AslpMemoryCheckBounds(v13, 224, v10, v11) )
  {
    v16 = 1955;
LABEL_9:
    AslLogCallPrintf(1, "AslpFileGetImageResourceDirectoryRoot", v16, "Image PE optional header outside image");
    return 3221226030LL;
  }
  v17 = v15[29];
  v18 = v15 + 34;
LABEL_16:
  if ( v17 <= 2 || v18[1] < 0x10u || !*v18 )
    return 3221225609LL;
  v19 = AslpImageRvaToVa(v15, a3);
  if ( !v19 || !(unsigned __int8)AslpMemoryCheckBounds(v19, (unsigned int)v18[1], v7, v8) )
    return v19 != 0 ? -1073741266 : -1073741687;
  *a1 = v19;
  return 0;
}

```

## disassembly

```asm
0x1400355e8  mov     rax, rsp
0x1400355eb  mov     [rax+8], rbx
0x1400355ef  mov     [rax+18h], rbp
0x1400355f3  mov     [rax+10h], rdx
0x1400355f7  push    rsi
0x1400355f8  push    rdi
0x1400355f9  push    r14
0x1400355fb  sub     rsp, 30h
0x1400355ff  cmp     dword ptr [r8+40h], 6
0x140035604  mov     rdi, r8
0x140035607  mov     r14, rcx
0x14003560a  mov     qword ptr [rax+10h], 0
0x140035612  jz      short loc_14003563C
0x140035614  lea     r9, aFileIsNotAPeIm; "File is not a PE image"
0x14003561b  mov     r8d, 784h
0x140035621  lea     rdx, aAslpfilegetima_0; "AslpFileGetImageResourceDirectoryRoot"
0x140035628  mov     ecx, 1
0x14003562d  call    AslLogCallPrintf
0x140035632  mov     eax, 0C00000BBh
0x140035637  jmp     loc_14003579C
0x14003563c  mov     rsi, [r8+20h]
0x140035640  lea     rcx, [rsp+48h+arg_8]
0x140035645  mov     rbp, [r8+28h]
0x140035649  mov     rdx, rdi
0x14003564c  call    AslpFileGetImageNtHeader
0x140035651  mov     ebx, eax
0x140035653  test    eax, eax
0x140035655  js      loc_140035778
0x14003565b  mov     r11, [rsp+48h+arg_8]
0x140035660  mov     r9, rbp
0x140035663  mov     rcx, r11
0x140035666  mov     r8, rsi
0x140035669  mov     edx, 8
0x14003566e  call    AslpMemoryCheckBounds
0x140035673  test    al, al
0x140035675  jz      loc_140035773
0x14003567b  lea     rcx, [r11+18h]
0x14003567f  mov     edx, 10Bh
0x140035684  movzx   eax, word ptr [rcx]
0x140035687  cmp     ax, dx
0x14003568a  jnz     short loc_1400356DB
0x14003568c  cmp     word ptr [r11+14h], 60h ; '`'
0x140035692  jb      loc_14003576C
0x140035698  mov     edx, 0E0h
0x14003569d  call    AslpMemoryCheckBounds
0x1400356a2  test    al, al
0x1400356a4  jnz     short loc_1400356CE
0x1400356a6  mov     r8d, 7A3h
0x1400356ac  lea     r9, aImagePeOptiona; "Image PE optional header outside image"
0x1400356b3  mov     ecx, 1
0x1400356b8  lea     rdx, aAslpfilegetima_0; "AslpFileGetImageResourceDirectoryRoot"
0x1400356bf  call    AslLogCallPrintf
0x1400356c4  mov     eax, 0C000022Eh
0x1400356c9  jmp     loc_14003579C
0x1400356ce  mov     eax, [r11+74h]
0x1400356d2  lea     rbx, [r11+88h]
0x1400356d9  jmp     short loc_140035715
0x1400356db  mov     edx, 20Bh
0x1400356e0  cmp     ax, dx
0x1400356e3  jnz     loc_14003576C
0x1400356e9  cmp     word ptr [r11+14h], 70h ; 'p'
0x1400356ef  jb      short loc_14003576C
0x1400356f1  mov     edx, 0F0h
0x1400356f6  call    AslpMemoryCheckBounds
0x1400356fb  test    al, al
0x1400356fd  jnz     short loc_140035707
0x1400356ff  mov     r8d, 7B3h
0x140035705  jmp     short loc_1400356AC
0x140035707  mov     eax, [r11+84h]
0x14003570e  lea     rbx, [r11+98h]
0x140035715  cmp     eax, 2
0x140035718  jbe     short loc_140035765
0x14003571a  cmp     dword ptr [rbx+4], 10h
0x14003571e  jb      short loc_140035765
0x140035720  mov     r8d, [rbx]
0x140035723  test    r8d, r8d
0x140035726  jz      short loc_140035765
0x140035728  mov     rdx, rdi
0x14003572b  mov     rcx, r11
0x14003572e  call    AslpImageRvaToVa
0x140035733  mov     rcx, rax
0x140035736  test    rax, rax
0x140035739  jz      short loc_140035754
0x14003573b  mov     edx, [rbx+4]
0x14003573e  mov     r9, rbp
0x140035741  mov     r8, rsi
0x140035744  call    AslpMemoryCheckBounds
0x140035749  test    al, al
0x14003574b  jz      short loc_140035754
0x14003574d  mov     [r14], rcx
0x140035750  xor     eax, eax
0x140035752  jmp     short loc_14003579C
0x140035754  neg     rcx
0x140035757  sbb     eax, eax
0x140035759  and     eax, 1A5h
0x14003575e  add     eax, 0C0000089h
0x140035763  jmp     short loc_14003579C
0x140035765  mov     eax, 0C0000089h
0x14003576a  jmp     short loc_14003579C
0x14003576c  mov     eax, 0C000007Bh
0x140035771  jmp     short loc_14003579C
0x140035773  mov     ebx, 0C000022Eh
0x140035778  lea     r9, aAslpfilegetima_2; "AslpFileGetImageNtHeader failed to get "...
0x14003577f  mov     [rsp+48h+var_28], ebx
0x140035783  mov     r8d, 791h
0x140035789  lea     rdx, aAslpfilegetima_0; "AslpFileGetImageResourceDirectoryRoot"
0x140035790  mov     ecx, 1
0x140035795  call    AslLogCallPrintf
0x14003579a  mov     eax, ebx
0x14003579c  mov     rbx, [rsp+48h+arg_0]
0x1400357a1  mov     rbp, [rsp+48h+arg_10]
0x1400357a6  add     rsp, 30h
0x1400357aa  pop     r14
0x1400357ac  pop     rdi
0x1400357ad  pop     rsi
0x1400357ae  retn
```
