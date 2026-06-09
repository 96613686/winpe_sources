# CCPLUserMgrBroker::s_RunFlowASTA(void *)

- ea: `0x140003b30`
- end: `0x140003d3a`
- name: `?s_RunFlowASTA@CCPLUserMgrBroker@@CAKPEAX@Z`
- size: `522`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140003b30`
- `0x140007010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140003b79`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140003b79`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x140003b44`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x140003b44`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x140003d25`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x140003d25`

## pseudocode

```c
// AFR coverage: broker thread only CoCreateInstance(CLSID_UserManagementWizards) and forwards task params; no file sink in EXE.
__int64 __fastcall CCPLUserMgrBroker::s_RunFlowASTA(_DWORD *a1)
{
  int v2; // ebx
  HRESULT v3; // edi
  __int64 v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rcx
  LPVOID v10; // rcx
  __int64 v12; // [rsp+60h] [rbp+20h] BYREF
  __int64 v13; // [rsp+68h] [rbp+28h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp+30h] BYREF

  v2 = RoInitialize(0);
  if ( v2 < 0 )
  {
    v3 = v2;
    goto LABEL_27;
  }
  ppv = 0;
  v3 = CoCreateInstance(&CLSID_UserManagementWizards, 0, 1u, &GUID_251f5a5a_564a_4889_bb5e_be7cfab519c7, &ppv);
  if ( v3 >= 0 )
  {
    v13 = 0;
    if ( (*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)a1 + 16) + 8LL))((char *)a1 + 128) )
    {
      v4 = v13;
      if ( v13 )
      {
        v13 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
      }
      v5 = (unsigned int)a1[34];
      v13 = 0;
      if ( (_DWORD)v5 )
      {
        v3 = a1[35];
        if ( v3 >= 0 )
          v3 = (*(__int64 (__fastcall **)(__int64, __int64, GUID *, __int64 *))(*(_QWORD *)qword_14000C868 + 40LL))(
                 qword_14000C868,
                 v5,
                 &GUID_e93cf64b_c14d_4a1a_9572_adab3c2e9461,
                 &v13);
      }
      else
      {
        v3 = -2147024809;
      }
    }
    v12 = 0;
    if ( v3 < 0 )
      goto LABEL_20;
    if ( !(*(unsigned __int8 (__fastcall **)(char *))(*((_QWORD *)a1 + 18) + 8LL))((char *)a1 + 144) )
      goto LABEL_19;
    v6 = v12;
    if ( v12 )
    {
      v12 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    v7 = (unsigned int)a1[38];
    v12 = 0;
    if ( (_DWORD)v7 )
    {
      v3 = a1[39];
      if ( v3 < 0 )
        goto LABEL_20;
      v3 = (*(__int64 (__fastcall **)(__int64, __int64, GUID *, __int64 *))(*(_QWORD *)qword_14000C868 + 40LL))(
             qword_14000C868,
             v7,
             &GUID_3ee328ab_8f69_420a_9b86_7080f22af38b,
             &v12);
    }
    else
    {
      v3 = -2147024809;
    }
    if ( v3 >= 0 )
LABEL_19:
      v3 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD, _QWORD, __int64, __int64))(*(_QWORD *)ppv + 24LL))(
             ppv,
             *((_QWORD *)a1 + 11),
             (unsigned int)a1[24],
             (unsigned int)a1[25],
             v13,
             v12);
LABEL_20:
    v8 = v12;
    if ( v12 )
    {
      v12 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    v9 = v13;
    if ( v13 )
    {
      v13 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
  }
  v10 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v10 + 16LL))(v10);
  }
LABEL_27:
  a1[26] = v3;
  if ( v2 >= 0 )
    RoUninitialize();
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140003b30  mov     [rsp-18h+arg_18], rbx; AFR coverage: broker thread only CoCreateInstance(CLSID_UserManagementWizards) and forwards task params; no file sink in EXE.
0x140003b35  push    rbp
0x140003b36  push    rsi
0x140003b37  push    rdi
0x140003b38  mov     rbp, rsp
0x140003b3b  sub     rsp, 40h
0x140003b3f  mov     rsi, rcx
0x140003b42  xor     ecx, ecx
0x140003b44  call    cs:__imp_RoInitialize
0x140003b4a  mov     ebx, eax
0x140003b4c  test    eax, eax
0x140003b4e  js      loc_140003D1C
0x140003b54  xor     edx, edx; pUnkOuter
0x140003b56  mov     [rbp+arg_10], 0
0x140003b5e  lea     rax, [rbp+arg_10]
0x140003b62  lea     r9, _GUID_251f5a5a_564a_4889_bb5e_be7cfab519c7; riid
0x140003b69  mov     [rsp+40h+ppv], rax; ppv
0x140003b6e  lea     rcx, CLSID_UserManagementWizards; rclsid
0x140003b75  lea     r8d, [rdx+1]; dwClsContext
0x140003b79  call    cs:__imp_CoCreateInstance
0x140003b7f  mov     edi, eax
0x140003b81  test    eax, eax
0x140003b83  js      loc_140003CFD
0x140003b89  lea     rcx, [rsi+80h]
0x140003b90  mov     [rbp+arg_8], 0
0x140003b98  mov     rdx, [rcx]
0x140003b9b  mov     rax, [rdx+8]
0x140003b9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003ba4  test    al, al
0x140003ba6  jz      short loc_140003C08
0x140003ba8  mov     rcx, [rbp+arg_8]
0x140003bac  test    rcx, rcx
0x140003baf  jz      short loc_140003BC5
0x140003bb1  mov     [rbp+arg_8], 0
0x140003bb9  mov     rax, [rcx]
0x140003bbc  mov     rax, [rax+10h]
0x140003bc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003bc5  mov     edx, [rsi+88h]
0x140003bcb  mov     [rbp+arg_8], 0
0x140003bd3  test    edx, edx
0x140003bd5  jz      short loc_140003C03
0x140003bd7  mov     edi, [rsi+8Ch]
0x140003bdd  test    edi, edi
0x140003bdf  js      short loc_140003C08
0x140003be1  mov     rcx, cs:qword_14000C868
0x140003be8  lea     r9, [rbp+arg_8]
0x140003bec  lea     r8, _GUID_e93cf64b_c14d_4a1a_9572_adab3c2e9461
0x140003bf3  mov     rax, [rcx]
0x140003bf6  mov     rax, [rax+28h]
0x140003bfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003bff  mov     edi, eax
0x140003c01  jmp     short loc_140003C08
0x140003c03  mov     edi, 80070057h
0x140003c08  mov     [rbp+arg_0], 0
0x140003c10  test    edi, edi
0x140003c12  js      loc_140003CC3
0x140003c18  lea     rcx, [rsi+90h]
0x140003c1f  mov     rax, [rcx]
0x140003c22  mov     rax, [rax+8]
0x140003c26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003c2b  test    al, al
0x140003c2d  jz      short loc_140003C93
0x140003c2f  mov     rcx, [rbp+arg_0]
0x140003c33  test    rcx, rcx
0x140003c36  jz      short loc_140003C4C
0x140003c38  mov     [rbp+arg_0], 0
0x140003c40  mov     rax, [rcx]
0x140003c43  mov     rax, [rax+10h]
0x140003c47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003c4c  mov     edx, [rsi+98h]
0x140003c52  mov     [rbp+arg_0], 0
0x140003c5a  test    edx, edx
0x140003c5c  jz      short loc_140003C8A
0x140003c5e  mov     edi, [rsi+9Ch]
0x140003c64  test    edi, edi
0x140003c66  js      short loc_140003CC3
0x140003c68  mov     rcx, cs:qword_14000C868
0x140003c6f  lea     r9, [rbp+arg_0]
0x140003c73  lea     r8, _GUID_3ee328ab_8f69_420a_9b86_7080f22af38b
0x140003c7a  mov     rax, [rcx]
0x140003c7d  mov     rax, [rax+28h]
0x140003c81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003c86  mov     edi, eax
0x140003c88  jmp     short loc_140003C8F
0x140003c8a  mov     edi, 80070057h
0x140003c8f  test    edi, edi
0x140003c91  js      short loc_140003CC3
0x140003c93  mov     rdx, [rbp+arg_0]
0x140003c97  mov     r8, [rbp+arg_8]
0x140003c9b  mov     rcx, [rbp+arg_10]
0x140003c9f  mov     r9d, [rsi+64h]
0x140003ca3  mov     [rsp+40h+var_18], rdx
0x140003ca8  mov     rdx, [rsi+58h]
0x140003cac  mov     rax, [rcx]
0x140003caf  mov     [rsp+40h+ppv], r8
0x140003cb4  mov     r8d, [rsi+60h]
0x140003cb8  mov     rax, [rax+18h]
0x140003cbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003cc1  mov     edi, eax
0x140003cc3  mov     rcx, [rbp+arg_0]
0x140003cc7  test    rcx, rcx
0x140003cca  jz      short loc_140003CE0
0x140003ccc  mov     [rbp+arg_0], 0
0x140003cd4  mov     rax, [rcx]
0x140003cd7  mov     rax, [rax+10h]
0x140003cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003ce0  mov     rcx, [rbp+arg_8]
0x140003ce4  test    rcx, rcx
0x140003ce7  jz      short loc_140003CFD
0x140003ce9  mov     [rbp+arg_8], 0
0x140003cf1  mov     rax, [rcx]
0x140003cf4  mov     rax, [rax+10h]
0x140003cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003cfd  mov     rcx, [rbp+arg_10]
0x140003d01  test    rcx, rcx
0x140003d04  jz      short loc_140003D1E
0x140003d06  mov     [rbp+arg_10], 0
0x140003d0e  mov     rax, [rcx]
0x140003d11  mov     rax, [rax+10h]
0x140003d15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d1a  jmp     short loc_140003D1E
0x140003d1c  mov     edi, ebx
0x140003d1e  mov     [rsi+68h], edi
0x140003d21  test    ebx, ebx
0x140003d23  js      short loc_140003D2B
0x140003d25  call    cs:__imp_RoUninitialize
0x140003d2b  mov     rbx, [rsp+40h+arg_18]
0x140003d30  mov     eax, edi
0x140003d32  add     rsp, 40h
0x140003d36  pop     rdi
0x140003d37  pop     rsi
0x140003d38  pop     rbp
0x140003d39  retn
```
