# USBDInternal_BuildServicePath

- ea: `0x14000c6b4`
- end: `0x14000c89e`
- name: `USBDInternal_BuildServicePath`
- size: `490`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000c9f0`

## callees

- `0x14000c6b4`
- `0x14000d900`
- `0x14000dc00`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000c87a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c87a`
- `ntoskrnl!RtlCompareMemory` at `0x14000c717`
- `ntoskrnl!RtlCompareMemory` at `0x14000c717`
- `ntoskrnl!DbgPrintEx` at `0x14000c6f3`
- `ntoskrnl!DbgPrintEx` at `0x14000c77b`
- `ntoskrnl!DbgPrintEx` at `0x14000c866`
- `ntoskrnl!DbgPrintEx` at `0x14000c6f3`
- `ntoskrnl!DbgPrintEx` at `0x14000c77b`
- `ntoskrnl!DbgPrintEx` at `0x14000c866`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c746`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14000c746`

## string_xrefs

- `0x14000c76f`: `Couldnt allocate servicePath of size %d\n`

## pseudocode

```c
__int64 __fastcall USBDInternal_BuildServicePath(__int64 a1, _QWORD *a2)
{
  __int64 v2; // rbx
  char *v4; // rsi
  unsigned int v5; // ebx
  __int64 v6; // r14
  unsigned int v7; // ebx
  unsigned int v8; // ebp
  char *PoolWithTag; // rax
  unsigned __int64 v10; // rdi
  unsigned __int64 v11; // rcx
  _WORD *v12; // rax
  unsigned __int64 v13; // rax
  const wchar_t *v14; // r8
  __int64 v15; // rcx
  char *v16; // rdx
  unsigned __int64 i; // rdi
  char *v18; // rcx

  v2 = *(_QWORD *)(a1 + 8);
  v4 = 0;
  if ( *(_WORD *)(v2 + 56) > 0x10u && RtlCompareMemory(*(const void **)(v2 + 64), L"\\Driver\\", 0x10u) == 16 )
  {
    v6 = *(_QWORD *)(v2 + 64);
    v7 = *(unsigned __int16 *)(v2 + 56) - 16;
    v8 = v7 + 24;
    PoolWithTag = (char *)ExAllocatePoolWithTag(PoolType, v7 + 24, 0x75617370u);
    v4 = PoolWithTag;
    if ( PoolWithTag )
    {
      memset(PoolWithTag, 0, v7 + 24);
      memmove(v4, (const void *)(v6 + 16), v7);
      v10 = (unsigned __int64)(v7 + 24) >> 1;
      if ( v10 )
      {
        v11 = (unsigned __int64)(v7 + 24) >> 1;
        v12 = v4;
        do
        {
          if ( !*v12 )
            break;
          ++v12;
          --v11;
        }
        while ( v11 );
        v5 = v11 == 0 ? 0xC000000D : 0;
        if ( v11 )
          v13 = v10 - v11;
        else
          v13 = 0;
        if ( v11 )
        {
          v14 = L"\\Parameters";
          v15 = 2147483646;
          v16 = &v4[2 * v13];
          for ( i = v10 - v13; i; --i )
          {
            if ( !v15 )
              break;
            if ( !*v14 )
              break;
            *(_WORD *)v16 = *v14++;
            v16 += 2;
            --v15;
          }
          v18 = v16 - 2;
          v5 = i == 0 ? 0x80000005 : 0;
          if ( i )
            v18 = v16;
          *(_WORD *)v18 = 0;
          if ( i )
          {
            v5 = 0;
            goto LABEL_29;
          }
        }
      }
      else
      {
        v5 = -1073741811;
      }
      if ( g_EnableDbgPrints )
        DbgPrintEx(0x4Du, 0, "RtlStringCchCatW failed with status 0x%x", v5);
      ExFreePoolWithTag(v4, 0x75617370u);
      v4 = 0;
    }
    else
    {
      v5 = -1073741670;
      if ( g_EnableDbgPrints )
        DbgPrintEx(0x4Du, 0, "Couldnt allocate servicePath of size %d\n", v8);
    }
  }
  else
  {
    if ( g_EnableDbgPrints )
      DbgPrintEx(0x4Du, 0, "Unexpected Driver name, Drvobj 0x%p\n", (const void *)v2);
    v5 = -1073741595;
  }
LABEL_29:
  *a2 = v4;
  return v5;
}

```

