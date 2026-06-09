# IsProcessListedUnderRegistryKey

- ea: `0x1400016ac`
- end: `0x1400018ae`
- name: `IsProcessListedUnderRegistryKey`
- size: `514`
- prototype: `unsigned __int8 __fastcall(PCUNICODE_STRING Source, PCUNICODE_STRING SourceString, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000aca0`

## callees

- `0x140001118`
- `0x140001168`
- `0x1400011b0`
- `0x140001298`
- `0x1400015c0`
- `0x14000164c`
- `0x1400016ac`
- `0x140001b40`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400017b5`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400017b5`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400017a1`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400017a1`
- `ntoskrnl!ZwOpenKey` at `0x1400017ff`
- `ntoskrnl!ZwOpenKey` at `0x1400017ff`
- `ntoskrnl!ZwClose` at `0x14000187d`
- `ntoskrnl!ZwClose` at `0x1400020a1`
- `ntoskrnl!ZwClose` at `0x14000187d`
- `ntoskrnl!ZwClose` at `0x1400020a1`

## string_xrefs

- `0x140001714`: `UevFilter.IsMonitoredProcess: Invalid parameter: pRegistryKey parameter is NULL.\n`

## pseudocode

```c
unsigned __int8 __fastcall IsProcessListedUnderRegistryKey(
        PCUNICODE_STRING Source,
        PCUNICODE_STRING SourceString,
        __int64 a3)
{
  unsigned __int8 v5; // si
  __int64 v6; // rdx
  __int64 v7; // r8
  const CHAR *v8; // rcx
  __int64 v9; // r8
  USHORT Length; // bx
  USHORT v11; // di
  __int64 v12; // rcx
  int GenericBuffer; // ebx
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 v16; // r8
  _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-78h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-68h] BYREF
  void *KeyHandle; // [rsp+B0h] [rbp+18h] BYREF

  v5 = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  memset(&ObjectAttributes, 0, 44);
  KeyHandle = 0;
  DbgTrace(2, "UevFilter.IsMonitoredProcess: Entry\n", a3);
  if ( !Source )
  {
    v8 = "UevFilter.IsMonitoredProcess: Invalid parameter: pProcessName parameter is NULL.\n";
LABEL_3:
    DbgTraceErr(v8, v6, v7);
    goto LABEL_13;
  }
  if ( !SourceString )
  {
    v8 = "UevFilter.IsMonitoredProcess: Invalid parameter: pRegistryKey parameter is NULL.\n";
    goto LABEL_3;
  }
  Length = SourceString->Length;
  v11 = Source->Length;
  DbgTrace(3, "UevFilter.AllocateGenericUnicodeString: Entry\n", v7);
  DestinationString.Length = 0;
  DestinationString.MaximumLength = Length + v11 + 2;
  GenericBuffer = AllocateGenericBuffer(v12, DestinationString.MaximumLength, (__int64 *)&DestinationString.Buffer);
  if ( GenericBuffer >= 0 )
    memset(DestinationString.Buffer, 0, DestinationString.MaximumLength);
  DbgTraceFrmt(3u, "UevFilter.AllocateGenericUnicodeString: Exit, status = 0x%X\n", GenericBuffer);
  if ( GenericBuffer >= 0 )
  {
    RtlCopyUnicodeString(&DestinationString, SourceString);
    RtlAppendUnicodeStringToString(&DestinationString, Source);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = &DestinationString;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
      v5 = 1;
    else
      KeyHandle = 0;
  }
  else
  {
    DbgTraceFrmtErr("UevFilter.IsMonitoredProcess: Failed to allocate buffer, status = 0x%X\n", GenericBuffer);
  }
LABEL_13:
  if ( DestinationString.Buffer )
  {
    DbgTrace(3, "UevFilter.FreeGenericUnicodeString: Entry\n", v9);
    if ( DestinationString.Buffer )
    {
      FreeGenericBuffer(DestinationString.Buffer, v14, v15);
      DestinationString.Buffer = 0;
    }
    else
    {
      DbgTraceErr("UevFilter.FreeGenericUnicodeString: Invalid parameter specified\n", v14, v15);
    }
    DbgTrace(3, "UevFilter.FreeGenericUnicodeString: Exit\n", v16);
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  DbgTraceFrmt(2u, "UevFilter.IsMonitoredProcess: Exit, retValue = 0x%X\n", v5);
  return v5;
}

```

## disassembly

