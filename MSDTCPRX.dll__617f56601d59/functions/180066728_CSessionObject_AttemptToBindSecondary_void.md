# CSessionObject::AttemptToBindSecondary(void)

- ea: `0x180066728`
- end: `0x180066b7e`
- name: `?AttemptToBindSecondary@CSessionObject@@AEAAJXZ`
- size: `1110`
- prototype: `__int64 __fastcall(CSessionObject *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001ca4`

## callees

- `0x180003cf0`
- `0x18000a5b4`
- `0x18000f674`
- `0x180012130`
- `0x18001234c`
- `0x1800123a8`
- `0x180066728`
- `0x180081dd0`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800667f2`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800667f2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180066b51`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180066b51`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800667be`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800667be`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18006684f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180066889`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180066a3b`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18006684f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180066889`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180066a3b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006686b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180066a1d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18006686b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180066a1d`

## string_xrefs

- `0x180066771`: `com\complus\dtc\dtc\cm\src\cso.cpp`
- `0x18006676a`: `CSessionObject::AttemptToBindSecondary`
- `0x180066855`: `Secondary: Poke Received E_CM_SERVER_NOT_READY Message`
- `0x1800668cf`: `Secondary: Session Bind Failed. The protocol Not Supported`
- `0x1800668f2`: `Secondary: Session Bind Failed. The protocol is not supported`
- `0x180066a75`: `STATUS : (SECONDARY)Attempt Failed.`
- `0x180066add`: `ERROR : Guids were different on SEC. Side.\n`

## pseudocode

```c
__int64 __fastcall CSessionObject::AttemptToBindSecondary(CSessionObject *this)
{
  unsigned int v2; // edi
  unsigned int i; // ebp
  unsigned int v4; // eax
  int v5; // esi
  DWORD TickCount; // eax
  int v7; // ecx
  unsigned int j; // ebp
  CSessionObject *v9; // rcx
  unsigned int v10; // eax
  DWORD v11; // eax
  int v12; // eax
  __int64 v13; // rdx
  void *v14; // rcx
  int v16; // [rsp+30h] [rbp-88h]
  char v17[40]; // [rsp+40h] [rbp-78h] BYREF

  v2 = 0;
  StringCbCopyA(v17, 0x25u, "00000000-0000-0000-0000-000000000000");
  if ( !*((_DWORD *)this + 4) )
  {
    for ( i = 0;
          i < (unsigned int)(*(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 81) + 136LL) + 8LL) + 1) >> 1
       && !*((_DWORD *)this + 4);
          ++i )
    {
      if ( !*((_DWORD *)this + 2) )
      {
        v2 = -2147467259;
        break;
      }
      ResetEvent(*((HANDLE *)this + 18));
      v4 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 80) + 16LL))(*((_QWORD *)this + 80));
      *((_DWORD *)this + 354) = v4;
      v2 = v4;
      if ( v4 )
      {
        switch ( v4 )
        {
          case 0x80000123:
            Sleep(0x3E8u);
            TraceStringInline(
              1,
              240,
              L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
              2256,
              L"CSessionObject::AttemptToBindSecondary",
              0,
              L"Secondary: Poke Received E_CM_SERVER_NOT_READY Message");
            break;
          case 0x80000101:
            TickCount = GetTickCount();
            Sleep(30 * (TickCount % 0x64));
            TraceStringInline(
              1,
              240,
              L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
              2263,
              L"CSessionObject::AttemptToBindSecondary",
              0,
              L"Secondary: Received E_S_UNAVAILABLE_OR_BUSY Message");
            break;
          case 0x80000173:
            DtcWriteToEventLoggerA(
              4u,
              3u,
              0x4000103Cu,
              0,
              0,
              "Secondary: Session Bind Failed. The protocol Not Supported",
              v16);
            TraceStringInline(
              1,
              2,
              L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
              2269,
              L"CSessionObject::AttemptToBindSecondary",
              0,
              L"Secondary: Session Bind Failed. The protocol is not supported");
            goto LABEL_22;
        }
      }
      else
      {
        v5 = 0;
        do
        {
          if ( WaitForSingleObject(*((HANDLE *)this + 18), 0x3E8u) )
            TraceStringInline(
              1,
              3,
              L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
              2244,
              L"CSessionObject::AttemptToBindSecondary",
              0,
              L"Wait for SecondaryBindEvent returned with 0x%x (0x102=Timeout, 0x80=Abandoned, 0xffffffff=Failed)");
          if ( *((_DWORD *)this + 4) == 1 )
            break;
          ++v5;
        }
        while ( !v5 );
      }
    }
  }
