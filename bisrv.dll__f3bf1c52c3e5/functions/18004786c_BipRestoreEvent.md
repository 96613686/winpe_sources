# BipRestoreEvent

- ea: `0x18004786c`
- end: `0x180047f16`
- name: `BipRestoreEvent`
- size: `1706`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004745c`

## callees

- `0x1800075f8`
- `0x1800095b0`
- `0x18001027c`
- `0x1800260e8`
- `0x1800263b8`
- `0x180026f8c`
- `0x18002abf8`
- `0x180030f24`
- `0x1800317f0`
- `0x18003a4b8`
- `0x18003a62c`
- `0x1800457ac`
- `0x18004786c`
- `0x180053100`
- `0x18006e218`
- `0x1800806b4`
- `0x180094662`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ntdll!NtOpenKey` at `0x18004797c`
- `ntdll!NtOpenKey` at `0x18004797c`
- `ntdll!RtlFreeUnicodeString` at `0x180047b7b`
- `ntdll!RtlFreeUnicodeString` at `0x180047b9f`
- `ntdll!RtlFreeUnicodeString` at `0x180047b7b`
- `ntdll!RtlFreeUnicodeString` at `0x180047b9f`
- `ntdll!RtlInitUnicodeString` at `0x18004799d`
- `ntdll!RtlInitUnicodeString` at `0x1800479d0`
- `ntdll!RtlInitUnicodeString` at `0x180047a37`
- `ntdll!RtlInitUnicodeString` at `0x180047a74`
- `ntdll!RtlInitUnicodeString` at `0x180047b40`
- `ntdll!RtlInitUnicodeString` at `0x180047bbc`
- `ntdll!RtlInitUnicodeString` at `0x180047c20`
- `ntdll!RtlInitUnicodeString` at `0x180047c6e`
- `ntdll!RtlInitUnicodeString` at `0x180047d58`
- `ntdll!RtlInitUnicodeString` at `0x18004799d`
- `ntdll!RtlInitUnicodeString` at `0x1800479d0`
- `ntdll!RtlInitUnicodeString` at `0x180047a37`
- `ntdll!RtlInitUnicodeString` at `0x180047a74`
- `ntdll!RtlInitUnicodeString` at `0x180047b40`
- `ntdll!RtlInitUnicodeString` at `0x180047bbc`
- `ntdll!RtlInitUnicodeString` at `0x180047c20`
- `ntdll!RtlInitUnicodeString` at `0x180047c6e`
- `ntdll!RtlInitUnicodeString` at `0x180047d58`
- `ntdll!RtlFreeHeap` at `0x180047ace`
- `ntdll!RtlFreeHeap` at `0x180047e85`
- `ntdll!RtlFreeHeap` at `0x180047ec8`
- `ntdll!RtlFreeHeap` at `0x180047ed0`
- `ntdll!RtlFreeHeap` at `0x180047ace`
- `ntdll!RtlFreeHeap` at `0x180047e85`
- `ntdll!RtlFreeHeap` at `0x180047ec8`
- `ntdll!RtlFreeHeap` at `0x180047ed0`
- `ntdll!RtlAllocateHeap` at `0x180047a0c`
- `ntdll!RtlAllocateHeap` at `0x180047a0c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047e95`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047e95`

## string_xrefs

- `0x180047bb1`: `UserSid`
- `0x180047992`: `BrokerId`
- `0x180047c15`: `ForUserSid`
- `0x180047d4d`: `CreationSid`

## pseudocode

```c
__int64 __fastcall BipRestoreEvent(void *a1, UUID *a2, struct _UNICODE_STRING *a3, int a4)
{
  void *v4; // r14
  __int64 v9; // r8
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // r9
  bool v13; // r15
  __int64 v14; // rsi
  int Event; // ebx
  __int64 v16; // r8
  int v17; // edi
  int v18; // eax
  unsigned int v19; // r13d
  int v20; // edi
  int v21; // eax
  int v22; // eax
  int v23; // eax
  _BYTE *v24; // rdx
  int v25; // eax
  _BYTE *v26; // rdx
  int v27; // eax
  int v28; // ebx
  __int64 v29; // rcx
  __int64 v30; // r8
  __int64 v31; // r9
  int v32; // eax
  __int64 v33; // rcx
  __int64 v34; // r9
  __int64 v35; // rcx
  __int64 v36; // r8
  __int64 v37; // r9
  char v39[8]; // [rsp+60h] [rbp-A0h] BYREF
  void *KeyHandle; // [rsp+68h] [rbp-98h] BYREF
  int v41; // [rsp+70h] [rbp-90h] BYREF
  __int64 Heap; // [rsp+78h] [rbp-88h] BYREF
  int v43[2]; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-78h] BYREF
  GUID *p_Guid; // [rsp+98h] [rbp-68h] BYREF
  __int64 v46; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v47; // [rsp+A8h] [rbp-58h] BYREF
  PSID Sid1; // [rsp+B0h] [rbp-50h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+B8h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C8h] [rbp-38h] BYREF
  GUID Guid; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE DestinationSid[80]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v53[80]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v54[256]; // [rsp+1B0h] [rbp+B0h] BYREF

  v4 = 0;
  KeyHandle = 0;
  LODWORD(p_Guid) = 0;
  v41 = 0;
  Guid = 0;
  memset_0(v53, 0, 0x44u);
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  UnicodeString = 0;
  memset_0(DestinationSid, 0, 0x44u);
  DestinationString = 0;
  if ( (unsigned int)dword_1800C3098 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800C3098, 2, v9) )
  {
    Heap = (__int64)a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(
      v10,
      (unsigned __int8 *)&dword_1800B4E6C,
      v11,
      v12,
      &Heap);
  }
  v13 = 1;
  v46 = 0;
  KeyHandle = 0;
  Guid = GUID_NULL;
  v39[0] = 1;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = a1;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v14 = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = a3;
  Event = NtOpenKey(&KeyHandle, 0xF003Fu, &ObjectAttributes);
  if ( Event >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"BrokerId");
    Event = BipReadRegGuid(KeyHandle, &DestinationString, &Guid);
    if ( Event >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, L"Flags");
      Event = BipReadRegUlong(KeyHandle, &DestinationString);
      if ( Event >= 0 )
      {
        v43[0] = 0x2000;
        Heap = (__int64)RtlAllocateHeap(BipHeap, 0, 0x2000u);
        v4 = (void *)Heap;
        if ( Heap )
        {
          RtlInitUnicodeString(&DestinationString, L"EventParameters");
          v18 = BipReadRegBinary(KeyHandle, &DestinationString, v4);
          Event = v18;
          if ( v18 < 0 )
          {
            if ( v18 != -1073741772 )
            {
              v17 = 50;
              goto LABEL_61;
            }
            RtlInitUnicodeString(&DestinationString, L"EventInformation");
            Event = BipReadRegBinary(KeyHandle, &DestinationString, v4);
            if ( Event < 0 )
            {
              v17 = 60;
              goto LABEL_61;
            }
            v13 = (v41 & 0x800000) != 0;
            v39[0] = v13;
          }
          v19 = v43[0];
          v20 = a4 | 1;
          if ( !v43[0] )
          {
            RtlFreeHeap(BipHeap, 0, v4);
            v4 = 0;
            Heap = 0;
          }
          if ( v4 && (v20 & 8) != 0 && !v13 )
          {
            v21 = BipConvertEventInfoToEventParam(&Guid, (PVOID *)&Heap, v43, v39);
            v4 = (void *)Heap;
            Event = v21;
            if ( v21 < 0 )
            {
              v17 = 70;
              goto LABEL_61;
            }
            v19 = v43[0];
            v13 = v39[0];
          }
          memset_0(v54, 0, sizeof(v54));
          RtlInitUnicodeString(&DestinationString, L"PackageFullName");
          v22 = BipReadRegUnicodeString(KeyHandle, &DestinationString, &UnicodeString);
          Event = v22;
          if ( v22 < 0 )
          {
            Heap = 0;
            if ( v22 != -1073741772 )
            {
              v17 = 90;
              goto LABEL_61;
            }
          }
          else
          {
            if ( UnicodeString.Length > 0xFEu )
            {
              Event = -1073741789;
              v17 = 80;
              RtlFreeUnicodeString(&UnicodeString);
              goto LABEL_61;
            }
            memcpy_0(v54, UnicodeString.Buffer, UnicodeString.Length);
            RtlFreeUnicodeString(&UnicodeString);
            Heap = (__int64)v54;
          }
          RtlInitUnicodeString(&DestinationString, L"UserSid");
          v23 = BipReadRegSid(KeyHandle, &DestinationString, DestinationSid);
          v24 = DestinationSid;
          v16 = 3221225524LL;
          if ( v23 == -1073741772 )
            v24 = 0;
          Event = 0;
          Sid1 = v24;
          if ( v23 != -1073741772 )
            Event = v23;
          if ( Event >= 0 )
          {
            RtlInitUnicodeString(&DestinationString, L"ForUserSid");
            v25 = BipReadRegSid(KeyHandle, &DestinationString, v53);
            Event = 0;
            v26 = v53;
            v16 = 3221225524LL;
            if ( v25 == -1073741772 )
              v26 = 0;
            else
              Event = v25;
            v47 = (__int64)v26;
            if ( Event >= 0 )
            {
              RtlInitUnicodeString(&DestinationString, L"EventType");
              v27 = BipReadRegUlong(KeyHandle, &DestinationString);
              Event = v27;
              if ( v27 == -1073741772 )
              {
                v28 = 0;
                v20 |= 4u;
              }
              else
              {
                if ( v27 < 0 )
                {
                  v17 = 120;
                  goto LABEL_61;
                }
                v28 = (int)p_Guid;
              }
              if ( v13 )
                v20 |= 0x10u;
              if ( (unsigned int)dword_1800C3098 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800C3098, 3, v16) )
              {
                *(_QWORD *)v43 = a2;
                p_Guid = &Guid;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>>(
                  v29,
                  (__int64)byte_1800B4E35,
                  v30,
                  v31,
                  v43,
                  &p_Guid);
              }
              Event = BiSrvCreateEvent(
                        (__int64)a2,
                        v20,
                        v41,
                        (__int64)&Guid,
                        a2,
                        (__int64 *)Heap,
                        (__int64 *)Sid1,
                        (__int64 *)v47,
                        v28,
                        v4,
                        v19,
                        0);
              if ( Event >= 0 )
              {
                RtlInitUnicodeString(&DestinationString, L"CreationSid");
                if ( (int)BipReadRegSid(KeyHandle, &DestinationString, DestinationSid) < 0 )
                {
                  Event = 0;
                }
                else
                {
                  v32 = BipLookupEventByGuid(a2);
                  v14 = v46;
                  Event = v32;
                  if ( v32 < 0 )
                  {
                    v17 = 140;
                    goto LABEL_61;
                  }
                  Event = BipSetEventCreationSid(v46, DestinationSid);
                }
                v17 = 0;
                goto LABEL_61;
              }
              v17 = 130;
            }
            else
            {
              v17 = 110;
            }
          }
          else
          {
            v17 = 100;
          }
        }
        else
        {
          Event = -1073741801;
          v17 = 40;
        }
      }
      else
      {
        v17 = 30;
      }
    }
    else
    {
      v17 = 20;
    }
  }
  else
  {
    v17 = 10;
  }
