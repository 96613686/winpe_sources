# WofPreCreateCallback

- ea: `0x140032640`
- end: `0x140032a04`
- name: `WofPreCreateCallback`
- size: `964`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1400014d0`
- `0x14000b760`
- `0x140011640`
- `0x140032640`

## import_xrefs

- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14003288f`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x14003288f`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140032715`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x140032715`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400328dd`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400328dd`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140032855`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003299a`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140032855`
- `FLTMGR!FltReleaseFileNameInformation` at `0x14003299a`
- `FLTMGR!FltGetFileNameInformation` at `0x14003295f`
- `FLTMGR!FltGetFileNameInformation` at `0x14003295f`
- `FLTMGR!FltAddOpenReparseEntry` at `0x140032755`
- `FLTMGR!FltAddOpenReparseEntry` at `0x140032755`
- `FLTMGR!FltReleaseContext` at `0x1400326aa`
- `FLTMGR!FltReleaseContext` at `0x140032866`
- `FLTMGR!FltReleaseContext` at `0x1400326aa`
- `FLTMGR!FltReleaseContext` at `0x140032866`

## pseudocode

```c
__int64 __fastcall WofPreCreateCallback(PFLT_CALLBACK_DATA CallbackData, __int64 a2, _QWORD *a3)
{
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  PFILE_OBJECT TargetFileObject; // r9
  int v7; // r9d
  PFLT_IO_PARAMETER_BLOCK v8; // rdx
  char *v9; // rax
  void *v10; // rbx
  NTSTATUS v11; // esi
  __int64 result; // rax
  UNICODE_STRING *p_FileName; // rsi
  UCHAR OperationFlags; // r15
  USHORT Length; // bx
  BOOLEAN v16; // r15
  unsigned __int16 v17; // bx
  unsigned __int16 v18; // r8
  WCHAR v19; // ax
  struct _FLT_FILE_NAME_INFORMATION *v20; // rcx
  unsigned int i; // ebp
  __int64 v22; // rcx
  unsigned int (__fastcall *v23)(_QWORD, UNICODE_STRING *, _QWORD); // rax
  int FileNameInformation; // eax
  UNICODE_STRING String1; // [rsp+50h] [rbp-48h] BYREF
  UNICODE_STRING String2; // [rsp+60h] [rbp-38h] BYREF
  PFLT_CONTEXT Context; // [rsp+A0h] [rbp+8h] BYREF

  Iopb = CallbackData->Iopb;
  Context = 0;
  TargetFileObject = Iopb->TargetFileObject;
  if ( (!TargetFileObject->FileName.Buffer || !TargetFileObject->FileName.Length)
    && !TargetFileObject->RelatedFileObject
    || (int)WofGetVolumeContext(*(PFLT_INSTANCE *)(a2 + 24), &Context) < 0 )
  {
    return 1;
  }
  if ( (*((_DWORD *)Context + 14) & 1) != 0 )
  {
    FltReleaseContext(Context);
    return 1;
  }
  FltReleaseContext(Context);
  *a3 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qZDlL(
      WPP_GLOBAL_Control->DeviceExtension,
      CallbackData->Iopb->Parameters.Create.Options & 0xFFFFFF,
      CallbackData->Iopb->TargetFileObject,
      v7);
  v8 = CallbackData->Iopb;
  if ( (*(_DWORD *)(v8->Parameters.WMI.ProviderId + 16) & 0xFFEFFF7F) != 0
    || HIBYTE(v8->Parameters.SetVolumeInformation.FsInformationClass) != 1 )
  {
    p_FileName = &v8->TargetFileObject->FileName;
    Context = 0;
    String1 = 0;
    OperationFlags = v8->OperationFlags;
    Length = p_FileName->Length;
    if ( p_FileName->Length )
      goto LABEL_16;
    FileNameInformation = FltGetFileNameInformation(CallbackData, 0x4000102u, (PFLT_FILE_NAME_INFORMATION *)&Context);
    if ( FileNameInformation < 0 )
    {
      CallbackData->IoStatus.Status = FileNameInformation;
      return 4;
    }
    v20 = (struct _FLT_FILE_NAME_INFORMATION *)Context;
    Length = *((_WORD *)Context + 4);
    p_FileName = (UNICODE_STRING *)((char *)Context + 8);
    if ( Length )
    {
LABEL_16:
      v16 = (unsigned __int8)~OperationFlags >> 7;
      v17 = Length >> 1;
      v18 = v17;
      do
      {
        v19 = p_FileName->Buffer[--v17];
        if ( v19 == 92 )
          break;
        if ( v19 == 58 )
        {
          String1.Buffer = &p_FileName->Buffer[v17];
          *(_QWORD *)&String2.Length = 917516;
          String1.MaximumLength = 2 * (v18 - v17);
          String1.Length = String1.MaximumLength;
          String2.Buffer = L":$DATA";
          if ( RtlCompareUnicodeString(&String1, &String2, v16) )
          {
            for ( i = 0; i < 4; ++i )
            {
              v22 = 424LL * i;
              if ( *((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v22) )
              {
                v23 = *(unsigned int (__fastcall **)(_QWORD, UNICODE_STRING *, _QWORD))((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels
                                                                                      + v22
                                                                                      + 136);
                if ( v23 )
                {
                  if ( v23(0, &String1, v16) == -1073741275 )
                  {
                    if ( Context )
                      FltReleaseFileNameInformation((PFLT_FILE_NAME_INFORMATION)Context);
                    CallbackData->IoStatus.Status = -1073741790;
                    return 4;
                  }
                }
              }
            }
          }
          v18 = v17;
        }
      }
      while ( v17 );
      v20 = (struct _FLT_FILE_NAME_INFORMATION *)Context;
    }
    if ( v20 )
      FltReleaseFileNameInformation(v20);
  }
  v9 = (char *)ExAllocateFromPagedLookasideList(&Lookaside);
  v10 = v9;
  if ( v9 )
  {
    *((_QWORD *)v9 + 1) = v9;
    *(_QWORD *)v9 = v9;
    *((_DWORD *)v9 + 4) = FileTag;
    *((_DWORD *)v9 + 5) = 0;
    *(_OWORD *)(v9 + 24) = 0;
    v11 = FltAddOpenReparseEntry(WofGlobal, CallbackData, v9);
    if ( v11 < 0 )
    {
      ExFreeToPagedLookasideList(&Lookaside, v10);
      result = 4;
      CallbackData->IoStatus.Status = v11;
    }
    else
    {
      *a3 = v10;
      return 5;
    }
  }
  else
  {
    CallbackData->IoStatus.Status = -1073741670;
    return 4;
  }
  return result;
}

```

