# Microsoft::WRL::Module<2,MultipleUseOutOfProcModule>::UnregisterCOMObject(ushort const *,ulong *,uint)

- ea: `0x140008cd0`
- end: `0x140008d13`
- name: `?UnregisterCOMObject@?$Module@$01VMultipleUseOutOfProcModule@@@WRL@Microsoft@@UEAAJPEBGPEAKI@Z`
- size: `67`
- prototype: `HRESULT __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140008cd0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x140008cf3`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x140008cf3`

## pseudocode

```c
HRESULT __fastcall Microsoft::WRL::Module<2,MultipleUseOutOfProcModule>::UnregisterCOMObject(
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
0x140008cd0  push    rbx
0x140008cd2  push    rbp
0x140008cd3  push    rsi
0x140008cd4  push    rdi
0x140008cd5  sub     rsp, 28h
0x140008cd9  xor     eax, eax
0x140008cdb  xor     ebx, ebx
0x140008cdd  mov     ebp, r9d
0x140008ce0  mov     rsi, r8
0x140008ce3  test    r9d, r9d
0x140008ce6  jz      short loc_140008D0A
0x140008ce8  test    eax, eax
0x140008cea  js      short loc_140008D0A
0x140008cec  mov     ecx, [rsi+rbx*4]; dwRegister
0x140008cef  test    ecx, ecx
0x140008cf1  jz      short loc_140008D04
0x140008cf3  call    cs:__imp_CoRevokeClassObject
0x140008cf9  test    eax, eax
0x140008cfb  js      short loc_140008D04
0x140008cfd  mov     dword ptr [rsi+rbx*4], 0
0x140008d04  inc     ebx
0x140008d06  cmp     ebx, ebp
0x140008d08  jb      short loc_140008CE8
0x140008d0a  add     rsp, 28h
0x140008d0e  pop     rdi
0x140008d0f  pop     rsi
0x140008d10  pop     rbp
0x140008d11  pop     rbx
0x140008d12  retn
```
