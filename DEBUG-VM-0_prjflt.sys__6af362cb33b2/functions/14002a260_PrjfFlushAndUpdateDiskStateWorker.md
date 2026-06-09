# PrjfFlushAndUpdateDiskStateWorker

- ea: `0x14002a260`
- end: `0x14002a6ac`
- name: `PrjfFlushAndUpdateDiskStateWorker`
- size: `1100`
- prototype: `void __stdcall(PFLT_GENERIC_WORKITEM FltWorkItem, PVOID FltObject, PVOID Context)`
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140002b50`
- `0x1400066a4`
- `0x14000d754`
- `0x14000d960`
- `0x14002a260`
- `0x14002b3c0`
- `0x14002b888`
- `0x14003d2c8`
- `0x14003dd88`

## import_xrefs

- `ntoskrnl!ExReInitializeRundownProtection` at `0x14002a626`
- `ntoskrnl!ExReInitializeRundownProtection` at `0x14002a626`
- `ntoskrnl!ExRundownCompleted` at `0x14002a407`
- `ntoskrnl!ExRundownCompleted` at `0x14002a407`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14002a3f8`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14002a3f8`
- `ntoskrnl!KeClearEvent` at `0x14002a3e2`
- `ntoskrnl!KeClearEvent` at `0x14002a3e2`
- `ntoskrnl!KeSetEvent` at `0x14002a5e5`
- `ntoskrnl!KeSetEvent` at `0x14002a640`
- `ntoskrnl!KeSetEvent` at `0x14002a5e5`
- `ntoskrnl!KeSetEvent` at `0x14002a640`
- `ntoskrnl!ObfDereferenceObject` at `0x14002a5fa`
- `ntoskrnl!ObfDereferenceObject` at `0x14002a690`
- `ntoskrnl!ObfDereferenceObject` at `0x14002a5fa`
- `ntoskrnl!ObfDereferenceObject` at `0x14002a690`
- `FLTMGR!FltFlushBuffers2` at `0x14002a342`
- `FLTMGR!FltFlushBuffers2` at `0x14002a342`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14002a654`
- `FLTMGR!FltFreeGenericWorkItem` at `0x14002a654`
- `FLTMGR!FltClose` at `0x14002a60f`
- `FLTMGR!FltClose` at `0x14002a60f`
- `FLTMGR!FltReleaseContext` at `0x14002a668`
- `FLTMGR!FltReleaseContext` at `0x14002a67c`
- `FLTMGR!FltReleaseContext` at `0x14002a668`
- `FLTMGR!FltReleaseContext` at `0x14002a67c`

## pseudocode

