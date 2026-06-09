# CCtlPlane::OnRequestCompleteFromDevice(long,ushort,void *,uint,uint)

- ea: `0x140024f60`
- end: `0x140025794`
- name: `?OnRequestCompleteFromDevice@CCtlPlane@@QEAAXJGPEAXII@Z`
- size: `2100`
- prototype: `void(CCtlPlane *__hidden this, int, unsigned __int16, void *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x14002ade0`

## callees

- `0x140003ea0`
- `0x140009420`
- `0x14000c778`
- `0x14000c940`
- `0x14000d054`
- `0x140021c0c`
- `0x140024f60`
- `0x140039b80`
- `0x1400dfd00`
- `0x1400dfd40`
- `0x1400dfe00`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x14002518a`
- `ntoskrnl!EtwWriteTransfer` at `0x140025312`
- `ntoskrnl!EtwWriteTransfer` at `0x14002547b`
- `ntoskrnl!EtwWriteTransfer` at `0x140025696`
- `ntoskrnl!EtwWriteTransfer` at `0x14002518a`
- `ntoskrnl!EtwWriteTransfer` at `0x140025312`
- `ntoskrnl!EtwWriteTransfer` at `0x14002547b`
- `ntoskrnl!EtwWriteTransfer` at `0x140025696`
- `NDIS!NdisConvertNtStatusToNdisStatus` at `0x1400251a6`
- `NDIS!NdisConvertNtStatusToNdisStatus` at `0x1400251a6`

## pseudocode

```c
void __fastcall CCtlPlane::OnRequestCompleteFromDevice(
        CCtlPlane *this,
        unsigned int a2,
        unsigned __int16 a3,
        const struct _WDI_MESSAGE_HEADER *a4,
        unsigned int Size,
        unsigned int a6)
{
  unsigned int v6; // ebx
  unsigned int v9; // r12d
  unsigned int v10; // r14d
  int v11; // r15d
  const char *v12; // rdi
  __int64 v13; // rbx
  int v14; // ebx
  const char *v15; // rdi
  __int64 v16; // rbx
  int v17; // ebx
  unsigned int v18; // eax
  __int64 v19; // rbx
  const char *v20; // rcx
  __int64 v21; // rax
  int v22; // eax
  _DWORD *v23; // rax
  _DWORD *v24; // r12
  int v25; // ecx
  const char *v26; // rax
  int v27; // ebx
  void (__fastcall *v28)(__int64, _QWORD, _DWORD *, CCtlPlane *); // rax
  __int64 v29; // rcx
  int UserDataCount; // [rsp+28h] [rbp-E0h]
  unsigned int v31; // [rsp+58h] [rbp-B0h] BYREF
  unsigned int TransactionId; // [rsp+5Ch] [rbp-ACh] BYREF
  unsigned int v33; // [rsp+60h] [rbp-A8h] BYREF
  unsigned int Status; // [rsp+64h] [rbp-A4h] BYREF
  unsigned int v35; // [rsp+68h] [rbp-A0h] BYREF
  unsigned int v36; // [rsp+6Ch] [rbp-9Ch] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+70h] [rbp-98h] BYREF
  struct _WDI_MESSAGE_HEADER *v38; // [rsp+80h] [rbp-88h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+88h] [rbp-80h] BYREF
  char *v40; // [rsp+98h] [rbp-70h]
  int v41; // [rsp+A0h] [rbp-68h]
  int v42; // [rsp+A4h] [rbp-64h]
  const char *v43; // [rsp+A8h] [rbp-60h]
  int v44; // [rsp+B0h] [rbp-58h]
  int v45; // [rsp+B4h] [rbp-54h]
  unsigned int *p_Status; // [rsp+B8h] [rbp-50h]
  __int64 v47; // [rsp+C0h] [rbp-48h]
  unsigned int *v48; // [rsp+C8h] [rbp-40h]
  __int64 v49; // [rsp+D0h] [rbp-38h]
  unsigned int *p_TransactionId; // [rsp+D8h] [rbp-30h]
  __int64 v51; // [rsp+E0h] [rbp-28h]
  unsigned int *v52; // [rsp+E8h] [rbp-20h]
  __int64 v53; // [rsp+F0h] [rbp-18h]

  v6 = a2;
  v9 = a3;
  LOWORD(v31) = a3;
  v36 = a2;
  v38 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      27,
      (__int64)WPP_2f30b4ad8bfd34f09d951cfde2e7a610_Traceguids);
  }
  *((_BYTE *)this + 16) = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_LdddD(
      WPP_GLOBAL_Control->DeviceExtension,
      v9,
      a3,
      (_DWORD)a4,
      UserDataCount,
      v9,
      v9,
      a4->PortId,
      a4->TransactionId,
      v6);
  if ( a4 != *((const struct _WDI_MESSAGE_HEADER **)this + 69) )
  {
    v38 = (struct _WDI_MESSAGE_HEADER *)a4;
    *((_BYTE *)this + 32) = 0;
  }
  v10 = Size;
  if ( Size >= 0x10 )
  {
    if ( v6 )
    {
      v11 = NdisConvertNtStatusToNdisStatus(v6);
      a4->Status = v11;
      v10 = 16;
    }
    else
    {
      v11 = 0;
    }
    CMessageHelper::LogMessage(3u, v9, *(_DWORD *)(*((_QWORD *)this + 1) + 5392LL), v10, a4);
    if ( *((_QWORD *)this + 68) )
    {
      v18 = v10 + 32;
      v19 = -1;
      if ( v10 + 32 < v10 )
      {
        v11 = -1073676267;
        if ( (unsigned int)dword_14010EC48 > 2 && (qword_14010EC58 & 5) != 0 && (qword_14010EC60 & 5) == qword_14010EC60 )
        {
          TransactionId = a4->TransactionId;
          LOWORD(v33) = a4->PortId;
          Status = v10;
          v20 = WDI_TLV::stringify::ToLogString(v9);
          v51 = 4;
          v49 = 2;
          p_TransactionId = &TransactionId;
          v47 = 4;
          v48 = &v33;
          p_Status = &Status;
          if ( v20 )
          {
            v21 = -1;
            do
              ++v21;
            while ( v20[v21] );
            v22 = v21 + 1;
          }
          else
          {
            v20 = (const char *)&qword_1400FC9C8;
            v22 = 1;
          }
          v44 = v22;
          *(_DWORD *)&EventDescriptor.Level = 2;
          UserData.Ptr = (ULONGLONG)off_14010EC50;
          v43 = v20;
          v45 = 0;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          EventDescriptor.Keyword = 5;
          UserData.Size = *(unsigned __int16 *)off_14010EC50;
          v40 = byte_14010411D;
          UserData.Reserved = 2;
          v41 = 108;
          v42 = 1;
          v35 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, &UserData);
        }
        v10 = 16;
        a4->Status = -1073676267;
        v18 = 48;
      }
      v23 = operator new(v18);
      v24 = v23;
      if ( v23 )
      {
        v23[2] &= 0xFFFFFFF8;
        v25 = (unsigned __int16)v31;
        v23[3] = 3;
        *((_QWORD *)v23 + 3) = 0;
        *(_QWORD *)v23 = *((_QWORD *)this + 72);
        v23[2] = *((_DWORD *)this + 146);
        *v23 = v25;
        v23[1] = v10;
        if ( v11 == -2147483643 || v11 == -1073676266 )
        {
          v11 = -2147483643;
          v23[6] = a6;
        }
        else if ( v11
               && (unsigned int)dword_14010EC48 > 2
               && (qword_14010EC58 & 5) != 0
               && (qword_14010EC60 & 5) == qword_14010EC60 )
        {
          v35 = a4->TransactionId;
          LOWORD(v31) = a4->PortId;
          Status = a4->Status;
          v26 = WDI_TLV::stringify::ToLogString(v25);
          v53 = 4;
          v52 = &v35;
          v51 = 2;
          p_TransactionId = &v31;
          v48 = &v36;
          p_Status = &Status;
          v49 = 4;
          v47 = 4;
          if ( v26 )
          {
            do
              ++v19;
            while ( v26[v19] );
            v27 = v19 + 1;
          }
          else
          {
            v26 = (const char *)&qword_1400FC9C8;
            v27 = 1;
          }
          v43 = v26;
          *(_DWORD *)&EventDescriptor.Level = 2;
          UserData.Ptr = (ULONGLONG)off_14010EC50;
          v45 = 0;
          v44 = v27;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          EventDescriptor.Keyword = 5;
          UserData.Size = *(unsigned __int16 *)off_14010EC50;
          v40 = (char *)&dword_14010409C;
          UserData.Reserved = 2;
          v41 = 117;
          v42 = 1;
          TransactionId = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 7u, &UserData);
        }
        v24[5] = v11;
        memmove(v24 + 8, a4, v10);
        v28 = (void (__fastcall *)(__int64, _QWORD, _DWORD *, CCtlPlane *))*((_QWORD *)this + 68);
        v29 = *((_QWORD *)this + 67);
        *((_QWORD *)this + 68) = 0;
        v28(v29, v10 + 32, v24, this);
      }
      else
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(a2) = 2;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            a2,
            1,
            29,
            (__int64)WPP_2f30b4ad8bfd34f09d951cfde2e7a610_Traceguids);
        }
        LOBYTE(v11) = -102;
      }
    }
    else if ( (unsigned int)dword_14010EC48 > 3
           && (qword_14010EC58 & 5) != 0
           && (qword_14010EC60 & 5) == qword_14010EC60 )
    {
      TransactionId = a4->TransactionId;
      LOWORD(v33) = a4->PortId;
      v15 = WDI_TLV::stringify::ToLogString(v9);
      v49 = 4;
      v47 = 2;
      v48 = &TransactionId;
      p_Status = &v33;
      if ( v15 )
      {
        v16 = -1;
        do
          ++v16;
        while ( v15[v16] );
        v17 = v16 + 1;
      }
      else
      {
        v15 = (const char *)&qword_1400FC9C8;
        v17 = 1;
      }
      *(_DWORD *)&EventDescriptor.Level = 3;
      UserData.Ptr = (ULONGLONG)off_14010EC50;
      v45 = 0;
      v43 = v15;
      v44 = v17;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 5;
      UserData.Size = *(unsigned __int16 *)off_14010EC50;
      v40 = byte_140104195;
      UserData.Reserved = 2;
      v41 = 82;
      v42 = 1;
      v31 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
    }
  }
  else
  {
    LOBYTE(v11) = 13;
    if ( (unsigned int)dword_14010EC48 > 2 && (qword_14010EC58 & 5) != 0 && (qword_14010EC60 & 5) == qword_14010EC60 )
    {
      v31 = v6;
      v33 = Size;
      v12 = WDI_TLV::stringify::ToLogString(v9);
      v49 = 4;
      v47 = 4;
      v48 = &v31;
      p_Status = &v33;
      if ( v12 )
      {
        v13 = -1;
        do
          ++v13;
        while ( v12[v13] );
        v14 = v13 + 1;
      }
      else
      {
        v12 = (const char *)&qword_1400FC9C8;
        v14 = 1;
      }
      *(_DWORD *)&EventDescriptor.Level = 2;
      UserData.Ptr = (ULONGLONG)off_14010EC50;
      v45 = 0;
      v43 = v12;
      v44 = v14;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 5;
      UserData.Size = *(unsigned __int16 *)off_14010EC50;
      v40 = byte_1401041F3;
      UserData.Reserved = 2;
      v41 = 100;
      v42 = 1;
      TransactionId = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EtwWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 5u, &UserData);
    }
  }
  if ( v38 )
    operator delete(v38);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      30,
      (__int64)WPP_2f30b4ad8bfd34f09d951cfde2e7a610_Traceguids,
      v11);
  }
}

