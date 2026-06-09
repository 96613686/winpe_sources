# USBSTOR_DetectPortableWorkspace

- ea: `0x14001f964`
- end: `0x14001fb75`
- name: `USBSTOR_DetectPortableWorkspace`
- size: `529`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400209f4`

## callees

- `0x1400105e8`
- `0x140013950`
- `0x140013d40`
- `0x14001f964`
- `0x1400208c0`

## import_xrefs

- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14001fadd`
- `ntoskrnl!RtlQueryRegistryValuesEx` at `0x14001fadd`
- `ntoskrnl!PoDisableSleepStates` at `0x14001fb11`
- `ntoskrnl!PoDisableSleepStates` at `0x14001fb11`
- `ntoskrnl!RtlCheckPortableOperatingSystem` at `0x14001f9b4`
- `ntoskrnl!RtlCheckPortableOperatingSystem` at `0x14001f9b4`
- `ntoskrnl!RtlSetPortableOperatingSystem` at `0x14001f9f2`
- `ntoskrnl!RtlSetPortableOperatingSystem` at `0x14001f9f2`

## string_xrefs

- `0x14001faba`: `\Registry\Machine\System\CurrentControlSet\Policies\Microsoft\PortableOperatingSystem`

## pseudocode

```c
__int64 __fastcall USBSTOR_DetectPortableWorkspace(PDEVICE_OBJECT DeviceObject)
{
  __int64 result; // rax
  __int64 v3; // rcx
  PDEVICE_OBJECT v4; // rcx
  __int64 v5; // rdx
  int v6; // ecx
  bool v7; // [rsp+30h] [rbp-D0h] BYREF
  char v8; // [rsp+31h] [rbp-CFh]
  int v9; // [rsp+34h] [rbp-CCh] BYREF
  int v10; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v11; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v12[22]; // [rsp+50h] [rbp-B0h] BYREF

  v10 = 0;
  v9 = 0;
  v7 = 0;
  v8 = 0;
  v11 = 0;
  result = RtlCheckPortableOperatingSystem(&v7);
  if ( (_DWORD)result == -1073741275 )
  {
    result = USBSTOR_InRootContainer(DeviceObject);
    if ( (int)result < 0 )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        result = HIDWORD(WPP_GLOBAL_Control->Timer);
        if ( (result & 2) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v5 = 175;
          goto LABEL_12;
        }
      }
    }
    else
    {
      LOBYTE(v3) = v8 == 0;
      v7 = v8 == 0;
      result = RtlSetPortableOperatingSystem(v3);
      if ( (int)result < 0 )
      {
        v4 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v5 = 174;
LABEL_12:
          result = WPP_SF_d(v4->AttachedDevice, v5, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
        }
      }
    }
  }
  if ( v7 )
  {
    v9 = 0;
    v10 = 1;
    memset(v12, 0, 0xA8u);
    LODWORD(v12[4]) = 0x4000000;
    LODWORD(v12[1]) = 288;
    v12[2] = L"Hibernate";
    LODWORD(v12[8]) = 288;
    v12[3] = &v9;
    LODWORD(v12[11]) = 0x4000000;
    v12[9] = L"Sleep";
    v12[10] = &v10;
    RtlQueryRegistryValuesEx(
      0,
      L"\\Registry\\Machine\\System\\CurrentControlSet\\Policies\\Microsoft\\PortableOperatingSystem",
      v12);
    v6 = v9 == 0 ? 8 : 0;
    result = (unsigned int)-v10;
    if ( v6 | (v10 == 0 ? 7 : 0) )
    {
      result = PoDisableSleepStates(3, v6 | (unsigned int)(v10 == 0 ? 7 : 0), &v11);
      if ( (int)result < 0
        && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        return WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 176, WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001f964  mov     [rsp-8+arg_8], rbx
0x14001f969  mov     [rsp-8+arg_10], r14
0x14001f96e  push    rbp
0x14001f96f  lea     rbp, [rsp-10h]
0x14001f974  sub     rsp, 110h
0x14001f97b  mov     rax, cs:__security_cookie
0x14001f982  xor     rax, rsp
0x14001f985  mov     [rbp+10h+var_10], rax
0x14001f989  mov     rbx, rcx
0x14001f98c  mov     [rsp+110h+var_D8], 0
0x14001f994  lea     rcx, [rsp+110h+var_E0]
0x14001f999  mov     [rsp+110h+var_DC], 0
0x14001f9a1  mov     [rsp+110h+var_E0], 0
0x14001f9a6  mov     [rsp+110h+var_DF], 0
0x14001f9ab  mov     [rsp+110h+var_D0], 0
0x14001f9b4  call    cs:__imp_RtlCheckPortableOperatingSystem
0x14001f9bb  nop     dword ptr [rax+rax+00h]
0x14001f9c0  lea     r14, WPP_GLOBAL_Control
0x14001f9c7  cmp     eax, 0C0000225h
0x14001f9cc  jnz     loc_14001FA54
0x14001f9d2  lea     rdx, [rsp+110h+var_DF]
0x14001f9d7  mov     rcx, rbx; DeviceObject
0x14001f9da  call    USBSTOR_InRootContainer
0x14001f9df  mov     r9d, eax
0x14001f9e2  test    eax, eax
0x14001f9e4  js      short loc_14001FA26
0x14001f9e6  cmp     [rsp+110h+var_DF], 0
0x14001f9eb  setz    cl
0x14001f9ee  mov     [rsp+110h+var_E0], cl
0x14001f9f2  call    cs:__imp_RtlSetPortableOperatingSystem
0x14001f9f9  nop     dword ptr [rax+rax+00h]
0x14001f9fe  test    eax, eax
0x14001fa00  jns     short loc_14001FA54
0x14001fa02  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fa09  cmp     rcx, r14
0x14001fa0c  jz      short loc_14001FA54
0x14001fa0e  mov     edx, [rcx+2Ch]
0x14001fa11  test    dl, 2
0x14001fa14  jz      short loc_14001FA54
0x14001fa16  cmp     byte ptr [rcx+29h], 2
0x14001fa1a  jb      short loc_14001FA54
0x14001fa1c  mov     edx, 0AEh
0x14001fa21  mov     r9d, eax
0x14001fa24  jmp     short loc_14001FA44
0x14001fa26  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fa2d  cmp     rcx, r14
0x14001fa30  jz      short loc_14001FA54
0x14001fa32  mov     eax, [rcx+2Ch]
0x14001fa35  test    al, 2
0x14001fa37  jz      short loc_14001FA54
0x14001fa39  cmp     byte ptr [rcx+29h], 2
0x14001fa3d  jb      short loc_14001FA54
0x14001fa3f  mov     edx, 0AFh
0x14001fa44  mov     rcx, [rcx+18h]
0x14001fa48  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x14001fa4f  call    WPP_SF_d
0x14001fa54  cmp     [rsp+110h+var_E0], 0
0x14001fa59  jz      loc_14001FB53
0x14001fa5f  xor     edx, edx; Val
0x14001fa61  mov     [rsp+110h+var_DC], 0
0x14001fa69  mov     r8d, 0A8h; Size
0x14001fa6f  mov     [rsp+110h+var_D8], 1
0x14001fa77  lea     rcx, [rsp+110h+var_C0]; void *
0x14001fa7c  call    memset
0x14001fa81  mov     ecx, 4000000h
0x14001fa86  mov     [rsp+110h+var_F0], 0
0x14001fa8f  mov     edx, 120h
0x14001fa94  mov     [rsp+110h+var_A0], ecx
0x14001fa98  lea     rax, aHibernate; "Hibernate"
0x14001fa9f  mov     [rsp+110h+var_B8], edx
0x14001faa3  mov     [rsp+110h+var_B0], rax
0x14001faa8  lea     r8, [rsp+110h+var_C0]
0x14001faad  lea     rax, [rsp+110h+var_DC]
0x14001fab2  mov     [rbp+10h+var_80], edx
0x14001fab5  mov     [rsp+110h+var_A8], rax
0x14001faba  lea     rdx, aRegistryMachin_1; "\\Registry\\Machine\\System\\CurrentCon"...
0x14001fac1  lea     rax, aSleep; "Sleep"
0x14001fac8  mov     [rbp+10h+var_68], ecx
0x14001facb  mov     [rbp+10h+var_78], rax
0x14001facf  xor     r9d, r9d
0x14001fad2  lea     rax, [rsp+110h+var_D8]
0x14001fad7  xor     ecx, ecx
0x14001fad9  mov     [rbp+10h+var_70], rax
0x14001fadd  call    cs:__imp_RtlQueryRegistryValuesEx
0x14001fae4  nop     dword ptr [rax+rax+00h]
0x14001fae9  mov     eax, [rsp+110h+var_DC]
0x14001faed  neg     eax
0x14001faef  mov     eax, [rsp+110h+var_D8]
0x14001faf3  sbb     ecx, ecx
0x14001faf5  not     ecx
0x14001faf7  and     ecx, 8
0x14001fafa  neg     eax
0x14001fafc  sbb     edx, edx
0x14001fafe  not     edx
0x14001fb00  and     edx, 7
0x14001fb03  or      edx, ecx
0x14001fb05  jz      short loc_14001FB53
0x14001fb07  lea     r8, [rsp+110h+var_D0]
0x14001fb0c  mov     ecx, 3
0x14001fb11  call    cs:__imp_PoDisableSleepStates
0x14001fb18  nop     dword ptr [rax+rax+00h]
0x14001fb1d  test    eax, eax
0x14001fb1f  jns     short loc_14001FB53
0x14001fb21  mov     rcx, cs:WPP_GLOBAL_Control
0x14001fb28  cmp     rcx, r14
0x14001fb2b  jz      short loc_14001FB53
0x14001fb2d  mov     edx, [rcx+2Ch]
0x14001fb30  test    dl, 2
0x14001fb33  jz      short loc_14001FB53
0x14001fb35  cmp     byte ptr [rcx+29h], 2
0x14001fb39  jb      short loc_14001FB53
0x14001fb3b  mov     rcx, [rcx+18h]
0x14001fb3f  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x14001fb46  mov     edx, 0B0h
0x14001fb4b  mov     r9d, eax
0x14001fb4e  call    WPP_SF_d
0x14001fb53  mov     rcx, [rbp+10h+var_10]
0x14001fb57  xor     rcx, rsp; StackCookie
0x14001fb5a  call    __security_check_cookie
0x14001fb5f  lea     r11, [rsp+110h+var_s0]
0x14001fb67  mov     rbx, [r11+18h]
0x14001fb6b  mov     r14, [r11+20h]
0x14001fb6f  mov     rsp, r11
0x14001fb72  pop     rbp
0x14001fb73  retn
```
