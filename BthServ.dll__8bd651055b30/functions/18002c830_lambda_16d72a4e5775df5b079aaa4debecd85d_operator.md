# _lambda_16d72a4e5775df5b079aaa4debecd85d_::operator()

- ea: `0x18002c830`
- end: `0x18002cb7b`
- name: `_lambda_16d72a4e5775df5b079aaa4debecd85d_::operator()`
- size: `843`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18002c13c`

## callees

- `0x180001790`
- `0x1800034a0`
- `0x180010cac`
- `0x180011194`
- `0x18001140c`
- `0x18002aec0`
- `0x18002c224`
- `0x18002c830`
- `0x18002d914`
- `0x18002e020`
- `0x18002f9fc`

## string_xrefs

- `0x18002caf4`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`
- `0x18002cb66`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`

## pseudocode

```c
void __fastcall lambda_16d72a4e5775df5b079aaa4debecd85d_::operator()(__int64 a1, __int64 a2, __int64 a3)
{
  Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *v3; // rbx
  _BYTE *v5; // rcx
  char v6; // di
  bool v7; // dl
  _UNKNOWN **v8; // r9
  bool v9; // dl
  ULONGLONG v10; // rbx
  unsigned int v11; // eax
  int v12; // edx
  __int64 v13; // r8
  bool v14; // cf
  bool v15; // dl
  _DWORD *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  __int64 v21; // rdx
  __int64 v22; // rax
  unsigned int v23; // eax
  unsigned int v24; // eax
  int v25; // [rsp+20h] [rbp-A8h]
  int v26; // [rsp+28h] [rbp-A0h]
  unsigned int v27; // [rsp+60h] [rbp-68h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v28; // [rsp+68h] [rbp-60h] BYREF
  __int64 v29; // [rsp+78h] [rbp-50h]
  __int64 v30; // [rsp+80h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v3 = *(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice **)a1;
  v5 = WPP_GLOBAL_Control;
  v6 = 1;
  v7 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  v8 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v5 = WPP_GLOBAL_Control;
    v8 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  }
  dword_1800443F6 = *((_DWORD *)v3 + 12);
  word_1800443FA = WORD2(*((_QWORD *)v3 + 6));
  xmmword_1800443FE = *(_OWORD *)((char *)v3 + 25);
  qword_180044416 = *(_QWORD *)((char *)v3 + 17);
  v9 = v5 != (_BYTE *)&WPP_GLOBAL_Control && v5[25] >= 5u;
  if ( v9 || v8 != &WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_si(*((_QWORD *)v5 + 2), v9, v8 != &WPP_RECORDER_INITIALIZED, *((_QWORD *)v5 + 5));
    v5 = WPP_GLOBAL_Control;
    v8 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
  }
  v10 = *(_QWORD *)a1;
  LOBYTE(a2) = v5 != (_BYTE *)&WPP_GLOBAL_Control && v5[25] >= 5u;
  LOBYTE(a3) = v8 != &WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)a2 || v8 != &WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(*((_QWORD *)v5 + 2), a2, a3, *((_QWORD *)v5 + 5));
  v28.Ptr = v10;
  *(_QWORD *)&v28.Size = &v27;
  v11 = wil::ResultFromException__lambda_cb293c6ec7bc4deeec064c1f58322c0f___(&v28, a2, a3);
  v12 = 0;
  v27 = v11;
  v13 = v11;
  if ( v11 )
    v14 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u;
  else
    v14 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u;
  v15 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    LOBYTE(v12) = !v14;
    if ( v12 )
      v15 = 1;
  }
  if ( v15 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_sqd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v15,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v25,
      v26,
      56,
      (__int64)WPP_95fda3e624973c89daad3dc985e66758_Traceguids);
    v13 = v27;
  }
  **(_DWORD **)(a1 + 8) = v13;
  v16 = *(_DWORD **)(a1 + 8);
  v17 = (unsigned int)*v16;
  if ( (int)v17 < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      v6 = 0;
    LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v17) = v6;
      WPP_RECORDER_AND_TRACE_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v17,
        v13,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v25,
        v26,
        48,
        (__int64)WPP_95fda3e624973c89daad3dc985e66758_Traceguids);
    }
    v23 = wil::verify_hresult<long>(**(unsigned int **)(a1 + 8), v17, v13);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1EF,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)v23,
      v25);
  }
  *v16 = Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::FinishOobPairing(*(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice **)a1);
  v21 = **(unsigned int **)(a1 + 8);
  if ( (int)v21 < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      v6 = 0;
    LOBYTE(v19) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v21) = v6;
      WPP_RECORDER_AND_TRACE_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v21,
        v19,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v25,
        v26,
        49,
        (__int64)WPP_95fda3e624973c89daad3dc985e66758_Traceguids);
    }
    v24 = wil::verify_hresult<long>(**(unsigned int **)(a1 + 8), v21, v19);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1F6,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)v24,
      v25);
  }
  if ( (Microsoft_Windows_Bluetooth_BthLEPrepairingEnableBits & 1) != 0 )
  {
    v22 = *(_QWORD *)a1 + 17LL;
    v30 = 8;
    v29 = v22;
    McGenEventWrite_EventWriteTransfer(v18, v21, v19, v20, &v28);
  }
  Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::CleanupPreviousAssociations(*(Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice **)a1);
}

