# MbbIpReportRoutes(_MBB_IPADDRESS_ENTRY *,ulong,_NET_LUID_LH *,ulong)

- ea: `0x140045448`
- end: `0x140045681`
- name: `?MbbIpReportRoutes@@YAXPEAU_MBB_IPADDRESS_ENTRY@@KPEAT_NET_LUID_LH@@K@Z`
- size: `569`
- prototype: `void __fastcall(struct _MBB_IPADDRESS_ENTRY *, unsigned int, union _NET_LUID_LH *, NET_IFINDEX)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x140042e30`

## callees

- `0x140045448`
- `0x140046378`
- `0x140046458`
- `0x1400466a4`
- `0x140046784`
- `0x140047e50`
- `0x140048340`

## import_xrefs

- `NETIO!CreateIpForwardEntry2` at `0x140045503`
- `NETIO!CreateIpForwardEntry2` at `0x1400455be`
- `NETIO!CreateIpForwardEntry2` at `0x140045503`
- `NETIO!CreateIpForwardEntry2` at `0x1400455be`
- `NETIO!InitializeIpForwardEntry` at `0x1400454b1`
- `NETIO!InitializeIpForwardEntry` at `0x1400454b1`

## pseudocode

```c
void __fastcall MbbIpReportRoutes(
        struct _MBB_IPADDRESS_ENTRY *a1,
        unsigned int a2,
        union _NET_LUID_LH *a3,
        NET_IFINDEX a4)
{
  unsigned int v8; // r15d
  __int64 v9; // rsi
  int v10; // eax
  ULONG v11; // eax
  NTSTATUS v12; // eax
  int v13; // edx
  int v14; // r8d
  __int128 v15; // xmm1
  NTSTATUS v16; // eax
  int v17; // edx
  int v18; // r8d
  int v19; // [rsp+20h] [rbp-79h]
  _MIB_IPFORWARD_ROW2 Row; // [rsp+40h] [rbp-59h] BYREF

  memset(&Row, 0, sizeof(Row));
  v8 = 0;
  if ( a2 )
  {
    v9 = 0;
    do
    {
      if ( (*((_DWORD *)a1 + 6 * v9) & 2) == 0 )
      {
        InitializeIpForwardEntry(&Row);
        Row.InterfaceLuid = (NET_LUID)a3->Value;
        Row.ValidLifetime = -1;
        Row.PreferredLifetime = -1;
        v10 = *((_DWORD *)a1 + 6 * v9);
        Row.InterfaceIndex = a4;
        Row.Origin = NlroManual;
        Row.DestinationPrefix.PrefixLength = 0;
        if ( (v10 & 1) != 0 )
        {
          v15 = *(_OWORD *)((char *)a1 + 24 * v9 + 8);
          *(_DWORD *)&Row.DestinationPrefix.Prefix.Ipv4.sin_family = 23;
          Row.NextHop.Ipv4.sin_family = 23;
          *(_OWORD *)(&Row.NextHop.si_family + 4) = v15;
          *(_OWORD *)(&Row.DestinationPrefix.Prefix.si_family + 4) = 0;
          v16 = CreateIpForwardEntry2(&Row);
          if ( v16 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              WPP_RECORDER_SF_i_IPV6_d(
                WPP_GLOBAL_Control->DeviceExtension,
                v17,
                v18,
                87,
                v19,
                a3->Value,
                (__int64)(&Row.NextHop.si_family + 4),
                v16);
          }
          else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            WPP_RECORDER_SF_i_IPV6_(WPP_GLOBAL_Control->DeviceExtension, v17, v18, 88);
          }
        }
        else
        {
          v11 = *((_DWORD *)a1 + 6 * v9 + 2);
          Row.NextHop.Ipv4.sin_family = 2;
          *(_QWORD *)&Row.DestinationPrefix.Prefix.Ipv4.sin_family = 2;
          Row.NextHop.Ipv4.sin_addr.S_un.S_addr = v11;
          v12 = CreateIpForwardEntry2(&Row);
          if ( v12 )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LOBYTE(v13) = 2;
              WPP_RECORDER_SF_i_IPV4_d(
                WPP_GLOBAL_Control->DeviceExtension,
                v13,
                v14,
                85,
                v19,
                a3->Value,
                (__int64)(&Row.NextHop.si_family + 2),
                v12);
            }
          }
          else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            WPP_RECORDER_SF_i_IPV4_(WPP_GLOBAL_Control->DeviceExtension, v13, v14, 86);
          }
        }
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
0x140045448  mov     [rsp-8+arg_8], rbx
0x14004544d  push    rbp
0x14004544e  push    rsi
0x14004544f  push    rdi
0x140045450  push    r12
0x140045452  push    r13
0x140045454  push    r14
0x140045456  push    r15
0x140045458  lea     rbp, [rsp-27h]
0x14004545d  sub     rsp, 0C0h
0x140045464  mov     rax, cs:__security_cookie
0x14004546b  xor     rax, rsp
0x14004546e  mov     [rbp+57h+var_40], rax
0x140045472  mov     r12d, edx
0x140045475  mov     r14, r8
0x140045478  xor     edx, edx; Val
0x14004547a  mov     rdi, rcx
0x14004547d  lea     rcx, [rbp+57h+Row]; void *
0x140045481  mov     r13d, r9d
0x140045484  lea     r8d, [rdx+68h]; Size
0x140045488  call    memset
0x14004548d  xor     r15d, r15d
0x140045490  test    r12d, r12d
0x140045493  jz      loc_140045659
0x140045499  xor     esi, esi
0x14004549b  lea     ecx, [rsi+2]
0x14004549e  lea     rbx, [rsi+rsi*2]
0x1400454a2  mov     eax, [rdi+rbx*8]
0x1400454a5  test    cl, al
0x1400454a7  jnz     loc_14004564A
0x1400454ad  lea     rcx, [rbp+57h+Row]; Row
0x1400454b1  call    cs:__imp_InitializeIpForwardEntry
0x1400454b8  nop     dword ptr [rax+rax+00h]
0x1400454bd  mov     rax, [r14]
0x1400454c0  mov     qword ptr [rbp+57h+Row.InterfaceLuid], rax
0x1400454c4  or      eax, 0FFFFFFFFh
0x1400454c7  mov     [rbp+57h+Row.ValidLifetime], eax
0x1400454ca  mov     [rbp+57h+Row.PreferredLifetime], eax
0x1400454cd  mov     eax, [rdi+rbx*8]
0x1400454d0  mov     [rbp+57h+Row.InterfaceIndex], r13d
0x1400454d4  mov     [rbp+57h+Row.Origin], 0
0x1400454db  mov     [rbp+57h+Row.DestinationPrefix.PrefixLength], 0
0x1400454df  test    al, 1
0x1400454e1  jnz     loc_140045599
0x1400454e7  mov     eax, [rdi+rbx*8+8]
0x1400454eb  mov     ecx, 2
0x1400454f0  mov     word ptr [rbp+57h+Row.NextHop], cx
0x1400454f4  lea     rcx, [rbp+57h+Row]; Row
0x1400454f8  mov     qword ptr [rbp+57h+Row.DestinationPrefix.Prefix], 2
0x140045500  mov     dword ptr [rbp+57h+Row.NextHop+4], eax
0x140045503  call    cs:__imp_CreateIpForwardEntry2
0x14004550a  nop     dword ptr [rax+rax+00h]
0x14004550f  test    eax, eax
0x140045511  jz      short loc_140045559
0x140045513  lea     rcx, WPP_RECORDER_INITIALIZED
0x14004551a  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140045521  jz      loc_140045642
0x140045527  mov     rcx, cs:WPP_GLOBAL_Control
0x14004552e  mov     r9d, 55h ; 'U'
0x140045534  mov     [rsp+0F0h+var_B8], eax
0x140045538  mov     dl, 2
0x14004553a  lea     rax, [rbp+57h+Row.NextHop+4]
0x14004553e  mov     [rsp+0F0h+var_C0], rax
0x140045543  mov     rax, [r14]
0x140045546  mov     rcx, [rcx+40h]
0x14004554a  mov     [rsp+0F0h+var_C8], rax
0x14004554f  call    WPP_RECORDER_SF_i_IPV4_d
0x140045554  jmp     loc_140045642
0x140045559  lea     rax, WPP_RECORDER_INITIALIZED
0x140045560  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140045567  jz      loc_140045642
0x14004556d  mov     rcx, cs:WPP_GLOBAL_Control
0x140045574  lea     rax, [rbp+57h+Row.NextHop+4]
0x140045578  mov     [rsp+0F0h+var_C0], rax
0x14004557d  mov     r9d, 56h ; 'V'
0x140045583  mov     rax, [r14]
0x140045586  mov     [rsp+0F0h+var_C8], rax
0x14004558b  mov     rcx, [rcx+40h]
0x14004558f  call    WPP_RECORDER_SF_i_IPV4_
0x140045594  jmp     loc_140045642
0x140045599  movups  xmm1, xmmword ptr [rdi+rbx*8+8]
0x14004559e  mov     eax, 17h
0x1400455a3  mov     dword ptr [rbp+57h+Row.DestinationPrefix.Prefix], 17h
0x1400455aa  xorps   xmm0, xmm0
0x1400455ad  mov     word ptr [rbp+57h+Row.NextHop], ax
0x1400455b1  lea     rcx, [rbp+57h+Row]; Row
0x1400455b5  movdqu  xmmword ptr [rbp+57h+Row.NextHop+8], xmm1
0x1400455ba  movups  xmmword ptr [rbp+57h+Row.DestinationPrefix.Prefix+8], xmm0
0x1400455be  call    cs:__imp_CreateIpForwardEntry2
0x1400455c5  nop     dword ptr [rax+rax+00h]
0x1400455ca  test    eax, eax
0x1400455cc  jz      short loc_14004560B
0x1400455ce  lea     rcx, WPP_RECORDER_INITIALIZED
0x1400455d5  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x1400455dc  jz      short loc_140045642
0x1400455de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400455e5  mov     r9d, 57h ; 'W'
0x1400455eb  mov     [rsp+0F0h+var_B8], eax
0x1400455ef  lea     rax, [rbp+57h+Row.NextHop+8]
0x1400455f3  mov     [rsp+0F0h+var_C0], rax
0x1400455f8  mov     rax, [r14]
0x1400455fb  mov     rcx, [rcx+40h]
0x1400455ff  mov     [rsp+0F0h+var_C8], rax
0x140045604  call    WPP_RECORDER_SF_i_IPV6_d
0x140045609  jmp     short loc_140045642
0x14004560b  lea     rax, WPP_RECORDER_INITIALIZED
0x140045612  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140045619  jz      short loc_140045642
0x14004561b  mov     rcx, cs:WPP_GLOBAL_Control
0x140045622  lea     rax, [rbp+57h+Row.NextHop+8]
0x140045626  mov     [rsp+0F0h+var_C0], rax
0x14004562b  mov     r9d, 58h ; 'X'
0x140045631  mov     rax, [r14]
0x140045634  mov     [rsp+0F0h+var_C8], rax
0x140045639  mov     rcx, [rcx+40h]
0x14004563d  call    WPP_RECORDER_SF_i_IPV6_
0x140045642  mov     ecx, 2
0x140045647  or      [rdi+rbx*8], ecx
0x14004564a  inc     r15d
0x14004564d  inc     rsi
0x140045650  cmp     r15d, r12d
0x140045653  jb      loc_14004549E
0x140045659  mov     rcx, [rbp+57h+var_40]
0x14004565d  xor     rcx, rsp; StackCookie
0x140045660  call    __security_check_cookie
0x140045665  mov     rbx, [rsp+0F0h+arg_8]
0x14004566d  add     rsp, 0C0h
0x140045674  pop     r15
0x140045676  pop     r14
0x140045678  pop     r13
0x14004567a  pop     r12
0x14004567c  pop     rdi
0x14004567d  pop     rsi
0x14004567e  pop     rbp
0x14004567f  retn
```
