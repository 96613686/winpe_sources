# CDriverLayerImpl::WaitForServiceStatus(SC_HANDLE__ * const,_SERVICE_STATUS_PROCESS,ulong,ulong,ulong)

- ea: `0x18000fae8`
- end: `0x18000fd11`
- name: `?WaitForServiceStatus@CDriverLayerImpl@@AEAAJQEAUSC_HANDLE__@@U_SERVICE_STATUS_PROCESS@@KKK@Z`
- size: `553`
- prototype: `int(CDriverLayerImpl *__hidden this, struct SC_HANDLE__ *const, struct _SERVICE_STATUS_PROCESS *__struct_ptr, unsigned int, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000f000`
- `0x18000f5c0`

## callees

- `0x180004374`
- `0x180008290`
- `0x18000ceac`
- `0x18000fae8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fc40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fc40`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000fb4b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000fbc3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000fbd1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000fb4b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000fbc3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000fbd1`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000fc06`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18000fc06`
- `ADVAPI32!QueryServiceStatusEx` at `0x18000fb79`
- `ADVAPI32!QueryServiceStatusEx` at `0x18000fb79`

## pseudocode

```c
__int64 __fastcall CDriverLayerImpl::WaitForServiceStatus(
        CDriverLayerImpl *this,
        struct SC_HANDLE__ *const a2,
        BYTE *a3,
        int a4)
{
  unsigned int v4; // ebx
  ULONGLONG TickCount64; // rax
  DWORD v9; // esi
  ULONGLONG v10; // rbp
  ULONGLONG v11; // rax
  DWORD v12; // edx
  CHostedCacheMsgEncoding *v13; // rcx
  signed int LastError; // eax
  DWORD pcbBytesNeeded[18]; // [rsp+30h] [rbp-48h] BYREF

  v4 = 0;
  pcbBytesNeeded[0] = 0;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 12), 39, WPP_cf1e279eb4443e5f62d342d21539bd0c_Traceguids);
  }
  TickCount64 = GetTickCount64();
  v9 = *((_DWORD *)a3 + 5);
  v10 = TickCount64;
  while ( 1 )
  {
    if ( *((_DWORD *)a3 + 1) != a4 )
      goto LABEL_31;
    if ( !QueryServiceStatusEx(a2, SC_STATUS_PROCESS_INFO, a3, 0x24u, pcbBytesNeeded) )
      break;
    if ( *((_DWORD *)a3 + 1) == 1 )
      goto LABEL_31;
    if ( *((_DWORD *)a3 + 5) <= v9 )
    {
      if ( GetTickCount64() - v10 > 0x7530 )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 42, WPP_cf1e279eb4443e5f62d342d21539bd0c_Traceguids);
LABEL_31:
          v13 = WPP_GLOBAL_Control;
          goto LABEL_32;
        }
        goto LABEL_32;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 41, WPP_cf1e279eb4443e5f62d342d21539bd0c_Traceguids);
      }
      v11 = GetTickCount64();
      v9 = *((_DWORD *)a3 + 5);
      v10 = v11;
    }
    v12 = *((_DWORD *)a3 + 6) / 0xAu;
    if ( v12 >= 0x3E8 )
    {
      if ( v12 > 0x2710 )
        v12 = 10000;
    }
    else
    {
      v12 = 1000;
    }
    Sleep(v12);
  }
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 40, WPP_cf1e279eb4443e5f62d342d21539bd0c_Traceguids, v4);
    goto LABEL_31;
  }
LABEL_32:
  if ( *((_DWORD *)a3 + 1) != 1 && (v4 & 0x80000000) == 0 )
  {
    if ( v13 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)v13 + 27) & 0x800) != 0
      && *((_BYTE *)v13 + 105) )
    {
      WPP_SF_d(*((_QWORD *)v13 + 12), 43, WPP_cf1e279eb4443e5f62d342d21539bd0c_Traceguids, 30000);
      v13 = WPP_GLOBAL_Control;
    }
    v4 = -2147024122;
  }
  if ( v13 != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)v13 + 27) & 0x800) != 0
    && *((_BYTE *)v13 + 105) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)v13 + 12), 44, WPP_cf1e279eb4443e5f62d342d21539bd0c_Traceguids, v4);
  }
  return v4;
}

