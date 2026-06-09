# CAudioSession::MatchesParameters(bool,ushort const *,ushort const *)

- ea: `0x1800e7400`
- end: `0x1800e7502`
- name: `?MatchesParameters@CAudioSession@@QEAAH_NPEBG1@Z`
- size: `258`
- prototype: `int(CAudioSession *__hidden this, bool, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b1a54`

## callees

- `0x18000accc`
- `0x180054ad4`
- `0x1800e7400`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e7425`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e7425`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e745b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e74e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e745b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e74e6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e7495`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e74c5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e7495`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e74c5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAudioSession::MatchesParameters(
        CAudioSession *this,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  struct _RTL_CRITICAL_SECTION *v7; // rdi
  _QWORD *v8; // rdx
  __int64 v9; // rbx
  const WCHAR *v10; // rax
  const WCHAR *v11; // rax
  __int64 v13; // [rsp+60h] [rbp+8h] BYREF

  v13 = 0;
  v7 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 664);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 664));
  v8 = (_QWORD *)*((_QWORD *)this + 88);
  if ( *((_QWORD **)this + 89) == v8 || !*v8 )
  {
    if ( v7 )
      LeaveCriticalSection(v7);
  }
  else
  {
    wil::com_ptr_t<IAudioProcess,wil::err_returncode_policy>::operator=(&v13, v8);
    if ( v7 )
      LeaveCriticalSection(v7);
    v9 = v13;
    if ( !a3
      || (v10 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 64LL))(v13)) != 0
      && CompareStringOrdinal(a3, -1, v10, -1, 1) == 2 )
    {
      if ( !a4
        || (v11 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 56LL))(v9),
            CompareStringOrdinal(a4, -1, v11, -1, 1) == 2) )
      {
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v13);
        return 1;
      }
    }
  }
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v13);
  return 0;
}

```

## disassembly

```asm
0x1800e7400  push    rbx
0x1800e7402  push    rbp
0x1800e7403  push    rsi
0x1800e7404  push    rdi
0x1800e7405  sub     rsp, 38h
0x1800e7409  mov     rbp, r9
0x1800e740c  mov     rsi, r8
0x1800e740f  mov     rbx, rcx
0x1800e7412  mov     [rsp+58h+arg_0], 0
0x1800e741b  lea     rdi, [rcx+298h]
0x1800e7422  mov     rcx, rdi; lpCriticalSection
0x1800e7425  call    cs:__imp_EnterCriticalSection
0x1800e742b  mov     rdx, [rbx+2C0h]
0x1800e7432  cmp     [rbx+2C8h], rdx
0x1800e7439  jz      loc_1800E74DE
0x1800e743f  cmp     qword ptr [rdx], 0
0x1800e7443  jz      loc_1800E74DE
0x1800e7449  lea     rcx, [rsp+58h+arg_0]
0x1800e744e  call    ??4?$com_ptr_t@UIAudioProcess@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<IAudioProcess,wil::err_returncode_policy>::operator=(wil::com_ptr_t<IAudioProcess,wil::err_returncode_policy> const &)
0x1800e7453  test    rdi, rdi
0x1800e7456  jz      short loc_1800E7461
0x1800e7458  mov     rcx, rdi; lpCriticalSection
0x1800e745b  call    cs:__imp_LeaveCriticalSection
0x1800e7461  mov     edi, 1
0x1800e7466  mov     rbx, [rsp+58h+arg_0]
0x1800e746b  test    rsi, rsi
0x1800e746e  jz      short loc_1800E74A0
0x1800e7470  mov     rax, [rbx]
0x1800e7473  mov     rcx, rbx
0x1800e7476  mov     rax, [rax+40h]
0x1800e747a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e747f  test    rax, rax
0x1800e7482  jz      short loc_1800E74ED
0x1800e7484  mov     [rsp+58h+bIgnoreCase], edi; bIgnoreCase
0x1800e7488  or      r9d, 0FFFFFFFFh; cchCount2
0x1800e748c  mov     r8, rax; lpString2
0x1800e748f  or      edx, r9d; cchCount1
0x1800e7492  mov     rcx, rsi; lpString1
0x1800e7495  call    cs:__imp_CompareStringOrdinal
0x1800e749b  cmp     eax, 2
0x1800e749e  jnz     short loc_1800E74ED
0x1800e74a0  test    rbp, rbp
0x1800e74a3  jz      short loc_1800E74D0
0x1800e74a5  mov     rax, [rbx]
0x1800e74a8  mov     rcx, rbx
0x1800e74ab  mov     rax, [rax+38h]
0x1800e74af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e74b4  mov     r8, rax; lpString2
0x1800e74b7  mov     [rsp+58h+bIgnoreCase], edi; bIgnoreCase
0x1800e74bb  or      r9d, 0FFFFFFFFh; cchCount2
0x1800e74bf  or      edx, r9d; cchCount1
0x1800e74c2  mov     rcx, rbp; lpString1
0x1800e74c5  call    cs:__imp_CompareStringOrdinal
0x1800e74cb  cmp     eax, 2
0x1800e74ce  jnz     short loc_1800E74ED
0x1800e74d0  lea     rcx, [rsp+58h+arg_0]
0x1800e74d5  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800e74da  mov     eax, edi
0x1800e74dc  jmp     short loc_1800E74F9
0x1800e74de  test    rdi, rdi
0x1800e74e1  jz      short loc_1800E74ED
0x1800e74e3  mov     rcx, rdi; lpCriticalSection
0x1800e74e6  call    cs:__imp_LeaveCriticalSection
0x1800e74ec  nop
0x1800e74ed  lea     rcx, [rsp+58h+arg_0]
0x1800e74f2  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800e74f7  xor     eax, eax
0x1800e74f9  add     rsp, 38h
0x1800e74fd  pop     rdi
0x1800e74fe  pop     rsi
0x1800e74ff  pop     rbp
0x1800e7500  pop     rbx
0x1800e7501  retn
```
