# GetIsOperationalError(_TRACE_EVENT_INFO * const,bool *)

- ea: `0x18007cba4`
- end: `0x18007ce80`
- name: `?GetIsOperationalError@@YAJQEAU_TRACE_EVENT_INFO@@PEA_N@Z`
- size: `732`
- prototype: `__int64 __fastcall(LPGUID pGuid, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18008c100`

## callees

- `0x1800490c0`
- `0x180071f50`
- `0x18007cba4`
- `0x18007ce88`
- `0x18007cefc`
- `0x1800992c4`
- `0x18009d3c4`
- `0x18009dddc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cd90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cde0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ce03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cd90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007cde0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007ce03`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007cd49`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007cd49`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtOpenChannelConfig` at `0x18007cd2b`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtOpenChannelConfig` at `0x18007cd2b`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtGetChannelConfigProperty` at `0x18007cd80`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtGetChannelConfigProperty` at `0x18007cdd0`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtGetChannelConfigProperty` at `0x18007cd80`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtGetChannelConfigProperty` at `0x18007cdd0`
- `api-ms-win-eventing-tdh-l1-1-0!TdhEnumerateProviderFieldInformation` at `0x18007cc0d`
- `api-ms-win-eventing-tdh-l1-1-0!TdhEnumerateProviderFieldInformation` at `0x18007cc48`
- `api-ms-win-eventing-tdh-l1-1-0!TdhEnumerateProviderFieldInformation` at `0x18007cc0d`
- `api-ms-win-eventing-tdh-l1-1-0!TdhEnumerateProviderFieldInformation` at `0x18007cc48`

## pseudocode

