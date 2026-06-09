# RIMAddNonPnpDeviceOfTypeUsingSuppliedFileHandle

- ea: `0x1400b7ee0`
- end: `0x1400b84a5`
- name: `RIMAddNonPnpDeviceOfTypeUsingSuppliedFileHandle`
- size: `1477`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x1400b6d30`

## callees

- `0x1400411c0`
- `0x1400449b0`
- `0x140066bf0`
- `0x140071828`
- `0x1400718f0`
- `0x14009e3c0`
- `0x1400b7e20`
- `0x1400b7ee0`
- `0x1400e5630`
- `0x1400fc030`
- `0x1401357d0`
- `0x1401362e4`
- `0x14019eeb8`
- `0x1401aa4fc`
- `0x1402bd208`
- `0x1402bd244`
- `0x1402bd3b4`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1400b8132`
- `ntoskrnl!ProbeForRead` at `0x1400b8132`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1400b81d2`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1400b81d2`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400b8185`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400b8185`
- `ntoskrnl!ObfDereferenceObject` at `0x1400b8305`
- `ntoskrnl!ObfDereferenceObject` at `0x1400b8305`
- `WIN32K!W32GetUserSessionState` at `0x1400b7f56`
- `WIN32K!W32GetUserSessionState` at `0x1400b7fe6`
- `WIN32K!W32GetUserSessionState` at `0x1400b8343`
- `WIN32K!W32GetUserSessionState` at `0x1400b83e7`
- `WIN32K!W32GetUserSessionState` at `0x1400b847a`
- `WIN32K!W32GetUserSessionState` at `0x1400b7f56`
- `WIN32K!W32GetUserSessionState` at `0x1400b7fe6`
- `WIN32K!W32GetUserSessionState` at `0x1400b8343`
- `WIN32K!W32GetUserSessionState` at `0x1400b83e7`
- `WIN32K!W32GetUserSessionState` at `0x1400b847a`

## pseudocode

