# CPlaybackManager::ApplicationChanged(IImmersiveApplication *,IMM_APP_CHANGED,HWND__ *)

- ea: `0x1800de9d0`
- end: `0x1800dec9e`
- name: `?ApplicationChanged@CPlaybackManager@@UEAAJPEAUIImmersiveApplication@@W4IMM_APP_CHANGED@@PEAUHWND__@@@Z`
- size: `718`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x180013244`
- `0x1800de39c`
- `0x1800de9d0`
- `0x1800df0fc`
- `0x1800dfc40`
- `0x1800e0664`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800dec7d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800dec7d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800dea61`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800debae`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800dea61`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800debae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800deb57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dec66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800deb57`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dec66`

## pseudocode

```c
__int64 __fastcall CPlaybackManager::ApplicationChanged(
        struct _RTL_CRITICAL_SECTION *a1,
        __int64 (__fastcall ***a2)(__int64, GUID *, __int64 *),
        unsigned int a3)
{
  unsigned __int64 v4; // rax
  CPlaybackManager *p_LockSemaphore; // rdi
  struct _RTL_CRITICAL_SECTION *v6; // r14
  __int64 (__fastcall **v7)(__int64, GUID *, __int64 *); // rax
  __int64 (__fastcall *v8)(__int64, GUID *, __int64 *); // rbx
  unsigned int v9; // eax
  struct _RTL_CRITICAL_SECTION *v10; // rcx
  unsigned __int64 i; // rax
  HANDLE *v12; // r14
  struct _RTL_CRITICAL_SECTION *v13; // rdi
  __int64 (__fastcall **v14)(__int64, GUID *, __int64 *); // rax
  __int64 (__fastcall *v15)(__int64, GUID *, __int64 *); // rbx
  int v17; // [rsp+38h] [rbp-19h] BYREF
  __int64 v18; // [rsp+40h] [rbp-11h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-9h] BYREF
  int v20; // [rsp+50h] [rbp-1h] BYREF
  int v21; // [rsp+54h] [rbp+3h] BYREF
  int v22; // [rsp+58h] [rbp+7h] BYREF
  int v23[2]; // [rsp+60h] [rbp+Fh] BYREF
  unsigned __int64 v24; // [rsp+68h] [rbp+17h] BYREF
  _QWORD v25[5]; // [rsp+70h] [rbp+1Fh] BYREF
  unsigned int v26; // [rsp+C8h] [rbp+77h] BYREF

  v26 = a3;
  v17 = 1;
  v20 = 0;
  v22 = 0;
  v4 = 0;
  v23[0] = 0;
  v21 = 0;
  pv = 0;
  v24 = -1;
  while ( v4 < 4 )
  {
    if ( dword_180108230[v4] == a3 )
    {
      p_LockSemaphore = (CPlaybackManager *)&a1[-4].LockSemaphore;
      if ( LOBYTE(a1[4].LockCount) )
      {
        v6 = a1 + 3;
        EnterCriticalSection(a1 + 3);
        v17 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *), LPVOID *))(*a2)[4])(
                a2,
                &pv);
        if ( v17 >= 0 )
        {
          v7 = *a2;
          v18 = 0;
          v8 = *v7;
          Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v18);
          v17 = v8((__int64)a2, &GUID_b00297dd_eb90_48c8_99c0_f0b2d68213d3, &v18);
          if ( v17 >= 0 )
          {
            v17 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v18 + 24LL))(v18, &v24);
            if ( v17 >= 0 )
            {
              v17 = CPlaybackManager::ComputeAggregateApplicationState(p_LockSemaphore, v24, &v20, &v22, v23, &v21);
              if ( v17 >= 0 )
              {
                if ( v26 == 6 && v20 || v26 == 14 && v21 || v26 == 5 && v21 )
                {
                  v17 = -2147467260;
                }
                else
                {
                  v9 = CPlaybackManager::IamAppChanged_2_PbmInteractivityChanged(
                         p_LockSemaphore,
                         v26,
                         (unsigned int)v22);
                  v17 = CPlaybackManager::ReportAppInteractivityChange(p_LockSemaphore, pv, v24, v9);
                }
              }
            }
          }
          CoTaskMemFree(pv);
          Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v18);
        }
        if ( v6 )
        {
          v10 = v6;
LABEL_36:
          LeaveCriticalSection(v10);
        }
        return (unsigned int)v17;
      }
      break;
    }
    ++v4;
  }
  for ( i = 0; i < 2; ++i )
  {
    if ( dword_180108228[i] == a3 )
    {
      v12 = &a1[-4].LockSemaphore;
      if ( LOBYTE(a1[4].LockCount) )
      {
        v13 = a1 + 3;
        EnterCriticalSection(a1 + 3);
        v17 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(__int64, GUID *, __int64 *), LPVOID *))(*a2)[4])(
                a2,
                &pv);
        if ( v17 >= 0 )
        {
          v14 = *a2;
          v18 = 0;
          v15 = *v14;
          Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v18);
          v17 = v15((__int64)a2, &GUID_b00297dd_eb90_48c8_99c0_f0b2d68213d3, &v18);
          if ( v17 >= 0 )
          {
            *(_QWORD *)v23 = 0;
            v17 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v18 + 24LL))(v18, v23);
            if ( v17 >= 0 )
            {
              if ( v26 == 11 || v26 == 16 )
              {
                v25[1] = v12;
                v25[0] = &v17;
                v25[2] = &pv;
                v25[3] = v23;
                v25[4] = &v26;
                lambda_2e05f4b5582b515c2c6be785142243e4_::operator()(v25);
              }
              CoTaskMemFree(pv);
            }
          }
          Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v18);
        }
        if ( v13 )
        {
          v10 = v13;
          goto LABEL_36;
        }
      }
      return (unsigned int)v17;
    }
  }
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x1800de9d0  mov     rax, rsp
0x1800de9d3  mov     [rax+8], rbx
0x1800de9d7  mov     [rax+10h], rsi
0x1800de9db  mov     [rax+18h], r8d
0x1800de9df  push    rbp
0x1800de9e0  push    rdi
0x1800de9e1  push    r14
0x1800de9e3  lea     rbp, [rax-5Fh]
0x1800de9e7  sub     rsp, 90h
0x1800de9ee  mov     rsi, rdx
0x1800de9f1  mov     [rbp+57h+var_70], 1
0x1800de9f8  lea     rdx, __ImageBase
0x1800de9ff  mov     [rbp+57h+var_58], 0
0x1800dea06  mov     [rbp+57h+var_50], 0
0x1800dea0d  xor     eax, eax
0x1800dea0f  mov     [rbp+57h+var_48], 0
0x1800dea16  mov     [rbp+57h+var_54], 0
0x1800dea1d  mov     [rbp+57h+pv], 0
0x1800dea25  mov     [rbp+57h+var_40], 0FFFFFFFFFFFFFFFFh
0x1800dea2d  cmp     rax, 4
0x1800dea31  jnb     loc_1800DEB77
0x1800dea37  cmp     ds:rva dword_180108230[rdx+rax*4], r8d
0x1800dea3f  jz      short loc_1800DEA46
0x1800dea41  inc     rax
0x1800dea44  jmp     short loc_1800DEA2D
0x1800dea46  lea     rdi, [rcx-88h]
0x1800dea4d  cmp     byte ptr [rdi+130h], 0
0x1800dea54  jz      loc_1800DEB77
0x1800dea5a  lea     r14, [rcx+78h]
0x1800dea5e  mov     rcx, r14; lpCriticalSection
0x1800dea61  call    cs:__imp_EnterCriticalSection
0x1800dea67  mov     rax, [rsi]
0x1800dea6a  lea     rdx, [rbp+57h+pv]
0x1800dea6e  mov     rcx, rsi
0x1800dea71  mov     rax, [rax+20h]
0x1800dea75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dea7a  mov     [rbp+57h+var_70], eax
0x1800dea7d  test    eax, eax
0x1800dea7f  js      loc_1800DEB66
0x1800dea85  mov     rax, [rsi]
0x1800dea88  lea     rcx, [rbp+57h+var_68]
0x1800dea8c  mov     [rbp+57h+var_68], 0
0x1800dea94  mov     rbx, [rax]
0x1800dea97  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800dea9c  lea     r8, [rbp+57h+var_68]
0x1800deaa0  mov     rcx, rsi
0x1800deaa3  lea     rdx, _GUID_b00297dd_eb90_48c8_99c0_f0b2d68213d3
0x1800deaaa  mov     rax, rbx
0x1800deaad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800deab2  mov     [rbp+57h+var_70], eax
0x1800deab5  test    eax, eax
0x1800deab7  js      loc_1800DEB53
0x1800deabd  mov     rcx, [rbp+57h+var_68]
0x1800deac1  lea     rdx, [rbp+57h+var_40]
0x1800deac5  mov     rax, [rcx]
0x1800deac8  mov     rax, [rax+18h]
0x1800deacc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dead1  mov     [rbp+57h+var_70], eax
0x1800dead4  test    eax, eax
0x1800dead6  js      short loc_1800DEB53
0x1800dead8  mov     rdx, [rbp+57h+var_40]; unsigned __int64
0x1800deadc  lea     rax, [rbp+57h+var_54]
0x1800deae0  mov     [rsp+0A0h+var_78], rax; int *
0x1800deae5  lea     r9, [rbp+57h+var_50]; int *
0x1800deae9  lea     rax, [rbp+57h+var_48]
0x1800deaed  mov     rcx, rdi; this
0x1800deaf0  lea     r8, [rbp+57h+var_58]; int *
0x1800deaf4  mov     [rsp+0A0h+var_80], rax; int *
0x1800deaf9  call    ?ComputeAggregateApplicationState@CPlaybackManager@@AEAAJ_KPEAH111@Z; CPlaybackManager::ComputeAggregateApplicationState(unsigned __int64,int *,int *,int *,int *)
0x1800deafe  mov     [rbp+57h+var_70], eax
0x1800deb01  test    eax, eax
0x1800deb03  js      short loc_1800DEB53
0x1800deb05  mov     edx, [rbp+57h+arg_10]
0x1800deb08  cmp     edx, 6
0x1800deb0b  jnz     short loc_1800DEB13
0x1800deb0d  cmp     [rbp+57h+var_58], 0
0x1800deb11  jnz     short loc_1800DEB28
0x1800deb13  mov     eax, [rbp+57h+var_54]
0x1800deb16  cmp     edx, 0Eh
0x1800deb19  jnz     short loc_1800DEB1F
0x1800deb1b  test    eax, eax
0x1800deb1d  jnz     short loc_1800DEB28
0x1800deb1f  cmp     edx, 5
0x1800deb22  jnz     short loc_1800DEB31
0x1800deb24  test    eax, eax
0x1800deb26  jz      short loc_1800DEB31
0x1800deb28  mov     [rbp+57h+var_70], 80004004h
0x1800deb2f  jmp     short loc_1800DEB53
0x1800deb31  mov     r8d, [rbp+57h+var_50]
0x1800deb35  mov     rcx, rdi
0x1800deb38  call    ?IamAppChanged_2_PbmInteractivityChanged@CPlaybackManager@@AEAA?AW4__MIDL___MIDL_itf_playbackmanagerrpc_0000_0000_0001@@W4IMM_APP_CHANGED@@H@Z; CPlaybackManager::IamAppChanged_2_PbmInteractivityChanged(IMM_APP_CHANGED,int)
0x1800deb3d  mov     r8, [rbp+57h+var_40]
0x1800deb41  mov     r9d, eax
0x1800deb44  mov     rdx, [rbp+57h+pv]
0x1800deb48  mov     rcx, rdi
0x1800deb4b  call    ?ReportAppInteractivityChange@CPlaybackManager@@AEAAJPEBG_KW4__MIDL___MIDL_itf_playbackmanagerrpc_0000_0000_0001@@@Z; CPlaybackManager::ReportAppInteractivityChange(ushort const *,unsigned __int64,__MIDL___MIDL_itf_playbackmanagerrpc_0000_0000_0001)
0x1800deb50  mov     [rbp+57h+var_70], eax
0x1800deb53  mov     rcx, [rbp+57h+pv]; pv
0x1800deb57  call    cs:__imp_CoTaskMemFree
0x1800deb5d  lea     rcx, [rbp+57h+var_68]
0x1800deb61  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800deb66  test    r14, r14
0x1800deb69  jz      loc_1800DEC83
0x1800deb6f  mov     rcx, r14
0x1800deb72  jmp     loc_1800DEC7D
0x1800deb77  xor     eax, eax
0x1800deb79  cmp     rax, 2
0x1800deb7d  jnb     loc_1800DEC83
0x1800deb83  cmp     ds:rva dword_180108228[rdx+rax*4], r8d
0x1800deb8b  jz      short loc_1800DEB92
0x1800deb8d  inc     rax
0x1800deb90  jmp     short loc_1800DEB79
0x1800deb92  lea     r14, [rcx-88h]
0x1800deb99  cmp     byte ptr [r14+130h], 0
0x1800deba1  jz      loc_1800DEC83
0x1800deba7  lea     rdi, [rcx+78h]
0x1800debab  mov     rcx, rdi; lpCriticalSection
0x1800debae  call    cs:__imp_EnterCriticalSection
0x1800debb4  mov     rax, [rsi]
0x1800debb7  lea     rdx, [rbp+57h+pv]
0x1800debbb  mov     rcx, rsi
0x1800debbe  mov     rax, [rax+20h]
0x1800debc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800debc7  mov     [rbp+57h+var_70], eax
0x1800debca  test    eax, eax
0x1800debcc  js      loc_1800DEC75
0x1800debd2  mov     rax, [rsi]
0x1800debd5  lea     rcx, [rbp+57h+var_68]
0x1800debd9  mov     [rbp+57h+var_68], 0
0x1800debe1  mov     rbx, [rax]
0x1800debe4  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800debe9  lea     r8, [rbp+57h+var_68]
0x1800debed  mov     rcx, rsi
0x1800debf0  lea     rdx, _GUID_b00297dd_eb90_48c8_99c0_f0b2d68213d3
0x1800debf7  mov     rax, rbx
0x1800debfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800debff  mov     [rbp+57h+var_70], eax
0x1800dec02  test    eax, eax
0x1800dec04  js      short loc_1800DEC6C
0x1800dec06  mov     rcx, [rbp+57h+var_68]
0x1800dec0a  lea     rdx, [rbp+57h+var_48]
0x1800dec0e  mov     qword ptr [rbp+57h+var_48], 0
0x1800dec16  mov     rax, [rcx]
0x1800dec19  mov     rax, [rax+18h]
0x1800dec1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dec22  mov     [rbp+57h+var_70], eax
0x1800dec25  test    eax, eax
0x1800dec27  js      short loc_1800DEC6C
0x1800dec29  cmp     [rbp+57h+arg_10], 0Bh
0x1800dec2d  jz      short loc_1800DEC35
0x1800dec2f  cmp     [rbp+57h+arg_10], 10h
0x1800dec33  jnz     short loc_1800DEC62
0x1800dec35  lea     rax, [rbp+57h+var_70]
0x1800dec39  mov     [rbp+57h+var_30], r14
0x1800dec3d  mov     [rbp+57h+var_38], rax
0x1800dec41  lea     rcx, [rbp+57h+var_38]
0x1800dec45  lea     rax, [rbp+57h+pv]
0x1800dec49  mov     [rbp+57h+var_28], rax
0x1800dec4d  lea     rax, [rbp+57h+var_48]
0x1800dec51  mov     [rbp+57h+var_20], rax
0x1800dec55  lea     rax, [rbp+57h+arg_10]
0x1800dec59  mov     [rbp+57h+var_18], rax
0x1800dec5d  call    _lambda_2e05f4b5582b515c2c6be785142243e4___operator__
0x1800dec62  mov     rcx, [rbp+57h+pv]; pv
0x1800dec66  call    cs:__imp_CoTaskMemFree
0x1800dec6c  lea     rcx, [rbp+57h+var_68]
0x1800dec70  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800dec75  test    rdi, rdi
0x1800dec78  jz      short loc_1800DEC83
0x1800dec7a  mov     rcx, rdi; lpCriticalSection
0x1800dec7d  call    cs:__imp_LeaveCriticalSection
0x1800dec83  mov     eax, [rbp+57h+var_70]
0x1800dec86  lea     r11, [rsp+0A0h+var_10]
0x1800dec8e  mov     rbx, [r11+20h]
0x1800dec92  mov     rsi, [r11+28h]
0x1800dec96  mov     rsp, r11
0x1800dec99  pop     r14
0x1800dec9b  pop     rdi
0x1800dec9c  pop     rbp
0x1800dec9d  retn
```