```c
__int64 __fastcall GetIsOperationalError(LPGUID pGuid, bool *a2)
{
  struct _EVT_VARIANT *v4; // rsi
  EVT_HANDLE v5; // rdi
  PROVIDER_FIELD_INFOARRAY *v6; // rbx
  signed int v7; // r14d
  unsigned __int64 v8; // rdx
  unsigned __int16 *v9; // r12
  int v10; // eax
  wil::details::in1diag3 *v11; // rcx
  unsigned __int64 v12; // r9
  __int64 v13; // rdx
  ULONG i; // ebp
  __int64 DescriptionOffset; // rax
  int v16; // eax
  __int64 v17; // r9
  __int64 v18; // rdx
  const WCHAR *v19; // rbp
  signed int LastError; // eax
  DWORD v21; // ebp
  unsigned __int64 v22; // rdx
  int PropertyValueBuffer; // [rsp+20h] [rbp-58h]
  unsigned __int16 *v25; // [rsp+30h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  ULONG pBufferSize; // [rsp+88h] [rbp+10h] BYREF
  DWORD PropertyValueBufferSize; // [rsp+90h] [rbp+18h] BYREF
  EVT_HANDLE v29; // [rsp+98h] [rbp+20h] BYREF

  if ( !a2 || !pGuid )
    return 2147942487LL;
  v29 = 0;
  v4 = 0;
  v5 = 0;
  v6 = 0;
  PropertyValueBufferSize = 0;
  pBufferSize = 0;
  if ( LOBYTE(pGuid[2].Data2) == 2 )
  {
    v7 = TdhEnumerateProviderFieldInformation(pGuid, EventChannelInformation, 0, &pBufferSize);
    if ( v7 == 122 )
    {
      v6 = (PROVIDER_FIELD_INFOARRAY *)operator new[](pBufferSize);
      operator delete(0, v8);
      v7 = TdhEnumerateProviderFieldInformation(pGuid, EventChannelInformation, v6, &pBufferSize);
    }
    if ( v7 )
    {
      if ( v7 <= 0 )
        goto LABEL_41;
      v7 = (unsigned __int16)v7;
    }
    else
    {
      v9 = (unsigned __int16 *)((char *)pGuid + *(unsigned int *)&pGuid[3].Data4[4]);
      v10 = StripInvalidCharsFromEvtChannelName(v9);
      v11 = retaddr;
      v7 = v10;
      if ( v10 < 0 )
      {
        v12 = (unsigned int)v10;
        v13 = 706;
LABEL_39:
        wil::details::in1diag3::_Log_Hr(
          v11,
          (void *)v13,
          (unsigned int)"onecore\\admin\\appmodel\\packagemanager\\logging\\appxlog.cpp",
          (const char *)v12,
          PropertyValueBuffer);
        goto LABEL_41;
      }
      for ( i = 0; ; ++i )
      {
        if ( i >= v6->NumberOfElements )
          goto LABEL_40;
        DescriptionOffset = v6->FieldInfoArray[i].DescriptionOffset;
        if ( (_DWORD)DescriptionOffset )
        {
          v25 = (unsigned __int16 *)((char *)v6 + DescriptionOffset);
          v16 = StripInvalidCharsFromEvtChannelName((unsigned __int16 *)((char *)v6 + DescriptionOffset));
          v11 = retaddr;
          v7 = v16;
          if ( v16 < 0 )
          {
            v12 = (unsigned int)v16;
            v13 = 714;
            goto LABEL_39;
          }
          v17 = -1;
          do
            ++v17;
          while ( v9[v17] );
          v18 = -1;
          do
            ++v18;
          while ( v25[v18] );
          if ( Common::String::Equals(v25, v18, v9, v17) )
            break;
        }
      }
      v19 = (const WCHAR *)((char *)v6 + v6->FieldInfoArray[i].NameOffset);
      if ( !v19 )
      {
LABEL_40:
        v7 = -2147467259;
        goto LABEL_41;
      }
      if ( (unsigned __int8)IsEvtOpenChannelConfigPresent() )
      {
        v5 = EvtOpenChannelConfig(0, v19, 0);
        v29 = v5;
      }
      else
      {
        SetLastError(0x32u);
      }
      if ( v5 )
      {
        if ( EvtGetChannelConfigProperty(v5, EvtChannelConfigType, 0, 0, 0, &PropertyValueBufferSize) )
          goto LABEL_35;
        LastError = GetLastError();
        if ( LastError != 122 )
          goto LABEL_32;
        v21 = PropertyValueBufferSize;
        v4 = (struct _EVT_VARIANT *)operator new[](PropertyValueBufferSize);
        if ( EvtGetChannelConfigProperty(v5, EvtChannelConfigType, 0, v21, v4, &PropertyValueBufferSize) )
          goto LABEL_35;
        LastError = GetLastError();
LABEL_32:
        if ( !LastError )
        {
LABEL_35:
          *a2 = v4->BooleanVal;
          goto LABEL_41;
        }
        if ( LastError <= 0 )
        {
          v7 = LastError;
          goto LABEL_41;
        }
      }
      else
      {
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError <= 0 )
          goto LABEL_41;
      }
      v7 = (unsigned __int16)LastError;
    }
    v7 |= 0x80070000;
    goto LABEL_41;
  }
  v7 = 0;
  *a2 = 0;
LABEL_41:
  operator delete(v6, (unsigned __int64)a2);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int EvtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int EvtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v29);
  if ( v4 )
    operator delete(v4, v22);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18007cba4  mov     rax, rsp
0x18007cba7  mov     [rax+8], rbx
0x18007cbab  push    rbp
0x18007cbac  push    rsi
0x18007cbad  push    rdi
0x18007cbae  push    r12
0x18007cbb0  push    r13
0x18007cbb2  push    r14
0x18007cbb4  push    r15
0x18007cbb6  sub     rsp, 40h
0x18007cbba  xor     r15d, r15d
0x18007cbbd  mov     r13, rdx
0x18007cbc0  mov     rbp, rcx
0x18007cbc3  test    rdx, rdx
0x18007cbc6  jz      loc_18007CE62
0x18007cbcc  test    rcx, rcx
0x18007cbcf  jz      loc_18007CE62
0x18007cbd5  lea     r12d, [r15+2]
0x18007cbd9  mov     [rax+20h], r15
0x18007cbdd  mov     esi, r15d
0x18007cbe0  mov     edi, r15d
0x18007cbe3  mov     ebx, r15d
0x18007cbe6  mov     [rax+18h], r15d
0x18007cbea  mov     [rax+10h], r15d
0x18007cbee  cmp     [rcx+24h], r12b
0x18007cbf2  jz      short loc_18007CBFF
0x18007cbf4  mov     r14d, r15d
0x18007cbf7  mov     [rdx], r15b
0x18007cbfa  jmp     loc_18007CE3B
0x18007cbff  lea     r9, [rsp+78h+pBufferSize]; pBufferSize
0x18007cc07  xor     r8d, r8d; pBuffer
0x18007cc0a  mov     edx, r12d; EventFieldType
0x18007cc0d  call    cs:__imp_TdhEnumerateProviderFieldInformation
0x18007cc14  nop     dword ptr [rax+rax+00h]
0x18007cc19  mov     r14d, eax
0x18007cc1c  cmp     eax, 7Ah ; 'z'
0x18007cc1f  jnz     short loc_18007CC57
0x18007cc21  mov     ecx, [rsp+78h+pBufferSize]; unsigned __int64
0x18007cc28  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18007cc2d  xor     ecx, ecx; void *
0x18007cc2f  mov     rbx, rax
0x18007cc32  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18007cc37  lea     r9, [rsp+78h+pBufferSize]; pBufferSize
0x18007cc3f  mov     r8, rbx; pBuffer
0x18007cc42  mov     edx, r12d; EventFieldType
0x18007cc45  mov     rcx, rbp; pGuid
0x18007cc48  call    cs:__imp_TdhEnumerateProviderFieldInformation
0x18007cc4f  nop     dword ptr [rax+rax+00h]
0x18007cc54  mov     r14d, eax
0x18007cc57  test    r14d, r14d
0x18007cc5a  jz      short loc_18007CC72
0x18007cc5c  jle     loc_18007CE3B
0x18007cc62  movzx   r14d, r14w
0x18007cc66  or      r14d, 80070000h
0x18007cc6d  jmp     loc_18007CE3B
0x18007cc72  mov     r12d, [rbp+3Ch]
0x18007cc76  add     r12, rbp
0x18007cc79  mov     rcx, r12; unsigned __int16 *
0x18007cc7c  call    ?StripInvalidCharsFromEvtChannelName@@YAJPEAG@Z; StripInvalidCharsFromEvtChannelName(ushort *)
0x18007cc81  mov     rcx, [rsp+78h]
0x18007cc86  mov     r14d, eax
0x18007cc89  test    eax, eax
0x18007cc8b  jns     short loc_18007CC9A
0x18007cc8d  mov     r9d, eax
0x18007cc90  mov     edx, 2C2h
0x18007cc95  jmp     loc_18007CE27
0x18007cc9a  mov     ebp, r15d
0x18007cc9d  cmp     ebp, [rbx]
0x18007cc9f  jnb     loc_18007CE35
0x18007cca5  mov     r15d, ebp
0x18007cca8  add     r15, r15
0x18007ccab  mov     eax, [rbx+r15*8+0Ch]
0x18007ccb0  test    eax, eax
0x18007ccb2  jz      short loc_18007CD05
0x18007ccb4  add     rax, rbx
0x18007ccb7  mov     rcx, rax; unsigned __int16 *
0x18007ccba  mov     [rsp+78h+var_48], rax
0x18007ccbf  call    ?StripInvalidCharsFromEvtChannelName@@YAJPEAG@Z; StripInvalidCharsFromEvtChannelName(ushort *)
0x18007ccc4  mov     rcx, [rsp+78h]; this
0x18007ccc9  mov     r14d, eax
0x18007cccc  xor     eax, eax
0x18007ccce  test    r14d, r14d
0x18007ccd1  js      loc_18007CE1F
0x18007ccd7  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18007ccdb  mov     r9, rcx
0x18007ccde  inc     r9; unsigned int
0x18007cce1  cmp     [r12+r9*2], ax
0x18007cce6  jnz     short loc_18007CCDE
0x18007cce8  mov     rdx, rcx
0x18007cceb  mov     rcx, [rsp+78h+var_48]; unsigned __int16 *
0x18007ccf0  inc     rdx; unsigned int
0x18007ccf3  cmp     [rcx+rdx*2], ax
0x18007ccf7  jnz     short loc_18007CCF0
0x18007ccf9  mov     r8, r12; unsigned __int16 *
0x18007ccfc  call    ?Equals@String@Common@@SAHPEBGK0K@Z; Common::String::Equals(ushort const *,ulong,ushort const *,ulong)
0x18007cd01  test    eax, eax
0x18007cd03  jnz     short loc_18007CD09
0x18007cd05  inc     ebp
0x18007cd07  jmp     short loc_18007CC9D
0x18007cd09  mov     ebp, [rbx+r15*8+8]
0x18007cd0e  xor     r15d, r15d
0x18007cd11  add     rbp, rbx
0x18007cd14  jz      loc_18007CE35
0x18007cd1a  call    IsEvtOpenChannelConfigPresent
0x18007cd1f  test    al, al
0x18007cd21  jz      short loc_18007CD44
0x18007cd23  xor     r8d, r8d; Flags
0x18007cd26  mov     rdx, rbp; ChannelPath
0x18007cd29  xor     ecx, ecx; Session
0x18007cd2b  call    cs:__imp_EvtOpenChannelConfig
0x18007cd32  nop     dword ptr [rax+rax+00h]
0x18007cd37  mov     rdi, rax
0x18007cd3a  mov     [rsp+78h+arg_18], rax
0x18007cd42  jmp     short loc_18007CD55
0x18007cd44  mov     ecx, 32h ; '2'; dwErrCode
0x18007cd49  call    cs:__imp_SetLastError
0x18007cd50  nop     dword ptr [rax+rax+00h]
0x18007cd55  test    rdi, rdi
0x18007cd58  jz      loc_18007CE03
0x18007cd5e  xor     r9d, r9d; PropertyValueBufferSize
0x18007cd61  lea     rax, [rsp+78h+PropertyValueBufferSize]
0x18007cd69  mov     [rsp+78h+PropertyValueBufferUsed], rax; PropertyValueBufferUsed
0x18007cd6e  xor     r8d, r8d; Flags
0x18007cd71  mov     rcx, rdi; ChannelConfig
0x18007cd74  mov     [rsp+78h+PropertyValueBuffer], r15; PropertyValueBuffer
0x18007cd79  lea     r12d, [r9+2]
0x18007cd7d  mov     edx, r12d; PropertyId
0x18007cd80  call    cs:__imp_EvtGetChannelConfigProperty
0x18007cd87  nop     dword ptr [rax+rax+00h]
0x18007cd8c  test    eax, eax
0x18007cd8e  jnz     short loc_18007CDF7
0x18007cd90  call    cs:__imp_GetLastError
0x18007cd97  nop     dword ptr [rax+rax+00h]
0x18007cd9c  cmp     eax, 7Ah ; 'z'
0x18007cd9f  jnz     short loc_18007CDEC
0x18007cda1  mov     ebp, [rsp+78h+PropertyValueBufferSize]
0x18007cda8  mov     ecx, ebp; unsigned __int64
0x18007cdaa  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18007cdaf  mov     rsi, rax
0x18007cdb2  mov     r9d, ebp; PropertyValueBufferSize
0x18007cdb5  lea     rax, [rsp+78h+PropertyValueBufferSize]
0x18007cdbd  xor     r8d, r8d; Flags
0x18007cdc0  mov     [rsp+78h+PropertyValueBufferUsed], rax; PropertyValueBufferUsed
0x18007cdc5  mov     edx, r12d; PropertyId
0x18007cdc8  mov     rcx, rdi; ChannelConfig
0x18007cdcb  mov     [rsp+78h+PropertyValueBuffer], rsi; PropertyValueBuffer
0x18007cdd0  call    cs:__imp_EvtGetChannelConfigProperty
0x18007cdd7  nop     dword ptr [rax+rax+00h]
0x18007cddc  test    eax, eax
0x18007cdde  jnz     short loc_18007CDF7
0x18007cde0  call    cs:__imp_GetLastError
0x18007cde7  nop     dword ptr [rax+rax+00h]
0x18007cdec  test    eax, eax
0x18007cdee  jz      short loc_18007CDF7
0x18007cdf0  jg      short loc_18007CE16
0x18007cdf2  mov     r14d, eax
0x18007cdf5  jmp     short loc_18007CE3B
0x18007cdf7  cmp     dword ptr [rsi], 1
0x18007cdfa  setz    al
0x18007cdfd  mov     [r13+0], al
0x18007ce01  jmp     short loc_18007CE3B
0x18007ce03  call    cs:__imp_GetLastError
0x18007ce0a  nop     dword ptr [rax+rax+00h]
0x18007ce0f  mov     r14d, eax
0x18007ce12  test    eax, eax
0x18007ce14  jle     short loc_18007CE3B
0x18007ce16  movzx   r14d, ax
0x18007ce1a  jmp     loc_18007CC66
0x18007ce1f  mov     r9d, r14d; char *
0x18007ce22  mov     edx, 2CAh; void *
0x18007ce27  lea     r8, aOnecoreAdminAp; "onecore\\admin\\appmodel\\packagemanage"...
0x18007ce2e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18007ce33  jmp     short loc_18007CE3B
0x18007ce35  mov     r14d, 80004005h
0x18007ce3b  mov     rcx, rbx; void *
0x18007ce3e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18007ce43  lea     rcx, [rsp+78h+arg_18]
0x18007ce4b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?EvtClose@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&EvtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&EvtClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18007ce50  test    rsi, rsi
0x18007ce53  jz      short loc_18007CE5D
0x18007ce55  mov     rcx, rsi; void *
0x18007ce58  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18007ce5d  mov     eax, r14d
0x18007ce60  jmp     short loc_18007CE67
0x18007ce62  mov     eax, 80070057h
0x18007ce67  mov     rbx, [rsp+78h+arg_0]
0x18007ce6f  add     rsp, 40h
0x18007ce73  pop     r15
0x18007ce75  pop     r14
0x18007ce77  pop     r13
0x18007ce79  pop     r12
0x18007ce7b  pop     rdi
0x18007ce7c  pop     rsi
0x18007ce7d  pop     rbp
0x18007ce7e  retn
```
