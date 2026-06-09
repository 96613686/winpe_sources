# RIMAddNonPnpDeviceOfType

- ea: `0x1401fdbc0`
- end: `0x1401fe0da`
- name: `RIMAddNonPnpDeviceOfType`
- size: `1306`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `broker_com_uri`

## callees

- `0x1400411c0`
- `0x1400449b0`
- `0x140066bf0`
- `0x140071828`
- `0x1400718f0`
- `0x14009e3c0`
- `0x1400b7e20`
- `0x1400e5630`
- `0x1400fc030`
- `0x1401357d0`
- `0x14019eeb8`
- `0x1401aa4fc`
- `0x1401fdbc0`
- `0x1402bd208`
- `0x1402bd244`
- `0x1402bd3b4`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x1401fdd76`
- `ntoskrnl!ProbeForRead` at `0x1401fdd76`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401fde29`
- `ntoskrnl!ExRaiseAccessViolation` at `0x1401fde29`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1401fddd2`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1401fddd2`
- `ntoskrnl!ObfDereferenceObject` at `0x1401fdf43`
- `ntoskrnl!ObfDereferenceObject` at `0x1401fdf43`
- `WIN32K!W32GetUserSessionState` at `0x1401fdc2d`
- `WIN32K!W32GetUserSessionState` at `0x1401fdf81`
- `WIN32K!W32GetUserSessionState` at `0x1401fe022`
- `WIN32K!W32GetUserSessionState` at `0x1401fe0af`
- `WIN32K!W32GetUserSessionState` at `0x1401fdc2d`
- `WIN32K!W32GetUserSessionState` at `0x1401fdf81`
- `WIN32K!W32GetUserSessionState` at `0x1401fe022`
- `WIN32K!W32GetUserSessionState` at `0x1401fe0af`

## pseudocode

