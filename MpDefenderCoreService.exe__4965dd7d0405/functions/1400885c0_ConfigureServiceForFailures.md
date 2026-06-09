# ConfigureServiceForFailures

- ea: `0x1400885c0`
- end: `0x14008878e`
- name: `ConfigureServiceForFailures`
- size: `462`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140088790`

## callees

- `0x140016064`
- `0x1400160cc`
- `0x14003a5c0`
- `0x14007d210`
- `0x1400885c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140088710`
- `KERNEL32!GetLastError` at `0x140088710`
- `ADVAPI32!CloseServiceHandle` at `0x140088686`
- `ADVAPI32!CloseServiceHandle` at `0x1400886f1`
- `ADVAPI32!CloseServiceHandle` at `0x140088752`
- `ADVAPI32!CloseServiceHandle` at `0x140088761`
- `ADVAPI32!CloseServiceHandle` at `0x140088686`
- `ADVAPI32!CloseServiceHandle` at `0x1400886f1`
- `ADVAPI32!CloseServiceHandle` at `0x140088752`
- `ADVAPI32!CloseServiceHandle` at `0x140088761`
- `ADVAPI32!ChangeServiceConfig2W` at `0x140088706`
- `ADVAPI32!ChangeServiceConfig2W` at `0x140088706`

## pseudocode

```c
__int64 ConfigureServiceForFailures()
{
  int v0; // eax
  signed int v1; // ebx
  __int64 v3; // rcx
  __int64 v4; // rdx
  signed int LastError; // eax
  _QWORD Info[5]; // [rsp+20h] [rbp-60h] BYREF
  __int16 v7; // [rsp+48h] [rbp-38h] BYREF
  SC_HANDLE hSCObject; // [rsp+50h] [rbp-30h] BYREF
  SC_HANDLE hService; // [rsp+58h] [rbp-28h] BYREF
  _DWORD v10[6]; // [rsp+60h] [rbp-20h] BYREF

  Info[3] = 3;
  Info[2] = &v7;
  v10[1] = 1000;
  v10[3] = 10000;
  v10[0] = 1;
  v10[2] = 1;
  v10[5] = 60000;
  v10[4] = 1;
  v7 = 0;
  Info[1] = 0;
  Info[4] = v10;
  hSCObject = 0;
  v0 = CommonUtil::HrOpenSCManager((CommonUtil *)&hSCObject, (struct SC_HANDLE__ **)1, 0, 0, (const wchar_t *)0x15180);
  v1 = v0;
  if ( v0 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        11,
        &WPP_015d1d1aad8334bf574fd190c463be63_Traceguids,
        (unsigned int)v0);
LABEL_5:
    if ( hSCObject )
      CloseServiceHandle(hSCObject);
    return (unsigned int)v1;
  }
  hService = 0;
  v1 = CommonUtil::HrOpenService(
         (CommonUtil *)&hService,
         (struct SC_HANDLE__ **)hSCObject,
         (struct SC_HANDLE__ *)L"MDCoreSvc",
         (const wchar_t *)0x12,
         Info[0]);
  if ( v1 < 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      v4 = 12;
LABEL_12:
      WPP_SF_d(*(_QWORD *)(v3 + 16), v4, &WPP_015d1d1aad8334bf574fd190c463be63_Traceguids, (unsigned int)v1);
      goto LABEL_13;
    }
    goto LABEL_13;
  }
  if ( !ChangeServiceConfig2W(hService, 2u, Info) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    if ( v1 < 0 )
    {
      v3 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        v4 = 13;
        goto LABEL_12;
      }
LABEL_13:
      if ( hService )
        CloseServiceHandle(hService);
      goto LABEL_5;
    }
  }
  if ( hService )
    CloseServiceHandle(hService);
  if ( hSCObject )
    CloseServiceHandle(hSCObject);
  return 0;
}

