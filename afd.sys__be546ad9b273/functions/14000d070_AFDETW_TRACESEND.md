# AFDETW_TRACESEND

- ea: `0x14000d070`
- end: `0x14000d49c`
- name: `AFDETW_TRACESEND`
- size: `1068`
- prototype: `int __fastcall(int, int, __int64, int, int, __int64, int, int, __int64)`
- caller_count: `13`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x140005bf0`
- `0x140005ddc`
- `0x140005fb0`
- `0x14000c0d0`
- `0x14000ce60`
- `0x140012338`
- `0x140013590`
- `0x14001f120`
- `0x14002b8b0`
- `0x14002cb90`
- `0x140054800`
- `0x140054990`
- `0x14006bd68`

## callees

- `0x14000d070`
- `0x140072840`

## import_xrefs

- `ntoskrnl!EtwWriteTransfer` at `0x14000d3c7`
- `ntoskrnl!EtwWriteTransfer` at `0x14000d3c7`
- `ntoskrnl!IoGetCurrentProcess` at `0x14000d48b`
- `ntoskrnl!IoGetCurrentProcess` at `0x14000d48b`
- `ntoskrnl!EtwWrite` at `0x14000d280`
- `ntoskrnl!EtwWrite` at `0x14000d306`
- `ntoskrnl!EtwWrite` at `0x14000d43c`
- `ntoskrnl!EtwWrite` at `0x14000d280`
- `ntoskrnl!EtwWrite` at `0x14000d306`
- `ntoskrnl!EtwWrite` at `0x14000d43c`

## pseudocode

```c
int __fastcall AFDETW_TRACESEND(int a1, int a2, __int64 a3, int a4, int a5, __int64 a6, int a7, int a8, __int64 a9)
{
  int result; // eax
  __int64 v14; // rcx
  PEPROCESS v15; // rax
  int v16; // [rsp+30h] [rbp-D0h] BYREF
  int v17; // [rsp+38h] [rbp-C8h] BYREF
  int v18; // [rsp+40h] [rbp-C0h] BYREF
  int v19; // [rsp+48h] [rbp-B8h] BYREF
  int v20; // [rsp+50h] [rbp-B0h] BYREF
  PEPROCESS v21; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v22; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v23; // [rsp+68h] [rbp-98h] BYREF
  GUID v24; // [rsp+70h] [rbp-90h] BYREF
  GUID RelatedActivityId; // [rsp+80h] [rbp-80h] BYREF
  GUID ActivityId; // [rsp+90h] [rbp-70h] BYREF
  int *v27; // [rsp+A0h] [rbp-60h]
  __int64 v28; // [rsp+A8h] [rbp-58h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+B0h] [rbp-50h] BYREF
  int *v30; // [rsp+C0h] [rbp-40h]
  __int64 v31; // [rsp+C8h] [rbp-38h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+D0h] [rbp-30h] BYREF
  int *v33; // [rsp+E0h] [rbp-20h]
  __int64 v34; // [rsp+E8h] [rbp-18h]
  PEPROCESS *v35; // [rsp+F0h] [rbp-10h]
  __int64 v36; // [rsp+F8h] [rbp-8h]
  __int64 *v37; // [rsp+100h] [rbp+0h]
  __int64 v38; // [rsp+108h] [rbp+8h]
  int *v39; // [rsp+110h] [rbp+10h]
  __int64 v40; // [rsp+118h] [rbp+18h]
  __int64 *v41; // [rsp+120h] [rbp+20h]
  __int64 v42; // [rsp+128h] [rbp+28h]
  int *v43; // [rsp+130h] [rbp+30h]
  __int64 v44; // [rsp+138h] [rbp+38h]
  int *v45; // [rsp+140h] [rbp+40h]
  __int64 v46; // [rsp+148h] [rbp+48h]

  RelatedActivityId = 0;
  v24 = 0;
  if ( g_AfdEtwTraceEnable || Microsoft_Windows_Networking_CorrelationEnabled )
  {
    *(_QWORD *)RelatedActivityId.Data4 = 0;
    *(_QWORD *)&RelatedActivityId.Data1 = a3;
    *(_QWORD *)v24.Data4 = 0;
    *(_QWORD *)&v24.Data1 = a9;
    if ( !a1 )
    {
      if ( Microsoft_Windows_Networking_CorrelationEnabled )
      {
        v16 = 2;
        if ( Microsoft_Windows_Networking_CorrelationTraceActivityPayload )
        {
          *(_QWORD *)&ActivityId.Data1 = &Microsoft_Windows_Networking_ProviderId;
          v27 = &v16;
          *(_QWORD *)ActivityId.Data4 = 16;
          v28 = 4;
          EtwWrite(
            Microsoft_Windows_Networking_CorrelationHandle,
            &ActivityStart,
            &v24,
            2u,
            (PEVENT_DATA_DESCRIPTOR)&ActivityId);
        }
        else
        {
          EtwWrite(Microsoft_Windows_Networking_CorrelationHandle, &ActivityStart, &v24, 0, 0);
        }
      }
      if ( Microsoft_Windows_Networking_CorrelationEnabled )
      {
        *(_QWORD *)&ActivityId.Data1 = ActivityTransfer;
        v16 = 2;
        *(_QWORD *)ActivityId.Data4 = 0x8000000000000001uLL;
        if ( Microsoft_Windows_Networking_CorrelationTraceActivityPayload )
        {
          *(_QWORD *)&EventDescriptor.Id = &Microsoft_Windows_Networking_ProviderId;
          v30 = &v16;
          EventDescriptor.Keyword = 16;
          v31 = 4;
          EtwWriteTransfer(
            Microsoft_Windows_Networking_CorrelationHandle,
            (PCEVENT_DESCRIPTOR)&ActivityId,
            &v24,
            &RelatedActivityId,
            2u,
            (PEVENT_DATA_DESCRIPTOR)&EventDescriptor);
        }
        else
        {
          EtwWriteTransfer(
            Microsoft_Windows_Networking_CorrelationHandle,
            (PCEVENT_DESCRIPTOR)&ActivityId,
            &v24,
            &RelatedActivityId,
            0,
            0);
        }
      }
    }
  }
  if ( g_AfdEtwTraceEnable )
  {
    v14 = 0;
    *(_DWORD *)&EventDescriptor.Id = AFD_EVENT_SEND;
    *(_WORD *)&EventDescriptor.Opcode = -5364;
    HIBYTE(EventDescriptor.Task) = 3;
    if ( a3 )
    {
      LOBYTE(v14) = *(_WORD *)a3 != 0xAFD1;
      ++v14;
    }
    v22 = a3;
    v18 = a2;
    v16 = a1;
    v21 = 0;
    *(_QWORD *)ActivityId.Data4 = 0;
    EventDescriptor.Keyword = v14 | (a4 != 0 ? 0x10 : 0) | 0x8000000000000004uLL;
    v17 = a8;
    EventDescriptor.Level = ((a8 >> 31) & 0xFE) + 4;
    v20 = a7;
    v23 = a6;
    v19 = a5;
    *(_QWORD *)&ActivityId.Data1 = a9 ? a9 : a3;
    v15 = a3 ? *(PEPROCESS *)(a3 + 48) : IoGetCurrentProcess();
    v21 = v15;
    *(_QWORD *)&UserData.Size = 4;
    UserData.Ptr = (ULONGLONG)&v16;
    v34 = 4;
    v33 = &v18;
    v35 = &v21;
    v37 = &v22;
    v39 = &v19;
    v41 = &v23;
    v43 = &v20;
    v45 = &v17;
    v36 = 8;
    v38 = 8;
    v40 = 4;
    v42 = 8;
    v44 = 4;
    v46 = 4;
    result = EtwWrite(g_AfdEtwHandle, &EventDescriptor, &ActivityId, 8u, &UserData);
    if ( g_AfdEtwTraceEnable )
      goto LABEL_34;
  }
  result = Microsoft_Windows_Networking_CorrelationEnabled;
  if ( Microsoft_Windows_Networking_CorrelationEnabled )
  {
LABEL_34:
    if ( a1 == 1 )
    {
      result = Microsoft_Windows_Networking_CorrelationEnabled;
      if ( Microsoft_Windows_Networking_CorrelationEnabled )
      {
        v17 = 2;
        if ( Microsoft_Windows_Networking_CorrelationTraceActivityPayload )
        {
          *(_QWORD *)&ActivityId.Data1 = &Microsoft_Windows_Networking_ProviderId;
          v27 = &v17;
          *(_QWORD *)ActivityId.Data4 = 16;
          v28 = 4;
          return EtwWrite(
                   Microsoft_Windows_Networking_CorrelationHandle,
                   &ActivityStop,
                   &v24,
                   2u,
                   (PEVENT_DATA_DESCRIPTOR)&ActivityId);
        }
        else
        {
          return EtwWrite(Microsoft_Windows_Networking_CorrelationHandle, &ActivityStop, &v24, 0, 0);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000d070  mov     [rsp-8+arg_0], rbx
0x14000d075  mov     [rsp-8+arg_8], rsi
0x14000d07a  push    rbp
0x14000d07b  push    rdi
0x14000d07c  push    r12
0x14000d07e  push    r14
0x14000d080  push    r15
0x14000d082  lea     rbp, [rsp-60h]
0x14000d087  sub     rsp, 160h
0x14000d08e  mov     rax, cs:__security_cookie
0x14000d095  xor     rax, rsp
0x14000d098  mov     [rbp+80h+var_30], rax
0x14000d09c  cmp     cs:g_AfdEtwTraceEnable, 0
0x14000d0a3  lea     r12, Microsoft_Windows_Networking_ProviderId
0x14000d0aa  mov     rdi, [rbp+80h+arg_40]
0x14000d0b1  xorps   xmm0, xmm0
0x14000d0b4  xorps   xmm1, xmm1
0x14000d0b7  mov     esi, r9d
0x14000d0ba  movups  xmmword ptr [rbp+80h+RelatedActivityId.Data1], xmm0
0x14000d0be  mov     rbx, r8
0x14000d0c1  mov     r14d, edx
0x14000d0c4  movups  xmmword ptr [rsp+180h+var_110.Data1], xmm1
0x14000d0c9  mov     r15d, ecx
0x14000d0cc  jnz     loc_14000D317
0x14000d0d2  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14000d0d8  test    eax, eax
0x14000d0da  jnz     loc_14000D317
0x14000d0e0  cmp     cs:g_AfdEtwTraceEnable, 0
0x14000d0e7  jnz     short loc_14000D120
0x14000d0e9  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14000d0ef  test    eax, eax
0x14000d0f1  jnz     loc_14000D299
0x14000d0f7  mov     rcx, [rbp+80h+var_30]
0x14000d0fb  xor     rcx, rsp; StackCookie
0x14000d0fe  call    __security_check_cookie
0x14000d103  lea     r11, [rsp+180h+var_20]
0x14000d10b  mov     rbx, [r11+30h]
0x14000d10f  mov     rsi, [r11+38h]
0x14000d113  mov     rsp, r11
0x14000d116  pop     r15
0x14000d118  pop     r14
0x14000d11a  pop     r12
0x14000d11c  pop     rdi
0x14000d11d  pop     rbp
0x14000d11e  retn
0x14000d120  mov     eax, cs:AFD_EVENT_SEND
0x14000d126  xor     ecx, ecx
0x14000d128  mov     dword ptr [rbp+80h+EventDescriptor.Id], eax
0x14000d12b  movzx   eax, cs:word_14007DA7D
0x14000d132  mov     word ptr [rbp+80h+EventDescriptor.Opcode], ax
0x14000d136  movzx   eax, cs:byte_14007DA7F
0x14000d13d  mov     byte ptr [rbp+80h+EventDescriptor.Task+1], al
0x14000d140  test    rbx, rbx
0x14000d143  jnz     loc_14000D3D8
0x14000d149  neg     esi
0x14000d14b  mov     [rsp+180h+var_120], rbx
0x14000d150  mov     [rsp+180h+var_140], r14d
0x14000d155  sbb     rax, rax
0x14000d158  mov     [rsp+180h+var_150], r15d
0x14000d15d  and     eax, 10h
0x14000d160  mov     [rsp+180h+var_128], 0
0x14000d169  or      rax, rcx
0x14000d16c  mov     qword ptr [rbp+80h+ActivityId.Data4], 0
0x14000d174  mov     rcx, 8000000000000004h
0x14000d17e  or      rax, rcx
0x14000d181  mov     ecx, [rbp+80h+arg_38]
0x14000d187  mov     [rbp+80h+EventDescriptor.Keyword], rax
0x14000d18b  mov     eax, ecx
0x14000d18d  sar     eax, 1Fh
0x14000d190  and     al, 0FEh
0x14000d192  mov     [rsp+180h+var_148], ecx
0x14000d196  add     al, 4
0x14000d198  mov     [rbp+80h+EventDescriptor.Level], al
0x14000d19b  mov     eax, [rbp+80h+arg_30]
0x14000d1a1  mov     [rsp+180h+var_130], eax
0x14000d1a5  mov     rax, [rbp+80h+arg_28]
0x14000d1ac  mov     [rsp+180h+var_118], rax
0x14000d1b1  mov     eax, [rbp+80h+arg_20]
0x14000d1b7  mov     [rsp+180h+var_138], eax
0x14000d1bb  test    rdi, rdi
0x14000d1be  jz      loc_14000D482
0x14000d1c4  mov     qword ptr [rbp+80h+ActivityId.Data1], rdi
0x14000d1c8  test    rbx, rbx
0x14000d1cb  jz      loc_14000D48B
0x14000d1d1  mov     rax, [rbx+30h]
0x14000d1d5  mov     rcx, cs:g_AfdEtwHandle; RegHandle
0x14000d1dc  lea     r8, [rbp+80h+ActivityId]; ActivityId
0x14000d1e0  mov     [rsp+180h+var_128], rax
0x14000d1e5  lea     rdx, [rbp+80h+EventDescriptor]; EventDescriptor
0x14000d1e9  lea     rax, [rsp+180h+var_150]
0x14000d1ee  mov     qword ptr [rbp+80h+var_B0.Size], 4
0x14000d1f6  mov     [rbp+80h+var_B0.Ptr], rax
0x14000d1fa  mov     r9d, 8; UserDataCount
0x14000d200  lea     rax, [rsp+180h+var_140]
0x14000d205  mov     [rbp+80h+var_98], 4
0x14000d20d  mov     [rbp+80h+var_A0], rax
0x14000d211  lea     rax, [rsp+180h+var_128]
0x14000d216  mov     [rbp+80h+var_90], rax
0x14000d21a  lea     rax, [rsp+180h+var_120]
0x14000d21f  mov     [rbp+80h+var_80], rax
0x14000d223  lea     rax, [rsp+180h+var_138]
0x14000d228  mov     [rbp+80h+var_70], rax
0x14000d22c  lea     rax, [rsp+180h+var_118]
0x14000d231  mov     [rbp+80h+var_60], rax
0x14000d235  lea     rax, [rsp+180h+var_130]
0x14000d23a  mov     [rbp+80h+var_50], rax
0x14000d23e  lea     rax, [rsp+180h+var_148]
0x14000d243  mov     [rbp+80h+var_40], rax
0x14000d247  lea     rax, [rbp+80h+var_B0]
0x14000d24b  mov     [rsp+180h+UserData], rax; UserData
0x14000d250  mov     [rbp+80h+var_88], 8
0x14000d258  mov     [rbp+80h+var_78], 8
0x14000d260  mov     [rbp+80h+var_68], 4
0x14000d268  mov     [rbp+80h+var_58], 8
0x14000d270  mov     [rbp+80h+var_48], 4
0x14000d278  mov     [rbp+80h+var_38], 4
0x14000d280  call    cs:__imp_EtwWrite
0x14000d287  nop     dword ptr [rax+rax+00h]
0x14000d28c  cmp     cs:g_AfdEtwTraceEnable, 0
0x14000d293  jz      loc_14000D0E9
0x14000d299  cmp     r15d, 1
0x14000d29d  jnz     loc_14000D0F7
0x14000d2a3  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14000d2a9  test    eax, eax
0x14000d2ab  jz      loc_14000D0F7
0x14000d2b1  mov     eax, cs:Microsoft_Windows_Networking_CorrelationTraceActivityPayload
0x14000d2b7  lea     r8, [rsp+180h+var_110]; ActivityId
0x14000d2bc  mov     rcx, cs:Microsoft_Windows_Networking_CorrelationHandle; RegHandle
0x14000d2c3  lea     rdx, ActivityStop; EventDescriptor
0x14000d2ca  mov     [rsp+180h+var_148], 2
0x14000d2d2  test    eax, eax
0x14000d2d4  jz      loc_14000D471
0x14000d2da  lea     rax, [rsp+180h+var_148]
0x14000d2df  mov     qword ptr [rbp+80h+ActivityId.Data1], r12
0x14000d2e3  mov     [rbp+80h+var_E0], rax
0x14000d2e7  mov     r9d, 2; UserDataCount
0x14000d2ed  lea     rax, [rbp+80h+ActivityId]
0x14000d2f1  mov     qword ptr [rbp+80h+ActivityId.Data4], 10h
0x14000d2f9  mov     [rsp+180h+UserData], rax; UserData
0x14000d2fe  mov     [rbp+80h+var_D8], 4
0x14000d306  call    cs:__imp_EtwWrite
0x14000d30d  nop     dword ptr [rax+rax+00h]
0x14000d312  jmp     loc_14000D0F7
0x14000d317  mov     qword ptr [rbp+80h+RelatedActivityId.Data4], 0
0x14000d31f  mov     qword ptr [rbp+80h+RelatedActivityId.Data1], rbx
0x14000d323  mov     qword ptr [rsp+180h+var_110.Data4], 0
0x14000d32c  mov     qword ptr [rsp+180h+var_110.Data1], rdi
0x14000d331  test    r15d, r15d
0x14000d334  jnz     loc_14000D0E0
0x14000d33a  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14000d340  test    eax, eax
0x14000d342  jnz     loc_14000D3EB
0x14000d348  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14000d34e  test    eax, eax
0x14000d350  jz      loc_14000D0E0
0x14000d356  mov     rax, cs:ActivityTransfer
0x14000d35d  lea     r9, [rbp+80h+RelatedActivityId]; RelatedActivityId
0x14000d361  mov     rcx, cs:Microsoft_Windows_Networking_CorrelationHandle; RegHandle
0x14000d368  lea     r8, [rsp+180h+var_110]; ActivityId
0x14000d36d  mov     qword ptr [rbp+80h+ActivityId.Data1], rax
0x14000d371  lea     rdx, [rbp+80h+ActivityId]; EventDescriptor
0x14000d375  mov     rax, 8000000000000001h
0x14000d37f  mov     [rsp+180h+var_150], 2
0x14000d387  mov     qword ptr [rbp+80h+ActivityId.Data4], rax
0x14000d38b  mov     eax, cs:Microsoft_Windows_Networking_CorrelationTraceActivityPayload
0x14000d391  test    eax, eax
0x14000d393  jz      loc_14000D45B
0x14000d399  lea     rax, [rsp+180h+var_150]
0x14000d39e  mov     qword ptr [rbp+80h+EventDescriptor.Id], r12
0x14000d3a2  mov     [rbp+80h+var_C0], rax
0x14000d3a6  lea     rax, [rbp+80h+EventDescriptor]
0x14000d3aa  mov     [rsp+180h+var_158], rax; UserData
0x14000d3af  mov     dword ptr [rsp+180h+UserData], 2; UserDataCount
0x14000d3b7  mov     [rbp+80h+EventDescriptor.Keyword], 10h
0x14000d3bf  mov     [rbp+80h+var_B8], 4
0x14000d3c7  call    cs:__imp_EtwWriteTransfer
0x14000d3ce  nop     dword ptr [rax+rax+00h]
0x14000d3d3  jmp     loc_14000D0E0
0x14000d3d8  mov     eax, 0AFD1h
0x14000d3dd  cmp     [rbx], ax
0x14000d3e0  setnz   cl
0x14000d3e3  inc     rcx
0x14000d3e6  jmp     loc_14000D149
0x14000d3eb  mov     eax, cs:Microsoft_Windows_Networking_CorrelationTraceActivityPayload
0x14000d3f1  lea     r8, [rsp+180h+var_110]; ActivityId
0x14000d3f6  mov     rcx, cs:Microsoft_Windows_Networking_CorrelationHandle; RegHandle
0x14000d3fd  lea     rdx, ActivityStart; EventDescriptor
0x14000d404  mov     [rsp+180h+var_150], 2
0x14000d40c  test    eax, eax
0x14000d40e  jz      short loc_14000D44D
0x14000d410  lea     rax, [rsp+180h+var_150]
0x14000d415  mov     qword ptr [rbp+80h+ActivityId.Data1], r12
0x14000d419  mov     [rbp+80h+var_E0], rax
0x14000d41d  mov     r9d, 2; UserDataCount
0x14000d423  lea     rax, [rbp+80h+ActivityId]
0x14000d427  mov     qword ptr [rbp+80h+ActivityId.Data4], 10h
0x14000d42f  mov     [rsp+180h+UserData], rax; UserData
0x14000d434  mov     [rbp+80h+var_D8], 4
0x14000d43c  call    cs:__imp_EtwWrite
0x14000d443  nop     dword ptr [rax+rax+00h]
0x14000d448  jmp     loc_14000D348
0x14000d44d  mov     [rsp+180h+UserData], 0
0x14000d456  xor     r9d, r9d
0x14000d459  jmp     short loc_14000D43C
0x14000d45b  mov     [rsp+180h+var_158], 0
0x14000d464  mov     dword ptr [rsp+180h+UserData], 0
0x14000d46c  jmp     loc_14000D3C7
0x14000d471  mov     [rsp+180h+UserData], 0
0x14000d47a  xor     r9d, r9d
0x14000d47d  jmp     loc_14000D306
0x14000d482  mov     qword ptr [rbp+80h+ActivityId.Data1], rbx
0x14000d486  jmp     loc_14000D1C8
0x14000d48b  call    cs:__imp_IoGetCurrentProcess
0x14000d492  nop     dword ptr [rax+rax+00h]
0x14000d497  jmp     loc_14000D1D5
```
