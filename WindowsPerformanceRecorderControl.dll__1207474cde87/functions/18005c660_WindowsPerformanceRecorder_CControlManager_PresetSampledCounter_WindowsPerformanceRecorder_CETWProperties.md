# WindowsPerformanceRecorder::CControlManager::PresetSampledCounter(WindowsPerformanceRecorder::CETWProperties &)

- ea: `0x18005c660`
- end: `0x18005c8e2`
- name: `?PresetSampledCounter@CControlManager@WindowsPerformanceRecorder@@AEAAJAEAVCETWProperties@2@@Z`
- size: `642`
- prototype: `__int64 __fastcall(WindowsPerformanceRecorder::CControlManager *__hidden this, struct WindowsPerformanceRecorder::CETWProperties *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180032adc`

## callees

- `0x18001e6e0`
- `0x180039de4`
- `0x18004ece0`
- `0x18005aaf8`
- `0x18005c660`
- `0x18008c010`

## import_xrefs

- `ntdll!RtlAdjustPrivilege` at `0x18005c6d7`
- `ntdll!RtlAdjustPrivilege` at `0x18005c729`
- `ntdll!RtlAdjustPrivilege` at `0x18005c7f8`
- `ntdll!RtlAdjustPrivilege` at `0x18005c825`
- `ntdll!RtlAdjustPrivilege` at `0x18005c6d7`
- `ntdll!RtlAdjustPrivilege` at `0x18005c729`
- `ntdll!RtlAdjustPrivilege` at `0x18005c7f8`
- `ntdll!RtlAdjustPrivilege` at `0x18005c825`
- `ntdll!NtSetSystemInformation` at `0x18005c701`
- `ntdll!NtSetSystemInformation` at `0x18005c701`
- `ntdll!NtSetIntervalProfile` at `0x18005c70f`
- `ntdll!NtSetIntervalProfile` at `0x18005c70f`

## pseudocode

