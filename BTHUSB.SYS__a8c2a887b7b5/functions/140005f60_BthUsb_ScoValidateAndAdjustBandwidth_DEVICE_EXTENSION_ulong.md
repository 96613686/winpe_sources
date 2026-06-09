# BthUsb_ScoValidateAndAdjustBandwidth(_DEVICE_EXTENSION *,ulong *)

- ea: `0x140005f60`
- end: `0x1400060fb`
- name: `?BthUsb_ScoValidateAndAdjustBandwidth@@YAJPEAU_DEVICE_EXTENSION@@PEAK@Z`
- size: `411`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x140006104`

## callees

- `0x1400017d4`
- `0x140001da0`
- `0x140005f60`
- `0x140006db0`

## pseudocode

```c
__int64 __fastcall BthUsb_ScoValidateAndAdjustBandwidth(struct _DEVICE_EXTENSION *a1, unsigned int *a2, int a3)
{
  unsigned int *v3; // rdi
  unsigned int v5; // esi
  char v6; // bl
  unsigned int v7; // edx
  unsigned int v8; // r9d
  unsigned int v9; // r8d

  v3 = a2;
  v5 = -1073741811;
  v6 = 1;
  LOBYTE(a2) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_qd(
    WPP_GLOBAL_Control->AttachedDevice,
    (_DWORD)a2,
    a3,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    4,
    36,
    (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids,
    (char)a1,
    *v3);
  v8 = *v3;
  if ( *v3 )
  {
    v7 = (v8 + 999) / 0x3E8;
    v9 = 1000 * v7;
    if ( 1000 * v7 < v8 )
    {
      LOBYTE(v7) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      WPP_RECORDER_AND_TRACE_SF_D(
        WPP_GLOBAL_Control->AttachedDevice,
        v7,
        v9,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        4,
        37,
        (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids,
        v8);
      goto LABEL_21;
    }
  }
  else
  {
    v9 = 0;
  }
  if ( v9 <= a1->Sco.MaxBandwidth && (v7 = v9 / 0x3E8, v9 == 1000 * (v9 / 0x3E8)) )
  {
    *v3 = v9;
    v5 = 0;
  }
  else
  {
    LOBYTE(v7) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    WPP_RECORDER_AND_TRACE_SF_dd(
      WPP_GLOBAL_Control->AttachedDevice,
      v7,
      v9,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      4,
      38,
      (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids,
      v8,
      v9);
  }
LABEL_21:
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    v6 = 0;
  LOBYTE(v7) = v6;
  WPP_RECORDER_AND_TRACE_SF_D(
    WPP_GLOBAL_Control->AttachedDevice,
    v7,
    v9,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    4,
    39,
    (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids,
    v5);
  return v5;
}

```

## disassembly

```asm
0x140005f60  push    rbx
0x140005f62  push    rbp
0x140005f63  push    rsi
0x140005f64  push    rdi
0x140005f65  push    r12
0x140005f67  sub     rsp, 50h
0x140005f6b  mov     rdi, rdx
0x140005f6e  mov     rbp, rcx
0x140005f71  mov     esi, 0C000000Dh
0x140005f76  mov     rcx, cs:WPP_GLOBAL_Control
0x140005f7d  mov     bl, 1
0x140005f7f  mov     eax, [rcx+2Ch]
0x140005f82  test    al, 8
0x140005f84  jz      short loc_140005F90
0x140005f86  cmp     byte ptr [rcx+29h], 4
0x140005f8a  jb      short loc_140005F90
0x140005f8c  mov     dl, bl
0x140005f8e  jmp     short loc_140005F92
0x140005f90  xor     dl, dl
0x140005f92  mov     eax, [rdi]
0x140005f94  lea     r12, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x140005f9b  mov     r9, [rcx+40h]
0x140005f9f  mov     rcx, [rcx+18h]
0x140005fa3  mov     [rsp+78h+var_30], eax
0x140005fa7  mov     [rsp+78h+var_38], rbp
0x140005fac  mov     [rsp+78h+var_40], r12
0x140005fb1  mov     [rsp+78h+var_48], 24h ; '$'
0x140005fb8  mov     [rsp+78h+var_50], 4
0x140005fc0  mov     [rsp+78h+var_58], 4
0x140005fc5  call    WPP_RECORDER_AND_TRACE_SF_qd
0x140005fca  mov     r9d, [rdi]
0x140005fcd  mov     r10d, 10624DD3h
0x140005fd3  test    r9d, r9d
0x140005fd6  jz      short loc_14000603A
0x140005fd8  lea     ecx, [r9+3E7h]
0x140005fdf  mov     eax, r10d
0x140005fe2  mul     ecx
0x140005fe4  shr     edx, 6
0x140005fe7  imul    r8d, edx, 3E8h
0x140005fee  cmp     r8d, r9d
0x140005ff1  jnb     short loc_14000603D
0x140005ff3  mov     rcx, cs:WPP_GLOBAL_Control
0x140005ffa  mov     eax, [rcx+2Ch]
0x140005ffd  test    al, 8
0x140005fff  jz      short loc_14000600B
0x140006001  cmp     byte ptr [rcx+29h], 2
0x140006005  jb      short loc_14000600B
0x140006007  mov     dl, bl
0x140006009  jmp     short loc_14000600D
0x14000600b  xor     dl, dl
0x14000600d  mov     dword ptr [rsp+78h+var_38], r9d
0x140006012  mov     r9, [rcx+40h]
0x140006016  mov     rcx, [rcx+18h]
0x14000601a  mov     [rsp+78h+var_40], r12
0x14000601f  mov     [rsp+78h+var_48], 25h ; '%'
0x140006026  mov     [rsp+78h+var_50], 4
0x14000602e  mov     [rsp+78h+var_58], 2
0x140006033  call    WPP_RECORDER_AND_TRACE_SF_D
0x140006038  jmp     short loc_1400060AB
0x14000603a  mov     r8d, r9d
0x14000603d  cmp     r8d, [rbp+2A8h]
0x140006044  ja      short loc_140006061
0x140006046  mov     eax, r10d
0x140006049  mul     r8d
0x14000604c  shr     edx, 6
0x14000604f  imul    ecx, edx, 3E8h
0x140006055  cmp     r8d, ecx
0x140006058  jnz     short loc_140006061
0x14000605a  mov     [rdi], r8d
0x14000605d  xor     esi, esi
0x14000605f  jmp     short loc_1400060AB
0x140006061  mov     rcx, cs:WPP_GLOBAL_Control
0x140006068  mov     eax, [rcx+2Ch]
0x14000606b  test    al, 8
0x14000606d  jz      short loc_140006079
0x14000606f  cmp     byte ptr [rcx+29h], 2
0x140006073  jb      short loc_140006079
0x140006075  mov     dl, bl
0x140006077  jmp     short loc_14000607B
0x140006079  xor     dl, dl
0x14000607b  mov     [rsp+78h+var_30], r8d
0x140006080  mov     dword ptr [rsp+78h+var_38], r9d
0x140006085  mov     r9, [rcx+40h]
0x140006089  mov     rcx, [rcx+18h]
0x14000608d  mov     [rsp+78h+var_40], r12
0x140006092  mov     [rsp+78h+var_48], 26h ; '&'
0x140006099  mov     [rsp+78h+var_50], 4
0x1400060a1  mov     [rsp+78h+var_58], 2
0x1400060a6  call    WPP_RECORDER_AND_TRACE_SF_dd
0x1400060ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400060b2  mov     eax, [rcx+2Ch]
0x1400060b5  test    al, 8
0x1400060b7  jz      short loc_1400060BF
0x1400060b9  cmp     byte ptr [rcx+29h], 4
0x1400060bd  jnb     short loc_1400060C1
0x1400060bf  xor     bl, bl
0x1400060c1  mov     r9, [rcx+40h]
0x1400060c5  mov     dl, bl
0x1400060c7  mov     rcx, [rcx+18h]
0x1400060cb  mov     dword ptr [rsp+78h+var_38], esi
0x1400060cf  mov     [rsp+78h+var_40], r12
0x1400060d4  mov     [rsp+78h+var_48], 27h ; '''
0x1400060db  mov     [rsp+78h+var_50], 4
0x1400060e3  mov     [rsp+78h+var_58], 4
0x1400060e8  call    WPP_RECORDER_AND_TRACE_SF_D
0x1400060ed  mov     eax, esi
0x1400060ef  add     rsp, 50h
0x1400060f3  pop     r12
0x1400060f5  pop     rdi
0x1400060f6  pop     rsi
0x1400060f7  pop     rbp
0x1400060f8  pop     rbx
0x1400060f9  retn
```
