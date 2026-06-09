# VidExoIoControlPartition

- ea: `0x140038040`
- end: `0x140038456`
- name: `VidExoIoControlPartition`
- size: `1046`
- prototype: `__int64 __fastcall(int, int, int, int, int, NTSTRSAFE_PWSTR, int, int, ULONGLONG)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140033bc0`

## callees

- `0x140012bc0`
- `0x140035708`
- `0x140038040`
- `0x140078c58`
- `0x14008503c`
- `0x1400852bc`
- `0x1400856d4`
- `0x1400d5414`
- `0x1400d5638`
- `0x1400d5a74`
- `0x1400d5ce0`
- `0x1400d5f2c`

## import_xrefs

- `winhvr!WinHvSetVpState` at `0x1400382aa`
- `winhvr!WinHvSetVpState` at `0x1400382aa`
- `winhvr!WinHvGetVpState` at `0x14003831b`
- `winhvr!WinHvGetVpState` at `0x14003831b`
- `winhvr!WinHvInstallIntercept` at `0x1400381e1`
- `winhvr!WinHvInstallIntercept` at `0x1400381e1`
- `winhvr!WinHvRegisterInterceptResult` at `0x140038356`
- `winhvr!WinHvRegisterInterceptResult` at `0x140038356`

## pseudocode

```c
__int64 __fastcall VidExoIoControlPartition(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        unsigned int *a4,
        unsigned int a5,
        NTSTRSAFE_PWSTR pszDest,
        unsigned int a7,
        unsigned int a8,
        unsigned int *pullResult)
{
  __int64 result; // rax

  *pullResult = 0;
  if ( a8 <= 0x22131C )
  {
    if ( a8 == 2233116 )
    {
      if ( a5 >= 0x20 )
        return VsmmExoGpaRangeIoctlAccessTrackingControl(
                 (_DWORD)a1,
                 *(_QWORD *)a4,
                 *((_QWORD *)a4 + 1),
                 *((_QWORD *)a4 + 2),
                 a4[6]);
    }
    else
    {
      if ( a8 <= 0x221274 )
      {
        if ( a8 == 2232948 || a8 == 2232388 || a8 == 2232564 || a8 == 2232568 || a8 == 2232644 || a8 == 2232784 )
          return VidIoControlPartition(a1, a2, a3, a4, a5, pszDest, a7, a8, pullResult);
        goto LABEL_57;
      }
      if ( a8 == 2232964 || a8 == 2233084 )
        return VidIoControlPartition(a1, a2, a3, a4, a5, pszDest, a7, a8, pullResult);
      if ( a8 != 2233108 )
      {
        if ( a8 == 2233112 )
        {
          if ( a5 >= 0x10 )
            return VsmmExoGpaRangeIoctlUnmap(a1, *(_QWORD *)a4, *((_QWORD *)a4 + 1));
          return 3221225507LL;
        }
LABEL_57:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 10, &WPP_a76ff6e5b5ee3bbc086e8bc9b11ca330_Traceguids);
        }
        return 3221225474LL;
      }
      if ( a5 >= 0x28 )
        return VsmmExoGpaRangeIoctlMap(
                 (int)a1,
                 *(_QWORD *)a4,
                 *((_QWORD *)a4 + 1),
                 *((_QWORD *)a4 + 2),
                 *((HANDLE *)a4 + 3),
                 a4[8],
                 a4[9]);
    }
    return 3221225507LL;
  }
  if ( a8 > 0x22133C )
  {
    switch ( a8 )
    {
      case 0x221340u:
        if ( (a5 & 0xF) == 0 )
          return VsmmExoGpaRangeIoctlPin(a1, a4, a5 >> 4);
        break;
      case 0x221344u:
        if ( (a5 & 0xF) == 0 )
          return VsmmExoGpaRangeIoctlUnpin(a1, a4, a5 >> 4);
        break;
      case 0x221348u:
        if ( a5 >= 0x10 )
          return VidExoBrokerIoctlSend(a1, a2, a4);
        break;
      case 0x22134Cu:
        if ( a7 >= 0x10 )
          return VidExoBrokerIoctlReceive((__int64)a1, a3, (unsigned int *)pszDest, a7, pullResult);
        break;
      default:
        goto LABEL_57;
    }
    return 3221225485LL;
  }
  switch ( a8 )
  {
    case 0x22133Cu:
      if ( a5 >= 0x38 )
        return WinHvRegisterInterceptResult(a1[81], *a4, a4[1], a4 + 2);
      return 3221225507LL;
    case 0x221324u:
      if ( a5 < 0x20 || !a7 )
        return 3221225507LL;
      if ( a7 <= 0x1FB000 && ((a4[2] & 0x80000000) != 0 || a7 <= 0x1000) )
      {
        LOBYTE(a3) = *((_BYTE *)a4 + 4);
        result = WinHvGetVpState(a1[81], *a4, a3);
        if ( (int)result >= 0 )
          *pullResult = a7;
        return result;
      }
      return 2147483653LL;
    case 0x221328u:
      if ( a5 <= 0x20 )
        return 3221225507LL;
      if ( a5 - 32 <= 0x1FB000 && ((a4[2] & 0x80000000) != 0 || a5 - 32 <= 0xFD8) )
      {
        LOBYTE(a3) = *((_BYTE *)a4 + 4);
        return WinHvSetVpState(a1[81], *a4, a3);
      }
      return 2147483653LL;
    case 0x22132Cu:
      if ( a5 >= 0x20 )
        return VidExoVpIoctlCreate(a1, *a4, *((_BYTE *)a4 + 4), a4 + 2, *((HANDLE *)a4 + 3));
      return 3221225485LL;
  }
  if ( a8 != 2233140 )
  {
    if ( a8 != 2233144 )
      goto LABEL_57;
    if ( a5 >= 0x18 )
      return WinHvInstallIntercept(a1[81], *a4, a4 + 2);
    return 3221225507LL;
  }
  if ( a5 < 4 )
    return 3221225485LL;
  if ( a7 < 0x20 )
    return 3221225507LL;
  result = VidExoVpIoctlMap(a1, a3, *a4, pszDest);
  if ( (int)result >= 0 )
    *pullResult = 32;
  return result;
}

```

