# FltpCommonAttachVolume

- ea: `0x180074810`
- end: `0x180074943`
- name: `FltpCommonAttachVolume`
- size: `307`
- prototype: `__int64 __usercall@<rax>(PVOID FltObject@<rcx>, PVOID@<rdx>, PCUNICODE_STRING Source, __int64, PUNICODE_STRING)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18004e520`
- `0x18004f1d0`
- `0x18004f210`

## callees

- `0x180010400`
- `0x1800698d0`
- `0x180069c90`
- `0x180074810`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x18007b3e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x18007b3e2`
- `ntoskrnl!ExAllocatePool2` at `0x1800748e5`
- `ntoskrnl!ExAllocatePool2` at `0x1800748e5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18007b371`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18007b403`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18007b371`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18007b403`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18007b389`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x18007b389`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18007b39d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x18007b39d`

## pseudocode

```c
__int64 __fastcall FltpCommonAttachVolume(
        PVOID FltObject,
        char *a2,
        int a3,
        UNICODE_STRING *SourceString,
        PCUNICODE_STRING Source,
        PVOID *a6,
        PUNICODE_STRING a7)
{
  int v7; // eax
  const UNICODE_STRING *v10; // rsi
  unsigned __int16 v11; // ax
  PUNICODE_STRING v12; // rbx
  int InstanceFromName; // eax
  int v15; // edi
  UNICODE_STRING DestinationString; // [rsp+40h] [rbp-28h] BYREF
  PVOID FltObjecta; // [rsp+70h] [rbp+8h] BYREF

  v7 = *((_DWORD *)FltObject + 24);
  *(_QWORD *)&DestinationString.Length = 0;
  FltObjecta = 0;
  if ( (v7 & 2) == 0 )
    return 3223060488LL;
  DestinationString.Buffer = 0;
  if ( a3 )
  {
    v12 = a7;
    InstanceFromName = FltpCreateInstanceFromName(FltObject, SourceString, (__int64)&FltObjecta, (__int64)a7);
  }
  else
  {
    v10 = Source;
    if ( SourceString )
    {
      v12 = a7;
    }
    else
    {
      v11 = Source->Length + 2 + *((_WORD *)FltObject + 32);
      DestinationString.MaximumLength = v11;
      if ( v11 > 0x1FEu )
      {
        v11 = 510;
        DestinationString.MaximumLength = 510;
      }
      v12 = a7;
      if ( a7 && a7->MaximumLength < (unsigned __int64)v11 + 2 )
        return 2149318657LL;
      DestinationString.Buffer = (wchar_t *)ExAllocatePool2(256, v11, 1852394822);
      if ( !DestinationString.Buffer )
        return 3221225626LL;
      RtlCopyUnicodeString(&DestinationString, (PCUNICODE_STRING)FltObject + 4);
      RtlAppendUnicodeToString(&DestinationString, L"_");
      RtlAppendUnicodeStringToString(&DestinationString, v10);
      SourceString = &DestinationString;
    }
    InstanceFromName = FltpInitInstance((char *)FltObject, a2, 2u, v10, SourceString, (__int64 *)&FltObjecta);
  }
  v15 = InstanceFromName;
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0x6E694D46u);
  if ( v15 >= 0 )
  {
    if ( v12 )
    {
      RtlCopyUnicodeString(v12, (PCUNICODE_STRING)((char *)FltObjecta + 104));
      v12->Buffer[(unsigned __int64)v12->Length >> 1] = 0;
    }
    if ( a6 )
      *a6 = FltObjecta;
    else
      FltObjectDereference(FltObjecta);
  }
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180074810  mov     r11, rsp
0x180074813  push    rbp
0x180074814  push    rdi
0x180074815  push    r15
0x180074817  sub     rsp, 50h
0x18007481b  mov     eax, [rcx+60h]
0x18007481e  xor     r15d, r15d
0x180074821  mov     [r11-28h], r15
0x180074825  mov     rbp, rdx
0x180074828  mov     [r11+8], r15
0x18007482c  mov     rdi, rcx
0x18007482f  test    al, 2
0x180074831  jz      loc_1800748BF
0x180074837  mov     [r11+10h], rbx
0x18007483b  mov     [r11+18h], rsi
0x18007483f  mov     [r11+20h], r14
0x180074843  mov     [r11-20h], r15
0x180074847  test    r8d, r8d
0x18007484a  jnz     loc_180074913
0x180074850  mov     rsi, [rsp+68h+Source]
0x180074858  test    r9, r9
0x18007485b  jnz     loc_180074906
0x180074861  movzx   ecx, word ptr [rsi]
0x180074864  movzx   eax, word ptr [rdi+40h]
0x180074868  add     cx, 2
0x18007486c  add     ax, cx
0x18007486f  mov     ecx, 1FEh
0x180074874  mov     [rsp+68h+DestinationString.MaximumLength], ax
0x180074879  cmp     ax, cx
0x18007487c  ja      short loc_1800748CE
0x18007487e  mov     rbx, [rsp+68h+arg_30]
0x180074886  test    rbx, rbx
0x180074889  jz      short loc_1800748D7
0x18007488b  movzx   ecx, word ptr [rbx+2]
0x18007488f  movzx   edx, ax
0x180074892  add     rdx, 2
0x180074896  cmp     rcx, rdx
0x180074899  jnb     short loc_1800748D7
0x18007489b  mov     eax, 801C0001h
0x1800748a0  mov     rsi, [rsp+68h+arg_10]
0x1800748a8  mov     rbx, [rsp+68h+arg_8]
0x1800748ad  mov     r14, [rsp+68h+arg_18]
0x1800748b5  add     rsp, 50h
0x1800748b9  pop     r15
0x1800748bb  pop     rdi
0x1800748bc  pop     rbp
0x1800748bd  retn
0x1800748bf  mov     eax, 0C01C0008h
0x1800748c4  add     rsp, 50h
0x1800748c8  pop     r15
0x1800748ca  pop     rdi
0x1800748cb  pop     rbp
0x1800748cc  retn
0x1800748ce  mov     eax, ecx
0x1800748d0  mov     [rsp+68h+DestinationString.MaximumLength], cx
0x1800748d5  jmp     short loc_18007487E
0x1800748d7  movzx   edx, ax
0x1800748da  mov     ecx, 100h
0x1800748df  mov     r8d, 6E694D46h
0x1800748e5  call    cs:__imp_ExAllocatePool2
0x1800748ec  nop     dword ptr [rax+rax+00h]
0x1800748f1  mov     [rsp+68h+DestinationString.Buffer], rax
0x1800748f6  test    rax, rax
0x1800748f9  jnz     loc_18007B368
0x1800748ff  mov     eax, 0C000009Ah
0x180074904  jmp     short loc_1800748A0
0x180074906  mov     rbx, [rsp+68h+arg_30]
0x18007490e  jmp     loc_18007B3AE
0x180074913  mov     rbx, [rsp+68h+arg_30]
0x18007491b  lea     rax, [rsp+68h+FltObject]
0x180074920  mov     [rsp+68h+var_38], rbx; __int64
0x180074925  mov     r8d, 2
0x18007492b  mov     [rsp+68h+var_40], rax; __int64
0x180074930  mov     [rsp+68h+SourceString], r9; SourceString
0x180074935  xor     r9d, r9d
0x180074938  call    FltpCreateInstanceFromName
0x18007493d  nop
0x18007493e  jmp     loc_18007B3D1
0x18007b368  lea     rdx, [rdi+40h]; SourceString
0x18007b36c  lea     rcx, [rsp+68h+DestinationString]; DestinationString
0x18007b371  call    cs:__imp_RtlCopyUnicodeString
0x18007b378  nop     dword ptr [rax+rax+00h]
0x18007b37d  lea     rdx, asc_18002B678; "_"
0x18007b384  lea     rcx, [rsp+68h+DestinationString]; Destination
0x18007b389  call    cs:__imp_RtlAppendUnicodeToString
0x18007b390  nop     dword ptr [rax+rax+00h]
0x18007b395  mov     rdx, rsi; Source
0x18007b398  lea     rcx, [rsp+68h+DestinationString]; Destination
0x18007b39d  call    cs:__imp_RtlAppendUnicodeStringToString
0x18007b3a4  nop     dword ptr [rax+rax+00h]
0x18007b3a9  lea     r9, [rsp+68h+DestinationString]
0x18007b3ae  lea     rax, [rsp+68h+FltObject]
0x18007b3b3  mov     r8d, 2
0x18007b3b9  mov     [rsp+68h+var_40], rax; __int64
0x18007b3be  mov     rdx, rbp; PVOID
0x18007b3c1  mov     [rsp+68h+SourceString], r9; SourceString
0x18007b3c6  mov     rcx, rdi; FltObject
0x18007b3c9  mov     r9, rsi
0x18007b3cc  call    FltpInitInstance
0x18007b3d1  mov     rcx, [rsp+68h+DestinationString.Buffer]; P
0x18007b3d6  mov     edi, eax
0x18007b3d8  test    rcx, rcx
0x18007b3db  jz      short loc_18007B3EE
0x18007b3dd  mov     edx, 6E694D46h; Tag
0x18007b3e2  call    cs:__imp_ExFreePoolWithTag
0x18007b3e9  nop     dword ptr [rax+rax+00h]
0x18007b3ee  test    edi, edi
0x18007b3f0  js      short loc_18007B43F
0x18007b3f2  test    rbx, rbx
0x18007b3f5  jz      short loc_18007B41E
0x18007b3f7  mov     rdx, [rsp+68h+FltObject]
0x18007b3fc  mov     rcx, rbx; DestinationString
0x18007b3ff  add     rdx, 68h ; 'h'; SourceString
0x18007b403  call    cs:__imp_RtlCopyUnicodeString
0x18007b40a  nop     dword ptr [rax+rax+00h]
0x18007b40f  movzx   edx, word ptr [rbx]
0x18007b412  mov     rcx, [rbx+8]
0x18007b416  shr     rdx, 1
0x18007b419  mov     [rcx+rdx*2], r15w
0x18007b41e  mov     rcx, [rsp+68h+arg_28]
0x18007b426  test    rcx, rcx
0x18007b429  jz      short loc_18007B435
0x18007b42b  mov     rax, [rsp+68h+FltObject]
0x18007b430  mov     [rcx], rax
0x18007b433  jmp     short loc_18007B43F
0x18007b435  mov     rcx, [rsp+68h+FltObject]; FltObject
0x18007b43a  call    FltObjectDereference
0x18007b43f  mov     eax, edi
0x18007b441  jmp     loc_1800748A0
```
