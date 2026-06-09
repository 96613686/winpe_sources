# CAudioSession::MatchesParameters(bool,ushort const *,ushort const *)

- ea: `0x1800e6c80`
- end: `0x1800e6d82`
- name: `?MatchesParameters@CAudioSession@@QEAAH_NPEBG1@Z`
- size: `258`
- prototype: `int(CAudioSession *__hidden this, bool, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800afd64`

## callees

- `0x18000ae1c`
- `0x180054644`
- `0x1800e6c80`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e6ca5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e6ca5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e6cdb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e6d66`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e6cdb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e6d66`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e6d15`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e6d45`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e6d15`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e6d45`

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
0x1800e6c80  push    rbx
0x1800e6c82  push    rbp
0x1800e6c83  push    rsi
0x1800e6c84  push    rdi
0x1800e6c85  sub     rsp, 38h
0x1800e6c89  mov     rbp, r9
0x1800e6c8c  mov     rsi, r8
0x1800e6c8f  mov     rbx, rcx
0x1800e6c92  mov     [rsp+58h+arg_0], 0
0x1800e6c9b  lea     rdi, [rcx+298h]
0x1800e6ca2  mov     rcx, rdi; lpCriticalSection
0x1800e6ca5  call    cs:__imp_EnterCriticalSection
0x1800e6cab  mov     rdx, [rbx+2C0h]
0x1800e6cb2  cmp     [rbx+2C8h], rdx
0x1800e6cb9  jz      loc_1800E6D5E
0x1800e6cbf  cmp     qword ptr [rdx], 0
0x1800e6cc3  jz      loc_1800E6D5E
0x1800e6cc9  lea     rcx, [rsp+58h+arg_0]
0x1800e6cce  call    ??4?$com_ptr_t@UIAudioProcess@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@AEBV01@@Z; wil::com_ptr_t<IAudioProcess,wil::err_returncode_policy>::operator=(wil::com_ptr_t<IAudioProcess,wil::err_returncode_policy> const &)
0x1800e6cd3  test    rdi, rdi
0x1800e6cd6  jz      short loc_1800E6CE1
0x1800e6cd8  mov     rcx, rdi; lpCriticalSection
0x1800e6cdb  call    cs:__imp_LeaveCriticalSection
0x1800e6ce1  mov     edi, 1
0x1800e6ce6  mov     rbx, [rsp+58h+arg_0]
0x1800e6ceb  test    rsi, rsi
0x1800e6cee  jz      short loc_1800E6D20
0x1800e6cf0  mov     rax, [rbx]
0x1800e6cf3  mov     rcx, rbx
0x1800e6cf6  mov     rax, [rax+40h]
0x1800e6cfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6cff  test    rax, rax
0x1800e6d02  jz      short loc_1800E6D6D
0x1800e6d04  mov     [rsp+58h+bIgnoreCase], edi; bIgnoreCase
0x1800e6d08  or      r9d, 0FFFFFFFFh; cchCount2
0x1800e6d0c  mov     r8, rax; lpString2
0x1800e6d0f  or      edx, r9d; cchCount1
0x1800e6d12  mov     rcx, rsi; lpString1
0x1800e6d15  call    cs:__imp_CompareStringOrdinal
0x1800e6d1b  cmp     eax, 2
0x1800e6d1e  jnz     short loc_1800E6D6D
0x1800e6d20  test    rbp, rbp
0x1800e6d23  jz      short loc_1800E6D50
0x1800e6d25  mov     rax, [rbx]
0x1800e6d28  mov     rcx, rbx
0x1800e6d2b  mov     rax, [rax+38h]
0x1800e6d2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e6d34  mov     r8, rax; lpString2
0x1800e6d37  mov     [rsp+58h+bIgnoreCase], edi; bIgnoreCase
0x1800e6d3b  or      r9d, 0FFFFFFFFh; cchCount2
0x1800e6d3f  or      edx, r9d; cchCount1
0x1800e6d42  mov     rcx, rbp; lpString1
0x1800e6d45  call    cs:__imp_CompareStringOrdinal
0x1800e6d4b  cmp     eax, 2
0x1800e6d4e  jnz     short loc_1800E6D6D
0x1800e6d50  lea     rcx, [rsp+58h+arg_0]
0x1800e6d55  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800e6d5a  mov     eax, edi
0x1800e6d5c  jmp     short loc_1800E6D79
0x1800e6d5e  test    rdi, rdi
0x1800e6d61  jz      short loc_1800E6D6D
0x1800e6d63  mov     rcx, rdi; lpCriticalSection
0x1800e6d66  call    cs:__imp_LeaveCriticalSection
0x1800e6d6c  nop
0x1800e6d6d  lea     rcx, [rsp+58h+arg_0]
0x1800e6d72  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800e6d77  xor     eax, eax
0x1800e6d79  add     rsp, 38h
0x1800e6d7d  pop     rdi
0x1800e6d7e  pop     rsi
0x1800e6d7f  pop     rbp
0x1800e6d80  pop     rbx
0x1800e6d81  retn
```
