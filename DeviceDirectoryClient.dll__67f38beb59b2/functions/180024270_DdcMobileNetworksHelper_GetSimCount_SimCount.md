# DdcMobileNetworksHelper::GetSimCount(SimCount *)

- ea: `0x180024270`
- end: `0x18002431f`
- name: `?GetSimCount@DdcMobileNetworksHelper@@CAJPEAW4SimCount@@@Z`
- size: `175`
- prototype: `__int64 __fastcall(enum SimCount *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180023f8c`

## callees

- `0x1800050b8`
- `0x180024270`
- `0x18002439c`

## string_xrefs

- `0x1800242af`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcmobilenetworkshelper.cpp`

## pseudocode

```c
__int64 __fastcall DdcMobileNetworksHelper::GetSimCount(enum SimCount *a1, int a2)
{
  int v3; // edi
  int v5; // [rsp+40h] [rbp+8h] BYREF
  unsigned int v6; // [rsp+48h] [rbp+10h] BYREF

  v5 = 0;
  v6 = 4;
  if ( a1 )
  {
    v3 = DdcMobileNetworksHelper::QueryWnfState(&WNF_CELL_RADIO_TYPE_MODEM0, &v5, &v6);
    if ( v3 < 0 )
      v3 = 0;
    if ( v5 )
    {
      if ( v5 == 5 || v5 == 6 || (unsigned int)(v5 - 8) < 2 )
        *(_DWORD *)a1 = 2;
      else
        *(_DWORD *)a1 = 1;
    }
    else
    {
      *(_DWORD *)a1 = 0;
    }
  }
  else
  {
    v3 = -2147024809;
    if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        0,
        a2,
        -2147024809,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcmobilenetworkshelper.cpp",
        163,
        "CPR(peSimCount)");
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180024270  mov     [rsp+arg_10], rbx
0x180024275  push    rdi
0x180024276  sub     rsp, 30h
0x18002427a  mov     [rsp+38h+arg_0], 0
0x180024282  mov     rbx, rcx
0x180024285  mov     [rsp+38h+arg_8], 4
0x18002428d  test    rcx, rcx
0x180024290  jnz     short loc_1800242C5
0x180024292  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180024299  mov     edi, 80070057h
0x18002429e  jz      short loc_180024312
0x1800242a0  lea     rax, aCprPesimcount; "CPR(peSimCount)"
0x1800242a7  mov     r8d, edi
0x1800242aa  mov     [rsp+38h+var_10], rax
0x1800242af  lea     r9, aOnecoreuapShel_14; "onecoreuap\\shell\\devicedirectory\\dev"...
0x1800242b6  mov     [rsp+38h+var_18], 1A3h
0x1800242be  call    McTemplateU0dsqs_EventWriteTransfer
0x1800242c3  jmp     short loc_180024312
0x1800242c5  lea     r8, [rsp+38h+arg_8]; unsigned int *
0x1800242ca  lea     rdx, [rsp+38h+arg_0]; void *
0x1800242cf  lea     rcx, WNF_CELL_RADIO_TYPE_MODEM0; struct _WNF_STATE_NAME *
0x1800242d6  call    ?QueryWnfState@DdcMobileNetworksHelper@@CAJPEBU_WNF_STATE_NAME@@PEAXPEAK@Z; DdcMobileNetworksHelper::QueryWnfState(_WNF_STATE_NAME const *,void *,ulong *)
0x1800242db  mov     ecx, [rsp+38h+arg_0]
0x1800242df  mov     edi, eax
0x1800242e1  xor     eax, eax
0x1800242e3  test    edi, edi
0x1800242e5  cmovs   edi, eax
0x1800242e8  test    ecx, ecx
0x1800242ea  jz      short loc_180024310
0x1800242ec  sub     ecx, 5
0x1800242ef  jz      short loc_180024308
0x1800242f1  sub     ecx, 1
0x1800242f4  jz      short loc_180024308
0x1800242f6  sub     ecx, 2
0x1800242f9  jz      short loc_180024308
0x1800242fb  cmp     ecx, 1
0x1800242fe  jz      short loc_180024308
0x180024300  mov     dword ptr [rbx], 1
0x180024306  jmp     short loc_180024312
0x180024308  mov     dword ptr [rbx], 2
0x18002430e  jmp     short loc_180024312
0x180024310  mov     [rbx], eax
0x180024312  mov     rbx, [rsp+38h+arg_10]
0x180024317  mov     eax, edi
0x180024319  add     rsp, 30h
0x18002431d  pop     rdi
0x18002431e  retn
```
