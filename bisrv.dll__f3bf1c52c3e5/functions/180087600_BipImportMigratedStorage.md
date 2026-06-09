# BipImportMigratedStorage

- ea: `0x180087600`
- end: `0x180087ac3`
- name: `BipImportMigratedStorage`
- size: `1219`
- prototype: `__int64 __fastcall(PCUNICODE_STRING Source, char *, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800639b0`

## callees

- `0x180025fcc`
- `0x1800260e8`
- `0x18002b060`
- `0x180053100`
- `0x18006d5cc`
- `0x180087600`
- `0x180087acc`
- `0x180087bd8`
- `0x1800946a0`

## import_xrefs

- `ntdll!NtQueryAttributesFile` at `0x18008773c`
- `ntdll!NtQueryAttributesFile` at `0x18008773c`
- `ntdll!NtLoadKeyEx` at `0x180087858`
- `ntdll!NtLoadKeyEx` at `0x180087858`
- `ntdll!RtlAppendUnicodeToString` at `0x1800877dd`
- `ntdll!RtlAppendUnicodeToString` at `0x1800877dd`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800877fc`
- `ntdll!RtlAppendUnicodeStringToString` at `0x1800877fc`
- `ntdll!RtlFreeUnicodeString` at `0x180087a90`
- `ntdll!RtlFreeUnicodeString` at `0x180087a90`
- `ntdll!RtlStringFromGUID` at `0x1800877bb`
- `ntdll!RtlStringFromGUID` at `0x1800877bb`
- `ntdll!RtlInitUnicodeString` at `0x18008788c`
- `ntdll!RtlInitUnicodeString` at `0x1800878c3`
- `ntdll!RtlInitUnicodeString` at `0x1800879bc`
- `ntdll!RtlInitUnicodeString` at `0x18008788c`
- `ntdll!RtlInitUnicodeString` at `0x1800878c3`
- `ntdll!RtlInitUnicodeString` at `0x1800879bc`
- `ntdll!RtlFreeHeap` at `0x180087a80`
- `ntdll!RtlFreeHeap` at `0x180087a80`
- `ntdll!RtlAllocateHeap` at `0x180087772`
- `ntdll!RtlAllocateHeap` at `0x180087772`
- `ntdll!NtClose` at `0x180087a67`
- `ntdll!NtClose` at `0x180087a67`
- `RPCRT4!UuidCreate` at `0x180087793`
- `RPCRT4!UuidCreate` at `0x180087793`

## string_xrefs

- `0x1800877d1`: `\REGISTRY\A\`

## pseudocode

```c
__int64 __fastcall BipImportMigratedStorage(PCUNICODE_STRING Source, char *a2, __int64 a3)
{
  __int64 result; // rax
  __int64 v6; // r8
  NTSTATUS appended; // ebx
  int v8; // edi
  RPC_STATUS v9; // eax
  NTSTATUS v10; // eax
  int v11; // eax
  __int64 v12; // r8
  char v13; // si
  unsigned int v14; // edx
  int v15; // r8d
  int v16; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v17; // [rsp+44h] [rbp-BCh] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-B8h]
  int v19; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+58h] [rbp-A8h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  struct _UNICODE_STRING v22; // [rsp+78h] [rbp-88h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+88h] [rbp-78h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-68h] BYREF
  struct _OBJECT_ATTRIBUTES TargetKey; // [rsp+C8h] [rbp-38h] BYREF
  UUID Uuid; // [rsp+F8h] [rbp-8h] BYREF
  _FILE_BASIC_INFORMATION FileInformation; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v28[32]; // [rsp+130h] [rbp+30h] BYREF
  unsigned int *v29; // [rsp+150h] [rbp+50h]
  __int64 v30; // [rsp+158h] [rbp+58h]
  int *v31; // [rsp+160h] [rbp+60h]
  __int64 v32; // [rsp+168h] [rbp+68h]
  int *v33; // [rsp+170h] [rbp+70h]
  __int64 v34; // [rsp+178h] [rbp+78h]
  char v35; // [rsp+180h] [rbp+80h] BYREF

  v16 = 0;
  Handle = 0;
  memset(&FileInformation, 0, sizeof(FileInformation));
  v22 = 0;
  memset(&ObjectAttributes, 0, 44);
  memset(&TargetKey, 0, 44);
  Destination = 0;
  Uuid = 0;
  GuidString = 0;
  DestinationString = 0;
  if ( (unsigned int)dword_1800C3098 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800C3098, 3, a3) )
    tlgWriteTransfer_EventWriteTransfer(&dword_1800C3098, &dword_1800B2B5C, 0, 0, 2, v28);
  *a2 = 0;
  *(_QWORD *)&v22.Length = 0x8000000;
  v22.Buffer = (PWSTR)&v35;
  result = BipStorageAppendToPath(Source, L"bbimigrate\\BBI", &v22);
  if ( (int)result >= 0 )
  {
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &v22;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    if ( NtQueryAttributesFile(&ObjectAttributes, &FileInformation) < 0 )
      return 0;
    Handle = 0;
    v17 = 0;
    GuidString.Buffer = 0;
    *(_DWORD *)&Destination.Length = 0x4000000;
    Destination.Buffer = (PWSTR)RtlAllocateHeap(BipHeap, 0, 0x400u);
    if ( !Destination.Buffer )
    {
      appended = -1073741801;
      v8 = 10;
      goto LABEL_35;
    }
    v9 = UuidCreate(&Uuid);
    if ( v9 && v9 != 1824 )
    {
      appended = -1073741823;
      v8 = 20;
      goto LABEL_35;
    }
    appended = RtlStringFromGUID(&Uuid, &GuidString);
    if ( appended < 0 )
    {
      v8 = 30;
      goto LABEL_35;
    }
    appended = RtlAppendUnicodeToString(&Destination, L"\\REGISTRY\\A\\");
    if ( appended < 0 )
    {
      v8 = 40;
      goto LABEL_35;
    }
    appended = RtlAppendUnicodeStringToString(&Destination, &GuidString);
    if ( appended < 0 )
    {
      v8 = 50;
      goto LABEL_35;
    }
    TargetKey.ObjectName = &Destination;
    TargetKey.Length = 48;
    TargetKey.RootDirectory = 0;
    TargetKey.Attributes = 64;
    *(_OWORD *)&TargetKey.SecurityDescriptor = 0;
    v10 = NtLoadKeyEx(&TargetKey, &ObjectAttributes, 0x10u, 0);
    appended = v10;
    v8 = 0;
    if ( v10 == -1073741766 )
    {
      appended = 0;
      goto LABEL_35;
    }
    if ( v10 < 0 )
    {
      v8 = 60;
      goto LABEL_35;
    }
    RtlInitUnicodeString(&DestinationString, L"HiveMigrated");
    appended = BipReadRegUlong(Handle, &DestinationString);
    if ( appended >= 0 && v16 == 1 )
      goto LABEL_35;
    RtlInitUnicodeString(&DestinationString, L"Version");
    v11 = BipReadRegUlong(Handle, &DestinationString);
    appended = v11;
    if ( v11 == -1073741772 )
    {
      v12 = 1;
      v13 = 1;
    }
    else
    {
      v13 = 0;
      if ( v11 < 0 )
      {
        v8 = 70;
LABEL_35:
        if ( (unsigned int)dword_1800C3098 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800C3098, 3, v6) )
        {
          v17 = appended;
          v29 = &v17;
          v16 = (unsigned __int8)*a2;
          v30 = 4;
          v31 = &v16;
          v32 = 4;
          v33 = &v19;
          v19 = v8;
          v34 = 4;
          tlgWriteTransfer_EventWriteTransfer(&dword_1800C3098, byte_1800B2AC9, 0, 0, 5, v28);
        }
        if ( Handle )
          NtClose(Handle);
        if ( Destination.Buffer )
          RtlFreeHeap(BipHeap, 0, Destination.Buffer);
        if ( GuidString.Buffer )
          RtlFreeUnicodeString(&GuidString);
        return (unsigned int)appended;
      }
      v12 = v17;
    }
    if ( (_DWORD)v12 == 1 )
    {
      BipImportStorageV1(Handle);
    }
    else if ( (unsigned int)dword_1800C3098 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800C3098, 3, v12) )
    {
      v17 = v14;
      v29 = &v17;
      v16 = v15;
      v31 = &v16;
      v30 = 4;
      v32 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_1800C3098, &byte_1800B2B0F, 0, 0, 4, v28);
    }
    RtlInitUnicodeString(&DestinationString, L"HiveMigrated");
    appended = BipWriteRegUlong(Handle, &DestinationString);
    *a2 = v13;
    goto LABEL_35;
  }
  return result;
}

