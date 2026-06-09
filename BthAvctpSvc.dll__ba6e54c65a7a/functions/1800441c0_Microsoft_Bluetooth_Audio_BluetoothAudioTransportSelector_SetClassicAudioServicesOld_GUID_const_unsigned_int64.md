# Microsoft::Bluetooth::Audio::BluetoothAudioTransportSelector::SetClassicAudioServicesOld(_GUID const &,unsigned __int64,std::vector<_GUID,std::allocator<_GUID>> const &,bool,wil::write_lock_required)

- ea: `0x1800441c0`
- end: `0x180044435`
- name: `?SetClassicAudioServicesOld@BluetoothAudioTransportSelector@Audio@Bluetooth@Microsoft@@AEAAXAEBU_GUID@@_KAEBV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@_NUwrite_lock_required@wil@@@Z`
- size: `629`
- prototype: `__int64 __usercall@<rax>(char@<cl>, __int64@<rdx>, char@<r8b>, char)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180043d98`

## callees

- `0x180001dd0`
- `0x1800029cc`
- `0x1800123b8`
- `0x1800441c0`
- `0x1800458a8`
- `0x180045de0`

## import_xrefs

- `BluetoothApis!BluetoothGetDeviceInfo` at `0x18004429f`
- `BluetoothApis!BluetoothGetDeviceInfo` at `0x18004429f`
- `ext-ms-win-bluetooth-apis-private-l1-1-0!BthpSetServiceStateEx` at `0x18004435e`
- `ext-ms-win-bluetooth-apis-private-l1-1-0!BthpSetServiceStateEx` at `0x18004435e`

## pseudocode

```c
int __fastcall Microsoft::Bluetooth::Audio::BluetoothAudioTransportSelector::SetClassicAudioServicesOld(
        char a1,
        __int64 a2,
        BTH_ADDR a3,
        __int64 a4,
        unsigned __int8 a5)
{
  _UNKNOWN **v7; // r8
  __int64 v8; // rax
  char v10; // bl
  _UNKNOWN **v11; // rax
  int v12; // edx
  int v13; // r8d
  bool v14; // sf
  _OWORD *v15; // rsi
  _OWORD *i; // rdi
  char v17; // r8
  signed int v18; // ecx
  bool v19; // dl
  const wchar_t *v20; // rax
  char v22[4]; // [rsp+20h] [rbp-2D8h]
  int v23; // [rsp+28h] [rbp-2D0h]
  int v24; // [rsp+30h] [rbp-2C8h]
  int MessageGuid; // [rsp+38h] [rbp-2C0h]
  __int64 v26[2]; // [rsp+70h] [rbp-288h] BYREF
  BLUETOOTH_DEVICE_INFO_STRUCT pbtdi; // [rsp+80h] [rbp-278h] BYREF

  v7 = &WPP_RECORDER_INITIALIZED;
  v8 = a2;
  v10 = 1;
  if ( a5 )
  {
    LOBYTE(a2) = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
    if ( (_BYTE)a2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF__guid_q(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (int)v7,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        4,
        1,
        52,
        &WPP_b836096fa1863519a0c995e3dad38024_Traceguids,
        v8,
        a1);
    }
  }
  memset_0(&pbtdi, 0, sizeof(pbtdi));
  pbtdi.dwSize = 560;
  pbtdi.Address.ullLong = a3;
  LODWORD(v11) = BluetoothGetDeviceInfo(0, &pbtdi);
  v14 = (int)v11 < 0;
  if ( (int)v11 > 0 )
  {
    LODWORD(v11) = (unsigned __int16)v11 | 0x80070000;
    v14 = (int)v11 < 0;
  }
  if ( v14 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      v10 = 0;
    }
    v11 = &WPP_RECORDER_INITIALIZED;
    if ( v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = v10;
      LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      LODWORD(v11) = WPP_RECORDER_AND_TRACE_SF_iq(
                       *((_QWORD *)WPP_GLOBAL_Control + 2),
                       v12,
                       v13,
                       *((_QWORD *)WPP_GLOBAL_Control + 5),
                       *(_DWORD *)v22,
                       v23,
                       v24,
                       MessageGuid,
                       a3,
                       a1);
    }
  }
  else
  {
    v15 = *(_OWORD **)(a4 + 8);
    for ( i = *(_OWORD **)a4; i != v15; ++i )
    {
      LOBYTE(MessageGuid) = 0;
      LOBYTE(v24) = 0;
      *(_OWORD *)v26 = *i;
      LODWORD(v11) = BthpSetServiceStateEx(0, &pbtdi, 0, v26);
      v17 = (char)v11;
      if ( (int)v11 > 0 )
        v18 = (unsigned __int16)v11 | 0x80070000;
      else
        v18 = (int)v11;
      if ( v18 < 0 )
      {
        v19 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u;
        v11 = &WPP_RECORDER_INITIALIZED;
        if ( v19 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v20 = L"start";
          if ( !a5 )
            v20 = (const wchar_t *)L"stop";
          LODWORD(v11) = WPP_RECORDER_AND_TRACE_SF_S_guid_iDq(
                           *((_QWORD *)WPP_GLOBAL_Control + 2),
                           a5,
                           0,
                           v24,
                           MessageGuid,
                           (__int64)v20,
                           (__int64)v26,
                           a3,
                           v17,
                           a1);
        }
      }
    }
  }
  return (int)v11;
}

```

