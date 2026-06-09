# BdeSvcpResumeTPMProtectedOSVolume_Thread(void *)

- ea: `0x18004f540`
- end: `0x18004f7d6`
- name: `?BdeSvcpResumeTPMProtectedOSVolume_Thread@@YAIPEAX@Z`
- size: `662`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180009c30`
- `0x180009f30`
- `0x180009f60`
- `0x18000daf8`
- `0x180034070`
- `0x180034d28`
- `0x18004f540`
- `0x18004f900`

## import_xrefs

- `FVEAPI!FveDecrementClearKeyCounter` at `0x18004f6f3`
- `FVEAPI!FveDecrementClearKeyCounter` at `0x18004f6f3`
- `FVEAPI!FveOpenVolumeW` at `0x18004f60a`
- `FVEAPI!FveOpenVolumeW` at `0x18004f60a`
- `FVEAPI!FveGetStatus` at `0x18004f664`
- `FVEAPI!FveGetStatus` at `0x18004f664`
- `FVEAPI!FveCloseVolume` at `0x18004f77b`
- `FVEAPI!FveCloseVolume` at `0x18004f77b`

## pseudocode

```c
__int64 __fastcall BdeSvcpResumeTPMProtectedOSVolume_Thread(void *a1)
{
  unsigned int OSVolume; // eax
  int v2; // ebx
  unsigned int v3; // eax
  unsigned int Status; // eax
  PVOID *v5; // rcx
  unsigned int refreshed; // eax
  _QWORD *v7; // rcx
  __int64 v8; // rdx
  BdeSvcWorkTracking *v9; // rcx
  __int64 v11; // [rsp+20h] [rbp-E0h] BYREF
  _DWORD v12[3]; // [rsp+30h] [rbp-D0h] BYREF
  int v13; // [rsp+3Ch] [rbp-C4h]
  _BYTE v14[528]; // [rsp+C0h] [rbp-40h] BYREF

  memset_0(v12, 0, 0x90u);
  v11 = -1;
  memset_0(v14, 0, 0x208u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_5f44ebab715039561e5e3e58bbae32d1_Traceguids);
  OSVolume = NgscbGetOSVolume(v14);
  v2 = OSVolume;
  if ( !OSVolume )
    goto LABEL_13;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_5f44ebab715039561e5e3e58bbae32d1_Traceguids, OSVolume);
  if ( v2 >= 0 )
  {
LABEL_13:
    v3 = FveOpenVolumeW(v14, 0, &v11);
    v2 = v3;
    if ( !v3 )
      goto LABEL_14;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_5f44ebab715039561e5e3e58bbae32d1_Traceguids, v3);
    if ( v2 >= 0 )
    {
LABEL_14:
      v12[0] = 144;
      v12[1] = 10;
      Status = FveGetStatus(v11, v12);
      v2 = Status;
      if ( Status )
      {
        v5 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_5f44ebab715039561e5e3e58bbae32d1_Traceguids, Status);
          v5 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v2 < 0 )
          goto LABEL_39;
      }
      else
      {
        v5 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( (v13 & 1) != 0 && (v13 & 0x200) != 0 )
      {
        if ( (v13 & 0x400) != 0 )
        {
          if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 )
            WPP_SF_(v5[2], 27, WPP_5f44ebab715039561e5e3e58bbae32d1_Traceguids);
          refreshed = FveDecrementClearKeyCounter(v11, 0);
          v2 = refreshed;
          if ( refreshed )
          {
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            {
              v8 = 28;
LABEL_38:
              WPP_SF_d(v7[2], v8, WPP_5f44ebab715039561e5e3e58bbae32d1_Traceguids, refreshed);
            }
          }
        }
        else
        {
          if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 8) != 0 )
            WPP_SF_(v5[2], 29, WPP_5f44ebab715039561e5e3e58bbae32d1_Traceguids);
          refreshed = RefreshTpmBinding(2);
          v2 = refreshed;
          if ( refreshed )
          {
            v7 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
            {
              v8 = 30;
              goto LABEL_38;
            }
          }
        }
      }
    }
  }
LABEL_39:
  v9 = (BdeSvcWorkTracking *)v11;
  if ( v11 != -1 )
  {
    FveCloseVolume(v11);
    v11 = -1;
  }
  BdeSvcWorkTracking::FinishWorkImpl(v9);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_5f44ebab715039561e5e3e58bbae32d1_Traceguids);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18004f540  push    rbp
