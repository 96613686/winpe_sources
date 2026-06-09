# FaxGetMessageTiffW

- ea: `0x18001e5e0`
- end: `0x18001ed2a`
- name: `FaxGetMessageTiffW`
- size: `1866`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, const WCHAR *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18001e590`

## callees

- `0x18000abe4`
- `0x18000ac14`
- `0x180014314`
- `0x18001e5e0`
- `0x180021530`
- `0x18002bab8`
- `0x18002bb58`
- `0x1800308e0`
- `0x180038d48`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18001e800`
- `RPCRT4!NdrClientCall3` at `0x18001e90e`
- `RPCRT4!NdrClientCall3` at `0x18001eb31`
- `RPCRT4!NdrClientCall3` at `0x18001e800`
- `RPCRT4!NdrClientCall3` at `0x18001e90e`
- `RPCRT4!NdrClientCall3` at `0x18001eb31`
- `KERNEL32!DeleteFileW` at `0x18001ec5b`
- `KERNEL32!DeleteFileW` at `0x18001ec5b`
- `KERNEL32!WriteFile` at `0x18001ea1d`
- `KERNEL32!WriteFile` at `0x18001ea1d`
- `KERNEL32!GetVersion` at `0x18001ebfa`
- `KERNEL32!GetVersion` at `0x18001ebfa`
- `KERNEL32!CloseHandle` at `0x18001eab2`
- `KERNEL32!CloseHandle` at `0x18001eab2`
- `KERNEL32!SetLastError` at `0x18001e6bc`
- `KERNEL32!SetLastError` at `0x18001ecd5`
- `KERNEL32!SetLastError` at `0x18001e6bc`
- `KERNEL32!SetLastError` at `0x18001ecd5`
- `KERNEL32!GetLastError` at `0x18001e717`
- `KERNEL32!GetLastError` at `0x18001ea2d`
- `KERNEL32!GetLastError` at `0x18001eac2`
- `KERNEL32!GetLastError` at `0x18001ec16`
- `KERNEL32!GetLastError` at `0x18001ec6f`
- `KERNEL32!GetLastError` at `0x18001e717`
- `KERNEL32!GetLastError` at `0x18001ea2d`
- `KERNEL32!GetLastError` at `0x18001eac2`
- `KERNEL32!GetLastError` at `0x18001ec16`
- `KERNEL32!GetLastError` at `0x18001ec6f`

## pseudocode

