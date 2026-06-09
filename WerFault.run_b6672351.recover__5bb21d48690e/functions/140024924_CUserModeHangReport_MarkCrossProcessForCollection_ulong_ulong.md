# CUserModeHangReport::MarkCrossProcessForCollection(ulong,ulong)

- ea: `0x140024924`
- end: `0x140024c88`
- name: `?MarkCrossProcessForCollection@CUserModeHangReport@@AEAAJKK@Z`
- size: `868`
- prototype: `__int64 __fastcall(CUserModeHangReport *__hidden this, DWORD dwProcessId, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x14002840c`

## callees

- `0x140002490`
- `0x14000b580`
- `0x140014f14`
- `0x140021930`
- `0x1400221f4`
- `0x140022d78`
- `0x140024924`
- `0x14005afa4`
- `0x14005ba44`
- `0x14005bcf8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140024b20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140024b20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140024c57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140024c57`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1400249c4`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1400249c4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUserModeHangReport::MarkCrossProcessForCollection(
        struct _EXCEPTION_POINTERS *this,
        DWORD dwProcessId,
        unsigned int a3)
{
  unsigned int v6; // r15d
  char *v7; // r14
  unsigned int v8; // ecx
  PEXCEPTION_RECORD ExceptionRecord; // r8
  int v10; // edx
  int v11; // eax
  int v12; // eax
  unsigned int v13; // ebx
  CUserModeHangReport *v14; // rcx
  __int64 v15; // rdx
  signed int LastError; // eax
  wchar_t v18[32]; // [rsp+50h] [rbp-88h] BYREF

  v6 = a3 != 0 ? -805306369 : -536870913;
  v7 = 0;
  v8 = 0;
  ExceptionRecord = this[1527].ExceptionRecord;
  do
  {
    v10 = *((_DWORD *)&ExceptionRecord[7].ExceptionInformation[8] + (int)v8 + 1);
    if ( v10 && v10 == dwProcessId )
    {
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids, dwProcessId);
      }
      v13 = -2147024713;
      goto LABEL_44;
    }
    ++v8;
  }
  while ( v8 < 0xF );
  v11 = ExceptionRecord[9].ExceptionInformation[5];
  if ( (v11 & 4) == 0 || (v11 & 0x10000) != 0 && !(unsigned int)CHangReport::_IsInLpeMode((CHangReport *)this) )
  {
    v12 = CElevatedDataCollection::AddReflectedCrossProcessPid(
            (CElevatedDataCollection *)&this[1409],
            this[1527].ContextRecord,
            dwProcessId,
            a3,
            v6);
    v13 = v12;
    if ( v12 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v15 = 55;
        goto LABEL_42;
      }
      goto LABEL_44;
    }
    goto LABEL_43;
  }
  v7 = (char *)OpenProcess(0x100C51u, 0, dwProcessId);
  if ( v7 == (char *)-1LL || v7 + 1 == (char *)1 )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids,
        (unsigned int)LastError);
    }
    v12 = CElevatedDataCollection::AddServerRequest((CElevatedDataCollection *)&this[1409], L"dc.xpdata", L"1");
    v13 = v12;
    if ( v12 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v15 = 60;
        goto LABEL_42;
      }
      goto LABEL_44;
    }
    v12 = CElevatedDataCollection::AddCrossProcessPid((CElevatedDataCollection *)&this[1409], dwProcessId, a3, v6, 0, 0);
    v13 = v12;
    if ( v12 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v15 = 61;
        goto LABEL_42;
      }
      goto LABEL_44;
    }
    goto LABEL_43;
  }
  v12 = CHangReport::_AddWerDumpForProcess(
          this[1527].ContextRecord,
          v7,
          dwProcessId,
          a3,
          WerDumpTypeTriageDump,
          0x20000003u,
          this + 2223,
          0);
  v13 = v12;
  if ( v12 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v15 = 56;
LABEL_42:
      WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids, (unsigned int)v12);
      goto LABEL_44;
    }
    goto LABEL_44;
  }
  v12 = StringCchPrintfW(v18, 0x20u, L"triagedump.%04x.dmp", dwProcessId);
  v13 = v12;
  if ( v12 >= 0 )
  {
    v12 = CHangReport::_AddFileToList(this, v18, dwProcessId, 1);
    v13 = v12;
    if ( v12 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v15 = 58;
        goto LABEL_42;
      }
      goto LABEL_44;
    }
LABEL_43:
    v13 = 0;
    goto LABEL_44;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v15 = 57;
    goto LABEL_42;
  }
LABEL_44:
  if ( (unsigned __int64)(v7 + 1) > 1 )
    CloseHandle(v7);
  return v13;
}

```

