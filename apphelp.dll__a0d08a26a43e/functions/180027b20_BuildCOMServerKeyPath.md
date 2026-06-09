# BuildCOMServerKeyPath

- ea: `0x180027b20`
- end: `0x180027daa`
- name: `BuildCOMServerKeyPath`
- size: `650`
- prototype: `char __fastcall(GUID *Guid, int, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180027a50`

## callees

- `0x18000f114`
- `0x180027b20`
- `0x18003988c`
- `0x180059169`
- `0x180059175`
- `0x1800591b0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180027cbf`
- `ntdll!RtlFreeHeap` at `0x180027cbf`
- `ntdll!RtlFreeUnicodeString` at `0x180027c8e`
- `ntdll!RtlFreeUnicodeString` at `0x180027c9f`
- `ntdll!RtlFreeUnicodeString` at `0x180027c8e`
- `ntdll!RtlFreeUnicodeString` at `0x180027c9f`
- `ntdll!RtlDuplicateUnicodeString` at `0x180027c74`
- `ntdll!RtlDuplicateUnicodeString` at `0x180027c74`
- `ntdll!RtlStringFromGUID` at `0x180027c02`
- `ntdll!RtlStringFromGUID` at `0x180027c02`
- `ntdll!RtlAppendUnicodeToString` at `0x180027bed`
- `ntdll!RtlAppendUnicodeToString` at `0x180027c44`
- `ntdll!RtlAppendUnicodeToString` at `0x180027c5d`
- `ntdll!RtlAppendUnicodeToString` at `0x180027bed`
- `ntdll!RtlAppendUnicodeToString` at `0x180027c44`
- `ntdll!RtlAppendUnicodeToString` at `0x180027c5d`
- `ntdll!RtlCopyUnicodeString` at `0x180027bdc`
- `ntdll!RtlCopyUnicodeString` at `0x180027bdc`
- `ntdll!RtlAllocateHeap` at `0x180027bbc`
- `ntdll!RtlAllocateHeap` at `0x180027bbc`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x180027cf9`
- `ntdll!RtlFormatCurrentUserKeyPath` at `0x180027cf9`
- `ntdll!RtlInitUnicodeStringEx` at `0x180027b87`
- `ntdll!RtlInitUnicodeStringEx` at `0x180027b87`

## string_xrefs

- `0x180027b7c`: `\Registry\Machine`
- `0x180027be2`: `\Software\Classes\CLSID\`
- `0x180027d15`: `BuildCOMServerKeyPath`
- `0x180027d35`: `BuildCOMServerKeyPath`
- `0x180027d62`: `BuildCOMServerKeyPath`
- `0x180027d26`: `Failed to allocate memory to store entire key path`
- `0x180027d07`: `Failed to format current user key path.`
- `0x180027d46`: `Failed to append CLSID onto existing key path`
- `0x180027d86`: `Failed to append CLSID onto existing key path`
- `0x180027d5b`: `Failed to initialize key path.`
- `0x180027d77`: `Failed to append subkey path to key base key path`
- `0x180027d95`: `Failed to fill return value buffer with key path`

## pseudocode

```c
char __fastcall BuildCOMServerKeyPath(GUID *Guid, int a2, struct _UNICODE_STRING *a3)
{
  char v6; // si
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // rdi
  __int64 v9; // rcx
  const char *v11; // r9
  __int64 v12; // r8
  struct _UNICODE_STRING Destination; // [rsp+20h] [rbp-69h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-59h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+40h] [rbp-49h] BYREF
  WCHAR Source[48]; // [rsp+50h] [rbp-39h] BYREF

  memset_0(Source, 0, 0x52u);
  v6 = 0;
  GuidString = 0;
  Destination = 0;
  DestinationString = 0;
  if ( a2 )
  {
    if ( a2 == 1 && RtlFormatCurrentUserKeyPath(&DestinationString) < 0 )
    {
      AslLogCallPrintf(
        1,
        "BuildCOMServerKeyPath",
        110,
        "Failed to format current user key path.",
        *(_QWORD *)&Destination.Length);
LABEL_13:
      RtlFreeUnicodeString(&DestinationString);
      goto LABEL_14;
    }
LABEL_3:
    Destination.Length = 0;
    Destination.MaximumLength = DestinationString.Length + 208;
    Destination.Buffer = (PWSTR)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, DestinationString.Length + 208LL);
    if ( Destination.Buffer )
    {
      RtlCopyUnicodeString(&Destination, &DestinationString);
      if ( RtlAppendUnicodeToString(&Destination, L"\\Software\\Classes\\CLSID\\") < 0 )
      {
        v11 = "Failed to append subkey path to key base key path";
        v12 = 149;
      }
      else
      {
        if ( RtlStringFromGUID(Guid, &GuidString) < 0 || (v7 = GuidString.Length >> 1, (unsigned int)v7 > 0x28) )
        {
LABEL_12:
          if ( a2 != 1 )
            goto LABEL_14;
          goto LABEL_13;
        }
        v8 = v7;
        memmove_0(Source, GuidString.Buffer, 2 * v7);
        if ( v8 >= 41 )
          _report_rangecheckfailure(v9);
        Source[v8] = 0;
        if ( RtlAppendUnicodeToString(&Destination, Source) < 0 )
        {
          v11 = "Failed to append CLSID onto existing key path";
          v12 = 174;
        }
        else
        {
          if ( RtlAppendUnicodeToString(&Destination, L"\\InProcServer32") < 0 )
          {
            AslLogCallPrintf(
              1,
              "BuildCOMServerKeyPath",
              183,
              "Failed to append CLSID onto existing key path",
              *(_QWORD *)&Destination.Length);
            goto LABEL_12;
          }
          if ( RtlDuplicateUnicodeString(1u, &Destination, a3) >= 0 )
          {
            v6 = 1;
            goto LABEL_12;
          }
          v11 = "Failed to fill return value buffer with key path";
          v12 = 194;
        }
      }
    }
    else
    {
      v11 = "Failed to allocate memory to store entire key path";
      v12 = 134;
    }
    AslLogCallPrintf(1, "BuildCOMServerKeyPath", v12, v11, *(_QWORD *)&Destination.Length);
    goto LABEL_12;
  }
  if ( RtlInitUnicodeStringEx(&DestinationString, L"\\Registry\\Machine") >= 0 )
    goto LABEL_3;
  AslLogCallPrintf(1, "BuildCOMServerKeyPath", 100, "Failed to initialize key path.", *(_QWORD *)&Destination.Length);
