# BthUsb_ScoValidateChnInfo(_DEVICE_EXTENSION *,ulong *,ulong *)

- ea: `0x140006104`
- end: `0x140006310`
- name: `?BthUsb_ScoValidateChnInfo@@YAJPEAU_DEVICE_EXTENSION@@PEAK1@Z`
- size: `524`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, unsigned int *, unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1400030e0`
- `0x140019f30`

## callees

- `0x14000175c`
- `0x1400017d4`
- `0x140005f60`
- `0x140006104`
- `0x140006db0`
- `0x14000700c`

## pseudocode

```c
__int64 __fastcall BthUsb_ScoValidateChnInfo(struct _DEVICE_EXTENSION *a1, unsigned int *a2, unsigned int *a3)
{
  unsigned int *v4; // r14
  char v6; // bl
  int v7; // edx
  int v8; // edi
  int v9; // edx
  int v10; // r8d
  unsigned int v11; // ecx
  unsigned int v13; // [rsp+98h] [rbp+10h] BYREF
  unsigned int v14; // [rsp+A0h] [rbp+18h] BYREF

  v4 = a2;
  v6 = 1;
  LOBYTE(a2) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u;
  WPP_RECORDER_AND_TRACE_SF_qdd(
    WPP_GLOBAL_Control->AttachedDevice,
    (_DWORD)a2,
    (_DWORD)a3,
    WPP_GLOBAL_Control->DeviceExtension);
  v13 = *v4;
  v14 = *a3;
  v8 = BthUsb_ScoValidateAndAdjustBandwidth(a1, &v13);
  if ( v8 >= 0 )
  {
    v8 = BthUsb_ScoValidateAndAdjustBandwidth(a1, &v14);
    if ( v8 >= 0 )
    {
      v11 = v14;
      if ( v14 || v13 )
      {
        *v4 = v13;
        v8 = 0;
        *a3 = v11;
      }
      else
      {
        LOBYTE(v9) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
        WPP_RECORDER_AND_TRACE_SF_(
          WPP_GLOBAL_Control->AttachedDevice,
          v9,
          v10,
          WPP_GLOBAL_Control->DeviceExtension,
          2,
          4,
          43,
          (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids);
        v8 = -1073741811;
      }
    }
    else
    {
      LOBYTE(v9) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
      WPP_RECORDER_AND_TRACE_SF_dd(
        WPP_GLOBAL_Control->AttachedDevice,
        v9,
        v10,
        WPP_GLOBAL_Control->DeviceExtension,
        2,
        4,
        42,
        (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids,
        *a3,
        v14);
    }
  }
  else
  {
    LOBYTE(v7) = (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    WPP_RECORDER_AND_TRACE_SF_dd(
      WPP_GLOBAL_Control->AttachedDevice,
      v7,
      (_DWORD)WPP_GLOBAL_Control,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      4,
      41,
      (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids,
      *v4,
      v13);
  }
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    v6 = 0;
  LOBYTE(v9) = v6;
  WPP_RECORDER_AND_TRACE_SF_D(
    WPP_GLOBAL_Control->AttachedDevice,
    v9,
    v10,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    4,
    44,
    (__int64)WPP_89eaa7be148f36a90e353489c15db76f_Traceguids,
    v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140006104  mov     [rsp+arg_0], rbx
0x140006109  mov     [rsp+arg_18], rbp
0x14000610e  push    rsi
0x14000610f  push    rdi
0x140006110  push    r13
0x140006112  push    r14
0x140006114  push    r15
0x140006116  sub     rsp, 60h
0x14000611a  mov     rsi, r8
0x14000611d  mov     r14, rdx
0x140006120  mov     rbp, rcx
0x140006123  mov     rcx, cs:WPP_GLOBAL_Control
0x14000612a  mov     bl, 1
0x14000612c  mov     r15d, 4
0x140006132  mov     eax, [rcx+2Ch]
0x140006135  test    al, 8
0x140006137  jz      short loc_140006143
0x140006139  cmp     [rcx+29h], r15b
0x14000613d  jb      short loc_140006143
0x14000613f  mov     dl, bl
0x140006141  jmp     short loc_140006145
0x140006143  xor     dl, dl
0x140006145  mov     eax, [r8]
0x140006148  lea     r13, WPP_89eaa7be148f36a90e353489c15db76f_Traceguids
0x14000614f  mov     r9, [rcx+40h]
0x140006153  mov     rcx, [rcx+18h]
0x140006157  mov     [rsp+88h+var_38], eax
0x14000615b  mov     eax, [r14]
0x14000615e  mov     [rsp+88h+var_40], eax
0x140006162  mov     [rsp+88h+var_48], rbp
0x140006167  mov     [rsp+88h+var_50], r13
0x14000616c  mov     [rsp+88h+var_58], 28h ; '('
0x140006173  mov     [rsp+88h+var_60], r15d
0x140006178  call    WPP_RECORDER_AND_TRACE_SF_qdd
0x14000617d  mov     eax, [r14]
0x140006180  lea     rdx, [rsp+88h+arg_8]; unsigned int *
0x140006188  mov     [rsp+88h+arg_8], eax
0x14000618f  mov     rcx, rbp; struct _DEVICE_EXTENSION *
0x140006192  mov     eax, [rsi]
0x140006194  mov     [rsp+88h+arg_10], eax
0x14000619b  call    ?BthUsb_ScoValidateAndAdjustBandwidth@@YAJPEAU_DEVICE_EXTENSION@@PEAK@Z; BthUsb_ScoValidateAndAdjustBandwidth(_DEVICE_EXTENSION *,ulong *)
0x1400061a0  mov     edi, eax
0x1400061a2  test    eax, eax
0x1400061a4  jns     short loc_1400061FD
0x1400061a6  mov     r8, cs:WPP_GLOBAL_Control
0x1400061ad  mov     ecx, [r8+2Ch]
0x1400061b1  test    cl, 8
0x1400061b4  jz      short loc_1400061C1
0x1400061b6  cmp     byte ptr [r8+29h], 2
0x1400061bb  jb      short loc_1400061C1
0x1400061bd  mov     dl, bl
0x1400061bf  jmp     short loc_1400061C3
0x1400061c1  xor     dl, dl
0x1400061c3  mov     eax, [rsp+88h+arg_8]
0x1400061ca  mov     r9, [r8+40h]
0x1400061ce  mov     rcx, [r8+18h]
0x1400061d2  mov     [rsp+88h+var_40], eax
0x1400061d6  mov     eax, [r14]
0x1400061d9  mov     dword ptr [rsp+88h+var_48], eax
0x1400061dd  mov     [rsp+88h+var_50], r13
0x1400061e2  mov     [rsp+88h+var_58], 29h ; ')'
0x1400061e9  mov     [rsp+88h+var_60], r15d
0x1400061ee  mov     [rsp+88h+var_68], 2
0x1400061f3  call    WPP_RECORDER_AND_TRACE_SF_dd
0x1400061f8  jmp     loc_1400062B5
0x1400061fd  lea     rdx, [rsp+88h+arg_10]; unsigned int *
0x140006205  mov     rcx, rbp; struct _DEVICE_EXTENSION *
0x140006208  call    ?BthUsb_ScoValidateAndAdjustBandwidth@@YAJPEAU_DEVICE_EXTENSION@@PEAK@Z; BthUsb_ScoValidateAndAdjustBandwidth(_DEVICE_EXTENSION *,ulong *)
0x14000620d  mov     edi, eax
0x14000620f  test    eax, eax
0x140006211  jns     short loc_140006254
0x140006213  mov     rcx, cs:WPP_GLOBAL_Control
0x14000621a  mov     eax, [rcx+2Ch]
0x14000621d  test    al, 8
0x14000621f  jz      short loc_14000622B
0x140006221  cmp     byte ptr [rcx+29h], 2
0x140006225  jb      short loc_14000622B
0x140006227  mov     dl, bl
0x140006229  jmp     short loc_14000622D
0x14000622b  xor     dl, dl
0x14000622d  mov     eax, [rsp+88h+arg_10]
0x140006234  mov     r9, [rcx+40h]
0x140006238  mov     rcx, [rcx+18h]
0x14000623c  mov     [rsp+88h+var_40], eax
0x140006240  mov     eax, [rsi]
0x140006242  mov     dword ptr [rsp+88h+var_48], eax
0x140006246  mov     [rsp+88h+var_50], r13
0x14000624b  mov     [rsp+88h+var_58], 2Ah ; '*'
0x140006252  jmp     short loc_1400061E9
0x140006254  mov     ecx, [rsp+88h+arg_10]
0x14000625b  mov     eax, [rsp+88h+arg_8]
0x140006262  test    ecx, ecx
0x140006264  jnz     short loc_1400062AE
0x140006266  test    eax, eax
0x140006268  jnz     short loc_1400062AE
0x14000626a  mov     rcx, cs:WPP_GLOBAL_Control
0x140006271  mov     eax, [rcx+2Ch]
0x140006274  test    al, 8
0x140006276  jz      short loc_140006282
0x140006278  cmp     byte ptr [rcx+29h], 2
0x14000627c  jb      short loc_140006282
0x14000627e  mov     dl, bl
0x140006280  jmp     short loc_140006284
0x140006282  xor     dl, dl
0x140006284  mov     r9, [rcx+40h]
0x140006288  mov     rcx, [rcx+18h]
0x14000628c  mov     [rsp+88h+var_50], r13
0x140006291  mov     [rsp+88h+var_58], 2Bh ; '+'
0x140006298  mov     [rsp+88h+var_60], r15d
0x14000629d  mov     [rsp+88h+var_68], 2
0x1400062a2  call    WPP_RECORDER_AND_TRACE_SF_
0x1400062a7  mov     edi, 0C000000Dh
0x1400062ac  jmp     short loc_1400062B5
0x1400062ae  mov     [r14], eax
0x1400062b1  xor     edi, edi
0x1400062b3  mov     [rsi], ecx
0x1400062b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400062bc  mov     eax, [rcx+2Ch]
0x1400062bf  test    al, 8
0x1400062c1  jz      short loc_1400062C9
0x1400062c3  cmp     [rcx+29h], r15b
0x1400062c7  jnb     short loc_1400062CB
0x1400062c9  xor     bl, bl
0x1400062cb  mov     r9, [rcx+40h]
0x1400062cf  mov     dl, bl
0x1400062d1  mov     rcx, [rcx+18h]
0x1400062d5  mov     dword ptr [rsp+88h+var_48], edi
0x1400062d9  mov     [rsp+88h+var_50], r13
0x1400062de  mov     [rsp+88h+var_58], 2Ch ; ','
0x1400062e5  mov     [rsp+88h+var_60], r15d
0x1400062ea  mov     [rsp+88h+var_68], r15b
0x1400062ef  call    WPP_RECORDER_AND_TRACE_SF_D
0x1400062f4  lea     r11, [rsp+88h+var_28]
0x1400062f9  mov     eax, edi
0x1400062fb  mov     rbx, [r11+30h]
0x1400062ff  mov     rbp, [r11+48h]
0x140006303  mov     rsp, r11
0x140006306  pop     r15
0x140006308  pop     r14
0x14000630a  pop     r13
0x14000630c  pop     rdi
0x14000630d  pop     rsi
0x14000630e  retn
```