```

## disassembly

```asm
0x140024f60  mov     r11, rsp
0x140024f63  push    rbp
0x140024f64  push    rbx
0x140024f65  lea     rbp, [r11-48h]
0x140024f69  sub     rsp, 138h
0x140024f70  mov     rax, cs:__security_cookie
0x140024f77  xor     rax, rsp
0x140024f7a  mov     [rbp+40h+var_50], rax
0x140024f7e  mov     [r11-18h], rsi
0x140024f82  mov     ebx, edx
0x140024f84  mov     [r11-20h], rdi
0x140024f88  mov     rsi, r9
0x140024f8b  mov     [r11-28h], r12
0x140024f8f  mov     [r11-30h], r13
0x140024f93  mov     r13, rcx
0x140024f96  movzx   r12d, r8w
0x140024f9a  mov     word ptr [rsp+140h+var_F0], r12w
0x140024fa0  mov     [r11-38h], r14
0x140024fa4  mov     [rsp+140h+var_DC], edx
0x140024fa8  mov     [rsp+140h+var_C8], 0
0x140024fb1  lea     rdi, WPP_RECORDER_INITIALIZED
0x140024fb8  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140024fbf  lea     rax, WPP_2f30b4ad8bfd34f09d951cfde2e7a610_Traceguids
0x140024fc6  jz      short loc_140024FF8
0x140024fc8  mov     rcx, cs:WPP_GLOBAL_Control
0x140024fcf  cmp     byte ptr [rcx+29h], 5
0x140024fd3  jnb     short loc_140024FDC
0x140024fd5  cmp     word ptr [rcx+48h], 0
0x140024fda  jz      short loc_140024FF8
0x140024fdc  mov     rcx, [rcx+40h]
0x140024fe0  mov     r9d, 1Bh
0x140024fe6  mov     r8d, 1
0x140024fec  mov     qword ptr [rsp+140h+UserDataCount], rax
0x140024ff1  mov     dl, 5
0x140024ff3  call    WPP_RECORDER_SF_
0x140024ff8  mov     byte ptr [r13+10h], 0
0x140024ffd  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140025004  jz      short loc_140025033
0x140025006  movzx   ecx, word ptr [rsi]
0x140025009  mov     edx, r12d
0x14002500c  mov     eax, [rsi+8]
0x14002500f  mov     [rsp+140h+var_F8], ebx
0x140025013  mov     [rsp+140h+var_100], eax
0x140025017  mov     [rsp+140h+var_108], ecx
0x14002501b  mov     rcx, cs:WPP_GLOBAL_Control
0x140025022  mov     [rsp+140h+var_110], edx
0x140025026  mov     dword ptr [rsp+140h+UserData], edx
0x14002502a  mov     rcx, [rcx+40h]
0x14002502e  call    WPP_RECORDER_SF_LdddD
0x140025033  cmp     rsi, [r13+228h]
0x14002503a  jz      short loc_140025046
0x14002503c  mov     [rsp+140h+var_C8], rsi
0x140025041  mov     byte ptr [r13+20h], 0
0x140025046  mov     r14d, dword ptr [rbp+40h+Size]
0x14002504a  mov     [rsp+140h+var_38], r15
0x140025052  cmp     r14d, 10h
0x140025056  jnb     loc_14002519B
0x14002505c  mov     eax, cs:dword_14010EC48
0x140025062  mov     r15d, 0C000000Dh
0x140025068  cmp     eax, 2
0x14002506b  jbe     loc_1400256F6
0x140025071  mov     rcx, cs:qword_14010EC60
0x140025078  mov     rax, cs:qword_14010EC58
0x14002507f  test    al, 5
0x140025081  jz      loc_1400256F6
0x140025087  mov     rax, rcx
0x14002508a  and     eax, 5
0x14002508d  cmp     rax, rcx
0x140025090  jnz     loc_1400256F6
0x140025096  movzx   ecx, r12w
0x14002509a  mov     [rsp+140h+var_F0], ebx
0x14002509e  mov     [rsp+140h+var_E8], r14d
0x1400250a3  call    ?ToLogString@stringify@WDI_TLV@@YAPEBDW4MESSAGE_ID@ENUMS@2@@Z; WDI_TLV::stringify::ToLogString(WDI_TLV::ENUMS::MESSAGE_ID)
0x1400250a8  mov     rdi, rax
0x1400250ab  mov     [rbp+40h+var_78], 4
0x1400250b3  lea     rax, [rsp+140h+var_F0]
0x1400250b8  mov     [rbp+40h+var_88], 4
0x1400250c0  mov     [rbp+40h+var_80], rax
0x1400250c4  xor     ecx, ecx
0x1400250c6  lea     rax, [rsp+140h+var_E8]
0x1400250cb  mov     [rbp+40h+var_90], rax
0x1400250cf  test    rdi, rdi
0x1400250d2  jz      short loc_1400250EC
0x1400250d4  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1400250db  nop     dword ptr [rax+rax+00h]
0x1400250e0  inc     rbx
0x1400250e3  cmp     [rdi+rbx], cl
0x1400250e6  jnz     short loc_1400250E0
0x1400250e8  inc     ebx
0x1400250ea  jmp     short loc_1400250F8
0x1400250ec  lea     rdi, qword_1400FC9C8
0x1400250f3  mov     ebx, 1
0x1400250f8  movzx   eax, cs:word_1401041E9
0x1400250ff  lea     rdx, [rsp+140h+EventDescriptor]; EventDescriptor
0x140025104  mov     dword ptr [rsp+140h+EventDescriptor.Level], eax
0x140025108  xor     r9d, r9d; RelatedActivityId
0x14002510b  mov     rax, cs:off_14010EC50
0x140025112  xor     r8d, r8d; ActivityId
0x140025115  mov     [rbp+40h+var_C0.Ptr], rax
0x140025119  mov     [rbp+40h+var_94], ecx
0x14002511c  lea     rcx, _TraceLoggingMetadata
0x140025123  mov     [rbp+40h+var_A0], rdi
0x140025127  mov     [rbp+40h+var_98], ebx
0x14002512a  mov     dword ptr [rsp+140h+EventDescriptor.Id], 0B000000h
0x140025132  mov     [rsp+140h+EventDescriptor.Keyword], 5
0x14002513b  movzx   eax, word ptr [rax]
0x14002513e  mov     [rbp+40h+var_C0.Size], eax
0x140025141  lea     rax, byte_1401041F3
0x140025148  mov     [rbp+40h+var_B0], rax
0x14002514c  lea     rax, _TraceLoggingMetadataEnd
0x140025153  sub     eax, ecx
0x140025155  mov     dword ptr [rbp+40h+var_C0.0Ch], 2
0x14002515c  mov     [rbp+40h+var_A8], 64h ; 'd'
0x140025163  mov     [rbp+40h+var_A4], 1
0x14002516a  mov     [rsp+140h+var_EC], eax
0x14002516e  mov     eax, [rsp+140h+var_EC]
0x140025172  mov     rcx, cs:RegHandle; RegHandle
0x140025179  lea     rax, [rbp+40h+var_C0]
0x14002517d  mov     [rsp+140h+UserData], rax; UserData
0x140025182  mov     [rsp+140h+UserDataCount], 5; UserDataCount
0x14002518a  call    cs:__imp_EtwWriteTransfer
0x140025191  nop     dword ptr [rax+rax+00h]
0x140025196  jmp     loc_1400256EF
0x14002519b  test    ebx, ebx
0x14002519d  jnz     short loc_1400251A4
0x14002519f  xor     r15d, r15d
0x1400251a2  jmp     short loc_1400251BE
0x1400251a4  mov     ecx, ebx
0x1400251a6  call    cs:__imp_NdisConvertNtStatusToNdisStatus
0x1400251ad  nop     dword ptr [rax+rax+00h]
0x1400251b2  mov     r15d, eax
0x1400251b5  mov     [rsi+4], eax
0x1400251b8  mov     r14d, 10h
0x1400251be  mov     r8, [r13+8]
0x1400251c2  mov     edx, r12d; unsigned int
0x1400251c5  mov     r9d, r14d; unsigned int
0x1400251c8  mov     qword ptr [rsp+140h+UserDataCount], rsi; struct _WDI_MESSAGE_HEADER *
0x1400251cd  mov     cl, 3; unsigned __int8
0x1400251cf  mov     r8d, [r8+1510h]; unsigned int
0x1400251d6  call    ?LogMessage@CMessageHelper@@SAXEKKKPEBU_WDI_MESSAGE_HEADER@@@Z; CMessageHelper::LogMessage(uchar,ulong,ulong,ulong,_WDI_MESSAGE_HEADER const *)
0x1400251db  cmp     qword ptr [r13+220h], 0
0x1400251e3  jnz     loc_140025323
0x1400251e9  mov     eax, cs:dword_14010EC48
0x1400251ef  cmp     eax, 3
0x1400251f2  jbe     loc_1400256F6
0x1400251f8  mov     rcx, cs:qword_14010EC60
0x1400251ff  mov     rax, cs:qword_14010EC58
0x140025206  test    al, 5
0x140025208  jz      loc_1400256F6
0x14002520e  mov     rax, rcx
0x140025211  and     eax, 5
0x140025214  cmp     rax, rcx
0x140025217  jnz     loc_1400256F6
0x14002521d  mov     eax, [rsi+8]
0x140025220  movzx   ecx, r12w
0x140025224  mov     [rsp+140h+var_EC], eax
0x140025228  movzx   eax, word ptr [rsi]
0x14002522b  mov     word ptr [rsp+140h+var_E8], ax
0x140025230  call    ?ToLogString@stringify@WDI_TLV@@YAPEBDW4MESSAGE_ID@ENUMS@2@@Z; WDI_TLV::stringify::ToLogString(WDI_TLV::ENUMS::MESSAGE_ID)
0x140025235  mov     rdi, rax
0x140025238  mov     [rbp+40h+var_78], 4
0x140025240  lea     rax, [rsp+140h+var_EC]
0x140025245  mov     [rbp+40h+var_88], 2
0x14002524d  mov     [rbp+40h+var_80], rax
0x140025251  xor     ecx, ecx
0x140025253  lea     rax, [rsp+140h+var_E8]
0x140025258  mov     [rbp+40h+var_90], rax
0x14002525c  test    rdi, rdi
0x14002525f  jz      short loc_140025274
0x140025261  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x140025268  inc     rbx
0x14002526b  cmp     [rdi+rbx], cl
0x14002526e  jnz     short loc_140025268
0x140025270  inc     ebx
0x140025272  jmp     short loc_140025280
0x140025274  lea     rdi, qword_1400FC9C8
0x14002527b  mov     ebx, 1
0x140025280  movzx   eax, cs:word_14010418B
0x140025287  lea     rdx, [rsp+140h+EventDescriptor]; EventDescriptor
0x14002528c  mov     dword ptr [rsp+140h+EventDescriptor.Level], eax
0x140025290  xor     r9d, r9d; RelatedActivityId
0x140025293  mov     rax, cs:off_14010EC50
0x14002529a  xor     r8d, r8d; ActivityId
0x14002529d  mov     [rbp+40h+var_C0.Ptr], rax
0x1400252a1  mov     [rbp+40h+var_94], ecx
0x1400252a4  lea     rcx, _TraceLoggingMetadata
0x1400252ab  mov     [rbp+40h+var_A0], rdi
0x1400252af  mov     [rbp+40h+var_98], ebx
0x1400252b2  mov     dword ptr [rsp+140h+EventDescriptor.Id], 0B000000h
0x1400252ba  mov     [rsp+140h+EventDescriptor.Keyword], 5
0x1400252c3  movzx   eax, word ptr [rax]
0x1400252c6  mov     [rbp+40h+var_C0.Size], eax
0x1400252c9  lea     rax, byte_140104195
0x1400252d0  mov     [rbp+40h+var_B0], rax
0x1400252d4  lea     rax, _TraceLoggingMetadataEnd
0x1400252db  sub     eax, ecx
0x1400252dd  mov     dword ptr [rbp+40h+var_C0.0Ch], 2
0x1400252e4  mov     [rbp+40h+var_A8], 52h ; 'R'
0x1400252eb  mov     [rbp+40h+var_A4], 1
0x1400252f2  mov     [rsp+140h+var_F0], eax
0x1400252f6  mov     eax, [rsp+140h+var_F0]
0x1400252fa  mov     rcx, cs:RegHandle; RegHandle
0x140025301  lea     rax, [rbp+40h+var_C0]
0x140025305  mov     [rsp+140h+UserData], rax; UserData
0x14002530a  mov     [rsp+140h+UserDataCount], 5; UserDataCount
0x140025312  call    cs:__imp_EtwWriteTransfer
0x140025319  nop     dword ptr [rax+rax+00h]
0x14002531e  jmp     loc_1400256EF
0x140025323  lea     eax, [r14+20h]
0x140025327  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x14002532e  lea     rdi, qword_1400FC9C8
0x140025335  cmp     eax, r14d
0x140025338  jnb     loc_140025496
0x14002533e  mov     eax, cs:dword_14010EC48
0x140025344  mov     r15d, 0C0010015h
0x14002534a  cmp     eax, 2
0x14002534d  jbe     loc_140025487
0x140025353  mov     rcx, cs:qword_14010EC60
0x14002535a  mov     rax, cs:qword_14010EC58
0x140025361  test    al, 5
0x140025363  jz      loc_140025487
0x140025369  mov     rax, rcx
0x14002536c  and     eax, 5
0x14002536f  cmp     rax, rcx
0x140025372  jnz     loc_140025487
0x140025378  mov     eax, [rsi+8]
0x14002537b  movzx   ecx, r12w
0x14002537f  mov     [rsp+140h+var_EC], eax
0x140025383  movzx   eax, word ptr [rsi]
0x140025386  mov     word ptr [rsp+140h+var_E8], ax
0x14002538b  mov     [rsp+140h+var_E4], r14d
0x140025390  call    ?ToLogString@stringify@WDI_TLV@@YAPEBDW4MESSAGE_ID@ENUMS@2@@Z; WDI_TLV::stringify::ToLogString(WDI_TLV::ENUMS::MESSAGE_ID)
0x140025395  mov     rcx, rax
0x140025398  mov     [rbp+40h+var_68], 4
0x1400253a0  lea     rax, [rsp+140h+var_EC]
0x1400253a5  mov     [rbp+40h+var_78], 2
0x1400253ad  mov     [rbp+40h+var_70], rax
0x1400253b1  xor     edx, edx
0x1400253b3  mov     [rbp+40h+var_88], 4
0x1400253bb  lea     rax, [rsp+140h+var_E8]
0x1400253c0  mov     [rbp+40h+var_80], rax
0x1400253c4  lea     rax, [rsp+140h+var_E4]
0x1400253c9  mov     [rbp+40h+var_90], rax
0x1400253cd  test    rcx, rcx
0x1400253d0  jz      short loc_1400253E1
0x1400253d2  mov     rax, rbx
0x1400253d5  inc     rax
0x1400253d8  cmp     [rcx+rax], dl
0x1400253db  jnz     short loc_1400253D5
0x1400253dd  inc     eax
0x1400253df  jmp     short loc_1400253E9
0x1400253e1  mov     rcx, rdi
0x1400253e4  mov     eax, 1
0x1400253e9  mov     [rbp+40h+var_98], eax
0x1400253ec  xor     r9d, r9d; RelatedActivityId
0x1400253ef  movzx   eax, cs:word_140104113
0x1400253f6  xor     r8d, r8d; ActivityId
0x1400253f9  mov     dword ptr [rsp+140h+EventDescriptor.Level], eax
0x1400253fd  mov     rax, cs:off_14010EC50
0x140025404  mov     [rbp+40h+var_C0.Ptr], rax
0x140025408  mov     [rbp+40h+var_A0], rcx
0x14002540c  lea     rcx, _TraceLoggingMetadata
0x140025413  mov     [rbp+40h+var_94], edx
0x140025416  lea     rdx, [rsp+140h+EventDescriptor]; EventDescriptor
0x14002541b  mov     dword ptr [rsp+140h+EventDescriptor.Id], 0B000000h
0x140025423  mov     [rsp+140h+EventDescriptor.Keyword], 5
0x14002542c  movzx   eax, word ptr [rax]
0x14002542f  mov     [rbp+40h+var_C0.Size], eax
0x140025432  lea     rax, byte_14010411D
0x140025439  mov     [rbp+40h+var_B0], rax
0x14002543d  lea     rax, _TraceLoggingMetadataEnd
0x140025444  sub     eax, ecx
0x140025446  mov     dword ptr [rbp+40h+var_C0.0Ch], 2
0x14002544d  mov     [rbp+40h+var_A8], 6Ch ; 'l'
0x140025454  mov     [rbp+40h+var_A4], 1
0x14002545b  mov     [rsp+140h+var_E0], eax
0x14002545f  mov     eax, [rsp+140h+var_E0]
0x140025463  mov     rcx, cs:RegHandle; RegHandle
0x14002546a  lea     rax, [rbp+40h+var_C0]
0x14002546e  mov     [rsp+140h+UserData], rax; UserData
0x140025473  mov     [rsp+140h+UserDataCount], 6; UserDataCount
0x14002547b  call    cs:__imp_EtwWriteTransfer
0x140025482  nop     dword ptr [rax+rax+00h]
0x140025487  mov     r14d, 10h
0x14002548d  mov     [rsi+4], r15d
0x140025491  mov     eax, 30h ; '0'
0x140025496  mov     ecx, eax; unsigned __int64
0x140025498  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002549d  mov     r12, rax
0x1400254a0  test    rax, rax
0x1400254a3  jnz     short loc_1400254EA
0x1400254a5  lea     rdi, WPP_RECORDER_INITIALIZED
0x1400254ac  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x1400254b3  lea     rbx, WPP_2f30b4ad8bfd34f09d951cfde2e7a610_Traceguids
0x1400254ba  jz      short loc_1400254DF
0x1400254bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400254c3  mov     r9d, 1Dh
0x1400254c9  mov     r8d, 1
0x1400254cf  mov     qword ptr [rsp+140h+UserDataCount], rbx
0x1400254d4  mov     dl, 2
  ... truncated ...
```
