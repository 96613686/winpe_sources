# _lambda_b2b9bd25491ab1ca3973359f8f43bea9_::operator()

- ea: `0x18002d36c`
- end: `0x18002d618`
- name: `_lambda_b2b9bd25491ab1ca3973359f8f43bea9_::operator()`
- size: `684`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x18002c204`

## callees

- `0x1800034a0`
- `0x180010cac`
- `0x180011194`
- `0x18001140c`
- `0x18002aec0`
- `0x18002c19c`
- `0x18002d36c`
- `0x18002df04`
- `0x18002e8c8`

## string_xrefs

- `0x18002d521`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`
- `0x18002d592`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`
- `0x18002d603`: `onecore\drivers\wdm\bluetooth\libs\bthleprepairing\bthleprepairingdevice.cpp`

## pseudocode

```c
_DWORD *__fastcall lambda_b2b9bd25491ab1ca3973359f8f43bea9_::operator()(unsigned int **a1, __int64 a2, __int64 a3)
{
  unsigned int *v3; // rbx
  char v5; // di
  unsigned int v6; // eax
  int v7; // edx
  __int64 v8; // r8
  bool v9; // cf
  bool v10; // dl
  _DWORD *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  _DWORD *v14; // rax
  __int64 v15; // rdx
  __int64 v16; // r8
  _DWORD *result; // rax
  __int64 v18; // rdx
  unsigned int v19; // eax
  unsigned int v20; // eax
  unsigned int v21; // eax
  int v22; // [rsp+20h] [rbp-88h]
  int v23; // [rsp+28h] [rbp-80h]
  _QWORD v24[9]; // [rsp+60h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  unsigned int v26; // [rsp+B0h] [rbp+8h] BYREF

  v3 = a1[1];
  v5 = 1;
  LOBYTE(a2) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  LOBYTE(a3) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(*((_QWORD *)WPP_GLOBAL_Control + 2), a2, a3, *((_QWORD *)WPP_GLOBAL_Control + 5));
  v24[0] = v3;
  v24[1] = &v26;
  v6 = wil::ResultFromException__lambda_8b2eda5c4de3e195837b02a7d86700e7___(v24, a2, a3);
  v7 = 0;
  v26 = v6;
  v8 = v6;
  if ( v6 )
    v9 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u;
  else
    v9 = *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u;
  v10 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    LOBYTE(v7) = !v9;
    if ( v7 )
      v10 = 1;
  }
  if ( v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_sqd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v22,
      v23,
      74,
      (__int64)WPP_95fda3e624973c89daad3dc985e66758_Traceguids);
    v8 = v26;
  }
  **a1 = v8;
  v12 = **a1;
  if ( (int)v12 < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      v5 = 0;
    LOBYTE(v8) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = v5;
      WPP_RECORDER_AND_TRACE_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        v8,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v22,
        v23,
        67,
        (__int64)WPP_95fda3e624973c89daad3dc985e66758_Traceguids);
    }
    v19 = wil::verify_hresult<long>(**a1, v12, v8);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x278,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)v19,
      v22);
  }
  v11 = *a1;
  *v11 = Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::SelectCeremony((Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *)a1[1]);
  v15 = **a1;
  if ( (int)v15 < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      v5 = 0;
    LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v15) = v5;
      WPP_RECORDER_AND_TRACE_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v15,
        v13,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v22,
        v23,
        68,
        (__int64)WPP_95fda3e624973c89daad3dc985e66758_Traceguids);
    }
    v20 = wil::verify_hresult<long>(**a1, v15, v13);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x27F,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)v20,
      v22);
  }
  v14 = *a1;
  *v14 = Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::FinalizePairing((Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice *)a1[1]);
  result = *a1;
  v18 = **a1;
  if ( (int)v18 < 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      v5 = 0;
    LOBYTE(v16) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v18) = v5;
      WPP_RECORDER_AND_TRACE_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v18,
        v16,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v22,
        v23,
        69,
        (__int64)WPP_95fda3e624973c89daad3dc985e66758_Traceguids);
    }
    v21 = wil::verify_hresult<long>(**a1, v18, v16);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x286,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\libs\\bthleprepairing\\bthleprepairingdevice.cpp",
      (const char *)v21,
      v22);
  }
  return result;
}

