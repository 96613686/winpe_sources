# MFCreateVirtualCamera

- ea: `0x180030880`
- end: `0x180030c0e`
- name: `MFCreateVirtualCamera`
- size: `910`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180005fa0`
- `0x18000f518`
- `0x180030880`
- `0x180044f30`
- `0x180045900`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18003097e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18003097e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180030a67`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180030a67`

## pseudocode

```c
__int64 __fastcall MFCreateVirtualCamera(
        unsigned int a1,
        unsigned int a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7,
        _QWORD *a8)
{
  HRESULT v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  LPVOID v13; // rcx
  __int64 *v14; // rcx
  LPVOID v15; // rbx
  __int64 v16; // rax
  __int64 (__fastcall *v17)(LPVOID, _QWORD, GUID *, __int64 **); // rdi
  __int64 v18; // rcx
  __int64 *v19; // rbx
  __int64 v20; // rax
  __int64 (__fastcall *v21)(__int64 *, _QWORD, _QWORD, _QWORD, __int64, __int64, __int64, int, __int64 *); // rdi
  __int64 v23; // [rsp+70h] [rbp-90h] BYREF
  __int64 *v24; // [rsp+78h] [rbp-88h] BYREF
  LPVOID ppv; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v26; // [rsp+88h] [rbp-78h]
  unsigned int v27; // [rsp+8Ch] [rbp-74h]
  __int64 v28; // [rsp+90h] [rbp-70h]
  GUID pguid; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int16 v30[56]; // [rsp+B0h] [rbp-50h] BYREF

  v26 = a3;
  v27 = a2;
  v28 = a6;
  ppv = 0;
  v24 = 0;
  v23 = 0;
  memset_0(v30, 0, 0x6Cu);
  *(_QWORD *)&pguid.Data1 = 0;
  *(_QWORD *)pguid.Data4 = 0;
  if ( !a4 )
  {
    v10 = -2147024809;
    v11 = -2147024809;
    if ( !g_wppLevels )
      return v11;
    v12 = 150;
    goto LABEL_4;
  }
  if ( !a5 )
  {
    v10 = -2147024809;
    v11 = -2147024809;
    if ( !g_wppLevels )
      return v11;
    v12 = 151;
    goto LABEL_4;
  }
  if ( !a8 )
  {
    v11 = -2147467261;
    if ( !g_wppLevels )
      return v11;
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      152,
      &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids,
      0,
      -2147467261);
    goto LABEL_37;
  }
  *a8 = 0;
  v10 = CoCreateGuid(&pguid);
  v11 = v10;
  if ( v10 >= 0 )
  {
    v10 = StringCchPrintfW(
            v30,
            0x36u,
            L"vcam_session-{%08lX-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}",
            pguid.Data1,
            pguid.Data2,
            pguid.Data3,
            pguid.Data4[0],
            pguid.Data4[1],
            pguid.Data4[2],
            pguid.Data4[3],
            pguid.Data4[4],
            pguid.Data4[5],
            pguid.Data4[6],
            pguid.Data4[7]);
    v11 = v10;
    if ( v10 >= 0 )
    {
      v13 = ppv;
      ppv = 0;
      if ( v13 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v13 + 16LL))(v13);
      v10 = CoCreateInstance(
              &CLSID_FrameServerMonitorObjectFactory,
              0,
              1u,
              &GUID_473ae402_5e85_4176_ba86_285b5ce2cb94,
              &ppv);
      v11 = v10;
      if ( v10 >= 0 )
      {
        v14 = v24;
        v15 = ppv;
        v16 = *(_QWORD *)ppv;
        v24 = 0;
        v17 = *(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, __int64 **))(v16 + 24);
        if ( v14 )
          (*(void (__fastcall **)(__int64 *))(*v14 + 16))(v14);
        v10 = v17(v15, 0, &GUID_746ea290_a034_4497_8afd_952a87bdd3d5, &v24);
        v11 = v10;
        if ( v10 >= 0 )
        {
          v10 = (*(__int64 (__fastcall **)(__int64 *, __int64, unsigned __int16 *))(*v24 + 24))(v24, 5, v30);
          v11 = v10;
          if ( v10 >= 0 )
          {
            v18 = v23;
            v19 = v24;
            v20 = *v24;
            v23 = 0;
            v21 = *(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, _QWORD, __int64, __int64, __int64, int, __int64 *))(v20 + 72);
            if ( v18 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
            v10 = v21(v19, a1, v27, v26, a4, a5, v28, a7, &v23);
            v11 = v10;
            if ( v10 >= 0 )
            {
              *a8 = v23;
              v23 = 0;
            }
            else if ( g_wppLevels )
            {
              v12 = 158;
              goto LABEL_4;
            }
          }
          else if ( g_wppLevels )
          {
            v12 = 157;
            goto LABEL_4;
          }
        }
        else if ( g_wppLevels )
        {
          v12 = 156;
          goto LABEL_4;
        }
      }
      else if ( g_wppLevels )
      {
        v12 = 155;
        goto LABEL_4;
      }
    }
    else if ( g_wppLevels )
    {
      v12 = 154;
      goto LABEL_4;
    }
  }
  else if ( g_wppLevels )
  {
    v12 = 153;
LABEL_4:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids, 0, v10);
  }