```c
void __fastcall PrjfFlushAndUpdateDiskStateWorker(
        PFLT_GENERIC_WORKITEM FltWorkItem,
        struct _FLT_INSTANCE *FltObject,
        struct _FILE_OBJECT *Context)
{
  char v6; // bl
  char ContextFileObject; // al
  int v8; // edx
  int v9; // r8d
  char *v10; // rdi
  _QWORD *v11; // r15
  int v12; // edx
  int v13; // r8d
  int v14; // r9d
  int v15; // edx
  int v16; // r8d
  int v17; // r9d
  int v18; // ecx
  int v19; // edx
  int v20; // r8d
  int v21; // r9d
  int v22; // edx
  int v23; // r8d
  int v24; // r9d
  int v25; // [rsp+20h] [rbp-50h]
  HANDLE FileHandle; // [rsp+60h] [rbp-10h] BYREF
  PVOID Object; // [rsp+B0h] [rbp+40h] BYREF
  PFLT_CONTEXT Contexta; // [rsp+C0h] [rbp+50h]
  PFLT_CONTEXT v29; // [rsp+C8h] [rbp+58h]

  Contexta = 0;
  v29 = 0;
  FileHandle = 0;
  Object = 0;
  v6 = 0;
  ContextFileObject = PrjfGetContextFileObject(FltObject, Context);
  v10 = (char *)Contexta;
  v11 = v29;
  if ( ContextFileObject )
  {
    v14 = FltFlushBuffers2(FltObject, Context, 2);
    if ( v14 >= 0 )
    {
      KeClearEvent((PRKEVENT)v10 + 13);
      ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)v10 + 42);
      ExRundownCompleted((PEX_RUNDOWN_REF)v10 + 42);
      v6 = 1;
      v17 = PrjfReopenFile(FltObject, Context, 0x100u, &FileHandle, (PFILE_OBJECT *)&Object);
      if ( v17 >= 0 )
      {
        v18 = *(_DWORD *)(*((_QWORD *)v10 + 11) + 4LL);
        if ( v18 == 3 )
        {
          v21 = PrjfRemoveSparse(FltObject, (PFILE_OBJECT)Object);
          if ( v21 >= 0 )
          {
            v24 = PrjfUntagFile(FltObject, (PFILE_OBJECT)Object);
            if ( v24 < 0
              && ((BYTE1(xmmword_14001A3D0) & 4) != 0
               || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED) )
            {
              LOBYTE(v22) = BYTE1(xmmword_14001A3D0) & 4;
              LOBYTE(v23) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
              WPP_RECORDER_AND_TRACE_SF_sDdZ(
                522,
                v22,
                v23,
                *((_QWORD *)WPP_GLOBAL_Control + 8),
                2,
                10,
                21,
                (__int64)WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids,
                (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\expansion.c",
                37,
                v24,
                (__int64)Object + 88);
            }
          }
          else if ( (BYTE1(xmmword_14001A3D0) & 4) != 0
                 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            LOBYTE(v19) = BYTE1(xmmword_14001A3D0) & 4;
            LOBYTE(v20) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            WPP_RECORDER_AND_TRACE_SF_sDdZ(
              522,
              v19,
              v20,
              *((_QWORD *)WPP_GLOBAL_Control + 8),
              2,
              10,
              20,
              (__int64)WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids,
              (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\expansion.c",
              20,
              v21,
              (__int64)Object + 88);
          }
        }
        else if ( v18 == 2 && (int)PrjfClearAttributes((PFILE_OBJECT)Object, FltObject) >= 0 )
        {
          LOBYTE(v25) = 0;
          PrjfSetPlaceHolderFlags(FltObject, Object, v11[1], 32, v25);
        }
      }
      else if ( (BYTE1(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v15) = BYTE1(xmmword_14001A3D0) & 4;
        LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDdZ(
          522,
          v15,
          v16,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          2,
          10,
          19,
          (__int64)WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\expansion.c",
          4,
          v17,
          (__int64)&Context->FileName);
      }
    }
    else if ( (BYTE1(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = BYTE1(xmmword_14001A3D0) & 4;
      LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDdZ(
        522,
        v12,
        v13,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        10,
        18,
        (__int64)WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\expansion.c",
        231,
        v14,
        (__int64)&Context->FileName);
    }
  }
  else if ( (BYTE1(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v8) = BYTE1(xmmword_14001A3D0) & 4;
    LOBYTE(v9) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDq(
      522,
      v8,
      v9,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      10,
      17,
      (__int64)WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\expansion.c",
      211,
      (char)Context);
  }
  if ( v10 )
    KeSetEvent((PRKEVENT)(v10 + 344), 0, 0);
  if ( Object )
    ObfDereferenceObject(Object);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( v6 )
  {
    ExReInitializeRundownProtection((PEX_RUNDOWN_REF)v10 + 42);
    KeSetEvent((PRKEVENT)v10 + 13, 1, 0);
  }
  if ( FltWorkItem )
    FltFreeGenericWorkItem(FltWorkItem);
  if ( v10 )
    FltReleaseContext(v10);
  if ( v11 )
    FltReleaseContext(v11);
  if ( Context )
    ObfDereferenceObject(Context);
}

```

## disassembly

