# PrjfEnumerateDirectoryWithMerge

- ea: `0x140024b24`
- end: `0x14002572d`
- name: `PrjfEnumerateDirectoryWithMerge`
- size: `3081`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1400280f0`
- `0x14002a6b4`

## callees

- `0x140001008`
- `0x140002d9c`
- `0x140006938`
- `0x14000b1a0`
- `0x14000ba20`
- `0x14000bb80`
- `0x14000d128`
- `0x14000d5e8`
- `0x140024b24`
- `0x140025734`
- `0x140025a78`
- `0x140028464`
- `0x140028760`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400256b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400256b5`
- `ntoskrnl!KeSetEvent` at `0x14002569b`
- `ntoskrnl!KeSetEvent` at `0x14002569b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140024f1b`
- `ntoskrnl!KeWaitForSingleObject` at `0x140024f1b`
- `ntoskrnl!RtlInitUnicodeString` at `0x140024bc1`
- `ntoskrnl!RtlInitUnicodeString` at `0x140024bc1`
- `FLTMGR!FltReleaseContext` at `0x1400256c9`
- `FLTMGR!FltReleaseContext` at `0x1400256e1`
- `FLTMGR!FltReleaseContext` at `0x1400256f7`
- `FLTMGR!FltReleaseContext` at `0x1400256c9`
- `FLTMGR!FltReleaseContext` at `0x1400256e1`
- `FLTMGR!FltReleaseContext` at `0x1400256f7`

## pseudocode