LABEL_61:
  if ( (unsigned int)dword_1800C3098 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800C3098, 3, v16) )
  {
    LODWORD(p_Guid) = v17;
    Sid1 = &Guid;
    v41 = Event;
    v47 = (__int64)a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v33,
      (unsigned __int8 *)&unk_1800B5030,
      v16,
      v34,
      &v47,
      (__int64 *)&Sid1,
      (__int64)&v41,
      (__int64)&p_Guid);
  }
  if ( Event < 0
    && (unsigned int)dword_1800C3098 > 2
    && (unsigned __int8)tlgKeywordOn(&dword_1800C3098, 0x200000000003LL, v16) )
  {
    v43[0] = v17;
    Sid1 = &Guid;
    LODWORD(v46) = Event;
    v47 = (__int64)a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v35,
      (unsigned __int8 *)byte_1800B513B,
      v36,
      v37,
      &v47,
      (__int64 *)&Sid1,
      (__int64)&v46,
      (__int64)v43);
  }
  if ( v4 )
    RtlFreeHeap(BipHeap, 0, v4);
  if ( KeyHandle )
    CloseHandle(KeyHandle);
  if ( v14 && _InterlockedExchangeAdd((volatile signed __int32 *)(v14 + 28), 0xFFFFFFFF) == 1 )
  {
    if ( *(_DWORD *)(v14 + 48) == 1 )
    {
      BipEventQueueDestroy((struct _BI_LOCK *)&qword_1800C4600);
    }
    else if ( *(_DWORD *)(v14 + 48) == 2 )
    {
      BipWorkItemCheckQueueDestroy((struct _BI_WORK_ITEM *)v14);
    }
    else
    {
      RtlFreeHeap(BipHeap, 0, (PVOID)v14);
    }
  }
  return (unsigned int)Event;
}

