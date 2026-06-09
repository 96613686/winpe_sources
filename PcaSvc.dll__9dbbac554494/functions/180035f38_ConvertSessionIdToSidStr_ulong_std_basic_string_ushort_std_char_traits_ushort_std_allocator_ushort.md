# ConvertSessionIdToSidStr(ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180035f38`
- end: `0x180036150`
- name: `?ConvertSessionIdToSidStr@@YAKKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `536`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003ab58`

## callees

- `0x180012920`
- `0x1800189e4`
- `0x180035f38`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180036034`
- `ntdll!RtlFreeHeap` at `0x180036034`
- `ntdll!RtlAllocateHeap` at `0x180035faf`
- `ntdll!RtlAllocateHeap` at `0x180035faf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035fe1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800360b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800360d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800360e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036120`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036138`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035fe1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800360b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800360d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800360e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036120`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036138`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003600f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003600f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180035f8b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180035fd7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180035f8b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180035fd7`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180036059`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180036059`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800360ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800360ce`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003606e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003606e`
- `WTSAPI32!WTSQueryUserToken` at `0x180035f68`
- `WTSAPI32!WTSQueryUserToken` at `0x180035f68`

## string_xrefs

- `0x180035ff4`: `ConvertSessionIdToSidStr`
- `0x180036092`: `ConvertSessionIdToSidStr`
- `0x18003610d`: `ConvertSessionIdToSidStr`
- `0x180035fe7`: `GetTokenInformation failed %d`
- `0x1800360ee`: `GetTokenInformation failed %d`
- `0x180036126`: `GetTokenInformation failed %d`
- `0x180036080`: `User SID: %ws`
- `0x1800360bc`: `WTSQueryUserToken failed %d`
- `0x18003613e`: `ConvertSidToStringSidW failed %d`

## pseudocode

```c
__int64 __fastcall ConvertSessionIdToSidStr(ULONG a1, __int64 a2)
{
  PSID *Heap; // rdi
  unsigned int v4; // ebx
  DWORD LastError; // eax
  const char *v6; // r9
  int v7; // r8d
  PDWORD ReturnLength; // [rsp+20h] [rbp-20h]
  LPWSTR StringSid; // [rsp+30h] [rbp-10h] BYREF
  DWORD TokenInformationLength; // [rsp+70h] [rbp+30h] BYREF
  void *phToken; // [rsp+78h] [rbp+38h] BYREF

  phToken = 0;
  Heap = 0;
  TokenInformationLength = 0;
  StringSid = 0;
  v4 = 1;
  if ( !WTSQueryUserToken(a1, &phToken) )
  {
    LastError = GetLastError();
    v6 = "WTSQueryUserToken failed %d";
    v7 = 724;
    goto LABEL_6;
  }
  if ( !GetTokenInformation(phToken, TokenUser, 0, 0, &TokenInformationLength) && GetLastError() != 122 )
  {
    LastError = GetLastError();
    v6 = "GetTokenInformation failed %d";
    v7 = 734;
    goto LABEL_6;
  }
  Heap = (PSID *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, TokenInformationLength);
  if ( Heap )
  {
    if ( !GetTokenInformation(phToken, TokenUser, Heap, TokenInformationLength, &TokenInformationLength) )
    {
      LastError = GetLastError();
      v6 = "GetTokenInformation failed %d";
      v7 = 747;
LABEL_6:
      LODWORD(ReturnLength) = LastError;
      AslLogCallPrintf(1, (unsigned int)"ConvertSessionIdToSidStr", v7, (_DWORD)v6, ReturnLength);
      goto LABEL_7;
    }
    if ( !IsValidSid(*Heap) )
    {
      LastError = GetLastError();
      v6 = "GetTokenInformation failed %d";
      v7 = 753;
      goto LABEL_6;
    }
    if ( !ConvertSidToStringSidW(*Heap, &StringSid) )
    {
      LastError = GetLastError();
      v6 = "ConvertSidToStringSidW failed %d";
      v7 = 759;
      goto LABEL_6;
    }
    AslLogCallPrintf(3, (unsigned int)"ConvertSessionIdToSidStr", 763, (unsigned int)"User SID: %ws", StringSid);
    std::wstring::assign(a2, StringSid);
    v4 = 0;
  }
  else
  {
    AslLogCallPrintf(1, (unsigned int)"ConvertSessionIdToSidStr", 741, (unsigned int)"Out of memory");
  }
LABEL_7:
  if ( phToken )
  {
    CloseHandle(phToken);
    phToken = 0;
  }
  if ( Heap )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
  if ( StringSid )
    LocalFree(StringSid);
  return v4;
}

