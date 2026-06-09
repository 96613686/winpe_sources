# GetFirstThreadInProcess(ulong,ulong *)

- ea: `0x14001715c`
- end: `0x140017306`
- name: `?GetFirstThreadInProcess@@YAJKPEAK@Z`
- size: `426`
- prototype: `__int64 __fastcall(unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140017998`

## callees

- `0x140002490`
- `0x14000333f`
- `0x140014ee4`
- `0x140014f14`
- `0x14001715c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017289`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017289`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32Next` at `0x140017224`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32Next` at `0x140017224`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32First` at `0x140017206`
- `api-ms-win-core-toolhelp-l1-1-0!Thread32First` at `0x140017206`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x1400171da`
- `api-ms-win-core-toolhelp-l1-1-0!CreateToolhelp32Snapshot` at `0x1400171da`

## pseudocode

```c
__int64 __fastcall GetFirstThreadInProcess(unsigned int a1, unsigned int *a2)
{
  unsigned int v4; // edi
  char *Toolhelp32Snapshot; // rbx
  DWORD th32OwnerProcessID; // eax
  signed int LastError_0; // eax
  THREADENTRY32 te; // [rsp+20h] [rbp-38h] BYREF

  memset(&te, 0, sizeof(te));
  if ( !a2 )
  {
    v4 = -2147024809;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids);
    }
    return v4;
  }
  *a2 = 0;
  Toolhelp32Snapshot = (char *)CreateToolhelp32Snapshot(4u, 0);
  if ( Toolhelp32Snapshot != (char *)-1LL && Toolhelp32Snapshot + 1 != (char *)1 )
  {
    te.dwSize = 28;
    if ( Thread32First(Toolhelp32Snapshot, &te) )
    {
      if ( te.th32OwnerProcessID == a1 )
        goto LABEL_16;
      while ( Thread32Next(Toolhelp32Snapshot, &te) )
      {
        th32OwnerProcessID = te.th32OwnerProcessID;
        if ( te.th32OwnerProcessID == a1 )
          goto LABEL_12;
      }
    }
    th32OwnerProcessID = te.th32OwnerProcessID;
LABEL_12:
    if ( th32OwnerProcessID != a1 )
    {
      v4 = -2147023728;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids, a1);
      }
      goto LABEL_17;
    }
LABEL_16:
    *a2 = te.th32ThreadID;
    v4 = 0;
LABEL_17:
    CloseHandle(Toolhelp32Snapshot);
    return v4;
  }
  LastError_0 = GetLastError_0();
  v4 = LastError_0;
  if ( LastError_0 > 0 )
    v4 = (unsigned __int16)LastError_0 | 0x80070000;
  if ( (v4 & 0x80000000) == 0 )
    v4 = -2147467259;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x14001715c  mov     [rsp+arg_10], rbx
