# CitmInitialize

- ea: `0x14002bb4c`
- end: `0x14002bd6c`
- name: `CitmInitialize`
- size: `544`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14002a3dc`

## callees

- `0x140003a58`
- `0x14002bb4c`
- `0x14002c4a4`
- `0x14003e364`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002bd2c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002bd45`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002bd2c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002bd45`
- `ntoskrnl!ExAllocatePool2` at `0x14002bc32`
- `ntoskrnl!ExAllocatePool2` at `0x14002bc32`
- `ntoskrnl!PsSetLoadImageNotifyRoutine` at `0x14002bcd9`
- `ntoskrnl!PsSetLoadImageNotifyRoutine` at `0x14002bcd9`

## string_xrefs

- `0x14002bbb9`: `\System32\mrt100.dll`
- `0x14002bbc7`: `Failed to read registry [%x]`

## pseudocode

```c
__int64 __fastcall CitmInitialize(__int64 a1)
{
  char *Pool2; // rsi
  int v3; // eax
  PVOID v4; // rdi
  unsigned int v5; // ebx
  const wchar_t *v6; // rbx
  __int64 v7; // rcx
  const wchar_t *v8; // rax
  __int64 v9; // rdx
  int v10; // r15d
  __int64 v11; // rax
  char *v12; // r12
  __int16 v13; // ax
  int v14; // eax
  __int64 v15; // rax
  NTSTATUS ImageNotifyRoutine; // eax
  __int64 v18; // [rsp+20h] [rbp-38h]
  PVOID P; // [rsp+68h] [rbp+10h] BYREF

  P = 0;
  Pool2 = 0;
  v3 = CitmpReadMultiString(&P);
  v4 = P;
  if ( v3 < 0 )
  {
    v6 = L"\\System32\\mrt100.dll";
    if ( v3 != -1073741772 )
      AslLogCallPrintf(1, "CitmInitialize", 369, "Failed to read registry [%x]", v3);
  }
  else
  {
    if ( !P )
    {
      v5 = -1073741595;
      AslLogCallPrintf(1, "CitmInitialize", 375, "Failed to find modules to track [%x]", -1073741595);
      goto LABEL_27;
    }
    v6 = (const wchar_t *)P;
  }
  LODWORD(v7) = 0;
  v8 = v6;
  if ( *v6 )
  {
    do
    {
      v7 = (unsigned int)(v7 + 1);
      v9 = -1;
      do
        ++v9;
      while ( v8[v9] );
      v8 += v9 + 1;
    }
    while ( *v8 );
    if ( (_DWORD)v7 )
    {
      Pool2 = (char *)ExAllocatePool2(256, 24 * v7, 1836345667);
      if ( !Pool2 )
      {
        v5 = -1073741801;
        AslLogCallPrintf(1, "CitmInitialize", 399, "Out of memory");
        goto LABEL_27;
      }
      v10 = 0;
      while ( *v6 )
      {
        v11 = -1;
        v12 = &Pool2[24 * v10];
        *((_QWORD *)v12 + 1) = v6;
        do
          ++v11;
        while ( v6[v11] );
        v13 = 2 * v11;
        *(_WORD *)v12 = v13;
        *((_WORD *)v12 + 1) = v13;
        v14 = CitmpComputeFileNameHash(&Pool2[24 * v10++]);
        *((_DWORD *)v12 + 4) = v14;
        v15 = -1;
        do
          ++v15;
        while ( v6[v15] );
        v6 += v15 + 1;
      }
      if ( !*(_DWORD *)(a1 + 704) )
      {
        ImageNotifyRoutine = PsSetLoadImageNotifyRoutine(CitmpLoadImageCallback);
        v5 = ImageNotifyRoutine;
        if ( ImageNotifyRoutine < 0 )
        {
          LODWORD(v18) = ImageNotifyRoutine;
          AslLogCallPrintf(1, "CitmInitialize", 420, "Failed to register callback [%x]", v18);
          goto LABEL_27;
        }
      }
      *(_QWORD *)(a1 + 664) = v4;
      v4 = 0;
      *(_QWORD *)(a1 + 648) = Pool2;
      Pool2 = 0;
      *(_DWORD *)(a1 + 656) = v10;
    }
  }
  v5 = 0;
LABEL_27:
  if ( v4 )
    ExFreePoolWithTag(v4, 0x6D746943u);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x6D746943u);
  return v5;
}

