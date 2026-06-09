# CTIPlugin::NotifyCFGViolation(void *,void *,wchar_t const *,ulong,_CONTEXT const *)

- ea: `0x140050908`
- end: `0x140050bff`
- name: `?NotifyCFGViolation@CTIPlugin@@CAXPEAX0PEB_WKPEBU_CONTEXT@@@Z`
- size: `759`
- prototype: `void __usercall(void *@<rcx>, void *@<rdx>, const wchar_t *@<r8>, unsigned int@<r9d>, const struct _CONTEXT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140050870`

## callees

- `0x140002470`
- `0x1400030a8`
- `0x140014474`
- `0x140015b40`
- `0x140050620`
- `0x1400506fc`
- `0x140050908`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140050a60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140050a60`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x140050a39`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x140050a39`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1400509d4`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140050a17`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1400509d4`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140050a17`
- `ntdll!EtwEventWriteNoRegistration` at `0x140050ba1`
- `ntdll!EtwEventWriteNoRegistration` at `0x140050ba1`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x140050993`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x140050993`

## pseudocode

```c
void __fastcall CTIPlugin::NotifyCFGViolation(void *a1, void *a2, const wchar_t *a3, int a4, const struct _CONTEXT *a5)
{
  const struct _CONTEXT *v5; // rdi
  const void *R8; // rdx
  unsigned int v10; // edx
  signed int LastError; // eax
  __int64 v12; // rax
  unsigned int v13; // eax
  unsigned int v14; // edx
  unsigned int TICallAddressInfo; // eax
  __int64 v16; // rcx
  int v17; // r9d
  unsigned int v18; // eax
  WINBOOL Wow64Process; // [rsp+30h] [rbp-D0h] BYREF
  int v20; // [rsp+34h] [rbp-CCh] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+38h] [rbp-C8h] BYREF
  struct _FILETIME ExitTime; // [rsp+40h] [rbp-C0h] BYREF
  struct _FILETIME CreationTime; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE Buffer[128]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v25; // [rsp+D0h] [rbp-30h]
  LPCVOID lpBaseAddress; // [rsp+E8h] [rbp-18h]
  _QWORD v27[90]; // [rsp+520h] [rbp+420h] BYREF
  _QWORD v28[90]; // [rsp+7F0h] [rbp+6F0h] BYREF
  const wchar_t *v29; // [rsp+AC0h] [rbp+9C0h] BYREF
  int v30; // [rsp+AC8h] [rbp+9C8h]
  int v31; // [rsp+ACCh] [rbp+9CCh]
  int *v32; // [rsp+AD0h] [rbp+9D0h]
  __int64 v33; // [rsp+AD8h] [rbp+9D8h]
  struct _FILETIME *p_CreationTime; // [rsp+AE0h] [rbp+9E0h]
  __int64 v35; // [rsp+AE8h] [rbp+9E8h]
  int *v36; // [rsp+AF0h] [rbp+9F0h]
  __int64 v37; // [rsp+AF8h] [rbp+9F8h]
  struct _EVENT_DATA_DESCRIPTOR v38; // [rsp+B00h] [rbp+A00h] BYREF
  int v39; // [rsp+C98h] [rbp+B98h] BYREF

  v39 = a4;
  v5 = a5;
  Wow64Process = 0;
  memset_0(v27, 0, 0x2C8u);
  memset_0(v28, 0, 0x2C8u);
  CreationTime = 0;
  ExitTime = 0;
  v20 = 1;
  if ( IsWow64Process(a1, &Wow64Process) && Wow64Process )
    v20 = 0;
  R8 = (const void *)v5->R8;
  NumberOfBytesRead = 0;
  if ( R8 )
  {
    Wow64Process = ReadProcessMemory(a1, R8, Buffer, 0x4D0u, &NumberOfBytesRead);
    if ( Wow64Process )
    {
      if ( NumberOfBytesRead == 1232 )
      {
        v28[0] = v25;
        if ( lpBaseAddress )
          ReadProcessMemory(a1, lpBaseAddress, v27, 8u, &NumberOfBytesRead);
      }
    }
  }
  Wow64Process = GetProcessTimes(a1, &CreationTime, &ExitTime, &ExitTime, &ExitTime);
  if ( !Wow64Process )
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_5d1834416bbb32ed8157f52948dd8803_Traceguids,
        (unsigned int)LastError);
    }
    CreationTime = 0;
  }
  if ( v28[0] )
    CTIPlugin::FillCallInfo((struct TI_ADDRESS_INFO *)v28, a1, a2, 1);
  if ( v27[0] )
    CTIPlugin::FillCallInfo((struct TI_ADDRESS_INFO *)v27, a1, a2, 0);
  v29 = a3;
  v12 = -1;
  do
    ++v12;
  while ( a3[v12] );
  v31 = 0;
  v30 = 2 * v12 + 2;
  v33 = 4;
  v32 = &v39;
  v35 = 8;
  p_CreationTime = &CreationTime;
  v36 = &v20;
  v37 = 4;
  v13 = CTIPlugin::EventDataDescCreateTICallAddressInfo(&v38, v10, (const struct TI_ADDRESS_INFO *)v27);
  TICallAddressInfo = CTIPlugin::EventDataDescCreateTICallAddressInfo(
                        (struct _EVENT_DATA_DESCRIPTOR *)&(&v29)[2 * v13 + 4],
                        v14,
                        (const struct TI_ADDRESS_INFO *)v28);
  if ( v17 + TICallAddressInfo != 24 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v16);
  v18 = EtwEventWriteNoRegistration(S_MICROSOFT_WINDOWS_WER_DIAG, EVENT_CFG_VIOLATION, 24, &v29);
  Wow64Process = v18;
  if ( v18
    && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_5d1834416bbb32ed8157f52948dd8803_Traceguids, v18);
  }
}

