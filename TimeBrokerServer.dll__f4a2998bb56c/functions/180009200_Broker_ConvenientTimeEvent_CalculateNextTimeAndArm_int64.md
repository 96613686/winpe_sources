# Broker::ConvenientTimeEvent::CalculateNextTimeAndArm(__int64)

- ea: `0x180009200`
- end: `0x18000965c`
- name: `?CalculateNextTimeAndArm@ConvenientTimeEvent@Broker@@MEAAX_J@Z`
- size: `1116`
- prototype: `void __fastcall(Broker::ConvenientTimeEvent *__hidden this, __int64)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180003800`
- `0x180009200`
- `0x180009cf0`
- `0x180009e40`
- `0x180009f10`
- `0x18000a330`
- `0x180011240`
- `0x18001181c`
- `0x180012dd0`
- `0x180013978`
- `0x1800140f4`
- `0x180014168`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000924e`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800092da`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000924e`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800092da`

## pseudocode

```c
void __fastcall Broker::ConvenientTimeEvent::CalculateNextTimeAndArm(Broker::ConvenientTimeEvent *this, __int64 a2)
{
  __int64 v4; // r15
  __int64 v5; // r12
  __int64 v6; // rsi
  __int64 v7; // rdx
  struct _FILETIME v8; // r8
  __int64 v9; // rdx
  int v10; // eax
  __int64 v11; // rsi
  struct _FILETIME v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // r8
  _QWORD *v16; // rcx
  int v17; // ecx
  Broker::TimeEvent *v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  int v21; // ecx
  __int64 v22; // rax
  struct _FILETIME v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rax
  __int128 *v26; // r8
  struct _FILETIME FileTime; // [rsp+30h] [rbp-59h] BYREF
  __int64 v28; // [rsp+38h] [rbp-51h] BYREF
  _QWORD v29[3]; // [rsp+40h] [rbp-49h] BYREF
  int v30; // [rsp+58h] [rbp-31h]
  unsigned int v31; // [rsp+60h] [rbp-29h]
  _QWORD pExceptionObject[3]; // [rsp+68h] [rbp-21h] BYREF
  int v33; // [rsp+80h] [rbp-9h]
  unsigned int v34; // [rsp+88h] [rbp-1h]
  __int128 v35; // [rsp+90h] [rbp+7h] BYREF

  v4 = *((_QWORD *)this + 4);
  v5 = *((_QWORD *)this + 3);
  v6 = *((_QWORD *)this + 8);
  FileTime = 0;
  if ( !SystemTimeToFileTime((const SYSTEMTIME *)((char *)this + 280), &FileTime) )
  {
    Broker::Win32Error::Win32Error((Broker::Win32Error *)v29);
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_7b3fa50611f3300368cf2233e3ad1277_Traceguids, v31);
    std::exception::exception((std::exception *)pExceptionObject, (const struct std::exception *)v29);
    v33 = v30;
    pExceptionObject[0] = &Broker::Win32Error::`vftable';
    v34 = v31;
    throw (Broker::Win32Error *)pExceptionObject;
  }
  v8 = FileTime;
  if ( a2 >= *(_QWORD *)&FileTime )
  {
    v7 = (*(_QWORD *)&FileTime - a2) % v6;
    v8 = (struct _FILETIME)(v6 + a2 + v7);
  }
  if ( *((_BYTE *)this + 92) )
  {
    v17 = (int)WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))WPP_SF__guid_ll)(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v7,
        v8,
        *((_QWORD *)this + 31),
        *((_DWORD *)this + 22),
        0);
    if ( (Microsoft_Windows_TimeBrokerEnableBits & 1) != 0 )
      McTemplateU0jqq_EventWriteTransfer(v17, v7, *((_QWORD *)this + 31), *((_DWORD *)this + 22), 0);
    *((_DWORD *)this + 22) = 0;
  }
  else
  {
    v9 = v5 / 2 + v4 / 2;
    v10 = *((_DWORD *)this + 22);
    if ( v10 != 4 )
    {
      if ( v10 == 2 )
      {
        if ( (*((_BYTE *)this + 304) & 1) != 0 )
        {
          v21 = (int)WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
            ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))WPP_SF__guid_ll)(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v9,
              v8,
              *((_QWORD *)this + 31),
              2,
              3);
          if ( (Microsoft_Windows_TimeBrokerEnableBits & 1) != 0 )
            McTemplateU0jqq_EventWriteTransfer(v21, v9, *((_QWORD *)this + 31), *((_DWORD *)this + 22), 3);
          *((_DWORD *)this + 22) = 3;
        }
        else
        {
          v11 = *((_QWORD *)this + 8);
          if ( v9 > a2 )
            a2 = v5 / 2 + v4 / 2;
          FileTime = 0;
          if ( !SystemTimeToFileTime((const SYSTEMTIME *)((char *)this + 280), &FileTime) )
          {
            Broker::Win32Error::Win32Error((Broker::Win32Error *)pExceptionObject);
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_7b3fa50611f3300368cf2233e3ad1277_Traceguids, v34);
            std::exception::exception((std::exception *)v29, (const struct std::exception *)pExceptionObject);
            v30 = v33;
            v29[0] = &Broker::Win32Error::`vftable';
            v31 = v34;
            throw (Broker::Win32Error *)v29;
          }
          v12 = FileTime;
          if ( a2 >= *(_QWORD *)&FileTime )
            v12 = (struct _FILETIME)(v11 + a2 + (*(_QWORD *)&FileTime - a2) % v11);
          *((_QWORD *)this + 10) = 0;
          v13 = *((_QWORD *)this + 7) / 2LL;
          v14 = *(_QWORD *)&v12 - v13;
          *((_QWORD *)this + 3) = *(_QWORD *)&v12 - v13;
          v15 = v13 + *(_QWORD *)&v12;
          *((_QWORD *)this + 4) = v13 + *(_QWORD *)&v12;
          v16 = WPP_GLOBAL_Control;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          {
            WPP_SF__guid_ii(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, v15, *((_QWORD *)this + 31), v14, v15);
            v16 = WPP_GLOBAL_Control;
          }
          LOBYTE(FileTime.dwLowDateTime) = Microsoft_Windows_TimeBrokerEnableBits & 1;
          if ( (Microsoft_Windows_TimeBrokerEnableBits & 1) != 0 )
          {
            v23 = (struct _FILETIME)*((_QWORD *)this + 4);
            v24 = *((_QWORD *)this + 3);
            v25 = *((_QWORD *)this + 31);
            v35 = 0;
            v26 = &v35;
            if ( v25 )
              LODWORD(v26) = v25;
            v28 = v24;
            FileTime = v23;
            McTemplateU0jmm_EventWriteTransfer(
              v24,
              v23.dwLowDateTime,
              (_DWORD)v26,
              (unsigned int)&v28,
              (__int64)&FileTime);
            v16 = WPP_GLOBAL_Control;
          }
          if ( (*((_BYTE *)v16 + 28) & 0x40) != 0 && *((_BYTE *)v16 + 25) >= 4u )
            WPP_SF__guid_ll(v16[2], v14, v15, *((_QWORD *)this + 31), *((_DWORD *)this + 22), 1);
          if ( (Microsoft_Windows_TimeBrokerEnableBits & 1) != 0 )
            McTemplateU0jqq_EventWriteTransfer((_DWORD)v16, v14, *((_QWORD *)this + 31), *((_DWORD *)this + 22), 1);
          *((_DWORD *)this + 22) = 1;
        }
        return;
      }
      v20 = *(_QWORD *)&v8 - v9;
      if ( *(_QWORD *)&v8 - v9 < 0 )
        v20 = v9 - *(_QWORD *)&v8;
      if ( v20 > *((_QWORD *)this + 8) )
        v9 = (__int64)v8;
LABEL_38:
      Broker::TimeEvent::ArmTimeEvent((__int64)this, v9);
      return;
    }
    if ( v9 )
      goto LABEL_38;
    v18 = (Broker::TimeEvent *)Broker::TimeEvent::DueDateToUtcDueTime(
                                 (Broker::TimeEvent *)(v5 / 2),
                                 (const struct _SYSTEMTIME *)((char *)this + 280),
                                 0);
    if ( a2 < (__int64)v18 )
    {
      v22 = Broker::TimeEvent::DueDateToUtcDueTime(v18, (const struct _SYSTEMTIME *)((char *)this + 280), 0);
      Broker::TimeEvent::ArmTimeEvent((__int64)this, v22);
    }
    else
    {
      v19 = (__int64)v18 + *((_QWORD *)this + 8);
      if ( a2 > v19 )
        v19 = a2;
      Broker::TimeEvent::ArmTimeEvent((__int64)this, v19);
    }
  }
}

```

## disassembly

```asm
0x180009200  mov     [rsp-8+arg_10], rbx
0x180009205  push    rbp
0x180009206  push    rsi
0x180009207  push    rdi
0x180009208  push    r12
0x18000920a  push    r13
0x18000920c  push    r14
0x18000920e  push    r15
0x180009210  lea     rbp, [rsp-27h]
0x180009215  sub     rsp, 0B0h
0x18000921c  mov     rax, cs:__security_cookie
0x180009223  xor     rax, rsp
0x180009226  mov     [rbp+57h+var_40], rax
0x18000922a  mov     rdi, rdx
0x18000922d  mov     rbx, rcx
0x180009230  mov     r15, [rcx+20h]
0x180009234  mov     r12, [rcx+18h]
0x180009238  mov     rsi, [rcx+40h]
0x18000923c  xor     r13d, r13d
0x18000923f  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], r13
0x180009243  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x180009247  add     rcx, 118h; lpSystemTime
0x18000924e  call    cs:__imp_SystemTimeToFileTime
0x180009254  test    eax, eax
0x180009256  jz      loc_1800094E3
0x18000925c  mov     r8, qword ptr [rbp+57h+FileTime.dwLowDateTime]
0x180009260  cmp     rdi, r8
0x180009263  jl      short loc_180009277
0x180009265  sub     r8, rdi
0x180009268  mov     rax, r8
0x18000926b  cqo
0x18000926d  idiv    rsi
0x180009270  lea     r8, [rdi+rdx]
0x180009274  add     r8, rsi
0x180009277  cmp     [rbx+5Ch], r13b
0x18000927b  jnz     loc_1800093D1
0x180009281  mov     rax, r12
0x180009284  cqo
0x180009286  sub     rax, rdx
0x180009289  sar     rax, 1
0x18000928c  mov     rcx, rax; this
0x18000928f  mov     rax, r15
0x180009292  cqo
0x180009294  sub     rax, rdx
0x180009297  sar     rax, 1
0x18000929a  lea     rdx, [rcx+rax]
0x18000929e  mov     eax, [rbx+58h]
0x1800092a1  cmp     eax, 4
0x1800092a4  jz      loc_180009413
0x1800092aa  cmp     eax, 2
0x1800092ad  jnz     loc_180009451
0x1800092b3  test    byte ptr [rbx+130h], 1
0x1800092ba  jnz     loc_180009478
0x1800092c0  mov     rsi, [rbx+40h]
0x1800092c4  cmp     rdx, rdi
0x1800092c7  cmovg   rdi, rdx
0x1800092cb  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], r13
0x1800092cf  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x1800092d3  lea     rcx, [rbx+118h]; lpSystemTime
0x1800092da  call    cs:__imp_SystemTimeToFileTime
0x1800092e0  test    eax, eax
0x1800092e2  jz      loc_180009585
0x1800092e8  mov     rcx, qword ptr [rbp+57h+FileTime.dwLowDateTime]
0x1800092ec  cmp     rdi, rcx
0x1800092ef  jl      short loc_180009303
0x1800092f1  sub     rcx, rdi
0x1800092f4  mov     rax, rcx
0x1800092f7  cqo
0x1800092f9  idiv    rsi
0x1800092fc  lea     rcx, [rdi+rdx]
0x180009300  add     rcx, rsi
0x180009303  mov     [rbx+50h], r13
0x180009307  mov     rax, [rbx+38h]
0x18000930b  cqo
0x18000930d  sub     rax, rdx
0x180009310  sar     rax, 1
0x180009313  mov     rdx, rcx
0x180009316  sub     rdx, rax
0x180009319  mov     [rbx+18h], rdx
0x18000931d  lea     r8, [rax+rcx]
0x180009321  mov     [rbx+20h], r8
0x180009325  mov     rcx, cs:WPP_GLOBAL_Control
0x18000932c  test    byte ptr [rcx+1Ch], 40h
0x180009330  jz      short loc_180009359
0x180009332  cmp     byte ptr [rcx+19h], 4
0x180009336  jb      short loc_180009359
0x180009338  mov     [rsp+0E0h+var_B8], r8
0x18000933d  mov     [rsp+0E0h+var_C0], rdx
0x180009342  mov     r9, [rbx+0F8h]
0x180009349  mov     rcx, [rcx+10h]
0x18000934d  call    WPP_SF__guid_ii
0x180009352  mov     rcx, cs:WPP_GLOBAL_Control
0x180009359  movzx   eax, cs:Microsoft_Windows_TimeBrokerEnableBits
0x180009360  and     al, 1
0x180009362  mov     byte ptr [rbp+57h+FileTime.dwLowDateTime], al
0x180009365  jnz     loc_1800095F0
0x18000936b  test    byte ptr [rcx+1Ch], 40h
0x18000936f  jz      short loc_180009396
0x180009371  cmp     byte ptr [rcx+19h], 4
0x180009375  jb      short loc_180009396
0x180009377  mov     dword ptr [rsp+0E0h+var_B8], 1
0x18000937f  mov     eax, [rbx+58h]
0x180009382  mov     dword ptr [rsp+0E0h+var_C0], eax
0x180009386  mov     r9, [rbx+0F8h]
0x18000938d  mov     rcx, [rcx+10h]
0x180009391  call    WPP_SF__guid_ll
0x180009396  test    cs:Microsoft_Windows_TimeBrokerEnableBits, 1
0x18000939d  jnz     loc_180009637
0x1800093a3  mov     dword ptr [rbx+58h], 1
0x1800093aa  mov     rcx, [rbp+57h+var_40]
0x1800093ae  xor     rcx, rsp; StackCookie
0x1800093b1  call    __security_check_cookie
0x1800093b6  mov     rbx, [rsp+0E0h+arg_10]
0x1800093be  add     rsp, 0B0h
0x1800093c5  pop     r15
0x1800093c7  pop     r14
0x1800093c9  pop     r13
0x1800093cb  pop     r12
0x1800093cd  pop     rdi
0x1800093ce  pop     rsi
0x1800093cf  pop     rbp
0x1800093d0  retn
0x1800093d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800093d8  test    byte ptr [rcx+1Ch], 40h
0x1800093dc  jz      short loc_180009400
0x1800093de  cmp     byte ptr [rcx+19h], 4
0x1800093e2  jb      short loc_180009400
0x1800093e4  mov     dword ptr [rsp+0E0h+var_B8], r13d
0x1800093e9  mov     eax, [rbx+58h]
0x1800093ec  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1800093f0  mov     r9, [rbx+0F8h]
0x1800093f7  mov     rcx, [rcx+10h]
0x1800093fb  call    WPP_SF__guid_ll
0x180009400  test    cs:Microsoft_Windows_TimeBrokerEnableBits, 1
0x180009407  jnz     loc_18000954E
0x18000940d  mov     [rbx+58h], r13d
0x180009411  jmp     short loc_1800093AA
0x180009413  test    rdx, rdx
0x180009416  jnz     short loc_18000946B
0x180009418  xor     r8d, r8d; bool
0x18000941b  lea     rdx, [rbx+118h]; struct _SYSTEMTIME *
0x180009422  call    ?DueDateToUtcDueTime@TimeEvent@Broker@@IEAA_JAEBU_SYSTEMTIME@@_N@Z; Broker::TimeEvent::DueDateToUtcDueTime(_SYSTEMTIME const &,bool)
0x180009427  mov     rcx, rax; this
0x18000942a  cmp     rdi, rax
0x18000942d  jl      loc_1800094C4
0x180009433  mov     rax, [rbx+40h]
0x180009437  add     rax, rcx
0x18000943a  cmp     rdi, rax
0x18000943d  cmovg   rax, rdi
0x180009441  mov     rdx, rax
0x180009444  mov     rcx, rbx
0x180009447  call    ?ArmTimeEvent@TimeEvent@Broker@@IEAAX_JW4States@12@@Z; Broker::TimeEvent::ArmTimeEvent(__int64,Broker::TimeEvent::States)
0x18000944c  jmp     loc_1800093AA
0x180009451  mov     rcx, rdx
0x180009454  sub     rcx, r8
0x180009457  mov     rax, rcx
0x18000945a  neg     rax
0x18000945d  cmovs   rax, rcx
0x180009461  cmp     rax, [rbx+40h]
0x180009465  jg      loc_180009654
0x18000946b  mov     rcx, rbx
0x18000946e  call    ?ArmTimeEvent@TimeEvent@Broker@@IEAAX_JW4States@12@@Z; Broker::TimeEvent::ArmTimeEvent(__int64,Broker::TimeEvent::States)
0x180009473  jmp     loc_1800093AA
0x180009478  mov     rcx, cs:WPP_GLOBAL_Control
0x18000947f  test    byte ptr [rcx+1Ch], 40h
0x180009483  jz      short loc_1800094AB
0x180009485  cmp     byte ptr [rcx+19h], 4
0x180009489  jb      short loc_1800094AB
0x18000948b  mov     dword ptr [rsp+0E0h+var_B8], 3
0x180009493  mov     dword ptr [rsp+0E0h+var_C0], 2
0x18000949b  mov     r9, [rbx+0F8h]
0x1800094a2  mov     rcx, [rcx+10h]
0x1800094a6  call    WPP_SF__guid_ll
0x1800094ab  test    cs:Microsoft_Windows_TimeBrokerEnableBits, 1
0x1800094b2  jnz     loc_180009568
0x1800094b8  mov     dword ptr [rbx+58h], 3
0x1800094bf  jmp     loc_1800093AA
0x1800094c4  xor     r8d, r8d; bool
0x1800094c7  lea     rdx, [rbx+118h]; struct _SYSTEMTIME *
0x1800094ce  call    ?DueDateToUtcDueTime@TimeEvent@Broker@@IEAA_JAEBU_SYSTEMTIME@@_N@Z; Broker::TimeEvent::DueDateToUtcDueTime(_SYSTEMTIME const &,bool)
0x1800094d3  mov     rdx, rax
0x1800094d6  mov     rcx, rbx
0x1800094d9  call    ?ArmTimeEvent@TimeEvent@Broker@@IEAAX_JW4States@12@@Z; Broker::TimeEvent::ArmTimeEvent(__int64,Broker::TimeEvent::States)
0x1800094de  jmp     loc_1800093AA
0x1800094e3  lea     rcx, [rbp+57h+var_A0]; this
0x1800094e7  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x1800094ec  nop
0x1800094ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800094f4  test    byte ptr [rcx+1Ch], 40h
0x1800094f8  jz      short loc_180009519
0x1800094fa  cmp     byte ptr [rcx+19h], 2
0x1800094fe  jb      short loc_180009519
0x180009500  mov     edx, 17h
0x180009505  mov     r9d, [rbp+57h+var_80]
0x180009509  lea     r8, WPP_7b3fa50611f3300368cf2233e3ad1277_Traceguids
0x180009510  mov     rcx, [rcx+10h]
0x180009514  call    WPP_SF_d
0x180009519  lea     rdx, [rbp+57h+var_A0]; struct std::exception *
0x18000951d  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180009521  call    ??0exception@std@@QEAA@AEBV01@@Z; std::exception::exception(std::exception const &)
0x180009526  mov     eax, [rbp+57h+var_88]
0x180009529  mov     [rbp+57h+var_60], eax
0x18000952c  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180009533  mov     [rbp+57h+pExceptionObject], rax
0x180009537  mov     eax, [rbp+57h+var_80]
0x18000953a  mov     [rbp+57h+var_58], eax
0x18000953d  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180009544  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180009548  call    _CxxThrowException_0
0x18000954e  mov     dword ptr [rsp+0E0h+var_C0], r13d
0x180009553  mov     r9d, [rbx+58h]
0x180009557  mov     r8, [rbx+0F8h]
0x18000955e  call    McTemplateU0jqq_EventWriteTransfer
0x180009563  jmp     loc_18000940D
0x180009568  mov     dword ptr [rsp+0E0h+var_C0], 3
0x180009570  mov     r9d, [rbx+58h]
0x180009574  mov     r8, [rbx+0F8h]
0x18000957b  call    McTemplateU0jqq_EventWriteTransfer
0x180009580  jmp     loc_1800094B8
0x180009585  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180009589  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x18000958e  nop
0x18000958f  mov     rcx, cs:WPP_GLOBAL_Control
0x180009596  test    byte ptr [rcx+1Ch], 40h
0x18000959a  jz      short loc_1800095BB
0x18000959c  cmp     byte ptr [rcx+19h], 2
0x1800095a0  jb      short loc_1800095BB
0x1800095a2  mov     edx, 17h
0x1800095a7  mov     r9d, [rbp+57h+var_58]
0x1800095ab  lea     r8, WPP_7b3fa50611f3300368cf2233e3ad1277_Traceguids
0x1800095b2  mov     rcx, [rcx+10h]
0x1800095b6  call    WPP_SF_d
0x1800095bb  lea     rdx, [rbp+57h+pExceptionObject]; struct std::exception *
0x1800095bf  lea     rcx, [rbp+57h+var_A0]; this
0x1800095c3  call    ??0exception@std@@QEAA@AEBV01@@Z; std::exception::exception(std::exception const &)
0x1800095c8  mov     eax, [rbp+57h+var_60]
0x1800095cb  mov     [rbp+57h+var_88], eax
0x1800095ce  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x1800095d5  mov     [rbp+57h+var_A0], rax
0x1800095d9  mov     eax, [rbp+57h+var_58]
0x1800095dc  mov     [rbp+57h+var_80], eax
0x1800095df  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x1800095e6  lea     rcx, [rbp+57h+var_A0]; pExceptionObject
0x1800095ea  call    _CxxThrowException_0
0x1800095f0  mov     rdx, [rbx+20h]
0x1800095f4  mov     rcx, [rbx+18h]
0x1800095f8  mov     rax, [rbx+0F8h]
0x1800095ff  xorps   xmm0, xmm0
0x180009602  movups  [rbp+57h+var_50], xmm0
0x180009606  lea     r8, [rbp+57h+var_50]
0x18000960a  test    rax, rax
0x18000960d  cmovnz  r8, rax
0x180009611  mov     [rbp+57h+var_A8], rcx
0x180009615  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], rdx
0x180009619  lea     rax, [rbp+57h+FileTime]
0x18000961d  mov     [rsp+0E0h+var_C0], rax
0x180009622  lea     r9, [rbp+57h+var_A8]
0x180009626  call    McTemplateU0jmm_EventWriteTransfer
0x18000962b  mov     rcx, cs:WPP_GLOBAL_Control
0x180009632  jmp     loc_18000936B
0x180009637  mov     dword ptr [rsp+0E0h+var_C0], 1
0x18000963f  mov     r9d, [rbx+58h]
0x180009643  mov     r8, [rbx+0F8h]
0x18000964a  call    McTemplateU0jqq_EventWriteTransfer
0x18000964f  jmp     loc_1800093A3
0x180009654  mov     rdx, r8
0x180009657  jmp     loc_18000946B
```
