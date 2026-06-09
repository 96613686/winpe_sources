# Smb2CreateContinueOnOplockAck

- ea: `0x14006ad90`
- end: `0x14006aed2`
- name: `Smb2CreateContinueOnOplockAck`
- size: `322`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x140007400`
- `0x140007900`
- `0x140008190`
- `0x14000f4d0`
- `0x14001ed38`
- `0x14001ffc4`
- `0x14006ad90`
- `0x14006ea80`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x14006ae02`
- `ntoskrnl!IoFreeMdl` at `0x14006ae02`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006adb7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006adb7`
- `ntoskrnl!MmUnlockPages` at `0x14006adf3`
- `ntoskrnl!MmUnlockPages` at `0x14006adf3`

## string_xrefs

- `0x14006aead`: `onecore\base\fs\remotefs\smb\srv\srv.v2\smb2\create.c`

## pseudocode

```c
__int64 __fastcall Smb2CreateContinueOnOplockAck(_QWORD *a1)
{
  __int64 v1; // rbp
  __int64 v3; // rdi
  void *v4; // rcx
  struct _MDL *v5; // rsi
  struct _MDL *v6; // r14
  CSHORT MdlFlags; // ax
  int BuildResponse; // esi
  __int64 v9; // r9
  __int64 v10; // rdx

  v1 = a1[15];
  v3 = a1[70];
  v4 = *(void **)(v1 + 160);
  if ( v4 )
  {
    ExFreePoolWithTag(v4, 0);
    *(_QWORD *)(v1 + 160) = 0;
  }
  v5 = *(struct _MDL **)(v1 + 8);
  if ( v5 && (v5->MdlFlags & 4) == 0 )
  {
    do
    {
      v6 = v5;
      v5 = v5->Next;
      MdlFlags = v6->MdlFlags;
      if ( (MdlFlags & 2) != 0 || (MdlFlags & 0x20) != 0 )
        MmUnlockPages(v6);
      IoFreeMdl(v6);
    }
    while ( v5 );
    *(_QWORD *)(v1 + 8) = 0;
  }
  if ( *(int *)(a1[15] + 48LL) < 0 )
  {
    Smb2CloseFile(*(_QWORD *)(v3 + 72));
    v9 = 3217;
    v10 = *(unsigned int *)(a1[15] + 48LL);
    goto LABEL_21;
  }
  if ( *(_BYTE *)(v3 + 378) )
  {
    BuildResponse = Smb2RequestOplockForResumedCreate(a1);
    if ( BuildResponse < 0 )
    {
      Smb2CloseFile(*(_QWORD *)(v3 + 72));
      v9 = 3187;
LABEL_14:
      v10 = (unsigned int)BuildResponse;
LABEL_21:
      Smb2SetError(a1, v10, "onecore\\base\\fs\\remotefs\\smb\\srv\\srv.v2\\smb2\\create.c", v9);
      return Srv2CompleteWorkItem(a1, 0);
    }
    if ( *(_BYTE *)(v3 + 381) )
    {
      Smb2RkfNotifyComplete(a1[8], *(_QWORD *)(*(_QWORD *)(v3 + 80) + 96LL));
      *(_BYTE *)(v3 + 381) = 0;
    }
  }
  BuildResponse = Smb2CreateBuildResponse(a1);
  if ( BuildResponse < 0 )
  {
    Smb2CloseFile(*(_QWORD *)(v3 + 72));
    v9 = 3207;
    goto LABEL_14;
  }
  Smb2SetSuccess(a1, 0);
  return Srv2CompleteWorkItem(a1, 0);
}

