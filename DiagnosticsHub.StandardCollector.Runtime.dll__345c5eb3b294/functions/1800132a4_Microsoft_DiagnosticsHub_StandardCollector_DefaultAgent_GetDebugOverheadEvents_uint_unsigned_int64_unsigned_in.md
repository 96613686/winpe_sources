# Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::GetDebugOverheadEvents(uint,unsigned __int64,unsigned __int64,DebugOverheadEvents &)

- ea: `0x1800132a4`
- end: `0x1800134ee`
- name: `?GetDebugOverheadEvents@DefaultAgent@StandardCollector@DiagnosticsHub@Microsoft@@AEAAXI_K0AEAUDebugOverheadEvents@@@Z`
- size: `586`
- prototype: `void __fastcall(Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent *__hidden this, unsigned int, unsigned __int64, unsigned __int64, struct DebugOverheadEvents *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180012408`

## callees

- `0x1800132a4`
- `0x18003d864`
- `0x180049b50`
- `0x18004b640`

## import_xrefs

- `KERNEL32!GetModuleHandleExW` at `0x18001331e`
- `KERNEL32!GetModuleHandleExW` at `0x18001331e`
- `KERNEL32!LeaveCriticalSection` at `0x1800134cb`
- `KERNEL32!LeaveCriticalSection` at `0x1800134cb`
- `KERNEL32!EnterCriticalSection` at `0x1800132e0`
- `KERNEL32!EnterCriticalSection` at `0x1800132e0`
- `KERNEL32!GetLastError` at `0x18001332d`
- `KERNEL32!GetLastError` at `0x18001332d`
- `KERNEL32!GetProcAddress` at `0x180013355`
- `KERNEL32!GetProcAddress` at `0x180013355`

## string_xrefs

