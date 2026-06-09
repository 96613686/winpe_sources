# APPPOOL_CONTROL_RECORD_PROVIDER::ReadRecord(PROPERTY_ENTRY *)

- ea: `0x1800199a0`
- end: `0x180019b49`
- name: `?ReadRecord@APPPOOL_CONTROL_RECORD_PROVIDER@@UEAAJPEAVPROPERTY_ENTRY@@@Z`
- size: `425`
- prototype: `__int64 __fastcall(APPPOOL_CONTROL_RECORD_PROVIDER *__hidden this, struct PROPERTY_ENTRY *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180017554`
- `0x1800199a0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800199ff`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800199ff`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180019a32`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180019a43`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180019aaf`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180019afc`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180019a32`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180019a43`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180019aaf`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180019afc`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180019a64`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180019a64`

## pseudocode

```c
__int64 __fastcall APPPOOL_CONTROL_RECORD_PROVIDER::ReadRecord(
        APPPOOL_CONTROL_RECORD_PROVIDER *this,
        struct PROPERTY_ENTRY *a2)
{
  HRESULT v4; // ebx
  BUFFER *v5; // rsi
  __int64 (__fastcall *v6)(LPVOID, unsigned __int16 *, __int64 *); // rbx
  unsigned __int16 *Str; // rax
  int v8; // eax
  unsigned int v9; // edi
  __int64 v11; // [rsp+30h] [rbp-10h] BYREF
  int v12; // [rsp+68h] [rbp+28h] BYREF
  int v13; // [rsp+70h] [rbp+30h] BYREF
  LPVOID ppv; // [rsp+78h] [rbp+38h] BYREF

  v11 = 0;
  v13 = 0;
  v12 = 0;
  ppv = 0;
  if ( !a2 )
    return (unsigned int)-2147024809;
  v4 = CoCreateInstance(&CLSID_RSCA_WAS, 0, 0x15u, &IID_IRSCA_WAS, &ppv);
  if ( v4 >= 0 )
  {
    v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 24LL))(ppv, 0);
    if ( v4 >= 0 )
    {
      v5 = (struct PROPERTY_ENTRY *)((char *)a2 + 16);
      if ( *(_DWORD *)BUFFER::QueryPtr(v5) == 9027 || *(_DWORD *)BUFFER::QueryPtr(v5) == 1099 )
      {
        v6 = *(__int64 (__fastcall **)(LPVOID, unsigned __int16 *, __int64 *))(*(_QWORD *)ppv + 32LL);
        Str = STRU::QueryStr((APPPOOL_CONTROL_RECORD_PROVIDER *)((char *)this + 16));
        v8 = v6(ppv, Str, &v11);
        v4 = v8;
        v9 = 3;
        if ( v8 < 0
          || (v8 = (*(__int64 (__fastcall **)(__int64, int *, int *))(*(_QWORD *)v11 + 24LL))(v11, &v13, &v12),
              v4 = v8,
              v8 < 0) )
        {
          v12 = v8;
          v13 = 3;
        }
        if ( *(_DWORD *)BUFFER::QueryPtr(v5) == 1099 )
        {
          v9 = WIN32_FROM_HRESULT(v12);
          goto LABEL_20;
        }
        switch ( v13 )
        {
          case 0:
            v9 = 1;
            goto LABEL_20;
          case 1:
            v9 = 2;
            goto LABEL_20;
          case 2:
LABEL_20:
            **((_DWORD **)BUFFER::QueryPtr(v5) + 3) = v9;
            goto LABEL_21;
          case 3:
            v9 = 4;
            goto LABEL_20;
        }
      }
      v4 = -2147024883;
    }
  }
