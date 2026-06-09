# BasepLoadLibraryAsDataFileInternal

- ea: `0x180046dc0`
- end: `0x18004756d`
- name: `BasepLoadLibraryAsDataFileInternal`
- size: `1965`
- prototype: `__int64 __usercall@<rax>(PCUNICODE_STRING Source@<rcx>, PCWSTR SourceString@<rdx>, PCWSTR@<r8>, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800145c0`

## callees

- `0x1800134a0`
- `0x180046dc0`
- `0x1800486a0`
- `0x180128998`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18004710b`
- `ntdll!RtlFreeUnicodeString` at `0x180047251`
- `ntdll!RtlFreeUnicodeString` at `0x18004710b`
- `ntdll!RtlFreeUnicodeString` at `0x180047251`
- `ntdll!RtlSetLastWin32Error` at `0x1800472ce`
- `ntdll!RtlSetLastWin32Error` at `0x1800472ce`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180047524`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180047536`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180047524`
- `ntdll!RtlAppendUnicodeStringToString` at `0x180047536`
- `ntdll!NtCreateSection` at `0x18004700d`
- `ntdll!NtCreateSection` at `0x1800472b3`
- `ntdll!NtCreateSection` at `0x18004700d`
- `ntdll!NtCreateSection` at `0x1800472b3`
- `ntdll!NtMapViewOfSection` at `0x180047067`
- `ntdll!NtMapViewOfSection` at `0x180047328`
- `ntdll!NtMapViewOfSection` at `0x180047067`
- `ntdll!NtMapViewOfSection` at `0x180047328`
- `ntdll!RtlInitUnicodeStringEx` at `0x180046f10`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800471b8`
- `ntdll!RtlInitUnicodeStringEx` at `0x180046f10`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800471b8`
- `ntdll!NtClose` at `0x1800470b7`
- `ntdll!NtClose` at `0x1800470c0`
- `ntdll!NtClose` at `0x180047233`
- `ntdll!NtClose` at `0x18004723c`
- `ntdll!NtClose` at `0x180047389`
- `ntdll!NtClose` at `0x180047394`
- `ntdll!NtClose` at `0x1800470b7`
- `ntdll!NtClose` at `0x1800470c0`
- `ntdll!NtClose` at `0x180047233`
- `ntdll!NtClose` at `0x18004723c`
- `ntdll!NtClose` at `0x180047389`
- `ntdll!NtClose` at `0x180047394`
- `ntdll!NtUnmapViewOfSection` at `0x180047228`
- `ntdll!NtUnmapViewOfSection` at `0x180047228`
- `ntdll!RtlFreeHeap` at `0x1800473d5`
- `ntdll!RtlFreeHeap` at `0x1800473d5`
- `ntdll!RtlDosApplyFileIsolationRedirection_Ustr` at `0x180046e81`
- `ntdll!RtlDosApplyFileIsolationRedirection_Ustr` at `0x180046e81`
- `ntdll!LdrGetDllHandleByName` at `0x180046f78`
- `ntdll!LdrGetDllHandleByName` at `0x18004718c`
- `ntdll!LdrGetDllHandleByName` at `0x1800473a9`
- `ntdll!LdrGetDllHandleByName` at `0x180046f78`
- `ntdll!LdrGetDllHandleByName` at `0x18004718c`
- `ntdll!LdrGetDllHandleByName` at `0x1800473a9`
- `ntdll!RtlDosSearchPath_Ustr` at `0x180046f59`
- `ntdll!RtlDosSearchPath_Ustr` at `0x180047204`
- `ntdll!RtlDosSearchPath_Ustr` at `0x180046f59`
- `ntdll!RtlDosSearchPath_Ustr` at `0x180047204`
- `ntdll!RtlImageNtHeaderEx` at `0x180047087`
- `ntdll!RtlImageNtHeaderEx` at `0x180047348`
- `ntdll!RtlImageNtHeaderEx` at `0x180047087`
- `ntdll!RtlImageNtHeaderEx` at `0x180047348`
- `ntdll!LdrGetDllHandleByMapping` at `0x18004709f`
- `ntdll!LdrGetDllHandleByMapping` at `0x180047360`
- `ntdll!LdrGetDllHandleByMapping` at `0x18004709f`
- `ntdll!LdrGetDllHandleByMapping` at `0x180047360`
- `ntdll!RtlGetActiveActivationContext` at `0x1800470d7`
- `ntdll!RtlGetActiveActivationContext` at `0x1800470d7`
- `ntdll!LdrAddLoadAsDataTable` at `0x1800470fa`
- `ntdll!LdrAddLoadAsDataTable` at `0x1800470fa`
- `ntdll!LdrAppxHandleIntegrityFailure` at `0x180047548`
- `ntdll!LdrAppxHandleIntegrityFailure` at `0x180047548`
- `ntdll!RtlAllocateHeap` at `0x1800474f8`
- `ntdll!RtlAllocateHeap` at `0x1800474f8`

