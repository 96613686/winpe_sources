# HearingAidProfileClientImpl::Create(_GUID,Microsoft::Bluetooth::Profiles::Hap::Interface::IHearingAidContainerService * *)

- ea: `0x1800562b0`
- end: `0x180056535`
- name: `?Create@HearingAidProfileClientImpl@@UEAAXU_GUID@@PEAPEAUIHearingAidContainerService@Interface@Hap@Profiles@Bluetooth@Microsoft@@@Z`
- size: `645`
- prototype: `void __fastcall(HearingAidProfileClientImpl *__hidden this, struct _GUID *__struct_ptr, struct Microsoft::Bluetooth::Profiles::Hap::Interface::IHearingAidContainerService **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000e0c0`
- `0x180012554`
- `0x1800562b0`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180056372`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180056372`

## string_xrefs

- `0x180056523`: `onecore\drivers\bluetooth\profiles\avrcp\avctp\service\lib\hearingaidprofileclient.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall HearingAidProfileClientImpl::Create(
        HMODULE *this,
        struct _GUID *a2,
        struct Microsoft::Bluetooth::Profiles::Hap::Interface::IHearingAidContainerService **a3)
{
  struct Microsoft::Bluetooth::Profiles::Hap::Interface::IHearingAidContainerService **v3; // rbx
  struct _GUID *v4; // rsi
  struct Microsoft::Bluetooth::Profiles::Hap::Interface::IHearingAidContainerService *v6; // rcx
  FARPROC ProcAddress; // rax
  int v8; // edx
  int v9; // r8d
  int v10; // eax
  int v11; // edx
  int v12; // r8d
  int v13; // [rsp+20h] [rbp-48h]
  struct _GUID v14; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]
  struct Microsoft::Bluetooth::Profiles::Hap::Interface::IHearingAidContainerService *v16; // [rsp+B0h] [rbp+48h] BYREF

  v3 = a3;
  v4 = a2;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || (LOBYTE(a2) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
  {
    LOBYTE(a2) = 0;
  }
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    || (LOBYTE(a3) = 1, !*((_WORD *)WPP_GLOBAL_Control + 24)) )
  {
    LOBYTE(a3) = 0;
  }
  if ( (_BYTE)a2 || (_BYTE)a3 )
    WPP_RECORDER_AND_TRACE_SF_q(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (int)a2,
      (int)a3,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      5,
      1,
      15,
      &WPP_6fa7f4f46ed53a8c08fe2b7537b301f3_Traceguids,
      (char)this);
  v6 = 0;
  v16 = 0;
  *v3 = 0;
  if ( this[1] )
  {
    ProcAddress = GetProcAddress(this[1], (LPCSTR)0xC8);
    if ( ProcAddress )
    {
      v14 = *v4;
      v10 = ((__int64 (__fastcall *)(struct _GUID *, struct Microsoft::Bluetooth::Profiles::Hap::Interface::IHearingAidContainerService **))ProcAddress)(
              &v14,
              &v16);
      if ( v10 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x43,
          (unsigned int)"onecore\\drivers\\bluetooth\\profiles\\avrcp\\avctp\\service\\lib\\hearingaidprofileclient.cpp",
          (const char *)(unsigned int)v10,
          v13);
      v6 = v16;
      if ( v16 )
      {
        (*(void (__fastcall **)(struct Microsoft::Bluetooth::Profiles::Hap::Interface::IHearingAidContainerService *))(*(_QWORD *)v16 + 8LL))(v16);
        v6 = v16;
      }
      *v3 = v6;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || (LOBYTE(v11) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u) )
      {
        LOBYTE(v11) = 0;
      }
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
        || (LOBYTE(v12) = 1, !*((_WORD *)WPP_GLOBAL_Control + 24)) )
      {
        LOBYTE(v12) = 0;
      }
      if ( (_BYTE)v11 || (_BYTE)v12 )
      {
        WPP_RECORDER_AND_TRACE_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v11,
          v12,
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          5,
          1,
          18,
          &WPP_6fa7f4f46ed53a8c08fe2b7537b301f3_Traceguids,
          (char)this);
        v6 = v16;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || (LOBYTE(v8) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u) )
      {
        LOBYTE(v8) = 0;
      }
      if ( (_BYTE)v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v9) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v8,
          v9,
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          3,
          1,
          16,
          &WPP_6fa7f4f46ed53a8c08fe2b7537b301f3_Traceguids,
          (char)this);
      }
      v6 = v16;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || (LOBYTE(a2) = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u) )
    {
      LOBYTE(a2) = 0;
    }
    if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_q(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (int)a2,
        (int)a3,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        2,
        1,
        17,
        &WPP_6fa7f4f46ed53a8c08fe2b7537b301f3_Traceguids,
        (char)this);
      v6 = v16;
    }
  }
  if ( v6 )
  {
    v16 = 0;
    (*(void (__fastcall **)(struct Microsoft::Bluetooth::Profiles::Hap::Interface::IHearingAidContainerService *))(*(_QWORD *)v6 + 16LL))(v6);
  }
}

```

