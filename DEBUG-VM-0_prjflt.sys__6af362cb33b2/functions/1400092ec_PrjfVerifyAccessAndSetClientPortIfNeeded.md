# PrjfVerifyAccessAndSetClientPortIfNeeded

- ea: `0x1400092ec`
- end: `0x140009871`
- name: `PrjfVerifyAccessAndSetClientPortIfNeeded`
- size: `1413`
- prototype: `__int64 __usercall@<rax>(PFLT_INSTANCE Instance@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400311b0`

## callees

- `0x1400092ec`
- `0x14000d008`
- `0x14000d128`
- `0x14000d5e8`

## import_xrefs

- `ntoskrnl!ExReleaseFastMutex` at `0x14000945b`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400094c6`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000945b`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400094c6`
- `ntoskrnl!ExAcquireFastMutex` at `0x140009443`
- `ntoskrnl!ExAcquireFastMutex` at `0x140009443`
- `ntoskrnl!ObfReferenceObject` at `0x1400097f5`
- `ntoskrnl!ObfReferenceObject` at `0x1400097f5`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400097e2`
- `ntoskrnl!IoGetCurrentProcess` at `0x1400097e2`
- `FLTMGR!FltCreateFileEx2` at `0x140009687`
- `FLTMGR!FltCreateFileEx2` at `0x140009687`
- `FLTMGR!FltClose` at `0x1400095be`
- `FLTMGR!FltClose` at `0x1400095be`
- `FLTMGR!FltAcquireResourceExclusive` at `0x1400094da`
- `FLTMGR!FltAcquireResourceExclusive` at `0x1400094da`
- `FLTMGR!FltReleaseResource` at `0x140009594`
- `FLTMGR!FltReleaseResource` at `0x140009594`
- `FLTMGR!FltGetInstanceContext` at `0x140009326`
- `FLTMGR!FltGetInstanceContext` at `0x140009326`
- `FLTMGR!FltReleaseContext` at `0x1400095a9`
- `FLTMGR!FltReleaseContext` at `0x1400095a9`

## pseudocode

