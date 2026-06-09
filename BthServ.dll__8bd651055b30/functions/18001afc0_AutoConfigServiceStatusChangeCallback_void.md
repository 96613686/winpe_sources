# AutoConfigServiceStatusChangeCallback(void *)

- ea: `0x18001afc0`
- end: `0x18001b2ab`
- name: `?AutoConfigServiceStatusChangeCallback@@YAXPEAX@Z`
- size: `747`
- prototype: `void __fastcall(void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18001b9d8`

## callees

- `0x1800110fc`
- `0x180011194`
- `0x18001afc0`
- `0x18001b73c`
- `0x18001bc50`

## import_xrefs

- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18001b14b`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18001b20a`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18001b14b`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18001b20a`

## pseudocode

```c
void __fastcall AutoConfigServiceStatusChangeCallback(_DWORD *a1)
{
  _BYTE *v2; // rcx
  char v3; // bl
  bool v4; // dl
  bool v5; // dl
  bool v6; // r8
  int v7; // eax
  bool v8; // dl
  int v9; // edx
  int v10; // r8d
  bool v11; // dl
  int v12; // edx
  int v13; // r8d
  int v14; // [rsp+20h] [rbp-58h]
  int v15; // [rsp+28h] [rbp-50h]

  v2 = WPP_GLOBAL_Control;
  v3 = 1;
  v4 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v4,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v2 = WPP_GLOBAL_Control;
  }
  if ( a1[6] )
  {
    v5 = v2 != (_BYTE *)&WPP_GLOBAL_Control && v2[25] >= 3u;
    v6 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_15;
  }
  else
  {
    v7 = a1[8];
    if ( *((_DWORD *)pInterfaceGuid + 29) != v7 )
    {
      *((_DWORD *)pInterfaceGuid + 29) = v7;
      if ( a1[8] == 1 )
      {
        v11 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
        if ( v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_AND_TRACE_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v11,
            WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
            *((_QWORD *)WPP_GLOBAL_Control + 5));
        CloseWlanApi();
        if ( !NotifyServiceStatusChangeW(
                *((SC_HANDLE *)pInterfaceGuid + 13),
                8u,
                (PSERVICE_NOTIFYW)((char *)pInterfaceGuid + 16)) )
          goto LABEL_58;
        v2 = WPP_GLOBAL_Control;
        LOBYTE(v12) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
        if ( (_BYTE)v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v12,
            v13,
            *((_QWORD *)WPP_GLOBAL_Control + 5),
            v14,
            v15,
            25,
            (__int64)WPP_3ced9c3b7bc93563dc6bccedf26a5837_Traceguids);
          goto LABEL_58;
        }
      }
      else
      {
        if ( a1[8] != 4 )
          goto LABEL_58;
        v8 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
        if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_AND_TRACE_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v8,
            WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
            *((_QWORD *)WPP_GLOBAL_Control + 5));
        if ( (unsigned int)OpenWlanApi() )
        {
          if ( NotifyServiceStatusChangeW(
                 *((SC_HANDLE *)pInterfaceGuid + 13),
                 1u,
                 (PSERVICE_NOTIFYW)((char *)pInterfaceGuid + 16)) )
          {
            LOBYTE(v9) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
            if ( (_BYTE)v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
              WPP_RECORDER_AND_TRACE_SF_sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v9,
                v10,
                *((_QWORD *)WPP_GLOBAL_Control + 5),
                v14,
                v15,
                23,
                (__int64)WPP_3ced9c3b7bc93563dc6bccedf26a5837_Traceguids);
            }
            CloseWlanApi();
          }
          goto LABEL_58;
        }
        v2 = WPP_GLOBAL_Control;
        v5 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
        v6 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
LABEL_15:
          WPP_RECORDER_AND_TRACE_SF_s(*((_QWORD *)v2 + 2), v5, v6, *((_QWORD *)v2 + 5));
LABEL_58:
          v2 = WPP_GLOBAL_Control;
        }
      }
    }
  }
  if ( v2 == (_BYTE *)&WPP_GLOBAL_Control || v2[25] < 4u )
    v3 = 0;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)v2 + 2),
      v3,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)v2 + 5));
}

```

## disassembly

