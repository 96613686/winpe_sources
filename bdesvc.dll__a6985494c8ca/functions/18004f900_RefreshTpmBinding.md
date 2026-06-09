# RefreshTpmBinding

- ea: `0x18004f900`
- end: `0x18004fb59`
- name: `RefreshTpmBinding`
- size: `601`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18004f378`
- `0x18004f540`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x18000daf8`
- `0x180034070`
- `0x18003a548`
- `0x18004f900`

## import_xrefs

- `FVEAPI!FveCommitChanges` at `0x18004fa74`
- `FVEAPI!FveCommitChanges` at `0x18004fa74`
- `FVEAPI!FveOpenVolumeW` at `0x18004f9af`
- `FVEAPI!FveOpenVolumeW` at `0x18004f9af`
- `FVEAPI!FveCloseVolume` at `0x18004fb02`
- `FVEAPI!FveCloseVolume` at `0x18004fb02`
- `FVEAPI!FveKeyManagement` at `0x18004f9fe`
- `FVEAPI!FveKeyManagement` at `0x18004f9fe`

## pseudocode

```c
__int64 __fastcall RefreshTpmBinding(int a1)
{
  unsigned int OSVolume; // eax
  int v3; // ebx
  unsigned int v4; // eax
  unsigned int v5; // eax
  PVOID *v6; // rcx
  unsigned int v7; // eax
  __int64 v9; // [rsp+20h] [rbp-258h] BYREF
  int v10; // [rsp+28h] [rbp-250h] BYREF
  _BYTE v11[528]; // [rsp+30h] [rbp-248h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_5f44ebab715039561e5e3e58bbae32d1_Traceguids);
  v9 = -1;
  v10 = 0;
  OSVolume = NgscbGetOSVolume(v11);
  v3 = OSVolume;
  if ( OSVolume )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_5f44ebab715039561e5e3e58bbae32d1_Traceguids, OSVolume);
    if ( v3 < 0 )
      goto LABEL_34;
  }
  v4 = FveOpenVolumeW(v11, 1, &v9);
  v3 = v4;
  if ( v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_5f44ebab715039561e5e3e58bbae32d1_Traceguids, v4);
    if ( v3 < 0 )
      goto LABEL_34;
  }
  v5 = FveKeyManagement(v9, a1 | 4u, &v10);
  v3 = v5;
  if ( v5 != 1 )
  {
    if ( !v5 )
      goto LABEL_23;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_5f44ebab715039561e5e3e58bbae32d1_Traceguids, v5);
    if ( v3 >= 0 )
    {
LABEL_23:
      v7 = FveCommitChanges(v9);
      v3 = v7;
      if ( !v7 )
      {
        v6 = (PVOID *)WPP_GLOBAL_Control;
LABEL_30:
        if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 8) != 0 )
        {
          WPP_SF_(v6[2], 16, WPP_5f44ebab715039561e5e3e58bbae32d1_Traceguids);
          v6 = (PVOID *)WPP_GLOBAL_Control;
        }
        goto LABEL_36;
      }
      v6 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_5f44ebab715039561e5e3e58bbae32d1_Traceguids, v7);
        v6 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v3 >= 0 )
        goto LABEL_30;
    }
LABEL_34:
    BdeSvcLogFailedTpmBinding(v3);
    goto LABEL_35;
  }
  v3 = 0;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_5f44ebab715039561e5e3e58bbae32d1_Traceguids);
LABEL_35:
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_36:
  if ( v9 != -1 )
  {
    FveCloseVolume(v9);
    v6 = (PVOID *)WPP_GLOBAL_Control;
    v9 = -1;
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x20) != 0 )
    WPP_SF_(v6[2], 17, WPP_5f44ebab715039561e5e3e58bbae32d1_Traceguids);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18004f900  push    rbx
0x18004f902  push    rbp
0x18004f903  push    rsi
0x18004f904  push    rdi
0x18004f905  sub     rsp, 258h
0x18004f90c  mov     rax, cs:__security_cookie
0x18004f913  xor     rax, rsp
0x18004f916  mov     [rsp+278h+var_38], rax
0x18004f91e  mov     edi, ecx
0x18004f920  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f927  lea     rsi, WPP_GLOBAL_Control
0x18004f92e  lea     rbp, WPP_5f44ebab715039561e5e3e58bbae32d1_Traceguids
0x18004f935  cmp     rcx, rsi
0x18004f938  jz      short loc_18004F951
0x18004f93a  test    byte ptr [rcx+1Ch], 20h
0x18004f93e  jz      short loc_18004F951
0x18004f940  mov     rcx, [rcx+10h]
0x18004f944  mov     edx, 0Ah
0x18004f949  mov     r8, rbp
0x18004f94c  call    WPP_SF_
0x18004f951  lea     rcx, [rsp+278h+var_248]
0x18004f956  mov     [rsp+278h+var_258], 0FFFFFFFFFFFFFFFFh
0x18004f95f  mov     [rsp+278h+var_250], 0
0x18004f967  call    NgscbGetOSVolume
0x18004f96c  mov     ebx, eax
0x18004f96e  test    eax, eax
0x18004f970  jz      short loc_18004F9A0
0x18004f972  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f979  cmp     rcx, rsi
0x18004f97c  jz      short loc_18004F998
0x18004f97e  test    byte ptr [rcx+1Ch], 40h
0x18004f982  jz      short loc_18004F998
0x18004f984  mov     rcx, [rcx+10h]
0x18004f988  mov     edx, 0Bh
0x18004f98d  mov     r9d, eax
0x18004f990  mov     r8, rbp
0x18004f993  call    WPP_SF_d
0x18004f998  test    ebx, ebx
0x18004f99a  js      loc_18004FAE7
0x18004f9a0  lea     r8, [rsp+278h+var_258]
0x18004f9a5  mov     edx, 1
0x18004f9aa  lea     rcx, [rsp+278h+var_248]
0x18004f9af  call    cs:__imp_FveOpenVolumeW
0x18004f9b6  nop     dword ptr [rax+rax+00h]
0x18004f9bb  mov     ebx, eax
0x18004f9bd  test    eax, eax
0x18004f9bf  jz      short loc_18004F9EF
0x18004f9c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18004f9c8  cmp     rcx, rsi
0x18004f9cb  jz      short loc_18004F9E7
0x18004f9cd  test    byte ptr [rcx+1Ch], 40h
0x18004f9d1  jz      short loc_18004F9E7
0x18004f9d3  mov     rcx, [rcx+10h]
0x18004f9d7  mov     edx, 0Ch
0x18004f9dc  mov     r9d, eax
0x18004f9df  mov     r8, rbp
0x18004f9e2  call    WPP_SF_d
0x18004f9e7  test    ebx, ebx
0x18004f9e9  js      loc_18004FAE7
0x18004f9ef  mov     rcx, [rsp+278h+var_258]
0x18004f9f4  lea     r8, [rsp+278h+var_250]
0x18004f9f9  or      edi, 4
0x18004f9fc  mov     edx, edi
0x18004f9fe  call    cs:__imp_FveKeyManagement
0x18004fa05  nop     dword ptr [rax+rax+00h]
0x18004fa0a  mov     ebx, eax
0x18004fa0c  cmp     eax, 1
0x18004fa0f  jnz     short loc_18004FA41
0x18004fa11  xor     ebx, ebx
0x18004fa13  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fa1a  cmp     rcx, rsi
0x18004fa1d  jz      loc_18004FAF5
0x18004fa23  test    byte ptr [rcx+1Ch], 8
0x18004fa27  jz      loc_18004FAF5
0x18004fa2d  mov     rcx, [rcx+10h]
0x18004fa31  lea     edx, [rax+0Ch]
0x18004fa34  mov     r8, rbp
0x18004fa37  call    WPP_SF_
0x18004fa3c  jmp     loc_18004FAEE
0x18004fa41  test    ebx, ebx
0x18004fa43  jz      short loc_18004FA6F
0x18004fa45  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fa4c  cmp     rcx, rsi
0x18004fa4f  jz      short loc_18004FA6B
0x18004fa51  test    byte ptr [rcx+1Ch], 40h
0x18004fa55  jz      short loc_18004FA6B
0x18004fa57  mov     rcx, [rcx+10h]
0x18004fa5b  mov     edx, 0Eh
0x18004fa60  mov     r9d, ebx
0x18004fa63  mov     r8, rbp
0x18004fa66  call    WPP_SF_d
0x18004fa6b  test    ebx, ebx
0x18004fa6d  js      short loc_18004FAE7
0x18004fa6f  mov     rcx, [rsp+278h+var_258]
0x18004fa74  call    cs:__imp_FveCommitChanges
0x18004fa7b  nop     dword ptr [rax+rax+00h]
0x18004fa80  mov     ebx, eax
0x18004fa82  test    eax, eax
0x18004fa84  jz      short loc_18004FAB9
0x18004fa86  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fa8d  cmp     rcx, rsi
0x18004fa90  jz      short loc_18004FAB3
0x18004fa92  test    byte ptr [rcx+1Ch], 40h
0x18004fa96  jz      short loc_18004FAB3
0x18004fa98  mov     rcx, [rcx+10h]
0x18004fa9c  mov     edx, 0Fh
0x18004faa1  mov     r9d, eax
0x18004faa4  mov     r8, rbp
0x18004faa7  call    WPP_SF_d
0x18004faac  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fab3  test    ebx, ebx
0x18004fab5  js      short loc_18004FAE7
0x18004fab7  jmp     short loc_18004FAC0
0x18004fab9  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fac0  cmp     rcx, rsi
0x18004fac3  jz      short loc_18004FAE3
0x18004fac5  test    byte ptr [rcx+1Ch], 8
0x18004fac9  jz      short loc_18004FAE3
0x18004facb  mov     rcx, [rcx+10h]
0x18004facf  mov     edx, 10h
0x18004fad4  mov     r8, rbp
0x18004fad7  call    WPP_SF_
0x18004fadc  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fae3  test    ebx, ebx
0x18004fae5  jns     short loc_18004FAF5
0x18004fae7  mov     ecx, ebx; int
0x18004fae9  call    ?BdeSvcLogFailedTpmBinding@@YAXJ@Z; BdeSvcLogFailedTpmBinding(long)
0x18004faee  mov     rcx, cs:WPP_GLOBAL_Control
0x18004faf5  cmp     [rsp+278h+var_258], 0FFFFFFFFFFFFFFFFh
0x18004fafb  jz      short loc_18004FB1E
0x18004fafd  mov     rcx, [rsp+278h+var_258]
0x18004fb02  call    cs:__imp_FveCloseVolume
0x18004fb09  nop     dword ptr [rax+rax+00h]
0x18004fb0e  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fb15  mov     [rsp+278h+var_258], 0FFFFFFFFFFFFFFFFh
0x18004fb1e  cmp     rcx, rsi
0x18004fb21  jz      short loc_18004FB3A
0x18004fb23  test    byte ptr [rcx+1Ch], 20h
0x18004fb27  jz      short loc_18004FB3A
0x18004fb29  mov     rcx, [rcx+10h]
0x18004fb2d  mov     edx, 11h
0x18004fb32  mov     r8, rbp
0x18004fb35  call    WPP_SF_
0x18004fb3a  mov     eax, ebx
0x18004fb3c  mov     rcx, [rsp+278h+var_38]
0x18004fb44  xor     rcx, rsp; StackCookie
0x18004fb47  call    __security_check_cookie
0x18004fb4c  add     rsp, 258h
0x18004fb53  pop     rdi
0x18004fb54  pop     rsi
0x18004fb55  pop     rbp
0x18004fb56  pop     rbx
0x18004fb57  retn
```
