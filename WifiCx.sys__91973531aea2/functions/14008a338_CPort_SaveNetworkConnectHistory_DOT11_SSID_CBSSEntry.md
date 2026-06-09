# CPort::SaveNetworkConnectHistory(_DOT11_SSID *,CBSSEntry *)

- ea: `0x14008a338`
- end: `0x14008a59e`
- name: `?SaveNetworkConnectHistory@CPort@@QEAAHPEAU_DOT11_SSID@@PEAVCBSSEntry@@@Z`
- size: `614`
- prototype: `__int64 __fastcall(CPort *__hidden this, struct _DOT11_SSID *, struct CBSSEntry *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14008aa68`

## callees

- `0x14000688c`
- `0x14000c778`
- `0x14000d054`
- `0x1400684cc`
- `0x14008a338`
- `0x1400bc3dc`
- `0x1400bc6c0`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x14008a437`
- `ntoskrnl!RtlCompareMemory` at `0x14008a437`

## pseudocode

```c
__int64 __fastcall CPort::SaveNetworkConnectHistory(
        CNetworkHistoryList **this,
        struct _DOT11_SSID *a2,
        struct CBSSEntry *a3)
{
  unsigned int v4; // ebx
  struct _DOT11_SSID *v5; // rbp
  int v7; // edx
  unsigned int v8; // eax
  int v9; // edx
  struct CNetworkHistory *v10; // r13
  int v11; // r8d
  unsigned int v12; // ebp
  unsigned int v13; // r15d
  struct CNetworkHistory *v15; // [rsp+80h] [rbp+8h] BYREF

  v4 = 0;
  v15 = 0;
  v5 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      372,
      (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids);
  }
  if ( CPropertyCache::GetPropertyBooleanOrDefault((CPropertyCache *)(this + 60), 0x20u, 0) )
  {
    v8 = CNetworkHistoryList::UpdateOrAddNetworkToTable(this[78], v5, &v15);
    v4 = v8;
    if ( v8 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v4;
      LOBYTE(v9) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        1,
        373,
        (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
        v8);
    }
    else
    {
      v10 = v15;
      if ( RtlCompareMemory((char *)v15 + 48, (char *)a3 + 32, 6u) == 6 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return v4;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          LOBYTE(v7) = 5;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v7,
            1,
            374,
            (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids);
        }
      }
      else
      {
        v12 = *((_DWORD *)a3 + 170);
        v13 = *((_DWORD *)a3 + 171);
        *((_DWORD *)v10 + 12) = *((_DWORD *)a3 + 8);
        *((_WORD *)v10 + 26) = *((_WORD *)a3 + 18);
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
          && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
        {
          LOBYTE(v7) = 5;
          WPP_RECORDER_SF_dddd(
            WPP_GLOBAL_Control->DeviceExtension,
            v7,
            v11,
            375,
            (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
            v13,
            v12,
            *((_DWORD *)a3 + 149),
            *((_DWORD *)a3 + 188));
        }
        CNetworkHistory::FindOrAddChannelEntry(v10, v13, v12);
      }
    }
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v7) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v7,
      1,
      376,
      (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
      v4);
  }
  return v4;
}

