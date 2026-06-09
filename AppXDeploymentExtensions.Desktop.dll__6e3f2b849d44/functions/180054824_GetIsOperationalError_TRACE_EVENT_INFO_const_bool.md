# GetIsOperationalError(_TRACE_EVENT_INFO * const,bool *)

- ea: `0x180054824`
- end: `0x180054af7`
- name: `?GetIsOperationalError@@YAJQEAU_TRACE_EVENT_INFO@@PEA_N@Z`
- size: `723`
- prototype: `__int64 __fastcall(LPGUID pGuid, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180094e98`

## callees

- `0x180012fc8`
- `0x18004c55c`
- `0x180054824`
- `0x1800840f4`
- `0x1800af1bc`
- `0x1800af6f8`
- `0x1800ba5fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180054a6a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180054a6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800549f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054a42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054a76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800549f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054a42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180054a76`
- `api-ms-win-eventing-tdh-l1-1-0!TdhEnumerateProviderFieldInformation` at `0x180054886`
- `api-ms-win-eventing-tdh-l1-1-0!TdhEnumerateProviderFieldInformation` at `0x1800548bb`
- `api-ms-win-eventing-tdh-l1-1-0!TdhEnumerateProviderFieldInformation` at `0x180054886`
- `api-ms-win-eventing-tdh-l1-1-0!TdhEnumerateProviderFieldInformation` at `0x1800548bb`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtOpenChannelConfig` at `0x1800549a8`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtOpenChannelConfig` at `0x1800549a8`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtGetChannelConfigProperty` at `0x1800549e2`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtGetChannelConfigProperty` at `0x180054a32`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtGetChannelConfigProperty` at `0x1800549e2`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtGetChannelConfigProperty` at `0x180054a32`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x180054abe`
- `ext-ms-win-wevtapi-eventlog-l1-1-0!EvtClose` at `0x180054abe`

## pseudocode

```c
__int64 __fastcall GetIsOperationalError(LPGUID pGuid, const struct std::nothrow_t *a2)
{
  struct _EVT_VARIANT *v4; // rsi
  EVT_HANDLE v5; // rbx
  PROVIDER_FIELD_INFOARRAY *v6; // rdi
  signed int v7; // r14d
  const struct std::nothrow_t *v8; // rdx
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
  const struct std::nothrow_t *v22; // rdx
  int PropertyValueBuffer; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  ULONG pBufferSize; // [rsp+78h] [rbp+10h] BYREF
  DWORD PropertyValueBufferSize; // [rsp+80h] [rbp+18h] BYREF
  unsigned __int16 *v28; // [rsp+88h] [rbp+20h]

  if ( !a2 || !pGuid )
    return 2147942487LL;
  PropertyValueBufferSize = 0;
  v4 = 0;
  v5 = 0;
  v6 = 0;
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
      if ( v7 > 0 )
      {
        v7 = (unsigned __int16)v7;
LABEL_10:
        v7 |= 0x80070000;
      }
    }
    else
    {
      v9 = (unsigned __int16 *)((char *)pGuid + *(unsigned int *)&pGuid[3].Data4[4]);
      v10 = StripInvalidCharsFromEvtChannelName(v9);
      v11 = retaddr;
      v7 = v10;
      if ( v10 >= 0 )
      {
        for ( i = 0; ; ++i )
        {
          if ( i >= v6->NumberOfElements )
            goto LABEL_39;
          DescriptionOffset = v6->FieldInfoArray[i].DescriptionOffset;
          if ( (_DWORD)DescriptionOffset )
          {
            v28 = (unsigned __int16 *)((char *)v6 + DescriptionOffset);
            v16 = StripInvalidCharsFromEvtChannelName((unsigned __int16 *)((char *)v6 + DescriptionOffset));
            v11 = retaddr;
            v7 = v16;
            if ( v16 < 0 )
            {
              v12 = (unsigned int)v16;
              v13 = 714;
              goto LABEL_38;
            }
            v17 = -1;
            do
              ++v17;
            while ( v9[v17] );
            v18 = -1;
            do
              ++v18;
            while ( v28[v18] );
            if ( Common::String::Equals(v28, v18, v9, v17) )
              break;
          }
        }
        v19 = (const WCHAR *)((char *)v6 + v6->FieldInfoArray[i].NameOffset);
        if ( v19 )
        {
          if ( (unsigned __int8)IsEvtOpenChannelConfigPresent() )
          {
            v5 = EvtOpenChannelConfig(0, v19, 0);
            if ( v5 )
            {
              if ( EvtGetChannelConfigProperty(v5, EvtChannelConfigType, 0, 0, 0, &PropertyValueBufferSize) )
                goto LABEL_33;
              LastError = GetLastError();
              if ( LastError != 122 )
                goto LABEL_30;
              v21 = PropertyValueBufferSize;
              v4 = (struct _EVT_VARIANT *)operator new[](PropertyValueBufferSize);
              if ( EvtGetChannelConfigProperty(v5, EvtChannelConfigType, 0, v21, v4, &PropertyValueBufferSize) )
              {
LABEL_33:
                *(_BYTE *)a2 = v4->BooleanVal;
                goto LABEL_40;
              }
              LastError = GetLastError();
LABEL_30:
              if ( LastError <= 0 )
              {
                if ( LastError )
                {
                  v7 = LastError;
                  goto LABEL_40;
                }
                goto LABEL_33;
              }
LABEL_36:
              v7 = (unsigned __int16)LastError;
              goto LABEL_10;
            }
          }
          else
          {
            SetLastError(0x32u);
          }
          LastError = GetLastError();
          v7 = LastError;
          if ( LastError <= 0 )
            goto LABEL_40;
          goto LABEL_36;
        }
LABEL_39:
        v7 = -2147467259;
      }
      else
      {
        v12 = (unsigned int)v10;
        v13 = 706;
LABEL_38:
        wil::details::in1diag3::_Log_Hr(
          v11,
          (void *)v13,
          (unsigned int)"onecore\\admin\\appmodel\\packagemanager\\logging\\appxlog.cpp",
          (const char *)v12,
          PropertyValueBuffer);
      }
    }
  }
  else
  {
    v7 = 0;
    *(_BYTE *)a2 = 0;
  }
