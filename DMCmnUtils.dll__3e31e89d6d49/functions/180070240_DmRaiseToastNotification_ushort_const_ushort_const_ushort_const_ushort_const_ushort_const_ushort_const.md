# DmRaiseToastNotification(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x180070240`
- end: `0x18007048d`
- name: `?DmRaiseToastNotification@@YAJPEBG00000@Z`
- size: `589`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180007270`
- `0x180064a44`
- `0x180070240`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800702ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800702ef`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800702df`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800702df`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070442`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180070442`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180070317`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180070317`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180070366`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180070366`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180070432`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180070432`

## string_xrefs

- `0x1800702a8`: `<toast launch="%1!ws!" activationType="%2!ws!"><visual><binding template="ToastGeneric"><text id="1">%3!ws!</text></binding></visual></toast>`
- `0x1800702af`: `<toast launch="%1!ws!" activationType="%2!ws!"><visual><binding template="ToastGeneric"><text id="1">%3!ws!</text><text id="2">%4!ws!</text></binding></visual></toast>`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DmRaiseToastNotification(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6)
{
  wchar_t *v8; // rdx
  signed int LastError; // eax
  int v10; // ebx
  HRESULT v11; // esi
  LPVOID v12; // rdi
  __int64 (__fastcall *v13)(LPVOID, __int64 *); // rbx
  __int64 v15; // [rsp+90h] [rbp-39h] BYREF
  LPVOID ppv; // [rsp+98h] [rbp-31h] BYREF
  int v17; // [rsp+A0h] [rbp-29h] BYREF
  WCHAR Buffer[4]; // [rsp+A8h] [rbp-21h] BYREF
  __int64 v19; // [rsp+B0h] [rbp-19h] BYREF
  int v20; // [rsp+B8h] [rbp-11h]
  va_list Arguments[2]; // [rsp+C0h] [rbp-9h] BYREF
  const unsigned __int16 *v22; // [rsp+D0h] [rbp+7h]
  const unsigned __int16 *v23; // [rsp+D8h] [rbp+Fh]

  v23 = 0;
  *(_QWORD *)Buffer = 0;
  ppv = 0;
  v15 = 0;
  Arguments[0] = (va_list)a3;
  Arguments[1] = (va_list)a4;
  if ( a5 )
  {
    v22 = a5;
    v23 = a6;
  }
  else
  {
    v22 = a6;
  }
  v8 = aToastLaunch1Ws_0;
  if ( !a5 )
    v8 = aToastLaunch1Ws;
  if ( FormatMessageW(0x2500u, v8, 0, 0, Buffer, 0, Arguments) )
  {
    v11 = CoInitializeEx(0, 0);
    if ( (int)(v11 + 0x80000000) < 0 || v11 == -2147417850 )
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
      v10 = CoCreateInstance(
              &GUID_0c9281f9_6da1_4006_8729_de6e6b61581c,
              0,
              0x17u,
              &GUID_df8e9480_ca73_448e_b8f0_da000f581428,
              &ppv);
      if ( v10 >= 0 )
      {
        v12 = ppv;
        v13 = *(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 24LL);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
        v10 = v13(v12, &v15);
        if ( v10 >= 0 )
        {
          v17 = 0;
          v19 = 0;
          v20 = 0;
          v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 *, _QWORD, int, _QWORD, const unsigned __int16 *, _QWORD, __int64 *, _DWORD, _DWORD, _QWORD, _QWORD, _QWORD, _DWORD, int *))(*(_QWORD *)v15 + 64LL))(
                  v15,
                  L"System",
                  a1,
                  0,
                  1,
                  *(_QWORD *)Buffer,
                  a2,
                  0,
                  &v19,
                  0,
                  0,
                  0,
                  0,
                  0,
                  0,
                  &v17);
        }
      }
    }
    else
    {
      v10 = v11;
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
    if ( v11 >= 0 )
      CoUninitialize();
    LocalFree(*(HLOCAL *)Buffer);
  }
  else
  {
    LastError = GetLastError();
    v10 = LastError;
    if ( LastError > 0 )
      v10 = (unsigned __int16)LastError | 0x80070000;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v15);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180070240  mov     [rsp-8+arg_10], rbx