```c
__int64 __fastcall RIMAddNonPnpDeviceOfType(__int64 a1, __int64 a2, unsigned int a3, int a4, _QWORD *a5)
{
  char v5; // bl
  bool v6; // r14
  __int64 UserSessionState; // rax
  int v8; // r8d
  int v9; // edx
  int v10; // r14d
  struct RawInputManagerObject *v11; // r15
  int v12; // ebx
  int ULongFromUser; // ebx
  char v14; // bl
  bool v15; // r15
  __int64 v16; // rax
  int v17; // r8d
  int v18; // edx
  char v20; // bl
  int v21; // edx
  int v22; // r8d
  __int64 v23; // r9
  __int16 v24; // [rsp+30h] [rbp-B8h]
  bool v25; // [rsp+50h] [rbp-98h]
  struct RIMDEV *v26; // [rsp+58h] [rbp-90h] BYREF
  PVOID Object; // [rsp+60h] [rbp-88h] BYREF
  UNICODE_STRING SourceString; // [rsp+68h] [rbp-80h] BYREF
  int v29; // [rsp+78h] [rbp-70h]
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-68h] BYREF
  struct _UNICODE_STRING *p_DestinationString; // [rsp+90h] [rbp-58h]
  char *v32; // [rsp+98h] [rbp-50h]
  __int128 v33; // [rsp+A0h] [rbp-48h]

  Object = 0;
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
    || (v5 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
  {
    v5 = 0;
  }
  v6 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    UserSessionState = W32GetUserSessionState(a1);
    LOBYTE(v8) = v6;
    LOBYTE(v9) = v5;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v9,
      v8,
      *(_QWORD *)(UserSessionState + 19408),
      4,
      1,
      26,
      (__int64)&WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids);
  }
  v10 = RawInputManagerObjectResolveHandle(a1, 3, 1, &Object);
  if ( v10 >= 0 )
  {
    v11 = (struct RawInputManagerObject *)Object;
    v32 = (char *)Object + 96;
    RIMLockExclusive((char *)Object + 96);
    if ( *((_BYTE *)v11 + 73) || *((_BYTE *)v11 + 74) )
    {
      v10 = -1073741637;
      if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
        || (v20 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
      {
        v20 = 0;
      }
      v25 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v20 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_32;
      v23 = *(_QWORD *)(W32GetUserSessionState(WPP_GLOBAL_Control) + 19408);
      v24 = 28;
    }
    else
    {
      if ( ((unsigned int)DeviceTypeToRimInputType(a3) & *((_DWORD *)v11 + 19)) != 0 )
      {
        SourceString = 0;
        p_DestinationString = 0;
        DestinationString = 0;
        v12 = a4;
        if ( a4 )
        {
          v33 = 0;
          ULongFromUser = RtlReadULongFromUser(a2);
          LODWORD(v33) = ULongFromUser;
          *((_QWORD *)&v33 + 1) = RtlReadULong64FromUser(a2 + 8);
          *(_DWORD *)&SourceString.Length = ULongFromUser;
          *(_DWORD *)(&SourceString.MaximumLength + 1) = DWORD1(v33);
          SourceString.Buffer = (PWSTR)*((_QWORD *)&v33 + 1);
          ProbeForRead(*((volatile void **)&v33 + 1), (unsigned __int16)ULongFromUser + 2LL, 2u);
          if ( SourceString.Length > SourceString.MaximumLength || (SourceString.Length & 1) != 0 )
          {
            if ( (SourceString.Length & 1) != 0 )
            {
              LODWORD(v26) = 0x20000;
              MicrosoftTelemetryAssertTriggeredArgsKM("IXPTelAssert", 0x20000, 833);
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
            v10 = -1073741801;
            v29 = -1073741801;
          }
          v12 = a4;
        }
        if ( v10 >= 0 )
        {
          v26 = 0;
          v10 = RIMCreateDev(v11, 0, 0, (__int64)&v26);
          if ( v10 >= 0 )
          {
            *((_DWORD *)v26 + 42) |= 1u;
            v10 = rimOnPnpArrived(v11, v26, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
            if ( v10 >= 0 )
            {
              if ( v12 )
                RtlWriteULong64ToUser(a5, *((_QWORD *)v26 + 2));
              else
                *a5 = *((_QWORD *)v26 + 2);
            }
            if ( v10 < 0 )
              RIMFreeDev(v11, v26);
          }
        }
        if ( DestinationString.Buffer )
          GreDeleteFastMutex(DestinationString.Buffer);
        goto LABEL_32;
      }
      v10 = -1073741637;
      if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
        || (v20 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 3u) )
      {
        v20 = 0;
      }
      v25 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v20 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_32;
      v23 = *(_QWORD *)(W32GetUserSessionState(WPP_GLOBAL_Control) + 19408);
      v24 = 27;
    }
    LOBYTE(v22) = v25;
    LOBYTE(v21) = v20;
    WPP_RECORDER_AND_TRACE_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v21,
      v22,
      v23,
      3,
      1,
      v24,
      (__int64)&WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids);
LABEL_32:
    RIMUnlockExclusive(v32);
    ObfDereferenceObject(v11);
  }
  if ( WPP_GLOBAL_Control == (CTouchProcessor *)&WPP_GLOBAL_Control
    || (*((_DWORD *)WPP_GLOBAL_Control + 11) & 1) == 0
    || (v14 = 1, *((_BYTE *)WPP_GLOBAL_Control + 41) < 4u) )
  {
    v14 = 0;
  }
  v15 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v14 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v16 = W32GetUserSessionState(WPP_GLOBAL_Control);
    LOBYTE(v17) = v15;
    LOBYTE(v18) = v14;
    WPP_RECORDER_AND_TRACE_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 3),
      v18,
      v17,
      *(_QWORD *)(v16 + 19408),
      4,
      1,
      29,
      (__int64)&WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids,
      v10);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1401fdbc0  mov     rax, rsp
0x1401fdbc3  mov     [rax+20h], r9d
0x1401fdbc7  mov     [rax+18h], r8d
0x1401fdbcb  mov     [rax+10h], rdx
0x1401fdbcf  mov     [rax+8], rcx
0x1401fdbd3  push    rbx
0x1401fdbd4  push    rdi
0x1401fdbd5  push    r12
0x1401fdbd7  push    r13
0x1401fdbd9  push    r14
0x1401fdbdb  push    r15
0x1401fdbdd  sub     rsp, 0B8h
0x1401fdbe4  xor     edi, edi
0x1401fdbe6  mov     [rsp+0E8h+Object], rdi
0x1401fdbeb  lea     r13, WPP_GLOBAL_Control
0x1401fdbf2  mov     r10, cs:WPP_GLOBAL_Control
0x1401fdbf9  cmp     r10, r13
0x1401fdbfc  jz      short loc_1401FDC0F
0x1401fdbfe  mov     eax, [r10+2Ch]
0x1401fdc02  test    al, 1
0x1401fdc04  jz      short loc_1401FDC0F
0x1401fdc06  cmp     byte ptr [r10+29h], 4
0x1401fdc0b  mov     bl, 1
0x1401fdc0d  jnb     short loc_1401FDC12
0x1401fdc0f  mov     bl, dil
0x1401fdc12  lea     r12, WPP_RECORDER_INITIALIZED
0x1401fdc19  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1401fdc20  setnz   r14b
0x1401fdc24  test    bl, bl
0x1401fdc26  jnz     short loc_1401FDC2D
0x1401fdc28  test    r14b, r14b
0x1401fdc2b  jz      short loc_1401FDC75
0x1401fdc2d  call    cs:__imp_W32GetUserSessionState
0x1401fdc34  nop     dword ptr [rax+rax+00h]
0x1401fdc39  mov     r9, [rax+4BD0h]
0x1401fdc40  lea     r15, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x1401fdc47  mov     [rsp+0E8h+var_B0], r15
0x1401fdc4c  mov     word ptr [rsp+0E8h+var_B8], 1Ah
0x1401fdc53  mov     dword ptr [rsp+0E8h+var_C0], 1
0x1401fdc5b  mov     byte ptr [rsp+0E8h+var_C8], 4
0x1401fdc60  mov     r8b, r14b
0x1401fdc63  mov     dl, bl
0x1401fdc65  mov     rcx, cs:WPP_GLOBAL_Control
0x1401fdc6c  mov     rcx, [rcx+18h]
0x1401fdc70  call    WPP_RECORDER_AND_TRACE_SF_
0x1401fdc75  lea     r9, [rsp+0E8h+Object]
0x1401fdc7a  mov     edx, 3
0x1401fdc7f  lea     r8d, [rdx-2]
0x1401fdc83  mov     rcx, [rsp+0E8h+arg_0]
0x1401fdc8b  call    RawInputManagerObjectResolveHandle
0x1401fdc90  mov     r14d, eax
0x1401fdc93  test    eax, eax
0x1401fdc95  js      loc_1401FDF4F
0x1401fdc9b  mov     r15, [rsp+0E8h+Object]
0x1401fdca0  lea     rax, [r15+60h]
0x1401fdca4  mov     [rsp+0E8h+var_50], rax
0x1401fdcac  mov     rcx, rax
0x1401fdcaf  call    RIMLockExclusive
0x1401fdcb4  cmp     [r15+49h], dil
0x1401fdcb8  jnz     loc_1401FE071
0x1401fdcbe  cmp     [r15+4Ah], dil
0x1401fdcc2  jnz     loc_1401FE071
0x1401fdcc8  mov     ecx, [rsp+0E8h+arg_10]
0x1401fdccf  call    DeviceTypeToRimInputType
0x1401fdcd4  test    [r15+4Ch], eax
0x1401fdcd8  jz      loc_1401FDFE4
0x1401fdcde  xorps   xmm0, xmm0
0x1401fdce1  movups  xmmword ptr [rsp+0E8h+SourceString.Length], xmm0
0x1401fdce6  mov     r12, rdi
0x1401fdce9  mov     [rsp+0E8h+var_58], rdi
0x1401fdcf1  movups  xmmword ptr [rsp+0E8h+DestinationString.Length], xmm0
0x1401fdcf9  mov     ebx, [rsp+0E8h+arg_18]
0x1401fdd00  test    ebx, ebx
0x1401fdd02  jnz     short loc_1401FDD11
0x1401fdd04  mov     r12, [rsp+0E8h+arg_8]
0x1401fdd0c  jmp     loc_1401FDE5E
0x1401fdd11  movups  [rsp+0E8h+var_48], xmm0
0x1401fdd19  mov     rcx, [rsp+0E8h+arg_8]
0x1401fdd21  call    RtlReadULongFromUser
0x1401fdd26  mov     ebx, eax
0x1401fdd28  mov     dword ptr [rsp+0E8h+var_48], ebx
0x1401fdd2f  mov     rcx, [rsp+0E8h+arg_8]
0x1401fdd37  add     rcx, 8
0x1401fdd3b  call    RtlReadULong64FromUser
0x1401fdd40  mov     qword ptr [rsp+0E8h+var_48+8], rax
0x1401fdd48  movzx   edx, bx
0x1401fdd4b  mov     [rsp+0E8h+SourceString.Length], dx
0x1401fdd50  shr     ebx, 10h
0x1401fdd53  mov     [rsp+0E8h+SourceString.MaximumLength], bx
0x1401fdd58  mov     ecx, dword ptr [rsp+0E8h+var_48+4]
0x1401fdd5f  mov     dword ptr [rsp+0E8h+SourceString+4], ecx
0x1401fdd63  mov     [rsp+0E8h+SourceString.Buffer], rax
0x1401fdd68  mov     ebx, 2
0x1401fdd6d  add     rdx, rbx; Length
0x1401fdd70  mov     r8d, ebx; Alignment
0x1401fdd73  mov     rcx, rax; Address
0x1401fdd76  call    cs:__imp_ProbeForRead
0x1401fdd7d  nop     dword ptr [rax+rax+00h]
0x1401fdd82  movzx   eax, [rsp+0E8h+SourceString.Length]
0x1401fdd87  cmp     ax, [rsp+0E8h+SourceString.MaximumLength]
0x1401fdd8c  ja      short loc_1401FDE04
0x1401fdd8e  mov     byte ptr [rsp+0E8h+SourceString.Length], al
0x1401fdd92  test    al, 1
0x1401fdd94  jnz     short loc_1401FDE04
0x1401fdd96  mov     [rsp+0E8h+DestinationString.MaximumLength], ax
0x1401fdd9e  mov     [rsp+0E8h+DestinationString.Length], ax
0x1401fdda6  mov     edx, eax; unsigned __int64
0x1401fdda8  mov     ecx, 100h; unsigned __int64
0x1401fddad  mov     r8d, 706D7452h; unsigned int
0x1401fddb3  call    ?Win32AllocPoolZInitImpl@@YAPEAX_K0K@Z; Win32AllocPoolZInitImpl(unsigned __int64,unsigned __int64,ulong)
0x1401fddb8  mov     [rsp+0E8h+DestinationString.Buffer], rax
0x1401fddc0  test    rax, rax
0x1401fddc3  jz      short loc_1401FDDF0
0x1401fddc5  lea     rdx, [rsp+0E8h+SourceString]; SourceString
0x1401fddca  lea     rcx, [rsp+0E8h+DestinationString]; DestinationString
0x1401fddd2  call    cs:__imp_RtlCopyUnicodeString
0x1401fddd9  nop     dword ptr [rax+rax+00h]
0x1401fddde  lea     r12, [rsp+0E8h+DestinationString]
0x1401fdde6  mov     [rsp+0E8h+var_58], r12
0x1401fddee  jmp     short loc_1401FDDFB
0x1401fddf0  mov     r14d, 0C0000017h
0x1401fddf6  mov     [rsp+0E8h+var_70], r14d
0x1401fddfb  mov     ebx, [rsp+0E8h+arg_18]
0x1401fde02  jmp     short loc_1401FDE5E
0x1401fde04  test    byte ptr [rsp+0E8h+SourceString.Length], 1
0x1401fde09  jz      short loc_1401FDE29
0x1401fde0b  mov     dword ptr [rsp+0E8h+var_90], 20000h
0x1401fde13  mov     r8d, 341h
0x1401fde19  mov     edx, dword ptr [rsp+0E8h+var_90]
0x1401fde1d  lea     rcx, aIxptelassert; "IXPTelAssert"
0x1401fde24  call    MicrosoftTelemetryAssertTriggeredArgsKM
0x1401fde29  call    cs:__imp_ExRaiseAccessViolation
0x1401fde30  nop     dword ptr [rax+rax+00h]
0x1401fde35  nop
0x1401fde36  mov     r14d, 0C000000Dh
0x1401fde3c  mov     [rsp+0E8h+var_70], r14d
0x1401fde41  xor     edi, edi
0x1401fde43  lea     r13, WPP_GLOBAL_Control
0x1401fde4a  mov     r15, [rsp+0E8h+Object]
0x1401fde4f  mov     r12, [rsp+0E8h+var_58]
0x1401fde57  mov     ebx, [rsp+0E8h+arg_18]
0x1401fde5e  test    r14d, r14d
0x1401fde61  js      loc_1401FDF1A
0x1401fde67  mov     [rsp+0E8h+var_90], rdi
0x1401fde6c  lea     rax, [rsp+0E8h+var_90]
0x1401fde71  mov     [rsp+0E8h+var_B8], rax; __int64
0x1401fde76  mov     [rsp+0E8h+var_C0], rdi; __int64
0x1401fde7b  mov     [rsp+0E8h+var_C8], edi; int
0x1401fde7f  mov     r9d, 1
0x1401fde85  mov     r8, r12
0x1401fde88  mov     edx, [rsp+0E8h+arg_10]
0x1401fde8f  mov     rcx, r15; struct RawInputManagerObject *
0x1401fde92  call    RIMCreateDev
0x1401fde97  mov     r14d, eax
0x1401fde9a  test    eax, eax
0x1401fde9c  js      short loc_1401FDF1A
0x1401fde9e  mov     rax, [rsp+0E8h+var_90]
0x1401fdea3  or      dword ptr [rax+0A8h], 1
0x1401fdeaa  or      r8, 0FFFFFFFFFFFFFFFFh; Handle
0x1401fdeae  mov     rdx, [rsp+0E8h+var_90]; struct RIMDEV *
0x1401fdeb3  mov     rcx, r15; struct RawInputManagerObject *
0x1401fdeb6  call    rimOnPnpArrived
0x1401fdebb  mov     r14d, eax
0x1401fdebe  test    eax, eax
0x1401fdec0  js      short loc_1401FDF08
0x1401fdec2  test    ebx, ebx
0x1401fdec4  jnz     short loc_1401FDEDC
0x1401fdec6  mov     rax, [rsp+0E8h+var_90]
0x1401fdecb  mov     rcx, [rax+10h]
0x1401fdecf  mov     rax, [rsp+0E8h+arg_20]
0x1401fded7  mov     [rax], rcx
0x1401fdeda  jmp     short loc_1401FDF08
0x1401fdedc  mov     rdx, [rsp+0E8h+var_90]
0x1401fdee1  mov     rdx, [rdx+10h]
0x1401fdee5  mov     rcx, [rsp+0E8h+arg_20]
0x1401fdeed  call    RtlWriteULong64ToUser
0x1401fdef2  jmp     short loc_1401FDF08
0x1401fdef4  xor     edi, edi
0x1401fdef6  mov     r14d, 0C000000Dh
0x1401fdefc  lea     r13, WPP_GLOBAL_Control
0x1401fdf03  mov     r15, [rsp+0E8h+Object]
0x1401fdf08  test    r14d, r14d
0x1401fdf0b  jns     short loc_1401FDF1A
0x1401fdf0d  mov     rdx, [rsp+0E8h+var_90]; struct RIMDEV *
0x1401fdf12  mov     rcx, r15; struct RawInputManagerObject *
0x1401fdf15  call    RIMFreeDev
0x1401fdf1a  mov     rcx, [rsp+0E8h+DestinationString.Buffer]; Buffer
0x1401fdf22  test    rcx, rcx
0x1401fdf25  jz      short loc_1401FDF2C
0x1401fdf27  call    GreDeleteFastMutex
0x1401fdf2c  lea     r12, WPP_RECORDER_INITIALIZED
0x1401fdf33  mov     rcx, [rsp+0E8h+var_50]
0x1401fdf3b  call    RIMUnlockExclusive
0x1401fdf40  mov     rcx, r15; Object
0x1401fdf43  call    cs:__imp_ObfDereferenceObject
0x1401fdf4a  nop     dword ptr [rax+rax+00h]
0x1401fdf4f  mov     rcx, cs:WPP_GLOBAL_Control
0x1401fdf56  cmp     rcx, r13
0x1401fdf59  jz      short loc_1401FDF6A
0x1401fdf5b  mov     eax, [rcx+2Ch]
0x1401fdf5e  test    al, 1
0x1401fdf60  jz      short loc_1401FDF6A
0x1401fdf62  cmp     byte ptr [rcx+29h], 4
0x1401fdf66  mov     bl, 1
0x1401fdf68  jnb     short loc_1401FDF6D
0x1401fdf6a  mov     bl, dil
0x1401fdf6d  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1401fdf74  setnz   r15b
0x1401fdf78  test    bl, bl
0x1401fdf7a  jnz     short loc_1401FDF81
0x1401fdf7c  test    r15b, r15b
0x1401fdf7f  jz      short loc_1401FDFCE
0x1401fdf81  call    cs:__imp_W32GetUserSessionState
0x1401fdf88  nop     dword ptr [rax+rax+00h]
0x1401fdf8d  mov     r9, [rax+4BD0h]
0x1401fdf94  mov     [rsp+0E8h+var_A8], r14d
0x1401fdf99  lea     rax, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x1401fdfa0  mov     [rsp+0E8h+var_B0], rax
0x1401fdfa5  mov     word ptr [rsp+0E8h+var_B8], 1Dh
0x1401fdfac  mov     dword ptr [rsp+0E8h+var_C0], 1
0x1401fdfb4  mov     byte ptr [rsp+0E8h+var_C8], 4
0x1401fdfb9  mov     r8b, r15b
0x1401fdfbc  mov     dl, bl
0x1401fdfbe  mov     rcx, cs:WPP_GLOBAL_Control
0x1401fdfc5  mov     rcx, [rcx+18h]
0x1401fdfc9  call    WPP_RECORDER_AND_TRACE_SF_d
0x1401fdfce  mov     eax, r14d
0x1401fdfd1  add     rsp, 0B8h
0x1401fdfd8  pop     r15
0x1401fdfda  pop     r14
0x1401fdfdc  pop     r13
0x1401fdfde  pop     r12
0x1401fdfe0  pop     rdi
0x1401fdfe1  pop     rbx
0x1401fdfe2  retn
0x1401fdfe4  mov     r14d, 0C00000BBh
0x1401fdfea  mov     rcx, cs:WPP_GLOBAL_Control
0x1401fdff1  cmp     rcx, r13
0x1401fdff4  jz      short loc_1401FE005
0x1401fdff6  mov     eax, [rcx+2Ch]
0x1401fdff9  test    al, 1
0x1401fdffb  jz      short loc_1401FE005
0x1401fdffd  cmp     byte ptr [rcx+29h], 3
0x1401fe001  mov     bl, 1
0x1401fe003  jnb     short loc_1401FE008
0x1401fe005  mov     bl, dil
0x1401fe008  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1401fe00f  setnz   al
0x1401fe012  mov     [rsp+0E8h+var_98], al
0x1401fe016  test    bl, bl
0x1401fe018  jnz     short loc_1401FE022
0x1401fe01a  test    al, al
0x1401fe01c  jz      loc_1401FDF33
0x1401fe022  call    cs:__imp_W32GetUserSessionState
0x1401fe029  nop     dword ptr [rax+rax+00h]
0x1401fe02e  mov     r9, [rax+4BD0h]
0x1401fe035  lea     rax, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x1401fe03c  mov     [rsp+0E8h+var_B0], rax
0x1401fe041  mov     word ptr [rsp+0E8h+var_B8], 1Bh
0x1401fe048  mov     dword ptr [rsp+0E8h+var_C0], 1
0x1401fe050  mov     byte ptr [rsp+0E8h+var_C8], 3
0x1401fe055  mov     r8b, [rsp+0E8h+var_98]
0x1401fe05a  mov     dl, bl
0x1401fe05c  mov     rcx, cs:WPP_GLOBAL_Control
0x1401fe063  mov     rcx, [rcx+18h]
0x1401fe067  call    WPP_RECORDER_AND_TRACE_SF_
0x1401fe06c  jmp     loc_1401FDF33
0x1401fe071  mov     r14d, 0C00000BBh
0x1401fe077  mov     rcx, cs:WPP_GLOBAL_Control
0x1401fe07e  cmp     rcx, r13
0x1401fe081  jz      short loc_1401FE092
0x1401fe083  mov     eax, [rcx+2Ch]
0x1401fe086  test    al, 1
0x1401fe088  jz      short loc_1401FE092
0x1401fe08a  cmp     byte ptr [rcx+29h], 3
0x1401fe08e  mov     bl, 1
0x1401fe090  jnb     short loc_1401FE095
0x1401fe092  mov     bl, dil
0x1401fe095  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1401fe09c  setnz   al
0x1401fe09f  mov     [rsp+0E8h+var_98], al
0x1401fe0a3  test    bl, bl
0x1401fe0a5  jnz     short loc_1401FE0AF
0x1401fe0a7  test    al, al
0x1401fe0a9  jz      loc_1401FDF33
0x1401fe0af  call    cs:__imp_W32GetUserSessionState
0x1401fe0b6  nop     dword ptr [rax+rax+00h]
0x1401fe0bb  mov     r9, [rax+4BD0h]
0x1401fe0c2  lea     rax, WPP_7c08c368c6363bda2d3438b6e725b2d5_Traceguids
0x1401fe0c9  mov     [rsp+0E8h+var_B0], rax
0x1401fe0ce  mov     word ptr [rsp+0E8h+var_B8], 1Ch
0x1401fe0d5  jmp     loc_1401FE048
```
