# CPort::SaveNetworkCandidatesHistory(_DOT11_SSID *,_WFC_CONNECT_SCAN_TYPE,ulong,CBSSEntry * *)

- ea: `0x14008a018`
- end: `0x14008a330`
- name: `?SaveNetworkCandidatesHistory@CPort@@QEAAHPEAU_DOT11_SSID@@W4_WFC_CONNECT_SCAN_TYPE@@KPEAPEAVCBSSEntry@@@Z`
- size: `792`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x1400a2644`

## callees

- `0x14000c778`
- `0x14000d054`
- `0x140024a20`
- `0x140050574`
- `0x1400683ac`
- `0x14008a018`
- `0x14008d334`
- `0x1400bc6c0`

## pseudocode

```c
__int64 __fastcall CPort::SaveNetworkCandidatesHistory(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, __int64 a5)
{
  unsigned int v6; // ebp
  int v7; // r14d
  struct _DOT11_SSID *v8; // rsi
  int v10; // eax
  int v11; // r8d
  int v12; // r9d
  struct CNetworkHistory *v13; // rdi
  __int64 v14; // r12
  unsigned int i; // ecx
  __int64 j; // rbx
  __int64 v17; // rsi
  __int64 v18; // rbx
  int v19; // r10d
  unsigned int v20; // ecx
  int v21; // r8d
  int v23; // [rsp+20h] [rbp-78h]
  __int64 v24; // [rsp+28h] [rbp-70h]
  struct CNetworkHistory *v25; // [rsp+40h] [rbp-58h] BYREF

  v6 = 0;
  v25 = 0;
  v7 = a3;
  v8 = (struct _DOT11_SSID *)a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      366,
      (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids);
  }
  if ( a4 > 1 )
  {
    LOBYTE(a3) = 1;
    CPropertyCache::SetPropertyBoolean((CPropertyCache *)(a1 + 480), 32, a3);
    v10 = CNetworkHistoryList::UpdateOrAddNetworkToTable(*(CNetworkHistoryList **)(a1 + 624), v8, &v25);
    v6 = v10;
    if ( v10 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v6;
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        1,
        367,
        (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
        v10);
    }
    else
    {
      v13 = v25;
      v14 = a5;
      if ( !*((_BYTE *)v25 + 208) )
      {
        for ( i = 0; i < a4; ++i )
        {
          a2 = *(_QWORD *)(a5 + 8LL * i);
          if ( *(_DWORD *)(a2 + 684) != 1 )
          {
            *((_BYTE *)v25 + 208) = 1;
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
              && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
            {
              WPP_RECORDER_SF__SSID_dd(
                WPP_GLOBAL_Control->DeviceExtension,
                a2,
                v11,
                v12,
                v23,
                (__int64)v8,
                *(_DWORD *)(a2 + 684),
                *(_DWORD *)(a2 + 680));
            }
            for ( j = 0; j != 8; ++j )
            {
              LODWORD(a2) = *((_DWORD *)v13 + 4 * j + 20);
              if ( (_DWORD)a2 == 1 )
              {
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
                  && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
                {
                  LOBYTE(a2) = 5;
                  WPP_RECORDER_SF_Ld(
                    WPP_GLOBAL_Control->DeviceExtension,
                    a2,
                    v11,
                    369,
                    (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
                    1,
                    *((_DWORD *)v13 + 4 * j + 21));
                }
                *((_DWORD *)v13 + 4 * j + 22) = 0;
              }
            }
            v14 = a5;
            break;
          }
        }
      }
      if ( v7 > 0 )
      {
        v17 = 0;
        v18 = 0;
        do
        {
          *((_BYTE *)v13 + v18 + 92) = 0;
          if ( *(_DWORD *)((char *)v13 + v18 + 88) )
          {
            v19 = *(_DWORD *)((char *)v13 + v18 + 84);
            v20 = 0;
            v21 = *((_DWORD *)v13 + 4 * v17 + 20);
            while ( v20 < a4 )
            {
              a2 = *(_QWORD *)(v14 + 8LL * v20);
              if ( *(_DWORD *)(a2 + 680) == v19 && *(_DWORD *)(a2 + 684) == v21 )
              {
                *((_BYTE *)v13 + v18 + 92) = 1;
                if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
                  && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
                {
                  LOBYTE(a2) = 5;
                  WPP_RECORDER_SF_dDd(
                    WPP_GLOBAL_Control->DeviceExtension,
                    a2,
                    v21,
                    370,
                    (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
                    v20,
                    v21,
                    v19);
                }
                break;
              }
              ++v20;
            }
          }
          ++v17;
          v18 += 16;
        }
        while ( v17 != 8 );
        v6 = 0;
      }
    }
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v24) = v6;
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      1,
      371,
      (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
      v24);
  }
  return v6;
}