```asm
0x1400016ac  mov     r11, rsp
0x1400016af  push    rbx
0x1400016b0  push    rsi
0x1400016b1  push    rdi
0x1400016b2  push    r13
0x1400016b4  push    r14
0x1400016b6  push    r15
0x1400016b8  sub     rsp, 68h
0x1400016bc  mov     r14, rdx
0x1400016bf  mov     r15, rcx
0x1400016c2  xor     sil, sil
0x1400016c5  xor     eax, eax
0x1400016c7  mov     [r11-78h], rax
0x1400016cb  mov     [r11-70h], rax
0x1400016cf  xorps   xmm0, xmm0
0x1400016d2  movups  xmmword ptr [rsp+98h+ObjectAttributes.Length], xmm0
0x1400016d7  movups  xmmword ptr [rsp+98h+ObjectAttributes.ObjectName], xmm0
0x1400016dc  movups  xmmword ptr [rsp+98h+ObjectAttributes+1Ch], xmm0
0x1400016e1  mov     [r11+18h], rax
0x1400016e5  lea     rdx, aUevfilterIsmon_2; "UevFilter.IsMonitoredProcess: Entry\n"
0x1400016ec  lea     r13d, [rax+2]
0x1400016f0  mov     ecx, r13d
0x1400016f3  call    DbgTrace
0x1400016f8  nop
0x1400016f9  test    r15, r15
0x1400016fc  jnz     short loc_14000170F
0x1400016fe  lea     rcx, aUevfilterIsmon_1; "UevFilter.IsMonitoredProcess: Invalid p"...
0x140001705  call    DbgTraceErr
0x14000170a  jmp     loc_140001820
0x14000170f  test    r14, r14
0x140001712  jnz     short loc_14000171D
0x140001714  lea     rcx, aUevfilterIsmon; "UevFilter.IsMonitoredProcess: Invalid p"...
0x14000171b  jmp     short loc_140001705
0x14000171d  movzx   ebx, word ptr [r14]
0x140001721  movzx   edi, word ptr [r15]
0x140001725  lea     rdx, aUevfilterAlloc_3; "UevFilter.AllocateGenericUnicodeString:"...
0x14000172c  mov     ecx, 3
0x140001731  call    DbgTrace
0x140001736  xor     eax, eax
0x140001738  mov     [rsp+98h+DestinationString.Length], ax
0x14000173d  add     di, bx
0x140001740  add     di, r13w
0x140001744  movzx   edx, di
0x140001747  mov     [rsp+98h+DestinationString.MaximumLength], dx
0x14000174c  lea     r8, [rsp+98h+DestinationString.Buffer]
0x140001751  call    AllocateGenericBuffer
0x140001756  mov     ebx, eax
0x140001758  test    eax, eax
0x14000175a  js      short loc_14000176E
0x14000175c  movzx   r8d, [rsp+98h+DestinationString.MaximumLength]; Size
0x140001762  xor     edx, edx; Val
0x140001764  mov     rcx, [rsp+98h+DestinationString.Buffer]; void *
0x140001769  call    memset
0x14000176e  mov     r8d, ebx
0x140001771  lea     rdx, aUevfilterAlloc; "UevFilter.AllocateGenericUnicodeString:"...
0x140001778  mov     ecx, 3
0x14000177d  call    DbgTraceFrmt
0x140001782  test    ebx, ebx
0x140001784  jns     short loc_140001799
0x140001786  mov     edx, ebx
0x140001788  lea     rcx, aUevfilterIsmon_3; "UevFilter.IsMonitoredProcess: Failed to"...
0x14000178f  call    DbgTraceFrmtErr
0x140001794  jmp     loc_140001820
0x140001799  mov     rdx, r14; SourceString
0x14000179c  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x1400017a1  call    cs:__imp_RtlCopyUnicodeString
0x1400017a8  nop     dword ptr [rax+rax+00h]
0x1400017ad  mov     rdx, r15; Source
0x1400017b0  lea     rcx, [rsp+98h+DestinationString]; Destination
0x1400017b5  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400017bc  nop     dword ptr [rax+rax+00h]
0x1400017c1  mov     [rsp+98h+ObjectAttributes.Length], 30h ; '0'
0x1400017c9  mov     [rsp+98h+ObjectAttributes.RootDirectory], 0
0x1400017d2  mov     [rsp+98h+ObjectAttributes.Attributes], 240h
0x1400017da  lea     rax, [rsp+98h+DestinationString]
0x1400017df  mov     [rsp+98h+ObjectAttributes.ObjectName], rax
0x1400017e4  xorps   xmm0, xmm0
0x1400017e7  movdqu  xmmword ptr [rsp+98h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400017ed  lea     r8, [rsp+98h+ObjectAttributes]; ObjectAttributes
0x1400017f2  mov     edx, 20019h; DesiredAccess
0x1400017f7  lea     rcx, [rsp+98h+KeyHandle]; KeyHandle
0x1400017ff  call    cs:__imp_ZwOpenKey
0x140001806  nop     dword ptr [rax+rax+00h]
0x14000180b  test    eax, eax
0x14000180d  jns     short loc_14000181D
0x14000180f  mov     [rsp+98h+KeyHandle], 0
0x14000181b  jmp     short loc_140001820
0x14000181d  mov     sil, 1
0x140001820  cmp     [rsp+98h+DestinationString.Buffer], 0
0x140001826  jz      short loc_140001870
0x140001828  lea     rdx, aUevfilterFreeg; "UevFilter.FreeGenericUnicodeString: Ent"...
0x14000182f  mov     ecx, 3
0x140001834  call    DbgTrace
0x140001839  mov     rcx, [rsp+98h+DestinationString.Buffer]; P
0x14000183e  test    rcx, rcx
0x140001841  jz      short loc_140001853
0x140001843  call    FreeGenericBuffer
0x140001848  mov     [rsp+98h+DestinationString.Buffer], 0
0x140001851  jmp     short loc_14000185F
0x140001853  lea     rcx, aUevfilterFreeg_2; "UevFilter.FreeGenericUnicodeString: Inv"...
0x14000185a  call    DbgTraceErr
0x14000185f  lea     rdx, aUevfilterFreeg_0; "UevFilter.FreeGenericUnicodeString: Exi"...
0x140001866  mov     ecx, 3
0x14000186b  call    DbgTrace
0x140001870  mov     rcx, [rsp+98h+KeyHandle]; Handle
0x140001878  test    rcx, rcx
0x14000187b  jz      short loc_140001889
0x14000187d  call    cs:__imp_ZwClose
0x140001884  nop     dword ptr [rax+rax+00h]
0x140001889  movzx   r8d, sil
0x14000188d  lea     rdx, aUevfilterIsmon_0; "UevFilter.IsMonitoredProcess: Exit, ret"...
0x140001894  mov     ecx, r13d
0x140001897  call    DbgTraceFrmt
0x14000189c  mov     al, sil
0x14000189f  add     rsp, 68h
0x1400018a3  pop     r15
0x1400018a5  pop     r14
0x1400018a7  pop     r13
0x1400018a9  pop     rdi
0x1400018aa  pop     rsi
0x1400018ab  pop     rbx
0x1400018ac  retn
0x14000203d  push    rbp
0x14000203f  sub     rsp, 20h
0x140002043  mov     rbp, rdx
0x140002046  cmp     qword ptr [rbp+28h], 0
0x14000204b  jz      short loc_140002095
0x14000204d  lea     rdx, aUevfilterFreeg; "UevFilter.FreeGenericUnicodeString: Ent"...
0x140002054  mov     ecx, 3
0x140002059  call    DbgTrace
0x14000205e  mov     rcx, [rbp+28h]; P
0x140002062  test    rcx, rcx
0x140002065  jz      short loc_140002076
0x140002067  call    FreeGenericBuffer
0x14000206c  mov     qword ptr [rbp+28h], 0
0x140002074  jmp     short loc_140002083
0x140002076  lea     rcx, aUevfilterFreeg_2; "UevFilter.FreeGenericUnicodeString: Inv"...
0x14000207d  call    DbgTraceErr
0x140002082  nop
0x140002083  lea     rdx, aUevfilterFreeg_0; "UevFilter.FreeGenericUnicodeString: Exi"...
0x14000208a  mov     ecx, 3
0x14000208f  call    DbgTrace
0x140002094  nop
0x140002095  mov     rcx, [rbp+0B0h]; Handle
0x14000209c  test    rcx, rcx
0x14000209f  jz      short loc_1400020AE
0x1400020a1  call    cs:__imp_ZwClose
0x1400020a8  nop     dword ptr [rax+rax+00h]
0x1400020ad  nop
0x1400020ae  add     rsp, 20h
0x1400020b2  pop     rbp
0x1400020b3  retn
```