0x180070245  mov     [rsp-8+arg_18], rsi
0x18007024a  push    rbp
0x18007024b  push    rdi
0x18007024c  push    r12
0x18007024e  push    r14
0x180070250  push    r15
0x180070252  lea     rbp, [rsp-27h]
0x180070257  sub     rsp, 0F0h
0x18007025e  mov     rax, cs:__security_cookie
0x180070265  xor     rax, rsp
0x180070268  mov     [rbp+47h+var_30], rax
0x18007026c  mov     r15, rdx
0x18007026f  mov     r14, rcx
0x180070272  xor     r12d, r12d
0x180070275  mov     [rbp+47h+var_38], r12
0x180070279  mov     qword ptr [rbp+47h+Buffer], r12
0x18007027d  mov     [rbp+47h+ppv], r12
0x180070281  mov     [rbp+47h+var_80], r12
0x180070285  mov     [rbp+47h+var_50], r8
0x180070289  mov     [rbp+47h+var_48], r9
0x18007028d  mov     rcx, [rbp+47h+arg_20]
0x180070291  mov     rax, [rbp+47h+arg_28]
0x180070295  test    rcx, rcx
0x180070298  jz      short loc_1800702A4
0x18007029a  mov     [rbp+47h+var_40], rcx
0x18007029e  mov     [rbp+47h+var_38], rax
0x1800702a2  jmp     short loc_1800702A8
0x1800702a4  mov     [rbp+47h+var_40], rax
0x1800702a8  lea     rax, aToastLaunch1Ws; "<toast launch=\"%1!ws!\" activationType"...
0x1800702af  lea     rdx, aToastLaunch1Ws_0; "<toast launch=\"%1!ws!\" activationType"...
0x1800702b6  test    rcx, rcx
0x1800702b9  cmovz   rdx, rax; lpSource
0x1800702bd  lea     rax, [rbp+47h+var_50]
0x1800702c1  mov     [rsp+110h+Arguments], rax; Arguments
0x1800702c6  mov     [rsp+110h+nSize], r12d; nSize
0x1800702cb  lea     rax, [rbp+47h+Buffer]
0x1800702cf  mov     [rsp+110h+lpBuffer], rax; lpBuffer
0x1800702d4  xor     r9d, r9d; dwLanguageId
0x1800702d7  xor     r8d, r8d; dwMessageId
0x1800702da  mov     ecx, 2500h; dwFlags
0x1800702df  call    cs:__imp_FormatMessageW
0x1800702e6  nop     dword ptr [rax+rax+00h]
0x1800702eb  test    eax, eax
0x1800702ed  jnz     short loc_180070313
0x1800702ef  call    cs:__imp_GetLastError
0x1800702f6  nop     dword ptr [rax+rax+00h]
0x1800702fb  mov     ebx, eax
0x1800702fd  test    eax, eax
0x1800702ff  jle     loc_18007044F
0x180070305  movzx   ebx, ax
0x180070308  or      ebx, 80070000h
0x18007030e  jmp     loc_18007044F
0x180070313  xor     edx, edx; dwCoInit
0x180070315  xor     ecx, ecx; pvReserved
0x180070317  call    cs:__imp_CoInitializeEx
0x18007031e  nop     dword ptr [rax+rax+00h]
0x180070323  mov     esi, eax
0x180070325  mov     eax, 80000000h
0x18007032a  lea     ecx, [rsi+rax]
0x18007032d  test    eax, ecx
0x18007032f  jnz     short loc_180070340
0x180070331  cmp     esi, 80010106h
0x180070337  jz      short loc_180070340
0x180070339  mov     ebx, esi
0x18007033b  jmp     loc_18007041C
0x180070340  lea     rcx, [rbp+47h+ppv]
0x180070344  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180070349  lea     rax, [rbp+47h+ppv]
0x18007034d  mov     [rsp+110h+lpBuffer], rax; ppv
0x180070352  lea     r9, _GUID_df8e9480_ca73_448e_b8f0_da000f581428; riid
0x180070359  xor     edx, edx; pUnkOuter
0x18007035b  lea     r8d, [rdx+17h]; dwClsContext
0x18007035f  lea     rcx, _GUID_0c9281f9_6da1_4006_8729_de6e6b61581c; rclsid
0x180070366  call    cs:__imp_CoCreateInstance
0x18007036d  nop     dword ptr [rax+rax+00h]
0x180070372  mov     ebx, eax
0x180070374  test    eax, eax
0x180070376  js      loc_18007041C
0x18007037c  mov     rdi, [rbp+47h+ppv]
0x180070380  mov     rax, [rdi]
0x180070383  mov     rbx, [rax+18h]
0x180070387  lea     rcx, [rbp+47h+var_80]
0x18007038b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180070390  lea     rdx, [rbp+47h+var_80]
0x180070394  mov     rcx, rdi
0x180070397  mov     rax, rbx
0x18007039a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007039f  mov     ebx, eax
0x1800703a1  test    eax, eax
0x1800703a3  js      short loc_18007041C
0x1800703a5  mov     [rbp+47h+var_70], r12d
0x1800703a9  xor     eax, eax
0x1800703ab  mov     rcx, [rbp+47h+var_80]
0x1800703af  mov     rdx, qword ptr [rbp+47h+Buffer]
0x1800703b3  mov     [rbp+47h+var_60], rax
0x1800703b7  mov     [rbp+47h+var_58], eax
0x1800703ba  mov     rax, [rcx]
0x1800703bd  lea     r8, [rbp+47h+var_70]
0x1800703c1  mov     [rsp+110h+var_98], r8
0x1800703c6  mov     [rsp+110h+var_A0], r12d
0x1800703cb  mov     [rsp+110h+var_A8], r12
0x1800703d0  mov     [rsp+110h+var_B0], r12
0x1800703d5  mov     [rsp+110h+var_B8], r12
0x1800703da  mov     [rsp+110h+var_C0], r12d
0x1800703df  mov     [rsp+110h+var_C8], r12d
0x1800703e4  lea     r8, [rbp+47h+var_60]
0x1800703e8  mov     [rsp+110h+var_D0], r8
0x1800703ed  mov     [rsp+110h+var_D8], r12
0x1800703f2  mov     [rsp+110h+Arguments], r15
0x1800703f7  mov     qword ptr [rsp+110h+nSize], rdx
0x1800703fc  mov     dword ptr [rsp+110h+lpBuffer], 1
0x180070404  xor     r9d, r9d
0x180070407  mov     r8, r14
0x18007040a  lea     rdx, aSystem; "System"
0x180070411  mov     rax, [rax+40h]
0x180070415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007041a  mov     ebx, eax
0x18007041c  lea     rcx, [rbp+47h+var_80]
0x180070420  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180070425  lea     rcx, [rbp+47h+ppv]
0x180070429  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007042e  test    esi, esi
0x180070430  js      short loc_18007043E
0x180070432  call    cs:__imp_CoUninitialize
0x180070439  nop     dword ptr [rax+rax+00h]
0x18007043e  mov     rcx, qword ptr [rbp+47h+Buffer]; hMem
0x180070442  call    cs:__imp_LocalFree
0x180070449  nop     dword ptr [rax+rax+00h]
0x18007044e  nop
0x18007044f  lea     rcx, [rbp+47h+var_80]
0x180070453  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180070458  nop
0x180070459  lea     rcx, [rbp+47h+ppv]
0x18007045d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180070462  mov     eax, ebx
0x180070464  mov     rcx, [rbp+47h+var_30]
0x180070468  xor     rcx, rsp; StackCookie
0x18007046b  call    __security_check_cookie
0x180070470  lea     r11, [rsp+110h+var_20]
0x180070478  mov     rbx, [r11+40h]
0x18007047c  mov     rsi, [r11+48h]
0x180070480  mov     rsp, r11
0x180070483  pop     r15
0x180070485  pop     r14
0x180070487  pop     r12
0x180070489  pop     rdi
0x18007048a  pop     rbp
0x18007048b  retn
```
