# BthEnumBuildDeviceCompatibleIds

- ea: `0x140018008`
- end: `0x140018124`
- name: `BthEnumBuildDeviceCompatibleIds`
- size: `284`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140019058`

## callees

- `0x1400013e8`
- `0x1400014cc`
- `0x140018008`

## import_xrefs

- `ntoskrnl!ExFreePool` at `0x1400180d9`
- `ntoskrnl!ExFreePool` at `0x1400180d9`
- `ntoskrnl!ExAllocatePool2` at `0x140018024`
- `ntoskrnl!ExAllocatePool2` at `0x140018024`

## pseudocode

```c
__int64 __fastcall BthEnumBuildDeviceCompatibleIds(__int64 a1, _QWORD *a2)
{
  _WORD *Pool2; // rbx
  unsigned int v4; // edi
  __int64 v5; // rax
  const wchar_t *v6; // rcx
  __int64 v7; // rdx
  _WORD *v8; // r8
  _WORD *v9; // rcx

  Pool2 = (_WORD *)ExAllocatePool2(256, 48, 1330467906);
  if ( !Pool2 )
  {
    v4 = -1073741670;
LABEL_13:
    Pool2 = 0;
    goto LABEL_16;
  }
  v5 = 2147483646;
  v6 = L"BTHENUM\\GENERIC_DEVICE";
  v7 = 24;
  v8 = Pool2;
  do
  {
    if ( !v5 )
      break;
    if ( !*v6 )
      break;
    *v8++ = *v6++;
    --v5;
    --v7;
  }
  while ( v7 );
  v9 = v8 - 1;
  v4 = v7 == 0 ? 0x80000005 : 0;
  if ( v7 )
    v9 = v8;
  *v9 = 0;
  if ( !v7 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        0,
        4,
        21,
        (__int64)WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids,
        -2147483643);
    ExFreePool(Pool2);
    goto LABEL_13;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_S(WPP_GLOBAL_Control->DeviceExtension, v7, (_DWORD)v8, 22);
LABEL_16:
  *a2 = Pool2;
  return v4;
}

```

## disassembly

```asm
0x140018008  push    rbx
0x14001800a  push    rbp
0x14001800b  push    rsi
0x14001800c  push    rdi
0x14001800d  sub     rsp, 38h
0x140018011  mov     rsi, rdx
0x140018014  mov     ecx, 100h
0x140018019  mov     edx, 30h ; '0'
0x14001801e  mov     r8d, 4F4D5442h
0x140018024  call    cs:__imp_ExAllocatePool2
0x14001802b  nop     dword ptr [rax+rax+00h]
0x140018030  xor     ebp, ebp
0x140018032  mov     rbx, rax
0x140018035  test    rax, rax
0x140018038  jnz     short loc_140018044
0x14001803a  mov     edi, 0C000009Ah
0x14001803f  jmp     loc_1400180E5
0x140018044  mov     eax, 7FFFFFFEh
0x140018049  lea     rcx, aBthenumGeneric; "BTHENUM\\GENERIC_DEVICE"
0x140018050  mov     edx, 18h
0x140018055  mov     r8, rbx
0x140018058  test    rax, rax
0x14001805b  jz      short loc_14001807C
0x14001805d  movzx   r9d, word ptr [rcx]
0x140018061  test    r9w, r9w
0x140018065  jz      short loc_14001807C
0x140018067  mov     [r8], r9w
0x14001806b  add     rcx, 2
0x14001806f  add     r8, 2
0x140018073  dec     rax
0x140018076  sub     rdx, 1
0x14001807a  jnz     short loc_140018058
0x14001807c  mov     rax, rdx
0x14001807f  lea     rcx, [r8-2]
0x140018083  neg     rax
0x140018086  sbb     edi, edi
0x140018088  not     edi
0x14001808a  and     edi, 80000005h
0x140018090  test    rdx, rdx
0x140018093  cmovnz  rcx, r8
0x140018097  mov     [rcx], bp
0x14001809a  jnz     short loc_1400180EA
0x14001809c  lea     rax, WPP_RECORDER_INITIALIZED
0x1400180a3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400180aa  jz      short loc_1400180D6
0x1400180ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400180b3  lea     rax, WPP_2de2e0e631453f5f69f68f01ca725c87_Traceguids
0x1400180ba  mov     r9d, 15h
0x1400180c0  mov     dword ptr [rsp+58h+var_30], edi
0x1400180c4  mov     [rsp+58h+var_38], rax
0x1400180c9  mov     rcx, [rcx+40h]
0x1400180cd  lea     r8d, [r9-11h]
0x1400180d1  call    WPP_RECORDER_SF_d
0x1400180d6  mov     rcx, rbx; P
0x1400180d9  call    cs:__imp_ExFreePool
0x1400180e0  nop     dword ptr [rax+rax+00h]
0x1400180e5  mov     rbx, rbp
0x1400180e8  jmp     short loc_140018115
0x1400180ea  lea     rax, WPP_RECORDER_INITIALIZED
0x1400180f1  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400180f8  jz      short loc_140018115
0x1400180fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140018101  mov     r9d, 16h
0x140018107  mov     [rsp+58h+var_30], rbx
0x14001810c  mov     rcx, [rcx+40h]
0x140018110  call    WPP_RECORDER_SF_S
0x140018115  mov     [rsi], rbx
0x140018118  mov     eax, edi
0x14001811a  add     rsp, 38h
0x14001811e  pop     rdi
0x14001811f  pop     rsi
0x140018120  pop     rbp
0x140018121  pop     rbx
0x140018122  retn
```