0x18004f542  push    rbx
0x18004f543  push    rsi
0x18004f544  push    rdi
0x18004f545  lea     rbp, [rsp-1E8h]
0x18004f54d  sub     rsp, 2E8h
0x18004f554  mov     rax, cs:__security_cookie
0x18004f55b  xor     rax, rsp
0x18004f55e  mov     [rbp+200h+var_30], rax
0x18004f565  xor     edx, edx; Val
0x18004f567  lea     rcx, [rsp+300h+var_2D0]; void *
0x18004f56c  mov     r8d, 90h; Size
0x18004f572  call    memset_0
0x18004f577  xor     edx, edx; Val
0x18004f579  mov     [rsp+300h+var_2E0], 0FFFFFFFFFFFFFFFFh
0x18004f582  mov     r8d, 208h; Size
0x18004f588  lea     rcx, [rbp+200h+var_240]; void *
0x18004f58c  call    memset_0
0x18004f591  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f598  lea     rdi, WPP_GLOBAL_Control
0x18004f59f  lea     rsi, WPP_5f44ebab715039561e5e3e58bbae32d1_Traceguids
0x18004f5a6  cmp     rcx, rdi
0x18004f5a9  jz      short loc_18004F5C2
0x18004f5ab  test    byte ptr [rcx+1Ch], 20h
0x18004f5af  jz      short loc_18004F5C2
0x18004f5b1  mov     rcx, [rcx+10h]
0x18004f5b5  mov     edx, 17h
0x18004f5ba  mov     r8, rsi
0x18004f5bd  call    WPP_SF_
0x18004f5c2  lea     rcx, [rbp+200h+var_240]
0x18004f5c6  call    NgscbGetOSVolume
0x18004f5cb  mov     ebx, eax
0x18004f5cd  test    eax, eax
0x18004f5cf  jz      short loc_18004F5FF
0x18004f5d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f5d8  cmp     rcx, rdi
0x18004f5db  jz      short loc_18004F5F7
0x18004f5dd  test    byte ptr [rcx+1Ch], 40h
0x18004f5e1  jz      short loc_18004F5F7
0x18004f5e3  mov     rcx, [rcx+10h]
0x18004f5e7  mov     edx, 18h
0x18004f5ec  mov     r9d, eax
0x18004f5ef  mov     r8, rsi
0x18004f5f2  call    WPP_SF_d
0x18004f5f7  test    ebx, ebx
0x18004f5f9  js      loc_18004F770
0x18004f5ff  lea     r8, [rsp+300h+var_2E0]
0x18004f604  xor     edx, edx
0x18004f606  lea     rcx, [rbp+200h+var_240]
0x18004f60a  call    cs:__imp_FveOpenVolumeW
0x18004f611  nop     dword ptr [rax+rax+00h]
0x18004f616  mov     ebx, eax
0x18004f618  test    eax, eax
0x18004f61a  jz      short loc_18004F64A
0x18004f61c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f623  cmp     rcx, rdi
0x18004f626  jz      short loc_18004F642
0x18004f628  test    byte ptr [rcx+1Ch], 40h
0x18004f62c  jz      short loc_18004F642
0x18004f62e  mov     rcx, [rcx+10h]
0x18004f632  mov     edx, 19h
0x18004f637  mov     r9d, eax
0x18004f63a  mov     r8, rsi
0x18004f63d  call    WPP_SF_d
0x18004f642  test    ebx, ebx
0x18004f644  js      loc_18004F770
0x18004f64a  mov     rcx, [rsp+300h+var_2E0]
0x18004f64f  lea     rdx, [rsp+300h+var_2D0]
0x18004f654  mov     [rsp+300h+var_2D0], 90h
0x18004f65c  mov     [rsp+300h+var_2CC], 0Ah
0x18004f664  call    cs:__imp_FveGetStatus
0x18004f66b  nop     dword ptr [rax+rax+00h]
0x18004f670  mov     ebx, eax
0x18004f672  test    eax, eax
0x18004f674  jz      short loc_18004F6AD
0x18004f676  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f67d  cmp     rcx, rdi
0x18004f680  jz      short loc_18004F6A3
0x18004f682  test    byte ptr [rcx+1Ch], 40h
0x18004f686  jz      short loc_18004F6A3
0x18004f688  mov     rcx, [rcx+10h]
0x18004f68c  mov     edx, 1Ah
0x18004f691  mov     r9d, eax
0x18004f694  mov     r8, rsi
0x18004f697  call    WPP_SF_d
0x18004f69c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f6a3  test    ebx, ebx
0x18004f6a5  js      loc_18004F770
0x18004f6ab  jmp     short loc_18004F6B4
0x18004f6ad  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f6b4  mov     eax, [rsp+300h+var_2C4]
0x18004f6b8  test    al, 1
0x18004f6ba  jz      loc_18004F770
0x18004f6c0  bt      eax, 9
0x18004f6c4  jnb     loc_18004F770
0x18004f6ca  bt      eax, 0Ah
0x18004f6ce  jnb     short loc_18004F71E
0x18004f6d0  cmp     rcx, rdi
0x18004f6d3  jz      short loc_18004F6EC
0x18004f6d5  test    byte ptr [rcx+1Ch], 8
0x18004f6d9  jz      short loc_18004F6EC
0x18004f6db  mov     rcx, [rcx+10h]
0x18004f6df  mov     edx, 1Bh
0x18004f6e4  mov     r8, rsi
0x18004f6e7  call    WPP_SF_
0x18004f6ec  mov     rcx, [rsp+300h+var_2E0]
0x18004f6f1  xor     edx, edx
0x18004f6f3  call    cs:__imp_FveDecrementClearKeyCounter
0x18004f6fa  nop     dword ptr [rax+rax+00h]
0x18004f6ff  mov     ebx, eax
0x18004f701  test    eax, eax
0x18004f703  jz      short loc_18004F770
0x18004f705  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f70c  cmp     rcx, rdi
0x18004f70f  jz      short loc_18004F770
0x18004f711  test    byte ptr [rcx+1Ch], 40h
0x18004f715  jz      short loc_18004F770
0x18004f717  mov     edx, 1Ch
0x18004f71c  jmp     short loc_18004F761
0x18004f71e  cmp     rcx, rdi
0x18004f721  jz      short loc_18004F73A
0x18004f723  test    byte ptr [rcx+1Ch], 8
0x18004f727  jz      short loc_18004F73A
0x18004f729  mov     rcx, [rcx+10h]
0x18004f72d  mov     edx, 1Dh
0x18004f732  mov     r8, rsi
0x18004f735  call    WPP_SF_
0x18004f73a  mov     ecx, 2
0x18004f73f  call    RefreshTpmBinding
0x18004f744  mov     ebx, eax
0x18004f746  test    eax, eax
0x18004f748  jz      short loc_18004F770
0x18004f74a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f751  cmp     rcx, rdi
0x18004f754  jz      short loc_18004F770
0x18004f756  test    byte ptr [rcx+1Ch], 40h
0x18004f75a  jz      short loc_18004F770
0x18004f75c  mov     edx, 1Eh
0x18004f761  mov     rcx, [rcx+10h]
0x18004f765  mov     r9d, eax
0x18004f768  mov     r8, rsi
0x18004f76b  call    WPP_SF_d
0x18004f770  mov     rcx, [rsp+300h+var_2E0]
0x18004f775  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18004f779  jz      short loc_18004F790
0x18004f77b  call    cs:__imp_FveCloseVolume
0x18004f782  nop     dword ptr [rax+rax+00h]
0x18004f787  mov     [rsp+300h+var_2E0], 0FFFFFFFFFFFFFFFFh
0x18004f790  call    ?FinishWorkImpl@BdeSvcWorkTracking@@AEAAXXZ; BdeSvcWorkTracking::FinishWorkImpl(void)
0x18004f795  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f79c  cmp     rcx, rdi
0x18004f79f  jz      short loc_18004F7B8
0x18004f7a1  test    byte ptr [rcx+1Ch], 20h
0x18004f7a5  jz      short loc_18004F7B8
0x18004f7a7  mov     rcx, [rcx+10h]
0x18004f7ab  mov     edx, 1Fh
0x18004f7b0  mov     r8, rsi
0x18004f7b3  call    WPP_SF_
0x18004f7b8  mov     eax, ebx
0x18004f7ba  mov     rcx, [rbp+200h+var_30]
0x18004f7c1  xor     rcx, rsp; StackCookie
0x18004f7c4  call    __security_check_cookie
0x18004f7c9  add     rsp, 2E8h
0x18004f7d0  pop     rdi
0x18004f7d1  pop     rsi
0x18004f7d2  pop     rbx
0x18004f7d3  pop     rbp
0x18004f7d4  retn
```