```

## disassembly

```asm
0x140050908  mov     [rsp-8+arg_10], rbx
0x14005090d  mov     [rsp-8+arg_18], r9d
0x140050912  push    rbp
0x140050913  push    rsi
0x140050914  push    rdi
0x140050915  push    r12
0x140050917  push    r14
0x140050919  lea     rbp, [rsp-0B50h]
0x140050921  sub     rsp, 0C50h
0x140050928  mov     rax, cs:__security_cookie
0x14005092f  xor     rax, rsp
0x140050932  mov     [rbp+0B70h+var_30], rax
0x140050939  mov     rdi, [rbp+0B70h+arg_20]
0x140050940  mov     rsi, r8
0x140050943  mov     r14, rdx
0x140050946  mov     rbx, rcx
0x140050949  xor     r12d, r12d
0x14005094c  lea     rcx, [rbp+0B70h+var_750]; void *
0x140050953  xor     edx, edx; Val
0x140050955  mov     [rsp+0C70h+Wow64Process], r12d
0x14005095a  mov     r8d, 2C8h; Size
0x140050960  call    memset_0
0x140050965  xor     edx, edx; Val
0x140050967  lea     rcx, [rbp+0B70h+var_480]; void *
0x14005096e  mov     r8d, 2C8h; Size
0x140050974  call    memset_0
0x140050979  lea     rdx, [rsp+0C70h+Wow64Process]; Wow64Process
0x14005097e  mov     qword ptr [rsp+0C70h+CreationTime.dwLowDateTime], r12
0x140050983  mov     rcx, rbx; hProcess
0x140050986  mov     qword ptr [rsp+0C70h+ExitTime.dwLowDateTime], r12
0x14005098b  mov     [rsp+0C70h+var_C3C], 1
0x140050993  call    cs:__imp_IsWow64Process
0x140050999  test    eax, eax
0x14005099b  jz      short loc_1400509A9
0x14005099d  cmp     [rsp+0C70h+Wow64Process], r12d
0x1400509a2  jz      short loc_1400509A9
0x1400509a4  mov     [rsp+0C70h+var_C3C], r12d
0x1400509a9  mov     rdx, [rdi+0B8h]; lpBaseAddress
0x1400509b0  mov     [rsp+0C70h+NumberOfBytesRead], r12
0x1400509b5  test    rdx, rdx
0x1400509b8  jz      short loc_140050A1D
0x1400509ba  lea     rax, [rsp+0C70h+NumberOfBytesRead]
0x1400509bf  mov     edi, 4D0h
0x1400509c4  mov     r9d, edi; nSize
0x1400509c7  mov     [rsp+0C70h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x1400509cc  lea     r8, [rsp+0C70h+Buffer]; lpBuffer
0x1400509d1  mov     rcx, rbx; hProcess
0x1400509d4  call    cs:__imp_ReadProcessMemory
0x1400509da  mov     [rsp+0C70h+Wow64Process], eax
0x1400509de  test    eax, eax
0x1400509e0  jz      short loc_140050A1D
0x1400509e2  cmp     [rsp+0C70h+NumberOfBytesRead], rdi
0x1400509e7  jnz     short loc_140050A1D
0x1400509e9  mov     rdx, [rbp+0B70h+lpBaseAddress]; lpBaseAddress
0x1400509ed  mov     rax, [rbp+0B70h+var_BA0]
0x1400509f1  mov     [rbp+0B70h+var_480], rax
0x1400509f8  test    rdx, rdx
0x1400509fb  jz      short loc_140050A1D
0x1400509fd  lea     rax, [rsp+0C70h+NumberOfBytesRead]
0x140050a02  mov     r9d, 8; nSize
0x140050a08  lea     r8, [rbp+0B70h+var_750]; lpBuffer
0x140050a0f  mov     [rsp+0C70h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x140050a14  mov     rcx, rbx; hProcess
0x140050a17  call    cs:__imp_ReadProcessMemory
0x140050a1d  lea     rax, [rsp+0C70h+ExitTime]
0x140050a22  mov     rcx, rbx; hProcess
0x140050a25  lea     r9, [rsp+0C70h+ExitTime]; lpKernelTime
0x140050a2a  mov     [rsp+0C70h+lpNumberOfBytesRead], rax; lpUserTime
0x140050a2f  lea     r8, [rsp+0C70h+ExitTime]; lpExitTime
0x140050a34  lea     rdx, [rsp+0C70h+CreationTime]; lpCreationTime
0x140050a39  call    cs:__imp_GetProcessTimes
0x140050a3f  mov     [rsp+0C70h+Wow64Process], eax
0x140050a43  lea     rdi, WPP_GLOBAL_Control
0x140050a4a  test    eax, eax
0x140050a4c  jnz     short loc_140050A96
0x140050a4e  mov     rax, cs:WPP_GLOBAL_Control
0x140050a55  cmp     rax, rdi
0x140050a58  jz      short loc_140050A91
0x140050a5a  test    byte ptr [rax+1Ch], 2
0x140050a5e  jz      short loc_140050A91
0x140050a60  call    cs:__imp_GetLastError
0x140050a66  test    eax, eax
0x140050a68  jle     short loc_140050A72
0x140050a6a  movzx   eax, ax
0x140050a6d  or      eax, 80070000h
0x140050a72  mov     rcx, cs:WPP_GLOBAL_Control
0x140050a79  lea     r8, WPP_5d1834416bbb32ed8157f52948dd8803_Traceguids
0x140050a80  mov     edx, 0Ah
0x140050a85  mov     r9d, eax
0x140050a88  mov     rcx, [rcx+10h]
0x140050a8c  call    WPP_SF_d
0x140050a91  mov     qword ptr [rsp+0C70h+CreationTime.dwLowDateTime], r12
0x140050a96  cmp     [rbp+0B70h+var_480], r12
0x140050a9d  jz      short loc_140050AB7
0x140050a9f  mov     r9d, 1; int
0x140050aa5  lea     rcx, [rbp+0B70h+var_480]; struct TI_ADDRESS_INFO *
0x140050aac  mov     r8, r14; void *
0x140050aaf  mov     rdx, rbx; void *
0x140050ab2  call    ?FillCallInfo@CTIPlugin@@CAXPEAUTI_ADDRESS_INFO@@PEAX1H@Z; CTIPlugin::FillCallInfo(TI_ADDRESS_INFO *,void *,void *,int)
0x140050ab7  cmp     [rbp+0B70h+var_750], r12
0x140050abe  jz      short loc_140050AD5
0x140050ac0  xor     r9d, r9d; int
0x140050ac3  lea     rcx, [rbp+0B70h+var_750]; struct TI_ADDRESS_INFO *
0x140050aca  mov     r8, r14; void *
0x140050acd  mov     rdx, rbx; void *
0x140050ad0  call    ?FillCallInfo@CTIPlugin@@CAXPEAUTI_ADDRESS_INFO@@PEAX1H@Z; CTIPlugin::FillCallInfo(TI_ADDRESS_INFO *,void *,void *,int)
0x140050ad5  mov     [rbp+0B70h+var_1B0], rsi
0x140050adc  or      rax, 0FFFFFFFFFFFFFFFFh
0x140050ae0  inc     rax
0x140050ae3  cmp     [rsi+rax*2], r12w
0x140050ae8  jnz     short loc_140050AE0
0x140050aea  lea     eax, ds:2[rax*2]
0x140050af1  mov     [rbp+0B70h+var_1A4], r12d
0x140050af8  mov     [rbp+0B70h+var_1A8], eax
0x140050afe  lea     r8, [rbp+0B70h+var_750]; struct TI_ADDRESS_INFO *
0x140050b05  lea     rax, [rbp+0B70h+arg_18]
0x140050b0c  mov     [rbp+0B70h+var_198], 4
0x140050b17  mov     [rbp+0B70h+var_1A0], rax
0x140050b1e  lea     rcx, [rbp+0B70h+var_170]; struct _EVENT_DATA_DESCRIPTOR *
0x140050b25  lea     rax, [rsp+0C70h+CreationTime]
0x140050b2a  mov     [rbp+0B70h+var_188], 8
0x140050b35  mov     [rbp+0B70h+var_190], rax
0x140050b3c  lea     rax, [rsp+0C70h+var_C3C]
0x140050b41  mov     [rbp+0B70h+var_180], rax
0x140050b48  mov     [rbp+0B70h+var_178], 4
0x140050b53  call    ?EventDataDescCreateTICallAddressInfo@CTIPlugin@@CAKPEAU_EVENT_DATA_DESCRIPTOR@@KPEBUTI_ADDRESS_INFO@@@Z; CTIPlugin::EventDataDescCreateTICallAddressInfo(_EVENT_DATA_DESCRIPTOR *,ulong,TI_ADDRESS_INFO const *)
0x140050b58  lea     rcx, [rbp+0B70h+var_1B0]
0x140050b5f  lea     r8, [rbp+0B70h+var_480]; struct TI_ADDRESS_INFO *
0x140050b66  lea     r9d, [rax+4]
0x140050b6a  mov     eax, r9d
0x140050b6d  shl     rax, 4
0x140050b71  add     rcx, rax; struct _EVENT_DATA_DESCRIPTOR *
0x140050b74  call    ?EventDataDescCreateTICallAddressInfo@CTIPlugin@@CAKPEAU_EVENT_DATA_DESCRIPTOR@@KPEBUTI_ADDRESS_INFO@@@Z; CTIPlugin::EventDataDescCreateTICallAddressInfo(_EVENT_DATA_DESCRIPTOR *,ulong,TI_ADDRESS_INFO const *)
0x140050b79  add     eax, r9d
0x140050b7c  cmp     eax, 18h
0x140050b7f  jz      short loc_140050B86
0x140050b81  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140050b86  lea     r9, [rbp+0B70h+var_1B0]
0x140050b8d  mov     r8d, 18h
0x140050b93  lea     rdx, EVENT_CFG_VIOLATION
0x140050b9a  lea     rcx, S_MICROSOFT_WINDOWS_WER_DIAG
0x140050ba1  call    cs:__imp_EtwEventWriteNoRegistration
0x140050ba7  mov     [rsp+0C70h+Wow64Process], eax
0x140050bab  test    eax, eax
0x140050bad  jz      short loc_140050BD9
0x140050baf  mov     rcx, cs:WPP_GLOBAL_Control
0x140050bb6  cmp     rcx, rdi
0x140050bb9  jz      short loc_140050BD9
0x140050bbb  test    byte ptr [rcx+1Ch], 2
0x140050bbf  jz      short loc_140050BD9
0x140050bc1  mov     rcx, [rcx+10h]
0x140050bc5  lea     r8, WPP_5d1834416bbb32ed8157f52948dd8803_Traceguids
0x140050bcc  mov     edx, 0Bh
0x140050bd1  mov     r9d, eax
0x140050bd4  call    WPP_SF_d
0x140050bd9  mov     rcx, [rbp+0B70h+var_30]
0x140050be0  xor     rcx, rsp; StackCookie
0x140050be3  call    __security_check_cookie
0x140050be8  mov     rbx, [rsp+0C70h+arg_10]
0x140050bf0  add     rsp, 0C50h
0x140050bf7  pop     r14
0x140050bf9  pop     r12
0x140050bfb  pop     rdi
0x140050bfc  pop     rsi
0x140050bfd  pop     rbp
0x140050bfe  retn
```