## disassembly

```asm
0x1800441c0  push    rbx
0x1800441c2  push    rbp
0x1800441c3  push    rsi
0x1800441c4  push    rdi
0x1800441c5  push    r12
0x1800441c7  push    r15
0x1800441c9  sub     rsp, 2C8h
0x1800441d0  mov     rax, cs:__security_cookie
0x1800441d7  xor     rax, rsp
0x1800441da  mov     [rsp+2F8h+var_48], rax
0x1800441e2  cmp     [rsp+2F8h+arg_20], 0
0x1800441ea  lea     rbp, WPP_GLOBAL_Control
0x1800441f1  mov     r15, r8
0x1800441f4  mov     rdi, r9
0x1800441f7  lea     r8, WPP_RECORDER_INITIALIZED
0x1800441fe  mov     rax, rdx
0x180044201  mov     r12, rcx
0x180044204  mov     ebx, 1
0x180044209  jz      short loc_18004426F
0x18004420b  mov     rcx, cs:WPP_GLOBAL_Control
0x180044212  cmp     rcx, rbp
0x180044215  jz      short loc_180044226
0x180044217  test    [rcx+1Ch], bl
0x18004421a  jz      short loc_180044226
0x18004421c  cmp     byte ptr [rcx+19h], 4
0x180044220  jb      short loc_180044226
0x180044222  mov     dl, bl
0x180044224  jmp     short loc_180044228
0x180044226  xor     dl, dl; int
0x180044228  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x18004422f  setnz   r8b; int
0x180044233  test    dl, dl
0x180044235  jnz     short loc_18004423C
0x180044237  test    r8b, r8b
0x18004423a  jz      short loc_18004426F
0x18004423c  mov     r9, [rcx+28h]; int
0x180044240  mov     rcx, [rcx+10h]; int
0x180044244  mov     qword ptr [rsp+2F8h+var_2B0], r12; char
0x180044249  mov     [rsp+2F8h+var_2B8], rax; __int64
0x18004424e  lea     rax, WPP_b836096fa1863519a0c995e3dad38024_Traceguids
0x180044255  mov     [rsp+2F8h+MessageGuid], rax; MessageGuid
0x18004425a  mov     [rsp+2F8h+var_2C8], 34h ; '4'; __int16
0x180044261  mov     [rsp+2F8h+var_2D0], ebx; int
0x180044265  mov     [rsp+2F8h+var_2D8], 4; char
0x18004426a  call    WPP_RECORDER_AND_TRACE_SF__guid_q
0x18004426f  mov     esi, 230h
0x180044274  lea     rcx, [rsp+2F8h+pbtdi]; void *
0x18004427c  mov     r8d, esi; Size
0x18004427f  xor     edx, edx; Val
0x180044281  call    memset_0
0x180044286  lea     rdx, [rsp+2F8h+pbtdi]; pbtdi
0x18004428e  mov     [rsp+2F8h+pbtdi.dwSize], esi
0x180044295  xor     ecx, ecx; hRadio
0x180044297  mov     qword ptr [rsp+2F8h+pbtdi.Address], r15
0x18004429f  call    cs:__imp_BluetoothGetDeviceInfo
0x1800442a5  test    eax, eax
0x1800442a7  jle     short loc_1800442B3
0x1800442a9  movzx   eax, ax
0x1800442ac  or      eax, 80070000h
0x1800442b1  test    eax, eax
0x1800442b3  jns     short loc_18004430B
0x1800442b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800442bc  cmp     rcx, rbp
0x1800442bf  jz      short loc_1800442CC
0x1800442c1  test    [rcx+1Ch], bl
0x1800442c4  jz      short loc_1800442CC
0x1800442c6  cmp     byte ptr [rcx+19h], 2
0x1800442ca  jnb     short loc_1800442CE
0x1800442cc  xor     bl, bl
0x1800442ce  lea     rax, WPP_RECORDER_INITIALIZED
0x1800442d5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800442dc  setnz   r8b
0x1800442e0  test    bl, bl
0x1800442e2  jnz     short loc_1800442ED
0x1800442e4  test    r8b, r8b
0x1800442e7  jz      loc_180044415
0x1800442ed  mov     r9, [rcx+28h]
0x1800442f1  mov     dl, bl
0x1800442f3  mov     rcx, [rcx+10h]
0x1800442f7  mov     qword ptr [rsp+2F8h+var_2B0], r12
0x1800442fc  mov     [rsp+2F8h+var_2B8], r15
0x180044301  call    WPP_RECORDER_AND_TRACE_SF_iq
0x180044306  jmp     loc_180044415
0x18004430b  mov     rsi, [rdi+8]
0x18004430f  mov     rdi, [rdi]
0x180044312  cmp     rdi, rsi
0x180044315  jz      loc_180044415
0x18004431b  movzx   ebp, [rsp+2F8h+arg_20]
0x180044323  movups  xmm0, xmmword ptr [rdi]
0x180044326  mov     [rsp+2F8h+var_2B0], bl
0x18004432a  lea     r9, [rsp+2F8h+var_288]
0x18004432f  mov     byte ptr [rsp+2F8h+var_2B8], 0
0x180044334  lea     rdx, [rsp+2F8h+pbtdi]
0x18004433c  mov     byte ptr [rsp+2F8h+MessageGuid], 0; int
0x180044341  xor     r8d, r8d
0x180044344  mov     byte ptr [rsp+2F8h+var_2C8], 0; int
0x180044349  xor     ecx, ecx
0x18004434b  mov     qword ptr [rsp+2F8h+var_2D0], 0; int
0x180044354  mov     dword ptr [rsp+2F8h+var_2D8], ebp; int
0x180044358  movdqu  xmmword ptr [rsp+2F8h+var_288], xmm0
0x18004435e  call    cs:__imp_BthpSetServiceStateEx
0x180044364  mov     r8d, eax
0x180044367  test    eax, eax
0x180044369  jg      short loc_18004436F
0x18004436b  mov     ecx, eax
0x18004436d  jmp     short loc_180044379
0x18004436f  movzx   ecx, r8w
0x180044373  or      ecx, 80070000h
0x180044379  test    ecx, ecx
0x18004437b  jns     loc_180044408
0x180044381  mov     rcx, cs:WPP_GLOBAL_Control
0x180044388  lea     rax, WPP_GLOBAL_Control
0x18004438f  cmp     rcx, rax
0x180044392  jz      short loc_1800443A3
0x180044394  test    [rcx+1Ch], bl
0x180044397  jz      short loc_1800443A3
0x180044399  cmp     byte ptr [rcx+19h], 2
0x18004439d  jb      short loc_1800443A3
0x18004439f  mov     dl, bl
0x1800443a1  jmp     short loc_1800443A5
0x1800443a3  xor     dl, dl
0x1800443a5  lea     rax, WPP_RECORDER_INITIALIZED
0x1800443ac  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800443b3  setnz   r10b
0x1800443b7  test    dl, dl
0x1800443b9  jnz     short loc_1800443C0
0x1800443bb  test    r10b, r10b
0x1800443be  jz      short loc_180044408
0x1800443c0  cmp     [rsp+2F8h+arg_20], 0
0x1800443c8  lea     r9, aStop; "stop"
0x1800443cf  mov     qword ptr [rsp+2F8h+var_298], r12; char
0x1800443d4  lea     rax, aStart; "start"
0x1800443db  mov     dword ptr [rsp+2F8h+var_2A0], r8d; char
0x1800443e0  cmovz   rax, r9
0x1800443e4  mov     r9, [rcx+28h]
0x1800443e8  lea     r8, [rsp+2F8h+var_288]
0x1800443ed  mov     rcx, [rcx+10h]; LoggerHandle
0x1800443f1  mov     qword ptr [rsp+2F8h+var_2A8], r15; char
0x1800443f6  mov     qword ptr [rsp+2F8h+var_2B0], r8; __int64
0x1800443fb  mov     r8b, r10b
0x1800443fe  mov     [rsp+2F8h+var_2B8], rax; __int64
0x180044403  call    WPP_RECORDER_AND_TRACE_SF_S_guid_iDq
0x180044408  add     rdi, 10h
0x18004440c  cmp     rdi, rsi
0x18004440f  jnz     loc_180044323
0x180044415  mov     rcx, [rsp+2F8h+var_48]
0x18004441d  xor     rcx, rsp; StackCookie
0x180044420  call    __security_check_cookie
0x180044425  add     rsp, 2C8h
0x18004442c  pop     r15
0x18004442e  pop     r12
0x180044430  pop     rdi
0x180044431  pop     rsi
0x180044432  pop     rbp
0x180044433  pop     rbx
0x180044434  retn
```