LABEL_22:
  v7 = *((_DWORD *)this + 4);
  if ( !v7 )
    return (unsigned int)-2147483344;
  if ( v7 == 1 )
  {
    for ( j = 0; ; ++j )
    {
      v9 = *(CSessionObject **)(*((_QWORD *)this + 81) + 136LL);
      if ( j >= (unsigned int)(*((_DWORD *)v9 + 2) + 1) >> 1 )
        break;
      TraceStringInline(
        1,
        240,
        L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
        2301,
        L"CSessionObject::AttemptToBindSecondary",
        0,
        L"SECONDARY: Taking the following  GUID with me %S",
        (char *)this + 48);
      v10 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *, char *))(**((_QWORD **)this + 80) + 8LL))(
              *((_QWORD *)this + 80),
              2,
              (char *)this + 48,
              v17);
      *((_DWORD *)this + 343) = v10;
      v2 = v10;
      StringCbCopyA((char *)this + 1376, 0x25u, v17);
      TraceStringInline(
        1,
        240,
        L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
        2313,
        L"CSessionObject::AttemptToBindSecondary",
        0,
        L"SECONDARY: Returned with the following  GUID with me %S",
        v17);
      if ( !v2 || !*((_DWORD *)this + 2) )
        break;
      if ( v2 != -2147483391 )
      {
        TraceStringInline(
          1,
          240,
          L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
          2331,
          L"CSessionObject::AttemptToBindSecondary",
          0,
          L"STATUS : (SECONDARY)Attempt Failed.");
        break;
      }
      v11 = GetTickCount();
      Sleep(30 * (v11 % 0x64));
      TraceStringInline(
        1,
        240,
        L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
        2327,
        L"CSessionObject::AttemptToBindSecondary",
        0,
        L"SECONDARY: Received E_S_UNAVAILABLE_OR_BUSY Message");
    }
    v12 = CSessionObject::AreGuidsEqual(v9, (unsigned __int8 *)this + 48, (unsigned __int8 *)v17);
    if ( v2 )
    {
      if ( v12 == 1 )
        goto LABEL_38;
    }
    else if ( v12 == 1 )
    {
      (***((void (__fastcall ****)(_QWORD))this + 21))(*((_QWORD *)this + 21));
      CSessionObject::SetStatus(this, 0);
      v13 = 5;
LABEL_37:
      CSessionObject::SetState(this, v13);
      goto LABEL_38;
    }
    TraceStringInline(
      1,
      3,
      L"com\\complus\\dtc\\dtc\\cm\\src\\cso.cpp",
      2352,
      L"CSessionObject::AttemptToBindSecondary",
      0,
      L"ERROR : Guids were different on SEC. Side.\n");
    StringCbCopyA((char *)this + 48, 0x25u, "00000000-0000-0000-0000-000000000000");
    CSessionObject::SetStatus(this, 1);
    if ( *((_DWORD *)this + 26) == 2 )
    {
      CSessionObject::SetStatus(this, 1);
      v13 = 4;
      goto LABEL_37;
    }
LABEL_38:
    v14 = (void *)*((_QWORD *)this + 17);
    *((_DWORD *)this + 4) = 0;
    SetEvent(v14);
  }
  return v2;
}

