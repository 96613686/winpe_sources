# Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::Start(void)

- ea: `0x18002ecb8`
- end: `0x18002ef97`
- name: `?Start@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@QEAAJXZ`
- size: `735`
- prototype: `__int64 __fastcall(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002acf0`

## callees

- `0x1800110fc`
- `0x180011194`
- `0x18001140c`
- `0x18002aec0`
- `0x18002e13c`
- `0x18002ecb8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002ee64`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002ee64`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::Start(
        Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *this)
{
  _BYTE *v2; // rcx
  char v3; // di
  bool v4; // dl
  int v5; // edx
  int v6; // esi
  int v7; // r8d
  int v8; // edx
  int v9; // edx
  signed __int32 v10; // eax
  struct _TP_TIMER *v11; // rcx
  bool v12; // dl
  BOOL v13; // eax
  bool v14; // dl
  int v16; // [rsp+20h] [rbp-78h]
  int v17; // [rsp+28h] [rbp-70h]
  struct _FILETIME pftDueTime; // [rsp+A0h] [rbp+8h] BYREF

  v2 = WPP_GLOBAL_Control;
  v3 = 1;
  v4 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v4,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v2 = WPP_GLOBAL_Control;
  }
  if ( *((_DWORD *)this + 11) == 3 )
  {
    v6 = 0;
    v14 = v2 != (_BYTE *)&WPP_GLOBAL_Control && v2[25] >= 4u;
    if ( v14 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_AND_TRACE_SF_s(
        *((_QWORD *)v2 + 2),
        v14,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        *((_QWORD *)v2 + 5));
      v2 = WPP_GLOBAL_Control;
    }
    goto LABEL_53;
  }
  *((_BYTE *)this + 144) = 0;
  v6 = Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::IncomingLEOobPairing(this);
  if ( v6 >= 0 )
  {
    if ( *((_BYTE *)this + 144) )
    {
      *((_DWORD *)this + 11) = 1;
      *((_DWORD *)this + 14) = 0;
    }
    else
    {
      v2 = WPP_GLOBAL_Control;
      v12 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
      if ( !v12 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
LABEL_44:
        if ( v6 )
          goto LABEL_45;
LABEL_53:
        v13 = v2[25] >= 5u;
        goto LABEL_54;
      }
      WPP_RECORDER_AND_TRACE_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
LABEL_43:
    v2 = WPP_GLOBAL_Control;
    goto LABEL_44;
  }
  v2 = WPP_GLOBAL_Control;
  LOBYTE(v5) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  if ( (_BYTE)v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      v7,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v16,
      v17,
      29,
      (__int64)WPP_95fda3e624973c89daad3dc985e66758_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  v8 = *((_DWORD *)this + 11);
  if ( !v8 || (v9 = v8 - 1) == 0 )
  {
    *((_DWORD *)this + 11) = 2;
    goto LABEL_33;
  }
  if ( v9 != 1 )
    goto LABEL_44;
  LOBYTE(v9) = v2 != (_BYTE *)&WPP_GLOBAL_Control && v2[25] >= 4u;
  if ( (_BYTE)v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_sd(
      *((_QWORD *)v2 + 2),
      v9,
      v7,
      *((_QWORD *)v2 + 5),
      v16,
      v17,
      30,
      (__int64)WPP_95fda3e624973c89daad3dc985e66758_Traceguids);
  }
  ++*((_DWORD *)this + 14);
  v10 = _InterlockedCompareExchange((volatile signed __int32 *)this + 20, 1, 0);
  if ( *((_DWORD *)this + 14) <= 3u || v10 || !*((_QWORD *)this + 9) || *((_DWORD *)this + 35) )
    goto LABEL_43;
  v11 = (struct _TP_TIMER *)*((_QWORD *)this + 9);
  *((_DWORD *)this + 11) = 3;
  pftDueTime = (struct _FILETIME)-300000000LL;
  SetThreadpoolTimer(v11, &pftDueTime, 0, 0);
LABEL_33:
  v2 = WPP_GLOBAL_Control;
LABEL_45:
  v13 = v2[25] >= 2u;
LABEL_54:
  if ( v2 == (_BYTE *)&WPP_GLOBAL_Control || !v13 )
    v3 = 0;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_sqd(
      *((_QWORD *)v2 + 2),
      v3,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)v2 + 5),
      v16,
      v17,
      33,
      (__int64)WPP_95fda3e624973c89daad3dc985e66758_Traceguids);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18002ecb8  push    rbx
0x18002ecba  push    rsi
0x18002ecbb  push    rdi
0x18002ecbc  push    r12
0x18002ecbe  push    r14
0x18002ecc0  push    r15
0x18002ecc2  sub     rsp, 68h
0x18002ecc6  mov     rbx, rcx
0x18002ecc9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ecd0  lea     r14, WPP_GLOBAL_Control
0x18002ecd7  mov     edi, 1
0x18002ecdc  cmp     rcx, r14
0x18002ecdf  jz      short loc_18002ECEC
0x18002ece1  cmp     byte ptr [rcx+19h], 5
0x18002ece5  jb      short loc_18002ECEC
0x18002ece7  mov     dl, dil
0x18002ecea  jmp     short loc_18002ECEE
0x18002ecec  xor     dl, dl
0x18002ecee  lea     r15, WPP_RECORDER_INITIALIZED
0x18002ecf5  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18002ecfc  lea     r12, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002ed03  setnz   r8b
0x18002ed07  test    dl, dl
0x18002ed09  jnz     short loc_18002ED10
0x18002ed0b  test    r8b, r8b
0x18002ed0e  jz      short loc_18002ED35
0x18002ed10  mov     r9, [rcx+28h]
0x18002ed14  mov     rcx, [rcx+10h]
0x18002ed18  mov     [rsp+98h+var_50], rbx
0x18002ed1d  mov     [rsp+98h+var_60], r12
0x18002ed22  mov     [rsp+98h+var_68], 1Ch
0x18002ed29  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002ed2e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ed35  cmp     dword ptr [rbx+2Ch], 3
0x18002ed39  jz      loc_18002EEF0
0x18002ed3f  mov     rcx, rbx; this
0x18002ed42  mov     byte ptr [rbx+90h], 0
0x18002ed49  call    ?IncomingLEOobPairing@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@AEAAJXZ; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::IncomingLEOobPairing(void)
0x18002ed4e  mov     esi, eax
0x18002ed50  test    eax, eax
0x18002ed52  jns     loc_18002EE7C
0x18002ed58  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ed5f  cmp     rcx, r14
0x18002ed62  jz      short loc_18002ED6F
0x18002ed64  cmp     byte ptr [rcx+19h], 4
0x18002ed68  jb      short loc_18002ED6F
0x18002ed6a  mov     dl, dil
0x18002ed6d  jmp     short loc_18002ED71
0x18002ed6f  xor     dl, dl
0x18002ed71  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18002ed78  setnz   r8b
0x18002ed7c  test    dl, dl
0x18002ed7e  jnz     short loc_18002ED85
0x18002ed80  test    r8b, r8b
0x18002ed83  jz      short loc_18002EDA9
0x18002ed85  mov     r9, [rcx+28h]
0x18002ed89  mov     rcx, [rcx+10h]
0x18002ed8d  mov     dword ptr [rsp+98h+var_50], esi
0x18002ed91  mov     [rsp+98h+var_60], r12
0x18002ed96  mov     [rsp+98h+var_68], 1Dh
0x18002ed9d  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18002eda2  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eda9  mov     edx, [rbx+2Ch]
0x18002edac  test    edx, edx
0x18002edae  jz      loc_18002EE6C
0x18002edb4  sub     edx, edi
0x18002edb6  jz      loc_18002EE6C
0x18002edbc  cmp     edx, edi
0x18002edbe  jnz     loc_18002EEDE
0x18002edc4  cmp     rcx, r14
0x18002edc7  jz      short loc_18002EDD4
0x18002edc9  cmp     byte ptr [rcx+19h], 4
0x18002edcd  jb      short loc_18002EDD4
0x18002edcf  mov     dl, dil
0x18002edd2  jmp     short loc_18002EDD6
0x18002edd4  xor     dl, dl
0x18002edd6  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18002eddd  setnz   r8b
0x18002ede1  test    dl, dl
0x18002ede3  jnz     short loc_18002EDEA
0x18002ede5  test    r8b, r8b
0x18002ede8  jz      short loc_18002EE0A
0x18002edea  mov     eax, [rbx+38h]
0x18002eded  mov     r9, [rcx+28h]
0x18002edf1  mov     rcx, [rcx+10h]
0x18002edf5  mov     dword ptr [rsp+98h+var_50], eax
0x18002edf9  mov     [rsp+98h+var_60], r12
0x18002edfe  mov     [rsp+98h+var_68], 1Eh
0x18002ee05  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18002ee0a  add     [rbx+38h], edi
0x18002ee0d  xor     eax, eax
0x18002ee0f  lock cmpxchg [rbx+50h], edi
0x18002ee14  cmp     dword ptr [rbx+38h], 3
0x18002ee18  jbe     loc_18002EED7
0x18002ee1e  test    eax, eax
0x18002ee20  jnz     loc_18002EED7
0x18002ee26  cmp     qword ptr [rbx+48h], 0
0x18002ee2b  jz      loc_18002EED7
0x18002ee31  mov     eax, [rbx+8Ch]
0x18002ee37  test    eax, eax
0x18002ee39  jnz     loc_18002EED7
0x18002ee3f  mov     rcx, [rbx+48h]; pti
0x18002ee43  lea     rdx, [rsp+98h+pftDueTime]; pftDueTime
0x18002ee4b  xor     r9d, r9d; msWindowLength
0x18002ee4e  mov     dword ptr [rbx+2Ch], 3
0x18002ee55  xor     r8d, r8d; msPeriod
0x18002ee58  mov     qword ptr [rsp+98h+pftDueTime.dwLowDateTime], 0FFFFFFFFEE1E5D00h
0x18002ee64  call    cs:__imp_SetThreadpoolTimer
0x18002ee6a  jmp     short loc_18002EE73
0x18002ee6c  mov     dword ptr [rbx+2Ch], 2
0x18002ee73  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ee7a  jmp     short loc_18002EEE2
0x18002ee7c  cmp     byte ptr [rbx+90h], 0
0x18002ee83  jz      short loc_18002EE91
0x18002ee85  mov     [rbx+2Ch], edi
0x18002ee88  mov     dword ptr [rbx+38h], 0
0x18002ee8f  jmp     short loc_18002EED7
0x18002ee91  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ee98  cmp     rcx, r14
0x18002ee9b  jz      short loc_18002EEA8
0x18002ee9d  cmp     byte ptr [rcx+19h], 2
0x18002eea1  jb      short loc_18002EEA8
0x18002eea3  mov     dl, dil
0x18002eea6  jmp     short loc_18002EEAA
0x18002eea8  xor     dl, dl
0x18002eeaa  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18002eeb1  setnz   r8b
0x18002eeb5  test    dl, dl
0x18002eeb7  jnz     short loc_18002EEBE
0x18002eeb9  test    r8b, r8b
0x18002eebc  jz      short loc_18002EEDE
0x18002eebe  mov     r9, [rcx+28h]
0x18002eec2  mov     rcx, [rcx+10h]
0x18002eec6  mov     [rsp+98h+var_60], r12
0x18002eecb  mov     [rsp+98h+var_68], 1Fh
0x18002eed2  call    WPP_RECORDER_AND_TRACE_SF_s
0x18002eed7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002eede  test    esi, esi
0x18002eee0  jz      short loc_18002EF38
0x18002eee2  cmp     byte ptr [rcx+19h], 2
0x18002eee6  jb      short loc_18002EEEC
0x18002eee8  mov     eax, edi
0x18002eeea  jmp     short loc_18002EF41
0x18002eeec  xor     eax, eax
0x18002eeee  jmp     short loc_18002EF41
0x18002eef0  xor     esi, esi
0x18002eef2  cmp     rcx, r14
0x18002eef5  jz      short loc_18002EF02
0x18002eef7  cmp     byte ptr [rcx+19h], 4
0x18002eefb  jb      short loc_18002EF02
0x18002eefd  mov     dl, dil
0x18002ef00  jmp     short loc_18002EF04
0x18002ef02  xor     dl, dl
0x18002ef04  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18002ef0b  setnz   r8b
0x18002ef0f  test    dl, dl
0x18002ef11  jnz     short loc_18002EF18
0x18002ef13  test    r8b, r8b
0x18002ef16  jz      short loc_18002EF38
0x18002ef18  mov     r9, [rcx+28h]
0x18002ef1c  mov     rcx, [rcx+10h]
0x18002ef20  mov     [rsp+98h+var_60], r12
0x18002ef25  mov     [rsp+98h+var_68], 20h ; ' '
0x18002ef2c  call    WPP_RECORDER_AND_TRACE_SF_s
0x18002ef31  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ef38  xor     eax, eax
0x18002ef3a  cmp     byte ptr [rcx+19h], 5
0x18002ef3e  setnb   al
0x18002ef41  cmp     rcx, r14
0x18002ef44  jz      short loc_18002EF4A
0x18002ef46  test    eax, eax
0x18002ef48  jnz     short loc_18002EF4D
0x18002ef4a  xor     dil, dil
0x18002ef4d  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18002ef54  setnz   r8b
0x18002ef58  test    dil, dil
0x18002ef5b  jnz     short loc_18002EF62
0x18002ef5d  test    r8b, r8b
0x18002ef60  jz      short loc_18002EF87
0x18002ef62  mov     r9, [rcx+28h]
0x18002ef66  mov     dl, dil
0x18002ef69  mov     rcx, [rcx+10h]
0x18002ef6d  mov     [rsp+98h+var_48], esi
0x18002ef71  mov     [rsp+98h+var_50], rbx
0x18002ef76  mov     [rsp+98h+var_60], r12
0x18002ef7b  mov     [rsp+98h+var_68], 21h ; '!'
0x18002ef82  call    WPP_RECORDER_AND_TRACE_SF_sqd
0x18002ef87  mov     eax, esi
0x18002ef89  add     rsp, 68h
0x18002ef8d  pop     r15
0x18002ef8f  pop     r14
0x18002ef91  pop     r12
0x18002ef93  pop     rdi
0x18002ef94  pop     rsi
0x18002ef95  pop     rbx
0x18002ef96  retn
```