## disassembly

```asm
0x140038040  mov     [rsp+arg_0], rbx
0x140038045  push    rdi
0x140038046  sub     rsp, 50h
0x14003804a  mov     rdi, [rsp+58h+arg_40]
0x140038052  mov     r10, r9
0x140038055  mov     r9d, [rsp+58h+arg_38]
0x14003805d  mov     eax, 22131Ch
0x140038062  mov     r11, r8
0x140038065  mov     dword ptr [rdi], 0
0x14003806b  cmp     r9d, eax
0x14003806e  ja      loc_140038187
0x140038074  jz      loc_140038160
0x14003807a  mov     eax, 221274h
0x14003807f  cmp     r9d, eax
0x140038082  ja      short loc_1400380E6
0x140038084  jz      short loc_1400380AC
0x140038086  mov     eax, r9d
0x140038089  sub     eax, 221044h
0x14003808e  jz      short loc_1400380AC
0x140038090  sub     eax, 0B0h
0x140038095  jz      short loc_1400380AC
0x140038097  sub     eax, 4
0x14003809a  jz      short loc_1400380AC
0x14003809c  sub     eax, 4Ch ; 'L'
0x14003809f  jz      short loc_1400380AC
0x1400380a1  cmp     eax, 8Ch
0x1400380a6  jnz     loc_140038388
0x1400380ac  mov     eax, [rsp+58h+arg_30]
0x1400380b3  mov     [rsp+58h+pullResult], rdi; pullResult
0x1400380b8  mov     [rsp+58h+var_20], r9d; int
0x1400380bd  mov     r9, r10
0x1400380c0  mov     [rsp+58h+var_28], eax; int
0x1400380c4  mov     rax, [rsp+58h+arg_28]
0x1400380cc  mov     [rsp+58h+pszDest], rax; pszDest
0x1400380d1  mov     eax, [rsp+58h+arg_20]
0x1400380d8  mov     dword ptr [rsp+58h+Handle], eax; int
0x1400380dc  call    VidIoControlPartition
0x1400380e1  jmp     loc_14003844A
0x1400380e6  mov     eax, r9d
0x1400380e9  sub     eax, 221284h
0x1400380ee  jz      short loc_1400380AC
0x1400380f0  sub     eax, 78h ; 'x'
0x1400380f3  jz      short loc_1400380AC
0x1400380f5  sub     eax, 18h
0x1400380f8  jz      short loc_14003811E
0x1400380fa  cmp     eax, 4
0x1400380fd  jnz     loc_140038388
0x140038103  cmp     [rsp+58h+arg_20], 10h
0x14003810b  jb      short loc_140038128
0x14003810d  mov     r8, [r10+8]
0x140038111  mov     rdx, [r10]
0x140038114  call    VsmmExoGpaRangeIoctlUnmap
0x140038119  jmp     loc_14003844A
0x14003811e  cmp     [rsp+58h+arg_20], 28h ; '('
0x140038126  jnb     short loc_140038132
0x140038128  mov     eax, 0C0000023h
0x14003812d  jmp     loc_14003844A
0x140038132  mov     eax, [r10+24h]
0x140038136  mov     r9, [r10+10h]; int
0x14003813a  mov     r8, [r10+8]; int
0x14003813e  mov     rdx, [r10]; int
0x140038141  mov     [rsp+58h+var_28], eax; int
0x140038145  mov     eax, [r10+20h]
0x140038149  mov     dword ptr [rsp+58h+pszDest], eax; int
0x14003814d  mov     rax, [r10+18h]
0x140038151  mov     [rsp+58h+Handle], rax; Handle
0x140038156  call    VsmmExoGpaRangeIoctlMap
0x14003815b  jmp     loc_14003844A
0x140038160  cmp     [rsp+58h+arg_20], 20h ; ' '
0x140038168  jb      short loc_140038128
0x14003816a  mov     eax, [r10+18h]
0x14003816e  mov     r9, [r10+10h]
0x140038172  mov     r8, [r10+8]
0x140038176  mov     rdx, [r10]
0x140038179  mov     dword ptr [rsp+58h+Handle], eax
0x14003817d  call    VsmmExoGpaRangeIoctlAccessTrackingControl
0x140038182  jmp     loc_14003844A
0x140038187  mov     eax, 22133Ch
0x14003818c  cmp     r9d, eax
0x14003818f  ja      loc_140038367
0x140038195  jz      loc_140038336
0x14003819b  mov     eax, r9d
0x14003819e  sub     eax, 221324h
0x1400381a3  jz      loc_1400382BB
0x1400381a9  sub     eax, 4
0x1400381ac  jz      loc_140038262
0x1400381b2  sub     eax, 4
0x1400381b5  jz      short loc_140038230
0x1400381b7  sub     eax, 8
0x1400381ba  jz      short loc_1400381F2
0x1400381bc  cmp     eax, 4
0x1400381bf  jnz     loc_140038388
0x1400381c5  cmp     [rsp+58h+arg_20], 18h
0x1400381cd  jb      loc_140038128
0x1400381d3  mov     edx, [r10]
0x1400381d6  lea     r8, [r10+8]
0x1400381da  mov     rcx, [rcx+288h]
0x1400381e1  call    cs:__imp_WinHvInstallIntercept
0x1400381e8  nop     dword ptr [rax+rax+00h]
0x1400381ed  jmp     loc_14003844A
0x1400381f2  cmp     [rsp+58h+arg_20], 4
0x1400381fa  jb      short loc_14003823A
0x1400381fc  cmp     [rsp+58h+arg_30], 20h ; ' '
0x140038204  jb      loc_140038128
0x14003820a  mov     r9, [rsp+58h+arg_28]
0x140038212  mov     rdx, r11
0x140038215  mov     r8d, [r10]
0x140038218  call    VidExoVpIoctlMap
0x14003821d  test    eax, eax
0x14003821f  js      loc_14003844A
0x140038225  mov     dword ptr [rdi], 20h ; ' '
0x14003822b  jmp     loc_14003844A
0x140038230  cmp     [rsp+58h+arg_20], 20h ; ' '
0x140038238  jnb     short loc_140038244
0x14003823a  mov     eax, 0C000000Dh
0x14003823f  jmp     loc_14003844A
0x140038244  mov     rax, [r10+18h]
0x140038248  lea     r9, [r10+8]
0x14003824c  mov     r8b, [r10+4]
0x140038250  mov     edx, [r10]
0x140038253  mov     [rsp+58h+Handle], rax; Handle
0x140038258  call    VidExoVpIoctlCreate
0x14003825d  jmp     loc_14003844A
0x140038262  mov     edx, [rsp+58h+arg_20]
0x140038269  cmp     edx, 20h ; ' '
0x14003826c  jbe     loc_140038128
0x140038272  add     edx, 0FFFFFFE0h
0x140038275  cmp     edx, 1FB000h
0x14003827b  ja      short loc_1400382E0
0x14003827d  lea     r9, [r10+8]
0x140038281  cmp     dword ptr [r9], 0
0x140038285  jl      short loc_14003828F
0x140038287  cmp     edx, 0FD8h
0x14003828d  ja      short loc_1400382E0
0x14003828f  mov     r8b, [r10+4]
0x140038293  lea     rax, [r10+20h]
0x140038297  mov     rcx, [rcx+288h]
0x14003829e  mov     dword ptr [rsp+58h+pszDest], edx
0x1400382a2  mov     edx, [r10]
0x1400382a5  mov     [rsp+58h+Handle], rax
0x1400382aa  call    cs:__imp_WinHvSetVpState
0x1400382b1  nop     dword ptr [rax+rax+00h]
0x1400382b6  jmp     loc_14003844A
0x1400382bb  cmp     [rsp+58h+arg_20], 20h ; ' '
0x1400382c3  jb      loc_140038128
0x1400382c9  mov     ebx, [rsp+58h+arg_30]
0x1400382d0  test    ebx, ebx
0x1400382d2  jz      loc_140038128
0x1400382d8  cmp     ebx, 1FB000h
0x1400382de  jbe     short loc_1400382EA
0x1400382e0  mov     eax, 80000005h
0x1400382e5  jmp     loc_14003844A
0x1400382ea  lea     r9, [r10+8]
0x1400382ee  cmp     dword ptr [r9], 0
0x1400382f2  jl      short loc_1400382FC
0x1400382f4  cmp     ebx, 1000h
0x1400382fa  ja      short loc_1400382E0
0x1400382fc  mov     rax, [rsp+58h+arg_28]
0x140038304  mov     r8b, [r10+4]
0x140038308  mov     edx, [r10]
0x14003830b  mov     rcx, [rcx+288h]
0x140038312  mov     dword ptr [rsp+58h+pszDest], ebx
0x140038316  mov     [rsp+58h+Handle], rax
0x14003831b  call    cs:__imp_WinHvGetVpState
0x140038322  nop     dword ptr [rax+rax+00h]
0x140038327  test    eax, eax
0x140038329  js      loc_14003844A
0x14003832f  mov     [rdi], ebx
0x140038331  jmp     loc_14003844A
0x140038336  cmp     [rsp+58h+arg_20], 38h ; '8'
0x14003833e  jb      loc_140038128
0x140038344  mov     r8d, [r10+4]
0x140038348  lea     r9, [r10+8]
0x14003834c  mov     edx, [r10]
0x14003834f  mov     rcx, [rcx+288h]
0x140038356  call    cs:__imp_WinHvRegisterInterceptResult
0x14003835d  nop     dword ptr [rax+rax+00h]
0x140038362  jmp     loc_14003844A
0x140038367  mov     eax, r9d
0x14003836a  sub     eax, 221340h
0x14003836f  jz      loc_14003842C
0x140038375  sub     eax, 4
0x140038378  jz      loc_14003840C
0x14003837e  sub     eax, 4
0x140038381  jz      short loc_1400383F0
0x140038383  cmp     eax, 4
0x140038386  jz      short loc_1400383C7
0x140038388  mov     rcx, cs:WPP_GLOBAL_Control
0x14003838f  lea     rax, WPP_GLOBAL_Control
0x140038396  cmp     rcx, rax
0x140038399  jz      short loc_1400383BD
0x14003839b  mov     eax, [rcx+2Ch]
0x14003839e  test    al, 1
0x1400383a0  jz      short loc_1400383BD
0x1400383a2  cmp     byte ptr [rcx+29h], 3
0x1400383a6  jb      short loc_1400383BD
0x1400383a8  mov     rcx, [rcx+18h]
0x1400383ac  lea     r8, WPP_a76ff6e5b5ee3bbc086e8bc9b11ca330_Traceguids
0x1400383b3  mov     edx, 0Ah
0x1400383b8  call    WPP_SF_d
0x1400383bd  mov     eax, 0C0000002h
0x1400383c2  jmp     loc_14003844A
0x1400383c7  mov     r9d, [rsp+58h+arg_30]
0x1400383cf  cmp     r9d, 10h
0x1400383d3  jb      loc_14003823A
0x1400383d9  mov     r8, [rsp+58h+arg_28]
0x1400383e1  mov     rdx, r11
0x1400383e4  mov     [rsp+58h+Handle], rdi
0x1400383e9  call    VidExoBrokerIoctlReceive
0x1400383ee  jmp     short loc_14003844A
0x1400383f0  mov     r9d, [rsp+58h+arg_20]
0x1400383f8  cmp     r9d, 10h
0x1400383fc  jb      loc_14003823A
0x140038402  mov     r8, r10
0x140038405  call    VidExoBrokerIoctlSend
0x14003840a  jmp     short loc_14003844A
0x14003840c  mov     r8d, [rsp+58h+arg_20]
0x140038414  test    r8b, 0Fh
0x140038418  jnz     loc_14003823A
0x14003841e  shr     r8d, 4
0x140038422  mov     rdx, r10
0x140038425  call    VsmmExoGpaRangeIoctlUnpin
0x14003842a  jmp     short loc_14003844A
0x14003842c  mov     r8d, [rsp+58h+arg_20]
0x140038434  test    r8b, 0Fh
0x140038438  jnz     loc_14003823A
0x14003843e  shr     r8d, 4
0x140038442  mov     rdx, r10
0x140038445  call    VsmmExoGpaRangeIoctlPin
0x14003844a  mov     rbx, [rsp+58h+arg_0]
0x14003844f  add     rsp, 50h
0x140038453  pop     rdi
0x140038454  retn
```
