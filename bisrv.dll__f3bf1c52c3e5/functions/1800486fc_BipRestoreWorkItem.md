# BipRestoreWorkItem

- ea: `0x1800486fc`
- end: `0x180048eda`
- name: `BipRestoreWorkItem`
- size: `2014`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800482ac`

## callees

- `0x180005670`
- `0x180009100`
- `0x180010c5c`
- `0x180011e7c`
- `0x1800260e8`
- `0x1800263b8`
- `0x180026f8c`
- `0x180030a80`
- `0x180030f24`
- `0x180033898`
- `0x18003b18c`
- `0x1800486fc`
- `0x18004c4cc`
- `0x180053100`
- `0x18005df20`
- `0x18006d364`
- `0x18007fdf8`
- `0x180094662`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ntdll!NtOpenKey` at `0x18004884f`
- `ntdll!NtOpenKey` at `0x18004884f`
- `ntdll!RtlFreeUnicodeString` at `0x180048a13`
- `ntdll!RtlFreeUnicodeString` at `0x180048a3f`
- `ntdll!RtlFreeUnicodeString` at `0x180048e9b`
- `ntdll!RtlFreeUnicodeString` at `0x180048ea5`
- `ntdll!RtlFreeUnicodeString` at `0x180048eaf`
- `ntdll!RtlFreeUnicodeString` at `0x180048a13`
- `ntdll!RtlFreeUnicodeString` at `0x180048a3f`
- `ntdll!RtlFreeUnicodeString` at `0x180048e9b`
- `ntdll!RtlFreeUnicodeString` at `0x180048ea5`
- `ntdll!RtlFreeUnicodeString` at `0x180048eaf`
- `ntdll!RtlInitUnicodeString` at `0x1800487f3`
- `ntdll!RtlInitUnicodeString` at `0x1800487ff`
- `ntdll!RtlInitUnicodeString` at `0x18004880b`
- `ntdll!RtlInitUnicodeString` at `0x180048870`
- `ntdll!RtlInitUnicodeString` at `0x1800488a2`
- `ntdll!RtlInitUnicodeString` at `0x180048900`
- `ntdll!RtlInitUnicodeString` at `0x180048932`
- `ntdll!RtlInitUnicodeString` at `0x18004897c`
- `ntdll!RtlInitUnicodeString` at `0x1800489d5`
- `ntdll!RtlInitUnicodeString` at `0x180048a71`
- `ntdll!RtlInitUnicodeString` at `0x180048aba`
- `ntdll!RtlInitUnicodeString` at `0x180048b2b`
- `ntdll!RtlInitUnicodeString` at `0x180048bbb`
- `ntdll!RtlInitUnicodeString` at `0x180048c73`
- `ntdll!RtlInitUnicodeString` at `0x180048d0d`
- `ntdll!RtlInitUnicodeString` at `0x1800487f3`
- `ntdll!RtlInitUnicodeString` at `0x1800487ff`
- `ntdll!RtlInitUnicodeString` at `0x18004880b`
- `ntdll!RtlInitUnicodeString` at `0x180048870`
- `ntdll!RtlInitUnicodeString` at `0x1800488a2`
- `ntdll!RtlInitUnicodeString` at `0x180048900`
- `ntdll!RtlInitUnicodeString` at `0x180048932`
- `ntdll!RtlInitUnicodeString` at `0x18004897c`
- `ntdll!RtlInitUnicodeString` at `0x1800489d5`
- `ntdll!RtlInitUnicodeString` at `0x180048a71`
- `ntdll!RtlInitUnicodeString` at `0x180048aba`
- `ntdll!RtlInitUnicodeString` at `0x180048b2b`
- `ntdll!RtlInitUnicodeString` at `0x180048bbb`
- `ntdll!RtlInitUnicodeString` at `0x180048c73`
- `ntdll!RtlInitUnicodeString` at `0x180048d0d`
- `ntdll!RtlFreeHeap` at `0x180048b67`
- `ntdll!RtlFreeHeap` at `0x180048e7a`
- `ntdll!RtlFreeHeap` at `0x180048e91`
- `ntdll!RtlFreeHeap` at `0x180048b67`
- `ntdll!RtlFreeHeap` at `0x180048e7a`
- `ntdll!RtlFreeHeap` at `0x180048e91`
- `ntdll!RtlAllocateHeap` at `0x180048b08`
- `ntdll!RtlAllocateHeap` at `0x180048b08`
- `ntdll!NtClose` at `0x180048e63`
- `ntdll!NtClose` at `0x180048e63`