```

## disassembly

```asm
0x14002bb4c  mov     rax, rsp
0x14002bb4f  mov     [rax+8], rbx
0x14002bb53  mov     [rax+18h], rsi
0x14002bb57  push    rdi
0x14002bb58  push    r12
0x14002bb5a  push    r13
0x14002bb5c  push    r14
0x14002bb5e  push    r15
0x14002bb60  sub     rsp, 30h
0x14002bb64  mov     r14, rcx
0x14002bb67  xor     r13d, r13d
0x14002bb6a  lea     rcx, [rax+10h]
0x14002bb6e  mov     [rax+10h], r13
0x14002bb72  mov     esi, r13d
0x14002bb75  call    CitmpReadMultiString
0x14002bb7a  mov     rdi, [rsp+58h+P]
0x14002bb7f  test    eax, eax
0x14002bb81  js      short loc_14002BBB9
0x14002bb83  test    rdi, rdi
0x14002bb86  jnz     short loc_14002BBB4
0x14002bb88  mov     ebx, 0C00000E5h
0x14002bb8d  lea     r9, aFailedToFindMo; "Failed to find modules to track [%x]"
0x14002bb94  mov     dword ptr [rsp+58h+var_38], ebx
0x14002bb98  mov     r8d, 177h
0x14002bb9e  lea     rdx, aCitminitialize; "CitmInitialize"
0x14002bba5  mov     ecx, 1
0x14002bbaa  call    AslLogCallPrintf
0x14002bbaf  jmp     loc_14002BD1F
0x14002bbb4  mov     rbx, rdi
0x14002bbb7  jmp     short loc_14002BBE9
0x14002bbb9  lea     rbx, aSystem32Mrt100; "\\System32\\mrt100.dll"
0x14002bbc0  cmp     eax, 0C0000034h
0x14002bbc5  jz      short loc_14002BBE9
0x14002bbc7  lea     r9, aFailedToReadRe; "Failed to read registry [%x]"
0x14002bbce  mov     dword ptr [rsp+58h+var_38], eax
0x14002bbd2  mov     r8d, 171h
0x14002bbd8  lea     rdx, aCitminitialize; "CitmInitialize"
0x14002bbdf  mov     ecx, 1
0x14002bbe4  call    AslLogCallPrintf
0x14002bbe9  mov     ecx, r13d
0x14002bbec  mov     rax, rbx
0x14002bbef  cmp     [rbx], r13w
0x14002bbf3  jz      loc_14002BD1C
0x14002bbf9  inc     ecx
0x14002bbfb  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14002bbff  inc     rdx
0x14002bc02  cmp     [rax+rdx*2], r13w
0x14002bc07  jnz     short loc_14002BBFF
0x14002bc09  lea     rax, [rax+rdx*2]
0x14002bc0d  add     rax, 2
0x14002bc11  cmp     [rax], r13w
0x14002bc15  jnz     short loc_14002BBF9
0x14002bc17  test    ecx, ecx
0x14002bc19  jz      loc_14002BD1C
0x14002bc1f  lea     rdx, [rcx+rcx*2]
0x14002bc23  mov     r8d, 6D746943h
0x14002bc29  shl     rdx, 3
0x14002bc2d  mov     ecx, 100h
0x14002bc32  call    cs:__imp_ExAllocatePool2
0x14002bc39  nop     dword ptr [rax+rax+00h]
0x14002bc3e  mov     rsi, rax
0x14002bc41  test    rax, rax
0x14002bc44  jnz     short loc_14002BC6C
0x14002bc46  lea     r9, aOutOfMemory; "Out of memory"
0x14002bc4d  mov     r8d, 18Fh
0x14002bc53  lea     rdx, aCitminitialize; "CitmInitialize"
0x14002bc5a  mov     ebx, 0C0000017h
0x14002bc5f  lea     ecx, [rax+1]
0x14002bc62  call    AslLogCallPrintf
0x14002bc67  jmp     loc_14002BD1F
0x14002bc6c  mov     r15d, r13d
0x14002bc6f  jmp     short loc_14002BCC3
0x14002bc71  mov     eax, r15d
0x14002bc74  lea     rcx, [rax+rax*2]
0x14002bc78  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002bc7c  lea     r12, [rsi+rcx*8]
0x14002bc80  mov     [r12+8], rbx
0x14002bc85  inc     rax
0x14002bc88  cmp     [rbx+rax*2], r13w
0x14002bc8d  jnz     short loc_14002BC85
0x14002bc8f  add     ax, ax
0x14002bc92  mov     rcx, r12
0x14002bc95  mov     [r12], ax
0x14002bc9a  mov     [r12+2], ax
0x14002bca0  call    CitmpComputeFileNameHash
0x14002bca5  inc     r15d
0x14002bca8  mov     [r12+10h], eax
0x14002bcad  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002bcb1  inc     rax
0x14002bcb4  cmp     [rbx+rax*2], r13w
0x14002bcb9  jnz     short loc_14002BCB1
0x14002bcbb  lea     rbx, [rbx+rax*2]
0x14002bcbf  add     rbx, 2
0x14002bcc3  cmp     [rbx], r13w
0x14002bcc7  jnz     short loc_14002BC71
0x14002bcc9  cmp     [r14+2C0h], r13d
0x14002bcd0  jnz     short loc_14002BD01
0x14002bcd2  lea     rcx, CitmpLoadImageCallback; NotifyRoutine
0x14002bcd9  call    cs:__imp_PsSetLoadImageNotifyRoutine
0x14002bce0  nop     dword ptr [rax+rax+00h]
0x14002bce5  mov     ebx, eax
0x14002bce7  test    eax, eax
0x14002bce9  jns     short loc_14002BD01
0x14002bceb  mov     dword ptr [rsp+58h+var_38], eax
0x14002bcef  lea     r9, aFailedToRegist_1; "Failed to register callback [%x]"
0x14002bcf6  mov     r8d, 1A4h
0x14002bcfc  jmp     loc_14002BB9E
0x14002bd01  mov     [r14+298h], rdi
0x14002bd08  mov     rdi, r13
0x14002bd0b  mov     [r14+288h], rsi
0x14002bd12  mov     rsi, r13
0x14002bd15  mov     [r14+290h], r15d
0x14002bd1c  mov     ebx, r13d
0x14002bd1f  test    rdi, rdi
0x14002bd22  jz      short loc_14002BD38
0x14002bd24  mov     edx, 6D746943h; Tag
0x14002bd29  mov     rcx, rdi; P
0x14002bd2c  call    cs:__imp_ExFreePoolWithTag
0x14002bd33  nop     dword ptr [rax+rax+00h]
0x14002bd38  test    rsi, rsi
0x14002bd3b  jz      short loc_14002BD51
0x14002bd3d  mov     edx, 6D746943h; Tag
0x14002bd42  mov     rcx, rsi; P
0x14002bd45  call    cs:__imp_ExFreePoolWithTag
0x14002bd4c  nop     dword ptr [rax+rax+00h]
0x14002bd51  mov     rsi, [rsp+58h+arg_10]
0x14002bd56  mov     eax, ebx
0x14002bd58  mov     rbx, [rsp+58h+arg_0]
0x14002bd5d  add     rsp, 30h
0x14002bd61  pop     r15
0x14002bd63  pop     r14
0x14002bd65  pop     r13
0x14002bd67  pop     r12
0x14002bd69  pop     rdi
0x14002bd6a  retn
```
