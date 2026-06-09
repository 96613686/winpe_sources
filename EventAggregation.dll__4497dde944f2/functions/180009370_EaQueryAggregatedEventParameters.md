# EaQueryAggregatedEventParameters

- ea: `0x180009370`
- end: `0x1800095d0`
- name: `EaQueryAggregatedEventParameters`
- size: `608`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `authz_impersonation`

## callees

- `0x180003630`
- `0x180007b5e`
- `0x180009300`
- `0x180009370`
- `0x18000982c`
- `0x180009c94`
- `0x180009d38`
- `0x18000a21c`
- `0x18000a2cc`
- `0x18000a368`
- `0x18000a414`
- `0x18000a528`
- `0x18000aa78`
- `0x18000aae8`
- `0x18000bde9`

## string_xrefs

- `0x1800094da`: `OwnerUserSid`

## pseudocode

```c
__int64 __fastcall EaQueryAggregatedEventParameters(void *a1, const GUID *a2, _QWORD *a3)
{
  _QWORD *v6; // rax
  _QWORD *v7; // rdi
  int AggregatedEventTrigger; // ebx
  int v9; // r9d
  int v10; // r9d
  HANDLE v11; // rcx
  int Buffer; // eax
  __int64 v13; // rbx
  void *v14; // rax
  void *v15; // rsi
  int v16; // r9d
  HANDLE KeyHandle; // [rsp+40h] [rbp-20h] BYREF
  __int64 v19[3]; // [rsp+48h] [rbp-18h] BYREF
  __int64 v20; // [rsp+98h] [rbp+38h] BYREF

  v19[1] = 0;
  KeyHandle = 0;
  v19[0] = 0;
  v6 = (_QWORD *)EaLibAllocate(72);
  v7 = v6;
  if ( !v6 )
    goto LABEL_2;
  memset_0(v6, 0, 0x48u);
  AggregatedEventTrigger = EapOpenAggregatedEventNode(a1, a2, &KeyHandle);
  if ( AggregatedEventTrigger >= 0 )
  {
    AggregatedEventTrigger = EapQueryAggregatedEventTrigger(KeyHandle, (__int64)v19);
    if ( AggregatedEventTrigger >= 0 )
    {
      AggregatedEventTrigger = EapQueryAggregatedEventCondition(KeyHandle, v19, v7 + 1);
      if ( AggregatedEventTrigger >= 0 )
      {
        v20 = 0;
        AggregatedEventTrigger = EapQueryValue((int)KeyHandle, (int)L"StartBoundary", 11, v9, &v20, 8, (__int64)v19);
        if ( AggregatedEventTrigger >= 0 )
        {
          v7[5] = v20;
          v20 = 0;
          AggregatedEventTrigger = EapQueryValue((int)KeyHandle, (int)L"EndBoundary", 11, v10, &v20, 8, (__int64)v19);
          if ( AggregatedEventTrigger >= 0 )
          {
            v7[6] = v20;
            AggregatedEventTrigger = EapQueryAggregatedEventOwnerAppName(KeyHandle, v19, v7 + 7);
            if ( AggregatedEventTrigger >= 0 )
            {
              v11 = KeyHandle;
              v7[8] = 0;
              Buffer = EapQueryBuffer(v11);
              AggregatedEventTrigger = Buffer;
              if ( Buffer != -1073741772 )
              {
                if ( Buffer < 0 )
                  goto LABEL_17;
                v13 = v19[0];
                v14 = (void *)EaLibAllocate(*(unsigned int *)(v19[0] + 12));
                v15 = v14;
                if ( !v14 )
                {
LABEL_2:
                  AggregatedEventTrigger = -1073741801;
                  goto LABEL_17;
                }
                memcpy_0(v14, (const void *)(v13 + *(unsigned int *)(v13 + 8)), *(unsigned int *)(v13 + 12));
                v7[8] = v15;
              }
              AggregatedEventTrigger = EapQueryAggregatedEventRepetition((int)KeyHandle, (__int64)v19);
              if ( AggregatedEventTrigger >= 0 )
              {
                AggregatedEventTrigger = EapQueryAggregatedEventDelay((int)KeyHandle, (__int64)v19);
                if ( AggregatedEventTrigger >= 0 )
                {
                  LODWORD(v20) = 0;
                  AggregatedEventTrigger = EapQueryValue(
                                             (int)KeyHandle,
                                             (int)L"TimeLimitInSeconds",
                                             4,
                                             v16,
                                             &v20,
                                             4,
                                             (__int64)v19);
                  if ( AggregatedEventTrigger >= 0 )
                  {
                    *((_DWORD *)v7 + 8) = v20;
                    *a3 = v7;
                    v7 = 0;
                    AggregatedEventTrigger = 0;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_17:
  EapCloseAggregatedEventNode(KeyHandle);
  if ( v7 )
    EaFreeAggregatedEventParameters(v7);
  EapReclaimKeyEnumBuffer(v19);
  return (unsigned int)AggregatedEventTrigger;
}

```

