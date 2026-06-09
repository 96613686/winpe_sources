# FltpGetOpenedDestinationFileName

- ea: `0x180058640`
- end: `0x180058a1b`
- name: `FltpGetOpenedDestinationFileName`
- size: `987`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x1800584e0`
- `0x18005e010`

## callees

- `0x180009f20`
- `0x18000dcb0`
- `0x18000e2e0`
- `0x18000eb80`
- `0x180058380`
- `0x180058640`
- `0x18005b880`
- `0x1800629c0`
- `0x180063830`
- `0x180064e80`
- `0x18006e9a0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1800589f2`
- `ntoskrnl!ObfDereferenceObject` at `0x1800589f2`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180058725`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180058947`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18007914c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1800792a2`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180058725`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180058947`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18007914c`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1800792a2`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005895b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x180079197`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1800792b6`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18005895b`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x180079197`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1800792b6`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1800587d1`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1800587d1`
- `ntoskrnl!IoFileObjectType` at `0x1800587ad`
- `ntoskrnl!IoGetBaseFileSystemDeviceObject` at `0x18005898f`
- `ntoskrnl!IoGetBaseFileSystemDeviceObject` at `0x1800589a2`
- `ntoskrnl!IoGetBaseFileSystemDeviceObject` at `0x18005898f`
- `ntoskrnl!IoGetBaseFileSystemDeviceObject` at `0x1800589a2`
- `ntoskrnl!ObIsKernelHandle` at `0x1800587a1`
- `ntoskrnl!ObIsKernelHandle` at `0x1800587a1`

## pseudocode

```c
__int64 __fastcall FltpGetOpenedDestinationFileName(__int64 a1)
{
  unsigned __int64 v1; // rax
  wchar_t *v3; // rcx
  PFLT_FILE_NAME_INFORMATION *v4; // r14
  void *v5; // rdx
  unsigned int FileNameInformation; // esi
  __int64 v8; // rax
  int v9; // edx
  __int64 v10; // rax
  __int64 v11; // rcx
  BOOLEAN IsKernelHandle; // al
  unsigned int v13; // edi
  unsigned int v14; // edx
  int v15; // edx
  unsigned int v16; // edx
  int v17; // edx
  unsigned int v18; // edx
  struct _DEVICE_OBJECT *BaseFileSystemDeviceObject; // rdi
  int v20; // ecx
  __int64 v21; // rdx
  struct _FLT_FILE_NAME_INFORMATION *v22; // rcx
  unsigned __int16 *v23; // rax
  unsigned __int64 v24; // rdx
  __int64 v25; // rax
  unsigned __int64 v26; // rdx
  unsigned int v27; // eax
  _WORD *v28; // rcx
  PVOID *Object; // [rsp+20h] [rbp-39h]
  PVOID *Objecta; // [rsp+20h] [rbp-39h]
  UNICODE_STRING SourceString; // [rsp+60h] [rbp+7h] BYREF
  UNICODE_STRING v32; // [rsp+70h] [rbp+17h] BYREF
  char v33; // [rsp+C0h] [rbp+67h] BYREF
  PFLT_FILE_NAME_INFORMATION *v34; // [rsp+C8h] [rbp+6Fh] BYREF
  PVOID v35; // [rsp+D0h] [rbp+77h] BYREF
  char v36; // [rsp+D8h] [rbp+7Fh] BYREF

  v1 = *(unsigned __int16 *)(a1 + 104);
  *(_DWORD *)(a1 + 40) |= 2u;
  v3 = *(wchar_t **)(a1 + 96);
  SourceString = 0;
  v35 = 0;
  v4 = 0;
  v5 = *(void **)(a1 + 88);
  v34 = 0;
  SourceString.Length = v1;
  SourceString.MaximumLength = v1;
  SourceString.Buffer = v3;
  v32 = 0;
  if ( v5 )
  {
    IsKernelHandle = ObIsKernelHandle(v5);
    v13 = ObReferenceObjectByHandle(
            *(HANDLE *)(a1 + 88),
            0,
            (POBJECT_TYPE)IoFileObjectType,
            IsKernelHandle == 0,
            &v35,
            0);
    if ( (int)FltpDbgStatus(v13, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 6328, 0) < 0 )
      return v13;
    BaseFileSystemDeviceObject = IoGetBaseFileSystemDeviceObject(*(PFILE_OBJECT *)(a1 + 64));
    if ( BaseFileSystemDeviceObject == IoGetBaseFileSystemDeviceObject((PFILE_OBJECT)v35) )
    {
      v21 = *(_QWORD *)(a1 + 16);
      v20 = *(_DWORD *)(a1 + 108) & 0x1000000;
    }
    else
    {
      v20 = 0;
      v21 = 0;
    }
    LODWORD(Object) = v20 | *(_DWORD *)(a1 + 108) & 0xFF00 | 2;
    FileNameInformation = FltpAllocateInitializeNameGenerationContext(&v34, v21, v35, 0, Object, 0, 0, 0, 0);
    if ( (int)FltpDbgStatus(FileNameInformation, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 6375, 3221225626LL) >= 0 )
    {
      v4 = v34;
      FileNameInformation = FltpGetFileNameInformation(v34);
      if ( (int)FltpDbgStatus(FileNameInformation, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 6382, 0) < 0 )
        goto LABEL_7;
      v14 = v4[15]->Name.Length + SourceString.Length + 2;
      if ( v14 > 0xFFFE )
        FileNameInformation = -1073741562;
      else
        FileNameInformation = v14 > (unsigned __int64)*(unsigned int *)(*(_QWORD *)(a1 + 112) + 20LL) - 2
                            ? FltpReallocNameControl(*(_QWORD *)(a1 + 112), v14 + 514, 0, 0)
                            : 0;
      if ( (int)FltpDbgStatus(FileNameInformation, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 6393, 0) < 0 )
        goto LABEL_7;
      RtlCopyUnicodeString(*(PUNICODE_STRING *)(a1 + 112), &v4[15]->Name);
      if ( *SourceString.Buffer != 92 && *SourceString.Buffer != 58 )
      {
        v23 = *(unsigned __int16 **)(a1 + 112);
        v24 = *v23;
        v25 = *((_QWORD *)v23 + 1);
        v26 = v24 >> 1;
        if ( *(_WORD *)(v25 + 2 * v26 - 2) != 92 )
        {
          *(_WORD *)(v25 + 2 * v26) = 92;
          **(_WORD **)(a1 + 112) += 2;
        }
      }
      RtlAppendUnicodeStringToString(*(PUNICODE_STRING *)(a1 + 112), &SourceString);
      goto LABEL_13;
    }
LABEL_64:
    v4 = v34;
    goto LABEL_7;
  }
  if ( *v3 == 92 )
  {
    if ( (unsigned int)v1 > 0xFFFE )
    {
      FileNameInformation = -1073741562;
    }
    else if ( v1 > (unsigned __int64)*(unsigned int *)(*(_QWORD *)(a1 + 112) + 20LL) - 2 )
    {
      FileNameInformation = FltpReallocNameControl(*(_QWORD *)(a1 + 112), (unsigned int)(v1 + 514), 0, 0);
    }
    else
    {
      FileNameInformation = 0;
    }
    if ( (int)FltpDbgStatus(FileNameInformation, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 6594, 0) < 0 )
      goto LABEL_7;
    RtlCopyUnicodeString(*(PUNICODE_STRING *)(a1 + 112), &SourceString);
LABEL_13:
    *(_DWORD *)(a1 + 40) |= 0x80u;
    FileNameInformation = FltpExpandFilePath(a1);
    if ( (int)FltpDbgStatus(FileNameInformation, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 6618, 0) >= 0 )
    {
      v8 = *(_QWORD *)(a1 + 24);
      v9 = v8 ? *(_DWORD *)(v8 + 56) : **(_DWORD **)(a1 + 32);
      if ( (v9 & 1) != 0 )
      {
        v10 = *(_QWORD *)(a1 + 24);
        if ( v10 )
          v11 = v10 + 112;
        else
          v11 = *(_QWORD *)(a1 + 32) + 8LL;
        FltpParseShareName(v11, *(_QWORD *)(a1 + 112));
      }
    }
    goto LABEL_7;
  }
  if ( (unsigned int)FltpFindCharReverse((_DWORD)v3, (unsigned __int16)v1, 92, (unsigned int)&v36, (__int64)&v33) != -1073741772 )
    return 3221225523LL;
  LODWORD(Objecta) = *(_DWORD *)(a1 + 108);
  FileNameInformation = FltpAllocateInitializeNameGenerationContext(
                          &v34,
                          *(_QWORD *)(a1 + 16),
                          *(_QWORD *)(a1 + 64),
                          0,
                          Objecta,
                          0,
                          0,
                          0,
                          0);
  if ( (int)FltpDbgStatus(FileNameInformation, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 6466, 3221225626LL) < 0 )
    goto LABEL_64;
  v4 = v34;
  FileNameInformation = FltpGetFileNameInformation(v34);
  if ( (int)FltpDbgStatus(FileNameInformation, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 6473, 0) >= 0 )
  {
    v27 = FltParseFileNameInformation(v4[15]);
    if ( (int)FltpDbgStatus(v27, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 6485, 0) >= 0 )
    {
      v28 = v4[15];
      if ( *SourceString.Buffer == 58 )
      {
        v15 = (unsigned __int16)(v28[4] - v28[36]);
        v32.Length = v15;
        v32.MaximumLength = v15;
        v16 = SourceString.Length + v15;
        v32.Buffer = v4[15]->Name.Buffer;
        if ( v16 > 0xFFFE )
        {
          FileNameInformation = -1073741562;
        }
        else if ( v16 > (unsigned __int64)*(unsigned int *)(*(_QWORD *)(a1 + 112) + 20LL) - 2 )
        {
          FileNameInformation = FltpReallocNameControl(*(_QWORD *)(a1 + 112), v16 + 514, 0, 0);
        }
        else
        {
          FileNameInformation = 0;
        }
        if ( (int)FltpDbgStatus(FileNameInformation, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 6517, 0) < 0 )
          goto LABEL_7;
        RtlCopyUnicodeString(*(PUNICODE_STRING *)(a1 + 112), &v32);
        RtlAppendUnicodeStringToString(*(PUNICODE_STRING *)(a1 + 112), &SourceString);
        *(_WORD *)(*(_QWORD *)(a1 + 112) + 26LL) = SourceString.Length;
      }
      else
      {
        v17 = (unsigned __int16)(v28[4] - v28[44]);
        v32.Length = v17;
        v32.MaximumLength = v17;
        v18 = SourceString.Length + v17;
        v32.Buffer = v4[15]->Name.Buffer;
        if ( v18 > 0xFFFE )
        {
          FileNameInformation = -1073741562;
        }
        else if ( v18 > (unsigned __int64)*(unsigned int *)(*(_QWORD *)(a1 + 112) + 20LL) - 2 )
        {
          FileNameInformation = FltpReallocNameControl(*(_QWORD *)(a1 + 112), v18 + 514, 0, 0);
        }
        else
        {
          FileNameInformation = 0;
        }
        if ( (int)FltpDbgStatus(FileNameInformation, "minkernel\\fs\\filtermgr\\filter\\namesup.c", 6562, 0) < 0 )
          goto LABEL_7;
        RtlCopyUnicodeString(*(PUNICODE_STRING *)(a1 + 112), &v32);
        RtlAppendUnicodeStringToString(*(PUNICODE_STRING *)(a1 + 112), &SourceString);
      }
      goto LABEL_13;
    }
    FileNameInformation = -1073741773;
  }
LABEL_7:
  if ( v35 )
    ObfDereferenceObject(v35);
  if ( v4 )
  {
    v22 = v4[15];
    if ( v22 )
      FltReleaseFileNameInformation(v22);
    FltpFreeNameGenerationContext(v4);
  }
  return FileNameInformation;
}

