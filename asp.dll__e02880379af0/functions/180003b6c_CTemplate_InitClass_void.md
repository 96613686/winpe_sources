# CTemplate::InitClass(void)

- ea: `0x180003b6c`
- end: `0x180003c32`
- name: `?InitClass@CTemplate@@SAJXZ`
- size: `198`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180004a64`

## callees

- `0x180003b6c`
- `0x180003c38`
- `0x18001778c`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180003beb`
- `KERNEL32!HeapAlloc` at `0x180003beb`
- `KERNEL32!HeapSetInformation` at `0x180003ba3`
- `KERNEL32!HeapSetInformation` at `0x180003bd8`
- `KERNEL32!HeapSetInformation` at `0x180003ba3`
- `KERNEL32!HeapSetInformation` at `0x180003bd8`
- `KERNEL32!HeapCreate` at `0x180003b7b`
- `KERNEL32!HeapCreate` at `0x180003bb0`
- `KERNEL32!HeapCreate` at `0x180003b7b`
- `KERNEL32!HeapCreate` at `0x180003bb0`

## pseudocode

```c
__int64 CTemplate::InitClass(void)
{
  HANDLE v0; // rax
  HANDLE v1; // rax
  CTemplate::CTokenList *v2; // rax
  CTemplate::CTokenList *v3; // rcx
  int HeapInformation; // [rsp+30h] [rbp+8h] BYREF
  int v6; // [rsp+38h] [rbp+10h] BYREF

  v0 = HeapCreate(0, 0, 0);
  CTemplate::sm_hSmallHeap = v0;
  if ( !v0 )
    return 2147942414LL;
  HeapInformation = 2;
  HeapSetInformation(v0, HeapCompatibilityInformation, &HeapInformation, 4u);
  v1 = HeapCreate(0, 0, 0);
  CTemplate::sm_hLargeHeap = v1;
  if ( !v1 )
    return 2147942414LL;
  v6 = 2;
  HeapSetInformation(v1, HeapCompatibilityInformation, &v6, 4u);
  v2 = (CTemplate::CTokenList *)HeapAlloc(g_hDenaliHeap, 0, 0x20u);
  if ( v2 )
    v2 = (CTemplate::CTokenList *)CTemplate::CTokenList::CTokenList(v2);
  CTemplate::gm_pTokenList = v2;
  if ( !v2 )
    return 2147942414LL;
  CTemplate::CTokenList::Init(v3);
  return 0;
}

```

## disassembly

```asm
0x180003b6c  push    rbx
0x180003b6e  sub     rsp, 20h
0x180003b72  xor     ebx, ebx
0x180003b74  xor     r8d, r8d; dwMaximumSize
0x180003b77  xor     edx, edx; dwInitialSize
0x180003b79  xor     ecx, ecx; flOptions
0x180003b7b  call    cs:__imp_HeapCreate
0x180003b81  mov     cs:?sm_hSmallHeap@CTemplate@@2PEAXEA, rax; void * CTemplate::sm_hSmallHeap
0x180003b88  test    rax, rax
0x180003b8b  jz      short loc_180003C0C
0x180003b8d  mov     [rsp+28h+HeapInformation], 2
0x180003b95  lea     r9d, [rbx+4]; HeapInformationLength
0x180003b99  lea     r8, [rsp+28h+HeapInformation]; HeapInformation
0x180003b9e  xor     edx, edx; HeapInformationClass
0x180003ba0  mov     rcx, rax; HeapHandle
0x180003ba3  call    cs:__imp_HeapSetInformation
0x180003ba9  xor     r8d, r8d; dwMaximumSize
0x180003bac  xor     edx, edx; dwInitialSize
0x180003bae  xor     ecx, ecx; flOptions
0x180003bb0  call    cs:__imp_HeapCreate
0x180003bb6  mov     cs:?sm_hLargeHeap@CTemplate@@2PEAXEA, rax; void * CTemplate::sm_hLargeHeap
0x180003bbd  test    rax, rax
0x180003bc0  jz      short loc_180003C13
0x180003bc2  mov     [rsp+28h+arg_8], 2
0x180003bca  lea     r9d, [rbx+4]; HeapInformationLength
0x180003bce  lea     r8, [rsp+28h+arg_8]; HeapInformation
0x180003bd3  xor     edx, edx; HeapInformationClass
0x180003bd5  mov     rcx, rax; HeapHandle
0x180003bd8  call    cs:__imp_HeapSetInformation
0x180003bde  xor     edx, edx; dwFlags
0x180003be0  lea     r8d, [rbx+20h]; dwBytes
0x180003be4  mov     rcx, cs:?g_hDenaliHeap@@3PEAXEA; hHeap
0x180003beb  call    cs:__imp_HeapAlloc
0x180003bf1  test    rax, rax
0x180003bf4  jz      short loc_180003BFE
0x180003bf6  mov     rcx, rax; this
0x180003bf9  call    ??0CTokenList@CTemplate@@QEAA@XZ; CTemplate::CTokenList::CTokenList(void)
0x180003bfe  mov     cs:?gm_pTokenList@CTemplate@@2PEAVCTokenList@1@EA, rax; CTemplate::CTokenList * CTemplate::gm_pTokenList
0x180003c05  test    rax, rax
0x180003c08  jz      short loc_180003C1A
0x180003c0a  jmp     short loc_180003C21
0x180003c0c  mov     eax, 8007000Eh
0x180003c11  jmp     short loc_180003C2C
0x180003c13  mov     eax, 8007000Eh
0x180003c18  jmp     short loc_180003C2C
0x180003c1a  mov     eax, 8007000Eh
0x180003c1f  jmp     short loc_180003C2C
0x180003c21  call    ?Init@CTokenList@CTemplate@@QEAAXXZ; CTemplate::CTokenList::Init(void)
0x180003c26  jmp     short loc_180003C2A
0x180003c28  mov     ebx, eax
0x180003c2a  mov     eax, ebx
0x180003c2c  add     rsp, 20h
0x180003c30  pop     rbx
0x180003c31  retn
```
