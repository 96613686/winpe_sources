# SearchHidDevicesForRadioFeature

- ea: `0x1800035b0`
- end: `0x180003910`
- name: `SearchHidDevicesForRadioFeature`
- size: `864`
- prototype: `__int64 __fastcall(unsigned int, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009500`
- `0x18000970c`

## callees

- `0x180002ec0`
- `0x1800035b0`
- `0x180003920`
- `0x180003ce0`
- `0x180003d50`
- `0x18000d2a0`
- `0x18000df4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003839`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003839`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800037aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800037aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003826`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800038d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003826`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800038d7`
- `HID!HidD_GetHidGuid` at `0x180003604`
- `HID!HidD_GetHidGuid` at `0x180003604`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180003677`
- `DEVOBJ!DevObjDestroyDeviceInfoList` at `0x180003677`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18000373f`
- `DEVOBJ!DevObjEnumDeviceInterfaces` at `0x18000373f`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18000376a`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1800037eb`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x18000376a`
- `DEVOBJ!DevObjGetDeviceInterfaceDetail` at `0x1800037eb`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180003619`
- `DEVOBJ!DevObjCreateDeviceInfoList` at `0x180003619`
- `DEVOBJ!DevObjGetClassDevs` at `0x18000364f`
- `DEVOBJ!DevObjGetClassDevs` at `0x18000364f`

## pseudocode

```c
__int64 __fastcall SearchHidDevicesForRadioFeature(unsigned int a1, __int64 a2)
{
  unsigned int v4; // edi
  unsigned __int8 v5; // bp
  __int64 DeviceInfoList; // rax
  __int64 v7; // rsi
  __int64 v8; // rcx
  unsigned __int64 v10; // rcx
  _DWORD *v11; // rax
  _DWORD *v12; // rbx
  __int64 v13; // rcx
  __int64 v14; // rdx
  size_t Size; // [rsp+30h] [rbp-68h] BYREF
  GUID HidGuid; // [rsp+38h] [rbp-60h] BYREF
  _OWORD v17[2]; // [rsp+48h] [rbp-50h] BYREF

  HidGuid = 0;
  v4 = 0;
  LODWORD(Size) = 0;
  memset(v17, 0, sizeof(v17));
  v5 = 0;
  HidD_GetHidGuid(&HidGuid);
  DeviceInfoList = DevObjCreateDeviceInfoList(0, 0, 0, 0, 0);
  v7 = DeviceInfoList;
  if ( DeviceInfoList != -1 )
  {
    if ( !(unsigned int)DevObjGetClassDevs(DeviceInfoList, &HidGuid, 0, 18, 0, 0) )
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 80, &WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids);
      }
LABEL_4:
      DevObjDestroyDeviceInfoList(v7);
      goto LABEL_5;
    }
    while ( 1 )
    {
      while ( 1 )
      {
        LODWORD(v17[0]) = 32;
        if ( (unsigned int)DevObjEnumDeviceInterfaces(v7, 0, &HidGuid, v4, v17) )
          break;
        if ( GetLastError() == 259 )
          goto LABEL_4;
      }
      DevObjGetDeviceInterfaceDetail(v7, v17, 0, 0, &Size, 0);
      if ( (_DWORD)Size )
      {
        if ( 0xFFFFFFFFFFFFFFFFuLL / (unsigned int)Size < 8 )
        {
          v12 = 0;
          goto LABEL_37;
        }
        v10 = 8LL * (unsigned int)Size;
        if ( v10 > 0x7FFFFFFF )
        {
          v12 = 0;
          goto LABEL_37;
        }
      }
      else
      {
        LODWORD(v10) = 0;
      }
      v11 = CoTaskMemAlloc((unsigned int)v10);
      v12 = v11;
      if ( v11 )
      {
        memset_0(v11, 0, (unsigned int)Size);
        *v12 = 8;
        if ( (unsigned int)DevObjGetDeviceInterfaceDetail(v7, v17, v12, (unsigned int)Size, 0, 0) )
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0
            && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 4u )
          {
            WPP_SF_S(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              77,
              &WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids,
              v12 + 1);
          }
          v5 = CheckIfDeviceHasRadioFeature(v12 + 1, a1, a2);
          if ( v5 )
          {
            ++v4;
            CoTaskMemFree(v12);
            goto LABEL_4;
          }
        }
        else
        {
          v13 = WPP_GLOBAL_Control;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0
            && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
          {
            v14 = 78;
LABEL_34:
            WPP_SF_(*(_QWORD *)(v13 + 16), v14, &WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids);
            goto LABEL_24;
          }
        }
        goto LABEL_24;
      }
LABEL_37:
      v13 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0
        && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      {
        v14 = 79;
        goto LABEL_34;
      }
LABEL_24:
      ++v4;
      CoTaskMemFree(v12);
    }
  }
  v8 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v5;
  if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 81, &WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids);
LABEL_5:
    v8 = WPP_GLOBAL_Control;
  }
  if ( (_UNKNOWN *)v8 != &WPP_GLOBAL_Control && (*(_BYTE *)(v8 + 28) & 1) != 0 && *(_BYTE *)(v8 + 25) >= 4u )
    WPP_SF_d(*(_QWORD *)(v8 + 16), 82, &WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids, v4);
  return v5;
}

```

