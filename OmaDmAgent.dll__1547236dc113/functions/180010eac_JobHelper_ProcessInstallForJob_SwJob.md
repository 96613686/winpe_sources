# JobHelper::ProcessInstallForJob(_SwJob)

- ea: `0x180010eac`
- end: `0x180011090`
- name: `?ProcessInstallForJob@JobHelper@@QEAAJU_SwJob@@@Z`
- size: `484`
- prototype: `int __high(struct _SwJob)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update`

## callers

- `0x180010700`

## callees

- `0x1800065f8`
- `0x18000702c`
- `0x18000a290`
- `0x18000b7d8`
- `0x18000bd00`
- `0x18000ccb4`
- `0x18000e980`
- `0x180010eac`
- `0x180012338`
- `0x1800182b4`
- `0x180019f78`
- `0x18001f420`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall JobHelper::ProcessInstallForJob(__int64 a1, const struct _SwJob *a2)
{
  int WebLink; // r15d
  _SwJob *v5; // rax
  _SwJob *v6; // rax
  JobHelper *v7; // rcx
  unsigned __int16 *v8; // rsi
  _BYTE *v9; // rcx
  _SwJob *v10; // rax
  JobHelper *v11; // rcx
  unsigned int v12; // ebx
  int v13; // edi
  _QWORD *v14; // rax
  _BYTE v16[32]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v17[32]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v18[320]; // [rsp+80h] [rbp-80h] BYREF
  const struct _SwJob *v19; // [rsp+1C0h] [rbp+C0h]

  v19 = a2;
  WebLink = 0;
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 147, &WPP_9f155fbe94773387205a22e9edb85311_Traceguids);
  if ( *((_DWORD *)a2 + 17) != 1 )
  {
    if ( *((_DWORD *)a2 + 17) == 2 )
    {
      v6 = _SwJob::_SwJob((_SwJob *)v18, a2);
      WebLink = WebAppUtil::CreateWebLink(v6);
      if ( WebLink >= 0 )
      {
        *((_DWORD *)a2 + 24) = 70;
        *((_DWORD *)a2 + 26) = 0;
        std::wstring::assign((char *)a2 + 112, &dword_180022F6C);
      }
      else
      {
        *((_DWORD *)a2 + 24) = 60;
        JobHelper::GetErrorMessage(v7, a2);
      }
      v8 = (unsigned __int16 *)std::wstring::wstring(v16, (char *)a2 + 112);
      v9 = v17;
    }
    else
    {
      if ( *((_DWORD *)a2 + 17) != 3 )
        goto LABEL_17;
      v10 = _SwJob::_SwJob((_SwJob *)v18, a2);
      WebLink = RemoteAppUtil::InstallRemoteApp(v10);
      if ( WebLink >= 0 )
      {
        *((_DWORD *)a2 + 24) = 70;
        *((_DWORD *)a2 + 26) = 0;
        std::wstring::assign((char *)a2 + 112, &dword_180022F6C);
      }
      else
      {
        *((_DWORD *)a2 + 24) = 60;
        JobHelper::GetErrorMessage(v11, a2);
      }
      v8 = (unsigned __int16 *)std::wstring::wstring(v17, (char *)a2 + 112);
      v9 = v16;
    }
    v12 = *((_DWORD *)a2 + 26);
    v13 = *((_DWORD *)a2 + 24);
    v14 = (_QWORD *)std::wstring::wstring(v9, a2);
    JobHelper::UpdateProgress(a1, v14, v13, 0, v12, v8);
    goto LABEL_17;
  }
  v5 = _SwJob::_SwJob((_SwJob *)v18, a2);
  JobHelper::DoDownload(a1, v5);
LABEL_17:
  _SwJob::~_SwJob(a2);
  return (unsigned int)WebLink;
}

