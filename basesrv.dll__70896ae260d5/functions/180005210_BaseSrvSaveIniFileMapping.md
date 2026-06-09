# BaseSrvSaveIniFileMapping

- ea: `0x180005210`
- end: `0x1800056d3`
- name: `BaseSrvSaveIniFileMapping`
- size: `1219`
- prototype: `__int64 __fastcall(__int64, void *)`
- caller_count: `2`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180004d80`
- `0x180005f10`

## callees

- `0x180005210`
- `0x1800056e0`
- `0x1800059b0`
- `0x18000d730`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18000533b`
- `ntdll!RtlAllocateHeap` at `0x1800053dd`
- `ntdll!RtlAllocateHeap` at `0x1800055c0`
- `ntdll!RtlAllocateHeap` at `0x18000533b`
- `ntdll!RtlAllocateHeap` at `0x1800053dd`
- `ntdll!RtlAllocateHeap` at `0x1800055c0`
- `ntdll!NtOpenKey` at `0x180005566`
- `ntdll!NtOpenKey` at `0x180005566`
- `ntdll!NtClose` at `0x18000569f`
- `ntdll!NtClose` at `0x18000569f`
- `ntdll!RtlFreeHeap` at `0x180005419`
- `ntdll!RtlFreeHeap` at `0x180005419`
- `ntdll!RtlCopyUnicodeString` at `0x180005375`
- `ntdll!RtlCopyUnicodeString` at `0x18000546d`
- `ntdll!RtlCopyUnicodeString` at `0x1800055fb`
- `ntdll!RtlCopyUnicodeString` at `0x180005375`
- `ntdll!RtlCopyUnicodeString` at `0x18000546d`
- `ntdll!RtlCopyUnicodeString` at `0x1800055fb`
- `ntdll!NtEnumerateKey` at `0x1800054ce`
- `ntdll!NtEnumerateKey` at `0x1800054ce`
- `ntdll!NtEnumerateValueKey` at `0x1800052c2`
- `ntdll!NtEnumerateValueKey` at `0x180005633`
- `ntdll!NtEnumerateValueKey` at `0x1800052c2`
- `ntdll!NtEnumerateValueKey` at `0x180005633`
- `ntdll!RtlInitUnicodeString` at `0x18000527e`
- `ntdll!RtlInitUnicodeString` at `0x18000527e`

## pseudocode

