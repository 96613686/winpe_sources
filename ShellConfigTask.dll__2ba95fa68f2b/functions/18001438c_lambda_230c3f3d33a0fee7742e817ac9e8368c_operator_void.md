# _lambda_230c3f3d33a0fee7742e817ac9e8368c_::operator()(void)

- ea: `0x18001438c`
- end: `0x180014486`
- name: `??R_lambda_230c3f3d33a0fee7742e817ac9e8368c_@@QEBA@XZ`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001f1c4`

## callees

- `0x18000f1a4`
- `0x180012efc`
- `0x18001438c`
- `0x18001c988`
- `0x18001d048`
- `0x18002062c`
- `0x18002189c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014475`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180014475`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014448`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180014448`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x180014403`
- `api-ms-win-shcore-registry-l1-1-0!SHDeleteValueW` at `0x180014403`
- `DismApi!DismCloseSession` at `0x18001439e`
- `DismApi!DismCloseSession` at `0x18001439e`

## string_xrefs

- `0x18001441e`: `pcshell\shell\aix\shellconfigtask\lib\RecallTaskHandlerHelpers.h`

## pseudocode

```c
void __fastcall _lambda_230c3f3d33a0fee7742e817ac9e8368c_::operator()(unsigned int **a1)
{
  AIXPolicyHelper *v2; // rcx
  unsigned int *v3; // rax
  AIXPolicyHelper *v4; // rcx
  int v5; // eax
  bool v6; // sf
  __int64 v7; // rbx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v10; // [rsp+30h] [rbp+8h] BYREF

  DismCloseSession(**a1);
  if ( !*a1[1] )
  {
    v10 = 4;
    wil::wnf_publish_nothrow<int>(v2, &v10);
  }
  v3 = a1[1];
  if ( !*v3 || *v3 == 1 && (AIXPolicyHelper::IsDeviceITManaged(v2) || AIXPolicyHelper::IsPolicyConfigured(v4)) )
  {
    LOBYTE(v10) = 0;
    AIXTelemetry::SetOCVisibility<bool &>(&v10);
    v5 = SHDeleteValueW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Policies\\Servicing\\OC\\71e2046e4c01f20a72081a8dc83202405da38f"
            "a75c2e4549fbb51c9daddbe207",
           L"OOBEManaged");
    v6 = v5 < 0;
    if ( v5 > 0 )
    {
      v5 = (unsigned __int16)v5 | 0x80070000;
      v6 = v5 < 0;
    }
    if ( v6 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x77,
        (unsigned int)"pcshell\\shell\\aix\\shellconfigtask\\lib\\RecallTaskHandlerHelpers.h",
        (const char *)(unsigned int)v5,
        v8);
  }
  v7 = *(_QWORD *)a1[2];
  if ( v7 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(v7 + 200));
    *(_DWORD *)(v7 + 72) |= 0x300u;
    if ( *(_QWORD *)(v7 + 248) )
      tip2::details::shared_data<0,0,0>::complete_helper(v7 + 8, 2u);
    if ( v7 != -200 )
      LeaveCriticalSection((LPCRITICAL_SECTION)(v7 + 200));
  }
}

```

## disassembly

```asm
0x18001438c  mov     [rsp+arg_8], rbx
0x180014391  push    rdi; int
0x180014392  sub     rsp, 20h
0x180014396  mov     rbx, rcx
0x180014399  mov     rcx, [rcx]
0x18001439c  mov     ecx, [rcx]
0x18001439e  call    cs:__imp_DismCloseSession
0x1800143a4  mov     rax, [rbx+8]
0x1800143a8  cmp     dword ptr [rax], 0
0x1800143ab  jnz     short loc_1800143BF
0x1800143ad  lea     rdx, [rsp+28h+arg_0]
0x1800143b2  mov     [rsp+28h+arg_0], 4
0x1800143ba  call    ??$wnf_publish_nothrow@H@wil@@YAJAEBU_WNF_STATE_NAME@@AEBH@Z; wil::wnf_publish_nothrow<int>(_WNF_STATE_NAME const &,int const &)
0x1800143bf  mov     rax, [rbx+8]
0x1800143c3  cmp     dword ptr [rax], 0
0x1800143c6  jz      short loc_1800143DF
0x1800143c8  cmp     dword ptr [rax], 1
0x1800143cb  jnz     short loc_180014432
0x1800143cd  call    ?IsDeviceITManaged@AIXPolicyHelper@@YA_NXZ; AIXPolicyHelper::IsDeviceITManaged(void)
0x1800143d2  test    al, al
0x1800143d4  jnz     short loc_1800143DF
0x1800143d6  call    ?IsPolicyConfigured@AIXPolicyHelper@@YA_NXZ; AIXPolicyHelper::IsPolicyConfigured(void)
0x1800143db  test    al, al
0x1800143dd  jz      short loc_180014432
0x1800143df  lea     rcx, [rsp+28h+arg_0]
0x1800143e4  mov     byte ptr [rsp+28h+arg_0], 0
0x1800143e9  call    ??$SetOCVisibility@AEA_N@AIXTelemetry@@SAXAEA_N@Z; AIXTelemetry::SetOCVisibility<bool &>(bool &)
0x1800143ee  lea     r8, ValueName; "OOBEManaged"
0x1800143f5  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800143fc  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180014403  call    cs:__imp_SHDeleteValueW
0x180014409  test    eax, eax
0x18001440b  jle     short loc_180014417
0x18001440d  movzx   eax, ax
0x180014410  or      eax, 80070000h
0x180014415  test    eax, eax
0x180014417  jns     short loc_180014432
0x180014419  mov     rcx, [rsp+28h]; this
0x18001441e  lea     r8, aPcshellShellAi_1; "pcshell\\shell\\aix\\shellconfigtask\\l"...
0x180014425  mov     r9d, eax; char *
0x180014428  mov     edx, 77h ; 'w'; void *
0x18001442d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180014432  mov     rax, [rbx+10h]
0x180014436  mov     rbx, [rax]
0x180014439  test    rbx, rbx
0x18001443c  jz      short loc_18001447B
0x18001443e  lea     rdi, [rbx+0C8h]
0x180014445  mov     rcx, rdi; lpCriticalSection
0x180014448  call    cs:__imp_EnterCriticalSection
0x18001444e  or      dword ptr [rbx+48h], 300h
0x180014455  cmp     qword ptr [rbx+0F8h], 0
0x18001445d  jz      short loc_18001446D
0x18001445f  mov     edx, 2
0x180014464  lea     rcx, [rbx+8]
0x180014468  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18001446d  test    rdi, rdi
0x180014470  jz      short loc_18001447B
0x180014472  mov     rcx, rdi; lpCriticalSection
0x180014475  call    cs:__imp_LeaveCriticalSection
0x18001447b  mov     rbx, [rsp+28h+arg_8]
0x180014480  add     rsp, 20h
0x180014484  pop     rdi
0x180014485  retn
```
