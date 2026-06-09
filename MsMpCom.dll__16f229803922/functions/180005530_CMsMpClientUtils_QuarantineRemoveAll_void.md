# CMsMpClientUtils::QuarantineRemoveAll(void)

- ea: `0x180005530`
- end: `0x180005684`
- name: `?QuarantineRemoveAll@CMsMpClientUtils@@UEAAJXZ`
- size: `340`
- prototype: `__int64 __fastcall(CMsMpClientUtils *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180004b7c`
- `0x180005530`
- `0x180005944`
- `0x180005b0c`
- `0x180009440`

## import_xrefs

- `mpclient!MpThreatEnumerate` at `0x180005638`
- `mpclient!MpThreatEnumerate` at `0x180005638`
- `mpclient!MpHandleClose` at `0x18000565b`
- `mpclient!MpHandleClose` at `0x18000565b`
- `mpclient!MpThreatOpen` at `0x18000559d`
- `mpclient!MpThreatOpen` at `0x18000559d`
- `mpclient!MpQuarantineRequest` at `0x1800055f1`
- `mpclient!MpQuarantineRequest` at `0x1800055f1`

## pseudocode

```c
__int64 __fastcall CMsMpClientUtils::QuarantineRemoveAll(CMsMpClientUtils *this)
{
  __int64 v2; // rcx
  int v3; // eax
  __int64 v4; // rcx
  int v5; // ebx
  char v6; // di
  __int64 v7; // rcx
  int v8; // eax
  char *v10; // [rsp+20h] [rbp-40h]
  __int64 v11; // [rsp+30h] [rbp-30h] BYREF
  __int64 v12; // [rsp+38h] [rbp-28h] BYREF
  __int128 v13; // [rsp+40h] [rbp-20h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v10 = (char *)this - 64;
    WPP_SF_sq(*((_QWORD *)WPP_GLOBAL_Control + 2), 12);
  }
  v2 = *((_QWORD *)this + 1);
  v11 = 0;
  v3 = MpThreatOpen(v2, 3, 0, &v11, v10);
  v4 = v11;
  v5 = v3;
  if ( v3 >= 0 )
  {
    v6 = 0;
    while ( 1 )
    {
      v12 = 0;
      v5 = MpThreatEnumerate(v4, &v12);
      if ( v5 < 0 )
        break;
      if ( v5 == 1 )
      {
        v5 = v6 != 0;
        break;
      }
      v13 = *(_OWORD *)(v12 + 112);
      MPTHREAT_INFO_FREE();
      v7 = *((_QWORD *)this + 1);
      v12 = 0;
      v8 = MpQuarantineRequest(v7, &v13, 1);
      if ( v8 < 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            &WPP_85f567f30ac03a1b1e78961f0afc6072_Traceguids,
            (unsigned int)v8);
        v6 = 1;
      }
      v4 = v11;
    }
    v4 = v11;
  }
  if ( v4 )
    MpHandleClose(v4);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180005530  mov     [rsp-18h+arg_8], rbx
0x180005535  mov     [rsp-18h+arg_10], rsi
0x18000553a  push    rbp
0x18000553b  push    rdi
0x18000553c  push    r15
0x18000553e  mov     rbp, rsp
0x180005541  sub     rsp, 60h
0x180005545  mov     rax, cs:__security_cookie
0x18000554c  xor     rax, rsp
0x18000554f  mov     [rbp+var_10], rax
0x180005553  mov     rsi, rcx
0x180005556  mov     rcx, cs:WPP_GLOBAL_Control
0x18000555d  lea     r15, WPP_GLOBAL_Control
0x180005564  cmp     rcx, r15
0x180005567  jz      short loc_180005586
0x180005569  test    byte ptr [rcx+1Ch], 8
0x18000556d  jz      short loc_180005586
0x18000556f  mov     rcx, [rcx+10h]
0x180005573  lea     rax, [rsi-40h]
0x180005577  mov     edx, 0Ch
0x18000557c  mov     [rsp+60h+var_40], rax
0x180005581  call    WPP_SF_sq
0x180005586  mov     rcx, [rsi+8]
0x18000558a  lea     r9, [rbp+var_30]
0x18000558e  xor     r8d, r8d
0x180005591  mov     [rbp+var_30], 0
0x180005599  lea     edx, [r8+3]
0x18000559d  call    cs:__imp_MpThreatOpen
0x1800055a3  mov     rcx, [rbp+var_30]
0x1800055a7  mov     ebx, eax
0x1800055a9  test    eax, eax
0x1800055ab  js      loc_180005656
0x1800055b1  xor     dil, dil
0x1800055b4  jmp     short loc_18000562C
0x1800055b6  cmp     ebx, 1
0x1800055b9  jz      loc_18000564A
0x1800055bf  mov     rcx, [rbp+var_28]
0x1800055c3  movups  xmm0, xmmword ptr [rcx+70h]
0x1800055c7  movdqu  [rbp+var_20], xmm0
0x1800055cc  call    MPTHREAT_INFO_FREE
0x1800055d1  mov     rcx, [rsi+8]
0x1800055d5  lea     rdx, [rbp+var_20]
0x1800055d9  xor     r9d, r9d
0x1800055dc  mov     [rbp+var_28], 0
0x1800055e4  mov     [rsp+60h+var_40], 0
0x1800055ed  lea     r8d, [r9+1]
0x1800055f1  call    cs:__imp_MpQuarantineRequest
0x1800055f7  test    eax, eax
0x1800055f9  jns     short loc_180005628
0x1800055fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180005602  cmp     rcx, r15
0x180005605  jz      short loc_180005625
0x180005607  test    byte ptr [rcx+1Ch], 1
0x18000560b  jz      short loc_180005625
0x18000560d  mov     rcx, [rcx+10h]
0x180005611  lea     r8, WPP_85f567f30ac03a1b1e78961f0afc6072_Traceguids
0x180005618  mov     edx, 0Dh
0x18000561d  mov     r9d, eax
0x180005620  call    WPP_SF_d
0x180005625  mov     dil, 1
0x180005628  mov     rcx, [rbp+var_30]
0x18000562c  lea     rdx, [rbp+var_28]
0x180005630  mov     [rbp+var_28], 0
0x180005638  call    cs:__imp_MpThreatEnumerate
0x18000563e  mov     ebx, eax
0x180005640  test    eax, eax
0x180005642  jns     loc_1800055B6
0x180005648  jmp     short loc_180005652
0x18000564a  xor     ebx, ebx
0x18000564c  test    dil, dil
0x18000564f  setnz   bl
0x180005652  mov     rcx, [rbp+var_30]
0x180005656  test    rcx, rcx
0x180005659  jz      short loc_180005661
0x18000565b  call    cs:__imp_MpHandleClose
0x180005661  mov     eax, ebx
0x180005663  mov     rcx, [rbp+var_10]
0x180005667  xor     rcx, rsp; StackCookie
0x18000566a  call    __security_check_cookie
0x18000566f  lea     r11, [rsp+60h+var_s0]
0x180005674  mov     rbx, [r11+28h]
0x180005678  mov     rsi, [r11+30h]
0x18000567c  mov     rsp, r11
0x18000567f  pop     r15
0x180005681  pop     rdi
0x180005682  pop     rbp
0x180005683  retn
```
