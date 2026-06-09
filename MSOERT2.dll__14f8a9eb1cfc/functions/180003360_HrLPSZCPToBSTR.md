# HrLPSZCPToBSTR

- ea: `0x180003360`
- end: `0x1800034ad`
- name: `HrLPSZCPToBSTR`
- size: `333`
- prototype: `__int64 __fastcall(UINT, __int64, BSTR *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180003140`
- `0x1800034c0`

## callees

- `0x180003360`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetACP` at `0x18000339f`
- `KERNEL32!GetACP` at `0x18000339f`
- `ole32!CoCreateInstance` at `0x1800033c4`
- `ole32!CoCreateInstance` at `0x1800033c4`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180003421`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180003421`

## pseudocode

```c
__int64 __fastcall HrLPSZCPToBSTR(UINT a1, __int64 a2, BSTR *a3)
{
  UINT ACP; // edi
  HRESULT v6; // ebx
  __int64 v7; // rdx
  BSTR v8; // rax
  BSTR v9; // rdi
  __int64 v10; // rcx
  LPVOID v11; // rcx
  __int64 v13; // [rsp+30h] [rbp-10h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-8h] BYREF
  int v15; // [rsp+60h] [rbp+20h] BYREF
  int v16; // [rsp+78h] [rbp+38h] BYREF

  v16 = 0;
  v15 = 0;
  ppv = 0;
  ACP = a1;
  v13 = 0;
  if ( !a1 )
    ACP = GetACP();
  v6 = CoCreateInstance(&CLSID_CMultiLanguage, 0, 1u, &IID_IMultiLanguage, &ppv);
  if ( v6 >= 0 )
  {
    v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64, _QWORD, __int64 *))(*(_QWORD *)ppv + 136LL))(
           ppv,
           ACP,
           1200,
           0,
           &v13);
    if ( v6 >= 0 )
    {
      if ( a2 )
      {
        v7 = -1;
        do
          ++v7;
        while ( *(_BYTE *)(a2 + v7) );
      }
      else
      {
        LODWORD(v7) = 0;
      }
      v16 = v7 + 1;
      v15 = v7 + 1;
      v8 = SysAllocStringLen(0, (int)v7 + 1);
      v9 = v8;
      if ( v8 )
      {
        v6 = (*(__int64 (__fastcall **)(__int64, __int64, int *, BSTR, int *))(*(_QWORD *)v13 + 64LL))(
               v13,
               a2,
               &v16,
               v8,
               &v15);
        *a3 = v9;
      }
      else
      {
        v6 = -2147024882;
      }
    }
  }
  v10 = v13;
  if ( v13 )
  {
    v13 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  v11 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v11 + 16LL))(v11);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180003360  mov     [rsp-18h+arg_8], rbx
0x180003365  mov     [rsp-18h+arg_10], rsi
0x18000336a  push    rbp
0x18000336b  push    rdi
0x18000336c  push    r14
0x18000336e  mov     rbp, rsp
0x180003371  sub     rsp, 40h
0x180003375  mov     [rbp+arg_18], 0
0x18000337c  mov     r14, r8
0x18000337f  mov     [rbp+arg_0], 0
0x180003386  mov     rsi, rdx
0x180003389  mov     [rbp+var_8], 0
0x180003391  mov     edi, ecx
0x180003393  mov     [rbp+var_10], 0
0x18000339b  test    ecx, ecx
0x18000339d  jnz     short loc_1800033A7
0x18000339f  call    cs:__imp_GetACP
0x1800033a5  mov     edi, eax
0x1800033a7  xor     edx, edx; pUnkOuter
0x1800033a9  lea     rax, [rbp+var_8]
0x1800033ad  lea     r9, IID_IMultiLanguage; riid
0x1800033b4  mov     [rsp+40h+ppv], rax; ppv
0x1800033b9  lea     rcx, CLSID_CMultiLanguage; rclsid
0x1800033c0  lea     r8d, [rdx+1]; dwClsContext
0x1800033c4  call    cs:__imp_CoCreateInstance
0x1800033ca  mov     ebx, eax
0x1800033cc  test    eax, eax
0x1800033ce  js      loc_18000345E
0x1800033d4  mov     rcx, [rbp+var_8]
0x1800033d8  lea     rdx, [rbp+var_10]
0x1800033dc  mov     [rsp+40h+ppv], rdx
0x1800033e1  xor     r9d, r9d
0x1800033e4  mov     r8d, 4B0h
0x1800033ea  mov     edx, edi
0x1800033ec  mov     rax, [rcx]
0x1800033ef  mov     rax, [rax+88h]
0x1800033f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033fb  mov     ebx, eax
0x1800033fd  test    eax, eax
0x1800033ff  js      short loc_18000345E
0x180003401  test    rsi, rsi
0x180003404  jz      short loc_180003415
0x180003406  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18000340a  inc     rdx
0x18000340d  cmp     byte ptr [rsi+rdx], 0
0x180003411  jnz     short loc_18000340A
0x180003413  jmp     short loc_180003417
0x180003415  xor     edx, edx
0x180003417  inc     edx; ui
0x180003419  xor     ecx, ecx; strIn
0x18000341b  mov     [rbp+arg_18], edx
0x18000341e  mov     [rbp+arg_0], edx
0x180003421  call    cs:__imp_SysAllocStringLen
0x180003427  mov     rdi, rax
0x18000342a  test    rax, rax
0x18000342d  jnz     short loc_180003436
0x18000342f  mov     ebx, 8007000Eh
0x180003434  jmp     short loc_18000345E
0x180003436  mov     rcx, [rbp+var_10]
0x18000343a  lea     rdx, [rbp+arg_0]
0x18000343e  mov     [rsp+40h+ppv], rdx
0x180003443  lea     r8, [rbp+arg_18]
0x180003447  mov     r9, rdi
0x18000344a  mov     rdx, rsi
0x18000344d  mov     rax, [rcx]
0x180003450  mov     rax, [rax+40h]
0x180003454  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003459  mov     ebx, eax
0x18000345b  mov     [r14], rdi
0x18000345e  mov     rcx, [rbp+var_10]
0x180003462  test    rcx, rcx
0x180003465  jz      short loc_18000347B
0x180003467  mov     [rbp+var_10], 0
0x18000346f  mov     rax, [rcx]
0x180003472  mov     rax, [rax+10h]
0x180003476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000347b  mov     rcx, [rbp+var_8]
0x18000347f  test    rcx, rcx
0x180003482  jz      short loc_180003498
0x180003484  mov     [rbp+var_8], 0
0x18000348c  mov     rax, [rcx]
0x18000348f  mov     rax, [rax+10h]
0x180003493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003498  mov     rsi, [rsp+40h+arg_10]
0x18000349d  mov     eax, ebx
0x18000349f  mov     rbx, [rsp+40h+arg_8]
0x1800034a4  add     rsp, 40h
0x1800034a8  pop     r14
0x1800034aa  pop     rdi
0x1800034ab  pop     rbp
0x1800034ac  retn
```
