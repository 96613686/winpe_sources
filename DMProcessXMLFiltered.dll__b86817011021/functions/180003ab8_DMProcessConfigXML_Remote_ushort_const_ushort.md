# DMProcessConfigXML_Remote(ushort const *,ushort * *)

- ea: `0x180003ab8`
- end: `0x180003c56`
- name: `?DMProcessConfigXML_Remote@@YAJPEBGPEAPEAG@Z`
- size: `414`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180002300`

## callees

- `0x180001520`
- `0x180003ab8`
- `0x180005224`
- `0x180006390`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003bb0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003c22`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003bb0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180003c22`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180003bc1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180003c2f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180003bc1`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180003c2f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180003b3a`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180003b3a`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x180003b82`
- `DMCmnUtils!DmGetCurrentUserSid` at `0x180003b82`

## string_xrefs

- `0x180003bcc`: `OMADM::TargetedUserSID`
- `0x180003b14`: `onecoreuap\admin\dm\dmprocessxml\lib\processxml.cpp`
- `0x180003b96`: `onecoreuap\admin\dm\dmprocessxml\lib\processxml.cpp`

## pseudocode

```c
__int64 __fastcall DMProcessConfigXML_Remote(const unsigned __int16 *a1, unsigned __int16 **a2)
{
  __int64 v4; // rdx
  int CurrentUserSid; // ebx
  __int64 v7; // rdx
  int v8; // [rsp+20h] [rbp-60h] BYREF
  HLOCAL hMem[2]; // [rsp+28h] [rbp-58h] BYREF
  char v10; // [rsp+38h] [rbp-48h]
  const wchar_t *v11; // [rsp+40h] [rbp-40h] BYREF
  __int128 v12; // [rsp+48h] [rbp-38h]
  __int128 v13; // [rsp+58h] [rbp-28h]
  const wchar_t *v14; // [rsp+68h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]

  v8 = 0;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  if ( !a1 )
  {
    v4 = 239;
LABEL_3:
    CurrentUserSid = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecoreuap\\admin\\dm\\dmprocessxml\\lib\\processxml.cpp",
      (const char *)(unsigned int)CurrentUserSid,
      v8);
    return (unsigned int)CurrentUserSid;
  }
  if ( !a2 )
  {
    v4 = 240;
    goto LABEL_3;
  }
  *a2 = 0;
  CurrentUserSid = CoInitializeEx(0, 0);
  if ( CurrentUserSid < 0 )
  {
    v4 = 244;
    goto LABEL_4;
  }
  v8 = 1;
  hMem[1] = &v8;
  v10 = 1;
  v11 = L"OMADM::AccountID";
  *(_QWORD *)&v12 = L"2648BF76-DA4B-409A-BFFA-6AF111C298A5";
  hMem[0] = 0;
  CurrentUserSid = DmGetCurrentUserSid((unsigned __int16 **)hMem);
  if ( CurrentUserSid < 0 )
  {
    v7 = 260;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\admin\\dm\\dmprocessxml\\lib\\processxml.cpp",
      (const char *)(unsigned int)CurrentUserSid,
      v8);
    if ( hMem[0] )
      LocalFree(hMem[0]);
    if ( v8 )
      CoUninitialize();
    return (unsigned int)CurrentUserSid;
  }
  *((_QWORD *)&v12 + 1) = L"OMADM::TargetedUserSID";
  *(HLOCAL *)&v13 = hMem[0];
  *((_QWORD *)&v13 + 1) = L"OMADM::DpuRunningMode";
  v14 = L"OUTPROC";
  CurrentUserSid = MdmProcessConfigXmlWithAttributes((__int64)a1, 3u, (OLECHAR *)&v11, a2);
  if ( CurrentUserSid < 0 )
  {
    v7 = 272;
    goto LABEL_12;
  }
  if ( hMem[0] )
    LocalFree(hMem[0]);
  if ( v8 )
    CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x180003ab8  mov     [rsp-18h+arg_10], rbx
