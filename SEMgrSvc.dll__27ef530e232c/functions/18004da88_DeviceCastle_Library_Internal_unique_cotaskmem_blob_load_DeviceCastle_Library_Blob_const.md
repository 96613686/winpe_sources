# DeviceCastle::Library::Internal::unique_cotaskmem_blob::load(DeviceCastle::Library::Blob const &)

- ea: `0x18004da88`
- end: `0x18004db36`
- name: `?load@unique_cotaskmem_blob@Internal@Library@DeviceCastle@@QEAAXAEBVBlob@34@@Z`
- size: `174`
- prototype: `void __fastcall(DeviceCastle::Library::Internal::unique_cotaskmem_blob *__hidden this, const struct DeviceCastle::Library::Blob *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004b2a8`

## callees

- `0x180005840`
- `0x180035bc0`
- `0x18004da88`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004dadf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004db09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004dadf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004db09`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004dace`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004dace`

## string_xrefs

- `0x18004db24`: `onecoreuap\ds\nfc\Product\SEManagement\Common\DevCastle\inc\NCryptHandles.h`

## pseudocode

```c
void __fastcall DeviceCastle::Library::Internal::unique_cotaskmem_blob::load(
        void **this,
        const struct DeviceCastle::Library::Blob *a2)
{
  SIZE_T v4; // rsi
  __int64 v5; // rax
  const void *v6; // rbx
  LPVOID v7; // rax
  const char *v8; // r9
  void *v9; // rcx
  void *v10; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = (*(__int64 (__fastcall **)(const struct DeviceCastle::Library::Blob *))(*(_QWORD *)a2 + 96LL))(a2);
  v5 = (*(__int64 (__fastcall **)(const struct DeviceCastle::Library::Blob *))(*(_QWORD *)a2 + 16LL))(a2);
  v6 = (const void *)v5;
  if ( v4 && v5 )
  {
    v7 = CoTaskMemAlloc(v4);
    v9 = *this;
    *this = v7;
    if ( v9 )
      CoTaskMemFree(v9);
    if ( !*this )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x2F,
        (unsigned int)"onecoreuap\\ds\\nfc\\Product\\SEManagement\\Common\\DevCastle\\inc\\NCryptHandles.h",
        v8);
    memcpy_0(*this, v6, v4);
  }
  else
  {
    v10 = *this;
    *this = 0;
    if ( v10 )
      CoTaskMemFree(v10);
  }
}

```

## disassembly

```asm
0x18004da88  mov     [rsp+arg_0], rbx
0x18004da8d  mov     [rsp+arg_8], rsi
0x18004da92  push    rdi
0x18004da93  sub     rsp, 20h
0x18004da97  mov     rax, [rdx]
0x18004da9a  mov     rdi, rcx
0x18004da9d  mov     rcx, rdx
0x18004daa0  mov     rbx, rdx
0x18004daa3  mov     rax, [rax+60h]
0x18004daa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004daac  mov     r8, [rbx]
0x18004daaf  mov     rsi, rax
0x18004dab2  mov     rcx, rbx
0x18004dab5  mov     rax, [r8+10h]
0x18004dab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004dabe  mov     rbx, rax
0x18004dac1  test    rsi, rsi
0x18004dac4  jz      short loc_18004DAFA
0x18004dac6  test    rax, rax
0x18004dac9  jz      short loc_18004DAFA
0x18004dacb  mov     rcx, rsi; cb
0x18004dace  call    cs:__imp_CoTaskMemAlloc
0x18004dad4  mov     rcx, [rdi]; pv
0x18004dad7  mov     [rdi], rax
0x18004dada  test    rcx, rcx
0x18004dadd  jz      short loc_18004DAE5
0x18004dadf  call    cs:__imp_CoTaskMemFree
0x18004dae5  mov     rcx, [rdi]; void *
0x18004dae8  test    rcx, rcx
0x18004daeb  jz      short loc_18004DB1F
0x18004daed  mov     r8, rsi; Size
0x18004daf0  mov     rdx, rbx; Src
0x18004daf3  call    memcpy_0
0x18004daf8  jmp     short loc_18004DB0F
0x18004dafa  mov     rcx, [rdi]; pv
0x18004dafd  mov     qword ptr [rdi], 0
0x18004db04  test    rcx, rcx
0x18004db07  jz      short loc_18004DB0F
0x18004db09  call    cs:__imp_CoTaskMemFree
0x18004db0f  mov     rbx, [rsp+28h+arg_0]
0x18004db14  mov     rsi, [rsp+28h+arg_8]
0x18004db19  add     rsp, 20h
0x18004db1d  pop     rdi
0x18004db1e  retn
0x18004db1f  mov     rcx, [rsp+28h]; this
0x18004db24  lea     r8, aOnecoreuapDsNf_51; "onecoreuap\\ds\\nfc\\Product\\SEManagem"...
0x18004db2b  mov     edx, 2Fh ; '/'; void *
0x18004db30  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
