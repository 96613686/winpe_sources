# AiParseAndTagUninstallerFromUninstallString

- ea: `0x140020db4`
- end: `0x14002110e`
- name: `AiParseAndTagUninstallerFromUninstallString`
- size: `858`
- prototype: `void __fastcall(UNICODE_STRING *, PWSTR Buffer)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update`

## callers

- `0x14001f3c0`

## callees

- `0x14002061c`
- `0x140020790`
- `0x140020a70`
- `0x140020cf4`
- `0x140020db4`
- `0x140021298`
- `0x140021634`
- `0x140024fec`
- `0x1400328b0`
- `0x140032a50`

## import_xrefs

- `ntoskrnl!RtlPrefixUnicodeString` at `0x140020f02`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140020f39`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140020f02`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140020f39`
- `ntoskrnl!RtlSuffixUnicodeString` at `0x140020ea3`
- `ntoskrnl!RtlSuffixUnicodeString` at `0x140020ea3`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140020fa0`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140020fa0`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140020fb4`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140020fb4`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002100d`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14002100d`
- `ntoskrnl!IoFileObjectType` at `0x140020fe7`
- `ntoskrnl!ObfDereferenceObject` at `0x1400210c0`
- `ntoskrnl!ObfDereferenceObject` at `0x1400210c0`
- `ntoskrnl!ZwClose` at `0x1400210d5`
- `ntoskrnl!ZwClose` at `0x1400210d5`

## pseudocode

```c
void __fastcall AiParseAndTagUninstallerFromUninstallString(UNICODE_STRING *a1, PWSTR Buffer)
{
  __int64 v2; // rbx
  __int64 v4; // r12
  UNICODE_STRING v5; // xmm0
  PVOID v6; // r14
  USHORT v7; // cx
  char v8; // r8
  void *v9; // rsi
  WCHAR *v10; // r15
  unsigned __int64 v11; // rax
  int CharInUnicodeString; // eax
  int v13; // eax
  WCHAR *v14; // rax
  USHORT v15; // di
  WCHAR *v16; // rax
  int v17; // eax
  NTSTATUS v18; // eax
  int v19; // eax
  void *v20; // [rsp+40h] [rbp-29h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-21h] BYREF
  _WORD *v22; // [rsp+50h] [rbp-19h] BYREF
  void *v23; // [rsp+58h] [rbp-11h] BYREF
  UNICODE_STRING Source; // [rsp+60h] [rbp-9h] BYREF
  UNICODE_STRING String2; // [rsp+70h] [rbp+7h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp+17h] BYREF
  PVOID Object; // [rsp+D0h] [rbp+67h] BYREF
  unsigned int v28; // [rsp+E0h] [rbp+77h] BYREF
  unsigned int v29; // [rsp+E8h] [rbp+7Fh] BYREF

  v2 = -1;
  v23 = 0;
  Source = 0;
  v4 = (__int64)Buffer;
  v5 = a1[1];
  Handle = (HANDLE)-1LL;
  v6 = 0;
  LOWORD(Object) = 0;
  v7 = _mm_cvtsi128_si32((__m128i)v5);
  v8 = 0;
  v22 = 0;
  v9 = 0;
  v20 = 0;
  v10 = 0;
  v29 = 0;
  v28 = 0;
  String2 = v5;
  DestinationString = 0;
  if ( v7 < 4u )
    goto LABEL_30;
  Buffer = String2.Buffer;
  v11 = v7;
  while ( !String2.Buffer[(v11 >> 1) - 1] )
  {
    v7 -= 2;
    v11 = v7;
    String2.Length = v7;
  }
  if ( v7 < 4u )
    goto LABEL_30;
  if ( *String2.Buffer == 34 )
  {
    Source.Buffer = String2.Buffer + 1;
    Source.Length = v7 - 2;
    Source.MaximumLength = String2.MaximumLength - 2;
    CharInUnicodeString = AiRtlFindCharInUnicodeString(0, &Source, &qword_140009278, &Object);
    v8 = CharInUnicodeString;
    if ( CharInUnicodeString < 0 )
      goto LABEL_30;
    goto LABEL_12;
  }
  if ( RtlSuffixUnicodeString(&String1, &String2, 1u) )
    goto LABEL_14;
  v13 = AiRtlFindCharInUnicodeString(0, &String2, &qword_140009258, &Object);
  if ( v13 >= 0 )
  {
    Source = String2;
LABEL_12:
    Source.Length = (_WORD)Object - 2;
    goto LABEL_15;
  }
  if ( v13 == -1073741275 )
LABEL_14:
    Source = String2;
LABEL_15:
  if ( RtlPrefixUnicodeString(&stru_140009248, &Source, 1u) )
  {
    *(_DWORD *)(&Source.MaximumLength + 1) = 0;
    v14 = L"\\SystemRoot\\System32\\msiexec.exe";
    *(_DWORD *)&Source.Length = 4325440;
  }
  else
  {
    if ( !RtlPrefixUnicodeString(&stru_140009228, &Source, 1u) )
    {
      v15 = Source.Length + 24;
      v16 = (WCHAR *)AiAlloc((unsigned int)Source.Length + 24);
      v10 = v16;
      if ( !v16 )
      {
        v8 = 23;
        goto LABEL_30;
      }
      DestinationString.Buffer = v16;
      DestinationString.MaximumLength = v15;
      DestinationString.Length = 0;
      RtlCopyUnicodeString(&DestinationString, &stru_140009208);
      RtlAppendUnicodeStringToString(&DestinationString, &Source);
      Source = DestinationString;
      goto LABEL_23;
    }
    *(_DWORD *)(&Source.MaximumLength + 1) = 0;
    v14 = L"\\SystemRoot\\System32\\rundll32.exe";
    *(_DWORD *)&Source.Length = 4456514;
  }
  Source.Buffer = v14;
LABEL_23:
  v17 = AiOpenFile(&Source, &Handle);
  v2 = (__int64)Handle;
  v8 = v17;
  if ( v17 >= 0 )
  {
    Object = 0;
    v18 = ObReferenceObjectByHandle(Handle, 1u, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0);
    v6 = Object;
    v8 = v18;
    if ( v18 >= 0 )
    {
      v19 = (int)AiGetUninstallStringEa((__int64)Object, (__int64 *)&v22, &v29, (__int64 *)&v23) < 0
          ? AiAllocUninstallStringEaData((const void **)&String2, v4, (__int64 *)&v20, &v28)
          : AiAddUninstallStringToUninstallStringEaData((const void **)&String2, v22, v29, &v20, &v28);
      v9 = v20;
      v8 = v19;
      if ( v19 >= 0 )
        v8 = AiSetUninstallStringEa(v6, v20, v28);
    }
  }
LABEL_30:
  AiLogRegisterUninstallerEvent(
    qword_1400196F8,
    (__int64)Buffer,
    &String2.Length,
    &Source.Length,
    &a1[2].Length,
    v4,
    v8);
  AiFree(v10);
  if ( v6 )
    ObfDereferenceObject(v6);
  if ( v2 != -1 )
    ZwClose((HANDLE)v2);
  AiFree(v23);
  AiFree(v9);
}