0x180003abd  push    rbp
0x180003abe  push    rsi
0x180003abf  push    rdi
0x180003ac0  mov     rbp, rsp
0x180003ac3  sub     rsp, 80h
0x180003aca  mov     rax, cs:__security_cookie
0x180003ad1  xor     rax, rsp
0x180003ad4  mov     [rbp+var_10], rax
0x180003ad8  mov     rdi, rdx
0x180003adb  mov     rsi, rcx
0x180003ade  mov     [rbp+var_60], 0
0x180003ae5  mov     [rbp+var_40], 0
0x180003aed  xorps   xmm0, xmm0
0x180003af0  xor     eax, eax
0x180003af2  movups  [rbp+var_38], xmm0
0x180003af6  movups  [rbp+var_28], xmm0
0x180003afa  mov     [rbp+var_18], rax
0x180003afe  test    rcx, rcx
0x180003b01  jnz     short loc_180003B27
0x180003b03  mov     edx, 0EFh; void *
0x180003b08  mov     ebx, 80070057h
0x180003b0d  mov     rcx, [rbp+18h]; this
0x180003b11  mov     r9d, ebx; char *
0x180003b14  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\dmprocessxml\\li"...
0x180003b1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003b20  mov     eax, ebx
0x180003b22  jmp     loc_180003C37
0x180003b27  test    rdi, rdi
0x180003b2a  jnz     short loc_180003B33
0x180003b2c  mov     edx, 0F0h
0x180003b31  jmp     short loc_180003B08
0x180003b33  mov     [rdx], rax
0x180003b36  xor     edx, edx; dwCoInit
0x180003b38  xor     ecx, ecx; pvReserved
0x180003b3a  call    cs:__imp_CoInitializeEx
0x180003b40  mov     ebx, eax
0x180003b42  test    eax, eax
0x180003b44  jns     short loc_180003B4D
0x180003b46  mov     edx, 0F4h
0x180003b4b  jmp     short loc_180003B0D
0x180003b4d  mov     [rbp+var_60], 1
0x180003b54  lea     rax, [rbp+var_60]
0x180003b58  mov     [rbp+var_50], rax
0x180003b5c  mov     [rbp+var_48], 1
0x180003b60  lea     rax, aOmadmAccountid; "OMADM::AccountID"
0x180003b67  mov     [rbp+var_40], rax
0x180003b6b  lea     rax, a2648bf76Da4b40; "2648BF76-DA4B-409A-BFFA-6AF111C298A5"
0x180003b72  mov     qword ptr [rbp+var_38], rax
0x180003b76  mov     [rbp+hMem], 0
0x180003b7e  lea     rcx, [rbp+hMem]
0x180003b82  call    cs:__imp_?DmGetCurrentUserSid@@YAJPEAPEAG@Z; DmGetCurrentUserSid(ushort * *)
0x180003b88  mov     ebx, eax
0x180003b8a  test    eax, eax
0x180003b8c  jns     short loc_180003BCC
0x180003b8e  mov     edx, 104h; void *
0x180003b93  mov     r9d, ebx; char *
0x180003b96  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\dmprocessxml\\li"...
0x180003b9d  mov     rcx, [rbp+18h]; this
0x180003ba1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180003ba6  nop
0x180003ba7  mov     rcx, [rbp+hMem]; hMem
0x180003bab  test    rcx, rcx
0x180003bae  jz      short loc_180003BB7
0x180003bb0  call    cs:__imp_LocalFree
0x180003bb6  nop
0x180003bb7  cmp     [rbp+var_60], 0
0x180003bbb  jz      loc_180003B20
0x180003bc1  call    cs:__imp_CoUninitialize
0x180003bc7  jmp     loc_180003B20
0x180003bcc  lea     rax, aOmadmTargetedu; "OMADM::TargetedUserSID"
0x180003bd3  mov     qword ptr [rbp+var_38+8], rax
0x180003bd7  mov     rax, [rbp+hMem]
0x180003bdb  mov     qword ptr [rbp+var_28], rax
0x180003bdf  lea     rax, aOmadmDpurunnin; "OMADM::DpuRunningMode"
0x180003be6  mov     qword ptr [rbp+var_28+8], rax
0x180003bea  lea     rax, aOutproc; "OUTPROC"
0x180003bf1  mov     [rbp+var_18], rax
0x180003bf5  mov     r9, rdi
0x180003bf8  lea     r8, [rbp+var_40]
0x180003bfc  mov     edx, 3
0x180003c01  mov     rcx, rsi
0x180003c04  call    MdmProcessConfigXmlWithAttributes
0x180003c09  mov     ebx, eax
0x180003c0b  test    eax, eax
0x180003c0d  jns     short loc_180003C19
0x180003c0f  mov     edx, 110h
0x180003c14  jmp     loc_180003B93
0x180003c19  mov     rcx, [rbp+hMem]; hMem
0x180003c1d  test    rcx, rcx
0x180003c20  jz      short loc_180003C29
0x180003c22  call    cs:__imp_LocalFree
0x180003c28  nop
0x180003c29  cmp     [rbp+var_60], 0
0x180003c2d  jz      short loc_180003C35
0x180003c2f  call    cs:__imp_CoUninitialize
0x180003c35  xor     eax, eax
0x180003c37  mov     rcx, [rbp+var_10]
0x180003c3b  xor     rcx, rsp; StackCookie
0x180003c3e  call    __security_check_cookie
0x180003c43  mov     rbx, [rsp+80h+arg_10]
0x180003c4b  add     rsp, 80h
0x180003c52  pop     rdi
0x180003c53  pop     rsi
0x180003c54  pop     rbp
0x180003c55  retn
```
