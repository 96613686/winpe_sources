# CAppRecorderPlugin::InvokeCallback(wchar_t const *,_WER_CALLBACK_INPUT *,int *)

- ea: `0x14004d230`
- end: `0x14004d54f`
- name: `?InvokeCallback@CAppRecorderPlugin@@UEAAJPEB_WPEAU_WER_CALLBACK_INPUT@@PEAH@Z`
- size: `799`
- prototype: `__int64 __fastcall(CAppRecorderPlugin *__hidden this, const wchar_t *, struct _WER_CALLBACK_INPUT *, int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140003ac0`
- `0x14001444c`
- `0x140014474`
- `0x1400144b4`
- `0x14004cbac`
- `0x14004d230`
- `0x14004da2c`
- `0x14004dd88`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004d3bb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x14004d3bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004d430`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004d430`
- `wer!WerpSetReportFlags` at `0x14004d331`
- `wer!WerpSetReportFlags` at `0x14004d4b9`
- `wer!WerpSetReportFlags` at `0x14004d331`
- `wer!WerpSetReportFlags` at `0x14004d4b9`
- `wer!WerpGetReportFlags` at `0x14004d2ea`
- `wer!WerpGetReportFlags` at `0x14004d4a2`
- `wer!WerpGetReportFlags` at `0x14004d2ea`
- `wer!WerpGetReportFlags` at `0x14004d4a2`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x14004d422`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x14004d422`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x14004d36f`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x14004d36f`

## string_xrefs

- `0x14004d414`: `Software\Microsoft\Windows\Windows Error Reporting\Plugins\AppRecorder`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CAppRecorderPlugin::InvokeCallback(
        CAppRecorderPlugin *this,
        const wchar_t *a2,
        struct _WER_CALLBACK_INPUT *a3,
        int *a4)
{
  int v7; // eax
  int ReportFlags; // eax
  unsigned int v9; // ebx
  CUserModeHangReport *v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // r9
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v16; // rcx
  int v17; // eax
  signed int LastError; // eax
  unsigned int v19; // [rsp+78h] [rbp+10h] BYREF

  v19 = 0;
  if ( a2 && a3 && a4 )
  {
    *a4 = 0;
    if ( (*((_DWORD *)a3 + 2) == 12 || *((_DWORD *)a3 + 2) == 6) && *((_DWORD *)this + 14) )
    {
      if ( !*((_DWORD *)this + 16) )
      {
        v7 = CAppRecorderPlugin::StopRecordingSession(this, *((_DWORD *)this + 10));
        if ( v7 >= 0 )
        {
          *((_DWORD *)this + 16) = 1;
        }
        else if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            16,
            WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids,
            *((unsigned int *)this + 10),
            v7);
        }
      }
      ReportFlags = WerpGetReportFlags(*(_QWORD *)a3, &v19);
      v9 = ReportFlags;
      if ( ReportFlags < 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          return v9;
        }
        v11 = 17;
        goto LABEL_17;
      }
      v13 = v19;
      v14 = *(_QWORD *)a3;
      v19 |= 0x800u;
      LODWORD(v13) = v19;
      ReportFlags = WerpSetReportFlags(v14, v13);
      v9 = ReportFlags;
      if ( ReportFlags < 0 )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          return v9;
        }
        v11 = 18;
        goto LABEL_17;
      }
    }
    if ( *((_DWORD *)a3 + 2) == 9
      && *((_DWORD *)a3 + 6) == 2
      && (unsigned __int8)IsIsWindowPresent(this, a2)
      && IsWindow(*((HWND *)a3 + 4)) )
    {
      *((_QWORD *)this + 9) = *((_QWORD *)a3 + 4);
      goto LABEL_28;
    }
    if ( *((_DWORD *)a3 + 2) == 1 )
    {
      v16 = *((_QWORD *)a3 + 3);
      if ( v16 )
      {
        if ( *((_QWORD *)a3 + 4) && !(unsigned int)_o__wcsicmp(v16, L"ApplicationRecorder") )
        {
          if ( *((_DWORD *)this + 14) )
          {
            v17 = CAppRecorderPlugin::RemoveAppCompatLayer(this);
            v9 = v17;
            if ( v17 >= 0 )
            {
              if ( !RegDeleteKeyW(
                      HKEY_CURRENT_USER,
                      L"Software\\Microsoft\\Windows\\Windows Error Reporting\\Plugins\\AppRecorder") )
                goto LABEL_28;
              LastError = GetLastError();
              v9 = LastError;
              if ( LastError > 0 )
                v9 = (unsigned __int16)LastError | 0x80070000;
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids, v9);
                v10 = WPP_GLOBAL_Control;
              }
              if ( (v9 & 0x80000000) == 0 )
                goto LABEL_28;
            }
            else
            {
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control )
                return v9;
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  21,
                  WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids,
                  (unsigned int)v17);
                v10 = WPP_GLOBAL_Control;
              }
            }
            if ( v10 == (CUserModeHangReport *)&WPP_GLOBAL_Control || (*((_BYTE *)v10 + 28) & 1) == 0 )
              return v9;
            v11 = 19;
            v12 = v9;
            goto LABEL_18;
          }
          if ( (int)WerpGetReportFlags(*(_QWORD *)a3, &v19) >= 0 )
            WerpSetReportFlags(*(_QWORD *)a3, v19 | 0x48000000);
          if ( !*((_DWORD *)this + 15) )
          {
            ReportFlags = CAppRecorderPlugin::EnableAppRecorder(this, *((const wchar_t **)a3 + 4), *(void **)a3);
            v9 = ReportFlags;
            if ( ReportFlags < 0 )
            {
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                return v9;
              }
              v11 = 20;
LABEL_17:
              v12 = (unsigned int)ReportFlags;
LABEL_18:
              WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids, v12);
              return v9;
            }
          }
