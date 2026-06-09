# CInstallService::StartDeployments(void)

- ea: `0x180017b58`
- end: `0x180017dbd`
- name: `?StartDeployments@CInstallService@@QEAAJXZ`
- size: `613`
- prototype: `__int64 __fastcall(CInstallService *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180010700`

## callees

- `0x180002a50`
- `0x18000702c`
- `0x18000a290`
- `0x18000a440`
- `0x18000b51c`
- `0x18000bbf8`
- `0x18000f8e4`
- `0x180012338`
- `0x1800169b8`
- `0x180017378`
- `0x1800179a8`
- `0x180017b58`
- `0x18001f420`
- `0x180021010`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CInstallService::StartDeployments(CInstallService *this)
{
  signed int v2; // esi
  struct JobHelper *JobHelper; // r15
  _QWORD *v4; // rbx
  __int64 v5; // rdi
  __int64 *v6; // rax
  _QWORD *v7; // r8
  _QWORD *v8; // r9
  unsigned __int16 *v9; // rdi
  _QWORD *v10; // rax
  int v11; // r8d
  __int64 v12; // rdi
  __int64 *v13; // rax
  _QWORD *v14; // rax
  _QWORD *v15; // r9
  __int64 v16; // rcx
  _QWORD v18[3]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v19[32]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v20[32]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v21[136]; // [rsp+88h] [rbp-78h] BYREF
  _DWORD v22[6]; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int64 v23; // [rsp+128h] [rbp+28h]
  _QWORD v24[3]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int64 v25; // [rsp+168h] [rbp+68h]
  int v26; // [rsp+170h] [rbp+70h]

  v2 = 0;
  if ( !*((_QWORD *)this + 1) )
    return (unsigned int)v2;
  JobHelper = JobHelper::GetJobHelper();
  v4 = *(_QWORD **)this;
  while ( 1 )
  {
    v4 = (_QWORD *)*v4;
    if ( v4 == *(_QWORD **)this )
      break;
    _DeployJob::_DeployJob((_DeployJob *)v22, (const struct _DeployJob *)(v4 + 2));
    Microsoft::WRL::Details::Make<DeploymentProgressHandler,>(v18);
    if ( ((v26 - 1) & 0xFFFFFFFD) != 0 )
    {
      if ( v26 != 2 )
        goto LABEL_25;
      v5 = v18[0];
      v6 = (__int64 *)_DeployJob::_DeployJob((_DeployJob *)v21, (const struct _DeployJob *)v22);
      v2 = RemovePackage(v6, v5);
      if ( v2 >= 0 )
        goto LABEL_25;
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      {
        v7 = v24;
        if ( v25 >= 8 )
          v7 = (_QWORD *)v24[0];
        v8 = v22;
        if ( v23 >= 8 )
          LODWORD(v8) = v22[0];
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          (unsigned int)WPP_b012fd7b767137dc7a4deb8381d88d18_Traceguids,
          (_DWORD)v8,
          (__int64)v7);
      }
      v18[1] = v19;
      v9 = (unsigned __int16 *)std::wstring::wstring(v19, &dword_180022F6C);
      v10 = (_QWORD *)std::wstring::wstring(v20, v22);
      v11 = 90;
    }
    else
    {
      v12 = v18[0];
      v13 = (__int64 *)_DeployJob::_DeployJob((_DeployJob *)v21, (const struct _DeployJob *)v22);
      v2 = InstallPackage(v13, v12);
      if ( v2 >= 0 )
        goto LABEL_25;
      if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      {
        v14 = v24;
        if ( v25 >= 8 )
          v14 = (_QWORD *)v24[0];
        v15 = v22;
        if ( v23 >= 8 )
          LODWORD(v15) = v22[0];
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          (unsigned int)WPP_b012fd7b767137dc7a4deb8381d88d18_Traceguids,
          (_DWORD)v15,
          (__int64)v14);
      }
      v18[2] = v20;
      v9 = (unsigned __int16 *)std::wstring::wstring(v20, &dword_180022F6C);
      v10 = (_QWORD *)std::wstring::wstring(v19, v22);
      v11 = 60;
    }
    JobHelper::UpdateProgress((__int64)JobHelper, v10, v11, 0, v2, v9);
LABEL_25:
    v16 = v18[0];
    if ( v18[0] )
    {
      v18[0] = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    _DeployJob::~_DeployJob((_DeployJob *)v22);
  }
  if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_b012fd7b767137dc7a4deb8381d88d18_Traceguids);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180017b58  push    rbp
