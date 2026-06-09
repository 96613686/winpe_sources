# Microsoft::WRL::Module<2,Windows::Internal::ServiceModule>::UnregisterCOMObject(ushort const *,ulong *,uint)

- ea: `0x180006580`
- end: `0x1800065c3`
- name: `?UnregisterCOMObject@?$Module@$01VServiceModule@Internal@Windows@@@WRL@Microsoft@@UEAAJPEBGPEAKI@Z`
- size: `67`
- prototype: `HRESULT __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006580`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x1800065a3`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x1800065a3`

## pseudocode

```c
HRESULT __fastcall Microsoft::WRL::Module<2,Windows::Internal::ServiceModule>::UnregisterCOMObject(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4)
{
  HRESULT result; // eax
  __int64 i; // rbx
  DWORD v8; // ecx

  result = 0;
  for ( i = 0; (unsigned int)i < a4; i = (unsigned int)(i + 1) )
  {
    if ( result < 0 )
      break;
    v8 = *(_DWORD *)(a3 + 4 * i);
    if ( v8 )
    {
      result = CoRevokeClassObject(v8);
      if ( result >= 0 )
        *(_DWORD *)(a3 + 4 * i) = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180006580  push    rbx
0x180006582  push    rbp
0x180006583  push    rsi
0x180006584  push    rdi
0x180006585  sub     rsp, 28h
0x180006589  xor     eax, eax
0x18000658b  xor     ebx, ebx
0x18000658d  mov     ebp, r9d
0x180006590  mov     rsi, r8
0x180006593  test    r9d, r9d
0x180006596  jz      short loc_1800065BA
0x180006598  test    eax, eax
0x18000659a  js      short loc_1800065BA
0x18000659c  mov     ecx, [rsi+rbx*4]; dwRegister
0x18000659f  test    ecx, ecx
0x1800065a1  jz      short loc_1800065B4
0x1800065a3  call    cs:__imp_CoRevokeClassObject
0x1800065a9  test    eax, eax
0x1800065ab  js      short loc_1800065B4
0x1800065ad  mov     dword ptr [rsi+rbx*4], 0
0x1800065b4  inc     ebx
0x1800065b6  cmp     ebx, ebp
0x1800065b8  jb      short loc_180006598
0x1800065ba  add     rsp, 28h
0x1800065be  pop     rdi
0x1800065bf  pop     rsi
0x1800065c0  pop     rbp
0x1800065c1  pop     rbx
0x1800065c2  retn
```
