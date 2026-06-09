# CBssidConnectHistory::AddEntry_WDFLocks(uchar const (&)[6],ulong,_GUID const &)

- ea: `0x1400bcb60`
- end: `0x1400bcec0`
- name: `?AddEntry_WDFLocks@CBssidConnectHistory@@QEAAXAEAY05$$CBEKAEBU_GUID@@@Z`
- size: `864`
- prototype: `void(CBssidConnectHistory *__hidden this, const unsigned __int8 (*)[6], unsigned int, const struct _GUID *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1400bc7b0`

## callees

- `0x140001008`
- `0x140001a78`
- `0x14002007c`
- `0x14002293c`
- `0x14002ed50`
- `0x14006b8ac`
- `0x140098ba8`
- `0x1400bcb60`
- `0x1400bd318`
- `0x1400dfe00`
- `0x1400e0100`

## pseudocode

```c
void __fastcall CBssidConnectHistory::AddEntry_WDFLocks(
        CBssidConnectHistory *this,
        const unsigned __int8 (*a2)[6],
        int a3,
        const struct _GUID *a4)
{
  int v7; // ebx
  int v8; // r15d
  _QWORD *v9; // r14
  char v10; // r13
  int v11; // edx
  int v12; // r8d
  unsigned int v13; // r9d
  unsigned int i; // edx
  char *v15; // r8
  __int64 v16; // r8
  unsigned __int8 *v17; // rbx
  unsigned int v18; // ecx
  unsigned int v19; // r15d
  unsigned int v20; // r14d
  unsigned int v21; // edi
  unsigned int v22; // eax
  unsigned int v23; // ecx
  unsigned int v24; // edx
  int v25; // ecx
  __int64 v26; // r8
  int v27; // r9d
  void *v28; // rcx
  size_t v29; // r8
  const unsigned __int8 *v30; // rdx
  int v31; // [rsp+20h] [rbp-79h]
  int v32; // [rsp+70h] [rbp-29h] BYREF
  int v33; // [rsp+74h] [rbp-25h] BYREF
  int v34; // [rsp+78h] [rbp-21h] BYREF
  unsigned int v35; // [rsp+7Ch] [rbp-1Dh] BYREF
  __int64 v36; // [rsp+80h] [rbp-19h] BYREF
  __int64 v37; // [rsp+88h] [rbp-11h] BYREF
  __int64 v38; // [rsp+90h] [rbp-9h] BYREF
  __int64 v39; // [rsp+98h] [rbp-1h] BYREF
  const struct _GUID *v40; // [rsp+A0h] [rbp+7h] BYREF
  _BYTE v41[72]; // [rsp+A8h] [rbp+Fh] BYREF

  if ( *(_DWORD *)a2 || *(_WORD *)&(*a2)[4] )
  {
    v7 = -1;
    v8 = 0;
    v9 = 0;
    v10 = 0;
    wil::details::unique_wdf_spin_lock_storage::acquire((char *)this + 704, v41);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v11) = 4;
      WPP_RECORDER_SF__MAC_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v11,
        v12,
        11,
        (__int64)WPP_f78b29c98039335d9b4302cfe054f8d1_Traceguids,
        (__int64)a2,
        a3);
    }
    v13 = *((_DWORD *)this + 169);
    for ( i = 0; i < v13; ++i )
    {
      v15 = (char *)this + 168 * i;
      if ( v15[160] )
      {
        if ( *(_DWORD *)a2 == *(_DWORD *)(v15 + 161) && *(_WORD *)&(*a2)[4] == *(_WORD *)(v15 + 165) )
        {
          v7 = i;
          v10 = 1;
          break;
        }
        if ( v7 == -1 && (!v9 || *v9 > *(_QWORD *)v15) )
        {
          v9 = (_QWORD *)((char *)this + 168 * i);
          v8 = i;
        }
      }
      else if ( v7 == -1 )
      {
        v7 = i;
      }
    }
    if ( v7 != -1 )
      v8 = v7;
    v16 = 168LL * v8;
    v36 = v16;
    v17 = (unsigned __int8 *)this + v16;
    if ( v10 )
    {
      v18 = *((_DWORD *)this + 168);
      v19 = 0;
      v20 = a3;
      v21 = a3;
      while ( v19 < v18 )
      {
        if ( !v17[16 * v19 + 12] )
          break;
        v22 = *(_DWORD *)&v17[16 * v19++ + 8];
        if ( v22 )
        {
          if ( v22 >= v20 )
          {
            if ( v22 > v21 )
              v21 = v22;
          }
          else
          {
            v20 = v22;
          }
        }
      }
      v23 = *((_DWORD *)this + 171);
      if ( v20 <= v23 )
      {
        v24 = *((_DWORD *)this + 170);
        if ( v21 - v20 > v24 )
        {
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_ddddd_MAC_(
              WPP_GLOBAL_Control->DeviceExtension,
              v24,
              v16,
              12,
              v31,
              v20,
              v21,
              a3,
              v24,
              v23,
              (__int64)(v17 + 161));
          if ( (unsigned int)dword_14010EBA8 > 5 )
          {
            if ( (unsigned __int8)tlgKeywordOn(&dword_14010EBA8, 0x400000000000LL) )
            {
              v32 = *((_DWORD *)this + 171);
              v33 = *((_DWORD *)this + 170);
              v37 = *(_QWORD *)v17;
              v34 = a3;
              v35 = v21;
              LODWORD(v36) = v20;
              v38 = *(_QWORD *)((char *)this + 16 * v19 + v26 - 16);
              v39 = v19;
              v40 = a4;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                v25,
                (unsigned int)word_140104D02,
                v26,
                v27,
                (__int64)&v40,
                (__int64)&v39,
                (__int64)&v38,
                (__int64)&v37,
                (__int64)&v36,
                (__int64)&v35,
                (__int64)&v34,
                (__int64)&v33,
                (__int64)&v32);
            }
          }
          memset(v17 + 16, 0, 0x90u);
          goto LABEL_44;
        }
      }
      v28 = v17 + 16;
      v29 = 144;
      v30 = v17;
    }
    else
    {
      if ( v17[160] )
      {
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(i) = 4;
          WPP_RECORDER_SF__MAC_(
            WPP_GLOBAL_Control->DeviceExtension,
            i,
            v16,
            13,
            (__int64)WPP_f78b29c98039335d9b4302cfe054f8d1_Traceguids,
            (__int64)(v17 + 161));
        }
        memset(v17, 0, 0xA0u);
      }
      v28 = v17 + 161;
      v29 = 6;
      v30 = (const unsigned __int8 *)a2;
    }
    memmove(v28, v30, v29);
LABEL_44:
    v17[160] = 1;
    v17[12] = 1;
    *(_QWORD *)v17 = CSystem::get_CurrentTime();
    *((_DWORD *)v17 + 2) = a3;
    wil::details::unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&void WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&void WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>(v41);
  }
}

```