```c
__int64 __fastcall WindowsPerformanceRecorder::CControlManager::PresetSampledCounter(
        WindowsPerformanceRecorder::CControlManager *this,
        struct WindowsPerformanceRecorder::CETWProperties *a2)
{
  __int64 v2; // r13
  __int64 v4; // rdi
  __int64 v5; // r14
  ULONG v6; // r15d
  KPROFILE_SOURCE v7; // r12d
  NTSTATUS v8; // ebx
  const struct _GUID *v9; // r8
  NTSTATUS v10; // eax
  unsigned int v11; // ebx
  WindowsPerformanceRecorder::CControlManager *v12; // r15
  unsigned int v13; // r9d
  unsigned int (*TraceSetInformation)(unsigned __int64, enum _TRACE_QUERY_INFO_CLASS, void *, unsigned int); // rbx
  const struct _GUID *v15; // r8
  int v16; // ebx
  __int64 v17; // r8
  char *v19; // [rsp+28h] [rbp-58h]
  struct IControlErrorInfo *v20; // [rsp+38h] [rbp-48h]
  unsigned __int8 OldValue[8]; // [rsp+40h] [rbp-40h] BYREF
  WindowsPerformanceRecorder::CControlManager *v22; // [rsp+48h] [rbp-38h]
  _DWORD SystemInformation[2]; // [rsp+50h] [rbp-30h] BYREF
  _DWORD v24[8]; // [rsp+58h] [rbp-28h] BYREF

  v2 = *((_QWORD *)a2 + 13);
  v4 = *((_QWORD *)a2 + 12);
  v22 = this;
  if ( (unsigned int)((v2 - v4) >> 4) )
  {
    v5 = 0;
    if ( v4 != v2 )
    {
      do
      {
        v6 = *(_DWORD *)(v4 + 12);
        v7 = *(_DWORD *)(v4 + 8);
        if ( !v6 )
          goto LABEL_14;
        OldValue[0] = 0;
        v8 = RtlAdjustPrivilege(0xBu, 1u, 0, OldValue);
        if ( v8 >= 0 )
        {
          if ( v7 )
          {
            v10 = NtSetIntervalProfile(v6, v7);
          }
          else
          {
            SystemInformation[0] = 3;
            SystemInformation[1] = v6;
            v10 = NtSetSystemInformation(SystemPerformanceTraceInformation, SystemInformation, 8u);
          }
          v8 = v10;
        }
        if ( !OldValue[0] )
          RtlAdjustPrivilege(0xBu, 0, 0, OldValue);
        if ( v8 < 0 )
        {
          v11 = v8 | 0x10000000;
          v12 = v22;
          WindowsPerformanceRecorder::CControlManager::AddProviderControlWarningInfo(
            v22,
            v11,
            v9,
            0,
            *((const unsigned __int16 **)a2 + 4),
            *((const unsigned __int16 **)a2 + 40),
            0,
            v20);
          v13 = v11;
          v19 = (char *)*((_QWORD *)a2 + 4);
          if ( *((_BYTE *)a2 + 40) )
          {
            v17 = 6553;
            goto LABEL_24;
          }
          WindowsPerformanceRecorder::TraceHR(
            (WindowsPerformanceRecorder *)3,
            (unsigned __int8)"PresetSampledCounter",
            (const char *)0x199D,
            v11,
            "%ws",
            v19);
        }
        else
        {
LABEL_14:
          v12 = v22;
          if ( v7 && (unsigned int)v5 < 8 )
          {
            v24[v5] = *(_DWORD *)(v4 + 8);
            v5 = (unsigned int)(v5 + 1);
          }
        }
        v4 += 16;
      }
      while ( v4 != v2 );
      if ( (_DWORD)v5 )
      {
        OldValue[0] = 0;
        TraceSetInformation = GetTraceSetInformation();
        if ( !TraceSetInformation
          || (RtlAdjustPrivilege(0xBu, 1u, 0, OldValue),
              v16 = ((__int64 (__fastcall *)(_QWORD, __int64, _DWORD *, _QWORD))TraceSetInformation)(
                      0,
                      6,
                      v24,
                      (unsigned int)(4 * v5)),
              RtlAdjustPrivilege(0xBu, OldValue[0], 0, OldValue),
              v16) )
        {
          v11 = -984086997;
          WindowsPerformanceRecorder::CControlManager::AddProviderControlWarningInfo(
            v12,
            -984086997,
            v15,
            0,
            *((const unsigned __int16 **)a2 + 4),
            *((const unsigned __int16 **)a2 + 40),
            0,
            v20);
          v13 = -984086997;
          v19 = (char *)*((_QWORD *)a2 + 4);
          if ( *((_BYTE *)a2 + 40) )
          {
            v17 = 6578;
LABEL_24:
            WindowsPerformanceRecorder::TraceHR(
              (WindowsPerformanceRecorder *)2,
              (unsigned __int8)"PresetSampledCounter",
              (const char *)v17,
              v13,
              "%ws",
              v19);
            return v11;
          }
          WindowsPerformanceRecorder::TraceHR(
            (WindowsPerformanceRecorder *)3,
            (unsigned __int8)"PresetSampledCounter",
            (const char *)0x19B6,
            0xC558062B,
            "%ws",
            v19);
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18005c660  mov     [rsp-38h+arg_10], rbx
0x18005c665  push    rbp
0x18005c666  push    rsi
0x18005c667  push    rdi
0x18005c668  push    r12
0x18005c66a  push    r13
0x18005c66c  push    r14
0x18005c66e  push    r15
0x18005c670  mov     rbp, rsp
0x18005c673  sub     rsp, 80h
0x18005c67a  mov     rax, cs:__security_cookie
0x18005c681  xor     rax, rsp
0x18005c684  mov     [rbp+var_8], rax
0x18005c688  mov     r13, [rdx+68h]
0x18005c68c  mov     rsi, rdx
0x18005c68f  mov     rdi, [rdx+60h]
0x18005c693  mov     rax, r13
0x18005c696  sub     rax, rdi
0x18005c699  mov     [rbp+var_38], rcx
0x18005c69d  sar     rax, 4
0x18005c6a1  test    eax, eax
0x18005c6a3  jz      loc_18005C8B9
0x18005c6a9  xor     r14d, r14d
0x18005c6ac  cmp     rdi, r13
0x18005c6af  jz      loc_18005C8B9
0x18005c6b5  mov     r15d, [rdi+0Ch]
0x18005c6b9  mov     r12d, [rdi+8]
0x18005c6bd  test    r15d, r15d
0x18005c6c0  jz      loc_18005C7A1
0x18005c6c6  xor     r8d, r8d; ForThread
0x18005c6c9  mov     [rbp+OldValue], 0
0x18005c6cd  lea     r9, [rbp+OldValue]; OldValue
0x18005c6d1  mov     dl, 1; NewValue
0x18005c6d3  lea     ecx, [r8+0Bh]; Privilege
0x18005c6d7  call    cs:__imp_RtlAdjustPrivilege
0x18005c6dd  mov     ebx, eax
0x18005c6df  test    eax, eax
0x18005c6e1  js      short loc_18005C717
0x18005c6e3  test    r12d, r12d
0x18005c6e6  jnz     short loc_18005C709
0x18005c6e8  lea     r8d, [r12+8]; SystemInformationLength
0x18005c6ed  mov     [rbp+SystemInformation], 3
0x18005c6f4  lea     rdx, [rbp+SystemInformation]; SystemInformation
0x18005c6f8  mov     [rbp+var_2C], r15d
0x18005c6fc  lea     ecx, [r12+1Fh]; SystemInformationClass
0x18005c701  call    cs:__imp_NtSetSystemInformation
0x18005c707  jmp     short loc_18005C715
0x18005c709  mov     edx, r12d; ClockSource
0x18005c70c  mov     ecx, r15d; Interval
0x18005c70f  call    cs:__imp_NtSetIntervalProfile
0x18005c715  mov     ebx, eax
0x18005c717  cmp     [rbp+OldValue], 0
0x18005c71b  jnz     short loc_18005C72F
0x18005c71d  xor     edx, edx; NewValue
0x18005c71f  lea     r9, [rbp+OldValue]; OldValue
0x18005c723  xor     r8d, r8d; ForThread
0x18005c726  lea     ecx, [rdx+0Bh]; Privilege
0x18005c729  call    cs:__imp_RtlAdjustPrivilege
0x18005c72f  test    ebx, ebx
0x18005c731  jns     short loc_18005C7A1
0x18005c733  mov     rax, [rsi+140h]
0x18005c73a  bts     ebx, 1Ch
0x18005c73e  mov     r15, [rbp+var_38]
0x18005c742  xor     r9d, r9d; struct _GUID *
0x18005c745  mov     [rsp+80h+var_50], 0; unsigned __int16 *
0x18005c74e  mov     edx, ebx; int
0x18005c750  mov     [rsp+80h+var_58], rax; unsigned __int16 *
0x18005c755  mov     rcx, r15; this
0x18005c758  mov     rax, [rsi+20h]
0x18005c75c  mov     [rsp+80h+Format], rax; unsigned __int16 *
0x18005c761  call    ?AddProviderControlWarningInfo@CControlManager@WindowsPerformanceRecorder@@QEAAXJAEBU_GUID@@PEBU3@PEBG22PEAUIControlErrorInfo@@@Z; WindowsPerformanceRecorder::CControlManager::AddProviderControlWarningInfo(long,_GUID const &,_GUID const *,ushort const *,ushort const *,ushort const *,IControlErrorInfo *)
0x18005c766  cmp     byte ptr [rsi+28h], 0
0x18005c76a  lea     rdx, aPresetsampledc; "PresetSampledCounter"
0x18005c771  mov     rax, [rsi+20h]
0x18005c775  mov     r9d, ebx; unsigned int
0x18005c778  mov     [rsp+80h+var_58], rax; char *
0x18005c77d  jnz     loc_18005C889
0x18005c783  lea     r12, aWs_0; "%ws"
0x18005c78a  mov     r8d, 199Dh; char *
0x18005c790  mov     ecx, 3; this
0x18005c795  mov     [rsp+80h+Format], r12; Format
0x18005c79a  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18005c79f  jmp     short loc_18005C7C2
0x18005c7a1  mov     r15, [rbp+var_38]
0x18005c7a5  test    r12d, r12d
0x18005c7a8  lea     r12, aWs_0; "%ws"
0x18005c7af  jz      short loc_18005C7C2
0x18005c7b1  cmp     r14d, 8
0x18005c7b5  jnb     short loc_18005C7C2
0x18005c7b7  mov     eax, [rdi+8]
0x18005c7ba  mov     [rbp+r14*4+var_28], eax
0x18005c7bf  inc     r14d
0x18005c7c2  add     rdi, 10h
0x18005c7c6  cmp     rdi, r13
0x18005c7c9  jnz     loc_18005C6B5
0x18005c7cf  test    r14d, r14d
0x18005c7d2  jz      loc_18005C8B9
0x18005c7d8  mov     [rbp+OldValue], 0
0x18005c7dc  call    ?GetTraceSetInformation@@YAP6AK_KW4_TRACE_QUERY_INFO_CLASS@@PEAXK@ZXZ; GetTraceSetInformation(void)
0x18005c7e1  mov     rbx, rax
0x18005c7e4  test    rax, rax
0x18005c7e7  jz      short loc_18005C833
0x18005c7e9  xor     r8d, r8d; ForThread
0x18005c7ec  lea     r9, [rbp+OldValue]; OldValue
0x18005c7f0  mov     dl, 1; NewValue
0x18005c7f2  lea     edi, [r8+0Bh]
0x18005c7f6  mov     ecx, edi; Privilege
0x18005c7f8  call    cs:__imp_RtlAdjustPrivilege
0x18005c7fe  lea     r9d, ds:0[r14*4]
0x18005c806  xor     ecx, ecx
0x18005c808  lea     r8, [rbp+var_28]
0x18005c80c  mov     rax, rbx
0x18005c80f  lea     edx, [rdi-5]
0x18005c812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c817  mov     dl, [rbp+OldValue]; NewValue
0x18005c81a  lea     r9, [rbp+OldValue]; OldValue
0x18005c81e  xor     r8d, r8d; ForThread
0x18005c821  mov     ecx, edi; Privilege
0x18005c823  mov     ebx, eax
0x18005c825  call    cs:__imp_RtlAdjustPrivilege
0x18005c82b  test    ebx, ebx
0x18005c82d  jz      loc_18005C8B9
0x18005c833  mov     rax, [rsi+140h]
0x18005c83a  mov     ebx, 0C558062Bh
0x18005c83f  mov     [rsp+80h+var_50], 0; unsigned __int16 *
0x18005c848  xor     r9d, r9d; struct _GUID *
0x18005c84b  mov     [rsp+80h+var_58], rax; unsigned __int16 *
0x18005c850  mov     edx, ebx; int
0x18005c852  mov     rax, [rsi+20h]
0x18005c856  mov     rcx, r15; this
0x18005c859  mov     [rsp+80h+Format], rax; unsigned __int16 *
0x18005c85e  call    ?AddProviderControlWarningInfo@CControlManager@WindowsPerformanceRecorder@@QEAAXJAEBU_GUID@@PEBU3@PEBG22PEAUIControlErrorInfo@@@Z; WindowsPerformanceRecorder::CControlManager::AddProviderControlWarningInfo(long,_GUID const &,_GUID const *,ushort const *,ushort const *,ushort const *,IControlErrorInfo *)
0x18005c863  cmp     byte ptr [rsi+28h], 0
0x18005c867  lea     rdx, aPresetsampledc; "PresetSampledCounter"
0x18005c86e  mov     rcx, [rsi+20h]
0x18005c872  mov     r9d, ebx; unsigned int
0x18005c875  mov     [rsp+80h+var_58], rcx; char *
0x18005c87a  mov     [rsp+80h+Format], r12; Format
0x18005c87f  jz      short loc_18005C8A9
0x18005c881  mov     r8d, 19B2h
0x18005c887  jmp     short loc_18005C89B
0x18005c889  lea     rax, aWs_0; "%ws"
0x18005c890  mov     r8d, 1999h; char *
0x18005c896  mov     [rsp+80h+Format], rax; Format
0x18005c89b  mov     ecx, 2; this
0x18005c8a0  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18005c8a5  mov     eax, ebx
0x18005c8a7  jmp     short loc_18005C8BB
0x18005c8a9  mov     r8d, 19B6h; char *
0x18005c8af  mov     ecx, 3; this
0x18005c8b4  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x18005c8b9  xor     eax, eax
0x18005c8bb  mov     rcx, [rbp+var_8]
0x18005c8bf  xor     rcx, rsp; StackCookie
0x18005c8c2  call    __security_check_cookie
0x18005c8c7  mov     rbx, [rsp+80h+arg_10]
0x18005c8cf  add     rsp, 80h
0x18005c8d6  pop     r15
0x18005c8d8  pop     r14
0x18005c8da  pop     r13
0x18005c8dc  pop     r12
0x18005c8de  pop     rdi
0x18005c8df  pop     rsi
0x18005c8e0  pop     rbp
0x18005c8e1  retn
```
