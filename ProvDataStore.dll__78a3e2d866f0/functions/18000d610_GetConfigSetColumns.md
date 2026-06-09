# GetConfigSetColumns

- ea: `0x18000d610`
- end: `0x18000d9ac`
- name: `GetConfigSetColumns`
- size: `924`
- prototype: `__int64 __fastcall(__int64 *, _QWORD *, _DWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d150`
- `0x18000e184`

## callees

- `0x18000d610`
- `0x18000f65c`
- `0x180012010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000d708`
- `msvcrt!_wcsicmp` at `0x18000d7d7`
- `msvcrt!_wcsicmp` at `0x18000d708`
- `msvcrt!_wcsicmp` at `0x18000d7d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d974`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d974`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18000d664`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18000d664`

## pseudocode

```c
__int64 __fastcall GetConfigSetColumns(__int64 *a1, _QWORD *a2, _DWORD *a3)
{
  __int64 *v3; // rsi
  HRESULT ClassObject; // edi
  int v5; // eax
  unsigned int v6; // r15d
  __int64 v7; // rdi
  unsigned int (__fastcall *v8)(__int64 *); // rax
  wil *v9; // rcx
  int v10; // eax
  __int64 v11; // r12
  _QWORD *v12; // r14
  bool v13; // zf
  __int64 v14; // rdi
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 i; // rsi
  __int64 v20; // rcx
  LPVOID v21; // rcx
  __int64 v23; // [rsp+30h] [rbp-68h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-60h] BYREF
  wchar_t *String1; // [rsp+40h] [rbp-58h] BYREF
  __int64 v26; // [rsp+48h] [rbp-50h] BYREF
  __int128 pv; // [rsp+50h] [rbp-48h] BYREF
  unsigned int v31; // [rsp+B8h] [rbp+20h] BYREF

  v3 = a1;
  v31 = 0;
  ppv = 0;
  pv = 0;
  ClassObject = CoGetClassObject(
                  &GUID_38be0989_9830_49a8_985b_7741219fd0fb,
                  1u,
                  0,
                  &GUID_00000001_0000_0000_c000_000000000046,
                  &ppv);
  if ( ClassObject < 0 )
    goto LABEL_39;
  ClassObject = (*(__int64 (__fastcall **)(__int64 *))(*v3 + 64))(v3);
  if ( ClassObject < 0 )
    goto LABEL_39;
  v5 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v3 + 184))(v3, &v31);
  ClassObject = v5;
  if ( v5 < 0 )
    goto LABEL_39;
  v6 = 0;
  LODWORD(v23) = 0;
  if ( v5 )
    goto LABEL_38;
  do
  {
    if ( v6 >= v31 )
      break;
    String1 = 0;
    ClassObject = (*(__int64 (__fastcall **)(__int64 *, wchar_t **, _QWORD))(*v3 + 112))(v3, &String1, 0);
    if ( ClassObject < 0 )
      goto LABEL_39;
    v7 = 0;
    do
    {
      if ( !_wcsicmp(String1, off_1800134C0[v7]) )
        break;
      v7 = (unsigned int)(v7 + 1);
    }
    while ( (unsigned int)v7 < 5 );
    v8 = *(unsigned int (__fastcall **)(__int64 *))(*v3 + 72);
    if ( (unsigned int)v7 >= 5 )
      LODWORD(v23) = ++v6;
  }
  while ( !v8(v3) );
  if ( !v6 )
  {
LABEL_38:
    ClassObject = -2147418113;
LABEL_39:
    v12 = (_QWORD *)pv;
    goto LABEL_40;
  }
  try
  {
    co_array_t<IMVKey *>::allocate((__int64)&pv, v6);
  }
  catch ( ... )
  {
    wil::ResultFromCaughtException(v9);
    v3 = a1;
    v6 = v23;
  }
  v10 = (*(__int64 (__fastcall **)(__int64 *))(*v3 + 64))(v3);
  ClassObject = v10;
  if ( v10 < 0 )
    goto LABEL_39;
  v11 = 0;
  v12 = (_QWORD *)pv;
  if ( v10 )
  {
LABEL_37:
    ClassObject = -2147418113;
    goto LABEL_40;
  }
  while ( 1 )
  {
    v13 = v6 == (_DWORD)v11;
    if ( v6 <= (unsigned int)v11 )
      goto LABEL_31;
    String1 = 0;
    v26 = 0;
    ClassObject = (*(__int64 (__fastcall **)(__int64 *, wchar_t **, _QWORD))(*v3 + 112))(v3, &String1, 0);
    if ( ClassObject < 0 )
      goto LABEL_40;
    v14 = 0;
    do
    {
      if ( !_wcsicmp(String1, off_1800134C0[v14]) )
        break;
      v14 = (unsigned int)(v14 + 1);
    }
    while ( (unsigned int)v14 < 5 );
    v15 = *v3;
    if ( (unsigned int)v14 >= 5 )
      break;
    ClassObject = (*(__int64 (__fastcall **)(__int64 *))(v15 + 72))(v3);
LABEL_29:
    if ( ClassObject )
    {
      v13 = v6 == (_DWORD)v11;
LABEL_31:
      if ( !v13 )
        goto LABEL_37;
      *a2 = v12;
      *a3 = DWORD2(pv);
      v12 = 0;
      DWORD2(pv) = 0;
      goto LABEL_40;
    }
  }
  ClassObject = (*(__int64 (__fastcall **)(__int64 *, __int64 *, _QWORD))(v15 + 128))(v3, &v26, 0);
  if ( ClassObject < 0 )
    goto LABEL_40;
  v23 = 0;
  ClassObject = (*(__int64 (__fastcall **)(LPVOID, _QWORD, GUID *, __int64 *))(*(_QWORD *)ppv + 24LL))(
                  ppv,
                  0,
                  &GUID_401e2463_465f_4bc9_9dc9_c6daf36894b0,
                  &v23);
  if ( ClassObject >= 0 )
  {
    ClassObject = (*(__int64 (__fastcall **)(__int64, wchar_t *, __int64))(*(_QWORD *)v23 + 24LL))(v23, String1, v26);
    if ( ClassObject < 0 )
    {
      v18 = v23;
      if ( !v23 )
        goto LABEL_40;
      goto LABEL_34;
    }
    v16 = v23;
    v23 = 0;
    v12[v11] = v16;
    v11 = (unsigned int)(v11 + 1);
    ClassObject = (*(__int64 (__fastcall **)(__int64 *))(*v3 + 72))(v3);
    v17 = v23;
    if ( v23 )
    {
      v23 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    goto LABEL_29;
  }
  v18 = v23;
  if ( v23 )
  {
LABEL_34:
    v23 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
LABEL_40:
  if ( v12 )
  {
    for ( i = 0; (unsigned int)i < DWORD2(pv); i = (unsigned int)(i + 1) )
    {
      v20 = v12[i];
      if ( v20 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        v12[i] = 0;
      }
    }
    CoTaskMemFree(v12);
  }
  v21 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v21 + 16LL))(v21);
  }
  return (unsigned int)ClassObject;
}

