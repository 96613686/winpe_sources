# VerifyReflectedProcessHandle(void *,void *)

- ea: `0x140019680`
- end: `0x1400197b5`
- name: `?VerifyReflectedProcessHandle@@YAHPEAX0@Z`
- size: `309`
- prototype: `__int64 __fastcall(HANDLE Process, HANDLE ProcessHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140017998`

## callees

- `0x140014ee4`
- `0x140019680`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1400196b6`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14001973d`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1400196b6`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14001973d`
- `ntdll!NtQueryInformationProcess` at `0x14001970a`
- `ntdll!NtQueryInformationProcess` at `0x14001970a`

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
    WPP_SF_(*((_QWORD *)v4 + 2), v5, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x140019680  mov     rax, rsp
0x140019683  mov     [rax+8], rbx
0x140019687  push    rdi
0x140019688  sub     rsp, 60h
0x14001968c  xorps   xmm0, xmm0
0x14001968f  mov     rbx, rdx
0x140019692  mov     rdi, rcx
0x140019695  movups  xmmword ptr [rax-38h], xmm0
0x140019699  movups  xmmword ptr [rax-28h], xmm0
0x14001969d  movups  xmmword ptr [rax-18h], xmm0
0x1400196a1  test    rcx, rcx
0x1400196a4  jz      loc_140019779
0x1400196aa  test    rdx, rdx
0x1400196ad  jz      loc_140019779
0x1400196b3  mov     rcx, rdx; Process
0x1400196b6  call    cs:__imp_GetProcessId
0x1400196bd  nop     dword ptr [rax+rax+00h]
0x1400196c2  test    eax, eax
0x1400196c4  jnz     short loc_1400196F1
0x1400196c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400196cd  lea     rax, WPP_GLOBAL_Control
0x1400196d4  cmp     rcx, rax
0x1400196d7  jz      loc_1400197A7
0x1400196dd  test    byte ptr [rcx+1Ch], 4
0x1400196e1  jz      loc_1400197A7
0x1400196e7  mov     edx, 11h
0x1400196ec  jmp     loc_140019797
0x1400196f1  mov     r9d, 30h ; '0'; ProcessInformationLength
0x1400196f7  mov     [rsp+68h+ReturnLength], 0; ReturnLength
0x140019700  lea     r8, [rsp+68h+ProcessInformation]; ProcessInformation
0x140019705  xor     edx, edx; ProcessInformationClass
0x140019707  mov     rcx, rbx; ProcessHandle
0x14001970a  call    cs:__imp_NtQueryInformationProcess
0x140019711  nop     dword ptr [rax+rax+00h]
0x140019716  test    eax, eax
0x140019718  jns     short loc_14001973A
0x14001971a  mov     rcx, cs:WPP_GLOBAL_Control
0x140019721  lea     rax, WPP_GLOBAL_Control
0x140019728  cmp     rcx, rax
0x14001972b  jz      short loc_1400197A7
0x14001972d  test    byte ptr [rcx+1Ch], 1
0x140019731  jz      short loc_1400197A7
0x140019733  mov     edx, 12h
0x140019738  jmp     short loc_140019797
0x14001973a  mov     rcx, rdi; Process
0x14001973d  call    cs:__imp_GetProcessId
0x140019744  nop     dword ptr [rax+rax+00h]
0x140019749  mov     eax, eax
0x14001974b  cmp     rax, [rsp+68h+var_10]
0x140019750  jz      short loc_140019772
0x140019752  mov     rcx, cs:WPP_GLOBAL_Control
0x140019759  lea     rax, WPP_GLOBAL_Control
0x140019760  cmp     rcx, rax
0x140019763  jz      short loc_1400197A7
0x140019765  test    byte ptr [rcx+1Ch], 1
0x140019769  jz      short loc_1400197A7
0x14001976b  mov     edx, 13h
0x140019770  jmp     short loc_140019797
0x140019772  mov     eax, 1
0x140019777  jmp     short loc_1400197A9
0x140019779  mov     rcx, cs:WPP_GLOBAL_Control
0x140019780  lea     rax, WPP_GLOBAL_Control
0x140019787  cmp     rcx, rax
0x14001978a  jz      short loc_1400197A7
0x14001978c  test    byte ptr [rcx+1Ch], 4
0x140019790  jz      short loc_1400197A7
0x140019792  mov     edx, 10h
0x140019797  mov     rcx, [rcx+10h]
0x14001979b  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x1400197a2  call    WPP_SF_
0x1400197a7  xor     eax, eax
0x1400197a9  mov     rbx, [rsp+68h+arg_0]
0x1400197ae  add     rsp, 60h
0x1400197b2  pop     rdi
0x1400197b3  retn
```
