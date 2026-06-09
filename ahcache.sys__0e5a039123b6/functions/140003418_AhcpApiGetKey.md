# AhcpApiGetKey

- ea: `0x140003418`
- end: `0x14000382a`
- name: `AhcpApiGetKey`
- size: `1042`
- prototype: `__int64 __fastcall(_OWORD *, void **, unsigned __int16 *, unsigned __int16 *, HANDLE Handle)`
- caller_count: `4`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14002b850`
- `0x140045a00`
- `0x14004be30`
- `0x14004c088`

## callees

- `0x140003418`
- `0x14003e364`
- `0x14004b2b0`
- `0x14004ba84`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000356f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000356f`
- `ntoskrnl!IoFileObjectType` at `0x14000355b`
- `ntoskrnl!IoFileObjectType` at `0x1400035bd`
- `ntoskrnl!RtlInitUnicodeString` at `0x140003678`
- `ntoskrnl!RtlInitUnicodeString` at `0x140003678`
- `ntoskrnl!ObfDereferenceObject` at `0x1400035f6`
- `ntoskrnl!ObfDereferenceObject` at `0x1400037f9`
- `ntoskrnl!ObfDereferenceObject` at `0x1400035f6`
- `ntoskrnl!ObfDereferenceObject` at `0x1400037f9`
- `ntoskrnl!ProbeForRead` at `0x14000347d`
- `ntoskrnl!ProbeForRead` at `0x1400034de`
- `ntoskrnl!ProbeForRead` at `0x14000347d`
- `ntoskrnl!ProbeForRead` at `0x1400034de`
- `ntoskrnl!ExGetPreviousMode` at `0x140003538`
- `ntoskrnl!ExGetPreviousMode` at `0x140003538`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400035da`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400035da`
- `ntoskrnl!ZwClose` at `0x1400037cc`
- `ntoskrnl!ZwClose` at `0x1400037e5`
- `ntoskrnl!ZwClose` at `0x1400037cc`
- `ntoskrnl!ZwClose` at `0x1400037e5`
- `ntoskrnl!ZwDuplicateObject` at `0x140003633`
- `ntoskrnl!ZwDuplicateObject` at `0x140003633`
- `ntoskrnl!ZwOpenFile` at `0x1400036ed`
- `ntoskrnl!ZwOpenFile` at `0x1400036ed`

## string_xrefs

- `0x140003775`: `No package or path specified [%x]`

## pseudocode