0x180017b5a  push    rbx
0x180017b5b  push    rsi
0x180017b5c  push    rdi
0x180017b5d  push    r12
0x180017b5f  push    r14
0x180017b61  push    r15
0x180017b63  lea     rbp, [rsp-0A0h]
0x180017b6b  sub     rsp, 1A0h
0x180017b72  mov     rax, cs:__security_cookie
0x180017b79  xor     rax, rsp
0x180017b7c  mov     [rbp+0D0h+var_40], rax
0x180017b83  mov     r14, rcx
0x180017b86  xor     esi, esi
0x180017b88  cmp     [rcx+8], rsi
0x180017b8c  jz      loc_180017D99
0x180017b92  call    ?GetJobHelper@JobHelper@@SAPEAV1@XZ; JobHelper::GetJobHelper(void)
0x180017b97  mov     r15, rax
0x180017b9a  mov     rbx, [r14]
0x180017b9d  lea     r12, WPP_GLOBAL_Control
0x180017ba4  mov     rbx, [rbx]
0x180017ba7  cmp     rbx, [r14]
0x180017baa  jz      loc_180017D72
0x180017bb0  lea     rdx, [rbx+10h]; struct _DeployJob *
0x180017bb4  lea     rcx, [rbp+0D0h+var_C0]; this
0x180017bb8  call    ??0_DeployJob@@QEAA@AEBU0@@Z; _DeployJob::_DeployJob(_DeployJob const &)
0x180017bbd  nop
0x180017bbe  lea     rcx, [rsp+1D0h+var_1A0]
0x180017bc3  call    ??$Make@VDeploymentProgressHandler@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VDeploymentProgressHandler@@@12@XZ; Microsoft::WRL::Details::Make<DeploymentProgressHandler,>(void)
0x180017bc8  nop
0x180017bc9  mov     ecx, [rbp+0D0h+var_60]
0x180017bcc  lea     eax, [rcx-1]
0x180017bcf  test    eax, 0FFFFFFFDh
0x180017bd4  jz      loc_180017C8A
0x180017bda  cmp     ecx, 2
0x180017bdd  jnz     loc_180017D44
0x180017be3  mov     rdi, [rsp+1D0h+var_1A0]
0x180017be8  lea     rdx, [rbp+0D0h+var_C0]; struct _DeployJob *
0x180017bec  lea     rcx, [rbp+0D0h+var_148]; this
0x180017bf0  call    ??0_DeployJob@@QEAA@AEBU0@@Z; _DeployJob::_DeployJob(_DeployJob const &)
0x180017bf5  mov     rdx, rdi
0x180017bf8  mov     rcx, rax
0x180017bfb  call    ?RemovePackage@@YAJU_DeployJob@@PEAVDeploymentProgressHandler@@@Z; RemovePackage(_DeployJob,DeploymentProgressHandler *)
0x180017c00  mov     esi, eax
0x180017c02  test    eax, eax
0x180017c04  jns     loc_180017D44
0x180017c0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180017c11  cmp     rcx, r12
0x180017c14  jz      short loc_180017C52
0x180017c16  test    byte ptr [rcx+1Ch], 4
0x180017c1a  jz      short loc_180017C52
0x180017c1c  lea     r8, [rbp+0D0h+var_80]
0x180017c20  cmp     [rbp+0D0h+var_68], 8
0x180017c25  cmovnb  r8, [rbp+0D0h+var_80]
0x180017c2a  lea     r9, [rbp+0D0h+var_C0]
0x180017c2e  cmp     [rbp+0D0h+var_A8], 8
0x180017c33  cmovnb  r9, qword ptr [rbp+0D0h+var_C0]
0x180017c38  mov     edx, 0Bh
0x180017c3d  mov     [rsp+1D0h+var_1B0], r8
0x180017c42  lea     r8, WPP_b012fd7b767137dc7a4deb8381d88d18_Traceguids
0x180017c49  mov     rcx, [rcx+10h]
0x180017c4d  call    WPP_SF_SS
0x180017c52  lea     rax, [rsp+1D0h+var_188]
0x180017c57  mov     [rsp+1D0h+var_198], rax
0x180017c5c  lea     rdx, dword_180022F6C
0x180017c63  lea     rcx, [rsp+1D0h+var_188]
0x180017c68  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180017c6d  mov     rdi, rax
0x180017c70  lea     rdx, [rbp+0D0h+var_C0]
0x180017c74  lea     rcx, [rsp+1D0h+var_168]
0x180017c79  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180017c7e  nop
0x180017c7f  mov     r8d, 5Ah ; 'Z'
0x180017c85  jmp     loc_180017D2C
0x180017c8a  mov     rdi, [rsp+1D0h+var_1A0]
0x180017c8f  lea     rdx, [rbp+0D0h+var_C0]; struct _DeployJob *
0x180017c93  lea     rcx, [rbp+0D0h+var_148]; this
0x180017c97  call    ??0_DeployJob@@QEAA@AEBU0@@Z; _DeployJob::_DeployJob(_DeployJob const &)
0x180017c9c  mov     rdx, rdi
0x180017c9f  mov     rcx, rax
0x180017ca2  call    ?InstallPackage@@YAJU_DeployJob@@PEAVDeploymentProgressHandler@@@Z; InstallPackage(_DeployJob,DeploymentProgressHandler *)
0x180017ca7  mov     esi, eax
0x180017ca9  test    eax, eax
0x180017cab  jns     loc_180017D44
0x180017cb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180017cb8  cmp     rcx, r12
0x180017cbb  jz      short loc_180017CF9
0x180017cbd  test    byte ptr [rcx+1Ch], 4
0x180017cc1  jz      short loc_180017CF9
0x180017cc3  lea     rax, [rbp+0D0h+var_80]
0x180017cc7  cmp     [rbp+0D0h+var_68], 8
0x180017ccc  cmovnb  rax, [rbp+0D0h+var_80]
0x180017cd1  lea     r9, [rbp+0D0h+var_C0]
0x180017cd5  cmp     [rbp+0D0h+var_A8], 8
0x180017cda  cmovnb  r9, qword ptr [rbp+0D0h+var_C0]
0x180017cdf  mov     edx, 0Ah
0x180017ce4  mov     [rsp+1D0h+var_1B0], rax
0x180017ce9  lea     r8, WPP_b012fd7b767137dc7a4deb8381d88d18_Traceguids
0x180017cf0  mov     rcx, [rcx+10h]
0x180017cf4  call    WPP_SF_SS
0x180017cf9  lea     rax, [rsp+1D0h+var_168]
0x180017cfe  mov     [rsp+1D0h+var_190], rax
0x180017d03  lea     rdx, dword_180022F6C
0x180017d0a  lea     rcx, [rsp+1D0h+var_168]
0x180017d0f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x180017d14  mov     rdi, rax
0x180017d17  lea     rdx, [rbp+0D0h+var_C0]
0x180017d1b  lea     rcx, [rsp+1D0h+var_188]
0x180017d20  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180017d25  nop
0x180017d26  mov     r8d, 3Ch ; '<'
0x180017d2c  mov     [rsp+1D0h+var_1A8], rdi
0x180017d31  mov     dword ptr [rsp+1D0h+var_1B0], esi
0x180017d35  xor     r9d, r9d
0x180017d38  mov     rdx, rax
0x180017d3b  mov     rcx, r15
0x180017d3e  call    ?UpdateProgress@JobHelper@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4JobStatus@@KK0@Z; JobHelper::UpdateProgress(std::wstring,JobStatus,ulong,ulong,std::wstring)
0x180017d43  nop
0x180017d44  mov     rcx, [rsp+1D0h+var_1A0]
0x180017d49  test    rcx, rcx
0x180017d4c  jz      short loc_180017D64
0x180017d4e  mov     [rsp+1D0h+var_1A0], 0
0x180017d57  mov     rax, [rcx]
0x180017d5a  mov     rax, [rax+10h]
0x180017d5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017d63  nop
0x180017d64  lea     rcx, [rbp+0D0h+var_C0]; this
0x180017d68  call    ??1_DeployJob@@QEAA@XZ; _DeployJob::~_DeployJob(void)
0x180017d6d  jmp     loc_180017BA4
0x180017d72  mov     rcx, cs:WPP_GLOBAL_Control
0x180017d79  cmp     rcx, r12
0x180017d7c  jz      short loc_180017D99
0x180017d7e  test    byte ptr [rcx+1Ch], 1
0x180017d82  jz      short loc_180017D99
0x180017d84  mov     edx, 0Ch
0x180017d89  lea     r8, WPP_b012fd7b767137dc7a4deb8381d88d18_Traceguids
0x180017d90  mov     rcx, [rcx+10h]
0x180017d94  call    WPP_SF_
0x180017d99  mov     eax, esi
0x180017d9b  mov     rcx, [rbp+0D0h+var_40]
0x180017da2  xor     rcx, rsp; StackCookie
0x180017da5  call    __security_check_cookie
0x180017daa  add     rsp, 1A0h
0x180017db1  pop     r15
0x180017db3  pop     r14
0x180017db5  pop     r12
0x180017db7  pop     rdi
0x180017db8  pop     rsi
0x180017db9  pop     rbx
0x180017dba  pop     rbp
0x180017dbb  retn
```
