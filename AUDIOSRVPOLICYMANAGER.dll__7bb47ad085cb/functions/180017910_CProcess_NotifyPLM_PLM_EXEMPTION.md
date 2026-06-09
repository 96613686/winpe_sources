# CProcess::NotifyPLM(_PLM_EXEMPTION)

- ea: `0x180017910`
- end: `0x180017cb1`
- name: `?NotifyPLM@CProcess@@QEAAXW4_PLM_EXEMPTION@@@Z`
- size: `929`
- prototype: `void __fastcall(__int64, int)`
- caller_count: `6`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800161d0`
- `0x180016a30`
- `0x180018330`
- `0x1800274fc`
- `0x180038798`
- `0x180039230`

## callees

- `0x18000f5f4`
- `0x180017910`
- `0x18001b340`
- `0x18001d580`
- `0x180031960`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001799a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180017a84`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001799a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180017a84`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180017c67`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x180017c67`

## pseudocode

```c
void __fastcall CProcess::NotifyPLM(__int64 a1, int a2)
{
  HRESULT Instance; // edi
  char v4; // si
  int v5; // edx
  _QWORD *v6; // rsi
  HRESULT v7; // eax
  int v8; // eax
  int *v9; // rax
  _QWORD *v10; // rsi
  HRESULT v11; // eax
  __int64 v12; // r10
  __int64 *v13; // rcx
  __int64 v14; // rax
  int v15; // eax
  int v16; // [rsp+30h] [rbp-69h] BYREF
  int v17; // [rsp+34h] [rbp-65h] BYREF
  _DWORD v18[2]; // [rsp+38h] [rbp-61h] BYREF
  __int64 v19; // [rsp+40h] [rbp-59h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-51h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-39h] BYREF
  char *v22; // [rsp+70h] [rbp-29h]
  int v23; // [rsp+78h] [rbp-21h]
  int v24; // [rsp+7Ch] [rbp-1Dh]
  __int64 *v25; // [rsp+80h] [rbp-19h]
  int v26; // [rsp+88h] [rbp-11h]
  int v27; // [rsp+8Ch] [rbp-Dh]
  __int64 *v28; // [rsp+90h] [rbp-9h]
  __int64 v29; // [rsp+98h] [rbp-1h]
  _DWORD *v30; // [rsp+A0h] [rbp+7h]
  __int64 v31; // [rsp+A8h] [rbp+Fh]
  int *v32; // [rsp+B0h] [rbp+17h]
  __int64 v33; // [rsp+B8h] [rbp+1Fh]
  int *v34; // [rsp+C0h] [rbp+27h]
  __int64 v35; // [rsp+C8h] [rbp+2Fh]

  Instance = 0;
  v4 = 0;
  v5 = a2 - 1;
  if ( !v5 )
  {
    if ( !*(_DWORD *)(a1 + 232) )
      goto LABEL_15;
    v7 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 240) + 40LL))(*(_QWORD *)(a1 + 240));
    if ( v7 != -2147023728 )
      Instance = v7;
    if ( Instance < 0 )
      goto LABEL_43;
    *(_DWORD *)(a1 + 232) = 0;
    goto LABEL_14;
  }
  if ( v5 == 1 )
  {
    if ( *(_DWORD *)(a1 + 416) )
      return;
    if ( !*(_DWORD *)(a1 + 232) )
    {
      v6 = (_QWORD *)(a1 + 240);
      if ( !*(_QWORD *)(a1 + 240) )
      {
        *v6 = 0;
        Instance = CoCreateInstance(
                     &CLSID_OSTaskCompletion,
                     0,
                     1u,
                     &GUID_c7e40572_c36a_43ea_9a40_f3b168da5558,
                     (LPVOID *)(a1 + 240));
        if ( Instance < 0 )
          goto LABEL_43;
      }
      Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(*(_QWORD *)*v6 + 32LL))(
                   *v6,
                   *(_QWORD *)(a1 + 152),
                   1);
      if ( Instance < 0 )
        goto LABEL_43;
      *(_DWORD *)(a1 + 232) = 1;
LABEL_14:
      v4 = 1;
    }
  }
