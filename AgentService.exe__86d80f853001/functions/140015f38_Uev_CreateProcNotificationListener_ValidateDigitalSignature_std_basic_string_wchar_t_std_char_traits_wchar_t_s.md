# Uev::CreateProcNotificationListener::ValidateDigitalSignature(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x140015f38`
- end: `0x1400160d7`
- name: `?ValidateDigitalSignature@CreateProcNotificationListener@Uev@@AEBA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z`
- size: `415`
- prototype: `char __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x140015224`

## callees

- `0x140003e50`
- `0x140004b14`
- `0x14000ac28`
- `0x14000ad1c`
- `0x14000efc4`
- `0x140015f38`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14001606d`
- `KERNEL32!GetLastError` at `0x14001606d`
- `WINTRUST!WinVerifyTrust` at `0x140015ffa`
- `WINTRUST!WinVerifyTrust` at `0x140015ffa`

## string_xrefs

- `0x140016053`: `AgentService.CreateProcNotificationListener::ValidateDigitalSignature: The file '%s' is signed and the signature was verified.`
- `0x14001608f`: `AgentService.CreateProcNotificationListener::ValidateDigitalSignature: The file '%s' is not signed.`
- `0x140016081`: `AgentService.CreateProcNotificationListener::ValidateDigitalSignature: An unknown error occurred trying to verify the signature of the '%s' file.`
- `0x140016064`: `AgentService.CreateProcNotificationListener::ValidateDigitalSignature: The signature present in file '%s' is specifically disallowed.`
- `0x140016098`: `AgentService.CreateProcNotificationListener::ValidateDigitalSignature: The signature present in file '%s' is not trusted.`
- `0x1400160a1`: `AgentService.CreateProcNotificationListener::ValidateDigitalSignature: The hash in file '%s' representing the subject or the publisher wasn't explicitly trusted by the admin  and admin policy has disabled user trust. No signature, publisher or timestamp errors.`
- `0x140016030`: `AgentService.CreateProcNotificationListener::ValidateDigitalSignature: Error 0x%X validating signature for file '%s'.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall Uev::CreateProcNotificationListener::ValidateDigitalSignature(__int64 a1, _QWORD *a2)
{
  char v2; // di
  _QWORD *v3; // rbx
  unsigned int v4; // eax
  wchar_t *v5; // rcx
  DWORD LastError; // eax
  _QWORD pWVTData[12]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v9[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v10; // [rsp+A0h] [rbp-60h]
  GUID pgActionID; // [rsp+B0h] [rbp-50h] BYREF
  wchar_t Buffer[256]; // [rsp+C0h] [rbp-40h] BYREF

  v2 = 0;
  v3 = a2;
  if ( a2[3] > 7u )
    v3 = (_QWORD *)*a2;
  v9[0] = 32;
  memset(&pWVTData[6], 0, 24);
  pWVTData[10] = 0;
  pWVTData[1] = 0;
  pWVTData[2] = 0;
  pWVTData[5] = v9;
  v9[1] = v3;
  v10 = 0;
  pgActionID.Data1 = 11191659;
  *(_DWORD *)&pgActionID.Data2 = 298896708;
  *(_DWORD *)pgActionID.Data4 = -1073692020;
  *(_DWORD *)&pgActionID.Data4[4] = -292175281;
  pWVTData[0] = 88;
  pWVTData[4] = 1;
  pWVTData[3] = 2;
  pWVTData[9] = 16;
  v4 = WinVerifyTrust(0, &pgActionID, pWVTData);
  switch ( v4 )
  {
    case 0x80092026:
      v5 = (wchar_t *)L"AgentService.CreateProcNotificationListener::ValidateDigitalSignature: The hash in file '%s' repre"
                       "senting the subject or the publisher wasn't explicitly trusted by the admin  and admin policy has"
                       " disabled user trust. No signature, publisher or timestamp errors.";
      goto LABEL_17;
    case 0x800B0004:
      v5 = L"AgentService.CreateProcNotificationListener::ValidateDigitalSignature: The signature present in file '%s' is not trusted.";
      goto LABEL_17;
    case 0x800B0100:
      LastError = GetLastError();
      if ( LastError == -2146762496
        || LastError == -2146762749
        || (v5 = L"AgentService.CreateProcNotificationListener::ValidateDigitalSignature: An unknown error occurred trying"
                  " to verify the signature of the '%s' file.",
            LastError == -2146762751) )
      {
        v5 = L"AgentService.CreateProcNotificationListener::ValidateDigitalSignature: The file '%s' is not signed.";
      }
      goto LABEL_17;
    case 0x800B0111:
      v5 = L"AgentService.CreateProcNotificationListener::ValidateDigitalSignature: The signature present in file '%s' is "
            "specifically disallowed.";
LABEL_17:
      DbgTraceFrmtErr<wchar_t const *>(v5);
      return v2;
  }
  if ( v4 )
  {
    swprintf_s(
      Buffer,
      0x100u,
      L"AgentService.CreateProcNotificationListener::ValidateDigitalSignature: Error 0x%X validating signature for file '%s'.",
      v4,
      v3);
    DbgTrace<2>(Buffer);
  }
  else
  {
    DbgTraceFrmt<4,wchar_t const *>((wchar_t *)L"AgentService.CreateProcNotificationListener::ValidateDigitalSignature: Th"
                                                "e file '%s' is signed and the signature was verified.");
    return 1;
  }
  return v2;
}

```

