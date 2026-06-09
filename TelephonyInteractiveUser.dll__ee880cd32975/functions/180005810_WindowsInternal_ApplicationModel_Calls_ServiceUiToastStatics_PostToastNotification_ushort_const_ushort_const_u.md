# WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics::_PostToastNotification(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,int)

- ea: `0x180005810`
- end: `0x180005a88`
- name: `?_PostToastNotification@ServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@MEAAJPEBG0000H@Z`
- size: `632`
- prototype: `__int64 __fastcall(WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180004ef0`

## callees

- `0x180001dc0`
- `0x180004d8c`
- `0x180005810`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000586f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000586f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800058fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800058fd`

## pseudocode

```c
__int64 __fastcall WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics::_PostToastNotification(
        WindowsInternal::ApplicationModel::Calls::ServiceUiToastStatics *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        int a7)
{
  HRESULT v10; // eax
  __int64 v11; // r8
  int v12; // ebx
  __int64 v13; // r8
  __int64 v14; // r9
  _QWORD *v15; // rcx
  LPVOID v16; // rcx
  void (*v17)(void); // rax
  __int64 v18; // r8
  __int64 v19; // rax
  _QWORD *v20; // rcx
  LPVOID v21; // rcx
  __int64 v23; // r9
  __int64 v24; // r8
  _QWORD *v25; // rcx
  LPVOID v26; // rcx
  LPVOID ppv; // [rsp+98h] [rbp-39h] BYREF
  _QWORD *v28; // [rsp+A0h] [rbp-31h] BYREF
  int v29; // [rsp+A8h] [rbp-29h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+B0h] [rbp-21h] BYREF
  _BYTE v31[12]; // [rsp+C0h] [rbp-11h] BYREF

  ppv = 0;
  v10 = CoCreateInstance(
          &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c,
          0,
          4u,
          &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
          &ppv);
  v12 = v10;
  if ( v10 < 0 )
  {
    Log_HREvent((unsigned int)v10, 1, v11, 75);
LABEL_22:
    v26 = ppv;
    if ( !ppv )
      return (unsigned int)v12;
    ppv = 0;
    v17 = *(void (**)(void))(*(_QWORD *)v26 + 16LL);
LABEL_24:
    v17();
    return (unsigned int)v12;
  }
  v28 = 0;
  v12 = (*(__int64 (__fastcall **)(LPVOID, _QWORD **))(*(_QWORD *)ppv + 24LL))(ppv, &v28);
  if ( v12 < 0 )
  {
    v14 = 78;
LABEL_5:
    Log_HREvent((unsigned int)v12, 1, v13, v14);
    v15 = v28;
    if ( v28 )
    {
      v28 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v15 + 16LL))(v15);
    }
    v16 = ppv;
    if ( !ppv )
      return (unsigned int)v12;
    ppv = 0;
    v17 = *(void (**)(void))(*(_QWORD *)v16 + 16LL);
    goto LABEL_24;
  }
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  *(_QWORD *)v31 = 0;
  if ( !is_mul_ok(0x989680u, 0x78u) )
  {
    v23 = 154;
LABEL_20:
    v12 = -2147024362;
    Log_HREvent(2147942934LL, 1, v18, v23);
    Log_HREvent(2147942934LL, 1, v24, 82);
    v25 = v28;
    if ( v28 )
    {
      v28 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v25 + 16LL))(v25);
    }
    goto LABEL_22;
  }
  if ( *(_QWORD *)&SystemTimeAsFileTime + 1200000000LL < *(unsigned __int64 *)&SystemTimeAsFileTime )
  {
    v23 = 157;
    goto LABEL_20;
  }
  *(_QWORD *)&v31[4] = *(_QWORD *)&SystemTimeAsFileTime + 1200000000LL;
  v29 = 0;
  v19 = *v28;
  *(_DWORD *)v31 = 1;
  v12 = (*(__int64 (__fastcall **)(_QWORD *, const unsigned __int16 *, const unsigned __int16 *, _QWORD, int, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, _BYTE *, _DWORD, _DWORD, _QWORD, _QWORD, _QWORD, int, int *))(v19 + 64))(
          v28,
          a2,
          a3,
          0,
          1,
          a4,
          a5,
          a6,
          v31,
          0,
          0,
          0,
          0,
          0,
          a7,
          &v29);
  if ( v12 < 0 )
  {
    v14 = 101;
    goto LABEL_5;
  }
  v20 = v28;
  if ( v28 )
  {
    v28 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v20 + 16LL))(v20);
  }
  v21 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v21 + 16LL))(v21);
  }
  return 0;
}

