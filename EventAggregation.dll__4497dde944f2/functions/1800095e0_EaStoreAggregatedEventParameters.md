# EaStoreAggregatedEventParameters

- ea: `0x1800095e0`
- end: `0x180009823`
- name: `EaStoreAggregatedEventParameters`
- size: `579`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800095e0`
- `0x18000982c`
- `0x180009848`
- `0x18000ab18`
- `0x18000ab7c`
- `0x18000aec4`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18000970c`
- `ntdll!RtlLengthSid` at `0x18000970c`

## string_xrefs

- `0x180009715`: `OwnerUserSid`

## pseudocode

```c
__int64 __fastcall EaStoreAggregatedEventParameters(__int64 a1, __int64 a2, __int64 a3)
{
  HANDLE v4; // rsi
  int v5; // eax
  int v6; // ebx
  __int64 v7; // r9
  __int64 v8; // rax
  ULONG v9; // eax
  HANDLE KeyHandle; // [rsp+70h] [rbp+8h] BYREF

  KeyHandle = 0;
  v4 = 0;
  if ( a1 && a3 && a2 )
  {
    v5 = EapCreateAggregatedEventNode(a1, a2, &KeyHandle);
    v4 = KeyHandle;
    v6 = v5;
    if ( v5 >= 0 )
    {
      if ( !*(_QWORD *)a3 || (v6 = EapStoreAggregatedEventTrigger(KeyHandle, *(GUID **)a3), v6 >= 0) )
      {
        if ( !*(_QWORD *)(a3 + 8) || (v6 = EapStoreAggregatedEventCondition(v4), v6 >= 0) )
        {
          if ( !*(_QWORD *)(a3 + 40) || (v6 = EapSetValue(v4, 8u), v6 >= 0) )
          {
            if ( !*(_QWORD *)(a3 + 48) || (v6 = EapSetValue(v4, 8u), v6 >= 0) )
            {
              v7 = *(_QWORD *)(a3 + 56);
              if ( !v7 )
                goto LABEL_34;
              v8 = -1;
              do
                ++v8;
              while ( *(_WORD *)(v7 + 2 * v8) );
              v6 = EapSetValue(v4, 2 * (int)v8 + 2);
              if ( v6 >= 0 )
              {
LABEL_34:
                if ( !*(_QWORD *)(a3 + 64) || (v9 = RtlLengthSid(*(PSID *)(a3 + 64)), v6 = EapSetValue(v4, v9), v6 >= 0) )
                {
                  if ( !*(_DWORD *)(a3 + 28)
                    || (v6 = EapSetValue(v4, 4u), v6 >= 0)
                    && (!*(_DWORD *)(a3 + 28) || (v6 = EapSetValue(v4, 4u), v6 >= 0)) )
                  {
                    if ( !*(_DWORD *)(a3 + 16)
                      || (v6 = EapSetValue(v4, 4u), v6 >= 0)
                      && (!*(_BYTE *)(a3 + 20) || (v6 = EapSetValue(v4, 4u), v6 >= 0)) )
                    {
                      if ( !*(_DWORD *)(a3 + 32) || (v6 = EapSetValue(v4, 4u), v6 >= 0) )
                        v6 = 0;
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  else
  {
    v6 = -1073741811;
  }
  EapCloseAggregatedEventNode(v4);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800095e0  push    rbx
0x1800095e2  push    rbp
0x1800095e3  push    rsi
0x1800095e4  push    rdi
0x1800095e5  push    r14
0x1800095e7  push    r15
0x1800095e9  sub     rsp, 38h
0x1800095ed  xor     r14d, r14d
0x1800095f0  mov     rdi, r8
0x1800095f3  mov     [rsp+68h+KeyHandle], r14
0x1800095f8  mov     esi, r14d
0x1800095fb  test    rcx, rcx
0x1800095fe  jz      loc_180009807
0x180009604  test    r8, r8
0x180009607  jz      loc_180009807
0x18000960d  test    rdx, rdx
0x180009610  jz      loc_180009807
0x180009616  lea     r8, [rsp+68h+KeyHandle]
0x18000961b  call    EapCreateAggregatedEventNode
0x180009620  mov     rsi, [rsp+68h+KeyHandle]
0x180009625  mov     ebx, eax
0x180009627  test    eax, eax
0x180009629  js      loc_18000980C
0x18000962f  mov     rdx, [rdi]; Guid
0x180009632  test    rdx, rdx
0x180009635  jz      short loc_180009649
0x180009637  mov     rcx, rsi; KeyHandle
0x18000963a  call    EapStoreAggregatedEventTrigger
0x18000963f  mov     ebx, eax
0x180009641  test    eax, eax
0x180009643  js      loc_18000980C
0x180009649  mov     rdx, [rdi+8]
0x18000964d  test    rdx, rdx
0x180009650  jz      short loc_180009664
0x180009652  mov     rcx, rsi; KeyHandle
0x180009655  call    EapStoreAggregatedEventCondition
0x18000965a  mov     ebx, eax
0x18000965c  test    eax, eax
0x18000965e  js      loc_18000980C
0x180009664  mov     ebp, 8
0x180009669  lea     r9, [rdi+28h]
0x18000966d  lea     r15d, [rbp+3]
0x180009671  cmp     [r9], r14
0x180009674  jz      short loc_180009696
0x180009676  mov     r8d, r15d
0x180009679  mov     [rsp+68h+var_48], ebp; ULONG
0x18000967d  lea     rdx, EA_STORE_AGGRERATED_EVENT_FIELD_START_BOUNDARY; "StartBoundary"
0x180009684  mov     rcx, rsi; KeyHandle
0x180009687  call    EapSetValue
0x18000968c  mov     ebx, eax
0x18000968e  test    eax, eax
0x180009690  js      loc_18000980C
0x180009696  lea     r9, [rdi+30h]
0x18000969a  cmp     [r9], r14
0x18000969d  jz      short loc_1800096BF
0x18000969f  mov     r8d, r15d
0x1800096a2  mov     [rsp+68h+var_48], ebp; ULONG
0x1800096a6  lea     rdx, EA_STORE_AGGRERATED_EVENT_FIELD_END_BOUNDARY; "EndBoundary"
0x1800096ad  mov     rcx, rsi; KeyHandle
0x1800096b0  call    EapSetValue
0x1800096b5  mov     ebx, eax
0x1800096b7  test    eax, eax
0x1800096b9  js      loc_18000980C
0x1800096bf  mov     r9, [rdi+38h]
0x1800096c3  test    r9, r9
0x1800096c6  jz      short loc_180009700
0x1800096c8  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800096cc  inc     rax
0x1800096cf  cmp     [r9+rax*2], r14w
0x1800096d4  jnz     short loc_1800096CC
0x1800096d6  lea     eax, ds:2[rax*2]
0x1800096dd  mov     r8d, 1
0x1800096e3  lea     rdx, EA_STORE_AGGRERATED_EVENT_FIELD_OWNER_APP_NAME; "OwnerAppName"
0x1800096ea  mov     [rsp+68h+var_48], eax; ULONG
0x1800096ee  mov     rcx, rsi; KeyHandle
0x1800096f1  call    EapSetValue
0x1800096f6  mov     ebx, eax
0x1800096f8  test    eax, eax
0x1800096fa  js      loc_18000980C
0x180009700  mov     rbx, [rdi+40h]
0x180009704  test    rbx, rbx
0x180009707  jz      short loc_180009738
0x180009709  mov     rcx, rbx; Sid
0x18000970c  call    cs:__imp_RtlLengthSid
0x180009712  mov     r9, rbx
0x180009715  lea     rdx, EA_STORE_AGGRERATED_EVENT_FIELD_OWNER_USER_SID; "OwnerUserSid"
0x18000971c  mov     r8d, 3
0x180009722  mov     [rsp+68h+var_48], eax; ULONG
0x180009726  mov     rcx, rsi; KeyHandle
0x180009729  call    EapSetValue
0x18000972e  mov     ebx, eax
0x180009730  test    eax, eax
0x180009732  js      loc_18000980C
0x180009738  mov     r15d, 4
0x18000973e  cmp     [rdi+1Ch], r14d
0x180009742  jz      short loc_18000978F
0x180009744  lea     r9, [rdi+18h]
0x180009748  mov     [rsp+68h+var_48], r15d; ULONG
0x18000974d  mov     r8d, r15d
0x180009750  lea     rdx, EA_STORE_AGGRERATED_EVENT_FIELD_REPETITION_INTERVAL; "RepetitionIntervalInSeconds"
0x180009757  mov     rcx, rsi; KeyHandle
0x18000975a  call    EapSetValue
0x18000975f  mov     ebx, eax
0x180009761  test    eax, eax
0x180009763  js      loc_18000980C
0x180009769  lea     r9, [rdi+1Ch]
0x18000976d  cmp     [r9], r14d
0x180009770  jz      short loc_18000978F
0x180009772  mov     r8d, r15d
0x180009775  mov     [rsp+68h+var_48], r15d; ULONG
0x18000977a  lea     rdx, EA_STORE_AGGRERATED_EVENT_FIELD_NUMBER_OF_REPETITIONS; "NumberOfRepetitions"
0x180009781  mov     rcx, rsi; KeyHandle
0x180009784  call    EapSetValue
0x180009789  mov     ebx, eax
0x18000978b  test    eax, eax
0x18000978d  js      short loc_18000980C
0x18000978f  cmp     [rdi+10h], r14d
0x180009793  jz      short loc_1800097DC
0x180009795  lea     r9, [rdi+10h]
0x180009799  mov     [rsp+68h+var_48], r15d; ULONG
0x18000979e  mov     r8d, r15d
0x1800097a1  lea     rdx, EA_STORE_AGGRERATED_EVENT_FIELD_DELAY_IN_SECONDS; "DelayIntervalInSeconds"
0x1800097a8  mov     rcx, rsi; KeyHandle
0x1800097ab  call    EapSetValue
0x1800097b0  mov     ebx, eax
0x1800097b2  test    eax, eax
0x1800097b4  js      short loc_18000980C
0x1800097b6  lea     r9, [rdi+14h]
0x1800097ba  cmp     [r9], r14b
0x1800097bd  jz      short loc_1800097DC
0x1800097bf  mov     r8d, r15d
0x1800097c2  mov     [rsp+68h+var_48], r15d; ULONG
0x1800097c7  lea     rdx, EA_STORE_AGGRERATED_EVENT_FIELD_IS_RANDOM; "IsRandom"
0x1800097ce  mov     rcx, rsi; KeyHandle
0x1800097d1  call    EapSetValue
0x1800097d6  mov     ebx, eax
0x1800097d8  test    eax, eax
0x1800097da  js      short loc_18000980C
0x1800097dc  lea     r9, [rdi+20h]
0x1800097e0  cmp     [r9], r14d
0x1800097e3  jz      short loc_180009802
0x1800097e5  mov     r8d, r15d
0x1800097e8  mov     [rsp+68h+var_48], r15d; ULONG
0x1800097ed  lea     rdx, EA_STORE_AGGRERATED_EVENT_FIELD_TIME_LIMIT; "TimeLimitInSeconds"
0x1800097f4  mov     rcx, rsi; KeyHandle
0x1800097f7  call    EapSetValue
0x1800097fc  mov     ebx, eax
0x1800097fe  test    eax, eax
0x180009800  js      short loc_18000980C
0x180009802  mov     ebx, r14d
0x180009805  jmp     short loc_18000980C
0x180009807  mov     ebx, 0C000000Dh
0x18000980c  mov     rcx, rsi
0x18000980f  call    EapCloseAggregatedEventNode
0x180009814  mov     eax, ebx
0x180009816  add     rsp, 38h
0x18000981a  pop     r15
0x18000981c  pop     r14
0x18000981e  pop     rdi
0x18000981f  pop     rsi
0x180009820  pop     rbp
0x180009821  pop     rbx
0x180009822  retn
```
