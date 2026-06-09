# FileProvFinalizeCompress

- ea: `0x14003ae2c`
- end: `0x14003b0c2`
- name: `FileProvFinalizeCompress`
- size: `662`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x14003a528`

## callees

- `0x14000d158`
- `0x14000d354`
- `0x14003ae2c`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x14003aeec`
- `ntoskrnl!KeDelayExecutionThread` at `0x14003aeec`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003af87`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003af87`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003b012`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003b09f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003b012`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14003b09f`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14003aff1`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14003aff1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003b05f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003b05f`
- `ntoskrnl!ObfDereferenceObject` at `0x14003b079`
- `ntoskrnl!ObfDereferenceObject` at `0x14003b089`
- `ntoskrnl!ObfDereferenceObject` at `0x14003b079`
- `ntoskrnl!ObfDereferenceObject` at `0x14003b089`
- `FLTMGR!FltWriteFile` at `0x14003aebf`
- `FLTMGR!FltWriteFile` at `0x14003aebf`

## pseudocode

```c
__int64 __fastcall FileProvFinalizeCompress(__int64 a1, __int64 a2, __int64 a3)
{
  int v3; // edi
  bool v6; // zf
  _DWORD *v7; // r14
  ULONG v8; // esi
  NTSTATUS v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  unsigned int v12; // edx
  unsigned int i; // esi
  __int64 v14; // r14
  __int64 v15; // rbp
  __int64 v16; // rcx
  void *v17; // rdx
  unsigned int v18; // esi
  __int64 v19; // r14
  __int64 v20; // rbp
  union _LARGE_INTEGER Interval; // [rsp+88h] [rbp+10h] BYREF
  ULONG BytesWritten; // [rsp+90h] [rbp+18h] BYREF

  BytesWritten = 0;
  v3 = a3;
  if ( (int)a3 >= 0 )
  {
    v6 = *(_BYTE *)(a2 + 60) == 0;
    v7 = (_DWORD *)(a2 + 296);
    *(_QWORD *)(a2 + 40) = 0;
    v8 = v6 ? *(_DWORD *)(a2 + 108) : (*v7 + 4095) & 0xFFFFF000;
    while ( 1 )
    {
      v9 = FltWriteFile(
             *(PFLT_INSTANCE *)(a2 + 64),
             *(PFILE_OBJECT *)(a2 + 72),
             (PLARGE_INTEGER)(a2 + 40),
             v8,
             *(PVOID *)(a2 + 96),
             0xFu,
             &BytesWritten,
             0,
             0);
      v3 = v9;
      if ( v9 != -1073741740 )
        break;
      Interval.QuadPart = -100000;
      KeDelayExecutionThread(0, 1u, &Interval);
    }
    if ( v9 >= 0 )
    {
      v3 = 51314691;
      v10 = *(_QWORD *)(a1 + 8);
      *(_QWORD *)(a1 + 16) = *(_QWORD *)v7;
      a3 = -(__int64)**(unsigned int **)(a1 + 24);
      if ( (a3 & (*(_QWORD *)v7 + (unsigned __int64)**(unsigned int **)(a1 + 24) - 1)) >= (a3
                                                                                         & ((unsigned __int64)**(unsigned int **)(a1 + 24)
                                                                                          + v10
                                                                                          - 1)) )
        v3 = -1073740689;
    }
  }
  if ( a2 )
  {
    if ( *(_QWORD *)(a2 + 232) )
    {
      if ( *(_DWORD *)(a2 + 256) )
      {
        do
        {
          v11 = *(_QWORD *)(a2 + 232) + 136LL * *(unsigned int *)(a2 + 248);
          *(_QWORD *)(a2 + 240) = v11;
          KeWaitForSingleObject((PVOID)(v11 + 96), Executive, 0, 0, 0);
          v12 = (unsigned int)(*(_DWORD *)(a2 + 248) + 1) % *(_DWORD *)(a2 + 52);
          v6 = (*(_DWORD *)(a2 + 256))-- == 1;
          *(_DWORD *)(a2 + 248) = v12;
        }
        while ( !v6 );
      }
      for ( i = 0; i < *(_DWORD *)(a2 + 52); ++i )
      {
        v14 = *(_QWORD *)(a2 + 232);
        v15 = 136LL * i;
        v16 = *(_QWORD *)(v14 + v15 + 120);
        if ( v16 && *(_BYTE *)(v16 + 17348) )
          LZX_EncodeFree();
        v17 = *(void **)(v14 + v15 + 80);
        if ( v17 )
          ExFreeToPagedLookasideList((PPAGED_LOOKASIDE_LIST)(*(_QWORD *)(v14 + v15 + 40) + 64LL), v17);
      }
      ExFreeToNPagedLookasideList(&FileProvCompressWorkitemsLookaside, *(PVOID *)(a2 + 232));
    }
    v18 = 0;
    v19 = 0;
    do
    {
      v20 = v19 << 6;
      if ( *(_QWORD *)(a2 + (v19 << 6) + 96) )
      {
        if ( v18 != *(_DWORD *)(a2 + 224) )
        {
          LOBYTE(a3) = v3 > -1;
          FileProvWaitForWriteComplete(a2, v18, a3);
          if ( *(int *)(a2 + v20 + 112) < 0 && v3 >= 0 )
            v3 = *(_DWORD *)(a2 + v20 + 112);
        }
        ExFreePoolWithTag(*(PVOID *)(a2 + v20 + 96), 0);
      }
      ++v18;
      ++v19;
    }
    while ( v18 < 2 );
    ObfDereferenceObject(*(PVOID *)(a2 + 72));
    ObfDereferenceObject(*(PVOID *)(a2 + 80));
    ExFreeToNPagedLookasideList(&FileProvCompressContextLookaside, (PVOID)a2);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14003ae2c  mov     rax, rsp
0x14003ae2f  mov     [rax+8], rbx
0x14003ae33  push    rbp
0x14003ae34  push    rsi
0x14003ae35  push    rdi
0x14003ae36  push    r14
0x14003ae38  push    r15
0x14003ae3a  sub     rsp, 50h
0x14003ae3e  mov     dword ptr [rax+18h], 0
0x14003ae45  mov     edi, r8d
0x14003ae48  mov     rbx, rdx
0x14003ae4b  mov     rbp, rcx
0x14003ae4e  test    r8d, r8d
0x14003ae51  js      loc_14003AF37
0x14003ae57  cmp     byte ptr [rdx+3Ch], 0
0x14003ae5b  lea     r14, [rdx+128h]
0x14003ae62  mov     qword ptr [rdx+28h], 0
0x14003ae6a  jz      short loc_14003AE7D
0x14003ae6c  mov     esi, [r14]
0x14003ae6f  add     esi, 0FFFh
0x14003ae75  and     esi, 0FFFFF000h
0x14003ae7b  jmp     short loc_14003AE80
0x14003ae7d  mov     esi, [rdx+6Ch]
0x14003ae80  mov     rdx, [rbx+48h]; FileObject
0x14003ae84  lea     rax, [rsp+78h+arg_10]
0x14003ae8c  mov     rcx, [rbx+40h]; InitiatingInstance
0x14003ae90  lea     r8, [rbx+28h]; ByteOffset
0x14003ae94  mov     [rsp+78h+CallbackContext], 0; CallbackContext
0x14003ae9d  mov     r9d, esi; Length
0x14003aea0  mov     [rsp+78h+CallbackRoutine], 0; CallbackRoutine
0x14003aea9  mov     [rsp+78h+BytesWritten], rax; BytesWritten
0x14003aeae  mov     rax, [rbx+60h]
0x14003aeb2  mov     [rsp+78h+Flags], 0Fh; Flags
0x14003aeba  mov     [rsp+78h+Buffer], rax; Buffer
0x14003aebf  call    cs:__imp_FltWriteFile
0x14003aec6  nop     dword ptr [rax+rax+00h]
0x14003aecb  mov     edi, eax
0x14003aecd  cmp     eax, 0C0000054h
0x14003aed2  jnz     short loc_14003AEFA
0x14003aed4  lea     r8, [rsp+78h+Interval]; Interval
0x14003aedc  mov     qword ptr [rsp+78h+Interval], 0FFFFFFFFFFFE7960h
0x14003aee8  mov     dl, 1; Alertable
0x14003aeea  xor     ecx, ecx; WaitMode
0x14003aeec  call    cs:__imp_KeDelayExecutionThread
0x14003aef3  nop     dword ptr [rax+rax+00h]
0x14003aef8  jmp     short loc_14003AE80
0x14003aefa  test    eax, eax
0x14003aefc  js      short loc_14003AF37
0x14003aefe  mov     rax, [r14]
0x14003af01  mov     edi, 30F0003h
0x14003af06  mov     rdx, [rbp+8]
0x14003af0a  mov     [rbp+10h], rax
0x14003af0e  dec     rdx
0x14003af11  mov     rax, [rbp+18h]
0x14003af15  mov     ecx, [rax]
0x14003af17  mov     eax, 0C000046Fh
0x14003af1c  add     rdx, rcx
0x14003af1f  mov     r8d, ecx
0x14003af22  dec     rcx
0x14003af25  neg     r8
0x14003af28  add     rcx, [r14]
0x14003af2b  and     rdx, r8
0x14003af2e  and     rcx, r8
0x14003af31  cmp     rcx, rdx
0x14003af34  cmovnb  edi, eax
0x14003af37  test    rbx, rbx
0x14003af3a  jz      loc_14003B0AB
0x14003af40  cmp     qword ptr [rbx+0E8h], 0
0x14003af48  jz      loc_14003B01E
0x14003af4e  cmp     dword ptr [rbx+100h], 0
0x14003af55  jbe     short loc_14003AFAF
0x14003af57  mov     eax, [rbx+0F8h]
0x14003af5d  xor     r9d, r9d; Alertable
0x14003af60  imul    rcx, rax, 88h
0x14003af67  xor     r8d, r8d; WaitMode
0x14003af6a  mov     [rsp+78h+Buffer], 0; Timeout
0x14003af73  add     rcx, [rbx+0E8h]
0x14003af7a  xor     edx, edx; WaitReason
0x14003af7c  mov     [rbx+0F0h], rcx
0x14003af83  add     rcx, 60h ; '`'; Object
0x14003af87  call    cs:__imp_KeWaitForSingleObject
0x14003af8e  nop     dword ptr [rax+rax+00h]
0x14003af93  mov     eax, [rbx+0F8h]
0x14003af99  xor     edx, edx
0x14003af9b  inc     eax
0x14003af9d  div     dword ptr [rbx+34h]
0x14003afa0  sub     dword ptr [rbx+100h], 1
0x14003afa7  mov     [rbx+0F8h], edx
0x14003afad  jnz     short loc_14003AF57
0x14003afaf  xor     esi, esi
0x14003afb1  cmp     [rbx+34h], esi
0x14003afb4  jbe     short loc_14003B004
0x14003afb6  mov     r14, [rbx+0E8h]
0x14003afbd  mov     eax, esi
0x14003afbf  imul    rbp, rax, 88h
0x14003afc6  mov     rcx, [r14+rbp+78h]
0x14003afcb  test    rcx, rcx
0x14003afce  jz      short loc_14003AFDE
0x14003afd0  cmp     byte ptr [rcx+43C4h], 0
0x14003afd7  jz      short loc_14003AFDE
0x14003afd9  call    LZX_EncodeFree
0x14003afde  mov     rdx, [r14+rbp+50h]; Entry
0x14003afe3  test    rdx, rdx
0x14003afe6  jz      short loc_14003AFFD
0x14003afe8  mov     rcx, [r14+rbp+28h]
0x14003afed  add     rcx, 40h ; '@'; Lookaside
0x14003aff1  call    cs:__imp_ExFreeToPagedLookasideList
0x14003aff8  nop     dword ptr [rax+rax+00h]
0x14003affd  inc     esi
0x14003afff  cmp     esi, [rbx+34h]
0x14003b002  jb      short loc_14003AFB6
0x14003b004  mov     rdx, [rbx+0E8h]; Entry
0x14003b00b  lea     rcx, FileProvCompressWorkitemsLookaside; Lookaside
0x14003b012  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003b019  nop     dword ptr [rax+rax+00h]
0x14003b01e  xor     esi, esi
0x14003b020  xor     r14d, r14d
0x14003b023  mov     rbp, r14
0x14003b026  shl     rbp, 6
0x14003b02a  cmp     qword ptr [rbx+rbp+60h], 0
0x14003b030  jz      short loc_14003B06B
0x14003b032  cmp     esi, [rbx+0E0h]
0x14003b038  jz      short loc_14003B058
0x14003b03a  cmp     edi, 0FFFFFFFFh
0x14003b03d  mov     edx, esi
0x14003b03f  mov     rcx, rbx
0x14003b042  setnle  r8b
0x14003b046  call    FileProvWaitForWriteComplete
0x14003b04b  mov     eax, [rbx+rbp+70h]
0x14003b04f  test    eax, eax
0x14003b051  jns     short loc_14003B058
0x14003b053  test    edi, edi
0x14003b055  cmovns  edi, eax
0x14003b058  mov     rcx, [rbx+rbp+60h]; P
0x14003b05d  xor     edx, edx; Tag
0x14003b05f  call    cs:__imp_ExFreePoolWithTag
0x14003b066  nop     dword ptr [rax+rax+00h]
0x14003b06b  inc     esi
0x14003b06d  inc     r14
0x14003b070  cmp     esi, 2
0x14003b073  jb      short loc_14003B023
0x14003b075  mov     rcx, [rbx+48h]; Object
0x14003b079  call    cs:__imp_ObfDereferenceObject
0x14003b080  nop     dword ptr [rax+rax+00h]
0x14003b085  mov     rcx, [rbx+50h]; Object
0x14003b089  call    cs:__imp_ObfDereferenceObject
0x14003b090  nop     dword ptr [rax+rax+00h]
0x14003b095  mov     rdx, rbx; Entry
0x14003b098  lea     rcx, FileProvCompressContextLookaside; Lookaside
0x14003b09f  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003b0a6  nop     dword ptr [rax+rax+00h]
0x14003b0ab  mov     rbx, [rsp+78h+arg_0]
0x14003b0b3  mov     eax, edi
0x14003b0b5  add     rsp, 50h
0x14003b0b9  pop     r15
0x14003b0bb  pop     r14
0x14003b0bd  pop     rdi
0x14003b0be  pop     rsi
0x14003b0bf  pop     rbp
0x14003b0c0  retn
```
