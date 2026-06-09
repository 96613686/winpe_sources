# NgcUtils::CallerIsAppContainer(bool *)

- ea: `0x180045500`
- end: `0x180045666`
- name: `?CallerIsAppContainer@NgcUtils@@YAJPEA_N@Z`
- size: `358`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, bool *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002dc90`
- `0x180081680`

## callees

- `0x180045500`
- `0x18005cee0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004556a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045618`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004556a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045618`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180045612`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180045612`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004554d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18004554d`

## pseudocode

```c
signed int __fastcall NgcUtils::CallerIsAppContainer(NgcUtils *this, bool *a2)
{
  DWORD LastError; // eax
  signed int result; // eax
  DWORD ReturnLength; // [rsp+30h] [rbp-68h] BYREF
  int TokenInformation; // [rsp+34h] [rbp-64h] BYREF
  _DWORD v7[2]; // [rsp+38h] [rbp-60h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-58h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-48h] BYREF
  __int16 *v10; // [rsp+60h] [rbp-38h]
  int v11; // [rsp+68h] [rbp-30h]
  int v12; // [rsp+6Ch] [rbp-2Ch]
  _DWORD *v13; // [rsp+70h] [rbp-28h]
  __int64 v14; // [rsp+78h] [rbp-20h]

  TokenInformation = 0;
  ReturnLength = 0;
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
  {
    if ( ReturnLength == 4 )
    {
      *(_BYTE *)this = TokenInformation != 0;
      return 0;
    }
    else
    {
      return -2147467259;
    }
  }
  else
  {
    if ( (unsigned int)dword_180122070 > 2 )
    {
      LastError = GetLastError();
      v14 = 4;
      v7[0] = LastError;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      v13 = v7;
      *(_DWORD *)&EventDescriptor.Level = 2;
      UserData.Ptr = (ULONGLONG)off_180122078;
      EventDescriptor.Keyword = 0;
      UserData.Size = *(unsigned __int16 *)off_180122078;
      v10 = word_180107562;
      UserData.Reserved = 2;
      v11 = 31;
      v12 = 1;
      v7[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180045500  mov     [rsp+arg_8], rbx
0x180045505  push    rdi
0x180045506  sub     rsp, 90h
0x18004550d  mov     rax, cs:__security_cookie
0x180045514  xor     rax, rsp
0x180045517  mov     [rsp+98h+var_18], rax
0x18004551f  mov     rbx, rcx
0x180045522  lea     rax, [rsp+98h+var_68]
0x180045527  xor     edi, edi
0x180045529  mov     [rsp+98h+ReturnLength], rax; ReturnLength
0x18004552e  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x180045535  mov     [rsp+98h+TokenInformation], edi
0x180045539  mov     r9d, 4; TokenInformationLength
0x18004553f  mov     [rsp+98h+var_68], edi
0x180045543  lea     r8, [rsp+98h+TokenInformation]; TokenInformation
0x180045548  mov     edx, 1Dh; TokenInformationClass
0x18004554d  call    cs:__imp_GetTokenInformation
0x180045553  test    eax, eax
0x180045555  jnz     loc_18004562C
0x18004555b  mov     eax, cs:dword_180122070
0x180045561  cmp     eax, 2
0x180045564  jbe     loc_180045618
0x18004556a  call    cs:__imp_GetLastError
0x180045570  mov     [rsp+98h+var_20], 4
0x180045579  lea     rcx, _TraceLoggingMetadata
0x180045580  mov     [rsp+98h+var_60], eax
0x180045584  lea     rdx, [rsp+98h+EventDescriptor]; EventDescriptor
0x180045589  lea     rax, [rsp+98h+var_60]
0x18004558e  mov     dword ptr [rsp+98h+EventDescriptor.Id], 0B000000h
0x180045596  mov     [rsp+98h+var_28], rax
0x18004559b  xor     r9d, r9d; RelatedActivityId
0x18004559e  movzx   eax, cs:word_180107558
0x1800455a5  xor     r8d, r8d; ActivityId
0x1800455a8  mov     dword ptr [rsp+98h+EventDescriptor.Level], eax
0x1800455ac  mov     rax, cs:off_180122078
0x1800455b3  mov     [rsp+98h+var_48.Ptr], rax
0x1800455b8  mov     [rsp+98h+EventDescriptor.Keyword], rdi
0x1800455bd  movzx   eax, word ptr [rax]
0x1800455c0  mov     [rsp+98h+var_48.Size], eax
0x1800455c4  lea     rax, word_180107562
0x1800455cb  mov     [rsp+98h+var_38], rax
0x1800455d0  lea     rax, _TraceLoggingMetadataEnd
0x1800455d7  sub     eax, ecx
0x1800455d9  mov     dword ptr [rsp+98h+var_48.0Ch], 2
0x1800455e1  mov     [rsp+98h+var_30], 1Fh
0x1800455e9  mov     [rsp+98h+var_2C], 1
0x1800455f1  mov     [rsp+98h+var_5C], eax
0x1800455f5  mov     eax, [rsp+98h+var_5C]
0x1800455f9  mov     rcx, cs:RegHandle; RegHandle
0x180045600  lea     rax, [rsp+98h+var_48]
0x180045605  mov     [rsp+98h+UserData], rax; UserData
0x18004560a  mov     dword ptr [rsp+98h+ReturnLength], 3; UserDataCount
0x180045612  call    cs:__imp_EventWriteTransfer
0x180045618  call    cs:__imp_GetLastError
0x18004561e  test    eax, eax
0x180045620  jle     short loc_180045645
0x180045622  movzx   eax, ax
0x180045625  or      eax, 80070000h
0x18004562a  jmp     short loc_180045645
0x18004562c  cmp     [rsp+98h+var_68], 4
0x180045631  jz      short loc_18004563A
0x180045633  mov     eax, 80004005h
0x180045638  jmp     short loc_180045645
0x18004563a  cmp     [rsp+98h+TokenInformation], edi
0x18004563e  setnz   al
0x180045641  mov     [rbx], al
0x180045643  xor     eax, eax
0x180045645  mov     rcx, [rsp+98h+var_18]
0x18004564d  xor     rcx, rsp; StackCookie
0x180045650  call    __security_check_cookie
0x180045655  mov     rbx, [rsp+98h+arg_8]
0x18004565d  add     rsp, 90h
0x180045664  pop     rdi
0x180045665  retn
```
