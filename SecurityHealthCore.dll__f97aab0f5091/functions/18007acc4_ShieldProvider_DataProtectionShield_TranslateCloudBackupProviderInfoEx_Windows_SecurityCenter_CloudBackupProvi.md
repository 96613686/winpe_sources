# ShieldProvider::DataProtectionShield::TranslateCloudBackupProviderInfoEx(Windows::SecurityCenter::CloudBackupProviderNamespaceDetails *,Shield_CloudBackupProviderInfo * *)

- ea: `0x18007acc4`
- end: `0x18007afd4`
- name: `?TranslateCloudBackupProviderInfoEx@DataProtectionShield@ShieldProvider@@CAJPEAUCloudBackupProviderNamespaceDetails@SecurityCenter@Windows@@PEAPEAUShield_CloudBackupProviderInfo@@@Z`
- size: `784`
- prototype: `__int64 __fastcall(struct Windows::SecurityCenter::CloudBackupProviderNamespaceDetails *, struct Shield_CloudBackupProviderInfo **)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180078840`
- `0x18007963c`

## callees

- `0x18000d7fc`
- `0x180076714`
- `0x18007acc4`
- `0x1800e1764`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18007ad2c`
- `ole32!CoTaskMemFree` at `0x18007ad36`
- `ole32!CoTaskMemFree` at `0x18007ad40`
- `ole32!CoTaskMemFree` at `0x18007ad4a`
- `ole32!CoTaskMemFree` at `0x18007ad54`
- `ole32!CoTaskMemFree` at `0x18007ad5d`
- `ole32!CoTaskMemFree` at `0x18007af8a`
- `ole32!CoTaskMemFree` at `0x18007af94`
- `ole32!CoTaskMemFree` at `0x18007af9e`
- `ole32!CoTaskMemFree` at `0x18007afa8`
- `ole32!CoTaskMemFree` at `0x18007afb2`
- `ole32!CoTaskMemFree` at `0x18007afbb`
- `ole32!CoTaskMemFree` at `0x18007ad2c`
- `ole32!CoTaskMemFree` at `0x18007ad36`
- `ole32!CoTaskMemFree` at `0x18007ad40`
- `ole32!CoTaskMemFree` at `0x18007ad4a`
- `ole32!CoTaskMemFree` at `0x18007ad54`
- `ole32!CoTaskMemFree` at `0x18007ad5d`
- `ole32!CoTaskMemFree` at `0x18007af8a`
- `ole32!CoTaskMemFree` at `0x18007af94`
- `ole32!CoTaskMemFree` at `0x18007af9e`
- `ole32!CoTaskMemFree` at `0x18007afa8`
- `ole32!CoTaskMemFree` at `0x18007afb2`
- `ole32!CoTaskMemFree` at `0x18007afbb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007adec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007ae4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007ae98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007aee6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007af38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007adec`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007ae4d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007ae98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007aee6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007af38`

## pseudocode