```c
__int64 __fastcall PrjfEnumerateDirectoryWithMerge(
        __int64 a1,
        struct _FLT_INSTANCE *a2,
        struct _FILE_OBJECT *a3,
        int a4,
        __int64 a5,
        int a6,
        char a7,
        char a8,
        unsigned int a9,
        __int64 a10,
        _DWORD *a11)
{
  int v14; // edi
  int v15; // ecx
  _DWORD *v16; // r10
  unsigned int v17; // edx
  unsigned int v18; // esi
  int v19; // ebx
  unsigned int v20; // r8d
  int v21; // r12d
  PFLT_CONTEXT v22; // r15
  char v23; // r14
  char v24; // al
  int v25; // edx
  int v26; // r8d
  __int64 v27; // rcx
  int v28; // eax
  unsigned int v29; // r14d
  int v30; // r14d
  int v31; // eax
  int v32; // ecx
  char v33; // r14
  __int64 v34; // rcx
  int v35; // eax
  int v36; // edx
  unsigned int v37; // eax
  unsigned int v38; // r14d
  int v39; // edx
  int v40; // r8d
  char v42; // [rsp+60h] [rbp-A0h] BYREF
  PFLT_CONTEXT v43; // [rsp+68h] [rbp-98h] BYREF
  char v44; // [rsp+70h] [rbp-90h]
  int v45; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v46; // [rsp+78h] [rbp-88h]
  PFLT_CONTEXT Context; // [rsp+80h] [rbp-80h]
  int v48; // [rsp+88h] [rbp-78h]
  unsigned int Size; // [rsp+8Ch] [rbp-74h] BYREF
  int Size_4; // [rsp+90h] [rbp-70h]
  void *Src; // [rsp+98h] [rbp-68h] BYREF
  __int64 v52; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v53; // [rsp+A8h] [rbp-58h] BYREF
  void *v54[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v55; // [rsp+C0h] [rbp-40h]
  PFLT_CONTEXT v56; // [rsp+C8h] [rbp-38h]
  struct _FILE_OBJECT *v57; // [rsp+D0h] [rbp-30h]
  struct _FLT_INSTANCE *v58; // [rsp+D8h] [rbp-28h]
  _DWORD *v59; // [rsp+E0h] [rbp-20h]
  struct _UNICODE_STRING DestinationString; // [rsp+E8h] [rbp-18h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v61; // [rsp+100h] [rbp+0h] BYREF
  char *v62; // [rsp+120h] [rbp+20h]
  __int64 v63; // [rsp+128h] [rbp+28h]
  __int64 *v64; // [rsp+130h] [rbp+30h]
  __int64 v65; // [rsp+138h] [rbp+38h]
  __int64 *v66; // [rsp+140h] [rbp+40h]
  __int64 v67; // [rsp+148h] [rbp+48h]

  v55 = a5;
  v53 = a10;
  v14 = 0;
  v43 = 0;
  v56 = 0;
  Context = 0;
  v45 = 0;
  v44 = 0;
  Src = 0;
  Size = 0;
  v54[1] = v54;
  v58 = a2;
  v52 = a1;
  v54[0] = v54;
  v57 = a3;
  v59 = a11;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, 0);
  if ( !(unsigned __int8)PrjfGetContextFileObjectEx(a2, a3, &v43) || (v16 = v43) == 0 )
  {
    MicrosoftTelemetryAssertTriggeredMsgKM("*Unexpected* trying to merge without file or stream handle context");
    if ( (BYTE10(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v39) = BYTE10(xmmword_14001A3D0) & 4;
      LOBYTE(v40) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sDL(
        786,
        v39,
        v40,
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        3,
        18,
        24,
        (__int64)WPP_c75e01ab741b3118f5a23fa3d9fd3c1c_Traceguids,
        (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\dir.c",
        217,
        a4);
    }
    *a11 = 0;
    goto LABEL_139;
  }
  if ( a4 > 38 )
  {
    v19 = 60;
    v15 = a4 - 60;
    if ( a4 == 60 )
    {
      v18 = 88;
    }
    else
    {
      v15 = a4 - 63;
      if ( a4 == 63 )
      {
        v18 = 114;
        v19 = 63;
      }
      else
      {
        v15 = a4 - 78;
        if ( a4 == 78 )
          goto LABEL_18;
        v15 = a4 - 79;
        if ( a4 != 79 )
        {
          v15 = a4 - 80;
          if ( a4 == 80 )
          {
            v17 = 96;
            v18 = 96;
            v19 = 80;
          }
          else
          {
            v15 = a4 - 81;
            if ( a4 != 81 )
              goto LABEL_25;
            v17 = 122;
            v18 = 122;
            v19 = 81;
          }
          goto LABEL_32;
        }
        v18 = 106;
        v19 = 79;
      }
    }
    v17 = v18;
    goto LABEL_32;
  }
  if ( a4 == 38 )
  {
LABEL_18:
    v18 = 80;
    v17 = 80;
    v19 = 78;
    goto LABEL_32;
  }
  v15 = a4 - 1;
  if ( a4 == 1 )
  {
    v17 = 64;
    goto LABEL_17;
  }
  v15 = a4 - 2;
  if ( a4 == 2 )
  {
    v17 = 68;
LABEL_17:
    v18 = 88;
    v19 = 60;
    goto LABEL_32;
  }
  v15 = a4 - 3;
  if ( a4 == 3 )
  {
    v17 = 94;
    v18 = 114;
    v19 = 63;
  }
  else if ( a4 == 12 )
  {
    v15 = (int)v56;
    v17 = 12;
    v18 = *((_BYTE *)v56 + 44) != 0 ? 88 : 12;
    v19 = *((_BYTE *)v56 + 44) != 0 ? 60 : 12;
  }
  else
  {
    v15 = a4 - 33;
    if ( a4 != 33 )
    {
      v15 = a4 - 37;
      if ( a4 == 37 )
      {
        v17 = 104;
        v18 = 106;
        v19 = 79;
        goto LABEL_32;
      }
LABEL_25:
      v14 = -1073741811;
      goto LABEL_139;
    }
    v17 = 16;
    v18 = 16;
    v19 = 33;
  }
LABEL_32:
  if ( a9 < v17 )
  {
    v14 = -1073741820;
    goto LABEL_139;
  }
  LOBYTE(v15) = 0;
  v20 = 0;
  v48 = v15;
  v21 = 0;
  v46 = 0;
  if ( a4 != 33 )
    v18 += 510;
  if ( a9 >= v18 )
  {
    v18 = a9;
    if ( a9 > 0x10014 )
      v18 = 65556;
  }
  v22 = Context;
  if ( !Context || *((_DWORD *)Context + 16) == 3 || a4 == 33 )
  {
    v33 = a7;
    v42 = a7;
    if ( (a7 & 1) != 0 )
    {
      *((_DWORD *)v43 + 22) = 0;
      *((_DWORD *)v43 + 153) = 0;
      *((_DWORD *)v43 + 10) |= 8u;
      v16 = v43;
    }
    else if ( (*((_DWORD *)v43 + 10) & 8) != 0 && *((_DWORD *)v43 + 22) && !*((_DWORD *)v43 + 153) )
    {
      v33 = a7 | 1;
      v42 = a7 | 1;
    }
    Size_4 = a6;
    while ( 1 )
    {
      if ( (_BYTE)v15 || v20 >= a9 )
        goto LABEL_74;
      PrjfFreeEnumContexts(v54);
      v14 = PrjfPrepareEnumerationContexts(v54, (int)v58, (int)v57, v18, v19, v33, *((_DWORD *)v43 + 153), 0);
      if ( v14 < 0 )
      {
        LOBYTE(v26) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        LOBYTE(v25) = BYTE2(xmmword_14001A3D0) & 4;
        if ( (BYTE2(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_84;
        goto LABEL_139;
      }
      v14 = PrjfEnumerateLayeredDirectories(v52, v54, v55, (char *)v43 + 92, *((_DWORD *)v43 + 153), Size_4, 0);
      if ( v14 < 0 )
      {
        LOBYTE(v26) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        LOBYTE(v25) = BYTE2(xmmword_14001A3D0) & 4;
        if ( (BYTE2(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_84;
        goto LABEL_139;
      }
      v35 = PrjfMergeEnumerationResults(v34, (__int64 *)v54, a4, a9, v53, a8, &v45, &Src, &Size);
      v14 = v35;
      if ( v35 == -2147483642 )
        break;
      v25 = -1073741809;
      if ( v35 == -1073741809 )
        break;
      if ( v35 == -2147483643 )
      {
        v36 = v45;
        *((_DWORD *)v43 + 22) += v45;
        *((_DWORD *)v43 + 10) |= 8u;
LABEL_122:
        v20 = v46;
        goto LABEL_123;
      }
      if ( v35 < 0 )
      {
        LOBYTE(v26) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        LOBYTE(v25) = BYTE2(xmmword_14001A3D0) & 4;
        if ( (BYTE2(xmmword_14001A3D0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
LABEL_84:
          WPP_RECORDER_AND_TRACE_SF_sDdd(530, v25, v26, *((_QWORD *)WPP_GLOBAL_Control + 8));
LABEL_139:
        v22 = Context;
        goto LABEL_140;
      }
      if ( v19 == 33 )
      {
        v20 = v45 + v46;
        v37 = a9 - (v45 + v46);
        v15 = (unsigned __int8)v48;
        v46 += v45;
        if ( v37 < 0x10 )
          v15 = 1;
        v48 = v15;
        if ( (v33 & 2) != 0 )
        {
          v15 = (unsigned __int8)v15;
          if ( v20 )
            v15 = 1;
          v48 = v15;
        }
        v16 = v43;
        v33 &= 0xFAu;
        v42 = v33;
        v55 = 0;
        Size_4 = 0;
      }
      else
      {
        v38 = Size;
        if ( Size )
          memmove((char *)v43 + 92, Src, Size);
        v15 = v45;
        v36 = v45;
        v20 = v46;
        *((_DWORD *)v43 + 153) = v38;
        v33 = v42;
        if ( v15 )
        {
          v20 += v15;
          v46 = v20;
          *((_DWORD *)v43 + 22) += v15;
LABEL_123:
          LOBYTE(v15) = 1;
          goto LABEL_124;
        }
        v33 = v42 & 0xFE;
        v42 &= ~1u;
LABEL_124:
        v16 = v43;
        v21 += v36;
        v48 = v15;
        if ( v14 < 0 )
          goto LABEL_74;
      }
    }
    v36 = v45;
    goto LABEL_122;
  }
  v23 = a7;
  v42 = a7;
  if ( (a7 & 4) == 0 )
  {
    if ( (a7 & 1) != 0 )
    {
      *((_DWORD *)v43 + 22) = 0;
      *((_DWORD *)v43 + 153) = 0;
      *((_DWORD *)v43 + 10) |= 8u;
      *((_DWORD *)v43 + 10) &= ~0x20u;
      v16 = v43;
    }
    else if ( (*((_DWORD *)v43 + 10) & 8) != 0 && *((_DWORD *)v43 + 22) && !*((_DWORD *)v43 + 153) )
    {
      v23 = a7 | 1;
      v42 = a7 | 1;
    }
    KeWaitForSingleObject(v16 + 4, Executive, 0, 0, 0);
    v16 = v43;
    v44 = 1;
    if ( (*((_DWORD *)v43 + 10) & 0x20) != 0 )
    {
      v14 = -2147483642;
    }
    else
    {
      v24 = v48;
      while ( !v24 && v46 < a9 )
      {
        v14 = PrjfPrepareEnumerationContexts(v16, (int)v58, (int)v57, v18, v19, v23, v16[153], (__int64)(v16 + 14));
        if ( v14 < 0 )
        {
          LOBYTE(v26) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          LOBYTE(v25) = BYTE2(xmmword_14001A3D0) & 4;
          if ( (BYTE2(xmmword_14001A3D0) & 4) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_139;
          goto LABEL_84;
        }
        v14 = PrjfEnumerateLayeredDirectories(v52, v43, v55, (char *)v43 + 92, *((_DWORD *)v43 + 153), a6, v43);
        if ( v14 < 0 )
        {
          LOBYTE(v26) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          LOBYTE(v25) = BYTE2(xmmword_14001A3D0) & 4;
          if ( (BYTE2(xmmword_14001A3D0) & 4) == 0 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            goto LABEL_139;
          goto LABEL_84;
        }
        v28 = PrjfMergeEnumerationResults(v27, (__int64 *)v43, a4, a9, v53, a8, &v45, &Src, &Size);
        v14 = v28;
        v25 = -1073741809;
        if ( v28 == -2147483642 || v28 == -1073741809 )
        {
          v21 += v45;
          v24 = 1;
          v16 = v43;
          if ( v14 < 0 )
            break;
        }
        else
        {
          if ( v28 == -2147483643 )
          {
            v32 = v45;
            *((_DWORD *)v43 + 22) += v45;
            *((_DWORD *)v43 + 10) |= 8u;
            v16 = v43;
            v21 += v32;
            break;
          }
          if ( v28 < 0 )
          {
            LOBYTE(v26) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
            LOBYTE(v25) = BYTE2(xmmword_14001A3D0) & 4;
            if ( (BYTE2(xmmword_14001A3D0) & 4) == 0
              && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              goto LABEL_139;
            }
            goto LABEL_84;
          }
          v29 = Size;
          if ( Size )
            memmove((char *)v43 + 92, Src, Size);
          *((_DWORD *)v43 + 153) = v29;
          v30 = v45;
          if ( v45 )
          {
            v46 += v45;
            *((_DWORD *)v43 + 22) += v45;
            v24 = 1;
            v16 = v43;
            v21 += v30;
            v23 = v42;
          }
          else
          {
            v16 = v43;
            if ( (*((_DWORD *)v43 + 10) & 0x20) != 0 )
            {
              v14 = -1073741809;
              v21 += v45;
              break;
            }
            PrjfResetEnumContexts(v43, (unsigned int)v14);
            v42 &= ~1u;
            v24 = 0;
            v16 = v43;
            v21 += v30;
            v23 = v42;
          }
        }
      }
LABEL_74:
      v31 = v16[10];
      if ( (v31 & 0x10) != 0 && v14 != -2147483643 )
      {
        if ( v14 == -2147483642 && !v16[22] )
          v14 = -1073741809;
        v16[10] = v31 & 0xFFFFFFEF;
      }
      *v59 = v21;
    }
    goto LABEL_139;
  }
  v14 = -1073741637;
  if ( (BYTE2(xmmword_14001A3E0) & 4) != 0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v17) = BYTE2(xmmword_14001A3E0) & 4;
    LOBYTE(v20) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sDL(
      1042,
      v17,
      v20,
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      4,
      18,
      28,
      (__int64)WPP_c75e01ab741b3118f5a23fa3d9fd3c1c_Traceguids,
      (__int64)"onecore\\base\\fs\\gvflt\\filter\\sys\\dir.c",
      56,
      187);
  }
  if ( (unsigned int)dword_14001A068 > 5
    && (qword_14001A078 & 0x400000000000LL) != 0
    && (qword_14001A080 & 0x400000000000LL) == qword_14001A080 )
  {
    v42 = 4;
    v62 = &v42;
    v63 = 1;
    v64 = &v53;
    v53 = 4;
    v66 = &v52;
    v65 = 8;
    v52 = 0x1000000;
    v67 = 8;
    tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_14001A068, (unsigned __int8 *)&byte_1400164A7, 0, 0, 5u, &v61);
    goto LABEL_139;
  }
LABEL_140:
  PrjfFreeEnumContexts(v54);
  if ( v44 )
  {
    PrjfResetEnumContexts(v43, (unsigned int)v14);
    KeSetEvent((PRKEVENT)((char *)v43 + 16), 0, 0);
  }
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0x6E664A50u);
  if ( v22 )
    FltReleaseContext(v22);
  if ( v56 )
    FltReleaseContext(v56);
  if ( v43 )
    FltReleaseContext(v43);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x140024b24  mov     [rsp-8+arg_18], rbx
0x140024b29  push    rbp
0x140024b2a  push    rsi
0x140024b2b  push    rdi
0x140024b2c  push    r12
0x140024b2e  push    r13
0x140024b30  push    r14
0x140024b32  push    r15
0x140024b34  lea     rbp, [rsp-60h]
0x140024b39  sub     rsp, 160h
0x140024b40  mov     rax, cs:__security_cookie
0x140024b47  xor     rax, rsp
0x140024b4a  mov     [rbp+90h+var_40], rax
0x140024b4e  mov     rax, [rbp+90h+arg_20]
0x140024b55  mov     rsi, rdx
0x140024b58  mov     rbx, [rbp+90h+arg_50]
0x140024b5f  xorps   xmm0, xmm0
0x140024b62  mov     [rbp+90h+var_D0], rax
0x140024b66  mov     r13d, r9d
0x140024b69  mov     rax, [rbp+90h+arg_48]
0x140024b70  mov     r14, r8
0x140024b73  mov     [rbp+90h+var_E8], rax
0x140024b77  xor     eax, eax
0x140024b79  mov     edi, eax
0x140024b7b  mov     [rsp+190h+var_128], rax
0x140024b80  mov     [rbp+90h+var_C8], rax
0x140024b84  mov     [rbp+90h+Context], rax
0x140024b88  mov     [rsp+190h+var_11C], eax
0x140024b8c  mov     [rsp+190h+var_120], al
0x140024b90  mov     [rbp+90h+Src], rax
0x140024b94  mov     dword ptr [rbp+90h+Size], eax
0x140024b97  lea     rax, [rbp+90h+var_E0]
0x140024b9b  mov     [rbp+90h+var_D8], rax
0x140024b9f  lea     rax, [rbp+90h+var_E0]
0x140024ba3  mov     [rbp+90h+var_B8], rdx
0x140024ba7  xor     edx, edx; SourceString
0x140024ba9  mov     [rbp+90h+var_F0], rcx
0x140024bad  lea     rcx, [rbp+90h+DestinationString]; DestinationString
0x140024bb1  mov     [rbp+90h+var_E0], rax
0x140024bb5  mov     [rbp+90h+var_C0], r8
0x140024bb9  mov     [rbp+90h+var_B0], rbx
0x140024bbd  movups  xmmword ptr [rbp+90h+DestinationString.Length], xmm0
0x140024bc1  call    cs:__imp_RtlInitUnicodeString
0x140024bc8  nop     dword ptr [rax+rax+00h]
0x140024bcd  lea     rax, [rsp+190h+var_128]
0x140024bd2  mov     rdx, r14; FileObject
0x140024bd5  lea     r9, [rbp+90h+var_C8]
0x140024bd9  mov     [rsp+190h+Timeout], rax; Context
0x140024bde  lea     r8, [rbp+90h+Context]
0x140024be2  mov     rcx, rsi; Instance
0x140024be5  call    PrjfGetContextFileObjectEx
0x140024bea  test    al, al
0x140024bec  jz      loc_1400255EF
0x140024bf2  mov     r10, [rsp+190h+var_128]
0x140024bf7  test    r10, r10
0x140024bfa  jz      loc_1400255EF
0x140024c00  mov     r8d, 10h
0x140024c06  cmp     r13d, 26h ; '&'
0x140024c0a  jg      loc_140024CB2
0x140024c10  jz      loc_140024CA4
0x140024c16  mov     ecx, r13d
0x140024c19  sub     ecx, 1
0x140024c1c  jz      short loc_140024C95
0x140024c1e  sub     ecx, 1
0x140024c21  jz      short loc_140024C8E
0x140024c23  sub     ecx, 1
0x140024c26  jz      short loc_140024C7E
0x140024c28  sub     ecx, 9
0x140024c2b  jz      short loc_140024C59
0x140024c2d  sub     ecx, 15h
0x140024c30  jz      short loc_140024C49
0x140024c32  sub     ecx, 4
0x140024c35  jnz     loc_140024CD7
0x140024c3b  lea     edx, [rcx+68h]
0x140024c3e  lea     esi, [rcx+6Ah]
0x140024c41  lea     ebx, [rcx+4Fh]
0x140024c44  jmp     loc_140024D14
0x140024c49  mov     edx, r8d
0x140024c4c  mov     esi, r8d
0x140024c4f  mov     ebx, 21h ; '!'
0x140024c54  jmp     loc_140024D14
0x140024c59  mov     rcx, [rbp+90h+var_C8]
0x140024c5d  mov     edx, 0Ch
0x140024c62  mov     cl, [rcx+2Ch]
0x140024c65  mov     al, cl
0x140024c67  neg     al
0x140024c69  sbb     esi, esi
0x140024c6b  and     esi, 4Ch
0x140024c6e  add     esi, edx
0x140024c70  neg     cl
0x140024c72  sbb     ebx, ebx
0x140024c74  and     ebx, 30h
0x140024c77  add     ebx, edx
0x140024c79  jmp     loc_140024D14
0x140024c7e  mov     edx, 5Eh ; '^'
0x140024c83  lea     esi, [rdx+14h]
0x140024c86  lea     ebx, [rdx-1Fh]
0x140024c89  jmp     loc_140024D14
0x140024c8e  mov     edx, 44h ; 'D'
0x140024c93  jmp     short loc_140024C9A
0x140024c95  mov     edx, 40h ; '@'
0x140024c9a  mov     esi, 58h ; 'X'
0x140024c9f  lea     ebx, [rsi-1Ch]
0x140024ca2  jmp     short loc_140024D14
0x140024ca4  mov     ebx, 50h ; 'P'
0x140024ca9  mov     esi, ebx
0x140024cab  mov     edx, ebx
0x140024cad  lea     ebx, [rsi-2]
0x140024cb0  jmp     short loc_140024D14
0x140024cb2  mov     ecx, r13d
0x140024cb5  mov     ebx, 3Ch ; '<'
0x140024cba  sub     ecx, ebx
0x140024cbc  jz      short loc_140024D0D
0x140024cbe  sub     ecx, 3
0x140024cc1  jz      short loc_140024D03
0x140024cc3  sub     ecx, 0Fh
0x140024cc6  jz      short loc_140024CA4
0x140024cc8  sub     ecx, 1
0x140024ccb  jz      short loc_140024CF9
0x140024ccd  sub     ecx, 1
0x140024cd0  jz      short loc_140024CED
0x140024cd2  sub     ecx, 1
0x140024cd5  jz      short loc_140024CE1
0x140024cd7  mov     edi, 0C000000Dh
0x140024cdc  jmp     loc_14002566D
0x140024ce1  mov     edx, 7Ah ; 'z'
0x140024ce6  mov     esi, edx
0x140024ce8  lea     ebx, [rdx-29h]
0x140024ceb  jmp     short loc_140024D14
0x140024ced  mov     edx, 60h ; '`'
0x140024cf2  mov     esi, edx
0x140024cf4  lea     ebx, [rdx-10h]
0x140024cf7  jmp     short loc_140024D14
0x140024cf9  mov     esi, 6Ah ; 'j'
0x140024cfe  lea     ebx, [rsi-1Bh]
0x140024d01  jmp     short loc_140024D12
0x140024d03  mov     esi, 72h ; 'r'
0x140024d08  lea     ebx, [rsi-33h]
0x140024d0b  jmp     short loc_140024D12
0x140024d0d  mov     esi, 58h ; 'X'
0x140024d12  mov     edx, esi
0x140024d14  cmp     [rbp+90h+arg_40], edx
0x140024d1a  jnb     short loc_140024D26
0x140024d1c  mov     edi, 0C0000004h
0x140024d21  jmp     loc_14002566D
0x140024d26  xor     cl, cl
0x140024d28  lea     eax, [rsi+1FEh]
0x140024d2e  xor     r8d, r8d; WaitMode
0x140024d31  mov     [rbp+90h+var_108], ecx
0x140024d34  xor     r12d, r12d
0x140024d37  mov     [rsp+190h+var_118], r8d
0x140024d3c  cmp     r13d, 21h ; '!'
0x140024d40  cmovnz  esi, eax
0x140024d43  cmp     [rbp+90h+arg_40], esi
0x140024d49  jb      short loc_140024D5B
0x140024d4b  mov     esi, [rbp+90h+arg_40]
0x140024d51  mov     eax, 10014h
0x140024d56  cmp     esi, eax
0x140024d58  cmova   esi, eax
0x140024d5b  mov     r15, [rbp+90h+Context]
0x140024d5f  test    r15, r15
0x140024d62  jz      loc_140025275
0x140024d68  cmp     dword ptr [r15+40h], 3
0x140024d6d  jz      loc_140025275
0x140024d73  cmp     r13d, 21h ; '!'
0x140024d77  jz      loc_140025275
0x140024d7d  mov     r14b, [rbp+90h+arg_30]
0x140024d84  mov     [rsp+190h+var_130], r14b
0x140024d89  test    r14b, 4
0x140024d8d  jz      loc_140024EBB
0x140024d93  mov     edi, 0C00000BBh
0x140024d98  mov     dl, byte ptr cs:xmmword_14001A3E0+2
0x140024d9e  lea     rax, WPP_RECORDER_INITIALIZED
0x140024da5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140024dac  setnz   r8b
0x140024db0  and     dl, 4
0x140024db3  jnz     short loc_140024DBA
0x140024db5  test    r8b, r8b
0x140024db8  jz      short loc_140024E07
0x140024dba  mov     r9, cs:WPP_GLOBAL_Control
0x140024dc1  lea     rax, aOnecoreBaseFsG_3; "onecore\\base\\fs\\gvflt\\filter\\sys\\"...
0x140024dc8  mov     [rsp+190h+var_140], edi
0x140024dcc  mov     ecx, 412h
0x140024dd1  mov     [rsp+190h+var_148], 0E38h
0x140024dd9  mov     [rsp+190h+var_150], rax
0x140024dde  lea     rax, WPP_c75e01ab741b3118f5a23fa3d9fd3c1c_Traceguids
0x140024de5  mov     r9, [r9+40h]
0x140024de9  mov     [rsp+190h+var_158], rax
0x140024dee  mov     word ptr [rsp+190h+var_160], 1Ch
0x140024df5  mov     dword ptr [rsp+190h+var_168], 12h
0x140024dfd  mov     byte ptr [rsp+190h+Timeout], 4
0x140024e02  call    WPP_RECORDER_AND_TRACE_SF_sDL
0x140024e07  mov     eax, cs:dword_14001A068
0x140024e0d  cmp     eax, 5
0x140024e10  jbe     loc_140025671
0x140024e16  mov     rcx, cs:qword_14001A080
0x140024e1d  mov     rdx, 400000000000h
0x140024e27  mov     rax, cs:qword_14001A078
0x140024e2e  test    rdx, rax
0x140024e31  jz      loc_140025671
0x140024e37  mov     rax, rcx
0x140024e3a  and     rax, rdx
0x140024e3d  cmp     rax, rcx
0x140024e40  jnz     loc_140025671
0x140024e46  lea     rax, [rsp+190h+var_130]
0x140024e4b  mov     [rsp+190h+var_130], 4
0x140024e50  mov     [rbp+90h+var_70], rax
0x140024e54  lea     rdx, byte_1400164A7
0x140024e5b  lea     rax, [rbp+90h+var_E8]
0x140024e5f  mov     [rbp+90h+var_68], 1
0x140024e67  mov     [rbp+90h+var_60], rax
0x140024e6b  lea     rcx, dword_14001A068
0x140024e72  lea     rax, [rbp+90h+var_F0]
0x140024e76  mov     [rbp+90h+var_E8], 4
0x140024e7e  mov     [rbp+90h+var_50], rax
0x140024e82  xor     r9d, r9d
0x140024e85  lea     rax, [rbp+90h+var_90]
0x140024e89  mov     [rbp+90h+var_58], 8
0x140024e91  mov     [rsp+190h+var_168], rax
0x140024e96  xor     r8d, r8d
0x140024e99  mov     dword ptr [rsp+190h+Timeout], 5
0x140024ea1  mov     [rbp+90h+var_F0], 1000000h
0x140024ea9  mov     [rbp+90h+var_48], 8
0x140024eb1  call    _tlgWriteTransfer_EtwWriteTransfer
0x140024eb6  jmp     loc_14002566D
0x140024ebb  mov     r15d, 1
0x140024ec1  test    r15b, r14b
0x140024ec4  jz      short loc_140024EEE
0x140024ec6  mov     [r10+58h], edi
0x140024eca  mov     rax, [rsp+190h+var_128]
0x140024ecf  mov     [rax+264h], edi
0x140024ed5  mov     rax, [rsp+190h+var_128]
0x140024eda  or      dword ptr [rax+28h], 8
0x140024ede  mov     rax, [rsp+190h+var_128]
0x140024ee3  and     dword ptr [rax+28h], 0FFFFFFDFh
0x140024ee7  mov     r10, [rsp+190h+var_128]
0x140024eec  jmp     short loc_140024F0D
0x140024eee  mov     eax, [r10+28h]
0x140024ef2  test    al, 8
0x140024ef4  jz      short loc_140024F0D
0x140024ef6  cmp     [r10+58h], edi
0x140024efa  jbe     short loc_140024F0D
0x140024efc  cmp     [r10+264h], edi
0x140024f03  jnz     short loc_140024F0D
0x140024f05  or      r14b, r15b
0x140024f08  mov     [rsp+190h+var_130], r14b
0x140024f0d  lea     rcx, [r10+10h]; Object
0x140024f11  mov     [rsp+190h+Timeout], rdi; Timeout
0x140024f16  xor     r9d, r9d; Alertable
0x140024f19  xor     edx, edx; WaitReason
0x140024f1b  call    cs:__imp_KeWaitForSingleObject
0x140024f22  nop     dword ptr [rax+rax+00h]
0x140024f27  mov     r10, [rsp+190h+var_128]
0x140024f2c  mov     [rsp+190h+var_120], r15b
0x140024f31  mov     eax, [r10+28h]
0x140024f35  test    al, 20h
0x140024f37  jz      short loc_140024F43
0x140024f39  mov     edi, 80000006h
0x140024f3e  jmp     loc_14002566D
0x140024f43  mov     eax, [rbp+90h+var_108]
0x140024f46  mov     edx, 0C000000Fh
0x140024f4b  test    al, al
0x140024f4d  jnz     loc_1400250EB
0x140024f53  mov     eax, [rsp+190h+var_118]
0x140024f57  cmp     eax, [rbp+90h+arg_40]
0x140024f5d  jnb     loc_1400250EB
0x140024f63  mov     r8, [rbp+90h+var_C0]
0x140024f67  lea     rax, [r10+38h]
0x140024f6b  mov     rdx, [rbp+90h+var_B8]
0x140024f6f  mov     r9d, esi
0x140024f72  mov     [rsp+190h+var_158], rax
0x140024f77  mov     rcx, r10
0x140024f7a  mov     eax, [r10+264h]
0x140024f81  mov     dword ptr [rsp+190h+var_160], eax
0x140024f85  mov     byte ptr [rsp+190h+var_168], r14b
0x140024f8a  mov     dword ptr [rsp+190h+Timeout], ebx
0x140024f8e  call    PrjfPrepareEnumerationContexts
0x140024f93  mov     edi, eax
0x140024f95  test    eax, eax
0x140024f97  js      loc_14002521A
0x140024f9d  mov     rdx, [rsp+190h+var_128]
0x140024fa2  mov     eax, [rbp+90h+arg_28]
0x140024fa8  mov     r8, [rbp+90h+var_D0]
0x140024fac  mov     rcx, [rbp+90h+var_F0]
0x140024fb0  mov     [rsp+190h+var_160], rdx
0x140024fb5  lea     r9, [rdx+5Ch]
0x140024fb9  mov     dword ptr [rsp+190h+var_168], eax
0x140024fbd  mov     eax, [rdx+264h]
0x140024fc3  mov     dword ptr [rsp+190h+Timeout], eax
0x140024fc7  call    PrjfEnumerateLayeredDirectories
0x140024fcc  mov     edi, eax
0x140024fce  test    eax, eax
0x140024fd0  js      loc_1400251BF
0x140024fd6  mov     r9d, [rbp+90h+arg_40]
0x140024fdd  lea     rax, [rbp+90h+Size]
0x140024fe1  mov     rdx, [rsp+190h+var_128]
0x140024fe6  mov     r8d, r13d
0x140024fe9  mov     [rsp+190h+var_150], rax
0x140024fee  lea     rax, [rbp+90h+Src]
0x140024ff2  mov     [rsp+190h+var_158], rax
  ... truncated ...
```