```

## disassembly

```asm
0x180066728  push    rbx
0x18006672a  push    rbp
0x18006672b  push    rsi
0x18006672c  push    rdi
0x18006672d  push    r12
0x18006672f  push    r13
0x180066731  push    r14
0x180066733  push    r15
0x180066735  sub     rsp, 78h
0x180066739  mov     rax, cs:__security_cookie
0x180066740  xor     rax, rsp
0x180066743  mov     [rsp+0B8h+var_50], rax
0x180066748  xor     r14d, r14d
0x18006674b  lea     r8, a00000000000000; "00000000-0000-0000-0000-000000000000"
0x180066752  mov     rbx, rcx
0x180066755  mov     edi, r14d
0x180066758  lea     rcx, [rsp+0B8h+var_78]; char *
0x18006675d  lea     edx, [r14+25h]; unsigned __int64
0x180066761  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x180066766  lea     r15d, [r14+1]
0x18006676a  lea     r13, aCsessionobject_4; "CSessionObject::AttemptToBindSecondary"
0x180066771  lea     r12, aComComplusDtcD_48; "com\\complus\\dtc\\dtc\\cm\\src\\cso.cp"...
0x180066778  cmp     [rbx+10h], r14d
0x18006677c  jnz     loc_180066925
0x180066782  mov     ebp, r14d
0x180066785  mov     rax, [rbx+288h]
0x18006678c  mov     rcx, [rax+88h]
0x180066793  mov     eax, [rcx+8]
0x180066796  add     eax, r15d
0x180066799  shr     eax, 1
0x18006679b  cmp     ebp, eax
0x18006679d  jnb     loc_180066925
0x1800667a3  cmp     [rbx+10h], r14d
0x1800667a7  jnz     loc_180066925
0x1800667ad  cmp     [rbx+8], r14d
0x1800667b1  jz      loc_180066920
0x1800667b7  mov     rcx, [rbx+90h]; hEvent
0x1800667be  call    cs:__imp_ResetEvent
0x1800667c4  mov     rcx, [rbx+280h]
0x1800667cb  mov     rax, [rcx]
0x1800667ce  mov     rax, [rax+10h]
0x1800667d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800667d7  mov     [rbx+588h], eax
0x1800667dd  mov     edi, eax
0x1800667df  test    eax, eax
0x1800667e1  jnz     short loc_180066843
0x1800667e3  mov     esi, r14d
0x1800667e6  mov     rcx, [rbx+90h]; hHandle
0x1800667ed  mov     edx, 3E8h; dwMilliseconds
0x1800667f2  call    cs:__imp_WaitForSingleObject
0x1800667f8  test    eax, eax
0x1800667fa  jz      short loc_18006682C
0x1800667fc  mov     dword ptr [rsp+0B8h+var_80], eax
0x180066800  mov     r9d, 8C4h
0x180066806  lea     rax, aWaitForSeconda; "Wait for SecondaryBindEvent returned wi"...
0x18006680d  mov     r8, r12
0x180066810  mov     [rsp+0B8h+var_88], rax
0x180066815  mov     edx, 3
0x18006681a  mov     [rsp+0B8h+var_90], r14
0x18006681f  mov     ecx, r15d
0x180066822  mov     [rsp+0B8h+var_98], r13
0x180066827  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18006682c  cmp     [rbx+10h], r15d
0x180066830  jz      loc_1800668C4
0x180066836  add     esi, r15d
0x180066839  cmp     esi, r15d
0x18006683c  jb      short loc_1800667E6
0x18006683e  jmp     loc_1800668C4
0x180066843  cmp     eax, 80000123h
0x180066848  jnz     short loc_180066864
0x18006684a  mov     ecx, 3E8h; dwMilliseconds
0x18006684f  call    cs:__imp_Sleep
0x180066855  lea     rax, aSecondaryPokeR; "Secondary: Poke Received E_CM_SERVER_NO"...
0x18006685c  mov     r9d, 8D0h
0x180066862  jmp     short loc_18006689C
0x180066864  cmp     eax, 80000101h
0x180066869  jnz     short loc_1800668BD
0x18006686b  call    cs:__imp_GetTickCount
0x180066871  mov     r8d, eax
0x180066874  mov     eax, 51EB851Fh
0x180066879  mul     r8d
0x18006687c  shr     edx, 5
0x18006687f  imul    ecx, edx, 64h ; 'd'
0x180066882  sub     r8d, ecx
0x180066885  imul    ecx, r8d, 1Eh; dwMilliseconds
0x180066889  call    cs:__imp_Sleep
0x18006688f  lea     rax, aSecondaryRecei_0; "Secondary: Received E_S_UNAVAILABLE_OR_"...
0x180066896  mov     r9d, 8D7h
0x18006689c  mov     [rsp+0B8h+var_88], rax
0x1800668a1  mov     r8, r12
0x1800668a4  mov     [rsp+0B8h+var_90], r14
0x1800668a9  mov     edx, 0F0h
0x1800668ae  mov     ecx, r15d
0x1800668b1  mov     [rsp+0B8h+var_98], r13
0x1800668b6  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x1800668bb  jmp     short loc_1800668C4
0x1800668bd  cmp     eax, 80000173h
0x1800668c2  jz      short loc_1800668CC
0x1800668c4  add     ebp, r15d
0x1800668c7  jmp     loc_180066785
0x1800668cc  xor     r9d, r9d; unsigned int
0x1800668cf  lea     rax, aSecondarySessi; "Secondary: Session Bind Failed. The pro"...
0x1800668d6  mov     [rsp+0B8h+var_90], rax; char *
0x1800668db  mov     r8d, 4000103Ch; unsigned int
0x1800668e1  mov     [rsp+0B8h+var_98], r14; void *
0x1800668e6  lea     edx, [r9+3]; unsigned int
0x1800668ea  lea     ecx, [rdx+1]; unsigned int
0x1800668ed  call    ?DtcWriteToEventLoggerA@@YAJKKKKPEAXPEADH@Z; DtcWriteToEventLoggerA(ulong,ulong,ulong,ulong,void *,char *,int)
0x1800668f2  lea     rax, aSecondarySessi_0; "Secondary: Session Bind Failed. The pro"...
0x1800668f9  mov     r9d, 8DDh
0x1800668ff  mov     [rsp+0B8h+var_88], rax
0x180066904  mov     r8, r12
0x180066907  mov     [rsp+0B8h+var_90], r14
0x18006690c  mov     edx, 2
0x180066911  mov     ecx, r15d
0x180066914  mov     [rsp+0B8h+var_98], r13
0x180066919  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18006691e  jmp     short loc_180066925
0x180066920  mov     edi, 80004005h
0x180066925  mov     ecx, [rbx+10h]
0x180066928  test    ecx, ecx
0x18006692a  jz      loc_180066B59
0x180066930  cmp     ecx, r15d
0x180066933  jnz     loc_180066B5E
0x180066939  mov     ebp, r14d
0x18006693c  lea     rsi, [rbx+30h]
0x180066940  mov     rax, [rbx+288h]
0x180066947  mov     rcx, [rax+88h]
0x18006694e  mov     eax, [rcx+8]
0x180066951  add     eax, r15d
0x180066954  shr     eax, 1
0x180066956  cmp     ebp, eax
0x180066958  jnb     loc_180066AA1
0x18006695e  mov     [rsp+0B8h+var_80], rsi
0x180066963  lea     rax, aSecondaryTakin; "SECONDARY: Taking the following  GUID w"...
0x18006696a  mov     [rsp+0B8h+var_88], rax
0x18006696f  mov     r9d, 8FDh
0x180066975  mov     [rsp+0B8h+var_90], r14
0x18006697a  mov     r8, r12
0x18006697d  mov     edx, 0F0h
0x180066982  mov     [rsp+0B8h+var_98], r13
0x180066987  mov     ecx, r15d
0x18006698a  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x18006698f  mov     rcx, [rbx+280h]
0x180066996  lea     r9, [rsp+0B8h+var_78]
0x18006699b  mov     r8, rsi
0x18006699e  mov     edx, 2
0x1800669a3  mov     rax, [rcx]
0x1800669a6  mov     rax, [rax+8]
0x1800669aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800669af  lea     rcx, [rbx+560h]; char *
0x1800669b6  mov     [rbx+55Ch], eax
0x1800669bc  lea     r8, [rsp+0B8h+var_78]; char *
0x1800669c1  mov     edx, 25h ; '%'; unsigned __int64
0x1800669c6  mov     edi, eax
0x1800669c8  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x1800669cd  lea     r10, [rsp+0B8h+var_78]
0x1800669d2  mov     r9d, 909h
0x1800669d8  mov     [rsp+0B8h+var_80], r10
0x1800669dd  lea     rax, aSecondaryRetur; "SECONDARY: Returned with the following "...
0x1800669e4  mov     [rsp+0B8h+var_88], rax
0x1800669e9  mov     r8, r12
0x1800669ec  mov     [rsp+0B8h+var_90], r14
0x1800669f1  mov     edx, 0F0h
0x1800669f6  mov     ecx, r15d
0x1800669f9  mov     [rsp+0B8h+var_98], r13
0x1800669fe  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180066a03  test    edi, edi
0x180066a05  jz      loc_180066AA1
0x180066a0b  cmp     [rbx+8], r14d
0x180066a0f  jz      loc_180066AA1
0x180066a15  cmp     edi, 80000101h
0x180066a1b  jnz     short loc_180066A75
0x180066a1d  call    cs:__imp_GetTickCount
0x180066a23  mov     r8d, eax
0x180066a26  mov     eax, 51EB851Fh
0x180066a2b  mul     r8d
0x180066a2e  shr     edx, 5
0x180066a31  imul    ecx, edx, 64h ; 'd'
0x180066a34  sub     r8d, ecx
0x180066a37  imul    ecx, r8d, 1Eh; dwMilliseconds
0x180066a3b  call    cs:__imp_Sleep
0x180066a41  lea     rax, aSecondaryRecei; "SECONDARY: Received E_S_UNAVAILABLE_OR_"...
0x180066a48  mov     r9d, 917h
0x180066a4e  mov     [rsp+0B8h+var_88], rax
0x180066a53  mov     r8, r12
0x180066a56  mov     [rsp+0B8h+var_90], r14
0x180066a5b  mov     edx, 0F0h
0x180066a60  mov     ecx, r15d
0x180066a63  mov     [rsp+0B8h+var_98], r13
0x180066a68  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180066a6d  add     ebp, r15d
0x180066a70  jmp     loc_180066940
0x180066a75  lea     rax, aStatusSecondar; "STATUS : (SECONDARY)Attempt Failed."
0x180066a7c  mov     r9d, 91Bh
0x180066a82  mov     [rsp+0B8h+var_88], rax
0x180066a87  mov     r8, r12
0x180066a8a  mov     [rsp+0B8h+var_90], r14
0x180066a8f  mov     edx, 0F0h
0x180066a94  mov     ecx, r15d
0x180066a97  mov     [rsp+0B8h+var_98], r13
0x180066a9c  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180066aa1  lea     r8, [rsp+0B8h+var_78]; unsigned __int8 *
0x180066aa6  mov     rdx, rsi; unsigned __int8 *
0x180066aa9  call    ?AreGuidsEqual@CSessionObject@@AEAAHPEAE0@Z; CSessionObject::AreGuidsEqual(uchar *,uchar *)
0x180066aae  test    edi, edi
0x180066ab0  jnz     short loc_180066AD8
0x180066ab2  cmp     eax, r15d
0x180066ab5  jnz     short loc_180066ADD
0x180066ab7  mov     rcx, [rbx+0A8h]
0x180066abe  mov     rax, [rcx]
0x180066ac1  mov     rax, [rax]
0x180066ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066ac9  xor     edx, edx
0x180066acb  mov     rcx, rbx
0x180066ace  call    ?SetStatus@CSessionObject@@QEAAXW4_SessionStatus@@@Z; CSessionObject::SetStatus(_SessionStatus)
0x180066ad3  lea     edx, [rdi+5]
0x180066ad6  jmp     short loc_180066B3E
0x180066ad8  cmp     eax, r15d
0x180066adb  jz      short loc_180066B46
0x180066add  lea     rax, aErrorGuidsWere; "ERROR : Guids were different on SEC. Si"...
0x180066ae4  mov     r9d, 930h
0x180066aea  mov     [rsp+0B8h+var_88], rax
0x180066aef  mov     r8, r12
0x180066af2  mov     [rsp+0B8h+var_90], r14
0x180066af7  mov     edx, 3
0x180066afc  mov     ecx, r15d
0x180066aff  mov     [rsp+0B8h+var_98], r13
0x180066b04  call    ?TraceStringInline@@YAXW4TraceSource@@EPEBGK1J1ZZ; TraceStringInline(TraceSource,uchar,ushort const *,ulong,ushort const *,long,ushort const *,...)
0x180066b09  lea     r8, a00000000000000; "00000000-0000-0000-0000-000000000000"
0x180066b10  mov     edx, 25h ; '%'; unsigned __int64
0x180066b15  mov     rcx, rsi; char *
0x180066b18  call    ?StringCbCopyA@@YAJPEAD_KPEBD@Z; StringCbCopyA(char *,unsigned __int64,char const *)
0x180066b1d  mov     edx, r15d
0x180066b20  mov     rcx, rbx
0x180066b23  call    ?SetStatus@CSessionObject@@QEAAXW4_SessionStatus@@@Z; CSessionObject::SetStatus(_SessionStatus)
0x180066b28  cmp     dword ptr [rbx+68h], 2
0x180066b2c  jnz     short loc_180066B46
0x180066b2e  mov     edx, r15d
0x180066b31  mov     rcx, rbx
0x180066b34  call    ?SetStatus@CSessionObject@@QEAAXW4_SessionStatus@@@Z; CSessionObject::SetStatus(_SessionStatus)
0x180066b39  mov     edx, 4
0x180066b3e  mov     rcx, rbx
0x180066b41  call    ?SetState@CSessionObject@@QEAAXW4_SessionState@@@Z; CSessionObject::SetState(_SessionState)
0x180066b46  mov     rcx, [rbx+88h]; hEvent
0x180066b4d  mov     [rbx+10h], r14d
0x180066b51  call    cs:__imp_SetEvent
0x180066b57  jmp     short loc_180066B5E
0x180066b59  mov     edi, 80000130h
0x180066b5e  mov     eax, edi
0x180066b60  mov     rcx, [rsp+0B8h+var_50]
0x180066b65  xor     rcx, rsp; StackCookie
0x180066b68  call    __security_check_cookie
0x180066b6d  add     rsp, 78h
0x180066b71  pop     r15
0x180066b73  pop     r14
0x180066b75  pop     r13
0x180066b77  pop     r12
0x180066b79  pop     rdi
0x180066b7a  pop     rsi
0x180066b7b  pop     rbp
0x180066b7c  pop     rbx
0x180066b7d  retn
```