```c
__int64 __fastcall PrjfVerifyAccessAndSetClientPortIfNeeded(
        PFLT_INSTANCE Instance,
        _QWORD *a2,
        __int64 a3,
        int a4,
        char **a5)
{
  NTSTATUS InstanceContext; // eax
  int v10; // edx
  int v11; // r8d
  NTSTATUS v12; // ebx
  int v13; // ecx
  int v14; // edx
  int v15; // r8d
  int v16; // r8d
  char *v17; // rdx
  char *i; // rcx
  char *v19; // rdi
  PEPROCESS CurrentProcess; // rax
  __int16 IoStatusBlock; // [rsp+30h] [rbp-91h]
  char ShareAccess; // [rsp+48h] [rbp-79h]
  char CreateDisposition; // [rsp+50h] [rbp-71h]
  PFLT_CONTEXT Context; // [rsp+80h] [rbp-41h] BYREF
  HANDLE FileHandle; // [rsp+88h] [rbp-39h] BYREF
  struct _IO_STATUS_BLOCK v27; // [rsp+90h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-21h] BYREF

  Context = 0;
  FileHandle = 0;
  *a5 = 0;
  InstanceContext = FltGetInstanceContext(Instance, &Context);
  v12 = InstanceContext;
  if ( InstanceContext < 0 )
  {
    if ( (BYTE1(xmmword_14001A3D0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = BYTE1(xmmword_14001A3D0) & 8;
      LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        523,
        v10,
        v11,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        11,
        10,
        (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
        111,
        InstanceContext);
    }
    goto LABEL_25;
  }
  v13 = *((_DWORD *)Context + 6);
  if ( v13 != 2 && v13 != 28 )
  {
    v12 = -1073741637;
    if ( (BYTE1(xmmword_14001A3D0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v10) = BYTE1(xmmword_14001A3D0) & 8;
      LOBYTE(v11) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(
        523,
        v10,
        v11,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        11,
        11,
        (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
        118);
    }
    goto LABEL_25;
  }
  ExAcquireFastMutex(&FastMutex);
  if ( !byte_14001A580 )
  {
    ExReleaseFastMutex(&FastMutex);
    FltAcquireResourceExclusive((PERESOURCE)((char *)Context + 48));
    v17 = (char *)Context + 152;
    for ( i = (char *)*((_QWORD *)Context + 19); ; i = *(char **)i )
    {
      if ( i == v17 )
        goto LABEL_20;
      v19 = i - 16;
      if ( *a2 == *((_QWORD *)i - 2) && a2[1] == *((_QWORD *)v19 + 1) )
        break;
    }
    if ( i != (char *)16 )
    {
      ObjectAttributes.RootDirectory = 0;
      *(_QWORD *)&ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)(v19 + 40);
      *(_QWORD *)&ObjectAttributes.Attributes = 576;
      v27 = 0;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v12 = FltCreateFileEx2(
              Globals,
              Instance,
              &FileHandle,
              0,
              3u,
              &ObjectAttributes,
              &v27,
              0,
              0,
              7u,
              1u,
              0x200029u,
              0,
              0,
              1u,
              0);
      if ( v12 < 0 )
      {
        if ( (BYTE1(xmmword_14001A3D0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v17) = BYTE1(xmmword_14001A3D0) & 8;
          LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sDdd(523, (_DWORD)v17, v16, *((_QWORD *)WPP_GLOBAL_Control + 8));
        }
        goto LABEL_24;
      }
      if ( !a4 )
      {
        if ( *((_QWORD *)v19 + 10) )
        {
          v12 = -1073740024;
          LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          LOBYTE(v17) = BYTE1(xmmword_14001A3D0) & 8;
          if ( (BYTE1(xmmword_14001A3D0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            CreateDisposition = 8;
            ShareAccess = -38;
            IoStatusBlock = 15;
            goto LABEL_23;
          }
          goto LABEL_24;
        }
        if ( *((_QWORD *)v19 + 4) )
        {
          v12 = -1073740024;
          LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          LOBYTE(v17) = BYTE1(xmmword_14001A3D0) & 8;
          if ( (BYTE1(xmmword_14001A3D0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            CreateDisposition = 8;
            ShareAccess = -26;
            IoStatusBlock = 16;
            goto LABEL_23;
          }
          goto LABEL_24;
        }
        CurrentProcess = IoGetCurrentProcess();
        *((_QWORD *)v19 + 4) = CurrentProcess;
        ObfReferenceObject(CurrentProcess);
        *((_QWORD *)v19 + 10) = a3;
        *a5 = v19;
      }
      if ( (BYTE1(xmmword_14001A3E0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v17) = BYTE1(xmmword_14001A3E0) & 8;
        LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sDL(
          1035,
          (_DWORD)v17,
          v16,
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          4,
          11,
          17,
          (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
          (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
          248,
          a4);
      }
      goto LABEL_24;
    }
LABEL_20:
    v12 = -1073689087;
    LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    LOBYTE(v17) = BYTE1(xmmword_14001A3D0) & 8;
    if ( (BYTE1(xmmword_14001A3D0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      CreateDisposition = 1;
      ShareAccess = -97;
      IoStatusBlock = 13;
LABEL_23:
      WPP_RECORDER_AND_TRACE_SF_sDL(
        523,
        (_DWORD)v17,
        v16,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        2,
        11,
        IoStatusBlock,
        (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
        ShareAccess,
        CreateDisposition);
    }
LABEL_24:
    FltReleaseResource((PERESOURCE)((char *)Context + 48));
    goto LABEL_25;
  }
  ExReleaseFastMutex(&FastMutex);
  v12 = -1073741637;
  if ( (BYTE1(xmmword_14001A3D0) & 8) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v14) = BYTE1(xmmword_14001A3D0) & 8;
    LOBYTE(v15) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sD(
      523,
      v14,
      v15,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      2,
      11,
      12,
      (__int64)WPP_f518d8db80f83e9c1a62003295e898de_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\utils.c",
      128);
  }
LABEL_25:
  if ( Context )
    FltReleaseContext(Context);
  if ( FileHandle )
    FltClose(FileHandle);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1400092ec  push    rbp
0x1400092ee  push    rbx
0x1400092ef  push    rsi
0x1400092f0  push    rdi
0x1400092f1  push    r12
0x1400092f3  push    r13
0x1400092f5  push    r14
0x1400092f7  push    r15
0x1400092f9  lea     rbp, [rsp-17h]
0x1400092fe  sub     rsp, 0D8h
0x140009305  mov     r15, [rbp+4Fh+arg_20]
0x140009309  xor     edi, edi
0x14000930b  mov     rsi, rdx
0x14000930e  mov     [rbp+4Fh+Context], rdi
0x140009312  lea     rdx, [rbp+4Fh+Context]; Context
0x140009316  mov     [rbp+4Fh+FileHandle], rdi
0x14000931a  mov     r14d, r9d
0x14000931d  mov     r13, r8
0x140009320  mov     [r15], rdi
0x140009323  mov     r12, rcx
0x140009326  call    cs:__imp_FltGetInstanceContext
0x14000932d  nop     dword ptr [rax+rax+00h]
0x140009332  mov     ebx, eax
0x140009334  test    eax, eax
0x140009336  jns     short loc_1400093B0
0x140009338  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14000933e  lea     rcx, WPP_RECORDER_INITIALIZED
0x140009345  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14000934c  setnz   r8b
0x140009350  and     dl, 8
0x140009353  jnz     short loc_14000935E
0x140009355  test    r8b, r8b
0x140009358  jz      loc_1400095A0
0x14000935e  mov     dword ptr [rsp+110h+CreateDisposition], eax
0x140009362  lea     r9, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140009369  mov     dword ptr [rsp+110h+ShareAccess], 16Fh
0x140009371  mov     ecx, 20Bh
0x140009376  mov     qword ptr [rsp+110h+FileAttributes], r9
0x14000937b  lea     r9, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140009382  mov     [rsp+110h+AllocationSize], r9
0x140009387  mov     r9, cs:WPP_GLOBAL_Control
0x14000938e  mov     word ptr [rsp+110h+IoStatusBlock], 0Ah
0x140009395  mov     dword ptr [rsp+110h+ObjectAttributes], 0Bh
0x14000939d  mov     byte ptr [rsp+110h+DesiredAccess], 2
0x1400093a2  mov     r9, [r9+40h]
0x1400093a6  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x1400093ab  jmp     loc_1400095A0
0x1400093b0  mov     rax, [rbp+4Fh+Context]
0x1400093b4  mov     ecx, [rax+18h]
0x1400093b7  cmp     ecx, 2
0x1400093ba  jz      short loc_140009439
0x1400093bc  cmp     ecx, 1Ch
0x1400093bf  jz      short loc_140009439
0x1400093c1  mov     ebx, 0C00000BBh
0x1400093c6  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x1400093cc  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400093d3  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400093da  setnz   r8b
0x1400093de  and     dl, 8
0x1400093e1  jnz     short loc_1400093EC
0x1400093e3  test    r8b, r8b
0x1400093e6  jz      loc_1400095A0
0x1400093ec  mov     dword ptr [rsp+110h+ShareAccess], 176h
0x1400093f4  lea     r9, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400093fb  mov     qword ptr [rsp+110h+FileAttributes], r9
0x140009400  mov     eax, 0Bh
0x140009405  lea     r9, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14000940c  mov     [rsp+110h+AllocationSize], r9
0x140009411  mov     word ptr [rsp+110h+IoStatusBlock], ax
0x140009416  mov     dword ptr [rsp+110h+ObjectAttributes], eax
0x14000941a  mov     r9, cs:WPP_GLOBAL_Control
0x140009421  mov     ecx, 20Bh
0x140009426  mov     byte ptr [rsp+110h+DesiredAccess], 2
0x14000942b  mov     r9, [r9+40h]
0x14000942f  call    WPP_RECORDER_AND_TRACE_SF_sD
0x140009434  jmp     loc_1400095A0
0x140009439  lea     rbx, FastMutex
0x140009440  mov     rcx, rbx; FastMutex
0x140009443  call    cs:__imp_ExAcquireFastMutex
0x14000944a  nop     dword ptr [rax+rax+00h]
0x14000944f  cmp     cs:byte_14001A580, dil
0x140009456  mov     rcx, rbx; FastMutex
0x140009459  jz      short loc_1400094C6
0x14000945b  call    cs:__imp_ExReleaseFastMutex
0x140009462  nop     dword ptr [rax+rax+00h]
0x140009467  mov     ebx, 0C00000BBh
0x14000946c  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140009472  lea     rcx, WPP_RECORDER_INITIALIZED
0x140009479  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140009480  setnz   r8b
0x140009484  and     dl, 8
0x140009487  jnz     short loc_140009492
0x140009489  test    r8b, r8b
0x14000948c  jz      loc_1400095A0
0x140009492  mov     dword ptr [rsp+110h+ShareAccess], 180h
0x14000949a  lea     r9, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400094a1  mov     qword ptr [rsp+110h+FileAttributes], r9
0x1400094a6  lea     r9, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x1400094ad  mov     [rsp+110h+AllocationSize], r9
0x1400094b2  mov     word ptr [rsp+110h+IoStatusBlock], 0Ch
0x1400094b9  mov     dword ptr [rsp+110h+ObjectAttributes], 0Bh
0x1400094c1  jmp     loc_14000941A
0x1400094c6  call    cs:__imp_ExReleaseFastMutex
0x1400094cd  nop     dword ptr [rax+rax+00h]
0x1400094d2  mov     rcx, [rbp+4Fh+Context]
0x1400094d6  add     rcx, 30h ; '0'; Resource
0x1400094da  call    cs:__imp_FltAcquireResourceExclusive
0x1400094e1  nop     dword ptr [rax+rax+00h]
0x1400094e6  mov     rdx, [rbp+4Fh+Context]
0x1400094ea  add     rdx, 98h
0x1400094f1  mov     rcx, [rdx]
0x1400094f4  jmp     short loc_140009513
0x1400094f6  mov     rax, [rsi]
0x1400094f9  lea     rdi, [rcx-10h]
0x1400094fd  cmp     rax, [rdi]
0x140009500  jnz     short loc_140009510
0x140009502  mov     rax, [rsi+8]
0x140009506  cmp     rax, [rdi+8]
0x14000950a  jz      loc_1400095E1
0x140009510  mov     rcx, [rcx]
0x140009513  cmp     rcx, rdx
0x140009516  jnz     short loc_1400094F6
0x140009518  mov     ebx, 0C000CE01h
0x14000951d  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140009523  lea     rcx, WPP_RECORDER_INITIALIZED
0x14000952a  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140009531  setnz   r8b
0x140009535  and     dl, 8
0x140009538  jnz     short loc_14000953F
0x14000953a  test    r8b, r8b
0x14000953d  jz      short loc_14000958C
0x14000953f  mov     dword ptr [rsp+110h+CreateDisposition], ebx
0x140009543  lea     r9, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14000954a  mov     dword ptr [rsp+110h+ShareAccess], 19Fh
0x140009552  mov     qword ptr [rsp+110h+FileAttributes], r9
0x140009557  lea     r9, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14000955e  mov     [rsp+110h+AllocationSize], r9
0x140009563  mov     word ptr [rsp+110h+IoStatusBlock], 0Dh
0x14000956a  mov     dword ptr [rsp+110h+ObjectAttributes], 0Bh
0x140009572  mov     ecx, 20Bh
0x140009577  mov     byte ptr [rsp+110h+DesiredAccess], 2
0x14000957c  mov     r9, cs:WPP_GLOBAL_Control
0x140009583  mov     r9, [r9+40h]
0x140009587  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x14000958c  mov     rcx, [rbp+4Fh+Context]
0x140009590  add     rcx, 30h ; '0'; Resource
0x140009594  call    cs:__imp_FltReleaseResource
0x14000959b  nop     dword ptr [rax+rax+00h]
0x1400095a0  mov     rcx, [rbp+4Fh+Context]; Context
0x1400095a4  test    rcx, rcx
0x1400095a7  jz      short loc_1400095B5
0x1400095a9  call    cs:__imp_FltReleaseContext
0x1400095b0  nop     dword ptr [rax+rax+00h]
0x1400095b5  mov     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x1400095b9  test    rcx, rcx
0x1400095bc  jz      short loc_1400095CA
0x1400095be  call    cs:__imp_FltClose
0x1400095c5  nop     dword ptr [rax+rax+00h]
0x1400095ca  mov     eax, ebx
0x1400095cc  add     rsp, 0D8h
0x1400095d3  pop     r15
0x1400095d5  pop     r14
0x1400095d7  pop     r13
0x1400095d9  pop     r12
0x1400095db  pop     rdi
0x1400095dc  pop     rsi
0x1400095dd  pop     rbx
0x1400095de  pop     rbp
0x1400095df  retn
0x1400095e1  test    rdi, rdi
0x1400095e4  jz      loc_140009518
0x1400095ea  mov     rcx, cs:Globals; Filter
0x1400095f1  lea     r8, [rbp+4Fh+FileHandle]; FileHandle
0x1400095f5  mov     [rsp+110h+DriverContext], 0; DriverContext
0x1400095fe  xor     eax, eax
0x140009600  mov     [rbp+4Fh+var_70.RootDirectory], rax
0x140009604  xorps   xmm0, xmm0
0x140009607  lea     rax, [rdi+28h]
0x14000960b  mov     qword ptr [rbp+4Fh+var_70.Length], 30h ; '0'
0x140009613  mov     [rbp+4Fh+var_70.ObjectName], rax
0x140009617  xor     r9d, r9d; FileObject
0x14000961a  mov     eax, 1
0x14000961f  mov     qword ptr [rbp+4Fh+var_70.Attributes], 240h
0x140009627  mov     [rsp+110h+Flags], eax; Flags
0x14000962b  mov     rdx, r12; Instance
0x14000962e  mov     [rsp+110h+EaLength], 0; EaLength
0x140009636  mov     [rsp+110h+EaBuffer], 0; EaBuffer
0x14000963f  mov     [rsp+110h+CreateOptions], 200029h; CreateOptions
0x140009647  mov     dword ptr [rsp+110h+CreateDisposition], eax; CreateDisposition
0x14000964b  lea     rax, [rbp+4Fh+var_80]
0x14000964f  mov     dword ptr [rsp+110h+ShareAccess], 7; ShareAccess
0x140009657  mov     [rsp+110h+FileAttributes], 0; FileAttributes
0x14000965f  mov     [rsp+110h+AllocationSize], 0; AllocationSize
0x140009668  mov     [rsp+110h+IoStatusBlock], rax; IoStatusBlock
0x14000966d  lea     rax, [rbp+4Fh+var_70]
0x140009671  mov     [rsp+110h+ObjectAttributes], rax; ObjectAttributes
0x140009676  mov     [rsp+110h+DesiredAccess], 3; DesiredAccess
0x14000967e  movups  xmmword ptr [rbp+4Fh+var_80], xmm0
0x140009682  movdqu  xmmword ptr [rbp+4Fh+var_70.SecurityDescriptor], xmm0
0x140009687  call    cs:__imp_FltCreateFileEx2
0x14000968e  nop     dword ptr [rax+rax+00h]
0x140009693  mov     ebx, eax
0x140009695  test    eax, eax
0x140009697  jns     short loc_140009711
0x140009699  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14000969f  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400096a6  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400096ad  setnz   r8b
0x1400096b1  and     dl, 8
0x1400096b4  jnz     short loc_1400096BF
0x1400096b6  test    r8b, r8b
0x1400096b9  jz      loc_14000958C
0x1400096bf  mov     [rsp+110h+CreateOptions], r14d
0x1400096c4  lea     r9, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400096cb  mov     dword ptr [rsp+110h+CreateDisposition], eax
0x1400096cf  mov     ecx, 20Bh
0x1400096d4  mov     dword ptr [rsp+110h+ShareAccess], 1CCh
0x1400096dc  mov     qword ptr [rsp+110h+FileAttributes], r9
0x1400096e1  lea     r9, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x1400096e8  mov     [rsp+110h+AllocationSize], r9
0x1400096ed  mov     r9, cs:WPP_GLOBAL_Control
0x1400096f4  mov     word ptr [rsp+110h+IoStatusBlock], 0Eh
0x1400096fb  mov     dword ptr [rsp+110h+ObjectAttributes], 0Bh
0x140009703  mov     r9, [r9+40h]
0x140009707  call    WPP_RECORDER_AND_TRACE_SF_sDdd
0x14000970c  jmp     loc_14000958C
0x140009711  test    r14d, r14d
0x140009714  jnz     loc_140009808
0x14000971a  cmp     qword ptr [rdi+50h], 0
0x14000971f  jz      short loc_14000977E
0x140009721  mov     eax, 0C0000708h
0x140009726  mov     ebx, eax
0x140009728  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x14000972e  lea     rcx, WPP_RECORDER_INITIALIZED
0x140009735  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14000973c  setnz   r8b
0x140009740  and     dl, 8
0x140009743  jnz     short loc_14000974E
0x140009745  test    r8b, r8b
0x140009748  jz      loc_14000958C
0x14000974e  mov     dword ptr [rsp+110h+CreateDisposition], eax
0x140009752  lea     r9, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140009759  mov     dword ptr [rsp+110h+ShareAccess], 1DAh
0x140009761  mov     qword ptr [rsp+110h+FileAttributes], r9
0x140009766  lea     r9, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x14000976d  mov     [rsp+110h+AllocationSize], r9
0x140009772  mov     word ptr [rsp+110h+IoStatusBlock], 0Fh
0x140009779  jmp     loc_14000956A
0x14000977e  cmp     qword ptr [rdi+20h], 0
0x140009783  jz      short loc_1400097E2
0x140009785  mov     eax, 0C0000708h
0x14000978a  mov     ebx, eax
0x14000978c  mov     dl, byte ptr cs:xmmword_14001A3D0+1
0x140009792  lea     rcx, WPP_RECORDER_INITIALIZED
0x140009799  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400097a0  setnz   r8b
0x1400097a4  and     dl, 8
0x1400097a7  jnz     short loc_1400097B2
0x1400097a9  test    r8b, r8b
0x1400097ac  jz      loc_14000958C
0x1400097b2  mov     dword ptr [rsp+110h+CreateDisposition], eax
0x1400097b6  lea     r9, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x1400097bd  mov     dword ptr [rsp+110h+ShareAccess], 1E6h
0x1400097c5  mov     qword ptr [rsp+110h+FileAttributes], r9
0x1400097ca  lea     r9, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x1400097d1  mov     [rsp+110h+AllocationSize], r9
0x1400097d6  mov     word ptr [rsp+110h+IoStatusBlock], 10h
0x1400097dd  jmp     loc_14000956A
0x1400097e2  call    cs:__imp_IoGetCurrentProcess
0x1400097e9  nop     dword ptr [rax+rax+00h]
0x1400097ee  mov     rcx, rax; Object
0x1400097f1  mov     [rdi+20h], rax
0x1400097f5  call    cs:__imp_ObfReferenceObject
0x1400097fc  nop     dword ptr [rax+rax+00h]
0x140009801  mov     [rdi+50h], r13
0x140009805  mov     [r15], rdi
0x140009808  mov     dl, byte ptr cs:xmmword_14001A3E0+1
0x14000980e  lea     rcx, WPP_RECORDER_INITIALIZED
0x140009815  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14000981c  setnz   r8b
0x140009820  and     dl, 8
0x140009823  jnz     short loc_14000982E
0x140009825  test    r8b, r8b
0x140009828  jz      loc_14000958C
0x14000982e  mov     dword ptr [rsp+110h+CreateDisposition], r14d
0x140009833  lea     r9, aOnecoreBaseFsG_2; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x14000983a  mov     dword ptr [rsp+110h+ShareAccess], 1F8h
0x140009842  mov     ecx, 40Bh
0x140009847  mov     qword ptr [rsp+110h+FileAttributes], r9
0x14000984c  lea     r9, WPP_f518d8db80f83e9c1a62003295e898de_Traceguids
0x140009853  mov     [rsp+110h+AllocationSize], r9
0x140009858  mov     word ptr [rsp+110h+IoStatusBlock], 11h
0x14000985f  mov     dword ptr [rsp+110h+ObjectAttributes], 0Bh
0x140009867  mov     byte ptr [rsp+110h+DesiredAccess], 4
0x14000986c  jmp     loc_14000957C
```