```c
__int64 __fastcall RIMAddNonPnpDeviceOfTypeUsingSuppliedFileHandle(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        void *a4,
        int a5,
        _QWORD *a6)
{
  char v6; // bl
  bool v7; // r14
  __int64 UserSessionState; // rax
  int v9; // r8d
  int v10; // edx
  char v11; // bl
  bool v12; // r14
  __int64 v13; // rax
  int v14; // r8d
  int v15; // edx
  int v17; // r14d
  struct RawInputManagerObject *v18; // r15
  int ULongFromUser; // ebx
  char v20; // bl
  bool v21; // r15
  __int64 v22; // rax
  int v23; // r8d
  int v24; // edx
  char v25; // bl
  int v26; // edx
  int v27; // r8d
  __int64 v28; // r9
  __int16 v29; // [rsp+30h] [rbp-B8h]
  struct RIMDEV *v30; // [rsp+50h] [rbp-98h] BYREF
  PVOID Object; // [rsp+58h] [rbp-90h] BYREF
  UNICODE_STRING SourceString; // [rsp+60h] [rbp-88h] BYREF
  int v33; // [rsp+70h] [rbp-78h]
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-70h] BYREF
  struct _UNICODE_STRING *p_DestinationString; // [rsp+88h] [rbp-60h]
  char *v36; // [rsp+90h] [rbp-58h]
  __int128 v37; // [rsp+98h] [rbp-50h]
  __int64 v38; // [rsp+F0h] [rbp+8h]
  bool Handlea; // [rsp+108h] [rbp+20h]

  v38 = a1;
  Object = 0;
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
    || (v6 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
  {
    v6 = 0;
  }
  v7 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    UserSessionState = W32GetUserSessionState(a1);
    LOBYTE(v9) = v7;
    LOBYTE(v10) = v6;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v10,
      v9,
      *(_QWORD *)(UserSessionState + 19408),
      4,
      1,
      30,
      (__int64)&WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids);
    a1 = v38;
  }
  if ( !a4 )
  {
    if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
      || (v11 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
    {
      v11 = 0;
    }
    v12 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v13 = W32GetUserSessionState(WPP_GLOBAL_Control);
      LOBYTE(v14) = v12;
      LOBYTE(v15) = v11;
      WPP_RECORDER_AND_TRACE_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 3),
        v15,
        v14,
        *(_QWORD *)(v13 + 19408),
        4,
        1,
        31,
        (__int64)&WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids,
        13);
    }
    return 3221225485LL;
  }
  v17 = RawInputManagerObjectResolveHandle(a1, 3, 1, &Object);
  if ( v17 >= 0 )
  {
    v18 = (struct RawInputManagerObject *)Object;
    v36 = (char *)Object + 96;
    RIMLockExclusive((char *)Object + 96);
    if ( *((_BYTE *)v18 + 73) || *((_BYTE *)v18 + 74) )
    {
      v17 = -1073741637;
      if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
        || (v25 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
      {
        v25 = 0;
      }
      Handlea = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v25 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_41;
      v28 = *(_QWORD *)(W32GetUserSessionState(WPP_GLOBAL_Control) + 19408);
      v29 = 33;
    }
    else
    {
      if ( ((unsigned int)DeviceTypeToRimInputType(a3) & *((_DWORD *)v18 + 19)) != 0 )
      {
        SourceString = 0;
        p_DestinationString = 0;
        DestinationString = 0;
        if ( a5 )
        {
          v37 = 0;
          ULongFromUser = RtlReadULongFromUser(a2);
          LODWORD(v37) = ULongFromUser;
          *((_QWORD *)&v37 + 1) = RtlReadULong64FromUser(a2 + 8);
          *(_DWORD *)&SourceString.Length = ULongFromUser;
          *(_DWORD *)(&SourceString.MaximumLength + 1) = DWORD1(v37);
          SourceString.Buffer = (PWSTR)*((_QWORD *)&v37 + 1);
          ProbeForRead(*((volatile void **)&v37 + 1), (unsigned __int16)ULongFromUser + 2LL, 2u);
          if ( SourceString.Length > SourceString.MaximumLength || (SourceString.Length & 1) != 0 )
          {
            if ( (SourceString.Length & 1) != 0 )
            {
              LODWORD(v30) = 0x20000;
              MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 991);
            }
            ExRaiseAccessViolation();
          }
          DestinationString.MaximumLength = SourceString.Length;
          DestinationString.Length = SourceString.Length;
          DestinationString.Buffer = (PWSTR)Win32AllocPoolZInitImpl(0x100u, SourceString.Length, 0x706D7452u);
          if ( DestinationString.Buffer )
          {
            RtlCopyUnicodeString(&DestinationString, &SourceString);
            p_DestinationString = &DestinationString;
          }
          else
          {
            v17 = -1073741801;
            v33 = -1073741801;
          }
        }
        if ( v17 >= 0 )
        {
          v30 = 0;
          v17 = RIMCreateDev(v18, 0, 0, (__int64)&v30);
          if ( v17 >= 0 )
          {
            *((_DWORD *)v30 + 42) |= 1u;
            v17 = rimOnPnpArrived(v18, v30, a4);
            if ( v17 >= 0 )
            {
              rimDoRimDevChange(v18, v30, 2);
              if ( a6 )
              {
                if ( a5 )
                  RtlWriteULong64ToUser(a6, *((_QWORD *)v30 + 2));
                else
                  *a6 = *((_QWORD *)v30 + 2);
              }
            }
            if ( v17 < 0 )
              RIMFreeDev(v18, v30);
          }
        }
        if ( DestinationString.Buffer )
          GreDeleteFastMutex(DestinationString.Buffer);
        goto LABEL_41;
      }
      v17 = -1073741637;
      if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
        || (v25 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
      {
        v25 = 0;
      }
      Handlea = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v25 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_41;
      v28 = *(_QWORD *)(W32GetUserSessionState(WPP_GLOBAL_Control) + 19408);
      v29 = 32;
    }
    LOBYTE(v27) = Handlea;
    LOBYTE(v26) = v25;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v26,
      v27,
      v28,
      3,
      1,
      v29,
      (__int64)&WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids);
LABEL_41:
    RIMUnlockExclusive(v36);
    ObfDereferenceObject(v18);
  }
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
    || (v20 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
  {
    v20 = 0;
  }
  v21 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v20 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v22 = W32GetUserSessionState(WPP_GLOBAL_Control);
    LOBYTE(v23) = v21;
    LOBYTE(v24) = v20;
    WPP_RECORDER_AND_TRACE_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v24,
      v23,
      *(_QWORD *)(v22 + 19408),
      4,
      1,
      34,
      (__int64)&WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids,
      v17);
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1400b7ee0  mov     rax, rsp
0x1400b7ee3  mov     [rax+20h], r9
0x1400b7ee7  mov     [rax+18h], r8d
0x1400b7eeb  mov     [rax+10h], rdx
0x1400b7eef  mov     [rax+8], rcx
0x1400b7ef3  push    rbx
0x1400b7ef4  push    rdi
0x1400b7ef5  push    r12
0x1400b7ef7  push    r13
0x1400b7ef9  push    r14
0x1400b7efb  push    r15
0x1400b7efd  sub     rsp, 0B8h
0x1400b7f04  xor     edi, edi
0x1400b7f06  mov     [rsp+0E8h+Object], rdi
0x1400b7f0b  lea     r13, WPP_GLOBAL_Control
0x1400b7f12  mov     r10, cs:WPP_GLOBAL_Control
0x1400b7f19  cmp     r10, r13
0x1400b7f1c  jz      short loc_1400B7F2F
0x1400b7f1e  mov     eax, [r10+2Ch]
0x1400b7f22  test    al, 1
0x1400b7f24  jz      short loc_1400B7F2F
0x1400b7f26  cmp     byte ptr [r10+29h], 4
0x1400b7f2b  mov     bl, 1
0x1400b7f2d  jnb     short loc_1400B7F32
0x1400b7f2f  mov     bl, dil
0x1400b7f32  lea     r12, WPP_RECORDER_INITIALIZED
0x1400b7f39  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400b7f40  setnz   r14b
0x1400b7f44  test    bl, bl
0x1400b7f46  jnz     short loc_1400B7F56
0x1400b7f48  test    r14b, r14b
0x1400b7f4b  jnz     short loc_1400B7F56
0x1400b7f4d  lea     r15, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x1400b7f54  jmp     short loc_1400B7FA6
0x1400b7f56  call    cs:__imp_W32GetUserSessionState
0x1400b7f5d  nop     dword ptr [rax+rax+00h]
0x1400b7f62  mov     r9, [rax+4BD0h]
0x1400b7f69  lea     r15, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x1400b7f70  mov     [rsp+0E8h+var_B0], r15
0x1400b7f75  mov     word ptr [rsp+0E8h+var_B8], 1Eh
0x1400b7f7c  mov     dword ptr [rsp+0E8h+var_C0], 1
0x1400b7f84  mov     byte ptr [rsp+0E8h+var_C8], 4
0x1400b7f89  mov     r8b, r14b
0x1400b7f8c  mov     dl, bl
0x1400b7f8e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b7f95  mov     rcx, [rcx+18h]
0x1400b7f99  call    WPP_RECORDER_AND_TRACE_SF_
0x1400b7f9e  mov     rcx, [rsp+0E8h+arg_0]
0x1400b7fa6  cmp     [rsp+0E8h+Handle], rdi
0x1400b7fae  jnz     loc_1400B8039
0x1400b7fb4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b7fbb  cmp     rcx, r13
0x1400b7fbe  jz      short loc_1400B7FCF
0x1400b7fc0  mov     eax, [rcx+2Ch]
0x1400b7fc3  test    al, 1
0x1400b7fc5  jz      short loc_1400B7FCF
0x1400b7fc7  cmp     byte ptr [rcx+29h], 4
0x1400b7fcb  mov     bl, 1
0x1400b7fcd  jnb     short loc_1400B7FD2
0x1400b7fcf  mov     bl, dil
0x1400b7fd2  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400b7fd9  setnz   r14b
0x1400b7fdd  test    bl, bl
0x1400b7fdf  jnz     short loc_1400B7FE6
0x1400b7fe1  test    r14b, r14b
0x1400b7fe4  jz      short loc_1400B802F
0x1400b7fe6  call    cs:__imp_W32GetUserSessionState
0x1400b7fed  nop     dword ptr [rax+rax+00h]
0x1400b7ff2  mov     r9, [rax+4BD0h]
0x1400b7ff9  mov     [rsp+0E8h+var_A8], 0C000000Dh
0x1400b8001  mov     [rsp+0E8h+var_B0], r15
0x1400b8006  mov     word ptr [rsp+0E8h+var_B8], 1Fh
0x1400b800d  mov     dword ptr [rsp+0E8h+var_C0], 1
0x1400b8015  mov     byte ptr [rsp+0E8h+var_C8], 4
0x1400b801a  mov     r8b, r14b
0x1400b801d  mov     dl, bl
0x1400b801f  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b8026  mov     rcx, [rcx+18h]
0x1400b802a  call    WPP_RECORDER_AND_TRACE_SF_d
0x1400b802f  mov     eax, 0C000000Dh
0x1400b8034  jmp     loc_1400B8393
0x1400b8039  lea     r9, [rsp+0E8h+Object]
0x1400b803e  mov     edx, 3
0x1400b8043  lea     r8d, [rdx-2]
0x1400b8047  call    RawInputManagerObjectResolveHandle
0x1400b804c  mov     r14d, eax
0x1400b804f  test    eax, eax
0x1400b8051  js      loc_1400B8311
0x1400b8057  mov     r15, [rsp+0E8h+Object]
0x1400b805c  lea     rax, [r15+60h]
0x1400b8060  mov     [rsp+0E8h+var_58], rax
0x1400b8068  mov     rcx, rax
0x1400b806b  call    RIMLockExclusive
0x1400b8070  cmp     [r15+49h], dil
0x1400b8074  jnz     loc_1400B8439
0x1400b807a  cmp     [r15+4Ah], dil
0x1400b807e  jnz     loc_1400B8439
0x1400b8084  mov     ecx, [rsp+0E8h+arg_10]
0x1400b808b  call    DeviceTypeToRimInputType
0x1400b8090  test    [r15+4Ch], eax
0x1400b8094  jz      loc_1400B83A6
0x1400b809a  xorps   xmm0, xmm0
0x1400b809d  movups  xmmword ptr [rsp+0E8h+SourceString.Length], xmm0
0x1400b80a2  mov     r12, rdi
0x1400b80a5  mov     [rsp+0E8h+var_60], rdi
0x1400b80ad  movups  xmmword ptr [rsp+0E8h+DestinationString.Length], xmm0
0x1400b80b2  cmp     [rsp+0E8h+arg_20], edi
0x1400b80b9  jnz     short loc_1400B80CD
0x1400b80bb  mov     r12, [rsp+0E8h+arg_8]
0x1400b80c3  mov     ebx, 2
0x1400b80c8  jmp     loc_1400B8203
0x1400b80cd  movups  [rsp+0E8h+var_50], xmm0
0x1400b80d5  mov     rcx, [rsp+0E8h+arg_8]
0x1400b80dd  call    RtlReadULongFromUser
0x1400b80e2  mov     ebx, eax
0x1400b80e4  mov     dword ptr [rsp+0E8h+var_50], ebx
0x1400b80eb  mov     rcx, [rsp+0E8h+arg_8]
0x1400b80f3  add     rcx, 8
0x1400b80f7  call    RtlReadULong64FromUser
0x1400b80fc  mov     qword ptr [rsp+0E8h+var_50+8], rax
0x1400b8104  movzx   edx, bx
0x1400b8107  mov     [rsp+0E8h+SourceString.Length], dx
0x1400b810c  shr     ebx, 10h
0x1400b810f  mov     [rsp+0E8h+SourceString.MaximumLength], bx
0x1400b8114  mov     ecx, dword ptr [rsp+0E8h+var_50+4]
0x1400b811b  mov     dword ptr [rsp+0E8h+SourceString+4], ecx
0x1400b811f  mov     [rsp+0E8h+SourceString.Buffer], rax
0x1400b8124  mov     ebx, 2
0x1400b8129  add     rdx, rbx; Length
0x1400b812c  mov     r8d, ebx; Alignment
0x1400b812f  mov     rcx, rax; Address
0x1400b8132  call    cs:__imp_ProbeForRead
0x1400b8139  nop     dword ptr [rax+rax+00h]
0x1400b813e  movzx   eax, [rsp+0E8h+SourceString.Length]
0x1400b8143  cmp     ax, [rsp+0E8h+SourceString.MaximumLength]
0x1400b8148  ja      short loc_1400B81AD
0x1400b814a  mov     byte ptr [rsp+0E8h+SourceString.Length], al
0x1400b814e  test    al, 1
0x1400b8150  jnz     short loc_1400B81AD
0x1400b8152  mov     [rsp+0E8h+DestinationString.MaximumLength], ax
0x1400b8157  mov     [rsp+0E8h+DestinationString.Length], ax
0x1400b815c  mov     edx, eax; unsigned __int64
0x1400b815e  mov     ecx, 100h; unsigned __int64
0x1400b8163  mov     r8d, 706D7452h; unsigned int
0x1400b8169  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1400b816e  mov     [rsp+0E8h+DestinationString.Buffer], rax
0x1400b8176  test    rax, rax
0x1400b8179  jz      short loc_1400B81A0
0x1400b817b  lea     rdx, [rsp+0E8h+SourceString]; SourceString
0x1400b8180  lea     rcx, [rsp+0E8h+DestinationString]; DestinationString
0x1400b8185  call    cs:__imp_RtlCopyUnicodeString
0x1400b818c  nop     dword ptr [rax+rax+00h]
0x1400b8191  lea     r12, [rsp+0E8h+DestinationString]
0x1400b8196  mov     [rsp+0E8h+var_60], r12
0x1400b819e  jmp     short loc_1400B81AB
0x1400b81a0  mov     r14d, 0C0000017h
0x1400b81a6  mov     [rsp+0E8h+var_78], r14d
0x1400b81ab  jmp     short loc_1400B8203
0x1400b81ad  test    byte ptr [rsp+0E8h+SourceString.Length], 1
0x1400b81b2  jz      short loc_1400B81D2
0x1400b81b4  mov     dword ptr [rsp+0E8h+var_98], 20000h
0x1400b81bc  mov     r8d, 3DFh
0x1400b81c2  mov     edx, dword ptr [rsp+0E8h+var_98]
0x1400b81c6  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1400b81cd  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1400b81d2  call    cs:__imp_ExRaiseAccessViolation
0x1400b81d9  nop     dword ptr [rax+rax+00h]
0x1400b81de  nop
0x1400b81df  mov     r14d, 0C000000Dh
0x1400b81e5  mov     [rsp+0E8h+var_78], r14d
0x1400b81ea  xor     edi, edi
0x1400b81ec  lea     r13, WPP_GLOBAL_Control
0x1400b81f3  lea     ebx, [rdi+2]
0x1400b81f6  mov     r15, [rsp+0E8h+Object]
0x1400b81fb  mov     r12, [rsp+0E8h+var_60]
0x1400b8203  test    r14d, r14d
0x1400b8206  js      loc_1400B82DC
0x1400b820c  mov     [rsp+0E8h+var_98], rdi
0x1400b8211  lea     rax, [rsp+0E8h+var_98]
0x1400b8216  mov     [rsp+0E8h+var_B8], rax; __int64
0x1400b821b  mov     [rsp+0E8h+var_C0], rdi; __int64
0x1400b8220  mov     [rsp+0E8h+var_C8], edi; int
0x1400b8224  mov     r9d, 1
0x1400b822a  mov     r8, r12
0x1400b822d  mov     edx, [rsp+0E8h+arg_10]
0x1400b8234  mov     rcx, r15; struct RawInputManagerObject *
0x1400b8237  call    RIMCreateDev
0x1400b823c  mov     r14d, eax
0x1400b823f  test    eax, eax
0x1400b8241  js      loc_1400B82DC
0x1400b8247  mov     rax, [rsp+0E8h+var_98]
0x1400b824c  or      dword ptr [rax+0A8h], 1
0x1400b8253  mov     r8, [rsp+0E8h+Handle]; Handle
0x1400b825b  mov     rdx, [rsp+0E8h+var_98]; struct RIMDEV *
0x1400b8260  mov     rcx, r15; struct RawInputManagerObject *
0x1400b8263  call    rimOnPnpArrived
0x1400b8268  mov     r14d, eax
0x1400b826b  test    eax, eax
0x1400b826d  js      short loc_1400B82CA
0x1400b826f  mov     r8d, ebx
0x1400b8272  mov     rdx, [rsp+0E8h+var_98]
0x1400b8277  mov     rcx, r15
0x1400b827a  call    rimDoRimDevChange
0x1400b827f  mov     r8, [rsp+0E8h+arg_28]
0x1400b8287  test    r8, r8
0x1400b828a  jz      short loc_1400B82CA
0x1400b828c  cmp     [rsp+0E8h+arg_20], edi
0x1400b8293  jnz     short loc_1400B82A3
0x1400b8295  mov     rax, [rsp+0E8h+var_98]
0x1400b829a  mov     rcx, [rax+10h]
0x1400b829e  mov     [r8], rcx
0x1400b82a1  jmp     short loc_1400B82CA
0x1400b82a3  mov     rdx, [rsp+0E8h+var_98]
0x1400b82a8  mov     rdx, [rdx+10h]
0x1400b82ac  mov     rcx, r8
0x1400b82af  call    RtlWriteULong64ToUser
0x1400b82b4  jmp     short loc_1400B82CA
0x1400b82b6  xor     edi, edi
0x1400b82b8  mov     r14d, 0C000000Dh
0x1400b82be  lea     r13, WPP_GLOBAL_Control
0x1400b82c5  mov     r15, [rsp+0E8h+Object]
0x1400b82ca  test    r14d, r14d
0x1400b82cd  jns     short loc_1400B82DC
0x1400b82cf  mov     rdx, [rsp+0E8h+var_98]; struct RIMDEV *
0x1400b82d4  mov     rcx, r15; struct RawInputManagerObject *
0x1400b82d7  call    RIMFreeDev
0x1400b82dc  mov     rcx, [rsp+0E8h+DestinationString.Buffer]; Buffer
0x1400b82e4  test    rcx, rcx
0x1400b82e7  jz      short loc_1400B82EE
0x1400b82e9  call    GreDeleteFastMutex
0x1400b82ee  lea     r12, WPP_RECORDER_INITIALIZED
0x1400b82f5  mov     rcx, [rsp+0E8h+var_58]
0x1400b82fd  call    RIMUnlockExclusive
0x1400b8302  mov     rcx, r15; Object
0x1400b8305  call    cs:__imp_ObfDereferenceObject
0x1400b830c  nop     dword ptr [rax+rax+00h]
0x1400b8311  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b8318  cmp     rcx, r13
0x1400b831b  jz      short loc_1400B832C
0x1400b831d  mov     eax, [rcx+2Ch]
0x1400b8320  test    al, 1
0x1400b8322  jz      short loc_1400B832C
0x1400b8324  cmp     byte ptr [rcx+29h], 4
0x1400b8328  mov     bl, 1
0x1400b832a  jnb     short loc_1400B832F
0x1400b832c  mov     bl, dil
0x1400b832f  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400b8336  setnz   r15b
0x1400b833a  test    bl, bl
0x1400b833c  jnz     short loc_1400B8343
0x1400b833e  test    r15b, r15b
0x1400b8341  jz      short loc_1400B8390
0x1400b8343  call    cs:__imp_W32GetUserSessionState
0x1400b834a  nop     dword ptr [rax+rax+00h]
0x1400b834f  mov     r9, [rax+4BD0h]
0x1400b8356  mov     [rsp+0E8h+var_A8], r14d
0x1400b835b  lea     rax, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x1400b8362  mov     [rsp+0E8h+var_B0], rax
0x1400b8367  mov     word ptr [rsp+0E8h+var_B8], 22h ; '"'
0x1400b836e  mov     dword ptr [rsp+0E8h+var_C0], 1
0x1400b8376  mov     byte ptr [rsp+0E8h+var_C8], 4
0x1400b837b  mov     r8b, r15b
0x1400b837e  mov     dl, bl
0x1400b8380  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b8387  mov     rcx, [rcx+18h]
0x1400b838b  call    WPP_RECORDER_AND_TRACE_SF_d
0x1400b8390  mov     eax, r14d
0x1400b8393  add     rsp, 0B8h
0x1400b839a  pop     r15
0x1400b839c  pop     r14
0x1400b839e  pop     r13
0x1400b83a0  pop     r12
0x1400b83a2  pop     rdi
0x1400b83a3  pop     rbx
0x1400b83a4  retn
0x1400b83a6  mov     r14d, 0C00000BBh
0x1400b83ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b83b3  cmp     rcx, r13
0x1400b83b6  jz      short loc_1400B83C7
0x1400b83b8  mov     eax, [rcx+2Ch]
0x1400b83bb  test    al, 1
0x1400b83bd  jz      short loc_1400B83C7
0x1400b83bf  cmp     byte ptr [rcx+29h], 3
0x1400b83c3  mov     bl, 1
0x1400b83c5  jnb     short loc_1400B83CA
0x1400b83c7  mov     bl, dil
0x1400b83ca  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400b83d1  setnz   al
0x1400b83d4  mov     byte ptr [rsp+0E8h+Handle], al
0x1400b83db  test    bl, bl
0x1400b83dd  jnz     short loc_1400B83E7
0x1400b83df  test    al, al
0x1400b83e1  jz      loc_1400B82F5
0x1400b83e7  call    cs:__imp_W32GetUserSessionState
0x1400b83ee  nop     dword ptr [rax+rax+00h]
0x1400b83f3  mov     r9, [rax+4BD0h]
0x1400b83fa  lea     rax, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x1400b8401  mov     [rsp+0E8h+var_B0], rax
0x1400b8406  mov     word ptr [rsp+0E8h+var_B8], 20h ; ' '
0x1400b840d  mov     dword ptr [rsp+0E8h+var_C0], 1
  ... truncated ...
```
