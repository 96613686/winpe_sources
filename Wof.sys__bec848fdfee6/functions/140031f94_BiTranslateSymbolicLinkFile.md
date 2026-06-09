# BiTranslateSymbolicLinkFile

- ea: `0x140031f94`
- end: `0x140032109`
- name: `BiTranslateSymbolicLinkFile`
- size: `373`
- prototype: `__int64 __fastcall(wchar_t *SourceString, wchar_t **)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path`

## callers

- `0x140031550`

## callees

- `0x14000da0d`
- `0x1400116c0`
- `0x140031ddc`
- `0x140031f94`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140032063`
- `ntoskrnl!ExAllocatePool2` at `0x140032063`
- `ntoskrnl!wcsrchr` at `0x140031fe1`
- `ntoskrnl!wcsrchr` at `0x140031fe1`

## pseudocode

```c
__int64 __fastcall BiTranslateSymbolicLinkFile(wchar_t *SourceString, wchar_t **a2)
{
  _WORD *v4; // rdi
  wchar_t *v5; // rsi
  wchar_t *v6; // r14
  char v7; // bp
  wchar_t *v8; // rax
  wchar_t *v9; // rbx
  NTSTATUS v10; // eax
  __int64 v11; // rax
  size_t v12; // r14
  __int64 v13; // rax
  wchar_t *Pool2; // rax
  wchar_t *v15; // r13
  unsigned int v16; // ebx
  unsigned int Size; // [rsp+60h] [rbp+8h]
  void *Src; // [rsp+70h] [rbp+18h] BYREF

  Src = 0;
  v4 = 0;
  if ( SourceString && a2 )
  {
    *a2 = 0;
    v5 = SourceString;
    v6 = 0;
    v7 = 0;
    while ( 1 )
    {
      v8 = wcsrchr(v5, 0x5Cu);
      v9 = v8;
      if ( v6 )
        *v6 = 92;
      if ( !v8 )
        break;
      *v8 = 0;
      v10 = BiTranslateSymbolicLink(v5, (PWSTR *)&Src);
      v4 = Src;
      if ( v10 >= 0 )
      {
        *v9 = 92;
        v11 = -1;
        do
          ++v11;
        while ( v4[v11] );
        v12 = (unsigned int)(2 * v11);
        v13 = -1;
        do
          ++v13;
        while ( v9[v13] );
        Size = 2 * v13 + 2;
        Pool2 = (wchar_t *)ExAllocatePool2(258, (unsigned int)v12 + Size, 1262764866);
        *a2 = Pool2;
        v15 = Pool2;
        if ( !Pool2 )
        {
          v16 = -1073741801;
          goto LABEL_20;
        }
        v7 = 1;
        memmove(Pool2, v4, v12);
        memmove((char *)v15 + v12, v9, Size);
        if ( v5 != SourceString )
          ExFreePoolWithTag_0(v5, 0x4B444342u);
        v5 = *a2;
        v9 = (wchar_t *)((char *)*a2 + v12);
        *v9 = 0;
      }
      v6 = v9;
    }
    v16 = v7 == 0 ? 0xC0000001 : 0;
  }
  else
  {
    v16 = -1073741811;
  }
LABEL_20:
  if ( v4 )
    ExFreePoolWithTag_0(v4, 0x4B444342u);
  return v16;
}

