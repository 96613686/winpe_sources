# Broker::AlarmTimeEvent::CalculateNextTimeAndArm(__int64)

- ea: `0x180008c70`
- end: `0x180008fbb`
- name: `?CalculateNextTimeAndArm@AlarmTimeEvent@Broker@@MEAAX_J@Z`
- size: `843`
- prototype: `void __fastcall(Broker::AlarmTimeEvent *this, __int64, __int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x180003800`
- `0x180008c70`
- `0x180009cf0`
- `0x180009f10`
- `0x18000a674`
- `0x180011240`
- `0x1800113dc`
- `0x180011594`
- `0x18001181c`
- `0x180013978`
- `0x180014168`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180008cb8`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180008cb8`
- `api-ms-win-core-file-l1-1-0!LocalFileTimeToFileTime` at `0x180008ee6`
- `api-ms-win-core-file-l1-1-0!LocalFileTimeToFileTime` at `0x180008ee6`

## pseudocode

```c
void __fastcall Broker::AlarmTimeEvent::CalculateNextTimeAndArm(Broker::AlarmTimeEvent *this, __int64 a2, __int64 a3)
{
  __int64 v3; // rdi
  Broker::AlarmTimeEvent *v4; // rbx
  char v5; // si
  __int64 PeriodicDueTime; // rcx
  struct _SYSTEMTIME *v7; // rdx
  _DWORD *QuadPart; // rsi
  int v9; // eax
  int v10; // ecx
  __int64 v11; // r8
  __int64 v12; // r8
  int v13; // ecx
  __int64 v14; // [rsp+0h] [rbp-C8h] BYREF
  FILETIME LocalFileTime; // [rsp+30h] [rbp-98h] BYREF
  _BYTE v16[24]; // [rsp+38h] [rbp-90h] BYREF
  int v17; // [rsp+50h] [rbp-78h]
  unsigned int v18; // [rsp+58h] [rbp-70h]
  _QWORD pExceptionObject[3]; // [rsp+60h] [rbp-68h] BYREF
  int v20; // [rsp+78h] [rbp-50h]
  unsigned int v21; // [rsp+80h] [rbp-48h]
  _QWORD v22[3]; // [rsp+88h] [rbp-40h] BYREF
  int v23; // [rsp+A0h] [rbp-28h]
  unsigned int v24; // [rsp+A8h] [rbp-20h]
  _ULARGE_INTEGER v26; // [rsp+E0h] [rbp+18h] BYREF
  struct _FILETIME FileTime; // [rsp+E8h] [rbp+20h] BYREF

  v3 = a2;
  v4 = this;
  v26.LowPart = 0;
  if ( *((_BYTE *)this + 92) )
  {
    v10 = (int)WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF__guid_ll(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, *((_QWORD *)v4 + 31), *((_DWORD *)v4 + 22), 0);
    if ( (Microsoft_Windows_TimeBrokerEnableBits & 1) != 0 )
      McTemplateU0jqq_EventWriteTransfer(v10, a2, *((_QWORD *)v4 + 31), *((_DWORD *)v4 + 22), 0);
    *((_DWORD *)v4 + 22) = 0;
  }
  else
  {
    v5 = *((_BYTE *)this + 300);
    FileTime = 0;
    LocalFileTime = 0;
    if ( !SystemTimeToFileTime((const SYSTEMTIME *)((char *)this + 280), &FileTime) )
    {
      Broker::Win32Error::Win32Error((Broker::Win32Error *)v16);
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_7b3fa50611f3300368cf2233e3ad1277_Traceguids, v18);
      std::exception::exception((std::exception *)pExceptionObject, (const struct std::exception *)v16);
      v20 = v17;
      pExceptionObject[0] = &Broker::Win32Error::`vftable';
      v21 = v18;
      throw (Broker::Win32Error *)pExceptionObject;
    }
    if ( v5 )
    {
      LocalFileTime = FileTime;
      if ( !LocalFileTimeToFileTime(&LocalFileTime, &FileTime) )
      {
        Broker::Win32Error::Win32Error((Broker::Win32Error *)v16);
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_7b3fa50611f3300368cf2233e3ad1277_Traceguids, v18);
        std::exception::exception((std::exception *)v22, (const struct std::exception *)v16);
        v23 = v17;
        v22[0] = &Broker::Win32Error::`vftable';
        v24 = v18;
        throw (Broker::Win32Error *)v22;
      }
    }
    PeriodicDueTime = (__int64)FileTime;
    v7 = (struct _SYSTEMTIME *)v3;
    QuadPart = (_DWORD *)((char *)v4 + 88);
    v9 = *((_DWORD *)v4 + 22);
    if ( v9 == 2 )
    {
      v11 = *((_QWORD *)v4 + 4);
      if ( v11 && v3 < v11 )
        v3 = *((_QWORD *)v4 + 4);
    }
    else if ( v9 == 4 && (!*((_QWORD *)v4 + 3) || !*((_DWORD *)v4 + 74)) )
    {
      v3 -= *((_QWORD *)v4 + 6);
    }
    if ( *(_QWORD *)&FileTime >= v3 )
      goto LABEL_10;
    v12 = *((unsigned int *)v4 + 74);
    if ( (_DWORD)v12 )
    {
      if ( *((_DWORD *)v4 + 76) )
      {
        Broker::CalculateDelay((Broker::AlarmTimeEvent *)((char *)v4 + 304), v7, (union _ULARGE_INTEGER)&FileTime, &v26);
        PeriodicDueTime = v3 + 10000000LL * v26.LowPart;
      }
      else
      {
        PeriodicDueTime = Broker::TimeEvent::NextPeriodicDueTime(
                            *(Broker::TimeEvent **)&FileTime,
                            *(_QWORD *)&FileTime,
                            v3,
                            10000000 * v12);
      }
LABEL_10:
      Broker::TimeEvent::ArmTimeEvent((__int64)v4, PeriodicDueTime);
      return;
    }
    v26.QuadPart = (ULONGLONG)v4 + 88;
    if ( v9 != 2 )
    {
      try
      {
        Broker::BILayer::DeleteEvent(*((Broker::BILayer **)v4 + 31), (const struct _GUID *)v7);
      }
      catch ( ... )
      {
        v7 = (struct _SYSTEMTIME *)&v14;
        v4 = this;
        QuadPart = (_DWORD *)v26.QuadPart;
      }
    }
    v13 = (int)WPP_GLOBAL_Control;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF__guid_ll(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, v12, *((_QWORD *)v4 + 31), *((_DWORD *)v4 + 22), 3);
    if ( (Microsoft_Windows_TimeBrokerEnableBits & 1) != 0 )
      McTemplateU0jqq_EventWriteTransfer(v13, (_DWORD)v7, *((_QWORD *)v4 + 31), *QuadPart, 3);
    *QuadPart = 3;
  }
}

```

## disassembly

```asm
0x180008c70  mov     rax, rsp
0x180008c73  mov     [rax+10h], rbx
0x180008c77  mov     [rax+8], rcx
0x180008c7b  push    rsi
0x180008c7c  push    rdi
0x180008c7d  push    r14
0x180008c7f  sub     rsp, 0B0h
0x180008c86  mov     rdi, rdx
0x180008c89  mov     rbx, rcx
0x180008c8c  xor     r14d, r14d
0x180008c8f  mov     [rax+18h], r14d
0x180008c93  cmp     [rcx+5Ch], r14b
0x180008c97  jnz     loc_180008D29
0x180008c9d  movzx   esi, byte ptr [rcx+12Ch]
0x180008ca4  mov     [rax+20h], r14
0x180008ca8  mov     qword ptr [rsp+0C8h+LocalFileTime.dwLowDateTime], r14
0x180008cad  add     rcx, 118h; lpSystemTime
0x180008cb4  lea     rdx, [rax+20h]; lpFileTime
0x180008cb8  call    cs:__imp_SystemTimeToFileTime
0x180008cbe  test    eax, eax
0x180008cc0  jz      loc_180008E54
0x180008cc6  test    sil, sil
0x180008cc9  jnz     loc_180008ECC
0x180008ccf  mov     rcx, qword ptr [rsp+0C8h+FileTime.dwLowDateTime]; this
0x180008cd7  mov     rdx, rdi; struct _GUID *
0x180008cda  mov     qword ptr [rsp+0C8h+FileTime.dwLowDateTime], rcx
0x180008ce2  lea     rsi, [rbx+58h]
0x180008ce6  mov     eax, [rsi]
0x180008ce8  cmp     eax, 2
0x180008ceb  jz      short loc_180008D6B
0x180008ced  cmp     eax, 4
0x180008cf0  jnz     short loc_180008D05
0x180008cf2  cmp     [rbx+18h], r14
0x180008cf6  jz      short loc_180008D01
0x180008cf8  cmp     [rbx+128h], r14d
0x180008cff  jnz     short loc_180008D05
0x180008d01  sub     rdi, [rbx+30h]
0x180008d05  cmp     rcx, rdi
0x180008d08  jl      short loc_180008D7E
0x180008d0a  mov     rdx, rcx
0x180008d0d  mov     rcx, rbx
0x180008d10  call    ?ArmTimeEvent@TimeEvent@Broker@@IEAAX_JW4States@12@@Z; Broker::TimeEvent::ArmTimeEvent(__int64,Broker::TimeEvent::States)
0x180008d15  mov     rbx, [rsp+0C8h+arg_8]
0x180008d1d  add     rsp, 0B0h
0x180008d24  pop     r14
0x180008d26  pop     rdi
0x180008d27  pop     rsi
0x180008d28  retn
0x180008d29  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d30  test    byte ptr [rcx+1Ch], 40h
0x180008d34  jz      short loc_180008D58
0x180008d36  cmp     byte ptr [rcx+19h], 4
0x180008d3a  jb      short loc_180008D58
0x180008d3c  mov     [rsp+0C8h+var_A0], r14d
0x180008d41  mov     eax, [rbx+58h]
0x180008d44  mov     [rsp+0C8h+var_A8], eax
0x180008d48  mov     r9, [rbx+0F8h]
0x180008d4f  mov     rcx, [rcx+10h]
0x180008d53  call    WPP_SF__guid_ll
0x180008d58  test    cs:Microsoft_Windows_TimeBrokerEnableBits, 1
0x180008d5f  jnz     loc_180008E3A
0x180008d65  mov     [rbx+58h], r14d
0x180008d69  jmp     short loc_180008D15
0x180008d6b  mov     r8, [rbx+20h]
0x180008d6f  test    r8, r8
0x180008d72  jz      short loc_180008D05
0x180008d74  cmp     rdi, r8
0x180008d77  jge     short loc_180008D05
0x180008d79  mov     rdi, r8
0x180008d7c  jmp     short loc_180008D05
0x180008d7e  mov     r8d, [rbx+128h]
0x180008d85  test    r8d, r8d
0x180008d88  jnz     short loc_180008DE5
0x180008d8a  mov     qword ptr [rsp+0C8h+arg_10], rsi
0x180008d92  cmp     eax, 2
0x180008d95  jnz     loc_180008F78
0x180008d9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008da2  test    byte ptr [rcx+1Ch], 40h
0x180008da6  jz      short loc_180008DCD
0x180008da8  cmp     byte ptr [rcx+19h], 4
0x180008dac  jb      short loc_180008DCD
0x180008dae  mov     [rsp+0C8h+var_A0], 3
0x180008db6  mov     eax, [rbx+58h]
0x180008db9  mov     [rsp+0C8h+var_A8], eax
0x180008dbd  mov     r9, [rbx+0F8h]
0x180008dc4  mov     rcx, [rcx+10h]
0x180008dc8  call    WPP_SF__guid_ll
0x180008dcd  test    cs:Microsoft_Windows_TimeBrokerEnableBits, 1
0x180008dd4  jnz     loc_180008F9F
0x180008dda  mov     dword ptr [rsi], 3
0x180008de0  jmp     loc_180008D15
0x180008de5  cmp     [rbx+130h], r14d
0x180008dec  jnz     short loc_180008E08
0x180008dee  imul    r9, r8, 989680h; __int64
0x180008df5  mov     r8, rdi; __int64
0x180008df8  mov     rdx, rcx; __int64
0x180008dfb  call    ?NextPeriodicDueTime@TimeEvent@Broker@@IEAA_J_J00@Z; Broker::TimeEvent::NextPeriodicDueTime(__int64,__int64,__int64)
0x180008e00  mov     rcx, rax
0x180008e03  jmp     loc_180008D0A
0x180008e08  lea     r9, [rsp+0C8h+arg_10]; union _ULARGE_INTEGER *
0x180008e10  lea     r8, [rsp+0C8h+FileTime]; union _ULARGE_INTEGER
0x180008e18  lea     rcx, [rbx+130h]; this
0x180008e1f  call    ?CalculateDelay@Broker@@YAHPEAU_TB_IRREGULAR_SCHEDULE@@T_ULARGE_INTEGER@@PEAT3@PEAK@Z; Broker::CalculateDelay(_TB_IRREGULAR_SCHEDULE *,_ULARGE_INTEGER,_ULARGE_INTEGER *,ulong *)
0x180008e24  mov     eax, dword ptr [rsp+0C8h+arg_10]
0x180008e2b  imul    rcx, rax, 989680h
0x180008e32  add     rcx, rdi
0x180008e35  jmp     loc_180008D0A
0x180008e3a  mov     [rsp+0C8h+var_A8], r14d
0x180008e3f  mov     r9d, [rbx+58h]
0x180008e43  mov     r8, [rbx+0F8h]
0x180008e4a  call    McTemplateU0jqq_EventWriteTransfer
0x180008e4f  jmp     loc_180008D65
0x180008e54  lea     rcx, [rsp+0C8h+var_90]; this
0x180008e59  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x180008e5e  nop
0x180008e5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e66  test    byte ptr [rcx+1Ch], 40h
0x180008e6a  jz      short loc_180008E8C
0x180008e6c  cmp     byte ptr [rcx+19h], 2
0x180008e70  jb      short loc_180008E8C
0x180008e72  mov     edx, 17h
0x180008e77  mov     r9d, [rsp+0C8h+var_70]
0x180008e7c  lea     r8, WPP_7b3fa50611f3300368cf2233e3ad1277_Traceguids
0x180008e83  mov     rcx, [rcx+10h]
0x180008e87  call    WPP_SF_d
0x180008e8c  lea     rdx, [rsp+0C8h+var_90]; struct std::exception *
0x180008e91  lea     rcx, [rsp+0C8h+pExceptionObject]; this
0x180008e96  call    ??0exception@std@@QEAA@AEBV01@@Z; std::exception::exception(std::exception const &)
0x180008e9b  mov     eax, [rsp+0C8h+var_78]
0x180008e9f  mov     [rsp+0C8h+var_50], eax
0x180008ea3  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180008eaa  mov     [rsp+0C8h+pExceptionObject], rax
0x180008eaf  mov     eax, [rsp+0C8h+var_70]
0x180008eb3  mov     [rsp+0C8h+var_48], eax
0x180008eba  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180008ec1  lea     rcx, [rsp+0C8h+pExceptionObject]; pExceptionObject
0x180008ec6  call    _CxxThrowException_0
0x180008ecc  mov     rax, qword ptr [rsp+0C8h+FileTime.dwLowDateTime]
0x180008ed4  mov     qword ptr [rsp+0C8h+LocalFileTime.dwLowDateTime], rax
0x180008ed9  lea     rdx, [rsp+0C8h+FileTime]; lpFileTime
0x180008ee1  lea     rcx, [rsp+0C8h+LocalFileTime]; lpLocalFileTime
0x180008ee6  call    cs:__imp_LocalFileTimeToFileTime
0x180008eec  test    eax, eax
0x180008eee  jnz     loc_180008CCF
0x180008ef4  lea     rcx, [rsp+0C8h+var_90]; this
0x180008ef9  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x180008efe  nop
0x180008eff  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f06  test    byte ptr [rcx+1Ch], 40h
0x180008f0a  jz      short loc_180008F2C
0x180008f0c  cmp     byte ptr [rcx+19h], 2
0x180008f10  jb      short loc_180008F2C
0x180008f12  mov     edx, 18h
0x180008f17  mov     r9d, [rsp+0C8h+var_70]
0x180008f1c  lea     r8, WPP_7b3fa50611f3300368cf2233e3ad1277_Traceguids
0x180008f23  mov     rcx, [rcx+10h]
0x180008f27  call    WPP_SF_d
0x180008f2c  lea     rdx, [rsp+0C8h+var_90]; struct std::exception *
0x180008f31  lea     rcx, [rsp+0C8h+var_40]; this
0x180008f39  call    ??0exception@std@@QEAA@AEBV01@@Z; std::exception::exception(std::exception const &)
0x180008f3e  mov     eax, [rsp+0C8h+var_78]
0x180008f42  mov     [rsp+0C8h+var_28], eax
0x180008f49  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x180008f50  mov     [rsp+0C8h+var_40], rax
0x180008f58  mov     eax, [rsp+0C8h+var_70]
0x180008f5c  mov     [rsp+0C8h+var_20], eax
0x180008f63  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x180008f6a  lea     rcx, [rsp+0C8h+var_40]; pExceptionObject
0x180008f72  call    _CxxThrowException_0
0x180008f78  mov     rcx, [rbx+0F8h]; this
0x180008f7f  call    ?DeleteEvent@BILayer@Broker@@YAXAEBU_GUID@@@Z; Broker::BILayer::DeleteEvent(_GUID const &)
0x180008f84  nop
0x180008f85  jmp     loc_180008D9B
0x180008f8a  mov     rbx, [rsp+0C8h+arg_0]
0x180008f92  mov     rsi, qword ptr [rsp+0C8h+arg_10]
0x180008f9a  jmp     loc_180008D9B
0x180008f9f  mov     [rsp+0C8h+var_A8], 3
0x180008fa7  mov     r9d, [rsi]
0x180008faa  mov     r8, [rbx+0F8h]
0x180008fb1  call    McTemplateU0jqq_EventWriteTransfer
0x180008fb6  jmp     loc_180008DDA
```
