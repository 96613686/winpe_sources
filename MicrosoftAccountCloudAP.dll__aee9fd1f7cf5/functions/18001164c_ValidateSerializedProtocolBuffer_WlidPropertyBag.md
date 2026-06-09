# ValidateSerializedProtocolBuffer(_WlidPropertyBag *)

- ea: `0x18001164c`
- end: `0x1800116cb`
- name: `?ValidateSerializedProtocolBuffer@@YAJPEAU_WlidPropertyBag@@@Z`
- size: `127`
- prototype: `__int64 __fastcall(struct _WlidPropertyBag *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180013478`

## callees

- `0x180008440`
- `0x18000baac`
- `0x18001164c`

## string_xrefs

- `0x18001167d`: `onecoreuap\ds\ext\live\identity\cloudapplugin\utils.cpp`
- `0x180011657`: `ValidateSerializedProtocolBuffer`

## pseudocode

```c
__int64 __fastcall ValidateSerializedProtocolBuffer(struct _WlidPropertyBag *a1)
{
  __int64 v2; // rcx
  unsigned int v3; // ebx
  _BYTE v5[8]; // [rsp+20h] [rbp-28h] BYREF
  int *v6; // [rsp+28h] [rbp-20h]
  __int64 v7; // [rsp+30h] [rbp-18h]
  __int64 v8; // [rsp+38h] [rbp-10h]
  int v9; // [rsp+50h] [rbp+8h] BYREF

  v9 = 0;
  v7 = 0;
  v8 = 0;
  v6 = &v9;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\utils.cpp",
    "ValidateSerializedProtocolBuffer",
    (const char *)0xDC,
    0,
    (const unsigned __int16 *)"ValidateSerializedProtocolBuffer");
  if ( *(_DWORD *)a1 >= 3u
    && (v2 = *((_QWORD *)a1 + 1), *(_DWORD *)v2 == 4)
    && **(_DWORD **)(v2 + 8) == 2
    && (*(_BYTE *)(v2 + 16) & 1) == 0 )
  {
    v3 = v9;
  }
  else
  {
    v3 = -1073741811;
    v9 = -1073741811;
  }
  CTraceFuncW<long>::~CTraceFuncW<long>(v5);
  return v3;
}

```

## disassembly

```asm
0x18001164c  mov     r11, rsp
0x18001164f  push    rbx
0x180011650  sub     rsp, 40h
0x180011654  mov     rbx, rcx
0x180011657  lea     rdx, aValidateserial; "ValidateSerializedProtocolBuffer"
0x18001165e  xor     ecx, ecx
0x180011660  mov     [r11-28h], rdx
0x180011664  mov     [rsp+48h+arg_0], ecx
0x180011668  lea     rax, [r11+8]
0x18001166c  mov     [r11-18h], rcx
0x180011670  xor     r9d, r9d; unsigned int
0x180011673  mov     [r11-10h], rcx
0x180011677  mov     r8d, 0DCh; char *
0x18001167d  lea     rcx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x180011684  mov     [r11-20h], rax
0x180011688  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18001168d  cmp     dword ptr [rbx], 3
0x180011690  jb      short loc_1800116B0
0x180011692  mov     rcx, [rbx+8]
0x180011696  cmp     dword ptr [rcx], 4
0x180011699  jnz     short loc_1800116B0
0x18001169b  mov     rax, [rcx+8]
0x18001169f  cmp     dword ptr [rax], 2
0x1800116a2  jnz     short loc_1800116B0
0x1800116a4  test    byte ptr [rcx+10h], 1
0x1800116a8  jnz     short loc_1800116B0
0x1800116aa  mov     ebx, [rsp+48h+arg_0]
0x1800116ae  jmp     short loc_1800116B9
0x1800116b0  mov     ebx, 0C000000Dh
0x1800116b5  mov     [rsp+48h+arg_0], ebx
0x1800116b9  lea     rcx, [rsp+48h+var_28]
0x1800116be  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x1800116c3  mov     eax, ebx
0x1800116c5  add     rsp, 40h
0x1800116c9  pop     rbx
0x1800116ca  retn
```
