# BfpInitializeContainerRootId

- ea: `0x140021b60`
- end: `0x140021d13`
- name: `BfpInitializeContainerRootId`
- size: `435`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140010898`
- `0x140010d64`
- `0x14001d974`
- `0x140021a68`

## callees

- `0x140003304`
- `0x140004cc0`
- `0x140021b60`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140021bb0`
- `ntoskrnl!ExAllocatePool2` at `0x140021bb0`

## pseudocode

```c
__int64 __fastcall BfpInitializeContainerRootId(
        unsigned __int16 *a1,
        unsigned __int16 *a2,
        __int16 a3,
        unsigned __int16 *a4,
        _QWORD *a5)
{
  unsigned int v7; // r9d
  __int64 Pool2; // rax
  int v11; // edx
  _WORD *v12; // rbx
  unsigned int v13; // ebp
  unsigned int v14; // esi
  unsigned __int16 v16; // cx
  __int64 v17; // rdx

  v7 = *a1 + 6;
  if ( a2 )
    v7 += *a2;
  if ( a4 )
    v7 += *a4 + 2;
  Pool2 = ExAllocatePool2(256, v7, 1886209602);
  v12 = (_WORD *)Pool2;
  if ( Pool2 )
  {
    *(_WORD *)(Pool2 + 4) = 0;
    *(_DWORD *)Pool2 = 6;
    v13 = 0;
    if ( a2 )
    {
      *(_WORD *)Pool2 = *a2 + 6;
      *(_WORD *)(Pool2 + 4) = *a2;
      *(_WORD *)(Pool2 + 2) = *a2;
      memmove((void *)(Pool2 + 6), *((const void **)a2 + 1), *a2);
      v14 = *a2 + 6;
    }
    else
    {
      v14 = 6;
      *(_WORD *)(Pool2 + 2) = a3;
    }
    *v12 += *a1;
    v12[2] += *a1;
    memmove((char *)v12 + v14, *((const void **)a1 + 1), *a1);
    if ( a4 && *a4 )
    {
      v16 = v12[2];
      v17 = v14 + *a1;
      if ( v12[((unsigned __int64)v16 >> 1) + 2] != 92 )
      {
        *v12 += 2;
        v12[2] = v16 + 2;
        *(_WORD *)((char *)v12 + v17) = 92;
        LODWORD(v17) = v17 + 2;
      }
      v12[2] += *a4;
      *v12 += *a4;
      memmove((char *)v12 + (unsigned int)v17, *((const void **)a4 + 1), *a4);
    }
    *a5 = v12;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = 2;
      WPP_RECORDER_SF_sD(
        WPP_GLOBAL_Control->DeviceExtension,
        v11,
        8,
        52,
        (__int64)WPP_55845795197b3ed810b516bf1e89ed04_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\mapping.c",
        54);
    }
    return (unsigned int)-1073741670;
  }
  return v13;
}

```

## disassembly