```

## disassembly

```asm
0x18000fae8  mov     [rsp+arg_0], rbx
0x18000faed  push    rbp
0x18000faee  push    rsi
0x18000faef  push    rdi
0x18000faf0  push    r12
0x18000faf2  push    r13
0x18000faf4  push    r14
0x18000faf6  push    r15
0x18000faf8  sub     rsp, 40h
0x18000fafc  xor     ebx, ebx
0x18000fafe  mov     r14d, r9d
0x18000fb01  mov     [rsp+78h+var_48], ebx
0x18000fb05  mov     rdi, r8
0x18000fb08  mov     r15, rdx
0x18000fb0b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb12  lea     r13, WPP_GLOBAL_Control
0x18000fb19  mov     r12d, 800h
0x18000fb1f  cmp     rcx, r13
0x18000fb22  jz      short loc_18000FB4B
0x18000fb24  test    [rcx+6Ch], r12d
0x18000fb28  jz      short loc_18000FB4B
0x18000fb2a  cmp     byte ptr [rcx+69h], 4
0x18000fb2e  jb      short loc_18000FB4B
0x18000fb30  mov     rcx, [rcx+60h]
0x18000fb34  lea     edx, [rbx+27h]
0x18000fb37  lea     r8, WPP_cf1e279eb4443e5f62d342d21539bd0c_Traceguids
0x18000fb3e  mov     dword ptr [rsp+78h+pcbBytesNeeded], 1
0x18000fb46  call    WPP_SF_Dd
0x18000fb4b  call    cs:__imp_GetTickCount64
0x18000fb51  mov     esi, [rdi+14h]
0x18000fb54  mov     rbp, rax
0x18000fb57  cmp     [rdi+4], r14d
0x18000fb5b  jnz     loc_18000FC85
0x18000fb61  lea     rax, [rsp+78h+var_48]
0x18000fb66  mov     r9d, 24h ; '$'; cbBufSize
0x18000fb6c  mov     r8, rdi; lpBuffer
0x18000fb6f  mov     [rsp+78h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18000fb74  xor     edx, edx; InfoLevel
0x18000fb76  mov     rcx, r15; hService
0x18000fb79  call    cs:__imp_QueryServiceStatusEx
0x18000fb7f  test    eax, eax
0x18000fb81  jz      loc_18000FC40
0x18000fb87  cmp     dword ptr [rdi+4], 1
0x18000fb8b  jz      loc_18000FC85
0x18000fb91  cmp     [rdi+14h], esi
0x18000fb94  jbe     short loc_18000FBD1
0x18000fb96  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fb9d  cmp     rcx, r13
0x18000fba0  jz      short loc_18000FBC3
0x18000fba2  test    [rcx+6Ch], r12d
0x18000fba6  jz      short loc_18000FBC3
0x18000fba8  cmp     byte ptr [rcx+69h], 4
0x18000fbac  jb      short loc_18000FBC3
0x18000fbae  mov     rcx, [rcx+60h]
0x18000fbb2  lea     r8, WPP_cf1e279eb4443e5f62d342d21539bd0c_Traceguids
0x18000fbb9  mov     edx, 29h ; ')'
0x18000fbbe  call    WPP_SF_
0x18000fbc3  call    cs:__imp_GetTickCount64
0x18000fbc9  mov     esi, [rdi+14h]
0x18000fbcc  mov     rbp, rax
0x18000fbcf  jmp     short loc_18000FBE2
0x18000fbd1  call    cs:__imp_GetTickCount64
0x18000fbd7  sub     rax, rbp
0x18000fbda  cmp     rax, 7530h
0x18000fbe0  ja      short loc_18000FC11
0x18000fbe2  mov     eax, 0CCCCCCCDh
0x18000fbe7  mul     dword ptr [rdi+18h]
0x18000fbea  mov     eax, 3E8h
0x18000fbef  shr     edx, 3
0x18000fbf2  cmp     edx, eax
0x18000fbf4  jnb     short loc_18000FBFA
0x18000fbf6  mov     edx, eax
0x18000fbf8  jmp     short loc_18000FC04
0x18000fbfa  mov     eax, 2710h
0x18000fbff  cmp     edx, eax
0x18000fc01  cmova   edx, eax
0x18000fc04  mov     ecx, edx; dwMilliseconds
0x18000fc06  call    cs:__imp_Sleep
0x18000fc0c  jmp     loc_18000FB57
0x18000fc11  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fc18  cmp     rcx, r13
0x18000fc1b  jz      short loc_18000FC8C
0x18000fc1d  test    [rcx+6Ch], r12d
0x18000fc21  jz      short loc_18000FC8C
0x18000fc23  cmp     byte ptr [rcx+69h], 4
0x18000fc27  jb      short loc_18000FC8C
0x18000fc29  mov     rcx, [rcx+60h]
0x18000fc2d  lea     r8, WPP_cf1e279eb4443e5f62d342d21539bd0c_Traceguids
0x18000fc34  mov     edx, 2Ah ; '*'
0x18000fc39  call    WPP_SF_
0x18000fc3e  jmp     short loc_18000FC85
0x18000fc40  call    cs:__imp_GetLastError
0x18000fc46  mov     ebx, eax
0x18000fc48  test    eax, eax
0x18000fc4a  jle     short loc_18000FC55
0x18000fc4c  movzx   ebx, ax
0x18000fc4f  or      ebx, 80070000h
0x18000fc55  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fc5c  cmp     rcx, r13
0x18000fc5f  jz      short loc_18000FC8C
0x18000fc61  test    [rcx+6Ch], r12d
0x18000fc65  jz      short loc_18000FC8C
0x18000fc67  cmp     byte ptr [rcx+69h], 1
0x18000fc6b  jb      short loc_18000FC8C
0x18000fc6d  mov     rcx, [rcx+60h]
0x18000fc71  lea     r8, WPP_cf1e279eb4443e5f62d342d21539bd0c_Traceguids
0x18000fc78  mov     edx, 28h ; '('
0x18000fc7d  mov     r9d, ebx
0x18000fc80  call    WPP_SF_d
0x18000fc85  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fc8c  cmp     dword ptr [rdi+4], 1
0x18000fc90  jz      short loc_18000FCCE
0x18000fc92  test    ebx, ebx
0x18000fc94  js      short loc_18000FCCE
0x18000fc96  cmp     rcx, r13
0x18000fc99  jz      short loc_18000FCC9
0x18000fc9b  test    [rcx+6Ch], r12d
0x18000fc9f  jz      short loc_18000FCC9
0x18000fca1  cmp     byte ptr [rcx+69h], 1
0x18000fca5  jb      short loc_18000FCC9
0x18000fca7  mov     rcx, [rcx+60h]
0x18000fcab  lea     r8, WPP_cf1e279eb4443e5f62d342d21539bd0c_Traceguids
0x18000fcb2  mov     edx, 2Bh ; '+'
0x18000fcb7  mov     r9d, 7530h
0x18000fcbd  call    WPP_SF_d
0x18000fcc2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fcc9  mov     ebx, 80070306h
0x18000fcce  cmp     rcx, r13
0x18000fcd1  jz      short loc_18000FCF7
0x18000fcd3  test    [rcx+6Ch], r12d
0x18000fcd7  jz      short loc_18000FCF7
0x18000fcd9  cmp     byte ptr [rcx+69h], 4
0x18000fcdd  jb      short loc_18000FCF7
0x18000fcdf  mov     rcx, [rcx+60h]
0x18000fce3  lea     r8, WPP_cf1e279eb4443e5f62d342d21539bd0c_Traceguids
0x18000fcea  mov     edx, 2Ch ; ','
0x18000fcef  mov     r9d, ebx
0x18000fcf2  call    WPP_SF_d
0x18000fcf7  mov     eax, ebx
0x18000fcf9  mov     rbx, [rsp+78h+arg_0]
0x18000fd01  add     rsp, 40h
0x18000fd05  pop     r15
0x18000fd07  pop     r14
0x18000fd09  pop     r13
0x18000fd0b  pop     r12
0x18000fd0d  pop     rdi
0x18000fd0e  pop     rsi
0x18000fd0f  pop     rbp
0x18000fd10  retn
```
