# VfsCreateCompletion

- ea: `0x140003f24`
- end: `0x140004146`
- name: `VfsCreateCompletion`
- size: `546`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData, __int64, char *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000a960`

## callees

- `0x140001fb4`
- `0x140003f24`
- `0x140005308`
- `0x140012acc`

## import_xrefs

- `ntoskrnl!RtlCopySid` at `0x1400040a3`
- `ntoskrnl!RtlCopySid` at `0x1400040a3`
- `ntoskrnl!ExAllocatePool2` at `0x140004027`
- `ntoskrnl!ExAllocatePool2` at `0x140004027`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000405a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000405a`
- `FLTMGR!FltCancelFileOpen` at `0x140004114`
- `FLTMGR!FltCancelFileOpen` at `0x140004114`
- `FLTMGR!FltDeleteContext` at `0x1400040eb`
- `FLTMGR!FltDeleteContext` at `0x140014932`
- `FLTMGR!FltDeleteContext` at `0x1400040eb`
- `FLTMGR!FltDeleteContext` at `0x140014932`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400040ce`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140014913`
- `FLTMGR!FltReleaseFileNameInformation` at `0x1400040ce`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140014913`
- `FLTMGR!FltGetFileNameInformation` at `0x140003fc8`
- `FLTMGR!FltGetFileNameInformation` at `0x140003fc8`
- `FLTMGR!FltReleaseContext` at `0x1400040fc`
- `FLTMGR!FltReleaseContext` at `0x140014942`
- `FLTMGR!FltReleaseContext` at `0x1400040fc`
- `FLTMGR!FltReleaseContext` at `0x140014942`

## string_xrefs

- `0x140003ff1`: `VfsCreateCompletion() - Failed to get filename info for data: %p\n IRP: %d\n Status: 0x%08X`

## pseudocode

```c
__int64 __fastcall VfsCreateCompletion(PFLT_CALLBACK_DATA CallbackData, __int64 a2, char *a3)
{
  int StreamHandleContext; // ebx
  PFLT_FILE_NAME_INFORMATION v7; // r12
  unsigned __int16 Length; // bx
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+88h] [rbp+20h] BYREF

  if ( !CallbackData->IoStatus.Status )
  {
    if ( (*(_DWORD *)a3 & 2) != 0 )
      *(_QWORD *)(*(_QWORD *)(a2 + 32) + 64LL) = *((_QWORD *)a3 + 1);
    if ( !CallbackData->IoStatus.Status && (*(_DWORD *)a3 & 4) != 0 )
    {
      FileNameInformation = 0;
      StreamHandleContext = VfsCreateStreamHandleContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32));
      if ( StreamHandleContext >= 0 )
      {
        if ( (*(_DWORD *)a3 & 1) != 0 )
        {
          StreamHandleContext = FltGetFileNameInformation(CallbackData, 0x101u, &FileNameInformation);
          if ( StreamHandleContext < 0 )
          {
            LogWrite(
              1,
              0,
              L"VfsCreateCompletion() - Failed to get filename info for data: %p\n IRP: %d\n Status: 0x%08X",
              CallbackData,
              CallbackData->Iopb->MajorFunction,
              StreamHandleContext,
              StreamHandleContext);
            goto LABEL_17;
          }
          v7 = FileNameInformation;
          Length = FileNameInformation->Name.Length;
          MEMORY[0x10] = ExAllocatePool2(256, Length, 1951614550);
          if ( MEMORY[0x10] )
          {
            MEMORY[8] = 0;
            MEMORY[0xA] = Length;
            StreamHandleContext = 0;
            RtlCopyUnicodeString((PUNICODE_STRING)8, &v7->Name);
          }
          else
          {
            StreamHandleContext = -1073741670;
          }
          if ( StreamHandleContext < 0 )
            goto LABEL_17;
          if ( (CallbackData->Iopb->OperationFlags & 4) != 0 )
          {
            MEMORY[0x18] = *(_OWORD *)(a3 + 120);
            *((_QWORD *)a3 + 16) = 0;
          }
        }
        RtlCopySid(0x44u, (PSID)0x48, a3 + 16);
        MEMORY[0x28] = *(_OWORD *)(a3 + 84);
        MEMORY[0x38] = *(_OWORD *)(a3 + 100);
      }
