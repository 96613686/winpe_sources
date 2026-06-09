# AutoConfigNotificationCallback(_L2_NOTIFICATION_DATA *,void *)

- ea: `0x18001aba0`
- end: `0x18001afba`
- name: `?AutoConfigNotificationCallback@@YAXPEAU_L2_NOTIFICATION_DATA@@PEAX@Z`
- size: `1050`
- prototype: `void __stdcall(PWLAN_NOTIFICATION_DATA, PVOID)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x1800110fc`
- `0x180011194`
- `0x18001aba0`
- `0x18001bf4c`
- `0x18001c2e4`

## import_xrefs

- `wlanapi!WlanFreeMemory` at `0x18001af51`
- `wlanapi!WlanFreeMemory` at `0x18001af51`
- `wlanapi!WlanEnumInterfaces` at `0x18001ad2b`
- `wlanapi!WlanEnumInterfaces` at `0x18001ad2b`

## pseudocode

```c
void __fastcall AutoConfigNotificationCallback(PWLAN_NOTIFICATION_DATA a1, PVOID a2)
{
  PWLAN_INTERFACE_INFO_LIST v2; // r8
  _BYTE *v4; // rcx
  char v5; // bl
  bool v6; // dl
  int v7; // r8d
  _QWORD *v8; // r10
  bool v9; // cl
  int v10; // edx
  bool v11; // dl
  int v12; // edx
  int v13; // r8d
  _BYTE *v14; // rcx
  bool v15; // r10
  _UNKNOWN **v16; // r9
  int v17; // edx
  GUID *v18; // rdx
  bool v19; // al
  bool v20; // al
  int v21; // [rsp+20h] [rbp-48h]
  int v22; // [rsp+28h] [rbp-40h]
  __int16 v23; // [rsp+30h] [rbp-38h]
  PWLAN_INTERFACE_INFO_LIST ppInterfaceList; // [rsp+70h] [rbp+8h] BYREF

  v2 = 0;
  ppInterfaceList = 0;
  v4 = WPP_GLOBAL_Control;
  v5 = 1;
  v6 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v6,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v2 = ppInterfaceList;
    v4 = WPP_GLOBAL_Control;
  }
  if ( a1->NotificationSource != 8 )
  {
    if ( a1->NotificationSource != 16 )
      goto LABEL_70;
    if ( a1->NotificationCode != 6 )
      goto LABEL_71;
    *((_BYTE *)pInterfaceGuid + 120) = QueryCurrent80211Channel();
    v8 = WPP_GLOBAL_Control;
    v9 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
    LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !v9 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_70;
    v10 = *((unsigned __int8 *)pInterfaceGuid + 120);
    v23 = 40;
LABEL_69:
    LOBYTE(v10) = v9;
    WPP_RECORDER_AND_TRACE_SF_sd(
      v8[2],
      v10,
      v7,
      v8[5],
      v21,
      v22,
      v23,
      (__int64)WPP_3ced9c3b7bc93563dc6bccedf26a5837_Traceguids);
    goto LABEL_70;
  }
  switch ( a1->NotificationCode )
  {
    case 0xAu:
      *((_BYTE *)pInterfaceGuid + 120) = QueryCurrent80211Channel();
      v8 = WPP_GLOBAL_Control;
      v9 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
      LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      if ( !v9 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        break;
      v10 = *((unsigned __int8 *)pInterfaceGuid + 120);
      v23 = 34;
      goto LABEL_69;
    case 0xDu:
    case 0xEu:
      if ( WlanEnumInterfaces(*((HANDLE *)pInterfaceGuid + 12), 0, &ppInterfaceList) )
      {
        LOBYTE(v12) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
        if ( (_BYTE)v12 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v12,
            v13,
            *((_QWORD *)WPP_GLOBAL_Control + 5),
            v21,
            v22,
            36,
            (__int64)WPP_3ced9c3b7bc93563dc6bccedf26a5837_Traceguids);
        }
        *((_DWORD *)pInterfaceGuid + 28) = 0;
      }
      else
      {
        *((_DWORD *)pInterfaceGuid + 28) = ppInterfaceList->dwNumberOfItems;
        v14 = WPP_GLOBAL_Control;
        v15 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
        v16 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
        if ( v15 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        {
          v17 = *((_DWORD *)pInterfaceGuid + 28);
          LOBYTE(v17) = v15;
          LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
          WPP_RECORDER_AND_TRACE_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v17,
            v13,
            *((_QWORD *)WPP_GLOBAL_Control + 5),
            v21,
            v22,
            37,
            (__int64)WPP_3ced9c3b7bc93563dc6bccedf26a5837_Traceguids);
          v14 = WPP_GLOBAL_Control;
          v16 = (_UNKNOWN **)WPP_RECORDER_INITIALIZED;
        }
        v18 = (GUID *)pInterfaceGuid;
        if ( *((_DWORD *)pInterfaceGuid + 28) == 1 )
        {
          v19 = v14 != (_BYTE *)&WPP_GLOBAL_Control && v14[25] >= 4u;
          if ( v19 || v16 != &WPP_RECORDER_INITIALIZED )
          {
            WPP_RECORDER_AND_TRACE_SF_s(
              *((_QWORD *)v14 + 2),
              v19,
              v16 != &WPP_RECORDER_INITIALIZED,
              *((_QWORD *)v14 + 5));
            v18 = (GUID *)pInterfaceGuid;
          }
          *v18 = ppInterfaceList->InterfaceInfo[0].InterfaceGuid;
          *((_BYTE *)pInterfaceGuid + 120) = QueryCurrent80211Channel();
        }
        else
        {
          v20 = v14 != (_BYTE *)&WPP_GLOBAL_Control && v14[25] >= 4u;
          if ( v20 || v16 != &WPP_RECORDER_INITIALIZED )
          {
            WPP_RECORDER_AND_TRACE_SF_s(
              *((_QWORD *)v14 + 2),
              v20,
              v16 != &WPP_RECORDER_INITIALIZED,
              *((_QWORD *)v14 + 5));
            v18 = (GUID *)pInterfaceGuid;
          }
          *v18 = 0;
          *((_BYTE *)pInterfaceGuid + 120) = 0;
        }
      }
      break;
    case 0x15u:
      *((_BYTE *)pInterfaceGuid + 120) = 0;
      v11 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
      if ( v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_AND_TRACE_SF_s(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v11,
          WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
          *((_QWORD *)WPP_GLOBAL_Control + 5));
      break;
    default:
      goto LABEL_71;
  }
LABEL_70:
  ProcessNotification();
  v2 = ppInterfaceList;
  v4 = WPP_GLOBAL_Control;
LABEL_71:
  if ( v2 )
  {
    WlanFreeMemory(v2);
    v4 = WPP_GLOBAL_Control;
    ppInterfaceList = 0;
  }
  if ( v4 == (_BYTE *)&WPP_GLOBAL_Control || v4[25] < 4u )
    v5 = 0;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)v4 + 2),
      v5,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)v4 + 5));
}

```