0x140017161  mov     [rsp+arg_18], rsi
0x140017166  push    rdi
0x140017167  sub     rsp, 50h
0x14001716b  mov     rax, cs:__security_cookie
0x140017172  xor     rax, rsp
0x140017175  mov     [rsp+58h+var_18], rax
0x14001717a  xorps   xmm0, xmm0
0x14001717d  xor     eax, eax
0x14001717f  mov     rdi, rdx
0x140017182  mov     esi, ecx
0x140017184  movups  xmmword ptr [rsp+58h+te.dwSize], xmm0
0x140017189  movups  xmmword ptr [rsp+58h+te.th32OwnerProcessID], xmm0
0x14001718e  test    rdx, rdx
0x140017191  jnz     short loc_1400171D3
0x140017193  mov     edi, 80070057h
0x140017198  mov     rcx, cs:WPP_GLOBAL_Control
0x14001719f  lea     rax, WPP_GLOBAL_Control
0x1400171a6  cmp     rcx, rax
0x1400171a9  jz      loc_1400172E6
0x1400171af  test    byte ptr [rcx+1Ch], 1
0x1400171b3  jz      loc_1400172E6
0x1400171b9  mov     rcx, [rcx+10h]
0x1400171bd  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x1400171c4  mov     edx, 0Dh
0x1400171c9  call    WPP_SF_
0x1400171ce  jmp     loc_1400172E6
0x1400171d3  mov     [rdx], eax
0x1400171d5  xor     edx, edx; th32ProcessID
0x1400171d7  lea     ecx, [rdx+4]; dwFlags
0x1400171da  call    cs:__imp_CreateToolhelp32Snapshot
0x1400171e1  nop     dword ptr [rax+rax+00h]
0x1400171e6  mov     rbx, rax
0x1400171e9  inc     rax
0x1400171ec  cmp     rax, 1
0x1400171f0  jbe     loc_140017297
0x1400171f6  lea     rdx, [rsp+58h+te]; lpte
0x1400171fb  mov     [rsp+58h+te.dwSize], 1Ch
0x140017203  mov     rcx, rbx; hSnapshot
0x140017206  call    cs:__imp_Thread32First
0x14001720d  nop     dword ptr [rax+rax+00h]
0x140017212  test    eax, eax
0x140017214  jz      short loc_14001723E
0x140017216  cmp     [rsp+58h+te.th32OwnerProcessID], esi
0x14001721a  jz      short loc_14001727E
0x14001721c  lea     rdx, [rsp+58h+te]; lpte
0x140017221  mov     rcx, rbx; hSnapshot
0x140017224  call    cs:__imp_Thread32Next
0x14001722b  nop     dword ptr [rax+rax+00h]
0x140017230  test    eax, eax
0x140017232  jz      short loc_14001723E
0x140017234  mov     eax, [rsp+58h+te.th32OwnerProcessID]
0x140017238  cmp     eax, esi
0x14001723a  jnz     short loc_14001721C
0x14001723c  jmp     short loc_140017242
0x14001723e  mov     eax, [rsp+58h+te.th32OwnerProcessID]
0x140017242  cmp     eax, esi
0x140017244  jz      short loc_14001727E
0x140017246  mov     edi, 80070490h
0x14001724b  mov     rcx, cs:WPP_GLOBAL_Control
0x140017252  lea     rax, WPP_GLOBAL_Control
0x140017259  cmp     rcx, rax
0x14001725c  jz      short loc_140017286
0x14001725e  test    byte ptr [rcx+1Ch], 1
0x140017262  jz      short loc_140017286
0x140017264  mov     rcx, [rcx+10h]
0x140017268  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x14001726f  mov     edx, 0Fh
0x140017274  mov     r9d, esi
0x140017277  call    WPP_SF_d
0x14001727c  jmp     short loc_140017286
0x14001727e  mov     eax, [rsp+58h+te.th32ThreadID]
0x140017282  mov     [rdi], eax
0x140017284  xor     edi, edi
0x140017286  mov     rcx, rbx; hObject
0x140017289  call    cs:__imp_CloseHandle
0x140017290  nop     dword ptr [rax+rax+00h]
0x140017295  jmp     short loc_1400172E6
0x140017297  call    GetLastError_0
0x14001729c  mov     edi, eax
0x14001729e  test    eax, eax
0x1400172a0  jle     short loc_1400172AB
0x1400172a2  movzx   edi, ax
0x1400172a5  or      edi, 80070000h
0x1400172ab  test    edi, edi
0x1400172ad  mov     eax, 80004005h
0x1400172b2  cmovns  edi, eax
0x1400172b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400172bc  lea     rax, WPP_GLOBAL_Control
0x1400172c3  cmp     rcx, rax
0x1400172c6  jz      short loc_1400172E6
0x1400172c8  test    byte ptr [rcx+1Ch], 1
0x1400172cc  jz      short loc_1400172E6
0x1400172ce  mov     rcx, [rcx+10h]
0x1400172d2  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x1400172d9  mov     edx, 0Eh
0x1400172de  mov     r9d, edi
0x1400172e1  call    WPP_SF_d
0x1400172e6  mov     eax, edi
0x1400172e8  mov     rcx, [rsp+58h+var_18]
0x1400172ed  xor     rcx, rsp; StackCookie
0x1400172f0  call    __security_check_cookie
0x1400172f5  mov     rbx, [rsp+58h+arg_10]
0x1400172fa  mov     rsi, [rsp+58h+arg_18]
0x1400172ff  add     rsp, 50h
0x140017303  pop     rdi
0x140017304  retn
```
