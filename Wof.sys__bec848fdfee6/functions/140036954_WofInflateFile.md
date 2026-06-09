# WofInflateFile

- ea: `0x140036954`
- end: `0x140036e69`
- name: `WofInflateFile`
- size: `1301`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *, char)`
- caller_count: `5`
- callee_count: `9`
- tags: `file_ops, loader_planting`

## callers

- `0x140033930`
- `0x1400361b0`
- `0x140036540`
- `0x14003b5a0`
- `0x14003e870`

## callees

- `0x14000b4a4`
- `0x14000dc88`
- `0x14000de64`
- `0x14000ed74`
- `0x140011560`
- `0x140011640`
- `0x1400119c0`
- `0x140036670`
- `0x140036954`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x140036c00`
- `ntoskrnl!KeDelayExecutionThread` at `0x140036c00`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140036c97`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140036d0e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140036c97`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140036d0e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036de1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140036de1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140036a7e`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140036a7e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140036c79`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140036cf0`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140036c79`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140036cf0`
- `FLTMGR!FltWriteFile` at `0x140036bdb`
- `FLTMGR!FltWriteFile` at `0x140036bdb`
- `FLTMGR!FltSetInformationFile` at `0x140036aed`
- `FLTMGR!FltSetInformationFile` at `0x140036e25`
- `FLTMGR!FltSetInformationFile` at `0x140036aed`
- `FLTMGR!FltSetInformationFile` at `0x140036e25`
- `FLTMGR!FltFsControlFile` at `0x140036cdd`
- `FLTMGR!FltFsControlFile` at `0x140036cdd`

## pseudocode

```c
__int64 __fastcall WofInflateFile(__int64 a1, __int64 a2, _DWORD *a3, char a4)
{
  __int64 v4; // rax
  _DWORD *v5; // r12
  __int64 v6; // rdi
  __int64 (__fastcall *v10)(_DWORD *); // rax
  __int64 result; // rax
  __int64 *v12; // rdx
  unsigned int v13; // ebx
  char *PoolWithTag; // r15
  struct _FILE_OBJECT *v15; // rdx
  struct _FLT_INSTANCE *v16; // rcx
  __int64 v17; // rdx
  union _LARGE_INTEGER v18; // rcx
  int v19; // edx
  NTSTATUS v20; // edi
  int v21; // r9d
  int v22; // edx
  struct _FLT_INSTANCE *v23; // rcx
  int v24; // r9d
  struct _FILE_OBJECT *v25; // rdx
  struct _FLT_INSTANCE *v26; // rcx
  int Flags; // [rsp+28h] [rbp-81h]
  __int64 v28; // [rsp+60h] [rbp-49h] BYREF
  __int64 v29; // [rsp+68h] [rbp-41h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+70h] [rbp-39h] BYREF
  ULONG BytesWritten; // [rsp+78h] [rbp-31h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+80h] [rbp-29h] BYREF
  __int128 InputBuffer; // [rsp+88h] [rbp-21h] BYREF
  __m128i FileInformation; // [rsp+98h] [rbp-11h] BYREF
  __m128i v35; // [rsp+A8h] [rbp-1h]
  __int64 v36; // [rsp+B8h] [rbp+Fh]

  *(_QWORD *)&InputBuffer = a1;
  v28 = 0;
  v36 = 0;
  v4 = (unsigned int)a3[3];
  v5 = a3 + 16;
  ByteOffset.QuadPart = 0;
  v6 = a1;
  v29 = 0;
  FileInformation = 0;
  v35 = 0;
  BytesWritten = 0;
  v10 = (__int64 (__fastcall *)(_DWORD *))*((_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 53 * v4 + 36);
  if ( v10 )
  {
    result = v10(a3 + 16);
    if ( (int)result < 0 )
      return result;
  }
  v12 = WPP_0d3c4c833653390108f193f53084a201_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v12) = 4;
    WPP_RECORDER_SF_qZ(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v12,
      10,
      11,
      (__int64)WPP_0d3c4c833653390108f193f53084a201_Traceguids,
      *(_QWORD *)(a2 + 32),
      *(_QWORD *)(a2 + 32) + 88LL);
  }
  result = (*((__int64 (__fastcall **)(_DWORD *, __int64 *, _QWORD))&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels
            + 53 * (unsigned int)a3[3]
            + 40))(
             v5,
             &v28,
             0);
  if ( (int)result < 0 )
    return result;
  v13 = 0x1000000;
  if ( v28 < 0x1000000 )
    v13 = (v28 + 4095) & 0xFFFFF000;
  while ( 1 )
  {
    PoolWithTag = (char *)ExAllocatePoolWithTag(PagedPool, v13, 0x49666F57u);
    if ( PoolWithTag )
      break;
    if ( v13 <= 0x8000 )
      return 3221225626LL;
    v13 = ((v13 >> 2) + 0x7FFF) & 0xFFFF8000;
  }
  if ( a4 )
  {
    v15 = *(struct _FILE_OBJECT **)(a2 + 32);
    v16 = *(struct _FLT_INSTANCE **)(a2 + 24);
    FileInformation = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    LODWORD(v36) = 0;
    v35 = FileInformation;
    FltSetInformationFile(v16, v15, &FileInformation, 0x28u, FileBasicInformation);
  }
  v17 = v28;
  v18.QuadPart = 0;
  while ( 1 )
  {
    ByteOffset = v18;
    if ( !v17 )
    {
      (*((void (__fastcall **)(_DWORD *, __int64 *, _QWORD))&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels
       + 53 * (unsigned int)a3[3]
       + 40))(
        v5,
        &v28,
        0);
      if ( v28 >= 4096 || (v20 = WofFlushFile(v6, *(_QWORD *)(a2 + 24), *(_QWORD *)(a2 + 32), 0, 0), v20 >= 0) )
      {
        v20 = WofMarkFileAsInflated(a2, a3);
        goto LABEL_37;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_37;
      v24 = 14;
LABEL_31:
      LOBYTE(v19) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v19,
        10,
        v24,
        (__int64)WPP_0d3c4c833653390108f193f53084a201_Traceguids,
        v20);
      goto LABEL_37;
    }
    if ( v17 < v13 )
      v13 = v17;
    LOBYTE(Flags) = 1;
    v20 = (*((__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD *, int, union _LARGE_INTEGER, unsigned int, char *, _QWORD, __int64 *))&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels
           + 53 * (unsigned int)a3[3]
           + 30))(
            v6,
            0,
            0,
            *(_QWORD *)(a2 + 24),
            v5,
            Flags,
            v18,
            v13,
            PoolWithTag,
            0,
            &v29);
    if ( v20 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_37;
      v24 = 12;
      goto LABEL_31;
    }
    v21 = v29;
    if ( (v29 & 0xFFF) != 0 )
    {
      memset(&PoolWithTag[v29], 0, 4096 - (v29 & 0xFFF));
      goto LABEL_21;
    }
    while ( 1 )
    {
      v20 = FltWriteFile(
              *(PFLT_INSTANCE *)(a2 + 24),
              *(PFILE_OBJECT *)(a2 + 32),
              &ByteOffset,
              (v21 + 4095) & 0xFFFFF000,
              PoolWithTag,
              0xFu,
              &BytesWritten,
              0,
              0);
      if ( v20 != -1073741740 )
        break;
      Interval.QuadPart = -100000;
      KeDelayExecutionThread(0, 1u, &Interval);
LABEL_21:
      v21 = v29;
    }
    if ( v20 < 0 )
      break;
    v17 = v28 - v29;
    v18.QuadPart = v29 + ByteOffset.QuadPart;
    v6 = InputBuffer;
    v28 -= v29;
  }
  InputBuffer = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v22) = 2;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v22,
      10,
      13,
      (__int64)WPP_0d3c4c833653390108f193f53084a201_Traceguids,
      v20);
  }
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)a3 + 32LL));
  a3[2] |= 0x10u;
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)a3 + 32LL));
  *((_QWORD *)&InputBuffer + 1) = v28 + ByteOffset.QuadPart;
  v23 = *(struct _FLT_INSTANCE **)(a2 + 24);
  *(_QWORD *)&InputBuffer = 0;
  FltFsControlFile(v23, *(PFILE_OBJECT *)(a2 + 32), 0x980C8u, &InputBuffer, 0x10u, 0, 0, 0);
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)a3 + 32LL));
  a3[2] &= ~0x10u;
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)a3 + 32LL));
LABEL_37:
  ExFreePoolWithTag(PoolWithTag, 0);
  if ( a4 )
  {
    v25 = *(struct _FILE_OBJECT **)(a2 + 32);
    v26 = *(struct _FLT_INSTANCE **)(a2 + 24);
    FileInformation = _mm_load_si128((const __m128i *)&_xmm_fffffffffffffffefffffffffffffffe);
    LODWORD(v36) = 0;
    v35 = FileInformation;
    FltSetInformationFile(v26, v25, &FileInformation, 0x28u, FileBasicInformation);
  }
  WofInflateTelemetry(a3, a2, (unsigned int)v20);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x140036954  mov     [rsp-8+arg_18], rbx