## disassembly

```asm
0x140024924  push    rbx
0x140024926  push    rbp
0x140024927  push    rsi
0x140024928  push    rdi
0x140024929  push    r12
0x14002492b  push    r14
0x14002492d  push    r15
0x14002492f  sub     rsp, 0A0h
0x140024936  mov     rax, cs:__security_cookie
0x14002493d  xor     rax, rsp
0x140024940  mov     [rsp+0D8h+var_48], rax
0x140024948  mov     r12d, r8d
0x14002494b  mov     esi, edx
0x14002494d  mov     rbp, rcx
0x140024950  mov     eax, r8d
0x140024953  neg     eax
0x140024955  sbb     r15d, r15d
0x140024958  and     r15d, 0F0000000h
0x14002495f  add     r15d, 0DFFFFFFFh
0x140024966  xor     r14d, r14d
0x140024969  mov     [rsp+0D8h+var_98], r14
0x14002496e  xor     ecx, ecx
0x140024970  mov     r8, [rbp+5F70h]
0x140024977  movsxd  rax, ecx
0x14002497a  mov     edx, [r8+rax*4+48Ch]
0x140024982  test    edx, edx
0x140024984  jz      short loc_14002498E
0x140024986  cmp     edx, esi
0x140024988  jz      loc_140024A50
0x14002498e  inc     ecx
0x140024990  cmp     ecx, 0Fh
0x140024993  jb      short loc_140024977
0x140024995  mov     eax, [r8+5A0h]
0x14002499c  test    al, 4
0x14002499e  jz      loc_140024BF1
0x1400249a4  bt      eax, 10h
0x1400249a8  jnb     short loc_1400249BA
0x1400249aa  mov     rcx, rbp; this
0x1400249ad  call    ?_IsInLpeMode@CHangReport@@IEBAHXZ; CHangReport::_IsInLpeMode(void)
0x1400249b2  test    eax, eax
0x1400249b4  jz      loc_140024BF1
0x1400249ba  mov     r8d, esi; dwProcessId
0x1400249bd  xor     edx, edx; bInheritHandle
0x1400249bf  mov     ecx, 100C51h; dwDesiredAccess
0x1400249c4  call    cs:__imp_OpenProcess
0x1400249cb  nop     dword ptr [rax+rax+00h]
0x1400249d0  mov     r14, rax
0x1400249d3  mov     [rsp+0D8h+var_98], rax
0x1400249d8  inc     rax
0x1400249db  cmp     rax, 1
0x1400249df  jbe     loc_140024B20
0x1400249e5  lea     rax, [rbp+8AF0h]
0x1400249ec  mov     [rsp+0D8h+var_A0], 0; struct HPSS__ *
0x1400249f5  mov     [rsp+0D8h+var_A8], rax; struct _EXCEPTION_POINTERS *
0x1400249fa  mov     [rsp+0D8h+var_B0], 20000003h; unsigned int
0x140024a02  mov     [rsp+0D8h+var_B8], 4; enum _WER_DUMP_TYPE
0x140024a0a  mov     r9d, r12d; unsigned int
0x140024a0d  mov     r8d, esi; unsigned int
0x140024a10  mov     rdx, r14; void *
0x140024a13  mov     rcx, [rbp+5F78h]; void *
0x140024a1a  call    ?_AddWerDumpForProcess@CHangReport@@KAJPEAX0KKW4_WER_DUMP_TYPE@@KPEAU_EXCEPTION_POINTERS@@PEAUHPSS__@@@Z; CHangReport::_AddWerDumpForProcess(void *,void *,ulong,ulong,_WER_DUMP_TYPE,ulong,_EXCEPTION_POINTERS *,HPSS__ *)
0x140024a1f  mov     ebx, eax
0x140024a21  test    eax, eax
0x140024a23  jns     short loc_140024A8B
0x140024a25  lea     rdi, WPP_GLOBAL_Control
0x140024a2c  mov     rcx, cs:WPP_GLOBAL_Control
0x140024a33  cmp     rcx, rdi
0x140024a36  jz      loc_140024C4A
0x140024a3c  test    byte ptr [rcx+1Ch], 1
0x140024a40  jz      loc_140024C4A
0x140024a46  mov     edx, 38h ; '8'
0x140024a4b  jmp     loc_140024C33
0x140024a50  lea     rdi, WPP_GLOBAL_Control
0x140024a57  mov     rcx, cs:WPP_GLOBAL_Control
0x140024a5e  cmp     rcx, rdi
0x140024a61  jz      short loc_140024A81
0x140024a63  test    byte ptr [rcx+1Ch], 4
0x140024a67  jz      short loc_140024A81
0x140024a69  mov     edx, 36h ; '6'
0x140024a6e  mov     r9d, esi
0x140024a71  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x140024a78  mov     rcx, [rcx+10h]
0x140024a7c  call    WPP_SF_d
0x140024a81  mov     ebx, 800700B7h
0x140024a86  jmp     loc_140024C4A
0x140024a8b  mov     r9d, esi
0x140024a8e  lea     r8, aTriagedump04xD; "triagedump.%04x.dmp"
0x140024a95  mov     edx, 20h ; ' '; unsigned __int64
0x140024a9a  lea     rcx, [rsp+0D8h+var_88]; wchar_t *
0x140024a9f  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140024aa4  mov     ebx, eax
0x140024aa6  test    eax, eax
0x140024aa8  jns     short loc_140024AD5
0x140024aaa  lea     rdi, WPP_GLOBAL_Control
0x140024ab1  mov     rcx, cs:WPP_GLOBAL_Control
0x140024ab8  cmp     rcx, rdi
0x140024abb  jz      loc_140024C4A
0x140024ac1  test    byte ptr [rcx+1Ch], 1
0x140024ac5  jz      loc_140024C4A
0x140024acb  mov     edx, 39h ; '9'
0x140024ad0  jmp     loc_140024C33
0x140024ad5  mov     r9d, 1
0x140024adb  mov     r8d, esi
0x140024ade  lea     rdx, [rsp+0D8h+var_88]
0x140024ae3  mov     rcx, rbp
0x140024ae6  call    ?_AddFileToList@CHangReport@@IEAAJPEB_WKW4FAULTREP_CROSSPROCESS_FILE_TYPE@@@Z; CHangReport::_AddFileToList(wchar_t const *,ulong,FAULTREP_CROSSPROCESS_FILE_TYPE)
0x140024aeb  mov     ebx, eax
0x140024aed  test    eax, eax
0x140024aef  jns     loc_140024C48
0x140024af5  lea     rdi, WPP_GLOBAL_Control
0x140024afc  mov     rcx, cs:WPP_GLOBAL_Control
0x140024b03  cmp     rcx, rdi
0x140024b06  jz      loc_140024C4A
0x140024b0c  test    byte ptr [rcx+1Ch], 1
0x140024b10  jz      loc_140024C4A
0x140024b16  mov     edx, 3Ah ; ':'
0x140024b1b  jmp     loc_140024C33
0x140024b20  call    cs:__imp_GetLastError
0x140024b27  nop     dword ptr [rax+rax+00h]
0x140024b2c  test    eax, eax
0x140024b2e  jle     short loc_140024B38
0x140024b30  movzx   eax, ax
0x140024b33  or      eax, 80070000h
0x140024b38  lea     rdi, WPP_GLOBAL_Control
0x140024b3f  mov     rcx, cs:WPP_GLOBAL_Control
0x140024b46  cmp     rcx, rdi
0x140024b49  jz      short loc_140024B69
0x140024b4b  test    byte ptr [rcx+1Ch], 2
0x140024b4f  jz      short loc_140024B69
0x140024b51  mov     edx, 3Bh ; ';'
0x140024b56  mov     r9d, eax
0x140024b59  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x140024b60  mov     rcx, [rcx+10h]
0x140024b64  call    WPP_SF_d
0x140024b69  lea     r8, a1; "1"
0x140024b70  lea     rdx, aDcXpdata; "dc.xpdata"
0x140024b77  lea     rcx, [rbp+5810h]; this
0x140024b7e  call    ?AddServerRequest@CElevatedDataCollection@@QEAAJPEB_W0@Z; CElevatedDataCollection::AddServerRequest(wchar_t const *,wchar_t const *)
0x140024b83  mov     ebx, eax
0x140024b85  test    eax, eax
0x140024b87  jns     short loc_140024BAD
0x140024b89  mov     rcx, cs:WPP_GLOBAL_Control
0x140024b90  cmp     rcx, rdi
0x140024b93  jz      loc_140024C4A
0x140024b99  test    byte ptr [rcx+1Ch], 1
0x140024b9d  jz      loc_140024C4A
0x140024ba3  mov     edx, 3Ch ; '<'
0x140024ba8  jmp     loc_140024C33
0x140024bad  mov     [rsp+0D8h+var_B0], 0; unsigned int
0x140024bb5  mov     qword ptr [rsp+0D8h+var_B8], 0; wchar_t *
0x140024bbe  mov     r9d, r15d; unsigned int
0x140024bc1  mov     r8d, r12d; unsigned int
0x140024bc4  mov     edx, esi; dwProcessId
0x140024bc6  lea     rcx, [rbp+5810h]; this
0x140024bcd  call    ?AddCrossProcessPid@CElevatedDataCollection@@QEAAJKKKPEB_WK@Z; CElevatedDataCollection::AddCrossProcessPid(ulong,ulong,ulong,wchar_t const *,ulong)
0x140024bd2  mov     ebx, eax
0x140024bd4  test    eax, eax
0x140024bd6  jns     short loc_140024C48
0x140024bd8  mov     rcx, cs:WPP_GLOBAL_Control
0x140024bdf  cmp     rcx, rdi
0x140024be2  jz      short loc_140024C4A
0x140024be4  test    byte ptr [rcx+1Ch], 1
0x140024be8  jz      short loc_140024C4A
0x140024bea  mov     edx, 3Dh ; '='
0x140024bef  jmp     short loc_140024C33
0x140024bf1  lea     rcx, [rbp+5810h]; this
0x140024bf8  mov     [rsp+0D8h+var_B8], r15d; unsigned int
0x140024bfd  mov     r9d, r12d; unsigned int
0x140024c00  mov     r8d, esi; dwProcessId
0x140024c03  mov     rdx, [rbp+5F78h]; void *
0x140024c0a  call    ?AddReflectedCrossProcessPid@CElevatedDataCollection@@QEAAJPEAXKKK@Z; CElevatedDataCollection::AddReflectedCrossProcessPid(void *,ulong,ulong,ulong)
0x140024c0f  mov     ebx, eax
0x140024c11  test    eax, eax
0x140024c13  jns     short loc_140024C48
0x140024c15  lea     rdi, WPP_GLOBAL_Control
0x140024c1c  mov     rcx, cs:WPP_GLOBAL_Control
0x140024c23  cmp     rcx, rdi
0x140024c26  jz      short loc_140024C4A
0x140024c28  test    byte ptr [rcx+1Ch], 1
0x140024c2c  jz      short loc_140024C4A
0x140024c2e  mov     edx, 37h ; '7'
0x140024c33  mov     r9d, eax
0x140024c36  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x140024c3d  mov     rcx, [rcx+10h]
0x140024c41  call    WPP_SF_d
0x140024c46  jmp     short loc_140024C4A
0x140024c48  xor     ebx, ebx
0x140024c4a  lea     rax, [r14+1]
0x140024c4e  cmp     rax, 1
0x140024c52  jbe     short loc_140024C63
0x140024c54  mov     rcx, r14; hObject
0x140024c57  call    cs:__imp_CloseHandle
0x140024c5e  nop     dword ptr [rax+rax+00h]
0x140024c63  mov     eax, ebx
0x140024c65  mov     rcx, [rsp+0D8h+var_48]
0x140024c6d  xor     rcx, rsp; StackCookie
0x140024c70  call    __security_check_cookie
0x140024c75  add     rsp, 0A0h
0x140024c7c  pop     r15
0x140024c7e  pop     r14
0x140024c80  pop     r12
0x140024c82  pop     rdi
0x140024c83  pop     rsi
0x140024c84  pop     rbp
0x140024c85  pop     rbx
0x140024c86  retn
```
