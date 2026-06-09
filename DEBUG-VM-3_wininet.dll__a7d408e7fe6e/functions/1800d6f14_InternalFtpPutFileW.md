# InternalFtpPutFileW

- ea: `0x1800d6f14`
- end: `0x1800d73c9`
- name: `InternalFtpPutFileW`
- size: `1205`
- prototype: `__int64 __fastcall(void *, unsigned __int16 *, unsigned __int16 *, unsigned int, __int64, int)`
- caller_count: `2`
- callee_count: `24`
- tags: `file_ops`

## callers

- `0x180173490`
- `0x180174230`

## callees

- `0x180003c40`
- `0x18000baa0`
- `0x180038610`
- `0x1800388a4`
- `0x180039788`
- `0x18003a870`
- `0x18003e350`
- `0x180053788`
- `0x180064060`
- `0x1800641c0`
- `0x180064560`
- `0x18006625c`
- `0x1800701d0`
- `0x18007ad20`
- `0x1800bdee8`
- `0x1800d6f14`
- `0x1800d73d0`
- `0x1800d7824`
- `0x18014a7a0`
- `0x18014b3b4`
- `0x1801731c4`
- `0x1801e1790`
- `0x1801eb45c`
- `0x1801ee010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d7122`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800d7122`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d7279`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d7279`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d7396`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d7396`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d72b0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800d72b0`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800d7341`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800d7341`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d73a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d73a5`

## pseudocode

```c
__int64 __fastcall InternalFtpPutFileW(
        void *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        unsigned int a4,
        __int64 a5,
        int a6)
{
  unsigned int v6; // esi
  DWORD IsValid; // ebx
  unsigned int v11; // edi
  __int64 v12; // rdx
  HANDLE_OBJECT *v13; // r14
  int v14; // edx
  unsigned __int64 v16; // r14
  CFsm_FtpPutFile *v17; // rax
  CFsm_FtpPutFile *v18; // rbx
  CFsm_FtpPutFile *v19; // rax
  HINTERNET v20; // rbx
  __int64 v21; // r15
  __int64 v22; // r12
  DWORD v23; // eax
  __int64 v24; // rcx
  void *v25; // r14
  HANDLE FileW; // rax
  unsigned __int64 v27; // r13
  __int64 v28; // rax
  BOOL v29; // [rsp+50h] [rbp-69h]
  __int64 ThreadInfo; // [rsp+58h] [rbp-61h]
  DWORD Buffer; // [rsp+68h] [rbp-51h] BYREF
  HANDLE_OBJECT *v33; // [rsp+70h] [rbp-49h] BYREF
  HANDLE_OBJECT *v34; // [rsp+78h] [rbp-41h] BYREF
  unsigned __int64 v35; // [rsp+80h] [rbp-39h]
  HINTERNET hInternet; // [rsp+88h] [rbp-31h] BYREF
  DWORD dwBufferLength; // [rsp+90h] [rbp-29h] BYREF
  struct _GUID v38; // [rsp+98h] [rbp-21h] BYREF
  int v39; // [rsp+A8h] [rbp-11h] BYREF

  v6 = a4;
  v35 = a5;
  hInternet = a1;
  if ( (xmmword_180266B60 & 0x80u) != 0LL )
    WPP_SF_qSSDPl((_DWORD)a1, (_DWORD)a2, (_DWORD)a3, (_DWORD)a1, (__int64)a2, (__int64)a3, a4, a5, a6);
  v33 = 0;
  v34 = 0;
  v38 = 0;
  v39 = 0;
  if ( !GlobalDataInitialized )
  {
    IsValid = 12172;
    goto LABEL_26;
  }
  ThreadInfo = InternetGetThreadInfo(a1, a2, a3);
  if ( !ThreadInfo )
  {
    IsValid = 12004;
LABEL_26:
    v11 = 0;
    if ( (xmmword_180266B50 & 4) != 0 )
      WPP_SF_d(514, 26, &WPP_8159590328cd30fd0989b12d5351a1b5_Traceguids, IsValid);
    goto LABEL_28;
  }
  v11 = 1;
  v29 = 1;
  IsValid = MapHandleToAddress(a1, &v33, 0);
  if ( !IsValid || v33 )
  {
    EtwBeginActivityIdInternal((struct _GUID *)((char *)v33 + 164), 0, &v38, &v39);
    InternetSetObjectHandle(ThreadInfo, a1, v33);
    InternetSetContext(ThreadInfo, a5);
    InternetSetLastError(ThreadInfo, v12, 0, 0, 0);
    if ( !IsValid )
    {
      v13 = v33;
      IsValid = HANDLE_OBJECT::IsValid(v33, 1852785478);
      if ( !IsValid )
      {
        (*(void (__fastcall **)(HANDLE_OBJECT *))(*(_QWORD *)v13 + 16LL))(v13);
        v14 = *(_DWORD *)(ThreadInfo + 64);
        if ( !v14 || !a6 )
        {
          if ( !a3 || !*a3 || !a2 || !*a2 )
            goto LABEL_19;
          if ( (v6 & 3) != 0 )
          {
            if ( (v6 & 3) - 1 > 1 )
            {
LABEL_19:
              IsValid = 87;
              goto LABEL_20;
            }
          }
          else
          {
            v6 |= 2u;
          }
          if ( ((*((_DWORD *)v33 + 116) | v6) & 0x1000000) != 0 )
          {
            IsValid = 19;
            goto LABEL_20;
          }
          if ( !v14 )
          {
            if ( *((_DWORD *)v13 + 131) )
            {
              v16 = v35;
              if ( v35 )
              {
                v17 = (CFsm_FtpPutFile *)operator new(0xF0u);
                v18 = v17;
                if ( v17
                  && (memset_0(v17, 0, 0xF0u), (v19 = CFsm_FtpPutFile::CFsm_FtpPutFile(v18, a1, v16, a2, a3, v6)) != 0) )
                {
                  if ( *((_DWORD *)v19 + 10) )
                  {
                    IsValid = *((_DWORD *)v19 + 10);
                    (**(void (__fastcall ***)(CFsm_FtpPutFile *, __int64))v19)(v19, 1);
                  }
                  else
                  {
                    IsValid = CFsm::InternalQueueWorkItem(v19, 1);
                    v29 = IsValid != 997;
                  }
                }
                else
                {
                  IsValid = 8;
                }
                if ( (xmmword_180266B60 & 0x80u) != 0LL )
                  WPP_SF_d(1031, 25, &WPP_8159590328cd30fd0989b12d5351a1b5_Traceguids, IsValid);
                goto LABEL_20;
              }
            }
          }
        }
        v20 = hInternet;
        v21 = 0;
        Buffer = 0;
        v22 = -1;
        dwBufferLength = 4;
        if ( InternetQueryOptionA(hInternet, 0xDu, &Buffer, &dwBufferLength) )
        {
          v23 = Buffer;
        }
        else
        {
          v23 = 4096;
          Buffer = 4096;
        }
        v25 = HeapAlloc(g_hWxProcessHeap, 0, v23);
        if ( v25 )
        {
          FileW = CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x8000000u, 0);
          v27 = v35;
          v22 = (__int64)FileW;
          if ( FileW != (HANDLE)-1LL )
          {
            v28 = InternalFtpOpenFileW(v20, a3, 0x40000000, v6, v35, 1);
            v21 = v28;
            if ( v28 )
            {
              IsValid = MapHandleToAddress(v28, &v34, 0);
              DereferenceObject(v34);
              if ( !IsValid )
              {
                while ( 1 )
                {
                  LODWORD(hInternet) = 0;
                  if ( (unsigned int)HANDLE_OBJECT::IsInvalidated(v34)
                    || (unsigned int)HANDLE_OBJECT::IsInvalidated(v33) )
                  {
                    break;
                  }
                  if ( !ReadFile((HANDLE)v22, v25, Buffer, (LPDWORD)&hInternet, 0) )
                    goto LABEL_61;
                  if ( !(_DWORD)hInternet )
                  {
                    IsValid = 0;
                    goto LABEL_62;
                  }
                  LODWORD(v35) = 0;
                  if ( !(unsigned int)FtpWriteFile(v34) )
                    goto LABEL_61;
                }
                IsValid = 12017;
              }
              goto LABEL_62;
            }
          }
        }
        else
        {
          v27 = v35;
        }
LABEL_61:
        IsValid = WxGetLastError(v24);
        if ( !v25 )
        {
LABEL_63:
          if ( v22 != -1 )
            CloseHandle((HANDLE)v22);
          if ( v21 )
            InternetCloseHandle(v21);
          InternetSetContext(ThreadInfo, v27);
          goto LABEL_20;
        }
LABEL_62:
        HeapFree(g_hWxProcessHeap, 0, v25);
        goto LABEL_63;
      }
    }
  }