- `0x18001334e`: `DllGetClassObject`
- `0x1800134bb`: `D:\a\_work\1\s\sources\Base\Collection\StandardCollector.Runtime\DefaultAgent.cpp`
- `0x180013315`: `DebugEventCollectionAgent.dll`
- `0x1800134b4`: `Failed to get debug overhead events. Access is denied.`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent::GetDebugOverheadEvents(
        Microsoft::DiagnosticsHub::StandardCollector::DefaultAgent *this,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        struct DebugOverheadEvents *a5)
{
  struct _RTL_CRITICAL_SECTION *v9; // rbx
  _QWORD *v10; // r14
  HMODULE v11; // rcx
  signed int LastError; // eax
  signed int v13; // edi
  FARPROC ProcAddress; // rax
  __int64 v15; // [rsp+38h] [rbp-30h] BYREF
  __int64 v16; // [rsp+40h] [rbp-28h] BYREF
  _DWORD v17[4]; // [rsp+48h] [rbp-20h] BYREF

  v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 120);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 3);
  v10 = (_QWORD *)((char *)this + 112);
  if ( !*((_QWORD *)this + 14) )
  {
    v17[0] = 56668272;
    v17[1] = 1081088253;
    v17[2] = -415954542;
    v17[3] = 2032863384;
    GetModuleHandleExW(0, L"DebugEventCollectionAgent.dll", (HMODULE *)this + 13);
    v11 = (HMODULE)*((_QWORD *)this + 13);
    if ( v11 )
    {
      ProcAddress = GetProcAddress(v11, "DllGetClassObject");
      if ( !ProcAddress )
        goto LABEL_32;
      v15 = 0;
      v13 = ((__int64 (__fastcall *)(_DWORD *, GUID *, __int64 *))ProcAddress)(
              v17,
              &GUID_00000001_0000_0000_c000_000000000046,
              &v15);
      if ( v13 >= 0 )
      {
        v16 = 0;
        v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v15 + 24LL))(
                v15,
                0,
                &GUID_9bfd2c97_c527_44ce_bd36_0be81c7d8156,
                &v16);
        if ( v13 >= 0 )
        {
          v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)v16 + 24LL))(v16, a2, v10);
          if ( v13 >= 0 )
          {
            if ( v16 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
            if ( v15 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
            goto LABEL_29;
          }
          if ( v16 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
          if ( v15 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        }
        else
        {
          if ( v16 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
          if ( v15 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
        }
      }
      else if ( v15 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      }
LABEL_23:
      if ( v13 != -2147024770 )
        goto LABEL_32;
      goto LABEL_29;
    }
    LastError = GetLastError();
    v13 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v13 = LastError;
    if ( v13 )
      goto LABEL_23;
  }
LABEL_29:
  if ( *v10
    && (*(unsigned int (__fastcall **)(_QWORD, __int64, __int64, struct DebugOverheadEvents *))(*(_QWORD *)*v10 + 24LL))(
         *v10,
         a3,
         a4,
         a5) == -2147024891 )
  {
    DiagHubCommon::LogStream::Write(
      (DiagHubCommon::LogStream *)((char *)_logger + 168),
      L"D:\\a\\_work\\1\\s\\sources\\Base\\Collection\\StandardCollector.Runtime\\DefaultAgent.cpp",
      L"Failed to get debug overhead events. Access is denied.");
  }
LABEL_32:
  LeaveCriticalSection(v9);
}

```

## disassembly

```asm
0x1800132a4  push    rbp
0x1800132a6  push    rbx
0x1800132a7  push    rsi
0x1800132a8  push    rdi
0x1800132a9  push    r12
0x1800132ab  push    r13
0x1800132ad  push    r14
0x1800132af  push    r15
0x1800132b1  mov     rbp, rsp
0x1800132b4  sub     rsp, 68h
0x1800132b8  mov     rax, cs:__security_cookie
0x1800132bf  xor     rax, rsp
0x1800132c2  mov     [rbp+var_10], rax
0x1800132c6  mov     r12, r9
0x1800132c9  mov     r15, r8
0x1800132cc  mov     esi, edx
0x1800132ce  mov     rdi, rcx
0x1800132d1  mov     r13, [rbp+arg_20]
0x1800132d5  lea     rbx, [rcx+78h]
0x1800132d9  mov     [rbp+var_38], rbx
0x1800132dd  mov     rcx, rbx; lpCriticalSection
0x1800132e0  call    cs:__imp_EnterCriticalSection
0x1800132e6  nop
0x1800132e7  lea     r14, [rdi+70h]
0x1800132eb  cmp     qword ptr [r14], 0
0x1800132ef  jnz     loc_180013481
0x1800132f5  mov     [rbp+var_20], 360B070h
0x1800132fc  mov     [rbp+var_1C], 407018FDh
0x180013303  mov     [rbp+var_18], 0E7350992h
0x18001330a  mov     [rbp+var_14], 792B0898h
0x180013311  lea     r8, [rdi+68h]; phModule
0x180013315  lea     rdx, aDebugeventcoll; "DebugEventCollectionAgent.dll"
0x18001331c  xor     ecx, ecx; dwFlags
0x18001331e  call    cs:__imp_GetModuleHandleExW
0x180013324  mov     rcx, [rdi+68h]; hModule
0x180013328  test    rcx, rcx
0x18001332b  jnz     short loc_18001334E
0x18001332d  call    cs:__imp_GetLastError
0x180013333  movzx   edi, ax
0x180013336  or      edi, 80070000h
0x18001333c  test    eax, eax
0x18001333e  cmovle  edi, eax
0x180013341  test    edi, edi
0x180013343  jz      loc_180013481
0x180013349  jmp     loc_180013449
0x18001334e  lea     rdx, aDllgetclassobj_0; "DllGetClassObject"
0x180013355  call    cs:__imp_GetProcAddress
0x18001335b  test    rax, rax
0x18001335e  jz      loc_1800134C8
0x180013364  mov     [rbp+var_30], 0
0x18001336c  lea     r8, [rbp+var_30]
0x180013370  lea     rdx, _GUID_00000001_0000_0000_c000_000000000046
0x180013377  lea     rcx, [rbp+var_20]
0x18001337b  call    cs:__guard_dispatch_icall_fptr
0x180013381  mov     edi, eax
0x180013383  test    eax, eax
0x180013385  jns     short loc_1800133A3
0x180013387  mov     rcx, [rbp+var_30]
0x18001338b  test    rcx, rcx
0x18001338e  jz      short loc_18001339E
0x180013390  mov     rdx, [rcx]
0x180013393  mov     rax, [rdx+10h]
0x180013397  call    cs:__guard_dispatch_icall_fptr
0x18001339d  nop
0x18001339e  jmp     loc_180013449
0x1800133a3  mov     [rbp+var_28], 0
0x1800133ab  mov     rcx, [rbp+var_30]
0x1800133af  mov     rax, [rcx]
0x1800133b2  lea     r9, [rbp+var_28]
0x1800133b6  lea     r8, _GUID_9bfd2c97_c527_44ce_bd36_0be81c7d8156
0x1800133bd  xor     edx, edx
0x1800133bf  mov     rax, [rax+18h]
0x1800133c3  call    cs:__guard_dispatch_icall_fptr
0x1800133c9  mov     edi, eax
0x1800133cb  test    eax, eax
0x1800133cd  jns     short loc_1800133FF
0x1800133cf  mov     rcx, [rbp+var_28]
0x1800133d3  test    rcx, rcx
0x1800133d6  jz      short loc_1800133E6
0x1800133d8  mov     rax, [rcx]
0x1800133db  mov     rax, [rax+10h]
0x1800133df  call    cs:__guard_dispatch_icall_fptr
0x1800133e5  nop
0x1800133e6  mov     rcx, [rbp+var_30]
0x1800133ea  test    rcx, rcx
0x1800133ed  jz      short loc_1800133FD
0x1800133ef  mov     rax, [rcx]
0x1800133f2  mov     rax, [rax+10h]
0x1800133f6  call    cs:__guard_dispatch_icall_fptr
0x1800133fc  nop
0x1800133fd  jmp     short loc_180013449
0x1800133ff  mov     rcx, [rbp+var_28]
0x180013403  mov     rax, [rcx]
0x180013406  mov     r8, r14
0x180013409  mov     edx, esi
0x18001340b  mov     rax, [rax+18h]
0x18001340f  call    cs:__guard_dispatch_icall_fptr
0x180013415  mov     edi, eax
0x180013417  test    eax, eax
0x180013419  jns     short loc_180013453
0x18001341b  mov     rcx, [rbp+var_28]
0x18001341f  test    rcx, rcx
0x180013422  jz      short loc_180013432
0x180013424  mov     rax, [rcx]
0x180013427  mov     rax, [rax+10h]
0x18001342b  call    cs:__guard_dispatch_icall_fptr
0x180013431  nop
0x180013432  mov     rcx, [rbp+var_30]
0x180013436  test    rcx, rcx
0x180013439  jz      short loc_180013449
0x18001343b  mov     rax, [rcx]
0x18001343e  mov     rax, [rax+10h]
0x180013442  call    cs:__guard_dispatch_icall_fptr
0x180013448  nop
0x180013449  cmp     edi, 8007007Eh
0x18001344f  jnz     short loc_1800134C8
0x180013451  jmp     short loc_180013481
0x180013453  mov     rcx, [rbp+var_28]
0x180013457  test    rcx, rcx
0x18001345a  jz      short loc_18001346A
0x18001345c  mov     rax, [rcx]
0x18001345f  mov     rax, [rax+10h]
0x180013463  call    cs:__guard_dispatch_icall_fptr
0x180013469  nop
0x18001346a  mov     rcx, [rbp+var_30]
0x18001346e  test    rcx, rcx
0x180013471  jz      short loc_180013481
0x180013473  mov     rax, [rcx]
0x180013476  mov     rax, [rax+10h]
0x18001347a  call    cs:__guard_dispatch_icall_fptr
0x180013480  nop
0x180013481  mov     rcx, [r14]
0x180013484  test    rcx, rcx
0x180013487  jz      short loc_1800134C8
0x180013489  mov     rax, [rcx]
0x18001348c  mov     r9, r13
0x18001348f  mov     r8, r12
0x180013492  mov     rdx, r15
0x180013495  mov     rax, [rax+18h]
0x180013499  call    cs:__guard_dispatch_icall_fptr
0x18001349f  cmp     eax, 80070005h
0x1800134a4  jnz     short loc_1800134C8
0x1800134a6  mov     rcx, cs:?_logger@@3AEAVLogger@DiagHubCommon@@EA; DiagHubCommon::Logger & _logger
0x1800134ad  add     rcx, 0A8h; this
0x1800134b4  lea     r8, aFailedToGetDeb; "Failed to get debug overhead events. Ac"...
0x1800134bb  lea     rdx, aDAWork1SSource_12; "D:\\a\\_work\\1\\s\\sources\\Base\\Coll"...
0x1800134c2  call    ?Write@LogStream@DiagHubCommon@@QEAAXPEBG0ZZ; DiagHubCommon::LogStream::Write(ushort const *,ushort const *,...)
0x1800134c7  nop
0x1800134c8  mov     rcx, rbx; lpCriticalSection
0x1800134cb  call    cs:__imp_LeaveCriticalSection
0x1800134d1  mov     rcx, [rbp+var_10]
0x1800134d5  xor     rcx, rsp; StackCookie
0x1800134d8  call    __security_check_cookie
0x1800134dd  add     rsp, 68h
0x1800134e1  pop     r15
0x1800134e3  pop     r14
0x1800134e5  pop     r13
0x1800134e7  pop     r12
0x1800134e9  pop     rdi
0x1800134ea  pop     rsi
0x1800134eb  pop     rbx
0x1800134ec  pop     rbp
0x1800134ed  retn
```