## pseudocode

```c
__int64 __fastcall BasepLoadLibraryAsDataFileInternal(
        struct _UNICODE_STRING *Source,
        PCWSTR SourceString,
        WCHAR *a3,
        char a4,
        unsigned __int64 *a5)
{
  char v5; // di
  NTSTATUS v10; // eax
  int DllHandleByName; // ebx
  __int64 Length; // r9
  char v13; // r8
  PWSTR Buffer; // rdx
  __int16 *v15; // rax
  __int16 v16; // cx
  const WCHAR *v17; // rcx
  HANDLE v18; // rdi
  ULONG v19; // eax
  unsigned __int64 v20; // rsi
  USHORT v22; // cx
  struct _UNICODE_STRING *p_i; // rcx
  HANDLE FileW; // rax
  NTSTATUS v25; // eax
  ULONG v26; // ecx
  unsigned int v27; // ebx
  PVOID BaseAddress; // [rsp+50h] [rbp-B0h] BYREF
  PUNICODE_STRING FullNameOut; // [rsp+58h] [rbp-A8h] BYREF
  ULONG_PTR ViewSize; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE SectionHandle; // [rsp+68h] [rbp-98h] BYREF
  PVOID P[2]; // [rsp+70h] [rbp-90h] BYREF
  PVOID Context; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+88h] [rbp-78h] BYREF
  struct _UNICODE_STRING StaticString; // [rsp+98h] [rbp-68h] BYREF
  HANDLE v36; // [rsp+A8h] [rbp-58h] BYREF
  PIMAGE_NT_HEADERS NtHeader; // [rsp+B0h] [rbp-50h] BYREF
  struct _UNICODE_STRING i; // [rsp+B8h] [rbp-48h] BYREF
  struct _UNICODE_STRING PathString; // [rsp+C8h] [rbp-38h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v41; // [rsp+E8h] [rbp-18h]
  _BYTE v42[28]; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v43; // [rsp+118h] [rbp+18h]
  char v44; // [rsp+130h] [rbp+30h] BYREF

  v5 = 0;
  StaticString.Buffer = (PWSTR)&v44;
  Context = 0;
  FullNameOut = 0;
  NtHeader = 0;
  SectionHandle = 0;
  *(_QWORD *)&StaticString.Length = 0x1000000;
  BaseAddress = 0;
  ViewSize = 0;
  DestinationString = 0;
  PathString = 0;
  *(_OWORD *)P = 0;
  i = 0;
  UnicodeString = 0;
  v10 = RtlDosApplyFileIsolationRedirection_Ustr(
          1u,
          Source,
          (PUNICODE_STRING)&DefaultExtension,
          &StaticString,
          &UnicodeString,
          &FullNameOut,
          0,
          0,
          0);
  DllHandleByName = v10;
  if ( v10 >= 0 )
  {
    DllHandleByName = LdrGetDllHandleByName(0, FullNameOut, a5);
    if ( DllHandleByName != -1073741515 )
      goto LABEL_46;
  }
  else
  {
    if ( v10 != -1072365560 )
      return (unsigned int)DllHandleByName;
    Length = Source->Length;
    v13 = 0;
    Buffer = Source->Buffer;
    v15 = (__int16 *)((char *)Buffer + Length);
    while ( --v15 >= (__int16 *)Buffer )
    {
      v16 = *v15;
      if ( *v15 == 46 )
      {
        v13 = 1;
        while ( 1 )
        {
          if ( --v15 < (__int16 *)Buffer )
            goto LABEL_32;
          if ( *v15 == 47 || *v15 == 92 )
          {
            v5 = 1;
            goto LABEL_14;
          }
        }
      }
      if ( v16 == 92 || v16 == 47 )
      {
        v5 = 1;
        goto LABEL_14;
      }
    }
LABEL_32:
    P[1] = 0;
    if ( v13 )
    {
      v22 = _mm_cvtsi128_si32(*(__m128i *)Source);
      for ( i = *Source; v22 >= 2u; i.Length = v22 )
      {
        if ( i.Buffer[((unsigned __int64)v22 >> 1) - 1] != 46 )
          break;
        v22 -= 2;
      }
      p_i = &i;
    }
    else
    {
      v27 = Length + 10;
      if ( (unsigned int)(Length + 10) > 0xFFFE )
        return (unsigned int)-1073741562;
      P[1] = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v27);
      if ( !P[1] )
        return (unsigned int)-1073741801;
      LOWORD(P[0]) = 0;
      WORD1(P[0]) = v27;
      RtlAppendUnicodeStringToString((PUNICODE_STRING)P, Source);
      RtlAppendUnicodeStringToString((PUNICODE_STRING)P, &DefaultExtension);
      p_i = (struct _UNICODE_STRING *)P;
    }
    FullNameOut = p_i;
    DllHandleByName = LdrGetDllHandleByName(p_i, 0, a5);
    if ( P[1] )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[1]);
    if ( DllHandleByName != -1073741515 )
      return (unsigned int)DllHandleByName;
LABEL_14:
    if ( !a3 )
      goto LABEL_15;
    DllHandleByName = RtlInitUnicodeStringEx(&PathString, a3);
    if ( DllHandleByName < 0 )
      return (unsigned int)DllHandleByName;
    a3 = 0;
    DllHandleByName = RtlDosSearchPath_Ustr(
                        6u,
                        &PathString,
                        Source,
                        (PUNICODE_STRING)&DefaultExtension,
                        &StaticString,
                        &UnicodeString,
                        &FullNameOut,
                        0,
                        0);
    if ( DllHandleByName == -1073741809 )
    {
LABEL_15:
      DllHandleByName = RtlInitUnicodeStringEx(&DestinationString, SourceString);
      if ( DllHandleByName < 0 )
        return (unsigned int)DllHandleByName;
      DllHandleByName = RtlDosSearchPath_Ustr(
                          6u,
                          &DestinationString,
                          Source,
                          (PUNICODE_STRING)&DefaultExtension,
                          &StaticString,
                          &UnicodeString,
                          &FullNameOut,
                          (PSIZE_T)a3,
                          (PSIZE_T)a3);
    }
    if ( DllHandleByName < 0 )
      return (unsigned int)DllHandleByName;
    if ( v5 )
    {
      DllHandleByName = LdrGetDllHandleByName(0, FullNameOut, a5);
      if ( DllHandleByName != -1073741515 )
        goto LABEL_46;
    }
  }
  v17 = FullNameOut->Buffer;
  if ( (a4 & 0x20) == 0 )
  {
    FileW = CreateFileW(v17, 0x80000000, 5u, 0, 3u, 0, 0);
    v18 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
LABEL_72:
      DllHandleByName = NtCurrentTeb()->LastStatusValue;
      goto LABEL_46;
    }
    memset(v42, 0, sizeof(v42));
    v36 = 0;
    v41 = 0;
    v43 = 0;
    v25 = NtCreateSection(&v36, 0xF0005u, 0, 0, 2u, 0x8000000u, FileW);
    if ( v25 < 0 )
    {
      if ( v25 == -1073740702 || (unsigned int)(v25 + 1073740674) <= 1 )
        v25 = LdrAppxHandleIntegrityFailure((unsigned int)v25);
      BaseSetLastNTError((unsigned int)v25);
      SectionHandle = 0;
    }
    else
    {
      if ( v25 == 0x40000000 )
        v26 = 183;
      else
        v26 = 0;
      RtlSetLastWin32Error(v26);
      SectionHandle = v36;
      if ( v36 )
      {
        BaseAddress = 0;
        ViewSize = 0;
        DllHandleByName = NtMapViewOfSection(
                            v36,
                            (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                            &BaseAddress,
                            0,
                            0,
                            0,
                            &ViewSize,
                            ViewShare,
                            0,
                            2u);
        if ( DllHandleByName < 0 )
          goto LABEL_44;
        DllHandleByName = RtlImageNtHeaderEx(0, BaseAddress, ViewSize, &NtHeader);
        if ( DllHandleByName >= 0 )
        {
          DllHandleByName = LdrGetDllHandleByMapping(BaseAddress, a5);
          if ( DllHandleByName == -1073741515 )
          {
            v20 = (unsigned __int64)BaseAddress | 1;
            if ( (a4 & 0x40) == 0 )
            {
              NtClose(v18);
LABEL_58:
              NtClose(SectionHandle);
              goto LABEL_28;
            }
            DllHandleByName = BasepTrackDataFileHandle((unsigned __int64)BaseAddress | 1, v18);
            if ( DllHandleByName >= 0 )
              goto LABEL_58;
          }
        }
LABEL_43:
        NtUnmapViewOfSection((HANDLE)0xFFFFFFFFFFFFFFFFLL, BaseAddress);
LABEL_44:
        NtClose(SectionHandle);
LABEL_45:
        NtClose(v18);
        goto LABEL_46;
      }
    }
    DllHandleByName = NtCurrentTeb()->LastStatusValue;
    goto LABEL_45;
  }
  v18 = CreateFileW(v17, 0xA0000000, 5u, 0, 3u, 0, 0);
  if ( v18 != (HANDLE)-1LL )
    goto LABEL_22;
  DllHandleByName = NtCurrentTeb()->LastStatusValue;
  if ( DllHandleByName != -1073741809 )
  {
    v18 = CreateFileW(FullNameOut->Buffer, 0x80000000, 5u, 0, 3u, 0, 0);
    if ( v18 != (HANDLE)-1LL )
    {
LABEL_22:
      v19 = 285212672;
      if ( (NtCurrentPeb()->BitField & 2) != 0 && (a4 & 0x42) == 0 )
        v19 = 0x1000000;
      DllHandleByName = NtCreateSection(&SectionHandle, 5u, 0, 0, 2u, v19, v18);
      if ( DllHandleByName < 0 )
        goto LABEL_45;
      BaseAddress = 0;
      ViewSize = 0;
      DllHandleByName = NtMapViewOfSection(
                          SectionHandle,
                          (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                          &BaseAddress,
                          0,
                          0,
                          0,
                          &ViewSize,
                          ViewShare,
                          0x40000u,
                          2u);
      if ( DllHandleByName < 0 )
        goto LABEL_44;
      DllHandleByName = RtlImageNtHeaderEx(0, BaseAddress, ViewSize, &NtHeader);
      if ( DllHandleByName >= 0 )
      {
        DllHandleByName = LdrGetDllHandleByMapping(BaseAddress, a5);
        if ( DllHandleByName == -1073741515 )
        {
          NtClose(SectionHandle);
          NtClose(v18);
          v20 = (unsigned __int64)BaseAddress | 2;
LABEL_28:
          Context = 0;
          RtlGetActiveActivationContext(&Context);
          LdrAddLoadAsDataTable(v20, FullNameOut->Buffer, ViewSize, 0, Context);
          if ( UnicodeString.Buffer )
            RtlFreeUnicodeString(&UnicodeString);
          *a5 = v20;
          return 0;
        }
      }
      goto LABEL_43;
    }
    goto LABEL_72;
  }
LABEL_46:
  if ( UnicodeString.Buffer )
    RtlFreeUnicodeString(&UnicodeString);
  return (unsigned int)DllHandleByName;
}

```

