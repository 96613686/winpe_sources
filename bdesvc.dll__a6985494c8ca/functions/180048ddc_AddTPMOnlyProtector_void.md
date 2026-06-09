# AddTPMOnlyProtector(void *)

- ea: `0x180048ddc`
- end: `0x180048f1e`
- name: `?AddTPMOnlyProtector@@YAJPEAX@Z`
- size: `322`
- prototype: `__int64 __fastcall(void *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18004b698`

## callees

- `0x180009f60`
- `0x180034070`
- `0x180048ddc`

## import_xrefs

- `FVEAPI!FveIsHardwareReadyForConversion` at `0x180048e54`
- `FVEAPI!FveIsHardwareReadyForConversion` at `0x180048e54`
- `FVEAPI!FveAddAuthMethodInformation` at `0x180048ec0`
- `FVEAPI!FveAddAuthMethodInformation` at `0x180048ec0`

## pseudocode

```c
__int64 __fastcall AddTPMOnlyProtector(void *a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  unsigned int IsHardwareReadyForConversion; // eax
  unsigned int v10; // eax
  __int128 v12; // [rsp+20h] [rbp-58h] BYREF
  __int128 v13; // [rsp+30h] [rbp-48h]
  __int128 v14; // [rsp+40h] [rbp-38h]
  __int64 v15; // [rsp+50h] [rbp-28h]
  __int128 v16; // [rsp+58h] [rbp-20h] BYREF

  v15 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  v16 = 0;
  if ( a1 == (void *)-1LL )
  {
    v5 = -2147024809;
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      v7 = 214;
      v8 = 2147942487LL;
LABEL_14:
      WPP_SF_d(v6[2], v7, &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids, v8);
    }
  }
  else
  {
    IsHardwareReadyForConversion = FveIsHardwareReadyForConversion(
                                     a1,
                                     a2,
                                     a3,
                                     a4,
                                     v12,
                                     *((_QWORD *)&v12 + 1),
                                     v13,
                                     *((_QWORD *)&v13 + 1),
                                     v14);
    v5 = IsHardwareReadyForConversion;
    if ( !IsHardwareReadyForConversion )
      goto LABEL_12;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        215,
        &WPP_951aaf4f82a831773594a9234edf98f2_Traceguids,
        IsHardwareReadyForConversion);
    if ( v5 >= 0 )
    {
LABEL_12:
      *(_QWORD *)&v12 = 0x100000038LL;
      DWORD2(v12) = 0x20000;
      v10 = FveAddAuthMethodInformation(a1, &v12, &v16);
      v5 = v10;
      if ( v10 )
      {
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          v7 = 216;
          v8 = v10;
          goto LABEL_14;
        }
      }
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180048ddc  mov     [rsp+arg_8], rbx
0x180048de1  mov     [rsp+arg_10], rsi
0x180048de6  push    rdi
0x180048de7  sub     rsp, 70h
0x180048deb  mov     rax, cs:__security_cookie
0x180048df2  xor     rax, rsp
0x180048df5  mov     [rsp+78h+var_10], rax
0x180048dfa  xorps   xmm0, xmm0
0x180048dfd  xor     eax, eax
0x180048dff  mov     [rsp+78h+var_28], rax
0x180048e04  mov     rsi, rcx
0x180048e07  movups  [rsp+78h+var_58], xmm0
0x180048e0c  movups  [rsp+78h+var_48], xmm0
0x180048e11  movups  [rsp+78h+var_38], xmm0
0x180048e16  movups  [rsp+78h+var_20], xmm0
0x180048e1b  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180048e1f  jnz     short loc_180048E54
0x180048e21  mov     ebx, 80070057h
0x180048e26  mov     rcx, cs:WPP_GLOBAL_Control
0x180048e2d  lea     rdi, WPP_GLOBAL_Control
0x180048e34  cmp     rcx, rdi
0x180048e37  jz      loc_180048EFC
0x180048e3d  test    byte ptr [rcx+1Ch], 40h
0x180048e41  jz      loc_180048EFC
0x180048e47  mov     edx, 0D6h
0x180048e4c  mov     r9d, ebx
0x180048e4f  jmp     loc_180048EEC
0x180048e54  call    cs:__imp_FveIsHardwareReadyForConversion
0x180048e5b  nop     dword ptr [rax+rax+00h]
0x180048e60  lea     rdi, WPP_GLOBAL_Control
0x180048e67  mov     ebx, eax
0x180048e69  test    eax, eax
0x180048e6b  jz      short loc_180048E9B
0x180048e6d  mov     rcx, cs:WPP_GLOBAL_Control
0x180048e74  cmp     rcx, rdi
0x180048e77  jz      short loc_180048E97
0x180048e79  test    byte ptr [rcx+1Ch], 40h
0x180048e7d  jz      short loc_180048E97
0x180048e7f  mov     rcx, [rcx+10h]
0x180048e83  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x180048e8a  mov     edx, 0D7h
0x180048e8f  mov     r9d, eax
0x180048e92  call    WPP_SF_d
0x180048e97  test    ebx, ebx
0x180048e99  js      short loc_180048EFC
0x180048e9b  lea     r8, [rsp+78h+var_20]
0x180048ea0  mov     dword ptr [rsp+78h+var_58], 38h ; '8'
0x180048ea8  lea     rdx, [rsp+78h+var_58]
0x180048ead  mov     dword ptr [rsp+78h+var_58+4], 1
0x180048eb5  mov     rcx, rsi
0x180048eb8  mov     dword ptr [rsp+78h+var_58+8], 20000h
0x180048ec0  call    cs:__imp_FveAddAuthMethodInformation
0x180048ec7  nop     dword ptr [rax+rax+00h]
0x180048ecc  mov     ebx, eax
0x180048ece  test    eax, eax
0x180048ed0  jz      short loc_180048EFC
0x180048ed2  mov     rcx, cs:WPP_GLOBAL_Control
0x180048ed9  cmp     rcx, rdi
0x180048edc  jz      short loc_180048EFC
0x180048ede  test    byte ptr [rcx+1Ch], 40h
0x180048ee2  jz      short loc_180048EFC
0x180048ee4  mov     edx, 0D8h
0x180048ee9  mov     r9d, eax
0x180048eec  mov     rcx, [rcx+10h]
0x180048ef0  lea     r8, WPP_951aaf4f82a831773594a9234edf98f2_Traceguids
0x180048ef7  call    WPP_SF_d
0x180048efc  mov     eax, ebx
0x180048efe  mov     rcx, [rsp+78h+var_10]
0x180048f03  xor     rcx, rsp; StackCookie
0x180048f06  call    __security_check_cookie
0x180048f0b  lea     r11, [rsp+78h+var_8]
0x180048f10  mov     rbx, [r11+18h]
0x180048f14  mov     rsi, [r11+20h]
0x180048f18  mov     rsp, r11
0x180048f1b  pop     rdi
0x180048f1c  retn
```
