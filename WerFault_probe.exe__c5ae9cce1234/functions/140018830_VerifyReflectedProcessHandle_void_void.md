# VerifyReflectedProcessHandle(void *,void *)

- ea: `0x140018830`
- end: `0x140018952`
- name: `?VerifyReflectedProcessHandle@@YAHPEAX0@Z`
- size: `290`
- prototype: `__int64 __fastcall(HANDLE Process, HANDLE ProcessHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140016cbc`

## callees

- `0x14001444c`
- `0x140018830`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140018866`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1400188e1`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140018866`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1400188e1`
- `ntdll!NtQueryInformationProcess` at `0x1400188b4`
- `ntdll!NtQueryInformationProcess` at `0x1400188b4`

## pseudocode

```c
__int64 __fastcall VerifyReflectedProcessHandle(HANDLE Process, HANDLE ProcessHandle)
{
  CUserModeHangReport *v4; // rcx
  __int64 v5; // rdx
  DWORD ProcessId; // eax
  _BYTE ProcessInformation[32]; // [rsp+30h] [rbp-38h] BYREF
  __int128 v9; // [rsp+50h] [rbp-18h]

  memset(ProcessInformation, 0, sizeof(ProcessInformation));
  v9 = 0;
  if ( !Process || !ProcessHandle )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      return 0;
    }
    v5 = 16;
    goto LABEL_19;
  }
  if ( !GetProcessId(ProcessHandle) )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      return 0;
    }
    v5 = 17;
    goto LABEL_19;
  }
  if ( NtQueryInformationProcess(ProcessHandle, ProcessBasicInformation, ProcessInformation, 0x30u, 0) < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      return 0;
    }
    v5 = 18;
    goto LABEL_19;
  }
  ProcessId = GetProcessId(Process);
  if ( ProcessId == *((_QWORD *)&v9 + 1) )
    return 1;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v5 = 19;
LABEL_19:
    WPP_SF_(*((_QWORD *)v4 + 2), v5, &WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x140018830  mov     rax, rsp
0x140018833  mov     [rax+8], rbx
0x140018837  push    rdi
0x140018838  sub     rsp, 60h
0x14001883c  xorps   xmm0, xmm0
0x14001883f  mov     rbx, rdx
0x140018842  mov     rdi, rcx
0x140018845  movups  xmmword ptr [rax-38h], xmm0
0x140018849  movups  xmmword ptr [rax-28h], xmm0
0x14001884d  movups  xmmword ptr [rax-18h], xmm0
0x140018851  test    rcx, rcx
0x140018854  jz      loc_140018917
0x14001885a  test    rdx, rdx
0x14001885d  jz      loc_140018917
0x140018863  mov     rcx, rdx; Process
0x140018866  call    cs:__imp_GetProcessId
0x14001886c  test    eax, eax
0x14001886e  jnz     short loc_14001889B
0x140018870  mov     rcx, cs:WPP_GLOBAL_Control
0x140018877  lea     rax, WPP_GLOBAL_Control
0x14001887e  cmp     rcx, rax
0x140018881  jz      loc_140018945
0x140018887  test    byte ptr [rcx+1Ch], 4
0x14001888b  jz      loc_140018945
0x140018891  mov     edx, 11h
0x140018896  jmp     loc_140018935
0x14001889b  mov     r9d, 30h ; '0'; ProcessInformationLength
0x1400188a1  mov     [rsp+68h+ReturnLength], 0; ReturnLength
0x1400188aa  lea     r8, [rsp+68h+ProcessInformation]; ProcessInformation
0x1400188af  xor     edx, edx; ProcessInformationClass
0x1400188b1  mov     rcx, rbx; ProcessHandle
0x1400188b4  call    cs:__imp_NtQueryInformationProcess
0x1400188ba  test    eax, eax
0x1400188bc  jns     short loc_1400188DE
0x1400188be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400188c5  lea     rax, WPP_GLOBAL_Control
0x1400188cc  cmp     rcx, rax
0x1400188cf  jz      short loc_140018945
0x1400188d1  test    byte ptr [rcx+1Ch], 1
0x1400188d5  jz      short loc_140018945
0x1400188d7  mov     edx, 12h
0x1400188dc  jmp     short loc_140018935
0x1400188de  mov     rcx, rdi; Process
0x1400188e1  call    cs:__imp_GetProcessId
0x1400188e7  mov     eax, eax
0x1400188e9  cmp     rax, [rsp+68h+var_10]
0x1400188ee  jz      short loc_140018910
0x1400188f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400188f7  lea     rax, WPP_GLOBAL_Control
0x1400188fe  cmp     rcx, rax
0x140018901  jz      short loc_140018945
0x140018903  test    byte ptr [rcx+1Ch], 1
0x140018907  jz      short loc_140018945
0x140018909  mov     edx, 13h
0x14001890e  jmp     short loc_140018935
0x140018910  mov     eax, 1
0x140018915  jmp     short loc_140018947
0x140018917  mov     rcx, cs:WPP_GLOBAL_Control
0x14001891e  lea     rax, WPP_GLOBAL_Control
0x140018925  cmp     rcx, rax
0x140018928  jz      short loc_140018945
0x14001892a  test    byte ptr [rcx+1Ch], 4
0x14001892e  jz      short loc_140018945
0x140018930  mov     edx, 10h
0x140018935  mov     rcx, [rcx+10h]
0x140018939  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x140018940  call    WPP_SF_
0x140018945  xor     eax, eax
0x140018947  mov     rbx, [rsp+68h+arg_0]
0x14001894c  add     rsp, 60h
0x140018950  pop     rdi
0x140018951  retn
```
