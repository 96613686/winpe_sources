# CImpIADOSecurity::getPolicy(ulong,ulong *)

- ea: `0x180029a14`
- end: `0x180029b0e`
- name: `?getPolicy@CImpIADOSecurity@@AEAAJKPEAK@Z`
- size: `250`
- prototype: `__int64 __fastcall(CImpIADOSecurity *__hidden this, unsigned int, unsigned int *)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800296f0`
- `0x180029760`
- `0x180029cbc`
- `0x180029d10`

## callees

- `0x180029a14`
- `0x180030010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180029a59`
- `ole32!CoCreateInstance` at `0x180029a59`

## pseudocode

```c
__int64 __fastcall CImpIADOSecurity::getPolicy(CImpIADOSecurity *this, unsigned int a2, unsigned int *a3)
{
  HRESULT v5; // edi
  unsigned int v7; // [rsp+60h] [rbp+20h] BYREF
  int v8; // [rsp+64h] [rbp+24h]
  LPVOID ppv; // [rsp+70h] [rbp+30h] BYREF

  v8 = HIDWORD(this);
  ppv = 0;
  v7 = 3;
  v5 = CoCreateInstance(&CLSID_InternetZoneManager, 0, 1u, &IID_IInternetZoneManager, &ppv);
  if ( v5 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64, unsigned int *, int, _DWORD))(*(_QWORD *)ppv + 56LL))(
           ppv,
           a2,
           5126,
           &v7,
           4,
           0);
    if ( v5 < 0 )
    {
      v5 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64, unsigned int *, int, _DWORD))(*(_QWORD *)ppv + 56LL))(
             ppv,
             a2,
             4609,
             &v7,
             4,
             0);
      if ( v5 >= 0 )
      {
        if ( a2 )
        {
          if ( a2 == 1 && v7 == 3 )
            v7 = 1;
        }
        else
        {
          v7 = 0;
        }
      }
    }
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  if ( a3 )
    *a3 = v7;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180029a14  mov     [rsp-18h+arg_8], rbx
0x180029a19  mov     [rsp-18h+arg_0], rcx
0x180029a1e  push    rbp
0x180029a1f  push    rsi
0x180029a20  push    rdi
0x180029a21  mov     rbp, rsp
0x180029a24  sub     rsp, 40h
0x180029a28  mov     ebx, edx
0x180029a2a  mov     [rbp+arg_10], 0
0x180029a32  xor     edx, edx; pUnkOuter
0x180029a34  mov     dword ptr [rbp+arg_0], 3
0x180029a3b  mov     rsi, r8
0x180029a3e  lea     rax, [rbp+arg_10]
0x180029a42  lea     r9, IID_IInternetZoneManager; riid
0x180029a49  mov     [rsp+40h+ppv], rax; ppv
0x180029a4e  lea     rcx, CLSID_InternetZoneManager; rclsid
0x180029a55  lea     r8d, [rdx+1]; dwClsContext
0x180029a59  call    cs:__imp_CoCreateInstance
0x180029a5f  mov     edi, eax
0x180029a61  test    eax, eax
0x180029a63  js      short loc_180029AE0
0x180029a65  mov     rcx, [rbp+arg_10]
0x180029a69  lea     r9, [rbp+arg_0]
0x180029a6d  mov     [rsp+40h+var_18], 0
0x180029a75  mov     r8d, 1406h
0x180029a7b  mov     edx, ebx
0x180029a7d  mov     dword ptr [rsp+40h+ppv], 4
0x180029a85  mov     rax, [rcx]
0x180029a88  mov     rax, [rax+38h]
0x180029a8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a91  mov     edi, eax
0x180029a93  test    eax, eax
0x180029a95  jns     short loc_180029AE0
0x180029a97  mov     rcx, [rbp+arg_10]
0x180029a9b  lea     r9, [rbp+arg_0]
0x180029a9f  mov     [rsp+40h+var_18], 0
0x180029aa7  mov     r8d, 1201h
0x180029aad  mov     edx, ebx
0x180029aaf  mov     dword ptr [rsp+40h+ppv], 4
0x180029ab7  mov     rax, [rcx]
0x180029aba  mov     rax, [rax+38h]
0x180029abe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ac3  mov     edi, eax
0x180029ac5  test    eax, eax
0x180029ac7  js      short loc_180029AE0
0x180029ac9  test    ebx, ebx
0x180029acb  jnz     short loc_180029AD2
0x180029acd  mov     dword ptr [rbp+arg_0], ebx
0x180029ad0  jmp     short loc_180029AE0
0x180029ad2  cmp     ebx, 1
0x180029ad5  jnz     short loc_180029AE0
0x180029ad7  cmp     dword ptr [rbp+arg_0], 3
0x180029adb  jnz     short loc_180029AE0
0x180029add  mov     dword ptr [rbp+arg_0], ebx
0x180029ae0  mov     rcx, [rbp+arg_10]
0x180029ae4  test    rcx, rcx
0x180029ae7  jz      short loc_180029AF5
0x180029ae9  mov     rax, [rcx]
0x180029aec  mov     rax, [rax+10h]
0x180029af0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029af5  test    rsi, rsi
0x180029af8  jz      short loc_180029AFF
0x180029afa  mov     eax, dword ptr [rbp+arg_0]
0x180029afd  mov     [rsi], eax
0x180029aff  mov     rbx, [rsp+40h+arg_8]
0x180029b04  mov     eax, edi
0x180029b06  add     rsp, 40h
0x180029b0a  pop     rdi
0x180029b0b  pop     rsi
0x180029b0c  pop     rbp
0x180029b0d  retn
```
