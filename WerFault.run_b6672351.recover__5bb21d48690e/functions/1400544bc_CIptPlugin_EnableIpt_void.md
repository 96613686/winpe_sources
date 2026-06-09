# CIptPlugin::EnableIpt(void)

- ea: `0x1400544bc`
- end: `0x14005472e`
- name: `?EnableIpt@CIptPlugin@@AEAAJXZ`
- size: `626`
- prototype: `__int64 __fastcall(CIptPlugin *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x140054c60`

## callees

- `0x140014ee4`
- `0x140014f14`
- `0x1400544bc`
- `0x140054d9c`
- `0x140058f58`
- `0x1400593c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140054517`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005458e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400545df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005460b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140054517`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005458e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400545df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005460b`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1400544e2`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x1400544e2`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1400545c6`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1400545c6`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140054639`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140054648`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140054639`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140054648`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140054557`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x140054557`
- `ntdll!RtlInitUnicodeString` at `0x1400546ad`
- `ntdll!RtlInitUnicodeString` at `0x1400546ca`
- `ntdll!RtlInitUnicodeString` at `0x1400546ad`
- `ntdll!RtlInitUnicodeString` at `0x1400546ca`

## pseudocode

```c
int __fastcall CIptPlugin::EnableIpt(PCWSTR *this)
{
  SC_HANDLE v2; // rax
  SC_HANDLE v3; // r14
  CUserModeHangReport *v4; // rcx
  DWORD LastError; // eax
  SC_HANDLE v6; // rax
  SC_HANDLE v7; // rbp
  BOOL started; // esi
  DWORD v9; // eax
  DWORD v10; // eax
  const WCHAR *v12; // rdx
  struct _UNICODE_STRING *p_DestinationString; // rdi
  int v14; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF
  struct _UNICODE_STRING v16; // [rsp+40h] [rbp-38h] BYREF

  v16 = 0;
  DestinationString = 0;
  v2 = OpenSCManagerW(0, 0, 1u);
  v3 = v2;
  if ( !v2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control )
      return -2147467259;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
LABEL_18:
      if ( v4 != (CUserModeHangReport *)&WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)v4 + 2), 23, WPP_3229bad3034f32dffa4581e190add958_Traceguids);
      return -2147467259;
    }
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 171, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids, LastError);
LABEL_17:
    v4 = WPP_GLOBAL_Control;
    goto LABEL_18;
  }
  v6 = OpenServiceW(v2, L"Ipt", 0x10u);
  v7 = v6;
  if ( v6 )
  {
    started = StartServiceW(v6, 0, 0);
    if ( !started )
    {
      if ( GetLastError() == 1056 )
      {
        started = 1;
      }
      else if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v10 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 173, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids, v10);
      }
    }
    CloseServiceHandle(v7);
  }
  else
  {
    started = 0;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v9 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 172, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids, v9);
    }
  }
  CloseServiceHandle(v3);
  if ( !started )
    goto LABEL_17;
  CIptPlugin::PrepareIptSettings((CIptPlugin *)this);
  if ( *((_BYTE *)this + 2880) )
  {
    v14 = StartCoreIptTracing(this[358], *((unsigned int *)this + 718), (unsigned int)(86400 * *((_DWORD *)this + 719)));
  }
  else
  {
    v12 = this[357];
    LODWORD(p_DestinationString) = 0;
    if ( v12 )
    {
      RtlInitUnicodeString(&DestinationString, v12);
      p_DestinationString = &DestinationString;
    }
    RtlInitUnicodeString(&v16, this[356]);
    v14 = RegisterExtendedImageForIptTracing(
            (unsigned int)&v16,
            (_DWORD)p_DestinationString,
            (unsigned int)this[358],
            *((_DWORD *)this + 718),
            86400 * *((_DWORD *)this + 719));
  }
  return v14 | 0x10000000;
}

```

## disassembly

