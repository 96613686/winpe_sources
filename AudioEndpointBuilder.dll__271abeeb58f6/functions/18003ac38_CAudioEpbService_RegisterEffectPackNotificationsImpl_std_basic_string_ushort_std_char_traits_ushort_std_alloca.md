# CAudioEpbService::RegisterEffectPackNotificationsImpl(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18003ac38`
- end: `0x18003af12`
- name: `?RegisterEffectPackNotificationsImpl@CAudioEpbService@@QEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `730`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x180046010`

## callees

- `0x180010da8`
- `0x18003512c`
- `0x18003514c`
- `0x18003ac38`
- `0x18003e920`

## import_xrefs

- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x18003adc9`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x18003aee1`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x18003adc9`
- `api-ms-win-devices-query-l1-1-0!DevCreateObjectQuery` at `0x18003aee1`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x18003ad83`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x18003ae99`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x18003ad83`
- `api-ms-win-devices-query-l1-1-0!DevCloseObjectQuery` at `0x18003ae99`

## string_xrefs

- `0x18003addc`: `avcore\audiocore\server\audioendpointbuilder\dll\audioepbservice.cpp`

## pseudocode

```c
__int64 __fastcall CAudioEpbService::RegisterEffectPackNotificationsImpl(__int64 a1, __int64 *a2)
{
  bool v2; // cc
  int v4; // eax
  _QWORD *v5; // rbx
  __int64 v6; // rdi
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v10; // rdi
  int v11; // [rsp+20h] [rbp-E0h]
  char v12; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v13[8]; // [rsp+58h] [rbp-A8h] BYREF
  DEVPROPKEY v14; // [rsp+60h] [rbp-A0h] BYREF
  int v15; // [rsp+74h] [rbp-8Ch]
  __int64 v16; // [rsp+78h] [rbp-88h]
  DEVPROPKEY v17; // [rsp+80h] [rbp-80h] BYREF
  int v18; // [rsp+94h] [rbp-6Ch]
  __int64 v19; // [rsp+98h] [rbp-68h]
  int v20; // [rsp+A0h] [rbp-60h] BYREF
  DEVPROPKEY v21; // [rsp+A8h] [rbp-58h]
  int v22; // [rsp+BCh] [rbp-44h]
  __int64 v23; // [rsp+C0h] [rbp-40h]
  int v24; // [rsp+C8h] [rbp-38h]
  int v25; // [rsp+CCh] [rbp-34h]
  GUID *v26; // [rsp+D0h] [rbp-30h]
  int v27; // [rsp+D8h] [rbp-28h]
  DEVPROPKEY v28; // [rsp+E0h] [rbp-20h]
  int v29; // [rsp+F4h] [rbp-Ch]
  __int64 v30; // [rsp+F8h] [rbp-8h]
  int v31; // [rsp+100h] [rbp+0h]
  int v32; // [rsp+104h] [rbp+4h]
  char *v33; // [rsp+108h] [rbp+8h]
  int v34; // [rsp+110h] [rbp+10h] BYREF
  DEVPROPKEY v35; // [rsp+118h] [rbp+18h]
  int v36; // [rsp+12Ch] [rbp+2Ch]
  __int64 v37; // [rsp+130h] [rbp+30h]
  int v38; // [rsp+138h] [rbp+38h]
  int v39; // [rsp+13Ch] [rbp+3Ch]
  GUID *v40; // [rsp+140h] [rbp+40h]
  int v41; // [rsp+148h] [rbp+48h]
  DEVPROPGUID fmtid; // [rsp+150h] [rbp+50h]
  DEVPROPID pid; // [rsp+160h] [rbp+60h]
  int v44; // [rsp+164h] [rbp+64h]
  __int64 v45; // [rsp+168h] [rbp+68h]
  int v46; // [rsp+170h] [rbp+70h]
  int v47; // [rsp+174h] [rbp+74h]
  char *v48; // [rsp+178h] [rbp+78h]
  int v49; // [rsp+180h] [rbp+80h]
  DEVPROPGUID v50; // [rsp+188h] [rbp+88h]
  DEVPROPID v51; // [rsp+198h] [rbp+98h]
  int v52; // [rsp+19Ch] [rbp+9Ch]
  __int64 v53; // [rsp+1A0h] [rbp+A0h]
  int v54; // [rsp+1A8h] [rbp+A8h]
  int v55; // [rsp+1ACh] [rbp+ACh]
  __int64 *v56; // [rsp+1B0h] [rbp+B0h]
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  v2 = (unsigned __int64)a2[3] <= 7;
  v35 = DEVPKEY_Device_ClassGuid;
  v12 = -1;
  v40 = &GUID_5989fce8_9cd0_467d_8a6a_5419e31529d4;
  pid = DEVPKEY_Device_IsPresent.pid;
  v48 = &v12;
  v51 = DEVPKEY_Device_Parent.pid;
  v4 = *((_DWORD *)a2 + 4);
  v34 = 2;
  fmtid = DEVPKEY_Device_IsPresent.fmtid;
  v36 = 0;
  v55 = 2 * v4 + 2;
  v37 = 0;
  v38 = 13;
  v39 = 16;
  v41 = 2;
  v44 = 0;
  v45 = 0;
  v46 = 17;
  v47 = 1;
  v49 = 131074;
  v50 = DEVPKEY_Device_Parent.fmtid;
  v52 = 0;
  v53 = 0;
  v54 = 18;
  if ( !v2 )
    a2 = (__int64 *)*a2;
  v5 = (_QWORD *)(a1 + 88);
  v6 = *(_QWORD *)(a1 + 88);
  v56 = a2;
  v14 = DEVPKEY_Device_InstallDate;
  v15 = 0;
  v16 = 0;
  if ( v6 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v13);
    DevCloseObjectQuery(v6);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v13);
  }
  *v5 = 0;
  v7 = DevCreateObjectQuery(3, 1, 1, &v14, 3, &v34, DevQueryGlobalAPOCallback, 0, v5);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v10 = *(_QWORD *)(a1 + 96);
    v21 = DEVPKEY_DeviceInterface_ClassGuid;
    v26 = &GUID_8679405b_0f5d_4952_8efe_3b79a4252624;
    v28 = DEVPKEY_DeviceInterface_Enabled;
    v33 = &v12;
    v20 = 2;
    v22 = 0;
    v23 = 0;
    v24 = 13;
    v25 = 16;
    v27 = 2;
    v29 = 0;
    v30 = 0;
    v31 = 17;
    v32 = 1;
    v17 = DEVPKEY_Device_InstanceId;
    v18 = 0;
    v19 = 0;
    if ( v10 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v13);
      DevCloseObjectQuery(v10);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v13);
    }
    *(_QWORD *)(a1 + 96) = 0;
    return DevCreateObjectQuery(1, 1, 1, &v17, 2, &v20, DevQueryMEPAPOCallback, a1 + 112, a1 + 96);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F9,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audioepbservice.cpp",
      (const char *)(unsigned int)v7,
      v11);
    return v8;
  }
}

```

