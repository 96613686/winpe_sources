# InstallStoreFile

- ea: `0x18000d060`
- end: `0x18000d3d7`
- name: `InstallStoreFile`
- size: `887`
- prototype: `__int64 __fastcall(__int64, const unsigned __int16 *, const unsigned __int16 *, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18000d3e0`

## callees

- `0x1800038c8`
- `0x180004d70`
- `0x180004dec`
- `0x180004e2c`
- `0x18000bdec`
- `0x18000bf9c`
- `0x18000d060`
- `0x18000ea18`
- `0x18000ed9c`
- `0x18000ede8`
- `0x18001031c`
- `0x180013700`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18000d358`
- `KERNEL32!GetProcessHeap` at `0x18000d3a1`
- `KERNEL32!GetProcessHeap` at `0x18000d358`
- `KERNEL32!GetProcessHeap` at `0x18000d3a1`
- `KERNEL32!HeapFree` at `0x18000d366`
- `KERNEL32!HeapFree` at `0x18000d3af`
- `KERNEL32!HeapFree` at `0x18000d366`
- `KERNEL32!HeapFree` at `0x18000d3af`
- `KERNEL32!GetLastError` at `0x18000d28e`
- `KERNEL32!GetLastError` at `0x18000d28e`

## pseudocode

```c
__int64 __fastcall InstallStoreFile(__int64 a1, const unsigned __int16 *a2, const unsigned __int16 *a3, __int64 a4)
{
  __int64 v7; // rcx
  unsigned __int16 *v8; // r14
  unsigned int v9; // ebx
  unsigned __int16 *Guid; // rax
  unsigned __int16 *v11; // r15
  unsigned int v12; // eax
  void *v13; // rcx
  unsigned int v14; // eax
  DWORD LastError; // eax
  __int64 v16; // r8
  DWORD v17; // ebx
  __int64 v18; // rax
  HANDLE ProcessHeap; // rax
  HANDLE v20; // rax
  DWORD v22; // [rsp+40h] [rbp-39h] BYREF
  int v23; // [rsp+48h] [rbp-31h] BYREF
  char v24[16]; // [rsp+50h] [rbp-29h] BYREF
  unsigned __int16 *v25; // [rsp+60h] [rbp-19h]
  int v26; // [rsp+68h] [rbp-11h]
  int v27; // [rsp+6Ch] [rbp-Dh]
  DWORD *v28; // [rsp+70h] [rbp-9h]
  __int64 v29; // [rsp+78h] [rbp-1h]

  v23 = 0;
  v22 = 0;
  v8 = MemMallocAndCat(a2, L"\\", a3, 0);
  if ( v8 )
  {
    v9 = ValidateMetadataFileName(v7, a3, &v22);
    if ( !v9 )
    {
      if ( v22 )
      {
        Guid = MemGetGuid(a3);
        v11 = Guid;
        if ( Guid )
        {
          v12 = (*(__int64 (__fastcall **)(unsigned __int16 *, __int64, _QWORD, unsigned __int16 *, int *, __int64))(a1 + 48))(
                  Guid,
                  1,
                  0,
                  v8,
                  &v23,
                  a4);
          v9 = v12;
          if ( v12 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_SD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                27,
                (unsigned int)&WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids,
                (_DWORD)v8,
                v12);
          }
          else if ( v23 )
          {
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, &WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids, a3);
            if ( (Microsoft_Windows_UserPnpEnableBits & 0x40) != 0 )
              McTemplateU0zz_EventWriteTransfer(v13, DMRC_NEWPACKAGE, a3, v8);
            v14 = (*(__int64 (__fastcall **)(unsigned __int16 *, unsigned __int16 *, __int64))(a1 + 40))(v11, v8, 1);
            v9 = v14;
            if ( v14 == 1296 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids, v8);
              }
              FSRemoveFile(v8);
            }
            else if ( v14 )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids, v14);
              }
            }
            else
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              {
                WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids, a3);
              }
              if ( !(unsigned int)IsFileMicrosoftTrusted(v8, 0) )
              {
                LastError = GetLastError();
                v17 = LastError;
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                {
                  WPP_SF_SD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    32,
                    (unsigned int)&WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids,
                    (_DWORD)a3,
                    LastError);
                }
                if ( (Microsoft_Windows_DeviceSetupManagerEnableBits & 8) != 0 )
                {
                  v22 = v17;
                  v18 = -1;
                  do
                    ++v18;
                  while ( v11[v18] );
                  v25 = v11;
                  v26 = 2 * v18 + 2;
                  v27 = 0;
                  v28 = &v22;
                  v29 = 4;
                  McGenEventWrite_EventWriteTransfer(
                    MICROSOFT_WINDOWS_DEVICESETUPMANAGER_Context,
                    MetadataPackageSignatureFailed,
                    v16,
                    3,
                    v24);
                }
                v9 = 0;
              }
            }
          }
          else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
          {
            WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids, a3);
          }
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v11);
        }
        else
        {
          v9 = 8;
        }
