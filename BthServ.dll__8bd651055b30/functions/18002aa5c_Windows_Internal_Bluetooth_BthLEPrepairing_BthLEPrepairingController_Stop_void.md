# Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::Stop(void)

- ea: `0x18002aa5c`
- end: `0x18002abe1`
- name: `?Stop@BthLEPrepairingController@BthLEPrepairing@Bluetooth@Internal@Windows@@QEAAJXZ`
- size: `389`
- prototype: `__int64 __fastcall(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18000eaec`
- `0x180029864`

## callees

- `0x1800110fc`
- `0x18001140c`
- `0x18002aa5c`
- `0x18002abe8`
- `0x18002aec0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002aadd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002aadd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ab55`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002ab55`

## pseudocode

```c
__int64 __fastcall Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::Stop(
        Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *this)
{
  char v2; // bl
  bool v3; // dl
  unsigned int v4; // esi
  char v5; // r14
  int v6; // ecx
  _BYTE *v7; // rcx
  bool v8; // dl
  unsigned int v9; // eax
  int v10; // edx
  bool v11; // cf
  int v13; // [rsp+20h] [rbp-88h]
  int v14; // [rsp+28h] [rbp-80h]

  v2 = 1;
  v3 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v3,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  v4 = 0;
  v5 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v6 = *((_DWORD *)this + 2);
  if ( v6 )
  {
    if ( (unsigned int)(v6 - 1) <= 1 )
    {
      *((_DWORD *)this + 2) = 0;
      v5 = 1;
    }
    goto LABEL_18;
  }
  v4 = -2147483634;
  v7 = WPP_GLOBAL_Control;
  v8 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
  if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
LABEL_18:
    v7 = WPP_GLOBAL_Control;
  }
  if ( this != (Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController *)-48LL )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    v7 = WPP_GLOBAL_Control;
  }
  if ( v5 )
  {
    v9 = Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::StopInternal(this);
    v7 = WPP_GLOBAL_Control;
    v4 = v9;
  }
  v10 = 0;
  if ( v4 )
    v11 = v7[25] < 2u;
  else
    v11 = v7[25] < 5u;
  if ( v7 == (_BYTE *)&WPP_GLOBAL_Control || (LOBYTE(v10) = !v11, !v10) )
    v2 = 0;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_sqd(
      *((_QWORD *)v7 + 2),
      v2,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)v7 + 5),
      v13,
      v14,
      16,
      (__int64)WPP_a555314c10c534a6d8c11e317bc5bc21_Traceguids);
  return v4;
}

