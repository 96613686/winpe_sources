# FSMonitorService::HandleCameraControlNotification(IMFAsyncResult *)

- ea: `0x180008a30`
- end: `0x180008d73`
- name: `?HandleCameraControlNotification@FSMonitorService@@IEAAXPEAUIMFAsyncResult@@@Z`
- size: `835`
- prototype: `void __fastcall(FSMonitorService *__hidden this, struct IMFAsyncResult *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task`

## callers

- `0x180009f10`

## callees

- `0x180002346`
- `0x180006a98`
- `0x180006cc0`
- `0x18000723c`
- `0x180008a30`
- `0x18000afb0`
- `0x18000d1e0`
- `0x18000d4f8`
- `0x18004d010`

## import_xrefs

- `ntdll!RtlPublishWnfStateData` at `0x180008c45`
- `ntdll!RtlPublishWnfStateData` at `0x180008c8c`
- `ntdll!RtlPublishWnfStateData` at `0x180008c45`
- `ntdll!RtlPublishWnfStateData` at `0x180008c8c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008a4f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008a4f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180008d6c`

## pseudocode

```c
void __fastcall FSMonitorService::HandleCameraControlNotification(FSMonitorService *this, struct IMFAsyncResult *a2)
{
  const struct std::nothrow_t *v3; // rdx
  bool v4; // zf
  const struct std::nothrow_t *unique; // rax
  const struct std::nothrow_t *v6; // rdx
  char *v7; // rbx
  const struct std::nothrow_t *v8; // rax
  const struct std::nothrow_t *v9; // rdx
  char *v10; // rdi
  int v11; // r13d
  __int64 v12; // r12
  __int64 *v13; // rax
  __int64 v14; // rax
  int v15; // r15d
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rdx
  int v20; // eax
  __int64 v21; // rdx
  const struct std::nothrow_t *v22; // rdx
  void *v23[3]; // [rsp+30h] [rbp-18h] BYREF
  int v24; // [rsp+90h] [rbp+48h]
  void *v25; // [rsp+98h] [rbp+50h] BYREF
  unsigned int v26; // [rsp+A0h] [rbp+58h] BYREF
  void *v27; // [rsp+A8h] [rbp+60h] BYREF

  v25 = a2;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v4 = *((_DWORD *)this + 23) == 3;
  v23[0] = 0;
  v27 = 0;
  *((_BYTE *)this + 224) = 0;
  if ( v4 )
    goto LABEL_34;
  unique = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned char [0]>(&v25, 0x1000u);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(v23, unique);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v25, v6);
  v7 = (char *)v23[0];
  if ( !v23[0] )
  {
    if ( !g_wppLevels )
      goto LABEL_34;
    v21 = 140;
    goto LABEL_33;
  }
  memset_0(v23[0], 0, 0x1000u);
  v8 = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned char [0]>(&v25, 0x1000u);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(&v27, v8);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v25, v9);
  v10 = (char *)v27;
  if ( !v27 )
  {
    if ( !g_wppLevels )
      goto LABEL_34;
    v21 = 141;
LABEL_33:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v21,
      &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids,
      this,
      -2147024882);
    goto LABEL_34;
  }
  v24 = 0;
  v11 = 0;
  memset_0(v27, 0, 0x1000u);
  v12 = 0;
  if ( *((_DWORD *)this + 52) )
  {
    v13 = (__int64 *)((char *)this + 200);
    do
    {
      v14 = *v13;
      LODWORD(v25) = 0;
      v26 = 0;
      v15 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)(v14 + 8 * v12) + 72LL))(
              *(_QWORD *)(v14 + 8 * v12),
              &v26);
      if ( v15 < 0 )
        goto LABEL_26;
      if ( v26 )
      {
        if ( v26 + v24 >= 0x1000 )
        {
          if ( v26 + v11 >= 0x1000 )
          {
            if ( (unsigned __int8)byte_18005E5A5 >= 8u )
              WPP_SF_q(
                *((_QWORD *)WPP_GLOBAL_Control + 27),
                142,
                &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids,
                this);
          }
          else
          {
            v17 = *(_QWORD *)(*((_QWORD *)this + 25) + 8 * v12);
            v15 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD, void **))(*(_QWORD *)v17 + 80LL))(
                    v17,
                    &v10[v11],
                    v26,
                    &v25);
            if ( v15 < 0 )
              goto LABEL_26;
            v11 += (int)v25;
          }
        }
        else
        {
          v16 = *(_QWORD *)(*((_QWORD *)this + 25) + 8 * v12);
          v15 = (*(__int64 (__fastcall **)(__int64, char *, _QWORD, void **))(*(_QWORD *)v16 + 80LL))(
                  v16,
                  &v7[v24],
                  v26,
                  &v25);
          if ( v15 < 0 )
            goto LABEL_26;
          v24 += (int)v25;
        }
      }
      else
      {
        CTUnkArray<FSMCameraDeviceProperty>::RemoveAt((char *)this + 200, (unsigned int)v12);
        LODWORD(v12) = v12 - 1;
      }
      v12 = (unsigned int)(v12 + 1);
      v13 = (__int64 *)((char *)this + 200);
    }
    while ( (unsigned int)v12 < *((_DWORD *)this + 52) );
  }
  v18 = RtlPublishWnfStateData(WNF_KSV_KSCAMERACONTROLNOTIFICATIONPRIMARY, 0, v7, 4096, 0);
  v15 = v18 | 0x10000000;
  if ( v18 >= 0 )
  {
    if ( !v11 )
      goto LABEL_34;
    v20 = RtlPublishWnfStateData(WNF_KSV_KSCAMERACONTROLNOTIFICATIONSECONDARY, 0, v10, 4096, 0);
    v15 = v20 | 0x10000000;
    if ( v20 >= 0 )
      goto LABEL_34;
    if ( !g_wppLevels )
      goto LABEL_26;
    v19 = 144;
    goto LABEL_25;
  }
  if ( g_wppLevels )
  {
    v19 = 143;
LABEL_25:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v19, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, this, v15);
  }
LABEL_26:
  if ( v15 != -2147024882 && byte_18005E5A5 )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 145, &WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids, this, v15);
LABEL_34:
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v27, v3);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(v23, v22);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
}

```

