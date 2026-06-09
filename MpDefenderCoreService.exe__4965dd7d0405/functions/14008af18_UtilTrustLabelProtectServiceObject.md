# UtilTrustLabelProtectServiceObject

- ea: `0x14008af18`
- end: `0x14008b0ae`
- name: `UtilTrustLabelProtectServiceObject`
- size: `406`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x14008a040`

## callees

- `0x1400103fc`
- `0x1400108f4`
- `0x140016064`
- `0x1400160cc`
- `0x14003a5c0`
- `0x14007d210`
- `0x14008af18`

## import_xrefs

- `ADVAPI32!CloseServiceHandle` at `0x14008af8e`
- `ADVAPI32!CloseServiceHandle` at `0x14008affd`
- `ADVAPI32!CloseServiceHandle` at `0x14008b080`
- `ADVAPI32!CloseServiceHandle` at `0x14008b08f`
- `ADVAPI32!CloseServiceHandle` at `0x14008af8e`
- `ADVAPI32!CloseServiceHandle` at `0x14008affd`
- `ADVAPI32!CloseServiceHandle` at `0x14008b080`
- `ADVAPI32!CloseServiceHandle` at `0x14008b08f`

## pseudocode

```c
__int64 UtilTrustLabelProtectServiceObject()
{
  int v0; // eax
  int v1; // ebx
  void *v3; // r8
  __int64 v4; // rcx
  __int64 v5; // rdx
  const wchar_t *v6; // r9
  SC_HANDLE v7; // [rsp+20h] [rbp-20h] BYREF
  SC_HANDLE hSCObject; // [rsp+28h] [rbp-18h] BYREF

  hSCObject = 0;
  v0 = CommonUtil::HrOpenSCManager((CommonUtil *)&hSCObject, (struct SC_HANDLE__ **)1, 0, 0, (const wchar_t *)v7);
  v1 = v0;
  if ( v0 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        14,
        &WPP_015d1d1aad8334bf574fd190c463be63_Traceguids,
        (unsigned int)v0);
LABEL_5:
    if ( hSCObject )
      CloseServiceHandle(hSCObject);
    return (unsigned int)v1;
  }
  v1 = CommonUtil::HrOpenService(
         (CommonUtil *)&v7,
         (struct SC_HANDLE__ **)hSCObject,
         (struct SC_HANDLE__ *)L"MDCoreSvc",
         (const wchar_t *)0x1000002,
         0);
  if ( v1 < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v5 = 15;
LABEL_12:
      WPP_SF_d(*(_QWORD *)(v4 + 16), v5, &WPP_015d1d1aad8334bf574fd190c463be63_Traceguids, (unsigned int)v1);
      goto LABEL_13;
    }
    goto LABEL_13;
  }
  v1 = CommonUtil::UtilRemoveTrustLabelAceForObject(SE_SERVICE, v7, v3);
  if ( v1 < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v5 = 16;
      goto LABEL_12;
    }
LABEL_13:
    if ( v7 )
      CloseServiceHandle(v7);
    goto LABEL_5;
  }
  v1 = CommonUtil::UtilAddTrustLabelAceForObject(SE_SERVICE, v7, L"S:P(TL;;CCLCSWRPLOCRRC;;;S-1-19-512-1536)", v6);
  if ( v1 < 0 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v5 = 17;
      goto LABEL_12;
    }
    goto LABEL_13;
  }
  if ( v7 )
    CloseServiceHandle(v7);
  if ( hSCObject )
    CloseServiceHandle(hSCObject);
  return 0;
}