```

## disassembly

```asm
0x18002aa5c  push    rbx
0x18002aa5e  push    rbp
0x18002aa5f  push    rsi
0x18002aa60  push    rdi
0x18002aa61  push    r12
0x18002aa63  push    r13
0x18002aa65  push    r14
0x18002aa67  push    r15
0x18002aa69  sub     rsp, 68h
0x18002aa6d  mov     rdi, rcx
0x18002aa70  mov     rcx, cs:WPP_GLOBAL_Control
0x18002aa77  lea     r15, WPP_GLOBAL_Control
0x18002aa7e  mov     bl, 1
0x18002aa80  cmp     rcx, r15
0x18002aa83  jz      short loc_18002AA8F
0x18002aa85  cmp     byte ptr [rcx+19h], 5
0x18002aa89  jb      short loc_18002AA8F
0x18002aa8b  mov     dl, bl
0x18002aa8d  jmp     short loc_18002AA91
0x18002aa8f  xor     dl, dl
0x18002aa91  lea     r12, WPP_RECORDER_INITIALIZED
0x18002aa98  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18002aa9f  lea     r13, WPP_a555314c10c534a6d8c11e317bc5bc21_Traceguids
0x18002aaa6  setnz   r8b
0x18002aaaa  test    dl, dl
0x18002aaac  jnz     short loc_18002AAB3
0x18002aaae  test    r8b, r8b
0x18002aab1  jz      short loc_18002AAD1
0x18002aab3  mov     r9, [rcx+28h]
0x18002aab7  mov     rcx, [rcx+10h]
0x18002aabb  mov     [rsp+0A8h+var_60], rdi
0x18002aac0  mov     [rsp+0A8h+var_70], r13
0x18002aac5  mov     [rsp+0A8h+var_78], 0Eh
0x18002aacc  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002aad1  lea     rbp, [rdi+30h]
0x18002aad5  xor     esi, esi
0x18002aad7  mov     rcx, rbp; lpCriticalSection
0x18002aada  xor     r14b, r14b
0x18002aadd  call    cs:__imp_EnterCriticalSection
0x18002aae3  mov     ecx, [rdi+8]
0x18002aae6  test    ecx, ecx
0x18002aae8  jz      short loc_18002AAFC
0x18002aaea  sub     ecx, 1
0x18002aaed  jz      short loc_18002AAF4
0x18002aaef  cmp     ecx, 1
0x18002aaf2  jnz     short loc_18002AB46
0x18002aaf4  mov     [rdi+8], esi
0x18002aaf7  mov     r14b, bl
0x18002aafa  jmp     short loc_18002AB46
0x18002aafc  mov     esi, 8000000Eh
0x18002ab01  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ab08  cmp     rcx, r15
0x18002ab0b  jz      short loc_18002AB17
0x18002ab0d  cmp     byte ptr [rcx+19h], 2
0x18002ab11  jb      short loc_18002AB17
0x18002ab13  mov     dl, bl
0x18002ab15  jmp     short loc_18002AB19
0x18002ab17  xor     dl, dl
0x18002ab19  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18002ab20  setnz   r8b
0x18002ab24  test    dl, dl
0x18002ab26  jnz     short loc_18002AB2D
0x18002ab28  test    r8b, r8b
0x18002ab2b  jz      short loc_18002AB4D
0x18002ab2d  mov     r9, [rcx+28h]
0x18002ab31  mov     rcx, [rcx+10h]
0x18002ab35  mov     [rsp+0A8h+var_70], r13
0x18002ab3a  mov     [rsp+0A8h+var_78], 0Fh
0x18002ab41  call    WPP_RECORDER_AND_TRACE_SF_s
0x18002ab46  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ab4d  test    rbp, rbp
0x18002ab50  jz      short loc_18002AB62
0x18002ab52  mov     rcx, rbp; lpCriticalSection
0x18002ab55  call    cs:__imp_LeaveCriticalSection
0x18002ab5b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ab62  test    r14b, r14b
0x18002ab65  jz      short loc_18002AB78
0x18002ab67  mov     rcx, rdi; this
0x18002ab6a  call    ?StopInternal@BthLEPrepairingController@BthLEPrepairing@Bluetooth@Internal@Windows@@AEAAJXZ; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingController::StopInternal(void)
0x18002ab6f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ab76  mov     esi, eax
0x18002ab78  xor     edx, edx
0x18002ab7a  test    esi, esi
0x18002ab7c  jnz     short loc_18002AB84
0x18002ab7e  cmp     byte ptr [rcx+19h], 5
0x18002ab82  jmp     short loc_18002AB88
0x18002ab84  cmp     byte ptr [rcx+19h], 2
0x18002ab88  setnb   dl
0x18002ab8b  cmp     rcx, r15
0x18002ab8e  jz      short loc_18002AB94
0x18002ab90  test    edx, edx
0x18002ab92  jnz     short loc_18002AB96
0x18002ab94  xor     bl, bl
0x18002ab96  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18002ab9d  setnz   r8b
0x18002aba1  test    bl, bl
0x18002aba3  jnz     short loc_18002ABAA
0x18002aba5  test    r8b, r8b
0x18002aba8  jz      short loc_18002ABCE
0x18002abaa  mov     r9, [rcx+28h]
0x18002abae  mov     dl, bl
0x18002abb0  mov     rcx, [rcx+10h]
0x18002abb4  mov     [rsp+0A8h+var_58], esi
0x18002abb8  mov     [rsp+0A8h+var_60], rdi
0x18002abbd  mov     [rsp+0A8h+var_70], r13
0x18002abc2  mov     [rsp+0A8h+var_78], 10h
0x18002abc9  call    WPP_RECORDER_AND_TRACE_SF_sqd
0x18002abce  mov     eax, esi
0x18002abd0  add     rsp, 68h
0x18002abd4  pop     r15
0x18002abd6  pop     r14
0x18002abd8  pop     r13
0x18002abda  pop     r12
0x18002abdc  pop     rdi
0x18002abdd  pop     rsi
0x18002abde  pop     rbp
0x18002abdf  pop     rbx
0x18002abe0  retn
```
