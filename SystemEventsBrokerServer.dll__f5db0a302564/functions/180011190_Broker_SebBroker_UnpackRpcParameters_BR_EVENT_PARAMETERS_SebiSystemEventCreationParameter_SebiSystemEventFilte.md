# Broker::SebBroker::UnpackRpcParameters(_BR_EVENT_PARAMETERS *,_SebiSystemEventCreationParameter &,_SebiSystemEventFilterParameter &)

- ea: `0x180011190`
- end: `0x1800114dc`
- name: `?UnpackRpcParameters@SebBroker@Broker@@CAXPEAU_BR_EVENT_PARAMETERS@@AEAU_SebiSystemEventCreationParameter@@AEAU_SebiSystemEventFilterParameter@@@Z`
- size: `844`
- prototype: `void __fastcall(struct _BR_EVENT_PARAMETERS *, struct _SebiSystemEventCreationParameter *, struct _SebiSystemEventFilterParameter *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180010560`

## callees

- `0x180005a50`
- `0x180011190`
- `0x180013c40`
- `0x18001a5dc`
- `0x18001a7dc`
- `0x18001cf50`
- `0x18001d9ac`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180011253`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001144b`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180011253`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001144b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800112bd`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800112bd`

## pseudocode

```c
void __fastcall Broker::SebBroker::UnpackRpcParameters(
        struct _BR_EVENT_PARAMETERS *a1,
        struct _SebiSystemEventCreationParameter *a2,
        struct _SebiSystemEventFilterParameter *a3)
{
  unsigned int v6; // esi
  int v7; // ebx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  unsigned int v11; // edx
  _DWORD *v12; // rcx
  unsigned int v13; // r8d
  unsigned int v14; // r9d
  int v15; // edx
  int v16; // eax
  unsigned int v17; // [rsp+30h] [rbp-49h] BYREF
  _DWORD v18[3]; // [rsp+34h] [rbp-45h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR pExceptionObject; // [rsp+50h] [rbp-29h] BYREF
  char *v21; // [rsp+60h] [rbp-19h]
  int v22; // [rsp+68h] [rbp-11h]
  int v23; // [rsp+6Ch] [rbp-Dh]
  _DWORD *v24; // [rsp+70h] [rbp-9h]
  __int64 v25; // [rsp+78h] [rbp-1h]
  unsigned int *v26; // [rsp+80h] [rbp+7h]
  __int64 v27; // [rsp+88h] [rbp+Fh]

  if ( (unsigned int)dword_180035050 > 4 )
  {
    *(_DWORD *)&EventDescriptor.Level = 260;
    pExceptionObject.Ptr = (ULONGLONG)off_180035058;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    pExceptionObject.Size = *(unsigned __int16 *)off_180035058;
    v21 = byte_18002DE81;
    pExceptionObject.Reserved = 2;
    v22 = 34;
    v23 = 1;
    v17 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 2u, &pExceptionObject);
  }
  v6 = 0;
  v17 = 0;
  if ( !*(_WORD *)a1 || *((_QWORD *)a1 + 1) )
  {
    *(_OWORD *)a2 = 0;
    *((_QWORD *)a2 + 2) = 0;
    if ( *(_WORD *)a1 == 1 && CompareStringW(0x7Fu, 1u, **((PCNZWCH **)a1 + 1), -1, L"EventInformation", -1) == 2 )
    {
      v8 = *((_QWORD *)a1 + 1);
      if ( *(_DWORD *)(v8 + 8) == 4 && *(_WORD *)(v8 + 16) >= 0x18u )
      {
        v9 = *(_QWORD *)(v8 + 24);
        *(_OWORD *)a2 = *(_OWORD *)v9;
        *((_QWORD *)a2 + 2) = *(_QWORD *)(v9 + 16);
        v10 = *((_QWORD *)a1 + 1);
        v11 = *(unsigned __int16 *)(v10 + 16);
        if ( v11 > 0x18 )
        {
          v12 = (_DWORD *)(*(_QWORD *)(v10 + 24) + 24LL);
          if ( *(_QWORD *)(v10 + 24) == -24
            || (v13 = v11 - 24,
                !a3
             || v13 < 8
             || *v12 != 1
             || (v14 = *((_DWORD *)a2 + 2), *(_DWORD *)a3 = 1, v15 = v12[1], (unsigned int)(v15 - 1) > 0xFFF)
             || (*((_DWORD *)a3 + 1) = v15, v15 != v13 - 8)) )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 100, &WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids);
            Broker::InvalidParameter::InvalidParameter((Broker::InvalidParameter *)&pExceptionObject);
            throw (Broker::InvalidParameter *)&pExceptionObject;
          }
          *((_QWORD *)a3 + 1) = v12 + 2;
          Broker::SebBroker::ValidateFilterParameters(v14, a3);
        }
        v7 = 0;
      }
      else
      {
        v6 = 2;
        v7 = -1073741811;
      }
    }
    else
    {
      v16 = Broker::SebParametersHelper::UnpackSebEventParameters(a1, a2, a3, &v17);
      v6 = v17;
      v7 = v16;
    }
  }
  else
  {
    v6 = 1;
    v7 = -1073741811;
  }
  if ( (unsigned int)dword_180035050 > 4 )
  {
    v17 = v6;
    v26 = &v17;
    v18[0] = v7;
    v24 = v18;
    *(_DWORD *)&EventDescriptor.Level = 516;
    pExceptionObject.Ptr = (ULONGLONG)off_180035058;
    v27 = 4;
    v25 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    pExceptionObject.Size = *(unsigned __int16 *)off_180035058;
    v21 = byte_18002DE3D;
    pExceptionObject.Reserved = 2;
    v22 = 56;
    v23 = 1;
    v18[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &pExceptionObject);
  }
  if ( v7 == -1073741811 )
  {
    Broker::InvalidParameter::InvalidParameter((Broker::InvalidParameter *)&pExceptionObject);
    throw (Broker::InvalidParameter *)&pExceptionObject;
  }
}

