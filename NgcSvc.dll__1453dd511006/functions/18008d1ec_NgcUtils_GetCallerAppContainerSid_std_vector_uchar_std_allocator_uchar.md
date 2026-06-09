# NgcUtils::GetCallerAppContainerSid(std::vector<uchar,std::allocator<uchar>> *)

- ea: `0x18008d1ec`
- end: `0x18008d338`
- name: `?GetCallerAppContainerSid@NgcUtils@@YAJPEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `332`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002dc90`
- `0x180081680`

## callees

- `0x180010990`
- `0x180022b00`
- `0x180028ca0`
- `0x180028d18`
- `0x18008d1ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d226`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d2b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d226`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008d2b0`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18008d2fe`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18008d2fe`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18008d318`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18008d318`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008d21c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008d2a6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008d21c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18008d2a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcUtils::GetCallerAppContainerSid(PSID *a1)
{
  signed int LastError; // ebx
  PSID *v3; // rdi
  DWORD LengthSid; // ebx
  LPVOID TokenInformation[4]; // [rsp+30h] [rbp-20h] BYREF
  DWORD TokenInformationLength; // [rsp+78h] [rbp+28h] BYREF
  signed int v8; // [rsp+80h] [rbp+30h] BYREF

  TokenInformationLength = 0;
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenAppContainerSid, 0, 0, &TokenInformationLength)
    || (LastError = GetLastError(), LastError == 122) )
  {
    std::vector<unsigned char>::vector<unsigned char>(TokenInformation, TokenInformationLength);
    v3 = (PSID *)TokenInformation[0];
    if ( GetTokenInformation(
           (HANDLE)0xFFFFFFFFFFFFFFFALL,
           TokenAppContainerSid,
           TokenInformation[0],
           TokenInformationLength,
           &TokenInformationLength) )
    {
      LengthSid = GetLengthSid(*v3);
      std::vector<unsigned char>::_Resize<std::_Value_init_tag>(a1, LengthSid);
      CopySid(LengthSid, *a1, *v3);
      LastError = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( (unsigned int)dword_180122070 > 2 )
      {
        v8 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (__int64)&dword_180122070,
          (unsigned __int8 *)byte_1801075AD,
          0,
          0,
          (__int64)&v8);
      }
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    std::vector<unsigned char>::_Tidy(TokenInformation);
  }
  else
  {
    if ( (unsigned int)dword_180122070 > 2 )
    {
      v8 = LastError;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)word_180107582,
        0,
        0,
        (__int64)&v8);
    }
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18008d1ec  mov     [rsp-18h+arg_0], rbx
0x18008d1f1  push    rbp
0x18008d1f2  push    rsi
0x18008d1f3  push    rdi
0x18008d1f4  mov     rbp, rsp
0x18008d1f7  sub     rsp, 50h
0x18008d1fb  mov     rsi, rcx
0x18008d1fe  mov     [rbp+TokenInformationLength], 0
0x18008d205  lea     rax, [rbp+TokenInformationLength]
0x18008d209  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x18008d20e  xor     r9d, r9d; TokenInformationLength
0x18008d211  xor     r8d, r8d; TokenInformation
0x18008d214  lea     edx, [r9+1Fh]; TokenInformationClass
0x18008d218  lea     rcx, [r9-6]; TokenHandle
0x18008d21c  call    cs:__imp_GetTokenInformation
0x18008d222  test    eax, eax
0x18008d224  jnz     short loc_18008D279
0x18008d226  call    cs:__imp_GetLastError
0x18008d22c  mov     ebx, eax
0x18008d22e  cmp     eax, 7Ah ; 'z'
0x18008d231  jz      short loc_18008D279
0x18008d233  mov     eax, cs:dword_180122070
0x18008d239  cmp     eax, 2
0x18008d23c  jbe     short loc_18008D263
0x18008d23e  mov     [rbp+arg_10], ebx
0x18008d241  lea     rax, [rbp+arg_10]
0x18008d245  mov     [rsp+50h+ReturnLength], rax
0x18008d24a  xor     r9d, r9d
0x18008d24d  xor     r8d, r8d
0x18008d250  lea     rdx, word_180107582
0x18008d257  lea     rcx, dword_180122070
0x18008d25e  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18008d263  test    ebx, ebx
0x18008d265  jle     loc_18008D329
0x18008d26b  movzx   ebx, bx
0x18008d26e  or      ebx, 80070000h
0x18008d274  jmp     loc_18008D329
0x18008d279  mov     edx, [rbp+TokenInformationLength]
0x18008d27c  lea     rcx, [rbp+TokenInformation]
0x18008d280  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18008d285  nop
0x18008d286  lea     rax, [rbp+TokenInformationLength]
0x18008d28a  mov     [rsp+50h+ReturnLength], rax; ReturnLength
0x18008d28f  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18008d293  mov     rdi, [rbp+TokenInformation]
0x18008d297  mov     r8, rdi; TokenInformation
0x18008d29a  mov     edx, 1Fh; TokenInformationClass
0x18008d29f  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x18008d2a6  call    cs:__imp_GetTokenInformation
0x18008d2ac  test    eax, eax
0x18008d2ae  jnz     short loc_18008D2FB
0x18008d2b0  call    cs:__imp_GetLastError
0x18008d2b6  mov     ebx, eax
0x18008d2b8  mov     ecx, cs:dword_180122070
0x18008d2be  cmp     ecx, 2
0x18008d2c1  jbe     short loc_18008D2EC
0x18008d2c3  mov     [rbp+arg_10], 0
0x18008d2ca  lea     rax, [rbp+arg_10]
0x18008d2ce  mov     [rsp+50h+ReturnLength], rax
0x18008d2d3  xor     r9d, r9d
0x18008d2d6  xor     r8d, r8d
0x18008d2d9  lea     rdx, byte_1801075AD
0x18008d2e0  lea     rcx, dword_180122070
0x18008d2e7  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18008d2ec  test    ebx, ebx
0x18008d2ee  jle     short loc_18008D320
0x18008d2f0  movzx   ebx, bx
0x18008d2f3  or      ebx, 80070000h
0x18008d2f9  jmp     short loc_18008D320
0x18008d2fb  mov     rcx, [rdi]; pSid
0x18008d2fe  call    cs:__imp_GetLengthSid
0x18008d304  mov     ebx, eax
0x18008d306  mov     edx, eax
0x18008d308  mov     rcx, rsi
0x18008d30b  call    ??$_Resize@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18008d310  mov     r8, [rdi]; pSourceSid
0x18008d313  mov     rdx, [rsi]; pDestinationSid
0x18008d316  mov     ecx, ebx; nDestinationSidLength
0x18008d318  call    cs:__imp_CopySid
0x18008d31e  xor     ebx, ebx
0x18008d320  lea     rcx, [rbp+TokenInformation]
0x18008d324  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18008d329  mov     eax, ebx
0x18008d32b  mov     rbx, [rsp+50h+arg_0]
0x18008d330  add     rsp, 50h
0x18008d334  pop     rdi
0x18008d335  pop     rsi
0x18008d336  pop     rbp
0x18008d337  retn
```