```

## disassembly

```asm
0x140031f94  mov     [rsp+arg_8], rbx
0x140031f99  push    rbp
0x140031f9a  push    rsi
0x140031f9b  push    rdi
0x140031f9c  push    r12
0x140031f9e  push    r13
0x140031fa0  push    r14
0x140031fa2  push    r15
0x140031fa4  sub     rsp, 20h
0x140031fa8  xor     r13d, r13d
0x140031fab  mov     r15, rdx
0x140031fae  mov     [rsp+58h+Src], r13
0x140031fb3  mov     r12, rcx
0x140031fb6  mov     edi, r13d
0x140031fb9  test    rcx, rcx
0x140031fbc  jz      loc_1400320DA
0x140031fc2  test    rdx, rdx
0x140031fc5  jz      loc_1400320DA
0x140031fcb  mov     [rdx], r13
0x140031fce  mov     rsi, rcx
0x140031fd1  mov     r14d, r13d
0x140031fd4  mov     bpl, r13b
0x140031fd7  mov     eax, 5Ch ; '\'
0x140031fdc  mov     rcx, rsi; Str
0x140031fdf  mov     edx, eax; Ch
0x140031fe1  call    cs:__imp_wcsrchr
0x140031fe8  nop     dword ptr [rax+rax+00h]
0x140031fed  mov     rbx, rax
0x140031ff0  test    r14, r14
0x140031ff3  jz      short loc_140031FFB
0x140031ff5  mov     word ptr [r14], 5Ch ; '\'
0x140031ffb  test    rbx, rbx
0x140031ffe  jz      loc_1400320CB
0x140032004  lea     rdx, [rsp+58h+Src]
0x140032009  mov     [rax], r13w
0x14003200d  mov     rcx, rsi; SourceString
0x140032010  call    BiTranslateSymbolicLink
0x140032015  mov     rdi, [rsp+58h+Src]
0x14003201a  test    eax, eax
0x14003201c  js      loc_1400320BC
0x140032022  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140032026  mov     word ptr [rbx], 5Ch ; '\'
0x14003202b  mov     rax, rcx
0x14003202e  inc     rax
0x140032031  cmp     [rdi+rax*2], r13w
0x140032036  jnz     short loc_14003202E
0x140032038  lea     r14d, [rax+rax]
0x14003203c  mov     rax, rcx
0x14003203f  inc     rax
0x140032042  cmp     [rbx+rax*2], r13w
0x140032047  jnz     short loc_14003203F
0x140032049  lea     eax, ds:2[rax*2]
0x140032050  mov     ecx, 102h
0x140032055  lea     edx, [r14+rax]
0x140032059  mov     dword ptr [rsp+58h+Size], eax
0x14003205d  mov     r8d, 4B444342h
0x140032063  call    cs:__imp_ExAllocatePool2
0x14003206a  nop     dword ptr [rax+rax+00h]
0x14003206f  mov     [r15], rax
0x140032072  mov     r13, rax
0x140032075  test    rax, rax
0x140032078  jz      short loc_1400320C4
0x14003207a  mov     r8, r14; Size
0x14003207d  mov     rdx, rdi; Src
0x140032080  mov     rcx, rax; void *
0x140032083  mov     bpl, 1
0x140032086  call    memmove
0x14003208b  mov     r8d, dword ptr [rsp+58h+Size]; Size
0x140032090  lea     rcx, [r14+r13]; void *
0x140032094  mov     rdx, rbx; Src
0x140032097  call    memmove
0x14003209c  cmp     rsi, r12
0x14003209f  jz      short loc_1400320AE
0x1400320a1  mov     edx, 4B444342h; Tag
0x1400320a6  mov     rcx, rsi; P
0x1400320a9  call    ExFreePoolWithTag_0
0x1400320ae  mov     rsi, [r15]
0x1400320b1  xor     r13d, r13d
0x1400320b4  lea     rbx, [rsi+r14]
0x1400320b8  mov     [rbx], r13w
0x1400320bc  mov     r14, rbx
0x1400320bf  jmp     loc_140031FD7
0x1400320c4  mov     ebx, 0C0000017h
0x1400320c9  jmp     short loc_1400320DF
0x1400320cb  neg     bpl
0x1400320ce  sbb     ebx, ebx
0x1400320d0  not     ebx
0x1400320d2  and     ebx, 0C0000001h
0x1400320d8  jmp     short loc_1400320DF
0x1400320da  mov     ebx, 0C000000Dh
0x1400320df  test    rdi, rdi
0x1400320e2  jz      short loc_1400320F1
0x1400320e4  mov     edx, 4B444342h; Tag
0x1400320e9  mov     rcx, rdi; P
0x1400320ec  call    ExFreePoolWithTag_0
0x1400320f1  mov     eax, ebx
0x1400320f3  mov     rbx, [rsp+58h+arg_8]
0x1400320f8  add     rsp, 20h
0x1400320fc  pop     r15
0x1400320fe  pop     r14
0x140032100  pop     r13
0x140032102  pop     r12
0x140032104  pop     rdi
0x140032105  pop     rsi
0x140032106  pop     rbp
0x140032107  retn
```