```

## disassembly

```asm
0x180011190  mov     [rsp-8+arg_18], rbx
0x180011195  push    rbp
0x180011196  push    rsi
0x180011197  push    rdi
0x180011198  push    r12
0x18001119a  push    r13
0x18001119c  push    r14
0x18001119e  push    r15
0x1800111a0  lea     rbp, [rsp-27h]
0x1800111a5  sub     rsp, 0A0h
0x1800111ac  mov     rax, cs:__security_cookie
0x1800111b3  xor     rax, rsp
0x1800111b6  mov     [rbp+57h+var_40], rax
0x1800111ba  mov     eax, cs:dword_180035050
0x1800111c0  lea     r15, _TraceLoggingMetadataEnd
0x1800111c7  xor     r12d, r12d
0x1800111ca  lea     r13, _TraceLoggingMetadata
0x1800111d1  mov     rdi, r8
0x1800111d4  mov     r14, rdx
0x1800111d7  mov     rbx, rcx
0x1800111da  cmp     eax, 4
0x1800111dd  jbe     short loc_180011259
0x1800111df  movzx   eax, cs:word_18002DE77
0x1800111e6  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x1800111ea  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x1800111ed  xor     r9d, r9d; RelatedActivityId
0x1800111f0  mov     rax, cs:off_180035058
0x1800111f7  xor     r8d, r8d; ActivityId
0x1800111fa  mov     [rbp+57h+pExceptionObject.Ptr], rax
0x1800111fe  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180011205  mov     [rbp+57h+EventDescriptor.Keyword], r12
0x180011209  movzx   eax, word ptr [rax]
0x18001120c  mov     [rbp+57h+pExceptionObject.Size], eax
0x18001120f  lea     rax, byte_18002DE81
0x180011216  mov     [rbp+57h+var_70], rax
0x18001121a  mov     rax, r15
0x18001121d  sub     eax, r13d
0x180011220  mov     dword ptr [rbp+57h+pExceptionObject.0Ch], 2
0x180011227  mov     [rbp+57h+var_68], 22h ; '"'
0x18001122e  mov     [rbp+57h+var_64], 1
0x180011235  mov     [rbp+57h+var_A0], eax
0x180011238  mov     eax, [rbp+57h+var_A0]
0x18001123b  mov     rcx, cs:RegHandle; RegHandle
0x180011242  lea     rax, [rbp+57h+pExceptionObject]
0x180011246  mov     [rsp+0D0h+UserData], rax; UserData
0x18001124b  mov     [rsp+0D0h+UserDataCount], 2; UserDataCount
0x180011253  call    cs:__imp_EventWriteTransfer
0x180011259  mov     esi, r12d
0x18001125c  mov     [rbp+57h+var_A0], r12d
0x180011260  cmp     [rbx], r12w
0x180011264  jz      short loc_18001127B
0x180011266  cmp     [rbx+8], rsi
0x18001126a  jnz     short loc_18001127B
0x18001126c  mov     esi, 1
0x180011271  mov     ebx, 0C000000Dh
0x180011276  jmp     loc_1800113A4
0x18001127b  xor     eax, eax
0x18001127d  xorps   xmm0, xmm0
0x180011280  movups  xmmword ptr [r14], xmm0
0x180011284  mov     [r14+10h], rax
0x180011288  cmp     word ptr [rbx], 1
0x18001128c  jnz     loc_18001138D
0x180011292  mov     r8, [rbx+8]
0x180011296  lea     rax, aEventinformati; "EventInformation"
0x18001129d  mov     dword ptr [rsp+0D0h+UserData], 0FFFFFFFFh; cchCount2
0x1800112a5  mov     r9d, 0FFFFFFFFh; cchCount1
0x1800112ab  mov     edx, 1; dwCmpFlags
0x1800112b0  mov     qword ptr [rsp+0D0h+UserDataCount], rax; lpString2
0x1800112b5  mov     ecx, 7Fh; Locale
0x1800112ba  mov     r8, [r8]; lpString1
0x1800112bd  call    cs:__imp_CompareStringW
0x1800112c3  cmp     eax, 2
0x1800112c6  jnz     loc_18001138D
0x1800112cc  mov     rax, [rbx+8]
0x1800112d0  cmp     dword ptr [rax+8], 4
0x1800112d4  jnz     loc_180011381
0x1800112da  cmp     word ptr [rax+10h], 18h
0x1800112df  jb      loc_180011381
0x1800112e5  mov     rax, [rax+18h]
0x1800112e9  movups  xmm0, xmmword ptr [rax]
0x1800112ec  movups  xmmword ptr [r14], xmm0
0x1800112f0  movsd   xmm1, qword ptr [rax+10h]
0x1800112f5  movsd   qword ptr [r14+10h], xmm1
0x1800112fb  mov     rax, [rbx+8]
0x1800112ff  movzx   edx, word ptr [rax+10h]
0x180011303  cmp     edx, 18h
0x180011306  jbe     short loc_18001137C
0x180011308  mov     rcx, [rax+18h]
0x18001130c  add     rcx, 18h
0x180011310  jz      loc_180011480
0x180011316  mov     r8d, edx
0x180011319  add     r8d, 0FFFFFFE8h
0x18001131d  jz      loc_180011480
0x180011323  test    rdi, rdi
0x180011326  jz      loc_180011480
0x18001132c  cmp     r8d, 8
0x180011330  jb      loc_180011480
0x180011336  cmp     dword ptr [rcx], 1
0x180011339  jnz     loc_180011480
0x18001133f  mov     r9d, [r14+8]
0x180011343  mov     dword ptr [rdi], 1
0x180011349  mov     edx, [rcx+4]
0x18001134c  lea     eax, [rdx-1]
0x18001134f  cmp     eax, 0FFFh
0x180011354  ja      loc_180011480
0x18001135a  lea     eax, [r8-8]
0x18001135e  mov     [rdi+4], edx
0x180011361  cmp     edx, eax
0x180011363  jnz     loc_180011480
0x180011369  lea     rax, [rcx+8]
0x18001136d  mov     rdx, rdi
0x180011370  mov     ecx, r9d
0x180011373  mov     [rdi+8], rax
0x180011377  call    ?ValidateFilterParameters@SebBroker@Broker@@CAXW4_SebiEventType@@PEBU_SebiSystemEventFilterParameter@@@Z; Broker::SebBroker::ValidateFilterParameters(_SebiEventType,_SebiSystemEventFilterParameter const *)
0x18001137c  mov     ebx, r12d
0x18001137f  jmp     short loc_1800113A4
0x180011381  mov     esi, 2
0x180011386  mov     ebx, 0C000000Dh
0x18001138b  jmp     short loc_1800113A4
0x18001138d  lea     r9, [rbp+57h+var_A0]; unsigned int *
0x180011391  mov     r8, rdi; struct _SebiSystemEventFilterParameter *
0x180011394  mov     rdx, r14; struct _SebiSystemEventCreationParameter *
0x180011397  mov     rcx, rbx; struct _BR_EVENT_PARAMETERS *
0x18001139a  call    ?UnpackSebEventParameters@SebParametersHelper@Broker@@SAJPEAU_BR_EVENT_PARAMETERS@@AEAU_SebiSystemEventCreationParameter@@AEAU_SebiSystemEventFilterParameter@@AEAK@Z; Broker::SebParametersHelper::UnpackSebEventParameters(_BR_EVENT_PARAMETERS *,_SebiSystemEventCreationParameter &,_SebiSystemEventFilterParameter &,ulong &)
0x18001139f  mov     esi, [rbp+57h+var_A0]
0x1800113a2  mov     ebx, eax
0x1800113a4  mov     ecx, cs:dword_180035050
0x1800113aa  cmp     ecx, 4
0x1800113ad  jbe     loc_180011451
0x1800113b3  mov     [rbp+57h+var_A0], esi
0x1800113b6  lea     rax, [rbp+57h+var_A0]
0x1800113ba  mov     [rbp+57h+var_50], rax
0x1800113be  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x1800113c2  lea     rax, [rbp+57h+var_9C]
0x1800113c6  mov     [rbp+57h+var_9C], ebx
0x1800113c9  mov     [rbp+57h+var_60], rax
0x1800113cd  sub     r15d, r13d
0x1800113d0  movzx   eax, cs:word_18002DE33
0x1800113d7  xor     r9d, r9d; RelatedActivityId
0x1800113da  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x1800113dd  xor     r8d, r8d; ActivityId
0x1800113e0  mov     rax, cs:off_180035058
0x1800113e7  mov     [rbp+57h+pExceptionObject.Ptr], rax
0x1800113eb  mov     [rbp+57h+var_48], 4
0x1800113f3  mov     [rbp+57h+var_58], 4
0x1800113fb  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180011402  mov     [rbp+57h+EventDescriptor.Keyword], r12
0x180011406  movzx   eax, word ptr [rax]
0x180011409  mov     [rbp+57h+pExceptionObject.Size], eax
0x18001140c  lea     rax, byte_18002DE3D
0x180011413  mov     [rbp+57h+var_70], rax
0x180011417  mov     dword ptr [rbp+57h+pExceptionObject.0Ch], 2
0x18001141e  mov     [rbp+57h+var_68], 38h ; '8'
0x180011425  mov     [rbp+57h+var_64], 1
0x18001142c  mov     [rbp+57h+var_98], r15d
0x180011430  mov     eax, [rbp+57h+var_98]
0x180011433  mov     rcx, cs:RegHandle; RegHandle
0x18001143a  lea     rax, [rbp+57h+pExceptionObject]
0x18001143e  mov     [rsp+0D0h+UserData], rax; UserData
0x180011443  mov     [rsp+0D0h+UserDataCount], 4; UserDataCount
0x18001144b  call    cs:__imp_EventWriteTransfer
0x180011451  cmp     ebx, 0C000000Dh
0x180011457  jz      short loc_1800114C2
0x180011459  mov     rcx, [rbp+57h+var_40]
0x18001145d  xor     rcx, rsp; StackCookie
0x180011460  call    __security_check_cookie
0x180011465  mov     rbx, [rsp+0D0h+arg_18]
0x18001146d  add     rsp, 0A0h
0x180011474  pop     r15
0x180011476  pop     r14
0x180011478  pop     r13
0x18001147a  pop     r12
0x18001147c  pop     rdi
0x18001147d  pop     rsi
0x18001147e  pop     rbp
0x18001147f  retn
0x180011480  mov     rcx, cs:WPP_GLOBAL_Control
0x180011487  test    byte ptr [rcx+1Ch], 1
0x18001148b  jz      short loc_1800114A8
0x18001148d  cmp     byte ptr [rcx+19h], 2
0x180011491  jb      short loc_1800114A8
0x180011493  mov     rcx, [rcx+10h]
0x180011497  lea     r8, WPP_f4c36fec5d693f0683c6af84739b0b39_Traceguids
0x18001149e  mov     edx, 64h ; 'd'
0x1800114a3  call    WPP_SF_
0x1800114a8  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800114ac  call    ??0InvalidParameter@Broker@@QEAA@XZ; Broker::InvalidParameter::InvalidParameter(void)
0x1800114b1  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x1800114b8  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800114bc  call    _CxxThrowException_0
0x1800114c2  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800114c6  call    ??0InvalidParameter@Broker@@QEAA@XZ; Broker::InvalidParameter::InvalidParameter(void)
0x1800114cb  lea     rdx, _TI3?AUInvalidParameter@Broker@@; pThrowInfo
0x1800114d2  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800114d6  call    _CxxThrowException_0
```