```

## disassembly

```asm
0x180058640  push    rbp
0x180058642  push    rbx
0x180058643  push    rsi
0x180058644  push    rdi
0x180058645  push    r14
0x180058647  push    r15
0x180058649  lea     rbp, [rsp-2Fh]
0x18005864e  sub     rsp, 88h
0x180058655  movzx   eax, word ptr [rcx+68h]
0x180058659  xor     r15d, r15d
0x18005865c  or      dword ptr [rcx+28h], 2
0x180058660  mov     rbx, rcx
0x180058663  mov     rcx, [rcx+60h]
0x180058667  xorps   xmm0, xmm0
0x18005866a  movups  xmmword ptr [rbp+57h+SourceString.Length], xmm0
0x18005866e  mov     [rbp+57h+arg_10], r15
0x180058672  mov     r14d, r15d
0x180058675  mov     rdx, [rbx+58h]
0x180058679  mov     [rbp+57h+arg_8], r15
0x18005867d  mov     [rbp+57h+SourceString.Length], ax
0x180058681  mov     [rbp+57h+SourceString.MaximumLength], ax
0x180058685  mov     [rbp+57h+SourceString.Buffer], rcx
0x180058689  movups  xmmword ptr [rbp+57h+var_40.Length], xmm0
0x18005868d  test    rdx, rdx
0x180058690  jnz     loc_18005879E
0x180058696  cmp     word ptr [rcx], 5Ch ; '\'
0x18005869a  jnz     loc_1800589C2
0x1800586a0  mov     edx, eax
0x1800586a2  cmp     eax, 0FFFEh
0x1800586a7  ja      loc_180058794
0x1800586ad  mov     r10, [rbx+70h]
0x1800586b1  mov     ecx, [r10+14h]
0x1800586b5  sub     rcx, 2
0x1800586b9  cmp     rax, rcx
0x1800586bc  ja      short loc_180058705
0x1800586be  mov     esi, r15d
0x1800586c1  mov     r8d, 19C2h
0x1800586c7  lea     rdx, aMinkernelFsFil_25; "minkernel\\fs\\filtermgr\\filter\\names"...
0x1800586ce  xor     r9d, r9d
0x1800586d1  mov     ecx, esi
0x1800586d3  call    FltpDbgStatus
0x1800586d8  test    eax, eax
0x1800586da  jns     short loc_18005871D
0x1800586dc  mov     rcx, [rbp+57h+arg_10]; Object
0x1800586e0  test    rcx, rcx
0x1800586e3  jnz     loc_1800589F2
0x1800586e9  test    r14, r14
0x1800586ec  jnz     loc_180058A03
0x1800586f2  mov     eax, esi
0x1800586f4  add     rsp, 88h
0x1800586fb  pop     r15
0x1800586fd  pop     r14
0x1800586ff  pop     rdi
0x180058700  pop     rsi
0x180058701  pop     rbx
0x180058702  pop     rbp
0x180058703  retn
0x180058705  add     edx, 202h
0x18005870b  xor     r9d, r9d
0x18005870e  xor     r8d, r8d
0x180058711  mov     rcx, r10
0x180058714  call    FltpReallocNameControl
0x180058719  mov     esi, eax
0x18005871b  jmp     short loc_1800586C1
0x18005871d  mov     rcx, [rbx+70h]; DestinationString
0x180058721  lea     rdx, [rbp+57h+SourceString]; SourceString
0x180058725  call    cs:__imp_RtlCopyUnicodeString
0x18005872c  nop     dword ptr [rax+rax+00h]
0x180058731  or      dword ptr [rbx+28h], 80h
0x180058738  mov     rcx, rbx
0x18005873b  call    FltpExpandFilePath
0x180058740  mov     r8d, 19DAh
0x180058746  lea     rdx, aMinkernelFsFil_25; "minkernel\\fs\\filtermgr\\filter\\names"...
0x18005874d  xor     r9d, r9d
0x180058750  mov     ecx, eax
0x180058752  mov     esi, eax
0x180058754  call    FltpDbgStatus
0x180058759  test    eax, eax
0x18005875b  js      loc_1800586DC
0x180058761  mov     rax, [rbx+18h]
0x180058765  test    rax, rax
0x180058768  jz      short loc_18005878C
0x18005876a  mov     edx, [rax+38h]
0x18005876d  test    dl, 1
0x180058770  jz      loc_1800586DC
0x180058776  mov     rax, [rbx+18h]
0x18005877a  test    rax, rax
0x18005877d  jz      loc_1800792DC
0x180058783  lea     rcx, [rax+70h]
0x180058787  jmp     loc_1800792E4
0x18005878c  mov     rax, [rbx+20h]
0x180058790  mov     edx, [rax]
0x180058792  jmp     short loc_18005876D
0x180058794  mov     esi, 0C0000106h
0x180058799  jmp     loc_1800586C1
0x18005879e  mov     rcx, rdx; Handle
0x1800587a1  call    cs:__imp_ObIsKernelHandle
0x1800587a8  nop     dword ptr [rax+rax+00h]
0x1800587ad  mov     r8, cs:__imp_IoFileObjectType
0x1800587b4  test    al, al
0x1800587b6  mov     rcx, [rbx+58h]; Handle
0x1800587ba  lea     rax, [rbp+57h+arg_10]
0x1800587be  setz    r9b; AccessMode
0x1800587c2  mov     [rsp+0B0h+HandleInformation], r15; HandleInformation
0x1800587c7  xor     edx, edx; DesiredAccess
0x1800587c9  mov     [rsp+0B0h+Object], rax; Object
0x1800587ce  mov     r8, [r8]; ObjectType
0x1800587d1  call    cs:__imp_ObReferenceObjectByHandle
0x1800587d8  nop     dword ptr [rax+rax+00h]
0x1800587dd  mov     r8d, 18B8h
0x1800587e3  lea     rdx, aMinkernelFsFil_25; "minkernel\\fs\\filtermgr\\filter\\names"...
0x1800587ea  mov     ecx, eax
0x1800587ec  xor     r9d, r9d
0x1800587ef  mov     edi, eax
0x1800587f1  call    FltpDbgStatus
0x1800587f6  test    eax, eax
0x1800587f8  jns     loc_18005898B
0x1800587fe  mov     eax, edi
0x180058800  add     rsp, 88h
0x180058807  pop     r15
0x180058809  pop     r14
0x18005880b  pop     rdi
0x18005880c  pop     rsi
0x18005880d  pop     rbx
0x18005880e  pop     rbp
0x18005880f  retn
0x180058811  mov     rax, [r14+78h]
0x180058815  movzx   edx, [rbp+57h+SourceString.Length]
0x180058819  add     edx, 2
0x18005881c  movzx   ecx, word ptr [rax+8]
0x180058820  add     edx, ecx
0x180058822  cmp     edx, 0FFFEh
0x180058828  ja      short loc_180058845
0x18005882a  mov     r10, [rbx+70h]
0x18005882e  mov     eax, edx
0x180058830  mov     ecx, [r10+14h]
0x180058834  sub     rcx, 2
0x180058838  cmp     rax, rcx
0x18005883b  ja      short loc_18005884F
0x18005883d  mov     esi, r15d
0x180058840  jmp     loc_180079121
0x180058845  mov     esi, 0C0000106h
0x18005884a  jmp     loc_180079121
0x18005884f  add     edx, 202h
0x180058855  xor     r9d, r9d
0x180058858  xor     r8d, r8d
0x18005885b  mov     rcx, r10
0x18005885e  call    FltpReallocNameControl
0x180058863  mov     esi, eax
0x180058865  jmp     loc_180079121
0x18005886a  movzx   eax, word ptr [rcx+48h]
0x18005886e  movzx   ecx, word ptr [rcx+8]
0x180058872  sub     cx, ax
0x180058875  movzx   edx, cx
0x180058878  mov     [rbp+57h+var_40.Length], dx
0x18005887c  mov     [rbp+57h+var_40.MaximumLength], dx
0x180058880  mov     rax, [r14+78h]
0x180058884  mov     rcx, [rax+10h]
0x180058888  movzx   eax, [rbp+57h+SourceString.Length]
0x18005888c  add     edx, eax
0x18005888e  mov     [rbp+57h+var_40.Buffer], rcx
0x180058892  cmp     edx, 0FFFEh
0x180058898  ja      short loc_1800588B5
0x18005889a  mov     r10, [rbx+70h]
0x18005889e  mov     eax, edx
0x1800588a0  mov     ecx, [r10+14h]
0x1800588a4  sub     rcx, 2
0x1800588a8  cmp     rax, rcx
0x1800588ab  ja      short loc_1800588BF
0x1800588ad  mov     esi, r15d
0x1800588b0  jmp     loc_18007927B
0x1800588b5  mov     esi, 0C0000106h
0x1800588ba  jmp     loc_18007927B
0x1800588bf  add     edx, 202h
0x1800588c5  xor     r9d, r9d
0x1800588c8  xor     r8d, r8d
0x1800588cb  mov     rcx, r10
0x1800588ce  call    FltpReallocNameControl
0x1800588d3  mov     esi, eax
0x1800588d5  jmp     loc_18007927B
0x1800588da  movzx   eax, word ptr [rcx+58h]
0x1800588de  movzx   ecx, word ptr [rcx+8]
0x1800588e2  sub     cx, ax
0x1800588e5  movzx   edx, cx
0x1800588e8  mov     [rbp+57h+var_40.Length], dx
0x1800588ec  mov     [rbp+57h+var_40.MaximumLength], dx
0x1800588f0  mov     rax, [r14+78h]
0x1800588f4  mov     rcx, [rax+10h]
0x1800588f8  movzx   eax, [rbp+57h+SourceString.Length]
0x1800588fc  add     edx, eax
0x1800588fe  mov     [rbp+57h+var_40.Buffer], rcx
0x180058902  cmp     edx, 0FFFEh
0x180058908  ja      short loc_18005896C
0x18005890a  mov     r10, [rbx+70h]
0x18005890e  mov     eax, edx
0x180058910  mov     ecx, [r10+14h]
0x180058914  sub     rcx, 2
0x180058918  cmp     rax, rcx
0x18005891b  ja      short loc_180058973
0x18005891d  mov     esi, r15d
0x180058920  mov     r8d, 19A2h
0x180058926  lea     rdx, aMinkernelFsFil_25; "minkernel\\fs\\filtermgr\\filter\\names"...
0x18005892d  xor     r9d, r9d
0x180058930  mov     ecx, esi
0x180058932  call    FltpDbgStatus
0x180058937  test    eax, eax
0x180058939  js      loc_1800586DC
0x18005893f  mov     rcx, [rbx+70h]; DestinationString
0x180058943  lea     rdx, [rbp+57h+var_40]; SourceString
0x180058947  call    cs:__imp_RtlCopyUnicodeString
0x18005894e  nop     dword ptr [rax+rax+00h]
0x180058953  mov     rcx, [rbx+70h]; Destination
0x180058957  lea     rdx, [rbp+57h+SourceString]; Source
0x18005895b  call    cs:__imp_RtlAppendUnicodeStringToString
0x180058962  nop     dword ptr [rax+rax+00h]
0x180058967  jmp     loc_180058731
0x18005896c  mov     esi, 0C0000106h
0x180058971  jmp     short loc_180058920
0x180058973  add     edx, 202h
0x180058979  xor     r9d, r9d
0x18005897c  xor     r8d, r8d
0x18005897f  mov     rcx, r10
0x180058982  call    FltpReallocNameControl
0x180058987  mov     esi, eax
0x180058989  jmp     short loc_180058920
0x18005898b  mov     rcx, [rbx+40h]; FileObject
0x18005898f  call    cs:__imp_IoGetBaseFileSystemDeviceObject
0x180058996  nop     dword ptr [rax+rax+00h]
0x18005899b  mov     rcx, [rbp+57h+arg_10]; FileObject
0x18005899f  mov     rdi, rax
0x1800589a2  call    cs:__imp_IoGetBaseFileSystemDeviceObject
0x1800589a9  nop     dword ptr [rax+rax+00h]
0x1800589ae  cmp     rdi, rax
0x1800589b1  jz      loc_18007907C
0x1800589b7  mov     ecx, r15d
0x1800589ba  mov     rdx, r15
0x1800589bd  jmp     loc_180079089
0x1800589c2  lea     rdx, [rbp+57h+arg_0]
0x1800589c6  mov     r8d, 5Ch ; '\'
0x1800589cc  mov     [rsp+0B0h+Object], rdx
0x1800589d1  lea     r9, [rbp+57h+arg_18]
0x1800589d5  movzx   edx, ax
0x1800589d8  call    FltpFindCharReverse
0x1800589dd  cmp     eax, 0C0000034h
0x1800589e2  jz      loc_1800791A9
0x1800589e8  mov     eax, 0C0000033h
0x1800589ed  jmp     loc_1800586F4
0x1800589f2  call    cs:__imp_ObfDereferenceObject
0x1800589f9  nop     dword ptr [rax+rax+00h]
0x1800589fe  jmp     loc_1800586E9
0x180058a03  mov     rcx, [r14+78h]; FileNameInformation
0x180058a07  test    rcx, rcx
0x180058a0a  jz      loc_1800792F3
0x180058a10  call    FltReleaseFileNameInformation
0x180058a15  nop
0x180058a16  jmp     loc_1800792F3
0x18007907c  mov     ecx, [rbx+6Ch]
0x18007907f  mov     rdx, [rbx+10h]
0x180079083  and     ecx, 1000000h
0x180079089  mov     eax, [rbx+6Ch]
0x18007908c  xor     r9d, r9d
0x18007908f  mov     r8, [rbp+57h+arg_10]
0x180079093  and     eax, 0FF00h
0x180079098  mov     [rsp+0B0h+var_60], 1
0x1800790a0  or      eax, ecx
0x1800790a2  mov     [rsp+0B0h+var_70], r15d
0x1800790a7  lea     rcx, [rbp+57h+arg_8]
0x1800790ab  mov     [rsp+0B0h+var_78], r15
0x1800790b0  or      eax, 2
0x1800790b3  mov     [rsp+0B0h+var_80], r15
0x1800790b8  mov     [rsp+0B0h+HandleInformation], r15
0x1800790bd  mov     dword ptr [rsp+0B0h+Object], eax
0x1800790c1  call    FltpAllocateInitializeNameGenerationContext
0x1800790c6  mov     r8d, 18E7h
0x1800790cc  mov     [rsp+0B0h+Object], r15
0x1800790d1  mov     r9d, 0C000009Ah
0x1800790d7  lea     rdx, aMinkernelFsFil_25; "minkernel\\fs\\filtermgr\\filter\\names"...
0x1800790de  mov     ecx, eax
0x1800790e0  mov     esi, eax
0x1800790e2  call    FltpDbgStatus
0x1800790e7  test    eax, eax
0x1800790e9  js      loc_1800792D3
0x1800790ef  mov     r14, [rbp+57h+arg_8]
0x1800790f3  mov     rcx, r14
0x1800790f6  call    FltpGetFileNameInformation
0x1800790fb  mov     r8d, 18EEh
0x180079101  lea     rdx, aMinkernelFsFil_25; "minkernel\\fs\\filtermgr\\filter\\names"...
0x180079108  xor     r9d, r9d
0x18007910b  mov     ecx, eax
0x18007910d  mov     esi, eax
0x18007910f  call    FltpDbgStatus
0x180079114  test    eax, eax
0x180079116  js      loc_1800586DC
0x18007911c  jmp     loc_180058811
0x180079121  mov     r8d, 18F9h
0x180079127  lea     rdx, aMinkernelFsFil_25; "minkernel\\fs\\filtermgr\\filter\\names"...
0x18007912e  xor     r9d, r9d
0x180079131  mov     ecx, esi
0x180079133  call    FltpDbgStatus
0x180079138  test    eax, eax
  ... truncated ...
```