```

## disassembly

```asm
0x14008af18  mov     [rsp-8+arg_0], rbx
0x14008af1d  push    rbp
0x14008af1e  mov     rbp, rsp
0x14008af21  sub     rsp, 40h
0x14008af25  mov     rax, cs:__security_cookie
0x14008af2c  xor     rax, rsp
0x14008af2f  mov     [rbp+var_10], rax
0x14008af33  xor     r9d, r9d; wchar_t *
0x14008af36  mov     [rbp+hSCObject], 0
0x14008af3e  xor     r8d, r8d; unsigned int
0x14008af41  lea     rcx, [rbp+hSCObject]; this
0x14008af45  lea     edx, [r9+1]; struct SC_HANDLE__ **
0x14008af49  call    ?HrOpenSCManager@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@KPEB_W1@Z; CommonUtil::HrOpenSCManager(SC_HANDLE__ * *,ulong,wchar_t const *,wchar_t const *)
0x14008af4e  mov     ebx, eax
0x14008af50  test    eax, eax
0x14008af52  jns     short loc_14008AF9B
0x14008af54  mov     rcx, cs:WPP_GLOBAL_Control
0x14008af5b  lea     rdx, WPP_GLOBAL_Control
0x14008af62  cmp     rcx, rdx
0x14008af65  jz      short loc_14008AF85
0x14008af67  test    byte ptr [rcx+1Ch], 1
0x14008af6b  jz      short loc_14008AF85
0x14008af6d  mov     rcx, [rcx+10h]
0x14008af71  lea     r8, WPP_015d1d1aad8334bf574fd190c463be63_Traceguids
0x14008af78  mov     edx, 0Eh
0x14008af7d  mov     r9d, eax
0x14008af80  call    WPP_SF_d
0x14008af85  mov     rcx, [rbp+hSCObject]; hSCObject
0x14008af89  test    rcx, rcx
0x14008af8c  jz      short loc_14008AF94
0x14008af8e  call    cs:__imp_CloseServiceHandle
0x14008af94  mov     eax, ebx
0x14008af96  jmp     loc_14008B097
0x14008af9b  mov     rdx, [rbp+hSCObject]; struct SC_HANDLE__ **
0x14008af9f  lea     r8, aMdcoresvc_0; "MDCoreSvc"
0x14008afa6  mov     r9d, 1000002h; wchar_t *
0x14008afac  mov     [rbp+var_20], 0
0x14008afb4  lea     rcx, [rbp+var_20]; this
0x14008afb8  call    ?HrOpenService@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@PEAU2@PEB_WK@Z; CommonUtil::HrOpenService(SC_HANDLE__ * *,SC_HANDLE__ *,wchar_t const *,ulong)
0x14008afbd  mov     ebx, eax
0x14008afbf  test    eax, eax
0x14008afc1  jns     short loc_14008B005
0x14008afc3  mov     rcx, cs:WPP_GLOBAL_Control
0x14008afca  lea     rdx, WPP_GLOBAL_Control
0x14008afd1  cmp     rcx, rdx
0x14008afd4  jz      short loc_14008AFF4
0x14008afd6  test    byte ptr [rcx+1Ch], 1
0x14008afda  jz      short loc_14008AFF4
0x14008afdc  mov     edx, 0Fh
0x14008afe1  mov     rcx, [rcx+10h]
0x14008afe5  lea     r8, WPP_015d1d1aad8334bf574fd190c463be63_Traceguids
0x14008afec  mov     r9d, ebx
0x14008afef  call    WPP_SF_d
0x14008aff4  mov     rcx, [rbp+var_20]; hSCObject
0x14008aff8  test    rcx, rcx
0x14008affb  jz      short loc_14008AF85
0x14008affd  call    cs:__imp_CloseServiceHandle
0x14008b003  jmp     short loc_14008AF85
0x14008b005  mov     rdx, [rbp+var_20]; handle
0x14008b009  mov     ecx, 2; ObjectType
0x14008b00e  call    ?UtilRemoveTrustLabelAceForObject@CommonUtil@@YAJW4_SE_OBJECT_TYPE@@PEAX@Z; CommonUtil::UtilRemoveTrustLabelAceForObject(_SE_OBJECT_TYPE,void *)
0x14008b013  mov     ebx, eax
0x14008b015  test    eax, eax
0x14008b017  jns     short loc_14008B039
0x14008b019  mov     rcx, cs:WPP_GLOBAL_Control
0x14008b020  lea     rdx, WPP_GLOBAL_Control
0x14008b027  cmp     rcx, rdx
0x14008b02a  jz      short loc_14008AFF4
0x14008b02c  test    byte ptr [rcx+1Ch], 1
0x14008b030  jz      short loc_14008AFF4
0x14008b032  mov     edx, 10h
0x14008b037  jmp     short loc_14008AFE1
0x14008b039  mov     rdx, [rbp+var_20]; handle
0x14008b03d  lea     r8, aSPTlCclcswrplo; "S:P(TL;;CCLCSWRPLOCRRC;;;S-1-19-512-153"...
0x14008b044  mov     ecx, 2; ObjectType
0x14008b049  call    ?UtilAddTrustLabelAceForObject@CommonUtil@@YAJW4_SE_OBJECT_TYPE@@PEAXPEB_W@Z; CommonUtil::UtilAddTrustLabelAceForObject(_SE_OBJECT_TYPE,void *,wchar_t const *)
0x14008b04e  mov     ebx, eax
0x14008b050  test    eax, eax
0x14008b052  jns     short loc_14008B077
0x14008b054  mov     rcx, cs:WPP_GLOBAL_Control
0x14008b05b  lea     rdx, WPP_GLOBAL_Control
0x14008b062  cmp     rcx, rdx
0x14008b065  jz      short loc_14008AFF4
0x14008b067  test    byte ptr [rcx+1Ch], 1
0x14008b06b  jz      short loc_14008AFF4
0x14008b06d  mov     edx, 11h
0x14008b072  jmp     loc_14008AFE1
0x14008b077  mov     rcx, [rbp+var_20]; hSCObject
0x14008b07b  test    rcx, rcx
0x14008b07e  jz      short loc_14008B086
0x14008b080  call    cs:__imp_CloseServiceHandle
0x14008b086  mov     rcx, [rbp+hSCObject]; hSCObject
0x14008b08a  test    rcx, rcx
0x14008b08d  jz      short loc_14008B095
0x14008b08f  call    cs:__imp_CloseServiceHandle
0x14008b095  xor     eax, eax
0x14008b097  mov     rcx, [rbp+var_10]
0x14008b09b  xor     rcx, rsp; StackCookie
0x14008b09e  call    __security_check_cookie
0x14008b0a3  mov     rbx, [rsp+40h+arg_0]
0x14008b0a8  add     rsp, 40h
0x14008b0ac  pop     rbp
0x14008b0ad  retn
```