```

## disassembly

```asm
0x18004786c  push    rbp
0x18004786e  push    rbx
0x18004786f  push    rsi
0x180047870  push    rdi
0x180047871  push    r12
0x180047873  push    r13
0x180047875  push    r14
0x180047877  push    r15
0x180047879  lea     rbp, [rsp-1C8h]
0x180047881  sub     rsp, 2C8h
0x180047888  mov     rax, cs:__security_cookie
0x18004788f  xor     rax, rsp
0x180047892  mov     [rbp+200h+var_50], rax
0x180047899  xor     r14d, r14d
0x18004789c  mov     r13, r8
0x18004789f  mov     r12, rdx
0x1800478a2  mov     [rsp+300h+KeyHandle], r14
0x1800478a7  mov     rbx, rcx
0x1800478aa  mov     dword ptr [rbp+200h+var_268], r14d
0x1800478ae  xorps   xmm0, xmm0
0x1800478b1  mov     [rsp+300h+var_290], r14d
0x1800478b6  lea     esi, [r14+44h]
0x1800478ba  xor     edx, edx; Val
0x1800478bc  mov     r8d, esi; Size
0x1800478bf  lea     rcx, [rbp+200h+var_1A0]; void *
0x1800478c3  mov     edi, r9d
0x1800478c6  movups  xmmword ptr [rbp+200h+Guid.Data1], xmm0
0x1800478ca  call    memset_0
0x1800478cf  xorps   xmm0, xmm0
0x1800478d2  lea     rcx, [rbp+200h+DestinationSid]; void *
0x1800478d6  mov     r8d, esi; Size
0x1800478d9  xor     edx, edx; Val
0x1800478db  movups  xmmword ptr [rbp+200h+ObjectAttributes.Length], xmm0
0x1800478df  movups  xmmword ptr [rbp+200h+ObjectAttributes.ObjectName], xmm0
0x1800478e3  movups  xmmword ptr [rbp+200h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800478e7  movups  xmmword ptr [rbp+200h+UnicodeString.Length], xmm0
0x1800478eb  call    memset_0
0x1800478f0  mov     eax, cs:dword_1800C3098
0x1800478f6  xorps   xmm0, xmm0
0x1800478f9  movups  xmmword ptr [rbp+200h+DestinationString.Length], xmm0
0x1800478fd  cmp     eax, 5
0x180047900  jbe     short loc_180047930
0x180047902  lea     edx, [rsi-42h]
0x180047905  lea     rcx, dword_1800C3098
0x18004790c  call    _tlgKeywordOn
0x180047911  test    al, al
0x180047913  jz      short loc_180047930
0x180047915  lea     rax, [rsp+300h+var_288]
0x18004791a  mov     [rsp+300h+var_288], r12
0x18004791f  lea     rdx, dword_1800B4E6C
0x180047926  mov     [rsp+300h+Source1], rax
0x18004792b  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &)
0x180047930  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180047937  mov     r15b, 1
0x18004793a  mov     [rbp+200h+var_260], r14
0x18004793e  lea     r8, [rbp+200h+ObjectAttributes]; ObjectAttributes
0x180047942  mov     [rsp+300h+KeyHandle], r14
0x180047947  movdqu  xmmword ptr [rbp+200h+Guid.Data1], xmm0
0x18004794c  mov     [rsp+300h+var_2A0], r15b
0x180047951  mov     edx, 0F003Fh; DesiredAccess
0x180047956  xorps   xmm0, xmm0
0x180047959  mov     [rbp+200h+ObjectAttributes.Length], 30h ; '0'
0x180047960  lea     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x180047965  mov     [rbp+200h+ObjectAttributes.RootDirectory], rbx
0x180047969  movdqu  xmmword ptr [rbp+200h+ObjectAttributes.SecurityDescriptor], xmm0
0x18004796e  mov     rsi, r14
0x180047971  mov     [rbp+200h+ObjectAttributes.Attributes], 40h ; '@'
0x180047978  mov     [rbp+200h+ObjectAttributes.ObjectName], r13
0x18004797c  call    cs:__imp_NtOpenKey
0x180047982  mov     ebx, eax
0x180047984  test    eax, eax
0x180047986  jns     short loc_180047992
0x180047988  mov     edi, 0Ah
0x18004798d  jmp     loc_180047DA5
0x180047992  lea     rdx, aBrokerid; "BrokerId"
0x180047999  lea     rcx, [rbp+200h+DestinationString]; DestinationString
0x18004799d  call    cs:__imp_RtlInitUnicodeString
0x1800479a3  mov     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x1800479a8  lea     r8, [rbp+200h+Guid]; Guid
0x1800479ac  lea     rdx, [rbp+200h+DestinationString]; ValueName
0x1800479b0  call    BipReadRegGuid
0x1800479b5  mov     ebx, eax
0x1800479b7  test    eax, eax
0x1800479b9  jns     short loc_1800479C5
0x1800479bb  mov     edi, 14h
0x1800479c0  jmp     loc_180047DA5
0x1800479c5  lea     rdx, aFlags; "Flags"
0x1800479cc  lea     rcx, [rbp+200h+DestinationString]; DestinationString
0x1800479d0  call    cs:__imp_RtlInitUnicodeString
0x1800479d6  mov     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x1800479db  lea     r8, [rsp+300h+var_290]
0x1800479e0  lea     rdx, [rbp+200h+DestinationString]; ValueName
0x1800479e4  call    BipReadRegUlong
0x1800479e9  mov     ebx, eax
0x1800479eb  test    eax, eax
0x1800479ed  jns     short loc_1800479F9
0x1800479ef  mov     edi, 1Eh
0x1800479f4  jmp     loc_180047DA5
0x1800479f9  mov     rcx, cs:BipHeap; HeapHandle
0x180047a00  mov     r8d, 2000h; Size
0x180047a06  xor     edx, edx; Flags
0x180047a08  mov     [rbp+200h+var_280], r8d
0x180047a0c  call    cs:__imp_RtlAllocateHeap
0x180047a12  mov     [rsp+300h+var_288], rax
0x180047a17  mov     r14, rax
0x180047a1a  test    rax, rax
0x180047a1d  jnz     short loc_180047A2C
0x180047a1f  mov     ebx, 0C0000017h
0x180047a24  lea     edi, [rax+28h]
0x180047a27  jmp     loc_180047DA5
0x180047a2c  lea     rdx, aEventparameter; "EventParameters"
0x180047a33  lea     rcx, [rbp+200h+DestinationString]; DestinationString
0x180047a37  call    cs:__imp_RtlInitUnicodeString
0x180047a3d  mov     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x180047a42  lea     r9, [rbp+200h+var_280]
0x180047a46  mov     r8, r14; void *
0x180047a49  lea     rdx, [rbp+200h+DestinationString]; ValueName
0x180047a4d  call    BipReadRegBinary
0x180047a52  mov     ebx, eax
0x180047a54  test    eax, eax
0x180047a56  jns     short loc_180047AB6
0x180047a58  cmp     eax, 0C0000034h
0x180047a5d  jz      short loc_180047A69
0x180047a5f  mov     edi, 32h ; '2'
0x180047a64  jmp     loc_180047DA5
0x180047a69  lea     rdx, aEventinformati; "EventInformation"
0x180047a70  lea     rcx, [rbp+200h+DestinationString]; DestinationString
0x180047a74  call    cs:__imp_RtlInitUnicodeString
0x180047a7a  mov     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x180047a7f  lea     r9, [rbp+200h+var_280]
0x180047a83  mov     r8, r14; void *
0x180047a86  lea     rdx, [rbp+200h+DestinationString]; ValueName
0x180047a8a  call    BipReadRegBinary
0x180047a8f  mov     ebx, eax
0x180047a91  test    eax, eax
0x180047a93  jns     short loc_180047A9F
0x180047a95  mov     edi, 3Ch ; '<'
0x180047a9a  jmp     loc_180047DA5
0x180047a9f  mov     eax, [rsp+300h+var_290]
0x180047aa3  and     eax, 800000h
0x180047aa8  neg     eax
0x180047aaa  sbb     al, al
0x180047aac  and     al, r15b
0x180047aaf  mov     r15b, al
0x180047ab2  mov     [rsp+300h+var_2A0], al
0x180047ab6  mov     r13d, [rbp+200h+var_280]
0x180047aba  or      edi, 1
0x180047abd  test    r13d, r13d
0x180047ac0  jnz     short loc_180047ADC
0x180047ac2  mov     rcx, cs:BipHeap; HeapHandle
0x180047ac9  mov     r8, r14; P
0x180047acc  xor     edx, edx; Flags
0x180047ace  call    cs:__imp_RtlFreeHeap
0x180047ad4  xor     r14d, r14d
0x180047ad7  mov     [rsp+300h+var_288], r14
0x180047adc  test    r14, r14
0x180047adf  jz      short loc_180047B21
0x180047ae1  test    dil, 8
0x180047ae5  jz      short loc_180047B21
0x180047ae7  test    r15b, r15b
0x180047aea  jnz     short loc_180047B21
0x180047aec  lea     r9, [rsp+300h+var_2A0]
0x180047af1  lea     r8, [rbp+200h+var_280]
0x180047af5  lea     rdx, [rsp+300h+var_288]
0x180047afa  lea     rcx, [rbp+200h+Guid]
0x180047afe  call    BipConvertEventInfoToEventParam
0x180047b03  mov     r14, [rsp+300h+var_288]
0x180047b08  mov     ebx, eax
0x180047b0a  test    eax, eax
0x180047b0c  jns     short loc_180047B18
0x180047b0e  mov     edi, 46h ; 'F'
0x180047b13  jmp     loc_180047DA5
0x180047b18  mov     r13d, [rbp+200h+var_280]
0x180047b1c  mov     r15b, [rsp+300h+var_2A0]
0x180047b21  xor     edx, edx; Val
0x180047b23  lea     rcx, [rbp+200h+var_150]; void *
0x180047b2a  mov     r8d, 100h; Size
0x180047b30  call    memset_0
0x180047b35  lea     rdx, aPackagefullnam; "PackageFullName"
0x180047b3c  lea     rcx, [rbp+200h+DestinationString]; DestinationString
0x180047b40  call    cs:__imp_RtlInitUnicodeString
0x180047b46  mov     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x180047b4b  lea     r8, [rbp+200h+UnicodeString]; DestinationString
0x180047b4f  lea     rdx, [rbp+200h+DestinationString]; ValueName
0x180047b53  call    BipReadRegUnicodeString
0x180047b58  mov     ebx, eax
0x180047b5a  test    eax, eax
0x180047b5c  js      loc_180047BFF
0x180047b62  mov     eax, 0FEh
0x180047b67  cmp     [rbp+200h+UnicodeString.Length], ax
0x180047b6b  jbe     short loc_180047B86
0x180047b6d  lea     rcx, [rbp+200h+UnicodeString]; UnicodeString
0x180047b71  mov     ebx, 0C0000023h
0x180047b76  mov     edi, 50h ; 'P'
0x180047b7b  call    cs:__imp_RtlFreeUnicodeString
0x180047b81  jmp     loc_180047DA5
0x180047b86  movzx   r8d, [rbp+200h+UnicodeString.Length]; Size
0x180047b8b  lea     rcx, [rbp+200h+var_150]; void *
0x180047b92  mov     rdx, [rbp+200h+UnicodeString.Buffer]; Src
0x180047b96  call    memcpy_0
0x180047b9b  lea     rcx, [rbp+200h+UnicodeString]; UnicodeString
0x180047b9f  call    cs:__imp_RtlFreeUnicodeString
0x180047ba5  lea     rax, [rbp+200h+var_150]
0x180047bac  mov     [rsp+300h+var_288], rax
0x180047bb1  lea     rdx, aUsersid; "UserSid"
0x180047bb8  lea     rcx, [rbp+200h+DestinationString]; DestinationString
0x180047bbc  call    cs:__imp_RtlInitUnicodeString
0x180047bc2  mov     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x180047bc7  lea     r8, [rbp+200h+DestinationSid]; DestinationSid
0x180047bcb  lea     rdx, [rbp+200h+DestinationString]; ValueName
0x180047bcf  call    BipReadRegSid
0x180047bd4  xor     ecx, ecx
0x180047bd6  lea     rdx, [rbp+200h+DestinationSid]
0x180047bda  mov     r8d, 0C0000034h
0x180047be0  cmp     eax, r8d
0x180047be3  cmovz   rdx, rcx
0x180047be7  xor     ebx, ebx
0x180047be9  cmp     eax, r8d
0x180047bec  mov     [rbp+200h+var_250], rdx
0x180047bf0  cmovnz  ebx, eax
0x180047bf3  test    ebx, ebx
0x180047bf5  jns     short loc_180047C15
0x180047bf7  lea     edi, [rcx+64h]
0x180047bfa  jmp     loc_180047DA5
0x180047bff  mov     [rsp+300h+var_288], rsi
0x180047c04  cmp     eax, 0C0000034h
0x180047c09  jz      short loc_180047BB1
0x180047c0b  mov     edi, 5Ah ; 'Z'
0x180047c10  jmp     loc_180047DA5
0x180047c15  lea     rdx, aForusersid; "ForUserSid"
0x180047c1c  lea     rcx, [rbp+200h+DestinationString]; DestinationString
0x180047c20  call    cs:__imp_RtlInitUnicodeString
0x180047c26  mov     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x180047c2b  lea     r8, [rbp+200h+var_1A0]; DestinationSid
0x180047c2f  lea     rdx, [rbp+200h+DestinationString]; ValueName
0x180047c33  call    BipReadRegSid
0x180047c38  xor     ebx, ebx
0x180047c3a  lea     rdx, [rbp+200h+var_1A0]
0x180047c3e  mov     r8d, 0C0000034h
0x180047c44  cmp     eax, r8d
0x180047c47  cmovnz  ebx, eax
0x180047c4a  xor     ecx, ecx
0x180047c4c  cmp     eax, r8d
0x180047c4f  cmovz   rdx, rcx
0x180047c53  mov     [rbp+200h+var_258], rdx
0x180047c57  test    ebx, ebx
0x180047c59  jns     short loc_180047C63
0x180047c5b  lea     edi, [rcx+6Eh]
0x180047c5e  jmp     loc_180047DA5
0x180047c63  lea     rdx, aEventtype; "EventType"
0x180047c6a  lea     rcx, [rbp+200h+DestinationString]; DestinationString
0x180047c6e  call    cs:__imp_RtlInitUnicodeString
0x180047c74  mov     rcx, [rsp+300h+KeyHandle]; KeyHandle
0x180047c79  lea     r8, [rbp+200h+var_268]
0x180047c7d  lea     rdx, [rbp+200h+DestinationString]; ValueName
0x180047c81  call    BipReadRegUlong
0x180047c86  mov     ebx, eax
0x180047c88  cmp     eax, 0C0000034h
0x180047c8d  jnz     short loc_180047C96
0x180047c8f  xor     ebx, ebx
0x180047c91  or      edi, 4
0x180047c94  jmp     short loc_180047CA7
0x180047c96  test    eax, eax
0x180047c98  jns     short loc_180047CA4
0x180047c9a  mov     edi, 78h ; 'x'
0x180047c9f  jmp     loc_180047DA5
0x180047ca4  mov     ebx, dword ptr [rbp+200h+var_268]
0x180047ca7  test    r15b, r15b
0x180047caa  jz      short loc_180047CAF
0x180047cac  or      edi, 10h
0x180047caf  mov     eax, cs:dword_1800C3098
0x180047cb5  cmp     eax, 4
0x180047cb8  jbe     short loc_180047CF9
0x180047cba  mov     edx, 3
0x180047cbf  lea     rcx, dword_1800C3098
0x180047cc6  call    _tlgKeywordOn
0x180047ccb  test    al, al
0x180047ccd  jz      short loc_180047CF9
0x180047ccf  lea     rax, [rbp+200h+Guid]
0x180047cd3  mov     qword ptr [rbp+200h+var_280], r12
0x180047cd7  mov     [rbp+200h+var_268], rax
0x180047cdb  lea     rdx, byte_1800B4E35
0x180047ce2  lea     rax, [rbp+200h+var_268]
0x180047ce6  mov     [rsp+300h+var_2D8], rax
0x180047ceb  lea     rax, [rbp+200h+var_280]
0x180047cef  mov     [rsp+300h+Source1], rax
0x180047cf4  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByRef<16> const &)
0x180047cf9  mov     rax, [rbp+200h+var_258]
0x180047cfd  lea     r9, [rbp+200h+Guid]; int
0x180047d01  mov     r8d, [rsp+300h+var_290]; int
0x180047d06  mov     edx, edi; int
0x180047d08  mov     [rsp+300h+var_2A8], rsi; __int64
0x180047d0d  mov     rcx, r12; int
0x180047d10  mov     [rsp+300h+var_2B0], r13d; int
0x180047d15  mov     [rsp+300h+var_2B8], r14; __int64
0x180047d1a  mov     [rsp+300h+var_2C0], ebx; int
0x180047d1e  mov     [rsp+300h+var_2C8], rax; __int64
0x180047d23  mov     rax, [rbp+200h+var_250]
0x180047d27  mov     [rsp+300h+Sid1], rax; Sid1
0x180047d2c  mov     rax, [rsp+300h+var_288]
  ... truncated ...
```
