# CreateMappingName

- ea: `0x14001360c`
- end: `0x140013766`
- name: `CreateMappingName`
- size: `346`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString, __int64, struct _UNICODE_STRING **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001376c`

## callees

- `0x14001322c`
- `0x14001360c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140013740`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013740`
- `ntoskrnl!ExAllocatePool2` at `0x140013645`
- `ntoskrnl!ExAllocatePool2` at `0x140013645`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001368c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14001368c`

## pseudocode

```c
__int64 __fastcall CreateMappingName(PCUNICODE_STRING SourceString, __int64 a2, struct _UNICODE_STRING **a3)
{
  unsigned __int16 NumberComponents; // di
  unsigned int v6; // ebp
  struct _UNICODE_STRING *Pool2; // rax
  struct _UNICODE_STRING *v8; // rbx
  unsigned __int16 v10; // r10
  unsigned __int16 i; // cx
  unsigned __int16 v12; // r9
  __int16 v13; // r8
  unsigned __int16 v14; // dx
  wchar_t **p_Buffer; // r9
  __int16 v16; // r8

  NumberComponents = GetNumberComponents(SourceString);
  v6 = 16 * NumberComponents + SourceString->MaximumLength + 24;
  Pool2 = (struct _UNICODE_STRING *)ExAllocatePool2(256, v6, 1850099286);
  v8 = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  Pool2->Length = 0;
  Pool2->MaximumLength = SourceString->MaximumLength;
  if ( NumberComponents )
  {
    Pool2->Buffer = (unsigned __int16 *)((char *)&Pool2->Length + v6 - SourceString->MaximumLength);
    RtlCopyUnicodeString(Pool2, SourceString);
  }
  v8[1].Length = NumberComponents;
  if ( NumberComponents )
  {
    v10 = 0;
    for ( i = 0; ; i = v14 + 1 )
    {
      v12 = v8->Length >> 1;
      if ( !i )
        i = *v8->Buffer == 92;
      if ( i >= v12 )
        break;
      v13 = 0;
      v14 = i;
      do
      {
        if ( v8->Buffer[v14] == 92 )
          break;
        ++v13;
        ++v14;
      }
      while ( v14 < v12 );
      if ( !v13 )
        break;
      p_Buffer = &v8[v10 + 1].Buffer;
      if ( p_Buffer )
      {
        v16 = 2 * v13;
        *((_WORD *)p_Buffer + 1) = v16;
        *(_WORD *)p_Buffer = v16;
        p_Buffer[1] = &v8->Buffer[i];
      }
      if ( ++v10 >= NumberComponents )
        goto LABEL_19;
    }
    ExFreePoolWithTag(v8, 0x6E464656u);
    return 3221225485LL;
  }
  else
  {
LABEL_19:
    *a3 = v8;
    return 0;
  }
}

```

## disassembly

```asm
0x14001360c  push    rbx
0x14001360e  push    rbp
0x14001360f  push    rsi
0x140013610  push    rdi
0x140013611  push    r14
0x140013613  push    r15
0x140013615  sub     rsp, 28h
0x140013619  mov     r14, r8
0x14001361c  mov     rsi, rcx
0x14001361f  call    GetNumberComponents
0x140013624  movzx   ebp, word ptr [rsi+2]
0x140013628  mov     ecx, 100h
0x14001362d  movzx   edi, ax
0x140013630  add     ebp, 18h
0x140013633  mov     r9d, edi
0x140013636  mov     r8d, 6E464656h
0x14001363c  shl     r9d, 4
0x140013640  add     ebp, r9d
0x140013643  mov     edx, ebp
0x140013645  call    cs:__imp_ExAllocatePool2
0x14001364c  nop     dword ptr [rax+rax+00h]
0x140013651  xor     r15d, r15d
0x140013654  mov     rbx, rax
0x140013657  test    rax, rax
0x14001365a  jnz     short loc_140013666
0x14001365c  mov     eax, 0C000009Ah
0x140013661  jmp     loc_140013758
0x140013666  mov     [rax], r15w
0x14001366a  movzx   eax, word ptr [rsi+2]
0x14001366e  mov     [rbx+2], ax
0x140013672  test    di, di
0x140013675  jz      short loc_140013698
0x140013677  movzx   eax, word ptr [rsi+2]
0x14001367b  mov     rdx, rsi; SourceString
0x14001367e  sub     ebp, eax
0x140013680  mov     rcx, rbx; DestinationString
0x140013683  mov     eax, ebp
0x140013685  add     rax, rbx
0x140013688  mov     [rbx+8], rax
0x14001368c  call    cs:__imp_RtlCopyUnicodeString
0x140013693  nop     dword ptr [rax+rax+00h]
0x140013698  mov     [rbx+10h], di
0x14001369c  cmp     r15w, di
0x1400136a0  jnb     loc_140013753
0x1400136a6  mov     r10d, r15d
0x1400136a9  mov     ecx, r15d
0x1400136ac  mov     esi, 1
0x1400136b1  movzx   r9d, word ptr [rbx]
0x1400136b5  shr     r9w, 1
0x1400136b9  test    cx, cx
0x1400136bc  jnz     short loc_1400136CB
0x1400136be  mov     rax, [rbx+8]
0x1400136c2  cmp     word ptr [rax], 5Ch ; '\'
0x1400136c6  jnz     short loc_1400136CB
0x1400136c8  movzx   ecx, si
0x1400136cb  cmp     cx, r9w
0x1400136cf  jnb     short loc_140013738
0x1400136d1  mov     r11, [rbx+8]
0x1400136d5  mov     r8d, r15d
0x1400136d8  movzx   edx, cx
0x1400136db  movzx   eax, dx
0x1400136de  cmp     word ptr [r11+rax*2], 5Ch ; '\'
0x1400136e4  jz      short loc_1400136F3
0x1400136e6  add     r8w, si
0x1400136ea  add     dx, si
0x1400136ed  cmp     dx, r9w
0x1400136f1  jb      short loc_1400136DB
0x1400136f3  test    r8w, r8w
0x1400136f7  jz      short loc_140013738
0x1400136f9  movzx   r9d, r10w
0x1400136fd  shl     r9, 4
0x140013701  add     r9, 18h
0x140013705  add     r9, rbx
0x140013708  jz      short loc_140013726
0x14001370a  add     r8w, r8w
0x14001370e  movzx   ecx, cx
0x140013711  mov     [r9+2], r8w
0x140013716  mov     [r9], r8w
0x14001371a  mov     rax, [rbx+8]
0x14001371e  lea     rcx, [rax+rcx*2]
0x140013722  mov     [r9+8], rcx
0x140013726  add     r10w, si
0x14001372a  cmp     r10w, di
0x14001372e  jnb     short loc_140013753
0x140013730  lea     ecx, [rsi+rdx]
0x140013733  jmp     loc_1400136B1
0x140013738  mov     edx, 6E464656h; Tag
0x14001373d  mov     rcx, rbx; P
0x140013740  call    cs:__imp_ExFreePoolWithTag
0x140013747  nop     dword ptr [rax+rax+00h]
0x14001374c  mov     eax, 0C000000Dh
0x140013751  jmp     short loc_140013758
0x140013753  mov     [r14], rbx
0x140013756  xor     eax, eax
0x140013758  add     rsp, 28h
0x14001375c  pop     r15
0x14001375e  pop     r14
0x140013760  pop     rdi
0x140013761  pop     rsi
0x140013762  pop     rbp
0x140013763  pop     rbx
0x140013764  retn
```
