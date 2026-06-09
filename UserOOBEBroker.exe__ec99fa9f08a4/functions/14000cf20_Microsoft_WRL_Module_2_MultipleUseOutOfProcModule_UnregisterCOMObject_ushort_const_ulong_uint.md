# Microsoft::WRL::Module<2,MultipleUseOutOfProcModule>::UnregisterCOMObject(ushort const *,ulong *,uint)

- ea: `0x14000cf20`
- end: `0x14000cf63`
- name: `?UnregisterCOMObject@?$Module@$01VMultipleUseOutOfProcModule@@@WRL@Microsoft@@UEAAJPEBGPEAKI@Z`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000cf20`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x14000cf43`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x14000cf43`

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
0x14000cf20  push    rbx
0x14000cf22  push    rbp
0x14000cf23  push    rsi
0x14000cf24  push    rdi
0x14000cf25  sub     rsp, 28h
0x14000cf29  xor     eax, eax
0x14000cf2b  xor     ebx, ebx
0x14000cf2d  mov     ebp, r9d
0x14000cf30  mov     rsi, r8
0x14000cf33  test    r9d, r9d
0x14000cf36  jz      short loc_14000CF5A
0x14000cf38  test    eax, eax
0x14000cf3a  js      short loc_14000CF5A
0x14000cf3c  mov     ecx, [rsi+rbx*4]; dwRegister
0x14000cf3f  test    ecx, ecx
0x14000cf41  jz      short loc_14000CF54
0x14000cf43  call    cs:__imp_CoRevokeClassObject
0x14000cf49  test    eax, eax
0x14000cf4b  js      short loc_14000CF54
0x14000cf4d  mov     dword ptr [rsi+rbx*4], 0
0x14000cf54  inc     ebx
0x14000cf56  cmp     ebx, ebp
0x14000cf58  jb      short loc_14000CF38
0x14000cf5a  add     rsp, 28h
0x14000cf5e  pop     rdi
0x14000cf5f  pop     rsi
0x14000cf60  pop     rbp
0x14000cf61  pop     rbx
0x14000cf62  retn
```