```

## disassembly

```asm
0x14008a338  mov     rax, rsp
0x14008a33b  mov     [rax+10h], rbx
0x14008a33f  mov     [rax+18h], rbp
0x14008a343  push    rsi
0x14008a344  push    rdi
0x14008a345  push    r13
0x14008a347  push    r14
0x14008a349  push    r15
0x14008a34b  sub     rsp, 50h
0x14008a34f  xor     r15d, r15d
0x14008a352  mov     rsi, r8
0x14008a355  mov     ebx, r15d
0x14008a358  mov     [rax+8], r15
0x14008a35c  mov     rbp, rdx
0x14008a35f  mov     rdi, rcx
0x14008a362  lea     rax, WPP_RECORDER_INITIALIZED
0x14008a369  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14008a370  lea     r14, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x14008a377  jz      short loc_14008A3A9
0x14008a379  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a380  cmp     byte ptr [rcx+29h], 5
0x14008a384  jnb     short loc_14008A38D
0x14008a386  cmp     [rcx+48h], r15w
0x14008a38b  jz      short loc_14008A3A9
0x14008a38d  mov     rcx, [rcx+40h]
0x14008a391  mov     r9d, 174h
0x14008a397  mov     r8d, 1
0x14008a39d  mov     [rsp+78h+var_58], r14
0x14008a3a2  mov     dl, 5
0x14008a3a4  call    WPP_RECORDER_SF_
0x14008a3a9  xor     r8d, r8d; unsigned __int8
0x14008a3ac  lea     rcx, [rdi+1E0h]; this
0x14008a3b3  lea     edx, [r8+20h]; unsigned int
0x14008a3b7  call    ?GetPropertyBooleanOrDefault@CPropertyCache@@QEAAEKE@Z; CPropertyCache::GetPropertyBooleanOrDefault(ulong,uchar)
0x14008a3bc  test    al, al
0x14008a3be  jz      loc_14008A535
0x14008a3c4  mov     rcx, [rdi+270h]; this
0x14008a3cb  lea     r8, [rsp+78h+arg_0]; struct CNetworkHistory **
0x14008a3d3  mov     rdx, rbp; struct _DOT11_SSID *
0x14008a3d6  call    ?UpdateOrAddNetworkToTable@CNetworkHistoryList@@QEAAHPEAU_DOT11_SSID@@PEAPEAVCNetworkHistory@@@Z; CNetworkHistoryList::UpdateOrAddNetworkToTable(_DOT11_SSID *,CNetworkHistory * *)
0x14008a3db  mov     ebx, eax
0x14008a3dd  test    eax, eax
0x14008a3df  jz      short loc_14008A421
0x14008a3e1  lea     rdi, WPP_RECORDER_INITIALIZED
0x14008a3e8  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14008a3ef  jz      loc_14008A582
0x14008a3f5  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a3fc  mov     r9d, 175h
0x14008a402  mov     [rsp+78h+var_50], eax
0x14008a406  mov     r8d, 1
0x14008a40c  mov     dl, 2
0x14008a40e  mov     [rsp+78h+var_58], r14
0x14008a413  mov     rcx, [rcx+40h]
0x14008a417  call    WPP_RECORDER_SF_d
0x14008a41c  jmp     loc_14008A545
0x14008a421  mov     r13, [rsp+78h+arg_0]
0x14008a429  lea     rdx, [rsi+20h]; Source2
0x14008a42d  mov     r8d, 6; Length
0x14008a433  lea     rcx, [r13+30h]; Source1
0x14008a437  call    cs:__imp_RtlCompareMemory
0x14008a43e  nop     dword ptr [rax+rax+00h]
0x14008a443  cmp     rax, 6
0x14008a447  jnz     short loc_14008A49D
0x14008a449  lea     rdi, WPP_RECORDER_INITIALIZED
0x14008a450  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14008a457  jz      loc_14008A582
0x14008a45d  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a464  cmp     byte ptr [rcx+29h], 5
0x14008a468  jnb     short loc_14008A475
0x14008a46a  cmp     [rcx+48h], r15w
0x14008a46f  jz      loc_14008A53E
0x14008a475  mov     rcx, [rcx+40h]
0x14008a479  lea     r14, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x14008a480  mov     r9d, 176h
0x14008a486  mov     [rsp+78h+var_58], r14
0x14008a48b  mov     r8d, 1
0x14008a491  mov     dl, 5
0x14008a493  call    WPP_RECORDER_SF_
0x14008a498  jmp     loc_14008A545
0x14008a49d  mov     eax, [rsi+20h]
0x14008a4a0  mov     ebp, [rsi+2A8h]
0x14008a4a6  mov     r15d, [rsi+2ACh]
0x14008a4ad  mov     [r13+30h], eax
0x14008a4b1  movzx   eax, word ptr [rsi+24h]
0x14008a4b5  mov     [r13+34h], ax
0x14008a4ba  lea     rdi, WPP_RECORDER_INITIALIZED
0x14008a4c1  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14008a4c8  jz      short loc_14008A51B
0x14008a4ca  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a4d1  cmp     byte ptr [rcx+29h], 5
0x14008a4d5  jnb     short loc_14008A4DF
0x14008a4d7  xor     eax, eax
0x14008a4d9  cmp     [rcx+48h], ax
0x14008a4dd  jz      short loc_14008A51B
0x14008a4df  mov     eax, [rsi+2F0h]
0x14008a4e5  lea     r14, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x14008a4ec  mov     rcx, [rcx+40h]
0x14008a4f0  mov     r9d, 177h
0x14008a4f6  mov     [rsp+78h+var_38], eax
0x14008a4fa  mov     dl, 5
0x14008a4fc  mov     eax, [rsi+254h]
0x14008a502  mov     [rsp+78h+var_40], eax
0x14008a506  mov     [rsp+78h+var_48], ebp
0x14008a50a  mov     [rsp+78h+var_50], r15d
0x14008a50f  mov     [rsp+78h+var_58], r14
0x14008a514  call    WPP_RECORDER_SF_dddd
0x14008a519  jmp     short loc_14008A522
0x14008a51b  lea     r14, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x14008a522  mov     r8d, ebp
0x14008a525  mov     edx, r15d
0x14008a528  mov     rcx, r13
0x14008a52b  call    ?FindOrAddChannelEntry@CNetworkHistory@@QEAAXW4_WDI_BAND_ID@@I@Z; CNetworkHistory::FindOrAddChannelEntry(_WDI_BAND_ID,uint)
0x14008a530  xor     r15d, r15d
0x14008a533  jmp     short loc_14008A545
0x14008a535  lea     rdi, WPP_RECORDER_INITIALIZED
0x14008a53c  jmp     short loc_14008A545
0x14008a53e  lea     r14, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x14008a545  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x14008a54c  jz      short loc_14008A582
0x14008a54e  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a555  cmp     byte ptr [rcx+29h], 5
0x14008a559  jnb     short loc_14008A562
0x14008a55b  cmp     [rcx+48h], r15w
0x14008a560  jz      short loc_14008A582
0x14008a562  mov     rcx, [rcx+40h]
0x14008a566  mov     r9d, 178h
0x14008a56c  mov     [rsp+78h+var_50], ebx
0x14008a570  mov     r8d, 1
0x14008a576  mov     dl, 5
0x14008a578  mov     [rsp+78h+var_58], r14
0x14008a57d  call    WPP_RECORDER_SF_d
0x14008a582  lea     r11, [rsp+78h+var_28]
0x14008a587  mov     eax, ebx
0x14008a589  mov     rbx, [r11+38h]
0x14008a58d  mov     rbp, [r11+40h]
0x14008a591  mov     rsp, r11
0x14008a594  pop     r15
0x14008a596  pop     r14
0x14008a598  pop     r13
0x14008a59a  pop     rdi
0x14008a59b  pop     rsi
0x14008a59c  retn
```