```

## disassembly

```asm
0x180010eac  mov     [rsp-8+arg_10], rbx
0x180010eb1  mov     [rsp-8+arg_18], rsi
0x180010eb6  push    rbp
0x180010eb7  push    rdi
0x180010eb8  push    r12
0x180010eba  push    r14
0x180010ebc  push    r15
0x180010ebe  lea     rbp, [rsp-0D0h]
0x180010ec6  sub     rsp, 1D0h
0x180010ecd  mov     rax, cs:__security_cookie
0x180010ed4  xor     rax, rsp
0x180010ed7  mov     [rbp+0F0h+var_28], rax
0x180010ede  mov     r14, rdx
0x180010ee1  mov     r12, rcx
0x180010ee4  mov     [rbp+0F0h+var_30], rdx
0x180010eeb  xor     r15d, r15d
0x180010eee  lea     rax, WPP_GLOBAL_Control
0x180010ef5  mov     rcx, cs:WPP_GLOBAL_Control
0x180010efc  cmp     rcx, rax
0x180010eff  jz      short loc_180010F1C
0x180010f01  test    byte ptr [rcx+1Ch], 1
0x180010f05  jz      short loc_180010F1C
0x180010f07  mov     edx, 93h
0x180010f0c  lea     r8, WPP_9f155fbe94773387205a22e9edb85311_Traceguids
0x180010f13  mov     rcx, [rcx+10h]
0x180010f17  call    WPP_SF_
0x180010f1c  cmp     dword ptr [r14+44h], 1
0x180010f21  jnz     short loc_180010F3F
0x180010f23  mov     rdx, r14; struct _SwJob *
0x180010f26  lea     rcx, [rbp+0F0h+var_170]; this
0x180010f2a  call    ??0_SwJob@@QEAA@AEBU0@@Z; _SwJob::_SwJob(_SwJob const &)
0x180010f2f  mov     rdx, rax
0x180010f32  mov     rcx, r12
0x180010f35  call    ?DoDownload@JobHelper@@AEAAJU_SwJob@@@Z; JobHelper::DoDownload(_SwJob)
0x180010f3a  jmp     loc_180011059
0x180010f3f  cmp     dword ptr [r14+44h], 2
0x180010f44  jnz     short loc_180010FB5
0x180010f46  mov     rdx, r14; struct _SwJob *
0x180010f49  lea     rcx, [rbp+0F0h+var_170]; this
0x180010f4d  call    ??0_SwJob@@QEAA@AEBU0@@Z; _SwJob::_SwJob(_SwJob const &)
0x180010f52  mov     rcx, rax
0x180010f55  call    ?CreateWebLink@WebAppUtil@@SAJU_SwJob@@@Z; WebAppUtil::CreateWebLink(_SwJob)
0x180010f5a  mov     r15d, eax
0x180010f5d  test    eax, eax
0x180010f5f  jns     short loc_180010F73
0x180010f61  mov     dword ptr [r14+60h], 3Ch ; '<'
0x180010f69  mov     rdx, r14; struct _SwJob *
0x180010f6c  call    ?GetErrorMessage@JobHelper@@AEAAXAEAU_SwJob@@@Z; JobHelper::GetErrorMessage(_SwJob &)
0x180010f71  jmp     short loc_180010F93
0x180010f73  mov     dword ptr [r14+60h], 46h ; 'F'
0x180010f7b  mov     dword ptr [r14+68h], 0
0x180010f83  lea     rcx, [r14+70h]
0x180010f87  lea     rdx, dword_180022F6C
0x180010f8e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180010f93  lea     rax, [rsp+1F0h+var_1B0]
0x180010f98  mov     [rsp+1F0h+var_1C0], rax
0x180010f9d  lea     rdx, [r14+70h]
0x180010fa1  lea     rcx, [rsp+1F0h+var_1B0]
0x180010fa6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180010fab  mov     rsi, rax
0x180010fae  lea     rcx, [rsp+1F0h+var_190]
0x180010fb3  jmp     short loc_18001102D
0x180010fb5  cmp     dword ptr [r14+44h], 3
0x180010fba  jnz     loc_180011059
0x180010fc0  mov     rdx, r14; struct _SwJob *
0x180010fc3  lea     rcx, [rbp+0F0h+var_170]; this
0x180010fc7  call    ??0_SwJob@@QEAA@AEBU0@@Z; _SwJob::_SwJob(_SwJob const &)
0x180010fcc  mov     rcx, rax
0x180010fcf  call    ?InstallRemoteApp@RemoteAppUtil@@SAJU_SwJob@@@Z; RemoteAppUtil::InstallRemoteApp(_SwJob)
0x180010fd4  mov     r15d, eax
0x180010fd7  test    eax, eax
0x180010fd9  jns     short loc_180010FED
0x180010fdb  mov     dword ptr [r14+60h], 3Ch ; '<'
0x180010fe3  mov     rdx, r14; struct _SwJob *
0x180010fe6  call    ?GetErrorMessage@JobHelper@@AEAAXAEAU_SwJob@@@Z; JobHelper::GetErrorMessage(_SwJob &)
0x180010feb  jmp     short loc_18001100D
0x180010fed  mov     dword ptr [r14+60h], 46h ; 'F'
0x180010ff5  mov     dword ptr [r14+68h], 0
0x180010ffd  lea     rcx, [r14+70h]
0x180011001  lea     rdx, dword_180022F6C
0x180011008  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18001100d  lea     rax, [rsp+1F0h+var_190]
0x180011012  mov     [rsp+1F0h+var_1B8], rax
0x180011017  lea     rdx, [r14+70h]
0x18001101b  lea     rcx, [rsp+1F0h+var_190]
0x180011020  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180011025  mov     rsi, rax
0x180011028  lea     rcx, [rsp+1F0h+var_1B0]
0x18001102d  mov     ebx, [r14+68h]
0x180011031  mov     edi, [r14+60h]
0x180011035  mov     rdx, r14
0x180011038  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001103d  nop
0x18001103e  mov     [rsp+1F0h+var_1C8], rsi
0x180011043  mov     [rsp+1F0h+var_1D0], ebx
0x180011047  xor     r9d, r9d
0x18001104a  mov     r8d, edi
0x18001104d  mov     rdx, rax
0x180011050  mov     rcx, r12
0x180011053  call    ?UpdateProgress@JobHelper@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4JobStatus@@KK0@Z; JobHelper::UpdateProgress(std::wstring,JobStatus,ulong,ulong,std::wstring)
0x180011058  nop
0x180011059  mov     rcx, r14; this
0x18001105c  call    ??1_SwJob@@QEAA@XZ; _SwJob::~_SwJob(void)
0x180011061  mov     eax, r15d
0x180011064  mov     rcx, [rbp+0F0h+var_28]
0x18001106b  xor     rcx, rsp; StackCookie
0x18001106e  call    __security_check_cookie
0x180011073  lea     r11, [rsp+1F0h+var_20]
0x18001107b  mov     rbx, [r11+40h]
0x18001107f  mov     rsi, [r11+48h]
0x180011083  mov     rsp, r11
0x180011086  pop     r15
0x180011088  pop     r14
0x18001108a  pop     r12
0x18001108c  pop     rdi
0x18001108d  pop     rbp
0x18001108e  retn
```