LABEL_14:
  if ( GuidString.Buffer )
    RtlFreeUnicodeString(&GuidString);
  if ( Destination.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Destination.Buffer);
  return v6;
}

```

## disassembly

```asm
0x180027b20  mov     [rsp-8+arg_8], rbx
0x180027b25  push    rbp
0x180027b26  push    rsi
0x180027b27  push    rdi
0x180027b28  push    r14
0x180027b2a  push    r15
0x180027b2c  lea     rbp, [rsp-37h]
0x180027b31  sub     rsp, 0C0h
0x180027b38  mov     rax, cs:__security_cookie
0x180027b3f  xor     rax, rsp
0x180027b42  mov     [rbp+57h+var_30], rax
0x180027b46  mov     r14d, edx
0x180027b49  mov     r15, r8
0x180027b4c  xor     edx, edx; Val
0x180027b4e  mov     rdi, rcx
0x180027b51  lea     rcx, [rbp+57h+Source]; void *
0x180027b55  lea     r8d, [rdx+52h]; Size
0x180027b59  call    memset_0
0x180027b5e  xorps   xmm0, xmm0
0x180027b61  xor     sil, sil
0x180027b64  xorps   xmm1, xmm1
0x180027b67  movups  xmmword ptr [rbp+57h+GuidString.Length], xmm0
0x180027b6b  movups  xmmword ptr [rbp+57h+Destination.Length], xmm1
0x180027b6f  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x180027b73  test    r14d, r14d
0x180027b76  jnz     loc_180027CEB
0x180027b7c  lea     rdx, aRegistryMachin_4; "\\Registry\\Machine"
0x180027b83  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180027b87  call    cs:__imp_RtlInitUnicodeStringEx
0x180027b8d  test    eax, eax
0x180027b8f  js      loc_180027D55
0x180027b95  movzx   r8d, [rbp+57h+DestinationString.Length]
0x180027b9a  xor     eax, eax
0x180027b9c  mov     [rbp+57h+Destination.Length], ax
0x180027ba0  add     r8, 0D0h; Size
0x180027ba7  mov     [rbp+57h+Destination.MaximumLength], r8w
0x180027bac  mov     rcx, gs:60h
0x180027bb5  lea     edx, [rax+8]; Flags
0x180027bb8  mov     rcx, [rcx+30h]; HeapHandle
0x180027bbc  call    cs:__imp_RtlAllocateHeap
0x180027bc2  mov     [rbp+57h+Destination.Buffer], rax
0x180027bc6  mov     ebx, 1
0x180027bcb  test    rax, rax
0x180027bce  jz      loc_180027D26
0x180027bd4  lea     rdx, [rbp+57h+DestinationString]; SourceString
0x180027bd8  lea     rcx, [rbp+57h+Destination]; DestinationString
0x180027bdc  call    cs:__imp_RtlCopyUnicodeString
0x180027be2  lea     rdx, aSoftwareClasse; "\\Software\\Classes\\CLSID\\"
0x180027be9  lea     rcx, [rbp+57h+Destination]; Destination
0x180027bed  call    cs:__imp_RtlAppendUnicodeToString
0x180027bf3  test    eax, eax
0x180027bf5  js      loc_180027D77
0x180027bfb  lea     rdx, [rbp+57h+GuidString]; GuidString
0x180027bff  mov     rcx, rdi; Guid
0x180027c02  call    cs:__imp_RtlStringFromGUID
0x180027c08  test    eax, eax
0x180027c0a  js      short loc_180027C85
0x180027c0c  movzx   eax, [rbp+57h+GuidString.Length]
0x180027c10  shr     eax, 1
0x180027c12  cmp     eax, 28h ; '('
0x180027c15  ja      short loc_180027C85
0x180027c17  mov     rdx, [rbp+57h+GuidString.Buffer]; Src
0x180027c1b  lea     rdi, [rax+rax]
0x180027c1f  mov     r8, rdi; Size
0x180027c22  lea     rcx, [rbp+57h+Source]; void *
0x180027c26  call    memmove_0
0x180027c2b  cmp     rdi, 52h ; 'R'
0x180027c2f  jnb     loc_180027DA4
0x180027c35  xor     eax, eax
0x180027c37  lea     rdx, [rbp+57h+Source]; Source
0x180027c3b  lea     rcx, [rbp+57h+Destination]; Destination
0x180027c3f  mov     [rbp+rdi+57h+Source], ax
0x180027c44  call    cs:__imp_RtlAppendUnicodeToString
0x180027c4a  test    eax, eax
0x180027c4c  js      loc_180027D86
0x180027c52  lea     rdx, aInprocserver32; "\\InProcServer32"
0x180027c59  lea     rcx, [rbp+57h+Destination]; Destination
0x180027c5d  call    cs:__imp_RtlAppendUnicodeToString
0x180027c63  mov     ecx, ebx; Flags
0x180027c65  test    eax, eax
0x180027c67  js      loc_180027D46
0x180027c6d  mov     r8, r15; DestinationString
0x180027c70  lea     rdx, [rbp+57h+Destination]; SourceString
0x180027c74  call    cs:__imp_RtlDuplicateUnicodeString
0x180027c7a  test    eax, eax
0x180027c7c  js      loc_180027D95
0x180027c82  mov     sil, bl
0x180027c85  cmp     r14d, ebx
0x180027c88  jnz     short loc_180027C94
0x180027c8a  lea     rcx, [rbp+57h+DestinationString]; UnicodeString
0x180027c8e  call    cs:__imp_RtlFreeUnicodeString
0x180027c94  cmp     [rbp+57h+GuidString.Buffer], 0
0x180027c99  jz      short loc_180027CA5
0x180027c9b  lea     rcx, [rbp+57h+GuidString]; UnicodeString
0x180027c9f  call    cs:__imp_RtlFreeUnicodeString
0x180027ca5  cmp     [rbp+57h+Destination.Buffer], 0
0x180027caa  jz      short loc_180027CC5
0x180027cac  mov     rcx, gs:60h
0x180027cb5  xor     edx, edx; Flags
0x180027cb7  mov     r8, [rbp+57h+Destination.Buffer]; P
0x180027cbb  mov     rcx, [rcx+30h]; HeapHandle
0x180027cbf  call    cs:__imp_RtlFreeHeap
0x180027cc5  mov     al, sil
0x180027cc8  mov     rcx, [rbp+57h+var_30]
0x180027ccc  xor     rcx, rsp; StackCookie
0x180027ccf  call    __security_check_cookie
0x180027cd4  mov     rbx, [rsp+0E0h+arg_8]
0x180027cdc  add     rsp, 0C0h
0x180027ce3  pop     r15
0x180027ce5  pop     r14
0x180027ce7  pop     rdi
0x180027ce8  pop     rsi
0x180027ce9  pop     rbp
0x180027cea  retn
0x180027ceb  cmp     r14d, 1
0x180027cef  jnz     loc_180027B95
0x180027cf5  lea     rcx, [rbp+57h+DestinationString]; KeyPath
0x180027cf9  call    cs:__imp_RtlFormatCurrentUserKeyPath
0x180027cff  test    eax, eax
0x180027d01  jns     loc_180027B95
0x180027d07  lea     r9, aFailedToFormat; "Failed to format current user key path."
0x180027d0e  mov     ecx, r14d
0x180027d11  lea     r8d, [r14+6Dh]
0x180027d15  lea     rdx, aBuildcomserver; "BuildCOMServerKeyPath"
0x180027d1c  call    AslLogCallPrintf
0x180027d21  jmp     loc_180027C8A
0x180027d26  lea     r9, aFailedToAlloca_31; "Failed to allocate memory to store enti"...
0x180027d2d  mov     r8d, 86h
0x180027d33  mov     ecx, ebx
0x180027d35  lea     rdx, aBuildcomserver; "BuildCOMServerKeyPath"
0x180027d3c  call    AslLogCallPrintf
0x180027d41  jmp     loc_180027C85
0x180027d46  lea     r9, aFailedToAppend_0; "Failed to append CLSID onto existing ke"...
0x180027d4d  mov     r8d, 0B7h
0x180027d53  jmp     short loc_180027D35
0x180027d55  mov     r8d, 64h ; 'd'
0x180027d5b  lea     r9, aFailedToInitia_0; "Failed to initialize key path."
0x180027d62  lea     rdx, aBuildcomserver; "BuildCOMServerKeyPath"
0x180027d69  lea     ecx, [r8-63h]
0x180027d6d  call    AslLogCallPrintf
0x180027d72  jmp     loc_180027C94
0x180027d77  lea     r9, aFailedToAppend_6; "Failed to append subkey path to key bas"...
0x180027d7e  mov     r8d, 95h
0x180027d84  jmp     short loc_180027D33
0x180027d86  lea     r9, aFailedToAppend_0; "Failed to append CLSID onto existing ke"...
0x180027d8d  mov     r8d, 0AEh
0x180027d93  jmp     short loc_180027D33
0x180027d95  lea     r9, aFailedToFillRe; "Failed to fill return value buffer with"...
0x180027d9c  mov     r8d, 0C2h
0x180027da2  jmp     short loc_180027D33
0x180027da4  call    __report_rangecheckfailure
```