## disassembly

```asm
0x1800562b0  push    rbp
0x1800562b2  push    rbx
0x1800562b3  push    rsi
0x1800562b4  push    rdi
0x1800562b5  push    r12
0x1800562b7  push    r13
0x1800562b9  push    r14
0x1800562bb  push    r15
0x1800562bd  mov     rbp, rsp
0x1800562c0  sub     rsp, 68h
0x1800562c4  mov     rbx, r8
0x1800562c7  mov     rsi, rdx
0x1800562ca  mov     rdi, rcx
0x1800562cd  lea     r12, WPP_GLOBAL_Control
0x1800562d4  xor     r14d, r14d
0x1800562d7  lea     r15d, [r14+1]
0x1800562db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800562e2  cmp     rcx, r12
0x1800562e5  jz      short loc_1800562F6
0x1800562e7  test    [rcx+1Ch], r15b
0x1800562eb  jz      short loc_1800562F6
0x1800562ed  cmp     byte ptr [rcx+19h], 5
0x1800562f1  mov     dl, r15b
0x1800562f4  jnb     short loc_1800562F9
0x1800562f6  mov     dl, r14b; int
0x1800562f9  lea     r13, WPP_RECORDER_INITIALIZED
0x180056300  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180056307  jz      short loc_180056313
0x180056309  cmp     [rcx+30h], r14w
0x18005630e  mov     r8b, r15b
0x180056311  jnz     short loc_180056316
0x180056313  mov     r8b, r14b; int
0x180056316  lea     r9, WPP_6fa7f4f46ed53a8c08fe2b7537b301f3_Traceguids
0x18005631d  test    dl, dl
0x18005631f  jnz     short loc_180056326
0x180056321  test    r8b, r8b
0x180056324  jz      short loc_180056355
0x180056326  mov     qword ptr [rsp+68h+var_28], rdi; char
0x18005632b  mov     [rsp+68h+MessageGuid], r9; MessageGuid
0x180056330  mov     [rsp+68h+var_38], 0Fh; __int16
0x180056337  mov     [rsp+68h+var_40], r15d; int
0x18005633c  mov     [rsp+68h+var_48], 5; int
0x180056341  mov     r9, [rcx+28h]; int
0x180056345  mov     rcx, [rcx+10h]; int
0x180056349  call    WPP_RECORDER_AND_TRACE_SF_q
0x18005634e  lea     r9, WPP_6fa7f4f46ed53a8c08fe2b7537b301f3_Traceguids
0x180056355  mov     rcx, r14
0x180056358  mov     [rbp+arg_0], rcx
0x18005635c  mov     [rbx], r14
0x18005635f  cmp     [rdi+8], r14
0x180056363  jz      loc_18005649B
0x180056369  mov     edx, 0C8h; lpProcName
0x18005636e  mov     rcx, [rdi+8]; hModule
0x180056372  call    cs:__imp_GetProcAddress
0x180056378  test    rax, rax
0x18005637b  jz      loc_180056433
0x180056381  movups  xmm0, xmmword ptr [rsi]
0x180056384  movdqu  xmmword ptr [rbp+var_18.Data1], xmm0
0x180056389  lea     rdx, [rbp+arg_0]
0x18005638d  lea     rcx, [rbp+var_18]
0x180056391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056396  mov     rcx, [rbp+40h]; this
0x18005639a  test    eax, eax
0x18005639c  js      loc_180056520
0x1800563a2  mov     rcx, [rbp+arg_0]
0x1800563a6  test    rcx, rcx
0x1800563a9  jz      short loc_1800563BB
0x1800563ab  mov     rax, [rcx]
0x1800563ae  mov     rax, [rax+8]
0x1800563b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800563b7  mov     rcx, [rbp+arg_0]
0x1800563bb  mov     [rbx], rcx
0x1800563be  mov     rax, cs:WPP_GLOBAL_Control
0x1800563c5  cmp     rax, r12
0x1800563c8  jz      short loc_1800563D9
0x1800563ca  test    [rax+1Ch], r15b
0x1800563ce  jz      short loc_1800563D9
0x1800563d0  cmp     byte ptr [rax+19h], 5
0x1800563d4  mov     dl, r15b
0x1800563d7  jnb     short loc_1800563DC
0x1800563d9  mov     dl, r14b; int
0x1800563dc  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1800563e3  jz      short loc_1800563EF
0x1800563e5  cmp     [rax+30h], r14w
0x1800563ea  mov     r8b, r15b
0x1800563ed  jnz     short loc_1800563F2
0x1800563ef  mov     r8b, r14b; int
0x1800563f2  test    dl, dl
0x1800563f4  jnz     short loc_1800563FB
0x1800563f6  test    r8b, r8b
0x1800563f9  jz      short loc_18005642E
0x1800563fb  mov     qword ptr [rsp+68h+var_28], rdi; char
0x180056400  lea     r9, WPP_6fa7f4f46ed53a8c08fe2b7537b301f3_Traceguids
0x180056407  mov     [rsp+68h+MessageGuid], r9; MessageGuid
0x18005640c  mov     [rsp+68h+var_38], 12h; __int16
0x180056413  mov     [rsp+68h+var_40], r15d; int
0x180056418  mov     [rsp+68h+var_48], 5; char
0x18005641d  mov     r9, [rax+28h]; int
0x180056421  mov     rcx, [rax+10h]; int
0x180056425  call    WPP_RECORDER_AND_TRACE_SF_q
0x18005642a  mov     rcx, [rbp+arg_0]
0x18005642e  jmp     loc_1800564F9
0x180056433  mov     rcx, cs:WPP_GLOBAL_Control
0x18005643a  cmp     rcx, r12
0x18005643d  jz      short loc_18005644E
0x18005643f  test    [rcx+1Ch], r15b
0x180056443  jz      short loc_18005644E
0x180056445  cmp     byte ptr [rcx+19h], 3
0x180056449  mov     dl, r15b
0x18005644c  jnb     short loc_180056451
0x18005644e  mov     dl, r14b; int
0x180056451  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180056458  setnz   r8b; int
0x18005645c  test    dl, dl
0x18005645e  jnz     short loc_180056465
0x180056460  test    r8b, r8b
0x180056463  jz      short loc_180056495
0x180056465  mov     qword ptr [rsp+68h+var_28], rdi; char
0x18005646a  lea     r9, WPP_6fa7f4f46ed53a8c08fe2b7537b301f3_Traceguids
0x180056471  mov     [rsp+68h+MessageGuid], r9; MessageGuid
0x180056476  mov     [rsp+68h+var_38], 10h; __int16
0x18005647d  mov     [rsp+68h+var_40], r15d; int
0x180056482  mov     [rsp+68h+var_48], 3; char
0x180056487  mov     r9, [rcx+28h]; int
0x18005648b  mov     rcx, [rcx+10h]; int
0x18005648f  call    WPP_RECORDER_AND_TRACE_SF_q
0x180056494  nop
0x180056495  mov     rcx, [rbp+arg_0]
0x180056499  jmp     short loc_1800564F9
0x18005649b  mov     rax, cs:WPP_GLOBAL_Control
0x1800564a2  cmp     rax, r12
0x1800564a5  jz      short loc_1800564B6
0x1800564a7  test    [rax+1Ch], r15b
0x1800564ab  jz      short loc_1800564B6
0x1800564ad  cmp     byte ptr [rax+19h], 2
0x1800564b1  mov     dl, r15b
0x1800564b4  jnb     short loc_1800564B9
0x1800564b6  mov     dl, r14b; int
0x1800564b9  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1800564c0  setnz   r8b; int
0x1800564c4  test    dl, dl
0x1800564c6  jnz     short loc_1800564CD
0x1800564c8  test    r8b, r8b
0x1800564cb  jz      short loc_1800564F9
0x1800564cd  mov     qword ptr [rsp+68h+var_28], rdi; char
0x1800564d2  mov     [rsp+68h+MessageGuid], r9; MessageGuid
0x1800564d7  mov     [rsp+68h+var_38], 11h; __int16
0x1800564de  mov     [rsp+68h+var_40], r15d; int
0x1800564e3  mov     [rsp+68h+var_48], 2; char
0x1800564e8  mov     r9, [rax+28h]; int
0x1800564ec  mov     rcx, [rax+10h]; int
0x1800564f0  call    WPP_RECORDER_AND_TRACE_SF_q
0x1800564f5  mov     rcx, [rbp+arg_0]
0x1800564f9  test    rcx, rcx
0x1800564fc  jz      short loc_18005650F
0x1800564fe  mov     [rbp+arg_0], r14
0x180056502  mov     rax, [rcx]
0x180056505  mov     rax, [rax+10h]
0x180056509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005650e  nop
0x18005650f  add     rsp, 68h
0x180056513  pop     r15
0x180056515  pop     r14
0x180056517  pop     r13
0x180056519  pop     r12
0x18005651b  pop     rdi
0x18005651c  pop     rsi
0x18005651d  pop     rbx
0x18005651e  pop     rbp
0x18005651f  retn
0x180056520  mov     r9d, eax; char *
0x180056523  lea     r8, aOnecoreDrivers_5; "onecore\\drivers\\bluetooth\\profiles\\"...
0x18005652a  mov     edx, 43h ; 'C'; void *
0x18005652f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