LABEL_20:
  if ( v34 )
    DereferenceObject(v34);
  if ( v33 && v29 )
    DereferenceObject(v33);
  if ( IsValid )
    goto LABEL_26;
LABEL_28:
  EtwEndActivityId(&v38);
  if ( (xmmword_180266B60 & 0x80u) != 0LL )
    WPP_SF_d(1031, 27, &WPP_8159590328cd30fd0989b12d5351a1b5_Traceguids, v11);
  SetLastError(IsValid);
  return v11;
}

```

## disassembly

```asm
0x1800d6f14  push    rbp
0x1800d6f16  push    rbx
0x1800d6f17  push    rsi
0x1800d6f18  push    rdi
0x1800d6f19  push    r12
0x1800d6f1b  push    r13
0x1800d6f1d  push    r14
0x1800d6f1f  push    r15
0x1800d6f21  lea     rbp, [rsp-0Fh]
0x1800d6f26  sub     rsp, 0C8h
0x1800d6f2d  mov     rax, cs:__security_cookie
0x1800d6f34  xor     rax, rsp
0x1800d6f37  mov     [rbp+47h+var_50], rax
0x1800d6f3b  mov     r14, [rbp+47h+arg_20]
0x1800d6f3f  mov     esi, r9d
0x1800d6f42  mov     [rbp+47h+var_80], r14
0x1800d6f46  mov     r15, r8
0x1800d6f49  mov     [rbp+47h+var_A0], r8
0x1800d6f4d  mov     r13, rdx
0x1800d6f50  mov     r12, rcx
0x1800d6f53  mov     [rbp+47h+hInternet], rcx
0x1800d6f57  xor     ebx, ebx
0x1800d6f59  cmp     byte ptr cs:xmmword_180266B60, bl
0x1800d6f5f  jge     short loc_1800D6F84
0x1800d6f61  mov     eax, [rbp+47h+arg_28]
0x1800d6f64  mov     [rsp+100h+var_C0], eax
0x1800d6f68  mov     [rsp+100h+var_C8], r14
0x1800d6f6d  mov     dword ptr [rsp+100h+hTemplateFile], r9d
0x1800d6f72  mov     r9, rcx
0x1800d6f75  mov     qword ptr [rsp+100h+dwFlagsAndAttributes], r8
0x1800d6f7a  mov     qword ptr [rsp+100h+dwCreationDisposition], rdx
0x1800d6f7f  call    WPP_SF_qSSDPl
0x1800d6f84  xor     eax, eax
0x1800d6f86  mov     [rbp+47h+var_90], rbx
0x1800d6f8a  cmp     cs:GlobalDataInitialized, ebx
0x1800d6f90  xorps   xmm0, xmm0
0x1800d6f93  mov     [rbp+47h+var_88], rbx
0x1800d6f97  movups  xmmword ptr [rbp+47h+var_68.Data1], xmm0
0x1800d6f9b  mov     [rbp+47h+var_58], eax
0x1800d6f9e  jnz     short loc_1800D6FAC
0x1800d6fa0  mov     ebx, 2F8Ch
0x1800d6fa5  xor     esi, esi
0x1800d6fa7  jmp     loc_1800D70D1
0x1800d6fac  call    InternetGetThreadInfo
0x1800d6fb1  mov     [rbp+47h+var_A8], rax
0x1800d6fb5  test    rax, rax
0x1800d6fb8  jnz     short loc_1800D6FC1
0x1800d6fba  mov     ebx, 2EE4h
0x1800d6fbf  jmp     short loc_1800D6FA5
0x1800d6fc1  mov     edi, 1
0x1800d6fc6  lea     rdx, [rbp+47h+var_90]
0x1800d6fca  xor     r8d, r8d
0x1800d6fcd  mov     [rbp+47h+var_B0], edi
0x1800d6fd0  mov     rcx, r12
0x1800d6fd3  call    MapHandleToAddress
0x1800d6fd8  mov     ebx, eax
0x1800d6fda  xor     eax, eax
0x1800d6fdc  test    ebx, ebx
0x1800d6fde  jz      short loc_1800D6FEA
0x1800d6fe0  cmp     [rbp+47h+var_90], rax
0x1800d6fe4  jz      loc_1800D70AA
0x1800d6fea  mov     rcx, [rbp+47h+var_90]
0x1800d6fee  lea     r9, [rbp+47h+var_58]; int *
0x1800d6ff2  add     rcx, 0A4h; struct _GUID *
0x1800d6ff9  lea     r8, [rbp+47h+var_68]; struct _GUID *
0x1800d6ffd  xor     edx, edx; unsigned int
0x1800d6fff  call    ?EtwBeginActivityIdInternal@@YAXPEAU_GUID@@K0PEAH@Z; EtwBeginActivityIdInternal(_GUID *,ulong,_GUID *,int *)
0x1800d7004  mov     r8, [rbp+47h+var_90]
0x1800d7008  mov     rdx, r12
0x1800d700b  mov     rcx, [rbp+47h+var_A8]
0x1800d700f  call    _InternetSetObjectHandle
0x1800d7014  mov     rcx, [rbp+47h+var_A8]
0x1800d7018  mov     rdx, r14
0x1800d701b  call    _InternetSetContext
0x1800d7020  mov     rcx, [rbp+47h+var_A8]
0x1800d7024  xor     r9d, r9d
0x1800d7027  xor     r8d, r8d
0x1800d702a  mov     [rsp+100h+dwCreationDisposition], 0
0x1800d7032  call    _InternetSetLastError
0x1800d7037  test    ebx, ebx
0x1800d7039  jnz     short loc_1800D70AA
0x1800d703b  mov     r14, [rbp+47h+var_90]
0x1800d703f  mov     edx, 6E6F4346h
0x1800d7044  mov     rcx, r14
0x1800d7047  call    ?IsValid@HANDLE_OBJECT@@QEAAKW4HINTERNET_HANDLE_TYPE@@@Z; HANDLE_OBJECT::IsValid(HINTERNET_HANDLE_TYPE)
0x1800d704c  mov     ebx, eax
0x1800d704e  test    eax, eax
0x1800d7050  jnz     short loc_1800D70AA
0x1800d7052  mov     rax, [r14]
0x1800d7055  mov     rcx, r14
0x1800d7058  mov     rax, [rax+10h]
0x1800d705c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d7061  mov     rax, [rbp+47h+var_A8]
0x1800d7065  xor     r8d, r8d
0x1800d7068  mov     edx, [rax+40h]
0x1800d706b  test    edx, edx
0x1800d706d  jz      short loc_1800D7079
0x1800d706f  cmp     [rbp+47h+arg_28], r8d
0x1800d7073  jnz     loc_1800D7231
0x1800d7079  test    r15, r15
0x1800d707c  jz      short loc_1800D70A5
0x1800d707e  cmp     [r15], r8w
0x1800d7082  jz      short loc_1800D70A5
0x1800d7084  test    r13, r13
0x1800d7087  jz      short loc_1800D70A5
0x1800d7089  cmp     [r13+0], r8w
0x1800d708e  jz      short loc_1800D70A5
0x1800d7090  mov     eax, esi
0x1800d7092  and     eax, 3
0x1800d7095  jz      loc_1800D714A
0x1800d709b  dec     eax
0x1800d709d  cmp     eax, edi
0x1800d709f  jbe     loc_1800D714D
0x1800d70a5  mov     ebx, 57h ; 'W'
0x1800d70aa  xor     esi, esi
0x1800d70ac  mov     rcx, [rbp+47h+var_88]
0x1800d70b0  test    rcx, rcx
0x1800d70b3  jz      short loc_1800D70BA
0x1800d70b5  call    DereferenceObject
0x1800d70ba  mov     rcx, [rbp+47h+var_90]
0x1800d70be  test    rcx, rcx
0x1800d70c1  jz      short loc_1800D70CD
0x1800d70c3  cmp     [rbp+47h+var_B0], esi
0x1800d70c6  jz      short loc_1800D70CD
0x1800d70c8  call    DereferenceObject
0x1800d70cd  test    ebx, ebx
0x1800d70cf  jz      short loc_1800D70F5
0x1800d70d1  mov     edi, esi
0x1800d70d3  test    byte ptr cs:xmmword_180266B50, 4
0x1800d70da  jz      short loc_1800D70F5
0x1800d70dc  mov     edx, 1Ah
0x1800d70e1  lea     r8, WPP_8159590328cd30fd0989b12d5351a1b5_Traceguids
0x1800d70e8  mov     ecx, 202h
0x1800d70ed  mov     r9d, ebx
0x1800d70f0  call    WPP_SF_d
0x1800d70f5  lea     rcx, [rbp+47h+var_68]
0x1800d70f9  call    EtwEndActivityId
0x1800d70fe  cmp     byte ptr cs:xmmword_180266B60, sil
0x1800d7105  jge     short loc_1800D7120
0x1800d7107  mov     edx, 1Bh
0x1800d710c  lea     r8, WPP_8159590328cd30fd0989b12d5351a1b5_Traceguids
0x1800d7113  mov     ecx, 407h
0x1800d7118  mov     r9d, edi
0x1800d711b  call    WPP_SF_d
0x1800d7120  mov     ecx, ebx; dwErrCode
0x1800d7122  call    cs:__imp_SetLastError
0x1800d7128  mov     eax, edi
0x1800d712a  mov     rcx, [rbp+47h+var_50]
0x1800d712e  xor     rcx, rsp; StackCookie
0x1800d7131  call    __security_check_cookie
0x1800d7136  add     rsp, 0C8h
0x1800d713d  pop     r15
0x1800d713f  pop     r14
0x1800d7141  pop     r13
0x1800d7143  pop     r12
0x1800d7145  pop     rdi
0x1800d7146  pop     rsi
0x1800d7147  pop     rbx
0x1800d7148  pop     rbp
0x1800d7149  retn
0x1800d714a  or      esi, 2
0x1800d714d  mov     rax, [rbp+47h+var_90]
0x1800d7151  mov     ecx, esi
0x1800d7153  or      ecx, [rax+1D0h]
0x1800d7159  bt      ecx, 18h
0x1800d715d  jnb     short loc_1800D7169
0x1800d715f  mov     ebx, 13h
0x1800d7164  jmp     loc_1800D70AA
0x1800d7169  test    edx, edx
0x1800d716b  jnz     loc_1800D7231
0x1800d7171  cmp     [r14+20Ch], r8d
0x1800d7178  jz      loc_1800D7231
0x1800d717e  mov     r14, [rbp+47h+var_80]
0x1800d7182  test    r14, r14
0x1800d7185  jz      loc_1800D7231
0x1800d718b  mov     ecx, 0F0h; unsigned __int64
0x1800d7190  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800d7195  mov     rbx, rax
0x1800d7198  test    rax, rax
0x1800d719b  jz      short loc_1800D71FF
0x1800d719d  xor     edx, edx; Val
0x1800d719f  mov     r8d, 0F0h; Size
0x1800d71a5  mov     rcx, rax; void *
0x1800d71a8  call    memset_0
0x1800d71ad  mov     r9, r13; unsigned __int16 *
0x1800d71b0  mov     [rsp+100h+dwFlagsAndAttributes], esi; unsigned int
0x1800d71b4  mov     r8, r14; unsigned __int64
0x1800d71b7  mov     qword ptr [rsp+100h+dwCreationDisposition], r15; unsigned __int16 *
0x1800d71bc  mov     rdx, r12; void *
0x1800d71bf  mov     rcx, rbx; this
0x1800d71c2  call    ??0CFsm_FtpPutFile@@QEAA@PEAX_KPEBG2K@Z; CFsm_FtpPutFile::CFsm_FtpPutFile(void *,unsigned __int64,ushort const *,ushort const *,ulong)
0x1800d71c7  xor     esi, esi
0x1800d71c9  mov     rcx, rax; this
0x1800d71cc  test    rax, rax
0x1800d71cf  jz      short loc_1800D7201
0x1800d71d1  mov     edx, edi; int
0x1800d71d3  cmp     [rax+28h], esi
0x1800d71d6  jnz     short loc_1800D71EF
0x1800d71d8  call    ?InternalQueueWorkItem@CFsm@@AEAAKH@Z; CFsm::InternalQueueWorkItem(int)
0x1800d71dd  mov     ebx, eax
0x1800d71df  mov     eax, esi
0x1800d71e1  cmp     ebx, 3E5h
0x1800d71e7  setnz   al
0x1800d71ea  mov     [rbp+47h+var_B0], eax
0x1800d71ed  jmp     short loc_1800D7206
0x1800d71ef  mov     ebx, [rax+28h]
0x1800d71f2  mov     rax, [rax]
0x1800d71f5  mov     rax, [rax]
0x1800d71f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d71fd  jmp     short loc_1800D7206
0x1800d71ff  xor     esi, esi
0x1800d7201  mov     ebx, 8
0x1800d7206  cmp     byte ptr cs:xmmword_180266B60, sil
0x1800d720d  jge     loc_1800D70AC
0x1800d7213  mov     edx, 19h
0x1800d7218  lea     r8, WPP_8159590328cd30fd0989b12d5351a1b5_Traceguids
0x1800d721f  mov     ecx, 407h
0x1800d7224  mov     r9d, ebx
0x1800d7227  call    WPP_SF_d
0x1800d722c  jmp     loc_1800D70AC
0x1800d7231  mov     rbx, [rbp+47h+hInternet]
0x1800d7235  lea     r9, [rbp+47h+dwBufferLength]; lpdwBufferLength
0x1800d7239  mov     r15, r8
0x1800d723c  mov     [rbp+47h+Buffer], r8d
0x1800d7240  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800d7244  mov     [rbp+47h+dwBufferLength], 4
0x1800d724b  lea     r8, [rbp+47h+Buffer]; lpBuffer
0x1800d724f  mov     rcx, rbx; hInternet
0x1800d7252  lea     edx, [r12+0Eh]; dwOption
0x1800d7257  call    InternetQueryOptionA
0x1800d725c  test    eax, eax
0x1800d725e  jnz     short loc_1800D726A
0x1800d7260  mov     eax, 1000h
0x1800d7265  mov     [rbp+47h+Buffer], eax
0x1800d7268  jmp     short loc_1800D726D
0x1800d726a  mov     eax, [rbp+47h+Buffer]
0x1800d726d  mov     rcx, cs:g_hWxProcessHeap; hHeap
0x1800d7274  xor     edx, edx; dwFlags
0x1800d7276  mov     r8d, eax; dwBytes
0x1800d7279  call    cs:__imp_HeapAlloc
0x1800d727f  mov     r14, rax
0x1800d7282  xor     eax, eax
0x1800d7284  test    r14, r14
0x1800d7287  jz      loc_1800D7378
0x1800d728d  mov     [rsp+100h+hTemplateFile], rax; hTemplateFile
0x1800d7292  xor     r9d, r9d; lpSecurityAttributes
0x1800d7295  mov     [rsp+100h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x1800d729d  mov     r8d, edi; dwShareMode
0x1800d72a0  mov     edx, 80000000h; dwDesiredAccess
0x1800d72a5  mov     [rsp+100h+dwCreationDisposition], 3; dwCreationDisposition
0x1800d72ad  mov     rcx, r13; lpFileName
0x1800d72b0  call    cs:__imp_CreateFileW
0x1800d72b6  mov     r13, [rbp+47h+var_80]
0x1800d72ba  mov     r12, rax
0x1800d72bd  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800d72c1  jz      loc_1800D737C
0x1800d72c7  mov     rdx, [rbp+47h+var_A0]
0x1800d72cb  mov     r9d, esi
0x1800d72ce  mov     [rsp+100h+dwFlagsAndAttributes], edi
0x1800d72d2  mov     r8d, 40000000h
0x1800d72d8  mov     rcx, rbx
0x1800d72db  mov     qword ptr [rsp+100h+dwCreationDisposition], r13
0x1800d72e0  call    InternalFtpOpenFileW
0x1800d72e5  xor     esi, esi
0x1800d72e7  mov     r15, rax
0x1800d72ea  test    rax, rax
0x1800d72ed  jz      loc_1800D737E
0x1800d72f3  xor     r8d, r8d
0x1800d72f6  lea     rdx, [rbp+47h+var_88]
0x1800d72fa  mov     rcx, rax
0x1800d72fd  call    MapHandleToAddress
0x1800d7302  mov     rcx, [rbp+47h+var_88]
0x1800d7306  mov     ebx, eax
0x1800d7308  call    DereferenceObject
0x1800d730d  test    ebx, ebx
0x1800d730f  jnz     short loc_1800D738A
0x1800d7311  mov     rcx, [rbp+47h+var_88]; this
0x1800d7315  mov     dword ptr [rbp+47h+hInternet], esi
0x1800d7318  call    ?IsInvalidated@HANDLE_OBJECT@@QEBAHXZ; HANDLE_OBJECT::IsInvalidated(void)
0x1800d731d  test    eax, eax
0x1800d731f  jnz     short loc_1800D7371
0x1800d7321  mov     rcx, [rbp+47h+var_90]; this
0x1800d7325  call    ?IsInvalidated@HANDLE_OBJECT@@QEBAHXZ; HANDLE_OBJECT::IsInvalidated(void)
0x1800d732a  test    eax, eax
0x1800d732c  jnz     short loc_1800D7371
0x1800d732e  mov     r8d, [rbp+47h+Buffer]; nNumberOfBytesToRead
0x1800d7332  lea     r9, [rbp+47h+hInternet]; lpNumberOfBytesRead
0x1800d7336  mov     rdx, r14; lpBuffer
0x1800d7339  mov     qword ptr [rsp+100h+dwCreationDisposition], rsi; lpOverlapped
0x1800d733e  mov     rcx, r12; hFile
0x1800d7341  call    cs:__imp_ReadFile
0x1800d7347  test    eax, eax
0x1800d7349  jz      short loc_1800D737E
0x1800d734b  mov     r8d, dword ptr [rbp+47h+hInternet]
0x1800d734f  test    r8d, r8d
0x1800d7352  jz      short loc_1800D736D
0x1800d7354  mov     rcx, [rbp+47h+var_88]; this
0x1800d7358  lea     r9, [rbp+47h+var_80]
0x1800d735c  mov     rdx, r14
0x1800d735f  mov     dword ptr [rbp+47h+var_80], esi
  ... truncated ...
```