```asm
0x14002a260  push    rbp
0x14002a262  push    rbx
0x14002a263  push    rsi
0x14002a264  push    rdi
0x14002a265  push    r12
0x14002a267  push    r14
0x14002a269  push    r15
0x14002a26b  mov     rbp, rsp
0x14002a26e  sub     rsp, 70h
0x14002a272  mov     r14, r8
0x14002a275  mov     [rbp+Context], 0
0x14002a27d  mov     rsi, rdx
0x14002a280  mov     [rbp+arg_18], 0
0x14002a288  mov     r12, rcx
0x14002a28b  mov     [rbp+FileHandle], 0
0x14002a293  mov     rdx, r14; FileObject
0x14002a296  mov     [rbp+Object], 0
0x14002a29e  mov     rcx, rsi; Instance
0x14002a2a1  lea     r9, [rbp+arg_18]
0x14002a2a5  lea     r8, [rbp+Context]
0x14002a2a9  xor     bl, bl
0x14002a2ab  call    PrjfGetContextFileObject
0x14002a2b0  mov     rdi, [rbp+Context]
0x14002a2b4  mov     r15, [rbp+arg_18]
0x14002a2b8  test    al, al
0x14002a2ba  jnz     short loc_14002A335
0x14002a2bc  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14002a2c2  lea     rax, WPP_RECORDER_INITIALIZED
0x14002a2c9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002a2d0  setnz   r8b
0x14002a2d4  and     dl, 4
0x14002a2d7  jnz     short loc_14002A2E2
0x14002a2d9  test    r8b, r8b
0x14002a2dc  jz      loc_14002A5D4
0x14002a2e2  mov     r9, cs:WPP_GLOBAL_Control
0x14002a2e9  lea     rax, aOnecoreBaseFsG_10; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002a2f0  mov     [rsp+70h+var_20], r14
0x14002a2f5  mov     ecx, 20Ah
0x14002a2fa  mov     [rsp+70h+var_28], 3D3h
0x14002a302  mov     [rsp+70h+var_30], rax
0x14002a307  lea     rax, WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids
0x14002a30e  mov     r9, [r9+40h]
0x14002a312  mov     [rsp+70h+var_38], rax
0x14002a317  mov     [rsp+70h+var_40], 11h
0x14002a31e  mov     [rsp+70h+var_48], 0Ah
0x14002a326  mov     byte ptr [rsp+70h+var_50], 2
0x14002a32b  call    WPP_RECORDER_AND_TRACE_SF_sDq
0x14002a330  jmp     loc_14002A5D4
0x14002a335  xor     r9d, r9d
0x14002a338  mov     rdx, r14
0x14002a33b  mov     rcx, rsi
0x14002a33e  lea     r8d, [r9+2]
0x14002a342  call    cs:__imp_FltFlushBuffers2
0x14002a349  nop     dword ptr [rax+rax+00h]
0x14002a34e  mov     r9d, eax
0x14002a351  test    eax, eax
0x14002a353  jns     loc_14002A3DB
0x14002a359  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14002a35f  lea     rax, WPP_RECORDER_INITIALIZED
0x14002a366  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002a36d  setnz   r8b
0x14002a371  and     dl, 4
0x14002a374  jnz     short loc_14002A37F
0x14002a376  test    r8b, r8b
0x14002a379  jz      loc_14002A5D4
0x14002a37f  lea     rax, [r14+58h]
0x14002a383  mov     [rsp+70h+var_18], rax
0x14002a388  lea     rax, aOnecoreBaseFsG_10; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002a38f  mov     dword ptr [rsp+70h+var_20], r9d
0x14002a394  mov     [rsp+70h+var_28], 3E7h
0x14002a39c  mov     [rsp+70h+var_30], rax
0x14002a3a1  lea     rax, WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids
0x14002a3a8  mov     [rsp+70h+var_38], rax
0x14002a3ad  mov     [rsp+70h+var_40], 12h
0x14002a3b4  mov     r9, cs:WPP_GLOBAL_Control
0x14002a3bb  mov     ecx, 20Ah
0x14002a3c0  mov     [rsp+70h+var_48], 0Ah
0x14002a3c8  mov     byte ptr [rsp+70h+var_50], 2
0x14002a3cd  mov     r9, [r9+40h]
0x14002a3d1  call    WPP_RECORDER_AND_TRACE_SF_sDdZ
0x14002a3d6  jmp     loc_14002A5D4
0x14002a3db  lea     rcx, [rdi+138h]; Event
0x14002a3e2  call    cs:__imp_KeClearEvent
0x14002a3e9  nop     dword ptr [rax+rax+00h]
0x14002a3ee  lea     rbx, [rdi+150h]
0x14002a3f5  mov     rcx, rbx; RunRef
0x14002a3f8  call    cs:__imp_ExWaitForRundownProtectionRelease
0x14002a3ff  nop     dword ptr [rax+rax+00h]
0x14002a404  mov     rcx, rbx; RunRef
0x14002a407  call    cs:__imp_ExRundownCompleted
0x14002a40e  nop     dword ptr [rax+rax+00h]
0x14002a413  lea     rax, [rbp+Object]
0x14002a417  mov     r8d, 100h; DesiredAccess
0x14002a41d  lea     r9, [rbp+FileHandle]; FileHandle
0x14002a421  mov     [rsp+70h+var_50], rax; PFILE_OBJECT *
0x14002a426  mov     rdx, r14; FileObject
0x14002a429  mov     rcx, rsi; Instance
0x14002a42c  mov     bl, 1
0x14002a42e  call    PrjfReopenFile
0x14002a433  mov     r9d, eax
0x14002a436  test    eax, eax
0x14002a438  jns     short loc_14002A49A
0x14002a43a  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14002a440  lea     rax, WPP_RECORDER_INITIALIZED
0x14002a447  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002a44e  setnz   r8b
0x14002a452  and     dl, 4
0x14002a455  jnz     short loc_14002A460
0x14002a457  test    r8b, r8b
0x14002a45a  jz      loc_14002A5D4
0x14002a460  lea     rax, [r14+58h]
0x14002a464  mov     [rsp+70h+var_18], rax
0x14002a469  lea     rax, aOnecoreBaseFsG_10; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002a470  mov     dword ptr [rsp+70h+var_20], r9d
0x14002a475  mov     [rsp+70h+var_28], 404h
0x14002a47d  mov     [rsp+70h+var_30], rax
0x14002a482  lea     rax, WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids
0x14002a489  mov     [rsp+70h+var_38], rax
0x14002a48e  mov     [rsp+70h+var_40], 13h
0x14002a495  jmp     loc_14002A3B4
0x14002a49a  mov     rax, [rdi+58h]
0x14002a49e  mov     ecx, [rax+4]
0x14002a4a1  cmp     ecx, 3
0x14002a4a4  jnz     loc_14002A59E
0x14002a4aa  mov     rdx, [rbp+Object]; FileObject
0x14002a4ae  mov     r8, r15
0x14002a4b1  mov     rcx, rsi; Instance
0x14002a4b4  call    PrjfRemoveSparse
0x14002a4b9  mov     r9d, eax
0x14002a4bc  test    eax, eax
0x14002a4be  jns     short loc_14002A524
0x14002a4c0  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14002a4c6  lea     rax, WPP_RECORDER_INITIALIZED
0x14002a4cd  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002a4d4  setnz   r8b
0x14002a4d8  and     dl, 4
0x14002a4db  jnz     short loc_14002A4E6
0x14002a4dd  test    r8b, r8b
0x14002a4e0  jz      loc_14002A5D4
0x14002a4e6  mov     rax, [rbp+Object]
0x14002a4ea  add     rax, 58h ; 'X'
0x14002a4ee  mov     [rsp+70h+var_18], rax
0x14002a4f3  lea     rax, aOnecoreBaseFsG_10; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002a4fa  mov     dword ptr [rsp+70h+var_20], r9d
0x14002a4ff  mov     [rsp+70h+var_28], 414h
0x14002a507  mov     [rsp+70h+var_30], rax
0x14002a50c  lea     rax, WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids
0x14002a513  mov     [rsp+70h+var_38], rax
0x14002a518  mov     [rsp+70h+var_40], 14h
0x14002a51f  jmp     loc_14002A3B4
0x14002a524  mov     rdx, [rbp+Object]; FileObject
0x14002a528  mov     r8, r15
0x14002a52b  mov     rcx, rsi; Instance
0x14002a52e  call    PrjfUntagFile
0x14002a533  mov     r9d, eax
0x14002a536  test    eax, eax
0x14002a538  jns     loc_14002A5D4
0x14002a53e  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14002a544  lea     rax, WPP_RECORDER_INITIALIZED
0x14002a54b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002a552  setnz   r8b
0x14002a556  and     dl, 4
0x14002a559  jnz     short loc_14002A560
0x14002a55b  test    r8b, r8b
0x14002a55e  jz      short loc_14002A5D4
0x14002a560  mov     rax, [rbp+Object]
0x14002a564  add     rax, 58h ; 'X'
0x14002a568  mov     [rsp+70h+var_18], rax
0x14002a56d  lea     rax, aOnecoreBaseFsG_10; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14002a574  mov     dword ptr [rsp+70h+var_20], r9d
0x14002a579  mov     [rsp+70h+var_28], 425h
0x14002a581  mov     [rsp+70h+var_30], rax
0x14002a586  lea     rax, WPP_f6f932a41f663696b98ce9faa74178e4_Traceguids
0x14002a58d  mov     [rsp+70h+var_38], rax
0x14002a592  mov     [rsp+70h+var_40], 15h
0x14002a599  jmp     loc_14002A3B4
0x14002a59e  cmp     ecx, 2
0x14002a5a1  jnz     short loc_14002A5D4
0x14002a5a3  mov     rcx, [rbp+Object]; FileObject
0x14002a5a7  mov     r8d, 400000h
0x14002a5ad  mov     rdx, rsi; Instance
0x14002a5b0  call    PrjfClearAttributes
0x14002a5b5  test    eax, eax
0x14002a5b7  js      short loc_14002A5D4
0x14002a5b9  mov     r8, [r15+8]
0x14002a5bd  mov     r9d, 20h ; ' '
0x14002a5c3  mov     rdx, [rbp+Object]
0x14002a5c7  mov     rcx, rsi
0x14002a5ca  mov     byte ptr [rsp+70h+var_50], 0
0x14002a5cf  call    PrjfSetPlaceHolderFlags
0x14002a5d4  test    rdi, rdi
0x14002a5d7  jz      short loc_14002A5F1
0x14002a5d9  lea     rcx, [rdi+158h]; Event
0x14002a5e0  xor     r8d, r8d; Wait
0x14002a5e3  xor     edx, edx; Increment
0x14002a5e5  call    cs:__imp_KeSetEvent
0x14002a5ec  nop     dword ptr [rax+rax+00h]
0x14002a5f1  mov     rcx, [rbp+Object]; Object
0x14002a5f5  test    rcx, rcx
0x14002a5f8  jz      short loc_14002A606
0x14002a5fa  call    cs:__imp_ObfDereferenceObject
0x14002a601  nop     dword ptr [rax+rax+00h]
0x14002a606  mov     rcx, [rbp+FileHandle]; FileHandle
0x14002a60a  test    rcx, rcx
0x14002a60d  jz      short loc_14002A61B
0x14002a60f  call    cs:__imp_FltClose
0x14002a616  nop     dword ptr [rax+rax+00h]
0x14002a61b  test    bl, bl
0x14002a61d  jz      short loc_14002A64C
0x14002a61f  lea     rcx, [rdi+150h]; RunRef
0x14002a626  call    cs:__imp_ExReInitializeRundownProtection
0x14002a62d  nop     dword ptr [rax+rax+00h]
0x14002a632  xor     r8d, r8d; Wait
0x14002a635  lea     rcx, [rdi+138h]; Event
0x14002a63c  lea     edx, [r8+1]; Increment
0x14002a640  call    cs:__imp_KeSetEvent
0x14002a647  nop     dword ptr [rax+rax+00h]
0x14002a64c  test    r12, r12
0x14002a64f  jz      short loc_14002A660
0x14002a651  mov     rcx, r12; FltWorkItem
0x14002a654  call    cs:__imp_FltFreeGenericWorkItem
0x14002a65b  nop     dword ptr [rax+rax+00h]
0x14002a660  test    rdi, rdi
0x14002a663  jz      short loc_14002A674
0x14002a665  mov     rcx, rdi; Context
0x14002a668  call    cs:__imp_FltReleaseContext
0x14002a66f  nop     dword ptr [rax+rax+00h]
0x14002a674  test    r15, r15
0x14002a677  jz      short loc_14002A688
0x14002a679  mov     rcx, r15; Context
0x14002a67c  call    cs:__imp_FltReleaseContext
0x14002a683  nop     dword ptr [rax+rax+00h]
0x14002a688  test    r14, r14
0x14002a68b  jz      short loc_14002A69C
0x14002a68d  mov     rcx, r14; Object
0x14002a690  call    cs:__imp_ObfDereferenceObject
0x14002a697  nop     dword ptr [rax+rax+00h]
0x14002a69c  add     rsp, 70h
0x14002a6a0  pop     r15
0x14002a6a2  pop     r14
0x14002a6a4  pop     r12
0x14002a6a6  pop     rdi
0x14002a6a7  pop     rsi
0x14002a6a8  pop     rbx
0x14002a6a9  pop     rbp
0x14002a6aa  retn
```
