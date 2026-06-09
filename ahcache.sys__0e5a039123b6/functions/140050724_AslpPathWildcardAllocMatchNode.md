# AslpPathWildcardAllocMatchNode

- ea: `0x140050724`
- end: `0x14005093c`
- name: `AslpPathWildcardAllocMatchNode`
- size: `536`
- prototype: `__int64 __fastcall(PUNICODE_STRING DestinationString, PCUNICODE_STRING SourceString, _WORD *, int, NTSTRSAFE_PCWSTR pszSrc, unsigned __int16)`
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14004fee8`
- `0x14005ac18`

## callees

- `0x1400018cc`
- `0x140001958`
- `0x140001a08`
- `0x140004553`
- `0x140004589`
- `0x14003e364`
- `0x140050724`
- `0x140050a14`

## string_xrefs

- `0x140050872`: `AslpPathWildcardAllocMatchNode`
- `0x140050918`: `RtlUnicodeStringCopy failed [%x]`
- `0x14005092a`: `Failed to open dir [%x]`

## pseudocode

```c
__int64 __fastcall AslpPathWildcardAllocMatchNode(
        PUNICODE_STRING DestinationString,
        PCUNICODE_STRING SourceString,
        _WORD *a3,
        int a4,
        NTSTRSAFE_PCWSTR pszSrc,
        unsigned __int16 a6)
{
  unsigned __int16 v8; // cx
  wchar_t *Pool2_0; // rax
  NTSTATUS v10; // eax
  const wchar_t *v11; // rdx
  unsigned int v12; // ebx
  const char *v14; // r9
  __int64 v15; // r8
  __int64 ShareAccess; // [rsp+20h] [rbp-58h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF

  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  *(_QWORD *)&DestinationString->Length = 0;
  DestinationString->Buffer = 0;
  DestinationString[1].Buffer = 0;
  while ( 1 )
  {
    *(_QWORD *)&DestinationString[1].Length = a3;
    if ( !*a3 )
      break;
    ++a3;
  }
  *(_QWORD *)&DestinationString[1].Length = a3 + 1;
  if ( !a3[1] )
  {
    v12 = a4 != 0 ? -1073741638 : -1073741197;
    goto LABEL_21;
  }
  if ( !a4 )
  {
    v12 = -1073741565;
    goto LABEL_21;
  }
  v8 = a6 + SourceString->Length;
  if ( v8 < SourceString->Length )
  {
    v10 = -1073741675;
    v14 = "RtlUShortAdd failed [%x]";
    v12 = -1073741675;
    v15 = 2886;
    goto LABEL_16;
  }
  if ( (unsigned __int16)(v8 + 4) < v8 )
  {
    v10 = -1073741675;
    v14 = "RtlUShortAdd failed [%x]";
    v12 = -1073741675;
    v15 = 2892;
    goto LABEL_16;
  }
  DestinationString->MaximumLength = v8 + 4;
  Pool2_0 = (wchar_t *)ExAllocatePool2_0(256, (unsigned __int16)(v8 + 4), 1953517633);
  DestinationString->Buffer = Pool2_0;
  if ( !Pool2_0 )
  {
    v12 = -1073741801;
    goto LABEL_21;
  }
  v10 = RtlUnicodeStringCopy(DestinationString, SourceString);
  v12 = v10;
  if ( v10 < 0 )
  {
    v14 = "RtlUnicodeStringCopy failed [%x]";
    v15 = 2907;
    goto LABEL_16;
  }
  if ( DestinationString->Buffer[((unsigned __int64)DestinationString->Length >> 1) - 1] != 92 )
  {
    v10 = RtlUnicodeStringCatString(DestinationString, v11);
    v12 = v10;
    if ( v10 < 0 )
    {
      v14 = "RtlUnicodeStringCatString failed [%x]";
      v15 = 2923;
LABEL_16:
      LODWORD(ShareAccess) = v10;
      AslLogCallPrintf(1, "AslpPathWildcardAllocMatchNode", v15, v14, ShareAccess);
LABEL_21:
      AslpPathWildcardFreeMatchNode(DestinationString);
      return v12;
    }
  }
  if ( pszSrc )
  {
    if ( a6 )
    {
      v10 = RtlUnicodeStringCbCatStringN(DestinationString, pszSrc, a6);
      v12 = v10;
      if ( v10 < 0 )
      {
        v14 = "RtlUnicodeStringCbCatStringN failed [%x]";
        v15 = 2931;
        goto LABEL_16;
      }
    }
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v10 = ZwOpenFile_0((PHANDLE)&DestinationString[1].Buffer, 0x100001u, &ObjectAttributes, &IoStatusBlock, 1u, 0x21u);
  v12 = v10;
  if ( v10 < 0 )
  {
    v14 = "Failed to open dir [%x]";
    v15 = 2945;
    goto LABEL_16;
  }
  return v12;
}

```

## disassembly

```asm
0x140050724  push    rbp
0x140050726  push    rbx
0x140050727  push    rdi
0x140050728  push    r14
0x14005072a  mov     rbp, rsp
0x14005072d  sub     rsp, 78h
0x140050731  xorps   xmm0, xmm0
0x140050734  xor     eax, eax
0x140050736  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14005073a  xor     r14d, r14d
0x14005073d  mov     rbx, rdx
0x140050740  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x140050744  mov     rdi, rcx
0x140050747  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14005074b  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x14005074f  mov     [rcx], r14
0x140050752  mov     [rcx+8], r14
0x140050756  mov     [rcx+18h], r14
0x14005075a  jmp     short loc_140050760
0x14005075c  add     r8, 2
0x140050760  mov     [rcx+10h], r8
0x140050764  cmp     [r8], r14w
0x140050768  jnz     short loc_14005075C
0x14005076a  lea     rax, [r8+2]
0x14005076e  mov     [rcx+10h], rax
0x140050772  cmp     [rax], r14w
0x140050776  jz      loc_1400508BA
0x14005077c  test    r9d, r9d
0x14005077f  jz      loc_1400508F8
0x140050785  movzx   eax, word ptr [rdx]
0x140050788  movzx   ecx, ax
0x14005078b  add     cx, [rbp+arg_28]
0x14005078f  cmp     cx, ax
0x140050792  jb      loc_1400508DF
0x140050798  lea     eax, [rcx+4]
0x14005079b  cmp     ax, cx
0x14005079e  jb      loc_1400508FF
0x1400507a4  movzx   edx, ax
0x1400507a7  mov     ecx, 100h
0x1400507ac  mov     r8d, 74705041h
0x1400507b2  mov     [rdi+2], ax
0x1400507b6  call    ExAllocatePool2_0
0x1400507bb  mov     [rdi+8], rax
0x1400507bf  test    rax, rax
0x1400507c2  jz      loc_1400508D8
0x1400507c8  mov     rdx, rbx; SourceString
0x1400507cb  mov     rcx, rdi; DestinationString
0x1400507ce  call    RtlUnicodeStringCopy
0x1400507d3  mov     ebx, eax
0x1400507d5  test    eax, eax
0x1400507d7  js      loc_140050918
0x1400507dd  movzx   ecx, word ptr [rdi]
0x1400507e0  mov     rax, [rdi+8]
0x1400507e4  shr     rcx, 1
0x1400507e7  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x1400507ed  jnz     short loc_140050857
0x1400507ef  mov     rdx, [rbp+pszSrc]; pszSrc
0x1400507f3  test    rdx, rdx
0x1400507f6  jnz     loc_140050889
0x1400507fc  xorps   xmm0, xmm0
0x1400507ff  mov     [rsp+78h+OpenOptions], 21h ; '!'; OpenOptions
0x140050807  lea     rcx, [rdi+18h]; FileHandle
0x14005080b  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140050812  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x140050816  mov     [rbp+ObjectAttributes.RootDirectory], r14
0x14005081a  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14005081e  mov     [rbp+ObjectAttributes.Attributes], 240h
0x140050825  mov     edx, 100001h; DesiredAccess
0x14005082a  mov     [rbp+ObjectAttributes.ObjectName], rdi
0x14005082e  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140050833  mov     dword ptr [rsp+78h+ShareAccess], 1; ShareAccess
0x14005083b  call    ZwOpenFile_0
0x140050840  mov     ebx, eax
0x140050842  test    eax, eax
0x140050844  js      loc_14005092A
0x14005084a  mov     eax, ebx
0x14005084c  add     rsp, 78h
0x140050850  pop     r14
0x140050852  pop     rdi
0x140050853  pop     rbx
0x140050854  pop     rbp
0x140050855  retn
0x140050857  mov     rcx, rdi; DestinationString
0x14005085a  call    RtlUnicodeStringCatString
0x14005085f  mov     ebx, eax
0x140050861  test    eax, eax
0x140050863  jns     short loc_1400507EF
0x140050865  lea     r9, aRtlunicodestri_0; "RtlUnicodeStringCatString failed [%x]"
0x14005086c  mov     r8d, 0B6Bh
0x140050872  lea     rdx, aAslppathwildca_7; "AslpPathWildcardAllocMatchNode"
0x140050879  mov     dword ptr [rsp+78h+ShareAccess], eax
0x14005087d  mov     ecx, 1
0x140050882  call    AslLogCallPrintf
0x140050887  jmp     short loc_1400508CB
0x140050889  cmp     [rbp+arg_28], r14w
0x14005088e  jbe     loc_1400507FC
0x140050894  movzx   r8d, [rbp+arg_28]; cbToAppend
0x140050899  mov     rcx, rdi; DestinationString
0x14005089c  call    RtlUnicodeStringCbCatStringN
0x1400508a1  mov     ebx, eax
0x1400508a3  test    eax, eax
0x1400508a5  jns     loc_1400507FC
0x1400508ab  lea     r9, aRtlunicodestri; "RtlUnicodeStringCbCatStringN failed [%x"...
0x1400508b2  mov     r8d, 0B73h
0x1400508b8  jmp     short loc_140050872
0x1400508ba  neg     r9d
0x1400508bd  sbb     ebx, ebx
0x1400508bf  and     ebx, 0FFFFFE47h
0x1400508c5  add     ebx, 0C0000273h
0x1400508cb  mov     rcx, rdi
0x1400508ce  call    AslpPathWildcardFreeMatchNode
0x1400508d3  jmp     loc_14005084A
0x1400508d8  mov     ebx, 0C0000017h
0x1400508dd  jmp     short loc_1400508CB
0x1400508df  mov     eax, 0C0000095h
0x1400508e4  lea     r9, aRtlushortaddFa; "RtlUShortAdd failed [%x]"
0x1400508eb  mov     ebx, eax
0x1400508ed  mov     r8d, 0B46h
0x1400508f3  jmp     loc_140050872
0x1400508f8  mov     ebx, 0C0000103h
0x1400508fd  jmp     short loc_1400508CB
0x1400508ff  mov     eax, 0C0000095h
0x140050904  lea     r9, aRtlushortaddFa; "RtlUShortAdd failed [%x]"
0x14005090b  mov     ebx, eax
0x14005090d  mov     r8d, 0B4Ch
0x140050913  jmp     loc_140050872
0x140050918  lea     r9, aRtlunicodestri_1; "RtlUnicodeStringCopy failed [%x]"
0x14005091f  mov     r8d, 0B5Bh
0x140050925  jmp     loc_140050872
0x14005092a  lea     r9, aFailedToOpenDi; "Failed to open dir [%x]"
0x140050931  mov     r8d, 0B81h
0x140050937  jmp     loc_140050872
```
