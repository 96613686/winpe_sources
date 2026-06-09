# SmPostCreate

- ea: `0x140007030`
- end: `0x14000725c`
- name: `SmPostCreate`
- size: `556`
- prototype: `__int64 __fastcall(PFLT_CALLBACK_DATA CallbackData)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x14000118c`
- `0x1400015e0`
- `0x140001674`
- `0x140007030`
- `0x1400076f0`
- `0x140007cec`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000720e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007227`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000720e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007227`
- `ntoskrnl!IoThreadToProcess` at `0x1400070d7`
- `ntoskrnl!IoThreadToProcess` at `0x1400070d7`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140007237`
- `FLTMGR!FltReleaseFileNameInformation` at `0x140007237`
- `FLTMGR!FltGetFileNameInformation` at `0x1400070a7`
- `FLTMGR!FltGetFileNameInformation` at `0x1400070a7`
- `FLTMGR!FltSetStreamHandleContext` at `0x1400071da`
- `FLTMGR!FltSetStreamHandleContext` at `0x1400071da`
- `FLTMGR!FltReleaseContext` at `0x1400071ea`
- `FLTMGR!FltReleaseContext` at `0x1400071ea`
- `FLTMGR!FltParseFileNameInformation` at `0x1400070bf`
- `FLTMGR!FltParseFileNameInformation` at `0x1400070bf`
- `FLTMGR!FltAllocateContext` at `0x140007195`
- `FLTMGR!FltAllocateContext` at `0x140007195`

## pseudocode

```c
__int64 __fastcall SmPostCreate(PFLT_CALLBACK_DATA CallbackData, __int64 a2)
{
  NTSTATUS Status; // eax
  ULONG_PTR Information; // rax
  int v6; // edi
  struct _KTHREAD *Thread; // rcx
  PEPROCESS v8; // rax
  struct _KPROCESS *v9; // rbx
  __int64 v10; // r14
  PVOID v11; // rbx
  struct _FLT_FILTER *v12; // rcx
  size_t Size; // [rsp+28h] [rbp-48h]
  size_t v15; // [rsp+40h] [rbp-30h] BYREF
  PVOID P; // [rsp+48h] [rbp-28h] BYREF
  PFLT_FILE_NAME_INFORMATION FileNameInformation; // [rsp+50h] [rbp-20h] BYREF
  PVOID Src; // [rsp+58h] [rbp-18h] BYREF
  __int64 v19; // [rsp+60h] [rbp-10h] BYREF
  PFLT_CONTEXT NewContext; // [rsp+90h] [rbp+20h] BYREF

  Status = CallbackData->IoStatus.Status;
  FileNameInformation = 0;
  LOBYTE(NewContext) = 0;
  if ( Status >= 0 && Status != 260 )
  {
    Information = CallbackData->IoStatus.Information;
    if ( (Information & 0xFFFFFFFFFFFFFFFCuLL) != 0 || (v6 = 1, Information == 1) )
    {
      if ( (*(_DWORD *)(CallbackData->Iopb->Parameters.WMI.ProviderId + 16) & 0x40000006) == 0 )
        return 0;
      v6 = 0;
    }
    if ( FltGetFileNameInformation(CallbackData, 0x101u, &FileNameInformation) >= 0 )
    {
      FltParseFileNameInformation(FileNameInformation);
      Thread = CallbackData->Thread;
      P = 0;
      v8 = IoThreadToProcess(Thread);
      Src = 0;
      v9 = v8;
      LODWORD(v15) = 0;
      v19 = 0;
      v10 = SmCheckProcessOrigin(v8);
      SmCheckProcessSessionOrigin(v9, &v15, &Src);
      SmCheckOrigin(v9, &NewContext, &P);
      v11 = Src;
      if ( (_BYTE)NewContext || v10 || Src )
      {
        LODWORD(Size) = v15;
        if ( (int)SmpSetEaFromOrigin(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), Src, Size, (__int64)&v19) >= 0 )
        {
          v12 = *(struct _FLT_FILTER **)(a2 + 8);
          NewContext = 0;
          if ( FltAllocateContext(v12, 0x10u, 8u, (POOL_TYPE)512, &NewContext) >= 0 )
          {
            *(_QWORD *)NewContext = 0;
            *(_DWORD *)NewContext = v6;
            *((_DWORD *)NewContext + 1) = *(_DWORD *)(v19 + 8);
            FltSetStreamHandleContext(
              *(PFLT_INSTANCE *)(a2 + 24),
              *(PFILE_OBJECT *)(a2 + 32),
              FLT_SET_CONTEXT_REPLACE_IF_EXISTS,
              NewContext,
              0);
            FltReleaseContext(NewContext);
          }
        }
        SmReleaseOriginProcessData(v10);
      }
      if ( P )
        ExFreePoolWithTag(P, 0x41746D73u);
      if ( v11 )
        ExFreePoolWithTag(v11, 0x53746D73u);
      FltReleaseFileNameInformation(FileNameInformation);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140007030  mov     [rsp-18h+arg_8], rbx
0x140007035  mov     [rsp-18h+arg_10], rdi
0x14000703a  push    rbp
0x14000703b  push    r14
0x14000703d  push    r15
0x14000703f  mov     rbp, rsp
0x140007042  sub     rsp, 70h
0x140007046  mov     eax, [rcx+18h]
0x140007049  mov     r15, rdx
0x14000704c  mov     [rbp+FileNameInformation], 0
0x140007054  mov     rbx, rcx
0x140007057  mov     byte ptr [rbp+NewContext], 0
0x14000705b  test    eax, eax
0x14000705d  js      loc_140007243
0x140007063  cmp     eax, 104h
0x140007068  jz      loc_140007243
0x14000706e  mov     rax, [rcx+20h]
0x140007072  test    rax, 0FFFFFFFFFFFFFFFCh
0x140007078  jnz     short loc_140007084
0x14000707a  mov     edi, 1
0x14000707f  cmp     rax, rdi
0x140007082  jnz     short loc_14000709B
0x140007084  mov     rax, [rcx+10h]
0x140007088  mov     rcx, [rax+18h]
0x14000708c  test    dword ptr [rcx+10h], 40000006h
0x140007093  jz      loc_140007243
0x140007099  xor     edi, edi
0x14000709b  lea     r8, [rbp+FileNameInformation]; FileNameInformation
0x14000709f  mov     edx, 101h; NameOptions
0x1400070a4  mov     rcx, rbx; CallbackData
0x1400070a7  call    cs:__imp_FltGetFileNameInformation
0x1400070ae  nop     dword ptr [rax+rax+00h]
0x1400070b3  test    eax, eax
0x1400070b5  js      loc_140007243
0x1400070bb  mov     rcx, [rbp+FileNameInformation]; FileNameInformation
0x1400070bf  call    cs:__imp_FltParseFileNameInformation
0x1400070c6  nop     dword ptr [rax+rax+00h]
0x1400070cb  mov     rcx, [rbx+8]; Thread
0x1400070cf  mov     [rbp+P], 0
0x1400070d7  call    cs:__imp_IoThreadToProcess
0x1400070de  nop     dword ptr [rax+rax+00h]
0x1400070e3  mov     rcx, rax
0x1400070e6  mov     [rbp+Src], 0
0x1400070ee  mov     rbx, rax
0x1400070f1  mov     dword ptr [rbp+var_30], 0
0x1400070f8  mov     [rbp+var_10], 0
0x140007100  call    SmCheckProcessOrigin
0x140007105  lea     r8, [rbp+Src]
0x140007109  mov     rcx, rbx
0x14000710c  lea     rdx, [rbp+var_30]
0x140007110  mov     r14, rax
0x140007113  call    SmCheckProcessSessionOrigin
0x140007118  lea     r8, [rbp+P]
0x14000711c  mov     rcx, rbx
0x14000711f  lea     rdx, [rbp+NewContext]
0x140007123  call    SmCheckOrigin
0x140007128  cmp     byte ptr [rbp+NewContext], 0
0x14000712c  mov     rbx, [rbp+Src]
0x140007130  jnz     short loc_140007140
0x140007132  test    r14, r14
0x140007135  jnz     short loc_140007140
0x140007137  test    rbx, rbx
0x14000713a  jz      loc_1400071FE
0x140007140  mov     r8, [rbp+P]
0x140007144  lea     rax, [rbp+var_10]
0x140007148  mov     rdx, [r15+20h]; FileObject
0x14000714c  mov     r9, r14
0x14000714f  mov     rcx, [r15+18h]; Instance
0x140007153  mov     [rsp+70h+var_40], rax; __int64
0x140007158  mov     eax, dword ptr [rbp+var_30]
0x14000715b  mov     dword ptr [rsp+70h+Size], eax; Size
0x14000715f  mov     [rsp+70h+ReturnedContext], rbx; Src
0x140007164  call    SmpSetEaFromOrigin
0x140007169  test    eax, eax
0x14000716b  js      loc_1400071F6
0x140007171  mov     rcx, [r15+8]; Filter
0x140007175  lea     rax, [rbp+NewContext]
0x140007179  mov     edx, 10h; ContextType
0x14000717e  mov     [rbp+NewContext], 0
0x140007186  mov     r9d, 200h; PoolType
0x14000718c  mov     [rsp+70h+ReturnedContext], rax; ReturnedContext
0x140007191  lea     r8d, [rdx-8]; ContextSize
0x140007195  call    cs:__imp_FltAllocateContext
0x14000719c  nop     dword ptr [rax+rax+00h]
0x1400071a1  test    eax, eax
0x1400071a3  js      short loc_1400071F6
0x1400071a5  mov     rax, [rbp+NewContext]
0x1400071a9  xor     ecx, ecx
0x1400071ab  xor     r8d, r8d; Operation
0x1400071ae  mov     [rsp+70h+ReturnedContext], 0; OldContext
0x1400071b7  mov     [rax], rcx
0x1400071ba  mov     rax, [rbp+NewContext]
0x1400071be  mov     [rax], edi
0x1400071c0  mov     rax, [rbp+var_10]
0x1400071c4  mov     ecx, [rax+8]
0x1400071c7  mov     rax, [rbp+NewContext]
0x1400071cb  mov     [rax+4], ecx
0x1400071ce  mov     r9, [rbp+NewContext]; NewContext
0x1400071d2  mov     rdx, [r15+20h]; FileObject
0x1400071d6  mov     rcx, [r15+18h]; Instance
0x1400071da  call    cs:__imp_FltSetStreamHandleContext
0x1400071e1  nop     dword ptr [rax+rax+00h]
0x1400071e6  mov     rcx, [rbp+NewContext]; Context
0x1400071ea  call    cs:__imp_FltReleaseContext
0x1400071f1  nop     dword ptr [rax+rax+00h]
0x1400071f6  mov     rcx, r14
0x1400071f9  call    SmReleaseOriginProcessData
0x1400071fe  cmp     [rbp+P], 0
0x140007203  jz      short loc_14000721A
0x140007205  mov     rcx, [rbp+P]; P
0x140007209  mov     edx, 41746D73h; Tag
0x14000720e  call    cs:__imp_ExFreePoolWithTag
0x140007215  nop     dword ptr [rax+rax+00h]
0x14000721a  test    rbx, rbx
0x14000721d  jz      short loc_140007233
0x14000721f  mov     edx, 53746D73h; Tag
0x140007224  mov     rcx, rbx; P
0x140007227  call    cs:__imp_ExFreePoolWithTag
0x14000722e  nop     dword ptr [rax+rax+00h]
0x140007233  mov     rcx, [rbp+FileNameInformation]; FileNameInformation
0x140007237  call    cs:__imp_FltReleaseFileNameInformation
0x14000723e  nop     dword ptr [rax+rax+00h]
0x140007243  lea     r11, [rsp+70h+var_s0]
0x140007248  xor     eax, eax
0x14000724a  mov     rbx, [r11+28h]
0x14000724e  mov     rdi, [r11+30h]
0x140007252  mov     rsp, r11
0x140007255  pop     r15
0x140007257  pop     r14
0x140007259  pop     rbp
0x14000725a  retn
```
