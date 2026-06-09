# CBssidConnectHistory::AddEntry(uchar const (&)[6],ulong,_GUID const &)

- ea: `0x1400bc7b0`
- end: `0x1400bcb57`
- name: `?AddEntry@CBssidConnectHistory@@QEAAXAEAY05$$CBEKAEBU_GUID@@@Z`
- size: `935`
- prototype: `void(CBssidConnectHistory *__hidden this, const unsigned __int8 (*)[6], unsigned int, const struct _GUID *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1400a77e8`

## callees

- `0x140001008`
- `0x140001a78`
- `0x14000cf40`
- `0x14002ed50`
- `0x14006b8ac`
- `0x140098ba8`
- `0x1400bc7b0`
- `0x1400bcb60`
- `0x1400bd318`
- `0x1400dfe00`
- `0x1400e0100`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x1400bcb23`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bcb23`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bc818`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bc818`

## pseudocode

```c
void __fastcall CBssidConnectHistory::AddEntry(
        CBssidConnectHistory *this,
        const unsigned __int8 (*a2)[6],
        __int64 a3,
        const struct _GUID *a4)
{
  unsigned int v5; // r12d
  __int64 v8; // rbx
  _QWORD *v9; // r13
  int v10; // edi
  int v11; // r15d
  int v12; // edx
  int v13; // r8d
  unsigned int v14; // r9d
  unsigned int i; // edx
  char *v16; // r8
  __int64 v17; // r8
  unsigned __int8 *v18; // rdi
  unsigned int v19; // ecx
  unsigned int v20; // r13d
  unsigned int v21; // r15d
  unsigned int v22; // esi
  unsigned int v23; // eax
  unsigned int v24; // ecx
  unsigned int v25; // edx
  int v26; // ecx
  __int64 v27; // r8
  int v28; // r9d
  void *v29; // rcx
  size_t v30; // r8
  const unsigned __int8 *v31; // rdx
  KIRQL v32; // dl
  int v33; // [rsp+20h] [rbp-79h]
  char v34; // [rsp+70h] [rbp-29h]
  int v35; // [rsp+74h] [rbp-25h] BYREF
  int v36; // [rsp+78h] [rbp-21h] BYREF
  unsigned int v37; // [rsp+7Ch] [rbp-1Dh] BYREF
  unsigned int v38; // [rsp+80h] [rbp-19h] BYREF
  __int64 v39; // [rsp+88h] [rbp-11h] BYREF
  __int64 v40; // [rsp+90h] [rbp-9h] BYREF
  __int64 v41; // [rsp+98h] [rbp-1h] BYREF
  __int64 v42; // [rsp+A0h] [rbp+7h] BYREF
  const struct _GUID *v43; // [rsp+A8h] [rbp+Fh] BYREF

  v5 = a3;
  if ( (unsigned int)Feature_54699885__private_IsEnabledDeviceUsageNoInline(this, (const unsigned __int8 *)a2, a3) )
  {
    CBssidConnectHistory::AddEntry_WDFLocks(this, a2, v5, a4);
  }
  else if ( *(_DWORD *)a2 || *(_WORD *)&(*a2)[4] )
  {
    v8 = *((_QWORD *)this + 87);
    v9 = 0;
    v34 = 0;
    v10 = -1;
    v11 = 0;
    *(_BYTE *)(v8 + 8) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v8);
    *(_BYTE *)(v8 + 16) = 1;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = 4;
      WPP_RECORDER_SF__MAC_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v12,
        v13,
        14,
        (__int64)WPP_f78b29c98039335d9b4302cfe054f8d1_Traceguids,
        (__int64)a2,
        v5);
    }
    v14 = *((_DWORD *)this + 169);
    for ( i = 0; i < v14; ++i )
    {
      v16 = (char *)this + 168 * i;
      if ( v16[160] )
      {
        if ( *(_DWORD *)a2 == *(_DWORD *)(v16 + 161) && *(_WORD *)&(*a2)[4] == *(_WORD *)(v16 + 165) )
        {
          v10 = i;
          v34 = 1;
          break;
        }
        if ( v10 == -1 && (!v9 || *v9 > *(_QWORD *)v16) )
        {
          v9 = (_QWORD *)((char *)this + 168 * i);
          v11 = i;
        }
      }
      else if ( v10 == -1 )
      {
        v10 = i;
      }
    }
    if ( v10 != -1 )
      v11 = v10;
    v17 = 168LL * v11;
    v39 = v17;
    v18 = (unsigned __int8 *)this + v17;
    if ( v34 )
    {
      v19 = *((_DWORD *)this + 168);
      v20 = 0;
      v21 = v5;
      v22 = v5;
      while ( v20 < v19 )
      {
        if ( !v18[16 * v20 + 12] )
          break;
        v23 = *(_DWORD *)&v18[16 * v20++ + 8];
        if ( v23 )
        {
          if ( v23 >= v21 )
          {
            if ( v23 > v22 )
              v22 = v23;
          }
          else
          {
            v21 = v23;
          }
        }
      }
      v24 = *((_DWORD *)this + 171);
      if ( v21 <= v24 )
      {
        v25 = *((_DWORD *)this + 170);
        if ( v22 - v21 > v25 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_ddddd_MAC_(
              WPP_GLOBAL_Control->DeviceExtension,
              v25,
              v17,
              15,
              v33,
              v21,
              v22,
              v5,
              v25,
              v24,
              (__int64)(v18 + 161));
          if ( (unsigned int)dword_14010EBA8 > 5 )
          {
            if ( (unsigned __int8)tlgKeywordOn(&dword_14010EBA8, 0x400000000000LL) )
            {
              v35 = *((_DWORD *)this + 171);
              v36 = *((_DWORD *)this + 170);
              v40 = *(_QWORD *)v18;
              v37 = v5;
              v38 = v22;
              LODWORD(v39) = v21;
              v41 = *(_QWORD *)((char *)this + 16 * v20 + v27 - 16);
              v42 = v20;
              v43 = a4;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                v26,
                (unsigned int)&dword_140104C44,
                v27,
                v28,
                (__int64)&v43,
                (__int64)&v42,
                (__int64)&v41,
                (__int64)&v40,
                (__int64)&v39,
                (__int64)&v38,
                (__int64)&v37,
                (__int64)&v36,
                (__int64)&v35);
            }
          }
          memset(v18 + 16, 0, 0x90u);
          goto LABEL_45;
        }
      }
      v29 = v18 + 16;
      v30 = 144;
      v31 = v18;
    }
    else
    {
      if ( v18[160] )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(i) = 4;
          WPP_RECORDER_SF__MAC_(
            WPP_GLOBAL_Control->DeviceExtension,
            i,
            v17,
            16,
            (__int64)WPP_f78b29c98039335d9b4302cfe054f8d1_Traceguids,
            (__int64)(v18 + 161));
        }
        memset(v18, 0, 0xA0u);
      }
      v29 = v18 + 161;
      v30 = 6;
      v31 = (const unsigned __int8 *)a2;
    }
    memmove(v29, v31, v30);
LABEL_45:
    v18[160] = 1;
    v18[12] = 1;
    *(_QWORD *)v18 = CSystem::get_CurrentTime();
    *((_DWORD *)v18 + 2) = v5;
    v32 = *(_BYTE *)(v8 + 8);
    *(_BYTE *)(v8 + 16) = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)v8, v32);
  }
}

```