## disassembly

```asm
0x140015f38  mov     [rsp-8+arg_0], rbx
0x140015f3d  mov     [rsp-8+arg_10], rdi
0x140015f42  push    rbp
0x140015f43  lea     rbp, [rsp-1D0h]
0x140015f4b  sub     rsp, 2D0h
0x140015f52  mov     rax, cs:__security_cookie
0x140015f59  xor     rax, rsp
0x140015f5c  mov     [rbp+1D0h+var_10], rax
0x140015f63  xor     dil, dil
0x140015f66  mov     rbx, rdx
0x140015f69  cmp     qword ptr [rdx+18h], 7
0x140015f6e  jbe     short loc_140015F73
0x140015f70  mov     rbx, [rdx]
0x140015f73  xor     eax, eax
0x140015f75  mov     [rbp+1D0h+var_240], 20h ; ' '
0x140015f7d  mov     [rsp+2D0h+var_270], rax
0x140015f82  lea     r8, [rsp+2D0h+pWVTData]; pWVTData
0x140015f87  mov     [rbp+1D0h+var_250], rax
0x140015f8b  lea     rdx, [rbp+1D0h+pgActionID]; pgActionID
0x140015f8f  mov     [rsp+2D0h+var_298], rax
0x140015f94  xorps   xmm0, xmm0
0x140015f97  mov     [rsp+2D0h+var_290], rax
0x140015f9c  xor     ecx, ecx; hwnd
0x140015f9e  mov     [rsp+2D0h+var_268], rax
0x140015fa3  mov     [rsp+2D0h+var_260], rax
0x140015fa8  lea     rax, [rbp+1D0h+var_240]
0x140015fac  mov     [rsp+2D0h+var_278], rax
0x140015fb1  mov     [rbp+1D0h+var_238], rbx
0x140015fb5  movdqu  [rbp+1D0h+var_230], xmm0
0x140015fba  mov     [rbp+1D0h+pgActionID.Data1], 0AAC56Bh
0x140015fc1  mov     dword ptr [rbp+1D0h+pgActionID.Data2], 11D0CD44h
0x140015fc8  mov     dword ptr [rbp+1D0h+pgActionID.Data4], 0C000C28Ch
0x140015fcf  mov     dword ptr [rbp+1D0h+pgActionID.Data4+4], 0EE95C24Fh
0x140015fd6  mov     [rsp+2D0h+pWVTData], 58h ; 'X'
0x140015fdf  mov     [rsp+2D0h+var_280], 1
0x140015fe8  mov     [rsp+2D0h+var_288], 2
0x140015ff1  mov     [rsp+2D0h+var_258], 10h
0x140015ffa  call    cs:__imp_WinVerifyTrust
0x140016000  cmp     eax, 80092026h
0x140016005  jz      loc_1400160A1
0x14001600b  cmp     eax, 800B0004h
0x140016010  jz      loc_140016098
0x140016016  cmp     eax, 800B0100h
0x14001601b  jz      short loc_14001606D
0x14001601d  cmp     eax, 800B0111h
0x140016022  jz      short loc_140016064
0x140016024  test    eax, eax
0x140016026  jz      short loc_140016050
0x140016028  mov     r9d, eax
0x14001602b  mov     [rsp+2D0h+var_2B0], rbx
0x140016030  lea     r8, aAgentserviceCr_33; "AgentService.CreateProcNotificationList"...
0x140016037  mov     edx, 100h; BufferCount
0x14001603c  lea     rcx, [rbp+1D0h+Buffer]; Buffer
0x140016040  call    swprintf_s
0x140016045  lea     rcx, [rbp+1D0h+Buffer]
0x140016049  call    ??$DbgTrace@$01@@YAXPEB_W@Z; DbgTrace<2>(wchar_t const *)
0x14001604e  jmp     short loc_1400160B0
0x140016050  mov     rdx, rbx
0x140016053  lea     rcx, aAgentserviceCr_49; "AgentService.CreateProcNotificationList"...
0x14001605a  call    ??$DbgTraceFrmt@$03PEB_W@@YAXPEB_W0@Z; DbgTraceFrmt<4,wchar_t const *>(wchar_t const *,wchar_t const *)
0x14001605f  mov     dil, 1
0x140016062  jmp     short loc_1400160B0
0x140016064  lea     rcx, aAgentserviceCr_22; "AgentService.CreateProcNotificationList"...
0x14001606b  jmp     short loc_1400160A8
0x14001606d  call    cs:__imp_GetLastError
0x140016073  cmp     eax, 800B0100h
0x140016078  jz      short loc_14001608F
0x14001607a  cmp     eax, 800B0003h
0x14001607f  jz      short loc_14001608F
0x140016081  lea     rcx, aAgentserviceCr_8; "AgentService.CreateProcNotificationList"...
0x140016088  cmp     eax, 800B0001h
0x14001608d  jnz     short loc_1400160A8
0x14001608f  lea     rcx, aAgentserviceCr_16; "AgentService.CreateProcNotificationList"...
0x140016096  jmp     short loc_1400160A8
0x140016098  lea     rcx, aAgentserviceCr_47; "AgentService.CreateProcNotificationList"...
0x14001609f  jmp     short loc_1400160A8
0x1400160a1  lea     rcx, aAgentserviceCr_24; "AgentService.CreateProcNotificationList"...
0x1400160a8  mov     rdx, rbx
0x1400160ab  call    ??$DbgTraceFrmtErr@PEB_W@@YAXPEB_W0@Z; DbgTraceFrmtErr<wchar_t const *>(wchar_t const *,wchar_t const *)
0x1400160b0  mov     al, dil
0x1400160b3  mov     rcx, [rbp+1D0h+var_10]
0x1400160ba  xor     rcx, rsp; StackCookie
0x1400160bd  call    __security_check_cookie
0x1400160c2  lea     r11, [rsp+2D0h+var_s0]
0x1400160ca  mov     rbx, [r11+10h]
0x1400160ce  mov     rdi, [r11+20h]
0x1400160d2  mov     rsp, r11
0x1400160d5  pop     rbp
0x1400160d6  retn
```
