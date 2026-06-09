# LuaCdfCreateFileNameForFile

- ea: `0x180004060`
- end: `0x1800043c0`
- name: `LuaCdfCreateFileNameForFile`
- size: `864`
- prototype: `__int64 __fastcall(PCWSTR DosPathName)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x180003d90`

## callees

- `0x1800031e0`
- `0x180003358`
- `0x1800033e0`
- `0x1800036a0`
- `0x180004060`
- `0x180004450`
- `0x180004500`
- `0x180004620`
- `0x1800293a0`
- `0x180099cb0`
- `0x18009a070`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x1800043a6`
- `ntdll!RtlFreeUnicodeString` at `0x1800043a6`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800040f9`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800040f9`
- `ntdll!RtlCopyUnicodeString` at `0x18000428c`
- `ntdll!RtlCopyUnicodeString` at `0x18000428c`

## pseudocode

```c
__int64 __fastcall LuaCdfCreateFileNameForFile(
        PCWSTR DosPathName,
        PCWSTR *a2,
        struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4)
{
  BOOLEAN v8; // al
  PCWSTR v9; // rcx
  PWSTR Buffer; // rax
  int inited; // ebx
  size_t v12; // rdi
  _DWORD *v13; // rcx
  void *v14; // rdx
  PWSTR v15; // rdx
  unsigned __int64 v16; // rcx
  WCHAR v17; // r8
  __int16 v18; // ax
  USHORT v19; // bx
  __int64 StringRoutine; // rax
  size_t Size[2]; // [rsp+20h] [rbp-E0h] BYREF
  void *Src; // [rsp+30h] [rbp-D0h]
  const char *v24; // [rsp+38h] [rbp-C8h]
  __int128 v25; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD *v26; // [rsp+50h] [rbp-B0h]
  __int128 v27; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE *v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h] BYREF
  PWSTR v30; // [rsp+80h] [rbp-80h]
  PCWSTR NtFileNamePart; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v32[256]; // [rsp+90h] [rbp-70h] BYREF

  v28 = 0;
  v30 = 0;
  Src = 0;
  v26 = 0;
  NtFileNamePart = 0;
  v27 = 0;
  v29 = 0;
  *(_OWORD *)Size = 0;
  v25 = 0;
  memset(v32, 0, 0xF8u);
  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  v8 = RtlDosPathNameToNtPathName_U(DosPathName, a3, &NtFileNamePart, 0);
  v9 = NtFileNamePart;
  *a2 = NtFileNamePart;
  if ( !v8 )
  {
    inited = -1073741801;
    goto LABEL_25;
  }
  if ( !v9 )
  {
LABEL_23:
    inited = 0;
    goto LABEL_25;
  }
  Buffer = a3->Buffer;
  if ( *Buffer != 92 || Buffer[1] != 63 || Buffer[2] != 63 || Buffer[3] != 92 )
  {
    RtlFreeUnicodeString(a3);
    *a3 = 0;
    *a2 = 0;
    goto LABEL_23;
  }
  inited = RtlInitLUnicodeStringFromNullTerminatedString(2147352624, Size);
  if ( inited < 0 )
    goto LABEL_25;
  v12 = Size[0];
  if ( Size[0] >= 0xFFFFFFFFFFFFFFF8uLL )
    goto LABEL_24;
  if ( v26 )
    __debugbreak();
  inited = RtlReallocateLUnicodeString(0, Size[0] + 8, &v25);
  if ( inited < 0 )
    goto LABEL_25;
  v13 = v26;
  v14 = Src;
  *v26 = 4128860;
  v13[1] = 6029375;
  memmove(v13 + 2, v14, v12);
  v15 = a3->Buffer;
  *(_QWORD *)&v25 = v12 + 8;
  v16 = 2 * (NtFileNamePart - v15);
  if ( v16 )
  {
    v17 = v15[(v16 >> 1) - 1];
    if ( v17 == 92 || v17 == 47 )
      v16 -= 2LL;
  }
  *(_QWORD *)&v27 = 0;
  v30 = v15 + 4;
  *(_QWORD *)&v29 = v16 - 8;
  v28 = v32;
  *((_QWORD *)&v29 + 1) = v16 - 8;
  *((_QWORD *)&v27 + 1) = 248;
  inited = LuaCdfGenerateFilemapFileName(v16 - 8, &v29, &v25, &v27);
  if ( inited < 0 )
    goto LABEL_25;
  v18 = v27;
  if ( (unsigned __int64)v27 > 0xFFFF || (v19 = v27 + 56, (unsigned __int16)(v27 + 56) < (unsigned __int16)v27) )
  {
LABEL_24:
    inited = -1073741675;
    goto LABEL_25;
  }
  *(_DWORD *)&a4->Length = 0;
  a4->Buffer = 0;
  if ( (v19 & 1) != 0 )
  {
    Src = (void *)57;
    Size[0] = (size_t)"onecore\\base\\lstring\\lunicode_string.cpp";
    Size[1] = (size_t)"RtlAllocateUnicodeString";
    v24 = "(Bytes % sizeof(WCHAR)) == 0";
    RtlReportErrorOrigination(Size, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
    inited = -1073741811;
  }
  else
  {
    if ( !v19 )
      goto LABEL_22;
    StringRoutine = anonymous_namespace_::OurRtlAllocateStringRoutine((unsigned __int16)(v18 + 56));
    a4->Buffer = (PWSTR)StringRoutine;
    if ( StringRoutine )
    {
      a4->MaximumLength = v19;
LABEL_22:
      RtlCopyUnicodeString(a4, &SourceString);
      inited = RtlAppendLUnicodeStringToUnicodeString(&v27, a4);
      if ( inited < 0 )
        goto LABEL_25;
      goto LABEL_23;
    }
    Src = (void *)61;
    Size[0] = (size_t)"onecore\\base\\lstring\\lunicode_string.cpp";
    Size[1] = (size_t)"RtlAllocateUnicodeString";
    v24 = "String->Buffer = reinterpret_cast<PWSTR>((*RtlAllocateStringRoutine)(Bytes))";
    RtlReportErrorOrigination(Size, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225495LL);
    inited = -1073741801;
  }
LABEL_25:
  if ( v26 )
    RtlFreeLUtf8String(&v25);
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180004060  push    rbp
0x180004062  push    rbx
0x180004063  push    rsi
0x180004064  push    rdi
0x180004065  push    r14
0x180004067  push    r15
0x180004069  lea     rbp, [rsp-0A8h]
0x180004071  sub     rsp, 1A8h
0x180004078  mov     rax, cs:__security_cookie
0x18000407f  xor     rax, rsp
0x180004082  mov     [rbp+0D0h+var_40], rax
0x180004089  xor     eax, eax
0x18000408b  xorps   xmm0, xmm0
0x18000408e  xorps   xmm1, xmm1
0x180004091  mov     [rsp+1D0h+var_168], rax
0x180004096  mov     rsi, r8
0x180004099  mov     [rbp+0D0h+var_150], rax
0x18000409d  mov     rdi, rdx
0x1800040a0  mov     [rsp+1D0h+Src], rax
0x1800040a5  mov     rbx, rcx
0x1800040a8  mov     [rsp+1D0h+var_180], rax
0x1800040ad  xor     r15d, r15d
0x1800040b0  lea     rcx, [rbp+0D0h+var_140]; void *
0x1800040b4  xor     edx, edx; Val
0x1800040b6  mov     [rbp+0D0h+NtFileNamePart], r15
0x1800040ba  mov     r8d, 0F8h; Size
0x1800040c0  mov     r14, r9
0x1800040c3  movups  [rsp+1D0h+var_178], xmm0
0x1800040c8  movups  [rsp+1D0h+var_160], xmm1
0x1800040cd  movups  xmmword ptr [rsp+1D0h+Size], xmm0
0x1800040d2  movups  [rsp+1D0h+var_190], xmm1
0x1800040d7  call    memset
0x1800040dc  mov     [rdi], r15
0x1800040df  lea     r8, [rbp+0D0h+NtFileNamePart]; NtFileNamePart
0x1800040e3  xorps   xmm0, xmm0
0x1800040e6  xorps   xmm1, xmm1
0x1800040e9  movups  xmmword ptr [rsi], xmm0
0x1800040ec  xor     r9d, r9d; DirectoryInfo
0x1800040ef  mov     rdx, rsi; NtPathName
0x1800040f2  mov     rcx, rbx; DosPathName
0x1800040f5  movups  xmmword ptr [r14], xmm1
0x1800040f9  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180004100  nop     dword ptr [rax+rax+00h]
0x180004105  mov     rcx, [rbp+0D0h+NtFileNamePart]
0x180004109  mov     [rdi], rcx
0x18000410c  test    al, al
0x18000410e  jz      loc_1800042EA
0x180004114  test    rcx, rcx
0x180004117  jz      loc_1800042AB
0x18000411d  mov     rax, [rsi+8]
0x180004121  cmp     word ptr [rax], 5Ch ; '\'
0x180004125  jnz     loc_1800043A3
0x18000412b  cmp     word ptr [rax+2], 3Fh ; '?'
0x180004130  jnz     loc_1800043A3
0x180004136  cmp     word ptr [rax+4], 3Fh ; '?'
0x18000413b  jnz     loc_1800043A3
0x180004141  cmp     word ptr [rax+6], 5Ch ; '\'
0x180004146  jnz     loc_1800043A3
0x18000414c  lea     rdx, [rsp+1D0h+Size]
0x180004151  mov     ecx, 7FFE0030h
0x180004156  call    RtlInitLUnicodeStringFromNullTerminatedString
0x18000415b  mov     ebx, eax
0x18000415d  test    eax, eax
0x18000415f  js      loc_1800042B5
0x180004165  mov     rdi, [rsp+1D0h+Size]
0x18000416a  lea     rdx, [rdi+8]
0x18000416e  cmp     rdx, 8
0x180004172  jb      loc_1800042B0
0x180004178  cmp     [rsp+1D0h+var_180], r15
0x18000417d  jnz     loc_1800042F1
0x180004183  lea     r8, [rsp+1D0h+var_190]
0x180004188  xor     ecx, ecx
0x18000418a  call    RtlReallocateLUnicodeString
0x18000418f  mov     ebx, eax
0x180004191  test    eax, eax
0x180004193  js      loc_1800042B5
0x180004199  mov     rcx, [rsp+1D0h+var_180]
0x18000419e  mov     r8, rdi; Size
0x1800041a1  mov     rdx, [rsp+1D0h+Src]; Src
0x1800041a6  mov     dword ptr [rcx], 3F005Ch
0x1800041ac  mov     dword ptr [rcx+4], 5C003Fh
0x1800041b3  add     rcx, 8; void *
0x1800041b7  call    memmove
0x1800041bc  mov     rdx, [rsi+8]
0x1800041c0  lea     rax, [rdi+8]
0x1800041c4  mov     qword ptr [rsp+1D0h+var_190], rax
0x1800041c9  mov     rax, [rbp+0D0h+NtFileNamePart]
0x1800041cd  sub     rax, rdx
0x1800041d0  sar     rax, 1
0x1800041d3  lea     rcx, [rax+rax]
0x1800041d7  test    rcx, rcx
0x1800041da  jz      short loc_1800041F7
0x1800041dc  mov     rax, rcx
0x1800041df  shr     rax, 1
0x1800041e2  movzx   r8d, word ptr [rdx+rax*2-2]
0x1800041e8  cmp     r8w, 5Ch ; '\'
0x1800041ed  jnz     loc_1800042F7
0x1800041f3  add     rcx, 0FFFFFFFFFFFFFFFEh
0x1800041f7  lea     rax, [rdx+8]
0x1800041fb  mov     qword ptr [rsp+1D0h+var_178], r15
0x180004200  sub     rcx, 8
0x180004204  mov     [rbp+0D0h+var_150], rax
0x180004208  lea     rax, [rbp+0D0h+var_140]
0x18000420c  mov     qword ptr [rsp+1D0h+var_160], rcx
0x180004211  lea     r9, [rsp+1D0h+var_178]
0x180004216  mov     [rsp+1D0h+var_168], rax
0x18000421b  lea     r8, [rsp+1D0h+var_190]
0x180004220  mov     qword ptr [rsp+1D0h+var_160+8], rcx
0x180004225  lea     rdx, [rsp+1D0h+var_160]
0x18000422a  mov     qword ptr [rsp+1D0h+var_178+8], 0F8h
0x180004233  call    LuaCdfGenerateFilemapFileName
0x180004238  mov     ebx, eax
0x18000423a  test    eax, eax
0x18000423c  js      short loc_1800042B5
0x18000423e  mov     rax, qword ptr [rsp+1D0h+var_178]
0x180004243  cmp     rax, 0FFFFh
0x180004249  ja      short loc_1800042B0
0x18000424b  lea     ebx, [rax+38h]
0x18000424e  cmp     bx, ax
0x180004251  jb      short loc_1800042B0
0x180004253  mov     [r14], r15d
0x180004256  mov     [r14+8], r15
0x18000425a  test    bl, 1
0x18000425d  jnz     loc_180004307
0x180004263  test    bx, bx
0x180004266  jz      short loc_180004282
0x180004268  movzx   ecx, bx
0x18000426b  call    _anonymous_namespace___OurRtlAllocateStringRoutine
0x180004270  mov     [r14+8], rax
0x180004274  test    rax, rax
0x180004277  jz      loc_180004355
0x18000427d  mov     [r14+2], bx
0x180004282  lea     rdx, SourceString; SourceString
0x180004289  mov     rcx, r14; DestinationString
0x18000428c  call    cs:__imp_RtlCopyUnicodeString
0x180004293  nop     dword ptr [rax+rax+00h]
0x180004298  mov     rdx, r14
0x18000429b  lea     rcx, [rsp+1D0h+var_178]
0x1800042a0  call    RtlAppendLUnicodeStringToUnicodeString
0x1800042a5  mov     ebx, eax
0x1800042a7  test    eax, eax
0x1800042a9  js      short loc_1800042B5
0x1800042ab  mov     ebx, r15d
0x1800042ae  jmp     short loc_1800042B5
0x1800042b0  mov     ebx, 0C0000095h
0x1800042b5  cmp     [rsp+1D0h+var_180], r15
0x1800042ba  jnz     short loc_1800042DE
0x1800042bc  mov     eax, ebx
0x1800042be  mov     rcx, [rbp+0D0h+var_40]
0x1800042c5  xor     rcx, rsp; StackCookie
0x1800042c8  call    __security_check_cookie
0x1800042cd  add     rsp, 1A8h
0x1800042d4  pop     r15
0x1800042d6  pop     r14
0x1800042d8  pop     rdi
0x1800042d9  pop     rsi
0x1800042da  pop     rbx
0x1800042db  pop     rbp
0x1800042dc  retn
0x1800042de  lea     rcx, [rsp+1D0h+var_190]
0x1800042e3  call    RtlFreeLUtf8String
0x1800042e8  jmp     short loc_1800042BC
0x1800042ea  mov     ebx, 0C0000017h
0x1800042ef  jmp     short loc_1800042B5
0x1800042f1  int     3; Trap to Debugger
0x1800042f2  jmp     loc_180004183
0x1800042f7  cmp     r8w, 2Fh ; '/'
0x1800042fc  jnz     loc_1800041F7
0x180004302  jmp     loc_1800041F3
0x180004307  lea     rax, aOnecoreBaseLst_3; "onecore\\base\\lstring\\lunicode_string"...
0x18000430e  mov     [rsp+1D0h+Src], 39h ; '9'
0x180004317  mov     [rsp+1D0h+Size], rax
0x18000431c  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180004323  lea     rax, aRtlallocateuni_0; "RtlAllocateUnicodeString"
0x18000432a  mov     r8d, 0C000000Dh
0x180004330  mov     [rsp+1D0h+Size+8], rax
0x180004335  lea     rcx, [rsp+1D0h+Size]
0x18000433a  lea     rax, aBytesSizeofWch; "(Bytes % sizeof(WCHAR)) == 0"
0x180004341  mov     [rsp+1D0h+var_198], rax
0x180004346  call    RtlReportErrorOrigination
0x18000434b  mov     ebx, 0C000000Dh
0x180004350  jmp     loc_1800042B5
0x180004355  lea     rax, aOnecoreBaseLst_3; "onecore\\base\\lstring\\lunicode_string"...
0x18000435c  mov     [rsp+1D0h+Src], 3Dh ; '='
0x180004365  mov     [rsp+1D0h+Size], rax
0x18000436a  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180004371  lea     rax, aRtlallocateuni_0; "RtlAllocateUnicodeString"
0x180004378  mov     r8d, 0C0000017h
0x18000437e  mov     [rsp+1D0h+Size+8], rax
0x180004383  lea     rcx, [rsp+1D0h+Size]
0x180004388  lea     rax, aStringBufferRe; "String->Buffer = reinterpret_cast<PWSTR"...
0x18000438f  mov     [rsp+1D0h+var_198], rax
0x180004394  call    RtlReportErrorOrigination
0x180004399  mov     ebx, 0C0000017h
0x18000439e  jmp     loc_1800042B5
0x1800043a3  mov     rcx, rsi; UnicodeString
0x1800043a6  call    cs:__imp_RtlFreeUnicodeString
0x1800043ad  nop     dword ptr [rax+rax+00h]
0x1800043b2  xorps   xmm0, xmm0
0x1800043b5  movups  xmmword ptr [rsi], xmm0
0x1800043b8  mov     [rdi], r15
0x1800043bb  jmp     loc_1800042AB
```