```c
__int64 __fastcall AhcpApiGetKey(_OWORD *a1, void **a2, unsigned __int16 *a3, unsigned __int16 *a4, HANDLE Handle)
{
  PVOID v9; // rsi
  volatile void *v10; // rcx
  int v11; // eax
  NTSTATUS v12; // edi
  volatile void *v13; // rcx
  int v14; // eax
  HANDLE v15; // r14
  KPROCESSOR_MODE PreviousMode; // al
  NTSTATUS v17; // eax
  NTSTATUS v18; // eax
  PVOID *Object; // [rsp+20h] [rbp-B8h]
  PVOID *Objecta; // [rsp+20h] [rbp-B8h]
  PVOID v22; // [rsp+48h] [rbp-90h] BYREF
  __int128 v23; // [rsp+50h] [rbp-88h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-78h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-68h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-58h] BYREF
  void *FileHandle; // [rsp+E0h] [rbp+8h] BYREF
  void *TargetHandle; // [rsp+E8h] [rbp+10h] BYREF

  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  IoStatusBlock = 0;
  v23 = 0;
  TargetHandle = 0;
  FileHandle = 0;
  v9 = 0;
  *a1 = 0;
  *a2 = 0;
  v10 = (volatile void *)*((_QWORD *)a3 + 1);
  if ( v10 )
  {
    ProbeForRead(v10, *a3, 4u);
    v11 = AslUnicodeStringDuplicate(&v23, a3);
    v12 = v11;
    if ( v11 < 0 )
    {
      AslLogCallPrintf(1, "AhcpApiGetKey", 77, "Failed to get package alias [%x]", v11);
      goto LABEL_22;
    }
  }
  else
  {
    v13 = (volatile void *)*((_QWORD *)a4 + 1);
    if ( !v13 )
    {
      v12 = -1073741811;
      AslLogCallPrintf(1, "AhcpApiGetKey", 89, "No package or path specified [%x]", -1073741811);
      goto LABEL_22;
    }
    ProbeForRead(v13, *a4, 4u);
    v14 = AslUnicodeStringDuplicate(&v23, a4);
    v12 = v14;
    if ( v14 < 0 )
    {
      AslLogCallPrintf(1, "AhcpApiGetKey", 84, "Failed to get package alias [%x]", v14);
      goto LABEL_22;
    }
  }
  v15 = Handle;
  if ( Handle )
  {
    PreviousMode = ExGetPreviousMode();
    v22 = 0;
    v17 = ObReferenceObjectByHandle(v15, 0x80u, (POBJECT_TYPE)IoFileObjectType, PreviousMode, &v22, 0);
    v9 = v22;
    if ( v17 < 0 )
    {
      AslLogCallPrintf(1, "AhcpApiGetKey", 108, "Failed to get file object by handle [%x]", v17);
      v12 = -1073741811;
      goto LABEL_22;
    }
    v12 = ObOpenObjectByPointer(v22, 0x240u, 0, 0x80u, (POBJECT_TYPE)IoFileObjectType, 0, &FileHandle);
    if ( v12 == -1073741790 )
    {
      ObfDereferenceObject(v9);
      v9 = 0;
      FileHandle = 0;
      v18 = ZwDuplicateObject(
              (HANDLE)0xFFFFFFFFFFFFFFFFLL,
              v15,
              (HANDLE)0xFFFFFFFFFFFFFFFFLL,
              &TargetHandle,
              0,
              0x200u,
              2u);
      v12 = v18;
      if ( v18 < 0 )
      {
        LODWORD(Objecta) = v18;
        AslLogCallPrintf(1, "AhcpApiGetKey", 148, "Failed to duplicate the user mode file handle [%x]", Objecta);
        goto LABEL_22;
      }
      RtlInitUnicodeString(&DestinationString, &pszSrc);
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = TargetHandle;
      ObjectAttributes.Attributes = 576;
      ObjectAttributes.ObjectName = &DestinationString;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v12 = ZwOpenFile(&FileHandle, 0x80100080, &ObjectAttributes, &IoStatusBlock, 1u, 0x60u);
    }
    if ( v12 < 0 )
    {
      LODWORD(Object) = v12;
      AslLogCallPrintf(1, "AhcpApiGetKey", 173, "Bad file handle [%x]", Object);
      goto LABEL_22;
    }
  }
  if ( *((_QWORD *)&v23 + 1) && (_WORD)v23 )
  {
    *a2 = FileHandle;
    FileHandle = 0;
    *a1 = v23;
    v23 = 0;
    v12 = 0;
  }
  else
  {
    v12 = -1073741811;
    LODWORD(Object) = -1073741811;
    AslLogCallPrintf(1, "AhcpApiGetKey", 199, "Failed to get key [%x]", Object);
  }
LABEL_22:
  if ( FileHandle )
    ZwClose(FileHandle);
  if ( TargetHandle )
    ZwClose(TargetHandle);
  if ( v9 )
    ObfDereferenceObject(v9);
  AslAnsiStringFree(&v23);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140003418  mov     rax, rsp
0x14000341b  mov     [rax+18h], rbx
0x14000341f  push    rsi
0x140003420  push    rdi
0x140003421  push    r12
0x140003423  push    r14
0x140003425  push    r15
0x140003427  sub     rsp, 0B0h
0x14000342e  mov     rdi, r9
0x140003431  mov     r14, r8
0x140003434  mov     r15, rdx
0x140003437  mov     r12, rcx
0x14000343a  xorps   xmm0, xmm0
0x14000343d  movups  xmmword ptr [rax-58h], xmm0
0x140003441  movups  xmmword ptr [rax-48h], xmm0
0x140003445  movups  xmmword ptr [rax-38h], xmm0
0x140003449  movups  xmmword ptr [rax-78h], xmm0
0x14000344d  xorps   xmm1, xmm1
0x140003450  movups  xmmword ptr [rax-68h], xmm1
0x140003454  movups  [rsp+0D8h+var_88], xmm0
0x140003459  xor     ebx, ebx
0x14000345b  mov     [rax+10h], rbx
0x14000345f  mov     [rax+8], rbx
0x140003463  mov     esi, ebx
0x140003465  movdqu  xmmword ptr [rcx], xmm0
0x140003469  mov     [rdx], rbx
0x14000346c  mov     rcx, [r8+8]; Address
0x140003470  test    rcx, rcx
0x140003473  jz      short loc_1400034C7
0x140003475  movzx   edx, word ptr [r8]; Length
0x140003479  lea     r8d, [rbx+4]; Alignment
0x14000347d  call    cs:__imp_ProbeForRead
0x140003484  nop     dword ptr [rax+rax+00h]
0x140003489  mov     rdx, r14
0x14000348c  lea     rcx, [rsp+0D8h+var_88]
0x140003491  call    AslUnicodeStringDuplicate
0x140003496  mov     edi, eax
0x140003498  mov     [rsp+0D8h+var_98], eax
0x14000349c  test    eax, eax
0x14000349e  jns     loc_140003527
0x1400034a4  mov     dword ptr [rsp+0D8h+Object], eax
0x1400034a8  lea     r9, aFailedToGetPac; "Failed to get package alias [%x]"
0x1400034af  lea     r8d, [rbx+4Dh]
0x1400034b3  lea     rdx, aAhcpapigetkey; "AhcpApiGetKey"
0x1400034ba  lea     ecx, [rbx+1]
0x1400034bd  call    AslLogCallPrintf
0x1400034c2  jmp     loc_1400037BF
0x1400034c7  mov     rcx, [r9+8]; Address
0x1400034cb  test    rcx, rcx
0x1400034ce  jz      loc_140003768
0x1400034d4  movzx   edx, word ptr [r9]; Length
0x1400034d8  mov     r8d, 4; Alignment
0x1400034de  call    cs:__imp_ProbeForRead
0x1400034e5  nop     dword ptr [rax+rax+00h]
0x1400034ea  mov     rdx, rdi
0x1400034ed  lea     rcx, [rsp+0D8h+var_88]
0x1400034f2  call    AslUnicodeStringDuplicate
0x1400034f7  mov     edi, eax
0x1400034f9  mov     [rsp+0D8h+var_98], eax
0x1400034fd  test    eax, eax
0x1400034ff  jns     short loc_140003527
0x140003501  mov     dword ptr [rsp+0D8h+Object], eax
0x140003505  lea     r9, aFailedToGetPac; "Failed to get package alias [%x]"
0x14000350c  mov     r8d, 54h ; 'T'
0x140003512  lea     rdx, aAhcpapigetkey; "AhcpApiGetKey"
0x140003519  lea     ecx, [r8-53h]
0x14000351d  call    AslLogCallPrintf
0x140003522  jmp     loc_1400037BF
0x140003527  mov     r14, [rsp+0D8h+Handle]
0x14000352f  test    r14, r14
0x140003532  jz      loc_140003715
0x140003538  call    cs:__imp_ExGetPreviousMode
0x14000353f  nop     dword ptr [rax+rax+00h]
0x140003544  mov     [rsp+0D8h+var_90], rbx
0x140003549  mov     [rsp+0D8h+HandleInformation], rbx; HandleInformation
0x14000354e  lea     rcx, [rsp+0D8h+var_90]
0x140003553  mov     [rsp+0D8h+Object], rcx; Object
0x140003558  mov     r9b, al; AccessMode
0x14000355b  mov     r8, cs:__imp_IoFileObjectType
0x140003562  mov     r8, [r8]; ObjectType
0x140003565  mov     edi, 80h
0x14000356a  mov     edx, edi; DesiredAccess
0x14000356c  mov     rcx, r14; Handle
0x14000356f  call    cs:__imp_ObReferenceObjectByHandle
0x140003576  nop     dword ptr [rax+rax+00h]
0x14000357b  mov     rsi, [rsp+0D8h+var_90]
0x140003580  test    eax, eax
0x140003582  jns     short loc_1400035AC
0x140003584  mov     dword ptr [rsp+0D8h+Object], eax
0x140003588  lea     r9, aFailedToGetFil_0; "Failed to get file object by handle [%x"...
0x14000358f  lea     r8d, [rdi-14h]
0x140003593  lea     rdx, aAhcpapigetkey; "AhcpApiGetKey"
0x14000359a  lea     ecx, [rdi-7Fh]
0x14000359d  call    AslLogCallPrintf
0x1400035a2  mov     edi, 0C000000Dh
0x1400035a7  jmp     loc_1400037BF
0x1400035ac  lea     rax, [rsp+0D8h+FileHandle]
0x1400035b4  mov     [rsp+0D8h+var_A8], rax; Handle
0x1400035b9  mov     byte ptr [rsp+0D8h+HandleInformation], bl; AccessMode
0x1400035bd  mov     rax, cs:__imp_IoFileObjectType
0x1400035c4  mov     rdx, [rax]
0x1400035c7  mov     [rsp+0D8h+Object], rdx; ObjectType
0x1400035cc  mov     r9d, edi; DesiredAccess
0x1400035cf  xor     r8d, r8d; PassedAccessState
0x1400035d2  mov     edx, 240h; HandleAttributes
0x1400035d7  mov     rcx, rsi; Object
0x1400035da  call    cs:__imp_ObOpenObjectByPointer
0x1400035e1  nop     dword ptr [rax+rax+00h]
0x1400035e6  mov     edi, eax
0x1400035e8  cmp     eax, 0C0000022h
0x1400035ed  jnz     loc_1400036FB
0x1400035f3  mov     rcx, rsi; Object
0x1400035f6  call    cs:__imp_ObfDereferenceObject
0x1400035fd  nop     dword ptr [rax+rax+00h]
0x140003602  mov     rsi, rbx
0x140003605  mov     [rsp+0D8h+FileHandle], rbx
0x14000360d  mov     dword ptr [rsp+0D8h+var_A8], 2; Options
0x140003615  mov     dword ptr [rsp+0D8h+HandleInformation], 200h; HandleAttributes
0x14000361d  mov     dword ptr [rsp+0D8h+Object], ebx; DesiredAccess
0x140003621  lea     r9, [rsp+0D8h+TargetHandle]; TargetHandle
0x140003629  or      rcx, 0FFFFFFFFFFFFFFFFh; SourceProcessHandle
0x14000362d  mov     r8, rcx; TargetProcessHandle
0x140003630  mov     rdx, r14; SourceHandle
0x140003633  call    cs:__imp_ZwDuplicateObject
0x14000363a  nop     dword ptr [rax+rax+00h]
0x14000363f  mov     edi, eax
0x140003641  test    eax, eax
0x140003643  jns     short loc_14000366C
0x140003645  mov     dword ptr [rsp+0D8h+Object], eax
0x140003649  lea     r9, aFailedToDuplic_3; "Failed to duplicate the user mode file "...
0x140003650  mov     r8d, 94h
0x140003656  lea     rdx, aAhcpapigetkey; "AhcpApiGetKey"
0x14000365d  mov     ecx, 1
0x140003662  call    AslLogCallPrintf
0x140003667  jmp     loc_1400037BF
0x14000366c  lea     rdx, pszSrc; SourceString
0x140003673  lea     rcx, [rsp+0D8h+DestinationString]; DestinationString
0x140003678  call    cs:__imp_RtlInitUnicodeString
0x14000367f  nop     dword ptr [rax+rax+00h]
0x140003684  mov     [rsp+0D8h+ObjectAttributes.Length], 30h ; '0'
0x14000368f  mov     rax, [rsp+0D8h+TargetHandle]
0x140003697  mov     [rsp+0D8h+ObjectAttributes.RootDirectory], rax
0x14000369f  mov     [rsp+0D8h+ObjectAttributes.Attributes], 240h
0x1400036aa  lea     rax, [rsp+0D8h+DestinationString]
0x1400036af  mov     [rsp+0D8h+ObjectAttributes.ObjectName], rax
0x1400036b7  xorps   xmm0, xmm0
0x1400036ba  movdqu  xmmword ptr [rsp+0D8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400036c3  mov     dword ptr [rsp+0D8h+HandleInformation], 60h ; '`'; OpenOptions
0x1400036cb  mov     dword ptr [rsp+0D8h+Object], 1; ShareAccess
0x1400036d3  lea     r9, [rsp+0D8h+IoStatusBlock]; IoStatusBlock
0x1400036d8  lea     r8, [rsp+0D8h+ObjectAttributes]; ObjectAttributes
0x1400036e0  mov     edx, 80100080h; DesiredAccess
0x1400036e5  lea     rcx, [rsp+0D8h+FileHandle]; FileHandle
0x1400036ed  call    cs:__imp_ZwOpenFile
0x1400036f4  nop     dword ptr [rax+rax+00h]
0x1400036f9  mov     edi, eax
0x1400036fb  test    edi, edi
0x1400036fd  jns     short loc_140003715
0x1400036ff  mov     dword ptr [rsp+0D8h+Object], edi
0x140003703  lea     r9, aBadFileHandleX; "Bad file handle [%x]"
0x14000370a  mov     r8d, 0ADh
0x140003710  jmp     loc_140003656
0x140003715  cmp     qword ptr [rsp+0D8h+var_88+8], rbx
0x14000371a  jz      short loc_14000374D
0x14000371c  cmp     word ptr [rsp+0D8h+var_88], bx
0x140003721  jz      short loc_14000374D
0x140003723  mov     rax, [rsp+0D8h+FileHandle]
0x14000372b  mov     [r15], rax
0x14000372e  mov     [rsp+0D8h+FileHandle], rbx
0x140003736  movups  xmm0, [rsp+0D8h+var_88]
0x14000373b  movdqu  xmmword ptr [r12], xmm0
0x140003741  xorps   xmm0, xmm0
0x140003744  movups  [rsp+0D8h+var_88], xmm0
0x140003749  mov     edi, ebx
0x14000374b  jmp     short loc_1400037BF
0x14000374d  mov     edi, 0C000000Dh
0x140003752  mov     dword ptr [rsp+0D8h+Object], edi
0x140003756  lea     r9, aFailedToGetKey_0; "Failed to get key [%x]"
0x14000375d  mov     r8d, 0C7h
0x140003763  jmp     loc_140003656
0x140003768  mov     edi, 0C000000Dh
0x14000376d  mov     [rsp+0D8h+var_98], edi
0x140003771  mov     dword ptr [rsp+0D8h+Object], edi
0x140003775  lea     r9, aNoPackageOrPat; "No package or path specified [%x]"
0x14000377c  mov     r8d, 59h ; 'Y'
0x140003782  lea     rdx, aAhcpapigetkey; "AhcpApiGetKey"
0x140003789  lea     ecx, [r8-58h]
0x14000378d  call    AslLogCallPrintf
0x140003792  jmp     short loc_1400037BF
0x140003794  mov     edi, eax
0x140003796  mov     [rsp+0D8h+var_98], eax
0x14000379a  mov     dword ptr [rsp+0D8h+Object], eax
0x14000379e  lea     r9, aGetkeyExceptio; "GetKey exception [%x]"
0x1400037a5  mov     r8d, 5Eh ; '^'
0x1400037ab  lea     rdx, aAhcpapigetkey; "AhcpApiGetKey"
0x1400037b2  lea     ecx, [r8-5Dh]
0x1400037b6  call    AslLogCallPrintf
0x1400037bb  xor     ebx, ebx
0x1400037bd  mov     esi, ebx
0x1400037bf  mov     rcx, [rsp+0D8h+FileHandle]; Handle
0x1400037c7  test    rcx, rcx
0x1400037ca  jz      short loc_1400037D8
0x1400037cc  call    cs:__imp_ZwClose
0x1400037d3  nop     dword ptr [rax+rax+00h]
0x1400037d8  mov     rcx, [rsp+0D8h+TargetHandle]; Handle
0x1400037e0  test    rcx, rcx
0x1400037e3  jz      short loc_1400037F1
0x1400037e5  call    cs:__imp_ZwClose
0x1400037ec  nop     dword ptr [rax+rax+00h]
0x1400037f1  test    rsi, rsi
0x1400037f4  jz      short loc_140003805
0x1400037f6  mov     rcx, rsi; Object
0x1400037f9  call    cs:__imp_ObfDereferenceObject
0x140003800  nop     dword ptr [rax+rax+00h]
0x140003805  lea     rcx, [rsp+0D8h+var_88]
0x14000380a  call    AslAnsiStringFree
0x14000380f  mov     eax, edi
0x140003811  mov     rbx, [rsp+0D8h+arg_10]
0x140003819  add     rsp, 0B0h
0x140003820  pop     r15
0x140003822  pop     r14
0x140003824  pop     r12
0x140003826  pop     rdi
0x140003827  pop     rsi
0x140003828  retn
```