LABEL_17:
      if ( FileNameInformation )
        FltReleaseFileNameInformation(FileNameInformation);
      if ( StreamHandleContext < 0 )
      {
        FltCancelFileOpen(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32));
        CallbackData->IoStatus.Status = StreamHandleContext;
        CallbackData->IoStatus.Information = 0;
      }
    }
  }
  return VfsDeleteCreateCompletionContext(a3);
}

```

## disassembly

```asm
0x140003f24  mov     [rsp+arg_8], rbx
0x140003f29  push    rsi
0x140003f2a  push    rdi
0x140003f2b  push    r12
0x140003f2d  push    r14
0x140003f2f  push    r15
0x140003f31  sub     rsp, 40h
0x140003f35  mov     rdi, r8
0x140003f38  mov     r15, rdx
0x140003f3b  mov     rsi, rcx
0x140003f3e  cmp     dword ptr [rcx+18h], 0
0x140003f42  jnz     loc_14000412B
0x140003f48  mov     eax, [r8]
0x140003f4b  test    al, 2
0x140003f4d  jz      short loc_140003F5B
0x140003f4f  mov     r9, [rdx+20h]
0x140003f53  mov     rax, [r8+8]
0x140003f57  mov     [r9+40h], rax
0x140003f5b  cmp     dword ptr [rcx+18h], 0
0x140003f5f  jnz     loc_14000412B
0x140003f65  mov     eax, [r8]
0x140003f68  test    al, 4
0x140003f6a  jz      loc_14000412B
0x140003f70  mov     [rsp+68h+var_38], 0
0x140003f78  mov     [rsp+68h+Context], 0
0x140003f81  mov     [rsp+68h+FileNameInformation], 0
0x140003f8d  lea     r8, [rsp+68h+Context]
0x140003f92  mov     rdx, [rdx+20h]; FileObject
0x140003f96  mov     rcx, [r15+18h]; Instance
0x140003f9a  call    VfsCreateStreamHandleContext
0x140003f9f  mov     ebx, eax
0x140003fa1  mov     [rsp+68h+var_38], eax
0x140003fa5  test    eax, eax
0x140003fa7  js      loc_1400040C1
0x140003fad  mov     ecx, [rdi]
0x140003faf  test    cl, 1
0x140003fb2  jz      loc_140004091
0x140003fb8  lea     r8, [rsp+68h+FileNameInformation]; FileNameInformation
0x140003fc0  mov     edx, 101h; NameOptions
0x140003fc5  mov     rcx, rsi; CallbackData
0x140003fc8  call    cs:__imp_FltGetFileNameInformation
0x140003fcf  nop     dword ptr [rax+rax+00h]
0x140003fd4  mov     ebx, eax
0x140003fd6  mov     [rsp+68h+var_38], eax
0x140003fda  test    eax, eax
0x140003fdc  jns     short loc_140004007
0x140003fde  mov     rax, [rsi+10h]
0x140003fe2  movzx   edx, byte ptr [rax+4]
0x140003fe6  mov     [rsp+68h+var_40], ebx
0x140003fea  mov     [rsp+68h+var_48], edx
0x140003fee  mov     r9, rsi
0x140003ff1  lea     r8, aVfscreatecompl; "VfsCreateCompletion() - Failed to get f"...
0x140003ff8  xor     edx, edx
0x140003ffa  lea     ecx, [rdx+1]
0x140003ffd  call    LogWrite
0x140004002  jmp     loc_1400040C1
0x140004007  mov     r14, [rsp+68h+Context]
0x14000400c  mov     r12, [rsp+68h+FileNameInformation]
0x140004014  movzx   ebx, word ptr [r12+8]
0x14000401a  mov     edx, ebx
0x14000401c  mov     ecx, 100h
0x140004021  mov     r8d, 74534656h
0x140004027  call    cs:__imp_ExAllocatePool2
0x14000402e  nop     dword ptr [rax+rax+00h]
0x140004033  mov     [r14+10h], rax
0x140004037  test    rax, rax
0x14000403a  jnz     short loc_140004043
0x14000403c  mov     ebx, 0C000009Ah
0x140004041  jmp     short loc_140004066
0x140004043  xor     eax, eax
0x140004045  mov     [r14+8], ax
0x14000404a  mov     [r14+0Ah], bx
0x14000404f  xor     ebx, ebx
0x140004051  lea     rdx, [r12+8]; SourceString
0x140004056  lea     rcx, [r14+8]; DestinationString
0x14000405a  call    cs:__imp_RtlCopyUnicodeString
0x140004061  nop     dword ptr [rax+rax+00h]
0x140004066  mov     [rsp+68h+var_38], ebx
0x14000406a  test    ebx, ebx
0x14000406c  js      short loc_1400040C1
0x14000406e  mov     rax, [rsi+10h]
0x140004072  test    byte ptr [rax+6], 4
0x140004076  jz      short loc_140004091
0x140004078  movups  xmm0, xmmword ptr [rdi+78h]
0x14000407c  mov     rax, [rsp+68h+Context]
0x140004081  movdqu  xmmword ptr [rax+18h], xmm0
0x140004086  mov     qword ptr [rdi+80h], 0
0x140004091  lea     r8, [rdi+10h]; SourceSid
0x140004095  mov     r14, [rsp+68h+Context]
0x14000409a  lea     rdx, [r14+48h]; DestinationSid
0x14000409e  mov     ecx, 44h ; 'D'; DestinationSidLength
0x1400040a3  call    cs:__imp_RtlCopySid
0x1400040aa  nop     dword ptr [rax+rax+00h]
0x1400040af  movups  xmm0, xmmword ptr [rdi+54h]
0x1400040b3  movups  xmmword ptr [r14+28h], xmm0
0x1400040b8  movups  xmm1, xmmword ptr [rdi+64h]
0x1400040bc  movups  xmmword ptr [r14+38h], xmm1
0x1400040c1  mov     rcx, [rsp+68h+FileNameInformation]; FileNameInformation
0x1400040c9  test    rcx, rcx
0x1400040cc  jz      short loc_1400040DA
0x1400040ce  call    cs:__imp_FltReleaseFileNameInformation
0x1400040d5  nop     dword ptr [rax+rax+00h]
0x1400040da  mov     r14, [rsp+68h+Context]
0x1400040df  test    r14, r14
0x1400040e2  jz      short loc_140004108
0x1400040e4  test    ebx, ebx
0x1400040e6  jns     short loc_1400040F7
0x1400040e8  mov     rcx, r14; Context
0x1400040eb  call    cs:__imp_FltDeleteContext
0x1400040f2  nop     dword ptr [rax+rax+00h]
0x1400040f7  mov     rcx, [rsp+68h+Context]; Context
0x1400040fc  call    cs:__imp_FltReleaseContext
0x140004103  nop     dword ptr [rax+rax+00h]
0x140004108  test    ebx, ebx
0x14000410a  jns     short loc_14000412B
0x14000410c  mov     rdx, [r15+20h]; FileObject
0x140004110  mov     rcx, [r15+18h]; Instance
0x140004114  call    cs:__imp_FltCancelFileOpen
0x14000411b  nop     dword ptr [rax+rax+00h]
0x140004120  mov     [rsi+18h], ebx
0x140004123  mov     qword ptr [rsi+20h], 0
0x14000412b  mov     rcx, rdi; Entry
0x14000412e  call    VfsDeleteCreateCompletionContext
0x140004133  mov     rbx, [rsp+68h+arg_8]
0x140004138  add     rsp, 40h
0x14000413c  pop     r15
0x14000413e  pop     r14
0x140004140  pop     r12
0x140004142  pop     rdi
0x140004143  pop     rsi
0x140004144  retn
0x1400148fd  push    rbx
0x1400148ff  push    rbp
0x140014900  sub     rsp, 38h
0x140014904  mov     rbp, rdx
0x140014907  mov     rcx, [rbp+88h]; FileNameInformation
0x14001490e  test    rcx, rcx
0x140014911  jz      short loc_140014920
0x140014913  call    cs:__imp_FltReleaseFileNameInformation
0x14001491a  nop     dword ptr [rax+rax+00h]
0x14001491f  nop
0x140014920  mov     rbx, [rbp+70h]
0x140014924  test    rbx, rbx
0x140014927  jz      short loc_14001494F
0x140014929  cmp     dword ptr [rbp+30h], 0
0x14001492d  jge     short loc_14001493F
0x14001492f  mov     rcx, rbx; Context
0x140014932  call    cs:__imp_FltDeleteContext
0x140014939  nop     dword ptr [rax+rax+00h]
0x14001493e  nop
0x14001493f  mov     rcx, rbx; Context
0x140014942  call    cs:__imp_FltReleaseContext
0x140014949  nop     dword ptr [rax+rax+00h]
0x14001494e  nop
0x14001494f  add     rsp, 38h
0x140014953  pop     rbp
0x140014954  pop     rbx
0x140014955  retn
```