## disassembly

```asm
0x180008a30  mov     [rsp-40h+arg_8], rdx
0x180008a35  push    rbp
0x180008a36  push    rbx
0x180008a37  push    rsi
0x180008a38  push    rdi
0x180008a39  push    r12
0x180008a3b  push    r13
0x180008a3d  push    r14
0x180008a3f  push    r15
0x180008a41  mov     rbp, rsp
0x180008a44  sub     rsp, 48h
0x180008a48  mov     r14, rcx
0x180008a4b  add     rcx, 30h ; '0'; lpCriticalSection
0x180008a4f  call    cs:__imp_EnterCriticalSection
0x180008a55  cmp     dword ptr [r14+5Ch], 3
0x180008a5a  mov     [rbp+var_18], 0
0x180008a62  mov     [rbp+arg_18], 0
0x180008a6a  mov     byte ptr [r14+0E0h], 0
0x180008a72  jz      loc_180008D46
0x180008a78  mov     edx, 1000h
0x180008a7d  lea     rcx, [rbp+arg_8]
0x180008a81  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x180008a86  mov     rdx, rax
0x180008a89  lea     rcx, [rbp+var_18]
0x180008a8d  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x180008a92  lea     rcx, [rbp+arg_8]
0x180008a96  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x180008a9b  mov     rbx, [rbp+var_18]
0x180008a9f  test    rbx, rbx
0x180008aa2  jz      loc_180008D16
0x180008aa8  xor     edx, edx; Val
0x180008aaa  mov     r8d, 1000h; Size
0x180008ab0  mov     rcx, rbx; void *
0x180008ab3  call    memset_0
0x180008ab8  mov     edx, 1000h
0x180008abd  lea     rcx, [rbp+arg_8]
0x180008ac1  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x180008ac6  mov     rdx, rax
0x180008ac9  lea     rcx, [rbp+arg_18]
0x180008acd  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x180008ad2  lea     rcx, [rbp+arg_8]
0x180008ad6  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x180008adb  mov     rdi, [rbp+arg_18]
0x180008adf  test    rdi, rdi
0x180008ae2  jz      loc_180008D06
0x180008ae8  xor     edx, edx; Val
0x180008aea  mov     [rbp+arg_0], 0
0x180008af1  mov     r8d, 1000h; Size
0x180008af7  mov     rcx, rdi; void *
0x180008afa  xor     r13d, r13d
0x180008afd  call    memset_0
0x180008b02  xor     r12d, r12d
0x180008b05  cmp     [r14+0D0h], r12d
0x180008b0c  jbe     loc_180008C2A
0x180008b12  lea     rax, [r14+0C8h]
0x180008b19  mov     rax, [rax]
0x180008b1c  lea     rdx, [rbp+arg_10]
0x180008b20  mov     dword ptr [rbp+arg_8], 0
0x180008b27  mov     [rbp+arg_10], 0
0x180008b2e  mov     rcx, [rax+r12*8]
0x180008b32  mov     rax, [rcx]
0x180008b35  mov     rax, [rax+48h]
0x180008b39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b3e  mov     r15d, eax
0x180008b41  test    eax, eax
0x180008b43  js      loc_180008CCB
0x180008b49  mov     r8d, [rbp+arg_10]
0x180008b4d  test    r8d, r8d
0x180008b50  jnz     short loc_180008B69
0x180008b52  mov     edx, r12d
0x180008b55  lea     rcx, [r14+0C8h]
0x180008b5c  call    ?RemoveAt@?$CTUnkArray@VFSMCameraDeviceProperty@@@@QEAAHK@Z; CTUnkArray<FSMCameraDeviceProperty>::RemoveAt(ulong)
0x180008b61  dec     r12d
0x180008b64  jmp     loc_180008C13
0x180008b69  mov     edx, [rbp+arg_0]
0x180008b6c  lea     eax, [r8+rdx]
0x180008b70  cmp     eax, 1000h
0x180008b75  jnb     short loc_180008BAB
0x180008b77  mov     rax, [r14+0C8h]
0x180008b7e  lea     r9, [rbp+arg_8]
0x180008b82  add     rdx, rbx
0x180008b85  mov     rcx, [rax+r12*8]
0x180008b89  mov     rax, [rcx]
0x180008b8c  mov     rax, [rax+50h]
0x180008b90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b95  mov     r15d, eax
0x180008b98  test    eax, eax
0x180008b9a  js      loc_180008CCB
0x180008ba0  mov     edx, [rbp+arg_0]
0x180008ba3  add     edx, dword ptr [rbp+arg_8]
0x180008ba6  mov     [rbp+arg_0], edx
0x180008ba9  jmp     short loc_180008C13
0x180008bab  lea     eax, [r8+r13]
0x180008baf  cmp     eax, 1000h
0x180008bb4  jnb     short loc_180008BE8
0x180008bb6  mov     rax, [r14+0C8h]
0x180008bbd  lea     r9, [rbp+arg_8]
0x180008bc1  mov     edx, r13d
0x180008bc4  add     rdx, rdi
0x180008bc7  mov     rcx, [rax+r12*8]
0x180008bcb  mov     rax, [rcx]
0x180008bce  mov     rax, [rax+50h]
0x180008bd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bd7  mov     r15d, eax
0x180008bda  test    eax, eax
0x180008bdc  js      loc_180008CCB
0x180008be2  add     r13d, dword ptr [rbp+arg_8]
0x180008be6  jmp     short loc_180008C13
0x180008be8  cmp     cs:byte_18005E5A5, 8
0x180008bef  jb      short loc_180008C13
0x180008bf1  mov     rcx, cs:WPP_GLOBAL_Control
0x180008bf8  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x180008bff  mov     edx, 8Eh
0x180008c04  mov     r9, r14
0x180008c07  mov     rcx, [rcx+0D8h]
0x180008c0e  call    WPP_SF_q
0x180008c13  inc     r12d
0x180008c16  lea     rax, [r14+0C8h]
0x180008c1d  cmp     r12d, [r14+0D0h]
0x180008c24  jb      loc_180008B19
0x180008c2a  mov     rcx, cs:WNF_KSV_KSCAMERACONTROLNOTIFICATIONPRIMARY
0x180008c31  mov     r9d, 1000h
0x180008c37  mov     r8, rbx
0x180008c3a  mov     [rsp+48h+var_28], 0
0x180008c43  xor     edx, edx
0x180008c45  call    cs:__imp_RtlPublishWnfStateData
0x180008c4b  mov     r15d, eax
0x180008c4e  mov     ebx, 10000000h
0x180008c53  or      r15d, ebx
0x180008c56  jge     short loc_180008C68
0x180008c58  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180008c5f  jb      short loc_180008CCB
0x180008c61  mov     edx, 8Fh
0x180008c66  jmp     short loc_180008CAC
0x180008c68  test    r13d, r13d
0x180008c6b  jz      loc_180008D46
0x180008c71  mov     rcx, cs:WNF_KSV_KSCAMERACONTROLNOTIFICATIONSECONDARY
0x180008c78  mov     r9d, 1000h
0x180008c7e  mov     r8, rdi
0x180008c81  mov     [rsp+48h+var_28], 0
0x180008c8a  xor     edx, edx
0x180008c8c  call    cs:__imp_RtlPublishWnfStateData
0x180008c92  mov     r15d, eax
0x180008c95  or      r15d, ebx
0x180008c98  jge     loc_180008D46
0x180008c9e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180008ca5  jb      short loc_180008CCB
0x180008ca7  mov     edx, 90h
0x180008cac  mov     rcx, cs:WPP_GLOBAL_Control
0x180008cb3  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x180008cba  mov     r9, r14
0x180008cbd  mov     dword ptr [rsp+48h+var_28], r15d
0x180008cc2  mov     rcx, [rcx+10h]
0x180008cc6  call    WPP_SF_qD
0x180008ccb  cmp     r15d, 8007000Eh
0x180008cd2  jz      short loc_180008D46
0x180008cd4  cmp     cs:byte_18005E5A5, 1
0x180008cdb  jb      short loc_180008D46
0x180008cdd  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ce4  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x180008ceb  mov     edx, 91h
0x180008cf0  mov     dword ptr [rsp+48h+var_28], r15d
0x180008cf5  mov     r9, r14
0x180008cf8  mov     rcx, [rcx+0D8h]
0x180008cff  call    WPP_SF_qD
0x180008d04  jmp     short loc_180008D46
0x180008d06  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180008d0d  jb      short loc_180008D46
0x180008d0f  mov     edx, 8Dh
0x180008d14  jmp     short loc_180008D24
0x180008d16  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180008d1d  jb      short loc_180008D46
0x180008d1f  mov     edx, 8Ch
0x180008d24  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d2b  lea     r8, WPP_734740b2bdb836e82b063d2e2b8b55ff_Traceguids
0x180008d32  mov     r9, r14
0x180008d35  mov     dword ptr [rsp+48h+var_28], 8007000Eh
0x180008d3d  mov     rcx, [rcx+10h]
0x180008d41  call    WPP_SF_qD
0x180008d46  lea     rcx, [rbp+arg_18]
0x180008d4a  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x180008d4f  lea     rcx, [rbp+var_18]
0x180008d53  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x180008d58  lea     rcx, [r14+30h]
0x180008d5c  add     rsp, 48h
0x180008d60  pop     r15
0x180008d62  pop     r14
0x180008d64  pop     r13
0x180008d66  pop     r12
0x180008d68  pop     rdi
0x180008d69  pop     rsi
0x180008d6a  pop     rbx
0x180008d6b  pop     rbp
0x180008d6c  jmp     cs:__imp_LeaveCriticalSection
```
