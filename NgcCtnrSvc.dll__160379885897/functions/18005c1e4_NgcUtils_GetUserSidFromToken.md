# NgcUtils::GetUserSidFromToken

- ea: `0x18005c1e4`
- end: `0x18005c3b6`
- name: `NgcUtils::GetUserSidFromToken`
- size: `466`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018818`
- `0x18005b394`

## callees

- `0x180018194`
- `0x180019b68`
- `0x180024c4c`
- `0x18002d518`
- `0x180037c34`
- `0x18005c1e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c233`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c2bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c233`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005c2bf`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005c31a`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18005c31a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005c223`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005c2af`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005c223`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005c2af`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18005c387`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18005c387`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcUtils::GetUserSidFromToken(__int64 a1, PSID *a2)
{
  signed int v3; // ebx
  DWORD LastError; // eax
  DWORD LengthSid; // eax
  DWORD v6; // r14d
  char *v7; // rdx
  char *v8; // rsi
  unsigned __int64 v9; // rcx
  size_t v10; // rbx
  LPVOID TokenInformation[4]; // [rsp+30h] [rbp-20h] BYREF
  DWORD TokenInformationLength; // [rsp+70h] [rbp+20h] BYREF
  int v14; // [rsp+74h] [rbp+24h]
  DWORD v15; // [rsp+80h] [rbp+30h] BYREF

  v14 = HIDWORD(a1);
  TokenInformationLength = 0;
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenUser, 0, 0, &TokenInformationLength)
    || (v3 = GetLastError(), v3 == 122) )
  {
    std::vector<unsigned char>::vector<unsigned char>(TokenInformation, TokenInformationLength);
    if ( GetTokenInformation(
           (HANDLE)0xFFFFFFFFFFFFFFFALL,
           TokenUser,
           TokenInformation[0],
           TokenInformationLength,
           &TokenInformationLength) )
    {
      LengthSid = GetLengthSid(*(PSID *)TokenInformation[0]);
      v6 = LengthSid;
      v7 = (char *)*a2;
      v8 = (char *)a2[1];
      v9 = v8 - (_BYTE *)*a2;
      if ( LengthSid >= v9 )
      {
        if ( LengthSid > v9 )
        {
          if ( LengthSid <= (unsigned __int64)((_BYTE *)a2[2] - v7) )
          {
            v10 = LengthSid - v9;
            memset_0(a2[1], 0, v10);
            a2[1] = &v8[v10];
          }
          else
          {
            std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(a2, LengthSid);
          }
        }
      }
      else
      {
        a2[1] = &v7[LengthSid];
      }
      CopySid(v6, *a2, *(PSID *)TokenInformation[0]);
      v3 = 0;
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( (unsigned int)dword_1800BE0B8 > 2 )
      {
        v15 = LastError;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_1800BE0B8,
          (unsigned __int8 *)byte_1800AE50B,
          0,
          0,
          (__int64)&v15);
      }
      if ( v3 > 0 )
        v3 = (unsigned __int16)v3 | 0x80070000;
    }
    std::vector<unsigned char>::_Tidy(TokenInformation);
  }
  else
  {
    if ( (unsigned int)dword_1800BE0B8 > 2 )
    {
      v15 = v3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_1800BE0B8,
        (unsigned __int8 *)&word_1800AE536,
        0,
        0,
        (__int64)&v15);
    }
    if ( v3 > 0 )
      return (unsigned __int16)v3 | 0x80070000;
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18005c1e4  mov     r11, rsp
0x18005c1e7  mov     [r11+10h], rbx
0x18005c1eb  mov     [r11+20h], rsi
0x18005c1ef  mov     [r11+8], rcx
0x18005c1f3  push    rbp
0x18005c1f4  push    rdi
0x18005c1f5  push    r14
0x18005c1f7  mov     rbp, rsp
0x18005c1fa  sub     rsp, 50h
0x18005c1fe  mov     rdi, rdx
0x18005c201  mov     [rbp+TokenInformationLength], 0
0x18005c208  lea     rax, [rbp+TokenInformationLength]
0x18005c20c  mov     [r11-48h], rax
0x18005c210  xor     r9d, r9d; TokenInformationLength
0x18005c213  xor     r8d, r8d; TokenInformation
0x18005c216  lea     esi, [r9+1]
0x18005c21a  mov     edx, esi; TokenInformationClass
0x18005c21c  lea     r14, [r9-6]
0x18005c220  mov     rcx, r14; TokenHandle
0x18005c223  call    cs:__imp_GetTokenInformation
0x18005c22a  nop     dword ptr [rax+rax+00h]
0x18005c22f  test    eax, eax
0x18005c231  jnz     short loc_18005C28C
0x18005c233  call    cs:__imp_GetLastError
0x18005c23a  nop     dword ptr [rax+rax+00h]
0x18005c23f  mov     ebx, eax
0x18005c241  cmp     eax, 7Ah ; 'z'
0x18005c244  jz      short loc_18005C28C
0x18005c246  mov     eax, cs:dword_1800BE0B8
0x18005c24c  cmp     eax, 2
0x18005c24f  jbe     short loc_18005C276
0x18005c251  mov     [rbp+arg_10], ebx
0x18005c254  lea     rax, [rbp+arg_10]
0x18005c258  mov     [rsp+50h+ReturnLength], rax
0x18005c25d  xor     r9d, r9d
0x18005c260  xor     r8d, r8d
0x18005c263  lea     rdx, word_1800AE536
0x18005c26a  lea     rcx, dword_1800BE0B8
0x18005c271  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18005c276  test    ebx, ebx
0x18005c278  jle     loc_18005C39E
0x18005c27e  movzx   ebx, bx
0x18005c281  or      ebx, 80070000h
0x18005c287  jmp     loc_18005C39E
0x18005c28c  mov     edx, [rbp+TokenInformationLength]
0x18005c28f  lea     rcx, [rbp+TokenInformation]
0x18005c293  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18005c298  nop
0x18005c299  lea     rax, [rbp+TokenInformationLength]
0x18005c29d  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x18005c2a2  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18005c2a6  mov     r8, [rbp+TokenInformation]; TokenInformation
0x18005c2aa  mov     edx, esi; TokenInformationClass
0x18005c2ac  mov     rcx, r14; TokenHandle
0x18005c2af  call    cs:__imp_GetTokenInformation
0x18005c2b6  nop     dword ptr [rax+rax+00h]
0x18005c2bb  test    eax, eax
0x18005c2bd  jnz     short loc_18005C313
0x18005c2bf  call    cs:__imp_GetLastError
0x18005c2c6  nop     dword ptr [rax+rax+00h]
0x18005c2cb  mov     ebx, eax
0x18005c2cd  mov     ecx, cs:dword_1800BE0B8
0x18005c2d3  cmp     ecx, 2
0x18005c2d6  jbe     short loc_18005C2FD
0x18005c2d8  mov     [rbp+arg_10], eax
0x18005c2db  lea     rax, [rbp+arg_10]
0x18005c2df  mov     [rsp+50h+ReturnLength], rax
0x18005c2e4  xor     r9d, r9d
0x18005c2e7  xor     r8d, r8d
0x18005c2ea  lea     rdx, byte_1800AE50B
0x18005c2f1  lea     rcx, dword_1800BE0B8
0x18005c2f8  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18005c2fd  test    ebx, ebx
0x18005c2ff  jle     loc_18005C395
0x18005c305  movzx   ebx, bx
0x18005c308  or      ebx, 80070000h
0x18005c30e  jmp     loc_18005C395
0x18005c313  mov     rcx, [rbp+TokenInformation]
0x18005c317  mov     rcx, [rcx]; pSid
0x18005c31a  call    cs:__imp_GetLengthSid
0x18005c321  nop     dword ptr [rax+rax+00h]
0x18005c326  mov     r14d, eax
0x18005c329  mov     rdx, [rdi]
0x18005c32c  mov     rsi, [rdi+8]
0x18005c330  mov     rcx, rsi
0x18005c333  sub     rcx, rdx
0x18005c336  mov     ebx, eax
0x18005c338  cmp     r14, rcx
0x18005c33b  jnb     short loc_18005C347
0x18005c33d  lea     rcx, [r14+rdx]
0x18005c341  mov     [rdi+8], rcx
0x18005c345  jmp     short loc_18005C37A
0x18005c347  jbe     short loc_18005C37A
0x18005c349  mov     rax, [rdi+10h]
0x18005c34d  sub     rax, rdx
0x18005c350  cmp     rbx, rax
0x18005c353  jbe     short loc_18005C362
0x18005c355  mov     rdx, rbx
0x18005c358  mov     rcx, rdi
0x18005c35b  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18005c360  jmp     short loc_18005C37A
0x18005c362  sub     rbx, rcx
0x18005c365  mov     r8, rbx; Size
0x18005c368  xor     edx, edx; Val
0x18005c36a  mov     rcx, rsi; void *
0x18005c36d  call    memset_0
0x18005c372  lea     rax, [rbx+rsi]
0x18005c376  mov     [rdi+8], rax
0x18005c37a  mov     r8, [rbp+TokenInformation]
0x18005c37e  mov     r8, [r8]; pSourceSid
0x18005c381  mov     rdx, [rdi]; pDestinationSid
0x18005c384  mov     ecx, r14d; nDestinationSidLength
0x18005c387  call    cs:__imp_CopySid
0x18005c38e  nop     dword ptr [rax+rax+00h]
0x18005c393  xor     ebx, ebx
0x18005c395  lea     rcx, [rbp+TokenInformation]
0x18005c399  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18005c39e  mov     eax, ebx
0x18005c3a0  lea     r11, [rsp+50h+var_s0]
0x18005c3a5  mov     rbx, [r11+28h]
0x18005c3a9  mov     rsi, [r11+38h]
0x18005c3ad  mov     rsp, r11
0x18005c3b0  pop     r14
0x18005c3b2  pop     rdi
0x18005c3b3  pop     rbp
0x18005c3b4  retn
```
