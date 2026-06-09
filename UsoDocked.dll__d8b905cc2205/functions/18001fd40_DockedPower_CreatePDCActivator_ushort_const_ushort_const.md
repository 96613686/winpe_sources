# DockedPower::CreatePDCActivator(ushort const *,ushort const *)

- ea: `0x18001fd40`
- end: `0x18001ffd9`
- name: `?CreatePDCActivator@DockedPower@@UEAAJPEBG0@Z`
- size: `665`
- prototype: `int(DockedPower *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update`

## callees

- `0x180007660`
- `0x18001fd40`
- `0x1800209fc`
- `0x180020ac0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001febc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001febc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ff18`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001fecf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ff2b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001fecf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001ff2b`
- `UMPDC!Pdcv2ActivationClientUnregister` at `0x18001ff23`
- `UMPDC!Pdcv2ActivationClientUnregister` at `0x18001ff5f`
- `UMPDC!Pdcv2ActivationClientUnregister` at `0x18001ff23`
- `UMPDC!Pdcv2ActivationClientUnregister` at `0x18001ff5f`
- `UMPDC!Pdcv2ActivationClientDeactivate` at `0x18001fec7`
- `UMPDC!Pdcv2ActivationClientDeactivate` at `0x18001ff49`
- `UMPDC!Pdcv2ActivationClientDeactivate` at `0x18001fec7`
- `UMPDC!Pdcv2ActivationClientDeactivate` at `0x18001ff49`
- `UMPDC!Pdcv2ActivationClientRegister` at `0x18001fdb4`
- `UMPDC!Pdcv2ActivationClientRegister` at `0x18001fdb4`
- `UMPDC!Pdcv2ActivationClientActivate` at `0x18001fe67`
- `UMPDC!Pdcv2ActivationClientActivate` at `0x18001fe67`

## string_xrefs

- `0x18001ff97`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedpower.cpp`
- `0x18001ffae`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedpower.cpp`
- `0x18001ffc6`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedpower.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall DockedPower::CreatePDCActivator(
        DockedPower *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int v4; // edi
  __int64 *v6; // r14
  int v8; // eax
  int v9; // eax
  __int64 v10; // rsi
  __int64 v11; // rbx
  DWORD LastError; // edi
  __int64 v13; // rbx
  __int64 v14; // rdi
  DWORD v15; // esi
  int v16; // [rsp+20h] [rbp-A8h]
  _QWORD v17[3]; // [rsp+40h] [rbp-88h] BYREF
  _DWORD v18[2]; // [rsp+58h] [rbp-70h] BYREF
  __int64 v19; // [rsp+60h] [rbp-68h]
  const unsigned __int16 *v20; // [rsp+68h] [rbp-60h]
  __int128 v21; // [rsp+70h] [rbp-58h]
  __int64 v22; // [rsp+80h] [rbp-48h]
  __int64 v23; // [rsp+88h] [rbp-40h]
  __int64 v24; // [rsp+90h] [rbp-38h] BYREF
  int v25; // [rsp+98h] [rbp-30h]
  __int64 v26; // [rsp+A0h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v4 = (int)a2;
  v6 = (__int64 *)((char *)this + 24);
  if ( *((_QWORD *)this + 3) )
    return 0;
  v17[0] = 1;
  v17[1] = lambda_2833b3bb1d26efff98574a7ca1eabba6_::_lambda_invoker_cdecl_;
  v17[2] = this;
  v24 = 0;
  v8 = Pdcv2ActivationClientRegister(115, v17, &v24);
  if ( v8 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x88,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedpower.cpp",
      (const char *)(unsigned int)v8,
      v16);
  if ( !v24 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x89,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedpower.cpp",
      (const char *)0x8000FFFFLL,
      v16);
  v19 = 0;
  v21 = 0;
  v22 = 3;
  v18[0] = 3;
  v23 = -1;
  v18[1] = 180;
  v20 = a3;
  v25 = -1;
  v26 = 0;
  v9 = Pdcv2ActivationClientActivate(v24, v18, 0, 3);
  if ( v9 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x98,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedpower.cpp",
      (const char *)(unsigned int)v9,
      v4);
  v10 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = 0;
  if ( (__int64 *)((char *)this + 32) == &v26 )
  {
    v11 = v26;
  }
  else
  {
    *((_QWORD *)this + 4) = v26;
    v11 = 0;
    v26 = 0;
  }
  if ( v11 )
  {
    LastError = GetLastError();
    Pdcv2ActivationClientDeactivate(v11);
    SetLastError(LastError);
  }
  v26 = v10;
  v13 = *v6;
  *v6 = 0;
  if ( v6 == &v24 )
  {
    v14 = v24;
  }
  else
  {
    *v6 = v24;
    v14 = 0;
    v24 = 0;
  }
  if ( v14 )
  {
    v15 = GetLastError();
    Pdcv2ActivationClientUnregister(v14);
    SetLastError(v15);
    v10 = v26;
  }
  v24 = v13;
  if ( v10 )
  {
    Pdcv2ActivationClientDeactivate(v10);
    v13 = v24;
  }
  if ( v13 )
    Pdcv2ActivationClientUnregister(v13);
  return 0;
}

```