```

## disassembly

```asm
0x180035f38  mov     [rsp-18h+arg_0], rbx
0x180035f3d  push    rbp
0x180035f3e  push    rsi
0x180035f3f  push    rdi
0x180035f40  mov     rbp, rsp
0x180035f43  sub     rsp, 40h
0x180035f47  mov     rsi, rdx
0x180035f4a  mov     [rbp+phToken], 0
0x180035f52  xor     edi, edi
0x180035f54  mov     [rbp+TokenInformationLength], 0
0x180035f5b  lea     rdx, [rbp+phToken]; phToken
0x180035f5f  mov     [rbp+StringSid], rdi
0x180035f63  mov     ebx, 1
0x180035f68  call    cs:__imp_WTSQueryUserToken
0x180035f6e  test    eax, eax
0x180035f70  jz      loc_1800360B6
0x180035f76  mov     rcx, [rbp+phToken]; TokenHandle
0x180035f7a  lea     rax, [rbp+TokenInformationLength]
0x180035f7e  xor     r9d, r9d; TokenInformationLength
0x180035f81  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x180035f86  xor     r8d, r8d; TokenInformation
0x180035f89  mov     edx, ebx; TokenInformationClass
0x180035f8b  call    cs:__imp_GetTokenInformation
0x180035f91  test    eax, eax
0x180035f93  jz      loc_1800360D9
0x180035f99  mov     rcx, gs:60h
0x180035fa2  mov     edx, 8; Flags
0x180035fa7  mov     r8d, [rbp+TokenInformationLength]; Size
0x180035fab  mov     rcx, [rcx+30h]; HeapHandle
0x180035faf  call    cs:__imp_RtlAllocateHeap
0x180035fb5  mov     rdi, rax
0x180035fb8  test    rax, rax
0x180035fbb  jz      loc_180036100
0x180035fc1  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180035fc5  lea     rax, [rbp+TokenInformationLength]
0x180035fc9  mov     rcx, [rbp+phToken]; TokenHandle
0x180035fcd  mov     r8, rdi; TokenInformation
0x180035fd0  mov     edx, ebx; TokenInformationClass
0x180035fd2  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x180035fd7  call    cs:__imp_GetTokenInformation
0x180035fdd  test    eax, eax
0x180035fdf  jnz     short loc_180036056
0x180035fe1  call    cs:__imp_GetLastError
0x180035fe7  lea     r9, aGettokeninform_0; "GetTokenInformation failed %d"
0x180035fee  mov     r8d, 2EBh
0x180035ff4  lea     rdx, aConvertsession; "ConvertSessionIdToSidStr"
0x180035ffb  mov     dword ptr [rsp+40h+ReturnLength], eax
0x180035fff  mov     ecx, ebx
0x180036001  call    AslLogCallPrintf
0x180036006  mov     rcx, [rbp+phToken]; hObject
0x18003600a  test    rcx, rcx
0x18003600d  jz      short loc_18003601D
0x18003600f  call    cs:__imp_CloseHandle
0x180036015  mov     [rbp+phToken], 0
0x18003601d  test    rdi, rdi
0x180036020  jz      short loc_18003603A
0x180036022  mov     rcx, gs:60h
0x18003602b  mov     r8, rdi; P
0x18003602e  xor     edx, edx; Flags
0x180036030  mov     rcx, [rcx+30h]; HeapHandle
0x180036034  call    cs:__imp_RtlFreeHeap
0x18003603a  mov     rcx, [rbp+StringSid]; hMem
0x18003603e  test    rcx, rcx
0x180036041  jnz     loc_1800360CE
0x180036047  mov     eax, ebx
0x180036049  mov     rbx, [rsp+40h+arg_0]
0x18003604e  add     rsp, 40h
0x180036052  pop     rdi
0x180036053  pop     rsi
0x180036054  pop     rbp
0x180036055  retn
0x180036056  mov     rcx, [rdi]; pSid
0x180036059  call    cs:__imp_IsValidSid
0x18003605f  test    eax, eax
0x180036061  jz      loc_180036120
0x180036067  mov     rcx, [rdi]; Sid
0x18003606a  lea     rdx, [rbp+StringSid]; StringSid
0x18003606e  call    cs:__imp_ConvertSidToStringSidW
0x180036074  test    eax, eax
0x180036076  jz      loc_180036138
0x18003607c  mov     rax, [rbp+StringSid]
0x180036080  lea     r9, aUserSidWs; "User SID: %ws"
0x180036087  mov     r8d, 2FBh
0x18003608d  mov     [rsp+40h+ReturnLength], rax
0x180036092  lea     rdx, aConvertsession; "ConvertSessionIdToSidStr"
0x180036099  mov     ecx, 3
0x18003609e  call    AslLogCallPrintf
0x1800360a3  mov     rdx, [rbp+StringSid]
0x1800360a7  mov     rcx, rsi
0x1800360aa  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x1800360af  xor     ebx, ebx
0x1800360b1  jmp     loc_180036006
0x1800360b6  call    cs:__imp_GetLastError
0x1800360bc  lea     r9, aWtsqueryuserto_0; "WTSQueryUserToken failed %d"
0x1800360c3  mov     r8d, 2D4h
0x1800360c9  jmp     loc_180035FF4
0x1800360ce  call    cs:__imp_LocalFree
0x1800360d4  jmp     loc_180036047
0x1800360d9  call    cs:__imp_GetLastError
0x1800360df  cmp     eax, 7Ah ; 'z'
0x1800360e2  jz      loc_180035F99
0x1800360e8  call    cs:__imp_GetLastError
0x1800360ee  lea     r9, aGettokeninform_0; "GetTokenInformation failed %d"
0x1800360f5  mov     r8d, 2DEh
0x1800360fb  jmp     loc_180035FF4
0x180036100  lea     r9, aOutOfMemory; "Out of memory"
0x180036107  mov     r8d, 2E5h
0x18003610d  lea     rdx, aConvertsession; "ConvertSessionIdToSidStr"
0x180036114  mov     ecx, ebx
0x180036116  call    AslLogCallPrintf
0x18003611b  jmp     loc_180036006
0x180036120  call    cs:__imp_GetLastError
0x180036126  lea     r9, aGettokeninform_0; "GetTokenInformation failed %d"
0x18003612d  mov     r8d, 2F1h
0x180036133  jmp     loc_180035FF4
0x180036138  call    cs:__imp_GetLastError
0x18003613e  lea     r9, aConvertsidtost_0; "ConvertSidToStringSidW failed %d"
0x180036145  mov     r8d, 2F7h
0x18003614b  jmp     loc_180035FF4
```