```asm
0x140021b60  push    rbx
0x140021b62  push    rbp
0x140021b63  push    rsi
0x140021b64  push    rdi
0x140021b65  push    r12
0x140021b67  push    r13
0x140021b69  push    r14
0x140021b6b  push    r15
0x140021b6d  sub     rsp, 48h
0x140021b71  mov     rdi, r9
0x140021b74  xor     r12d, r12d
0x140021b77  movzx   r9d, word ptr [rcx]
0x140021b7b  movzx   r15d, r8w
0x140021b7f  add     r9d, 6
0x140021b83  mov     rsi, rdx
0x140021b86  mov     r14, rcx
0x140021b89  test    rdx, rdx
0x140021b8c  jz      short loc_140021B94
0x140021b8e  movzx   eax, word ptr [rdx]
0x140021b91  add     r9d, eax
0x140021b94  test    rdi, rdi
0x140021b97  jz      short loc_140021BA2
0x140021b99  movzx   eax, word ptr [rdi]
0x140021b9c  add     eax, 2
0x140021b9f  add     r9d, eax
0x140021ba2  mov     edx, r9d
0x140021ba5  mov     ecx, 100h
0x140021baa  mov     r8d, 706D4642h
0x140021bb0  call    cs:__imp_ExAllocatePool2
0x140021bb7  nop     dword ptr [rax+rax+00h]
0x140021bbc  mov     rbx, rax
0x140021bbf  test    rax, rax
0x140021bc2  jz      loc_140021CAE
0x140021bc8  mov     [rax+4], r12w
0x140021bcd  mov     r13d, 6
0x140021bd3  mov     [rax], r13d
0x140021bd6  mov     ebp, r12d
0x140021bd9  test    rsi, rsi
0x140021bdc  jz      loc_140021CC8
0x140021be2  movzx   eax, word ptr [rsi]
0x140021be5  lea     rcx, [rbx+6]; void *
0x140021be9  add     ax, r13w
0x140021bed  mov     [rbx], ax
0x140021bf0  movzx   eax, word ptr [rsi]
0x140021bf3  mov     [rbx+4], ax
0x140021bf7  movzx   eax, word ptr [rsi]
0x140021bfa  mov     [rbx+2], ax
0x140021bfe  movzx   r8d, word ptr [rsi]; Size
0x140021c02  mov     rdx, [rsi+8]; Src
0x140021c06  call    memmove
0x140021c0b  movzx   esi, word ptr [rsi]
0x140021c0e  add     esi, r13d
0x140021c11  movzx   eax, word ptr [r14]
0x140021c15  add     [rbx], ax
0x140021c18  movzx   eax, word ptr [r14]
0x140021c1c  add     [rbx+4], ax
0x140021c20  movzx   r8d, word ptr [r14]; Size
0x140021c24  mov     rdx, [r14+8]; Src
0x140021c28  mov     ecx, esi
0x140021c2a  add     rcx, rbx; void *
0x140021c2d  call    memmove
0x140021c32  test    rdi, rdi
0x140021c35  jnz     short loc_140021C56
0x140021c37  mov     rcx, [rsp+88h+arg_20]
0x140021c3f  mov     [rcx], rbx
0x140021c42  mov     eax, ebp
0x140021c44  add     rsp, 48h
0x140021c48  pop     r15
0x140021c4a  pop     r14
0x140021c4c  pop     r13
0x140021c4e  pop     r12
0x140021c50  pop     rdi
0x140021c51  pop     rsi
0x140021c52  pop     rbp
0x140021c53  pop     rbx
0x140021c54  retn
0x140021c56  cmp     [rdi], r12w
0x140021c5a  jbe     short loc_140021C37
0x140021c5c  movzx   ecx, word ptr [rbx+4]
0x140021c60  mov     r8d, 5Ch ; '\'
0x140021c66  movzx   edx, word ptr [r14]
0x140021c6a  mov     eax, ecx
0x140021c6c  shr     rax, 1
0x140021c6f  add     edx, esi
0x140021c71  cmp     [rbx+rax*2+4], r8w
0x140021c77  jz      short loc_140021C8D
0x140021c79  add     word ptr [rbx], 2
0x140021c7d  add     cx, 2
0x140021c81  mov     [rbx+4], cx
0x140021c85  mov     [rdx+rbx], r8w
0x140021c8a  add     edx, 2
0x140021c8d  movzx   eax, word ptr [rdi]
0x140021c90  add     [rbx+4], ax
0x140021c94  movzx   ecx, word ptr [rdi]
0x140021c97  add     [rbx], cx
0x140021c9a  movzx   r8d, word ptr [rdi]; Size
0x140021c9e  mov     ecx, edx
0x140021ca0  mov     rdx, [rdi+8]; Src
0x140021ca4  add     rcx, rbx; void *
0x140021ca7  call    memmove
0x140021cac  jmp     short loc_140021C37
0x140021cae  lea     rax, WPP_RECORDER_INITIALIZED
0x140021cb5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140021cbc  jnz     short loc_140021CD5
0x140021cbe  mov     ebp, 0C000009Ah
0x140021cc3  jmp     loc_140021C42
0x140021cc8  mov     esi, r13d
0x140021ccb  mov     [rax+2], r15w
0x140021cd0  jmp     loc_140021C11
0x140021cd5  mov     rcx, cs:WPP_GLOBAL_Control
0x140021cdc  lea     rax, aOnecoreBaseFsW_9; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140021ce3  mov     r9d, 34h ; '4'
0x140021ce9  mov     [rsp+88h+var_58], 836h
0x140021cf1  mov     [rsp+88h+var_60], rax
0x140021cf6  mov     dl, 2
0x140021cf8  lea     rax, WPP_55845795197b3ed810b516bf1e89ed04_Traceguids
0x140021cff  mov     rcx, [rcx+40h]
0x140021d03  lea     r8d, [r9-2Ch]
0x140021d07  mov     [rsp+88h+var_68], rax
0x140021d0c  call    WPP_RECORDER_SF_sD
0x140021d11  jmp     short loc_140021CBE
```