## disassembly

```asm
0x180009370  mov     [rsp-18h+arg_0], rbx
0x180009375  mov     [rsp-18h+arg_8], rsi
0x18000937a  push    rbp
0x18000937b  push    rdi
0x18000937c  push    r14
0x18000937e  mov     rbp, rsp
0x180009381  sub     rsp, 60h
0x180009385  mov     rsi, rcx
0x180009388  mov     [rbp+var_10], 0
0x180009390  mov     ecx, 48h ; 'H'
0x180009395  mov     [rbp+KeyHandle], 0
0x18000939d  mov     r14, r8
0x1800093a0  mov     [rbp+var_18], 0
0x1800093a8  mov     rbx, rdx
0x1800093ab  call    EaLibAllocate
0x1800093b0  mov     rdi, rax
0x1800093b3  test    rax, rax
0x1800093b6  jnz     short loc_1800093C2
0x1800093b8  mov     ebx, 0C0000017h
0x1800093bd  jmp     loc_18000959A
0x1800093c2  xor     edx, edx; Val
0x1800093c4  mov     rcx, rdi; void *
0x1800093c7  lea     r8d, [rdx+48h]; Size
0x1800093cb  call    memset_0
0x1800093d0  lea     r8, [rbp+KeyHandle]
0x1800093d4  mov     rdx, rbx
0x1800093d7  mov     rcx, rsi
0x1800093da  call    EapOpenAggregatedEventNode
0x1800093df  mov     ebx, eax
0x1800093e1  test    eax, eax
0x1800093e3  js      loc_18000959A
0x1800093e9  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1800093ed  lea     rdx, [rbp+var_18]; __int64
0x1800093f1  mov     r8, rdi
0x1800093f4  call    EapQueryAggregatedEventTrigger
0x1800093f9  mov     ebx, eax
0x1800093fb  test    eax, eax
0x1800093fd  js      loc_18000959A
0x180009403  mov     rcx, [rbp+KeyHandle]
0x180009407  lea     r8, [rdi+8]
0x18000940b  lea     rdx, [rbp+var_18]
0x18000940f  call    EapQueryAggregatedEventCondition
0x180009414  mov     ebx, eax
0x180009416  test    eax, eax
0x180009418  js      loc_18000959A
0x18000941e  mov     rcx, [rbp+KeyHandle]; int
0x180009422  lea     rax, [rbp+var_18]
0x180009426  mov     [rsp+60h+var_30], rax; __int64
0x18000942b  lea     rdx, EA_STORE_AGGRERATED_EVENT_FIELD_START_BOUNDARY; "StartBoundary"
0x180009432  mov     esi, 8
0x180009437  mov     [rbp+arg_18], 0
0x18000943f  lea     rax, [rbp+arg_18]
0x180009443  mov     [rsp+60h+var_38], esi; int
0x180009447  mov     [rsp+60h+var_40], rax; void *
0x18000944c  lea     r8d, [rsi+3]; int
0x180009450  call    EapQueryValue
0x180009455  mov     ebx, eax
0x180009457  test    eax, eax
0x180009459  js      loc_18000959A
0x18000945f  mov     rax, [rbp+arg_18]
0x180009463  mov     [rdi+28h], rax
0x180009467  mov     rcx, [rbp+KeyHandle]; int
0x18000946b  lea     rax, [rbp+var_18]
0x18000946f  mov     [rsp+60h+var_30], rax; __int64
0x180009474  lea     r8d, [rsi+3]; int
0x180009478  lea     rax, [rbp+arg_18]
0x18000947c  mov     [rsp+60h+var_38], esi; int
0x180009480  lea     rdx, EA_STORE_AGGRERATED_EVENT_FIELD_END_BOUNDARY; "EndBoundary"
0x180009487  mov     [rsp+60h+var_40], rax; void *
0x18000948c  mov     [rbp+arg_18], 0
0x180009494  call    EapQueryValue
0x180009499  mov     ebx, eax
0x18000949b  test    eax, eax
0x18000949d  js      loc_18000959A
0x1800094a3  mov     rax, [rbp+arg_18]
0x1800094a7  mov     [rdi+30h], rax
0x1800094ab  mov     rcx, [rbp+KeyHandle]
0x1800094af  lea     r8, [rdi+38h]
0x1800094b3  lea     rdx, [rbp+var_18]
0x1800094b7  call    EapQueryAggregatedEventOwnerAppName
0x1800094bc  mov     ebx, eax
0x1800094be  test    eax, eax
0x1800094c0  js      loc_18000959A
0x1800094c6  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x1800094ca  lea     r9, [rbp+var_18]
0x1800094ce  lea     r8d, [rsi-5]
0x1800094d2  mov     qword ptr [rdi+40h], 0
0x1800094da  lea     rdx, EA_STORE_AGGRERATED_EVENT_FIELD_OWNER_USER_SID; "OwnerUserSid"
0x1800094e1  call    EapQueryBuffer
0x1800094e6  mov     ebx, eax
0x1800094e8  cmp     eax, 0C0000034h
0x1800094ed  jz      short loc_180009525
0x1800094ef  test    eax, eax
0x1800094f1  js      loc_18000959A
0x1800094f7  mov     rbx, [rbp+var_18]
0x1800094fb  mov     ecx, [rbx+0Ch]
0x1800094fe  call    EaLibAllocate
0x180009503  mov     rsi, rax
0x180009506  test    rax, rax
0x180009509  jz      loc_1800093B8
0x18000950f  mov     edx, [rbx+8]
0x180009512  mov     rcx, rax; void *
0x180009515  mov     r8d, [rbx+0Ch]; Size
0x180009519  add     rdx, rbx; Src
0x18000951c  call    memcpy_0
0x180009521  mov     [rdi+40h], rsi
0x180009525  mov     rcx, [rbp+KeyHandle]; int
0x180009529  lea     r8, [rdi+18h]
0x18000952d  lea     rdx, [rbp+var_18]; __int64
0x180009531  call    EapQueryAggregatedEventRepetition
0x180009536  mov     ebx, eax
0x180009538  test    eax, eax
0x18000953a  js      short loc_18000959A
0x18000953c  mov     rcx, [rbp+KeyHandle]; int
0x180009540  lea     r8, [rdi+10h]
0x180009544  lea     rdx, [rbp+var_18]; __int64
0x180009548  call    EapQueryAggregatedEventDelay
0x18000954d  mov     ebx, eax
0x18000954f  test    eax, eax
0x180009551  js      short loc_18000959A
0x180009553  mov     rcx, [rbp+KeyHandle]; int
0x180009557  lea     rax, [rbp+var_18]
0x18000955b  mov     [rsp+60h+var_30], rax; __int64
0x180009560  lea     rdx, EA_STORE_AGGRERATED_EVENT_FIELD_TIME_LIMIT; "TimeLimitInSeconds"
0x180009567  mov     r8d, 4; int
0x18000956d  mov     dword ptr [rbp+arg_18], 0
0x180009574  lea     rax, [rbp+arg_18]
0x180009578  mov     [rsp+60h+var_38], r8d; int
0x18000957d  mov     [rsp+60h+var_40], rax; void *
0x180009582  call    EapQueryValue
0x180009587  mov     ebx, eax
0x180009589  test    eax, eax
0x18000958b  js      short loc_18000959A
0x18000958d  mov     eax, dword ptr [rbp+arg_18]
0x180009590  mov     [rdi+20h], eax
0x180009593  mov     [r14], rdi
0x180009596  xor     edi, edi
0x180009598  xor     ebx, ebx
0x18000959a  mov     rcx, [rbp+KeyHandle]
0x18000959e  call    EapCloseAggregatedEventNode
0x1800095a3  test    rdi, rdi
0x1800095a6  jz      short loc_1800095B0
0x1800095a8  mov     rcx, rdi
0x1800095ab  call    EaFreeAggregatedEventParameters
0x1800095b0  lea     rcx, [rbp+var_18]
0x1800095b4  call    EapReclaimKeyEnumBuffer
0x1800095b9  lea     r11, [rsp+60h+var_s0]
0x1800095be  mov     eax, ebx
0x1800095c0  mov     rbx, [r11+20h]
0x1800095c4  mov     rsi, [r11+28h]
0x1800095c8  mov     rsp, r11
0x1800095cb  pop     r14
0x1800095cd  pop     rdi
0x1800095ce  pop     rbp
0x1800095cf  retn
```
