# Broker::CAlarmTimeEvent::CalculateNextTimeAndArm(__int64)

- ea: `0x180009750`
- end: `0x180009cea`
- name: `?CalculateNextTimeAndArm@CAlarmTimeEvent@Broker@@MEAAX_J@Z`
- size: `1434`
- prototype: `void __fastcall(Broker::CAlarmTimeEvent *this, struct _SYSTEMTIME *, __int64)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x180003800`
- `0x180009750`
- `0x180009e40`
- `0x180009ea0`
- `0x180009f10`
- `0x180009f70`
- `0x180009fc0`
- `0x180011240`
- `0x1800113dc`
- `0x18001181c`
- `0x180012dd0`
- `0x180013978`
- `0x1800140f4`
- `0x180014168`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800097ce`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800097ce`
- `api-ms-win-core-file-l1-1-0!LocalFileTimeToFileTime` at `0x180009be4`
- `api-ms-win-core-file-l1-1-0!LocalFileTimeToFileTime` at `0x180009be4`

## pseudocode

```c
void __fastcall Broker::CAlarmTimeEvent::CalculateNextTimeAndArm(
        Broker::CAlarmTimeEvent *this,
        struct _SYSTEMTIME *a2,
        __int64 a3)
{
  struct _SYSTEMTIME *v3; // rdi
  __int64 v5; // rbx
  _QWORD *v6; // rcx
  char v7; // r14
  __int64 v8; // r8
  struct _FILETIME v9; // r14
  __int64 *v10; // r15
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  _QWORD *v14; // rcx
  __int64 v15; // r11
  __int64 v16; // r10
  __int64 v17; // rcx
  __int128 v18; // rax
  __int64 v19; // r14
  int v20; // ecx
  __int64 v21; // r8
  FILETIME v22; // rdx
  struct _FILETIME v23; // rcx
  __int64 v24; // rax
  __int128 *v25; // r8
  union _ULARGE_INTEGER v26; // [rsp+30h] [rbp-59h] BYREF
  struct _FILETIME FileTime; // [rsp+38h] [rbp-51h] BYREF
  FILETIME LocalFileTime; // [rsp+40h] [rbp-49h] BYREF
  __int64 v29; // [rsp+48h] [rbp-41h]
  _QWORD v30[3]; // [rsp+50h] [rbp-39h] BYREF
  int v31; // [rsp+68h] [rbp-21h]
  unsigned int v32; // [rsp+70h] [rbp-19h]
  _QWORD pExceptionObject[3]; // [rsp+78h] [rbp-11h] BYREF
  int v34; // [rsp+90h] [rbp+7h]
  unsigned int v35; // [rsp+98h] [rbp+Fh]
  __int128 v36; // [rsp+A0h] [rbp+17h] BYREF

  v3 = a2;
  v5 = *(_QWORD *)(*((_QWORD *)this + 31) + 16LL);
  v29 = v5;
  v26.LowPart = 0;
  v6 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_DD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      &WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids,
      (unsigned int)v5,
      HIDWORD(v5));
    v6 = WPP_GLOBAL_Control;
  }
  if ( *((_BYTE *)this + 92) )
  {
    if ( (*((_BYTE *)v6 + 28) & 0x40) != 0 && *((_BYTE *)v6 + 25) >= 4u )
      WPP_SF__guid_ll(v6[2], a2, a3, *((_QWORD *)this + 31), *((_DWORD *)this + 22), 0);
    if ( (Microsoft_Windows_TimeBrokerEnableBits & 1) != 0 )
      McTemplateU0jqq_EventWriteTransfer((_DWORD)v6, (_DWORD)a2, *((_QWORD *)this + 31), *((_DWORD *)this + 22), 0);
    *((_DWORD *)this + 22) = 0;
  }
  else
  {
    v7 = *((_BYTE *)this + 322);
    FileTime = 0;
    LocalFileTime = 0;
    if ( !SystemTimeToFileTime((const SYSTEMTIME *)((char *)this + 284), &FileTime) )
    {
      Broker::Win32Error::Win32Error((Broker::Win32Error *)v30);
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_7b3fa50611f3300368cf2233e3ad1277_Traceguids, v32);
      std::exception::exception((std::exception *)pExceptionObject, (const struct std::exception *)v30);
      v34 = v31;
      pExceptionObject[0] = &Broker::Win32Error::`vftable';
      v35 = v32;
      throw (Broker::Win32Error *)pExceptionObject;
    }
    if ( v7 )
    {
      LocalFileTime = FileTime;
      if ( !LocalFileTimeToFileTime(&LocalFileTime, &FileTime) )
      {
        Broker::Win32Error::Win32Error((Broker::Win32Error *)pExceptionObject);
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_7b3fa50611f3300368cf2233e3ad1277_Traceguids, v35);
        std::exception::exception((std::exception *)v30, (const struct std::exception *)pExceptionObject);
        v31 = v34;
        v30[0] = &Broker::Win32Error::`vftable';
        v32 = v35;
        throw (Broker::Win32Error *)v30;
      }
    }
    v9 = FileTime;
    LocalFileTime = FileTime;
    if ( *((_BYTE *)this + 321) && *((_BYTE *)this + 320) )
    {
      v21 = *((_QWORD *)this + 7) / 2LL + *((_QWORD *)this + 38);
      *((_QWORD *)this + 4) = v21;
      *((_QWORD *)this + 3) = v21;
      Broker::TimeEvent::SetState(this, 1);
    }
    else
    {
      if ( *((_DWORD *)this + 22) == 4 || !*((_QWORD *)this + 39) )
      {
        v10 = (__int64 *)((char *)this + 56);
      }
      else
      {
        v15 = *((_QWORD *)this + 8);
        if ( !v15 && !*((_DWORD *)this + 82) )
        {
          Broker::TimeEvent::SetState(this, 3);
          return;
        }
        v10 = (__int64 *)((char *)this + 56);
        v16 = *((_QWORD *)this + 7) / 2LL;
        if ( *(_QWORD *)&FileTime - v16 < (__int64)v3 )
        {
          v8 = *((_QWORD *)this + 4);
          v17 = v8 - *((_QWORD *)this + 7);
          if ( *((_DWORD *)this + 82) )
          {
            if ( (__int64)v3 > v17 && (__int64)v3 < v8 )
              v3 = (struct _SYSTEMTIME *)*((_QWORD *)this + 4);
            Broker::CalculateDelay(
              (Broker::CAlarmTimeEvent *)((char *)this + 328),
              v3,
              (union _ULARGE_INTEGER)&LocalFileTime,
              &v26);
            v9 = (struct _FILETIME)&v3[625000 * v26.LowPart];
          }
          else
          {
            if ( (__int64)v3 < v17 || v8 < (__int64)v3 )
              v8 = (__int64)v3;
            if ( v8 >= *(_QWORD *)&FileTime )
              v9 = (struct _FILETIME)(10000000LL * *((unsigned int *)this + 70)
                                    + v8
                                    + (*(_QWORD *)&FileTime - v8) % (10000000LL * *((unsigned int *)this + 70)));
            if ( (__int64)v3 >= *(_QWORD *)&v9 - v16 && (__int64)v3 <= v16 + *(_QWORD *)&v9 )
              *(_QWORD *)&v9 += v15;
          }
        }
      }
      if ( *((_BYTE *)this + 321) )
      {
        *((struct _FILETIME *)this + 38) = v9;
        v18 = *v10;
        v19 = *(_QWORD *)&v9 - *v10 / 2;
        *((_QWORD *)this + 4) = v19;
        *((_QWORD *)this + 3) = v19;
        v20 = (int)WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          WPP_SF__guid_ll(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            *((_QWORD *)&v18 + 1),
            v8,
            *((_QWORD *)this + 31),
            *((_DWORD *)this + 22),
            1);
        if ( (Microsoft_Windows_TimeBrokerEnableBits & 1) != 0 )
          McTemplateU0jqq_EventWriteTransfer(v20, DWORD2(v18), *((_QWORD *)this + 31), *((_DWORD *)this + 22), 1);
        *((_DWORD *)this + 22) = 1;
      }
      else
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_i)(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            17,
            &WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids,
            v9);
        *((_QWORD *)this + 10) = 0;
        v11 = *v10 / 2;
        v12 = *(_QWORD *)&v9 - v11;
        *((_QWORD *)this + 3) = *(_QWORD *)&v9 - v11;
        v13 = v11 + *(_QWORD *)&v9;
        *((_QWORD *)this + 4) = v11 + *(_QWORD *)&v9;
        v14 = WPP_GLOBAL_Control;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF__guid_ii(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v12,
            v13,
            *((_QWORD *)this + 31),
            *(_QWORD *)&v9 - v11,
            v11 + *(_QWORD *)&v9);
          v14 = WPP_GLOBAL_Control;
        }
        if ( (Microsoft_Windows_TimeBrokerEnableBits & 1) != 0 )
        {
          v22 = (FILETIME)*((_QWORD *)this + 4);
          v23 = (struct _FILETIME)*((_QWORD *)this + 3);
          v24 = *((_QWORD *)this + 31);
          v36 = 0;
          v25 = &v36;
          if ( v24 )
            LODWORD(v25) = v24;
          FileTime = v23;
          LocalFileTime = v22;
          McTemplateU0jmm_EventWriteTransfer(
            v23.dwLowDateTime,
            v22.dwLowDateTime,
            (_DWORD)v25,
            (unsigned int)&FileTime,
            (__int64)&LocalFileTime);
          v14 = WPP_GLOBAL_Control;
        }
        if ( (*((_BYTE *)v14 + 28) & 0x40) != 0 && *((_BYTE *)v14 + 25) >= 4u )
          WPP_SF__guid_ll(v14[2], v12, v13, *((_QWORD *)this + 31), *((_DWORD *)this + 22), 1);
        if ( (Microsoft_Windows_TimeBrokerEnableBits & 1) != 0 )
          McTemplateU0jqq_EventWriteTransfer((_DWORD)v14, v12, *((_QWORD *)this + 31), *((_DWORD *)this + 22), 1);
        *((_DWORD *)this + 22) = 1;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
          WPP_SF_DD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            18,
            &WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids,
            (unsigned int)v5,
            HIDWORD(v29));
      }
    }
  }
}

```

## disassembly

```asm
0x180009750  mov     [rsp-8+arg_10], rbx
0x180009755  mov     [rsp-8+arg_18], rsi
0x18000975a  push    rbp
0x18000975b  push    rdi
0x18000975c  push    r12
0x18000975e  push    r14
0x180009760  push    r15
0x180009762  lea     rbp, [rsp-37h]
0x180009767  sub     rsp, 0C0h
0x18000976e  mov     rax, cs:__security_cookie
0x180009775  xor     rax, rsp
0x180009778  mov     [rbp+57h+var_30], rax
0x18000977c  mov     rdi, rdx
0x18000977f  mov     rsi, rcx
0x180009782  mov     rbx, [rcx+0F8h]
0x180009789  mov     rbx, [rbx+10h]
0x18000978d  mov     [rbp+57h+var_98], rbx
0x180009791  xor     r12d, r12d
0x180009794  mov     dword ptr [rbp+57h+var_B0], r12d
0x180009798  mov     rcx, cs:WPP_GLOBAL_Control
0x18000979f  test    byte ptr [rcx+1Ch], 1
0x1800097a3  jnz     loc_180009976
0x1800097a9  cmp     [rsi+5Ch], r12b
0x1800097ad  jnz     loc_180009915
0x1800097b3  movzx   r14d, byte ptr [rsi+142h]
0x1800097bb  mov     qword ptr [rbp+57h+FileTime.dwLowDateTime], r12
0x1800097bf  mov     qword ptr [rbp+57h+LocalFileTime.dwLowDateTime], r12
0x1800097c3  lea     rcx, [rsi+11Ch]; lpSystemTime
0x1800097ca  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x1800097ce  call    cs:__imp_SystemTimeToFileTime
0x1800097d4  test    eax, eax
0x1800097d6  jz      loc_180009B69
0x1800097dc  test    r14b, r14b
0x1800097df  jnz     loc_180009BD4
0x1800097e5  mov     r14, qword ptr [rbp+57h+FileTime.dwLowDateTime]
0x1800097e9  mov     qword ptr [rbp+57h+LocalFileTime.dwLowDateTime], r14
0x1800097ed  cmp     [rsi+141h], r12b
0x1800097f4  jnz     loc_180009B12
0x1800097fa  cmp     dword ptr [rsi+58h], 4
0x1800097fe  jnz     loc_1800099AF
0x180009804  lea     r15, [rsi+38h]
0x180009808  cmp     [rsi+141h], r12b
0x18000980f  jnz     loc_180009A59
0x180009815  mov     rcx, cs:WPP_GLOBAL_Control
0x18000981c  test    byte ptr [rcx+1Ch], 1
0x180009820  jz      short loc_180009840
0x180009822  cmp     byte ptr [rcx+19h], 4
0x180009826  jb      short loc_180009840
0x180009828  mov     edx, 11h
0x18000982d  mov     r9, r14
0x180009830  lea     r8, WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids
0x180009837  mov     rcx, [rcx+10h]
0x18000983b  call    WPP_SF_i
0x180009840  mov     [rsi+50h], r12
0x180009844  mov     rax, [r15]
0x180009847  cqo
0x180009849  sub     rax, rdx
0x18000984c  sar     rax, 1
0x18000984f  mov     rdx, r14
0x180009852  sub     rdx, rax
0x180009855  mov     [rsi+18h], rdx
0x180009859  lea     r8, [rax+r14]
0x18000985d  mov     [rsi+20h], r8
0x180009861  mov     rcx, cs:WPP_GLOBAL_Control
0x180009868  test    byte ptr [rcx+1Ch], 40h
0x18000986c  jz      short loc_180009895
0x18000986e  cmp     byte ptr [rcx+19h], 4
0x180009872  jb      short loc_180009895
0x180009874  mov     [rsp+0E0h+var_B8], r8
0x180009879  mov     [rsp+0E0h+var_C0], rdx
0x18000987e  mov     r9, [rsi+0F8h]
0x180009885  mov     rcx, [rcx+10h]
0x180009889  call    WPP_SF__guid_ii
0x18000988e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009895  test    cs:Microsoft_Windows_TimeBrokerEnableBits, 1
0x18000989c  jnz     loc_180009C86
0x1800098a2  test    byte ptr [rcx+1Ch], 40h
0x1800098a6  jz      short loc_1800098CD
0x1800098a8  cmp     byte ptr [rcx+19h], 4
0x1800098ac  jb      short loc_1800098CD
0x1800098ae  mov     dword ptr [rsp+0E0h+var_B8], 1
0x1800098b6  mov     eax, [rsi+58h]
0x1800098b9  mov     dword ptr [rsp+0E0h+var_C0], eax
0x1800098bd  mov     r9, [rsi+0F8h]
0x1800098c4  mov     rcx, [rcx+10h]
0x1800098c8  call    WPP_SF__guid_ll
0x1800098cd  test    cs:Microsoft_Windows_TimeBrokerEnableBits, 1
0x1800098d4  jnz     loc_180009CCD
0x1800098da  mov     dword ptr [rsi+58h], 1
0x1800098e1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800098e8  test    byte ptr [rcx+1Ch], 1
0x1800098ec  jz      short loc_18000994E
0x1800098ee  cmp     byte ptr [rcx+19h], 4
0x1800098f2  jb      short loc_18000994E
0x1800098f4  mov     edx, 12h
0x1800098f9  mov     eax, dword ptr [rbp+57h+var_98+4]
0x1800098fc  mov     dword ptr [rsp+0E0h+var_C0], eax
0x180009900  mov     r9d, ebx
0x180009903  lea     r8, WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids
0x18000990a  mov     rcx, [rcx+10h]
0x18000990e  call    WPP_SF_DD
0x180009913  jmp     short loc_18000994E
0x180009915  test    byte ptr [rcx+1Ch], 40h
0x180009919  jz      short loc_18000993D
0x18000991b  cmp     byte ptr [rcx+19h], 4
0x18000991f  jb      short loc_18000993D
0x180009921  mov     dword ptr [rsp+0E0h+var_B8], r12d
0x180009926  mov     eax, [rsi+58h]
0x180009929  mov     dword ptr [rsp+0E0h+var_C0], eax
0x18000992d  mov     r9, [rsi+0F8h]
0x180009934  mov     rcx, [rcx+10h]
0x180009938  call    WPP_SF__guid_ll
0x18000993d  test    cs:Microsoft_Windows_TimeBrokerEnableBits, 1
0x180009944  jnz     loc_180009B4F
0x18000994a  mov     [rsi+58h], r12d
0x18000994e  mov     rcx, [rbp+57h+var_30]
0x180009952  xor     rcx, rsp; StackCookie
0x180009955  call    __security_check_cookie
0x18000995a  lea     r11, [rsp+0E0h+var_20]
0x180009962  mov     rbx, [r11+40h]
0x180009966  mov     rsi, [r11+48h]
0x18000996a  mov     rsp, r11
0x18000996d  pop     r15
0x18000996f  pop     r14
0x180009971  pop     r12
0x180009973  pop     rdi
0x180009974  pop     rbp
0x180009975  retn
0x180009976  cmp     byte ptr [rcx+19h], 4
0x18000997a  jb      loc_1800097A9
0x180009980  mov     rax, rbx
0x180009983  shr     rax, 20h
0x180009987  mov     edx, 10h
0x18000998c  mov     dword ptr [rsp+0E0h+var_C0], eax
0x180009990  mov     r9d, ebx
0x180009993  lea     r8, WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids
0x18000999a  mov     rcx, [rcx+10h]
0x18000999e  call    WPP_SF_DD
0x1800099a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800099aa  jmp     loc_1800097A9
0x1800099af  cmp     [rsi+138h], r12
0x1800099b6  jz      loc_180009804
0x1800099bc  mov     r11, [rsi+40h]
0x1800099c0  test    r11, r11
0x1800099c3  jz      loc_180009AC1
0x1800099c9  lea     r15, [rsi+38h]
0x1800099cd  mov     r9, [r15]
0x1800099d0  mov     rax, r9
0x1800099d3  cqo
0x1800099d5  sub     rax, rdx
0x1800099d8  sar     rax, 1
0x1800099db  mov     r10, rax
0x1800099de  mov     rcx, r14
0x1800099e1  sub     rcx, rax
0x1800099e4  cmp     rcx, rdi
0x1800099e7  jge     loc_180009808
0x1800099ed  mov     r8, [rsi+20h]
0x1800099f1  mov     rcx, r8
0x1800099f4  sub     rcx, r9
0x1800099f7  cmp     [rsi+148h], r12d
0x1800099fe  jnz     loc_180009AE0
0x180009a04  cmp     rdi, rcx
0x180009a07  jl      short loc_180009A0E
0x180009a09  cmp     r8, rdi
0x180009a0c  jge     short loc_180009A11
0x180009a0e  mov     r8, rdi
0x180009a11  cmp     r8, r14
0x180009a14  jl      short loc_180009A35
0x180009a16  mov     eax, [rsi+118h]
0x180009a1c  imul    rcx, rax, 989680h
0x180009a23  sub     r14, r8
0x180009a26  mov     rax, r14
0x180009a29  cqo
0x180009a2b  idiv    rcx
0x180009a2e  lea     r14, [r8+rdx]
0x180009a32  add     r14, rcx
0x180009a35  mov     rax, r14
0x180009a38  sub     rax, r10
0x180009a3b  cmp     rdi, rax
0x180009a3e  jl      loc_180009808
0x180009a44  lea     rax, [r10+r14]
0x180009a48  cmp     rdi, rax
0x180009a4b  jg      loc_180009808
0x180009a51  add     r14, r11
0x180009a54  jmp     loc_180009808
0x180009a59  mov     [rsi+130h], r14
0x180009a60  mov     rax, [r15]
0x180009a63  cqo
0x180009a65  sub     rax, rdx
0x180009a68  sar     rax, 1
0x180009a6b  sub     r14, rax
0x180009a6e  mov     [rsi+20h], r14
0x180009a72  mov     [rsi+18h], r14
0x180009a76  mov     rcx, cs:WPP_GLOBAL_Control
0x180009a7d  test    byte ptr [rcx+1Ch], 40h
0x180009a81  jz      short loc_180009AA8
0x180009a83  cmp     byte ptr [rcx+19h], 4
0x180009a87  jb      short loc_180009AA8
0x180009a89  mov     dword ptr [rsp+0E0h+var_B8], 1
0x180009a91  mov     eax, [rsi+58h]
0x180009a94  mov     dword ptr [rsp+0E0h+var_C0], eax
0x180009a98  mov     r9, [rsi+0F8h]
0x180009a9f  mov     rcx, [rcx+10h]
0x180009aa3  call    WPP_SF__guid_ll
0x180009aa8  test    cs:Microsoft_Windows_TimeBrokerEnableBits, 1
0x180009aaf  jnz     loc_180009C69
0x180009ab5  mov     dword ptr [rsi+58h], 1
0x180009abc  jmp     loc_18000994E
0x180009ac1  cmp     [rsi+148h], r12d
0x180009ac8  jnz     loc_1800099C9
0x180009ace  mov     edx, 3
0x180009ad3  mov     rcx, rsi
0x180009ad6  call    ?SetState@TimeEvent@Broker@@IEAAXW4States@12@@Z; Broker::TimeEvent::SetState(Broker::TimeEvent::States)
0x180009adb  jmp     loc_18000994E
0x180009ae0  cmp     rdi, rcx
0x180009ae3  jg      loc_180009C5D
0x180009ae9  lea     r9, [rbp+57h+var_B0]; union _ULARGE_INTEGER *
0x180009aed  lea     r8, [rbp+57h+LocalFileTime]; union _ULARGE_INTEGER
0x180009af1  mov     rdx, rdi; struct _SYSTEMTIME *
0x180009af4  lea     rcx, [rsi+148h]; this
0x180009afb  call    ?CalculateDelay@Broker@@YAHPEAU_TB_IRREGULAR_SCHEDULE@@T_ULARGE_INTEGER@@PEAT3@PEAK@Z; Broker::CalculateDelay(_TB_IRREGULAR_SCHEDULE *,_ULARGE_INTEGER,_ULARGE_INTEGER *,ulong *)
0x180009b00  mov     eax, dword ptr [rbp+57h+var_B0]
0x180009b03  imul    r14, rax, 989680h
0x180009b0a  add     r14, rdi
0x180009b0d  jmp     loc_180009808
0x180009b12  cmp     [rsi+140h], r12b
0x180009b19  jz      loc_1800097FA
0x180009b1f  mov     rax, [rsi+38h]
0x180009b23  cqo
0x180009b25  sub     rax, rdx
0x180009b28  sar     rax, 1
0x180009b2b  mov     r8, [rsi+130h]
0x180009b32  add     r8, rax
0x180009b35  mov     [rsi+20h], r8
0x180009b39  mov     [rsi+18h], r8
0x180009b3d  mov     edx, 1
0x180009b42  mov     rcx, rsi
0x180009b45  call    ?SetState@TimeEvent@Broker@@IEAAXW4States@12@@Z; Broker::TimeEvent::SetState(Broker::TimeEvent::States)
0x180009b4a  jmp     loc_18000994E
0x180009b4f  mov     dword ptr [rsp+0E0h+var_C0], r12d
0x180009b54  mov     r9d, [rsi+58h]
0x180009b58  mov     r8, [rsi+0F8h]
0x180009b5f  call    McTemplateU0jqq_EventWriteTransfer
0x180009b64  jmp     loc_18000994A
0x180009b69  lea     rcx, [rbp+57h+var_90]; this
0x180009b6d  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x180009b72  nop
0x180009b73  mov     rcx, cs:WPP_GLOBAL_Control
0x180009b7a  test    byte ptr [rcx+1Ch], 40h
0x180009b7e  jz      short loc_180009B9F
0x180009b80  cmp     byte ptr [rcx+19h], 2
0x180009b84  jb      short loc_180009B9F
0x180009b86  mov     edx, 17h
0x180009b8b  mov     r9d, [rbp+57h+var_70]
0x180009b8f  lea     r8, WPP_7b3fa50611f3300368cf2233e3ad1277_Traceguids
0x180009b96  mov     rcx, [rcx+10h]
0x180009b9a  call    WPP_SF_d
0x180009b9f  lea     rdx, [rbp+57h+var_90]; struct std::exception *
0x180009ba3  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180009ba7  call    ??0exception@std@@QEAA@AEBV01@@Z; std::exception::exception(std::exception const &)
0x180009bac  mov     eax, [rbp+57h+var_78]
0x180009baf  mov     [rbp+57h+var_50], eax
0x180009bb2  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180009bb9  mov     [rbp+57h+pExceptionObject], rax
0x180009bbd  mov     eax, [rbp+57h+var_70]
0x180009bc0  mov     [rbp+57h+var_48], eax
0x180009bc3  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180009bca  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180009bce  call    _CxxThrowException_0
0x180009bd4  mov     rax, qword ptr [rbp+57h+FileTime.dwLowDateTime]
0x180009bd8  mov     qword ptr [rbp+57h+LocalFileTime.dwLowDateTime], rax
0x180009bdc  lea     rdx, [rbp+57h+FileTime]; lpFileTime
0x180009be0  lea     rcx, [rbp+57h+LocalFileTime]; lpLocalFileTime
0x180009be4  call    cs:__imp_LocalFileTimeToFileTime
0x180009bea  test    eax, eax
0x180009bec  jnz     loc_1800097E5
0x180009bf2  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180009bf6  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x180009bfb  nop
0x180009bfc  mov     rcx, cs:WPP_GLOBAL_Control
0x180009c03  test    byte ptr [rcx+1Ch], 40h
0x180009c07  jz      short loc_180009C28
0x180009c09  cmp     byte ptr [rcx+19h], 2
0x180009c0d  jb      short loc_180009C28
0x180009c0f  mov     edx, 18h
0x180009c14  mov     r9d, [rbp+57h+var_48]
0x180009c18  lea     r8, WPP_7b3fa50611f3300368cf2233e3ad1277_Traceguids
0x180009c1f  mov     rcx, [rcx+10h]
0x180009c23  call    WPP_SF_d
0x180009c28  lea     rdx, [rbp+57h+pExceptionObject]; struct std::exception *
0x180009c2c  lea     rcx, [rbp+57h+var_90]; this
0x180009c30  call    ??0exception@std@@QEAA@AEBV01@@Z; std::exception::exception(std::exception const &)
0x180009c35  mov     eax, [rbp+57h+var_50]
0x180009c38  mov     [rbp+57h+var_78], eax
0x180009c3b  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180009c42  mov     [rbp+57h+var_90], rax
0x180009c46  mov     eax, [rbp+57h+var_48]
0x180009c49  mov     [rbp+57h+var_70], eax
0x180009c4c  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180009c53  lea     rcx, [rbp+57h+var_90]; pExceptionObject
  ... truncated ...
```
