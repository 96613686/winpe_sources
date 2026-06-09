# CUserModeHangReport::MarkCrossProcessForCollection(ulong,ulong)

- ea: `0x140023204`
- end: `0x140023555`
- name: `?MarkCrossProcessForCollection@CUserModeHangReport@@AEAAJKK@Z`
- size: `849`
- prototype: `__int64 __fastcall(CUserModeHangReport *__hidden this, DWORD dwProcessId, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x140026a70`

## callees

- `0x140002470`
- `0x14000b540`
- `0x140014474`
- `0x140020364`
- `0x140020c20`
- `0x14002173c`
- `0x140023204`
- `0x140057238`
- `0x140057cb0`
- `0x140057f58`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400233fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400233fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002352b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002352b`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1400232a4`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1400232a4`

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
0x140023204  push    rbx
0x140023206  push    rbp
0x140023207  push    rsi
0x140023208  push    rdi
0x140023209  push    r12
0x14002320b  push    r14
0x14002320d  push    r15
0x14002320f  sub     rsp, 0A0h
0x140023216  mov     rax, cs:__security_cookie
0x14002321d  xor     rax, rsp
0x140023220  mov     [rsp+0D8h+var_48], rax
0x140023228  mov     r12d, r8d
0x14002322b  mov     esi, edx
0x14002322d  mov     rbp, rcx
0x140023230  mov     eax, r8d
0x140023233  neg     eax
0x140023235  sbb     r15d, r15d
0x140023238  and     r15d, 0F0000000h
0x14002323f  add     r15d, 0DFFFFFFFh
0x140023246  xor     r14d, r14d
0x140023249  mov     [rsp+0D8h+var_98], r14
0x14002324e  xor     ecx, ecx
0x140023250  mov     r8, [rbp+5F70h]
0x140023257  movsxd  rax, ecx
0x14002325a  mov     edx, [r8+rax*4+48Ch]
0x140023262  test    edx, edx
0x140023264  jz      short loc_14002326E
0x140023266  cmp     edx, esi
0x140023268  jz      loc_14002332A
0x14002326e  inc     ecx
0x140023270  cmp     ecx, 0Fh
0x140023273  jb      short loc_140023257
0x140023275  mov     eax, [r8+5A0h]
0x14002327c  test    al, 4
0x14002327e  jz      loc_1400234C5
0x140023284  bt      eax, 10h
0x140023288  jnb     short loc_14002329A
0x14002328a  mov     rcx, rbp; this
0x14002328d  call    ?_IsInLpeMode@CHangReport@@IEBAHXZ; CHangReport::_IsInLpeMode(void)
0x140023292  test    eax, eax
0x140023294  jz      loc_1400234C5
0x14002329a  mov     r8d, esi; dwProcessId
0x14002329d  xor     edx, edx; bInheritHandle
0x14002329f  mov     ecx, 100C51h; dwDesiredAccess
0x1400232a4  call    cs:__imp_OpenProcess
0x1400232aa  mov     r14, rax
0x1400232ad  mov     [rsp+0D8h+var_98], rax
0x1400232b2  inc     rax
0x1400232b5  cmp     rax, 1
0x1400232b9  jbe     loc_1400233FA
0x1400232bf  lea     rax, [rbp+8AF0h]
0x1400232c6  mov     [rsp+0D8h+var_A0], 0; struct HPSS__ *
0x1400232cf  mov     [rsp+0D8h+var_A8], rax; struct _EXCEPTION_POINTERS *
0x1400232d4  mov     [rsp+0D8h+var_B0], 20000003h; unsigned int
0x1400232dc  mov     [rsp+0D8h+var_B8], 4; enum _WER_DUMP_TYPE
0x1400232e4  mov     r9d, r12d; unsigned int
0x1400232e7  mov     r8d, esi; unsigned int
0x1400232ea  mov     rdx, r14; void *
0x1400232ed  mov     rcx, [rbp+5F78h]; void *
0x1400232f4  call    ?_AddWerDumpForProcess@CHangReport@@KAJPEAX0KKW4_WER_DUMP_TYPE@@KPEAU_EXCEPTION_POINTERS@@PEAUHPSS__@@@Z; CHangReport::_AddWerDumpForProcess(void *,void *,ulong,ulong,_WER_DUMP_TYPE,ulong,_EXCEPTION_POINTERS *,HPSS__ *)
0x1400232f9  mov     ebx, eax
0x1400232fb  test    eax, eax
0x1400232fd  jns     short loc_140023365
0x1400232ff  lea     rdi, WPP_GLOBAL_Control
0x140023306  mov     rcx, cs:WPP_GLOBAL_Control
0x14002330d  cmp     rcx, rdi
0x140023310  jz      loc_14002351E
0x140023316  test    byte ptr [rcx+1Ch], 1
0x14002331a  jz      loc_14002351E
0x140023320  mov     edx, 38h ; '8'
0x140023325  jmp     loc_140023507
0x14002332a  lea     rdi, WPP_GLOBAL_Control
0x140023331  mov     rcx, cs:WPP_GLOBAL_Control
0x140023338  cmp     rcx, rdi
0x14002333b  jz      short loc_14002335B
0x14002333d  test    byte ptr [rcx+1Ch], 4
0x140023341  jz      short loc_14002335B
0x140023343  mov     edx, 36h ; '6'
0x140023348  mov     r9d, esi
0x14002334b  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x140023352  mov     rcx, [rcx+10h]
0x140023356  call    WPP_SF_d
0x14002335b  mov     ebx, 800700B7h
0x140023360  jmp     loc_14002351E
0x140023365  mov     r9d, esi
0x140023368  lea     r8, aTriagedump04xD; "triagedump.%04x.dmp"
0x14002336f  mov     edx, 20h ; ' '; unsigned __int64
0x140023374  lea     rcx, [rsp+0D8h+var_88]; wchar_t *
0x140023379  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x14002337e  mov     ebx, eax
0x140023380  test    eax, eax
0x140023382  jns     short loc_1400233AF
0x140023384  lea     rdi, WPP_GLOBAL_Control
0x14002338b  mov     rcx, cs:WPP_GLOBAL_Control
0x140023392  cmp     rcx, rdi
0x140023395  jz      loc_14002351E
0x14002339b  test    byte ptr [rcx+1Ch], 1
0x14002339f  jz      loc_14002351E
0x1400233a5  mov     edx, 39h ; '9'
0x1400233aa  jmp     loc_140023507
0x1400233af  mov     r9d, 1
0x1400233b5  mov     r8d, esi
0x1400233b8  lea     rdx, [rsp+0D8h+var_88]
0x1400233bd  mov     rcx, rbp
0x1400233c0  call    ?_AddFileToList@CHangReport@@IEAAJPEB_WKW4FAULTREP_CROSSPROCESS_FILE_TYPE@@@Z; CHangReport::_AddFileToList(wchar_t const *,ulong,FAULTREP_CROSSPROCESS_FILE_TYPE)
0x1400233c5  mov     ebx, eax
0x1400233c7  test    eax, eax
0x1400233c9  jns     loc_14002351C
0x1400233cf  lea     rdi, WPP_GLOBAL_Control
0x1400233d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400233dd  cmp     rcx, rdi
0x1400233e0  jz      loc_14002351E
0x1400233e6  test    byte ptr [rcx+1Ch], 1
0x1400233ea  jz      loc_14002351E
0x1400233f0  mov     edx, 3Ah ; ':'
0x1400233f5  jmp     loc_140023507
0x1400233fa  call    cs:__imp_GetLastError
0x140023400  test    eax, eax
0x140023402  jle     short loc_14002340C
0x140023404  movzx   eax, ax
0x140023407  or      eax, 80070000h
0x14002340c  lea     rdi, WPP_GLOBAL_Control
0x140023413  mov     rcx, cs:WPP_GLOBAL_Control
0x14002341a  cmp     rcx, rdi
0x14002341d  jz      short loc_14002343D
0x14002341f  test    byte ptr [rcx+1Ch], 2
0x140023423  jz      short loc_14002343D
0x140023425  mov     edx, 3Bh ; ';'
0x14002342a  mov     r9d, eax
0x14002342d  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x140023434  mov     rcx, [rcx+10h]
0x140023438  call    WPP_SF_d
0x14002343d  lea     r8, a1; "1"
0x140023444  lea     rdx, aDcXpdata; "dc.xpdata"
0x14002344b  lea     rcx, [rbp+5810h]; this
0x140023452  call    ?AddServerRequest@CElevatedDataCollection@@QEAAJPEB_W0@Z; CElevatedDataCollection::AddServerRequest(wchar_t const *,wchar_t const *)
0x140023457  mov     ebx, eax
0x140023459  test    eax, eax
0x14002345b  jns     short loc_140023481
0x14002345d  mov     rcx, cs:WPP_GLOBAL_Control
0x140023464  cmp     rcx, rdi
0x140023467  jz      loc_14002351E
0x14002346d  test    byte ptr [rcx+1Ch], 1
0x140023471  jz      loc_14002351E
0x140023477  mov     edx, 3Ch ; '<'
0x14002347c  jmp     loc_140023507
0x140023481  mov     [rsp+0D8h+var_B0], 0; unsigned int
0x140023489  mov     qword ptr [rsp+0D8h+var_B8], 0; wchar_t *
0x140023492  mov     r9d, r15d; unsigned int
0x140023495  mov     r8d, r12d; unsigned int
0x140023498  mov     edx, esi; dwProcessId
0x14002349a  lea     rcx, [rbp+5810h]; this
0x1400234a1  call    ?AddCrossProcessPid@CElevatedDataCollection@@QEAAJKKKPEB_WK@Z; CElevatedDataCollection::AddCrossProcessPid(ulong,ulong,ulong,wchar_t const *,ulong)
0x1400234a6  mov     ebx, eax
0x1400234a8  test    eax, eax
0x1400234aa  jns     short loc_14002351C
0x1400234ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400234b3  cmp     rcx, rdi
0x1400234b6  jz      short loc_14002351E
0x1400234b8  test    byte ptr [rcx+1Ch], 1
0x1400234bc  jz      short loc_14002351E
0x1400234be  mov     edx, 3Dh ; '='
0x1400234c3  jmp     short loc_140023507
0x1400234c5  lea     rcx, [rbp+5810h]; this
0x1400234cc  mov     [rsp+0D8h+var_B8], r15d; unsigned int
0x1400234d1  mov     r9d, r12d; unsigned int
0x1400234d4  mov     r8d, esi; dwProcessId
0x1400234d7  mov     rdx, [rbp+5F78h]; void *
0x1400234de  call    ?AddReflectedCrossProcessPid@CElevatedDataCollection@@QEAAJPEAXKKK@Z; CElevatedDataCollection::AddReflectedCrossProcessPid(void *,ulong,ulong,ulong)
0x1400234e3  mov     ebx, eax
0x1400234e5  test    eax, eax
0x1400234e7  jns     short loc_14002351C
0x1400234e9  lea     rdi, WPP_GLOBAL_Control
0x1400234f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400234f7  cmp     rcx, rdi
0x1400234fa  jz      short loc_14002351E
0x1400234fc  test    byte ptr [rcx+1Ch], 1
0x140023500  jz      short loc_14002351E
0x140023502  mov     edx, 37h ; '7'
0x140023507  mov     r9d, eax
0x14002350a  lea     r8, WPP_f1de6a7590de3fa4c1de946d67d2af95_Traceguids
0x140023511  mov     rcx, [rcx+10h]
0x140023515  call    WPP_SF_d
0x14002351a  jmp     short loc_14002351E
0x14002351c  xor     ebx, ebx
0x14002351e  lea     rax, [r14+1]
0x140023522  cmp     rax, 1
0x140023526  jbe     short loc_140023531
0x140023528  mov     rcx, r14; hObject
0x14002352b  call    cs:__imp_CloseHandle
0x140023531  mov     eax, ebx
0x140023533  mov     rcx, [rsp+0D8h+var_48]
0x14002353b  xor     rcx, rsp; StackCookie
0x14002353e  call    __security_check_cookie
0x140023543  add     rsp, 0A0h
0x14002354a  pop     r15
0x14002354c  pop     r14
0x14002354e  pop     r12
0x140023550  pop     rdi
0x140023551  pop     rsi
0x140023552  pop     rbp
0x140023553  pop     rbx
0x140023554  retn
```