```

## disassembly

```asm
0x18002d36c  push    rbx
0x18002d36e  push    rbp
0x18002d36f  push    rsi
0x18002d370  push    rdi
0x18002d371  push    r12
0x18002d373  push    r15
0x18002d375  sub     rsp, 78h
0x18002d379  mov     rbx, [rcx+8]
0x18002d37d  mov     rsi, rcx
0x18002d380  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d387  lea     rbp, WPP_GLOBAL_Control
0x18002d38e  mov     dil, 1
0x18002d391  cmp     rcx, rbp
0x18002d394  jz      short loc_18002D3A1
0x18002d396  cmp     byte ptr [rcx+19h], 5
0x18002d39a  jb      short loc_18002D3A1
0x18002d39c  mov     dl, dil
0x18002d39f  jmp     short loc_18002D3A3
0x18002d3a1  xor     dl, dl
0x18002d3a3  lea     r15, WPP_RECORDER_INITIALIZED
0x18002d3aa  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18002d3b1  lea     r12, WPP_95fda3e624973c89daad3dc985e66758_Traceguids
0x18002d3b8  setnz   r8b
0x18002d3bc  test    dl, dl
0x18002d3be  jnz     short loc_18002D3C5
0x18002d3c0  test    r8b, r8b
0x18002d3c3  jz      short loc_18002D3E3
0x18002d3c5  mov     r9, [rcx+28h]
0x18002d3c9  mov     rcx, [rcx+10h]
0x18002d3cd  mov     [rsp+0A8h+var_60], rbx
0x18002d3d2  mov     [rsp+0A8h+var_70], r12
0x18002d3d7  mov     [rsp+0A8h+var_78], 47h ; 'G'
0x18002d3de  call    WPP_RECORDER_AND_TRACE_SF_si
0x18002d3e3  lea     rax, [rsp+0A8h+arg_0]
0x18002d3eb  mov     [rsp+0A8h+var_48], rbx
0x18002d3f0  lea     rcx, [rsp+0A8h+var_48]
0x18002d3f5  mov     [rsp+0A8h+var_40], rax
0x18002d3fa  call    wil__ResultFromException__lambda_8b2eda5c4de3e195837b02a7d86700e7___
0x18002d3ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d406  xor     edx, edx
0x18002d408  mov     [rsp+0A8h+arg_0], eax
0x18002d40f  mov     r8d, eax
0x18002d412  test    eax, eax
0x18002d414  jnz     short loc_18002D41C
0x18002d416  cmp     byte ptr [rcx+19h], 5
0x18002d41a  jmp     short loc_18002D420
0x18002d41c  cmp     byte ptr [rcx+19h], 2
0x18002d420  setnb   dl
0x18002d423  cmp     rcx, rbp
0x18002d426  jz      short loc_18002D431
0x18002d428  test    edx, edx
0x18002d42a  jz      short loc_18002D431
0x18002d42c  mov     dl, dil
0x18002d42f  jmp     short loc_18002D433
0x18002d431  xor     dl, dl
0x18002d433  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18002d43a  setnz   al
0x18002d43d  test    dl, dl
0x18002d43f  jnz     short loc_18002D445
0x18002d441  test    al, al
0x18002d443  jz      short loc_18002D473
0x18002d445  mov     r9, [rcx+28h]
0x18002d449  mov     rcx, [rcx+10h]
0x18002d44d  mov     [rsp+0A8h+var_58], r8d
0x18002d452  mov     r8b, al
0x18002d455  mov     [rsp+0A8h+var_60], rbx
0x18002d45a  mov     [rsp+0A8h+var_70], r12
0x18002d45f  mov     [rsp+0A8h+var_78], 4Ah ; 'J'
0x18002d466  call    WPP_RECORDER_AND_TRACE_SF_sqd
0x18002d46b  mov     r8d, [rsp+0A8h+arg_0]
0x18002d473  mov     rax, [rsi]
0x18002d476  mov     [rax], r8d
0x18002d479  mov     rax, [rsi]
0x18002d47c  mov     edx, [rax]
0x18002d47e  test    edx, edx
0x18002d480  js      short loc_18002D4C5
0x18002d482  mov     rcx, [rsi+8]; this
0x18002d486  mov     rbx, rax
0x18002d489  call    ?SelectCeremony@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@AEAAJXZ; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::SelectCeremony(void)
0x18002d48e  mov     [rbx], eax
0x18002d490  mov     rax, [rsi]
0x18002d493  mov     edx, [rax]
0x18002d495  test    edx, edx
0x18002d497  js      loc_18002D536
0x18002d49d  mov     rcx, [rsi+8]; this
0x18002d4a1  mov     rbx, rax
0x18002d4a4  call    ?FinalizePairing@BthLEPrepairingDevice@BthLEPrepairing@Bluetooth@Internal@Windows@@AEAAJXZ; Windows::Internal::Bluetooth::BthLEPrepairing::BthLEPrepairingDevice::FinalizePairing(void)
0x18002d4a9  mov     [rbx], eax
0x18002d4ab  mov     rax, [rsi]
0x18002d4ae  mov     edx, [rax]
0x18002d4b0  test    edx, edx
0x18002d4b2  js      loc_18002D5A7
0x18002d4b8  add     rsp, 78h
0x18002d4bc  pop     r15
0x18002d4be  pop     r12
0x18002d4c0  pop     rdi
0x18002d4c1  pop     rsi
0x18002d4c2  pop     rbp
0x18002d4c3  pop     rbx
0x18002d4c4  retn
0x18002d4c5  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d4cc  cmp     rcx, rbp
0x18002d4cf  jz      short loc_18002D4D7
0x18002d4d1  cmp     byte ptr [rcx+19h], 2
0x18002d4d5  jnb     short loc_18002D4DA
0x18002d4d7  xor     dil, dil
0x18002d4da  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18002d4e1  setnz   r8b
0x18002d4e5  test    dil, dil
0x18002d4e8  jnz     short loc_18002D4EF
0x18002d4ea  test    r8b, r8b
0x18002d4ed  jz      short loc_18002D50F
0x18002d4ef  mov     r9, [rcx+28h]
0x18002d4f3  mov     rcx, [rcx+10h]
0x18002d4f7  mov     dword ptr [rsp+0A8h+var_60], edx
0x18002d4fb  mov     dl, dil
0x18002d4fe  mov     [rsp+0A8h+var_70], r12
0x18002d503  mov     [rsp+0A8h+var_78], 43h ; 'C'
0x18002d50a  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18002d50f  mov     rcx, [rsi]
0x18002d512  mov     ecx, [rcx]
0x18002d514  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002d519  mov     rcx, [rsp+0A8h]; this
0x18002d521  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x18002d528  mov     r9d, eax; char *
0x18002d52b  mov     edx, 278h; void *
0x18002d530  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002d536  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d53d  cmp     rcx, rbp
0x18002d540  jz      short loc_18002D548
0x18002d542  cmp     byte ptr [rcx+19h], 2
0x18002d546  jnb     short loc_18002D54B
0x18002d548  xor     dil, dil
0x18002d54b  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18002d552  setnz   r8b
0x18002d556  test    dil, dil
0x18002d559  jnz     short loc_18002D560
0x18002d55b  test    r8b, r8b
0x18002d55e  jz      short loc_18002D580
0x18002d560  mov     r9, [rcx+28h]
0x18002d564  mov     rcx, [rcx+10h]
0x18002d568  mov     dword ptr [rsp+0A8h+var_60], edx
0x18002d56c  mov     dl, dil
0x18002d56f  mov     [rsp+0A8h+var_70], r12
0x18002d574  mov     [rsp+0A8h+var_78], 44h ; 'D'
0x18002d57b  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18002d580  mov     rcx, [rsi]
0x18002d583  mov     ecx, [rcx]
0x18002d585  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002d58a  mov     rcx, [rsp+0A8h]; this
0x18002d592  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x18002d599  mov     r9d, eax; char *
0x18002d59c  mov     edx, 27Fh; void *
0x18002d5a1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002d5a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d5ae  cmp     rcx, rbp
0x18002d5b1  jz      short loc_18002D5B9
0x18002d5b3  cmp     byte ptr [rcx+19h], 2
0x18002d5b7  jnb     short loc_18002D5BC
0x18002d5b9  xor     dil, dil
0x18002d5bc  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18002d5c3  setnz   r8b
0x18002d5c7  test    dil, dil
0x18002d5ca  jnz     short loc_18002D5D1
0x18002d5cc  test    r8b, r8b
0x18002d5cf  jz      short loc_18002D5F1
0x18002d5d1  mov     r9, [rcx+28h]
0x18002d5d5  mov     rcx, [rcx+10h]
0x18002d5d9  mov     dword ptr [rsp+0A8h+var_60], edx
0x18002d5dd  mov     dl, dil
0x18002d5e0  mov     [rsp+0A8h+var_70], r12
0x18002d5e5  mov     [rsp+0A8h+var_78], 45h ; 'E'
0x18002d5ec  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18002d5f1  mov     rcx, [rsi]
0x18002d5f4  mov     ecx, [rcx]
0x18002d5f6  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002d5fb  mov     rcx, [rsp+0A8h]; this
0x18002d603  lea     r8, aOnecoreDrivers_6; "onecore\\drivers\\wdm\\bluetooth\\libs"...
0x18002d60a  mov     r9d, eax; char *
0x18002d60d  mov     edx, 286h; void *
0x18002d612  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