LABEL_28:
          v9 = 0;
          *a4 = 1;
          return v9;
        }
      }
    }
    return 2147500033LL;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids);
    }
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x14004d230  push    rbx
0x14004d232  push    rbp
0x14004d233  push    rdi
0x14004d234  push    r12
0x14004d236  push    r14
0x14004d238  push    r15
0x14004d23a  sub     rsp, 38h
0x14004d23e  mov     [rsp+68h+arg_8], 0
0x14004d246  mov     r12, r9
0x14004d249  mov     rdi, r8
0x14004d24c  mov     r14, rcx
0x14004d24f  test    rdx, rdx
0x14004d252  jz      loc_14004D50E
0x14004d258  test    r8, r8
0x14004d25b  jz      loc_14004D50E
0x14004d261  test    r9, r9
0x14004d264  jz      loc_14004D50E
0x14004d26a  mov     dword ptr [r9], 0
0x14004d271  lea     rbp, WPP_GLOBAL_Control
0x14004d278  cmp     dword ptr [r8+8], 0Ch
0x14004d27d  lea     r15, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x14004d284  jz      short loc_14004D291
0x14004d286  cmp     dword ptr [r8+8], 6
0x14004d28b  jnz     loc_14004D356
0x14004d291  cmp     dword ptr [rcx+38h], 0
0x14004d295  jz      loc_14004D356
0x14004d29b  cmp     dword ptr [rcx+40h], 0
0x14004d29f  jnz     short loc_14004D2E2
0x14004d2a1  mov     edx, [rcx+28h]; unsigned int
0x14004d2a4  call    ?StopRecordingSession@CAppRecorderPlugin@@AEAAJK@Z; CAppRecorderPlugin::StopRecordingSession(ulong)
0x14004d2a9  test    eax, eax
0x14004d2ab  jns     short loc_14004D2DA
0x14004d2ad  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d2b4  cmp     rcx, rbp
0x14004d2b7  jz      short loc_14004D2E2
0x14004d2b9  test    byte ptr [rcx+1Ch], 2
0x14004d2bd  jz      short loc_14004D2E2
0x14004d2bf  mov     r9d, [r14+28h]
0x14004d2c3  mov     edx, 10h
0x14004d2c8  mov     rcx, [rcx+10h]
0x14004d2cc  mov     r8, r15
0x14004d2cf  mov     [rsp+68h+var_48], eax
0x14004d2d3  call    WPP_SF_Dd
0x14004d2d8  jmp     short loc_14004D2E2
0x14004d2da  mov     dword ptr [r14+40h], 1
0x14004d2e2  mov     rcx, [rdi]
0x14004d2e5  lea     rdx, [rsp+68h+arg_8]
0x14004d2ea  call    cs:__imp_WerpGetReportFlags
0x14004d2f0  mov     ebx, eax
0x14004d2f2  test    eax, eax
0x14004d2f4  jns     short loc_14004D322
0x14004d2f6  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d2fd  cmp     rcx, rbp
0x14004d300  jz      loc_14004D38B
0x14004d306  test    byte ptr [rcx+1Ch], 1
0x14004d30a  jz      short loc_14004D38B
0x14004d30c  mov     edx, 11h
0x14004d311  mov     r9d, eax
0x14004d314  mov     rcx, [rcx+10h]
0x14004d318  mov     r8, r15
0x14004d31b  call    WPP_SF_d
0x14004d320  jmp     short loc_14004D38B
0x14004d322  mov     edx, [rsp+68h+arg_8]
0x14004d326  mov     rcx, [rdi]
0x14004d329  bts     edx, 0Bh
0x14004d32d  mov     [rsp+68h+arg_8], edx
0x14004d331  call    cs:__imp_WerpSetReportFlags
0x14004d337  mov     ebx, eax
0x14004d339  test    eax, eax
0x14004d33b  jns     short loc_14004D356
0x14004d33d  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d344  cmp     rcx, rbp
0x14004d347  jz      short loc_14004D38B
0x14004d349  test    byte ptr [rcx+1Ch], 1
0x14004d34d  jz      short loc_14004D38B
0x14004d34f  mov     edx, 12h
0x14004d354  jmp     short loc_14004D311
0x14004d356  cmp     dword ptr [rdi+8], 9
0x14004d35a  jnz     short loc_14004D392
0x14004d35c  cmp     dword ptr [rdi+18h], 2
0x14004d360  jnz     short loc_14004D392
0x14004d362  call    IsIsWindowPresent
0x14004d367  test    al, al
0x14004d369  jz      short loc_14004D392
0x14004d36b  mov     rcx, [rdi+20h]; hWnd
0x14004d36f  call    cs:__imp_IsWindow
0x14004d375  test    eax, eax
0x14004d377  jz      short loc_14004D392
0x14004d379  mov     rax, [rdi+20h]
0x14004d37d  mov     [r14+48h], rax
0x14004d381  xor     ebx, ebx
0x14004d383  mov     dword ptr [r12], 1
0x14004d38b  mov     eax, ebx
0x14004d38d  jmp     loc_14004D541
0x14004d392  cmp     dword ptr [rdi+8], 1
0x14004d396  jnz     loc_14004D507
0x14004d39c  mov     rcx, [rdi+18h]
0x14004d3a0  test    rcx, rcx
0x14004d3a3  jz      loc_14004D507
0x14004d3a9  cmp     qword ptr [rdi+20h], 0
0x14004d3ae  jz      loc_14004D507
0x14004d3b4  lea     rdx, aApplicationrec; "ApplicationRecorder"
0x14004d3bb  call    cs:__imp__o__wcsicmp
0x14004d3c1  test    eax, eax
0x14004d3c3  jnz     loc_14004D507
0x14004d3c9  cmp     [r14+38h], eax
0x14004d3cd  jz      loc_14004D49A
0x14004d3d3  mov     rcx, r14; this
0x14004d3d6  call    ?RemoveAppCompatLayer@CAppRecorderPlugin@@AEAAJXZ; CAppRecorderPlugin::RemoveAppCompatLayer(void)
0x14004d3db  mov     ebx, eax
0x14004d3dd  test    eax, eax
0x14004d3df  jns     short loc_14004D414
0x14004d3e1  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d3e8  cmp     rcx, rbp
0x14004d3eb  jz      short loc_14004D38B
0x14004d3ed  test    byte ptr [rcx+1Ch], 1
0x14004d3f1  jz      loc_14004D47A
0x14004d3f7  mov     rcx, [rcx+10h]
0x14004d3fb  mov     edx, 15h
0x14004d400  mov     r9d, eax
0x14004d403  mov     r8, r15
0x14004d406  call    WPP_SF_d
0x14004d40b  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d412  jmp     short loc_14004D47A
0x14004d414  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\Windows\\Windows E"...
0x14004d41b  mov     rcx, 0FFFFFFFF80000001h; hKey
0x14004d422  call    cs:__imp_RegDeleteKeyW
0x14004d428  test    eax, eax
0x14004d42a  jz      loc_14004D381
0x14004d430  call    cs:__imp_GetLastError
0x14004d436  mov     ebx, eax
0x14004d438  test    eax, eax
0x14004d43a  jle     short loc_14004D445
0x14004d43c  movzx   ebx, ax
0x14004d43f  or      ebx, 80070000h
0x14004d445  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d44c  cmp     rcx, rbp
0x14004d44f  jz      short loc_14004D472
0x14004d451  test    byte ptr [rcx+1Ch], 4
0x14004d455  jz      short loc_14004D472
0x14004d457  mov     rcx, [rcx+10h]
0x14004d45b  mov     edx, 16h
0x14004d460  mov     r9d, ebx
0x14004d463  mov     r8, r15
0x14004d466  call    WPP_SF_d
0x14004d46b  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d472  test    ebx, ebx
0x14004d474  jns     loc_14004D381
0x14004d47a  cmp     rcx, rbp
0x14004d47d  jz      loc_14004D38B
0x14004d483  test    byte ptr [rcx+1Ch], 1
0x14004d487  jz      loc_14004D38B
0x14004d48d  mov     edx, 13h
0x14004d492  mov     r9d, ebx
0x14004d495  jmp     loc_14004D314
0x14004d49a  mov     rcx, [rdi]
0x14004d49d  lea     rdx, [rsp+68h+arg_8]
0x14004d4a2  call    cs:__imp_WerpGetReportFlags
0x14004d4a8  test    eax, eax
0x14004d4aa  js      short loc_14004D4BF
0x14004d4ac  mov     edx, [rsp+68h+arg_8]
0x14004d4b0  mov     rcx, [rdi]
0x14004d4b3  or      edx, 48000000h
0x14004d4b9  call    cs:__imp_WerpSetReportFlags
0x14004d4bf  cmp     dword ptr [r14+3Ch], 0
0x14004d4c4  jnz     loc_14004D381
0x14004d4ca  mov     r8, [rdi]; void *
0x14004d4cd  mov     rcx, r14; this
0x14004d4d0  mov     rdx, [rdi+20h]; wchar_t *
0x14004d4d4  call    ?EnableAppRecorder@CAppRecorderPlugin@@AEAAJPEB_WPEAX@Z; CAppRecorderPlugin::EnableAppRecorder(wchar_t const *,void *)
0x14004d4d9  mov     ebx, eax
0x14004d4db  test    eax, eax
0x14004d4dd  jns     loc_14004D381
0x14004d4e3  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d4ea  cmp     rcx, rbp
0x14004d4ed  jz      loc_14004D38B
0x14004d4f3  test    byte ptr [rcx+1Ch], 1
0x14004d4f7  jz      loc_14004D38B
0x14004d4fd  mov     edx, 14h
0x14004d502  jmp     loc_14004D311
0x14004d507  mov     eax, 80004001h
0x14004d50c  jmp     short loc_14004D541
0x14004d50e  mov     rcx, cs:WPP_GLOBAL_Control
0x14004d515  lea     rbp, WPP_GLOBAL_Control
0x14004d51c  cmp     rcx, rbp
0x14004d51f  jz      short loc_14004D53C
0x14004d521  test    byte ptr [rcx+1Ch], 1
0x14004d525  jz      short loc_14004D53C
0x14004d527  mov     rcx, [rcx+10h]
0x14004d52b  lea     r8, WPP_59716befc9b73f80870fd6b78a9fc400_Traceguids
0x14004d532  mov     edx, 0Fh
0x14004d537  call    WPP_SF_
0x14004d53c  mov     eax, 80070057h
0x14004d541  add     rsp, 38h
0x14004d545  pop     r15
0x14004d547  pop     r14
0x14004d549  pop     r12
0x14004d54b  pop     rdi
0x14004d54c  pop     rbp
0x14004d54d  pop     rbx
0x14004d54e  retn
```