## disassembly

```asm
0x18001fd40  mov     [rsp+arg_18], rbx
0x18001fd45  push    rsi
0x18001fd46  push    rdi
0x18001fd47  push    r14
0x18001fd49  sub     rsp, 0B0h
0x18001fd50  mov     rax, cs:__security_cookie
0x18001fd57  xor     rax, rsp
0x18001fd5a  mov     [rsp+0C8h+var_20], rax
0x18001fd62  mov     rsi, r8
0x18001fd65  mov     rdi, rdx
0x18001fd68  mov     rbx, rcx
0x18001fd6b  lea     r14, [rcx+18h]
0x18001fd6f  cmp     qword ptr [r14], 0
0x18001fd73  jz      short loc_18001FD7C
0x18001fd75  xor     eax, eax
0x18001fd77  jmp     loc_18001FF70
0x18001fd7c  mov     [rsp+0C8h+var_88], 1
0x18001fd85  lea     rax, _lambda_2833b3bb1d26efff98574a7ca1eabba6____lambda_invoker_cdecl_
0x18001fd8c  mov     [rsp+0C8h+var_80], rax
0x18001fd91  mov     [rsp+0C8h+var_78], rbx
0x18001fd96  mov     [rsp+0C8h+var_38], 0
0x18001fda2  lea     r8, [rsp+0C8h+var_38]
0x18001fdaa  lea     rdx, [rsp+0C8h+var_88]
0x18001fdaf  mov     ecx, 73h ; 's'
0x18001fdb4  call    cs:__imp_Pdcv2ActivationClientRegister
0x18001fdba  mov     rcx, [rsp+0C8h]; this
0x18001fdc2  test    eax, eax
0x18001fdc4  js      loc_18001FF94
0x18001fdca  mov     rax, [rsp+0C8h]
0x18001fdd2  mov     rcx, [rsp+0C8h+var_38]
0x18001fdda  test    rcx, rcx
0x18001fddd  jz      loc_18001FFA8
0x18001fde3  mov     [rsp+0C8h+var_68], 0
0x18001fdec  xorps   xmm0, xmm0
0x18001fdef  movdqu  [rsp+0C8h+var_58], xmm0
0x18001fdf5  mov     [rsp+0C8h+var_48], 3
0x18001fe01  mov     r9d, 3
0x18001fe07  mov     [rsp+0C8h+var_70], r9d
0x18001fe0c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001fe10  mov     [rsp+0C8h+var_40], rax
0x18001fe18  mov     [rsp+0C8h+var_6C], 0B4h
0x18001fe20  mov     [rsp+0C8h+var_60], rsi
0x18001fe25  mov     [rsp+0C8h+var_30], eax
0x18001fe2c  mov     [rsp+0C8h+var_28], 0
0x18001fe38  lea     rax, [rsp+0C8h+var_30]
0x18001fe40  mov     [rsp+0C8h+var_90], rax
0x18001fe45  lea     rax, [rsp+0C8h+var_28]
0x18001fe4d  mov     [rsp+0C8h+var_98], rax
0x18001fe52  mov     [rsp+0C8h+var_A0], 0
0x18001fe5a  mov     qword ptr [rsp+0C8h+var_A8], rdi; int
0x18001fe5f  xor     r8d, r8d
0x18001fe62  lea     rdx, [rsp+0C8h+var_70]
0x18001fe67  call    cs:__imp_Pdcv2ActivationClientActivate
0x18001fe6d  mov     rcx, [rsp+0C8h]; this
0x18001fe75  test    eax, eax
0x18001fe77  js      loc_18001FFC3
0x18001fe7d  lea     rcx, [rbx+20h]
0x18001fe81  mov     rsi, [rcx]
0x18001fe84  mov     qword ptr [rcx], 0
0x18001fe8b  lea     rax, [rsp+0C8h+var_28]
0x18001fe93  cmp     rcx, rax
0x18001fe96  jz      short loc_18001FEAF
0x18001fe98  mov     rax, [rsp+0C8h+var_28]
0x18001fea0  mov     [rcx], rax
0x18001fea3  xor     ebx, ebx
0x18001fea5  mov     [rsp+0C8h+var_28], rbx
0x18001fead  jmp     short loc_18001FEB7
0x18001feaf  mov     rbx, [rsp+0C8h+var_28]
0x18001feb7  test    rbx, rbx
0x18001feba  jz      short loc_18001FED5
0x18001febc  call    cs:__imp_GetLastError
0x18001fec2  mov     edi, eax
0x18001fec4  mov     rcx, rbx
0x18001fec7  call    cs:__imp_Pdcv2ActivationClientDeactivate
0x18001fecd  mov     ecx, edi; dwErrCode
0x18001fecf  call    cs:__imp_SetLastError
0x18001fed5  mov     [rsp+0C8h+var_28], rsi
0x18001fedd  mov     rbx, [r14]
0x18001fee0  mov     qword ptr [r14], 0
0x18001fee7  lea     rax, [rsp+0C8h+var_38]
0x18001feef  cmp     r14, rax
0x18001fef2  jz      short loc_18001FF0B
0x18001fef4  mov     rax, [rsp+0C8h+var_38]
0x18001fefc  mov     [r14], rax
0x18001feff  xor     edi, edi
0x18001ff01  mov     [rsp+0C8h+var_38], rdi
0x18001ff09  jmp     short loc_18001FF13
0x18001ff0b  mov     rdi, [rsp+0C8h+var_38]
0x18001ff13  test    rdi, rdi
0x18001ff16  jz      short loc_18001FF39
0x18001ff18  call    cs:__imp_GetLastError
0x18001ff1e  mov     esi, eax
0x18001ff20  mov     rcx, rdi
0x18001ff23  call    cs:__imp_Pdcv2ActivationClientUnregister
0x18001ff29  mov     ecx, esi; dwErrCode
0x18001ff2b  call    cs:__imp_SetLastError
0x18001ff31  mov     rsi, [rsp+0C8h+var_28]
0x18001ff39  mov     [rsp+0C8h+var_38], rbx
0x18001ff41  test    rsi, rsi
0x18001ff44  jz      short loc_18001FF57
0x18001ff46  mov     rcx, rsi
0x18001ff49  call    cs:__imp_Pdcv2ActivationClientDeactivate
0x18001ff4f  mov     rbx, [rsp+0C8h+var_38]
0x18001ff57  test    rbx, rbx
0x18001ff5a  jz      short loc_18001FF65
0x18001ff5c  mov     rcx, rbx
0x18001ff5f  call    cs:__imp_Pdcv2ActivationClientUnregister
0x18001ff65  xor     eax, eax
0x18001ff67  jmp     short loc_18001FF70
0x18001ff69  mov     eax, [rsp+0C8h+var_30]
0x18001ff70  mov     rcx, [rsp+0C8h+var_20]
0x18001ff78  xor     rcx, rsp; StackCookie
0x18001ff7b  call    __security_check_cookie
0x18001ff80  mov     rbx, [rsp+0C8h+arg_18]
0x18001ff88  add     rsp, 0B0h
0x18001ff8f  pop     r14
0x18001ff91  pop     rdi
0x18001ff92  pop     rsi
0x18001ff93  retn
0x18001ff94  mov     r9d, eax; char *
0x18001ff97  lea     r8, aOnecoreEnduser_20; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18001ff9e  mov     edx, 88h; void *
0x18001ffa3  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18001ffa8  mov     r9d, 8000FFFFh; char *
0x18001ffae  lea     r8, aOnecoreEnduser_20; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18001ffb5  mov     edx, 89h; void *
0x18001ffba  mov     rcx, rax; this
0x18001ffbd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001ffc3  mov     r9d, eax; char *
0x18001ffc6  lea     r8, aOnecoreEnduser_20; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18001ffcd  mov     edx, 98h; void *
0x18001ffd2  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
```