```asm
0x18001afc0  push    rbx
0x18001afc2  push    rbp
0x18001afc3  push    rsi
0x18001afc4  push    rdi
0x18001afc5  push    r15
0x18001afc7  sub     rsp, 50h
0x18001afcb  mov     rdi, rcx
0x18001afce  mov     rcx, cs:WPP_GLOBAL_Control
0x18001afd5  lea     rsi, WPP_GLOBAL_Control
0x18001afdc  mov     ebx, 1
0x18001afe1  cmp     rcx, rsi
0x18001afe4  jz      short loc_18001AFF0
0x18001afe6  cmp     byte ptr [rcx+19h], 4
0x18001afea  jb      short loc_18001AFF0
0x18001afec  mov     dl, bl
0x18001afee  jmp     short loc_18001AFF2
0x18001aff0  xor     dl, dl
0x18001aff2  lea     rbp, WPP_RECORDER_INITIALIZED
0x18001aff9  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18001b000  lea     r15, WPP_3ced9c3b7bc93563dc6bccedf26a5837_Traceguids
0x18001b007  setnz   r8b
0x18001b00b  test    dl, dl
0x18001b00d  jnz     short loc_18001B014
0x18001b00f  test    r8b, r8b
0x18001b012  jz      short loc_18001B034
0x18001b014  mov     r9, [rcx+28h]
0x18001b018  mov     rcx, [rcx+10h]
0x18001b01c  mov     [rsp+78h+var_40], r15
0x18001b021  mov     [rsp+78h+var_48], 13h
0x18001b028  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001b02d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b034  cmp     dword ptr [rdi+18h], 0
0x18001b038  jz      short loc_18001B081
0x18001b03a  cmp     rcx, rsi
0x18001b03d  jz      short loc_18001B049
0x18001b03f  cmp     byte ptr [rcx+19h], 3
0x18001b043  jb      short loc_18001B049
0x18001b045  mov     dl, bl
0x18001b047  jmp     short loc_18001B04B
0x18001b049  xor     dl, dl
0x18001b04b  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18001b052  setnz   r8b
0x18001b056  test    dl, dl
0x18001b058  jnz     short loc_18001B063
0x18001b05a  test    r8b, r8b
0x18001b05d  jz      loc_18001B264
0x18001b063  mov     [rsp+78h+var_40], r15
0x18001b068  mov     [rsp+78h+var_48], 14h
0x18001b06f  mov     r9, [rcx+28h]
0x18001b073  mov     rcx, [rcx+10h]
0x18001b077  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001b07c  jmp     loc_18001B25D
0x18001b081  mov     rdx, cs:pInterfaceGuid
0x18001b088  mov     eax, [rdi+20h]
0x18001b08b  cmp     [rdx+74h], eax
0x18001b08e  jz      loc_18001B264
0x18001b094  mov     [rdx+74h], eax
0x18001b097  mov     ecx, [rdi+20h]
0x18001b09a  sub     ecx, ebx
0x18001b09c  jz      loc_18001B1AC
0x18001b0a2  cmp     ecx, 3
0x18001b0a5  jnz     loc_18001B25D
0x18001b0ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b0b2  cmp     rcx, rsi
0x18001b0b5  jz      short loc_18001B0C1
0x18001b0b7  cmp     byte ptr [rcx+19h], 4
0x18001b0bb  jb      short loc_18001B0C1
0x18001b0bd  mov     dl, bl
0x18001b0bf  jmp     short loc_18001B0C3
0x18001b0c1  xor     dl, dl
0x18001b0c3  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18001b0ca  setnz   r8b
0x18001b0ce  test    dl, dl
0x18001b0d0  jnz     short loc_18001B0D7
0x18001b0d2  test    r8b, r8b
0x18001b0d5  jz      short loc_18001B0F0
0x18001b0d7  mov     r9, [rcx+28h]
0x18001b0db  mov     rcx, [rcx+10h]
0x18001b0df  mov     [rsp+78h+var_40], r15
0x18001b0e4  mov     [rsp+78h+var_48], 15h
0x18001b0eb  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001b0f0  call    ?OpenWlanApi@@YAHXZ; OpenWlanApi(void)
0x18001b0f5  test    eax, eax
0x18001b0f7  jnz     short loc_18001B13A
0x18001b0f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b100  cmp     rcx, rsi
0x18001b103  jz      short loc_18001B10F
0x18001b105  cmp     byte ptr [rcx+19h], 3
0x18001b109  jb      short loc_18001B10F
0x18001b10b  mov     dl, bl
0x18001b10d  jmp     short loc_18001B111
0x18001b10f  xor     dl, dl
0x18001b111  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18001b118  setnz   r8b
0x18001b11c  test    dl, dl
0x18001b11e  jnz     short loc_18001B129
0x18001b120  test    r8b, r8b
0x18001b123  jz      loc_18001B264
0x18001b129  mov     [rsp+78h+var_40], r15
0x18001b12e  mov     [rsp+78h+var_48], 16h
0x18001b135  jmp     loc_18001B06F
0x18001b13a  mov     rcx, cs:pInterfaceGuid
0x18001b141  mov     edx, ebx; dwNotifyMask
0x18001b143  lea     r8, [rcx+10h]; pNotifyBuffer
0x18001b147  mov     rcx, [rcx+68h]; hService
0x18001b14b  call    cs:__imp_NotifyServiceStatusChangeW
0x18001b151  test    eax, eax
0x18001b153  jz      loc_18001B25D
0x18001b159  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b160  cmp     rcx, rsi
0x18001b163  jz      short loc_18001B16F
0x18001b165  cmp     byte ptr [rcx+19h], 3
0x18001b169  jb      short loc_18001B16F
0x18001b16b  mov     dl, bl
0x18001b16d  jmp     short loc_18001B171
0x18001b16f  xor     dl, dl
0x18001b171  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18001b178  setnz   r8b
0x18001b17c  test    dl, dl
0x18001b17e  jnz     short loc_18001B185
0x18001b180  test    r8b, r8b
0x18001b183  jz      short loc_18001B1A2
0x18001b185  mov     r9, [rcx+28h]
0x18001b189  mov     rcx, [rcx+10h]
0x18001b18d  mov     [rsp+78h+var_30], eax
0x18001b191  mov     [rsp+78h+var_40], r15
0x18001b196  mov     [rsp+78h+var_48], 17h
0x18001b19d  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18001b1a2  call    ?CloseWlanApi@@YAXXZ; CloseWlanApi(void)
0x18001b1a7  jmp     loc_18001B25D
0x18001b1ac  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b1b3  cmp     rcx, rsi
0x18001b1b6  jz      short loc_18001B1C2
0x18001b1b8  cmp     byte ptr [rcx+19h], 4
0x18001b1bc  jb      short loc_18001B1C2
0x18001b1be  mov     dl, bl
0x18001b1c0  jmp     short loc_18001B1C4
0x18001b1c2  xor     dl, dl
0x18001b1c4  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18001b1cb  setnz   r8b
0x18001b1cf  test    dl, dl
0x18001b1d1  jnz     short loc_18001B1D8
0x18001b1d3  test    r8b, r8b
0x18001b1d6  jz      short loc_18001B1F1
0x18001b1d8  mov     r9, [rcx+28h]
0x18001b1dc  mov     rcx, [rcx+10h]
0x18001b1e0  mov     [rsp+78h+var_40], r15
0x18001b1e5  mov     [rsp+78h+var_48], 18h
0x18001b1ec  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001b1f1  call    ?CloseWlanApi@@YAXXZ; CloseWlanApi(void)
0x18001b1f6  mov     rcx, cs:pInterfaceGuid
0x18001b1fd  mov     edx, 8; dwNotifyMask
0x18001b202  lea     r8, [rcx+10h]; pNotifyBuffer
0x18001b206  mov     rcx, [rcx+68h]; hService
0x18001b20a  call    cs:__imp_NotifyServiceStatusChangeW
0x18001b210  test    eax, eax
0x18001b212  jz      short loc_18001B25D
0x18001b214  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b21b  cmp     rcx, rsi
0x18001b21e  jz      short loc_18001B22A
0x18001b220  cmp     byte ptr [rcx+19h], 3
0x18001b224  jb      short loc_18001B22A
0x18001b226  mov     dl, bl
0x18001b228  jmp     short loc_18001B22C
0x18001b22a  xor     dl, dl
0x18001b22c  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18001b233  setnz   r8b
0x18001b237  test    dl, dl
0x18001b239  jnz     short loc_18001B240
0x18001b23b  test    r8b, r8b
0x18001b23e  jz      short loc_18001B264
0x18001b240  mov     r9, [rcx+28h]
0x18001b244  mov     rcx, [rcx+10h]
0x18001b248  mov     [rsp+78h+var_30], eax
0x18001b24c  mov     [rsp+78h+var_40], r15
0x18001b251  mov     [rsp+78h+var_48], 19h
0x18001b258  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18001b25d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b264  cmp     rcx, rsi
0x18001b267  jz      short loc_18001B26F
0x18001b269  cmp     byte ptr [rcx+19h], 4
0x18001b26d  jnb     short loc_18001B271
0x18001b26f  xor     bl, bl
0x18001b271  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18001b278  setnz   r8b
0x18001b27c  test    bl, bl
0x18001b27e  jnz     short loc_18001B285
0x18001b280  test    r8b, r8b
0x18001b283  jz      short loc_18001B2A0
0x18001b285  mov     r9, [rcx+28h]
0x18001b289  mov     dl, bl
0x18001b28b  mov     rcx, [rcx+10h]
0x18001b28f  mov     [rsp+78h+var_40], r15
0x18001b294  mov     [rsp+78h+var_48], 1Ah
0x18001b29b  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001b2a0  add     rsp, 50h
0x18001b2a4  pop     r15
0x18001b2a6  pop     rdi
0x18001b2a7  pop     rsi
0x18001b2a8  pop     rbp
0x18001b2a9  pop     rbx
0x18001b2aa  retn
```