LABEL_15:
  if ( *(_QWORD *)(a1 + 224) )
  {
    v8 = CApplication::Category();
  }
  else
  {
    v9 = (int *)(a1 + 484);
    if ( !*(_DWORD *)(a1 + 480) )
      v9 = (int *)(a1 + 312);
    v8 = *v9;
  }
  if ( !v8 && *(_DWORD *)(a1 + 436) )
  {
    if ( !*(_DWORD *)(a1 + 236) )
    {
      v10 = (_QWORD *)(a1 + 248);
      if ( *(_QWORD *)(a1 + 248)
        || (*v10 = 0,
            Instance = CoCreateInstance(
                         &CLSID_OSTaskCompletion,
                         0,
                         1u,
                         &GUID_c7e40572_c36a_43ea_9a40_f3b168da5558,
                         (LPVOID *)(a1 + 248)),
            Instance >= 0) )
      {
        Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(*(_QWORD *)*v10 + 32LL))(
                     *v10,
                     *(_QWORD *)(a1 + 152),
                     0x80000);
        if ( Instance >= 0 )
        {
          *(_DWORD *)(a1 + 236) = 1;
LABEL_33:
          v12 = *((_QWORD *)AudioSrvPolicyManagerTelemetryProvider::Instance() + 1);
          if ( *(_DWORD *)v12 > 4u
            && (*(_QWORD *)(v12 + 16) & 0x20000LL) != 0
            && (*(_QWORD *)(v12 + 24) & 0x20000LL) == *(_QWORD *)(v12 + 24) )
          {
            v16 = *(_DWORD *)(a1 + 236);
            v17 = *(_DWORD *)(a1 + 232);
            v18[0] = *(_DWORD *)(a1 + 160);
            v19 = *(_QWORD *)(a1 + 208);
            v13 = *(__int64 **)(a1 + 176);
            v34 = &v16;
            v35 = 4;
            v32 = &v17;
            v33 = 4;
            v30 = v18;
            v31 = 4;
            v28 = &v19;
            v29 = 8;
            if ( v13 )
            {
              v14 = -1;
              do
                ++v14;
              while ( *((_WORD *)v13 + v14) );
              v15 = 2 * v14 + 2;
            }
            else
            {
              v13 = &qword_180053B30;
              v15 = 2;
            }
            v25 = v13;
            v26 = v15;
            v27 = 0;
            *(_DWORD *)&EventDescriptor.Id = 184549376;
            *(_DWORD *)&EventDescriptor.Level = 4;
            EventDescriptor.Keyword = 0x20000;
            UserData.Ptr = *(_QWORD *)(v12 + 8);
            UserData.Size = *(unsigned __int16 *)UserData.Ptr;
            UserData.Reserved = 2;
            v22 = &byte_1800572CF;
            v23 = 115;
            v24 = 1;
            v18[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
            EventWriteTransfer(*(_QWORD *)(v12 + 32), &EventDescriptor, 0, 0, 7u, &UserData);
          }
          return;
        }
      }
      goto LABEL_43;
    }
LABEL_32:
    if ( v4 != 1 )
      return;
    goto LABEL_33;
  }
  if ( !*(_DWORD *)(a1 + 236) )
    goto LABEL_32;
  v11 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 248) + 40LL))(*(_QWORD *)(a1 + 248));
  Instance = 0;
  if ( v11 != -2147023728 )
    Instance = v11;
  if ( Instance >= 0 )
  {
    *(_DWORD *)(a1 + 236) = 0;
    goto LABEL_33;
  }
LABEL_43:
  if ( Instance != -805305819 )
    AudPolicyLogError("CProcess::NotifyPLM", 3468, Instance);
}

