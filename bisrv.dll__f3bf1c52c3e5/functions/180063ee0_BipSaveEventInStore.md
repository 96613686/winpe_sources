# BipSaveEventInStore

- ea: `0x180063ee0`
- end: `0x18006420c`
- name: `BipSaveEventInStore`
- size: `812`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18005f8f0`

## callees

- `0x1800249ec`
- `0x180024b54`
- `0x180024e14`
- `0x180025d68`
- `0x180025e0c`
- `0x180025f14`
- `0x180025fcc`
- `0x18003a62c`
- `0x18003d470`
- `0x180053100`
- `0x180063ee0`

## import_xrefs

- `ntdll!NtDeleteKey` at `0x18006416e`
- `ntdll!NtDeleteKey` at `0x18006416e`
- `ntdll!RtlInitUnicodeString` at `0x180063f58`
- `ntdll!RtlInitUnicodeString` at `0x180063f64`
- `ntdll!RtlInitUnicodeString` at `0x180063fb9`
- `ntdll!RtlInitUnicodeString` at `0x180063ff9`
- `ntdll!RtlInitUnicodeString` at `0x180064035`
- `ntdll!RtlInitUnicodeString` at `0x180064077`
- `ntdll!RtlInitUnicodeString` at `0x1800640b9`
- `ntdll!RtlInitUnicodeString` at `0x1800640c6`
- `ntdll!RtlInitUnicodeString` at `0x1800640fe`
- `ntdll!RtlInitUnicodeString` at `0x180064139`
- `ntdll!RtlInitUnicodeString` at `0x180063f58`
- `ntdll!RtlInitUnicodeString` at `0x180063f64`
- `ntdll!RtlInitUnicodeString` at `0x180063fb9`
- `ntdll!RtlInitUnicodeString` at `0x180063ff9`
- `ntdll!RtlInitUnicodeString` at `0x180064035`
- `ntdll!RtlInitUnicodeString` at `0x180064077`
- `ntdll!RtlInitUnicodeString` at `0x1800640b9`
- `ntdll!RtlInitUnicodeString` at `0x1800640c6`
- `ntdll!RtlInitUnicodeString` at `0x1800640fe`
- `ntdll!RtlInitUnicodeString` at `0x180064139`
- `ntdll!RtlFreeHeap` at `0x180064190`
- `ntdll!RtlFreeHeap` at `0x180064190`
- `ntdll!NtClose` at `0x180064178`
- `ntdll!NtClose` at `0x180064178`

## string_xrefs

- `0x1800640f3`: `UserSid`
- `0x180063fae`: `BrokerId`
- `0x18006412e`: `ForUserSid`

## pseudocode

```c
__int64 __fastcall BipSaveEventInStore(__int64 a1, int a2, __int64 a3)
{
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  int v8; // ebx
  int v9; // edi
  const WCHAR *v10; // rdx
  HANDLE v11; // rcx
  PVOID v12; // r8
  __int64 v13; // r8
  __int64 v14; // r9
  HANDLE KeyHandle; // [rsp+40h] [rbp-40h] BYREF
  __int64 v17; // [rsp+48h] [rbp-38h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+50h] [rbp-30h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp-20h] BYREF
  PVOID P[2]; // [rsp+70h] [rbp-10h] BYREF
  __int64 v21; // [rsp+B0h] [rbp+30h] BYREF
  int v22; // [rsp+B8h] [rbp+38h] BYREF

  KeyHandle = 0;
  *(_OWORD *)P = 0;
  DestinationString = 0;
  ValueName = 0;
  if ( (unsigned int)dword_1800C3098 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800C3098, 2, a3) )
  {
    v21 = a1 + 32;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(
      v5,
      (unsigned __int8 *)byte_1800B4E99,
      v6,
      v7,
      &v21);
  }
  RtlInitUnicodeString(&DestinationString, 0);
  RtlInitUnicodeString(&ValueName, 0);
  KeyHandle = 0;
  v8 = BipConstructEventKeyName(a1, P);
  if ( v8 >= 0 )
  {
    v8 = BipCreateKey(::KeyHandle, &KeyHandle, P);
    if ( v8 >= 0 )
    {
      RtlInitUnicodeString(&ValueName, L"BrokerId");
      v8 = BipWriteRegGuid(KeyHandle, &ValueName, (GUID *)(a1 + 128));
      if ( v8 >= 0 )
      {
        v10 = L"EventInformation";
        if ( a2 )
          v10 = L"EventParameters";
        RtlInitUnicodeString(&ValueName, v10);
        v8 = BipWriteRegBinary(KeyHandle, &ValueName, (PVOID)(a1 + 796), *(_DWORD *)(a1 + 792));
        if ( v8 >= 0 )
        {
          RtlInitUnicodeString(&ValueName, L"Flags");
          v8 = BipWriteRegUlong(KeyHandle, &ValueName);
          if ( v8 >= 0 )
          {
            if ( (*(_DWORD *)(a1 + 24) & 0x20000000) != 0
              && (RtlInitUnicodeString(&ValueName, L"EventType"), v8 = BipWriteRegUlong(KeyHandle, &ValueName), v8 < 0) )
            {
              v9 = 60;
            }
            else if ( *(_WORD *)(a1 + 192)
                   && (RtlInitUnicodeString(&ValueName, L"PackageFullName"),
                       RtlInitUnicodeString(&DestinationString, (PCWSTR)(a1 + 192)),
                       v8 = BipWriteRegUnicodeString(KeyHandle, &ValueName),
                       v8 < 0) )
            {
              v9 = 70;
            }
            else if ( *(_QWORD *)(a1 + 168)
                   && (RtlInitUnicodeString(&ValueName, L"UserSid"),
                       v8 = BipWriteRegSid(KeyHandle, &ValueName, *(PVOID *)(a1 + 168)),
                       v8 < 0) )
            {
              v9 = 80;
            }
            else if ( !*(_QWORD *)(a1 + 176)
                   || (RtlInitUnicodeString(&ValueName, L"ForUserSid"),
                       v8 = BipWriteRegSid(KeyHandle, &ValueName, *(PVOID *)(a1 + 176)),
                       v9 = 90,
                       v8 >= 0) )
            {
              v9 = 0;
            }
          }
          else
          {
            v9 = 50;
          }
        }
        else
        {
          v9 = 40;
        }
      }
      else
      {
        v9 = 30;
      }
    }
    else
    {
      v9 = 20;
    }
  }
  else
  {
    v9 = 10;
  }
  v11 = KeyHandle;
  if ( KeyHandle )
  {
    if ( v8 < 0 )
    {
      NtDeleteKey(KeyHandle);
      v11 = KeyHandle;
    }
    NtClose(v11);
  }
  v12 = P[1];
  if ( P[1] )
    RtlFreeHeap(BipHeap, 0, P[1]);
  if ( (unsigned int)dword_1800C3098 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800C3098, 2, v12) )
  {
    LODWORD(v21) = v9;
    v17 = a1 + 32;
    v22 = v8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)&dword_1800C3098,
      (unsigned __int8 *)byte_1800B507D,
      v13,
      v14,
      &v17,
      (__int64)&v22,
      (__int64)&v21);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180063ee0  mov     [rsp-18h+arg_0], rbx