## disassembly

```asm
0x1400bc7b0  mov     [rsp-8+arg_18], r9
0x1400bc7b5  push    rbp
0x1400bc7b6  push    rbx
0x1400bc7b7  push    rsi
0x1400bc7b8  push    rdi
0x1400bc7b9  push    r12
0x1400bc7bb  push    r13
0x1400bc7bd  push    r14
0x1400bc7bf  push    r15
0x1400bc7c1  lea     rbp, [rsp-1Fh]
0x1400bc7c6  sub     rsp, 0B8h
0x1400bc7cd  mov     rbx, r9
0x1400bc7d0  mov     r12d, r8d
0x1400bc7d3  mov     rsi, rdx
0x1400bc7d6  mov     r14, rcx
0x1400bc7d9  call    Feature_54699885__private_IsEnabledDeviceUsageNoInline
0x1400bc7de  test    eax, eax
0x1400bc7e0  jnz     loc_1400BCB31
0x1400bc7e6  mov     eax, cs:dword_1400FEE60
0x1400bc7ec  cmp     eax, [rsi]
0x1400bc7ee  jnz     short loc_1400BC801
0x1400bc7f0  movzx   eax, cs:word_1400FEE64
0x1400bc7f7  cmp     ax, [rsi+4]
0x1400bc7fb  jz      loc_1400BCB42
0x1400bc801  mov     rbx, [r14+2B8h]
0x1400bc808  xor     r13d, r13d
0x1400bc80b  mov     rcx, rbx; SpinLock
0x1400bc80e  mov     [rbp+57h+var_80], r13b
0x1400bc812  or      edi, 0FFFFFFFFh
0x1400bc815  xor     r15d, r15d
0x1400bc818  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400bc81f  nop     dword ptr [rax+rax+00h]
0x1400bc824  mov     [rbx+8], al
0x1400bc827  mov     byte ptr [rbx+10h], 1
0x1400bc82b  lea     r11, WPP_RECORDER_INITIALIZED
0x1400bc832  cmp     cs:WPP_RECORDER_INITIALIZED, r11
0x1400bc839  lea     r10, WPP_f78b29c98039335d9b4302cfe054f8d1_Traceguids
0x1400bc840  jz      short loc_1400BC875
0x1400bc842  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bc849  lea     r9d, [rdi+0Fh]
0x1400bc84d  mov     dword ptr [rsp+0F0h+var_C0], r12d
0x1400bc852  mov     dl, 4
0x1400bc854  mov     [rsp+0F0h+var_C8], rsi
0x1400bc859  mov     [rsp+0F0h+var_D0], r10
0x1400bc85e  mov     rcx, [rcx+40h]
0x1400bc862  call    WPP_RECORDER_SF__MAC_d
0x1400bc867  lea     r10, WPP_f78b29c98039335d9b4302cfe054f8d1_Traceguids
0x1400bc86e  lea     r11, WPP_RECORDER_INITIALIZED
0x1400bc875  mov     r9d, [r14+2A4h]
0x1400bc87c  xor     edx, edx
0x1400bc87e  test    r9d, r9d
0x1400bc881  jz      short loc_1400BC8E2
0x1400bc883  mov     eax, edx
0x1400bc885  imul    r8, rax, 0A8h
0x1400bc88c  add     r8, r14
0x1400bc88f  cmp     byte ptr [r8+0A0h], 0
0x1400bc897  jz      short loc_1400BC8CD
0x1400bc899  mov     eax, [rsi]
0x1400bc89b  cmp     eax, [r8+0A1h]
0x1400bc8a2  jnz     short loc_1400BC8B2
0x1400bc8a4  movzx   eax, word ptr [rsi+4]
0x1400bc8a8  cmp     ax, [r8+0A5h]
0x1400bc8b0  jz      short loc_1400BC8DC
0x1400bc8b2  cmp     edi, 0FFFFFFFFh
0x1400bc8b5  jnz     short loc_1400BC8D3
0x1400bc8b7  test    r13, r13
0x1400bc8ba  jz      short loc_1400BC8C5
0x1400bc8bc  mov     rax, [r8]
0x1400bc8bf  cmp     [r13+0], rax
0x1400bc8c3  jbe     short loc_1400BC8D3
0x1400bc8c5  mov     r13, r8
0x1400bc8c8  mov     r15d, edx
0x1400bc8cb  jmp     short loc_1400BC8D3
0x1400bc8cd  cmp     edi, 0FFFFFFFFh
0x1400bc8d0  cmovz   edi, edx
0x1400bc8d3  inc     edx
0x1400bc8d5  cmp     edx, r9d
0x1400bc8d8  jb      short loc_1400BC883
0x1400bc8da  jmp     short loc_1400BC8E2
0x1400bc8dc  mov     edi, edx
0x1400bc8de  mov     [rbp+57h+var_80], 1
0x1400bc8e2  cmp     edi, 0FFFFFFFFh
0x1400bc8e5  cmovnz  r15d, edi
0x1400bc8e9  movsxd  rax, r15d
0x1400bc8ec  imul    r8, rax, 0A8h
0x1400bc8f3  cmp     [rbp+57h+var_80], 0
0x1400bc8f7  mov     [rbp+57h+var_68], r8
0x1400bc8fb  lea     rdi, [r8+r14]
0x1400bc8ff  jz      loc_1400BCAA2
0x1400bc905  mov     ecx, [r14+2A0h]
0x1400bc90c  xor     r13d, r13d
0x1400bc90f  mov     r15d, r12d
0x1400bc912  mov     esi, r12d
0x1400bc915  test    ecx, ecx
0x1400bc917  jz      short loc_1400BC945
0x1400bc919  mov     eax, r13d
0x1400bc91c  add     rax, rax
0x1400bc91f  cmp     byte ptr [rdi+rax*8+0Ch], 0
0x1400bc924  jz      short loc_1400BC945
0x1400bc926  mov     eax, [rdi+rax*8+8]
0x1400bc92a  inc     r13d
0x1400bc92d  test    eax, eax
0x1400bc92f  jz      short loc_1400BC940
0x1400bc931  cmp     eax, r15d
0x1400bc934  jnb     short loc_1400BC93B
0x1400bc936  mov     r15d, eax
0x1400bc939  jmp     short loc_1400BC940
0x1400bc93b  cmp     eax, esi
0x1400bc93d  cmova   esi, eax
0x1400bc940  cmp     r13d, ecx
0x1400bc943  jb      short loc_1400BC919
0x1400bc945  mov     ecx, [r14+2ACh]
0x1400bc94c  cmp     r15d, ecx
0x1400bc94f  ja      loc_1400BCA93
0x1400bc955  mov     edx, [r14+2A8h]
0x1400bc95c  mov     eax, esi
0x1400bc95e  sub     eax, r15d
0x1400bc961  cmp     eax, edx
0x1400bc963  jbe     loc_1400BCA93
0x1400bc969  cmp     cs:WPP_RECORDER_INITIALIZED, r11
0x1400bc970  jz      short loc_1400BC9AE
0x1400bc972  lea     rax, [rdi+0A1h]
0x1400bc979  mov     r9d, 0Fh
0x1400bc97f  mov     [rsp+0F0h+var_A0], rax
0x1400bc984  mov     dword ptr [rsp+0F0h+var_A8], ecx
0x1400bc988  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bc98f  mov     dword ptr [rsp+0F0h+var_B0], edx
0x1400bc993  mov     dword ptr [rsp+0F0h+var_B8], r12d
0x1400bc998  mov     dword ptr [rsp+0F0h+var_C0], esi
0x1400bc99c  mov     rcx, [rcx+40h]
0x1400bc9a0  mov     dword ptr [rsp+0F0h+var_C8], r15d
0x1400bc9a5  call    WPP_RECORDER_SF_ddddd_MAC_
0x1400bc9aa  mov     r8, [rbp+57h+var_68]
0x1400bc9ae  mov     eax, cs:dword_14010EBA8
0x1400bc9b4  cmp     eax, 5
0x1400bc9b7  jbe     loc_1400BCA80
0x1400bc9bd  mov     rdx, 400000000000h
0x1400bc9c7  lea     rcx, dword_14010EBA8
0x1400bc9ce  call    _tlgKeywordOn
0x1400bc9d3  test    al, al
0x1400bc9d5  jz      loc_1400BCA80
0x1400bc9db  mov     eax, [r14+2ACh]
0x1400bc9e2  lea     rdx, dword_140104C44
0x1400bc9e9  mov     [rbp+57h+var_7C], eax
0x1400bc9ec  mov     eax, [r14+2A8h]
0x1400bc9f3  mov     [rbp+57h+var_78], eax
0x1400bc9f6  mov     rax, [rdi]
0x1400bc9f9  mov     [rbp+57h+var_60], rax
0x1400bc9fd  lea     eax, [r13-1]
0x1400bca01  shl     rax, 4
0x1400bca05  add     rax, r8
0x1400bca08  mov     [rbp+57h+var_74], r12d
0x1400bca0c  mov     [rbp+57h+var_70], esi
0x1400bca0f  mov     dword ptr [rbp+57h+var_68], r15d
0x1400bca13  mov     rax, [rax+r14]
0x1400bca17  mov     [rbp+57h+var_58], rax
0x1400bca1b  mov     eax, r13d
0x1400bca1e  mov     [rbp+57h+var_50], rax
0x1400bca22  mov     rax, [rbp+57h+arg_18]
0x1400bca26  mov     [rbp+57h+var_48], rax
0x1400bca2a  lea     rax, [rbp+57h+var_7C]
0x1400bca2e  mov     [rsp+0F0h+var_90], rax
0x1400bca33  lea     rax, [rbp+57h+var_78]
0x1400bca37  mov     [rsp+0F0h+var_98], rax
0x1400bca3c  lea     rax, [rbp+57h+var_74]
0x1400bca40  mov     [rsp+0F0h+var_A0], rax
0x1400bca45  lea     rax, [rbp+57h+var_70]
0x1400bca49  mov     [rsp+0F0h+var_A8], rax
0x1400bca4e  lea     rax, [rbp+57h+var_68]
0x1400bca52  mov     [rsp+0F0h+var_B0], rax
0x1400bca57  lea     rax, [rbp+57h+var_60]
0x1400bca5b  mov     [rsp+0F0h+var_B8], rax
0x1400bca60  lea     rax, [rbp+57h+var_58]
0x1400bca64  mov     [rsp+0F0h+var_C0], rax
0x1400bca69  lea     rax, [rbp+57h+var_50]
0x1400bca6d  mov     [rsp+0F0h+var_C8], rax
0x1400bca72  lea     rax, [rbp+57h+var_48]
0x1400bca76  mov     [rsp+0F0h+var_D0], rax
0x1400bca7b  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@U2@U2@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@44AEBU?$_tlgWrapperByVal@$03@@5555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400bca80  lea     rcx, [rdi+10h]; void *
0x1400bca84  xor     edx, edx; Val
0x1400bca86  mov     r8d, 90h; Size
0x1400bca8c  call    memset
0x1400bca91  jmp     short loc_1400BCB02
0x1400bca93  lea     rcx, [rdi+10h]
0x1400bca97  mov     r8d, 90h
0x1400bca9d  mov     rdx, rdi
0x1400bcaa0  jmp     short loc_1400BCAFD
0x1400bcaa2  cmp     byte ptr [rdi+0A0h], 0
0x1400bcaa9  jz      short loc_1400BCAED
0x1400bcaab  cmp     cs:WPP_RECORDER_INITIALIZED, r11
0x1400bcab2  jz      short loc_1400BCADD
0x1400bcab4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bcabb  lea     rax, [rdi+0A1h]
0x1400bcac2  mov     [rsp+0F0h+var_C8], rax
0x1400bcac7  mov     r9d, 10h
0x1400bcacd  mov     dl, 4
0x1400bcacf  mov     [rsp+0F0h+var_D0], r10
0x1400bcad4  mov     rcx, [rcx+40h]
0x1400bcad8  call    WPP_RECORDER_SF__MAC_
0x1400bcadd  xor     edx, edx; Val
0x1400bcadf  mov     r8d, 0A0h; Size
0x1400bcae5  mov     rcx, rdi; void *
0x1400bcae8  call    memset
0x1400bcaed  lea     rcx, [rdi+0A1h]; void *
0x1400bcaf4  mov     r8d, 6; Size
0x1400bcafa  mov     rdx, rsi; Src
0x1400bcafd  call    memmove
0x1400bcb02  mov     byte ptr [rdi+0A0h], 1
0x1400bcb09  mov     byte ptr [rdi+0Ch], 1
0x1400bcb0d  call    ?get_CurrentTime@CSystem@@SA_KXZ; CSystem::get_CurrentTime(void)
0x1400bcb12  mov     [rdi], rax
0x1400bcb15  mov     rcx, rbx; SpinLock
0x1400bcb18  mov     [rdi+8], r12d
0x1400bcb1c  mov     dl, [rbx+8]; NewIrql
0x1400bcb1f  mov     byte ptr [rbx+10h], 0
0x1400bcb23  call    cs:__imp_KeReleaseSpinLock
0x1400bcb2a  nop     dword ptr [rax+rax+00h]
0x1400bcb2f  jmp     short loc_1400BCB42
0x1400bcb31  mov     r9, rbx; struct _GUID *
0x1400bcb34  mov     r8d, r12d; unsigned int
0x1400bcb37  mov     rdx, rsi; unsigned __int8 (*)[6]
0x1400bcb3a  mov     rcx, r14; this
0x1400bcb3d  call    ?AddEntry_WDFLocks@CBssidConnectHistory@@QEAAXAEAY05$$CBEKAEBU_GUID@@@Z; CBssidConnectHistory::AddEntry_WDFLocks(uchar const (&)[6],ulong,_GUID const &)
0x1400bcb42  add     rsp, 0B8h
0x1400bcb49  pop     r15
0x1400bcb4b  pop     r14
0x1400bcb4d  pop     r13
0x1400bcb4f  pop     r12
0x1400bcb51  pop     rdi
0x1400bcb52  pop     rsi
0x1400bcb53  pop     rbx
0x1400bcb54  pop     rbp
0x1400bcb55  retn
```
