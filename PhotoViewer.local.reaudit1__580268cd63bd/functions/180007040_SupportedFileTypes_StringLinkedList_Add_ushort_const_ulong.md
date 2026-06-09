# SupportedFileTypes::StringLinkedList::Add(ushort const *,ulong)

- ea: `0x180007040`
- end: `0x180007289`
- name: `?Add@StringLinkedList@SupportedFileTypes@@QEAAJPEBGK@Z`
- size: `585`
- prototype: `int(SupportedFileTypes::StringLinkedList *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180072134`
- `0x180072504`

## callees

- `0x180007040`
- `0x180007290`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x18000721e`
- `KERNEL32!lstrlenW` at `0x18000721e`
- `KERNEL32!CompareStringW` at `0x180007089`
- `KERNEL32!CompareStringW` at `0x180007110`
- `KERNEL32!CompareStringW` at `0x180007089`
- `KERNEL32!CompareStringW` at `0x180007110`
- `KERNEL32!LocalAlloc` at `0x180007154`
- `KERNEL32!LocalAlloc` at `0x1800071f7`
- `KERNEL32!LocalAlloc` at `0x180007154`
- `KERNEL32!LocalAlloc` at `0x1800071f7`

## pseudocode

```c
__int64 __fastcall SupportedFileTypes::StringLinkedList::Add(
        SupportedFileTypes::StringLinkedList *this,
        const unsigned __int16 *a2,
        int a3)
{
  __int64 i; // rbx
  int v7; // eax
  __int64 result; // rax
  const unsigned __int16 *v9; // rdx
  unsigned __int64 v10; // rax
  unsigned int v11; // ebp
  __int64 v12; // rbx
  __int64 v13; // rsi
  _WORD *v14; // rax
  __int64 v15; // rcx
  unsigned __int64 v16; // rbx
  _QWORD *v17; // rax
  _QWORD *v18; // r14
  int v19; // eax

  for ( i = *(_QWORD *)this; i; i = *(_QWORD *)(i + 16) )
  {
    v7 = CompareStringW(0x400u, 1u, *(PCNZWCH *)i, -1, a2, -1) - 1;
    if ( v7 )
    {
      if ( v7 == 1 )
      {
        *(_DWORD *)(i + 8) |= a3;
        return 0;
      }
      break;
    }
  }
  v17 = LocalAlloc(0x40u, 0x18u);
  v18 = v17;
  if ( !v17 )
    return 2147942414LL;
  v13 = 0;
  *v17 = 0;
  *((_DWORD *)v17 + 2) = 0;
  v17[2] = 0;
  v19 = lstrlenW(a2);
  LODWORD(v9) = v19;
  if ( !v19 )
  {
    v11 = -2147024809;
LABEL_31:
    SupportedFileTypes::StringLinkedList::Node::`scalar deleting destructor'(v18, (unsigned int)v9);
    return v11;
  }
  v16 = v19 + 1LL;
  if ( v16 >= v19 && (LODWORD(v9) = -1, v10 = 2LL * (unsigned int)v16, v10 <= 0xFFFFFFFF) )
  {
    v14 = LocalAlloc(0x40u, (unsigned int)v10);
    *v18 = v14;
    if ( v14 )
    {
      if ( v16 )
      {
        if ( v16 > 0x7FFFFFFF )
        {
          v11 = -2147024809;
          *v14 = 0;
        }
        else
        {
          v15 = 2147483646;
          v9 = a2;
          v11 = 0;
          while ( v15 && *v9 )
          {
            *v14++ = *v9++;
            --v15;
            if ( !--v16 )
            {
              --v14;
              v11 = -2147024774;
              break;
            }
          }
          *v14 = 0;
        }
      }
      else
      {
        v11 = -2147024809;
      }
    }
    else
    {
      v11 = -2147024882;
    }
  }
  else
  {
    v11 = -2147024362;
  }
  if ( (v11 & 0x80000000) != 0 )
    goto LABEL_31;
  *((_DWORD *)v18 + 2) = a3;
  v12 = *(_QWORD *)this;
  if ( !*(_QWORD *)this )
    goto LABEL_24;
  do
  {
    if ( CompareStringW(0x400u, 1u, *(PCNZWCH *)v12, -1, a2, -1) != 1 )
      break;
    v13 = v12;
    v12 = *(_QWORD *)(v12 + 16);
  }
  while ( v12 );
  if ( v13 )
  {
    v18[2] = *(_QWORD *)(v13 + 16);
    result = v11;
    *(_QWORD *)(v13 + 16) = v18;
  }
  else
  {
LABEL_24:
    v18[2] = *(_QWORD *)this;
    result = v11;
    *(_QWORD *)this = v18;
  }
  return result;
}

```

## disassembly

```asm
0x180007040  mov     [rsp+arg_18], rbx
0x180007045  push    rdi
0x180007046  push    r12
0x180007048  push    r15
0x18000704a  sub     rsp, 30h
0x18000704e  mov     rbx, [rcx]
0x180007051  mov     r15d, r8d
0x180007054  mov     rdi, rdx
0x180007057  mov     [rsp+48h+arg_8], rsi
0x18000705c  mov     r12, rcx
0x18000705f  nop
0x180007060  test    rbx, rbx
0x180007063  jz      loc_1800071E3
0x180007069  mov     r8, [rbx]; lpString1
0x18000706c  mov     r9d, 0FFFFFFFFh; cchCount1
0x180007072  mov     [rsp+48h+cchCount2], 0FFFFFFFFh; cchCount2
0x18000707a  mov     edx, 1; dwCmpFlags
0x18000707f  mov     ecx, 400h; Locale
0x180007084  mov     [rsp+48h+lpString2], rdi; lpString2
0x180007089  call    cs:__imp_CompareStringW
0x18000708f  sub     eax, 1
0x180007092  jnz     short loc_18000709A
0x180007094  mov     rbx, [rbx+10h]
0x180007098  jmp     short loc_180007060
0x18000709a  cmp     eax, 1
0x18000709d  jnz     loc_1800071E3
0x1800070a3  xor     esi, esi
0x1800070a5  or      [rbx+8], r15d
0x1800070a9  mov     eax, esi
0x1800070ab  mov     rsi, [rsp+48h+arg_8]
0x1800070b0  mov     rbx, [rsp+48h+arg_18]
0x1800070b5  add     rsp, 30h
0x1800070b9  pop     r15
0x1800070bb  pop     r12
0x1800070bd  pop     rdi
0x1800070be  retn
0x1800070bf  mov     eax, ebx
0x1800070c1  mov     edx, 0FFFFFFFFh
0x1800070c6  add     rax, rax
0x1800070c9  cmp     rax, rdx
0x1800070cc  jbe     short loc_18000714D
0x1800070ce  mov     ebp, 80070216h
0x1800070d3  test    ebp, ebp
0x1800070d5  js      loc_180007242
0x1800070db  mov     [r14+8], r15d
0x1800070df  mov     rbx, [r12]
0x1800070e3  test    rbx, rbx
0x1800070e6  jz      loc_1800071C6
0x1800070ec  nop     dword ptr [rax+00h]
0x1800070f0  mov     r8, [rbx]; lpString1
0x1800070f3  mov     r9d, 0FFFFFFFFh; cchCount1
0x1800070f9  mov     [rsp+48h+cchCount2], 0FFFFFFFFh; cchCount2
0x180007101  mov     edx, 1; dwCmpFlags
0x180007106  mov     ecx, 400h; Locale
0x18000710b  mov     [rsp+48h+lpString2], rdi; lpString2
0x180007110  call    cs:__imp_CompareStringW
0x180007116  cmp     eax, 1
0x180007119  jnz     short loc_180007127
0x18000711b  mov     rsi, rbx
0x18000711e  mov     rbx, [rbx+10h]
0x180007122  test    rbx, rbx
0x180007125  jnz     short loc_1800070F0
0x180007127  test    rsi, rsi
0x18000712a  jz      loc_1800071C6
0x180007130  mov     rax, [rsi+10h]
0x180007134  mov     [r14+10h], rax
0x180007138  mov     eax, ebp
0x18000713a  mov     [rsi+10h], r14
0x18000713e  mov     rbp, [rsp+48h+arg_0]
0x180007143  mov     r14, [rsp+48h+arg_10]
0x180007148  jmp     loc_1800070AB
0x18000714d  mov     edx, eax; uBytes
0x18000714f  mov     ecx, 40h ; '@'; uFlags
0x180007154  call    cs:__imp_LocalAlloc
0x18000715a  mov     [r14], rax
0x18000715d  test    rax, rax
0x180007160  jz      short loc_1800071BC
0x180007162  test    rbx, rbx
0x180007165  jz      loc_180007273
0x18000716b  cmp     rbx, 7FFFFFFFh
0x180007172  ja      loc_18000726C
0x180007178  mov     ecx, 7FFFFFFEh
0x18000717d  mov     rdx, rdi
0x180007180  mov     ebp, esi
0x180007182  test    rcx, rcx
0x180007185  jz      loc_180007264
0x18000718b  movzx   r8d, word ptr [rdx]
0x18000718f  test    r8w, r8w
0x180007193  jz      loc_18000725B
0x180007199  mov     [rax], r8w
0x18000719d  add     rdx, 2
0x1800071a1  add     rax, 2
0x1800071a5  dec     rcx
0x1800071a8  sub     rbx, 1
0x1800071ac  jnz     short loc_180007182
0x1800071ae  sub     rax, 2
0x1800071b2  mov     ebp, 8007007Ah
0x1800071b7  jmp     loc_180007264
0x1800071bc  mov     ebp, 8007000Eh
0x1800071c1  jmp     loc_1800070D3
0x1800071c6  mov     rax, [r12]
0x1800071ca  mov     [r14+10h], rax
0x1800071ce  mov     eax, ebp
0x1800071d0  mov     rbp, [rsp+48h+arg_0]
0x1800071d5  mov     [r12], r14
0x1800071d9  mov     r14, [rsp+48h+arg_10]
0x1800071de  jmp     loc_1800070AB
0x1800071e3  mov     [rsp+48h+arg_0], rbp
0x1800071e8  mov     edx, 18h; uBytes
0x1800071ed  mov     ecx, 40h ; '@'; uFlags
0x1800071f2  mov     [rsp+48h+arg_10], r14
0x1800071f7  call    cs:__imp_LocalAlloc
0x1800071fd  mov     r14, rax
0x180007200  test    rax, rax
0x180007203  jnz     short loc_18000720F
0x180007205  mov     eax, 8007000Eh
0x18000720a  jmp     loc_18000713E
0x18000720f  xor     esi, esi
0x180007211  mov     rcx, rdi; lpString
0x180007214  mov     [rax], rsi
0x180007217  mov     [rax+8], esi
0x18000721a  mov     [rax+10h], rsi
0x18000721e  call    cs:__imp_lstrlenW
0x180007224  movsxd  rdx, eax; unsigned int
0x180007227  test    eax, eax
0x180007229  jz      short loc_18000723D
0x18000722b  lea     rbx, [rdx+1]
0x18000722f  cmp     rbx, rdx
0x180007232  jb      loc_1800070CE
0x180007238  jmp     loc_1800070BF
0x18000723d  mov     ebp, 80070057h
0x180007242  mov     rcx, r14; hMem
0x180007245  call    ??_GNode@StringLinkedList@SupportedFileTypes@@QEAAPEAXI@Z; SupportedFileTypes::StringLinkedList::Node::`scalar deleting destructor'(uint)
0x18000724a  mov     r14, [rsp+48h+arg_10]
0x18000724f  mov     eax, ebp
0x180007251  mov     rbp, [rsp+48h+arg_0]
0x180007256  jmp     loc_1800070AB
0x18000725b  test    rbx, rbx
0x18000725e  jz      loc_1800071AE
0x180007264  mov     [rax], si
0x180007267  jmp     loc_1800070D3
0x18000726c  mov     ebp, 80070057h
0x180007271  jmp     short loc_180007281
0x180007273  mov     ebp, 80070057h
0x180007278  test    rbx, rbx
0x18000727b  jz      loc_1800070D3
0x180007281  mov     [rax], si
0x180007284  jmp     loc_1800070D3
```