```

## disassembly

```asm
0x140020db4  mov     [rsp-8+arg_8], rbx
0x140020db9  push    rbp
0x140020dba  push    rsi
0x140020dbb  push    rdi
0x140020dbc  push    r12
0x140020dbe  push    r13
0x140020dc0  push    r14
0x140020dc2  push    r15
0x140020dc4  lea     rbp, [rsp-27h]
0x140020dc9  sub     rsp, 90h
0x140020dd0  xor     edi, edi
0x140020dd2  xorps   xmm0, xmm0
0x140020dd5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140020dd9  mov     [rbp+57h+var_68], rdi
0x140020ddd  movups  xmmword ptr [rbp+57h+Source.Length], xmm0
0x140020de1  mov     r13, rcx
0x140020de4  mov     r12, rdx
0x140020de7  movups  xmm0, xmmword ptr [rcx+10h]
0x140020deb  mov     [rbp+57h+Handle], rbx
0x140020def  mov     r14d, edi
0x140020df2  xorps   xmm1, xmm1
0x140020df5  mov     word ptr [rbp+57h+arg_0], di
0x140020df9  movd    ecx, xmm0
0x140020dfd  mov     r8d, edi
0x140020e00  mov     [rbp+57h+var_70], rdi
0x140020e04  mov     esi, edi
0x140020e06  mov     [rbp+57h+var_80], rdi
0x140020e0a  mov     r15d, edi
0x140020e0d  mov     [rbp+57h+arg_18], edi
0x140020e10  mov     [rbp+57h+arg_10], edi
0x140020e13  movaps  xmmword ptr [rbp+57h+String2.Length], xmm0
0x140020e17  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x140020e1b  cmp     cx, 4
0x140020e1f  jb      loc_140021089
0x140020e25  mov     rdx, [rbp+57h+String2.Buffer]
0x140020e29  movzx   eax, cx
0x140020e2c  jmp     short loc_140020E3C
0x140020e2e  sub     cx, 2
0x140020e32  movzx   eax, cx
0x140020e35  movzx   ecx, ax
0x140020e38  mov     [rbp+57h+String2.Length], ax
0x140020e3c  shr     rax, 1
0x140020e3f  cmp     [rdx+rax*2-2], di
0x140020e44  jz      short loc_140020E2E
0x140020e46  cmp     cx, 4
0x140020e4a  jb      loc_140021089
0x140020e50  cmp     word ptr [rdx], 22h ; '"'
0x140020e54  jnz     short loc_140020E95
0x140020e56  lea     rax, [rdx+2]
0x140020e5a  sub     cx, 2
0x140020e5e  mov     [rbp+57h+Source.Buffer], rax
0x140020e62  lea     r9, [rbp+57h+arg_0]
0x140020e66  movzx   eax, [rbp+57h+String2.MaximumLength]
0x140020e6a  lea     r8, qword_140009278
0x140020e71  sub     ax, 2
0x140020e75  mov     [rbp+57h+Source.Length], cx
0x140020e79  lea     rdx, [rbp+57h+Source]
0x140020e7d  mov     [rbp+57h+Source.MaximumLength], ax
0x140020e81  xor     ecx, ecx
0x140020e83  call    AiRtlFindCharInUnicodeString
0x140020e88  mov     r8d, eax
0x140020e8b  test    eax, eax
0x140020e8d  js      loc_140021089
0x140020e93  jmp     short loc_140020ED6
0x140020e95  mov     r8b, 1; CaseInSensitive
0x140020e98  lea     rdx, [rbp+57h+String2]; String2
0x140020e9c  lea     rcx, String1; String1
0x140020ea3  call    cs:__imp_RtlSuffixUnicodeString
0x140020eaa  nop     dword ptr [rax+rax+00h]
0x140020eaf  test    al, al
0x140020eb1  jnz     short loc_140020EEB
0x140020eb3  lea     r9, [rbp+57h+arg_0]
0x140020eb7  xor     ecx, ecx
0x140020eb9  lea     r8, qword_140009258
0x140020ec0  lea     rdx, [rbp+57h+String2]
0x140020ec4  call    AiRtlFindCharInUnicodeString
0x140020ec9  test    eax, eax
0x140020ecb  js      short loc_140020EE4
0x140020ecd  movaps  xmm0, xmmword ptr [rbp+57h+String2.Length]
0x140020ed1  movdqa  xmmword ptr [rbp+57h+Source.Length], xmm0
0x140020ed6  movzx   eax, word ptr [rbp+57h+arg_0]
0x140020eda  sub     ax, 2
0x140020ede  mov     [rbp+57h+Source.Length], ax
0x140020ee2  jmp     short loc_140020EF4
0x140020ee4  cmp     eax, 0C0000225h
0x140020ee9  jnz     short loc_140020EF4
0x140020eeb  movaps  xmm0, xmmword ptr [rbp+57h+String2.Length]
0x140020eef  movdqa  xmmword ptr [rbp+57h+Source.Length], xmm0
0x140020ef4  mov     r8b, 1; CaseInSensitive
0x140020ef7  lea     rdx, [rbp+57h+Source]; String2
0x140020efb  lea     rcx, stru_140009248; String1
0x140020f02  call    cs:__imp_RtlPrefixUnicodeString
0x140020f09  nop     dword ptr [rax+rax+00h]
0x140020f0e  test    al, al
0x140020f10  jz      short loc_140020F2B
0x140020f12  mov     eax, cs:dword_14000923C
0x140020f18  mov     dword ptr [rbp+57h+Source+4], eax
0x140020f1b  mov     rax, cs:off_140009240; "\\SystemRoot\\System32\\msiexec.exe"
0x140020f22  mov     dword ptr [rbp+57h+Source.Length], 420040h
0x140020f29  jmp     short loc_140020F60
0x140020f2b  mov     r8b, 1; CaseInSensitive
0x140020f2e  lea     rdx, [rbp+57h+Source]; String2
0x140020f32  lea     rcx, stru_140009228; String1
0x140020f39  call    cs:__imp_RtlPrefixUnicodeString
0x140020f40  nop     dword ptr [rax+rax+00h]
0x140020f45  test    al, al
0x140020f47  jz      short loc_140020F66
0x140020f49  mov     eax, cs:dword_14000921C
0x140020f4f  mov     dword ptr [rbp+57h+Source+4], eax
0x140020f52  mov     rax, cs:off_140009220; "\\SystemRoot\\System32\\rundll32.exe"
0x140020f59  mov     dword ptr [rbp+57h+Source.Length], 440042h
0x140020f60  mov     [rbp+57h+Source.Buffer], rax
0x140020f64  jmp     short loc_140020FCB
0x140020f66  movzx   edi, [rbp+57h+Source.Length]
0x140020f6a  add     edi, 18h
0x140020f6d  mov     ecx, edi
0x140020f6f  call    AiAlloc
0x140020f74  mov     r15, rax
0x140020f77  test    rax, rax
0x140020f7a  jnz     short loc_140020F87
0x140020f7c  mov     r8d, 0C0000017h
0x140020f82  jmp     loc_140021089
0x140020f87  mov     [rbp+57h+DestinationString.Buffer], rax
0x140020f8b  lea     rdx, stru_140009208; SourceString
0x140020f92  xor     eax, eax
0x140020f94  mov     [rbp+57h+DestinationString.MaximumLength], di
0x140020f98  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140020f9c  mov     [rbp+57h+DestinationString.Length], ax
0x140020fa0  call    cs:__imp_RtlCopyUnicodeString
0x140020fa7  nop     dword ptr [rax+rax+00h]
0x140020fac  lea     rdx, [rbp+57h+Source]; Source
0x140020fb0  lea     rcx, [rbp+57h+DestinationString]; Destination
0x140020fb4  call    cs:__imp_RtlAppendUnicodeStringToString
0x140020fbb  nop     dword ptr [rax+rax+00h]
0x140020fc0  movaps  xmm0, xmmword ptr [rbp+57h+DestinationString.Length]
0x140020fc4  xor     edi, edi
0x140020fc6  movdqa  xmmword ptr [rbp+57h+Source.Length], xmm0
0x140020fcb  lea     rdx, [rbp+57h+Handle]
0x140020fcf  lea     rcx, [rbp+57h+Source]
0x140020fd3  call    AiOpenFile
0x140020fd8  mov     rbx, [rbp+57h+Handle]
0x140020fdc  mov     r8d, eax
0x140020fdf  test    eax, eax
0x140020fe1  js      loc_140021089
0x140020fe7  mov     r8, cs:__imp_IoFileObjectType
0x140020fee  lea     rax, [rbp+57h+arg_0]
0x140020ff2  xor     r9d, r9d; AccessMode
0x140020ff5  mov     [rsp+0C0h+HandleInformation], rdi; HandleInformation
0x140020ffa  mov     rcx, rbx; Handle
0x140020ffd  mov     [rbp+57h+arg_0], rdi
0x140021001  mov     [rsp+0C0h+Object], rax; Object
0x140021006  mov     r8, [r8]; ObjectType
0x140021009  lea     edx, [r9+1]; DesiredAccess
0x14002100d  call    cs:__imp_ObReferenceObjectByHandle
0x140021014  nop     dword ptr [rax+rax+00h]
0x140021019  mov     r14, [rbp+57h+arg_0]
0x14002101d  mov     r8d, eax
0x140021020  test    eax, eax
0x140021022  js      short loc_140021089
0x140021024  lea     r9, [rbp+57h+var_68]
0x140021028  mov     rcx, r14
0x14002102b  lea     r8, [rbp+57h+arg_18]
0x14002102f  lea     rdx, [rbp+57h+var_70]
0x140021033  call    AiGetUninstallStringEa
0x140021038  lea     rcx, [rbp+57h+String2]
0x14002103c  test    eax, eax
0x14002103e  js      short loc_14002105C
0x140021040  mov     r8d, [rbp+57h+arg_18]
0x140021044  lea     rax, [rbp+57h+arg_10]
0x140021048  mov     rdx, [rbp+57h+var_70]
0x14002104c  lea     r9, [rbp+57h+var_80]
0x140021050  mov     [rsp+0C0h+Object], rax
0x140021055  call    AiAddUninstallStringToUninstallStringEaData
0x14002105a  jmp     short loc_14002106C
0x14002105c  lea     r9, [rbp+57h+arg_10]
0x140021060  mov     rdx, r12
0x140021063  lea     r8, [rbp+57h+var_80]
0x140021067  call    AiAllocUninstallStringEaData
0x14002106c  mov     rsi, [rbp+57h+var_80]
0x140021070  mov     r8d, eax
0x140021073  test    eax, eax
0x140021075  js      short loc_140021089
0x140021077  mov     r8d, [rbp+57h+arg_10]
0x14002107b  mov     rdx, rsi
0x14002107e  mov     rcx, r14
0x140021081  call    AiSetUninstallStringEa
0x140021086  mov     r8d, eax
0x140021089  mov     rcx, cs:qword_1400196F8; RegHandle
0x140021090  lea     rax, [r13+20h]
0x140021094  mov     [rsp+0C0h+var_90], r8d; int
0x140021099  lea     r9, [rbp+57h+Source]
0x14002109d  mov     [rsp+0C0h+HandleInformation], r12; __int64
0x1400210a2  lea     r8, [rbp+57h+String2]
0x1400210a6  mov     [rsp+0C0h+Object], rax; __int64
0x1400210ab  call    AiLogRegisterUninstallerEvent
0x1400210b0  mov     rcx, r15
0x1400210b3  call    AiFree
0x1400210b8  test    r14, r14
0x1400210bb  jz      short loc_1400210CC
0x1400210bd  mov     rcx, r14; Object
0x1400210c0  call    cs:__imp_ObfDereferenceObject
0x1400210c7  nop     dword ptr [rax+rax+00h]
0x1400210cc  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1400210d0  jz      short loc_1400210E1
0x1400210d2  mov     rcx, rbx; Handle
0x1400210d5  call    cs:__imp_ZwClose
0x1400210dc  nop     dword ptr [rax+rax+00h]
0x1400210e1  mov     rcx, [rbp+57h+var_68]
0x1400210e5  call    AiFree
0x1400210ea  mov     rcx, rsi
0x1400210ed  call    AiFree
0x1400210f2  mov     rbx, [rsp+0C0h+arg_8]
0x1400210fa  add     rsp, 90h
0x140021101  pop     r15
0x140021103  pop     r14
0x140021105  pop     r13
0x140021107  pop     r12
0x140021109  pop     rdi
0x14002110a  pop     rsi
0x14002110b  pop     rbp
0x14002110c  retn
```