## disassembly

```asm
0x1800035b0  mov     [rsp+arg_10], rbp
0x1800035b5  mov     [rsp+arg_18], rsi
0x1800035ba  push    rdi
0x1800035bb  push    r12
0x1800035bd  push    r13
0x1800035bf  push    r14
0x1800035c1  push    r15
0x1800035c3  sub     rsp, 70h
0x1800035c7  mov     rax, cs:__security_cookie
0x1800035ce  xor     rax, rsp
0x1800035d1  mov     [rsp+98h+var_30], rax
0x1800035d6  xorps   xmm1, xmm1
0x1800035d9  mov     r15d, ecx
0x1800035dc  xorps   xmm0, xmm0
0x1800035df  lea     rcx, [rsp+98h+HidGuid]; HidGuid
0x1800035e4  xor     r13d, r13d
0x1800035e7  mov     r12, rdx
0x1800035ea  movups  xmmword ptr [rsp+98h+HidGuid.Data1], xmm0
0x1800035ef  mov     edi, r13d
0x1800035f2  mov     dword ptr [rsp+98h+Size], r13d
0x1800035f7  movups  [rsp+98h+var_50], xmm1
0x1800035fc  xor     bpl, bpl
0x1800035ff  movups  [rsp+98h+var_40], xmm1
0x180003604  call    cs:__imp_HidD_GetHidGuid
0x18000360a  xor     r9d, r9d
0x18000360d  mov     [rsp+98h+var_78], r13
0x180003612  xor     r8d, r8d
0x180003615  xor     edx, edx
0x180003617  xor     ecx, ecx
0x180003619  call    cs:__imp_DevObjCreateDeviceInfoList
0x18000361f  mov     rsi, rax
0x180003622  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180003626  jz      loc_1800036E2
0x18000362c  mov     [rsp+98h+var_70], r13
0x180003631  lea     rdx, [rsp+98h+HidGuid]
0x180003636  mov     r9d, 12h
0x18000363c  mov     [rsp+98h+var_78], r13
0x180003641  xor     r8d, r8d
0x180003644  mov     [rsp+98h+arg_0], rbx
0x18000364c  mov     rcx, rax
0x18000364f  call    cs:__imp_DevObjGetClassDevs
0x180003655  lea     r14, WPP_GLOBAL_Control
0x18000365c  test    eax, eax
0x18000365e  jnz     loc_180003720
0x180003664  mov     rcx, cs:WPP_GLOBAL_Control
0x18000366b  cmp     rcx, r14
0x18000366e  jnz     loc_1800038E2
0x180003674  mov     rcx, rsi
0x180003677  call    cs:__imp_DevObjDestroyDeviceInfoList
0x18000367d  mov     rbx, [rsp+98h+arg_0]
0x180003685  mov     rcx, cs:WPP_GLOBAL_Control
0x18000368c  cmp     rcx, r14
0x18000368f  jnz     short loc_1800036BC
0x180003691  movzx   eax, bpl
0x180003695  mov     rcx, [rsp+98h+var_30]
0x18000369a  xor     rcx, rsp; StackCookie
0x18000369d  call    __security_check_cookie
0x1800036a2  lea     r11, [rsp+98h+var_28]
0x1800036a7  mov     rbp, [r11+40h]
0x1800036ab  mov     rsi, [r11+48h]
0x1800036af  mov     rsp, r11
0x1800036b2  pop     r15
0x1800036b4  pop     r14
0x1800036b6  pop     r13
0x1800036b8  pop     r12
0x1800036ba  pop     rdi
0x1800036bb  retn
0x1800036bc  test    byte ptr [rcx+1Ch], 1
0x1800036c0  jz      short loc_180003691
0x1800036c2  cmp     byte ptr [rcx+19h], 4
0x1800036c6  jb      short loc_180003691
0x1800036c8  mov     rcx, [rcx+10h]
0x1800036cc  lea     r8, WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids
0x1800036d3  mov     edx, 52h ; 'R'
0x1800036d8  mov     r9d, edi
0x1800036db  call    WPP_SF_d
0x1800036e0  jmp     short loc_180003691
0x1800036e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800036e9  lea     r14, WPP_GLOBAL_Control
0x1800036f0  cmp     rcx, r14
0x1800036f3  jz      short loc_180003691
0x1800036f5  test    byte ptr [rcx+1Ch], 1
0x1800036f9  jz      short loc_18000368C
0x1800036fb  cmp     byte ptr [rcx+19h], 2
0x1800036ff  jb      short loc_18000368C
0x180003701  mov     rcx, [rcx+10h]
0x180003705  lea     r8, WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids
0x18000370c  mov     edx, 51h ; 'Q'
0x180003711  call    WPP_SF_
0x180003716  jmp     loc_180003685
0x180003720  lea     rax, [rsp+98h+var_50]
0x180003725  mov     dword ptr [rsp+98h+var_50], 20h ; ' '
0x18000372d  mov     r9d, edi
0x180003730  mov     [rsp+98h+var_78], rax
0x180003735  lea     r8, [rsp+98h+HidGuid]
0x18000373a  xor     edx, edx
0x18000373c  mov     rcx, rsi
0x18000373f  call    cs:__imp_DevObjEnumDeviceInterfaces
0x180003745  test    eax, eax
0x180003747  jz      loc_180003839
0x18000374d  lea     rax, [rsp+98h+Size]
0x180003752  mov     [rsp+98h+var_70], r13
0x180003757  xor     r9d, r9d
0x18000375a  mov     [rsp+98h+var_78], rax
0x18000375f  xor     r8d, r8d
0x180003762  lea     rdx, [rsp+98h+var_50]
0x180003767  mov     rcx, rsi
0x18000376a  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x180003770  mov     ecx, dword ptr [rsp+98h+Size]
0x180003774  test    rcx, rcx
0x180003777  jz      loc_180003831
0x18000377d  xor     edx, edx
0x18000377f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180003786  div     rcx
0x180003789  cmp     rax, 8
0x18000378d  jb      loc_18000389F
0x180003793  lea     rcx, ds:0[rcx*8]
0x18000379b  cmp     rcx, 7FFFFFFFh
0x1800037a2  ja      loc_1800038A4
0x1800037a8  mov     ecx, ecx; cb
0x1800037aa  call    cs:__imp_CoTaskMemAlloc
0x1800037b0  mov     rbx, rax
0x1800037b3  test    rax, rax
0x1800037b6  jz      loc_1800038A7
0x1800037bc  mov     r8d, dword ptr [rsp+98h+Size]; Size
0x1800037c1  xor     edx, edx; Val
0x1800037c3  mov     rcx, rax; void *
0x1800037c6  call    memset_0
0x1800037cb  mov     dword ptr [rbx], 8
0x1800037d1  lea     rdx, [rsp+98h+var_50]
0x1800037d6  mov     r9d, dword ptr [rsp+98h+Size]
0x1800037db  mov     r8, rbx
0x1800037de  mov     rcx, rsi
0x1800037e1  mov     [rsp+98h+var_70], r13
0x1800037e6  mov     [rsp+98h+var_78], r13
0x1800037eb  call    cs:__imp_DevObjGetDeviceInterfaceDetail
0x1800037f1  test    eax, eax
0x1800037f3  jz      short loc_180003870
0x1800037f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800037fc  cmp     rcx, r14
0x1800037ff  jz      short loc_180003807
0x180003801  test    byte ptr [rcx+1Ch], 1
0x180003805  jnz     short loc_18000384F
0x180003807  lea     rcx, [rbx+4]
0x18000380b  mov     r8, r12
0x18000380e  mov     edx, r15d
0x180003811  call    CheckIfDeviceHasRadioFeature
0x180003816  movzx   ebp, al
0x180003819  test    al, al
0x18000381b  jnz     loc_1800038D2
0x180003821  inc     edi
0x180003823  mov     rcx, rbx; pv
0x180003826  call    cs:__imp_CoTaskMemFree
0x18000382c  jmp     loc_180003720
0x180003831  mov     rcx, r13
0x180003834  jmp     loc_1800037A8
0x180003839  call    cs:__imp_GetLastError
0x18000383f  cmp     eax, 103h
0x180003844  jnz     loc_180003720
0x18000384a  jmp     loc_180003674
0x18000384f  cmp     byte ptr [rcx+19h], 4
0x180003853  jb      short loc_180003807
0x180003855  mov     rcx, [rcx+10h]
0x180003859  lea     r9, [rbx+4]
0x18000385d  mov     edx, 4Dh ; 'M'
0x180003862  lea     r8, WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids
0x180003869  call    WPP_SF_S
0x18000386e  jmp     short loc_180003807
0x180003870  mov     rcx, cs:WPP_GLOBAL_Control
0x180003877  cmp     rcx, r14
0x18000387a  jz      short loc_180003821
0x18000387c  test    byte ptr [rcx+1Ch], 1
0x180003880  jz      short loc_180003821
0x180003882  cmp     byte ptr [rcx+19h], 2
0x180003886  jb      short loc_180003821
0x180003888  mov     edx, 4Eh ; 'N'
0x18000388d  mov     rcx, [rcx+10h]
0x180003891  lea     r8, WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids
0x180003898  call    WPP_SF_
0x18000389d  jmp     short loc_180003821
0x18000389f  mov     rbx, r13
0x1800038a2  jmp     short loc_1800038A7
0x1800038a4  mov     rbx, r13
0x1800038a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800038ae  cmp     rcx, r14
0x1800038b1  jz      loc_180003821
0x1800038b7  test    byte ptr [rcx+1Ch], 1
0x1800038bb  jz      loc_180003821
0x1800038c1  cmp     byte ptr [rcx+19h], 2
0x1800038c5  jb      loc_180003821
0x1800038cb  mov     edx, 4Fh ; 'O'
0x1800038d0  jmp     short loc_18000388D
0x1800038d2  inc     edi
0x1800038d4  mov     rcx, rbx; pv
0x1800038d7  call    cs:__imp_CoTaskMemFree
0x1800038dd  jmp     loc_180003674
0x1800038e2  test    byte ptr [rcx+1Ch], 1
0x1800038e6  jz      loc_180003674
0x1800038ec  cmp     byte ptr [rcx+19h], 2
0x1800038f0  jb      loc_180003674
0x1800038f6  mov     rcx, [rcx+10h]
0x1800038fa  lea     r8, WPP_a21bdbfcba293ef5dc0b3c60c52e054b_Traceguids
0x180003901  mov     edx, 50h ; 'P'
0x180003906  call    WPP_SF_
0x18000390b  jmp     loc_180003674
```
