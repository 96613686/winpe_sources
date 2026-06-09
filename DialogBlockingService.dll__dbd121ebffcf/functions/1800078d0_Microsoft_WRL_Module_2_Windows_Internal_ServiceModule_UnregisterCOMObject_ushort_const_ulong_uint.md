# Microsoft::WRL::Module<2,Windows::Internal::ServiceModule>::UnregisterCOMObject(ushort const *,ulong *,uint)

- ea: `0x1800078d0`
- end: `0x180007913`
- name: `?UnregisterCOMObject@?$Module@$01VServiceModule@Internal@Windows@@@WRL@Microsoft@@UEAAJPEBGPEAKI@Z`
- size: `67`
- prototype: `HRESULT __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800078d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x1800078f3`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x1800078f3`

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
0x1800078d0  push    rbx
0x1800078d2  push    rbp
0x1800078d3  push    rsi
0x1800078d4  push    rdi
0x1800078d5  sub     rsp, 28h
0x1800078d9  xor     eax, eax
0x1800078db  xor     ebx, ebx
0x1800078dd  mov     ebp, r9d
0x1800078e0  mov     rsi, r8
0x1800078e3  test    r9d, r9d
0x1800078e6  jz      short loc_18000790A
0x1800078e8  test    eax, eax
0x1800078ea  js      short loc_18000790A
0x1800078ec  mov     ecx, [rsi+rbx*4]; dwRegister
0x1800078ef  test    ecx, ecx
0x1800078f1  jz      short loc_180007904
0x1800078f3  call    cs:__imp_CoRevokeClassObject
0x1800078f9  test    eax, eax
0x1800078fb  js      short loc_180007904
0x1800078fd  mov     dword ptr [rsi+rbx*4], 0
0x180007904  inc     ebx
0x180007906  cmp     ebx, ebp
0x180007908  jb      short loc_1800078E8
0x18000790a  add     rsp, 28h
0x18000790e  pop     rdi
0x18000790f  pop     rsi
0x180007910  pop     rbp
0x180007911  pop     rbx
0x180007912  retn
```
