# UtilReadTEB(void *,void *,void *,ulong,ulong)

- ea: `0x140011fc8`
- end: `0x140012114`
- name: `?UtilReadTEB@@YAJPEAX00KK@Z`
- size: `332`
- prototype: `__int64 __usercall@<rax>(HANDLE hProcess@<rcx>, HANDLE ThreadHandle@<rdx>, void *lpBuffer@<r8>, unsigned int@<r9d>, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1400450ac`
- `0x140046d60`

## callees

- `0x140011fc8`
- `0x14001444c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400120b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400120b1`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140012079`
- `api-ms-win-core-memory-l1-1-0!ReadProcessMemory` at `0x140012079`
- `ntdll!NtQueryInformationThread` at `0x14001201a`
- `ntdll!NtQueryInformationThread` at `0x14001201a`

## pseudocode

```c
__int64 __fastcall UtilReadTEB(
        HANDLE hProcess,
        HANDLE ThreadHandle,
        void *lpBuffer,
        unsigned int a4,
        unsigned int nSize)
{
  __int64 v5; // rsi
  NTSTATUS InformationThread; // ebx
  signed int v9; // ebx
  signed int LastError; // eax
  _OWORD ThreadInformation[5]; // [rsp+30h] [rbp-58h] BYREF

  v5 = a4;
  memset(ThreadInformation, 0, 48);
  if ( ThreadHandle && lpBuffer )
  {
    InformationThread = NtQueryInformationThread(ThreadHandle, ThreadBasicInformation, ThreadInformation, 0x30u, 0);
    if ( InformationThread >= 0 )
    {
      if ( ReadProcessMemory(hProcess, (LPCVOID)(*((_QWORD *)&ThreadInformation[0] + 1) + v5), lpBuffer, nSize, 0) )
      {
        return 0;
      }
      else
      {
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
        }
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
        if ( v9 >= 0 )
          return (unsigned int)-2147467259;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
      }
      return (unsigned int)(InformationThread | 0x10000000);
    }
    return (unsigned int)v9;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_988ce82756cb3ec502560a762615dae0_Traceguids);
    }
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x140011fc8  push    rbx
0x140011fca  push    rbp
0x140011fcb  push    rsi
0x140011fcc  push    rdi
0x140011fcd  sub     rsp, 68h
0x140011fd1  mov     esi, r9d
0x140011fd4  xorps   xmm0, xmm0
0x140011fd7  mov     rdi, r8
0x140011fda  mov     rax, rdx
0x140011fdd  mov     rbp, rcx
0x140011fe0  movups  [rsp+88h+ThreadInformation], xmm0
0x140011fe5  movups  [rsp+88h+var_48], xmm0
0x140011fea  movups  [rsp+88h+var_38], xmm0
0x140011fef  test    rdx, rdx
0x140011ff2  jz      loc_1400120D8
0x140011ff8  test    r8, r8
0x140011ffb  jz      loc_1400120D8
0x140012001  mov     r9d, 30h ; '0'; ThreadInformationLength
0x140012007  mov     [rsp+88h+ReturnLength], 0; ReturnLength
0x140012010  lea     r8, [rsp+88h+ThreadInformation]; ThreadInformation
0x140012015  xor     edx, edx; ThreadInformationClass
0x140012017  mov     rcx, rax; ThreadHandle
0x14001201a  call    cs:__imp_NtQueryInformationThread
0x140012020  mov     ebx, eax
0x140012022  test    eax, eax
0x140012024  jns     short loc_14001205A
0x140012026  mov     rcx, cs:WPP_GLOBAL_Control
0x14001202d  lea     rax, WPP_GLOBAL_Control
0x140012034  cmp     rcx, rax
0x140012037  jz      short loc_140012054
0x140012039  test    byte ptr [rcx+1Ch], 1
0x14001203d  jz      short loc_140012054
0x14001203f  mov     rcx, [rcx+10h]
0x140012043  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x14001204a  mov     edx, 37h ; '7'
0x14001204f  call    WPP_SF_
0x140012054  bts     ebx, 1Ch
0x140012058  jmp     short loc_1400120D4
0x14001205a  mov     r9d, dword ptr [rsp+88h+nSize]; nSize
0x140012062  mov     rdx, rsi
0x140012065  add     rdx, qword ptr [rsp+88h+ThreadInformation+8]; lpBaseAddress
0x14001206a  mov     r8, rdi; lpBuffer
0x14001206d  mov     rcx, rbp; hProcess
0x140012070  mov     [rsp+88h+ReturnLength], 0; lpNumberOfBytesRead
0x140012079  call    cs:__imp_ReadProcessMemory
0x14001207f  test    eax, eax
0x140012081  jnz     short loc_1400120D2
0x140012083  mov     rcx, cs:WPP_GLOBAL_Control
0x14001208a  lea     rax, WPP_GLOBAL_Control
0x140012091  cmp     rcx, rax
0x140012094  jz      short loc_1400120B1
0x140012096  test    byte ptr [rcx+1Ch], 1
0x14001209a  jz      short loc_1400120B1
0x14001209c  mov     rcx, [rcx+10h]
0x1400120a0  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x1400120a7  mov     edx, 38h ; '8'
0x1400120ac  call    WPP_SF_
0x1400120b1  call    cs:__imp_GetLastError
0x1400120b7  mov     ebx, eax
0x1400120b9  test    eax, eax
0x1400120bb  jle     short loc_1400120C6
0x1400120bd  movzx   ebx, ax
0x1400120c0  or      ebx, 80070000h
0x1400120c6  test    ebx, ebx
0x1400120c8  mov     eax, 80004005h
0x1400120cd  cmovns  ebx, eax
0x1400120d0  jmp     short loc_1400120D4
0x1400120d2  xor     ebx, ebx
0x1400120d4  mov     eax, ebx
0x1400120d6  jmp     short loc_14001210B
0x1400120d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400120df  lea     rax, WPP_GLOBAL_Control
0x1400120e6  cmp     rcx, rax
0x1400120e9  jz      short loc_140012106
0x1400120eb  test    byte ptr [rcx+1Ch], 1
0x1400120ef  jz      short loc_140012106
0x1400120f1  mov     rcx, [rcx+10h]
0x1400120f5  lea     r8, WPP_988ce82756cb3ec502560a762615dae0_Traceguids
0x1400120fc  mov     edx, 36h ; '6'
0x140012101  call    WPP_SF_
0x140012106  mov     eax, 80070057h
0x14001210b  add     rsp, 68h
0x14001210f  pop     rdi
0x140012110  pop     rsi
0x140012111  pop     rbp
0x140012112  pop     rbx
0x140012113  retn
```