LABEL_37:
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  if ( v24 )
    (*(void (__fastcall **)(__int64 *))(*v24 + 16))(v24);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v11;
}

```

## disassembly

```asm
0x180030880  push    rbp
0x180030882  push    rbx
0x180030883  push    rsi
0x180030884  push    rdi
0x180030885  push    r12
0x180030887  push    r13
0x180030889  push    r14
0x18003088b  push    r15
0x18003088d  lea     rbp, [rsp-38h]
0x180030892  sub     rsp, 138h
0x180030899  mov     rax, cs:__security_cookie
0x1800308a0  xor     rax, rsp
0x1800308a3  mov     [rbp+70h+var_50], rax
0x1800308a7  mov     rax, [rbp+70h+arg_28]
0x1800308ae  xor     esi, esi
0x1800308b0  mov     r15, [rbp+70h+arg_20]
0x1800308b7  mov     r13d, ecx
0x1800308ba  mov     r14, [rbp+70h+arg_38]
0x1800308c1  lea     rcx, [rbp+70h+var_C0]; void *
0x1800308c5  mov     [rbp+70h+var_E8], r8d
0x1800308c9  mov     r12, r9
0x1800308cc  mov     [rbp+70h+var_E4], edx
0x1800308cf  lea     r8d, [rsi+6Ch]; Size
0x1800308d3  xor     edx, edx; Val
0x1800308d5  mov     [rbp+70h+var_E0], rax
0x1800308d9  mov     [rbp+70h+var_F0], rsi
0x1800308dd  mov     [rsp+170h+var_F8], rsi
0x1800308e2  mov     [rsp+170h+var_100], rsi
0x1800308e7  call    memset_0
0x1800308ec  mov     qword ptr [rbp+70h+pguid.Data1], rsi
0x1800308f0  mov     qword ptr [rbp+70h+pguid.Data4], rsi
0x1800308f4  test    r12, r12
0x1800308f7  jnz     short loc_180030935
0x1800308f9  mov     eax, 80070057h
0x1800308fe  mov     ebx, eax
0x180030900  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180030907  jb      loc_180030BEC
0x18003090d  mov     edx, 96h
0x180030912  mov     dword ptr [rsp+170h+ppv], eax
0x180030916  mov     rcx, cs:WPP_GLOBAL_Control
0x18003091d  lea     r8, WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids
0x180030924  xor     r9d, r9d
0x180030927  mov     rcx, [rcx+10h]
0x18003092b  call    WPP_SF_qD
0x180030930  jmp     loc_180030BAB
0x180030935  test    r15, r15
0x180030938  jnz     short loc_180030955
0x18003093a  mov     eax, 80070057h
0x18003093f  mov     ebx, eax
0x180030941  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180030948  jb      loc_180030BEC
0x18003094e  mov     edx, 97h
0x180030953  jmp     short loc_180030912
0x180030955  test    r14, r14
0x180030958  jnz     short loc_180030977
0x18003095a  mov     ebx, 80004003h
0x18003095f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180030966  jb      loc_180030BEC
0x18003096c  mov     edx, 98h
0x180030971  mov     dword ptr [rsp+170h+ppv], ebx
0x180030975  jmp     short loc_180030916
0x180030977  lea     rcx, [rbp+70h+pguid]; pguid
0x18003097b  mov     [r14], rsi
0x18003097e  call    cs:__imp_CoCreateGuid
0x180030984  mov     ebx, eax
0x180030986  test    eax, eax
0x180030988  jns     short loc_1800309A1
0x18003098a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180030991  jb      loc_180030BAB
0x180030997  mov     edx, 99h
0x18003099c  jmp     loc_180030912
0x1800309a1  movzx   ecx, [rbp+70h+pguid.Data4+6]
0x1800309a5  movzx   edx, [rbp+70h+pguid.Data4+5]
0x1800309a9  movzx   r8d, [rbp+70h+pguid.Data4+4]
0x1800309ae  movzx   r9d, [rbp+70h+pguid.Data4+3]
0x1800309b3  movzx   eax, [rbp+70h+pguid.Data4+7]
0x1800309b7  movzx   r10d, [rbp+70h+pguid.Data4+2]
0x1800309bc  movzx   r11d, [rbp+70h+pguid.Data4+1]
0x1800309c1  movzx   ebx, [rbp+70h+pguid.Data4]
0x1800309c5  movzx   edi, [rbp+70h+pguid.Data3]
0x1800309c9  movzx   esi, [rbp+70h+pguid.Data2]
0x1800309cd  mov     [rsp+170h+var_108], eax
0x1800309d1  mov     [rsp+170h+var_110], ecx
0x1800309d5  lea     rcx, [rbp+70h+var_C0]; unsigned __int16 *
0x1800309d9  mov     [rsp+170h+var_118], edx
0x1800309dd  mov     edx, 36h ; '6'; unsigned __int64
0x1800309e2  mov     [rsp+170h+var_120], r8d
0x1800309e7  lea     r8, aVcamSession08l; "vcam_session-{%08lX-%04X-%04X-%02X%02X-"...
0x1800309ee  mov     [rsp+170h+var_128], r9d
0x1800309f3  mov     r9d, [rbp+70h+pguid.Data1]
0x1800309f7  mov     dword ptr [rsp+170h+var_130], r10d
0x1800309fc  mov     [rsp+170h+var_138], r11d
0x180030a01  mov     dword ptr [rsp+170h+var_140], ebx
0x180030a05  mov     dword ptr [rsp+170h+var_148], edi
0x180030a09  mov     dword ptr [rsp+170h+ppv], esi
0x180030a0d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180030a12  xor     esi, esi
0x180030a14  mov     ebx, eax
0x180030a16  test    eax, eax
0x180030a18  jns     short loc_180030A31
0x180030a1a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180030a21  jb      loc_180030BAB
0x180030a27  mov     edx, 9Ah
0x180030a2c  jmp     loc_180030912
0x180030a31  mov     rcx, [rbp+70h+var_F0]
0x180030a35  mov     [rbp+70h+var_F0], rsi
0x180030a39  test    rcx, rcx
0x180030a3c  jz      short loc_180030A4A
0x180030a3e  mov     rax, [rcx]
0x180030a41  mov     rax, [rax+10h]
0x180030a45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030a4a  xor     edx, edx; pUnkOuter
0x180030a4c  lea     rax, [rbp+70h+var_F0]
0x180030a50  lea     r9, _GUID_473ae402_5e85_4176_ba86_285b5ce2cb94; riid
0x180030a57  mov     [rsp+170h+ppv], rax; ppv
0x180030a5c  lea     rcx, CLSID_FrameServerMonitorObjectFactory; rclsid
0x180030a63  lea     r8d, [rdx+1]; dwClsContext
0x180030a67  call    cs:__imp_CoCreateInstance
0x180030a6d  mov     ebx, eax
0x180030a6f  test    eax, eax
0x180030a71  jns     short loc_180030A8A
0x180030a73  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180030a7a  jb      loc_180030BAB
0x180030a80  mov     edx, 9Bh
0x180030a85  jmp     loc_180030912
0x180030a8a  mov     rcx, [rsp+170h+var_F8]
0x180030a8f  mov     rbx, [rbp+70h+var_F0]
0x180030a93  mov     rax, [rbx]
0x180030a96  mov     [rsp+170h+var_F8], rsi
0x180030a9b  mov     rdi, [rax+18h]
0x180030a9f  test    rcx, rcx
0x180030aa2  jz      short loc_180030AB0
0x180030aa4  mov     rdx, [rcx]
0x180030aa7  mov     rax, [rdx+10h]
0x180030aab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030ab0  lea     r9, [rsp+170h+var_F8]
0x180030ab5  xor     edx, edx
0x180030ab7  lea     r8, _GUID_746ea290_a034_4497_8afd_952a87bdd3d5
0x180030abe  mov     rcx, rbx
0x180030ac1  mov     rax, rdi
0x180030ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030ac9  mov     ebx, eax
0x180030acb  test    eax, eax
0x180030acd  jns     short loc_180030AE6
0x180030acf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180030ad6  jb      loc_180030BAB
0x180030adc  mov     edx, 9Ch
0x180030ae1  jmp     loc_180030912
0x180030ae6  mov     rcx, [rsp+170h+var_F8]
0x180030aeb  lea     r8, [rbp+70h+var_C0]
0x180030aef  xor     r9d, r9d
0x180030af2  mov     rax, [rcx]
0x180030af5  lea     edx, [r9+5]
0x180030af9  mov     rax, [rax+18h]
0x180030afd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b02  mov     ebx, eax
0x180030b04  test    eax, eax
0x180030b06  jns     short loc_180030B1F
0x180030b08  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180030b0f  jb      loc_180030BAB
0x180030b15  mov     edx, 9Dh
0x180030b1a  jmp     loc_180030912
0x180030b1f  mov     rcx, [rsp+170h+var_100]
0x180030b24  mov     rbx, [rsp+170h+var_F8]
0x180030b29  mov     rax, [rbx]
0x180030b2c  mov     [rsp+170h+var_100], rsi
0x180030b31  mov     rdi, [rax+48h]
0x180030b35  test    rcx, rcx
0x180030b38  jz      short loc_180030B46
0x180030b3a  mov     rax, [rcx]
0x180030b3d  mov     rax, [rax+10h]
0x180030b41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b46  mov     r10d, [rbp+70h+arg_30]
0x180030b4d  lea     rax, [rsp+170h+var_100]
0x180030b52  mov     r9d, [rbp+70h+var_E8]
0x180030b56  mov     edx, r13d
0x180030b59  mov     r8d, [rbp+70h+var_E4]
0x180030b5d  mov     rcx, rbx
0x180030b60  mov     [rsp+170h+var_130], rax
0x180030b65  mov     rax, [rbp+70h+var_E0]
0x180030b69  mov     [rsp+170h+var_138], r10d
0x180030b6e  mov     [rsp+170h+var_140], rax
0x180030b73  mov     rax, rdi
0x180030b76  mov     [rsp+170h+var_148], r15
0x180030b7b  mov     [rsp+170h+ppv], r12
0x180030b80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030b85  mov     ebx, eax
0x180030b87  test    eax, eax
0x180030b89  jns     short loc_180030B9E
0x180030b8b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180030b92  jb      short loc_180030BAB
0x180030b94  mov     edx, 9Eh
0x180030b99  jmp     loc_180030912
0x180030b9e  mov     rax, [rsp+170h+var_100]
0x180030ba3  mov     [r14], rax
0x180030ba6  mov     [rsp+170h+var_100], rsi
0x180030bab  mov     rcx, [rsp+170h+var_100]
0x180030bb0  test    rcx, rcx
0x180030bb3  jz      short loc_180030BC1
0x180030bb5  mov     rax, [rcx]
0x180030bb8  mov     rax, [rax+10h]
0x180030bbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030bc1  mov     rcx, [rsp+170h+var_F8]
0x180030bc6  test    rcx, rcx
0x180030bc9  jz      short loc_180030BD7
0x180030bcb  mov     rax, [rcx]
0x180030bce  mov     rax, [rax+10h]
0x180030bd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030bd7  mov     rcx, [rbp+70h+var_F0]
0x180030bdb  test    rcx, rcx
0x180030bde  jz      short loc_180030BEC
0x180030be0  mov     rax, [rcx]
0x180030be3  mov     rax, [rax+10h]
0x180030be7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030bec  mov     eax, ebx
0x180030bee  mov     rcx, [rbp+70h+var_50]
0x180030bf2  xor     rcx, rsp; StackCookie
0x180030bf5  call    __security_check_cookie
0x180030bfa  add     rsp, 138h
0x180030c01  pop     r15
0x180030c03  pop     r14
0x180030c05  pop     r13
0x180030c07  pop     r12
0x180030c09  pop     rdi
0x180030c0a  pop     rsi
0x180030c0b  pop     rbx
0x180030c0c  pop     rbp
0x180030c0d  retn
```
