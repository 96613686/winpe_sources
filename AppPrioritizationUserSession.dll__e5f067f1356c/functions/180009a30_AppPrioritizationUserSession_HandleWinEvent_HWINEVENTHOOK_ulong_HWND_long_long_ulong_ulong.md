# AppPrioritizationUserSession::HandleWinEvent(HWINEVENTHOOK__ *,ulong,HWND__ *,long,long,ulong,ulong)

- ea: `0x180009a30`
- end: `0x180009e23`
- name: `?HandleWinEvent@AppPrioritizationUserSession@@CAXPEAUHWINEVENTHOOK__@@KPEAUHWND__@@JJKK@Z`
- size: `1011`
- prototype: `void __fastcall(HWINEVENTHOOK hWinEventHook, DWORD event, HWND hwnd, LONG idObject)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001304`
- `0x180002650`
- `0x18000887c`
- `0x180009414`
- `0x180009a30`
- `0x18000b140`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ae3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ae3`
- `USER32!GetWindowThreadProcessId` at `0x180009ac6`
- `USER32!GetWindowThreadProcessId` at `0x180009ac6`
- `USER32!IsIconic` at `0x180009d15`
- `USER32!IsIconic` at `0x180009d15`
- `USER32!IsWindowVisible` at `0x180009d2f`
- `USER32!IsWindowVisible` at `0x180009d2f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall AppPrioritizationUserSession::HandleWinEvent(
        HWINEVENTHOOK hWinEventHook,
        DWORD event,
        HWND hwnd,
        LONG idObject)
{
  __int64 v6; // rdx
  int v7; // eax
  __int64 v8; // rcx
  __int64 v9; // rcx
  int v10; // edx
  DWORD v11; // eax
  int *v12; // r8
  __int64 v13; // rdx
  BOOL v14; // eax
  DWORD LastError; // [rsp+30h] [rbp-118h] BYREF
  DWORD v16; // [rsp+34h] [rbp-114h] BYREF
  DWORD v17; // [rsp+38h] [rbp-110h] BYREF
  DWORD v18; // [rsp+3Ch] [rbp-10Ch] BYREF
  DWORD v19; // [rsp+40h] [rbp-108h] BYREF
  DWORD dwProcessId[4]; // [rsp+48h] [rbp-100h] BYREF
  __int64 v21; // [rsp+58h] [rbp-F0h] BYREF
  _QWORD v22[4]; // [rsp+60h] [rbp-E8h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v23; // [rsp+80h] [rbp-C8h] BYREF
  DWORD *p_LastError; // [rsp+A0h] [rbp-A8h]
  __int64 v25; // [rsp+A8h] [rbp-A0h]
  struct _EVENT_DATA_DESCRIPTOR v26; // [rsp+B0h] [rbp-98h] BYREF
  DWORD *v27; // [rsp+D0h] [rbp-78h]
  __int64 v28; // [rsp+D8h] [rbp-70h]
  DWORD *v29; // [rsp+E0h] [rbp-68h]
  __int64 v30; // [rsp+E8h] [rbp-60h]
  int *v31; // [rsp+F0h] [rbp-58h]
  int v32; // [rsp+F8h] [rbp-50h]
  int v33; // [rsp+FCh] [rbp-4Ch]
  DWORD *v34; // [rsp+100h] [rbp-48h]
  __int64 v35; // [rsp+108h] [rbp-40h]
  DWORD *v36; // [rsp+110h] [rbp-38h]
  __int64 v37; // [rsp+118h] [rbp-30h]
  DWORD *v38; // [rsp+120h] [rbp-28h]
  __int64 v39; // [rsp+128h] [rbp-20h]

  v6 = 0;
  v21 = 0;
  if ( AppPrioritizationUserSession::s_weakReference )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64 *))(*AppPrioritizationUserSession::s_weakReference + 24LL))(
           AppPrioritizationUserSession::s_weakReference,
           &GUID_ca9ef94a_1e31_4de6_87ce_74c22fab5a86,
           &v21);
    v6 = v21;
  }
  else
  {
    v7 = 0;
  }
  if ( v7 < 0 )
  {
    if ( v6 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    return;
  }
  *(_OWORD *)dwProcessId = 0;
  if ( GetWindowThreadProcessId(hwnd, dwProcessId) )
  {
    AppPrioritizationUserSession::GetProcessNameFromProcessId(v22, dwProcessId[0]);
    if ( event == 3 )
    {
      v11 = 1;
      dwProcessId[2] = 1;
      dwProcessId[1] = 1;
    }
    else
    {
      if ( event == 22 )
      {
        dwProcessId[2] = 3;
        dwProcessId[1] = 0;
        goto LABEL_24;
      }
      if ( event != 23 )
      {
        if ( event == 32791 )
        {
          v10 = 2;
          dwProcessId[2] = 2;
          dwProcessId[1] = 0;
          goto LABEL_25;
        }
        if ( event != 32792 )
        {
          MicrosoftTelemetryAssertTriggeredArgs(v9, event, event);
          if ( (unsigned int)dword_180014000 > 2 )
          {
            LastError = event;
            p_LastError = &LastError;
            v25 = 4;
            tlgWriteTransfer_EventWriteTransfer((int)&dword_180014000, (int)&byte_18000FCA7, 0, 0, 3u, &v23);
          }
          std::wstring::~wstring(v22);
          v8 = v21;
          if ( v21 )
            goto LABEL_20;
          return;
        }
      }
      v11 = dwProcessId[2];
    }
    if ( !v11 )
    {
      if ( !IsIconic(hwnd) )
      {
        v14 = IsWindowVisible(hwnd);
        v10 = 2;
        dwProcessId[2] = 2 - v14;
LABEL_25:
        dwProcessId[3] = 1;
        if ( (unsigned int)dword_180014000 > 4 )
        {
          LastError = dwProcessId[3];
          v16 = dwProcessId[2];
          v17 = dwProcessId[1];
          v12 = (int *)v22;
          if ( v22[3] > 7u )
            v12 = (int *)v22[0];
          v18 = dwProcessId[0];
          v19 = event;
          v38 = &LastError;
          v39 = 4;
          v36 = &v16;
          v37 = 4;
          v34 = &v17;
          v35 = 4;
          if ( v12 )
          {
            v13 = -1;
            do
              ++v13;
            while ( *((_WORD *)v12 + v13) );
            v10 = 2 * v13 + 2;
          }
          else
          {
            v12 = &dword_18000EE34;
          }
          v31 = v12;
          v32 = v10;
          v33 = 0;
          v29 = &v18;
          v30 = 4;
          v27 = &v19;
          v28 = 4;
          tlgWriteTransfer_EventWriteTransfer((int)&dword_180014000, (int)&word_18000FC22, 0, 0, 8u, &v26);
        }
        (*(void (__fastcall **)(__int64, DWORD *))(*(_QWORD *)v21 + 64LL))(v21, dwProcessId);
        std::wstring::~wstring(v22);
        v8 = v21;
        if ( v21 )
          goto LABEL_20;
        return;
      }
      dwProcessId[2] = 3;
    }
LABEL_24:
    v10 = 2;
    goto LABEL_25;
  }
  if ( (unsigned int)dword_180014000 > 2 )
  {
    LastError = GetLastError();
    p_LastError = &LastError;
    v25 = 4;
    tlgWriteTransfer_EventWriteTransfer((int)&dword_180014000, (int)&byte_18000FD0D, 0, 0, 3u, &v23);
  }
  v8 = v21;
  if ( v21 )
  {
LABEL_20:
    v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
}

```

## disassembly

```asm
0x180009a30  mov     [rsp+arg_0], rsi
0x180009a35  mov     [rsp+arg_18], rdi
0x180009a3a  push    r14
0x180009a3c  sub     rsp, 140h
0x180009a43  mov     rax, cs:__security_cookie
0x180009a4a  xor     rax, rsp
0x180009a4d  mov     [rsp+148h+var_18], rax
0x180009a55  mov     rsi, r8
0x180009a58  mov     edi, edx
0x180009a5a  xor     r14d, r14d
0x180009a5d  mov     edx, r14d
0x180009a60  mov     [rsp+148h+var_F0], rdx
0x180009a65  mov     rcx, cs:?s_weakReference@AppPrioritizationUserSession@@2VWeakRef@WRL@Microsoft@@A; Microsoft::WRL::WeakRef AppPrioritizationUserSession::s_weakReference
0x180009a6c  test    rcx, rcx
0x180009a6f  jnz     short loc_180009A76
0x180009a71  mov     eax, r14d
0x180009a74  jmp     short loc_180009A93
0x180009a76  mov     rax, [rcx]
0x180009a79  lea     r8, [rsp+148h+var_F0]
0x180009a7e  lea     rdx, _GUID_ca9ef94a_1e31_4de6_87ce_74c22fab5a86
0x180009a85  mov     rax, [rax+18h]
0x180009a89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a8e  mov     rdx, [rsp+148h+var_F0]
0x180009a93  test    eax, eax
0x180009a95  jns     short loc_180009AB6
0x180009a97  test    rdx, rdx
0x180009a9a  jz      short loc_180009AB1
0x180009a9c  mov     [rsp+148h+var_F0], r14
0x180009aa1  mov     rax, [rdx]
0x180009aa4  mov     rcx, rdx
0x180009aa7  mov     rax, [rax+10h]
0x180009aab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ab0  nop
0x180009ab1  jmp     loc_180009DFD
0x180009ab6  xorps   xmm0, xmm0
0x180009ab9  movups  xmmword ptr [rsp+148h+dwProcessId], xmm0
0x180009abe  lea     rdx, [rsp+148h+dwProcessId]; lpdwProcessId
0x180009ac3  mov     rcx, rsi; hWnd
0x180009ac6  call    cs:__imp_GetWindowThreadProcessId
0x180009acc  test    eax, eax
0x180009ace  jnz     loc_180009B56
0x180009ad4  mov     eax, cs:dword_180014000
0x180009ada  mov     edx, 2
0x180009adf  cmp     eax, edx
0x180009ae1  jbe     short loc_180009B35
0x180009ae3  call    cs:__imp_GetLastError
0x180009ae9  mov     [rsp+148h+var_118], eax
0x180009aed  lea     rax, [rsp+148h+var_118]
0x180009af2  mov     [rsp+148h+var_A8], rax
0x180009afa  mov     [rsp+148h+var_A0], 4
0x180009b06  lea     rax, [rsp+148h+var_C8]
0x180009b0e  mov     [rsp+148h+var_120], rax; PEVENT_DATA_DESCRIPTOR
0x180009b13  mov     [rsp+148h+var_128], 3; ULONG
0x180009b1b  xor     r9d, r9d; int
0x180009b1e  xor     r8d, r8d; int
0x180009b21  lea     rdx, byte_18000FD0D; int
0x180009b28  lea     rcx, dword_180014000; int
0x180009b2f  call    _tlgWriteTransfer_EventWriteTransfer
0x180009b34  nop
0x180009b35  mov     rcx, [rsp+148h+var_F0]
0x180009b3a  test    rcx, rcx
0x180009b3d  jz      short loc_180009B51
0x180009b3f  mov     [rsp+148h+var_F0], r14
0x180009b44  mov     rax, [rcx]
0x180009b47  mov     rax, [rax+10h]
0x180009b4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b50  nop
0x180009b51  jmp     loc_180009DFD
0x180009b56  mov     edx, [rsp+148h+dwProcessId]
0x180009b5a  lea     rcx, [rsp+148h+var_E8]
0x180009b5f  call    ?GetProcessNameFromProcessId@AppPrioritizationUserSession@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; AppPrioritizationUserSession::GetProcessNameFromProcessId(ulong)
0x180009b64  nop
0x180009b65  mov     eax, edi
0x180009b67  sub     eax, 3
0x180009b6a  jz      loc_180009CFD
0x180009b70  sub     eax, 13h
0x180009b73  jz      loc_180009C40
0x180009b79  sub     eax, 1
0x180009b7c  jz      loc_180009C37
0x180009b82  sub     eax, 8000h
0x180009b87  jz      loc_180009C27
0x180009b8d  cmp     eax, 1
0x180009b90  jz      loc_180009C37
0x180009b96  mov     r8d, edi
0x180009b99  mov     edx, edi
0x180009b9b  call    MicrosoftTelemetryAssertTriggeredArgs
0x180009ba0  mov     eax, cs:dword_180014000
0x180009ba6  mov     edx, 2
0x180009bab  cmp     eax, edx
0x180009bad  jbe     short loc_180009BFB
0x180009baf  mov     [rsp+148h+var_118], edi
0x180009bb3  lea     rax, [rsp+148h+var_118]
0x180009bb8  mov     [rsp+148h+var_A8], rax
0x180009bc0  mov     [rsp+148h+var_A0], 4
0x180009bcc  lea     rax, [rsp+148h+var_C8]
0x180009bd4  mov     [rsp+148h+var_120], rax; PEVENT_DATA_DESCRIPTOR
0x180009bd9  mov     [rsp+148h+var_128], 3; ULONG
0x180009be1  xor     r9d, r9d; int
0x180009be4  xor     r8d, r8d; int
0x180009be7  lea     rdx, byte_18000FCA7; int
0x180009bee  lea     rcx, dword_180014000; int
0x180009bf5  call    _tlgWriteTransfer_EventWriteTransfer
0x180009bfa  nop
0x180009bfb  lea     rcx, [rsp+148h+var_E8]
0x180009c00  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180009c05  nop
0x180009c06  mov     rcx, [rsp+148h+var_F0]
0x180009c0b  test    rcx, rcx
0x180009c0e  jz      short loc_180009C22
0x180009c10  mov     [rsp+148h+var_F0], r14
0x180009c15  mov     rax, [rcx]
0x180009c18  mov     rax, [rax+10h]
0x180009c1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c21  nop
0x180009c22  jmp     loc_180009DFD
0x180009c27  mov     edx, 2
0x180009c2c  mov     [rsp+148h+dwProcessId+8], edx
0x180009c30  mov     [rsp+148h+dwProcessId+4], r14d
0x180009c35  jmp     short loc_180009C52
0x180009c37  mov     eax, [rsp+148h+dwProcessId+8]
0x180009c3b  jmp     loc_180009D0A
0x180009c40  mov     [rsp+148h+dwProcessId+8], 3
0x180009c48  mov     [rsp+148h+dwProcessId+4], r14d
0x180009c4d  mov     edx, 2
0x180009c52  mov     [rsp+148h+dwProcessId+0Ch], 1
0x180009c5a  mov     eax, cs:dword_180014000
0x180009c60  mov     ecx, 4
0x180009c65  cmp     eax, ecx
0x180009c67  jbe     loc_180009DBF
0x180009c6d  mov     eax, [rsp+148h+dwProcessId+0Ch]
0x180009c71  mov     [rsp+148h+var_118], eax
0x180009c75  mov     eax, [rsp+148h+dwProcessId+8]
0x180009c79  mov     [rsp+148h+var_114], eax
0x180009c7d  mov     eax, [rsp+148h+dwProcessId+4]
0x180009c81  mov     [rsp+148h+var_110], eax
0x180009c85  lea     r8, [rsp+148h+var_E8]
0x180009c8a  cmp     [rsp+148h+var_D0], 7
0x180009c90  cmova   r8, [rsp+148h+var_E8]
0x180009c96  mov     eax, [rsp+148h+dwProcessId]
0x180009c9a  mov     [rsp+148h+var_10C], eax
0x180009c9e  mov     [rsp+148h+var_108], edi
0x180009ca2  lea     rax, [rsp+148h+var_118]
0x180009ca7  mov     [rsp+148h+var_28], rax
0x180009caf  mov     [rsp+148h+var_20], rcx
0x180009cb7  lea     rax, [rsp+148h+var_114]
0x180009cbc  mov     [rsp+148h+var_38], rax
0x180009cc4  mov     [rsp+148h+var_30], rcx
0x180009ccc  lea     rax, [rsp+148h+var_110]
0x180009cd1  mov     [rsp+148h+var_48], rax
0x180009cd9  mov     [rsp+148h+var_40], rcx
0x180009ce1  test    r8, r8
0x180009ce4  jz      short loc_180009D49
0x180009ce6  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180009cea  inc     rdx
0x180009ced  cmp     [r8+rdx*2], r14w
0x180009cf2  jnz     short loc_180009CEA
0x180009cf4  lea     edx, ds:2[rdx*2]
0x180009cfb  jmp     short loc_180009D50
0x180009cfd  mov     eax, 1
0x180009d02  mov     [rsp+148h+dwProcessId+8], eax
0x180009d06  mov     [rsp+148h+dwProcessId+4], eax
0x180009d0a  test    eax, eax
0x180009d0c  jnz     loc_180009C4D
0x180009d12  mov     rcx, rsi; hWnd
0x180009d15  call    cs:__imp_IsIconic
0x180009d1b  test    eax, eax
0x180009d1d  jz      short loc_180009D2C
0x180009d1f  mov     [rsp+148h+dwProcessId+8], 3
0x180009d27  jmp     loc_180009C4D
0x180009d2c  mov     rcx, rsi; hWnd
0x180009d2f  call    cs:__imp_IsWindowVisible
0x180009d35  neg     eax
0x180009d37  sbb     ecx, ecx
0x180009d39  mov     edx, 2
0x180009d3e  add     ecx, edx
0x180009d40  mov     [rsp+148h+dwProcessId+8], ecx
0x180009d44  jmp     loc_180009C52
0x180009d49  lea     r8, dword_18000EE34
0x180009d50  mov     [rsp+148h+var_58], r8
0x180009d58  mov     [rsp+148h+var_50], edx
0x180009d5f  mov     [rsp+148h+var_4C], r14d
0x180009d67  lea     rax, [rsp+148h+var_10C]
0x180009d6c  mov     [rsp+148h+var_68], rax
0x180009d74  mov     [rsp+148h+var_60], rcx
0x180009d7c  lea     rax, [rsp+148h+var_108]
0x180009d81  mov     [rsp+148h+var_78], rax
0x180009d89  mov     [rsp+148h+var_70], rcx
0x180009d91  lea     rax, [rsp+148h+var_98]
0x180009d99  mov     [rsp+148h+var_120], rax; PEVENT_DATA_DESCRIPTOR
0x180009d9e  mov     [rsp+148h+var_128], 8; ULONG
0x180009da6  xor     r9d, r9d; int
0x180009da9  xor     r8d, r8d; int
0x180009dac  lea     rdx, word_18000FC22; int
0x180009db3  lea     rcx, dword_180014000; int
0x180009dba  call    _tlgWriteTransfer_EventWriteTransfer
0x180009dbf  mov     rcx, [rsp+148h+var_F0]
0x180009dc4  mov     rax, [rcx]
0x180009dc7  lea     rdx, [rsp+148h+dwProcessId]
0x180009dcc  mov     rax, [rax+40h]
0x180009dd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dd5  nop
0x180009dd6  lea     rcx, [rsp+148h+var_E8]
0x180009ddb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180009de0  nop
0x180009de1  mov     rcx, [rsp+148h+var_F0]
0x180009de6  test    rcx, rcx
0x180009de9  jz      short loc_180009DFD
0x180009deb  mov     [rsp+148h+var_F0], r14
0x180009df0  mov     rax, [rcx]
0x180009df3  mov     rax, [rax+10h]
0x180009df7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dfc  nop
0x180009dfd  mov     rcx, [rsp+148h+var_18]
0x180009e05  xor     rcx, rsp; StackCookie
0x180009e08  call    __security_check_cookie
0x180009e0d  lea     r11, [rsp+148h+var_8]
0x180009e15  mov     rsi, [r11+10h]
0x180009e19  mov     rdi, [r11+28h]
0x180009e1d  mov     rsp, r11
0x180009e20  pop     r14
0x180009e22  retn
```
