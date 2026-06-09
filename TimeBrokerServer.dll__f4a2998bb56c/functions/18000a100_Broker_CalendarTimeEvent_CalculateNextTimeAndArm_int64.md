# Broker::CalendarTimeEvent::CalculateNextTimeAndArm(__int64)

- ea: `0x18000a100`
- end: `0x18000a25d`
- name: `?CalculateNextTimeAndArm@CalendarTimeEvent@Broker@@MEAAX_J@Z`
- size: `349`
- prototype: `void __fastcall(Broker::CalendarTimeEvent *this, __int64)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180003800`
- `0x180009cf0`
- `0x180009ea0`
- `0x18000a100`
- `0x18000a674`
- `0x180011240`
- `0x180011594`
- `0x18001181c`
- `0x180013978`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000a129`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000a129`

## pseudocode

```c
void __fastcall Broker::CalendarTimeEvent::CalculateNextTimeAndArm(Broker::CalendarTimeEvent *this, __int64 a2)
{
  Broker::CalendarTimeEvent *v3; // rbx
  Broker::TimeEvent *v4; // rcx
  __int64 v5; // rdx
  struct _GUID *PeriodicDueTime; // rdx
  __int64 v7; // rax
  _BYTE v8[24]; // [rsp+20h] [rbp-58h] BYREF
  int v9; // [rsp+38h] [rbp-40h]
  unsigned int v10; // [rsp+40h] [rbp-38h]
  _QWORD pExceptionObject[3]; // [rsp+48h] [rbp-30h] BYREF
  int v12; // [rsp+60h] [rbp-18h]
  unsigned int v13; // [rsp+68h] [rbp-10h]
  struct _GUID *v16; // [rsp+90h] [rbp+18h] BYREF

  v3 = this;
  v16 = 0;
  if ( !SystemTimeToFileTime((const SYSTEMTIME *)((char *)this + 280), (LPFILETIME)&v16) )
  {
    Broker::Win32Error::Win32Error((Broker::Win32Error *)v8);
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, &WPP_7b3fa50611f3300368cf2233e3ad1277_Traceguids, v10);
    std::exception::exception((std::exception *)pExceptionObject, (const struct std::exception *)v8);
    v12 = v9;
    pExceptionObject[0] = &Broker::Win32Error::`vftable';
    v13 = v10;
    throw (Broker::Win32Error *)pExceptionObject;
  }
  if ( *((_BYTE *)v3 + 92) )
  {
    v5 = 0;
LABEL_8:
    Broker::TimeEvent::SetState(v3, v5);
    return;
  }
  PeriodicDueTime = v16;
  if ( *((_DWORD *)v3 + 22) == 2 )
  {
    v7 = *((_QWORD *)v3 + 4);
    if ( v7 && a2 < v7 )
      a2 = *((_QWORD *)v3 + 4);
  }
  else if ( *((_DWORD *)v3 + 22) == 4 && (!*((_QWORD *)v3 + 3) || !*((_DWORD *)v3 + 74)) )
  {
    a2 -= *((_QWORD *)v3 + 6);
  }
  if ( (__int64)v16 < a2 )
  {
    if ( !*((_DWORD *)v3 + 74) )
    {
      if ( *((_DWORD *)v3 + 22) != 2 )
      {
        try
        {
          Broker::BILayer::DeleteEvent(*((Broker::BILayer **)v3 + 31), v16);
        }
        catch ( ... )
        {
          v3 = this;
        }
      }
      v5 = 3;
      goto LABEL_8;
    }
    PeriodicDueTime = (struct _GUID *)Broker::TimeEvent::NextPeriodicDueTime(
                                        v4,
                                        (__int64)v16,
                                        a2,
                                        864000000000LL * *((unsigned int *)v3 + 74));
  }
  Broker::TimeEvent::ArmTimeEvent((__int64)v3, (__int64)PeriodicDueTime);
}