```

## disassembly

```asm
0x180005810  mov     [rsp-8+arg_0], rbx
0x180005815  push    rbp
0x180005816  push    rsi
0x180005817  push    rdi
0x180005818  push    r12
0x18000581a  push    r13
0x18000581c  push    r14
0x18000581e  push    r15
0x180005820  lea     rbp, [rsp-0Fh]
0x180005825  sub     rsp, 0E0h
0x18000582c  mov     rax, cs:__security_cookie
0x180005833  xor     rax, rsp
0x180005836  mov     [rbp+3Fh+var_40], rax
0x18000583a  mov     r15, [rbp+3Fh+arg_20]
0x18000583e  lea     rax, [rbp+3Fh+var_78]
0x180005842  mov     r12, [rbp+3Fh+arg_28]
0x180005846  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c; rclsid
0x18000584d  xor     r13d, r13d
0x180005850  mov     [rsp+110h+ppv], rax; ppv
0x180005855  mov     r14, r9
0x180005858  mov     [rbp+3Fh+var_78], r13
0x18000585c  mov     rsi, r8
0x18000585f  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x180005866  mov     rdi, rdx
0x180005869  xor     edx, edx; pUnkOuter
0x18000586b  lea     r8d, [r13+4]; dwClsContext
0x18000586f  call    cs:__imp_CoCreateInstance
0x180005875  mov     ebx, eax
0x180005877  test    eax, eax
0x180005879  jns     short loc_18000588F
0x18000587b  lea     edx, [r13+1]
0x18000587f  mov     ecx, eax
0x180005881  lea     r9d, [r13+4Bh]
0x180005885  call    Log_HREvent
0x18000588a  jmp     loc_180005A46
0x18000588f  mov     rcx, [rbp+3Fh+var_78]
0x180005893  lea     rdx, [rbp+3Fh+var_70]
0x180005897  mov     [rbp+3Fh+var_70], r13
0x18000589b  mov     rax, [rcx]
0x18000589e  mov     rax, [rax+18h]
0x1800058a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058a7  mov     ebx, eax
0x1800058a9  test    eax, eax
0x1800058ab  jns     short loc_1800058F5
0x1800058ad  mov     r9d, 4Eh ; 'N'
0x1800058b3  mov     edx, 1
0x1800058b8  mov     ecx, ebx
0x1800058ba  call    Log_HREvent
0x1800058bf  mov     rcx, [rbp+3Fh+var_70]
0x1800058c3  test    rcx, rcx
0x1800058c6  jz      short loc_1800058D8
0x1800058c8  mov     [rbp+3Fh+var_70], r13
0x1800058cc  mov     rdx, [rcx]
0x1800058cf  mov     rax, [rdx+10h]
0x1800058d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058d8  mov     rcx, [rbp+3Fh+var_78]
0x1800058dc  test    rcx, rcx
0x1800058df  jz      loc_180005A5F
0x1800058e5  mov     [rbp+3Fh+var_78], r13
0x1800058e9  mov     rax, [rcx]
0x1800058ec  mov     rax, [rax+10h]
0x1800058f0  jmp     loc_180005A5A
0x1800058f5  lea     rcx, [rbp+3Fh+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800058f9  mov     qword ptr [rbp+3Fh+SystemTimeAsFileTime.dwLowDateTime], r13
0x1800058fd  call    cs:__imp_GetSystemTimeAsFileTime
0x180005903  mov     eax, [rbp+3Fh+SystemTimeAsFileTime.dwHighDateTime]
0x180005906  mov     ecx, 989680h
0x18000590b  mov     dword ptr [rbp+3Fh+var_80+4], eax
0x18000590e  mov     eax, [rbp+3Fh+SystemTimeAsFileTime.dwLowDateTime]
0x180005911  mov     dword ptr [rbp+3Fh+var_80], eax
0x180005914  mov     eax, 78h ; 'x'
0x180005919  mul     rcx
0x18000591c  mov     [rbp+3Fh+var_50], r13
0x180005920  test    rdx, rdx
0x180005923  jnz     loc_180005A06
0x180005929  add     rax, [rbp+3Fh+var_80]
0x18000592d  cmp     rax, [rbp+3Fh+var_80]
0x180005931  jb      loc_1800059FE
0x180005937  mov     r11, [rbp+3Fh+var_70]
0x18000593b  xor     r9d, r9d
0x18000593e  mov     [rbp+3Fh+var_80], rax
0x180005942  mov     r8, rsi
0x180005945  mov     ecx, dword ptr [rbp+3Fh+var_80+4]
0x180005948  mov     rdx, rdi
0x18000594b  mov     dword ptr [rbp+3Fh+var_50+4], eax
0x18000594e  mov     [rbp+3Fh+var_68], r13d
0x180005952  mov     rax, [r11]
0x180005955  mov     [rbp+3Fh+var_48], ecx
0x180005958  mov     rcx, r11
0x18000595b  mov     dword ptr [rbp+3Fh+var_50], 1
0x180005962  mov     r10, [rax+40h]
0x180005966  lea     rax, [rbp+3Fh+var_68]
0x18000596a  mov     [rsp+110h+var_98], rax
0x18000596f  mov     eax, [rbp+3Fh+arg_30]
0x180005972  mov     [rsp+110h+var_A0], eax
0x180005976  lea     rax, [rbp+3Fh+var_50]
0x18000597a  mov     [rsp+110h+var_A8], r13
0x18000597f  mov     [rsp+110h+var_B0], r13
0x180005984  mov     [rsp+110h+var_B8], r13
0x180005989  mov     [rsp+110h+var_C0], r13d
0x18000598e  mov     [rsp+110h+var_C8], r13d
0x180005993  mov     [rsp+110h+var_D0], rax
0x180005998  mov     rax, r10
0x18000599b  mov     [rsp+110h+var_D8], r12
0x1800059a0  mov     [rsp+110h+var_E0], r15
0x1800059a5  mov     [rsp+110h+var_E8], r14
0x1800059aa  mov     dword ptr [rsp+110h+ppv], 1
0x1800059b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059b7  mov     ebx, eax
0x1800059b9  test    eax, eax
0x1800059bb  jns     short loc_1800059C8
0x1800059bd  mov     r9d, 65h ; 'e'
0x1800059c3  jmp     loc_1800058B3
0x1800059c8  mov     rcx, [rbp+3Fh+var_70]
0x1800059cc  test    rcx, rcx
0x1800059cf  jz      short loc_1800059E1
0x1800059d1  mov     [rbp+3Fh+var_70], r13
0x1800059d5  mov     rax, [rcx]
0x1800059d8  mov     rax, [rax+10h]
0x1800059dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059e1  mov     rcx, [rbp+3Fh+var_78]
0x1800059e5  test    rcx, rcx
0x1800059e8  jz      short loc_1800059FA
0x1800059ea  mov     [rbp+3Fh+var_78], r13
0x1800059ee  mov     rax, [rcx]
0x1800059f1  mov     rax, [rax+10h]
0x1800059f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059fa  xor     eax, eax
0x1800059fc  jmp     short loc_180005A61
0x1800059fe  mov     r9d, 9Dh
0x180005a04  jmp     short loc_180005A0C
0x180005a06  mov     r9d, 9Ah
0x180005a0c  mov     ebx, 80070216h
0x180005a11  mov     edx, 1
0x180005a16  mov     ecx, ebx
0x180005a18  call    Log_HREvent
0x180005a1d  mov     edx, 1
0x180005a22  mov     ecx, ebx
0x180005a24  lea     r9d, [rdx+51h]
0x180005a28  call    Log_HREvent
0x180005a2d  mov     rcx, [rbp+3Fh+var_70]
0x180005a31  test    rcx, rcx
0x180005a34  jz      short loc_180005A46
0x180005a36  mov     [rbp+3Fh+var_70], r13
0x180005a3a  mov     rax, [rcx]
0x180005a3d  mov     rax, [rax+10h]
0x180005a41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a46  mov     rcx, [rbp+3Fh+var_78]
0x180005a4a  test    rcx, rcx
0x180005a4d  jz      short loc_180005A5F
0x180005a4f  mov     [rbp+3Fh+var_78], r13
0x180005a53  mov     rdx, [rcx]
0x180005a56  mov     rax, [rdx+10h]
0x180005a5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a5f  mov     eax, ebx
0x180005a61  mov     rcx, [rbp+3Fh+var_40]
0x180005a65  xor     rcx, rsp; StackCookie
0x180005a68  call    __security_check_cookie
0x180005a6d  mov     rbx, [rsp+110h+arg_0]
0x180005a75  add     rsp, 0E0h
0x180005a7c  pop     r15
0x180005a7e  pop     r14
0x180005a80  pop     r13
0x180005a82  pop     r12
0x180005a84  pop     rdi
0x180005a85  pop     rsi
0x180005a86  pop     rbp
0x180005a87  retn
```
