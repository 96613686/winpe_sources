# FileProvReadCompressedCompletionWorker

- ea: `0x1400016f0`
- end: `0x140001882`
- name: `FileProvReadCompressedCompletionWorker`
- size: `402`
- prototype: `void __fastcall(PFLT_GENERIC_WORKITEM FltWorkItem, PVOID FltObject, _DWORD *Context)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x140001570`

## callees

- `0x1400016f0`
- `0x1400022a0`
- `0x14000d3b8`
- `0x14000fb60`
- `0x1400105e8`
- `0x140011640`

## import_xrefs

- `FLTMGR!FltFreeGenericWorkItem` at `0x140001768`
- `FLTMGR!FltFreeGenericWorkItem` at `0x140001768`

## pseudocode

```c
void __fastcall FileProvReadCompressedCompletionWorker(
        PFLT_GENERIC_WORKITEM FltWorkItem,
        PVOID FltObject,
        _DWORD *Context)
{
  __int64 v3; // rbx
  unsigned int v5; // ebp
  int v7; // ebx
  void (__fastcall *v8)(_DWORD *, PVOID); // rax
  const char *v9; // r9

  v3 = *(_QWORD *)Context;
  v5 = Context[28];
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_3b099794e4b93327e327da255c047df6_Traceguids);
  if ( v3 )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      v9 = "SYNC";
      if ( !*((_BYTE *)Context + 137) )
        v9 = "ASYNC";
      WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_3b099794e4b93327e327da255c047df6_Traceguids, v9);
    }
    v7 = *(_DWORD *)(v3 + 24);
  }
  else
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 40, WPP_3b099794e4b93327e327da255c047df6_Traceguids);
    v7 = Context[2];
  }
  if ( v7 < 0 )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        41,
        WPP_3b099794e4b93327e327da255c047df6_Traceguids,
        (unsigned int)v7);
  }
  else
  {
    v8 = (void (__fastcall *)(_DWORD *, PVOID))*((_QWORD *)Context + 22);
    if ( v8 )
    {
      Context[2] = v7;
      v8(Context, FltObject);
      goto LABEL_9;
    }
  }
  FileProvCompleteRead((char *)Context, v5, v7);
LABEL_9:
  if ( FltWorkItem )
    FltFreeGenericWorkItem(FltWorkItem);
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_3b099794e4b93327e327da255c047df6_Traceguids, (unsigned int)v7);
}

```

## disassembly

```asm
0x1400016f0  push    rbx
0x1400016f2  push    rbp
0x1400016f3  push    rsi
0x1400016f4  push    rdi
0x1400016f5  sub     rsp, 28h
0x1400016f9  mov     rbx, [r8]
0x1400016fc  mov     rdi, r8
0x1400016ff  mov     ebp, [r8+70h]
0x140001703  mov     rsi, rcx
0x140001706  mov     rcx, cs:WPP_GLOBAL_Control
0x14000170d  mov     eax, [rcx+2Ch]
0x140001710  test    al, 20h
0x140001712  jnz     short loc_140001790
0x140001714  test    rbx, rbx
0x140001717  jz      loc_1400017F1
0x14000171d  mov     rcx, cs:WPP_GLOBAL_Control
0x140001724  mov     eax, [rcx+2Ch]
0x140001727  test    al, 20h
0x140001729  jnz     loc_1400017B4
0x14000172f  mov     ebx, [rbx+18h]
0x140001732  test    ebx, ebx
0x140001734  js      loc_140001822
0x14000173a  mov     rax, [rdi+0B0h]
0x140001741  test    rax, rax
0x140001744  jz      short loc_140001753
0x140001746  mov     rcx, rdi
0x140001749  mov     [rdi+8], ebx
0x14000174c  call    _guard_dispatch_icall
0x140001751  jmp     short loc_140001760
0x140001753  mov     r8d, ebx
0x140001756  mov     edx, ebp
0x140001758  mov     rcx, rdi; Entry
0x14000175b  call    FileProvCompleteRead
0x140001760  test    rsi, rsi
0x140001763  jz      short loc_140001774
0x140001765  mov     rcx, rsi; FltWorkItem
0x140001768  call    cs:__imp_FltFreeGenericWorkItem
0x14000176f  nop     dword ptr [rax+rax+00h]
0x140001774  mov     rcx, cs:WPP_GLOBAL_Control
0x14000177b  mov     eax, [rcx+2Ch]
0x14000177e  test    al, 20h
0x140001780  jnz     loc_14000185B
0x140001786  add     rsp, 28h
0x14000178a  pop     rdi
0x14000178b  pop     rsi
0x14000178c  pop     rbp
0x14000178d  pop     rbx
0x14000178e  retn
0x140001790  cmp     byte ptr [rcx+29h], 4
0x140001794  jb      loc_140001714
0x14000179a  mov     rcx, [rcx+18h]
0x14000179e  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x1400017a5  mov     edx, 26h ; '&'
0x1400017aa  call    WPP_SF_
0x1400017af  jmp     loc_140001714
0x1400017b4  cmp     byte ptr [rcx+29h], 5
0x1400017b8  jb      loc_14000172F
0x1400017be  cmp     byte ptr [rdi+89h], 0
0x1400017c5  lea     rdx, aAsync; "ASYNC"
0x1400017cc  mov     rcx, [rcx+18h]
0x1400017d0  lea     r9, aSync; "SYNC"
0x1400017d7  cmovz   r9, rdx
0x1400017db  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x1400017e2  mov     edx, 27h ; '''
0x1400017e7  call    WPP_SF_s
0x1400017ec  jmp     loc_14000172F
0x1400017f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400017f8  mov     eax, [rcx+2Ch]
0x1400017fb  test    al, 20h
0x1400017fd  jz      short loc_14000181A
0x1400017ff  cmp     byte ptr [rcx+29h], 5
0x140001803  jb      short loc_14000181A
0x140001805  mov     rcx, [rcx+18h]
0x140001809  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x140001810  mov     edx, 28h ; '('
0x140001815  call    WPP_SF_
0x14000181a  mov     ebx, [rdi+8]
0x14000181d  jmp     loc_140001732
0x140001822  mov     rcx, cs:WPP_GLOBAL_Control
0x140001829  mov     eax, [rcx+2Ch]
0x14000182c  test    al, 20h
0x14000182e  jz      loc_140001753
0x140001834  cmp     byte ptr [rcx+29h], 2
0x140001838  jb      loc_140001753
0x14000183e  mov     rcx, [rcx+18h]
0x140001842  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x140001849  mov     edx, 29h ; ')'
0x14000184e  mov     r9d, ebx
0x140001851  call    WPP_SF_d
0x140001856  jmp     loc_140001753
0x14000185b  cmp     byte ptr [rcx+29h], 4
0x14000185f  jb      loc_140001786
0x140001865  mov     rcx, [rcx+18h]
0x140001869  lea     r8, WPP_3b099794e4b93327e327da255c047df6_Traceguids
0x140001870  mov     edx, 2Ah ; '*'
0x140001875  mov     r9d, ebx
0x140001878  call    WPP_SF_d
0x14000187d  jmp     loc_140001786
```