```

## disassembly

```asm
0x18000a100  mov     rax, rsp
0x18000a103  mov     [rax+10h], rbx
0x18000a107  mov     [rax+8], rcx
0x18000a10b  push    rdi
0x18000a10c  sub     rsp, 70h
0x18000a110  mov     rdi, rdx
0x18000a113  mov     rbx, rcx
0x18000a116  mov     qword ptr [rax+18h], 0
0x18000a11e  add     rcx, 118h; lpSystemTime
0x18000a125  lea     rdx, [rax+18h]; lpFileTime
0x18000a129  call    cs:__imp_SystemTimeToFileTime
0x18000a12f  test    eax, eax
0x18000a131  jnz     short loc_18000A1A8
0x18000a133  lea     rcx, [rsp+78h+var_58]; this
0x18000a138  call    ??0Win32Error@Broker@@QEAA@XZ; Broker::Win32Error::Win32Error(void)
0x18000a13d  nop
0x18000a13e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a145  test    byte ptr [rcx+1Ch], 40h
0x18000a149  jz      short loc_18000A16B
0x18000a14b  cmp     byte ptr [rcx+19h], 2
0x18000a14f  jb      short loc_18000A16B
0x18000a151  mov     edx, 17h
0x18000a156  mov     r9d, [rsp+78h+var_38]
0x18000a15b  lea     r8, WPP_7b3fa50611f3300368cf2233e3ad1277_Traceguids
0x18000a162  mov     rcx, [rcx+10h]
0x18000a166  call    WPP_SF_d
0x18000a16b  lea     rdx, [rsp+78h+var_58]; struct std::exception *
0x18000a170  lea     rcx, [rsp+78h+pExceptionObject]; this
0x18000a175  call    ??0exception@std@@QEAA@AEBV01@@Z; std::exception::exception(std::exception const &)
0x18000a17a  mov     eax, [rsp+78h+var_40]
0x18000a17e  mov     [rsp+78h+var_18], eax
0x18000a182  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18000a189  mov     [rsp+78h+pExceptionObject], rax
0x18000a18e  mov     eax, [rsp+78h+var_38]
0x18000a192  mov     [rsp+78h+var_10], eax
0x18000a196  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000a19d  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18000a1a2  call    _CxxThrowException_0
0x18000a1a8  cmp     byte ptr [rbx+5Ch], 0
0x18000a1ac  jz      short loc_18000A1BD
0x18000a1ae  xor     edx, edx
0x18000a1b0  mov     rcx, rbx
0x18000a1b3  call    ?SetState@TimeEvent@Broker@@IEAAXW4States@12@@Z; Broker::TimeEvent::SetState(Broker::TimeEvent::States)
0x18000a1b8  jmp     loc_18000A24F
0x18000a1bd  mov     rdx, [rsp+78h+arg_10]; __int64
0x18000a1c5  cmp     dword ptr [rbx+58h], 2
0x18000a1c9  jnz     short loc_18000A1DE
0x18000a1cb  mov     rax, [rbx+20h]
0x18000a1cf  test    rax, rax
0x18000a1d2  jz      short loc_18000A1F8
0x18000a1d4  cmp     rdi, rax
0x18000a1d7  jge     short loc_18000A1F8
0x18000a1d9  mov     rdi, rax
0x18000a1dc  jmp     short loc_18000A1F8
0x18000a1de  cmp     dword ptr [rbx+58h], 4
0x18000a1e2  jnz     short loc_18000A1F8
0x18000a1e4  cmp     qword ptr [rbx+18h], 0
0x18000a1e9  jz      short loc_18000A1F4
0x18000a1eb  cmp     dword ptr [rbx+128h], 0
0x18000a1f2  jnz     short loc_18000A1F8
0x18000a1f4  sub     rdi, [rbx+30h]
0x18000a1f8  cmp     rdx, rdi
0x18000a1fb  jge     short loc_18000A247
0x18000a1fd  mov     eax, [rbx+128h]
0x18000a203  test    eax, eax
0x18000a205  jnz     short loc_18000A22B
0x18000a207  cmp     dword ptr [rbx+58h], 2
0x18000a20b  jz      short loc_18000A224
0x18000a20d  mov     rcx, [rbx+0F8h]; this
0x18000a214  call    ?DeleteEvent@BILayer@Broker@@YAXAEBU_GUID@@@Z; Broker::BILayer::DeleteEvent(_GUID const &)
0x18000a219  nop
0x18000a21a  jmp     short loc_18000A224
0x18000a21c  mov     rbx, [rsp+78h+arg_0]
0x18000a224  mov     edx, 3
0x18000a229  jmp     short loc_18000A1B0
0x18000a22b  mov     r9, rax
0x18000a22e  mov     rax, 0C92A69C000h
0x18000a238  imul    r9, rax; __int64
0x18000a23c  mov     r8, rdi; __int64
0x18000a23f  call    ?NextPeriodicDueTime@TimeEvent@Broker@@IEAA_J_J00@Z; Broker::TimeEvent::NextPeriodicDueTime(__int64,__int64,__int64)
0x18000a244  mov     rdx, rax
0x18000a247  mov     rcx, rbx
0x18000a24a  call    ?ArmTimeEvent@TimeEvent@Broker@@IEAAX_JW4States@12@@Z; Broker::TimeEvent::ArmTimeEvent(__int64,Broker::TimeEvent::States)
0x18000a24f  mov     rbx, [rsp+78h+arg_8]
0x18000a257  add     rsp, 70h
0x18000a25b  pop     rdi
0x18000a25c  retn
```
