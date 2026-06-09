# DpspRaiseScenarioDPSFailedEvent

- ea: `0x180007500`
- end: `0x18000768b`
- name: `DpspRaiseScenarioDPSFailedEvent`
- size: `395`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180002090`
- `0x180003830`
- `0x18000b484`
- `0x180012670`

## callees

- `0x180007500`
- `0x180009090`
- `0x180009fb0`
- `0x18000a856`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x1800075a1`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x1800075a1`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180007650`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x180007650`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800075c9`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000765f`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800075c9`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18000765f`

## pseudocode

```c
__int64 __fastcall DpspRaiseScenarioDPSFailedEvent(__int64 a1, const EVENT_DESCRIPTOR *a2)
{
  int v4; // r8d
  unsigned int v5; // ebx
  ULONGLONG v6; // r8
  __int64 v7; // rax
  int v8; // ecx
  __int64 v9; // rax
  GUID ActivityId; // [rsp+30h] [rbp-39h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+40h] [rbp-29h] BYREF
  __int64 v13; // [rsp+50h] [rbp-19h]
  __int64 v14; // [rsp+58h] [rbp-11h]
  __int64 v15; // [rsp+60h] [rbp-9h]
  __int64 v16; // [rsp+68h] [rbp-1h]
  __int64 v17; // [rsp+70h] [rbp+7h]
  __int64 v18; // [rsp+78h] [rbp+Fh]
  __int64 v19; // [rsp+80h] [rbp+17h]
  int v20; // [rsp+88h] [rbp+1Fh]
  int v21; // [rsp+8Ch] [rbp+23h]
  __int64 v22; // [rsp+90h] [rbp+27h]
  __int64 v23; // [rsp+98h] [rbp+2Fh]

  UserData.Ptr = 0;
  ActivityId = 0;
  memset_0(&UserData.Size, 0, 0x58u);
  if ( !a1 )
  {
    v4 = 392;
LABEL_3:
    v5 = -2147024809;
    WdipTraceError(
      (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsevents.cpp",
      (__int64)L"DpspRaiseScenarioDPSFailedEvent",
      v4,
      (const wchar_t *)L"Error = %d",
      87);
    return v5;
  }
  if ( !*(_QWORD *)(a1 + 1216) )
  {
    v4 = 393;
    goto LABEL_3;
  }
  v5 = 0;
  if ( EventEnabled(g_hETW, a2) )
  {
    if ( a1 != -24 )
      ActivityId = *(GUID *)(a1 + 24);
    EventActivityIdControl(4u, &ActivityId);
    v6 = *(_QWORD *)(a1 + 1216);
    v15 = a1 + 56;
    UserData.Ptr = v6;
    v17 = a1 + 132;
    *(_QWORD *)&UserData.Size = 16;
    v13 = a1 + 24;
    v14 = 16;
    v16 = 16;
    v18 = 4;
    v7 = *(_QWORD *)(v6 + 96);
    v8 = *(_DWORD *)(v7 + 148);
    v9 = *(_QWORD *)(v7 + 128);
    v20 = v8;
    v19 = v9;
    v21 = 0;
    v22 = *(_QWORD *)(v6 + 96);
    v23 = 16;
    EventWrite(g_hETW, a2, 6u, &UserData);
    EventActivityIdControl(2u, &ActivityId);
  }
  return v5;
}

```

## disassembly

```asm
0x180007500  mov     [rsp-8+arg_0], rbx
0x180007505  mov     [rsp-8+arg_10], rsi
0x18000750a  push    rbp
0x18000750b  push    rdi
0x18000750c  push    r14
0x18000750e  lea     rbp, [rsp-47h]
0x180007513  sub     rsp, 0B0h
0x18000751a  mov     rax, cs:__security_cookie
0x180007521  xor     rax, rsp
0x180007524  mov     [rbp+57h+var_20], rax
0x180007528  mov     r14, rdx
0x18000752b  mov     [rbp+57h+UserData.Ptr], 0
0x180007533  xor     edx, edx; Val
0x180007535  mov     rdi, rcx
0x180007538  xorps   xmm0, xmm0
0x18000753b  lea     rcx, [rbp+57h+UserData.Size]; void *
0x18000753f  movups  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x180007543  lea     r8d, [rdx+58h]; Size
0x180007547  call    memset_0
0x18000754c  test    rdi, rdi
0x18000754f  jnz     short loc_180007583
0x180007551  mov     r8d, 188h; int
0x180007557  lea     r9, aErrorD; "Error = %d"
0x18000755e  mov     dword ptr [rsp+0C0h+Args], 57h ; 'W'; Args
0x180007566  lea     rdx, aDpspraisescena_1; "DpspRaiseScenarioDPSFailedEvent"
0x18000756d  mov     ebx, 80070057h
0x180007572  lea     rcx, aClientcoreBase_6; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180007579  call    WdipTraceError
0x18000757e  jmp     loc_180007665
0x180007583  cmp     qword ptr [rdi+4C0h], 0
0x18000758b  jnz     short loc_180007595
0x18000758d  mov     r8d, 189h
0x180007593  jmp     short loc_180007557
0x180007595  mov     rcx, cs:g_hETW; RegHandle
0x18000759c  mov     rdx, r14; EventDescriptor
0x18000759f  xor     ebx, ebx
0x1800075a1  call    cs:__imp_EventEnabled
0x1800075a7  test    al, al
0x1800075a9  jz      loc_180007665
0x1800075af  lea     rsi, [rdi+18h]
0x1800075b3  test    rsi, rsi
0x1800075b6  jz      short loc_1800075C0
0x1800075b8  movups  xmm0, xmmword ptr [rsi]
0x1800075bb  movdqu  xmmword ptr [rbp+57h+ActivityId.Data1], xmm0
0x1800075c0  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x1800075c4  mov     ecx, 4; ControlCode
0x1800075c9  call    cs:__imp_EventActivityIdControl
0x1800075cf  mov     r8, [rdi+4C0h]
0x1800075d6  lea     rax, [rdi+38h]
0x1800075da  mov     [rbp+57h+var_60], rax
0x1800075de  lea     r9, [rbp+57h+UserData]; UserData
0x1800075e2  mov     [rbp+57h+UserData.Ptr], r8
0x1800075e6  lea     rax, [rdi+84h]
0x1800075ed  mov     [rbp+57h+var_50], rax
0x1800075f1  mov     rdx, r14; EventDescriptor
0x1800075f4  mov     qword ptr [rbp+57h+UserData.Size], 10h
0x1800075fc  mov     [rbp+57h+var_70], rsi
0x180007600  mov     [rbp+57h+var_68], 10h
0x180007608  mov     [rbp+57h+var_58], 10h
0x180007610  mov     [rbp+57h+var_48], 4
0x180007618  mov     rax, [r8+60h]
0x18000761c  mov     ecx, [rax+94h]
0x180007622  mov     rax, [rax+80h]
0x180007629  mov     [rbp+57h+var_38], ecx
0x18000762c  mov     [rbp+57h+var_40], rax
0x180007630  mov     [rbp+57h+var_34], ebx
0x180007633  mov     rcx, [r8+60h]
0x180007637  mov     r8d, 6; UserDataCount
0x18000763d  mov     [rbp+57h+var_30], rcx
0x180007641  mov     rcx, cs:g_hETW; RegHandle
0x180007648  mov     [rbp+57h+var_28], 10h
0x180007650  call    cs:__imp_EventWrite
0x180007656  lea     rdx, [rbp+57h+ActivityId]; ActivityId
0x18000765a  mov     ecx, 2; ControlCode
0x18000765f  call    cs:__imp_EventActivityIdControl
0x180007665  mov     eax, ebx
0x180007667  mov     rcx, [rbp+57h+var_20]
0x18000766b  xor     rcx, rsp; StackCookie
0x18000766e  call    __security_check_cookie
0x180007673  lea     r11, [rsp+0C0h+var_10]
0x18000767b  mov     rbx, [r11+20h]
0x18000767f  mov     rsi, [r11+30h]
0x180007683  mov     rsp, r11
0x180007686  pop     r14
0x180007688  pop     rdi
0x180007689  pop     rbp
0x18000768a  retn
```
