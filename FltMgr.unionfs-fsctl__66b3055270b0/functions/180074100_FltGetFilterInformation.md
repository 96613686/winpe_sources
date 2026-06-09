# FltGetFilterInformation

- ea: `0x180074100`
- end: `0x18007428e`
- name: `FltGetFilterInformation`
- size: `398`
- prototype: `NTSTATUS __stdcall(PFLT_FILTER Filter, FILTER_INFORMATION_CLASS InformationClass, PVOID Buffer, ULONG BufferSize, PULONG BytesReturned)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180056538`
- `0x180073b50`
- `0x180076d00`

## callees

- `0x180024900`
- `0x180074100`
- `0x1800742a0`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1800741aa`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1800741ea`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18007b1b9`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18007b1f9`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1800741aa`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1800741ea`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18007b1b9`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18007b1f9`

## pseudocode

```c
NTSTATUS __stdcall FltGetFilterInformation(
        PFLT_FILTER Filter,
        FILTER_INFORMATION_CLASS InformationClass,
        PVOID Buffer,
        ULONG BufferSize,
        PULONG BytesReturned)
{
  _UNICODE_STRING *p_Name; // r14
  unsigned __int16 v8; // si
  _UNICODE_STRING *p_DefaultAltitude; // r12
  NTSTATUS result; // eax
  unsigned __int16 Length; // ax
  __int64 v12; // rdi
  unsigned __int16 v13; // ax
  __int64 v14; // rdi
  UNICODE_STRING DestinationString; // [rsp+20h] [rbp-38h] BYREF

  DestinationString = 0;
  *BytesReturned = 0;
  if ( InformationClass )
  {
    if ( InformationClass == FilterAggregateBasicInformation )
    {
      p_DefaultAltitude = &Filter->DefaultAltitude;
      p_Name = &Filter->Name;
      v8 = Filter->Name.Length + Filter->DefaultAltitude.Length + 24;
    }
    else
    {
      if ( InformationClass != FilterAggregateStandardInformation )
        return -1073741811;
      p_DefaultAltitude = &Filter->DefaultAltitude;
      p_Name = &Filter->Name;
      v8 = Filter->Name.Length + Filter->DefaultAltitude.Length + 28;
    }
  }
  else
  {
    p_Name = &Filter->Name;
    v8 = Filter->Name.Length + 14;
    p_DefaultAltitude = &Filter->DefaultAltitude;
  }
  if ( BufferSize < v8 )
  {
    result = -1073741789;
    goto LABEL_8;
  }
  if ( InformationClass == FilterAggregateStandardInformation )
  {
    *(_DWORD *)Buffer = 0;
    *(_QWORD *)((char *)Buffer + 4) = 1;
    *((_DWORD *)Buffer + 3) = Filter->Frame->FrameID;
    result = FltpFilterCountInstances(Filter, (char *)Buffer + 16);
    if ( result < 0 )
      return result;
    DestinationString.Length = 0;
    DestinationString.MaximumLength = v8 - 28;
    DestinationString.Buffer = (wchar_t *)((char *)Buffer + 28);
    RtlCopyUnicodeString(&DestinationString, p_Name);
    Length = p_Name->Length;
    *((_WORD *)Buffer + 10) = p_Name->Length;
    *((_WORD *)Buffer + 11) = 28;
    v12 = (unsigned __int16)(Length + 28);
    DestinationString.Length = 0;
    DestinationString.MaximumLength = v8 - v12;
    DestinationString.Buffer = (wchar_t *)((char *)Buffer + v12);
    RtlCopyUnicodeString(&DestinationString, p_DefaultAltitude);
    *((_WORD *)Buffer + 12) = p_DefaultAltitude->Length;
    *((_WORD *)Buffer + 13) = v12;
    goto LABEL_7;
  }
  if ( InformationClass )
  {
    *(_DWORD *)Buffer = 0;
    *((_DWORD *)Buffer + 1) = 1;
    *((_DWORD *)Buffer + 2) = Filter->Frame->FrameID;
    result = FltpFilterCountInstances(Filter, (char *)Buffer + 12);
    if ( result >= 0 )
    {
      DestinationString.Length = 0;
      DestinationString.MaximumLength = v8 - 24;
      DestinationString.Buffer = (wchar_t *)((char *)Buffer + 24);
      RtlCopyUnicodeString(&DestinationString, p_Name);
      v13 = p_Name->Length;
      *((_WORD *)Buffer + 8) = p_Name->Length;
      *((_WORD *)Buffer + 9) = 24;
      v14 = (unsigned __int16)(v13 + 24);
      DestinationString.Length = 0;
      DestinationString.MaximumLength = v8 - v14;
      DestinationString.Buffer = (wchar_t *)((char *)Buffer + v14);
      RtlCopyUnicodeString(&DestinationString, p_DefaultAltitude);
      *((_WORD *)Buffer + 10) = p_DefaultAltitude->Length;
      *((_WORD *)Buffer + 11) = v14;
LABEL_7:
      result = 0;
LABEL_8:
      *BytesReturned = v8;
    }
  }
  else
  {
    *(_DWORD *)Buffer = 0;
    *((_DWORD *)Buffer + 1) = Filter->Frame->FrameID;
    result = FltpFilterCountInstances(Filter, (char *)Buffer + 8);
    if ( result >= 0 )
    {
      *((_WORD *)Buffer + 6) = p_Name->Length;
      memmove((char *)Buffer + 14, Filter->Name.Buffer, p_Name->Length);
      goto LABEL_7;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180074100  mov     [rsp+arg_8], rbx
0x180074105  mov     [rsp+arg_10], rsi
0x18007410a  push    rdi
0x18007410b  push    r12
0x18007410d  push    r13
0x18007410f  push    r14
0x180074111  push    r15
0x180074113  sub     rsp, 30h
0x180074117  mov     r15, [rsp+58h+BytesReturned]
0x18007411f  xor     r13d, r13d
0x180074122  xorps   xmm0, xmm0
0x180074125  mov     rbx, r8
0x180074128  mov     rdi, rcx
0x18007412b  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x180074130  mov     [r15], r13d
0x180074133  test    edx, edx
0x180074135  jnz     loc_180074227
0x18007413b  movzx   esi, word ptr [rcx+40h]
0x18007413f  lea     r14, [rcx+40h]
0x180074143  add     si, 0Eh
0x180074147  lea     r12, [rcx+50h]
0x18007414b  mov     [rsp+58h+arg_0], rbp
0x180074150  movzx   ebp, si
0x180074153  cmp     r9d, ebp
0x180074156  jb      loc_18007426C
0x18007415c  cmp     edx, 2
0x18007415f  jnz     loc_180074273
0x180074165  mov     [r8], r13d
0x180074168  lea     rdx, [r8+10h]
0x18007416c  mov     qword ptr [r8+4], 1
0x180074174  mov     rax, [rdi+38h]
0x180074178  mov     ecx, [rax+18h]
0x18007417b  mov     [r8+0Ch], ecx
0x18007417f  mov     rcx, rdi
0x180074182  call    FltpFilterCountInstances
0x180074187  test    eax, eax
0x180074189  js      short loc_180074209
0x18007418b  lea     eax, [rsi-1Ch]
0x18007418e  mov     [rsp+58h+DestinationString.Length], r13w
0x180074194  mov     [rsp+58h+DestinationString.MaximumLength], ax
0x180074199  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x18007419e  lea     rax, [rbx+1Ch]
0x1800741a2  mov     rdx, r14; SourceString
0x1800741a5  mov     [rsp+58h+DestinationString.Buffer], rax
0x1800741aa  call    cs:__imp_RtlCopyUnicodeString
0x1800741b1  nop     dword ptr [rax+rax+00h]
0x1800741b6  movzx   eax, word ptr [r14]
0x1800741ba  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x1800741bf  mov     [rbx+14h], ax
0x1800741c3  mov     rdx, r12; SourceString
0x1800741c6  add     ax, 1Ch
0x1800741ca  mov     word ptr [rbx+16h], 1Ch
0x1800741d0  movzx   edi, ax
0x1800741d3  sub     si, di
0x1800741d6  mov     [rsp+58h+DestinationString.Length], r13w
0x1800741dc  mov     [rsp+58h+DestinationString.MaximumLength], si
0x1800741e1  lea     rax, [rbx+rdi]
0x1800741e5  mov     [rsp+58h+DestinationString.Buffer], rax
0x1800741ea  call    cs:__imp_RtlCopyUnicodeString
0x1800741f1  nop     dword ptr [rax+rax+00h]
0x1800741f6  movzx   eax, word ptr [r12]
0x1800741fb  mov     [rbx+18h], ax
0x1800741ff  mov     [rbx+1Ah], di
0x180074203  mov     eax, r13d
0x180074206  mov     [r15], ebp
0x180074209  mov     rbp, [rsp+58h+arg_0]
0x18007420e  mov     rbx, [rsp+58h+arg_8]
0x180074213  mov     rsi, [rsp+58h+arg_10]
0x180074218  add     rsp, 30h
0x18007421c  pop     r15
0x18007421e  pop     r14
0x180074220  pop     r13
0x180074222  pop     r12
0x180074224  pop     rdi
0x180074225  retn
0x180074227  mov     ecx, edx
0x180074229  sub     ecx, 1
0x18007422c  jz      short loc_180074253
0x18007422e  cmp     ecx, 1
0x180074231  jz      short loc_18007423A
0x180074233  mov     eax, 0C000000Dh
0x180074238  jmp     short loc_18007420E
0x18007423a  movzx   esi, word ptr [rdi+50h]
0x18007423e  lea     r12, [rdi+50h]
0x180074242  add     si, 1Ch
0x180074246  lea     r14, [rdi+40h]
0x18007424a  add     si, [r14]
0x18007424e  jmp     loc_18007414B
0x180074253  movzx   esi, word ptr [rdi+50h]
0x180074257  lea     r12, [rdi+50h]
0x18007425b  add     si, 18h
0x18007425f  lea     r14, [rdi+40h]
0x180074263  add     si, [r14]
0x180074267  jmp     loc_18007414B
0x18007426c  mov     eax, 0C0000023h
0x180074271  jmp     short loc_180074206
0x180074273  test    edx, edx
0x180074275  jz      loc_18007B217
0x18007427b  cmp     edx, 1
0x18007427e  jz      loc_18007B170
0x180074284  mov     eax, 0C000000Dh
0x180074289  jmp     loc_180074209
0x18007b170  mov     [r8], r13d
0x18007b173  lea     rdx, [r8+0Ch]
0x18007b177  mov     dword ptr [r8+4], 1
0x18007b17f  mov     rax, [rdi+38h]
0x18007b183  mov     ecx, [rax+18h]
0x18007b186  mov     [r8+8], ecx
0x18007b18a  mov     rcx, rdi
0x18007b18d  call    FltpFilterCountInstances
0x18007b192  test    eax, eax
0x18007b194  js      loc_180074209
0x18007b19a  lea     eax, [rsi-18h]
0x18007b19d  mov     [rsp+58h+DestinationString.Length], r13w
0x18007b1a3  mov     [rsp+58h+DestinationString.MaximumLength], ax
0x18007b1a8  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x18007b1ad  lea     rax, [rbx+18h]
0x18007b1b1  mov     rdx, r14; SourceString
0x18007b1b4  mov     [rsp+58h+DestinationString.Buffer], rax
0x18007b1b9  call    cs:__imp_RtlCopyUnicodeString
0x18007b1c0  nop     dword ptr [rax+rax+00h]
0x18007b1c5  movzx   eax, word ptr [r14]
0x18007b1c9  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x18007b1ce  mov     [rbx+10h], ax
0x18007b1d2  mov     rdx, r12; SourceString
0x18007b1d5  add     ax, 18h
0x18007b1d9  mov     word ptr [rbx+12h], 18h
0x18007b1df  movzx   edi, ax
0x18007b1e2  sub     si, di
0x18007b1e5  mov     [rsp+58h+DestinationString.Length], r13w
0x18007b1eb  mov     [rsp+58h+DestinationString.MaximumLength], si
0x18007b1f0  lea     rax, [rbx+rdi]
0x18007b1f4  mov     [rsp+58h+DestinationString.Buffer], rax
0x18007b1f9  call    cs:__imp_RtlCopyUnicodeString
0x18007b200  nop     dword ptr [rax+rax+00h]
0x18007b205  movzx   eax, word ptr [r12]
0x18007b20a  mov     [rbx+14h], ax
0x18007b20e  mov     [rbx+16h], di
0x18007b212  jmp     loc_180074203
0x18007b217  mov     [r8], r13d
0x18007b21a  lea     rdx, [r8+8]
0x18007b21e  mov     rax, [rdi+38h]
0x18007b222  mov     ecx, [rax+18h]
0x18007b225  mov     [r8+4], ecx
0x18007b229  mov     rcx, rdi
0x18007b22c  call    FltpFilterCountInstances
0x18007b231  test    eax, eax
0x18007b233  js      loc_180074209
0x18007b239  movzx   eax, word ptr [r14]
0x18007b23d  lea     rcx, [rbx+0Eh]; void *
0x18007b241  mov     [rbx+0Ch], ax
0x18007b245  movzx   r8d, word ptr [r14]; Size
0x18007b249  mov     rdx, [rdi+48h]; Src
0x18007b24d  call    memmove
0x18007b252  nop
0x18007b253  jmp     loc_180074203
```
