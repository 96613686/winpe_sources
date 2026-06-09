# ManualRegisterInterfaces

- ea: `0x180002320`
- end: `0x180002466`
- name: `ManualRegisterInterfaces`
- size: `326`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002000`
- `0x180002320`
- `0x180002810`

## import_xrefs

- `ole32!CoRegisterClassObject` at `0x1800023da`
- `ole32!CoRegisterClassObject` at `0x1800023da`
- `ole32!CoRegisterPSClsid` at `0x18000240b`
- `ole32!CoRegisterPSClsid` at `0x18000240b`

## pseudocode

```c
__int64 ManualRegisterInterfaces()
{
  unsigned int ClassObject; // [rsp+30h] [rbp-38h]
  unsigned int v2; // [rsp+30h] [rbp-38h]
  unsigned __int64 i; // [rsp+38h] [rbp-30h]
  IID *rclsid; // [rsp+40h] [rbp-28h]
  LPVOID ppv; // [rsp+48h] [rbp-20h] BYREF

  if ( dword_18007B2C8 )
    return 1;
  for ( i = 0; i < 0xE; ++i )
  {
    _mm_lfence();
    rclsid = (&InterfacesToRegister)[2 * i];
    ClassObject = DllGetClassObject(rclsid, &IID_IUnknown, &ppv);
    if ( ClassObject )
      return ClassObject;
    v2 = CoRegisterClassObject(rclsid, (LPUNKNOWN)ppv, 1u, 1u, (LPDWORD)&(&InterfacesToRegister)[2 * i] + 2);
    if ( v2 || (v2 = CoRegisterPSClsid(rclsid, rclsid)) != 0 )
    {
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
      return v2;
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  dword_18007B2C8 = 1;
  return 0;
}

```

## disassembly

```asm
0x180002320  sub     rsp, 68h
0x180002324  mov     rax, cs:__security_cookie
0x18000232b  xor     rax, rsp
0x18000232e  mov     [rsp+68h+var_18], rax
0x180002333  cmp     cs:dword_18007B2C8, 0
0x18000233a  jz      short loc_180002346
0x18000233c  mov     eax, 1
0x180002341  jmp     loc_180002454
0x180002346  mov     [rsp+68h+var_30], 0
0x18000234f  jmp     short loc_18000235E
0x180002351  mov     rax, [rsp+68h+var_30]
0x180002356  inc     rax
0x180002359  mov     [rsp+68h+var_30], rax
0x18000235e  cmp     [rsp+68h+var_30], 0Eh
0x180002364  jnb     loc_180002448
0x18000236a  lfence
0x18000236d  imul    rax, [rsp+68h+var_30], 10h
0x180002373  lea     rcx, InterfacesToRegister
0x18000237a  mov     rax, [rcx+rax]
0x18000237e  mov     [rsp+68h+rclsid], rax
0x180002383  lea     r8, [rsp+68h+ppv]; ppv
0x180002388  lea     rdx, IID_IUnknown; riid
0x18000238f  mov     rcx, [rsp+68h+rclsid]; rclsid
0x180002394  call    DllGetClassObject
0x180002399  mov     [rsp+68h+var_38], eax
0x18000239d  cmp     [rsp+68h+var_38], 0
0x1800023a2  jz      short loc_1800023AD
0x1800023a4  mov     eax, [rsp+68h+var_38]
0x1800023a8  jmp     loc_180002454
0x1800023ad  imul    rax, [rsp+68h+var_30], 10h
0x1800023b3  lea     rcx, InterfacesToRegister
0x1800023ba  lea     rax, [rcx+rax+8]
0x1800023bf  mov     [rsp+68h+lpdwRegister], rax; lpdwRegister
0x1800023c4  mov     r9d, 1; flags
0x1800023ca  mov     r8d, 1; dwClsContext
0x1800023d0  mov     rdx, [rsp+68h+ppv]; pUnk
0x1800023d5  mov     rcx, [rsp+68h+rclsid]; rclsid
0x1800023da  call    cs:__imp_CoRegisterClassObject
0x1800023e0  mov     [rsp+68h+var_38], eax
0x1800023e4  cmp     [rsp+68h+var_38], 0
0x1800023e9  jz      short loc_180002401
0x1800023eb  mov     rax, [rsp+68h+ppv]
0x1800023f0  mov     rax, [rax]
0x1800023f3  mov     rcx, [rsp+68h+ppv]
0x1800023f8  call    qword ptr [rax+10h]
0x1800023fb  mov     eax, [rsp+68h+var_38]
0x1800023ff  jmp     short loc_180002454
0x180002401  mov     rdx, [rsp+68h+rclsid]; rclsid
0x180002406  mov     rcx, [rsp+68h+rclsid]; riid
0x18000240b  call    cs:__imp_CoRegisterPSClsid
0x180002411  mov     [rsp+68h+var_38], eax
0x180002415  cmp     [rsp+68h+var_38], 0
0x18000241a  jz      short loc_180002432
0x18000241c  mov     rax, [rsp+68h+ppv]
0x180002421  mov     rax, [rax]
0x180002424  mov     rcx, [rsp+68h+ppv]
0x180002429  call    qword ptr [rax+10h]
0x18000242c  mov     eax, [rsp+68h+var_38]
0x180002430  jmp     short loc_180002454
0x180002432  mov     rax, [rsp+68h+ppv]
0x180002437  mov     rax, [rax]
0x18000243a  mov     rcx, [rsp+68h+ppv]
0x18000243f  call    qword ptr [rax+10h]
0x180002442  nop
0x180002443  jmp     loc_180002351
0x180002448  mov     cs:dword_18007B2C8, 1
0x180002452  xor     eax, eax
0x180002454  mov     rcx, [rsp+68h+var_18]
0x180002459  xor     rcx, rsp; StackCookie
0x18000245c  call    __security_check_cookie
0x180002461  add     rsp, 68h
0x180002465  retn
```
