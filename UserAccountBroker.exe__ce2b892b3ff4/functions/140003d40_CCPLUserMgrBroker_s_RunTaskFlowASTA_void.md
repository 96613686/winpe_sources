# CCPLUserMgrBroker::s_RunTaskFlowASTA(void *)

- ea: `0x140003d40`
- end: `0x140003eab`
- name: `?s_RunTaskFlowASTA@CCPLUserMgrBroker@@CAKPEAX@Z`
- size: `363`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140003d40`
- `0x140007010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140003d89`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140003d89`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x140003d54`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x140003d54`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x140003e96`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x140003e96`

## pseudocode

```c
__int64 __fastcall CCPLUserMgrBroker::s_RunTaskFlowASTA(_QWORD *a1)
{
  int v2; // ebx
  HRESULT v3; // edi
  __int64 v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rcx
  LPVOID v7; // rcx
  __int64 v9; // [rsp+50h] [rbp+20h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp+28h] BYREF

  v2 = RoInitialize(0);
  if ( v2 < 0 )
  {
    v3 = v2;
    goto LABEL_19;
  }
  ppv = 0;
  v3 = CoCreateInstance(&CLSID_UserManagementWizards, 0, 1u, &GUID_251f5a5a_564a_4889_bb5e_be7cfab519c7, &ppv);
  if ( v3 >= 0 )
  {
    v9 = 0;
    if ( !(*(unsigned __int8 (__fastcall **)(char *))(a1[14] + 8LL))((char *)a1 + 112) )
    {
LABEL_11:
      if ( v9 || (v3 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)ppv + 40LL))(ppv, &v9), v3 >= 0) )
        v3 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, __int64))(*(_QWORD *)ppv + 32LL))(
               ppv,
               *((unsigned int *)a1 + 24),
               a1[11],
               v9);
      goto LABEL_14;
    }
    v4 = v9;
    if ( v9 )
    {
      v9 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
    v5 = *((unsigned int *)a1 + 30);
    v9 = 0;
    if ( (_DWORD)v5 )
    {
      v3 = *((_DWORD *)a1 + 31);
      if ( v3 < 0 )
        goto LABEL_14;
      v3 = (*(__int64 (__fastcall **)(__int64, __int64, GUID *, __int64 *))(*(_QWORD *)qword_14000C868 + 40LL))(
             qword_14000C868,
             v5,
             &GUID_73aecad8_7e70_4e21_8767_82b03c862455,
             &v9);
    }
    else
    {
      v3 = -2147024809;
    }
    if ( v3 >= 0 )
      goto LABEL_11;
LABEL_14:
    v6 = v9;
    if ( v9 )
    {
      v9 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
  }
  v7 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v7 + 16LL))(v7);
  }
LABEL_19:
  *((_DWORD *)a1 + 26) = v3;
  if ( v2 >= 0 )
    RoUninitialize();
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140003d40  mov     [rsp-18h+arg_10], rbx
0x140003d45  push    rbp
0x140003d46  push    rsi
0x140003d47  push    rdi
0x140003d48  mov     rbp, rsp
0x140003d4b  sub     rsp, 30h
0x140003d4f  mov     rsi, rcx
0x140003d52  xor     ecx, ecx
0x140003d54  call    cs:__imp_RoInitialize
0x140003d5a  mov     ebx, eax
0x140003d5c  test    eax, eax
0x140003d5e  js      loc_140003E8D
0x140003d64  xor     edx, edx; pUnkOuter
0x140003d66  mov     [rbp+arg_8], 0
0x140003d6e  lea     rax, [rbp+arg_8]
0x140003d72  lea     r9, _GUID_251f5a5a_564a_4889_bb5e_be7cfab519c7; riid
0x140003d79  mov     [rsp+30h+ppv], rax; ppv
0x140003d7e  lea     rcx, CLSID_UserManagementWizards; rclsid
0x140003d85  lea     r8d, [rdx+1]; dwClsContext
0x140003d89  call    cs:__imp_CoCreateInstance
0x140003d8f  mov     edi, eax
0x140003d91  test    eax, eax
0x140003d93  js      loc_140003E6E
0x140003d99  lea     rcx, [rsi+70h]
0x140003d9d  mov     [rbp+arg_0], 0
0x140003da5  mov     rax, [rcx]
0x140003da8  mov     rax, [rax+8]
0x140003dac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003db1  test    al, al
0x140003db3  jz      short loc_140003E13
0x140003db5  mov     rcx, [rbp+arg_0]
0x140003db9  test    rcx, rcx
0x140003dbc  jz      short loc_140003DD2
0x140003dbe  mov     [rbp+arg_0], 0
0x140003dc6  mov     rax, [rcx]
0x140003dc9  mov     rax, [rax+10h]
0x140003dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003dd2  mov     edx, [rsi+78h]
0x140003dd5  mov     [rbp+arg_0], 0
0x140003ddd  test    edx, edx
0x140003ddf  jz      short loc_140003E0A
0x140003de1  mov     edi, [rsi+7Ch]
0x140003de4  test    edi, edi
0x140003de6  js      short loc_140003E51
0x140003de8  mov     rcx, cs:qword_14000C868
0x140003def  lea     r9, [rbp+arg_0]
0x140003df3  lea     r8, _GUID_73aecad8_7e70_4e21_8767_82b03c862455
0x140003dfa  mov     rax, [rcx]
0x140003dfd  mov     rax, [rax+28h]
0x140003e01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003e06  mov     edi, eax
0x140003e08  jmp     short loc_140003E0F
0x140003e0a  mov     edi, 80070057h
0x140003e0f  test    edi, edi
0x140003e11  js      short loc_140003E51
0x140003e13  cmp     [rbp+arg_0], 0
0x140003e18  jnz     short loc_140003E34
0x140003e1a  mov     rcx, [rbp+arg_8]
0x140003e1e  lea     rdx, [rbp+arg_0]
0x140003e22  mov     rax, [rcx]
0x140003e25  mov     rax, [rax+28h]
0x140003e29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003e2e  mov     edi, eax
0x140003e30  test    eax, eax
0x140003e32  js      short loc_140003E51
0x140003e34  mov     rcx, [rbp+arg_8]
0x140003e38  mov     r9, [rbp+arg_0]
0x140003e3c  mov     r8, [rsi+58h]
0x140003e40  mov     edx, [rsi+60h]
0x140003e43  mov     rax, [rcx]
0x140003e46  mov     rax, [rax+20h]
0x140003e4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003e4f  mov     edi, eax
0x140003e51  mov     rcx, [rbp+arg_0]
0x140003e55  test    rcx, rcx
0x140003e58  jz      short loc_140003E6E
0x140003e5a  mov     [rbp+arg_0], 0
0x140003e62  mov     rax, [rcx]
0x140003e65  mov     rax, [rax+10h]
0x140003e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003e6e  mov     rcx, [rbp+arg_8]
0x140003e72  test    rcx, rcx
0x140003e75  jz      short loc_140003E8F
0x140003e77  mov     [rbp+arg_8], 0
0x140003e7f  mov     rax, [rcx]
0x140003e82  mov     rax, [rax+10h]
0x140003e86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003e8b  jmp     short loc_140003E8F
0x140003e8d  mov     edi, ebx
0x140003e8f  mov     [rsi+68h], edi
0x140003e92  test    ebx, ebx
0x140003e94  js      short loc_140003E9C
0x140003e96  call    cs:__imp_RoUninitialize
0x140003e9c  mov     rbx, [rsp+30h+arg_10]
0x140003ea1  mov     eax, edi
0x140003ea3  add     rsp, 30h
0x140003ea7  pop     rdi
0x140003ea8  pop     rsi
0x140003ea9  pop     rbp
0x140003eaa  retn
```
