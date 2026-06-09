# Microsoft::WRL::Module<2,CSingleUseOutOfProcModule>::UnregisterCOMObject(ushort const *,ulong *,uint)

- ea: `0x140003650`
- end: `0x140003693`
- name: `?UnregisterCOMObject@?$Module@$01VCSingleUseOutOfProcModule@@@WRL@Microsoft@@UEAAJPEBGPEAKI@Z`
- size: `67`
- prototype: `HRESULT __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140003650`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x140003673`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x140003673`

## pseudocode

```c
HRESULT __fastcall Microsoft::WRL::Module<2,CSingleUseOutOfProcModule>::UnregisterCOMObject(
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
0x140003650  push    rbx
0x140003652  push    rbp
0x140003653  push    rsi
0x140003654  push    rdi
0x140003655  sub     rsp, 28h
0x140003659  xor     eax, eax
0x14000365b  xor     ebx, ebx
0x14000365d  mov     ebp, r9d
0x140003660  mov     rsi, r8
0x140003663  test    r9d, r9d
0x140003666  jz      short loc_14000368A
0x140003668  test    eax, eax
0x14000366a  js      short loc_14000368A
0x14000366c  mov     ecx, [rsi+rbx*4]; dwRegister
0x14000366f  test    ecx, ecx
0x140003671  jz      short loc_140003684
0x140003673  call    cs:__imp_CoRevokeClassObject
0x140003679  test    eax, eax
0x14000367b  js      short loc_140003684
0x14000367d  mov     dword ptr [rsi+rbx*4], 0
0x140003684  inc     ebx
0x140003686  cmp     ebx, ebp
0x140003688  jb      short loc_140003668
0x14000368a  add     rsp, 28h
0x14000368e  pop     rdi
0x14000368f  pop     rsi
0x140003690  pop     rbp
0x140003691  pop     rbx
0x140003692  retn
```
