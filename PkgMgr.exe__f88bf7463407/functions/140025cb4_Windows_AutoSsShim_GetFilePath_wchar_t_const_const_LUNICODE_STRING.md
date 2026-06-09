# Windows::AutoSsShim::GetFilePath(wchar_t const * const,_LUNICODE_STRING &)

- ea: `0x140025cb4`
- end: `0x140025d77`
- name: `?GetFilePath@AutoSsShim@Windows@@QEAAJQEB_WAEAU_LUNICODE_STRING@@@Z`
- size: `195`
- prototype: `__int64 __fastcall(Windows::AutoSsShim *__hidden this, const wchar_t *const, struct _LUNICODE_STRING *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400251e4`

## callees

- `0x140002360`
- `0x1400074c0`
- `0x140025cb4`
- `0x14002a010`

## string_xrefs

- `0x140025d28`: `Windows::AutoSsShim::GetFilePath`
- `0x140025d37`: `m_pfnSssGetServicingStackFilePath( 0, m_Cookie, BinaryName, FullPath.MaximumLength, FullPath.Buffer, &CharNewLengthWithNull)`

## pseudocode

```c
__int64 __fastcall Windows::AutoSsShim::GetFilePath(
        Windows::AutoSsShim *this,
        const wchar_t *a2,
        struct _LUNICODE_STRING *a3)
{
  __int64 v3; // r9
  __int64 v6; // rcx
  __int64 v8; // rdx
  __int64 (__fastcall *v9)(_QWORD, __int64, const wchar_t *const, __int64, __int64, __int64 *); // rax
  int v10; // eax
  _QWORD v12[4]; // [rsp+40h] [rbp-48h] BYREF
  int v13; // [rsp+60h] [rbp-28h] BYREF
  __int64 v14; // [rsp+68h] [rbp-20h] BYREF

  v3 = *((_QWORD *)a3 + 1);
  v13 = 0;
  v6 = *((_QWORD *)a3 + 2);
  v8 = *((_QWORD *)this + 1);
  v9 = (__int64 (__fastcall *)(_QWORD, __int64, const wchar_t *const, __int64, __int64, __int64 *))*((_QWORD *)this + 6);
  v14 = 0;
  v10 = v9(0, v8, a2, v3, v6, &v14);
  if ( v10 >= 0 )
  {
    *(_QWORD *)a3 = 2 * v14 - 2;
    return 0;
  }
  else
  {
    v12[2] = 286;
    v12[0] = "onecore\\base\\wcp\\rtllib\\inc\\auto_ssshim.h";
    v12[1] = "Windows::AutoSsShim::GetFilePath";
    v12[3] = "m_pfnSssGetServicingStackFilePath( 0, m_Cookie, BinaryName, FullPath.MaximumLength, FullPath.Buffer, &CharN"
             "ewLengthWithNull)";
    return Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(
             &v13,
             v12,
             (unsigned int)v10);
  }
}

```

## disassembly

```asm
0x140025cb4  mov     r11, rsp
0x140025cb7  push    rbx
0x140025cb8  sub     rsp, 80h
0x140025cbf  mov     rax, cs:__security_cookie
0x140025cc6  xor     rax, rsp
0x140025cc9  mov     [rsp+88h+var_18], rax
0x140025cce  mov     r9, [r8+8]
0x140025cd2  mov     rax, rcx
0x140025cd5  lea     rcx, [r11-20h]
0x140025cd9  mov     [rsp+88h+var_28], 0
0x140025ce1  mov     [r11-60h], rcx
0x140025ce5  mov     rbx, r8
0x140025ce8  mov     rcx, [r8+10h]
0x140025cec  mov     r8, rdx
0x140025cef  mov     rdx, [rax+8]
0x140025cf3  mov     rax, [rax+30h]
0x140025cf7  mov     [r11-68h], rcx
0x140025cfb  xor     ecx, ecx
0x140025cfd  mov     qword ptr [r11-20h], 0
0x140025d05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140025d0a  test    eax, eax
0x140025d0c  jns     short loc_140025D4F
0x140025d0e  lea     rcx, aOnecoreBaseWcp_0; "onecore\\base\\wcp\\rtllib\\inc\\auto_s"...
0x140025d15  mov     [rsp+88h+var_38], 11Eh
0x140025d1e  mov     [rsp+88h+var_48], rcx
0x140025d23  lea     rdx, [rsp+88h+var_48]
0x140025d28  lea     rcx, aWindowsAutosss; "Windows::AutoSsShim::GetFilePath"
0x140025d2f  mov     r8d, eax
0x140025d32  mov     [rsp+88h+var_40], rcx
0x140025d37  lea     rcx, aMPfnsssgetserv_1; "m_pfnSssGetServicingStackFilePath( 0, m"...
0x140025d3e  mov     [rsp+88h+var_30], rcx
0x140025d43  lea     rcx, [rsp+88h+var_28]
0x140025d48  call    ?OriginateHResult@?$CBaseFrame@UCSimpleHResultCarryingFrame@COM@ErrorHandling@Windows@@J@COM@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::COM::CBaseFrame<Windows::ErrorHandling::COM::CSimpleHResultCarryingFrame,long>::OriginateHResult(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x140025d4d  jmp     short loc_140025D61
0x140025d4f  mov     rax, [rsp+88h+var_20]
0x140025d54  lea     rax, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x140025d5c  mov     [rbx], rax
0x140025d5f  xor     eax, eax
0x140025d61  mov     rcx, [rsp+88h+var_18]
0x140025d66  xor     rcx, rsp; StackCookie
0x140025d69  call    __security_check_cookie
0x140025d6e  add     rsp, 80h
0x140025d75  pop     rbx
0x140025d76  retn
```
