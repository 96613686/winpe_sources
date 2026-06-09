# FMyProviderCacheInit

- ea: `0x18000beb0`
- end: `0x18000bf26`
- name: `FMyProviderCacheInit`
- size: `118`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000a0c0`
- `0x18000a1b0`

## callees

- `0x1800015f4`
- `0x180001620`
- `0x18000beb0`
- `0x18000c3b0`
- `0x18000c40c`

## pseudocode

```c
void FMyProviderCacheInit()
{
  _DWORD *v0; // rax
  CLinkedList *v1; // rbx

  v0 = operator new(0x48u);
  if ( v0 )
  {
    v0[2] = 0;
    *((_QWORD *)v0 + 7) = BCryptProvIsMatch;
    *((_QWORD *)v0 + 8) = BCryptProvFreeElt;
    *(_QWORD *)v0 = 0;
    g_pBCProvList = (CLinkedList *)v0;
    if ( (unsigned int)CLinkedList::Initialize((CLinkedList *)BCryptProvFreeElt) )
      return;
    v1 = g_pBCProvList;
    if ( g_pBCProvList )
    {
      CLinkedList::~CLinkedList((void (**)(void))g_pBCProvList);
      operator delete(v1);
    }
  }
  g_pBCProvList = 0;
}

```

## disassembly

```asm
0x18000beb0  push    rbx
0x18000beb2  sub     rsp, 20h
0x18000beb6  mov     ecx, 48h ; 'H'; unsigned __int64
0x18000bebb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000bec0  test    rax, rax
0x18000bec3  jz      short loc_18000BF15
0x18000bec5  lea     rcx, ?BCryptProvIsMatch@@YAHPEAU_ELT@@0@Z; BCryptProvIsMatch(_ELT *,_ELT *)
0x18000becc  mov     dword ptr [rax+8], 0
0x18000bed3  mov     [rax+38h], rcx
0x18000bed7  lea     rcx, ?BCryptProvFreeElt@@YAXPEAU_ELT@@@Z; this
0x18000bede  mov     [rax+40h], rcx
0x18000bee2  mov     qword ptr [rax], 0
0x18000bee9  mov     cs:?g_pBCProvList@@3PEAVCBCryptProvList@@EA, rax; CBCryptProvList * g_pBCProvList
0x18000bef0  call    ?Initialize@CLinkedList@@QEAAHXZ; CLinkedList::Initialize(void)
0x18000bef5  test    eax, eax
0x18000bef7  jnz     short loc_18000BF20
0x18000bef9  mov     rbx, cs:?g_pBCProvList@@3PEAVCBCryptProvList@@EA; CBCryptProvList * g_pBCProvList
0x18000bf00  test    rbx, rbx
0x18000bf03  jz      short loc_18000BF15
0x18000bf05  mov     rcx, rbx; this
0x18000bf08  call    ??1CLinkedList@@QEAA@XZ; CLinkedList::~CLinkedList(void)
0x18000bf0d  mov     rcx, rbx; void *
0x18000bf10  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000bf15  mov     cs:?g_pBCProvList@@3PEAVCBCryptProvList@@EA, 0; CBCryptProvList * g_pBCProvList
0x18000bf20  add     rsp, 20h
0x18000bf24  pop     rbx
0x18000bf25  retn
```