```

## disassembly

```asm
0x18000d610  mov     rax, rsp
0x18000d613  mov     [rax+18h], r8
0x18000d617  mov     [rax+10h], rdx
0x18000d61b  mov     [rax+8], rcx
0x18000d61f  push    rsi
0x18000d620  push    rdi
0x18000d621  push    r12
0x18000d623  push    r13
0x18000d625  push    r14
0x18000d627  push    r15
0x18000d629  sub     rsp, 68h
0x18000d62d  mov     rsi, rcx
0x18000d630  mov     dword ptr [rax+20h], 0
0x18000d637  mov     qword ptr [rax-60h], 0
0x18000d63f  xorps   xmm0, xmm0
0x18000d642  movups  xmmword ptr [rax-48h], xmm0
0x18000d646  lea     rax, [rax-60h]
0x18000d64a  mov     [rsp+98h+ppv], rax; ppv
0x18000d64f  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x18000d656  xor     r8d, r8d; pvReserved
0x18000d659  lea     edx, [r8+1]; dwClsContext
0x18000d65d  lea     rcx, _GUID_38be0989_9830_49a8_985b_7741219fd0fb; rclsid
0x18000d664  call    cs:__imp_CoGetClassObject
0x18000d66a  mov     edi, eax
0x18000d66c  test    eax, eax
0x18000d66e  js      loc_18000D93A
0x18000d674  mov     rax, [rsi]
0x18000d677  mov     rcx, rsi
0x18000d67a  mov     rax, [rax+40h]
0x18000d67e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d683  mov     edi, eax
0x18000d685  test    eax, eax
0x18000d687  js      loc_18000D93A
0x18000d68d  mov     rax, [rsi]
0x18000d690  lea     rdx, [rsp+98h+arg_18]
0x18000d698  mov     rcx, rsi
0x18000d69b  mov     rax, [rax+0B8h]
0x18000d6a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6a7  mov     edi, eax
0x18000d6a9  test    eax, eax
0x18000d6ab  js      loc_18000D93A
0x18000d6b1  xor     r15d, r15d
0x18000d6b4  mov     dword ptr [rsp+98h+var_68], r15d
0x18000d6b9  test    eax, eax
0x18000d6bb  jnz     loc_18000D935
0x18000d6c1  lea     r13, off_1800134C0; "Type"
0x18000d6c8  cmp     r15d, [rsp+98h+arg_18]
0x18000d6d0  jnb     short loc_18000D739
0x18000d6d2  mov     [rsp+98h+String1], 0
0x18000d6db  mov     rax, [rsi]
0x18000d6de  xor     r8d, r8d
0x18000d6e1  lea     rdx, [rsp+98h+String1]
0x18000d6e6  mov     rcx, rsi
0x18000d6e9  mov     rax, [rax+70h]
0x18000d6ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6f2  mov     edi, eax
0x18000d6f4  test    eax, eax
0x18000d6f6  js      loc_18000D93A
0x18000d6fc  xor     edi, edi
0x18000d6fe  mov     rdx, [r13+rdi*8+0]; String2
0x18000d703  mov     rcx, [rsp+98h+String1]; String1
0x18000d708  call    cs:__imp__wcsicmp
0x18000d70e  test    eax, eax
0x18000d710  jz      short loc_18000D719
0x18000d712  inc     edi
0x18000d714  cmp     edi, 5
0x18000d717  jb      short loc_18000D6FE
0x18000d719  mov     rax, [rsi]
0x18000d71c  mov     rax, [rax+48h]
0x18000d720  mov     rcx, rsi
0x18000d723  cmp     edi, 5
0x18000d726  jb      short loc_18000D730
0x18000d728  inc     r15d
0x18000d72b  mov     dword ptr [rsp+98h+var_68], r15d
0x18000d730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d735  test    eax, eax
0x18000d737  jz      short loc_18000D6C8
0x18000d739  test    r15d, r15d
0x18000d73c  jz      loc_18000D935
0x18000d742  mov     edx, r15d
0x18000d745  lea     rcx, [rsp+98h+pv]
0x18000d74a  call    ?allocate@?$co_array_t@PEAUIMVKey@@@@QEAAX_K@Z; co_array_t<IMVKey *>::allocate(unsigned __int64)
0x18000d74f  nop
0x18000d750  jmp     short loc_18000D766
0x18000d752  lea     r13, off_1800134C0; "Type"
0x18000d759  mov     rsi, [rsp+98h+arg_0]
0x18000d761  mov     r15d, dword ptr [rsp+98h+var_68]
0x18000d766  mov     rax, [rsi]
0x18000d769  mov     rcx, rsi
0x18000d76c  mov     rax, [rax+40h]
0x18000d770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d775  mov     edi, eax
0x18000d777  test    eax, eax
0x18000d779  js      loc_18000D93A
0x18000d77f  xor     r12d, r12d
0x18000d782  mov     r14, [rsp+98h+pv]
0x18000d787  test    eax, eax
0x18000d789  jnz     loc_18000D92E
0x18000d78f  cmp     r15d, r12d
0x18000d792  jbe     loc_18000D8C5
0x18000d798  mov     [rsp+98h+String1], 0
0x18000d7a1  mov     [rsp+98h+var_50], 0
0x18000d7aa  mov     rax, [rsi]
0x18000d7ad  xor     r8d, r8d
0x18000d7b0  lea     rdx, [rsp+98h+String1]
0x18000d7b5  mov     rcx, rsi
0x18000d7b8  mov     rax, [rax+70h]
0x18000d7bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7c1  mov     edi, eax
0x18000d7c3  test    eax, eax
0x18000d7c5  js      loc_18000D93F
0x18000d7cb  xor     edi, edi
0x18000d7cd  mov     rdx, [r13+rdi*8+0]; String2
0x18000d7d2  mov     rcx, [rsp+98h+String1]; String1
0x18000d7d7  call    cs:__imp__wcsicmp
0x18000d7dd  test    eax, eax
0x18000d7df  jz      short loc_18000D7E8
0x18000d7e1  inc     edi
0x18000d7e3  cmp     edi, 5
0x18000d7e6  jb      short loc_18000D7CD
0x18000d7e8  mov     rax, [rsi]
0x18000d7eb  mov     rcx, rsi
0x18000d7ee  cmp     edi, 5
0x18000d7f1  jnb     short loc_18000D803
0x18000d7f3  mov     rax, [rax+48h]
0x18000d7f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7fc  mov     edi, eax
0x18000d7fe  jmp     loc_18000D8BA
0x18000d803  xor     r8d, r8d
0x18000d806  lea     rdx, [rsp+98h+var_50]
0x18000d80b  mov     rax, [rax+80h]
0x18000d812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d817  mov     edi, eax
0x18000d819  test    eax, eax
0x18000d81b  js      loc_18000D93F
0x18000d821  mov     [rsp+98h+var_68], 0
0x18000d82a  mov     rcx, [rsp+98h+var_60]
0x18000d82f  mov     rax, [rcx]
0x18000d832  lea     r9, [rsp+98h+var_68]
0x18000d837  lea     r8, _GUID_401e2463_465f_4bc9_9dc9_c6daf36894b0
0x18000d83e  xor     edx, edx
0x18000d840  mov     rax, [rax+18h]
0x18000d844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d849  mov     edi, eax
0x18000d84b  test    eax, eax
0x18000d84d  js      loc_18000D90C
0x18000d853  mov     rcx, [rsp+98h+var_68]
0x18000d858  mov     rax, [rcx]
0x18000d85b  mov     r8, [rsp+98h+var_50]
0x18000d860  mov     rdx, [rsp+98h+String1]
0x18000d865  mov     rax, [rax+18h]
0x18000d869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d86e  mov     edi, eax
0x18000d870  test    eax, eax
0x18000d872  js      short loc_18000D8EA
0x18000d874  mov     rcx, [rsp+98h+var_68]
0x18000d879  mov     [rsp+98h+var_68], 0
0x18000d882  mov     [r14+r12*8], rcx
0x18000d886  inc     r12d
0x18000d889  mov     rax, [rsi]
0x18000d88c  mov     rcx, rsi
0x18000d88f  mov     rax, [rax+48h]
0x18000d893  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d898  mov     edi, eax
0x18000d89a  mov     rcx, [rsp+98h+var_68]
0x18000d89f  test    rcx, rcx
0x18000d8a2  jz      short loc_18000D8BA
0x18000d8a4  mov     [rsp+98h+var_68], 0
0x18000d8ad  mov     rax, [rcx]
0x18000d8b0  mov     rax, [rax+10h]
0x18000d8b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8b9  nop
0x18000d8ba  test    edi, edi
0x18000d8bc  jz      loc_18000D78F
0x18000d8c2  cmp     r15d, r12d
0x18000d8c5  jnz     short loc_18000D92E
0x18000d8c7  mov     rax, [rsp+98h+arg_8]
0x18000d8cf  mov     [rax], r14
0x18000d8d2  mov     eax, [rsp+98h+var_40]
0x18000d8d6  mov     rcx, [rsp+98h+arg_10]
0x18000d8de  mov     [rcx], eax
0x18000d8e0  xor     r14d, r14d
0x18000d8e3  mov     [rsp+98h+var_40], r14d
0x18000d8e8  jmp     short loc_18000D93F
0x18000d8ea  mov     rcx, [rsp+98h+var_68]
0x18000d8ef  test    rcx, rcx
0x18000d8f2  jz      short loc_18000D90A
0x18000d8f4  mov     [rsp+98h+var_68], 0
0x18000d8fd  mov     rax, [rcx]
0x18000d900  mov     rax, [rax+10h]
0x18000d904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d909  nop
0x18000d90a  jmp     short loc_18000D93F
0x18000d90c  mov     rcx, [rsp+98h+var_68]
0x18000d911  test    rcx, rcx
0x18000d914  jz      short loc_18000D92C
0x18000d916  mov     [rsp+98h+var_68], 0
0x18000d91f  mov     rax, [rcx]
0x18000d922  mov     rax, [rax+10h]
0x18000d926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d92b  nop
0x18000d92c  jmp     short loc_18000D93F
0x18000d92e  mov     edi, 8000FFFFh
0x18000d933  jmp     short loc_18000D93F
0x18000d935  mov     edi, 8000FFFFh
0x18000d93a  mov     r14, [rsp+98h+pv]
0x18000d93f  test    r14, r14
0x18000d942  jz      short loc_18000D97B
0x18000d944  xor     esi, esi
0x18000d946  cmp     [rsp+98h+var_40], esi
0x18000d94a  jbe     short loc_18000D971
0x18000d94c  mov     rcx, [r14+rsi*8]
0x18000d950  test    rcx, rcx
0x18000d953  jz      short loc_18000D969
0x18000d955  mov     rax, [rcx]
0x18000d958  mov     rax, [rax+10h]
0x18000d95c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d961  mov     qword ptr [r14+rsi*8], 0
0x18000d969  inc     esi
0x18000d96b  cmp     esi, [rsp+98h+var_40]
0x18000d96f  jb      short loc_18000D94C
0x18000d971  mov     rcx, r14; pv
0x18000d974  call    cs:__imp_CoTaskMemFree
0x18000d97a  nop
0x18000d97b  mov     rcx, [rsp+98h+var_60]
0x18000d980  test    rcx, rcx
0x18000d983  jz      short loc_18000D99B
0x18000d985  mov     [rsp+98h+var_60], 0
0x18000d98e  mov     rax, [rcx]
0x18000d991  mov     rax, [rax+10h]
0x18000d995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d99a  nop
0x18000d99b  mov     eax, edi
0x18000d99d  add     rsp, 68h
0x18000d9a1  pop     r15
0x18000d9a3  pop     r14
0x18000d9a5  pop     r13
0x18000d9a7  pop     r12
0x18000d9a9  pop     rdi
0x18000d9aa  pop     rsi
0x18000d9ab  retn
```
