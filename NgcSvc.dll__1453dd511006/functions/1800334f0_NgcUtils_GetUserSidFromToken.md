# NgcUtils::GetUserSidFromToken

- ea: `0x1800334f0`
- end: `0x180033981`
- name: `NgcUtils::GetUserSidFromToken`
- size: `1169`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18002dc90`
- `0x1800745dc`
- `0x1800748b0`
- `0x180083fe4`
- `0x18008f3b4`

## callees

- `0x1800334f0`
- `0x18004d408`
- `0x18005cee0`
- `0x18005d2b0`
- `0x18005d2ec`
- `0x18005dd38`
- `0x18005dd44`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033549`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800336b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033549`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800336b5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800335fa`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18003375d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1800335fa`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18003375d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800337be`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800337be`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18003390b`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x18003390b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003353b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800336a7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18003353b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800336a7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcUtils::GetUserSidFromToken(HANDLE TokenHandle, const void **a2)
{
  _QWORD *v4; // r12
  signed int v5; // ebx
  DWORD v7; // r9d
  size_t v8; // rsi
  char *v9; // rdi
  void *v10; // rax
  PSID *v11; // rbx
  int LastError; // esi
  unsigned __int64 v13; // rdi
  void *v14; // rcx
  DWORD LengthSid; // eax
  __int64 v16; // r15
  char *v17; // rsi
  char *v18; // rdx
  unsigned __int64 v19; // r13
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // rdx
  size_t v22; // rsi
  size_t v23; // rcx
  void *v24; // rax
  char *v25; // rax
  unsigned __int64 v26; // rdx
  void *v27; // rcx
  size_t v28; // r15
  unsigned __int64 v29; // rdi
  PSID *v30; // rcx
  DWORD nDestinationSidLength; // [rsp+30h] [rbp-39h] BYREF
  DWORD TokenInformationLength; // [rsp+34h] [rbp-35h] BYREF
  unsigned int v33; // [rsp+38h] [rbp-31h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-29h] BYREF
  char *v35; // [rsp+50h] [rbp-19h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+58h] [rbp-11h] BYREF
  __int16 *v37; // [rsp+68h] [rbp-1h]
  int v38; // [rsp+70h] [rbp+7h]
  int v39; // [rsp+74h] [rbp+Bh]
  DWORD *p_nDestinationSidLength; // [rsp+78h] [rbp+Fh]
  __int64 v41; // [rsp+80h] [rbp+17h]

  v4 = 0;
  TokenInformationLength = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) || (v5 = GetLastError(), v5 == 122) )
  {
    v7 = TokenInformationLength;
    v8 = TokenInformationLength;
    EventDescriptor = 0;
    v9 = 0;
    v35 = 0;
    if ( TokenInformationLength )
    {
      if ( TokenInformationLength < 0x1000uLL )
      {
        v11 = (PSID *)operator new(TokenInformationLength);
      }
      else
      {
        if ( (unsigned __int64)TokenInformationLength + 39 < TokenInformationLength )
          std::_Throw_bad_array_new_length();
        v10 = operator new(TokenInformationLength + 39LL);
        if ( !v10 )
          goto LABEL_55;
        v11 = (PSID *)(((unsigned __int64)v10 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v11 - 1) = v10;
      }
      *(_QWORD *)&EventDescriptor.Id = v11;
      v9 = (char *)v11 + v8;
      v35 = (char *)v11 + v8;
      memset_0(v11, 0, v8);
      EventDescriptor.Keyword = (ULONGLONG)v11 + v8;
      v7 = TokenInformationLength;
    }
    else
    {
      v11 = *(PSID **)&EventDescriptor.Id;
    }
    if ( !GetTokenInformation(TokenHandle, TokenUser, v11, v7, &TokenInformationLength) )
    {
      LastError = GetLastError();
      if ( (unsigned int)dword_180122070 > 2 )
      {
        nDestinationSidLength = LastError;
        p_nDestinationSidLength = &nDestinationSidLength;
        v41 = 4;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        *(_DWORD *)&EventDescriptor.Level = 2;
        EventDescriptor.Keyword = 0;
        UserData.Ptr = (ULONGLONG)off_180122078;
        UserData.Size = *(unsigned __int16 *)off_180122078;
        UserData.Reserved = 2;
        v37 = &word_18010760E;
        v38 = 31;
        v39 = 1;
        v33 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
      }
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( v11 )
      {
        v13 = v9 - (char *)v11;
        if ( v13 >= 0x1000 )
        {
          v14 = *(v11 - 1);
          if ( (unsigned __int64)((char *)v11 - (_BYTE *)v14 - 8) <= 0x1F )
          {
            operator delete(v14, v13 + 39);
            return (unsigned int)LastError;
          }
LABEL_55:
          __fastfail(5u);
        }
        operator delete(v11, v13);
      }
      return (unsigned int)LastError;
    }
    LengthSid = GetLengthSid(*v11);
    nDestinationSidLength = LengthSid;
    v16 = LengthSid;
    v17 = (char *)a2[1];
    v18 = (char *)*a2;
    v19 = v17 - (_BYTE *)*a2;
    if ( LengthSid < v19 )
    {
      a2[1] = &v18[LengthSid];
      goto LABEL_51;
    }
    if ( LengthSid > v19 )
    {
      v20 = (_BYTE *)a2[2] - v18;
      if ( LengthSid > v20 )
      {
        v21 = v20 >> 1;
        v22 = 0x7FFFFFFFFFFFFFFFLL;
        if ( v20 <= 0x7FFFFFFFFFFFFFFFLL - (v20 >> 1) )
        {
          v22 = v20 + v21;
          if ( v20 + v21 < LengthSid )
            v22 = LengthSid;
          if ( !v22 )
            goto LABEL_42;
          if ( v22 < 0x1000 )
          {
            v4 = operator new(v22);
            goto LABEL_42;
          }
          v23 = v22 + 39;
          if ( v22 + 39 < v22 )
            std::_Throw_bad_array_new_length();
        }
        else
        {
          v23 = 0x8000000000000026uLL;
        }
        v24 = operator new(v23);
        if ( !v24 )
          goto LABEL_46;
        v4 = (_QWORD *)(((unsigned __int64)v24 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v4 - 1) = v24;
LABEL_42:
        memset_0((char *)v4 + v19, 0, v16 - v19);
        memmove_0(v4, *a2, (_BYTE *)a2[1] - (_BYTE *)*a2);
        v25 = (char *)*a2;
        if ( !*a2 )
        {
LABEL_49:
          *a2 = v4;
          a2[1] = (char *)v4 + v16;
          a2[2] = (char *)v4 + v22;
          goto LABEL_51;
        }
        v26 = (_BYTE *)a2[2] - v25;
        if ( v26 < 0x1000 )
        {
          v27 = (void *)*a2;
          goto LABEL_48;
        }
        v27 = (void *)*((_QWORD *)v25 - 1);
        if ( (unsigned __int64)(v25 - (_BYTE *)v27 - 8) <= 0x1F )
        {
          v26 += 39LL;
LABEL_48:
          operator delete(v27, v26);
          goto LABEL_49;
        }
LABEL_46:
        __fastfail(5u);
      }
      v28 = LengthSid - v19;
      memset_0((void *)a2[1], 0, v28);
      a2[1] = &v17[v28];
    }
LABEL_51:
    CopySid(nDestinationSidLength, (PSID)*a2, *v11);
    if ( v11 )
    {
      v29 = v9 - (char *)v11;
      if ( v29 < 0x1000 )
      {
        v30 = v11;
      }
      else
      {
        v30 = (PSID *)*(v11 - 1);
        if ( (unsigned __int64)((char *)v11 - (char *)v30 - 8) > 0x1F )
          goto LABEL_55;
        v29 += 39LL;
      }
      operator delete(v30, v29);
    }
    return 0;
  }
  if ( (unsigned int)dword_180122070 > 2 )
  {
    v33 = v5;
    p_nDestinationSidLength = &v33;
    v41 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    *(_DWORD *)&EventDescriptor.Level = 2;
    EventDescriptor.Keyword = 0;
    UserData.Ptr = (ULONGLONG)off_180122078;
    UserData.Size = *(unsigned __int16 *)off_180122078;
    UserData.Reserved = 2;
    v37 = (__int16 *)byte_1801075E3;
    v38 = 31;
    v39 = 1;
    nDestinationSidLength = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  if ( v5 > 0 )
    return (unsigned __int16)v5 | 0x80070000;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800334f0  mov     [rsp-8+arg_10], rbx
0x1800334f5  push    rbp
0x1800334f6  push    rsi
0x1800334f7  push    rdi
0x1800334f8  push    r12
0x1800334fa  push    r13
0x1800334fc  push    r14
0x1800334fe  push    r15
0x180033500  lea     rbp, [rsp-27h]
0x180033505  sub     rsp, 90h
0x18003350c  mov     rax, cs:__security_cookie
0x180033513  xor     rax, rsp
0x180033516  mov     [rbp+57h+var_38], rax
0x18003351a  mov     r14, rdx
0x18003351d  mov     r15, rcx
0x180033520  xor     r12d, r12d
0x180033523  mov     [rbp+57h+TokenInformationLength], r12d
0x180033527  lea     rax, [rbp+57h+TokenInformationLength]
0x18003352b  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x180033530  xor     r9d, r9d; TokenInformationLength
0x180033533  xor     r8d, r8d; TokenInformation
0x180033536  mov     edx, 1; TokenInformationClass
0x18003353b  call    cs:__imp_GetTokenInformation
0x180033541  test    eax, eax
0x180033543  jnz     loc_180033614
0x180033549  call    cs:__imp_GetLastError
0x18003354f  mov     ebx, eax
0x180033551  cmp     eax, 7Ah ; 'z'
0x180033554  jz      loc_180033614
0x18003355a  mov     eax, cs:dword_180122070
0x180033560  cmp     eax, 2
0x180033563  jbe     loc_180033600
0x180033569  mov     [rbp+57h+var_88], ebx
0x18003356c  lea     rax, [rbp+57h+var_88]
0x180033570  mov     [rbp+57h+var_48], rax
0x180033574  mov     [rbp+57h+var_40], 4
0x18003357c  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180033583  movzx   eax, cs:word_1801075D9
0x18003358a  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18003358d  mov     [rbp+57h+EventDescriptor.Keyword], r12
0x180033591  mov     rax, cs:off_180122078
0x180033598  mov     [rbp+57h+var_68.Ptr], rax
0x18003359c  movzx   eax, word ptr [rax]
0x18003359f  mov     [rbp+57h+var_68.Size], eax
0x1800335a2  mov     dword ptr [rbp+57h+var_68.0Ch], 2
0x1800335a9  lea     rax, byte_1801075E3
0x1800335b0  mov     [rbp+57h+var_58], rax
0x1800335b4  mov     [rbp+57h+var_50], 1Fh
0x1800335bb  mov     [rbp+57h+var_4C], 1
0x1800335c2  lea     rax, _TraceLoggingMetadataEnd
0x1800335c9  lea     rcx, _TraceLoggingMetadata
0x1800335d0  sub     eax, ecx
0x1800335d2  mov     [rbp+57h+nDestinationSidLength], eax
0x1800335d5  mov     eax, [rbp+57h+nDestinationSidLength]
0x1800335d8  lea     rax, [rbp+57h+var_68]
0x1800335dc  mov     [rsp+0C0h+UserData], rax; UserData
0x1800335e1  mov     dword ptr [rsp+0C0h+ReturnLength], 3; UserDataCount
0x1800335e9  xor     r9d, r9d; RelatedActivityId
0x1800335ec  xor     r8d, r8d; ActivityId
0x1800335ef  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x1800335f3  mov     rcx, cs:RegHandle; RegHandle
0x1800335fa  call    cs:__imp_EventWriteTransfer
0x180033600  test    ebx, ebx
0x180033602  jle     short loc_18003360D
0x180033604  movzx   ebx, bx
0x180033607  or      ebx, 80070000h
0x18003360d  mov     eax, ebx
0x18003360f  jmp     loc_18003394E
0x180033614  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x180033618  mov     esi, r9d
0x18003361b  xorps   xmm0, xmm0
0x18003361e  movdqu  xmmword ptr [rbp+57h+EventDescriptor.Id], xmm0
0x180033623  mov     rdi, r12
0x180033626  mov     [rbp+57h+var_70], r12
0x18003362a  test    r9d, r9d
0x18003362d  jz      short loc_18003368F
0x18003362f  cmp     r9, 1000h
0x180033636  jb      short loc_180033661
0x180033638  lea     rcx, [r9+27h]; Size
0x18003363c  cmp     rcx, r9
0x18003363f  jbe     loc_180033975
0x180033645  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003364a  test    rax, rax
0x18003364d  jz      loc_18003393A
0x180033653  lea     rbx, [rax+27h]
0x180033657  and     rbx, 0FFFFFFFFFFFFFFE0h
0x18003365b  mov     [rbx-8], rax
0x18003365f  jmp     short loc_18003366C
0x180033661  mov     rcx, rsi; Size
0x180033664  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180033669  mov     rbx, rax
0x18003366c  mov     qword ptr [rbp+57h+EventDescriptor.Id], rbx
0x180033670  lea     rdi, [rbx+rsi]
0x180033674  mov     [rbp+57h+var_70], rdi
0x180033678  mov     r8, rsi; Size
0x18003367b  xor     edx, edx; Val
0x18003367d  mov     rcx, rbx; void *
0x180033680  call    memset_0
0x180033685  mov     [rbp+57h+EventDescriptor.Keyword], rdi
0x180033689  mov     r9d, [rbp+57h+TokenInformationLength]
0x18003368d  jmp     short loc_180033693
0x18003368f  mov     rbx, qword ptr [rbp+57h+EventDescriptor.Id]
0x180033693  lea     rax, [rbp+57h+TokenInformationLength]
0x180033697  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x18003369c  mov     r8, rbx; TokenInformation
0x18003369f  mov     edx, 1; TokenInformationClass
0x1800336a4  mov     rcx, r15; TokenHandle
0x1800336a7  call    cs:__imp_GetTokenInformation
0x1800336ad  test    eax, eax
0x1800336af  jnz     loc_1800337BB
0x1800336b5  call    cs:__imp_GetLastError
0x1800336bb  mov     esi, eax
0x1800336bd  mov     eax, cs:dword_180122070
0x1800336c3  cmp     eax, 2
0x1800336c6  jbe     loc_180033763
0x1800336cc  mov     [rbp+57h+nDestinationSidLength], esi
0x1800336cf  lea     rax, [rbp+57h+nDestinationSidLength]
0x1800336d3  mov     [rbp+57h+var_48], rax
0x1800336d7  mov     [rbp+57h+var_40], 4
0x1800336df  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x1800336e6  movzx   eax, cs:word_180107604
0x1800336ed  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x1800336f0  mov     [rbp+57h+EventDescriptor.Keyword], r12
0x1800336f4  mov     rax, cs:off_180122078
0x1800336fb  mov     [rbp+57h+var_68.Ptr], rax
0x1800336ff  movzx   eax, word ptr [rax]
0x180033702  mov     [rbp+57h+var_68.Size], eax
0x180033705  mov     dword ptr [rbp+57h+var_68.0Ch], 2
0x18003370c  lea     rax, word_18010760E
0x180033713  mov     [rbp+57h+var_58], rax
0x180033717  mov     [rbp+57h+var_50], 1Fh
0x18003371e  mov     [rbp+57h+var_4C], 1
0x180033725  lea     rax, _TraceLoggingMetadataEnd
0x18003372c  lea     rcx, _TraceLoggingMetadata
0x180033733  sub     eax, ecx
0x180033735  mov     [rbp+57h+var_88], eax
0x180033738  mov     eax, [rbp+57h+var_88]
0x18003373b  lea     rax, [rbp+57h+var_68]
0x18003373f  mov     [rsp+0C0h+UserData], rax; UserData
0x180033744  mov     dword ptr [rsp+0C0h+ReturnLength], 3; UserDataCount
0x18003374c  xor     r9d, r9d; RelatedActivityId
0x18003374f  xor     r8d, r8d; ActivityId
0x180033752  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180033756  mov     rcx, cs:RegHandle; RegHandle
0x18003375d  call    cs:__imp_EventWriteTransfer
0x180033763  test    esi, esi
0x180033765  jle     short loc_180033770
0x180033767  movzx   esi, si
0x18003376a  or      esi, 80070000h
0x180033770  test    rbx, rbx
0x180033773  jz      short loc_1800337B4
0x180033775  sub     rdi, rbx
0x180033778  cmp     rdi, 1000h
0x18003377f  jb      short loc_1800337A9
0x180033781  mov     rcx, [rbx-8]; void *
0x180033785  sub     rbx, rcx
0x180033788  sub     rbx, 8
0x18003378c  cmp     rbx, 1Fh
0x180033790  ja      loc_18003393A
0x180033796  add     rdi, 27h ; '''
0x18003379a  mov     rdx, rdi; unsigned __int64
0x18003379d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800337a2  mov     eax, esi
0x1800337a4  jmp     loc_18003394E
0x1800337a9  mov     rcx, rbx; void *
0x1800337ac  mov     rdx, rdi; unsigned __int64
0x1800337af  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800337b4  mov     eax, esi
0x1800337b6  jmp     loc_18003394E
0x1800337bb  mov     rcx, [rbx]; pSid
0x1800337be  call    cs:__imp_GetLengthSid
0x1800337c4  mov     [rbp+57h+nDestinationSidLength], eax
0x1800337c7  mov     r15d, eax
0x1800337ca  mov     rsi, [r14+8]
0x1800337ce  mov     rdx, [r14]
0x1800337d1  mov     r13, rsi
0x1800337d4  sub     r13, rdx
0x1800337d7  cmp     r15, r13
0x1800337da  jnb     short loc_1800337E9
0x1800337dc  lea     rcx, [rdx+r15]
0x1800337e0  mov     [r14+8], rcx
0x1800337e4  jmp     loc_180033902
0x1800337e9  jbe     loc_180033902
0x1800337ef  mov     rcx, [r14+10h]
0x1800337f3  sub     rcx, rdx
0x1800337f6  cmp     r15, rcx
0x1800337f9  jbe     loc_1800338EA
0x1800337ff  mov     rdx, rcx
0x180033802  shr     rdx, 1
0x180033805  mov     rsi, 7FFFFFFFFFFFFFFFh
0x18003380f  mov     rax, rsi
0x180033812  sub     rax, rdx
0x180033815  cmp     rcx, rax
0x180033818  jbe     short loc_180033841
0x18003381a  mov     rcx, 8000000000000026h; Size
0x180033824  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180033829  test    rax, rax
0x18003382c  jz      loc_1800338C6
0x180033832  lea     r12, [rax+27h]
0x180033836  and     r12, 0FFFFFFFFFFFFFFE0h
0x18003383a  mov     [r12-8], rax
0x18003383f  jmp     short loc_180033874
0x180033841  lea     rsi, [rcx+rdx]
0x180033845  cmp     rsi, r15
0x180033848  cmovb   rsi, r15
0x18003384c  test    rsi, rsi
0x18003384f  jz      short loc_180033874
0x180033851  cmp     rsi, 1000h
0x180033858  jb      short loc_180033869
0x18003385a  lea     rcx, [rsi+27h]
0x18003385e  cmp     rcx, rsi
0x180033861  jbe     loc_18003397B
0x180033867  jmp     short loc_180033824
0x180033869  mov     rcx, rsi; Size
0x18003386c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180033871  mov     r12, rax
0x180033874  mov     r8, r15
0x180033877  sub     r8, r13; Size
0x18003387a  lea     rcx, [r12+r13]; void *
0x18003387e  xor     edx, edx; Val
0x180033880  call    memset_0
0x180033885  mov     rdx, [r14]; Src
0x180033888  mov     r8, [r14+8]
0x18003388c  sub     r8, rdx; Size
0x18003388f  mov     rcx, r12; void *
0x180033892  call    memmove_0
0x180033897  mov     rax, [r14]
0x18003389a  test    rax, rax
0x18003389d  jz      short loc_1800338D5
0x18003389f  mov     rdx, [r14+10h]
0x1800338a3  sub     rdx, rax; unsigned __int64
0x1800338a6  cmp     rdx, 1000h
0x1800338ad  jb      short loc_1800338CD
0x1800338af  mov     rcx, [rax-8]
0x1800338b3  sub     rax, rcx
0x1800338b6  sub     rax, 8
0x1800338ba  cmp     rax, 1Fh
0x1800338be  ja      short loc_1800338C6
0x1800338c0  add     rdx, 27h ; '''
0x1800338c4  jmp     short loc_1800338D0
0x1800338c6  mov     ecx, 5
0x1800338cb  int     29h; Win8: RtlFailFast(ecx)
0x1800338cd  mov     rcx, rax; void *
0x1800338d0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800338d5  mov     [r14], r12
0x1800338d8  lea     rax, [r12+r15]
0x1800338dc  mov     [r14+8], rax
0x1800338e0  lea     rax, [r12+rsi]
0x1800338e4  mov     [r14+10h], rax
0x1800338e8  jmp     short loc_180033902
0x1800338ea  sub     r15, r13
0x1800338ed  mov     r8, r15; Size
0x1800338f0  xor     edx, edx; Val
0x1800338f2  mov     rcx, rsi; void *
0x1800338f5  call    memset_0
0x1800338fa  lea     rax, [r15+rsi]
0x1800338fe  mov     [r14+8], rax
0x180033902  mov     r8, [rbx]; pSourceSid
0x180033905  mov     rdx, [r14]; pDestinationSid
0x180033908  mov     ecx, [rbp+57h+nDestinationSidLength]; nDestinationSidLength
0x18003390b  call    cs:__imp_CopySid
0x180033911  nop
0x180033912  test    rbx, rbx
0x180033915  jz      short loc_18003394C
0x180033917  sub     rdi, rbx
0x18003391a  cmp     rdi, 1000h
0x180033921  jb      short loc_180033941
0x180033923  mov     rcx, [rbx-8]
0x180033927  sub     rbx, rcx
0x18003392a  sub     rbx, 8
0x18003392e  cmp     rbx, 1Fh
0x180033932  ja      short loc_18003393A
0x180033934  add     rdi, 27h ; '''
0x180033938  jmp     short loc_180033944
0x18003393a  mov     ecx, 5
0x18003393f  int     29h; Win8: RtlFailFast(ecx)
0x180033941  mov     rcx, rbx; void *
0x180033944  mov     rdx, rdi; unsigned __int64
0x180033947  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003394c  xor     eax, eax
0x18003394e  mov     rcx, [rbp+57h+var_38]
0x180033952  xor     rcx, rsp; StackCookie
0x180033955  call    __security_check_cookie
0x18003395a  mov     rbx, [rsp+0C0h+arg_10]
0x180033962  add     rsp, 90h
0x180033969  pop     r15
0x18003396b  pop     r14
0x18003396d  pop     r13
0x18003396f  pop     r12
0x180033971  pop     rdi
0x180033972  pop     rsi
0x180033973  pop     rbp
0x180033974  retn
0x180033975  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x18003397b  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
```
