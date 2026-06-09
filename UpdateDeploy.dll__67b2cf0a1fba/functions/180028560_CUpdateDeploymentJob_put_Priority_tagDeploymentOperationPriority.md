# CUpdateDeploymentJob::put_Priority(tagDeploymentOperationPriority)

- ea: `0x180028560`
- end: `0x180028717`
- name: `?put_Priority@CUpdateDeploymentJob@@UEAAJW4tagDeploymentOperationPriority@@@Z`
- size: `439`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180003180`
- `0x180007b6c`
- `0x1800110fc`
- `0x180011b44`
- `0x180028560`
- `0x18003843c`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002858a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002858a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800286f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800286f7`

## string_xrefs

- `0x1800285f8`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x18002868a`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\UpdateDeploymentJob.cpp`
- `0x1800286c8`: `Deployment job Id %ws : put_Priority request processing complete. Job Status = %ws`

## pseudocode

```c
__int64 __fastcall CUpdateDeploymentJob::put_Priority(__int64 a1, int a2)
{
  __int64 v2; // rbx
  int v5; // eax
  unsigned int v6; // edi
  __int64 v7; // rcx
  int v8; // eax
  wchar_t v10[40]; // [rsp+40h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v2 = a1 + 880;
  if ( a1 != -880 )
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 888));
  GetDeploymentJobStatusAsString(*(unsigned int *)(a1 + 872));
  Trace::GuidToString::GuidToString(v10, (const struct _GUID *)(a1 + 16));
  WUTrace(0, 0, 0x1000000, 4);
  v5 = *(_DWORD *)(a1 + 872);
  if ( v5 == 7 || (v5 & 0xFFFFFFFD) == 0 )
  {
    if ( *(_DWORD *)(a1 + 824) != a2 )
    {
      *(_DWORD *)(a1 + 824) = a2;
      if ( v5 == 2 || v5 == 7 )
      {
        v7 = *(_QWORD *)(a1 + 840);
        if ( v7 )
        {
          v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 88LL))(v7);
          if ( v8 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xE6,
              (int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
              (const char *)(unsigned int)v8);
        }
      }
      GetDeploymentJobStatusAsString(*(unsigned int *)(a1 + 872));
      Trace::GuidToString::GuidToString(v10, (const struct _GUID *)(a1 + 16));
      WUTrace(0, 0, 0x1000000, 4);
    }
    v6 = 0;
  }
  else
  {
    v6 = -2145124298;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDD,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\UpdateDeploymentJob.cpp",
      (const char *)0x80240036LL,
      0);
  }
  if ( v2 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v2 + 8));
  return v6;
}

```

## disassembly

