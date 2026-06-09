# MpCoCreateUnknownComObject_CMsMpSimpleConfig_

- ea: `0x180002a60`
- end: `0x180002b4b`
- name: `MpCoCreateUnknownComObject_CMsMpSimpleConfig_`
- size: `235`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003b30`

## callees

- `0x180002a60`
- `0x1800039bc`
- `0x180004ccc`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall MpCoCreateUnknownComObject_CMsMpSimpleConfig_(_QWORD *a1)
{
  int v2; // edi
  CMsMpSimpleConfig *v3; // rbx
  __int64 (__fastcall **v4)(_QWORD, GUID *, _QWORD *); // rax
  char *v6; // rbx
  __int64 v7; // rax
  __int64 v8; // [rsp+30h] [rbp+8h] BYREF
  CMsMpSimpleConfig *v9; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  v9 = 0;
  v2 = ATL::CComObject<CMsMpSimpleConfig>::CreateInstance(&v9);
  if ( v2 < 0 )
    return (unsigned int)v2;
  v3 = v9;
  (*(void (__fastcall **)(char *))(*((_QWORD *)v9 + 8) + 8LL))((char *)v9 + 64);
  v2 = CMsMpSimpleConfig::Initialize(v3);
  if ( v2 < 0 )
  {
    if ( !v3 )
      return (unsigned int)v2;
    v4 = (__int64 (__fastcall **)(_QWORD, GUID *, _QWORD *))*((_QWORD *)v3 + 8);
LABEL_5:
    ((void (*)(void))v4[2])();
    return (unsigned int)v2;
  }
  v8 = 0;
  v6 = (char *)v3 + 64;
  v2 = (**(__int64 (__fastcall ***)(char *, GUID *, __int64 *))v6)(v6, &GUID_00000000_0000_0000_c000_000000000046, &v8);
  if ( v2 < 0 )
  {
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    v4 = *(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *))v6;
    goto LABEL_5;
  }
  v7 = v8;
  v8 = 0;
  *a1 = v7;
  (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 16LL))(v6);
  return 0;
}

```

## disassembly

```asm
0x180002a60  mov     rax, rsp
0x180002a63  mov     [rax+18h], rbx
0x180002a67  mov     [rax+20h], rsi
0x180002a6b  push    rdi
0x180002a6c  sub     rsp, 20h
0x180002a70  mov     rsi, rcx
0x180002a73  mov     qword ptr [rcx], 0
0x180002a7a  mov     qword ptr [rax+10h], 0
0x180002a82  lea     rcx, [rax+10h]
0x180002a86  call    ?CreateInstance@?$CComObject@VCMsMpSimpleConfig@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CMsMpSimpleConfig>::CreateInstance(ATL::CComObject<CMsMpSimpleConfig> * *)
0x180002a8b  mov     edi, eax
0x180002a8d  test    eax, eax
0x180002a8f  js      short loc_180002AC9
0x180002a91  mov     rbx, [rsp+28h+arg_8]
0x180002a96  lea     rcx, [rbx+40h]
0x180002a9a  mov     rax, [rcx]
0x180002a9d  mov     rax, [rax+8]
0x180002aa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002aa6  mov     rcx, rbx; this
0x180002aa9  call    ?Initialize@CMsMpSimpleConfig@@QEAAJXZ; CMsMpSimpleConfig::Initialize(void)
0x180002aae  mov     edi, eax
0x180002ab0  test    eax, eax
0x180002ab2  jns     short loc_180002ADB
0x180002ab4  test    rbx, rbx
0x180002ab7  jz      short loc_180002AC9
0x180002ab9  lea     rcx, [rbx+40h]
0x180002abd  mov     rax, [rcx]
0x180002ac0  mov     rax, [rax+10h]
0x180002ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ac9  mov     eax, edi
0x180002acb  mov     rbx, [rsp+28h+arg_10]
0x180002ad0  mov     rsi, [rsp+28h+arg_18]
0x180002ad5  add     rsp, 20h
0x180002ad9  pop     rdi
0x180002ada  retn
0x180002adb  mov     [rsp+28h+arg_0], 0
0x180002ae4  add     rbx, 40h ; '@'
0x180002ae8  mov     rax, [rbx]
0x180002aeb  lea     r8, [rsp+28h+arg_0]
0x180002af0  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x180002af7  mov     rcx, rbx
0x180002afa  mov     rax, [rax]
0x180002afd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b02  mov     edi, eax
0x180002b04  test    eax, eax
0x180002b06  jns     short loc_180002B27
0x180002b08  mov     rcx, [rsp+28h+arg_0]
0x180002b0d  test    rcx, rcx
0x180002b10  jz      short loc_180002B1F
0x180002b12  mov     rdx, [rcx]
0x180002b15  mov     rax, [rdx+10h]
0x180002b19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b1e  nop
0x180002b1f  mov     rax, [rbx]
0x180002b22  mov     rcx, rbx
0x180002b25  jmp     short loc_180002AC0
0x180002b27  mov     rax, [rsp+28h+arg_0]
0x180002b2c  mov     [rsp+28h+arg_0], 0
0x180002b35  mov     [rsi], rax
0x180002b38  mov     rax, [rbx]
0x180002b3b  mov     rcx, rbx
0x180002b3e  mov     rax, [rax+10h]
0x180002b42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b47  xor     eax, eax
0x180002b49  jmp     short loc_180002ACB
```