## disassembly

```asm
0x180046dc0  mov     [rsp-8+arg_18], rbx
0x180046dc5  push    rbp
0x180046dc6  push    rsi
0x180046dc7  push    rdi
0x180046dc8  push    r12
0x180046dca  push    r13
0x180046dcc  push    r14
0x180046dce  push    r15
0x180046dd0  lea     rbp, [rsp-140h]
0x180046dd8  sub     rsp, 240h
0x180046ddf  mov     rax, cs:__security_cookie
0x180046de6  xor     rax, rsp
0x180046de9  mov     [rbp+170h+var_40], rax
0x180046df0  mov     r14, [rbp+170h+arg_20]
0x180046df7  lea     rax, [rbp+170h+var_140]
0x180046dfb  xor     edi, edi
0x180046dfd  mov     [rbp+170h+StaticString.Buffer], rax
0x180046e01  xorps   xmm0, xmm0
0x180046e04  mov     [rsp+270h+RequiredLength], rdi; RequiredLength
0x180046e09  mov     [rsp+270h+FileNameSize], rdi; FileNameSize
0x180046e0e  lea     rax, [rsp+270h+FullNameOut]
0x180046e13  mov     [rsp+270h+NewFlags], rdi; NewFlags
0x180046e18  mov     r12, rdx
0x180046e1b  mov     [rsp+270h+NewName], rax; NewName
0x180046e20  mov     r13d, r9d
0x180046e23  lea     rax, [rbp+170h+UnicodeString]
0x180046e27  mov     [rbp+170h+Context], rdi
0x180046e2b  mov     r15, r8
0x180046e2e  mov     [rsp+270h+DynamicString], rax; DynamicString
0x180046e33  mov     rsi, rcx
0x180046e36  mov     [rsp+270h+FullNameOut], rdi
0x180046e3b  xorps   xmm1, xmm1
0x180046e3e  mov     [rbp+170h+NtHeader], rdi
0x180046e42  mov     rdx, rcx; OriginalName
0x180046e45  mov     [rsp+270h+SectionHandle], rdi
0x180046e4a  lea     r9, [rbp+170h+StaticString]; StaticString
0x180046e4e  mov     qword ptr [rbp+170h+StaticString.Length], 1000000h
0x180046e56  lea     r8, DefaultExtension; Extension
0x180046e5d  mov     [rsp+270h+BaseAddress], rdi
0x180046e62  mov     ecx, 1; Flags
0x180046e67  mov     [rsp+270h+ViewSize], rdi
0x180046e6c  movups  xmmword ptr [rbp+170h+DestinationString.Length], xmm0
0x180046e70  movups  xmmword ptr [rbp+170h+PathString.Length], xmm1
0x180046e74  movups  xmmword ptr [rsp+270h+P], xmm0
0x180046e79  movups  [rbp+170h+var_1B8], xmm0
0x180046e7d  movups  xmmword ptr [rbp+170h+UnicodeString.Length], xmm0
0x180046e81  call    cs:__imp_RtlDosApplyFileIsolationRedirection_Ustr
0x180046e87  mov     ebx, eax
0x180046e89  test    eax, eax
0x180046e8b  jns     loc_18004739F
0x180046e91  cmp     eax, 0C0150008h
0x180046e96  jnz     loc_180047117
0x180046e9c  movzx   r9d, word ptr [rsi]
0x180046ea0  xor     r8b, r8b
0x180046ea3  mov     rdx, [rsi+8]
0x180046ea7  lea     rax, [rdx+r9]
0x180046eab  sub     rax, 2
0x180046eaf  cmp     rax, rdx
0x180046eb2  jb      loc_180047143
0x180046eb8  movzx   ecx, word ptr [rax]
0x180046ebb  cmp     cx, 2Eh ; '.'
0x180046ebf  jz      short loc_180046ED2
0x180046ec1  cmp     cx, 5Ch ; '\'
0x180046ec5  jz      short loc_180046ECD
0x180046ec7  cmp     cx, 2Fh ; '/'
0x180046ecb  jnz     short loc_180046EAB
0x180046ecd  mov     dil, 1
0x180046ed0  jmp     short loc_180046F00
0x180046ed2  mov     r8b, 1
0x180046ed5  nop     word ptr [rax+rax+00000000h]
0x180046ee0  sub     rax, 2
0x180046ee4  cmp     rax, rdx
0x180046ee7  jb      loc_180047143
0x180046eed  movzx   ecx, word ptr [rax]
0x180046ef0  cmp     cx, 2Fh ; '/'
0x180046ef4  jz      short loc_180046EFC
0x180046ef6  cmp     cx, 5Ch ; '\'
0x180046efa  jnz     short loc_180046EE0
0x180046efc  movzx   edi, r8b
0x180046f00  test    r15, r15
0x180046f03  jnz     loc_1800471B1
0x180046f09  mov     rdx, r12; SourceString
0x180046f0c  lea     rcx, [rbp+170h+DestinationString]; DestinationString
0x180046f10  call    cs:__imp_RtlInitUnicodeStringEx
0x180046f16  mov     ebx, eax
0x180046f18  test    eax, eax
0x180046f1a  js      loc_180047117
0x180046f20  mov     [rsp+270h+RequiredLength], r15; LengthNeeded
0x180046f25  lea     rax, [rsp+270h+FullNameOut]
0x180046f2a  mov     [rsp+270h+FileNameSize], r15; FilePartSize
0x180046f2f  lea     r9, DefaultExtension; ExtensionString
0x180046f36  mov     [rsp+270h+NewFlags], rax; FullNameOut
0x180046f3b  lea     rdx, [rbp+170h+DestinationString]; PathString
0x180046f3f  lea     rax, [rbp+170h+UnicodeString]
0x180046f43  mov     r8, rsi; FileNameString
0x180046f46  mov     [rsp+270h+NewName], rax; DynamicString
0x180046f4b  mov     ecx, 6; Flags
0x180046f50  lea     rax, [rbp+170h+StaticString]
0x180046f54  mov     [rsp+270h+DynamicString], rax; CallerBuffer
0x180046f59  call    cs:__imp_RtlDosSearchPath_Ustr
0x180046f5f  mov     ebx, eax
0x180046f61  test    ebx, ebx
0x180046f63  js      loc_180047117
0x180046f69  test    dil, dil
0x180046f6c  jz      short loc_180046F8B
0x180046f6e  mov     rdx, [rsp+270h+FullNameOut]
0x180046f73  mov     r8, r14
0x180046f76  xor     ecx, ecx
0x180046f78  call    cs:__imp_LdrGetDllHandleByName
0x180046f7e  mov     ebx, eax
0x180046f80  cmp     eax, 0C0000135h
0x180046f85  jnz     loc_180047242
0x180046f8b  xor     edi, edi
0x180046f8d  mov     rcx, [rsp+270h+FullNameOut]
0x180046f92  xor     r9d, r9d; lpSecurityAttributes
0x180046f95  mov     [rsp+270h+NewFlags], rdi; hTemplateFile
0x180046f9a  mov     r8d, 5; dwShareMode
0x180046fa0  mov     dword ptr [rsp+270h+NewName], edi; dwFlagsAndAttributes
0x180046fa4  mov     dword ptr [rsp+270h+DynamicString], 3; dwCreationDisposition
0x180046fac  mov     rcx, [rcx+8]; lpFileName
0x180046fb0  test    r13b, 20h
0x180046fb4  jz      loc_18004725C
0x180046fba  mov     edx, 0A0000000h; dwDesiredAccess
0x180046fbf  call    CreateFileW
0x180046fc4  mov     rdi, rax
0x180046fc7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180046fcb  jz      loc_180047449
0x180046fd1  xor     r15d, r15d
0x180046fd4  mov     rax, gs:60h
0x180046fdd  test    byte ptr [rax+3], 2
0x180046fe1  mov     eax, 11000000h
0x180046fe6  jnz     loc_18004741A
0x180046fec  mov     [rsp+270h+NewFlags], rdi; FileHandle
0x180046ff1  lea     rcx, [rsp+270h+SectionHandle]; SectionHandle
0x180046ff6  mov     dword ptr [rsp+270h+NewName], eax; AllocationAttributes
0x180046ffa  xor     r9d, r9d; MaximumSize
0x180046ffd  xor     r8d, r8d; ObjectAttributes
0x180047000  mov     dword ptr [rsp+270h+DynamicString], 2; SectionPageProtection
0x180047008  mov     edx, 5; DesiredAccess
0x18004700d  call    cs:__imp_NtCreateSection
0x180047013  mov     ebx, eax
0x180047015  test    eax, eax
0x180047017  js      loc_180047239
0x18004701d  mov     rcx, [rsp+270h+SectionHandle]; SectionHandle
0x180047022  lea     rax, [rsp+270h+ViewSize]
0x180047027  mov     [rsp+270h+AccessProtection], 2; AccessProtection
0x18004702f  lea     r8, [rsp+270h+BaseAddress]; BaseAddress
0x180047034  mov     dword ptr [rsp+270h+RequiredLength], 40000h; AllocationType
0x18004703c  xor     r9d, r9d; ZeroBits
0x18004703f  mov     dword ptr [rsp+270h+FileNameSize], 1; InheritDisposition
0x180047047  mov     rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18004704e  mov     [rsp+270h+NewFlags], rax; ViewSize
0x180047053  mov     [rsp+270h+NewName], r15; SectionOffset
0x180047058  mov     [rsp+270h+DynamicString], r15; CommitSize
0x18004705d  mov     [rsp+270h+BaseAddress], r15
0x180047062  mov     [rsp+270h+ViewSize], r15
0x180047067  call    cs:__imp_NtMapViewOfSection
0x18004706d  mov     ebx, eax
0x18004706f  test    eax, eax
0x180047071  js      loc_18004722E
0x180047077  mov     r8, [rsp+270h+ViewSize]; Size
0x18004707c  lea     r9, [rbp+170h+NtHeader]; NtHeader
0x180047080  mov     rdx, [rsp+270h+BaseAddress]; BaseAddress
0x180047085  xor     ecx, ecx; Flags
0x180047087  call    cs:__imp_RtlImageNtHeaderEx
0x18004708d  mov     ebx, eax
0x18004708f  test    eax, eax
0x180047091  js      loc_18004721C
0x180047097  mov     rcx, [rsp+270h+BaseAddress]
0x18004709c  mov     rdx, r14
0x18004709f  call    cs:__imp_LdrGetDllHandleByMapping
0x1800470a5  mov     ebx, eax
0x1800470a7  cmp     eax, 0C0000135h
0x1800470ac  jnz     loc_18004721C
0x1800470b2  mov     rcx, [rsp+270h+SectionHandle]; Handle
0x1800470b7  call    cs:__imp_NtClose
0x1800470bd  mov     rcx, rdi; Handle
0x1800470c0  call    cs:__imp_NtClose
0x1800470c6  mov     rsi, [rsp+270h+BaseAddress]
0x1800470cb  or      rsi, 2
0x1800470cf  lea     rcx, [rbp+170h+Context]; Context
0x1800470d3  mov     [rbp+170h+Context], r15
0x1800470d7  call    cs:__imp_RtlGetActiveActivationContext
0x1800470dd  mov     rdx, [rsp+270h+FullNameOut]
0x1800470e2  xor     r9d, r9d
0x1800470e5  mov     rax, [rbp+170h+Context]
0x1800470e9  mov     rcx, rsi
0x1800470ec  mov     r8, [rsp+270h+ViewSize]
0x1800470f1  mov     [rsp+270h+DynamicString], rax
0x1800470f6  mov     rdx, [rdx+8]
0x1800470fa  call    cs:__imp_LdrAddLoadAsDataTable
0x180047100  cmp     [rbp+170h+UnicodeString.Buffer], 0
0x180047105  jz      short loc_180047111
0x180047107  lea     rcx, [rbp+170h+UnicodeString]; UnicodeString
0x18004710b  call    cs:__imp_RtlFreeUnicodeString
0x180047111  mov     [r14], rsi
0x180047114  mov     ebx, r15d
0x180047117  mov     eax, ebx
0x180047119  mov     rcx, [rbp+170h+var_40]
0x180047120  xor     rcx, rsp; StackCookie
0x180047123  call    __security_check_cookie
0x180047128  mov     rbx, [rsp+270h+arg_18]
0x180047130  add     rsp, 240h
0x180047137  pop     r15
0x180047139  pop     r14
0x18004713b  pop     r13
0x18004713d  pop     r12
0x18004713f  pop     rdi
0x180047140  pop     rsi
0x180047141  pop     rbp
0x180047142  retn
0x180047143  mov     [rsp+270h+P+8], rdi
0x180047148  test    r8b, r8b
0x18004714b  jz      loc_1800474CD
0x180047151  movups  xmm0, xmmword ptr [rsi]
0x180047154  movd    ecx, xmm0
0x180047158  movups  [rbp+170h+var_1B8], xmm0
0x18004715c  cmp     cx, 2
0x180047160  jb      short loc_18004717E
0x180047162  mov     rdx, qword ptr [rbp+170h+var_1B8+8]
0x180047166  mov     r8d, 0FFFEh
0x18004716c  movzx   eax, cx
0x18004716f  shr     rax, 1
0x180047172  cmp     word ptr [rdx+rax*2-2], 2Eh ; '.'
0x180047178  jz      loc_1800474B6
0x18004717e  lea     rcx, [rbp+170h+var_1B8]
0x180047182  mov     r8, r14
0x180047185  mov     [rsp+270h+FullNameOut], rcx
0x18004718a  xor     edx, edx
0x18004718c  call    cs:__imp_LdrGetDllHandleByName
0x180047192  cmp     [rsp+270h+P+8], 0
0x180047198  mov     ebx, eax
0x18004719a  jnz     loc_1800473C1
0x1800471a0  cmp     ebx, 0C0000135h
0x1800471a6  jz      loc_180046F00
0x1800471ac  jmp     loc_180047117
0x1800471b1  mov     rdx, r15; SourceString
0x1800471b4  lea     rcx, [rbp+170h+PathString]; DestinationString
0x1800471b8  call    cs:__imp_RtlInitUnicodeStringEx
0x1800471be  mov     ebx, eax
0x1800471c0  test    eax, eax
0x1800471c2  js      loc_180047117
0x1800471c8  xor     r15d, r15d
0x1800471cb  lea     rax, [rsp+270h+FullNameOut]
0x1800471d0  mov     [rsp+270h+RequiredLength], r15; LengthNeeded
0x1800471d5  lea     r9, DefaultExtension; ExtensionString
0x1800471dc  mov     [rsp+270h+FileNameSize], r15; FilePartSize
0x1800471e1  lea     rdx, [rbp+170h+PathString]; PathString
0x1800471e5  mov     [rsp+270h+NewFlags], rax; FullNameOut
0x1800471ea  mov     r8, rsi; FileNameString
0x1800471ed  lea     rax, [rbp+170h+UnicodeString]
0x1800471f1  mov     ecx, 6; Flags
0x1800471f6  mov     [rsp+270h+NewName], rax; DynamicString
0x1800471fb  lea     rax, [rbp+170h+StaticString]
0x1800471ff  mov     [rsp+270h+DynamicString], rax; CallerBuffer
0x180047204  call    cs:__imp_RtlDosSearchPath_Ustr
0x18004720a  mov     ebx, eax
0x18004720c  cmp     eax, 0C000000Fh
0x180047211  jz      loc_180046F09
0x180047217  jmp     loc_180046F61
0x18004721c  mov     rdx, [rsp+270h+BaseAddress]; BaseAddress
0x180047221  mov     rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180047228  call    cs:__imp_NtUnmapViewOfSection
0x18004722e  mov     rcx, [rsp+270h+SectionHandle]; Handle
0x180047233  call    cs:__imp_NtClose
0x180047239  mov     rcx, rdi; Handle
0x18004723c  call    cs:__imp_NtClose
0x180047242  cmp     [rbp+170h+UnicodeString.Buffer], 0
0x180047247  jz      loc_180047117
0x18004724d  lea     rcx, [rbp+170h+UnicodeString]; UnicodeString
0x180047251  call    cs:__imp_RtlFreeUnicodeString
0x180047257  jmp     loc_180047117
0x18004725c  mov     edx, 80000000h; dwDesiredAccess
0x180047261  call    CreateFileW
0x180047266  mov     rdi, rax
0x180047269  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004726d  jz      loc_18004742B
0x180047273  xorps   xmm0, xmm0
0x180047276  mov     [rsp+270h+NewFlags], rdi; FileHandle
0x18004727b  movups  xmmword ptr [rbp+170h+var_178], xmm0
0x18004727f  xor     r15d, r15d
0x180047282  mov     dword ptr [rsp+270h+NewName], 8000000h; AllocationAttributes
0x18004728a  xor     eax, eax
0x18004728c  mov     [rbp+170h+var_1C8], r15
0x180047290  xor     r9d, r9d; MaximumSize
0x180047293  mov     dword ptr [rsp+270h+DynamicString], 2; SectionPageProtection
0x18004729b  xor     r8d, r8d; ObjectAttributes
0x18004729e  lea     rcx, [rbp+170h+var_1C8]; SectionHandle
0x1800472a2  mov     edx, 0F0005h; DesiredAccess
0x1800472a7  movups  xmmword ptr [rbp+170h+var_178+0Ch], xmm0
0x1800472ab  movups  [rbp+170h+var_188], xmm0
0x1800472af  movups  [rbp+170h+var_158], xmm0
0x1800472b3  call    cs:__imp_NtCreateSection
0x1800472b9  test    eax, eax
0x1800472bb  js      loc_1800473E0
0x1800472c1  cmp     eax, 40000000h
0x1800472c6  jz      loc_18004743F
0x1800472cc  xor     ecx, ecx; LastError
0x1800472ce  call    cs:__imp_RtlSetLastWin32Error
0x1800472d4  mov     rcx, [rbp+170h+var_1C8]; SectionHandle
  ... truncated ...
```
