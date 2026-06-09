# VfsPrepareMergeDirectory

- ea: `0x140006710`
- end: `0x140006990`
- name: `VfsPrepareMergeDirectory`
- size: `640`
- prototype: `__int64 __usercall@<rax>(PFLT_CALLBACK_DATA CallbackData@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140006998`

## callees

- `0x140006710`
- `0x1400074f4`
- `0x140007a14`
- `0x140007acc`
- `0x140012acc`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140006855`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140006855`

## string_xrefs

- `0x140006800`: `VfsValidateDirQueryParameters() - Invalid directory query inforamtion class: %d`
- `0x1400067e5`: `VfsValidateDirQueryParameters() - Directory query index is not supported`
- `0x1400068ae`: `VfsPrepareMergeDirectory() - Failed to create directory query context`
- `0x1400068e6`: `VfsPrepareMergeDirectory() - Multi async directory queries on the same directory are not supported`

## pseudocode

```c
__int64 __fastcall VfsPrepareMergeDirectory(
        PFLT_CALLBACK_DATA CallbackData,
        __int64 a2,
        volatile signed __int64 *a3,
        _QWORD *a4,
        ULONG *a5,
        _BYTE *a6)
{
  volatile signed __int64 v7; // rdi
  volatile signed __int64 *v8; // r12
  char v9; // si
  int DirQueryContext; // ebx
  PFLT_IO_PARAMETER_BLOCK Iopb; // rcx
  unsigned __int64 LowPart; // r9
  __int64 v13; // rdx
  PFLT_IO_PARAMETER_BLOCK v14; // rax
  LARGE_INTEGER AllocationSize; // rcx
  PVOID EaBuffer; // rax
  ULONG Length; // r15d
  PVOID Entry; // [rsp+38h] [rbp-40h]
  PVOID v20; // [rsp+40h] [rbp-38h]

  v7 = 0;
  Entry = 0;
  v8 = 0;
  v20 = 0;
  v9 = 0;
  *a5 = 0;
  *a6 = 0;
  if ( *(_WORD *)a2 == 5768 )
  {
    v8 = (volatile signed __int64 *)(a2 + 144);
LABEL_8:
    v7 = *v8;
    Entry = (PVOID)*v8;
    DirQueryContext = 0;
    goto LABEL_9;
  }
  if ( (*(_DWORD *)(*(_QWORD *)(a2 + 24) + 272LL) & 2) == 0 )
  {
    DirQueryContext = -1073741811;
    goto LABEL_9;
  }
  if ( (*(_DWORD *)(a2 + 4) & 4) != 0 || (DirQueryContext = *(_DWORD *)(a2 + 32), DirQueryContext >= 0) )
  {
    v8 = (volatile signed __int64 *)(a2 + 120);
    goto LABEL_8;
  }
LABEL_9:
  if ( DirQueryContext < 0 )
    goto LABEL_38;
  Iopb = CallbackData->Iopb;
  LowPart = (int)Iopb->Parameters.Read.ByteOffset.LowPart;
  if ( (unsigned int)LowPart <= 0x26 && (v13 = 0x600000100ELL, _bittest64(&v13, LowPart)) )
  {
    v9 = 1;
    if ( (Iopb->OperationFlags & 4) != 0 )
    {
      LogWrite(1, 0, L"VfsValidateDirQueryParameters() - Directory query index is not supported");
      DirQueryContext = -1073741637;
    }
    else
    {
      DirQueryContext = 0;
    }
  }
  else
  {
    v9 = 1;
    LogWrite(1, 0, L"VfsValidateDirQueryParameters() - Invalid directory query inforamtion class: %d");
    DirQueryContext = -1073741821;
  }
  if ( DirQueryContext < 0 )
    goto LABEL_37;
  v14 = CallbackData->Iopb;
  AllocationSize = v14->Parameters.Create.AllocationSize;
  if ( !AllocationSize.QuadPart )
  {
    EaBuffer = v14->Parameters.Create.EaBuffer;
LABEL_24:
    v20 = EaBuffer;
    Length = CallbackData->Iopb->Parameters.Read.Length;
    DirQueryContext = 0;
    goto LABEL_25;
  }
  if ( (*(_BYTE *)(AllocationSize.QuadPart + 10) & 5) != 0 )
    EaBuffer = *(PVOID *)(AllocationSize.QuadPart + 24);
  else
    EaBuffer = MmMapLockedPagesSpecifyCache((PMDL)AllocationSize.QuadPart, 0, MmCached, 0, 0, 0x10u);
  if ( EaBuffer )
    goto LABEL_24;
  Length = 0;
  DirQueryContext = -1073741670;
LABEL_25:
  if ( DirQueryContext < 0 )
  {
LABEL_37:
    v9 = 0;
    goto LABEL_38;
  }
  if ( !v7 )
  {
    DirQueryContext = VfsCreateDirQueryContext(CallbackData);
    if ( DirQueryContext < 0 )
    {
      LogWrite(1, 0, L"VfsPrepareMergeDirectory() - Failed to create directory query context");
      v7 = (volatile signed __int64)Entry;
      goto LABEL_37;
    }
    v7 = (volatile signed __int64)Entry;
    if ( _InterlockedCompareExchange64(v8, (signed __int64)Entry, 0) )
    {
      VfsDeleteDirQueryContext(Entry);
      v7 = 0;
LABEL_31:
      LogWrite(
        1,
        0,
        L"VfsPrepareMergeDirectory() - Multi async directory queries on the same directory are not supported");
      DirQueryContext = -1073741670;
      goto LABEL_37;
    }
  }
  if ( *(_DWORD *)(v7 + 28) <= 1u )
  {
    *a6 = 1;
    DirQueryContext = 0;
    goto LABEL_37;
  }
  if ( _InterlockedCompareExchange((volatile signed __int32 *)(v7 + 4), 1, 0) )
    goto LABEL_31;
  DirQueryContext = VfsUpdateDirQueryContext(CallbackData, v7);
  if ( DirQueryContext >= 0 )
  {
    *a3 = v7;
    *a4 = v20;
    *a5 = Length;
  }
LABEL_38:
  if ( DirQueryContext < 0 && v9 )
    _InterlockedExchange((volatile __int32 *)(v7 + 4), 0);
  return (unsigned int)DirQueryContext;
}

```

