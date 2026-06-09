# MbbNdisMultiCarrierDsCidListStatusHandler(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)

- ea: `0x140030830`
- end: `0x140030bb3`
- name: `?MbbNdisMultiCarrierDsCidListStatusHandler@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z`
- size: `899`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, _DWORD *, unsigned int)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400051ac`
- `0x140005644`
- `0x1400187d8`
- `0x14002e9c4`
- `0x140030830`
- `0x14003b0e8`
- `0x14003f7e4`
- `0x140047e50`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x140030a64`
- `ntoskrnl!RtlCompareMemory` at `0x140030ac0`
- `ntoskrnl!RtlCompareMemory` at `0x140030a64`
- `ntoskrnl!RtlCompareMemory` at `0x140030ac0`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030a99`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030b2b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030a99`
- `ntoskrnl!KeReleaseSpinLock` at `0x140030b2b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030a7e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030ad8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030a7e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140030ad8`

## pseudocode

```c
__int64 __fastcall MbbNdisMultiCarrierDsCidListStatusHandler(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        _DWORD *a4,
        unsigned int a5)
{
  unsigned int v6; // esi
  int v8; // eax
  int v9; // r9d
  __int64 v10; // rdi
  int v11; // ecx
  unsigned int v12; // ecx
  unsigned __int64 v13; // rdx
  unsigned int v14; // r9d
  int v15; // r9d
  unsigned int v16; // eax
  KIRQL v17; // al
  KIRQL v18; // al
  __int64 v19; // r8
  char v21; // [rsp+30h] [rbp-68h]
  __int128 Source1; // [rsp+50h] [rbp-48h] BYREF

  v6 = a2;
  Source1 = 0;
  if ( a2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v8 = *(_DWORD *)(a1 + 16);
      v9 = 215;
      v21 = a2;
LABEL_4:
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_DD(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        1,
        v9,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        v8,
        v21);
    }
  }
  else
  {
    v10 = **(_QWORD **)(a1 + 48);
    v11 = MbbUtilMbbToWwanStatus(a3);
    if ( v11 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_40;
      v8 = *(_DWORD *)(a1 + 16);
      v9 = 216;
      v21 = v11;
      goto LABEL_4;
    }
    if ( a4 && a5 >= 4 )
    {
      v12 = -1;
      v13 = 4LL * (unsigned int)*a4;
      v14 = 4 * *a4;
      if ( v13 > 0xFFFFFFFF )
        v14 = -1;
      v6 = v13 > 0xFFFFFFFF ? 0xC0000095 : 0;
      if ( (v13 > 0xFFFFFFFF ? 0xC0000000 : 0) == 0xC0000000 )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_40;
        v15 = 218;
      }
      else
      {
        v16 = v14 + 4;
        if ( v14 + 4 >= v14 )
          v12 = v14 + 4;
        v6 = v16 < v14 ? 0xC0000095 : 0;
        if ( (v16 < v14 ? 0xC0000000 : 0) != 0xC0000000 )
        {
          if ( a5 >= v12 )
          {
            LODWORD(Source1) = _byteswap_ulong(*(_DWORD *)(a1 + 764));
            WORD2(Source1) = __ROR2__(*(_WORD *)(a1 + 768), 8);
            WORD3(Source1) = __ROR2__(*(_WORD *)(a1 + 770), 8);
            *((_QWORD *)&Source1 + 1) = *(_QWORD *)(a1 + 772);
            if ( RtlCompareMemory(&Source1, &MBB_UUID_USSD, 0x10u) == 16 )
            {
              if ( *a4 )
              {
                v17 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v10);
                *(_DWORD *)(v10 + 1088) |= 2u;
                *(_BYTE *)(v10 + 8) = v17;
                KeReleaseSpinLock((PKSPIN_LOCK)v10, v17);
              }
              *(_DWORD *)(a1 + 780) |= 1u;
            }
            else if ( RtlCompareMemory(&Source1, &MBB_UUID_AUTH, 0x10u) == 16 )
            {
              v18 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v10);
              v19 = 0;
              for ( *(_BYTE *)(v10 + 8) = v18; (unsigned int)v19 < *a4; v19 = (unsigned int)(v19 + 1) )
              {
                switch ( a4[v19 + 1] )
                {
                  case 1:
                    *(_DWORD *)(v10 + 1088) |= 8u;
                    break;
                  case 2:
                    *(_DWORD *)(v10 + 1088) |= 0x10u;
                    break;
                  case 3:
                    *(_DWORD *)(v10 + 1088) |= 4u;
                    break;
                }
              }
              KeReleaseSpinLock((PKSPIN_LOCK)v10, v18);
              *(_DWORD *)(a1 + 780) |= 2u;
            }
          }
          else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            WPP_RECORDER_SF_Dddd(
              WPP_GLOBAL_Control->DeviceExtension,
              v13,
              1,
              220,
              (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
              *(_DWORD *)(a1 + 16),
              *a4,
              a5,
              v12);
          }
          goto LABEL_40;
        }
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          goto LABEL_40;
        v15 = 219;
      }
      WPP_RECORDER_SF_DDDi(WPP_GLOBAL_Control->DeviceExtension, v13, a5, v15);
      goto LABEL_40;
    }
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(a2) = 2;
      WPP_RECORDER_SF_Ddd(
        WPP_GLOBAL_Control->DeviceExtension,
        a2,
        1,
        217,
        (__int64)WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids,
        *(_DWORD *)(a1 + 16),
        a5,
        4);
    }
  }
LABEL_40:
  MbbNdisIndicateDeviceCaps((struct _MBB_REQUEST_CONTEXT *)a1, v6);
  return v6;
}

```

