# MbbIpReportIps(_MBB_IPADDRESS_ENTRY *,ulong,_NET_LUID_LH *,ulong)

- ea: `0x1400450ac`
- end: `0x14004543f`
- name: `?MbbIpReportIps@@YAXPEAU_MBB_IPADDRESS_ENTRY@@KPEAT_NET_LUID_LH@@K@Z`
- size: `915`
- prototype: `void __fastcall(struct _MBB_IPADDRESS_ENTRY *, unsigned int, union _NET_LUID_LH *, NET_IFINDEX)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x140042bf4`

## callees

- `0x1400013ec`
- `0x1400450ac`
- `0x140046378`
- `0x140046458`
- `0x1400466a4`
- `0x140046784`
- `0x140047e50`
- `0x140048340`

## import_xrefs

- `NETIO!InitializeUnicastIpAddressEntry` at `0x14004511b`
- `NETIO!InitializeUnicastIpAddressEntry` at `0x14004511b`
- `NETIO!DeleteUnicastIpAddressEntry` at `0x14004519c`
- `NETIO!DeleteUnicastIpAddressEntry` at `0x14004519c`
- `NETIO!CreateUnicastIpAddressEntry` at `0x140045183`
- `NETIO!CreateUnicastIpAddressEntry` at `0x1400451e9`
- `NETIO!CreateUnicastIpAddressEntry` at `0x1400452fc`
- `NETIO!CreateUnicastIpAddressEntry` at `0x140045183`
- `NETIO!CreateUnicastIpAddressEntry` at `0x1400451e9`
- `NETIO!CreateUnicastIpAddressEntry` at `0x1400452fc`

## pseudocode

```c
void __fastcall MbbIpReportIps(
        struct _MBB_IPADDRESS_ENTRY *a1,
        unsigned int a2,
        union _NET_LUID_LH *a3,
        NET_IFINDEX a4)
{
  NET_IFINDEX v5; // ebx
  unsigned int v8; // r12d
  __int64 v9; // r14
  UINT8 v10; // cl
  int v11; // eax
  int v12; // edx
  NTSTATUS v13; // ebx
  int v14; // r8d
  int v15; // r9d
  char v16; // al
  int v17; // edx
  int v18; // r8d
  __int128 v19; // xmm0
  int v20; // edx
  NTSTATUS v21; // ebx
  int v22; // r8d
  int v23; // r9d
  int v24; // [rsp+20h] [rbp-79h]
  NTSTATUS OnLinkPrefixLength; // [rsp+40h] [rbp-59h] BYREF
  NTSTATUS v26; // [rsp+44h] [rbp-55h] BYREF
  NET_IFINDEX v27; // [rsp+48h] [rbp-51h]
  _QWORD v28[2]; // [rsp+50h] [rbp-49h] BYREF
  struct _MIB_UNICASTIPADDRESS_ROW Row; // [rsp+60h] [rbp-39h] BYREF

  v5 = a4;
  v27 = a4;
  memset(&Row, 0, sizeof(Row));
  v8 = 0;
  if ( a2 )
  {
    v9 = 0;
    do
    {
      if ( (*((_DWORD *)a1 + 6 * v9) & 2) == 0 )
      {
        InitializeUnicastIpAddressEntry(&Row);
        v10 = *((_BYTE *)a1 + 24 * v9 + 4);
        Row.CreationTimeStamp.QuadPart = MEMORY[0xFFFFF78000000014];
        Row.InterfaceLuid = (NET_LUID)a3->Value;
        Row.ValidLifetime = -1;
        Row.PreferredLifetime = -1;
        v11 = *((_DWORD *)a1 + 6 * v9);
        Row.OnLinkPrefixLength = v10;
        Row.InterfaceIndex = v5;
        Row.PrefixOrigin = IpPrefixOriginManual;
        Row.SuffixOrigin = NlsoManual;
        Row.SkipAsSource = 0;
        if ( (v11 & 1) != 0 )
        {
          v19 = *(_OWORD *)((char *)a1 + 24 * v9 + 8);
          Row.Address.Ipv4.sin_family = 23;
          *(_OWORD *)(&Row.Address.si_family + 4) = v19;
          v21 = CreateUnicastIpAddressEntry(&Row);
          if ( v21 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_i_IPV6_d(
                WPP_GLOBAL_Control->DeviceExtension,
                v20,
                v22,
                74,
                v24,
                a3->Value,
                (__int64)(&Row.Address.si_family + 4),
                v21);
            if ( (unsigned int)dword_14005E0C8 > 5
              && (qword_14005E0D8 & 0x400000000000LL) != 0
              && (qword_14005E0E0 & 0x400000000000LL) == qword_14005E0E0 )
            {
              OnLinkPrefixLength = Row.OnLinkPrefixLength;
              v28[0] = "IPv6";
              v26 = v21;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                qword_14005E0E0,
                (unsigned int)&word_140058E26,
                v22,
                v23,
                (__int64)v28,
                (__int64)&OnLinkPrefixLength,
                (__int64)&v26);
            }
          }
          else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            WPP_RECORDER_SF_i_IPV6_(WPP_GLOBAL_Control->DeviceExtension, v20, v22, 75);
          }
        }
        else
        {
          Row.Address.Ipv4.sin_addr.S_un.S_addr = *((_DWORD *)a1 + 6 * v9 + 2);
          Row.Address.Ipv4.sin_family = 2;
          v13 = CreateUnicastIpAddressEntry(&Row);
          if ( v13 == -1073741270 )
          {
            v16 = DeleteUnicastIpAddressEntry(&Row);
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v17) = 3;
              WPP_RECORDER_SF_i_IPV4_d(
                WPP_GLOBAL_Control->DeviceExtension,
                v17,
                v18,
                71,
                v24,
                a3->Value,
                (__int64)(&Row.Address.si_family + 2),
                v16);
            }
            v13 = CreateUnicastIpAddressEntry(&Row);
          }
          if ( v13 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v12) = 2;
              WPP_RECORDER_SF_i_IPV4_d(
                WPP_GLOBAL_Control->DeviceExtension,
                v12,
                v14,
                72,
                v24,
                a3->Value,
                (__int64)(&Row.Address.si_family + 2),
                v13);
            }
            if ( (unsigned int)dword_14005E0C8 > 5
              && (qword_14005E0D8 & 0x400000000000LL) != 0
              && (qword_14005E0E0 & 0x400000000000LL) == qword_14005E0E0 )
            {
              v26 = Row.OnLinkPrefixLength;
              v28[0] = "IPv4";
              OnLinkPrefixLength = v13;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                qword_14005E0E0,
                (unsigned int)&dword_140058E6C,
                v14,
                v15,
                (__int64)v28,
                (__int64)&v26,
                (__int64)&OnLinkPrefixLength);
            }
          }
          else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            WPP_RECORDER_SF_i_IPV4_(WPP_GLOBAL_Control->DeviceExtension, v12, v14, 73);
          }
        }
        v5 = v27;
        *((_DWORD *)a1 + 6 * v9) |= 2u;
      }
      ++v8;
      ++v9;
    }
    while ( v8 < a2 );
  }
}

```