## disassembly

```asm
0x18001aba0  mov     [rsp+arg_8], rbx
0x18001aba5  mov     [rsp+arg_10], rdi
0x18001abaa  push    r12
0x18001abac  push    r14
0x18001abae  push    r15
0x18001abb0  sub     rsp, 50h
0x18001abb4  xor     r8d, r8d
0x18001abb7  mov     rdi, rcx
0x18001abba  mov     [rsp+68h+ppInterfaceList], r8
0x18001abbf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001abc6  lea     r14, WPP_GLOBAL_Control
0x18001abcd  lea     ebx, [r8+1]
0x18001abd1  cmp     rcx, r14
0x18001abd4  jz      short loc_18001ABE0
0x18001abd6  cmp     byte ptr [rcx+19h], 4
0x18001abda  jb      short loc_18001ABE0
0x18001abdc  mov     dl, bl
0x18001abde  jmp     short loc_18001ABE2
0x18001abe0  xor     dl, dl
0x18001abe2  lea     r15, WPP_RECORDER_INITIALIZED
0x18001abe9  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001abf0  lea     r12, WPP_3ced9c3b7bc93563dc6bccedf26a5837_Traceguids
0x18001abf7  setnz   al
0x18001abfa  test    dl, dl
0x18001abfc  jnz     short loc_18001AC02
0x18001abfe  test    al, al
0x18001ac00  jz      short loc_18001AC2A
0x18001ac02  mov     r9, [rcx+28h]
0x18001ac06  mov     r8b, al
0x18001ac09  mov     rcx, [rcx+10h]
0x18001ac0d  mov     [rsp+68h+var_30], r12
0x18001ac12  mov     [rsp+68h+var_38], 21h ; '!'
0x18001ac19  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001ac1e  mov     r8, [rsp+68h+ppInterfaceList]
0x18001ac23  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ac2a  cmp     dword ptr [rdi], 8
0x18001ac2d  jz      short loc_18001ACA2
0x18001ac2f  cmp     dword ptr [rdi], 10h
0x18001ac32  jnz     loc_18001AF38
0x18001ac38  cmp     dword ptr [rdi+4], 6
0x18001ac3c  jnz     loc_18001AF49
0x18001ac42  call    ?QueryCurrent80211Channel@@YAEXZ; QueryCurrent80211Channel(void)
0x18001ac47  mov     rcx, cs:pInterfaceGuid
0x18001ac4e  mov     [rcx+78h], al
0x18001ac51  mov     r10, cs:WPP_GLOBAL_Control
0x18001ac58  cmp     r10, r14
0x18001ac5b  jz      short loc_18001AC68
0x18001ac5d  cmp     byte ptr [r10+19h], 4
0x18001ac62  jb      short loc_18001AC68
0x18001ac64  mov     cl, bl
0x18001ac66  jmp     short loc_18001AC6A
0x18001ac68  xor     cl, cl
0x18001ac6a  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001ac71  setnz   r8b
0x18001ac75  test    cl, cl
0x18001ac77  jnz     short loc_18001AC82
0x18001ac79  test    r8b, r8b
0x18001ac7c  jz      loc_18001AF38
0x18001ac82  mov     rax, cs:pInterfaceGuid
0x18001ac89  movzx   edx, byte ptr [rax+78h]
0x18001ac8d  mov     [rsp+68h+var_20], edx
0x18001ac91  mov     [rsp+68h+var_30], r12
0x18001ac96  mov     [rsp+68h+var_38], 28h ; '('
0x18001ac9d  jmp     loc_18001AF29
0x18001aca2  mov     edx, [rdi+4]
0x18001aca5  sub     edx, 0Ah
0x18001aca8  jz      loc_18001AED2
0x18001acae  sub     edx, 3
0x18001acb1  jz      short loc_18001AD19
0x18001acb3  sub     edx, ebx
0x18001acb5  jz      short loc_18001AD19
0x18001acb7  cmp     edx, 7
0x18001acba  jnz     loc_18001AF49
0x18001acc0  mov     rax, cs:pInterfaceGuid
0x18001acc7  mov     byte ptr [rax+78h], 0
0x18001accb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001acd2  cmp     rcx, r14
0x18001acd5  jz      short loc_18001ACE1
0x18001acd7  cmp     byte ptr [rcx+19h], 4
0x18001acdb  jb      short loc_18001ACE1
0x18001acdd  mov     dl, bl
0x18001acdf  jmp     short loc_18001ACE3
0x18001ace1  xor     dl, dl
0x18001ace3  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001acea  setnz   r8b
0x18001acee  test    dl, dl
0x18001acf0  jnz     short loc_18001ACFB
0x18001acf2  test    r8b, r8b
0x18001acf5  jz      loc_18001AF38
0x18001acfb  mov     r9, [rcx+28h]
0x18001acff  mov     rcx, [rcx+10h]
0x18001ad03  mov     [rsp+68h+var_30], r12
0x18001ad08  mov     [rsp+68h+var_38], 23h ; '#'
0x18001ad0f  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001ad14  jmp     loc_18001AF38
0x18001ad19  mov     rcx, cs:pInterfaceGuid
0x18001ad20  lea     r8, [rsp+68h+ppInterfaceList]; ppInterfaceList
0x18001ad25  xor     edx, edx; pReserved
0x18001ad27  mov     rcx, [rcx+60h]; hClientHandle
0x18001ad2b  call    cs:__imp_WlanEnumInterfaces
0x18001ad31  test    eax, eax
0x18001ad33  jz      short loc_18001AD91
0x18001ad35  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ad3c  cmp     rcx, r14
0x18001ad3f  jz      short loc_18001AD4B
0x18001ad41  cmp     byte ptr [rcx+19h], 3
0x18001ad45  jb      short loc_18001AD4B
0x18001ad47  mov     dl, bl
0x18001ad49  jmp     short loc_18001AD4D
0x18001ad4b  xor     dl, dl
0x18001ad4d  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001ad54  setnz   r8b
0x18001ad58  test    dl, dl
0x18001ad5a  jnz     short loc_18001AD61
0x18001ad5c  test    r8b, r8b
0x18001ad5f  jz      short loc_18001AD7E
0x18001ad61  mov     r9, [rcx+28h]
0x18001ad65  mov     rcx, [rcx+10h]
0x18001ad69  mov     [rsp+68h+var_20], eax
0x18001ad6d  mov     [rsp+68h+var_30], r12
0x18001ad72  mov     [rsp+68h+var_38], 24h ; '$'
0x18001ad79  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18001ad7e  mov     rax, cs:pInterfaceGuid
0x18001ad85  mov     dword ptr [rax+70h], 0
0x18001ad8c  jmp     loc_18001AF38
0x18001ad91  mov     rax, [rsp+68h+ppInterfaceList]
0x18001ad96  mov     ecx, [rax]
0x18001ad98  mov     rax, cs:pInterfaceGuid
0x18001ad9f  mov     [rax+70h], ecx
0x18001ada2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ada9  cmp     rcx, r14
0x18001adac  jz      short loc_18001ADB9
0x18001adae  cmp     byte ptr [rcx+19h], 4
0x18001adb2  jb      short loc_18001ADB9
0x18001adb4  mov     r10b, bl
0x18001adb7  jmp     short loc_18001ADBC
0x18001adb9  xor     r10b, r10b
0x18001adbc  mov     r9, cs:WPP_RECORDER_INITIALIZED
0x18001adc3  cmp     r9, r15
0x18001adc6  setnz   r8b
0x18001adca  test    r10b, r10b
0x18001adcd  jnz     short loc_18001ADD4
0x18001adcf  test    r8b, r8b
0x18001add2  jz      short loc_18001AE0C
0x18001add4  mov     rax, cs:pInterfaceGuid
0x18001addb  mov     r9, [rcx+28h]
0x18001addf  mov     rcx, [rcx+10h]
0x18001ade3  mov     edx, [rax+70h]
0x18001ade6  mov     [rsp+68h+var_20], edx
0x18001adea  mov     dl, r10b
0x18001aded  mov     [rsp+68h+var_30], r12
0x18001adf2  mov     [rsp+68h+var_38], 25h ; '%'
0x18001adf9  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18001adfe  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ae05  mov     r9, cs:WPP_RECORDER_INITIALIZED
0x18001ae0c  mov     rdx, cs:pInterfaceGuid
0x18001ae13  cmp     [rdx+70h], ebx
0x18001ae16  jnz     short loc_18001AE7C
0x18001ae18  cmp     rcx, r14
0x18001ae1b  jz      short loc_18001AE27
0x18001ae1d  cmp     byte ptr [rcx+19h], 4
0x18001ae21  jb      short loc_18001AE27
0x18001ae23  mov     al, bl
0x18001ae25  jmp     short loc_18001AE29
0x18001ae27  xor     al, al
0x18001ae29  cmp     r9, r15
0x18001ae2c  setnz   r8b
0x18001ae30  test    al, al
0x18001ae32  jnz     short loc_18001AE39
0x18001ae34  test    r8b, r8b
0x18001ae37  jz      short loc_18001AE5B
0x18001ae39  mov     r9, [rcx+28h]
0x18001ae3d  mov     dl, al
0x18001ae3f  mov     rcx, [rcx+10h]
0x18001ae43  mov     [rsp+68h+var_30], r12
0x18001ae48  mov     [rsp+68h+var_38], 26h ; '&'
0x18001ae4f  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001ae54  mov     rdx, cs:pInterfaceGuid
0x18001ae5b  mov     rax, [rsp+68h+ppInterfaceList]
0x18001ae60  movups  xmm0, xmmword ptr [rax+8]
0x18001ae64  movdqu  xmmword ptr [rdx], xmm0
0x18001ae68  call    ?QueryCurrent80211Channel@@YAEXZ; QueryCurrent80211Channel(void)
0x18001ae6d  mov     rcx, cs:pInterfaceGuid
0x18001ae74  mov     [rcx+78h], al
0x18001ae77  jmp     loc_18001AF38
0x18001ae7c  cmp     rcx, r14
0x18001ae7f  jz      short loc_18001AE8B
0x18001ae81  cmp     byte ptr [rcx+19h], 4
0x18001ae85  jb      short loc_18001AE8B
0x18001ae87  mov     al, bl
0x18001ae89  jmp     short loc_18001AE8D
0x18001ae8b  xor     al, al
0x18001ae8d  cmp     r9, r15
0x18001ae90  setnz   r8b
0x18001ae94  test    al, al
0x18001ae96  jnz     short loc_18001AE9D
0x18001ae98  test    r8b, r8b
0x18001ae9b  jz      short loc_18001AEBF
0x18001ae9d  mov     r9, [rcx+28h]
0x18001aea1  mov     dl, al
0x18001aea3  mov     rcx, [rcx+10h]
0x18001aea7  mov     [rsp+68h+var_30], r12
0x18001aeac  mov     [rsp+68h+var_38], 27h ; '''
0x18001aeb3  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001aeb8  mov     rdx, cs:pInterfaceGuid
0x18001aebf  xorps   xmm0, xmm0
0x18001aec2  movups  xmmword ptr [rdx], xmm0
0x18001aec5  mov     rax, cs:pInterfaceGuid
0x18001aecc  mov     byte ptr [rax+78h], 0
0x18001aed0  jmp     short loc_18001AF38
0x18001aed2  call    ?QueryCurrent80211Channel@@YAEXZ; QueryCurrent80211Channel(void)
0x18001aed7  mov     rcx, cs:pInterfaceGuid
0x18001aede  mov     [rcx+78h], al
0x18001aee1  mov     r10, cs:WPP_GLOBAL_Control
0x18001aee8  cmp     r10, r14
0x18001aeeb  jz      short loc_18001AEF8
0x18001aeed  cmp     byte ptr [r10+19h], 4
0x18001aef2  jb      short loc_18001AEF8
0x18001aef4  mov     cl, bl
0x18001aef6  jmp     short loc_18001AEFA
0x18001aef8  xor     cl, cl
0x18001aefa  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001af01  setnz   r8b
0x18001af05  test    cl, cl
0x18001af07  jnz     short loc_18001AF0E
0x18001af09  test    r8b, r8b
0x18001af0c  jz      short loc_18001AF38
0x18001af0e  mov     rax, cs:pInterfaceGuid
0x18001af15  movzx   edx, byte ptr [rax+78h]
0x18001af19  mov     [rsp+68h+var_20], edx
0x18001af1d  mov     [rsp+68h+var_30], r12
0x18001af22  mov     [rsp+68h+var_38], 22h ; '"'
0x18001af29  mov     r9, [r10+28h]
0x18001af2d  mov     dl, cl
0x18001af2f  mov     rcx, [r10+10h]
0x18001af33  call    WPP_RECORDER_AND_TRACE_SF_sd
0x18001af38  call    ?ProcessNotification@@YAXXZ; ProcessNotification(void)
0x18001af3d  mov     r8, [rsp+68h+ppInterfaceList]
0x18001af42  mov     rcx, cs:WPP_GLOBAL_Control
0x18001af49  test    r8, r8
0x18001af4c  jz      short loc_18001AF67
0x18001af4e  mov     rcx, r8; pMemory
0x18001af51  call    cs:__imp_WlanFreeMemory
0x18001af57  mov     rcx, cs:WPP_GLOBAL_Control
0x18001af5e  mov     [rsp+68h+ppInterfaceList], 0
0x18001af67  cmp     rcx, r14
0x18001af6a  jz      short loc_18001AF72
0x18001af6c  cmp     byte ptr [rcx+19h], 4
0x18001af70  jnb     short loc_18001AF74
0x18001af72  xor     bl, bl
0x18001af74  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001af7b  setnz   r8b
0x18001af7f  test    bl, bl
0x18001af81  jnz     short loc_18001AF88
0x18001af83  test    r8b, r8b
0x18001af86  jz      short loc_18001AFA3
0x18001af88  mov     r9, [rcx+28h]
0x18001af8c  mov     dl, bl
0x18001af8e  mov     rcx, [rcx+10h]
0x18001af92  mov     [rsp+68h+var_30], r12
0x18001af97  mov     [rsp+68h+var_38], 29h ; ')'
0x18001af9e  call    WPP_RECORDER_AND_TRACE_SF_s
0x18001afa3  lea     r11, [rsp+68h+var_18]
0x18001afa8  mov     rbx, [r11+28h]
0x18001afac  mov     rdi, [r11+30h]
0x18001afb0  mov     rsp, r11
0x18001afb3  pop     r15
0x18001afb5  pop     r14
0x18001afb7  pop     r12
0x18001afb9  retn
```