```asm
0x180028560  mov     [rsp+arg_8], rbx
0x180028565  mov     [rsp+arg_10], rbp
0x18002856a  push    rsi
0x18002856b  push    rdi
0x18002856c  push    r14
0x18002856e  sub     rsp, 90h
0x180028575  lea     rbx, [rcx+370h]
0x18002857c  mov     esi, edx
0x18002857e  mov     rbp, rcx
0x180028581  test    rbx, rbx
0x180028584  jz      short loc_180028590
0x180028586  lea     rcx, [rbx+8]; lpCriticalSection
0x18002858a  call    cs:__imp_EnterCriticalSection
0x180028590  mov     ecx, [rbp+368h]
0x180028596  call    GetDeploymentJobStatusAsString
0x18002859b  lea     rcx, [rsp+0A8h+var_68]; this
0x1800285a0  mov     rdi, rax
0x1800285a3  lea     rdx, [rbp+10h]; struct _GUID *
0x1800285a7  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x1800285ac  mov     [rsp+0A8h+var_70], rdi
0x1800285b1  xor     edx, edx
0x1800285b3  mov     [rsp+0A8h+var_78], rax
0x1800285b8  xor     ecx, ecx
0x1800285ba  lea     rax, aDeploymentJobI_5; "Deployment job Id %ws : put_Priority re"...
0x1800285c1  mov     r8d, 1000000h
0x1800285c7  mov     [rsp+0A8h+var_80], rax
0x1800285cc  lea     r9d, [rdx+4]
0x1800285d0  mov     qword ptr [rsp+0A8h+var_88], 0; int
0x1800285d9  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800285de  mov     eax, [rbp+368h]
0x1800285e4  cmp     eax, 7
0x1800285e7  jz      short loc_180028616
0x1800285e9  test    eax, 0FFFFFFFDh
0x1800285ee  jz      short loc_180028616
0x1800285f0  mov     rcx, [rsp+0A8h]; this
0x1800285f8  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x1800285ff  mov     edi, 80240036h
0x180028604  mov     edx, 0DDh; void *
0x180028609  mov     r9d, edi; char *
0x18002860c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028611  jmp     loc_1800286EE
0x180028616  cmp     [rbp+338h], esi
0x18002861c  jz      loc_1800286EC
0x180028622  mov     edx, 2
0x180028627  mov     [rbp+338h], esi
0x18002862d  cmp     eax, edx
0x18002862f  jz      short loc_180028636
0x180028631  cmp     eax, 7
0x180028634  jnz     short loc_18002869E
0x180028636  mov     rcx, [rbp+348h]
0x18002863d  test    rcx, rcx
0x180028640  jz      short loc_18002869E
0x180028642  mov     rax, [rcx]
0x180028645  mov     r8, [rax+58h]
0x180028649  test    esi, esi
0x18002864b  jz      short loc_180028674
0x18002864d  sub     esi, 1
0x180028650  jz      short loc_18002866D
0x180028652  sub     esi, 1
0x180028655  jz      short loc_180028676
0x180028657  sub     esi, 1
0x18002865a  jz      short loc_180028666
0x18002865c  cmp     esi, 1
0x18002865f  jnz     short loc_180028676
0x180028661  lea     edx, [rsi+3]
0x180028664  jmp     short loc_180028676
0x180028666  mov     edx, 3
0x18002866b  jmp     short loc_180028676
0x18002866d  mov     edx, 1
0x180028672  jmp     short loc_180028676
0x180028674  xor     edx, edx
0x180028676  mov     rax, r8
0x180028679  call    _guard_dispatch_icall
0x18002867e  test    eax, eax
0x180028680  jns     short loc_18002869E
0x180028682  mov     rcx, [rsp+0A8h]; this
0x18002868a  lea     r8, aCW1SSrcClientU_10; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180028691  mov     r9d, eax; char *
0x180028694  mov     edx, 0E6h; void *
0x180028699  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002869e  mov     ecx, [rbp+368h]
0x1800286a4  call    GetDeploymentJobStatusAsString
0x1800286a9  lea     rcx, [rsp+0A8h+var_68]; this
0x1800286ae  mov     rdi, rax
0x1800286b1  lea     rdx, [rbp+10h]; struct _GUID *
0x1800286b5  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x1800286ba  mov     [rsp+0A8h+var_70], rdi
0x1800286bf  xor     edx, edx
0x1800286c1  mov     [rsp+0A8h+var_78], rax
0x1800286c6  xor     ecx, ecx
0x1800286c8  lea     rax, aDeploymentJobI_58; "Deployment job Id %ws : put_Priority re"...
0x1800286cf  mov     r8d, 1000000h
0x1800286d5  mov     [rsp+0A8h+var_80], rax
0x1800286da  lea     r9d, [rdx+4]
0x1800286de  mov     qword ptr [rsp+0A8h+var_88], 0
0x1800286e7  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800286ec  xor     edi, edi
0x1800286ee  test    rbx, rbx
0x1800286f1  jz      short loc_1800286FD
0x1800286f3  lea     rcx, [rbx+8]; lpCriticalSection
0x1800286f7  call    cs:__imp_LeaveCriticalSection
0x1800286fd  lea     r11, [rsp+0A8h+var_18]
0x180028705  mov     eax, edi
0x180028707  mov     rbx, [r11+28h]
0x18002870b  mov     rbp, [r11+30h]
0x18002870f  mov     rsp, r11
0x180028712  pop     r14
0x180028714  pop     rdi
0x180028715  pop     rsi
0x180028716  retn
```