```

## disassembly

```asm
0x18002c830  push    rbx
0x18002c832  push    rbp
0x18002c833  push    rsi
0x18002c834  push    rdi
0x18002c835  push    r12
0x18002c837  push    r13
0x18002c839  sub     rsp, 98h
0x18002c840  mov     rax, cs:__security_cookie
0x18002c847  xor     rax, rsp
0x18002c84a  mov     [rsp+0C8h+var_40], rax
0x18002c852  mov     rbx, [rcx]
0x18002c855  mov     rsi, rcx
0x18002c858  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c85f  lea     rbp, WPP_GLOBAL_Control
0x18002c866  mov     dil, 1
0x18002c869  cmp     rcx, rbp
0x18002c86c  jz      short loc_18002C879
0x18002c86e  cmp     byte ptr [rcx+19h], 5
0x18002c872  jb      short loc_18002C879
0x18002c874  mov     dl, dil
0x18002c877  jmp     short loc_18002C87B
0x18002c879  xor     dl, dl
0x18002c87b  mov     r9, cs:WPP_RECORDER_INITIALIZED
0x18002c882  lea     r12, WPP_RECORDER_INITIALIZED
0x18002c889  cmp     r9, r12
0x18002c88c  lea     r13, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002c893  setnz   r8b
0x18002c897  test    dl, dl
0x18002c899  jnz     short loc_18002C8A0
0x18002c89b  test    r8b, r8b
0x18002c89e  jz      short loc_18002C8CC
0x18002c8a0  mov     r9, [rcx+28h]
0x18002c8a4  mov     rcx, [rcx+10h]
0x18002c8a8  mov     [rsp+0C8h+var_80], rbx
0x18002c8ad  mov     [rsp+0C8h+var_90], r13
0x18002c8b2  mov     [rsp+0C8h+var_98], 33h ; '3'
0x18002c8b9  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002c8be  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c8c5  mov     r9, cs:WPP_RECORDER_INITIALIZED
0x18002c8cc  mov     eax, [rbx+30h]
0x18002c8cf  mov     cs:dword_1800443F6, eax
0x18002c8d5  mov     rax, [rbx+30h]
0x18002c8d9  shr     rax, 20h
0x18002c8dd  mov     cs:word_1800443FA, ax
0x18002c8e4  movups  xmm0, xmmword ptr [rbx+19h]
0x18002c8e8  movdqu  cs:xmmword_1800443FE, xmm0
0x18002c8f0  mov     rax, [rbx+11h]
0x18002c8f4  mov     cs:qword_180044416, rax
0x18002c8fb  cmp     rcx, rbp
0x18002c8fe  jz      short loc_18002C90B
0x18002c900  cmp     byte ptr [rcx+19h], 5
0x18002c904  jb      short loc_18002C90B
0x18002c906  mov     dl, dil
0x18002c909  jmp     short loc_18002C90D
0x18002c90b  xor     dl, dl
0x18002c90d  cmp     r9, r12
0x18002c910  setnz   r8b
0x18002c914  test    dl, dl
0x18002c916  jnz     short loc_18002C91D
0x18002c918  test    r8b, r8b
0x18002c91b  jz      short loc_18002C949
0x18002c91d  mov     r9, [rcx+28h]
0x18002c921  mov     rcx, [rcx+10h]
0x18002c925  mov     [rsp+0C8h+var_80], rbx
0x18002c92a  mov     [rsp+0C8h+var_90], r13
0x18002c92f  mov     [rsp+0C8h+var_98], 34h ; '4'
0x18002c936  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002c93b  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c942  mov     r9, cs:WPP_RECORDER_INITIALIZED
0x18002c949  mov     rbx, [rsi]
0x18002c94c  cmp     rcx, rbp
0x18002c94f  jz      short loc_18002C95C
0x18002c951  cmp     byte ptr [rcx+19h], 5
0x18002c955  jb      short loc_18002C95C
0x18002c957  mov     dl, dil
0x18002c95a  jmp     short loc_18002C95E
0x18002c95c  xor     dl, dl
0x18002c95e  cmp     r9, r12
0x18002c961  setnz   r8b
0x18002c965  test    dl, dl
0x18002c967  jnz     short loc_18002C96E
0x18002c969  test    r8b, r8b
0x18002c96c  jz      short loc_18002C98C
0x18002c96e  mov     r9, [rcx+28h]
0x18002c972  mov     rcx, [rcx+10h]
0x18002c976  mov     [rsp+0C8h+var_80], rbx
0x18002c97b  mov     [rsp+0C8h+var_90], r13
0x18002c980  mov     [rsp+0C8h+var_98], 35h ; '5'
0x18002c987  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002c98c  lea     rax, [rsp+0C8h+var_68]
0x18002c991  mov     [rsp+0C8h+var_60.Ptr], rbx
0x18002c996  lea     rcx, [rsp+0C8h+var_60]
0x18002c99b  mov     qword ptr [rsp+0C8h+var_60.Size], rax
0x18002c9a0  call    wil__ResultFromException__lambda_cb293c6ec7bc4deeec064c1f58322c0f___
0x18002c9a5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c9ac  xor     edx, edx
0x18002c9ae  mov     [rsp+0C8h+var_68], eax
0x18002c9b2  mov     r8d, eax
0x18002c9b5  test    eax, eax
0x18002c9b7  jnz     short loc_18002C9BF
0x18002c9b9  cmp     byte ptr [rcx+19h], 5
0x18002c9bd  jmp     short loc_18002C9C3
0x18002c9bf  cmp     byte ptr [rcx+19h], 2
0x18002c9c3  setnb   dl
0x18002c9c6  cmp     rcx, rbp
0x18002c9c9  jz      short loc_18002C9D4
0x18002c9cb  test    edx, edx
0x18002c9cd  jz      short loc_18002C9D4
0x18002c9cf  mov     dl, dil
0x18002c9d2  jmp     short loc_18002C9D6
0x18002c9d4  xor     dl, dl
0x18002c9d6  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18002c9dd  setnz   al
0x18002c9e0  test    dl, dl
0x18002c9e2  jnz     short loc_18002C9E8
0x18002c9e4  test    al, al
0x18002c9e6  jz      short loc_18002CA13
0x18002c9e8  mov     r9, [rcx+28h]
0x18002c9ec  mov     rcx, [rcx+10h]
0x18002c9f0  mov     [rsp+0C8h+var_78], r8d
0x18002c9f5  mov     r8b, al
0x18002c9f8  mov     [rsp+0C8h+var_80], rbx
0x18002c9fd  mov     [rsp+0C8h+var_90], r13
0x18002ca02  mov     [rsp+0C8h+var_98], 38h ; '8'
0x18002ca09  call    WPP_RECORDER_AND_TRACE_SF_sqd
0x18002ca0e  mov     r8d, [rsp+0C8h+var_68]
0x18002ca13  mov     rax, [rsi+8]
0x18002ca17  mov     [rax], r8d
0x18002ca1a  mov     rax, [rsi+8]
0x18002ca1e  mov     edx, [rax]
0x18002ca20  test    edx, edx
0x18002ca22  js      short loc_18002CA97
0x18002ca24  mov     rcx, [rsi]; this
0x18002ca27  mov     rbx, rax
0x18002ca2a  call    ?FinishOobPairing@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@AEAAJXZ; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::FinishOobPairing(void)
0x18002ca2f  mov     [rbx], eax
0x18002ca31  mov     rax, [rsi+8]
0x18002ca35  mov     edx, [rax]; int
0x18002ca37  test    edx, edx
0x18002ca39  js      loc_18002CB09
0x18002ca3f  test    cs:Microsoft_Windows_Bluetooth_BthLEPrepairingEnableBits, dil
0x18002ca46  jz      short loc_18002CA6F
0x18002ca48  mov     rax, [rsi]
0x18002ca4b  add     rax, 11h
0x18002ca4f  mov     [rsp+0C8h+var_48], 8
0x18002ca5b  mov     [rsp+0C8h+var_50], rax
0x18002ca60  lea     rax, [rsp+0C8h+var_60]
0x18002ca65  mov     [rsp+0C8h+var_A8], rax; PEVENT_DATA_DESCRIPTOR
0x18002ca6a  call    McGenEventWrite_EventWriteTransfer
0x18002ca6f  mov     rcx, [rsi]; this
0x18002ca72  call    ?CleanupPreviousAssociations@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@AEAAXXZ; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::CleanupPreviousAssociations(void)
0x18002ca77  mov     rcx, [rsp+0C8h+var_40]
0x18002ca7f  xor     rcx, rsp; StackCookie
0x18002ca82  call    __security_check_cookie
0x18002ca87  add     rsp, 98h
0x18002ca8e  pop     r13
0x18002ca90  pop     r12
0x18002ca92  pop     rdi
0x18002ca93  pop     rsi
0x18002ca94  pop     rbp
0x18002ca95  pop     rbx
0x18002ca96  retn
0x18002ca97  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ca9e  cmp     rcx, rbp
0x18002caa1  jz      short loc_18002CAA9
0x18002caa3  cmp     byte ptr [rcx+19h], 2
0x18002caa7  jnb     short loc_18002CAAC
0x18002caa9  xor     dil, dil
0x18002caac  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18002cab3  setnz   r8b
0x18002cab7  test    dil, dil
0x18002caba  jnz     short loc_18002CAC1
0x18002cabc  test    r8b, r8b
0x18002cabf  jz      short loc_18002CAE1
0x18002cac1  mov     r9, [rcx+28h]
0x18002cac5  mov     rcx, [rcx+10h]
0x18002cac9  mov     dword ptr [rsp+0C8h+var_80], edx
0x18002cacd  mov     dl, dil
0x18002cad0  mov     [rsp+0C8h+var_90], r13
0x18002cad5  mov     [rsp+0C8h+var_98], 30h ; '0'
0x18002cadc  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18002cae1  mov     rcx, [rsi+8]
0x18002cae5  mov     ecx, [rcx]
0x18002cae7  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002caec  mov     rcx, [rsp+0C8h]; this
0x18002caf4  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x18002cafb  mov     r9d, eax; char *
0x18002cafe  mov     edx, 1EFh; void *
0x18002cb03  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002cb09  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cb10  cmp     rcx, rbp
0x18002cb13  jz      short loc_18002CB1B
0x18002cb15  cmp     byte ptr [rcx+19h], 2
0x18002cb19  jnb     short loc_18002CB1E
0x18002cb1b  xor     dil, dil
0x18002cb1e  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18002cb25  setnz   r8b
0x18002cb29  test    dil, dil
0x18002cb2c  jnz     short loc_18002CB33
0x18002cb2e  test    r8b, r8b
0x18002cb31  jz      short loc_18002CB53
0x18002cb33  mov     r9, [rcx+28h]
0x18002cb37  mov     rcx, [rcx+10h]
0x18002cb3b  mov     dword ptr [rsp+0C8h+var_80], edx
0x18002cb3f  mov     dl, dil
0x18002cb42  mov     [rsp+0C8h+var_90], r13
0x18002cb47  mov     [rsp+0C8h+var_98], 31h ; '1'
0x18002cb4e  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18002cb53  mov     rcx, [rsi+8]
0x18002cb57  mov     ecx, [rcx]
0x18002cb59  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002cb5e  mov     rcx, [rsp+0C8h]; this
0x18002cb66  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x18002cb6d  mov     r9d, eax; char *
0x18002cb70  mov     edx, 1F6h; void *
0x18002cb75  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