```

## disassembly

```asm
0x14008a018  push    rbx
0x14008a01a  push    rbp
0x14008a01b  push    rsi
0x14008a01c  push    rdi
0x14008a01d  push    r12
0x14008a01f  push    r13
0x14008a021  push    r14
0x14008a023  push    r15
0x14008a025  sub     rsp, 58h
0x14008a029  xor     r13d, r13d
0x14008a02c  mov     r15d, r9d
0x14008a02f  mov     ebp, r13d
0x14008a032  mov     [rsp+98h+var_58], r13
0x14008a037  mov     r14d, r8d
0x14008a03a  mov     rsi, rdx
0x14008a03d  mov     rbx, rcx
0x14008a040  lea     rax, WPP_RECORDER_INITIALIZED
0x14008a047  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14008a04e  lea     rdi, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x14008a055  jz      short loc_14008A087
0x14008a057  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a05e  cmp     byte ptr [rcx+29h], 5
0x14008a062  jnb     short loc_14008A06B
0x14008a064  cmp     [rcx+48h], r13w
0x14008a069  jz      short loc_14008A087
0x14008a06b  mov     rcx, [rcx+40h]
0x14008a06f  mov     r9d, 16Eh
0x14008a075  mov     r8d, 1
0x14008a07b  mov     [rsp+98h+var_78], rdi
0x14008a080  mov     dl, 5
0x14008a082  call    WPP_RECORDER_SF_
0x14008a087  cmp     r15d, 1
0x14008a08b  jbe     loc_14008A2D8
0x14008a091  lea     rcx, [rbx+1E0h]; this
0x14008a098  mov     r8b, 1; unsigned __int8
0x14008a09b  mov     edx, 20h ; ' '; unsigned int
0x14008a0a0  call    ?SetPropertyBoolean@CPropertyCache@@QEAAHKE@Z; CPropertyCache::SetPropertyBoolean(ulong,uchar)
0x14008a0a5  mov     rcx, [rbx+270h]; this
0x14008a0ac  lea     r8, [rsp+98h+var_58]; struct CNetworkHistory **
0x14008a0b1  mov     rdx, rsi; struct _DOT11_SSID *
0x14008a0b4  call    ?UpdateOrAddNetworkToTable@CNetworkHistoryList@@QEAAHPEAU_DOT11_SSID@@PEAPEAVCNetworkHistory@@@Z; CNetworkHistoryList::UpdateOrAddNetworkToTable(_DOT11_SSID *,CNetworkHistory * *)
0x14008a0b9  mov     [rsp+98h+arg_18], eax
0x14008a0c0  mov     ebp, eax
0x14008a0c2  test    eax, eax
0x14008a0c4  jz      short loc_14008A106
0x14008a0c6  lea     r14, WPP_RECORDER_INITIALIZED
0x14008a0cd  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14008a0d4  jz      loc_14008A31C
0x14008a0da  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a0e1  mov     r9d, 16Fh
0x14008a0e7  mov     dword ptr [rsp+98h+var_70], eax
0x14008a0eb  mov     r8d, 1
0x14008a0f1  mov     dl, 2
0x14008a0f3  mov     [rsp+98h+var_78], rdi
0x14008a0f8  mov     rcx, [rcx+40h]
0x14008a0fc  call    WPP_RECORDER_SF_d
0x14008a101  jmp     loc_14008A2DF
0x14008a106  mov     rdi, [rsp+98h+var_58]
0x14008a10b  mov     r12, [rsp+98h+arg_20]
0x14008a113  cmp     [rdi+0D0h], r13b
0x14008a11a  jnz     loc_14008A214
0x14008a120  mov     ecx, r13d
0x14008a123  cmp     ecx, r15d
0x14008a126  jnb     loc_14008A214
0x14008a12c  mov     eax, ecx
0x14008a12e  mov     rdx, [r12+rax*8]
0x14008a132  cmp     dword ptr [rdx+2ACh], 1
0x14008a139  jnz     short loc_14008A13F
0x14008a13b  inc     ecx
0x14008a13d  jmp     short loc_14008A123
0x14008a13f  mov     byte ptr [rdi+0D0h], 1
0x14008a146  lea     rcx, WPP_RECORDER_INITIALIZED
0x14008a14d  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14008a154  jz      short loc_14008A193
0x14008a156  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a15d  cmp     byte ptr [rcx+29h], 5
0x14008a161  jnb     short loc_14008A16A
0x14008a163  cmp     [rcx+48h], r13w
0x14008a168  jz      short loc_14008A18C
0x14008a16a  mov     eax, [rdx+2A8h]
0x14008a170  mov     rcx, [rcx+40h]
0x14008a174  mov     [rsp+98h+var_60], eax
0x14008a178  mov     eax, [rdx+2ACh]
0x14008a17e  mov     [rsp+98h+var_68], eax
0x14008a182  mov     [rsp+98h+var_70], rsi
0x14008a187  call    WPP_RECORDER_SF__SSID_dd
0x14008a18c  lea     rcx, WPP_RECORDER_INITIALIZED
0x14008a193  mov     rbx, r13
0x14008a196  lea     r12, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x14008a19d  lea     rax, [rbx+5]
0x14008a1a1  add     rax, rax
0x14008a1a4  mov     edx, [rdi+rax*8]
0x14008a1a7  cmp     edx, 1
0x14008a1aa  jnz     short loc_14008A203
0x14008a1ac  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14008a1b3  jz      short loc_14008A1F8
0x14008a1b5  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a1bc  cmp     byte ptr [rcx+29h], 5
0x14008a1c0  jnb     short loc_14008A1C9
0x14008a1c2  cmp     [rcx+48h], r13w
0x14008a1c7  jz      short loc_14008A1F1
0x14008a1c9  mov     rcx, [rcx+40h]
0x14008a1cd  mov     rax, rbx
0x14008a1d0  add     rax, rax
0x14008a1d3  mov     r9d, 171h
0x14008a1d9  mov     eax, [rdi+rax*8+54h]
0x14008a1dd  mov     [rsp+98h+var_68], eax
0x14008a1e1  mov     dword ptr [rsp+98h+var_70], edx
0x14008a1e5  mov     dl, 5
0x14008a1e7  mov     [rsp+98h+var_78], r12
0x14008a1ec  call    WPP_RECORDER_SF_Ld
0x14008a1f1  lea     rcx, WPP_RECORDER_INITIALIZED
0x14008a1f8  mov     rax, rbx
0x14008a1fb  add     rax, rax
0x14008a1fe  mov     [rdi+rax*8+58h], r13d
0x14008a203  inc     rbx
0x14008a206  cmp     rbx, 8
0x14008a20a  jnz     short loc_14008A19D
0x14008a20c  mov     r12, [rsp+98h+arg_20]
0x14008a214  test    r14d, r14d
0x14008a217  lea     r14, WPP_RECORDER_INITIALIZED
0x14008a21e  jle     loc_14008A2CF
0x14008a224  mov     rsi, r13
0x14008a227  lea     rbp, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x14008a22e  mov     rbx, r13
0x14008a231  mov     [rbx+rdi+5Ch], r13b
0x14008a236  cmp     [rbx+rdi+58h], r13d
0x14008a23b  jbe     short loc_14008A2B7
0x14008a23d  mov     r10d, [rbx+rdi+54h]
0x14008a242  lea     rax, [rsi+5]
0x14008a246  add     rax, rax
0x14008a249  mov     ecx, r13d
0x14008a24c  mov     r8d, [rdi+rax*8]
0x14008a250  cmp     ecx, r15d
0x14008a253  jnb     short loc_14008A2B7
0x14008a255  mov     eax, ecx
0x14008a257  mov     rdx, [r12+rax*8]
0x14008a25b  cmp     [rdx+2A8h], r10d
0x14008a262  jnz     short loc_14008A26D
0x14008a264  cmp     [rdx+2ACh], r8d
0x14008a26b  jz      short loc_14008A271
0x14008a26d  inc     ecx
0x14008a26f  jmp     short loc_14008A250
0x14008a271  mov     byte ptr [rbx+rdi+5Ch], 1
0x14008a276  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14008a27d  jz      short loc_14008A2B7
0x14008a27f  mov     rax, cs:WPP_GLOBAL_Control
0x14008a286  cmp     byte ptr [rax+29h], 5
0x14008a28a  jnb     short loc_14008A293
0x14008a28c  cmp     [rax+48h], r13w
0x14008a291  jz      short loc_14008A2B7
0x14008a293  mov     [rsp+98h+var_60], r10d
0x14008a298  mov     r9d, 172h
0x14008a29e  mov     [rsp+98h+var_68], r8d
0x14008a2a3  mov     dl, 5
0x14008a2a5  mov     dword ptr [rsp+98h+var_70], ecx
0x14008a2a9  mov     rcx, [rax+40h]
0x14008a2ad  mov     [rsp+98h+var_78], rbp
0x14008a2b2  call    WPP_RECORDER_SF_dDd
0x14008a2b7  inc     rsi
0x14008a2ba  add     rbx, 10h
0x14008a2be  cmp     rsi, 8
0x14008a2c2  jnz     loc_14008A231
0x14008a2c8  mov     ebp, [rsp+98h+arg_18]
0x14008a2cf  lea     rdi, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x14008a2d6  jmp     short loc_14008A2DF
0x14008a2d8  lea     r14, WPP_RECORDER_INITIALIZED
0x14008a2df  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14008a2e6  jz      short loc_14008A31C
0x14008a2e8  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a2ef  cmp     byte ptr [rcx+29h], 5
0x14008a2f3  jnb     short loc_14008A2FC
0x14008a2f5  cmp     [rcx+48h], r13w
0x14008a2fa  jz      short loc_14008A31C
0x14008a2fc  mov     rcx, [rcx+40h]
0x14008a300  mov     r9d, 173h
0x14008a306  mov     dword ptr [rsp+98h+var_70], ebp
0x14008a30a  mov     r8d, 1
0x14008a310  mov     dl, 5
0x14008a312  mov     [rsp+98h+var_78], rdi
0x14008a317  call    WPP_RECORDER_SF_d
0x14008a31c  mov     eax, ebp
0x14008a31e  add     rsp, 58h
0x14008a322  pop     r15
0x14008a324  pop     r14
0x14008a326  pop     r13
0x14008a328  pop     r12
0x14008a32a  pop     rdi
0x14008a32b  pop     rsi
0x14008a32c  pop     rbp
0x14008a32d  pop     rbx
0x14008a32e  retn
```