## disassembly

```asm
0x14000c6b4  push    rbx
0x14000c6b6  push    rbp
0x14000c6b7  push    rsi
0x14000c6b8  push    rdi
0x14000c6b9  push    r12
0x14000c6bb  push    r14
0x14000c6bd  push    r15
0x14000c6bf  sub     rsp, 20h
0x14000c6c3  mov     rbx, [rcx+8]
0x14000c6c7  xor     r12d, r12d
0x14000c6ca  mov     r15, rdx
0x14000c6cd  mov     esi, r12d
0x14000c6d0  lea     edi, [r12+10h]
0x14000c6d5  cmp     [rbx+38h], di
0x14000c6d9  ja      short loc_14000C709
0x14000c6db  cmp     cs:g_EnableDbgPrints, r12b
0x14000c6e2  jz      short loc_14000C6FF
0x14000c6e4  xor     edx, edx; Level
0x14000c6e6  lea     r8, aUnexpectedDriv; "Unexpected Driver name, Drvobj 0x%p\n"
0x14000c6ed  mov     r9, rbx
0x14000c6f0  lea     ecx, [rdx+4Dh]; ComponentId
0x14000c6f3  call    cs:__imp_DbgPrintEx
0x14000c6fa  nop     dword ptr [rax+rax+00h]
0x14000c6ff  mov     ebx, 0C00000E5h
0x14000c704  jmp     loc_14000C889
0x14000c709  mov     rcx, [rbx+40h]; Source1
0x14000c70d  lea     rdx, aDriver; "\\Driver\\"
0x14000c714  mov     r8, rdi; Length
0x14000c717  call    cs:__imp_RtlCompareMemory
0x14000c71e  nop     dword ptr [rax+rax+00h]
0x14000c723  cmp     rax, rdi
0x14000c726  jnz     short loc_14000C6DB
0x14000c728  mov     r14, [rbx+40h]
0x14000c72c  mov     r8d, 75617370h; Tag
0x14000c732  movzx   ebx, word ptr [rbx+38h]
0x14000c736  mov     ecx, cs:PoolType; PoolType
0x14000c73c  add     ebx, 0FFFFFFF0h
0x14000c73f  lea     ebp, [rbx+18h]
0x14000c742  mov     edx, ebp; NumberOfBytes
0x14000c744  mov     edi, ebp
0x14000c746  call    cs:__imp_ExAllocatePoolWithTag
0x14000c74d  nop     dword ptr [rax+rax+00h]
0x14000c752  mov     rsi, rax
0x14000c755  test    rax, rax
0x14000c758  jnz     short loc_14000C78C
0x14000c75a  cmp     cs:g_EnableDbgPrints, r12b
0x14000c761  mov     ebx, 0C000009Ah
0x14000c766  jz      loc_14000C889
0x14000c76c  mov     r9d, ebp
0x14000c76f  lea     r8, aCouldntAllocat; "Couldnt allocate servicePath of size %d"...
0x14000c776  xor     edx, edx; Level
0x14000c778  lea     ecx, [rax+4Dh]; ComponentId
0x14000c77b  call    cs:__imp_DbgPrintEx
0x14000c782  nop     dword ptr [rax+rax+00h]
0x14000c787  jmp     loc_14000C889
0x14000c78c  mov     r8, rdi; Size
0x14000c78f  xor     edx, edx; Val
0x14000c791  mov     rcx, rsi; void *
0x14000c794  call    memset
0x14000c799  mov     r8d, ebx; Size
0x14000c79c  lea     rdx, [r14+10h]; Src
0x14000c7a0  mov     rcx, rsi; void *
0x14000c7a3  call    memmove
0x14000c7a8  shr     rdi, 1
0x14000c7ab  jz      loc_14000C849
0x14000c7b1  mov     rcx, rdi
0x14000c7b4  mov     rax, rsi
0x14000c7b7  cmp     [rax], r12w
0x14000c7bb  jz      short loc_14000C7C7
0x14000c7bd  add     rax, 2
0x14000c7c1  sub     rcx, 1
0x14000c7c5  jnz     short loc_14000C7B7
0x14000c7c7  mov     rax, rcx
0x14000c7ca  neg     rax
0x14000c7cd  sbb     ebx, ebx
0x14000c7cf  not     ebx
0x14000c7d1  and     ebx, 0C000000Dh
0x14000c7d7  test    rcx, rcx
0x14000c7da  jz      short loc_14000C7E4
0x14000c7dc  mov     rax, rdi
0x14000c7df  sub     rax, rcx
0x14000c7e2  jmp     short loc_14000C7E7
0x14000c7e4  mov     rax, r12
0x14000c7e7  test    rcx, rcx
0x14000c7ea  jz      short loc_14000C84E
0x14000c7ec  lea     r8, aParameters; "\\Parameters"
0x14000c7f3  mov     ecx, 7FFFFFFEh
0x14000c7f8  lea     rdx, [rsi+rax*2]
0x14000c7fc  sub     rdi, rax
0x14000c7ff  jz      short loc_14000C823
0x14000c801  test    rcx, rcx
0x14000c804  jz      short loc_14000C823
0x14000c806  movzx   eax, word ptr [r8]
0x14000c80a  test    ax, ax
0x14000c80d  jz      short loc_14000C823
0x14000c80f  mov     [rdx], ax
0x14000c812  add     r8, 2
0x14000c816  add     rdx, 2
0x14000c81a  dec     rcx
0x14000c81d  sub     rdi, 1
0x14000c821  jnz     short loc_14000C801
0x14000c823  mov     rax, rdi
0x14000c826  lea     rcx, [rdx-2]
0x14000c82a  neg     rax
0x14000c82d  sbb     ebx, ebx
0x14000c82f  not     ebx
0x14000c831  and     ebx, 80000005h
0x14000c837  test    rdi, rdi
0x14000c83a  cmovnz  rcx, rdx
0x14000c83e  mov     [rcx], r12w
0x14000c842  jz      short loc_14000C84E
0x14000c844  mov     ebx, r12d
0x14000c847  jmp     short loc_14000C889
0x14000c849  mov     ebx, 0C000000Dh
0x14000c84e  cmp     cs:g_EnableDbgPrints, r12b
0x14000c855  jz      short loc_14000C872
0x14000c857  xor     edx, edx; Level
0x14000c859  lea     r8, aRtlstringcchca; "RtlStringCchCatW failed with status 0x%"...
0x14000c860  mov     r9d, ebx
0x14000c863  lea     ecx, [rdx+4Dh]; ComponentId
0x14000c866  call    cs:__imp_DbgPrintEx
0x14000c86d  nop     dword ptr [rax+rax+00h]
0x14000c872  mov     edx, 75617370h; Tag
0x14000c877  mov     rcx, rsi; P
0x14000c87a  call    cs:__imp_ExFreePoolWithTag
0x14000c881  nop     dword ptr [rax+rax+00h]
0x14000c886  mov     rsi, r12
0x14000c889  mov     [r15], rsi
0x14000c88c  mov     eax, ebx
0x14000c88e  add     rsp, 20h
0x14000c892  pop     r15
0x14000c894  pop     r14
0x14000c896  pop     r12
0x14000c898  pop     rdi
0x14000c899  pop     rsi
0x14000c89a  pop     rbp
0x14000c89b  pop     rbx
0x14000c89c  retn
```