```asm
0x1400544bc  push    rbx
0x1400544be  push    rbp
0x1400544bf  push    rsi
0x1400544c0  push    rdi
0x1400544c1  push    r14
0x1400544c3  sub     rsp, 50h
0x1400544c7  xor     edx, edx; lpDatabaseName
0x1400544c9  mov     rbx, rcx
0x1400544cc  xorps   xmm0, xmm0
0x1400544cf  xorps   xmm1, xmm1
0x1400544d2  xor     ecx, ecx; lpMachineName
0x1400544d4  movups  xmmword ptr [rsp+78h+var_38.Length], xmm0
0x1400544d9  lea     r8d, [rdx+1]; dwDesiredAccess
0x1400544dd  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm1
0x1400544e2  call    cs:__imp_OpenSCManagerW
0x1400544e9  nop     dword ptr [rax+rax+00h]
0x1400544ee  mov     r14, rax
0x1400544f1  test    rax, rax
0x1400544f4  jnz     short loc_140054547
0x1400544f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400544fd  lea     rdi, WPP_GLOBAL_Control
0x140054504  cmp     rcx, rdi
0x140054507  jz      loc_14005467F
0x14005450d  test    byte ptr [rcx+1Ch], 1
0x140054511  jz      loc_14005465F
0x140054517  call    cs:__imp_GetLastError
0x14005451e  nop     dword ptr [rax+rax+00h]
0x140054523  mov     rcx, cs:WPP_GLOBAL_Control
0x14005452a  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x140054531  mov     edx, 0ABh
0x140054536  mov     r9d, eax
0x140054539  mov     rcx, [rcx+10h]
0x14005453d  call    WPP_SF_d
0x140054542  jmp     loc_140054658
0x140054547  mov     r8d, 10h; dwDesiredAccess
0x14005454d  lea     rdx, ServiceName; "Ipt"
0x140054554  mov     rcx, r14; hSCManager
0x140054557  call    cs:__imp_OpenServiceW
0x14005455e  nop     dword ptr [rax+rax+00h]
0x140054563  mov     rbp, rax
0x140054566  test    rax, rax
0x140054569  jnz     short loc_1400545BE
0x14005456b  xor     esi, esi
0x14005456d  mov     rax, cs:WPP_GLOBAL_Control
0x140054574  lea     rdi, WPP_GLOBAL_Control
0x14005457b  cmp     rax, rdi
0x14005457e  jz      loc_140054645
0x140054584  test    byte ptr [rax+1Ch], 4
0x140054588  jz      loc_140054645
0x14005458e  call    cs:__imp_GetLastError
0x140054595  nop     dword ptr [rax+rax+00h]
0x14005459a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400545a1  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x1400545a8  mov     edx, 0ACh
0x1400545ad  mov     r9d, eax
0x1400545b0  mov     rcx, [rcx+10h]
0x1400545b4  call    WPP_SF_d
0x1400545b9  jmp     loc_140054645
0x1400545be  xor     r8d, r8d; lpServiceArgVectors
0x1400545c1  xor     edx, edx; dwNumServiceArgs
0x1400545c3  mov     rcx, rbp; hService
0x1400545c6  call    cs:__imp_StartServiceW
0x1400545cd  nop     dword ptr [rax+rax+00h]
0x1400545d2  lea     rdi, WPP_GLOBAL_Control
0x1400545d9  mov     esi, eax
0x1400545db  test    eax, eax
0x1400545dd  jnz     short loc_140054636
0x1400545df  call    cs:__imp_GetLastError
0x1400545e6  nop     dword ptr [rax+rax+00h]
0x1400545eb  cmp     eax, 420h
0x1400545f0  jnz     short loc_1400545F9
0x1400545f2  mov     esi, 1
0x1400545f7  jmp     short loc_140054636
0x1400545f9  mov     rax, cs:WPP_GLOBAL_Control
0x140054600  cmp     rax, rdi
0x140054603  jz      short loc_140054636
0x140054605  test    byte ptr [rax+1Ch], 4
0x140054609  jz      short loc_140054636
0x14005460b  call    cs:__imp_GetLastError
0x140054612  nop     dword ptr [rax+rax+00h]
0x140054617  mov     rcx, cs:WPP_GLOBAL_Control
0x14005461e  lea     r8, WPP_a64051d924863e2da6af6f261aa69bc0_Traceguids
0x140054625  mov     edx, 0ADh
0x14005462a  mov     r9d, eax
0x14005462d  mov     rcx, [rcx+10h]
0x140054631  call    WPP_SF_d
0x140054636  mov     rcx, rbp; hSCObject
0x140054639  call    cs:__imp_CloseServiceHandle
0x140054640  nop     dword ptr [rax+rax+00h]
0x140054645  mov     rcx, r14; hSCObject
0x140054648  call    cs:__imp_CloseServiceHandle
0x14005464f  nop     dword ptr [rax+rax+00h]
0x140054654  test    esi, esi
0x140054656  jnz     short loc_140054689
0x140054658  mov     rcx, cs:WPP_GLOBAL_Control
0x14005465f  cmp     rcx, rdi
0x140054662  jz      short loc_14005467F
0x140054664  test    byte ptr [rcx+1Ch], 1
0x140054668  jz      short loc_14005467F
0x14005466a  mov     rcx, [rcx+10h]
0x14005466e  lea     r8, WPP_3229bad3034f32dffa4581e190add958_Traceguids
0x140054675  mov     edx, 17h
0x14005467a  call    WPP_SF_
0x14005467f  mov     eax, 80004005h
0x140054684  jmp     loc_140054722
0x140054689  mov     rcx, rbx; this
0x14005468c  call    ?PrepareIptSettings@CIptPlugin@@AEAAXXZ; CIptPlugin::PrepareIptSettings(void)
0x140054691  cmp     byte ptr [rbx+0B40h], 0
0x140054698  jnz     short loc_140054701
0x14005469a  mov     rdx, [rbx+0B28h]; SourceString
0x1400546a1  xor     edi, edi
0x1400546a3  test    rdx, rdx
0x1400546a6  jz      short loc_1400546BE
0x1400546a8  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x1400546ad  call    cs:__imp_RtlInitUnicodeString
0x1400546b4  nop     dword ptr [rax+rax+00h]
0x1400546b9  lea     rdi, [rsp+78h+DestinationString]
0x1400546be  mov     rdx, [rbx+0B20h]; SourceString
0x1400546c5  lea     rcx, [rsp+78h+var_38]; DestinationString
0x1400546ca  call    cs:__imp_RtlInitUnicodeString
0x1400546d1  nop     dword ptr [rax+rax+00h]
0x1400546d6  imul    eax, [rbx+0B3Ch], 15180h
0x1400546e0  lea     rcx, [rsp+78h+var_38]
0x1400546e5  mov     r9d, [rbx+0B38h]
0x1400546ec  mov     rdx, rdi
0x1400546ef  mov     r8, [rbx+0B30h]
0x1400546f6  mov     [rsp+78h+var_58], eax
0x1400546fa  call    RegisterExtendedImageForIptTracing
0x1400546ff  jmp     short loc_14005471E
0x140054701  imul    r8d, [rbx+0B3Ch], 15180h
0x14005470c  mov     edx, [rbx+0B38h]
0x140054712  mov     rcx, [rbx+0B30h]
0x140054719  call    StartCoreIptTracing
0x14005471e  bts     eax, 1Ch
0x140054722  add     rsp, 50h
0x140054726  pop     r14
0x140054728  pop     rdi
0x140054729  pop     rsi
0x14005472a  pop     rbp
0x14005472b  pop     rbx
0x14005472c  retn
```