```

## disassembly

```asm
0x180017910  mov     [rsp-8+arg_8], rbx
0x180017915  mov     [rsp-8+arg_10], rsi
0x18001791a  push    rbp
0x18001791b  push    rdi
0x18001791c  push    r14
0x18001791e  lea     rbp, [rsp-47h]
0x180017923  sub     rsp, 0E0h
0x18001792a  mov     rax, cs:__security_cookie
0x180017931  xor     rax, rsp
0x180017934  mov     [rbp+57h+var_20], rax
0x180017938  mov     rbx, rcx
0x18001793b  xor     r14d, r14d
0x18001793e  mov     edi, r14d
0x180017941  xor     sil, sil
0x180017944  sub     edx, 1
0x180017947  jz      loc_1800179DC
0x18001794d  cmp     edx, 1
0x180017950  jnz     loc_180017A11
0x180017956  cmp     [rcx+1A0h], r14d
0x18001795d  jnz     loc_180017C8D
0x180017963  cmp     [rcx+0E8h], r14d
0x18001796a  jnz     loc_180017A11
0x180017970  lea     rsi, [rcx+0F0h]
0x180017977  cmp     [rsi], rdi
0x18001797a  jnz     short loc_1800179AA
0x18001797c  mov     [rsi], r14
0x18001797f  mov     [rsp+0F0h+ppv], rsi; ppv
0x180017984  lea     r9, _GUID_c7e40572_c36a_43ea_9a40_f3b168da5558; riid
0x18001798b  xor     edx, edx; pUnkOuter
0x18001798d  mov     r8d, 1; dwClsContext
0x180017993  lea     rcx, CLSID_OSTaskCompletion; rclsid
0x18001799a  call    cs:__imp_CoCreateInstance
0x1800179a0  mov     edi, eax
0x1800179a2  test    eax, eax
0x1800179a4  js      loc_180017C71
0x1800179aa  mov     rcx, [rsi]
0x1800179ad  mov     rax, [rcx]
0x1800179b0  mov     r8d, 1
0x1800179b6  mov     rdx, [rbx+98h]
0x1800179bd  mov     rax, [rax+20h]
0x1800179c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800179c6  mov     edi, eax
0x1800179c8  test    eax, eax
0x1800179ca  js      loc_180017C71
0x1800179d0  mov     dword ptr [rbx+0E8h], 1
0x1800179da  jmp     short loc_180017A0E
0x1800179dc  cmp     [rcx+0E8h], edi
0x1800179e2  jz      short loc_180017A11
0x1800179e4  mov     rcx, [rcx+0F0h]
0x1800179eb  mov     rax, [rcx]
0x1800179ee  mov     rax, [rax+28h]
0x1800179f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800179f7  cmp     eax, 80070490h
0x1800179fc  cmovnz  edi, eax
0x1800179ff  test    edi, edi
0x180017a01  js      loc_180017C71
0x180017a07  mov     [rbx+0E8h], r14d
0x180017a0e  mov     sil, 1
0x180017a11  mov     rcx, [rbx+0E0h]
0x180017a18  test    rcx, rcx
0x180017a1b  jz      short loc_180017A24
0x180017a1d  call    ?Category@CApplication@@QEAA?AW4_APPLICATION_CATEGORY@@XZ; CApplication::Category(void)
0x180017a22  jmp     short loc_180017A3D
0x180017a24  cmp     dword ptr [rbx+1E0h], 0
0x180017a2b  lea     rax, [rbx+1E4h]
0x180017a32  jnz     short loc_180017A3B
0x180017a34  lea     rax, [rbx+138h]
0x180017a3b  mov     eax, [rax]
0x180017a3d  test    eax, eax
0x180017a3f  jnz     loc_180017AC6
0x180017a45  cmp     [rbx+1B4h], eax
0x180017a4b  jz      short loc_180017AC6
0x180017a4d  cmp     [rbx+0ECh], eax
0x180017a53  jnz     loc_180017AFE
0x180017a59  lea     rsi, [rbx+0F8h]
0x180017a60  cmp     qword ptr [rsi], 0
0x180017a64  jnz     short loc_180017A94
0x180017a66  mov     [rsi], r14
0x180017a69  mov     [rsp+0F0h+ppv], rsi; ppv
0x180017a6e  lea     r9, _GUID_c7e40572_c36a_43ea_9a40_f3b168da5558; riid
0x180017a75  xor     edx, edx; pUnkOuter
0x180017a77  mov     r8d, 1; dwClsContext
0x180017a7d  lea     rcx, CLSID_OSTaskCompletion; rclsid
0x180017a84  call    cs:__imp_CoCreateInstance
0x180017a8a  mov     edi, eax
0x180017a8c  test    eax, eax
0x180017a8e  js      loc_180017C71
0x180017a94  mov     rcx, [rsi]
0x180017a97  mov     rax, [rcx]
0x180017a9a  mov     r8d, 80000h
0x180017aa0  mov     rdx, [rbx+98h]
0x180017aa7  mov     rax, [rax+20h]
0x180017aab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ab0  mov     edi, eax
0x180017ab2  test    eax, eax
0x180017ab4  js      loc_180017C71
0x180017aba  mov     dword ptr [rbx+0ECh], 1
0x180017ac4  jmp     short loc_180017B08
0x180017ac6  cmp     dword ptr [rbx+0ECh], 0
0x180017acd  jz      short loc_180017AFE
0x180017acf  mov     rcx, [rbx+0F8h]
0x180017ad6  mov     rax, [rcx]
0x180017ad9  mov     rax, [rax+28h]
0x180017add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ae2  mov     edi, r14d
0x180017ae5  cmp     eax, 80070490h
0x180017aea  cmovnz  edi, eax
0x180017aed  test    edi, edi
0x180017aef  js      loc_180017C71
0x180017af5  mov     [rbx+0ECh], r14d
0x180017afc  jmp     short loc_180017B08
0x180017afe  cmp     sil, 1
0x180017b02  jnz     loc_180017C6D
0x180017b08  call    ?Instance@AudioSrvPolicyManagerTelemetryProvider@@KAPEAV1@XZ; AudioSrvPolicyManagerTelemetryProvider::Instance(void)
0x180017b0d  mov     r10, [rax+8]
0x180017b11  mov     eax, [r10]
0x180017b14  cmp     eax, 4
0x180017b17  jbe     loc_180017C6D
0x180017b1d  mov     rcx, [r10+18h]
0x180017b21  mov     rax, [r10+10h]
0x180017b25  bt      rax, 11h
0x180017b2a  jnb     loc_180017C6D
0x180017b30  mov     rax, rcx
0x180017b33  and     eax, 20000h
0x180017b38  cmp     rax, rcx
0x180017b3b  jnz     loc_180017C6D
0x180017b41  mov     eax, [rbx+0ECh]
0x180017b47  mov     [rbp+57h+var_C0], eax
0x180017b4a  mov     eax, [rbx+0E8h]
0x180017b50  mov     [rbp+57h+var_BC], eax
0x180017b53  mov     eax, [rbx+0A0h]
0x180017b59  mov     [rbp+57h+var_B8], eax
0x180017b5c  mov     rax, [rbx+0D0h]
0x180017b63  mov     [rbp+57h+var_B0], rax
0x180017b67  mov     rcx, [rbx+0B0h]
0x180017b6e  lea     rax, [rbp+57h+var_C0]
0x180017b72  mov     [rbp+57h+var_30], rax
0x180017b76  mov     [rbp+57h+var_28], 4
0x180017b7e  lea     rax, [rbp+57h+var_BC]
0x180017b82  mov     [rbp+57h+var_40], rax
0x180017b86  mov     [rbp+57h+var_38], 4
0x180017b8e  lea     rax, [rbp+57h+var_B8]
0x180017b92  mov     [rbp+57h+var_50], rax
0x180017b96  mov     [rbp+57h+var_48], 4
0x180017b9e  lea     rax, [rbp+57h+var_B0]
0x180017ba2  mov     [rbp+57h+var_60], rax
0x180017ba6  mov     [rbp+57h+var_58], 8
0x180017bae  test    rcx, rcx
0x180017bb1  jz      short loc_180017BD4
0x180017bb3  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180017bba  nop     word ptr [rax+rax+00h]
0x180017bc0  lea     rax, [rax+1]
0x180017bc4  cmp     word ptr [rcx+rax*2], 0
0x180017bc9  jnz     short loc_180017BC0
0x180017bcb  lea     eax, ds:2[rax*2]
0x180017bd2  jmp     short loc_180017BE0
0x180017bd4  lea     rcx, qword_180053B30
0x180017bdb  mov     eax, 2
0x180017be0  mov     [rbp+57h+var_70], rcx
0x180017be4  mov     [rbp+57h+var_68], eax
0x180017be7  mov     [rbp+57h+var_64], r14d
0x180017beb  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x180017bf2  movzx   eax, cs:word_1800572C5
0x180017bf9  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x180017bfc  mov     [rbp+57h+EventDescriptor.Keyword], 20000h
0x180017c04  mov     rax, [r10+8]
0x180017c08  mov     [rbp+57h+var_90.Ptr], rax
0x180017c0c  movzx   eax, word ptr [rax]
0x180017c0f  mov     [rbp+57h+var_90.Size], eax
0x180017c12  mov     dword ptr [rbp+57h+var_90.0Ch], 2
0x180017c19  lea     rax, byte_1800572CF
0x180017c20  mov     [rbp+57h+var_80], rax
0x180017c24  mov     [rbp+57h+var_78], 73h ; 's'
0x180017c2b  mov     [rbp+57h+var_74], 1
0x180017c32  lea     rax, _TraceLoggingMetadataEnd
0x180017c39  lea     rcx, _TraceLoggingMetadata
0x180017c40  sub     eax, ecx
0x180017c42  mov     [rbp+57h+var_B4], eax
0x180017c45  mov     eax, [rbp+57h+var_B4]
0x180017c48  lea     rax, [rbp+57h+var_90]
0x180017c4c  mov     [rsp+0F0h+UserData], rax; UserData
0x180017c51  mov     dword ptr [rsp+0F0h+ppv], 7; UserDataCount
0x180017c59  xor     r9d, r9d; RelatedActivityId
0x180017c5c  xor     r8d, r8d; ActivityId
0x180017c5f  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x180017c63  mov     rcx, [r10+20h]; RegHandle
0x180017c67  call    cs:__imp_EventWriteTransfer
0x180017c6d  test    edi, edi
0x180017c6f  jns     short loc_180017C8D
0x180017c71  cmp     edi, 0D0000225h
0x180017c77  jz      short loc_180017C8D
0x180017c79  mov     r8d, edi; int
0x180017c7c  mov     edx, 0D8Ch; int
0x180017c81  lea     rcx, aCprocessNotify; "CProcess::NotifyPLM"
0x180017c88  call    ?AudPolicyLogError@@YAXPEBDHJ@Z; AudPolicyLogError(char const *,int,long)
0x180017c8d  mov     rcx, [rbp+57h+var_20]
0x180017c91  xor     rcx, rsp; StackCookie
0x180017c94  call    __security_check_cookie
0x180017c99  lea     r11, [rsp+0F0h+var_10]
0x180017ca1  mov     rbx, [r11+28h]
0x180017ca5  mov     rsi, [r11+30h]
0x180017ca9  mov     rsp, r11
0x180017cac  pop     r14
0x180017cae  pop     rdi
0x180017caf  pop     rbp
0x180017cb0  retn
```