LABEL_46:
        v20 = GetProcessHeap();
        HeapFree(v20, 0, v8);
        return v9;
      }
      v9 = 13;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, &WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids, v22);
    goto LABEL_46;
  }
  return 8;
}

```

## disassembly

```asm
0x18000d060  push    rbp
0x18000d062  push    rbx
0x18000d063  push    rsi
0x18000d064  push    rdi
0x18000d065  push    r12
0x18000d067  push    r13
0x18000d069  push    r14
0x18000d06b  push    r15
0x18000d06d  lea     rbp, [rsp-1Fh]
0x18000d072  sub     rsp, 98h
0x18000d079  mov     rax, cs:__security_cookie
0x18000d080  xor     rax, rsp
0x18000d083  mov     [rbp+57h+var_50], rax
0x18000d087  mov     rax, rdx
0x18000d08a  mov     r12, r9
0x18000d08d  mov     r13, rcx
0x18000d090  lea     rdx, asc_180016E08; "\\"
0x18000d097  xor     edi, edi
0x18000d099  mov     rcx, rax; unsigned __int16 *
0x18000d09c  xor     r9d, r9d
0x18000d09f  mov     [rbp+57h+var_88], edi
0x18000d0a2  mov     rsi, r8
0x18000d0a5  mov     [rbp+57h+var_90], edi
0x18000d0a8  call    ?MemMallocAndCat@@YAPEAGPEBGZZ; MemMallocAndCat(ushort const *,...)
0x18000d0ad  mov     r14, rax
0x18000d0b0  test    rax, rax
0x18000d0b3  jnz     short loc_18000D0BD
0x18000d0b5  lea     ebx, [rdi+8]
0x18000d0b8  jmp     loc_18000D3B5
0x18000d0bd  lea     r8, [rbp+57h+var_90]
0x18000d0c1  mov     rdx, rsi
0x18000d0c4  call    ValidateMetadataFileName
0x18000d0c9  mov     r9d, [rbp+57h+var_90]
0x18000d0cd  mov     ebx, eax
0x18000d0cf  test    eax, eax
0x18000d0d1  jnz     loc_18000D373
0x18000d0d7  test    r9d, r9d
0x18000d0da  jz      loc_18000D36E
0x18000d0e0  mov     rcx, rsi; unsigned __int16 *
0x18000d0e3  call    ?MemGetGuid@@YAPEAGPEBG@Z; MemGetGuid(ushort const *)
0x18000d0e8  mov     r15, rax
0x18000d0eb  test    rax, rax
0x18000d0ee  jnz     short loc_18000D0F8
0x18000d0f0  lea     ebx, [rax+8]
0x18000d0f3  jmp     loc_18000D3A1
0x18000d0f8  xor     r8d, r8d
0x18000d0fb  mov     [rsp+0D0h+var_A8], r12
0x18000d100  lea     rax, [rbp+57h+var_88]
0x18000d104  mov     r9, r14
0x18000d107  mov     [rsp+0D0h+var_B0], rax
0x18000d10c  mov     rcx, r15
0x18000d10f  mov     rax, [r13+30h]
0x18000d113  lea     edx, [r8+1]
0x18000d117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d11c  mov     ebx, eax
0x18000d11e  test    eax, eax
0x18000d120  jz      short loc_18000D164
0x18000d122  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d129  lea     rdi, WPP_GLOBAL_Control
0x18000d130  cmp     rcx, rdi
0x18000d133  jz      loc_18000D358
0x18000d139  test    byte ptr [rcx+1Ch], 1
0x18000d13d  jz      loc_18000D358
0x18000d143  mov     rcx, [rcx+10h]
0x18000d147  lea     r8, WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids
0x18000d14e  mov     edx, 1Bh
0x18000d153  mov     dword ptr [rsp+0D0h+var_B0], eax
0x18000d157  mov     r9, r14
0x18000d15a  call    WPP_SF_SD
0x18000d15f  jmp     loc_18000D358
0x18000d164  cmp     [rbp+57h+var_88], edi
0x18000d167  jz      loc_18000D327
0x18000d16d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d174  lea     rdi, WPP_GLOBAL_Control
0x18000d17b  cmp     rcx, rdi
0x18000d17e  jz      short loc_18000D19E
0x18000d180  test    byte ptr [rcx+1Ch], 8
0x18000d184  jz      short loc_18000D19E
0x18000d186  mov     rcx, [rcx+10h]
0x18000d18a  lea     r8, WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids
0x18000d191  mov     edx, 1Ch
0x18000d196  mov     r9, rsi
0x18000d199  call    WPP_SF_S
0x18000d19e  test    cs:Microsoft_Windows_UserPnpEnableBits, 40h
0x18000d1a5  jz      short loc_18000D1B9
0x18000d1a7  mov     r9, r14
0x18000d1aa  lea     rdx, DMRC_NEWPACKAGE
0x18000d1b1  mov     r8, rsi
0x18000d1b4  call    McTemplateU0zz_EventWriteTransfer
0x18000d1b9  mov     rax, [r13+28h]
0x18000d1bd  xor     r9d, r9d
0x18000d1c0  mov     rdx, r14
0x18000d1c3  mov     [rsp+0D0h+var_B0], r12
0x18000d1c8  mov     rcx, r15
0x18000d1cb  lea     r8d, [r9+1]
0x18000d1cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d1d4  mov     ebx, eax
0x18000d1d6  cmp     eax, 510h
0x18000d1db  jnz     short loc_18000D214
0x18000d1dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d1e4  cmp     rcx, rdi
0x18000d1e7  jz      short loc_18000D207
0x18000d1e9  test    byte ptr [rcx+1Ch], 8
0x18000d1ed  jz      short loc_18000D207
0x18000d1ef  mov     rcx, [rcx+10h]
0x18000d1f3  lea     r8, WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids
0x18000d1fa  mov     edx, 1Dh
0x18000d1ff  mov     r9, r14
0x18000d202  call    WPP_SF_S
0x18000d207  mov     rcx, r14; unsigned __int16 *
0x18000d20a  call    FSRemoveFile
0x18000d20f  jmp     loc_18000D358
0x18000d214  xor     r12d, r12d
0x18000d217  test    eax, eax
0x18000d219  jz      short loc_18000D252
0x18000d21b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d222  cmp     rcx, rdi
0x18000d225  jz      loc_18000D358
0x18000d22b  test    byte ptr [rcx+1Ch], 1
0x18000d22f  jz      loc_18000D358
0x18000d235  mov     rcx, [rcx+10h]
0x18000d239  lea     edx, [r12+1Eh]
0x18000d23e  mov     r9d, eax
0x18000d241  lea     r8, WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids
0x18000d248  call    WPP_SF_d
0x18000d24d  jmp     loc_18000D358
0x18000d252  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d259  cmp     rcx, rdi
0x18000d25c  jz      short loc_18000D27C
0x18000d25e  test    byte ptr [rcx+1Ch], 8
0x18000d262  jz      short loc_18000D27C
0x18000d264  mov     rcx, [rcx+10h]
0x18000d268  lea     r8, WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids
0x18000d26f  mov     edx, 1Fh
0x18000d274  mov     r9, rsi
0x18000d277  call    WPP_SF_S
0x18000d27c  xor     edx, edx; int
0x18000d27e  mov     rcx, r14; lpFileName
0x18000d281  call    ?IsFileMicrosoftTrusted@@YAHPEBGH@Z; IsFileMicrosoftTrusted(ushort const *,int)
0x18000d286  test    eax, eax
0x18000d288  jnz     loc_18000D358
0x18000d28e  call    cs:__imp_GetLastError
0x18000d294  mov     ebx, eax
0x18000d296  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d29d  cmp     rcx, rdi
0x18000d2a0  jz      short loc_18000D2C4
0x18000d2a2  test    byte ptr [rcx+1Ch], 2
0x18000d2a6  jz      short loc_18000D2C4
0x18000d2a8  mov     rcx, [rcx+10h]
0x18000d2ac  lea     r8, WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids
0x18000d2b3  mov     edx, 20h ; ' '
0x18000d2b8  mov     dword ptr [rsp+0D0h+var_B0], eax
0x18000d2bc  mov     r9, rsi
0x18000d2bf  call    WPP_SF_SD
0x18000d2c4  test    cs:Microsoft_Windows_DeviceSetupManagerEnableBits, 8
0x18000d2cb  jz      short loc_18000D322
0x18000d2cd  mov     [rbp+57h+var_90], ebx
0x18000d2d0  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d2d4  inc     rax
0x18000d2d7  cmp     [r15+rax*2], r12w
0x18000d2dc  jnz     short loc_18000D2D4
0x18000d2de  lea     eax, ds:2[rax*2]
0x18000d2e5  mov     [rbp+57h+var_70], r15
0x18000d2e9  mov     [rbp+57h+var_68], eax
0x18000d2ec  lea     rdx, MetadataPackageSignatureFailed
0x18000d2f3  lea     rax, [rbp+57h+var_90]
0x18000d2f7  mov     [rbp+57h+var_64], r12d
0x18000d2fb  mov     [rbp+57h+var_60], rax
0x18000d2ff  lea     rcx, MICROSOFT_WINDOWS_DEVICESETUPMANAGER_Context
0x18000d306  lea     rax, [rbp+57h+var_80]
0x18000d30a  mov     [rbp+57h+var_58], 4
0x18000d312  mov     r9d, 3
0x18000d318  mov     [rsp+0D0h+var_B0], rax
0x18000d31d  call    McGenEventWrite_EventWriteTransfer
0x18000d322  mov     ebx, r12d
0x18000d325  jmp     short loc_18000D358
0x18000d327  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d32e  lea     rdi, WPP_GLOBAL_Control
0x18000d335  cmp     rcx, rdi
0x18000d338  jz      short loc_18000D358
0x18000d33a  test    byte ptr [rcx+1Ch], 8
0x18000d33e  jz      short loc_18000D358
0x18000d340  mov     rcx, [rcx+10h]
0x18000d344  lea     r8, WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids
0x18000d34b  mov     edx, 21h ; '!'
0x18000d350  mov     r9, rsi
0x18000d353  call    WPP_SF_S
0x18000d358  call    cs:__imp_GetProcessHeap
0x18000d35e  mov     r8, r15; lpMem
0x18000d361  xor     edx, edx; dwFlags
0x18000d363  mov     rcx, rax; hHeap
0x18000d366  call    cs:__imp_HeapFree
0x18000d36c  jmp     short loc_18000D3A1
0x18000d36e  mov     ebx, 0Dh
0x18000d373  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d37a  lea     rdi, WPP_GLOBAL_Control
0x18000d381  cmp     rcx, rdi
0x18000d384  jz      short loc_18000D3A1
0x18000d386  test    byte ptr [rcx+1Ch], 1
0x18000d38a  jz      short loc_18000D3A1
0x18000d38c  mov     rcx, [rcx+10h]
0x18000d390  lea     r8, WPP_9ef25192afa6373630721ca38a5a19bb_Traceguids
0x18000d397  mov     edx, 1Ah
0x18000d39c  call    WPP_SF_d
0x18000d3a1  call    cs:__imp_GetProcessHeap
0x18000d3a7  mov     r8, r14; lpMem
0x18000d3aa  xor     edx, edx; dwFlags
0x18000d3ac  mov     rcx, rax; hHeap
0x18000d3af  call    cs:__imp_HeapFree
0x18000d3b5  mov     eax, ebx
0x18000d3b7  mov     rcx, [rbp+57h+var_50]
0x18000d3bb  xor     rcx, rsp; StackCookie
0x18000d3be  call    __security_check_cookie
0x18000d3c3  add     rsp, 98h
0x18000d3ca  pop     r15
0x18000d3cc  pop     r14
0x18000d3ce  pop     r13
0x18000d3d0  pop     r12
0x18000d3d2  pop     rdi
0x18000d3d3  pop     rsi
0x18000d3d4  pop     rbx
0x18000d3d5  pop     rbp
0x18000d3d6  retn
```