## disassembly

```asm
0x1400450ac  mov     [rsp-8+arg_8], rbx
0x1400450b1  push    rbp
0x1400450b2  push    rsi
0x1400450b3  push    rdi
0x1400450b4  push    r12
0x1400450b6  push    r13
0x1400450b8  push    r14
0x1400450ba  push    r15
0x1400450bc  lea     rbp, [rsp-27h]
0x1400450c1  sub     rsp, 0C0h
0x1400450c8  mov     rax, cs:__security_cookie
0x1400450cf  xor     rax, rsp
0x1400450d2  mov     [rbp+57h+var_40], rax
0x1400450d6  mov     r13d, edx
0x1400450d9  mov     ebx, r9d
0x1400450dc  xor     edx, edx; Val
0x1400450de  mov     [rbp+57h+var_A8], ebx
0x1400450e1  mov     r15, r8
0x1400450e4  mov     rsi, rcx
0x1400450e7  lea     rcx, [rbp+57h+Row]; void *
0x1400450eb  lea     r8d, [rdx+50h]; Size
0x1400450ef  call    memset
0x1400450f4  xor     r12d, r12d
0x1400450f7  test    r13d, r13d
0x1400450fa  jz      loc_140045417
0x140045100  xor     r14d, r14d
0x140045103  lea     ecx, [r12+2]
0x140045108  lea     rdi, [r14+r14*2]
0x14004510c  mov     eax, [rsi+rdi*8]
0x14004510f  test    cl, al
0x140045111  jnz     loc_140045408
0x140045117  lea     rcx, [rbp+57h+Row]; Row
0x14004511b  call    cs:__imp_InitializeUnicastIpAddressEntry
0x140045122  nop     dword ptr [rax+rax+00h]
0x140045127  mov     rax, 0FFFFF78000000014h
0x140045131  mov     rax, [rax]
0x140045134  mov     cl, [rsi+rdi*8+4]
0x140045138  mov     qword ptr [rbp+57h+Row.CreationTimeStamp], rax
0x14004513c  mov     rax, [r15]
0x14004513f  mov     qword ptr [rbp+57h+Row.InterfaceLuid], rax
0x140045143  or      eax, 0FFFFFFFFh
0x140045146  mov     [rbp+57h+Row.ValidLifetime], eax
0x140045149  mov     [rbp+57h+Row.PreferredLifetime], eax
0x14004514c  mov     eax, [rsi+rdi*8]
0x14004514f  mov     [rbp+57h+Row.OnLinkPrefixLength], cl
0x140045152  lea     rcx, [rbp+57h+Row]; Row
0x140045156  mov     [rbp+57h+Row.InterfaceIndex], ebx
0x140045159  mov     [rbp+57h+Row.PrefixOrigin], 1
0x140045160  mov     [rbp+57h+Row.SuffixOrigin], 1
0x140045167  mov     [rbp+57h+Row.SkipAsSource], 0
0x14004516b  test    al, 1
0x14004516d  jnz     loc_1400452E9
0x140045173  mov     eax, [rsi+rdi*8+8]
0x140045177  mov     dword ptr [rbp+57h+Row.Address+4], eax
0x14004517a  mov     eax, 2
0x14004517f  mov     word ptr [rbp+57h+Row.Address], ax
0x140045183  call    cs:__imp_CreateUnicastIpAddressEntry
0x14004518a  nop     dword ptr [rax+rax+00h]
0x14004518f  mov     ebx, eax
0x140045191  cmp     eax, 0C000022Ah
0x140045196  jnz     short loc_1400451F7
0x140045198  lea     rcx, [rbp+57h+Row]; Row
0x14004519c  call    cs:__imp_DeleteUnicastIpAddressEntry
0x1400451a3  nop     dword ptr [rax+rax+00h]
0x1400451a8  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400451af  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400451b6  jz      short loc_1400451E5
0x1400451b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400451bf  mov     r9d, 47h ; 'G'
0x1400451c5  mov     [rsp+0F0h+var_B8], eax
0x1400451c9  mov     dl, 3
0x1400451cb  lea     rax, [rbp+57h+Row.Address+4]
0x1400451cf  mov     [rsp+0F0h+var_C0], rax
0x1400451d4  mov     rax, [r15]
0x1400451d7  mov     rcx, [rcx+40h]
0x1400451db  mov     [rsp+0F0h+var_C8], rax
0x1400451e0  call    WPP_RECORDER_SF_i_IPV4_d
0x1400451e5  lea     rcx, [rbp+57h+Row]; Row
0x1400451e9  call    cs:__imp_CreateUnicastIpAddressEntry
0x1400451f0  nop     dword ptr [rax+rax+00h]
0x1400451f5  mov     ebx, eax
0x1400451f7  test    ebx, ebx
0x1400451f9  jz      loc_1400452A9
0x1400451ff  lea     rax, WPP_RECORDER_INITIALIZED
0x140045206  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004520d  jz      short loc_14004523C
0x14004520f  mov     rcx, cs:WPP_GLOBAL_Control
0x140045216  lea     rax, [rbp+57h+Row.Address+4]
0x14004521a  mov     [rsp+0F0h+var_B8], ebx
0x14004521e  mov     r9d, 48h ; 'H'
0x140045224  mov     [rsp+0F0h+var_C0], rax
0x140045229  mov     dl, 2
0x14004522b  mov     rax, [r15]
0x14004522e  mov     rcx, [rcx+40h]
0x140045232  mov     [rsp+0F0h+var_C8], rax
0x140045237  call    WPP_RECORDER_SF_i_IPV4_d
0x14004523c  mov     eax, cs:dword_14005E0C8
0x140045242  cmp     eax, 5
0x140045245  jbe     loc_1400453FD
0x14004524b  mov     rcx, cs:qword_14005E0E0
0x140045252  mov     rdx, 400000000000h
0x14004525c  mov     rax, cs:qword_14005E0D8
0x140045263  test    rdx, rax
0x140045266  jz      loc_1400453FD
0x14004526c  mov     rax, rcx
0x14004526f  and     rax, rdx
0x140045272  cmp     rax, rcx
0x140045275  jnz     loc_1400453FD
0x14004527b  movzx   eax, [rbp+57h+Row.OnLinkPrefixLength]
0x14004527f  lea     rdx, dword_140058E6C
0x140045286  mov     [rbp+57h+var_AC], eax
0x140045289  lea     rax, aIpv4; "IPv4"
0x140045290  mov     [rbp+57h+var_A0], rax
0x140045294  lea     rax, [rbp+57h+var_B0]
0x140045298  mov     [rsp+0F0h+var_C0], rax
0x14004529d  lea     rax, [rbp+57h+var_AC]
0x1400452a1  mov     [rbp+57h+var_B0], ebx
0x1400452a4  jmp     loc_1400453B1
0x1400452a9  lea     rax, WPP_RECORDER_INITIALIZED
0x1400452b0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400452b7  jz      loc_1400453FD
0x1400452bd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400452c4  lea     rax, [rbp+57h+Row.Address+4]
0x1400452c8  mov     [rsp+0F0h+var_C0], rax
0x1400452cd  mov     r9d, 49h ; 'I'
0x1400452d3  mov     rax, [r15]
0x1400452d6  mov     [rsp+0F0h+var_C8], rax
0x1400452db  mov     rcx, [rcx+40h]
0x1400452df  call    WPP_RECORDER_SF_i_IPV4_
0x1400452e4  jmp     loc_1400453FD
0x1400452e9  movups  xmm0, xmmword ptr [rsi+rdi*8+8]
0x1400452ee  mov     eax, 17h
0x1400452f3  mov     word ptr [rbp+57h+Row.Address], ax
0x1400452f7  movdqu  xmmword ptr [rbp+57h+Row.Address+8], xmm0
0x1400452fc  call    cs:__imp_CreateUnicastIpAddressEntry
0x140045303  nop     dword ptr [rax+rax+00h]
0x140045308  mov     ebx, eax
0x14004530a  test    eax, eax
0x14004530c  jz      loc_1400453C6
0x140045312  lea     rax, WPP_RECORDER_INITIALIZED
0x140045319  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140045320  jz      short loc_14004534D
0x140045322  mov     rcx, [r15]
0x140045325  lea     rax, [rbp+57h+Row.Address+8]
0x140045329  mov     [rsp+0F0h+var_B8], ebx
0x14004532d  mov     r9d, 4Ah ; 'J'
0x140045333  mov     [rsp+0F0h+var_C0], rax
0x140045338  mov     [rsp+0F0h+var_C8], rcx
0x14004533d  mov     rcx, cs:WPP_GLOBAL_Control
0x140045344  mov     rcx, [rcx+40h]
0x140045348  call    WPP_RECORDER_SF_i_IPV6_d
0x14004534d  mov     eax, cs:dword_14005E0C8
0x140045353  cmp     eax, 5
0x140045356  jbe     loc_1400453FD
0x14004535c  mov     rcx, cs:qword_14005E0E0
0x140045363  mov     rdx, 400000000000h
0x14004536d  mov     rax, cs:qword_14005E0D8
0x140045374  test    rdx, rax
0x140045377  jz      loc_1400453FD
0x14004537d  mov     rax, rcx
0x140045380  and     rax, rdx
0x140045383  cmp     rax, rcx
0x140045386  jnz     short loc_1400453FD
0x140045388  movzx   eax, [rbp+57h+Row.OnLinkPrefixLength]
0x14004538c  lea     rdx, word_140058E26
0x140045393  mov     [rbp+57h+var_B0], eax
0x140045396  lea     rax, aIpv6; "IPv6"
0x14004539d  mov     [rbp+57h+var_A0], rax
0x1400453a1  lea     rax, [rbp+57h+var_AC]
0x1400453a5  mov     [rsp+0F0h+var_C0], rax
0x1400453aa  lea     rax, [rbp+57h+var_B0]
0x1400453ae  mov     [rbp+57h+var_AC], ebx
0x1400453b1  mov     [rsp+0F0h+var_C8], rax
0x1400453b6  lea     rax, [rbp+57h+var_A0]
0x1400453ba  mov     [rsp+0F0h+var_D0], rax
0x1400453bf  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1400453c4  jmp     short loc_1400453FD
0x1400453c6  lea     rax, WPP_RECORDER_INITIALIZED
0x1400453cd  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400453d4  jz      short loc_1400453FD
0x1400453d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400453dd  lea     rax, [rbp+57h+Row.Address+8]
0x1400453e1  mov     [rsp+0F0h+var_C0], rax
0x1400453e6  mov     r9d, 4Bh ; 'K'
0x1400453ec  mov     rax, [r15]
0x1400453ef  mov     [rsp+0F0h+var_C8], rax
0x1400453f4  mov     rcx, [rcx+40h]
0x1400453f8  call    WPP_RECORDER_SF_i_IPV6_
0x1400453fd  mov     ebx, [rbp+57h+var_A8]
0x140045400  mov     ecx, 2
0x140045405  or      [rsi+rdi*8], ecx
0x140045408  inc     r12d
0x14004540b  inc     r14
0x14004540e  cmp     r12d, r13d
0x140045411  jb      loc_140045108
0x140045417  mov     rcx, [rbp+57h+var_40]
0x14004541b  xor     rcx, rsp; StackCookie
0x14004541e  call    __security_check_cookie
0x140045423  mov     rbx, [rsp+0F0h+arg_8]
0x14004542b  add     rsp, 0C0h
0x140045432  pop     r15
0x140045434  pop     r14
0x140045436  pop     r13
0x140045438  pop     r12
0x14004543a  pop     rdi
0x14004543b  pop     rsi
0x14004543c  pop     rbp
0x14004543d  retn
```