```c
__int64 __fastcall FaxGetMessageTiffW(__int64 a1, __int64 a2, unsigned int a3, const WCHAR *a4)
{
  __int64 v6; // rax
  _QWORD *v8; // rcx
  DWORD v9; // ecx
  DWORD LastError; // eax
  CLIENT_CALL_RETURN v11; // rbx
  void *v12; // r12
  _QWORD *v13; // rax
  _QWORD *v14; // rcx
  __int64 v15; // rdx
  __int64 Pointer_low; // r9
  HANDLE v17; // rdi
  DWORD v18; // eax
  DWORD v19; // edi
  DWORD v20; // eax
  CLIENT_CALL_RETURN v21; // rax
  int Pointer; // edi
  DWORD v23; // eax
  DWORD v24; // eax
  LPOVERLAPPED lpOverlapped; // [rsp+20h] [rbp-88h]
  int v27[2]; // [rsp+28h] [rbp-80h]
  DWORD NumberOfBytesWritten[2]; // [rsp+48h] [rbp-60h] BYREF
  int v29; // [rsp+50h] [rbp-58h]
  __int64 v30; // [rsp+58h] [rbp-50h] BYREF
  HANDLE hFile; // [rsp+60h] [rbp-48h]
  void *v32; // [rsp+68h] [rbp-40h]
  CLIENT_CALL_RETURN v33; // [rsp+70h] [rbp-38h]
  DWORD nNumberOfBytesToWrite; // [rsp+C0h] [rbp+18h] BYREF
  const WCHAR *v36; // [rsp+C8h] [rbp+20h]

  v36 = a4;
  v6 = a2;
  v30 = 0;
  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 269, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids);
    v8 = WPP_GLOBAL_Control;
    v6 = a2;
  }
  if ( a3 > 2 )
  {
    if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x1000) != 0 && *((_BYTE *)v8 + 25) >= 2u )
      WPP_SF_d(v8[2], 270, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids, a3);
LABEL_15:
    v9 = 87;
    goto LABEL_16;
  }
  if ( !v6 )
  {
    if ( v8 != &WPP_GLOBAL_Control && (*((_DWORD *)v8 + 7) & 0x1000) != 0 && *((_BYTE *)v8 + 25) >= 2u )
      WPP_SF_(v8[2], 271, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids);
    goto LABEL_15;
  }
  if ( !a1 || !*(_DWORD *)a1 || *(_DWORD *)(a1 + 16) )
  {
    SetLastError(6u);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 272, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids);
    }
    return 0;
  }
  hFile = (HANDLE)InternalSafeCreateFile(a4, 0x40000000u, 1u, 2u, 128);
  if ( hFile == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    LODWORD(v11.Pointer) = LastError;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        273,
        (unsigned int)&WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids,
        (_DWORD)a4,
        LastError);
    }
    if ( LODWORD(v11.Pointer) == 5 || LODWORD(v11.Pointer) == 32 )
      LODWORD(v11.Pointer) = 7008;
  }
  else
  {
    v12 = (void *)pMemAlloc(0x4000u);
    v32 = v12;
    if ( v12 )
    {
      v13 = *(_QWORD **)(a1 + 32);
      *(_QWORD *)NumberOfBytesWritten = 0;
      v27[0] = a3;
      v11.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x45u, 0, *v13, a2, *(_QWORD *)v27, &v30).Pointer;
      *(CLIENT_CALL_RETURN *)NumberOfBytesWritten = v11;
      v14 = WPP_GLOBAL_Control;
      if ( LODWORD(v11.Pointer) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v15 = 276;
LABEL_39:
          Pointer_low = LODWORD(v11.Pointer);
LABEL_40:
          WPP_SF_d(v14[2], v15, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids, Pointer_low);
        }
      }
      else
      {
        v17 = hFile;
        while ( 1 )
        {
          nNumberOfBytesToWrite = 0x4000;
          NumberOfBytesWritten[0] = 0;
          v33.Simple = 0;
          LODWORD(lpOverlapped) = 0x4000;
          v33.Pointer = NdrClientCall3(
                          (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                          0x47u,
                          0,
                          v30,
                          lpOverlapped,
                          v12,
                          &nNumberOfBytesToWrite).Pointer;
          LODWORD(v11.Pointer) = v33.Pointer;
          v14 = WPP_GLOBAL_Control;
          if ( LODWORD(v33.Pointer) )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v15 = 278;
              goto LABEL_39;
            }
            goto LABEL_65;
          }
          if ( !nNumberOfBytesToWrite )
            goto LABEL_65;
          if ( nNumberOfBytesToWrite > 0x4000 )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 279, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids);
            }
            LODWORD(v11.Pointer) = 111;
            goto LABEL_65;
          }
          if ( !WriteFile(v17, v12, nNumberOfBytesToWrite, NumberOfBytesWritten, 0) )
            break;
          if ( NumberOfBytesWritten[0] != nNumberOfBytesToWrite )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 281, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids);
            }
            LODWORD(v11.Pointer) = 31;
            goto LABEL_65;
          }
        }
        v18 = GetLastError();
        LODWORD(v11.Pointer) = v18;
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v15 = 280;
          Pointer_low = v18;
          goto LABEL_40;
        }
      }
    }
    else
    {
      LODWORD(v11.Pointer) = 8;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 274, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids);
      }
    }
LABEL_65:
    v19 = 0;
    if ( !CloseHandle(hFile) )
    {
      v20 = GetLastError();
      v19 = v20;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 282, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids, v20);
      }
    }
    if ( !LODWORD(v11.Pointer) )
      LODWORD(v11.Pointer) = v19;
    if ( v30 )
    {
      v33.Simple = 0;
      v21.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x48u, 0, &v30).Pointer;
      Pointer = (int)v21.Pointer;
      v33.Pointer = v21.Pointer;
      v29 = (int)v21.Pointer;
      if ( LODWORD(v21.Pointer)
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          284,
          &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids,
          LODWORD(v21.Pointer));
      }
      if ( !LODWORD(v11.Pointer) )
        LODWORD(v11.Pointer) = Pointer;
    }
    if ( v12 )
      pMemFree(v12);
    if ( !LODWORD(v11.Pointer) )
    {
      if ( (unsigned __int8)GetVersion() < 5u && !(unsigned int)TiffLimitTagNumber(a4) )
      {
        v23 = GetLastError();
        LODWORD(v11.Pointer) = v23;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 285, &WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids, v23);
        }
      }
      if ( !LODWORD(v11.Pointer) )
        return 1;
    }
    if ( !DeleteFileW(a4) )
    {
      v24 = GetLastError();
      if ( v24 != 2
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          286,
          (unsigned int)&WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids,
          (_DWORD)a4,
          v24);
      }
    }
  }
  v9 = (DWORD)v11.Pointer;
LABEL_16:
  SetLastError(v9);
  return 0;
}

```

