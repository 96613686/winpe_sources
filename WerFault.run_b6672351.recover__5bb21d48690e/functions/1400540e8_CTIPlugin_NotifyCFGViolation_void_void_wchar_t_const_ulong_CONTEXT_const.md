# CTIPlugin::NotifyCFGViolation(void *,void *,wchar_t const *,ulong,_CONTEXT const *)

- ea: `0x1400540e8`
- end: `0x140054404`
- name: `?NotifyCFGViolation@CTIPlugin@@CAXPEAX0PEB_WKPEBU_CONTEXT@@@Z`
- size: `796`
- prototype: `void __usercall(void *@<rcx>, void *@<rdx>, const wchar_t *@<r8>, unsigned int@<r9d>, const struct _CONTEXT *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140054050`

## callees

- `0x140002490`
- `0x1400030f8`
- `0x140014f14`
- `0x1400166ec`
- `0x140053de4`
- `0x140053ec0`
- `0x1400540e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140054258`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140054258`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x14005422b`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x14005422b`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1400541ba`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140054203`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x1400541ba`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140054203`
- `ntdll!EtwEventWriteNoRegistration` at `0x14005439f`
- `ntdll!EtwEventWriteNoRegistration` at `0x14005439f`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x140054173`
- `api-ms-win-core-wow64-l1-1-0!IsWow64Process` at `0x140054173`

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
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  unsigned int v20; // eax
  WINBOOL Wow64Process; // [rsp+30h] [rbp-D0h] BYREF
  int v22; // [rsp+34h] [rbp-CCh] BYREF
  SIZE_T NumberOfBytesRead; // [rsp+38h] [rbp-C8h] BYREF
  struct _FILETIME ExitTime; // [rsp+40h] [rbp-C0h] BYREF
  struct _FILETIME CreationTime; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE Buffer[128]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v27; // [rsp+D0h] [rbp-30h]
  LPCVOID lpBaseAddress; // [rsp+E8h] [rbp-18h]
  _QWORD v29[90]; // [rsp+520h] [rbp+420h] BYREF
  _QWORD v30[90]; // [rsp+7F0h] [rbp+6F0h] BYREF
  const wchar_t *v31; // [rsp+AC0h] [rbp+9C0h] BYREF
  int v32; // [rsp+AC8h] [rbp+9C8h]
  int v33; // [rsp+ACCh] [rbp+9CCh]
  int *v34; // [rsp+AD0h] [rbp+9D0h]
  __int64 v35; // [rsp+AD8h] [rbp+9D8h]
  struct _FILETIME *p_CreationTime; // [rsp+AE0h] [rbp+9E0h]
  __int64 v37; // [rsp+AE8h] [rbp+9E8h]
  int *v38; // [rsp+AF0h] [rbp+9F0h]
  __int64 v39; // [rsp+AF8h] [rbp+9F8h]
  struct _EVENT_DATA_DESCRIPTOR v40; // [rsp+B00h] [rbp+A00h] BYREF
  int v41; // [rsp+C98h] [rbp+B98h] BYREF

  v41 = a4;
  v5 = a5;
  Wow64Process = 0;
  memset_0(v29, 0, 0x2C8u);
  memset_0(v30, 0, 0x2C8u);
  CreationTime = 0;
  ExitTime = 0;
  v22 = 1;
  if ( IsWow64Process(a1, &Wow64Process) && Wow64Process )
    v22 = 0;
  R8 = (const void *)v5->R8;
  NumberOfBytesRead = 0;
  if ( R8 )
  {
    Wow64Process = ReadProcessMemory(a1, R8, Buffer, 0x4D0u, &NumberOfBytesRead);
    if ( Wow64Process )
    {
      if ( NumberOfBytesRead == 1232 )
      {
        v30[0] = v27;
        if ( lpBaseAddress )
          ReadProcessMemory(a1, lpBaseAddress, v29, 8u, &NumberOfBytesRead);
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
  if ( v30[0] )
    CTIPlugin::FillCallInfo((struct TI_ADDRESS_INFO *)v30, a1, a2, 1);
  if ( v29[0] )
    CTIPlugin::FillCallInfo((struct TI_ADDRESS_INFO *)v29, a1, a2, 0);
  v31 = a3;
  v12 = -1;
  do
    ++v12;
  while ( a3[v12] );
  v33 = 0;
  v32 = 2 * v12 + 2;
  v35 = 4;
  v34 = &v41;
  v37 = 8;
  p_CreationTime = &CreationTime;
  v38 = &v22;
  v39 = 4;
  v13 = CTIPlugin::EventDataDescCreateTICallAddressInfo(&v40, v10, (const struct TI_ADDRESS_INFO *)v29);
  TICallAddressInfo = CTIPlugin::EventDataDescCreateTICallAddressInfo(
                        (struct _EVENT_DATA_DESCRIPTOR *)&(&v31)[2 * v13 + 4],
                        v14,
                        (const struct TI_ADDRESS_INFO *)v30);
  if ( (_DWORD)v19 + TICallAddressInfo != 24 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v17, v16, v18, v19);
  v20 = EtwEventWriteNoRegistration(S_MICROSOFT_WINDOWS_WER_DIAG, EVENT_CFG_VIOLATION, 24, &v31);
  Wow64Process = v20;
  if ( v20
    && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_5d1834416bbb32ed8157f52948dd8803_Traceguids, v20);
  }
}

```

## disassembly

```asm
0x1400540e8  mov     [rsp-8+arg_10], rbx
0x1400540ed  mov     [rsp-8+arg_18], r9d
0x1400540f2  push    rbp
0x1400540f3  push    rsi
0x1400540f4  push    rdi
0x1400540f5  push    r12
0x1400540f7  push    r14
0x1400540f9  lea     rbp, [rsp-0B50h]
0x140054101  sub     rsp, 0C50h
0x140054108  mov     rax, cs:__security_cookie
0x14005410f  xor     rax, rsp
0x140054112  mov     [rbp+0B70h+var_30], rax
0x140054119  mov     rdi, [rbp+0B70h+arg_20]
0x140054120  mov     rsi, r8
0x140054123  mov     r14, rdx
0x140054126  mov     rbx, rcx
0x140054129  xor     r12d, r12d
0x14005412c  lea     rcx, [rbp+0B70h+var_750]; void *
0x140054133  xor     edx, edx; Val
0x140054135  mov     [rsp+0C70h+Wow64Process], r12d
0x14005413a  mov     r8d, 2C8h; Size
0x140054140  call    memset_0
0x140054145  xor     edx, edx; Val
0x140054147  lea     rcx, [rbp+0B70h+var_480]; void *
0x14005414e  mov     r8d, 2C8h; Size
0x140054154  call    memset_0
0x140054159  lea     rdx, [rsp+0C70h+Wow64Process]; Wow64Process
0x14005415e  mov     qword ptr [rsp+0C70h+CreationTime.dwLowDateTime], r12
0x140054163  mov     rcx, rbx; hProcess
0x140054166  mov     qword ptr [rsp+0C70h+ExitTime.dwLowDateTime], r12
0x14005416b  mov     [rsp+0C70h+var_C3C], 1
0x140054173  call    cs:__imp_IsWow64Process
0x14005417a  nop     dword ptr [rax+rax+00h]
0x14005417f  test    eax, eax
0x140054181  jz      short loc_14005418F
0x140054183  cmp     [rsp+0C70h+Wow64Process], r12d
0x140054188  jz      short loc_14005418F
0x14005418a  mov     [rsp+0C70h+var_C3C], r12d
0x14005418f  mov     rdx, [rdi+0B8h]; lpBaseAddress
0x140054196  mov     [rsp+0C70h+NumberOfBytesRead], r12
0x14005419b  test    rdx, rdx
0x14005419e  jz      short loc_14005420F
0x1400541a0  lea     rax, [rsp+0C70h+NumberOfBytesRead]
0x1400541a5  mov     edi, 4D0h
0x1400541aa  mov     r9d, edi; nSize
0x1400541ad  mov     [rsp+0C70h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x1400541b2  lea     r8, [rsp+0C70h+Buffer]; lpBuffer
0x1400541b7  mov     rcx, rbx; hProcess
0x1400541ba  call    cs:__imp_ReadProcessMemory
0x1400541c1  nop     dword ptr [rax+rax+00h]
0x1400541c6  mov     [rsp+0C70h+Wow64Process], eax
0x1400541ca  test    eax, eax
0x1400541cc  jz      short loc_14005420F
0x1400541ce  cmp     [rsp+0C70h+NumberOfBytesRead], rdi
0x1400541d3  jnz     short loc_14005420F
0x1400541d5  mov     rdx, [rbp+0B70h+lpBaseAddress]; lpBaseAddress
0x1400541d9  mov     rax, [rbp+0B70h+var_BA0]
0x1400541dd  mov     [rbp+0B70h+var_480], rax
0x1400541e4  test    rdx, rdx
0x1400541e7  jz      short loc_14005420F
0x1400541e9  lea     rax, [rsp+0C70h+NumberOfBytesRead]
0x1400541ee  mov     r9d, 8; nSize
0x1400541f4  lea     r8, [rbp+0B70h+var_750]; lpBuffer
0x1400541fb  mov     [rsp+0C70h+lpNumberOfBytesRead], rax; lpNumberOfBytesRead
0x140054200  mov     rcx, rbx; hProcess
0x140054203  call    cs:__imp_ReadProcessMemory
0x14005420a  nop     dword ptr [rax+rax+00h]
0x14005420f  lea     rax, [rsp+0C70h+ExitTime]
0x140054214  mov     rcx, rbx; hProcess
0x140054217  lea     r9, [rsp+0C70h+ExitTime]; lpKernelTime
0x14005421c  mov     [rsp+0C70h+lpNumberOfBytesRead], rax; lpUserTime
0x140054221  lea     r8, [rsp+0C70h+ExitTime]; lpExitTime
0x140054226  lea     rdx, [rsp+0C70h+CreationTime]; lpCreationTime
0x14005422b  call    cs:__imp_GetProcessTimes
0x140054232  nop     dword ptr [rax+rax+00h]
0x140054237  mov     [rsp+0C70h+Wow64Process], eax
0x14005423b  lea     rdi, WPP_GLOBAL_Control
0x140054242  test    eax, eax
0x140054244  jnz     short loc_140054294
0x140054246  mov     rax, cs:WPP_GLOBAL_Control
0x14005424d  cmp     rax, rdi
0x140054250  jz      short loc_14005428F
0x140054252  test    byte ptr [rax+1Ch], 2
0x140054256  jz      short loc_14005428F
0x140054258  call    cs:__imp_GetLastError
0x14005425f  nop     dword ptr [rax+rax+00h]
0x140054264  test    eax, eax
0x140054266  jle     short loc_140054270
0x140054268  movzx   eax, ax
0x14005426b  or      eax, 80070000h
0x140054270  mov     rcx, cs:WPP_GLOBAL_Control
0x140054277  lea     r8, WPP_5d1834416bbb32ed8157f52948dd8803_Traceguids
0x14005427e  mov     edx, 0Ah
0x140054283  mov     r9d, eax
0x140054286  mov     rcx, [rcx+10h]
0x14005428a  call    WPP_SF_d
0x14005428f  mov     qword ptr [rsp+0C70h+CreationTime.dwLowDateTime], r12
0x140054294  cmp     [rbp+0B70h+var_480], r12
0x14005429b  jz      short loc_1400542B5
0x14005429d  mov     r9d, 1; int
0x1400542a3  lea     rcx, [rbp+0B70h+var_480]; struct TI_ADDRESS_INFO *
0x1400542aa  mov     r8, r14; void *
0x1400542ad  mov     rdx, rbx; void *
0x1400542b0  call    ?FillCallInfo@CTIPlugin@@CAXPEAUTI_ADDRESS_INFO@@PEAX1H@Z; CTIPlugin::FillCallInfo(TI_ADDRESS_INFO *,void *,void *,int)
0x1400542b5  cmp     [rbp+0B70h+var_750], r12
0x1400542bc  jz      short loc_1400542D3
0x1400542be  xor     r9d, r9d; int
0x1400542c1  lea     rcx, [rbp+0B70h+var_750]; struct TI_ADDRESS_INFO *
0x1400542c8  mov     r8, r14; void *
0x1400542cb  mov     rdx, rbx; void *
0x1400542ce  call    ?FillCallInfo@CTIPlugin@@CAXPEAUTI_ADDRESS_INFO@@PEAX1H@Z; CTIPlugin::FillCallInfo(TI_ADDRESS_INFO *,void *,void *,int)
0x1400542d3  mov     [rbp+0B70h+var_1B0], rsi
0x1400542da  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400542de  inc     rax
0x1400542e1  cmp     [rsi+rax*2], r12w
0x1400542e6  jnz     short loc_1400542DE
0x1400542e8  lea     eax, ds:2[rax*2]
0x1400542ef  mov     [rbp+0B70h+var_1A4], r12d
0x1400542f6  mov     [rbp+0B70h+var_1A8], eax
0x1400542fc  lea     r8, [rbp+0B70h+var_750]; struct TI_ADDRESS_INFO *
0x140054303  lea     rax, [rbp+0B70h+arg_18]
0x14005430a  mov     [rbp+0B70h+var_198], 4
0x140054315  mov     [rbp+0B70h+var_1A0], rax
0x14005431c  lea     rcx, [rbp+0B70h+var_170]; struct _EVENT_DATA_DESCRIPTOR *
0x140054323  lea     rax, [rsp+0C70h+CreationTime]
0x140054328  mov     [rbp+0B70h+var_188], 8
0x140054333  mov     [rbp+0B70h+var_190], rax
0x14005433a  lea     rax, [rsp+0C70h+var_C3C]
0x14005433f  mov     [rbp+0B70h+var_180], rax
0x140054346  mov     [rbp+0B70h+var_178], 4
0x140054351  call    ?EventDataDescCreateTICallAddressInfo@CTIPlugin@@CAKPEAU_EVENT_DATA_DESCRIPTOR@@KPEBUTI_ADDRESS_INFO@@@Z; CTIPlugin::EventDataDescCreateTICallAddressInfo(_EVENT_DATA_DESCRIPTOR *,ulong,TI_ADDRESS_INFO const *)
0x140054356  lea     rcx, [rbp+0B70h+var_1B0]
0x14005435d  lea     r8, [rbp+0B70h+var_480]; struct TI_ADDRESS_INFO *
0x140054364  lea     r9d, [rax+4]
0x140054368  mov     eax, r9d
0x14005436b  shl     rax, 4
0x14005436f  add     rcx, rax; struct _EVENT_DATA_DESCRIPTOR *
0x140054372  call    ?EventDataDescCreateTICallAddressInfo@CTIPlugin@@CAKPEAU_EVENT_DATA_DESCRIPTOR@@KPEBUTI_ADDRESS_INFO@@@Z; CTIPlugin::EventDataDescCreateTICallAddressInfo(_EVENT_DATA_DESCRIPTOR *,ulong,TI_ADDRESS_INFO const *)
0x140054377  add     eax, r9d
0x14005437a  cmp     eax, 18h
0x14005437d  jz      short loc_140054384
0x14005437f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x140054384  lea     r9, [rbp+0B70h+var_1B0]
0x14005438b  mov     r8d, 18h
0x140054391  lea     rdx, EVENT_CFG_VIOLATION
0x140054398  lea     rcx, S_MICROSOFT_WINDOWS_WER_DIAG
0x14005439f  call    cs:__imp_EtwEventWriteNoRegistration
0x1400543a6  nop     dword ptr [rax+rax+00h]
0x1400543ab  mov     [rsp+0C70h+Wow64Process], eax
0x1400543af  test    eax, eax
0x1400543b1  jz      short loc_1400543DD
0x1400543b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400543ba  cmp     rcx, rdi
0x1400543bd  jz      short loc_1400543DD
0x1400543bf  test    byte ptr [rcx+1Ch], 2
0x1400543c3  jz      short loc_1400543DD
0x1400543c5  mov     rcx, [rcx+10h]
0x1400543c9  lea     r8, WPP_5d1834416bbb32ed8157f52948dd8803_Traceguids
0x1400543d0  mov     edx, 0Bh
0x1400543d5  mov     r9d, eax
0x1400543d8  call    WPP_SF_d
0x1400543dd  mov     rcx, [rbp+0B70h+var_30]
0x1400543e4  xor     rcx, rsp; StackCookie
0x1400543e7  call    __security_check_cookie
0x1400543ec  mov     rbx, [rsp+0C70h+arg_10]
0x1400543f4  add     rsp, 0C50h
0x1400543fb  pop     r14
0x1400543fd  pop     r12
0x1400543ff  pop     rdi
0x140054400  pop     rsi
0x140054401  pop     rbp
0x140054402  retn
```