```

## disassembly

```asm
0x1400885c0  mov     [rsp-8+arg_0], rbx
0x1400885c5  mov     [rsp-8+arg_8], rsi
0x1400885ca  mov     [rsp-8+arg_10], rdi
0x1400885cf  push    rbp
0x1400885d0  mov     rbp, rsp
0x1400885d3  sub     rsp, 80h
0x1400885da  mov     rax, cs:__security_cookie
0x1400885e1  xor     rax, rsp
0x1400885e4  mov     [rbp+var_8], rax
0x1400885e8  xor     edi, edi
0x1400885ea  mov     [rbp+Info], 15180h
0x1400885f2  lea     rax, [rbp+var_38]
0x1400885f6  mov     [rbp+var_48], 3
0x1400885fe  mov     [rbp+var_50], rax
0x140088602  lea     rcx, [rbp+hSCObject]; this
0x140088606  lea     rax, [rbp+var_20]
0x14008860a  mov     [rbp+var_1C], 3E8h
0x140088611  lea     esi, [rdi+1]
0x140088614  mov     [rbp+var_14], 2710h
0x14008861b  mov     edx, esi; struct SC_HANDLE__ **
0x14008861d  mov     [rbp+var_20], esi
0x140088620  xor     r9d, r9d; wchar_t *
0x140088623  mov     [rbp+var_18], esi
0x140088626  xor     r8d, r8d; unsigned int
0x140088629  mov     [rbp+var_C], 0EA60h
0x140088630  mov     [rbp+var_10], esi
0x140088633  mov     [rbp+var_38], di
0x140088637  mov     [rbp+var_58], rdi
0x14008863b  mov     [rbp+var_40], rax
0x14008863f  mov     [rbp+hSCObject], rdi
0x140088643  call    ?HrOpenSCManager@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@KPEB_W1@Z
0x140088648  mov     ebx, eax
0x14008864a  test    eax, eax
0x14008864c  jns     short loc_140088693
0x14008864e  mov     rcx, cs:WPP_GLOBAL_Control
0x140088655  lea     rdx, WPP_GLOBAL_Control
0x14008865c  cmp     rcx, rdx
0x14008865f  jz      short loc_14008867D
0x140088661  test    [rcx+1Ch], sil
0x140088665  jz      short loc_14008867D
0x140088667  mov     rcx, [rcx+10h]
0x14008866b  lea     edx, [rdi+0Bh]
0x14008866e  mov     r9d, eax
0x140088671  lea     r8, WPP_015d1d1aad8334bf574fd190c463be63_Traceguids
0x140088678  call    WPP_SF_d
0x14008867d  mov     rcx, [rbp+hSCObject]; hSCObject
0x140088681  test    rcx, rcx
0x140088684  jz      short loc_14008868C
0x140088686  call    cs:__imp_CloseServiceHandle
0x14008868c  mov     eax, ebx
0x14008868e  jmp     loc_140088769
0x140088693  mov     rdx, [rbp+hSCObject]; struct SC_HANDLE__ **
0x140088697  lea     r8, aMdcoresvc_0
0x14008869e  mov     r9d, 12h; wchar_t *
0x1400886a4  mov     [rbp+hService], rdi
0x1400886a8  lea     rcx, [rbp+hService]; this
0x1400886ac  call    ?HrOpenService@CommonUtil@@YAJPEAPEAUSC_HANDLE__@@PEAU2@PEB_WK@Z
0x1400886b1  mov     ebx, eax
0x1400886b3  test    eax, eax
0x1400886b5  jns     short loc_1400886F9
0x1400886b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400886be  lea     rdx, WPP_GLOBAL_Control
0x1400886c5  cmp     rcx, rdx
0x1400886c8  jz      short loc_1400886E8
0x1400886ca  test    [rcx+1Ch], sil
0x1400886ce  jz      short loc_1400886E8
0x1400886d0  mov     edx, 0Ch
0x1400886d5  mov     rcx, [rcx+10h]
0x1400886d9  lea     r8, WPP_015d1d1aad8334bf574fd190c463be63_Traceguids
0x1400886e0  mov     r9d, ebx
0x1400886e3  call    WPP_SF_d
0x1400886e8  mov     rcx, [rbp+hService]; hSCObject
0x1400886ec  test    rcx, rcx
0x1400886ef  jz      short loc_14008867D
0x1400886f1  call    cs:__imp_CloseServiceHandle
0x1400886f7  jmp     short loc_14008867D
0x1400886f9  mov     rcx, [rbp+hService]; hService
0x1400886fd  lea     r8, [rbp+Info]; lpInfo
0x140088701  mov     edx, 2; dwInfoLevel
0x140088706  call    cs:__imp_ChangeServiceConfig2W
0x14008870c  test    eax, eax
0x14008870e  jnz     short loc_140088749
0x140088710  call    cs:__imp_GetLastError
0x140088716  mov     ebx, eax
0x140088718  test    eax, eax
0x14008871a  jle     short loc_140088725
0x14008871c  movzx   ebx, ax
0x14008871f  or      ebx, 80070000h
0x140088725  test    ebx, ebx
0x140088727  jns     short loc_140088749
0x140088729  mov     rcx, cs:WPP_GLOBAL_Control
0x140088730  lea     rdx, WPP_GLOBAL_Control
0x140088737  cmp     rcx, rdx
0x14008873a  jz      short loc_1400886E8
0x14008873c  test    [rcx+1Ch], sil
0x140088740  jz      short loc_1400886E8
0x140088742  mov     edx, 0Dh
0x140088747  jmp     short loc_1400886D5
0x140088749  mov     rcx, [rbp+hService]; hSCObject
0x14008874d  test    rcx, rcx
0x140088750  jz      short loc_140088758
0x140088752  call    cs:__imp_CloseServiceHandle
0x140088758  mov     rcx, [rbp+hSCObject]; hSCObject
0x14008875c  test    rcx, rcx
0x14008875f  jz      short loc_140088767
0x140088761  call    cs:__imp_CloseServiceHandle
0x140088767  xor     eax, eax
0x140088769  mov     rcx, [rbp+var_8]
0x14008876d  xor     rcx, rsp; StackCookie
0x140088770  call    __security_check_cookie
0x140088775  lea     r11, [rsp+80h+var_s0]
0x14008877d  mov     rbx, [r11+10h]
0x140088781  mov     rsi, [r11+18h]
0x140088785  mov     rdi, [r11+20h]
0x140088789  mov     rsp, r11
0x14008878c  pop     rbp
0x14008878d  retn
```