```

## disassembly

```asm
0x14006ad90  push    rbx
0x14006ad92  push    rbp
0x14006ad93  push    rsi
0x14006ad94  push    rdi
0x14006ad95  push    r14
0x14006ad97  sub     rsp, 20h
0x14006ad9b  mov     rbp, [rcx+78h]
0x14006ad9f  mov     rbx, rcx
0x14006ada2  mov     rdi, [rcx+230h]
0x14006ada9  mov     rcx, [rbp+0A0h]; P
0x14006adb0  test    rcx, rcx
0x14006adb3  jz      short loc_14006ADCE
0x14006adb5  xor     edx, edx; Tag
0x14006adb7  call    cs:__imp_ExFreePoolWithTag
0x14006adbe  nop     dword ptr [rax+rax+00h]
0x14006adc3  mov     qword ptr [rbp+0A0h], 0
0x14006adce  mov     rsi, [rbp+8]
0x14006add2  test    rsi, rsi
0x14006add5  jz      short loc_14006AE17
0x14006add7  test    byte ptr [rsi+0Ah], 4
0x14006addb  jnz     short loc_14006AE17
0x14006addd  mov     r14, rsi
0x14006ade0  mov     rsi, [rsi]
0x14006ade3  movzx   eax, word ptr [r14+0Ah]
0x14006ade8  test    al, 2
0x14006adea  jnz     short loc_14006ADF0
0x14006adec  test    al, 20h
0x14006adee  jz      short loc_14006ADFF
0x14006adf0  mov     rcx, r14; MemoryDescriptorList
0x14006adf3  call    cs:__imp_MmUnlockPages
0x14006adfa  nop     dword ptr [rax+rax+00h]
0x14006adff  mov     rcx, r14; Mdl
0x14006ae02  call    cs:__imp_IoFreeMdl
0x14006ae09  nop     dword ptr [rax+rax+00h]
0x14006ae0e  test    rsi, rsi
0x14006ae11  jnz     short loc_14006ADDD
0x14006ae13  mov     [rbp+8], rsi
0x14006ae17  mov     rax, [rbx+78h]
0x14006ae1b  cmp     dword ptr [rax+30h], 0
0x14006ae1f  jl      short loc_14006AE97
0x14006ae21  cmp     byte ptr [rdi+17Ah], 0
0x14006ae28  jz      short loc_14006AE6C
0x14006ae2a  mov     rcx, rbx
0x14006ae2d  call    Smb2RequestOplockForResumedCreate
0x14006ae32  mov     esi, eax
0x14006ae34  test    eax, eax
0x14006ae36  jns     short loc_14006AE4B
0x14006ae38  mov     rcx, [rdi+48h]
0x14006ae3c  call    Smb2CloseFile
0x14006ae41  mov     r9d, 0C73h
0x14006ae47  mov     edx, esi
0x14006ae49  jmp     short loc_14006AEAD
0x14006ae4b  cmp     byte ptr [rdi+17Dh], 0
0x14006ae52  jz      short loc_14006AE6C
0x14006ae54  mov     rdx, [rdi+50h]
0x14006ae58  mov     rcx, [rbx+40h]
0x14006ae5c  mov     rdx, [rdx+60h]
0x14006ae60  call    Smb2RkfNotifyComplete
0x14006ae65  mov     byte ptr [rdi+17Dh], 0
0x14006ae6c  mov     rcx, rbx
0x14006ae6f  call    Smb2CreateBuildResponse
0x14006ae74  mov     esi, eax
0x14006ae76  test    eax, eax
0x14006ae78  jns     short loc_14006AE8B
0x14006ae7a  mov     rcx, [rdi+48h]
0x14006ae7e  call    Smb2CloseFile
0x14006ae83  mov     r9d, 0C87h
0x14006ae89  jmp     short loc_14006AE47
0x14006ae8b  xor     edx, edx
0x14006ae8d  mov     rcx, rbx
0x14006ae90  call    Smb2SetSuccess
0x14006ae95  jmp     short loc_14006AEBC
0x14006ae97  mov     rcx, [rdi+48h]
0x14006ae9b  call    Smb2CloseFile
0x14006aea0  mov     rdx, [rbx+78h]
0x14006aea4  mov     r9d, 0C91h
0x14006aeaa  mov     edx, [rdx+30h]
0x14006aead  lea     r8, aOnecoreBaseFsR_19; "onecore\\base\\fs\\remotefs\\smb\\srv\\"...
0x14006aeb4  mov     rcx, rbx
0x14006aeb7  call    _Smb2SetError
0x14006aebc  xor     edx, edx
0x14006aebe  mov     rcx, rbx
0x14006aec1  call    Srv2CompleteWorkItem
0x14006aec6  add     rsp, 20h
0x14006aeca  pop     r14
0x14006aecc  pop     rdi
0x14006aecd  pop     rsi
0x14006aece  pop     rbp
0x14006aecf  pop     rbx
0x14006aed0  retn
```
