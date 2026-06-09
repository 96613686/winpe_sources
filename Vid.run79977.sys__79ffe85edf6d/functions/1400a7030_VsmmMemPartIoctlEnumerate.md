# VsmmMemPartIoctlEnumerate

- ea: `0x1400a7030`
- end: `0x1400a725a`
- name: `VsmmMemPartIoctlEnumerate`
- size: `554`
- prototype: `__int64 __fastcall(ACCESS_MASK DesiredAccess)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x14003782c`

## callees

- `0x140016afc`
- `0x1400386a0`
- `0x140079dfc`
- `0x140079ed4`
- `0x140079fac`
- `0x1400a7030`
- `0x1400fe5ec`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x1400a711c`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400a711c`
- `ntoskrnl!PsPartitionType` at `0x1400a70eb`
- `ntoskrnl!NtClose` at `0x1400a7230`
- `ntoskrnl!NtClose` at `0x1400a7230`

## pseudocode

```c
__int64 __fastcall VsmmMemPartIoctlEnumerate(ACCESS_MASK DesiredAccess, __int64 a2, void *a3)
{
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // rdi
  int v7; // esi
  unsigned __int64 ULong64FromUser; // r15
  int i; // esi
  __int64 v10; // rax
  __int64 v11; // r13
  void *PartitionObject; // rax
  POBJECT_TYPE ObjectType; // rdx
  void *Handle[2]; // [rsp+48h] [rbp-70h] BYREF
  HANDLE Src[12]; // [rsp+58h] [rbp-60h] BYREF

  v5 = 0;
  v6 = 0;
  if ( a2 )
  {
    ULong64FromUser = RtlReadULong64FromUser(a2);
    if ( ULong64FromUser >= 2 )
      ULong64FromUser = 2;
    if ( DesiredAccess - 1 <= 1 || DesiredAccess == 2031619 )
    {
      for ( i = 0; i < 2; ++i )
      {
        Handle[1] = (void *)0xFFFFFFFFLL;
        Handle[0] = 0;
        v10 = VsmmMemReserveMemPartGet((unsigned int)i);
        v11 = v10;
        if ( v10 )
        {
          if ( (unsigned int)(*(_DWORD *)(v10 + 32) - 1) <= 2 )
          {
            PartitionObject = (void *)VsmmMemPartGetPartitionObject(v10);
            if ( ObOpenObjectByPointer(PartitionObject, 0, 0, DesiredAccess, ObjectType, 1, Handle) >= 0 )
            {
              LODWORD(Handle[1]) = *(_DWORD *)(v11 + 28);
              *(_OWORD *)&Src[2 * v6++] = *(_OWORD *)Handle;
            }
          }
        }
      }
      if ( v6 )
      {
        if ( ULong64FromUser < v6 || !a3 )
        {
          v7 = -1073741789;
          goto LABEL_20;
        }
        RtlCopyToUser(a3, Src, 16 * v6);
      }
      v7 = 0;
      goto LABEL_20;
    }
    v7 = -1073741811;
  }
  else
  {
    v7 = -1073741811;
    VidTraceErrorInternal0("VsmmMemPartIoctlEnumerate", "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempart.c", 210);
  }
LABEL_20:
  RtlWriteULong64ToUser(a2, v6);
  if ( v7 < 0 && v6 )
  {
    do
      NtClose(Src[2 * v5++]);
    while ( v5 < v6 );
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1400a7030  mov     [rsp+arg_10], r8
0x1400a7035  mov     [rsp+arg_8], rdx
0x1400a703a  push    rbx
0x1400a703b  push    rsi
0x1400a703c  push    rdi
0x1400a703d  push    r12
0x1400a703f  push    r13
0x1400a7041  push    r14
0x1400a7043  push    r15
0x1400a7045  sub     rsp, 80h
0x1400a704c  mov     r14, rdx
0x1400a704f  mov     r12d, ecx
0x1400a7052  xor     ebx, ebx
0x1400a7054  mov     edi, ebx
0x1400a7056  mov     [rsp+0B8h+arg_18], rbx
0x1400a705e  test    rdx, rdx
0x1400a7061  jnz     short loc_1400A7086
0x1400a7063  mov     esi, 0C000000Dh
0x1400a7068  mov     r8d, 0D2h
0x1400a706e  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a7075  lea     rcx, aVsmmmempartioc; "VsmmMemPartIoctlEnumerate"
0x1400a707c  call    VidTraceErrorInternal0
0x1400a7081  jmp     loc_1400A71E9
0x1400a7086  mov     rcx, rdx
0x1400a7089  call    RtlReadULong64FromUser
0x1400a708e  mov     r15, rax
0x1400a7091  mov     [rsp+0B8h+var_78], rax
0x1400a7096  mov     eax, 2
0x1400a709b  cmp     r15, rax
0x1400a709e  cmovnb  r15, rax
0x1400a70a2  lea     eax, [r12-1]
0x1400a70a7  cmp     eax, 1
0x1400a70aa  jbe     short loc_1400A70BF
0x1400a70ac  cmp     r12d, 1F0003h
0x1400a70b3  jz      short loc_1400A70BF
0x1400a70b5  mov     esi, 0C000000Dh
0x1400a70ba  jmp     loc_1400A71E9
0x1400a70bf  mov     esi, ebx
0x1400a70c1  mov     dword ptr [rsp+0B8h+var_70+0Ch], ebx
0x1400a70c5  mov     dword ptr [rsp+0B8h+var_70+8], 0FFFFFFFFh
0x1400a70cd  mov     [rsp+0B8h+var_70], rbx
0x1400a70d2  mov     ecx, esi
0x1400a70d4  call    VsmmMemReserveMemPartGet
0x1400a70d9  mov     r13, rax
0x1400a70dc  test    rax, rax
0x1400a70df  jz      short loc_1400A7150
0x1400a70e1  mov     eax, [rax+20h]
0x1400a70e4  dec     eax
0x1400a70e6  cmp     eax, 2
0x1400a70e9  ja      short loc_1400A7150
0x1400a70eb  mov     rax, cs:__imp_PsPartitionType
0x1400a70f2  mov     rdx, [rax]
0x1400a70f5  mov     rcx, r13
0x1400a70f8  call    VsmmMemPartGetPartitionObject
0x1400a70fd  mov     rcx, rax; Object
0x1400a7100  lea     rax, [rsp+0B8h+var_70]
0x1400a7105  mov     [rsp+0B8h+Handle], rax; Handle
0x1400a710a  mov     [rsp+0B8h+AccessMode], 1; AccessMode
0x1400a710f  mov     [rsp+0B8h+ObjectType], rdx; ObjectType
0x1400a7114  mov     r9d, r12d; DesiredAccess
0x1400a7117  xor     r8d, r8d; PassedAccessState
0x1400a711a  xor     edx, edx; HandleAttributes
0x1400a711c  call    cs:__imp_ObOpenObjectByPointer
0x1400a7123  nop     dword ptr [rax+rax+00h]
0x1400a7128  test    eax, eax
0x1400a712a  js      short loc_1400A7150
0x1400a712c  mov     eax, [r13+1Ch]
0x1400a7130  mov     dword ptr [rsp+0B8h+var_70+8], eax
0x1400a7134  mov     rax, rdi
0x1400a7137  add     rax, rax
0x1400a713a  movups  xmm0, xmmword ptr [rsp+0B8h+var_70]
0x1400a713f  movdqu  xmmword ptr [rsp+rax*8+0B8h+Src], xmm0
0x1400a7145  inc     rdi
0x1400a7148  mov     [rsp+0B8h+arg_18], rdi
0x1400a7150  inc     esi
0x1400a7152  cmp     esi, 2
0x1400a7155  jl      loc_1400A70C1
0x1400a715b  test    rdi, rdi
0x1400a715e  jz      short loc_1400A71BE
0x1400a7160  cmp     r15, rdi
0x1400a7163  jb      short loc_1400A71B7
0x1400a7165  mov     rax, [rsp+0B8h+arg_10]
0x1400a716d  test    rax, rax
0x1400a7170  jz      short loc_1400A71B7
0x1400a7172  mov     r8, rdi
0x1400a7175  shl     r8, 4; Size
0x1400a7179  lea     rdx, [rsp+0B8h+Src]; Src
0x1400a717e  mov     rcx, rax; void *
0x1400a7181  call    RtlCopyToUser
0x1400a7186  jmp     short loc_1400A71BE
0x1400a7188  mov     esi, eax
0x1400a718a  mov     r8d, 13Bh
0x1400a7190  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a7197  lea     rcx, aVsmmmempartioc; "VsmmMemPartIoctlEnumerate"
0x1400a719e  call    VidTraceErrorInternal0
0x1400a71a3  xor     ebx, ebx
0x1400a71a5  mov     r14, [rsp+0B8h+arg_8]
0x1400a71ad  mov     rdi, [rsp+0B8h+arg_18]
0x1400a71b5  jmp     short loc_1400A71E9
0x1400a71b7  mov     esi, 0C0000023h
0x1400a71bc  jmp     short loc_1400A71E9
0x1400a71be  mov     esi, ebx
0x1400a71c0  jmp     short loc_1400A71E9
0x1400a71c2  mov     esi, eax
0x1400a71c4  mov     r8d, 0DCh
0x1400a71ca  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a71d1  lea     rcx, aVsmmmempartioc; "VsmmMemPartIoctlEnumerate"
0x1400a71d8  call    VidTraceErrorInternal0
0x1400a71dd  xor     ebx, ebx
0x1400a71df  mov     r14, [rsp+0B8h+arg_8]
0x1400a71e7  mov     edi, ebx
0x1400a71e9  nop
0x1400a71ea  mov     rdx, rdi
0x1400a71ed  mov     rcx, r14
0x1400a71f0  call    RtlWriteULong64ToUser
0x1400a71f5  jmp     short loc_1400A721C
0x1400a71f7  mov     esi, eax
0x1400a71f9  mov     r8d, 157h
0x1400a71ff  lea     rdx, aOnecoreVmVidSy_38; "onecore\\vm\\vid\\sys\\vsmm\\vsmmmempar"...
0x1400a7206  lea     rcx, aVsmmmempartioc; "VsmmMemPartIoctlEnumerate"
0x1400a720d  call    VidTraceErrorInternal0
0x1400a7212  xor     ebx, ebx
0x1400a7214  mov     rdi, [rsp+0B8h+arg_18]
0x1400a721c  test    esi, esi
0x1400a721e  jns     short loc_1400A7244
0x1400a7220  test    rdi, rdi
0x1400a7223  jz      short loc_1400A7244
0x1400a7225  mov     rcx, rbx
0x1400a7228  add     rcx, rcx
0x1400a722b  mov     rcx, [rsp+rcx*8+0B8h+Src]; Handle
0x1400a7230  call    cs:__imp_NtClose
0x1400a7237  nop     dword ptr [rax+rax+00h]
0x1400a723c  inc     rbx
0x1400a723f  cmp     rbx, rdi
0x1400a7242  jb      short loc_1400A7225
0x1400a7244  mov     eax, esi
0x1400a7246  add     rsp, 80h
0x1400a724d  pop     r15
0x1400a724f  pop     r14
0x1400a7251  pop     r13
0x1400a7253  pop     r12
0x1400a7255  pop     rdi
0x1400a7256  pop     rsi
0x1400a7257  pop     rbx
0x1400a7258  retn
```
