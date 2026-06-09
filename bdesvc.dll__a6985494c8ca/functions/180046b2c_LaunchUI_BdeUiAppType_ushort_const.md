# LaunchUI(BdeUiAppType,ushort const *)

- ea: `0x180046b2c`
- end: `0x180046d00`
- name: `?LaunchUI@@YAJW4BdeUiAppType@@PEBG@Z`
- size: `468`
- prototype: `int __high(enum BdeUiAppType, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180027ca4`

## callees

- `0x180009f30`
- `0x180009f60`
- `0x18001d09c`
- `0x180023c1c`
- `0x180034070`
- `0x18004694c`
- `0x180046a50`
- `0x180046b2c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180046cd6`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180046cd6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180046bf7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180046bf7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall LaunchUI(unsigned int a1, const unsigned __int16 *a2)
{
  unsigned int v4; // eax
  int v5; // edi
  PVOID *v6; // rcx
  unsigned int v7; // eax
  LPVOID v8; // r14
  _bstr_t *v9; // rax
  __int64 v10; // r8
  __int64 v12; // r9
  _BYTE v13[8]; // [rsp+30h] [rbp-68h] BYREF
  int v14; // [rsp+38h] [rbp-60h] BYREF
  const _com_error *v15; // [rsp+40h] [rbp-58h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-50h] BYREF

  v13[0] = 0;
  ppv = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b44aeec6d25238c9cd95b2ffd1fa0196_Traceguids);
  v4 = CInitializeCom::Initialize((CInitializeCom *)v13);
  v5 = v4;
  if ( !v4 )
    goto LABEL_9;
  v6 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_b44aeec6d25238c9cd95b2ffd1fa0196_Traceguids, v4);
    v6 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v5 >= 0 )
  {
LABEL_9:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
    v7 = CoCreateInstance(&stru_180088218, 0, 4u, &GUID_8961f0a0_ff62_403b_91b4_7b9280241ceb, &ppv);
    v5 = v7;
    if ( !v7 )
      goto LABEL_14;
    v6 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_b44aeec6d25238c9cd95b2ffd1fa0196_Traceguids, v7);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v5 >= 0 )
    {
LABEL_14:
      v8 = ppv;
      try
      {
        v9 = _bstr_t::_bstr_t((_bstr_t *)&v14, a2);
        BdeUISrvLib::IBDEUILauncher::BdeUIProcessStart(v8, a1, v10, v9);
      }
      catch ( const _com_error *v15 )
      {
        v12 = *((unsigned int *)v15 + 2);
        v14 = *((_DWORD *)v15 + 2);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_b44aeec6d25238c9cd95b2ffd1fa0196_Traceguids, v12);
        v5 = v14;
      }
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v5 == -2147467238 )
  {
    if ( v6 == &WPP_GLOBAL_Control )
      goto LABEL_23;
    if ( (*((_BYTE *)v6 + 28) & 8) != 0 )
    {
      WPP_SF_(v6[2], 14, WPP_b44aeec6d25238c9cd95b2ffd1fa0196_Traceguids);
      v6 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( v6 != &WPP_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 0x20) != 0 )
    WPP_SF_(v6[2], 15, WPP_b44aeec6d25238c9cd95b2ffd1fa0196_Traceguids);
LABEL_23:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppv);
  if ( v13[0] )
    CoUninitialize();
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180046b2c  push    rbx
0x180046b2e  push    rsi
0x180046b2f  push    rdi
0x180046b30  push    r12
0x180046b32  push    r14
0x180046b34  push    r15
0x180046b36  sub     rsp, 68h
0x180046b3a  mov     rax, cs:__security_cookie
0x180046b41  xor     rax, rsp
0x180046b44  mov     [rsp+98h+var_48], rax
0x180046b49  mov     r12, rdx
0x180046b4c  mov     r15d, ecx
0x180046b4f  xor     ebx, ebx
0x180046b51  mov     [rsp+98h+var_68], bl
0x180046b55  mov     [rsp+98h+var_50], rbx
0x180046b5a  lea     rsi, WPP_GLOBAL_Control
0x180046b61  mov     rcx, cs:WPP_GLOBAL_Control
0x180046b68  cmp     rcx, rsi
0x180046b6b  jz      short loc_180046B86
0x180046b6d  test    byte ptr [rcx+1Ch], 20h
0x180046b71  jz      short loc_180046B86
0x180046b73  lea     edx, [rbx+0Ah]
0x180046b76  lea     r8, WPP_b44aeec6d25238c9cd95b2ffd1fa0196_Traceguids
0x180046b7d  mov     rcx, [rcx+10h]
0x180046b81  call    WPP_SF_
0x180046b86  lea     rcx, [rsp+98h+var_68]; this
0x180046b8b  call    ?Initialize@CInitializeCom@@QEAAJXZ; CInitializeCom::Initialize(void)
0x180046b90  mov     edi, eax
0x180046b92  test    eax, eax
0x180046b94  jz      short loc_180046BCF
0x180046b96  mov     rcx, cs:WPP_GLOBAL_Control
0x180046b9d  cmp     rcx, rsi
0x180046ba0  jz      short loc_180046BC7
0x180046ba2  test    byte ptr [rcx+1Ch], 40h
0x180046ba6  jz      short loc_180046BC7
0x180046ba8  mov     edx, 0Bh
0x180046bad  mov     r9d, eax
0x180046bb0  lea     r8, WPP_b44aeec6d25238c9cd95b2ffd1fa0196_Traceguids
0x180046bb7  mov     rcx, [rcx+10h]
0x180046bbb  call    WPP_SF_d
0x180046bc0  mov     rcx, cs:WPP_GLOBAL_Control
0x180046bc7  test    edi, edi
0x180046bc9  js      loc_180046C75
0x180046bcf  lea     rcx, [rsp+98h+var_50]
0x180046bd4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180046bd9  lea     rax, [rsp+98h+var_50]
0x180046bde  mov     [rsp+98h+ppv], rax; ppv
0x180046be3  lea     r9, _GUID_8961f0a0_ff62_403b_91b4_7b9280241ceb; riid
0x180046bea  xor     edx, edx; pUnkOuter
0x180046bec  lea     r8d, [rdx+4]; dwClsContext
0x180046bf0  lea     rcx, stru_180088218; rclsid
0x180046bf7  call    cs:__imp_CoCreateInstance
0x180046bfe  nop     dword ptr [rax+rax+00h]
0x180046c03  mov     edi, eax
0x180046c05  test    eax, eax
0x180046c07  jz      short loc_180046C3E
0x180046c09  mov     rcx, cs:WPP_GLOBAL_Control
0x180046c10  cmp     rcx, rsi
0x180046c13  jz      short loc_180046C3A
0x180046c15  test    byte ptr [rcx+1Ch], 40h
0x180046c19  jz      short loc_180046C3A
0x180046c1b  mov     edx, 0Ch
0x180046c20  mov     r9d, eax
0x180046c23  lea     r8, WPP_b44aeec6d25238c9cd95b2ffd1fa0196_Traceguids
0x180046c2a  mov     rcx, [rcx+10h]
0x180046c2e  call    WPP_SF_d
0x180046c33  mov     rcx, cs:WPP_GLOBAL_Control
0x180046c3a  test    edi, edi
0x180046c3c  js      short loc_180046C75
0x180046c3e  mov     r14, [rsp+98h+var_50]
0x180046c43  mov     rdx, r12; unsigned __int16 *
0x180046c46  lea     rcx, [rsp+98h+var_60]; this
0x180046c4b  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x180046c50  mov     r9, rax
0x180046c53  mov     edx, r15d
0x180046c56  mov     rcx, r14
0x180046c59  call    ?BdeUIProcessStart@IBDEUILauncher@BdeUISrvLib@@QEAAJJJV_bstr_t@@@Z; BdeUISrvLib::IBDEUILauncher::BdeUIProcessStart(long,long,_bstr_t)
0x180046c5e  nop
0x180046c5f  jmp     short loc_180046C6E
0x180046c61  xor     ebx, ebx
0x180046c63  lea     rsi, WPP_GLOBAL_Control
0x180046c6a  mov     edi, [rsp+98h+var_60]
0x180046c6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180046c75  cmp     edi, 8000401Ah
0x180046c7b  jnz     short loc_180046CA4
0x180046c7d  cmp     rcx, rsi
0x180046c80  jz      short loc_180046CC5
0x180046c82  test    byte ptr [rcx+1Ch], 8
0x180046c86  jz      short loc_180046CA4
0x180046c88  mov     edx, 0Eh
0x180046c8d  lea     r8, WPP_b44aeec6d25238c9cd95b2ffd1fa0196_Traceguids
0x180046c94  mov     rcx, [rcx+10h]
0x180046c98  call    WPP_SF_
0x180046c9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180046ca4  cmp     rcx, rsi
0x180046ca7  jz      short loc_180046CC5
0x180046ca9  test    byte ptr [rcx+1Ch], 20h
0x180046cad  jz      short loc_180046CC5
0x180046caf  mov     edx, 0Fh
0x180046cb4  lea     r8, WPP_b44aeec6d25238c9cd95b2ffd1fa0196_Traceguids
0x180046cbb  mov     rcx, [rcx+10h]
0x180046cbf  call    WPP_SF_
0x180046cc4  nop
0x180046cc5  lea     rcx, [rsp+98h+var_50]
0x180046cca  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180046ccf  nop
0x180046cd0  cmp     [rsp+98h+var_68], bl
0x180046cd4  jz      short loc_180046CE2
0x180046cd6  call    cs:__imp_CoUninitialize
0x180046cdd  nop     dword ptr [rax+rax+00h]
0x180046ce2  mov     eax, edi
0x180046ce4  mov     rcx, [rsp+98h+var_48]
0x180046ce9  xor     rcx, rsp; StackCookie
0x180046cec  call    __security_check_cookie
0x180046cf1  add     rsp, 68h
0x180046cf5  pop     r15
0x180046cf7  pop     r14
0x180046cf9  pop     r12
0x180046cfb  pop     rdi
0x180046cfc  pop     rsi
0x180046cfd  pop     rbx
0x180046cfe  retn
```