## disassembly

```asm
0x140006710  mov     rax, rsp
0x140006713  mov     [rax+8], rbx
0x140006717  mov     [rax+10h], rsi
0x14000671b  mov     [rax+20h], r9
0x14000671f  mov     [rax+18h], r8
0x140006723  push    rdi
0x140006724  push    r12
0x140006726  push    r13
0x140006728  push    r14
0x14000672a  push    r15
0x14000672c  sub     rsp, 50h
0x140006730  mov     r14, rdx
0x140006733  mov     r13, rcx
0x140006736  mov     dword ptr [rax-44h], 0
0x14000673d  xor     edi, edi
0x14000673f  mov     [rax-40h], rdi
0x140006743  xor     r12d, r12d
0x140006746  mov     [rax-38h], rdi
0x14000674a  xor     sil, sil
0x14000674d  mov     [rax-48h], sil
0x140006751  mov     rax, [rsp+78h+arg_20]
0x140006759  mov     [rax], edi
0x14000675b  mov     rax, [rsp+78h+arg_28]
0x140006763  mov     [rax], sil
0x140006766  mov     eax, 1688h
0x14000676b  cmp     [rdx], ax
0x14000676e  jnz     short loc_140006779
0x140006770  lea     r12, [rdx+90h]
0x140006777  jmp     short loc_1400067A1
0x140006779  mov     rax, [rdx+18h]
0x14000677d  mov     ecx, [rax+110h]
0x140006783  test    cl, 2
0x140006786  jnz     short loc_14000678F
0x140006788  mov     ebx, 0C000000Dh
0x14000678d  jmp     short loc_1400067AC
0x14000678f  mov     eax, [rdx+4]
0x140006792  test    al, 4
0x140006794  jnz     short loc_14000679D
0x140006796  mov     ebx, [rdx+20h]
0x140006799  test    ebx, ebx
0x14000679b  js      short loc_1400067AC
0x14000679d  lea     r12, [rdx+78h]
0x1400067a1  mov     rdi, [r12]
0x1400067a5  mov     [rsp+78h+Entry], rdi
0x1400067aa  xor     ebx, ebx
0x1400067ac  mov     [rsp+78h+var_44], ebx
0x1400067b0  test    ebx, ebx
0x1400067b2  js      loc_140006965
0x1400067b8  mov     rcx, [r13+10h]
0x1400067bc  movsxd  r9, dword ptr [rcx+28h]
0x1400067c0  cmp     r9d, 26h ; '&'
0x1400067c4  ja      short loc_140006800
0x1400067c6  mov     rax, r9
0x1400067c9  mov     rdx, 600000100Eh
0x1400067d3  bt      rdx, rax
0x1400067d7  jnb     short loc_140006800
0x1400067d9  mov     al, [rcx+6]
0x1400067dc  mov     esi, 1
0x1400067e1  test    al, 4
0x1400067e3  jz      short loc_1400067FC
0x1400067e5  lea     r8, aVfsvalidatedir_0; "VfsValidateDirQueryParameters() - Direc"...
0x1400067ec  xor     edx, edx
0x1400067ee  mov     ecx, esi
0x1400067f0  call    LogWrite
0x1400067f5  mov     ebx, 0C00000BBh
0x1400067fa  jmp     short loc_140006818
0x1400067fc  xor     ebx, ebx
0x1400067fe  jmp     short loc_140006818
0x140006800  lea     r8, aVfsvalidatedir; "VfsValidateDirQueryParameters() - Inval"...
0x140006807  xor     edx, edx
0x140006809  lea     esi, [rdx+1]
0x14000680c  mov     ecx, esi
0x14000680e  call    LogWrite
0x140006813  mov     ebx, 0C0000003h
0x140006818  mov     [rsp+78h+var_44], ebx
0x14000681c  test    ebx, ebx
0x14000681e  js      loc_140006960
0x140006824  mov     rax, [r13+10h]
0x140006828  mov     rcx, [rax+40h]; MemoryDescriptorList
0x14000682c  test    rcx, rcx
0x14000682f  jz      short loc_140006870
0x140006831  test    byte ptr [rcx+0Ah], 5
0x140006835  jz      short loc_14000683D
0x140006837  mov     rax, [rcx+18h]
0x14000683b  jmp     short loc_140006861
0x14000683d  mov     [rsp+78h+Priority], 10h; Priority
0x140006845  mov     [rsp+78h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14000684d  xor     r9d, r9d; RequestedAddress
0x140006850  mov     r8d, esi; CacheType
0x140006853  xor     edx, edx; AccessMode
0x140006855  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14000685c  nop     dword ptr [rax+rax+00h]
0x140006861  test    rax, rax
0x140006864  jnz     short loc_140006874
0x140006866  xor     r15d, r15d
0x140006869  mov     ebx, 0C000009Ah
0x14000686e  jmp     short loc_140006883
0x140006870  mov     rax, [rax+38h]
0x140006874  mov     [rsp+78h+var_38], rax
0x140006879  mov     rax, [r13+10h]
0x14000687d  mov     r15d, [rax+18h]
0x140006881  xor     ebx, ebx
0x140006883  mov     [rsp+78h+var_44], ebx
0x140006887  test    ebx, ebx
0x140006889  js      loc_140006960
0x14000688f  test    rdi, rdi
0x140006892  jnz     short loc_140006901
0x140006894  lea     r8, [rsp+78h+Entry]
0x140006899  mov     rdx, r14
0x14000689c  mov     rcx, r13; CallbackData
0x14000689f  call    VfsCreateDirQueryContext
0x1400068a4  mov     ebx, eax
0x1400068a6  mov     [rsp+78h+var_44], eax
0x1400068aa  test    eax, eax
0x1400068ac  jns     short loc_1400068C8
0x1400068ae  lea     r8, aVfspreparemerg_0; "VfsPrepareMergeDirectory() - Failed to "...
0x1400068b5  xor     edx, edx
0x1400068b7  mov     ecx, esi
0x1400068b9  call    LogWrite
0x1400068be  mov     rdi, [rsp+78h+Entry]
0x1400068c3  jmp     loc_140006960
0x1400068c8  mov     rdi, [rsp+78h+Entry]
0x1400068cd  xor     eax, eax
0x1400068cf  lock cmpxchg [r12], rdi
0x1400068d5  jz      short loc_140006901
0x1400068d7  mov     rcx, rdi; Entry
0x1400068da  call    VfsDeleteDirQueryContext
0x1400068df  xor     edi, edi
0x1400068e1  mov     [rsp+78h+Entry], rdi
0x1400068e6  lea     r8, aVfspreparemerg; "VfsPrepareMergeDirectory() - Multi asyn"...
0x1400068ed  xor     edx, edx
0x1400068ef  mov     ecx, esi
0x1400068f1  call    LogWrite
0x1400068f6  mov     ebx, 0C000009Ah
0x1400068fb  mov     [rsp+78h+var_44], ebx
0x1400068ff  jmp     short loc_140006960
0x140006901  cmp     [rdi+1Ch], esi
0x140006904  ja      short loc_140006915
0x140006906  mov     rax, [rsp+78h+arg_28]
0x14000690e  mov     [rax], sil
0x140006911  xor     ebx, ebx
0x140006913  jmp     short loc_1400068FB
0x140006915  xor     eax, eax
0x140006917  lock cmpxchg [rdi+4], esi
0x14000691c  jnz     short loc_1400068E6
0x14000691e  mov     [rsp+78h+var_48], sil
0x140006923  mov     rdx, rdi
0x140006926  mov     rcx, r13
0x140006929  call    VfsUpdateDirQueryContext
0x14000692e  mov     ebx, eax
0x140006930  mov     [rsp+78h+var_44], eax
0x140006934  test    eax, eax
0x140006936  js      short loc_140006965
0x140006938  mov     rax, [rsp+78h+arg_10]
0x140006940  mov     [rax], rdi
0x140006943  mov     rax, [rsp+78h+var_38]
0x140006948  mov     rcx, [rsp+78h+arg_18]
0x140006950  mov     [rcx], rax
0x140006953  mov     rax, [rsp+78h+arg_20]
0x14000695b  mov     [rax], r15d
0x14000695e  jmp     short loc_140006965
0x140006960  mov     sil, [rsp+78h+var_48]
0x140006965  test    ebx, ebx
0x140006967  jns     short loc_140006973
0x140006969  test    sil, sil
0x14000696c  jz      short loc_140006973
0x14000696e  xor     eax, eax
0x140006970  xchg    eax, [rdi+4]
0x140006973  mov     eax, ebx
0x140006975  lea     r11, [rsp+78h+var_28]
0x14000697a  mov     rbx, [r11+30h]
0x14000697e  mov     rsi, [r11+38h]
0x140006982  mov     rsp, r11
0x140006985  pop     r15
0x140006987  pop     r14
0x140006989  pop     r13
0x14000698b  pop     r12
0x14000698d  pop     rdi
0x14000698e  retn
0x140014af7  push    rbp
0x140014af9  sub     rsp, 30h
0x140014afd  mov     rbp, rdx
0x140014b00  cmp     dword ptr [rbp+34h], 0
0x140014b04  jge     short loc_140014B15
0x140014b06  cmp     byte ptr [rbp+30h], 0
0x140014b0a  jz      short loc_140014B15
0x140014b0c  mov     rcx, [rbp+38h]
0x140014b10  xor     eax, eax
0x140014b12  xchg    eax, [rcx+4]
0x140014b15  add     rsp, 30h
0x140014b19  pop     rbp
0x140014b1a  retn
```