```c
__int64 __fastcall BaseSrvSaveIniFileMapping(__int64 a1, void *a2)
{
  ULONG v2; // esi
  ULONG v5; // r14d
  NTSTATUS v6; // eax
  NTSTATUS v7; // ebx
  _QWORD *v8; // rax
  _QWORD *i; // rdi
  char *Heap; // rax
  char *v11; // rbx
  wchar_t *v12; // r15
  _QWORD *v13; // rax
  _QWORD *j; // rsi
  char *v15; // rdi
  NTSTATUS v16; // eax
  _QWORD *v18; // rax
  _QWORD *k; // rbx
  char *v20; // rax
  char *v21; // r14
  ULONG m; // edi
  __int64 v23; // rcx
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  int v25; // [rsp+34h] [rbp-CCh]
  UNICODE_STRING SourceString; // [rsp+38h] [rbp-C8h] BYREF
  UNICODE_STRING v27; // [rsp+48h] [rbp-B8h] BYREF
  void *KeyHandle; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v30; // [rsp+70h] [rbp-90h]
  char *v31; // [rsp+78h] [rbp-88h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-80h] BYREF
  _BYTE KeyValueInformation[4]; // [rsp+B0h] [rbp-50h] BYREF
  int v34; // [rsp+B4h] [rbp-4Ch]
  int v35; // [rsp+B8h] [rbp-48h]
  USHORT v36; // [rsp+BCh] [rbp-44h]
  USHORT v37; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v38[1002]; // [rsp+C4h] [rbp-3Ch] BYREF
  __int16 v39; // [rsp+4AEh] [rbp+3AEh]

  v2 = 0;
  v31 = 0;
  KeyHandle = 0;
  ResultLength = 0;
  memset(&ObjectAttributes, 0, 44);
  SourceString = 0;
  v27 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  v5 = 0;
  while ( 1 )
  {
    v6 = NtEnumerateValueKey(a2, v5, KeyValueFullInformation, KeyValueInformation, 0x400u, &ResultLength);
    v39 = 0;
    v7 = v6;
    if ( v6 < 0 )
      break;
    SourceString.Buffer = (PWSTR)v38;
    SourceString.Length = v37;
    SourceString.MaximumLength = v37;
    if ( v34 != 1 )
      goto LABEL_24;
    if ( v37 )
    {
      v8 = *(_QWORD **)(a1 + 24);
      for ( i = (_QWORD *)(a1 + 24); v8; v8 = (_QWORD *)*v8 )
        i = v8;
    }
    else
    {
      i = (_QWORD *)(a1 + 32);
    }
    Heap = (char *)RtlAllocateHeap(BaseSrvSharedHeap, (BaseSrvSharedTag + 0x40000) | 8, v37 + 40LL);
    v11 = Heap;
    if ( !Heap )
      return (unsigned int)-1073741801;
    if ( SourceString.Length )
    {
      *((_QWORD *)Heap + 2) = Heap + 40;
      *((_WORD *)Heap + 5) = SourceString.MaximumLength;
      RtlCopyUnicodeString((PUNICODE_STRING)(Heap + 8), &SourceString);
    }
    *i = v11;
    v12 = (wchar_t *)&KeyValueInformation[v35];
    v30 = 0;
    v25 = 0;
    if ( DestinationString.Length )
    {
      v13 = (_QWORD *)*((_QWORD *)v11 + 3);
      for ( j = v11 + 24; v13; v13 = (_QWORD *)*v13 )
        j = v13;
    }
    else
    {
      j = v11 + 32;
    }
    v15 = (char *)RtlAllocateHeap(
                    BaseSrvSharedHeap,
                    (BaseSrvSharedTag + 0x40000) | 8,
                    DestinationString.MaximumLength + 40LL);
    if ( !v15 )
      return (unsigned int)-1073741801;
    v7 = BaseSrvSaveMappingTarget(v12);
    if ( v7 >= 0 )
    {
      *((_DWORD *)v15 + 6) = v25;
      *((_QWORD *)v15 + 4) = v30;
      if ( DestinationString.Length )
      {
        *((_QWORD *)v15 + 2) = v15 + 40;
        *((_WORD *)v15 + 5) = DestinationString.MaximumLength;
        RtlCopyUnicodeString((PUNICODE_STRING)(v15 + 8), &DestinationString);
      }
      *j = v15;
      v31 = v15;
      if ( !SourceString.Length )
        *((_DWORD *)v15 + 6) |= 0x20000000u;
      v2 = 0;
LABEL_24:
      ++v5;
    }
    else
    {
      RtlFreeHeap(BaseSrvSharedHeap, 0, v15);
      if ( v7 == -1073741801 )
        return (unsigned int)v7;
      v2 = 0;
      ++v5;
    }
  }
  if ( v6 == -2147483622 )
  {
    while ( 1 )
    {
      v16 = NtEnumerateKey(a2, v2, KeyBasicInformation, KeyValueInformation, 0x400u, &ResultLength);
      v7 = v16;
      if ( v16 >= 0 )
      {
        ObjectAttributes.Length = 48;
        v27.Buffer = &v37;
        v27.Length = v36;
        v27.MaximumLength = v36;
        ObjectAttributes.RootDirectory = a2;
        ObjectAttributes.ObjectName = &v27;
        ObjectAttributes.Attributes = 64;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        v7 = NtOpenKey(&KeyHandle, 0x80000000, &ObjectAttributes);
        if ( v7 < 0 )
          return (unsigned int)v7;
        if ( v27.Length )
        {
          v18 = *(_QWORD **)(a1 + 24);
          for ( k = (_QWORD *)(a1 + 24); v18; v18 = (_QWORD *)*v18 )
            k = v18;
        }
        else
        {
          k = (_QWORD *)(a1 + 32);
        }
        v20 = (char *)RtlAllocateHeap(BaseSrvSharedHeap, (BaseSrvSharedTag + 0x40000) | 8, v27.MaximumLength + 40LL);
        v21 = v20;
        if ( v20 )
        {
          if ( v27.Length )
          {
            *((_QWORD *)v20 + 2) = v20 + 40;
            *((_WORD *)v20 + 5) = v27.MaximumLength;
            RtlCopyUnicodeString((PUNICODE_STRING)(v20 + 8), &v27);
          }
          *k = v21;
          for ( m = 0; ; ++m )
          {
            v7 = NtEnumerateValueKey(KeyHandle, m, KeyValueFullInformation, KeyValueInformation, 0x400u, &ResultLength);
            if ( v7 < 0 )
              break;
            SourceString.Buffer = (PWSTR)v38;
            SourceString.Length = v37;
            SourceString.MaximumLength = v37;
            if ( v34 == 1 )
            {
              v7 = BaseSrvSaveVarNameMapping(v23, v21, &SourceString, &KeyValueInformation[v35], &v31);
              if ( v7 == -1073741801 )
                goto LABEL_46;
            }
          }
          if ( v7 == -2147483622 )
            v7 = 0;
        }
        else
        {
          v7 = -1073741801;
        }
LABEL_46:
        NtClose(KeyHandle);
      }
      else if ( v16 == -2147483622 )
      {
        return 0;
      }
      if ( v7 < 0 )
        return (unsigned int)v7;
      ++v2;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180005210  push    rbp
0x180005212  push    rbx
0x180005213  push    rsi
0x180005214  push    rdi
0x180005215  push    r12
0x180005217  push    r13
0x180005219  push    r14
0x18000521b  lea     rbp, [rsp-3C0h]
0x180005223  sub     rsp, 4C0h
0x18000522a  mov     rax, cs:__security_cookie
0x180005231  xor     rax, rsp
0x180005234  mov     [rbp+3F0h+var_40], rax
0x18000523b  xorps   xmm0, xmm0
0x18000523e  xor     esi, esi
0x180005240  xor     eax, eax
0x180005242  mov     [rsp+4F0h+var_478], rsi
0x180005247  mov     r12, rdx
0x18000524a  mov     [rbp+3F0h+ObjectAttributes.SecurityDescriptor], rax
0x18000524e  mov     r13, rcx
0x180005251  mov     dword ptr [rbp+3F0h+ObjectAttributes.SecurityQualityOfService], eax
0x180005254  xorps   xmm1, xmm1
0x180005257  mov     [rsp+4F0h+KeyHandle], rsi
0x18000525c  xor     edx, edx; SourceString
0x18000525e  mov     [rsp+4F0h+var_4C0], esi
0x180005262  lea     rcx, [rsp+4F0h+DestinationString]; DestinationString
0x180005267  movups  xmmword ptr [rbp+3F0h+ObjectAttributes.Length], xmm0
0x18000526b  movups  xmmword ptr [rbp+3F0h+ObjectAttributes.ObjectName], xmm0
0x18000526f  movups  xmmword ptr [rsp+4F0h+SourceString.Length], xmm0
0x180005274  movups  xmmword ptr [rsp+4F0h+var_4A8.Length], xmm1
0x180005279  movups  xmmword ptr [rsp+4F0h+DestinationString.Length], xmm0
0x18000527e  call    cs:__imp_RtlInitUnicodeString
0x180005285  nop     dword ptr [rax+rax+00h]
0x18000528a  mov     r14d, esi
0x18000528d  mov     [rsp+4F0h+arg_10], r15
0x180005295  nop     word ptr [rax+rax+00000000h]
0x1800052a0  lea     rax, [rsp+4F0h+var_4C0]
0x1800052a5  mov     r8d, 1; KeyValueInformationClass
0x1800052ab  mov     [rsp+4F0h+ResultLength], rax; ResultLength
0x1800052b0  lea     r9, [rbp+3F0h+KeyValueInformation]; KeyValueInformation
0x1800052b4  mov     edx, r14d; Index
0x1800052b7  mov     [rsp+4F0h+Length], 400h; Length
0x1800052bf  mov     rcx, r12; KeyHandle
0x1800052c2  call    cs:__imp_NtEnumerateValueKey
0x1800052c9  nop     dword ptr [rax+rax+00h]
0x1800052ce  mov     [rbp+3F0h+var_42], si
0x1800052d5  mov     ebx, eax
0x1800052d7  test    eax, eax
0x1800052d9  js      loc_18000549A
0x1800052df  cmp     [rbp+3F0h+var_43C], 1
0x1800052e3  lea     rax, [rbp+3F0h+var_42C]
0x1800052e7  movzx   ecx, [rbp+3F0h+var_430]
0x1800052eb  mov     [rsp+4F0h+SourceString.Buffer], rax
0x1800052f0  mov     [rsp+4F0h+SourceString.Length], cx
0x1800052f5  mov     [rsp+4F0h+SourceString.MaximumLength], cx
0x1800052fa  jnz     loc_180005492
0x180005300  test    cx, cx
0x180005303  jz      loc_1800056B0
0x180005309  mov     rax, [r13+18h]
0x18000530d  lea     rdi, [r13+18h]
0x180005311  test    rax, rax
0x180005314  jz      short loc_180005321
0x180005316  mov     rdi, rax
0x180005319  mov     rax, [rax]
0x18000531c  test    rax, rax
0x18000531f  jnz     short loc_180005316
0x180005321  mov     edx, cs:BaseSrvSharedTag
0x180005327  lea     r8, [rcx+28h]; Size
0x18000532b  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x180005332  add     edx, 40000h
0x180005338  or      edx, 8; Flags
0x18000533b  call    cs:__imp_RtlAllocateHeap
0x180005342  nop     dword ptr [rax+rax+00h]
0x180005347  mov     rbx, rax
0x18000534a  test    rax, rax
0x18000534d  jz      loc_1800056C9
0x180005353  cmp     [rsp+4F0h+SourceString.Length], 0
0x180005359  jz      short loc_180005381
0x18000535b  lea     rcx, [rax+28h]
0x18000535f  mov     [rax+10h], rcx
0x180005363  lea     rdx, [rsp+4F0h+SourceString]; SourceString
0x180005368  movzx   ecx, [rsp+4F0h+SourceString.MaximumLength]
0x18000536d  mov     [rax+0Ah], cx
0x180005371  lea     rcx, [rax+8]; DestinationString
0x180005375  call    cs:__imp_RtlCopyUnicodeString
0x18000537c  nop     dword ptr [rax+rax+00h]
0x180005381  mov     [rdi], rbx
0x180005384  lea     r15, [rbp+3F0h+KeyValueInformation]
0x180005388  mov     eax, [rbp+3F0h+var_438]
0x18000538b  add     r15, rax
0x18000538e  mov     [rsp+4F0h+var_480], rsi
0x180005393  cmp     [rsp+4F0h+DestinationString.Length], 0
0x180005399  mov     [rsp+4F0h+var_4BC], esi
0x18000539d  jz      short loc_1800053B9
0x18000539f  mov     rax, [rbx+18h]
0x1800053a3  lea     rsi, [rbx+18h]
0x1800053a7  test    rax, rax
0x1800053aa  jz      short loc_1800053BD
0x1800053ac  mov     rsi, rax
0x1800053af  mov     rax, [rax]
0x1800053b2  test    rax, rax
0x1800053b5  jnz     short loc_1800053AC
0x1800053b7  jmp     short loc_1800053BD
0x1800053b9  lea     rsi, [rbx+20h]
0x1800053bd  mov     edx, cs:BaseSrvSharedTag
0x1800053c3  movzx   r8d, [rsp+4F0h+DestinationString.MaximumLength]
0x1800053c9  add     edx, 40000h
0x1800053cf  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x1800053d6  or      edx, 8; Flags
0x1800053d9  add     r8, 28h ; '('; Size
0x1800053dd  call    cs:__imp_RtlAllocateHeap
0x1800053e4  nop     dword ptr [rax+rax+00h]
0x1800053e9  mov     rdi, rax
0x1800053ec  test    rax, rax
0x1800053ef  jz      loc_1800056C9
0x1800053f5  lea     r8, [rsp+4F0h+var_4BC]
0x1800053fa  mov     rcx, r15; String1
0x1800053fd  lea     rdx, [rsp+4F0h+var_480]
0x180005402  call    BaseSrvSaveMappingTarget
0x180005407  mov     ebx, eax
0x180005409  test    eax, eax
0x18000540b  jns     short loc_18000543B
0x18000540d  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x180005414  mov     r8, rdi; P
0x180005417  xor     edx, edx; Flags
0x180005419  call    cs:__imp_RtlFreeHeap
0x180005420  nop     dword ptr [rax+rax+00h]
0x180005425  cmp     ebx, 0C0000017h
0x18000542b  jz      loc_1800054F2
0x180005431  xor     esi, esi
0x180005433  inc     r14d
0x180005436  jmp     loc_1800052A0
0x18000543b  mov     eax, [rsp+4F0h+var_4BC]
0x18000543f  mov     [rdi+18h], eax
0x180005442  mov     rax, [rsp+4F0h+var_480]
0x180005447  mov     [rdi+20h], rax
0x18000544b  cmp     [rsp+4F0h+DestinationString.Length], 0
0x180005451  jz      short loc_180005479
0x180005453  lea     rax, [rdi+28h]
0x180005457  mov     [rdi+10h], rax
0x18000545b  lea     rcx, [rdi+8]; DestinationString
0x18000545f  movzx   eax, [rsp+4F0h+DestinationString.MaximumLength]
0x180005464  lea     rdx, [rsp+4F0h+DestinationString]; SourceString
0x180005469  mov     [rdi+0Ah], ax
0x18000546d  call    cs:__imp_RtlCopyUnicodeString
0x180005474  nop     dword ptr [rax+rax+00h]
0x180005479  mov     [rsi], rdi
0x18000547c  cmp     [rsp+4F0h+SourceString.Length], 0
0x180005482  mov     [rsp+4F0h+var_478], rdi
0x180005487  jnz     short loc_180005490
0x180005489  or      dword ptr [rdi+18h], 20000000h
0x180005490  xor     esi, esi
0x180005492  inc     r14d
0x180005495  jmp     loc_1800052A0
0x18000549a  cmp     eax, 8000001Ah
0x18000549f  jnz     short loc_1800054F2
0x1800054a1  xor     r15d, r15d
0x1800054a4  nop     dword ptr [rax+00h]
0x1800054a8  nop     dword ptr [rax+rax+00000000h]
0x1800054b0  lea     rax, [rsp+4F0h+var_4C0]
0x1800054b5  xor     r8d, r8d; KeyInformationClass
0x1800054b8  mov     [rsp+4F0h+ResultLength], rax; ResultLength
0x1800054bd  lea     r9, [rbp+3F0h+KeyValueInformation]; KeyInformation
0x1800054c1  mov     edx, esi; Index
0x1800054c3  mov     [rsp+4F0h+Length], 400h; Length
0x1800054cb  mov     rcx, r12; KeyHandle
0x1800054ce  call    cs:__imp_NtEnumerateKey
0x1800054d5  nop     dword ptr [rax+rax+00h]
0x1800054da  mov     ebx, eax
0x1800054dc  test    eax, eax
0x1800054de  jns     short loc_18000551E
0x1800054e0  cmp     eax, 8000001Ah
0x1800054e5  jz      short loc_1800054EF
0x1800054e7  test    ebx, ebx
0x1800054e9  js      short loc_1800054F2
0x1800054eb  inc     esi
0x1800054ed  jmp     short loc_1800054B0
0x1800054ef  mov     ebx, r15d
0x1800054f2  mov     r15, [rsp+4F0h+arg_10]
0x1800054fa  mov     eax, ebx
0x1800054fc  mov     rcx, [rbp+3F0h+var_40]
0x180005503  xor     rcx, rsp; StackCookie
0x180005506  call    __security_check_cookie
0x18000550b  add     rsp, 4C0h
0x180005512  pop     r14
0x180005514  pop     r13
0x180005516  pop     r12
0x180005518  pop     rdi
0x180005519  pop     rsi
0x18000551a  pop     rbx
0x18000551b  pop     rbp
0x18000551c  retn
0x18000551e  lea     rax, [rbp+3F0h+var_430]
0x180005522  mov     [rbp+3F0h+ObjectAttributes.Length], 30h ; '0'
0x180005529  mov     [rsp+4F0h+var_4A8.Buffer], rax
0x18000552e  lea     r8, [rbp+3F0h+ObjectAttributes]; ObjectAttributes
0x180005532  movzx   eax, [rbp+3F0h+var_434]
0x180005536  lea     rcx, [rsp+4F0h+KeyHandle]; KeyHandle
0x18000553b  mov     [rsp+4F0h+var_4A8.Length], ax
0x180005540  xorps   xmm0, xmm0
0x180005543  mov     [rsp+4F0h+var_4A8.MaximumLength], ax
0x180005548  mov     edx, 80000000h; DesiredAccess
0x18000554d  lea     rax, [rsp+4F0h+var_4A8]
0x180005552  mov     [rbp+3F0h+ObjectAttributes.RootDirectory], r12
0x180005556  mov     [rbp+3F0h+ObjectAttributes.ObjectName], rax
0x18000555a  mov     [rbp+3F0h+ObjectAttributes.Attributes], 40h ; '@'
0x180005561  movdqu  xmmword ptr [rbp+3F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180005566  call    cs:__imp_NtOpenKey
0x18000556d  nop     dword ptr [rax+rax+00h]
0x180005572  mov     ebx, eax
0x180005574  test    eax, eax
0x180005576  js      loc_1800054F2
0x18000557c  cmp     [rsp+4F0h+var_4A8.Length], r15w
0x180005582  jz      loc_1800056B9
0x180005588  mov     rax, [r13+18h]
0x18000558c  lea     rbx, [r13+18h]
0x180005590  test    rax, rax
0x180005593  jz      short loc_1800055A0
0x180005595  mov     rbx, rax
0x180005598  mov     rax, [rax]
0x18000559b  test    rax, rax
0x18000559e  jnz     short loc_180005595
0x1800055a0  mov     edx, cs:BaseSrvSharedTag
0x1800055a6  movzx   r8d, [rsp+4F0h+var_4A8.MaximumLength]
0x1800055ac  add     edx, 40000h
0x1800055b2  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x1800055b9  or      edx, 8; Flags
0x1800055bc  add     r8, 28h ; '('; Size
0x1800055c0  call    cs:__imp_RtlAllocateHeap
0x1800055c7  nop     dword ptr [rax+rax+00h]
0x1800055cc  mov     r14, rax
0x1800055cf  test    rax, rax
0x1800055d2  jz      loc_1800056C2
0x1800055d8  cmp     [rsp+4F0h+var_4A8.Length], r15w
0x1800055de  jz      short loc_180005607
0x1800055e0  add     rax, 28h ; '('
0x1800055e4  lea     rcx, [r14+8]; DestinationString
0x1800055e8  mov     [r14+10h], rax
0x1800055ec  lea     rdx, [rsp+4F0h+var_4A8]; SourceString
0x1800055f1  movzx   eax, [rsp+4F0h+var_4A8.MaximumLength]
0x1800055f6  mov     [r14+0Ah], ax
0x1800055fb  call    cs:__imp_RtlCopyUnicodeString
0x180005602  nop     dword ptr [rax+rax+00h]
0x180005607  mov     [rbx], r14
0x18000560a  mov     edi, r15d
0x18000560d  nop     dword ptr [rax]
0x180005610  mov     rcx, [rsp+4F0h+KeyHandle]; KeyHandle
0x180005615  lea     rax, [rsp+4F0h+var_4C0]
0x18000561a  mov     [rsp+4F0h+ResultLength], rax; ResultLength
0x18000561f  lea     r9, [rbp+3F0h+KeyValueInformation]; KeyValueInformation
0x180005623  mov     r8d, 1; KeyValueInformationClass
0x180005629  mov     [rsp+4F0h+Length], 400h; Length
0x180005631  mov     edx, edi; Index
0x180005633  call    cs:__imp_NtEnumerateValueKey
0x18000563a  nop     dword ptr [rax+rax+00h]
0x18000563f  mov     ebx, eax
0x180005641  test    eax, eax
0x180005643  js      short loc_180005690
0x180005645  cmp     [rbp+3F0h+var_43C], 1
0x180005649  lea     rax, [rbp+3F0h+var_42C]
0x18000564d  mov     [rsp+4F0h+SourceString.Buffer], rax
0x180005652  movzx   eax, [rbp+3F0h+var_430]
0x180005656  mov     [rsp+4F0h+SourceString.Length], ax
0x18000565b  mov     [rsp+4F0h+SourceString.MaximumLength], ax
0x180005660  jnz     short loc_18000568C
0x180005662  mov     eax, [rbp+3F0h+var_438]
0x180005665  lea     r9, [rbp+3F0h+KeyValueInformation]
0x180005669  add     r9, rax
0x18000566c  lea     r8, [rsp+4F0h+SourceString]
0x180005671  lea     rax, [rsp+4F0h+var_478]
0x180005676  mov     rdx, r14
0x180005679  mov     qword ptr [rsp+4F0h+Length], rax
0x18000567e  call    BaseSrvSaveVarNameMapping
0x180005683  mov     ebx, eax
0x180005685  cmp     eax, 0C0000017h
0x18000568a  jz      short loc_18000569A
0x18000568c  inc     edi
0x18000568e  jmp     short loc_180005610
0x180005690  cmp     ebx, 8000001Ah
0x180005696  cmovz   ebx, r15d
0x18000569a  mov     rcx, [rsp+4F0h+KeyHandle]; Handle
0x18000569f  call    cs:__imp_NtClose
0x1800056a6  nop     dword ptr [rax+rax+00h]
0x1800056ab  jmp     loc_1800054E7
0x1800056b0  lea     rdi, [r13+20h]
0x1800056b4  jmp     loc_180005321
0x1800056b9  lea     rbx, [r13+20h]
0x1800056bd  jmp     loc_1800055A0
0x1800056c2  mov     ebx, 0C0000017h
0x1800056c7  jmp     short loc_18000569A
0x1800056c9  mov     ebx, 0C0000017h
0x1800056ce  jmp     loc_1800054F2
```