## string_xrefs

- `0x180048d02`: `TaskEntryPoint`
- `0x180048bb0`: `TaskEntryPointId`

## pseudocode

```c
__int64 __fastcall BipRestoreWorkItem(void *a1, struct _GUID *a2, struct _UNICODE_STRING *a3, int a4)
{
  struct _BI_CONDITIONAL_EVENT_INFORMATION *v4; // r15
  int v8; // edi
  __int64 v10; // r8
  unsigned int v11; // r12d
  __int64 v12; // r8
  __int64 v13; // r9
  PVOID Heap; // r14
  int v15; // ebx
  __int64 v16; // r8
  int v17; // eax
  int v18; // eax
  int v19; // eax
  struct _UNICODE_STRING *v20; // rdx
  unsigned int v21; // esi
  int v22; // r12d
  __int64 v23; // rdx
  __int64 v24; // rcx
  int v25; // eax
  int v26; // edi
  unsigned int v27; // esi
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v32; // [rsp+88h] [rbp-A8h]
  size_t v33; // [rsp+A0h] [rbp-90h]
  unsigned int v34; // [rsp+B0h] [rbp-80h]
  _DWORD KeyHandle[3]; // [rsp+B4h] [rbp-7Ch] BYREF
  unsigned int v36; // [rsp+C0h] [rbp-70h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+C8h] [rbp-68h] BYREF
  int v38; // [rsp+D8h] [rbp-58h] BYREF
  unsigned int v39; // [rsp+DCh] [rbp-54h]
  int v40; // [rsp+E0h] [rbp-50h] BYREF
  __int64 p_Guid; // [rsp+E8h] [rbp-48h] BYREF
  int v42[2]; // [rsp+F0h] [rbp-40h] BYREF
  unsigned int v43; // [rsp+F8h] [rbp-38h]
  struct _UNICODE_STRING UnicodeString; // [rsp+100h] [rbp-30h] BYREF
  struct _UNICODE_STRING v45; // [rsp+110h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+120h] [rbp-10h] BYREF
  struct _UNICODE_STRING v47; // [rsp+130h] [rbp+0h] BYREF
  GUID Buf1; // [rsp+140h] [rbp+10h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+150h] [rbp+20h] BYREF
  __int64 v50; // [rsp+180h] [rbp+50h] BYREF
  GUID Guid; // [rsp+188h] [rbp+58h] BYREF
  GUID v52; // [rsp+1A0h] [rbp+70h] BYREF
  _BYTE v53[144]; // [rsp+1B0h] [rbp+80h] BYREF

  v4 = 0;
  v43 = 0;
  v39 = 0;
  v40 = 0;
  v8 = 130;
  DestinationString = 0;
  v47 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  UnicodeString = 0;
  memset_0(v53, 0, 0x82u);
  v11 = a4 | 1;
  memset(KeyHandle, 0, sizeof(KeyHandle));
  v50 = 0;
  v34 = v11;
  v45 = 0;
  v52 = 0;
  Guid = 0;
  ValueName = 0;
  if ( (unsigned int)dword_1800C3098 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800C3098, 2, v10) )
  {
    *(_QWORD *)v42 = a2;
    v36 = v11;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      (__int64)&dword_1800C3098,
      (unsigned __int8 *)&word_1800B518E,
      v12,
      v13,
      (__int64)&v36,
      (__int64 *)v42);
  }
  RtlInitUnicodeString(&DestinationString, 0);
  RtlInitUnicodeString(&v47, 0);
  RtlInitUnicodeString(&v45, 0);
  v38 = 0;
  Heap = 0;
  *(_QWORD *)&KeyHandle[1] = 0;
  p_Guid = 0;
  v36 = 0;
  ObjectAttributes.Length = 48;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.RootDirectory = a1;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = a3;
  v15 = NtOpenKey((PHANDLE)&KeyHandle[1], 0xF003Fu, &ObjectAttributes);
  if ( v15 >= 0 )
  {
    RtlInitUnicodeString(&ValueName, L"ActivationType");
    v15 = BipReadRegUlong(*(HANDLE *)&KeyHandle[1], &ValueName);
    if ( v15 < 0 )
    {
      v8 = 20;
      goto LABEL_64;
    }
    RtlInitUnicodeString(&ValueName, L"Conditions");
    v17 = BipReadRegMultiSz(*(HANDLE *)&KeyHandle[1], &ValueName, &DestinationString);
    v15 = v17;
    if ( v17 < 0 )
    {
      if ( v17 != -1073741772 )
      {
        v8 = 40;
        goto LABEL_64;
      }
    }
    else
    {
      v18 = BipParseConditionString(&DestinationString.Length, (int *)&v36, (PVOID *)&p_Guid);
      v4 = (struct _BI_CONDITIONAL_EVENT_INFORMATION *)p_Guid;
      v15 = v18;
      if ( v18 < 0 )
      {
        v8 = 30;
        goto LABEL_64;
      }
    }
    RtlInitUnicodeString(&ValueName, L"Flags");
    v15 = BipReadRegUlong(*(HANDLE *)&KeyHandle[1], &ValueName);
    if ( v15 < 0 )
    {
      v8 = 50;
      goto LABEL_64;
    }
    RtlInitUnicodeString(&ValueName, L"Name");
    v19 = BipReadRegUnicodeString(*(HANDLE *)&KeyHandle[1], &ValueName, &v47);
    v16 = 3221225524LL;
    v20 = &v47;
    v15 = 0;
    if ( v19 == -1073741772 )
      v20 = 0;
    else
      v15 = v19;
    p_Guid = (__int64)v20;
    if ( v15 < 0 )
    {
      v8 = 60;
      goto LABEL_64;
    }
    RtlInitUnicodeString(&ValueName, L"TriggerEvent");
    v15 = BipReadRegGuid(*(HANDLE *)&KeyHandle[1], &ValueName, &Guid);
    if ( v15 < 0 )
    {
      v8 = 70;
      goto LABEL_64;
    }
    *(_QWORD *)v42 = 0;
    v21 = v43;
    if ( (unsigned __int8)BipUtilActTypeIsDebugSupported(v43) )
    {
      memset_0(v53, 0, 0x82u);
      RtlInitUnicodeString(&ValueName, L"PackageRelativeAppName");
      v15 = BipReadRegUnicodeString(*(HANDLE *)&KeyHandle[1], &ValueName, &UnicodeString);
      if ( v15 < 0 )
      {
        v8 = 80;
        goto LABEL_64;
      }
      if ( UnicodeString.Length > 0x80u )
      {
        v15 = -1073741789;
        RtlFreeUnicodeString(&UnicodeString);
        v8 = 90;
        goto LABEL_64;
      }
      if ( UnicodeString.Length )
      {
        memcpy_0(v53, UnicodeString.Buffer, UnicodeString.Length);
        RtlFreeUnicodeString(&UnicodeString);
        *(_QWORD *)v42 = v53;
      }
    }
    if ( !(unsigned __int8)BipUtilActTypeIsResourceTimerSupported(v21)
      || (unsigned __int8)BipUtilActTypeIsHostedInWinMainApp(v21) )
    {
      v22 = 4;
    }
    else
    {
      RtlInitUnicodeString(&ValueName, L"PsmActivationType");
      v15 = BipReadRegUlong(*(HANDLE *)&KeyHandle[1], &ValueName);
      if ( v15 < 0 )
      {
        v8 = 100;
        goto LABEL_64;
      }
      v22 = KeyHandle[0];
    }
    if ( (unsigned __int8)BipUtilActTypeIsDebugSupported(v21) )
    {
      RtlInitUnicodeString(&ValueName, L"PackageFlags");
      v15 = BipReadRegUlong(*(HANDLE *)&KeyHandle[1], &ValueName);
      if ( v15 < 0 )
      {
        v8 = 110;
LABEL_38:
        v11 = v34;
        goto LABEL_64;
      }
    }
    if ( (unsigned __int8)BipUtilActTypeIsDebugSupported(v21) )
    {
      KeyHandle[0] = 0x2000;
      Heap = RtlAllocateHeap(BipHeap, 0, 0x2000u);
      if ( !Heap )
      {
        v15 = -1073741801;
        v8 = 120;
        goto LABEL_38;
      }
      RtlInitUnicodeString(&ValueName, L"ExtendedRegistrationData");
      memset_0(Heap, 0, 0x2000u);
      v25 = BipReadRegBinary(*(HANDLE *)&KeyHandle[1], &ValueName, Heap);
      v15 = v25;
      if ( v25 == -1073741772 )
      {
        RtlFreeHeap(BipHeap, 0, Heap);
        Heap = 0;
        v26 = 0;
      }
      else
      {
        if ( v25 < 0 )
          goto LABEL_38;
        v26 = KeyHandle[0];
      }
    }
    else
    {
      v26 = v38;
    }
    if ( v21 )
    {
      v27 = v21 - 1;
      if ( v27 )
      {
        if ( v27 != 1 )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs(v24, v23, v16);
          v15 = -1073741811;
          v8 = 200;
          goto LABEL_38;
        }
        RtlInitUnicodeString(&ValueName, L"TaskEntryPointId");
        v11 = v34;
        v15 = BipReadRegGuid(*(HANDLE *)&KeyHandle[1], &ValueName, &v52);
        if ( v15 < 0 )
        {
          v8 = 180;
          goto LABEL_64;
        }
        Buf1 = v52;
        v15 = BiSrvWorkItemAssociateClsid(
                a2,
                0,
                *(_QWORD *)v42,
                0,
                v34,
                v39,
                a2,
                &Buf1,
                &Guid,
                v4,
                0,
                v36,
                p_Guid,
                Heap,
                v26,
                0);
        if ( v15 < 0 )
        {
          v8 = 190;
          goto LABEL_64;
        }
      }
      else
      {
        v38 = 8;
        RtlInitUnicodeString(&ValueName, L"StateName");
        v11 = v34;
        v15 = BipReadRegBinary(*(HANDLE *)&KeyHandle[1], &ValueName, &v50);
        if ( v15 < 0 )
        {
          v8 = 160;
          goto LABEL_64;
        }
        v15 = BiSrvAssociateActivationProxy(a2, &v50, 0, v34, v39, a2, &v50, 0, &Guid, v4, v36, p_Guid);
        if ( v15 < 0 )
        {
          v8 = 170;
          goto LABEL_64;
        }
      }
    }
    else
    {
      RtlInitUnicodeString(&ValueName, L"TaskEntryPoint");
      v15 = BipReadRegUnicodeString(*(HANDLE *)&KeyHandle[1], &ValueName, &v45);
      if ( v15 < 0 )
      {
        v8 = 140;
        goto LABEL_38;
      }
      LODWORD(v33) = v26;
      LODWORD(v32) = v22;
      v11 = v34;
      Buf1 = GUID_NULL;
      v15 = BiSrvAssociateApplicationEntryPoint(
              a2,
              0,
              *(const WCHAR **)v42,
              0,
              &Buf1,
              v34,
              v39,
              a2,
              v45.Buffer,
              v45.Length,
              0,
              0,
              &Guid,
              v4,
              0,
              v36,
              (const UNICODE_STRING *)p_Guid,
              v32,
              v40,
              (__int64)Heap,
              v33,
              0);
      if ( v15 < 0 )
      {
        v8 = 150;
        goto LABEL_64;
      }
    }
    v15 = 0;
    v8 = 0;
    goto LABEL_64;
  }
  v8 = 10;
LABEL_64:
  if ( (unsigned int)dword_1800C3098 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800C3098, 2, v16) )
  {
    v38 = v8;
    p_Guid = (__int64)&Guid;
    v40 = v15;
    KeyHandle[0] = v11;
    *(_QWORD *)v42 = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v28,
      (unsigned __int8 *)word_1800B4F6A,
      v29,
      v30,
      &p_Guid,
      (__int64 *)v42,
      (__int64)KeyHandle,
      (__int64)&v40,
      (__int64)&v38);
  }
  if ( *(_QWORD *)&KeyHandle[1] )
    NtClose(*(HANDLE *)&KeyHandle[1]);
  if ( v4 )
    RtlFreeHeap(BipHeap, 0, v4);
  if ( Heap )
    RtlFreeHeap(BipHeap, 0, Heap);
  RtlFreeUnicodeString(&DestinationString);
  RtlFreeUnicodeString(&v47);
  RtlFreeUnicodeString(&v45);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x1800486fc  push    rbp
0x1800486fe  push    rbx
0x1800486ff  push    rsi
0x180048700  push    rdi
0x180048701  push    r12
0x180048703  push    r13
0x180048705  push    r14
0x180048707  push    r15
0x180048709  lea     rbp, [rsp-128h]
0x180048711  sub     rsp, 258h
0x180048718  mov     rax, cs:__security_cookie
0x18004871f  xor     rax, rsp
0x180048722  mov     [rbp+160h+var_50], rax
0x180048729  xorps   xmm0, xmm0
0x18004872c  xor     r15d, r15d
0x18004872f  mov     rsi, r8
0x180048732  mov     [rbp+160h+var_198], r15d
0x180048736  mov     r13, rdx
0x180048739  mov     [rbp+160h+var_1B4], r15d
0x18004873d  mov     rbx, rcx
0x180048740  mov     [rbp+160h+var_1B0], r15d
0x180048744  xorps   xmm1, xmm1
0x180048747  lea     rcx, [rbp+160h+var_E0]; void *
0x18004874e  mov     edi, 82h
0x180048753  xor     edx, edx; Val
0x180048755  mov     r8d, edi; Size
0x180048758  mov     r12d, r9d
0x18004875b  movups  xmmword ptr [rbp+160h+DestinationString.Length], xmm0
0x18004875f  movups  xmmword ptr [rbp+160h+var_160.Length], xmm1
0x180048763  movups  xmmword ptr [rbp+160h+ObjectAttributes.Length], xmm0
0x180048767  movups  xmmword ptr [rbp+160h+ObjectAttributes.ObjectName], xmm0
0x18004876b  movups  xmmword ptr [rbp+160h+ObjectAttributes.SecurityDescriptor], xmm0
0x18004876f  movups  xmmword ptr [rbp+160h+UnicodeString.Length], xmm0
0x180048773  call    memset_0
0x180048778  mov     eax, cs:dword_1800C3098
0x18004877e  or      r12d, 1
0x180048782  mov     dword ptr [rbp+160h+KeyHandle], r15d
0x180048786  xorps   xmm0, xmm0
0x180048789  mov     [rbp+160h+var_110], r15
0x18004878d  xorps   xmm1, xmm1
0x180048790  mov     qword ptr [rbp+160h+KeyHandle+4], r15
0x180048794  mov     [rbp+160h+var_1E0], r12d
0x180048798  movups  xmmword ptr [rbp+160h+var_180.Length], xmm0
0x18004879c  movups  xmmword ptr [rbp+160h+var_F0.Data1], xmm1
0x1800487a0  movups  xmmword ptr [rbp+160h+Guid.Data1], xmm0
0x1800487a4  movups  xmmword ptr [rbp+160h+ValueName.Length], xmm1
0x1800487a8  cmp     eax, 5
0x1800487ab  jbe     short loc_1800487ED
0x1800487ad  lea     edx, [rdi-80h]
0x1800487b0  lea     rcx, dword_1800C3098
0x1800487b7  call    _tlgKeywordOn
0x1800487bc  test    al, al
0x1800487be  jz      short loc_1800487ED
0x1800487c0  lea     rax, [rbp+160h+var_1A0]
0x1800487c4  mov     qword ptr [rbp+160h+var_1A0], r13
0x1800487c8  mov     qword ptr [rsp+290h+var_268], rax
0x1800487cd  lea     rdx, word_1800B518E
0x1800487d4  lea     rax, [rbp+160h+var_1D0]
0x1800487d8  mov     [rbp+160h+var_1D0], r12d
0x1800487dc  lea     rcx, dword_1800C3098
0x1800487e3  mov     [rsp+290h+Buf1], rax
0x1800487e8  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x1800487ed  xor     edx, edx; SourceString
0x1800487ef  lea     rcx, [rbp+160h+DestinationString]; DestinationString
0x1800487f3  call    cs:__imp_RtlInitUnicodeString
0x1800487f9  xor     edx, edx; SourceString
0x1800487fb  lea     rcx, [rbp+160h+var_160]; DestinationString
0x1800487ff  call    cs:__imp_RtlInitUnicodeString
0x180048805  xor     edx, edx; SourceString
0x180048807  lea     rcx, [rbp+160h+var_180]; DestinationString
0x18004880b  call    cs:__imp_RtlInitUnicodeString
0x180048811  xorps   xmm0, xmm0
0x180048814  mov     [rbp+160h+var_1B8], r15d
0x180048818  mov     r14, r15
0x18004881b  mov     qword ptr [rbp+160h+KeyHandle+4], r15
0x18004881f  lea     r8, [rbp+160h+ObjectAttributes]; ObjectAttributes
0x180048823  mov     [rbp+160h+var_1A8], r15
0x180048827  mov     edx, 0F003Fh; DesiredAccess
0x18004882c  mov     [rbp+160h+var_1D0], r14d
0x180048830  lea     rcx, [rbp+160h+KeyHandle+4]; KeyHandle
0x180048834  mov     [rbp+160h+ObjectAttributes.Length], 30h ; '0'
0x18004883b  movdqu  xmmword ptr [rbp+160h+ObjectAttributes.SecurityDescriptor], xmm0
0x180048840  mov     [rbp+160h+ObjectAttributes.RootDirectory], rbx
0x180048844  mov     [rbp+160h+ObjectAttributes.Attributes], 40h ; '@'
0x18004884b  mov     [rbp+160h+ObjectAttributes.ObjectName], rsi
0x18004884f  call    cs:__imp_NtOpenKey
0x180048855  xor     esi, esi
0x180048857  mov     ebx, eax
0x180048859  test    eax, eax
0x18004885b  jns     short loc_180048865
0x18004885d  lea     edi, [rsi+0Ah]
0x180048860  jmp     loc_180048DEB
0x180048865  lea     rdx, aActivationtype; "ActivationType"
0x18004886c  lea     rcx, [rbp+160h+ValueName]; DestinationString
0x180048870  call    cs:__imp_RtlInitUnicodeString
0x180048876  mov     rcx, qword ptr [rbp+160h+KeyHandle+4]; KeyHandle
0x18004887a  lea     r8, [rbp+160h+var_198]
0x18004887e  lea     rdx, [rbp+160h+ValueName]; ValueName
0x180048882  call    BipReadRegUlong
0x180048887  mov     ebx, eax
0x180048889  test    eax, eax
0x18004888b  jns     short loc_180048897
0x18004888d  mov     edi, 14h
0x180048892  jmp     loc_180048DEB
0x180048897  lea     rdx, aConditions; "Conditions"
0x18004889e  lea     rcx, [rbp+160h+ValueName]; DestinationString
0x1800488a2  call    cs:__imp_RtlInitUnicodeString
0x1800488a8  mov     rcx, qword ptr [rbp+160h+KeyHandle+4]; KeyHandle
0x1800488ac  lea     r8, [rbp+160h+DestinationString]; DestinationString
0x1800488b0  lea     rdx, [rbp+160h+ValueName]; ValueName
0x1800488b4  call    BipReadRegMultiSz
0x1800488b9  mov     ebx, eax
0x1800488bb  test    eax, eax
0x1800488bd  js      short loc_1800488E4
0x1800488bf  lea     r8, [rbp+160h+var_1A8]
0x1800488c3  lea     rdx, [rbp+160h+var_1D0]
0x1800488c7  lea     rcx, [rbp+160h+DestinationString]
0x1800488cb  call    BipParseConditionString
0x1800488d0  mov     r15, [rbp+160h+var_1A8]
0x1800488d4  mov     ebx, eax
0x1800488d6  test    eax, eax
0x1800488d8  jns     short loc_1800488F5
0x1800488da  mov     edi, 1Eh
0x1800488df  jmp     loc_180048DEB
0x1800488e4  cmp     eax, 0C0000034h
0x1800488e9  jz      short loc_1800488F5
0x1800488eb  mov     edi, 28h ; '('
0x1800488f0  jmp     loc_180048DEB
0x1800488f5  lea     rdx, aFlags; "Flags"
0x1800488fc  lea     rcx, [rbp+160h+ValueName]; DestinationString
0x180048900  call    cs:__imp_RtlInitUnicodeString
0x180048906  mov     rcx, qword ptr [rbp+160h+KeyHandle+4]; KeyHandle
0x18004890a  lea     r8, [rbp+160h+var_1B4]
0x18004890e  lea     rdx, [rbp+160h+ValueName]; ValueName
0x180048912  call    BipReadRegUlong
0x180048917  mov     ebx, eax
0x180048919  test    eax, eax
0x18004891b  jns     short loc_180048927
0x18004891d  mov     edi, 32h ; '2'
0x180048922  jmp     loc_180048DEB
0x180048927  lea     rdx, aName; "Name"
0x18004892e  lea     rcx, [rbp+160h+ValueName]; DestinationString
0x180048932  call    cs:__imp_RtlInitUnicodeString
0x180048938  mov     rcx, qword ptr [rbp+160h+KeyHandle+4]; KeyHandle
0x18004893c  lea     r8, [rbp+160h+var_160]; DestinationString
0x180048940  lea     rdx, [rbp+160h+ValueName]; ValueName
0x180048944  call    BipReadRegUnicodeString
0x180048949  mov     r8d, 0C0000034h
0x18004894f  lea     rdx, [rbp+160h+var_160]
0x180048953  cmp     eax, r8d
0x180048956  mov     ebx, esi
0x180048958  cmovz   rdx, rsi
0x18004895c  cmovnz  ebx, eax
0x18004895f  mov     [rbp+160h+var_1A8], rdx
0x180048963  test    ebx, ebx
0x180048965  jns     short loc_180048971
0x180048967  mov     edi, 3Ch ; '<'
0x18004896c  jmp     loc_180048DEB
0x180048971  lea     rdx, aTriggerevent; "TriggerEvent"
0x180048978  lea     rcx, [rbp+160h+ValueName]; DestinationString
0x18004897c  call    cs:__imp_RtlInitUnicodeString
0x180048982  mov     rcx, qword ptr [rbp+160h+KeyHandle+4]; KeyHandle
0x180048986  lea     r8, [rbp+160h+Guid]; Guid
0x18004898a  lea     rdx, [rbp+160h+ValueName]; ValueName
0x18004898e  call    BipReadRegGuid
0x180048993  mov     ebx, eax
0x180048995  test    eax, eax
0x180048997  jns     short loc_1800489A3
0x180048999  mov     edi, 46h ; 'F'
0x18004899e  jmp     loc_180048DEB
0x1800489a3  mov     qword ptr [rbp+160h+var_1A0], rsi
0x1800489a7  mov     esi, [rbp+160h+var_198]
0x1800489aa  mov     ecx, esi
0x1800489ac  call    BipUtilActTypeIsDebugSupported
0x1800489b1  xor     edx, edx; Val
0x1800489b3  test    al, al
0x1800489b5  jz      loc_180048A50
0x1800489bb  mov     r8, rdi; Size
0x1800489be  lea     rcx, [rbp+160h+var_E0]; void *
0x1800489c5  call    memset_0
0x1800489ca  lea     rdx, aPackagerelativ_0; "PackageRelativeAppName"
0x1800489d1  lea     rcx, [rbp+160h+ValueName]; DestinationString
0x1800489d5  call    cs:__imp_RtlInitUnicodeString
0x1800489db  mov     rcx, qword ptr [rbp+160h+KeyHandle+4]; KeyHandle
0x1800489df  lea     r8, [rbp+160h+UnicodeString]; DestinationString
0x1800489e3  lea     rdx, [rbp+160h+ValueName]; ValueName
0x1800489e7  call    BipReadRegUnicodeString
0x1800489ec  mov     ebx, eax
0x1800489ee  test    eax, eax
0x1800489f0  jns     short loc_1800489FC
0x1800489f2  mov     edi, 50h ; 'P'
0x1800489f7  jmp     loc_180048DEB
0x1800489fc  movzx   eax, [rbp+160h+UnicodeString.Length]
0x180048a00  mov     ecx, 80h
0x180048a05  cmp     ax, cx
0x180048a08  jbe     short loc_180048A23
0x180048a0a  lea     rcx, [rbp+160h+UnicodeString]; UnicodeString
0x180048a0e  mov     ebx, 0C0000023h
0x180048a13  call    cs:__imp_RtlFreeUnicodeString
0x180048a19  mov     edi, 5Ah ; 'Z'
0x180048a1e  jmp     loc_180048DEB
0x180048a23  test    ax, ax
0x180048a26  jz      short loc_180048A50
0x180048a28  mov     rdx, [rbp+160h+UnicodeString.Buffer]; Src
0x180048a2c  lea     rcx, [rbp+160h+var_E0]; void *
0x180048a33  mov     r8, rax; Size
0x180048a36  call    memcpy_0
0x180048a3b  lea     rcx, [rbp+160h+UnicodeString]; UnicodeString
0x180048a3f  call    cs:__imp_RtlFreeUnicodeString
0x180048a45  lea     rax, [rbp+160h+var_E0]
0x180048a4c  mov     qword ptr [rbp+160h+var_1A0], rax
0x180048a50  mov     ecx, esi
0x180048a52  call    BipUtilActTypeIsResourceTimerSupported
0x180048a57  test    al, al
0x180048a59  jz      short loc_180048A9E
0x180048a5b  mov     ecx, esi
0x180048a5d  call    BipUtilActTypeIsHostedInWinMainApp
0x180048a62  test    al, al
0x180048a64  jnz     short loc_180048A9E
0x180048a66  lea     rdx, aPsmactivationt; "PsmActivationType"
0x180048a6d  lea     rcx, [rbp+160h+ValueName]; DestinationString
0x180048a71  call    cs:__imp_RtlInitUnicodeString
0x180048a77  mov     rcx, qword ptr [rbp+160h+KeyHandle+4]; KeyHandle
0x180048a7b  lea     r8, [rbp+160h+KeyHandle]
0x180048a7f  lea     rdx, [rbp+160h+ValueName]; ValueName
0x180048a83  call    BipReadRegUlong
0x180048a88  mov     ebx, eax
0x180048a8a  test    eax, eax
0x180048a8c  jns     short loc_180048A98
0x180048a8e  mov     edi, 64h ; 'd'
0x180048a93  jmp     loc_180048DEB
0x180048a98  mov     r12d, dword ptr [rbp+160h+KeyHandle]
0x180048a9c  jmp     short loc_180048AA4
0x180048a9e  mov     r12d, 4
0x180048aa4  mov     ecx, esi
0x180048aa6  call    BipUtilActTypeIsDebugSupported
0x180048aab  test    al, al
0x180048aad  jz      short loc_180048AE5
0x180048aaf  lea     rdx, aPackageflags; "PackageFlags"
0x180048ab6  lea     rcx, [rbp+160h+ValueName]; DestinationString
0x180048aba  call    cs:__imp_RtlInitUnicodeString
0x180048ac0  mov     rcx, qword ptr [rbp+160h+KeyHandle+4]; KeyHandle
0x180048ac4  lea     r8, [rbp+160h+var_1B0]
0x180048ac8  lea     rdx, [rbp+160h+ValueName]; ValueName
0x180048acc  call    BipReadRegUlong
0x180048ad1  mov     ebx, eax
0x180048ad3  test    eax, eax
0x180048ad5  jns     short loc_180048AE5
0x180048ad7  mov     edi, 6Eh ; 'n'
0x180048adc  mov     r12d, [rbp+160h+var_1E0]
0x180048ae0  jmp     loc_180048DEB
0x180048ae5  mov     ecx, esi
0x180048ae7  call    BipUtilActTypeIsDebugSupported
0x180048aec  test    al, al
0x180048aee  jz      loc_180048B83
0x180048af4  mov     rcx, cs:BipHeap; HeapHandle
0x180048afb  mov     ebx, 2000h
0x180048b00  mov     r8d, ebx; Size
0x180048b03  mov     dword ptr [rbp+160h+KeyHandle], ebx
0x180048b06  xor     edx, edx; Flags
0x180048b08  call    cs:__imp_RtlAllocateHeap
0x180048b0e  mov     r14, rax
0x180048b11  test    rax, rax
0x180048b14  jnz     short loc_180048B20
0x180048b16  mov     ebx, 0C0000017h
0x180048b1b  lea     edi, [rax+78h]
0x180048b1e  jmp     short loc_180048ADC
0x180048b20  lea     rdx, aExtendedregist; "ExtendedRegistrationData"
0x180048b27  lea     rcx, [rbp+160h+ValueName]; DestinationString
0x180048b2b  call    cs:__imp_RtlInitUnicodeString
0x180048b31  mov     r8, rbx; Size
0x180048b34  xor     edx, edx; Val
0x180048b36  mov     rcx, r14; void *
0x180048b39  call    memset_0
0x180048b3e  mov     rcx, qword ptr [rbp+160h+KeyHandle+4]; KeyHandle
0x180048b42  lea     r9, [rbp+160h+KeyHandle]
0x180048b46  mov     r8, r14; void *
0x180048b49  lea     rdx, [rbp+160h+ValueName]; ValueName
0x180048b4d  call    BipReadRegBinary
0x180048b52  mov     ebx, eax
0x180048b54  cmp     eax, 0C0000034h
0x180048b59  jnz     short loc_180048B76
0x180048b5b  mov     rcx, cs:BipHeap; HeapHandle
0x180048b62  mov     r8, r14; P
0x180048b65  xor     edx, edx; Flags
0x180048b67  call    cs:__imp_RtlFreeHeap
0x180048b6d  xor     eax, eax
0x180048b6f  mov     r14d, eax
0x180048b72  mov     edi, eax
0x180048b74  jmp     short loc_180048B86
0x180048b76  test    eax, eax
0x180048b78  js      loc_180048ADC
0x180048b7e  mov     edi, dword ptr [rbp+160h+KeyHandle]
0x180048b81  jmp     short loc_180048B86
0x180048b83  mov     edi, [rbp+160h+var_1B8]
0x180048b86  test    esi, esi
0x180048b88  jz      loc_180048D02
0x180048b8e  sub     esi, 1
0x180048b91  jz      loc_180048C61
0x180048b97  cmp     esi, 1
  ... truncated ...
```