## disassembly

```asm
0x18003ac38  mov     [rsp-8+arg_10], rbx
0x18003ac3d  mov     [rsp-8+arg_18], rsi
0x18003ac42  push    rbp
0x18003ac43  push    rdi
0x18003ac44  push    r12
0x18003ac46  push    r14
0x18003ac48  push    r15
0x18003ac4a  lea     rbp, [rsp-0D0h]
0x18003ac52  sub     rsp, 1D0h
0x18003ac59  mov     rax, cs:__security_cookie
0x18003ac60  xor     rax, rsp
0x18003ac63  mov     [rbp+0F0h+var_30], rax
0x18003ac6a  mov     eax, cs:DEVPKEY_Device_ClassGuid.pid
0x18003ac70  xor     r14d, r14d
0x18003ac73  cmp     qword ptr [rdx+18h], 7
0x18003ac78  mov     r12d, 2
0x18003ac7e  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_ClassGuid.fmtid.Data1
0x18003ac85  mov     [rbp+0F0h+var_C8], eax
0x18003ac88  mov     rsi, rcx
0x18003ac8b  lea     rax, _GUID_5989fce8_9cd0_467d_8a6a_5419e31529d4
0x18003ac92  mov     [rsp+1F0h+var_1A0], 0FFh
0x18003ac97  mov     [rbp+0F0h+var_B0], rax
0x18003ac9b  lea     r15d, [r12-1]
0x18003aca0  mov     eax, cs:DEVPKEY_Device_IsPresent.pid
0x18003aca6  mov     [rbp+0F0h+var_90], eax
0x18003aca9  lea     rax, [rsp+1F0h+var_1A0]
0x18003acae  mov     [rbp+0F0h+var_78], rax
0x18003acb2  mov     eax, cs:DEVPKEY_Device_Parent.pid
0x18003acb8  movups  [rbp+0F0h+var_D8], xmm0
0x18003acbc  mov     [rbp+0F0h+var_58], eax
0x18003acc2  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_IsPresent.fmtid.Data1
0x18003acc9  mov     eax, [rdx+10h]
0x18003accc  mov     [rbp+0F0h+var_E0], r12d
0x18003acd0  movaps  [rbp+0F0h+var_A0], xmm0
0x18003acd4  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_Parent.fmtid.Data1
0x18003acdb  lea     eax, ds:2[rax*2]
0x18003ace2  mov     [rbp+0F0h+var_C4], r14d
0x18003ace6  mov     [rbp+0F0h+var_44], eax
0x18003acec  mov     [rbp+0F0h+var_C0], r14
0x18003acf0  mov     [rbp+0F0h+var_B8], 0Dh
0x18003acf7  mov     [rbp+0F0h+var_B4], 10h
0x18003acfe  mov     [rbp+0F0h+var_A8], r12d
0x18003ad02  mov     [rbp+0F0h+var_8C], r14d
0x18003ad06  mov     [rbp+0F0h+var_88], r14
0x18003ad0a  mov     [rbp+0F0h+var_80], 11h
0x18003ad11  mov     [rbp+0F0h+var_7C], r15d
0x18003ad15  mov     [rbp+0F0h+var_70], 20002h
0x18003ad1f  movups  [rbp+0F0h+var_68], xmm0
0x18003ad26  mov     [rbp+0F0h+var_54], r14d
0x18003ad2d  mov     [rbp+0F0h+var_50], r14
0x18003ad34  mov     [rbp+0F0h+var_48], 12h
0x18003ad3e  jbe     short loc_18003AD43
0x18003ad40  mov     rdx, [rdx]
0x18003ad43  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_InstallDate.fmtid.Data1
0x18003ad4a  mov     eax, cs:DEVPKEY_Device_InstallDate.pid
0x18003ad50  lea     rbx, [rcx+58h]
0x18003ad54  mov     rdi, [rbx]
0x18003ad57  mov     [rbp+0F0h+var_40], rdx
0x18003ad5e  mov     [rsp+1F0h+var_180], eax
0x18003ad62  mov     [rsp+1F0h+var_17C], r14d
0x18003ad67  mov     [rsp+1F0h+var_178], r14
0x18003ad6c  movups  [rsp+1F0h+var_190], xmm0
0x18003ad71  test    rdi, rdi
0x18003ad74  jz      short loc_18003AD93
0x18003ad76  lea     rcx, [rsp+1F0h+var_198]; this
0x18003ad7b  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003ad80  mov     rcx, rdi
0x18003ad83  call    cs:__imp_DevCloseObjectQuery
0x18003ad89  lea     rcx, [rsp+1F0h+var_198]; this
0x18003ad8e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003ad93  mov     [rsp+1F0h+var_1B0], rbx
0x18003ad98  lea     rax, ?DevQueryGlobalAPOCallback@@YAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; DevQueryGlobalAPOCallback(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x18003ad9f  mov     [rsp+1F0h+var_1B8], r14
0x18003ada4  lea     r9, [rsp+1F0h+var_190]
0x18003ada9  mov     [rsp+1F0h+var_1C0], rax
0x18003adae  mov     ecx, 3
0x18003adb3  lea     rax, [rbp+0F0h+var_E0]
0x18003adb7  mov     [rbx], r14
0x18003adba  mov     [rsp+1F0h+var_1C8], rax
0x18003adbf  mov     r8d, r15d
0x18003adc2  mov     edx, r15d
0x18003adc5  mov     [rsp+1F0h+var_1D0], ecx; int
0x18003adc9  call    cs:__imp_DevCreateObjectQuery
0x18003adcf  mov     ebx, eax
0x18003add1  test    eax, eax
0x18003add3  jns     short loc_18003ADF7
0x18003add5  mov     rcx, [rbp+0F8h]; this
0x18003addc  lea     r8, aAvcoreAudiocor_12; "avcore\\audiocore\\server\\audioendpoin"...
0x18003ade3  mov     r9d, eax; char *
0x18003ade6  mov     edx, 1F9h; void *
0x18003adeb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003adf0  mov     eax, ebx
0x18003adf2  jmp     loc_18003AEE7
0x18003adf7  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_ClassGuid.fmtid.Data1
0x18003adfe  mov     eax, cs:DEVPKEY_DeviceInterface_ClassGuid.pid
0x18003ae04  lea     rbx, [rsi+60h]
0x18003ae08  mov     rdi, [rbx]
0x18003ae0b  mov     [rbp+0F0h+var_138], eax
0x18003ae0e  lea     rax, _GUID_8679405b_0f5d_4952_8efe_3b79a4252624
0x18003ae15  mov     [rbp+0F0h+var_120], rax
0x18003ae19  mov     eax, cs:DEVPKEY_DeviceInterface_Enabled.pid
0x18003ae1f  mov     [rbp+0F0h+var_100], eax
0x18003ae22  lea     rax, [rsp+1F0h+var_1A0]
0x18003ae27  mov     [rbp+0F0h+var_E8], rax
0x18003ae2b  mov     eax, cs:DEVPKEY_Device_InstanceId.pid
0x18003ae31  mov     [rbp+0F0h+var_150], r12d
0x18003ae35  mov     [rbp+0F0h+var_134], r14d
0x18003ae39  mov     [rbp+0F0h+var_130], r14
0x18003ae3d  mov     [rbp+0F0h+var_128], 0Dh
0x18003ae44  mov     [rbp+0F0h+var_124], 10h
0x18003ae4b  mov     [rbp+0F0h+var_118], r12d
0x18003ae4f  mov     [rbp+0F0h+var_FC], r14d
0x18003ae53  mov     [rbp+0F0h+var_F8], r14
0x18003ae57  mov     [rbp+0F0h+var_F0], 11h
0x18003ae5e  mov     [rbp+0F0h+var_EC], r15d
0x18003ae62  mov     [rbp+0F0h+var_160], eax
0x18003ae65  mov     [rbp+0F0h+var_15C], r14d
0x18003ae69  mov     [rbp+0F0h+var_158], r14
0x18003ae6d  movups  [rbp+0F0h+var_148], xmm0
0x18003ae71  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_Enabled.fmtid.Data1
0x18003ae78  movaps  [rbp+0F0h+var_110], xmm0
0x18003ae7c  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_InstanceId.fmtid.Data1
0x18003ae83  movups  [rbp+0F0h+var_170], xmm0
0x18003ae87  test    rdi, rdi
0x18003ae8a  jz      short loc_18003AEA9
0x18003ae8c  lea     rcx, [rsp+1F0h+var_198]; this
0x18003ae91  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003ae96  mov     rcx, rdi
0x18003ae99  call    cs:__imp_DevCloseObjectQuery
0x18003ae9f  lea     rcx, [rsp+1F0h+var_198]; this
0x18003aea4  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003aea9  mov     [rsp+1F0h+var_1B0], rbx
0x18003aeae  lea     rax, [rsi+70h]
0x18003aeb2  mov     [rsp+1F0h+var_1B8], rax
0x18003aeb7  lea     r9, [rbp+0F0h+var_170]
0x18003aebb  lea     rax, ?DevQueryMEPAPOCallback@@YAXPEAUHDEVQUERY__@@PEAXPEBU_DEV_QUERY_RESULT_ACTION_DATA@@@Z; DevQueryMEPAPOCallback(HDEVQUERY__ *,void *,_DEV_QUERY_RESULT_ACTION_DATA const *)
0x18003aec2  mov     [rbx], r14
0x18003aec5  mov     [rsp+1F0h+var_1C0], rax
0x18003aeca  mov     r8d, r15d
0x18003aecd  lea     rax, [rbp+0F0h+var_150]
0x18003aed1  mov     edx, r15d
0x18003aed4  mov     [rsp+1F0h+var_1C8], rax
0x18003aed9  mov     ecx, r15d
0x18003aedc  mov     [rsp+1F0h+var_1D0], r12d
0x18003aee1  call    cs:__imp_DevCreateObjectQuery
0x18003aee7  mov     rcx, [rbp+0F0h+var_30]
0x18003aeee  xor     rcx, rsp; StackCookie
0x18003aef1  call    __security_check_cookie
0x18003aef6  lea     r11, [rsp+1F0h+var_20]
0x18003aefe  mov     rbx, [r11+40h]
0x18003af02  mov     rsi, [r11+48h]
0x18003af06  mov     rsp, r11
0x18003af09  pop     r15
0x18003af0b  pop     r14
0x18003af0d  pop     r12
0x18003af0f  pop     rdi
0x18003af10  pop     rbp
0x18003af11  retn
```