0x180063ee5  mov     [rsp-18h+arg_8], rsi
0x180063eea  push    rbp
0x180063eeb  push    rdi
0x180063eec  push    r14
0x180063eee  mov     rbp, rsp
0x180063ef1  sub     rsp, 80h
0x180063ef8  mov     eax, cs:dword_1800C3098
0x180063efe  xor     r14d, r14d
0x180063f01  mov     [rbp+KeyHandle], r14
0x180063f05  xorps   xmm0, xmm0
0x180063f08  xorps   xmm1, xmm1
0x180063f0b  mov     edi, edx
0x180063f0d  mov     rsi, rcx
0x180063f10  movups  xmmword ptr [rbp+P], xmm0
0x180063f14  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x180063f18  movups  xmmword ptr [rbp+ValueName.Length], xmm0
0x180063f1c  cmp     eax, 4
0x180063f1f  jbe     short loc_180063F52
0x180063f21  lea     edx, [r14+2]
0x180063f25  lea     rcx, dword_1800C3098
0x180063f2c  call    _tlgKeywordOn
0x180063f31  test    al, al
0x180063f33  jz      short loc_180063F52
0x180063f35  lea     rax, [rsi+20h]
0x180063f39  mov     [rbp+arg_10], rax
0x180063f3d  lea     rdx, byte_1800B4E99
0x180063f44  lea     rax, [rbp+arg_10]
0x180063f48  mov     [rsp+80h+var_60], rax
0x180063f4d  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &)
0x180063f52  xor     edx, edx; SourceString
0x180063f54  lea     rcx, [rbp+DestinationString]; DestinationString
0x180063f58  call    cs:__imp_RtlInitUnicodeString
0x180063f5e  xor     edx, edx; SourceString
0x180063f60  lea     rcx, [rbp+ValueName]; DestinationString
0x180063f64  call    cs:__imp_RtlInitUnicodeString
0x180063f6a  lea     rdx, [rbp+P]
0x180063f6e  mov     [rbp+KeyHandle], r14
0x180063f72  mov     rcx, rsi
0x180063f75  call    BipConstructEventKeyName
0x180063f7a  mov     ebx, eax
0x180063f7c  test    eax, eax
0x180063f7e  jns     short loc_180063F8A
0x180063f80  mov     edi, 0Ah
0x180063f85  jmp     loc_180064161
0x180063f8a  mov     rcx, cs:KeyHandle
0x180063f91  lea     r8, [rbp+P]
0x180063f95  lea     rdx, [rbp+KeyHandle]
0x180063f99  call    BipCreateKey
0x180063f9e  mov     ebx, eax
0x180063fa0  test    eax, eax
0x180063fa2  jns     short loc_180063FAE
0x180063fa4  mov     edi, 14h
0x180063fa9  jmp     loc_180064161
0x180063fae  lea     rdx, aBrokerid; "BrokerId"
0x180063fb5  lea     rcx, [rbp+ValueName]; DestinationString
0x180063fb9  call    cs:__imp_RtlInitUnicodeString
0x180063fbf  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180063fc3  lea     r8, [rsi+80h]; Guid
0x180063fca  lea     rdx, [rbp+ValueName]; ValueName
0x180063fce  call    BipWriteRegGuid
0x180063fd3  mov     ebx, eax
0x180063fd5  test    eax, eax
0x180063fd7  jns     short loc_180063FE3
0x180063fd9  mov     edi, 1Eh
0x180063fde  jmp     loc_180064161
0x180063fe3  lea     rcx, [rbp+ValueName]; DestinationString
0x180063fe7  lea     rdx, aEventinformati; "EventInformation"
0x180063fee  test    edi, edi
0x180063ff0  jz      short loc_180063FF9
0x180063ff2  lea     rdx, aEventparameter; "EventParameters"
0x180063ff9  call    cs:__imp_RtlInitUnicodeString
0x180063fff  mov     r9d, [rsi+318h]; DataSize
0x180064006  lea     r8, [rsi+31Ch]; Data
0x18006400d  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180064011  lea     rdx, [rbp+ValueName]; ValueName
0x180064015  call    BipWriteRegBinary
0x18006401a  mov     ebx, eax
0x18006401c  test    eax, eax
0x18006401e  jns     short loc_18006402A
0x180064020  mov     edi, 28h ; '('
0x180064025  jmp     loc_180064161
0x18006402a  lea     rdx, aFlags; "Flags"
0x180064031  lea     rcx, [rbp+ValueName]; DestinationString
0x180064035  call    cs:__imp_RtlInitUnicodeString
0x18006403b  mov     r8d, [rsi+18h]
0x18006403f  lea     rdx, [rbp+ValueName]; ValueName
0x180064043  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180064047  and     r8d, 1FFFFFFFh
0x18006404e  call    BipWriteRegUlong
0x180064053  mov     ebx, eax
0x180064055  test    eax, eax
0x180064057  jns     short loc_180064063
0x180064059  mov     edi, 32h ; '2'
0x18006405e  jmp     loc_180064161
0x180064063  test    dword ptr [rsi+18h], 20000000h
0x18006406a  jz      short loc_1800640A1
0x18006406c  lea     rdx, aEventtype; "EventType"
0x180064073  lea     rcx, [rbp+ValueName]; DestinationString
0x180064077  call    cs:__imp_RtlInitUnicodeString
0x18006407d  mov     r8d, [rsi+244h]
0x180064084  lea     rdx, [rbp+ValueName]; ValueName
0x180064088  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18006408c  call    BipWriteRegUlong
0x180064091  mov     ebx, eax
0x180064093  test    eax, eax
0x180064095  jns     short loc_1800640A1
0x180064097  mov     edi, 3Ch ; '<'
0x18006409c  jmp     loc_180064161
0x1800640a1  lea     rdi, [rsi+0C0h]
0x1800640a8  cmp     [rdi], r14w
0x1800640ac  jz      short loc_1800640EA
0x1800640ae  lea     rdx, aPackagefullnam; "PackageFullName"
0x1800640b5  lea     rcx, [rbp+ValueName]; DestinationString
0x1800640b9  call    cs:__imp_RtlInitUnicodeString
0x1800640bf  mov     rdx, rdi; SourceString
0x1800640c2  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800640c6  call    cs:__imp_RtlInitUnicodeString
0x1800640cc  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1800640d0  lea     r8, [rbp+DestinationString]
0x1800640d4  lea     rdx, [rbp+ValueName]; ValueName
0x1800640d8  call    BipWriteRegUnicodeString
0x1800640dd  mov     ebx, eax
0x1800640df  test    eax, eax
0x1800640e1  jns     short loc_1800640EA
0x1800640e3  mov     edi, 46h ; 'F'
0x1800640e8  jmp     short loc_180064161
0x1800640ea  cmp     [rsi+0A8h], r14
0x1800640f1  jz      short loc_180064125
0x1800640f3  lea     rdx, aUsersid; "UserSid"
0x1800640fa  lea     rcx, [rbp+ValueName]; DestinationString
0x1800640fe  call    cs:__imp_RtlInitUnicodeString
0x180064104  mov     r8, [rsi+0A8h]; Data
0x18006410b  lea     rdx, [rbp+ValueName]; ValueName
0x18006410f  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180064113  call    BipWriteRegSid
0x180064118  mov     ebx, eax
0x18006411a  test    eax, eax
0x18006411c  jns     short loc_180064125
0x18006411e  mov     edi, 50h ; 'P'
0x180064123  jmp     short loc_180064161
0x180064125  cmp     [rsi+0B0h], r14
0x18006412c  jz      short loc_18006415E
0x18006412e  lea     rdx, aForusersid; "ForUserSid"
0x180064135  lea     rcx, [rbp+ValueName]; DestinationString
0x180064139  call    cs:__imp_RtlInitUnicodeString
0x18006413f  mov     r8, [rsi+0B0h]; Data
0x180064146  lea     rdx, [rbp+ValueName]; ValueName
0x18006414a  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18006414e  call    BipWriteRegSid
0x180064153  mov     ebx, eax
0x180064155  mov     edi, 5Ah ; 'Z'
0x18006415a  test    eax, eax
0x18006415c  js      short loc_180064161
0x18006415e  mov     edi, r14d
0x180064161  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x180064165  test    rcx, rcx
0x180064168  jz      short loc_18006417E
0x18006416a  test    ebx, ebx
0x18006416c  jns     short loc_180064178
0x18006416e  call    cs:__imp_NtDeleteKey
0x180064174  mov     rcx, [rbp+KeyHandle]; Handle
0x180064178  call    cs:__imp_NtClose
0x18006417e  mov     r8, [rbp+P+8]; P
0x180064182  test    r8, r8
0x180064185  jz      short loc_180064196
0x180064187  mov     rcx, cs:BipHeap; HeapHandle
0x18006418e  xor     edx, edx; Flags
0x180064190  call    cs:__imp_RtlFreeHeap
0x180064196  mov     eax, cs:dword_1800C3098
0x18006419c  cmp     eax, 4
0x18006419f  jbe     short loc_1800641F2
0x1800641a1  mov     edx, 2
0x1800641a6  lea     rcx, dword_1800C3098
0x1800641ad  call    _tlgKeywordOn
0x1800641b2  test    al, al
0x1800641b4  jz      short loc_1800641F2
0x1800641b6  lea     rax, [rsi+20h]
0x1800641ba  mov     dword ptr [rbp+arg_10], edi
0x1800641bd  mov     [rbp+var_38], rax
0x1800641c1  lea     rdx, byte_1800B507D
0x1800641c8  lea     rax, [rbp+arg_10]
0x1800641cc  mov     [rbp+arg_18], ebx
0x1800641cf  mov     [rsp+80h+var_50], rax
0x1800641d4  lea     rcx, dword_1800C3098
0x1800641db  lea     rax, [rbp+arg_18]
0x1800641df  mov     [rsp+80h+var_58], rax
0x1800641e4  lea     rax, [rbp+var_38]
0x1800641e8  mov     [rsp+80h+var_60], rax
0x1800641ed  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800641f2  lea     r11, [rsp+80h+var_s0]
0x1800641fa  mov     eax, ebx
0x1800641fc  mov     rbx, [r11+20h]
0x180064200  mov     rsi, [r11+28h]
0x180064204  mov     rsp, r11
0x180064207  pop     r14
0x180064209  pop     rdi
0x18006420a  pop     rbp
0x18006420b  retn
```