LABEL_21:
  if ( v11 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v11 = 0;
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800199a0  mov     [rsp-18h+arg_0], rbx
0x1800199a5  push    rbp
0x1800199a6  push    rsi
0x1800199a7  push    rdi
0x1800199a8  mov     rbp, rsp
0x1800199ab  sub     rsp, 40h
0x1800199af  mov     [rbp+var_10], 0
0x1800199b7  mov     rsi, rdx
0x1800199ba  mov     [rbp+arg_10], 0
0x1800199c1  mov     rdi, rcx
0x1800199c4  mov     [rbp+arg_8], 0
0x1800199cb  mov     [rbp+arg_18], 0
0x1800199d3  test    rdx, rdx
0x1800199d6  jnz     short loc_1800199E2
0x1800199d8  mov     ebx, 80070057h
0x1800199dd  jmp     loc_180019B3A
0x1800199e2  xor     edx, edx; pUnkOuter
0x1800199e4  lea     rax, [rbp+arg_18]
0x1800199e8  lea     r9, IID_IRSCA_WAS; riid
0x1800199ef  mov     [rsp+40h+ppv], rax; ppv
0x1800199f4  lea     rcx, CLSID_RSCA_WAS; rclsid
0x1800199fb  lea     r8d, [rdx+15h]; dwClsContext
0x1800199ff  call    cs:__imp_CoCreateInstance
0x180019a05  mov     ebx, eax
0x180019a07  test    eax, eax
0x180019a09  js      loc_180019B08
0x180019a0f  mov     rcx, [rbp+arg_18]
0x180019a13  xor     edx, edx
0x180019a15  mov     rax, [rcx]
0x180019a18  mov     rax, [rax+18h]
0x180019a1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a21  mov     ebx, eax
0x180019a23  test    eax, eax
0x180019a25  js      loc_180019B08
0x180019a2b  add     rsi, 10h
0x180019a2f  mov     rcx, rsi
0x180019a32  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180019a38  cmp     dword ptr [rax], 2343h
0x180019a3e  jz      short loc_180019A55
0x180019a40  mov     rcx, rsi
0x180019a43  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180019a49  cmp     dword ptr [rax], 44Bh
0x180019a4f  jnz     loc_180019ADF
0x180019a55  mov     rax, [rbp+arg_18]
0x180019a59  mov     rcx, [rax]
0x180019a5c  mov     rbx, [rcx+20h]
0x180019a60  lea     rcx, [rdi+10h]
0x180019a64  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180019a6a  mov     rcx, [rbp+arg_18]
0x180019a6e  lea     r8, [rbp+var_10]
0x180019a72  mov     rdx, rax
0x180019a75  mov     rax, rbx
0x180019a78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a7d  mov     ebx, eax
0x180019a7f  mov     edi, 3
0x180019a84  test    eax, eax
0x180019a86  js      short loc_180019AA6
0x180019a88  mov     rcx, [rbp+var_10]
0x180019a8c  lea     r8, [rbp+arg_8]
0x180019a90  lea     rdx, [rbp+arg_10]
0x180019a94  mov     rax, [rcx]
0x180019a97  mov     rax, [rax+18h]
0x180019a9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019aa0  mov     ebx, eax
0x180019aa2  test    eax, eax
0x180019aa4  jns     short loc_180019AAC
0x180019aa6  mov     [rbp+arg_8], eax
0x180019aa9  mov     [rbp+arg_10], edi
0x180019aac  mov     rcx, rsi
0x180019aaf  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180019ab5  cmp     dword ptr [rax], 44Bh
0x180019abb  jnz     short loc_180019AC9
0x180019abd  mov     ecx, [rbp+arg_8]; int
0x180019ac0  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x180019ac5  mov     edi, eax
0x180019ac7  jmp     short loc_180019AF9
0x180019ac9  mov     ecx, [rbp+arg_10]
0x180019acc  test    ecx, ecx
0x180019ace  jz      short loc_180019AF4
0x180019ad0  sub     ecx, 1
0x180019ad3  jz      short loc_180019AED
0x180019ad5  sub     ecx, 1
0x180019ad8  jz      short loc_180019AF9
0x180019ada  cmp     ecx, 1
0x180019add  jz      short loc_180019AE6
0x180019adf  mov     ebx, 8007000Dh
0x180019ae4  jmp     short loc_180019B08
0x180019ae6  mov     edi, 4
0x180019aeb  jmp     short loc_180019AF9
0x180019aed  mov     edi, 2
0x180019af2  jmp     short loc_180019AF9
0x180019af4  mov     edi, 1
0x180019af9  mov     rcx, rsi
0x180019afc  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180019b02  mov     rcx, [rax+18h]
0x180019b06  mov     [rcx], edi
0x180019b08  mov     rcx, [rbp+var_10]
0x180019b0c  test    rcx, rcx
0x180019b0f  jz      short loc_180019B25
0x180019b11  mov     rax, [rcx]
0x180019b14  mov     rax, [rax+10h]
0x180019b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b1d  mov     [rbp+var_10], 0
0x180019b25  mov     rcx, [rbp+arg_18]
0x180019b29  test    rcx, rcx
0x180019b2c  jz      short loc_180019B3A
0x180019b2e  mov     rax, [rcx]
0x180019b31  mov     rax, [rax+10h]
0x180019b35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019b3a  mov     eax, ebx
0x180019b3c  mov     rbx, [rsp+40h+arg_0]
0x180019b41  add     rsp, 40h
0x180019b45  pop     rdi
0x180019b46  pop     rsi
0x180019b47  pop     rbp
0x180019b48  retn
```