0x140036959  push    rbp
0x14003695a  push    rsi
0x14003695b  push    rdi
0x14003695c  push    r12
0x14003695e  push    r13
0x140036960  push    r14
0x140036962  push    r15
0x140036964  lea     rbp, [rsp-27h]
0x140036969  sub     rsp, 0D0h
0x140036970  mov     rax, cs:__security_cookie
0x140036977  xor     rax, rsp
0x14003697a  mov     [rbp+57h+var_40], rax
0x14003697e  xor     ebx, ebx
0x140036980  mov     qword ptr [rbp+57h+InputBuffer], rcx
0x140036984  xor     eax, eax
0x140036986  mov     [rbp+57h+var_A0], rbx
0x14003698a  mov     [rbp+57h+var_48], rax
0x14003698e  lea     r15, WPP_MAIN_CB.Queue+10h
0x140036995  mov     eax, [r8+0Ch]
0x140036999  lea     r12, [r8+40h]
0x14003699d  xorps   xmm0, xmm0
0x1400369a0  mov     qword ptr [rbp+57h+ByteOffset], rbx
0x1400369a4  mov     rdi, rcx
0x1400369a7  mov     [rbp+57h+var_98], rbx
0x1400369ab  imul    rcx, rax, 1A8h
0x1400369b2  movups  [rbp+57h+FileInformation], xmm0
0x1400369b6  movups  [rbp+57h+var_58], xmm0
0x1400369ba  mov     r13b, r9b
0x1400369bd  mov     [rbp+57h+var_88], ebx
0x1400369c0  mov     r14, r8
0x1400369c3  mov     rsi, rdx
0x1400369c6  mov     rax, [rcx+r15+120h]
0x1400369ce  test    rax, rax
0x1400369d1  jz      short loc_1400369E3
0x1400369d3  mov     rcx, r12
0x1400369d6  call    _guard_dispatch_icall
0x1400369db  test    eax, eax
0x1400369dd  js      loc_140036E41
0x1400369e3  lea     rax, WPP_RECORDER_INITIALIZED
0x1400369ea  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400369f1  lea     rdx, WPP_0d3c4c833653390108f193f53084a201_Traceguids
0x1400369f8  jz      short loc_140036A2D
0x1400369fa  mov     rcx, [rsi+20h]
0x1400369fe  mov     r9d, 0Bh
0x140036a04  lea     rax, [rcx+58h]
0x140036a08  mov     [rsp+100h+BytesWritten], rax
0x140036a0d  lea     r8d, [r9-1]
0x140036a11  mov     qword ptr [rsp+100h+Flags], rcx
0x140036a16  mov     rcx, cs:WPP_GLOBAL_Control
0x140036a1d  mov     qword ptr [rsp+100h+FileInformationClass], rdx
0x140036a22  mov     dl, 4
0x140036a24  mov     rcx, [rcx+40h]
0x140036a28  call    WPP_RECORDER_SF_qZ
0x140036a2d  mov     eax, [r14+0Ch]
0x140036a31  lea     rdx, [rbp+57h+var_A0]
0x140036a35  imul    rcx, rax, 1A8h
0x140036a3c  xor     r8d, r8d
0x140036a3f  mov     rax, [rcx+r15+140h]
0x140036a47  mov     rcx, r12
0x140036a4a  call    _guard_dispatch_icall
0x140036a4f  test    eax, eax
0x140036a51  js      loc_140036E41
0x140036a57  mov     rax, [rbp+57h+var_A0]
0x140036a5b  mov     ebx, 1000000h
0x140036a60  cmp     rax, rbx
0x140036a63  jge     short loc_140036A71
0x140036a65  lea     ebx, [rax+0FFFh]
0x140036a6b  and     ebx, 0FFFFF000h
0x140036a71  mov     edx, ebx; NumberOfBytes
0x140036a73  mov     ecx, 1; PoolType
0x140036a78  mov     r8d, 49666F57h; Tag
0x140036a7e  call    cs:__imp_ExAllocatePoolWithTag
0x140036a85  nop     dword ptr [rax+rax+00h]
0x140036a8a  mov     r15, rax
0x140036a8d  test    rax, rax
0x140036a90  jnz     short loc_140036AB5
0x140036a92  cmp     ebx, 8000h
0x140036a98  jbe     short loc_140036AAB
0x140036a9a  shr     ebx, 2
0x140036a9d  add     ebx, 7FFFh
0x140036aa3  and     ebx, 0FFFF8000h
0x140036aa9  jmp     short loc_140036A71
0x140036aab  mov     eax, 0C000009Ah
0x140036ab0  jmp     loc_140036E41
0x140036ab5  test    r13b, r13b
0x140036ab8  jz      short loc_140036AF9
0x140036aba  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x140036ac2  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x140036ac6  mov     rdx, [rsi+20h]; FileObject
0x140036aca  mov     r9d, 28h ; '('; Length
0x140036ad0  mov     rcx, [rsi+18h]; Instance
0x140036ad4  movdqu  [rbp+57h+FileInformation], xmm0
0x140036ad9  mov     dword ptr [rbp+57h+var_48], 0
0x140036ae0  movdqu  [rbp+57h+var_58], xmm0
0x140036ae5  mov     [rsp+100h+FileInformationClass], 4; FileInformationClass
0x140036aed  call    cs:__imp_FltSetInformationFile
0x140036af4  nop     dword ptr [rax+rax+00h]
0x140036af9  mov     rdx, [rbp+57h+var_A0]
0x140036afd  xor     ecx, ecx
0x140036aff  mov     qword ptr [rbp+57h+ByteOffset], rcx
0x140036b03  test    rdx, rdx
0x140036b06  jz      loc_140036D63
0x140036b0c  mov     r9, [rsi+18h]
0x140036b10  mov     eax, ebx
0x140036b12  cmp     rdx, rax
0x140036b15  mov     eax, [r14+0Ch]
0x140036b19  cmovl   ebx, edx
0x140036b1c  xor     r8d, r8d
0x140036b1f  imul    rdx, rax, 1A8h
0x140036b26  lea     rax, WPP_MAIN_CB.Queue+10h
0x140036b2d  mov     rax, [rdx+rax+0F0h]
0x140036b35  lea     rdx, [rbp+57h+var_98]
0x140036b39  mov     [rsp+100h+var_B0], rdx
0x140036b3e  xor     edx, edx
0x140036b40  mov     [rsp+100h+var_B8], 0
0x140036b49  mov     [rsp+100h+CallbackContext], r15
0x140036b4e  mov     dword ptr [rsp+100h+CallbackRoutine], ebx
0x140036b52  mov     [rsp+100h+BytesWritten], rcx
0x140036b57  mov     rcx, rdi
0x140036b5a  mov     byte ptr [rsp+100h+Flags], 1
0x140036b5f  mov     qword ptr [rsp+100h+FileInformationClass], r12
0x140036b64  call    _guard_dispatch_icall
0x140036b69  mov     edi, eax
0x140036b6b  test    eax, eax
0x140036b6d  js      loc_140036D1F
0x140036b73  mov     r9, [rbp+57h+var_98]
0x140036b77  mov     rax, r9
0x140036b7a  and     eax, 0FFFh
0x140036b7f  jz      short loc_140036B99
0x140036b81  mov     r8d, 1000h
0x140036b87  lea     rcx, [r9+r15]; void *
0x140036b8b  sub     r8, rax; Size
0x140036b8e  xor     edx, edx; Val
0x140036b90  call    memset
0x140036b95  mov     r9, [rbp+57h+var_98]
0x140036b99  mov     rdx, [rsi+20h]; FileObject
0x140036b9d  lea     rax, [rbp+57h+var_88]
0x140036ba1  mov     rcx, [rsi+18h]; InitiatingInstance
0x140036ba5  lea     r8, [rbp+57h+ByteOffset]; ByteOffset
0x140036ba9  mov     [rsp+100h+CallbackContext], 0; CallbackContext
0x140036bb2  add     r9d, 0FFFh
0x140036bb9  mov     [rsp+100h+CallbackRoutine], 0; CallbackRoutine
0x140036bc2  and     r9d, 0FFFFF000h; Length
0x140036bc9  mov     [rsp+100h+BytesWritten], rax; BytesWritten
0x140036bce  mov     [rsp+100h+Flags], 0Fh; Flags
0x140036bd6  mov     qword ptr [rsp+100h+FileInformationClass], r15; Buffer
0x140036bdb  call    cs:__imp_FltWriteFile
0x140036be2  nop     dword ptr [rax+rax+00h]
0x140036be7  mov     edi, eax
0x140036be9  cmp     eax, 0C0000054h
0x140036bee  jnz     short loc_140036C0E
0x140036bf0  lea     r8, [rbp+57h+Interval]; Interval
0x140036bf4  mov     qword ptr [rbp+57h+Interval], 0FFFFFFFFFFFE7960h
0x140036bfc  mov     dl, 1; Alertable
0x140036bfe  xor     ecx, ecx; WaitMode
0x140036c00  call    cs:__imp_KeDelayExecutionThread
0x140036c07  nop     dword ptr [rax+rax+00h]
0x140036c0c  jmp     short loc_140036B95
0x140036c0e  test    edi, edi
0x140036c10  js      short loc_140036C2F
0x140036c12  mov     rdx, [rbp+57h+var_A0]
0x140036c16  sub     rdx, [rbp+57h+var_98]
0x140036c1a  mov     rcx, qword ptr [rbp+57h+ByteOffset]
0x140036c1e  add     rcx, [rbp+57h+var_98]
0x140036c22  mov     rdi, qword ptr [rbp+57h+InputBuffer]
0x140036c26  mov     [rbp+57h+var_A0], rdx
0x140036c2a  jmp     loc_140036AFF
0x140036c2f  xorps   xmm0, xmm0
0x140036c32  movups  [rbp+57h+InputBuffer], xmm0
0x140036c36  lea     rax, WPP_RECORDER_INITIALIZED
0x140036c3d  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140036c44  jz      short loc_140036C72
0x140036c46  mov     rcx, cs:WPP_GLOBAL_Control
0x140036c4d  lea     rax, WPP_0d3c4c833653390108f193f53084a201_Traceguids
0x140036c54  mov     r9d, 0Dh
0x140036c5a  mov     [rsp+100h+Flags], edi
0x140036c5e  mov     dl, 2
0x140036c60  mov     qword ptr [rsp+100h+FileInformationClass], rax
0x140036c65  mov     rcx, [rcx+40h]
0x140036c69  lea     r8d, [r9-3]
0x140036c6d  call    WPP_RECORDER_SF_d
0x140036c72  mov     rcx, [r14]
0x140036c75  add     rcx, 20h ; ' '; FastMutex
0x140036c79  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140036c80  nop     dword ptr [rax+rax+00h]
0x140036c85  mov     eax, [r14+8]
0x140036c89  or      eax, 10h
0x140036c8c  mov     [r14+8], eax
0x140036c90  mov     rcx, [r14]
0x140036c93  add     rcx, 20h ; ' '; FastMutex
0x140036c97  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140036c9e  nop     dword ptr [rax+rax+00h]
0x140036ca3  mov     rcx, qword ptr [rbp+57h+ByteOffset]
0x140036ca7  lea     r9, [rbp+57h+InputBuffer]; InputBuffer
0x140036cab  add     rcx, [rbp+57h+var_A0]
0x140036caf  xor     edx, edx
0x140036cb1  mov     [rsp+100h+CallbackRoutine], rdx; LengthReturned
0x140036cb6  mov     r8d, 980C8h; FsControlCode
0x140036cbc  mov     dword ptr [rsp+100h+BytesWritten], edx; OutputBufferLength
0x140036cc0  mov     qword ptr [rsp+100h+Flags], rdx; OutputBuffer
0x140036cc5  mov     qword ptr [rbp+57h+InputBuffer+8], rcx
0x140036cc9  mov     rcx, [rsi+18h]; Instance
0x140036ccd  mov     qword ptr [rbp+57h+InputBuffer], rdx
0x140036cd1  mov     rdx, [rsi+20h]; FileObject
0x140036cd5  mov     [rsp+100h+FileInformationClass], 10h; InputBufferLength
0x140036cdd  call    cs:__imp_FltFsControlFile
0x140036ce4  nop     dword ptr [rax+rax+00h]
0x140036ce9  mov     rcx, [r14]
0x140036cec  add     rcx, 20h ; ' '; FastMutex
0x140036cf0  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140036cf7  nop     dword ptr [rax+rax+00h]
0x140036cfc  mov     eax, [r14+8]
0x140036d00  and     eax, 0FFFFFFEFh
0x140036d03  mov     [r14+8], eax
0x140036d07  mov     rcx, [r14]
0x140036d0a  add     rcx, 20h ; ' '; FastMutex
0x140036d0e  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140036d15  nop     dword ptr [rax+rax+00h]
0x140036d1a  jmp     loc_140036DDC
0x140036d1f  lea     rax, WPP_RECORDER_INITIALIZED
0x140036d26  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140036d2d  jz      loc_140036DDC
0x140036d33  mov     r9d, 0Ch
0x140036d39  mov     rcx, cs:WPP_GLOBAL_Control
0x140036d40  lea     rax, WPP_0d3c4c833653390108f193f53084a201_Traceguids
0x140036d47  mov     [rsp+100h+Flags], edi
0x140036d4b  mov     r8d, 0Ah
0x140036d51  mov     dl, 2
0x140036d53  mov     qword ptr [rsp+100h+FileInformationClass], rax
0x140036d58  mov     rcx, [rcx+40h]
0x140036d5c  call    WPP_RECORDER_SF_d
0x140036d61  jmp     short loc_140036DDC
0x140036d63  mov     eax, [r14+0Ch]
0x140036d67  xor     r8d, r8d
0x140036d6a  imul    rdx, rax, 1A8h
0x140036d71  lea     rax, WPP_MAIN_CB.Queue+10h
0x140036d78  mov     rcx, r12
0x140036d7b  mov     rax, [rdx+rax+140h]
0x140036d83  lea     rdx, [rbp+57h+var_A0]
0x140036d87  call    _guard_dispatch_icall
0x140036d8c  cmp     [rbp+57h+var_A0], 1000h
0x140036d94  jge     short loc_140036DCF
0x140036d96  mov     r8, [rsi+20h]
0x140036d9a  xor     r9d, r9d
0x140036d9d  mov     rdx, [rsi+18h]
0x140036da1  mov     rcx, rdi
0x140036da4  mov     byte ptr [rsp+100h+FileInformationClass], 0
0x140036da9  call    WofFlushFile
0x140036dae  mov     edi, eax
0x140036db0  test    eax, eax
0x140036db2  jns     short loc_140036DCF
0x140036db4  lea     rax, WPP_RECORDER_INITIALIZED
0x140036dbb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140036dc2  jz      short loc_140036DDC
0x140036dc4  mov     r9d, 0Eh
0x140036dca  jmp     loc_140036D39
0x140036dcf  mov     rdx, r14
0x140036dd2  mov     rcx, rsi
0x140036dd5  call    WofMarkFileAsInflated
0x140036dda  mov     edi, eax
0x140036ddc  xor     edx, edx; Tag
0x140036dde  mov     rcx, r15; P
0x140036de1  call    cs:__imp_ExFreePoolWithTag
0x140036de8  nop     dword ptr [rax+rax+00h]
0x140036ded  test    r13b, r13b
0x140036df0  jz      short loc_140036E31
0x140036df2  movdqa  xmm0, cs:__xmm@fffffffffffffffefffffffffffffffe
0x140036dfa  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x140036dfe  mov     rdx, [rsi+20h]; FileObject
0x140036e02  mov     r9d, 28h ; '('; Length
0x140036e08  mov     rcx, [rsi+18h]; Instance
0x140036e0c  movdqu  [rbp+57h+FileInformation], xmm0
0x140036e11  mov     dword ptr [rbp+57h+var_48], 0
0x140036e18  movdqu  [rbp+57h+var_58], xmm0
0x140036e1d  mov     [rsp+100h+FileInformationClass], 4; FileInformationClass
0x140036e25  call    cs:__imp_FltSetInformationFile
0x140036e2c  nop     dword ptr [rax+rax+00h]
0x140036e31  mov     r8d, edi
0x140036e34  mov     rdx, rsi
0x140036e37  mov     rcx, r14
0x140036e3a  call    WofInflateTelemetry
0x140036e3f  mov     eax, edi
0x140036e41  mov     rcx, [rbp+57h+var_40]
0x140036e45  xor     rcx, rsp; StackCookie
0x140036e48  call    __security_check_cookie
0x140036e4d  mov     rbx, [rsp+100h+arg_18]
0x140036e55  add     rsp, 0D0h
0x140036e5c  pop     r15
0x140036e5e  pop     r14
0x140036e60  pop     r13
0x140036e62  pop     r12
0x140036e64  pop     rdi
0x140036e65  pop     rsi
0x140036e66  pop     rbp
0x140036e67  retn
```