LABEL_40:
  operator delete(v6, a2);
  if ( v5 )
    EvtClose(v5);
  if ( v4 )
    operator delete(v4, v22);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180054824  mov     rax, rsp
0x180054827  mov     [rax+8], rbx
0x18005482b  push    rbp
0x18005482c  push    rsi
0x18005482d  push    rdi
0x18005482e  push    r12
0x180054830  push    r13
0x180054832  push    r14
0x180054834  push    r15
0x180054836  sub     rsp, 30h
0x18005483a  xor     r15d, r15d
0x18005483d  mov     r13, rdx
0x180054840  mov     rbp, rcx
0x180054843  test    rdx, rdx
0x180054846  jz      loc_180054ADC
0x18005484c  test    rcx, rcx
0x18005484f  jz      loc_180054ADC
0x180054855  lea     r12d, [r15+2]
0x180054859  mov     [rax+18h], r15d
0x18005485d  mov     esi, r15d
0x180054860  mov     ebx, r15d
0x180054863  mov     edi, r15d
0x180054866  mov     [rax+10h], r15d
0x18005486a  cmp     [rcx+24h], r12b
0x18005486e  jz      short loc_18005487B
0x180054870  mov     r14d, r15d
0x180054873  mov     [rdx], r15b
0x180054876  jmp     loc_180054AAE
0x18005487b  lea     r9, [rsp+68h+pBufferSize]; pBufferSize
0x180054880  xor     r8d, r8d; pBuffer
0x180054883  mov     edx, r12d; EventFieldType
0x180054886  call    cs:__imp_TdhEnumerateProviderFieldInformation
0x18005488d  nop     dword ptr [rax+rax+00h]
0x180054892  mov     r14d, eax
0x180054895  cmp     eax, 7Ah ; 'z'
0x180054898  jnz     short loc_1800548CA
0x18005489a  mov     ecx, [rsp+68h+pBufferSize]; unsigned __int64
0x18005489e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800548a3  xor     ecx, ecx; void *
0x1800548a5  mov     rdi, rax
0x1800548a8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800548ad  lea     r9, [rsp+68h+pBufferSize]; pBufferSize
0x1800548b2  mov     r8, rdi; pBuffer
0x1800548b5  mov     edx, r12d; EventFieldType
0x1800548b8  mov     rcx, rbp; pGuid
0x1800548bb  call    cs:__imp_TdhEnumerateProviderFieldInformation
0x1800548c2  nop     dword ptr [rax+rax+00h]
0x1800548c7  mov     r14d, eax
0x1800548ca  test    r14d, r14d
0x1800548cd  jz      short loc_1800548E5
0x1800548cf  jle     loc_180054AAE
0x1800548d5  movzx   r14d, r14w
0x1800548d9  or      r14d, 80070000h
0x1800548e0  jmp     loc_180054AAE
0x1800548e5  mov     r12d, [rbp+3Ch]
0x1800548e9  add     r12, rbp
0x1800548ec  mov     rcx, r12; unsigned __int16 *
0x1800548ef  call    ?StripInvalidCharsFromEvtChannelName@@YAJPEAG@Z; StripInvalidCharsFromEvtChannelName(ushort *)
0x1800548f4  mov     rcx, [rsp+68h]
0x1800548f9  mov     r14d, eax
0x1800548fc  test    eax, eax
0x1800548fe  jns     short loc_18005490D
0x180054900  mov     r9d, eax
0x180054903  mov     edx, 2C2h
0x180054908  jmp     loc_180054A9A
0x18005490d  mov     ebp, r15d
0x180054910  cmp     ebp, [rdi]
0x180054912  jnb     loc_180054AA8
0x180054918  mov     r15d, ebp
0x18005491b  add     r15, r15
0x18005491e  mov     eax, [rdi+r15*8+0Ch]
0x180054923  test    eax, eax
0x180054925  jz      short loc_18005497E
0x180054927  add     rax, rdi
0x18005492a  mov     rcx, rax; unsigned __int16 *
0x18005492d  mov     [rsp+68h+arg_18], rax
0x180054935  call    ?StripInvalidCharsFromEvtChannelName@@YAJPEAG@Z; StripInvalidCharsFromEvtChannelName(ushort *)
0x18005493a  mov     rcx, [rsp+68h]; this
0x18005493f  mov     r14d, eax
0x180054942  xor     eax, eax
0x180054944  test    r14d, r14d
0x180054947  js      loc_180054A92
0x18005494d  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180054951  mov     r9, rcx
0x180054954  inc     r9; unsigned int
0x180054957  cmp     [r12+r9*2], ax
0x18005495c  jnz     short loc_180054954
0x18005495e  mov     rdx, rcx
0x180054961  mov     rcx, [rsp+68h+arg_18]; unsigned __int16 *
0x180054969  inc     rdx; unsigned int
0x18005496c  cmp     [rcx+rdx*2], ax
0x180054970  jnz     short loc_180054969
0x180054972  mov     r8, r12; unsigned __int16 *
0x180054975  call    ?Equals@String@Common@@SAHPEBGK0K@Z; Common::String::Equals(ushort const *,ulong,ushort const *,ulong)
0x18005497a  test    eax, eax
0x18005497c  jnz     short loc_180054982
0x18005497e  inc     ebp
0x180054980  jmp     short loc_180054910
0x180054982  mov     ebp, [rdi+r15*8+8]
0x180054987  xor     r15d, r15d
0x18005498a  add     rbp, rdi
0x18005498d  jz      loc_180054AA8
0x180054993  call    IsEvtOpenChannelConfigPresent
0x180054998  test    al, al
0x18005499a  jz      loc_180054A65
0x1800549a0  xor     r8d, r8d; Flags
0x1800549a3  mov     rdx, rbp; ChannelPath
0x1800549a6  xor     ecx, ecx; Session
0x1800549a8  call    cs:__imp_EvtOpenChannelConfig
0x1800549af  nop     dword ptr [rax+rax+00h]
0x1800549b4  mov     rbx, rax
0x1800549b7  test    rax, rax
0x1800549ba  jz      loc_180054A76
0x1800549c0  lea     rax, [rsp+68h+PropertyValueBufferSize]
0x1800549c8  xor     r9d, r9d; PropertyValueBufferSize
0x1800549cb  mov     [rsp+68h+PropertyValueBufferUsed], rax; PropertyValueBufferUsed
0x1800549d0  lea     r12d, [r15+2]
0x1800549d4  mov     edx, r12d; PropertyId
0x1800549d7  mov     [rsp+68h+PropertyValueBuffer], r15; PropertyValueBuffer
0x1800549dc  xor     r8d, r8d; Flags
0x1800549df  mov     rcx, rbx; ChannelConfig
0x1800549e2  call    cs:__imp_EvtGetChannelConfigProperty
0x1800549e9  nop     dword ptr [rax+rax+00h]
0x1800549ee  test    eax, eax
0x1800549f0  jnz     short loc_180054A59
0x1800549f2  call    cs:__imp_GetLastError
0x1800549f9  nop     dword ptr [rax+rax+00h]
0x1800549fe  cmp     eax, 7Ah ; 'z'
0x180054a01  jnz     short loc_180054A4E
0x180054a03  mov     ebp, [rsp+68h+PropertyValueBufferSize]
0x180054a0a  mov     ecx, ebp; unsigned __int64
0x180054a0c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180054a11  mov     rsi, rax
0x180054a14  mov     r9d, ebp; PropertyValueBufferSize
0x180054a17  lea     rax, [rsp+68h+PropertyValueBufferSize]
0x180054a1f  xor     r8d, r8d; Flags
0x180054a22  mov     [rsp+68h+PropertyValueBufferUsed], rax; PropertyValueBufferUsed
0x180054a27  mov     edx, r12d; PropertyId
0x180054a2a  mov     rcx, rbx; ChannelConfig
0x180054a2d  mov     [rsp+68h+PropertyValueBuffer], rsi; PropertyValueBuffer
0x180054a32  call    cs:__imp_EvtGetChannelConfigProperty
0x180054a39  nop     dword ptr [rax+rax+00h]
0x180054a3e  test    eax, eax
0x180054a40  jnz     short loc_180054A59
0x180054a42  call    cs:__imp_GetLastError
0x180054a49  nop     dword ptr [rax+rax+00h]
0x180054a4e  test    eax, eax
0x180054a50  jg      short loc_180054A89
0x180054a52  jz      short loc_180054A59
0x180054a54  mov     r14d, eax
0x180054a57  jmp     short loc_180054AAE
0x180054a59  cmp     dword ptr [rsi], 1
0x180054a5c  setz    al
0x180054a5f  mov     [r13+0], al
0x180054a63  jmp     short loc_180054AAE
0x180054a65  mov     ecx, 32h ; '2'; dwErrCode
0x180054a6a  call    cs:__imp_SetLastError
0x180054a71  nop     dword ptr [rax+rax+00h]
0x180054a76  call    cs:__imp_GetLastError
0x180054a7d  nop     dword ptr [rax+rax+00h]
0x180054a82  mov     r14d, eax
0x180054a85  test    eax, eax
0x180054a87  jle     short loc_180054AAE
0x180054a89  movzx   r14d, ax
0x180054a8d  jmp     loc_1800548D9
0x180054a92  mov     r9d, r14d; char *
0x180054a95  mov     edx, 2CAh; void *
0x180054a9a  lea     r8, aOnecoreAdminAp_107; "onecore\\admin\\appmodel\\packagemanage"...
0x180054aa1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180054aa6  jmp     short loc_180054AAE
0x180054aa8  mov     r14d, 80004005h
0x180054aae  mov     rcx, rdi; void *
0x180054ab1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180054ab6  test    rbx, rbx
0x180054ab9  jz      short loc_180054ACA
0x180054abb  mov     rcx, rbx; Object
0x180054abe  call    cs:__imp_EvtClose
0x180054ac5  nop     dword ptr [rax+rax+00h]
0x180054aca  test    rsi, rsi
0x180054acd  jz      short loc_180054AD7
0x180054acf  mov     rcx, rsi; void *
0x180054ad2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180054ad7  mov     eax, r14d
0x180054ada  jmp     short loc_180054AE1
0x180054adc  mov     eax, 80070057h
0x180054ae1  mov     rbx, [rsp+68h+arg_0]
0x180054ae6  add     rsp, 30h
0x180054aea  pop     r15
0x180054aec  pop     r14
0x180054aee  pop     r13
0x180054af0  pop     r12
0x180054af2  pop     rdi
0x180054af3  pop     rsi
0x180054af4  pop     rbp
0x180054af5  retn
```