## disassembly

```asm
0x140032640  push    rdi
0x140032642  push    r12
0x140032644  push    r14
0x140032646  sub     rsp, 80h
0x14003264d  mov     rax, [rcx+10h]
0x140032651  xor     r12d, r12d
0x140032654  mov     r14, r8
0x140032657  mov     [rsp+98h+Context], r12
0x14003265f  mov     r10, rdx
0x140032662  mov     rdi, rcx
0x140032665  mov     r9, [rax+8]
0x140032669  cmp     [r9+60h], r12
0x14003266d  jz      loc_1400327A3
0x140032673  cmp     [r9+58h], r12w
0x140032678  jz      loc_1400327A3
0x14003267e  mov     rcx, [r10+18h]; Instance
0x140032682  lea     rdx, [rsp+98h+Context]
0x14003268a  call    WofGetVolumeContext
0x14003268f  test    eax, eax
0x140032691  js      loc_140032872
0x140032697  mov     rcx, [rsp+98h+Context]; Context
0x14003269f  mov     eax, [rcx+38h]
0x1400326a2  test    al, 1
0x1400326a4  jnz     loc_140032866
0x1400326aa  call    cs:__imp_FltReleaseContext
0x1400326b1  nop     dword ptr [rax+rax+00h]
0x1400326b6  mov     [r14], r12
0x1400326b9  lea     rax, WPP_RECORDER_INITIALIZED
0x1400326c0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400326c7  jnz     loc_1400329C4
0x1400326cd  mov     rdx, [rdi+10h]
0x1400326d1  mov     [rsp+98h+arg_8], rbx
0x1400326d9  mov     [rsp+98h+arg_10], rbp
0x1400326e1  mov     [rsp+98h+arg_18], rsi
0x1400326e9  mov     rax, [rdx+18h]
0x1400326ed  mov     [rsp+98h+var_20], r13
0x1400326f2  mov     [rsp+98h+var_28], r15
0x1400326f7  test    dword ptr [rax+10h], 0FFEFFF7Fh
0x1400326fe  jnz     loc_1400327C0
0x140032704  cmp     byte ptr [rdx+23h], 1
0x140032708  jnz     loc_1400327C0
0x14003270e  lea     rcx, Lookaside; Lookaside
0x140032715  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14003271c  nop     dword ptr [rax+rax+00h]
0x140032721  mov     rbx, rax
0x140032724  test    rax, rax
0x140032727  jz      loc_1400327B2
0x14003272d  mov     [rax+8], rax
0x140032731  xorps   xmm0, xmm0
0x140032734  mov     [rax], rax
0x140032737  mov     r8, rbx
0x14003273a  mov     eax, cs:FileTag
0x140032740  mov     rdx, rdi
0x140032743  mov     [rbx+10h], eax
0x140032746  mov     [rbx+14h], r12d
0x14003274a  movups  xmmword ptr [rbx+18h], xmm0
0x14003274e  mov     rcx, cs:WofGlobal
0x140032755  call    cs:__imp_FltAddOpenReparseEntry
0x14003275c  nop     dword ptr [rax+rax+00h]
0x140032761  mov     esi, eax
0x140032763  test    eax, eax
0x140032765  js      loc_140032885
0x14003276b  mov     [r14], rbx
0x14003276e  mov     eax, 5
0x140032773  mov     r13, [rsp+98h+var_20]
0x140032778  mov     rsi, [rsp+98h+arg_18]
0x140032780  mov     rbp, [rsp+98h+arg_10]
0x140032788  mov     rbx, [rsp+98h+arg_8]
0x140032790  mov     r15, [rsp+98h+var_28]
0x140032795  add     rsp, 80h
0x14003279c  pop     r14
0x14003279e  pop     r12
0x1400327a0  pop     rdi
0x1400327a1  retn
0x1400327a3  cmp     [r9+40h], r12
0x1400327a7  jnz     loc_14003267E
0x1400327ad  jmp     loc_140032872
0x1400327b2  mov     dword ptr [rdi+18h], 0C000009Ah
0x1400327b9  mov     eax, 4
0x1400327be  jmp     short loc_140032773
0x1400327c0  mov     rsi, [rdx+8]
0x1400327c4  mov     rcx, r12
0x1400327c7  add     rsi, 58h ; 'X'
0x1400327cb  mov     [rsp+98h+Context], rcx
0x1400327d3  xorps   xmm0, xmm0
0x1400327d6  movups  xmmword ptr [rsp+98h+String1.Length], xmm0
0x1400327db  movzx   r15d, byte ptr [rdx+6]
0x1400327e0  movzx   ebx, word ptr [rsi]
0x1400327e3  test    bx, bx
0x1400327e6  jz      loc_14003294F
0x1400327ec  not     r15b
0x1400327ef  lea     r9, aData_0; ":$DATA"
0x1400327f6  shr     r15b, 7
0x1400327fa  mov     r13d, 0FFFFh
0x140032800  shr     bx, 1
0x140032803  mov     r10d, 0Ch
0x140032809  movzx   r8d, bx
0x14003280d  mov     r11d, 0Eh
0x140032813  nop     dword ptr [rax+00h]
0x140032817  nop     word ptr [rax+rax+00000000h]
0x140032820  mov     rax, [rsi+8]
0x140032824  add     bx, r13w
0x140032828  movzx   ecx, bx
0x14003282b  lea     rdx, [rax+rcx*2]
0x14003282f  movzx   eax, word ptr [rax+rcx*2]
0x140032833  cmp     ax, 5Ch ; '\'
0x140032837  jz      short loc_140032844
0x140032839  cmp     ax, 3Ah ; ':'
0x14003283d  jz      short loc_1400328A8
0x14003283f  test    bx, bx
0x140032842  jnz     short loc_140032820
0x140032844  mov     rcx, [rsp+98h+Context]; FileNameInformation
0x14003284c  test    rcx, rcx
0x14003284f  jz      loc_14003270E
0x140032855  call    cs:__imp_FltReleaseFileNameInformation
0x14003285c  nop     dword ptr [rax+rax+00h]
0x140032861  jmp     loc_14003270E
0x140032866  call    cs:__imp_FltReleaseContext
0x14003286d  nop     dword ptr [rax+rax+00h]
0x140032872  mov     eax, 1
0x140032877  add     rsp, 80h
0x14003287e  pop     r14
0x140032880  pop     r12
0x140032882  pop     rdi
0x140032883  retn
0x140032885  mov     rdx, rbx; Entry
0x140032888  lea     rcx, Lookaside; Lookaside
0x14003288f  call    cs:__imp_ExFreeToPagedLookasideList
0x140032896  nop     dword ptr [rax+rax+00h]
0x14003289b  mov     eax, 4
0x1400328a0  mov     [rdi+18h], esi
0x1400328a3  jmp     loc_140032773
0x1400328a8  sub     r8w, bx
0x1400328ac  mov     [rsp+98h+String1.Buffer], rdx
0x1400328b1  add     r8w, r8w
0x1400328b5  mov     qword ptr [rsp+98h+String2.Length], 0E000Ch
0x1400328be  mov     [rsp+98h+String1.MaximumLength], r8w
0x1400328c4  lea     rdx, [rsp+98h+String2]; String2
0x1400328c9  mov     [rsp+98h+String1.Length], r8w
0x1400328cf  lea     rcx, [rsp+98h+String1]; String1
0x1400328d4  movzx   r8d, r15b; CaseInSensitive
0x1400328d8  mov     [rsp+98h+String2.Buffer], r9
0x1400328dd  call    cs:__imp_RtlCompareUnicodeString
0x1400328e4  nop     dword ptr [rax+rax+00h]
0x1400328e9  test    eax, eax
0x1400328eb  jz      short loc_140032933
0x1400328ed  mov     ebp, r12d
0x1400328f0  cmp     ebp, 4
0x1400328f3  jnb     short loc_140032933
0x1400328f5  mov     eax, ebp
0x1400328f7  imul    rcx, rax, 1A8h
0x1400328fe  lea     rax, WPP_MAIN_CB.Queue+10h
0x140032905  cmp     [rcx+rax], r12b
0x140032909  jz      short loc_14003292F
0x14003290b  mov     rax, [rcx+rax+88h]
0x140032913  test    rax, rax
0x140032916  jz      short loc_14003292F
0x140032918  movzx   r8d, r15b
0x14003291c  lea     rdx, [rsp+98h+String1]
0x140032921  xor     ecx, ecx
0x140032923  call    _guard_dispatch_icall
0x140032928  cmp     eax, 0C0000225h
0x14003292d  jz      short loc_14003298D
0x14003292f  inc     ebp
0x140032931  jmp     short loc_1400328F0
0x140032933  movzx   r8d, bx
0x140032937  lea     r9, aData_0; ":$DATA"
0x14003293e  mov     r10d, 0Ch
0x140032944  mov     r11d, 0Eh
0x14003294a  jmp     loc_14003283F
0x14003294f  lea     r8, [rsp+98h+Context]; FileNameInformation
0x140032957  mov     edx, 4000102h; NameOptions
0x14003295c  mov     rcx, rdi; CallbackData
0x14003295f  call    cs:__imp_FltGetFileNameInformation
0x140032966  nop     dword ptr [rax+rax+00h]
0x14003296b  test    eax, eax
0x14003296d  js      short loc_1400329B7
0x14003296f  mov     rcx, [rsp+98h+Context]
0x140032977  movzx   ebx, word ptr [rcx+8]
0x14003297b  lea     rsi, [rcx+8]
0x14003297f  test    bx, bx
0x140032982  jz      loc_14003284C
0x140032988  jmp     loc_1400327EC
0x14003298d  mov     rcx, [rsp+98h+Context]; FileNameInformation
0x140032995  test    rcx, rcx
0x140032998  jz      short loc_1400329A6
0x14003299a  call    cs:__imp_FltReleaseFileNameInformation
0x1400329a1  nop     dword ptr [rax+rax+00h]
0x1400329a6  mov     dword ptr [rdi+18h], 0C0000022h
0x1400329ad  mov     eax, 4
0x1400329b2  jmp     loc_140032773
0x1400329b7  mov     [rdi+18h], eax
0x1400329ba  mov     eax, 4
0x1400329bf  jmp     loc_140032773
0x1400329c4  mov     rax, [rdi+10h]
0x1400329c8  movzx   ecx, byte ptr [rax+23h]
0x1400329cc  mov     r8, [rax+8]
0x1400329d0  mov     edx, [rax+20h]
0x1400329d3  mov     [rsp+98h+var_58], ecx
0x1400329d7  and     edx, 0FFFFFFh
0x1400329dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400329e4  mov     [rsp+98h+var_60], edx
0x1400329e8  lea     rax, [r8+58h]
0x1400329ec  mov     [rsp+98h+var_68], rax
0x1400329f1  mov     [rsp+98h+var_70], r8
0x1400329f6  mov     rcx, [rcx+40h]
0x1400329fa  call    WPP_RECORDER_SF_qZDlL
0x1400329ff  jmp     loc_1400326CD
```