```c
__int64 __fastcall ShieldProvider::DataProtectionShield::TranslateCloudBackupProviderInfoEx(
        struct Windows::SecurityCenter::CloudBackupProviderNamespaceDetails *a1,
        LPVOID **a2)
{
  int v4; // eax
  int v5; // ebp
  LPVOID *v6; // rbx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  HSTRING v14; // rcx
  unsigned __int16 **StringRawBuffer; // rax
  unsigned __int16 *v16; // r8
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  HSTRING v19; // rcx
  unsigned __int16 **v20; // rax
  unsigned __int16 *v21; // r8
  HSTRING v22; // rcx
  unsigned __int16 **v23; // rax
  unsigned __int16 *v24; // r8
  HSTRING v25; // rcx
  unsigned __int16 **v26; // rax
  unsigned __int16 *v27; // r8
  HSTRING v28; // rcx
  unsigned __int16 **v29; // rax
  unsigned __int16 *v30; // r8
  int v31; // eax
  unsigned int v32; // edi
  LPVOID pv; // [rsp+60h] [rbp+18h] BYREF

  pv = 0;
  v4 = CommonUtil::UtilCoTaskMemAllocObject<Shield_CloudBackupProviderInfo>(&pv);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        87,
        WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids,
        (unsigned int)v4);
    v6 = (LPVOID *)pv;
    goto LABEL_6;
  }
  v6 = (LPVOID *)pv;
  *(_OWORD *)((char *)pv + 4) = *((_OWORD *)a1 + 1);
  *(_DWORD *)v6 = *(_DWORD *)a1;
  *((_DWORD *)v6 + 16) = 3;
  if ( *((_DWORD *)a1 + 17) == 1 )
    *((_DWORD *)v6 + 16) = (*((_DWORD *)a1 + 16) != 1) + 1;
  v8 = *((_DWORD *)a1 + 18);
  if ( v8 && (v9 = v8 - 1) != 0 && (v10 = v9 - 1) != 0 && (v11 = v10 - 1) != 0 && (v12 = v11 - 1) != 0 )
  {
    v13 = v12 - 1;
    if ( v13 )
    {
      if ( v13 == 1 )
        *((_DWORD *)v6 + 17) = 3;
      else
        *((_DWORD *)v6 + 17) = 0;
    }
    else
    {
      *((_DWORD *)v6 + 17) = 2;
    }
  }
  else
  {
    *((_DWORD *)v6 + 17) = 1;
  }
  *((_DWORD *)v6 + 18) = *((_DWORD *)a1 + 19);
  v14 = (HSTRING)*((_QWORD *)a1 + 1);
  if ( v14 )
  {
    StringRawBuffer = (unsigned __int16 **)WindowsGetStringRawBuffer(v14, 0);
    v5 = CommonUtil::UtilCoDuplicateString((CommonUtil *)(v6 + 3), StringRawBuffer, v16);
    if ( v5 < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v18 = 88;
LABEL_27:
        WPP_SF_d(v17[2], v18, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids, (unsigned int)v5);
        goto LABEL_6;
      }
      goto LABEL_6;
    }
  }
  v19 = (HSTRING)*((_QWORD *)a1 + 6);
  if ( v19 )
  {
    v20 = (unsigned __int16 **)WindowsGetStringRawBuffer(v19, 0);
    v5 = CommonUtil::UtilCoDuplicateString((CommonUtil *)(v6 + 4), v20, v21);
    if ( v5 < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v18 = 89;
        goto LABEL_27;
      }
LABEL_6:
      if ( v6 )
      {
        CoTaskMemFree(v6[3]);
        CoTaskMemFree(v6[4]);
        CoTaskMemFree(v6[5]);
        CoTaskMemFree(v6[6]);
        CoTaskMemFree(v6[7]);
        CoTaskMemFree(v6);
      }
      return (unsigned int)v5;
    }
  }
  v22 = (HSTRING)*((_QWORD *)a1 + 4);
  if ( v22 )
  {
    v23 = (unsigned __int16 **)WindowsGetStringRawBuffer(v22, 0);
    v5 = CommonUtil::UtilCoDuplicateString((CommonUtil *)(v6 + 5), v23, v24);
    if ( v5 < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v18 = 90;
        goto LABEL_27;
      }
      goto LABEL_6;
    }
  }
  v25 = (HSTRING)*((_QWORD *)a1 + 5);
  if ( v25 )
  {
    v26 = (unsigned __int16 **)WindowsGetStringRawBuffer(v25, 0);
    v5 = CommonUtil::UtilCoDuplicateString((CommonUtil *)(v6 + 6), v26, v27);
    if ( v5 < 0 )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v18 = 91;
        goto LABEL_27;
      }
      goto LABEL_6;
    }
  }
  v28 = (HSTRING)*((_QWORD *)a1 + 7);
  if ( v28
    && (v29 = (unsigned __int16 **)WindowsGetStringRawBuffer(v28, 0),
        v31 = CommonUtil::UtilCoDuplicateString((CommonUtil *)(v6 + 7), v29, v30),
        v32 = v31,
        v31 < 0) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        92,
        WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids,
        (unsigned int)v31);
    if ( v6 )
    {
      CoTaskMemFree(v6[3]);
      CoTaskMemFree(v6[4]);
      CoTaskMemFree(v6[5]);
      CoTaskMemFree(v6[6]);
      CoTaskMemFree(v6[7]);
      CoTaskMemFree(v6);
    }
    return v32;
  }
  else
  {
    *a2 = v6;
    return 0;
  }
}

```

