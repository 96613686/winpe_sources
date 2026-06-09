# Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::ProcessDeviceMatch(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *)

- ea: `0x18002a034`
- end: `0x18002a2e7`
- name: `?ProcessDeviceMatch@BthLEPrepairingController@BthLEPrepairing@Bluetooth@Internal@Windows@@AEAAJPEAVBthLEPrepairingDevice@2345@@Z`
- size: `691`
- prototype: `__int64 __fastcall(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *__hidden this, struct Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *)`
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180029e9c`
- `0x18002a2f0`

## callees

- `0x1800110fc`
- `0x180011194`
- `0x18001140c`
- `0x180029640`
- `0x18002a034`
- `0x18002a488`
- `0x18002aec0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a0bd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a0bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a1bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002a1bd`
- `BthTelemetry!BthProcessEventOccurrenceBthaddr` at `0x18002a1e2`
- `BthTelemetry!BthProcessEventOccurrenceBthaddr` at `0x18002a1e2`

## string_xrefs

- `0x18002a1d7`: `BTH_TELEMETRYDATA_PREPAIRING_INITIAL_HW_FILTER_MATCHED`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::ProcessDeviceMatch(
        Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *this,
        struct Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *a2)
{
  char v4; // bl
  bool v5; // dl
  char v6; // r15
  int v7; // esi
  int v8; // ecx
  int v9; // ecx
  _BYTE *v10; // rcx
  bool v11; // dl
  bool v12; // dl
  int v13; // edx
  int v14; // r8d
  int v15; // eax
  bool v16; // cf
  int v18; // [rsp+20h] [rbp-68h]
  int v19; // [rsp+28h] [rbp-60h]
  Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *v20; // [rsp+90h] [rbp+8h] BYREF

  v4 = 1;
  v5 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  v6 = 0;
  v7 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v8 = *((_DWORD *)this + 2);
  if ( v8 )
  {
    v9 = v8 - 1;
    if ( v9 )
    {
      if ( v9 == 1 )
      {
        v10 = WPP_GLOBAL_Control;
        v11 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
        if ( v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          WPP_RECORDER_AND_TRACE_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v11,
            WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
            *((_QWORD *)WPP_GLOBAL_Control + 5));
          v10 = WPP_GLOBAL_Control;
        }
        goto LABEL_28;
      }
    }
    else
    {
      *((_DWORD *)this + 2) = 2;
      v6 = 1;
      *((_QWORD *)this + 11) = a2;
    }
    v10 = WPP_GLOBAL_Control;
    goto LABEL_28;
  }
  v10 = WPP_GLOBAL_Control;
  v12 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
  if ( v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v12,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v10 = WPP_GLOBAL_Control;
  }
  v7 = -2147418113;
LABEL_28:
  if ( this != (Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *)-48LL )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    v10 = WPP_GLOBAL_Control;
  }
  if ( v6 )
  {
    BthProcessEventOccurrenceBthaddr(
      "BTH_TELEMETRYDATA_PREPAIRING_INITIAL_HW_FILTER_MATCHED",
      *(_QWORD *)(*((_QWORD *)this + 11) + 48LL));
    v20 = this;
    v7 = wil::ResultFromException__lambda_69d4ebafcdfc875e4eef5671220ca470___(&v20);
    if ( v7 < 0 )
    {
      LOBYTE(v13) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
      if ( (_BYTE)v13 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v14) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v13,
          v14,
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v18,
          v19,
          35,
          (__int64)WPP_a555314c10c534a6d8c11e317bc5bc21_Traceguids);
      }
      Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::ResetPairingState(this);
      v10 = WPP_GLOBAL_Control;
      goto LABEL_40;
    }
    v10 = WPP_GLOBAL_Control;
  }
  if ( !v7 )
  {
    v15 = 0;
    v16 = v10[25] < 5u;
    goto LABEL_41;
  }
LABEL_40:
  v15 = 0;
  v16 = v10[25] < 2u;
LABEL_41:
  if ( v10 == (_BYTE *)&WPP_GLOBAL_Control || (LOBYTE(v15) = !v16, !v15) )
    v4 = 0;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_sqd(
      *((_QWORD *)v10 + 2),
      v4,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)v10 + 5),
      v18,
      v19,
      36,
      (__int64)WPP_a555314c10c534a6d8c11e317bc5bc21_Traceguids);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18002a034  mov     [rsp+arg_8], rbx
0x18002a039  mov     [rsp+arg_10], rbp
0x18002a03e  push    rsi
0x18002a03f  push    rdi
0x18002a040  push    r12
0x18002a042  push    r14
0x18002a044  push    r15
0x18002a046  sub     rsp, 60h
0x18002a04a  mov     rbp, rdx
0x18002a04d  mov     rdi, rcx
0x18002a050  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a057  lea     r12, WPP_GLOBAL_Control
0x18002a05e  mov     bl, 1
0x18002a060  cmp     rcx, r12
0x18002a063  jz      short loc_18002A06F
0x18002a065  cmp     byte ptr [rcx+19h], 5
0x18002a069  jb      short loc_18002A06F
0x18002a06b  mov     dl, bl
0x18002a06d  jmp     short loc_18002A071
0x18002a06f  xor     dl, dl
0x18002a071  lea     rax, WPP_RECORDER_INITIALIZED
0x18002a078  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002a07f  lea     r9, WPP_a555314c10c534a6d8c11e317bc5bc21_Traceguids
0x18002a086  setnz   r8b
0x18002a08a  test    dl, dl
0x18002a08c  jnz     short loc_18002A093
0x18002a08e  test    r8b, r8b
0x18002a091  jz      short loc_18002A0B1
0x18002a093  mov     [rsp+88h+var_40], rdi
0x18002a098  mov     [rsp+88h+var_50], r9
0x18002a09d  mov     r9, [rcx+28h]
0x18002a0a1  mov     rcx, [rcx+10h]
0x18002a0a5  mov     [rsp+88h+var_58], 20h ; ' '
0x18002a0ac  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002a0b1  lea     r14, [rdi+30h]
0x18002a0b5  xor     r15b, r15b
0x18002a0b8  mov     rcx, r14; lpCriticalSection
0x18002a0bb  xor     esi, esi
0x18002a0bd  call    cs:__imp_EnterCriticalSection
0x18002a0c3  mov     ecx, [rdi+8]
0x18002a0c6  test    ecx, ecx
0x18002a0c8  jz      loc_18002A156
0x18002a0ce  sub     ecx, 1
0x18002a0d1  jz      short loc_18002A138
0x18002a0d3  cmp     ecx, 1
0x18002a0d6  jnz     short loc_18002A146
0x18002a0d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a0df  cmp     rcx, r12
0x18002a0e2  jz      short loc_18002A0EE
0x18002a0e4  cmp     byte ptr [rcx+19h], 4
0x18002a0e8  jb      short loc_18002A0EE
0x18002a0ea  mov     dl, bl
0x18002a0ec  jmp     short loc_18002A0F0
0x18002a0ee  xor     dl, dl
0x18002a0f0  lea     rbp, WPP_RECORDER_INITIALIZED
0x18002a0f7  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18002a0fe  setnz   r8b
0x18002a102  test    dl, dl
0x18002a104  jnz     short loc_18002A10F
0x18002a106  test    r8b, r8b
0x18002a109  jz      loc_18002A1B5
0x18002a10f  lea     r9, WPP_a555314c10c534a6d8c11e317bc5bc21_Traceguids
0x18002a116  mov     [rsp+88h+var_50], r9
0x18002a11b  mov     r9, [rcx+28h]
0x18002a11f  mov     rcx, [rcx+10h]
0x18002a123  mov     [rsp+88h+var_58], 22h ; '"'
0x18002a12a  call    WPP_RECORDER_AND_TRACE_SF_s
0x18002a12f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a136  jmp     short loc_18002A1B5
0x18002a138  mov     dword ptr [rdi+8], 2
0x18002a13f  mov     r15b, bl
0x18002a142  mov     [rdi+58h], rbp
0x18002a146  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a14d  lea     rbp, WPP_RECORDER_INITIALIZED
0x18002a154  jmp     short loc_18002A1B5
0x18002a156  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a15d  cmp     rcx, r12
0x18002a160  jz      short loc_18002A16C
0x18002a162  cmp     byte ptr [rcx+19h], 2
0x18002a166  jb      short loc_18002A16C
0x18002a168  mov     dl, bl
0x18002a16a  jmp     short loc_18002A16E
0x18002a16c  xor     dl, dl
0x18002a16e  lea     rbp, WPP_RECORDER_INITIALIZED
0x18002a175  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18002a17c  setnz   r8b
0x18002a180  test    dl, dl
0x18002a182  jnz     short loc_18002A189
0x18002a184  test    r8b, r8b
0x18002a187  jz      short loc_18002A1B0
0x18002a189  lea     r9, WPP_a555314c10c534a6d8c11e317bc5bc21_Traceguids
0x18002a190  mov     [rsp+88h+var_50], r9
0x18002a195  mov     r9, [rcx+28h]
0x18002a199  mov     rcx, [rcx+10h]
0x18002a19d  mov     [rsp+88h+var_58], 21h ; '!'
0x18002a1a4  call    WPP_RECORDER_AND_TRACE_SF_s
0x18002a1a9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a1b0  mov     esi, 8000FFFFh
0x18002a1b5  test    r14, r14
0x18002a1b8  jz      short loc_18002A1CA
0x18002a1ba  mov     rcx, r14; lpCriticalSection
0x18002a1bd  call    cs:__imp_LeaveCriticalSection
0x18002a1c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a1ca  test    r15b, r15b
0x18002a1cd  jz      loc_18002A2DB
0x18002a1d3  mov     rdx, [rdi+58h]
0x18002a1d7  lea     rcx, aBthTelemetryda; "BTH_TELEMETRYDATA_PREPAIRING_INITIAL_HW"...
0x18002a1de  mov     rdx, [rdx+30h]
0x18002a1e2  call    cs:__imp_?BthProcessEventOccurrenceBthaddr@@YAXPEBD_K@Z; BthProcessEventOccurrenceBthaddr(char const *,unsigned __int64)
0x18002a1e8  lea     rcx, [rsp+88h+arg_0]
0x18002a1f0  mov     [rsp+88h+arg_0], rdi
0x18002a1f8  call    wil__ResultFromException__lambda_69d4ebafcdfc875e4eef5671220ca470___
0x18002a1fd  mov     esi, eax
0x18002a1ff  test    eax, eax
0x18002a201  jns     loc_18002A2D4
0x18002a207  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a20e  cmp     rcx, r12
0x18002a211  jz      short loc_18002A21D
0x18002a213  cmp     byte ptr [rcx+19h], 2
0x18002a217  jb      short loc_18002A21D
0x18002a219  mov     dl, bl
0x18002a21b  jmp     short loc_18002A21F
0x18002a21d  xor     dl, dl
0x18002a21f  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18002a226  setnz   r8b
0x18002a22a  test    dl, dl
0x18002a22c  jnz     short loc_18002A233
0x18002a22e  test    r8b, r8b
0x18002a231  jz      short loc_18002A257
0x18002a233  mov     dword ptr [rsp+88h+var_40], eax
0x18002a237  lea     r9, WPP_a555314c10c534a6d8c11e317bc5bc21_Traceguids
0x18002a23e  mov     [rsp+88h+var_50], r9
0x18002a243  mov     r9, [rcx+28h]
0x18002a247  mov     rcx, [rcx+10h]
0x18002a24b  mov     [rsp+88h+var_58], 23h ; '#'
0x18002a252  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18002a257  mov     rcx, rdi; this
0x18002a25a  call    ?ResetPairingState@BthLEPrepairingController@BthLEPrepairing@Bluetooth@Internal@Windows@@AEAAXXZ; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::ResetPairingState(void)
0x18002a25f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a266  xor     eax, eax
0x18002a268  cmp     byte ptr [rcx+19h], 2
0x18002a26c  setnb   al
0x18002a26f  cmp     rcx, r12
0x18002a272  jz      short loc_18002A278
0x18002a274  test    eax, eax
0x18002a276  jnz     short loc_18002A27A
0x18002a278  xor     bl, bl
0x18002a27a  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x18002a281  setnz   r8b
0x18002a285  test    bl, bl
0x18002a287  jnz     short loc_18002A28E
0x18002a289  test    r8b, r8b
0x18002a28c  jz      short loc_18002A2B9
0x18002a28e  mov     r9, [rcx+28h]
0x18002a292  lea     rdx, WPP_a555314c10c534a6d8c11e317bc5bc21_Traceguids
0x18002a299  mov     rcx, [rcx+10h]
0x18002a29d  mov     [rsp+88h+var_38], esi
0x18002a2a1  mov     [rsp+88h+var_40], rdi
0x18002a2a6  mov     [rsp+88h+var_50], rdx
0x18002a2ab  mov     dl, bl
0x18002a2ad  mov     [rsp+88h+var_58], 24h ; '$'
0x18002a2b4  call    WPP_RECORDER_AND_TRACE_SF_sqd
0x18002a2b9  lea     r11, [rsp+88h+var_28]
0x18002a2be  mov     eax, esi
0x18002a2c0  mov     rbx, [r11+38h]
0x18002a2c4  mov     rbp, [r11+40h]
0x18002a2c8  mov     rsp, r11
0x18002a2cb  pop     r15
0x18002a2cd  pop     r14
0x18002a2cf  pop     r12
0x18002a2d1  pop     rdi
0x18002a2d2  pop     rsi
0x18002a2d3  retn
0x18002a2d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a2db  test    esi, esi
0x18002a2dd  jnz     short loc_18002A266
0x18002a2df  xor     eax, eax
0x18002a2e1  cmp     byte ptr [rcx+19h], 5
0x18002a2e5  jmp     short loc_18002A26C
```