## disassembly

```asm
0x18001e5e0  mov     r11, rsp
0x18001e5e3  mov     [r11+8], rbx
0x18001e5e7  mov     [r11+20h], r9
0x18001e5eb  mov     [r11+10h], rdx
0x18001e5ef  push    rdi
0x18001e5f0  push    r12
0x18001e5f2  push    r13
0x18001e5f4  push    r14
0x18001e5f6  push    r15
0x18001e5f8  sub     rsp, 80h
0x18001e5ff  mov     r13, r9
0x18001e602  mov     edi, r8d
0x18001e605  mov     rax, rdx
0x18001e608  mov     rbx, rcx
0x18001e60b  mov     qword ptr [r11-50h], 0
0x18001e613  lea     r15, WPP_GLOBAL_Control
0x18001e61a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e621  mov     r14d, 1000h
0x18001e627  cmp     rcx, r15
0x18001e62a  jz      short loc_18001E65C
0x18001e62c  test    [rcx+1Ch], r14d
0x18001e630  jz      short loc_18001E65C
0x18001e632  cmp     byte ptr [rcx+19h], 5
0x18001e636  jb      short loc_18001E65C
0x18001e638  mov     edx, 10Dh
0x18001e63d  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x18001e644  mov     rcx, [rcx+10h]
0x18001e648  call    WPP_SF_
0x18001e64d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e654  mov     rax, [rsp+0A8h+arg_8]
0x18001e65c  cmp     edi, 2
0x18001e65f  jbe     short loc_18001E68C
0x18001e661  cmp     rcx, r15
0x18001e664  jz      short loc_18001E6B7
0x18001e666  test    [rcx+1Ch], r14d
0x18001e66a  jz      short loc_18001E6B7
0x18001e66c  cmp     byte ptr [rcx+19h], 2
0x18001e670  jb      short loc_18001E6B7
0x18001e672  mov     edx, 10Eh
0x18001e677  mov     r9d, edi
0x18001e67a  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x18001e681  mov     rcx, [rcx+10h]
0x18001e685  call    WPP_SF_d
0x18001e68a  jmp     short loc_18001E6B7
0x18001e68c  test    rax, rax
0x18001e68f  jnz     short loc_18001E6CD
0x18001e691  cmp     rcx, r15
0x18001e694  jz      short loc_18001E6B7
0x18001e696  test    [rcx+1Ch], r14d
0x18001e69a  jz      short loc_18001E6B7
0x18001e69c  cmp     byte ptr [rcx+19h], 2
0x18001e6a0  jb      short loc_18001E6B7
0x18001e6a2  mov     edx, 10Fh
0x18001e6a7  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x18001e6ae  mov     rcx, [rcx+10h]
0x18001e6b2  call    WPP_SF_
0x18001e6b7  mov     ecx, 57h ; 'W'; dwErrCode
0x18001e6bc  call    cs:__imp_SetLastError
0x18001e6c3  nop     dword ptr [rax+rax+00h]
0x18001e6c8  jmp     loc_18001ED0E
0x18001e6cd  test    rbx, rbx
0x18001e6d0  jz      loc_18001ECD0
0x18001e6d6  cmp     dword ptr [rbx], 0
0x18001e6d9  jz      loc_18001ECD0
0x18001e6df  cmp     dword ptr [rbx+10h], 0
0x18001e6e3  jnz     loc_18001ECD0
0x18001e6e9  mov     [rsp+0A8h+var_80], 80h; int
0x18001e6f1  mov     dword ptr [rsp+0A8h+lpOverlapped], 2; DWORD
0x18001e6f9  mov     edx, 40000000h; dwDesiredAccess
0x18001e6fe  mov     r8d, 1; dwShareMode
0x18001e704  mov     rcx, r13; lpFileName
0x18001e707  call    InternalSafeCreateFile
0x18001e70c  mov     [rsp+0A8h+hFile], rax
0x18001e711  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001e715  jnz     short loc_18001E76F
0x18001e717  call    cs:__imp_GetLastError
0x18001e71e  nop     dword ptr [rax+rax+00h]
0x18001e723  mov     ebx, eax
0x18001e725  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e72c  cmp     rcx, r15
0x18001e72f  jz      short loc_18001E759
0x18001e731  test    [rcx+1Ch], r14d
0x18001e735  jz      short loc_18001E759
0x18001e737  cmp     byte ptr [rcx+19h], 2
0x18001e73b  jb      short loc_18001E759
0x18001e73d  mov     edx, 111h
0x18001e742  mov     dword ptr [rsp+0A8h+lpOverlapped], eax
0x18001e746  mov     r9, r13
0x18001e749  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x18001e750  mov     rcx, [rcx+10h]
0x18001e754  call    WPP_SF_Sd
0x18001e759  cmp     ebx, 5
0x18001e75c  jz      short loc_18001E763
0x18001e75e  cmp     ebx, 20h ; ' '
0x18001e761  jnz     short loc_18001E768
0x18001e763  mov     ebx, 1B60h
0x18001e768  mov     ecx, ebx
0x18001e76a  jmp     loc_18001E6BC
0x18001e76f  mov     ecx, 4000h; dwBytes
0x18001e774  call    pMemAlloc
0x18001e779  mov     r12, rax
0x18001e77c  mov     [rsp+0A8h+var_40], rax
0x18001e781  test    rax, rax
0x18001e784  jnz     short loc_18001E7C7
0x18001e786  lea     ebx, [rax+8]
0x18001e789  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e790  cmp     rcx, r15
0x18001e793  jz      loc_18001EAAB
0x18001e799  test    [rcx+1Ch], r14d
0x18001e79d  jz      loc_18001EAAB
0x18001e7a3  cmp     byte ptr [rcx+19h], 2
0x18001e7a7  jb      loc_18001EAAB
0x18001e7ad  mov     edx, 112h
0x18001e7b2  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x18001e7b9  mov     rcx, [rcx+10h]
0x18001e7bd  call    WPP_SF_
0x18001e7c2  jmp     loc_18001EAAB
0x18001e7c7  mov     rax, [rbx+20h]
0x18001e7cb  mov     qword ptr [rsp+0A8h+NumberOfBytesWritten], 0
0x18001e7d4  lea     rcx, [rsp+0A8h+var_50]
0x18001e7d9  mov     [rsp+0A8h+var_78], rcx
0x18001e7de  mov     [rsp+0A8h+var_80], edi
0x18001e7e2  mov     rcx, [rsp+0A8h+arg_8]
0x18001e7ea  mov     [rsp+0A8h+lpOverlapped], rcx
0x18001e7ef  mov     r9, [rax]
0x18001e7f2  xor     r8d, r8d; pReturnValue
0x18001e7f5  lea     edx, [r8+45h]; nProcNum
0x18001e7f9  lea     rcx, pProxyInfo; pProxyInfo
0x18001e800  call    cs:__imp_NdrClientCall3
0x18001e807  nop     dword ptr [rax+rax+00h]
0x18001e80c  mov     rbx, rax
0x18001e80f  mov     qword ptr [rsp+0A8h+NumberOfBytesWritten], rax
0x18001e814  mov     [rsp+0A8h+var_68], eax
0x18001e818  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e81f  jmp     short loc_18001E882
0x18001e821  mov     ebx, eax
0x18001e823  mov     [rsp+0A8h+var_68], eax
0x18001e827  lea     rdx, WPP_GLOBAL_Control
0x18001e82e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e835  cmp     rcx, rdx
0x18001e838  jz      short loc_18001E868
0x18001e83a  test    dword ptr [rcx+1Ch], 1000h
0x18001e841  jz      short loc_18001E868
0x18001e843  cmp     byte ptr [rcx+19h], 2
0x18001e847  jb      short loc_18001E868
0x18001e849  mov     edx, 113h
0x18001e84e  mov     r9d, eax
0x18001e851  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x18001e858  mov     rcx, [rcx+10h]
0x18001e85c  call    WPP_SF_d
0x18001e861  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e868  lea     r15, WPP_GLOBAL_Control
0x18001e86f  mov     r14d, 1000h
0x18001e875  mov     r13, [rsp+0A8h+arg_18]
0x18001e87d  mov     r12, [rsp+0A8h+var_40]
0x18001e882  test    ebx, ebx
0x18001e884  jz      short loc_18001E8C0
0x18001e886  cmp     rcx, r15
0x18001e889  jz      loc_18001EAAB
0x18001e88f  test    [rcx+1Ch], r14d
0x18001e893  jz      loc_18001EAAB
0x18001e899  cmp     byte ptr [rcx+19h], 2
0x18001e89d  jb      loc_18001EAAB
0x18001e8a3  mov     edx, 114h
0x18001e8a8  mov     r9d, ebx
0x18001e8ab  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x18001e8b2  mov     rcx, [rcx+10h]
0x18001e8b6  call    WPP_SF_d
0x18001e8bb  jmp     loc_18001EAAB
0x18001e8c0  mov     rdi, [rsp+0A8h+hFile]
0x18001e8c5  mov     [rsp+0A8h+nNumberOfBytesToWrite], 4000h
0x18001e8d0  mov     [rsp+0A8h+NumberOfBytesWritten], 0
0x18001e8d8  mov     [rsp+0A8h+var_38], 0
0x18001e8e1  lea     rax, [rsp+0A8h+nNumberOfBytesToWrite]
0x18001e8e9  mov     [rsp+0A8h+var_78], rax
0x18001e8ee  mov     qword ptr [rsp+0A8h+var_80], r12
0x18001e8f3  mov     dword ptr [rsp+0A8h+lpOverlapped], 4000h
0x18001e8fb  mov     r9, [rsp+0A8h+var_50]
0x18001e900  xor     r8d, r8d; pReturnValue
0x18001e903  lea     edx, [r8+47h]; nProcNum
0x18001e907  lea     rcx, pProxyInfo; pProxyInfo
0x18001e90e  call    cs:__imp_NdrClientCall3
0x18001e915  nop     dword ptr [rax+rax+00h]
0x18001e91a  mov     [rsp+0A8h+var_38], rax
0x18001e91f  mov     ebx, eax
0x18001e921  mov     [rsp+0A8h+var_68], eax
0x18001e925  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e92c  jmp     short loc_18001E994
0x18001e92e  mov     ebx, eax
0x18001e930  mov     [rsp+0A8h+var_68], eax
0x18001e934  lea     rdx, WPP_GLOBAL_Control
0x18001e93b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e942  cmp     rcx, rdx
0x18001e945  jz      short loc_18001E975
0x18001e947  test    dword ptr [rcx+1Ch], 1000h
0x18001e94e  jz      short loc_18001E975
0x18001e950  cmp     byte ptr [rcx+19h], 2
0x18001e954  jb      short loc_18001E975
0x18001e956  mov     edx, 115h
0x18001e95b  mov     r9d, eax
0x18001e95e  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x18001e965  mov     rcx, [rcx+10h]
0x18001e969  call    WPP_SF_d
0x18001e96e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e975  lea     r15, WPP_GLOBAL_Control
0x18001e97c  mov     r14d, 1000h
0x18001e982  mov     r13, [rsp+0A8h+arg_18]
0x18001e98a  mov     r12, [rsp+0A8h+var_40]
0x18001e98f  mov     rdi, [rsp+0A8h+hFile]
0x18001e994  test    ebx, ebx
0x18001e996  jz      short loc_18001E9BF
0x18001e998  cmp     rcx, r15
0x18001e99b  jz      loc_18001EAAB
0x18001e9a1  test    [rcx+1Ch], r14d
0x18001e9a5  jz      loc_18001EAAB
0x18001e9ab  cmp     byte ptr [rcx+19h], 2
0x18001e9af  jb      loc_18001EAAB
0x18001e9b5  mov     edx, 116h
0x18001e9ba  jmp     loc_18001E8A8
0x18001e9bf  mov     r8d, [rsp+0A8h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x18001e9c7  test    r8d, r8d
0x18001e9ca  jz      loc_18001EAAB
0x18001e9d0  cmp     r8d, 4000h
0x18001e9d7  jbe     short loc_18001EA09
0x18001e9d9  cmp     rcx, r15
0x18001e9dc  jz      short loc_18001E9FF
0x18001e9de  test    [rcx+1Ch], r14d
0x18001e9e2  jz      short loc_18001E9FF
0x18001e9e4  cmp     byte ptr [rcx+19h], 2
0x18001e9e8  jb      short loc_18001E9FF
0x18001e9ea  mov     edx, 117h
0x18001e9ef  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x18001e9f6  mov     rcx, [rcx+10h]
0x18001e9fa  call    WPP_SF_
0x18001e9ff  mov     ebx, 6Fh ; 'o'
0x18001ea04  jmp     loc_18001EAAB
0x18001ea09  mov     [rsp+0A8h+lpOverlapped], 0; lpOverlapped
0x18001ea12  lea     r9, [rsp+0A8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18001ea17  mov     rdx, r12; lpBuffer
0x18001ea1a  mov     rcx, rdi; hFile
0x18001ea1d  call    cs:__imp_WriteFile
0x18001ea24  nop     dword ptr [rax+rax+00h]
0x18001ea29  test    eax, eax
0x18001ea2b  jnz     short loc_18001EA60
0x18001ea2d  call    cs:__imp_GetLastError
0x18001ea34  nop     dword ptr [rax+rax+00h]
0x18001ea39  mov     ebx, eax
0x18001ea3b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ea42  cmp     rcx, r15
0x18001ea45  jz      short loc_18001EAAB
0x18001ea47  test    [rcx+1Ch], r14d
0x18001ea4b  jz      short loc_18001EAAB
0x18001ea4d  cmp     byte ptr [rcx+19h], 2
0x18001ea51  jb      short loc_18001EAAB
0x18001ea53  mov     edx, 118h
0x18001ea58  mov     r9d, eax
0x18001ea5b  jmp     loc_18001E8AB
0x18001ea60  mov     eax, [rsp+0A8h+NumberOfBytesWritten]
0x18001ea64  mov     r9d, [rsp+0A8h+nNumberOfBytesToWrite]
0x18001ea6c  cmp     eax, r9d
0x18001ea6f  jz      loc_18001E8C5
0x18001ea75  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ea7c  cmp     rcx, r15
0x18001ea7f  jz      short loc_18001EAA6
0x18001ea81  test    [rcx+1Ch], r14d
0x18001ea85  jz      short loc_18001EAA6
0x18001ea87  cmp     byte ptr [rcx+19h], 2
0x18001ea8b  jb      short loc_18001EAA6
0x18001ea8d  mov     edx, 119h
0x18001ea92  mov     dword ptr [rsp+0A8h+lpOverlapped], eax
0x18001ea96  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x18001ea9d  mov     rcx, [rcx+10h]
0x18001eaa1  call    WPP_SF_dd
0x18001eaa6  mov     ebx, 1Fh
0x18001eaab  xor     edi, edi
0x18001eaad  mov     rcx, [rsp+0A8h+hFile]; hObject
0x18001eab2  call    cs:__imp_CloseHandle
0x18001eab9  nop     dword ptr [rax+rax+00h]
0x18001eabe  test    eax, eax
0x18001eac0  jnz     short loc_18001EB00
0x18001eac2  call    cs:__imp_GetLastError
0x18001eac9  nop     dword ptr [rax+rax+00h]
0x18001eace  mov     edi, eax
0x18001ead0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ead7  cmp     rcx, r15
0x18001eada  jz      short loc_18001EB00
0x18001eadc  test    [rcx+1Ch], r14d
0x18001eae0  jz      short loc_18001EB00
0x18001eae2  cmp     byte ptr [rcx+19h], 2
0x18001eae6  jb      short loc_18001EB00
0x18001eae8  mov     edx, 11Ah
0x18001eaed  mov     r9d, eax
0x18001eaf0  lea     r8, WPP_bbb96673651e32d7e8cdc355e88671db_Traceguids
0x18001eaf7  mov     rcx, [rcx+10h]
0x18001eafb  call    WPP_SF_d
0x18001eb00  test    ebx, ebx
0x18001eb02  cmovz   ebx, edi
0x18001eb05  mov     [rsp+0A8h+var_68], ebx
0x18001eb09  cmp     [rsp+0A8h+var_50], 0
0x18001eb0f  jz      loc_18001EBE9
  ... truncated ...
```