```

## disassembly

```asm
0x180087600  mov     [rsp-8+arg_10], rbx
0x180087605  mov     [rsp-8+arg_18], rsi
0x18008760a  push    rbp
0x18008760b  push    rdi
0x18008760c  push    r12
0x18008760e  push    r14
0x180087610  push    r15
0x180087612  lea     rbp, [rsp-890h]
0x18008761a  sub     rsp, 990h
0x180087621  mov     rax, cs:__security_cookie
0x180087628  xor     rax, rsp
0x18008762b  mov     [rbp+8B0h+var_30], rax
0x180087632  xorps   xmm0, xmm0
0x180087635  xor     r15d, r15d
0x180087638  xor     eax, eax
0x18008763a  mov     [rsp+9B0h+var_970], r15d
0x18008763f  xorps   xmm1, xmm1
0x180087642  mov     qword ptr [rbp+8B0h+FileInformation.FileAttributes], rax
0x180087646  mov     eax, cs:dword_1800C3098
0x18008764c  mov     r14, rdx
0x18008764f  lea     r12d, [r15+4]
0x180087653  mov     [rsp+9B0h+Handle], r15
0x180087658  mov     rbx, rcx
0x18008765b  movups  xmmword ptr [rbp+8B0h+ObjectAttributes.ObjectName], xmm0
0x18008765f  movups  xmmword ptr [rbp+8B0h+TargetKey.ObjectName], xmm0
0x180087663  movups  xmmword ptr [rbp+8B0h+FileInformation.CreationTime], xmm0
0x180087667  movups  xmmword ptr [rbp+8B0h+FileInformation.LastWriteTime], xmm0
0x18008766b  movups  xmmword ptr [rsp+9B0h+var_938.Length], xmm0
0x180087670  movups  xmmword ptr [rbp+8B0h+ObjectAttributes.Length], xmm0
0x180087674  movups  xmmword ptr [rbp+8B0h+ObjectAttributes+1Ch], xmm0
0x180087678  movups  xmmword ptr [rbp+8B0h+TargetKey.Length], xmm0
0x18008767c  movups  xmmword ptr [rbp+8B0h+TargetKey+1Ch], xmm0
0x180087680  movups  xmmword ptr [rsp+9B0h+Destination.Length], xmm0
0x180087685  movups  xmmword ptr [rbp+8B0h+Uuid.Data1], xmm1
0x180087689  movups  xmmword ptr [rbp+8B0h+GuidString.Length], xmm0
0x18008768d  movups  xmmword ptr [rsp+9B0h+DestinationString.Length], xmm1
0x180087692  cmp     eax, r12d
0x180087695  jbe     short loc_1800876D5
0x180087697  lea     edx, [r15+3]
0x18008769b  lea     rcx, dword_1800C3098
0x1800876a2  call    _tlgKeywordOn
0x1800876a7  test    al, al
0x1800876a9  jz      short loc_1800876D5
0x1800876ab  lea     rax, [rbp+8B0h+var_880]
0x1800876af  xor     r9d, r9d
0x1800876b2  mov     [rsp+9B0h+var_988], rax
0x1800876b7  lea     rdx, dword_1800B2B5C
0x1800876be  xor     r8d, r8d
0x1800876c1  mov     dword ptr [rsp+9B0h+var_990], 2
0x1800876c9  lea     rcx, dword_1800C3098
0x1800876d0  call    _tlgWriteTransfer_EventWriteTransfer
0x1800876d5  xorps   xmm0, xmm0
0x1800876d8  mov     [r14], r15b
0x1800876db  movups  xmmword ptr [rsp+9B0h+var_938.Length], xmm0
0x1800876e0  mov     eax, 800h
0x1800876e5  lea     r8, [rsp+9B0h+var_938]; Destination
0x1800876ea  mov     [rsp+9B0h+var_938.MaximumLength], ax
0x1800876ef  lea     rdx, aBbimigrateBbi; "bbimigrate\\BBI"
0x1800876f6  lea     rax, [rbp+8B0h+var_830]
0x1800876fd  mov     rcx, rbx; Source
0x180087700  mov     [rbp+8B0h+var_938.Buffer], rax
0x180087704  call    BipStorageAppendToPath
0x180087709  test    eax, eax
0x18008770b  js      loc_180087A98
0x180087711  mov     edi, 30h ; '0'
0x180087716  mov     [rbp+8B0h+ObjectAttributes.RootDirectory], r15
0x18008771a  lea     rax, [rsp+9B0h+var_938]
0x18008771f  mov     [rbp+8B0h+ObjectAttributes.Length], edi
0x180087722  xorps   xmm0, xmm0
0x180087725  mov     [rbp+8B0h+ObjectAttributes.ObjectName], rax
0x180087729  lea     rdx, [rbp+8B0h+FileInformation]; FileInformation
0x18008772d  lea     esi, [rdi+10h]
0x180087730  lea     rcx, [rbp+8B0h+ObjectAttributes]; ObjectAttributes
0x180087734  mov     [rbp+8B0h+ObjectAttributes.Attributes], esi
0x180087737  movdqu  xmmword ptr [rbp+8B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x18008773c  call    cs:__imp_NtQueryAttributesFile
0x180087742  test    eax, eax
0x180087744  jns     short loc_18008774D
0x180087746  xor     eax, eax
0x180087748  jmp     loc_180087A98
0x18008774d  mov     rcx, cs:BipHeap; HeapHandle
0x180087754  xor     edx, edx; Flags
0x180087756  mov     r8d, 400h; Size
0x18008775c  mov     [rsp+9B0h+Handle], r15
0x180087761  mov     [rsp+9B0h+var_96C], r15d
0x180087766  mov     [rbp+8B0h+GuidString.Buffer], r15
0x18008776a  mov     dword ptr [rsp+9B0h+Destination.Length], 4000000h
0x180087772  call    cs:__imp_RtlAllocateHeap
0x180087778  mov     [rsp+9B0h+Destination.Buffer], rax
0x18008777d  test    rax, rax
0x180087780  jnz     short loc_18008778F
0x180087782  mov     ebx, 0C0000017h
0x180087787  lea     edi, [rax+0Ah]
0x18008778a  jmp     loc_1800879DC
0x18008778f  lea     rcx, [rbp+8B0h+Uuid]; Uuid
0x180087793  call    cs:__imp_UuidCreate
0x180087799  test    eax, eax
0x18008779b  jz      short loc_1800877B3
0x18008779d  cmp     eax, 720h
0x1800877a2  jz      short loc_1800877B3
0x1800877a4  mov     ebx, 0C0000001h
0x1800877a9  mov     edi, 14h
0x1800877ae  jmp     loc_1800879DC
0x1800877b3  lea     rdx, [rbp+8B0h+GuidString]; GuidString
0x1800877b7  lea     rcx, [rbp+8B0h+Uuid]; Guid
0x1800877bb  call    cs:__imp_RtlStringFromGUID
0x1800877c1  mov     ebx, eax
0x1800877c3  test    eax, eax
0x1800877c5  jns     short loc_1800877D1
0x1800877c7  mov     edi, 1Eh
0x1800877cc  jmp     loc_1800879DC
0x1800877d1  lea     rdx, aRegistryA; "\\REGISTRY\\A\\"
0x1800877d8  lea     rcx, [rsp+9B0h+Destination]; Destination
0x1800877dd  call    cs:__imp_RtlAppendUnicodeToString
0x1800877e3  mov     ebx, eax
0x1800877e5  test    eax, eax
0x1800877e7  jns     short loc_1800877F3
0x1800877e9  mov     edi, 28h ; '('
0x1800877ee  jmp     loc_1800879DC
0x1800877f3  lea     rdx, [rbp+8B0h+GuidString]; Source
0x1800877f7  lea     rcx, [rsp+9B0h+Destination]; Destination
0x1800877fc  call    cs:__imp_RtlAppendUnicodeStringToString
0x180087802  mov     ebx, eax
0x180087804  test    eax, eax
0x180087806  jns     short loc_180087812
0x180087808  mov     edi, 32h ; '2'
0x18008780d  jmp     loc_1800879DC
0x180087812  mov     [rsp+9B0h+var_978], r15
0x180087817  lea     rax, [rsp+9B0h+Destination]
0x18008781c  xor     r9d, r9d; TrustClassKey
0x18008781f  mov     [rbp+8B0h+TargetKey.ObjectName], rax
0x180087823  lea     rax, [rsp+9B0h+Handle]
0x180087828  mov     [rbp+8B0h+TargetKey.Length], edi
0x18008782b  mov     [rsp+9B0h+var_980], rax
0x180087830  lea     rdx, [rbp+8B0h+ObjectAttributes]; SourceFile
0x180087834  xorps   xmm0, xmm0
0x180087837  mov     dword ptr [rsp+9B0h+var_988], 0F003Fh
0x18008783f  lea     r8d, [r9+10h]; Flags
0x180087843  mov     [rsp+9B0h+var_990], r15
0x180087848  lea     rcx, [rbp+8B0h+TargetKey]; TargetKey
0x18008784c  mov     [rbp+8B0h+TargetKey.RootDirectory], r15
0x180087850  mov     [rbp+8B0h+TargetKey.Attributes], esi
0x180087853  movdqu  xmmword ptr [rbp+8B0h+TargetKey.SecurityDescriptor], xmm0
0x180087858  call    cs:__imp_NtLoadKeyEx
0x18008785e  mov     ebx, eax
0x180087860  mov     edi, r15d
0x180087863  cmp     eax, 0C000003Ah
0x180087868  jnz     short loc_180087872
0x18008786a  mov     ebx, r15d
0x18008786d  jmp     loc_1800879DC
0x180087872  test    eax, eax
0x180087874  jns     short loc_180087880
0x180087876  mov     edi, 3Ch ; '<'
0x18008787b  jmp     loc_1800879DC
0x180087880  lea     rdx, aHivemigrated; "HiveMigrated"
0x180087887  lea     rcx, [rsp+9B0h+DestinationString]; DestinationString
0x18008788c  call    cs:__imp_RtlInitUnicodeString
0x180087892  mov     rcx, [rsp+9B0h+Handle]; KeyHandle
0x180087897  lea     r8, [rsp+9B0h+var_970]
0x18008789c  lea     rdx, [rsp+9B0h+DestinationString]; ValueName
0x1800878a1  call    BipReadRegUlong
0x1800878a6  mov     ebx, eax
0x1800878a8  test    eax, eax
0x1800878aa  js      short loc_1800878B7
0x1800878ac  cmp     [rsp+9B0h+var_970], 1
0x1800878b1  jz      loc_1800879DC
0x1800878b7  lea     rdx, aVersion; "Version"
0x1800878be  lea     rcx, [rsp+9B0h+DestinationString]; DestinationString
0x1800878c3  call    cs:__imp_RtlInitUnicodeString
0x1800878c9  mov     rcx, [rsp+9B0h+Handle]; KeyHandle
0x1800878ce  lea     r8, [rsp+9B0h+var_96C]
0x1800878d3  lea     rdx, [rsp+9B0h+DestinationString]; ValueName
0x1800878d8  call    BipReadRegUlong
0x1800878dd  mov     ebx, eax
0x1800878df  cmp     eax, 0C0000034h
0x1800878e4  jnz     short loc_1800878F1
0x1800878e6  mov     r8d, 1
0x1800878ec  mov     sil, r8b
0x1800878ef  jmp     short loc_180087907
0x1800878f1  mov     sil, r15b
0x1800878f4  test    eax, eax
0x1800878f6  jns     short loc_180087902
0x1800878f8  mov     edi, 46h ; 'F'
0x1800878fd  jmp     loc_1800879DC
0x180087902  mov     r8d, [rsp+9B0h+var_96C]
0x180087907  mov     eax, r8d
0x18008790a  sub     eax, 1
0x18008790d  jz      loc_1800879A6
0x180087913  sub     eax, 1
0x180087916  jz      loc_18008799F
0x18008791c  cmp     eax, 1
0x18008791f  jz      short loc_180087991
0x180087921  mov     eax, cs:dword_1800C3098
0x180087927  cmp     eax, r12d
0x18008792a  jbe     loc_1800879B0
0x180087930  mov     edx, 3
0x180087935  lea     rcx, dword_1800C3098
0x18008793c  call    _tlgKeywordOn
0x180087941  test    al, al
0x180087943  jz      short loc_1800879B0
0x180087945  lea     rax, [rsp+9B0h+var_96C]
0x18008794a  mov     [rsp+9B0h+var_96C], edx
0x18008794e  mov     [rbp+8B0h+var_860], rax
0x180087952  lea     rdx, byte_1800B2B0F
0x180087959  lea     rax, [rsp+9B0h+var_970]
0x18008795e  mov     [rsp+9B0h+var_970], r8d
0x180087963  mov     [rbp+8B0h+var_850], rax
0x180087967  lea     rcx, dword_1800C3098
0x18008796e  lea     rax, [rbp+8B0h+var_880]
0x180087972  mov     [rbp+8B0h+var_858], r12
0x180087976  mov     [rsp+9B0h+var_988], rax
0x18008797b  xor     r9d, r9d
0x18008797e  xor     r8d, r8d
0x180087981  mov     dword ptr [rsp+9B0h+var_990], r12d
0x180087986  mov     [rbp+8B0h+var_848], r12
0x18008798a  call    _tlgWriteTransfer_EventWriteTransfer
0x18008798f  jmp     short loc_1800879B0
0x180087991  xor     edx, edx
0x180087993  mov     rcx, [rsp+9B0h+Handle]
0x180087998  call    BipImportStorageCurrent
0x18008799d  jmp     short loc_1800879B0
0x18008799f  mov     edx, 80h
0x1800879a4  jmp     short loc_180087993
0x1800879a6  mov     rcx, [rsp+9B0h+Handle]
0x1800879ab  call    BipImportStorageV1
0x1800879b0  lea     rdx, aHivemigrated; "HiveMigrated"
0x1800879b7  lea     rcx, [rsp+9B0h+DestinationString]; DestinationString
0x1800879bc  call    cs:__imp_RtlInitUnicodeString
0x1800879c2  mov     rcx, [rsp+9B0h+Handle]; KeyHandle
0x1800879c7  lea     rdx, [rsp+9B0h+DestinationString]; ValueName
0x1800879cc  mov     r8d, 1
0x1800879d2  call    BipWriteRegUlong
0x1800879d7  mov     ebx, eax
0x1800879d9  mov     [r14], sil
0x1800879dc  mov     eax, cs:dword_1800C3098
0x1800879e2  cmp     eax, r12d
0x1800879e5  jbe     short loc_180087A5D
0x1800879e7  mov     edx, 3
0x1800879ec  lea     rcx, dword_1800C3098
0x1800879f3  call    _tlgKeywordOn
0x1800879f8  test    al, al
0x1800879fa  jz      short loc_180087A5D
0x1800879fc  lea     rax, [rsp+9B0h+var_96C]
0x180087a01  mov     [rsp+9B0h+var_96C], ebx
0x180087a05  mov     [rbp+8B0h+var_860], rax
0x180087a09  lea     rdx, byte_1800B2AC9
0x180087a10  movzx   eax, byte ptr [r14]
0x180087a14  lea     rcx, dword_1800C3098
0x180087a1b  mov     [rsp+9B0h+var_970], eax
0x180087a1f  xor     r9d, r9d
0x180087a22  lea     rax, [rsp+9B0h+var_970]
0x180087a27  mov     [rbp+8B0h+var_858], r12
0x180087a2b  mov     [rbp+8B0h+var_850], rax
0x180087a2f  xor     r8d, r8d
0x180087a32  lea     rax, [rsp+9B0h+var_960]
0x180087a37  mov     [rbp+8B0h+var_848], r12
0x180087a3b  mov     [rbp+8B0h+var_840], rax
0x180087a3f  lea     rax, [rbp+8B0h+var_880]
0x180087a43  mov     [rsp+9B0h+var_988], rax
0x180087a48  mov     dword ptr [rsp+9B0h+var_990], 5
0x180087a50  mov     [rsp+9B0h+var_960], edi
0x180087a54  mov     [rbp+8B0h+var_838], r12
0x180087a58  call    _tlgWriteTransfer_EventWriteTransfer
0x180087a5d  mov     rcx, [rsp+9B0h+Handle]; Handle
0x180087a62  test    rcx, rcx
0x180087a65  jz      short loc_180087A6D
0x180087a67  call    cs:__imp_NtClose
0x180087a6d  mov     r8, [rsp+9B0h+Destination.Buffer]; P
0x180087a72  test    r8, r8
0x180087a75  jz      short loc_180087A86
0x180087a77  mov     rcx, cs:BipHeap; HeapHandle
0x180087a7e  xor     edx, edx; Flags
0x180087a80  call    cs:__imp_RtlFreeHeap
0x180087a86  cmp     [rbp+8B0h+GuidString.Buffer], r15
0x180087a8a  jz      short loc_180087A96
0x180087a8c  lea     rcx, [rbp+8B0h+GuidString]; UnicodeString
0x180087a90  call    cs:__imp_RtlFreeUnicodeString
0x180087a96  mov     eax, ebx
0x180087a98  mov     rcx, [rbp+8B0h+var_30]
0x180087a9f  xor     rcx, rsp; StackCookie
0x180087aa2  call    __security_check_cookie
0x180087aa7  lea     r11, [rsp+9B0h+var_20]
0x180087aaf  mov     rbx, [r11+40h]
0x180087ab3  mov     rsi, [r11+48h]
0x180087ab7  mov     rsp, r11
0x180087aba  pop     r15
0x180087abc  pop     r14
0x180087abe  pop     r12
0x180087ac0  pop     rdi
0x180087ac1  pop     rbp
0x180087ac2  retn
```