## disassembly

```asm
0x140030830  push    rbx
0x140030832  push    rbp
0x140030833  push    rsi
0x140030834  push    rdi
0x140030835  push    r14
0x140030837  sub     rsp, 70h
0x14003083b  mov     rax, cs:__security_cookie
0x140030842  xor     rax, rsp
0x140030845  mov     [rsp+98h+var_38], rax
0x14003084a  xorps   xmm0, xmm0
0x14003084d  mov     rbp, r9
0x140030850  mov     esi, edx
0x140030852  mov     rbx, rcx
0x140030855  movups  [rsp+98h+Source1], xmm0
0x14003085a  test    edx, edx
0x14003085c  jz      short loc_1400308AC
0x14003085e  lea     rax, WPP_RECORDER_INITIALIZED
0x140030865  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003086c  jz      loc_140030B8E
0x140030872  mov     eax, [rcx+10h]
0x140030875  mov     r9d, 0D7h
0x14003087b  mov     dword ptr [rsp+98h+var_68], edx
0x14003087f  mov     rcx, cs:WPP_GLOBAL_Control
0x140030886  mov     r8d, 1
0x14003088c  mov     [rsp+98h+var_70], eax
0x140030890  mov     dl, 2
0x140030892  lea     rax, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140030899  mov     [rsp+98h+var_78], rax
0x14003089e  mov     rcx, [rcx+40h]
0x1400308a2  call    WPP_RECORDER_SF_DD
0x1400308a7  jmp     loc_140030B8E
0x1400308ac  mov     rax, [rcx+30h]
0x1400308b0  mov     ecx, r8d
0x1400308b3  mov     rdi, [rax]
0x1400308b6  call    ?MbbUtilMbbToWwanStatus@@YAKW4_MBB_STATUS@@@Z; MbbUtilMbbToWwanStatus(_MBB_STATUS)
0x1400308bb  mov     ecx, eax
0x1400308bd  test    eax, eax
0x1400308bf  jz      short loc_1400308E4
0x1400308c1  lea     rax, WPP_RECORDER_INITIALIZED
0x1400308c8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400308cf  jz      loc_140030B8E
0x1400308d5  mov     eax, [rbx+10h]
0x1400308d8  mov     r9d, 0D8h
0x1400308de  mov     dword ptr [rsp+98h+var_68], ecx
0x1400308e2  jmp     short loc_14003087F
0x1400308e4  mov     r8d, [rsp+98h+arg_20]
0x1400308ec  test    rbp, rbp
0x1400308ef  jz      loc_140030B40
0x1400308f5  cmp     r8d, 4
0x1400308f9  jb      loc_140030B40
0x1400308ff  mov     r10d, [rbp+0]
0x140030903  mov     ecx, 0FFFFFFFFh
0x140030908  mov     edx, r10d
0x14003090b  shl     rdx, 2
0x14003090f  mov     r9d, edx
0x140030912  cmp     rdx, rcx
0x140030915  jbe     short loc_14003091A
0x140030917  mov     r9d, ecx
0x14003091a  cmp     rcx, rdx
0x14003091d  mov     r11d, 0C0000000h
0x140030923  mov     r14d, 0C0000095h
0x140030929  sbb     esi, esi
0x14003092b  and     esi, r14d
0x14003092e  mov     eax, esi
0x140030930  and     eax, r11d
0x140030933  cmp     eax, r11d
0x140030936  jnz     short loc_140030978
0x140030938  lea     rax, WPP_RECORDER_INITIALIZED
0x14003093f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140030946  jz      loc_140030B8E
0x14003094c  mov     [rsp+98h+var_58], rdx
0x140030951  mov     r9d, 0DAh
0x140030957  mov     dword ptr [rsp+98h+var_68], r10d
0x14003095c  mov     rcx, cs:WPP_GLOBAL_Control
0x140030963  mov     eax, [rbx+10h]
0x140030966  mov     [rsp+98h+var_70], eax
0x14003096a  mov     rcx, [rcx+40h]
0x14003096e  call    WPP_RECORDER_SF_DDDi
0x140030973  jmp     loc_140030B8E
0x140030978  lea     eax, [r9+4]
0x14003097c  cmp     eax, r9d
0x14003097f  cmovnb  ecx, eax
0x140030982  sbb     esi, esi
0x140030984  and     esi, r14d
0x140030987  mov     eax, esi
0x140030989  and     eax, r11d
0x14003098c  cmp     eax, r11d
0x14003098f  jnz     short loc_1400309BC
0x140030991  lea     rax, WPP_RECORDER_INITIALIZED
0x140030998  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14003099f  jz      loc_140030B8E
0x1400309a5  mov     eax, ecx
0x1400309a7  mov     r9d, 0DBh
0x1400309ad  add     rax, 4
0x1400309b1  mov     [rsp+98h+var_58], rax
0x1400309b6  mov     dword ptr [rsp+98h+var_68], ecx
0x1400309ba  jmp     short loc_14003095C
0x1400309bc  cmp     r8d, ecx
0x1400309bf  jnb     short loc_140030A17
0x1400309c1  lea     rax, WPP_RECORDER_INITIALIZED
0x1400309c8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400309cf  jz      loc_140030B8E
0x1400309d5  mov     eax, [rbx+10h]
0x1400309d8  mov     r9d, 0DCh
0x1400309de  mov     dword ptr [rsp+98h+var_58], ecx
0x1400309e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400309e9  mov     [rsp+98h+var_60], r8d
0x1400309ee  mov     r8d, 1
0x1400309f4  mov     dword ptr [rsp+98h+var_68], r10d
0x1400309f9  mov     [rsp+98h+var_70], eax
0x1400309fd  lea     rax, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140030a04  mov     rcx, [rcx+40h]
0x140030a08  mov     [rsp+98h+var_78], rax
0x140030a0d  call    WPP_RECORDER_SF_Dddd
0x140030a12  jmp     loc_140030B8E
0x140030a17  mov     eax, [rbx+2FCh]
0x140030a1d  lea     rdx, MBB_UUID_USSD; Source2
0x140030a24  bswap   eax
0x140030a26  mov     dword ptr [rsp+98h+Source1], eax
0x140030a2a  lea     rcx, [rsp+98h+Source1]; Source1
0x140030a2f  movzx   eax, word ptr [rbx+300h]
0x140030a36  mov     r14d, 10h
0x140030a3c  ror     ax, 8
0x140030a40  mov     r8d, r14d; Length
0x140030a43  mov     word ptr [rsp+98h+Source1+4], ax
0x140030a48  movzx   eax, word ptr [rbx+302h]
0x140030a4f  ror     ax, 8
0x140030a53  mov     word ptr [rsp+98h+Source1+6], ax
0x140030a58  mov     rax, [rbx+304h]
0x140030a5f  mov     qword ptr [rsp+98h+Source1+8], rax
0x140030a64  call    cs:__imp_RtlCompareMemory
0x140030a6b  nop     dword ptr [rax+rax+00h]
0x140030a70  cmp     rax, r14
0x140030a73  jnz     short loc_140030AB1
0x140030a75  cmp     dword ptr [rbp+0], 0
0x140030a79  jbe     short loc_140030AA5
0x140030a7b  mov     rcx, rdi; SpinLock
0x140030a7e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140030a85  nop     dword ptr [rax+rax+00h]
0x140030a8a  or      dword ptr [rdi+440h], 2
0x140030a91  mov     rcx, rdi; SpinLock
0x140030a94  mov     dl, al; NewIrql
0x140030a96  mov     [rdi+8], al
0x140030a99  call    cs:__imp_KeReleaseSpinLock
0x140030aa0  nop     dword ptr [rax+rax+00h]
0x140030aa5  or      dword ptr [rbx+30Ch], 1
0x140030aac  jmp     loc_140030B8E
0x140030ab1  mov     r8, r14; Length
0x140030ab4  lea     rdx, MBB_UUID_AUTH; Source2
0x140030abb  lea     rcx, [rsp+98h+Source1]; Source1
0x140030ac0  call    cs:__imp_RtlCompareMemory
0x140030ac7  nop     dword ptr [rax+rax+00h]
0x140030acc  cmp     rax, r14
0x140030acf  jnz     loc_140030B8E
0x140030ad5  mov     rcx, rdi; SpinLock
0x140030ad8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140030adf  nop     dword ptr [rax+rax+00h]
0x140030ae4  xor     r8d, r8d
0x140030ae7  mov     [rdi+8], al
0x140030aea  cmp     [rbp+0], r8d
0x140030aee  jbe     short loc_140030B26
0x140030af0  mov     edx, [rbp+r8*4+4]
0x140030af5  sub     edx, 1
0x140030af8  jz      short loc_140030B16
0x140030afa  sub     edx, 1
0x140030afd  jz      short loc_140030B0D
0x140030aff  cmp     edx, 1
0x140030b02  jnz     short loc_140030B1D
0x140030b04  or      dword ptr [rdi+440h], 4
0x140030b0b  jmp     short loc_140030B1D
0x140030b0d  or      [rdi+440h], r14d
0x140030b14  jmp     short loc_140030B1D
0x140030b16  or      dword ptr [rdi+440h], 8
0x140030b1d  inc     r8d
0x140030b20  cmp     r8d, [rbp+0]
0x140030b24  jb      short loc_140030AF0
0x140030b26  mov     dl, al; NewIrql
0x140030b28  mov     rcx, rdi; SpinLock
0x140030b2b  call    cs:__imp_KeReleaseSpinLock
0x140030b32  nop     dword ptr [rax+rax+00h]
0x140030b37  or      dword ptr [rbx+30Ch], 2
0x140030b3e  jmp     short loc_140030B8E
0x140030b40  lea     rax, WPP_RECORDER_INITIALIZED
0x140030b47  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140030b4e  jz      short loc_140030B8E
0x140030b50  mov     eax, [rbx+10h]
0x140030b53  mov     r9d, 0D9h
0x140030b59  mov     rcx, cs:WPP_GLOBAL_Control
0x140030b60  mov     dl, 2
0x140030b62  mov     [rsp+98h+var_60], 4
0x140030b6a  mov     dword ptr [rsp+98h+var_68], r8d
0x140030b6f  mov     r8d, 1
0x140030b75  mov     [rsp+98h+var_70], eax
0x140030b79  lea     rax, WPP_b8178d739bbd3ea395057f3ca1574bd6_Traceguids
0x140030b80  mov     rcx, [rcx+40h]
0x140030b84  mov     [rsp+98h+var_78], rax
0x140030b89  call    WPP_RECORDER_SF_Ddd
0x140030b8e  mov     edx, esi; int
0x140030b90  mov     rcx, rbx; struct _MBB_REQUEST_CONTEXT *
0x140030b93  call    ?MbbNdisIndicateDeviceCaps@@YAXPEAU_MBB_REQUEST_CONTEXT@@H@Z; MbbNdisIndicateDeviceCaps(_MBB_REQUEST_CONTEXT *,int)
0x140030b98  mov     eax, esi
0x140030b9a  mov     rcx, [rsp+98h+var_38]
0x140030b9f  xor     rcx, rsp; StackCookie
0x140030ba2  call    __security_check_cookie
0x140030ba7  add     rsp, 70h
0x140030bab  pop     r14
0x140030bad  pop     rdi
0x140030bae  pop     rsi
0x140030baf  pop     rbp
0x140030bb0  pop     rbx
0x140030bb1  retn
```