## disassembly

```asm
0x1400bcb60  mov     [rsp-8+arg_18], r9
0x1400bcb65  push    rbp
0x1400bcb66  push    rbx
0x1400bcb67  push    rsi
0x1400bcb68  push    rdi
0x1400bcb69  push    r12
0x1400bcb6b  push    r13
0x1400bcb6d  push    r14
0x1400bcb6f  push    r15
0x1400bcb71  lea     rbp, [rsp-1Fh]
0x1400bcb76  sub     rsp, 0B8h
0x1400bcb7d  mov     eax, cs:dword_1400FEE60
0x1400bcb83  mov     r12d, r8d
0x1400bcb86  mov     rdi, rdx
0x1400bcb89  mov     rsi, rcx
0x1400bcb8c  cmp     eax, [rdx]
0x1400bcb8e  jnz     short loc_1400BCBA1
0x1400bcb90  movzx   eax, cs:word_1400FEE64
0x1400bcb97  cmp     ax, [rdx+4]
0x1400bcb9b  jz      loc_1400BCEAB
0x1400bcba1  or      ebx, 0FFFFFFFFh
0x1400bcba4  lea     rdx, [rbp+57h+var_48]
0x1400bcba8  xor     r15d, r15d
0x1400bcbab  xor     r14d, r14d
0x1400bcbae  xor     r13b, r13b
0x1400bcbb1  add     rcx, 2C0h
0x1400bcbb8  call    ?acquire@unique_wdf_spin_lock_storage@details@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUWDFSPINLOCK__@@P6AXPEAU1@@Z$1?WdfSpinLockRelease@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@XZ; wil::details::unique_wdf_spin_lock_storage::acquire(void)
0x1400bcbbd  lea     r11, WPP_RECORDER_INITIALIZED
0x1400bcbc4  cmp     cs:WPP_RECORDER_INITIALIZED, r11
0x1400bcbcb  lea     r10, WPP_f78b29c98039335d9b4302cfe054f8d1_Traceguids
0x1400bcbd2  jz      short loc_1400BCC07
0x1400bcbd4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bcbdb  lea     r9d, [rbx+0Ch]
0x1400bcbdf  mov     dword ptr [rsp+0F0h+var_C0], r12d
0x1400bcbe4  mov     dl, 4
0x1400bcbe6  mov     [rsp+0F0h+var_C8], rdi
0x1400bcbeb  mov     [rsp+0F0h+var_D0], r10
0x1400bcbf0  mov     rcx, [rcx+40h]
0x1400bcbf4  call    WPP_RECORDER_SF__MAC_d
0x1400bcbf9  lea     r10, WPP_f78b29c98039335d9b4302cfe054f8d1_Traceguids
0x1400bcc00  lea     r11, WPP_RECORDER_INITIALIZED
0x1400bcc07  mov     r9d, [rsi+2A4h]
0x1400bcc0e  xor     edx, edx
0x1400bcc10  test    r9d, r9d
0x1400bcc13  jz      short loc_1400BCC71
0x1400bcc15  mov     eax, edx
0x1400bcc17  imul    r8, rax, 0A8h
0x1400bcc1e  add     r8, rsi
0x1400bcc21  cmp     [r8+0A0h], r13b
0x1400bcc28  jz      short loc_1400BCC5D
0x1400bcc2a  mov     eax, [rdi]
0x1400bcc2c  cmp     eax, [r8+0A1h]
0x1400bcc33  jnz     short loc_1400BCC43
0x1400bcc35  movzx   eax, word ptr [rdi+4]
0x1400bcc39  cmp     ax, [r8+0A5h]
0x1400bcc41  jz      short loc_1400BCC6C
0x1400bcc43  cmp     ebx, 0FFFFFFFFh
0x1400bcc46  jnz     short loc_1400BCC63
0x1400bcc48  test    r14, r14
0x1400bcc4b  jz      short loc_1400BCC55
0x1400bcc4d  mov     rax, [r8]
0x1400bcc50  cmp     [r14], rax
0x1400bcc53  jbe     short loc_1400BCC63
0x1400bcc55  mov     r14, r8
0x1400bcc58  mov     r15d, edx
0x1400bcc5b  jmp     short loc_1400BCC63
0x1400bcc5d  cmp     ebx, 0FFFFFFFFh
0x1400bcc60  cmovz   ebx, edx
0x1400bcc63  inc     edx
0x1400bcc65  cmp     edx, r9d
0x1400bcc68  jb      short loc_1400BCC15
0x1400bcc6a  jmp     short loc_1400BCC71
0x1400bcc6c  mov     ebx, edx
0x1400bcc6e  mov     r13b, 1
0x1400bcc71  cmp     ebx, 0FFFFFFFFh
0x1400bcc74  cmovnz  r15d, ebx
0x1400bcc78  movsxd  rax, r15d
0x1400bcc7b  imul    r8, rax, 0A8h
0x1400bcc82  mov     [rbp+57h+var_70], r8
0x1400bcc86  lea     rbx, [r8+rsi]
0x1400bcc8a  test    r13b, r13b
0x1400bcc8d  jz      loc_1400BCE2B
0x1400bcc93  mov     ecx, [rsi+2A0h]
0x1400bcc99  xor     r15d, r15d
0x1400bcc9c  mov     r14d, r12d
0x1400bcc9f  mov     edi, r12d
0x1400bcca2  test    ecx, ecx
0x1400bcca4  jz      short loc_1400BCCD2
0x1400bcca6  mov     eax, r15d
0x1400bcca9  add     rax, rax
0x1400bccac  cmp     byte ptr [rbx+rax*8+0Ch], 0
0x1400bccb1  jz      short loc_1400BCCD2
0x1400bccb3  mov     eax, [rbx+rax*8+8]
0x1400bccb7  inc     r15d
0x1400bccba  test    eax, eax
0x1400bccbc  jz      short loc_1400BCCCD
0x1400bccbe  cmp     eax, r14d
0x1400bccc1  jnb     short loc_1400BCCC8
0x1400bccc3  mov     r14d, eax
0x1400bccc6  jmp     short loc_1400BCCCD
0x1400bccc8  cmp     eax, edi
0x1400bccca  cmova   edi, eax
0x1400bcccd  cmp     r15d, ecx
0x1400bccd0  jb      short loc_1400BCCA6
0x1400bccd2  mov     ecx, [rsi+2ACh]
0x1400bccd8  cmp     r14d, ecx
0x1400bccdb  ja      loc_1400BCE1C
0x1400bcce1  mov     edx, [rsi+2A8h]
0x1400bcce7  mov     eax, edi
0x1400bcce9  sub     eax, r14d
0x1400bccec  cmp     eax, edx
0x1400bccee  jbe     loc_1400BCE1C
0x1400bccf4  cmp     cs:WPP_RECORDER_INITIALIZED, r11
0x1400bccfb  jz      short loc_1400BCD39
0x1400bccfd  lea     rax, [rbx+0A1h]
0x1400bcd04  mov     r9d, 0Ch
0x1400bcd0a  mov     [rsp+0F0h+var_A0], rax
0x1400bcd0f  mov     dword ptr [rsp+0F0h+var_A8], ecx
0x1400bcd13  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bcd1a  mov     dword ptr [rsp+0F0h+var_B0], edx
0x1400bcd1e  mov     dword ptr [rsp+0F0h+var_B8], r12d
0x1400bcd23  mov     dword ptr [rsp+0F0h+var_C0], edi
0x1400bcd27  mov     rcx, [rcx+40h]
0x1400bcd2b  mov     dword ptr [rsp+0F0h+var_C8], r14d
0x1400bcd30  call    WPP_RECORDER_SF_ddddd_MAC_
0x1400bcd35  mov     r8, [rbp+57h+var_70]
0x1400bcd39  mov     eax, cs:dword_14010EBA8
0x1400bcd3f  cmp     eax, 5
0x1400bcd42  jbe     loc_1400BCE09
0x1400bcd48  mov     rdx, 400000000000h
0x1400bcd52  lea     rcx, dword_14010EBA8
0x1400bcd59  call    _tlgKeywordOn
0x1400bcd5e  test    al, al
0x1400bcd60  jz      loc_1400BCE09
0x1400bcd66  mov     eax, [rsi+2ACh]
0x1400bcd6c  lea     rdx, word_140104D02
0x1400bcd73  mov     [rbp+57h+var_80], eax
0x1400bcd76  mov     eax, [rsi+2A8h]
0x1400bcd7c  mov     [rbp+57h+var_7C], eax
0x1400bcd7f  mov     rax, [rbx]
0x1400bcd82  mov     [rbp+57h+var_68], rax
0x1400bcd86  lea     eax, [r15-1]
0x1400bcd8a  shl     rax, 4
0x1400bcd8e  add     rax, r8
0x1400bcd91  mov     [rbp+57h+var_78], r12d
0x1400bcd95  mov     [rbp+57h+var_74], edi
0x1400bcd98  mov     dword ptr [rbp+57h+var_70], r14d
0x1400bcd9c  mov     rax, [rax+rsi]
0x1400bcda0  mov     [rbp+57h+var_60], rax
0x1400bcda4  mov     eax, r15d
0x1400bcda7  mov     [rbp+57h+var_58], rax
0x1400bcdab  mov     rax, [rbp+57h+arg_18]
0x1400bcdaf  mov     [rbp+57h+var_50], rax
0x1400bcdb3  lea     rax, [rbp+57h+var_80]
0x1400bcdb7  mov     [rsp+0F0h+var_90], rax
0x1400bcdbc  lea     rax, [rbp+57h+var_7C]
0x1400bcdc0  mov     [rsp+0F0h+var_98], rax
0x1400bcdc5  lea     rax, [rbp+57h+var_78]
0x1400bcdc9  mov     [rsp+0F0h+var_A0], rax
0x1400bcdce  lea     rax, [rbp+57h+var_74]
0x1400bcdd2  mov     [rsp+0F0h+var_A8], rax
0x1400bcdd7  lea     rax, [rbp+57h+var_70]
0x1400bcddb  mov     [rsp+0F0h+var_B0], rax
0x1400bcde0  lea     rax, [rbp+57h+var_68]
0x1400bcde4  mov     [rsp+0F0h+var_B8], rax
0x1400bcde9  lea     rax, [rbp+57h+var_60]
0x1400bcded  mov     [rsp+0F0h+var_C0], rax
0x1400bcdf2  lea     rax, [rbp+57h+var_58]
0x1400bcdf6  mov     [rsp+0F0h+var_C8], rax
0x1400bcdfb  lea     rax, [rbp+57h+var_50]
0x1400bcdff  mov     [rsp+0F0h+var_D0], rax
0x1400bce04  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@U2@U2@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@44AEBU?$_tlgWrapperByVal@$03@@5555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400bce09  lea     rcx, [rbx+10h]; void *
0x1400bce0d  xor     edx, edx; Val
0x1400bce0f  mov     r8d, 90h; Size
0x1400bce15  call    memset
0x1400bce1a  jmp     short loc_1400BCE8B
0x1400bce1c  lea     rcx, [rbx+10h]
0x1400bce20  mov     r8d, 90h
0x1400bce26  mov     rdx, rbx
0x1400bce29  jmp     short loc_1400BCE86
0x1400bce2b  cmp     byte ptr [rbx+0A0h], 0
0x1400bce32  jz      short loc_1400BCE76
0x1400bce34  cmp     cs:WPP_RECORDER_INITIALIZED, r11
0x1400bce3b  jz      short loc_1400BCE66
0x1400bce3d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bce44  lea     rax, [rbx+0A1h]
0x1400bce4b  mov     [rsp+0F0h+var_C8], rax
0x1400bce50  mov     r9d, 0Dh
0x1400bce56  mov     dl, 4
0x1400bce58  mov     [rsp+0F0h+var_D0], r10
0x1400bce5d  mov     rcx, [rcx+40h]
0x1400bce61  call    WPP_RECORDER_SF__MAC_
0x1400bce66  xor     edx, edx; Val
0x1400bce68  mov     r8d, 0A0h; Size
0x1400bce6e  mov     rcx, rbx; void *
0x1400bce71  call    memset
0x1400bce76  lea     rcx, [rbx+0A1h]; void *
0x1400bce7d  mov     r8d, 6; Size
0x1400bce83  mov     rdx, rdi; Src
0x1400bce86  call    memmove
0x1400bce8b  mov     byte ptr [rbx+0A0h], 1
0x1400bce92  mov     byte ptr [rbx+0Ch], 1
0x1400bce96  call    ?get_CurrentTime@CSystem@@SA_KXZ; CSystem::get_CurrentTime(void)
0x1400bce9b  lea     rcx, [rbp+57h+var_48]
0x1400bce9f  mov     [rbx], rax
0x1400bcea2  mov     [rbx+8], r12d
0x1400bcea6  call    ??1?$unique_storage@U?$resource_policy@PEAUWDFSPINLOCK__@@P6AXPEAU1@@Z$1?WdfSpinLockRelease@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSPINLOCK__ *,void (*)(WDFSPINLOCK__ *),&WdfSpinLockRelease(WDFSPINLOCK__ *),wistd::integral_constant<unsigned __int64,2>,WDFSPINLOCK__ *,WDFSPINLOCK__ *,0,std::nullptr_t>>(void)
0x1400bceab  add     rsp, 0B8h
0x1400bceb2  pop     r15
0x1400bceb4  pop     r14
0x1400bceb6  pop     r13
0x1400bceb8  pop     r12
0x1400bceba  pop     rdi
0x1400bcebb  pop     rsi
0x1400bcebc  pop     rbx
0x1400bcebd  pop     rbp
0x1400bcebe  retn
```