## disassembly

```asm
0x18007acc4  push    rbx
0x18007acc6  push    rbp
0x18007acc7  push    rdi
0x18007acc8  push    r14
0x18007acca  sub     rsp, 28h
0x18007acce  mov     rdi, rcx
0x18007acd1  mov     [rsp+48h+pv], 0
0x18007acda  lea     rcx, [rsp+48h+pv]
0x18007acdf  mov     r14, rdx
0x18007ace2  call    ??$UtilCoTaskMemAllocObject@UShield_CloudBackupProviderInfo@@@CommonUtil@@YAJPEAPEAUShield_CloudBackupProviderInfo@@_K_N@Z; CommonUtil::UtilCoTaskMemAllocObject<Shield_CloudBackupProviderInfo>(Shield_CloudBackupProviderInfo * *,unsigned __int64,bool)
0x18007ace7  mov     ebp, eax
0x18007ace9  test    eax, eax
0x18007aceb  jns     short loc_18007AD6A
0x18007aced  mov     rcx, cs:WPP_GLOBAL_Control
0x18007acf4  lea     rdx, WPP_GLOBAL_Control
0x18007acfb  cmp     rcx, rdx
0x18007acfe  jz      short loc_18007AD1E
0x18007ad00  test    byte ptr [rcx+1Ch], 1
0x18007ad04  jz      short loc_18007AD1E
0x18007ad06  mov     rcx, [rcx+10h]
0x18007ad0a  lea     r8, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids
0x18007ad11  mov     edx, 57h ; 'W'
0x18007ad16  mov     r9d, eax
0x18007ad19  call    WPP_SF_d
0x18007ad1e  mov     rbx, [rsp+48h+pv]
0x18007ad23  test    rbx, rbx
0x18007ad26  jz      short loc_18007AD63
0x18007ad28  mov     rcx, [rbx+18h]; pv
0x18007ad2c  call    cs:__imp_CoTaskMemFree
0x18007ad32  mov     rcx, [rbx+20h]; pv
0x18007ad36  call    cs:__imp_CoTaskMemFree
0x18007ad3c  mov     rcx, [rbx+28h]; pv
0x18007ad40  call    cs:__imp_CoTaskMemFree
0x18007ad46  mov     rcx, [rbx+30h]; pv
0x18007ad4a  call    cs:__imp_CoTaskMemFree
0x18007ad50  mov     rcx, [rbx+38h]; pv
0x18007ad54  call    cs:__imp_CoTaskMemFree
0x18007ad5a  mov     rcx, rbx; pv
0x18007ad5d  call    cs:__imp_CoTaskMemFree
0x18007ad63  mov     eax, ebp
0x18007ad65  jmp     loc_18007AFCA
0x18007ad6a  mov     rbx, [rsp+48h+pv]
0x18007ad6f  mov     edx, 3
0x18007ad74  movups  xmm0, xmmword ptr [rdi+10h]
0x18007ad78  movdqu  xmmword ptr [rbx+4], xmm0
0x18007ad7d  mov     eax, [rdi]
0x18007ad7f  mov     [rbx], eax
0x18007ad81  mov     [rbx+40h], edx
0x18007ad84  cmp     dword ptr [rdi+44h], 1
0x18007ad88  jnz     short loc_18007AD98
0x18007ad8a  xor     eax, eax
0x18007ad8c  cmp     dword ptr [rdi+40h], 1
0x18007ad90  setnz   al
0x18007ad93  inc     eax
0x18007ad95  mov     [rbx+40h], eax
0x18007ad98  mov     ecx, [rdi+48h]
0x18007ad9b  test    ecx, ecx
0x18007ad9d  jz      short loc_18007ADD4
0x18007ad9f  sub     ecx, 1
0x18007ada2  jz      short loc_18007ADD4
0x18007ada4  sub     ecx, 1
0x18007ada7  jz      short loc_18007ADD4
0x18007ada9  sub     ecx, 1
0x18007adac  jz      short loc_18007ADD4
0x18007adae  sub     ecx, 1
0x18007adb1  jz      short loc_18007ADD4
0x18007adb3  sub     ecx, 1
0x18007adb6  jz      short loc_18007ADCB
0x18007adb8  cmp     ecx, 1
0x18007adbb  jz      short loc_18007ADC6
0x18007adbd  mov     dword ptr [rbx+44h], 0
0x18007adc4  jmp     short loc_18007ADDB
0x18007adc6  mov     [rbx+44h], edx
0x18007adc9  jmp     short loc_18007ADDB
0x18007adcb  mov     dword ptr [rbx+44h], 2
0x18007add2  jmp     short loc_18007ADDB
0x18007add4  mov     dword ptr [rbx+44h], 1
0x18007addb  mov     eax, [rdi+4Ch]
0x18007adde  mov     [rbx+48h], eax
0x18007ade1  mov     rcx, [rdi+8]; string
0x18007ade5  test    rcx, rcx
0x18007ade8  jz      short loc_18007AE42
0x18007adea  xor     edx, edx; length
0x18007adec  call    cs:__imp_WindowsGetStringRawBuffer
0x18007adf2  mov     rdx, rax; unsigned __int16 **
0x18007adf5  lea     rcx, [rbx+18h]; this
0x18007adf9  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x18007adfe  mov     ebp, eax
0x18007ae00  test    eax, eax
0x18007ae02  jns     short loc_18007AE42
0x18007ae04  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ae0b  lea     rdx, WPP_GLOBAL_Control
0x18007ae12  cmp     rcx, rdx
0x18007ae15  jz      loc_18007AD23
0x18007ae1b  test    byte ptr [rcx+1Ch], 1
0x18007ae1f  jz      loc_18007AD23
0x18007ae25  mov     edx, 58h ; 'X'
0x18007ae2a  mov     rcx, [rcx+10h]
0x18007ae2e  lea     r8, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids
0x18007ae35  mov     r9d, ebp
0x18007ae38  call    WPP_SF_d
0x18007ae3d  jmp     loc_18007AD23
0x18007ae42  mov     rcx, [rdi+30h]; string
0x18007ae46  test    rcx, rcx
0x18007ae49  jz      short loc_18007AE8D
0x18007ae4b  xor     edx, edx; length
0x18007ae4d  call    cs:__imp_WindowsGetStringRawBuffer
0x18007ae53  mov     rdx, rax; unsigned __int16 **
0x18007ae56  lea     rcx, [rbx+20h]; this
0x18007ae5a  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x18007ae5f  mov     ebp, eax
0x18007ae61  test    eax, eax
0x18007ae63  jns     short loc_18007AE8D
0x18007ae65  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ae6c  lea     rdx, WPP_GLOBAL_Control
0x18007ae73  cmp     rcx, rdx
0x18007ae76  jz      loc_18007AD23
0x18007ae7c  test    byte ptr [rcx+1Ch], 1
0x18007ae80  jz      loc_18007AD23
0x18007ae86  mov     edx, 59h ; 'Y'
0x18007ae8b  jmp     short loc_18007AE2A
0x18007ae8d  mov     rcx, [rdi+20h]; string
0x18007ae91  test    rcx, rcx
0x18007ae94  jz      short loc_18007AEDB
0x18007ae96  xor     edx, edx; length
0x18007ae98  call    cs:__imp_WindowsGetStringRawBuffer
0x18007ae9e  mov     rdx, rax; unsigned __int16 **
0x18007aea1  lea     rcx, [rbx+28h]; this
0x18007aea5  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x18007aeaa  mov     ebp, eax
0x18007aeac  test    eax, eax
0x18007aeae  jns     short loc_18007AEDB
0x18007aeb0  mov     rcx, cs:WPP_GLOBAL_Control
0x18007aeb7  lea     rdx, WPP_GLOBAL_Control
0x18007aebe  cmp     rcx, rdx
0x18007aec1  jz      loc_18007AD23
0x18007aec7  test    byte ptr [rcx+1Ch], 1
0x18007aecb  jz      loc_18007AD23
0x18007aed1  mov     edx, 5Ah ; 'Z'
0x18007aed6  jmp     loc_18007AE2A
0x18007aedb  mov     rcx, [rdi+28h]; string
0x18007aedf  test    rcx, rcx
0x18007aee2  jz      short loc_18007AF29
0x18007aee4  xor     edx, edx; length
0x18007aee6  call    cs:__imp_WindowsGetStringRawBuffer
0x18007aeec  mov     rdx, rax; unsigned __int16 **
0x18007aeef  lea     rcx, [rbx+30h]; this
0x18007aef3  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x18007aef8  mov     ebp, eax
0x18007aefa  test    eax, eax
0x18007aefc  jns     short loc_18007AF29
0x18007aefe  mov     rcx, cs:WPP_GLOBAL_Control
0x18007af05  lea     rdx, WPP_GLOBAL_Control
0x18007af0c  cmp     rcx, rdx
0x18007af0f  jz      loc_18007AD23
0x18007af15  test    byte ptr [rcx+1Ch], 1
0x18007af19  jz      loc_18007AD23
0x18007af1f  mov     edx, 5Bh ; '['
0x18007af24  jmp     loc_18007AE2A
0x18007af29  mov     rcx, [rdi+38h]; string
0x18007af2d  test    rcx, rcx
0x18007af30  jz      loc_18007AFC5
0x18007af36  xor     edx, edx; length
0x18007af38  call    cs:__imp_WindowsGetStringRawBuffer
0x18007af3e  mov     rdx, rax; unsigned __int16 **
0x18007af41  lea     rcx, [rbx+38h]; this
0x18007af45  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x18007af4a  mov     edi, eax
0x18007af4c  test    eax, eax
0x18007af4e  jns     short loc_18007AFC5
0x18007af50  mov     rcx, cs:WPP_GLOBAL_Control
0x18007af57  lea     rdx, WPP_GLOBAL_Control
0x18007af5e  cmp     rcx, rdx
0x18007af61  jz      short loc_18007AF81
0x18007af63  test    byte ptr [rcx+1Ch], 1
0x18007af67  jz      short loc_18007AF81
0x18007af69  mov     rcx, [rcx+10h]
0x18007af6d  lea     r8, WPP_719fd88cf1093718c4ebc2b6da90c1c0_Traceguids
0x18007af74  mov     edx, 5Ch ; '\'
0x18007af79  mov     r9d, eax
0x18007af7c  call    WPP_SF_d
0x18007af81  test    rbx, rbx
0x18007af84  jz      short loc_18007AFC1
0x18007af86  mov     rcx, [rbx+18h]; pv
0x18007af8a  call    cs:__imp_CoTaskMemFree
0x18007af90  mov     rcx, [rbx+20h]; pv
0x18007af94  call    cs:__imp_CoTaskMemFree
0x18007af9a  mov     rcx, [rbx+28h]; pv
0x18007af9e  call    cs:__imp_CoTaskMemFree
0x18007afa4  mov     rcx, [rbx+30h]; pv
0x18007afa8  call    cs:__imp_CoTaskMemFree
0x18007afae  mov     rcx, [rbx+38h]; pv
0x18007afb2  call    cs:__imp_CoTaskMemFree
0x18007afb8  mov     rcx, rbx; pv
0x18007afbb  call    cs:__imp_CoTaskMemFree
0x18007afc1  mov     eax, edi
0x18007afc3  jmp     short loc_18007AFCA
0x18007afc5  mov     [r14], rbx
0x18007afc8  xor     eax, eax
0x18007afca  add     rsp, 28h
0x18007afce  pop     r14
0x18007afd0  pop     rdi
0x18007afd1  pop     rbp
0x18007afd2  pop     rbx
0x18007afd3  retn
```
