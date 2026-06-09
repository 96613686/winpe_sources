# EdppStartAndEnableSession

- ea: `0x14002e9d8`
- end: `0x14002eccf`
- name: `EdppStartAndEnableSession`
- size: `759`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14002e6f0`

## callees

- `0x140006c40`
- `0x14002e10c`
- `0x14002e228`
- `0x14002e3cc`
- `0x14002e45c`
- `0x14002e7ec`
- `0x14002e9d8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002ec73`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ec8c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ec73`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002ec8c`
- `ntoskrnl!EtwEnableTrace` at `0x14002ebd7`
- `ntoskrnl!EtwEnableTrace` at `0x14002ebd7`
- `ntoskrnl!ZwWriteFile` at `0x14002ec34`
- `ntoskrnl!ZwWriteFile` at `0x14002ec34`
- `ntoskrnl!ZwTraceControl` at `0x14002eb50`
- `ntoskrnl!ZwTraceControl` at `0x14002eb9b`
- `ntoskrnl!ZwTraceControl` at `0x14002eb50`
- `ntoskrnl!ZwTraceControl` at `0x14002eb9b`
- `ntoskrnl!ZwClose` at `0x14002eca3`
- `ntoskrnl!ZwClose` at `0x14002eca3`

## pseudocode

```c
__int64 __fastcall EdppStartAndEnableSession(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        char a6,
        _QWORD *a7)
{
  __int64 v9; // rax
  bool v10; // si
  int v11; // edi
  unsigned int v12; // r14d
  int BaseLoggerInfo; // eax
  unsigned int *QuadPart; // rbx
  size_t v15; // r8
  __int16 v16; // ax
  void *v17; // rdx
  __int64 v18; // rsi
  int IoStatusBlock; // [rsp+20h] [rbp-61h]
  _WORD v21[2]; // [rsp+50h] [rbp-31h] BYREF
  unsigned int v22; // [rsp+54h] [rbp-2Dh] BYREF
  int v23; // [rsp+58h] [rbp-29h] BYREF
  unsigned int Buffer; // [rsp+60h] [rbp-21h] BYREF
  void *Src; // [rsp+68h] [rbp-19h] BYREF
  HANDLE FileHandle; // [rsp+70h] [rbp-11h] BYREF
  union _LARGE_INTEGER ByteOffset; // [rsp+78h] [rbp-9h] BYREF
  struct _IO_STATUS_BLOCK v28; // [rsp+80h] [rbp-1h] BYREF

  FileHandle = 0;
  v21[0] = 0;
  ByteOffset.QuadPart = 0;
  Buffer = 0;
  v23 = 0;
  v22 = 0;
  Src = 0;
  *a7 = 0;
  v9 = *a1 - 0x41514B71D425B399LL;
  if ( *a1 == 0x41514B71D425B399LL )
    v9 = a1[1] + 0x3CA1586DC0BE5073LL;
  v10 = v9 == 0;
  v11 = EdppReadIndexOrDefault(a4, a2, &FileHandle, &v22);
  if ( v11 >= 0 )
  {
    if ( v10 )
      v12 = 1;
    else
      v12 = ((_BYTE)v22 + 1) & 0x7F;
    v11 = EdppComposeFullPath(a3, v12, &Src, v21);
    if ( v11 < 0 )
    {
LABEL_27:
      if ( Src )
        ExFreePoolWithTag(Src, 0);
      goto LABEL_29;
    }
    BaseLoggerInfo = EdppCreateBaseLoggerInfo((_DWORD)a1, a2, v21[0], (unsigned int)&ByteOffset, (__int64)&Buffer);
    QuadPart = (unsigned int *)ByteOffset.QuadPart;
    v11 = BaseLoggerInfo;
    if ( BaseLoggerInfo >= 0 )
    {
      if ( v10 )
      {
        *(_DWORD *)(ByteOffset.QuadPart + 64) = 268435461;
        QuadPart[10] = 2;
      }
      else
      {
        *(_DWORD *)(ByteOffset.QuadPart + 64) = 268435458;
        QuadPart[10] = 1;
      }
      if ( a6 )
        QuadPart[16] |= 0x80u;
      v15 = v21[0];
      v16 = v21[0] - 2;
      v17 = Src;
      QuadPart[15] = v10 ? 8 : 1;
      QuadPart[12] = 8;
      QuadPart[17] = 0;
      *((_WORD *)QuadPart + 64) = v16;
      memmove(*((void **)QuadPart + 17), v17, v15);
      v11 = ZwTraceControl(1, QuadPart, *QuadPart, QuadPart, *QuadPart, &v23);
      if ( v11 == -1073741811 )
      {
        if ( !v10 || (int)EdppDeleteLogFile((const unsigned __int16 *)Src) < 0 )
          goto LABEL_25;
        v11 = ZwTraceControl(1, QuadPart, *QuadPart, QuadPart, *QuadPart, &v23);
      }
      if ( v11 >= 0 )
      {
        v18 = *((_QWORD *)QuadPart + 1);
        LOBYTE(IoStatusBlock) = 5;
        v11 = EtwEnableTrace(a5, 0, v18, 1, IoStatusBlock, 0, 0, 0);
        if ( v11 < 0
          || (Buffer = v12,
              v28 = 0,
              ByteOffset.QuadPart = 0,
              v11 = ZwWriteFile(FileHandle, 0, 0, 0, &v28, &Buffer, 4u, &ByteOffset, 0),
              v11 < 0) )
        {
LABEL_23:
          if ( v18 )
            EdppDisableAndStopSession(a1, a2, a5, v18);
          goto LABEL_25;
        }
        if ( LODWORD(v28.Information) != 4 )
        {
          v11 = -1073741672;
          goto LABEL_23;
        }
        *a7 = v18;
      }
    }
LABEL_25:
    if ( QuadPart )
      ExFreePoolWithTag(QuadPart, 0);
    goto LABEL_27;
  }
LABEL_29:
  if ( FileHandle )
    ZwClose(FileHandle);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14002e9d8  mov     [rsp-8+arg_8], rdx
0x14002e9dd  push    rbp
0x14002e9de  push    rbx
0x14002e9df  push    rsi
0x14002e9e0  push    rdi
0x14002e9e1  push    r12
0x14002e9e3  push    r14
0x14002e9e5  lea     rbp, [rsp-17h]
0x14002e9ea  sub     rsp, 98h
0x14002e9f1  xor     eax, eax
0x14002e9f3  mov     [rbp+3Fh+FileHandle], 0
0x14002e9fb  mov     [rbp+3Fh+var_70], ax
0x14002e9ff  mov     r10, r9
0x14002ea02  mov     qword ptr [rbp+3Fh+var_48], rax
0x14002ea06  mov     rbx, r8
0x14002ea09  mov     [rbp+3Fh+var_60], eax
0x14002ea0c  mov     r12, rcx
0x14002ea0f  mov     [rbp+3Fh+var_68], eax
0x14002ea12  mov     rax, [rbp+3Fh+arg_30]
0x14002ea16  mov     [rbp+3Fh+var_6C], 0
0x14002ea1d  mov     [rbp+3Fh+Src], 0
0x14002ea25  mov     qword ptr [rax], 0
0x14002ea2c  mov     rax, [rcx]
0x14002ea2f  sub     rax, cs:qword_1400157E8
0x14002ea36  jnz     short loc_14002EA43
0x14002ea38  mov     rax, [rcx+8]
0x14002ea3c  sub     rax, cs:qword_1400157F0
0x14002ea43  test    rax, rax
0x14002ea46  lea     r9, [rbp+3Fh+var_6C]
0x14002ea4a  lea     r8, [rbp+3Fh+FileHandle]
0x14002ea4e  mov     rcx, r10
0x14002ea51  setz    sil
0x14002ea55  call    EdppReadIndexOrDefault
0x14002ea5a  mov     edi, eax
0x14002ea5c  test    eax, eax
0x14002ea5e  js      loc_14002EC98
0x14002ea64  test    sil, sil
0x14002ea67  jz      short loc_14002EA71
0x14002ea69  mov     r14d, 1
0x14002ea6f  jmp     short loc_14002EA7C
0x14002ea71  mov     r14d, [rbp+3Fh+var_6C]
0x14002ea75  inc     r14d
0x14002ea78  and     r14d, 7Fh
0x14002ea7c  lea     r9, [rbp+3Fh+var_70]
0x14002ea80  mov     edx, r14d
0x14002ea83  lea     r8, [rbp+3Fh+Src]
0x14002ea87  mov     rcx, rbx
0x14002ea8a  call    EdppComposeFullPath
0x14002ea8f  mov     edi, eax
0x14002ea91  test    eax, eax
0x14002ea93  js      loc_14002EC7F
0x14002ea99  movzx   r8d, [rbp+3Fh+var_70]
0x14002ea9e  lea     rax, [rbp+3Fh+var_60]
0x14002eaa2  mov     rdx, [rbp+3Fh+arg_8]
0x14002eaa6  lea     r9, [rbp+3Fh+var_48]
0x14002eaaa  mov     rcx, r12
0x14002eaad  mov     [rsp+0C0h+IoStatusBlock], rax
0x14002eab2  call    EdppCreateBaseLoggerInfo
0x14002eab7  mov     rbx, qword ptr [rbp+3Fh+var_48]
0x14002eabb  mov     edi, eax
0x14002eabd  test    eax, eax
0x14002eabf  js      loc_14002EC69
0x14002eac5  mov     edx, 2
0x14002eaca  test    sil, sil
0x14002eacd  jz      short loc_14002EADB
0x14002eacf  mov     dword ptr [rbx+40h], 10000005h
0x14002ead6  mov     [rbx+28h], edx
0x14002ead9  jmp     short loc_14002EAE9
0x14002eadb  mov     dword ptr [rbx+40h], 10000002h
0x14002eae2  mov     dword ptr [rbx+28h], 1
0x14002eae9  cmp     [rbp+3Fh+arg_28], 0
0x14002eaed  jz      short loc_14002EAF4
0x14002eaef  bts     dword ptr [rbx+40h], 7
0x14002eaf4  movzx   r8d, [rbp+3Fh+var_70]; Size
0x14002eaf9  mov     al, sil
0x14002eafc  neg     al
0x14002eafe  movzx   eax, [rbp+3Fh+var_70]
0x14002eb02  sbb     ecx, ecx
0x14002eb04  sub     ax, dx
0x14002eb07  mov     rdx, [rbp+3Fh+Src]; Src
0x14002eb0b  and     ecx, 7
0x14002eb0e  inc     ecx
0x14002eb10  mov     [rbx+3Ch], ecx
0x14002eb13  mov     dword ptr [rbx+30h], 8
0x14002eb1a  mov     dword ptr [rbx+44h], 0
0x14002eb21  mov     [rbx+80h], ax
0x14002eb28  mov     rcx, [rbx+88h]; void *
0x14002eb2f  call    memmove
0x14002eb34  mov     r8d, [rbx]
0x14002eb37  lea     rax, [rbp+3Fh+var_68]
0x14002eb3b  mov     [rsp+0C0h+Buffer], rax
0x14002eb40  mov     r9, rbx
0x14002eb43  mov     rdx, rbx
0x14002eb46  mov     dword ptr [rsp+0C0h+IoStatusBlock], r8d
0x14002eb4b  mov     ecx, 1
0x14002eb50  call    cs:__imp_ZwTraceControl
0x14002eb57  nop     dword ptr [rax+rax+00h]
0x14002eb5c  mov     edi, eax
0x14002eb5e  cmp     eax, 0C000000Dh
0x14002eb63  jnz     short loc_14002EBA9
0x14002eb65  test    sil, sil
0x14002eb68  jz      loc_14002EC69
0x14002eb6e  mov     rcx, [rbp+3Fh+Src]
0x14002eb72  call    EdppDeleteLogFile
0x14002eb77  test    eax, eax
0x14002eb79  js      loc_14002EC69
0x14002eb7f  mov     r8d, [rbx]
0x14002eb82  lea     rax, [rbp+3Fh+var_68]
0x14002eb86  mov     [rsp+0C0h+Buffer], rax
0x14002eb8b  mov     r9, rbx
0x14002eb8e  mov     rdx, rbx
0x14002eb91  mov     dword ptr [rsp+0C0h+IoStatusBlock], r8d
0x14002eb96  mov     ecx, 1
0x14002eb9b  call    cs:__imp_ZwTraceControl
0x14002eba2  nop     dword ptr [rax+rax+00h]
0x14002eba7  mov     edi, eax
0x14002eba9  xor     eax, eax
0x14002ebab  test    edi, edi
0x14002ebad  js      loc_14002EC69
0x14002ebb3  mov     rsi, [rbx+8]
0x14002ebb7  lea     r9d, [rax+1]
0x14002ebbb  mov     rcx, [rbp+3Fh+arg_20]
0x14002ebbf  mov     r8, rsi
0x14002ebc2  mov     dword ptr [rsp+0C0h+ByteOffset], eax
0x14002ebc6  xor     edx, edx
0x14002ebc8  mov     qword ptr [rsp+0C0h+Length], rax
0x14002ebcd  mov     [rsp+0C0h+Buffer], rax
0x14002ebd2  mov     byte ptr [rsp+0C0h+IoStatusBlock], 5
0x14002ebd7  call    cs:__imp_EtwEnableTrace
0x14002ebde  nop     dword ptr [rax+rax+00h]
0x14002ebe3  mov     edi, eax
0x14002ebe5  test    eax, eax
0x14002ebe7  js      short loc_14002EC51
0x14002ebe9  mov     rcx, [rbp+3Fh+FileHandle]; FileHandle
0x14002ebed  lea     rax, [rbp+3Fh+var_48]
0x14002ebf1  mov     [rsp+0C0h+Key], 0; Key
0x14002ebfa  xorps   xmm0, xmm0
0x14002ebfd  mov     [rsp+0C0h+ByteOffset], rax; ByteOffset
0x14002ec02  xor     r9d, r9d; ApcContext
0x14002ec05  lea     rax, [rbp+3Fh+var_60]
0x14002ec09  mov     [rsp+0C0h+Length], 4; Length
0x14002ec11  mov     [rsp+0C0h+Buffer], rax; Buffer
0x14002ec16  xor     r8d, r8d; ApcRoutine
0x14002ec19  lea     rax, [rbp+3Fh+var_40]
0x14002ec1d  mov     [rbp+3Fh+var_60], r14d
0x14002ec21  xor     edx, edx; Event
0x14002ec23  mov     [rsp+0C0h+IoStatusBlock], rax; IoStatusBlock
0x14002ec28  movups  xmmword ptr [rbp+3Fh+var_40], xmm0
0x14002ec2c  mov     qword ptr [rbp+3Fh+var_48], 0
0x14002ec34  call    cs:__imp_ZwWriteFile
0x14002ec3b  nop     dword ptr [rax+rax+00h]
0x14002ec40  mov     edi, eax
0x14002ec42  test    eax, eax
0x14002ec44  js      short loc_14002EC51
0x14002ec46  cmp     dword ptr [rbp+3Fh+var_40.Information], 4
0x14002ec4a  jz      short loc_14002ECC2
0x14002ec4c  mov     edi, 0C0000098h
0x14002ec51  test    rsi, rsi
0x14002ec54  jz      short loc_14002EC69
0x14002ec56  mov     r8, [rbp+3Fh+arg_20]
0x14002ec5a  mov     r9, rsi
0x14002ec5d  mov     rdx, [rbp+3Fh+arg_8]
0x14002ec61  mov     rcx, r12
0x14002ec64  call    EdppDisableAndStopSession
0x14002ec69  test    rbx, rbx
0x14002ec6c  jz      short loc_14002EC7F
0x14002ec6e  xor     edx, edx; Tag
0x14002ec70  mov     rcx, rbx; P
0x14002ec73  call    cs:__imp_ExFreePoolWithTag
0x14002ec7a  nop     dword ptr [rax+rax+00h]
0x14002ec7f  cmp     [rbp+3Fh+Src], 0
0x14002ec84  jz      short loc_14002EC98
0x14002ec86  mov     rcx, [rbp+3Fh+Src]; P
0x14002ec8a  xor     edx, edx; Tag
0x14002ec8c  call    cs:__imp_ExFreePoolWithTag
0x14002ec93  nop     dword ptr [rax+rax+00h]
0x14002ec98  cmp     [rbp+3Fh+FileHandle], 0
0x14002ec9d  jz      short loc_14002ECAF
0x14002ec9f  mov     rcx, [rbp+3Fh+FileHandle]; Handle
0x14002eca3  call    cs:__imp_ZwClose
0x14002ecaa  nop     dword ptr [rax+rax+00h]
0x14002ecaf  mov     eax, edi
0x14002ecb1  add     rsp, 98h
0x14002ecb8  pop     r14
0x14002ecba  pop     r12
0x14002ecbc  pop     rdi
0x14002ecbd  pop     rsi
0x14002ecbe  pop     rbx
0x14002ecbf  pop     rbp
0x14002ecc0  retn
0x14002ecc2  test    eax, eax
0x14002ecc4  js      short loc_14002EC51
0x14002ecc6  mov     rax, [rbp+3Fh+arg_30]
0x14002ecca  mov     [rax], rsi
0x14002eccd  jmp     short loc_14002EC69
```
